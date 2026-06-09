# win_musl::consumption::ZipConsumptionPart::AddZipFileSender(win_musl::consumption::PartType::Enum,uint,__MIDL___MIDL_itf_opc2Eio_0000_0000_0002,win_musl::OptionalValue<__MIDL___MIDL_itf_dox2Ebase_0000_0000_0002,unsigned __int64> const &,win_scope::scope<win_musl::ZipFileSender *,win_scope::const_policies<win_scope::shared_policies>>,__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)

- ea: `0x18001486c`
- end: `0x1800150b0`
- name: `?AddZipFileSender@ZipConsumptionPart@consumption@win_musl@@QEAAXW4Enum@PartType@23@IW4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@AEBV?$OptionalValue@U__MIDL___MIDL_itf_dox2Ebase_0000_0000_0002@@_K@3@V?$scope@PEAVZipFileSender@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z`
- size: `2116`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010780`

## callees

- `0x18000531c`
- `0x18000f9a0`
- `0x180011b14`
- `0x18001486c`
- `0x18001568c`
- `0x180017320`
- `0x180023e64`
- `0x1800240dc`
- `0x180028cf0`
- `0x1800298a0`
- `0x18002db70`
- `0x180031eb0`
- `0x18004ea94`
- `0x180060c90`
- `0x180084010`
- `0x18009c7bc`
- `0x1800cd6fc`
- `0x1800d0848`
- `0x18010b61c`
- `0x18011394c`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800148ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800148ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014b66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014b66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800148d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800148d9`

## string_xrefs

