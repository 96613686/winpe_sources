# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `30`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001be0`
- `0x180002c8c`
- `0x180003240`
- `0x180003918`
- `0x180003984`
- `0x180003b00`
- `0x180003b30`
- `0x180003cd8`
- `0x180007650`
- `0x180008550`
- `0x180008650`
- `0x1800095a0`
- `0x1800095e0`
- `0x180009640`
- `0x1800096a0`
- `0x1800097d0`
- `0x180009940`
- `0x180009ab0`
- `0x180009c20`
- `0x180009d50`
- `0x18000a100`
- `0x18000a190`
- `0x18000a220`
- `0x18000a2b0`
- `0x18000a410`
- `0x18000a4a0`
- `0x18000a51c`
- `0x18000ba58`
- `0x18000bdc0`
- `0x18000dd60`

## callees

- `0x180001532`

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
