# NGENService::GetCLRServiceStatus(_COR_SERVICE_STATUS *)

- ea: `0x18001ae6c`
- end: `0x18001afba`
- name: `?GetCLRServiceStatus@NGENService@@YAJPEAU_COR_SERVICE_STATUS@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(wchar_t *Buffer, struct _COR_SERVICE_STATUS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001bf08`

## callees

- `0x1800177f0`
- `0x18001a3a0`
- `0x18001ada4`
- `0x18001ae6c`
- `0x180030d84`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001af8a`
- `KERNEL32!HeapFree` at `0x18001af8a`
- `KERNEL32!GetProcessHeap` at `0x18001af75`
- `KERNEL32!GetProcessHeap` at `0x18001af75`

## pseudocode

```c

```
