# DpiMiracastInterfaceChange

- ea: `0x1400825d0`
- end: `0x140082f44`
- name: `DpiMiracastInterfaceChange`
- size: `2420`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140040908`
- `0x14004094c`
- `0x1400825d0`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x14019ce18`
- `0x1402b8634`
- `0x1402b87bc`
- `0x1402b89c4`
- `0x1402ba264`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140082b12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082ba6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082c5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082b81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082ba6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082c5b`
- `ntoskrnl!ExAllocatePool2` at `0x140082696`
- `ntoskrnl!ExAllocatePool2` at `0x14008290b`
- `ntoskrnl!ExAllocatePool2` at `0x140082696`
- `ntoskrnl!ExAllocatePool2` at `0x14008290b`
- `ntoskrnl!KeInitializeEvent` at `0x14008272b`
- `ntoskrnl!KeInitializeEvent` at `0x14008272b`
- `ntoskrnl!KeInitializeDpc` at `0x140082748`
- `ntoskrnl!KeInitializeDpc` at `0x140082748`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140082bfb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140082bfb`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x140082840`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x140082840`
- `ntoskrnl!ObfDereferenceObject` at `0x140082bc9`
- `ntoskrnl!ObfDereferenceObject` at `0x140082be1`
- `ntoskrnl!ObfDereferenceObject` at `0x140082d37`
- `ntoskrnl!ObfDereferenceObject` at `0x140082ed6`
- `ntoskrnl!ObfDereferenceObject` at `0x140082bc9`
- `ntoskrnl!ObfDereferenceObject` at `0x140082be1`
- `ntoskrnl!ObfDereferenceObject` at `0x140082d37`
- `ntoskrnl!ObfDereferenceObject` at `0x140082ed6`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x140082d94`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x140082d94`
- `ntoskrnl!ObfReferenceObject` at `0x140082820`
- `ntoskrnl!ObfReferenceObject` at `0x140082820`
- `ntoskrnl!ZwClose` at `0x140082831`
- `ntoskrnl!ZwClose` at `0x140082831`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008296d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140082a95`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008296d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140082a95`
- `ntoskrnl!IoCreateNotificationEvent` at `0x1400827e0`
- `ntoskrnl!IoCreateNotificationEvent` at `0x1400827e0`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400827a3`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400827a3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140082d77`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140082d77`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14008277e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14008277e`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140082d03`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140082d03`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140082c4a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140082e50`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140082c4a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140082e50`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140082c18`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140082e17`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140082c18`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140082e17`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x140082ddb`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x140082ddb`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140082ec2`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140082ec2`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140082e8c`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140082e8c`
- `watchdog!WdLogSingleEntry1` at `0x1400826b4`
- `watchdog!WdLogSingleEntry1` at `0x1400827be`
- `watchdog!WdLogSingleEntry1` at `0x140082802`
- `watchdog!WdLogSingleEntry1` at `0x140082a66`
- `watchdog!WdLogSingleEntry1` at `0x140082ad7`
- `watchdog!WdLogSingleEntry1` at `0x140082c80`
- `watchdog!WdLogSingleEntry1` at `0x140082d18`
- `watchdog!WdLogSingleEntry1` at `0x140082da9`
- `watchdog!WdLogSingleEntry1` at `0x140082df0`
- `watchdog!WdLogSingleEntry1` at `0x140082ea1`
- `watchdog!WdLogSingleEntry1` at `0x140082f0b`
- `watchdog!WdLogSingleEntry1` at `0x1400826b4`
- `watchdog!WdLogSingleEntry1` at `0x1400827be`
- `watchdog!WdLogSingleEntry1` at `0x140082802`
- `watchdog!WdLogSingleEntry1` at `0x140082a66`
- `watchdog!WdLogSingleEntry1` at `0x140082ad7`
- `watchdog!WdLogSingleEntry1` at `0x140082c80`
- `watchdog!WdLogSingleEntry1` at `0x140082d18`
- `watchdog!WdLogSingleEntry1` at `0x140082da9`
- `watchdog!WdLogSingleEntry1` at `0x140082df0`
- `watchdog!WdLogSingleEntry1` at `0x140082ea1`
- `watchdog!WdLogSingleEntry1` at `0x140082f0b`

## pseudocode

