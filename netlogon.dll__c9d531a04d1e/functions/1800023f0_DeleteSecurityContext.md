# DeleteSecurityContext

- ea: `0x1800023f0`
- end: `0x18000250f`
- name: `DeleteSecurityContext`
- size: `287`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800023f0`
- `0x180007278`
- `0x18000d710`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024f9`
- `ntdll!RtlLeaveCriticalSection` at `0x180002473`
- `ntdll!RtlLeaveCriticalSection` at `0x180002502`
- `ntdll!RtlLeaveCriticalSection` at `0x180002473`
- `ntdll!RtlLeaveCriticalSection` at `0x180002502`
- `ntdll!RtlEnterCriticalSection` at `0x180002438`
- `ntdll!RtlEnterCriticalSection` at `0x180002438`

## string_xrefs

- `0x1800023fd`: `DeleteSecurityContext: %Ix.%Ix: called\n`
- `0x18000245b`: `DeleteContext: %Ix.%Ix: context handle not found\n`
- `0x1800024c4`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x1800024e1`: `DeleteContext: %Ix.%Ix: context freed\n`

## pseudocode

```c

```
