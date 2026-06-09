# AOMDHandler::InitializeConfig(void)

- ea: `0x18000d77c`
- end: `0x18000dbb5`
- name: `?InitializeConfig@AOMDHandler@@AEAAXXZ`
- size: `1081`
- prototype: `void __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a6d4`

## callees

- `0x180004560`
- `0x1800045dc`
- `0x180004654`
- `0x1800046cc`
- `0x180004744`
- `0x1800048ec`
- `0x180004964`
- `0x1800049dc`
- `0x180006348`
- `0x180006390`
- `0x18000d77c`
- `0x18000e168`
- `0x180015764`

## string_xrefs

- `0x18000d7d9`: `InitializeConfig_BugcheckThresholdOverrideNotFound`
- `0x18000d823`: `InitializeConfig_AppCrashThresholdOverrideNotFound`
- `0x18000d85a`: `InitializeConfig_PageNotZeroThresholdOverrideNotFound`
- `0x18000d891`: `InitializeConfig_StoreCorruptionThresholdOverrideNotFound`
- `0x18000d8cb`: `InitializeConfig_LookbackTimeNotFound`
- `0x18000d907`: `InitializeConfig_CooldownTimeNotFound`
- `0x18000d93a`: `InitializeConfig_SelfThrottleTimeNotFound`
- `0x18000d999`: `InitializeConfig_MdSchedLastRunTimeNotFound`
- `0x18000d9dd`: `InitializeConfig_LastScanDecisionTimeNotFound`
- `0x18000da1c`: `InitializeConfig_LastScanOfferedTimeNotFound`
- `0x18000da5b`: `InitializeConfig_NumTimesScanOfferedNotFound`
- `0x18000da8c`: `InitializeConfig_BugCheckThreshold`
- `0x18000daa7`: `InitializeConfig_AppCrashThreshold`
- `0x18000dae8`: `InitializeConfig_LookbackTimeHours`
- `0x18000db01`: `InitializeConfig_CooldownTimeHours`

## pseudocode

