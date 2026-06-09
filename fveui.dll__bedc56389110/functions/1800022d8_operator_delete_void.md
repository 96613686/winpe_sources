# operator delete(void *)

- ea: `0x1800022d8`
- end: `0x1800022dd`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001bd4`
- `0x180001c50`
- `0x18001114c`
- `0x18001167c`
- `0x1800126b8`
- `0x1800128ac`
- `0x1800129dc`
- `0x180013660`
- `0x1800137d8`
- `0x180015400`
- `0x18002980c`
- `0x180029e18`
- `0x180029ea8`
- `0x18002a330`
- `0x18002ab90`
- `0x18002add0`
- `0x18002af40`

## callees

- `0x180002720`

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
0x1800022d8  jmp     free
```
