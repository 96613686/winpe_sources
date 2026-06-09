# DsUpdateSPNsOnComputerObject(ldap *,_GUID *,ushort const *,ushort * *)

- ea: `0x18018f88c`
- end: `0x18019001c`
- name: `?DsUpdateSPNsOnComputerObject@@YAKPEAUldap@@PEAU_GUID@@PEBGPEAPEAG@Z`
- size: `1936`
- prototype: `__int64 __fastcall(LDAP *ld, struct _GUID *, WCHAR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18018ef50`

## callees

- `0x180006330`
- `0x18001e090`
- `0x18001ea60`
- `0x1800ef72c`
- `0x180166ee0`
- `0x180167220`
- `0x180173e2c`
- `0x18018e734`
- `0x18018e9d0`
- `0x18018f88c`
- `0x180192394`
- `0x180197ef0`
- `0x18026331c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18018f8e0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18018f8e0`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18018f9d6`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18018f9d6`
- `WLDAP32!__imp_ldap_first_entry` at `0x18018f9eb`
- `WLDAP32!__imp_ldap_first_entry` at `0x18018f9eb`
- `WLDAP32!__imp_ldap_msgfree` at `0x18018fb58`
- `WLDAP32!__imp_ldap_msgfree` at `0x18018ffa4`
- `WLDAP32!__imp_ldap_msgfree` at `0x18018fb58`
- `WLDAP32!__imp_ldap_msgfree` at `0x18018ffa4`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18018fa07`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18018fa3d`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18018fa07`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18018fa3d`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x18018fed4`
- `WLDAP32!__imp_ldap_modify_ext_sW` at `0x18018fed4`
- `WLDAP32!__imp_ldap_search_sW` at `0x18018f9c7`
- `WLDAP32!__imp_ldap_search_sW` at `0x18018f9c7`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18018ffb2`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18018ffc0`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18018ffb2`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18018ffc0`

## string_xrefs

- `0x18018fe3a`: `servicePrincipalName`

## pseudocode

```c

```
