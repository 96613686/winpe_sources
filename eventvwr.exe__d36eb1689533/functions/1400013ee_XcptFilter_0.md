# _XcptFilter_0

- ea: `0x1400013ee`
- end: `0x1400013f4`
- name: `_XcptFilter_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001190`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x1400013ee`

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
0x1400013ee  jmp     cs:__imp__XcptFilter
```
