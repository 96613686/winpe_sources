# myLdapOpen(ushort const *,ulong,ldap * *,ushort * *,ushort * *)

- ea: `0x18002b07c`
- end: `0x18002b138`
- name: `?myLdapOpen@@YAJPEBGKPEAPEAUldap@@PEAPEAG2@Z`
- size: `188`
- prototype: `int(const unsigned __int16 *, unsigned int, struct ldap **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015c0c`

## callees

- `0x1800213f0`
- `0x18002ac84`
- `0x18002b07c`

## import_xrefs

- `certca!__imp_myRobustLdapBindEx` at `0x18002b0c2`
- `certca!__imp_myRobustLdapBindEx` at `0x18002b0c2`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002b0d5`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002b0d5`
- `WLDAP32!__imp_ldap_unbind` at `0x18002b120`
- `WLDAP32!__imp_ldap_unbind` at `0x18002b120`

## pseudocode

```c

```
