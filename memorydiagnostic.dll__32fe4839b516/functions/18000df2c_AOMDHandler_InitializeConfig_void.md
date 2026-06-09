# AOMDHandler::InitializeConfig(void)

- ea: `0x18000df2c`
- end: `0x18000e5ec`
- name: `?InitializeConfig@AOMDHandler@@AEAAXXZ`
- size: `1728`
- prototype: `void __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a7e4`

## callees

- `0x180001178`
- `0x18000404c`
- `0x1800040c0`
- `0x180004134`
- `0x180006268`
- `0x1800062b4`
- `0x18000df2c`
- `0x18000e964`
- `0x18000f144`
- `0x1800164a4`

## string_xrefs

- `0x18000df88`: `InitializeConfig_BugcheckThresholdOverrideNotFound`
- `0x18000dfd0`: `InitializeConfig_AppCrashThresholdOverrideNotFound`
- `0x18000e012`: `InitializeConfig_PageNotZeroThresholdOverrideNotFound`
- `0x18000e054`: `InitializeConfig_StoreCorruptionThresholdOverrideNotFound`
- `0x18000e096`: `InitializeConfig_LookbackTimeNotFound`
- `0x18000e0d8`: `InitializeConfig_CooldownTimeNotFound`
- `0x18000e11a`: `InitializeConfig_SelfThrottleTimeNotFound`
- `0x18000e186`: `InitializeConfig_MdSchedLastRunTimeNotFound`
- `0x18000e1d0`: `InitializeConfig_LastScanDecisionTimeNotFound`
- `0x18000e21a`: `InitializeConfig_LastScanOfferedTimeNotFound`
- `0x18000e264`: `InitializeConfig_NumTimesScanOfferedNotFound`
- `0x18000e2b3`: `InitializeConfig_BugCheckThreshold`
- `0x18000e313`: `InitializeConfig_AppCrashThreshold`
- `0x18000e36d`: `InitializeConfig_PageNotZeroThreshold`
- `0x18000e3c7`: `InitializeConfig_StoreCorruptionThreshold`
- `0x18000e421`: `InitializeConfig_LookbackTimeHours`
- `0x18000e47b`: `InitializeConfig_CooldownTimeHours`
- `0x18000e4d5`: `InitializeConfig_SelfThrottleTimeHours`
- `0x18000e59b`: `InitializeConfig_NumScanOffersSinceLastDecision`

## pseudocode

