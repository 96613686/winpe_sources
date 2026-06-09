# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800019c0`
- `0x180002150`
- `0x180002190`
- `0x1800030d0`
- `0x1800030fc`
- `0x180003140`
- `0x180003180`
- `0x1800040d0`
- `0x180004390`
- `0x1800043d0`
- `0x180004410`
- `0x180004450`
- `0x1800044c8`
- `0x180004600`

## callees

- `0x180001526`

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
