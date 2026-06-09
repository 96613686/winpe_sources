# _tlgKeywordOn

- ea: `0x140001008`
- end: `0x140001037`
- name: `_tlgKeywordOn`
- size: `47`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x140009a30`
- `0x140009aac`
- `0x140009b28`
- `0x140009ba4`
- `0x140009c64`
- `0x140009f9c`
- `0x14000a018`
- `0x14000a394`
- `0x14000a410`
- `0x14000a48c`
- `0x14000a508`
- `0x14000a584`
- `0x14000a600`
- `0x14000b23c`
- `0x14000b2b8`
- `0x14000bb7c`
- `0x14000bbf8`
- `0x14000bc74`
- `0x14000bcf0`
- `0x14000cbe0`

## callees

- `0x140001008`

## pseudocode

```c
bool tlgKeywordOn()
{
  return (qword_140013020 & 0x400000000000LL) != 0 && (qword_140013028 & 0x400000000000LL) == qword_140013028;
}

```

## disassembly

```asm
0x140001008  mov     rcx, cs:qword_140013028
0x14000100f  mov     rdx, 400000000000h
0x140001019  mov     rax, cs:qword_140013020
0x140001020  test    rdx, rax
0x140001023  jz      short loc_140001034
0x140001025  mov     rax, rcx
0x140001028  and     rax, rdx
0x14000102b  cmp     rax, rcx
0x14000102e  jnz     short loc_140001034
0x140001030  mov     al, 1
0x140001032  retn
0x140001034  xor     al, al
0x140001036  retn
```
