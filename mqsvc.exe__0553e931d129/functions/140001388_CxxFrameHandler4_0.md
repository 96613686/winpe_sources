# __CxxFrameHandler4_0

- ea: `0x140001388`
- end: `0x14000138e`
- name: `__CxxFrameHandler4_0`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `msvcrt!__CxxFrameHandler4` at `0x140001388`

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
0x140001388  jmp     cs:__imp___CxxFrameHandler4
```
