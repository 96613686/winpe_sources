# win_musl::consumption::ZipConsumptionPart::AddPartToReceiver(__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)

- ea: `0x180028cf0`
- end: `0x18002932c`
- name: `?AddPartToReceiver@ZipConsumptionPart@consumption@win_musl@@AEAAXPEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z`
- size: `1596`
- prototype: `void __fastcall(win_musl::consumption::ZipConsumptionPart *__hidden this, const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001486c`
- `0x180028aa4`

## callees

- `0x18000531c`
- `0x180011b14`
- `0x180011fe8`
- `0x1800120a4`
- `0x180012468`
- `0x1800124f4`
- `0x18001568c`
- `0x1800190e0`
- `0x1800195ac`
- `0x1800240dc`
- `0x180028cf0`
- `0x180029334`
- `0x18002976c`
- `0x18002a198`
- `0x18002db70`
- `0x18009c7bc`
- `0x1800cd6fc`
- `0x1800cded0`
- `0x1800d0848`
- `0x1800d6354`
- `0x1800e850c`
- `0x18010b61c`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180029193`
- `msvcrt!memcpy_s` at `0x180029193`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028ec3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028ec3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028eb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028eb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall win_musl::consumption::ZipConsumptionPart::AddPartToReceiver(
        win_musl::consumption::ZipConsumptionPart *this,
        const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *a2)
{
  const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *v2; // r12
  __int64 v4; // rsi
  _QWORD *v5; // rax
  int v6; // edx
  const char *v7; // r8
  unsigned int v8; // r9d
  _QWORD *v9; // rbx
  void *v10; // rax
  __int64 v11; // rbx
  unsigned int v12; // r15d
  bool v13; // dl
  win_dox *v14; // rcx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, _QWORD *, _QWORD, __int128 *, __int64, const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *); // r14
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  signed int v19; // esi
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  _QWORD *v27; // r14
  unsigned __int64 v28; // r15
  _QWORD *v29; // r8
  unsigned __int64 v30; // rdx
  _QWORD *v31; // rcx
  const wchar_t *v32; // rax
  __int64 v33; // r10
  _QWORD *v34; // r9
  __int128 v35; // [rsp+48h] [rbp-C0h] BYREF
  const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *v36; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v37; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v38; // [rsp+70h] [rbp-98h] BYREF
  win_musl::consumption::ZipConsumptionPart *v39; // [rsp+80h] [rbp-88h] BYREF
  __int64 v40; // [rsp+88h] [rbp-80h]
  __int128 *v41; // [rsp+90h] [rbp-78h] BYREF
  _QWORD *v42; // [rsp+98h] [rbp-70h]
  __int64 v43; // [rsp+A0h] [rbp-68h] BYREF
  win_musl::consumption::ZipConsumptionPart *v44; // [rsp+A8h] [rbp-60h]
  __int64 v45; // [rsp+B0h] [rbp-58h]
  _BYTE v46[48]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v48[160]; // [rsp+128h] [rbp+20h] BYREF
  wchar_t v49[512]; // [rsp+1C8h] [rbp+C0h] BYREF

  v45 = -2;
  v2 = a2;
  v36 = a2;
  if ( *((_BYTE *)this + 152) )
    return;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
  {
    v32 = win_musl::StringOfCompressionOptions(*((_DWORD *)this + 14));
    v34 = (_QWORD *)((char *)this + 24);
    if ( *((_QWORD *)this + 6) >= 8u )
      v34 = (_QWORD *)*v34;
    WPP_SF_SS(
      *(_QWORD *)(v33 + 56),
      11,
      (unsigned int)&WPP_030c92eb782e391dc47680cbab48d7b3_Traceguids,
      (_DWORD)v34,
      (__int64)v32);
  }
  v44 = 0;
  v39 = this;
  v4 = *((_QWORD *)this + 1);
  v43 = v4;
  if ( !v4 )
  {
    win_scope::close_delete::close<win_musl::CallingThread>(&v39);
    win_scope::report_policy_throw::report_init_failure();
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(v4 + 8)) == 1 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 12));
  v44 = this;
  v5 = operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v5;
  if ( !v5 )
    SplException::RealThrowFromHR((SplException *)0x8007000ELL, v6, v7, v8);
  v39 = (win_musl::consumption::ZipConsumptionPart *)v5;
  v41 = &v35;
  v35 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v4 + 8)) == 1 )
    _InterlockedAdd((volatile signed __int32 *)(v4 + 12), 1u);
  *(_QWORD *)&v35 = v4;
  *((_QWORD *)&v35 + 1) = this;
  v41 = &v35;
  v37 = 0;
  v21 = *((_QWORD *)this + 13);
  if ( v21 )
  {
    v22 = *((_QWORD *)this + 14);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v21 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v21 + 12), 1u);
    *(_QWORD *)&v37 = v21;
    *((_QWORD *)&v37 + 1) = v22;
  }
  *(_QWORD *)&v38 = &v37;
  *v5 = 0;
  v5[1] = 0;
  v23 = v37;
  if ( (_QWORD)v37 )
  {
    v24 = *((_QWORD *)&v37 + 1);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v37 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v23 + 12), 1u);
    *v5 = v23;
    v5[1] = v24;
  }
  v5[2] = 0;
  v5[3] = -1;
  v5[4] = 0;
  v5[5] = 0;
  v25 = v35;
  if ( (_QWORD)v35 )
  {
    v26 = *((_QWORD *)&v35 + 1);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v35 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v25 + 12), 1u);
    v5[4] = v25;
    v5[5] = v26;
  }
  v5[10] = 7;
  v27 = v5 + 7;
  v5[9] = 0;
  *((_WORD *)v5 + 28) = 0;
  v28 = *((_QWORD *)this + 5);
  if ( v5 + 6 == (_QWORD *)((char *)this + 16) )
  {
    std::wstring::erase(v5 + 6, *((_QWORD *)this + 5), -1);
    std::wstring::erase(v9 + 6, 0, 0);
  }
  else
  {
    if ( v28 > 0x7FFFFFFFFFFFFFFELL )
      std::_String_base::_Xlen();
    if ( v5[10] >= v28 )
    {
      if ( !v28 )
      {
        if ( v5[10] >= 8u )
          v27 = (_QWORD *)*v27;
        v5[9] = 0;
        *(_WORD *)v27 = 0;
        goto LABEL_58;
      }
      goto LABEL_51;
    }
    std::wstring::_Copy(v5 + 6, *((_QWORD *)this + 5), v5[9]);
    if ( v28 )
    {
LABEL_51:
      v29 = (_QWORD *)((char *)this + 24);
      if ( *((_QWORD *)this + 6) >= 8u )
        v29 = (_QWORD *)*v29;
      v30 = v9[10];
      if ( v30 < 8 )
        v31 = v9 + 7;
      else
        v31 = (_QWORD *)*v27;
      memcpy_s(v31, 2 * v30, v29, 2 * v28);
      if ( v9[10] >= 8u )
        v27 = (_QWORD *)*v27;
      v9[9] = v28;
      *((_WORD *)v27 + v28) = 0;
      v2 = v36;
    }
  }
LABEL_58:
  *((_BYTE *)v9 + 88) = 0;
  if ( *((_QWORD *)&v37 + 1) && (_QWORD)v37 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v37);
    v37 = 0;
  }
  if ( *((_QWORD *)&v35 + 1) && (_QWORD)v35 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v35);
    v35 = 0;
  }
  v42 = 0;
  v36 = (const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *)v9;
  v10 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v10 )
  {
    win_scope::close_delete::close<win_musl::consumption::ZipConsumptionByteCollection>(&v36);
    win_scope::report_policy_throw::report_init_failure();
  }
  *((_QWORD *)v10 + 1) = 0;
  *(_QWORD *)v10 = &win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionByteCollection *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
  *((_QWORD *)v10 + 2) = v9;
  v41 = (__int128 *)v10;
  if ( _InterlockedIncrement((volatile signed __int32 *)v10 + 2) == 1 )
    _InterlockedAdd((volatile signed __int32 *)v10 + 3, 1u);
  v42 = v9;
  v38 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)v10 + 2) == 1 )
    _InterlockedAdd((volatile signed __int32 *)v10 + 3, 1u);
  *(_QWORD *)&v38 = v10;
  *((_QWORD *)&v38 + 1) = v9;
  win_dox::CreateInstanceFromInner<IByteCollection,win_scope::scope<win_musl::consumption::ZipConsumptionByteCollection *,win_scope::const_policies<win_scope::shared_policies>>>(
    &v39,
    &v38);
  v11 = *((_QWORD *)this + 14);
  v12 = *((_DWORD *)this + 14);
  *(_QWORD *)&v38 = v11;
  EnterCriticalSection((LPCRITICAL_SECTION)v11);
  v14 = (win_dox *)*(unsigned int *)(v11 + 44);
  *(_DWORD *)(v11 + 44) = (_DWORD)v14 + 1;
  if ( !(_DWORD)v14 )
    *(_DWORD *)(v11 + 40) = GetCurrentThreadId();
  LOBYTE(v14) = *(_BYTE *)(v11 + 80);
  win_dox::ThrowIfFailed(v14, v13);
  if ( !*(_QWORD *)(v11 + 64) || !*(_QWORD *)(v11 + 72) || dword_1801C4E30 == -1 )
  {
    win_musl::DebugLogHelper(
      "(no filename)",
      &word_180139126,
      124,
      1024,
      -2147418113,
      L"ZipDeinterleaverState::AddOpcStream() is called at invalid state");
    std::string::string(v46, "Program has entered an unexpected state");
    std::logic_error::logic_error(pExceptionObject, v46);
    throw (std::logic_error *)pExceptionObject;
  }
  v15 = *(_QWORD *)(*(_QWORD *)(v11 + 72) + 16LL);
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int128 *, __int64, const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *))(*(_QWORD *)v15 + 48LL);
  v17 = *(_QWORD *)win_dox::StartSendBase<IByteSender>::GetInterface(&v39, &v36);
  v18 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 6) >= 8u )
    v18 = (_QWORD *)*v18;
  v35 = *((_OWORD *)this + 4);
  v19 = v16(v15, v18, v12, &v35, v17, v2);
  if ( v36 )
    (*(void (__fastcall **)(const struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v19 < 0 )
  {
    memset_0(v49, 0, sizeof(v49));
    StringCchPrintfW(v49, 0x200u, L"Call to AddOpcStream failed with HResult 0x%X.", (unsigned int)v19);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v48,
      0x65u,
      v19,
      (struct win_musl::TStringEllipseBase *)v49);
    throw (SplException::THResultException *)v48;
  }
  if ( (*(_DWORD *)(v11 + 44))-- == 1 )
    *(_DWORD *)(v11 + 40) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v11);
  *((_BYTE *)this + 152) = 1;
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v41);
  win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v43);
}

```

