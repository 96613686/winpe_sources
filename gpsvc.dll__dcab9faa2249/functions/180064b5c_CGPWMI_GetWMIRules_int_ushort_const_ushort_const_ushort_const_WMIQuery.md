# CGPWMI::GetWMIRules(int,ushort const *,ushort * const,ushort * const,_WMIQuery *)

- ea: `0x180064b5c`
- end: `0x180064f04`
- name: `?GetWMIRules@CGPWMI@@CAKHPEBGQEAG1PEAU_WMIQuery@@@Z`
- size: `936`
- prototype: `unsigned int __fastcall(int, const unsigned __int16 *, PWSTR base, PWSTR filter, struct _WMIQuery *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800a45d8`

## callees

- `0x180063ce4`
- `0x180064028`
- `0x180064b5c`
- `0x180064f0c`
- `0x18006f894`
- `0x1800741ec`
- `0x180075ec0`
- `0x1800a4918`
- `0x1800a4934`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064ed9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064b8a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180064dd9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180064dd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064e14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064e7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064e14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064e7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064e8e`
- `WLDAP32!__imp_ldap_first_entry` at `0x180064cfb`
- `WLDAP32!__imp_ldap_first_entry` at `0x180064cfb`
- `WLDAP32!__imp_ldap_next_entry` at `0x180064dfb`
- `WLDAP32!__imp_ldap_next_entry` at `0x180064dfb`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180064d26`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180064d65`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180064d26`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180064d65`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180064c88`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180064c88`

## pseudocode

```c

```
