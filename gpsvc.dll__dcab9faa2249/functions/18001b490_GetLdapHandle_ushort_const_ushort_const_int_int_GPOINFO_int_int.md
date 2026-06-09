# GetLdapHandle(ushort const *,ushort const *,int,int,_GPOINFO *,int,int)

- ea: `0x18001b490`
- end: `0x18001bc80`
- name: `?GetLdapHandle@@YAPEAUldap@@PEBG0HHPEAU_GPOINFO@@HH@Z`
- size: `2032`
- prototype: `struct ldap *__usercall@<rax>(PWSTR HostName@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, int@<r9d>, struct _GPOINFO *, int, int)`
- caller_count: `4`
- callee_count: `14`
- tags: ``

## callers

- `0x18001bc88`
- `0x18005ce5c`
- `0x180095704`
- `0x18009cc38`

## callees

- `0x18001ae40`
- `0x18001b490`
- `0x180030bcc`
- `0x180067c90`
- `0x180067d58`
- `0x18006f470`
- `0x18006f894`
- `0x180073984`
- `0x180075ec0`
- `0x18007c910`
- `0x18007d320`
- `0x1800990ac`
- `0x1800ba1ec`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bb73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bb73`
- `WLDAP32!__imp_ldap_unbind` at `0x18001b998`
- `WLDAP32!__imp_ldap_unbind` at `0x18001b998`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001b793`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001b82b`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001b8af`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001b793`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001b82b`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001b8af`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001b690`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001b704`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001b690`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001b704`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b7a1`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b839`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b8c0`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b932`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001badb`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b7a1`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b839`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b8c0`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001b932`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001badb`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18001ba69`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18001ba69`
- `WLDAP32!__imp_ldap_connect` at `0x18001b924`
- `WLDAP32!__imp_ldap_connect` at `0x18001b924`
- `WLDAP32!__imp_ldap_initW` at `0x18001b64e`
- `WLDAP32!__imp_ldap_initW` at `0x18001b64e`

## string_xrefs

- `0x18001b6a0`: `GetLdapHandle:  ldap_open for <%s> failed with = 0x%x or %d`
- `0x18001b714`: `GetLdapHandle:  ldap_open for <%s> failed with = 0x%x or %d`

## pseudocode

```c

```
