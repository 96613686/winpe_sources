# FwGPMonGPUpdate(void *,uchar)

- ea: `0x1800981a0`
- end: `0x180098480`
- name: `?FwGPMonGPUpdate@@YAXPEAXE@Z`
- size: `736`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007b58`
- `0x180008d60`
- `0x18000a710`
- `0x1800192e0`
- `0x180048250`
- `0x180059160`
- `0x180069d98`
- `0x180069dd0`
- `0x18006e92c`
- `0x18006f778`
- `0x18007ead0`
- `0x18008e9c8`
- `0x180091230`
- `0x180092610`
- `0x180092630`
- `0x180094550`
- `0x180094610`
- `0x1800981a0`
- `0x1800aa54c`
- `0x1800bb410`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18009835a`
- `ntdll!EtwEventWrite` at `0x180098386`
- `ntdll!EtwEventWrite` at `0x18009835a`
- `ntdll!EtwEventWrite` at `0x180098386`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180098264`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800983e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180098264`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800983e4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009831b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009831b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009842b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009842b`

## string_xrefs

- `0x180098273`: `FwGPMonGPUpdate`
- `0x180098303`: `FwGPMonGPUpdate`
- `0x180098437`: `FwGPMonGPUpdate`
- `0x180098408`: `GpPolicyUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FwGPMonGPUpdate(void *a1)
{
  __int64 v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rdx
  int TickCount64; // edi
  int v5; // eax
  __int64 v6; // r9
  int updated; // ebx
  int v8; // eax
  _BYTE v9[40]; // [rsp+30h] [rbp-28h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF
  __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  v10 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_54aaf373e16d351bc598c08934e7dc83_Traceguids);
  v11 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
  {
    v1 = CallbackGate::TryEnterQueue(&g_FwGPMonGPUpdateGate, v9);
    CallbackGate::QueueState::operator=(&v11, v1);
    CallbackGate::QueueState::~QueueState((CallbackGate::QueueState *)v9);
    if ( !v11 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v3 = 15;
LABEL_33:
        WPP_SF_(*(_QWORD *)(v2 + 16), v3, WPP_54aaf373e16d351bc598c08934e7dc83_Traceguids);
        goto LABEL_34;
      }
      goto LABEL_34;
    }
    ++g_CallbackGateCountGPUpdate;
  }
  TickCount64 = GetTickCount64();
  v5 = FwAcquireRPCSharedLock("FwGPMonGPUpdate");
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        16,
        WPP_54aaf373e16d351bc598c08934e7dc83_Traceguids,
        (unsigned int)v5);
    goto LABEL_34;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
  {
    if ( _InterlockedCompareExchange(&g_IsThreadWaiting, 1, 0) )
    {
      v6 = (unsigned int)_InterlockedIncrement(&g_ThreadsReturnedCount);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_54aaf373e16d351bc598c08934e7dc83_Traceguids, v6);
      FwReleaseRPCSharedLock("FwGPMonGPUpdate");
      goto LABEL_34;
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
  FwEdpOnGroupPolicyChangePhase1(&v10);
  FwAdhSnSGroupPolicyUpdate();
  FwHttpProxyGroupPolicyUpdate();
  FwEdpOnGroupPolicyChangePhase2(&v10);
  FwTenantRestrictionsPolicyUpdate();
  v8 = GetTickCount64();
  FwTelemetryEventWriteDataUpdate((unsigned int)L"GpPolicyUpdate", 0, v10, v8 - TickCount64, (__int64)L"NULL");
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
    ReleaseSRWLockExclusive(&g_FwGPMonGPUpdateLock);
  FwReleaseRPCSharedLock("FwGPMonGPUpdate");
  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    v3 = 18;
    goto LABEL_33;
  }
LABEL_34:
  CallbackGate::QueueState::~QueueState((CallbackGate::QueueState *)&v11);
}

