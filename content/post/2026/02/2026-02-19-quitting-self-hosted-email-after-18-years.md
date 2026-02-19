---
title: Quitting self-hosted email after 18 years
date: 2026-02-19
category:
  - linux
  - tech
---

Recently I was writing some code to send transactional emails for a project but I had to stop for some serious thought when it came time to configure the SMTP hostname and authentication details.

I'd been [self-hosting email for a long time](/2008/01/01/isp-style-mail-server-on-debian-vps/) so the first option was to start digging though old [Ansible playbooks](/2014/08/10/blogging-on-ansible/) to add additional domains and accounts to my existing setup. The downside to this would be that email deliverability is arguably a lot more challenging now and if the project ever got any traction I'd effectively be running an email hosting company. So I started looking at alternatives.

For purely transactional emails sending through Amazon SES appeared the best choice but I was also interested in having an inbox to send and receive project-related emails.

Most hosted email accounts were priced equivalent to what I'd been paying to rent a server but then I noticed [MXroute](https://mxroute.com/) was having a promotion: a one-off setup fee of $248 plus $1/year for unlimited domains and unlimited accounts. Plus the bulk of their business seemed to be transactional email. For a very reasonable price I could migrate away from running an email server completely as well as satisfy the email requirements of any number of projects. I couldn't argue against it.

After signing up and adding some domain and account details I ran [imapsync](https://imapsync.lamiral.info/) overnight to migrate across my Maildir from the existing server. The next day I updated the DNS for the domain, reconfigured the email clients on my laptop and phone and sent a test email from the project I was working on. Everything worked without a problem. A last run of imapsync to check just the inbox and I was confident I could shutdown the server and forget about the pain of self-hosted email. What a relief!
