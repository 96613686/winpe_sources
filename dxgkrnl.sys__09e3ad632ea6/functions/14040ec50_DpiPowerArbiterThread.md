# DpiPowerArbiterThread

- ea: `0x14040ec50`
- end: `0x14040f632`
- name: `DpiPowerArbiterThread`
- size: `2530`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `24`
- tags: `service_task`

## callees

- `0x14001f950`
- `0x1400221f4`
- `0x140022af4`
- `0x140035f90`
- `0x140040f60`
- `0x140041db4`
- `0x140057b04`
- `0x14007fd3c`
- `0x14007fe80`
- `0x1400a0cb0`
- `0x1401c2ff0`
- `0x1401df2cc`
- `0x1401ee23c`
- `0x1403675cc`
- `0x140367a7c`
- `0x140367c14`
- `0x1403a94dc`
- `0x1403b02e0`
- `0x1403bc654`
- `0x1403ef4dc`
- `0x1403ef660`
- `0x1403f00c8`
- `0x1403f8400`
- `0x14040ec50`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14040f3c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14040f3c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14040f3f1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14040f3f1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14040f3d6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14040f3d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14040f3e5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14040f3e5`
- `ntoskrnl!PoFxUnregisterDevice` at `0x14040f102`
- `ntoskrnl!PoFxUnregisterDevice` at `0x14040f102`
- `ntoskrnl!KeClearEvent` at `0x14040f06d`
- `ntoskrnl!KeClearEvent` at `0x14040f06d`
- `ntoskrnl!PsTerminateSystemThread` at `0x14040f37c`
- `ntoskrnl!PsTerminateSystemThread` at `0x14040f37c`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14040ecb6`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14040ecb6`
- `ntoskrnl!KeSetEvent` at `0x14040f089`
- `ntoskrnl!KeSetEvent` at `0x14040f0ef`
- `ntoskrnl!KeSetEvent` at `0x14040f18b`
- `ntoskrnl!KeSetEvent` at `0x14040f21a`
- `ntoskrnl!KeSetEvent` at `0x14040f296`
- `ntoskrnl!KeSetEvent` at `0x14040f33c`
- `ntoskrnl!KeSetEvent` at `0x14040f089`
- `ntoskrnl!KeSetEvent` at `0x14040f0ef`
- `ntoskrnl!KeSetEvent` at `0x14040f18b`
- `ntoskrnl!KeSetEvent` at `0x14040f21a`
- `ntoskrnl!KeSetEvent` at `0x14040f296`
- `ntoskrnl!KeSetEvent` at `0x14040f33c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14040ed32`
- `ntoskrnl!KeWaitForSingleObject` at `0x14040ed32`
- `ntoskrnl!KeSetBasePriorityThread` at `0x14040ecfe`
- `ntoskrnl!KeSetBasePriorityThread` at `0x14040ecfe`
- `watchdog!WdLogSingleEntry4` at `0x14040ee48`
- `watchdog!WdLogSingleEntry4` at `0x14040ee48`
- `watchdog!WdLogSingleEntry2` at `0x14040f00d`
- `watchdog!WdLogSingleEntry2` at `0x14040f00d`
- `watchdog!WdLogSingleEntry3` at `0x14040ee9b`
- `watchdog!WdLogSingleEntry3` at `0x14040ef0f`
- `watchdog!WdLogSingleEntry3` at `0x14040f1f4`
- `watchdog!WdLogSingleEntry3` at `0x14040f30f`
- `watchdog!WdLogSingleEntry3` at `0x14040f438`
- `watchdog!WdLogSingleEntry3` at `0x14040f472`
- `watchdog!WdLogSingleEntry3` at `0x14040f51b`
- `watchdog!WdLogSingleEntry3` at `0x14040f5a3`
- `watchdog!WdLogSingleEntry3` at `0x14040ee9b`
- `watchdog!WdLogSingleEntry3` at `0x14040ef0f`
- `watchdog!WdLogSingleEntry3` at `0x14040f1f4`
- `watchdog!WdLogSingleEntry3` at `0x14040f30f`
- `watchdog!WdLogSingleEntry3` at `0x14040f438`
- `watchdog!WdLogSingleEntry3` at `0x14040f472`
- `watchdog!WdLogSingleEntry3` at `0x14040f51b`
- `watchdog!WdLogSingleEntry3` at `0x14040f5a3`
- `watchdog!WdLogSingleEntry1` at `0x14040ecce`
- `watchdog!WdLogSingleEntry1` at `0x14040ed4e`
- `watchdog!WdLogSingleEntry1` at `0x14040eeca`
- `watchdog!WdLogSingleEntry1` at `0x14040ef88`
- `watchdog!WdLogSingleEntry1` at `0x14040efc1`
- `watchdog!WdLogSingleEntry1` at `0x14040f2ce`
- `watchdog!WdLogSingleEntry1` at `0x14040ecce`
- `watchdog!WdLogSingleEntry1` at `0x14040ed4e`
- `watchdog!WdLogSingleEntry1` at `0x14040eeca`
- `watchdog!WdLogSingleEntry1` at `0x14040ef88`
- `watchdog!WdLogSingleEntry1` at `0x14040efc1`
- `watchdog!WdLogSingleEntry1` at `0x14040f2ce`

## pseudocode

```c
void __fastcall DpiPowerArbiterThread(_QWORD *StartContext)
{
  __int64 v1; // rdi
  NTSTATUS v2; // esi
  NTSTATUS v3; // eax
  void *v4; // rax
  NTSTATUS v5; // eax
  char v6; // r12
  char v7; // r13
  int Blink; // edx
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v9; // r14
  bool v10; // bp
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // ebx
  __int64 v22; // rcx
  struct _LIST_ENTRY *v23; // r15
  DXGADAPTER *v24; // rcx
  __int64 v25; // rdx
  DXGADAPTER *v26; // rcx
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v27; // r8
  int v28; // ebx
  char IsPowerRuntimeDStateTransition; // r14
  int v30; // ebx
  int v31; // eax
  struct _LIST_ENTRY *PowerActionQueueEntry; // rax
  int v33; // eax
  DXGADAPTER **v34; // rbx
  __int64 v35; // rcx
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdx
  unsigned __int8 started; // al
  DXGADAPTER *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  _BYTE v43[8]; // [rsp+30h] [rbp-88h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v44; // [rsp+38h] [rbp-80h]
  __int128 ProcessInformation; // [rsp+40h] [rbp-78h] BYREF
  __int128 v46; // [rsp+50h] [rbp-68h]
  __int128 v47; // [rsp+60h] [rbp-58h]

  v1 = StartContext[8];
  *(_QWORD *)(v1 + 4096) = KeGetCurrentThread();
  if ( (unsigned int)Feature_BoostPriorityOfPowerArbiterThread__private_IsEnabledDeviceUsageNoInline() )
  {
    ProcessInformation = 0;
    v46 = 0;
    v47 = 0;
    v3 = ZwQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessBasicInformation, &ProcessInformation, 0x30u, 0);
    v2 = v3;
    if ( v3 >= 0 )
    {
      if ( SDWORD2(v46) < 15 )
        KeSetBasePriorityThread(KeGetCurrentThread(), 15 - DWORD2(v46));
    }
    else
    {
      WdLogSingleEntry1(2, v3);
      WdLogGlobalForLineNumber = 2053;
    }
  }
  else
  {
    v2 = 0;
  }
  if ( *(_DWORD *)(v1 + 4120) != 7 )
  {
    v4 = (void *)(v1 + 4072);
    while ( 1 )
    {
      v5 = KeWaitForSingleObject(v4, Executive, 0, 0, 0);
      v2 = v5;
      if ( !v5 )
        break;
      WdLogSingleEntry1(2, v5);
      WdLogGlobalForLineNumber = 2087;
LABEL_88:
      v4 = (void *)(v1 + 4072);
      if ( *(_DWORD *)(v1 + 4120) == 7 )
        goto LABEL_89;
    }
    while ( 1 )
    {
      PowerActionQueueEntry = DpiGetPowerActionQueueEntry((struct _FDO_CONTEXT *)v1);
      v23 = PowerActionQueueEntry;
      if ( !PowerActionQueueEntry )
        goto LABEL_88;
      v2 = 0;
      v43[0] = 0;
      v6 = 0;
      v7 = 0;
      CDisplayScenarioContextScope::ContextScopeConstructor(
        (CDisplayScenarioContextScope *)v43,
        (const struct _GUID *)((char *)&PowerActionQueueEntry[4].Blink + 4),
        0x45u,
        0);
      Blink = (int)v23[2].Blink;
      v9 = v44;
      v10 = Blink != 64;
      if ( LODWORD(v23[1].Blink) != 1 )
        break;
      if ( ((*(_DWORD *)(v1 + 4120) - 1) & 0xFFFFFFFD) != 0 )
      {
        DxgkShutdownBootGraphics(0, 0);
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite((PERESOURCE)(v1 + 3928), 1u);
        ExReleaseResourceLite((PERESOURCE)(v1 + 3928));
        KeLeaveCriticalRegion();
        v33 = (int)v23[2].Blink;
        v34 = (DXGADAPTER **)(v1 + 4032);
        v35 = *(_QWORD *)(v1 + 4032);
        if ( (v33 & 0x40) != 0 )
        {
          DxgkAcquireAdapterCoreSync(v35, 4);
          if ( !(unsigned __int8)DxgkIsAdapterCoreSyncAcquired(*v34, 2) )
          {
            WdLogSingleEntry3(9, v1, 0, 0);
            WdLogGlobalForLineNumber = 2161;
            DpiSetDevicePowerTransitionStateAtPassiveLevel(v1, 0);
            v2 = -1073741823;
            goto LABEL_84;
          }
          WdLogSingleEntry3(9, v1, 0, 0);
          WdLogGlobalForLineNumber = 2170;
        }
        else
        {
          v36 = 6;
          if ( (v33 & 0x98) == 0 )
            v36 = 3;
          DxgkAcquireAdapterCoreSync(v35, v36);
        }
        if ( *(_DWORD *)(v1 + 284) == 1 )
        {
          MonitorAdapterPowerChange(*v34, 1u, v9);
          DmmAdapterPowerChange(*v34, 1u);
        }
        DmmResetModeState(*v34, 0xFFFFFFFF);
        v37 = (int)v23[2].Blink;
        if ( (v37 & 0x20) != 0 )
        {
          v38 = 4;
          goto LABEL_120;
        }
        if ( (v37 & 0x10) != 0 )
        {
          v38 = 3;
          goto LABEL_120;
        }
        if ( (v37 & 8) != 0 )
        {
          v38 = 2;
          goto LABEL_120;
        }
        if ( (v37 & 0x80u) != 0 )
        {
          v38 = 5;
          goto LABEL_120;
        }
        if ( (v37 & 0x40) == 0 )
        {
          v38 = 1;
LABEL_120:
          DXGADAPTER::ApplyCoreSyncAction(*v34, v38);
LABEL_121:
          *(_DWORD *)(v1 + 4120) = 1;
          goto LABEL_84;
        }
        WdLogSingleEntry3(9, v1, 1, 0);
        WdLogGlobalForLineNumber = 2235;
        if ( *(_BYTE *)(v1 + 5816) )
          DxgkNotifySharedPowerGraphicsPowerTransition(*v34, PowerDeviceD3, 1u);
        started = DpiStartSuspendingAdapter((struct _FDO_CONTEXT *)v1);
        v40 = *v34;
        if ( started )
        {
          DXGADAPTER::ApplyCoreSyncAction(v40, 3);
          DpiFinishSuspendAdapter((struct _FDO_CONTEXT *)v1);
          if ( *(_DWORD *)(v1 + 4120) == 1 )
          {
            if ( *(_BYTE *)(v1 + 5816) )
              DxgkNotifySharedPowerGraphicsPowerTransition(*v34, PowerDeviceD3, 0);
            goto LABEL_121;
          }
          WdLogSingleEntry3(9, v1, 0, 0);
          WdLogGlobalForLineNumber = 2275;
          v41 = 5;
          v40 = *v34;
        }
        else
        {
          v41 = 2;
        }
        DxgkReleaseAdapterCoreSync(v40, v41);
        DpiSetDevicePowerTransitionStateAtPassiveLevel(v1, 0);
        if ( *(_BYTE *)(v1 + 5816) )
          DxgkNotifySharedPowerGraphicsPowerTransition(*v34, PowerDeviceD0, 0);
      }
      else if ( (unsigned __int8)DpiIsPowerRuntimeDStateTransition(v1) )
      {
        DpiSetDevicePowerTransitionStateAtPassiveLevel(v42, 5);
      }
LABEL_84:
      if ( v10 )
      {
        LODWORD(v23[4].Blink) = v2;
        KeSetEvent((PRKEVENT)&v23[3], 0, 0);
      }
      CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v43);
    }
    if ( LODWORD(v23[1].Blink) == 2 )
    {
      if ( *(_DWORD *)(v1 + 4120) == 1 )
      {
        v26 = *(DXGADAPTER **)(v1 + 4032);
        v27 = v44;
        *(_DWORD *)(v1 + 4120) = 2;
        v28 = (int)v23[2].Blink;
        MonitorAdapterPowerChange(v26, 0, v27);
        IsPowerRuntimeDStateTransition = DpiIsPowerRuntimeDStateTransition(v1);
        if ( IsPowerRuntimeDStateTransition )
        {
          if ( v28 != 64 )
          {
            WdLogSingleEntry3(9, v1, 0, 0);
            WdLogGlobalForLineNumber = 2379;
            LODWORD(v23[4].Blink) = 0;
            v10 = 0;
            KeSetEvent((PRKEVENT)&v23[3], 0, 0);
            v23 = 0;
            if ( *(_BYTE *)(v1 + 5816) )
              DxgkNotifySharedPowerGraphicsPowerTransition(*(void **)(v1 + 4032), PowerDeviceD0, 0);
          }
        }
        v2 = DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), 5);
        if ( IsPowerRuntimeDStateTransition )
        {
          if ( v28 == 64 )
          {
            DpiSetDevicePowerTransitionStateAtPassiveLevel(v1, 0);
            if ( *(_BYTE *)(v1 + 5816) )
              DxgkNotifySharedPowerGraphicsPowerTransition(*(void **)(v1 + 4032), PowerDeviceD0, 0);
          }
          KeSetEvent((PRKEVENT)(v1 + 4240), 0, 0);
          DpiScheduleDelayedDevicePowerRequiredAtPassiveLevel(v1);
        }
      }
      goto LABEL_77;
    }
    if ( LODWORD(v23[1].Blink) == 3 || LODWORD(v23[1].Blink) == 4 )
    {
      v21 = *(_DWORD *)(v1 + 4120);
      if ( v21 == 3 || (v22 = *(_QWORD *)(v1 + 4032)) == 0 )
      {
        *(_DWORD *)(v1 + 4120) = 3;
      }
      else
      {
        if ( LODWORD(v23[1].Blink) == 4 )
        {
          KeClearEvent((PRKEVENT)(v1 + 4264));
          LODWORD(v23[4].Blink) = 0;
          v10 = 0;
          KeSetEvent((PRKEVENT)&v23[3], 0, 0);
          v22 = *(_QWORD *)(v1 + 4032);
          v23 = 0;
        }
        if ( v21 != 1 )
          v2 = DxgkAcquireAdapterCoreSync(v22, 3);
        v24 = *(DXGADAPTER **)(v1 + 4032);
        if ( v24 )
          DXGADAPTER::PrepareToRemove(v24);
        if ( v21 != 1 )
          v2 = DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), 3);
        if ( *(_QWORD *)(v1 + 488) )
        {
          KeSetEvent((PRKEVENT)(v1 + 4240), 0, 0);
          PoFxUnregisterDevice(*(_QWORD *)(v1 + 488));
          *(_QWORD *)(*(_QWORD *)(v1 + 4032) + 3360LL) = 0;
          *(_QWORD *)(v1 + 488) = 0;
        }
        if ( v21 == 1 )
        {
          v25 = 5;
          if ( (*(_BYTE *)(v1 + 4040) & 0x18) == 0 && *(_BYTE *)(v1 + 1160) )
            v25 = 2;
          v2 = DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), v25);
        }
        DpiRemoveAdapter(v9, 1);
        *(_DWORD *)(v1 + 4120) = 3;
        KeSetEvent((PRKEVENT)(v1 + 4264), 0, 0);
      }
      goto LABEL_77;
    }
    if ( LODWORD(v23[1].Blink) != 5 )
    {
      if ( LODWORD(v23[1].Blink) == 6 )
      {
        v11 = *(_DWORD *)(v1 + 4124);
        if ( (v11 & 4) != 0 )
        {
          v12 = *(_QWORD *)(v1 + 3000);
          *(_DWORD *)(v1 + 4124) = v11 & 0xFFFFFFFB;
          if ( (*(int (__fastcall **)(__int64))(v1 + 3032))(v12) < 0 )
          {
            WdLogSingleEntry4(0, 275);
            WdLogGlobalForLineNumber = 2723;
          }
        }
        v13 = *(_DWORD *)(v1 + 4124);
        v14 = *(_QWORD *)(v1 + 4032);
        if ( (v13 & 1) != 0 )
        {
          *(_DWORD *)(v1 + 4124) = v13 & 0xFFFFFFFE;
          v15 = DxgkReleaseAdapterCoreSync(v14, 5);
          v2 = v15;
          if ( v15 < 0 )
          {
            WdLogSingleEntry3(0, 275, 21, v15);
            WdLogGlobalForLineNumber = 2744;
          }
        }
        else
        {
          v16 = DxgkResumeMemorySegments(v14);
          v2 = v16;
          v17 = v16;
          if ( v16 < 0 )
          {
            WdLogSingleEntry1(2, v16);
            WdLogGlobalForLineNumber = 2763;
          }
          if ( (*(_DWORD *)(v1 + 4124) & 2) == 0 && (int)DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), 2) < 0 )
          {
            WdLogSingleEntry3(0, 275, 21, v17);
            WdLogGlobalForLineNumber = 2787;
          }
          *(_DWORD *)(v1 + 4124) &= ~2u;
        }
        *(_DWORD *)(v1 + 4120) = 6;
      }
      else
      {
        if ( LODWORD(v23[1].Blink) != 7 )
          goto LABEL_84;
        if ( *(_DWORD *)(v1 + 4120) == 1 )
          v2 = DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), 5);
        *(_DWORD *)(v1 + 4120) = 7;
      }
      goto LABEL_77;
    }
    if ( (Blink & 1) != 0 )
    {
      DxgkAcquireAdapterCoreSync(*(_QWORD *)(v1 + 4032), 3);
      DXGADAPTER::ApplyCoreSyncAction(*(_QWORD *)(v1 + 4032), 1);
    }
    else
    {
      if ( (Blink & 2) != 0 )
        goto LABEL_37;
      v19 = DxgkAcquireAdapterCoreSync(*(_QWORD *)(v1 + 4032), 2);
      v2 = v19;
      if ( v19 < 0 )
      {
        WdLogSingleEntry1(2, v19);
        WdLogGlobalForLineNumber = 2633;
        goto LABEL_84;
      }
    }
    v6 = 1;
