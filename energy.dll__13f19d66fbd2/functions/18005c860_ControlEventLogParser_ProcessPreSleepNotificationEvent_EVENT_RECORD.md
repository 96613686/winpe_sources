# ControlEventLogParser::ProcessPreSleepNotificationEvent(_EVENT_RECORD *)

- ea: `0x18005c860`
- end: `0x18005d138`
- name: `?ProcessPreSleepNotificationEvent@ControlEventLogParser@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `2264`
- prototype: `void(ControlEventLogParser *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800487b8`

## callees

- `0x180008740`
- `0x180008da0`
- `0x18000b6f0`
- `0x18001be60`
- `0x18001c8cc`
- `0x18001f6f4`
- `0x1800253e0`
- `0x180027e10`
- `0x180027f10`
- `0x18003362c`
- `0x180033a70`
- `0x180036c88`
- `0x180037090`
- `0x18003bce0`
- `0x18004ca90`
- `0x180059198`
- `0x180059514`
- `0x18005c860`
- `0x18005d56c`

## string_xrefs

- `0x18005ca0d`: `RequestorProcessId`
- `0x18005d002`: `RequestorProcessId`
- `0x18005ca2e`: `RequestorServiceTag`
- `0x18005d052`: `RequestorServiceTag`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall ControlEventLogParser::ProcessPreSleepNotificationEvent(
        ControlEventLogParser *this,
        struct _EVENT_RECORD *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rbx
  __int64 v14; // rbx
  void *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rax
  _BYTE *v18; // rdx
  void *v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rax
  _BYTE *v22; // rdx
  void *v23; // rdi
  __int64 v24; // rax
  __int64 v25; // rax
  _BYTE *v26; // rdx
  void *v27; // r14
  int v28; // ebx
  unsigned __int64 v29; // rdi
  int v30; // eax
  __int64 v31; // r14
  void *v32; // rax
  __int64 v33; // rax
  _BYTE *v34; // rdx
  void *v35; // rax
  __int64 v36; // rax
  _BYTE *v37; // rdx
  void *v38; // rdi
  __int64 v39; // rax
  __int64 v40; // rax
  _BYTE *v41; // rdx
  void *v42; // rdi
  __int64 v43; // rax
  __int64 v44; // rax
  _BYTE *v45; // rdx
  void *v46; // rdi
  __int64 v47; // rax
  __int64 v48; // rax
  _BYTE *v49; // rdx
  void *v50; // rax
  __int64 v51; // rax
  _BYTE *v52; // rdx
  void *v53; // rax
  __int64 v54; // rax
  _BYTE *v55; // rdx
  void *v56; // rax
  __int64 v57; // rax
  _BYTE *v58; // rdx
  void *v59; // rdi
  __int64 v60; // rax
  __int64 v61; // rax
  _BYTE *v62; // rdx
  __int64 v63; // rcx
  _BYTE *v64; // rdx
  unsigned __int8 v65; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int8 v66; // [rsp+31h] [rbp-68h] BYREF
  unsigned __int8 v67[6]; // [rsp+32h] [rbp-67h] BYREF
  __int64 v68; // [rsp+38h] [rbp-61h] BYREF
  unsigned int v69; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v70; // [rsp+44h] [rbp-55h] BYREF
  unsigned int v71; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v72; // [rsp+4Ch] [rbp-4Dh] BYREF
  unsigned int v73; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v74; // [rsp+54h] [rbp-45h] BYREF
  unsigned int v75; // [rsp+58h] [rbp-41h] BYREF
  void *v76; // [rsp+60h] [rbp-39h]
  unsigned int v77; // [rsp+68h] [rbp-31h] BYREF
  __int64 v78; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int64 v79; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v80[32]; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v81[4]; // [rsp+A0h] [rbp+7h] BYREF

  v71 = 0;
  v67[0] = 0;
  v73 = 0;
  v77 = 0;
  v72 = 0;
  v69 = 0;
  std::wstring::wstring(v81);
  v74 = 0;
  v75 = 0;
  v70 = 0;
  v79 = 0;
  v66 = 2;
  v65 = 3;
  if ( GetEventProperty(a2, L"Timestamp", &v79) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4, v6);
    goto LABEL_136;
  }
  if ( GetEventProperty(a2, L"TargetState", &v70)
    || GetEventProperty(a2, L"EffectiveState", &v71)
    || GetEventProperty(a2, L"Reason", &v77) )
  {
LABEL_11:
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9);
    goto LABEL_136;
  }
  if ( a2->EventHeader.EventDescriptor.Version )
  {
    if ( GetEventProperty(a2, L"RemainingBatteryCapacity", &v72) || GetEventProperty(a2, L"MaxBatteryCapacity", &v73) )
      goto LABEL_11;
    if ( a2->EventHeader.EventDescriptor.Version >= 2u )
    {
      if ( GetEventProperty(a2, L"LidState", &v65) )
        goto LABEL_33;
      if ( v65 >= 4u )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
        v65 = 3;
      }
    }
  }
  else
  {
    v72 = 0;
    v73 = 0;
  }
  if ( a2->EventHeader.EventDescriptor.Version < 3u )
  {
    v69 = -1;
    v74 = -1;
    v75 = -1;
    std::wstring::assign(v81, &qword_18009CA18);
  }
  else if ( GetEventProperty(a2, L"RequestorCallerType", &v69)
         || GetEventProperty(a2, L"RequestorProcessId", &v74)
         || GetEventProperty(a2, L"RequestorServiceTag", &v75)
         || (unsigned int)GetEventProperty(a2) )
  {
    goto LABEL_33;
  }
  if ( a2->EventHeader.EventDescriptor.Version >= 4u )
  {
    if ( GetEventProperty(a2, L"ExternalMonitorState", &v66) )
    {
LABEL_33:
      MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
      goto LABEL_136;
    }
    if ( v66 >= 3u )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
      v66 = 2;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NU4MP>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NU4MP>::GetImpl'::`2'::impl)
    && a2->EventHeader.EventDescriptor.Version >= 5u )
  {
    if ( GetEventProperty(a2, L"ExternalMonitorSource", v67) )
      goto LABEL_33;
    if ( v67[0] >= 4u )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
      v67[0] = 3;
    }
  }
  v13 = *(_QWORD *)(*(_QWORD *)this + 8LL);
  if ( v13 != **(_QWORD **)this )
  {
    v14 = *(_QWORD *)(v13 - 8);
    *(_BYTE *)(v14 + 20) = 1;
    *(_QWORD *)(v14 + 96) = v79;
    *(_BYTE *)(v14 + 104) = 1;
    if ( (unsigned int)IsActive((struct OsStateInstance *)v14) )
    {
      if ( *(_DWORD *)(v14 + 152) == 1 )
        *(_DWORD *)(v14 + 152) = 0;
      if ( !*(_BYTE *)(v14 + 182) && a2->EventHeader.EventDescriptor.Version >= 2u )
      {
        v15 = operator new(0x50u);
        v78 = (__int64)v15;
        if ( v15 )
        {
          v16 = std::wstring::wstring((__int64)v80, &LidStateStrings[4 * v65]);
          v17 = CustomData::CustomData(v15, L"LidState", v16);
        }
        else
        {
          v17 = 0;
        }
        v68 = v17;
        v18 = *(_BYTE **)(v14 + 216);
        if ( v18 == *(_BYTE **)(v14 + 224) )
        {
          std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
            (void **)(v14 + 208),
            v18,
            &v68);
        }
        else
        {
          *(_QWORD *)v18 = v17;
          *(_QWORD *)(v14 + 216) += 8LL;
        }
        *(_BYTE *)(v14 + 182) = 1;
      }
      if ( !*(_BYTE *)(v14 + 181) && a2->EventHeader.EventDescriptor.Version >= 4u )
      {
        v19 = operator new(0x50u);
        v78 = (__int64)v19;
        if ( v19 )
        {
          v20 = std::wstring::wstring((__int64)v80, &ExternalMonitorStateStrings[4 * v66]);
          v21 = CustomData::CustomData(v19, L"ExternalMonitorState", v20);
        }
        else
        {
          v21 = 0;
        }
        v68 = v21;
        v22 = *(_BYTE **)(v14 + 216);
        if ( v22 == *(_BYTE **)(v14 + 224) )
        {
          std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
            (void **)(v14 + 208),
            v22,
            &v68);
        }
        else
        {
          *(_QWORD *)v22 = v21;
          *(_QWORD *)(v14 + 216) += 8LL;
        }
        *(_BYTE *)(v14 + 181) = 1;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NU4MP>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NU4MP>::GetImpl'::`2'::impl)
        && !*(_BYTE *)(v14 + 180)
        && a2->EventHeader.EventDescriptor.Version >= 5u )
      {
        v23 = operator new(0x50u);
        v78 = (__int64)v23;
        if ( v23 )
        {
          v24 = std::wstring::wstring((__int64)v80, &ExternalMonitorSourceStrings[4 * v67[0]]);
          v25 = CustomData::CustomData(v23, L"ExternalMonitorSource", v24);
        }
        else
        {
          v25 = 0;
        }
        v68 = v25;
        v26 = *(_BYTE **)(v14 + 216);
        if ( v26 == *(_BYTE **)(v14 + 224) )
        {
          std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
            (void **)(v14 + 208),
            v26,
            &v68);
        }
        else
        {
          *(_QWORD *)v26 = v25;
          *(_QWORD *)(v14 + 216) += 8LL;
        }
        *(_BYTE *)(v14 + 180) = 1;
      }
    }
  }
  v27 = operator new(0x1E0u);
  v78 = (__int64)v27;
  if ( v27 )
  {
    v28 = *((_DWORD *)this + 8);
    v29 = v79;
    v30 = anonymous_namespace_::MapPowerStatesToInstanceType(v70, v71);
    v31 = OsStateInstance::OsStateInstance((__int64)v27, v30, v29, v28, 0);
  }
  else
  {
    v31 = 0;
  }
  v78 = v31;
  *(_DWORD *)(v31 + 36) = v77;
  *(_DWORD *)(v31 + 80) = 4;
  *(_QWORD *)(v31 + 24) = v79;
  v32 = operator new(0x50u);
  v68 = (__int64)v32;
  if ( v32 )
    v33 = CustomData::CustomData(v32, L"TargetState", v70, 0);
  else
    v33 = 0;
  v68 = v33;
  v34 = *(_BYTE **)(v31 + 216);
  if ( v34 == *(_BYTE **)(v31 + 224) )
  {
    std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
      (void **)(v31 + 208),
      v34,
      &v68);
  }
  else
  {
    *(_QWORD *)v34 = v33;
    *(_QWORD *)(v31 + 216) += 8LL;
  }
  v35 = operator new(0x50u);
  v68 = (__int64)v35;
  if ( v35 )
    v36 = CustomData::CustomData(v35, L"EffectiveState", v71, 0);
  else
    v36 = 0;
  v68 = v36;
  v37 = *(_BYTE **)(v31 + 216);
  if ( v37 == *(_BYTE **)(v31 + 224) )
  {
    std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
      (void **)(v31 + 208),
      v37,
      &v68);
  }
  else
  {
    *(_QWORD *)v37 = v36;
    *(_QWORD *)(v31 + 216) += 8LL;
  }
  *(_DWORD *)(v31 + 84) = v72;
  *(_DWORD *)(v31 + 88) = v73;
  if ( a2->EventHeader.EventDescriptor.Version >= 2u )
  {
    v38 = operator new(0x50u);
    v68 = (__int64)v38;
    if ( v38 )
    {
      v39 = std::wstring::wstring((__int64)v80, &LidStateStrings[4 * v65]);
      v40 = CustomData::CustomData(v38, L"LidState", v39);
    }
    else
    {
      v40 = 0;
    }
    v68 = v40;
    v41 = *(_BYTE **)(v31 + 216);
    if ( v41 == *(_BYTE **)(v31 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v31 + 208),
        v41,
        &v68);
    }
    else
    {
      *(_QWORD *)v41 = v40;
      *(_QWORD *)(v31 + 216) += 8LL;
    }
    *(_BYTE *)(v31 + 182) = 1;
  }
  if ( a2->EventHeader.EventDescriptor.Version >= 4u )
  {
    v42 = operator new(0x50u);
    v76 = v42;
    if ( v42 )
    {
      v43 = std::wstring::wstring((__int64)v80, &ExternalMonitorStateStrings[4 * v66]);
      v44 = CustomData::CustomData(v42, L"ExternalMonitorState", v43);
    }
    else
    {
      v44 = 0;
    }
    v68 = v44;
    v45 = *(_BYTE **)(v31 + 216);
    if ( v45 == *(_BYTE **)(v31 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v31 + 208),
        v45,
        &v68);
    }
    else
    {
      *(_QWORD *)v45 = v44;
      *(_QWORD *)(v31 + 216) += 8LL;
    }
    *(_BYTE *)(v31 + 181) = 1;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NU4MP>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NU4MP>::GetImpl'::`2'::impl)
    && a2->EventHeader.EventDescriptor.Version >= 5u )
  {
    v46 = operator new(0x50u);
    v76 = v46;
    if ( v46 )
    {
      v47 = std::wstring::wstring((__int64)v80, &ExternalMonitorSourceStrings[4 * v67[0]]);
      v48 = CustomData::CustomData(v46, L"ExternalMonitorSource", v47);
    }
    else
    {
      v48 = 0;
    }
    v68 = v48;
    v49 = *(_BYTE **)(v31 + 216);
    if ( v49 == *(_BYTE **)(v31 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v31 + 208),
        v49,
        &v68);
    }
    else
    {
      *(_QWORD *)v49 = v48;
      *(_QWORD *)(v31 + 216) += 8LL;
    }
    *(_BYTE *)(v31 + 180) = 1;
  }
  if ( v69 != -1 )
  {
    v50 = operator new(0x50u);
    v76 = v50;
    if ( v50 )
      v51 = CustomData::CustomData(v50, L"RequestorCallerType", v69, 0);
    else
      v51 = 0;
    v68 = v51;
    v52 = *(_BYTE **)(v31 + 216);
    if ( v52 == *(_BYTE **)(v31 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v31 + 208),
        v52,
        &v68);
    }
    else
    {
      *(_QWORD *)v52 = v51;
      *(_QWORD *)(v31 + 216) += 8LL;
    }
    v53 = operator new(0x50u);
    v76 = v53;
    if ( v53 )
      v54 = CustomData::CustomData(v53, L"RequestorProcessId", v74, 0);
    else
      v54 = 0;
    v68 = v54;
    v55 = *(_BYTE **)(v31 + 216);
    if ( v55 == *(_BYTE **)(v31 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v31 + 208),
        v55,
        &v68);
    }
    else
    {
      *(_QWORD *)v55 = v54;
      *(_QWORD *)(v31 + 216) += 8LL;
    }
    v56 = operator new(0x50u);
    v76 = v56;
    if ( v56 )
      v57 = CustomData::CustomData(v56, L"RequestorServiceTag", v75, 0);
    else
      v57 = 0;
    v68 = v57;
    v58 = *(_BYTE **)(v31 + 216);
    if ( v58 == *(_BYTE **)(v31 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v31 + 208),
        v58,
        &v68);
    }
    else
    {
      *(_QWORD *)v58 = v57;
      *(_QWORD *)(v31 + 216) += 8LL;
    }
    v59 = operator new(0x50u);
    v76 = v59;
    if ( v59 )
    {
      v60 = std::wstring::wstring((__int64)v80, v81);
      v61 = CustomData::CustomData(v59, L"RequestorDescription", v60);
    }
    else
    {
      v61 = 0;
    }
    v68 = v61;
    v62 = *(_BYTE **)(v31 + 216);
    if ( v62 == *(_BYTE **)(v31 + 224) )
    {
      std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
        (void **)(v31 + 208),
        v62,
        &v68);
    }
    else
    {
      *(_QWORD *)v62 = v61;
      *(_QWORD *)(v31 + 216) += 8LL;
    }
  }
  v63 = *(_QWORD *)this;
  v64 = *(_BYTE **)(*(_QWORD *)this + 8LL);
  if ( v64 == *(_BYTE **)(*(_QWORD *)this + 16LL) )
  {
    std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
      (void **)v63,
      v64,
      &v78);
  }
  else
  {
    *(_QWORD *)v64 = v31;
    *(_QWORD *)(v63 + 8) += 8LL;
  }
