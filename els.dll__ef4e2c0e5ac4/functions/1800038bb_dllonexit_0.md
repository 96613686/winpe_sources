# __dllonexit_0

- ea: `0x1800038bb`
- end: `0x1800038c1`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800030a8`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1800038bb`

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
0x1800038bb  jmp     cs:__imp___dllonexit
```
