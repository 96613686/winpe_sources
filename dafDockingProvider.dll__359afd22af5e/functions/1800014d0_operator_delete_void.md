# operator delete(void *)

- ea: `0x1800014d0`
- end: `0x1800014d5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `62`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001550`
- `0x180001ba0`
- `0x180001f1c`
- `0x180003740`
- `0x180003770`
- `0x1800086a4`
- `0x18000871c`
- `0x180008738`
- `0x180008940`
- `0x1800089c0`
- `0x1800089f0`
- `0x18000a790`
- `0x18000bee0`
- `0x18000c4cc`
- `0x18000c930`
- `0x18000cc5c`
- `0x18000ccdc`
- `0x18000d400`
- `0x18000d4f4`
- `0x18000f160`
- `0x18000f1a0`
- `0x18000fce8`
- `0x1800111b4`
- `0x180011220`
- `0x18001134c`
- `0x180011430`
- `0x180012cd4`
- `0x18001320c`
- `0x180013390`
- `0x180013c98`
- `0x180013ce4`
- `0x180013d18`
- `0x180014030`
- `0x1800143b4`
- `0x1800145cc`
- `0x180014e20`
- `0x180015700`
- `0x1800165a4`
- `0x180016a30`
- `0x180016e2c`
- `0x180016e6c`
- `0x1800172d8`
- `0x1800182e4`
- `0x180018310`
- `0x18001837c`
- `0x1800183e4`
- `0x180018420`
- `0x180018710`
- `0x18001884c`
- `0x180018be0`

## callees

- `0x180002099`

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
0x1800014d0  jmp     free_0
```
