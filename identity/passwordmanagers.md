# Password Managers

Are you using the same password to many different web-sites/services?

Don't do this. However, don't use a `Password Manager` too. See why.

## Understanding the threat

Digital identities are essential to enable business in the internet era. Doing business in the digital modern world requires you to Know Your Customer (KYC) in order to run any kind of business. This is where the things become hard. Digital identity a user is hard because the characteristics of the internet and it's way of work (the protocols, tools, browsers, etc).

Secure digital credentials in most cases represented as a username id and password is challenging because it's supposed to be something private, non-disclosable and unique. In this way keep this credentials is a critical requirement for any business. In the same way, enforce security controls and mitigations is hard because in general you need to turn the solution less usable and easy for the end user.

On the other side, keep many different usernames and passwords is hard for the end user too. The opportunity to help digital users to keep this credentials safe is where some tools called Password Managers (PM) came in. PMs are softwares that, in general, enables the user to store, use and rotate credentials when using the internet. It's obvious that PM software will be the target of engaged attackers looking for credentials exfiltration. The main target of an attacker, in this case, is to have access to the user credentials and use them after.

PM solutions in general works together with web browsers providing a featured called Form Autofill, where users don't need to fill authentications forms manually, the PM software does this automatically bringing more convenience to the end user. The process starts when the user access for the first time the web-based application and the PM software stores the username, the password and many details about the context and the login form. After this, when the user came back to the same webpage with the same login form then the PM software autofill the username and password with the same credentials.

***The main threats, in this case, are credentials exfiltration and personal information exposition.***

An attacker can use multiple and different vectors and strategies to gain access to the user credentials. Some of them are: 1) main-in-the-middle, having access to network traffic, for example; 2) coffee shop attacker, controlling the user network or equipment (e.g routers); 3) Sweep attacks, using compromised web applications to exfiltrate passwords from the form autofill feature. Different PM software is vulnerable to different attacks based on the implementation decisions of the form autofill feature.

The privacy implications of this kind of attack are clearly terrible for the target. The tracking and web-advertisement industry are using these vulnerabilities to extract user emails from PMs and then track the user on the next pages visits, showing targeted advertisement. However, this breach can be used by an attacker as explained here. Some tools provide the Session Replay feature where is possible to see all the activity of the end user in your website, including when it's typing the credit card information, for example. (Full Story is one of them: https://www.fullstory.com/).

Almost all websites and web-based solutions use digital credentials (username and password) to keep systems secure and a password exfiltration can be really serious because can expose user personal and private data.  In the case of corporate or enterprise users, the examples of assets at risk are: financial, medical, social and business data.

## Weaponize this threat

To weaponize this vulnerability it's necessary to
1. Create a login form with exact same characteristics of the original one (like Facebook, Gmail, etc)
2. Create a wifi login page to "accept the terms of service" and add our login form as invisible login forms to the end of the page (this will force the PM to autofill the credentials). This page will have some javascript code to catch the typed username and password filled by the PM in runtime;
3. Create a server-side REST API to receive the exfiltrated credentials.

## References

1. https://freedom-to-tinker.com/2017/12/27/no-boundaries-for-user-identities-web-trackers-exploit-browser-login-managers/
2. http://randomwalker.info/publications/OpenWPM_1_million_site_tracking_measurement.pdf
3. https://github.com/EFForg/privacybadger
4. https://webtransparency.cs.princeton.edu/no_boundaries/autofill_sites.html
5. https://webtap.princeton.edu/
6. https://github.com/citp/OpenWPM
7. https://www.onaudience.com/index.php?action=dataexchange
8. https://www.fullstory.com/
