# ClasspMpdevCancelRemove

- ea: `0x14003ac04`
- end: `0x14003adf5`
- name: `ClasspMpdevCancelRemove`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003a790`

## callees

- `0x14002001c`
- `0x14002249c`
- `0x14003ac04`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14003acb1`
- `ntoskrnl!IofCallDriver` at `0x14003acb1`
- `ntoskrnl!KeInitializeEvent` at `0x14003ac75`
- `ntoskrnl!KeInitializeEvent` at `0x14003ac75`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003acdc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003acdc`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003ad82`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003ad82`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14003ad04`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14003ad04`
- `ntoskrnl!IofCompleteRequest` at `0x14003adc4`
- `ntoskrnl!IofCompleteRequest` at `0x14003adc4`

## pseudocode

```c
__int64 __fastcall ClasspMpdevCancelRemove(__int64 a1, IRP *a2)
{
  __int64 v2; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v6; // rax
  NTSTATUS Status; // edi
  volatile signed __int32 *DriverObjectExtension; // rax
  bool v9; // zf
  int v10; // ecx
  struct _KEVENT Object; // [rsp+30h] [rbp-48h] BYREF
  __int128 v13; // [rsp+48h] [rbp-30h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  memset(&Object, 0, sizeof(Object));
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  KeInitializeEvent(&Object, SynchronizationEvent, 0);
  v6 = a2->Tail.Overlay.CurrentStackLocation;
  v6[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ClasspMpdevSyncCompletion;
  v6[-1].Context = &Object;
  v6[-1].Control = -32;
  _InterlockedIncrement((volatile signed __int32 *)(v2 + 588));
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 520), a2);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
    Status = a2->IoStatus.Status;
  }
  _InterlockedDecrement((volatile signed __int32 *)(v2 + 588));
  if ( Status >= 0 )
  {
    DriverObjectExtension = (volatile signed __int32 *)IoGetDriverObjectExtension(
                                                         *(PDRIVER_OBJECT *)(v2 + 512),
                                                         ClassInitialize);
    *(_BYTE *)(v2 + 580) = *(_BYTE *)(v2 + 581);
    *(_BYTE *)(v2 + 581) = 1;
    _InterlockedIncrement(DriverObjectExtension + 102);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids, a1, Status);
  }
  v9 = ClassPnPETWEnabled == 0;
  a2->IoStatus.Status = Status;
  if ( !v9 )
  {
    v13 = 0;
    if ( (int)IoGetActivityIdIrp(a2, &v13) >= 0 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
      McTemplateK0qpd_EtwWriteTransfer(
        v10,
        (unsigned int)EventPnpRequestComplete,
        (unsigned int)&v13,
        *(_DWORD *)(v2 + 576),
        (char)a2,
        a2->IoStatus.Status);
  }
  IofCompleteRequest(a2, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14003ac04  mov     r11, rsp
0x14003ac07  mov     [r11+18h], rbx
0x14003ac0b  mov     [r11+20h], rbp
0x14003ac0f  push    rsi
0x14003ac10  push    rdi
0x14003ac11  push    r14
0x14003ac13  sub     rsp, 60h
0x14003ac17  mov     rax, cs:__security_cookie
0x14003ac1e  xor     rax, rsp
0x14003ac21  mov     [rsp+78h+var_20], rax
0x14003ac26  mov     rbx, [rcx+40h]
0x14003ac2a  xorps   xmm0, xmm0
0x14003ac2d  movups  xmmword ptr [rsp+78h+Object], xmm0
0x14003ac32  xor     eax, eax
0x14003ac34  xor     r8d, r8d; State
0x14003ac37  mov     [r11-38h], rax
0x14003ac3b  mov     rsi, rdx
0x14003ac3e  mov     rax, [rdx+0B8h]
0x14003ac45  mov     rbp, rcx
0x14003ac48  lea     rcx, [r11-48h]; Event
0x14003ac4c  lea     edx, [r8+1]; Type
0x14003ac50  movups  xmm0, xmmword ptr [rax]
0x14003ac53  movups  xmmword ptr [rax-48h], xmm0
0x14003ac57  movups  xmm1, xmmword ptr [rax+10h]
0x14003ac5b  movups  xmmword ptr [rax-38h], xmm1
0x14003ac5f  movups  xmm0, xmmword ptr [rax+20h]
0x14003ac63  movups  xmmword ptr [rax-28h], xmm0
0x14003ac67  movsd   xmm1, qword ptr [rax+30h]
0x14003ac6c  movsd   qword ptr [rax-18h], xmm1
0x14003ac71  mov     byte ptr [rax-45h], 0
0x14003ac75  call    cs:__imp_KeInitializeEvent
0x14003ac7c  nop     dword ptr [rax+rax+00h]
0x14003ac81  mov     rax, [rsi+0B8h]
0x14003ac88  lea     rcx, ClasspMpdevSyncCompletion
0x14003ac8f  mov     [rax-10h], rcx
0x14003ac93  lea     rcx, [rsp+78h+Object]
0x14003ac98  mov     [rax-8], rcx
0x14003ac9c  mov     byte ptr [rax-45h], 0E0h
0x14003aca0  lock inc dword ptr [rbx+24Ch]
0x14003aca7  mov     rcx, [rbx+208h]; DeviceObject
0x14003acae  mov     rdx, rsi; Irp
0x14003acb1  call    cs:__imp_IofCallDriver
0x14003acb8  nop     dword ptr [rax+rax+00h]
0x14003acbd  mov     edi, eax
0x14003acbf  cmp     eax, 103h
0x14003acc4  jnz     short loc_14003ACEB
0x14003acc6  xor     r9d, r9d; Alertable
0x14003acc9  mov     [rsp+78h+Timeout], 0; Timeout
0x14003acd2  xor     r8d, r8d; WaitMode
0x14003acd5  lea     rcx, [rsp+78h+Object]; Object
0x14003acda  xor     edx, edx; WaitReason
0x14003acdc  call    cs:__imp_KeWaitForSingleObject
0x14003ace3  nop     dword ptr [rax+rax+00h]
0x14003ace8  mov     edi, [rsi+30h]
0x14003aceb  lock dec dword ptr [rbx+24Ch]
0x14003acf2  test    edi, edi
0x14003acf4  js      short loc_14003AD2A
0x14003acf6  mov     rcx, [rbx+200h]; DriverObject
0x14003acfd  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x14003ad04  call    cs:__imp_IoGetDriverObjectExtension
0x14003ad0b  nop     dword ptr [rax+rax+00h]
0x14003ad10  mov     cl, [rbx+245h]
0x14003ad16  mov     [rbx+244h], cl
0x14003ad1c  mov     byte ptr [rbx+245h], 1
0x14003ad23  lock inc dword ptr [rax+198h]
0x14003ad2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad31  lea     rax, WPP_GLOBAL_Control
0x14003ad38  cmp     rcx, rax
0x14003ad3b  jz      short loc_14003AD66
0x14003ad3d  mov     eax, [rcx+2Ch]
0x14003ad40  test    al, 2
0x14003ad42  jz      short loc_14003AD66
0x14003ad44  cmp     byte ptr [rcx+29h], 4
0x14003ad48  jb      short loc_14003AD66
0x14003ad4a  mov     rcx, [rcx+18h]
0x14003ad4e  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003ad55  mov     edx, 17h
0x14003ad5a  mov     dword ptr [rsp+78h+Timeout], edi
0x14003ad5e  mov     r9, rbp
0x14003ad61  call    WPP_SF_qD
0x14003ad66  cmp     cs:ClassPnPETWEnabled, 0
0x14003ad6d  mov     [rsi+30h], edi
0x14003ad70  jz      short loc_14003ADBF
0x14003ad72  xorps   xmm0, xmm0
0x14003ad75  lea     rdx, [rsp+78h+var_30]
0x14003ad7a  mov     rcx, rsi
0x14003ad7d  movups  [rsp+78h+var_30], xmm0
0x14003ad82  call    cs:__imp_IoGetActivityIdIrp
0x14003ad89  nop     dword ptr [rax+rax+00h]
0x14003ad8e  test    eax, eax
0x14003ad90  js      short loc_14003ADBF
0x14003ad92  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14003ad99  jz      short loc_14003ADBF
0x14003ad9b  mov     eax, [rsi+30h]
0x14003ad9e  lea     r8, [rsp+78h+var_30]
0x14003ada3  mov     r9d, [rbx+240h]
0x14003adaa  lea     rdx, EventPnpRequestComplete
0x14003adb1  mov     [rsp+78h+var_50], eax
0x14003adb5  mov     [rsp+78h+Timeout], rsi
0x14003adba  call    McTemplateK0qpd_EtwWriteTransfer
0x14003adbf  xor     edx, edx; PriorityBoost
0x14003adc1  mov     rcx, rsi; Irp
0x14003adc4  call    cs:__imp_IofCompleteRequest
0x14003adcb  nop     dword ptr [rax+rax+00h]
0x14003add0  mov     eax, edi
0x14003add2  mov     rcx, [rsp+78h+var_20]
0x14003add7  xor     rcx, rsp; StackCookie
0x14003adda  call    __security_check_cookie
0x14003addf  lea     r11, [rsp+78h+var_18]
0x14003ade4  mov     rbx, [r11+30h]
0x14003ade8  mov     rbp, [r11+38h]
0x14003adec  mov     rsp, r11
0x14003adef  pop     r14
0x14003adf1  pop     rdi
0x14003adf2  pop     rsi
0x14003adf3  retn
```
