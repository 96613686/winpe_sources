# operator delete(void *)

- ea: `0x180001334`
- end: `0x180001339`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `39`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001340`
- `0x180003660`
- `0x1800036a0`
- `0x180003700`
- `0x180003740`
- `0x180003780`
- `0x1800037b0`
- `0x1800037f0`
- `0x180005140`
- `0x180006880`
- `0x180009690`
- `0x18000a3d0`
- `0x18000c018`
- `0x18000c410`
- `0x18000c5d0`
- `0x18000c65c`
- `0x18000d060`
- `0x18000d338`
- `0x18000e7ac`
- `0x18000f074`
- `0x18000fc80`
- `0x18000ffe0`
- `0x180010404`
- `0x180010780`
- `0x180012e80`
- `0x180013160`
- `0x180013458`
- `0x180014b78`
- `0x180015428`
- `0x180015930`
- `0x180016530`
- `0x180016a70`
- `0x180016fa8`
- `0x1800174f0`
- `0x18001772c`
- `0x18001775c`
- `0x1800178d4`
- `0x1800179f0`
- `0x180017ab0`

## callees

- `0x180001cbc`

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
0x180001334  jmp     free_0
```
