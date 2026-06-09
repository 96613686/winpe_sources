# win_musl::consumption::ZipDeinterleaver::AddFile(std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70> const &,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0010,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0011,win_scope::scope<win_musl::ZipFileSender *,win_scope::const_policies<win_scope::shared_policies>>)

- ea: `0x180010780`
- end: `0x18001179f`
- name: `?AddFile@ZipDeinterleaver@consumption@win_musl@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0010@@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0011@@V?$scope@PEAVZipFileSender@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z`
- size: `4127`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180011c50`

## callees

- `0x18000531c`
- `0x18000b424`
- `0x18000d690`
- `0x18000f9a0`
- `0x180010780`
- `0x180011b14`
- `0x180013cf4`
- `0x1800147d0`
- `0x18001486c`
- `0x18001568c`
- `0x180017320`
- `0x1800190e0`
- `0x1800195ac`
- `0x18001ad90`
- `0x18001b99c`
- `0x180023e64`
- `0x1800240dc`
- `0x18002a2a8`
- `0x18002a2dc`
- `0x18002a334`
- `0x18002d818`
- `0x18002db70`
- `0x18003c8e8`
- `0x180060c90`
- `0x18007acf0`
- `0x180084010`
- `0x18009c7bc`
- `0x1800ca8e0`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800cded0`
- `0x1800d0848`
- `0x1800e85b8`
- `0x180110b54`
- `0x180110b98`
- `0x18011311c`
- `0x1801178f0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001091b`
- `msvcrt!memcpy_s` at `0x180010c59`
- `msvcrt!memcpy_s` at `0x18001113a`
- `msvcrt!memcpy_s` at `0x180011313`
- `msvcrt!memcpy_s` at `0x18001091b`
- `msvcrt!memcpy_s` at `0x180010c59`
- `msvcrt!memcpy_s` at `0x18001113a`
- `msvcrt!memcpy_s` at `0x180011313`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010801`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010873`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010873`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010e93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010e93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800107ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800107ec`

## string_xrefs

