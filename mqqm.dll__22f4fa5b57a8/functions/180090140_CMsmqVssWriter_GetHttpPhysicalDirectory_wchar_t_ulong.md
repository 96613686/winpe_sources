# CMsmqVssWriter::GetHttpPhysicalDirectory(wchar_t *,ulong)

- ea: `0x180090140`
- end: `0x180090259`
- name: `?GetHttpPhysicalDirectory@CMsmqVssWriter@@AEAAJPEA_WK@Z`
- size: `281`
- prototype: `int(CMsmqVssWriter *__hidden this, wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18008eec0`
- `0x180093428`

## callees

- `0x18000bb04`
- `0x18002c61c`
- `0x180090140`
- `0x18009a590`

## import_xrefs

- `msvcrt!free` at `0x1800901ba`
- `msvcrt!free` at `0x180090201`
- `msvcrt!free` at `0x180090237`
- `msvcrt!free` at `0x180090245`
- `msvcrt!free` at `0x1800901ba`
- `msvcrt!free` at `0x180090201`
- `msvcrt!free` at `0x180090237`
- `msvcrt!free` at `0x180090245`
- `KERNEL32!GetFileAttributesW` at `0x18009020d`
- `KERNEL32!GetFileAttributesW` at `0x18009020d`

## string_xrefs

- `0x1800901a4`: `writer/mqwriter`
- `0x1800901ed`: `writer/mqwriter`
- `0x18009021e`: `writer/mqwriter`
- `0x18009016e`: `PathWWWRoot`

## pseudocode

```c

```
