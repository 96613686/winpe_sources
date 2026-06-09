# operator delete(void *,unsigned __int64)

- ea: `0x180001f44`
- end: `0x180001f49`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `16`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002c20`
- `0x180002c80`
- `0x180003310`
- `0x180003370`
- `0x180003910`
- `0x180003940`
- `0x180004dd8`
- `0x180005240`
- `0x180005404`
- `0x180005624`
- `0x1800058d0`
- `0x180005900`
- `0x180005940`
- `0x1800059a0`
- `0x1800059e0`
- `0x180005a40`

## callees

- `0x180001f38`

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
0x180001f44  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
