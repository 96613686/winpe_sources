# _XcptFilter_0

- ea: `0x14000143e`
- end: `0x140001444`
- name: `_XcptFilter_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001140`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x14000143e`

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
0x14000143e  jmp     cs:__imp__XcptFilter
```
