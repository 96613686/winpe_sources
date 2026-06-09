# __dllonexit_0

- ea: `0x18001bf01`
- end: `0x18001bf07`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001be30`

## import_xrefs

- `msvcrt!__dllonexit` at `0x18001bf01`

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
0x18001bf01  jmp     cs:__imp___dllonexit
```
