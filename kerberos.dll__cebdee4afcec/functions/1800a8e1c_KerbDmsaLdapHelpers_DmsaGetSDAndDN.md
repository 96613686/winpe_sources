# KerbDmsaLdapHelpers::DmsaGetSDAndDN

- ea: `0x1800a8e1c`
- end: `0x1800a9298`
- name: `KerbDmsaLdapHelpers::DmsaGetSDAndDN`
- size: `1148`
- prototype: `__int64 __fastcall(LDAP **, unsigned __int16 *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a8380`

## callees

- `0x1800093f0`
- `0x180032964`
- `0x180065c48`
- `0x180070680`
- `0x1800744cf`
- `0x1800797c8`
- `0x18007f63c`
- `0x18008b70c`
- `0x18008c4f0`
- `0x1800a8e1c`

## import_xrefs

- `WLDAP32!__imp_ldap_first_entry` at `0x1800a8f47`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800a9125`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800a8f47`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800a9125`
- `WLDAP32!__imp_ldap_count_entries` at `0x1800a90a3`
- `WLDAP32!__imp_ldap_count_entries` at `0x1800a90a3`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a8f12`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a8f6e`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a8fb5`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a908c`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a90f0`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a91dc`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a9217`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a9251`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a8f12`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a8f6e`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a8fb5`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a908c`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a90f0`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a91dc`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a9217`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800a9251`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800a8f30`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800a910e`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800a91fa`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800a9274`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800a8f30`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800a910e`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800a91fa`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800a9274`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800a8f57`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800a914f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800a8f57`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800a914f`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1800a9188`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1800a9188`
- `WLDAP32!__imp_ldap_search_sW` at `0x1800a8ede`
- `WLDAP32!__imp_ldap_search_sW` at `0x1800a904e`
- `WLDAP32!__imp_ldap_search_sW` at `0x1800a8ede`
- `WLDAP32!__imp_ldap_search_sW` at `0x1800a904e`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a8f1c`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a8f26`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a90fa`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a9104`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a91e6`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a91f0`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a9260`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a926a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a8f1c`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a8f26`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a90fa`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a9104`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a91e6`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a91f0`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a9260`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800a926a`

## string_xrefs

- `0x1800a8fe3`: `)(objectClass=msds-DelegatedManagedServiceAccount))`

## pseudocode

```c

```
