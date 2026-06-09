# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180006600`
- end: `0x1800067ae`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `430`
- prototype: `_QWORD *__fastcall(_QWORD *Src, _QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800067b4`
- `0x180006dc0`
- `0x180007178`

## callees

- `0x180006418`
- `0x1800065d0`
- `0x1800065e8`
- `0x180006600`
- `0x18000ab16`
- `0x18000ab22`

## pseudocode

```c
_QWORD *__fastcall std::wstring::assign(_QWORD *Src, _QWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbp
  _QWORD *v6; // r14
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // rdi
  _QWORD *v13; // r9
  _QWORD *v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rax
  unsigned __int64 v17; // r8
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  unsigned __int64 v20; // rax
  _QWORD *v21; // rcx
  void *v22; // rcx
  _WORD *v23; // rax
  _QWORD *v24; // rax

  v4 = a2[2];
  v5 = a3;
  v6 = a2;
  if ( v4 < a3 )
    std::wstring::_Xran();
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( Src == a2 )
  {
    v9 = v8 + a3;
    v10 = Src[2];
    if ( v10 < v9 )
      std::wstring::_Xran();
    v11 = v10 - v9;
    v12 = -1;
    if ( v11 != -1 )
    {
      if ( !v11 )
      {
LABEL_16:
        v17 = Src[2];
        if ( v17 < v5 )
          v5 = Src[2];
        if ( v5 )
        {
          if ( Src[3] < 8u )
          {
            v18 = Src;
            v19 = Src;
          }
          else
          {
            v18 = (_QWORD *)*Src;
            v19 = (_QWORD *)*Src;
          }
          memmove_0(v18, (char *)v19 + 2 * v5, 2 * (v17 - v5));
          v20 = Src[2] - v5;
          if ( Src[3] < 8u )
            v21 = Src;
          else
            v21 = (_QWORD *)*Src;
          Src[2] = v20;
          *((_WORD *)v21 + v20) = 0;
        }
        return Src;
      }
      v12 = v11;
    }
    if ( Src[3] < 8u )
    {
      v13 = Src;
      v14 = Src;
    }
    else
    {
      v13 = (_QWORD *)*Src;
      v14 = (_QWORD *)*Src;
    }
    memmove_0((char *)v13 + 2 * v9, (char *)v14 + 2 * v9 + 2 * v12, 2 * (v11 - v12));
    v15 = Src[2] - v12;
    if ( Src[3] < 8u )
      v16 = Src;
    else
      v16 = (_QWORD *)*Src;
    Src[2] = v15;
    *((_WORD *)v16 + v15) = 0;
    goto LABEL_16;
  }
  if ( v8 > 0x7FFFFFFFFFFFFFFELL )
    std::wstring::_Xlen();
  if ( Src[3] >= v8 )
  {
    if ( !v8 )
    {
      if ( Src[3] < 8u )
        v23 = Src;
      else
        v23 = (_WORD *)*Src;
      Src[2] = 0;
      *v23 = 0;
      return Src;
    }
  }
  else
  {
    std::wstring::_Copy((const void **)Src, v8, Src[2]);
    if ( !v8 )
      return Src;
  }
  if ( v6[3] >= 8u )
    v6 = (_QWORD *)*v6;
  if ( Src[3] < 8u )
    v22 = Src;
  else
    v22 = (void *)*Src;
  memcpy_0(v22, (char *)v6 + 2 * v5, 2 * v8);
  if ( Src[3] < 8u )
    v24 = Src;
  else
    v24 = (_QWORD *)*Src;
  Src[2] = v8;
  *((_WORD *)v24 + v8) = 0;
  return Src;
}

```

## disassembly