```c
void __fastcall AOMDHandler::InitializeConfig(AOMDHandler *this)
{
  int *v2; // rbx
  unsigned int value_dword; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // edx
  unsigned int v11; // eax
  unsigned int value_qword; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  int v16; // ebx
  const struct _tlgProvider_t *v17; // rax
  int v18; // r8d
  int v19; // r9d
  int v20; // ebx
  const struct _tlgProvider_t *v21; // rax
  int v22; // r8d
  int v23; // r9d
  int v24; // ebx
  const struct _tlgProvider_t *v25; // rax
  int v26; // r8d
  int v27; // r9d
  int v28; // ebx
  const struct _tlgProvider_t *v29; // rax
  int v30; // r8d
  int v31; // r9d
  int v32; // ebx
  const struct _tlgProvider_t *v33; // rax
  int v34; // r8d
  int v35; // r9d
  int v36; // ebx
  const struct _tlgProvider_t *v37; // rax
  int v38; // r8d
  int v39; // r9d
  int v40; // ebx
  const struct _tlgProvider_t *v41; // rax
  __int64 v42; // rcx
  int v43; // r8d
  int v44; // r9d
  __int64 v45; // rcx
  __int64 v46; // rcx
  int v47; // ebx
  const struct _tlgProvider_t *v48; // rax
  int v49; // r8d
  const char *v50; // r9
  const wchar_t *v51; // [rsp+30h] [rbp-38h] BYREF
  __int64 v52; // [rsp+38h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v54; // [rsp+78h] [rbp+10h] BYREF
  const wchar_t *v55; // [rsp+80h] [rbp+18h] BYREF

  try
  {
    v2 = (int *)((char *)this + 60);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::__private_IsEnabled() )
    {
      *v2 = 1;
    }
    else
    {
      value_dword = wil::reg::get_value_dword_nothrow<unsigned long,0>(
                      -2147483646,
                      L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
                      L"AOMDBugCheckThreshold",
                      (char *)this + 60);
      v51 = L"InitializeConfig_BugcheckThresholdOverrideNotFound";
      v52 = 50;
      TlgHelper::LogIfFailedExpected(&v51, value_dword);
    }
    v4 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
           -2147483646,
           L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
           L"AOMDAppCrashThreshold",
           (char *)this + 56);
    v51 = L"InitializeConfig_AppCrashThresholdOverrideNotFound";
    v52 = 50;
    TlgHelper::LogIfFailedExpected(&v51, v4);
    v5 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
           -2147483646,
           L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
           L"AOMDPageNotZeroThreshold",
           (char *)this + 64);
    v51 = L"InitializeConfig_PageNotZeroThresholdOverrideNotFound";
    v52 = 53;
    TlgHelper::LogIfFailedExpected(&v51, v5);
    v6 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
           -2147483646,
           L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
           L"AOMDStoreCorruptionThreshold",
           (char *)this + 68);
    v51 = L"InitializeConfig_StoreCorruptionThresholdOverrideNotFound";
    v52 = 57;
    TlgHelper::LogIfFailedExpected(&v51, v6);
    v7 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
           -2147483646,
           L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
           L"AOMDLookbackTimeHours",
           (char *)this + 72);
    v51 = L"InitializeConfig_LookbackTimeNotFound";
    v52 = 37;
    TlgHelper::LogIfFailedExpected(&v51, v7);
    v8 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
           -2147483646,
           L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
           L"AOMDCooldownTimeHours",
           (char *)this + 76);
    v51 = L"InitializeConfig_CooldownTimeNotFound";
    v52 = 37;
    TlgHelper::LogIfFailedExpected(&v51, v8);
    v9 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
           -2147483646,
           L"SOFTWARE\\Microsoft\\MemoryDiagnostic",
           L"AOMDSelfThrottleTimeHours",
           (char *)this + 80);
    v51 = L"InitializeConfig_SelfThrottleTimeNotFound";
    v52 = 41;
    TlgHelper::LogIfFailedExpected(&v51, v9);
    v10 = *((_DWORD *)this + 18);
    if ( v10 > 0x2238 )
      v10 = 8760;
    v11 = *((_DWORD *)this + 19);
    if ( v11 > 0x2238 )
      v11 = 8760;
    *((_DWORD *)this + 19) = v11;
    if ( !v10 )
      v10 = 1;
    *((_DWORD *)this + 18) = v10;
    value_qword = wil::reg::get_value_qword_nothrow<unsigned __int64,0>(
                    -2147483646,
                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\MemoryDiagnostic",
                    L"LastRunTime",
                    (char *)this + 120);
    v51 = L"InitializeConfig_MdSchedLastRunTimeNotFound";
    v52 = 43;
    TlgHelper::LogIfFailedExpected(&v51, value_qword);
    v13 = wil::reg::get_value_qword_nothrow<unsigned __int64,0>(
            -2147483647,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
            L"AOMDLastScanDecisionTime",
            (char *)this + 96);
    v51 = L"InitializeConfig_LastScanDecisionTimeNotFound";
    v52 = 45;
    TlgHelper::LogIfFailedExpected(&v51, v13);
    v14 = wil::reg::get_value_qword_nothrow<unsigned __int64,0>(
            -2147483647,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
            L"AOMDLastScanOfferedTime",
            (char *)this + 104);
    v51 = L"InitializeConfig_LastScanOfferedTimeNotFound";
    v52 = 44;
    TlgHelper::LogIfFailedExpected(&v51, v14);
    v15 = wil::reg::get_value_dword_nothrow<unsigned long,0>(
            -2147483647,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
            L"AOMDNumScanOffersSinceLastDecision",
            (char *)this + 112);
    v51 = L"InitializeConfig_NumTimesScanOfferedNotFound";
    v52 = 44;
    TlgHelper::LogIfFailedExpected(&v51, v15);
    v16 = *v2;
    v17 = TlgHelper::Provider();
    if ( *(_DWORD *)v17 > 4u && (*((_BYTE *)v17 + 16) & 2) != 0 && (*((_QWORD *)v17 + 3) & 2LL) == *((_QWORD *)v17 + 3) )
    {
      LODWORD(v54) = v16;
      v55 = L"InitializeConfig_BugCheckThreshold";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v17,
        (unsigned int)&unk_18002AB49,
        v18,
        v19,
        (__int64)&v55,
        (__int64)&v54);
    }
    v20 = *((_DWORD *)this + 14);
    v21 = TlgHelper::Provider();
    if ( *(_DWORD *)v21 > 4u && (*((_BYTE *)v21 + 16) & 2) != 0 && (*((_QWORD *)v21 + 3) & 2LL) == *((_QWORD *)v21 + 3) )
    {
      LODWORD(v54) = v20;
      v55 = L"InitializeConfig_AppCrashThreshold";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v21,
        (unsigned int)&unk_18002AB49,
        v22,
        v23,
        (__int64)&v55,
        (__int64)&v54);
    }
    v24 = *((_DWORD *)this + 16);
    v25 = TlgHelper::Provider();
    if ( *(_DWORD *)v25 > 4u && (*((_BYTE *)v25 + 16) & 2) != 0 && (*((_QWORD *)v25 + 3) & 2LL) == *((_QWORD *)v25 + 3) )
    {
      LODWORD(v54) = v24;
      v55 = L"InitializeConfig_PageNotZeroThreshold";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v25,
        (unsigned int)&unk_18002AB49,
        v26,
        v27,
        (__int64)&v55,
        (__int64)&v54);
    }
    v28 = *((_DWORD *)this + 17);
    v29 = TlgHelper::Provider();
    if ( *(_DWORD *)v29 > 4u && (*((_BYTE *)v29 + 16) & 2) != 0 && (*((_QWORD *)v29 + 3) & 2LL) == *((_QWORD *)v29 + 3) )
    {
      LODWORD(v54) = v28;
      v55 = L"InitializeConfig_StoreCorruptionThreshold";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v29,
        (unsigned int)&unk_18002AB49,
        v30,
        v31,
        (__int64)&v55,
        (__int64)&v54);
    }
    v32 = *((_DWORD *)this + 18);
    v33 = TlgHelper::Provider();
    if ( *(_DWORD *)v33 > 4u && (*((_BYTE *)v33 + 16) & 2) != 0 && (*((_QWORD *)v33 + 3) & 2LL) == *((_QWORD *)v33 + 3) )
    {
      LODWORD(v54) = v32;
      v55 = L"InitializeConfig_LookbackTimeHours";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v33,
        (unsigned int)&unk_18002AB49,
        v34,
        v35,
        (__int64)&v55,
        (__int64)&v54);
    }
    v36 = *((_DWORD *)this + 19);
    v37 = TlgHelper::Provider();
    if ( *(_DWORD *)v37 > 4u && (*((_BYTE *)v37 + 16) & 2) != 0 && (*((_QWORD *)v37 + 3) & 2LL) == *((_QWORD *)v37 + 3) )
    {
      LODWORD(v54) = v36;
      v55 = L"InitializeConfig_CooldownTimeHours";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v37,
        (unsigned int)&unk_18002AB49,
        v38,
        v39,
        (__int64)&v55,
        (__int64)&v54);
    }
    v40 = *((_DWORD *)this + 20);
    v41 = TlgHelper::Provider();
    if ( *(_DWORD *)v41 > 4u && (*((_BYTE *)v41 + 16) & 2) != 0 )
    {
      v42 = *((_QWORD *)v41 + 3) & 2LL;
      if ( v42 == *((_QWORD *)v41 + 3) )
      {
        LODWORD(v54) = v40;
        v55 = L"InitializeConfig_SelfThrottleTimeHours";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v41,
          (unsigned int)&unk_18002AB49,
          v43,
          v44,
          (__int64)&v55,
          (__int64)&v54);
      }
    }
    v54 = *((_QWORD *)this + 15);
    TlgHelper::LogInfoFiletime<unsigned short const (&)[36],_FILETIME>(v42, &v54);
    v54 = *((_QWORD *)this + 12);
    TlgHelper::LogInfoFiletime<unsigned short const (&)[38],_FILETIME>(v45, &v54);
    v54 = *((_QWORD *)this + 13);
    TlgHelper::LogInfoFiletime<unsigned short const (&)[37],_FILETIME>(v46, &v54);
    v47 = *((_DWORD *)this + 28);
    v48 = TlgHelper::Provider();
    if ( *(_DWORD *)v48 > 4u && (*((_BYTE *)v48 + 16) & 2) != 0 && (*((_QWORD *)v48 + 3) & 2LL) == *((_QWORD *)v48 + 3) )
    {
      LODWORD(v54) = v47;
      v55 = L"InitializeConfig_NumScanOffersSinceLastDecision";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v48,
        (unsigned int)&unk_18002AB49,
        v49,
        (_DWORD)v50,
        (__int64)&v55,
        (__int64)&v54);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x2D9,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      v50);
  }
}

```

