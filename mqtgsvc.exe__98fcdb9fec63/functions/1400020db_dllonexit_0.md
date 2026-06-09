# __dllonexit_0

- ea: `0x1400020db`
- end: `0x1400020e1`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001a10`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1400020db`

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
0x1400020db  jmp     cs:__imp___dllonexit
```
