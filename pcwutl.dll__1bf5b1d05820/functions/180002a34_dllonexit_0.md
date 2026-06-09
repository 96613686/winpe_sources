# __dllonexit_0

- ea: `0x180002a34`
- end: `0x180002a3a`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800026a0`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180002a34`

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
0x180002a34  jmp     cs:__imp___dllonexit
```
