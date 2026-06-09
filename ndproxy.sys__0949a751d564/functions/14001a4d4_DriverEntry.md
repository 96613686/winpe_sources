# DriverEntry

- ea: `0x14001a4d4`
- end: `0x14001a7c6`
- name: `DriverEntry`
- size: `754`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001a010`

## callees

- `0x140001b54`
- `0x140005480`
- `0x1400084c0`
- `0x140017254`
- `0x1400172e8`
- `0x1400176c4`
- `0x14001a320`
- `0x14001a4d4`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14001a69f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a6c4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a70a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a69f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a6c4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001a70a`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001a59b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001a5ce`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001a59b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001a5ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a642`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a642`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  ULONG v3; // edx
  ULONG v4; // r9d
  PKDEFERRED_ROUTINE DeferredRoutine; // rbx
  _QWORD *v7; // rax
  PKDEFERRED_ROUTINE v8; // rcx
  PDEVICE_OBJECT v9; // rax
  NTSTATUS v10; // ebx
  ULONG Size; // [rsp+20h] [rbp-48h]
  BOOLEAN Tag; // [rsp+28h] [rbp-40h]
  PCUNICODE_STRING Depth; // [rsp+30h] [rbp-38h]
  const GUID *v14; // [rsp+38h] [rbp-30h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp+18h] BYREF

  DeviceObject = 0;
  DestinationString = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_NdProxyWpp;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport(DriverObject, RegistryPath);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids);
  ExInitializeNPagedLookasideList(&ProviderEventLookaside, 0, 0, 0x200u, 0x40u, 0x315850u, 0);
  ExInitializeNPagedLookasideList(&VcLookaside, 0, 0, 0x200u, 0x218u, 0x695850u, 0);
  *(_OWORD *)&WPP_MAIN_CB.Dpc.DpcData = 0;
  *(_QWORD *)&WPP_MAIN_CB.SectorSize = 0;
  *(_OWORD *)&WPP_MAIN_CB.SecurityDescriptor = 0;
  WPP_MAIN_CB.DeviceLock.Header.WaitListHead = 0;
  *(_OWORD *)&WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.Queue.ListEntry = 0;
  *(_OWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = 0;
  *(_OWORD *)&WPP_MAIN_CB.Queue.Wcb.DeviceObject = 0;
  *(_OWORD *)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc = 0;
  *(_OWORD *)&WPP_MAIN_CB.DeviceQueue.Type = 0;
  *(_OWORD *)&WPP_MAIN_CB.DeviceQueue.Busy = 0;
  *(_OWORD *)&WPP_MAIN_CB.Dpc.DpcListEntry.Next = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\NDProxy");
  if ( WdmlibIoCreateDeviceSecure(DriverObject, v3, &DestinationString, v4, Size, Tag, Depth, v14, &DeviceObject) < 0 )
    return -1073741823;
  WPP_MAIN_CB.Dpc.DeferredRoutine = (PKDEFERRED_ROUTINE)DeviceObject->DeviceExtension;
  DeferredRoutine = WPP_MAIN_CB.Dpc.DeferredRoutine;
  memset(WPP_MAIN_CB.Dpc.DeferredRoutine, 0, 0x68u);
  *((_QWORD *)DeferredRoutine + 1) = DriverObject;
  KeInitializeSpinLock((PKSPIN_LOCK)DeferredRoutine + 11);
  v7 = (_QWORD *)((char *)WPP_MAIN_CB.Dpc.DeferredRoutine + 32);
  *((_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 5) = (char *)WPP_MAIN_CB.Dpc.DeferredRoutine + 32;
  *v7 = v7;
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink);
  WPP_MAIN_CB.Dpc.DpcData = (PVOID)0x100000001LL;
  WPP_MAIN_CB.SecurityDescriptor = &WPP_MAIN_CB.ActiveThreadCount;
  *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = &WPP_MAIN_CB.ActiveThreadCount;
  WPP_MAIN_CB.DeviceLock.Header.LockNV = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  v8 = WPP_MAIN_CB.Dpc.DeferredRoutine;
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = &WPP_MAIN_CB.DeviceExtension;
  WPP_MAIN_CB.DeviceExtension = &WPP_MAIN_CB.DeviceExtension;
  *((_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 2) = DeviceObject;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)PxUnload;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)PxIOCreate;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&PxIOClose;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)PxIODispatch;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)PxIOCleanup;
  v9 = DeviceObject;
  DriverObject->FastIoDispatch = 0;
  v9->Flags |= 0x10u;
  *((_QWORD *)v8 + 2) = DeviceObject;
  if ( (unsigned __int8)InitNDISProxy() )
    return 0;
  v10 = -1073741823;
  PxUnload(DriverObject);
  return v10;
}

```

