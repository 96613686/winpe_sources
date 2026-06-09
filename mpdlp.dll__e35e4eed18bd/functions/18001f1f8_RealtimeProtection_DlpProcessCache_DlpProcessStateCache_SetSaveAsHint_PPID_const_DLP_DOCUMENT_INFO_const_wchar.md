# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::SetSaveAsHint(PPID const &,_DLP_DOCUMENT_INFO * const,wchar_t const *,bool)

- ea: `0x18001f1f8`
- end: `0x18001f65e`
- name: `?SetSaveAsHint@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@QEAU_DLP_DOCUMENT_INFO@@PEB_W_N@Z`
- size: `1126`
- prototype: `int(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct PPID *, struct _DLP_DOCUMENT_INFO *const, const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1801d852c`

## callees

- `0x18001bad0`
- `0x18001f1f8`
- `0x180028d80`
- `0x180034420`
- `0x180038450`
- `0x18004b3bc`
- `0x180080030`
- `0x1800809d0`
- `0x18008c840`
- `0x180097aa0`
- `0x180097bb0`
- `0x18009be50`
- `0x18009d524`
- `0x18009faa0`
- `0x1800b6520`
- `0x1800b66e8`
- `0x1800ca244`
- `0x18010cb40`
- `0x18014cda0`
- `0x1801d98c0`
- `0x1801e01b8`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18001f3b3`
- `KERNEL32!CompareStringOrdinal` at `0x18001f3b3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001f244`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001f244`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001f280`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001f5f0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001f280`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001f5f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpProcessCache::DlpProcessStateCache::SetSaveAsHint(
        RTL_SRWLOCK *this,
        const struct PPID *a2,
        struct _DLP_DOCUMENT_INFO *const a3,
        const wchar_t *a4,
        bool a5)
{
  RTL_SRWLOCK *v9; // r15
  _QWORD *v10; // rbx
  const wchar_t *v12; // r13
  wchar_t *v13; // rdx
  wchar_t *v14; // r15
  __int64 v15; // rdi
  const WCHAR *v16; // rcx
  __int64 v17; // r14
  __int64 v18; // r15
  std::_Ref_count_base *v19; // rcx
  char v20; // al
  PVOID *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  void *Src; // [rsp+30h] [rbp-E8h] BYREF
  __int128 v26; // [rsp+38h] [rbp-E0h]
  __int64 v27; // [rsp+48h] [rbp-D0h]
  char v28; // [rsp+50h] [rbp-C8h]
  __int16 v29; // [rsp+51h] [rbp-C7h]
  char v30; // [rsp+53h] [rbp-C5h]
  const struct PPID *v31; // [rsp+58h] [rbp-C0h]
  __int128 v32; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+70h] [rbp-A8h]
  int v34; // [rsp+78h] [rbp-A0h]
  PSRWLOCK SRWLock; // [rsp+90h] [rbp-88h]
  char v36; // [rsp+98h] [rbp-80h]
  _QWORD v37[3]; // [rsp+A8h] [rbp-70h] BYREF
  std::_Ref_count_base *v38[2]; // [rsp+C0h] [rbp-58h] BYREF

  v31 = a2;
  v37[0] = a4;
  v9 = this + 58;
  SRWLock = this + 58;
  AcquireSRWLockExclusive(this + 58);
  v36 = 1;
  Src = 0;
  std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(
    &this[25],
    &Src,
    a2);
  v10 = Src;
  if ( Src == this[26].Ptr )
  {
    ReleaseSRWLockExclusive(v9);
    return 1;
  }
  v12 = &qword_18025C818;
  v13 = (wchar_t *)&qword_18025C818;
  if ( *((_QWORD *)a3 + 2) )
    v13 = (wchar_t *)*((_QWORD *)a3 + 2);
  Src = v13;
  v14 = (wchar_t *)&qword_18025C818;
  if ( *((_QWORD *)a3 + 1) )
    v14 = (wchar_t *)*((_QWORD *)a3 + 1);
  if ( !a5 )
  {
    *(_OWORD *)v38 = 0;
    std::make_shared<RealtimeProtection::DocumentDescriptor,>(v38);
    *(_DWORD *)v38[0] = *(_DWORD *)a3;
    std::wstring::assign((char *)v38[0] + 40, v14);
    std::wstring::assign((char *)v38[0] + 8, Src);
    *(_QWORD *)&v26 = *(_QWORD *)v31;
    DWORD2(v26) = *((_DWORD *)v31 + 2);
    BYTE12(v26) = 1;
    BYTE4(v27) = 0;
    v28 = 1;
    v29 = 0;
    v30 = 0;
    v32 = v26;
    v33 = v27;
    v34 = 1;
    v20 = Dlp::Utils::FileExists(v14, &v32) ^ 1;
    *((_BYTE *)v38[0] + 72) = v20;
    if ( v20 )
    {
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v22 = 192;
LABEL_30:
          WPP_SF_S(v21[2], v22, &WPP_37379ce3a908304aafca380d907f5915_Traceguids, v14);
          v21 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_31;
        }
        goto LABEL_31;
      }
    }
    else
    {
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v22 = 193;
          goto LABEL_30;
        }
