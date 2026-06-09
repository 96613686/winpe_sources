# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::RemoveFile(wchar_t const *)

- ea: `0x1800335d0`
- end: `0x180033d68`
- name: `?RemoveFile@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJPEB_W@Z`
- size: `1944`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001b760`

## callees

- `0x18002c990`
- `0x18002e090`
- `0x1800335d0`
- `0x180034420`
- `0x1800344a0`
- `0x180037754`
- `0x180037a14`
- `0x180038328`
- `0x180038450`
- `0x18003a09c`
- `0x18004d26c`
- `0x18004d480`
- `0x18004e000`
- `0x1800553b4`
- `0x18005da68`
- `0x18006c458`
- `0x18006c680`
- `0x18006c814`
- `0x1800809d0`
- `0x180088980`
- `0x180089534`
- `0x18008981c`
- `0x18009351c`
- `0x1800a3358`
- `0x1800b51d0`
- `0x180109324`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18010ce44`
- `0x18011db70`
- `0x18023a6d0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180033a33`
- `KERNEL32!CompareStringOrdinal` at `0x180033a33`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180033625`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180033625`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800338ed`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180033c81`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800338ed`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180033c81`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180033687`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180033687`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::RemoveFile(
        RTL_SRWLOCK *this,
        const wchar_t *a2)
{
  RealtimeProtection::DlpProcessCache::DlpProcessStateCache *v3; // r12
  int v4; // r13d
  RTL_SRWLOCK *v5; // rsi
  _QWORD *v6; // rdx
  __int64 *v7; // rbx
  __m128i si128; // xmm6
  unsigned __int64 v9; // r14
  void **v10; // r15
  unsigned __int64 v11; // rsi
  size_t v12; // rcx
  void *v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  void **v16; // r14
  void **v17; // r8
  void **v18; // rax
  void **v19; // r15
  void **v20; // rsi
  void **v21; // r9
  __int64 v22; // rsi
  unsigned __int64 v23; // r10
  unsigned __int64 i; // rdx
  const struct std::nothrow_t *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rsi
  _QWORD *v29; // rdx
  char *v31; // r14
  PVOID *v32; // rcx
  __int64 v33; // r14
  const WCHAR *v34; // r8
  void **v35; // rcx
  const struct RealtimeProtection::FileUniqueId *v36; // r15
  char *v37; // r12
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // r14
  __int64 v42; // rdx
  _QWORD *v43; // rax
  int updated; // eax
  _QWORD *v45; // r9
  unsigned __int64 v46; // [rsp+30h] [rbp-158h] BYREF
  void *v47; // [rsp+38h] [rbp-150h] BYREF
  RealtimeProtection::DlpProcessCache::DlpProcessStateCache *v48; // [rsp+40h] [rbp-148h]
  const wchar_t *v49; // [rsp+48h] [rbp-140h]
  RTL_SRWLOCK *v50; // [rsp+58h] [rbp-130h]
  char v51; // [rsp+60h] [rbp-128h]
  _BYTE v52[16]; // [rsp+68h] [rbp-120h] BYREF
  _BYTE v53[16]; // [rsp+78h] [rbp-110h] BYREF
  _BYTE v54[16]; // [rsp+88h] [rbp-100h] BYREF
  _BYTE v55[16]; // [rsp+98h] [rbp-F0h] BYREF
  _BYTE v56[16]; // [rsp+A8h] [rbp-E0h] BYREF
  _BYTE v57[16]; // [rsp+B8h] [rbp-D0h] BYREF
  _BYTE v58[16]; // [rsp+C8h] [rbp-C0h] BYREF
  void *v59[2]; // [rsp+D8h] [rbp-B0h] BYREF
  __m128i v60; // [rsp+E8h] [rbp-A0h]
  _FILETIME SystemTimeAsFileTime; // [rsp+F8h] [rbp-90h] BYREF
  void *Src[2]; // [rsp+100h] [rbp-88h] BYREF
  unsigned __int64 v63; // [rsp+110h] [rbp-78h]
  unsigned __int64 v64; // [rsp+118h] [rbp-70h]
  _QWORD v65[4]; // [rsp+120h] [rbp-68h] BYREF

  v49 = a2;
  v3 = (RealtimeProtection::DlpProcessCache::DlpProcessStateCache *)this;
  v48 = (RealtimeProtection::DlpProcessCache::DlpProcessStateCache *)this;
  v4 = 0;
  v5 = this + 58;
  v50 = this + 58;
  AcquireSRWLockExclusive(this + 58);
  v51 = 1;
  if ( !*((_QWORD *)v3 + 27) )
  {
    ReleaseSRWLockExclusive(v5);
    return 1;
  }
  std::wstring::wstring(v65, a2);
  v6 = v65;
  if ( v65[3] > 7u )
    v6 = (_QWORD *)v65[0];
  RealtimeProtection::DlpUtils::GetFileExtensions(Src, v6);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v7 = (__int64 *)**((_QWORD **)v3 + 26);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v7 != *((__int64 **)v3 + 26) )
  {
    *(_OWORD *)v59 = 0;
    v60 = 0;
    v9 = v63;
    v10 = Src;
    if ( v64 > 7 )
      v10 = (void **)Src[0];
    if ( v63 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v63 > 7 )
    {
      v11 = v63 | 7;
      if ( (v63 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        if ( v11 < 0xA )
          v11 = 10;
        if ( v11 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
        v12 = 2 * (v11 + 1);
        if ( v12 )
        {
LABEL_15:
          _mm_lfence();
          if ( v12 >= 0x1000 )
            v13 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(
                            v12,
                            0x7FFFFFFFFFFFFFFFLL);
          else
            v13 = operator new(v12);
        }
        else
        {
          v13 = 0;
        }
        v59[0] = v13;
        v60.m128i_i64[0] = v9;
        v60.m128i_i64[1] = v11;
        memmove(v13, v10, 2 * v9 + 2);
        v14 = v60.m128i_u64[1];
        v15 = v60.m128i_i64[0];
        goto LABEL_18;
      }
      v11 = 0x7FFFFFFFFFFFFFFELL;
      v12 = -2;
      goto LABEL_15;
    }
    v15 = v63;
    v60.m128i_i64[0] = v63;
    v14 = 7;
    v60.m128i_i64[1] = 7;
    *(_OWORD *)v59 = *(_OWORD *)v10;
LABEL_18:
    v16 = v59;
    v17 = (void **)v59[0];
    if ( v14 > 7 )
      v16 = (void **)v59[0];
    v18 = v59;
    if ( v14 > 7 )
      v18 = (void **)v59[0];
    v19 = (void **)((char *)v18 + 2 * v15);
    v20 = v59;
    if ( v14 > 7 )
      v20 = (void **)v59[0];
    while ( v20 != v19 )
    {
      *(_WORD *)v16 = towlower(*(_WORD *)v20);
      v20 = (void **)((char *)v20 + 2);
      v16 = (void **)((char *)v16 + 2);
      v14 = v60.m128i_u64[1];
      v15 = v60.m128i_i64[0];
      v17 = (void **)v59[0];
    }
    v21 = v59;
    if ( v14 > 7 )
      v21 = v17;
    v22 = 0xCBF29CE484222325uLL;
    v23 = 2 * v15;
    for ( i = 0; i < v23; ++i )
      v22 = 0x100000001B3LL * (*((unsigned __int8 *)v21 + i) ^ (unsigned __int64)v22);
    if ( v14 > 7 )
    {
      v25 = (const struct std::nothrow_t *)(2 * v14 + 2);
      v46 = (unsigned __int64)v25;
      v47 = v17;
      if ( (unsigned __int64)v25 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v47, &v46);
        v25 = (const struct std::nothrow_t *)v46;
        v17 = (void **)v47;
      }
      operator delete(v17, v25);
    }
    v60 = si128;
    LOWORD(v59[0]) = 0;
    v26 = 2 * (v22 & v7[28]);
    v27 = v7[25];
    v28 = *(_QWORD *)(v27 + 16 * (v22 & v7[28]) + 8);
    v29 = v7 + 23;
    if ( v28 != v7[23] )
    {
      v33 = *(_QWORD *)(v27 + 8 * v26);
      while ( 1 )
      {
        v34 = (const WCHAR *)(v28 + 16);
        if ( *(_QWORD *)(v28 + 40) > 7u )
          v34 = *(const WCHAR **)v34;
        v35 = Src;
        if ( v64 > 7 )
          v35 = (void **)Src[0];
        if ( CompareStringOrdinal((LPCWCH)v35, -1, v34, -1, 1) == 2 )
        {
          v29 = v7 + 23;
          goto LABEL_36;
        }
        if ( v28 == v33 )
          break;
        v28 = *(_QWORD *)(v28 + 8);
      }
      v29 = v7 + 23;
    }
    v28 = 0;
LABEL_36:
    if ( v28 )
    {
      if ( v28 != *v29 )
      {
        v47 = 0;
        std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>,0>>::find(
          v28 + 48,
          &v47,
          v65);
        if ( v47 != *(void **)(v28 + 56) )
        {
          v31 = (char *)v47 + 48;
          *((_BYTE *)v47 + 52) = 0;
          v32 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              87,
              (unsigned int)&WPP_37379ce3a908304aafca380d907f5915_Traceguids,
              (_DWORD)v49,
              *(_DWORD *)v31);
            v32 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( *((_DWORD *)v7 + 92) == 1 || !v31[304] )
          {
            if ( *(_DWORD *)v31 )
            {
              if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 0x10) != 0 )
              {
                v45 = v31 + 8;
                if ( *((_QWORD *)v31 + 4) > 7u )
                  v45 = (_QWORD *)*v45;
                WPP_SF_SLd(
                  (unsigned int)v32[2],
                  89,
                  (unsigned int)&WPP_37379ce3a908304aafca380d907f5915_Traceguids,
                  (_DWORD)v45,
                  *(_DWORD *)v31,
                  *((_DWORD *)v7 + 6));
              }
            }
            else
            {
              RealtimeProtection::DlpProcessCache::DlpProcessStateCache::RemoveFileFromProcessCacheUnsafe(
                (_DWORD)v3,
                (_DWORD)v7 + 32,
                (_DWORD)v31 + 8,
                (_DWORD)v7 + 16,
                (__int64)&SystemTimeAsFileTime);
            }
          }
          else
          {
            v36 = (const struct RealtimeProtection::FileUniqueId *)std::optional<RealtimeProtection::FileUniqueId>::value(v31 + 240);
            v37 = (char *)v3 + 552;
            v38 = (_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                              v37,
                              v52,
                              v36);
            *(_BYTE *)(*(_QWORD *)std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Try_emplace<PPID const &,>(
                                    *v38 + 80LL,
                                    v53,
                                    v7 + 2)
                     + 32LL) = 0;
            v39 = (_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                              v37,
                              v54,
                              v36);
            if ( *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Try_emplace<PPID const &,>(
                                          *v39 + 80LL,
                                          v55,
                                          v7 + 2)
                           + 28LL) )
            {
              v3 = v48;
            }
            else
            {
              v43 = (_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                                v37,
                                v56,
                                v36);
              std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Erase<PPID>(
                *v43 + 80LL,
                v7 + 2);
              if ( !*(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(
                                             v37,
                                             v57,
                                             v36)
                              + 96LL) )
                std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Erase<RealtimeProtection::FileUniqueId>(
                  v37,
                  v36);
              v3 = v48;
              if ( !RealtimeProtection::DlpProcessCache::DlpProcessStateCache::IsFileCurrentlyProtectedUnsafe(v48, v36) )
              {
                updated = RealtimeProtection::DlpQuarantineEngine::UpdateQuarantineItemProtectionStatus(
                            (RealtimeProtection::DlpProcessCache::DlpProcessStateCache *)((char *)v3 + 616),
                            v36,
                            0);
                v4 = updated;
                if ( updated < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      88,
                      &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
                      (unsigned int)updated);
                  v4 = 0;
                }
              }
            }
            if ( !*(_DWORD *)v31 )
            {
              RealtimeProtection::DlpProcessCache::DlpProcessStateCache::UpdateRecallCacheOnClose(
                (struct RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor *)(v7 + 4),
                (const struct RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor *)v31);
              std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>,0>>::_Erase<std::wstring>(
                v28 + 48,
                v65);
              if ( !*(_QWORD *)(v28 + 64) )
              {
                v41 = std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>::operator()<std::wstring>(
                        v40,
                        Src);
                v42 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::wstring,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>>>,0>>::_Find_last<std::wstring>(
                                    v7 + 22,
                                    v58,
                                    Src,
                                    v41)
                                + 8);
                if ( v42 )
                {
                  std::_Hash<std::_Umap_traits<unsigned long,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<unsigned long>>>>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<unsigned long>>>>>>,0>>::_Erase_bucket(
                    v7 + 22,
                    v42,
                    v41 & v7[28]);
                  std::list<std::pair<std::wstring const,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>>>::_Unchecked_erase(v7 + 23);
                }
              }
            }
          }
        }
      }
    }
    v7 = (__int64 *)*v7;
    v5 = (RTL_SRWLOCK *)((char *)v3 + 464);
  }
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v65);
  ReleaseSRWLockExclusive(v5);
  if ( v4 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      90,
      &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800335d0  mov     rax, rsp
0x1800335d3  mov     [rax+18h], rbx
0x1800335d7  mov     [rax+20h], rsi
0x1800335db  push    rdi
0x1800335dc  push    r12
0x1800335de  push    r13
0x1800335e0  push    r14
0x1800335e2  push    r15
0x1800335e4  sub     rsp, 160h
0x1800335eb  movaps  xmmword ptr [rax-38h], xmm6
0x1800335ef  mov     rax, cs:__security_cookie
0x1800335f6  xor     rax, rsp
0x1800335f9  mov     [rsp+188h+var_48], rax
0x180033601  mov     rbx, rdx
0x180033604  mov     [rsp+188h+var_140], rdx
0x180033609  mov     r12, rcx
0x18003360c  mov     [rsp+188h+var_148], rcx
0x180033611  xor     edi, edi
0x180033613  mov     r13d, edi
0x180033616  lea     rsi, [rcx+1D0h]
0x18003361d  mov     [rsp+188h+var_130], rsi
0x180033622  mov     rcx, rsi; SRWLock
0x180033625  call    cs:__imp_AcquireSRWLockExclusive
0x18003362b  mov     [rsp+188h+var_128], 1
0x180033630  cmp     [r12+0D8h], rdi
0x180033638  jz      loc_180033C7E
0x18003363e  mov     rdx, rbx
0x180033641  lea     rcx, [rsp+188h+var_68]
0x180033649  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003364e  nop
0x18003364f  lea     rdx, [rsp+188h+var_68]
0x180033657  cmp     [rsp+188h+var_50], 7
0x180033660  cmova   rdx, [rsp+188h+var_68]
0x180033669  lea     rcx, [rsp+188h+Src]
0x180033671  call    ?GetFileExtensions@DlpUtils@RealtimeProtection@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; RealtimeProtection::DlpUtils::GetFileExtensions(wchar_t const *)
0x180033676  nop
0x180033677  mov     qword ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18003367f  lea     rcx, [rsp+188h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180033687  call    cs:__imp_GetSystemTimeAsFileTime
0x18003368d  mov     rbx, [r12+0D0h]
0x180033695  mov     rbx, [rbx]
0x180033698  lea     r15, WPP_GLOBAL_Control
0x18003369f  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800336a7  mov     r8d, 0Ah
0x1800336ad  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1800336b7  mov     rcx, 7FFFFFFFFFFFFFFEh
0x1800336c1  cmp     rbx, [r12+0D0h]
0x1800336c9  jz      loc_1800338CE
0x1800336cf  xorps   xmm0, xmm0
0x1800336d2  movups  xmmword ptr [rsp+188h+var_B0], xmm0
0x1800336da  xorps   xmm1, xmm1
0x1800336dd  movdqu  [rsp+188h+var_A0], xmm1
0x1800336e6  mov     r14, [rsp+188h+var_78]
0x1800336ee  lea     r15, [rsp+188h+Src]
0x1800336f6  cmp     [rsp+188h+var_70], 7
0x1800336ff  cmova   r15, [rsp+188h+Src]
0x180033708  cmp     r14, rcx
0x18003370b  ja      loc_180033C91
0x180033711  cmp     r14, 7
0x180033715  jbe     loc_1800339BF
0x18003371b  mov     rsi, r14
0x18003371e  or      rsi, 7
0x180033722  cmp     rsi, rcx
0x180033725  ja      loc_1800339EE
0x18003372b  cmp     rsi, r8
0x18003372e  cmovb   rsi, r8
0x180033732  lea     rcx, [rsi+1]
0x180033736  cmp     rcx, rdx
0x180033739  ja      loc_180033C9D
0x18003373f  add     rcx, rcx; Size
0x180033742  jz      loc_180033A64
0x180033748  lfence
0x18003374b  cmp     rcx, 1000h
0x180033752  jnb     loc_180033A5A
0x180033758  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003375d  mov     [rsp+188h+var_B0], rax
0x180033765  mov     qword ptr [rsp+188h+var_A0], r14
0x18003376d  mov     qword ptr [rsp+188h+var_A0+8], rsi
0x180033775  lea     r8, ds:2[r14*2]; Size
0x18003377d  mov     rdx, r15; Src
0x180033780  mov     rcx, rax; void *
0x180033783  call    memmove
0x180033788  mov     rcx, qword ptr [rsp+188h+var_A0+8]
0x180033790  mov     rdx, qword ptr [rsp+188h+var_A0]
0x180033798  lea     r14, [rsp+188h+var_B0]
0x1800337a0  mov     r8, [rsp+188h+var_B0]
0x1800337a8  cmp     rcx, 7
0x1800337ac  cmova   r14, r8
0x1800337b0  lea     rax, [rsp+188h+var_B0]
0x1800337b8  cmova   rax, r8
0x1800337bc  lea     r15, [rax+rdx*2]
0x1800337c0  lea     rsi, [rsp+188h+var_B0]
0x1800337c8  cmova   rsi, r8
0x1800337cc  cmp     rsi, r15
0x1800337cf  jz      short loc_1800337FF
0x1800337d1  movzx   ecx, word ptr [rsi]; C
0x1800337d4  call    towlower
0x1800337d9  mov     [r14], ax
0x1800337dd  add     rsi, 2
0x1800337e1  add     r14, 2
0x1800337e5  mov     rcx, qword ptr [rsp+188h+var_A0+8]
0x1800337ed  mov     rdx, qword ptr [rsp+188h+var_A0]
0x1800337f5  mov     r8, [rsp+188h+var_B0]
0x1800337fd  jmp     short loc_1800337CC
0x1800337ff  lea     r9, [rsp+188h+var_B0]
0x180033807  cmp     rcx, 7
0x18003380b  cmova   r9, r8
0x18003380f  mov     rsi, 0CBF29CE484222325h
0x180033819  lea     r10, [rdx+rdx]
0x18003381d  mov     rdx, rdi
0x180033820  test    r10, r10
0x180033823  jz      short loc_180033843
0x180033825  movzx   eax, byte ptr [rdx+r9]
0x18003382a  xor     rsi, rax
0x18003382d  mov     r11, 100000001B3h
0x180033837  imul    rsi, r11
0x18003383b  inc     rdx
0x18003383e  cmp     rdx, r10
0x180033841  jb      short loc_180033825
0x180033843  cmp     rcx, 7
0x180033847  jbe     short loc_180033870
0x180033849  lea     rdx, ds:2[rcx*2]; struct std::nothrow_t *
0x180033851  mov     [rsp+188h+var_158], rdx
0x180033856  mov     [rsp+188h+var_150], r8
0x18003385b  cmp     rdx, 1000h
0x180033862  jnb     loc_180033C60
0x180033868  mov     rcx, r8; void *
0x18003386b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180033870  movdqu  [rsp+188h+var_A0], xmm6
0x180033879  mov     word ptr [rsp+188h+var_B0], di
0x180033881  mov     rax, [rbx+0E0h]
0x180033888  and     rax, rsi
0x18003388b  add     rax, rax
0x18003388e  mov     rcx, [rbx+0C8h]
0x180033895  mov     rsi, [rcx+rax*8+8]
0x18003389a  lea     rdx, [rbx+0B8h]
0x1800338a1  cmp     rsi, [rdx]
0x1800338a4  jnz     loc_1800339FA
0x1800338aa  mov     rsi, rdi
0x1800338ad  test    rsi, rsi
0x1800338b0  jz      short loc_1800338B7
0x1800338b2  cmp     rsi, [rdx]
0x1800338b5  jnz     short loc_180033932
0x1800338b7  lea     r15, WPP_GLOBAL_Control
0x1800338be  mov     rbx, [rbx]
0x1800338c1  lea     rsi, [r12+1D0h]
0x1800338c9  jmp     loc_1800336A7
0x1800338ce  lea     rcx, [rsp+188h+Src]; void *
0x1800338d6  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800338db  nop
0x1800338dc  lea     rcx, [rsp+188h+var_68]; void *
0x1800338e4  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800338e9  nop
0x1800338ea  mov     rcx, rsi; SRWLock
0x1800338ed  call    cs:__imp_ReleaseSRWLockExclusive
0x1800338f3  nop
0x1800338f4  test    r13d, r13d
0x1800338f7  js      loc_180033D31
0x1800338fd  mov     eax, r13d
0x180033900  mov     rcx, [rsp+188h+var_48]
0x180033908  xor     rcx, rsp; StackCookie
0x18003390b  call    __security_check_cookie
0x180033910  lea     r11, [rsp+188h+var_28]
0x180033918  mov     rbx, [r11+40h]
0x18003391c  mov     rsi, [r11+48h]
0x180033920  movaps  xmm6, xmmword ptr [r11-10h]
0x180033925  mov     rsp, r11
0x180033928  pop     r15
0x18003392a  pop     r14
0x18003392c  pop     r13
0x18003392e  pop     r12
0x180033930  pop     rdi
0x180033931  retn
0x180033932  mov     [rsp+188h+var_150], rdi
0x180033937  lea     rcx, [rsi+30h]
0x18003393b  lea     r8, [rsp+188h+var_68]
0x180033943  lea     rdx, [rsp+188h+var_150]
0x180033948  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>,0>>::find(std::wstring const &)
0x18003394d  mov     rax, [rsp+188h+var_150]
0x180033952  cmp     rax, [rsi+38h]
0x180033956  jz      loc_1800338B7
0x18003395c  lea     r14, [rax+30h]
0x180033960  mov     [r14+4], dil
0x180033964  mov     rcx, cs:WPP_GLOBAL_Control
0x18003396b  lea     r15, WPP_GLOBAL_Control
0x180033972  cmp     rcx, r15
0x180033975  jz      short loc_180033981
0x180033977  test    byte ptr [rcx+1Ch], 10h
0x18003397b  jnz     loc_180033B99
0x180033981  lea     rdx, [rbx+20h]
0x180033985  cmp     dword ptr [rdx+150h], 1
0x18003398c  jnz     loc_180033A78
0x180033992  mov     eax, [r14]
0x180033995  test    eax, eax
0x180033997  jnz     loc_180033CCC
0x18003399d  lea     r9, [rbx+10h]
0x1800339a1  lea     r8, [r14+8]
0x1800339a5  lea     rax, [rsp+188h+SystemTimeAsFileTime]
0x1800339ad  mov     qword ptr [rsp+188h+bIgnoreCase], rax
0x1800339b2  mov     rcx, r12
0x1800339b5  call    ?RemoveFileFromProcessCacheUnsafe@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@AEAAXAEAUProcessEnforcementDescriptor@123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUPPID@@AEBU_FILETIME@@@Z; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::RemoveFileFromProcessCacheUnsafe(RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor &,std::wstring const &,PPID const &,_FILETIME const &)
0x1800339ba  jmp     loc_1800338BE
0x1800339bf  mov     rdx, [rsp+188h+var_78]
0x1800339c7  mov     qword ptr [rsp+188h+var_A0], rdx
0x1800339cf  mov     ecx, 7
0x1800339d4  mov     qword ptr [rsp+188h+var_A0+8], rcx
0x1800339dc  movups  xmm0, xmmword ptr [r15]
0x1800339e0  movdqu  xmmword ptr [rsp+188h+var_B0], xmm0
0x1800339e9  jmp     loc_180033798
0x1800339ee  mov     rsi, rcx
0x1800339f1  lea     rcx, [rdx+rdx]
0x1800339f5  jmp     loc_180033748
0x1800339fa  mov     r14, [rcx+rax*8]
0x1800339fe  lea     r8, [rsi+10h]; lpString2
0x180033a02  cmp     qword ptr [rsi+28h], 7
0x180033a07  ja      short loc_180033A55
0x180033a09  lea     rcx, [rsp+188h+Src]
0x180033a11  cmp     [rsp+188h+var_70], 7
0x180033a1a  cmova   rcx, [rsp+188h+Src]; lpString1
0x180033a23  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x180033a2b  or      eax, 0FFFFFFFFh
0x180033a2e  mov     r9d, eax; cchCount2
0x180033a31  mov     edx, eax; cchCount1
0x180033a33  call    cs:__imp_CompareStringOrdinal
0x180033a39  cmp     eax, 2
0x180033a3c  jnz     short loc_180033A4A
0x180033a3e  lea     rdx, [rbx+0B8h]
0x180033a45  jmp     loc_1800338AD
0x180033a4a  cmp     rsi, r14
0x180033a4d  jz      short loc_180033A6C
0x180033a4f  mov     rsi, [rsi+8]
0x180033a53  jmp     short loc_1800339FE
0x180033a55  mov     r8, [r8]
0x180033a58  jmp     short loc_180033A09
0x180033a5a  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x180033a5f  jmp     loc_18003375D
0x180033a64  mov     rax, rdi
0x180033a67  jmp     loc_18003375D
0x180033a6c  lea     rdx, [rbx+0B8h]
0x180033a73  jmp     loc_1800338AA
0x180033a78  cmp     [r14+130h], dil
0x180033a7f  jz      loc_180033992
0x180033a85  lea     rcx, [r14+0F0h]
0x180033a8c  call    ?value@?$optional@VFileUniqueId@RealtimeProtection@@@std@@QEGBAAEBVFileUniqueId@RealtimeProtection@@XZ; std::optional<RealtimeProtection::FileUniqueId>::value(void)
0x180033a91  mov     r15, rax
0x180033a94  add     r12, 228h
0x180033a9b  mov     r8, rax
0x180033a9e  lea     rdx, [rsp+188h+var_120]
0x180033aa3  mov     rcx, r12
0x180033aa6  call    ??$_Try_emplace@AEBVFileUniqueId@RealtimeProtection@@$$V@?$_Hash@V?$_Umap_traits@VFileUniqueId@RealtimeProtection@@UFileProtectionStatus@DlpProcessStateCache@DlpProcessCache@2@V?$_Uhash_compare@VFileUniqueId@RealtimeProtection@@UFileUniqueIdHasher@2@UFileUniqueIdComparer@2@@std@@V?$allocator@U?$pair@$$CBVFileUniqueId@RealtimeProtection@@UFileProtectionStatus@DlpProcessStateCache@DlpProcessCache@2@@std@@@7@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBVFileUniqueId@RealtimeProtection@@UFileProtectionStatus@DlpProcessStateCache@DlpProcessCache@2@@std@@PEAX@std@@_N@1@AEBVFileUniqueId@RealtimeProtection@@@Z; std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(RealtimeProtection::FileUniqueId const &)
0x180033aab  lea     r8, [rbx+10h]
0x180033aaf  mov     rcx, [rax]
0x180033ab2  add     rcx, 50h ; 'P'
0x180033ab6  lea     rdx, [rsp+188h+var_110]
0x180033abb  call    ??$_Try_emplace@AEBUPPID@@$$V@?$_Hash@V?$_Umap_traits@UPPID@@UFileRefCount@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UFileRefCount@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUPPID@@UFileRefCount@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@_N@1@AEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Try_emplace<PPID const &,>(PPID const &)
0x180033ac0  mov     rax, [rax]
0x180033ac3  mov     [rax+20h], dil
0x180033ac7  mov     r8, r15
0x180033aca  lea     rdx, [rsp+188h+var_100]
0x180033ad2  mov     rcx, r12
0x180033ad5  call    ??$_Try_emplace@AEBVFileUniqueId@RealtimeProtection@@$$V@?$_Hash@V?$_Umap_traits@VFileUniqueId@RealtimeProtection@@UFileProtectionStatus@DlpProcessStateCache@DlpProcessCache@2@V?$_Uhash_compare@VFileUniqueId@RealtimeProtection@@UFileUniqueIdHasher@2@UFileUniqueIdComparer@2@@std@@V?$allocator@U?$pair@$$CBVFileUniqueId@RealtimeProtection@@UFileProtectionStatus@DlpProcessStateCache@DlpProcessCache@2@@std@@@7@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBVFileUniqueId@RealtimeProtection@@UFileProtectionStatus@DlpProcessStateCache@DlpProcessCache@2@@std@@PEAX@std@@_N@1@AEBVFileUniqueId@RealtimeProtection@@@Z; std::_Hash<std::_Umap_traits<RealtimeProtection::FileUniqueId,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus,std::_Uhash_compare<RealtimeProtection::FileUniqueId,RealtimeProtection::FileUniqueIdHasher,RealtimeProtection::FileUniqueIdComparer>,std::allocator<std::pair<RealtimeProtection::FileUniqueId const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileProtectionStatus>>,0>>::_Try_emplace<RealtimeProtection::FileUniqueId const &,>(RealtimeProtection::FileUniqueId const &)
0x180033ada  mov     rcx, [rax]
0x180033add  add     rcx, 50h ; 'P'
0x180033ae1  lea     r8, [rbx+10h]
0x180033ae5  lea     rdx, [rsp+188h+var_F0]
0x180033aed  call    ??$_Try_emplace@AEBUPPID@@$$V@?$_Hash@V?$_Umap_traits@UPPID@@UFileRefCount@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UFileRefCount@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUPPID@@UFileRefCount@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@PEAX@std@@_N@1@AEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileRefCount>>,0>>::_Try_emplace<PPID const &,>(PPID const &)
0x180033af2  mov     rax, [rax]
0x180033af5  cmp     [rax+1Ch], edi
0x180033af8  jz      loc_180033BC6
0x180033afe  mov     r12, [rsp+188h+var_148]
0x180033b03  lea     r15, WPP_GLOBAL_Control
0x180033b0a  cmp     [r14], edi
0x180033b0d  jnz     loc_1800338BE
0x180033b13  mov     rdx, r14; struct RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor *
0x180033b16  lea     rcx, [rbx+20h]; struct RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor *
0x180033b1a  call    ?UpdateRecallCacheOnClose@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@CAXAEAUProcessEnforcementDescriptor@123@AEBUFileEnforcementDescriptor@123@@Z; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::UpdateRecallCacheOnClose(RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor &,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor const &)
0x180033b1f  lea     rdx, [rsp+188h+var_68]
0x180033b27  lea     rcx, [rsi+30h]
0x180033b2b  call    ??$_Erase@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@$0A@@std@@@std@@AEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>,0>>::_Erase<std::wstring>(std::wstring const &)
0x180033b30  cmp     [rsi+40h], rdi
0x180033b34  jnz     loc_1800338BE
0x180033b3a  lea     rsi, [rbx+0B0h]
0x180033b41  lea     rdx, [rsp+188h+Src]
0x180033b49  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@std@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>::operator()<std::wstring>(std::wstring const &)
0x180033b4e  mov     r14, rax
0x180033b51  mov     r9, rax
0x180033b54  lea     r8, [rsp+188h+Src]
0x180033b5c  lea     rdx, [rsp+188h+var_C0]
0x180033b64  mov     rcx, rsi
0x180033b67  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@UCaseInsensitiveHasher@DlpUtils@6@UCStrOrdinalCompEqual@86@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHasher@DlpUtils@RealtimeProtection@@UCStrOrdinalCompEqual@45@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@UCaseInsensitiveHasher@DlpUtils@6@UCStrOrdinalCompEqual@86@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@UCaseInsensitiveHasher@DlpUtils@6@UCStrOrdinalCompEqual@86@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>,std::_Uhash_compare<std::wstring,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual>,std::allocator<std::pair<std::wstring const,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180033b6c  mov     rdx, [rax+8]
0x180033b70  test    rdx, rdx
0x180033b73  jz      loc_1800338BE
0x180033b79  mov     r8, [rsi+30h]
0x180033b7d  and     r8, r14
0x180033b80  mov     rcx, rsi
0x180033b83  call    ?_Erase_bucket@?$_Hash@V?$_Umap_traits@KU?$pair@USaveAsCandidate@DlpSaveAsCache@Dlp@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKU?$pair@USaveAsCandidate@DlpSaveAsCache@Dlp@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@$$CBKU?$pair@USaveAsCandidate@DlpSaveAsCache@Dlp@@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@@std@@@std@@PEAX@2@_K@Z; std::_Hash<std::_Umap_traits<ulong,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<ulong>>>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<ulong>>>>>>,0>>::_Erase_bucket(std::_List_node<std::pair<ulong const,std::pair<Dlp::DlpSaveAsCache::SaveAsCandidate,std::_List_iterator<std::_List_val<std::_List_simple_types<ulong>>>>>,void *> *,unsigned __int64)
0x180033b88  lea     rcx, [rbx+0B8h]
0x180033b8f  call    ?_Unchecked_erase@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@UCaseInsensitiveHasher@DlpUtils@6@UCStrOrdinalCompEqual@86@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@UCaseInsensitiveHasher@DlpUtils@6@UCStrOrdinalCompEqual@86@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@@2@@std@@@2@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@UCaseInsensitiveHasher@DlpUtils@6@UCStrOrdinalCompEqual@86@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFileEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@2@@2@@std@@PEAX@2@QEAU32@@Z; std::list<std::pair<std::wstring const,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>>>::_Unchecked_erase(std::_List_node<std::pair<std::wstring const,std::unordered_map<std::wstring,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor,RealtimeProtection::DlpUtils::CaseInsensitiveHasher,RealtimeProtection::DlpUtils::CStrOrdinalCompEqual,std::allocator<std::pair<std::wstring const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::FileEnforcementDescriptor>>>>,void *> * const)
0x180033b94  jmp     loc_1800338BE
  ... truncated ...
```
