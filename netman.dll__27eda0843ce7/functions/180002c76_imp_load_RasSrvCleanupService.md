# __imp_load_RasSrvCleanupService

- ea: `0x180002c76`
- end: `0x180002c82`
- name: `__imp_load_RasSrvCleanupService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002baf`

## import_xrefs

- `RASDLG!RasSrvCleanupService` at `0x180002c76`

## pseudocode

```c
__int64 load_RasSrvCleanupService()
{
  return _tailMerge_rasdlg_dll();
}

```

## disassembly

```asm
0x180002c76  lea     rax, __imp_RasSrvCleanupService
0x180002c7d  jmp     __tailMerge_rasdlg_dll
```
