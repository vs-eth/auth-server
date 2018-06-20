# Auth-Server
Set up OpenLDAP and MIT Kerberos to authenticate users. Tested on Debian 9.

## Note
Some settings only take effect if you set them before running the role for the first time, as they use `debconf` to be injected at installation time!

## Configuration
| Name | Default value | Description |
| ---- | ------------- | ----------- |
| `auth_ldap_domain` | `False` | Which base domain should be used for this role? |
| `auth_ldap_domain_ldap` | `False` | `auth_ldap_domain` in LDAP format (dc=...) |
| `auth_ldap_admin_pwd_clear` | `False` | The LDAP administrator password |
| `auth_ldap_admin_pwd` | `False` | The LDAP administrator password (hashed) |
| `auth_kerberos_ldap_password` | `False` | The kerberos LDAP service account password |
| `auth_kerberos_ldap_password_ldap` | `False` | The kerberos LDAP service account password (hashed) |
| `auth_kerberos_database_master_key` | `False` | The initial kerberos database master key |
| `auth_kerberos_enctypes` | `aes256-cts-hmac-sha384-192 aes128-cts-hmac-sha256-128` | Which encryption modes to enable? The default is for recent versions of Kerberos and no Windows clients only. |
| `auth_ldap_have_tls` | `True` | Whether to enable SSL/TLS support in openLDAP |
| `auth_ldap_ssl_cert_path` | `/etc/ldap/server.pem` | Path to openLDAP's certificate |
| `auth_ldap_ssl_key_path` | `/etc/ldap/server.key` | Path to openLDAP's certificate's key|
| `auth_ldap_ssl_ca_path` | `/etc/ldap/ca.pem` | Path to the CA certificate of openLDAP's certificate |

## License
Apache 2.0, except for `files/kerberos.ldif`, which is `CoPyRiGhT=(c) Copyright 2006, Novell, Inc.  All rights reserved` and has been extracted from the freely available openLDAP source.
