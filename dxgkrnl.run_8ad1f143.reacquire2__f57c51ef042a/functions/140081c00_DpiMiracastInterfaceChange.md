# DpiMiracastInterfaceChange

- ea: `0x140081c00`
- end: `0x140082574`
- name: `DpiMiracastInterfaceChange`
- size: `2420`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400406a8`
- `0x1400406ec`
- `0x140081c00`
- `0x1400a0100`
- `0x1400a0240`
- `0x1400a0540`
- `0x140198e18`
- `0x1402b1c84`
- `0x1402b1e0c`
- `0x1402b2014`
- `0x1402b38b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140082142`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082167`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008218c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400821b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400821d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008228b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082142`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082167`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008218c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400821b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400821d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008228b`
- `ntoskrnl!ExAllocatePool2` at `0x140081cc6`
- `ntoskrnl!ExAllocatePool2` at `0x140081f3b`
- `ntoskrnl!ExAllocatePool2` at `0x140081cc6`
- `ntoskrnl!ExAllocatePool2` at `0x140081f3b`
- `ntoskrnl!KeInitializeEvent` at `0x140081d5b`
- `ntoskrnl!KeInitializeEvent` at `0x140081d5b`
- `ntoskrnl!KeInitializeDpc` at `0x140081d78`
- `ntoskrnl!KeInitializeDpc` at `0x140081d78`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14008222b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14008222b`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x140081e70`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x140081e70`
- `ntoskrnl!ObfDereferenceObject` at `0x1400821f9`
- `ntoskrnl!ObfDereferenceObject` at `0x140082211`
- `ntoskrnl!ObfDereferenceObject` at `0x140082367`
- `ntoskrnl!ObfDereferenceObject` at `0x140082506`
- `ntoskrnl!ObfDereferenceObject` at `0x1400821f9`
- `ntoskrnl!ObfDereferenceObject` at `0x140082211`
- `ntoskrnl!ObfDereferenceObject` at `0x140082367`
- `ntoskrnl!ObfDereferenceObject` at `0x140082506`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x1400823c4`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x1400823c4`
- `ntoskrnl!ObfReferenceObject` at `0x140081e50`
- `ntoskrnl!ObfReferenceObject` at `0x140081e50`
- `ntoskrnl!ZwClose` at `0x140081e61`
- `ntoskrnl!ZwClose` at `0x140081e61`
- `ntoskrnl!RtlInitUnicodeString` at `0x140081f9d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400820c5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140081f9d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400820c5`
- `ntoskrnl!IoCreateNotificationEvent` at `0x140081e10`
- `ntoskrnl!IoCreateNotificationEvent` at `0x140081e10`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140081dd3`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140081dd3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400823a7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400823a7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140081dae`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140081dae`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140082333`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140082333`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14008227a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140082480`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14008227a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140082480`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140082248`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140082447`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140082248`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140082447`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14008240b`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14008240b`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400824f2`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400824f2`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400824bc`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400824bc`
- `watchdog!WdLogSingleEntry1` at `0x140081ce4`
- `watchdog!WdLogSingleEntry1` at `0x140081dee`
- `watchdog!WdLogSingleEntry1` at `0x140081e32`
- `watchdog!WdLogSingleEntry1` at `0x140082096`
- `watchdog!WdLogSingleEntry1` at `0x140082107`
- `watchdog!WdLogSingleEntry1` at `0x1400822b0`
- `watchdog!WdLogSingleEntry1` at `0x140082348`
- `watchdog!WdLogSingleEntry1` at `0x1400823d9`
- `watchdog!WdLogSingleEntry1` at `0x140082420`
- `watchdog!WdLogSingleEntry1` at `0x1400824d1`
- `watchdog!WdLogSingleEntry1` at `0x14008253b`
- `watchdog!WdLogSingleEntry1` at `0x140081ce4`
- `watchdog!WdLogSingleEntry1` at `0x140081dee`
- `watchdog!WdLogSingleEntry1` at `0x140081e32`
- `watchdog!WdLogSingleEntry1` at `0x140082096`
- `watchdog!WdLogSingleEntry1` at `0x140082107`
- `watchdog!WdLogSingleEntry1` at `0x1400822b0`
- `watchdog!WdLogSingleEntry1` at `0x140082348`
- `watchdog!WdLogSingleEntry1` at `0x1400823d9`
- `watchdog!WdLogSingleEntry1` at `0x140082420`
- `watchdog!WdLogSingleEntry1` at `0x1400824d1`
- `watchdog!WdLogSingleEntry1` at `0x14008253b`

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
  PKEVENT v14; // rax
  unsigned int v15; // ebx
  int DevicePropertyDataString; // eax
  unsigned int v17; // r15d
  unsigned int v18; // r12d
  unsigned __int64 v19; // rdx
  char *v20; // rax
  char *v21; // r9
  unsigned __int16 Length; // ax
  unsigned __int16 v23; // cx
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  __int64 v30; // rcx
  _QWORD *v31; // rax
  __int128 v32; // xmm1
  void *v33; // rcx
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int64 v40; // rbx
  __int64 *v41; // rax
  char v42; // [rsp+41h] [rbp-BFh]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  void *EventHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v46; // [rsp+78h] [rbp-88h]
  _OWORD v47[9]; // [rsp+90h] [rbp-70h] BYREF

  memset(v47, 0, 0x88u);
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
        v46 = 0;
        v6 = *(unsigned __int16 *)(v4 + 2) + 792LL;
        *(_DWORD *)&DestinationString.Length = 0;
        Pool2 = (void *)ExAllocatePool2(64, v6, 1953656900);
        v8 = (__int64)Pool2;
        if ( !Pool2 )
        {
          WdLogSingleEntry1(6);
          WdLogGlobalForLineNumber = 2466;
          return 0;
        }
        v42 = 0;
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
        if ( IoGetDeviceObjectPointer(
               (PUNICODE_STRING)(v8 + 144),
               0x80000000,
               (PFILE_OBJECT *)(v8 + 176),
               (PDEVICE_OBJECT *)(v8 + 184)) < 0 )
        {
          v12 = 0;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 2525;
LABEL_38:
          v24 = *(void **)(v8 + 336);
          if ( v24 )
          {
            ExFreePoolWithTag(v24, 0);
            *(_QWORD *)(v8 + 336) = 0;
          }
          v25 = *(void **)(v8 + 344);
          if ( v25 )
          {
            ExFreePoolWithTag(v25, 0);
            *(_QWORD *)(v8 + 344) = 0;
          }
          v26 = *(void **)(v8 + 352);
          if ( v26 )
          {
            ExFreePoolWithTag(v26, 0);
            *(_QWORD *)(v8 + 352) = 0;
          }
          v27 = *(void **)(v8 + 360);
          if ( v27 )
          {
            ExFreePoolWithTag(v27, 0);
            *(_QWORD *)(v8 + 360) = 0;
          }
          v28 = *(void **)(v8 + 368);
          if ( v28 )
          {
            ExFreePoolWithTag(v28, 0);
            *(_QWORD *)(v8 + 368) = 0;
          }
          if ( v12 )
            ObfDereferenceObject(*(PVOID *)(v8 + 176));
          v29 = *(void **)(v8 + 464);
          if ( v29 )
            ObfDereferenceObject(v29);
          if ( *(_QWORD *)(v8 + 136) )
            RtlFreeUnicodeString((PUNICODE_STRING)(v8 + 128));
          if ( !v11 )
            goto LABEL_58;
          KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
          v30 = *(_QWORD *)v8;
          if ( *(_QWORD *)(*(_QWORD *)v8 + 8LL) == v8 )
          {
            v31 = *(_QWORD **)(v8 + 8);
            if ( *v31 == v8 )
            {
              *v31 = v30;
              *(_QWORD *)(v30 + 8) = v31;
              KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_58:
              ExFreePoolWithTag((PVOID)v8, 0);
              v11 = v42;
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
        v14 = IoCreateNotificationEvent(0, &EventHandle);
        *(_QWORD *)(v8 + 464) = v14;
        if ( !v14 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 2548;
          goto LABEL_38;
        }
        ObfReferenceObject(v14);
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
          v15 = *(_DWORD *)&DestinationString.Length;
        }
        else
        {
          v15 = 0;
        }
        DevicePropertyDataString = DpiGetDevicePropertyDataString(
                                     DeviceAttachmentBaseRef,
                                     (DEVPROPKEY *)&DEVPKEY_DeviceContainer_ModelName,
                                     v8 + 344,
                                     (__int64)&DestinationString);
        v17 = *(_DWORD *)&DestinationString.Length;
        if ( DevicePropertyDataString < 0 )
          v17 = 0;
        v18 = v15 + v17;
        if ( v15 + v17 )
        {
          v19 = v18 + 4LL;
          if ( v19 < 0xFFFF )
          {
            v20 = (char *)ExAllocatePool2(64, v19, 1953656900);
            *(_QWORD *)(v8 + 352) = v20;
            v21 = v20;
            if ( v20 )
            {
              DestinationString = 0;
              if ( v18 == v17 )
              {
                Length = DestinationString.Length;
                v23 = 0;
              }
              else
              {
                memmove(v20, *(const void **)(v8 + 336), v15);
                *(_WORD *)(*(_QWORD *)(v8 + 352) + 2 * ((unsigned __int64)v15 >> 1)) = 0;
                RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v8 + 352));
                *(_WORD *)(*(_QWORD *)(v8 + 352) + 2 * ((unsigned __int64)DestinationString.Length >> 1)) = 32;
                v21 = *(char **)(v8 + 352);
                Length = DestinationString.Length + 2;
                DestinationString.Length = Length;
                v23 = Length;
              }
              DestinationString.MaximumLength = v18 + 4;
              if ( v17 )
              {
                memmove(&v21[2 * ((unsigned __int64)v23 >> 1)], *(const void **)(v8 + 344), v17);
                Length = DestinationString.Length;
              }
              *(_WORD *)(*(_QWORD *)(v8 + 352) + 2 * ((unsigned __int64)(v17 + Length) >> 1)) = 0;
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
        if ( (int)DpiGetDeviceInstanceId(DeviceAttachmentBaseRef) < 0 )
        {
          WdLogSingleEntry1(2);
          v11 = 0;
          v12 = 1;
          WdLogGlobalForLineNumber = 2731;
          goto LABEL_38;
        }
        RtlInitUnicodeString((PUNICODE_STRING)(v8 + 160), *(PCWSTR *)&DestinationString.Length);
        if ( (int)DpiMiracastSendSyncUserModeRequest(v8, 2295808) >= 0 )
        {
          if ( *((_QWORD *)&v46 + 1) >= 0x88u )
          {
            v32 = v47[1];
            v33 = (void *)DWORD1(v47[8]);
            *(_OWORD *)(v8 + 204) = v47[0];
            v34 = v47[2];
            *(_OWORD *)(v8 + 220) = v32;
            v35 = v47[3];
            *(_OWORD *)(v8 + 236) = v34;
            v36 = v47[4];
            *(_OWORD *)(v8 + 252) = v35;
            v37 = v47[5];
            *(_OWORD *)(v8 + 268) = v36;
            v38 = v47[6];
            *(_OWORD *)(v8 + 284) = v37;
            v39 = v47[7];
            *(_OWORD *)(v8 + 300) = v38;
            *(_OWORD *)(v8 + 316) = v39;
            *(_WORD *)(v8 + 332) = 0;
            if ( PsLookupProcessByProcessId(v33, (PEPROCESS *)(v8 + 104)) >= 0 )
            {
              ObfDereferenceObject(*(PVOID *)(v8 + 104));
              AcquireMiniportListMutex();
              v40 = qword_14015F280;
              v12 = 1;
              v11 = 1;
              v42 = 1;
              while ( (__int64 *)v40 != &qword_14015F280 )
              {
                if ( !RtlCompareUnicodeString(
                        *((PCUNICODE_STRING *)NotificationStructure + 5),
                        (PCUNICODE_STRING)(v40 + 144),
                        0) )
                  goto LABEL_36;
                v40 = *(_QWORD *)v40;
              }
              if ( ZwAllocateLocallyUniqueId((PLUID)(v8 + 96)) >= 0 )
              {
                if ( IoRegisterDeviceInterface(
                       DeviceAttachmentBaseRef,
                       &GUID_DEVINTERFACE_MIRACAST_DISPLAY_ARRIVAL,
                       0,
                       (PUNICODE_STRING)(v8 + 128)) >= 0 )
                {
                  KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
                  v41 = (__int64 *)qword_14015F288;
                  if ( *(__int64 **)qword_14015F288 != &qword_14015F280 )
                    goto LABEL_79;
                  *(_QWORD *)v8 = &qword_14015F280;
                  *(_QWORD *)(v8 + 8) = v41;
                  *v41 = v8;
                  qword_14015F288 = v8;
                  KeReleaseInStackQueuedSpinLock(&LockHandle);
                  if ( IoRegisterPlugPlayNotification(
                         EventCategoryTargetDeviceChange,
                         0,
                         *(PVOID *)(v8 + 176),
                         (PDRIVER_OBJECT)g_pDriverObject,
                         DpiMiracastTargetDeviceChange,
                         (PVOID)v8,
                         (PVOID *)(v8 + 400)) >= 0 )
                  {
                    IoSetDeviceInterfaceState((PUNICODE_STRING)(v8 + 128), 1u);
                    goto LABEL_75;
                  }
                  WdLogSingleEntry1(2);
                  WdLogGlobalForLineNumber = 2909;
                  goto LABEL_37;
                }
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 2870;
              }
              else
              {
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 2851;
              }
LABEL_36:
              v11 = 0;
LABEL_37:
              DxgkFreeUnicodeString(v8 + 160);
              goto LABEL_38;
            }
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 2798;
          }
          else
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 2769;
          }
        }
        else
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 2759;
        }
        v12 = 1;
        goto LABEL_36;
      }
    }
  }
  WdLogSingleEntry1(2);
  result = 3221225711LL;
  WdLogGlobalForLineNumber = 2427;
  return result;
}

```

