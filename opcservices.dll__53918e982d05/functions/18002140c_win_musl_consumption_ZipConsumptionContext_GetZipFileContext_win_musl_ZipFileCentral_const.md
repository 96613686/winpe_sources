# win_musl::consumption::ZipConsumptionContext::GetZipFileContext(win_musl::ZipFileCentral const &)

- ea: `0x18002140c`
- end: `0x1800216d8`
- name: `?GetZipFileContext@ZipConsumptionContext@consumption@win_musl@@QEAA?AV?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@AEBVZipFileCentral@3@@Z`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f158`

## callees

- `0x18000531c`
- `0x180011b14`
- `0x18001568c`
- `0x18002140c`
- `0x1800216e0`
- `0x18002184c`
- `0x180021928`
- `0x180021984`
- `0x180021eb8`
- `0x180022edc`
- `0x18002db70`
- `0x18009c7bc`
- `0x1800cd6fc`
- `0x1800d0848`
- `0x1801178c6`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021475`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021580`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021580`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021462`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021462`

## string_xrefs

- `0x180021692`: `mismatch between central directory and actual files.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall win_musl::consumption::ZipConsumptionContext::GetZipFileContext(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  bool v7; // dl
  win_dox *v8; // rcx
  __int64 *v9; // r15
  __int64 *v10; // rdi
  __int64 *v11; // rbp
  size_t v12; // r12
  const void *v13; // rdx
  size_t v14; // r8
  _QWORD *v15; // rcx
  int v16; // eax
  win_musl::consumption::ZipFileContext *v17; // rax
  int v18; // edx
  const char *v19; // r8
  unsigned int v20; // r9d
  void *v23; // rax
  __m128i v24; // xmm0
  __int64 v25; // rdi
  __m128i v26; // [rsp+48h] [rbp-110h] BYREF
  __int64 v27; // [rsp+58h] [rbp-100h]
  _QWORD *v28; // [rsp+60h] [rbp-F8h]
  __int64 v29; // [rsp+68h] [rbp-F0h]
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-E8h] BYREF

  v27 = -2;
  v28 = a2;
  v6 = a1 + 40;
  v29 = a1 + 40;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v8 = (win_dox *)*(unsigned int *)(v6 + 44);
  *(_DWORD *)(v6 + 44) = (_DWORD)v8 + 1;
  if ( !(_DWORD)v8 )
    *(_DWORD *)(v6 + 40) = GetCurrentThreadId();
  LOBYTE(v8) = *(_BYTE *)(a1 + 96);
  win_dox::ThrowIfFailed(v8, v7);
  *a2 = 0;
  a2[1] = 0;
  v9 = *(__int64 **)(a1 + 24);
  v10 = (__int64 *)v9[1];
  v11 = v9;
  if ( *((_BYTE *)v10 + 81) )
  {
LABEL_18:
    v11 = v9;
    goto LABEL_19;
  }
  v12 = a3[4];
  do
  {
    if ( a3[5] < 0x10u )
      v13 = a3 + 2;
    else
      v13 = (const void *)a3[2];
    v14 = v12;
    if ( v10[6] < v12 )
      v14 = v10[6];
    v15 = v10 + 4;
    if ( (unsigned __int64)v10[7] >= 0x10 )
      v15 = (_QWORD *)*v15;
    v16 = memcmp_0(v15, v13, v14);
    if ( v16 )
    {
      if ( v16 < 0 )
        goto LABEL_13;
    }
    else if ( v10[6] < v12 )
    {
LABEL_13:
      v10 = (__int64 *)v10[2];
      continue;
    }
    v11 = v10;
    v10 = (__int64 *)*v10;
  }
  while ( !*((_BYTE *)v10 + 81) );
  v6 = a1 + 40;
  if ( v11 == v9 )
    goto LABEL_18;
  if ( (int)std::string::compare(a3 + 1, v11 + 3) < 0 )
  {
    v9 = *(__int64 **)(a1 + 24);
    goto LABEL_18;
  }
LABEL_19:
  if ( *(__int64 **)(a1 + 24) == v11 )
  {
    if ( !win_dox::ByteCollection::CanPosition((win_dox::ByteCollection *)(a1 + 104))
      || !win_dox::ByteCollection::HasSize((win_dox::ByteCollection *)(a1 + 104)) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x29Au,
        0x80511006,
        (struct win_musl::TStringEllipseBase *)L"mismatch between central directory and actual files.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v17 = (win_musl::consumption::ZipFileContext *)operator new(0x1F0u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v17 )
      SplException::RealThrowFromHR((SplException *)0x8007000ELL, v18, v19, v20);
    v25 = win_musl::consumption::ZipFileContext::ZipFileContext(v17);
    v26.m128i_i64[0] = v25;
    if ( v25 )
    {
      v23 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v23 )
      {
        win_scope::close_delete::close<win_musl::consumption::ZipFileContext>((win_musl::consumption::ZipFileContext **)&v26);
        win_scope::report_policy_throw::report_init_failure();
      }
      *((_QWORD *)v23 + 1) = 0;
      *(_QWORD *)v23 = &win_scope::counted_strong_weak<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
      *((_QWORD *)v23 + 2) = v25;
      if ( _InterlockedIncrement((volatile signed __int32 *)v23 + 2) == 1 )
        _InterlockedAdd((volatile signed __int32 *)v23 + 3, 1u);
    }
    else
    {
      v25 = 0;
      v23 = 0;
    }
    v26 = *(__m128i *)a2;
    v24 = v26;
    *a2 = v23;
    a2[1] = v25;
    if ( v24.m128i_i64[0] && _mm_srli_si128(v24, 8).m128i_u64[0] )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v26);
  }
  else
  {
    win_scope::scope<unsigned char *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>::operator=(
      a2,
      v11 + 8);
  }
  if ( v6 )
  {
    if ( (*(_DWORD *)(v6 + 44))-- == 1 )
      *(_DWORD *)(v6 + 40) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  }
  return a2;
}

```

