# operator delete[](void *)

- ea: `0x18001c8b0`
- end: `0x18001c8b5`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18001c890`

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
0x18001c8b0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
