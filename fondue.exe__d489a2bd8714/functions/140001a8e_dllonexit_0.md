# __dllonexit_0

- ea: `0x140001a8e`
- end: `0x140001a94`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400017cc`

## import_xrefs

- `msvcrt!__dllonexit` at `0x140001a8e`

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
0x140001a8e  jmp     cs:__imp___dllonexit
```
