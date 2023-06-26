require 'rake'
require 'filewatcher'

MAIN_PATH = 'lib/main.c'
BUILD_PATH = 'build/lil-lisp'

task :watch do
  Filewatcher.new(['lib/**/*.c', 'lib/**/*.h']).watch do |update|
    update.each_key do |filename|
      system("echo 'File #{File.basename(filename)} changed!'")
    end
    system "cc -std=c99 -Wall #{MAIN_PATH} -o #{BUILD_PATH}"
  end

  filewatcher.start
end

task :build do
  system "cc -std=c99 -Wall #{MAIN_PATH} -o #{BUILD_PATH}"
end

task :run do
  system "cc -std=c99 -Wall #{MAIN_PATH} -o #{BUILD_PATH}"
  system "./#{BUILD_PATH}"
end
