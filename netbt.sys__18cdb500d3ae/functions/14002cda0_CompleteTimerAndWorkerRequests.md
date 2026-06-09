# CompleteTimerAndWorkerRequests

- ea: `0x14002cda0`
- end: `0x14002d086`
- name: `CompleteTimerAndWorkerRequests`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140044a00`

## callees

- `0x140006080`
- `0x140006900`
- `0x14000dc40`
- `0x14001a2b8`
- `0x14001f6dc`
- `0x140029108`
- `0x14002cda0`
- `0x14004031c`
- `0x140040428`
- `0x140041c38`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14002ce99`
- `ntoskrnl!KeClearEvent` at `0x14002ce99`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002cf8a`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002cf8a`
- `ntoskrnl!IoDeleteDevice` at `0x14002d030`
- `ntoskrnl!IoDeleteDevice` at `0x14002d030`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002cf4c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002cf4c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002cdbf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ce19`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ce7c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002cdbf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ce19`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ce7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ce00`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ce3e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cf28`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cf5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ce00`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ce3e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cf28`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002cf5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d016`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d016`

## pseudocode

```c
__int64 CompleteTimerAndWorkerRequests()
{
  unsigned int v0; // edi
  KIRQL v1; // si
  __int64 v2; // r8
  struct _DEVICE_OBJECT *v3; // rbx
  KIRQL v4; // al
  __int64 v5; // rcx
  KIRQL v6; // si
  _QWORD *v7; // rbx
  __int64 v8; // rax
  struct _DEVICE_OBJECT *v9; // rbx
  struct _DRIVER_OBJECT *DriverObject; // rcx
  struct _DEVICE_OBJECT *NextDevice; // rdx
  PKDPC BufferChainingDpc; // rcx
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-28h]
  union _LARGE_INTEGER Interval; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  v1 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  while ( (__int64 *)NbtConfig != &NbtConfig )
  {
    v3 = (struct _DEVICE_OBJECT *)(NbtConfig - 344);
    LOBYTE(v2) = 1;
    NBT_REFERENCE_DEVICE(NbtConfig - 344, 6, v2);
    KeReleaseSpinLock(&SpinLock, v1);
    NbtDestroyDevice(v3);
    v1 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    NBT_DEREFERENCE_DEVICE(v3, 6);
  }
  KeReleaseSpinLock(&SpinLock, v1);
  if ( pNbtSmbDevice )
  {
    NbtDestroyDevice(pNbtSmbDevice);
    pNbtSmbDevice = 0;
  }
  NbtDestroyDevice(pWinsDeviceContext);
  pWinsDeviceContext = 0;
  v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  LOBYTE(v5) = 1;
  v6 = v4;
  StopInitTimers(v5);
  KeClearEvent(&Event);
  while ( 1 )
  {
    v7 = TimerQ;
    if ( TimerQ == &TimerQ )
      break;
    if ( *((PVOID **)TimerQ + 1) != &TimerQ || (v8 = *(_QWORD *)TimerQ, *(PVOID *)(*(_QWORD *)TimerQ + 8LL) != TimerQ) )
LABEL_28:
      __fastfail(3u);
    TimerQ = *(PVOID *)TimerQ;
    *(_QWORD *)(v8 + 8) = &TimerQ;
    v7[1] = v7;
    *v7 = v7;
    if ( (BYTE3(xmmword_140038420) & 1) != 0 )
      WPP_SF_dq(1048, 47, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, v0, v7);
    StopTimer(v7);
    ++v0;
  }
  if ( dword_1400396A0 )
  {
    KeReleaseSpinLock(&SpinLock, v6);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
  else
  {
    KeReleaseSpinLock(&SpinLock, v6);
  }
  while ( dword_1400396F4 || dword_140039754 )
  {
    Interval.QuadPart = -10000000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  NTExecuteWorker(0);
  while ( (__int64 *)qword_140039450 != &qword_140039450 )
  {
    v9 = (struct _DEVICE_OBJECT *)(qword_140039450 - 344);
    if ( (xmmword_140038420 & 4) != 0 )
      WPP_SF_Z(1026, 48, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, &v9[1].Queue.Wcb.CurrentIrp);
    DriverObject = v9[1].DriverObject;
    if ( DriverObject->DeviceObject != (PDEVICE_OBJECT)&v9[1].DriverObject )
      goto LABEL_28;
    NextDevice = v9[1].NextDevice;
    if ( *(struct _DEVICE_OBJECT **)&NextDevice->Type != (struct _DEVICE_OBJECT *)&v9[1].DriverObject )
      goto LABEL_28;
    *(_QWORD *)&NextDevice->Type = DriverObject;
    DriverObject->DeviceObject = NextDevice;
    BufferChainingDpc = v9[1].Queue.Wcb.BufferChainingDpc;
    if ( BufferChainingDpc )
    {
      ExFreePoolWithTag(BufferChainingDpc, 0);
      v9[1].Queue.Wcb.BufferChainingDpc = 0;
    }
    IoDeleteDevice(v9);
  }
  if ( (xmmword_140038420 & 4) != 0 )
  {
    LODWORD(Timeout) = 0;
    WPP_SF_dd(1026, 49, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, v0, Timeout);
  }
  return v0;
}

```

