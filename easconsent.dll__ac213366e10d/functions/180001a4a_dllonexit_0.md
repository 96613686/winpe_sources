# __dllonexit_0

- ea: `0x180001a4a`
- end: `0x180001a50`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000157c`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001a4a`

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
0x180001a4a  jmp     cs:__imp___dllonexit
```
