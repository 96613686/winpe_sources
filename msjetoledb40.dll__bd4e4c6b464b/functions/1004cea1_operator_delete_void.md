# operator delete(void *)

- ea: `0x1004cea1`
- end: `0x1004cea7`
- name: `??3@YAXPAX@Z`
- size: `6`
- prototype: `void __cdecl(void *Block)`
- caller_count: `89`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1000bcf0`
- `0x1000be60`
- `0x1000c0d0`
- `0x1000d450`
- `0x1000d510`
- `0x1000e9d0`
- `0x1000e9f0`
- `0x1000ec00`
- `0x1000ecc0`
- `0x1000ee10`
- `0x1000f0b0`
- `0x1000f690`
- `0x1000f6d0`
- `0x1000f840`
- `0x10012360`
- `0x10012470`
- `0x100124f0`
- `0x10012e10`
- `0x10012f70`
- `0x10013b30`
- `0x10013d20`
- `0x10013d50`
- `0x10013f50`
- `0x100147f0`
- `0x10014a70`
- `0x10015d90`
- `0x10015dc0`
- `0x10016040`
- `0x10016be0`
- `0x10016c40`
- `0x10016d50`
- `0x10016f60`
- `0x10017160`
- `0x10017690`
- `0x10017930`
- `0x10017960`
- `0x10017b50`
- `0x10018750`
- `0x100198d0`
- `0x1001a7b0`
- `0x1001a970`
- `0x1001b4a0`
- `0x1001bdc0`
- `0x1001c890`
- `0x1001d3b0`
- `0x1001df20`
- `0x1001ebc0`
- `0x1001f270`
- `0x1001f370`
- `0x1001f4f0`

## import_xrefs

- `msvcrt!free` at `0x1004cea1`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  _free(Block);
}

```

## disassembly

```asm
0x1004cea1  jmp     ds:__imp__free
```
