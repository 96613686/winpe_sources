# LocalFileLoader::SerializeReferenceKeyTo(wchar_t const *,DateTime const *,wchar_t const *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180123484`
- end: `0x1801236d4`
- name: `?SerializeReferenceKeyTo@LocalFileLoader@@SAXPEB_WPEBVDateTime@@0AEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(LPCWCH lpString2)`
- caller_count: `7`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801222ec`
- `0x180122cd0`
- `0x180124280`
- `0x1801243d0`
- `0x1801246bc`
- `0x1801e7d50`
- `0x18022b830`

## callees

- `0x180123484`
- `0x1801236dc`
- `0x18012376c`
- `0x18012379c`
- `0x1801237dc`
- `0x1801644d0`
- `0x1801d8f6c`
- `0x1801f37b0`
- `0x180202db8`
- `0x180236f00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012364e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012364e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180123578`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180123578`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LocalFileLoader::SerializeReferenceKeyTo(
        LPCWCH lpString2,
        const struct DateTime *a2,
        __int64 a3,
        _QWORD *a4)
{
  const WCHAR *v6; // r12
  __int64 v7; // r15
  unsigned __int64 v8; // r14
  unsigned __int8 v9; // r13
  __int64 v10; // rdx
  struct DWrite::RefString::Data *v11; // rbx
  unsigned __int64 v12; // rsi
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rsi
  WCHAR *v16; // rsi
  WCHAR *v17; // rax
  const WCHAR *v18; // rcx
  bool v19; // zf
  unsigned __int64 v20; // [rsp+30h] [rbp-38h] BYREF
  struct DWrite::RefString::Data *v21; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-28h] BYREF
  __int64 v23; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int64 v24; // [rsp+50h] [rbp-18h] BYREF
  char v25[16]; // [rsp+58h] [rbp-10h] BYREF

  v6 = lpString2;
  v24 = GetFileLastWriteTimeTicks(lpString2, a2);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v6[v8] );
  if ( a3 )
  {
    do
      ++v7;
    while ( *(_WORD *)(a3 + 2 * v7) );
  }
  else
  {
    v7 = 0;
  }
  v9 = 0;
  GetFontsDirectory(&v21);
  v11 = v21;
  v12 = *((unsigned int *)v21 + 1);
  if ( v8 < v12 )
    goto LABEL_6;
  v18 = (const WCHAR *)((char *)v21 + 8);
  if ( v21 == (struct DWrite::RefString::Data *)-8LL )
  {
    v19 = v6 == 0;
LABEL_30:
    if ( v19 )
    {
      v6 += v12;
      v8 -= v12;
      v9 = 1;
    }
    goto LABEL_6;
  }
  if ( v6 )
  {
    if ( (unsigned int)v12 > 0x7FFFFFFF )
      SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v18, v10);
    v19 = CompareStringOrdinal(v18, v12, v6, v12, 1) == 2;
    goto LABEL_30;
  }
LABEL_6:
  if ( *a4 != a4[1] )
    a4[1] = *a4;
  v23 = 2;
  v22 = v8 + 1;
  v20 = 0;
  LargeIntRegMultiply<unsigned __int64,unsigned __int64>::RegMultiplyThrow<SafeIntExceptionHandler<Exception>>(
    &v23,
    &v22,
    &v20);
  v15 = v20 + 2 * (v9 + 4LL);
  if ( v15 < v20 )
    goto LABEL_36;
  if ( !v7 )
  {
    LODWORD(v14) = 0;
    goto LABEL_11;
  }
  v23 = 2;
  v14 = *(_QWORD *)SafeInt<unsigned __int64,SafeIntExceptionHandler<Exception>>::operator*<unsigned __int64>(
                     &v23,
                     v25,
                     v7 + 1);
  if ( v14 > 0xFFFFFFFF )
LABEL_36:
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v14, v13);
LABEL_11:
  v14 = v15 + (unsigned int)v14;
  if ( v14 < v15 )
    goto LABEL_36;
  v23 = v14;
  if ( v14 > a4[2] - *a4 )
  {
    if ( v14 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    std::vector<unsigned char>::_Reallocate<0>(a4, &v23);
  }
  std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(a4, a4[1], &v24, 8);
  if ( v9 )
    std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(a4, a4[1], byte_180374150, 2);
  v16 = (WCHAR *)a4[1];
  std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(a4, v16, v6, 2 * v8 + 2);
  ToUpperInvariant(v16, v8);
  v17 = &v16[v8];
  while ( v16 != v17 )
  {
    if ( *v16 == 47 )
      *v16 = 92;
    ++v16;
  }
  if ( v7 )
    std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(a4, a4[1], a3, 2 * v7 + 2);
  DWrite::RefString::DecrementRef(v11);
}

