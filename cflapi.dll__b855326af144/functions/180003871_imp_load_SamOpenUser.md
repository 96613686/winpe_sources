# __imp_load_SamOpenUser

- ea: `0x180003871`
- end: `0x18000387d`
- name: `__imp_load_SamOpenUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800037bc`

## import_xrefs

- `SAMLIB!SamOpenUser` at `0x180003871`

## pseudocode

```c
__int64 load_SamOpenUser()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x180003871  lea     rax, __imp_SamOpenUser
0x180003878  jmp     __tailMerge_samlib_dll
```
