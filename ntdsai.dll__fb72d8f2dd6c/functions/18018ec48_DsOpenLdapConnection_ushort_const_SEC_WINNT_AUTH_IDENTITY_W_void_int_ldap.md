# DsOpenLdapConnection(ushort const *,_SEC_WINNT_AUTH_IDENTITY_W *,void *,int,ldap * *)

- ea: `0x18018ec48`
- end: `0x18018ed39`
- name: `?DsOpenLdapConnection@@YAKPEBGPEAU_SEC_WINNT_AUTH_IDENTITY_W@@PEAXHPEAPEAUldap@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(WCHAR *, WCHAR *, void *, int, struct ldap **)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18018ca64`
- `0x18018ed40`
- `0x18018ef50`
- `0x180190aa8`

## callees

- `0x18018ec48`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18018ecd0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18018ecd0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18018ed0d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18018ed0d`
- `WLDAP32!__imp_ldap_unbind` at `0x18018ed1f`
- `WLDAP32!__imp_ldap_unbind` at `0x18018ed1f`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18018ecba`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18018ecba`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18018ec9e`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18018ecdf`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18018ed01`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18018ec9e`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18018ecdf`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18018ed01`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18018ecf5`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18018ecf5`
- `WLDAP32!__imp_ldap_connect` at `0x18018ec92`
- `WLDAP32!__imp_ldap_connect` at `0x18018ec92`
- `WLDAP32!__imp_ldap_initW` at `0x18018ec6a`
- `WLDAP32!__imp_ldap_initW` at `0x18018ec6a`

## pseudocode

```c

```
