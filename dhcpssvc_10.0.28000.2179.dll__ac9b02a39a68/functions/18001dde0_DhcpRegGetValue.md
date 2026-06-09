# DhcpRegGetValue

- ea: `0x18001dde0`
- end: `0x18001dfc1`
- name: `DhcpRegGetValue`
- size: `481`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038f0`
- `0x18000601c`
- `0x18001c56c`
- `0x18001c97c`
- `0x18001cdc8`
- `0x18001d824`
- `0x18001db9c`
- `0x18001e26c`
- `0x18002356c`
- `0x180034480`
- `0x180035ab0`
- `0x180051a00`
- `0x18005518c`
- `0x180062c84`
- `0x18006632c`
- `0x1800666e0`
- `0x180066e90`
- `0x180075d70`

## callees

- `0x18000282c`
- `0x18001dde0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18001de2a`
- `ADVAPI32!RegQueryValueExW` at `0x18001dec7`
- `ADVAPI32!RegQueryValueExW` at `0x18001de2a`
- `ADVAPI32!RegQueryValueExW` at `0x18001dec7`
- `KERNEL32!LocalAlloc` at `0x18001df15`
- `KERNEL32!LocalAlloc` at `0x18001df81`
- `KERNEL32!LocalAlloc` at `0x18001df15`
- `KERNEL32!LocalAlloc` at `0x18001df81`
- `KERNEL32!LocalFree` at `0x18001dee6`
- `KERNEL32!LocalFree` at `0x18001df98`
- `KERNEL32!LocalFree` at `0x18001dee6`
- `KERNEL32!LocalFree` at `0x18001df98`

## pseudocode

```c

```