## disassembly

```asm
0x14001a4d4  mov     rax, rsp
0x14001a4d7  mov     [rax+8], rbx
0x14001a4db  push    rdi
0x14001a4dc  sub     rsp, 60h
0x14001a4e0  xorps   xmm0, xmm0
0x14001a4e3  mov     qword ptr [rax+18h], 0
0x14001a4eb  movups  xmmword ptr [rax-18h], xmm0
0x14001a4ef  lea     rax, WPP_ThisDir_CTLGUID_NdProxyWpp
0x14001a4f6  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14001a501  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14001a508  mov     rdi, rcx
0x14001a50b  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14001a516  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14001a521  mov     cs:WPP_MAIN_CB.Timer, 1
0x14001a52c  call    WppLoadTracingSupport
0x14001a531  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14001a53c  call    WppInitKm
0x14001a541  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a548  lea     rax, WPP_GLOBAL_Control
0x14001a54f  cmp     rcx, rax
0x14001a552  jz      short loc_14001A56F
0x14001a554  cmp     byte ptr [rcx+29h], 4
0x14001a558  jb      short loc_14001A56F
0x14001a55a  mov     rcx, [rcx+18h]
0x14001a55e  lea     r8, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids
0x14001a565  mov     edx, 0Ah
0x14001a56a  call    WPP_SF_
0x14001a56f  xor     eax, eax
0x14001a571  lea     rcx, ProviderEventLookaside; Lookaside
0x14001a578  mov     word ptr [rsp+68h+Depth], ax; Depth
0x14001a57d  mov     ebx, 200h
0x14001a582  mov     dword ptr [rsp+68h+Tag], 315850h; Tag
0x14001a58a  mov     r9d, ebx; Flags
0x14001a58d  xor     r8d, r8d; Free
0x14001a590  mov     [rsp+68h+Size], 40h ; '@'; Size
0x14001a599  xor     edx, edx; Allocate
0x14001a59b  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001a5a2  nop     dword ptr [rax+rax+00h]
0x14001a5a7  xor     eax, eax
0x14001a5a9  lea     rcx, VcLookaside; Lookaside
0x14001a5b0  mov     word ptr [rsp+68h+Depth], ax; DefaultSDDLString
0x14001a5b5  mov     r9d, ebx; Flags
0x14001a5b8  mov     dword ptr [rsp+68h+Tag], 695850h; Exclusive
0x14001a5c0  xor     r8d, r8d; Free
0x14001a5c3  xor     edx, edx; Allocate
0x14001a5c5  mov     [rsp+68h+Size], 218h; DeviceCharacteristics
0x14001a5ce  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001a5d5  nop     dword ptr [rax+rax+00h]
0x14001a5da  xorps   xmm0, xmm0
0x14001a5dd  lea     rdx, aDeviceNdproxy; "\\Device\\NDProxy"
0x14001a5e4  xorps   xmm1, xmm1
0x14001a5e7  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14001a5ec  xor     eax, eax
0x14001a5ee  movups  xmmword ptr cs:WPP_MAIN_CB.Dpc.DpcData, xmm0
0x14001a5f5  mov     qword ptr cs:WPP_MAIN_CB.SectorSize, rax
0x14001a5fc  movups  xmmword ptr cs:WPP_MAIN_CB.SecurityDescriptor, xmm0
0x14001a603  movups  xmmword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, xmm0
0x14001a60a  movups  xmmword ptr cs:WPP_MAIN_CB.DeviceExtension, xmm0
0x14001a611  movups  xmmword ptr cs:WPP_MAIN_CB.Queue, xmm0
0x14001a618  movups  xmmword ptr cs:WPP_MAIN_CB.Queue+10h, xmm0
0x14001a61f  movups  xmmword ptr cs:WPP_MAIN_CB.Queue+30h, xmm1
0x14001a626  movups  xmmword ptr cs:WPP_MAIN_CB.Queue+40h, xmm1
0x14001a62d  movups  xmmword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, xmm1
0x14001a634  movups  xmmword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, xmm0
0x14001a63b  movups  xmmword ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, xmm0
0x14001a642  call    cs:__imp_RtlInitUnicodeString
0x14001a649  nop     dword ptr [rax+rax+00h]
0x14001a64e  lea     rax, [rsp+68h+arg_10]
0x14001a656  mov     rcx, rdi; DriverObject
0x14001a659  lea     r8, [rsp+68h+DestinationString]; DeviceName
0x14001a65e  mov     [rsp+68h+DeviceObject], rax; DeviceObject
0x14001a663  call    WdmlibIoCreateDeviceSecure
0x14001a668  test    eax, eax
0x14001a66a  jns     short loc_14001A676
0x14001a66c  mov     eax, 0C0000001h
0x14001a671  jmp     loc_14001A7BA
0x14001a676  mov     rax, [rsp+68h+arg_10]
0x14001a67e  xor     edx, edx; Val
0x14001a680  mov     rbx, [rax+40h]
0x14001a684  lea     r8d, [rdx+68h]; Size
0x14001a688  mov     rcx, rbx; void *
0x14001a68b  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rbx
0x14001a692  call    memset
0x14001a697  lea     rcx, [rbx+58h]; SpinLock
0x14001a69b  mov     [rbx+8], rdi
0x14001a69f  call    cs:__imp_KeInitializeSpinLock
0x14001a6a6  nop     dword ptr [rax+rax+00h]
0x14001a6ab  mov     rax, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a6b2  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink; SpinLock
0x14001a6b9  add     rax, 20h ; ' '
0x14001a6bd  mov     [rax+8], rax
0x14001a6c1  mov     [rax], rax
0x14001a6c4  call    cs:__imp_KeInitializeSpinLock
0x14001a6cb  nop     dword ptr [rax+rax+00h]
0x14001a6d0  lea     rax, WPP_MAIN_CB.ActiveThreadCount
0x14001a6d7  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DpcData, 1
0x14001a6e1  lea     rcx, WPP_MAIN_CB.Queue+10h; SpinLock
0x14001a6e8  mov     cs:WPP_MAIN_CB.SecurityDescriptor, rax
0x14001a6ef  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rax
0x14001a6f6  mov     dword ptr cs:WPP_MAIN_CB.DeviceLock.Header, 0
0x14001a700  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DpcData+4, 1
0x14001a70a  call    cs:__imp_KeInitializeSpinLock
0x14001a711  nop     dword ptr [rax+rax+00h]
0x14001a716  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14001a71d  lea     rax, WPP_MAIN_CB.DeviceExtension
0x14001a724  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x14001a72b  mov     cs:WPP_MAIN_CB.DeviceExtension, rax
0x14001a732  mov     rax, [rsp+68h+arg_10]
0x14001a73a  mov     [rcx+10h], rax
0x14001a73e  lea     rax, PxUnload
0x14001a745  mov     [rdi+68h], rax
0x14001a749  lea     rax, PxIOCreate
0x14001a750  mov     [rdi+70h], rax
0x14001a754  lea     rax, PxIOClose
0x14001a75b  mov     [rdi+80h], rax
0x14001a762  lea     rax, PxIODispatch
0x14001a769  mov     [rdi+0E0h], rax
0x14001a770  lea     rax, PxIOCleanup
0x14001a777  mov     [rdi+100h], rax
0x14001a77e  mov     rax, [rsp+68h+arg_10]
0x14001a786  mov     qword ptr [rdi+50h], 0
0x14001a78e  or      dword ptr [rax+30h], 10h
0x14001a792  mov     rax, [rsp+68h+arg_10]
0x14001a79a  mov     [rcx+10h], rax
0x14001a79e  call    InitNDISProxy
0x14001a7a3  test    al, al
0x14001a7a5  jz      short loc_14001A7AB
0x14001a7a7  xor     ebx, ebx
0x14001a7a9  jmp     short loc_14001A7B8
0x14001a7ab  mov     rcx, rdi
0x14001a7ae  mov     ebx, 0C0000001h
0x14001a7b3  call    PxUnload
0x14001a7b8  mov     eax, ebx
0x14001a7ba  mov     rbx, [rsp+68h+arg_0]
0x14001a7bf  add     rsp, 60h
0x14001a7c3  pop     rdi
0x14001a7c4  retn
```