- `0x180015007`: `During streamed consumption found invalid piece in part. %{part}`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall win_musl::consumption::ZipConsumptionPart::AddZipFileSender(
        struct _RTL_CRITICAL_SECTION *this,
        int a2,
        int a3,
        unsigned int a4,
        _OWORD *a5,
        _QWORD *a6,
        struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *a7)
{
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  bool v12; // dl
  win_dox *DebugInfo_high; // rcx
  _QWORD *v14; // rax
  int v15; // edx
  const char *v16; // r8
  unsigned int v17; // r9d
  __int64 v18; // rsi
  volatile signed __int32 *v19; // r15
  unsigned __int32 v20; // r8d
  char v21; // cl
  bool v22; // r12
  __int64 *v23; // rcx
  __int64 *v24; // rax
  __m128i *v25; // rdx
  __m128i *v26; // rcx
  __m128i *v27; // rax
  __m128i *v28; // r9
  __int8 v29; // r10
  __m128i *v30; // rbx
  __m128i v31; // xmm0
  _QWORD *v33; // rbx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rcx
  __int64 v37; // rdx
  void *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // r8
  _QWORD *v41; // rax
  int v42; // edx
  const char *v43; // r8
  unsigned int v44; // r9d
  _QWORD *v45; // r15
  __int64 v46; // rcx
  __int64 v47; // rcx
  __m128i v48; // xmm0
  __int64 v49; // rbx
  __int64 v50; // r12
  __int64 v51; // rax
  int v52; // edx
  __int64 v53; // r8
  HANDLE *p_LockSemaphore; // r9
  __int64 *v55; // rdx
  __int64 *v56; // rax
  __int64 v57; // rbx
  win_musl::Formatter *v58; // rax
  struct win_musl::TStringEllipseBase *v59; // rax
  __int128 v60; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v61; // [rsp+58h] [rbp-B0h] BYREF
  __m128i v62; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v63; // [rsp+78h] [rbp-90h] BYREF
  __m128i v64; // [rsp+88h] [rbp-80h] BYREF
  __int128 v65; // [rsp+98h] [rbp-70h] BYREF
  struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *v66; // [rsp+A8h] [rbp-60h]
  _QWORD *v67; // [rsp+B0h] [rbp-58h]
  __int64 v68; // [rsp+B8h] [rbp-50h]
  _QWORD *v69; // [rsp+C0h] [rbp-48h]
  struct _RTL_CRITICAL_SECTION *v70; // [rsp+C8h] [rbp-40h]
  _QWORD *v71; // [rsp+D0h] [rbp-38h]
  unsigned __int32 v72; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v73; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v74[40]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v76[160]; // [rsp+1C8h] [rbp+C0h] BYREF

  v68 = -2;
  v67 = a6;
  v69 = a6;
  v66 = a7;
  v11 = this + 4;
  v70 = this + 4;
  EnterCriticalSection(this + 4);
  DebugInfo_high = (win_dox *)HIDWORD(v11[1].DebugInfo);
  HIDWORD(v11[1].DebugInfo) = (_DWORD)DebugInfo_high + 1;
  if ( !(_DWORD)DebugInfo_high )
    LODWORD(v11[1].DebugInfo) = GetCurrentThreadId();
  LOBYTE(DebugInfo_high) = this[5].OwningThread;
  win_dox::ThrowIfFailed(DebugInfo_high, v12);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
  {
    v51 = win_musl::StringOfCompressionOptions(a4);
    p_LockSemaphore = &this->LockSemaphore;
    if ( *(_QWORD *)&this[1].LockCount >= 8u )
      p_LockSemaphore = (HANDLE *)*p_LockSemaphore;
    WPP_SF_SDS(*(_QWORD *)(v53 + 56), v52, v53, (_DWORD)p_LockSemaphore, a3, v51);
  }
  if ( LODWORD(this[1].OwningThread) == -1 && a4 != -1 )
    LODWORD(this[1].OwningThread) = a4;
  *(_OWORD *)&this[1].LockSemaphore = *a5;
  v14 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = (__int64)v14;
  if ( !v14 )
    SplException::RealThrowFromHR((SplException *)0x8007000ELL, v15, v16, v17);
  v71 = v14;
  *(_QWORD *)&v65 = &v63;
  v63 = 0;
  v36 = *a6;
  if ( *a6 )
  {
    v37 = a6[1];
    if ( _InterlockedIncrement((volatile signed __int32 *)(v36 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v36 + 12), 1u);
    *(_QWORD *)&v63 = v36;
    *((_QWORD *)&v63 + 1) = v37;
  }
  v64.m128i_i64[0] = (__int64)&v63;
  v61 = 0;
  v62.m128i_i64[0] = (__int64)this;
  if ( this )
  {
    v46 = *(_QWORD *)&this->LockCount;
    *(_QWORD *)&v61 = v46;
    if ( !v46 )
      goto LABEL_81;
    if ( _InterlockedIncrement((volatile signed __int32 *)(v46 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v46 + 12), 1u);
    *((_QWORD *)&v61 + 1) = this;
    if ( !(_QWORD)v61 )
    {
LABEL_81:
      win_scope::close_delete::close<win_musl::CallingThread>(&v62);
      win_scope::report_policy_throw::report_init_failure();
    }
  }
  *(_QWORD *)&v65 = &v61;
  v14[1] = 0;
  *v14 = &win_scope::intrusive_shared_weak<win_scope::scope<win_dox::OpcRelationshipImplementation *,win_scope::const_policies<win_scope::shared_policies>>>::`vftable';
  v38 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v38 )
  {
    *((_QWORD *)v38 + 1) = 0;
    *(_QWORD *)v38 = &win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
    *((_QWORD *)v38 + 2) = v18;
    *(_QWORD *)(v18 + 8) = v38;
    _InterlockedAdd((volatile signed __int32 *)v38 + 3, 1u);
  }
  else
  {
    *(_QWORD *)(v18 + 8) = 0;
  }
  *(_QWORD *)v18 = &win_musl::consumption::ZipConsumptionPart::Piece::`vftable';
  *(_DWORD *)(v18 + 16) = a2;
  *(_OWORD *)(v18 + 24) = *(_OWORD *)&this[1].LockSemaphore;
  *(_DWORD *)(v18 + 40) = a3;
  *(_QWORD *)(v18 + 48) = 0;
  *(_QWORD *)(v18 + 56) = 0;
  v39 = v63;
  if ( (_QWORD)v63 )
  {
    v40 = *((_QWORD *)&v63 + 1);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v63 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v39 + 12), 1u);
    *(_QWORD *)(v18 + 48) = v39;
    *(_QWORD *)(v18 + 56) = v40;
  }
  *(_BYTE *)(v18 + 64) = 0;
  *(_QWORD *)(v18 + 72) = 0;
  *(_QWORD *)(v18 + 80) = 0;
  v41 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v45 = v41;
  if ( !v41 )
    SplException::RealThrowFromHR((SplException *)0x8007000ELL, v42, v43, v44);
  v62.m128i_i64[0] = (__int64)v41;
  v60 = 0;
  v49 = v61;
  if ( (_QWORD)v61 )
  {
    v50 = *((_QWORD *)&v61 + 1);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v61 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v49 + 12), 1u);
    *(_QWORD *)&v60 = v49;
    *((_QWORD *)&v60 + 1) = v50;
  }
  else
  {
    v50 = *((_QWORD *)&v60 + 1);
    v49 = v60;
  }
  win_scope::intrusive_shared_weak<win_scope::scope<win_musl::consumption::PieceReceiver *,win_scope::const_policies<win_scope::shared_policies>>>::intrusive_shared_weak<win_scope::scope<win_musl::consumption::PieceReceiver *,win_scope::const_policies<win_scope::shared_policies>>>(v41);
  *v45 = &win_musl::consumption::PieceReceiver::`vftable';
  v45[2] = 0;
  v45[3] = 0;
  if ( v49 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v49 + 12));
    v45[2] = v49;
    v45[3] = v50;
  }
  *((_DWORD *)v45 + 8) = a3;
  v45[6] = 0;
  v45[5] = &win_dox::OpcRelationshipCollection::`vftable';
  if ( v49 && v50 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v60);
  v62.m128i_i64[0] = (__int64)v45;
  v47 = v45[1];
  if ( !v47 )
  {
    win_scope::close_delete::close<win_musl::CallingThread>(&v62);
    win_scope::report_policy_throw::report_init_failure();
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(v47 + 8)) == 1 )
    _InterlockedAdd((volatile signed __int32 *)(v47 + 12), 1u);
  v62 = *(__m128i *)(v18 + 72);
  v48 = v62;
  *(_QWORD *)(v18 + 72) = v47;
  *(_QWORD *)(v18 + 80) = v45;
  if ( v48.m128i_i64[0] && _mm_srli_si128(v48, 8).m128i_u64[0] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v62);
  if ( *((_QWORD *)&v61 + 1) && (_QWORD)v61 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v61);
    v61 = 0;
  }
  if ( *((_QWORD *)&v63 + 1) && (_QWORD)v63 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v63);
    v63 = 0;
  }
  v65 = 0;
  v62.m128i_i64[0] = v18;
  v19 = *(volatile signed __int32 **)(v18 + 8);
  *(_QWORD *)&v65 = v19;
  if ( !v19 )
  {
    win_scope::close_delete::close<win_musl::CallingThread>(&v62);
    win_scope::report_policy_throw::report_init_failure();
  }
  if ( _InterlockedIncrement(v19 + 2) == 1 )
    _InterlockedAdd(v19 + 3, 1u);
  *((_QWORD *)&v65 + 1) = v18;
  v20 = *(_DWORD *)(v18 + 40);
  v21 = BYTE4(this[3].DebugInfo);
  if ( (*(_DWORD *)(v18 + 16) & 0xFFFFFFFD) != 0 )
  {
    v22 = 0;
    if ( v21 && v20 > LODWORD(this[3].DebugInfo) )
    {
LABEL_120:
      if ( !*(_BYTE *)(this[2].SpinCount + 57) )
      {
        std::wstring::wstring(&v72, L"During streamed consumption found invalid piece in part. %{part}");
        v57 = win_musl::Formatter::Formatter(pExceptionObject, &v72);
        std::wstring::wstring(v74, L"part");
        v58 = (win_musl::Formatter *)win_musl::Formatter::insert<std::wstring>(v57, v74, &this->OwningThread);
        v59 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v58);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)v76,
          0xD7u,
          0x80510016,
          v59);
        throw (SplException::THResultException *)v76;
      }
      BYTE1(this[3].SpinCount) = 1;
      goto LABEL_42;
    }
  }
  else
  {
    v22 = v21 != 0;
    v23 = *(__int64 **)&this[2].LockCount;
    v24 = (__int64 *)*v23;
    if ( (__int64 *)*v23 != v23 )
    {
      if ( *((_BYTE *)v23 + 49) )
      {
        v24 = (__int64 *)v23[2];
      }
      else if ( *((_BYTE *)v24 + 49) )
      {
        v55 = (__int64 *)v23[1];
        if ( !*((_BYTE *)v55 + 49) )
        {
          v56 = *(__int64 **)&this[2].LockCount;
          do
          {
            if ( v56 != (__int64 *)*v55 )
              break;
            v56 = v55;
            v23 = v55;
            v55 = (__int64 *)v55[1];
          }
          while ( !*((_BYTE *)v55 + 49) );
        }
        v24 = v23;
        if ( !*((_BYTE *)v23 + 49) )
          v24 = v55;
      }
      else
      {
        while ( !*(_BYTE *)(v24[2] + 49) )
          v24 = (__int64 *)v24[2];
      }
      if ( *(_DWORD *)(v24[5] + 40) > v20 )
        v22 = 1;
    }
    BYTE4(this[3].DebugInfo) = 1;
    LODWORD(this[3].DebugInfo) = v20;
  }
  v25 = *(__m128i **)&this[2].LockCount;
  v26 = (__m128i *)v25->m128i_i64[1];
  v27 = v26;
  v28 = v25;
  v29 = v26[3].m128i_i8[1];
  if ( !v29 )
  {
    do
    {
      if ( v27[1].m128i_i32[2] < v20 )
      {
        v27 = (__m128i *)v27[1].m128i_i64[0];
      }
      else
      {
        v28 = v27;
        v27 = (__m128i *)v27->m128i_i64[0];
      }
    }
    while ( !v27[3].m128i_i8[1] );
    if ( v28 != v25 && v20 >= v28[1].m128i_i32[2] )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xC7u,
        0x80510015,
        (struct win_musl::TStringEllipseBase *)L"The same piece number existed twice in the same part");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  v30 = *(__m128i **)&this[2].LockCount;
  if ( v29 )
    goto LABEL_34;
  do
  {
    if ( v26[1].m128i_i32[2] < v20 )
    {
      v26 = (__m128i *)v26[1].m128i_i64[0];
    }
    else
    {
      v30 = v26;
      v26 = (__m128i *)v26->m128i_i64[0];
    }
  }
  while ( !v26[3].m128i_i8[1] );
  if ( v30 == v25 || v20 < v30[1].m128i_i32[2] )
  {
LABEL_34:
    v64 = 0;
    v72 = v20;
    v73 = 0;
    v30 = *(__m128i **)std::_Tree<std::_Tmap_traits<unsigned int,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>>,0>>::insert(
                         &this[2],
                         &v60,
                         v30,
                         &v72);
    if ( *((_QWORD *)&v73 + 1) )
    {
      if ( (_QWORD)v73 )
        win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v73);
    }
  }
  v64 = 0;
  if ( _InterlockedIncrement(v19 + 2) == 1 )
    _InterlockedAdd(v19 + 3, 1u);
  v64.m128i_i64[0] = (__int64)v19;
  v64.m128i_i64[1] = v18;
  v31 = v30[2];
  v30[2] = _mm_load_si128(&v64);
  v64 = v31;
  if ( v31.m128i_i64[0] && _mm_srli_si128(v31, 8).m128i_u64[0] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v64);
  if ( v22 )
    goto LABEL_120;
