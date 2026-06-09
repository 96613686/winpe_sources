# __dllonexit_0

- ea: `0x18000fbcb`
- end: `0x18000fbd1`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000f6f4`

## import_xrefs

- `msvcrt!__dllonexit` at `0x18000fbcb`

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
0x18000fbcb  jmp     cs:__imp___dllonexit
```
