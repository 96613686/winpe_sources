# EvaluateDeferredOUs(_DNENTRY *,ulong,void *,_GROUP_POLICY_OBJECTW * *,_GROUP_POLICY_OBJECTW * *,_SCOPEOFMGMT * *,_GPCONTAINER * *,int,ldap *,int *,void *,_GPOINFO *,int)

- ea: `0x18002d188`
- end: `0x18002d9b0`
- name: `?EvaluateDeferredOUs@@YAHPEAU_DNENTRY@@KPEAXPEAPEAU_GROUP_POLICY_OBJECTW@@2PEAPEAU_SCOPEOFMGMT@@PEAPEAU_GPCONTAINER@@HPEAUldap@@PEAH1PEAU_GPOINFO@@H@Z`
- size: `2088`
- prototype: `__int64 __usercall@<rax>(struct _DNENTRY *@<rcx>, unsigned int@<edx>, void *@<r8>, struct _GROUP_POLICY_OBJECTW **@<r9>, struct _GROUP_POLICY_OBJECTW **, struct _SCOPEOFMGMT **, struct _GPCONTAINER **, int, LDAP *ld, int *, void *, struct _GPOINFO *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800147b0`

## callees

- `0x18002c740`
- `0x18002d188`
- `0x180030bcc`
- `0x18003e060`
- `0x180053080`
- `0x180067d58`
- `0x18006f894`
- `0x18007060c`
- `0x180073984`
- `0x180075ec0`
- `0x18007d320`
- `0x1800ba1ec`
- `0x1800ba578`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d985`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d34e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d34e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d598`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d67c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d80c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d8f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d67c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d80c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d8f8`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18002d384`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18002d384`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002d395`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002d477`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002d787`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002d871`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002d395`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002d477`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002d787`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002d871`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18002d44d`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18002d44d`

## string_xrefs

- `0x18002d292`: `nTSecurityDescriptor`
- `0x18002d24e`: `gPLink`
- `0x18002d6f4`: `EvaluateDeferredOUs:  All objects can not be accessed.`
- `0x18002d71f`: `EvaluateDeferredOUs:  All objects can not be accessed.`
- `0x18002d7a8`: `EvalateDeferredOUs:  Too many linked GPOs in search.`
- `0x18002d7cb`: `EvalateDeferredOUs:  Too many linked GPOs in search.`
- `0x18002d622`: `EvaluateDeferredOUs: Object <%s> cannot be accessed`
- `0x18002d648`: `EvaluateDeferredOUs: Object <%s> cannot be accessed`

## pseudocode

```c

```
