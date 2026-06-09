# RealtimeProtection::CRtpDlpEngine::OnNewProcess(ulong,PPID const &,PPID const &,wchar_t const *,wchar_t const *,_MP_KNOWN_PROCESS_TYPE)

- ea: `0x1801a0290`
- end: `0x1801a0e8e`
- name: `?OnNewProcess@CRtpDlpEngine@RealtimeProtection@@QEAAJKAEBUPPID@@0PEB_W1W4_MP_KNOWN_PROCESS_TYPE@@@Z`
- size: `3070`
- prototype: `int __high(unsigned int, const struct PPID *, const struct PPID *, const wchar_t *, const wchar_t *, enum _MP_KNOWN_PROCESS_TYPE)`
- caller_count: `2`
- callee_count: `31`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180050370`
- `0x1800689f0`

## callees

- `0x18001b9ec`
- `0x180028a10`
- `0x180028d80`
- `0x18003fa60`
- `0x18003fb10`
- `0x180040d60`
- `0x180044eb0`
- `0x180079dc0`
- `0x1800809d0`
- `0x1800890e0`
- `0x18008aa18`
- `0x180091f04`
- `0x180096378`
- `0x180096a40`
- `0x18009bd10`
- `0x1800a33f8`
- `0x1800a4018`
- `0x1800ab660`
- `0x1800c98a4`
- `0x180107874`
- `0x18010b558`
- `0x18010b568`
- `0x18010cb40`
- `0x18010ce44`
- `0x18010ed90`
- `0x180119740`
- `0x180145e30`
- `0x180161464`
- `0x1801a0290`
- `0x1801a3fb8`
- `0x18023a290`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x1801a0384`
- `KERNEL32!AcquireSRWLockShared` at `0x1801a0985`
- `KERNEL32!AcquireSRWLockShared` at `0x1801a0384`
- `KERNEL32!AcquireSRWLockShared` at `0x1801a0985`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a03a0`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a04a1`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a04ee`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a05b9`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0688`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a085e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0a6d`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0a7d`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0b40`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0bbd`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0c19`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0d16`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a03a0`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a04a1`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a04ee`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a05b9`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0688`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a085e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0a6d`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0a7d`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0b40`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0bbd`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0c19`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801a0d16`
- `KERNEL32!CompareFileTime` at `0x1801a0a28`
- `KERNEL32!CompareFileTime` at `0x1801a0a28`
- `SHLWAPI!StrStrIW` at `0x1801a03b7`
- `SHLWAPI!StrStrIW` at `0x1801a03b7`

## string_xrefs

