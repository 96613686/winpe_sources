# AOMDHandler::Worker(void)

- ea: `0x180015010`
- end: `0x180015484`
- name: `?Worker@AOMDHandler@@EEAAJXZ`
- size: `1140`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000425c`
- `0x1800047bc`
- `0x1800079bc`
- `0x180007c18`
- `0x180007ca4`
- `0x18000872c`
- `0x18000a6d4`
- `0x18000d0d0`
- `0x18000e310`
- `0x180015010`
- `0x180015668`
- `0x180015e38`
- `0x180018a48`
- `0x180018c48`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001525d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001525d`
- `KERNEL32!GetCurrentThreadId` at `0x1800151d4`
- `KERNEL32!GetCurrentThreadId` at `0x1800151d4`
- `KERNEL32!CreateTimerQueueTimer` at `0x18001512a`
- `KERNEL32!CreateTimerQueueTimer` at `0x18001512a`
- `ole32!CoTaskMemFree` at `0x180015070`
- `ole32!CoTaskMemFree` at `0x1800150ce`
- `ole32!CoTaskMemFree` at `0x1800150fc`
- `ole32!CoTaskMemFree` at `0x180015450`
- `ole32!CoTaskMemFree` at `0x180015070`
- `ole32!CoTaskMemFree` at `0x1800150ce`
- `ole32!CoTaskMemFree` at `0x1800150fc`
- `ole32!CoTaskMemFree` at `0x180015450`
- `ADVAPI32!RegSetKeyValueW` at `0x180015310`
- `ADVAPI32!RegSetKeyValueW` at `0x180015310`

## pseudocode

