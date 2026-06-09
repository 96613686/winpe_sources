# CMsiEmbeddedUIManager::CreateTemporaryDirectory(void)

- ea: `0x1802091a8`
- end: `0x1802093e6`
- name: `?CreateTemporaryDirectory@CMsiEmbeddedUIManager@@IEAAKXZ`
- size: `574`
- prototype: `unsigned int __fastcall(CMsiEmbeddedUIManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180209570`

## callees

- `0x180010ac0`
- `0x180014160`
- `0x18008c93c`
- `0x1800d04fc`
- `0x180152484`
- `0x1802091a8`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `msvcrt!rand` at `0x180209299`
- `msvcrt!rand` at `0x180209299`
- `msvcrt!time` at `0x1802091e7`
- `msvcrt!time` at `0x1802091e7`
- `msvcrt!srand` at `0x1802091f6`
- `msvcrt!srand` at `0x1802091f6`
- `KERNEL32!GetLastError` at `0x180209300`
- `KERNEL32!GetLastError` at `0x18020931f`
- `KERNEL32!GetLastError` at `0x180209300`
- `KERNEL32!GetLastError` at `0x18020931f`
- `KERNEL32!GlobalFree` at `0x18020934a`
- `KERNEL32!GlobalFree` at `0x18020937b`
- `KERNEL32!GlobalFree` at `0x1802093ad`
- `KERNEL32!GlobalFree` at `0x18020934a`
- `KERNEL32!GlobalFree` at `0x18020937b`
- `KERNEL32!GlobalFree` at `0x1802093ad`
- `KERNEL32!CreateDirectoryW` at `0x1802092d1`
- `KERNEL32!CreateDirectoryW` at `0x1802092d1`

## string_xrefs

- `0x1802092aa`: `%sMSI%d`

## pseudocode

```c

```