- `0x1801a06dd`: `RealtimeProtection::DlpRtpPluginQuery::IsSetWindowsHooksProcess`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall RealtimeProtection::CRtpDlpEngine::OnNewProcess(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        FILETIME *a4,
        wchar_t *Str,
        const WCHAR *pszFirst,
        int a7)
{
  PVOID *v10; // rcx
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  RTL_SRWLOCK *v14; // r15
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  std::_Ref_count_base *v18; // rbx
  RealtimeProtection::DlpProcessCache::DlpProcessStateCache *v19; // rdi
  int v20; // edi
  int v21; // eax
  enum RealtimeProtection::AppBlanketLevel *v22; // r8
  unsigned int v23; // ebx
  unsigned int Value; // eax
  unsigned int v25; // r8d
  int v26; // eax
  RealtimeProtection::DlpPlugin *v27; // rcx
  int v28; // eax
  struct RealtimeProtection::DlpCEngine **v29; // rdx
  RealtimeProtection::DlpProcessCache::DlpProcessStateCache *v30; // rbx
  bool v31; // r12
  int v32; // eax
  int v33; // edi
  FILETIME *v34; // rdi
  int v35; // eax
  unsigned int v36; // ebx
  unsigned int v37; // ebx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  unsigned __int8 v41; // al
  DWORD dwLowDateTime; // ebx
  std::_Ref_count_base *v43; // rdi
  RTL_SRWLOCK *v44; // rbx
  RTL_SRWLOCK *v45; // rcx
  RTL_SRWLOCK *v46; // r8
  __int64 v47; // rdx
  __int64 v48; // rbx
  char v49; // bl
  int v50; // eax
  unsigned int v51; // edi
  FILETIME *v52; // r14
  int AppBlanketEnforcementLevel; // eax
  bool *v54; // r8
  int v55; // eax
  int EngineConfigForAppBlanketEnforcement; // eax
  __int64 v57; // rdx
  int v58; // eax
  RealtimeProtection::CRtpDlpEngine *v59; // rcx
  wchar_t *v60; // rbx
  unsigned int v61; // r15d
  _OWORD *v62; // r14
  unsigned int v63; // ebx
  RealtimeProtection::DlpPlugin *v64; // rcx
  struct RealtimeProtection::CPluginWorkItemQueue *PluginWorkItemQueue; // rax
  __int64 v66; // rax
  __int64 v67; // rbx
  char v68[8]; // [rsp+20h] [rbp-F8h]
  char v69[4]; // [rsp+20h] [rbp-F8h]
  char v70[8]; // [rsp+28h] [rbp-F0h]
  int v71; // [rsp+28h] [rbp-F0h]
  int v72; // [rsp+40h] [rbp-D8h]
  char v73[4]; // [rsp+50h] [rbp-C8h] BYREF
  char v74[4]; // [rsp+54h] [rbp-C4h]
  FILETIME *lpFileTime1; // [rsp+58h] [rbp-C0h]
  RealtimeProtection::DlpProcessCache::DlpProcessStateCache *v76; // [rsp+60h] [rbp-B8h] BYREF
  wchar_t *v77; // [rsp+68h] [rbp-B0h]
  wchar_t *String1; // [rsp+70h] [rbp-A8h]
  __int64 v79; // [rsp+78h] [rbp-A0h]
  __int64 v80; // [rsp+80h] [rbp-98h]
  PSRWLOCK SRWLock; // [rsp+88h] [rbp-90h]
  RTL_SRWLOCK *v82; // [rsp+98h] [rbp-80h]
  char v83; // [rsp+A0h] [rbp-78h]
  FILETIME FileTime1; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v85; // [rsp+B8h] [rbp-60h]
  _QWORD v86[2]; // [rsp+C0h] [rbp-58h] BYREF

  lpFileTime1 = a4;
  *(_DWORD *)v74 = a2;
  v79 = a1;
  v77 = Str;
  v80 = (__int64)pszFirst;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_ddDSS(*((_QWORD *)WPP_GLOBAL_Control + 2), a4[1].dwLowDateTime, a2, (__int64)Str, (__int64)pszFirst);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(a1 + 8) != 2 )
    return 0;
  if ( Str && pszFirst )
  {
    v12 = wcsrchr(Str, 0x5Cu);
    if ( v12 )
      v13 = v12 + 1;
    else
      v13 = Str;
    String1 = v13;
    v14 = (RTL_SRWLOCK *)(a1 + 16);
    v82 = v14;
    AcquireSRWLockShared(v14);
    v83 = 1;
    if ( *(_DWORD *)(v79 + 8) != 2 )
    {
      ReleaseSRWLockShared(v14);
      return 0;
    }
    if ( !StrStrIW(pszFirst, L" -k ClipboardSvcGroup -p") )
    {
      Value = Dlp::FeatureControl::GetValue(222);
      if ( RealtimeProtection::DlpUtils::IsAutoInjectionCandidate(v13, (const wchar_t *)Value, v25) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SLLS(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_DWORD *)(a3 + 8), a2, (__int64)pszFirst);
        v70[0] = 0;
        v68[0] = 1;
        v26 = RealtimeProtection::DlpProcessCache::AddProcess(
                a3,
                lpFileTime1,
                a2,
                v13,
                *(_DWORD *)v68,
                *(_DWORD *)v70,
                a7,
                0,
                0);
        v23 = v26;
        if ( v26 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              563,
              &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              (unsigned int)v26);
          goto LABEL_48;
        }
      }
      else if ( v13 )
      {
        if ( wcsicmp(v13, L"acrobat.exe") )
        {
          if ( (unsigned int)RealtimeProtection::DlpPlugin::IsPluginInitialized(v27) )
          {
            v76 = 0;
            RealtimeProtection::DlpPlugin::GetEngine((RealtimeProtection::DlpPlugin *)&v76, v29);
            v30 = v76;
            if ( v76 )
            {
              v31 = 0;
              v85 = 0;
              FileTime1 = (FILETIME)v13;
              v32 = (*((__int64 (__fastcall **)(_QWORD, __int64, FILETIME *, __int64))v76 + 2))(
                      *((_QWORD *)v76 + 3),
                      16551,
                      &FileTime1,
                      16);
              v33 = v32;
              if ( v32 >= 0 )
              {
                v31 = (_DWORD)v85 == 1;
                v33 = 0;
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  26,
                  (unsigned int)WPP_2f1a258b79b036cc8d24fffabf360af1_Traceguids,
                  (unsigned int)"RealtimeProtection::DlpCEngine::DlpQueryEngineSetWindowsHooksUsed",
                  v32);
              }
              if ( v33 >= 0 && v31 )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v30 + 2, 0xFFFFFFFF) <= 1 )
                {
                  _mm_lfence();
                  (**(void (__fastcall ***)(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *, __int64))v30)(
                    v30,
                    1);
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  WPP_SF_SLLS(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_DWORD *)(a3 + 8), v74[0], v80);
                v70[0] = 0;
                v68[0] = 1;
                v34 = lpFileTime1;
                v35 = RealtimeProtection::DlpProcessCache::AddProcess(
                        a3,
                        lpFileTime1,
                        *(unsigned int *)v74,
                        String1,
                        *(_DWORD *)v68,
                        *(_DWORD *)v70,
                        a7,
                        0,
                        1);
                v36 = v35;
                if ( v35 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      567,
                      &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                      (unsigned int)v35);
                  goto LABEL_70;
                }
