# ImportKey(_CAPI_FUNCTION_TABLE *,unsigned __int64,uint,uchar *,ulong,ulong,unsigned __int64 *)

- ea: `0x1800c4e10`
- end: `0x1800c4fc4`
- name: `?ImportKey@@YAHPEAU_CAPI_FUNCTION_TABLE@@_KIPEAEKKPEA_K@Z`
- size: `436`
- prototype: `int(struct _CAPI_FUNCTION_TABLE *, unsigned __int64, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800c5060`
- `0x1800c59a4`

## callees

- `0x1800018a4`
- `0x180004970`
- `0x1800c4e10`
- `0x1801614c4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4f17`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c4e47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c4e47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c4fab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c4fab`

## string_xrefs

- `0x1800c4e7d`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c4f3f`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`

## pseudocode

```c

```