```c
__int64 __fastcall DpiMiracastInterfaceChange(char *NotificationStructure, PVOID Context)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  void *Pool2; // rax
  __int64 v8; // rdi
  __int64 result; // rax
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // r13
  char v11; // r12
  char v12; // r15
  const UNICODE_STRING *v13; // rdx
  NTSTATUS DeviceObjectPointer; // eax
  PKEVENT v15; // rax
  unsigned int v16; // ebx
  int DevicePropertyDataString; // eax
  unsigned int v18; // r15d
  unsigned int v19; // r12d
  unsigned __int64 v20; // rdx
  char *v21; // rax
  char *v22; // r9
  unsigned __int16 Length; // ax
  unsigned __int16 v24; // cx
  int DeviceInstanceId; // eax
  int v26; // eax
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  __int64 v33; // rcx
  _QWORD *v34; // rax
  __int128 v35; // xmm1
  void *v36; // rcx
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  NTSTATUS v43; // eax
  __int64 v44; // rbx
  NTSTATUS LocallyUniqueId; // eax
  NTSTATUS v46; // eax
  __int64 *v47; // rax
  NTSTATUS v48; // eax
  char v49; // [rsp+41h] [rbp-BFh]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  void *EventHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v53; // [rsp+78h] [rbp-88h]
  _OWORD v54[9]; // [rsp+90h] [rbp-70h] BYREF

  memset(v54, 0, 0x88u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( NotificationStructure )
  {
    v3 = *(_QWORD *)(NotificationStructure + 20) - *(_QWORD *)&GUID_DEVINTERFACE_UMDF_MIRACAST_DIVICE_ARRIVAL.Data1;
    if ( !v3 )
      v3 = *(_QWORD *)(NotificationStructure + 28) - *(_QWORD *)GUID_DEVINTERFACE_UMDF_MIRACAST_DIVICE_ARRIVAL.Data4;
    if ( !v3 )
    {
      v4 = *((_QWORD *)NotificationStructure + 5);
      if ( v4 )
      {
        v5 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_DEVICE_INTERFACE_ARRIVAL.Data1;
        if ( !v5 )
          v5 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_DEVICE_INTERFACE_ARRIVAL.Data4;
        if ( v5 )
          return 0;
        EventHandle = 0;
        v53 = 0;
        v6 = *(unsigned __int16 *)(v4 + 2) + 792LL;
        *(_DWORD *)&DestinationString.Length = 0;
        Pool2 = (void *)ExAllocatePool2(64, v6, 1953656900);
        v8 = (__int64)Pool2;
        if ( !Pool2 )
        {
          WdLogSingleEntry1(6, -1073741801);
          WdLogGlobalForLineNumber = 2466;
          return 0;
        }
        v49 = 0;
        DeviceAttachmentBaseRef = 0;
        v11 = 0;
        memset(Pool2, 0, 0x318u);
        *(_DWORD *)(v8 + 16) = 1953656900;
        *(_DWORD *)(v8 + 20) = 14;
        *(_DWORD *)(v8 + 420) = -1;
        v12 = 1;
        *(_DWORD *)(v8 + 456) = -1;
        *(_QWORD *)(v8 + 24) = 1;
        *(_QWORD *)(v8 + 88) = 0;
        *(_DWORD *)(v8 + 32) = 1;
        *(_QWORD *)(v8 + 40) = 0;
        *(_DWORD *)(v8 + 48) = 0;
        KeInitializeEvent((PRKEVENT)(v8 + 56), SynchronizationEvent, 0);
        KeInitializeDpc((PRKDPC)(v8 + 520), DpiMiracastChunkInfoCallbackDpc, (PVOID)v8);
        v13 = (const UNICODE_STRING *)*((_QWORD *)NotificationStructure + 5);
        *(_WORD *)(v8 + 144) = 0;
        *(_WORD *)(v8 + 146) = v13->MaximumLength;
        *(_QWORD *)(v8 + 152) = v8 + 792;
        RtlCopyUnicodeString((PUNICODE_STRING)(v8 + 144), v13);
        DeviceObjectPointer = IoGetDeviceObjectPointer(
                                (PUNICODE_STRING)(v8 + 144),
                                0x80000000,
                                (PFILE_OBJECT *)(v8 + 176),
                                (PDEVICE_OBJECT *)(v8 + 184));
        if ( DeviceObjectPointer < 0 )
        {
          v12 = 0;
          WdLogSingleEntry1(2, DeviceObjectPointer);
          WdLogGlobalForLineNumber = 2525;
LABEL_38:
          v27 = *(void **)(v8 + 336);
          if ( v27 )
          {
            ExFreePoolWithTag(v27, 0);
            *(_QWORD *)(v8 + 336) = 0;
          }
          v28 = *(void **)(v8 + 344);
          if ( v28 )
          {
            ExFreePoolWithTag(v28, 0);
            *(_QWORD *)(v8 + 344) = 0;
          }
          v29 = *(void **)(v8 + 352);
          if ( v29 )
          {
            ExFreePoolWithTag(v29, 0);
            *(_QWORD *)(v8 + 352) = 0;
          }
          v30 = *(void **)(v8 + 360);
          if ( v30 )
          {
            ExFreePoolWithTag(v30, 0);
            *(_QWORD *)(v8 + 360) = 0;
          }
          v31 = *(void **)(v8 + 368);
          if ( v31 )
          {
            ExFreePoolWithTag(v31, 0);
            *(_QWORD *)(v8 + 368) = 0;
          }
          if ( v12 )
            ObfDereferenceObject(*(PVOID *)(v8 + 176));
          v32 = *(void **)(v8 + 464);
          if ( v32 )
            ObfDereferenceObject(v32);
          if ( *(_QWORD *)(v8 + 136) )
            RtlFreeUnicodeString((PUNICODE_STRING)(v8 + 128));
          if ( !v11 )
            goto LABEL_58;
          KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
          v33 = *(_QWORD *)v8;
          if ( *(_QWORD *)(*(_QWORD *)v8 + 8LL) == v8 )
          {
            v34 = *(_QWORD **)(v8 + 8);
            if ( *v34 == v8 )
            {
              *v34 = v33;
              *(_QWORD *)(v33 + 8) = v34;
              KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_58:
              ExFreePoolWithTag((PVOID)v8, 0);
              v11 = v49;
LABEL_75:
              if ( DeviceAttachmentBaseRef )
                ObfDereferenceObject(DeviceAttachmentBaseRef);
              if ( v11 )
                ReleaseMiniportListMutex();
              return 0;
            }
          }
LABEL_79:
          __fastfail(3u);
        }
        v15 = IoCreateNotificationEvent(0, &EventHandle);
        *(_QWORD *)(v8 + 464) = v15;
        if ( !v15 )
        {
          WdLogSingleEntry1(2, -1073741801);
          WdLogGlobalForLineNumber = 2548;
          goto LABEL_38;
        }
        ObfReferenceObject(v15);
        ZwClose(EventHandle);
        DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(*(PDEVICE_OBJECT *)(v8 + 184));
        if ( (int)DpiGetDevicePropertyDataString(
                    DeviceAttachmentBaseRef,
                    (DEVPROPKEY *)&DEVPKEY_DeviceContainer_Manufacturer,
                    v8 + 336,
                    (__int64)&DestinationString) >= 0
          || (int)DpiGetDevicePropertyString(
                    DeviceAttachmentBaseRef,
                    DevicePropertyManufacturer,
                    (__int64)&DestinationString) >= 0 )
        {
          v16 = *(_DWORD *)&DestinationString.Length;
        }
        else
        {
          v16 = 0;
        }
        DevicePropertyDataString = DpiGetDevicePropertyDataString(
                                     DeviceAttachmentBaseRef,
                                     (DEVPROPKEY *)&DEVPKEY_DeviceContainer_ModelName,
                                     v8 + 344,
                                     (__int64)&DestinationString);
        v18 = *(_DWORD *)&DestinationString.Length;
        if ( DevicePropertyDataString < 0 )
          v18 = 0;
        v19 = v16 + v18;
        if ( v16 + v18 )
        {
          v20 = v19 + 4LL;
          if ( v20 < 0xFFFF )
          {
            v21 = (char *)ExAllocatePool2(64, v20, 1953656900);
            *(_QWORD *)(v8 + 352) = v21;
            v22 = v21;
            if ( v21 )
            {
              DestinationString = 0;
              if ( v19 == v18 )
              {
                Length = DestinationString.Length;
                v24 = 0;
              }
              else
              {
                memmove(v21, *(const void **)(v8 + 336), v16);
                *(_WORD *)(*(_QWORD *)(v8 + 352) + 2 * ((unsigned __int64)v16 >> 1)) = 0;
                RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v8 + 352));
                *(_WORD *)(*(_QWORD *)(v8 + 352) + 2 * ((unsigned __int64)DestinationString.Length >> 1)) = 32;
                v22 = *(char **)(v8 + 352);
                Length = DestinationString.Length + 2;
                DestinationString.Length = Length;
                v24 = Length;
              }
              DestinationString.MaximumLength = v19 + 4;
              if ( v18 )
              {
                memmove(&v22[2 * ((unsigned __int64)v24 >> 1)], *(const void **)(v8 + 344), v18);
                Length = DestinationString.Length;
              }
              *(_WORD *)(*(_QWORD *)(v8 + 352) + 2 * ((unsigned __int64)(v18 + Length) >> 1)) = 0;
            }
          }
        }
        DpiGetDevicePropertyDataString(
          DeviceAttachmentBaseRef,
          (DEVPROPKEY *)&DEVPKEY_DeviceContainer_ModelNumber,
          v8 + 360,
          (__int64)&DestinationString);
        DpiGetDevicePropertyDataString(
          DeviceAttachmentBaseRef,
          (DEVPROPKEY *)&DEVPKEY_Device_FriendlyName,
          v8 + 368,
          (__int64)&DestinationString);
        *(_QWORD *)&DestinationString.Length = 0;
        DeviceInstanceId = DpiGetDeviceInstanceId(DeviceAttachmentBaseRef);
        if ( DeviceInstanceId < 0 )
        {
          WdLogSingleEntry1(2, DeviceInstanceId);
          v11 = 0;
          v12 = 1;
          WdLogGlobalForLineNumber = 2731;
          goto LABEL_38;
        }
        RtlInitUnicodeString((PUNICODE_STRING)(v8 + 160), *(PCWSTR *)&DestinationString.Length);
        v26 = DpiMiracastSendSyncUserModeRequest(v8, 2295808);
        if ( v26 >= 0 )
        {
          if ( *((_QWORD *)&v53 + 1) >= 0x88u )
          {
            v35 = v54[1];
            v36 = (void *)DWORD1(v54[8]);
            *(_OWORD *)(v8 + 204) = v54[0];
            v37 = v54[2];
            *(_OWORD *)(v8 + 220) = v35;
            v38 = v54[3];
            *(_OWORD *)(v8 + 236) = v37;
            v39 = v54[4];
            *(_OWORD *)(v8 + 252) = v38;
            v40 = v54[5];
            *(_OWORD *)(v8 + 268) = v39;
            v41 = v54[6];
            *(_OWORD *)(v8 + 284) = v40;
            v42 = v54[7];
            *(_OWORD *)(v8 + 300) = v41;
            *(_OWORD *)(v8 + 316) = v42;
            *(_WORD *)(v8 + 332) = 0;
            v43 = PsLookupProcessByProcessId(v36, (PEPROCESS *)(v8 + 104));
            if ( v43 >= 0 )
            {
              ObfDereferenceObject(*(PVOID *)(v8 + 104));
              AcquireMiniportListMutex();
              v44 = qword_140163300;
              v12 = 1;
              v11 = 1;
              v49 = 1;
              while ( (__int64 *)v44 != &qword_140163300 )
              {
                if ( !RtlCompareUnicodeString(
                        *((PCUNICODE_STRING *)NotificationStructure + 5),
                        (PCUNICODE_STRING)(v44 + 144),
                        0) )
                  goto LABEL_36;
                v44 = *(_QWORD *)v44;
              }
              LocallyUniqueId = ZwAllocateLocallyUniqueId((PLUID)(v8 + 96));
              if ( LocallyUniqueId >= 0 )
              {
                v46 = IoRegisterDeviceInterface(
                        DeviceAttachmentBaseRef,
                        &GUID_DEVINTERFACE_MIRACAST_DISPLAY_ARRIVAL,
                        0,
                        (PUNICODE_STRING)(v8 + 128));
                if ( v46 >= 0 )
                {
                  KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
                  v47 = (__int64 *)qword_140163308;
                  if ( *(__int64 **)qword_140163308 != &qword_140163300 )
                    goto LABEL_79;
                  *(_QWORD *)v8 = &qword_140163300;
                  *(_QWORD *)(v8 + 8) = v47;
                  *v47 = v8;
                  qword_140163308 = v8;
                  KeReleaseInStackQueuedSpinLock(&LockHandle);
                  v48 = IoRegisterPlugPlayNotification(
                          EventCategoryTargetDeviceChange,
                          0,
                          *(PVOID *)(v8 + 176),
                          (PDRIVER_OBJECT)g_pDriverObject,
                          DpiMiracastTargetDeviceChange,
                          (PVOID)v8,
                          (PVOID *)(v8 + 400));
                  if ( v48 >= 0 )
                  {
                    IoSetDeviceInterfaceState((PUNICODE_STRING)(v8 + 128), 1u);
                    goto LABEL_75;
                  }
                  WdLogSingleEntry1(2, v48);
                  WdLogGlobalForLineNumber = 2909;
                  goto LABEL_37;
                }
                WdLogSingleEntry1(2, v46);
                WdLogGlobalForLineNumber = 2870;
              }
              else
              {
                WdLogSingleEntry1(2, LocallyUniqueId);
                WdLogGlobalForLineNumber = 2851;
              }
LABEL_36:
              v11 = 0;
LABEL_37:
              DxgkFreeUnicodeString(v8 + 160);
              goto LABEL_38;
            }
            WdLogSingleEntry1(2, v43);
            WdLogGlobalForLineNumber = 2798;
          }
          else
          {
            WdLogSingleEntry1(2, -1073741811);
            WdLogGlobalForLineNumber = 2769;
          }
        }
        else
        {
          WdLogSingleEntry1(2, v26);
          WdLogGlobalForLineNumber = 2759;
        }
        v12 = 1;
        goto LABEL_36;
      }
    }
  }
  WdLogSingleEntry1(2, -1073741585);
  result = 3221225711LL;
  WdLogGlobalForLineNumber = 2427;
  return result;
}

```

