# std::vector<uchar,std::allocator<uchar>>::_Insert<std::_Vector_iterator<uchar,std::allocator<uchar>>>(std::_Vector_iterator<uchar,std::allocator<uchar>>,std::_Vector_iterator<uchar,std::allocator<uchar>>,std::_Vector_iterator<uchar,std::allocator<uchar>>,std::forward_iterator_tag)

- ea: `0x18007a3c8`
- end: `0x18007a66e`
- name: `??$_Insert@V?$_Vector_iterator@EV?$allocator@E@std@@@std@@@?$vector@EV?$allocator@E@std@@@std@@QEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@1@00Uforward_iterator_tag@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, _BYTE *, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18007a38c`

## callees

- `0x18000171c`
- `0x18007a3c8`
- `0x18007a674`
- `0x1800b3d2c`
- `0x1800cd178`
- `0x1800cd1c4`
- `0x1800cd6fc`

## import_xrefs

- `msvcrt!memmove_s` at `0x18007a4de`
- `msvcrt!memmove_s` at `0x18007a50c`
- `msvcrt!memmove_s` at `0x18007a599`
- `msvcrt!memmove_s` at `0x18007a64e`
- `msvcrt!memmove_s` at `0x18007a4de`
- `msvcrt!memmove_s` at `0x18007a50c`
- `msvcrt!memmove_s` at `0x18007a599`
- `msvcrt!memmove_s` at `0x18007a64e`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18007a606`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18007a606`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<unsigned char>::_Insert<std::_Vector_iterator<unsigned char>>(
        __int64 a1,
        _BYTE *a2,
        _BYTE *a3,
        _BYTE *a4)
{
  _BYTE *v5; // rbx
  rsize_t v7; // r12
  __int64 v8; // rdx
  unsigned __int64 v9; // r8
  void **v10; // r15
  unsigned __int64 v11; // rax
  char *v12; // rax
  size_t v13; // rdi
  char *v14; // rax
  size_t v15; // rcx
  char *v16; // r13
  _BYTE *v17; // r8
  __int64 v18; // rax
  void *v19; // rax
  const char *v20; // rsi
  _BYTE *v21; // rcx
  signed __int64 v22; // rbx
  char *v23; // rax
  _BYTE *v24; // rdi
  char *v25; // r13
  rsize_t v26; // rdx
  _QWORD pExceptionObject[10]; // [rsp+38h] [rbp-50h] BYREF
  const char *v28; // [rsp+90h] [rbp+8h] BYREF
  __int64 v29; // [rsp+A0h] [rbp+18h]
  void *v30; // [rsp+A8h] [rbp+20h]

  v28 = (const char *)a1;
  v5 = a3;
  v7 = a4 - a3;
  v8 = *(_QWORD *)(a1 + 8);
  if ( v8 )
    v9 = *(_QWORD *)(a1 + 24) - v8;
  else
    v9 = 0;
  if ( v7 )
  {
    v10 = (void **)(a1 + 16);
    if ( v8 )
      v11 = (unsigned __int64)*v10 - v8;
    else
      v11 = 0;
    if ( ~v11 < v7 )
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(a1);
    if ( v8 )
      v12 = (char *)*v10 - v8;
    else
      v12 = 0;
    if ( v9 >= (unsigned __int64)&v12[v7] )
    {
      v25 = (char *)*v10;
      v26 = (_BYTE *)*v10 - a2;
      if ( v26 < v7 )
      {
        if ( v26 )
          memmove_s(&a2[v7], v26, a2, (_BYTE *)*v10 - a2);
        try
        {
          v24 = &v5[(_BYTE *)*v10 - a2];
          std::_Uninit_copy<std::_Vector_iterator<unsigned char>,unsigned char *,std::allocator<unsigned char>>(
            v24,
            a4,
            *v10);
          *v10 = (char *)*v10 + v7;
          while ( v5 != v24 )
            *a2++ = *v5++;
        }
        catch ( ... )
        {
          throw;
        }
      }
      else
      {
        memmove_s(*v10, v7, &v25[-v7], v7);
        *v10 = &v25[v7];
        std::copy_backward<unsigned char *,unsigned char *>(a2);
        while ( v5 != a4 )
          *a2++ = *v5++;
      }
    }
    else
    {
      if ( ~(v9 >> 1) >= v9 )
        v13 = (v9 >> 1) + v9;
      else
        v13 = 0;
      if ( v8 )
        v14 = (char *)*v10 - v8;
      else
        v14 = 0;
      if ( v13 < (unsigned __int64)&v14[v7] )
      {
        if ( v8 )
          v23 = (char *)*v10 - v8;
        else
          v23 = 0;
        v13 = (size_t)&v23[v7];
      }
      if ( v13 )
      {
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v13) )
        {
          v28 = 0;
          exception::exception((exception *)pExceptionObject, &v28);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v15 = v13;
      }
      else
      {
        v15 = 0;
      }
      v16 = (char *)operator new(v15);
      v30 = v16;
      v17 = (_BYTE *)*((_QWORD *)v28 + 1);
      v18 = a2 - v17;
      v29 = a2 - v17;
      if ( a2 != v17 )
      {
        memmove_s(v16, a2 - v17, v17, a2 - v17);
        v18 = v29;
      }
      try
      {
        v19 = (void *)std::_Uninit_copy<std::_Vector_iterator<unsigned char>,unsigned char *,std::allocator<unsigned char>>(
                        v5,
                        a4,
                        &v16[v18]);
        if ( *v10 != a2 )
          memmove_s(v19, (_BYTE *)*v10 - a2, a2, (_BYTE *)*v10 - a2);
      }
      catch ( ... )
      {
        operator delete(v30);
        throw;
      }
      v20 = v28;
      v21 = (_BYTE *)*((_QWORD *)v28 + 1);
      if ( v21 )
      {
        v22 = (_BYTE *)*v10 - v21;
        operator delete(v21);
      }
      else
      {
        v22 = 0;
      }
      *((_QWORD *)v20 + 3) = &v16[v13];
      *v10 = &v16[v7 + v22];
      *((_QWORD *)v20 + 1) = v16;
    }
  }
}

