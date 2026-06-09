# __imp_load_CMP_WaitNoPendingInstallEvents

- ea: `0x1800021de`
- end: `0x1800021ea`
- name: `__imp_load_CMP_WaitNoPendingInstallEvents`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800020bd`

## import_xrefs

- `SETUPAPI!CMP_WaitNoPendingInstallEvents` at `0x1800021de`

## pseudocode

```c
__int64 load_CMP_WaitNoPendingInstallEvents()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x1800021de  lea     rax, __imp_CMP_WaitNoPendingInstallEvents
0x1800021e5  jmp     __tailMerge_setupapi_dll
```
