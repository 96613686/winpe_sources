# __dllonexit_0

- ea: `0x180001c6e`
- end: `0x180001c74`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800016b8`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001c6e`

## pseudocode

```c
// attributes: thunk
__int64 _dllonexit_0()
{
  return __dllonexit();
}

```

## disassembly

```asm
0x180001c6e  jmp     cs:__imp___dllonexit
```
