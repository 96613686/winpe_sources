# EncodePartUri(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &)

- ea: `0x180017810`
- end: `0x180018194`
- name: `?EncodePartUri@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV12@0@Z`
- size: `2436`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800160c4`

## callees

- `0x180012468`
- `0x18001568c`
- `0x1800175b0`
- `0x180017810`
- `0x1800181a0`
- `0x180018450`
- `0x1800190e0`
- `0x1800195ac`
- `0x180019650`
- `0x1800196c0`
- `0x180019d10`
- `0x18002db70`
- `0x18005a110`
- `0x1800631e4`
- `0x18009c7bc`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800cded0`
- `0x1800cdf2c`
- `0x1800d0848`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180017aa9`
- `msvcrt!memcpy_s` at `0x180017b77`
- `msvcrt!memcpy_s` at `0x180017deb`
- `msvcrt!memcpy_s` at `0x180017aa9`
- `msvcrt!memcpy_s` at `0x180017b77`
- `msvcrt!memcpy_s` at `0x180017deb`

## string_xrefs

- `0x180017a5c`: `http://www.example.com`
- `0x180017f75`: `Call to CPercentDecodePartUri::GetEncodedLength failed with HResult 0x%X.`
- `0x180018041`: `Call to CPercentDecodePartUri::Decode failed with HResult 0x%X.`
- `0x180017fdb`: `Call to PercentEncodePartUri::Encode failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall EncodePartUri(__int64 a1, _QWORD *a2, __int64 a3, unsigned __int16 **a4)
{
  __int64 v6; // rcx
  _QWORD *v7; // rax
  signed int v8; // ebx
  unsigned __int64 v9; // rax
  int v10; // edx
  void **v11; // rbx
  const char *v12; // r8
  unsigned int v13; // r9d
  volatile signed __int32 *v14; // rax
  unsigned __int16 **v15; // r9
  win_scope::counted_strong_weak_base *v16; // r14
  signed int v17; // edi
  unsigned __int16 **v18; // r9
  signed int v19; // edi
  unsigned __int64 v20; // r8
  unsigned int v21; // eax
  _WORD *v22; // rdx
  unsigned __int64 v23; // r11
  unsigned __int64 v24; // r10
  unsigned __int64 v25; // rdi
  char v26; // dl
  char v27; // r9
  unsigned __int64 i; // rcx
  __int16 v29; // ax
  unsigned __int64 v30; // r8
  unsigned __int64 v31; // r10
  unsigned __int64 v32; // r11
  char v33; // dl
  unsigned __int64 j; // rcx
  __int16 v35; // ax
  void **v36; // rcx
  void **v37; // rcx
  unsigned __int64 v38; // r10
  unsigned __int64 v39; // rdi
  void **v40; // rax
  void **v41; // rcx
  unsigned __int64 v42; // rsi
  void **v43; // rax
  void **v44; // rcx
  __int16 v46; // r9
  void **v47; // rax
  void **v48; // rcx
  unsigned __int64 v49; // rdi
  void **v50; // rax
  void **v51; // rcx
  void **v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rdx
  void **v55; // rcx
  void **v56; // rax
  void **v57; // rax
  unsigned __int64 *v58; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v59; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v60; // [rsp+20h] [rbp-E0h]
  char v61; // [rsp+28h] [rbp-D8h]
  char v62; // [rsp+28h] [rbp-D8h]
  char v63; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v64; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v65[8]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v66[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v67[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v68; // [rsp+88h] [rbp-78h]
  __int64 v69; // [rsp+98h] [rbp-68h]
  char v70[8]; // [rsp+A0h] [rbp-60h] BYREF
  void *Destination[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v72; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v73; // [rsp+C0h] [rbp-40h]
  _BYTE pExceptionObject[160]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t v75[512]; // [rsp+170h] [rbp+70h] BYREF

  v69 = -2;
  v68 = 0;
  v64 = 0;
  v6 = a2[3];
  v7 = a2 + 1;
  if ( a2[4] >= 8u )
    v7 = (_QWORD *)*v7;
  v67[1] = v7;
  v67[2] = v6;
  v67[0] = &win_dox::PercentEncodePartUri::`vftable';
  v8 = CPercentEncodeString::Encode((CPercentEncodeString *)v67, 0, &v64, a4, v58, v61);
  if ( v8 < 0 )
  {
    memset_0(v75, 0, sizeof(v75));
    StringCchPrintfW(
      v75,
      0x200u,
      L"Call to CPercentDecodePartUri::GetEncodedLength failed with HResult 0x%X.",
      (unsigned int)v8);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x485u,
      v8,
      (struct win_musl::TStringEllipseBase *)v75);
    throw (SplException::THResultException *)pExceptionObject;
  }
  ++v64;
  v9 = 2 * v64;
  if ( !is_mul_ok(v64, 2u) )
    v9 = -1;
  v11 = (void **)operator new(v9, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v11 )
    SplException::RealThrowFromHR((SplException *)0x8007000ELL, v10, v12, v13);
  v14 = (volatile signed __int32 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = (win_scope::counted_strong_weak_base *)v14;
  if ( !v14 )
  {
    operator delete(v11);
    win_scope::report_policy_throw::report_init_failure();
  }
  *((_QWORD *)v14 + 1) = 0;
  *(_QWORD *)v14 = &win_scope::counted_strong_weak<bool volatile *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
  *((_QWORD *)v14 + 2) = v11;
  if ( _InterlockedIncrement(v14 + 2) == 1 )
    _InterlockedIncrement(v14 + 3);
  *(_QWORD *)&v68 = v14;
  *((_QWORD *)&v68 + 1) = v11;
  v17 = CPercentEncodeString::Encode((CPercentEncodeString *)v67, (unsigned __int16 *)v11, &v64, v15, v59, v62);
  if ( v17 < 0 )
  {
    memset_0(v75, 0, sizeof(v75));
    StringCchPrintfW(v75, 0x200u, L"Call to PercentEncodePartUri::Encode failed with HResult 0x%X.", (unsigned int)v17);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x492u,
      v17,
      (struct win_musl::TStringEllipseBase *)v75);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v66[1] = v11;
  v66[2] = v64;
  v66[0] = &win_dox::PercentDecodePartUri::`vftable';
  ++v64;
  v19 = CPercentDecodeString::Decode((CPercentDecodeString *)v66, (unsigned __int16 *)v11, &v64, v18, v60, v63);
  if ( v19 < 0 )
  {
    memset_0(v75, 0, sizeof(v75));
    StringCchPrintfW(v75, 0x200u, L"Call to CPercentDecodePartUri::Decode failed with HResult 0x%X.", (unsigned int)v19);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x4A9u,
      v19,
      (struct win_musl::TStringEllipseBase *)v75);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v20 = v64 + 1;
  v21 = 0;
  if ( (_DWORD)v64 != -1 )
  {
    do
    {
      v22 = (_WORD *)v11 + v21;
      if ( !*v22 )
        break;
      if ( *v22 == 92 )
        *v22 = 47;
      ++v21;
    }
    while ( v21 < (unsigned int)v20 );
  }
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 1;
  for ( i = 0; i < v20; ++i )
  {
    v29 = *((_WORD *)v11 + i);
    if ( v29 == 47 || !v29 )
    {
      if ( v23 != i )
      {
        if ( !v26 || v27 )
        {
          if ( v24 == v23 )
          {
            v24 = i;
          }
          else
          {
            for ( ; v23 < i; ++v24 )
              *((_WORD *)v11 + v24) = *((_WORD *)v11 + v23++);
          }
        }
        else if ( v24 == v23 )
        {
          v24 = v25;
        }
        else
        {
          for ( ; v23 < v25; ++v24 )
            *((_WORD *)v11 + v24) = *((_WORD *)v11 + v23++);
        }
      }
      if ( !*((_WORD *)v11 + i) )
        *((_WORD *)v11 + v24) = 0;
      v23 = i;
      v27 = 1;
    }
    else
    {
      if ( v29 == 46 )
      {
        if ( !v26 )
        {
          v26 = 1;
          v25 = i;
        }
        continue;
      }
      v27 = 0;
    }
    v26 = 0;
  }
  v30 = v24 + 1;
  v31 = 0;
  v32 = 0;
  v33 = 1;
  for ( j = 0; j < v30; ++j )
  {
    v35 = *((_WORD *)v11 + j);
    if ( v35 == 47 || !v35 )
    {
      v46 = *((_WORD *)v11 + j);
      if ( v31 != j && (!v33 || j - v31 - 2 <= 1 || j - v31 == 1 && *((_WORD *)v11 + v31) == 46) )
      {
        if ( v32 == v31 )
        {
          v32 = j;
        }
        else if ( v31 < j )
        {
          do
            *((_WORD *)v11 + v32++) = *((_WORD *)v11 + v31++);
          while ( v31 < j );
          v46 = *((_WORD *)v11 + j);
        }
      }
      if ( !v46 )
        *((_WORD *)v11 + v32) = 0;
      v31 = j;
      v33 = 1;
    }
    else if ( v35 != 46 )
    {
      v33 = 0;
    }
  }
  v73 = 7;
  v72 = 0;
  LOWORD(Destination[0]) = 0;
  std::wstring::_Copy(v70, 22, 0);
  v36 = Destination;
  if ( v73 >= 8 )
    v36 = (void **)Destination[0];
  memcpy_s(v36, 2 * v73, L"http://www.example.com", 0x2Cu);
  v37 = Destination;
  if ( v73 >= 8 )
    v37 = (void **)Destination[0];
  v72 = 22;
  *((_WORD *)v37 + 22) = 0;
  if ( *(_WORD *)v11 == 47 )
    goto LABEL_35;
  if ( *(_QWORD *)(a3 + 24) )
  {
    std::wstring::append(v70, a3, 0, -1);
    if ( *(_WORD *)v11 != 63 && *(_WORD *)v11 != 35 )
    {
      v65[0] = 47;
      v53 = std::wstring::rfind(v70, v65, -1, 1);
      if ( v53 != -1 )
      {
        v54 = v53 + 1;
        if ( v53 + 1 > v72 )
          std::wstring::append(v70, v54 - v72, 0);
        else
          std::wstring::erase(v70, v54, -1);
      }
    }
    goto LABEL_35;
  }
  v47 = Destination;
  v38 = v73;
  if ( v73 >= 8 )
    v47 = (void **)Destination[0];
  if ( L"/" >= (const OLECHAR *)v47 )
  {
    v48 = Destination;
    if ( v73 >= 8 )
      v48 = (void **)Destination[0];
    if ( (char *)v48 + 2 * v72 > (char *)L"/" )
    {
      v56 = Destination;
      if ( v73 >= 8 )
        v56 = (void **)Destination[0];
      std::wstring::append(v70, v70, ((char *)L"/" - (char *)v56) >> 1, 1);
      goto LABEL_35;
    }
  }
  if ( -1LL - v72 <= 1 )
    std::_String_base::_Xlen();
  v49 = v72 + 1;
  if ( v72 + 1 > 0x7FFFFFFFFFFFFFFELL )
    std::_String_base::_Xlen();
  if ( v73 < v49 )
  {
    std::wstring::_Copy(v70, v72 + 1, v72);
    v38 = v73;
    if ( !v49 )
      goto LABEL_36;
  }
  else if ( v72 == -1 )
  {
    v55 = Destination;
    if ( v73 >= 8 )
      v55 = (void **)Destination[0];
    v72 = 0;
    *(_WORD *)v55 = 0;
    goto LABEL_35;
  }
  v50 = Destination;
  if ( v38 >= 8 )
    v50 = (void **)Destination[0];
  memcpy_s((char *)v50 + 2 * v72, 2 * (v38 - v72), L"/", 2u);
  v51 = Destination;
  if ( v73 >= 8 )
    v51 = (void **)Destination[0];
  v72 = v49;
  *((_WORD *)v51 + v49) = 0;
LABEL_35:
  v38 = v73;
LABEL_36:
  v39 = -1;
  do
    ++v39;
  while ( *((_WORD *)v11 + v39) );
  v40 = Destination;
  if ( v38 >= 8 )
    v40 = (void **)Destination[0];
  if ( v11 < v40 )
    goto LABEL_44;
  v41 = Destination;
  if ( v38 >= 8 )
    v41 = (void **)Destination[0];
  if ( (void **)((char *)v41 + 2 * v72) > v11 )
  {
    v57 = Destination;
    if ( v38 >= 8 )
      v57 = (void **)Destination[0];
    std::wstring::append(v70, v70, ((char *)v11 - (char *)v57) >> 1, v39);
  }
  else
  {
LABEL_44:
    if ( -1LL - v72 <= v39 )
      std::_String_base::_Xlen();
    if ( v39 )
    {
      v42 = v39 + v72;
      if ( v39 + v72 > 0x7FFFFFFFFFFFFFFELL )
        std::_String_base::_Xlen();
      if ( v38 < v42 )
      {
        std::wstring::_Copy(v70, v39 + v72, v72);
        v38 = v73;
        if ( !v42 )
          goto LABEL_54;
        goto LABEL_49;
      }
      if ( v42 )
      {
LABEL_49:
        v43 = Destination;
        if ( v38 >= 8 )
          v43 = (void **)Destination[0];
        memcpy_s((char *)v43 + 2 * v72, 2 * (v38 - v72), v11, 2 * v39);
        v44 = Destination;
        if ( v73 >= 8 )
          v44 = (void **)Destination[0];
        v72 = v42;
        *((_WORD *)v44 + v42) = 0;
        goto LABEL_54;
      }
      v52 = Destination;
      if ( v38 >= 8 )
        v52 = (void **)Destination[0];
      v72 = 0;
      *(_WORD *)v52 = 0;
    }
  }
LABEL_54:
  win_dox::Uri::CreateUri((__int64)&v64, (__int64)v70, 0x1100u);
  win_dox::Uri::GetPath(&v64, a1);
  if ( v64 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v64 + 16LL))(v64);
  if ( v73 >= 8 )
    operator delete(Destination[0]);
  v73 = 7;
  v72 = 0;
  LOWORD(Destination[0]) = 0;
  v66[0] = &CPercentDecodeString::`vftable';
  v67[0] = &CPercentEncodeString::`vftable';
  if ( v16 )
    win_scope::counted_strong_weak_base::Release(v16);
  return a1;
}

```

## disassembly

```asm
0x180017810  push    rbp
0x180017812  push    rsi
0x180017813  push    rdi
0x180017814  push    r12
0x180017816  push    r13
0x180017818  push    r14
0x18001781a  push    r15
0x18001781c  lea     rbp, [rsp-480h]
0x180017824  sub     rsp, 580h
0x18001782b  mov     [rbp+4B0h+var_518], 0FFFFFFFFFFFFFFFEh
0x180017833  mov     [rsp+5B0h+arg_8], rbx
0x18001783b  mov     rax, cs:__security_cookie
0x180017842  xor     rax, rsp
0x180017845  mov     [rbp+4B0h+var_40], rax
0x18001784c  mov     r13, r8
0x18001784f  mov     r12, rcx
0x180017852  mov     [rsp+5B0h+var_570], rcx
0x180017857  xor     esi, esi
0x180017859  xorps   xmm0, xmm0
0x18001785c  movdqu  [rbp+4B0h+var_528], xmm0
0x180017861  mov     [rsp+5B0h+var_570], rsi
0x180017866  mov     rcx, [rdx+18h]
0x18001786a  lea     rax, [rdx+8]
0x18001786e  cmp     qword ptr [rdx+20h], 8
0x180017873  jb      short loc_180017878
0x180017875  mov     rax, [rax]
0x180017878  mov     [rsp+5B0h+var_538], rax
0x18001787d  mov     [rbp+4B0h+var_530], rcx
0x180017881  lea     rax, ??_7PercentEncodePartUri@win_dox@@6B@; const win_dox::PercentEncodePartUri::`vftable'
0x180017888  mov     [rsp+5B0h+var_540], rax
0x18001788d  lea     r8, [rsp+5B0h+var_570]; unsigned __int64 *
0x180017892  xor     edx, edx; unsigned __int16 *
0x180017894  lea     rcx, [rsp+5B0h+var_540]; this
0x180017899  call    ?Encode@CPercentEncodeString@@QEAAJPEAGPEA_KPEAPEAG1K@Z; CPercentEncodeString::Encode(ushort *,unsigned __int64 *,ushort * *,unsigned __int64 *,ulong)
0x18001789e  mov     ebx, eax
0x1800178a0  test    eax, eax
0x1800178a2  js      loc_180017F61
0x1800178a8  mov     rcx, [rsp+5B0h+var_570]
0x1800178ad  inc     rcx
0x1800178b0  mov     [rsp+5B0h+var_570], rcx
0x1800178b5  mov     eax, 2
0x1800178ba  mul     rcx
0x1800178bd  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800178c4  cmovb   rax, r15
0x1800178c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800178cf  mov     rcx, rax; unsigned __int64
0x1800178d2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800178d7  mov     rbx, rax
0x1800178da  test    rax, rax
0x1800178dd  jz      loc_180017E0E
0x1800178e3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800178ea  mov     ecx, 18h; unsigned __int64
0x1800178ef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800178f4  mov     r14, rax
0x1800178f7  test    rax, rax
0x1800178fa  jz      loc_180017EAE
0x180017900  mov     [rax+8], rsi
0x180017904  lea     rax, ??_7?$counted_strong_weak@PEC_NU?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<bool volatile *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x18001790b  mov     [r14], rax
0x18001790e  mov     [r14+10h], rbx
0x180017912  mov     eax, 1
0x180017917  lock xadd [r14+8], eax
0x18001791d  inc     eax
0x18001791f  cmp     eax, 1
0x180017922  jz      loc_180017CC3
0x180017928  mov     qword ptr [rbp+4B0h+var_528], r14
0x18001792c  mov     qword ptr [rbp+4B0h+var_528+8], rbx
0x180017930  lea     r8, [rsp+5B0h+var_570]; unsigned __int64 *
0x180017935  mov     rdx, rbx; unsigned __int16 *
0x180017938  lea     rcx, [rsp+5B0h+var_540]; this
0x18001793d  call    ?Encode@CPercentEncodeString@@QEAAJPEAGPEA_KPEAPEAG1K@Z; CPercentEncodeString::Encode(ushort *,unsigned __int64 *,ushort * *,unsigned __int64 *,ulong)
0x180017942  mov     edi, eax
0x180017944  test    eax, eax
0x180017946  js      loc_180017FC7
0x18001794c  mov     [rsp+5B0h+var_550], rbx
0x180017951  mov     rcx, [rsp+5B0h+var_570]
0x180017956  mov     dword ptr [rsp+5B0h+var_548], ecx
0x18001795a  mov     eax, dword ptr [rsp+5B0h+var_570+4]
0x18001795e  mov     dword ptr [rsp+5B0h+var_548+4], eax
0x180017962  lea     rax, ??_7PercentDecodePartUri@win_dox@@6B@; const win_dox::PercentDecodePartUri::`vftable'
0x180017969  mov     [rsp+5B0h+var_558], rax
0x18001796e  inc     rcx
0x180017971  mov     [rsp+5B0h+var_570], rcx
0x180017976  lea     r8, [rsp+5B0h+var_570]; unsigned __int64 *
0x18001797b  mov     rdx, rbx; unsigned __int16 *
0x18001797e  lea     rcx, [rsp+5B0h+var_558]; this
0x180017983  call    ?Decode@CPercentDecodeString@@QEAAJPEAGPEA_KPEAPEAG1K@Z; CPercentDecodeString::Decode(ushort *,unsigned __int64 *,ushort * *,unsigned __int64 *,ulong)
0x180017988  mov     edi, eax
0x18001798a  test    eax, eax
0x18001798c  js      loc_18001802D
0x180017992  mov     r8, [rsp+5B0h+var_570]
0x180017997  inc     r8
0x18001799a  mov     eax, esi
0x18001799c  test    r8d, r8d
0x18001799f  jz      short loc_1800179C0
0x1800179a1  mov     ecx, eax
0x1800179a3  lea     rdx, [rbx+rcx*2]
0x1800179a7  movzx   ecx, word ptr [rdx]
0x1800179aa  test    cx, cx
0x1800179ad  jz      short loc_1800179C0
0x1800179af  cmp     cx, 5Ch ; '\'
0x1800179b3  jz      loc_180017C43
0x1800179b9  inc     eax
0x1800179bb  cmp     eax, r8d
0x1800179be  jb      short loc_1800179A1
0x1800179c0  mov     r11, rsi
0x1800179c3  mov     r10, rsi
0x1800179c6  mov     rdi, rsi
0x1800179c9  xor     dl, dl
0x1800179cb  mov     r9b, 1
0x1800179ce  mov     rcx, rsi
0x1800179d1  test    r8, r8
0x1800179d4  jz      short loc_180017A0E
0x1800179d6  nop     word ptr [rax+rax+00000000h]
0x1800179e0  movzx   eax, word ptr [rbx+rcx*2]
0x1800179e4  cmp     ax, 2Fh ; '/'
0x1800179e8  jz      loc_180017C4D
0x1800179ee  test    ax, ax
0x1800179f1  jz      loc_180017C4D
0x1800179f7  cmp     ax, 2Eh ; '.'
0x1800179fb  jz      loc_180017C7D
0x180017a01  xor     r9b, r9b
0x180017a04  xor     dl, dl
0x180017a06  inc     rcx
0x180017a09  cmp     rcx, r8
0x180017a0c  jb      short loc_1800179E0
0x180017a0e  lea     r8, [r10+1]
0x180017a12  mov     r10, rsi
0x180017a15  mov     r11, rsi
0x180017a18  mov     dl, 1
0x180017a1a  mov     rcx, rsi
0x180017a1d  test    r8, r8
0x180017a20  jz      short loc_180017A49
0x180017a22  movzx   eax, word ptr [rbx+rcx*2]
0x180017a26  cmp     ax, 2Fh ; '/'
0x180017a2a  jz      loc_180017C8F
0x180017a30  test    ax, ax
0x180017a33  jz      loc_180017C8F
0x180017a39  cmp     ax, 2Eh ; '.'
0x180017a3d  jz      short loc_180017A41
0x180017a3f  xor     dl, dl
0x180017a41  inc     rcx
0x180017a44  cmp     rcx, r8
0x180017a47  jb      short loc_180017A22
0x180017a49  mov     [rbp+4B0h+var_4F0], 7
0x180017a51  mov     rcx, rsi
0x180017a54  mov     [rbp+4B0h+var_4F8], rcx
0x180017a58  mov     word ptr [rbp+4B0h+Destination], si
0x180017a5c  lea     rdi, ?g_sampleBaseUri@win_musl@@3QB_WB; "http://www.example.com"
0x180017a63  lea     rax, [rbp+4B0h+Destination]
0x180017a67  cmp     rdi, rax
0x180017a6a  jb      short loc_180017A79
0x180017a6c  lea     rax, [rbp+4B0h+Destination]
0x180017a70  cmp     rax, rdi
0x180017a73  ja      loc_180017CFD
0x180017a79  xor     r8d, r8d
0x180017a7c  mov     esi, 16h
0x180017a81  mov     edx, esi
0x180017a83  lea     rcx, [rbp+4B0h+var_510]
0x180017a87  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180017a8c  mov     rdx, [rbp+4B0h+var_4F0]
0x180017a90  lea     rcx, [rbp+4B0h+Destination]
0x180017a94  cmp     rdx, 8
0x180017a98  cmovnb  rcx, [rbp+4B0h+Destination]; Destination
0x180017a9d  add     rdx, rdx; DestinationSize
0x180017aa0  mov     r9d, 2Ch ; ','; SourceSize
0x180017aa6  mov     r8, rdi; Source
0x180017aa9  call    cs:__imp_memcpy_s
0x180017aaf  lea     rcx, [rbp+4B0h+Destination]
0x180017ab3  cmp     [rbp+4B0h+var_4F0], 8
0x180017ab8  cmovnb  rcx, [rbp+4B0h+Destination]
0x180017abd  mov     [rbp+4B0h+var_4F8], rsi
0x180017ac1  xor     eax, eax
0x180017ac3  mov     [rcx+2Ch], ax
0x180017ac7  cmp     word ptr [rbx], 2Fh ; '/'
0x180017acb  jnz     loc_180017D3F
0x180017ad1  mov     r13, 7FFFFFFFFFFFFFFEh
0x180017adb  mov     r10, [rbp+4B0h+var_4F0]
0x180017adf  mov     rdi, r15
0x180017ae2  inc     rdi
0x180017ae5  cmp     word ptr [rbx+rdi*2], 0
0x180017aea  jnz     short loc_180017AE2
0x180017aec  lea     rax, [rbp+4B0h+Destination]
0x180017af0  mov     rdx, [rbp+4B0h+Destination]
0x180017af4  cmp     r10, 8
0x180017af8  cmovnb  rax, rdx
0x180017afc  cmp     rbx, rax
0x180017aff  jb      short loc_180017B1E
0x180017b01  lea     rcx, [rbp+4B0h+Destination]
0x180017b05  cmp     r10, 8
0x180017b09  cmovnb  rcx, rdx
0x180017b0d  mov     rax, [rbp+4B0h+var_4F8]
0x180017b11  lea     rcx, [rcx+rax*2]
0x180017b15  cmp     rcx, rbx
0x180017b18  ja      loc_18001814D
0x180017b1e  sub     r15, [rbp+4B0h+var_4F8]
0x180017b22  cmp     r15, rdi
0x180017b25  jbe     loc_180018177
0x180017b2b  test    rdi, rdi
0x180017b2e  jz      short loc_180017B95
0x180017b30  mov     rsi, [rbp+4B0h+var_4F8]
0x180017b34  add     rsi, rdi
0x180017b37  cmp     rsi, r13
0x180017b3a  ja      loc_180018185
0x180017b40  cmp     r10, rsi
0x180017b43  jb      loc_180017CDB
0x180017b49  test    rsi, rsi
0x180017b4c  jz      loc_180017E19
0x180017b52  mov     rdx, r10
0x180017b55  mov     rcx, [rbp+4B0h+var_4F8]
0x180017b59  sub     rdx, rcx
0x180017b5c  lea     rax, [rbp+4B0h+Destination]
0x180017b60  cmp     r10, 8
0x180017b64  cmovnb  rax, [rbp+4B0h+Destination]
0x180017b69  lea     r9, [rdi+rdi]; SourceSize
0x180017b6d  add     rdx, rdx; DestinationSize
0x180017b70  lea     rcx, [rax+rcx*2]; Destination
0x180017b74  mov     r8, rbx; Source
0x180017b77  call    cs:__imp_memcpy_s
0x180017b7d  lea     rcx, [rbp+4B0h+Destination]
0x180017b81  cmp     [rbp+4B0h+var_4F0], 8
0x180017b86  cmovnb  rcx, [rbp+4B0h+Destination]
0x180017b8b  mov     [rbp+4B0h+var_4F8], rsi
0x180017b8f  xor     eax, eax
0x180017b91  mov     [rcx+rsi*2], ax
0x180017b95  mov     r8d, 1100h
0x180017b9b  lea     rdx, [rbp+4B0h+var_510]
0x180017b9f  lea     rcx, [rsp+5B0h+var_570]
0x180017ba4  call    ?CreateUri@Uri@win_dox@@SA?AV12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@K@Z; win_dox::Uri::CreateUri(std::wstring const &,ulong)
0x180017ba9  nop
0x180017baa  mov     rdx, r12
0x180017bad  lea     rcx, [rsp+5B0h+var_570]
0x180017bb2  call    ?GetPath@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetPath(void)
0x180017bb7  nop
0x180017bb8  mov     rcx, [rsp+5B0h+var_570]
0x180017bbd  test    rcx, rcx
0x180017bc0  jz      short loc_180017BCF
0x180017bc2  mov     rax, [rcx]
0x180017bc5  mov     rax, [rax+10h]
0x180017bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bce  nop
0x180017bcf  cmp     [rbp+4B0h+var_4F0], 8
0x180017bd4  jnb     loc_180017CCD
0x180017bda  mov     [rbp+4B0h+var_4F0], 7
0x180017be2  mov     [rbp+4B0h+var_4F8], 0
0x180017bea  xor     eax, eax
0x180017bec  mov     word ptr [rbp+4B0h+Destination], ax
0x180017bf0  lea     rax, ??_7CPercentDecodeString@@6B@; const CPercentDecodeString::`vftable'
0x180017bf7  mov     [rsp+5B0h+var_558], rax
0x180017bfc  lea     rax, ??_7CPercentEncodeString@@6B@; const CPercentEncodeString::`vftable'
0x180017c03  mov     [rsp+5B0h+var_540], rax
0x180017c08  test    r14, r14
0x180017c0b  jz      short loc_180017C16
0x180017c0d  mov     rcx, r14; this
0x180017c10  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x180017c15  nop
0x180017c16  mov     rax, r12
0x180017c19  mov     rcx, [rbp+4B0h+var_40]
0x180017c20  xor     rcx, rsp; StackCookie
0x180017c23  call    __security_check_cookie
0x180017c28  mov     rbx, [rsp+5B0h+arg_8]
0x180017c30  add     rsp, 580h
0x180017c37  pop     r15
0x180017c39  pop     r14
0x180017c3b  pop     r13
0x180017c3d  pop     r12
0x180017c3f  pop     rdi
0x180017c40  pop     rsi
0x180017c41  pop     rbp
0x180017c42  retn
0x180017c43  mov     word ptr [rdx], 2Fh ; '/'
0x180017c48  jmp     loc_1800179B9
0x180017c4d  cmp     r11, rcx
0x180017c50  jz      short loc_180017C66
0x180017c52  test    dl, dl
0x180017c54  jnz     loc_180017F0D
0x180017c5a  cmp     r10, r11
0x180017c5d  jnz     loc_18001809B
0x180017c63  mov     r10, rcx
0x180017c66  cmp     word ptr [rbx+rcx*2], 0
0x180017c6b  jnz     short loc_180017C72
0x180017c6d  mov     [rbx+r10*2], si
0x180017c72  mov     r11, rcx
0x180017c75  mov     r9b, 1
0x180017c78  jmp     loc_180017A04
0x180017c7d  test    dl, dl
0x180017c7f  jnz     loc_180017A06
0x180017c85  mov     dl, 1
0x180017c87  mov     rdi, rcx
0x180017c8a  jmp     loc_180017A06
0x180017c8f  movzx   r9d, ax
0x180017c93  cmp     r10, rcx
0x180017c96  jz      short loc_180017CAC
0x180017c98  test    dl, dl
0x180017c9a  jnz     loc_180017EDE
0x180017ca0  cmp     r11, r10
0x180017ca3  jnz     loc_1800180BE
0x180017ca9  mov     r11, rcx
0x180017cac  test    r9w, r9w
0x180017cb0  jz      short loc_180017CBC
  ... truncated ...
```
