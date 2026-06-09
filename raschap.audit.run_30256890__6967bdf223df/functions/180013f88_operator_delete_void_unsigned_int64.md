# operator delete(void *,unsigned __int64)

- ea: `0x180013f88`
- end: `0x180013f8d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001f2d0`
- `0x18001f310`
- `0x18001f350`
- `0x18001f390`

## callees

- `0x180013bd0`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180013f88  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