LABEL_74:
                v37 = 0;
                if ( (unsigned int)(a7 - 9) > 1 )
                  goto LABEL_107;
                LODWORD(v86[0]) = 0;
                FileTime1 = *v34;
                LODWORD(v85) = v34[1].dwLowDateTime;
                RealtimeProtection::DlpProcessCache::GetKnownProcessType(&FileTime1, v86);
                if ( LODWORD(v86[0]) != a7 )
                {
                  v41 = 1;
                  v73[0] = 1;
                  goto LABEL_100;
                }
                v73[0] = 0;
                v86[0] = *v34;
                dwLowDateTime = v34[1].dwLowDateTime;
                Lock_shared_ptr_spin_lock(v39, v38, v40);
                v43 = qword_180314488;
                if ( qword_180314488 )
                {
                  _InterlockedIncrement((volatile signed __int32 *)qword_180314488 + 2);
                  v43 = qword_180314488;
                }
                v76 = qword_180314480;
                Unlock_shared_ptr_spin_lock();
                if ( !v76 )
                {
                  if ( v43 )
                    std::_Ref_count_base::_Decref(v43);
                  goto LABEL_107;
                }
                FileTime1 = (FILETIME)v86[0];
                LODWORD(v85) = dwLowDateTime;
                v44 = (RTL_SRWLOCK *)((char *)v76 + 464);
                SRWLock = (PSRWLOCK)((char *)v76 + 464);
                AcquireSRWLockShared((PSRWLOCK)v76 + 58);
                if ( *((_QWORD *)v76 + 27) )
                {
                  LODWORD(v86[0]) = 0;
                  MpHashCrc32(v86, 12);
                  v46 = (RTL_SRWLOCK *)v76;
                  v47 = *((_QWORD *)v76 + 28);
                  v48 = *(_QWORD *)(v47 + 16 * (*((_QWORD *)v76 + 31) & LODWORD(v86[0])) + 8);
                  if ( v48 != *((_QWORD *)v76 + 26) )
                  {
                    v86[0] = *(_QWORD *)(v47 + 16 * (*((_QWORD *)v76 + 31) & LODWORD(v86[0])));
                    while ( 1 )
                    {
                      if ( (_DWORD)v85 == *(_DWORD *)(v48 + 24)
                        && !CompareFileTime(&FileTime1, (const FILETIME *)(v48 + 16)) )
                      {
                        v46 = (RTL_SRWLOCK *)v76;
                        goto LABEL_91;
                      }
                      if ( v48 == v86[0] )
                        break;
                      v48 = *(_QWORD *)(v48 + 8);
                    }
                    v46 = (RTL_SRWLOCK *)v76;
                  }
                  v48 = 0;
LABEL_91:
                  if ( v48 && (PVOID)v48 != v46[26].Ptr )
                  {
                    v49 = *(_BYTE *)(v48 + 472);
                    ReleaseSRWLockShared(v46 + 58);
                    goto LABEL_96;
                  }
                  v45 = SRWLock;
                }
                else
                {
                  v45 = v44;
                }
                ReleaseSRWLockShared(v45);
                v49 = 0;
LABEL_96:
                if ( v43 )
                  std::_Ref_count_base::_Decref(v43);
                if ( v49 )
                {
                  v37 = 1;
                  v41 = 0;
LABEL_100:
                  *(_DWORD *)v70 = *(_DWORD *)v74;
                  *(_DWORD *)v68 = v41;
                  RealtimeProtection::MpLogMessageImpl(
                    (RealtimeProtection *)L"[DlpEngine] Adding executable due to process hierarchy policy: application nam"
                                           "e: %ls pid %lu hierarchyPolicy %d isRootProcess %d for session %lu: %ls",
                    v77,
                    *(unsigned int *)(a3 + 8),
                    v37,
                    *(_QWORD *)v68,
                    *(_QWORD *)v70,
                    v80);
                  LOBYTE(v72) = 0;
                  LOBYTE(v71) = v73[0];
                  v69[0] = 0;
                  v50 = RealtimeProtection::DlpProcessCache::AddProcess(
                          a3,
                          lpFileTime1,
                          *(unsigned int *)v74,
                          String1,
                          *(_DWORD *)v69,
                          v71,
                          a7,
                          v37,
                          v72);
                  v51 = v50;
                  if ( v50 < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        569,
                        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                        (unsigned int)v50);
LABEL_104:
                    ReleaseSRWLockShared(v14);
                    return v51;
                  }
