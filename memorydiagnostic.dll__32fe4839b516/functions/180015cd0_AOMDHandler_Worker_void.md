# AOMDHandler::Worker(void)

- ea: `0x180015cd0`
- end: `0x180016130`
- name: `?Worker@AOMDHandler@@EEAAJXZ`
- size: `1120`
- prototype: `__int64 __fastcall(DWORD *this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003ca8`
- `0x180003f2c`
- `0x180006a0c`
- `0x180006bc4`
- `0x180007bf0`
- `0x1800085b0`
- `0x1800087a4`
- `0x18000a7e4`
- `0x18000d804`
- `0x18000eaec`
- `0x180010ba8`
- `0x180015cd0`
- `0x18001634c`
- `0x180019a18`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180015f0f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180015f0f`
- `KERNEL32!GetCurrentThreadId` at `0x180015e7e`
- `KERNEL32!GetCurrentThreadId` at `0x180015e7e`
- `KERNEL32!CreateTimerQueueTimer` at `0x180015d9d`
- `KERNEL32!CreateTimerQueueTimer` at `0x180015d9d`
- `ole32!CoTaskMemFree` at `0x180015d32`
- `ole32!CoTaskMemFree` at `0x180015d32`
- `ADVAPI32!RegSetKeyValueW` at `0x180015fbf`
- `ADVAPI32!RegSetKeyValueW` at `0x180015fbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AOMDHandler::Worker(DWORD *this)
{
  volatile signed __int32 *v2; // rbx
  __int64 v3; // rdi
  void **v4; // rax
  void *v5; // rdx
  void *v6; // rcx
  void *v8; // rdx
  LPVOID v9; // rcx
  unsigned int v10; // r8d
  const char *v11; // r9
  void **v12; // rax
  void *v13; // rcx
  __int64 *Local; // rax
  DWORD CurrentThreadId; // eax
  int v16; // eax
  unsigned int v17; // r8d
  __int64 v18; // rcx
  __int64 v19; // rbx
  int v20; // eax
  unsigned int v21; // r8d
  const char *v22; // r9
  __int64 result; // rax
  int DueTime; // [rsp+20h] [rbp-C8h]
  int DueTimea; // [rsp+20h] [rbp-C8h]
  int v26; // [rsp+40h] [rbp-A8h] BYREF
  int v27; // [rsp+44h] [rbp-A4h] BYREF
  __int64 v28; // [rsp+48h] [rbp-A0h]
  void *phNewTimer; // [rsp+50h] [rbp-98h] BYREF
  void **p_phNewTimer; // [rsp+58h] [rbp-90h] BYREF
  char v31; // [rsp+60h] [rbp-88h]
  LPVOID pv; // [rsp+68h] [rbp-80h] BYREF
  LPVOID v33; // [rsp+70h] [rbp-78h] BYREF
  __int64 v34; // [rsp+78h] [rbp-70h] BYREF
  __int64 v35; // [rsp+80h] [rbp-68h] BYREF
  __int64 v36; // [rsp+88h] [rbp-60h] BYREF
  void **v37; // [rsp+90h] [rbp-58h] BYREF
  _QWORD v38[2]; // [rsp+98h] [rbp-50h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-40h]
  DWORD v40; // [rsp+B0h] [rbp-38h]
  __int64 v41; // [rsp+B8h] [rbp-30h]
  char v42; // [rsp+C0h] [rbp-28h]
  LPVOID v43; // [rsp+C8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  void *v45; // [rsp+F8h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+100h] [rbp+18h] BYREF
  __int64 Data; // [rsp+108h] [rbp+20h] BYREF

  v45 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::start(
    &v45,
    &p_phNewTimer);
  v2 = (volatile signed __int32 *)g_usageTipTest;
  g_usageTipTest = v45;
  v3 = -1;
  if ( v2 && _InterlockedExchangeAdd(v2 + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(v2);
    CoTaskMemFree((LPVOID)v2);
  }
  v4 = (void **)tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>>(&pv);
  v5 = *v4;
  *v4 = 0;
  v6 = g_reliabilityTipTest;
  g_reliabilityTipTest = v5;
  if ( v6 )
    tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(v6);
  if ( pv )
    tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(pv);
  phNewTimer = 0;
  if ( !CreateTimerQueueTimer(&phNewTimer, 0, AOMDTipTestsExpirationTimerCallback, 0, 0x23D59580u, 0, 0) )
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x5AB, v10, v11);
    phNewTimer = 0;
  }
  if ( !g_reliabilityTipTest )
  {
    v12 = (void **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>,>(&v33);
    v8 = *v12;
    *v12 = 0;
    v13 = g_reliabilityTipTest;
    g_reliabilityTipTest = v8;
    if ( v13 )
      tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(v13);
    v9 = v33;
    if ( v33 )
      tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(v33);
  }
  v37 = &tip2::test_watcher<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::`vftable';
  v38[0] = 0;
  v38[1] = &v37;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v8) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v9,
                         v8);
    v38[0] = Local;
    if ( Local )
    {
      v39 = *Local;
      *Local = (__int64)v38;
      CurrentThreadId = GetCurrentThreadId();
      v40 = CurrentThreadId;
    }
  }
  else
  {
    v38[0] = 0;
  }
  v43 = g_reliabilityTipTest;
  if ( g_reliabilityTipTest )
    _InterlockedIncrement((volatile signed __int32 *)g_reliabilityTipTest + 68);
  p_phNewTimer = &phNewTimer;
  v31 = 1;
  try
  {
    v16 = AOMDHandler::DoWork((AOMDHandler *)this);
    LODWORD(v45) = v16;
    if ( v16 >= 0 )
    {
      if ( g_aomdPromptResult != 7 )
      {
LABEL_31:
        if ( g_aomdPromptResult )
        {
          SystemTimeAsFileTime.dwLowDateTime = this[32];
          Data = *((_QWORD *)this + 15);
          v34 = Data;
          Data = *((_QWORD *)this + 13);
          v35 = Data;
          LODWORD(Data) = this[28];
          v28 = *((_QWORD *)this + 12);
          v36 = v28;
          v26 = g_mainToastSetting;
          v27 = g_aomdPromptResult;
          TlgHelper::AOMDEscalationStatus<unsigned int,unsigned int,long const &,_FILETIME,unsigned int,_FILETIME,_FILETIME,unsigned int>(
            (unsigned int)&v27,
            (unsigned int)&v26,
            (unsigned int)&v45,
            (unsigned int)&v36,
            (__int64)&Data,
            (__int64)&v35,
            (__int64)&v34,
            (__int64)&SystemTimeAsFileTime);
        }
        v31 = 0;
        lambda_312d26372c3169cab680c6a412e6d847_::operator()(&p_phNewTimer);
        if ( v43 )
          tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(v43);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v38);
        return (unsigned int)v45;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x5D6, v17, (const char *)(unsigned int)v16, DueTime);
    }
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( this[20] <= 0x1E8ABFD5 )
      v3 = 36000000000LL * this[20];
    v19 = v3 + *(_QWORD *)&SystemTimeAsFileTime;
    Data = v3 + *(_QWORD *)&SystemTimeAsFileTime;
    TlgHelper::LogInfoFiletime<unsigned short const (&)[34],_FILETIME &,_FILETIME>(v18, &SystemTimeAsFileTime, &Data);
    Data = v19;
    v20 = RegSetKeyValueW(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
            L"AOMDSelfThrottleEndTime",
            0xBu,
            &Data,
            8u);
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x5F2, v21, (const char *)(unsigned int)v20, DueTimea);
    goto LABEL_31;
  }
  catch ( ... )
  {
    LODWORD(v45) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x606,
                     (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                     v22);
    return (unsigned int)v45;
  }
  return result;
}

```

## disassembly

```asm
0x180015cd0  mov     rax, rsp
0x180015cd3  mov     [rax+8], rbx
0x180015cd7  push    rsi
0x180015cd8  push    rdi
0x180015cd9  push    r14
0x180015cdb  sub     rsp, 0D0h
0x180015ce2  mov     rsi, rcx
0x180015ce5  xor     r14d, r14d
0x180015ce8  mov     [rax+10h], r14
0x180015cec  lea     rdx, [rsp+0E8h+var_90]
0x180015cf1  lea     rcx, [rax+10h]
0x180015cf5  call    ?start@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::start(void)
0x180015cfa  mov     rax, [rsp+0E8h+arg_8]
0x180015d02  mov     rbx, cs:?g_usageTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>> g_usageTipTest
0x180015d09  mov     cs:?g_usageTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A, rax; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>> g_usageTipTest
0x180015d10  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180015d14  test    rbx, rbx
0x180015d17  jz      short loc_180015D3E
0x180015d19  mov     eax, edi
0x180015d1b  lock xadd [rbx+150h], eax
0x180015d23  add     eax, edi
0x180015d25  jnz     short loc_180015D3E
0x180015d27  mov     rcx, rbx
0x180015d2a  call    ??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)
0x180015d2f  mov     rcx, rbx; pv
0x180015d32  call    cs:__imp_CoTaskMemFree
0x180015d39  nop     dword ptr [rax+rax+00h]
0x180015d3e  lea     rcx, [rsp+0E8h+pv]
0x180015d43  call    ??$start@V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>>(void)
0x180015d48  mov     rdx, [rax]
0x180015d4b  mov     [rax], r14
0x180015d4e  mov     rcx, cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A; pv
0x180015d55  mov     cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A, rdx; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x180015d5c  test    rcx, rcx
0x180015d5f  jz      short loc_180015D66
0x180015d61  call    ?Release@?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(void)
0x180015d66  mov     rcx, [rsp+0E8h+pv]; pv
0x180015d6b  test    rcx, rcx
0x180015d6e  jz      short loc_180015D75
0x180015d70  call    ?Release@?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(void)
0x180015d75  mov     [rsp+0E8h+phNewTimer], r14
0x180015d7a  mov     [rsp+0E8h+Flags], r14d; Flags
0x180015d7f  mov     [rsp+0E8h+Period], r14d; Period
0x180015d84  mov     [rsp+0E8h+DueTime], 23D59580h; int
0x180015d8c  xor     r9d, r9d; Parameter
0x180015d8f  lea     r8, ?AOMDTipTestsExpirationTimerCallback@@YAXPEAXE@Z; Callback
0x180015d96  xor     edx, edx; TimerQueue
0x180015d98  lea     rcx, [rsp+0E8h+phNewTimer]; phNewTimer
0x180015d9d  call    cs:__imp_CreateTimerQueueTimer
0x180015da4  nop     dword ptr [rax+rax+00h]
0x180015da9  test    eax, eax
0x180015dab  jnz     short loc_180015DC4
0x180015dad  mov     rcx, [rsp+0E8h]; this
0x180015db5  mov     edx, 5ABh; void *
0x180015dba  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180015dbf  mov     [rsp+0E8h+phNewTimer], r14
0x180015dc4  cmp     cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A, r14; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x180015dcb  jnz     short loc_180015E04
0x180015dcd  lea     rcx, [rsp+0E8h+var_78]
0x180015dd2  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>,>(void)
0x180015dd7  mov     rdx, [rax]
0x180015dda  mov     [rax], r14
0x180015ddd  mov     rcx, cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A; pv
0x180015de4  mov     cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A, rdx; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x180015deb  test    rcx, rcx
0x180015dee  jz      short loc_180015DF5
0x180015df0  call    ?Release@?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(void)
0x180015df5  mov     rcx, [rsp+0E8h+var_78]; pv
0x180015dfa  test    rcx, rcx
0x180015dfd  jz      short loc_180015E04
0x180015dff  call    ?Release@?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(void)
0x180015e04  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::`vftable'
0x180015e0b  mov     [rsp+0E8h+var_58], rax
0x180015e13  mov     [rsp+0E8h+var_50], r14
0x180015e1b  lea     rax, [rsp+0E8h+var_58]
0x180015e23  mov     [rsp+0E8h+var_48], rax
0x180015e2b  mov     [rsp+0E8h+var_40], r14
0x180015e33  mov     [rsp+0E8h+var_38], r14d
0x180015e3b  mov     [rsp+0E8h+var_30], r14
0x180015e43  mov     [rsp+0E8h+var_28], r14b
0x180015e4b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180015e52  jz      short loc_180015E93
0x180015e54  mov     dl, 1
0x180015e56  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180015e5b  mov     [rsp+0E8h+var_50], rax
0x180015e63  test    rax, rax
0x180015e66  jz      short loc_180015E9B
0x180015e68  mov     rcx, [rax]
0x180015e6b  mov     [rsp+0E8h+var_40], rcx
0x180015e73  lea     rcx, [rsp+0E8h+var_50]
0x180015e7b  mov     [rax], rcx
0x180015e7e  call    cs:__imp_GetCurrentThreadId
0x180015e85  nop     dword ptr [rax+rax+00h]
0x180015e8a  mov     [rsp+0E8h+var_38], eax
0x180015e91  jmp     short loc_180015E9B
0x180015e93  mov     [rsp+0E8h+var_50], r14
0x180015e9b  mov     rax, cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x180015ea2  mov     [rsp+0E8h+var_20], rax
0x180015eaa  test    rax, rax
0x180015ead  jz      short loc_180015EB6
0x180015eaf  lock inc dword ptr [rax+110h]
0x180015eb6  lea     rax, [rsp+0E8h+phNewTimer]
0x180015ebb  mov     [rsp+0E8h+var_90], rax
0x180015ec0  mov     [rsp+0E8h+var_88], 1
0x180015ec5  mov     rcx, rsi; this
0x180015ec8  call    ?DoWork@AOMDHandler@@AEAAJXZ; AOMDHandler::DoWork(void)
0x180015ecd  mov     dword ptr [rsp+0E8h+arg_8], eax
0x180015ed4  mov     rcx, [rsp+0E8h]; this
0x180015edc  test    eax, eax
0x180015ede  jns     short loc_180015EEF
0x180015ee0  mov     r9d, eax; char *
0x180015ee3  mov     edx, 5D6h; void *
0x180015ee8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015eed  jmp     short loc_180015EFF
0x180015eef  mov     eax, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180015ef5  nop
0x180015ef6  cmp     eax, 7
0x180015ef9  jnz     loc_180015FF0
0x180015eff  mov     qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180015f07  lea     rcx, [rsp+0E8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015f0f  call    cs:__imp_GetSystemTimeAsFileTime
0x180015f16  nop     dword ptr [rax+rax+00h]
0x180015f1b  cmp     dword ptr [rsi+50h], 1E8ABFD5h
0x180015f22  ja      short loc_180015F35
0x180015f24  mov     edi, [rsi+50h]
0x180015f27  mov     rax, 861C46800h
0x180015f31  imul    rdi, rax
0x180015f35  mov     ebx, [rsp+0E8h+SystemTimeAsFileTime.dwHighDateTime]
0x180015f3c  shl     rbx, 20h
0x180015f40  mov     eax, [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime]
0x180015f47  or      rbx, rax
0x180015f4a  add     rbx, rdi
0x180015f4d  mov     dword ptr [rsp+0E8h+Data], ebx
0x180015f54  mov     rax, rbx
0x180015f57  shr     rax, 20h
0x180015f5b  mov     dword ptr [rsp+0E8h+Data+4], eax
0x180015f62  mov     rax, [rsp+0E8h+Data]
0x180015f6a  mov     [rsp+0E8h+Data], rax
0x180015f72  lea     r8, [rsp+0E8h+Data]
0x180015f7a  lea     rdx, [rsp+0E8h+SystemTimeAsFileTime]
0x180015f82  call    ??$LogInfoFiletime@AEAY0CC@$$CBGAEAU_FILETIME@@U1@@TlgHelper@@SAXAEAY0CC@$$CBGAEAU_FILETIME@@$$QEAU1@@Z; TlgHelper::LogInfoFiletime<ushort const (&)[34],_FILETIME &,_FILETIME>(ushort const (&)[34],_FILETIME &,_FILETIME &&)
0x180015f87  mov     [rsp+0E8h+Data], rbx
0x180015f8f  mov     [rsp+0E8h+Period], 8; cbData
0x180015f97  lea     rax, [rsp+0E8h+Data]
0x180015f9f  mov     qword ptr [rsp+0E8h+DueTime], rax; int
0x180015fa4  mov     r9d, 0Bh; dwType
0x180015faa  lea     r8, aAomdselfthrott_0; "AOMDSelfThrottleEndTime"
0x180015fb1  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180015fb8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180015fbf  call    cs:__imp_RegSetKeyValueW
0x180015fc6  nop     dword ptr [rax+rax+00h]
0x180015fcb  test    eax, eax
0x180015fcd  jle     short loc_180015FD7
0x180015fcf  movzx   eax, ax
0x180015fd2  or      eax, 80070000h
0x180015fd7  mov     rcx, [rsp+0E8h]; this
0x180015fdf  test    eax, eax
0x180015fe1  jns     short loc_180015FF0
0x180015fe3  mov     r9d, eax; char *
0x180015fe6  mov     edx, 5F2h; void *
0x180015feb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015ff0  mov     ecx, cs:?g_aomdPromptResult@@3U?$atomic@W4AOMDPromptResult@@@std@@A; std::atomic<AOMDPromptResult> g_aomdPromptResult
0x180015ff6  nop
0x180015ff7  test    ecx, ecx
0x180015ff9  jz      loc_1800160DC
0x180015fff  mov     eax, [rsi+80h]
0x180016005  mov     [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18001600c  mov     rax, [rsi+78h]
0x180016010  mov     dword ptr [rsp+0E8h+Data], eax
0x180016017  shr     rax, 20h
0x18001601b  mov     dword ptr [rsp+0E8h+Data+4], eax
0x180016022  mov     rax, [rsp+0E8h+Data]
0x18001602a  mov     [rsp+0E8h+var_70], rax
0x18001602f  mov     rax, [rsi+68h]
0x180016033  mov     dword ptr [rsp+0E8h+Data], eax
0x18001603a  shr     rax, 20h
0x18001603e  mov     dword ptr [rsp+0E8h+Data+4], eax
0x180016045  mov     rax, [rsp+0E8h+Data]
0x18001604d  mov     [rsp+0E8h+var_68], rax
0x180016055  mov     eax, [rsi+70h]
0x180016058  mov     dword ptr [rsp+0E8h+Data], eax
0x18001605f  mov     rax, [rsi+60h]
0x180016063  mov     dword ptr [rsp+0E8h+var_A0], eax
0x180016067  shr     rax, 20h
0x18001606b  mov     dword ptr [rsp+0E8h+var_A0+4], eax
0x18001606f  mov     rax, [rsp+0E8h+var_A0]
0x180016074  mov     [rsp+0E8h+var_60], rax
0x18001607c  mov     eax, cs:?g_mainToastSetting@@3U?$atomic@W4MainToastNotificationSetting@@@std@@A; std::atomic<MainToastNotificationSetting> g_mainToastSetting
0x180016082  nop
0x180016083  mov     [rsp+0E8h+var_A8], eax
0x180016087  mov     [rsp+0E8h+var_A4], ecx
0x18001608b  lea     rax, [rsp+0E8h+SystemTimeAsFileTime]
0x180016093  mov     [rsp+0E8h+var_B0], rax
0x180016098  lea     rax, [rsp+0E8h+var_70]
0x18001609d  mov     qword ptr [rsp+0E8h+Flags], rax
0x1800160a2  lea     rax, [rsp+0E8h+var_68]
0x1800160aa  mov     qword ptr [rsp+0E8h+Period], rax
0x1800160af  lea     rax, [rsp+0E8h+Data]
0x1800160b7  mov     qword ptr [rsp+0E8h+DueTime], rax
0x1800160bc  lea     r9, [rsp+0E8h+var_60]
0x1800160c4  lea     r8, [rsp+0E8h+arg_8]
0x1800160cc  lea     rdx, [rsp+0E8h+var_A8]
0x1800160d1  lea     rcx, [rsp+0E8h+var_A4]
0x1800160d6  call    ??$AOMDEscalationStatus@IIAEBJU_FILETIME@@IU1@U1@I@TlgHelper@@SAX$$QEAI0AEBJ$$QEAU_FILETIME@@0220@Z; TlgHelper::AOMDEscalationStatus<uint,uint,long const &,_FILETIME,uint,_FILETIME,_FILETIME,uint>(uint &&,uint &&,long const &,_FILETIME &&,uint &&,_FILETIME &&,_FILETIME &&,uint &&)
0x1800160db  nop
0x1800160dc  mov     [rsp+0E8h+var_88], r14b
0x1800160e1  lea     rcx, [rsp+0E8h+var_90]
0x1800160e6  call    _lambda_312d26372c3169cab680c6a412e6d847___operator__
0x1800160eb  nop
0x1800160ec  mov     rcx, [rsp+0E8h+var_20]; pv
0x1800160f4  test    rcx, rcx
0x1800160f7  jz      short loc_1800160FE
0x1800160f9  call    ?Release@?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(void)
0x1800160fe  lea     rcx, [rsp+0E8h+var_50]; this
0x180016106  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001610b  mov     eax, dword ptr [rsp+0E8h+arg_8]
0x180016112  jmp     short loc_18001611B
0x180016114  mov     eax, dword ptr [rsp+0E8h+arg_8]
0x18001611b  mov     rbx, [rsp+0E8h+arg_0]
0x180016123  add     rsp, 0D0h
0x18001612a  pop     r14
0x18001612c  pop     rdi
0x18001612d  pop     rsi
0x18001612e  retn
```
