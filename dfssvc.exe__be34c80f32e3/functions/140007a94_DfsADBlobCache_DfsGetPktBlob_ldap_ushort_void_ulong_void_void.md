# DfsADBlobCache::DfsGetPktBlob(ldap *,ushort *,void * *,ulong *,void * *,void * *)

- ea: `0x140007a94`
- end: `0x140007d32`
- name: `?DfsGetPktBlob@DfsADBlobCache@@QEAAKPEAUldap@@PEAGPEAPEAXPEAK22@Z`
- size: `670`
- prototype: `unsigned int(DfsADBlobCache *__hidden this, struct ldap *, unsigned __int16 *, void **, unsigned int *, void **, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140009220`

## callees

- `0x140005ad8`
- `0x140005b28`
- `0x140005b90`
- `0x140006bf0`
- `0x140007a94`

## import_xrefs

- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140007c41`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140007c9e`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140007c41`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140007c9e`
- `WLDAP32!__imp_ldap_first_entry` at `0x140007bcb`
- `WLDAP32!__imp_ldap_first_entry` at `0x140007bcb`
- `WLDAP32!__imp_ldap_msgfree` at `0x140007d07`
- `WLDAP32!__imp_ldap_msgfree` at `0x140007d07`
- `WLDAP32!__imp_ldap_count_values_len` at `0x140007bfc`
- `WLDAP32!__imp_ldap_count_values_len` at `0x140007bfc`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x140007bea`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x140007bea`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x140007b6b`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x140007b6b`

## pseudocode

```c

```