```

## disassembly

```asm
0x18007a3c8  mov     [rsp+arg_0], rcx
0x18007a3cd  push    rbx
0x18007a3ce  push    rsi
0x18007a3cf  push    rdi
0x18007a3d0  push    r12
0x18007a3d2  push    r13
0x18007a3d4  push    r14
0x18007a3d6  push    r15
0x18007a3d8  sub     rsp, 50h
0x18007a3dc  mov     [rsp+88h+var_58], 0FFFFFFFFFFFFFFFEh
0x18007a3e5  mov     rsi, r9
0x18007a3e8  mov     rbx, r8
0x18007a3eb  mov     r14, rdx
0x18007a3ee  mov     r12, r9
0x18007a3f1  sub     r12, r8
0x18007a3f4  mov     rdx, [rcx+8]
0x18007a3f8  test    rdx, rdx
0x18007a3fb  jz      short loc_18007A419
0x18007a3fd  mov     r8, [rcx+18h]
0x18007a401  sub     r8, rdx
0x18007a404  test    r12, r12
0x18007a407  jnz     short loc_18007A41E
0x18007a409  add     rsp, 50h
0x18007a40d  pop     r15
0x18007a40f  pop     r14
0x18007a411  pop     r13
0x18007a413  pop     r12
0x18007a415  pop     rdi
0x18007a416  pop     rsi
0x18007a417  pop     rbx
0x18007a418  retn
0x18007a419  xor     r8d, r8d
0x18007a41c  jmp     short loc_18007A404
0x18007a41e  lea     r15, [rcx+10h]
0x18007a422  test    rdx, rdx
0x18007a425  jz      loc_18007A553
0x18007a42b  mov     rax, [r15]
0x18007a42e  sub     rax, rdx
0x18007a431  not     rax
0x18007a434  cmp     rax, r12
0x18007a437  jb      loc_18007A56C
0x18007a43d  test    rdx, rdx
0x18007a440  jz      loc_18007A55A
0x18007a446  mov     rax, [r15]
0x18007a449  sub     rax, rdx
0x18007a44c  add     rax, r12
0x18007a44f  cmp     r8, rax
0x18007a452  jnb     loc_18007A62A
0x18007a458  mov     rcx, r8
0x18007a45b  shr     rcx, 1
0x18007a45e  mov     rax, rcx
0x18007a461  not     rax
0x18007a464  cmp     rax, r8
0x18007a467  jnb     loc_18007A54A
0x18007a46d  xor     edi, edi
0x18007a46f  test    rdx, rdx
0x18007a472  jz      loc_18007A561
0x18007a478  mov     rax, [r15]
0x18007a47b  sub     rax, rdx
0x18007a47e  add     rax, r12
0x18007a481  cmp     rdi, rax
0x18007a484  jb      loc_18007A572
0x18007a48a  test    rdi, rdi
0x18007a48d  jz      loc_18007A5E6
0x18007a493  xor     edx, edx
0x18007a495  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007a499  div     rdi
0x18007a49c  cmp     rax, 1
0x18007a4a0  jb      loc_18007A5ED
0x18007a4a6  mov     rcx, rdi; Size
0x18007a4a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007a4ae  mov     r13, rax
0x18007a4b1  mov     [rsp+88h+arg_18], rax
0x18007a4b9  mov     rax, [rsp+88h+arg_0]
0x18007a4c1  mov     r8, [rax+8]; Source
0x18007a4c5  mov     rax, r14
0x18007a4c8  sub     rax, r8
0x18007a4cb  mov     [rsp+88h+arg_10], rax
0x18007a4d3  jz      short loc_18007A4EC
0x18007a4d5  mov     r9, rax; SourceSize
0x18007a4d8  mov     rdx, rax; DestinationSize
0x18007a4db  mov     rcx, r13; Destination
0x18007a4de  call    cs:__imp_memmove_s
0x18007a4e4  mov     rax, [rsp+88h+arg_10]
0x18007a4ec  lea     r8, [rax+r13]
0x18007a4f0  mov     rdx, rsi
0x18007a4f3  mov     rcx, rbx
0x18007a4f6  call    ??$_Uninit_copy@V?$_Vector_iterator@EV?$allocator@E@std@@@std@@PEAEV?$allocator@E@2@@std@@YAPEAEV?$_Vector_iterator@EV?$allocator@E@std@@@0@0PEAEAEAV?$allocator@E@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<std::_Vector_iterator<uchar>,uchar *,std::allocator<uchar>>(std::_Vector_iterator<uchar>,std::_Vector_iterator<uchar>,uchar *,std::allocator<uchar> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x18007a4fb  mov     rdx, [r15]
0x18007a4fe  sub     rdx, r14; DestinationSize
0x18007a501  jz      short loc_18007A513
0x18007a503  mov     r9, rdx; SourceSize
0x18007a506  mov     r8, r14; Source
0x18007a509  mov     rcx, rax; Destination
0x18007a50c  call    cs:__imp_memmove_s
0x18007a512  nop
0x18007a513  mov     rsi, [rsp+88h+arg_0]
0x18007a51b  mov     rcx, [rsi+8]; Block
0x18007a51f  test    rcx, rcx
0x18007a522  jz      short loc_18007A568
0x18007a524  mov     rbx, [r15]
0x18007a527  sub     rbx, rcx
0x18007a52a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007a52f  lea     rax, [rdi+r13]
0x18007a533  mov     [rsi+18h], rax
0x18007a537  lea     rax, [r12+rbx]
0x18007a53b  add     rax, r13
0x18007a53e  mov     [r15], rax
0x18007a541  mov     [rsi+8], r13
0x18007a545  jmp     loc_18007A409
0x18007a54a  lea     rdi, [rcx+r8]
0x18007a54e  jmp     loc_18007A46F
0x18007a553  xor     eax, eax
0x18007a555  jmp     loc_18007A431
0x18007a55a  xor     eax, eax
0x18007a55c  jmp     loc_18007A44C
0x18007a561  xor     eax, eax
0x18007a563  jmp     loc_18007A47E
0x18007a568  xor     ebx, ebx
0x18007a56a  jmp     short loc_18007A52F
0x18007a56c  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x18007a572  test    rdx, rdx
0x18007a575  jnz     short loc_18007A582
0x18007a577  xor     eax, eax
0x18007a579  lea     rdi, [r12+rax]
0x18007a57d  jmp     loc_18007A48A
0x18007a582  mov     rax, [r15]
0x18007a585  sub     rax, rdx
0x18007a588  jmp     short loc_18007A579
0x18007a58a  test    rdx, rdx
0x18007a58d  jz      short loc_18007A59F
0x18007a58f  lea     rcx, [r12+r14]; Destination
0x18007a593  mov     r9, rdx; SourceSize
0x18007a596  mov     r8, r14; Source
0x18007a599  call    cs:__imp_memmove_s
0x18007a59f  mov     rdi, [r15]
0x18007a5a2  sub     rdi, r14
0x18007a5a5  add     rdi, rbx
0x18007a5a8  mov     r8, [r15]
0x18007a5ab  mov     rdx, rsi
0x18007a5ae  mov     rcx, rdi
0x18007a5b1  call    ??$_Uninit_copy@V?$_Vector_iterator@EV?$allocator@E@std@@@std@@PEAEV?$allocator@E@2@@std@@YAPEAEV?$_Vector_iterator@EV?$allocator@E@std@@@0@0PEAEAEAV?$allocator@E@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<std::_Vector_iterator<uchar>,uchar *,std::allocator<uchar>>(std::_Vector_iterator<uchar>,std::_Vector_iterator<uchar>,uchar *,std::allocator<uchar> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x18007a5b6  nop
0x18007a5b7  add     [r15], r12
0x18007a5ba  cmp     rbx, rdi
0x18007a5bd  jz      loc_18007A409
0x18007a5c3  mov     al, [rbx]
0x18007a5c5  mov     [r14], al
0x18007a5c8  inc     r14
0x18007a5cb  inc     rbx
0x18007a5ce  jmp     short loc_18007A5BA
0x18007a5d0  cmp     rbx, rsi
0x18007a5d3  jz      loc_18007A409
0x18007a5d9  mov     al, [rbx]
0x18007a5db  mov     [r14], al
0x18007a5de  inc     r14
0x18007a5e1  inc     rbx
0x18007a5e4  jmp     short loc_18007A5D0
0x18007a5e6  xor     ecx, ecx
0x18007a5e8  jmp     loc_18007A4A9
0x18007a5ed  mov     [rsp+88h+arg_0], 0
0x18007a5f9  lea     rdx, [rsp+88h+arg_0]
0x18007a601  lea     rcx, [rsp+88h+pExceptionObject]
0x18007a606  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18007a60c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18007a613  mov     [rsp+88h+pExceptionObject], rax
0x18007a618  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18007a61f  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18007a624  call    _CxxThrowException_0
0x18007a62a  mov     r13, [r15]
0x18007a62d  mov     rdx, r13
0x18007a630  sub     rdx, r14; DestinationSize
0x18007a633  cmp     rdx, r12
0x18007a636  jb      loc_18007A58A
0x18007a63c  mov     rdi, r13
0x18007a63f  sub     rdi, r12
0x18007a642  mov     r9, r12; SourceSize
0x18007a645  mov     r8, rdi; Source
0x18007a648  mov     rdx, r12; DestinationSize
0x18007a64b  mov     rcx, r13; Destination
0x18007a64e  call    cs:__imp_memmove_s
0x18007a654  lea     rax, [r12+r13]
0x18007a658  mov     [r15], rax
0x18007a65b  mov     r8, r13
0x18007a65e  mov     rdx, rdi
0x18007a661  mov     rcx, r14; Source
0x18007a664  call    ??$copy_backward@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::copy_backward<uchar *,uchar *>(uchar *,uchar *,uchar *)
0x18007a669  jmp     loc_18007A5D0
```
