# KerbBuildGssChecksum(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_TICKET_CACHE_ENTRY *,ulong *,KERB_CHECKSUM *,ulong *,PSEC_CHANNEL_BINDINGS_ANY,utl::map<uint,utl::vector<uchar,utl::allocator<uchar>>,utl::less<uint>,utl::allocator<utl::pair<uint const,utl::vector<uchar,utl::allocator<uchar>>>>> const &)

- ea: `0x18003d7d0`
- end: `0x18003de09`
- name: `?KerbBuildGssChecksum@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_TICKET_CACHE_ENTRY@@PEAKPEAUKERB_CHECKSUM@@4TPSEC_CHANNEL_BINDINGS_ANY@@AEBV?$map@IV?$vector@EV?$allocator@E@utl@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$vector@EV?$allocator@E@utl@@@utl@@@utl@@@2@@utl@@@Z`
- size: `1593`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180085c20`

## callees

- `0x1800063e8`
- `0x18002a9b0`
- `0x18002c9b8`
- `0x18003d7d0`
- `0x18003e488`
- `0x180070a50`
- `0x18007108c`
- `0x1800740f4`
- `0x1800744cf`
- `0x18008663c`
- `0x180089e48`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003dac7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003dac7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dd4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ddf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dd4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ddf8`
- `ntdll!RtlEqualUnicodeString` at `0x18003d8ac`
- `ntdll!RtlEqualUnicodeString` at `0x18003d8d2`
- `ntdll!RtlEqualUnicodeString` at `0x18003d8ac`
- `ntdll!RtlEqualUnicodeString` at `0x18003d8d2`
- `ntdll!RtlEnterCriticalSection` at `0x18003d870`
- `ntdll!RtlEnterCriticalSection` at `0x18003d888`
- `ntdll!RtlEnterCriticalSection` at `0x18003d870`
- `ntdll!RtlEnterCriticalSection` at `0x18003d888`
- `ntdll!RtlLeaveCriticalSection` at `0x18003d8fd`
- `ntdll!RtlLeaveCriticalSection` at `0x18003d90f`
- `ntdll!RtlLeaveCriticalSection` at `0x18003d99e`
- `ntdll!RtlLeaveCriticalSection` at `0x18003d8fd`
- `ntdll!RtlLeaveCriticalSection` at `0x18003d90f`
- `ntdll!RtlLeaveCriticalSection` at `0x18003d99e`
- `LSASRV!LsaIIsSuppressChannelBindingInfo` at `0x18003db97`
- `LSASRV!LsaIIsSuppressChannelBindingInfo` at `0x18003db97`

## pseudocode

```c

```
