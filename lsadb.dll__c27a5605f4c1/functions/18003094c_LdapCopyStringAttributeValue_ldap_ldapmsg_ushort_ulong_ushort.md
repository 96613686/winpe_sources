# LdapCopyStringAttributeValue(ldap *,ldapmsg *,ushort *,ulong,ushort * *)

- ea: `0x18003094c`
- end: `0x1800309c9`
- name: `?LdapCopyStringAttributeValue@@YAKPEAUldap@@PEAUldapmsg@@PEAGKPEAPEAG@Z`
- size: `125`
- prototype: `unsigned int __fastcall(struct ldap *, struct ldapmsg *, unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ff34`

## callees

- `0x18002fe60`
- `0x18003094c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800309ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800309ae`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003096b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003096b`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800309b7`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800309b7`

## pseudocode

```c

```
