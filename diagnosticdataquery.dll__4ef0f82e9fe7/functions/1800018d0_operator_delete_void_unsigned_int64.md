# operator delete(void *,unsigned __int64)

- ea: `0x1800018d0`
- end: `0x1800018d5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006040`
- `0x180006080`
- `0x180008c10`
- `0x180009090`
- `0x180009100`
- `0x1800091a0`
- `0x180009200`
- `0x180009260`

## callees

- `0x180001e10`

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
0x1800018d0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
