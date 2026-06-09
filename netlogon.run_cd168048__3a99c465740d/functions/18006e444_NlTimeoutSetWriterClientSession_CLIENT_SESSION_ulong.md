# NlTimeoutSetWriterClientSession(_CLIENT_SESSION *,ulong)

- ea: `0x18006e444`
- end: `0x18006e504`
- name: `?NlTimeoutSetWriterClientSession@@YAHPEAU_CLIENT_SESSION@@K@Z`
- size: `192`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, DWORD dwMilliseconds)`
- caller_count: `25`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002346c`
- `0x180029218`
- `0x18002ada0`
- `0x180030078`
- `0x180031a3c`
- `0x180033b90`
- `0x180033f80`
- `0x180035924`
- `0x18004370c`
- `0x180047dfc`
- `0x18005239c`
- `0x18005c514`
- `0x18005dfe0`
- `0x18005eb90`
- `0x18005fa30`
- `0x180061580`
- `0x180061800`
- `0x180068008`
- `0x180069f80`
- `0x18006ad64`
- `0x18006b5b4`
- `0x18006e1bc`
- `0x180070380`
- `0x180073c20`
- `0x180075b60`

## callees

- `0x18000dd00`
- `0x180040f18`
- `0x18006e444`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006e47e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006e47e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e490`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e4e7`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e4e7`
- `ntdll!RtlEnterCriticalSection` at `0x18006e4ca`
- `ntdll!RtlEnterCriticalSection` at `0x18006e4ca`

## string_xrefs

- `0x18006e462`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006e49c`: `NlTimeoutSetWriterClientSession timed out: %ld %ld\n`

## pseudocode

```c

```
