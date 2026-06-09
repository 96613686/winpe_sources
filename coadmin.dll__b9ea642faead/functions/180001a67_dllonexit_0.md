# __dllonexit_0

- ea: `0x180001a67`
- end: `0x180001a6d`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001598`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001a67`

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
0x180001a67  jmp     cs:__imp___dllonexit
```