## disassembly

```asm
0x18002140c  mov     rax, rsp
0x18002140f  push    rbp
0x180021410  push    rsi
0x180021411  push    rdi
0x180021412  push    r12
0x180021414  push    r13
0x180021416  push    r14
0x180021418  push    r15
0x18002141a  sub     rsp, 120h
0x180021421  mov     [rsp+158h+var_100], 0FFFFFFFFFFFFFFFEh
0x18002142a  mov     [rax+20h], rbx
0x18002142e  mov     rax, cs:__security_cookie
0x180021435  xor     rax, rsp
0x180021438  mov     [rsp+158h+var_48], rax
0x180021440  mov     r13, r8
0x180021443  mov     rsi, rdx
0x180021446  mov     r14, rcx
0x180021449  mov     [rsp+158h+var_F8], rdx
0x18002144e  xor     r12d, r12d
0x180021451  mov     [rsp+158h+var_118], r12d
0x180021456  lea     rbx, [rcx+28h]
0x18002145a  mov     [rsp+158h+var_F0], rbx
0x18002145f  mov     rcx, rbx; lpCriticalSection
0x180021462  call    cs:__imp_EnterCriticalSection
0x180021468  mov     ecx, [rbx+2Ch]
0x18002146b  lea     eax, [rcx+1]
0x18002146e  mov     [rbx+2Ch], eax
0x180021471  test    ecx, ecx
0x180021473  jnz     short loc_18002147E
0x180021475  call    cs:__imp_GetCurrentThreadId
0x18002147b  mov     [rbx+28h], eax
0x18002147e  mov     cl, [r14+60h]; this
0x180021482  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180021487  mov     [rsi], r12
0x18002148a  mov     [rsi+8], r12
0x18002148e  mov     [rsp+158h+var_118], 1
0x180021496  mov     r15, [r14+18h]
0x18002149a  mov     rdi, [r15+8]
0x18002149e  mov     rbp, r15
0x1800214a1  cmp     [rdi+51h], r12b
0x1800214a5  jnz     short loc_180021507
0x1800214a7  mov     r12, [r13+20h]
0x1800214ab  cmp     qword ptr [r13+28h], 10h
0x1800214b0  jb      loc_180021557
0x1800214b6  mov     rdx, [r13+10h]; Buf2
0x1800214ba  mov     r8, r12
0x1800214bd  cmp     [rdi+30h], r12
0x1800214c1  cmovb   r8, [rdi+30h]; Size
0x1800214c6  lea     rcx, [rdi+20h]
0x1800214ca  cmp     qword ptr [rdi+38h], 10h
0x1800214cf  jb      short loc_1800214D4
0x1800214d1  mov     rcx, [rcx]; Buf1
0x1800214d4  call    memcmp_0
0x1800214d9  test    eax, eax
0x1800214db  jz      short loc_1800214E5
0x1800214dd  jns     short loc_1800214EB
0x1800214df  mov     rdi, [rdi+10h]
0x1800214e3  jmp     short loc_1800214F1
0x1800214e5  cmp     [rdi+30h], r12
0x1800214e9  jb      short loc_1800214DF
0x1800214eb  mov     rbp, rdi
0x1800214ee  mov     rdi, [rdi]
0x1800214f1  cmp     byte ptr [rdi+51h], 0
0x1800214f5  jz      short loc_1800214AB
0x1800214f7  cmp     rbp, r15
0x1800214fa  lea     rbx, [r14+28h]
0x1800214fe  jnz     loc_1800215B4
0x180021504  xor     r12d, r12d
0x180021507  mov     rbp, r15
0x18002150a  cmp     [r14+18h], rbp
0x18002150e  jnz     short loc_180021560
0x180021510  lea     rcx, [r14+68h]; this
0x180021514  call    ?CanPosition@ByteCollection@win_dox@@QEBA_NXZ; win_dox::ByteCollection::CanPosition(void)
0x180021519  test    al, al
0x18002151b  jz      loc_180021692
0x180021521  lea     rcx, [r14+68h]; this
0x180021525  call    ?HasSize@ByteCollection@win_dox@@QEBA_NXZ; win_dox::ByteCollection::HasSize(void)
0x18002152a  test    al, al
0x18002152c  jz      loc_180021692
0x180021532  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021539  mov     ecx, 1F0h; unsigned __int64
0x18002153e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021543  test    rax, rax
0x180021546  jnz     loc_18002165C
0x18002154c  mov     ecx, 8007000Eh; this
0x180021551  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x180021557  lea     rdx, [r13+10h]
0x18002155b  jmp     loc_1800214BA
0x180021560  lea     rdx, [rbp+40h]
0x180021564  mov     rcx, rsi
0x180021567  call    ??4?$scope@PEAEU?$const_policies@U?$shared_close_policies@Uclose_delete_array@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAAAEAV01@AEBV01@@Z; win_scope::scope<uchar *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>::operator=(win_scope::scope<uchar *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>> const &)
0x18002156c  jmp     short $+2
0x18002156e  test    rbx, rbx
0x180021571  jz      short loc_180021586
0x180021573  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180021577  jnz     short loc_18002157D
0x180021579  mov     [rbx+28h], r12d
0x18002157d  mov     rcx, rbx; lpCriticalSection
0x180021580  call    cs:__imp_LeaveCriticalSection
0x180021586  mov     rax, rsi
0x180021589  mov     rcx, [rsp+158h+var_48]
0x180021591  xor     rcx, rsp; StackCookie
0x180021594  call    __security_check_cookie
0x180021599  mov     rbx, [rsp+158h+arg_18]
0x1800215a1  add     rsp, 120h
0x1800215a8  pop     r15
0x1800215aa  pop     r14
0x1800215ac  pop     r13
0x1800215ae  pop     r12
0x1800215b0  pop     rdi
0x1800215b1  pop     rsi
0x1800215b2  pop     rbp
0x1800215b3  retn
0x1800215b4  lea     rdx, [rbp+18h]
0x1800215b8  lea     rcx, [r13+8]
0x1800215bc  call    ?compare@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEBAHAEBV12@@Z; std::string::compare(std::string const &)
0x1800215c1  xor     r12d, r12d
0x1800215c4  test    eax, eax
0x1800215c6  jns     loc_18002150A
0x1800215cc  mov     r15, [r14+18h]
0x1800215d0  jmp     loc_180021507
0x1800215d5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800215dc  mov     ecx, 18h; unsigned __int64
0x1800215e1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800215e6  test    rax, rax
0x1800215e9  jz      loc_180021682
0x1800215ef  mov     qword ptr [rax+8], 0
0x1800215f7  lea     rcx, ??_7?$counted_strong_weak@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x1800215fe  mov     [rax], rcx
0x180021601  mov     [rax+10h], rdi
0x180021605  mov     edx, 1
0x18002160a  mov     ecx, edx
0x18002160c  lock xadd [rax+8], ecx
0x180021611  add     ecx, edx
0x180021613  cmp     ecx, edx
0x180021615  jz      short loc_180021656
0x180021617  movups  xmm0, xmmword ptr [rsi]
0x18002161a  movups  [rsp+158h+var_110], xmm0
0x18002161f  mov     [rsi], rax
0x180021622  mov     [rsi+8], rdi
0x180021626  movq    rax, xmm0
0x18002162b  test    rax, rax
0x18002162e  jz      loc_18002156E
0x180021634  psrldq  xmm0, 8
0x180021639  movq    rax, xmm0
0x18002163e  test    rax, rax
0x180021641  jz      loc_18002156E
0x180021647  lea     rcx, [rsp+158h+var_110]
0x18002164c  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180021651  jmp     loc_18002156E
0x180021656  lock add [rax+0Ch], edx
0x18002165a  jmp     short loc_180021617
0x18002165c  mov     qword ptr [rsp+158h+var_110], rax
0x180021661  mov     rcx, rax; this
0x180021664  call    ??0ZipFileContext@consumption@win_musl@@QEAA@XZ; win_musl::consumption::ZipFileContext::ZipFileContext(void)
0x180021669  mov     rdi, rax
0x18002166c  mov     qword ptr [rsp+158h+var_110], rax
0x180021671  test    rax, rax
0x180021674  jnz     loc_1800215D5
0x18002167a  mov     rdi, r12
0x18002167d  mov     rax, r12
0x180021680  jmp     short loc_180021617
0x180021682  lea     rcx, [rsp+158h+var_110]
0x180021687  call    ??$close@UZipFileContext@consumption@win_musl@@@close_delete@win_scope@@SAXPEAPEAUZipFileContext@consumption@win_musl@@@Z; win_scope::close_delete::close<win_musl::consumption::ZipFileContext>(win_musl::consumption::ZipFileContext * *)
0x18002168c  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x180021692  lea     rax, aMismatchBetwee; "mismatch between central directory and "...
0x180021699  mov     [rsp+158h+var_128], rax; struct win_musl::TStringEllipseBase *
0x18002169e  mov     [rsp+158h+var_130], 80511006h; unsigned int
0x1800216a6  mov     [rsp+158h+var_138], 29Ah; unsigned int
0x1800216ae  lea     r9, word_180139126
0x1800216b5  lea     r8, aNoFilename; "(no filename)"
0x1800216bc  lea     rcx, [rsp+158h+pExceptionObject]; this
0x1800216c1  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800216c6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800216cd  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x1800216d2  call    _CxxThrowException_0
```
