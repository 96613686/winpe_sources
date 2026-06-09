# SleepStudyTroubleshooter::ProcessSpmScenarioStopEvent(_EVENT_RECORD *)

- ea: `0x1800830e8`
- end: `0x180083d23`
- name: `?ProcessSpmScenarioStopEvent@SleepStudyTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `3131`
- prototype: `void(SleepStudyTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180081b00`

## callees

- `0x180008740`
- `0x180008da0`
- `0x18001cf30`
- `0x18001f6f4`
- `0x180027e10`
- `0x180027f10`
- `0x18003362c`
- `0x1800359ac`
- `0x180036324`
- `0x180037108`
- `0x18005719c`
- `0x180057a3c`
- `0x180057b80`
- `0x18008197c`
- `0x1800830e8`
- `0x180096010`

## string_xrefs

- `0x1800831f3`: `DripsResidencyInUs`
- `0x18008327d`: `HwDripsResidencyInUs`
- `0x1800837ae`: `LidOpenState`
- `0x1800836e5`: `RemoteDesktopEnabled`
- `0x180083816`: `SleepSwDripsResidencyInUs`
- `0x1800837ce`: `NonDripsIdleCpuInUs`
- `0x1800837fb`: `SleepHwDripsResidencyInUs`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SleepStudyTroubleshooter::ProcessSpmScenarioStopEvent(
        SleepStudyTroubleshooter *this,
        struct _EVENT_RECORD *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  signed int v7; // eax
  char *v8; // rbx
  char *v9; // r14
  char *v10; // r12
  char *v11; // r15
  char *v12; // rbx
  char *v13; // r14
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  UCHAR *p_Version; // rbx
  UCHAR *v18; // r14
  UCHAR *v19; // rbx
  __int64 v20; // r14
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rdx
  __int64 v26; // r8
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rax
  char v29; // al
  unsigned __int64 v30; // rbx
  void *v31; // r15
  __int64 v32; // rbx
  _QWORD *v33; // rax
  __int64 v34; // rax
  _BYTE *v35; // rdx
  void *v36; // r12
  __int64 v37; // rbx
  _QWORD *v38; // rax
  __int64 v39; // rax
  _BYTE *v40; // rdx
  __int64 UnregisteredFxDevices; // r12
  __int64 v42; // r15
  __int64 v43; // rbx
  __int64 v44; // r8
  unsigned int v45; // r12d
  unsigned __int64 v46; // rbx
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 *v52; // r8
  _BYTE *v53; // rdx
  unsigned int v54; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v55; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int v56; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v57; // [rsp+2Ch] [rbp-D4h] BYREF
  unsigned int v58; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v59; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v60; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v61; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v62; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v63; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v64; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v65; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v66; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v67; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v68; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v69; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v70; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v71; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v72; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v73; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v74; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v75; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v76; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v77; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v78; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v79; // [rsp+88h] [rbp-78h] BYREF
  __int64 v80; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v81; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v82; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v83; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v84; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v85; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v86; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v87; // [rsp+D0h] [rbp-30h] BYREF
  union _LARGE_INTEGER v88; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v89; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v90; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v91; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v92; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v93; // [rsp+100h] [rbp+0h] BYREF
  __int128 v94; // [rsp+110h] [rbp+10h]
  _OWORD v95[5]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int8 v96; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v97; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v98; // [rsp+198h] [rbp+98h] BYREF

  v78 = 0;
  v55 = 0;
  v79 = 0;
  v98 = 0;
  v83 = 0;
  v74 = 0;
  v75 = 0;
  v81 = 0;
  v90 = 0;
  v76 = 0;
  v89 = 0;
  v87 = 0;
  v85 = 0;
  v86 = 0;
  v84 = 0;
  v54 = 0;
  v57 = 0;
  v56 = 0;
  v65 = 0;
  v97 = 17;
  v67 = 0;
  v66 = 0;
  v91 = 0;
  v92 = 0;
  v60 = 0;
  v61 = 0;
  v64 = 0;
  v63 = 0;
  v62 = 0;
  v88.QuadPart = 0;
  v77 = 0;
  v68 = 0;
  v69 = 0;
  v72 = 0;
  v70 = 0;
  v71 = 0;
  v58 = 0;
  v59 = 0;
  v73 = 0;
  v82 = 0;
  v96 = 3;
  if ( !*((_QWORD *)this + 4) )
  {
    *(_DWORD *)(*((_QWORD *)this + 3) + 396LL) |= 1u;
    goto LABEL_143;
  }
  if ( !GetEventProperty(a2, L"DripsResidencyInUs", &v79)
    && !GetEventProperty(a2, L"EnergyDrain", &v74)
    && !GetEventProperty(a2, L"EnergyDrainV2", &v88)
    && !GetEventProperty(a2, L"EnergyDrainV2Flags", &v77)
    && !GetEventProperty(a2, L"OnAc", &v76)
    && !GetEventProperty(a2, L"HwDripsResidencyInUs", &v81)
    && !GetEventProperty(a2, L"PreVetoCount", &v89)
    && !GetEventProperty(a2, L"DurationInUs", &v83)
    && !GetEventProperty(a2, L"FullChargeCapacity", &v75)
    && !GetEventProperty(a2, L"NonActivatedCpuInUs", &v90)
    && !GetEventProperty(a2, L"DesignCapacity", &v78)
    && (!GetEventProperty(a2, L"AudioDurationInUs", &v84) || (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0)
    && (!GetEventProperty(a2, L"Reason", &v97) || (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0) )
  {
    v7 = v97;
    if ( (v97 & 0x80000000) != 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4, v6);
      v7 = v97;
    }
    if ( v7 >= 20 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4, v6);
    if ( (!GetEventProperty(a2, L"DisconnectedStandby", &v56) || (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0)
      && (!GetEventProperty(a2, L"NonAttributedCpuInUs", &v91) || (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0)
      && (!GetEventProperty(a2, L"EnergySaverPolicy", &v60) || (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0)
      && (!GetEventProperty(a2, L"LockConsoleTimeoutInSec", &v61)
       || (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0)
      && (!GetEventProperty(a2, L"StandbyTimeoutInSec", &v63) || (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0) )
    {
      v8 = (char *)this + 24;
      if ( !GetEventProperty(a2, L"VideoTimeoutInSec", &v62) || (*(_BYTE *)(*(_QWORD *)v8 + 392LL) & 0x20) != 0 )
      {
        if ( GetEventProperty(a2, L"ModernSleepEnabledActionsBitmask", &v66) )
        {
          if ( (*(_BYTE *)(*(_QWORD *)v8 + 392LL) & 0x20) == 0 )
            goto LABEL_143;
          v9 = (char *)this + 24;
        }
        else
        {
          v9 = (char *)this + 24;
        }
        if ( GetEventProperty(a2, L"ModernSleepAppliedActionsBitmask", &v67) )
        {
          if ( (*(_BYTE *)(*(_QWORD *)v8 + 392LL) & 0x20) == 0 )
            goto LABEL_143;
          v10 = (char *)this + 24;
        }
        else
        {
          v10 = v9;
        }
        v55 = 0;
        if ( GetEventProperty(a2, L"DirectedDripsTransitionCount", &v55) )
        {
          if ( (*(_BYTE *)(*(_QWORD *)v8 + 392LL) & 0x20) == 0 )
            goto LABEL_143;
          v11 = (char *)this + 24;
        }
        else
        {
          v11 = v10;
        }
        if ( GetEventProperty(a2, L"IsHibernateEnabled", &v69) )
        {
          if ( (*(_BYTE *)(*(_QWORD *)v9 + 392LL) & 0x20) == 0 )
            goto LABEL_143;
          v12 = (char *)this + 24;
        }
        else
        {
          v12 = v11;
        }
        if ( GetEventProperty(a2, L"HibernateTimeoutInSec", &v70) )
        {
          if ( (*(_BYTE *)(*(_QWORD *)v10 + 392LL) & 0x20) == 0 )
            goto LABEL_143;
          v13 = (char *)this + 24;
        }
        else
        {
          v13 = v12;
        }
        if ( (!GetEventProperty(a2, L"HibernateBudgetPercentage", &v71)
           || (*(_BYTE *)(*(_QWORD *)v11 + 392LL) & 0x20) != 0)
          && (!GetEventProperty(a2, L"IsLockConsoleTimeoutActive", &v72)
           || (*(_BYTE *)(*(_QWORD *)v12 + 392LL) & 0x20) != 0)
          && (!GetEventProperty(a2, L"IsDebuggerEnabled", &v68) || (*(_BYTE *)(*(_QWORD *)v13 + 392LL) & 0x20) != 0) )
        {
          p_Version = &a2->EventHeader.EventDescriptor.Version;
          if ( !a2->EventHeader.EventDescriptor.Version
            || !GetEventProperty(a2, L"ScenarioInstanceId", &v87)
            && ((*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0
             || (v15 = **((_QWORD **)this + 4), *(_QWORD *)(v15 + 184) == v87)) )
          {
            if ( *p_Version >= 2u )
            {
              if ( GetEventProperty(a2, L"RemainingSleepTimeoutInSeconds", &v64)
                || GetEventProperty(a2, L"IdleTimeoutSource", &v65) )
              {
                goto LABEL_143;
              }
              p_Version = &a2->EventHeader.EventDescriptor.Version;
            }
            v98 = 0;
            if ( *p_Version < 3u )
            {
              v18 = p_Version;
            }
            else
            {
              if ( GetEventProperty(a2, L"DripsTransitions", &v98) )
                goto LABEL_143;
              v18 = &a2->EventHeader.EventDescriptor.Version;
            }
            if ( *p_Version < 4u )
            {
              v18 = p_Version;
            }
            else if ( GetEventProperty(a2, L"UserConnectivitySetting", &v59)
                   || GetEventProperty(a2, L"RemoteDesktopEnabled", &v58)
                   || GetEventProperty(a2, L"BIRequestActive", &v57) )
            {
              goto LABEL_143;
            }
            if ( *v18 < 5u )
            {
              v19 = v18;
            }
            else
            {
              if ( GetEventProperty(a2, L"TimerRebaseThresholdInSec", &v73)
                || GetEventProperty(a2, L"CumulativeTimerRebaseInUs", &v82) )
              {
                goto LABEL_143;
              }
              v19 = &a2->EventHeader.EventDescriptor.Version;
            }
            if ( *v18 >= 6u && GetEventProperty(a2, L"RestrictedStandby", &v54) )
            {
              if ( GetEventProperty(a2, L"AusterityMode", &v54) )
                goto LABEL_143;
            }
            else
            {
              v19 = v18;
            }
            if ( (*v19 < 7u || !GetEventProperty(a2, L"LidOpenState", &v96))
              && (*v19 < 8u
               || !GetEventProperty(a2, L"NonDripsIdleCpuInUs", &v92)
               || (*(_BYTE *)(*((_QWORD *)this + 3) + 392LL) & 0x20) != 0)
              && (*v19 < 9u
               || !GetEventProperty(a2, L"SleepHwDripsResidencyInUs", &v81)
               && !GetEventProperty(a2, L"SleepSwDripsResidencyInUs", &v79)) )
            {
              v20 = **((_QWORD **)this + 4);
              v21 = 5 * v83;
              if ( (*(_BYTE *)(v20 + 1708) & 2) != 0 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14, v16);
              *(_QWORD *)(v20 + 1392) = 2 * v21 + 50000000;
              *(_DWORD *)(v20 + 1708) |= 2u;
              *(_BYTE *)(v20 + 120) = v56 != 0;
              *(_BYTE *)(v20 + 121) = v57 != 0;
              *(_BYTE *)(v20 + 122) = v58 != 0;
              *(_DWORD *)(v20 + 124) = v59;
              *(_DWORD *)(v20 + 88) = v97;
              *(_BYTE *)(v20 + 129) = v60 != 0;
              *(_DWORD *)(v20 + 132) = v61;
              *(_DWORD *)(v20 + 140) = v62;
              *(_DWORD *)(v20 + 136) = v63;
              *(_DWORD *)(v20 + 148) = v64;
              *(_DWORD *)(v20 + 152) = v65;
              *(_DWORD *)(v20 + 160) = v66;
              *(_DWORD *)(v20 + 164) = v67;
              *(_BYTE *)(v20 + 244) = v68;
              *(_BYTE *)(v20 + 245) = v69;
              *(_DWORD *)(v20 + 248) = v70;
              *(_DWORD *)(v20 + 252) = v71;
              *(_BYTE *)(v20 + 144) = v72;
              *(_DWORD *)(v20 + 256) = v98;
              *(_DWORD *)(v20 + 260) = v73;
              *(_QWORD *)(v20 + 264) = v82;
              *(_DWORD *)(v20 + 276) = v54;
              *(_DWORD *)(v20 + 284) = v96;
              v22 = v79;
              v23 = v82;
              if ( v79 < v82 )
              {
                MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14, v79);
                v23 = v82;
                v22 = v79;
              }
              if ( v22 )
                v24 = ((v22 >> 1) + 100 * v23) / v22;
              else
                LOBYTE(v24) = 0;
              *(_BYTE *)(v20 + 272) = v24;
              ScenarioInstanceData::SetBatteryData((ScenarioInstanceData *)v20, v76, v75, v74);
              *(_BYTE *)(v20 + 229) = 0;
              if ( v97 == 2 )
                *(_BYTE *)(v20 + 229) = 1;
              *(union _LARGE_INTEGER *)(v20 + 200) = v88;
              *(_DWORD *)(v20 + 208) = v77;
              *(_QWORD *)(v20 + 56) = 10 * v79;
              *(_QWORD *)(v20 + 40) = a2->EventHeader.TimeStamp.QuadPart;
              *(_QWORD *)(v20 + 64) = v81;
              if ( v81 != -1 )
                *(_QWORD *)(v20 + 64) = 10 * v81;
              *(_QWORD *)(v20 + 112) = v84;
              v27 = v83;
              if ( v83 )
              {
                v28 = 100 * v84 / v83;
                v25 = 100 * v84 % v83;
              }
              else
              {
                LOBYTE(v28) = 0;
              }
              *(_BYTE *)(v20 + 108) = v28;
              if ( (unsigned __int8)v28 > 0x64u )
                MicrosoftTelemetryAssertTriggeredNoArgs(v27, v25, v26);
              v29 = *(_BYTE *)(v20 + 108);
              if ( (unsigned __int8)v29 > 0x64u )
                v29 = 100;
              *(_BYTE *)(v20 + 108) = v29;
              *(_QWORD *)(v20 + 96) = v89;
              *(_DWORD *)(v20 + 28) = v78;
              v30 = 10 * v90;
              if ( (*(_BYTE *)(v20 + 1204) & 2) != 0 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v27, v25, v26);
              *(_QWORD *)(v20 + 752) = v30;
              v31 = operator new(0x250u);
              v80 = (__int64)v31;
              if ( v31 )
              {
                v32 = 10 * v91;
                v33 = (_QWORD *)std::wstring::wstring((__int64)&v93, (__int64)L"CPU C0 Time.Non-attributed Time");
                v34 = ProcessorData::ProcessorData((__int64)v31, v33, v32);
              }
              else
              {
                v34 = 0;
              }
              v80 = v34;
              v35 = *(_BYTE **)(v20 + 320);
              if ( v35 == *(_BYTE **)(v20 + 328) )
              {
                std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
                  (void **)(v20 + 312),
                  v35,
                  &v80);
              }
              else
              {
                *(_QWORD *)v35 = v34;
                *(_QWORD *)(v20 + 320) += 8LL;
              }
              v36 = operator new(0x250u);
              *(_QWORD *)&v95[0] = v36;
              if ( v36 )
              {
                v37 = 10 * v92;
                v38 = (_QWORD *)std::wstring::wstring((__int64)&v93, (__int64)L"Non-DRIPS Idle Time");
                v39 = ProcessorData::ProcessorData((__int64)v36, v38, v37);
              }
              else
              {
                v39 = 0;
              }
              v80 = v39;
              v40 = *(_BYTE **)(v20 + 320);
              if ( v40 == *(_BYTE **)(v20 + 328) )
              {
                std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
                  (void **)(v20 + 312),
                  v40,
                  &v80);
              }
              else
              {
                *(_QWORD *)v40 = v39;
                *(_QWORD *)(v20 + 320) += 8LL;
              }
              if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 392LL) & 0x60) == 0x40 )
                ScenarioInstanceData::AddSrumData((ScenarioInstanceData *)v20);
              *(_DWORD *)(v20 + 240) = v55;
              *(_BYTE *)(*((_QWORD *)this + 4) + 248LL) = (*(_DWORD *)(*((_QWORD *)this + 3) + 392LL) & 0x10) != 0;
              *(_BYTE *)(*((_QWORD *)this + 4) + 249LL) = (*(_DWORD *)(*((_QWORD *)this + 3) + 392LL) & 8) != 0;
              UnregisteredFxDevices = DevicePowerRequirements::FindUnregisteredFxDevices(
                                        *((_QWORD *)this + 4) + 168LL,
                                        v95);
              if ( &v85 == (__int128 *)UnregisteredFxDevices )
              {
                v43 = *((_QWORD *)&v85 + 1);
                v42 = v85;
              }
              else
              {
                std::vector<std::wstring>::_Tidy(&v85);
                v42 = *(_QWORD *)UnregisteredFxDevices;
                *(_QWORD *)&v85 = *(_QWORD *)UnregisteredFxDevices;
                v43 = *(_QWORD *)(UnregisteredFxDevices + 8);
                *((_QWORD *)&v85 + 1) = v43;
                v86 = *(_QWORD *)(UnregisteredFxDevices + 16);
                *(_QWORD *)UnregisteredFxDevices = 0;
                *(_QWORD *)(UnregisteredFxDevices + 8) = 0;
                *(_QWORD *)(UnregisteredFxDevices + 16) = 0;
              }
              std::vector<std::wstring>::_Tidy(v95);
              v45 = 0;
              v46 = (v43 - v42) >> 5;
              if ( v46 )
              {
                do
                {
                  v47 = 32LL * v45;
                  v93 = 0;
                  v94 = 0u;
                  v93 = *(_OWORD *)(v47 + v42);
                  v94 = *(_OWORD *)(v47 + v42 + 16);
                  *(_QWORD *)(v47 + v42 + 16) = 0;
                  *(_QWORD *)(v47 + v42 + 24) = 7;
                  *(_WORD *)(v47 + v42) = 0;
                  SleepStudyTroubleshooter::AddUnregisteredDevice(this, &v93, v45++);
                }
                while ( v45 < v46 );
              }
              v48 = (unsigned int)((__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 5)) >> 3) + 1;
              v49 = (__int64 *)*((_QWORD *)this + 4);
              v50 = *v49;
              *(_DWORD *)(*v49 + 24) = v48;
              if ( !*(_QWORD *)(v20 + 1344) )
                MicrosoftTelemetryAssertTriggeredNoArgs(v50, v48, v44);
              v51 = *(_QWORD *)(v20 + 1344);
              if ( v51 )
              {
                v95[0] = a2->EventHeader.ProviderId;
                (*(void (__fastcall **)(__int64, _OWORD *, _QWORD))(*(_QWORD *)v51 + 8LL))(
                  v51,
                  v95,
                  a2->EventHeader.EventDescriptor.Id);
              }
              v52 = (__int64 *)((char *)this + 32);
              v53 = (_BYTE *)*((_QWORD *)this + 6);
              if ( v53 == *((_BYTE **)this + 7) )
              {
                std::vector<ScenarioInstanceScaffold *>::_Emplace_reallocate<ScenarioInstanceScaffold * const &>(
                  (void **)this + 5,
                  v53,
                  v52);
              }
              else
              {
                *(_QWORD *)v53 = *v52;
                *((_QWORD *)this + 6) += 8LL;
              }
              *((_QWORD *)this + 4) = 0;
            }
          }
        }
      }
    }
  }
LABEL_143:
  std::vector<std::wstring>::_Tidy(&v85);
}

```

## disassembly

```asm
0x1800830e8  mov     [rsp-8+arg_8], rbx
0x1800830ed  push    rbp
0x1800830ee  push    rsi
0x1800830ef  push    rdi
0x1800830f0  push    r12
0x1800830f2  push    r13
0x1800830f4  push    r14
0x1800830f6  push    r15
0x1800830f8  lea     rbp, [rsp-40h]
0x1800830fd  sub     rsp, 140h
0x180083104  mov     rdi, rdx
0x180083107  mov     rsi, rcx
0x18008310a  xor     r13d, r13d
0x18008310d  mov     [rbp+70h+var_F0], r13d
0x180083111  mov     [rsp+170h+var_14C], r13d
0x180083116  mov     [rbp+70h+var_E8], r13
0x18008311a  mov     [rbp+70h+arg_18], r13d
0x180083121  mov     [rbp+70h+var_C8], r13
0x180083125  mov     [rsp+170h+var_100], r13d
0x18008312a  mov     [rsp+170h+var_FC], r13d
0x18008312f  mov     [rbp+70h+var_D8], r13
0x180083133  mov     [rbp+70h+var_88], r13
0x180083137  mov     [rsp+170h+var_F8], r13d
0x18008313c  mov     [rbp+70h+var_90], r13
0x180083140  mov     [rbp+70h+var_A0], r13
0x180083144  xorps   xmm0, xmm0
0x180083147  movdqu  [rbp+70h+var_B8], xmm0
0x18008314c  mov     [rbp+70h+var_A8], r13
0x180083150  mov     [rbp+70h+var_C0], r13
0x180083154  mov     [rsp+170h+var_150], r13d
0x180083159  mov     [rsp+170h+var_144], r13d
0x18008315e  mov     [rsp+170h+var_148], r13d
0x180083163  mov     [rsp+170h+var_124], r13d
0x180083168  mov     [rbp+70h+arg_10], 11h
0x180083172  mov     [rsp+170h+var_11C], r13d
0x180083177  mov     [rsp+170h+var_120], r13d
0x18008317c  mov     [rbp+70h+var_80], r13
0x180083180  mov     [rbp+70h+var_78], r13
0x180083184  mov     [rsp+170h+var_138], r13d
0x180083189  mov     [rsp+170h+var_134], r13d
0x18008318e  mov     [rsp+170h+var_128], r13d
0x180083193  mov     [rsp+170h+var_12C], r13d
0x180083198  mov     [rsp+170h+var_130], r13d
0x18008319d  mov     qword ptr [rbp+70h+var_98], r13
0x1800831a1  mov     [rsp+170h+var_F4], r13d
0x1800831a6  mov     [rsp+170h+var_118], r13d
0x1800831ab  mov     [rsp+170h+var_114], r13d
0x1800831b0  mov     [rsp+170h+var_108], r13d
0x1800831b5  mov     [rsp+170h+var_110], r13d
0x1800831ba  mov     [rsp+170h+var_10C], r13d
0x1800831bf  mov     [rsp+170h+var_140], r13d
0x1800831c4  mov     [rsp+170h+var_13C], r13d
0x1800831c9  mov     [rsp+170h+var_104], r13d
0x1800831ce  mov     [rbp+70h+var_D0], r13
0x1800831d2  mov     [rbp+70h+arg_0], 3
0x1800831d9  cmp     [rcx+20h], r13
0x1800831dd  jnz     short loc_1800831EF
0x1800831df  mov     rax, [rcx+18h]
0x1800831e3  or      dword ptr [rax+18Ch], 1
0x1800831ea  jmp     loc_180083CFF
0x1800831ef  lea     r8, [rbp+70h+var_E8]; unsigned __int64 *
0x1800831f3  lea     rdx, aDripsresidency; "DripsResidencyInUs"
0x1800831fa  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800831fd  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x180083202  test    eax, eax
0x180083204  jnz     loc_180083CFF
0x18008320a  lea     r8, [rsp+170h+var_100]; unsigned int *
0x18008320f  lea     rdx, aEnergydrain_0; "EnergyDrain"
0x180083216  mov     rcx, rdi; struct _EVENT_RECORD *
0x180083219  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18008321e  test    eax, eax
0x180083220  jnz     loc_180083CFF
0x180083226  lea     r8, [rbp+70h+var_98]; union _LARGE_INTEGER *
0x18008322a  lea     rdx, aEnergydrainv2; "EnergyDrainV2"
0x180083231  mov     rcx, rdi; struct _EVENT_RECORD *
0x180083234  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAT_LARGE_INTEGER@@@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,_LARGE_INTEGER &)
0x180083239  test    eax, eax
0x18008323b  jnz     loc_180083CFF
0x180083241  lea     r8, [rsp+170h+var_F4]; unsigned int *
0x180083246  lea     rdx, aEnergydrainv2f; "EnergyDrainV2Flags"
0x18008324d  mov     rcx, rdi; struct _EVENT_RECORD *
0x180083250  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x180083255  test    eax, eax
0x180083257  jnz     loc_180083CFF
0x18008325d  lea     r8, [rsp+170h+var_F8]; unsigned int *
0x180083262  lea     rdx, aOnac; "OnAc"
0x180083269  mov     rcx, rdi; struct _EVENT_RECORD *
0x18008326c  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x180083271  test    eax, eax
0x180083273  jnz     loc_180083CFF
0x180083279  lea     r8, [rbp+70h+var_D8]; unsigned __int64 *
0x18008327d  lea     rdx, aHwdripsresiden; "HwDripsResidencyInUs"
0x180083284  mov     rcx, rdi; struct _EVENT_RECORD *
0x180083287  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x18008328c  test    eax, eax
0x18008328e  jnz     loc_180083CFF
0x180083294  lea     r8, [rbp+70h+var_90]; unsigned __int64 *
0x180083298  lea     rdx, aPrevetocount_0; "PreVetoCount"
0x18008329f  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800832a2  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x1800832a7  test    eax, eax
0x1800832a9  jnz     loc_180083CFF
0x1800832af  lea     r8, [rbp+70h+var_C8]; unsigned __int64 *
0x1800832b3  lea     rdx, aDurationinus; "DurationInUs"
0x1800832ba  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800832bd  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x1800832c2  test    eax, eax
0x1800832c4  jnz     loc_180083CFF
0x1800832ca  lea     r8, [rsp+170h+var_FC]; unsigned int *
0x1800832cf  lea     rdx, aFullchargecapa; "FullChargeCapacity"
0x1800832d6  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800832d9  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x1800832de  test    eax, eax
0x1800832e0  jnz     loc_180083CFF
0x1800832e6  lea     r8, [rbp+70h+var_88]; unsigned __int64 *
0x1800832ea  lea     rdx, aNonactivatedcp; "NonActivatedCpuInUs"
0x1800832f1  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800832f4  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x1800832f9  test    eax, eax
0x1800832fb  jnz     loc_180083CFF
0x180083301  lea     r8, [rbp+70h+var_F0]; unsigned int *
0x180083305  lea     rdx, aDesigncapacity_3; "DesignCapacity"
0x18008330c  mov     rcx, rdi; struct _EVENT_RECORD *
0x18008330f  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x180083314  test    eax, eax
0x180083316  jnz     loc_180083CFF
0x18008331c  lea     r8, [rbp+70h+var_C0]; unsigned __int64 *
0x180083320  lea     rdx, aAudiodurationi; "AudioDurationInUs"
0x180083327  mov     rcx, rdi; struct _EVENT_RECORD *
0x18008332a  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x18008332f  mov     r15b, 20h ; ' '
0x180083332  test    eax, eax
0x180083334  jz      short loc_180083347
0x180083336  mov     rax, [rsi+18h]
0x18008333a  test    [rax+188h], r15b
0x180083341  jz      loc_180083CFF
0x180083347  lea     r8, [rbp+70h+arg_10]; unsigned int *
0x18008334e  lea     rdx, aReason_1; "Reason"
0x180083355  mov     rcx, rdi; struct _EVENT_RECORD *
0x180083358  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18008335d  test    eax, eax
0x18008335f  jz      short loc_180083372
0x180083361  mov     rax, [rsi+18h]
0x180083365  test    [rax+188h], r15b
0x18008336c  jz      loc_180083CFF
0x180083372  mov     eax, [rbp+70h+arg_10]
0x180083378  test    eax, eax
0x18008337a  jns     short loc_180083387
0x18008337c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180083381  mov     eax, [rbp+70h+arg_10]
0x180083387  cmp     eax, 14h
0x18008338a  jl      short loc_180083391
0x18008338c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180083391  lea     r8, [rsp+170h+var_148]; unsigned int *
0x180083396  lea     rdx, aDisconnectedst_1; "DisconnectedStandby"
0x18008339d  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800833a0  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x1800833a5  test    eax, eax
0x1800833a7  jz      short loc_1800833BA
0x1800833a9  mov     rax, [rsi+18h]
0x1800833ad  test    [rax+188h], r15b
0x1800833b4  jz      loc_180083CFF
0x1800833ba  lea     r8, [rbp+70h+var_80]; unsigned __int64 *
0x1800833be  lea     rdx, aNonattributedc; "NonAttributedCpuInUs"
0x1800833c5  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800833c8  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEA_K@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,unsigned __int64 &)
0x1800833cd  test    eax, eax
0x1800833cf  jz      short loc_1800833E2
0x1800833d1  mov     rax, [rsi+18h]
0x1800833d5  test    [rax+188h], r15b
0x1800833dc  jz      loc_180083CFF
0x1800833e2  lea     r8, [rsp+170h+var_138]; unsigned int *
0x1800833e7  lea     rdx, aEnergysaverpol_0; "EnergySaverPolicy"
0x1800833ee  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800833f1  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x1800833f6  test    eax, eax
0x1800833f8  jz      short loc_18008340B
0x1800833fa  mov     rax, [rsi+18h]
0x1800833fe  test    [rax+188h], r15b
0x180083405  jz      loc_180083CFF
0x18008340b  lea     r8, [rsp+170h+var_134]; unsigned int *
0x180083410  lea     rdx, aLockconsoletim_0; "LockConsoleTimeoutInSec"
0x180083417  mov     rcx, rdi; struct _EVENT_RECORD *
0x18008341a  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18008341f  test    eax, eax
0x180083421  jz      short loc_180083434
0x180083423  mov     rax, [rsi+18h]
0x180083427  test    [rax+188h], r15b
0x18008342e  jz      loc_180083CFF
0x180083434  lea     r8, [rsp+170h+var_12C]; unsigned int *
0x180083439  lea     rdx, aStandbytimeout; "StandbyTimeoutInSec"
0x180083440  mov     rcx, rdi; struct _EVENT_RECORD *
0x180083443  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x180083448  test    eax, eax
0x18008344a  jz      short loc_18008345D
0x18008344c  mov     rax, [rsi+18h]
0x180083450  test    [rax+188h], r15b
0x180083457  jz      loc_180083CFF
0x18008345d  lea     r8, [rsp+170h+var_130]; unsigned int *
0x180083462  lea     rdx, aVideotimeoutin_0; "VideoTimeoutInSec"
0x180083469  mov     rcx, rdi; struct _EVENT_RECORD *
0x18008346c  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x180083471  lea     rbx, [rsi+18h]
0x180083475  test    eax, eax
0x180083477  jz      short loc_180083489
0x180083479  mov     rax, [rbx]
0x18008347c  test    [rax+188h], r15b
0x180083483  jz      loc_180083CFF
0x180083489  lea     r8, [rsp+170h+var_120]; unsigned int *
0x18008348e  lea     rdx, aModernsleepena; "ModernSleepEnabledActionsBitmask"
0x180083495  mov     rcx, rdi; struct _EVENT_RECORD *
0x180083498  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18008349d  test    eax, eax
0x18008349f  jz      short loc_1800834B7
0x1800834a1  mov     rax, [rbx]
0x1800834a4  test    [rax+188h], r15b
0x1800834ab  jz      loc_180083CFF
0x1800834b1  lea     r14, [rsi+18h]
0x1800834b5  jmp     short loc_1800834BA
0x1800834b7  mov     r14, rbx
0x1800834ba  lea     r8, [rsp+170h+var_11C]; unsigned int *
0x1800834bf  lea     rdx, aModernsleepapp; "ModernSleepAppliedActionsBitmask"
0x1800834c6  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800834c9  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x1800834ce  test    eax, eax
0x1800834d0  jz      short loc_1800834E8
0x1800834d2  mov     rax, [rbx]
0x1800834d5  test    [rax+188h], r15b
0x1800834dc  jz      loc_180083CFF
0x1800834e2  lea     r12, [rsi+18h]
0x1800834e6  jmp     short loc_1800834EB
0x1800834e8  mov     r12, r14
0x1800834eb  mov     [rsp+170h+var_14C], r13d
0x1800834f0  lea     r8, [rsp+170h+var_14C]; unsigned int *
0x1800834f5  lea     rdx, aDirecteddripst_0; "DirectedDripsTransitionCount"
0x1800834fc  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800834ff  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x180083504  test    eax, eax
0x180083506  jz      short loc_18008351E
0x180083508  mov     rax, [rbx]
0x18008350b  test    [rax+188h], r15b
0x180083512  jz      loc_180083CFF
0x180083518  lea     r15, [rsi+18h]
0x18008351c  jmp     short loc_180083521
0x18008351e  mov     r15, r12
0x180083521  lea     r8, [rsp+170h+var_114]; unsigned int *
0x180083526  lea     rdx, aIshibernateena; "IsHibernateEnabled"
0x18008352d  mov     rcx, rdi; struct _EVENT_RECORD *
0x180083530  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x180083535  test    eax, eax
0x180083537  jz      short loc_18008354F
0x180083539  mov     rax, [r14]
0x18008353c  test    byte ptr [rax+188h], 20h
0x180083543  jz      loc_180083CFF
0x180083549  lea     rbx, [rsi+18h]
0x18008354d  jmp     short loc_180083552
0x18008354f  mov     rbx, r15
0x180083552  lea     r8, [rsp+170h+var_110]; unsigned int *
0x180083557  lea     rdx, aHibernatetimeo_0; "HibernateTimeoutInSec"
0x18008355e  mov     rcx, rdi; struct _EVENT_RECORD *
0x180083561  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x180083566  test    eax, eax
0x180083568  jz      short loc_180083584
0x18008356a  mov     rax, [r12]
0x18008356e  mov     r12b, 20h ; ' '
0x180083571  test    [rax+188h], r12b
0x180083578  jz      loc_180083CFF
0x18008357e  lea     r14, [rsi+18h]
0x180083582  jmp     short loc_18008358A
0x180083584  mov     r14, rbx
0x180083587  mov     r12b, 20h ; ' '
0x18008358a  lea     r8, [rsp+170h+var_10C]; unsigned int *
0x18008358f  lea     rdx, aHibernatebudge; "HibernateBudgetPercentage"
0x180083596  mov     rcx, rdi; struct _EVENT_RECORD *
0x180083599  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x18008359e  test    eax, eax
0x1800835a0  jz      short loc_1800835B2
0x1800835a2  mov     rax, [r15]
0x1800835a5  test    [rax+188h], r12b
0x1800835ac  jz      loc_180083CFF
0x1800835b2  lea     r8, [rsp+170h+var_108]; unsigned int *
0x1800835b7  lea     rdx, aIslockconsolet; "IsLockConsoleTimeoutActive"
0x1800835be  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800835c1  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x1800835c6  test    eax, eax
0x1800835c8  jz      short loc_1800835DA
0x1800835ca  mov     rax, [rbx]
0x1800835cd  test    [rax+188h], r12b
0x1800835d4  jz      loc_180083CFF
0x1800835da  lea     r8, [rsp+170h+var_118]; unsigned int *
0x1800835df  lea     rdx, aIsdebuggerenab_0; "IsDebuggerEnabled"
0x1800835e6  mov     rcx, rdi; struct _EVENT_RECORD *
0x1800835e9  call    ?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAK@Z; GetEventProperty(_EVENT_RECORD *,ushort const *,ulong &)
0x1800835ee  test    eax, eax
0x1800835f0  jz      short loc_180083602
0x1800835f2  mov     rax, [r14]
0x1800835f5  test    [rax+188h], r12b
0x1800835fc  jz      loc_180083CFF
0x180083602  lea     rbx, [rdi+2Ah]
0x180083606  cmp     byte ptr [rbx], 1
  ... truncated ...
```
