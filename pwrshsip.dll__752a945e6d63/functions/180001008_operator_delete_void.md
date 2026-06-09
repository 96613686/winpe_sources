# operator delete(void *)

- ea: `0x180001008`
- end: `0x18000100d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `21`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001970`
- `0x1800019c0`
- `0x180001e40`
- `0x1800025b0`
- `0x180002720`
- `0x1800033c0`
- `0x180003400`
- `0x180003424`
- `0x1800034d4`
- `0x180003648`
- `0x1800037bc`
- `0x180003c70`
- `0x180003d50`
- `0x180003dd4`
- `0x180003ed8`
- `0x180004220`
- `0x1800042ec`
- `0x180004574`
- `0x180004700`
- `0x180004fd4`
- `0x1800050b0`

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
0x180001008  jmp     free_0
```