## disassembly

```asm
0x180028cf0  mov     rax, rsp
0x180028cf3  push    rbp
0x180028cf4  push    rsi
0x180028cf5  push    rdi
0x180028cf6  push    r12
0x180028cf8  push    r13
0x180028cfa  push    r14
0x180028cfc  push    r15
0x180028cfe  lea     rbp, [rax-508h]
0x180028d05  sub     rsp, 5D0h
0x180028d0c  mov     [rbp+500h+var_558], 0FFFFFFFFFFFFFFFEh
0x180028d14  mov     [rax+18h], rbx
0x180028d18  mov     rax, cs:__security_cookie
0x180028d1f  xor     rax, rsp
0x180028d22  mov     [rbp+500h+var_40], rax
0x180028d29  mov     r12, rdx
0x180028d2c  mov     qword ptr [rsp+600h+var_5B0], rdx
0x180028d31  mov     rdi, rcx
0x180028d34  xor     r15d, r15d
0x180028d37  cmp     [rcx+98h], r15b
0x180028d3e  jz      short loc_180028D6A
0x180028d40  mov     rcx, [rbp+500h+var_40]
0x180028d47  xor     rcx, rsp; StackCookie
0x180028d4a  call    __security_check_cookie
0x180028d4f  mov     rbx, [rsp+600h+arg_10]
0x180028d57  add     rsp, 5D0h
0x180028d5e  pop     r15
0x180028d60  pop     r14
0x180028d62  pop     r13
0x180028d64  pop     r12
0x180028d66  pop     rdi
0x180028d67  pop     rsi
0x180028d68  pop     rbp
0x180028d69  retn
0x180028d6a  lea     rax, WPP_GLOBAL_Control
0x180028d71  mov     r10, cs:WPP_GLOBAL_Control
0x180028d78  cmp     r10, rax
0x180028d7b  jz      short loc_180028D88
0x180028d7d  test    byte ptr [r10+44h], 4
0x180028d82  jnz     loc_180029250
0x180028d88  mov     [rbp+500h+var_560], r15
0x180028d8c  mov     [rsp+600h+var_588], rdi
0x180028d91  mov     rsi, [rdi+8]
0x180028d95  mov     [rbp+500h+var_568], rsi
0x180028d99  test    rsi, rsi
0x180028d9c  jz      short loc_180028DE1
0x180028d9e  mov     eax, 1
0x180028da3  lock xadd [rsi+8], eax
0x180028da8  inc     eax
0x180028daa  cmp     eax, 1
0x180028dad  jz      short loc_180028DDB
0x180028daf  mov     [rbp+500h+var_560], rdi
0x180028db3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028dba  mov     ecx, 60h ; '`'; unsigned __int64
0x180028dbf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028dc4  mov     rbx, rax
0x180028dc7  test    rax, rax
0x180028dca  jnz     loc_18002902C
0x180028dd0  mov     ecx, 8007000Eh; this
0x180028dd5  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x180028ddb  lock inc dword ptr [rsi+0Ch]
0x180028ddf  jmp     short loc_180028DAF
0x180028de1  lea     rcx, [rsp+600h+var_588]
0x180028de6  call    ??$close@VCallingThread@win_musl@@@close_delete@win_scope@@SAXPEAPEAVCallingThread@win_musl@@@Z; win_scope::close_delete::close<win_musl::CallingThread>(win_musl::CallingThread * *)
0x180028deb  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x180028df1  cmp     qword ptr [rsp+600h+var_5C8+8], r13
0x180028df6  jz      short loc_180028E0B
0x180028df8  lea     rcx, [rsp+600h+var_5C8+8]
0x180028dfd  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180028e02  xorps   xmm0, xmm0
0x180028e05  movdqu  [rsp+600h+var_5C8+8], xmm0
0x180028e0b  mov     [rbp+500h+var_570], r13
0x180028e0f  mov     qword ptr [rsp+600h+var_5B0], rbx
0x180028e14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028e1b  mov     ecx, 18h; unsigned __int64
0x180028e20  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028e25  mov     rdx, rax
0x180028e28  test    rax, rax
0x180028e2b  jz      loc_18002931C
0x180028e31  mov     qword ptr [rax+8], 0
0x180028e39  lea     rax, ??_7?$counted_strong_weak@PEAVZipConsumptionByteCollection@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionByteCollection *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x180028e40  mov     [rdx], rax
0x180028e43  mov     [rdx+10h], rbx
0x180028e47  mov     [rbp+500h+var_578], rdx
0x180028e4b  mov     r9d, 1
0x180028e51  mov     ecx, r9d
0x180028e54  lock xadd [rdx+8], ecx
0x180028e59  add     ecx, r9d
0x180028e5c  cmp     ecx, r9d
0x180028e5f  jz      loc_180028FB6
0x180028e65  mov     [rbp+500h+var_570], rbx
0x180028e69  xorps   xmm0, xmm0
0x180028e6c  movdqu  [rsp+600h+var_5A0+8], xmm0
0x180028e72  mov     eax, r9d
0x180028e75  lock xadd [rdx+8], eax
0x180028e7a  add     eax, r9d
0x180028e7d  cmp     eax, r9d
0x180028e80  jz      loc_180028FC0
0x180028e86  mov     qword ptr [rsp+600h+var_5A0+8], rdx
0x180028e8b  mov     [rsp+600h+var_590], rbx
0x180028e90  lea     rdx, [rsp+600h+var_5A0+8]
0x180028e95  lea     rcx, [rsp+600h+var_588]
0x180028e9a  call    ??$CreateInstanceFromInner@UIByteCollection@@V?$scope@PEAVZipConsumptionByteCollection@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVByteCollection@0@V?$scope@PEAVZipConsumptionByteCollection@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IByteCollection,win_scope::scope<win_musl::consumption::ZipConsumptionByteCollection *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_musl::consumption::ZipConsumptionByteCollection *,win_scope::const_policies<win_scope::shared_policies>>)
0x180028e9f  nop
0x180028ea0  mov     rbx, [rdi+70h]
0x180028ea4  mov     r15d, [rdi+38h]
0x180028ea8  mov     qword ptr [rsp+600h+var_5A0+8], rbx
0x180028ead  mov     rcx, rbx; lpCriticalSection
0x180028eb0  call    cs:__imp_EnterCriticalSection
0x180028eb6  mov     ecx, [rbx+2Ch]
0x180028eb9  lea     eax, [rcx+1]
0x180028ebc  mov     [rbx+2Ch], eax
0x180028ebf  test    ecx, ecx
0x180028ec1  jnz     short loc_180028ECC
0x180028ec3  call    cs:__imp_GetCurrentThreadId
0x180028ec9  mov     [rbx+28h], eax
0x180028ecc  mov     cl, [rbx+50h]; this
0x180028ecf  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180028ed4  cmp     [rbx+40h], r13
0x180028ed8  jz      loc_180028FCA
0x180028ede  cmp     [rbx+48h], r13
0x180028ee2  jz      loc_180028FCA
0x180028ee8  cmp     cs:dword_1801C4E30, 0FFFFFFFFh
0x180028eef  jz      loc_180028FCA
0x180028ef5  mov     rax, [rbx+48h]
0x180028ef9  mov     rsi, [rax+10h]
0x180028efd  mov     rax, [rsi]
0x180028f00  mov     r14, [rax+30h]
0x180028f04  lea     rdx, [rsp+600h+var_5B0]
0x180028f09  lea     rcx, [rsp+600h+var_588]
0x180028f0e  call    ?GetInterface@?$StartSendBase@UIByteSender@@@win_dox@@QEBA?AV?$scope@PEAUIByteSender@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::StartSendBase<IByteSender>::GetInterface(void)
0x180028f13  nop
0x180028f14  mov     rcx, [rax]
0x180028f17  lea     rdx, [rdi+18h]
0x180028f1b  cmp     qword ptr [rdi+30h], 8
0x180028f20  jb      short loc_180028F25
0x180028f22  mov     rdx, [rdx]
0x180028f25  movups  xmm0, xmmword ptr [rdi+40h]
0x180028f29  movdqu  [rsp+600h+var_5C8+8], xmm0
0x180028f2f  mov     qword ptr [rsp+600h+var_5D8], r12
0x180028f34  mov     qword ptr [rsp+600h+var_5E0], rcx
0x180028f39  lea     r9, [rsp+600h+var_5C8+8]
0x180028f3e  mov     r8d, r15d
0x180028f41  mov     rcx, rsi
0x180028f44  mov     rax, r14
0x180028f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f4c  mov     esi, eax
0x180028f4e  mov     rcx, qword ptr [rsp+600h+var_5B0]
0x180028f53  test    rcx, rcx
0x180028f56  jz      short loc_180028F65
0x180028f58  mov     rdx, [rcx]
0x180028f5b  mov     rax, [rdx+10h]
0x180028f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f64  nop
0x180028f65  test    esi, esi
0x180028f67  js      loc_1800292AD
0x180028f6d  sub     dword ptr [rbx+2Ch], 1
0x180028f71  jnz     short loc_180028F77
0x180028f73  mov     [rbx+28h], r13d
0x180028f77  mov     rcx, rbx; lpCriticalSection
0x180028f7a  call    cs:__imp_LeaveCriticalSection
0x180028f80  mov     byte ptr [rdi+98h], 1
0x180028f87  mov     rcx, [rbp+500h+var_580]
0x180028f8b  test    rcx, rcx
0x180028f8e  jz      short loc_180028F9D
0x180028f90  mov     rax, [rcx]
0x180028f93  mov     rax, [rax+10h]
0x180028f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f9c  nop
0x180028f9d  lea     rcx, [rbp+500h+var_578]
0x180028fa1  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180028fa6  nop
0x180028fa7  lea     rcx, [rbp+500h+var_568]
0x180028fab  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180028fb0  nop
0x180028fb1  jmp     loc_180028D40
0x180028fb6  lock add [rdx+0Ch], r9d
0x180028fbb  jmp     loc_180028E65
0x180028fc0  lock add [rdx+0Ch], r9d
0x180028fc5  jmp     loc_180028E86
0x180028fca  lea     rax, aZipdeinterleav; "ZipDeinterleaverState::AddOpcStream() i"...
0x180028fd1  mov     qword ptr [rsp+600h+var_5D8], rax
0x180028fd6  mov     [rsp+600h+var_5E0], 8000FFFFh
0x180028fde  mov     r9d, 400h
0x180028fe4  mov     r8d, 7Ch ; '|'
0x180028fea  lea     rdx, word_180139126
0x180028ff1  lea     rcx, aNoFilename; "(no filename)"
0x180028ff8  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x180028ffd  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x180029004  lea     rcx, [rbp+500h+var_550]
0x180029008  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18002900d  nop
0x18002900e  lea     rdx, [rbp+500h+var_550]
0x180029012  lea     rcx, [rbp+500h+pExceptionObject]
0x180029016  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x18002901b  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x180029022  lea     rcx, [rbp+500h+pExceptionObject]; pExceptionObject
0x180029026  call    _CxxThrowException_0
0x18002902c  mov     [rsp+600h+var_588], rbx
0x180029031  lea     rax, [rsp+600h+var_5C8+8]
0x180029036  mov     [rbp+500h+var_578], rax
0x18002903a  xorps   xmm0, xmm0
0x18002903d  movdqu  [rsp+600h+var_5C8+8], xmm0
0x180029043  mov     r8d, 1
0x180029049  mov     eax, r8d
0x18002904c  lock xadd [rsi+8], eax
0x180029051  add     eax, r8d
0x180029054  cmp     eax, r8d
0x180029057  jz      loc_1800291E9
0x18002905d  mov     qword ptr [rsp+600h+var_5C8+8], rsi
0x180029062  mov     [rsp+600h+var_5B8], rdi
0x180029067  lea     rax, [rsp+600h+var_5C8+8]
0x18002906c  mov     [rbp+500h+var_578], rax
0x180029070  movdqu  [rsp+600h+var_5B0+8], xmm0
0x180029076  mov     rcx, [rdi+68h]
0x18002907a  test    rcx, rcx
0x18002907d  jz      short loc_1800290A1
0x18002907f  mov     rdx, [rdi+70h]
0x180029083  mov     eax, r8d
0x180029086  lock xadd [rcx+8], eax
0x18002908b  add     eax, r8d
0x18002908e  cmp     eax, r8d
0x180029091  jz      loc_1800291F3
0x180029097  mov     qword ptr [rsp+600h+var_5B0+8], rcx
0x18002909c  mov     qword ptr [rsp+600h+var_5A0], rdx
0x1800290a1  lea     rax, [rsp+600h+var_5B0+8]
0x1800290a6  mov     qword ptr [rsp+600h+var_5A0+8], rax
0x1800290ab  lea     r13, [rdi+10h]
0x1800290af  mov     [rbx], r15
0x1800290b2  mov     [rbx+8], r15
0x1800290b6  mov     rcx, qword ptr [rsp+600h+var_5B0+8]
0x1800290bb  test    rcx, rcx
0x1800290be  jz      short loc_1800290E0
0x1800290c0  mov     rdx, qword ptr [rsp+600h+var_5A0]
0x1800290c5  mov     eax, r8d
0x1800290c8  lock xadd [rcx+8], eax
0x1800290cd  add     eax, r8d
0x1800290d0  cmp     eax, r8d
0x1800290d3  jz      loc_1800291FD
0x1800290d9  mov     [rbx], rcx
0x1800290dc  mov     [rbx+8], rdx
0x1800290e0  mov     [rbx+10h], r15
0x1800290e4  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x1800290ec  mov     [rbx+20h], r15
0x1800290f0  mov     [rbx+28h], r15
0x1800290f4  mov     rcx, qword ptr [rsp+600h+var_5C8+8]
0x1800290f9  test    rcx, rcx
0x1800290fc  jz      short loc_18002911F
0x1800290fe  mov     rdx, [rsp+600h+var_5B8]
0x180029103  mov     eax, r8d
0x180029106  lock xadd [rcx+8], eax
0x18002910b  add     eax, r8d
0x18002910e  cmp     eax, r8d
0x180029111  jz      loc_180029207
0x180029117  mov     [rbx+20h], rcx
0x18002911b  mov     [rbx+28h], rdx
0x18002911f  lea     rsi, [rbx+30h]
0x180029123  mov     qword ptr [rsi+20h], 7
0x18002912b  lea     r14, [rsi+8]
0x18002912f  mov     [rsi+18h], r15
0x180029133  mov     [r14], r15w
0x180029137  mov     r15, [r13+18h]
0x18002913b  cmp     rsi, r13
0x18002913e  jz      loc_180029285
0x180029144  mov     rax, 7FFFFFFFFFFFFFFEh
0x18002914e  cmp     r15, rax
0x180029151  ja      loc_1800292A3
0x180029157  cmp     [rsi+20h], r15
0x18002915b  jb      loc_180029211
0x180029161  test    r15, r15
0x180029164  jz      loc_180029236
0x18002916a  lea     r8, [r13+8]
0x18002916e  cmp     qword ptr [r13+20h], 8
0x180029173  jb      short loc_180029178
0x180029175  mov     r8, [r8]; Source
0x180029178  mov     rdx, [rsi+20h]
0x18002917c  cmp     rdx, 8
0x180029180  jb      loc_18002922E
0x180029186  mov     rcx, [r14]; Destination
0x180029189  lea     r12, [r15+r15]
0x18002918d  add     rdx, rdx; DestinationSize
0x180029190  mov     r9, r12; SourceSize
0x180029193  call    cs:__imp_memcpy_s
0x180029199  cmp     qword ptr [rsi+20h], 8
0x18002919e  jb      short loc_1800291A3
0x1800291a0  mov     r14, [r14]
0x1800291a3  mov     [rsi+18h], r15
0x1800291a7  xor     r13d, r13d
0x1800291aa  mov     [r12+r14], r13w
0x1800291af  mov     r12, qword ptr [rsp+600h+var_5B0]
0x1800291b4  mov     [rbx+58h], r13b
0x1800291b8  cmp     qword ptr [rsp+600h+var_5A0], r13
0x1800291bd  jz      short loc_1800291D9
0x1800291bf  cmp     qword ptr [rsp+600h+var_5B0+8], r13
0x1800291c4  jz      short loc_1800291D9
0x1800291c6  lea     rcx, [rsp+600h+var_5B0+8]
0x1800291cb  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800291d0  xorps   xmm0, xmm0
0x1800291d3  movdqu  [rsp+600h+var_5B0+8], xmm0
0x1800291d9  cmp     [rsp+600h+var_5B8], r13
  ... truncated ...
```
