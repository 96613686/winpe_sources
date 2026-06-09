# CTSCredManAssistant::PrepareForCredWriteOld(ushort const *,ushort const *,uchar *,ulong,ulong *,ushort * *,ushort * *,uchar * *,ulong *,int)

- ea: `0x1804a8d20`
- end: `0x1804a9274`
- name: `?PrepareForCredWriteOld@CTSCredManAssistant@@AEAAJPEBG0PEAEKPEAKPEAPEAG3PEAPEAE2H@Z`
- size: `1364`
- prototype: `__int64 __fastcall(CTSCredManAssistant *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, DWORD cbAuthBuffer, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned __int8 **, unsigned int *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1804a927c`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x180101d30`
- `0x1804a5878`
- `0x1804a8d20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804a8edd`
- `KERNEL32!GetLastError` at `0x1804a8edd`
- `KERNEL32!LocalAlloc` at `0x1804a8dc1`
- `KERNEL32!LocalAlloc` at `0x1804a8e2d`
- `KERNEL32!LocalAlloc` at `0x1804a8f08`
- `KERNEL32!LocalAlloc` at `0x1804a8f3a`
- `KERNEL32!LocalAlloc` at `0x1804a8dc1`
- `KERNEL32!LocalAlloc` at `0x1804a8e2d`
- `KERNEL32!LocalAlloc` at `0x1804a8f08`
- `KERNEL32!LocalAlloc` at `0x1804a8f3a`
- `KERNEL32!LocalFree` at `0x1804a8ef7`
- `KERNEL32!LocalFree` at `0x1804a8f23`
- `KERNEL32!LocalFree` at `0x1804a91b1`
- `KERNEL32!LocalFree` at `0x1804a91c3`
- `KERNEL32!LocalFree` at `0x1804a925b`
- `KERNEL32!LocalFree` at `0x1804a8ef7`
- `KERNEL32!LocalFree` at `0x1804a8f23`
- `KERNEL32!LocalFree` at `0x1804a91b1`
- `KERNEL32!LocalFree` at `0x1804a91c3`
- `KERNEL32!LocalFree` at `0x1804a925b`
- `credui!CredUnPackAuthenticationBufferW` at `0x1804a8f7b`
- `credui!CredUnPackAuthenticationBufferW` at `0x1804a8f7b`

## string_xrefs

- `0x1804a915a`: `CreateSPN failed`

## pseudocode

```c

```
