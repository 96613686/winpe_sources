# WaitForSynchronizationObjectFromCpu(_D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU const *,DXGPROCESS *,DXGDEVICE *,void *)

- ea: `0x14034c010`
- end: `0x14034cb2c`
- name: `?WaitForSynchronizationObjectFromCpu@@YAJPEBU_D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU@@PEAVDXGPROCESS@@PEAVDXGDEVICE@@PEAX@Z`
- size: `2844`
- prototype: `__int64 __fastcall(const struct _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU *, struct DXGPROCESS *, struct DXGDEVICE *, void *)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x14034b77c`

## callees

- `0x140012380`
- `0x140015970`
- `0x140017fb8`
- `0x14001b890`
- `0x14001d070`
- `0x14001e26c`
- `0x14001f120`
- `0x14001f870`
- `0x140020200`
- `0x140030680`
- `0x140030860`
- `0x140033bd4`
- `0x140036cd8`
- `0x140037a9c`
- `0x140037d50`
- `0x140038c48`
- `0x14004885c`
- `0x14004ce64`
- `0x1400549f0`
- `0x1400a0100`
- `0x1401990b0`
- `0x14032d860`
- `0x14032f5f0`
- `0x14034c010`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034c505`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14034c505`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c190`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c1b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c282`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c2ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c911`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c93a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034cae1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c190`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c1b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c282`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c2ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c911`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034c93a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034cae1`
- `ntoskrnl!ExAllocatePool2` at `0x14034c113`
- `ntoskrnl!ExAllocatePool2` at `0x14034c113`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14034c4f9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14034c4f9`
- `ntoskrnl!KeInitializeEvent` at `0x14034c376`
- `ntoskrnl!KeInitializeEvent` at `0x14034c376`
- `ntoskrnl!ObfDereferenceObject` at `0x14034c979`
- `ntoskrnl!ObfDereferenceObject` at `0x14034cac8`
- `ntoskrnl!ObfDereferenceObject` at `0x14034cafa`
- `ntoskrnl!ObfDereferenceObject` at `0x14034c979`
- `ntoskrnl!ObfDereferenceObject` at `0x14034cac8`
- `ntoskrnl!ObfDereferenceObject` at `0x14034cafa`
- `ntoskrnl!ObfReferenceObject` at `0x14034c860`
- `ntoskrnl!ObfReferenceObject` at `0x14034c860`
- `ntoskrnl!ExEventObjectType` at `0x14034c20b`
- `ntoskrnl!ExEventObjectType` at `0x14034c2e2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14034c22f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14034c22f`
- `ntoskrnl!PsIsThreadTerminating` at `0x14034ca22`
- `ntoskrnl!PsIsThreadTerminating` at `0x14034ca22`
- `ntoskrnl!ObCreateObject` at `0x14034c335`
- `ntoskrnl!ObCreateObject` at `0x14034c335`
- `ntoskrnl!KeSetEvent` at `0x14034cab9`
- `ntoskrnl!KeSetEvent` at `0x14034cab9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14034ca0b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14034ca0b`
- `watchdog!WdLogSingleEntry4` at `0x14034c7b2`
- `watchdog!WdLogSingleEntry4` at `0x14034c7b2`
- `watchdog!WdLogSingleEntry2` at `0x14034c256`
- `watchdog!WdLogSingleEntry2` at `0x14034c256`
- `watchdog!WdLogSingleEntry3` at `0x14034c6c8`
- `watchdog!WdLogSingleEntry3` at `0x14034c6c8`
- `watchdog!WdLogSingleEntry0` at `0x14034c12e`
- `watchdog!WdLogSingleEntry0` at `0x14034c49a`
- `watchdog!WdLogSingleEntry0` at `0x14034c666`
- `watchdog!WdLogSingleEntry0` at `0x14034ca49`
- `watchdog!WdLogSingleEntry0` at `0x14034ca96`
- `watchdog!WdLogSingleEntry0` at `0x14034c12e`
- `watchdog!WdLogSingleEntry0` at `0x14034c49a`
- `watchdog!WdLogSingleEntry0` at `0x14034c666`
- `watchdog!WdLogSingleEntry0` at `0x14034ca49`
- `watchdog!WdLogSingleEntry0` at `0x14034ca96`
- `watchdog!WdLogSingleEntry1` at `0x14034c350`
- `watchdog!WdLogSingleEntry1` at `0x14034c5b3`
- `watchdog!WdLogSingleEntry1` at `0x14034c5f9`
- `watchdog!WdLogSingleEntry1` at `0x14034c735`
- `watchdog!WdLogSingleEntry1` at `0x14034c9a0`
- `watchdog!WdLogSingleEntry1` at `0x14034c350`
- `watchdog!WdLogSingleEntry1` at `0x14034c5b3`
- `watchdog!WdLogSingleEntry1` at `0x14034c5f9`
- `watchdog!WdLogSingleEntry1` at `0x14034c735`
- `watchdog!WdLogSingleEntry1` at `0x14034c9a0`

## string_xrefs

- `0x14034c74b`: `0x%I64x object is opened as signal only and thus cannot be waited on.`

## pseudocode

