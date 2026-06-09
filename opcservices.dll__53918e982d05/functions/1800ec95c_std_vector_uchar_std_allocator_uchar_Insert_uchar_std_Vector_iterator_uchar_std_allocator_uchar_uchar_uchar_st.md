# std::vector<uchar,std::allocator<uchar>>::_Insert<uchar *>(std::_Vector_iterator<uchar,std::allocator<uchar>>,uchar *,uchar *,std::forward_iterator_tag)

- ea: `0x1800ec95c`
- end: `0x1800ecbb5`
- name: `??$_Insert@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@1@PEAE1Uforward_iterator_tag@1@@Z`
- size: `601`
- prototype: `char *__fastcall(__int64, _BYTE *, char *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800c2d94`
- `0x1800ec904`

## callees

- `0x18000171c`
- `0x1800761c0`
- `0x1800b3d2c`
- `0x1800cd178`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800ec95c`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800ecaab`
- `msvcrt!memmove_s` at `0x1800ecac2`
- `msvcrt!memmove_s` at `0x1800ecada`
- `msvcrt!memmove_s` at `0x1800ecb31`
- `msvcrt!memmove_s` at `0x1800ecb51`
- `msvcrt!memmove_s` at `0x1800ecb6f`
- `msvcrt!memmove_s` at `0x1800ecaab`
- `msvcrt!memmove_s` at `0x1800ecac2`
- `msvcrt!memmove_s` at `0x1800ecada`
- `msvcrt!memmove_s` at `0x1800ecb31`
- `msvcrt!memmove_s` at `0x1800ecb51`
- `msvcrt!memmove_s` at `0x1800ecb6f`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800eca61`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800eca61`

## pseudocode

