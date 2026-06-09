# NetpGetAccountObject(ldap *,ushort const *,ushort const *,ushort * *,int *)

- ea: `0x18006655c`
- end: `0x1800669a9`
- name: `?NetpGetAccountObject@@YAJPEAUldap@@PEBG1PEAPEAGPEAH@Z`
- size: `1101`
- prototype: `__int64 __usercall@<rax>(LDAP *ld@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 **@<r9>, int *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180065520`
- `0x1800660e0`
- `0x1800669b0`
- `0x180067400`
- `0x180067760`

## callees

- `0x180007518`
- `0x18000e910`
- `0x180065bec`
- `0x180066068`
- `0x18006655c`
- `0x180066fb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800668c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800668c4`
- `netutils!NetApiBufferFree` at `0x180066793`
- `netutils!NetApiBufferFree` at `0x18006685e`
- `netutils!NetApiBufferFree` at `0x180066793`
- `netutils!NetApiBufferFree` at `0x18006685e`
- `WLDAP32!__imp_ldap_first_entry` at `0x18006665a`
- `WLDAP32!__imp_ldap_first_entry` at `0x180066824`
- `WLDAP32!__imp_ldap_first_entry` at `0x18006665a`
- `WLDAP32!__imp_ldap_first_entry` at `0x180066824`
- `WLDAP32!__imp_ldap_count_entries` at `0x180066748`
- `WLDAP32!__imp_ldap_count_entries` at `0x180066748`
- `WLDAP32!__imp_ldap_msgfree` at `0x180066687`
- `WLDAP32!__imp_ldap_msgfree` at `0x180066777`
- `WLDAP32!__imp_ldap_msgfree` at `0x18006684a`
- `WLDAP32!__imp_ldap_msgfree` at `0x180066687`
- `WLDAP32!__imp_ldap_msgfree` at `0x180066777`
- `WLDAP32!__imp_ldap_msgfree` at `0x18006684a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180066670`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18006689c`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800668f2`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180066670`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18006689c`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800668f2`
- `WLDAP32!__imp_ldap_search_sW` at `0x180066626`
- `WLDAP32!__imp_ldap_search_sW` at `0x180066724`
- `WLDAP32!__imp_ldap_search_sW` at `0x180066626`
- `WLDAP32!__imp_ldap_search_sW` at `0x180066724`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180066872`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800668dc`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180066950`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180066872`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800668dc`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180066950`

## string_xrefs

- `0x1800665de`: `GetAccountObject: attempting to find DN for %s\n`
- `0x1800667df`: `GetAccountObject: account %s not found with appended $.  Was it already present?\n`

## pseudocode

```c

```
