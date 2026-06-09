# RealtimeProtection::CRtpDlpEngine::Shutdown(void)

- ea: `0x1801a22bc`
- end: `0x1801a26dd`
- name: `?Shutdown@CRtpDlpEngine@RealtimeProtection@@QEAAXXZ`
- size: `1057`
- prototype: `void __fastcall(RealtimeProtection::CRtpDlpEngine *__hidden this)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180160194`

## callees

- `0x180028d80`
- `0x180079dc0`
- `0x180094e70`
- `0x18010b558`
- `0x18010b568`
- `0x18014f750`
- `0x18015463c`
- `0x1801639ac`
- `0x1801a22bc`
- `0x1801cc110`
- `0x1801d2748`
- `0x1801d77ac`
- `0x1801d8cd4`
- `0x1801d984c`
- `0x1801ecfe8`
- `0x1801ed05c`
- `0x1801ed0d0`
- `0x1801ed144`
- `0x1801ed1b8`
- `0x1801ed22c`
- `0x1801ed2a0`
- `0x1801f65e8`
- `0x1801fb998`
- `0x1801fba90`
- `0x1801fbe00`
- `0x1801fc204`
- `0x1802035d4`
- `0x1802077c4`
- `0x18020bf04`
- `0x18020ca8c`
- `0x180227b54`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1801a26bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1801a26bd`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1801a237d`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1801a237d`

## string_xrefs

- `0x1801a24fe`: `[DLP] Destroy DlpFileSourceDataCache instance`
- `0x1801a239b`: `[DLP] Destroy DLPBrowserCache instance`
- `0x1801a244f`: `[DLP] Destroy DlpPrinterCache instance`
- `0x1801a252d`: `[DLP] Destroy DlpUserSidCache instance`
- `0x1801a254f`: `[DLP] Destroy DlpClipboardStateCache instance`
- `0x1801a2586`: `[DLP] Destroy CPasteCacheDirectoryMonitor instance`
- `0x1801a25be`: `[DLP] Destroy DlpIpAddressCache instance`
- `0x1801a248c`: `[DLP] Destroy MpDlpUxSessionCacheT`
- `0x1801a23da`: `[DLP] Destroy DlpUserAgentManager instance`
- `0x1801a2412`: `[DLP] Destroy DlpUserConfigManager instance`

## pseudocode

```c
void __fastcall RealtimeProtection::CRtpDlpEngine::Shutdown(RealtimeProtection::CRtpDlpEngine *this)
{
  std::_Ref_count_base *v2; // rbx
  std::_Ref_count_base *v3; // rbx
  Dlp::Etw::Consumer *v4; // rcx
  Dlp::Etw::Controller *v5; // rcx
  __int64 v6; // rcx
  const wchar_t *v7; // rdx
  RealtimeProtection::DlpScheduleMaintainer *v8; // rcx
  MipDlp *v9; // rcx
  __int64 v10; // rcx
  void *v11; // rdx
  const wchar_t *v12; // rdx
  RealtimeProtection::DlpUserAgentManagement::DlpUserAgentManager *v13; // rsi
  std::_Ref_count_base *v14; // rbx
  const wchar_t *v15; // rdx
  std::_Ref_count_base *v16; // rbx
  const wchar_t *v17; // rdx
  Dlp::DeviceAttribute *v18; // rcx
  std::_Ref_count_base *v19; // rbx
  const wchar_t *v20; // rdx
  RealtimeProtection::DlpCloudConfig *v21; // rcx
  std::_Ref_count_base *v22; // rbx
  const wchar_t *v23; // rdx
  RealtimeProtection::DlpFileEvidence *v24; // rcx
  RealtimeProtection::DlpJitStateMachine *v25; // rcx
  __int64 v26; // rbx
  std::_Ref_count_base *v27; // r14
  std::_Ref_count_base *v28; // rsi
  const wchar_t *v29; // rdx
  RealtimeProtection::DlpProcessCache *v30; // rcx
  __int64 v31; // rcx
  const wchar_t *v32; // rdx
  RealtimeProtection::DlpPathCache *v33; // rcx
  __int64 v34; // rcx
  const wchar_t *v35; // rdx
  __int64 v36; // rbx
  std::_Ref_count_base *v37; // rsi
  const wchar_t *v38; // rdx
  std::_Ref_count_base *v39; // rbx
  const wchar_t *v40; // rdx
  __int64 v41; // rcx
  const wchar_t *v42; // rdx
  __int64 v43; // rcx
  const wchar_t *v44; // rdx
  __int64 v45; // rcx
  const wchar_t *v46; // rdx
  __int64 v47; // rcx
  const wchar_t *v48; // rdx
  __int64 v49; // rcx
  const wchar_t *v50; // rdx
  __int64 v51; // rcx
  const wchar_t *v52; // rdx
  __int64 v53; // rcx
  const wchar_t *v54; // rdx
  RealtimeProtection::DlpTelemetry *v55; // rcx
  __int128 v56; // [rsp+20h] [rbp-20h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+30h] [rbp-10h] BYREF

  Lock_shared_ptr_spin_lock();
  qword_180314678 = 0;
  v2 = qword_180314680;
  qword_180314680 = 0;
  Unlock_shared_ptr_spin_lock();
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Lock_shared_ptr_spin_lock();
  qword_1803144D0 = 0;
  v3 = qword_1803144D8;
  qword_1803144D8 = 0;
  Unlock_shared_ptr_spin_lock();
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  Dlp::Etw::Consumer::DestroyInstance(v4);
  Dlp::Etw::_anonymous_namespace_::DlpEtwTelemetry::Send();
  Dlp::Etw::Controller::StopTraceSession(v5);
  *(_OWORD *)SRWLock = 0;
  std::atomic_store_Dlp::Etw::Controller::_anonymous_namespace_::DlpEtwController_(v6, SRWLock);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy DlpEtwController instance", v7);
  RealtimeProtection::DlpScheduleMaintainer::DestroyConfigMaintainer(v8);
  MipDlp::DestroyInstance(v9);
  v11 = (void *)*((_QWORD *)this + 22);
  if ( v11 )
  {
    DeleteTimerQueueTimer(0, v11, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 22) = 0;
  }
  *(_OWORD *)SRWLock = 0;
  std::atomic_store<Dlp::BrowserCache::DLPBrowserCache>(v10, SRWLock);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy DLPBrowserCache instance", v12);
  Lock_shared_ptr_spin_lock();
  v13 = qword_1803145A8;
  qword_1803145A8 = 0;
  v14 = qword_1803145B0;
  qword_1803145B0 = 0;
  Unlock_shared_ptr_spin_lock();
  if ( v13 )
    RealtimeProtection::DlpUserAgentManagement::DlpUserAgentManager::RemoveAllAgents(v13);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy DlpUserAgentManager instance", v15);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  Lock_shared_ptr_spin_lock();
  qword_1803145B8 = 0;
  v16 = qword_1803145C0;
  qword_1803145C0 = 0;
  Unlock_shared_ptr_spin_lock();
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy DlpUserConfigManager instance", v17);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  Dlp::DeviceAttribute::DestroyInstance(v18);
  Lock_shared_ptr_spin_lock();
  qword_180313BE8 = 0;
  v19 = qword_180313BF0;
  qword_180313BF0 = 0;
  Unlock_shared_ptr_spin_lock();
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy DlpPrinterCache instance", v20);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  RealtimeProtection::DlpCloudConfig::DestroyInstance(v21);
  Lock_shared_ptr_spin_lock();
  qword_180314598 = 0;
  v22 = qword_1803145A0;
  qword_1803145A0 = 0;
  Unlock_shared_ptr_spin_lock();
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy MpDlpUxSessionCacheT", v23);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(
    SRWLock,
    (char *)this + 16);
  *((_BYTE *)this + 69) = 1;
  RealtimeProtection::DlpFileEvidence::DestroyInstance(v24);
  RealtimeProtection::DlpJitStateMachine::DestroyInstance(v25);
  Lock_shared_ptr_spin_lock();
  v26 = qword_1803139A8;
  qword_1803139A8 = 0;
  v27 = qword_1803139B0;
  qword_1803139B0 = 0;
  v28 = v27;
  Unlock_shared_ptr_spin_lock();
  if ( v26 )
  {
    v28 = 0;
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
  }
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy DlpFileSourceDataCache instance", v29);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  RealtimeProtection::DlpProcessCache::DestroyInstance(v30);
  v56 = 0;
  std::atomic_store__anonymous_namespace_::UserSidCache_(v31, &v56);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy DlpUserSidCache instance", v32);
  RealtimeProtection::DlpPathCache::DestroyInstance(v33);
  v56 = 0;
  std::atomic_store__anonymous_namespace_::ClipboardStateCache_(v34, &v56);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy DlpClipboardStateCache instance", v35);
  Lock_shared_ptr_spin_lock();
  v36 = qword_1803144B0;
  qword_1803144B0 = 0;
  v37 = qword_1803144B8;
  qword_1803144B8 = 0;
  Unlock_shared_ptr_spin_lock();
  if ( v36 )
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"[DLP] Destroy CPasteCacheDirectoryMonitor instance",
      v38);
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
  Lock_shared_ptr_spin_lock();
  qword_1803144C0 = 0;
  v39 = qword_1803144C8;
  qword_1803144C8 = 0;
  Unlock_shared_ptr_spin_lock();
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy DlpIpAddressCache instance", v40);
  if ( v39 )
    std::_Ref_count_base::_Decref(v39);
  v56 = 0;
  std::atomic_store<RealtimeProtection::DlpThrottle::DlpClipboardEventsThrottlingInstance>(v41, &v56);
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"[DLP] Destroy DlpClipboardEventsThrottling instance",
    v42);
  v56 = 0;
  std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleEvent>>(
    v43,
    &v56);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy g_DlpGenericThrottling instance", v44);
  v56 = 0;
  std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleCloudEgressEvent>>(
    v45,
    &v56);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy g_DlpCloudEgressThrottling instance", v46);
  v56 = 0;
  std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent>>(
    v47,
    &v56);
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"[DLP] Destroy g_DlpUnallowedAppsThrottling instance",
    v48);
  v56 = 0;
  std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleRecallEvent>>(
    v49,
    &v56);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy g_DlpRecallThrottling instance", v50);
  v56 = 0;
  std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent>>(
    v51,
    &v56);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy g_DlpAnyAppThrottling instance", v52);
  v56 = 0;
  std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleCloudSyncEvent>>(
    v53,
    &v56);
  RealtimeProtection::MpLogMessageImpl((RealtimeProtection *)L"[DLP] Destroy g_DlpCloudSyncThrottling instance", v54);
  RealtimeProtection::DlpTelemetry::DestroyInstance(v55);
  UnloadWinRTDlls();
  *((_DWORD *)this + 2) = 3;
  if ( LOBYTE(SRWLock[1]) )
    ReleaseSRWLockExclusive(SRWLock[0]);
}

