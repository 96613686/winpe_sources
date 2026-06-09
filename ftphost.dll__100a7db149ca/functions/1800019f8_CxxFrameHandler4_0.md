# __CxxFrameHandler4_0

- ea: `0x1800019f8`
- end: `0x1800019fe`
- name: `__CxxFrameHandler4_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004388`

## import_xrefs

- `msvcrt!__CxxFrameHandler4` at `0x1800019f8`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall _CxxFrameHandler4_0(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return __CxxFrameHandler4(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800019f8  jmp     cs:__imp___CxxFrameHandler4
```
