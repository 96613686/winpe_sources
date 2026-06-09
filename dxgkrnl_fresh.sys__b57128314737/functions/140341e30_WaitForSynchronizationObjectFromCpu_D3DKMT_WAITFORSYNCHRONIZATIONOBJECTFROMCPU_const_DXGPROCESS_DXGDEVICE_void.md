# WaitForSynchronizationObjectFromCpu(_D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU const *,DXGPROCESS *,DXGDEVICE *,void *)

- ea: `0x140341e30`
- end: `0x14034294c`
- name: `?WaitForSynchronizationObjectFromCpu@@YAJPEBU_D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU@@PEAVDXGPROCESS@@PEAVDXGDEVICE@@PEAX@Z`
- size: `2844`
- prototype: `__int64 __fastcall(const struct _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU *, struct DXGPROCESS *, struct DXGDEVICE *, void *)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x14034159c`

## callees

- `0x140012540`
- `0x140015b30`
- `0x140018054`
- `0x14001b9c0`
- `0x14001d1a0`
- `0x14001e43c`
- `0x14001f2f0`
- `0x14001fa40`
- `0x1400203d0`
- `0x140030850`
- `0x140030a30`
- `0x140033da4`
- `0x140036ea8`
- `0x140037c6c`
- `0x140037f20`
- `0x140038ea8`
- `0x140048a5c`
- `0x14004d064`
- `0x140054bd0`
- `0x1400a0bd0`
- `0x14019d0b0`
- `0x1403345d0`
- `0x140336360`
- `0x140341e30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140342325`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140342325`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341fb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341fd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403420a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403420cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140342731`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034275a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140342901`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341fb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140341fd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403420a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403420cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140342731`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034275a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140342901`
- `ntoskrnl!ExAllocatePool2` at `0x140341f33`
- `ntoskrnl!ExAllocatePool2` at `0x140341f33`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140342319`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140342319`
- `ntoskrnl!KeInitializeEvent` at `0x140342196`
- `ntoskrnl!KeInitializeEvent` at `0x140342196`
- `ntoskrnl!ObfDereferenceObject` at `0x140342799`
- `ntoskrnl!ObfDereferenceObject` at `0x1403428e8`
- `ntoskrnl!ObfDereferenceObject` at `0x14034291a`
- `ntoskrnl!ObfDereferenceObject` at `0x140342799`
- `ntoskrnl!ObfDereferenceObject` at `0x1403428e8`
- `ntoskrnl!ObfDereferenceObject` at `0x14034291a`
- `ntoskrnl!ObfReferenceObject` at `0x140342680`
- `ntoskrnl!ObfReferenceObject` at `0x140342680`
- `ntoskrnl!ExEventObjectType` at `0x14034202b`
- `ntoskrnl!ExEventObjectType` at `0x140342102`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14034204f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14034204f`
- `ntoskrnl!PsIsThreadTerminating` at `0x140342842`
- `ntoskrnl!PsIsThreadTerminating` at `0x140342842`
- `ntoskrnl!ObCreateObject` at `0x140342155`
- `ntoskrnl!ObCreateObject` at `0x140342155`
- `ntoskrnl!KeSetEvent` at `0x1403428d9`
- `ntoskrnl!KeSetEvent` at `0x1403428d9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14034282b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14034282b`
- `watchdog!WdLogSingleEntry4` at `0x1403425d2`
- `watchdog!WdLogSingleEntry4` at `0x1403425d2`
- `watchdog!WdLogSingleEntry2` at `0x140342076`
- `watchdog!WdLogSingleEntry2` at `0x140342076`
- `watchdog!WdLogSingleEntry3` at `0x1403424e8`
- `watchdog!WdLogSingleEntry3` at `0x1403424e8`
- `watchdog!WdLogSingleEntry0` at `0x140341f4e`
- `watchdog!WdLogSingleEntry0` at `0x1403422ba`
- `watchdog!WdLogSingleEntry0` at `0x140342486`
- `watchdog!WdLogSingleEntry0` at `0x140342869`
- `watchdog!WdLogSingleEntry0` at `0x1403428b6`
- `watchdog!WdLogSingleEntry0` at `0x140341f4e`
- `watchdog!WdLogSingleEntry0` at `0x1403422ba`
- `watchdog!WdLogSingleEntry0` at `0x140342486`
- `watchdog!WdLogSingleEntry0` at `0x140342869`
- `watchdog!WdLogSingleEntry0` at `0x1403428b6`
- `watchdog!WdLogSingleEntry1` at `0x140342170`
- `watchdog!WdLogSingleEntry1` at `0x1403423d3`
- `watchdog!WdLogSingleEntry1` at `0x140342419`
- `watchdog!WdLogSingleEntry1` at `0x140342555`
- `watchdog!WdLogSingleEntry1` at `0x1403427c0`
- `watchdog!WdLogSingleEntry1` at `0x140342170`
- `watchdog!WdLogSingleEntry1` at `0x1403423d3`
- `watchdog!WdLogSingleEntry1` at `0x140342419`
- `watchdog!WdLogSingleEntry1` at `0x140342555`
- `watchdog!WdLogSingleEntry1` at `0x1403427c0`