LABEL_31:
        if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 )
        {
          if ( a4 )
            v12 = a4;
          WPP_SF_SSS((TRACEHANDLE)v21[2], (__int64)v14, (__int64)v12);
        }
      }
    }
    if ( a4 )
    {
      v23 = std::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>(
              &v32,
              v37,
              v38);
      std::map<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>>::insert<std::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>,0>(
        v10 + 69,
        v37,
        v23);
      std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DlpTelemetry::DlpTelemetryData>>::~pair<std::wstring const,std::shared_ptr<RealtimeProtection::DlpTelemetry::DlpTelemetryData>>(&v32);
    }
    else
    {
      v24 = v10[76];
      if ( v24 == v10[77] )
      {
        std::vector<std::shared_ptr<RealtimeProtection::DocumentDescriptor>>::_Emplace_reallocate<std::shared_ptr<RealtimeProtection::DocumentDescriptor> const &>(
          v10 + 75,
          v10[76],
          v38);
      }
      else
      {
        std::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>(
          v24,
          v38);
        v10[76] += 16LL;
      }
    }
    if ( v38[1] )
      std::_Ref_count_base::_Decref(v38[1]);
    goto LABEL_43;
  }
  if ( a4 )
  {
    std::wstring::wstring(&v32, a4);
    *(_OWORD *)v38 = *(_OWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Eqrange<std::wstring>(
                                  v10 + 69,
                                  v37,
                                  &v32);
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::_Erase(
      v10 + 69,
      v38);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v32);
    std::wstring::wstring(&v32, a4);
    *(_OWORD *)v38 = *(_OWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Eqrange<std::wstring>(
                                  v10 + 71,
                                  v37,
                                  &v32);
    std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Erase(
      v10 + 71,
      v38);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v32);
  }
  else
  {
    v15 = v10[75];
    while ( v15 != v10[76] )
    {
      v16 = (const WCHAR *)(*(_QWORD *)v15 + 8LL);
      if ( *(_QWORD *)(*(_QWORD *)v15 + 32LL) > 7u )
        v16 = *(const WCHAR **)v16;
      v17 = v15 + 16;
      if ( CompareStringOrdinal(v16, -1, v13, -1, 1) == 2 )
      {
        v18 = v10[76];
        while ( v17 != v18 )
        {
          std::shared_ptr<RealtimeProtection::DocumentDescriptor>::operator=(v17 - 16, v17);
          v17 += 16;
        }
        v19 = *(std::_Ref_count_base **)(v10[76] - 8LL);
        if ( v19 )
          std::_Ref_count_base::_Decref(v19);
        v10[76] -= 16LL;
      }
      else
      {
        v15 += 16;
      }
      v13 = (wchar_t *)Src;
    }
  }
LABEL_43:
  ReleaseSRWLockExclusive(SRWLock);
  return 0;
}

