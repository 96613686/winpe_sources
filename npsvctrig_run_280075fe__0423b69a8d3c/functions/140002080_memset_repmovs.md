# __memset_repmovs

- ea: `0x140002080`
- end: `0x1400020c3`
- name: `__memset_repmovs`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001f40`

## callees

- `0x140002080`
- `0x140002100`

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
0x140002080  push    rdi
0x140002081  test    cs:__isa_info, 1
0x140002088  jz      short loc_1400020BC
0x14000208a  mov     rdi, rcx
0x14000208d  add     r8, rcx
0x140002090  movups  xmmword ptr [rcx], xmm0
0x140002093  add     rdi, 40h ; '@'
0x140002097  movups  xmmword ptr [rcx+10h], xmm0
0x14000209b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x14000209f  movups  xmmword ptr [rcx+20h], xmm0
0x1400020a3  sub     r8, rdi
0x1400020a6  movups  xmmword ptr [rcx+30h], xmm0
0x1400020aa  mov     rcx, r8
0x1400020ad  mov     r9, rax
0x1400020b0  movq    rax, xmm0
0x1400020b5  rep stosb
0x1400020b7  mov     rax, r9
0x1400020ba  pop     rdi
0x1400020bb  retn
0x1400020bc  call    __memset_query
0x1400020c1  jmp     short loc_14000208A
```
