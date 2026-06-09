# CSrApiViewerAxHost::s_GetSessEnvPublicBinding(CSrApiViewerAxHost::EServerLocality,ushort const *,void * *)

- ea: `0x1400b2974`
- end: `0x1400b2cc8`
- name: `?s_GetSessEnvPublicBinding@CSrApiViewerAxHost@@CAJW4EServerLocality@1@PEBGPEAPEAX@Z`
- size: `852`
- prototype: `static int __high(enum CSrApiViewerAxHost::EServerLocality, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400af6e8`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400b2974`
- `0x1400b3aa8`
- `0x1400b3be8`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1400b29b6`
- `KERNEL32!LocalAlloc` at `0x1400b29b6`
- `KERNEL32!LocalFree` at `0x1400b2c9c`
- `KERNEL32!LocalFree` at `0x1400b2c9c`
- `KERNEL32!GetLastError` at `0x1400b2a2e`
- `KERNEL32!GetLastError` at `0x1400b2a2e`
- `RPCRT4!RpcBindingFree` at `0x1400b2cac`
- `RPCRT4!RpcBindingFree` at `0x1400b2cac`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400b2b64`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400b2b64`
- `ADVAPI32!CreateWellKnownSid` at `0x1400b2a24`
- `ADVAPI32!CreateWellKnownSid` at `0x1400b2a24`

## pseudocode

```c

```
