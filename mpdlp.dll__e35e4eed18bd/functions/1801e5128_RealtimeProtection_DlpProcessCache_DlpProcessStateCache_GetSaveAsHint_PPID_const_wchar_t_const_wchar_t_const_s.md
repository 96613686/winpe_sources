# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetSaveAsHint(PPID const &,wchar_t const *,wchar_t const *,std::vector<RealtimeProtection::FileProps,std::allocator<RealtimeProtection::FileProps>> const &,std::vector<RealtimeProtection::FileProps,std::allocator<RealtimeProtection::FileProps>> &,std::shared_ptr<RealtimeProtection::DocumentDescriptor> &)

- ea: `0x1801e5128`
- end: `0x1801e5c61`
- name: `?GetSaveAsHint@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEBAJAEBUPPID@@PEB_W1AEBV?$vector@UFileProps@RealtimeProtection@@V?$allocator@UFileProps@RealtimeProtection@@@std@@@std@@AEAV56@AEAV?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@6@@Z`
- size: `2873`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1801d7ef4`

## callees

- `0x18001bad0`
- `0x180023f30`
- `0x180028d80`
- `0x180029290`
- `0x180029590`
- `0x18002c150`
- `0x180034420`
- `0x1800374f8`
- `0x180037afc`
- `0x180038450`
- `0x1800398a0`
- `0x1800442d0`
- `0x18004b3bc`
- `0x18004de90`
- `0x1800542d0`
- `0x18006aa2c`
- `0x18006f3e4`
- `0x180079034`
- `0x1800799c8`
- `0x18007f5fc`
- `0x1800809d0`
- `0x1800839a0`
- `0x180089510`
- `0x18008ac70`
- `0x18008f660`
- `0x1800943fc`
- `0x18009faa0`
- `0x1800a1a28`
- `0x1800a3548`
- `0x1800a440c`
- `0x1800a5ff4`
- `0x18010cb40`
- `0x18010ce3c`
- `0x180119740`
- `0x1801e063c`
- `0x1801e1ac4`
- `0x1801e5128`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1801e5740`
- `KERNEL32!CompareStringOrdinal` at `0x1801e58f2`
- `KERNEL32!CompareStringOrdinal` at `0x1801e5740`
- `KERNEL32!CompareStringOrdinal` at `0x1801e58f2`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e556f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5633`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e56b6`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e587e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5a3c`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5a97`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5b12`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5b4d`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5b9c`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5be1`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e556f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5633`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e56b6`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e587e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5a3c`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5a97`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5b12`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5b4d`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5b9c`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801e5be1`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetSaveAsHint(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        const WCHAR **a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // rax
  char v15; // r14
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  char *v23; // rdi
  __int64 **v24; // r12
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  const WCHAR *v29; // r14
  const WCHAR *v30; // r15
  __int64 v31; // r13
  __int64 v32; // rbx
  const WCHAR *v33; // r8
  const WCHAR *v34; // rcx
  wchar_t **v35; // r9
  unsigned int *v36; // rdx
  void *v37; // rbx
  const struct std::nothrow_t *v38; // rdx
  __int64 v39; // r14
  __int64 v40; // r13
  const WCHAR *v41; // r15
  const WCHAR *v42; // r12
  const WCHAR *v43; // r8
  const WCHAR *v44; // rcx
  wchar_t **v45; // r9
  unsigned int *v46; // rdx
  void *v47; // rbx
  const struct std::nothrow_t *v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rbx
  int DestinationNtName; // [rsp+30h] [rbp-3B8h]
  void *Src; // [rsp+38h] [rbp-3B0h] BYREF
  __int64 v53; // [rsp+40h] [rbp-3A8h] BYREF
  __int64 v54; // [rsp+48h] [rbp-3A0h]
  __int64 v55; // [rsp+50h] [rbp-398h]
  const WCHAR **v56; // [rsp+58h] [rbp-390h]
  __int64 v57; // [rsp+60h] [rbp-388h]
  _BYTE v58[32]; // [rsp+70h] [rbp-378h] BYREF
  _BYTE v59[32]; // [rsp+90h] [rbp-358h] BYREF
  _BYTE v60[32]; // [rsp+B0h] [rbp-338h] BYREF
  PSRWLOCK SRWLock[4]; // [rsp+D0h] [rbp-318h] BYREF
  _QWORD v62[4]; // [rsp+F0h] [rbp-2F8h] BYREF
  __int128 v63; // [rsp+110h] [rbp-2D8h] BYREF
  __int64 v64; // [rsp+120h] [rbp-2C8h]
  __int64 v65; // [rsp+128h] [rbp-2C0h]
  _BYTE v66[32]; // [rsp+130h] [rbp-2B8h] BYREF
  _BYTE v67[32]; // [rsp+150h] [rbp-298h] BYREF
  _BYTE v68[48]; // [rsp+170h] [rbp-278h] BYREF
  _BYTE v69[64]; // [rsp+1A0h] [rbp-248h] BYREF
  unsigned int v70[6]; // [rsp+1E0h] [rbp-208h] BYREF
  unsigned __int64 v71; // [rsp+1F8h] [rbp-1F0h]

  v57 = a2;
  v54 = a6;
  v56 = a5;
  v55 = a7;
  DestinationNtName = 0;
  *(_OWORD *)SRWLock = 0;
  std::shared_ptr<RealtimeProtection::DocumentDescriptor>::operator=(a7, SRWLock);
  if ( SRWLock[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)SRWLock[1]);
  if ( !a3 )
    return 1;
  std::wstring::wstring(v62, a3);
  if ( std::wstring::find(v62, L"LanmanRedirector") != -1 )
  {
    std::wstring::wstring(v66, a3);
    RealtimeProtection::DlpPathCache::GetDosPath(v68, v66);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v66);
    if ( v68[32] )
    {
      v12 = std::optional<std::wstring>::value(v68);
      std::wstring::wstring(SRWLock, v12);
      std::wstring::erase(SRWLock, 0, 1);
      v13 = std::operator+<wchar_t>(v67);
      std::wstring::operator=(v62, v13);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v67);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(SRWLock);
    }
    std::optional<std::wstring>::~optional<std::wstring>(v68);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v14 = v62;
    if ( v62[3] > 7u )
      v14 = (_QWORD *)v62[0];
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      196,
      (unsigned int)&WPP_37379ce3a908304aafca380d907f5915_Traceguids,
      a3,
      (__int64)v14);
  }
  v63 = 0;
  v64 = 0;
  v65 = 7;
  LOWORD(v63) = 0;
  v15 = 0;
  if ( !wcsicmp(a4, L"powerpnt.exe") || !wcsicmp(a4, L"winword.exe") || !wcsicmp(a4, L"excel.exe") )
  {
    std::wstring::wstring(SRWLock, v62);
    v16 = std::wstring::rfind(SRWLock, L".");
    if ( v16 != -1 )
    {
      std::wstring::substr(SRWLock, v66, v16 + 1, -1);
      v15 = std::wstring::_Equal(v66, L"tmp");
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v66);
    }
    v17 = std::wstring::rfind(SRWLock, L"\\");
    v18 = v17;
    if ( v17 != -1 )
    {
      std::wstring::substr(SRWLock, v66, v17 + 1, -1);
      std::wstring::wstring(v67, L"~$");
      if ( !std::wstring::find(v66, v67, 0) )
      {
        v19 = std::wstring::substr(v66, v68, 2, -1);
        v20 = std::wstring::substr(SRWLock, v60, 0, v18);
        v21 = std::operator+<wchar_t>(v59, v20, L"\\");
        v22 = std::operator+<wchar_t>(v58, v21, v19);
        std::wstring::operator=(&v63, v22);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v58);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v59);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v60);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v68);
      }
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v67);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v66);
    }
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(SRWLock);
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>(
    SRWLock,
    a1 + 464);
  Src = 0;
  std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(
    a1 + 200,
    &Src,
    a2);
  v23 = (char *)Src;
  if ( Src != *(void **)(a1 + 208) )
  {
    v24 = (__int64 **)((char *)Src + 552);
    v25 = std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::_Find<std::wstring>(
            (char *)Src + 552,
            v62);
    if ( (__int64 *)v25 == *v24 )
    {
      v26 = **((_QWORD **)v23 + 71);
      v53 = v26;
      while ( !*(_BYTE *)(v26 + 25) )
      {
        v27 = v26 + 32;
        Src = 0;
        std::find_if_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___________lambda_4662e67aacd32013e3884eba9146ff6b___(
          &Src,
          *(_QWORD *)(v26 + 64),
          *(_QWORD *)(v26 + 72),
          v62);
        if ( Src != *(void **)(v27 + 40) )
        {
          v28 = std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::_Find<std::wstring>(
                  v23 + 552,
                  v27);
          if ( (__int64 *)v28 != *v24 )
          {
            std::shared_ptr<Dlp::TelemetryFilterManager::DlpTelemetryFilter>::operator=(a7, v28 + 64);
            if ( !LOBYTE(SRWLock[1]) )
              goto LABEL_110;
            goto LABEL_109;
          }
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v53);
        v26 = v53;
      }
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_37379ce3a908304aafca380d907f5915_Traceguids);
        if ( LOBYTE(SRWLock[1]) )
          ReleaseSRWLockShared(SRWLock[0]);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v63);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v62);
        return 2147943623LL;
      }
      v29 = *v56;
      v30 = v56[1];
      v31 = v54;
      while ( v29 != v30 )
      {
        v32 = **v24;
        v53 = v32;
        while ( !*(_BYTE *)(v32 + 25) )
        {
          v33 = (const WCHAR *)(*(_QWORD *)(v32 + 64) + 8LL);
          if ( *(_QWORD *)(*(_QWORD *)(v32 + 64) + 32LL) > 7u )
            v33 = *(const WCHAR **)v33;
          v34 = v29;
          if ( *((_QWORD *)v29 + 3) > 7u )
            v34 = *(const WCHAR **)v29;
          if ( CompareStringOrdinal(v34, -1, v33, -1, 1) == 2 )
          {
            RealtimeProtection::FileProps::FileProps(
              (RealtimeProtection::FileProps *)v69,
              (const struct RealtimeProtection::FileProps *)v29);
            std::wstring::operator=(v70, (void *)(*(_QWORD *)(v32 + 64) + 40LL));
            Src = 0;
            v36 = v70;
            if ( v71 > 7 )
              LODWORD(v36) = v70[0];
            DestinationNtName = RealtimeProtection::DlpUtils::GetDestinationNtName(
                                  (RealtimeProtection::DlpUtils *)*(unsigned int *)(v57 + 8),
                                  (unsigned int)v36,
                                  (const wchar_t *)&Src,
                                  v35);
            v37 = Src;
            if ( DestinationNtName >= 0 )
              std::wstring::assign(v70, Src);
            if ( *(_QWORD *)(v31 + 8) == *(_QWORD *)(v31 + 16) )
            {
              std::vector<RealtimeProtection::FileProps>::_Emplace_reallocate<RealtimeProtection::FileProps const &>(
                v31,
                *(_QWORD *)(v31 + 8),
                v69);
            }
            else
            {
              RealtimeProtection::FileProps::FileProps(
                *(RealtimeProtection::FileProps **)(v31 + 8),
                (const struct RealtimeProtection::FileProps *)v69);
              *(_QWORD *)(v31 + 8) += 512LL;
            }
            if ( v37 )
              operator delete(v37, v38);
            RealtimeProtection::FileProps::~FileProps((RealtimeProtection::FileProps *)v69);
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v53);
          v32 = v53;
        }
        v29 += 256;
      }
      if ( *(_QWORD *)v31 == *(_QWORD *)(v31 + 8) )
      {
        v39 = *((_QWORD *)v23 + 75);
        v40 = *((_QWORD *)v23 + 76);
        if ( v40 - v39 == 16 )
        {
          std::shared_ptr<Dlp::TelemetryFilterManager::DlpTelemetryFilter>::operator=(v55, *((_QWORD *)v23 + 75));
          if ( !LOBYTE(SRWLock[1]) )
            goto LABEL_110;
        }
        else
        {
          while ( v39 != v40 )
          {
            v41 = *v56;
            v42 = v56[1];
            while ( v41 != v42 )
            {
              v43 = (const WCHAR *)(*(_QWORD *)v39 + 8LL);
              if ( *(_QWORD *)(*(_QWORD *)v39 + 32LL) > 7u )
                v43 = *(const WCHAR **)v43;
              v44 = v41;
              if ( *((_QWORD *)v41 + 3) > 7u )
                v44 = *(const WCHAR **)v41;
              if ( CompareStringOrdinal(v44, -1, v43, -1, 1) == 2 )
              {
                RealtimeProtection::FileProps::FileProps(
                  (RealtimeProtection::FileProps *)v69,
                  (const struct RealtimeProtection::FileProps *)v41);
                std::wstring::operator=(v70, (void *)(*(_QWORD *)v39 + 40LL));
                Src = 0;
                v46 = v70;
                if ( v71 > 7 )
                  LODWORD(v46) = v70[0];
                DestinationNtName = RealtimeProtection::DlpUtils::GetDestinationNtName(
                                      (RealtimeProtection::DlpUtils *)*(unsigned int *)(v57 + 8),
                                      (unsigned int)v46,
                                      (const wchar_t *)&Src,
                                      v45);
                v47 = Src;
                if ( DestinationNtName >= 0 )
                  std::wstring::assign(v70, Src);
                if ( *(_QWORD *)(v54 + 8) == *(_QWORD *)(v54 + 16) )
                {
                  std::vector<RealtimeProtection::FileProps>::_Emplace_reallocate<RealtimeProtection::FileProps const &>(
                    v54,
                    *(_QWORD *)(v54 + 8),
                    v69);
                }
                else
                {
                  RealtimeProtection::FileProps::FileProps(
                    *(RealtimeProtection::FileProps **)(v54 + 8),
                    (const struct RealtimeProtection::FileProps *)v69);
                  *(_QWORD *)(v54 + 8) += 512LL;
                }
                if ( v47 )
                  operator delete(v47, v48);
                RealtimeProtection::FileProps::~FileProps((RealtimeProtection::FileProps *)v69);
              }
              v41 += 256;
            }
            v39 += 16;
          }
          if ( *(_QWORD *)v54 != *(_QWORD *)(v54 + 8) )
          {
            if ( LOBYTE(SRWLock[1]) )
              ReleaseSRWLockShared(SRWLock[0]);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v63);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v62);
            if ( DestinationNtName >= 0 )
              return 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                200,
                &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
                (unsigned int)DestinationNtName);
            return (unsigned int)DestinationNtName;
          }
          if ( !v64
            || (v49 = std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::_Find<std::wstring>(
                        v23 + 552,
                        &v63),
                v49 == *((_QWORD *)v23 + 69)) )
          {
            v50 = std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::_Find<std::wstring>(
                    v23 + 584,
                    v62);
            if ( v50 == *((_QWORD *)v23 + 73) )
            {
              if ( LOBYTE(SRWLock[1]) )
                ReleaseSRWLockShared(SRWLock[0]);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v63);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v62);
              return 2147943568LL;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, &WPP_37379ce3a908304aafca380d907f5915_Traceguids);
            std::shared_ptr<Dlp::TelemetryFilterManager::DlpTelemetryFilter>::operator=(v55, v50 + 64);
            if ( !LOBYTE(SRWLock[1]) )
              goto LABEL_110;
          }
          else
          {
            std::shared_ptr<Dlp::TelemetryFilterManager::DlpTelemetryFilter>::operator=(v55, v49 + 64);
            if ( !LOBYTE(SRWLock[1]) )
              goto LABEL_110;
          }
        }
      }
      else if ( !LOBYTE(SRWLock[1]) )
      {
        goto LABEL_110;
      }
    }
    else
    {
      std::shared_ptr<Dlp::TelemetryFilterManager::DlpTelemetryFilter>::operator=(a7, v25 + 64);
      if ( !LOBYTE(SRWLock[1]) )
      {
LABEL_110:
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v63);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v62);
        return 0;
      }
    }
