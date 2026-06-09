# CreateCrossRefDataFromLdapResult(ldap *,ldapmsg *,_CROSSREF_DATA * *)

- ea: `0x18002ff34`
- end: `0x18003008e`
- name: `?CreateCrossRefDataFromLdapResult@@YAKPEAUldap@@PEAUldapmsg@@PEAPEAU_CROSSREF_DATA@@@Z`
- size: `346`
- prototype: `unsigned int __fastcall(struct ldap *, struct ldapmsg *, struct _CROSSREF_DATA **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180030aa8`

## callees

- `0x18002fe60`
- `0x18002ff34`
- `0x1800305bc`
- `0x1800308dc`
- `0x18003094c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ff59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ff59`
- `WLDAP32!__imp_LdapGetLastError` at `0x18002ff8c`
- `WLDAP32!__imp_LdapGetLastError` at `0x18002ff8c`
- `WLDAP32!__imp_ldap_get_dnW` at `0x18002ff7e`
- `WLDAP32!__imp_ldap_get_dnW` at `0x18002ff7e`
- `WLDAP32!__imp_ldap_memfreeW` at `0x180030071`
- `WLDAP32!__imp_ldap_memfreeW` at `0x180030071`

## pseudocode

```c

```
