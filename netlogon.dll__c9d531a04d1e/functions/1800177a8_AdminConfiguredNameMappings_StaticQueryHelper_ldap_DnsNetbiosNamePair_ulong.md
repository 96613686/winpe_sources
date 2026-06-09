# AdminConfiguredNameMappings::StaticQueryHelper(ldap *,DnsNetbiosNamePair * * *,ulong *)

- ea: `0x1800177a8`
- end: `0x180017c1d`
- name: `?StaticQueryHelper@AdminConfiguredNameMappings@@CAKPEAUldap@@PEAPEAPEAVDnsNetbiosNamePair@@PEAK@Z`
- size: `1141`
- prototype: `unsigned int __fastcall(LDAP *ld, struct DnsNetbiosNamePair ***, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x180017340`

## callees

- `0x18000b790`
- `0x18000e270`
- `0x18000ed34`
- `0x180016d34`
- `0x1800177a8`
- `0x180018414`
- `0x18001847c`
- `0x1800184c8`
- `0x18001852c`
- `0x18001858c`
- `0x180018690`
- `0x180019be8`
- `0x18001ac94`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x180017bc8`
- `netutils!NetApiBufferFree` at `0x180017be4`
- `netutils!NetApiBufferFree` at `0x180017bee`
- `netutils!NetApiBufferFree` at `0x180017bc8`
- `netutils!NetApiBufferFree` at `0x180017be4`
- `netutils!NetApiBufferFree` at `0x180017bee`
- `netutils!NetApiBufferAllocate` at `0x180017a85`
- `netutils!NetApiBufferAllocate` at `0x180017a85`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001796c`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800179ee`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001796c`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800179ee`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800179bf`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800179bf`
- `WLDAP32!__imp_ldap_msgfree` at `0x180017bdb`
- `WLDAP32!__imp_ldap_msgfree` at `0x180017bdb`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180017a11`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180017a11`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180017a01`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180017a01`
- `WLDAP32!__imp_ldap_search_sW` at `0x18001792a`
- `WLDAP32!__imp_ldap_search_sW` at `0x18001792a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180017bd1`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180017bd1`

## string_xrefs

- `0x1800177f9`: `configurationNamingContext`
- `0x18001790f`: `(objectClass=serviceConnectionPoint)`

## pseudocode

```c

```
