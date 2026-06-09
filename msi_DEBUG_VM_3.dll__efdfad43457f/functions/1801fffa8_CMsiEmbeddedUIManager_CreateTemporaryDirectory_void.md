# CMsiEmbeddedUIManager::CreateTemporaryDirectory(void)

- ea: `0x1801fffa8`
- end: `0x1802001a8`
- name: `?CreateTemporaryDirectory@CMsiEmbeddedUIManager@@IEAAKXZ`
- size: `512`
- prototype: `unsigned int __fastcall(CMsiEmbeddedUIManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18020032c`

## callees

- `0x180022120`
- `0x180025560`
- `0x18004295c`
- `0x1800c2854`
- `0x18014ba64`
- `0x1801fffa8`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `msvcrt!rand` at `0x18020008d`
- `msvcrt!rand` at `0x18020008d`
- `msvcrt!time` at `0x1801fffe7`
- `msvcrt!time` at `0x1801fffe7`
- `msvcrt!srand` at `0x1801ffff0`
- `msvcrt!srand` at `0x1801ffff0`
- `KERNEL32!GetLastError` at `0x1802000e4`
- `KERNEL32!GetLastError` at `0x1802000fa`
- `KERNEL32!GetLastError` at `0x1802000e4`
- `KERNEL32!GetLastError` at `0x1802000fa`
- `KERNEL32!GlobalFree` at `0x18020011f`
- `KERNEL32!GlobalFree` at `0x18020014a`
- `KERNEL32!GlobalFree` at `0x180200176`
- `KERNEL32!GlobalFree` at `0x18020011f`
- `KERNEL32!GlobalFree` at `0x18020014a`
- `KERNEL32!GlobalFree` at `0x180200176`
- `KERNEL32!CreateDirectoryW` at `0x1802000bf`
- `KERNEL32!CreateDirectoryW` at `0x1802000bf`

## string_xrefs

- `0x180200098`: `%sMSI%d`

## pseudocode

```c

```
