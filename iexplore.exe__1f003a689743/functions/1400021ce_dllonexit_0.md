# __dllonexit_0

- ea: `0x1400021ce`
- end: `0x1400021d4`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001c08`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1400021ce`

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
0x1400021ce  jmp     cs:__imp___dllonexit
```
