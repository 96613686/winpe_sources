# HbPnpDispatch

- ea: `0x1400140f0`
- end: `0x1400146bb`
- name: `HbPnpDispatch`
- size: `1483`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, IRP *Tag)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001600`
- `0x140002174`
- `0x14000f948`
- `0x14000fc48`
- `0x1400101d0`
- `0x1400140f0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140014620`
- `ntoskrnl!IoDeleteDevice` at `0x140014620`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001436b`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001436b`
- `ntoskrnl!EtwUnregister` at `0x14001450c`
- `ntoskrnl!EtwUnregister` at `0x14001453d`
- `ntoskrnl!EtwUnregister` at `0x14001450c`
- `ntoskrnl!EtwUnregister` at `0x14001453d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001415f`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001415f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400146ab`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400146ab`
- `ntoskrnl!KdDeregisterPowerHandler` at `0x1400143cf`
- `ntoskrnl!KdDeregisterPowerHandler` at `0x1400143cf`
- `ntoskrnl!ZwClose` at `0x1400143ee`
- `ntoskrnl!ZwClose` at `0x14001440d`
- `ntoskrnl!ZwClose` at `0x1400143ee`
- `ntoskrnl!ZwClose` at `0x14001440d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400144cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400144cc`
- `ntoskrnl!IofCompleteRequest` at `0x14001419b`
- `ntoskrnl!IofCompleteRequest` at `0x14001419b`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1400142b2`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1400142b2`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140014227`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14001439a`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140014227`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14001439a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140014237`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400143aa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140014237`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400143aa`
- `ntoskrnl!IofCallDriver` at `0x1400145ff`
- `ntoskrnl!IofCallDriver` at `0x140014690`
- `ntoskrnl!IofCallDriver` at `0x1400145ff`
- `ntoskrnl!IofCallDriver` at `0x140014690`
- `ntoskrnl!IoFreeMdl` at `0x140014482`
- `ntoskrnl!IoFreeMdl` at `0x140014482`
- `ntoskrnl!IoDetachDevice` at `0x140014611`
- `ntoskrnl!IoDetachDevice` at `0x140014611`
- `HAL!KeQueryPerformanceCounter` at `0x140014256`
- `HAL!KeQueryPerformanceCounter` at `0x1400142c5`
- `HAL!KeQueryPerformanceCounter` at `0x140014550`
- `HAL!KeQueryPerformanceCounter` at `0x140014256`
- `HAL!KeQueryPerformanceCounter` at `0x1400142c5`
- `HAL!KeQueryPerformanceCounter` at `0x140014550`
- `winhvr!WinHvSetEventLogCompletedNotificationRoutine` at `0x140014382`
- `winhvr!WinHvSetEventLogCompletedNotificationRoutine` at `0x140014382`
- `winhvr!WinHvUnmapStatsPage` at `0x14001449b`
- `winhvr!WinHvUnmapStatsPage` at `0x14001449b`

## string_xrefs

- `0x140014171`: `PnP dispatch: IoAcquireRemoveLock failed with 0x%x`
- `0x14001462c`: `Device removed`

## pseudocode

```c
__int64 __fastcall HbPnpDispatch(PDEVICE_OBJECT DeviceObject, IRP *Tag)
{
  char *DeviceExtension; // r15
  __int64 result; // rax
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v10; // rdx
  LONGLONG v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  _QWORD **v14; // r12
  _QWORD *v15; // rbx
  _QWORD *i; // rdi
  struct _MDL *v17; // rcx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  REGHANDLE v20; // rcx
  LARGE_INTEGER v21; // rax
  __int64 v22; // rdx
  LONGLONG v23; // rcx
  struct _DEVICE_OBJECT *v24; // rcx
  unsigned int v25; // ebx
  PVOID v26; // rdi
  unsigned int v27; // ebx

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  if ( *((_QWORD *)DeviceExtension + 3) )
  {
    v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 2, Tag, File, 1u, 0x20u);
    v7 = v6;
    if ( v6 >= 0 )
    {
      CurrentStackLocation = Tag->Tail.Overlay.CurrentStackLocation;
      HbpTraceEvent(3, "HbPnpDispatch", 599, "PnP dispatch: MinorFunction 0x%x", CurrentStackLocation->MinorFunction);
      switch ( CurrentStackLocation->MinorFunction )
      {
        case 0u:
          return HbPnpStartDevice(DeviceObject, Tag);
        case 1u:
        case 3u:
        case 4u:
        case 5u:
        case 6u:
          goto LABEL_54;
        case 2u:
          qword_140009220 = KeQueryPerformanceCounter(&stru_140009228).QuadPart;
          HbpTraceEvent(3, "HbRecordPhaseTimestamp", 177, "Phase %s reached", "Unload.RemoveDevice");
          HbDriverLastRecordedLifecyclePhase = 3;
          HbPnpDeleteAllEventLogs((__int64)DeviceExtension);
          IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)DeviceExtension + 2, Tag, 0x20u);
          PerformanceCounter = KeQueryPerformanceCounter(&stru_140009288);
          qword_140009280 = PerformanceCounter.QuadPart;
          v10 = qword_1400091D8[3 * HbDriverLastRecordedLifecyclePhase];
          if ( v10 && PerformanceCounter.QuadPart && stru_140009288.QuadPart )
            v11 = 1000 * (PerformanceCounter.QuadPart - v10) / stru_140009288.QuadPart;
          else
            v11 = 0;
          HbpTraceEvent(
            3,
            "HbRecordPhaseTimestamp",
            185,
            "Phase %s reached (%llu ms since %s)",
            "Unload.RemoveLockDrained",
            v11,
            HbDriverPhaseNames[HbDriverLastRecordedLifecyclePhase]);
          HbDriverLastRecordedLifecyclePhase = 7;
          if ( *((_QWORD *)DeviceExtension + 7) )
            IoDeleteSymbolicLink((PUNICODE_STRING)DeviceExtension + 3);
          if ( HbpIsCpuManagementPartition )
            WinHvSetEventLogCompletedNotificationRoutine(0);
          if ( *((_QWORD *)DeviceExtension + 5) )
          {
            IoSetDeviceInterfaceState((PUNICODE_STRING)DeviceExtension + 2, 0);
            RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 2);
            *((_QWORD *)DeviceExtension + 5) = 0;
          }
          if ( HbpIsCpuManagementPartition )
          {
            if ( *((_QWORD *)DeviceExtension + 43) )
            {
              KdDeregisterPowerHandler();
              *((_QWORD *)DeviceExtension + 43) = 0;
            }
            v12 = (void *)*((_QWORD *)DeviceExtension + 25);
            if ( v12 )
            {
              ZwClose(v12);
              *((_QWORD *)DeviceExtension + 25) = 0;
            }
            v13 = (void *)*((_QWORD *)DeviceExtension + 24);
            if ( v13 )
            {
              ZwClose(v13);
              *((_QWORD *)DeviceExtension + 24) = 0;
            }
          }
          if ( *((_DWORD *)DeviceExtension + 46) )
          {
            v14 = (_QWORD **)(DeviceExtension + 168);
            while ( 1 )
            {
              v15 = *v14;
              if ( *v14 == v14 )
                break;
              HvStatspClientBufferUnshare(v15 + 5, 0, v15 + 5);
              for ( i = v15 + 10; (_QWORD *)*i != i; HvStatspClientBufferUnshare(v15 + 5, 0, *i - 8LL) )
                ;
              v17 = (struct _MDL *)v15[12];
              if ( v17 )
              {
                IoFreeMdl(v17);
                v15[12] = 0;
              }
              if ( v15[4] )
              {
                WinHvUnmapStatsPage();
                v15[4] = 0;
              }
              v18 = *v15;
              if ( *(_QWORD **)(*v15 + 8LL) != v15 || (v19 = (_QWORD *)v15[1], (_QWORD *)*v19 != v15) )
                __fastfail(3u);
              *v19 = v18;
              *(_QWORD *)(v18 + 8) = v19;
              ExFreePoolWithTag(v15, 0x74537648u);
            }
            *((_DWORD *)DeviceExtension + 46) = 0;
          }
          if ( HbpIsCpuManagementPartition )
            McGenEventUnregister_EtwUnregister();
          if ( HbEvtpLocalDiagnosticsEventsHandle )
          {
            EtwUnregister(HbEvtpLocalDiagnosticsEventsHandle);
            HbEvtpLocalDiagnosticsEventsHandle = 0;
          }
          if ( byte_140009049 )
          {
            v20 = RegHandle;
            dword_140009050 = 0;
            RegHandle = 0;
            EtwUnregister(v20);
          }
          v21 = KeQueryPerformanceCounter(&stru_1400092A0);
          qword_140009298 = v21.QuadPart;
          v22 = qword_1400091D8[3 * HbDriverLastRecordedLifecyclePhase];
          if ( v22 && v21.QuadPart && stru_1400092A0.QuadPart )
            v23 = 1000 * (v21.QuadPart - v22) / stru_1400092A0.QuadPart;
          else
            v23 = 0;
          HbpTraceEvent(
            3,
            "HbRecordPhaseTimestamp",
            185,
            "Phase %s reached (%llu ms since %s)",
            "Unload.ResourcesFreed",
            v23,
            HbDriverPhaseNames[HbDriverLastRecordedLifecyclePhase]);
          ++Tag->CurrentLocation;
          ++Tag->Tail.Overlay.CurrentStackLocation;
          Tag->IoStatus.Status = 0;
          v24 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 3);
          HbDriverLastRecordedLifecyclePhase = 8;
          v25 = IofCallDriver(v24, Tag);
          IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 3));
          IoDeleteDevice(DeviceObject);
          HbpTraceEvent(2, "HbPnpDispatch", 680, "Device removed");
          return v25;
        case 0x17u:
          IoSetDeviceInterfaceState((PUNICODE_STRING)DeviceExtension + 2, 0);
          RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 2);
          *((_QWORD *)DeviceExtension + 5) = 0;
