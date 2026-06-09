# CGatherer::ProcessModifyRequest_Internal(SDataChange &,CTransactionHashEntry &,ulong)

- ea: `0x18006be9c`
- end: `0x18006c6c7`
- name: `?ProcessModifyRequest_Internal@CGatherer@@QEAAJAEAUSDataChange@@AEAVCTransactionHashEntry@@K@Z`
- size: `2091`
- prototype: `__int64 __fastcall(CGatherer *__hidden this, struct SDataChange *, struct CTransactionHashEntry *, unsigned int)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000afec`

## callees

- `0x18000d0d0`
- `0x18000d280`
- `0x180012120`
- `0x18002d4e0`
- `0x180043310`
- `0x1800485fc`
- `0x18005c9dc`
- `0x18006be9c`
- `0x18006c6d0`
- `0x18006c714`
- `0x18006c7a8`
- `0x18006cb98`
- `0x180099bbc`
- `0x18009a198`
- `0x1800a3a38`
- `0x1800af8ac`
- `0x1800b0fc0`
- `0x1800ce7c0`
- `0x1800d0914`
- `0x1800d27b4`
- `0x1800d34f4`
- `0x1800d3584`
- `0x1800d41d4`
- `0x180101738`
- `0x1801244c0`
- `0x1801299bb`
- `0x1801299c7`
- `0x1801c4ea4`
- `0x180222524`
- `0x1802228d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006c272`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006c272`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006c0b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006c131`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006c644`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006c0b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006c131`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006c644`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c318`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c35a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c318`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c35a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006c42d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006c42d`

## string_xrefs

