# AdminConfiguredNameMappings::StaticQueryHelper(ldap *,DnsNetbiosNamePair * * *,ulong *)

- ea: `0x18001825c`
- end: `0x18001871a`
- name: `?StaticQueryHelper@AdminConfiguredNameMappings@@CAKPEAUldap@@PEAPEAPEAVDnsNetbiosNamePair@@PEAK@Z`
- size: `1214`
- prototype: `unsigned int __fastcall(LDAP *ld, struct DnsNetbiosNamePair ***, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x180017ddc`

## callees

- `0x18000b790`
- `0x18000e910`
- `0x18000f3e4`
- `0x180017790`
- `0x18001825c`
- `0x180018f38`
- `0x180018fac`
- `0x180019000`
- `0x18001906c`
- `0x1800190d4`
- `0x1800191e4`
- `0x18001a81c`
- `0x18001ba5c`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x1800186a6`
- `netutils!NetApiBufferFree` at `0x1800186d4`
- `netutils!NetApiBufferFree` at `0x1800186e4`
- `netutils!NetApiBufferFree` at `0x1800186a6`
- `netutils!NetApiBufferFree` at `0x1800186d4`
- `netutils!NetApiBufferFree` at `0x1800186e4`
- `netutils!NetApiBufferAllocate` at `0x18001855d`
- `netutils!NetApiBufferAllocate` at `0x18001855d`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180018426`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800184b4`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180018426`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800184b4`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001847f`
- `WLDAP32!__imp_ldap_first_entry` at `0x18001847f`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800186c5`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800186c5`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800184e3`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800184e3`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800184cd`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800184cd`
- `WLDAP32!__imp_ldap_search_sW` at `0x1800183de`
- `WLDAP32!__imp_ldap_search_sW` at `0x1800183de`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800186b5`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800186b5`

## string_xrefs

- `0x1800182ad`: `configurationNamingContext`
- `0x1800183c3`: `(objectClass=serviceConnectionPoint)`

## pseudocode

```c

```
