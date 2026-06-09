# operator delete(void *)

- ea: `0x1800088fc`
- end: `0x180008901`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001d20`
- `0x180005f60`
- `0x180006840`
- `0x180006f50`
- `0x180007160`
- `0x1800087e0`
- `0x1800092c8`
- `0x180009fa0`
- `0x18000a260`
- `0x18000a270`
- `0x18000a4a0`

## callees

- `0x180008dd6`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x1800088fc  jmp     free_0
```
