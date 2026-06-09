# CKsDevice::CompleteDevicePowerIrp(_DEVICE_OBJECT *,_IRP *,CKsDevice *)

- ea: `0x18000eff0`
- end: `0x18000f15b`
- name: `?CompleteDevicePowerIrp@CKsDevice@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAV1@@Z`
- size: `363`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, struct CKsDevice *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x18000eff0`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x18000f0dc`
- `ntoskrnl!ExQueueWorkItem` at `0x18000f0dc`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000f07a`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000f07a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000f06b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000f06b`

## pseudocode

```c
__int64 __fastcall CKsDevice::CompleteDevicePowerIrp(struct _DEVICE_OBJECT *a1, struct _IRP *a2, struct CKsDevice *a3)
{
  NTSTATUS Status; // ebx
  struct _IRP *v5; // rdi
  int v6; // edx
  int v8; // edx
  __int64 v9; // [rsp+28h] [rbp-40h]
  NTSTATUS v10; // [rsp+28h] [rbp-40h]

  Status = a2->IoStatus.Status;
  v5 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v10 = a2->IoStatus.Status;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      132,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      v10);
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
        LODWORD(v9) = Status;
        LOBYTE(v6) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          133,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          v9);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000eff0  push    rbx
0x18000eff2  push    rbp
0x18000eff3  push    rsi
0x18000eff4  push    rdi
0x18000eff5  push    r12
0x18000eff7  push    r14
0x18000eff9  push    r15
0x18000effb  sub     rsp, 30h
0x18000efff  mov     ebx, [rdx+30h]
0x18000f002  mov     rsi, r8
0x18000f005  mov     rdi, rdx
0x18000f008  xor     ebp, ebp
0x18000f00a  lea     r15, WPP_RECORDER_INITIALIZED
0x18000f011  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f018  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000f01f  lea     r14d, [rbp+1]
0x18000f023  jz      short loc_18000F04F
0x18000f025  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f02c  cmp     [rcx+48h], bp
0x18000f030  jz      short loc_18000F04F
0x18000f032  mov     rcx, [rcx+40h]
0x18000f036  mov     r9d, 84h
0x18000f03c  mov     dword ptr [rsp+68h+var_40], ebx
0x18000f040  mov     r8d, r14d
0x18000f043  mov     dl, 5
0x18000f045  mov     [rsp+68h+var_48], r12
0x18000f04a  call    WPP_RECORDER_SF_D
0x18000f04f  test    ebx, ebx
0x18000f051  jns     short loc_18000F0C0
0x18000f053  mov     rax, [rsi+0E0h]
0x18000f05a  mov     r8d, 20h ; ' '; RemlockSize
0x18000f060  mov     rdx, rdi; Tag
0x18000f063  mov     rcx, [rax+40h]
0x18000f067  sub     rcx, 20h ; ' '; RemoveLock
0x18000f06b  call    cs:__imp_IoReleaseRemoveLockEx
0x18000f072  nop     dword ptr [rax+rax+00h]
0x18000f077  mov     rcx, rdi; Irp
0x18000f07a  call    cs:__imp_PoStartNextPowerIrp
0x18000f081  nop     dword ptr [rax+rax+00h]
0x18000f086  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f08d  jz      short loc_18000F0B9
0x18000f08f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f096  cmp     [rcx+48h], bp
0x18000f09a  jz      short loc_18000F0B9
0x18000f09c  mov     rcx, [rcx+40h]
0x18000f0a0  mov     r9d, 85h
0x18000f0a6  mov     dword ptr [rsp+68h+var_40], ebx
0x18000f0aa  mov     r8d, r14d
0x18000f0ad  mov     dl, 5
0x18000f0af  mov     [rsp+68h+var_48], r12
0x18000f0b4  call    WPP_RECORDER_SF_D
0x18000f0b9  xor     eax, eax
0x18000f0bb  jmp     loc_18000F14B
0x18000f0c0  lea     rcx, [rsi+3A0h]; WorkItem
0x18000f0c7  mov     edx, r14d; QueueType
0x18000f0ca  lea     rax, ?PassiveWakeDevice@CKsDevice@@CAXPEAU_IRP@@@Z; CKsDevice::PassiveWakeDevice(_IRP *)
0x18000f0d1  mov     [rcx+18h], rdi
0x18000f0d5  mov     [rcx+10h], rax
0x18000f0d9  mov     [rcx], rbp
0x18000f0dc  call    cs:__imp_ExQueueWorkItem
0x18000f0e3  nop     dword ptr [rax+rax+00h]
0x18000f0e8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f0ef  jz      short loc_18000F146
0x18000f0f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0f8  cmp     [rcx+48h], bp
0x18000f0fc  jz      short loc_18000F117
0x18000f0fe  mov     rcx, [rcx+40h]
0x18000f102  mov     r9d, 86h
0x18000f108  mov     r8d, r14d
0x18000f10b  mov     [rsp+68h+var_48], r12
0x18000f110  mov     dl, 5
0x18000f112  call    WPP_RECORDER_SF_
0x18000f117  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000f11e  jz      short loc_18000F146
0x18000f120  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f127  cmp     [rcx+48h], bp
0x18000f12b  jz      short loc_18000F146
0x18000f12d  mov     rcx, [rcx+40h]
0x18000f131  mov     r9d, 87h
0x18000f137  mov     r8d, r14d
0x18000f13a  mov     [rsp+68h+var_48], r12
0x18000f13f  mov     dl, 5
0x18000f141  call    WPP_RECORDER_SF_
0x18000f146  mov     eax, 0C0000016h
0x18000f14b  add     rsp, 30h
0x18000f14f  pop     r15
0x18000f151  pop     r14
0x18000f153  pop     r12
0x18000f155  pop     rdi
0x18000f156  pop     rsi
0x18000f157  pop     rbp
0x18000f158  pop     rbx
0x18000f159  retn
```
