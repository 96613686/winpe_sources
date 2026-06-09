# __dllonexit_0

- ea: `0x180002f9e`
- end: `0x180002fa4`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002ad4`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180002f9e`

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
0x180002f9e  jmp     cs:__imp___dllonexit
```
