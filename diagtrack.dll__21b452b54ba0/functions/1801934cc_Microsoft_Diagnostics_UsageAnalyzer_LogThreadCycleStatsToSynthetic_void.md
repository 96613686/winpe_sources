# Microsoft::Diagnostics::UsageAnalyzer::LogThreadCycleStatsToSynthetic(void)

- ea: `0x1801934cc`
- end: `0x180193ceb`
- name: `?LogThreadCycleStatsToSynthetic@UsageAnalyzer@Diagnostics@Microsoft@@AEAAXXZ`
- size: `2079`
- prototype: `void __fastcall(Microsoft::Diagnostics::UsageAnalyzer *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180257ea0`

## callees

- `0x18001e228`
- `0x18002df00`
- `0x180049c98`
- `0x180049d00`
- `0x180055730`
- `0x18005d660`
- `0x18005fb44`
- `0x18008a51c`
- `0x18008a580`
- `0x18008a5d8`
- `0x1800b47f0`
- `0x180111f9c`
- `0x18013c164`
- `0x1801934cc`
- `0x18020aac0`
- `0x180259984`
- `0x180301708`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180193c8d`
- `msvcp_win!_Mtx_unlock` at `0x180193c8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180193663`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180193727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180193663`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180193727`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1801938f4`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1801939aa`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180193a48`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1801938f4`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1801939aa`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180193a48`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18019373a`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x18019373a`

## string_xrefs

- `0x180193aa3`: `ConsumerThreadOverheadKCy`
- `0x1801938b9`: `UpdateRulesCy`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::Diagnostics::UsageAnalyzer::LogThreadCycleStatsToSynthetic(
        Microsoft::Diagnostics::UsageAnalyzer *this)
{
  unsigned __int64 UbiTime; // rdi
  __int64 Cpu0Name; // rax
  __int64 Cpu0Identifier; // rax
  HANDLE CurrentProcess; // rax
  unsigned __int64 v6; // r8
  double v7; // xmm0_8
  double v8; // xmm0_8
  double v9; // xmm1_8
  HANDLE v10; // rax
  unsigned __int64 v11; // rdi
  __int64 v12; // rcx
  double v13; // xmm0_8
  double v14; // xmm0_8
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // r15
  __int64 v17; // rcx
  double v18; // xmm0_8
  double v19; // xmm0_8
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // rsi
  void *v23; // rcx
  unsigned __int64 v24; // rdi
  unsigned __int64 v25; // rsi
  __int64 v26; // rdi
  __int64 v27; // r12
  unsigned __int64 v28; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B8h]
  __int128 v30; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v31; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 CycleTime; // [rsp+78h] [rbp-90h] BYREF
  __int64 v33; // [rsp+80h] [rbp-88h]
  int v34[282]; // [rsp+98h] [rbp-70h] BYREF
  int v35[14]; // [rsp+500h] [rbp+3F8h] BYREF

  UbiTime = Microsoft::Diagnostics::Utils::Time::QueryUbiTime();
  *(_QWORD *)&v30 = L"UsageAnalyzer_PerfStats_0";
  *((_QWORD *)&v30 + 1) = 25;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
    (unsigned int)v34,
    (unsigned int)&v30,
    0x1000000,
    0,
    0,
    0,
    0);
  Cpu0Name = Microsoft::Diagnostics::Utils::Os::GetCpu0Name(&CycleTime);
  *(_QWORD *)&v30 = L"Cpu0Name";
  *((_QWORD *)&v30 + 1) = 8;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v34, v35, &v30, Cpu0Name);
  std::wstring::_Tidy_deallocate(&CycleTime);
  Cpu0Identifier = Microsoft::Diagnostics::Utils::Os::GetCpu0Identifier(&CycleTime);
  *(_QWORD *)&v30 = L"Cpu0Id";
  *((_QWORD *)&v30 + 1) = 6;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v34, v35, &v30, Cpu0Identifier);
  std::wstring::_Tidy_deallocate(&CycleTime);
  *(_QWORD *)&v30 = (char *)this + 1256;
  std::_Mutex_base::lock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 1256));
  CycleTime = (UbiTime - *((_QWORD *)this + 188)) / 0x989680;
  v28 = (unsigned __int64)L"TimeCoveredSec";
  v29 = 14;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v34, (int)v35);
  *((_QWORD *)this + 188) = UbiTime;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcProcessPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UtcProcessPerf>::GetImpl'::`2'::impl) )
  {
    *(double *)&CycleTime = 0.0;
    v28 = 0;
    v31 = 0;
    CurrentProcess = GetCurrentProcess();
    Microsoft::Diagnostics::UsageAnalyzer::GetProcessTimesDelta(this, CurrentProcess, &CycleTime, &v28, &v31);
    if ( v31 )
    {
      v6 = CycleTime + v28;
      if ( (__int64)(CycleTime + v28) < 0 )
        v7 = (double)(int)(v6 & 1 | (v6 >> 1)) + (double)(int)(v6 & 1 | (v6 >> 1));
      else
        v7 = (double)(int)v6;
      v8 = v7 * 100.0;
      if ( (v31 & 0x8000000000000000uLL) != 0LL )
        v9 = (double)(int)(v31 & 1 | (v31 >> 1)) + (double)(int)(v31 & 1 | (v31 >> 1));
      else
        v9 = (double)(int)v31;
      *(double *)&CycleTime = v8 / v9;
      v28 = (unsigned __int64)L"ProcessCpuPercent";
      v29 = 17;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<double>((int)v34, (int)v35);
    }
  }
  v10 = GetCurrentProcess();
  *(double *)&CycleTime = 0.0;
  QueryProcessCycleTime(v10, &CycleTime);
  v11 = CycleTime;
  CycleTime = ((CycleTime - *((_QWORD *)this + 187)) & -(__int64)(*((_QWORD *)this + 187) < CycleTime)) / 0x3E8;
  v28 = (unsigned __int64)L"UtcProcessKCy";
  v29 = 13;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v34, (int)v35);
  *((_QWORD *)this + 187) = v11;
  *(double *)&CycleTime = COERCE_DOUBLE(L"ConsumerCallbackCy");
  v33 = 18;
  Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField((int)v34);
  v12 = *((_QWORD *)this + 167);
  if ( v12 < 0 )
    v13 = (double)(int)(*((_DWORD *)this + 334) & 1 | ((unsigned __int64)v12 >> 1))
        + (double)(int)(*((_DWORD *)this + 334) & 1 | ((unsigned __int64)v12 >> 1));
  else
    v13 = (double)(int)v12;
  v14 = v13 * *((double *)this + 170);
  v15 = 0;
  if ( v14 >= 9.223372036854776e18 )
  {
    v14 = v14 - 9.223372036854776e18;
    if ( v14 < 9.223372036854776e18 )
      v15 = 0x8000000000000000uLL;
  }
  v16 = v15 + (unsigned int)(int)v14;
  *(double *)&CycleTime = COERCE_DOUBLE(L"DefaultPersistCy");
  v33 = 16;
  Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField((int)v34);
  v17 = *((_QWORD *)this + 172);
  if ( v17 < 0 )
    v18 = (double)(int)(*((_DWORD *)this + 344) & 1 | ((unsigned __int64)v17 >> 1))
        + (double)(int)(*((_DWORD *)this + 344) & 1 | ((unsigned __int64)v17 >> 1));
  else
    v18 = (double)(int)v17;
  v19 = v18 * *((double *)this + 175);
  v20 = 0;
  if ( v19 >= 9.223372036854776e18 )
  {
    v19 = v19 - 9.223372036854776e18;
    if ( v19 < 9.223372036854776e18 )
      v20 = 0x8000000000000000uLL;
  }
  v21 = v20 + (unsigned int)(int)v19;
  *(double *)&CycleTime = COERCE_DOUBLE(L"UpdateRulesCy");
  v33 = 13;
  Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField((int)v34);
  *(double *)&CycleTime = 0.0;
  QueryThreadCycleTime(*((HANDLE *)&xmmword_180463140 + 1), &CycleTime);
  v22 = CycleTime;
  CycleTime = ((((CycleTime - *((_QWORD *)this + 144)) & -(__int64)(*((_QWORD *)this + 144) < CycleTime)) - v21)
             & -(__int64)(v21 < ((CycleTime - *((_QWORD *)this + 144)) & -(__int64)(*((_QWORD *)this + 144) < CycleTime))))
            / 0x3E8;
  v28 = (unsigned __int64)L"MatchEngineOverheadKCy";
  v29 = 22;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v34, (int)v35);
  if ( *((_QWORD *)this + 144) >= v22 )
    v22 = *((_QWORD *)this + 144);
  *((_QWORD *)this + 144) = v22;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_1804631B0, 0, 0) )
    v23 = *(void **)(xmmword_1804631B0 + 24);
  else
    v23 = 0;
  *(double *)&CycleTime = 0.0;
  QueryThreadCycleTime(v23, &CycleTime);
  v24 = CycleTime;
  CycleTime = ((CycleTime - *((_QWORD *)this + 145)) & -(__int64)(*((_QWORD *)this + 145) < CycleTime)) / 0x3E8;
  v28 = (unsigned __int64)L"MetadataEngineOverheadKCy";
  v29 = 25;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v34, (int)v35);
  if ( *((_QWORD *)this + 145) >= v24 )
    v24 = *((_QWORD *)this + 145);
  *((_QWORD *)this + 145) = v24;
  v25 = 0;
  v26 = qword_1804632F8;
  v27 = xmmword_180463300;
  while ( v26 != v27 )
  {
    *(double *)&CycleTime = 0.0;
    QueryThreadCycleTime(*(HANDLE *)(v26 + 16), &CycleTime);
    v25 += CycleTime;
    v26 += 24;
  }
  CycleTime = ((((v25 - *((_QWORD *)this + 146)) & -(__int64)(*((_QWORD *)this + 146) < v25)) - v16)
             & -(__int64)(v16 < ((v25 - *((_QWORD *)this + 146)) & -(__int64)(*((_QWORD *)this + 146) < v25))))
            / 0x3E8;
  v28 = (unsigned __int64)L"ConsumerThreadOverheadKCy";
  v29 = 25;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v34, (int)v35);
  if ( *((_QWORD *)this + 146) >= v25 )
    v25 = *((_QWORD *)this + 146);
  *((_QWORD *)this + 146) = v25;
  CycleTime = *((_QWORD *)this + 185) / 0x3E8uLL;
  v28 = (unsigned __int64)L"TotalUploadKCy";
  v29 = 14;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v34, (int)v35);
  *((_QWORD *)this + 185) = 0;
  CycleTime = *((_QWORD *)this + 186) / 0x3E8uLL;
  v28 = (unsigned __int64)L"TotalSettingsDlKCy";
  v29 = 18;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v34, (int)v35);
  *((_QWORD *)this + 186) = 0;
  CycleTime = *((_QWORD *)this + 182) / 0x3E8uLL;
  v28 = (unsigned __int64)L"TotalScenarioListeningKCy";
  v29 = 25;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v34, (int)v35);
  *((_QWORD *)this + 182) = 0;
  CycleTime = *((_QWORD *)this + 183) / 0x3E8uLL;
  v28 = (unsigned __int64)L"TotalScenarioMatchEngineKCy";
  v29 = 27;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v34, (int)v35);
  *((_QWORD *)this + 183) = 0;
  CycleTime = *((_QWORD *)this + 184) / 0x3E8uLL;
  v28 = (unsigned __int64)L"TotalEscalationKCy";
  v29 = 18;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v34, (int)v35);
  *((_QWORD *)this + 184) = 0;
  _Mtx_unlock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 1256));
  v30 = 0;
  Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(&v31, &v30);
  Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v34);
  Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v34);
}

