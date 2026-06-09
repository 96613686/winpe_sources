# get_block_stats

- ea: `0x18000ec98`
- end: `0x18000ecf7`
- name: `get_block_stats`
- size: `95`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e558`
- `0x180010130`
- `0x180014568`

## callees

- `0x180010064`
- `0x18001562a`

## pseudocode

```c
__int64 __fastcall get_block_stats(_DWORD *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  memset_0(a1 + 2640, 0, 2LL * (8 * a1[552] + 256));
  memset_0((char *)a1 + 15462, 0, 0x1F2u);
  return tally_frequency(a1, 0, 0, a4);
}

```

## disassembly

```asm
0x18000ec98  mov     [rsp+arg_0], rbx
0x18000ec9d  push    rdi
0x18000ec9e  sub     rsp, 20h
0x18000eca2  mov     eax, [rcx+8A0h]
0x18000eca8  mov     rdi, rcx
0x18000ecab  add     rcx, 2940h; void *
0x18000ecb2  xor     edx, edx; Val
0x18000ecb4  mov     ebx, r9d
0x18000ecb7  lea     eax, ds:100h[rax*8]
0x18000ecbe  movsxd  r8, eax
0x18000ecc1  add     r8, r8; Size
0x18000ecc4  call    memset_0
0x18000ecc9  lea     rcx, [rdi+3C66h]; void *
0x18000ecd0  xor     edx, edx; Val
0x18000ecd2  mov     r8d, 1F2h; Size
0x18000ecd8  call    memset_0
0x18000ecdd  mov     r9d, ebx
0x18000ece0  xor     r8d, r8d
0x18000ece3  xor     edx, edx
0x18000ece5  mov     rcx, rdi
0x18000ece8  mov     rbx, [rsp+28h+arg_0]
0x18000eced  add     rsp, 20h
0x18000ecf1  pop     rdi
0x18000ecf2  jmp     tally_frequency
```
