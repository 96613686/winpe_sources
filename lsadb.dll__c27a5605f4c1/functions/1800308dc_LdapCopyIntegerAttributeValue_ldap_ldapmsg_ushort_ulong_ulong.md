# LdapCopyIntegerAttributeValue(ldap *,ldapmsg *,ushort *,ulong,ulong *)

- ea: `0x1800308dc`
- end: `0x180030944`
- name: `?LdapCopyIntegerAttributeValue@@YAKPEAUldap@@PEAUldapmsg@@PEAGKPEAK@Z`
- size: `104`
- prototype: `unsigned int __fastcall(struct ldap *, struct ldapmsg *, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ff34`
- `0x180030d3c`

## callees

- `0x1800308dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003090f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003090f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800308f9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800308f9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003092c`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003092c`

## pseudocode

```c

```