```

## disassembly

```asm
0x1801a22bc  mov     [rsp-18h+arg_8], rbx
0x1801a22c1  mov     [rsp-18h+arg_10], rsi
0x1801a22c6  mov     [rsp-18h+arg_18], rdi
0x1801a22cb  push    rbp
0x1801a22cc  push    r14
0x1801a22ce  push    r15
0x1801a22d0  mov     rbp, rsp
0x1801a22d3  sub     rsp, 40h
0x1801a22d7  mov     rdi, rcx
0x1801a22da  call    _Lock_shared_ptr_spin_lock
0x1801a22df  xor     r15d, r15d
0x1801a22e2  mov     cs:qword_180314678, r15
0x1801a22e9  mov     rbx, cs:qword_180314680
0x1801a22f0  mov     cs:qword_180314680, r15
0x1801a22f7  call    _Unlock_shared_ptr_spin_lock
0x1801a22fc  test    rbx, rbx
0x1801a22ff  jz      short loc_1801A2309
0x1801a2301  mov     rcx, rbx; this
0x1801a2304  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a2309  call    _Lock_shared_ptr_spin_lock
0x1801a230e  mov     cs:qword_1803144D0, r15
0x1801a2315  mov     rbx, cs:qword_1803144D8
0x1801a231c  mov     cs:qword_1803144D8, r15
0x1801a2323  call    _Unlock_shared_ptr_spin_lock
0x1801a2328  test    rbx, rbx
0x1801a232b  jz      short loc_1801A2335
0x1801a232d  mov     rcx, rbx; this
0x1801a2330  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a2335  call    ?DestroyInstance@Consumer@Etw@Dlp@@YAJXZ; Dlp::Etw::Consumer::DestroyInstance(void)
0x1801a233a  call    Dlp__Etw___anonymous_namespace___DlpEtwTelemetry__Send
0x1801a233f  call    ?StopTraceSession@Controller@Etw@Dlp@@YAJXZ; Dlp::Etw::Controller::StopTraceSession(void)
0x1801a2344  xorps   xmm0, xmm0
0x1801a2347  movdqu  xmmword ptr [rbp+SRWLock], xmm0
0x1801a234c  lea     rdx, [rbp+SRWLock]
0x1801a2350  call    std__atomic_store_Dlp__Etw__Controller___anonymous_namespace___DlpEtwController_
0x1801a2355  lea     rcx, aDlpDestroyDlpe; "[DLP] Destroy DlpEtwController instance"
0x1801a235c  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a2361  call    ?DestroyConfigMaintainer@DlpScheduleMaintainer@RealtimeProtection@@YAJXZ; RealtimeProtection::DlpScheduleMaintainer::DestroyConfigMaintainer(void)
0x1801a2366  call    ?DestroyInstance@MipDlp@@YAJXZ; MipDlp::DestroyInstance(void)
0x1801a236b  mov     rdx, [rdi+0B0h]; Timer
0x1801a2372  test    rdx, rdx
0x1801a2375  jz      short loc_1801A238A
0x1801a2377  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1801a237b  xor     ecx, ecx; TimerQueue
0x1801a237d  call    cs:__imp_DeleteTimerQueueTimer
0x1801a2383  mov     [rdi+0B0h], r15
0x1801a238a  xorps   xmm0, xmm0
0x1801a238d  movdqu  xmmword ptr [rbp+SRWLock], xmm0
0x1801a2392  lea     rdx, [rbp+SRWLock]
0x1801a2396  call    ??$atomic_store@VDLPBrowserCache@BrowserCache@Dlp@@@std@@YAXPEAV?$shared_ptr@VDLPBrowserCache@BrowserCache@Dlp@@@0@V10@@Z; std::atomic_store<Dlp::BrowserCache::DLPBrowserCache>(std::shared_ptr<Dlp::BrowserCache::DLPBrowserCache> *,std::shared_ptr<Dlp::BrowserCache::DLPBrowserCache>)
0x1801a239b  lea     rcx, aDlpDestroyDlpb; "[DLP] Destroy DLPBrowserCache instance"
0x1801a23a2  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a23a7  call    _Lock_shared_ptr_spin_lock
0x1801a23ac  mov     rsi, cs:qword_1803145A8
0x1801a23b3  mov     cs:qword_1803145A8, r15
0x1801a23ba  mov     rbx, cs:qword_1803145B0
0x1801a23c1  mov     cs:qword_1803145B0, r15
0x1801a23c8  call    _Unlock_shared_ptr_spin_lock
0x1801a23cd  test    rsi, rsi
0x1801a23d0  jz      short loc_1801A23DA
0x1801a23d2  mov     rcx, rsi; this
0x1801a23d5  call    ?RemoveAllAgents@DlpUserAgentManager@DlpUserAgentManagement@RealtimeProtection@@QEAAXXZ; RealtimeProtection::DlpUserAgentManagement::DlpUserAgentManager::RemoveAllAgents(void)
0x1801a23da  lea     rcx, aDlpDestroyDlpu_0; "[DLP] Destroy DlpUserAgentManager insta"...
0x1801a23e1  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a23e6  test    rbx, rbx
0x1801a23e9  jz      short loc_1801A23F3
0x1801a23eb  mov     rcx, rbx; this
0x1801a23ee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a23f3  call    _Lock_shared_ptr_spin_lock
0x1801a23f8  mov     cs:qword_1803145B8, r15
0x1801a23ff  mov     rbx, cs:qword_1803145C0
0x1801a2406  mov     cs:qword_1803145C0, r15
0x1801a240d  call    _Unlock_shared_ptr_spin_lock
0x1801a2412  lea     rcx, aDlpDestroyDlpu; "[DLP] Destroy DlpUserConfigManager inst"...
0x1801a2419  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a241e  test    rbx, rbx
0x1801a2421  jz      short loc_1801A242B
0x1801a2423  mov     rcx, rbx; this
0x1801a2426  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a242b  call    ?DestroyInstance@DeviceAttribute@Dlp@@YAJXZ; Dlp::DeviceAttribute::DestroyInstance(void)
0x1801a2430  call    _Lock_shared_ptr_spin_lock
0x1801a2435  mov     cs:qword_180313BE8, r15
0x1801a243c  mov     rbx, cs:qword_180313BF0
0x1801a2443  mov     cs:qword_180313BF0, r15
0x1801a244a  call    _Unlock_shared_ptr_spin_lock
0x1801a244f  lea     rcx, aDlpDestroyDlpp_0; "[DLP] Destroy DlpPrinterCache instance"
0x1801a2456  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a245b  test    rbx, rbx
0x1801a245e  jz      short loc_1801A2468
0x1801a2460  mov     rcx, rbx; this
0x1801a2463  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a2468  call    ?DestroyInstance@DlpCloudConfig@RealtimeProtection@@YAJXZ; RealtimeProtection::DlpCloudConfig::DestroyInstance(void)
0x1801a246d  call    _Lock_shared_ptr_spin_lock
0x1801a2472  mov     cs:qword_180314598, r15
0x1801a2479  mov     rbx, cs:qword_1803145A0
0x1801a2480  mov     cs:qword_1803145A0, r15
0x1801a2487  call    _Unlock_shared_ptr_spin_lock
0x1801a248c  lea     rcx, aDlpDestroyMpdl_0; "[DLP] Destroy MpDlpUxSessionCacheT"
0x1801a2493  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a2498  test    rbx, rbx
0x1801a249b  jz      short loc_1801A24A5
0x1801a249d  mov     rcx, rbx; this
0x1801a24a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a24a5  lea     rdx, [rdi+10h]
0x1801a24a9  lea     rcx, [rbp+SRWLock]
0x1801a24ad  call    ??0?$CGenericAutoLock@U?$CMpWriteLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@AEAVCMpSRWLock@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(CommonUtil::CMpSRWLock &,CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::ENUM_LOCK_INITIAL_STATE)
0x1801a24b2  mov     byte ptr [rdi+45h], 1
0x1801a24b6  call    ?DestroyInstance@DlpFileEvidence@RealtimeProtection@@YAJXZ; RealtimeProtection::DlpFileEvidence::DestroyInstance(void)
0x1801a24bb  call    ?DestroyInstance@DlpJitStateMachine@RealtimeProtection@@YAJXZ; RealtimeProtection::DlpJitStateMachine::DestroyInstance(void)
0x1801a24c0  call    _Lock_shared_ptr_spin_lock
0x1801a24c5  mov     rbx, cs:qword_1803139A8
0x1801a24cc  mov     cs:qword_1803139A8, r15
0x1801a24d3  mov     r14, cs:qword_1803139B0
0x1801a24da  mov     cs:qword_1803139B0, r15
0x1801a24e1  mov     rsi, r14
0x1801a24e4  call    _Unlock_shared_ptr_spin_lock
0x1801a24e9  test    rbx, rbx
0x1801a24ec  jz      short loc_1801A24FE
0x1801a24ee  mov     rsi, r15
0x1801a24f1  test    r14, r14
0x1801a24f4  jz      short loc_1801A24FE
0x1801a24f6  mov     rcx, r14; this
0x1801a24f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a24fe  lea     rcx, aDlpDestroyDlpf; "[DLP] Destroy DlpFileSourceDataCache in"...
0x1801a2505  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a250a  test    rsi, rsi
0x1801a250d  jz      short loc_1801A2517
0x1801a250f  mov     rcx, rsi; this
0x1801a2512  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a2517  call    ?DestroyInstance@DlpProcessCache@RealtimeProtection@@YAJXZ; RealtimeProtection::DlpProcessCache::DestroyInstance(void)
0x1801a251c  xorps   xmm0, xmm0
0x1801a251f  movdqu  [rbp+var_20], xmm0
0x1801a2524  lea     rdx, [rbp+var_20]
0x1801a2528  call    std__atomic_store__anonymous_namespace___UserSidCache_
0x1801a252d  lea     rcx, aDlpDestroyDlpu_1; "[DLP] Destroy DlpUserSidCache instance"
0x1801a2534  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a2539  call    ?DestroyInstance@DlpPathCache@RealtimeProtection@@YAJXZ; RealtimeProtection::DlpPathCache::DestroyInstance(void)
0x1801a253e  xorps   xmm0, xmm0
0x1801a2541  movdqu  [rbp+var_20], xmm0
0x1801a2546  lea     rdx, [rbp+var_20]
0x1801a254a  call    std__atomic_store__anonymous_namespace___ClipboardStateCache_
0x1801a254f  lea     rcx, aDlpDestroyDlpc; "[DLP] Destroy DlpClipboardStateCache in"...
0x1801a2556  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a255b  call    _Lock_shared_ptr_spin_lock
0x1801a2560  mov     rbx, cs:qword_1803144B0
0x1801a2567  mov     cs:qword_1803144B0, r15
0x1801a256e  mov     rsi, cs:qword_1803144B8
0x1801a2575  mov     cs:qword_1803144B8, r15
0x1801a257c  call    _Unlock_shared_ptr_spin_lock
0x1801a2581  test    rbx, rbx
0x1801a2584  jz      short loc_1801A2592
0x1801a2586  lea     rcx, aDlpDestroyCpas; "[DLP] Destroy CPasteCacheDirectoryMonit"...
0x1801a258d  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a2592  test    rsi, rsi
0x1801a2595  jz      short loc_1801A259F
0x1801a2597  mov     rcx, rsi; this
0x1801a259a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a259f  call    _Lock_shared_ptr_spin_lock
0x1801a25a4  mov     cs:qword_1803144C0, r15
0x1801a25ab  mov     rbx, cs:qword_1803144C8
0x1801a25b2  mov     cs:qword_1803144C8, r15
0x1801a25b9  call    _Unlock_shared_ptr_spin_lock
0x1801a25be  lea     rcx, aDlpDestroyDlpi; "[DLP] Destroy DlpIpAddressCache instanc"...
0x1801a25c5  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a25ca  test    rbx, rbx
0x1801a25cd  jz      short loc_1801A25D7
0x1801a25cf  mov     rcx, rbx; this
0x1801a25d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a25d7  xorps   xmm0, xmm0
0x1801a25da  movdqu  [rbp+var_20], xmm0
0x1801a25df  lea     rdx, [rbp+var_20]
0x1801a25e3  call    ??$atomic_store@VDlpClipboardEventsThrottlingInstance@DlpThrottle@RealtimeProtection@@@std@@YAXPEAV?$shared_ptr@VDlpClipboardEventsThrottlingInstance@DlpThrottle@RealtimeProtection@@@0@V10@@Z; std::atomic_store<RealtimeProtection::DlpThrottle::DlpClipboardEventsThrottlingInstance>(std::shared_ptr<RealtimeProtection::DlpThrottle::DlpClipboardEventsThrottlingInstance> *,std::shared_ptr<RealtimeProtection::DlpThrottle::DlpClipboardEventsThrottlingInstance>)
0x1801a25e8  lea     rcx, aDlpDestroyDlpc_0; "[DLP] Destroy DlpClipboardEventsThrottl"...
0x1801a25ef  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a25f4  xorps   xmm0, xmm0
0x1801a25f7  movdqu  [rbp+var_20], xmm0
0x1801a25fc  lea     rdx, [rbp+var_20]
0x1801a2600  call    ??$atomic_store@V?$DlpThrottleTemplate@UDlpThrottleEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@std@@YAXPEAV?$shared_ptr@V?$DlpThrottleTemplate@UDlpThrottleEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@0@V10@@Z; std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleEvent>>(std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleEvent>> *,std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleEvent>>)
0x1801a2605  lea     rcx, aDlpDestroyGDlp_1; "[DLP] Destroy g_DlpGenericThrottling in"...
0x1801a260c  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a2611  xorps   xmm0, xmm0
0x1801a2614  movdqu  [rbp+var_20], xmm0
0x1801a2619  lea     rdx, [rbp+var_20]
0x1801a261d  call    ??$atomic_store@V?$DlpThrottleTemplate@UDlpThrottleCloudEgressEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@std@@YAXPEAV?$shared_ptr@V?$DlpThrottleTemplate@UDlpThrottleCloudEgressEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@0@V10@@Z; std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleCloudEgressEvent>>(std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleCloudEgressEvent>> *,std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleCloudEgressEvent>>)
0x1801a2622  lea     rcx, aDlpDestroyGDlp; "[DLP] Destroy g_DlpCloudEgressThrottlin"...
0x1801a2629  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a262e  xorps   xmm0, xmm0
0x1801a2631  movdqu  [rbp+var_20], xmm0
0x1801a2636  lea     rdx, [rbp+var_20]
0x1801a263a  call    ??$atomic_store@V?$DlpThrottleTemplate@UDlpThrottleUnallowedAppsEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@std@@YAXPEAV?$shared_ptr@V?$DlpThrottleTemplate@UDlpThrottleUnallowedAppsEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@0@V10@@Z; std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent>>(std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent>> *,std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent>>)
0x1801a263f  lea     rcx, aDlpDestroyGDlp_2; "[DLP] Destroy g_DlpUnallowedAppsThrottl"...
0x1801a2646  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a264b  xorps   xmm0, xmm0
0x1801a264e  movdqu  [rbp+var_20], xmm0
0x1801a2653  lea     rdx, [rbp+var_20]
0x1801a2657  call    ??$atomic_store@V?$DlpThrottleTemplate@UDlpThrottleRecallEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@std@@YAXPEAV?$shared_ptr@V?$DlpThrottleTemplate@UDlpThrottleRecallEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@0@V10@@Z; std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleRecallEvent>>(std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleRecallEvent>> *,std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleRecallEvent>>)
0x1801a265c  lea     rcx, aDlpDestroyGDlp_0; "[DLP] Destroy g_DlpRecallThrottling ins"...
0x1801a2663  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a2668  xorps   xmm0, xmm0
0x1801a266b  movdqu  [rbp+var_20], xmm0
0x1801a2670  lea     rdx, [rbp+var_20]
0x1801a2674  call    ??$atomic_store@V?$DlpThrottleTemplate@UDlpThrottleAnyAppEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@std@@YAXPEAV?$shared_ptr@V?$DlpThrottleTemplate@UDlpThrottleAnyAppEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@0@V10@@Z; std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent>>(std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent>> *,std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleAnyAppEvent>>)
0x1801a2679  lea     rcx, aDlpDestroyGDlp_4; "[DLP] Destroy g_DlpAnyAppThrottling ins"...
0x1801a2680  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a2685  xorps   xmm0, xmm0
0x1801a2688  movdqu  [rbp+var_20], xmm0
0x1801a268d  lea     rdx, [rbp+var_20]
0x1801a2691  call    ??$atomic_store@V?$DlpThrottleTemplate@UDlpThrottleCloudSyncEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@std@@YAXPEAV?$shared_ptr@V?$DlpThrottleTemplate@UDlpThrottleCloudSyncEvent@DlpThrottle@RealtimeProtection@@@DlpThrottle@RealtimeProtection@@@0@V10@@Z; std::atomic_store<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleCloudSyncEvent>>(std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleCloudSyncEvent>> *,std::shared_ptr<RealtimeProtection::DlpThrottle::DlpThrottleTemplate<RealtimeProtection::DlpThrottle::DlpThrottleCloudSyncEvent>>)
0x1801a2696  lea     rcx, aDlpDestroyGDlp_3; "[DLP] Destroy g_DlpCloudSyncThrottling "...
0x1801a269d  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x1801a26a2  call    ?DestroyInstance@DlpTelemetry@RealtimeProtection@@YAJXZ; RealtimeProtection::DlpTelemetry::DestroyInstance(void)
0x1801a26a7  call    ?UnloadWinRTDlls@@YAXXZ; UnloadWinRTDlls(void)
0x1801a26ac  mov     dword ptr [rdi+8], 3
0x1801a26b3  cmp     byte ptr [rbp+SRWLock+8], r15b
0x1801a26b7  jz      short loc_1801A26C4
0x1801a26b9  mov     rcx, [rbp+SRWLock]; SRWLock
0x1801a26bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1801a26c3  nop
0x1801a26c4  mov     rbx, [rsp+40h+arg_8]
0x1801a26c9  mov     rsi, [rsp+40h+arg_10]
0x1801a26ce  mov     rdi, [rsp+40h+arg_18]
0x1801a26d3  add     rsp, 40h
0x1801a26d7  pop     r15
0x1801a26d9  pop     r14
0x1801a26db  pop     rbp
0x1801a26dc  retn
```
