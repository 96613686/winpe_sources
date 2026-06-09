# __imp_load_CredWriteW

- ea: `0x18000ab94`
- end: `0x18000aba0`
- name: `__imp_load_CredWriteW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000aa85`

## import_xrefs

- `ADVAPI32!CredWriteW` at `0x18000ab94`

## pseudocode

```c
__int64 load_CredWriteW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000ab94  lea     rax, __imp_CredWriteW
0x18000ab9b  jmp     __tailMerge_advapi32_dll
```
