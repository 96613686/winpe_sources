# NlSetDsSPNWorker(_NL_SPN_UPDATE *)

- ea: `0x18005d090`
- end: `0x18005db85`
- name: `?NlSetDsSPNWorker@@YAKPEAU_NL_SPN_UPDATE@@@Z`
- size: `2805`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005cdb4`

## callees

- `0x180007518`
- `0x18000e910`
- `0x18000f4a4`
- `0x18000f508`
- `0x180041fbc`
- `0x18005d090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005d2d1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005d35e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005d488`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005d4a1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005d4bd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005d2d1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005d35e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005d488`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005d4a1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005d4bd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005d2bb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005d348`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005d46c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005d2bb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005d348`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005d46c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d729`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d292`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d31f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d292`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d31f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005db3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005db53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005db3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005db53`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x18005daf8`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x18005daf8`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x18005d57a`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x18005d57a`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x18005d4e4`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x18005d4e4`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x18005dae2`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x18005dae2`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18005d75a`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18005d7b8`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18005d7f3`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18005d75a`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18005d7b8`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18005d7f3`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18005d9db`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18005d9db`
- `WLDAP32!__imp_ldap_result` at `0x18005d8d5`
- `WLDAP32!__imp_ldap_result` at `0x18005d8d5`
- `WLDAP32!__imp_ldap_msgfree` at `0x18005db0e`
- `WLDAP32!__imp_ldap_msgfree` at `0x18005db0e`
- `WLDAP32!__imp_ldap_unbind_s` at `0x18005db22`
- `WLDAP32!__imp_ldap_unbind_s` at `0x18005db22`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18005d82d`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18005d82d`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d76e`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d7cc`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d807`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d841`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d88a`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d91d`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d965`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d76e`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d7cc`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d807`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d841`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d88a`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d91d`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18005d965`
- `WLDAP32!__imp_ldap_initW` at `0x18005d715`
- `WLDAP32!__imp_ldap_initW` at `0x18005d715`
- `WLDAP32!__imp_ldap_modify_extW` at `0x18005d876`
- `WLDAP32!__imp_ldap_modify_extW` at `0x18005d876`

## string_xrefs

- `0x18005d3a2`: `ServicePrincipalName`

## pseudocode

```c

```
