# CommonUtil::MpIsPathSymlink(bool &,wchar_t const *)

- ea: `0x180108b54`
- end: `0x180108d8d`
- name: `?MpIsPathSymlink@CommonUtil@@YAJAEA_NPEB_W@Z`
- size: `569`
- prototype: `int(CommonUtil *__hidden this, bool *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18010831c`

## callees

- `0x1800809d0`
- `0x1800af840`
- `0x180105f50`
- `0x180108b54`
- `0x18010cb40`
- `0x18010ce3c`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180108b87`
- `KERNEL32!GetFileAttributesW` at `0x180108b87`
- `KERNEL32!CreateFileW` at `0x180108bcc`
- `KERNEL32!CreateFileW` at `0x180108bcc`
- `KERNEL32!DeviceIoControl` at `0x180108c53`
- `KERNEL32!DeviceIoControl` at `0x180108c53`
- `KERNEL32!CloseHandle` at `0x180108d25`
- `KERNEL32!CloseHandle` at `0x180108d25`

## pseudocode

```c

```