LABEL_37:
    if ( ((__int64)v23[2].Blink & 1) == 0 )
    {
      v18 = DxgkSuspendMemorySegments(*(_QWORD *)(v1 + 4032));
      v2 = v18;
      if ( v18 < 0 )
      {
        WdLogSingleEntry1(3, v18);
        WdLogGlobalForLineNumber = 2660;
LABEL_81:
        if ( v6 == 1 )
        {
          v31 = DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), 5);
          if ( v31 < 0 )
          {
            WdLogSingleEntry3(0, 275, 21, v31);
            WdLogGlobalForLineNumber = 2863;
          }
        }
        goto LABEL_84;
      }
      v7 = 1;
    }
    if ( ((__int64)v23[2].Blink & 4) != 0 )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD))(v1 + 3024))(*(_QWORD *)(v1 + 3000));
      v2 = v20;
      if ( v20 < 0 )
      {
        WdLogSingleEntry2(2, *(_QWORD *)(v1 + 3024), v20);
        WdLogGlobalForLineNumber = 2683;
LABEL_78:
        if ( v7 == 1 )
        {
          v30 = DxgkResumeMemorySegments(*(_QWORD *)(v1 + 4032));
          if ( v30 < 0 )
          {
            WdLogSingleEntry1(2, v2);
            WdLogGlobalForLineNumber = 2843;
            v2 = v30;
          }
        }
        goto LABEL_81;
      }
    }
    *(_DWORD *)(v1 + 4120) = 5;
    *(_DWORD *)(v1 + 4124) |= LODWORD(v23[2].Blink);