LABEL_108:
                  if ( !*(_BYTE *)(v79 + 108) )
                  {
                    v52 = lpFileTime1;
LABEL_130:
                    if ( (unsigned int)Dlp::FeatureControl::GetValue(166) )
                    {
                      v60 = v77;
                      if ( (int)RealtimeProtection::CRtpDlpEngine::CheckAndSetAppDelegation(
                                  v59,
                                  (const struct PPID *)a3,
                                  (const struct PPID *)v52,
                                  v77) >= 0
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                      {
                        WPP_SF_ddS(*((_QWORD *)WPP_GLOBAL_Control + 2), v52[1].dwLowDateTime, (__int64)v60);
                      }
                    }
                    ReleaseSRWLockShared(v14);
                    if ( (*(_DWORD *)(v79 + 112) & 1) != 0 )
                    {
                      v61 = *(_DWORD *)v74;
                      if ( *(_DWORD *)v74 )
                      {
                        if ( String1 && !wcsicmp(String1, L"explorer.exe") )
                        {
                          v62 = operator new(0x58u);
                          *v62 = 0;
                          v62[1] = 0;
                          v62[2] = 0;
                          v62[3] = 0;
                          v62[4] = 0;
                          *((_QWORD *)v62 + 10) = 0;
                          v63 = *(_DWORD *)(a3 + 8);
                          PluginWorkItemQueue = RealtimeProtection::DlpPlugin::GetPluginWorkItemQueue(v64);
                          v66 = RealtimeProtection::CDlpUserAgentWorkItem::CDlpUserAgentWorkItem(
                                  (RealtimeProtection::CDlpUserAgentWorkItem *)v62,
                                  PluginWorkItemQueue,
                                  v61,
                                  v63,
                                  1u);
                          v67 = v66;
                          if ( v66 )
                          {
                            _InterlockedIncrement((volatile signed __int32 *)(v66 + 8));
                            RealtimeProtection::CMpPluginWorkItemBase::PrioritizedDispatchJob(v66, 5);
                            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v67 + 8), 0xFFFFFFFF) <= 1 )
                            {
                              _mm_lfence();
                              (**(void (__fastcall ***)(__int64, __int64))v67)(v67, 1);
                            }
                          }
                          else
                          {
                            RealtimeProtection::CMpPluginWorkItemBase::PrioritizedDispatchJob(0, 5);
                          }
                        }
                      }
                    }
                    if ( (v51 & 0x80000000) != 0
                      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        575,
                        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                        v51);
                    }
                    return v51;
                  }
                  LODWORD(v86[0]) = 0;
                  v52 = lpFileTime1;
                  AppBlanketEnforcementLevel = RealtimeProtection::DlpProcessCache::GetAppBlanketEnforcementLevel(
                                                 lpFileTime1,
                                                 (const struct PPID *)v86,
                                                 v22);
                  v36 = AppBlanketEnforcementLevel;
                  if ( AppBlanketEnforcementLevel < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        570,
                        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                        (unsigned int)AppBlanketEnforcementLevel);
LABEL_70:
                    ReleaseSRWLockShared(v14);
                    return v36;
                  }
                  if ( LODWORD(v86[0]) == 2 )
                  {
                    v55 = RealtimeProtection::DlpProcessCache::SetAppBlanketEnforcementLevel(a3, 2);
                    v51 = v55;
                    if ( v55 < 0 )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          571,
                          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                          (unsigned int)v55);
                      goto LABEL_104;
                    }
                    goto LABEL_130;
                  }
                  v73[0] = 0;
                  EngineConfigForAppBlanketEnforcement = RealtimeProtection::DlpEngineUtils::GetEngineConfigForAppBlanketEnforcement(
                                                           (RealtimeProtection::DlpEngineUtils *)a3,
                                                           (const struct PPID *)v73,
                                                           v54);
                  if ( EngineConfigForAppBlanketEnforcement >= 0 )
                  {
                    if ( !v73[0] )
                    {
                      v57 = 2;
                      goto LABEL_125;
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      572,
                      &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                      (unsigned int)EngineConfigForAppBlanketEnforcement);
                    v57 = 1;
LABEL_125:
                    v58 = RealtimeProtection::DlpProcessCache::SetAppBlanketEnforcementLevel(a3, v57);
                    v51 = v58;
                    if ( v58 < 0
                      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        573,
                        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                        (unsigned int)v58);
                    }
                    goto LABEL_130;
                  }
                  v57 = 1;
                  goto LABEL_125;
                }
LABEL_107:
                v51 = 0;
                goto LABEL_108;
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v30 + 2, 0xFFFFFFFF) <= 1 )
              {
                _mm_lfence();
                (**(void (__fastcall ***)(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *, __int64))v30)(
                  v30,
                  1);
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                40,
                WPP_9bce63ce04f53a278728ac7dd0e232b4_Traceguids,
                "RealtimeProtection::DlpRtpPluginQuery::IsSetWindowsHooksProcess");
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SLLS(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_DWORD *)(a3 + 8), a2, (__int64)pszFirst);
          v70[0] = 0;
          v68[0] = 1;
          v28 = RealtimeProtection::DlpProcessCache::AddProcess(
                  a3,
                  lpFileTime1,
                  a2,
                  v13,
                  *(_DWORD *)v68,
                  *(_DWORD *)v70,
                  a7,
                  0,
                  0);
          v23 = v28;
          if ( v28 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                565,
                &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
                (unsigned int)v28);
            goto LABEL_48;
          }
        }
      }
