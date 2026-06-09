# CSrApiViewerAxHost::s_GetSessEnvPublicBinding(CSrApiViewerAxHost::EServerLocality,ushort const *,void * *)

- ea: `0x1400b0804`
- end: `0x1400b0b58`
- name: `?s_GetSessEnvPublicBinding@CSrApiViewerAxHost@@CAJW4EServerLocality@1@PEBGPEAPEAX@Z`
- size: `852`
- prototype: `static int __high(enum CSrApiViewerAxHost::EServerLocality, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400ad578`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400b0804`
- `0x1400b1938`
- `0x1400b1a78`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1400b0846`
- `KERNEL32!LocalAlloc` at `0x1400b0846`
- `KERNEL32!LocalFree` at `0x1400b0b2c`
- `KERNEL32!LocalFree` at `0x1400b0b2c`
- `KERNEL32!GetLastError` at `0x1400b08be`
- `KERNEL32!GetLastError` at `0x1400b08be`
- `RPCRT4!RpcBindingFree` at `0x1400b0b3c`
- `RPCRT4!RpcBindingFree` at `0x1400b0b3c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400b09f4`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400b09f4`
- `ADVAPI32!CreateWellKnownSid` at `0x1400b08b4`
- `ADVAPI32!CreateWellKnownSid` at `0x1400b08b4`

## pseudocode

```c

```