```c
void __fastcall AOMDHandler::InitializeConfig(AOMDHandler *this)
{
  char IsEnabled; // cl
  unsigned int value_dword; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int *v7; // r13
  unsigned int v8; // eax
  int *v9; // r12
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // edx
  int v13; // eax
  unsigned int value_qword; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  const char *v23; // r9
  const wchar_t *v24; // [rsp+20h] [rbp-38h] BYREF
  __int64 v25; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  _DWORD *v28; // [rsp+68h] [rbp+10h] BYREF

  try
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::__private_IsEnabled();
    v28 = (_DWORD *)((char *)this + 60);
    if ( IsEnabled )
    {
      *((_DWORD *)this + 15) = 1;
      v28 = (_DWORD *)((char *)this + 60);
    }
    else
    {
      value_dword = wil::reg::get_value_dword_nothrow<unsigned long,0>(
                      -2147483646,
                      L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
                      L"AOMDBugCheckThreshold",
                      (char *)this + 60);
      v24 = L"InitializeConfig_BugcheckThresholdOverrideNotFound";
      v25 = 50;
      TlgHelper::LogIfFailedExpected(&v24, value_dword);
    }
    v4 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
           -2147483646,
           L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
           L"AOMDAppCrashThreshold",
           (char *)this + 56);
    v24 = L"InitializeConfig_AppCrashThresholdOverrideNotFound";
    v25 = 50;
    TlgHelper::LogIfFailedExpected(&v24, v4);
    v5 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
           -2147483646,
           L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
           L"AOMDPageNotZeroThreshold",
           (char *)this + 64);
    v24 = L"InitializeConfig_PageNotZeroThresholdOverrideNotFound";
    v25 = 53;
    TlgHelper::LogIfFailedExpected(&v24, v5);
    v6 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
           -2147483646,
           L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
           L"AOMDStoreCorruptionThreshold",
           (char *)this + 68);
    v24 = L"InitializeConfig_StoreCorruptionThresholdOverrideNotFound";
    v25 = 57;
    TlgHelper::LogIfFailedExpected(&v24, v6);
    v7 = (unsigned int *)((char *)this + 72);
    v8 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
           -2147483646,
           L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
           L"AOMDLookbackTimeHours",
           (char *)this + 72);
    v24 = L"InitializeConfig_LookbackTimeNotFound";
    v25 = 37;
    TlgHelper::LogIfFailedExpected(&v24, v8);
    v9 = (int *)((char *)this + 76);
    v10 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
            -2147483646,
            L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
            L"AOMDCooldownTimeHours",
            (char *)this + 76);
    v24 = L"InitializeConfig_CooldownTimeNotFound";
    v25 = 37;
    TlgHelper::LogIfFailedExpected(&v24, v10);
    v11 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
            -2147483646,
            L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
            L"AOMDSelfThrottleTimeHours",
            (char *)this + 80);
    v24 = L"InitializeConfig_SelfThrottleTimeNotFound";
    v25 = 41;
    TlgHelper::LogIfFailedExpected(&v24, v11);
    v12 = *((_DWORD *)this + 18);
    if ( v12 > 0x2238 )
      v12 = 8760;
    v13 = *v9;
    if ( (unsigned int)*v9 > 0x2238 )
      v13 = 8760;
    *v9 = v13;
    if ( !v12 )
      v12 = 1;
    *v7 = v12;
    value_qword = wil::reg::get_value_qword_nothrow<unsigned __int64,0>(
                    -2147483646,
                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\MemoryDiagnostic",
                    L"LastRunTime",
                    (char *)this + 120);
    v24 = L"InitializeConfig_MdSchedLastRunTimeNotFound";
    v25 = 43;
    TlgHelper::LogIfFailedExpected(&v24, value_qword);
    v15 = wil::reg::get_value_qword_nothrow<unsigned __int64,0>(
            -2147483647,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
            L"AOMDLastScanDecisionTime",
            (char *)this + 96);
    v24 = L"InitializeConfig_LastScanDecisionTimeNotFound";
    v25 = 45;
    TlgHelper::LogIfFailedExpected(&v24, v15);
    v16 = wil::reg::get_value_qword_nothrow<unsigned __int64,0>(
            -2147483647,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
            L"AOMDLastScanOfferedTime",
            (char *)this + 104);
    v24 = L"InitializeConfig_LastScanOfferedTimeNotFound";
    v25 = 44;
    TlgHelper::LogIfFailedExpected(&v24, v16);
    v17 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
            -2147483647,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
            L"AOMDNumScanOffersSinceLastDecision",
            (char *)this + 112);
    v24 = L"InitializeConfig_NumTimesScanOfferedNotFound";
    v25 = 44;
    TlgHelper::LogIfFailedExpected(&v24, v17);
    LODWORD(v28) = *v28;
    TlgHelper::LogInfo<unsigned short const (&)[35],unsigned int>(L"InitializeConfig_BugCheckThreshold", &v28);
    LODWORD(v28) = *((_DWORD *)this + 14);
    TlgHelper::LogInfo<unsigned short const (&)[35],unsigned int>(L"InitializeConfig_AppCrashThreshold", &v28);
    LODWORD(v28) = *((_DWORD *)this + 16);
    TlgHelper::LogInfo<unsigned short const (&)[38],unsigned int>((__int64)this, &v28);
    LODWORD(v28) = *((_DWORD *)this + 17);
    TlgHelper::LogInfo<unsigned short const (&)[42],unsigned int>((__int64)this, &v28);
    LODWORD(v28) = *v7;
    TlgHelper::LogInfo<unsigned short const (&)[35],unsigned int>(L"InitializeConfig_LookbackTimeHours", &v28);
    LODWORD(v28) = *v9;
    TlgHelper::LogInfo<unsigned short const (&)[35],unsigned int>(L"InitializeConfig_CooldownTimeHours", &v28);
    LODWORD(v28) = *((_DWORD *)this + 20);
    TlgHelper::LogInfo<unsigned short const (&)[39],unsigned int>(v18, &v28);
    v28 = (_DWORD *)*((_QWORD *)this + 15);
    TlgHelper::LogInfoFiletime<unsigned short const (&)[36],_FILETIME>(v19, (__int64 *)&v28);
    v28 = (_DWORD *)*((_QWORD *)this + 12);
    TlgHelper::LogInfoFiletime<unsigned short const (&)[38],_FILETIME>(v20, (__int64 *)&v28);
    v28 = (_DWORD *)*((_QWORD *)this + 13);
    TlgHelper::LogInfoFiletime<unsigned short const (&)[37],_FILETIME>(v21, (__int64 *)&v28);
    LODWORD(v28) = *((_DWORD *)this + 28);
    TlgHelper::LogInfo<unsigned short const (&)[48],unsigned int>(v22, &v28);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x27B,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      v23);
  }
}

```

