# __dllonexit_0

- ea: `0x140001dcc`
- end: `0x140001dd2`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400019dc`

## import_xrefs

- `msvcrt!__dllonexit` at `0x140001dcc`

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
0x140001dcc  jmp     cs:__imp___dllonexit
```
