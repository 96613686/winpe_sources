# DpiPowerArbiterThread

- ea: `0x14040a7d0`
- end: `0x14040b1b2`
- name: `DpiPowerArbiterThread`
- size: `2530`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `24`
- tags: `service_task`

## callees

- `0x14001f780`
- `0x140022024`
- `0x140022924`
- `0x140035dc0`
- `0x140040d00`
- `0x140041b54`
- `0x140057894`
- `0x14007f438`
- `0x14007f57c`
- `0x1400a01e0`
- `0x1401c03f0`
- `0x1401dcf5c`
- `0x1401ebe6c`
- `0x14036758c`
- `0x140367a3c`
- `0x140367bd4`
- `0x1403a86fc`
- `0x1403b2ec0`
- `0x1403bd334`
- `0x1403f0dac`
- `0x1403f0f30`
- `0x1403f1998`
- `0x1403fa9a0`
- `0x14040a7d0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14040af44`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14040af44`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14040af71`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14040af71`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14040af56`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14040af56`
- `ntoskrnl!ExReleaseResourceLite` at `0x14040af65`
- `ntoskrnl!ExReleaseResourceLite` at `0x14040af65`
- `ntoskrnl!PoFxUnregisterDevice` at `0x14040ac82`
- `ntoskrnl!PoFxUnregisterDevice` at `0x14040ac82`
- `ntoskrnl!KeClearEvent` at `0x14040abed`
- `ntoskrnl!KeClearEvent` at `0x14040abed`
- `ntoskrnl!PsTerminateSystemThread` at `0x14040aefc`
- `ntoskrnl!PsTerminateSystemThread` at `0x14040aefc`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14040a836`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14040a836`
- `ntoskrnl!KeSetEvent` at `0x14040ac09`
- `ntoskrnl!KeSetEvent` at `0x14040ac6f`
- `ntoskrnl!KeSetEvent` at `0x14040ad0b`
- `ntoskrnl!KeSetEvent` at `0x14040ad9a`
- `ntoskrnl!KeSetEvent` at `0x14040ae16`
- `ntoskrnl!KeSetEvent` at `0x14040aebc`
- `ntoskrnl!KeSetEvent` at `0x14040ac09`
- `ntoskrnl!KeSetEvent` at `0x14040ac6f`
- `ntoskrnl!KeSetEvent` at `0x14040ad0b`
- `ntoskrnl!KeSetEvent` at `0x14040ad9a`
- `ntoskrnl!KeSetEvent` at `0x14040ae16`
- `ntoskrnl!KeSetEvent` at `0x14040aebc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14040a8b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14040a8b2`
- `ntoskrnl!KeSetBasePriorityThread` at `0x14040a87e`
- `ntoskrnl!KeSetBasePriorityThread` at `0x14040a87e`
- `watchdog!WdLogSingleEntry4` at `0x14040a9c8`
- `watchdog!WdLogSingleEntry4` at `0x14040a9c8`
- `watchdog!WdLogSingleEntry2` at `0x14040ab8d`
- `watchdog!WdLogSingleEntry2` at `0x14040ab8d`
- `watchdog!WdLogSingleEntry3` at `0x14040aa1b`
- `watchdog!WdLogSingleEntry3` at `0x14040aa8f`
- `watchdog!WdLogSingleEntry3` at `0x14040ad74`
- `watchdog!WdLogSingleEntry3` at `0x14040ae8f`
- `watchdog!WdLogSingleEntry3` at `0x14040afb8`
- `watchdog!WdLogSingleEntry3` at `0x14040aff2`
- `watchdog!WdLogSingleEntry3` at `0x14040b09b`
- `watchdog!WdLogSingleEntry3` at `0x14040b123`
- `watchdog!WdLogSingleEntry3` at `0x14040aa1b`
- `watchdog!WdLogSingleEntry3` at `0x14040aa8f`
- `watchdog!WdLogSingleEntry3` at `0x14040ad74`
- `watchdog!WdLogSingleEntry3` at `0x14040ae8f`
- `watchdog!WdLogSingleEntry3` at `0x14040afb8`
- `watchdog!WdLogSingleEntry3` at `0x14040aff2`
- `watchdog!WdLogSingleEntry3` at `0x14040b09b`
- `watchdog!WdLogSingleEntry3` at `0x14040b123`
- `watchdog!WdLogSingleEntry1` at `0x14040a84e`
- `watchdog!WdLogSingleEntry1` at `0x14040a8ce`
- `watchdog!WdLogSingleEntry1` at `0x14040aa4a`
- `watchdog!WdLogSingleEntry1` at `0x14040ab08`
- `watchdog!WdLogSingleEntry1` at `0x14040ab41`
- `watchdog!WdLogSingleEntry1` at `0x14040ae4e`
- `watchdog!WdLogSingleEntry1` at `0x14040a84e`
- `watchdog!WdLogSingleEntry1` at `0x14040a8ce`
- `watchdog!WdLogSingleEntry1` at `0x14040aa4a`
- `watchdog!WdLogSingleEntry1` at `0x14040ab08`
- `watchdog!WdLogSingleEntry1` at `0x14040ab41`
- `watchdog!WdLogSingleEntry1` at `0x14040ae4e`

## pseudocode

```c
void __fastcall DpiPowerArbiterThread(_QWORD *StartContext)
{
  __int64 v1; // rdi
  int v2; // esi
  void *v3; // rax
  char v4; // r12
  char v5; // r13
  int Blink; // edx
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v7; // r14
  bool v8; // bp
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  int v15; // ebx
  __int64 v16; // rcx
  struct _LIST_ENTRY *v17; // r15
  DXGADAPTER *v18; // rcx
  __int64 v19; // rdx
  DXGADAPTER *v20; // rcx
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v21; // r8
  int v22; // ebx
  char IsPowerRuntimeDStateTransition; // r14
  int v24; // ebx
  int v25; // eax
  struct _LIST_ENTRY *PowerActionQueueEntry; // rax
  int v27; // eax
  DXGADAPTER **v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  unsigned __int8 started; // al
  DXGADAPTER *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  _BYTE v37[8]; // [rsp+30h] [rbp-88h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v38; // [rsp+38h] [rbp-80h]
  __int128 ProcessInformation; // [rsp+40h] [rbp-78h] BYREF
  __int128 v40; // [rsp+50h] [rbp-68h]
  __int128 v41; // [rsp+60h] [rbp-58h]

  v1 = StartContext[8];
  *(_QWORD *)(v1 + 4096) = KeGetCurrentThread();
  if ( (unsigned int)Feature_BoostPriorityOfPowerArbiterThread__private_IsEnabledDeviceUsageNoInline() )
  {
    ProcessInformation = 0;
    v40 = 0;
    v41 = 0;
    v2 = ZwQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessBasicInformation, &ProcessInformation, 0x30u, 0);
    if ( v2 >= 0 )
    {
      if ( SDWORD2(v40) < 15 )
        KeSetBasePriorityThread(KeGetCurrentThread(), 15 - DWORD2(v40));
    }
    else
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2053;
    }
  }
  else
  {
    v2 = 0;
  }
  if ( *(_DWORD *)(v1 + 4120) != 7 )
  {
    v3 = (void *)(v1 + 4072);
    while ( 1 )
    {
      v2 = KeWaitForSingleObject(v3, Executive, 0, 0, 0);
      if ( !v2 )
        break;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2087;
LABEL_88:
      v3 = (void *)(v1 + 4072);
      if ( *(_DWORD *)(v1 + 4120) == 7 )
        goto LABEL_89;
    }
    while ( 1 )
    {
      PowerActionQueueEntry = DpiGetPowerActionQueueEntry((struct _FDO_CONTEXT *)v1);
      v17 = PowerActionQueueEntry;
      if ( !PowerActionQueueEntry )
        goto LABEL_88;
      v2 = 0;
      v37[0] = 0;
      v4 = 0;
      v5 = 0;
      CDisplayScenarioContextScope::ContextScopeConstructor(
        (CDisplayScenarioContextScope *)v37,
        (const struct _GUID *)((char *)&PowerActionQueueEntry[4].Blink + 4),
        0x45u,
        0);
      Blink = (int)v17[2].Blink;
      v7 = v38;
      v8 = Blink != 64;
      if ( LODWORD(v17[1].Blink) != 1 )
        break;
      if ( ((*(_DWORD *)(v1 + 4120) - 1) & 0xFFFFFFFD) != 0 )
      {
        DxgkShutdownBootGraphics(0, 0);
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite((PERESOURCE)(v1 + 3928), 1u);
        ExReleaseResourceLite((PERESOURCE)(v1 + 3928));
        KeLeaveCriticalRegion();
        v27 = (int)v17[2].Blink;
        v28 = (DXGADAPTER **)(v1 + 4032);
        v29 = *(_QWORD *)(v1 + 4032);
        if ( (v27 & 0x40) != 0 )
        {
          DxgkAcquireAdapterCoreSync(v29, 4);
          if ( !(unsigned __int8)DxgkIsAdapterCoreSyncAcquired(*v28, 2) )
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
          v30 = 6;
          if ( (v27 & 0x98) == 0 )
            v30 = 3;
          DxgkAcquireAdapterCoreSync(v29, v30);
        }
        if ( *(_DWORD *)(v1 + 284) == 1 )
        {
          MonitorAdapterPowerChange(*v28, 1u, v7);
          DmmAdapterPowerChange(*v28, 1u);
        }
        DmmResetModeState(*v28, 0xFFFFFFFF);
        v31 = (int)v17[2].Blink;
        if ( (v31 & 0x20) != 0 )
        {
          v32 = 4;
          goto LABEL_120;
        }
        if ( (v31 & 0x10) != 0 )
        {
          v32 = 3;
          goto LABEL_120;
        }
        if ( (v31 & 8) != 0 )
        {
          v32 = 2;
          goto LABEL_120;
        }
        if ( (v31 & 0x80u) != 0 )
        {
          v32 = 5;
          goto LABEL_120;
        }
        if ( (v31 & 0x40) == 0 )
        {
          v32 = 1;
LABEL_120:
          DXGADAPTER::ApplyCoreSyncAction(*v28, v32);
LABEL_121:
          *(_DWORD *)(v1 + 4120) = 1;
          goto LABEL_84;
        }
        WdLogSingleEntry3(9, v1, 1, 0);
        WdLogGlobalForLineNumber = 2235;
        if ( *(_BYTE *)(v1 + 5816) )
          DxgkNotifySharedPowerGraphicsPowerTransition(*v28, PowerDeviceD3, 1u);
        started = DpiStartSuspendingAdapter((struct _FDO_CONTEXT *)v1);
        v34 = *v28;
        if ( started )
        {
          DXGADAPTER::ApplyCoreSyncAction(v34, 3);
          DpiFinishSuspendAdapter((struct _FDO_CONTEXT *)v1);
          if ( *(_DWORD *)(v1 + 4120) == 1 )
          {
            if ( *(_BYTE *)(v1 + 5816) )
              DxgkNotifySharedPowerGraphicsPowerTransition(*v28, PowerDeviceD3, 0);
            goto LABEL_121;
          }
          WdLogSingleEntry3(9, v1, 0, 0);
          WdLogGlobalForLineNumber = 2275;
          v35 = 5;
          v34 = *v28;
        }
        else
        {
          v35 = 2;
        }
        DxgkReleaseAdapterCoreSync(v34, v35);
        DpiSetDevicePowerTransitionStateAtPassiveLevel(v1, 0);
        if ( *(_BYTE *)(v1 + 5816) )
          DxgkNotifySharedPowerGraphicsPowerTransition(*v28, PowerDeviceD0, 0);
      }
      else if ( (unsigned __int8)DpiIsPowerRuntimeDStateTransition(v1) )
      {
        DpiSetDevicePowerTransitionStateAtPassiveLevel(v36, 5);
      }
LABEL_84:
      if ( v8 )
      {
        LODWORD(v17[4].Blink) = v2;
        KeSetEvent((PRKEVENT)&v17[3], 0, 0);
      }
      CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v37);
    }
    if ( LODWORD(v17[1].Blink) == 2 )
    {
      if ( *(_DWORD *)(v1 + 4120) == 1 )
      {
        v20 = *(DXGADAPTER **)(v1 + 4032);
        v21 = v38;
        *(_DWORD *)(v1 + 4120) = 2;
        v22 = (int)v17[2].Blink;
        MonitorAdapterPowerChange(v20, 0, v21);
        IsPowerRuntimeDStateTransition = DpiIsPowerRuntimeDStateTransition(v1);
        if ( IsPowerRuntimeDStateTransition )
        {
          if ( v22 != 64 )
          {
            WdLogSingleEntry3(9, v1, 0, 0);
            WdLogGlobalForLineNumber = 2379;
            LODWORD(v17[4].Blink) = 0;
            v8 = 0;
            KeSetEvent((PRKEVENT)&v17[3], 0, 0);
            v17 = 0;
            if ( *(_BYTE *)(v1 + 5816) )
              DxgkNotifySharedPowerGraphicsPowerTransition(*(void **)(v1 + 4032), PowerDeviceD0, 0);
          }
        }
        v2 = DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), 5);
        if ( IsPowerRuntimeDStateTransition )
        {
          if ( v22 == 64 )
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
    if ( LODWORD(v17[1].Blink) == 3 || LODWORD(v17[1].Blink) == 4 )
    {
      v15 = *(_DWORD *)(v1 + 4120);
      if ( v15 == 3 || (v16 = *(_QWORD *)(v1 + 4032)) == 0 )
      {
        *(_DWORD *)(v1 + 4120) = 3;
      }
      else
      {
        if ( LODWORD(v17[1].Blink) == 4 )
        {
          KeClearEvent((PRKEVENT)(v1 + 4264));
          LODWORD(v17[4].Blink) = 0;
          v8 = 0;
          KeSetEvent((PRKEVENT)&v17[3], 0, 0);
          v16 = *(_QWORD *)(v1 + 4032);
          v17 = 0;
        }
        if ( v15 != 1 )
          v2 = DxgkAcquireAdapterCoreSync(v16, 3);
        v18 = *(DXGADAPTER **)(v1 + 4032);
        if ( v18 )
          DXGADAPTER::PrepareToRemove(v18);
        if ( v15 != 1 )
          v2 = DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), 3);
        if ( *(_QWORD *)(v1 + 488) )
        {
          KeSetEvent((PRKEVENT)(v1 + 4240), 0, 0);
          PoFxUnregisterDevice(*(_QWORD *)(v1 + 488));
          *(_QWORD *)(*(_QWORD *)(v1 + 4032) + 3344LL) = 0;
          *(_QWORD *)(v1 + 488) = 0;
        }
        if ( v15 == 1 )
        {
          v19 = 5;
          if ( (*(_BYTE *)(v1 + 4040) & 0x18) == 0 && *(_BYTE *)(v1 + 1160) )
            v19 = 2;
          v2 = DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), v19);
        }
        DpiRemoveAdapter(v7, 1);
        *(_DWORD *)(v1 + 4120) = 3;
        KeSetEvent((PRKEVENT)(v1 + 4264), 0, 0);
      }
      goto LABEL_77;
    }
    if ( LODWORD(v17[1].Blink) != 5 )
    {
      if ( LODWORD(v17[1].Blink) == 6 )
      {
        v9 = *(_DWORD *)(v1 + 4124);
        if ( (v9 & 4) != 0 )
        {
          v10 = *(_QWORD *)(v1 + 3000);
          *(_DWORD *)(v1 + 4124) = v9 & 0xFFFFFFFB;
          v11 = (*(__int64 (__fastcall **)(__int64))(v1 + 3032))(v10);
          if ( v11 < 0 )
          {
            WdLogSingleEntry4(0, 275, 21, *(_QWORD *)(v1 + 3032), v11);
            WdLogGlobalForLineNumber = 2723;
          }
        }
        v12 = *(_DWORD *)(v1 + 4124);
        v13 = *(_QWORD *)(v1 + 4032);
        if ( (v12 & 1) != 0 )
        {
          *(_DWORD *)(v1 + 4124) = v12 & 0xFFFFFFFE;
          v14 = DxgkReleaseAdapterCoreSync(v13, 5);
          v2 = v14;
          if ( v14 < 0 )
          {
            WdLogSingleEntry3(0, 275, 21, v14);
            WdLogGlobalForLineNumber = 2744;
          }
        }
        else
        {
          v2 = DxgkResumeMemorySegments(v13);
          if ( v2 < 0 )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 2763;
          }
          if ( (*(_DWORD *)(v1 + 4124) & 2) == 0 && (int)DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), 2) < 0 )
          {
            WdLogSingleEntry3(0, 275, 21, v2);
            WdLogGlobalForLineNumber = 2787;
          }
          *(_DWORD *)(v1 + 4124) &= ~2u;
        }
        *(_DWORD *)(v1 + 4120) = 6;
      }
      else
      {
        if ( LODWORD(v17[1].Blink) != 7 )
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
      v2 = DxgkAcquireAdapterCoreSync(*(_QWORD *)(v1 + 4032), 2);
      if ( v2 < 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 2633;
        goto LABEL_84;
      }
    }
    v4 = 1;
