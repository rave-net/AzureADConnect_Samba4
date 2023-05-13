# Changelog


## [2023-05-13]
- Support for writing "CN=62a0ff2e-97b9-4513-943f-0d221bd30080,CN=Device Registration Configuration" in samba4
- Add azureadname config in azure.conf (use for write CN=Device Registration Configuration) 

## [2023-05-10]
- Add Device synchronization in sync (configuration in conf file)
- Force usertype in dict (restart a forced sync for users)
- Add onPremiseSecurityIdentifier and usercertificate for the user

## [2023-05-09]
- Add "do_delete" in the configuration file, if True, delete accounts with a "sourceanchor" online and not found in samba

## [2023-05-03]
- Switch from saving the last sendings of a json file to a sqlite database (restart of a forced synchronization)

## [2023-04-29]
- added backward compatibility of samba 4.13

## [2023-04-28]
- Added "hash_synchronization" option in the configuration file 

## [2023-04-27 - 2023-04-26]
switch to "microsoft azure ad connect" operating mode:
- Choice of sourceanchor in the configuration file
- objectGUID and ObjectSid are not decoded (byte) (convert to base64 when sending to azuread)
- possibility to use ms-ds-consistencyguid
- Added the possibility of a sourceanchor objectSID_str for backward compatibility with old version of the project.

## [2023-04-24]
- Added a pause when sending the password hash, otherwise too fast between account creation and password sending.
- Sending the group twice for nested groups, otherwise too fast between the creation of groups.

## [2023-04-21 - 2023-04-20]
- added "adsync" and "PasswordHashSync" enable (allows to run the script on an instance that has never seen "microsoft azure ad connect")

## [2023-02-02]
- Send only if data change, write last data send in json file
- Add attributes in the sync

## [2023-02-01]
- first working version, use obectsid decoded for sourceanchor