LABEL_77:
    if ( v2 >= 0 )
      goto LABEL_84;
    goto LABEL_78;
  }
LABEL_89:
  PsTerminateSystemThread(v2);
}

```

## disassembly

```asm
0x14040ec50  push    rbx
0x14040ec52  push    rbp
0x14040ec53  push    rsi
0x14040ec54  push    rdi
0x14040ec55  push    r12
0x14040ec57  push    r13
0x14040ec59  push    r14
0x14040ec5b  push    r15
0x14040ec5d  sub     rsp, 78h
0x14040ec61  mov     rdi, [rcx+40h]
0x14040ec65  mov     rax, gs:188h
0x14040ec6e  mov     [rdi+1000h], rax
0x14040ec75  call    Feature_BoostPriorityOfPowerArbiterThread__private_IsEnabledDeviceUsageNoInline
0x14040ec7a  mov     ebx, 2
0x14040ec7f  test    eax, eax
0x14040ec81  jnz     short loc_14040EC8A
0x14040ec83  xor     esi, esi
0x14040ec85  jmp     loc_14040ED0A
0x14040ec8a  xorps   xmm0, xmm0
0x14040ec8d  mov     [rsp+0B8h+ReturnLength], 0; ReturnLength
0x14040ec96  mov     r9d, 30h ; '0'; ProcessInformationLength
0x14040ec9c  lea     r8, [rsp+0B8h+ProcessInformation]; ProcessInformation
0x14040eca1  xor     edx, edx; ProcessInformationClass
0x14040eca3  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14040eca7  movups  [rsp+0B8h+ProcessInformation], xmm0
0x14040ecac  movups  [rsp+0B8h+var_68], xmm0
0x14040ecb1  movups  [rsp+0B8h+var_58], xmm0
0x14040ecb6  call    cs:__imp_ZwQueryInformationProcess
0x14040ecbd  nop     dword ptr [rax+rax+00h]
0x14040ecc2  movsxd  rsi, eax
0x14040ecc5  test    eax, eax
0x14040ecc7  jns     short loc_14040ECE6
0x14040ecc9  mov     rdx, rsi
0x14040eccc  mov     ecx, ebx
0x14040ecce  call    cs:__imp_WdLogSingleEntry1
0x14040ecd5  nop     dword ptr [rax+rax+00h]
0x14040ecda  mov     cs:WdLogGlobalForLineNumber, 805h
0x14040ece4  jmp     short loc_14040ED0A
0x14040ece6  mov     edx, 0Fh
0x14040eceb  cmp     dword ptr [rsp+0B8h+var_68+8], edx
0x14040ecef  jge     short loc_14040ED0A
0x14040ecf1  sub     edx, dword ptr [rsp+0B8h+var_68+8]; Increment
0x14040ecf5  mov     rcx, gs:188h; Thread
0x14040ecfe  call    cs:__imp_KeSetBasePriorityThread
0x14040ed05  nop     dword ptr [rax+rax+00h]
0x14040ed0a  cmp     dword ptr [rdi+1018h], 7
0x14040ed11  jz      loc_14040F37A
0x14040ed17  lea     rax, [rdi+0FE8h]
0x14040ed1e  xor     r9d, r9d; Alertable
0x14040ed21  mov     [rsp+0B8h+ReturnLength], 0; Timeout
0x14040ed2a  xor     r8d, r8d; WaitMode
0x14040ed2d  xor     edx, edx; WaitReason
0x14040ed2f  mov     rcx, rax; Object
0x14040ed32  call    cs:__imp_KeWaitForSingleObject
0x14040ed39  nop     dword ptr [rax+rax+00h]
0x14040ed3e  movsxd  rsi, eax
0x14040ed41  test    eax, eax
0x14040ed43  jz      loc_14040F352
0x14040ed49  mov     rdx, rsi
0x14040ed4c  mov     ecx, ebx
0x14040ed4e  call    cs:__imp_WdLogSingleEntry1
0x14040ed55  nop     dword ptr [rax+rax+00h]
0x14040ed5a  mov     cs:WdLogGlobalForLineNumber, 827h
0x14040ed64  jmp     loc_14040F366
0x14040ed69  xor     esi, esi
0x14040ed6b  lea     rdx, [r15+4Ch]; struct _GUID *
0x14040ed6f  xor     r9d, r9d; unsigned int
0x14040ed72  mov     [rsp+0B8h+var_88], sil
0x14040ed77  lea     rcx, [rsp+0B8h+var_88]; this
0x14040ed7c  xor     r12b, r12b
0x14040ed7f  xor     r13b, r13b
0x14040ed82  lea     r8d, [rsi+45h]; unsigned int
0x14040ed86  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x14040ed8b  mov     edx, [r15+28h]
0x14040ed8f  cmp     edx, 40h ; '@'
0x14040ed92  mov     r8d, [r15+18h]
0x14040ed96  mov     ecx, r8d
0x14040ed99  mov     r14, [rsp+0B8h+var_80]
0x14040ed9e  setnz   bpl
0x14040eda2  sub     ecx, 1
0x14040eda5  jz      loc_14040F39A
0x14040edab  sub     ecx, 1
0x14040edae  jz      loc_14040F1AB
0x14040edb4  sub     ecx, 1
0x14040edb7  jz      loc_14040F041
0x14040edbd  sub     ecx, 1
0x14040edc0  jz      loc_14040F041
0x14040edc6  sub     ecx, 1
0x14040edc9  jz      loc_14040EF3B
0x14040edcf  sub     ecx, 1
0x14040edd2  jz      short loc_14040EE05
0x14040edd4  cmp     ecx, 1
0x14040edd7  jnz     loc_14040F32A
0x14040eddd  cmp     [rdi+1018h], ecx
0x14040ede3  jnz     short loc_14040EDF6
0x14040ede5  mov     rcx, [rdi+0FC0h]
0x14040edec  lea     edx, [rsi+5]
0x14040edef  call    DxgkReleaseAdapterCoreSync
0x14040edf4  mov     esi, eax
0x14040edf6  mov     dword ptr [rdi+1018h], 7
0x14040ee00  jmp     loc_14040F2AA
0x14040ee05  mov     eax, [rdi+101Ch]
0x14040ee0b  test    al, 4
0x14040ee0d  jz      short loc_14040EE5E
0x14040ee0f  mov     rcx, [rdi+0BB8h]
0x14040ee16  and     eax, 0FFFFFFFBh
0x14040ee19  mov     [rdi+101Ch], eax
0x14040ee1f  mov     rax, [rdi+0BD8h]
0x14040ee26  call    _guard_dispatch_icall
0x14040ee2b  test    eax, eax
0x14040ee2d  jns     short loc_14040EE5E
0x14040ee2f  mov     r9, [rdi+0BD8h]
0x14040ee36  xor     ecx, ecx
0x14040ee38  cdqe
0x14040ee3a  mov     edx, 113h
0x14040ee3f  mov     [rsp+0B8h+ReturnLength], rax
0x14040ee44  lea     r8d, [rcx+15h]
0x14040ee48  call    cs:__imp_WdLogSingleEntry4
0x14040ee4f  nop     dword ptr [rax+rax+00h]
0x14040ee54  mov     cs:WdLogGlobalForLineNumber, 0AA3h
0x14040ee5e  mov     eax, [rdi+101Ch]
0x14040ee64  mov     rcx, [rdi+0FC0h]
0x14040ee6b  test    al, 1
0x14040ee6d  jz      short loc_14040EEB3
0x14040ee6f  and     eax, 0FFFFFFFEh
0x14040ee72  mov     edx, 5
0x14040ee77  mov     [rdi+101Ch], eax
0x14040ee7d  call    DxgkReleaseAdapterCoreSync
0x14040ee82  movsxd  rsi, eax
0x14040ee85  test    eax, eax
0x14040ee87  jns     loc_14040EF2C
0x14040ee8d  xor     ecx, ecx
0x14040ee8f  mov     r9, rsi
0x14040ee92  mov     edx, 113h
0x14040ee97  lea     r8d, [rcx+15h]
0x14040ee9b  call    cs:__imp_WdLogSingleEntry3
0x14040eea2  nop     dword ptr [rax+rax+00h]
0x14040eea7  mov     cs:WdLogGlobalForLineNumber, 0AB8h
0x14040eeb1  jmp     short loc_14040EF2C
0x14040eeb3  call    DxgkResumeMemorySegments
0x14040eeb8  movsxd  rsi, eax
0x14040eebb  mov     rbx, rsi
0x14040eebe  test    eax, eax
0x14040eec0  jns     short loc_14040EEE0
0x14040eec2  mov     rdx, rbx
0x14040eec5  mov     ecx, 2
0x14040eeca  call    cs:__imp_WdLogSingleEntry1
0x14040eed1  nop     dword ptr [rax+rax+00h]
0x14040eed6  mov     cs:WdLogGlobalForLineNumber, 0ACBh
0x14040eee0  mov     eax, [rdi+101Ch]
0x14040eee6  mov     ecx, 2
0x14040eeeb  test    cl, al
0x14040eeed  jnz     short loc_14040EF25
0x14040eeef  mov     edx, ecx
0x14040eef1  mov     rcx, [rdi+0FC0h]
0x14040eef8  call    DxgkReleaseAdapterCoreSync
0x14040eefd  test    eax, eax
0x14040eeff  jns     short loc_14040EF25
0x14040ef01  xor     ecx, ecx
0x14040ef03  mov     r9, rbx
0x14040ef06  mov     edx, 113h
0x14040ef0b  lea     r8d, [rcx+15h]
0x14040ef0f  call    cs:__imp_WdLogSingleEntry3
0x14040ef16  nop     dword ptr [rax+rax+00h]
0x14040ef1b  mov     cs:WdLogGlobalForLineNumber, 0AE3h
0x14040ef25  and     dword ptr [rdi+101Ch], 0FFFFFFFDh
0x14040ef2c  mov     dword ptr [rdi+1018h], 6
0x14040ef36  jmp     loc_14040F2AA
0x14040ef3b  test    dl, 1
0x14040ef3e  jz      short loc_14040EFA3
0x14040ef40  mov     rcx, [rdi+0FC0h]
0x14040ef47  mov     edx, 3
0x14040ef4c  call    DxgkAcquireAdapterCoreSync
0x14040ef51  mov     rcx, [rdi+0FC0h]
0x14040ef58  mov     edx, 1
0x14040ef5d  call    ?ApplyCoreSyncAction@DXGADAPTER@@QEAAXW4DXGADAPTERCORESYNC_ACTION@@@Z; DXGADAPTER::ApplyCoreSyncAction(DXGADAPTERCORESYNC_ACTION)
0x14040ef62  mov     r12b, 1
0x14040ef65  mov     eax, [r15+28h]
0x14040ef69  test    al, 1
0x14040ef6b  jnz     short loc_14040EFDF
0x14040ef6d  mov     rcx, [rdi+0FC0h]
0x14040ef74  call    DxgkSuspendMemorySegments
0x14040ef79  movsxd  rsi, eax
0x14040ef7c  test    eax, eax
0x14040ef7e  jns     short loc_14040EFDC
0x14040ef80  mov     rdx, rsi
0x14040ef83  mov     ecx, 3
0x14040ef88  call    cs:__imp_WdLogSingleEntry1
0x14040ef8f  nop     dword ptr [rax+rax+00h]
0x14040ef94  mov     cs:WdLogGlobalForLineNumber, 0A64h
0x14040ef9e  jmp     loc_14040F2E6
0x14040efa3  test    bl, dl
0x14040efa5  jnz     short loc_14040EF65
0x14040efa7  mov     rcx, [rdi+0FC0h]
0x14040efae  mov     edx, ebx
0x14040efb0  call    DxgkAcquireAdapterCoreSync
0x14040efb5  movsxd  rsi, eax
0x14040efb8  test    eax, eax
0x14040efba  jns     short loc_14040EF62
0x14040efbc  mov     rdx, rsi
0x14040efbf  mov     ecx, ebx
0x14040efc1  call    cs:__imp_WdLogSingleEntry1
0x14040efc8  nop     dword ptr [rax+rax+00h]
0x14040efcd  mov     cs:WdLogGlobalForLineNumber, 0A49h
0x14040efd7  jmp     loc_14040F32A
0x14040efdc  mov     r13b, 1
0x14040efdf  mov     eax, [r15+28h]
0x14040efe3  test    al, 4
0x14040efe5  jz      short loc_14040F028
0x14040efe7  mov     rax, [rdi+0BD0h]
0x14040efee  mov     rcx, [rdi+0BB8h]
0x14040eff5  call    _guard_dispatch_icall
0x14040effa  movsxd  rsi, eax
0x14040effd  test    eax, eax
0x14040efff  jns     short loc_14040F028
0x14040f001  mov     rdx, [rdi+0BD0h]
0x14040f008  mov     r8, rsi
0x14040f00b  mov     ecx, ebx
0x14040f00d  call    cs:__imp_WdLogSingleEntry2
0x14040f014  nop     dword ptr [rax+rax+00h]
0x14040f019  mov     cs:WdLogGlobalForLineNumber, 0A7Bh
0x14040f023  jmp     loc_14040F2AE
0x14040f028  mov     dword ptr [rdi+1018h], 5
0x14040f032  mov     eax, [r15+28h]
0x14040f036  or      [rdi+101Ch], eax
0x14040f03c  jmp     loc_14040F2AA
0x14040f041  mov     ebx, [rdi+1018h]
0x14040f047  cmp     ebx, 3
0x14040f04a  jz      loc_14040F19C
0x14040f050  mov     rcx, [rdi+0FC0h]
0x14040f057  test    rcx, rcx
0x14040f05a  jz      loc_14040F19C
0x14040f060  cmp     r8d, 4
0x14040f064  jnz     short loc_14040F09F
0x14040f066  lea     rcx, [rdi+10A8h]; Event
0x14040f06d  call    cs:__imp_KeClearEvent
0x14040f074  nop     dword ptr [rax+rax+00h]
0x14040f079  lea     rcx, [r15+30h]; Event
0x14040f07d  mov     [r15+48h], esi
0x14040f081  xor     r8d, r8d; Wait
0x14040f084  xor     edx, edx; Increment
0x14040f086  xor     bpl, bpl
0x14040f089  call    cs:__imp_KeSetEvent
0x14040f090  nop     dword ptr [rax+rax+00h]
0x14040f095  mov     rcx, [rdi+0FC0h]
0x14040f09c  xor     r15d, r15d
0x14040f09f  cmp     ebx, 1
0x14040f0a2  jz      short loc_14040F0B0
0x14040f0a4  mov     edx, 3
0x14040f0a9  call    DxgkAcquireAdapterCoreSync
0x14040f0ae  mov     esi, eax
0x14040f0b0  mov     rcx, [rdi+0FC0h]; this
0x14040f0b7  test    rcx, rcx
0x14040f0ba  jz      short loc_14040F0C1
0x14040f0bc  call    ?PrepareToRemove@DXGADAPTER@@QEAAXXZ; DXGADAPTER::PrepareToRemove(void)
0x14040f0c1  cmp     ebx, 1
0x14040f0c4  jz      short loc_14040F0D9
0x14040f0c6  mov     rcx, [rdi+0FC0h]
0x14040f0cd  mov     edx, 3
0x14040f0d2  call    DxgkReleaseAdapterCoreSync
0x14040f0d7  mov     esi, eax
0x14040f0d9  cmp     qword ptr [rdi+1E8h], 0
0x14040f0e1  jz      short loc_14040F12B
0x14040f0e3  lea     rcx, [rdi+1090h]; Event
0x14040f0ea  xor     r8d, r8d; Wait
0x14040f0ed  xor     edx, edx; Increment
0x14040f0ef  call    cs:__imp_KeSetEvent
0x14040f0f6  nop     dword ptr [rax+rax+00h]
0x14040f0fb  mov     rcx, [rdi+1E8h]
0x14040f102  call    cs:__imp_PoFxUnregisterDevice
0x14040f109  nop     dword ptr [rax+rax+00h]
0x14040f10e  mov     rax, [rdi+0FC0h]
0x14040f115  mov     qword ptr [rax+0D20h], 0
0x14040f120  mov     qword ptr [rdi+1E8h], 0
0x14040f12b  cmp     ebx, 1
0x14040f12e  jnz     short loc_14040F157
0x14040f130  test    byte ptr [rdi+0FC8h], 18h
0x14040f137  lea     edx, [rbx+4]
0x14040f13a  jnz     short loc_14040F149
0x14040f13c  cmp     [rdi+488h], r12b
0x14040f143  lea     eax, [rbx+1]
0x14040f146  cmovnz  edx, eax
0x14040f149  mov     rcx, [rdi+0FC0h]
0x14040f150  call    DxgkReleaseAdapterCoreSync
0x14040f155  mov     esi, eax
0x14040f157  mov     r9b, [rdi+489h]
0x14040f15e  mov     rdx, rdi
0x14040f161  mov     r8b, [rdi+488h]
0x14040f168  mov     rcx, r14
0x14040f16b  mov     byte ptr [rsp+0B8h+ReturnLength], 1
0x14040f170  call    DpiRemoveAdapter
0x14040f175  lea     rcx, [rdi+10A8h]; Event
0x14040f17c  mov     dword ptr [rdi+1018h], 3
0x14040f186  xor     r8d, r8d; Wait
0x14040f189  xor     edx, edx; Increment
0x14040f18b  call    cs:__imp_KeSetEvent
0x14040f192  nop     dword ptr [rax+rax+00h]
0x14040f197  jmp     loc_14040F2AA
0x14040f19c  mov     dword ptr [rdi+1018h], 3
0x14040f1a6  jmp     loc_14040F2AA
  ... truncated ...
```
