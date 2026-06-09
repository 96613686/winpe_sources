# operator delete(void *)

- ea: `0x140076620`
- end: `0x140076625`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140076074`
- `0x140076080`
- `0x14009323c`
- `0x140094794`

## callees

- `0x1400767c4`

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
0x140076620  jmp     free
```
