# __imp_load_ProcessGroupPolicyCompleted

- ea: `0x18000c375`
- end: `0x18000c381`
- name: `__imp_load_ProcessGroupPolicyCompleted`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c2f6`

## import_xrefs

- `USERENV!ProcessGroupPolicyCompleted` at `0x18000c375`

## pseudocode

```c
__int64 load_ProcessGroupPolicyCompleted()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x18000c375  lea     rax, __imp_ProcessGroupPolicyCompleted
0x18000c37c  jmp     __tailMerge_userenv_dll
```