## disassembly

```asm
0x1400825d0  push    rbp
0x1400825d2  push    rbx
0x1400825d3  push    rsi
0x1400825d4  push    rdi
0x1400825d5  push    r12
0x1400825d7  push    r13
0x1400825d9  push    r14
0x1400825db  push    r15
0x1400825dd  lea     rbp, [rsp-38h]
0x1400825e2  sub     rsp, 138h
0x1400825e9  mov     rax, cs:__security_cookie
0x1400825f0  xor     rax, rsp
0x1400825f3  mov     [rbp+70h+var_50], rax
0x1400825f7  mov     r14, rcx
0x1400825fa  xor     edx, edx; Val
0x1400825fc  lea     rcx, [rbp+70h+var_E0]; void *
0x140082600  mov     r8d, 88h; Size
0x140082606  call    memset
0x14008260b  xor     eax, eax
0x14008260d  xor     esi, esi
0x14008260f  mov     qword ptr [rsp+170h+LockHandle.OldIrql], rax
0x140082614  xorps   xmm0, xmm0
0x140082617  movups  xmmword ptr [rsp+170h+LockHandle.LockQueue.Next], xmm0
0x14008261c  test    r14, r14
0x14008261f  jz      loc_140082EFC
0x140082625  mov     rax, [r14+14h]
0x140082629  sub     rax, qword ptr cs:GUID_DEVINTERFACE_UMDF_MIRACAST_DIVICE_ARRIVAL.Data1
0x140082630  jnz     short loc_14008263D
0x140082632  mov     rax, [r14+1Ch]
0x140082636  sub     rax, qword ptr cs:GUID_DEVINTERFACE_UMDF_MIRACAST_DIVICE_ARRIVAL.Data4
0x14008263d  test    rax, rax
0x140082640  jnz     loc_140082EFC
0x140082646  mov     rcx, [r14+28h]
0x14008264a  test    rcx, rcx
0x14008264d  jz      loc_140082EFC
0x140082653  mov     rax, [r14+4]
0x140082657  sub     rax, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data1
0x14008265e  jnz     short loc_14008266B
0x140082660  mov     rax, [r14+0Ch]
0x140082664  sub     rax, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data4
0x14008266b  test    rax, rax
0x14008266e  jnz     short loc_1400826CA
0x140082670  mov     [rsp+170h+EventHandle], rsi
0x140082675  mov     ebx, 318h
0x14008267a  movups  [rsp+170h+var_F8], xmm0
0x14008267f  movzx   edx, word ptr [rcx+2]
0x140082683  mov     r15d, 74727044h
0x140082689  add     rdx, rbx
0x14008268c  mov     dword ptr [rsp+170h+DestinationString.Length], esi
0x140082690  mov     r8d, r15d
0x140082693  lea     ecx, [rax+40h]
0x140082696  call    cs:__imp_ExAllocatePool2
0x14008269d  nop     dword ptr [rax+rax+00h]
0x1400826a2  mov     rdi, rax
0x1400826a5  test    rax, rax
0x1400826a8  jnz     short loc_1400826D1
0x1400826aa  mov     rdx, 0FFFFFFFFC0000017h
0x1400826b1  lea     ecx, [rax+6]
0x1400826b4  call    cs:__imp_WdLogSingleEntry1
0x1400826bb  nop     dword ptr [rax+rax+00h]
0x1400826c0  mov     cs:WdLogGlobalForLineNumber, 9A2h
0x1400826ca  xor     eax, eax
0x1400826cc  jmp     loc_140082F23
0x1400826d1  mov     r8, rbx; Size
0x1400826d4  mov     [rsp+170h+var_12F], sil
0x1400826d9  xor     edx, edx; Val
0x1400826db  mov     [rsp+170h+var_130], sil
0x1400826e0  mov     rcx, rdi; void *
0x1400826e3  mov     r13, rsi
0x1400826e6  mov     r12b, sil
0x1400826e9  call    memset
0x1400826ee  mov     [rdi+10h], r15d
0x1400826f2  lea     rcx, [rdi+38h]; Event
0x1400826f6  mov     dword ptr [rdi+14h], 0Eh
0x1400826fd  or      eax, 0FFFFFFFFh
0x140082700  mov     [rdi+1A4h], eax
0x140082706  mov     r15d, 1
0x14008270c  mov     [rdi+1C8h], eax
0x140082712  mov     edx, r15d; Type
0x140082715  mov     [rdi+18h], r15
0x140082719  xor     r8d, r8d; State
0x14008271c  mov     [rdi+58h], rsi
0x140082720  mov     [rdi+20h], r15d
0x140082724  mov     [rdi+28h], rsi
0x140082728  mov     [rdi+30h], esi
0x14008272b  call    cs:__imp_KeInitializeEvent
0x140082732  nop     dword ptr [rax+rax+00h]
0x140082737  lea     rcx, [rdi+208h]; Dpc
0x14008273e  mov     r8, rdi; DeferredContext
0x140082741  lea     rdx, DpiMiracastChunkInfoCallbackDpc; DeferredRoutine
0x140082748  call    cs:__imp_KeInitializeDpc
0x14008274f  nop     dword ptr [rax+rax+00h]
0x140082754  mov     rdx, [r14+28h]; SourceString
0x140082758  lea     rbx, [rdi+90h]
0x14008275f  mov     [rbx], si
0x140082762  mov     rcx, rbx; DestinationString
0x140082765  movzx   eax, word ptr [rdx+2]
0x140082769  mov     [rdi+92h], ax
0x140082770  lea     rax, [rdi+318h]
0x140082777  mov     [rdi+98h], rax
0x14008277e  call    cs:__imp_RtlCopyUnicodeString
0x140082785  nop     dword ptr [rax+rax+00h]
0x14008278a  lea     rsi, [rdi+0B8h]
0x140082791  mov     edx, 80000000h; DesiredAccess
0x140082796  mov     r9, rsi; DeviceObject
0x140082799  lea     r8, [rdi+0B0h]; FileObject
0x1400827a0  mov     rcx, rbx; ObjectName
0x1400827a3  call    cs:__imp_IoGetDeviceObjectPointer
0x1400827aa  nop     dword ptr [rax+rax+00h]
0x1400827af  test    eax, eax
0x1400827b1  jns     short loc_1400827D9
0x1400827b3  xor     r15b, r15b
0x1400827b6  movsxd  rdx, eax
0x1400827b9  mov     ecx, 2
0x1400827be  call    cs:__imp_WdLogSingleEntry1
0x1400827c5  nop     dword ptr [rax+rax+00h]
0x1400827ca  mov     cs:WdLogGlobalForLineNumber, 9DDh
0x1400827d4  jmp     loc_140082B04
0x1400827d9  lea     rdx, [rsp+170h+EventHandle]; EventHandle
0x1400827de  xor     ecx, ecx; EventName
0x1400827e0  call    cs:__imp_IoCreateNotificationEvent
0x1400827e7  nop     dword ptr [rax+rax+00h]
0x1400827ec  mov     [rdi+1D0h], rax
0x1400827f3  test    rax, rax
0x1400827f6  jnz     short loc_14008281D
0x1400827f8  mov     rdx, 0FFFFFFFFC0000017h
0x1400827ff  lea     ecx, [rax+2]
0x140082802  call    cs:__imp_WdLogSingleEntry1
0x140082809  nop     dword ptr [rax+rax+00h]
0x14008280e  mov     cs:WdLogGlobalForLineNumber, 9F4h
0x140082818  jmp     loc_140082B04
0x14008281d  mov     rcx, rax; Object
0x140082820  call    cs:__imp_ObfReferenceObject
0x140082827  nop     dword ptr [rax+rax+00h]
0x14008282c  mov     rcx, [rsp+170h+EventHandle]; Handle
0x140082831  call    cs:__imp_ZwClose
0x140082838  nop     dword ptr [rax+rax+00h]
0x14008283d  mov     rcx, [rsi]; DeviceObject
0x140082840  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x140082847  nop     dword ptr [rax+rax+00h]
0x14008284c  mov     esi, 100h
0x140082851  lea     rbx, [rdi+150h]
0x140082858  mov     r13, rax
0x14008285b  lea     rdx, DEVPKEY_DeviceContainer_Manufacturer; PropertyKey
0x140082862  lea     rax, [rsp+170h+DestinationString]
0x140082867  mov     r9d, esi
0x14008286a  mov     [rsp+170h+Context], rax; __int64
0x14008286f  mov     rcx, r13; Pdo
0x140082872  mov     [rsp+170h+CallbackRoutine], rbx; __int64
0x140082877  call    DpiGetDevicePropertyDataString
0x14008287c  test    eax, eax
0x14008287e  jns     short loc_1400828A5
0x140082880  lea     rax, [rsp+170h+DestinationString]
0x140082885  mov     r9, rbx
0x140082888  mov     r8, r15
0x14008288b  mov     [rsp+170h+CallbackRoutine], rax; __int64
0x140082890  mov     edx, 8; DeviceProperty
0x140082895  mov     rcx, r13; DeviceObject
0x140082898  call    DpiGetDevicePropertyString
0x14008289d  test    eax, eax
0x14008289f  jns     short loc_1400828A5
0x1400828a1  xor     ebx, ebx
0x1400828a3  jmp     short loc_1400828A9
0x1400828a5  mov     ebx, dword ptr [rsp+170h+DestinationString.Length]
0x1400828a9  lea     rcx, [rsp+170h+DestinationString]
0x1400828ae  mov     r9, rsi
0x1400828b1  mov     [rsp+170h+Context], rcx; __int64
0x1400828b6  lea     rax, [rdi+158h]
0x1400828bd  mov     rcx, r13; Pdo
0x1400828c0  mov     [rsp+170h+CallbackRoutine], rax; __int64
0x1400828c5  lea     rdx, DEVPKEY_DeviceContainer_ModelName; PropertyKey
0x1400828cc  call    DpiGetDevicePropertyDataString
0x1400828d1  mov     r15d, dword ptr [rsp+170h+DestinationString.Length]
0x1400828d6  xor     edx, edx
0x1400828d8  test    eax, eax
0x1400828da  cmovs   r15d, edx
0x1400828de  lea     esi, [rdx+2]
0x1400828e1  lea     r12d, [rbx+r15]
0x1400828e5  test    r12d, r12d
0x1400828e8  jz      loc_1400829F2
0x1400828ee  mov     edx, r12d
0x1400828f1  add     rdx, 4
0x1400828f5  cmp     rdx, 0FFFFh
0x1400828fc  jnb     loc_1400829F2
0x140082902  lea     ecx, [rsi+3Eh]
0x140082905  mov     r8d, 74727044h
0x14008290b  call    cs:__imp_ExAllocatePool2
0x140082912  nop     dword ptr [rax+rax+00h]
0x140082917  mov     [rdi+160h], rax
0x14008291e  mov     r9, rax
0x140082921  test    rax, rax
0x140082924  jz      loc_1400829F2
0x14008292a  xorps   xmm0, xmm0
0x14008292d  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x140082932  cmp     r12d, r15d
0x140082935  jz      short loc_1400829A7
0x140082937  mov     rdx, [rdi+150h]; Src
0x14008293e  mov     ecx, r12d
0x140082941  sub     ecx, r15d
0x140082944  mov     ebx, ecx
0x140082946  mov     r8d, ecx; Size
0x140082949  mov     rcx, rax; void *
0x14008294c  call    memmove
0x140082951  mov     rcx, [rdi+160h]
0x140082958  xor     eax, eax
0x14008295a  shr     rbx, 1
0x14008295d  mov     [rcx+rbx*2], ax
0x140082961  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x140082966  mov     rdx, [rdi+160h]; SourceString
0x14008296d  call    cs:__imp_RtlInitUnicodeString
0x140082974  nop     dword ptr [rax+rax+00h]
0x140082979  movzx   ecx, [rsp+170h+DestinationString.Length]
0x14008297e  mov     rax, [rdi+160h]
0x140082985  shr     rcx, 1
0x140082988  mov     word ptr [rax+rcx*2], 20h ; ' '
0x14008298e  movzx   eax, [rsp+170h+DestinationString.Length]
0x140082993  mov     r9, [rdi+160h]
0x14008299a  add     ax, si
0x14008299d  mov     [rsp+170h+DestinationString.Length], ax
0x1400829a2  movzx   ecx, ax
0x1400829a5  jmp     short loc_1400829AE
0x1400829a7  movzx   eax, [rsp+170h+DestinationString.Length]
0x1400829ac  xor     ecx, ecx
0x1400829ae  add     r12w, 4
0x1400829b3  mov     [rsp+170h+DestinationString.MaximumLength], r12w
0x1400829b9  test    r15d, r15d
0x1400829bc  jz      short loc_1400829DC
0x1400829be  mov     rdx, [rdi+158h]; Src
0x1400829c5  movzx   eax, cx
0x1400829c8  shr     rax, 1
0x1400829cb  mov     r8d, r15d; Size
0x1400829ce  lea     rcx, [r9+rax*2]; void *
0x1400829d2  call    memmove
0x1400829d7  movzx   eax, [rsp+170h+DestinationString.Length]
0x1400829dc  mov     rcx, [rdi+160h]
0x1400829e3  movzx   edx, ax
0x1400829e6  add     edx, r15d
0x1400829e9  shr     rdx, 1
0x1400829ec  xor     eax, eax
0x1400829ee  mov     [rcx+rdx*2], ax
0x1400829f2  lea     rcx, [rsp+170h+DestinationString]
0x1400829f7  mov     ebx, 100h
0x1400829fc  mov     [rsp+170h+Context], rcx; __int64
0x140082a01  lea     rax, [rdi+168h]
0x140082a08  mov     rcx, r13; Pdo
0x140082a0b  mov     [rsp+170h+CallbackRoutine], rax; __int64
0x140082a10  mov     r9d, ebx
0x140082a13  lea     rdx, DEVPKEY_DeviceContainer_ModelNumber; PropertyKey
0x140082a1a  call    DpiGetDevicePropertyDataString
0x140082a1f  lea     rcx, [rsp+170h+DestinationString]
0x140082a24  mov     r9d, ebx
0x140082a27  mov     [rsp+170h+Context], rcx; __int64
0x140082a2c  lea     rax, [rdi+170h]
0x140082a33  mov     rcx, r13; Pdo
0x140082a36  mov     [rsp+170h+CallbackRoutine], rax; __int64
0x140082a3b  lea     rdx, DEVPKEY_Device_FriendlyName; PropertyKey
0x140082a42  call    DpiGetDevicePropertyDataString
0x140082a47  lea     rdx, [rsp+170h+DestinationString]
0x140082a4c  mov     qword ptr [rsp+170h+DestinationString.Length], 0
0x140082a55  mov     rcx, r13; DeviceObject
0x140082a58  call    DpiGetDeviceInstanceId
0x140082a5d  test    eax, eax
0x140082a5f  jns     short loc_140082A89
0x140082a61  movsxd  rdx, eax
0x140082a64  mov     ecx, esi
0x140082a66  call    cs:__imp_WdLogSingleEntry1
0x140082a6d  nop     dword ptr [rax+rax+00h]
0x140082a72  mov     r12b, [rsp+170h+var_130]
0x140082a77  mov     r15d, 1
0x140082a7d  mov     cs:WdLogGlobalForLineNumber, 0AABh
0x140082a87  jmp     short loc_140082B04
0x140082a89  mov     rdx, qword ptr [rsp+170h+DestinationString.Length]; SourceString
0x140082a8e  lea     rcx, [rdi+0A0h]; DestinationString
0x140082a95  call    cs:__imp_RtlInitUnicodeString
0x140082a9c  nop     dword ptr [rax+rax+00h]
0x140082aa1  lea     rax, [rsp+170h+var_F8]
0x140082aa6  mov     ebx, 88h
0x140082aab  mov     [rsp+170h+NotificationEntry], rax
0x140082ab0  mov     edx, 230800h
0x140082ab5  lea     rax, [rbp+70h+var_E0]
0x140082ab9  mov     dword ptr [rsp+170h+Context], ebx
0x140082abd  mov     rcx, rdi
0x140082ac0  mov     [rsp+170h+CallbackRoutine], rax
0x140082ac5  call    DpiMiracastSendSyncUserModeRequest
0x140082aca  test    eax, eax
0x140082acc  jns     loc_140082C71
0x140082ad2  movsxd  rdx, eax
0x140082ad5  mov     ecx, esi
0x140082ad7  call    cs:__imp_WdLogSingleEntry1
0x140082ade  nop     dword ptr [rax+rax+00h]
0x140082ae3  mov     cs:WdLogGlobalForLineNumber, 0AC7h
0x140082aed  mov     r15d, 1
0x140082af3  mov     r12b, [rsp+170h+var_130]
0x140082af8  lea     rcx, [rdi+0A0h]
0x140082aff  call    DxgkFreeUnicodeString
0x140082b04  mov     rcx, [rdi+150h]; P
0x140082b0b  test    rcx, rcx
0x140082b0e  jz      short loc_140082B29
0x140082b10  xor     edx, edx; Tag
0x140082b12  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
