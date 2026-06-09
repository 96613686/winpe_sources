# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::OpenDocumentFileSaveAsHint(PPID const &,_DLP_DOCUMENT_INFO * const,bool)

- ea: `0x1800ba270`
- end: `0x1800ba7a7`
- name: `?OpenDocumentFileSaveAsHint@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@QEAU_DLP_DOCUMENT_INFO@@_N@Z`
- size: `1335`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct PPID *, struct _DLP_DOCUMENT_INFO *const, bool)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ba1f4`

## callees

- `0x18001bad0`
- `0x180028d80`
- `0x180034420`
- `0x180038450`
- `0x18004b3bc`
- `0x18006f3e4`
- `0x180079034`
- `0x180080030`
- `0x1800809d0`
- `0x180089510`
- `0x1800943fc`
- `0x180094e70`
- `0x18009d524`
- `0x1800b64ec`
- `0x1800b66e8`
- `0x1800ba270`
- `0x1800c9028`
- `0x1800ca244`
- `0x1800ca2b8`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18014cda0`
- `0x1801d98c0`
- `0x1801e063c`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800ba43b`
- `KERNEL32!CompareStringOrdinal` at `0x1800ba48f`
- `KERNEL32!CompareStringOrdinal` at `0x1800ba43b`
- `KERNEL32!CompareStringOrdinal` at `0x1800ba48f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ba33a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ba3ed`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ba510`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ba5b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ba726`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ba33a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ba3ed`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ba510`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ba5b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ba726`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::OpenDocumentFileSaveAsHint(
        LPCWCH *this,
        const struct PPID *a2,
        struct _DLP_DOCUMENT_INFO *const a3,
        char a4)
{
  unsigned int v8; // r14d
  WCHAR *v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rax
  LPCWCH v13; // rbx
  LPCWCH v14; // r14
  _QWORD *v15; // r15
  __int64 v16; // rdi
  __int64 v17; // rbx
  _QWORD *v18; // rax
  __int64 *v19; // r15
  const WCHAR *v20; // rcx
  wchar_t **v21; // r9
  int DestinationNtName; // eax
  const struct std::nothrow_t *v23; // rdx
  const WCHAR *v24; // rcx
  WCHAR *v25; // rdi
  int v26; // eax
  const struct std::nothrow_t *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rax
  char v31; // al
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rax
  LPCWCH lpString2; // [rsp+30h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C0h] BYREF
  char v37; // [rsp+40h] [rbp-B8h]
  _QWORD *v38; // [rsp+48h] [rbp-B0h] BYREF
  __int128 v39; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-98h]
  char v41; // [rsp+68h] [rbp-90h]
  __int16 v42; // [rsp+69h] [rbp-8Fh]
  char v43; // [rsp+6Bh] [rbp-8Dh]
  __int128 v44; // [rsp+70h] [rbp-88h] BYREF
  __int64 v45; // [rsp+80h] [rbp-78h]
  int v46; // [rsp+88h] [rbp-70h]
  std::_Ref_count_base *v47[2]; // [rsp+A8h] [rbp-50h] BYREF

  *(_QWORD *)&v39 = a2;
  v8 = 0;
  if ( !a3 )
    return 2147942487LL;
  v10 = (WCHAR *)&qword_18025C818;
  if ( *((_QWORD *)a3 + 1) )
    v10 = (WCHAR *)*((_QWORD *)a3 + 1);
  v38 = (_QWORD *)((char *)a3 + 16);
  v11 = *((_QWORD *)a3 + 2);
  if ( !v11 )
    return 1;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(v11 + 2 * v12) );
  if ( !v12 )
    return 1;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(
    &SRWLock,
    this + 58);
  lpString2 = 0;
  std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(
    this + 25,
    &lpString2,
    a2);
  v13 = lpString2;
  if ( lpString2 == this[26] )
  {
    if ( v37 )
      ReleaseSRWLockExclusive(SRWLock);
    return 1;
  }
  if ( a4 )
  {
    v14 = lpString2 + 292;
    v15 = v38;
    std::wstring::wstring(&v44, *v38);
    v16 = std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::_Find<std::wstring>(
            v13 + 292,
            &v44);
    v17 = *(_QWORD *)v14;
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v44);
    if ( v16 != v17 )
    {
      std::wstring::wstring(&v44, *v15);
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::erase(
        v14,
        &v44);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v44);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, &WPP_37379ce3a908304aafca380d907f5915_Traceguids);
    }
    if ( v37 )
      ReleaseSRWLockExclusive(SRWLock);
    return 0;
  }
  v18 = (_QWORD *)**((_QWORD **)lpString2 + 69);
  v38 = v18;
  while ( !*((_BYTE *)v18 + 25) )
  {
    v19 = v18 + 4;
    v20 = (const WCHAR *)(v18[8] + 40LL);
    if ( *(_QWORD *)(v18[8] + 64LL) > 7u )
      v20 = *(const WCHAR **)v20;
    if ( CompareStringOrdinal(v20, -1, v10, -1, 1) == 2 )
    {
LABEL_41:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v28 = (__int64)v19;
        if ( (unsigned __int64)v19[3] > 7 )
          v28 = *v19;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          203,
          (unsigned int)&WPP_37379ce3a908304aafca380d907f5915_Traceguids,
          *((_QWORD *)a3 + 2),
          v28);
      }
      v29 = *(_QWORD *)std::map<std::wstring,std::vector<std::wstring>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::_Try_emplace<std::wstring const &,>(
                         v13 + 284,
                         &v39,
                         v19);
      std::wstring::wstring(&v44, *((_QWORD *)a3 + 2));
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(v29 + 64, &v44);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v44);
      if ( v37 )
        ReleaseSRWLockExclusive(SRWLock);
      return 0;
    }
    lpString2 = 0;
    DestinationNtName = RealtimeProtection::DlpUtils::GetDestinationNtName(
                          (RealtimeProtection::DlpUtils *)*(unsigned int *)(v39 + 8),
                          (unsigned int)v10,
                          (const wchar_t *)&lpString2,
                          v21);
    v8 = DestinationNtName;
    if ( DestinationNtName < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          202,
          &WPP_37379ce3a908304aafca380d907f5915_Traceguids,
          (unsigned int)DestinationNtName);
      if ( lpString2 )
        operator delete((void *)lpString2, v23);
      if ( v37 )
        ReleaseSRWLockExclusive(SRWLock);
      return v8;
    }
    v24 = (const WCHAR *)v19;
    if ( (unsigned __int64)v19[3] > 7 )
      v24 = (const WCHAR *)*v19;
    v25 = (WCHAR *)lpString2;
    v26 = CompareStringOrdinal(v24, -1, lpString2, -1, 1);
    LODWORD(lpString2) = v26;
    if ( v25 )
    {
      operator delete(v25, v27);
      v26 = (int)lpString2;
    }
    if ( v26 == 2 )
      goto LABEL_41;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v38);
    v18 = v38;
  }
  *(_OWORD *)v47 = 0;
  std::make_shared<RealtimeProtection::DocumentDescriptor,>(v47);
  *(_DWORD *)v47[0] = *(_DWORD *)a3;
  std::wstring::assign((char *)v47[0] + 40, v10);
  std::wstring::assign((char *)v47[0] + 8, *((void **)a3 + 2));
  v30 = v39;
  *(_QWORD *)&v39 = *(_QWORD *)v39;
  DWORD2(v39) = *(_DWORD *)(v30 + 8);
  BYTE12(v39) = 1;
  BYTE4(v40) = 0;
  v41 = 1;
  v42 = 0;
  v43 = 0;
  v44 = v39;
  v45 = v40;
  v46 = 1;
  v31 = Dlp::Utils::FileExists(v10, &v44) ^ 1;
  *((_BYTE *)v47[0] + 72) = v31;
  if ( v31 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_57;
    v33 = 204;
  }
  else
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_57;
    v33 = 205;
  }
  WPP_SF_S(v32[2], v33, &WPP_37379ce3a908304aafca380d907f5915_Traceguids, v10);