```c
__int64 __fastcall WaitForSynchronizationObjectFromCpu(
        const struct _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU *a1,
        struct DXGPROCESS *a2,
        struct ADAPTER_RENDER **a3,
        void *a4)
{
  int v7; // ebx
  struct _KEVENT *v8; // r12
  __int64 Pool2; // r13
  struct DXGGLOBAL *Global; // rax
  DXGPROCESS *v11; // rbx
  HANDLE hAsyncEvent; // rcx
  NTSTATUS v13; // eax
  struct _VIDSCH_SYNC_OBJECT **v14; // r15
  struct ADAPTER_RENDER *v15; // rcx
  struct VIDMM_DEVICE *v16; // rdx
  __int64 v17; // rax
  UINT ObjectCount; // r8d
  __int64 v19; // rcx
  DXGPUSHLOCK *v20; // rdx
  __int64 v21; // r15
  unsigned int v22; // eax
  __int64 v23; // rbx
  int v24; // ecx
  __int64 v25; // rbx
  struct VIDMM_PAGING_QUEUE *v26; // rcx
  struct ADAPTER_RENDER **v27; // r8
  __int64 v28; // rax
  UINT v29; // r8d
  DXGPROCESS *v30; // rsi
  __int64 v31; // r9
  __int64 v32; // rbx
  struct _VIDSCH_SYNC_OBJECT *VidSchSyncObject; // rax
  __int64 v34; // r9
  int v35; // edx
  int v36; // ecx
  int v37; // r8d
  PRKEVENT v38; // rcx
  NTSTATUS v39; // edi
  bool IsNativeFenceOpenedAsMonitoredFence; // [rsp+50h] [rbp-B0h]
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v43[32]; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+80h] [rbp-80h]
  PVOID v45; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v46[32]; // [rsp+90h] [rbp-70h] BYREF
  int v47; // [rsp+B0h] [rbp-50h]
  struct DXGDEVICE *v48; // [rsp+B8h] [rbp-48h] BYREF
  char v49; // [rsp+C0h] [rbp-40h]
  PRKEVENT Event; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v51[16]; // [rsp+D0h] [rbp-30h] BYREF
  DXGPROCESS *v52; // [rsp+E0h] [rbp-20h]
  int v53; // [rsp+E8h] [rbp-18h]
  struct VIDMM_PAGING_QUEUE *i; // [rsp+F0h] [rbp-10h] BYREF
  D3DKMT_HANDLE v55; // [rsp+F8h] [rbp-8h]
  __int64 v56; // [rsp+100h] [rbp+0h]
  PVOID Object; // [rsp+108h] [rbp+8h] BYREF
  void *v58; // [rsp+110h] [rbp+10h]
  struct _VIDSCH_SYNC_OBJECT **v59; // [rsp+118h] [rbp+18h]
  _QWORD v60[4]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v61; // [rsp+140h] [rbp+40h]
  _QWORD v62[4]; // [rsp+150h] [rbp+50h] BYREF
  char v63; // [rsp+170h] [rbp+70h]
  _BYTE v64[160]; // [rsp+180h] [rbp+80h] BYREF

  v58 = a4;
  v52 = a2;
  Event = 0;
  v49 = 0;
  v48 = (struct DXGDEVICE *)a3;
  DXGDEVICEACCESSLOCKSHARED::Acquire((DXGDEVICEACCESSLOCKSHARED *)&v48);
  COREDEVICEACCESS::COREDEVICEACCESS(v64, a3, 0);
  v7 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v64, 0);
  if ( v7 < 0 )
    goto LABEL_2;
  v8 = 0;
  Pool2 = 0;
  Global = DXGGLOBAL::GetGlobal();
  DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v51, Global, 0);
  DXGSYNCOBJECTLOCK::AcquireShared((DXGSYNCOBJECTLOCK *)v51);
  v11 = v52;
  v45 = 0;
  v47 = 0;
  P = 0;
  v44 = 0;
  if ( !a4 )
  {
    if ( DXGPROCESS::IsNativeWslProcess(v52) && a1->hAsyncEvent )
    {
      Pool2 = ExAllocatePool2(64, 40, 1265072196);
      if ( !Pool2 )
      {
        WdLogSingleEntry0(6);
        WdLogGlobalForLineNumber = 5870;
        DxgkLogInternalTriageEvent(
          0,
          262145,
          -1,
          (unsigned int)L"Failed to allocate memory for DXG_SIGNAL_GUEST_CPU_EVENT",
          5870,
          0,
          0,
          0,
          0);
        v7 = -1073741801;
LABEL_8:
        v44 = 0;
        P = 0;
        v45 = 0;
        v47 = 0;
        DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v51);
LABEL_2:
        COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v64);
        DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)&v48);
        return (unsigned int)v7;
      }
      *(_QWORD *)(Pool2 + 8) = a1->hAsyncEvent;
      v58 = (void *)Pool2;
      *(_BYTE *)(Pool2 + 16) = 1;
      *(_BYTE *)(Pool2 + 19) = 1;
      DXG_SIGNAL_GUEST_CPU_EVENT::AcquireReference((struct DXG_SIGNAL_GUEST_CPU_EVENT *)Pool2);
    }
    else
    {
      hAsyncEvent = a1->hAsyncEvent;
      if ( hAsyncEvent )
      {
        Object = 0;
        v13 = ObReferenceObjectByHandle(hAsyncEvent, 2u, (POBJECT_TYPE)ExEventObjectType, 1, &Object, 0);
        v8 = (struct _KEVENT *)Object;
        v7 = v13;
        if ( v13 < 0 )
        {
          WdLogSingleEntry2(3, a1->hAsyncEvent);
          WdLogGlobalForLineNumber = 5894;
          goto LABEL_13;
        }
      }
      else
      {
        v60[0] = 48;
        v60[3] = 512;
        v60[1] = 0;
        v60[2] = 0;
        v61 = 0;
        v7 = ObCreateObject(0, ExEventObjectType, v60, 0, 0, 24, 0, 0, &Event);
        if ( v7 < 0 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 5914;
          goto LABEL_8;
        }
        KeInitializeEvent(Event, SynchronizationEvent, 0);
        v8 = Event;
      }
      v11 = v52;
    }
  }
  v59 = (struct _VIDSCH_SYNC_OBJECT **)NonPagedPoolZeroedArray<_VIDSCH_SYNC_OBJECT *,4,1265072196>::AllocateElements(
                                         &v45,
                                         a1->ObjectCount);
  v14 = v59;
  if ( !v59 )
    goto LABEL_25;
  if ( (*((_DWORD *)v11 + 102) & 0x180) != 0 && a3 && a1->ObjectCount == 1 && !*a1->ObjectHandleArray )
  {
    v15 = a3[2];
    v16 = a3[99];
    i = 0;
    VIDMM_EXPORT::VidMmGetDevicePagingQueue(*((VIDMM_EXPORT **)v15 + 95), v16, 0, &i, v59);
    goto LABEL_70;
  }
  v17 = PagedPoolZeroedArray<DXGSYNCOBJECT *,4>::AllocateElements(&P, a1->ObjectCount);
  v56 = v17;
  if ( !v17 )
  {
LABEL_25:
    v7 = -1073741801;
    goto LABEL_13;
  }
  ObjectCount = a1->ObjectCount;
  v19 = 0;
  v53 = 0;
  if ( ObjectCount )
  {
    v20 = (DXGPROCESS *)((char *)v11 + 248);
    for ( i = (DXGPROCESS *)((char *)v11 + 248); ; v20 = i )
    {
      v21 = (unsigned int)v19;
      v55 = a1->ObjectHandleArray[v19];
      DXGPUSHLOCK::AcquireShared(v20);
      v22 = (v55 >> 6) & 0xFFFFFF;
      if ( v22 < *((_DWORD *)v11 + 74)
        && (v23 = *((_QWORD *)v11 + 35), ((v55 >> 25) & 0x60) == (*(_BYTE *)(v23 + 16LL * v22 + 8) & 0x60))
        && (*(_DWORD *)(v23 + 16LL * v22 + 8) & 0x2000) == 0
        && (v24 = *(_DWORD *)(v23 + 16LL * v22 + 8) & 0x1F) != 0 )
      {
        if ( v24 == 11 )
        {
          v25 = *(_QWORD *)(v23 + 16LL * v22);
        }
        else
        {
          WdLogSingleEntry0(2);
          v25 = 0;
          WdLogGlobalForLineNumber = 318;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        }
      }
      else
      {
        v25 = 0;
      }
      v26 = i;
      _InterlockedDecrement((volatile signed __int32 *)i + 4);
      ExReleasePushLockSharedEx(v26, 0);
      KeLeaveCriticalRegion();
      if ( !v25 )
        break;
      if ( (*(_DWORD *)(v25 + 72) & 0x20) != 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 5975;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"0x%I64x object is opened as signal only and thus cannot be waited on.",
          a1->ObjectHandleArray[v21],
          0,
          0,
          0,
          0);
        v7 = -1073741790;
        goto LABEL_13;
      }
      v27 = *(struct ADAPTER_RENDER ***)(v25 + 16);
      if ( v27 != a3 )
      {
        WdLogSingleEntry3(2, a1->ObjectHandleArray[v21], v27, a3);
        WdLogGlobalForLineNumber = 5987;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"0x%x object belongs to a different device 0x%p that 0x%p passed to the wait from CPU call.",
          a1->ObjectHandleArray[v21],
          *(_QWORD *)(v25 + 16),
          (__int64)a3,
          0,
          0);
        goto LABEL_61;
      }
      IsNativeFenceOpenedAsMonitoredFence = DXGSYNCOBJECT::IsNativeFenceOpenedAsMonitoredFence(
                                              *(DXGSYNCOBJECT **)(v25 + 32),
                                              v27[2]);
      if ( !*((_BYTE *)DXGGLOBAL::GetGlobal() + 305952)
        && *(_DWORD *)(*(_QWORD *)(v25 + 32) + 420LL) == 7
        && !*(_QWORD *)(v25 + 96)
        && !IsNativeFenceOpenedAsMonitoredFence )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 6001;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"DXGDEVICESYNCOBJECT 0x%x is a native fence object and has a NULL Driver Handle, returning STATUS"
                         "_INVALID_PARAMETER",
          v25,
          0,
          0,
          0,
          0);
LABEL_61:
        v7 = -1073741811;
        goto LABEL_13;
      }
      v28 = *(_QWORD *)(v25 + 32);
      if ( *(_DWORD *)(v28 + 420) == 7 && *(_DWORD *)(v28 + 316) == 1 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 6010;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"DXGDEVICESYNCOBJECT 0x%x. Queuing Wait/Signals not supported on native fence of type D3DDDI_NATI"
                         "VEFENCE_TYPE_INTRA_GPU, returning STATUS_INVALID_PARAMETER",
          v25,
          0,
          0,
          0,
          0);
        goto LABEL_61;
      }
      *(_QWORD *)(v56 + 8 * v21) = v28;
      v29 = a1->ObjectCount;
      v19 = (unsigned int)(v53 + 1);
      v53 = v19;
      if ( (unsigned int)v19 >= v29 )
      {
        v14 = v59;
        v17 = v56;
        goto LABEL_56;
      }
      v11 = v52;
    }
    v7 = -1073741811;
    v30 = v52;
    WdLogSingleEntry4(2, v52, a1->ObjectHandleArray[v21], v21, -1073741811);
    WdLogGlobalForLineNumber = 5967;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"0x%I64x passed an invalid wait for hSyncObject 0x%I64x at index %I64d returning 0x%I64x",
      (__int64)v30,
      a1->ObjectHandleArray[v21],
      v21,
      -1073741811,
      0);
    goto LABEL_13;
  }
LABEL_56:
  DXGPOINTERARRAYORDEREDACQUIRE<DXGSYNCOBJECT,&void AcquireSyncObjectMutex(DXGSYNCOBJECT *),&void ReleaseSyncObjectMutex(DXGSYNCOBJECT *),2>::DXGPOINTERARRAYORDEREDACQUIRE<DXGSYNCOBJECT,&void AcquireSyncObjectMutex(DXGSYNCOBJECT *),&void ReleaseSyncObjectMutex(DXGSYNCOBJECT *),2>(
    v62,
    v17);
  if ( v63 )
  {
    if ( !v62[0] )
    {
      v7 = -1073741801;
      goto LABEL_65;
    }
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 6035;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"The same sync object handle is passed twice",
      6035,
      0,
      0,
      0,
      0);
LABEL_59:
    v7 = -1073741811;
LABEL_65:
    DXGPOINTERARRAYORDEREDACQUIRE<DXGSYNCOBJECT,&void AcquireSyncObjectMutex(DXGSYNCOBJECT *),&void ReleaseSyncObjectMutex(DXGSYNCOBJECT *),2>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGSYNCOBJECT,&void AcquireSyncObjectMutex(DXGSYNCOBJECT *),&void ReleaseSyncObjectMutex(DXGSYNCOBJECT *),2>(v62);
LABEL_13:
    if ( P != v43 && P )
      ExFreePoolWithTag(P, 0);
    v44 = 0;
    P = 0;
    if ( v45 != v46 && v45 )
      ExFreePoolWithTag(v45, 0);
    v45 = 0;
    v47 = 0;
    DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v51);
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v64);
    DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)&v48);
    goto LABEL_84;
  }
  v31 = 0;
  if ( a1->ObjectCount )
  {
    while ( 1 )
    {
      v32 = (unsigned int)v31;
      VidSchSyncObject = DXGSYNCOBJECT::GetVidSchSyncObject(*(DXGSYNCOBJECT **)(v56 + 8 * v31), a3[2]);
      v14[v34] = VidSchSyncObject;
      if ( !VidSchSyncObject )
        break;
      v31 = (unsigned int)(v34 + 1);
      if ( (unsigned int)v31 >= a1->ObjectCount )
        goto LABEL_69;
    }
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 6048;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"0x%x object adapter state has been destroyed, so it cannot be waited on.",
      a1->ObjectHandleArray[v32],
      0,
      0,
      0,
      0);
    goto LABEL_59;
  }
LABEL_69:
  DXGPOINTERARRAYORDEREDACQUIRE<DXGSYNCOBJECT,&void AcquireSyncObjectMutex(DXGSYNCOBJECT *),&void ReleaseSyncObjectMutex(DXGSYNCOBJECT *),2>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGSYNCOBJECT,&void AcquireSyncObjectMutex(DXGSYNCOBJECT *),&void ReleaseSyncObjectMutex(DXGSYNCOBJECT *),2>(v62);
LABEL_70:
  if ( Event )
    ObfReferenceObject(Event);
  v7 = VIDSCH_EXPORT::VidSchSubmitWaitFromCpu(
         *((VIDSCH_EXPORT **)a3[2] + 92),
         a1->ObjectCount,
         v14,
         a1->FenceValueArray,
         v8,
         *(_BYTE *)&a1->Flags.0 & 1,
         v58 == 0,
         a3[100],
         v58);
  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    McTemplateK0pqPR1XR1pq_EtwWriteTransfer(
      v36,
      v35,
      v37,
      (_DWORD)a3,
      a1->ObjectCount,
      (__int64)v14,
      (__int64)a1->FenceValueArray,
      (char)a1->hAsyncEvent,
      a1->Flags.Value);
  if ( P != v43 && P )
    ExFreePoolWithTag(P, 0);
  P = 0;
  v44 = 0;
  if ( v45 != v46 && v45 )
    ExFreePoolWithTag(v45, 0);
  v45 = 0;
  v47 = 0;
  DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v51);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v64);
  DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)&v48);
  if ( v7 < 0 )
  {
    if ( Event )
      ObfDereferenceObject(Event);
LABEL_84:
    if ( !v8 )
      goto LABEL_95;
    goto LABEL_94;
  }
  if ( v8 )
  {
    v38 = Event;
    if ( v8 == Event )
    {
      do
      {
        v39 = KeWaitForSingleObject(v8, Executive, 0, 1u, 0);
        if ( PsIsThreadTerminating(KeGetCurrentThread()) )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 6111;
          v7 = -1073741130;
          goto LABEL_94;
        }
        v7 = v39;
      }
      while ( v39 == 257 );
      if ( v39 >= 0 )
        goto LABEL_98;
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 6120;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"Failed to wait for event!", 6120, 0, 0, 0, 0);
LABEL_94:
      KeSetEvent(v8, 0, 0);
      ObfDereferenceObject(v8);
LABEL_95:
      if ( Pool2 )
        ExFreePoolWithTag((PVOID)Pool2, 0x4B677844u);
      return (unsigned int)v7;
    }
  }
  else
  {
LABEL_98:
    v38 = Event;
  }
  if ( v38 )
    ObfDereferenceObject(v38);
  return 0;
}

```

