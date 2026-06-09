# __dllonexit_0

- ea: `0x1800021ce`
- end: `0x1800021d4`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001c90`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1800021ce`

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
0x1800021ce  jmp     cs:__imp___dllonexit
```
