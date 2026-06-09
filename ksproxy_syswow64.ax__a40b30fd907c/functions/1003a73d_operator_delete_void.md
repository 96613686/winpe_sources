# operator delete(void *)

- ea: `0x1003a73d`
- end: `0x1003a742`
- name: `??3@YAXPAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x10037750`
- `0x100378f0`
- `0x10037fa0`
- `0x100388f0`
- `0x10038920`
- `0x10038950`
- `0x100389b0`
- `0x10038d40`
- `0x10039b30`
- `0x10039ca0`
- `0x10039cf0`
- `0x1003a6f2`
- `0x1003af9d`

## callees

- `0x1003b5b4`

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
0x1003a73d  jmp     _free
```
