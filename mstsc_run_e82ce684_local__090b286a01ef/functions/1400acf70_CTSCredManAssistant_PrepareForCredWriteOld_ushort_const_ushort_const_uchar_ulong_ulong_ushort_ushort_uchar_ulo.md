# CTSCredManAssistant::PrepareForCredWriteOld(ushort const *,ushort const *,uchar *,ulong,ulong *,ushort * *,ushort * *,uchar * *,ulong *,int)

- ea: `0x1400acf70`
- end: `0x1400ad49d`
- name: `?PrepareForCredWriteOld@CTSCredManAssistant@@AEAAJPEBG0PEAEKPEAKPEAPEAG3PEAPEAE2H@Z`
- size: `1325`
- prototype: `__int64 __fastcall(CTSCredManAssistant *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, DWORD cbAuthBuffer, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned __int8 **, unsigned int *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400ad4a4`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x140042438`
- `0x1400aae70`
- `0x1400acf70`
- `0x1400b3ef0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400ad132`
- `KERNEL32!LocalFree` at `0x1400ad15a`
- `KERNEL32!LocalFree` at `0x1400ad3da`
- `KERNEL32!LocalFree` at `0x1400ad3ec`
- `KERNEL32!LocalFree` at `0x1400ad484`
- `KERNEL32!LocalFree` at `0x1400ad132`
- `KERNEL32!LocalFree` at `0x1400ad15a`
- `KERNEL32!LocalFree` at `0x1400ad3da`
- `KERNEL32!LocalFree` at `0x1400ad3ec`
- `KERNEL32!LocalFree` at `0x1400ad484`
- `KERNEL32!GetLastError` at `0x1400ad118`
- `KERNEL32!GetLastError` at `0x1400ad118`
- `credui!CredUnPackAuthenticationBufferW` at `0x1400ad1a8`
- `credui!CredUnPackAuthenticationBufferW` at `0x1400ad1a8`

## string_xrefs

- `0x1400ad383`: `CreateSPN failed`

## pseudocode

```c

```