LABEL_42:
  if ( *(_DWORD *)(v18 + 16) )
  {
    v60 = 0;
    win_scope::counted_strong_weak_base::AddRef((win_scope::counted_strong_weak_base *)v19);
    *(_QWORD *)&v60 = v19;
    *((_QWORD *)&v60 + 1) = v18;
    win_musl::consumption::ZipConsumptionPart::NotifyAboutNewPiece(this, &v60, v34, v35);
  }
  if ( !*(_BYTE *)(this[2].SpinCount + 57) || !*(_DWORD *)(v18 + 16) )
    win_musl::consumption::ZipConsumptionPart::AddPartToReceiver((win_musl::consumption::ZipConsumptionPart *)this, v66);
  if ( v18 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v65);
  if ( v11 )
  {
    if ( HIDWORD(v11[1].DebugInfo)-- == 1 )
      LODWORD(v11[1].DebugInfo) = 0;
    LeaveCriticalSection(v11);
  }
  v33 = v67;
  if ( *v67 )
  {
    if ( v67[1] )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v67);
      *v33 = 0;
      v33[1] = 0;
    }
  }
}

```

## disassembly

```asm
0x18001486c  mov     rax, rsp
0x18001486f  push    rbp
0x180014870  push    rsi
0x180014871  push    rdi
0x180014872  push    r12
0x180014874  push    r13
0x180014876  push    r14
0x180014878  push    r15
0x18001487a  lea     rbp, [rax-1A8h]
0x180014881  sub     rsp, 270h
0x180014888  mov     [rbp+1A0h+var_1F0], 0FFFFFFFFFFFFFFFEh
0x180014890  mov     [rax+10h], rbx
0x180014894  mov     rax, cs:__security_cookie
0x18001489b  xor     rax, rsp
0x18001489e  mov     [rbp+1A0h+var_40], rax
0x1800148a5  mov     ebx, r9d
0x1800148a8  mov     r13d, r8d
0x1800148ab  mov     r15d, edx
0x1800148ae  mov     r14, rcx
0x1800148b1  mov     r12, [rbp+1A0h+arg_28]
0x1800148b8  mov     [rbp+1A0h+var_1F8], r12
0x1800148bc  mov     [rbp+1A0h+var_1E8], r12
0x1800148c0  mov     rax, [rbp+1A0h+arg_30]
0x1800148c7  mov     [rbp+1A0h+var_200], rax
0x1800148cb  lea     rdi, [rcx+0A0h]
0x1800148d2  mov     [rbp+1A0h+var_1E0], rdi
0x1800148d6  mov     rcx, rdi; lpCriticalSection
0x1800148d9  call    cs:__imp_EnterCriticalSection
0x1800148df  mov     ecx, [rdi+2Ch]
0x1800148e2  lea     eax, [rcx+1]
0x1800148e5  mov     [rdi+2Ch], eax
0x1800148e8  test    ecx, ecx
0x1800148ea  jnz     short loc_1800148F5
0x1800148ec  call    cs:__imp_GetCurrentThreadId
0x1800148f2  mov     [rdi+28h], eax
0x1800148f5  mov     cl, [r14+0D8h]; this
0x1800148fc  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180014901  lea     rax, WPP_GLOBAL_Control
0x180014908  mov     r8, cs:WPP_GLOBAL_Control
0x18001490f  cmp     r8, rax
0x180014912  jz      short loc_18001491F
0x180014914  test    byte ptr [r8+44h], 4
0x180014919  jnz     loc_180014F61
0x18001491f  cmp     dword ptr [r14+38h], 0FFFFFFFFh
0x180014924  jnz     short loc_18001492F
0x180014926  cmp     ebx, 0FFFFFFFFh
0x180014929  jz      short loc_18001492F
0x18001492b  mov     [r14+38h], ebx
0x18001492f  mov     rax, [rbp+1A0h+arg_20]
0x180014936  movups  xmm0, xmmword ptr [rax]
0x180014939  movdqu  xmmword ptr [r14+40h], xmm0
0x18001493f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014946  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001494b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014950  mov     rsi, rax
0x180014953  xor     ebx, ebx
0x180014955  test    rax, rax
0x180014958  jnz     loc_180014C83
0x18001495e  mov     ecx, 8007000Eh; this
0x180014963  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x180014969  cmp     qword ptr [rsp+2A0h+var_238+8], r13
0x18001496e  jz      short loc_180014983
0x180014970  lea     rcx, [rsp+2A0h+var_238+8]
0x180014975  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18001497a  xorps   xmm0, xmm0
0x18001497d  movdqu  xmmword ptr [rsp+2A0h+var_238+8], xmm0
0x180014983  xorps   xmm0, xmm0
0x180014986  movdqu  [rbp+1A0h+var_210], xmm0
0x18001498b  mov     qword ptr [rsp+2A0h+var_248+8], rsi
0x180014990  mov     r15, [rsi+8]
0x180014994  mov     qword ptr [rbp+1A0h+var_210], r15
0x180014998  test    r15, r15
0x18001499b  jz      loc_1800150A0
0x1800149a1  mov     r11d, 1
0x1800149a7  mov     eax, r11d
0x1800149aa  lock xadd [r15+8], eax
0x1800149b0  add     eax, r11d
0x1800149b3  cmp     eax, r11d
0x1800149b6  jz      loc_180014BB5
0x1800149bc  mov     qword ptr [rbp+1A0h+var_210+8], rsi
0x1800149c0  mov     r8d, [rsi+28h]
0x1800149c4  test    dword ptr [rsi+10h], 0FFFFFFFDh
0x1800149cb  setz    al
0x1800149ce  mov     cl, [r14+7Ch]
0x1800149d2  test    al, al
0x1800149d4  jz      loc_180014C69
0x1800149da  test    cl, cl
0x1800149dc  setnz   r12b
0x1800149e0  mov     rcx, [r14+58h]
0x1800149e4  mov     rax, [rcx]
0x1800149e7  cmp     rax, rcx
0x1800149ea  jz      short loc_180014A0A
0x1800149ec  cmp     [rcx+31h], r13b
0x1800149f0  jz      loc_180014FA8
0x1800149f6  mov     rax, [rcx+10h]
0x1800149fa  mov     rcx, [rax+28h]
0x1800149fe  movzx   r12d, r12b
0x180014a02  cmp     [rcx+28h], r8d
0x180014a06  cmova   r12d, r11d
0x180014a0a  mov     [r14+7Ch], r11b
0x180014a0e  mov     [r14+78h], r8d
0x180014a12  mov     rdx, [r14+58h]
0x180014a16  mov     rcx, [rdx+8]
0x180014a1a  mov     rax, rcx
0x180014a1d  mov     r9, rdx
0x180014a20  mov     r10b, [rcx+31h]
0x180014a24  test    r10b, r10b
0x180014a27  jnz     short loc_180014A48
0x180014a29  cmp     [rax+18h], r8d
0x180014a2d  jb      loc_180014C25
0x180014a33  mov     r9, rax
0x180014a36  mov     rax, [rax]
0x180014a39  cmp     [rax+31h], r13b
0x180014a3d  jz      short loc_180014A29
0x180014a3f  cmp     r9, rdx
0x180014a42  jnz     loc_180014BBF
0x180014a48  mov     rbx, rdx
0x180014a4b  test    r10b, r10b
0x180014a4e  jnz     short loc_180014A71
0x180014a50  cmp     [rcx+18h], r8d
0x180014a54  jb      loc_180014C2E
0x180014a5a  mov     rbx, rcx
0x180014a5d  mov     rcx, [rcx]
0x180014a60  cmp     [rcx+31h], r13b
0x180014a64  jz      short loc_180014A50
0x180014a66  cmp     rbx, rdx
0x180014a69  jz      short loc_180014A71
0x180014a6b  cmp     r8d, [rbx+18h]
0x180014a6f  jnb     short loc_180014AB6
0x180014a71  lea     rcx, [r14+50h]
0x180014a75  xorps   xmm0, xmm0
0x180014a78  movdqu  [rbp+1A0h+var_220], xmm0
0x180014a7d  mov     [rbp+1A0h+var_1D0], r8d
0x180014a81  movdqu  [rbp+1A0h+var_1C8], xmm0
0x180014a86  lea     r9, [rbp+1A0h+var_1D0]
0x180014a8a  mov     r8, rbx
0x180014a8d  lea     rdx, [rsp+2A0h+var_268+8]
0x180014a92  call    ?insert@?$_Tree@V?$_Tmap_traits@IV?$scope@PEAVPiece@ZipConsumptionPart@consumption@win_musl@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$scope@PEAVPiece@ZipConsumptionPart@consumption@win_musl@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@std@@@4@$0A@@std@@@std@@QEAA?AViterator@12@V312@AEBU?$pair@$$CBIV?$scope@PEAVPiece@ZipConsumptionPart@consumption@win_musl@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@2@@Z; std::_Tree<std::_Tmap_traits<uint,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,std::less<uint>,std::allocator<std::pair<uint const,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>>,0>>::insert(std::_Tree<std::_Tmap_traits<uint,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,std::less<uint>,std::allocator<std::pair<uint const,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>>,0>>::iterator,std::pair<uint const,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>> const &)
0x180014a97  mov     rbx, [rax]
0x180014a9a  cmp     qword ptr [rbp+1A0h+var_1C8+8], r13
0x180014a9e  jz      short loc_180014AB0
0x180014aa0  cmp     qword ptr [rbp+1A0h+var_1C8], r13
0x180014aa4  jz      short loc_180014AB0
0x180014aa6  lea     rcx, [rbp+1A0h+var_1C8]
0x180014aaa  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180014aaf  nop
0x180014ab0  mov     r11d, 1
0x180014ab6  xorps   xmm1, xmm1
0x180014ab9  movdqa  [rbp+1A0h+var_220], xmm1
0x180014abe  test    r15, r15
0x180014ac1  jz      short loc_180014AE5
0x180014ac3  mov     eax, r11d
0x180014ac6  lock xadd [r15+8], eax
0x180014acc  add     eax, r11d
0x180014acf  cmp     eax, r11d
0x180014ad2  jz      loc_180014C0D
0x180014ad8  mov     qword ptr [rbp+1A0h+var_220], r15
0x180014adc  mov     qword ptr [rbp+1A0h+var_220+8], rsi
0x180014ae0  movdqa  xmm1, [rbp+1A0h+var_220]
0x180014ae5  movups  xmm0, xmmword ptr [rbx+20h]
0x180014ae9  movdqu  xmmword ptr [rbx+20h], xmm1
0x180014aee  movdqa  [rbp+1A0h+var_220], xmm0
0x180014af3  movq    rax, xmm0
0x180014af8  test    rax, rax
0x180014afb  jz      short loc_180014B10
0x180014afd  psrldq  xmm0, 8
0x180014b02  movq    rax, xmm0
0x180014b07  test    rax, rax
0x180014b0a  jnz     loc_180014C17
0x180014b10  test    r12b, r12b
0x180014b13  jnz     loc_180014FF3
0x180014b19  cmp     [rsi+10h], r13d
0x180014b1d  jnz     loc_180014C37
0x180014b23  mov     rax, [r14+70h]
0x180014b27  cmp     [rax+39h], r13b
0x180014b2b  jz      short loc_180014B33
0x180014b2d  cmp     [rsi+10h], r13d
0x180014b31  jnz     short loc_180014B40
0x180014b33  mov     rdx, [rbp+1A0h+var_200]; struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *
0x180014b37  mov     rcx, r14; this
0x180014b3a  call    ?AddPartToReceiver@ZipConsumptionPart@consumption@win_musl@@AEAAXPEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z; win_musl::consumption::ZipConsumptionPart::AddPartToReceiver(__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)
0x180014b3f  nop
0x180014b40  test    r15, r15
0x180014b43  jz      short loc_180014B54
0x180014b45  test    rsi, rsi
0x180014b48  jz      short loc_180014B54
0x180014b4a  lea     rcx, [rbp+1A0h+var_210]
0x180014b4e  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180014b53  nop
0x180014b54  test    rdi, rdi
0x180014b57  jz      short loc_180014B6D
0x180014b59  add     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x180014b5d  jnz     short loc_180014B63
0x180014b5f  mov     [rdi+28h], r13d
0x180014b63  mov     rcx, rdi; lpCriticalSection
0x180014b66  call    cs:__imp_LeaveCriticalSection
0x180014b6c  nop
0x180014b6d  mov     rbx, [rbp+1A0h+var_1F8]
0x180014b71  cmp     [rbx], r13
0x180014b74  jz      short loc_180014B8B
0x180014b76  cmp     [rbx+8], r13
0x180014b7a  jz      short loc_180014B8B
0x180014b7c  mov     rcx, rbx
0x180014b7f  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180014b84  mov     [rbx], r13
0x180014b87  mov     [rbx+8], r13
0x180014b8b  mov     rcx, [rbp+1A0h+var_40]
0x180014b92  xor     rcx, rsp; StackCookie
0x180014b95  call    __security_check_cookie
0x180014b9a  mov     rbx, [rsp+2A0h+arg_8]
0x180014ba2  add     rsp, 270h
0x180014ba9  pop     r15
0x180014bab  pop     r14
0x180014bad  pop     r13
0x180014baf  pop     r12
0x180014bb1  pop     rdi
0x180014bb2  pop     rsi
0x180014bb3  pop     rbp
0x180014bb4  retn
0x180014bb5  lock add [r15+0Ch], r11d
0x180014bba  jmp     loc_1800149BC
0x180014bbf  cmp     r8d, [r9+18h]
0x180014bc3  jb      loc_180014A48
0x180014bc9  lea     rax, aTheSamePieceNu; "The same piece number existed twice in "...
0x180014bd0  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180014bd5  mov     [rsp+2A0h+var_278], 80510015h; unsigned int
0x180014bdd  mov     [rsp+2A0h+var_280], 0C7h; unsigned int
0x180014be5  lea     r9, word_180139126
0x180014bec  lea     r8, aNoFilename; "(no filename)"
0x180014bf3  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x180014bf7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180014bfc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180014c03  lea     rcx, [rbp+1A0h+pExceptionObject]; pExceptionObject
0x180014c07  call    _CxxThrowException_0
0x180014c0d  lock add [r15+0Ch], r11d
0x180014c12  jmp     loc_180014AD8
0x180014c17  lea     rcx, [rbp+1A0h+var_220]
0x180014c1b  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180014c20  jmp     loc_180014B10
0x180014c25  mov     rax, [rax+10h]
0x180014c29  jmp     loc_180014A39
0x180014c2e  mov     rcx, [rcx+10h]
0x180014c32  jmp     loc_180014A60
0x180014c37  xorps   xmm0, xmm0
0x180014c3a  movdqu  [rsp+2A0h+var_268+8], xmm0
0x180014c40  test    r15, r15
0x180014c43  jz      short loc_180014C57
0x180014c45  mov     rcx, r15; this
0x180014c48  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180014c4d  mov     qword ptr [rsp+2A0h+var_268+8], r15
0x180014c52  mov     qword ptr [rsp+2A0h+var_258], rsi
0x180014c57  lea     rdx, [rsp+2A0h+var_268+8]
0x180014c5c  mov     rcx, r14
0x180014c5f  call    ?NotifyAboutNewPiece@ZipConsumptionPart@consumption@win_musl@@AEAAXV?$scope@PEAVPiece@ZipConsumptionPart@consumption@win_musl@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::consumption::ZipConsumptionPart::NotifyAboutNewPiece(win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>)
0x180014c64  jmp     loc_180014B23
0x180014c69  mov     r12b, r13b
0x180014c6c  test    cl, cl
0x180014c6e  jz      loc_180014A12
0x180014c74  cmp     r8d, [r14+78h]
0x180014c78  ja      loc_180014FF9
0x180014c7e  jmp     loc_180014A12
0x180014c83  mov     [rbp+1A0h+var_1D8], rsi
0x180014c87  lea     rax, [rsp+2A0h+var_238+8]
0x180014c8c  mov     qword ptr [rbp+1A0h+var_210], rax
0x180014c90  xorps   xmm0, xmm0
0x180014c93  movdqu  xmmword ptr [rsp+2A0h+var_238+8], xmm0
0x180014c99  mov     rcx, [r12]
0x180014c9d  test    rcx, rcx
0x180014ca0  jz      loc_180014F8E
0x180014ca6  mov     rdx, [r12+8]
0x180014cab  mov     r12d, 1
0x180014cb1  mov     eax, r12d
0x180014cb4  lock xadd [rcx+8], eax
0x180014cb9  add     eax, r12d
0x180014cbc  cmp     eax, r12d
0x180014cbf  jz      loc_180014DB6
0x180014cc5  mov     qword ptr [rsp+2A0h+var_238+8], rcx
0x180014cca  mov     qword ptr [rsp+2A0h+var_238+10h], rdx
0x180014ccf  lea     rax, [rsp+2A0h+var_238+8]
0x180014cd4  mov     qword ptr [rbp+1A0h+var_220], rax
0x180014cd8  movdqu  [rsp+2A0h+var_258+8], xmm0
0x180014cde  mov     qword ptr [rsp+2A0h+var_248+8], r14
0x180014ce3  test    r14, r14
0x180014ce6  jnz     loc_180014DC7
0x180014cec  lea     rax, [rsp+2A0h+var_258+8]
0x180014cf1  mov     qword ptr [rbp+1A0h+var_210], rax
0x180014cf5  mov     [rsi+8], rbx
0x180014cf9  lea     rax, ??_7?$intrusive_shared_weak@V?$scope@PEAVOpcRelationshipImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::intrusive_shared_weak<win_scope::scope<win_dox::OpcRelationshipImplementation *,win_scope::const_policies<win_scope::shared_policies>>>::`vftable'
0x180014d00  mov     [rsi], rax
0x180014d03  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014d0a  mov     ecx, 18h; unsigned __int64
0x180014d0f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014d14  test    rax, rax
0x180014d17  jz      loc_180014E0F
0x180014d1d  mov     [rax+8], rbx
0x180014d21  lea     rcx, ??_7?$counted_strong_weak@PEAVZipConsumptionPart@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x180014d28  mov     [rax], rcx
0x180014d2b  mov     [rax+10h], rsi
0x180014d2f  mov     [rsi+8], rax
0x180014d33  lock add [rax+0Ch], r12d
  ... truncated ...
```
