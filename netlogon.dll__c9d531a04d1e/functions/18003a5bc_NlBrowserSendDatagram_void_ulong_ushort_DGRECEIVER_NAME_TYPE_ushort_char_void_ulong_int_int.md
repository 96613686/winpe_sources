# NlBrowserSendDatagram(void *,ulong,ushort *,_DGRECEIVER_NAME_TYPE,ushort *,char *,void *,ulong,int,int *)

- ea: `0x18003a5bc`
- end: `0x18003a9b1`
- name: `?NlBrowserSendDatagram@@YAJPEAXKPEAGW4_DGRECEIVER_NAME_TYPE@@1PEAD0KHPEAH@Z`
- size: `1013`
- prototype: `__int64 __fastcall(__int64, unsigned int, const WCHAR *, unsigned int, PCWSTR SourceString, char *Source, unsigned __int8 *, DWORD, int, _DWORD *)`
- caller_count: `5`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18000b1c4`
- `0x18003a5bc`
- `0x18003a9b8`
- `0x18007070c`
- `0x18007b398`

## callees

- `0x180003200`
- `0x180003670`
- `0x180007278`
- `0x18000d710`
- `0x18001606c`
- `0x18003a09c`
- `0x18003a5bc`
- `0x18003af24`
- `0x18003f054`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18003a8a0`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18003a8a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003a8d8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003a907`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003a8d8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003a907`
- `ntdll!RtlLeaveCriticalSection` at `0x18003a664`
- `ntdll!RtlLeaveCriticalSection` at `0x18003a784`
- `ntdll!RtlLeaveCriticalSection` at `0x18003a798`
- `ntdll!RtlLeaveCriticalSection` at `0x18003a664`
- `ntdll!RtlLeaveCriticalSection` at `0x18003a784`
- `ntdll!RtlLeaveCriticalSection` at `0x18003a798`
- `ntdll!RtlEnterCriticalSection` at `0x18003a60b`
- `ntdll!RtlEnterCriticalSection` at `0x18003a739`
- `ntdll!RtlEnterCriticalSection` at `0x18003a60b`
- `ntdll!RtlEnterCriticalSection` at `0x18003a739`
- `ntdll!RtlInitUnicodeString` at `0x18003a8e5`
- `ntdll!RtlInitUnicodeString` at `0x18003a914`
- `ntdll!RtlInitUnicodeString` at `0x18003a8e5`
- `ntdll!RtlInitUnicodeString` at `0x18003a914`

## string_xrefs

- `0x18003a69a`: `onecore\ds\netapi\svcdlls\logonsrv\server\mailslot.cxx`

## pseudocode

```c

```