```

## disassembly

```asm
0x18001f1f8  mov     r11, rsp
0x18001f1fb  push    rbx
0x18001f1fc  push    rdi
0x18001f1fd  push    r12
0x18001f1ff  push    r13
0x18001f201  push    r14
0x18001f203  push    r15
0x18001f205  sub     rsp, 0E8h
0x18001f20c  mov     rax, cs:__security_cookie
0x18001f213  xor     rax, rsp
0x18001f216  mov     [rsp+118h+var_48], rax
0x18001f21e  mov     r14, r9
0x18001f221  mov     r12, r8
0x18001f224  mov     rbx, rdx
0x18001f227  mov     [rsp+118h+var_C0], rdx
0x18001f22c  mov     rdi, rcx
0x18001f22f  mov     [r11-70h], r9
0x18001f233  lea     r15, [rcx+1D0h]
0x18001f23a  mov     [r11-88h], r15
0x18001f241  mov     rcx, r15; SRWLock
0x18001f244  call    cs:__imp_AcquireSRWLockExclusive
0x18001f24a  mov     [rsp+118h+var_80], 1
0x18001f252  mov     [rsp+118h+Src], 0
0x18001f25b  lea     rcx, [rdi+0C8h]
0x18001f262  mov     r8, rbx
0x18001f265  lea     rdx, [rsp+118h+Src]
0x18001f26a  call    ?find@?$_Hash@V?$_Umap_traits@UPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@V?$_Uhash_compare@UPPID@@UPPIDHasher@DlpUtils@RealtimeProtection@@UPPIDComparer@34@@std@@V?$allocator@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@7@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUPPID@@UProcessEnforcementDescriptor@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@@std@@@std@@@std@@@2@AEBUPPID@@@Z; std::_Hash<std::_Umap_traits<PPID,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor,std::_Uhash_compare<PPID,RealtimeProtection::DlpUtils::PPIDHasher,RealtimeProtection::DlpUtils::PPIDComparer>,std::allocator<std::pair<PPID const,RealtimeProtection::DlpProcessCache::DlpProcessStateCache::ProcessEnforcementDescriptor>>,0>>::find(PPID const &)
0x18001f26f  mov     rbx, [rsp+118h+Src]
0x18001f274  cmp     rbx, [rdi+0D0h]
0x18001f27b  jnz     short loc_18001F290
0x18001f27d  mov     rcx, r15; SRWLock
0x18001f280  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f286  mov     eax, 1
0x18001f28b  jmp     loc_18001F63C
0x18001f290  lea     r13, qword_18025C818
0x18001f297  mov     rdx, r13
0x18001f29a  cmp     qword ptr [r12+10h], 0
0x18001f2a0  cmovnz  rdx, [r12+10h]
0x18001f2a6  mov     [rsp+118h+Src], rdx
0x18001f2ab  mov     r15, r13
0x18001f2ae  cmp     qword ptr [r12+8], 0
0x18001f2b4  cmovnz  r15, [r12+8]
0x18001f2ba  cmp     [rsp+118h+arg_20], 0
0x18001f2c2  jz      loc_18001F408
0x18001f2c8  test    r14, r14
0x18001f2cb  jz      loc_18001F375
0x18001f2d1  lea     rdi, [rbx+228h]
0x18001f2d8  mov     rdx, r14
0x18001f2db  lea     rcx, [rsp+118h+var_B8]
0x18001f2e0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f2e5  lea     r8, [rsp+118h+var_B8]
0x18001f2ea  lea     rdx, [rsp+118h+var_70]
0x18001f2f2  mov     rcx, rdi
0x18001f2f5  call    ??$_Eqrange@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@PEAX@std@@PEAU12@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Eqrange<std::wstring>(std::wstring const &)
0x18001f2fa  movups  xmm0, xmmword ptr [rax]
0x18001f2fd  movdqu  xmmword ptr [rsp+118h+var_58], xmm0
0x18001f306  lea     rdx, [rsp+118h+var_58]
0x18001f30e  mov     rcx, rdi
0x18001f311  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>,void *> *,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>,void *> *>)
0x18001f316  lea     rcx, [rsp+118h+var_B8]; void *
0x18001f31b  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001f320  mov     rdx, r14
0x18001f323  lea     rcx, [rsp+118h+var_B8]
0x18001f328  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f32d  lea     r8, [rsp+118h+var_B8]
0x18001f332  lea     rdx, [rsp+118h+var_70]
0x18001f33a  lea     rcx, [rbx+238h]
0x18001f341  call    ??$_Eqrange@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@PEAX@std@@PEAU12@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Eqrange<std::wstring>(std::wstring const &)
0x18001f346  movups  xmm0, xmmword ptr [rax]
0x18001f349  movdqu  xmmword ptr [rsp+118h+var_58], xmm0
0x18001f352  lea     rdx, [rsp+118h+var_58]
0x18001f35a  lea     rcx, [rbx+238h]
0x18001f361  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::wstring>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<std::wstring const,std::vector<std::wstring>>,void *> *,std::_Tree_node<std::pair<std::wstring const,std::vector<std::wstring>>,void *> *>)
0x18001f366  lea     rcx, [rsp+118h+var_B8]; void *
0x18001f36b  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001f370  jmp     loc_18001F5E8
0x18001f375  mov     rdi, [rbx+258h]
0x18001f37c  or      r12d, 0FFFFFFFFh
0x18001f380  cmp     rdi, [rbx+260h]
0x18001f387  jz      loc_18001F5E8
0x18001f38d  mov     rcx, [rdi]
0x18001f390  add     rcx, 8
0x18001f394  cmp     qword ptr [rcx+18h], 7
0x18001f399  jbe     short loc_18001F39E
0x18001f39b  mov     rcx, [rcx]; lpString1
0x18001f39e  lea     r14, [rdi+10h]
0x18001f3a2  mov     [rsp+118h+bIgnoreCase], 1; bIgnoreCase
0x18001f3aa  mov     r9d, r12d; cchCount2
0x18001f3ad  mov     r8, rdx; lpString2
0x18001f3b0  mov     edx, r12d; cchCount1
0x18001f3b3  call    cs:__imp_CompareStringOrdinal
0x18001f3b9  cmp     eax, 2
0x18001f3bc  jnz     short loc_18001F3FB
0x18001f3be  mov     r15, [rbx+260h]
0x18001f3c5  jmp     short loc_18001F3D7
0x18001f3c7  lea     rcx, [r14-10h]
0x18001f3cb  mov     rdx, r14
0x18001f3ce  call    ??4?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<RealtimeProtection::DocumentDescriptor>::operator=(std::shared_ptr<RealtimeProtection::DocumentDescriptor> &&)
0x18001f3d3  add     r14, 10h
0x18001f3d7  cmp     r14, r15
0x18001f3da  jnz     short loc_18001F3C7
0x18001f3dc  mov     rax, [rbx+260h]
0x18001f3e3  mov     rcx, [rax-8]; this
0x18001f3e7  test    rcx, rcx
0x18001f3ea  jz      short loc_18001F3F1
0x18001f3ec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f3f1  add     qword ptr [rbx+260h], 0FFFFFFFFFFFFFFF0h
0x18001f3f9  jmp     short loc_18001F3FE
0x18001f3fb  mov     rdi, r14
0x18001f3fe  mov     rdx, [rsp+118h+Src]
0x18001f403  jmp     loc_18001F380
0x18001f408  xorps   xmm0, xmm0
0x18001f40b  movups  xmmword ptr [rsp+118h+var_58], xmm0
0x18001f413  lea     rcx, [rsp+118h+var_58]
0x18001f41b  call    ??$make_shared@UDocumentDescriptor@RealtimeProtection@@$$V@std@@YA?AV?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@0@XZ; std::make_shared<RealtimeProtection::DocumentDescriptor,>(void)
0x18001f420  nop
0x18001f421  mov     ecx, [r12]
0x18001f425  mov     rax, [rsp+118h+var_58]
0x18001f42d  mov     [rax], ecx
0x18001f42f  mov     rcx, [rsp+118h+var_58]
0x18001f437  add     rcx, 28h ; '('; void *
0x18001f43b  mov     rdx, r15; Src
0x18001f43e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18001f443  mov     rcx, [rsp+118h+var_58]
0x18001f44b  add     rcx, 8; void *
0x18001f44f  mov     r12, [rsp+118h+Src]
0x18001f454  mov     rdx, r12; Src
0x18001f457  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18001f45c  mov     rax, [rsp+118h+var_C0]
0x18001f461  movsd   xmm0, qword ptr [rax]
0x18001f465  movsd   qword ptr [rsp+118h+var_E0], xmm0
0x18001f46b  mov     eax, [rax+8]
0x18001f46e  mov     dword ptr [rsp+118h+var_E0+8], eax
0x18001f472  mov     byte ptr [rsp+118h+var_E0+0Ch], 1
0x18001f477  mov     [rsp+118h+var_CC], 0
0x18001f47c  mov     byte ptr [rsp+118h+var_C8], 1
0x18001f481  xor     eax, eax
0x18001f483  mov     word ptr [rsp+118h+var_C8+1], ax
0x18001f488  mov     byte ptr [rsp+118h+var_C8+3], al
0x18001f48c  movups  xmm0, [rsp+118h+var_E0]
0x18001f491  movaps  [rsp+118h+var_B8], xmm0
0x18001f496  movsd   xmm1, qword ptr [rsp+48h]
0x18001f49c  movsd   [rsp+118h+var_A8], xmm1
0x18001f4a2  mov     eax, [rsp+118h+var_C8]
0x18001f4a6  mov     [rsp+118h+var_A0], eax
0x18001f4aa  lea     rdx, [rsp+118h+var_B8]
0x18001f4af  mov     rcx, r15
0x18001f4b2  call    ?FileExists@Utils@Dlp@@YA_NPEB_WUImpersonationOptions@DlpUtils@RealtimeProtection@@@Z; Dlp::Utils::FileExists(wchar_t const *,RealtimeProtection::DlpUtils::ImpersonationOptions)
0x18001f4b7  xor     al, 1
0x18001f4b9  mov     rcx, [rsp+118h+var_58]
0x18001f4c1  mov     [rcx+48h], al
0x18001f4c4  jz      short loc_18001F4E6
0x18001f4c6  lea     rdi, WPP_GLOBAL_Control
0x18001f4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4d4  cmp     rcx, rdi
0x18001f4d7  jz      short loc_18001F552
0x18001f4d9  test    byte ptr [rcx+1Ch], 4
0x18001f4dd  jz      short loc_18001F51E
0x18001f4df  mov     edx, 0C0h
0x18001f4e4  jmp     short loc_18001F504
0x18001f4e6  lea     rdi, WPP_GLOBAL_Control
0x18001f4ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4f4  cmp     rcx, rdi
0x18001f4f7  jz      short loc_18001F552
0x18001f4f9  test    byte ptr [rcx+1Ch], 4
0x18001f4fd  jz      short loc_18001F51E
0x18001f4ff  mov     edx, 0C1h
0x18001f504  mov     r9, r15
0x18001f507  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x18001f50e  mov     rcx, [rcx+10h]
0x18001f512  call    WPP_SF_S
0x18001f517  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f51e  cmp     rcx, rdi
0x18001f521  jz      short loc_18001F552
0x18001f523  test    byte ptr [rcx+1Ch], 4
0x18001f527  jz      short loc_18001F552
0x18001f529  test    r14, r14
0x18001f52c  cmovnz  r13, r14
0x18001f530  mov     edx, 0C2h
0x18001f535  mov     [rsp+118h+var_F0], r13; __int64
0x18001f53a  mov     qword ptr [rsp+118h+bIgnoreCase], r15; __int64
0x18001f53f  mov     r9, r12
0x18001f542  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x18001f549  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f54d  call    WPP_SF_SSS
0x18001f552  test    r14, r14
0x18001f555  jz      short loc_18001F596
0x18001f557  lea     r8, [rsp+118h+var_58]
0x18001f55f  lea     rdx, [rsp+118h+var_70]
0x18001f567  lea     rcx, [rsp+118h+var_B8]
0x18001f56c  call    ??$?0AEAPEB_WAEAV?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@std@@$0A@@?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@QEAA@AEAPEB_WAEAV?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@1@@Z; std::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>(wchar_t const * &,std::shared_ptr<RealtimeProtection::DocumentDescriptor> &)
0x18001f571  nop
0x18001f572  mov     r8, rax
0x18001f575  lea     rdx, [rsp+118h+var_70]
0x18001f57d  lea     rcx, [rbx+228h]
0x18001f584  call    ??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@UCStrOrdinalCompLess@DlpUtils@RealtimeProtection@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@2@@1@@Z; std::map<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>,RealtimeProtection::DlpUtils::CStrOrdinalCompLess,std::allocator<std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>>>::insert<std::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>>,0>(std::pair<std::wstring,std::shared_ptr<RealtimeProtection::DocumentDescriptor>> &&)
0x18001f589  nop
0x18001f58a  lea     rcx, [rsp+118h+var_B8]
0x18001f58f  call    ??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VDlpTelemetryData@DlpTelemetry@RealtimeProtection@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<RealtimeProtection::DlpTelemetry::DlpTelemetryData>>::~pair<std::wstring const,std::shared_ptr<RealtimeProtection::DlpTelemetry::DlpTelemetryData>>(void)
0x18001f594  jmp     short loc_18001F5D5
0x18001f596  mov     rcx, [rbx+260h]
0x18001f59d  cmp     rcx, [rbx+268h]
0x18001f5a4  jz      short loc_18001F5BD
0x18001f5a6  lea     rdx, [rsp+118h+var_58]
0x18001f5ae  call    ??0?$shared_ptr@VIFMBDataStore@DataStore@FileMetadata@Dlp@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore>(std::shared_ptr<Dlp::FileMetadata::DataStore::IFMBDataStore> const &)
0x18001f5b3  add     qword ptr [rbx+260h], 10h
0x18001f5bb  jmp     short loc_18001F5D5
0x18001f5bd  lea     r8, [rsp+118h+var_58]
0x18001f5c5  mov     rdx, rcx
0x18001f5c8  lea     rcx, [rbx+258h]
0x18001f5cf  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@std@@@?$vector@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@std@@V?$allocator@V?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UDocumentDescriptor@RealtimeProtection@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<RealtimeProtection::DocumentDescriptor>>::_Emplace_reallocate<std::shared_ptr<RealtimeProtection::DocumentDescriptor> const &>(std::shared_ptr<RealtimeProtection::DocumentDescriptor> * const,std::shared_ptr<RealtimeProtection::DocumentDescriptor> const &)
0x18001f5d4  nop
0x18001f5d5  mov     rcx, [rsp+118h+var_58+8]; this
0x18001f5dd  test    rcx, rcx
0x18001f5e0  jz      short loc_18001F5E8
0x18001f5e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f5e7  nop
0x18001f5e8  mov     rcx, [rsp+118h+SRWLock]; SRWLock
0x18001f5f0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f5f6  nop
0x18001f5f7  jmp     short loc_18001F601
0x18001f5f9  mov     ebx, dword ptr [rsp+118h+Src]
0x18001f5fd  test    ebx, ebx
0x18001f5ff  js      short loc_18001F609
0x18001f601  xor     eax, eax
0x18001f603  jmp     short loc_18001F63C
0x18001f605  mov     ebx, dword ptr [rsp+118h+Src]
0x18001f609  lea     rdi, WPP_GLOBAL_Control
0x18001f610  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f617  cmp     rcx, rdi
0x18001f61a  jz      short loc_18001F63A
0x18001f61c  test    byte ptr [rcx+1Ch], 1
0x18001f620  jz      short loc_18001F63A
0x18001f622  mov     edx, 0C3h
0x18001f627  mov     r9d, ebx
0x18001f62a  lea     r8, WPP_37379ce3a908304aafca380d907f5915_Traceguids
0x18001f631  mov     rcx, [rcx+10h]
0x18001f635  call    WPP_SF_d
0x18001f63a  mov     eax, ebx
0x18001f63c  mov     rcx, [rsp+118h+var_48]
0x18001f644  xor     rcx, rsp; StackCookie
0x18001f647  call    __security_check_cookie
0x18001f64c  add     rsp, 0E8h
0x18001f653  pop     r15
0x18001f655  pop     r14
0x18001f657  pop     r13
0x18001f659  pop     r12
0x18001f65b  pop     rdi
0x18001f65c  pop     rbx
0x18001f65d  retn
```
