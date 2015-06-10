require "erb"

desc "README.md + template.html.erb -> index.html"
task :md2html do
  @content = File.read("#{__dir__}/README.md")

  # README.mdの1行目をtitleにする
  @title = @content.lines.first.gsub(/^#+\s*/, "").strip

  body = ERB.new(File.read("#{__dir__}/template.html.erb")).result
  File.open("#{__dir__}/index.html", "wb") do |f|
    f.write(body)
  end
end

task :default => :md2html
