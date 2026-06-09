# CTSCredManAssistant::PrepareForCredWriteOld(ushort const *,ushort const *,uchar *,ulong,ulong *,ushort * *,ushort * *,uchar * *,ulong *,int)

- ea: `0x1400aae00`
- end: `0x1400ab32d`
- name: `?PrepareForCredWriteOld@CTSCredManAssistant@@AEAAJPEBG0PEAEKPEAKPEAPEAG3PEAPEAE2H@Z`
- size: `1325`
- prototype: `__int64 __fastcall(CTSCredManAssistant *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, DWORD cbAuthBuffer, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned __int8 **, unsigned int *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400ab334`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x140040474`
- `0x1400a8d00`
- `0x1400aae00`
- `0x1400b1d80`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400aafc2`
- `KERNEL32!LocalFree` at `0x1400aafea`
- `KERNEL32!LocalFree` at `0x1400ab26a`
- `KERNEL32!LocalFree` at `0x1400ab27c`
- `KERNEL32!LocalFree` at `0x1400ab314`
- `KERNEL32!LocalFree` at `0x1400aafc2`
- `KERNEL32!LocalFree` at `0x1400aafea`
- `KERNEL32!LocalFree` at `0x1400ab26a`
- `KERNEL32!LocalFree` at `0x1400ab27c`
- `KERNEL32!LocalFree` at `0x1400ab314`
- `KERNEL32!GetLastError` at `0x1400aafa8`
- `KERNEL32!GetLastError` at `0x1400aafa8`
- `credui!CredUnPackAuthenticationBufferW` at `0x1400ab038`
- `credui!CredUnPackAuthenticationBufferW` at `0x1400ab038`

## string_xrefs

- `0x1400ab213`: `CreateSPN failed`

## pseudocode

```c

```
