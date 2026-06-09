# _XcptFilter_0

- ea: `0x1800019d4`
- end: `0x1800019da`
- name: `_XcptFilter_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800014a4`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x1800019d4`

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
0x1800019d4  jmp     cs:__imp__XcptFilter
```
