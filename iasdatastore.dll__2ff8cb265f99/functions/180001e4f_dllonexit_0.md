# __dllonexit_0

- ea: `0x180001e4f`
- end: `0x180001e55`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001a64`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001e4f`

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
0x180001e4f  jmp     cs:__imp___dllonexit
```