```c
__int64 __fastcall AOMDHandler::Worker(AOMDHandler *this)
{
  volatile signed __int32 *v2; // rbx
  void *v3; // rax
  volatile signed __int32 *v4; // rbx
  void *v5; // rbx
  unsigned int v6; // r8d
  const char *v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  volatile signed __int32 **v10; // rbx
  __int64 *Local; // rax
  volatile signed __int32 *v12; // rax
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // esi
  __int64 v16; // rax
  void *v17; // rbx
  int v18; // eax
  unsigned int v19; // r8d
  void *v20; // rbx
  const char *v21; // r9
  __int64 result; // rax
  int DueTime; // [rsp+20h] [rbp-B8h]
  int DueTimea; // [rsp+20h] [rbp-B8h]
  __int64 v25; // [rsp+40h] [rbp-98h] BYREF
  int v26; // [rsp+48h] [rbp-90h] BYREF
  void *phNewTimer; // [rsp+50h] [rbp-88h] BYREF
  void **p_phNewTimer; // [rsp+58h] [rbp-80h] BYREF
  char v29; // [rsp+60h] [rbp-78h]
  LPVOID v30; // [rsp+68h] [rbp-70h] BYREF
  LPVOID v31; // [rsp+70h] [rbp-68h] BYREF
  __int64 v32; // [rsp+78h] [rbp-60h] BYREF
  void **v33; // [rsp+80h] [rbp-58h] BYREF
  _QWORD v34[2]; // [rsp+88h] [rbp-50h] BYREF
  __int64 v35; // [rsp+98h] [rbp-40h]
  DWORD CurrentThreadId; // [rsp+A0h] [rbp-38h]
  __int64 v37; // [rsp+A8h] [rbp-30h]
  char v38; // [rsp+B0h] [rbp-28h]
  LPVOID v39; // [rsp+B8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+E8h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+F0h] [rbp+18h] BYREF
  int v43; // [rsp+F8h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::start(
    &SystemTimeAsFileTime,
    &p_phNewTimer);
  v2 = (volatile signed __int32 *)g_usageTipTest;
  g_usageTipTest = (LPVOID)SystemTimeAsFileTime;
  if ( v2 && _InterlockedExchangeAdd(v2 + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(v2);
    CoTaskMemFree((LPVOID)v2);
  }
  pv = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::start(
    &pv,
    &p_phNewTimer);
  v3 = pv;
  pv = 0;
  v4 = (volatile signed __int32 *)g_reliabilityTipTest;
  g_reliabilityTipTest = v3;
  if ( v4 && _InterlockedExchangeAdd(v4 + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(v4);
    CoTaskMemFree((LPVOID)v4);
  }
  v5 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(v5);
    CoTaskMemFree(v5);
  }
  phNewTimer = 0;
  if ( !CreateTimerQueueTimer(&phNewTimer, 0, AOMDTipTestsExpirationTimerCallback, 0, 0x23D59580u, 0, 0) )
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x54C, v6, v7);
    phNewTimer = 0;
  }
  v10 = (volatile signed __int32 **)tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::ensure_data(&g_reliabilityTipTest);
  v33 = &tip2::test_watcher<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::`vftable';
  v34[0] = 0;
  v34[1] = &v33;
  v35 = 0;
  CurrentThreadId = 0;
  v37 = 0;
  v38 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v8) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v9,
                         v8);
    v34[0] = Local;
    if ( Local )
    {
      v35 = *Local;
      *Local = (__int64)v34;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v34[0] = 0;
  }
  v12 = *v10;
  v39 = (LPVOID)v12;
  if ( v12 )
    _InterlockedIncrement(v12 + 68);
  p_phNewTimer = &phNewTimer;
  v29 = 1;
  try
  {
    v13 = AOMDHandler::DoWork(this);
    v15 = v13;
    v43 = v13;
    if ( v13 >= 0 )
    {
      if ( g_aomdPromptResult != 7 )
      {
LABEL_29:
        if ( g_aomdPromptResult )
        {
          SystemTimeAsFileTime.dwLowDateTime = *((_DWORD *)this + 32);
          pv = (LPVOID)*((_QWORD *)this + 15);
          v30 = pv;
          pv = (LPVOID)*((_QWORD *)this + 13);
          v31 = pv;
          LODWORD(pv) = *((_DWORD *)this + 28);
          v25 = *((_QWORD *)this + 12);
          v32 = v25;
          v26 = g_mainToastSetting;
          LODWORD(v25) = g_aomdPromptResult;
          TlgHelper::AOMDEscalationStatus<unsigned int,unsigned int,long const &,_FILETIME,unsigned int,_FILETIME,_FILETIME,unsigned int>(
            (unsigned int)&v25,
            (unsigned int)&v26,
            (unsigned int)&v43,
            (unsigned int)&v32,
            (__int64)&pv,
            (__int64)&v31,
            (__int64)&v30,
            (__int64)&SystemTimeAsFileTime);
        }
        wil::details::lambda_call__lambda_9bb325be806e1a45cb5af93f77587a6e___::_lambda_call__lambda_9bb325be806e1a45cb5af93f77587a6e___(&p_phNewTimer);
        v20 = v39;
        if ( v39 && _InterlockedExchangeAdd((volatile signed __int32 *)v39 + 68, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(v20);
          CoTaskMemFree(v20);
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v34);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x571, v14, (const char *)(unsigned int)v13, DueTime);
    }
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( *((_DWORD *)this + 20) <= 0x1E8ABFD5u )
      v16 = 36000000000LL * *((unsigned int *)this + 20);
    else
      v16 = -1;
    v17 = (void *)(*(_QWORD *)&SystemTimeAsFileTime + v16);
    pv = (LPVOID)(*(_QWORD *)&SystemTimeAsFileTime + v16);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))TlgHelper::LogInfoFiletime<unsigned short const (&)[34],_FILETIME &,_FILETIME>)(
      SystemTimeAsFileTime,
      &SystemTimeAsFileTime,
      &pv);
    pv = v17;
    v18 = RegSetKeyValueW(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
            L"AOMDSelfThrottleEndTime",
            0xBu,
            &pv,
            8u);
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x58D, v19, (const char *)(unsigned int)v18, DueTimea);
    goto LABEL_29;
  }
  catch ( ... )
  {
    SystemTimeAsFileTime.dwLowDateTime = wil::details::in1diag3::Return_CaughtException(
                                           retaddr,
                                           (void *)0x5A1,
                                           (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                                           v21);
    return SystemTimeAsFileTime.dwLowDateTime;
  }
  return result;
}

