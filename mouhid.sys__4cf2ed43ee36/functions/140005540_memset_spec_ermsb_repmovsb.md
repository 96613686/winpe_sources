# __memset_spec_ermsb_repmovsb

- ea: `0x140005540`
- end: `0x140005573`
- name: `__memset_spec_ermsb_repmovsb`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140005400`

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
0x140005540  push    rdi
0x140005541  mov     rdi, rcx
0x140005544  add     r8, rcx
0x140005547  movups  xmmword ptr [rcx], xmm0
0x14000554a  add     rdi, 40h ; '@'
0x14000554e  movups  xmmword ptr [rcx+10h], xmm0
0x140005552  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140005556  movups  xmmword ptr [rcx+20h], xmm0
0x14000555a  sub     r8, rdi
0x14000555d  movups  xmmword ptr [rcx+30h], xmm0
0x140005561  mov     rcx, r8
0x140005564  mov     r9, rax
0x140005567  movq    rax, xmm0
0x14000556c  rep stosb
0x14000556e  mov     rax, r9
0x140005571  pop     rdi
0x140005572  retn
```
