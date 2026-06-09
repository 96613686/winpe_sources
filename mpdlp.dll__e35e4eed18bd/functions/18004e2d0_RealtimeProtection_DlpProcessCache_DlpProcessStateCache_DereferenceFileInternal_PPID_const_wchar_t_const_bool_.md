# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DereferenceFileInternal(PPID const &,wchar_t const *,bool,_MP_KNOWN_PROCESS_TYPE &)

- ea: `0x18004e2d0`
- end: `0x18004f36b`
- name: `?DereferenceFileInternal@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@AEAAJAEBUPPID@@PEB_W_NAEAW4_MP_KNOWN_PROCESS_TYPE@@@Z`
- size: `4251`
- prototype: `int(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct PPID *, const wchar_t *, bool, enum _MP_KNOWN_PROCESS_TYPE *)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004f430`

## callees

- `0x180022708`
- `0x180022920`
- `0x180023460`
- `0x180023c58`
- `0x18002e090`
- `0x180034420`
- `0x180037754`
- `0x180037a14`
- `0x180038328`
- `0x18003a09c`
- `0x180042594`
- `0x18004d26c`
- `0x18004d480`
- `0x18004e000`
- `0x18004e2d0`
- `0x18005da68`
- `0x18006c610`
- `0x1800809d0`
- `0x180084c44`
- `0x180088980`
- `0x180088bdc`
- `0x180089534`
- `0x18008981c`
- `0x18008c12c`
- `0x1800a3358`
- `0x1800a4154`
- `0x180107874`
- `0x180109324`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18010ce44`
- `0x180119428`
- `0x18011db70`
- `0x18023a6d0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18004ea61`
- `KERNEL32!CompareStringOrdinal` at `0x18004ec1c`
- `KERNEL32!CompareStringOrdinal` at `0x18004ea61`
- `KERNEL32!CompareStringOrdinal` at `0x18004ec1c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004e3dc`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004e3dc`
- `KERNEL32!CompareFileTime` at `0x18004e389`
- `KERNEL32!CompareFileTime` at `0x18004e389`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::DereferenceFileInternal(
        RealtimeProtection::DlpProcessCache::DlpProcessStateCache *this,
        const FILETIME *a2,
        const wchar_t *a3,
        __int64 a4,
        enum _MP_KNOWN_PROCESS_TYPE *a5)
{
  RealtimeProtection::DlpProcessCache::DlpProcessStateCache *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // r14
  __int64 v10; // rbx
  unsigned __int64 v11; // rbx
  __int64 v12; // r12
  unsigned __int64 v13; // rdi
  size_t v14; // rcx
  WCHAR *v15; // rsi
  size_t v16; // rbx
  LPCWCH *v17; // rdx
  unsigned __int64 v18; // rdi
  void **v19; // rsi
  unsigned __int64 v20; // rbx
  size_t v21; // rcx
  void *v22; // rax
  unsigned __int64 v23; // r9
  void **v24; // rdi
  void **v25; // r10
  void **v26; // rcx
  void **v27; // rsi
  void **v28; // rbx
  void **v29; // rdx
  __int64 v30; // rsi
  __int64 v31; // rbx
  unsigned __int64 i; // rax
  const struct std::nothrow_t *v33; // rdx
  void **v34; // rax
  __m128i si128; // xmm2
  __int64 v36; // rax
  _QWORD *v37; // r13
  unsigned __int64 v38; // rbx
  LPCWCH *v39; // r14
  size_t v40; // rcx
  void *v41; // rax
  unsigned __int64 v42; // r9
  void **v43; // r14
  void **v44; // r10
  void **v45; // rcx
  void **v46; // r15
  void **v47; // rbx
  const struct std::nothrow_t *v48; // rdx
  void *v49; // rcx
  const struct std::nothrow_t *v50; // rdx
  WCHAR *v51; // rcx
  size_t v53; // rbx
  void **v54; // rdx
  unsigned __int64 v55; // r8
  unsigned __int64 j; // rcx
  void *v57; // rdx
  __int64 v58; // rax
  __int64 v59; // rbx
  __int64 v60; // rdi
  const WCHAR *v61; // r8
  const WCHAR *v62; // rcx
  int v63; // ecx
  bool v64; // r12
  int v65; // eax
  int v66; // edi
  bool v67; // si
  int v68; // r14d
  int *v69; // r15
  bool v70; // si
  bool v71; // al
  _QWORD *v72; // rbx
  const WCHAR *v73; // r8
  void **v74; // rcx
  struct RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor *v75; // r14
  int v76; // ebx
  void *v77; // rdx
  void *v78; // rcx
  void *v79; // rdx
  WCHAR *v80; // rcx
  _QWORD *v81; // rax
  _QWORD *v82; // rax
  const FILETIME *v83; // r15
  __int64 v84; // rax
  _QWORD *v85; // rax
  _QWORD *v86; // rax
  _QWORD *v87; // rax
  int updated; // eax
  int v89; // [rsp+40h] [rbp-218h]
  void *v92[2]; // [rsp+58h] [rbp-200h] BYREF
  int *v93; // [rsp+68h] [rbp-1F0h]
  void *v94[2]; // [rsp+70h] [rbp-1E8h] BYREF
  __int64 v95; // [rsp+80h] [rbp-1D8h]
  int v96[34]; // [rsp+90h] [rbp-1C8h] BYREF
  char v97; // [rsp+118h] [rbp-140h]
  bool v98; // [rsp+120h] [rbp-138h] BYREF
  struct RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor *v99; // [rsp+128h] [rbp-130h] BYREF
  LPCWCH lpString1[2]; // [rsp+130h] [rbp-128h] BYREF
  unsigned __int64 v101; // [rsp+140h] [rbp-118h]
  unsigned __int64 v102; // [rsp+148h] [rbp-110h]
  void *Src[2]; // [rsp+150h] [rbp-108h] BYREF
  unsigned __int64 v104; // [rsp+160h] [rbp-F8h]
  unsigned __int64 v105; // [rsp+168h] [rbp-F0h]
  void *v106[2]; // [rsp+170h] [rbp-E8h] BYREF
  __m128i v107; // [rsp+180h] [rbp-D8h]
  void *v108[2]; // [rsp+190h] [rbp-C8h] BYREF
  __m128i v109; // [rsp+1A0h] [rbp-B8h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1B0h] [rbp-A8h] BYREF
  _BYTE v111[8]; // [rsp+1C0h] [rbp-98h] BYREF
  bool *v112; // [rsp+1C8h] [rbp-90h]
  int *v113; // [rsp+1D0h] [rbp-88h]
  LPCWCH *v114; // [rsp+1D8h] [rbp-80h]
  const FILETIME *v115; // [rsp+1E0h] [rbp-78h]
  char v116; // [rsp+200h] [rbp-58h]

