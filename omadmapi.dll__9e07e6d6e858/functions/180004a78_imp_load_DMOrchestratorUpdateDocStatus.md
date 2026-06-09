# __imp_load_DMOrchestratorUpdateDocStatus

- ea: `0x180004a78`
- end: `0x180004a84`
- name: `__imp_load_DMOrchestratorUpdateDocStatus`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800049f9`

## import_xrefs

- `DeclaredConfiguration!DMOrchestratorUpdateDocStatus` at `0x180004a78`

## pseudocode

```c
__int64 load_DMOrchestratorUpdateDocStatus()
{
  return _tailMerge_declaredconfiguration_dll();
}

```

## disassembly

```asm
0x180004a78  lea     rax, __imp_DMOrchestratorUpdateDocStatus
0x180004a7f  jmp     __tailMerge_declaredconfiguration_dll
```
