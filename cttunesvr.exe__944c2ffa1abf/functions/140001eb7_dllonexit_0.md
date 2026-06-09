# __dllonexit_0

- ea: `0x140001eb7`
- end: `0x140001ebd`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400019cc`

## import_xrefs

- `msvcrt!__dllonexit` at `0x140001eb7`

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
0x140001eb7  jmp     cs:__imp___dllonexit
```
