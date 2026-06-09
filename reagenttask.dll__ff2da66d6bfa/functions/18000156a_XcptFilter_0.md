# _XcptFilter_0

- ea: `0x18000156a`
- end: `0x180001570`
- name: `_XcptFilter_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001324`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x18000156a`

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
0x18000156a  jmp     cs:__imp__XcptFilter
```
