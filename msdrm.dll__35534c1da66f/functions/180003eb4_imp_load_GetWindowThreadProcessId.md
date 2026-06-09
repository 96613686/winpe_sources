# __imp_load_GetWindowThreadProcessId

- ea: `0x180003eb4`
- end: `0x180003ec0`
- name: `__imp_load_GetWindowThreadProcessId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003ddb`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x180003eb4`

## pseudocode

```c
__int64 load_GetWindowThreadProcessId()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x180003eb4  lea     rax, __imp_GetWindowThreadProcessId
0x180003ebb  jmp     __tailMerge_user32_dll
```
