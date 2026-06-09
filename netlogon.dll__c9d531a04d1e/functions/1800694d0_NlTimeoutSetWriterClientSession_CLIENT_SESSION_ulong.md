# NlTimeoutSetWriterClientSession(_CLIENT_SESSION *,ulong)

- ea: `0x1800694d0`
- end: `0x180069577`
- name: `?NlTimeoutSetWriterClientSession@@YAHPEAU_CLIENT_SESSION@@K@Z`
- size: `167`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *, DWORD dwMilliseconds)`
- caller_count: `25`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180022374`
- `0x180027d78`
- `0x180029680`
- `0x18002e478`
- `0x18002fdb4`
- `0x180031d90`
- `0x180032160`
- `0x180033a34`
- `0x180040bf8`
- `0x180044eb8`
- `0x18004ecb8`
- `0x1800585a0`
- `0x180059e9c`
- `0x18005a990`
- `0x18005b7e0`
- `0x18005d1c0`
- `0x18005d440`
- `0x1800636d4`
- `0x180065440`
- `0x180066108`
- `0x180066904`
- `0x18006925c`
- `0x18006b2e0`
- `0x18006e960`
- `0x18007070c`

## callees

- `0x18000d710`
- `0x18003e71c`
- `0x1800694d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006950a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006950a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069516`
- `ntdll!RtlLeaveCriticalSection` at `0x180069561`
- `ntdll!RtlLeaveCriticalSection` at `0x180069561`
- `ntdll!RtlEnterCriticalSection` at `0x18006954a`
- `ntdll!RtlEnterCriticalSection` at `0x18006954a`

## string_xrefs

- `0x1800694ee`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006951c`: `NlTimeoutSetWriterClientSession timed out: %ld %ld\n`

## pseudocode

```c

```
