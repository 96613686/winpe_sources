# __imp_load_CryptCreateHash

- ea: `0x18001725d`
- end: `0x180017269`
- name: `__imp_load_CryptCreateHash`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180017196`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x18001725d`

## pseudocode

```c
__int64 load_CryptCreateHash()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18001725d  lea     rax, __imp_CryptCreateHash
0x180017264  jmp     __tailMerge_advapi32_dll
```
