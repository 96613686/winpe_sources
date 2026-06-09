# operator delete(void *)

- ea: `0x18000e308`
- end: `0x18000e30d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000bff8`
- `0x18000cc1c`
- `0x18000cca4`
- `0x18000e264`
- `0x18000e2b0`
- `0x18000ff00`
- `0x180010208`
- `0x1800103a0`
- `0x1800103e0`
- `0x180010480`
- `0x1800104e0`
- `0x1800105d0`
- `0x180010610`

## callees

- `0x18000ef98`

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
0x18000e308  jmp     free
```
