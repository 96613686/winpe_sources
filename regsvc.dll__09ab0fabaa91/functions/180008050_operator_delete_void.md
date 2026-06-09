# operator delete(void *)

- ea: `0x180008050`
- end: `0x180008055`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `45`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001520`
- `0x180002810`
- `0x180003810`
- `0x180003b40`
- `0x180004bb0`
- `0x180005680`
- `0x180005f20`
- `0x180006bc0`
- `0x180006fd0`
- `0x180008080`
- `0x180008230`
- `0x1800082f0`
- `0x1800093a8`
- `0x18000a2a4`
- `0x18000ae4c`
- `0x18000b350`
- `0x18000b6d4`
- `0x18000bbec`
- `0x18000be10`
- `0x18000c2b0`
- `0x18000cb04`
- `0x18000cc70`
- `0x18000d158`
- `0x18000d4ac`
- `0x18000da58`
- `0x18000e1a8`
- `0x18000f640`
- `0x18000fb6c`
- `0x180010430`
- `0x180010f28`
- `0x180011180`
- `0x180011568`
- `0x180011d10`
- `0x180012604`
- `0x1800146c8`
- `0x180014b54`
- `0x180015250`
- `0x180015e20`
- `0x1800161a4`
- `0x180016260`
- `0x1800163f4`
- `0x180016544`
- `0x1800166cc`
- `0x18001681c`
- `0x180016930`

## callees

- `0x180008006`

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
0x180008050  jmp     free
```
