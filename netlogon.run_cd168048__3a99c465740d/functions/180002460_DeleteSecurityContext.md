# DeleteSecurityContext

- ea: `0x180002460`
- end: `0x180002598`
- name: `DeleteSecurityContext`
- size: `312`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002460`
- `0x180007518`
- `0x18000dd00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002576`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002576`
- `ntdll!RtlLeaveCriticalSection` at `0x1800024e9`
- `ntdll!RtlLeaveCriticalSection` at `0x180002585`
- `ntdll!RtlLeaveCriticalSection` at `0x1800024e9`
- `ntdll!RtlLeaveCriticalSection` at `0x180002585`
- `ntdll!RtlEnterCriticalSection` at `0x1800024a8`
- `ntdll!RtlEnterCriticalSection` at `0x1800024a8`

## string_xrefs

- `0x18000246d`: `DeleteSecurityContext: %Ix.%Ix: called\n`
- `0x1800024d1`: `DeleteContext: %Ix.%Ix: context handle not found\n`
- `0x180002541`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x18000255e`: `DeleteContext: %Ix.%Ix: context freed\n`

## pseudocode

```c

```
