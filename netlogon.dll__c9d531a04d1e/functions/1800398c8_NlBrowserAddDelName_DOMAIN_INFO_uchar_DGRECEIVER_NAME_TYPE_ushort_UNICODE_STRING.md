# NlBrowserAddDelName(_DOMAIN_INFO *,uchar,_DGRECEIVER_NAME_TYPE,ushort *,_UNICODE_STRING *)

- ea: `0x1800398c8`
- end: `0x180039a7e`
- name: `?NlBrowserAddDelName@@YAJPEAU_DOMAIN_INFO@@EW4_DGRECEIVER_NAME_TYPE@@PEAGPEAU_UNICODE_STRING@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(__int64, char, __int64, __int64, const void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180039a84`
- `0x180039df4`

## callees

- `0x180003200`
- `0x180003670`
- `0x18000d710`
- `0x1800398c8`
- `0x18003a09c`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800399d7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180039a01`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800399d7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180039a01`
- `ntdll!RtlInitUnicodeString` at `0x1800399c1`
- `ntdll!RtlInitUnicodeString` at `0x1800399e4`
- `ntdll!RtlInitUnicodeString` at `0x180039a0e`
- `ntdll!RtlInitUnicodeString` at `0x1800399c1`
- `ntdll!RtlInitUnicodeString` at `0x1800399e4`
- `ntdll!RtlInitUnicodeString` at `0x180039a0e`

## string_xrefs

- `0x18003997e`: `onecore\ds\netapi\svcdlls\logonsrv\server\mailslot.cxx`

## pseudocode

```c

```
