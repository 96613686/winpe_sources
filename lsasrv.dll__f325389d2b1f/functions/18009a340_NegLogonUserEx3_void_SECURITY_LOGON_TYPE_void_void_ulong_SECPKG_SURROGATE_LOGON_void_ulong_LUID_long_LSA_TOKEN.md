# NegLogonUserEx3(void * *,_SECURITY_LOGON_TYPE,void *,void *,ulong,_SECPKG_SURROGATE_LOGON *,void * *,ulong *,_LUID *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x18009a340`
- end: `0x18009ac49`
- name: `?NegLogonUserEx3@@YAJPEAPEAXW4_SECURITY_LOGON_TYPE@@PEAX2KPEAU_SECPKG_SURROGATE_LOGON@@0PEAKPEAU_LUID@@PEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@0PEAPEAU_UNICODE_STRING@@88PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `2313`
- prototype: `int(void **, enum _SECURITY_LOGON_TYPE, void *, void *, unsigned int, struct _SECPKG_SURROGATE_LOGON *, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800093b0`
- `0x180009410`
- `0x18000b7d0`
- `0x18000c300`
- `0x1800163d0`
- `0x180016f70`
- `0x18001ec40`
- `0x180021230`
- `0x18002620c`
- `0x180052990`
- `0x180056f84`
- `0x18007b134`
- `0x18007eedc`
- `0x180081b18`
- `0x180081c38`
- `0x180087264`
- `0x18009a340`
- `0x18009ac50`
- `0x1800b86d0`
- `0x1800bd6e0`
- `0x1800d35d4`
- `0x1800d529c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18009a662`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18009a662`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18009a685`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18009a685`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a5b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a5c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a5b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a5c8`
- `ntdll!EtwEventActivityIdControl` at `0x18009a924`
- `ntdll!EtwEventActivityIdControl` at `0x18009ab8d`
- `ntdll!EtwEventActivityIdControl` at `0x18009a924`
- `ntdll!EtwEventActivityIdControl` at `0x18009ab8d`
- `ntdll!RtlEqualUnicodeString` at `0x18009a500`
- `ntdll!RtlEqualUnicodeString` at `0x18009a500`
- `ntdll!RtlInitUnicodeString` at `0x18009a4e9`
- `ntdll!RtlInitUnicodeString` at `0x18009a4e9`

## pseudocode

```c

```
