task :default => :lint

task :ruby => [] do
  begin
    sh 'for f in **/*.rb; do ruby -wc $f 2>&1 | grep -v "Syntax OK" | grep -v openssl | grep -v rubygems; done'
  rescue
  end
end

task :reek => [] do
  sh 'bundle exec reek -q .; true'
end

task :flay => [] do
  sh 'bundle exec flay .'
end

task :roodi => [] do
  sh 'bundle exec roodi -config=roodi.yml *.rb **/*.rb'
end

task :cane => [] do
  sh 'bundle exec cane -f *.rb; bundle exec cane **/*.rb'
end

task :excellent => [] do
  sh 'bundle exec excellent .'
end

task :rubocop => [] do
  sh 'bundle exec rubocop **/*.rb **/*.erb **/Guardfile*'
end

task :tailor => [] do
  sh 'bundle exec tailor'
end

task :cowl => [] do
  sh 'cowl .'
end

task :lint => [:ruby, :reek, :flay, :roodi, :cane, :excellent, :rubocop, :tailor, :cowl] do
end
