# __memset_repmovs

- ea: `0x140003c00`
- end: `0x140003c43`
- name: `__memset_repmovs`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ac0`

## callees

- `0x140003c00`
- `0x140003c80`

## pseudocode

```c
__int64 __fastcall _memset_repmovs(_OWORD *a1, __int64 a2, __int64 a3)
{
  __int128 v3; // xmm0
  __int64 result; // rax

  if ( (_isa_info & 1) == 0 )
    result = _memset_query();
  *a1 = v3;
  a1[1] = v3;
  a1[2] = v3;
  a1[3] = v3;
  memset(
    (void *)((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL),
    v3,
    (unsigned __int64)a1 + a3 - ((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL));
  return result;
}

```

## disassembly

```asm
0x140003c00  push    rdi
0x140003c01  test    cs:__isa_info, 1
0x140003c08  jz      short loc_140003C3C
0x140003c0a  mov     rdi, rcx
0x140003c0d  add     r8, rcx
0x140003c10  movups  xmmword ptr [rcx], xmm0
0x140003c13  add     rdi, 40h ; '@'
0x140003c17  movups  xmmword ptr [rcx+10h], xmm0
0x140003c1b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140003c1f  movups  xmmword ptr [rcx+20h], xmm0
0x140003c23  sub     r8, rdi
0x140003c26  movups  xmmword ptr [rcx+30h], xmm0
0x140003c2a  mov     rcx, r8
0x140003c2d  mov     r9, rax
0x140003c30  movq    rax, xmm0
0x140003c35  rep stosb
0x140003c37  mov     rax, r9
0x140003c3a  pop     rdi
0x140003c3b  retn
0x140003c3c  call    __memset_query
0x140003c41  jmp     short loc_140003C0A
```