- `0x18006c2b5`: `ProcessModifyRequest - modify times different, change detected: %u %u (link) vs %u %u (history)`
- `0x18006c125`: `ProcessModifyRequest - New modify scheduled`
- `0x18006c11c`: `ProcessModifyRequest - Modify was already scheduled - updated`
- `0x18006c321`: `ProcessModifyRequest - Notification on an URL marked as deleted -- bringing back to life (time: %d)`
- `0x18006c367`: `Queued Delete Event found and canceled (time: %d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGatherer::ProcessModifyRequest_Internal(
        CGatherer *this,
        struct SDataChange *a2,
        struct CTransactionHashEntry *a3,
        int a4)
{
  CGatherer *v7; // r15
  int v8; // ecx
  char v9; // r12
  const wchar_t **v10; // r13
  unsigned int CrawlNumberCrawled; // eax
  unsigned int v12; // r9d
  int v13; // ecx
  int v14; // eax
  unsigned int *v15; // rax
  int v16; // edx
  int v17; // ecx
  _DWORD *v18; // rbx
  char v19; // r14
  unsigned __int8 Priority; // al
  unsigned int *v21; // rbx
  unsigned int v22; // ecx
  int v23; // eax
  unsigned int v24; // ebx
  ULONGLONG v25; // rcx
  bool v26; // al
  const wchar_t *v27; // r8
  ULONGLONG v28; // rax
  __int64 v29; // rdx
  int v30; // eax
  int updated; // ebx
  LONG v33; // eax
  unsigned int v34; // ecx
  bool v35; // r9
  DWORD v36; // eax
  DWORD TickCount; // eax
  unsigned int v38; // ebx
  const void *v39; // r12
  size_t v40; // r15
  char *v41; // r14
  int v42; // edx
  int v43; // edx
  unsigned int v44; // eax
  __int64 Instance; // rax
  char v46; // r14
  bool v47; // r15
  TransactionPass *v48; // rax
  int v49; // ebx
  ULONGLONG TickCount64; // rax
  __int64 v51; // rdx
  __int64 v52; // [rsp+20h] [rbp-59h]
  __int64 v53; // [rsp+28h] [rbp-51h]
  bool v54; // [rsp+40h] [rbp-39h]
  char v55; // [rsp+42h] [rbp-37h]
  int v56; // [rsp+44h] [rbp-35h] BYREF
  CGatherer *v57; // [rsp+48h] [rbp-31h]
  FILETIME FileTime2; // [rsp+50h] [rbp-29h] BYREF
  __int64 v59; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v60[32]; // [rsp+60h] [rbp-19h] BYREF

  v7 = this;
  v57 = this;
  v56 = 0;
  v54 = *((_BYTE *)a3 + 132) != 0xFF;
  v8 = *((_DWORD *)a3 + 37);
  v9 = 1;
  if ( (v8 & 8) != 0 )
  {
    v43 = *((_DWORD *)a2 + 125);
    if ( (((unsigned __int16)v8 ^ (unsigned __int16)v43) & 0x800) != 0 )
      CTransactionHashEntry::SetTransactionFlags(a3, v8 ^ (v8 ^ v43) & 0x800);
    CTransactionHashEntry::SetShouldBeDeleted(a3, 0);
    v54 = v35;
    v55 = 1;
    v56 = *((_DWORD *)a3 + 40);
    std::_Tree<std::_Tmap_traits<unsigned long,unsigned long,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::find(
      (char *)v7 + 5336,
      &v59,
      &v56);
    if ( v59 == *((_QWORD *)v7 + 667) )
    {
      v10 = (const wchar_t **)((char *)a2 + 32);
    }
    else
    {
      std::_Tree<std::_Tmap_traits<unsigned long,unsigned long,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned long>>>>,0>(
        (char *)v7 + 5336,
        &v59);
      CTransactionHashEntry::SetTransactionFlags(a3, *((_DWORD *)a3 + 37) & 0xBFFFFFFF);
      TickCount = GetTickCount();
      v10 = (const wchar_t **)((char *)a2 + 32);
      ETWLog::LogItem(
        *((_DWORD *)a2 + 142),
        *((const wchar_t **)a2 + 4),
        L"Queued Delete Event found and canceled (time: %d)",
        TickCount);
    }
    v36 = GetTickCount();
    ETWLog::LogItem(
      *((_DWORD *)a2 + 142),
      *v10,
      L"ProcessModifyRequest - Notification on an URL marked as deleted -- bringing back to life (time: %d)",
      v36);
  }
  else
  {
    v55 = 0;
    v10 = (const wchar_t **)((char *)a2 + 32);
  }
  SDataChange::GetCrawlNumberCrawled(a2);
  CrawlNumberCrawled = SDataChange::GetCrawlNumberCrawled(a2);
  v12 = *((_DWORD *)a3 + 36);
  if ( v12 >= CrawlNumberCrawled && v12 != -1 && *((_QWORD *)a2 + 60) )
  {
    ETWLog::LogItem(
      *((_DWORD *)a2 + 142),
      *v10,
      L"ProcessModifyRequest - Notification on an existing URL denied - duplicate transaction (crawl ID: %d, request: %d)");
    return 2147749133LL;
  }
  if ( a4 != *((unsigned __int16 *)a3 + 70) )
  {
    ETWLog::LogItem(*((_DWORD *)a2 + 142), *v10, L"ProcessModifyRequest - Correcting URL start address from %d to %d");
    CTransactionHashEntry::SetStartAddressIdentifier(a3, a4);
  }
  if ( *((_QWORD *)a2 + 60) )
  {
    v44 = SDataChange::GetCrawlNumberCrawled(a2);
    CTransactionHashEntry::SetCrawlNumberCrawled(a3, v44);
  }
  v13 = *((_DWORD *)a3 + 37);
  *((_DWORD *)a2 + 125) |= v13 & 0xF95A3FFF;
  v14 = *((_DWORD *)a2 + 125);
  if ( (v13 & 0x8000) == 0 && *((_BYTE *)a3 + 132) != 0xFF )
  {
    v14 &= ~0x8000u;
    *((_DWORD *)a2 + 125) = v14;
  }
  if ( (v14 & 0x2000000) != 0 && *((_BYTE *)a3 + 132) != 0xFF && (v13 & 0x2000000) == 0 )
    *((_DWORD *)a2 + 125) = v14 & 0xFDFFFFFF;
  v15 = (unsigned int *)*((_QWORD *)a2 + 64);
  if ( v15 )
  {
    v38 = *v15;
    v39 = (const void *)*((_QWORD *)v15 + 1);
    if ( *v15 == *((_DWORD *)a3 + 12) )
    {
      if ( !v38 )
        goto LABEL_59;
      v40 = *v15;
      if ( !memcmp_0(*((const void **)v15 + 1), *((const void **)a3 + 7), v40) )
      {
LABEL_58:
        v7 = v57;
LABEL_59:
        v9 = 1;
        goto LABEL_11;
      }
    }
    else
    {
      v40 = v38;
    }
    if ( v38 >= 0x40 )
      v41 = (char *)CoTaskMemAlloc(v40);
    else
      v41 = (char *)a3 + 64;
    if ( v41 )
    {
      *(_DWORD *)a3 |= 0x10u;
      memcpy_0(v41, v39, v40);
      CTransactionHashEntry::FreeBlobPointer(a3);
      *((_QWORD *)a3 + 7) = v41;
      *((_DWORD *)a3 + 12) = v38;
    }
    goto LABEL_58;
  }
LABEL_11:
  v16 = *((_DWORD *)a2 + 125);
  if ( (v16 & 0x20000) != 0 && (*((_DWORD *)a3 + 37) & 0x20000) == 0 && *((_BYTE *)a3 + 132) != 0xFF )
  {
    v16 &= ~0x20000u;
    *((_DWORD *)a2 + 125) = v16;
  }
  if ( (v16 & 3) == 0 )
    v16 |= *((_DWORD *)a3 + 37) & 3;
  v17 = *((_DWORD *)a3 + 37);
  *((_DWORD *)a3 + 39) |= v17 ^ v16;
  if ( v16 != v17 )
  {
    *(_DWORD *)a3 |= 0x200u;
    *((_DWORD *)a3 + 37) = v16;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl) )
    CTransactionHashEntry::SetTransactionExtendedFlags(a3, *((_DWORD *)a2 + 126));
  FileTime2 = *(FILETIME *)((char *)a3 + 220);
  v18 = (_DWORD *)((char *)a2 + 492);
  if ( !*((_DWORD *)a2 + 124) && !*v18 || (*((_DWORD *)a2 + 125) & 0x8000) == 0 )
    goto LABEL_20;
  v33 = CompareFileTime((const FILETIME *)((char *)a2 + 492), &FileTime2);
  v34 = *((_DWORD *)a2 + 142);
  if ( v33 )
  {
    ETWLog::LogItem(
      v34,
      *v10,
      L"ProcessModifyRequest - modify times different, change detected: %u %u (link) vs %u %u (history)",
      *((unsigned int *)a2 + 124),
      *v18,
      FileTime2.dwHighDateTime,
      FileTime2.dwLowDateTime);
LABEL_20:
    v19 = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58816171>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_58816171>::GetImpl'::`2'::impl) )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl) )
      {
        v42 = *((_DWORD *)a3 + 52);
        if ( (v42 & 0x8000) != 0 )
          CTransactionHashEntry::SetTransactionExtendedFlags(a3, v42 & 0xFFFF7FFF);
      }
    }
    Priority = CGatherer::GetPriority(v7, a2, a3);
    if ( Priority != *((_BYTE *)a3 + 132) )
    {
      *(_DWORD *)a3 |= 0x2000u;
      *((_BYTE *)a3 + 132) = Priority;
    }
    if ( *((_DWORD *)a3 + 11) != -1 )
    {
      *(_DWORD *)a3 |= 0x4000u;
      *((_DWORD *)a3 + 11) = -1;
    }
    v21 = (unsigned int *)((char *)a2 + 504);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56981110>::GetImpl'::`2'::impl) )
    {
      *v21 |= 0x1000u;
      CTransactionHashEntry::SetTransactionExtendedFlags(a3, *((_DWORD *)a3 + 52) | 0x1000);
      Instance = winrt::Windows::Indexer::SemanticSearch::SemanticSearchConfigManager::GetInstance(&v59);
      v46 = 1;
      v56 = 1;
      v47 = 0;
      if ( (unsigned __int8)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticSearchConfigManager<winrt::Windows::Indexer::SemanticSearch::ISemanticSearchConfigManager>::IsHardwareSupported(Instance) )
      {
        std::wstring::wstring(v60, *v10);
        v46 = 3;
        if ( (unsigned __int8)IsSemanticContentIndexingApplicableOnFileItem(v60) )
          v47 = 1;
      }
      if ( (v46 & 2) != 0 )
      {
        v46 &= ~2u;
        ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v60);
      }
      if ( (v46 & 1) != 0 )
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v59);
      if ( v47 )
      {
        *v21 |= 0x800u;
        CTransactionHashEntry::SetTransactionExtendedFlags(a3, *((_DWORD *)a3 + 52) | 0x800);
      }
      v7 = v57;
      v19 = 1;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl) )
    {
      v48 = (TransactionPass *)TransactionPass::RequiredForIndexingURL(&v56, *v10);
      TransactionPass::StoreInTransactionExtendedFlags(v48, (unsigned int *)a2 + 126);
      CTransactionHashEntry::SetTransactionExtendedFlags(a3, *v21);
    }
    v22 = *((_DWORD *)a3 + 54);
    if ( v22 )
    {
      v23 = 75;
      if ( v22 > 0x4B )
        v23 = *((_DWORD *)a3 + 54);
    }
    else
    {
      v23 = 0;
    }
    v24 = (int)((double)v23 / 100.0 + 0.5);
    v25 = GetTickCount64() - qword_1802DBC88;
    v26 = !FileTime2.dwHighDateTime && !FileTime2.dwLowDateTime
       || v55
       || (*((_DWORD *)a3 + 37) & 0x41100000) != 0x1000000
       || *((_DWORD *)v7 + 309) == 1 && !*((_BYTE *)v7 + 5269);
    if ( v24 + *((_DWORD *)a3 + 53) <= dword_1802DAF18 + (unsigned int)(v25 / 0x3E8) || v26 )
    {
      v27 = L"ProcessModifyRequest - Modify was already scheduled - updated";
      if ( !v54 )
        v27 = L"ProcessModifyRequest - New modify scheduled";
      ETWLog::LogItem(*((_DWORD *)a2 + 142), *v10, v27);
    }
    else
    {
      CTransactionHashEntry::SetFutureRunTime(a3, v24);
      v49 = *((_DWORD *)a3 + 11);
      TickCount64 = GetTickCount64();
      v51 = ((TickCount64 - qword_1802DBC88) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      LODWORD(v53) = v49 - ((v51 + ((TickCount64 - qword_1802DBC88 - v51) >> 1)) >> 9) - dword_1802DAF18;
      LODWORD(v52) = *((_DWORD *)a3 + 54);
      ETWLog::LogItem(
        *((_DWORD *)a2 + 142),
        *v10,
        L"ProcessModifyRequest - Penalty Box - Item's cost is too high - last notification: %d, last cost: %d, delaying to"
         ": %d seconds from now",
        *((unsigned int *)a3 + 53),
        v52,
        v53);
    }
    v28 = GetTickCount64();
    v29 = ((v28 - qword_1802DBC88) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
    v30 = dword_1802DAF18 + ((v29 + ((v28 - qword_1802DBC88 - v29) >> 1)) >> 9);
    if ( v30 != *((_DWORD *)a3 + 53) )
    {
      *(_DWORD *)a3 |= 0x20000u;
      *((_DWORD *)a3 + 53) = v30;
    }
    if ( (*((_BYTE *)a2 + 524) & 0x20) != 0 )
      CTransactionHashEntry::SetFutureRunTime(a3, 0x15180u);
    goto LABEL_41;
  }
  v19 = 0;
  ETWLog::LogItem(
    v34,
    *((const wchar_t **)a2 + 4),
    L"ProcessModifyRequest - Modify suppressed - LastModified hasn't changed");
LABEL_41:
  updated = 0;
  if ( !*((_BYTE *)a2 + 508) || v54 )
    v9 = 0;
  *((_BYTE *)a2 + 508) = v9;
  if ( !*(_DWORD *)a3
    || (DelayProblemHandlers(a2, a3), updated = TableMap::UpdateCurrentEntry(*((TableMap **)v7 + 175), a3), updated >= 0) )
  {
    if ( !v19 )
      updated = 266755;
  }
  ETWLog::LogItemIfFailed(updated, *((_DWORD *)a2 + 142), *((const wchar_t **)a2 + 4), L"ProcessModifyRequest");
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18006be9c  push    rbp
0x18006be9e  push    rbx
0x18006be9f  push    rsi
0x18006bea0  push    rdi
0x18006bea1  push    r12
0x18006bea3  push    r13
0x18006bea5  push    r14
0x18006bea7  push    r15
0x18006bea9  lea     rbp, [rsp-1Fh]
0x18006beae  sub     rsp, 98h
0x18006beb5  mov     rax, cs:__security_cookie
0x18006bebc  xor     rax, rsp
0x18006bebf  mov     [rbp+57h+var_50], rax
0x18006bec3  mov     r14d, r9d
0x18006bec6  mov     rdi, r8
0x18006bec9  mov     rsi, rdx
0x18006becc  mov     r15, rcx
0x18006becf  mov     [rbp+57h+var_88], rcx
0x18006bed3  xor     r9d, r9d
0x18006bed6  mov     [rbp+57h+var_8C], r9d
0x18006beda  cmp     byte ptr [r8+84h], 0FFh
0x18006bee2  setnz   [rbp+57h+var_90]
0x18006bee6  mov     ecx, [r8+94h]
0x18006beed  mov     r8d, 800h
0x18006bef3  lea     r12d, [r9+1]
0x18006bef7  test    cl, 8
0x18006befa  jnz     loc_18006C489
0x18006bf00  mov     [rbp+57h+var_8E], r9b
0x18006bf04  lea     r13, [rdx+20h]
0x18006bf08  mov     rcx, rsi; this
0x18006bf0b  call    ?GetCrawlNumberCrawled@SDataChange@@QEAAKXZ; SDataChange::GetCrawlNumberCrawled(void)
0x18006bf10  mov     ebx, eax
0x18006bf12  mov     rcx, rsi; this
0x18006bf15  call    ?GetCrawlNumberCrawled@SDataChange@@QEAAKXZ; SDataChange::GetCrawlNumberCrawled(void)
0x18006bf1a  mov     r9d, [rdi+90h]
0x18006bf21  cmp     r9d, eax
0x18006bf24  jnb     loc_18006C4B0
0x18006bf2a  movzx   r9d, word ptr [rdi+8Ch]
0x18006bf32  cmp     r14d, r9d
0x18006bf35  jnz     loc_18006C4EC
0x18006bf3b  cmp     qword ptr [rsi+1E0h], 0
0x18006bf43  jnz     loc_18006C518
0x18006bf49  mov     ecx, [rdi+94h]
0x18006bf4f  mov     eax, ecx
0x18006bf51  and     eax, 0F95A3FFFh
0x18006bf56  or      [rsi+1F4h], eax
0x18006bf5c  mov     eax, [rsi+1F4h]
0x18006bf62  bt      ecx, 0Fh
0x18006bf66  jnb     loc_18006C37F
0x18006bf6c  bt      eax, 19h
0x18006bf70  jb      loc_18006C39B
0x18006bf76  mov     rax, [rsi+200h]
0x18006bf7d  test    rax, rax
0x18006bf80  jnz     loc_18006C3C1
0x18006bf86  mov     edx, [rsi+1F4h]
0x18006bf8c  mov     eax, 20000h
0x18006bf91  test    eax, edx
0x18006bf93  jnz     loc_18006C52F
0x18006bf99  test    dl, 3
0x18006bf9c  jnz     short loc_18006BFA9
0x18006bf9e  mov     eax, [rdi+94h]
0x18006bfa4  and     eax, 3
0x18006bfa7  or      edx, eax
0x18006bfa9  mov     ecx, [rdi+94h]
0x18006bfaf  mov     eax, edx
0x18006bfb1  xor     eax, ecx
0x18006bfb3  or      [rdi+9Ch], eax
0x18006bfb9  cmp     edx, ecx
0x18006bfbb  jz      short loc_18006BFC7
0x18006bfbd  bts     dword ptr [rdi], 9
0x18006bfc1  mov     [rdi+94h], edx
0x18006bfc7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55904201@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201> `wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl(void)'::`2'::impl
0x18006bfce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(void)
0x18006bfd3  test    al, al
0x18006bfd5  jz      loc_18006C1FA
0x18006bfdb  mov     rax, [rdi+0DCh]
0x18006bfe2  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], rax
0x18006bfe6  lea     rbx, [rsi+1ECh]
0x18006bfed  cmp     dword ptr [rbx+4], 0
0x18006bff1  jz      loc_18006C1EC
0x18006bff7  test    dword ptr [rsi+1F4h], 8000h
0x18006c001  jnz     loc_18006C26B
0x18006c007  mov     r14b, r12b
0x18006c00a  mov     [rbp+57h+var_8F], r12b
0x18006c00e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58816171@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58816171@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58816171> `wil::Feature<__WilFeatureTraits_Feature_58816171>::GetImpl(void)'::`2'::impl
0x18006c015  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58816171@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58816171>::__private_IsEnabled(void)
0x18006c01a  test    al, al
0x18006c01c  jnz     loc_18006C454
0x18006c022  mov     r8, rdi; struct CTransactionHashEntry *
0x18006c025  mov     rdx, rsi; struct CURL *
0x18006c028  mov     rcx, r15; this
0x18006c02b  call    ?GetPriority@CGatherer@@QEAAEAEAVCURL@@PEBVCTransactionHashEntry@@@Z; CGatherer::GetPriority(CURL &,CTransactionHashEntry const *)
0x18006c030  cmp     al, [rdi+84h]
0x18006c036  jz      short loc_18006C042
0x18006c038  bts     dword ptr [rdi], 0Dh
0x18006c03c  mov     [rdi+84h], al
0x18006c042  mov     ecx, [rdi]
0x18006c044  or      eax, 0FFFFFFFFh
0x18006c047  cmp     [rdi+2Ch], eax
0x18006c04a  jz      short loc_18006C055
0x18006c04c  bts     ecx, 0Eh
0x18006c050  mov     [rdi], ecx
0x18006c052  mov     [rdi+2Ch], eax
0x18006c055  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56981110@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110> `wil::Feature<__WilFeatureTraits_Feature_56981110>::GetImpl(void)'::`2'::impl
0x18006c05c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56981110@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56981110>::__private_IsEnabled(void)
0x18006c061  lea     rbx, [rsi+1F8h]
0x18006c068  test    al, al
0x18006c06a  jnz     loc_18006C540
0x18006c070  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55904201@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201> `wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl(void)'::`2'::impl
0x18006c077  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(void)
0x18006c07c  test    al, al
0x18006c07e  jnz     loc_18006C5E7
0x18006c084  mov     ecx, [rdi+0D8h]
0x18006c08a  test    ecx, ecx
0x18006c08c  jnz     loc_18006C60E
0x18006c092  xor     eax, eax
0x18006c094  xorps   xmm0, xmm0
0x18006c097  cvtsi2sd xmm0, rax
0x18006c09c  divsd   xmm0, cs:__real@4059000000000000
0x18006c0a4  addsd   xmm0, cs:__real@3fe0000000000000
0x18006c0ac  cvttsd2si rbx, xmm0
0x18006c0b1  call    cs:__imp_GetTickCount64
0x18006c0b7  mov     rcx, rax
0x18006c0ba  sub     rcx, cs:qword_1802DBC88
0x18006c0c1  mov     rax, 624DD2F1A9FBE77h
0x18006c0cb  mul     rcx
0x18006c0ce  sub     rcx, rdx
0x18006c0d1  shr     rcx, 1
0x18006c0d4  lea     r8, [rdx+rcx]
0x18006c0d8  shr     r8, 9
0x18006c0dc  mov     edx, [rdi+0D4h]
0x18006c0e2  add     edx, ebx
0x18006c0e4  add     r8d, cs:dword_1802DAF18
0x18006c0eb  xor     r9d, r9d
0x18006c0ee  cmp     [rbp+57h+FileTime2.dwHighDateTime], r9d
0x18006c0f2  jnz     loc_18006C20D
0x18006c0f8  cmp     [rbp+57h+FileTime2.dwLowDateTime], r9d
0x18006c0fc  jnz     loc_18006C20D
0x18006c102  mov     al, r12b
0x18006c105  cmp     edx, r8d
0x18006c108  ja      loc_18006C62F
0x18006c10e  mov     ecx, [rsi+238h]; unsigned int
0x18006c114  mov     rdx, [r13+0]; wchar_t *
0x18006c118  cmp     [rbp+57h+var_90], r9b
0x18006c11c  lea     r8, aProcessmodifyr_3; "ProcessModifyRequest - Modify was alrea"...
0x18006c123  jnz     short loc_18006C12C
0x18006c125  lea     r8, aProcessmodifyr; "ProcessModifyRequest - New modify sched"...
0x18006c12c  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18006c131  call    cs:__imp_GetTickCount64
0x18006c137  mov     r8, rax
0x18006c13a  sub     r8, cs:qword_1802DBC88
0x18006c141  mov     rax, 624DD2F1A9FBE77h
0x18006c14b  mul     r8
0x18006c14e  sub     r8, rdx
0x18006c151  shr     r8, 1
0x18006c154  lea     rax, [rdx+r8]
0x18006c158  shr     rax, 9
0x18006c15c  add     eax, cs:dword_1802DAF18
0x18006c162  cmp     eax, [rdi+0D4h]
0x18006c168  jz      short loc_18006C174
0x18006c16a  bts     dword ptr [rdi], 11h
0x18006c16e  mov     [rdi+0D4h], eax
0x18006c174  test    byte ptr [rsi+20Ch], 20h
0x18006c17b  jnz     loc_18006C6A6
0x18006c181  xor     r13d, r13d
0x18006c184  mov     ebx, r13d
0x18006c187  cmp     [rsi+1FCh], r13b
0x18006c18e  jnz     loc_18006C6B8
0x18006c194  mov     r12b, r13b
0x18006c197  mov     [rsi+1FCh], r12b
0x18006c19e  cmp     [rdi], r13d
0x18006c1a1  jnz     loc_18006C242
0x18006c1a7  mov     eax, 41203h
0x18006c1ac  test    r14b, r14b
0x18006c1af  cmovz   ebx, eax
0x18006c1b2  lea     r9, aProcessmodifyr_4; "ProcessModifyRequest"
0x18006c1b9  mov     r8, [rsi+20h]; wchar_t *
0x18006c1bd  mov     edx, [rsi+238h]; unsigned int
0x18006c1c3  mov     ecx, ebx; int
0x18006c1c5  call    ?LogItemIfFailed@ETWLog@@SAXJKPEB_W0ZZ; ETWLog::LogItemIfFailed(long,ulong,wchar_t const *,wchar_t const *,...)
0x18006c1ca  mov     eax, ebx
0x18006c1cc  mov     rcx, [rbp+57h+var_50]
0x18006c1d0  xor     rcx, rsp; StackCookie
0x18006c1d3  call    __security_check_cookie
0x18006c1d8  add     rsp, 98h
0x18006c1df  pop     r15
0x18006c1e1  pop     r14
0x18006c1e3  pop     r13
0x18006c1e5  pop     r12
0x18006c1e7  pop     rdi
0x18006c1e8  pop     rsi
0x18006c1e9  pop     rbx
0x18006c1ea  pop     rbp
0x18006c1eb  retn
0x18006c1ec  cmp     dword ptr [rbx], 0
0x18006c1ef  jz      loc_18006C007
0x18006c1f5  jmp     loc_18006BFF7
0x18006c1fa  mov     edx, [rsi+1F8h]; unsigned int
0x18006c200  mov     rcx, rdi; this
0x18006c203  call    ?SetTransactionExtendedFlags@CTransactionHashEntry@@QEAAXK@Z; CTransactionHashEntry::SetTransactionExtendedFlags(ulong)
0x18006c208  jmp     loc_18006BFDB
0x18006c20d  cmp     [rbp+57h+var_8E], r9b
0x18006c211  jnz     loc_18006C102
0x18006c217  mov     eax, [rdi+94h]
0x18006c21d  and     eax, 41100000h
0x18006c222  cmp     eax, 1000000h
0x18006c227  jnz     loc_18006C102
0x18006c22d  cmp     [r15+4D4h], r12d
0x18006c234  jz      loc_18006C61D
0x18006c23a  mov     al, r9b
0x18006c23d  jmp     loc_18006C105
0x18006c242  mov     rdx, rdi; struct CTransactionHashEntry *
0x18006c245  mov     rcx, rsi; struct SDataChange *
0x18006c248  call    ?DelayProblemHandlers@@YAXAEAUSDataChange@@AEAVCTransactionHashEntry@@@Z; DelayProblemHandlers(SDataChange &,CTransactionHashEntry &)
0x18006c24d  mov     rdx, rdi; struct CTransactionHashEntry *
0x18006c250  mov     rcx, [r15+578h]; this
0x18006c257  call    ?UpdateCurrentEntry@TableMap@@UEAAJPEBVCTransactionHashEntry@@@Z; TableMap::UpdateCurrentEntry(CTransactionHashEntry const *)
0x18006c25c  mov     ebx, eax
0x18006c25e  test    eax, eax
0x18006c260  js      loc_18006C1B2
0x18006c266  jmp     loc_18006C1A7
0x18006c26b  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x18006c26f  mov     rcx, rbx; lpFileTime1
0x18006c272  call    cs:__imp_CompareFileTime
0x18006c278  mov     ecx, [rsi+238h]; unsigned int
0x18006c27e  test    eax, eax
0x18006c280  jnz     short loc_18006C29A
0x18006c282  xor     r14b, r14b
0x18006c285  lea     r8, aProcessmodifyr_0; "ProcessModifyRequest - Modify suppresse"...
0x18006c28c  mov     rdx, [rsi+20h]; wchar_t *
0x18006c290  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18006c295  jmp     loc_18006C181
0x18006c29a  mov     eax, [rbp+57h+FileTime2.dwLowDateTime]
0x18006c29d  mov     [rsp+0D0h+var_A0], eax
0x18006c2a1  mov     eax, [rbp+57h+FileTime2.dwHighDateTime]
0x18006c2a4  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18006c2a8  mov     eax, [rbx]
0x18006c2aa  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18006c2ae  mov     r9d, [rsi+1F0h]
0x18006c2b5  lea     r8, aProcessmodifyr_5; "ProcessModifyRequest - modify times dif"...
0x18006c2bc  mov     rdx, [r13+0]; wchar_t *
0x18006c2c0  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18006c2c5  jmp     loc_18006C007
0x18006c2ca  mov     r15, [rbp+57h+var_88]
0x18006c2ce  mov     r12d, 1
0x18006c2d4  jmp     loc_18006BF86
0x18006c2d9  xor     edx, edx; bool
0x18006c2db  mov     rcx, rdi; this
0x18006c2de  call    ?SetShouldBeDeleted@CTransactionHashEntry@@QEAAX_N@Z; CTransactionHashEntry::SetShouldBeDeleted(bool)
0x18006c2e3  mov     [rbp+57h+var_90], r9b
0x18006c2e7  mov     [rbp+57h+var_8E], r12b
0x18006c2eb  lea     rbx, [r15+14D8h]
0x18006c2f2  mov     eax, [rdi+0A0h]
0x18006c2f8  mov     [rbp+57h+var_8C], eax
0x18006c2fb  lea     r8, [rbp+57h+var_8C]
0x18006c2ff  lea     rdx, [rbp+57h+var_78]
0x18006c303  mov     rcx, rbx
0x18006c306  call    ?find@?$_Tree@V?$_Tmap_traits@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,ulong,std::less<ulong>,std::allocator<std::pair<ulong const,ulong>>,0>>::find(ulong const &)
0x18006c30b  mov     r8, [rbp+57h+var_78]
0x18006c30f  cmp     r8, [rbx]
0x18006c312  jnz     short loc_18006C33C
0x18006c314  lea     r13, [rsi+20h]
0x18006c318  call    cs:__imp_GetTickCount
0x18006c31e  mov     r9d, eax
0x18006c321  lea     r8, aProcessmodifyr_1; "ProcessModifyRequest - Notification on "...
0x18006c328  mov     rdx, [r13+0]; wchar_t *
0x18006c32c  mov     ecx, [rsi+238h]; unsigned int
0x18006c332  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18006c337  jmp     loc_18006BF08
0x18006c33c  lea     rdx, [rbp+57h+var_78]
0x18006c340  mov     rcx, rbx
0x18006c343  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@KKU?$less@K@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<ulong,ulong,std::less<ulong>,std::allocator<std::pair<ulong const,ulong>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ulong>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ulong>>>>)
0x18006c348  mov     edx, [rdi+94h]
0x18006c34e  btr     edx, 1Eh; unsigned int
0x18006c352  mov     rcx, rdi; this
0x18006c355  call    ?SetTransactionFlags@CTransactionHashEntry@@QEAAXK@Z; CTransactionHashEntry::SetTransactionFlags(ulong)
0x18006c35a  call    cs:__imp_GetTickCount
0x18006c360  lea     r13, [rsi+20h]
0x18006c364  mov     r9d, eax
0x18006c367  lea     r8, aQueuedDeleteEv; "Queued Delete Event found and canceled "...
0x18006c36e  mov     rdx, [r13+0]; wchar_t *
0x18006c372  mov     ecx, [rsi+238h]; unsigned int
0x18006c378  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18006c37d  jmp     short loc_18006C318
0x18006c37f  cmp     byte ptr [rdi+84h], 0FFh
0x18006c386  jz      loc_18006BF6C
0x18006c38c  btr     eax, 0Fh
0x18006c390  mov     [rsi+1F4h], eax
0x18006c396  jmp     loc_18006BF6C
0x18006c39b  cmp     byte ptr [rdi+84h], 0FFh
0x18006c3a2  jz      loc_18006BF76
0x18006c3a8  bt      ecx, 19h
0x18006c3ac  jb      loc_18006BF76
0x18006c3b2  btr     eax, 19h
0x18006c3b6  mov     [rsi+1F4h], eax
0x18006c3bc  jmp     loc_18006BF76
0x18006c3c1  mov     ebx, [rax]
0x18006c3c3  mov     r12, [rax+8]
0x18006c3c7  cmp     ebx, [rdi+30h]
0x18006c3ca  jz      short loc_18006C406
  ... truncated ...
```