LABEL_136:
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v81);
}

```

## disassembly

```asm
0x18005c860  mov     [rsp-8+arg_10], rbx
0x18005c865  mov     [rsp-8+arg_18], rsi
0x18005c86a  push    rbp
0x18005c86b  push    rdi
0x18005c86c  push    r12
0x18005c86e  push    r14
0x18005c870  push    r15
0x18005c872  lea     rbp, [rsp-37h]
0x18005c877  sub     rsp, 0D0h
0x18005c87e  mov     rax, cs:__security_cookie
0x18005c885  xor     rax, rsp
0x18005c888  mov     [rbp+57h+var_30], rax
0x18005c88c  mov     rsi, rdx
0x18005c88f  mov     r15, rcx
0x18005c892  xor     r12d, r12d
0x18005c895  mov     [rbp+57h+var_A8], r12d
0x18005c899  mov     [rbp+57h+var_BE], r12b
0x18005c89d  mov     [rbp+57h+var_A0], r12d
0x18005c8a1  mov     [rbp+57h+var_88], r12d
0x18005c8a5  mov     [rbp+57h+var_A4], r12d
0x18005c8a9  mov     [rbp+57h+var_B0], r12d
0x18005c8ad  lea     rcx, [rbp+57h+var_50]; void *
0x18005c8b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005c8b6  nop
0x18005c8b7  mov     [rbp+57h+var_9C], r12d
0x18005c8bb  mov     [rbp+57h+var_98], r12d
0x18005c8bf  mov     [rbp+57h+var_AC], r12d
0x18005c8c3  mov     [rbp+57h+var_78], r12
0x18005c8c7  mov     [rbp+57h+var_BF], 2
0x18005c8cb  mov     [rbp+57h+var_C0], 3
0x18005c8cf  lea     r8, [rbp+57h+var_78]; unsigned __int64 *
0x18005c8d3  lea     rdx, aTimestamp_2; "Timestamp"
0x18005c8da  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005c8dd  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x18005c8e2  test    eax, eax
0x18005c8e4  jz      short loc_18005C8F0
0x18005c8e6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005c8eb  jmp     loc_18005D107
0x18005c8f0  lea     r8, [rbp+57h+var_AC]; unsigned int *
0x18005c8f4  lea     rdx, aTargetstate; "TargetState"
0x18005c8fb  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005c8fe  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18005c903  test    eax, eax
0x18005c905  jz      short loc_18005C911
0x18005c907  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005c90c  jmp     loc_18005D107
0x18005c911  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x18005c915  lea     rdx, aEffectivestate; "EffectiveState"
0x18005c91c  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005c91f  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18005c924  test    eax, eax
0x18005c926  jz      short loc_18005C932
0x18005c928  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005c92d  jmp     loc_18005D107
0x18005c932  lea     r8, [rbp+57h+var_88]; unsigned int *
0x18005c936  lea     rdx, aReason_1; "Reason"
0x18005c93d  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005c940  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18005c945  test    eax, eax
0x18005c947  jz      short loc_18005C953
0x18005c949  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005c94e  jmp     loc_18005D107
0x18005c953  cmp     byte ptr [rsi+2Ah], 1
0x18005c957  jb      short loc_18005C9D3
0x18005c959  lea     r8, [rbp+57h+var_A4]; unsigned int *
0x18005c95d  lea     rdx, aRemainingbatte; "RemainingBatteryCapacity"
0x18005c964  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005c967  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18005c96c  test    eax, eax
0x18005c96e  jz      short loc_18005C97A
0x18005c970  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005c975  jmp     loc_18005D107
0x18005c97a  lea     r8, [rbp+57h+var_A0]; unsigned int *
0x18005c97e  lea     rdx, aMaxbatterycapa; "MaxBatteryCapacity"
0x18005c985  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005c988  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18005c98d  test    eax, eax
0x18005c98f  jz      short loc_18005C99B
0x18005c991  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005c996  jmp     loc_18005D107
0x18005c99b  cmp     byte ptr [rsi+2Ah], 2
0x18005c99f  jb      short loc_18005C9DB
0x18005c9a1  lea     r8, [rbp+57h+var_C0]; unsigned __int8 *
0x18005c9a5  lea     rdx, aLidstate; "LidState"
0x18005c9ac  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005c9af  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAE@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,uchar &)
0x18005c9b4  test    eax, eax
0x18005c9b6  jz      short loc_18005C9C2
0x18005c9b8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005c9bd  jmp     loc_18005D107
0x18005c9c2  cmp     [rbp+57h+var_C0], 4
0x18005c9c6  jb      short loc_18005C9DB
0x18005c9c8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005c9cd  mov     [rbp+57h+var_C0], 3
0x18005c9d1  jmp     short loc_18005C9DB
0x18005c9d3  mov     [rbp+57h+var_A4], r12d
0x18005c9d7  mov     [rbp+57h+var_A0], r12d
0x18005c9db  or      eax, 0FFFFFFFFh
0x18005c9de  cmp     byte ptr [rsi+2Ah], 3
0x18005c9e2  jb      loc_18005CA6F
0x18005c9e8  lea     r8, [rbp+57h+var_B0]; unsigned int *
0x18005c9ec  lea     rdx, aRequestorcalle; "RequestorCallerType"
0x18005c9f3  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005c9f6  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18005c9fb  test    eax, eax
0x18005c9fd  jz      short loc_18005CA09
0x18005c9ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005ca04  jmp     loc_18005D107
0x18005ca09  lea     r8, [rbp+57h+var_9C]; unsigned int *
0x18005ca0d  lea     rdx, aRequestorproce; "RequestorProcessId"
0x18005ca14  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005ca17  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18005ca1c  test    eax, eax
0x18005ca1e  jz      short loc_18005CA2A
0x18005ca20  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005ca25  jmp     loc_18005D107
0x18005ca2a  lea     r8, [rbp+57h+var_98]; unsigned int *
0x18005ca2e  lea     rdx, aRequestorservi; "RequestorServiceTag"
0x18005ca35  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005ca38  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18005ca3d  test    eax, eax
0x18005ca3f  jz      short loc_18005CA4B
0x18005ca41  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005ca46  jmp     loc_18005D107
0x18005ca4b  xor     r9d, r9d
0x18005ca4e  lea     r8, [rbp+57h+var_50]
0x18005ca52  lea     rdx, aRequestordescr; "RequestorDescription"
0x18005ca59  mov     rcx, rsi; pEvent
0x18005ca5c  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,std::wstring &,uchar)
0x18005ca61  test    eax, eax
0x18005ca63  jz      short loc_18005CA88
0x18005ca65  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005ca6a  jmp     loc_18005D107
0x18005ca6f  mov     [rbp+57h+var_B0], eax
0x18005ca72  mov     [rbp+57h+var_9C], eax
0x18005ca75  mov     [rbp+57h+var_98], eax
0x18005ca78  lea     rdx, qword_18009CA18
0x18005ca7f  lea     rcx, [rbp+57h+var_50]
0x18005ca83  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18005ca88  cmp     byte ptr [rsi+2Ah], 4
0x18005ca8c  jb      short loc_18005CABE
0x18005ca8e  lea     r8, [rbp+57h+var_BF]; unsigned __int8 *
0x18005ca92  lea     rdx, aExternalmonito_1; "ExternalMonitorState"
0x18005ca99  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005ca9c  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAE@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,uchar &)
0x18005caa1  test    eax, eax
0x18005caa3  jz      short loc_18005CAAF
0x18005caa5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005caaa  jmp     loc_18005D107
0x18005caaf  cmp     [rbp+57h+var_BF], 3
0x18005cab3  jb      short loc_18005CABE
0x18005cab5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005caba  mov     [rbp+57h+var_BF], 2
0x18005cabe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NU4MP@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NU4MP@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NU4MP> `wil::Feature<__WilFeatureTraits_Feature_NU4MP>::GetImpl(void)'::`2'::impl
0x18005cac5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NU4MP@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NU4MP>::__private_IsEnabled(void)
0x18005caca  test    al, al
0x18005cacc  jz      short loc_18005CB04
0x18005cace  cmp     byte ptr [rsi+2Ah], 5
0x18005cad2  jb      short loc_18005CB04
0x18005cad4  lea     r8, [rbp+57h+var_BE]; unsigned __int8 *
0x18005cad8  lea     rdx, aExternalmonito; "ExternalMonitorSource"
0x18005cadf  mov     rcx, rsi; struct _EVENT_RECORD *
0x18005cae2  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAE@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,uchar &)
0x18005cae7  test    eax, eax
0x18005cae9  jz      short loc_18005CAF5
0x18005caeb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005caf0  jmp     loc_18005D107
0x18005caf5  cmp     [rbp+57h+var_BE], 4
0x18005caf9  jb      short loc_18005CB04
0x18005cafb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005cb00  mov     [rbp+57h+var_BE], 3
0x18005cb04  mov     rcx, [r15]
0x18005cb07  mov     rbx, [rcx+8]
0x18005cb0b  mov     r14d, 50h ; 'P'
0x18005cb11  cmp     rbx, [rcx]
0x18005cb14  jz      loc_18005CCEE
0x18005cb1a  mov     rbx, [rbx-8]
0x18005cb1e  mov     byte ptr [rbx+14h], 1
0x18005cb22  mov     rax, [rbp+57h+var_78]
0x18005cb26  mov     [rbx+60h], rax
0x18005cb2a  mov     byte ptr [rbx+68h], 1
0x18005cb2e  mov     rcx, rbx; struct OsStateInstance *
0x18005cb31  call    ?IsActive@@YAHPEAVOsStateInstance@@@Z; IsActive(OsStateInstance *)
0x18005cb36  test    eax, eax
0x18005cb38  jz      loc_18005CCEE
0x18005cb3e  cmp     dword ptr [rbx+98h], 1
0x18005cb45  jnz     short loc_18005CB4E
0x18005cb47  mov     [rbx+98h], r12d
0x18005cb4e  cmp     [rbx+0B6h], r12b
0x18005cb55  jnz     short loc_18005CBD2
0x18005cb57  cmp     byte ptr [rsi+2Ah], 2
0x18005cb5b  jb      short loc_18005CBD2
0x18005cb5d  mov     rcx, r14; dwBytes
0x18005cb60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005cb65  mov     rdi, rax
0x18005cb68  mov     [rbp+57h+var_80], rax
0x18005cb6c  test    rax, rax
0x18005cb6f  jz      short loc_18005CBA0
0x18005cb71  movzx   edx, [rbp+57h+var_C0]
0x18005cb75  shl     rdx, 5
0x18005cb79  lea     rax, ?LidStateStrings@@3PAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring near * LidStateStrings
0x18005cb80  add     rdx, rax
0x18005cb83  lea     rcx, [rbp+57h+var_70]
0x18005cb87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005cb8c  mov     r8, rax
0x18005cb8f  lea     rdx, aLidstate; "LidState"
0x18005cb96  mov     rcx, rdi
0x18005cb99  call    ??0CustomData@@QEAA@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CustomData::CustomData(ushort const *,std::wstring)
0x18005cb9e  jmp     short loc_18005CBA3
0x18005cba0  mov     rax, r12
0x18005cba3  mov     [rbp+57h+var_B8], rax
0x18005cba7  lea     rcx, [rbx+0D0h]
0x18005cbae  mov     rdx, [rcx+8]
0x18005cbb2  cmp     rdx, [rcx+10h]
0x18005cbb6  jz      short loc_18005CBC2
0x18005cbb8  mov     [rdx], rax
0x18005cbbb  add     qword ptr [rcx+8], 8
0x18005cbc0  jmp     short loc_18005CBCB
0x18005cbc2  lea     r8, [rbp+57h+var_B8]
0x18005cbc6  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18005cbcb  mov     byte ptr [rbx+0B6h], 1
0x18005cbd2  cmp     [rbx+0B5h], r12b
0x18005cbd9  jnz     short loc_18005CC56
0x18005cbdb  cmp     byte ptr [rsi+2Ah], 4
0x18005cbdf  jb      short loc_18005CC56
0x18005cbe1  mov     rcx, r14; dwBytes
0x18005cbe4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005cbe9  mov     rdi, rax
0x18005cbec  mov     [rbp+57h+var_80], rax
0x18005cbf0  test    rax, rax
0x18005cbf3  jz      short loc_18005CC24
0x18005cbf5  movzx   edx, [rbp+57h+var_BF]
0x18005cbf9  shl     rdx, 5
0x18005cbfd  lea     rax, ?ExternalMonitorStateStrings@@3PAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring near * ExternalMonitorStateStrings
0x18005cc04  add     rdx, rax
0x18005cc07  lea     rcx, [rbp+57h+var_70]
0x18005cc0b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005cc10  mov     r8, rax
0x18005cc13  lea     rdx, aExternalmonito_1; "ExternalMonitorState"
0x18005cc1a  mov     rcx, rdi
0x18005cc1d  call    ??0CustomData@@QEAA@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CustomData::CustomData(ushort const *,std::wstring)
0x18005cc22  jmp     short loc_18005CC27
0x18005cc24  mov     rax, r12
0x18005cc27  mov     [rbp+57h+var_B8], rax
0x18005cc2b  lea     rcx, [rbx+0D0h]
0x18005cc32  mov     rdx, [rcx+8]
0x18005cc36  cmp     rdx, [rcx+10h]
0x18005cc3a  jz      short loc_18005CC46
0x18005cc3c  mov     [rdx], rax
0x18005cc3f  add     qword ptr [rcx+8], 8
0x18005cc44  jmp     short loc_18005CC4F
0x18005cc46  lea     r8, [rbp+57h+var_B8]
0x18005cc4a  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18005cc4f  mov     byte ptr [rbx+0B5h], 1
0x18005cc56  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NU4MP@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NU4MP@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NU4MP> `wil::Feature<__WilFeatureTraits_Feature_NU4MP>::GetImpl(void)'::`2'::impl
0x18005cc5d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NU4MP@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NU4MP>::__private_IsEnabled(void)
0x18005cc62  test    al, al
0x18005cc64  jz      loc_18005CCEE
0x18005cc6a  cmp     [rbx+0B4h], r12b
0x18005cc71  jnz     short loc_18005CCEE
0x18005cc73  cmp     byte ptr [rsi+2Ah], 5
0x18005cc77  jb      short loc_18005CCEE
0x18005cc79  mov     rcx, r14; dwBytes
0x18005cc7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005cc81  mov     rdi, rax
0x18005cc84  mov     [rbp+57h+var_80], rax
0x18005cc88  test    rax, rax
0x18005cc8b  jz      short loc_18005CCBC
0x18005cc8d  movzx   edx, [rbp+57h+var_BE]
0x18005cc91  shl     rdx, 5
0x18005cc95  lea     rax, ?ExternalMonitorSourceStrings@@3PAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring near * ExternalMonitorSourceStrings
0x18005cc9c  add     rdx, rax
0x18005cc9f  lea     rcx, [rbp+57h+var_70]
0x18005cca3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005cca8  mov     r8, rax
0x18005ccab  lea     rdx, aExternalmonito; "ExternalMonitorSource"
0x18005ccb2  mov     rcx, rdi
0x18005ccb5  call    ??0CustomData@@QEAA@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CustomData::CustomData(ushort const *,std::wstring)
0x18005ccba  jmp     short loc_18005CCBF
0x18005ccbc  mov     rax, r12
0x18005ccbf  mov     [rbp+57h+var_B8], rax
0x18005ccc3  lea     rcx, [rbx+0D0h]
0x18005ccca  mov     rdx, [rcx+8]
0x18005ccce  cmp     rdx, [rcx+10h]
0x18005ccd2  jz      short loc_18005CCDE
0x18005ccd4  mov     [rdx], rax
0x18005ccd7  add     qword ptr [rcx+8], 8
0x18005ccdc  jmp     short loc_18005CCE7
0x18005ccde  lea     r8, [rbp+57h+var_B8]
0x18005cce2  call    ??$_Emplace_reallocate@AEBQEAUScenarioInstanceScaffold@@@?$vector@PEAUScenarioInstanceScaffold@@V?$allocator@PEAUScenarioInstanceScaffold@@@std@@@std@@AEAAPEAPEAUScenarioInstanceScaffold@@QEAPEAU2@AEBQEAU2@@Z; std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(ScenarioInstanceScaffold * * const,ScenarioInstanceScaffold * const &)
0x18005cce7  mov     byte ptr [rbx+0B4h], 1
0x18005ccee  mov     ecx, 1E0h; dwBytes
0x18005ccf3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005ccf8  mov     r14, rax
0x18005ccfb  mov     [rbp+57h+var_80], rax
0x18005ccff  test    rax, rax
0x18005cd02  jz      short loc_18005CD31
0x18005cd04  mov     ebx, [r15+20h]
0x18005cd08  mov     rdi, [rbp+57h+var_78]
0x18005cd0c  mov     edx, [rbp+57h+var_A8]
  ... truncated ...
```
