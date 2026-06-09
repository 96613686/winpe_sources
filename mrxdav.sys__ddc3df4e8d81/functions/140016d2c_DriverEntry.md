# DriverEntry

- ea: `0x140016d2c`
- end: `0x140017303`
- name: `DriverEntry`
- size: `1495`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14002b010`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140006880`
- `0x140006c00`
- `0x140016d2c`
- `0x140017b78`
- `0x140017dfc`
- `0x1400185c0`
- `0x140027ce8`
- `0x1400282d4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001703c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017078`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400170cf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017158`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017202`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400172d4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028f51`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001703c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017078`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400170cf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017158`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017202`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400172d4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028f51`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016ed5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016ed5`
- `ntoskrnl!KeInitializeEvent` at `0x140016dd8`
- `ntoskrnl!KeInitializeEvent` at `0x140016e32`
- `ntoskrnl!KeInitializeEvent` at `0x140016dd8`
- `ntoskrnl!KeInitializeEvent` at `0x140016e32`
- `ntoskrnl!ZwClose` at `0x1400172af`
- `ntoskrnl!ZwClose` at `0x1400172af`
- `ntoskrnl!ExInitializeResourceLite` at `0x140016e1a`
- `ntoskrnl!ExInitializeResourceLite` at `0x140016e5a`
- `ntoskrnl!ExInitializeResourceLite` at `0x140016e82`
- `ntoskrnl!ExInitializeResourceLite` at `0x140016e9b`
- `ntoskrnl!ExInitializeResourceLite` at `0x140016e1a`
- `ntoskrnl!ExInitializeResourceLite` at `0x140016e5a`
- `ntoskrnl!ExInitializeResourceLite` at `0x140016e82`
- `ntoskrnl!ExInitializeResourceLite` at `0x140016e9b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14001711b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14001711b`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400171a0`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400171b3`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400171c6`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400171d9`
- `ntoskrnl!ExDeleteResourceLite` at `0x140028f9c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140028faf`
- `ntoskrnl!ExDeleteResourceLite` at `0x140028fc2`
- `ntoskrnl!ExDeleteResourceLite` at `0x140028fd5`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400171a0`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400171b3`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400171c6`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400171d9`
- `ntoskrnl!ExDeleteResourceLite` at `0x140028f9c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140028faf`
- `ntoskrnl!ExDeleteResourceLite` at `0x140028fc2`
- `ntoskrnl!ExDeleteResourceLite` at `0x140028fd5`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140017010`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140017010`
- `ntoskrnl!KeInitializeSpinLock` at `0x140016deb`
- `ntoskrnl!KeInitializeSpinLock` at `0x140016deb`
- `ntoskrnl!KeInitializeTimerEx` at `0x140016e00`
- `ntoskrnl!KeInitializeTimerEx` at `0x140016e00`
- `rdbss!RxGetRDBSSProcess` at `0x140016da7`
- `rdbss!RxGetRDBSSProcess` at `0x140016da7`
- `rdbss!RxRegisterMinirdr` at `0x140016f18`
- `rdbss!RxRegisterMinirdr` at `0x140016f18`
- `rdbss!RxUnregisterMinirdr` at `0x14001718d`
- `rdbss!RxUnregisterMinirdr` at `0x140028f88`
- `rdbss!RxUnregisterMinirdr` at `0x14001718d`
- `rdbss!RxUnregisterMinirdr` at `0x140028f88`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 v3; // rcx
  int v4; // r15d
  int v5; // ebx
  struct _DEVICE_OBJECT *v6; // rdi
  __int64 v7; // rdi
  HANDLE CurrentThreadId; // rax
  __int64 v9; // rdi
  HANDLE v10; // rax
  __int64 v11; // rdi
  HANDLE v12; // rax
  PRDBSS_DEVICE_OBJECT v13; // rdi
  __int64 v14; // rdi
  HANDLE v15; // rax
  __int64 v16; // rdi
  HANDLE v17; // rax
  __int64 v19; // rdi
  HANDLE v20; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-90h] BYREF
  __int128 v22; // [rsp+58h] [rbp-80h]
  __int128 v23; // [rsp+68h] [rbp-70h]
  __int128 v24; // [rsp+78h] [rbp-60h]
  _BYTE v25[28]; // [rsp+88h] [rbp-50h] BYREF

  DestinationString = 0;
  v24 = 0;
  memset(v25, 0, sizeof(v25));
  v22 = 0;
  v23 = 0;
  MRxDAVInitializeTheTimeValues(DriverObject, RegistryPath);
  if ( (unsigned int)UMRxReadDWORDFromTheRegistry(v3, L"DisableEFSOnWebDav", &DisableEFS) )
    DisableEFS = 0;
  RxGetRDBSSProcess();
  MRxDAVSerializationMutex.Count = 1;
  MRxDAVSerializationMutex.Owner = 0;
  MRxDAVSerializationMutex.Contention = 0;
  KeInitializeEvent(&MRxDAVSerializationMutex.Event, SynchronizationEvent, 0);
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  KeInitializeTimerEx(&DavTimerObject, NotificationTimer);
  TimerThreadShutDown = 0;
  ExInitializeResourceLite(&MRxDAVTimerThreadLock);
  KeInitializeEvent(&TimerThreadEvent, NotificationEvent, 0);
  qword_14000BB58 = (__int64)&LockTokenEntryList;
  LockTokenEntryList = (__int64)&LockTokenEntryList;
  ExInitializeResourceLite(&LockTokenEntryListLock);
  qword_14000BC58 = (__int64)&LockConflictEntryList;
  LockConflictEntryList = &LockConflictEntryList;
  ExInitializeResourceLite(&LockConflictEntryListLock);
  QueueLockRefreshWorkItem = 1;
  ExInitializeResourceLite(&QueueLockRefreshWorkItemLock);
  memset(&DavWinInetCachePath, 0, 0x208u);
  MRxDAVInitializeTables();
  v4 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\WebDavRedirector");
  v5 = RxRegisterMinirdr(
         &g_MRxDAVDeviceObject,
         DriverObject,
         (PMINIRDR_DISPATCH)&WPP_MAIN_CB.DeviceQueue,
         0x42u,
         &DestinationString,
         0x160u,
         0x14u,
         0x10u);
  if ( !v5 )
  {
    v4 = 1;
    *(_QWORD *)&WPP_MAIN_CB.Type = 0;
    WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_MupLog;
    WPP_MAIN_CB.NextDevice = (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceExtension;
    WPP_MAIN_CB.CurrentIrp = 0;
    WPP_MAIN_CB.Timer = (PIO_TIMER)1;
    WPP_MAIN_CB.DeviceExtension = 0;
    *(_QWORD *)&WPP_MAIN_CB.DeviceType = WPP_ThisDir_CTLGUID_RFSMon;
    WPP_MAIN_CB.Queue.ListEntry.Flink = 0;
    *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = 0;
    WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = (PDRIVER_CONTROL)1;
    WppLoadTracingSupport();
    WPP_MAIN_CB.CurrentIrp = 0;
    v6 = &WPP_MAIN_CB;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_MAIN_CB )
    {
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      if ( WPPTraceSuite == 4 )
      {
        while ( v6 )
        {
          v6->Vpb = 0;
          ((void (__fastcall *)(struct _DRIVER_OBJECT *, _QWORD, __int64 (__fastcall *)(), struct _DEVICE_OBJECT *, PVPB *))pfnEtwRegisterClassicProvider)(
            v6->DriverObject,
            0,
            WppClassicProviderCallback,
            v6,
            &v6->Vpb);
          v6 = v6->NextDevice;
        }
      }
      else if ( WPPTraceSuite == 2 )
      {
        *(_QWORD *)&WPP_MAIN_CB.Type = &WppTraceCallback;
        IoWMIRegistrationControl(&WPP_MAIN_CB, 0x80010001);
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v7, 10, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v10 = PsGetCurrentThreadId();
      WPP_SF_qq(v9, 11, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v10, DriverObject);
    }
    v5 = UMRxInitializeDeviceObject(g_MRxDAVDeviceObject);
    if ( v5 >= 0 )
    {
      LOBYTE(g_MRxDAVDeviceObject->RdbssScavengerInDeviceObject.ClosePendingProcessingSyncEvent.Header.WaitListHead.Flink) = 0;
      g_MRxDAVDeviceObject->RdbssScavengerInDeviceObject.ClosePendingProcessingSyncEvent.Header.WaitListHead.Blink = 0;
      v13 = g_MRxDAVDeviceObject;
      *(_QWORD *)&v13[1].DeviceObject.Type = IoGetCurrentProcess();
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = PsGetCurrentThreadId();
      WPP_SF_qD(v11, 12, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v12, v5);
    }
  }
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v15 = PsGetCurrentThreadId();
      WPP_SF_q(v14, 13, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v15);
    }
    if ( v4 )
      RxUnregisterMinirdr(g_MRxDAVDeviceObject);
    ExDeleteResourceLite(&MRxDAVTimerThreadLock);
    ExDeleteResourceLite(&LockTokenEntryListLock);
    ExDeleteResourceLite(&LockConflictEntryListLock);
    ExDeleteResourceLite(&QueueLockRefreshWorkItemLock);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v16 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v17 = PsGetCurrentThreadId();
      WPP_SF_qD(v16, 14, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v17, v5);
    }
    return v5;
  }
  else
  {
    memset64(DriverObject->MajorFunction, (unsigned __int64)&MRxDAVFsdDispatch, 0x1Bu);
    DriverObject->DriverUnload = (PDRIVER_UNLOAD)MRxDAVUnload;
    DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)&MRxDAVFastIoDispatch;
    MRxDAVFastIoDispatch = 224;
    qword_14000B830 = (__int64)MRxDAVFastIoDeviceControl;
    qword_14000B7F0 = (__int64)MRxDAVFastIoRead;
    qword_14000B7F8 = (__int64)MRxDAVFastIoWrite;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v19 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v20 = PsGetCurrentThreadId();
      WPP_SF_qD(v19, 21, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids, v20, 0);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140016d2c  mov     r11, rsp
