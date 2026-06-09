# SampDsGetSecureChannelDcName(_UNICODE_STRING *)

- ea: `0x1803f3ccc`
- end: `0x1803f3e21`
- name: `?SampDsGetSecureChannelDcName@@YAJPEAU_UNICODE_STRING@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1803f7090`

## callees

- `0x18001ea60`
- `0x180021aa3`
- `0x1803f3ccc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803f3d36`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803f3d36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803f3de1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803f3de1`
- `ntdll!RtlCreateUnicodeString` at `0x1803f3dce`
- `ntdll!RtlCreateUnicodeString` at `0x1803f3dce`
- `NETLOGON!I_NetLogonGetAuthDataEx` at `0x1803f3db7`
- `NETLOGON!I_NetLogonGetAuthDataEx` at `0x1803f3db7`
- `NETLOGON!I_NetLogonFree` at `0x1803f3dff`
- `NETLOGON!I_NetLogonFree` at `0x1803f3dff`
- `netutils!NetApiBufferFree` at `0x1803f3df0`
- `netutils!NetApiBufferFree` at `0x1803f3e0e`
- `netutils!NetApiBufferFree` at `0x1803f3df0`
- `netutils!NetApiBufferFree` at `0x1803f3e0e`
- `SAMSRV!SampUsingDsData` at `0x1803f3d11`
- `SAMSRV!SampUsingDsData` at `0x1803f3d11`
- `SAMSRV!SampGetExternalNameFromIndex` at `0x1803f3d20`
- `SAMSRV!SampGetExternalNameFromIndex` at `0x1803f3d20`

## pseudocode

```c

```
