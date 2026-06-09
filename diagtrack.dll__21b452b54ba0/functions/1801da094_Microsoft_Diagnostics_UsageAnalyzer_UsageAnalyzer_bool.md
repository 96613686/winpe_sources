# Microsoft::Diagnostics::UsageAnalyzer::UsageAnalyzer(bool)

- ea: `0x1801da094`
- end: `0x1801da6f0`
- name: `??0UsageAnalyzer@Diagnostics@Microsoft@@QEAA@_N@Z`
- size: `1628`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UsageAnalyzer *__hidden this, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802549f8`

## callees

- `0x180039e6c`
- `0x18005d660`
- `0x18008f3ec`
- `0x1800d39fc`
- `0x1800e8f80`
- `0x180105a18`
- `0x1801a42f8`
- `0x1801b2084`
- `0x1801b4ce0`
- `0x1801b6520`
- `0x1801b7980`
- `0x1801d0d84`
- `0x1801da094`
- `0x1801dfd64`
- `0x18020aac0`
- `0x18025f094`
- `0x180300a00`
- `0x180300a4c`
- `0x180302908`
- `0x180302b40`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801da57c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801da5aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801da5d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801da57c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801da5aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801da5d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801da678`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801da678`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801da101`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801da1b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801da101`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801da1b7`

## string_xrefs

