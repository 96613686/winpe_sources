# operator delete[](void *)

- ea: `0x180001150`
- end: `0x180001155`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002178`
- `0x180002aec`
- `0x180004714`
- `0x180004784`
- `0x18000b358`
- `0x180015790`

## callees

- `0x180001144`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180001150  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
