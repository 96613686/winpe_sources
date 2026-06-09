# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `34`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001d50`
- `0x180002380`
- `0x1800033e0`
- `0x180003eb0`
- `0x18000401c`
- `0x180004544`
- `0x1800047ec`
- `0x180004a40`
- `0x180004a80`
- `0x180005030`
- `0x180005068`
- `0x180007090`
- `0x180007180`
- `0x180007b00`
- `0x180008164`
- `0x180008d90`
- `0x180009b4c`
- `0x180009c00`
- `0x180009eb4`
- `0x18000ab6c`
- `0x18000abfc`
- `0x18000b180`
- `0x18000b21c`
- `0x18000b310`
- `0x18000b33c`
- `0x18000b564`
- `0x18000c390`
- `0x18000c640`
- `0x18000cb30`
- `0x18000d370`
- `0x18000e330`
- `0x18000e510`
- `0x18000e770`
- `0x18000eb10`

## callees

- `0x18000153c`

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
