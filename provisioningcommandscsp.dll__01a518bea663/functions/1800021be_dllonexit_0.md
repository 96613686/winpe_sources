# __dllonexit_0

- ea: `0x1800021be`
- end: `0x1800021c4`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001c80`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1800021be`

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
0x1800021be  jmp     cs:__imp___dllonexit
```