LABEL_57:
  v34 = std::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>(
          &v44,
          (char *)a3 + 16,
          v47);
  std::map<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>>::insert<std::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>,0>(
    v13 + 292,
    &v39,
    v34);
  std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DlpTelemetry::DlpTelemetryData>>::~pair<std::wstring const,std::shared_ptr<RealtimeProtection::DlpTelemetry::DlpTelemetryData>>(&v44);
  if ( v47[1] )
    std::_Ref_count_base::_Decref(v47[1]);
  if ( v37 )
    ReleaseSRWLockExclusive(SRWLock);
  if ( (v8 & 0x80000000) == 0 )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 206, &WPP_37379ce3a908304aafca380d907f5915_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800ba270  push    rbx
0x1800ba272  push    rsi
0x1800ba273  push    rdi
0x1800ba274  push    r12
0x1800ba276  push    r13
0x1800ba278  push    r14
0x1800ba27a  push    r15
0x1800ba27c  sub     rsp, 0C0h
0x1800ba283  mov     rax, cs:__security_cookie
0x1800ba28a  xor     rax, rsp
0x1800ba28d  mov     [rsp+0F8h+var_40], rax
0x1800ba295  mov     r15b, r9b
0x1800ba298  mov     r12, r8
0x1800ba29b  mov     rbx, rdx
0x1800ba29e  mov     qword ptr [rsp+0F8h+var_A8], rdx
0x1800ba2a3  mov     rdi, rcx
0x1800ba2a6  xor     esi, esi
0x1800ba2a8  mov     r14d, esi
0x1800ba2ab  test    r8, r8
0x1800ba2ae  jnz     short loc_1800BA2BA
0x1800ba2b0  mov     eax, 80070057h
0x1800ba2b5  jmp     loc_1800BA784
0x1800ba2ba  lea     r13, qword_18025C818
0x1800ba2c1  cmp     [r8+8], rsi
0x1800ba2c5  cmovnz  r13, [r8+8]
0x1800ba2ca  lea     rax, [r8+10h]
0x1800ba2ce  mov     [rsp+0F8h+var_B0], rax
0x1800ba2d3  mov     rcx, [rax]
0x1800ba2d6  test    rcx, rcx
0x1800ba2d9  jz      loc_1800BA77F
0x1800ba2df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ba2e3  inc     rax
0x1800ba2e6  cmp     [rcx+rax*2], si
0x1800ba2ea  jnz     short loc_1800BA2E3
0x1800ba2ec  test    rax, rax
0x1800ba2ef  jz      loc_1800BA77F
0x1800ba2f5  lea     rdx, [rdi+1D0h]
0x1800ba2fc  lea     rcx, [rsp+0F8h+SRWLock]
0x1800ba301  call    ??0?$CGenericAutoLock@U?$CMpWriteLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@AEAVCMpSRWLock@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(CommonUtil::CMpSRWLock &,CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::ENUM_LOCK_INITIAL_STATE)
0x1800ba306  nop
0x1800ba307  mov     [rsp+0F8h+lpString2], rsi
0x1800ba30c  lea     rcx, [rdi+0C8h]
0x1800ba313  mov     r8, rbx
0x1800ba316  lea     rdx, [rsp+0F8h+lpString2]
0x1800ba31b  call    ?find@?$_Hash@V?$_Umap_traits@UPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(PPID const &)
0x1800ba320  mov     rbx, [rsp+0F8h+lpString2]
0x1800ba325  cmp     rbx, [rdi+0D0h]
0x1800ba32c  jnz     short loc_1800BA34A
0x1800ba32e  cmp     [rsp+0F8h+var_B8], sil
0x1800ba333  jz      short loc_1800BA340
0x1800ba335  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x1800ba33a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ba340  mov     eax, 1
0x1800ba345  jmp     loc_1800BA784
0x1800ba34a  test    r15b, r15b
0x1800ba34d  jz      loc_1800BA3FA
0x1800ba353  lea     r14, [rbx+248h]
0x1800ba35a  mov     r15, [rsp+0F8h+var_B0]
0x1800ba35f  mov     rdx, [r15]
0x1800ba362  lea     rcx, [rsp+0F8h+var_88]
0x1800ba367  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800ba36c  lea     rdx, [rsp+0F8h+var_88]
0x1800ba371  mov     rcx, r14
0x1800ba374  call    ??$_Find@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::_Find<std::wstring>(std::wstring const &)
0x1800ba379  mov     rdi, rax
0x1800ba37c  mov     rbx, [r14]
0x1800ba37f  lea     rcx, [rsp+0F8h+var_88]; void *
0x1800ba384  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800ba389  cmp     rdi, rbx
0x1800ba38c  jz      short loc_1800BA3E1
0x1800ba38e  mov     rdx, [r15]
0x1800ba391  lea     rcx, [rsp+0F8h+var_88]
0x1800ba396  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800ba39b  lea     rdx, [rsp+0F8h+var_88]
0x1800ba3a0  mov     rcx, r14
0x1800ba3a3  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::erase(std::wstring const &)
0x1800ba3a8  lea     rcx, [rsp+0F8h+var_88]; void *
0x1800ba3ad  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800ba3b2  lea     rdi, WPP_GLOBAL_Control
0x1800ba3b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba3c0  cmp     rcx, rdi
0x1800ba3c3  jz      short loc_1800BA3E1
0x1800ba3c5  test    byte ptr [rcx+1Ch], 4
0x1800ba3c9  jz      short loc_1800BA3E1
0x1800ba3cb  mov     edx, 0C9h
0x1800ba3d0  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x1800ba3d7  mov     rcx, [rcx+10h]
0x1800ba3db  call    WPP_SF_
0x1800ba3e0  nop
0x1800ba3e1  cmp     [rsp+0F8h+var_B8], sil
0x1800ba3e6  jz      short loc_1800BA3F3
0x1800ba3e8  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x1800ba3ed  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ba3f3  xor     eax, eax
0x1800ba3f5  jmp     loc_1800BA784
0x1800ba3fa  mov     rax, [rbx+228h]
0x1800ba401  mov     rax, [rax]
0x1800ba404  mov     [rsp+0F8h+var_B0], rax
0x1800ba409  cmp     [rax+19h], sil
0x1800ba40d  jnz     loc_1800BA5BD
0x1800ba413  lea     r15, [rax+20h]
0x1800ba417  mov     rcx, [r15+20h]
0x1800ba41b  add     rcx, 28h ; '('
0x1800ba41f  cmp     qword ptr [rcx+18h], 7
0x1800ba424  jbe     short loc_1800BA429
0x1800ba426  mov     rcx, [rcx]; lpString1
0x1800ba429  mov     [rsp+0F8h+bIgnoreCase], 1; bIgnoreCase
0x1800ba431  or      r9d, 0FFFFFFFFh; cchCount2
0x1800ba435  mov     r8, r13; lpString2
0x1800ba438  or      edx, r9d; cchCount1
0x1800ba43b  call    cs:__imp_CompareStringOrdinal
0x1800ba441  cmp     eax, 2
0x1800ba444  jz      loc_1800BA51E
0x1800ba44a  mov     [rsp+0F8h+lpString2], rsi
0x1800ba44f  lea     r8, [rsp+0F8h+lpString2]; wchar_t *
0x1800ba454  mov     rdx, r13; unsigned int
0x1800ba457  mov     rax, qword ptr [rsp+0F8h+var_A8]
0x1800ba45c  mov     ecx, [rax+8]; this
0x1800ba45f  call    ?GetDestinationNtName@DlpUtils@RealtimeProtection@@YAJKPEB_WPEAPEA_W@Z; RealtimeProtection::DlpUtils::GetDestinationNtName(ulong,wchar_t const *,wchar_t * *)
0x1800ba464  mov     r14d, eax
0x1800ba467  test    eax, eax
0x1800ba469  js      short loc_1800BA4C3
0x1800ba46b  mov     rcx, r15
0x1800ba46e  cmp     qword ptr [r15+18h], 7
0x1800ba473  jbe     short loc_1800BA478
0x1800ba475  mov     rcx, [r15]; lpString1
0x1800ba478  mov     [rsp+0F8h+bIgnoreCase], 1; bIgnoreCase
0x1800ba480  or      r9d, 0FFFFFFFFh; cchCount2
0x1800ba484  mov     rdi, [rsp+0F8h+lpString2]
0x1800ba489  mov     r8, rdi; lpString2
0x1800ba48c  or      edx, r9d; cchCount1
0x1800ba48f  call    cs:__imp_CompareStringOrdinal
0x1800ba495  mov     dword ptr [rsp+0F8h+lpString2], eax
0x1800ba499  test    rdi, rdi
0x1800ba49c  jz      short loc_1800BA4AA
0x1800ba49e  mov     rcx, rdi; void *
0x1800ba4a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ba4a6  mov     eax, dword ptr [rsp+0F8h+lpString2]
0x1800ba4aa  cmp     eax, 2
0x1800ba4ad  jz      short loc_1800BA51E
0x1800ba4af  lea     rcx, [rsp+0F8h+var_B0]
0x1800ba4b4  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x1800ba4b9  mov     rax, [rsp+0F8h+var_B0]
0x1800ba4be  jmp     loc_1800BA409
0x1800ba4c3  lea     rdi, WPP_GLOBAL_Control
0x1800ba4ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba4d1  cmp     rcx, rdi
0x1800ba4d4  jz      short loc_1800BA4F4
0x1800ba4d6  test    byte ptr [rcx+1Ch], 1
0x1800ba4da  jz      short loc_1800BA4F4
0x1800ba4dc  mov     edx, 0CAh
0x1800ba4e1  mov     r9d, r14d
0x1800ba4e4  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x1800ba4eb  mov     rcx, [rcx+10h]
0x1800ba4ef  call    WPP_SF_d
0x1800ba4f4  mov     rcx, [rsp+0F8h+lpString2]; void *
0x1800ba4f9  test    rcx, rcx
0x1800ba4fc  jz      short loc_1800BA504
0x1800ba4fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ba503  nop
0x1800ba504  cmp     [rsp+0F8h+var_B8], sil
0x1800ba509  jz      short loc_1800BA516
0x1800ba50b  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x1800ba510  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ba516  mov     eax, r14d
0x1800ba519  jmp     loc_1800BA784
0x1800ba51e  lea     rdi, WPP_GLOBAL_Control
0x1800ba525  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba52c  cmp     rcx, rdi
0x1800ba52f  jz      short loc_1800BA563
0x1800ba531  test    byte ptr [rcx+1Ch], 4
0x1800ba535  jz      short loc_1800BA563
0x1800ba537  mov     rax, r15
0x1800ba53a  cmp     qword ptr [r15+18h], 7
0x1800ba53f  jbe     short loc_1800BA544
0x1800ba541  mov     rax, [r15]
0x1800ba544  mov     edx, 0CBh
0x1800ba549  mov     qword ptr [rsp+0F8h+bIgnoreCase], rax
0x1800ba54e  mov     r9, [r12+10h]
0x1800ba553  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x1800ba55a  mov     rcx, [rcx+10h]
0x1800ba55e  call    WPP_SF_SS
0x1800ba563  lea     rcx, [rbx+238h]
0x1800ba56a  mov     r8, r15
0x1800ba56d  lea     rdx, [rsp+0F8h+var_A8]
0x1800ba572  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::map<std::wstring,std::vector<std::wstring>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800ba577  mov     rbx, [rax]
0x1800ba57a  mov     rdx, [r12+10h]
0x1800ba57f  lea     rcx, [rsp+0F8h+var_88]
0x1800ba584  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800ba589  nop
0x1800ba58a  lea     rdx, [rsp+0F8h+var_88]
0x1800ba58f  lea     rcx, [rbx+40h]
0x1800ba593  call    ??$_Emplace_one_at_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x1800ba598  nop
0x1800ba599  lea     rcx, [rsp+0F8h+var_88]; void *
0x1800ba59e  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800ba5a3  nop
0x1800ba5a4  cmp     [rsp+0F8h+var_B8], sil
0x1800ba5a9  jz      short loc_1800BA5B6
0x1800ba5ab  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x1800ba5b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ba5b6  xor     eax, eax
0x1800ba5b8  jmp     loc_1800BA784
0x1800ba5bd  xorps   xmm0, xmm0
0x1800ba5c0  movups  xmmword ptr [rsp+0F8h+var_50], xmm0
0x1800ba5c8  lea     rcx, [rsp+0F8h+var_50]
0x1800ba5d0  call    ??$make_shared@UDocumentDescriptor@RealtimeProtection@@$$V@std@@YA?AV?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@0@XZ; std::make_shared<RealtimeProtection::DocumentDescriptor,>(void)
0x1800ba5d5  nop
0x1800ba5d6  mov     ecx, [r12]
0x1800ba5da  mov     rax, [rsp+0F8h+var_50]
0x1800ba5e2  mov     [rax], ecx
0x1800ba5e4  mov     rcx, [rsp+0F8h+var_50]
0x1800ba5ec  add     rcx, 28h ; '('; void *
0x1800ba5f0  mov     rdx, r13; Src
0x1800ba5f3  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800ba5f8  mov     rcx, [rsp+0F8h+var_50]
0x1800ba600  add     rcx, 8; void *
0x1800ba604  mov     rdx, [r12+10h]; Src
0x1800ba609  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800ba60e  mov     rax, qword ptr [rsp+0F8h+var_A8]
0x1800ba613  movsd   xmm0, qword ptr [rax]
0x1800ba617  movsd   qword ptr [rsp+0F8h+var_A8], xmm0
0x1800ba61d  mov     eax, [rax+8]
0x1800ba620  mov     dword ptr [rsp+0F8h+var_A8+8], eax
0x1800ba624  mov     byte ptr [rsp+0F8h+var_A8+0Ch], 1
0x1800ba629  mov     [rsp+0F8h+var_94], sil
0x1800ba62e  mov     byte ptr [rsp+0F8h+var_90], 1
0x1800ba633  xor     eax, eax
0x1800ba635  mov     word ptr [rsp+0F8h+var_90+1], ax
0x1800ba63a  mov     byte ptr [rsp+0F8h+var_90+3], al
0x1800ba63e  movups  xmm0, [rsp+0F8h+var_A8]
0x1800ba643  movaps  [rsp+0F8h+var_88], xmm0
0x1800ba648  movsd   xmm1, qword ptr [rsp+60h]
0x1800ba64e  movsd   [rsp+0F8h+var_78], xmm1
0x1800ba657  mov     eax, [rsp+0F8h+var_90]
0x1800ba65b  mov     [rsp+0F8h+var_70], eax
0x1800ba662  lea     rdx, [rsp+0F8h+var_88]
0x1800ba667  mov     rcx, r13
0x1800ba66a  call    ?FileExists@Utils@Dlp@@YA_NPEB_WUImpersonationOptions@DlpUtils@RealtimeProtection@@@Z; Dlp::Utils::FileExists(wchar_t const *,RealtimeProtection::DlpUtils::ImpersonationOptions)
0x1800ba66f  xor     al, 1
0x1800ba671  mov     rcx, [rsp+0F8h+var_50]
0x1800ba679  mov     [rcx+48h], al
0x1800ba67c  jz      short loc_1800BA69E
0x1800ba67e  lea     rdi, WPP_GLOBAL_Control
0x1800ba685  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba68c  cmp     rcx, rdi
0x1800ba68f  jz      short loc_1800BA6CF
0x1800ba691  test    byte ptr [rcx+1Ch], 4
0x1800ba695  jz      short loc_1800BA6CF
0x1800ba697  mov     edx, 0CCh
0x1800ba69c  jmp     short loc_1800BA6BC
0x1800ba69e  lea     rdi, WPP_GLOBAL_Control
0x1800ba6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba6ac  cmp     rcx, rdi
0x1800ba6af  jz      short loc_1800BA6CF
0x1800ba6b1  test    byte ptr [rcx+1Ch], 4
0x1800ba6b5  jz      short loc_1800BA6CF
0x1800ba6b7  mov     edx, 0CDh
0x1800ba6bc  mov     r9, r13
0x1800ba6bf  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x1800ba6c6  mov     rcx, [rcx+10h]
0x1800ba6ca  call    WPP_SF_S
0x1800ba6cf  lea     r8, [rsp+0F8h+var_50]
0x1800ba6d7  lea     rdx, [r12+10h]
0x1800ba6dc  lea     rcx, [rsp+0F8h+var_88]
0x1800ba6e1  call    ??$?0AEAPEB_WAEAV?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@std@@$0A@@?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@QEAA@AEAPEB_WAEAV?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@1@@Z; std::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>(wchar_t const * &,std::shared_ptr<RealtimeProtection::DocumentDescriptor> &)
0x1800ba6e6  nop
0x1800ba6e7  mov     r8, rax
0x1800ba6ea  lea     rdx, [rsp+0F8h+var_A8]
0x1800ba6ef  lea     rcx, [rbx+248h]
0x1800ba6f6  call    ??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@1@@Z; std::map<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>>::insert<std::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>,0>(std::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>> &&)
0x1800ba6fb  nop
0x1800ba6fc  lea     rcx, [rsp+0F8h+var_88]
0x1800ba701  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VDlpTelemetryData@DlpTelemetry@RealtimeProtection@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DlpTelemetry::DlpTelemetryData>>::~pair<std::wstring const,std::shared_ptr<RealtimeProtection::DlpTelemetry::DlpTelemetryData>>(void)
0x1800ba706  nop
0x1800ba707  mov     rcx, [rsp+0F8h+var_50+8]; this
0x1800ba70f  test    rcx, rcx
0x1800ba712  jz      short loc_1800BA71A
0x1800ba714  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ba719  nop
0x1800ba71a  cmp     [rsp+0F8h+var_B8], sil
0x1800ba71f  jz      short loc_1800BA72D
0x1800ba721  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x1800ba726  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ba72c  nop
0x1800ba72d  jmp     short loc_1800BA73B
0x1800ba72f  lea     rdi, WPP_GLOBAL_Control
0x1800ba736  mov     r14d, dword ptr [rsp+0F8h+lpString2]
0x1800ba73b  test    r14d, r14d
0x1800ba73e  js      short loc_1800BA750
0x1800ba740  xor     eax, eax
0x1800ba742  jmp     short loc_1800BA784
0x1800ba744  lea     rdi, WPP_GLOBAL_Control
0x1800ba74b  mov     r14d, dword ptr [rsp+0F8h+lpString2]
0x1800ba750  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba757  cmp     rcx, rdi
0x1800ba75a  jz      short loc_1800BA77A
0x1800ba75c  test    byte ptr [rcx+1Ch], 1
0x1800ba760  jz      short loc_1800BA77A
  ... truncated ...
```
