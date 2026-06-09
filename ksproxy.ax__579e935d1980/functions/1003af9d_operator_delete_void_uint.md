# operator delete(void *,uint)

- ea: `0x1003af9d`
- end: `0x1003afad`
- name: `??3@YAXPAXI@Z`
- size: `16`
- prototype: `void __cdecl(void *Block, unsigned int)`
- caller_count: `78`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x10008bf0`
- `0x1000b910`
- `0x1000ba10`
- `0x1000bb10`
- `0x1000cf60`
- `0x1000ea60`
- `0x1000f5dc`
- `0x10010250`
- `0x10010350`
- `0x10010590`
- `0x10010760`
- `0x100110e0`
- `0x1001110d`
- `0x10013a30`
- `0x10014780`
- `0x100147ad`
- `0x10014a8b`
- `0x100150a0`
- `0x10017097`
- `0x10017f50`
- `0x100181f0`
- `0x10018250`
- `0x100182b0`
- `0x10018300`
- `0x10018450`
- `0x10019960`
- `0x10019990`
- `0x1001a710`
- `0x1001a8f0`
- `0x1001c7fd`
- `0x1001c916`
- `0x1001cc70`
- `0x1001cd50`
- `0x1001cfd0`
- `0x1001d103`
- `0x1001d3d0`
- `0x1001d6ae`
- `0x1001d8a0`
- `0x1001d9fe`
- `0x1001dc00`
- `0x1001dc70`
- `0x1001dfb0`
- `0x1001e1f8`
- `0x10020bea`
- `0x10021391`
- `0x100213de`
- `0x1002179f`
- `0x10021a03`
- `0x10021c30`
- `0x10021d80`

## callees

- `0x1003a73d`

## pseudocode

```c
void __cdecl operator delete(void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x1003af9d  mov     edi, edi
0x1003af9f  push    ebp
0x1003afa0  mov     ebp, esp
0x1003afa2  push    [ebp+Block]; Block
0x1003afa5  call    ??3@YAXPAX@Z; operator delete(void *)
0x1003afaa  pop     ecx
0x1003afab  pop     ebp
0x1003afac  retn
```
