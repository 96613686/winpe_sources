# FwGPMonGPUpdate(void *,uchar)

- ea: `0x180093470`
- end: `0x180093743`
- name: `?FwGPMonGPUpdate@@YAXPEAXE@Z`
- size: `723`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008618`
- `0x180009720`
- `0x18000af3c`
- `0x180017110`
- `0x180049d98`
- `0x180053edc`
- `0x1800666d0`
- `0x180066704`
- `0x18006b84c`
- `0x18006c438`
- `0x18007aca4`
- `0x18008a20c`
- `0x18008c954`
- `0x18008dd20`
- `0x18008fba0`
- `0x18008fc50`
- `0x180093470`
- `0x1800a4ba8`
- `0x1800b4cb0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18009362d`
- `ntdll!EtwEventWrite` at `0x180093653`
- `ntdll!EtwEventWrite` at `0x18009362d`
- `ntdll!EtwEventWrite` at `0x180093653`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093542`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800936ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093542`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800936ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800934fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009372a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800934fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009372a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800935f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800935f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800936ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800936ec`

## string_xrefs

- `0x18009354b`: `FwGPMonGPUpdate`
- `0x1800935dc`: `FwGPMonGPUpdate`
- `0x1800936f2`: `FwGPMonGPUpdate`
- `0x1800936c9`: `GpPolicyUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FwGPMonGPUpdate(void *a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  __int64 v2; // rax
  int TickCount64; // esi
  int v4; // eax
  __int64 v5; // r9
  int updated; // edi
  int v7; // eax
  LPCRITICAL_SECTION lpCriticalSection[5]; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+70h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+78h] [rbp+20h] BYREF

  v9 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_18c1d7ad682534e2dcda8ef6e9929c06_Traceguids);
  v1 = 0;
  v10 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
  {
    v2 = CallbackGate::TryEnterQueue(&g_FwGPMonGPUpdateGate, lpCriticalSection);
    CallbackGate::QueueState::operator=(&v10, v2);
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
    v1 = v10;
    if ( !v10 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)((_DWORD)v10 + 15),
          WPP_18c1d7ad682534e2dcda8ef6e9929c06_Traceguids);
      return;
    }
    ++g_CallbackGateCountGPUpdate;
  }
  TickCount64 = GetTickCount64();
  v4 = FwAcquireRPCSharedLock("FwGPMonGPUpdate");
  if ( v4 >= 0 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
    {
      if ( _InterlockedCompareExchange(&g_IsThreadWaiting, 1, 0) )
      {
        v5 = (unsigned int)_InterlockedIncrement(&g_ThreadsReturnedCount);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_18c1d7ad682534e2dcda8ef6e9929c06_Traceguids, v5);
        FwReleaseRPCSharedLock("FwGPMonGPUpdate");
        goto LABEL_36;
      }
      AcquireSRWLockExclusive(&g_FwGPMonGPUpdateLock);
      ++g_CallbackGateCountGPUpdate_old;
      _InterlockedCompareExchange(&g_IsThreadWaiting, 0, 1);
    }
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_SVC_GP_Policy_Begin, 0, 0);
    updated = FwProfileMgrOnUpdatePolicyControl();
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_SVC_GP_Policy_End, 0, 0);
    if ( updated < 0 )
    {
      FwEventGroupPolicyFailure((unsigned int)updated);
    }
    else
    {
      FwAuditLogGroupPolicyChanged();
      FwLogEvent(&WFGroupPolicySuccessEvent, 0, 0);
    }
    appIsolation::AppContainerDatabase::LoadDaGPConfigHint(gFwIsolationManager);
    FwEdpOnGroupPolicyChangePhase1(&v9);
    FwAdhSnSGroupPolicyUpdate();
    FwHttpProxyGroupPolicyUpdate();
    FwEdpOnGroupPolicyChangePhase2(&v9);
    FwTenantRestrictionsPolicyUpdate();
    v7 = GetTickCount64();
    FwTelemetryEventWriteDataUpdate((unsigned int)L"GpPolicyUpdate", 0, v9, v7 - TickCount64, (__int64)L"NULL");
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
      ReleaseSRWLockExclusive(&g_FwGPMonGPUpdateLock);
    FwReleaseRPCSharedLock("FwGPMonGPUpdate");
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_18c1d7ad682534e2dcda8ef6e9929c06_Traceguids);
    goto LABEL_36;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      16,
      WPP_18c1d7ad682534e2dcda8ef6e9929c06_Traceguids,
      (unsigned int)v4);
LABEL_36:
  if ( v1 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180093470  mov     [rsp+arg_0], rbx
0x180093475  mov     [rsp+arg_8], rbp
0x18009347a  push    rsi
0x18009347b  push    rdi
0x18009347c  push    r14
0x18009347e  sub     rsp, 40h
0x180093482  mov     [rsp+58h+arg_10], 0
0x18009348a  lea     rbp, WPP_GLOBAL_Control
0x180093491  lea     r14, WPP_18c1d7ad682534e2dcda8ef6e9929c06_Traceguids
0x180093498  mov     rcx, cs:WPP_GLOBAL_Control
0x18009349f  cmp     rcx, rbp
0x1800934a2  jz      short loc_1800934BB
0x1800934a4  test    byte ptr [rcx+1Ch], 8
0x1800934a8  jz      short loc_1800934BB
0x1800934aa  mov     edx, 0Eh
0x1800934af  mov     r8, r14
0x1800934b2  mov     rcx, [rcx+10h]
0x1800934b6  call    WPP_SF_
0x1800934bb  xor     ebx, ebx
0x1800934bd  mov     [rsp+58h+arg_18], rbx
0x1800934c2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x1800934c9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x1800934ce  lea     edi, [rbx+1]
0x1800934d1  test    al, al
0x1800934d3  jz      short loc_180093542
0x1800934d5  lea     rdx, [rsp+58h+lpCriticalSection]
0x1800934da  lea     rcx, ?g_FwGPMonGPUpdateGate@@3VCallbackGate@@A; CallbackGate g_FwGPMonGPUpdateGate
0x1800934e1  call    ?TryEnterQueue@CallbackGate@@QEAA?AVQueueState@1@XZ; CallbackGate::TryEnterQueue(void)
0x1800934e6  mov     rdx, rax
0x1800934e9  lea     rcx, [rsp+58h+arg_18]
0x1800934ee  call    ??4QueueState@CallbackGate@@QEAAAEAV01@$$QEAV01@@Z; CallbackGate::QueueState::operator=(CallbackGate::QueueState &&)
0x1800934f3  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800934f8  test    rcx, rcx
0x1800934fb  jz      short loc_180093503
0x1800934fd  call    cs:__imp_LeaveCriticalSection
0x180093503  mov     rbx, [rsp+58h+arg_18]
0x180093508  test    rbx, rbx
0x18009350b  jnz     short loc_180093534
0x18009350d  mov     rcx, cs:WPP_GLOBAL_Control
0x180093514  cmp     rcx, rbp
0x180093517  jz      short loc_18009352F
0x180093519  test    byte ptr [rcx+1Ch], 4
0x18009351d  jz      short loc_18009352F
0x18009351f  lea     edx, [rbx+0Fh]
0x180093522  mov     r8, r14
0x180093525  mov     rcx, [rcx+10h]
0x180093529  call    WPP_SF_
0x18009352e  nop
0x18009352f  jmp     loc_180093730
0x180093534  mov     eax, cs:?g_CallbackGateCountGPUpdate@@3KC; ulong volatile g_CallbackGateCountGPUpdate
0x18009353a  add     eax, edi
0x18009353c  mov     cs:?g_CallbackGateCountGPUpdate@@3KC, eax; ulong volatile g_CallbackGateCountGPUpdate
0x180093542  call    cs:__imp_GetTickCount64
0x180093548  mov     rsi, rax
0x18009354b  lea     rcx, aFwgpmongpupdat; "FwGPMonGPUpdate"
0x180093552  call    FwAcquireRPCSharedLock
0x180093557  test    eax, eax
0x180093559  jns     short loc_18009358E
0x18009355b  mov     rcx, cs:WPP_GLOBAL_Control
0x180093562  cmp     rcx, rbp
0x180093565  jz      loc_180093722
0x18009356b  test    [rcx+1Ch], dil
0x18009356f  jz      loc_180093722
0x180093575  mov     edx, 10h
0x18009357a  mov     r9d, eax
0x18009357d  mov     r8, r14
0x180093580  mov     rcx, [rcx+10h]
0x180093584  call    WPP_SF_d
0x180093589  jmp     loc_180093722
0x18009358e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x180093595  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x18009359a  test    al, al
0x18009359c  jnz     short loc_180093614
0x18009359e  xor     eax, eax
0x1800935a0  lock cmpxchg cs:?g_IsThreadWaiting@@3HC, edi; int volatile g_IsThreadWaiting
0x1800935a8  jz      short loc_1800935ED
0x1800935aa  mov     r9d, edi
0x1800935ad  lock xadd cs:?g_ThreadsReturnedCount@@3JC, r9d; long volatile g_ThreadsReturnedCount
0x1800935b6  add     r9d, edi
0x1800935b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800935c0  cmp     rcx, rbp
0x1800935c3  jz      short loc_1800935DC
0x1800935c5  test    byte ptr [rcx+1Ch], 4
0x1800935c9  jz      short loc_1800935DC
0x1800935cb  mov     edx, 11h
0x1800935d0  mov     r8, r14
0x1800935d3  mov     rcx, [rcx+10h]
0x1800935d7  call    WPP_SF_d
0x1800935dc  lea     rcx, aFwgpmongpupdat; "FwGPMonGPUpdate"
0x1800935e3  call    FwReleaseRPCSharedLock
0x1800935e8  jmp     loc_180093722
0x1800935ed  lea     rcx, ?g_FwGPMonGPUpdateLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800935f4  call    cs:__imp_AcquireSRWLockExclusive
0x1800935fa  mov     ecx, cs:?g_CallbackGateCountGPUpdate_old@@3KC; ulong volatile g_CallbackGateCountGPUpdate_old
0x180093600  add     ecx, edi
0x180093602  mov     cs:?g_CallbackGateCountGPUpdate_old@@3KC, ecx; ulong volatile g_CallbackGateCountGPUpdate_old
0x180093608  xor     ecx, ecx
0x18009360a  mov     eax, edi
0x18009360c  lock cmpxchg cs:?g_IsThreadWaiting@@3HC, ecx; int volatile g_IsThreadWaiting
0x180093614  mov     rcx, cs:g_Provider
0x18009361b  test    rcx, rcx
0x18009361e  jz      short loc_180093633
0x180093620  xor     r9d, r9d
0x180093623  xor     r8d, r8d
0x180093626  lea     rdx, MPS_SVC_GP_Policy_Begin
0x18009362d  call    cs:__imp_EtwEventWrite
0x180093633  call    FwProfileMgrOnUpdatePolicyControl
0x180093638  mov     edi, eax
0x18009363a  mov     rcx, cs:g_Provider
0x180093641  test    rcx, rcx
0x180093644  jz      short loc_180093659
0x180093646  xor     r9d, r9d
0x180093649  xor     r8d, r8d
0x18009364c  lea     rdx, MPS_SVC_GP_Policy_End
0x180093653  call    cs:__imp_EtwEventWrite
0x180093659  test    edi, edi
0x18009365b  js      short loc_180093675
0x18009365d  call    FwAuditLogGroupPolicyChanged
0x180093662  xor     r8d, r8d; struct _EVENT_DATA_DESCRIPTOR *
0x180093665  xor     edx, edx; unsigned int
0x180093667  lea     rcx, WFGroupPolicySuccessEvent; struct _EVENT_DESCRIPTOR *
0x18009366e  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180093673  jmp     short loc_18009367C
0x180093675  mov     ecx, edi
0x180093677  call    FwEventGroupPolicyFailure
0x18009367c  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; this
0x180093683  call    ?LoadDaGPConfigHint@AppContainerDatabase@appIsolation@@QEAAKXZ; appIsolation::AppContainerDatabase::LoadDaGPConfigHint(void)
0x180093688  lea     rcx, [rsp+58h+arg_10]
0x18009368d  call    FwEdpOnGroupPolicyChangePhase1
0x180093692  call    FwAdhSnSGroupPolicyUpdate
0x180093697  call    FwHttpProxyGroupPolicyUpdate
0x18009369c  lea     rcx, [rsp+58h+arg_10]
0x1800936a1  call    FwEdpOnGroupPolicyChangePhase2
0x1800936a6  call    FwTenantRestrictionsPolicyUpdate
0x1800936ab  call    cs:__imp_GetTickCount64
0x1800936b1  sub     eax, esi
0x1800936b3  lea     rdx, aNull_2; "NULL"
0x1800936ba  mov     [rsp+58h+var_38], rdx
0x1800936bf  mov     r9d, eax
0x1800936c2  mov     r8d, [rsp+58h+arg_10]
0x1800936c7  xor     edx, edx
0x1800936c9  lea     rcx, aGppolicyupdate; "GpPolicyUpdate"
0x1800936d0  call    FwTelemetryEventWriteDataUpdate
0x1800936d5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x1800936dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x1800936e1  test    al, al
0x1800936e3  jnz     short loc_1800936F2
0x1800936e5  lea     rcx, ?g_FwGPMonGPUpdateLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800936ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800936f2  lea     rcx, aFwgpmongpupdat; "FwGPMonGPUpdate"
0x1800936f9  call    FwReleaseRPCSharedLock
0x1800936fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180093705  cmp     rcx, rbp
0x180093708  jz      short loc_180093722
0x18009370a  test    byte ptr [rcx+1Ch], 8
0x18009370e  jz      short loc_180093722
0x180093710  mov     edx, 12h
0x180093715  mov     r8, r14
0x180093718  mov     rcx, [rcx+10h]
0x18009371c  call    WPP_SF_
0x180093721  nop
0x180093722  test    rbx, rbx
0x180093725  jz      short loc_180093730
0x180093727  mov     rcx, rbx; lpCriticalSection
0x18009372a  call    cs:__imp_LeaveCriticalSection
0x180093730  mov     rbx, [rsp+58h+arg_0]
0x180093735  mov     rbp, [rsp+58h+arg_8]
0x18009373a  add     rsp, 40h
0x18009373e  pop     r14
0x180093740  pop     rdi
0x180093741  pop     rsi
0x180093742  retn
```
