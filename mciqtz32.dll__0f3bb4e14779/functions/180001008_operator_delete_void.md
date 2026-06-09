# operator delete[](void *)

- ea: `0x180001008`
- end: `0x18000100d`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002254`
- `0x180003604`
- `0x180003c8c`
- `0x1800041fc`

## callees

- `0x180001020`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180001008  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
