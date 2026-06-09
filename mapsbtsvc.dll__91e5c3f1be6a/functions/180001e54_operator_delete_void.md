# operator delete(void *)

- ea: `0x180001e54`
- end: `0x180001e59`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `18`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001e94`
- `0x180002790`
- `0x180002af0`
- `0x180002b28`
- `0x180002b50`
- `0x180003248`
- `0x180003420`
- `0x180004648`
- `0x180004874`
- `0x1800048a0`
- `0x180006e70`
- `0x18000b8a4`
- `0x18000b8e0`
- `0x18000b910`
- `0x18000b950`
- `0x18000b980`
- `0x180012280`
- `0x180012ca0`

## callees

- `0x1800028d0`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180001e54  jmp     free
```
