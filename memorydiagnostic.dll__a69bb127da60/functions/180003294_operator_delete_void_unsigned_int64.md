# operator delete(void *,unsigned __int64)

- ea: `0x180003294`
- end: `0x180003299`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `36`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005fa4`
- `0x1800060e4`
- `0x180006210`
- `0x18000772c`
- `0x18000779c`
- `0x180007818`
- `0x180007ee4`
- `0x180007f50`
- `0x180008950`
- `0x180008980`
- `0x1800089b0`
- `0x1800089f0`
- `0x180008a30`
- `0x180008aa0`
- `0x180008ae0`
- `0x180008b40`
- `0x180008ba0`
- `0x18001a208`
- `0x18001a2d0`
- `0x18001a310`
- `0x18001a350`
- `0x18001a390`
- `0x18001aa94`
- `0x18001c310`
- `0x18001cae4`
- `0x18001cd88`
- `0x18001d7a0`
- `0x18001e794`
- `0x18001e88c`
- `0x18001e9a8`
- `0x18001eaac`
- `0x18001ed4c`
- `0x18001efc0`
- `0x18001effc`
- `0x18001fa10`
- `0x180021555`

## callees

- `0x180003288`

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
0x180003294  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
