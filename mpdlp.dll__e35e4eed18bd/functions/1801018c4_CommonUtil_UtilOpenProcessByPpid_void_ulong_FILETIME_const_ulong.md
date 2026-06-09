# CommonUtil::UtilOpenProcessByPpid(void * *,ulong,_FILETIME const *,ulong)

- ea: `0x1801018c4`
- end: `0x1801019b9`
- name: `?UtilOpenProcessByPpid@CommonUtil@@YAJPEAPEAXKPEBU_FILETIME@@K@Z`
- size: `245`
- prototype: `int(CommonUtil *__hidden this, void **, unsigned int, const struct _FILETIME *, unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d790`
- `0x180042610`
- `0x180069cb8`
- `0x18007eab0`
- `0x1800af07c`
- `0x18014e4ec`
- `0x1801e70b4`

## callees

- `0x1801018c4`
- `0x1801051e8`
- `0x18010cb40`

## import_xrefs

- `KERNEL32!GetProcessTimes` at `0x180101950`
- `KERNEL32!GetProcessTimes` at `0x180101950`
- `KERNEL32!GetLastError` at `0x18010195a`
- `KERNEL32!GetLastError` at `0x18010195a`
- `KERNEL32!CloseHandle` at `0x180101910`
- `KERNEL32!CloseHandle` at `0x18010198e`
- `KERNEL32!CloseHandle` at `0x180101910`
- `KERNEL32!CloseHandle` at `0x18010198e`
- `KERNEL32!CompareFileTime` at `0x18010197b`
- `KERNEL32!CompareFileTime` at `0x18010197b`

## pseudocode

```c

```
