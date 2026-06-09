# __imp_load_OpenTraceW

- ea: `0x1800580fc`
- end: `0x180058108`
- name: `__imp_load_OpenTraceW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18005807d`

## import_xrefs

- `ADVAPI32!OpenTraceW` at `0x1800580fc`

## pseudocode

```c
__int64 load_OpenTraceW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800580fc  lea     rax, __imp_OpenTraceW
0x180058103  jmp     __tailMerge_advapi32_dll
```
