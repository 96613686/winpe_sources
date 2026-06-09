# std::vector<uchar,std::allocator<uchar>>::_Insert_n(std::_Vector_iterator<uchar,std::allocator<uchar>>,unsigned __int64,uchar const &)

- ea: `0x180060580`
- end: `0x180060827`
- name: `?_Insert_n@?$vector@EV?$allocator@E@std@@@std@@IEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@2@_KAEBE@Z`
- size: `679`
- prototype: ``
- caller_count: `13`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18005e9ac`
- `0x18005f688`
- `0x18005faf0`
- `0x18005ff48`
- `0x180060188`
- `0x180060238`
- `0x1800602e8`
- `0x1800603c4`
- `0x18006046c`
- `0x180060500`
- `0x18010ea14`
- `0x18010ece0`
- `0x180111f4c`

## callees

- `0x18000171c`
- `0x180060580`
- `0x18009219c`
- `0x1800b3d2c`
- `0x1800cd178`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800d6354`

## import_xrefs

- `msvcrt!memmove_s` at `0x180060693`
- `msvcrt!memmove_s` at `0x1800606ba`
- `msvcrt!memmove_s` at `0x180060749`
- `msvcrt!memmove_s` at `0x1800607a8`
- `msvcrt!memmove_s` at `0x180060693`
- `msvcrt!memmove_s` at `0x1800606ba`
- `msvcrt!memmove_s` at `0x180060749`
- `msvcrt!memmove_s` at `0x1800607a8`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180060803`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180060803`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<unsigned char>::_Insert_n(__int64 a1, _BYTE *a2, rsize_t a3, _BYTE *a4)
{
  char *result; // rax
  char v8; // r12
  __int64 v9; // rdx
  unsigned __int64 v10; // r8
  void **v11; // r14
  unsigned __int64 v12; // rax
  char *v13; // rax
  size_t v14; // rdi
  char *v15; // rax
  char *v16; // rax
  size_t v17; // rcx
  char *v18; // rax
  char *v19; // r15
  _BYTE *v20; // r8
  rsize_t v21; // rdx
  char *v22; // r12
  _BYTE *v23; // rcx
  char *v24; // r15
  rsize_t v25; // rdx
  size_t v26; // rdi
  _BYTE *v27; // rcx
  size_t v28; // r8
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-40h] BYREF
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF
  const char *Val; // [rsp+70h] [rbp+8h] BYREF
  char *v32; // [rsp+80h] [rbp+18h] BYREF

  result = (char *)&retaddr;
  LOBYTE(Val) = *a4;
  v8 = (char)Val;
  LOBYTE(v32) = (_BYTE)Val;
  v9 = *(_QWORD *)(a1 + 8);
  if ( v9 )
    v10 = *(_QWORD *)(a1 + 24) - v9;
  else
    v10 = 0;
  if ( a3 )
  {
    v11 = (void **)(a1 + 16);
    if ( v9 )
      v12 = (unsigned __int64)*v11 - v9;
    else
      v12 = 0;
    if ( ~v12 < a3 )
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(a1);
    if ( v9 )
      v13 = (char *)*v11 - v9;
    else
      v13 = 0;
    if ( v10 >= (unsigned __int64)&v13[a3] )
    {
      v24 = (char *)*v11;
      v25 = (_BYTE *)*v11 - a2;
      if ( v25 >= a3 )
      {
        memmove_s(*v11, a3, &v24[-a3], a3);
        *v11 = &v24[a3];
        std::copy_backward<unsigned char *,unsigned char *>(a2);
        return (char *)std::fill<unsigned char *,unsigned char>(a2, &a2[a3], &v32);
      }
      else
      {
        if ( v25 )
          memmove_s(&a2[a3], v25, a2, (_BYTE *)*v11 - a2);
        v26 = &a2[a3] - (_BYTE *)*v11;
        if ( v26 )
        {
          LOBYTE(v25) = v8;
          memset_0(*v11, v25, v26);
        }
        v27 = *v11;
        *v11 = (char *)*v11 + a3;
        v28 = v27 - a2;
        result = 0;
        if ( a2 > v27 )
          v28 = 0;
        if ( v28 )
        {
          LOBYTE(v25) = v8;
          return (char *)memset_0(a2, v25, v28);
        }
      }
    }
    else
    {
      if ( ~(v10 >> 1) < v10 )
        v14 = 0;
      else
        v14 = (v10 >> 1) + v10;
      if ( v9 )
        v15 = (char *)*v11 - v9;
      else
        v15 = 0;
      if ( v14 < (unsigned __int64)&v15[a3] )
      {
        if ( v9 )
          v16 = (char *)*v11 - v9;
        else
          v16 = 0;
        v14 = (size_t)&v16[a3];
      }
      if ( v14 )
      {
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v14) )
        {
          Val = 0;
          exception::exception((exception *)pExceptionObject, &Val);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v17 = v14;
      }
      else
      {
        v17 = 0;
      }
      v18 = (char *)operator new(v17);
      v19 = v18;
      v32 = v18;
      v20 = *(_BYTE **)(a1 + 8);
      v21 = a2 - v20;
      v22 = &v18[a2 - v20];
      if ( a2 != v20 )
        memmove_s(v18, v21, v20, a2 - v20);
      LOBYTE(v21) = (_BYTE)Val;
      memset_0(v22, v21, a3);
      if ( *v11 != a2 )
        memmove_s(&v22[a3], (_BYTE *)*v11 - a2, a2, (_BYTE *)*v11 - a2);
      v23 = *(_BYTE **)(a1 + 8);
      if ( v23 )
      {
        a3 += (_BYTE *)*v11 - v23;
        operator delete(v23);
      }
      *(_QWORD *)(a1 + 24) = &v19[v14];
      result = &v19[a3];
      *v11 = &v19[a3];
      *(_QWORD *)(a1 + 8) = v19;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180060580  mov     rax, rsp
0x180060583  push    rdi
0x180060584  push    r12
0x180060586  push    r13
0x180060588  push    r14
0x18006058a  push    r15
0x18006058c  sub     rsp, 40h
0x180060590  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180060598  mov     [rax+10h], rbx
0x18006059c  mov     [rax+20h], rsi
0x1800605a0  mov     rsi, r8
0x1800605a3  mov     rbx, rdx
0x1800605a6  mov     r13, rcx
0x1800605a9  mov     r12b, [r9]
0x1800605ac  mov     [rax+8], r12b
0x1800605b0  mov     [rax+18h], r12b
0x1800605b4  mov     rdx, [rcx+8]
0x1800605b8  test    rdx, rdx
0x1800605bb  jz      loc_180060721
0x1800605c1  mov     r8, [rcx+18h]
0x1800605c5  sub     r8, rdx
0x1800605c8  test    rsi, rsi
0x1800605cb  jz      loc_1800606EB
0x1800605d1  lea     r14, [rcx+10h]
0x1800605d5  test    rdx, rdx
0x1800605d8  jz      loc_180060705
0x1800605de  mov     rax, [r14]
0x1800605e1  sub     rax, rdx
0x1800605e4  not     rax
0x1800605e7  cmp     rax, rsi
0x1800605ea  jb      loc_1800607E3
0x1800605f0  test    rdx, rdx
0x1800605f3  jz      loc_18006070C
0x1800605f9  mov     rax, [r14]
0x1800605fc  sub     rax, rdx
0x1800605ff  add     rax, rsi
0x180060602  cmp     r8, rax
0x180060605  jnb     loc_180060729
0x18006060b  mov     rcx, r8
0x18006060e  shr     rcx, 1
0x180060611  mov     rax, rcx
0x180060614  not     rax
0x180060617  cmp     rax, r8
0x18006061a  jb      loc_1800607DC
0x180060620  lea     rdi, [rcx+r8]
0x180060624  test    rdx, rdx
0x180060627  jz      loc_180060713
0x18006062d  mov     rax, [r14]
0x180060630  sub     rax, rdx
0x180060633  add     rax, rsi
0x180060636  cmp     rdi, rax
0x180060639  jnb     short loc_18006064E
0x18006063b  test    rdx, rdx
0x18006063e  jz      loc_18006071A
0x180060644  mov     rax, [r14]
0x180060647  sub     rax, rdx
0x18006064a  lea     rdi, [rax+rsi]
0x18006064e  test    rdi, rdi
0x180060651  jz      loc_1800607E9
0x180060657  xor     edx, edx
0x180060659  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006065d  div     rdi
0x180060660  cmp     rax, 1
0x180060664  jb      loc_1800607F0
0x18006066a  mov     rcx, rdi; Size
0x18006066d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060672  mov     r15, rax
0x180060675  mov     [rsp+68h+arg_10], rax
0x18006067d  mov     r8, [r13+8]; Source
0x180060681  mov     rdx, rbx
0x180060684  sub     rdx, r8; DestinationSize
0x180060687  lea     r12, [rdx+rax]
0x18006068b  jz      short loc_180060699
0x18006068d  mov     r9, rdx; SourceSize
0x180060690  mov     rcx, rax; Destination
0x180060693  call    cs:__imp_memmove_s
0x180060699  mov     r8, rsi; Size
0x18006069c  mov     dl, byte ptr [rsp+68h+Val]; Val
0x1800606a0  mov     rcx, r12; void *
0x1800606a3  call    memset_0
0x1800606a8  mov     rdx, [r14]
0x1800606ab  sub     rdx, rbx; DestinationSize
0x1800606ae  jz      short loc_1800606C1
0x1800606b0  lea     rcx, [r12+rsi]; Destination
0x1800606b4  mov     r9, rdx; SourceSize
0x1800606b7  mov     r8, rbx; Source
0x1800606ba  call    cs:__imp_memmove_s
0x1800606c0  nop
0x1800606c1  mov     rcx, [r13+8]; Block
0x1800606c5  test    rcx, rcx
0x1800606c8  jz      short loc_1800606D8
0x1800606ca  mov     rax, [r14]
0x1800606cd  sub     rax, rcx
0x1800606d0  add     rsi, rax
0x1800606d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800606d8  lea     rax, [r15+rdi]
0x1800606dc  mov     [r13+18h], rax
0x1800606e0  lea     rax, [rsi+r15]
0x1800606e4  mov     [r14], rax
0x1800606e7  mov     [r13+8], r15
0x1800606eb  lea     r11, [rsp+68h+var_28]
0x1800606f0  mov     rbx, [r11+38h]
0x1800606f4  mov     rsi, [r11+48h]
0x1800606f8  mov     rsp, r11
0x1800606fb  pop     r15
0x1800606fd  pop     r14
0x1800606ff  pop     r13
0x180060701  pop     r12
0x180060703  pop     rdi
0x180060704  retn
0x180060705  xor     eax, eax
0x180060707  jmp     loc_1800605E4
0x18006070c  xor     eax, eax
0x18006070e  jmp     loc_1800605FF
0x180060713  xor     eax, eax
0x180060715  jmp     loc_180060633
0x18006071a  xor     eax, eax
0x18006071c  jmp     loc_18006064A
0x180060721  xor     r8d, r8d
0x180060724  jmp     loc_1800605C8
0x180060729  mov     r15, [r14]
0x18006072c  mov     rdx, r15
0x18006072f  sub     rdx, rbx; DestinationSize
0x180060732  cmp     rdx, rsi
0x180060735  jnb     short loc_180060796
0x180060737  lea     rdi, [rbx+rsi]
0x18006073b  test    rdx, rdx
0x18006073e  jz      short loc_180060750
0x180060740  mov     r9, rdx; SourceSize
0x180060743  mov     r8, rbx; Source
0x180060746  mov     rcx, rdi; Destination
0x180060749  call    cs:__imp_memmove_s
0x18006074f  nop
0x180060750  sub     rdi, [r14]
0x180060753  jz      short loc_180060764
0x180060755  mov     r8, rdi; Size
0x180060758  mov     dl, r12b; Val
0x18006075b  mov     rcx, [r14]; void *
0x18006075e  call    memset_0
0x180060763  nop
0x180060764  mov     rcx, [r14]
0x180060767  lea     rax, [rcx+rsi]
0x18006076b  mov     [r14], rax
0x18006076e  mov     r8, rcx
0x180060771  sub     r8, rbx
0x180060774  xor     eax, eax
0x180060776  cmp     rbx, rcx
0x180060779  cmova   r8, rax; Size
0x18006077d  test    r8, r8
0x180060780  jz      loc_1800606EB
0x180060786  mov     dl, r12b; Val
0x180060789  mov     rcx, rbx; void *
0x18006078c  call    memset_0
0x180060791  jmp     loc_1800606EB
0x180060796  mov     rdi, r15
0x180060799  sub     rdi, rsi
0x18006079c  mov     r9, rsi; SourceSize
0x18006079f  mov     r8, rdi; Source
0x1800607a2  mov     rdx, rsi; DestinationSize
0x1800607a5  mov     rcx, r15; Destination
0x1800607a8  call    cs:__imp_memmove_s
0x1800607ae  lea     rax, [r15+rsi]
0x1800607b2  mov     [r14], rax
0x1800607b5  mov     r8, r15
0x1800607b8  mov     rdx, rdi
0x1800607bb  mov     rcx, rbx; Source
0x1800607be  call    ??$copy_backward@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::copy_backward<uchar *,uchar *>(uchar *,uchar *,uchar *)
0x1800607c3  lea     rdx, [rbx+rsi]
0x1800607c7  lea     r8, [rsp+68h+arg_10]
0x1800607cf  mov     rcx, rbx
0x1800607d2  call    ??$fill@PEAEE@std@@YAXPEAE0AEBE@Z; std::fill<uchar *,uchar>(uchar *,uchar *,uchar const &)
0x1800607d7  jmp     loc_1800606EB
0x1800607dc  xor     edi, edi
0x1800607de  jmp     loc_180060624
0x1800607e3  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x1800607e9  xor     ecx, ecx
0x1800607eb  jmp     loc_18006066D
0x1800607f0  mov     [rsp+68h+Val], 0
0x1800607f9  lea     rdx, [rsp+68h+Val]
0x1800607fe  lea     rcx, [rsp+68h+pExceptionObject]
0x180060803  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180060809  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180060810  mov     [rsp+68h+pExceptionObject], rax
0x180060815  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18006081c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180060821  call    _CxxThrowException_0
```
