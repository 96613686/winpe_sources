# __memset_spec_ermsb_repmovsb

- ea: `0x140001940`
- end: `0x140001973`
- name: `__memset_spec_ermsb_repmovsb`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001800`

## pseudocode

```c
void __fastcall _memset_spec_ermsb_repmovsb(_OWORD *a1, __int64 a2, __int64 a3)
{
  __int128 v3; // xmm0

  *a1 = v3;
  a1[1] = v3;
  a1[2] = v3;
  a1[3] = v3;
  memset(
    (void *)((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL),
    v3,
    (unsigned __int64)a1 + a3 - ((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL));
}

```

## disassembly

```asm
0x140001940  push    rdi
0x140001941  mov     rdi, rcx
0x140001944  add     r8, rcx
0x140001947  movups  xmmword ptr [rcx], xmm0
0x14000194a  add     rdi, 40h ; '@'
0x14000194e  movups  xmmword ptr [rcx+10h], xmm0
0x140001952  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140001956  movups  xmmword ptr [rcx+20h], xmm0
0x14000195a  sub     r8, rdi
0x14000195d  movups  xmmword ptr [rcx+30h], xmm0
0x140001961  mov     rcx, r8
0x140001964  mov     r9, rax
0x140001967  movq    rax, xmm0
0x14000196c  rep stosb
0x14000196e  mov     rax, r9
0x140001971  pop     rdi
0x140001972  retn
```