## disassembly

```asm
0x14034c010  push    rbp
0x14034c012  push    rbx
0x14034c013  push    rsi
0x14034c014  push    rdi
0x14034c015  push    r12
0x14034c017  push    r13
0x14034c019  push    r14
0x14034c01b  push    r15
0x14034c01d  lea     rbp, [rsp-138h]
0x14034c025  sub     rsp, 238h
0x14034c02c  mov     rax, cs:__security_cookie
0x14034c033  xor     rax, rsp
0x14034c036  mov     [rbp+170h+var_50], rax
0x14034c03d  mov     rdi, rcx
0x14034c040  mov     [rbp+170h+var_160], r9
0x14034c044  xor     r15d, r15d
0x14034c047  mov     [rbp+170h+var_190], rdx
0x14034c04b  lea     rcx, [rbp+170h+var_1B8]; this
0x14034c04f  mov     [rbp+170h+Event], r15
0x14034c053  mov     [rbp+170h+var_1B0], r15b
0x14034c057  mov     r14, r9
0x14034c05a  mov     rsi, r8
0x14034c05d  mov     [rbp+170h+var_1B8], r8
0x14034c061  call    ?Acquire@DXGDEVICEACCESSLOCKSHARED@@QEAAXXZ; DXGDEVICEACCESSLOCKSHARED::Acquire(void)
0x14034c066  xor     r8d, r8d
0x14034c069  mov     byte ptr [rsp+270h+Object], r15b
0x14034c06e  mov     rdx, rsi
0x14034c071  lea     rcx, [rbp+170h+var_F0]
0x14034c078  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x14034c07d  xor     edx, edx; char *
0x14034c07f  lea     rcx, [rbp+170h+var_F0]; this
0x14034c086  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x14034c08b  mov     ebx, eax
0x14034c08d  test    eax, eax
0x14034c08f  jns     short loc_14034C0AB
0x14034c091  lea     rcx, [rbp+170h+var_F0]; this
0x14034c098  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x14034c09d  lea     rcx, [rbp+170h+var_1B8]; this
0x14034c0a1  call    ??1DXGDEVICEACCESSLOCKSHARED@@QEAA@XZ; DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED(void)
0x14034c0a6  jmp     loc_14034CAED
0x14034c0ab  mov     r12, r15
0x14034c0ae  mov     r13, r15
0x14034c0b1  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14034c0b6  mov     rdx, rax; struct DXGGLOBAL *
0x14034c0b9  lea     rcx, [rbp+170h+var_1A0]; this
0x14034c0bd  xor     r8d, r8d; bool
0x14034c0c0  call    ??0DXGSYNCOBJECTLOCK@@QEAA@QEAVDXGGLOBAL@@_N@Z; DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK(DXGGLOBAL * const,bool)
0x14034c0c5  lea     rcx, [rbp+170h+var_1A0]; this
0x14034c0c9  call    ?AcquireShared@DXGSYNCOBJECTLOCK@@QEAAXXZ; DXGSYNCOBJECTLOCK::AcquireShared(void)
0x14034c0ce  mov     rbx, [rbp+170h+var_190]
0x14034c0d2  mov     [rbp+170h+var_1E8], r15
0x14034c0d6  mov     [rbp+170h+var_1C0], r15d
0x14034c0da  mov     [rsp+270h+P], r15
0x14034c0df  mov     [rbp+170h+var_1F0], r15d
0x14034c0e3  test    r14, r14
0x14034c0e6  jnz     loc_14034C38A
0x14034c0ec  mov     rcx, rbx; this
0x14034c0ef  call    ?IsNativeWslProcess@DXGPROCESS@@QEBAEXZ; DXGPROCESS::IsNativeWslProcess(void)
0x14034c0f4  test    al, al
0x14034c0f6  jz      loc_14034C1FE
0x14034c0fc  cmp     [rdi+18h], r15
0x14034c100  jz      loc_14034C1FE
0x14034c106  lea     edx, [r14+28h]
0x14034c10a  mov     r8d, 4B677844h
0x14034c110  lea     ecx, [rdx+18h]
0x14034c113  call    cs:__imp_ExAllocatePool2
0x14034c11a  nop     dword ptr [rax+rax+00h]
0x14034c11f  mov     r13, rax
0x14034c122  test    rax, rax
0x14034c125  jnz     loc_14034C1DB
0x14034c12b  lea     ecx, [rax+6]
0x14034c12e  call    cs:__imp_WdLogSingleEntry0
0x14034c135  nop     dword ptr [rax+rax+00h]
0x14034c13a  mov     [rsp+270h+var_230], r15
0x14034c13f  lea     r9, aFailedToAlloca_158; "Failed to allocate memory for DXG_SIGNA"...
0x14034c146  mov     [rsp+270h+var_238], r15
0x14034c14b  mov     eax, 16EEh
0x14034c150  mov     qword ptr [rsp+270h+var_240], r15
0x14034c155  or      r8d, 0FFFFFFFFh
0x14034c159  mov     [rsp+270h+HandleInformation], r15
0x14034c15e  mov     edx, 40001h
0x14034c163  xor     ecx, ecx
0x14034c165  mov     [rsp+270h+Object], rax
0x14034c16a  mov     cs:WdLogGlobalForLineNumber, eax
0x14034c170  call    DxgkLogInternalTriageEvent
0x14034c175  mov     ebx, 0C0000017h
0x14034c17a  mov     rcx, [rsp+270h+P]; P
0x14034c17f  lea     rax, [rsp+270h+var_210]
0x14034c184  cmp     rcx, rax
0x14034c187  jz      short loc_14034C19C
0x14034c189  test    rcx, rcx
0x14034c18c  jz      short loc_14034C19C
0x14034c18e  xor     edx, edx; Tag
0x14034c190  call    cs:__imp_ExFreePoolWithTag
0x14034c197  nop     dword ptr [rax+rax+00h]
0x14034c19c  mov     rcx, [rbp+170h+var_1E8]; P
0x14034c1a0  lea     rax, [rbp+170h+var_1E0]
0x14034c1a4  mov     [rbp+170h+var_1F0], r15d
0x14034c1a8  mov     [rsp+270h+P], r15
0x14034c1ad  cmp     rcx, rax
0x14034c1b0  jz      short loc_14034C1C5
0x14034c1b2  test    rcx, rcx
0x14034c1b5  jz      short loc_14034C1C5
0x14034c1b7  xor     edx, edx; Tag
0x14034c1b9  call    cs:__imp_ExFreePoolWithTag
0x14034c1c0  nop     dword ptr [rax+rax+00h]
0x14034c1c5  lea     rcx, [rbp+170h+var_1A0]; this
0x14034c1c9  mov     [rbp+170h+var_1E8], r15
0x14034c1cd  mov     [rbp+170h+var_1C0], r15d
0x14034c1d1  call    ??1DXGSYNCOBJECTLOCK@@QEAA@XZ; DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK(void)
0x14034c1d6  jmp     loc_14034C091
0x14034c1db  mov     rax, [rdi+18h]
0x14034c1df  mov     rcx, r13; struct DXG_SIGNAL_GUEST_CPU_EVENT *
0x14034c1e2  mov     [r13+8], rax
0x14034c1e6  mov     [rbp+170h+var_160], r13
0x14034c1ea  mov     byte ptr [r13+10h], 1
0x14034c1ef  mov     byte ptr [r13+13h], 1
0x14034c1f4  call    ?AcquireReference@DXG_SIGNAL_GUEST_CPU_EVENT@@SAXPEAU1@@Z; DXG_SIGNAL_GUEST_CPU_EVENT::AcquireReference(DXG_SIGNAL_GUEST_CPU_EVENT *)
0x14034c1f9  jmp     loc_14034C38A
0x14034c1fe  mov     rcx, [rdi+18h]; Handle
0x14034c202  test    rcx, rcx
0x14034c205  jz      loc_14034C2E2
0x14034c20b  mov     r8, cs:ExEventObjectType
0x14034c212  lea     rax, [rbp+170h+var_168]
0x14034c216  mov     [rsp+270h+HandleInformation], r15; HandleInformation
0x14034c21b  mov     r9b, 1; AccessMode
0x14034c21e  mov     edx, 2; DesiredAccess
0x14034c223  mov     [rbp+170h+var_168], r15
0x14034c227  mov     [rsp+270h+Object], rax; Object
0x14034c22c  mov     r8, [r8]; ObjectType
0x14034c22f  call    cs:__imp_ObReferenceObjectByHandle
0x14034c236  nop     dword ptr [rax+rax+00h]
0x14034c23b  mov     r12, [rbp+170h+var_168]
0x14034c23f  movsxd  rbx, eax
0x14034c242  test    eax, eax
0x14034c244  jns     loc_14034C386
0x14034c24a  mov     rdx, [rdi+18h]
0x14034c24e  mov     r8, rbx
0x14034c251  mov     ecx, 3
0x14034c256  call    cs:__imp_WdLogSingleEntry2
0x14034c25d  nop     dword ptr [rax+rax+00h]
0x14034c262  mov     cs:WdLogGlobalForLineNumber, 1706h
0x14034c26c  mov     rcx, [rsp+270h+P]; P
0x14034c271  lea     rax, [rsp+270h+var_210]
0x14034c276  cmp     rcx, rax
0x14034c279  jz      short loc_14034C28E
0x14034c27b  test    rcx, rcx
0x14034c27e  jz      short loc_14034C28E
0x14034c280  xor     edx, edx; Tag
0x14034c282  call    cs:__imp_ExFreePoolWithTag
0x14034c289  nop     dword ptr [rax+rax+00h]
0x14034c28e  mov     rcx, [rbp+170h+var_1E8]; P
0x14034c292  lea     rax, [rbp+170h+var_1E0]
0x14034c296  mov     [rbp+170h+var_1F0], r15d
0x14034c29a  mov     [rsp+270h+P], r15
0x14034c29f  cmp     rcx, rax
0x14034c2a2  jz      short loc_14034C2B7
0x14034c2a4  test    rcx, rcx
0x14034c2a7  jz      short loc_14034C2B7
0x14034c2a9  xor     edx, edx; Tag
0x14034c2ab  call    cs:__imp_ExFreePoolWithTag
0x14034c2b2  nop     dword ptr [rax+rax+00h]
0x14034c2b7  lea     rcx, [rbp+170h+var_1A0]; this
0x14034c2bb  mov     [rbp+170h+var_1E8], r15
0x14034c2bf  mov     [rbp+170h+var_1C0], r15d
0x14034c2c3  call    ??1DXGSYNCOBJECTLOCK@@QEAA@XZ; DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK(void)
0x14034c2c8  lea     rcx, [rbp+170h+var_F0]; this
0x14034c2cf  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x14034c2d4  lea     rcx, [rbp+170h+var_1B8]; this
0x14034c2d8  call    ??1DXGDEVICEACCESSLOCKSHARED@@QEAA@XZ; DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED(void)
0x14034c2dd  jmp     loc_14034C985
0x14034c2e2  mov     rdx, cs:ExEventObjectType
0x14034c2e9  lea     rax, [rbp+170h+Event]
0x14034c2ed  mov     [rsp+270h+var_230], rax
0x14034c2f2  lea     r8, [rbp+170h+var_150]
0x14034c2f6  mov     dword ptr [rsp+270h+var_238], r15d
0x14034c2fb  xorps   xmm0, xmm0
0x14034c2fe  mov     dword ptr [rsp+270h+var_240], r15d
0x14034c303  xor     r9d, r9d
0x14034c306  mov     rdx, [rdx]
0x14034c309  xor     ecx, ecx
0x14034c30b  mov     dword ptr [rsp+270h+HandleInformation], 18h
0x14034c313  mov     [rsp+270h+Object], r15
0x14034c318  mov     [rbp+170h+var_150], 30h ; '0'
0x14034c320  mov     [rbp+170h+var_138], 200h
0x14034c328  mov     [rbp+170h+var_148], r15
0x14034c32c  mov     [rbp+170h+var_140], r15
0x14034c330  movdqu  [rbp+170h+var_130], xmm0
0x14034c335  call    cs:__imp_ObCreateObject
0x14034c33c  nop     dword ptr [rax+rax+00h]
0x14034c341  movsxd  rbx, eax
0x14034c344  test    eax, eax
0x14034c346  jns     short loc_14034C36B
0x14034c348  mov     rdx, rbx
0x14034c34b  mov     ecx, 3
0x14034c350  call    cs:__imp_WdLogSingleEntry1
0x14034c357  nop     dword ptr [rax+rax+00h]
0x14034c35c  mov     cs:WdLogGlobalForLineNumber, 171Ah
0x14034c366  jmp     loc_14034C17A
0x14034c36b  mov     rcx, [rbp+170h+Event]; Event
0x14034c36f  xor     r8d, r8d; State
0x14034c372  lea     edx, [r8+1]; Type
0x14034c376  call    cs:__imp_KeInitializeEvent
0x14034c37d  nop     dword ptr [rax+rax+00h]
0x14034c382  mov     r12, [rbp+170h+Event]
0x14034c386  mov     rbx, [rbp+170h+var_190]
0x14034c38a  mov     edx, [rdi+4]
0x14034c38d  lea     rcx, [rbp+170h+var_1E8]
0x14034c391  call    ?AllocateElements@?$NonPagedPoolZeroedArray@PEAU_VIDSCH_SYNC_OBJECT@@$03$0ELGHHIEE@@@QEAAPEAPEAU_VIDSCH_SYNC_OBJECT@@I@Z; NonPagedPoolZeroedArray<_VIDSCH_SYNC_OBJECT *,4,1265072196>::AllocateElements(uint)
0x14034c396  mov     [rbp+170h+var_158], rax
0x14034c39a  mov     r15, rax
0x14034c39d  test    rax, rax
0x14034c3a0  jnz     short loc_14034C3AF
0x14034c3a2  mov     ebx, 0C0000017h
0x14034c3a7  xor     r15d, r15d
0x14034c3aa  jmp     loc_14034C26C
0x14034c3af  or      r14d, 0FFFFFFFFh
0x14034c3b3  test    dword ptr [rbx+198h], 180h
0x14034c3bd  jz      short loc_14034C403
0x14034c3bf  test    rsi, rsi
0x14034c3c2  jz      short loc_14034C403
0x14034c3c4  cmp     dword ptr [rdi+4], 1
0x14034c3c8  jnz     short loc_14034C403
0x14034c3ca  mov     rax, [rdi+8]
0x14034c3ce  cmp     dword ptr [rax], 0
0x14034c3d1  jnz     short loc_14034C403
0x14034c3d3  mov     rcx, [rsi+10h]
0x14034c3d7  lea     r9, [rbp+170h+var_180]; struct VIDMM_PAGING_QUEUE **
0x14034c3db  mov     rdx, [rsi+318h]; struct VIDMM_DEVICE *
0x14034c3e2  xor     r8d, r8d; unsigned int
0x14034c3e5  mov     [rbp+170h+var_180], 0
0x14034c3ed  mov     [rsp+270h+Object], r15; struct _VIDSCH_SYNC_OBJECT **
0x14034c3f2  mov     rcx, [rcx+2F8h]; this
0x14034c3f9  call    ?VidMmGetDevicePagingQueue@VIDMM_EXPORT@@QEAAXPEAVVIDMM_DEVICE@@IPEAPEAUVIDMM_PAGING_QUEUE@@PEAPEAU_VIDSCH_SYNC_OBJECT@@@Z; VIDMM_EXPORT::VidMmGetDevicePagingQueue(VIDMM_DEVICE *,uint,VIDMM_PAGING_QUEUE * *,_VIDSCH_SYNC_OBJECT * *)
0x14034c3fe  jmp     loc_14034C857
0x14034c403  mov     edx, [rdi+4]
0x14034c406  lea     rcx, [rsp+270h+P]
0x14034c40b  call    ?AllocateElements@?$PagedPoolZeroedArray@PEAVDXGSYNCOBJECT@@$03@@QEAAPEAPEAVDXGSYNCOBJECT@@I@Z; PagedPoolZeroedArray<DXGSYNCOBJECT *,4>::AllocateElements(uint)
0x14034c410  mov     [rbp+170h+var_170], rax
0x14034c414  test    rax, rax
0x14034c417  jz      short loc_14034C3A2
0x14034c419  mov     r8d, [rdi+4]
0x14034c41d  xor     ecx, ecx
0x14034c41f  mov     [rbp+170h+var_188], ecx
0x14034c422  test    r8d, r8d
0x14034c425  jz      loc_14034C63F
0x14034c42b  lea     rdx, [rbx+0F8h]
0x14034c432  mov     [rbp+170h+var_180], rdx
0x14034c436  mov     rax, [rdi+8]
0x14034c43a  mov     r15d, ecx
0x14034c43d  mov     ecx, [rax+rcx*4]
0x14034c440  mov     [rbp+170h+var_178], ecx
0x14034c443  mov     rcx, rdx; this
0x14034c446  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x14034c44b  mov     edx, [rbp+170h+var_178]
0x14034c44e  mov     eax, edx
0x14034c450  shr     eax, 6
0x14034c453  and     eax, 0FFFFFFh
0x14034c458  cmp     eax, [rbx+128h]
0x14034c45e  jnb     loc_14034C4EA
0x14034c464  mov     rbx, [rbx+118h]
0x14034c46b  mov     r8d, eax
0x14034c46e  add     r8, r8
0x14034c471  shr     edx, 19h
0x14034c474  and     edx, 60h
0x14034c477  mov     ecx, [rbx+r8*8+8]
0x14034c47c  mov     eax, ecx
0x14034c47e  and     eax, 60h
0x14034c481  cmp     dl, al
0x14034c483  jnz     short loc_14034C4EA
0x14034c485  bt      ecx, 0Dh
0x14034c489  jb      short loc_14034C4EA
0x14034c48b  and     ecx, 1Fh
0x14034c48e  jz      short loc_14034C4EA
0x14034c490  cmp     ecx, 0Bh
0x14034c493  jz      short loc_14034C4E4
0x14034c495  mov     ecx, 2
0x14034c49a  call    cs:__imp_WdLogSingleEntry0
0x14034c4a1  nop     dword ptr [rax+rax+00h]
0x14034c4a6  xor     ebx, ebx
0x14034c4a8  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x14034c4af  mov     [rsp+270h+var_230], rbx
0x14034c4b4  mov     eax, 13Eh
0x14034c4b9  mov     [rsp+270h+var_238], rbx
0x14034c4be  mov     r8d, r14d
0x14034c4c1  mov     qword ptr [rsp+270h+var_240], rbx
0x14034c4c6  mov     edx, 40000h
0x14034c4cb  mov     [rsp+270h+HandleInformation], rbx
0x14034c4d0  xor     ecx, ecx
0x14034c4d2  mov     [rsp+270h+Object], rax
0x14034c4d7  mov     cs:WdLogGlobalForLineNumber, eax
0x14034c4dd  call    DxgkLogInternalTriageEvent
0x14034c4e2  jmp     short loc_14034C4EC
0x14034c4e4  mov     rbx, [rbx+r8*8]
0x14034c4e8  jmp     short loc_14034C4EC
0x14034c4ea  xor     ebx, ebx
0x14034c4ec  mov     rax, [rbp+170h+var_180]
0x14034c4f0  xor     edx, edx
0x14034c4f2  mov     rcx, rax
0x14034c4f5  lock dec dword ptr [rax+10h]
  ... truncated ...
```
