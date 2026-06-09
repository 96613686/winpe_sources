# operator delete(void *)

- ea: `0x180002030`
- end: `0x180002035`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001010`
- `0x180001f40`
- `0x180002af0`
- `0x180002b1c`
- `0x180002b50`
- `0x180002c00`
- `0x180005360`
- `0x1800073c4`
- `0x1800073f0`

## callees

- `0x180002506`

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
0x180002030  jmp     free_0
```
