# CGPWMI::GetLDAPHandle(int,ushort const *,ldap * *)

- ea: `0x180064f0c`
- end: `0x180065201`
- name: `?GetLDAPHandle@CGPWMI@@CAKHPEBGPEAPEAUldap@@@Z`
- size: `757`
- prototype: `static unsigned int(int, const unsigned __int16 *, struct ldap **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180064b5c`

## callees

- `0x180064f0c`
- `0x18006f894`
- `0x180075ec0`
- `0x1800a4918`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800651d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800651d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fdd`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18006501f`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18006501f`
- `WLDAP32!__imp_LdapGetLastError` at `0x180064f9c`
- `WLDAP32!__imp_LdapGetLastError` at `0x180064fe5`
- `WLDAP32!__imp_LdapGetLastError` at `0x180064f9c`
- `WLDAP32!__imp_LdapGetLastError` at `0x180064fe5`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800651b3`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800651b3`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180065154`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180065154`
- `WLDAP32!__imp_ldap_connect` at `0x18006509d`
- `WLDAP32!__imp_ldap_connect` at `0x18006509d`
- `WLDAP32!__imp_ldap_initW` at `0x180064f60`
- `WLDAP32!__imp_ldap_initW` at `0x180064f60`

## string_xrefs

- `0x180064fac`: `GetLDAPHandle:  ldap_open for <%s> failed with = 0x%x or %d`
- `0x180064ff5`: `GetLDAPHandle:  ldap_open for <%s> failed with = 0x%x or %d`

## pseudocode

```c

```
