# _XcptFilter_0

- ea: `0x18000154a`
- end: `0x180001550`
- name: `_XcptFilter_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001314`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x18000154a`

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
0x18000154a  jmp     cs:__imp__XcptFilter
```
