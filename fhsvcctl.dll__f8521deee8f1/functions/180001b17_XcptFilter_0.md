# _XcptFilter_0

- ea: `0x180001b17`
- end: `0x180001b1d`
- name: `_XcptFilter_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800018b4`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x180001b17`

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
0x180001b17  jmp     cs:__imp__XcptFilter
```
