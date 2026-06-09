# __memset_spec_ermsb_repmovsb

- ea: `0x140003c80`
- end: `0x140003cb3`
- name: `__memset_spec_ermsb_repmovsb`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140003b40`

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
0x140003c80  push    rdi
0x140003c81  mov     rdi, rcx
0x140003c84  add     r8, rcx
0x140003c87  movups  xmmword ptr [rcx], xmm0
0x140003c8a  add     rdi, 40h ; '@'
0x140003c8e  movups  xmmword ptr [rcx+10h], xmm0
0x140003c92  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140003c96  movups  xmmword ptr [rcx+20h], xmm0
0x140003c9a  sub     r8, rdi
0x140003c9d  movups  xmmword ptr [rcx+30h], xmm0
0x140003ca1  mov     rcx, r8
0x140003ca4  mov     r9, rax
0x140003ca7  movq    rax, xmm0
0x140003cac  rep stosb
0x140003cae  mov     rax, r9
0x140003cb1  pop     rdi
0x140003cb2  retn
```
