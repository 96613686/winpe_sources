# Config::AdQuery::GetNextSearchPage(ldapcontrolW * *)

- ea: `0x1401e8058`
- end: `0x1401e8338`
- name: `?GetNextSearchPage@AdQuery@Config@@IEAAPEAVFrsStatus@@PEAPEAUldapcontrolW@@@Z`
- size: `736`
- prototype: `struct FrsStatus *(Config::AdQuery *__hidden this, struct ldapcontrolW **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1401e7efc`

## callees

- `0x14000cd1c`
- `0x1401b90b4`
- `0x1401b9494`
- `0x1401e8058`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401e8280`
- `KERNEL32!GetCurrentThreadId` at `0x1401e82d8`
- `KERNEL32!GetCurrentThreadId` at `0x1401e8280`
- `KERNEL32!GetCurrentThreadId` at `0x1401e82d8`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1401e8290`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1401e8290`
- `WLDAP32!__imp_ber_bvfree` at `0x1401e820a`
- `WLDAP32!__imp_ber_bvfree` at `0x1401e820a`
- `WLDAP32!__imp_ldap_controls_freeW` at `0x1401e81fa`
- `WLDAP32!__imp_ldap_controls_freeW` at `0x1401e81fa`
- `WLDAP32!__imp_ldap_create_page_controlW` at `0x1401e8121`
- `WLDAP32!__imp_ldap_create_page_controlW` at `0x1401e8121`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1401e8180`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1401e81d2`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1401e825c`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1401e8180`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1401e81d2`
- `WLDAP32!__imp_ldap_err2stringW` at `0x1401e825c`
- `WLDAP32!__imp_ldap_parse_page_controlW` at `0x1401e80dd`
- `WLDAP32!__imp_ldap_parse_page_controlW` at `0x1401e80dd`
- `WLDAP32!__imp_ldap_parse_resultW` at `0x1401e80b1`
- `WLDAP32!__imp_ldap_parse_resultW` at `0x1401e80b1`

## string_xrefs

- `0x1401e818c`: `Failed to ldap_create_page_control(). Error:%?`
- `0x1401e815a`: `Config::AdQuery::GetNextSearchPage`
- `0x1401e81ac`: `Config::AdQuery::GetNextSearchPage`
- `0x1401e8236`: `Config::AdQuery::GetNextSearchPage`
- `0x1401e82a1`: `Config::AdQuery::GetNextSearchPage`

## pseudocode

```c

```
