# CommonUtil::OpenCurrentThreadToken(void * *,ulong)

- ea: `0x18010114c`
- end: `0x1801011f6`
- name: `?OpenCurrentThreadToken@CommonUtil@@YAJPEAPEAXK@Z`
- size: `170`
- prototype: `int(CommonUtil *__hidden this, void **, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a16dc`
- `0x180106d38`
- `0x180107074`

## callees

- `0x18010114c`
- `0x1801019bc`
- `0x180101a54`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18010119e`
- `KERNEL32!CloseHandle` at `0x1801011d2`
- `KERNEL32!CloseHandle` at `0x18010119e`
- `KERNEL32!CloseHandle` at `0x1801011d2`
- `KERNEL32!GetCurrentProcess` at `0x18010118b`
- `KERNEL32!GetCurrentProcess` at `0x18010118b`
- `KERNEL32!GetCurrentThread` at `0x180101169`
- `KERNEL32!GetCurrentThread` at `0x180101169`

## pseudocode

```c

```
