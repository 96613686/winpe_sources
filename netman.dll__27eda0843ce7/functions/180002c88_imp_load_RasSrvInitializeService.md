# __imp_load_RasSrvInitializeService

- ea: `0x180002c88`
- end: `0x180002c94`
- name: `__imp_load_RasSrvInitializeService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002baf`

## import_xrefs

- `RASDLG!RasSrvInitializeService` at `0x180002c88`

## pseudocode

```c
__int64 load_RasSrvInitializeService()
{
  return _tailMerge_rasdlg_dll();
}

```

## disassembly

```asm
0x180002c88  lea     rax, __imp_RasSrvInitializeService
0x180002c8f  jmp     __tailMerge_rasdlg_dll
```
