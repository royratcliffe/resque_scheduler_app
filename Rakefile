require 'resque_scheduler/tasks'

namespace :resque do
  task :setup do
    require 'resque'
    require 'resque_scheduler'
    require 'resque/scheduler'

    Resque::Scheduler.dynamic = true

    uri = URI.parse(ENV['REDIS_URL'])
    Resque.redis = Redis.new(host: uri.host, port: uri.port, password: uri.password)
  end
end
