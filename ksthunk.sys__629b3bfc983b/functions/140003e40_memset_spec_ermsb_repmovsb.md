# __memset_spec_ermsb_repmovsb

- ea: `0x140003e40`
- end: `0x140003e73`
- name: `__memset_spec_ermsb_repmovsb`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140003d00`

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
0x140003e40  push    rdi
0x140003e41  mov     rdi, rcx
0x140003e44  add     r8, rcx
0x140003e47  movups  xmmword ptr [rcx], xmm0
0x140003e4a  add     rdi, 40h ; '@'
0x140003e4e  movups  xmmword ptr [rcx+10h], xmm0
0x140003e52  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140003e56  movups  xmmword ptr [rcx+20h], xmm0
0x140003e5a  sub     r8, rdi
0x140003e5d  movups  xmmword ptr [rcx+30h], xmm0
0x140003e61  mov     rcx, r8
0x140003e64  mov     r9, rax
0x140003e67  movq    rax, xmm0
0x140003e6c  rep stosb
0x140003e6e  mov     rax, r9
0x140003e71  pop     rdi
0x140003e72  retn
```
