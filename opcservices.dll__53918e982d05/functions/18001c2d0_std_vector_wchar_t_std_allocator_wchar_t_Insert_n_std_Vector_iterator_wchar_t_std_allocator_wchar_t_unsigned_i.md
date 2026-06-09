# std::vector<wchar_t,std::allocator<wchar_t>>::_Insert_n(std::_Vector_iterator<wchar_t,std::allocator<wchar_t>>,unsigned __int64,wchar_t const &)

- ea: `0x18001c2d0`
- end: `0x18001c5f1`
- name: `?_Insert_n@?$vector@_WV?$allocator@_W@std@@@std@@IEAAXV?$_Vector_iterator@_WV?$allocator@_W@std@@@2@_KAEB_W@Z`
- size: `801`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001b99c`
- `0x1800786a4`

## callees

- `0x18000171c`
- `0x18001c2d0`
- `0x1800cd178`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800df79c`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001c4ef`
- `msvcrt!memmove_s` at `0x18001c514`
- `msvcrt!memmove_s` at `0x18001c576`
- `msvcrt!memmove_s` at `0x18001c595`
- `msvcrt!memmove_s` at `0x18001c5cc`
- `msvcrt!memmove_s` at `0x18001c4ef`
- `msvcrt!memmove_s` at `0x18001c514`
- `msvcrt!memmove_s` at `0x18001c576`
- `msvcrt!memmove_s` at `0x18001c595`
- `msvcrt!memmove_s` at `0x18001c5cc`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001c54c`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001c54c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<wchar_t>::_Insert_n(__int64 a1, _BYTE *a2, unsigned __int64 a3, __int16 *a4)
{
  char *result; // rax
  __int16 v8; // r10
  __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // r8
  void **v12; // r13
  __int64 v13; // r9
  __int64 v14; // rax
  unsigned __int64 v15; // r12
  __int64 v16; // rax
  __int64 v17; // rax
  char *v18; // rax
  char *v19; // r15
  _BYTE *v20; // r8
  __int64 v21; // rcx
  char *v22; // rdi
  unsigned __int64 v23; // rcx
  __int16 v24; // ax
  __int64 v25; // rdx
  _BYTE *v26; // rcx
  _WORD *v27; // rdi
  unsigned __int64 v28; // rsi
  char *v29; // rdx
  rsize_t v30; // rdx
  char *v31; // rsi
  __int64 v32; // rdi
  char *v33; // r14
  __int64 v34; // r15
  unsigned __int64 v35; // rdx
  unsigned __int64 i; // rcx
  _QWORD pExceptionObject[10]; // [rsp+28h] [rbp-50h] BYREF
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h] BYREF
  const char *v39; // [rsp+80h] [rbp+8h] BYREF
  char *v40; // [rsp+90h] [rbp+18h] BYREF
  void *v41; // [rsp+98h] [rbp+20h]

  result = (char *)&retaddr;
  v8 = *a4;
  LOWORD(v39) = v8;
  LOWORD(v40) = v8;
  v9 = *(_QWORD *)(a1 + 8);
  if ( v9 )
  {
    v11 = (*(_QWORD *)(a1 + 24) - v9) >> 1;
    v10 = 0;
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  if ( a3 )
  {
    v12 = (void **)(a1 + 16);
    if ( v9 )
      v13 = ((__int64)*v12 - v9) >> 1;
    else
      v13 = 0;
    if ( 0x7FFFFFFFFFFFFFFFLL - v13 < a3 )
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(v9);
    if ( v9 )
      v14 = ((__int64)*v12 - v9) >> 1;
    else
      v14 = 0;
    if ( v11 >= a3 + v14 )
    {
      v33 = (char *)*v12;
      v34 = 2 * a3;
      v35 = ((_BYTE *)*v12 - a2) >> 1;
      if ( v35 >= a3 )
      {
        v30 = 2 * (v34 >> 1);
        v31 = &v33[v30];
        if ( v34 >> 1 )
          memmove_s(*v12, v30, &v33[-v34], 2 * (v34 >> 1));
        *v12 = v31;
        v32 = (&v33[-v34] - a2) >> 1;
        if ( v32 > 0 )
          memmove_s(&v33[-2 * v32], 2 * v32, a2, 2 * v32);
        v29 = &a2[v34];
      }
      else
      {
        if ( v35 )
        {
          memmove_s(&a2[v34], 2 * v35, a2, 2 * v35);
          v8 = (__int16)v39;
        }
        v27 = *v12;
        v28 = a3 - (((_BYTE *)*v12 - a2) >> 1);
        if ( v28 )
        {
          for ( i = v28; i; --i )
            *v27++ = v8;
        }
        v29 = (char *)*v12;
        *v12 = (char *)*v12 + v34;
      }
      return (char *)std::fill<wchar_t *,wchar_t>(a2, v29, &v40);
    }
    else
    {
      v15 = 0;
      if ( 0x7FFFFFFFFFFFFFFFLL - (v11 >> 1) >= v11 )
        v15 = (v11 >> 1) + v11;
      if ( v9 )
        v16 = ((__int64)*v12 - v9) >> 1;
      else
        v16 = 0;
      if ( v15 < a3 + v16 )
      {
        if ( v9 )
          v17 = ((__int64)*v12 - v9) >> 1;
        else
          v17 = 0;
        v15 = v17 + a3;
      }
      if ( v15 )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
        {
          v39 = 0;
          exception::exception((exception *)pExceptionObject, &v39);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v10 = v15;
      }
      v18 = (char *)operator new(2 * v10);
      v19 = v18;
      v41 = v18;
      v20 = *(_BYTE **)(a1 + 8);
      v21 = (a2 - v20) >> 1;
      v22 = &v18[2 * v21];
      v40 = v22;
      if ( v21 )
      {
        try
        {
          memmove_s(v18, 2 * v21, v20, 2 * v21);
        }
        catch ( ... )
        {
          operator delete(v41);
          throw;
        }
      }
      v23 = (2 * a3) >> 1;
      v24 = (__int16)v39;
      while ( v23 )
      {
        *(_WORD *)v22 = v24;
        v22 += 2;
        --v23;
      }
      v25 = ((_BYTE *)*v12 - a2) >> 1;
      if ( v25 )
        memmove_s(&v40[2 * a3], 2 * v25, a2, 2 * v25);
      v26 = *(_BYTE **)(a1 + 8);
      if ( v26 )
      {
        a3 += ((_BYTE *)*v12 - v26) >> 1;
        operator delete(v26);
      }
      *(_QWORD *)(a1 + 24) = &v19[2 * v15];
      result = &v19[2 * a3];
      *v12 = result;
      *(_QWORD *)(a1 + 8) = v19;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001c2d0  mov     rax, rsp
0x18001c2d3  push    rbx
0x18001c2d4  push    rsi
0x18001c2d5  push    rdi
0x18001c2d6  push    r12
0x18001c2d8  push    r13
0x18001c2da  push    r14
0x18001c2dc  push    r15
0x18001c2de  sub     rsp, 40h
0x18001c2e2  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x18001c2ea  mov     rsi, r8
0x18001c2ed  mov     rbx, rdx
0x18001c2f0  mov     r14, rcx
0x18001c2f3  movzx   r10d, word ptr [r9]
0x18001c2f7  mov     [rax+8], r10w
0x18001c2fc  mov     [rax+18h], r10w
0x18001c301  mov     rcx, [rcx+8]
0x18001c305  test    rcx, rcx
0x18001c308  jnz     loc_18001C520
0x18001c30e  xor     edi, edi
0x18001c310  mov     r8d, edi
0x18001c313  test    rsi, rsi
0x18001c316  jz      loc_18001C42D
0x18001c31c  lea     r13, [r14+10h]
0x18001c320  test    rcx, rcx
0x18001c323  jnz     loc_18001C43D
0x18001c329  mov     r9, rdi
0x18001c32c  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18001c336  mov     rax, rdx
0x18001c339  sub     rax, r9
0x18001c33c  cmp     rax, rsi
0x18001c33f  jb      loc_18001C531
0x18001c345  test    rcx, rcx
0x18001c348  jnz     loc_18001C44C
0x18001c34e  mov     rax, rdi
0x18001c351  add     rax, rsi
0x18001c354  cmp     r8, rax
0x18001c357  jnb     loc_18001C5A0
0x18001c35d  mov     rax, r8
0x18001c360  shr     rax, 1
0x18001c363  sub     rdx, rax
0x18001c366  cmp     rdx, r8
0x18001c369  mov     r12, rdi
0x18001c36c  jb      short loc_18001C372
0x18001c36e  lea     r12, [rax+r8]
0x18001c372  test    rcx, rcx
0x18001c375  jnz     loc_18001C45B
0x18001c37b  mov     rax, rdi
0x18001c37e  add     rax, rsi
0x18001c381  cmp     r12, rax
0x18001c384  jnb     short loc_18001C396
0x18001c386  test    rcx, rcx
0x18001c389  jnz     loc_18001C47E
0x18001c38f  mov     rax, rdi
0x18001c392  lea     r12, [rax+rsi]
0x18001c396  test    r12, r12
0x18001c399  jz      short loc_18001C3B4
0x18001c39b  xor     edx, edx
0x18001c39d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001c3a4  div     r12
0x18001c3a7  cmp     rax, 2
0x18001c3ab  jb      loc_18001C537
0x18001c3b1  mov     rdi, r12
0x18001c3b4  lea     rcx, [rdi+rdi]; Size
0x18001c3b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c3bd  mov     r15, rax
0x18001c3c0  mov     [rsp+78h+arg_18], rax
0x18001c3c8  mov     r8, [r14+8]; Source
0x18001c3cc  mov     rcx, rbx
0x18001c3cf  sub     rcx, r8
0x18001c3d2  sar     rcx, 1
0x18001c3d5  lea     rdx, [rcx+rcx]; DestinationSize
0x18001c3d9  lea     rdi, [rdx+rax]
0x18001c3dd  mov     [rsp+78h+arg_10], rdi
0x18001c3e5  jnz     loc_18001C570
0x18001c3eb  lea     r8, [rsi+rsi]
0x18001c3ef  mov     rcx, r8
0x18001c3f2  shr     rcx, 1
0x18001c3f5  movzx   eax, word ptr [rsp+78h+arg_0]
0x18001c3fd  rep stosw
0x18001c400  mov     rdx, [r13+0]
0x18001c404  sub     rdx, rbx
0x18001c407  sar     rdx, 1
0x18001c40a  jnz     loc_18001C581
0x18001c410  mov     rcx, [r14+8]; Block
0x18001c414  test    rcx, rcx
0x18001c417  jnz     short loc_18001C46A
0x18001c419  lea     rax, [r15+r12*2]
0x18001c41d  mov     [r14+18h], rax
0x18001c421  lea     rax, [r15+rsi*2]
0x18001c425  mov     [r13+0], rax
0x18001c429  mov     [r14+8], r15
0x18001c42d  add     rsp, 40h
0x18001c431  pop     r15
0x18001c433  pop     r14
0x18001c435  pop     r13
0x18001c437  pop     r12
0x18001c439  pop     rdi
0x18001c43a  pop     rsi
0x18001c43b  pop     rbx
0x18001c43c  retn
0x18001c43d  mov     r9, [r13+0]
0x18001c441  sub     r9, rcx
0x18001c444  sar     r9, 1
0x18001c447  jmp     loc_18001C32C
0x18001c44c  mov     rax, [r13+0]
0x18001c450  sub     rax, rcx
0x18001c453  sar     rax, 1
0x18001c456  jmp     loc_18001C351
0x18001c45b  mov     rax, [r13+0]
0x18001c45f  sub     rax, rcx
0x18001c462  sar     rax, 1
0x18001c465  jmp     loc_18001C37E
0x18001c46a  mov     rax, [r13+0]
0x18001c46e  sub     rax, rcx
0x18001c471  sar     rax, 1
0x18001c474  add     rsi, rax
0x18001c477  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c47c  jmp     short loc_18001C419
0x18001c47e  mov     rax, [r13+0]
0x18001c482  sub     rax, rcx
0x18001c485  sar     rax, 1
0x18001c488  jmp     loc_18001C392
0x18001c48d  test    rdx, rdx
0x18001c490  jnz     loc_18001C5BF
0x18001c496  mov     rdi, [r13+0]
0x18001c49a  mov     rax, rdi
0x18001c49d  sub     rax, rbx
0x18001c4a0  sar     rax, 1
0x18001c4a3  sub     rsi, rax
0x18001c4a6  jnz     loc_18001C5E0
0x18001c4ac  mov     rdx, [r13+0]
0x18001c4b0  lea     rax, [r15+rdx]
0x18001c4b4  mov     [r13+0], rax
0x18001c4b8  lea     r8, [rsp+78h+arg_10]
0x18001c4c0  mov     rcx, rbx
0x18001c4c3  call    ??$fill@PEA_W_W@std@@YAXPEA_W0AEB_W@Z; std::fill<wchar_t *,wchar_t>(wchar_t *,wchar_t *,wchar_t const &)
0x18001c4c8  jmp     loc_18001C42D
0x18001c4cd  mov     rax, r15
0x18001c4d0  sar     rax, 1
0x18001c4d3  lea     rdx, [rax+rax]; DestinationSize
0x18001c4d7  lea     rsi, [rdx+r14]
0x18001c4db  mov     rdi, r14
0x18001c4de  sub     rdi, r15
0x18001c4e1  test    rax, rax
0x18001c4e4  jz      short loc_18001C4F5
0x18001c4e6  mov     r9, rdx; SourceSize
0x18001c4e9  mov     r8, rdi; Source
0x18001c4ec  mov     rcx, r14; Destination
0x18001c4ef  call    cs:__imp_memmove_s
0x18001c4f5  mov     [r13+0], rsi
0x18001c4f9  sub     rdi, rbx
0x18001c4fc  sar     rdi, 1
0x18001c4ff  test    rdi, rdi
0x18001c502  jle     short loc_18001C51A
0x18001c504  lea     rdx, [rdi+rdi]; DestinationSize
0x18001c508  sub     r14, rdx
0x18001c50b  mov     r9, rdx; SourceSize
0x18001c50e  mov     r8, rbx; Source
0x18001c511  mov     rcx, r14; Destination
0x18001c514  call    cs:__imp_memmove_s
0x18001c51a  lea     rdx, [r15+rbx]
0x18001c51e  jmp     short loc_18001C4B8
0x18001c520  mov     r8, [r14+18h]
0x18001c524  sub     r8, rcx
0x18001c527  sar     r8, 1
0x18001c52a  xor     edi, edi
0x18001c52c  jmp     loc_18001C313
0x18001c531  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x18001c537  mov     [rsp+78h+arg_0], rdi
0x18001c53f  lea     rdx, [rsp+78h+arg_0]
0x18001c547  lea     rcx, [rsp+78h+pExceptionObject]
0x18001c54c  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001c552  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001c559  mov     [rsp+78h+pExceptionObject], rax
0x18001c55e  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001c565  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001c56a  call    _CxxThrowException_0
0x18001c570  mov     r9, rdx; SourceSize
0x18001c573  mov     rcx, r15; Destination
0x18001c576  call    cs:__imp_memmove_s
0x18001c57c  jmp     loc_18001C3EB
0x18001c581  add     rdx, rdx; DestinationSize
0x18001c584  mov     rcx, [rsp+78h+arg_10]
0x18001c58c  add     rcx, r8; Destination
0x18001c58f  mov     r9, rdx; SourceSize
0x18001c592  mov     r8, rbx; Source
0x18001c595  call    cs:__imp_memmove_s
0x18001c59b  jmp     loc_18001C410
0x18001c5a0  mov     r14, [r13+0]
0x18001c5a4  lea     r15, [rsi+rsi]
0x18001c5a8  mov     rdx, r14
0x18001c5ab  sub     rdx, rbx
0x18001c5ae  sar     rdx, 1
0x18001c5b1  cmp     rdx, rsi
0x18001c5b4  jnb     loc_18001C4CD
0x18001c5ba  jmp     loc_18001C48D
0x18001c5bf  add     rdx, rdx; DestinationSize
0x18001c5c2  lea     rcx, [r15+rbx]; Destination
0x18001c5c6  mov     r9, rdx; SourceSize
0x18001c5c9  mov     r8, rbx; Source
0x18001c5cc  call    cs:__imp_memmove_s
0x18001c5d2  movzx   r10d, word ptr [rsp+78h+arg_0]
0x18001c5db  jmp     loc_18001C496
0x18001c5e0  movzx   eax, r10w
0x18001c5e4  mov     rcx, rsi
0x18001c5e7  rep stosw
0x18001c5ea  jmp     loc_18001C4AC
```
