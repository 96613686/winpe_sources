# __dllonexit_0

- ea: `0x1800059ae`
- end: `0x1800059b4`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800056f0`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1800059ae`

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
0x1800059ae  jmp     cs:__imp___dllonexit
```
