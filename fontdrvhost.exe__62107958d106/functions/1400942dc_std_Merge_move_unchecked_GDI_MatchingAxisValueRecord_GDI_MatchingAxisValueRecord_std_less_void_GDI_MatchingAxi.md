# std::_Merge_move_unchecked<GDI::MatchingAxisValueRecord *,GDI::MatchingAxisValueRecord *,std::less<void>>(GDI::MatchingAxisValueRecord *,GDI::MatchingAxisValueRecord * const,GDI::MatchingAxisValueRecord * const,GDI::MatchingAxisValueRecord *,std::less<void>)

- ea: `0x1400942dc`
- end: `0x14009436f`
- name: `??$_Merge_move_unchecked@PEAUMatchingAxisValueRecord@GDI@@PEAU12@U?$less@X@std@@@std@@YAPEAUMatchingAxisValueRecord@GDI@@PEAU12@QEAU12@10U?$less@X@0@@Z`
- size: `147`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140093e00`

## callees

- `0x140076ef6`
- `0x1400942dc`

## pseudocode

```c
__int64 __fastcall std::_Merge_move_unchecked<GDI::MatchingAxisValueRecord *,GDI::MatchingAxisValueRecord *,std::less<void>>(
        _QWORD *Src,
        char *a2,
        char *a3,
        _OWORD *a4)
{
  _BYTE *v4; // rdi
  _OWORD *v5; // rbx
  __int128 v6; // xmm1
  size_t v7; // rdi
  __int128 v9; // xmm1
  __int64 v10; // rsi

  v4 = a2;
  while ( 1 )
  {
    v5 = a4 + 2;
    if ( *((_QWORD *)a2 + 1) >= Src[1] )
      break;
    *a4 = *(_OWORD *)a2;
    v6 = *((_OWORD *)a2 + 1);
    a2 += 32;
    a4[1] = v6;
    if ( a2 == a3 )
    {
      v7 = v4 - (_BYTE *)Src;
      memmove_0(a4 + 2, Src, v7);
      return (__int64)v5 + v7;
    }
LABEL_6:
    a4 += 2;
  }
  *a4 = *(_OWORD *)Src;
  v9 = *((_OWORD *)Src + 1);
  Src += 4;
  a4[1] = v9;
  if ( Src != (_QWORD *)v4 )
    goto LABEL_6;
  v10 = a3 - a2;
  memmove_0(a4 + 2, a2, a3 - a2);
  return (__int64)v5 + v10;
}

```

## disassembly

```asm
0x1400942dc  mov     [rsp+arg_0], rbx
0x1400942e1  mov     [rsp+arg_8], rsi
0x1400942e6  push    rdi
0x1400942e7  sub     rsp, 20h
0x1400942eb  mov     rsi, r8
0x1400942ee  mov     rdi, rdx
0x1400942f1  mov     rax, [rcx+8]
0x1400942f5  lea     rbx, [r9+20h]
0x1400942f9  cmp     [rdx+8], rax
0x1400942fd  jnb     short loc_14009432F
0x1400942ff  movups  xmm0, xmmword ptr [rdx]
0x140094302  movups  xmmword ptr [r9], xmm0
0x140094306  movups  xmm1, xmmword ptr [rdx+10h]
0x14009430a  add     rdx, 20h ; ' '
0x14009430e  movups  xmmword ptr [r9+10h], xmm1
0x140094313  cmp     rdx, rsi
0x140094316  jnz     short loc_140094348
0x140094318  sub     rdi, rcx
0x14009431b  mov     rdx, rcx; Src
0x14009431e  mov     r8, rdi; Size
0x140094321  mov     rcx, rbx; void *
0x140094324  call    memmove_0
0x140094329  lea     rax, [rdi+rbx]
0x14009432d  jmp     short loc_14009435F
0x14009432f  movups  xmm0, xmmword ptr [rcx]
0x140094332  movups  xmmword ptr [r9], xmm0
0x140094336  movups  xmm1, xmmword ptr [rcx+10h]
0x14009433a  add     rcx, 20h ; ' '
0x14009433e  movups  xmmword ptr [r9+10h], xmm1
0x140094343  cmp     rcx, rdi
0x140094346  jz      short loc_14009434D
0x140094348  mov     r9, rbx
0x14009434b  jmp     short loc_1400942F1
0x14009434d  sub     rsi, rdx
0x140094350  mov     rcx, rbx; void *
0x140094353  mov     r8, rsi; Size
0x140094356  call    memmove_0
0x14009435b  lea     rax, [rsi+rbx]
0x14009435f  mov     rbx, [rsp+28h+arg_0]
0x140094364  mov     rsi, [rsp+28h+arg_8]
0x140094369  add     rsp, 20h
0x14009436d  pop     rdi
0x14009436e  retn
```
