# NetpGetAccountObject(ldap *,ushort const *,ushort const *,ushort * *,int *)

- ea: `0x180061e88`
- end: `0x18006226a`
- name: `?NetpGetAccountObject@@YAJPEAUldap@@PEBG1PEAPEAGPEAH@Z`
- size: `994`
- prototype: `__int64 __fastcall(LDAP *ld, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180060fa4`
- `0x180061a74`
- `0x180062270`
- `0x180062bb8`
- `0x180062ee0`

## callees

- `0x180007278`
- `0x18000e270`
- `0x1800615f0`
- `0x180061a04`
- `0x180061e88`
- `0x1800627cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006219e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006219e`
- `netutils!NetApiBufferFree` at `0x180062091`
- `netutils!NetApiBufferFree` at `0x18006214a`
- `netutils!NetApiBufferFree` at `0x180062091`
- `netutils!NetApiBufferFree` at `0x18006214a`
- `WLDAP32!__imp_ldap_first_entry` at `0x180061f80`
- `WLDAP32!__imp_ldap_first_entry` at `0x18006211c`
- `WLDAP32!__imp_ldap_first_entry` at `0x180061f80`
- `WLDAP32!__imp_ldap_first_entry` at `0x18006211c`
- `WLDAP32!__imp_ldap_count_entries` at `0x180062056`
- `WLDAP32!__imp_ldap_count_entries` at `0x180062056`
- `WLDAP32!__imp_ldap_msgfree` at `0x180061fa1`
- `WLDAP32!__imp_ldap_msgfree` at `0x18006207b`
- `WLDAP32!__imp_ldap_msgfree` at `0x18006213c`
- `WLDAP32!__imp_ldap_msgfree` at `0x180061fa1`
- `WLDAP32!__imp_ldap_msgfree` at `0x18006207b`
- `WLDAP32!__imp_ldap_msgfree` at `0x18006213c`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180061f90`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18006217c`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800621c0`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180061f90`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18006217c`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800621c0`
- `WLDAP32!__imp_ldap_search_sW` at `0x180061f52`
- `WLDAP32!__imp_ldap_search_sW` at `0x180062038`
- `WLDAP32!__imp_ldap_search_sW` at `0x180061f52`
- `WLDAP32!__imp_ldap_search_sW` at `0x180062038`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180062158`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800621b0`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180062218`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180062158`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800621b0`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180062218`

## string_xrefs

- `0x180061f0a`: `GetAccountObject: attempting to find DN for %s\n`
- `0x1800620d7`: `GetAccountObject: account %s not found with appended $.  Was it already present?\n`

## pseudocode

```c

```
