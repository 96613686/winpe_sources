# CTSCredManAssistant::SaveCreds(ushort const *,ushort const *,uchar *,ulong,int)

- ea: `0x1804a927c`
- end: `0x1804a9803`
- name: `?SaveCreds@CTSCredManAssistant@@QEAAJPEBG0PEAEKH@Z`
- size: `1415`
- prototype: `int(CTSCredManAssistant *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1804e99b0`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x1801a7bac`
- `0x1804a5a94`
- `0x1804a8700`
- `0x1804a8d20`
- `0x1804a927c`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804a93eb`
- `KERNEL32!GetLastError` at `0x1804a9419`
- `KERNEL32!GetLastError` at `0x1804a968e`
- `KERNEL32!GetLastError` at `0x1804a96c7`
- `KERNEL32!GetLastError` at `0x1804a93eb`
- `KERNEL32!GetLastError` at `0x1804a9419`
- `KERNEL32!GetLastError` at `0x1804a968e`
- `KERNEL32!GetLastError` at `0x1804a96c7`
- `KERNEL32!LocalFree` at `0x1804a9350`
- `KERNEL32!LocalFree` at `0x1804a9360`
- `KERNEL32!LocalFree` at `0x1804a9389`
- `KERNEL32!LocalFree` at `0x1804a9350`
- `KERNEL32!LocalFree` at `0x1804a9360`
- `KERNEL32!LocalFree` at `0x1804a9389`
- `ADVAPI32!CredGetSessionTypes` at `0x1804a93bd`
- `ADVAPI32!CredGetSessionTypes` at `0x1804a93bd`
- `ADVAPI32!CredWriteW` at `0x1804a967f`
- `ADVAPI32!CredWriteW` at `0x1804a96b9`
- `ADVAPI32!CredWriteW` at `0x1804a967f`
- `ADVAPI32!CredWriteW` at `0x1804a96b9`

## string_xrefs

- `0x1804a9710`: `CredWrite failed`
- `0x1804a95fc`: `PrepareForCredWriteNew failed`
- `0x1804a94d5`: `PrepareForCredWriteOld failed`

## pseudocode

```c

```
