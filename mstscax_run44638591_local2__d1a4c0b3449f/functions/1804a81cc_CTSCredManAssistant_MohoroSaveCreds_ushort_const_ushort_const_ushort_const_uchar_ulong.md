# CTSCredManAssistant::MohoroSaveCreds(ushort const *,ushort const *,ushort const *,uchar *,ulong)

- ea: `0x1804a81cc`
- end: `0x1804a86f9`
- name: `?MohoroSaveCreds@CTSCredManAssistant@@QEAAJPEBG00PEAEK@Z`
- size: `1325`
- prototype: `int(CTSCredManAssistant *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1803ef494`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800cfa74`
- `0x1800e9b1c`
- `0x1804a5430`
- `0x1804a81cc`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804a85a5`
- `KERNEL32!GetLastError` at `0x1804a8611`
- `KERNEL32!GetLastError` at `0x1804a85a5`
- `KERNEL32!GetLastError` at `0x1804a8611`
- `KERNEL32!LocalAlloc` at `0x1804a83a7`
- `KERNEL32!LocalAlloc` at `0x1804a840f`
- `KERNEL32!LocalAlloc` at `0x1804a83a7`
- `KERNEL32!LocalAlloc` at `0x1804a840f`
- `KERNEL32!LocalFree` at `0x1804a867f`
- `KERNEL32!LocalFree` at `0x1804a86a1`
- `KERNEL32!LocalFree` at `0x1804a86c7`
- `KERNEL32!LocalFree` at `0x1804a867f`
- `KERNEL32!LocalFree` at `0x1804a86a1`
- `KERNEL32!LocalFree` at `0x1804a86c7`
- `ADVAPI32!CredWriteW` at `0x1804a8607`
- `ADVAPI32!CredWriteW` at `0x1804a8607`
- `CRYPT32!CryptProtectData` at `0x1804a859b`
- `CRYPT32!CryptProtectData` at `0x1804a859b`

## string_xrefs

- `0x1804a82fd`: `CreateGenericTargetName failed to create target name`

## pseudocode

```c

```
