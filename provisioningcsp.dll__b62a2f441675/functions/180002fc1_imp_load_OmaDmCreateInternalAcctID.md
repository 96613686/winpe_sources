# __imp_load_OmaDmCreateInternalAcctID

- ea: `0x180002fc1`
- end: `0x180002fcd`
- name: `__imp_load_OmaDmCreateInternalAcctID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002f42`

## import_xrefs

- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x180002fc1`

## pseudocode

```c
__int64 load_OmaDmCreateInternalAcctID()
{
  return _tailMerge_omadmapi_dll();
}

```

## disassembly

```asm
0x180002fc1  lea     rax, __imp_OmaDmCreateInternalAcctID
0x180002fc8  jmp     __tailMerge_omadmapi_dll
```
