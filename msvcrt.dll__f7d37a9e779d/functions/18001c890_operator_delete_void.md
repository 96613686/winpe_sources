# operator delete(void *)

- ea: `0x18001c890`
- end: `0x18001c895`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000afb0`
- `0x18000b040`
- `0x18000b0d0`
- `0x18000b7e0`
- `0x1800173d0`
- `0x180017db0`
- `0x180017ddc`
- `0x180017e64`
- `0x180017ea0`
- `0x1800183f0`
- `0x18001c8b0`
- `0x18007b6f2`
- `0x18007b7d6`

## callees

- `0x18001d300`

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
0x18001c890  jmp     free; void operator delete(void *)
```
