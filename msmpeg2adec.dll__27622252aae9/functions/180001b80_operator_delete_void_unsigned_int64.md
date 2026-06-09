# operator delete(void *,unsigned __int64)

- ea: `0x180001b80`
- end: `0x180001b85`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000aa40`
- `0x18000ae90`
- `0x18000aed0`
- `0x18000afe0`
- `0x18000b050`
- `0x18000b0b0`
- `0x18000b160`
- `0x180018e90`
- `0x180018ff0`
- `0x180019030`
- `0x18001d760`
- `0x180025490`
- `0x1800262b0`
- `0x180026310`
- `0x180028dd0`
- `0x180028e10`
- `0x18002a400`
- `0x18002b5d0`
- `0x18002b684`
- `0x180033760`
- `0x18004fbb0`
- `0x180088930`
- `0x180088960`
- `0x1800889f0`
- `0x180088a40`
- `0x180088a70`
- `0x180088bc0`

## callees

- `0x1800013a0`

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
0x180001b80  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