LABEL_73:
      v34 = lpFileTime1;
      goto LABEL_74;
    }
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"[DlpEngine] tracking cbdhsvc pid %lu for session %lu: %ls",
      (const wchar_t *)*(unsigned int *)(a3 + 8),
      a2,
      pszFirst);
    Lock_shared_ptr_spin_lock(v16, v15, v17);
    v18 = qword_180314488;
    if ( qword_180314488 )
    {
      _InterlockedIncrement((volatile signed __int32 *)qword_180314488 + 2);
      v18 = qword_180314488;
    }
    v19 = qword_180314480;
    Unlock_shared_ptr_spin_lock();
    if ( v19 )
    {
      v20 = RealtimeProtection::DlpProcessCache::DlpProcessStateCache::SetCbdhsvcPpid(v19, a2, (const struct PPID *)a3);
      if ( v18 )
        std::_Ref_count_base::_Decref(v18);
      if ( v20 >= 0 )
      {
        v70[0] = 0;
        v68[0] = 0;
        v21 = RealtimeProtection::DlpProcessCache::AddProcess(
                a3,
                lpFileTime1,
                a2,
                v77,
                *(_DWORD *)v68,
                *(_DWORD *)v70,
                a7,
                0,
                0);
        v23 = v21;
        if ( v21 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              561,
              &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
              (unsigned int)v21);
LABEL_48:
          ReleaseSRWLockShared(v14);
          return v23;
        }
        goto LABEL_73;
      }
    }
    else
    {
      if ( v18 )
        std::_Ref_count_base::_Decref(v18);
      v20 = -2147483634;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        560,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v20);
    ReleaseSRWLockShared(v14);
    return (unsigned int)v20;
  }
  else
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      WPP_SF_d(v10[2], 559, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1801a0290  push    rbx
0x1801a0292  push    rsi
0x1801a0293  push    rdi
0x1801a0294  push    r12
0x1801a0296  push    r13
0x1801a0298  push    r14
0x1801a029a  push    r15
0x1801a029c  sub     rsp, 0E0h
0x1801a02a3  mov     rax, cs:__security_cookie
0x1801a02aa  xor     rax, rsp
0x1801a02ad  mov     [rsp+118h+var_48], rax
0x1801a02b5  mov     [rsp+118h+lpFileTime1], r9
0x1801a02ba  mov     r13, r8
0x1801a02bd  mov     r12d, edx
0x1801a02c0  mov     dword ptr [rsp+118h+var_C4], edx
0x1801a02c4  mov     r15, rcx
0x1801a02c7  mov     [rsp+118h+var_A0], rcx
0x1801a02cc  mov     r14, [rsp+118h+Str]
0x1801a02d4  mov     [rsp+118h+var_B0], r14
0x1801a02d9  mov     rbx, [rsp+118h+pszFirst]
0x1801a02e1  mov     [rsp+118h+var_98], rbx
0x1801a02e9  lea     rsi, WPP_GLOBAL_Control
0x1801a02f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a02f7  cmp     rcx, rsi
0x1801a02fa  jz      short loc_1801A0332
0x1801a02fc  test    byte ptr [rcx+1Ch], 4
0x1801a0300  jz      short loc_1801A0332
0x1801a0302  mov     edx, 22Eh
0x1801a0307  mov     [rsp+118h+var_E0], rbx; __int64
0x1801a030c  mov     [rsp+118h+var_E8], r14; __int64
0x1801a0311  mov     dword ptr [rsp+118h+var_F0], r12d; char
0x1801a0316  mov     eax, [r9+8]
0x1801a031a  mov     dword ptr [rsp+118h+var_F8], eax; char
0x1801a031e  mov     r9d, [r8+8]
0x1801a0322  mov     rcx, [rcx+10h]; LoggerHandle
0x1801a0326  call    WPP_SF_ddDSS
0x1801a032b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a0332  cmp     dword ptr [r15+8], 2
0x1801a0337  jz      short loc_1801A0340
0x1801a0339  xor     eax, eax
0x1801a033b  jmp     loc_1801A0E6B
0x1801a0340  test    r14, r14
0x1801a0343  jz      loc_1801A0DF6
0x1801a0349  test    rbx, rbx
0x1801a034c  jz      loc_1801A0DF6
0x1801a0352  mov     edx, 5Ch ; '\'; Ch
0x1801a0357  mov     rcx, r14; Str
0x1801a035a  call    wcsrchr
0x1801a035f  mov     rdi, rax
0x1801a0362  test    rax, rax
0x1801a0365  jnz     short loc_1801A036C
0x1801a0367  mov     rdi, r14
0x1801a036a  jmp     short loc_1801A0370
0x1801a036c  add     rdi, 2
0x1801a0370  mov     [rsp+118h+String1], rdi
0x1801a0375  add     r15, 10h
0x1801a0379  mov     [rsp+118h+var_80], r15
0x1801a0381  mov     rcx, r15; SRWLock
0x1801a0384  call    cs:__imp_AcquireSRWLockShared
0x1801a038a  mov     [rsp+118h+var_78], 1
0x1801a0392  mov     rcx, [rsp+118h+var_A0]
0x1801a0397  cmp     dword ptr [rcx+8], 2
0x1801a039b  jz      short loc_1801A03AD
0x1801a039d  mov     rcx, r15; SRWLock
0x1801a03a0  call    cs:__imp_ReleaseSRWLockShared
0x1801a03a6  xor     eax, eax
0x1801a03a8  jmp     loc_1801A0E6B
0x1801a03ad  lea     rdx, pszSrch; " -k ClipboardSvcGroup -p"
0x1801a03b4  mov     rcx, rbx; pszFirst
0x1801a03b7  call    cs:__imp_StrStrIW
0x1801a03bd  test    rax, rax
0x1801a03c0  jz      loc_1801A04FB
0x1801a03c6  mov     r9, rbx
0x1801a03c9  mov     r8d, r12d
0x1801a03cc  mov     edx, [r13+8]; wchar_t *
0x1801a03d0  lea     rcx, aDlpengineTrack_0; "[DlpEngine] tracking cbdhsvc pid %lu fo"...
0x1801a03d7  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a03dc  call    _Lock_shared_ptr_spin_lock
0x1801a03e1  mov     rbx, cs:qword_180314488
0x1801a03e8  test    rbx, rbx
0x1801a03eb  jz      short loc_1801A03F8
0x1801a03ed  lock inc dword ptr [rbx+8]
0x1801a03f1  mov     rbx, cs:qword_180314488
0x1801a03f8  mov     rdi, cs:qword_180314480
0x1801a03ff  call    _Unlock_shared_ptr_spin_lock
0x1801a0404  test    rdi, rdi
0x1801a0407  jz      loc_1801A04AE
0x1801a040d  mov     r8, r13; struct PPID *
0x1801a0410  mov     edx, r12d; unsigned int
0x1801a0413  mov     rcx, rdi; this
0x1801a0416  call    ?SetCbdhsvcPpid@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJKAEBUPPID@@@Z; RealtimeProtection::DlpProcessCache::DlpProcessStateCache::SetCbdhsvcPpid(ulong,PPID const &)
0x1801a041b  mov     edi, eax
0x1801a041d  test    rbx, rbx
0x1801a0420  jz      short loc_1801A042A
0x1801a0422  mov     rcx, rbx; this
0x1801a0425  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a042a  test    edi, edi
0x1801a042c  js      loc_1801A04C0
0x1801a0432  mov     byte ptr [rsp+118h+var_D8], 0
0x1801a0437  xor     r14d, r14d
0x1801a043a  mov     dword ptr [rsp+118h+var_E0], r14d
0x1801a043f  mov     eax, [rsp+118h+arg_30]
0x1801a0446  mov     dword ptr [rsp+118h+var_E8], eax
0x1801a044a  mov     [rsp+118h+var_F0], r14b
0x1801a044f  mov     [rsp+118h+var_F8], r14b
0x1801a0454  mov     r9, [rsp+118h+var_B0]
0x1801a0459  mov     r8d, r12d
0x1801a045c  mov     rdx, [rsp+118h+lpFileTime1]
0x1801a0461  mov     rcx, r13
0x1801a0464  call    ?AddProcess@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@0KPEB_W_N2W4_MP_KNOWN_PROCESS_TYPE@@W4ProcessHierarchyPolicy@2@2@Z; RealtimeProtection::DlpProcessCache::AddProcess(PPID const &,PPID const &,ulong,wchar_t const *,bool,bool,_MP_KNOWN_PROCESS_TYPE,RealtimeProtection::ProcessHierarchyPolicy,bool)
0x1801a0469  mov     ebx, eax
0x1801a046b  test    eax, eax
0x1801a046d  jns     loc_1801A089A
0x1801a0473  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a047a  cmp     rcx, rsi
0x1801a047d  jz      short loc_1801A049E
0x1801a047f  test    byte ptr [rcx+1Ch], 1
0x1801a0483  jz      short loc_1801A049E
0x1801a0485  mov     edx, 231h
0x1801a048a  mov     r9d, eax
0x1801a048d  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x1801a0494  mov     rcx, [rcx+10h]
0x1801a0498  call    WPP_SF_d
0x1801a049d  nop
0x1801a049e  mov     rcx, r15; SRWLock
0x1801a04a1  call    cs:__imp_ReleaseSRWLockShared
0x1801a04a7  mov     eax, ebx
0x1801a04a9  jmp     loc_1801A0E6B
0x1801a04ae  test    rbx, rbx
0x1801a04b1  jz      short loc_1801A04BB
0x1801a04b3  mov     rcx, rbx; this
0x1801a04b6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a04bb  mov     edi, 8000000Eh
0x1801a04c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a04c7  cmp     rcx, rsi
0x1801a04ca  jz      short loc_1801A04EB
0x1801a04cc  test    byte ptr [rcx+1Ch], 1
0x1801a04d0  jz      short loc_1801A04EB
0x1801a04d2  mov     edx, 230h
0x1801a04d7  mov     r9d, edi
0x1801a04da  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x1801a04e1  mov     rcx, [rcx+10h]
0x1801a04e5  call    WPP_SF_d
0x1801a04ea  nop
0x1801a04eb  mov     rcx, r15; SRWLock
0x1801a04ee  call    cs:__imp_ReleaseSRWLockShared
0x1801a04f4  mov     eax, edi
0x1801a04f6  jmp     loc_1801A0E6B
0x1801a04fb  mov     ecx, 0DEh
0x1801a0500  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x1801a0505  mov     edx, eax; wchar_t *
0x1801a0507  mov     rcx, rdi; String1
0x1801a050a  call    ?IsAutoInjectionCandidate@DlpUtils@RealtimeProtection@@YA_NPEB_WI@Z; RealtimeProtection::DlpUtils::IsAutoInjectionCandidate(wchar_t const *,uint)
0x1801a050f  test    al, al
0x1801a0511  jz      loc_1801A05C6
0x1801a0517  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a051e  cmp     rcx, rsi
0x1801a0521  jz      short loc_1801A054C
0x1801a0523  test    byte ptr [rcx+1Ch], 4
0x1801a0527  jz      short loc_1801A054C
0x1801a0529  mov     edx, 232h
0x1801a052e  mov     [rsp+118h+var_E8], rbx; __int64
0x1801a0533  mov     dword ptr [rsp+118h+var_F0], r12d; char
0x1801a0538  mov     eax, [r13+8]
0x1801a053c  mov     dword ptr [rsp+118h+var_F8], eax; char
0x1801a0540  mov     r9, r14
0x1801a0543  mov     rcx, [rcx+10h]; LoggerHandle
0x1801a0547  call    WPP_SF_SLLS
0x1801a054c  mov     byte ptr [rsp+118h+var_D8], 0
0x1801a0551  xor     r14d, r14d
0x1801a0554  mov     dword ptr [rsp+118h+var_E0], r14d
0x1801a0559  mov     eax, [rsp+118h+arg_30]
0x1801a0560  mov     dword ptr [rsp+118h+var_E8], eax
0x1801a0564  mov     [rsp+118h+var_F0], r14b
0x1801a0569  mov     [rsp+118h+var_F8], 1
0x1801a056e  mov     r9, rdi
0x1801a0571  mov     r8d, r12d
0x1801a0574  mov     rdx, [rsp+118h+lpFileTime1]
0x1801a0579  mov     rcx, r13
0x1801a057c  call    ?AddProcess@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@0KPEB_W_N2W4_MP_KNOWN_PROCESS_TYPE@@W4ProcessHierarchyPolicy@2@2@Z; RealtimeProtection::DlpProcessCache::AddProcess(PPID const &,PPID const &,ulong,wchar_t const *,bool,bool,_MP_KNOWN_PROCESS_TYPE,RealtimeProtection::ProcessHierarchyPolicy,bool)
0x1801a0581  mov     ebx, eax
0x1801a0583  test    eax, eax
0x1801a0585  jns     loc_1801A089A
0x1801a058b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a0592  cmp     rcx, rsi
0x1801a0595  jz      short loc_1801A05B6
0x1801a0597  test    byte ptr [rcx+1Ch], 1
0x1801a059b  jz      short loc_1801A05B6
0x1801a059d  mov     edx, 233h
0x1801a05a2  mov     r9d, eax
0x1801a05a5  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x1801a05ac  mov     rcx, [rcx+10h]
0x1801a05b0  call    WPP_SF_d
0x1801a05b5  nop
0x1801a05b6  mov     rcx, r15; SRWLock
0x1801a05b9  call    cs:__imp_ReleaseSRWLockShared
0x1801a05bf  mov     eax, ebx
0x1801a05c1  jmp     loc_1801A0E6B
0x1801a05c6  test    rdi, rdi
0x1801a05c9  jz      loc_1801A0897
0x1801a05cf  lea     rdx, aAcrobatExe; "acrobat.exe"
0x1801a05d6  mov     rcx, rdi; String1
0x1801a05d9  call    _wcsicmp
0x1801a05de  test    eax, eax
0x1801a05e0  jnz     loc_1801A0695
0x1801a05e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a05ed  cmp     rcx, rsi
0x1801a05f0  jz      short loc_1801A061B
0x1801a05f2  test    byte ptr [rcx+1Ch], 4
0x1801a05f6  jz      short loc_1801A061B
0x1801a05f8  mov     edx, 234h
0x1801a05fd  mov     [rsp+118h+var_E8], rbx; __int64
0x1801a0602  mov     dword ptr [rsp+118h+var_F0], r12d; char
0x1801a0607  mov     eax, [r13+8]
0x1801a060b  mov     dword ptr [rsp+118h+var_F8], eax; char
0x1801a060f  mov     r9, r14
0x1801a0612  mov     rcx, [rcx+10h]; LoggerHandle
0x1801a0616  call    WPP_SF_SLLS
0x1801a061b  mov     byte ptr [rsp+118h+var_D8], 0
0x1801a0620  xor     r14d, r14d
0x1801a0623  mov     dword ptr [rsp+118h+var_E0], r14d
0x1801a0628  mov     eax, [rsp+118h+arg_30]
0x1801a062f  mov     dword ptr [rsp+118h+var_E8], eax
0x1801a0633  mov     [rsp+118h+var_F0], r14b
0x1801a0638  mov     [rsp+118h+var_F8], 1
0x1801a063d  mov     r9, rdi
0x1801a0640  mov     r8d, r12d
0x1801a0643  mov     rdx, [rsp+118h+lpFileTime1]
0x1801a0648  mov     rcx, r13
0x1801a064b  call    ?AddProcess@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@0KPEB_W_N2W4_MP_KNOWN_PROCESS_TYPE@@W4ProcessHierarchyPolicy@2@2@Z; RealtimeProtection::DlpProcessCache::AddProcess(PPID const &,PPID const &,ulong,wchar_t const *,bool,bool,_MP_KNOWN_PROCESS_TYPE,RealtimeProtection::ProcessHierarchyPolicy,bool)
0x1801a0650  mov     ebx, eax
0x1801a0652  test    eax, eax
0x1801a0654  jns     loc_1801A089A
0x1801a065a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a0661  cmp     rcx, rsi
0x1801a0664  jz      short loc_1801A0685
0x1801a0666  test    byte ptr [rcx+1Ch], 1
0x1801a066a  jz      short loc_1801A0685
0x1801a066c  mov     edx, 235h
0x1801a0671  mov     r9d, eax
0x1801a0674  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x1801a067b  mov     rcx, [rcx+10h]
0x1801a067f  call    WPP_SF_d
0x1801a0684  nop
0x1801a0685  mov     rcx, r15; SRWLock
0x1801a0688  call    cs:__imp_ReleaseSRWLockShared
0x1801a068e  mov     eax, ebx
0x1801a0690  jmp     loc_1801A0E6B
0x1801a0695  call    ?IsPluginInitialized@DlpPlugin@RealtimeProtection@@YAHXZ; RealtimeProtection::DlpPlugin::IsPluginInitialized(void)
0x1801a069a  xor     r14d, r14d
0x1801a069d  test    eax, eax
0x1801a069f  jz      loc_1801A089A
0x1801a06a5  mov     [rsp+118h+var_B8], r14
0x1801a06aa  lea     rcx, [rsp+118h+var_B8]; this
0x1801a06af  call    ?GetEngine@DlpPlugin@RealtimeProtection@@YAXPEAPEAVDlpCEngine@2@@Z; RealtimeProtection::DlpPlugin::GetEngine(RealtimeProtection::DlpCEngine * *)
0x1801a06b4  mov     rbx, [rsp+118h+var_B8]
0x1801a06b9  test    rbx, rbx
0x1801a06bc  jnz     short loc_1801A06F9
0x1801a06be  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a06c5  cmp     rcx, rsi
0x1801a06c8  jz      loc_1801A089A
0x1801a06ce  test    byte ptr [rcx+1Ch], 1
0x1801a06d2  jz      loc_1801A089A
0x1801a06d8  mov     edx, 28h ; '('
0x1801a06dd  lea     r9, aRealtimeprotec_11; "RealtimeProtection::DlpRtpPluginQuery::"...
0x1801a06e4  lea     r8, WPP_9bce63ce04f53a278728ac7dd0e232b4_Traceguids
0x1801a06eb  mov     rcx, [rcx+10h]
0x1801a06ef  call    WPP_SF_s
0x1801a06f4  jmp     loc_1801A089A
0x1801a06f9  xor     r12b, r12b
0x1801a06fc  mov     [rsp+118h+var_60], r14
0x1801a0704  mov     qword ptr [rsp+118h+FileTime1.dwLowDateTime], rdi
0x1801a070c  mov     r9d, 10h
0x1801a0712  lea     r8, [rsp+118h+FileTime1]
0x1801a071a  mov     edx, 40A7h
0x1801a071f  mov     rcx, [rbx+18h]
0x1801a0723  mov     rax, [rbx+10h]
0x1801a0727  call    cs:__guard_dispatch_icall_fptr
0x1801a072d  mov     edi, eax
0x1801a072f  test    eax, eax
0x1801a0731  jns     short loc_1801A0767
0x1801a0733  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a073a  cmp     rcx, rsi
0x1801a073d  jz      short loc_1801A0776
0x1801a073f  test    byte ptr [rcx+1Ch], 1
0x1801a0743  jz      short loc_1801A0776
0x1801a0745  mov     edx, 1Ah
0x1801a074a  mov     dword ptr [rsp+118h+var_F8], eax
0x1801a074e  lea     r9, aRealtimeprotec_7; "RealtimeProtection::DlpCEngine::DlpQuer"...
0x1801a0755  lea     r8, WPP_2f1a258b79b036cc8d24fffabf360af1_Traceguids
0x1801a075c  mov     rcx, [rcx+10h]
0x1801a0760  call    WPP_SF_sd
0x1801a0765  jmp     short loc_1801A0776
0x1801a0767  cmp     dword ptr [rsp+118h+var_60], 1
0x1801a076f  setz    r12b
0x1801a0773  mov     edi, r14d
0x1801a0776  test    edi, edi
0x1801a0778  js      loc_1801A086B
0x1801a077e  test    r12b, r12b
0x1801a0781  jz      loc_1801A086B
  ... truncated ...
```
