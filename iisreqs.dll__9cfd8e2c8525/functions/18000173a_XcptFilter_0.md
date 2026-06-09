# _XcptFilter_0

- ea: `0x18000173a`
- end: `0x180001740`
- name: `_XcptFilter_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001314`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x18000173a`

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
0x18000173a  jmp     cs:__imp__XcptFilter
```
