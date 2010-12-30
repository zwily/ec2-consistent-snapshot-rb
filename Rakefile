require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "ec2-consistent-snapshot-rb"
  gem.homepage = "http://github.com/zwily/ec2-consistent-snapshot-rb"
  gem.license = "MIT"
  gem.summary = %Q{Takes EBS snapshots while locking MySQL and freezing XFS}
  gem.description = %Q{Ported from ec2-consistent-snapshot (http://alestic.com/2009/09/ec2-consistent-snapshot)}
  gem.email = "zach@zwily.com"
  gem.authors = ["Zach Wily"]
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

require 'rcov/rcovtask'
Rcov::RcovTask.new do |test|
  test.libs << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "ec2-consistent-snapshot-rb #{version}"
  rdoc.rdoc_files.include('README*')
end
