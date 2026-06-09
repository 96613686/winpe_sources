# operator delete(void *,unsigned __int64)

- ea: `0x180002ee4`
- end: `0x180002ee9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `111`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005038`
- `0x1800051b0`
- `0x180005a80`
- `0x180005ac0`
- `0x180005b00`
- `0x180005b70`
- `0x180005bb0`
- `0x180005c20`
- `0x180006734`
- `0x18000cac4`
- `0x18000cd50`
- `0x18000d028`
- `0x18000d228`
- `0x18000d248`
- `0x18000d390`
- `0x18000d5a8`
- `0x18000d668`
- `0x18000dc48`
- `0x18000de10`
- `0x18000e140`
- `0x1800126a0`
- `0x1800126c4`
- `0x1800128a8`
- `0x180017110`
- `0x18001adac`
- `0x18001afe0`
- `0x18001b214`
- `0x18001b480`
- `0x18001b7e0`
- `0x18001b9bc`
- `0x18001bbc8`
- `0x18001be38`
- `0x18001c08c`
- `0x18001c314`
- `0x18001c574`
- `0x18001c7e4`
- `0x18001ca60`
- `0x18001cd4c`
- `0x18001d1e0`
- `0x18001d534`
- `0x18001d650`
- `0x18001d754`
- `0x18001d894`
- `0x18001e53c`
- `0x18001e5ac`
- `0x18001e6dc`
- `0x18001e748`
- `0x18001e7bc`
- `0x18001e87c`
- `0x18001e948`

## callees

- `0x180002f4c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002ee4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