## disassembly

```asm
0x140081c00  push    rbp
0x140081c02  push    rbx
0x140081c03  push    rsi
0x140081c04  push    rdi
0x140081c05  push    r12
0x140081c07  push    r13
0x140081c09  push    r14
0x140081c0b  push    r15
0x140081c0d  lea     rbp, [rsp-38h]
0x140081c12  sub     rsp, 138h
0x140081c19  mov     rax, cs:__security_cookie
0x140081c20  xor     rax, rsp
0x140081c23  mov     [rbp+70h+var_50], rax
0x140081c27  mov     r14, rcx
0x140081c2a  xor     edx, edx; Val
0x140081c2c  lea     rcx, [rbp+70h+var_E0]; void *
0x140081c30  mov     r8d, 88h; Size
0x140081c36  call    memset
0x140081c3b  xor     eax, eax
0x140081c3d  xor     esi, esi
0x140081c3f  mov     qword ptr [rsp+170h+LockHandle.OldIrql], rax
0x140081c44  xorps   xmm0, xmm0
0x140081c47  movups  xmmword ptr [rsp+170h+LockHandle.LockQueue.Next], xmm0
0x140081c4c  test    r14, r14
0x140081c4f  jz      loc_14008252C
0x140081c55  mov     rax, [r14+14h]
0x140081c59  sub     rax, qword ptr cs:GUID_DEVINTERFACE_UMDF_MIRACAST_DIVICE_ARRIVAL.Data1
0x140081c60  jnz     short loc_140081C6D
0x140081c62  mov     rax, [r14+1Ch]
0x140081c66  sub     rax, qword ptr cs:GUID_DEVINTERFACE_UMDF_MIRACAST_DIVICE_ARRIVAL.Data4
0x140081c6d  test    rax, rax
0x140081c70  jnz     loc_14008252C
0x140081c76  mov     rcx, [r14+28h]
0x140081c7a  test    rcx, rcx
0x140081c7d  jz      loc_14008252C
0x140081c83  mov     rax, [r14+4]
0x140081c87  sub     rax, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data1
0x140081c8e  jnz     short loc_140081C9B
0x140081c90  mov     rax, [r14+0Ch]
0x140081c94  sub     rax, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data4
0x140081c9b  test    rax, rax
0x140081c9e  jnz     short loc_140081CFA
0x140081ca0  mov     [rsp+170h+EventHandle], rsi
0x140081ca5  mov     ebx, 318h
0x140081caa  movups  [rsp+170h+var_F8], xmm0
0x140081caf  movzx   edx, word ptr [rcx+2]
0x140081cb3  mov     r15d, 74727044h
0x140081cb9  add     rdx, rbx
0x140081cbc  mov     dword ptr [rsp+170h+DestinationString.Length], esi
0x140081cc0  mov     r8d, r15d
0x140081cc3  lea     ecx, [rax+40h]
0x140081cc6  call    cs:__imp_ExAllocatePool2
0x140081ccd  nop     dword ptr [rax+rax+00h]
0x140081cd2  mov     rdi, rax
0x140081cd5  test    rax, rax
0x140081cd8  jnz     short loc_140081D01
0x140081cda  mov     rdx, 0FFFFFFFFC0000017h
0x140081ce1  lea     ecx, [rax+6]
0x140081ce4  call    cs:__imp_WdLogSingleEntry1
0x140081ceb  nop     dword ptr [rax+rax+00h]
0x140081cf0  mov     cs:WdLogGlobalForLineNumber, 9A2h
0x140081cfa  xor     eax, eax
0x140081cfc  jmp     loc_140082553
0x140081d01  mov     r8, rbx; Size
0x140081d04  mov     [rsp+170h+var_12F], sil
0x140081d09  xor     edx, edx; Val
0x140081d0b  mov     [rsp+170h+var_130], sil
0x140081d10  mov     rcx, rdi; void *
0x140081d13  mov     r13, rsi
0x140081d16  mov     r12b, sil
0x140081d19  call    memset
0x140081d1e  mov     [rdi+10h], r15d
0x140081d22  lea     rcx, [rdi+38h]; Event
0x140081d26  mov     dword ptr [rdi+14h], 0Eh
0x140081d2d  or      eax, 0FFFFFFFFh
0x140081d30  mov     [rdi+1A4h], eax
0x140081d36  mov     r15d, 1
0x140081d3c  mov     [rdi+1C8h], eax
0x140081d42  mov     edx, r15d; Type
0x140081d45  mov     [rdi+18h], r15
0x140081d49  xor     r8d, r8d; State
0x140081d4c  mov     [rdi+58h], rsi
0x140081d50  mov     [rdi+20h], r15d
0x140081d54  mov     [rdi+28h], rsi
0x140081d58  mov     [rdi+30h], esi
0x140081d5b  call    cs:__imp_KeInitializeEvent
0x140081d62  nop     dword ptr [rax+rax+00h]
0x140081d67  lea     rcx, [rdi+208h]; Dpc
0x140081d6e  mov     r8, rdi; DeferredContext
0x140081d71  lea     rdx, DpiMiracastChunkInfoCallbackDpc; DeferredRoutine
0x140081d78  call    cs:__imp_KeInitializeDpc
0x140081d7f  nop     dword ptr [rax+rax+00h]
0x140081d84  mov     rdx, [r14+28h]; SourceString
0x140081d88  lea     rbx, [rdi+90h]
0x140081d8f  mov     [rbx], si
0x140081d92  mov     rcx, rbx; DestinationString
0x140081d95  movzx   eax, word ptr [rdx+2]
0x140081d99  mov     [rdi+92h], ax
0x140081da0  lea     rax, [rdi+318h]
0x140081da7  mov     [rdi+98h], rax
0x140081dae  call    cs:__imp_RtlCopyUnicodeString
0x140081db5  nop     dword ptr [rax+rax+00h]
0x140081dba  lea     rsi, [rdi+0B8h]
0x140081dc1  mov     edx, 80000000h; DesiredAccess
0x140081dc6  mov     r9, rsi; DeviceObject
0x140081dc9  lea     r8, [rdi+0B0h]; FileObject
0x140081dd0  mov     rcx, rbx; ObjectName
0x140081dd3  call    cs:__imp_IoGetDeviceObjectPointer
0x140081dda  nop     dword ptr [rax+rax+00h]
0x140081ddf  test    eax, eax
0x140081de1  jns     short loc_140081E09
0x140081de3  xor     r15b, r15b
0x140081de6  movsxd  rdx, eax
0x140081de9  mov     ecx, 2
0x140081dee  call    cs:__imp_WdLogSingleEntry1
0x140081df5  nop     dword ptr [rax+rax+00h]
0x140081dfa  mov     cs:WdLogGlobalForLineNumber, 9DDh
0x140081e04  jmp     loc_140082134
0x140081e09  lea     rdx, [rsp+170h+EventHandle]; EventHandle
0x140081e0e  xor     ecx, ecx; EventName
0x140081e10  call    cs:__imp_IoCreateNotificationEvent
0x140081e17  nop     dword ptr [rax+rax+00h]
0x140081e1c  mov     [rdi+1D0h], rax
0x140081e23  test    rax, rax
0x140081e26  jnz     short loc_140081E4D
0x140081e28  mov     rdx, 0FFFFFFFFC0000017h
0x140081e2f  lea     ecx, [rax+2]
0x140081e32  call    cs:__imp_WdLogSingleEntry1
0x140081e39  nop     dword ptr [rax+rax+00h]
0x140081e3e  mov     cs:WdLogGlobalForLineNumber, 9F4h
0x140081e48  jmp     loc_140082134
0x140081e4d  mov     rcx, rax; Object
0x140081e50  call    cs:__imp_ObfReferenceObject
0x140081e57  nop     dword ptr [rax+rax+00h]
0x140081e5c  mov     rcx, [rsp+170h+EventHandle]; Handle
0x140081e61  call    cs:__imp_ZwClose
0x140081e68  nop     dword ptr [rax+rax+00h]
0x140081e6d  mov     rcx, [rsi]; DeviceObject
0x140081e70  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x140081e77  nop     dword ptr [rax+rax+00h]
0x140081e7c  mov     esi, 100h
0x140081e81  lea     rbx, [rdi+150h]
0x140081e88  mov     r13, rax
0x140081e8b  lea     rdx, DEVPKEY_DeviceContainer_Manufacturer; PropertyKey
0x140081e92  lea     rax, [rsp+170h+DestinationString]
0x140081e97  mov     r9d, esi
0x140081e9a  mov     [rsp+170h+Context], rax; __int64
0x140081e9f  mov     rcx, r13; Pdo
0x140081ea2  mov     [rsp+170h+CallbackRoutine], rbx; __int64
0x140081ea7  call    DpiGetDevicePropertyDataString
0x140081eac  test    eax, eax
0x140081eae  jns     short loc_140081ED5
0x140081eb0  lea     rax, [rsp+170h+DestinationString]
0x140081eb5  mov     r9, rbx
0x140081eb8  mov     r8, r15
0x140081ebb  mov     [rsp+170h+CallbackRoutine], rax; __int64
0x140081ec0  mov     edx, 8; DeviceProperty
0x140081ec5  mov     rcx, r13; DeviceObject
0x140081ec8  call    DpiGetDevicePropertyString
0x140081ecd  test    eax, eax
0x140081ecf  jns     short loc_140081ED5
0x140081ed1  xor     ebx, ebx
0x140081ed3  jmp     short loc_140081ED9
0x140081ed5  mov     ebx, dword ptr [rsp+170h+DestinationString.Length]
0x140081ed9  lea     rcx, [rsp+170h+DestinationString]
0x140081ede  mov     r9, rsi
0x140081ee1  mov     [rsp+170h+Context], rcx; __int64
0x140081ee6  lea     rax, [rdi+158h]
0x140081eed  mov     rcx, r13; Pdo
0x140081ef0  mov     [rsp+170h+CallbackRoutine], rax; __int64
0x140081ef5  lea     rdx, DEVPKEY_DeviceContainer_ModelName; PropertyKey
0x140081efc  call    DpiGetDevicePropertyDataString
0x140081f01  mov     r15d, dword ptr [rsp+170h+DestinationString.Length]
0x140081f06  xor     edx, edx
0x140081f08  test    eax, eax
0x140081f0a  cmovs   r15d, edx
0x140081f0e  lea     esi, [rdx+2]
0x140081f11  lea     r12d, [rbx+r15]
0x140081f15  test    r12d, r12d
0x140081f18  jz      loc_140082022
0x140081f1e  mov     edx, r12d
0x140081f21  add     rdx, 4
0x140081f25  cmp     rdx, 0FFFFh
0x140081f2c  jnb     loc_140082022
0x140081f32  lea     ecx, [rsi+3Eh]
0x140081f35  mov     r8d, 74727044h
0x140081f3b  call    cs:__imp_ExAllocatePool2
0x140081f42  nop     dword ptr [rax+rax+00h]
0x140081f47  mov     [rdi+160h], rax
0x140081f4e  mov     r9, rax
0x140081f51  test    rax, rax
0x140081f54  jz      loc_140082022
0x140081f5a  xorps   xmm0, xmm0
0x140081f5d  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x140081f62  cmp     r12d, r15d
0x140081f65  jz      short loc_140081FD7
0x140081f67  mov     rdx, [rdi+150h]; Src
0x140081f6e  mov     ecx, r12d
0x140081f71  sub     ecx, r15d
0x140081f74  mov     ebx, ecx
0x140081f76  mov     r8d, ecx; Size
0x140081f79  mov     rcx, rax; void *
0x140081f7c  call    memmove
0x140081f81  mov     rcx, [rdi+160h]
0x140081f88  xor     eax, eax
0x140081f8a  shr     rbx, 1
0x140081f8d  mov     [rcx+rbx*2], ax
0x140081f91  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x140081f96  mov     rdx, [rdi+160h]; SourceString
0x140081f9d  call    cs:__imp_RtlInitUnicodeString
0x140081fa4  nop     dword ptr [rax+rax+00h]
0x140081fa9  movzx   ecx, [rsp+170h+DestinationString.Length]
0x140081fae  mov     rax, [rdi+160h]
0x140081fb5  shr     rcx, 1
0x140081fb8  mov     word ptr [rax+rcx*2], 20h ; ' '
0x140081fbe  movzx   eax, [rsp+170h+DestinationString.Length]
0x140081fc3  mov     r9, [rdi+160h]
0x140081fca  add     ax, si
0x140081fcd  mov     [rsp+170h+DestinationString.Length], ax
0x140081fd2  movzx   ecx, ax
0x140081fd5  jmp     short loc_140081FDE
0x140081fd7  movzx   eax, [rsp+170h+DestinationString.Length]
0x140081fdc  xor     ecx, ecx
0x140081fde  add     r12w, 4
0x140081fe3  mov     [rsp+170h+DestinationString.MaximumLength], r12w
0x140081fe9  test    r15d, r15d
0x140081fec  jz      short loc_14008200C
0x140081fee  mov     rdx, [rdi+158h]; Src
0x140081ff5  movzx   eax, cx
0x140081ff8  shr     rax, 1
0x140081ffb  mov     r8d, r15d; Size
0x140081ffe  lea     rcx, [r9+rax*2]; void *
0x140082002  call    memmove
0x140082007  movzx   eax, [rsp+170h+DestinationString.Length]
0x14008200c  mov     rcx, [rdi+160h]
0x140082013  movzx   edx, ax
0x140082016  add     edx, r15d
0x140082019  shr     rdx, 1
0x14008201c  xor     eax, eax
0x14008201e  mov     [rcx+rdx*2], ax
0x140082022  lea     rcx, [rsp+170h+DestinationString]
0x140082027  mov     ebx, 100h
0x14008202c  mov     [rsp+170h+Context], rcx; __int64
0x140082031  lea     rax, [rdi+168h]
0x140082038  mov     rcx, r13; Pdo
0x14008203b  mov     [rsp+170h+CallbackRoutine], rax; __int64
0x140082040  mov     r9d, ebx
0x140082043  lea     rdx, DEVPKEY_DeviceContainer_ModelNumber; PropertyKey
0x14008204a  call    DpiGetDevicePropertyDataString
0x14008204f  lea     rcx, [rsp+170h+DestinationString]
0x140082054  mov     r9d, ebx
0x140082057  mov     [rsp+170h+Context], rcx; __int64
0x14008205c  lea     rax, [rdi+170h]
0x140082063  mov     rcx, r13; Pdo
0x140082066  mov     [rsp+170h+CallbackRoutine], rax; __int64
0x14008206b  lea     rdx, DEVPKEY_Device_FriendlyName; PropertyKey
0x140082072  call    DpiGetDevicePropertyDataString
0x140082077  lea     rdx, [rsp+170h+DestinationString]
0x14008207c  mov     qword ptr [rsp+170h+DestinationString.Length], 0
0x140082085  mov     rcx, r13; DeviceObject
0x140082088  call    DpiGetDeviceInstanceId
0x14008208d  test    eax, eax
0x14008208f  jns     short loc_1400820B9
0x140082091  movsxd  rdx, eax
0x140082094  mov     ecx, esi
0x140082096  call    cs:__imp_WdLogSingleEntry1
0x14008209d  nop     dword ptr [rax+rax+00h]
0x1400820a2  mov     r12b, [rsp+170h+var_130]
0x1400820a7  mov     r15d, 1
0x1400820ad  mov     cs:WdLogGlobalForLineNumber, 0AABh
0x1400820b7  jmp     short loc_140082134
0x1400820b9  mov     rdx, qword ptr [rsp+170h+DestinationString.Length]; SourceString
0x1400820be  lea     rcx, [rdi+0A0h]; DestinationString
0x1400820c5  call    cs:__imp_RtlInitUnicodeString
0x1400820cc  nop     dword ptr [rax+rax+00h]
0x1400820d1  lea     rax, [rsp+170h+var_F8]
0x1400820d6  mov     ebx, 88h
0x1400820db  mov     [rsp+170h+NotificationEntry], rax
0x1400820e0  mov     edx, 230800h
0x1400820e5  lea     rax, [rbp+70h+var_E0]
0x1400820e9  mov     dword ptr [rsp+170h+Context], ebx
0x1400820ed  mov     rcx, rdi
0x1400820f0  mov     [rsp+170h+CallbackRoutine], rax
0x1400820f5  call    DpiMiracastSendSyncUserModeRequest
0x1400820fa  test    eax, eax
0x1400820fc  jns     loc_1400822A1
0x140082102  movsxd  rdx, eax
0x140082105  mov     ecx, esi
0x140082107  call    cs:__imp_WdLogSingleEntry1
0x14008210e  nop     dword ptr [rax+rax+00h]
0x140082113  mov     cs:WdLogGlobalForLineNumber, 0AC7h
0x14008211d  mov     r15d, 1
0x140082123  mov     r12b, [rsp+170h+var_130]
0x140082128  lea     rcx, [rdi+0A0h]
0x14008212f  call    DxgkFreeUnicodeString
0x140082134  mov     rcx, [rdi+150h]; P
0x14008213b  test    rcx, rcx
0x14008213e  jz      short loc_140082159
0x140082140  xor     edx, edx; Tag
0x140082142  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
