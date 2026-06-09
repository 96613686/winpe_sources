# CLdapWrapper::GetSecurityDescriptor(wchar_t const *,cxl::SecurityDescriptor &,ulong)

- ea: `0x1800a7d5c`
- end: `0x1800a7f8c`
- name: `?GetSecurityDescriptor@CLdapWrapper@@QEAAJPEB_WAEAVSecurityDescriptor@cxl@@K@Z`
- size: `560`
- prototype: `int(CLdapWrapper *__hidden this, const wchar_t *, struct SecurityDescriptor *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a3a0c`

## callees

- `0x180002f50`
- `0x18000d380`
- `0x18000d3e8`
- `0x18009ab0c`
- `0x1800a72d8`
- `0x1800a7448`
- `0x1800a7d5c`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800a7e81`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800a7eda`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800a7e81`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800a7eda`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800a7eaf`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800a7eaf`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a7f1c`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a7f1c`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800a7f2a`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800a7f2a`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1800a7ec6`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1800a7ec6`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x1800a7e75`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x1800a7e75`

## string_xrefs

- `0x1800a7dba`: `nTSecurityDescriptor`

## pseudocode

```c

```
