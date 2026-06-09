# FilterCheck(ldap *,ldapmsg *,void *,ushort *,CGpoFilter *,CLocator *,int *,ushort * *,_GPWMIINFO *,_GPOINFO *)

- ea: `0x18009e9b4`
- end: `0x18009f399`
- name: `?FilterCheck@@YAHPEAUldap@@PEAUldapmsg@@PEAXPEAGPEAVCGpoFilter@@PEAVCLocator@@PEAHPEAPEAGPEAU_GPWMIINFO@@PEAU_GPOINFO@@@Z`
- size: `2533`
- prototype: `__int64 __usercall@<rax>(LDAP *ld@<rcx>, LDAPMessage *entry@<rdx>, void *@<r8>, unsigned __int16 *@<r9>, struct CGpoFilter *, struct CLocator *, int *, unsigned __int16 **, struct _GPWMIINFO *, struct _GPOINFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18003a810`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18001ee6c`
- `0x18002c690`
- `0x1800535a0`
- `0x1800585e8`
- `0x18005ce04`
- `0x180062fcc`
- `0x180075ec0`
- `0x18007d320`
- `0x18009e9b4`
- `0x1800a4b30`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009eb0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009f1ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009f35e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009eb0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009f1ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009f35e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ea40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009eaad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f2d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ea40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009eaad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f2d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f303`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009ede7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009ede7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009ea90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009ecff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009ea90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009ecff`
- `OLEAUT32!__imp_SysFreeString` at `0x18009efaa`
- `OLEAUT32!__imp_SysFreeString` at `0x18009efbf`
- `OLEAUT32!__imp_SysFreeString` at `0x18009efc9`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f035`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f10f`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f119`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f1af`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f1b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f23f`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f249`
- `OLEAUT32!__imp_SysFreeString` at `0x18009efaa`
- `OLEAUT32!__imp_SysFreeString` at `0x18009efbf`
- `OLEAUT32!__imp_SysFreeString` at `0x18009efc9`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f035`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f10f`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f119`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f1af`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f1b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f23f`
- `OLEAUT32!__imp_SysFreeString` at `0x18009f249`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18009ea56`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18009ea56`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18009eb06`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18009eb84`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18009eb06`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18009eb84`

## pseudocode

```c

```
