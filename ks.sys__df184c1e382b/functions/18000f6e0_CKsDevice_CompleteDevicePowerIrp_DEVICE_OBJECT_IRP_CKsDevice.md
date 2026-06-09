# CKsDevice::CompleteDevicePowerIrp(_DEVICE_OBJECT *,_IRP *,CKsDevice *)

- ea: `0x18000f6e0`
- end: `0x18000f84b`
- name: `?CompleteDevicePowerIrp@CKsDevice@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAV1@@Z`
- size: `363`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, struct CKsDevice *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x18000f6e0`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x18000f7cc`
- `ntoskrnl!ExQueueWorkItem` at `0x18000f7cc`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000f76a`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000f76a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000f75b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000f75b`

## pseudocode

```c
__int64 __fastcall CKsDevice::CompleteDevicePowerIrp(struct _DEVICE_OBJECT *a1, struct _IRP *a2, struct CKsDevice *a3)
{
  NTSTATUS Status; // ebx
  struct _IRP *v5; // rdi
  int v6; // edx
  int v8; // edx
  NTSTATUS v9; // [rsp+28h] [rbp-40h]

  Status = a2->IoStatus.Status;
  v5 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v9 = a2->IoStatus.Status;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      132,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      v9);
  }
  if ( Status >= 0 )
  {
    a3->m_PassivePowerWorker.Parameter = v5;
    a3->m_PassivePowerWorker.WorkerRoutine = (PWORKER_THREAD_ROUTINE)CKsDevice::PassiveWakeDevice;
    a3->m_PassivePowerWorker.List.Flink = 0;
    ExQueueWorkItem(&a3->m_PassivePowerWorker, DelayedWorkQueue);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v8) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          1,
          134,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v8) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          1,
          135,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
    }
    return 3221225494LL;
  }
  else
  {
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)a3->m_Ext.Public.FunctionalDeviceObject->DeviceExtension - 1, v5, 0x20u);
    PoStartNextPowerIrp(v5);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v6) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          133,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          Status);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000f6e0  push    rbx
0x18000f6e2  push    rbp
0x18000f6e3  push    rsi
0x18000f6e4  push    rdi
0x18000f6e5  push    r12
0x18000f6e7  push    r14
0x18000f6e9  push    r15
0x18000f6eb  sub     rsp, 30h
0x18000f6ef  mov     ebx, [rdx+30h]
0x18000f6f2  mov     rsi, r8
0x18000f6f5  mov     rdi, rdx
0x18000f6f8  xor     ebp, ebp
0x18000f6fa  lea     r15, WPP_RECORDER_INITIALIZED
0x18000f701  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f708  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000f70f  lea     r14d, [rbp+1]
0x18000f713  jz      short loc_18000F73F
0x18000f715  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f71c  cmp     [rcx+48h], bp
0x18000f720  jz      short loc_18000F73F
0x18000f722  mov     rcx, [rcx+40h]
0x18000f726  mov     r9d, 84h
0x18000f72c  mov     [rsp+68h+var_40], ebx
0x18000f730  mov     r8d, r14d
0x18000f733  mov     dl, 5
0x18000f735  mov     [rsp+68h+var_48], r12
0x18000f73a  call    WPP_RECORDER_SF_D
0x18000f73f  test    ebx, ebx
0x18000f741  jns     short loc_18000F7B0
0x18000f743  mov     rax, [rsi+0E0h]
0x18000f74a  mov     r8d, 20h ; ' '; RemlockSize
0x18000f750  mov     rdx, rdi; Tag
0x18000f753  mov     rcx, [rax+40h]
0x18000f757  sub     rcx, 20h ; ' '; RemoveLock
0x18000f75b  call    cs:__imp_IoReleaseRemoveLockEx
0x18000f762  nop     dword ptr [rax+rax+00h]
0x18000f767  mov     rcx, rdi; Irp
0x18000f76a  call    cs:__imp_PoStartNextPowerIrp
0x18000f771  nop     dword ptr [rax+rax+00h]
0x18000f776  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f77d  jz      short loc_18000F7A9
0x18000f77f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f786  cmp     [rcx+48h], bp
0x18000f78a  jz      short loc_18000F7A9
0x18000f78c  mov     rcx, [rcx+40h]
0x18000f790  mov     r9d, 85h
0x18000f796  mov     [rsp+68h+var_40], ebx
0x18000f79a  mov     r8d, r14d
0x18000f79d  mov     dl, 5
0x18000f79f  mov     [rsp+68h+var_48], r12
0x18000f7a4  call    WPP_RECORDER_SF_D
0x18000f7a9  xor     eax, eax
0x18000f7ab  jmp     loc_18000F83B
0x18000f7b0  lea     rcx, [rsi+3A0h]; WorkItem
0x18000f7b7  mov     edx, r14d; QueueType
0x18000f7ba  lea     rax, ?PassiveWakeDevice@CKsDevice@@CAXPEAU_IRP@@@Z; CKsDevice::PassiveWakeDevice(_IRP *)
0x18000f7c1  mov     [rcx+18h], rdi
0x18000f7c5  mov     [rcx+10h], rax
0x18000f7c9  mov     [rcx], rbp
0x18000f7cc  call    cs:__imp_ExQueueWorkItem
0x18000f7d3  nop     dword ptr [rax+rax+00h]
0x18000f7d8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f7df  jz      short loc_18000F836
0x18000f7e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7e8  cmp     [rcx+48h], bp
0x18000f7ec  jz      short loc_18000F807
0x18000f7ee  mov     rcx, [rcx+40h]
0x18000f7f2  mov     r9d, 86h
0x18000f7f8  mov     r8d, r14d
0x18000f7fb  mov     [rsp+68h+var_48], r12
0x18000f800  mov     dl, 5
0x18000f802  call    WPP_RECORDER_SF_
0x18000f807  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f80e  jz      short loc_18000F836
0x18000f810  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f817  cmp     [rcx+48h], bp
0x18000f81b  jz      short loc_18000F836
0x18000f81d  mov     rcx, [rcx+40h]
0x18000f821  mov     r9d, 87h
0x18000f827  mov     r8d, r14d
0x18000f82a  mov     [rsp+68h+var_48], r12
0x18000f82f  mov     dl, 5
0x18000f831  call    WPP_RECORDER_SF_
0x18000f836  mov     eax, 0C0000016h
0x18000f83b  add     rsp, 30h
0x18000f83f  pop     r15
0x18000f841  pop     r14
0x18000f843  pop     r12
0x18000f845  pop     rdi
0x18000f846  pop     rsi
0x18000f847  pop     rbp
0x18000f848  pop     rbx
0x18000f849  retn
```
