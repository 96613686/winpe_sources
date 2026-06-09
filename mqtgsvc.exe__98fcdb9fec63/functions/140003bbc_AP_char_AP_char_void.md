# AP<char>::~AP<char>(void)

- ea: `0x140003bbc`
- end: `0x140003bcf`
- name: `??1?$AP@D@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(void **)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x14001d19a`
- `0x14001e4ec`
- `0x14001e4fe`
- `0x14001e510`
- `0x14001e667`
- `0x14001e6d3`
- `0x14001e966`
- `0x14001ea71`
- `0x14001ee31`
- `0x14001ee43`

## import_xrefs

- `msvcrt!free` at `0x140003bc3`
- `msvcrt!free` at `0x140003bc3`

## pseudocode

```c
void __fastcall AP<char>::~AP<char>(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x140003bbc  sub     rsp, 28h
0x140003bc0  mov     rcx, [rcx]; Block
0x140003bc3  call    cs:__imp_free
0x140003bc9  nop
0x140003bca  add     rsp, 28h
0x140003bce  retn
```
