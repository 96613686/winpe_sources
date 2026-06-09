# DrUninitialize

- ea: `0x140017cac`
- end: `0x140017ea9`
- name: `DrUninitialize`
- size: `509`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140017eb0`
- `0x14002ac20`
- `0x14002e078`

## callees

- `0x140001660`
- `0x140001e30`
- `0x14000324c`
- `0x140005d58`
- `0x140006350`
- `0x140006560`
- `0x140017cac`
- `0x14001851c`
- `0x14001dcb4`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140017e10`
- `ntoskrnl!IoDeleteDevice` at `0x140017e47`
- `ntoskrnl!IoDeleteDevice` at `0x140017e65`
- `ntoskrnl!IoDeleteDevice` at `0x140017e86`
- `ntoskrnl!IoDeleteDevice` at `0x140017e10`
- `ntoskrnl!IoDeleteDevice` at `0x140017e47`
- `ntoskrnl!IoDeleteDevice` at `0x140017e65`
- `ntoskrnl!IoDeleteDevice` at `0x140017e86`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140017ce4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140017ce4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017d03`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017d03`
- `rdbss!RxUnregisterMinirdr` at `0x140017d2a`
- `rdbss!RxUnregisterMinirdr` at `0x140017d2a`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140017d12`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140017d12`
- `rdbss!RxStopMinirdr` at `0x140017cf7`
- `rdbss!RxStopMinirdr` at `0x140017cf7`
- `rdbss!RxCreateRxContext` at `0x140017cd0`
- `rdbss!RxCreateRxContext` at `0x140017cd0`

## pseudocode

```c
__int64 __fastcall DrUninitialize(DrSessionManager *a1)
{
  PRX_CONTEXT RxContext; // rbx
  void *v2; // rcx
  struct _DEVICE_OBJECT *DeviceObject; // rbx
  RefCount *v4; // rcx
  __int64 i; // rbx
  struct _DEVICE_OBJECT *v6; // rcx

  if ( WPP_MAIN_CB.Queue.Wcb.DeviceContext )
    DrSessionManager::TerminateOutstandingRequests(a1);
  RxContext = RxCreateRxContext(0, (PRDBSS_DEVICE_OBJECT)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc, 0x200u);
  if ( RxContext )
  {
    KeEnterCriticalRegion();
    RxStopMinirdr(RxContext, (PBOOLEAN)&RxContext->RealDevice + 3);
    KeLeaveCriticalRegion();
    RxDereferenceAndDeleteRxContext_Real(RxContext);
  }
  if ( WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
    RxUnregisterMinirdr((PRDBSS_DEVICE_OBJECT)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
  if ( *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type )
  {
    operator delete(*(void **)&WPP_MAIN_CB.DeviceQueue.Type);
    *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = 0;
  }
  if ( WPP_MAIN_CB.Queue.Wcb.DeviceContext )
  {
    (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceContext + 16LL))(
      WPP_MAIN_CB.Queue.Wcb.DeviceContext,
      1);
    WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
  }
  v2 = qword_14000C8A0;
  if ( qword_14000C8A0 )
  {
    operator delete(qword_14000C8A0);
    qword_14000C8A0 = 0;
  }
  if ( *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement
    && (unsigned int)TSDeleteQueue(v2)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  }
  if ( WPP_MAIN_CB.Queue.ListEntry.Blink )
  {
    ((void (__fastcall *)(struct _LIST_ENTRY *, __int64))WPP_MAIN_CB.Queue.ListEntry.Blink->Flink[1].Flink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      1);
    WPP_MAIN_CB.Queue.ListEntry.Blink = 0;
  }
  UninitializeKernelUtilities();
  if ( WPP_MAIN_CB.Queue.Wcb.CurrentIrp )
  {
    IoDeleteDevice((PDEVICE_OBJECT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
    WPP_MAIN_CB.Queue.Wcb.CurrentIrp = 0;
  }
  DeviceObject = (struct _DEVICE_OBJECT *)WPP_MAIN_CB.Queue.Wcb.DeviceObject;
  if ( WPP_MAIN_CB.Queue.Wcb.DeviceObject )
  {
    v4 = (RefCount *)**((_QWORD **)WPP_MAIN_CB.Queue.Wcb.DeviceObject + 8);
    if ( v4 )
      RefCount::Release(v4);
    IoDeleteDevice(DeviceObject);
  }
  for ( i = 0; i != 16; ++i )
  {
    v6 = (struct _DEVICE_OBJECT *)(&DrFakeVidDeviceObject)[i];
    if ( v6 )
      IoDeleteDevice(v6);
  }
  if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters )
  {
    IoDeleteDevice(*(PDEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
    *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = 0;
  }
  return wil_UninitializeFeatureStaging();
}

```

## disassembly

