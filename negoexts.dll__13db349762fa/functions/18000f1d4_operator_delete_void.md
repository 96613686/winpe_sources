# operator delete(void *)

- ea: `0x18000f1d4`
- end: `0x18000f1d9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180010b40`

## callees

- `0x18000f9b2`

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
0x18000f1d4  jmp     free_0
```