```c
char *__fastcall std::vector<unsigned char>::_Insert<unsigned char *>(__int64 a1, _BYTE *a2, char *a3, __int64 a4)
{
  char *result; // rax
  rsize_t v9; // rdi
  __int64 v10; // rdx
  unsigned __int64 v11; // r10
  void **v12; // rsi
  unsigned __int64 v13; // rax
  char *v14; // rax
  size_t v15; // r14
  char *v16; // rax
  char *v17; // rax
  size_t v18; // rcx
  char *v19; // rax
  char *v20; // r15
  _BYTE *v21; // r8
  char *v22; // r12
  _BYTE *v23; // rcx
  signed __int64 v24; // rbx
  char *v25; // r15
  rsize_t v26; // rdx
  rsize_t v27; // r14
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-40h] BYREF
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF
  void *v30; // [rsp+70h] [rbp+8h]
  void *Source; // [rsp+80h] [rbp+18h] BYREF

  result = (char *)&retaddr;
  Source = a3;
  v9 = a4 - (_QWORD)a3;
  v10 = *(_QWORD *)(a1 + 8);
  if ( v10 )
    v11 = *(_QWORD *)(a1 + 24) - v10;
  else
    v11 = 0;
  if ( v9 )
  {
    v12 = (void **)(a1 + 16);
    if ( v10 )
      v13 = (unsigned __int64)*v12 - v10;
    else
      v13 = 0;
    if ( ~v13 < v9 )
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(a1);
    if ( v10 )
      v14 = (char *)*v12 - v10;
    else
      v14 = 0;
    if ( v11 >= (unsigned __int64)&v14[v9] )
    {
      v25 = (char *)*v12;
      v26 = (_BYTE *)*v12 - a2;
      if ( v26 >= v9 )
      {
        memmove_s(*v12, v9, &v25[-v9], v9);
        *v12 = &v25[v9];
        std::copy_backward<unsigned char *,unsigned char *>(a2);
      }
      else
      {
        if ( v26 )
          memmove_s(&a2[v9], v26, a2, (_BYTE *)*v12 - a2);
        v27 = a4 - (_QWORD)&a3[(_BYTE *)*v12 - a2];
        if ( v27 )
          memmove_s(*v12, v27, &a3[(_BYTE *)*v12 - a2], v27);
        *v12 = (char *)*v12 + v9;
      }
      return (char *)std::copy<unsigned char const *,unsigned char *>(a3);
    }
    else
    {
      if ( ~(v11 >> 1) >= v11 )
        v15 = (v11 >> 1) + v11;
      else
        v15 = 0;
      if ( v10 )
        v16 = (char *)*v12 - v10;
      else
        v16 = 0;
      if ( v15 < (unsigned __int64)&v16[v9] )
      {
        if ( v10 )
          v17 = (char *)*v12 - v10;
        else
          v17 = 0;
        v15 = (size_t)&v17[v9];
      }
      if ( v15 )
      {
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v15) )
        {
          Source = 0;
          exception::exception((exception *)pExceptionObject, (const char *const *)&Source);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v18 = v15;
      }
      else
      {
        v18 = 0;
      }
      v19 = (char *)operator new(v18);
      v20 = v19;
      v30 = v19;
      try
      {
        v21 = *(_BYTE **)(a1 + 8);
        v22 = &v19[a2 - v21];
        if ( a2 != v21 )
          memmove_s(v19, a2 - v21, v21, a2 - v21);
        memmove_s(v22, v9, Source, v9);
        if ( *v12 != a2 )
          memmove_s(&v22[v9], (_BYTE *)*v12 - a2, a2, (_BYTE *)*v12 - a2);
        v23 = *(_BYTE **)(a1 + 8);
        if ( v23 )
        {
          v24 = (_BYTE *)*v12 - v23;
          operator delete(v23);
        }
        else
        {
          v24 = 0;
        }
        *(_QWORD *)(a1 + 24) = &v20[v15];
        result = &v20[v9 + v24];
        *v12 = result;
        *(_QWORD *)(a1 + 8) = v20;
      }
      catch ( ... )
      {
        operator delete(v30);
        throw;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ec95c  mov     rax, rsp
0x1800ec95f  mov     [rax+18h], r8
0x1800ec963  push    rdi
0x1800ec964  push    r12
0x1800ec966  push    r13
0x1800ec968  push    r14
0x1800ec96a  push    r15
0x1800ec96c  sub     rsp, 40h
0x1800ec970  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800ec978  mov     [rax+10h], rbx
0x1800ec97c  mov     [rax+20h], rsi
0x1800ec980  mov     r14, r9
0x1800ec983  mov     r12, r8
0x1800ec986  mov     rbx, rdx
0x1800ec989  mov     r13, rcx
0x1800ec98c  mov     rdi, r9
0x1800ec98f  sub     rdi, r8
0x1800ec992  mov     rdx, [rcx+8]
0x1800ec996  test    rdx, rdx
0x1800ec999  jnz     short loc_1800EC9A0
0x1800ec99b  xor     r10d, r10d
0x1800ec99e  jmp     short loc_1800EC9A7
0x1800ec9a0  mov     r10, [rcx+18h]
0x1800ec9a4  sub     r10, rdx
0x1800ec9a7  test    rdi, rdi
0x1800ec9aa  jz      loc_1800ECB9B
0x1800ec9b0  lea     rsi, [rcx+10h]
0x1800ec9b4  test    rdx, rdx
0x1800ec9b7  jnz     short loc_1800EC9BD
0x1800ec9b9  xor     eax, eax
0x1800ec9bb  jmp     short loc_1800EC9C3
0x1800ec9bd  mov     rax, [rsi]
0x1800ec9c0  sub     rax, rdx
0x1800ec9c3  not     rax
0x1800ec9c6  cmp     rax, rdi
0x1800ec9c9  jnb     short loc_1800EC9D1
0x1800ec9cb  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x1800ec9d1  test    rdx, rdx
0x1800ec9d4  jnz     short loc_1800EC9DA
0x1800ec9d6  xor     eax, eax
0x1800ec9d8  jmp     short loc_1800EC9E0
0x1800ec9da  mov     rax, [rsi]
0x1800ec9dd  sub     rax, rdx
0x1800ec9e0  add     rax, rdi
0x1800ec9e3  cmp     r10, rax
0x1800ec9e6  jnb     loc_1800ECB14
0x1800ec9ec  mov     rcx, r10
0x1800ec9ef  shr     rcx, 1
0x1800ec9f2  mov     rax, rcx
0x1800ec9f5  not     rax
0x1800ec9f8  cmp     rax, r10
0x1800ec9fb  jnb     short loc_1800ECA02
0x1800ec9fd  xor     r14d, r14d
0x1800eca00  jmp     short loc_1800ECA06
0x1800eca02  lea     r14, [rcx+r10]
0x1800eca06  test    rdx, rdx
0x1800eca09  jnz     short loc_1800ECA0F
0x1800eca0b  xor     eax, eax
0x1800eca0d  jmp     short loc_1800ECA15
0x1800eca0f  mov     rax, [rsi]
0x1800eca12  sub     rax, rdx
0x1800eca15  add     rax, rdi
0x1800eca18  cmp     r14, rax
0x1800eca1b  jnb     short loc_1800ECA30
0x1800eca1d  test    rdx, rdx
0x1800eca20  jnz     short loc_1800ECA26
0x1800eca22  xor     eax, eax
0x1800eca24  jmp     short loc_1800ECA2C
0x1800eca26  mov     rax, [rsi]
0x1800eca29  sub     rax, rdx
0x1800eca2c  lea     r14, [rdi+rax]
0x1800eca30  test    r14, r14
0x1800eca33  jnz     short loc_1800ECA39
0x1800eca35  xor     ecx, ecx
0x1800eca37  jmp     short loc_1800ECA88
0x1800eca39  xor     edx, edx
0x1800eca3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800eca3f  div     r14
0x1800eca42  cmp     rax, 1
0x1800eca46  jnb     short loc_1800ECA85
0x1800eca48  mov     [rsp+68h+Source], 0
0x1800eca54  lea     rdx, [rsp+68h+Source]
0x1800eca5c  lea     rcx, [rsp+68h+pExceptionObject]
0x1800eca61  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x1800eca67  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800eca6e  mov     [rsp+68h+pExceptionObject], rax
0x1800eca73  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800eca7a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800eca7f  call    _CxxThrowException_0
0x1800eca85  mov     rcx, r14; Size
0x1800eca88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eca8d  mov     r15, rax
0x1800eca90  mov     [rsp+68h+arg_0], rax
0x1800eca95  mov     r8, [r13+8]; Source
0x1800eca99  mov     rdx, rbx
0x1800eca9c  sub     rdx, r8; DestinationSize
0x1800eca9f  lea     r12, [rdx+rax]
0x1800ecaa3  jz      short loc_1800ECAB1
0x1800ecaa5  mov     r9, rdx; SourceSize
0x1800ecaa8  mov     rcx, rax; Destination
0x1800ecaab  call    cs:__imp_memmove_s
0x1800ecab1  mov     r9, rdi; SourceSize
0x1800ecab4  mov     r8, [rsp+68h+Source]; Source
0x1800ecabc  mov     rdx, rdi; DestinationSize
0x1800ecabf  mov     rcx, r12; Destination
0x1800ecac2  call    cs:__imp_memmove_s
0x1800ecac8  mov     rdx, [rsi]
0x1800ecacb  sub     rdx, rbx; DestinationSize
0x1800ecace  jz      short loc_1800ECAE1
0x1800ecad0  lea     rcx, [r12+rdi]; Destination
0x1800ecad4  mov     r9, rdx; SourceSize
0x1800ecad7  mov     r8, rbx; Source
0x1800ecada  call    cs:__imp_memmove_s
0x1800ecae0  nop
0x1800ecae1  mov     rcx, [r13+8]; Block
0x1800ecae5  test    rcx, rcx
0x1800ecae8  jnz     short loc_1800ECAEE
0x1800ecaea  xor     ebx, ebx
0x1800ecaec  jmp     short loc_1800ECAF9
0x1800ecaee  mov     rbx, [rsi]
0x1800ecaf1  sub     rbx, rcx
0x1800ecaf4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ecaf9  lea     rax, [r15+r14]
0x1800ecafd  mov     [r13+18h], rax
0x1800ecb01  lea     rax, [rdi+rbx]
0x1800ecb05  add     rax, r15
0x1800ecb08  mov     [rsi], rax
0x1800ecb0b  mov     [r13+8], r15
0x1800ecb0f  jmp     loc_1800ECB9B
0x1800ecb14  mov     r15, [rsi]
0x1800ecb17  mov     rdx, r15
0x1800ecb1a  sub     rdx, rbx; DestinationSize
0x1800ecb1d  cmp     rdx, rdi
0x1800ecb20  jnb     short loc_1800ECB60
0x1800ecb22  test    rdx, rdx
0x1800ecb25  jz      short loc_1800ECB37
0x1800ecb27  lea     rcx, [rdi+rbx]; Destination
0x1800ecb2b  mov     r9, rdx; SourceSize
0x1800ecb2e  mov     r8, rbx; Source
0x1800ecb31  call    cs:__imp_memmove_s
0x1800ecb37  mov     r15, [rsi]
0x1800ecb3a  sub     r15, rbx
0x1800ecb3d  add     r15, r12
0x1800ecb40  sub     r14, r15
0x1800ecb43  jz      short loc_1800ECB58
0x1800ecb45  mov     r9, r14; SourceSize
0x1800ecb48  mov     r8, r15; Source
0x1800ecb4b  mov     rdx, r14; DestinationSize
0x1800ecb4e  mov     rcx, [rsi]; Destination
0x1800ecb51  call    cs:__imp_memmove_s
0x1800ecb57  nop
0x1800ecb58  add     [rsi], rdi
0x1800ecb5b  mov     rdx, r15
0x1800ecb5e  jmp     short loc_1800ECB90
0x1800ecb60  mov     r8, r15
0x1800ecb63  sub     r8, rdi; Source
0x1800ecb66  mov     r9, rdi; SourceSize
0x1800ecb69  mov     rdx, rdi; DestinationSize
0x1800ecb6c  mov     rcx, r15; Destination
0x1800ecb6f  call    cs:__imp_memmove_s
0x1800ecb75  lea     rax, [rdi+r15]
0x1800ecb79  mov     [rsi], rax
0x1800ecb7c  mov     rdx, r15
0x1800ecb7f  sub     rdx, rdi
0x1800ecb82  mov     r8, r15
0x1800ecb85  mov     rcx, rbx; Source
0x1800ecb88  call    ??$copy_backward@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::copy_backward<uchar *,uchar *>(uchar *,uchar *,uchar *)
0x1800ecb8d  mov     rdx, r14
0x1800ecb90  mov     r8, rbx
0x1800ecb93  mov     rcx, r12; Source
0x1800ecb96  call    ??$copy@PEBEPEAE@std@@YAPEAEPEBE0PEAE@Z; std::copy<uchar const *,uchar *>(uchar const *,uchar const *,uchar *)
0x1800ecb9b  lea     r11, [rsp+68h+var_28]
0x1800ecba0  mov     rbx, [r11+38h]
0x1800ecba4  mov     rsi, [r11+48h]
0x1800ecba8  mov     rsp, r11
0x1800ecbab  pop     r15
0x1800ecbad  pop     r14
0x1800ecbaf  pop     r13
0x1800ecbb1  pop     r12
0x1800ecbb3  pop     rdi
0x1800ecbb4  retn
```
