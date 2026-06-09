# operator delete(void *)

- ea: `0x180002014`
- end: `0x180002019`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002020`
- `0x1800021d0`
- `0x180002290`
- `0x180003fa8`
- `0x18000416c`
- `0x180004da0`
- `0x1800052b4`
- `0x1800080f0`
- `0x1800099c0`
- `0x18000a300`
- `0x18000c4a0`
- `0x18000cca0`
- `0x18000de40`
- `0x18000ece4`
- `0x18000ef18`
- `0x18000f90c`
- `0x18000ff6c`
- `0x180010634`
- `0x180012674`
- `0x18001356c`
- `0x180013c30`
- `0x180013e28`

## callees

- `0x180001e9a`

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
0x180002014  jmp     free
```
