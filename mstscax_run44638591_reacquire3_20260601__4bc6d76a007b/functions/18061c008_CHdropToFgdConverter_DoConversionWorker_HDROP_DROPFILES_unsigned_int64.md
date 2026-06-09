# CHdropToFgdConverter::DoConversionWorker(HDROP__ *,_DROPFILES *,unsigned __int64)

- ea: `0x18061c008`
- end: `0x18061c42d`
- name: `?DoConversionWorker@CHdropToFgdConverter@@AEAAJPEAUHDROP__@@PEAU_DROPFILES@@_K@Z`
- size: `1061`
- prototype: `__int64 __fastcall(CHdropToFgdConverter *__hidden this, HDROP hMem, struct _DROPFILES *, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18061bcc4`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1800ebae0`
- `0x18061ae3c`
- `0x18061b614`
- `0x18061c008`
- `0x180621bfc`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18061c278`
- `msvcrt!wcsrchr` at `0x18061c278`
- `KERNEL32!GetLastError` at `0x18061c2c8`
- `KERNEL32!GetLastError` at `0x18061c3e1`
- `KERNEL32!GetLastError` at `0x18061c2c8`
- `KERNEL32!GetLastError` at `0x18061c3e1`
- `KERNEL32!LocalAlloc` at `0x18061c113`
- `KERNEL32!LocalAlloc` at `0x18061c182`
- `KERNEL32!LocalAlloc` at `0x18061c113`
- `KERNEL32!LocalAlloc` at `0x18061c182`
- `KERNEL32!LocalFree` at `0x18061c406`
- `KERNEL32!LocalFree` at `0x18061c414`
- `KERNEL32!LocalFree` at `0x18061c406`
- `KERNEL32!LocalFree` at `0x18061c414`
- `KERNEL32!GetFileAttributesW` at `0x18061c1e0`
- `KERNEL32!GetFileAttributesW` at `0x18061c1e0`
- `KERNEL32!GlobalFree` at `0x18061c2bd`
- `KERNEL32!GlobalFree` at `0x18061c2bd`
- `SHELL32!DragQueryFileW` at `0x18061c069`
- `SHELL32!DragQueryFileW` at `0x18061c1d5`
- `SHELL32!DragQueryFileW` at `0x18061c069`
- `SHELL32!DragQueryFileW` at `0x18061c1d5`

## string_xrefs

- `0x18061c14c`: `FILEGROUPDESCRIPTOR`
- `0x18061c23f`: `AddDirectoryToFgd failed!`

## pseudocode

```c

```