```

## disassembly

```asm
0x180015010  mov     rax, rsp
0x180015013  mov     [rax+8], rbx
0x180015017  push    rsi
0x180015018  push    r14
0x18001501a  push    r15
0x18001501c  sub     rsp, 0C0h
0x180015023  mov     r14, rcx
0x180015026  xor     r15d, r15d
0x180015029  mov     [rax+10h], r15
0x18001502d  lea     rdx, [rax-80h]
0x180015031  lea     rcx, [rax+10h]
0x180015035  call    ?start@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::start(void)
0x18001503a  mov     rbx, cs:?g_usageTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>> g_usageTipTest
0x180015041  mov     rax, qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime]
0x180015049  mov     cs:?g_usageTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A, rax; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>> g_usageTipTest
0x180015050  test    rbx, rbx
0x180015053  jz      short loc_180015076
0x180015055  or      eax, 0FFFFFFFFh
0x180015058  lock xadd [rbx+150h], eax
0x180015060  cmp     eax, 1
0x180015063  jnz     short loc_180015076
0x180015065  mov     rcx, rbx
0x180015068  call    ??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)
0x18001506d  mov     rcx, rbx; pv
0x180015070  call    cs:__imp_CoTaskMemFree
0x180015076  mov     [rsp+0D8h+pv], r15
0x18001507e  lea     rdx, [rsp+0D8h+var_80]
0x180015083  lea     rcx, [rsp+0D8h+pv]
0x18001508b  call    ?start@?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::start(void)
0x180015090  mov     rax, [rsp+0D8h+pv]
0x180015098  mov     [rsp+0D8h+pv], r15
0x1800150a0  mov     rbx, cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x1800150a7  mov     cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A, rax; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x1800150ae  test    rbx, rbx
0x1800150b1  jz      short loc_1800150D4
0x1800150b3  or      eax, 0FFFFFFFFh
0x1800150b6  lock xadd [rbx+110h], eax
0x1800150be  cmp     eax, 1
0x1800150c1  jnz     short loc_1800150D4
0x1800150c3  mov     rcx, rbx
0x1800150c6  call    ??1?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(void)
0x1800150cb  mov     rcx, rbx; pv
0x1800150ce  call    cs:__imp_CoTaskMemFree
0x1800150d4  mov     rbx, [rsp+0D8h+pv]
0x1800150dc  test    rbx, rbx
0x1800150df  jz      short loc_180015102
0x1800150e1  or      eax, 0FFFFFFFFh
0x1800150e4  lock xadd [rbx+110h], eax
0x1800150ec  cmp     eax, 1
0x1800150ef  jnz     short loc_180015102
0x1800150f1  mov     rcx, rbx
0x1800150f4  call    ??1?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(void)
0x1800150f9  mov     rcx, rbx; pv
0x1800150fc  call    cs:__imp_CoTaskMemFree
0x180015102  mov     [rsp+0D8h+phNewTimer], r15
0x180015107  mov     [rsp+0D8h+Flags], r15d; Flags
0x18001510c  mov     [rsp+0D8h+Period], r15d; Period
0x180015111  mov     [rsp+0D8h+DueTime], 23D59580h; int
0x180015119  xor     r9d, r9d; Parameter
0x18001511c  lea     r8, ?AOMDTipTestsExpirationTimerCallback@@YAXPEAXE@Z; Callback
0x180015123  xor     edx, edx; TimerQueue
0x180015125  lea     rcx, [rsp+0D8h+phNewTimer]; phNewTimer
0x18001512a  call    cs:__imp_CreateTimerQueueTimer
0x180015130  test    eax, eax
0x180015132  jnz     short loc_18001514B
0x180015134  mov     rcx, [rsp+0D8h]; this
0x18001513c  mov     edx, 54Ch; void *
0x180015141  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180015146  mov     [rsp+0D8h+phNewTimer], r15
0x18001514b  lea     rcx, ?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x180015152  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::ensure_data(void)
0x180015157  mov     rbx, rax
0x18001515a  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::`vftable'
0x180015161  mov     [rsp+0D8h+var_58], rax
0x180015169  mov     [rsp+0D8h+var_50], r15
0x180015171  lea     rax, [rsp+0D8h+var_58]
0x180015179  mov     [rsp+0D8h+var_48], rax
0x180015181  mov     [rsp+0D8h+var_40], r15
0x180015189  mov     [rsp+0D8h+var_38], r15d
0x180015191  mov     [rsp+0D8h+var_30], r15
0x180015199  mov     [rsp+0D8h+var_28], r15b
0x1800151a1  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800151a8  jz      short loc_1800151E3
0x1800151aa  mov     dl, 1
0x1800151ac  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800151b1  mov     [rsp+0D8h+var_50], rax
0x1800151b9  test    rax, rax
0x1800151bc  jz      short loc_1800151EB
0x1800151be  mov     rcx, [rax]
0x1800151c1  mov     [rsp+0D8h+var_40], rcx
0x1800151c9  lea     rcx, [rsp+0D8h+var_50]
0x1800151d1  mov     [rax], rcx
0x1800151d4  call    cs:__imp_GetCurrentThreadId
0x1800151da  mov     [rsp+0D8h+var_38], eax
0x1800151e1  jmp     short loc_1800151EB
0x1800151e3  mov     [rsp+0D8h+var_50], r15
0x1800151eb  mov     rax, [rbx]
0x1800151ee  mov     [rsp+0D8h+var_20], rax
0x1800151f6  test    rax, rax
0x1800151f9  jz      short loc_180015202
0x1800151fb  lock inc dword ptr [rax+110h]
0x180015202  lea     rax, [rsp+0D8h+phNewTimer]
0x180015207  mov     [rsp+0D8h+var_80], rax
0x18001520c  mov     [rsp+0D8h+var_78], 1
0x180015211  mov     rcx, r14; this
0x180015214  call    ?DoWork@AOMDHandler@@AEAAJXZ; AOMDHandler::DoWork(void)
0x180015219  mov     esi, eax
0x18001521b  mov     [rsp+0D8h+arg_18], eax
0x180015222  mov     rcx, [rsp+0D8h]; this
0x18001522a  test    eax, eax
0x18001522c  jns     short loc_18001523D
0x18001522e  mov     r9d, eax; char *
0x180015231  mov     edx, 571h; void *
0x180015236  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001523b  jmp     short loc_18001524D
0x18001523d  mov     eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180015243  nop
0x180015244  cmp     eax, 7
0x180015247  jnz     loc_18001533B
0x18001524d  mov     qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180015255  lea     rcx, [rsp+0D8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001525d  call    cs:__imp_GetSystemTimeAsFileTime
0x180015263  mov     ecx, [rsp+0D8h+SystemTimeAsFileTime.dwHighDateTime]
0x18001526a  shl     rcx, 20h
0x18001526e  mov     eax, [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime]
0x180015275  or      rcx, rax
0x180015278  cmp     dword ptr [r14+50h], 1E8ABFD5h
0x180015280  jbe     short loc_180015288
0x180015282  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015286  jmp     short loc_18001529A
0x180015288  mov     eax, [r14+50h]
0x18001528c  mov     rdx, 861C46800h
0x180015296  imul    rax, rdx
0x18001529a  lea     rbx, [rcx+rax]
0x18001529e  mov     dword ptr [rsp+0D8h+pv], ebx
0x1800152a5  mov     rax, rbx
0x1800152a8  shr     rax, 20h
0x1800152ac  mov     dword ptr [rsp+0D8h+pv+4], eax
0x1800152b3  mov     rax, [rsp+0D8h+pv]
0x1800152bb  mov     [rsp+0D8h+pv], rax
0x1800152c3  lea     r8, [rsp+0D8h+pv]
0x1800152cb  lea     rdx, [rsp+0D8h+SystemTimeAsFileTime]
0x1800152d3  call    ??$LogInfoFiletime@AEAY0CC@$$CBGAEAU_FILETIME@@U1@@TlgHelper@@SAXAEAY0CC@$$CBGAEAU_FILETIME@@$$QEAU1@@Z; TlgHelper::LogInfoFiletime<ushort const (&)[34],_FILETIME &,_FILETIME>(ushort const (&)[34],_FILETIME &,_FILETIME &&)
0x1800152d8  mov     [rsp+0D8h+pv], rbx
0x1800152e0  mov     [rsp+0D8h+Period], 8; cbData
0x1800152e8  lea     rax, [rsp+0D8h+pv]
0x1800152f0  mov     qword ptr [rsp+0D8h+DueTime], rax; int
0x1800152f5  mov     r9d, 0Bh; dwType
0x1800152fb  lea     r8, aAomdselfthrott_0; "AOMDSelfThrottleEndTime"
0x180015302  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180015309  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180015310  call    cs:__imp_RegSetKeyValueW
0x180015316  test    eax, eax
0x180015318  jle     short loc_180015322
0x18001531a  movzx   eax, ax
0x18001531d  or      eax, 80070000h
0x180015322  mov     rcx, [rsp+0D8h]; this
0x18001532a  test    eax, eax
0x18001532c  jns     short loc_18001533B
0x18001532e  mov     r9d, eax; char *
0x180015331  mov     edx, 58Dh; void *
0x180015336  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001533b  mov     ecx, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180015341  nop
0x180015342  test    ecx, ecx
0x180015344  jz      loc_18001541D
0x18001534a  mov     eax, [r14+80h]
0x180015351  mov     [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime], eax
0x180015358  mov     rax, [r14+78h]
0x18001535c  mov     dword ptr [rsp+0D8h+pv], eax
0x180015363  shr     rax, 20h
0x180015367  mov     dword ptr [rsp+0D8h+pv+4], eax
0x18001536e  mov     rax, [rsp+0D8h+pv]
0x180015376  mov     [rsp+0D8h+var_70], rax
0x18001537b  mov     rax, [r14+68h]
0x18001537f  mov     dword ptr [rsp+0D8h+pv], eax
0x180015386  shr     rax, 20h
0x18001538a  mov     dword ptr [rsp+0D8h+pv+4], eax
0x180015391  mov     rax, [rsp+0D8h+pv]
0x180015399  mov     [rsp+0D8h+var_68], rax
0x18001539e  mov     eax, [r14+70h]
0x1800153a2  mov     dword ptr [rsp+0D8h+pv], eax
0x1800153a9  mov     rax, [r14+60h]
0x1800153ad  mov     dword ptr [rsp+0D8h+var_98], eax
0x1800153b1  shr     rax, 20h
0x1800153b5  mov     dword ptr [rsp+0D8h+var_98+4], eax
0x1800153b9  mov     rax, [rsp+0D8h+var_98]
0x1800153be  mov     [rsp+0D8h+var_60], rax
0x1800153c3  mov     eax, cs:?g_mainToastSetting@@3U?$atomic@W4MainToastNotificationSetting@@@std@@A; std::atomic<MainToastNotificationSetting> g_mainToastSetting
0x1800153c9  nop
0x1800153ca  mov     [rsp+0D8h+var_90], eax
0x1800153ce  mov     dword ptr [rsp+0D8h+var_98], ecx
0x1800153d2  lea     rax, [rsp+0D8h+SystemTimeAsFileTime]
0x1800153da  mov     [rsp+0D8h+var_A0], rax
0x1800153df  lea     rax, [rsp+0D8h+var_70]
0x1800153e4  mov     qword ptr [rsp+0D8h+Flags], rax
0x1800153e9  lea     rax, [rsp+0D8h+var_68]
0x1800153ee  mov     qword ptr [rsp+0D8h+Period], rax
0x1800153f3  lea     rax, [rsp+0D8h+pv]
0x1800153fb  mov     qword ptr [rsp+0D8h+DueTime], rax
0x180015400  lea     r9, [rsp+0D8h+var_60]
0x180015405  lea     r8, [rsp+0D8h+arg_18]
0x18001540d  lea     rdx, [rsp+0D8h+var_90]
0x180015412  lea     rcx, [rsp+0D8h+var_98]
0x180015417  call    ??$AOMDEscalationStatus@IIAEBJU_FILETIME@@IU1@U1@I@TlgHelper@@SAX$$QEAI0AEBJ$$QEAU_FILETIME@@0220@Z; TlgHelper::AOMDEscalationStatus<uint,uint,long const &,_FILETIME,uint,_FILETIME,_FILETIME,uint>(uint &&,uint &&,long const &,_FILETIME &&,uint &&,_FILETIME &&,_FILETIME &&,uint &&)
0x18001541c  nop
0x18001541d  lea     rcx, [rsp+0D8h+var_80]
0x180015422  call    wil__details__lambda_call__lambda_9bb325be806e1a45cb5af93f77587a6e______lambda_call__lambda_9bb325be806e1a45cb5af93f77587a6e___
0x180015427  nop
0x180015428  mov     rbx, [rsp+0D8h+var_20]
0x180015430  test    rbx, rbx
0x180015433  jz      short loc_180015456
0x180015435  or      edx, 0FFFFFFFFh
0x180015438  lock xadd [rbx+110h], edx
0x180015440  cmp     edx, 1
0x180015443  jnz     short loc_180015456
0x180015445  mov     rcx, rbx
0x180015448  call    ??1?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(void)
0x18001544d  mov     rcx, rbx; pv
0x180015450  call    cs:__imp_CoTaskMemFree
0x180015456  lea     rcx, [rsp+0D8h+var_50]; this
0x18001545e  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180015463  mov     eax, esi
0x180015465  jmp     short loc_18001546E
0x180015467  mov     eax, [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime]
0x18001546e  mov     rbx, [rsp+0D8h+arg_0]
0x180015476  add     rsp, 0C0h
0x18001547d  pop     r15
0x18001547f  pop     r14
0x180015481  pop     rsi
0x180015482  retn
```