```

## disassembly

```asm
0x180123484  mov     [rsp-40h+arg_10], r8
0x180123489  push    rbp
0x18012348a  push    rbx
0x18012348b  push    rsi
0x18012348c  push    rdi
0x18012348d  push    r12
0x18012348f  push    r13
0x180123491  push    r14
0x180123493  push    r15
0x180123495  mov     rbp, rsp
0x180123498  sub     rsp, 68h
0x18012349c  mov     rdi, r9
0x18012349f  mov     rbx, r8
0x1801234a2  mov     r12, rcx
0x1801234a5  call    ?GetFileLastWriteTimeTicks@@YA_KPEB_WPEBVDateTime@@@Z; GetFileLastWriteTimeTicks(wchar_t const *,DateTime const *)
0x1801234aa  mov     [rbp+var_18], rax
0x1801234ae  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801234b2  mov     r14, r15
0x1801234b5  xor     eax, eax
0x1801234b7  inc     r14
0x1801234ba  cmp     [r12+r14*2], ax
0x1801234bf  jnz     short loc_1801234B7
0x1801234c1  test    rbx, rbx
0x1801234c4  jnz     loc_18012366C
0x1801234ca  mov     r15, rax
0x1801234cd  mov     r13b, al
0x1801234d0  lea     rcx, [rbp+var_30]
0x1801234d4  call    ?GetFontsDirectory@@YA?AVRefString@DWrite@@XZ; GetFontsDirectory(void)
0x1801234d9  nop
0x1801234da  mov     rbx, [rbp+var_30]
0x1801234de  mov     esi, [rbx+4]
0x1801234e1  cmp     r14, rsi
0x1801234e4  jnb     loc_180123620
0x1801234ea  mov     rax, [rdi]
0x1801234ed  cmp     rax, [rdi+8]
0x1801234f1  jz      short loc_1801234F7
0x1801234f3  mov     [rdi+8], rax
0x1801234f7  mov     [rbp+var_20], 2
0x1801234ff  lea     rax, [r14+1]
0x180123503  mov     [rbp+var_28], rax
0x180123507  mov     [rbp+var_38], 0
0x18012350f  lea     r8, [rbp+var_38]
0x180123513  lea     rdx, [rbp+var_28]
0x180123517  lea     rcx, [rbp+var_20]
0x18012351b  call    ??$RegMultiplyThrow@V?$SafeIntExceptionHandler@VException@@@@@?$LargeIntRegMultiply@_K_K@@SAXAEB_K0AEA_K@Z; LargeIntRegMultiply<unsigned __int64,unsigned __int64>::RegMultiplyThrow<SafeIntExceptionHandler<Exception>>(unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 &)
0x180123520  mov     rax, [rbp+var_38]
0x180123524  movzx   esi, r13b
0x180123528  add     rsi, 4
0x18012352c  lea     rsi, [rax+rsi*2]
0x180123530  cmp     rsi, rax
0x180123533  jb      loc_1801236AB
0x180123539  test    r15, r15
0x18012353c  jnz     loc_180123681
0x180123542  xor     ecx, ecx
0x180123544  mov     ecx, ecx
0x180123546  add     rcx, rsi
0x180123549  cmp     rcx, rsi
0x18012354c  jb      loc_1801236AB
0x180123552  mov     [rbp+var_20], rcx
0x180123556  mov     rax, [rdi+10h]
0x18012355a  sub     rax, [rdi]
0x18012355d  cmp     rcx, rax
0x180123560  jbe     short loc_18012358B
0x180123562  mov     rax, 7FFFFFFFFFFFFFFFh
0x18012356c  cmp     rcx, rax
0x18012356f  jbe     short loc_18012357F
0x180123571  lea     rcx, aVectorTooLong; "vector too long"
0x180123578  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18012357f  lea     rdx, [rbp+var_20]
0x180123583  mov     rcx, rdi
0x180123586  call    ??$_Reallocate@$0A@@?$vector@EV?$allocator@E@std@@@std@@AEAAXAEA_K@Z; std::vector<uchar>::_Reallocate<0>(unsigned __int64 &)
0x18012358b  mov     r9d, 8
0x180123591  lea     r8, [rbp+var_18]
0x180123595  mov     rdx, [rdi+8]
0x180123599  mov     rcx, rdi
0x18012359c  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x1801235a1  test    r13b, r13b
0x1801235a4  jz      short loc_1801235BF
0x1801235a6  mov     r9d, 2
0x1801235ac  lea     r8, byte_180374150
0x1801235b3  mov     rdx, [rdi+8]
0x1801235b7  mov     rcx, rdi
0x1801235ba  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x1801235bf  mov     rsi, [rdi+8]
0x1801235c3  lea     r9, ds:2[r14*2]
0x1801235cb  mov     r8, r12
0x1801235ce  mov     rdx, rsi
0x1801235d1  mov     rcx, rdi
0x1801235d4  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x1801235d9  mov     rdx, r14; cchDest
0x1801235dc  mov     rcx, rsi; lpDestStr
0x1801235df  call    ?ToUpperInvariant@@YAXPEA_W_K@Z; ToUpperInvariant(wchar_t *,unsigned __int64)
0x1801235e4  lea     rax, [rsi+r14*2]
0x1801235e8  cmp     rsi, rax
0x1801235eb  jz      short loc_1801235FE
0x1801235ed  cmp     word ptr [rsi], 2Fh ; '/'
0x1801235f1  jnz     short loc_1801235F8
0x1801235f3  mov     word ptr [rsi], 5Ch ; '\'
0x1801235f8  add     rsi, 2
0x1801235fc  jmp     short loc_1801235E8
0x1801235fe  test    r15, r15
0x180123601  jnz     loc_1801236B6
0x180123607  mov     rcx, rbx; struct DWrite::RefString::Data *
0x18012360a  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18012360f  add     rsp, 68h
0x180123613  pop     r15
0x180123615  pop     r14
0x180123617  pop     r13
0x180123619  pop     r12
0x18012361b  pop     rdi
0x18012361c  pop     rsi
0x18012361d  pop     rbx
0x18012361e  pop     rbp
0x18012361f  retn
0x180123620  lea     rcx, [rbx+8]; lpString1
0x180123624  test    rcx, rcx
0x180123627  jz      loc_1801236B1
0x18012362d  test    r12, r12
0x180123630  jz      loc_1801234EA
0x180123636  cmp     esi, 7FFFFFFFh
0x18012363c  ja      short loc_18012367B
0x18012363e  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180123646  mov     r9d, esi; cchCount2
0x180123649  mov     r8, r12; lpString2
0x18012364c  mov     edx, esi; cchCount1
0x18012364e  call    cs:__imp_CompareStringOrdinal
0x180123654  add     eax, 0FFFFFFFEh
0x180123657  jnz     loc_1801234EA
0x18012365d  lea     r12, [r12+rsi*2]
0x180123661  sub     r14, rsi
0x180123664  mov     r13b, 1
0x180123667  jmp     loc_1801234EA
0x18012366c  inc     r15
0x18012366f  cmp     [rbx+r15*2], ax
0x180123674  jnz     short loc_18012366C
0x180123676  jmp     loc_1801234CD
0x18012367b  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x180123681  mov     [rbp+var_20], 2
0x180123689  lea     r8, [r15+1]
0x18012368d  lea     rdx, [rbp+var_10]
0x180123691  lea     rcx, [rbp+var_20]
0x180123695  call    ??$?D_K@?$SafeInt@_KV?$SafeIntExceptionHandler@VException@@@@@@QEBA?AV0@_K@Z; SafeInt<unsigned __int64,SafeIntExceptionHandler<Exception>>::operator*<unsigned __int64>(unsigned __int64)
0x18012369a  mov     rcx, [rax]
0x18012369d  mov     eax, 0FFFFFFFFh
0x1801236a2  cmp     rcx, rax
0x1801236a5  jbe     loc_180123544
0x1801236ab  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x1801236b1  test    r12, r12
0x1801236b4  jmp     short loc_180123657
0x1801236b6  lea     r9, ds:2[r15*2]
0x1801236be  mov     r8, [rbp+arg_10]
0x1801236c2  mov     rdx, [rdi+8]
0x1801236c6  mov     rcx, rdi
0x1801236c9  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x1801236ce  jmp     loc_180123607
```