```asm
0x140017cac  push    rbx
0x140017cae  sub     rsp, 20h
0x140017cb2  cmp     qword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140017cba  jz      short loc_140017CC1
0x140017cbc  call    ?TerminateOutstandingRequests@DrSessionManager@@QEAAXXZ; DrSessionManager::TerminateOutstandingRequests(void)
0x140017cc1  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+40h; RxDeviceObject
0x140017cc8  mov     r8d, 200h; InitialContextFlags
0x140017cce  xor     ecx, ecx; Irp
0x140017cd0  call    cs:__imp_RxCreateRxContext
0x140017cd7  nop     dword ptr [rax+rax+00h]
0x140017cdc  mov     rbx, rax
0x140017cdf  test    rax, rax
0x140017ce2  jz      short loc_140017D1E
0x140017ce4  call    cs:__imp_KeEnterCriticalRegion
0x140017ceb  nop     dword ptr [rax+rax+00h]
0x140017cf0  lea     rdx, [rbx+23h]; PostToFsp
0x140017cf4  mov     rcx, rbx; RxContext
0x140017cf7  call    cs:__imp_RxStopMinirdr
0x140017cfe  nop     dword ptr [rax+rax+00h]
0x140017d03  call    cs:__imp_KeLeaveCriticalRegion
0x140017d0a  nop     dword ptr [rax+rax+00h]
0x140017d0f  mov     rcx, rbx; RxContext
0x140017d12  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140017d19  nop     dword ptr [rax+rax+00h]
0x140017d1e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h; RxDeviceObject
0x140017d25  test    rcx, rcx
0x140017d28  jz      short loc_140017D36
0x140017d2a  call    cs:__imp_RxUnregisterMinirdr
0x140017d31  nop     dword ptr [rax+rax+00h]
0x140017d36  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type; void *
0x140017d3d  test    rcx, rcx
0x140017d40  jz      short loc_140017D52
0x140017d42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140017d47  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, 0
0x140017d52  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h
0x140017d59  test    rcx, rcx
0x140017d5c  jz      short loc_140017D7A
0x140017d5e  mov     rax, [rcx]
0x140017d61  mov     edx, 1
0x140017d66  mov     rax, [rax+10h]
0x140017d6a  call    _guard_dispatch_icall
0x140017d6f  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140017d7a  mov     rcx, cs:qword_14000C8A0; void *
0x140017d81  test    rcx, rcx
0x140017d84  jz      short loc_140017D96
0x140017d86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140017d8b  mov     cs:qword_14000C8A0, 0
0x140017d96  cmp     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, 0
0x140017d9e  jz      short loc_140017DD7
0x140017da0  call    TSDeleteQueue
0x140017da5  test    eax, eax
0x140017da7  jz      short loc_140017DD7
0x140017da9  mov     rcx, cs:WPP_GLOBAL_Control
0x140017db0  lea     rax, WPP_GLOBAL_Control
0x140017db7  cmp     rcx, rax
0x140017dba  jz      short loc_140017DD7
0x140017dbc  cmp     byte ptr [rcx+29h], 2
0x140017dc0  jb      short loc_140017DD7
0x140017dc2  mov     rcx, [rcx+18h]
0x140017dc6  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140017dcd  mov     edx, 1Dh
0x140017dd2  call    WPP_SF_
0x140017dd7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140017dde  test    rcx, rcx
0x140017de1  jz      short loc_140017DFF
0x140017de3  mov     rax, [rcx]
0x140017de6  mov     edx, 1
0x140017deb  mov     rax, [rax+10h]
0x140017def  call    _guard_dispatch_icall
0x140017df4  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, 0
0x140017dff  call    ?UninitializeKernelUtilities@@YAXXZ; UninitializeKernelUtilities(void)
0x140017e04  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h; DeviceObject
0x140017e0b  test    rcx, rcx
0x140017e0e  jz      short loc_140017E27
0x140017e10  call    cs:__imp_IoDeleteDevice
0x140017e17  nop     dword ptr [rax+rax+00h]
0x140017e1c  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, 0
0x140017e27  mov     rbx, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140017e2e  test    rbx, rbx
0x140017e31  jz      short loc_140017E53
0x140017e33  mov     rax, [rbx+40h]
0x140017e37  mov     rcx, [rax]; this
0x140017e3a  test    rcx, rcx
0x140017e3d  jz      short loc_140017E44
0x140017e3f  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140017e44  mov     rcx, rbx; DeviceObject
0x140017e47  call    cs:__imp_IoDeleteDevice
0x140017e4e  nop     dword ptr [rax+rax+00h]
0x140017e53  xor     ebx, ebx
0x140017e55  lea     rcx, ?DrFakeVidDeviceObject@@3PAPEAU_DEVICE_OBJECT@@A; _DEVICE_OBJECT * near * DrFakeVidDeviceObject
0x140017e5c  mov     rcx, [rcx+rbx*8]; DeviceObject
0x140017e60  test    rcx, rcx
0x140017e63  jz      short loc_140017E71
0x140017e65  call    cs:__imp_IoDeleteDevice
0x140017e6c  nop     dword ptr [rax+rax+00h]
0x140017e71  inc     rbx
0x140017e74  cmp     rbx, 10h
0x140017e78  jnz     short loc_140017E55
0x140017e7a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h; DeviceObject
0x140017e81  test    rcx, rcx
0x140017e84  jz      short loc_140017E9D
0x140017e86  call    cs:__imp_IoDeleteDevice
0x140017e8d  nop     dword ptr [rax+rax+00h]
0x140017e92  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, 0
0x140017e9d  call    wil_UninitializeFeatureStaging
0x140017ea2  add     rsp, 20h
0x140017ea6  pop     rbx
0x140017ea7  retn
```