0x140016d2f  mov     [r11+8], rbx
0x140016d33  push    rsi
0x140016d34  push    rdi
0x140016d35  push    r12
0x140016d37  push    r13
0x140016d39  push    r15
0x140016d3b  sub     rsp, 0B0h
0x140016d42  mov     r13, rcx
0x140016d45  xor     r12d, r12d
0x140016d48  mov     [rsp+0D8h+var_98], r12d
0x140016d4d  mov     [rsp+0D8h+var_94], r12d
0x140016d52  xorps   xmm0, xmm0
0x140016d55  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x140016d5a  xor     eax, eax
0x140016d5c  movups  [rsp+0D8h+var_60], xmm0
0x140016d61  movups  xmmword ptr [r11-50h], xmm0
0x140016d66  movups  xmmword ptr [r11-44h], xmm0
0x140016d6b  mov     qword ptr [r11+20h], 0FFFFFFFFFFFFFFFFh
0x140016d73  movups  [rsp+0D8h+var_80], xmm0
0x140016d78  xorps   xmm1, xmm1
0x140016d7b  movups  [rsp+0D8h+var_70], xmm1
0x140016d80  mov     [r11+18h], r12d
0x140016d84  call    MRxDAVInitializeTheTimeValues
0x140016d89  lea     r8, DisableEFS
0x140016d90  lea     rdx, aDisableefsonwe; "DisableEFSOnWebDav"
0x140016d97  call    UMRxReadDWORDFromTheRegistry
0x140016d9c  test    eax, eax
0x140016d9e  jz      short loc_140016DA7
0x140016da0  mov     cs:DisableEFS, r12d
0x140016da7  call    cs:__imp_RxGetRDBSSProcess
0x140016dae  nop     dword ptr [rax+rax+00h]
0x140016db3  mov     edi, 1
0x140016db8  mov     cs:MRxDAVSerializationMutex.Count, edi
0x140016dbe  mov     cs:MRxDAVSerializationMutex.Owner, r12
0x140016dc5  mov     cs:MRxDAVSerializationMutex.Contention, r12d
0x140016dcc  xor     r8d, r8d; State
0x140016dcf  mov     edx, edi; Type
0x140016dd1  lea     rcx, MRxDAVSerializationMutex.Event; Event
0x140016dd8  call    cs:__imp_KeInitializeEvent
0x140016ddf  nop     dword ptr [rax+rax+00h]
0x140016de4  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x140016deb  call    cs:__imp_KeInitializeSpinLock
0x140016df2  nop     dword ptr [rax+rax+00h]
0x140016df7  xor     edx, edx; Type
0x140016df9  lea     rcx, DavTimerObject; Timer
0x140016e00  call    cs:__imp_KeInitializeTimerEx
0x140016e07  nop     dword ptr [rax+rax+00h]
0x140016e0c  mov     cs:TimerThreadShutDown, r12d
0x140016e13  lea     rcx, MRxDAVTimerThreadLock; Resource
0x140016e1a  call    cs:__imp_ExInitializeResourceLite
0x140016e21  nop     dword ptr [rax+rax+00h]
0x140016e26  xor     r8d, r8d; State
0x140016e29  xor     edx, edx; Type
0x140016e2b  lea     rcx, TimerThreadEvent; Event
0x140016e32  call    cs:__imp_KeInitializeEvent
0x140016e39  nop     dword ptr [rax+rax+00h]
0x140016e3e  lea     rax, LockTokenEntryList
0x140016e45  mov     cs:qword_14000BB58, rax
0x140016e4c  mov     cs:LockTokenEntryList, rax
0x140016e53  lea     rcx, LockTokenEntryListLock; Resource
0x140016e5a  call    cs:__imp_ExInitializeResourceLite
0x140016e61  nop     dword ptr [rax+rax+00h]
0x140016e66  lea     rax, LockConflictEntryList
0x140016e6d  mov     cs:qword_14000BC58, rax
0x140016e74  mov     cs:LockConflictEntryList, rax
0x140016e7b  lea     rcx, LockConflictEntryListLock; Resource
0x140016e82  call    cs:__imp_ExInitializeResourceLite
0x140016e89  nop     dword ptr [rax+rax+00h]
0x140016e8e  mov     cs:QueueLockRefreshWorkItem, edi
0x140016e94  lea     rcx, QueueLockRefreshWorkItemLock; Resource
0x140016e9b  call    cs:__imp_ExInitializeResourceLite
0x140016ea2  nop     dword ptr [rax+rax+00h]
0x140016ea7  xor     edx, edx; Val
0x140016ea9  mov     r8d, 208h; Size
0x140016eaf  lea     rcx, DavWinInetCachePath; void *
0x140016eb6  call    memset
0x140016ebb  nop
0x140016ebc  call    MRxDAVInitializeTables
0x140016ec1  mov     r15d, r12d
0x140016ec4  mov     [rsp+0D8h+var_94], r12d
0x140016ec9  lea     rdx, aDeviceWebdavre; "\\Device\\WebDavRedirector"
0x140016ed0  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x140016ed5  call    cs:__imp_RtlInitUnicodeString
0x140016edc  nop     dword ptr [rax+rax+00h]
0x140016ee1  mov     [rsp+0D8h+DeviceCharacteristics], 10h; DeviceCharacteristics
0x140016ee9  mov     [rsp+0D8h+DeviceType], 14h; DeviceType
0x140016ef1  mov     [rsp+0D8h+DeviceExtensionSize], 160h; DeviceExtensionSize
0x140016ef9  lea     rax, [rsp+0D8h+DestinationString]
0x140016efe  mov     [rsp+0D8h+DeviceName], rax; DeviceName
0x140016f03  lea     r9d, [rdi+41h]; Controls
0x140016f07  lea     r8, WPP_MAIN_CB.DeviceQueue; MrdrDispatch
0x140016f0e  mov     rdx, r13; DriverObject
0x140016f11  lea     rcx, g_MRxDAVDeviceObject; DeviceObject
0x140016f18  call    cs:__imp_RxRegisterMinirdr
0x140016f1f  nop     dword ptr [rax+rax+00h]
0x140016f24  mov     ebx, eax
0x140016f26  mov     [rsp+0D8h+var_98], eax
0x140016f2a  test    eax, eax
0x140016f2c  jnz     loc_140017130
0x140016f32  mov     r15d, edi
0x140016f35  mov     [rsp+0D8h+var_94], edi
0x140016f39  mov     qword ptr cs:WPP_MAIN_CB.Type, r12
0x140016f40  lea     rax, WPP_ThisDir_CTLGUID_MupLog
0x140016f47  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140016f4e  lea     rax, WPP_MAIN_CB.DeviceExtension
0x140016f55  mov     cs:WPP_MAIN_CB.NextDevice, rax
0x140016f5c  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x140016f63  mov     cs:WPP_MAIN_CB.Timer, r15
0x140016f6a  mov     cs:WPP_MAIN_CB.DeviceExtension, r12
0x140016f71  lea     rax, WPP_ThisDir_CTLGUID_RFSMon
0x140016f78  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x140016f7f  mov     qword ptr cs:WPP_MAIN_CB.Queue, r12
0x140016f86  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, r12
0x140016f8d  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, r15
0x140016f94  call    WppLoadTracingSupport
0x140016f99  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x140016fa0  lea     rdi, WPP_MAIN_CB
0x140016fa7  cmp     cs:WPP_GLOBAL_Control, rdi
0x140016fae  jz      short loc_14001701C
0x140016fb0  mov     cs:WPP_GLOBAL_Control, rdi
0x140016fb7  mov     eax, cs:WPPTraceSuite
0x140016fbd  cmp     eax, 4
0x140016fc0  jnz     short loc_140016FF5
0x140016fc2  test    rdi, rdi
0x140016fc5  jz      short loc_14001701C
0x140016fc7  lea     rcx, [rdi+38h]
0x140016fcb  mov     [rcx], r12
0x140016fce  mov     rax, cs:pfnEtwRegisterClassicProvider
0x140016fd5  mov     [rsp+0D8h+DeviceName], rcx
0x140016fda  mov     r9, rdi
0x140016fdd  lea     r8, WppClassicProviderCallback
0x140016fe4  xor     edx, edx
0x140016fe6  mov     rcx, [rdi+8]
0x140016fea  call    _guard_dispatch_icall
0x140016fef  mov     rdi, [rdi+10h]
0x140016ff3  jmp     short loc_140016FC2
0x140016ff5  cmp     eax, 2
0x140016ff8  jnz     short loc_14001701C
0x140016ffa  lea     rax, WppTraceCallback
0x140017001  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x140017008  mov     edx, 80010001h; Action
0x14001700d  mov     rcx, rdi; DeviceObject
0x140017010  call    cs:__imp_IoWMIRegistrationControl
0x140017017  nop     dword ptr [rax+rax+00h]
0x14001701c  lea     rsi, WPP_GLOBAL_Control
0x140017023  mov     rdi, cs:WPP_GLOBAL_Control
0x14001702a  cmp     rdi, rsi
0x14001702d  jz      short loc_14001705F
0x14001702f  test    dword ptr [rdi+2Ch], 4000h
0x140017036  jz      short loc_14001705F
0x140017038  mov     rdi, [rdi+18h]
0x14001703c  call    cs:__imp_PsGetCurrentThreadId
0x140017043  nop     dword ptr [rax+rax+00h]
0x140017048  mov     r9, rax
0x14001704b  mov     edx, 0Ah
0x140017050  lea     r8, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x140017057  mov     rcx, rdi
0x14001705a  call    WPP_SF_q
0x14001705f  mov     rdi, cs:WPP_GLOBAL_Control
0x140017066  cmp     rdi, rsi
0x140017069  jz      short loc_1400170A0
0x14001706b  test    dword ptr [rdi+2Ch], 2000h
0x140017072  jz      short loc_1400170A0
0x140017074  mov     rdi, [rdi+18h]
0x140017078  call    cs:__imp_PsGetCurrentThreadId
0x14001707f  nop     dword ptr [rax+rax+00h]
0x140017084  mov     r9, rax
0x140017087  mov     edx, 0Bh
0x14001708c  mov     [rsp+0D8h+DeviceName], r13
0x140017091  lea     r8, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x140017098  mov     rcx, rdi
0x14001709b  call    WPP_SF_qq
0x1400170a0  mov     rcx, cs:g_MRxDAVDeviceObject
0x1400170a7  call    UMRxInitializeDeviceObject
0x1400170ac  mov     ebx, eax
0x1400170ae  mov     [rsp+0D8h+var_98], eax
0x1400170b2  test    eax, eax
0x1400170b4  jns     short loc_1400170F8
0x1400170b6  mov     rdi, cs:WPP_GLOBAL_Control
0x1400170bd  cmp     rdi, rsi
0x1400170c0  jz      short loc_140017137
0x1400170c2  mov     eax, [rdi+2Ch]
0x1400170c5  bt      eax, 0Dh
0x1400170c9  jnb     short loc_140017137
0x1400170cb  mov     rdi, [rdi+18h]
0x1400170cf  call    cs:__imp_PsGetCurrentThreadId
0x1400170d6  nop     dword ptr [rax+rax+00h]
0x1400170db  mov     r9, rax
0x1400170de  mov     edx, 0Ch
0x1400170e3  mov     dword ptr [rsp+0D8h+DeviceName], ebx
0x1400170e7  lea     r8, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x1400170ee  mov     rcx, rdi
0x1400170f1  call    WPP_SF_qD
0x1400170f6  jmp     short loc_140017137
0x1400170f8  mov     rax, cs:g_MRxDAVDeviceObject
0x1400170ff  mov     [rax+660h], r12b
0x140017106  mov     rax, cs:g_MRxDAVDeviceObject
0x14001710d  mov     [rax+668h], r12
0x140017114  mov     rdi, cs:g_MRxDAVDeviceObject
0x14001711b  call    cs:__imp_IoGetCurrentProcess
0x140017122  nop     dword ptr [rax+rax+00h]
0x140017127  mov     [rdi+670h], rax
0x14001712e  jmp     short loc_140017137
0x140017130  lea     rsi, WPP_GLOBAL_Control
0x140017137  test    ebx, ebx
0x140017139  jz      loc_140017244
0x14001713f  mov     rdi, cs:WPP_GLOBAL_Control
0x140017146  cmp     rdi, rsi
0x140017149  jz      short loc_14001717B
0x14001714b  test    dword ptr [rdi+2Ch], 2000h
0x140017152  jz      short loc_14001717B
0x140017154  mov     rdi, [rdi+18h]
0x140017158  call    cs:__imp_PsGetCurrentThreadId
0x14001715f  nop     dword ptr [rax+rax+00h]
0x140017164  mov     r9, rax
0x140017167  mov     edx, 0Dh
0x14001716c  lea     r8, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x140017173  mov     rcx, rdi
0x140017176  call    WPP_SF_q
0x14001717b  test    r15d, r15d
0x14001717e  jz      short loc_140017199
0x140017180  cmp     r15d, 1
0x140017184  jnz     short loc_1400171E5
0x140017186  mov     rcx, cs:g_MRxDAVDeviceObject; RxDeviceObject
0x14001718d  call    cs:__imp_RxUnregisterMinirdr
0x140017194  nop     dword ptr [rax+rax+00h]
0x140017199  lea     rcx, MRxDAVTimerThreadLock; Resource
0x1400171a0  call    cs:__imp_ExDeleteResourceLite
0x1400171a7  nop     dword ptr [rax+rax+00h]
0x1400171ac  lea     rcx, LockTokenEntryListLock; Resource
0x1400171b3  call    cs:__imp_ExDeleteResourceLite
0x1400171ba  nop     dword ptr [rax+rax+00h]
0x1400171bf  lea     rcx, LockConflictEntryListLock; Resource
0x1400171c6  call    cs:__imp_ExDeleteResourceLite
0x1400171cd  nop     dword ptr [rax+rax+00h]
0x1400171d2  lea     rcx, QueueLockRefreshWorkItemLock; Resource
0x1400171d9  call    cs:__imp_ExDeleteResourceLite
0x1400171e0  nop     dword ptr [rax+rax+00h]
0x1400171e5  test    ebx, ebx
0x1400171e7  jz      short loc_140017244
0x1400171e9  mov     rdi, cs:WPP_GLOBAL_Control
0x1400171f0  cmp     rdi, rsi
0x1400171f3  jz      short loc_140017229
0x1400171f5  test    dword ptr [rdi+2Ch], 2000h
0x1400171fc  jz      short loc_140017229
0x1400171fe  mov     rdi, [rdi+18h]
0x140017202  call    cs:__imp_PsGetCurrentThreadId
0x140017209  nop     dword ptr [rax+rax+00h]
0x14001720e  mov     r9, rax
0x140017211  mov     edx, 0Eh
0x140017216  mov     dword ptr [rsp+0D8h+DeviceName], ebx
0x14001721a  lea     r8, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x140017221  mov     rcx, rdi
0x140017224  call    WPP_SF_qD
0x140017229  mov     eax, ebx
0x14001722b  mov     rbx, [rsp+0D8h+arg_0]
0x140017233  add     rsp, 0B0h
0x14001723a  pop     r15
0x14001723c  pop     r13
0x14001723e  pop     r12
0x140017240  pop     rdi
0x140017241  pop     rsi
0x140017242  retn
0x140017244  lea     rdi, [r13+70h]
0x140017248  lea     rax, MRxDAVFsdDispatch
0x14001724f  mov     ecx, 1Bh
0x140017254  rep stosq
0x140017257  lea     rax, MRxDAVUnload
0x14001725e  mov     [r13+68h], rax
0x140017262  lea     rax, MRxDAVFastIoDispatch
0x140017269  mov     [r13+50h], rax
0x14001726d  mov     cs:MRxDAVFastIoDispatch, 0E0h
0x140017277  lea     rax, MRxDAVFastIoDeviceControl
0x14001727e  mov     cs:qword_14000B830, rax
0x140017285  lea     rax, MRxDAVFastIoRead
0x14001728c  mov     cs:qword_14000B7F0, rax
0x140017293  lea     rax, MRxDAVFastIoWrite
0x14001729a  mov     cs:qword_14000B7F8, rax
0x1400172a1  mov     rcx, [rsp+0D8h+Handle]; Handle
0x1400172a9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400172ad  jz      short loc_1400172BB
0x1400172af  call    cs:__imp_ZwClose
0x1400172b6  nop     dword ptr [rax+rax+00h]
0x1400172bb  mov     rdi, cs:WPP_GLOBAL_Control
0x1400172c2  cmp     rdi, rsi
0x1400172c5  jz      short loc_1400172FC
0x1400172c7  test    dword ptr [rdi+2Ch], 4000h
0x1400172ce  jz      short loc_1400172FC
0x1400172d0  mov     rdi, [rdi+18h]
0x1400172d4  call    cs:__imp_PsGetCurrentThreadId
0x1400172db  nop     dword ptr [rax+rax+00h]
0x1400172e0  mov     r9, rax
0x1400172e3  mov     edx, 15h
0x1400172e8  mov     dword ptr [rsp+0D8h+DeviceName], r12d
0x1400172ed  lea     r8, WPP_5fffc1f97ba7303780e5dbf01b72fcb5_Traceguids
0x1400172f4  mov     rcx, rdi
0x1400172f7  call    WPP_SF_qD
0x1400172fc  xor     eax, eax
0x1400172fe  jmp     loc_14001722B
  ... truncated ...
```