LABEL_109:
    ReleaseSRWLockShared(SRWLock[0]);
    goto LABEL_110;
  }
  if ( LOBYTE(SRWLock[1]) )
    ReleaseSRWLockShared(SRWLock[0]);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v63);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v62);
  return 1;
}

```

## disassembly

```asm
0x1801e5128  push    rbx
0x1801e512a  push    rsi
0x1801e512b  push    rdi
0x1801e512c  push    r12
0x1801e512e  push    r13
0x1801e5130  push    r14
0x1801e5132  push    r15
0x1801e5134  sub     rsp, 3B0h
0x1801e513b  mov     rax, cs:__security_cookie
0x1801e5142  xor     rax, rsp
0x1801e5145  mov     [rsp+3E8h+var_48], rax
0x1801e514d  mov     rdi, r9
0x1801e5150  mov     rbx, r8
0x1801e5153  mov     r12, rdx
0x1801e5156  mov     [rsp+3E8h+var_388], rdx
0x1801e515b  mov     r15, rcx
0x1801e515e  mov     rcx, [rsp+3E8h+arg_28]
0x1801e5166  mov     [rsp+3E8h+var_3A0], rcx
0x1801e516b  mov     rax, [rsp+3E8h+arg_20]
0x1801e5173  mov     [rsp+3E8h+var_390], rax
0x1801e5178  mov     r13, [rsp+3E8h+arg_30]
0x1801e5180  mov     [rsp+3E8h+var_398], r13
0x1801e5185  xor     esi, esi
0x1801e5187  mov     [rsp+3E8h+var_3B8], esi
0x1801e518b  xorps   xmm0, xmm0
0x1801e518e  movdqu  xmmword ptr [rsp+3E8h+SRWLock], xmm0
0x1801e5197  lea     rdx, [rsp+3E8h+SRWLock]
0x1801e519f  mov     rcx, r13
0x1801e51a2  call    ??4?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<RealtimeProtection::DocumentDescriptor>::operator=(std::shared_ptr<RealtimeProtection::DocumentDescriptor> &&)
0x1801e51a7  mov     rcx, [rsp+3E8h+SRWLock+8]; this
0x1801e51af  test    rcx, rcx
0x1801e51b2  jz      short loc_1801E51B9
0x1801e51b4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801e51b9  test    rbx, rbx
0x1801e51bc  jnz     short loc_1801E51C6
0x1801e51be  lea     eax, [rbx+1]
0x1801e51c1  jmp     loc_1801E5C3E
0x1801e51c6  mov     rdx, rbx
0x1801e51c9  lea     rcx, [rsp+3E8h+var_2F8]
0x1801e51d1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801e51d6  nop
0x1801e51d7  lea     rdx, aLanmanredirect; "LanmanRedirector"
0x1801e51de  lea     rcx, [rsp+3E8h+var_2F8]
0x1801e51e6  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find(wchar_t const * const,unsigned __int64)
0x1801e51eb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801e51ef  jz      loc_1801E52B3
0x1801e51f5  mov     rdx, rbx
0x1801e51f8  lea     rcx, [rsp+3E8h+var_2B8]
0x1801e5200  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801e5205  lea     rdx, [rsp+3E8h+var_2B8]
0x1801e520d  lea     rcx, [rsp+3E8h+var_278]
0x1801e5215  call    ?GetDosPath@DlpPathCache@RealtimeProtection@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; RealtimeProtection::DlpPathCache::GetDosPath(std::wstring const &)
0x1801e521a  nop
0x1801e521b  lea     rcx, [rsp+3E8h+var_2B8]; void *
0x1801e5223  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e5228  cmp     [rsp+3E8h+var_258], sil
0x1801e5230  jz      short loc_1801E52A6
0x1801e5232  lea     rcx, [rsp+3E8h+var_278]
0x1801e523a  call    ?value@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEGAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1801e523f  mov     rdx, rax
0x1801e5242  lea     rcx, [rsp+3E8h+SRWLock]
0x1801e524a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801e524f  nop
0x1801e5250  xor     edx, edx
0x1801e5252  lea     r8d, [rdx+1]
0x1801e5256  lea     rcx, [rsp+3E8h+SRWLock]
0x1801e525e  call    ?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x1801e5263  mov     r8, rax
0x1801e5266  lea     rdx, aDeviceMup; "\\Device\\Mup"
0x1801e526d  lea     rcx, [rsp+3E8h+var_298]; void *
0x1801e5275  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_WAEBV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring const &)
0x1801e527a  mov     rdx, rax
0x1801e527d  lea     rcx, [rsp+3E8h+var_2F8]
0x1801e5285  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801e528a  lea     rcx, [rsp+3E8h+var_298]; void *
0x1801e5292  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e5297  nop
0x1801e5298  lea     rcx, [rsp+3E8h+SRWLock]; void *
0x1801e52a0  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e52a5  nop
0x1801e52a6  lea     rcx, [rsp+3E8h+var_278]
0x1801e52ae  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1801e52b3  lea     rax, WPP_GLOBAL_Control
0x1801e52ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1801e52c1  cmp     rcx, rax
0x1801e52c4  jz      short loc_1801E5303
0x1801e52c6  test    byte ptr [rcx+1Ch], 4
0x1801e52ca  jz      short loc_1801E5303
0x1801e52cc  lea     rax, [rsp+3E8h+var_2F8]
0x1801e52d4  cmp     [rsp+3E8h+var_2E0], 7
0x1801e52dd  cmova   rax, [rsp+3E8h+var_2F8]
0x1801e52e6  mov     edx, 0C4h
0x1801e52eb  mov     qword ptr [rsp+3E8h+bIgnoreCase], rax
0x1801e52f0  mov     r9, rbx
0x1801e52f3  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x1801e52fa  mov     rcx, [rcx+10h]
0x1801e52fe  call    WPP_SF_SS
0x1801e5303  xorps   xmm0, xmm0
0x1801e5306  movups  [rsp+3E8h+var_2D8], xmm0
0x1801e530e  mov     [rsp+3E8h+var_2C8], rsi
0x1801e5316  mov     [rsp+3E8h+var_2C0], 7
0x1801e5322  mov     word ptr [rsp+3E8h+var_2D8], si
0x1801e532a  mov     r14b, sil
0x1801e532d  lea     rdx, aPowerpntExe; "powerpnt.exe"
0x1801e5334  mov     rcx, rdi; String1
0x1801e5337  call    _wcsicmp
0x1801e533c  test    eax, eax
0x1801e533e  jz      short loc_1801E536A
0x1801e5340  lea     rdx, aWinwordExe; "winword.exe"
0x1801e5347  mov     rcx, rdi; String1
0x1801e534a  call    _wcsicmp
0x1801e534f  test    eax, eax
0x1801e5351  jz      short loc_1801E536A
0x1801e5353  lea     rdx, aExcelExe; "excel.exe"
0x1801e535a  mov     rcx, rdi; String1
0x1801e535d  call    _wcsicmp
0x1801e5362  test    eax, eax
0x1801e5364  jnz     loc_1801E5521
0x1801e536a  lea     rdx, [rsp+3E8h+var_2F8]
0x1801e5372  lea     rcx, [rsp+3E8h+SRWLock]
0x1801e537a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801e537f  nop
0x1801e5380  lea     rdx, asc_18025D638; "."
0x1801e5387  lea     rcx, [rsp+3E8h+SRWLock]
0x1801e538f  call    ?rfind@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::rfind(wchar_t const * const,unsigned __int64)
0x1801e5394  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801e5398  cmp     rax, rdi
0x1801e539b  jz      short loc_1801E53DD
0x1801e539d  lea     r8, [rax+1]
0x1801e53a1  mov     r9, rdi
0x1801e53a4  lea     rdx, [rsp+3E8h+var_2B8]
0x1801e53ac  lea     rcx, [rsp+3E8h+SRWLock]
0x1801e53b4  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1801e53b9  lea     rdx, aTmp_0; "tmp"
0x1801e53c0  lea     rcx, [rsp+3E8h+var_2B8]
0x1801e53c8  call    ?_Equal@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_NQEB_W@Z; std::wstring::_Equal(wchar_t const * const)
0x1801e53cd  mov     r14b, al
0x1801e53d0  lea     rcx, [rsp+3E8h+var_2B8]; void *
0x1801e53d8  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e53dd  lea     rdx, SubBlock; "\\"
0x1801e53e4  lea     rcx, [rsp+3E8h+SRWLock]
0x1801e53ec  call    ?rfind@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::rfind(wchar_t const * const,unsigned __int64)
0x1801e53f1  mov     rbx, rax
0x1801e53f4  cmp     rax, rdi
0x1801e53f7  jz      loc_1801E5514
0x1801e53fd  lea     r8, [rax+1]
0x1801e5401  mov     r9, rdi
0x1801e5404  lea     rdx, [rsp+3E8h+var_2B8]
0x1801e540c  lea     rcx, [rsp+3E8h+SRWLock]
0x1801e5414  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1801e5419  nop
0x1801e541a  lea     rdx, asc_18029FD50; "~$"
0x1801e5421  lea     rcx, [rsp+3E8h+var_298]
0x1801e5429  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801e542e  nop
0x1801e542f  xor     r8d, r8d
0x1801e5432  lea     rdx, [rsp+3E8h+var_298]
0x1801e543a  lea     rcx, [rsp+3E8h+var_2B8]
0x1801e5442  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1801e5447  test    rax, rax
0x1801e544a  jnz     loc_1801E54F8
0x1801e5450  mov     r9, rdi
0x1801e5453  lea     r8d, [rax+2]
0x1801e5457  lea     rdx, [rsp+3E8h+var_278]
0x1801e545f  lea     rcx, [rsp+3E8h+var_2B8]
0x1801e5467  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1801e546c  mov     rdi, rax
0x1801e546f  mov     r9, rbx
0x1801e5472  xor     r8d, r8d
0x1801e5475  lea     rdx, [rsp+3E8h+var_338]
0x1801e547d  lea     rcx, [rsp+3E8h+SRWLock]
0x1801e5485  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1801e548a  nop
0x1801e548b  lea     r8, SubBlock; "\\"
0x1801e5492  mov     rdx, rax
0x1801e5495  lea     rcx, [rsp+3E8h+var_358]
0x1801e549d  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1801e54a2  nop
0x1801e54a3  mov     r8, rdi
0x1801e54a6  mov     rdx, rax
0x1801e54a9  lea     rcx, [rsp+3E8h+var_378]
0x1801e54ae  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1801e54b3  mov     rdx, rax
0x1801e54b6  lea     rcx, [rsp+3E8h+var_2D8]
0x1801e54be  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801e54c3  lea     rcx, [rsp+3E8h+var_378]; void *
0x1801e54c8  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e54cd  nop
0x1801e54ce  lea     rcx, [rsp+3E8h+var_358]; void *
0x1801e54d6  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e54db  nop
0x1801e54dc  lea     rcx, [rsp+3E8h+var_338]; void *
0x1801e54e4  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e54e9  nop
0x1801e54ea  lea     rcx, [rsp+3E8h+var_278]; void *
0x1801e54f2  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e54f7  nop
0x1801e54f8  lea     rcx, [rsp+3E8h+var_298]; void *
0x1801e5500  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e5505  nop
0x1801e5506  lea     rcx, [rsp+3E8h+var_2B8]; void *
0x1801e550e  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e5513  nop
0x1801e5514  lea     rcx, [rsp+3E8h+SRWLock]; void *
0x1801e551c  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e5521  lea     rdx, [r15+1D0h]
0x1801e5528  lea     rcx, [rsp+3E8h+SRWLock]
0x1801e5530  call    ??0?$CGenericAutoLock@U?$CMpReadLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpSRWLock@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>(CommonUtil::CMpSRWLock const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::ENUM_LOCK_INITIAL_STATE)
0x1801e5535  nop
0x1801e5536  mov     [rsp+3E8h+Src], rsi
0x1801e553b  lea     rcx, [r15+0C8h]
0x1801e5542  mov     r8, r12
0x1801e5545  lea     rdx, [rsp+3E8h+Src]
0x1801e554a  call    ?find@?$_Hash@V?$_Umap_traits@UPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(PPID const &)
0x1801e554f  mov     rdi, [rsp+3E8h+Src]
0x1801e5554  cmp     rdi, [r15+0D0h]
0x1801e555b  jnz     short loc_1801E559B
0x1801e555d  cmp     byte ptr [rsp+3E8h+SRWLock+8], sil
0x1801e5565  jz      short loc_1801E5576
0x1801e5567  mov     rcx, [rsp+3E8h+SRWLock]; SRWLock
0x1801e556f  call    cs:__imp_ReleaseSRWLockShared
0x1801e5575  nop
0x1801e5576  lea     rcx, [rsp+3E8h+var_2D8]; void *
0x1801e557e  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e5583  nop
0x1801e5584  lea     rcx, [rsp+3E8h+var_2F8]; void *
0x1801e558c  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e5591  mov     eax, 1
0x1801e5596  jmp     loc_1801E5C3E
0x1801e559b  lea     r12, [rdi+228h]
0x1801e55a2  lea     rdx, [rsp+3E8h+var_2F8]
0x1801e55aa  mov     rcx, r12
0x1801e55ad  call    ??$_Find@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::_Find<std::wstring>(std::wstring const &)
0x1801e55b2  cmp     rax, [r12]
0x1801e55b6  jnz     loc_1801E5BC2
0x1801e55bc  mov     rax, [rdi+238h]
0x1801e55c3  mov     rax, [rax]
0x1801e55c6  mov     [rsp+3E8h+var_3A8], rax
0x1801e55cb  cmp     [rax+19h], sil
0x1801e55cf  jnz     loc_1801E5670
0x1801e55d5  lea     rbx, [rax+20h]
0x1801e55d9  mov     [rsp+3E8h+Src], rsi
0x1801e55de  mov     r8, [rbx+28h]
0x1801e55e2  mov     rdx, [rbx+20h]
0x1801e55e6  lea     r9, [rsp+3E8h+var_2F8]
0x1801e55ee  lea     rcx, [rsp+3E8h+Src]
0x1801e55f3  call    std__find_if_std___Vector_const_iterator_std___Vector_val_std___Simple_types_std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t___________lambda_4662e67aacd32013e3884eba9146ff6b___
0x1801e55f8  mov     rax, [rbx+28h]
0x1801e55fc  cmp     [rsp+3E8h+Src], rax
0x1801e5601  jz      short loc_1801E565C
0x1801e5603  mov     rdx, rbx
0x1801e5606  mov     rcx, r12
0x1801e5609  call    ??$_Find@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::_Find<std::wstring>(std::wstring const &)
0x1801e560e  cmp     rax, [r12]
0x1801e5612  jz      short loc_1801E565C
0x1801e5614  lea     rdx, [rax+40h]
0x1801e5618  mov     rcx, r13
0x1801e561b  call    ??4?$shared_ptr@VDlpTelemetryFilter@TelemetryFilterManager@Dlp@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Dlp::TelemetryFilterManager::DlpTelemetryFilter>::operator=(std::shared_ptr<Dlp::TelemetryFilterManager::DlpTelemetryFilter> const &)
0x1801e5620  nop
0x1801e5621  cmp     byte ptr [rsp+3E8h+SRWLock+8], sil
0x1801e5629  jz      short loc_1801E563A
0x1801e562b  mov     rcx, [rsp+3E8h+SRWLock]; SRWLock
0x1801e5633  call    cs:__imp_ReleaseSRWLockShared
0x1801e5639  nop
0x1801e563a  lea     rcx, [rsp+3E8h+var_2D8]; void *
0x1801e5642  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e5647  nop
0x1801e5648  lea     rcx, [rsp+3E8h+var_2F8]; void *
0x1801e5650  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e5655  xor     eax, eax
0x1801e5657  jmp     loc_1801E5C3E
0x1801e565c  lea     rcx, [rsp+3E8h+var_3A8]
0x1801e5661  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x1801e5666  mov     rax, [rsp+3E8h+var_3A8]
0x1801e566b  jmp     loc_1801E55CB
0x1801e5670  test    r14b, r14b
0x1801e5673  jz      short loc_1801E56E2
0x1801e5675  mov     rcx, cs:WPP_GLOBAL_Control
0x1801e567c  lea     rax, WPP_GLOBAL_Control
0x1801e5683  cmp     rcx, rax
0x1801e5686  jz      short loc_1801E56A4
0x1801e5688  test    byte ptr [rcx+1Ch], 4
0x1801e568c  jz      short loc_1801E56A4
0x1801e568e  mov     edx, 0C5h
0x1801e5693  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x1801e569a  mov     rcx, [rcx+10h]
0x1801e569e  call    WPP_SF_
0x1801e56a3  nop
0x1801e56a4  cmp     byte ptr [rsp+3E8h+SRWLock+8], sil
0x1801e56ac  jz      short loc_1801E56BD
0x1801e56ae  mov     rcx, [rsp+3E8h+SRWLock]; SRWLock
0x1801e56b6  call    cs:__imp_ReleaseSRWLockShared
0x1801e56bc  nop
0x1801e56bd  lea     rcx, [rsp+3E8h+var_2D8]; void *
0x1801e56c5  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e56ca  nop
0x1801e56cb  lea     rcx, [rsp+3E8h+var_2F8]; void *
0x1801e56d3  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801e56d8  mov     eax, 800704C7h
0x1801e56dd  jmp     loc_1801E5C3E
  ... truncated ...
```