## disassembly

```asm
0x18000d77c  mov     [rsp+arg_10], rbx
0x18000d781  mov     [rsp+arg_18], rsi
0x18000d786  mov     [rsp+arg_0], rcx
0x18000d78b  push    rdi
0x18000d78c  push    r12
0x18000d78e  push    r13
0x18000d790  push    r14
0x18000d792  push    r15
0x18000d794  sub     rsp, 30h
0x18000d798  mov     r14, rcx
0x18000d79b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59116012@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59116012@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012> `wil::Feature<__WilFeatureTraits_Feature_59116012>::GetImpl(void)'::`2'::impl
0x18000d7a2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59116012@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::__private_IsEnabled(void)
0x18000d7a7  mov     cl, al
0x18000d7a9  lea     rax, [r14+3Ch]
0x18000d7ad  mov     [rsp+58h+arg_8], rax
0x18000d7b2  lea     rdi, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MemoryDiagnostic"
0x18000d7b9  mov     rbx, 0FFFFFFFF80000002h
0x18000d7c0  test    cl, cl
0x18000d7c2  jnz     short loc_18000D801
0x18000d7c4  mov     r9, rax
0x18000d7c7  lea     r8, aAomdbugcheckth; "AOMDBugCheckThreshold"
0x18000d7ce  mov     rdx, rdi
0x18000d7d1  mov     rcx, rbx
0x18000d7d4  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000d7d9  lea     rcx, aInitializeconf; "InitializeConfig_BugcheckThresholdOverr"...
0x18000d7e0  mov     [rsp+58h+var_38], rcx
0x18000d7e5  mov     [rsp+58h+var_30], 32h ; '2'
0x18000d7ee  mov     edx, eax
0x18000d7f0  lea     rcx, [rsp+58h+var_38]
0x18000d7f5  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000d7fa  mov     esi, 1
0x18000d7ff  jmp     short loc_18000D80D
0x18000d801  mov     esi, 1
0x18000d806  mov     [rax], esi
0x18000d808  mov     [rsp+58h+arg_8], rax
0x18000d80d  lea     r9, [r14+38h]
0x18000d811  lea     r8, aAomdappcrashth; "AOMDAppCrashThreshold"
0x18000d818  mov     rdx, rdi
0x18000d81b  mov     rcx, rbx
0x18000d81e  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000d823  lea     rcx, aInitializeconf_13; "InitializeConfig_AppCrashThresholdOverr"...
0x18000d82a  mov     [rsp+58h+var_38], rcx
0x18000d82f  mov     [rsp+58h+var_30], 32h ; '2'
0x18000d838  mov     edx, eax
0x18000d83a  lea     rcx, [rsp+58h+var_38]
0x18000d83f  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000d844  lea     r9, [r14+40h]
0x18000d848  lea     r8, aAomdpagenotzer; "AOMDPageNotZeroThreshold"
0x18000d84f  mov     rdx, rdi
0x18000d852  mov     rcx, rbx
0x18000d855  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000d85a  lea     rcx, aInitializeconf_14; "InitializeConfig_PageNotZeroThresholdOv"...
0x18000d861  mov     [rsp+58h+var_38], rcx
0x18000d866  mov     [rsp+58h+var_30], 35h ; '5'
0x18000d86f  mov     edx, eax
0x18000d871  lea     rcx, [rsp+58h+var_38]
0x18000d876  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000d87b  lea     r9, [r14+44h]
0x18000d87f  lea     r8, aAomdstorecorru; "AOMDStoreCorruptionThreshold"
0x18000d886  mov     rdx, rdi
0x18000d889  mov     rcx, rbx
0x18000d88c  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000d891  lea     rcx, aInitializeconf_0; "InitializeConfig_StoreCorruptionThresho"...
0x18000d898  mov     [rsp+58h+var_38], rcx
0x18000d89d  mov     [rsp+58h+var_30], 39h ; '9'
0x18000d8a6  mov     edx, eax
0x18000d8a8  lea     rcx, [rsp+58h+var_38]
0x18000d8ad  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000d8b2  lea     r13, [r14+48h]
0x18000d8b6  mov     r9, r13
0x18000d8b9  lea     r8, aAomdlookbackti; "AOMDLookbackTimeHours"
0x18000d8c0  mov     rdx, rdi
0x18000d8c3  mov     rcx, rbx
0x18000d8c6  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000d8cb  lea     rcx, aInitializeconf_7; "InitializeConfig_LookbackTimeNotFound"
0x18000d8d2  mov     [rsp+58h+var_38], rcx
0x18000d8d7  mov     r15d, 25h ; '%'
0x18000d8dd  mov     [rsp+58h+var_30], r15
0x18000d8e2  mov     edx, eax
0x18000d8e4  lea     rcx, [rsp+58h+var_38]
0x18000d8e9  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000d8ee  lea     r12, [r14+4Ch]
0x18000d8f2  mov     r9, r12
0x18000d8f5  lea     r8, aAomdcooldownti; "AOMDCooldownTimeHours"
0x18000d8fc  mov     rdx, rdi
0x18000d8ff  mov     rcx, rbx
0x18000d902  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000d907  lea     rcx, aInitializeconf_16; "InitializeConfig_CooldownTimeNotFound"
0x18000d90e  mov     [rsp+58h+var_38], rcx
0x18000d913  mov     [rsp+58h+var_30], r15
0x18000d918  mov     edx, eax
0x18000d91a  lea     rcx, [rsp+58h+var_38]
0x18000d91f  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000d924  lea     r9, [r14+50h]
0x18000d928  lea     r8, aAomdselfthrott; "AOMDSelfThrottleTimeHours"
0x18000d92f  mov     rdx, rdi
0x18000d932  mov     rcx, rbx
0x18000d935  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000d93a  lea     rcx, aInitializeconf_12; "InitializeConfig_SelfThrottleTimeNotFou"...
0x18000d941  mov     [rsp+58h+var_38], rcx
0x18000d946  mov     [rsp+58h+var_30], 29h ; ')'
0x18000d94f  mov     edx, eax
0x18000d951  lea     rcx, [rsp+58h+var_38]
0x18000d956  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000d95b  mov     edx, [r13+0]
0x18000d95f  mov     ecx, 2238h
0x18000d964  cmp     edx, ecx
0x18000d966  cmova   edx, ecx
0x18000d969  mov     eax, [r12]
0x18000d96d  cmp     eax, ecx
0x18000d96f  cmova   eax, ecx
0x18000d972  mov     [r12], eax
0x18000d976  cmp     edx, esi
0x18000d978  cmovb   edx, esi
0x18000d97b  mov     [r13+0], edx
0x18000d97f  lea     r9, [r14+78h]
0x18000d983  lea     r8, aLastruntime; "LastRunTime"
0x18000d98a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000d991  mov     rcx, rbx
0x18000d994  call    ??$get_value_qword_nothrow@_K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEA_K@Z; wil::reg::get_value_qword_nothrow<unsigned __int64,0>(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *)
0x18000d999  lea     rcx, aInitializeconf_18; "InitializeConfig_MdSchedLastRunTimeNotF"...
0x18000d9a0  mov     [rsp+58h+var_38], rcx
0x18000d9a5  mov     [rsp+58h+var_30], 2Bh ; '+'
0x18000d9ae  mov     edx, eax
0x18000d9b0  lea     rcx, [rsp+58h+var_38]
0x18000d9b5  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000d9ba  mov     rbx, [rsp+58h+arg_0]
0x18000d9bf  lea     r9, [rbx+60h]
0x18000d9c3  lea     r8, ValueName; "AOMDLastScanDecisionTime"
0x18000d9ca  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000d9d1  mov     rcx, 0FFFFFFFF80000001h
0x18000d9d8  call    ??$get_value_qword_nothrow@_K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEA_K@Z; wil::reg::get_value_qword_nothrow<unsigned __int64,0>(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *)
0x18000d9dd  lea     rcx, aInitializeconf_17; "InitializeConfig_LastScanDecisionTimeNo"...
0x18000d9e4  mov     [rsp+58h+var_38], rcx
0x18000d9e9  mov     [rsp+58h+var_30], 2Dh ; '-'
0x18000d9f2  mov     edx, eax
0x18000d9f4  lea     rcx, [rsp+58h+var_38]
0x18000d9f9  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000d9fe  lea     r9, [rbx+68h]
0x18000da02  lea     r8, aAomdlastscanof; "AOMDLastScanOfferedTime"
0x18000da09  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000da10  mov     rcx, 0FFFFFFFF80000001h
0x18000da17  call    ??$get_value_qword_nothrow@_K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEA_K@Z; wil::reg::get_value_qword_nothrow<unsigned __int64,0>(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *)
0x18000da1c  lea     r8, aInitializeconf_2; "InitializeConfig_LastScanOfferedTimeNot"...
0x18000da23  mov     [rsp+58h+var_38], r8
0x18000da28  mov     [rsp+58h+var_30], 2Ch ; ','
0x18000da31  mov     edx, eax
0x18000da33  lea     rcx, [rsp+58h+var_38]
0x18000da38  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000da3d  lea     r9, [rbx+70h]
0x18000da41  lea     r8, aAomdnumscanoff; "AOMDNumScanOffersSinceLastDecision"
0x18000da48  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000da4f  mov     rcx, 0FFFFFFFF80000001h
0x18000da56  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000da5b  lea     rcx, aInitializeconf_19; "InitializeConfig_NumTimesScanOfferedNot"...
0x18000da62  mov     [rsp+58h+var_38], rcx
0x18000da67  mov     [rsp+58h+var_30], 2Ch ; ','
0x18000da70  mov     edx, eax
0x18000da72  lea     rcx, [rsp+58h+var_38]
0x18000da77  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000da7c  mov     rcx, [rsp+58h+arg_8]
0x18000da81  mov     eax, [rcx]
0x18000da83  mov     dword ptr [rsp+58h+arg_8], eax
0x18000da87  lea     rdx, [rsp+58h+arg_8]
0x18000da8c  lea     rcx, aInitializeconf_5; "InitializeConfig_BugCheckThreshold"
0x18000da93  call    ??$LogInfo@AEAY0CD@$$CBGI@TlgHelper@@SAXAEAY0CD@$$CBG$$QEAI@Z; TlgHelper::LogInfo<ushort const (&)[35],uint>(ushort const (&)[35],uint &&)
0x18000da98  mov     rcx, rbx
0x18000da9b  mov     eax, [rbx+38h]
0x18000da9e  mov     dword ptr [rsp+58h+arg_8], eax
0x18000daa2  lea     rdx, [rsp+58h+arg_8]
0x18000daa7  lea     rcx, aInitializeconf_3; "InitializeConfig_AppCrashThreshold"
0x18000daae  call    ??$LogInfo@AEAY0CD@$$CBGI@TlgHelper@@SAXAEAY0CD@$$CBG$$QEAI@Z; TlgHelper::LogInfo<ushort const (&)[35],uint>(ushort const (&)[35],uint &&)
0x18000dab3  mov     rcx, rbx
0x18000dab6  mov     eax, [rbx+40h]
0x18000dab9  mov     dword ptr [rsp+58h+arg_8], eax
0x18000dabd  lea     rdx, [rsp+58h+arg_8]
0x18000dac2  call    ??$LogInfo@AEAY0CG@$$CBGI@TlgHelper@@SAXAEAY0CG@$$CBG$$QEAI@Z; TlgHelper::LogInfo<ushort const (&)[38],uint>(ushort const (&)[38],uint &&)
0x18000dac7  mov     rcx, rbx
0x18000daca  mov     eax, [rbx+44h]
0x18000dacd  mov     dword ptr [rsp+58h+arg_8], eax
0x18000dad1  lea     rdx, [rsp+58h+arg_8]
0x18000dad6  call    ??$LogInfo@AEAY0CK@$$CBGI@TlgHelper@@SAXAEAY0CK@$$CBG$$QEAI@Z; TlgHelper::LogInfo<ushort const (&)[42],uint>(ushort const (&)[42],uint &&)
0x18000dadb  mov     eax, [r13+0]
0x18000dadf  mov     dword ptr [rsp+58h+arg_8], eax
0x18000dae3  lea     rdx, [rsp+58h+arg_8]
0x18000dae8  lea     rcx, aInitializeconf_1; "InitializeConfig_LookbackTimeHours"
0x18000daef  call    ??$LogInfo@AEAY0CD@$$CBGI@TlgHelper@@SAXAEAY0CD@$$CBG$$QEAI@Z; TlgHelper::LogInfo<ushort const (&)[35],uint>(ushort const (&)[35],uint &&)
0x18000daf4  mov     eax, [r12]
0x18000daf8  mov     dword ptr [rsp+58h+arg_8], eax
0x18000dafc  lea     rdx, [rsp+58h+arg_8]
0x18000db01  lea     rcx, aInitializeconf_6; "InitializeConfig_CooldownTimeHours"
0x18000db08  call    ??$LogInfo@AEAY0CD@$$CBGI@TlgHelper@@SAXAEAY0CD@$$CBG$$QEAI@Z; TlgHelper::LogInfo<ushort const (&)[35],uint>(ushort const (&)[35],uint &&)
0x18000db0d  mov     eax, [r14+50h]
0x18000db11  mov     dword ptr [rsp+58h+arg_8], eax
0x18000db15  lea     rdx, [rsp+58h+arg_8]
0x18000db1a  call    ??$LogInfo@AEAY0CH@$$CBGI@TlgHelper@@SAXAEAY0CH@$$CBG$$QEAI@Z; TlgHelper::LogInfo<ushort const (&)[39],uint>(ushort const (&)[39],uint &&)
0x18000db1f  mov     rax, [r14+78h]
0x18000db23  mov     dword ptr [rsp+58h+arg_8], eax
0x18000db27  shr     rax, 20h
0x18000db2b  mov     dword ptr [rsp+58h+arg_8+4], eax
0x18000db2f  mov     rax, [rsp+58h+arg_8]
0x18000db34  mov     [rsp+58h+arg_8], rax
0x18000db39  lea     rdx, [rsp+58h+arg_8]
0x18000db3e  call    ??$LogInfoFiletime@AEAY0CE@$$CBGU_FILETIME@@@TlgHelper@@SAXAEAY0CE@$$CBG$$QEAU_FILETIME@@@Z; TlgHelper::LogInfoFiletime<ushort const (&)[36],_FILETIME>(ushort const (&)[36],_FILETIME &&)
0x18000db43  mov     rax, [rbx+60h]
0x18000db47  mov     dword ptr [rsp+58h+arg_8], eax
0x18000db4b  shr     rax, 20h
0x18000db4f  mov     dword ptr [rsp+58h+arg_8+4], eax
0x18000db53  mov     rax, [rsp+58h+arg_8]
0x18000db58  mov     [rsp+58h+arg_8], rax
0x18000db5d  lea     rdx, [rsp+58h+arg_8]
0x18000db62  call    ??$LogInfoFiletime@AEAY0CG@$$CBGU_FILETIME@@@TlgHelper@@SAXAEAY0CG@$$CBG$$QEAU_FILETIME@@@Z; TlgHelper::LogInfoFiletime<ushort const (&)[38],_FILETIME>(ushort const (&)[38],_FILETIME &&)
0x18000db67  mov     rax, [rbx+68h]
0x18000db6b  mov     dword ptr [rsp+58h+arg_8], eax
0x18000db6f  shr     rax, 20h
0x18000db73  mov     dword ptr [rsp+58h+arg_8+4], eax
0x18000db77  mov     rax, [rsp+58h+arg_8]
0x18000db7c  mov     [rsp+58h+arg_8], rax
0x18000db81  lea     rdx, [rsp+58h+arg_8]
0x18000db86  call    ??$LogInfoFiletime@AEAY0CF@$$CBGU_FILETIME@@@TlgHelper@@SAXAEAY0CF@$$CBG$$QEAU_FILETIME@@@Z; TlgHelper::LogInfoFiletime<ushort const (&)[37],_FILETIME>(ushort const (&)[37],_FILETIME &&)
0x18000db8b  mov     eax, [rbx+70h]
0x18000db8e  mov     dword ptr [rsp+58h+arg_8], eax
0x18000db92  lea     rdx, [rsp+58h+arg_8]
0x18000db97  call    ??$LogInfo@AEAY0DA@$$CBGI@TlgHelper@@SAXAEAY0DA@$$CBG$$QEAI@Z; TlgHelper::LogInfo<ushort const (&)[48],uint>(ushort const (&)[48],uint &&)
0x18000db9c  nop
0x18000db9d  mov     rbx, [rsp+58h+arg_10]
0x18000dba2  mov     rsi, [rsp+58h+arg_18]
0x18000dba7  add     rsp, 30h
0x18000dbab  pop     r15
0x18000dbad  pop     r14
0x18000dbaf  pop     r13
0x18000dbb1  pop     r12
0x18000dbb3  pop     rdi
0x18000dbb4  retn
```
