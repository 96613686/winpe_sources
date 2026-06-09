# __memset_spec_ermsb_repmovsb

- ea: `0x140002cc0`
- end: `0x140002cf3`
- name: `__memset_spec_ermsb_repmovsb`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140002b80`

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
0x140002cc0  push    rdi
0x140002cc1  mov     rdi, rcx
0x140002cc4  add     r8, rcx
0x140002cc7  movups  xmmword ptr [rcx], xmm0
0x140002cca  add     rdi, 40h ; '@'
0x140002cce  movups  xmmword ptr [rcx+10h], xmm0
0x140002cd2  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140002cd6  movups  xmmword ptr [rcx+20h], xmm0
0x140002cda  sub     r8, rdi
0x140002cdd  movups  xmmword ptr [rcx+30h], xmm0
0x140002ce1  mov     rcx, r8
0x140002ce4  mov     r9, rax
0x140002ce7  movq    rax, xmm0
0x140002cec  rep stosb
0x140002cee  mov     rax, r9
0x140002cf1  pop     rdi
0x140002cf2  retn
```