LABEL_37:
    if ( ((__int64)v17[2].Blink & 1) == 0 )
    {
      v2 = DxgkSuspendMemorySegments(*(_QWORD *)(v1 + 4032));
      if ( v2 < 0 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 2660;
LABEL_81:
        if ( v4 == 1 )
        {
          v25 = DxgkReleaseAdapterCoreSync(*(_QWORD *)(v1 + 4032), 5);
          if ( v25 < 0 )
          {
            WdLogSingleEntry3(0, 275, 21, v25);
            WdLogGlobalForLineNumber = 2863;
          }
        }
        goto LABEL_84;
      }
      v5 = 1;
    }
    if ( ((__int64)v17[2].Blink & 4) != 0 )
    {
      v2 = (*(__int64 (__fastcall **)(_QWORD))(v1 + 3024))(*(_QWORD *)(v1 + 3000));
      if ( v2 < 0 )
      {
        WdLogSingleEntry2(2, *(_QWORD *)(v1 + 3024));
        WdLogGlobalForLineNumber = 2683;
LABEL_78:
        if ( v5 == 1 )
        {
          v24 = DxgkResumeMemorySegments(*(_QWORD *)(v1 + 4032));
          if ( v24 < 0 )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 2843;
            v2 = v24;
          }
        }
        goto LABEL_81;
      }
    }
    *(_DWORD *)(v1 + 4120) = 5;
    *(_DWORD *)(v1 + 4124) |= LODWORD(v17[2].Blink);
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
0x14040a7d0  push    rbx
0x14040a7d2  push    rbp
0x14040a7d3  push    rsi
0x14040a7d4  push    rdi
0x14040a7d5  push    r12
0x14040a7d7  push    r13
0x14040a7d9  push    r14
0x14040a7db  push    r15
0x14040a7dd  sub     rsp, 78h
0x14040a7e1  mov     rdi, [rcx+40h]
0x14040a7e5  mov     rax, gs:188h
0x14040a7ee  mov     [rdi+1000h], rax
0x14040a7f5  call    Feature_BoostPriorityOfPowerArbiterThread__private_IsEnabledDeviceUsageNoInline
0x14040a7fa  mov     ebx, 2
0x14040a7ff  test    eax, eax
0x14040a801  jnz     short loc_14040A80A
0x14040a803  xor     esi, esi
0x14040a805  jmp     loc_14040A88A
0x14040a80a  xorps   xmm0, xmm0
0x14040a80d  mov     [rsp+0B8h+ReturnLength], 0; ReturnLength
0x14040a816  mov     r9d, 30h ; '0'; ProcessInformationLength
0x14040a81c  lea     r8, [rsp+0B8h+ProcessInformation]; ProcessInformation
0x14040a821  xor     edx, edx; ProcessInformationClass
0x14040a823  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14040a827  movups  [rsp+0B8h+ProcessInformation], xmm0
0x14040a82c  movups  [rsp+0B8h+var_68], xmm0
0x14040a831  movups  [rsp+0B8h+var_58], xmm0
0x14040a836  call    cs:__imp_ZwQueryInformationProcess
0x14040a83d  nop     dword ptr [rax+rax+00h]
0x14040a842  movsxd  rsi, eax
0x14040a845  test    eax, eax
0x14040a847  jns     short loc_14040A866
0x14040a849  mov     rdx, rsi
0x14040a84c  mov     ecx, ebx
0x14040a84e  call    cs:__imp_WdLogSingleEntry1
0x14040a855  nop     dword ptr [rax+rax+00h]
0x14040a85a  mov     cs:WdLogGlobalForLineNumber, 805h
0x14040a864  jmp     short loc_14040A88A
0x14040a866  mov     edx, 0Fh
0x14040a86b  cmp     dword ptr [rsp+0B8h+var_68+8], edx
0x14040a86f  jge     short loc_14040A88A
0x14040a871  sub     edx, dword ptr [rsp+0B8h+var_68+8]; Increment
0x14040a875  mov     rcx, gs:188h; Thread
0x14040a87e  call    cs:__imp_KeSetBasePriorityThread
0x14040a885  nop     dword ptr [rax+rax+00h]
0x14040a88a  cmp     dword ptr [rdi+1018h], 7
0x14040a891  jz      loc_14040AEFA
0x14040a897  lea     rax, [rdi+0FE8h]
0x14040a89e  xor     r9d, r9d; Alertable
0x14040a8a1  mov     [rsp+0B8h+ReturnLength], 0; Timeout
0x14040a8aa  xor     r8d, r8d; WaitMode
0x14040a8ad  xor     edx, edx; WaitReason
0x14040a8af  mov     rcx, rax; Object
0x14040a8b2  call    cs:__imp_KeWaitForSingleObject
0x14040a8b9  nop     dword ptr [rax+rax+00h]
0x14040a8be  movsxd  rsi, eax
0x14040a8c1  test    eax, eax
0x14040a8c3  jz      loc_14040AED2
0x14040a8c9  mov     rdx, rsi
0x14040a8cc  mov     ecx, ebx
0x14040a8ce  call    cs:__imp_WdLogSingleEntry1
0x14040a8d5  nop     dword ptr [rax+rax+00h]
0x14040a8da  mov     cs:WdLogGlobalForLineNumber, 827h
0x14040a8e4  jmp     loc_14040AEE6
0x14040a8e9  xor     esi, esi
0x14040a8eb  lea     rdx, [r15+4Ch]; struct _GUID *
0x14040a8ef  xor     r9d, r9d; unsigned int
0x14040a8f2  mov     [rsp+0B8h+var_88], sil
0x14040a8f7  lea     rcx, [rsp+0B8h+var_88]; this
0x14040a8fc  xor     r12b, r12b
0x14040a8ff  xor     r13b, r13b
0x14040a902  lea     r8d, [rsi+45h]; unsigned int
0x14040a906  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x14040a90b  mov     edx, [r15+28h]
0x14040a90f  cmp     edx, 40h ; '@'
0x14040a912  mov     r8d, [r15+18h]
0x14040a916  mov     ecx, r8d
0x14040a919  mov     r14, [rsp+0B8h+var_80]
0x14040a91e  setnz   bpl
0x14040a922  sub     ecx, 1
0x14040a925  jz      loc_14040AF1A
0x14040a92b  sub     ecx, 1
0x14040a92e  jz      loc_14040AD2B
0x14040a934  sub     ecx, 1
0x14040a937  jz      loc_14040ABC1
0x14040a93d  sub     ecx, 1
0x14040a940  jz      loc_14040ABC1
0x14040a946  sub     ecx, 1
0x14040a949  jz      loc_14040AABB
0x14040a94f  sub     ecx, 1
0x14040a952  jz      short loc_14040A985
0x14040a954  cmp     ecx, 1
0x14040a957  jnz     loc_14040AEAA
0x14040a95d  cmp     [rdi+1018h], ecx
0x14040a963  jnz     short loc_14040A976
0x14040a965  mov     rcx, [rdi+0FC0h]
0x14040a96c  lea     edx, [rsi+5]
0x14040a96f  call    DxgkReleaseAdapterCoreSync
0x14040a974  mov     esi, eax
0x14040a976  mov     dword ptr [rdi+1018h], 7
0x14040a980  jmp     loc_14040AE2A
0x14040a985  mov     eax, [rdi+101Ch]
0x14040a98b  test    al, 4
0x14040a98d  jz      short loc_14040A9DE
0x14040a98f  mov     rcx, [rdi+0BB8h]
0x14040a996  and     eax, 0FFFFFFFBh
0x14040a999  mov     [rdi+101Ch], eax
0x14040a99f  mov     rax, [rdi+0BD8h]
0x14040a9a6  call    _guard_dispatch_icall
0x14040a9ab  test    eax, eax
0x14040a9ad  jns     short loc_14040A9DE
0x14040a9af  mov     r9, [rdi+0BD8h]
0x14040a9b6  xor     ecx, ecx
0x14040a9b8  cdqe
0x14040a9ba  mov     edx, 113h
0x14040a9bf  mov     [rsp+0B8h+ReturnLength], rax
0x14040a9c4  lea     r8d, [rcx+15h]
0x14040a9c8  call    cs:__imp_WdLogSingleEntry4
0x14040a9cf  nop     dword ptr [rax+rax+00h]
0x14040a9d4  mov     cs:WdLogGlobalForLineNumber, 0AA3h
0x14040a9de  mov     eax, [rdi+101Ch]
0x14040a9e4  mov     rcx, [rdi+0FC0h]
0x14040a9eb  test    al, 1
0x14040a9ed  jz      short loc_14040AA33
0x14040a9ef  and     eax, 0FFFFFFFEh
0x14040a9f2  mov     edx, 5
0x14040a9f7  mov     [rdi+101Ch], eax
0x14040a9fd  call    DxgkReleaseAdapterCoreSync
0x14040aa02  movsxd  rsi, eax
0x14040aa05  test    eax, eax
0x14040aa07  jns     loc_14040AAAC
0x14040aa0d  xor     ecx, ecx
0x14040aa0f  mov     r9, rsi
0x14040aa12  mov     edx, 113h
0x14040aa17  lea     r8d, [rcx+15h]
0x14040aa1b  call    cs:__imp_WdLogSingleEntry3
0x14040aa22  nop     dword ptr [rax+rax+00h]
0x14040aa27  mov     cs:WdLogGlobalForLineNumber, 0AB8h
0x14040aa31  jmp     short loc_14040AAAC
0x14040aa33  call    DxgkResumeMemorySegments
0x14040aa38  movsxd  rsi, eax
0x14040aa3b  mov     rbx, rsi
0x14040aa3e  test    eax, eax
0x14040aa40  jns     short loc_14040AA60
0x14040aa42  mov     rdx, rbx
0x14040aa45  mov     ecx, 2
0x14040aa4a  call    cs:__imp_WdLogSingleEntry1
0x14040aa51  nop     dword ptr [rax+rax+00h]
0x14040aa56  mov     cs:WdLogGlobalForLineNumber, 0ACBh
0x14040aa60  mov     eax, [rdi+101Ch]
0x14040aa66  mov     ecx, 2
0x14040aa6b  test    cl, al
0x14040aa6d  jnz     short loc_14040AAA5
0x14040aa6f  mov     edx, ecx
0x14040aa71  mov     rcx, [rdi+0FC0h]
0x14040aa78  call    DxgkReleaseAdapterCoreSync
0x14040aa7d  test    eax, eax
0x14040aa7f  jns     short loc_14040AAA5
0x14040aa81  xor     ecx, ecx
0x14040aa83  mov     r9, rbx
0x14040aa86  mov     edx, 113h
0x14040aa8b  lea     r8d, [rcx+15h]
0x14040aa8f  call    cs:__imp_WdLogSingleEntry3
0x14040aa96  nop     dword ptr [rax+rax+00h]
0x14040aa9b  mov     cs:WdLogGlobalForLineNumber, 0AE3h
0x14040aaa5  and     dword ptr [rdi+101Ch], 0FFFFFFFDh
0x14040aaac  mov     dword ptr [rdi+1018h], 6
0x14040aab6  jmp     loc_14040AE2A
0x14040aabb  test    dl, 1
0x14040aabe  jz      short loc_14040AB23
0x14040aac0  mov     rcx, [rdi+0FC0h]
0x14040aac7  mov     edx, 3
0x14040aacc  call    DxgkAcquireAdapterCoreSync
0x14040aad1  mov     rcx, [rdi+0FC0h]
0x14040aad8  mov     edx, 1
0x14040aadd  call    ?ApplyCoreSyncAction@DXGADAPTER@@QEAAXW4DXGADAPTERCORESYNC_ACTION@@@Z; DXGADAPTER::ApplyCoreSyncAction(DXGADAPTERCORESYNC_ACTION)
0x14040aae2  mov     r12b, 1
0x14040aae5  mov     eax, [r15+28h]
0x14040aae9  test    al, 1
0x14040aaeb  jnz     short loc_14040AB5F
0x14040aaed  mov     rcx, [rdi+0FC0h]
0x14040aaf4  call    DxgkSuspendMemorySegments
0x14040aaf9  movsxd  rsi, eax
0x14040aafc  test    eax, eax
0x14040aafe  jns     short loc_14040AB5C
0x14040ab00  mov     rdx, rsi
0x14040ab03  mov     ecx, 3
0x14040ab08  call    cs:__imp_WdLogSingleEntry1
0x14040ab0f  nop     dword ptr [rax+rax+00h]
0x14040ab14  mov     cs:WdLogGlobalForLineNumber, 0A64h
0x14040ab1e  jmp     loc_14040AE66
0x14040ab23  test    bl, dl
0x14040ab25  jnz     short loc_14040AAE5
0x14040ab27  mov     rcx, [rdi+0FC0h]
0x14040ab2e  mov     edx, ebx
0x14040ab30  call    DxgkAcquireAdapterCoreSync
0x14040ab35  movsxd  rsi, eax
0x14040ab38  test    eax, eax
0x14040ab3a  jns     short loc_14040AAE2
0x14040ab3c  mov     rdx, rsi
0x14040ab3f  mov     ecx, ebx
0x14040ab41  call    cs:__imp_WdLogSingleEntry1
0x14040ab48  nop     dword ptr [rax+rax+00h]
0x14040ab4d  mov     cs:WdLogGlobalForLineNumber, 0A49h
0x14040ab57  jmp     loc_14040AEAA
0x14040ab5c  mov     r13b, 1
0x14040ab5f  mov     eax, [r15+28h]
0x14040ab63  test    al, 4
0x14040ab65  jz      short loc_14040ABA8
0x14040ab67  mov     rax, [rdi+0BD0h]
0x14040ab6e  mov     rcx, [rdi+0BB8h]
0x14040ab75  call    _guard_dispatch_icall
0x14040ab7a  movsxd  rsi, eax
0x14040ab7d  test    eax, eax
0x14040ab7f  jns     short loc_14040ABA8
0x14040ab81  mov     rdx, [rdi+0BD0h]
0x14040ab88  mov     r8, rsi
0x14040ab8b  mov     ecx, ebx
0x14040ab8d  call    cs:__imp_WdLogSingleEntry2
0x14040ab94  nop     dword ptr [rax+rax+00h]
0x14040ab99  mov     cs:WdLogGlobalForLineNumber, 0A7Bh
0x14040aba3  jmp     loc_14040AE2E
0x14040aba8  mov     dword ptr [rdi+1018h], 5
0x14040abb2  mov     eax, [r15+28h]
0x14040abb6  or      [rdi+101Ch], eax
0x14040abbc  jmp     loc_14040AE2A
0x14040abc1  mov     ebx, [rdi+1018h]
0x14040abc7  cmp     ebx, 3
0x14040abca  jz      loc_14040AD1C
0x14040abd0  mov     rcx, [rdi+0FC0h]
0x14040abd7  test    rcx, rcx
0x14040abda  jz      loc_14040AD1C
0x14040abe0  cmp     r8d, 4
0x14040abe4  jnz     short loc_14040AC1F
0x14040abe6  lea     rcx, [rdi+10A8h]; Event
0x14040abed  call    cs:__imp_KeClearEvent
0x14040abf4  nop     dword ptr [rax+rax+00h]
0x14040abf9  lea     rcx, [r15+30h]; Event
0x14040abfd  mov     [r15+48h], esi
0x14040ac01  xor     r8d, r8d; Wait
0x14040ac04  xor     edx, edx; Increment
0x14040ac06  xor     bpl, bpl
0x14040ac09  call    cs:__imp_KeSetEvent
0x14040ac10  nop     dword ptr [rax+rax+00h]
0x14040ac15  mov     rcx, [rdi+0FC0h]
0x14040ac1c  xor     r15d, r15d
0x14040ac1f  cmp     ebx, 1
0x14040ac22  jz      short loc_14040AC30
0x14040ac24  mov     edx, 3
0x14040ac29  call    DxgkAcquireAdapterCoreSync
0x14040ac2e  mov     esi, eax
0x14040ac30  mov     rcx, [rdi+0FC0h]; this
0x14040ac37  test    rcx, rcx
0x14040ac3a  jz      short loc_14040AC41
0x14040ac3c  call    ?PrepareToRemove@DXGADAPTER@@QEAAXXZ; DXGADAPTER::PrepareToRemove(void)
0x14040ac41  cmp     ebx, 1
0x14040ac44  jz      short loc_14040AC59
0x14040ac46  mov     rcx, [rdi+0FC0h]
0x14040ac4d  mov     edx, 3
0x14040ac52  call    DxgkReleaseAdapterCoreSync
0x14040ac57  mov     esi, eax
0x14040ac59  cmp     qword ptr [rdi+1E8h], 0
0x14040ac61  jz      short loc_14040ACAB
0x14040ac63  lea     rcx, [rdi+1090h]; Event
0x14040ac6a  xor     r8d, r8d; Wait
0x14040ac6d  xor     edx, edx; Increment
0x14040ac6f  call    cs:__imp_KeSetEvent
0x14040ac76  nop     dword ptr [rax+rax+00h]
0x14040ac7b  mov     rcx, [rdi+1E8h]
0x14040ac82  call    cs:__imp_PoFxUnregisterDevice
0x14040ac89  nop     dword ptr [rax+rax+00h]
0x14040ac8e  mov     rax, [rdi+0FC0h]
0x14040ac95  mov     qword ptr [rax+0D10h], 0
0x14040aca0  mov     qword ptr [rdi+1E8h], 0
0x14040acab  cmp     ebx, 1
0x14040acae  jnz     short loc_14040ACD7
0x14040acb0  test    byte ptr [rdi+0FC8h], 18h
0x14040acb7  lea     edx, [rbx+4]
0x14040acba  jnz     short loc_14040ACC9
0x14040acbc  cmp     [rdi+488h], r12b
0x14040acc3  lea     eax, [rbx+1]
0x14040acc6  cmovnz  edx, eax
0x14040acc9  mov     rcx, [rdi+0FC0h]
0x14040acd0  call    DxgkReleaseAdapterCoreSync
0x14040acd5  mov     esi, eax
0x14040acd7  mov     r9b, [rdi+489h]
0x14040acde  mov     rdx, rdi
0x14040ace1  mov     r8b, [rdi+488h]
0x14040ace8  mov     rcx, r14
0x14040aceb  mov     byte ptr [rsp+0B8h+ReturnLength], 1
0x14040acf0  call    DpiRemoveAdapter
0x14040acf5  lea     rcx, [rdi+10A8h]; Event
0x14040acfc  mov     dword ptr [rdi+1018h], 3
0x14040ad06  xor     r8d, r8d; Wait
0x14040ad09  xor     edx, edx; Increment
0x14040ad0b  call    cs:__imp_KeSetEvent
0x14040ad12  nop     dword ptr [rax+rax+00h]
0x14040ad17  jmp     loc_14040AE2A
0x14040ad1c  mov     dword ptr [rdi+1018h], 3
0x14040ad26  jmp     loc_14040AE2A
  ... truncated ...
```