## disassembly

```asm
0x18000df2c  mov     [rsp+arg_0], rbx
0x18000df31  mov     [rsp+arg_18], rsi
0x18000df36  push    rdi
0x18000df37  push    r12
0x18000df39  push    r13
0x18000df3b  push    r14
0x18000df3d  push    r15
0x18000df3f  sub     rsp, 40h
0x18000df43  mov     r15, rcx
0x18000df46  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59116012@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59116012@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012> `wil::Feature<__WilFeatureTraits_Feature_59116012>::GetImpl(void)'::`2'::impl
0x18000df4d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59116012@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59116012>::__private_IsEnabled(void)
0x18000df52  lea     rbx, [r15+3Ch]
0x18000df56  lea     rsi, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MemoryDiagnostic"
0x18000df5d  mov     rdi, 0FFFFFFFF80000002h
0x18000df64  test    al, al
0x18000df66  jz      short loc_18000DF73
0x18000df68  mov     r14d, 1
0x18000df6e  mov     [rbx], r14d
0x18000df71  jmp     short loc_18000DFBA
0x18000df73  mov     r9, rbx
0x18000df76  lea     r8, aAomdbugcheckth; "AOMDBugCheckThreshold"
0x18000df7d  mov     rdx, rsi
0x18000df80  mov     rcx, rdi
0x18000df83  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000df88  lea     rcx, aInitializeconf; "InitializeConfig_BugcheckThresholdOverr"...
0x18000df8f  mov     qword ptr [rsp+68h+var_38], rcx
0x18000df94  mov     qword ptr [rsp+68h+var_38+8], 32h ; '2'
0x18000df9d  movaps  xmm0, [rsp+68h+var_38]
0x18000dfa2  movdqa  [rsp+68h+var_38], xmm0
0x18000dfa8  mov     edx, eax
0x18000dfaa  lea     rcx, [rsp+68h+var_38]
0x18000dfaf  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000dfb4  mov     r14d, 1
0x18000dfba  lea     r9, [r15+38h]
0x18000dfbe  lea     r8, aAomdappcrashth; "AOMDAppCrashThreshold"
0x18000dfc5  mov     rdx, rsi
0x18000dfc8  mov     rcx, rdi
0x18000dfcb  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000dfd0  lea     rcx, aInitializeconf_13; "InitializeConfig_AppCrashThresholdOverr"...
0x18000dfd7  mov     qword ptr [rsp+68h+var_38], rcx
0x18000dfdc  mov     qword ptr [rsp+68h+var_38+8], 32h ; '2'
0x18000dfe5  movaps  xmm0, [rsp+68h+var_38]
0x18000dfea  movdqa  [rsp+68h+var_38], xmm0
0x18000dff0  mov     edx, eax
0x18000dff2  lea     rcx, [rsp+68h+var_38]
0x18000dff7  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000dffc  lea     r9, [r15+40h]
0x18000e000  lea     r8, aAomdpagenotzer; "AOMDPageNotZeroThreshold"
0x18000e007  mov     rdx, rsi
0x18000e00a  mov     rcx, rdi
0x18000e00d  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000e012  lea     rcx, aInitializeconf_14; "InitializeConfig_PageNotZeroThresholdOv"...
0x18000e019  mov     qword ptr [rsp+68h+var_38], rcx
0x18000e01e  mov     qword ptr [rsp+68h+var_38+8], 35h ; '5'
0x18000e027  movaps  xmm0, [rsp+68h+var_38]
0x18000e02c  movdqa  [rsp+68h+var_38], xmm0
0x18000e032  mov     edx, eax
0x18000e034  lea     rcx, [rsp+68h+var_38]
0x18000e039  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000e03e  lea     r9, [r15+44h]
0x18000e042  lea     r8, aAomdstorecorru; "AOMDStoreCorruptionThreshold"
0x18000e049  mov     rdx, rsi
0x18000e04c  mov     rcx, rdi
0x18000e04f  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000e054  lea     rcx, aInitializeconf_0; "InitializeConfig_StoreCorruptionThresho"...
0x18000e05b  mov     qword ptr [rsp+68h+var_38], rcx
0x18000e060  mov     qword ptr [rsp+68h+var_38+8], 39h ; '9'
0x18000e069  movaps  xmm0, [rsp+68h+var_38]
0x18000e06e  movdqa  [rsp+68h+var_38], xmm0
0x18000e074  mov     edx, eax
0x18000e076  lea     rcx, [rsp+68h+var_38]
0x18000e07b  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000e080  lea     r9, [r15+48h]
0x18000e084  lea     r8, aAomdlookbackti; "AOMDLookbackTimeHours"
0x18000e08b  mov     rdx, rsi
0x18000e08e  mov     rcx, rdi
0x18000e091  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000e096  lea     rcx, aInitializeconf_7; "InitializeConfig_LookbackTimeNotFound"
0x18000e09d  mov     qword ptr [rsp+68h+var_38], rcx
0x18000e0a2  mov     qword ptr [rsp+68h+var_38+8], 25h ; '%'
0x18000e0ab  movaps  xmm0, [rsp+68h+var_38]
0x18000e0b0  movdqa  [rsp+68h+var_38], xmm0
0x18000e0b6  mov     edx, eax
0x18000e0b8  lea     rcx, [rsp+68h+var_38]
0x18000e0bd  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000e0c2  lea     r9, [r15+4Ch]
0x18000e0c6  lea     r8, aAomdcooldownti; "AOMDCooldownTimeHours"
0x18000e0cd  mov     rdx, rsi
0x18000e0d0  mov     rcx, rdi
0x18000e0d3  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000e0d8  lea     rcx, aInitializeconf_16; "InitializeConfig_CooldownTimeNotFound"
0x18000e0df  mov     qword ptr [rsp+68h+var_38], rcx
0x18000e0e4  mov     qword ptr [rsp+68h+var_38+8], 25h ; '%'
0x18000e0ed  movaps  xmm0, [rsp+68h+var_38]
0x18000e0f2  movdqa  [rsp+68h+var_38], xmm0
0x18000e0f8  mov     edx, eax
0x18000e0fa  lea     rcx, [rsp+68h+var_38]
0x18000e0ff  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000e104  lea     r9, [r15+50h]
0x18000e108  lea     r8, aAomdselfthrott; "AOMDSelfThrottleTimeHours"
0x18000e10f  mov     rdx, rsi
0x18000e112  mov     rcx, rdi
0x18000e115  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000e11a  lea     rcx, aInitializeconf_12; "InitializeConfig_SelfThrottleTimeNotFou"...
0x18000e121  mov     qword ptr [rsp+68h+var_38], rcx
0x18000e126  mov     qword ptr [rsp+68h+var_38+8], 29h ; ')'
0x18000e12f  movaps  xmm0, [rsp+68h+var_38]
0x18000e134  movdqa  [rsp+68h+var_38], xmm0
0x18000e13a  mov     edx, eax
0x18000e13c  lea     rcx, [rsp+68h+var_38]
0x18000e141  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000e146  mov     edx, [r15+48h]
0x18000e14a  mov     ecx, 2238h
0x18000e14f  cmp     edx, ecx
0x18000e151  cmova   edx, ecx
0x18000e154  mov     eax, [r15+4Ch]
0x18000e158  cmp     eax, ecx
0x18000e15a  cmova   eax, ecx
0x18000e15d  mov     [r15+4Ch], eax
0x18000e161  cmp     edx, r14d
0x18000e164  cmovb   edx, r14d
0x18000e168  mov     [r15+48h], edx
0x18000e16c  lea     r9, [r15+78h]
0x18000e170  lea     r8, aLastruntime; "LastRunTime"
0x18000e177  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000e17e  mov     rcx, rdi
0x18000e181  call    ??$get_value_qword_nothrow@_K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEA_K@Z; wil::reg::get_value_qword_nothrow<unsigned __int64,0>(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *)
0x18000e186  lea     rcx, aInitializeconf_18; "InitializeConfig_MdSchedLastRunTimeNotF"...
0x18000e18d  mov     qword ptr [rsp+68h+var_38], rcx
0x18000e192  mov     qword ptr [rsp+68h+var_38+8], 2Bh ; '+'
0x18000e19b  movaps  xmm0, [rsp+68h+var_38]
0x18000e1a0  movdqa  [rsp+68h+var_38], xmm0
0x18000e1a6  mov     edx, eax
0x18000e1a8  lea     rcx, [rsp+68h+var_38]
0x18000e1ad  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000e1b2  lea     r9, [r15+60h]
0x18000e1b6  lea     r8, ValueName; "AOMDLastScanDecisionTime"
0x18000e1bd  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000e1c4  mov     rcx, 0FFFFFFFF80000001h
0x18000e1cb  call    ??$get_value_qword_nothrow@_K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEA_K@Z; wil::reg::get_value_qword_nothrow<unsigned __int64,0>(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *)
0x18000e1d0  lea     rcx, aInitializeconf_17; "InitializeConfig_LastScanDecisionTimeNo"...
0x18000e1d7  mov     qword ptr [rsp+68h+var_38], rcx
0x18000e1dc  mov     qword ptr [rsp+68h+var_38+8], 2Dh ; '-'
0x18000e1e5  movaps  xmm0, [rsp+68h+var_38]
0x18000e1ea  movdqa  [rsp+68h+var_38], xmm0
0x18000e1f0  mov     edx, eax
0x18000e1f2  lea     rcx, [rsp+68h+var_38]
0x18000e1f7  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000e1fc  lea     r9, [r15+68h]
0x18000e200  lea     r8, aAomdlastscanof; "AOMDLastScanOfferedTime"
0x18000e207  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000e20e  mov     rcx, 0FFFFFFFF80000001h
0x18000e215  call    ??$get_value_qword_nothrow@_K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEA_K@Z; wil::reg::get_value_qword_nothrow<unsigned __int64,0>(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *)
0x18000e21a  lea     r8, aInitializeconf_2; "InitializeConfig_LastScanOfferedTimeNot"...
0x18000e221  mov     qword ptr [rsp+68h+var_38], r8
0x18000e226  mov     qword ptr [rsp+68h+var_38+8], 2Ch ; ','
0x18000e22f  movaps  xmm0, [rsp+68h+var_38]
0x18000e234  movdqa  [rsp+68h+var_38], xmm0
0x18000e23a  mov     edx, eax
0x18000e23c  lea     rcx, [rsp+68h+var_38]
0x18000e241  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000e246  lea     r9, [r15+70h]
0x18000e24a  lea     r8, aAomdnumscanoff; "AOMDNumScanOffersSinceLastDecision"
0x18000e251  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000e258  mov     rcx, 0FFFFFFFF80000001h
0x18000e25f  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000e264  lea     rcx, aInitializeconf_19; "InitializeConfig_NumTimesScanOfferedNot"...
0x18000e26b  mov     qword ptr [rsp+68h+var_38], rcx
0x18000e270  mov     qword ptr [rsp+68h+var_38+8], 2Ch ; ','
0x18000e279  movaps  xmm0, [rsp+68h+var_38]
0x18000e27e  movdqa  [rsp+68h+var_38], xmm0
0x18000e284  mov     edx, eax
0x18000e286  lea     rcx, [rsp+68h+var_38]
0x18000e28b  call    ?LogIfFailedExpected@TlgHelper@@SA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@J@Z; TlgHelper::LogIfFailedExpected(std::basic_string_view<ushort>,long)
0x18000e290  mov     ebx, [rbx]
0x18000e292  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000e297  cmp     dword ptr [rax], 4
0x18000e29a  jbe     short loc_18000E2E8
0x18000e29c  test    byte ptr [rax+10h], 2
0x18000e2a0  jz      short loc_18000E2E8
0x18000e2a2  mov     rcx, [rax+18h]
0x18000e2a6  and     ecx, 2
0x18000e2a9  cmp     rcx, [rax+18h]
0x18000e2ad  jnz     short loc_18000E2E8
0x18000e2af  mov     dword ptr [rsp+68h+arg_8], ebx
0x18000e2b3  lea     rcx, aInitializeconf_5; "InitializeConfig_BugCheckThreshold"
0x18000e2ba  mov     [rsp+68h+arg_10], rcx
0x18000e2c2  lea     rcx, [rsp+68h+arg_8]
0x18000e2c7  mov     [rsp+68h+var_40], rcx
0x18000e2cc  lea     rcx, [rsp+68h+arg_10]
0x18000e2d4  mov     [rsp+68h+var_48], rcx
0x18000e2d9  lea     rdx, unk_18002AB49
0x18000e2e0  mov     rcx, rax
0x18000e2e3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e2e8  mov     ebx, [r15+38h]
0x18000e2ec  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000e2f1  mov     r12d, 4
0x18000e2f7  cmp     [rax], r12d
0x18000e2fa  jbe     short loc_18000E348
0x18000e2fc  test    byte ptr [rax+10h], 2
0x18000e300  jz      short loc_18000E348
0x18000e302  mov     rcx, [rax+18h]
0x18000e306  and     ecx, 2
0x18000e309  cmp     rcx, [rax+18h]
0x18000e30d  jnz     short loc_18000E348
0x18000e30f  mov     dword ptr [rsp+68h+arg_8], ebx
0x18000e313  lea     rcx, aInitializeconf_3; "InitializeConfig_AppCrashThreshold"
0x18000e31a  mov     [rsp+68h+arg_10], rcx
0x18000e322  lea     rcx, [rsp+68h+arg_8]
0x18000e327  mov     [rsp+68h+var_40], rcx
0x18000e32c  lea     rcx, [rsp+68h+arg_10]
0x18000e334  mov     [rsp+68h+var_48], rcx
0x18000e339  lea     rdx, unk_18002AB49
0x18000e340  mov     rcx, rax
0x18000e343  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e348  mov     ebx, [r15+40h]
0x18000e34c  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000e351  cmp     [rax], r12d
0x18000e354  jbe     short loc_18000E3A2
0x18000e356  test    byte ptr [rax+10h], 2
0x18000e35a  jz      short loc_18000E3A2
0x18000e35c  mov     rcx, [rax+18h]
0x18000e360  and     ecx, 2
0x18000e363  cmp     rcx, [rax+18h]
0x18000e367  jnz     short loc_18000E3A2
0x18000e369  mov     dword ptr [rsp+68h+arg_8], ebx
0x18000e36d  lea     rcx, aInitializeconf_8; "InitializeConfig_PageNotZeroThreshold"
0x18000e374  mov     [rsp+68h+arg_10], rcx
0x18000e37c  lea     rcx, [rsp+68h+arg_8]
0x18000e381  mov     [rsp+68h+var_40], rcx
0x18000e386  lea     rcx, [rsp+68h+arg_10]
0x18000e38e  mov     [rsp+68h+var_48], rcx
0x18000e393  lea     rdx, unk_18002AB49
0x18000e39a  mov     rcx, rax
0x18000e39d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e3a2  mov     ebx, [r15+44h]
0x18000e3a6  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000e3ab  cmp     [rax], r12d
0x18000e3ae  jbe     short loc_18000E3FC
0x18000e3b0  test    byte ptr [rax+10h], 2
0x18000e3b4  jz      short loc_18000E3FC
0x18000e3b6  mov     rcx, [rax+18h]
0x18000e3ba  and     ecx, 2
0x18000e3bd  cmp     rcx, [rax+18h]
0x18000e3c1  jnz     short loc_18000E3FC
0x18000e3c3  mov     dword ptr [rsp+68h+arg_8], ebx
0x18000e3c7  lea     rcx, aInitializeconf_9; "InitializeConfig_StoreCorruptionThresho"...
0x18000e3ce  mov     [rsp+68h+arg_10], rcx
0x18000e3d6  lea     rcx, [rsp+68h+arg_8]
0x18000e3db  mov     [rsp+68h+var_40], rcx
0x18000e3e0  lea     rcx, [rsp+68h+arg_10]
0x18000e3e8  mov     [rsp+68h+var_48], rcx
0x18000e3ed  lea     rdx, unk_18002AB49
0x18000e3f4  mov     rcx, rax
0x18000e3f7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e3fc  mov     ebx, [r15+48h]
0x18000e400  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000e405  cmp     [rax], r12d
0x18000e408  jbe     short loc_18000E456
0x18000e40a  test    byte ptr [rax+10h], 2
0x18000e40e  jz      short loc_18000E456
0x18000e410  mov     rcx, [rax+18h]
0x18000e414  and     ecx, 2
0x18000e417  cmp     rcx, [rax+18h]
0x18000e41b  jnz     short loc_18000E456
0x18000e41d  mov     dword ptr [rsp+68h+arg_8], ebx
0x18000e421  lea     rcx, aInitializeconf_1; "InitializeConfig_LookbackTimeHours"
0x18000e428  mov     [rsp+68h+arg_10], rcx
0x18000e430  lea     rcx, [rsp+68h+arg_8]
0x18000e435  mov     [rsp+68h+var_40], rcx
0x18000e43a  lea     rcx, [rsp+68h+arg_10]
0x18000e442  mov     [rsp+68h+var_48], rcx
0x18000e447  lea     rdx, unk_18002AB49
0x18000e44e  mov     rcx, rax
0x18000e451  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e456  mov     ebx, [r15+4Ch]
0x18000e45a  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000e45f  cmp     [rax], r12d
0x18000e462  jbe     short loc_18000E4B0
0x18000e464  test    byte ptr [rax+10h], 2
0x18000e468  jz      short loc_18000E4B0
0x18000e46a  mov     rcx, [rax+18h]
0x18000e46e  and     ecx, 2
0x18000e471  cmp     rcx, [rax+18h]
0x18000e475  jnz     short loc_18000E4B0
0x18000e477  mov     dword ptr [rsp+68h+arg_8], ebx
0x18000e47b  lea     rcx, aInitializeconf_6; "InitializeConfig_CooldownTimeHours"
0x18000e482  mov     [rsp+68h+arg_10], rcx
0x18000e48a  lea     rcx, [rsp+68h+arg_8]
0x18000e48f  mov     [rsp+68h+var_40], rcx
0x18000e494  lea     rcx, [rsp+68h+arg_10]
0x18000e49c  mov     [rsp+68h+var_48], rcx
0x18000e4a1  lea     rdx, unk_18002AB49
0x18000e4a8  mov     rcx, rax
0x18000e4ab  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e4b0  mov     ebx, [r15+50h]
0x18000e4b4  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000e4b9  cmp     [rax], r12d
0x18000e4bc  jbe     short loc_18000E50A
0x18000e4be  test    byte ptr [rax+10h], 2
  ... truncated ...
```
