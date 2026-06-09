# operator delete(void *)

- ea: `0x18000178c`
- end: `0x180001793`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __cdecl(void *Block)`
- caller_count: `107`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001e30`
- `0x18000272c`
- `0x180003c60`
- `0x180003c90`
- `0x180003cd0`
- `0x180005880`
- `0x180006c40`
- `0x1800091e8`
- `0x1800091f8`
- `0x180009374`
- `0x180009710`
- `0x180009d90`
- `0x180009f54`
- `0x18000ad18`
- `0x18000b194`
- `0x18000b218`
- `0x18000b240`
- `0x18000b268`
- `0x18000b290`
- `0x18000b2b8`
- `0x18000b2e0`
- `0x18000b308`
- `0x18000b330`
- `0x18000b358`
- `0x18000b380`
- `0x18000b3a8`
- `0x18000b3d0`
- `0x18000b400`
- `0x18000b440`
- `0x18000b480`
- `0x18000b4c0`
- `0x18000b500`
- `0x18000b540`
- `0x18000b580`
- `0x18000b5c0`
- `0x18000b600`
- `0x18000b640`
- `0x18000b678`
- `0x18000b6a0`
- `0x18000b6e0`
- `0x18000b720`
- `0x18000b760`
- `0x18000b7a0`
- `0x18000b7e0`
- `0x18000b820`
- `0x18000b860`
- `0x18000b8a0`
- `0x18000b8e0`
- `0x18000b920`
- `0x18000b960`

## import_xrefs

- `msvcrt!free` at `0x18000178c`

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
0x18000178c  jmp     cs:__imp_free
```
