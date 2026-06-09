# operator delete(void *,unsigned __int64)

- ea: `0x180016114`
- end: `0x180016119`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006f40`
- `0x1800075d0`
- `0x180008554`
- `0x18000e210`
- `0x180015854`
- `0x18001c7f0`
- `0x18001c830`
- `0x18001e340`

## callees

- `0x1800166c0`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180016114  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