```

## disassembly

```asm
0x1800981a0  mov     [rsp+arg_0], rbx
0x1800981a5  push    rbp
0x1800981a6  push    rdi
0x1800981a7  push    r14
0x1800981a9  sub     rsp, 40h
0x1800981ad  mov     [rsp+58h+arg_10], 0
0x1800981b5  lea     rbp, WPP_GLOBAL_Control
0x1800981bc  lea     r14, WPP_54aaf373e16d351bc598c08934e7dc83_Traceguids
0x1800981c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800981ca  cmp     rcx, rbp
0x1800981cd  jz      short loc_1800981E6
0x1800981cf  test    byte ptr [rcx+1Ch], 8
0x1800981d3  jz      short loc_1800981E6
0x1800981d5  mov     edx, 0Eh
0x1800981da  mov     r8, r14
0x1800981dd  mov     rcx, [rcx+10h]
0x1800981e1  call    WPP_SF_
0x1800981e6  mov     [rsp+58h+arg_18], 0
0x1800981ef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x1800981f6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x1800981fb  mov     ebx, 1
0x180098200  test    al, al
0x180098202  jz      short loc_180098264
0x180098204  lea     rdx, [rsp+58h+var_28]
0x180098209  lea     rcx, ?g_FwGPMonGPUpdateGate@@3VCallbackGate@@A; CallbackGate g_FwGPMonGPUpdateGate
0x180098210  call    ?TryEnterQueue@CallbackGate@@QEAA?AVQueueState@1@XZ; CallbackGate::TryEnterQueue(void)
0x180098215  mov     rdx, rax
0x180098218  lea     rcx, [rsp+58h+arg_18]
0x18009821d  call    ??4QueueState@CallbackGate@@QEAAAEAV01@$$QEAV01@@Z; CallbackGate::QueueState::operator=(CallbackGate::QueueState &&)
0x180098222  lea     rcx, [rsp+58h+var_28]; this
0x180098227  call    ??1QueueState@CallbackGate@@QEAA@XZ; CallbackGate::QueueState::~QueueState(void)
0x18009822c  cmp     [rsp+58h+arg_18], 0
0x180098232  jnz     short loc_180098256
0x180098234  mov     rcx, cs:WPP_GLOBAL_Control
0x18009823b  cmp     rcx, rbp
0x18009823e  jz      loc_180098467
0x180098244  test    byte ptr [rcx+1Ch], 4
0x180098248  jz      loc_180098467
0x18009824e  lea     edx, [rbx+0Eh]
0x180098251  jmp     loc_18009845A
0x180098256  mov     eax, cs:?g_CallbackGateCountGPUpdate@@3KC; ulong volatile g_CallbackGateCountGPUpdate
0x18009825c  add     eax, ebx
0x18009825e  mov     cs:?g_CallbackGateCountGPUpdate@@3KC, eax; ulong volatile g_CallbackGateCountGPUpdate
0x180098264  call    cs:__imp_GetTickCount64
0x18009826b  nop     dword ptr [rax+rax+00h]
0x180098270  mov     rdi, rax
0x180098273  lea     rcx, aFwgpmongpupdat; "FwGPMonGPUpdate"
0x18009827a  call    FwAcquireRPCSharedLock
0x18009827f  test    eax, eax
0x180098281  jns     short loc_1800982B5
0x180098283  mov     rcx, cs:WPP_GLOBAL_Control
0x18009828a  cmp     rcx, rbp
0x18009828d  jz      loc_180098467
0x180098293  test    [rcx+1Ch], bl
0x180098296  jz      loc_180098467
0x18009829c  mov     edx, 10h
0x1800982a1  mov     r9d, eax
0x1800982a4  mov     r8, r14
0x1800982a7  mov     rcx, [rcx+10h]
0x1800982ab  call    WPP_SF_d
0x1800982b0  jmp     loc_180098467
0x1800982b5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x1800982bc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x1800982c1  test    al, al
0x1800982c3  jnz     short loc_180098341
0x1800982c5  xor     eax, eax
0x1800982c7  lock cmpxchg cs:?g_IsThreadWaiting@@3HC, ebx; int volatile g_IsThreadWaiting
0x1800982cf  jz      short loc_180098314
0x1800982d1  mov     r9d, ebx
0x1800982d4  lock xadd cs:?g_ThreadsReturnedCount@@3JC, r9d; long volatile g_ThreadsReturnedCount
0x1800982dd  add     r9d, ebx
0x1800982e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800982e7  cmp     rcx, rbp
0x1800982ea  jz      short loc_180098303
0x1800982ec  test    byte ptr [rcx+1Ch], 4
0x1800982f0  jz      short loc_180098303
0x1800982f2  mov     edx, 11h
0x1800982f7  mov     r8, r14
0x1800982fa  mov     rcx, [rcx+10h]
0x1800982fe  call    WPP_SF_d
0x180098303  lea     rcx, aFwgpmongpupdat; "FwGPMonGPUpdate"
0x18009830a  call    FwReleaseRPCSharedLock
0x18009830f  jmp     loc_180098467
0x180098314  lea     rcx, ?g_FwGPMonGPUpdateLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18009831b  call    cs:__imp_AcquireSRWLockExclusive
0x180098322  nop     dword ptr [rax+rax+00h]
0x180098327  mov     ecx, cs:?g_CallbackGateCountGPUpdate_old@@3KC; ulong volatile g_CallbackGateCountGPUpdate_old
0x18009832d  add     ecx, ebx
0x18009832f  mov     cs:?g_CallbackGateCountGPUpdate_old@@3KC, ecx; ulong volatile g_CallbackGateCountGPUpdate_old
0x180098335  xor     ecx, ecx
0x180098337  mov     eax, ebx
0x180098339  lock cmpxchg cs:?g_IsThreadWaiting@@3HC, ecx; int volatile g_IsThreadWaiting
0x180098341  mov     rcx, cs:g_Provider
0x180098348  test    rcx, rcx
0x18009834b  jz      short loc_180098366
0x18009834d  xor     r9d, r9d
0x180098350  xor     r8d, r8d
0x180098353  lea     rdx, MPS_SVC_GP_Policy_Begin
0x18009835a  call    cs:__imp_EtwEventWrite
0x180098361  nop     dword ptr [rax+rax+00h]
0x180098366  call    FwProfileMgrOnUpdatePolicyControl
0x18009836b  mov     ebx, eax
0x18009836d  mov     rcx, cs:g_Provider
0x180098374  test    rcx, rcx
0x180098377  jz      short loc_180098392
0x180098379  xor     r9d, r9d
0x18009837c  xor     r8d, r8d
0x18009837f  lea     rdx, MPS_SVC_GP_Policy_End
0x180098386  call    cs:__imp_EtwEventWrite
0x18009838d  nop     dword ptr [rax+rax+00h]
0x180098392  test    ebx, ebx
0x180098394  js      short loc_1800983AE
0x180098396  call    FwAuditLogGroupPolicyChanged
0x18009839b  xor     r8d, r8d; struct _EVENT_DATA_DESCRIPTOR *
0x18009839e  xor     edx, edx; unsigned int
0x1800983a0  lea     rcx, WFGroupPolicySuccessEvent; struct _EVENT_DESCRIPTOR *
0x1800983a7  call    ?FwLogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; FwLogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x1800983ac  jmp     short loc_1800983B5
0x1800983ae  mov     ecx, ebx
0x1800983b0  call    FwEventGroupPolicyFailure
0x1800983b5  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; this
0x1800983bc  call    ?LoadDaGPConfigHint@AppContainerDatabase@appIsolation@@QEAAKXZ; appIsolation::AppContainerDatabase::LoadDaGPConfigHint(void)
0x1800983c1  lea     rcx, [rsp+58h+arg_10]
0x1800983c6  call    FwEdpOnGroupPolicyChangePhase1
0x1800983cb  call    FwAdhSnSGroupPolicyUpdate
0x1800983d0  call    FwHttpProxyGroupPolicyUpdate
0x1800983d5  lea     rcx, [rsp+58h+arg_10]
0x1800983da  call    FwEdpOnGroupPolicyChangePhase2
0x1800983df  call    FwTenantRestrictionsPolicyUpdate
0x1800983e4  call    cs:__imp_GetTickCount64
0x1800983eb  nop     dword ptr [rax+rax+00h]
0x1800983f0  sub     eax, edi
0x1800983f2  lea     rdx, aNull_2; "NULL"
0x1800983f9  mov     [rsp+58h+var_38], rdx
0x1800983fe  mov     r9d, eax
0x180098401  mov     r8d, [rsp+58h+arg_10]
0x180098406  xor     edx, edx
0x180098408  lea     rcx, aGppolicyupdate; "GpPolicyUpdate"
0x18009840f  call    FwTelemetryEventWriteDataUpdate
0x180098414  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x18009841b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x180098420  test    al, al
0x180098422  jnz     short loc_180098437
0x180098424  lea     rcx, ?g_FwGPMonGPUpdateLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18009842b  call    cs:__imp_ReleaseSRWLockExclusive
0x180098432  nop     dword ptr [rax+rax+00h]
0x180098437  lea     rcx, aFwgpmongpupdat; "FwGPMonGPUpdate"
0x18009843e  call    FwReleaseRPCSharedLock
0x180098443  mov     rcx, cs:WPP_GLOBAL_Control
0x18009844a  cmp     rcx, rbp
0x18009844d  jz      short loc_180098467
0x18009844f  test    byte ptr [rcx+1Ch], 8
0x180098453  jz      short loc_180098467
0x180098455  mov     edx, 12h
0x18009845a  mov     r8, r14
0x18009845d  mov     rcx, [rcx+10h]
0x180098461  call    WPP_SF_
0x180098466  nop
0x180098467  lea     rcx, [rsp+58h+arg_18]; this
0x18009846c  call    ??1QueueState@CallbackGate@@QEAA@XZ; CallbackGate::QueueState::~QueueState(void)
0x180098471  mov     rbx, [rsp+58h+arg_0]
0x180098476  add     rsp, 40h
0x18009847a  pop     r14
0x18009847c  pop     rdi
0x18009847d  pop     rbp
0x18009847e  retn
```
