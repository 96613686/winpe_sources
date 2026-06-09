# LoadWSAPoll(int (**)(pollfd * const,ulong,int),HINSTANCE__ * *)

- ea: `0x1801652a0`
- end: `0x18016552f`
- name: `?LoadWSAPoll@@YAKPEAP6AHQEAUpollfd@@KH@ZPEAPEAUHINSTANCE__@@@Z`
- size: `655`
- prototype: `unsigned int __fastcall(int (**)(struct pollfd *const, unsigned int, int), HINSTANCE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180164ab0`

## callees

- `0x180001f70`
- `0x1800030c0`
- `0x180003d80`
- `0x180157620`
- `0x18015a6f0`
- `0x18015a880`
- `0x1801652a0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180165473`
- `KERNEL32!FreeLibrary` at `0x180165473`
- `KERNEL32!GetLastError` at `0x180165340`
- `KERNEL32!GetLastError` at `0x1801653da`
- `KERNEL32!GetLastError` at `0x18016547d`
- `KERNEL32!GetLastError` at `0x180165340`
- `KERNEL32!GetLastError` at `0x1801653da`
- `KERNEL32!GetLastError` at `0x18016547d`
- `KERNEL32!GetProcAddress` at `0x1801653c8`
- `KERNEL32!GetProcAddress` at `0x1801653c8`

## string_xrefs

- `0x18016532c`: `ws2_32.dll`

## pseudocode

```c

```