## disassembly

```asm
0x14002cda0  mov     [rsp+arg_8], rbx
0x14002cda5  mov     [rsp+arg_10], rsi
0x14002cdaa  push    rdi
0x14002cdab  push    r14
0x14002cdad  push    r15
0x14002cdaf  sub     rsp, 30h
0x14002cdb3  lea     r14, SpinLock
0x14002cdba  xor     edi, edi
0x14002cdbc  mov     rcx, r14; SpinLock
0x14002cdbf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002cdc6  nop     dword ptr [rax+rax+00h]
0x14002cdcb  mov     sil, al
0x14002cdce  lea     r15d, [rdi+6]
0x14002cdd2  mov     rbx, cs:NbtConfig
0x14002cdd9  lea     rax, NbtConfig
0x14002cde0  cmp     rbx, rax
0x14002cde3  jz      short loc_14002CE38
0x14002cde5  add     rbx, 0FFFFFFFFFFFFFEA8h
0x14002cdec  mov     r8b, 1
0x14002cdef  mov     rcx, rbx
0x14002cdf2  mov     edx, r15d
0x14002cdf5  call    NBT_REFERENCE_DEVICE
0x14002cdfa  mov     dl, sil; NewIrql
0x14002cdfd  mov     rcx, r14; SpinLock
0x14002ce00  call    cs:__imp_KeReleaseSpinLock
0x14002ce07  nop     dword ptr [rax+rax+00h]
0x14002ce0c  xor     edx, edx
0x14002ce0e  mov     rcx, rbx; DeviceObject
0x14002ce11  call    NbtDestroyDevice
0x14002ce16  mov     rcx, r14; SpinLock
0x14002ce19  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ce20  nop     dword ptr [rax+rax+00h]
0x14002ce25  mov     r8b, 1
0x14002ce28  mov     edx, r15d
0x14002ce2b  mov     rcx, rbx
0x14002ce2e  mov     sil, al
0x14002ce31  call    NBT_DEREFERENCE_DEVICE
0x14002ce36  jmp     short loc_14002CDD2
0x14002ce38  mov     dl, sil; NewIrql
0x14002ce3b  mov     rcx, r14; SpinLock
0x14002ce3e  call    cs:__imp_KeReleaseSpinLock
0x14002ce45  nop     dword ptr [rax+rax+00h]
0x14002ce4a  mov     rcx, cs:pNbtSmbDevice; DeviceObject
0x14002ce51  test    rcx, rcx
0x14002ce54  jz      short loc_14002CE64
0x14002ce56  xor     edx, edx
0x14002ce58  call    NbtDestroyDevice
0x14002ce5d  mov     cs:pNbtSmbDevice, rdi
0x14002ce64  mov     rcx, cs:pWinsDeviceContext; DeviceObject
0x14002ce6b  xor     edx, edx
0x14002ce6d  call    NbtDestroyDevice
0x14002ce72  mov     rcx, r14; SpinLock
0x14002ce75  mov     cs:pWinsDeviceContext, rdi
0x14002ce7c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ce83  nop     dword ptr [rax+rax+00h]
0x14002ce88  mov     cl, 1
0x14002ce8a  mov     sil, al
0x14002ce8d  call    StopInitTimers
0x14002ce92  lea     rcx, Event; Event
0x14002ce99  call    cs:__imp_KeClearEvent
0x14002cea0  nop     dword ptr [rax+rax+00h]
0x14002cea5  lea     r15, TimerQ
0x14002ceac  mov     rbx, cs:TimerQ
0x14002ceb3  cmp     rbx, r15
0x14002ceb6  jz      short loc_14002CF19
0x14002ceb8  cmp     [rbx+8], r15
0x14002cebc  jnz     loc_14002D041
0x14002cec2  mov     rax, [rbx]
0x14002cec5  cmp     [rax+8], rbx
0x14002cec9  jnz     loc_14002D041
0x14002cecf  mov     cs:TimerQ, rax
0x14002ced6  mov     [rax+8], r15
0x14002ceda  mov     [rbx+8], rbx
0x14002cede  mov     [rbx], rbx
0x14002cee1  test    byte ptr cs:xmmword_140038420+3, 1
0x14002cee8  jz      short loc_14002CF08
0x14002ceea  mov     edx, 2Fh ; '/'
0x14002ceef  mov     [rsp+48h+Timeout], rbx
0x14002cef4  mov     ecx, 418h
0x14002cef9  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x14002cf00  mov     r9d, edi
0x14002cf03  call    WPP_SF_dq
0x14002cf08  xor     r8d, r8d
0x14002cf0b  xor     edx, edx
0x14002cf0d  mov     rcx, rbx; Entry
0x14002cf10  call    StopTimer
0x14002cf15  inc     edi
0x14002cf17  jmp     short loc_14002CEAC
0x14002cf19  cmp     cs:dword_1400396A0, 0
0x14002cf20  mov     dl, sil; NewIrql
0x14002cf23  mov     rcx, r14; SpinLock
0x14002cf26  jz      short loc_14002CF5A
0x14002cf28  call    cs:__imp_KeReleaseSpinLock
0x14002cf2f  nop     dword ptr [rax+rax+00h]
0x14002cf34  xor     r9d, r9d; Alertable
0x14002cf37  mov     [rsp+48h+Timeout], 0; Timeout
0x14002cf40  xor     r8d, r8d; WaitMode
0x14002cf43  lea     rcx, Event; Object
0x14002cf4a  xor     edx, edx; WaitReason
0x14002cf4c  call    cs:__imp_KeWaitForSingleObject
0x14002cf53  nop     dword ptr [rax+rax+00h]
0x14002cf58  jmp     short loc_14002CF66
0x14002cf5a  call    cs:__imp_KeReleaseSpinLock
0x14002cf61  nop     dword ptr [rax+rax+00h]
0x14002cf66  mov     eax, cs:dword_1400396F4
0x14002cf6c  test    eax, eax
0x14002cf6e  jnz     short loc_14002CF78
0x14002cf70  cmp     cs:dword_140039754, eax
0x14002cf76  jz      short loc_14002CF98
0x14002cf78  lea     r8, [rsp+48h+Interval]; Interval
0x14002cf7d  mov     qword ptr [rsp+48h+Interval], 0FFFFFFFFFF676980h
0x14002cf86  xor     edx, edx; Alertable
0x14002cf88  xor     ecx, ecx; WaitMode
0x14002cf8a  call    cs:__imp_KeDelayExecutionThread
0x14002cf91  nop     dword ptr [rax+rax+00h]
0x14002cf96  jmp     short loc_14002CF66
0x14002cf98  xor     ecx, ecx
0x14002cf9a  call    NTExecuteWorker
0x14002cf9f  mov     esi, 402h
0x14002cfa4  mov     rbx, cs:qword_140039450
0x14002cfab  lea     rax, qword_140039450
0x14002cfb2  cmp     rbx, rax
0x14002cfb5  jz      loc_14002D048
0x14002cfbb  add     rbx, 0FFFFFFFFFFFFFEA8h
0x14002cfc2  test    byte ptr cs:xmmword_140038420, 4
0x14002cfc9  jz      short loc_14002CFE5
0x14002cfcb  lea     r9, [rbx+1D8h]
0x14002cfd2  mov     edx, 30h ; '0'
0x14002cfd7  mov     ecx, esi
0x14002cfd9  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x14002cfe0  call    WPP_SF_Z
0x14002cfe5  lea     rax, [rbx+158h]
0x14002cfec  mov     rcx, [rax]
0x14002cfef  cmp     [rcx+8], rax
0x14002cff3  jnz     short loc_14002D041
0x14002cff5  mov     rdx, [rbx+160h]
0x14002cffc  cmp     [rdx], rax
0x14002cfff  jnz     short loc_14002D041
0x14002d001  mov     [rdx], rcx
0x14002d004  mov     [rcx+8], rdx
0x14002d008  mov     rcx, [rbx+1E0h]; P
0x14002d00f  test    rcx, rcx
0x14002d012  jz      short loc_14002D02D
0x14002d014  xor     edx, edx; Tag
0x14002d016  call    cs:__imp_ExFreePoolWithTag
0x14002d01d  nop     dword ptr [rax+rax+00h]
0x14002d022  mov     qword ptr [rbx+1E0h], 0
0x14002d02d  mov     rcx, rbx; DeviceObject
0x14002d030  call    cs:__imp_IoDeleteDevice
0x14002d037  nop     dword ptr [rax+rax+00h]
0x14002d03c  jmp     loc_14002CFA4
0x14002d041  mov     ecx, 3
0x14002d046  int     29h; Win8: RtlFailFast(ecx)
0x14002d048  test    byte ptr cs:xmmword_140038420, 4
0x14002d04f  jz      short loc_14002D06F
0x14002d051  mov     edx, 31h ; '1'
0x14002d056  mov     dword ptr [rsp+48h+Timeout], 0
0x14002d05e  mov     ecx, esi
0x14002d060  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x14002d067  mov     r9d, edi
0x14002d06a  call    WPP_SF_dd
0x14002d06f  mov     rbx, [rsp+48h+arg_8]
0x14002d074  mov     eax, edi
0x14002d076  mov     rsi, [rsp+48h+arg_10]
0x14002d07b  add     rsp, 30h
0x14002d07f  pop     r15
0x14002d081  pop     r14
0x14002d083  pop     rdi
0x14002d084  retn
```
