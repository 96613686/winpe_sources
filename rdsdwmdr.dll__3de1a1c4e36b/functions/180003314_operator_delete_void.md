# operator delete(void *)

- ea: `0x180003314`
- end: `0x180003319`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `56`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004180`
- `0x1800041b0`
- `0x1800041ec`
- `0x180004728`
- `0x180005504`
- `0x180007970`
- `0x18000ae80`
- `0x18000cc60`
- `0x18000df3c`
- `0x18000f0bc`
- `0x18000f150`
- `0x18000f190`
- `0x18000f23c`
- `0x18000f3e0`
- `0x180012e28`
- `0x180013000`
- `0x180013038`
- `0x180013070`
- `0x180015bc0`
- `0x180016350`
- `0x180016450`
- `0x180017560`
- `0x18001a030`
- `0x18001a9a4`
- `0x18001a9fc`
- `0x18001aae0`
- `0x18001ab18`
- `0x18001ca00`
- `0x18001d498`
- `0x18001d4c4`
- `0x18001deb4`
- `0x18001dfc8`
- `0x18001f5bc`
- `0x18001f760`
- `0x18001f798`
- `0x18001f7d0`
- `0x180020078`
- `0x180020b30`
- `0x180020e90`
- `0x1800213d0`
- `0x1800218b0`
- `0x1800219e0`
- `0x180021a18`
- `0x180021a60`
- `0x180021a98`
- `0x180022d00`
- `0x180022d38`
- `0x180022d70`
- `0x180022da8`
- `0x180022df0`

## callees

- `0x1800038d4`

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
0x180003314  jmp     free_0
```