```

## disassembly

```asm
0x1801934cc  mov     rax, rsp
0x1801934cf  push    rbp
0x1801934d0  push    rbx
0x1801934d1  push    rsi
0x1801934d2  push    rdi
0x1801934d3  push    r12
0x1801934d5  push    r13
0x1801934d7  push    r14
0x1801934d9  push    r15
0x1801934db  lea     rbp, [rax-498h]
0x1801934e2  sub     rsp, 558h
0x1801934e9  movaps  xmmword ptr [rax-58h], xmm6
0x1801934ed  mov     rax, cs:__security_cookie
0x1801934f4  xor     rax, rsp
0x1801934f7  mov     [rbp+490h+var_60], rax
0x1801934fe  mov     r14, rcx
0x180193501  call    ?QueryUbiTime@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::QueryUbiTime(void)
0x180193506  mov     rdi, rax
0x180193509  xor     r13d, r13d
0x18019350c  lea     rax, aUsageanalyzerP; "UsageAnalyzer_PerfStats_0"
0x180193513  mov     qword ptr [rsp+590h+var_548+8], rax
0x180193518  mov     [rsp+590h+var_538], 19h
0x180193521  mov     r8d, 1000000h
0x180193527  mov     [rsp+30h], r13b
0x18019352c  mov     [rsp+590h+var_568], r13b
0x180193531  mov     byte ptr [rsp+590h+var_570], r13b
0x180193536  mov     r9, 400000000000h
0x180193540  lea     rdx, [rsp+590h+var_548+8]
0x180193545  lea     rcx, [rbp+490h+var_500]
0x180193549  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x18019354e  nop
0x18019354f  lea     rcx, [rsp+590h+CycleTime]
0x180193554  call    ?GetCpu0Name@Os@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::Os::GetCpu0Name(void)
0x180193559  nop
0x18019355a  lea     rcx, aCpu0name; "Cpu0Name"
0x180193561  mov     qword ptr [rsp+590h+var_548+8], rcx
0x180193566  mov     [rsp+590h+var_538], 8
0x18019356f  mov     r9, rax
0x180193572  lea     r8, [rsp+590h+var_548+8]
0x180193577  lea     rdx, [rbp+490h+var_98]
0x18019357e  lea     rcx, [rbp+490h+var_500]
0x180193582  call    ??$AddField@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring const &)
0x180193587  nop
0x180193588  lea     rcx, [rsp+590h+CycleTime]
0x18019358d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180193592  lea     rcx, [rsp+590h+CycleTime]
0x180193597  call    ?GetCpu0Identifier@Os@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::Os::GetCpu0Identifier(void)
0x18019359c  nop
0x18019359d  lea     rcx, aCpu0id; "Cpu0Id"
0x1801935a4  mov     qword ptr [rsp+590h+var_548+8], rcx
0x1801935a9  mov     [rsp+590h+var_538], 6
0x1801935b2  mov     r9, rax
0x1801935b5  lea     r8, [rsp+590h+var_548+8]
0x1801935ba  lea     rdx, [rbp+490h+var_98]
0x1801935c1  lea     rcx, [rbp+490h+var_500]
0x1801935c5  call    ??$AddField@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring const &)
0x1801935ca  nop
0x1801935cb  lea     rcx, [rsp+590h+CycleTime]
0x1801935d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801935d5  lea     rbx, [r14+4E8h]
0x1801935dc  mov     qword ptr [rsp+590h+var_548+8], rbx
0x1801935e1  mov     rcx, rbx; this
0x1801935e4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801935e9  nop
0x1801935ea  mov     rcx, rdi
0x1801935ed  sub     rcx, [r14+5E0h]
0x1801935f4  mov     rax, 0D6BF94D5E57A42BDh
0x1801935fe  mul     rcx
0x180193601  shr     rdx, 17h
0x180193605  mov     [rsp+590h+CycleTime], rdx
0x18019360a  lea     rax, aTimecoveredsec; "TimeCoveredSec"
0x180193611  mov     [rsp+590h+var_550], rax
0x180193616  mov     qword ptr [rsp+590h+var_548], 0Eh
0x18019361f  lea     r9, [rsp+590h+CycleTime]
0x180193624  lea     r8, [rsp+590h+var_550]
0x180193629  lea     rdx, [rbp+490h+var_98]; int
0x180193630  lea     rcx, [rbp+490h+var_500]; int
0x180193634  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x180193639  mov     [r14+5E0h], rdi
0x180193640  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UtcProcessPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UtcProcessPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcProcessPerf> `wil::Feature<__WilFeatureTraits_Feature_UtcProcessPerf>::GetImpl(void)'::`2'::impl
0x180193647  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UtcProcessPerf@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcProcessPerf>::__private_IsEnabled(void)
0x18019364c  test    al, al
0x18019364e  jz      loc_180193727
0x180193654  mov     [rsp+590h+CycleTime], r13
0x180193659  mov     [rsp+590h+var_550], r13
0x18019365e  mov     [rsp+590h+var_530], r13
0x180193663  call    cs:__imp_GetCurrentProcess
0x180193669  mov     rdx, rax; void *
0x18019366c  lea     rax, [rsp+590h+var_530]
0x180193671  mov     [rsp+590h+var_570], rax; unsigned __int64 *
0x180193676  lea     r9, [rsp+590h+var_550]; unsigned __int64 *
0x18019367b  lea     r8, [rsp+590h+CycleTime]; unsigned __int64 *
0x180193680  mov     rcx, r14; this
0x180193683  call    ?GetProcessTimesDelta@UsageAnalyzer@Diagnostics@Microsoft@@AEAAXPEAXAEA_K11@Z; Microsoft::Diagnostics::UsageAnalyzer::GetProcessTimesDelta(void *,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &)
0x180193688  mov     rdx, [rsp+590h+var_530]
0x18019368d  test    rdx, rdx
0x180193690  jz      loc_180193727
0x180193696  mov     r8, [rsp+590h+var_550]
0x18019369b  add     r8, [rsp+590h+CycleTime]
0x1801936a0  xorps   xmm0, xmm0
0x1801936a3  js      short loc_1801936AC
0x1801936a5  cvtsi2sd xmm0, r8
0x1801936aa  jmp     short loc_1801936C2
0x1801936ac  mov     rax, r8
0x1801936af  shr     rax, 1
0x1801936b2  and     r8d, 1
0x1801936b6  or      rax, r8
0x1801936b9  cvtsi2sd xmm0, rax
0x1801936be  addsd   xmm0, xmm0
0x1801936c2  mulsd   xmm0, cs:__real@4059000000000000
0x1801936ca  xorps   xmm1, xmm1
0x1801936cd  test    rdx, rdx
0x1801936d0  js      short loc_1801936D9
0x1801936d2  cvtsi2sd xmm1, rdx
0x1801936d7  jmp     short loc_1801936EE
0x1801936d9  mov     rax, rdx
0x1801936dc  shr     rax, 1
0x1801936df  and     edx, 1
0x1801936e2  or      rax, rdx
0x1801936e5  cvtsi2sd xmm1, rax
0x1801936ea  addsd   xmm1, xmm1
0x1801936ee  divsd   xmm0, xmm1
0x1801936f2  movsd   [rsp+590h+CycleTime], xmm0
0x1801936f8  lea     rax, aProcesscpuperc; "ProcessCpuPercent"
0x1801936ff  mov     [rsp+590h+var_550], rax
0x180193704  mov     qword ptr [rsp+590h+var_548], 11h
0x18019370d  lea     r9, [rsp+590h+CycleTime]
0x180193712  lea     r8, [rsp+590h+var_550]
0x180193717  lea     rdx, [rbp+490h+var_98]; int
0x18019371e  lea     rcx, [rbp+490h+var_500]; int
0x180193722  call    ??$AddField@N@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBN@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<double>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,double const &)
0x180193727  call    cs:__imp_GetCurrentProcess
0x18019372d  mov     [rsp+590h+CycleTime], r13
0x180193732  lea     rdx, [rsp+590h+CycleTime]; CycleTime
0x180193737  mov     rcx, rax; ProcessHandle
0x18019373a  call    cs:__imp_QueryProcessCycleTime
0x180193740  mov     rdi, [rsp+590h+CycleTime]
0x180193745  mov     rcx, [r14+5D8h]
0x18019374c  mov     rax, rdi
0x18019374f  sub     rax, rcx
0x180193752  cmp     rcx, rdi
0x180193755  sbb     rcx, rcx
0x180193758  and     rcx, rax
0x18019375b  mov     r12, 624DD2F1A9FBE77h
0x180193765  mov     rax, r12
0x180193768  mul     rcx
0x18019376b  sub     rcx, rdx
0x18019376e  shr     rcx, 1
0x180193771  add     rcx, rdx
0x180193774  shr     rcx, 9
0x180193778  mov     [rsp+590h+CycleTime], rcx
0x18019377d  lea     rax, aUtcprocesskcy; "UtcProcessKCy"
0x180193784  mov     [rsp+590h+var_550], rax
0x180193789  mov     qword ptr [rsp+590h+var_548], 0Dh
0x180193792  lea     r9, [rsp+590h+CycleTime]
0x180193797  lea     r8, [rsp+590h+var_550]
0x18019379c  lea     rdx, [rbp+490h+var_98]; int
0x1801937a3  lea     rcx, [rbp+490h+var_500]; int
0x1801937a7  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x1801937ac  mov     [r14+5D8h], rdi
0x1801937b3  lea     rax, aConsumercallba; "ConsumerCallbackCy"
0x1801937ba  mov     [rsp+590h+CycleTime], rax
0x1801937bf  mov     [rsp+590h+var_518], 12h
0x1801937c8  lea     rdi, [r14+538h]
0x1801937cf  mov     r8, rdi
0x1801937d2  lea     rdx, [rsp+590h+CycleTime]
0x1801937d7  lea     rcx, [rbp+490h+var_500]; int
0x1801937db  call    ?AddDistroInfoSyntheticField@UsageAnalyzer@Diagnostics@Microsoft@@CAXAEAVAsimovSyntheticEvent@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$SimpleDistroInfo@_K@23@@Z; Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::wstring_view,Microsoft::Diagnostics::SimpleDistroInfo<unsigned __int64> &)
0x1801937e0  mov     rcx, [rdi]
0x1801937e3  xorps   xmm0, xmm0
0x1801937e6  test    rcx, rcx
0x1801937e9  js      short loc_1801937F2
0x1801937eb  cvtsi2sd xmm0, rcx
0x1801937f0  jmp     short loc_180193807
0x1801937f2  mov     rax, rcx
0x1801937f5  shr     rax, 1
0x1801937f8  and     ecx, 1
0x1801937fb  or      rax, rcx
0x1801937fe  cvtsi2sd xmm0, rax
0x180193803  addsd   xmm0, xmm0
0x180193807  mulsd   xmm0, qword ptr [r14+550h]
0x180193810  xor     eax, eax
0x180193812  mov     rsi, 8000000000000000h
0x18019381c  movsd   xmm6, cs:__real@43e0000000000000
0x180193824  comisd  xmm0, xmm6
0x180193828  jb      short loc_180193837
0x18019382a  subsd   xmm0, xmm6
0x18019382e  comisd  xmm0, xmm6
0x180193832  jnb     short loc_180193837
0x180193834  mov     rax, rsi
0x180193837  cvttsd2si r15, xmm0
0x18019383c  add     r15, rax
0x18019383f  lea     rax, aDefaultpersist; "DefaultPersistCy"
0x180193846  mov     [rsp+590h+CycleTime], rax
0x18019384b  mov     [rsp+590h+var_518], 10h
0x180193854  lea     rdi, [r14+560h]
0x18019385b  mov     r8, rdi
0x18019385e  lea     rdx, [rsp+590h+CycleTime]
0x180193863  lea     rcx, [rbp+490h+var_500]; int
0x180193867  call    ?AddDistroInfoSyntheticField@UsageAnalyzer@Diagnostics@Microsoft@@CAXAEAVAsimovSyntheticEvent@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$SimpleDistroInfo@_K@23@@Z; Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::wstring_view,Microsoft::Diagnostics::SimpleDistroInfo<unsigned __int64> &)
0x18019386c  mov     rcx, [rdi]
0x18019386f  xorps   xmm0, xmm0
0x180193872  test    rcx, rcx
0x180193875  js      short loc_18019387E
0x180193877  cvtsi2sd xmm0, rcx
0x18019387c  jmp     short loc_180193893
0x18019387e  mov     rax, rcx
0x180193881  shr     rax, 1
0x180193884  and     ecx, 1
0x180193887  or      rax, rcx
0x18019388a  cvtsi2sd xmm0, rax
0x18019388f  addsd   xmm0, xmm0
0x180193893  mulsd   xmm0, qword ptr [r14+578h]
0x18019389c  xor     eax, eax
0x18019389e  comisd  xmm0, xmm6
0x1801938a2  jb      short loc_1801938B1
0x1801938a4  subsd   xmm0, xmm6
0x1801938a8  comisd  xmm0, xmm6
0x1801938ac  jnb     short loc_1801938B1
0x1801938ae  mov     rax, rsi
0x1801938b1  cvttsd2si rdi, xmm0
0x1801938b6  add     rdi, rax
0x1801938b9  lea     rax, aUpdaterulescy; "UpdateRulesCy"
0x1801938c0  mov     [rsp+590h+CycleTime], rax
0x1801938c5  mov     [rsp+590h+var_518], 0Dh
0x1801938ce  lea     r8, [r14+588h]
0x1801938d5  lea     rdx, [rsp+590h+CycleTime]
0x1801938da  lea     rcx, [rbp+490h+var_500]; int
0x1801938de  call    ?AddDistroInfoSyntheticField@UsageAnalyzer@Diagnostics@Microsoft@@CAXAEAVAsimovSyntheticEvent@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$SimpleDistroInfo@_K@23@@Z; Microsoft::Diagnostics::UsageAnalyzer::AddDistroInfoSyntheticField(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::wstring_view,Microsoft::Diagnostics::SimpleDistroInfo<unsigned __int64> &)
0x1801938e3  mov     [rsp+590h+CycleTime], r13
0x1801938e8  lea     rdx, [rsp+590h+CycleTime]; CycleTime
0x1801938ed  mov     rcx, qword ptr cs:xmmword_180463140+8; ThreadHandle
0x1801938f4  call    cs:__imp_QueryThreadCycleTime
0x1801938fa  mov     rsi, [rsp+590h+CycleTime]
0x1801938ff  mov     rcx, [r14+480h]
0x180193906  mov     rax, rsi
0x180193909  sub     rax, rcx
0x18019390c  cmp     rcx, rsi
0x18019390f  sbb     rcx, rcx
0x180193912  and     rcx, rax
0x180193915  mov     rax, rcx
0x180193918  sub     rax, rdi
0x18019391b  cmp     rdi, rcx
0x18019391e  sbb     rcx, rcx
0x180193921  and     rcx, rax
0x180193924  mov     rax, r12
0x180193927  mul     rcx
0x18019392a  sub     rcx, rdx
0x18019392d  shr     rcx, 1
0x180193930  add     rcx, rdx
0x180193933  shr     rcx, 9
0x180193937  mov     [rsp+590h+CycleTime], rcx
0x18019393c  lea     rax, aMatchengineove; "MatchEngineOverheadKCy"
0x180193943  mov     [rsp+590h+var_550], rax
0x180193948  mov     qword ptr [rsp+590h+var_548], 16h
0x180193951  lea     r9, [rsp+590h+CycleTime]
0x180193956  lea     r8, [rsp+590h+var_550]
0x18019395b  lea     rdx, [rbp+490h+var_98]; int
0x180193962  lea     rcx, [rbp+490h+var_500]; int
0x180193966  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x18019396b  mov     rax, [r14+480h]
0x180193972  cmp     rax, rsi
0x180193975  cmovnb  rsi, rax
0x180193979  mov     [r14+480h], rsi
0x180193980  mov     rcx, r13
0x180193983  xor     eax, eax
0x180193985  lock cmpxchg qword ptr cs:xmmword_1804631B0, rcx
0x18019398e  jz      short loc_18019399D
0x180193990  mov     rax, qword ptr cs:xmmword_1804631B0
0x180193997  mov     rcx, [rax+18h]
0x18019399b  jmp     short loc_1801939A0
0x18019399d  mov     rcx, r13; ThreadHandle
0x1801939a0  mov     [rsp+590h+CycleTime], r13
0x1801939a5  lea     rdx, [rsp+590h+CycleTime]; CycleTime
0x1801939aa  call    cs:__imp_QueryThreadCycleTime
0x1801939b0  mov     rdi, [rsp+590h+CycleTime]
0x1801939b5  mov     rcx, [r14+488h]
0x1801939bc  mov     rax, rdi
0x1801939bf  sub     rax, rcx
0x1801939c2  cmp     rcx, rdi
0x1801939c5  sbb     rcx, rcx
0x1801939c8  and     rcx, rax
0x1801939cb  mov     rax, r12
0x1801939ce  mul     rcx
0x1801939d1  sub     rcx, rdx
0x1801939d4  shr     rcx, 1
0x1801939d7  add     rcx, rdx
0x1801939da  shr     rcx, 9
0x1801939de  mov     [rsp+590h+CycleTime], rcx
0x1801939e3  lea     rax, aMetadataengine_1; "MetadataEngineOverheadKCy"
0x1801939ea  mov     [rsp+590h+var_550], rax
0x1801939ef  mov     qword ptr [rsp+590h+var_548], 19h
0x1801939f8  lea     r9, [rsp+590h+CycleTime]
0x1801939fd  lea     r8, [rsp+590h+var_550]
0x180193a02  lea     rdx, [rbp+490h+var_98]; int
0x180193a09  lea     rcx, [rbp+490h+var_500]; int
0x180193a0d  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x180193a12  mov     rax, [r14+488h]
0x180193a19  cmp     rax, rdi
0x180193a1c  cmovnb  rdi, rax
  ... truncated ...
```