  v95 = (__int64)a3;
  v7 = this;
  v93 = (int *)a5;
  v89 = 0;
  LODWORD(v99) = 0;
  MpHashCrc32(&v99, 12);
  v8 = *((_QWORD *)v7 + 28);
  v9 = *(_QWORD *)(v8 + 16 * ((unsigned int)v99 & *((_QWORD *)v7 + 31)) + 8);
  if ( v9 != *((_QWORD *)v7 + 26) )
  {
    v10 = *(_QWORD *)(v8 + 16 * ((unsigned int)v99 & *((_QWORD *)v7 + 31)));
    while ( 1 )
    {
      if ( a2[1].dwLowDateTime == *(_DWORD *)(v9 + 24) && !CompareFileTime(a2, (const FILETIME *)(v9 + 16)) )
      {
        v7 = this;
        goto LABEL_10;
      }
      if ( v9 == v10 )
        break;
      v9 = *(_QWORD *)(v9 + 8);
    }
    v7 = this;
  }
  v9 = 0;
LABEL_10:
  if ( !v9 || v9 == *((_QWORD *)v7 + 26) )
    return 1;
  v99 = (struct RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor *)(v9 + 32);
  *(_DWORD *)a5 = *(_DWORD *)(v9 + 160);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(_OWORD *)lpString1 = 0;
  v101 = 0;
  v102 = 0;
  v11 = -1;
  do
    ++v11;
  while ( a3[v11] );
  v12 = 0x7FFFFFFFFFFFFFFELL;
  if ( v11 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v11 > 7 )
  {
    v13 = v11 | 7;
    if ( (v11 | 7) > 0x7FFFFFFFFFFFFFFELL )
    {
      v13 = 0x7FFFFFFFFFFFFFFELL;
      v14 = -2;
    }
    else
    {
      if ( v13 < 0xA )
        v13 = 10;
      if ( v13 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v14 = 2 * (v13 + 1);
      if ( !v14 )
      {
        v15 = 0;
LABEL_23:
        _mm_lfence();
        lpString1[0] = v15;
        v101 = v11;
        v102 = v13;
        v16 = v11;
        memmove(v15, a3, v16 * 2);
        v15[v16] = 0;
        goto LABEL_24;
      }
    }
    _mm_lfence();
    if ( v14 >= 0x1000 )
      v15 = (WCHAR *)((__int64 (*)(void))std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>)();
    else
      v15 = (WCHAR *)operator new(v14);
    goto LABEL_23;
  }
  _mm_lfence();
  v101 = v11;
  v102 = 7;
  v53 = 2 * v11;
  memmove(lpString1, a3, v53);
  *(_WORD *)((char *)lpString1 + v53) = 0;
LABEL_24:
  v17 = lpString1;
  if ( v102 > 7 )
    v17 = (LPCWCH *)lpString1[0];
  RealtimeProtection::DlpUtils::GetFileExtensions(Src, v17);
  *(_OWORD *)v106 = 0;
  v107 = 0;
  v18 = v104;
  v19 = Src;
  if ( v105 > 7 )
    v19 = (void **)Src[0];
  if ( v104 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v104 > 7 )
  {
    v20 = v104 | 7;
    if ( (v104 | 7) > 0x7FFFFFFFFFFFFFFELL )
    {
      v20 = 0x7FFFFFFFFFFFFFFELL;
      v21 = -2;
    }
    else
    {
      if ( v20 < 0xA )
        v20 = 10;
      if ( v20 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v21 = 2 * (v20 + 1);
      if ( !v21 )
      {
        v22 = 0;
LABEL_37:
        v106[0] = v22;
        v107.m128i_i64[0] = v18;
        v107.m128i_i64[1] = v20;
        memmove(v22, v19, 2 * v18 + 2);
        v23 = v107.m128i_u64[1];
        goto LABEL_38;
      }
    }
    _mm_lfence();
    if ( v21 >= 0x1000 )
      v22 = (void *)((__int64 (*)(void))std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>)();
    else
      v22 = operator new(v21);
    goto LABEL_37;
  }
  v107.m128i_i64[0] = v104;
  v23 = 7;
  v107.m128i_i64[1] = 7;
  *(_OWORD *)v106 = *(_OWORD *)v19;
LABEL_38:
  v24 = v106;
  v25 = (void **)v106[0];
  if ( v23 > 7 )
    v24 = (void **)v106[0];
  v26 = v106;
  if ( v23 > 7 )
    v26 = (void **)v106[0];
  v27 = (void **)((char *)v26 + 2 * v107.m128i_i64[0]);
  v28 = v106;
  if ( v23 > 7 )
    v28 = (void **)v106[0];
  while ( v28 != v27 )
  {
    *(_WORD *)v24 = towlower(*(_WORD *)v28);
    v28 = (void **)((char *)v28 + 2);
    v24 = (void **)((char *)v24 + 2);
    v23 = v107.m128i_u64[1];
    v25 = (void **)v106[0];
  }
  v29 = v106;
  if ( v23 > 7 )
    v29 = v25;
  v30 = 0xCBF29CE484222325uLL;
  v31 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 2 * v107.m128i_i64[0]; ++i )
    v31 = 0x100000001B3LL * (*((unsigned __int8 *)v29 + i) ^ (unsigned __int64)v31);
  if ( v23 > 7 )
  {
    v33 = (const struct std::nothrow_t *)(2 * v23 + 2);
    v34 = v25;
    if ( (unsigned __int64)v33 >= 0x1000 )
    {
      v33 = (const struct std::nothrow_t *)(2 * v23 + 41);
      v25 = (void **)*(v25 - 1);
      if ( (unsigned __int64)((char *)v34 - (char *)v25 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v25, v33);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v107 = si128;
  LOWORD(v106[0]) = 0;
  v36 = *(_QWORD *)(v9 + 200);
  v37 = *(_QWORD **)(v36 + 16 * (v31 & *(_QWORD *)(v9 + 224)) + 8);
  if ( v37 != *(_QWORD **)(v9 + 184) )
  {
    v72 = *(_QWORD **)(v36 + 16 * (v31 & *(_QWORD *)(v9 + 224)));
    while ( 1 )
    {
      v73 = (const WCHAR *)(v37 + 2);
      if ( v37[5] > 7u )
        v73 = *(const WCHAR **)v73;
      v74 = Src;
      if ( v105 > 7 )
        v74 = (void **)Src[0];
      if ( CompareStringOrdinal((LPCWCH)v74, -1, v73, -1, 1) == 2 )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        goto LABEL_55;
      }
      if ( v37 == v72 )
        break;
      v37 = (_QWORD *)v37[1];
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v37 = 0;
LABEL_55:
  if ( !v37 )
    v37 = *(_QWORD **)(v9 + 184);
  v98 = 0;
  v111[0] = 0;
  v112 = &v98;
  v113 = v93;
  v114 = lpString1;
  v115 = a2;
  if ( v37 != *((_QWORD **)v99 + 19) )
  {
    *(_OWORD *)v108 = 0;
    v109 = 0;
    v38 = v101;
    v39 = lpString1;
    if ( v102 > 7 )
      v39 = (LPCWCH *)lpString1[0];
    if ( v101 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v101 <= 7 )
    {
      v109.m128i_i64[0] = v101;
      v42 = 7;
      v109.m128i_i64[1] = 7;
      *(_OWORD *)v108 = *(_OWORD *)v39;
LABEL_70:
      v43 = v108;
      v44 = (void **)v108[0];
      if ( v42 > 7 )
        v43 = (void **)v108[0];
      v45 = v108;
      if ( v42 > 7 )
        v45 = (void **)v108[0];
      v46 = (void **)((char *)v45 + 2 * v109.m128i_i64[0]);
      v47 = v108;
      if ( v42 > 7 )
        v47 = (void **)v108[0];
      while ( v47 != v46 )
      {
        *(_WORD *)v43 = towlower(*(_WORD *)v47);
        v47 = (void **)((char *)v47 + 2);
        v43 = (void **)((char *)v43 + 2);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v42 = v109.m128i_u64[1];
        v44 = (void **)v108[0];
      }
      v54 = v108;
      if ( v42 > 7 )
        v54 = v44;
      v55 = 2 * v109.m128i_i64[0];
      for ( j = 0; j < v55; ++j )
        v30 = 0x100000001B3LL * (*((unsigned __int8 *)v54 + j) ^ (unsigned __int64)v30);
      if ( v42 > 7 )
      {
        v57 = (void *)(2 * v42 + 2);
        v94[0] = v57;
        v92[0] = v44;
        if ( (unsigned __int64)v57 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(v92, (unsigned __int64 *)v94);
          v57 = v94[0];
          v44 = (void **)v92[0];
        }
        operator delete(v44, (const struct std::nothrow_t *)v57);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      v109 = si128;
      LOWORD(v108[0]) = 0;
      v58 = v37[9];
      v59 = *(_QWORD *)(v58 + 16 * (v30 & v37[12]) + 8);
      if ( v59 == v37[7] )
      {
LABEL_103:
        v59 = 0;
      }
      else
      {
        v60 = *(_QWORD *)(v58 + 16 * (v30 & v37[12]));
        while ( 1 )
        {
          v61 = (const WCHAR *)(v59 + 16);
          if ( *(_QWORD *)(v59 + 40) > 7u )
            v61 = *(const WCHAR **)v61;
          v62 = (const WCHAR *)lpString1;
          if ( v102 > 7 )
            v62 = lpString1[0];
          if ( CompareStringOrdinal(v62, -1, v61, -1, 1) == 2 )
            break;
          if ( v59 == v60 )
            goto LABEL_103;
          v59 = *(_QWORD *)(v59 + 8);
        }
      }
      if ( !v59 || v59 == v37[7] )
      {
        v98 = 1;
        CommonUtil::ScopeGuardImpl__lambda_400cec65ce93663de686e1d93b9695ce___::_ScopeGuardImpl__lambda_400cec65ce93663de686e1d93b9695ce___(v111);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpString1);
        return 1;
      }
      v63 = *(_DWORD *)(v59 + 48);
      if ( v63 )
        *(_DWORD *)(v59 + 48) = --v63;
      *(struct _FILETIME *)(v59 + 480) = SystemTimeAsFileTime;
      v64 = !v63 && !*(_BYTE *)(v59 + 52);
      v98 = v63 == 0;
      v65 = (int)v99;
      v66 = *((_DWORD *)v99 + 85);
      if ( *((_DWORD *)v99 + 84) != 1 || v66 == 2 )
      {
        v67 = *v93 == 5 || ((*v93 - 4) & 0xFFFFFFFD) == 0;
        if ( *(_BYTE *)(v59 + 352) )
        {
          v81 = (_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                            (char *)this + 552,
                            v92,
                            v59 + 288);
          if ( *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Try_emplace<PPID const &,>(
                                        *v81 + 80LL,
                                        v94,
                                        a2)
                         + 28LL) )
          {
            v82 = (_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                              (char *)this + 552,
                              v92,
                              v59 + 288);
            v83 = a2;
            v84 = std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Try_emplace<PPID const &,>(
                    *v82 + 80LL,
                    v94,
                    a2);
            --*(_DWORD *)(*(_QWORD *)v84 + 28LL);
          }
          else
          {
            v83 = a2;
          }
          v85 = (_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                            (char *)this + 552,
                            v92,
                            v59 + 288);
          if ( !*(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Try_emplace<PPID const &,>(
                                         *v85 + 80LL,
                                         v94,
                                         v83)
                          + 28LL) )
          {
            v86 = (_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                              (char *)this + 552,
                              v92,
                              v59 + 288);
            if ( !*(_BYTE *)(*(_QWORD *)std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Try_emplace<PPID const &,>(
                                          *v86 + 80LL,
                                          v94,
                                          v83)
                           + 32LL)
              || v66 == 2 )
            {
              v87 = (_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                                (char *)this + 552,
                                v92,
                                v59 + 288);
              std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Erase<PPID>(
                *v87 + 80LL,
                v83);
              if ( !*(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                                             (char *)this + 552,
                                             v92,
                                             v59 + 288)
                              + 96LL) )
                std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Erase<RealtimeProtection::FileUniqueId>(
                  (char *)this + 552,
                  v59 + 288);
              if ( !RealtimeProtection::DlpProcessCache::DlpProcessStateCache::IsFileCurrentlyProtectedUnsafe(
                      this,
                      (const struct RealtimeProtection::FileUniqueId *)(v59 + 288)) )
              {
                updated = RealtimeProtection::DlpQuarantineEngine::UpdateQuarantineItemProtectionStatus(
                            (RealtimeProtection::DlpProcessCache::DlpProcessStateCache *)((char *)this + 616),
                            (const struct RealtimeProtection::FileUniqueId *)(v59 + 288),
                            0);
                v89 = updated;
                if ( updated < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      35,
                      &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
                      (unsigned int)updated);
                  v89 = 0;
                }
              }
            }
          }
        }
        v68 = v95;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_DSdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v95, *(_DWORD *)(v59 + 48), *(_BYTE *)(v59 + 52));
        v69 = v93;
        v70 = v67 && (unsigned __int8)anonymous_namespace_::IsOfficeCandidateAutoSaveTarget(Src, (unsigned int)*v93);
        v71 = *v69 == 20 && (unsigned __int8)Dlp::Utils::IsExplorerBurnTarget(lpString1, v54);
        if ( !v70 && *v69 != 12 && !v71 )
        {
          if ( v64 )
          {
            v75 = v99;
            RealtimeProtection::DlpProcessCache::DlpProcessStateCache::UpdateRecallCacheOnClose(
              v99,
              (const struct RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor *)(v59 + 48));
            std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>,0>>::_Erase<std::wstring>(
              v37 + 6,
              lpString1);
            if ( !v37[8] )
              std::_Hash<std::_Umap_traits<std::wstring,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>>>,0>>::_Erase<std::wstring>(
                (char *)v75 + 144,
                Src);
            goto LABEL_151;
          }
LABEL_124:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_SddD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)v54,
              v55,
              v68,
              *(_DWORD *)(v59 + 48),
              *(_BYTE *)(v59 + 52),
              a2[1].dwLowDateTime);
LABEL_151:
          v76 = (int)a2;
          goto LABEL_152;
        }
        v65 = (int)v99;
      }
      else
      {
        v68 = v95;
        v69 = v93;
      }
      if ( v64 )
      {
        v76 = (int)a2;
        RealtimeProtection::DlpProcessCache::DlpProcessStateCache::RemoveFileFromProcessCacheUnsafe(
          (_DWORD)this,
          v65,
          (unsigned int)lpString1,
          (_DWORD)a2,
          (__int64)&SystemTimeAsFileTime);
LABEL_152:
        if ( v98 && *v69 == 20 && (unsigned __int8)Dlp::Utils::IsExplorerBurnTarget(lpString1, v54) )
        {
          Dlp::Utils::GetDlpFileUniqueId(v111, lpString1);
          if ( v116 )
          {
            Dlp::SubstituteCache::FindSubstitute(
              (int)v96,
              v76,
              *v69,
              (int)lpString1,
              (struct RealtimeProtection::FileUniqueId *)v111);
            if ( v97 )
              Dlp::SubstituteCache::SubstituteInfo::~SubstituteInfo((Dlp::SubstituteCache::SubstituteInfo *)v96);
          }
          std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v111);
        }
        if ( v105 > 7 )
        {
          v77 = (void *)(2 * v105 + 2);
          v92[0] = v77;
          v78 = Src[0];
          v94[0] = Src[0];
          if ( (unsigned __int64)v77 >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned(v94, (unsigned __int64 *)v92);
            v77 = v92[0];
            v78 = v94[0];
          }
          operator delete(v78, (const struct std::nothrow_t *)v77);
        }
        v104 = 0;
        v105 = 7;
        LOWORD(Src[0]) = 0;
        if ( v102 > 7 )
        {
          v79 = (void *)(2 * v102 + 2);
          v92[0] = v79;
          v80 = (WCHAR *)lpString1[0];
          v94[0] = (void *)lpString1[0];
          if ( (unsigned __int64)v79 >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned(v94, (unsigned __int64 *)v92);
            v79 = v92[0];
            v80 = (WCHAR *)v94[0];
          }
          operator delete(v80, (const struct std::nothrow_t *)v79);
        }
        if ( v89 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
            (unsigned int)v89);
        return (unsigned int)v89;
      }
      goto LABEL_124;
    }
    if ( (v101 | 7) > 0x7FFFFFFFFFFFFFFELL )
    {
      v40 = -2;
    }
    else
    {
      v12 = v101 | 7;
      if ( (v101 | 7) < 0xA )
        v12 = 10;
      if ( (unsigned __int64)(v12 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v40 = 2 * (v12 + 1);
      if ( !v40 )
      {
        v41 = 0;
LABEL_69:
        v108[0] = v41;
        v109.m128i_i64[0] = v38;
        v109.m128i_i64[1] = v12;
        memmove(v41, v39, 2 * v38 + 2);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v42 = v109.m128i_u64[1];
        goto LABEL_70;
      }
    }
    _mm_lfence();
    if ( v40 >= 0x1000 )
      v41 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v40, v29);
    else
      v41 = operator new(v40);
    goto LABEL_69;
  }
  v98 = 1;
  if ( *v93 == 20 && (unsigned __int8)Dlp::Utils::IsExplorerBurnTarget(lpString1, v29) )
  {
    Dlp::Utils::GetDlpFileUniqueId(v111, lpString1);
    if ( v116 )
    {
      Dlp::SubstituteCache::FindSubstitute(
        (int)v96,
        (int)a2,
        *v93,
        (int)lpString1,
        (struct RealtimeProtection::FileUniqueId *)v111);
      if ( v97 )
        Dlp::SubstituteCache::SubstituteInfo::~SubstituteInfo((Dlp::SubstituteCache::SubstituteInfo *)v96);
    }
    std::_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>::~_Optional_destruct_base<RealtimeProtection::FileUniqueId,0>(v111);
  }
  if ( v105 > 7 )
  {
    v48 = (const struct std::nothrow_t *)(2 * v105 + 2);
    v49 = Src[0];
    if ( (unsigned __int64)v48 >= 0x1000 )
    {
      v48 = (const struct std::nothrow_t *)(2 * v105 + 41);
      v49 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v49 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v49, v48);
  }
  v104 = 0;
  v105 = 7;
  LOWORD(Src[0]) = 0;
  if ( v102 > 7 )
  {
    v50 = (const struct std::nothrow_t *)(2 * v102 + 2);
    v51 = (WCHAR *)lpString1[0];
    if ( (unsigned __int64)v50 >= 0x1000 )
    {
      v50 = (const struct std::nothrow_t *)(2 * v102 + 41);
      v51 = (WCHAR *)*((_QWORD *)lpString1[0] - 1);
      if ( (unsigned __int64)((char *)lpString1[0] - (char *)v51 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v51, v50);
  }
  return 1;
}

```

## disassembly

```asm
0x18004e2d0  push    rbx
0x18004e2d2  push    rsi
0x18004e2d3  push    rdi
0x18004e2d4  push    r12
0x18004e2d6  push    r13
0x18004e2d8  push    r14
0x18004e2da  push    r15
0x18004e2dc  sub     rsp, 220h
0x18004e2e3  mov     rax, cs:__security_cookie
0x18004e2ea  xor     rax, rsp
0x18004e2ed  mov     [rsp+258h+var_48], rax
0x18004e2f5  mov     r15, r8
0x18004e2f8  mov     [rsp+258h+var_1D8], r8
0x18004e300  mov     rdi, rdx
0x18004e303  mov     qword ptr [rsp+258h+var_210], rdx
0x18004e308  mov     rbx, rcx
0x18004e30b  mov     [rsp+258h+var_208], rcx
0x18004e310  mov     rsi, [rsp+258h+arg_20]
0x18004e318  mov     [rsp+258h+var_1F0], rsi
0x18004e31d  xor     r13d, r13d
0x18004e320  mov     [rsp+258h+var_218], r13d
0x18004e325  mov     dword ptr [rsp+258h+var_130], r13d
0x18004e32d  mov     r8, rdx
0x18004e330  mov     edx, 0Ch
0x18004e335  lea     rcx, [rsp+258h+var_130]
0x18004e33d  call    MpHashCrc32
0x18004e342  mov     eax, dword ptr [rsp+258h+var_130]
0x18004e349  mov     rcx, [rbx+0F8h]
0x18004e350  and     rcx, rax
0x18004e353  add     rcx, rcx
0x18004e356  mov     rax, [rbx+0E0h]
0x18004e35d  mov     r14, [rax+rcx*8+8]
0x18004e362  cmp     r14, [rbx+0D0h]
0x18004e369  jz      short loc_18004E39F
0x18004e36b  mov     rbx, [rax+rcx*8]
0x18004e36f  lea     rdx, [r14+10h]; lpFileTime2
0x18004e373  mov     eax, [rdx+8]
0x18004e376  cmp     [rdi+8], eax
0x18004e379  jz      short loc_18004E386
0x18004e37b  cmp     r14, rbx
0x18004e37e  jz      short loc_18004E39A
0x18004e380  mov     r14, [r14+8]
0x18004e384  jmp     short loc_18004E36F
0x18004e386  mov     rcx, rdi; lpFileTime1
0x18004e389  call    cs:__imp_CompareFileTime
0x18004e38f  test    eax, eax
0x18004e391  jnz     short loc_18004E37B
0x18004e393  mov     rbx, [rsp+258h+var_208]
0x18004e398  jmp     short loc_18004E3A2
0x18004e39a  mov     rbx, [rsp+258h+var_208]
0x18004e39f  mov     r14, r13
0x18004e3a2  test    r14, r14
0x18004e3a5  jz      loc_18004EE16
0x18004e3ab  cmp     r14, [rbx+0D0h]
0x18004e3b2  jz      loc_18004EE16
0x18004e3b8  lea     rax, [r14+20h]
0x18004e3bc  mov     [rsp+258h+var_130], rax
0x18004e3c4  mov     eax, [rax+80h]
0x18004e3ca  mov     [rsi], eax
0x18004e3cc  mov     qword ptr [rsp+258h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18004e3d4  lea     rcx, [rsp+258h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004e3dc  call    cs:__imp_GetSystemTimeAsFileTime
0x18004e3e2  xorps   xmm0, xmm0
0x18004e3e5  movups  xmmword ptr [rsp+258h+lpString1], xmm0
0x18004e3ed  mov     [rsp+258h+var_118], r13
0x18004e3f5  mov     [rsp+258h+var_110], r13
0x18004e3fd  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18004e404  inc     rbx
0x18004e407  cmp     word ptr [r15+rbx*2], 0
0x18004e40d  jnz     short loc_18004E404
0x18004e40f  mov     r12, 7FFFFFFFFFFFFFFEh
0x18004e419  cmp     rbx, r12
0x18004e41c  ja      loc_18004F2DD
0x18004e422  cmp     rbx, 7
0x18004e426  jbe     loc_18004E946
0x18004e42c  mov     rdi, rbx
0x18004e42f  or      rdi, 7
0x18004e433  mov     r13, 7FFFFFFFFFFFFFFFh
0x18004e43d  cmp     rdi, r12
0x18004e440  ja      loc_18004EC37
0x18004e446  mov     eax, 0Ah
0x18004e44b  cmp     rdi, rax
0x18004e44e  cmovb   rdi, rax
0x18004e452  lea     rcx, [rdi+1]
0x18004e456  cmp     rcx, r13
0x18004e459  ja      loc_18004F2E9
0x18004e45f  add     rcx, rcx; Size
0x18004e462  jz      loc_18004F167
0x18004e468  lfence
0x18004e46b  cmp     rcx, 1000h
0x18004e472  jnb     loc_18004F0B9
0x18004e478  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e47d  mov     rsi, rax
0x18004e480  lfence
0x18004e483  mov     [rsp+258h+lpString1], rsi
0x18004e48b  mov     [rsp+258h+var_118], rbx
0x18004e493  mov     [rsp+258h+var_110], rdi
0x18004e49b  add     rbx, rbx
0x18004e49e  mov     r8, rbx; Size
0x18004e4a1  mov     rdx, r15; Src
0x18004e4a4  mov     rcx, rsi; void *
0x18004e4a7  call    memmove
0x18004e4ac  xor     eax, eax
0x18004e4ae  mov     [rbx+rsi], ax
0x18004e4b2  mov     r15d, 0Ah
0x18004e4b8  lea     rdx, [rsp+258h+lpString1]
0x18004e4c0  cmp     [rsp+258h+var_110], 7
0x18004e4c9  cmova   rdx, [rsp+258h+lpString1]
0x18004e4d2  lea     rcx, [rsp+258h+Src]
0x18004e4da  call    ?GetFileExtensions@DlpUtils@RealtimeProtection@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; RealtimeProtection::DlpUtils::GetFileExtensions(wchar_t const *)
0x18004e4df  nop
0x18004e4e0  xorps   xmm0, xmm0
0x18004e4e3  movups  xmmword ptr [rsp+258h+var_E8], xmm0
0x18004e4eb  xorps   xmm1, xmm1
0x18004e4ee  movdqu  [rsp+258h+var_D8], xmm1
0x18004e4f7  mov     rdi, [rsp+258h+var_F8]
0x18004e4ff  lea     rsi, [rsp+258h+Src]
0x18004e507  cmp     [rsp+258h+var_F0], 7
0x18004e510  cmova   rsi, [rsp+258h+Src]
0x18004e519  cmp     rdi, r12
0x18004e51c  ja      loc_18004F2EF
0x18004e522  cmp     rdi, 7
0x18004e526  jbe     loc_18004EBAA
0x18004e52c  mov     rbx, rdi
0x18004e52f  or      rbx, 7
0x18004e533  cmp     rbx, r12
0x18004e536  ja      loc_18004EBD0
0x18004e53c  cmp     rbx, r15
0x18004e53f  cmovb   rbx, r15
0x18004e543  lea     rcx, [rbx+1]
0x18004e547  cmp     rcx, r13
0x18004e54a  ja      loc_18004F2FB
0x18004e550  add     rcx, rcx; Size
0x18004e553  jz      loc_18004F150
0x18004e559  lfence
0x18004e55c  cmp     rcx, 1000h
0x18004e563  jnb     loc_18004EFF8
0x18004e569  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e56e  mov     [rsp+258h+var_E8], rax
0x18004e576  mov     qword ptr [rsp+258h+var_D8], rdi
0x18004e57e  mov     qword ptr [rsp+258h+var_D8+8], rbx
0x18004e586  lea     r8, ds:2[rdi*2]; Size
0x18004e58e  mov     rdx, rsi; Src
0x18004e591  mov     rcx, rax; void *
0x18004e594  call    memmove
0x18004e599  mov     r9, qword ptr [rsp+258h+var_D8+8]
0x18004e5a1  lea     rdi, [rsp+258h+var_E8]
0x18004e5a9  mov     r10, [rsp+258h+var_E8]
0x18004e5b1  cmp     r9, 7
0x18004e5b5  cmova   rdi, r10
0x18004e5b9  lea     rcx, [rsp+258h+var_E8]
0x18004e5c1  cmova   rcx, r10
0x18004e5c5  mov     rax, qword ptr [rsp+258h+var_D8]
0x18004e5cd  lea     rsi, [rcx+rax*2]
0x18004e5d1  lea     rbx, [rsp+258h+var_E8]
0x18004e5d9  cmova   rbx, r10
0x18004e5dd  nop     dword ptr [rax]
0x18004e5e0  cmp     rbx, rsi
0x18004e5e3  jz      short loc_18004E60A
0x18004e5e5  movzx   ecx, word ptr [rbx]; C
0x18004e5e8  call    towlower
0x18004e5ed  mov     [rdi], ax
0x18004e5f0  add     rbx, 2
0x18004e5f4  add     rdi, 2
0x18004e5f8  mov     r9, qword ptr [rsp+258h+var_D8+8]
0x18004e600  mov     r10, [rsp+258h+var_E8]
0x18004e608  jmp     short loc_18004E5E0
0x18004e60a  lea     rdx, [rsp+258h+var_E8]
0x18004e612  cmp     r9, 7
0x18004e616  cmova   rdx, r10
0x18004e61a  mov     rsi, 0CBF29CE484222325h
0x18004e624  mov     rbx, rsi
0x18004e627  mov     rax, qword ptr [rsp+258h+var_D8]
0x18004e62f  lea     r8, [rax+rax]
0x18004e633  xor     r11d, r11d
0x18004e636  mov     eax, r11d
0x18004e639  mov     rdi, 100000001B3h
0x18004e643  test    r8, r8
0x18004e646  jz      short loc_18004E663
0x18004e648  nop     dword ptr [rax+rax+00000000h]
0x18004e650  movzx   ecx, byte ptr [rdx+rax]
0x18004e654  xor     rbx, rcx
0x18004e657  imul    rbx, rdi
0x18004e65b  inc     rax
0x18004e65e  cmp     rax, r8
0x18004e661  jb      short loc_18004E650
0x18004e663  cmp     r9, 7
0x18004e667  jbe     short loc_18004E68C
0x18004e669  lea     rdx, ds:2[r9*2]; struct std::nothrow_t *
0x18004e671  mov     rax, r10
0x18004e674  cmp     rdx, 1000h
0x18004e67b  jnb     loc_18004F1F7
0x18004e681  mov     rcx, r10; void *
0x18004e684  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e689  xor     r11d, r11d
0x18004e68c  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x18004e694  movdqu  [rsp+258h+var_D8], xmm2
0x18004e69d  mov     word ptr [rsp+258h+var_E8], r11w
0x18004e6a6  mov     rcx, [r14+0E0h]
0x18004e6ad  and     rcx, rbx
0x18004e6b0  add     rcx, rcx
0x18004e6b3  mov     rax, [r14+0C8h]
0x18004e6ba  mov     r13, [rax+rcx*8+8]
0x18004e6bf  cmp     r13, [r14+0B8h]
0x18004e6c6  jnz     loc_18004EBE0
0x18004e6cc  mov     r13, r11
0x18004e6cf  test    r13, r13
0x18004e6d2  jz      loc_18004EB9E
0x18004e6d8  mov     [rsp+258h+var_138], 0
0x18004e6e0  mov     [rsp+258h+var_98], 0
0x18004e6e8  lea     rax, [rsp+258h+var_138]
0x18004e6f0  mov     [rsp+258h+var_90], rax
0x18004e6f8  mov     rax, [rsp+258h+var_1F0]
0x18004e6fd  mov     [rsp+258h+var_88], rax
0x18004e705  lea     rcx, [rsp+258h+lpString1]
0x18004e70d  mov     [rsp+258h+var_80], rcx
0x18004e715  mov     rbx, qword ptr [rsp+258h+var_210]
0x18004e71a  mov     [rsp+258h+var_78], rbx
0x18004e722  mov     r14, [rsp+258h+var_130]
0x18004e72a  cmp     r13, [r14+98h]
0x18004e731  jz      loc_18004E887
0x18004e737  xorps   xmm0, xmm0
0x18004e73a  movups  xmmword ptr [rsp+258h+var_C8], xmm0
0x18004e742  xorps   xmm1, xmm1
0x18004e745  movdqu  [rsp+258h+var_B8], xmm1
0x18004e74e  mov     rbx, [rsp+258h+var_118]
0x18004e756  lea     r14, [rsp+258h+lpString1]
0x18004e75e  cmp     [rsp+258h+var_110], 7
0x18004e767  cmova   r14, [rsp+258h+lpString1]
0x18004e770  cmp     rbx, r12
0x18004e773  ja      loc_18004F301
0x18004e779  cmp     rbx, 7
0x18004e77d  jbe     loc_18004EC84
0x18004e783  mov     rax, rbx
0x18004e786  or      rax, 7
0x18004e78a  cmp     rax, r12
0x18004e78d  ja      loc_18004EE03
0x18004e793  mov     r12, rax
0x18004e796  cmp     rax, 0Ah
0x18004e79a  cmovb   r12, r15
0x18004e79e  lea     rcx, [r12+1]
0x18004e7a3  mov     rax, 7FFFFFFFFFFFFFFFh
0x18004e7ad  cmp     rcx, rax
0x18004e7b0  ja      loc_18004F30D
0x18004e7b6  add     rcx, rcx; Size
0x18004e7b9  jz      loc_18004F1C8
0x18004e7bf  lfence
0x18004e7c2  cmp     rcx, 1000h
0x18004e7c9  jnb     loc_18004F1AA
0x18004e7cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e7d4  mov     [rsp+258h+var_C8], rax
0x18004e7dc  mov     qword ptr [rsp+258h+var_B8], rbx
0x18004e7e4  mov     qword ptr [rsp+258h+var_B8+8], r12
0x18004e7ec  lea     r8, ds:2[rbx*2]; Size
0x18004e7f4  mov     rdx, r14; Src
0x18004e7f7  mov     rcx, rax; void *
0x18004e7fa  call    memmove
0x18004e7ff  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x18004e807  mov     r9, qword ptr [rsp+258h+var_B8+8]
0x18004e80f  lea     r14, [rsp+258h+var_C8]
0x18004e817  mov     r10, [rsp+258h+var_C8]
0x18004e81f  cmp     r9, 7
0x18004e823  cmova   r14, r10
0x18004e827  lea     rcx, [rsp+258h+var_C8]
0x18004e82f  cmova   rcx, r10
0x18004e833  mov     rax, qword ptr [rsp+258h+var_B8]
0x18004e83b  lea     r15, [rcx+rax*2]
0x18004e83f  lea     rbx, [rsp+258h+var_C8]
0x18004e847  cmova   rbx, r10
0x18004e84b  nop     dword ptr [rax+rax+00h]
0x18004e850  cmp     rbx, r15
0x18004e853  jz      loc_18004E98B
0x18004e859  movzx   ecx, word ptr [rbx]; C
0x18004e85c  call    towlower
0x18004e861  mov     [r14], ax
0x18004e865  add     rbx, 2
0x18004e869  add     r14, 2
0x18004e86d  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x18004e875  mov     r9, qword ptr [rsp+258h+var_B8+8]
0x18004e87d  mov     r10, [rsp+258h+var_C8]
0x18004e885  jmp     short loc_18004E850
0x18004e887  mov     [rsp+258h+var_138], 1
0x18004e88f  cmp     dword ptr [rax], 14h
0x18004e892  jz      loc_18004F0C6
0x18004e898  mov     rax, [rsp+258h+var_F0]
0x18004e8a0  cmp     rax, 7
0x18004e8a4  jbe     short loc_18004E8CB
0x18004e8a6  lea     rdx, ds:2[rax*2]; struct std::nothrow_t *
0x18004e8ae  mov     rcx, [rsp+258h+Src]; void *
0x18004e8b6  mov     rax, rcx
0x18004e8b9  cmp     rdx, 1000h
0x18004e8c0  jnb     loc_18004F225
0x18004e8c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004e8cb  xor     r8d, r8d
0x18004e8ce  mov     [rsp+258h+var_F8], r8
0x18004e8d6  mov     [rsp+258h+var_F0], 7
0x18004e8e2  mov     word ptr [rsp+258h+Src], r8w
0x18004e8eb  mov     rax, [rsp+258h+var_110]
0x18004e8f3  cmp     rax, 7
0x18004e8f7  jbe     short loc_18004E91E
  ... truncated ...
```
