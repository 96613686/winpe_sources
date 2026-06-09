# __dllonexit_0

- ea: `0x1400018fe`
- end: `0x140001904`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001640`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1400018fe`

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
0x1400018fe  jmp     cs:__imp___dllonexit
```
