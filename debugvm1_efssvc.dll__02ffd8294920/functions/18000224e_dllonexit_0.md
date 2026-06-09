# __dllonexit_0

- ea: `0x18000224e`
- end: `0x180002254`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001f8c`

## import_xrefs

- `msvcrt!__dllonexit` at `0x18000224e`

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
0x18000224e  jmp     cs:__imp___dllonexit
```