## string_xrefs

- `0x14034256b`: `0x%I64x object is opened as signal only and thus cannot be waited on.`

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
  int v14; // eax
  struct _VIDSCH_SYNC_OBJECT **v15; // r15
  struct ADAPTER_RENDER *v16; // rcx
  struct VIDMM_DEVICE *v17; // rdx
  __int64 v18; // rax
  __int64 ObjectCount; // r8
  __int64 v20; // rcx
  DXGPUSHLOCK *v21; // rdx
  __int64 v22; // r15
  unsigned int v23; // eax
  __int64 v24; // rbx
  int v25; // ecx
  __int64 v26; // rbx
  struct VIDMM_PAGING_QUEUE *v27; // rcx
  struct ADAPTER_RENDER **v28; // r8
  __int64 v29; // rax
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
  PRKEVENT Event; // [rsp+C8h] [rbp-38h]
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
        WdLogGlobalForLineNumber = 5980;
        DxgkLogInternalTriageEvent(
          0,
          262145,
          -1,
          (unsigned int)L"Failed to allocate memory for DXG_SIGNAL_GUEST_CPU_EVENT",
          5980,
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
          WdLogSingleEntry2(3, a1->hAsyncEvent, v13);
          WdLogGlobalForLineNumber = 6004;
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
        v14 = ObCreateObject(0, ExEventObjectType, v60);
        v7 = v14;
        if ( v14 < 0 )
        {
          WdLogSingleEntry1(3, v14);
          WdLogGlobalForLineNumber = 6024;
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
  v15 = v59;
  if ( !v59 )
    goto LABEL_25;
  if ( (*((_DWORD *)v11 + 102) & 0x180) != 0 && a3 && a1->ObjectCount == 1 && !*a1->ObjectHandleArray )
  {
    v16 = a3[2];
    v17 = a3[99];
    i = 0;
    VIDMM_EXPORT::VidMmGetDevicePagingQueue(*((VIDMM_EXPORT **)v16 + 95), v17, 0, &i, v59);
    goto LABEL_70;
  }
  v18 = PagedPoolZeroedArray<DXGSYNCOBJECT *,4>::AllocateElements(&P, a1->ObjectCount);
  v56 = v18;
  if ( !v18 )
  {
LABEL_25:
    v7 = -1073741801;
    goto LABEL_13;
  }
  ObjectCount = a1->ObjectCount;
  v20 = 0;
  v53 = 0;
  if ( (_DWORD)ObjectCount )
  {
    v21 = (DXGPROCESS *)((char *)v11 + 248);
    for ( i = (DXGPROCESS *)((char *)v11 + 248); ; v21 = i )
    {
      v22 = (unsigned int)v20;
      v55 = a1->ObjectHandleArray[v20];
      DXGPUSHLOCK::AcquireShared(v21);
      v23 = (v55 >> 6) & 0xFFFFFF;
      if ( v23 < *((_DWORD *)v11 + 74)
        && (v24 = *((_QWORD *)v11 + 35), ((v55 >> 25) & 0x60) == (*(_BYTE *)(v24 + 16LL * v23 + 8) & 0x60))
        && (*(_DWORD *)(v24 + 16LL * v23 + 8) & 0x2000) == 0
        && (v25 = *(_DWORD *)(v24 + 16LL * v23 + 8) & 0x1F) != 0 )
      {
        if ( v25 == 11 )
        {
          v26 = *(_QWORD *)(v24 + 16LL * v23);
        }
        else
        {
          WdLogSingleEntry0(2);
          v26 = 0;
          WdLogGlobalForLineNumber = 318;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        }
      }
      else
      {
        v26 = 0;
      }
      v27 = i;
      _InterlockedDecrement((volatile signed __int32 *)i + 4);
      ExReleasePushLockSharedEx(v27, 0);
      KeLeaveCriticalRegion();
      if ( !v26 )
        break;
      if ( (*(_DWORD *)(v26 + 72) & 0x20) != 0 )
      {
        WdLogSingleEntry1(2, a1->ObjectHandleArray[v22]);
        WdLogGlobalForLineNumber = 6085;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"0x%I64x object is opened as signal only and thus cannot be waited on.",
          a1->ObjectHandleArray[v22],
          0,
          0,
          0,
          0);
        v7 = -1073741790;
        goto LABEL_13;
      }
      v28 = *(struct ADAPTER_RENDER ***)(v26 + 16);
      if ( v28 != a3 )
      {
        WdLogSingleEntry3(2, a1->ObjectHandleArray[v22], v28, a3);
        WdLogGlobalForLineNumber = 6097;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"0x%x object belongs to a different device 0x%p that 0x%p passed to the wait from CPU call.",
          a1->ObjectHandleArray[v22],
          *(_QWORD *)(v26 + 16),
          (__int64)a3,
          0,
          0);
        goto LABEL_61;
      }
      IsNativeFenceOpenedAsMonitoredFence = DXGSYNCOBJECT::IsNativeFenceOpenedAsMonitoredFence(
                                              *(DXGSYNCOBJECT **)(v26 + 32),
                                              v28[2]);
      if ( !*((_BYTE *)DXGGLOBAL::GetGlobal() + 305952)
        && *(_DWORD *)(*(_QWORD *)(v26 + 32) + 420LL) == 7
        && !*(_QWORD *)(v26 + 96)
        && !IsNativeFenceOpenedAsMonitoredFence )
      {
        WdLogSingleEntry1(2, v26);
        WdLogGlobalForLineNumber = 6111;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"DXGDEVICESYNCOBJECT 0x%x is a native fence object and has a NULL Driver Handle, returning STATUS"
                         "_INVALID_PARAMETER",
          v26,
          0,
          0,
          0,
          0);
LABEL_61:
        v7 = -1073741811;
        goto LABEL_13;
      }
      v29 = *(_QWORD *)(v26 + 32);
      if ( *(_DWORD *)(v29 + 420) == 7 && *(_DWORD *)(v29 + 316) == 1 )
      {
        WdLogSingleEntry1(2, v26);
        WdLogGlobalForLineNumber = 6120;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"DXGDEVICESYNCOBJECT 0x%x. Queuing Wait/Signals not supported on native fence of type D3DDDI_NATI"
                         "VEFENCE_TYPE_INTRA_GPU, returning STATUS_INVALID_PARAMETER",
          v26,
          0,
          0,
          0,
          0);
        goto LABEL_61;
      }
      *(_QWORD *)(v56 + 8 * v22) = v29;
      ObjectCount = a1->ObjectCount;
      v20 = (unsigned int)(v53 + 1);
      v53 = v20;
      if ( (unsigned int)v20 >= (unsigned int)ObjectCount )
      {
        v15 = v59;
        v18 = v56;
        goto LABEL_56;
      }
      v11 = v52;
    }
    v7 = -1073741811;
    v30 = v52;
    WdLogSingleEntry4(2, v52, a1->ObjectHandleArray[v22]);
    WdLogGlobalForLineNumber = 6077;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"0x%I64x passed an invalid wait for hSyncObject 0x%I64x at index %I64d returning 0x%I64x",
      (__int64)v30,
      a1->ObjectHandleArray[v22],
      v22,
      -1073741811,
      0);
    goto LABEL_13;
  }
