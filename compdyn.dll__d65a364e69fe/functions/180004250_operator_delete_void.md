# operator delete(void *)

- ea: `0x180004250`
- end: `0x180004255`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800012b0`
- `0x180001890`
- `0x180001960`
- `0x180004130`
- `0x180005a40`
- `0x180006470`
- `0x180006550`
- `0x180006e14`

## callees

- `0x180004726`

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
0x180004250  jmp     free_0
```