LABEL_54:
          Tag->IoStatus.Status = 0;
          goto LABEL_55;
        default:
LABEL_55:
          v26 = DeviceObject->DeviceExtension;
          ++Tag->CurrentLocation;
          ++Tag->Tail.Overlay.CurrentStackLocation;
          v27 = IofCallDriver(*((PDEVICE_OBJECT *)v26 + 3), Tag);
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)v26 + 2, Tag, 0x20u);
          result = v27;
          break;
      }
    }
    else
    {
      HbpTraceEvent(1, "HbPnpDispatch", 588, "PnP dispatch: IoAcquireRemoveLock failed with 0x%x", v6);
      Tag->IoStatus.Status = v7;
      IofCompleteRequest(Tag, 0);
      return v7;
    }
  }
  else
  {
    HbpTraceEvent(1, "HbPnpDispatch", 571, "PnP IRP on legacy device object, returning STATUS_INVALID_DEVICE_REQUEST");
    return 3221225488LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400140f0  push    rbp
0x1400140f2  push    r13
0x1400140f4  push    r15
0x1400140f6  sub     rsp, 50h
0x1400140fa  mov     r15, [rcx+40h]
0x1400140fe  mov     rbp, rdx
0x140014101  mov     r13, rcx
0x140014104  cmp     qword ptr [r15+18h], 0
0x140014109  jnz     short loc_140014139
0x14001410b  lea     r9, aPnpIrpOnLegacy; "PnP IRP on legacy device object, return"...
0x140014112  mov     r8d, 23Bh
0x140014118  lea     rdx, aHbpnpdispatch; "HbPnpDispatch"
0x14001411f  mov     ecx, 1
0x140014124  call    HbpTraceEvent
0x140014129  mov     eax, 0C0000010h
0x14001412e  add     rsp, 50h
0x140014132  pop     r15
0x140014134  pop     r13
0x140014136  pop     rbp
0x140014137  retn
0x140014139  mov     [rsp+68h+arg_0], rbx
0x14001413e  lea     r8, File; File
0x140014145  mov     r9d, 1; Line
0x14001414b  mov     [rsp+68h+arg_10], rdi
0x140014153  lea     rcx, [r15+40h]; RemoveLock
0x140014157  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x14001415f  call    cs:__imp_IoAcquireRemoveLockEx
0x140014166  nop     dword ptr [rax+rax+00h]
0x14001416b  mov     ebx, eax
0x14001416d  test    eax, eax
0x14001416f  jns     short loc_1400141AE
0x140014171  lea     r9, aPnpDispatchIoa; "PnP dispatch: IoAcquireRemoveLock faile"...
0x140014178  mov     [rsp+68h+RemlockSize], eax
0x14001417c  mov     r8d, 24Ch
0x140014182  lea     rdx, aHbpnpdispatch; "HbPnpDispatch"
0x140014189  mov     ecx, 1
0x14001418e  call    HbpTraceEvent
0x140014193  xor     edx, edx; PriorityBoost
0x140014195  mov     [rbp+30h], ebx
0x140014198  mov     rcx, rbp; Irp
0x14001419b  call    cs:__imp_IofCompleteRequest
0x1400141a2  nop     dword ptr [rax+rax+00h]
0x1400141a7  mov     eax, ebx
0x1400141a9  jmp     loc_14001465B
0x1400141ae  mov     [rsp+68h+arg_8], rsi
0x1400141b3  mov     [rsp+68h+var_28], r14
0x1400141b8  mov     rbx, [rbp+0B8h]
0x1400141bf  lea     r9, aPnpDispatchMin; "PnP dispatch: MinorFunction 0x%x"
0x1400141c6  mov     r8d, 257h
0x1400141cc  lea     rdx, aHbpnpdispatch; "HbPnpDispatch"
0x1400141d3  mov     ecx, 3
0x1400141d8  movzx   eax, byte ptr [rbx+1]
0x1400141dc  mov     [rsp+68h+RemlockSize], eax
0x1400141e0  call    HbpTraceEvent
0x1400141e5  movzx   eax, byte ptr [rbx+1]
0x1400141e9  cmp     eax, 17h; switch 24 cases
0x1400141ec  ja      def_14001420B; jumptable 000000014001420B default case, cases 7-22
0x1400141f2  lea     rsi, cs:140000000h
0x1400141f9  movzx   eax, ds:(byte_140007214 - 140000000h)[rsi+rax]
0x140014201  mov     ecx, ds:(jpt_14001420B - 140000000h)[rsi+rax*4]
0x140014208  add     rcx, rsi
0x14001420b  jmp     rcx; switch jump
0x140014211  mov     rdx, rbp; jumptable 000000014001420B case 0
0x140014214  mov     rcx, r13
0x140014217  call    HbPnpStartDevice
0x14001421c  jmp     loc_140014651
0x140014221  xor     edx, edx; jumptable 000000014001420B case 23
0x140014223  lea     rcx, [r15+20h]; SymbolicLinkName
0x140014227  call    cs:__imp_IoSetDeviceInterfaceState
0x14001422e  nop     dword ptr [rax+rax+00h]
0x140014233  lea     rcx, [r15+20h]; UnicodeString
0x140014237  call    cs:__imp_RtlFreeUnicodeString
0x14001423e  nop     dword ptr [rax+rax+00h]
0x140014243  xor     r14d, r14d
0x140014246  mov     [r15+28h], r14
0x14001424a  jmp     loc_140014676
0x14001424f  lea     rcx, stru_140009228; jumptable 000000014001420B case 2
0x140014256  call    cs:__imp_KeQueryPerformanceCounter
0x14001425d  nop     dword ptr [rax+rax+00h]
0x140014262  mov     cs:qword_140009220, rax
0x140014269  mov     rax, cs:off_140005018; "Unload.RemoveDevice"
0x140014270  lea     r9, aPhaseSReached; "Phase %s reached"
0x140014277  mov     r8d, 0B1h
0x14001427d  mov     qword ptr [rsp+68h+RemlockSize], rax
0x140014282  lea     rdx, aHbrecordphaset; "HbRecordPhaseTimestamp"
0x140014289  mov     ecx, 3
0x14001428e  call    HbpTraceEvent
0x140014293  mov     rcx, r15
0x140014296  mov     cs:HbDriverLastRecordedLifecyclePhase, 3
0x1400142a0  call    HbPnpDeleteAllEventLogs
0x1400142a5  mov     r8d, 20h ; ' '; RemlockSize
0x1400142ab  lea     rcx, [r15+40h]; RemoveLock
0x1400142af  mov     rdx, rbp; Tag
0x1400142b2  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x1400142b9  nop     dword ptr [rax+rax+00h]
0x1400142be  lea     rcx, stru_140009288; PerformanceFrequency
0x1400142c5  call    cs:__imp_KeQueryPerformanceCounter
0x1400142cc  nop     dword ptr [rax+rax+00h]
0x1400142d1  mov     cs:qword_140009280, rax
0x1400142d8  movsxd  r8, cs:HbDriverLastRecordedLifecyclePhase
0x1400142df  xor     r14d, r14d
0x1400142e2  lea     rcx, [r8+r8*2]
0x1400142e6  mov     rdx, rva qword_1400091D8[rsi+rcx*8]
0x1400142ee  test    rdx, rdx
0x1400142f1  jz      short loc_140014318
0x1400142f3  test    rax, rax
0x1400142f6  jz      short loc_140014318
0x1400142f8  mov     rcx, qword ptr cs:stru_140009288
0x1400142ff  test    rcx, rcx
0x140014302  jz      short loc_140014318
0x140014304  sub     rax, rdx
0x140014307  imul    rax, 3E8h
0x14001430e  cqo
0x140014310  idiv    rcx
0x140014313  mov     rcx, rax
0x140014316  jmp     short loc_14001431B
0x140014318  mov     rcx, r14
0x14001431b  mov     rax, ds:rva HbDriverPhaseNames[rsi+r8*8]
0x140014323  lea     r9, aPhaseSReachedL; "Phase %s reached (%llu ms since %s)"
0x14001432a  mov     [rsp+68h+var_38], rax
0x14001432f  lea     rdx, aHbrecordphaset; "HbRecordPhaseTimestamp"
0x140014336  mov     rax, cs:off_140005038; "Unload.RemoveLockDrained"
0x14001433d  mov     r8d, 0B9h
0x140014343  mov     [rsp+68h+var_40], rcx
0x140014348  mov     ecx, 3
0x14001434d  mov     qword ptr [rsp+68h+RemlockSize], rax
0x140014352  call    HbpTraceEvent
0x140014357  mov     cs:HbDriverLastRecordedLifecyclePhase, 7
0x140014361  cmp     [r15+38h], r14
0x140014365  jz      short loc_140014377
0x140014367  lea     rcx, [r15+30h]; SymbolicLinkName
0x14001436b  call    cs:__imp_IoDeleteSymbolicLink
0x140014372  nop     dword ptr [rax+rax+00h]
0x140014377  cmp     cs:HbpIsCpuManagementPartition, r14b
0x14001437e  jz      short loc_14001438E
0x140014380  xor     ecx, ecx
0x140014382  call    cs:__imp_WinHvSetEventLogCompletedNotificationRoutine
0x140014389  nop     dword ptr [rax+rax+00h]
0x14001438e  cmp     [r15+28h], r14
0x140014392  jz      short loc_1400143BA
0x140014394  xor     edx, edx; Enable
0x140014396  lea     rcx, [r15+20h]; SymbolicLinkName
0x14001439a  call    cs:__imp_IoSetDeviceInterfaceState
0x1400143a1  nop     dword ptr [rax+rax+00h]
0x1400143a6  lea     rcx, [r15+20h]; UnicodeString
0x1400143aa  call    cs:__imp_RtlFreeUnicodeString
0x1400143b1  nop     dword ptr [rax+rax+00h]
0x1400143b6  mov     [r15+28h], r14
0x1400143ba  cmp     cs:HbpIsCpuManagementPartition, r14b
0x1400143c1  jz      short loc_140014420
0x1400143c3  mov     rcx, [r15+158h]
0x1400143ca  test    rcx, rcx
0x1400143cd  jz      short loc_1400143E2
0x1400143cf  call    cs:__imp_KdDeregisterPowerHandler
0x1400143d6  nop     dword ptr [rax+rax+00h]
0x1400143db  mov     [r15+158h], r14
0x1400143e2  mov     rcx, [r15+0C8h]; Handle
0x1400143e9  test    rcx, rcx
0x1400143ec  jz      short loc_140014401
0x1400143ee  call    cs:__imp_ZwClose
0x1400143f5  nop     dword ptr [rax+rax+00h]
0x1400143fa  mov     [r15+0C8h], r14
0x140014401  mov     rcx, [r15+0C0h]; Handle
0x140014408  test    rcx, rcx
0x14001440b  jz      short loc_140014420
0x14001440d  call    cs:__imp_ZwClose
0x140014414  nop     dword ptr [rax+rax+00h]
0x140014419  mov     [r15+0C0h], r14
0x140014420  mov     [rsp+68h+var_20], r12
0x140014425  cmp     [r15+0B8h], r14d
0x14001442c  jz      loc_1400144F2
0x140014432  lea     r12, [r15+0A8h]
0x140014439  nop     dword ptr [rax+00000000h]
0x140014440  mov     rbx, [r12]
0x140014444  cmp     rbx, r12
0x140014447  jz      loc_1400144E4
0x14001444d  lea     r8, [rbx+28h]
0x140014451  xor     edx, edx
0x140014453  lea     rcx, [rbx+28h]
0x140014457  call    HvStatspClientBufferUnshare
0x14001445c  lea     rdi, [rbx+50h]
0x140014460  mov     r8, [rdi]
0x140014463  cmp     r8, rdi
0x140014466  jz      short loc_140014479
0x140014468  add     r8, 0FFFFFFFFFFFFFFF8h
0x14001446c  lea     rcx, [rbx+28h]
0x140014470  xor     edx, edx
0x140014472  call    HvStatspClientBufferUnshare
0x140014477  jmp     short loc_140014460
0x140014479  mov     rcx, [rbx+60h]; Mdl
0x14001447d  test    rcx, rcx
0x140014480  jz      short loc_140014492
0x140014482  call    cs:__imp_IoFreeMdl
0x140014489  nop     dword ptr [rax+rax+00h]
0x14001448e  mov     [rbx+60h], r14
0x140014492  mov     rcx, [rbx+20h]
0x140014496  test    rcx, rcx
0x140014499  jz      short loc_1400144AB
0x14001449b  call    cs:__imp_WinHvUnmapStatsPage
0x1400144a2  nop     dword ptr [rax+rax+00h]
0x1400144a7  mov     [rbx+20h], r14
0x1400144ab  mov     rcx, [rbx]
0x1400144ae  cmp     [rcx+8], rbx
0x1400144b2  jnz     short loc_1400144DD
0x1400144b4  mov     rax, [rbx+8]
0x1400144b8  cmp     [rax], rbx
0x1400144bb  jnz     short loc_1400144DD
0x1400144bd  mov     [rax], rcx
0x1400144c0  mov     edx, 74537648h; Tag
0x1400144c5  mov     [rcx+8], rax
0x1400144c9  mov     rcx, rbx; P
0x1400144cc  call    cs:__imp_ExFreePoolWithTag
0x1400144d3  nop     dword ptr [rax+rax+00h]
0x1400144d8  jmp     loc_140014440
0x1400144dd  mov     ecx, 3
0x1400144e2  int     29h; Win8: RtlFailFast(ecx)
0x1400144e4  mov     [r15+0B8h], r14d
0x1400144eb  lea     rsi, cs:140000000h
0x1400144f2  cmp     cs:HbpIsCpuManagementPartition, r14b
0x1400144f9  jz      short loc_140014500
0x1400144fb  call    McGenEventUnregister_EtwUnregister
0x140014500  mov     rcx, cs:HbEvtpLocalDiagnosticsEventsHandle; RegHandle
0x140014507  test    rcx, rcx
0x14001450a  jz      short loc_14001451F
0x14001450c  call    cs:__imp_EtwUnregister
0x140014513  nop     dword ptr [rax+rax+00h]
0x140014518  mov     cs:HbEvtpLocalDiagnosticsEventsHandle, r14
0x14001451f  cmp     cs:byte_140009049, r14b
0x140014526  jz      short loc_140014549
0x140014528  mov     rcx, cs:RegHandle; RegHandle
0x14001452f  mov     cs:dword_140009050, r14d
0x140014536  mov     cs:RegHandle, r14
0x14001453d  call    cs:__imp_EtwUnregister
0x140014544  nop     dword ptr [rax+rax+00h]
0x140014549  lea     rcx, stru_1400092A0; PerformanceFrequency
0x140014550  call    cs:__imp_KeQueryPerformanceCounter
0x140014557  nop     dword ptr [rax+rax+00h]
0x14001455c  mov     cs:qword_140009298, rax
0x140014563  movsxd  r8, cs:HbDriverLastRecordedLifecyclePhase
0x14001456a  lea     rcx, [r8+r8*2]
0x14001456e  mov     rdx, rva qword_1400091D8[rsi+rcx*8]
0x140014576  test    rdx, rdx
0x140014579  jz      short loc_1400145A0
0x14001457b  test    rax, rax
0x14001457e  jz      short loc_1400145A0
0x140014580  mov     rcx, qword ptr cs:stru_1400092A0
0x140014587  test    rcx, rcx
0x14001458a  jz      short loc_1400145A0
0x14001458c  sub     rax, rdx
0x14001458f  imul    rax, 3E8h
0x140014596  cqo
0x140014598  idiv    rcx
0x14001459b  mov     rcx, rax
0x14001459e  jmp     short loc_1400145A3
0x1400145a0  mov     rcx, r14
0x1400145a3  mov     rax, ds:rva HbDriverPhaseNames[rsi+r8*8]
0x1400145ab  lea     r9, aPhaseSReachedL; "Phase %s reached (%llu ms since %s)"
0x1400145b2  mov     [rsp+68h+var_38], rax
0x1400145b7  lea     rdx, aHbrecordphaset; "HbRecordPhaseTimestamp"
0x1400145be  mov     rax, cs:off_140005040; "Unload.ResourcesFreed"
0x1400145c5  mov     r8d, 0B9h
0x1400145cb  mov     [rsp+68h+var_40], rcx
0x1400145d0  mov     ecx, 3
0x1400145d5  mov     qword ptr [rsp+68h+RemlockSize], rax
0x1400145da  call    HbpTraceEvent
0x1400145df  inc     byte ptr [rbp+43h]
0x1400145e2  mov     rdx, rbp; Irp
0x1400145e5  add     qword ptr [rbp+0B8h], 48h ; 'H'
0x1400145ed  mov     [rbp+30h], r14d
0x1400145f1  mov     rcx, [r15+18h]; DeviceObject
0x1400145f5  mov     cs:HbDriverLastRecordedLifecyclePhase, 8
0x1400145ff  call    cs:__imp_IofCallDriver
0x140014606  nop     dword ptr [rax+rax+00h]
0x14001460b  mov     rcx, [r15+18h]; TargetDevice
0x14001460f  mov     ebx, eax
0x140014611  call    cs:__imp_IoDetachDevice
0x140014618  nop     dword ptr [rax+rax+00h]
0x14001461d  mov     rcx, r13; DeviceObject
0x140014620  call    cs:__imp_IoDeleteDevice
0x140014627  nop     dword ptr [rax+rax+00h]
0x14001462c  lea     r9, aDeviceRemoved; "Device removed"
0x140014633  mov     r8d, 2A8h
0x140014639  lea     rdx, aHbpnpdispatch; "HbPnpDispatch"
0x140014640  mov     ecx, 2
0x140014645  call    HbpTraceEvent
0x14001464a  mov     r12, [rsp+68h+var_20]
0x14001464f  mov     eax, ebx
0x140014651  mov     rsi, [rsp+68h+arg_8]
0x140014656  mov     r14, [rsp+68h+var_28]
0x14001465b  mov     rbx, [rsp+68h+arg_0]
0x140014660  mov     rdi, [rsp+68h+arg_10]
0x140014668  add     rsp, 50h
0x14001466c  pop     r15
0x14001466e  pop     r13
0x140014670  pop     rbp
0x140014671  retn
0x140014673  xor     r14d, r14d; jumptable 000000014001420B cases 1,3-6
0x140014676  mov     [rbp+30h], r14d
0x14001467a  mov     rdi, [r13+40h]; jumptable 000000014001420B default case, cases 7-22
0x14001467e  mov     rdx, rbp; Irp
  ... truncated ...
```
