# __CxxFrameHandler4_0

- ea: `0x1800014d6`
- end: `0x1800014dc`
- name: `__CxxFrameHandler4_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000541c`

## import_xrefs

- `msvcrt!__CxxFrameHandler4` at `0x1800014d6`

## pseudocode

```c
// attributes: thunk
__int64 _CxxFrameHandler4_0()
{
  return __CxxFrameHandler4();
}

```

## disassembly

```asm
0x1800014d6  jmp     cs:__imp___CxxFrameHandler4
```
