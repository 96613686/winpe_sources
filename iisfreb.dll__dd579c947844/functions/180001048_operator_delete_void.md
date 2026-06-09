# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001af4`
- `0x180001b6c`
- `0x180001d00`
- `0x180001d30`
- `0x180001d74`
- `0x180001e90`
- `0x180003600`
- `0x180003630`
- `0x180003a10`
- `0x1800054e8`
- `0x180006910`
- `0x180006aec`
- `0x180006f98`
- `0x180007d84`
- `0x180007e04`
- `0x180008424`
- `0x1800087a8`
- `0x180008958`
- `0x180009050`
- `0x1800097c4`
- `0x18000a4dc`
- `0x18000a7e0`
- `0x18000a934`
- `0x18000aad4`

## callees

- `0x180001854`

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
0x180001048  jmp     free_0
```