LABEL_56:
  DXGPOINTERARRAYORDEREDACQUIRE<DXGSYNCOBJECT,&void AcquireSyncObjectMutex(DXGSYNCOBJECT *),&void ReleaseSyncObjectMutex(DXGSYNCOBJECT *),2>::DXGPOINTERARRAYORDEREDACQUIRE<DXGSYNCOBJECT,&void AcquireSyncObjectMutex(DXGSYNCOBJECT *),&void ReleaseSyncObjectMutex(DXGSYNCOBJECT *),2>(
    v62,
    v18,
    ObjectCount);
  if ( v63 )
  {
    if ( !v62[0] )
    {
      v7 = -1073741801;
      goto LABEL_65;
    }
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 6145;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"The same sync object handle is passed twice",
      6145,
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
      v15[v34] = VidSchSyncObject;
      if ( !VidSchSyncObject )
        break;
      v31 = (unsigned int)(v34 + 1);
      if ( (unsigned int)v31 >= a1->ObjectCount )
        goto LABEL_69;
    }
    WdLogSingleEntry1(2, a1->ObjectHandleArray[v34]);
    WdLogGlobalForLineNumber = 6158;
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
         v15,
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
      (__int64)v15,
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
          WdLogGlobalForLineNumber = 6221;
          v7 = -1073741130;
          goto LABEL_94;
        }
        v7 = v39;
      }
      while ( v39 == 257 );
      if ( v39 >= 0 )
        goto LABEL_98;
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 6230;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"Failed to wait for event!", 6230, 0, 0, 0, 0);
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
0x140341e30  push    rbp
0x140341e32  push    rbx
0x140341e33  push    rsi
0x140341e34  push    rdi
0x140341e35  push    r12
0x140341e37  push    r13
0x140341e39  push    r14
0x140341e3b  push    r15
0x140341e3d  lea     rbp, [rsp-138h]
0x140341e45  sub     rsp, 238h
0x140341e4c  mov     rax, cs:__security_cookie
0x140341e53  xor     rax, rsp
0x140341e56  mov     [rbp+170h+var_50], rax
0x140341e5d  mov     rdi, rcx
0x140341e60  mov     [rbp+170h+var_160], r9
0x140341e64  xor     r15d, r15d
0x140341e67  mov     [rbp+170h+var_190], rdx
0x140341e6b  lea     rcx, [rbp+170h+var_1B8]; this
0x140341e6f  mov     [rbp+170h+Event], r15
0x140341e73  mov     [rbp+170h+var_1B0], r15b
0x140341e77  mov     r14, r9
0x140341e7a  mov     rsi, r8
0x140341e7d  mov     [rbp+170h+var_1B8], r8
0x140341e81  call    ?Acquire@DXGDEVICEACCESSLOCKSHARED@@QEAAXXZ; DXGDEVICEACCESSLOCKSHARED::Acquire(void)
0x140341e86  xor     r8d, r8d
0x140341e89  mov     byte ptr [rsp+270h+Object], r15b
0x140341e8e  mov     rdx, rsi
0x140341e91  lea     rcx, [rbp+170h+var_F0]
0x140341e98  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x140341e9d  xor     edx, edx; char *
0x140341e9f  lea     rcx, [rbp+170h+var_F0]; this
0x140341ea6  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x140341eab  mov     ebx, eax
0x140341ead  test    eax, eax
0x140341eaf  jns     short loc_140341ECB
0x140341eb1  lea     rcx, [rbp+170h+var_F0]; this
0x140341eb8  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x140341ebd  lea     rcx, [rbp+170h+var_1B8]; this
0x140341ec1  call    ??1DXGDEVICEACCESSLOCKSHARED@@QEAA@XZ; DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED(void)
0x140341ec6  jmp     loc_14034290D
0x140341ecb  mov     r12, r15
0x140341ece  mov     r13, r15
0x140341ed1  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140341ed6  mov     rdx, rax; struct DXGGLOBAL *
0x140341ed9  lea     rcx, [rbp+170h+var_1A0]; this
0x140341edd  xor     r8d, r8d; bool
0x140341ee0  call    ??0DXGSYNCOBJECTLOCK@@QEAA@QEAVDXGGLOBAL@@_N@Z; DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK(DXGGLOBAL * const,bool)
0x140341ee5  lea     rcx, [rbp+170h+var_1A0]; this
0x140341ee9  call    ?AcquireShared@DXGSYNCOBJECTLOCK@@QEAAXXZ; DXGSYNCOBJECTLOCK::AcquireShared(void)
0x140341eee  mov     rbx, [rbp+170h+var_190]
0x140341ef2  mov     [rbp+170h+var_1E8], r15
0x140341ef6  mov     [rbp+170h+var_1C0], r15d
0x140341efa  mov     [rsp+270h+P], r15
0x140341eff  mov     [rbp+170h+var_1F0], r15d
0x140341f03  test    r14, r14
0x140341f06  jnz     loc_1403421AA
0x140341f0c  mov     rcx, rbx; this
0x140341f0f  call    ?IsNativeWslProcess@DXGPROCESS@@QEBAEXZ; DXGPROCESS::IsNativeWslProcess(void)
0x140341f14  test    al, al
0x140341f16  jz      loc_14034201E
0x140341f1c  cmp     [rdi+18h], r15
0x140341f20  jz      loc_14034201E
0x140341f26  lea     edx, [r14+28h]
0x140341f2a  mov     r8d, 4B677844h
0x140341f30  lea     ecx, [rdx+18h]
0x140341f33  call    cs:__imp_ExAllocatePool2
0x140341f3a  nop     dword ptr [rax+rax+00h]
0x140341f3f  mov     r13, rax
0x140341f42  test    rax, rax
0x140341f45  jnz     loc_140341FFB
0x140341f4b  lea     ecx, [rax+6]
0x140341f4e  call    cs:__imp_WdLogSingleEntry0
0x140341f55  nop     dword ptr [rax+rax+00h]
0x140341f5a  mov     [rsp+270h+var_230], r15
0x140341f5f  lea     r9, aFailedToAlloca_158; "Failed to allocate memory for DXG_SIGNA"...
0x140341f66  mov     [rsp+270h+var_238], r15
0x140341f6b  mov     eax, 175Ch
0x140341f70  mov     qword ptr [rsp+270h+var_240], r15
0x140341f75  or      r8d, 0FFFFFFFFh
0x140341f79  mov     [rsp+270h+HandleInformation], r15
0x140341f7e  mov     edx, 40001h
0x140341f83  xor     ecx, ecx
0x140341f85  mov     [rsp+270h+Object], rax
0x140341f8a  mov     cs:WdLogGlobalForLineNumber, eax
0x140341f90  call    DxgkLogInternalTriageEvent
0x140341f95  mov     ebx, 0C0000017h
0x140341f9a  mov     rcx, [rsp+270h+P]; P
0x140341f9f  lea     rax, [rsp+270h+var_210]
0x140341fa4  cmp     rcx, rax
0x140341fa7  jz      short loc_140341FBC
0x140341fa9  test    rcx, rcx
0x140341fac  jz      short loc_140341FBC
0x140341fae  xor     edx, edx; Tag
0x140341fb0  call    cs:__imp_ExFreePoolWithTag
0x140341fb7  nop     dword ptr [rax+rax+00h]
0x140341fbc  mov     rcx, [rbp+170h+var_1E8]; P
0x140341fc0  lea     rax, [rbp+170h+var_1E0]
0x140341fc4  mov     [rbp+170h+var_1F0], r15d
0x140341fc8  mov     [rsp+270h+P], r15
0x140341fcd  cmp     rcx, rax
0x140341fd0  jz      short loc_140341FE5
0x140341fd2  test    rcx, rcx
0x140341fd5  jz      short loc_140341FE5
0x140341fd7  xor     edx, edx; Tag
0x140341fd9  call    cs:__imp_ExFreePoolWithTag
0x140341fe0  nop     dword ptr [rax+rax+00h]
0x140341fe5  lea     rcx, [rbp+170h+var_1A0]; this
0x140341fe9  mov     [rbp+170h+var_1E8], r15
0x140341fed  mov     [rbp+170h+var_1C0], r15d
0x140341ff1  call    ??1DXGSYNCOBJECTLOCK@@QEAA@XZ; DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK(void)
0x140341ff6  jmp     loc_140341EB1
0x140341ffb  mov     rax, [rdi+18h]
0x140341fff  mov     rcx, r13; struct DXG_SIGNAL_GUEST_CPU_EVENT *
0x140342002  mov     [r13+8], rax
0x140342006  mov     [rbp+170h+var_160], r13
0x14034200a  mov     byte ptr [r13+10h], 1
0x14034200f  mov     byte ptr [r13+13h], 1
0x140342014  call    ?AcquireReference@DXG_SIGNAL_GUEST_CPU_EVENT@@SAXPEAU1@@Z; DXG_SIGNAL_GUEST_CPU_EVENT::AcquireReference(DXG_SIGNAL_GUEST_CPU_EVENT *)
0x140342019  jmp     loc_1403421AA
0x14034201e  mov     rcx, [rdi+18h]; Handle
0x140342022  test    rcx, rcx
0x140342025  jz      loc_140342102
0x14034202b  mov     r8, cs:ExEventObjectType
0x140342032  lea     rax, [rbp+170h+var_168]
0x140342036  mov     [rsp+270h+HandleInformation], r15; HandleInformation
0x14034203b  mov     r9b, 1; AccessMode
0x14034203e  mov     edx, 2; DesiredAccess
0x140342043  mov     [rbp+170h+var_168], r15
0x140342047  mov     [rsp+270h+Object], rax; Object
0x14034204c  mov     r8, [r8]; ObjectType
0x14034204f  call    cs:__imp_ObReferenceObjectByHandle
0x140342056  nop     dword ptr [rax+rax+00h]
0x14034205b  mov     r12, [rbp+170h+var_168]
0x14034205f  movsxd  rbx, eax
0x140342062  test    eax, eax
0x140342064  jns     loc_1403421A6
0x14034206a  mov     rdx, [rdi+18h]
0x14034206e  mov     r8, rbx
0x140342071  mov     ecx, 3
0x140342076  call    cs:__imp_WdLogSingleEntry2
0x14034207d  nop     dword ptr [rax+rax+00h]
0x140342082  mov     cs:WdLogGlobalForLineNumber, 1774h
0x14034208c  mov     rcx, [rsp+270h+P]; P
0x140342091  lea     rax, [rsp+270h+var_210]
0x140342096  cmp     rcx, rax
0x140342099  jz      short loc_1403420AE
0x14034209b  test    rcx, rcx
0x14034209e  jz      short loc_1403420AE
0x1403420a0  xor     edx, edx; Tag
0x1403420a2  call    cs:__imp_ExFreePoolWithTag
0x1403420a9  nop     dword ptr [rax+rax+00h]
0x1403420ae  mov     rcx, [rbp+170h+var_1E8]; P
0x1403420b2  lea     rax, [rbp+170h+var_1E0]
0x1403420b6  mov     [rbp+170h+var_1F0], r15d
0x1403420ba  mov     [rsp+270h+P], r15
0x1403420bf  cmp     rcx, rax
0x1403420c2  jz      short loc_1403420D7
0x1403420c4  test    rcx, rcx
0x1403420c7  jz      short loc_1403420D7
0x1403420c9  xor     edx, edx; Tag
0x1403420cb  call    cs:__imp_ExFreePoolWithTag
0x1403420d2  nop     dword ptr [rax+rax+00h]
0x1403420d7  lea     rcx, [rbp+170h+var_1A0]; this
0x1403420db  mov     [rbp+170h+var_1E8], r15
0x1403420df  mov     [rbp+170h+var_1C0], r15d
0x1403420e3  call    ??1DXGSYNCOBJECTLOCK@@QEAA@XZ; DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK(void)
0x1403420e8  lea     rcx, [rbp+170h+var_F0]; this
0x1403420ef  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1403420f4  lea     rcx, [rbp+170h+var_1B8]; this
0x1403420f8  call    ??1DXGDEVICEACCESSLOCKSHARED@@QEAA@XZ; DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED(void)
0x1403420fd  jmp     loc_1403427A5
0x140342102  mov     rdx, cs:ExEventObjectType
0x140342109  lea     rax, [rbp+170h+Event]
0x14034210d  mov     [rsp+270h+var_230], rax
0x140342112  lea     r8, [rbp+170h+var_150]
0x140342116  mov     dword ptr [rsp+270h+var_238], r15d
0x14034211b  xorps   xmm0, xmm0
0x14034211e  mov     dword ptr [rsp+270h+var_240], r15d
0x140342123  xor     r9d, r9d
0x140342126  mov     rdx, [rdx]
0x140342129  xor     ecx, ecx
0x14034212b  mov     dword ptr [rsp+270h+HandleInformation], 18h
0x140342133  mov     [rsp+270h+Object], r15
0x140342138  mov     [rbp+170h+var_150], 30h ; '0'
0x140342140  mov     [rbp+170h+var_138], 200h
0x140342148  mov     [rbp+170h+var_148], r15
0x14034214c  mov     [rbp+170h+var_140], r15
0x140342150  movdqu  [rbp+170h+var_130], xmm0
0x140342155  call    cs:__imp_ObCreateObject
0x14034215c  nop     dword ptr [rax+rax+00h]
0x140342161  movsxd  rbx, eax
0x140342164  test    eax, eax
0x140342166  jns     short loc_14034218B
0x140342168  mov     rdx, rbx
0x14034216b  mov     ecx, 3
0x140342170  call    cs:__imp_WdLogSingleEntry1
0x140342177  nop     dword ptr [rax+rax+00h]
0x14034217c  mov     cs:WdLogGlobalForLineNumber, 1788h
0x140342186  jmp     loc_140341F9A
0x14034218b  mov     rcx, [rbp+170h+Event]; Event
0x14034218f  xor     r8d, r8d; State
0x140342192  lea     edx, [r8+1]; Type
0x140342196  call    cs:__imp_KeInitializeEvent
0x14034219d  nop     dword ptr [rax+rax+00h]
0x1403421a2  mov     r12, [rbp+170h+Event]
0x1403421a6  mov     rbx, [rbp+170h+var_190]
0x1403421aa  mov     edx, [rdi+4]
0x1403421ad  lea     rcx, [rbp+170h+var_1E8]
0x1403421b1  call    ?AllocateElements@?$NonPagedPoolZeroedArray@PEAU_VIDSCH_SYNC_OBJECT@@$03$0ELGHHIEE@@@QEAAPEAPEAU_VIDSCH_SYNC_OBJECT@@I@Z; NonPagedPoolZeroedArray<_VIDSCH_SYNC_OBJECT *,4,1265072196>::AllocateElements(uint)
0x1403421b6  mov     [rbp+170h+var_158], rax
0x1403421ba  mov     r15, rax
0x1403421bd  test    rax, rax
0x1403421c0  jnz     short loc_1403421CF
0x1403421c2  mov     ebx, 0C0000017h
0x1403421c7  xor     r15d, r15d
0x1403421ca  jmp     loc_14034208C
0x1403421cf  or      r14d, 0FFFFFFFFh
0x1403421d3  test    dword ptr [rbx+198h], 180h
0x1403421dd  jz      short loc_140342223
0x1403421df  test    rsi, rsi
0x1403421e2  jz      short loc_140342223
0x1403421e4  cmp     dword ptr [rdi+4], 1
0x1403421e8  jnz     short loc_140342223
0x1403421ea  mov     rax, [rdi+8]
0x1403421ee  cmp     dword ptr [rax], 0
0x1403421f1  jnz     short loc_140342223
0x1403421f3  mov     rcx, [rsi+10h]
0x1403421f7  lea     r9, [rbp+170h+var_180]; struct VIDMM_PAGING_QUEUE **
0x1403421fb  mov     rdx, [rsi+318h]; struct VIDMM_DEVICE *
0x140342202  xor     r8d, r8d; unsigned int
0x140342205  mov     [rbp+170h+var_180], 0
0x14034220d  mov     [rsp+270h+Object], r15; struct _VIDSCH_SYNC_OBJECT **
0x140342212  mov     rcx, [rcx+2F8h]; this
0x140342219  call    ?VidMmGetDevicePagingQueue@VIDMM_EXPORT@@QEAAXPEAVVIDMM_DEVICE@@IPEAPEAUVIDMM_PAGING_QUEUE@@PEAPEAU_VIDSCH_SYNC_OBJECT@@@Z; VIDMM_EXPORT::VidMmGetDevicePagingQueue(VIDMM_DEVICE *,uint,VIDMM_PAGING_QUEUE * *,_VIDSCH_SYNC_OBJECT * *)
0x14034221e  jmp     loc_140342677
0x140342223  mov     edx, [rdi+4]
0x140342226  lea     rcx, [rsp+270h+P]
0x14034222b  call    ?AllocateElements@?$PagedPoolZeroedArray@PEAVDXGSYNCOBJECT@@$03@@QEAAPEAPEAVDXGSYNCOBJECT@@I@Z; PagedPoolZeroedArray<DXGSYNCOBJECT *,4>::AllocateElements(uint)
0x140342230  mov     [rbp+170h+var_170], rax
0x140342234  test    rax, rax
0x140342237  jz      short loc_1403421C2
0x140342239  mov     r8d, [rdi+4]
0x14034223d  xor     ecx, ecx
0x14034223f  mov     [rbp+170h+var_188], ecx
0x140342242  test    r8d, r8d
0x140342245  jz      loc_14034245F
0x14034224b  lea     rdx, [rbx+0F8h]
0x140342252  mov     [rbp+170h+var_180], rdx
0x140342256  mov     rax, [rdi+8]
0x14034225a  mov     r15d, ecx
0x14034225d  mov     ecx, [rax+rcx*4]
0x140342260  mov     [rbp+170h+var_178], ecx
0x140342263  mov     rcx, rdx; this
0x140342266  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x14034226b  mov     edx, [rbp+170h+var_178]
0x14034226e  mov     eax, edx
0x140342270  shr     eax, 6
0x140342273  and     eax, 0FFFFFFh
0x140342278  cmp     eax, [rbx+128h]
0x14034227e  jnb     loc_14034230A
0x140342284  mov     rbx, [rbx+118h]
0x14034228b  mov     r8d, eax
0x14034228e  add     r8, r8
0x140342291  shr     edx, 19h
0x140342294  and     edx, 60h
0x140342297  mov     ecx, [rbx+r8*8+8]
0x14034229c  mov     eax, ecx
0x14034229e  and     eax, 60h
0x1403422a1  cmp     dl, al
0x1403422a3  jnz     short loc_14034230A
0x1403422a5  bt      ecx, 0Dh
0x1403422a9  jb      short loc_14034230A
0x1403422ab  and     ecx, 1Fh
0x1403422ae  jz      short loc_14034230A
0x1403422b0  cmp     ecx, 0Bh
0x1403422b3  jz      short loc_140342304
0x1403422b5  mov     ecx, 2
0x1403422ba  call    cs:__imp_WdLogSingleEntry0
0x1403422c1  nop     dword ptr [rax+rax+00h]
0x1403422c6  xor     ebx, ebx
0x1403422c8  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x1403422cf  mov     [rsp+270h+var_230], rbx
0x1403422d4  mov     eax, 13Eh
0x1403422d9  mov     [rsp+270h+var_238], rbx
0x1403422de  mov     r8d, r14d
0x1403422e1  mov     qword ptr [rsp+270h+var_240], rbx
0x1403422e6  mov     edx, 40000h
0x1403422eb  mov     [rsp+270h+HandleInformation], rbx
0x1403422f0  xor     ecx, ecx
0x1403422f2  mov     [rsp+270h+Object], rax
0x1403422f7  mov     cs:WdLogGlobalForLineNumber, eax
0x1403422fd  call    DxgkLogInternalTriageEvent
0x140342302  jmp     short loc_14034230C
0x140342304  mov     rbx, [rbx+r8*8]
0x140342308  jmp     short loc_14034230C
0x14034230a  xor     ebx, ebx
0x14034230c  mov     rax, [rbp+170h+var_180]
0x140342310  xor     edx, edx
0x140342312  mov     rcx, rax
0x140342315  lock dec dword ptr [rax+10h]
  ... truncated ...
```
