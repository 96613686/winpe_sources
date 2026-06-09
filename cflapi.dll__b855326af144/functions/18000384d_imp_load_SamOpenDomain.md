# __imp_load_SamOpenDomain

- ea: `0x18000384d`
- end: `0x180003859`
- name: `__imp_load_SamOpenDomain`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800037bc`

## import_xrefs

- `SAMLIB!SamOpenDomain` at `0x18000384d`

## pseudocode

```c
__int64 load_SamOpenDomain()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18000384d  lea     rax, __imp_SamOpenDomain
0x180003854  jmp     __tailMerge_samlib_dll
```