- `0x18001086c`: `/[Content_Types].xml`
- `0x18001170e`: `Compression method %{method} is unknown`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
void __fastcall win_musl::consumption::ZipDeinterleaver::AddFile(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v9; // r13
  bool v10; // dl
  win_dox *v11; // rcx
  const WCHAR *v12; // r8
  LPCWCH *v13; // rcx
  __int64 v14; // rdx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rsi
  LPCWCH *v17; // r8
  void **v18; // rcx
  void **v19; // rcx
  void **v20; // rcx
  void **v21; // rcx
  void **v22; // rax
  __int16 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rax
  void **v26; // r10
  unsigned __int64 v27; // r9
  _QWORD *v28; // rcx
  bool v29; // cf
  _QWORD *v30; // rax
  unsigned __int64 v31; // rcx
  void **v32; // r8
  bool v33; // cf
  void *v34; // rax
  int v35; // edx
  const char *v36; // r8
  unsigned int v37; // r9d
  __int64 v38; // rsi
  __m128i v39; // xmm1
  win_scope::counted_strong_weak_base *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // r12
  bool v43; // zf
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // r13
  const void *p_Source; // r8
  void **v47; // rcx
  void **v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r8
  volatile signed __int32 *v52; // rcx
  win_scope::counted_strong_weak_base *v53; // rdx
  int v54; // eax
  __int64 v55; // r8
  unsigned int i; // ecx
  __int64 v57; // rbx
  win_musl::Formatter *v58; // rax
  struct win_musl::TStringEllipseBase *v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rdx
  _QWORD *v62; // r12
  unsigned __int64 v63; // r13
  LPCWCH *v64; // r8
  unsigned __int64 v65; // rdx
  _QWORD *v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rcx
  __int64 v69; // rdx
  unsigned int v70; // edx
  unsigned __int64 v71; // rdx
  unsigned __int64 v72; // r13
  void **v73; // r8
  void **v74; // rcx
  void **v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rax
  __int64 v82; // r11
  __int64 v83; // r8
  __int64 v84; // r10
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // rax
  __int64 v88; // r10
  __int64 v89; // r11
  LPCWCH *v90; // r8
  __int64 v91; // rax
  __int64 v92; // r8
  __int64 v93; // rax
  __int64 v94; // rdx
  __int64 v95; // r10
  LPCWCH *v96; // r8
  __int64 v97; // rbx
  win_musl::Formatter *v98; // rax
  struct win_musl::TStringEllipseBase *v99; // rax
  int v100; // [rsp+48h] [rbp-C0h] BYREF
  win_scope::counted_strong_weak_base *v101[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v102; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v103; // [rsp+78h] [rbp-90h] BYREF
  __m128i v104; // [rsp+88h] [rbp-80h] BYREF
  __int64 v105; // [rsp+98h] [rbp-70h] BYREF
  win_scope::counted_strong_weak_base **v106; // [rsp+A0h] [rbp-68h]
  __int64 v107; // [rsp+A8h] [rbp-60h] BYREF
  win_scope::counted_strong_weak_base **v108; // [rsp+B0h] [rbp-58h]
  __int64 v109; // [rsp+B8h] [rbp-50h]
  __int64 v110; // [rsp+C0h] [rbp-48h]
  _QWORD *v111; // [rsp+C8h] [rbp-40h]
  char v112[8]; // [rsp+D0h] [rbp-38h] BYREF
  void *Destination[2]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int64 v114; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v115; // [rsp+F0h] [rbp-18h]
  char v116[8]; // [rsp+F8h] [rbp-10h] BYREF
  void *v117[2]; // [rsp+100h] [rbp-8h] BYREF
  unsigned __int64 v118; // [rsp+110h] [rbp+8h]
  unsigned __int64 v119; // [rsp+118h] [rbp+10h]
  int v120; // [rsp+120h] [rbp+18h] BYREF
  char v121[8]; // [rsp+128h] [rbp+20h] BYREF
  LPCWCH lpString2[2]; // [rsp+130h] [rbp+28h] BYREF
  unsigned __int64 v123; // [rsp+140h] [rbp+38h]
  unsigned __int64 v124; // [rsp+148h] [rbp+40h]
  char v125[8]; // [rsp+150h] [rbp+48h]
  char v126[8]; // [rsp+158h] [rbp+50h] BYREF
  void *Block; // [rsp+160h] [rbp+58h]
  __int64 v128; // [rsp+170h] [rbp+68h]
  unsigned __int64 v129; // [rsp+178h] [rbp+70h]
  char v130[8]; // [rsp+180h] [rbp+78h] BYREF
  void *v131[2]; // [rsp+188h] [rbp+80h] BYREF
  unsigned __int64 v132; // [rsp+198h] [rbp+90h]
  unsigned __int64 v133; // [rsp+1A0h] [rbp+98h]
  __int128 v134; // [rsp+1A8h] [rbp+A0h]
  __int64 v135; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 v136; // [rsp+1C0h] [rbp+B8h]
  __int64 v137; // [rsp+1C8h] [rbp+C0h]
  __int64 v138; // [rsp+1D0h] [rbp+C8h]
  char pExceptionObject[8]; // [rsp+1D8h] [rbp+D0h] BYREF
  void *Source; // [rsp+1E0h] [rbp+D8h] BYREF
  unsigned __int64 v141; // [rsp+1F0h] [rbp+E8h]
  unsigned __int64 v142; // [rsp+1F8h] [rbp+F0h]
  __int128 v143; // [rsp+200h] [rbp+F8h]
  _BYTE v144[160]; // [rsp+278h] [rbp+170h] BYREF

  v110 = -2;
  v103 = a4;
  v111 = a5;
  v100 = 0;
  v9 = a1 + 56;
  v107 = a1 + 56;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  v11 = (win_dox *)*(unsigned int *)(v9 + 44);
  *(_DWORD *)(v9 + 44) = (_DWORD)v11 + 1;
  if ( !(_DWORD)v11 )
    *(_DWORD *)(v9 + 40) = GetCurrentThreadId();
  LOBYTE(v11) = *(_BYTE *)(a1 + 156);
  win_dox::ThrowIfFailed(v11, v10);
  win_musl::Unicode8ToUnicodeWide(v126, a2);
  if ( a3 == 2 )
  {
    win_musl::consumption::ZipDeinterleaver::PartNameFromZipPart(&v120, a2);
    if ( *(_DWORD *)(a1 + 152) == 1 && v120 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x99u,
        0x80080201,
        (struct win_musl::TStringEllipseBase *)L"An APPX package must not contain interleaved parts.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v12 = (const WCHAR *)lpString2;
    if ( v124 >= 8 )
      v12 = lpString2[0];
    if ( CompareStringOrdinal(L"/[Content_Types].xml", -1, v12, -1, 1) == 2 )
      goto LABEL_12;
    v13 = lpString2;
    if ( v124 >= 8 )
      v13 = (LPCWCH *)lpString2[0];
    if ( (unsigned __int8)win_dox::IsValidPartUriInternal(v13) )
    {
LABEL_12:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      {
        v91 = win_musl::StringOfZipDeflateOption(*(unsigned int *)(a4 + 8));
        v93 = win_musl::StringOfZipFileCompressionMethod(*(unsigned int *)(a4 + 12), v91, v92);
        v96 = lpString2;
        if ( v124 >= 8 )
          v96 = (LPCWCH *)lpString2[0];
        WPP_SF_SSDSS(*(_QWORD *)(v95 + 56), (__int64)v96, v125[0], v93, v94);
      }
      v15 = 7;
      v115 = 7;
      v114 = 0;
      LOWORD(Destination[0]) = 0;
      v16 = v123;
      if ( v123 > 0x7FFFFFFFFFFFFFFELL )
        std::_String_base::_Xlen();
      if ( v123 > 7 )
      {
        std::wstring::_Copy(v112, v123, v114);
        v15 = v115;
        if ( !v16 )
        {
LABEL_24:
          v100 = 5;
          v20 = Destination;
          if ( v15 >= 8 )
            v20 = (void **)Destination[0];
          v21 = (void **)((char *)v20 + 2 * v114);
          v22 = Destination;
          if ( v15 >= 8 )
            v22 = (void **)Destination[0];
          while ( v22 != v21 )
          {
            v23 = *(_WORD *)v22;
            if ( (unsigned __int16)(*(_WORD *)v22 - 97) <= 0x19u )
              v23 -= 32;
            *(_WORD *)v22 = v23;
            v22 = (void **)((char *)v22 + 2);
          }
          v109 = a1 + 32;
          v24 = *(_QWORD *)(a1 + 40);
          v25 = *(_QWORD *)(v24 + 8);
          while ( !*(_BYTE *)(v25 + 81) )
          {
            v26 = Destination;
            if ( v115 >= 8 )
              v26 = (void **)Destination[0];
            v27 = v114;
            if ( *(_QWORD *)(v25 + 48) < v114 )
              v27 = *(_QWORD *)(v25 + 48);
            v28 = (_QWORD *)(v25 + 32);
            if ( *(_QWORD *)(v25 + 56) >= 8u )
              v28 = (_QWORD *)*v28;
            while ( v27 )
            {
              v29 = *(_WORD *)v28 < *(_WORD *)v26;
              if ( *(_WORD *)v28 != *(_WORD *)v26 )
                goto LABEL_43;
              v28 = (_QWORD *)((char *)v28 + 2);
              v26 = (void **)((char *)v26 + 2);
              --v27;
            }
            v29 = *(_QWORD *)(v25 + 48) < v114;
LABEL_43:
            if ( v29 )
            {
              v25 = *(_QWORD *)(v25 + 16);
            }
            else
            {
              v24 = v25;
              v25 = *(_QWORD *)v25;
            }
          }
          if ( v24 == *(_QWORD *)(a1 + 40) )
            goto LABEL_56;
          v30 = (_QWORD *)(v24 + 32);
          if ( *(_QWORD *)(v24 + 56) >= 8u )
            v30 = (_QWORD *)*v30;
          v31 = *(_QWORD *)(v24 + 48);
          if ( v114 < v31 )
            v31 = v114;
          v32 = Destination;
          if ( v115 >= 8 )
            v32 = (void **)Destination[0];
          while ( v31 )
          {
            v33 = *(_WORD *)v32 < *(_WORD *)v30;
            if ( *(_WORD *)v32 != *(_WORD *)v30 )
              goto LABEL_132;
            v32 = (void **)((char *)v32 + 2);
            v30 = (_QWORD *)((char *)v30 + 2);
            --v31;
          }
          v33 = v114 < *(_QWORD *)(v24 + 48);
LABEL_132:
          if ( v33 )
LABEL_56:
            v24 = *(_QWORD *)(a1 + 40);
          v104 = 0;
          if ( v24 != *(_QWORD *)(a1 + 40) )
          {
            v39 = 0;
            v104 = 0;
            v40 = *(win_scope::counted_strong_weak_base **)(v24 + 64);
            if ( v40 )
            {
              win_scope::counted_strong_weak_base::AddRef(v40);
              v104.m128i_i64[0] = v41;
              v104.m128i_i64[1] = v24;
              v39 = _mm_load_si128(&v104);
            }
            v104 = v39;
            v38 = _mm_srli_si128(v39, 8).m128i_u64[0];
            v42 = v39.m128i_i64[0];
            goto LABEL_93;
          }
          v34 = operator new(0xE0u, (const struct std::nothrow_t *)&std::nothrow);
          v38 = (__int64)v34;
          if ( !v34 )
            SplException::RealThrowFromHR((SplException *)0x8007000ELL, v35, v36, v37);
          v105 = (__int64)v34;
          v102 = 0;
          v60 = *(_QWORD *)(a1 + 112);
          if ( v60 )
          {
            v61 = *(_QWORD *)(a1 + 120);
            if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v60 + 8), 1u) )
              _InterlockedAdd((volatile signed __int32 *)(v60 + 12), 1u);
            *(_QWORD *)&v102 = v60;
            *((_QWORD *)&v102 + 1) = v61;
          }
          v108 = (win_scope::counted_strong_weak_base **)&v102;
          win_scope::intrusive_shared_weak<win_scope::scope<win_musl::consumption::PieceReceiver *,win_scope::const_policies<win_scope::shared_policies>>>::intrusive_shared_weak<win_scope::scope<win_musl::consumption::PieceReceiver *,win_scope::const_policies<win_scope::shared_policies>>>(v34);
          *(_QWORD *)v38 = &win_musl::consumption::ZipConsumptionPart::`vftable';
          *(_QWORD *)(v38 + 48) = 7;
          v62 = (_QWORD *)(v38 + 24);
          *(_QWORD *)(v38 + 40) = 0;
          *(_WORD *)(v38 + 24) = 0;
          v63 = v123;
          if ( (char *)(v38 + 16) == v121 )
          {
            std::wstring::erase(v38 + 16, v123, -1);
            std::wstring::erase(v38 + 16, 0, 0);
            goto LABEL_152;
          }
          if ( v123 > 0x7FFFFFFFFFFFFFFELL )
            std::_String_base::_Xlen();
          if ( *(_QWORD *)(v38 + 48) < v123 )
          {
            std::wstring::_Copy(v38 + 16, v123, *(_QWORD *)(v38 + 40));
            if ( !v63 )
              goto LABEL_152;
          }
          else if ( !v123 )
          {
            if ( *(_QWORD *)(v38 + 48) >= 8u )
              v62 = (_QWORD *)*v62;
            *(_QWORD *)(v38 + 40) = 0;
            *(_WORD *)v62 = 0;
LABEL_152:
            *(_DWORD *)(v38 + 56) = -1;
            *(_QWORD *)(v38 + 64) = 1;
            *(_QWORD *)(v38 + 72) = -1;
            v67 = std::_Tree<std::_Tmap_traits<unsigned int,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>>,0>>::_Buynode();
            *(_QWORD *)(v38 + 88) = v67;
            *(_BYTE *)(v67 + 49) = 1;
            *(_QWORD *)(*(_QWORD *)(v38 + 88) + 8LL) = *(_QWORD *)(v38 + 88);
            **(_QWORD **)(v38 + 88) = *(_QWORD *)(v38 + 88);
            *(_QWORD *)(*(_QWORD *)(v38 + 88) + 16LL) = *(_QWORD *)(v38 + 88);
            *(_QWORD *)(v38 + 96) = 0;
            *(_QWORD *)(v38 + 104) = 0;
            *(_QWORD *)(v38 + 112) = 0;
            v68 = v102;
            if ( (_QWORD)v102 )
            {
              v69 = *((_QWORD *)&v102 + 1);
              if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v102 + 8), 1u) )
                _InterlockedAdd((volatile signed __int32 *)(v68 + 12), 1u);
              *(_QWORD *)(v38 + 104) = v68;
              *(_QWORD *)(v38 + 112) = v69;
            }
            *(_DWORD *)(v38 + 120) = 0;
            *(_BYTE *)(v38 + 124) = 0;
            *(_QWORD *)(v38 + 136) = std::list<win_scope::scope<win_musl::consumption::ZipConsumptionByteSender *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>::_Buynode();
            *(_QWORD *)(v38 + 144) = 0;
            *(_WORD *)(v38 + 152) = 0;
            win_musl::CriticalSection::CriticalSection((win_musl::CriticalSection *)(v38 + 160), v70);
            *(_BYTE *)(v38 + 216) = 0;
            if ( *((_QWORD *)&v102 + 1) && (_QWORD)v102 )
            {
              win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v102);
              v102 = 0;
            }
            v105 = v38;
            v42 = *(_QWORD *)(v38 + 8);
            if ( !v42 )
            {
              win_scope::close_delete::close<win_musl::CallingThread>(&v105);
              win_scope::report_policy_throw::report_init_failure();
            }
            if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v42 + 8), 1u) )
              _InterlockedAdd((volatile signed __int32 *)(v42 + 12), 1u);
            v104.m128i_i64[0] = v42;
            v104.m128i_i64[1] = v38;
            v106 = v101;
            *(_OWORD *)v101 = 0;
            if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v42 + 8), 1u) )
              _InterlockedAdd((volatile signed __int32 *)(v42 + 12), 1u);
            v101[0] = (win_scope::counted_strong_weak_base *)v42;
            v101[1] = (win_scope::counted_strong_weak_base *)v38;
            v108 = v101;
            v71 = 7;
            v119 = 7;
            v118 = 0;
            LOWORD(v117[0]) = 0;
            v72 = v114;
            if ( v114 > 0x7FFFFFFFFFFFFFFELL )
              std::_String_base::_Xlen();
            if ( v114 > 7 )
            {
              std::wstring::_Copy(v116, v114, 0);
              v71 = v119;
              if ( !v72 )
                goto LABEL_174;
            }
            else if ( !v114 )
            {
              v118 = 0;
              LOWORD(v117[0]) = 0;
              goto LABEL_174;
            }
            v73 = Destination;
            if ( v115 >= 8 )
              v73 = (void **)Destination[0];
            v74 = v117;
            if ( v71 >= 8 )
              v74 = (void **)v117[0];
            memcpy_s(v74, 2 * v71, v73, 2 * v72);
            v75 = v117;
            if ( v119 >= 8 )
              v75 = (void **)v117[0];
            v118 = v72;
            *((_WORD *)v75 + v72) = 0;
LABEL_174:
            v106 = (win_scope::counted_strong_weak_base **)v116;
            std::wstring::wstring(pExceptionObject, v116);
            v143 = 0;
            if ( v101[0] )
            {
              win_scope::counted_strong_weak_base::AddRef(v101[0]);
              *(_QWORD *)&v143 = v76;
              *((_QWORD *)&v143 + 1) = v77;
            }
            v100 = 13;
            if ( v119 >= 8 )
              operator delete(v117[0]);
            v119 = 7;
            v118 = 0;
            LOWORD(v117[0]) = 0;
            if ( v101[1] && v101[0] )
            {
              win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v101);
              *(_OWORD *)v101 = 0;
            }
            v44 = 7;
            v133 = 7;
            v132 = 0;
            LOWORD(v131[0]) = 0;
            v45 = v141;
            if ( v141 > 0x7FFFFFFFFFFFFFFELL )
              std::_String_base::_Xlen();
            if ( v141 > 7 )
            {
              std::wstring::_Copy(v130, v141, 0);
              v44 = v133;
              if ( v45 )
                goto LABEL_81;
            }
            else
            {
              if ( v141 )
              {
LABEL_81:
                p_Source = &Source;
                if ( v142 >= 8 )
                  p_Source = Source;
                v47 = v131;
                if ( v44 >= 8 )
                  v47 = (void **)v131[0];
                memcpy_s(v47, 2 * v44, p_Source, 2 * v45);
                v48 = v131;
                if ( v133 >= 8 )
                  v48 = (void **)v131[0];
                v132 = v45;
                *((_WORD *)v48 + v45) = 0;
                goto LABEL_88;
              }
              v132 = 0;
              LOWORD(v131[0]) = 0;
            }
LABEL_88:
            v134 = 0;
            v49 = v143;
            if ( (_QWORD)v143 )
            {
              v50 = *((_QWORD *)&v143 + 1);
              if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v143 + 8), 1u) )
                _InterlockedAdd((volatile signed __int32 *)(v49 + 12), 1u);
              *(_QWORD *)&v134 = v49;
              *((_QWORD *)&v134 + 1) = v50;
            }
            std::_Tree<std::_Tmap_traits<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>>,0>>::insert(
              v109,
              &v102,
              v130);
            std::pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>::~pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>(v130);
            std::pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>::~pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>(pExceptionObject);
            v9 = v107;
LABEL_93:
            v102 = 0;
            v51 = v103;
            v135 = *(_QWORD *)(v103 + 56);
            v136 = 0;
            v137 = 0;
            v138 = 0;
            if ( *(_DWORD *)(v103 + 40) )
              v136 = *(_QWORD *)(v103 + 48);
            if ( *(_DWORD *)(v103 + 24) )
            {
              v137 = *(_QWORD *)(v103 + 32);
              *(_QWORD *)&v102 = 1;
              *((_QWORD *)&v102 + 1) = v137;
            }
            if ( *(_DWORD *)(v103 + 64) )
            {
              LODWORD(v138) = win_musl::get_value(
                                (win_musl *)(v103 + 64),
                                (const struct __MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0009 *)v24);
              v51 = v103;
            }
            v106 = v101;
            *(_OWORD *)v101 = 0;
            v52 = (volatile signed __int32 *)*a5;
            if ( *a5 )
            {
              v53 = (win_scope::counted_strong_weak_base *)a5[1];
              if ( !_InterlockedExchangeAdd(v52 + 2, 1u) )
                _InterlockedAdd(v52 + 3, 1u);
              v101[0] = (win_scope::counted_strong_weak_base *)v52;
              v101[1] = v53;
            }
            v54 = *(_DWORD *)(v51 + 12);
            LODWORD(v103) = v54;
            v55 = *(unsigned int *)(v51 + 8);
            v100 = v55;
            if ( v54 )
            {
              if ( v54 == 9 )
              {
                win_musl::detail::ThrowBuilder<SplException::THResultException>(
                  (SplException::TSystemException *)pExceptionObject,
                  0x67u,
                  0x80511008,
                  (struct win_musl::TStringEllipseBase *)L"Deflate64 is not supported");
                throw (SplException::THResultException *)pExceptionObject;
              }
              if ( v54 != 8 )
              {
                std::wstring::wstring(v130, L"Compression method %{method} is unknown");
                v97 = win_musl::Formatter::Formatter(pExceptionObject, v130);
                std::wstring::wstring(v116, L"method");
                v98 = (win_musl::Formatter *)win_musl::Formatter::insert<enum win_musl::consumption::ZipFileState::type>(
                                               v97,
                                               v116,
                                               &v103);
                v99 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v98);
                win_musl::detail::ThrowBuilder<SplException::THResultException>(
                  (SplException::TSystemException *)v144,
                  0x85u,
                  0x80511008,
                  v99);
                throw (SplException::THResultException *)v144;
              }
              for ( i = 0; ; ++i )
              {
                if ( i >= 5 )
                {
                  std::wstring::wstring(
                    v116,
                    L"Deflate option %{option} is unknown",
                    v55,
                    &win_musl::ZipTranslations::msc_zipOptionsMap);
                  v57 = win_musl::Formatter::Formatter(pExceptionObject, v116);
                  std::wstring::wstring(v130, L"option");
                  v58 = (win_musl::Formatter *)win_musl::Formatter::insert<enum win_musl::consumption::ZipFileState::type>(
                                                 v57,
                                                 v130,
                                                 &v100);
                  v59 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v58);
                  win_musl::detail::ThrowBuilder<SplException::THResultException>(
                    (SplException::TSystemException *)v144,
                    0x7Cu,
                    0x80511008,
                    v59);
                  throw (SplException::THResultException *)v144;
                }
                if ( *((_DWORD *)&win_musl::ZipTranslations::msc_zipOptionsMap + 3 * (int)i + 1) == (_DWORD)v55 )
                  break;
              }
            }
            win_musl::consumption::ZipConsumptionPart::AddZipFileSender(
              (win_musl::consumption::ZipConsumptionPart *)v38,
              (__int64)&v102,
              (__int64)v101,
              (__int64)&v135);
            if ( v42 && v38 )
              win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v104);
            if ( v115 >= 8 )
              operator delete(Destination[0]);
            v115 = 7;
            v114 = 0;
            LOWORD(Destination[0]) = 0;
            if ( v124 >= 8 )
              operator delete((void *)lpString2[0]);
            v124 = 7;
            v123 = 0;
            LOWORD(lpString2[0]) = 0;
            if ( v129 >= 8 )
              operator delete(Block);
            v129 = 7;
            v128 = 0;
            LOWORD(Block) = 0;
            if ( v9 )
            {
              v43 = (*(_DWORD *)(v9 + 44))-- == 1;
              if ( v43 )
                *(_DWORD *)(v9 + 40) = 0;
              LeaveCriticalSection((LPCRITICAL_SECTION)v9);
            }
            if ( *a5 && a5[1] )
            {
              win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)a5);
              *a5 = 0;
              a5[1] = 0;
            }
            return;
          }
          v64 = lpString2;
          if ( v124 >= 8 )
            v64 = (LPCWCH *)lpString2[0];
          v65 = *(_QWORD *)(v38 + 48);
          if ( v65 < 8 )
            v66 = (_QWORD *)(v38 + 24);
          else
            v66 = (_QWORD *)*v62;
          memcpy_s(v66, 2 * v65, v64, 2 * v63);
          if ( *(_QWORD *)(v38 + 48) >= 8u )
            v62 = (_QWORD *)*v62;
          *(_QWORD *)(v38 + 40) = v63;
          *((_WORD *)v62 + v63) = 0;
          goto LABEL_152;
        }
      }
      else if ( !v123 )
      {
        v114 = 0;
        LOWORD(Destination[0]) = 0;
LABEL_23:
        v15 = v115;
        goto LABEL_24;
      }
      v17 = lpString2;
      if ( v124 >= 8 )
        v17 = (LPCWCH *)lpString2[0];
      v18 = Destination;
      if ( v15 >= 8 )
        v18 = (void **)Destination[0];
      memcpy_s(v18, 2 * v15, v17, 2 * v16);
      v19 = Destination;
      if ( v115 >= 8 )
        v19 = (void **)Destination[0];
      v114 = v16;
      *((_WORD *)v19 + v16) = 0;
      goto LABEL_23;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0 )
    {
      win_musl::StringOfZipDeflateOption(*(unsigned int *)(a4 + 8));
      v87 = win_musl::StringOfZipFileCompressionMethod(*(unsigned int *)(a4 + 12), v85, v86);
      v90 = lpString2;
      if ( v124 >= 8 )
        v90 = (LPCWCH *)lpString2[0];
      WPP_SF_SSSS(*(_QWORD *)(v89 + 56), (__int64)v90, v87, v88);
    }
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v121, v14, 0);
    LOBYTE(v78) = 1;
    std::wstring::_Tidy(v126, v78, 0);
    win_musl::Locker<win_musl::CriticalSection *>::~Locker<win_musl::CriticalSection *>(&v107);
    if ( *a5 && a5[1] )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)a5);
      *a5 = 0;
      a5[1] = 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0 )
    {
      v79 = win_musl::StringOfZipDeflateOption(*(unsigned int *)(a4 + 8));
      v81 = win_musl::StringOfZipFileCompressionMethod(*(unsigned int *)(a4 + 12), v80, v79);
      WPP_SF_SSSS(*(_QWORD *)(v82 + 56), v81, v83, v84);
    }
    if ( !*(_BYTE *)(*(_QWORD *)(a1 + 120) + 57LL) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x90u,
        0x80511008,
        (struct win_musl::TStringEllipseBase *)L"Zip item is not a file - all Zip items must be files when streaming a package in-order");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( v129 >= 8 )
      operator delete(Block);
    v129 = 7;
    v128 = 0;
    LOWORD(Block) = 0;
    if ( v9 )
    {
      v43 = (*(_DWORD *)(v9 + 44))-- == 1;
      if ( v43 )
        *(_DWORD *)(v9 + 40) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)v9);
    }
    if ( *a5 && a5[1] )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)a5);
      *a5 = 0;
      a5[1] = 0;
    }
  }
}

```

## disassembly

```asm
0x180010780  mov     rax, rsp
0x180010783  push    rbp
0x180010784  push    rsi
0x180010785  push    rdi
0x180010786  push    r12
0x180010788  push    r13
0x18001078a  push    r14
0x18001078c  push    r15
0x18001078e  lea     rbp, [rax-268h]
0x180010795  sub     rsp, 330h
0x18001079c  mov     [rbp+260h+var_2A8], 0FFFFFFFFFFFFFFFEh
0x1800107a4  mov     [rax+18h], rbx
0x1800107a8  movaps  xmmword ptr [rax-48h], xmm6
0x1800107ac  mov     rax, cs:__security_cookie
0x1800107b3  xor     rax, rsp
0x1800107b6  mov     [rbp+260h+var_50], rax
0x1800107bd  mov     rsi, r9
0x1800107c0  mov     [rsp+360h+var_2F0], r9
0x1800107c5  mov     ebx, r8d
0x1800107c8  mov     rdi, rdx
0x1800107cb  mov     r12, rcx
0x1800107ce  mov     r15, [rbp+260h+arg_20]
0x1800107d5  mov     [rbp+260h+var_2A0], r15
0x1800107d9  mov     [rsp+360h+var_320], 0
0x1800107e1  lea     r13, [rcx+38h]
0x1800107e5  mov     [rbp+260h+var_2C0], r13
0x1800107e9  mov     rcx, r13; lpCriticalSection
0x1800107ec  call    cs:__imp_EnterCriticalSection
0x1800107f2  mov     ecx, [r13+2Ch]
0x1800107f6  lea     eax, [rcx+1]
0x1800107f9  mov     [r13+2Ch], eax
0x1800107fd  test    ecx, ecx
0x1800107ff  jnz     short loc_18001080B
0x180010801  call    cs:__imp_GetCurrentThreadId
0x180010807  mov     [r13+28h], eax
0x18001080b  mov     cl, [r12+9Ch]; this
0x180010813  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180010818  mov     rdx, rdi
0x18001081b  lea     rcx, [rbp+260h+var_210]
0x18001081f  call    ?Unicode8ToUnicodeWide@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@3@@Z; win_musl::Unicode8ToUnicodeWide(std::string const &)
0x180010824  nop
0x180010825  cmp     ebx, 2
0x180010828  jnz     loc_180010B20
0x18001082e  mov     rdx, rdi
0x180010831  lea     rcx, [rbp+260h+var_248]
0x180010835  call    ?PartNameFromZipPart@ZipDeinterleaver@consumption@win_musl@@KA?AUPartData@123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@@Z; win_musl::consumption::ZipDeinterleaver::PartNameFromZipPart(std::string const &)
0x18001083a  nop
0x18001083b  lea     edi, [rbx-1]
0x18001083e  cmp     [r12+98h], edi
0x180010846  jz      loc_180010ACC
0x18001084c  lea     r8, [rbp+260h+lpString2]
0x180010850  mov     r14d, 8
0x180010856  cmp     [rbp+260h+var_220], r14
0x18001085a  cmovnb  r8, [rbp+260h+lpString2]; lpString2
0x18001085f  mov     [rsp+360h+bIgnoreCase], edi; bIgnoreCase
0x180010863  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010867  mov     r9d, eax; cchCount2
0x18001086a  mov     edx, eax; cchCount1
0x18001086c  lea     rcx, ?gc_contentTypePart@win_musl@@3QB_WB; "/[Content_Types].xml"
0x180010873  call    cs:__imp_CompareStringOrdinal
0x180010879  cmp     eax, 2
0x18001087c  jz      short loc_18001089A
0x18001087e  lea     rcx, [rbp+260h+lpString2]
0x180010882  cmp     [rbp+260h+var_220], r14
0x180010886  cmovnb  rcx, [rbp+260h+lpString2]; Source
0x18001088b  xor     edx, edx
0x18001088d  call    ?IsValidPartUriInternal@win_dox@@YA_NPEB_WPEAV?$scope@PEAVOpcPartUri@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::IsValidPartUriInternal(wchar_t const *,win_scope::scope<win_dox::OpcPartUri *,win_scope::const_policies<win_scope::shared_policies>> *)
0x180010892  test    al, al
0x180010894  jz      loc_180011586
0x18001089a  lea     rax, WPP_GLOBAL_Control
0x1800108a1  mov     r10, cs:WPP_GLOBAL_Control
0x1800108a8  cmp     r10, rax
0x1800108ab  jz      short loc_1800108B8
0x1800108ad  test    byte ptr [r10+44h], 4
0x1800108b2  jnz     loc_1800115FE
0x1800108b8  mov     edx, 7
0x1800108bd  mov     [rbp+260h+var_278], rdx
0x1800108c1  mov     [rbp+260h+var_280], 0
0x1800108c9  xor     eax, eax
0x1800108cb  mov     word ptr [rbp+260h+Destination], ax
0x1800108cf  mov     rsi, [rbp+260h+var_228]
0x1800108d3  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800108dd  cmp     rsi, rax
0x1800108e0  ja      loc_18001164F
0x1800108e6  cmp     rdx, rsi
0x1800108e9  jb      loc_180010F22
0x1800108ef  test    rsi, rsi
0x1800108f2  jz      loc_180010F92
0x1800108f8  lea     r8, [rbp+260h+lpString2]
0x1800108fc  cmp     [rbp+260h+var_220], r14
0x180010900  cmovnb  r8, [rbp+260h+lpString2]; Source
0x180010905  lea     rcx, [rbp+260h+Destination]
0x180010909  cmp     rdx, r14
0x18001090c  cmovnb  rcx, [rbp+260h+Destination]; Destination
0x180010911  lea     rbx, [rsi+rsi]
0x180010915  add     rdx, rdx; DestinationSize
0x180010918  mov     r9, rbx; SourceSize
0x18001091b  call    cs:__imp_memcpy_s
0x180010921  lea     rcx, [rbp+260h+Destination]
0x180010925  cmp     [rbp+260h+var_278], r14
0x180010929  cmovnb  rcx, [rbp+260h+Destination]
0x18001092e  mov     [rbp+260h+var_280], rsi
0x180010932  xor     eax, eax
0x180010934  mov     [rbx+rcx], ax
0x180010938  mov     rdx, [rbp+260h+var_278]
0x18001093c  mov     [rsp+360h+var_320], 5
0x180010944  lea     rcx, [rbp+260h+Destination]
0x180010948  cmp     rdx, r14
0x18001094b  cmovnb  rcx, [rbp+260h+Destination]
0x180010950  mov     rax, [rbp+260h+var_280]
0x180010954  lea     rcx, [rcx+rax*2]
0x180010958  lea     rax, [rbp+260h+Destination]
0x18001095c  cmovnb  rax, [rbp+260h+Destination]
0x180010961  cmp     rax, rcx
0x180010964  jz      short loc_18001097E
0x180010966  movzx   r8d, word ptr [rax]
0x18001096a  lea     edx, [r8-61h]
0x18001096e  cmp     dx, 19h
0x180010972  jbe     short loc_1800109EF
0x180010974  mov     [rax], r8w
0x180010978  add     rax, 2
0x18001097c  jmp     short loc_180010961
0x18001097e  lea     rax, [r12+20h]
0x180010983  mov     [rbp+260h+var_2B0], rax
0x180010987  mov     rdx, [rax+8]
0x18001098b  mov     rax, [rdx+8]
0x18001098f  mov     r8, [rbp+260h+var_280]
0x180010993  cmp     byte ptr [rax+51h], 0
0x180010997  jnz     short loc_1800109F9
0x180010999  lea     r10, [rbp+260h+Destination]
0x18001099d  cmp     [rbp+260h+var_278], r14
0x1800109a1  cmovnb  r10, [rbp+260h+Destination]
0x1800109a6  mov     r9, r8
0x1800109a9  cmp     [rax+30h], r8
0x1800109ad  cmovb   r9, [rax+30h]
0x1800109b2  lea     rcx, [rax+20h]
0x1800109b6  cmp     [rax+38h], r14
0x1800109ba  jb      short loc_1800109BF
0x1800109bc  mov     rcx, [rcx]
0x1800109bf  test    r9, r9
0x1800109c2  jz      loc_18001165D
0x1800109c8  movzx   r11d, word ptr [rcx]
0x1800109cc  cmp     r11w, [r10]
0x1800109d0  jnz     short loc_1800109DF
0x1800109d2  add     rcx, 2
0x1800109d6  add     r10, 2
0x1800109da  sub     r9, rdi
0x1800109dd  jmp     short loc_1800109BF
0x1800109df  jb      short loc_1800109E9
0x1800109e1  mov     rdx, rax
0x1800109e4  mov     rax, [rax]
0x1800109e7  jmp     short loc_180010993
0x1800109e9  mov     rax, [rax+10h]
0x1800109ed  jmp     short loc_180010993
0x1800109ef  sub     r8w, 20h ; ' '
0x1800109f4  jmp     loc_180010974
0x1800109f9  cmp     rdx, [r12+28h]
0x1800109fe  jz      short loc_180010A4C
0x180010a00  lea     rax, [rdx+20h]
0x180010a04  mov     r11, r8
0x180010a07  cmp     [rdx+38h], r14
0x180010a0b  jb      short loc_180010A10
0x180010a0d  mov     rax, [rax]
0x180010a10  mov     rcx, [rdx+30h]
0x180010a14  cmp     r8, rcx
0x180010a17  cmovb   rcx, r8
0x180010a1b  lea     r8, [rbp+260h+Destination]
0x180010a1f  cmp     [rbp+260h+var_278], r14
0x180010a23  cmovnb  r8, [rbp+260h+Destination]
0x180010a28  test    rcx, rcx
0x180010a2b  jz      loc_180011666
0x180010a31  movzx   r9d, word ptr [r8]
0x180010a35  cmp     r9w, [rax]
0x180010a39  jnz     loc_180010F87
0x180010a3f  add     r8, 2
0x180010a43  add     rax, 2
0x180010a47  sub     rcx, rdi
0x180010a4a  jmp     short loc_180010A28
0x180010a4c  mov     rdx, [r12+28h]
0x180010a51  xorps   xmm6, xmm6
0x180010a54  movdqa  [rbp+260h+var_2E0], xmm6
0x180010a59  cmp     rdx, [r12+28h]
0x180010a5e  jnz     short loc_180010A88
0x180010a60  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010a67  mov     ecx, 0E0h; unsigned __int64
0x180010a6c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010a71  mov     rsi, rax
0x180010a74  test    rax, rax
0x180010a77  jnz     loc_180011068
0x180010a7d  mov     ecx, 8007000Eh; this
0x180010a82  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x180010a88  xorps   xmm1, xmm1
0x180010a8b  movdqa  [rbp+260h+var_2E0], xmm1
0x180010a90  mov     rcx, [rdx+40h]; this
0x180010a94  test    rcx, rcx
0x180010a97  jz      short loc_180010AAF
0x180010a99  mov     rdx, [rdx+48h]
0x180010a9d  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180010aa2  mov     qword ptr [rbp+260h+var_2E0], rcx
0x180010aa6  mov     qword ptr [rbp+260h+var_2E0+8], rdx
0x180010aaa  movdqa  xmm1, [rbp+260h+var_2E0]
0x180010aaf  movdqa  [rbp+260h+var_2E0], xmm1
0x180010ab4  movdqa  xmm0, xmm1
0x180010ab8  psrldq  xmm0, 8
0x180010abd  movq    rsi, xmm0
0x180010ac2  movq    r12, xmm1
0x180010ac7  jmp     loc_180010CEC
0x180010acc  cmp     [rbp+260h+var_248], 0
0x180010ad0  jz      loc_18001084C
0x180010ad6  lea     rax, aAnAppxPackageM; "An APPX package must not contain interl"...
0x180010add  mov     [rsp+360h+var_330], rax; struct win_musl::TStringEllipseBase *
0x180010ae2  mov     dword ptr [rsp+360h+var_338], 80080201h; unsigned int
0x180010aea  mov     [rsp+360h+bIgnoreCase], 99h; unsigned int
0x180010af2  lea     r9, word_180139126
0x180010af9  lea     r8, aNoFilename; "(no filename)"
0x180010b00  lea     rcx, [rbp+260h+pExceptionObject]; this
0x180010b07  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180010b0c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180010b13  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x180010b1a  call    _CxxThrowException_0
0x180010b20  lea     rax, WPP_GLOBAL_Control
0x180010b27  mov     r14d, 8
0x180010b2d  mov     r11, cs:WPP_GLOBAL_Control
0x180010b34  cmp     r11, rax
0x180010b37  jnz     loc_1800114C2
0x180010b3d  mov     rax, [r12+78h]
0x180010b42  xor     ebx, ebx
0x180010b44  cmp     [rax+39h], bl
0x180010b47  jz      loc_18001153C
0x180010b4d  cmp     [rbp+260h+var_1F0], r14
0x180010b51  jnb     loc_180010F79
0x180010b57  mov     [rbp+260h+var_1F0], 7
0x180010b5f  mov     [rbp+260h+var_1F8], rbx
0x180010b63  mov     word ptr [rbp+260h+Block], bx
0x180010b67  test    r13, r13
0x180010b6a  jz      short loc_180010B81
0x180010b6c  add     dword ptr [r13+2Ch], 0FFFFFFFFh
0x180010b71  jnz     short loc_180010B77
0x180010b73  mov     [r13+28h], ebx
0x180010b77  mov     rcx, r13; lpCriticalSection
0x180010b7a  call    cs:__imp_LeaveCriticalSection
0x180010b80  nop
0x180010b81  cmp     [r15], rbx
0x180010b84  jz      short loc_180010B90
0x180010b86  cmp     [r15+8], rbx
0x180010b8a  jnz     loc_180010F44
0x180010b90  mov     rcx, [rbp+260h+var_50]
0x180010b97  xor     rcx, rsp; StackCookie
0x180010b9a  call    __security_check_cookie
0x180010b9f  lea     r11, [rsp+360h+var_30]
0x180010ba7  mov     rbx, [r11+50h]
0x180010bab  movaps  xmm6, xmmword ptr [r11-10h]
0x180010bb0  mov     rsp, r11
0x180010bb3  pop     r15
0x180010bb5  pop     r14
0x180010bb7  pop     r13
0x180010bb9  pop     r12
0x180010bbb  pop     rdi
0x180010bbc  pop     rsi
0x180010bbd  pop     rbp
0x180010bbe  retn
0x180010bbf  cmp     [rsp+360h+var_318+8], 0
0x180010bc5  jz      short loc_180010BDA
0x180010bc7  lea     rcx, [rsp+360h+var_318+8]
0x180010bcc  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180010bd1  xorps   xmm0, xmm0
0x180010bd4  movdqu  xmmword ptr [rsp+360h+var_318+8], xmm0
0x180010bda  mov     rdx, rbx
0x180010bdd  mov     [rbp+260h+var_1C8], rbx
0x180010be4  xor     r8d, r8d
0x180010be7  mov     [rbp+260h+var_1D0], r8
0x180010bee  xor     eax, eax
0x180010bf0  mov     word ptr [rbp+260h+var_1E0], ax
0x180010bf7  mov     r13, [rbp+260h+var_178]
0x180010bfe  mov     rax, 7FFFFFFFFFFFFFFEh
0x180010c08  cmp     r13, rax
0x180010c0b  ja      loc_1800116AC
0x180010c11  cmp     rdx, r13
0x180010c14  jb      loc_180010F58
0x180010c1a  test    r13, r13
0x180010c1d  jz      loc_180010FB0
0x180010c23  lea     r8, [rbp+260h+Source]
0x180010c2a  cmp     [rbp+260h+var_170], r14
0x180010c31  cmovnb  r8, [rbp+260h+Source]; Source
0x180010c39  lea     rcx, [rbp+260h+var_1E0]
0x180010c40  cmp     rdx, r14
0x180010c43  cmovnb  rcx, [rbp+260h+var_1E0]; Destination
0x180010c4b  lea     rbx, ds:0[r13*2]
0x180010c53  add     rdx, rdx; DestinationSize
0x180010c56  mov     r9, rbx; SourceSize
0x180010c59  call    cs:__imp_memcpy_s
0x180010c5f  lea     rcx, [rbp+260h+var_1E0]
0x180010c66  cmp     [rbp+260h+var_1C8], r14
0x180010c6d  cmovnb  rcx, [rbp+260h+var_1E0]
0x180010c75  mov     [rbp+260h+var_1D0], r13
0x180010c7c  xor     eax, eax
0x180010c7e  mov     [rbx+rcx], ax
0x180010c82  xorps   xmm0, xmm0
0x180010c85  movdqu  [rbp+260h+var_1C0], xmm0
0x180010c8d  mov     rdx, qword ptr [rbp+260h+var_168]
  ... truncated ...
```
