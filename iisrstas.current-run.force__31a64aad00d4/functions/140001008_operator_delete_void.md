# operator delete[](void *)

- ea: `0x140001008`
- end: `0x14000100d`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001898`
- `0x140001a10`
- `0x140001f74`
- `0x1400023fc`
- `0x140002a40`

## callees

- `0x140001054`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x140001008  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