```asm
0x180006600  push    rbx
0x180006602  push    rbp
0x180006603  push    rsi
0x180006604  push    rdi
0x180006605  push    r14
0x180006607  push    r15
0x180006609  sub     rsp, 28h
0x18000660d  mov     rdi, [rdx+10h]
0x180006611  mov     rbp, r8
0x180006614  mov     r14, rdx
0x180006617  mov     rbx, rcx
0x18000661a  cmp     rdi, r8
0x18000661d  jb      loc_18000679C
0x180006623  sub     rdi, r8
0x180006626  cmp     r9, rdi
0x180006629  cmovb   rdi, r9
0x18000662d  cmp     rcx, rdx
0x180006630  jnz     loc_180006702
0x180006636  lea     rcx, [rdi+r8]
0x18000663a  mov     r8, [rbx+10h]
0x18000663e  cmp     r8, rcx
0x180006641  jb      loc_1800067A2
0x180006647  sub     r8, rcx
0x18000664a  xor     esi, esi
0x18000664c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006650  cmp     r8, rdi
0x180006653  jnb     short loc_18000665D
0x180006655  test    r8, r8
0x180006658  jz      short loc_1800066A7
0x18000665a  mov     rdi, r8
0x18000665d  cmp     qword ptr [rbx+18h], 8
0x180006662  jb      short loc_18000666C
0x180006664  mov     r9, [rbx]
0x180006667  mov     rdx, r9
0x18000666a  jmp     short loc_180006672
0x18000666c  mov     r9, rbx
0x18000666f  mov     rdx, rbx
0x180006672  lea     rax, [rcx+rdi]
0x180006676  sub     r8, rdi
0x180006679  add     r8, r8; Size
0x18000667c  lea     rdx, [rdx+rax*2]; Src
0x180006680  lea     rcx, [r9+rcx*2]; void *
0x180006684  call    memmove_0
0x180006689  mov     rcx, [rbx+10h]
0x18000668d  sub     rcx, rdi
0x180006690  cmp     qword ptr [rbx+18h], 8
0x180006695  jb      short loc_18000669C
0x180006697  mov     rax, [rbx]
0x18000669a  jmp     short loc_18000669F
0x18000669c  mov     rax, rbx
0x18000669f  mov     [rbx+10h], rcx
0x1800066a3  mov     [rax+rcx*2], si
0x1800066a7  mov     r8, [rbx+10h]
0x1800066ab  cmp     r8, rbp
0x1800066ae  cmovb   rbp, r8
0x1800066b2  test    rbp, rbp
0x1800066b5  jz      loc_18000678C
0x1800066bb  cmp     qword ptr [rbx+18h], 8
0x1800066c0  jb      short loc_1800066CA
0x1800066c2  mov     rcx, [rbx]
0x1800066c5  mov     rax, rcx
0x1800066c8  jmp     short loc_1800066D0
0x1800066ca  mov     rcx, rbx; void *
0x1800066cd  mov     rax, rbx
0x1800066d0  sub     r8, rbp
0x1800066d3  lea     rdx, [rax+rbp*2]; Src
0x1800066d7  add     r8, r8; Size
0x1800066da  call    memmove_0
0x1800066df  mov     rax, [rbx+10h]
0x1800066e3  sub     rax, rbp
0x1800066e6  cmp     qword ptr [rbx+18h], 8
0x1800066eb  jb      short loc_1800066F2
0x1800066ed  mov     rcx, [rbx]
0x1800066f0  jmp     short loc_1800066F5
0x1800066f2  mov     rcx, rbx; Src
0x1800066f5  mov     [rbx+10h], rax
0x1800066f9  mov     [rcx+rax*2], si
0x1800066fd  jmp     loc_18000678C
0x180006702  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000670c  cmp     rdi, rax
0x18000670f  ja      loc_1800067A8
0x180006715  xor     esi, esi
0x180006717  cmp     [rcx+18h], rdi
0x18000671b  jnb     short loc_180006744
0x18000671d  mov     r8, [rcx+10h]
0x180006721  mov     rdx, rdi
0x180006724  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180006729  test    rdi, rdi
0x18000672c  jz      short loc_18000678C
0x18000672e  cmp     qword ptr [r14+18h], 8
0x180006733  jb      short loc_180006738
0x180006735  mov     r14, [r14]
0x180006738  cmp     qword ptr [rbx+18h], 8
0x18000673d  jb      short loc_180006761
0x18000673f  mov     rcx, [rbx]
0x180006742  jmp     short loc_180006764
0x180006744  test    rdi, rdi
0x180006747  jnz     short loc_18000672E
0x180006749  cmp     qword ptr [rcx+18h], 8
0x18000674e  jb      short loc_180006755
0x180006750  mov     rax, [rcx]
0x180006753  jmp     short loc_180006758
0x180006755  mov     rax, rbx
0x180006758  mov     [rcx+10h], rsi
0x18000675c  mov     [rax], si
0x18000675f  jmp     short loc_18000678C
0x180006761  mov     rcx, rbx; void *
0x180006764  lea     r15, [rdi+rdi]
0x180006768  mov     r8, r15; Size
0x18000676b  lea     rdx, [r14+rbp*2]; Src
0x18000676f  call    memcpy_0
0x180006774  cmp     qword ptr [rbx+18h], 8
0x180006779  jb      short loc_180006780
0x18000677b  mov     rax, [rbx]
0x18000677e  jmp     short loc_180006783
0x180006780  mov     rax, rbx
0x180006783  mov     [rbx+10h], rdi
0x180006787  mov     [r15+rax], si
0x18000678c  mov     rax, rbx
0x18000678f  add     rsp, 28h
0x180006793  pop     r15
0x180006795  pop     r14
0x180006797  pop     rdi
0x180006798  pop     rsi
0x180006799  pop     rbp
0x18000679a  pop     rbx
0x18000679b  retn
0x18000679c  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x1800067a2  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x1800067a8  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
