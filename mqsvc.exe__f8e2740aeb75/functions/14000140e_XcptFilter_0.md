# _XcptFilter_0

- ea: `0x14000140e`
- end: `0x140001414`
- name: `_XcptFilter_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011c0`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x14000140e`

## pseudocode

```c
// attributes: thunk
__int64 XcptFilter_0()
{
  return _XcptFilter();
}

```

## disassembly

```asm
0x14000140e  jmp     cs:__imp__XcptFilter
```
