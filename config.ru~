#\ -s puma
require 'dashing'

configure do
  set :auth_token, 'A3AEAF95-B123-4EB2-AA2A-1EB803809D23'

  helpers do
    def protected!
      # Put any authentication code you want in here.
      # This method is run before accessing any resource.
    end
  end
end

map Sinatra::Application.assets_prefix do
  run Sinatra::Application.sprockets
end

run Sinatra::Application

require "rack-timeout"
use Rack::Timeout          # Call as early as possible so rack-timeout runs before all other middleware.
Rack::Timeout.timeout = 5  # Recommended. If omitted, defaults to 15 seconds.
