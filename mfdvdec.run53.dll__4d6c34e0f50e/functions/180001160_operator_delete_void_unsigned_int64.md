# operator delete(void *,unsigned __int64)

- ea: `0x180001160`
- end: `0x180001165`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800020a0`
- `0x1800020e0`
- `0x180002130`
- `0x180004818`
- `0x180006b70`
- `0x180007b50`

## callees

- `0x180001178`

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
0x180001160  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
