# operator delete(void *,unsigned __int64)

- ea: `0x1400021b4`
- end: `0x1400021b9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400045d4`
- `0x140004718`
- `0x140004d8c`
- `0x140005020`
- `0x14000513c`
- `0x140005580`
- `0x140005960`
- `0x140005a04`
- `0x140005b20`
- `0x140005b60`
- `0x140005ba0`
- `0x140005c00`
- `0x140005c40`
- `0x140005ca0`
- `0x14000cd48`
- `0x14000e878`
- `0x14000eeb8`

## callees

- `0x140002178`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1400021b4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
