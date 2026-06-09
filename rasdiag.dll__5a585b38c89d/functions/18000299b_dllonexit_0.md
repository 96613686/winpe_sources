# __dllonexit_0

- ea: `0x18000299b`
- end: `0x1800029a1`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800024c4`

## import_xrefs

- `msvcrt!__dllonexit` at `0x18000299b`

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
0x18000299b  jmp     cs:__imp___dllonexit
```
