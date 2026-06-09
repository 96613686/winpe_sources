# __memset_spec_ermsb_repmovsb

- ea: `0x1400048c0`
- end: `0x1400048f3`
- name: `__memset_spec_ermsb_repmovsb`
- size: `51`
- prototype: `void __fastcall(_OWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140004780`

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
0x1400048c0  push    rdi
0x1400048c1  mov     rdi, rcx
0x1400048c4  add     r8, rcx
0x1400048c7  movups  xmmword ptr [rcx], xmm0
0x1400048ca  add     rdi, 40h ; '@'
0x1400048ce  movups  xmmword ptr [rcx+10h], xmm0
0x1400048d2  and     rdi, 0FFFFFFFFFFFFFFC0h
0x1400048d6  movups  xmmword ptr [rcx+20h], xmm0
0x1400048da  sub     r8, rdi
0x1400048dd  movups  xmmword ptr [rcx+30h], xmm0
0x1400048e1  mov     rcx, r8
0x1400048e4  mov     r9, rax
0x1400048e7  movq    rax, xmm0
0x1400048ec  rep stosb
0x1400048ee  mov     rax, r9
0x1400048f1  pop     rdi
0x1400048f2  retn
```