- `0x1801da6ba`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x1801da6cc`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x1801da6de`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
Microsoft::Diagnostics::UsageAnalyzer *__fastcall Microsoft::Diagnostics::UsageAnalyzer::UsageAnalyzer(
        Microsoft::Diagnostics::UsageAnalyzer *this)
{
  _QWORD *v2; // rax
  size_t size_of; // rax
  _QWORD *v4; // rax
  __int64 RegistryConfig; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v7; // r9
  PTP_TIMER v8; // rax
  const char *v9; // r9
  PTP_TIMER v10; // rax
  const char *v11; // r9
  __int64 v12; // rax
  __int64 v13; // rbx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h]
  __int128 v18; // [rsp+50h] [rbp-B0h] BYREF
  Microsoft::Diagnostics::UsageAnalyzer *v19; // [rsp+60h] [rbp-A0h]
  _BYTE v20[224]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v19 = this;
  Microsoft::Diagnostics::ProcessStateEventBasedMetadata::ProcessStateEventBasedMetadata(this);
  *(_QWORD *)this = &Microsoft::Diagnostics::UsageAnalyzer::`vftable'{for `Microsoft::Diagnostics::ProcessStateEventBasedMetadata'};
  *((_QWORD *)this + 20) = &Microsoft::Diagnostics::UsageAnalyzer::`vftable'{for `Microsoft::Diagnostics::IRundownProducer'};
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 2 * GetTickCount64();
  *((_QWORD *)this + 25) = 258;
  *((_OWORD *)this + 14) = 0;
  *((_OWORD *)this + 15) = 0;
  *((_OWORD *)this + 16) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 68) = -1;
  *((_DWORD *)this + 69) = 0;
  Microsoft::Diagnostics::UsageAnalyzer::ScenarioStats::ScenarioStats((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 280));
  *((_QWORD *)this + 41) = 258;
  *((_OWORD *)this + 22) = 0;
  *((_OWORD *)this + 23) = 0;
  *((_OWORD *)this + 24) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_DWORD *)this + 100) = -1;
  *((_DWORD *)this + 101) = 0;
  Microsoft::Diagnostics::UsageAnalyzer::DerivedEventStats::DerivedEventStats((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 408));
  *((_QWORD *)this + 71) = 0;
  *((_BYTE *)this + 576) = 0;
  *((_QWORD *)this + 73) = GetTickCount64();
  *((_QWORD *)this + 74) = 258;
  *(_OWORD *)((char *)this + 616) = 0;
  *(_OWORD *)((char *)this + 632) = 0;
  *(_OWORD *)((char *)this + 648) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_DWORD *)this + 166) = -1;
  *((_DWORD *)this + 167) = 0;
  pftDueTime = (struct _FILETIME)((char *)this + 672);
  *((_DWORD *)this + 168) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  v2 = std::_Allocate<16,std::_Default_allocate_traits>(0x40u);
  *v2 = v2;
  v2[1] = v2;
  *((_QWORD *)this + 85) = v2;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 7;
  *((_QWORD *)this + 91) = 8;
  *((_DWORD *)this + 168) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,Microsoft::Diagnostics::AppIdMetadata::SessionInfo>>>>>>::_Assign_grow(
    (char *)this + 696,
    16,
    *((_QWORD *)this + 85));
  *((_QWORD *)this + 92) = 258;
  *(_OWORD *)((char *)this + 760) = 0;
  *(_OWORD *)((char *)this + 776) = 0;
  *(_OWORD *)((char *)this + 792) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 101) = 0xFFFFFFFFLL;
  Microsoft::Diagnostics::UsageAnalyzer::AggregatedAsimovData::AggregatedAsimovData((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 816));
  *((_QWORD *)this + 106) = 258;
  *(_OWORD *)((char *)this + 872) = 0;
  *(_OWORD *)((char *)this + 888) = 0;
  *(_OWORD *)((char *)this + 904) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 108) = 0;
  *((_DWORD *)this + 230) = -1;
  *((_DWORD *)this + 231) = 0;
  Microsoft::Diagnostics::UsageAnalyzer::ReportScenarioStats::ReportScenarioStats((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 928));
  *((_QWORD *)this + 121) = 258;
  *((_OWORD *)this + 62) = 0;
  *((_OWORD *)this + 63) = 0;
  *((_OWORD *)this + 64) = 0;
  *((_QWORD *)this + 122) = 0;
  *((_QWORD *)this + 123) = 0;
  *((_DWORD *)this + 260) = -1;
  *((_DWORD *)this + 261) = 0;
  *((_QWORD *)this + 131) = 0;
  *((_QWORD *)this + 132) = 0;
  size_of = std::_Get_size_of_n<72>(1);
  v4 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  *((_QWORD *)this + 131) = v4;
  pftDueTime.dwLowDateTime = 0;
  v16 = L"PersistInprocInfo";
  v17 = 17;
  v18 = *(_OWORD *)&off_18036D328;
  RegistryConfig = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
                     (unsigned int)v20,
                     (unsigned int)&pftDueTime,
                     (unsigned int)&v18,
                     (unsigned int)&v16,
                     0);
  *((_DWORD *)this + 266) = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(RegistryConfig);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v20);
  *((_QWORD *)this + 134) = 258;
  *(_OWORD *)((char *)this + 1096) = 0;
  *(_OWORD *)((char *)this + 1112) = 0;
  *(_OWORD *)((char *)this + 1128) = 0;
  *((_QWORD *)this + 135) = 0;
  *((_QWORD *)this + 136) = 0;
  *((_DWORD *)this + 286) = -1;
  *((_DWORD *)this + 287) = 0;
  *((_QWORD *)this + 144) = 0;
  *((_QWORD *)this + 145) = 0;
  *((_QWORD *)this + 146) = 0;
  *((_QWORD *)this + 147) = 258;
  *((_OWORD *)this + 75) = 0;
  *((_OWORD *)this + 76) = 0;
  *((_OWORD *)this + 77) = 0;
  *((_QWORD *)this + 148) = 0;
  *((_QWORD *)this + 149) = 0;
  *((_DWORD *)this + 312) = -1;
  *((_DWORD *)this + 313) = 0;
  *((_QWORD *)this + 157) = 258;
  *((_OWORD *)this + 80) = 0;
  *((_OWORD *)this + 81) = 0;
  *((_OWORD *)this + 82) = 0;
  *((_QWORD *)this + 158) = 0;
  *((_QWORD *)this + 159) = 0;
  *((_DWORD *)this + 332) = -1;
  *((_DWORD *)this + 333) = 0;
  *((_QWORD *)this + 167) = 0;
  *((_QWORD *)this + 168) = -1;
  *((_QWORD *)this + 169) = 0;
  *((_QWORD *)this + 170) = 0;
  *((_QWORD *)this + 171) = 0;
  *((_QWORD *)this + 172) = 0;
  *((_QWORD *)this + 173) = -1;
  *((_QWORD *)this + 174) = 0;
  *((_QWORD *)this + 175) = 0;
  *((_QWORD *)this + 176) = 0;
  *((_QWORD *)this + 177) = 0;
  *((_QWORD *)this + 178) = -1;
  *((_QWORD *)this + 179) = 0;
  *((_QWORD *)this + 180) = 0;
  *((_QWORD *)this + 181) = 0;
  *((_QWORD *)this + 182) = 0;
  *((_QWORD *)this + 183) = 0;
  *((_QWORD *)this + 184) = 0;
  *((_QWORD *)this + 185) = 0;
  *((_QWORD *)this + 186) = 0;
  *((_QWORD *)this + 187) = 0;
  *((_QWORD *)this + 188) = Microsoft::Diagnostics::Utils::Time::QueryUbiTime();
  *((_QWORD *)this + 189) = 0;
  *((_QWORD *)this + 190) = 0;
  *((_QWORD *)this + 191) = 0;
  *((_QWORD *)this + 190) = std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>>>();
  *((_QWORD *)this + 192) = 0;
  *((_QWORD *)this + 193) = 0;
  *((_QWORD *)this + 194) = 0;
  *((_BYTE *)this + 1560) = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(
                      Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::UsageAnalyzer,{public: void Microsoft::Diagnostics::UsageAnalyzer::ClearReportState(void),0}>,
                      this,
                      0);
  if ( !ThreadpoolTimer )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
      v7);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 176,
    ThreadpoolTimer);
  v8 = CreateThreadpoolTimer(
         Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::UsageAnalyzer,{private: void Microsoft::Diagnostics::UsageAnalyzer::LogStatsToSynthetic(void),0}>,
         this,
         0);
  if ( !v8 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
      v9);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 168,
    v8);
  v10 = CreateThreadpoolTimer(
          Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::UsageAnalyzer const,{[thunk]: Microsoft::Diagnostics::UsageAnalyzer::`vcall'{8,{flat}},160}>,
          this,
          0);
  if ( !v10 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
      v11);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 184,
    v10);
  pftDueTime.dwLowDateTime = 0;
  v16 = L"UsageAnalyzerTimer_DoCaptureState";
  v17 = 33;
  v18 = *(_OWORD *)&off_18036D328;
  v12 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateRegistryConfig(
          (unsigned int)v20,
          (unsigned int)&pftDueTime,
          (unsigned int)&v18,
          (unsigned int)&v16,
          0);
  v13 = (unsigned int)Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v12);
  Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v20);
  if ( (_DWORD)v13 )
  {
    pftDueTime = (struct _FILETIME)(-10000 * v13);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 23), &pftDueTime, v13, 0x2710u);
  }
  Microsoft::Diagnostics::UsageAnalyzer::RefreshReportEnabled(this);
  Microsoft::Diagnostics::UsageAnalyzer::RearmLogStatsToSyntheticTimer(this);
  Microsoft::Diagnostics::ProcessStateEventBasedMetadata::RegisterForAppStateChangeEvents(this);
  return this;
}

```

## disassembly

```asm
0x1801da094  push    rbp
0x1801da096  push    rbx
0x1801da097  push    rsi
0x1801da098  push    rdi
0x1801da099  push    r12
0x1801da09b  push    r13
0x1801da09d  push    r14
0x1801da09f  push    r15
0x1801da0a1  lea     rbp, [rsp-68h]
0x1801da0a6  sub     rsp, 168h
0x1801da0ad  mov     rax, cs:__security_cookie
0x1801da0b4  xor     rax, rsp
0x1801da0b7  mov     [rbp+0A0h+var_50], rax
0x1801da0bb  mov     rdi, rcx
0x1801da0be  mov     [rsp+1A0h+var_140], rcx
0x1801da0c3  call    ??0ProcessStateEventBasedMetadata@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ProcessStateEventBasedMetadata::ProcessStateEventBasedMetadata(void)
0x1801da0c8  nop
0x1801da0c9  lea     rax, ??_7UsageAnalyzer@Diagnostics@Microsoft@@6BProcessStateEventBasedMetadata@12@@; const Microsoft::Diagnostics::UsageAnalyzer::`vftable'{for `Microsoft::Diagnostics::ProcessStateEventBasedMetadata'}
0x1801da0d0  mov     [rdi], rax
0x1801da0d3  lea     rax, ??_7UsageAnalyzer@Diagnostics@Microsoft@@6BIRundownProducer@12@@; const Microsoft::Diagnostics::UsageAnalyzer::`vftable'{for `Microsoft::Diagnostics::IRundownProducer'}
0x1801da0da  mov     [rdi+0A0h], rax
0x1801da0e1  lea     r14, [rdi+0A8h]
0x1801da0e8  xor     ebx, ebx
0x1801da0ea  mov     [r14], rbx
0x1801da0ed  lea     rsi, [rdi+0B0h]
0x1801da0f4  mov     [rsi], rbx
0x1801da0f7  lea     r15, [rdi+0B8h]
0x1801da0fe  mov     [r15], rbx
0x1801da101  call    cs:__imp_GetTickCount64
0x1801da107  add     rax, rax
0x1801da10a  mov     [rdi+0C0h], rax
0x1801da111  mov     qword ptr [rdi+0C8h], 102h
0x1801da11c  xorps   xmm0, xmm0
0x1801da11f  movups  xmmword ptr [rdi+0E0h], xmm0
0x1801da126  movups  xmmword ptr [rdi+0F0h], xmm0
0x1801da12d  movups  xmmword ptr [rdi+100h], xmm0
0x1801da134  mov     [rdi+0D0h], rbx
0x1801da13b  mov     [rdi+0D8h], rbx
0x1801da142  or      r13, 0FFFFFFFFFFFFFFFFh
0x1801da146  mov     [rdi+110h], r13d
0x1801da14d  mov     [rdi+114h], ebx
0x1801da153  lea     rcx, [rdi+118h]; this
0x1801da15a  call    ??0ScenarioStats@UsageAnalyzer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UsageAnalyzer::ScenarioStats::ScenarioStats(void)
0x1801da15f  nop
0x1801da160  mov     qword ptr [rdi+148h], 102h
0x1801da16b  xorps   xmm0, xmm0
0x1801da16e  movups  xmmword ptr [rdi+160h], xmm0
0x1801da175  movups  xmmword ptr [rdi+170h], xmm0
0x1801da17c  movups  xmmword ptr [rdi+180h], xmm0
0x1801da183  mov     [rdi+150h], rbx
0x1801da18a  mov     [rdi+158h], rbx
0x1801da191  mov     [rdi+190h], r13d
0x1801da198  mov     [rdi+194h], ebx
0x1801da19e  lea     rcx, [rdi+198h]; this
0x1801da1a5  call    ??0DerivedEventStats@UsageAnalyzer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UsageAnalyzer::DerivedEventStats::DerivedEventStats(void)
0x1801da1aa  mov     [rdi+238h], rbx
0x1801da1b1  mov     [rdi+240h], bl
0x1801da1b7  call    cs:__imp_GetTickCount64
0x1801da1bd  mov     [rdi+248h], rax
0x1801da1c4  mov     qword ptr [rdi+250h], 102h
0x1801da1cf  xorps   xmm0, xmm0
0x1801da1d2  movups  xmmword ptr [rdi+268h], xmm0
0x1801da1d9  movups  xmmword ptr [rdi+278h], xmm0
0x1801da1e0  movups  xmmword ptr [rdi+288h], xmm0
0x1801da1e7  mov     [rdi+258h], rbx
0x1801da1ee  mov     [rdi+260h], rbx
0x1801da1f5  mov     [rdi+298h], r13d
0x1801da1fc  mov     [rdi+29Ch], ebx
0x1801da202  lea     rbx, [rdi+2A0h]
0x1801da209  mov     qword ptr [rsp+1A0h+pftDueTime.dwLowDateTime], rbx
0x1801da20e  xor     eax, eax
0x1801da210  mov     [rbx], eax
0x1801da212  mov     [rbx+8], rax
0x1801da216  mov     [rbx+10h], rax
0x1801da21a  lea     ecx, [rax+40h]
0x1801da21d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1801da222  mov     [rax], rax
0x1801da225  mov     [rax+8], rax
0x1801da229  mov     [rbx+8], rax
0x1801da22d  lea     rcx, [rbx+18h]
0x1801da231  xor     eax, eax
0x1801da233  mov     [rcx], rax
0x1801da236  mov     [rcx+8], rax
0x1801da23a  mov     [rcx+10h], rax
0x1801da23e  mov     qword ptr [rbx+30h], 7
0x1801da246  mov     qword ptr [rbx+38h], 8
0x1801da24e  mov     dword ptr [rbx], 3F800000h
0x1801da254  mov     r8, [rbx+8]
0x1801da258  lea     edx, [rax+10h]
0x1801da25b  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUSessionInfo@AppIdMetadata@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUSessionInfo@AppIdMetadata@Diagnostics@Microsoft@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,Microsoft::Diagnostics::AppIdMetadata::SessionInfo>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,Microsoft::Diagnostics::AppIdMetadata::SessionInfo>>>>)
0x1801da260  nop
0x1801da261  mov     qword ptr [rdi+2E0h], 102h
0x1801da26c  xorps   xmm0, xmm0
0x1801da26f  movups  xmmword ptr [rdi+2F8h], xmm0
0x1801da276  movups  xmmword ptr [rdi+308h], xmm0
0x1801da27d  movups  xmmword ptr [rdi+318h], xmm0
0x1801da284  xor     ebx, ebx
0x1801da286  mov     [rdi+2E8h], rbx
0x1801da28d  mov     [rdi+2F0h], rbx
0x1801da294  mov     [rdi+328h], r13d
0x1801da29b  mov     [rdi+32Ch], ebx
0x1801da2a1  lea     rcx, [rdi+330h]; this
0x1801da2a8  call    ??0AggregatedAsimovData@UsageAnalyzer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UsageAnalyzer::AggregatedAsimovData::AggregatedAsimovData(void)
0x1801da2ad  nop
0x1801da2ae  mov     qword ptr [rdi+350h], 102h
0x1801da2b9  xorps   xmm0, xmm0
0x1801da2bc  movups  xmmword ptr [rdi+368h], xmm0
0x1801da2c3  movups  xmmword ptr [rdi+378h], xmm0
0x1801da2ca  movups  xmmword ptr [rdi+388h], xmm0
0x1801da2d1  mov     [rdi+358h], rbx
0x1801da2d8  mov     [rdi+360h], rbx
0x1801da2df  mov     [rdi+398h], r13d
0x1801da2e6  mov     [rdi+39Ch], ebx
0x1801da2ec  lea     rcx, [rdi+3A0h]; this
0x1801da2f3  call    ??0ReportScenarioStats@UsageAnalyzer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UsageAnalyzer::ReportScenarioStats::ReportScenarioStats(void)
0x1801da2f8  nop
0x1801da2f9  mov     qword ptr [rdi+3C8h], 102h
0x1801da304  xorps   xmm0, xmm0
0x1801da307  movups  xmmword ptr [rdi+3E0h], xmm0
0x1801da30e  movups  xmmword ptr [rdi+3F0h], xmm0
0x1801da315  movups  xmmword ptr [rdi+400h], xmm0
0x1801da31c  mov     [rdi+3D0h], rbx
0x1801da323  mov     [rdi+3D8h], rbx
0x1801da32a  mov     [rdi+410h], r13d
0x1801da331  mov     [rdi+414h], ebx
0x1801da337  lea     rbx, [rdi+418h]
0x1801da33e  xor     eax, eax
0x1801da340  mov     [rbx], rax
0x1801da343  mov     [rbx+8], rax
0x1801da347  lea     ecx, [rax+1]
0x1801da34a  call    ??$_Get_size_of_n@$0EI@@std@@YA_K_K@Z; std::_Get_size_of_n<72>(unsigned __int64)
0x1801da34f  mov     rcx, rax
0x1801da352  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1801da357  mov     [rax], rax
0x1801da35a  mov     [rax+8], rax
0x1801da35e  mov     [rax+10h], rax
0x1801da362  mov     word ptr [rax+18h], 101h
0x1801da368  mov     [rbx], rax
0x1801da36b  xor     ebx, ebx
0x1801da36d  mov     [rsp+1A0h+pftDueTime.dwLowDateTime], ebx
0x1801da371  lea     rax, aPersistinproci; "PersistInprocInfo"
0x1801da378  mov     [rsp+1A0h+var_160], rax
0x1801da37d  mov     [rsp+1A0h+var_158], 11h
0x1801da386  movups  xmm0, xmmword ptr cs:off_18036D328; "%DiagtrackRegistryRoot%\\UsageAnalyzer"
0x1801da38d  movdqu  [rsp+1A0h+var_150], xmm0
0x1801da393  mov     [rsp+1A0h+var_180], bl
0x1801da397  lea     r9, [rsp+1A0h+var_160]
0x1801da39c  lea     r8, [rsp+1A0h+var_150]
0x1801da3a1  lea     rdx, [rsp+1A0h+pftDueTime]
0x1801da3a6  lea     rcx, [rsp+1A0h+var_130]
0x1801da3ab  call    ?CreateRegistryConfig@?$DynamicConfig@K@Diagnostics@Microsoft@@SA?AV123@AEBKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_N@Z; Microsoft::Diagnostics::DynamicConfig<ulong>::CreateRegistryConfig(ulong const &,std::wstring_view,std::wstring_view,bool)
0x1801da3b0  nop
0x1801da3b1  mov     rcx, rax
0x1801da3b4  call    ?Get@?$DynamicConfig@K@Diagnostics@Microsoft@@QEBAKXZ; Microsoft::Diagnostics::DynamicConfig<ulong>::Get(void)
0x1801da3b9  mov     [rdi+428h], eax
0x1801da3bf  lea     rcx, [rsp+1A0h+var_130]
0x1801da3c4  call    ??1?$DynamicConfig@K@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::DynamicConfig<ulong>::~DynamicConfig<ulong>(void)
0x1801da3c9  mov     qword ptr [rdi+430h], 102h
0x1801da3d4  xorps   xmm0, xmm0
0x1801da3d7  movups  xmmword ptr [rdi+448h], xmm0
0x1801da3de  movups  xmmword ptr [rdi+458h], xmm0
0x1801da3e5  movups  xmmword ptr [rdi+468h], xmm0
0x1801da3ec  mov     [rdi+438h], rbx
0x1801da3f3  mov     [rdi+440h], rbx
0x1801da3fa  mov     [rdi+478h], r13d
0x1801da401  mov     [rdi+47Ch], ebx
0x1801da407  mov     [rdi+480h], rbx
0x1801da40e  mov     [rdi+488h], rbx
0x1801da415  mov     [rdi+490h], rbx
0x1801da41c  mov     qword ptr [rdi+498h], 102h
0x1801da427  movups  xmmword ptr [rdi+4B0h], xmm0
0x1801da42e  movups  xmmword ptr [rdi+4C0h], xmm0
0x1801da435  movups  xmmword ptr [rdi+4D0h], xmm0
0x1801da43c  mov     [rdi+4A0h], rbx
0x1801da443  mov     [rdi+4A8h], rbx
0x1801da44a  mov     [rdi+4E0h], r13d
0x1801da451  mov     [rdi+4E4h], ebx
0x1801da457  mov     qword ptr [rdi+4E8h], 102h
0x1801da462  movups  xmmword ptr [rdi+500h], xmm0
0x1801da469  movups  xmmword ptr [rdi+510h], xmm0
0x1801da470  movups  xmmword ptr [rdi+520h], xmm0
0x1801da477  mov     [rdi+4F0h], rbx
0x1801da47e  mov     [rdi+4F8h], rbx
0x1801da485  mov     [rdi+530h], r13d
0x1801da48c  mov     [rdi+534h], ebx
0x1801da492  mov     [rdi+538h], rbx
0x1801da499  mov     [rdi+540h], r13
0x1801da4a0  mov     [rdi+548h], rbx
0x1801da4a7  mov     [rdi+550h], rbx
0x1801da4ae  mov     [rdi+558h], rbx
0x1801da4b5  mov     [rdi+560h], rbx
0x1801da4bc  mov     [rdi+568h], r13
0x1801da4c3  mov     [rdi+570h], rbx
0x1801da4ca  mov     [rdi+578h], rbx
0x1801da4d1  mov     [rdi+580h], rbx
0x1801da4d8  mov     [rdi+588h], rbx
0x1801da4df  mov     [rdi+590h], r13
0x1801da4e6  mov     [rdi+598h], rbx
0x1801da4ed  mov     [rdi+5A0h], rbx
0x1801da4f4  mov     [rdi+5A8h], rbx
0x1801da4fb  mov     [rdi+5B0h], rbx
0x1801da502  mov     [rdi+5B8h], rbx
0x1801da509  mov     [rdi+5C0h], rbx
0x1801da510  mov     [rdi+5C8h], rbx
0x1801da517  mov     [rdi+5D0h], rbx
0x1801da51e  mov     [rdi+5D8h], rbx
0x1801da525  call    ?QueryUbiTime@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::QueryUbiTime(void)
0x1801da52a  mov     [rdi+5E0h], rax
0x1801da531  lea     rax, [rdi+5E8h]
0x1801da538  mov     [rax], rbx
0x1801da53b  lea     rbx, [rax+8]
0x1801da53f  xor     r12d, r12d
0x1801da542  mov     [rbx], r12
0x1801da545  mov     [rbx+8], r12
0x1801da549  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>> &)
0x1801da54e  mov     [rbx], rax
0x1801da551  xor     eax, eax
0x1801da553  mov     [rdi+600h], rax
0x1801da55a  mov     [rdi+608h], rax
0x1801da561  mov     [rdi+610h], r12
0x1801da568  mov     [rdi+618h], r12b
0x1801da56f  xor     r8d, r8d; pcbe
0x1801da572  mov     rdx, rdi; pv
0x1801da575  lea     rcx, ??$MethodToTpTimerCallbackAdapter@VUsageAnalyzer@Diagnostics@Microsoft@@$H?ClearReportState@123@QEAAXXZA@@Os@Utils@Diagnostics@Microsoft@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1801da57c  call    cs:__imp_CreateThreadpoolTimer
0x1801da582  mov     rcx, [rbp+0A8h]; this
0x1801da589  test    rax, rax
0x1801da58c  jz      loc_1801DA6CC
0x1801da592  mov     rdx, rax
0x1801da595  mov     rcx, rsi
0x1801da598  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801da59d  xor     r8d, r8d; pcbe
0x1801da5a0  mov     rdx, rdi; pv
0x1801da5a3  lea     rcx, ??$MethodToTpTimerCallbackAdapter@VUsageAnalyzer@Diagnostics@Microsoft@@$H?LogStatsToSynthetic@123@AEAAXXZA@@Os@Utils@Diagnostics@Microsoft@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1801da5aa  call    cs:__imp_CreateThreadpoolTimer
0x1801da5b0  mov     rcx, [rbp+0A8h]; this
0x1801da5b7  test    rax, rax
0x1801da5ba  jz      loc_1801DA6DE
0x1801da5c0  mov     rdx, rax
0x1801da5c3  mov     rcx, r14
0x1801da5c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801da5cb  xor     r8d, r8d; pcbe
0x1801da5ce  mov     rdx, rdi; pv
0x1801da5d1  lea     rcx, ??$MethodToTpTimerCallbackAdapter@$$CBVUsageAnalyzer@Diagnostics@Microsoft@@$H??_9123@$B7AAKA@@Os@Utils@Diagnostics@Microsoft@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1801da5d8  call    cs:__imp_CreateThreadpoolTimer
0x1801da5de  mov     rcx, [rbp+0A8h]; this
0x1801da5e5  test    rax, rax
0x1801da5e8  jz      loc_1801DA6BA
0x1801da5ee  mov     rdx, rax
0x1801da5f1  mov     rcx, r15
0x1801da5f4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1801da5f9  mov     [rsp+1A0h+pftDueTime.dwLowDateTime], r12d
0x1801da5fe  lea     rax, aUsageanalyzert_1; "UsageAnalyzerTimer_DoCaptureState"
0x1801da605  mov     [rsp+1A0h+var_160], rax
0x1801da60a  mov     [rsp+1A0h+var_158], 21h ; '!'
0x1801da613  movups  xmm0, xmmword ptr cs:off_18036D328; "%DiagtrackRegistryRoot%\\UsageAnalyzer"
0x1801da61a  movdqu  [rsp+1A0h+var_150], xmm0
0x1801da620  mov     [rsp+1A0h+var_180], r12b
0x1801da625  lea     r9, [rsp+1A0h+var_160]
0x1801da62a  lea     r8, [rsp+1A0h+var_150]
0x1801da62f  lea     rdx, [rsp+1A0h+pftDueTime]
0x1801da634  lea     rcx, [rsp+1A0h+var_130]
0x1801da639  call    ?CreateRegistryConfig@?$DynamicConfig@K@Diagnostics@Microsoft@@SA?AV123@AEBKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1_N@Z; Microsoft::Diagnostics::DynamicConfig<ulong>::CreateRegistryConfig(ulong const &,std::wstring_view,std::wstring_view,bool)
0x1801da63e  nop
0x1801da63f  mov     rcx, rax
0x1801da642  call    ?Get@?$DynamicConfig@K@Diagnostics@Microsoft@@QEBAKXZ; Microsoft::Diagnostics::DynamicConfig<ulong>::Get(void)
0x1801da647  mov     ebx, eax
0x1801da649  lea     rcx, [rsp+1A0h+var_130]
0x1801da64e  call    ??1?$DynamicConfig@K@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::DynamicConfig<ulong>::~DynamicConfig<ulong>(void)
0x1801da653  test    ebx, ebx
0x1801da655  jz      short loc_1801DA67E
0x1801da657  imul    rdx, rbx, 0FFFFFFFFFFFFD8F0h
0x1801da65e  mov     qword ptr [rsp+1A0h+pftDueTime.dwLowDateTime], rdx
0x1801da663  mov     r9d, 2710h; msWindowLength
0x1801da669  mov     r8d, ebx; msPeriod
0x1801da66c  lea     rdx, [rsp+1A0h+pftDueTime]; pftDueTime
0x1801da671  mov     rcx, [rdi+0B8h]; pti
0x1801da678  call    cs:__imp_SetThreadpoolTimer
0x1801da67e  mov     rcx, rdi; this
0x1801da681  call    ?RefreshReportEnabled@UsageAnalyzer@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::UsageAnalyzer::RefreshReportEnabled(void)
0x1801da686  mov     rcx, rdi; this
0x1801da689  call    ?RearmLogStatsToSyntheticTimer@UsageAnalyzer@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::UsageAnalyzer::RearmLogStatsToSyntheticTimer(void)
0x1801da68e  mov     rcx, rdi; this
0x1801da691  call    ?RegisterForAppStateChangeEvents@ProcessStateEventBasedMetadata@Diagnostics@Microsoft@@IEAAXXZ; Microsoft::Diagnostics::ProcessStateEventBasedMetadata::RegisterForAppStateChangeEvents(void)
0x1801da696  nop
0x1801da697  mov     rax, rdi
0x1801da69a  mov     rcx, [rbp+0A0h+var_50]
0x1801da69e  xor     rcx, rsp; StackCookie
0x1801da6a1  call    __security_check_cookie
0x1801da6a6  add     rsp, 168h
0x1801da6ad  pop     r15
0x1801da6af  pop     r14
0x1801da6b1  pop     r13
0x1801da6b3  pop     r12
0x1801da6b5  pop     rdi
0x1801da6b6  pop     rsi
0x1801da6b7  pop     rbx
0x1801da6b8  pop     rbp
0x1801da6b9  retn
0x1801da6ba  lea     r8, aOnecoreBaseTel_151; "onecore\\base\\telemetry\\utc\\service"...
  ... truncated ...
```
