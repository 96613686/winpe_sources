# DsCreateBranchKrbTGTAccount(ushort *,ldap *,ldap *,ushort * *)

- ea: `0x18018dd04`
- end: `0x18018deeb`
- name: `?DsCreateBranchKrbTGTAccount@@YAKPEAGPEAUldap@@1PEAPEAG@Z`
- size: `487`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct ldap *, struct ldap *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18018ef50`

## callees

- `0x18001e090`
- `0x180167220`
- `0x18018dc04`
- `0x18018dd04`
- `0x18018def4`
- `0x18018e3e8`
- `0x18018e684`
- `0x18018eab8`

## import_xrefs

- `WLDAP32!__imp_LdapGetLastError` at `0x18018de60`
- `WLDAP32!__imp_LdapGetLastError` at `0x18018de60`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18018de75`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18018de75`
- `WLDAP32!__imp_ldap_first_entry` at `0x18018de06`
- `WLDAP32!__imp_ldap_first_entry` at `0x18018de06`
- `WLDAP32!__imp_ldap_msgfree` at `0x18018de9a`
- `WLDAP32!__imp_ldap_msgfree` at `0x1804628c0`
- `WLDAP32!__imp_ldap_msgfree` at `0x18018de9a`
- `WLDAP32!__imp_ldap_msgfree` at `0x1804628c0`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18018de1c`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18018de1c`
- `WLDAP32!__imp_ldap_search_sW` at `0x18018ddf4`
- `WLDAP32!__imp_ldap_search_sW` at `0x18018ddf4`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18018deb1`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1804628d7`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18018deb1`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1804628d7`

## string_xrefs

- `0x18018dd3d`: `dsServiceName`

## pseudocode

```c

```
