# operator delete(void *)

- ea: `0x180002f84`
- end: `0x180002f89`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `18`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002ee0`
- `0x180002ef0`
- `0x18000a9d8`
- `0x18000a9f4`
- `0x18000d5c0`
- `0x18000d600`
- `0x18000d630`
- `0x18000d660`
- `0x18000d6a0`
- `0x180010ca0`
- `0x180010ce0`
- `0x180010d10`
- `0x180010d40`
- `0x180010d80`
- `0x180011e74`
- `0x18001506c`
- `0x1800191ce`
- `0x180019204`

## callees

- `0x180003564`

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
0x180002f84  jmp     free
```
