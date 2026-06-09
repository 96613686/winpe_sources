# ___CxxFrameHandler3

- ea: `0x10035e9f`
- end: `0x10035ea5`
- name: `___CxxFrameHandler3`
- size: `6`
- prototype: ``
- caller_count: `28`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1001eba0`
- `0x1001eca0`
- `0x1001f360`
- `0x1001f420`
- `0x1001f5a0`
- `0x1001f760`
- `0x1001fa20`
- `0x1001fe30`
- `0x100203a0`
- `0x100204f0`
- `0x10020600`
- `0x10020680`
- `0x10020780`
- `0x10020e70`
- `0x10021260`
- `0x100213d0`
- `0x10021e70`
- `0x10022160`
- `0x10022240`
- `0x10032956`
- `0x10032b82`
- `0x10032c26`
- `0x10032fa0`
- `0x1003325b`
- `0x10033a09`
- `0x10033c94`
- `0x10033ce9`
- `0x10036c00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__CxxFrameHandler3` at `0x10035e9f`

## pseudocode

```c
// attributes: thunk
int __CxxFrameHandler3()
{
  return ___CxxFrameHandler3();
}

```

## disassembly

```asm
0x10035e9f  jmp     ds:__imp____CxxFrameHandler3
```
