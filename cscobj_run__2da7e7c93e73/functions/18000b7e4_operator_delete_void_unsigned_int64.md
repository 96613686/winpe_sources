# operator delete(void *,unsigned __int64)

- ea: `0x18000b7e4`
- end: `0x18000b7e9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `50`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005c30`
- `0x180005e40`
- `0x180006010`
- `0x180007360`
- `0x1800074c0`
- `0x180007eb0`
- `0x180008020`
- `0x18000ce30`
- `0x18000cee0`
- `0x18000cf84`
- `0x18000e470`
- `0x18000e520`
- `0x18000e560`
- `0x18000e5a0`
- `0x18000e610`
- `0x18000f6f0`
- `0x18000f72c`
- `0x180011440`
- `0x180011490`
- `0x1800114e0`
- `0x180013fb0`
- `0x180014930`
- `0x180014970`
- `0x1800149b0`
- `0x180015730`
- `0x180015770`
- `0x180015f40`
- `0x180015f80`
- `0x180015fc0`
- `0x180016bc0`
- `0x180016c00`
- `0x180016c40`
- `0x180016c80`
- `0x180016cc0`
- `0x180016d00`
- `0x180016d40`
- `0x180016d80`
- `0x180016dc0`
- `0x180018720`
- `0x180018760`
- `0x1800187b0`
- `0x1800187f0`
- `0x180018830`
- `0x1800198a0`
- `0x1800198f0`
- `0x18001cc00`
- `0x18001cc40`
- `0x180023870`
- `0x180025bb0`
- `0x1800267c0`

## callees

- `0x18000b384`

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
0x18000b7e4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
