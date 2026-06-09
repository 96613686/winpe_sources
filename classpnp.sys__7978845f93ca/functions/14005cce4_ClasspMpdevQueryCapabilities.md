# ClasspMpdevQueryCapabilities

- ea: `0x14005cce4`
- end: `0x14005ce56`
- name: `ClasspMpdevQueryCapabilities`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003a790`

## callees

- `0x14002249c`
- `0x14003e430`
- `0x14005cce4`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14005cd83`
- `ntoskrnl!IofCallDriver` at `0x14005cd83`
- `ntoskrnl!KeInitializeEvent` at `0x14005cd4e`
- `ntoskrnl!KeInitializeEvent` at `0x14005cd4e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005cdae`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005cdae`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005cde8`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005cde8`
- `ntoskrnl!IofCompleteRequest` at `0x14005ce2a`
- `ntoskrnl!IofCompleteRequest` at `0x14005ce2a`

## pseudocode

```c
__int64 __fastcall ClasspMpdevQueryCapabilities(__int64 a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  __int64 v3; // rbp
  _IO_STACK_LOCATION *v5; // rax
  NTSTATUS Status; // edi
  _IO_SECURITY_CONTEXT *SecurityContext; // rax
  int v8; // ecx
  struct _KEVENT Event; // [rsp+30h] [rbp-48h] BYREF
  __int128 v11; // [rsp+48h] [rbp-30h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = *(_QWORD *)(a1 + 64);
  a2->IoStatus.Status = 0;
  memset(&Event, 0, sizeof(Event));
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v5 = a2->Tail.Overlay.CurrentStackLocation;
  v5[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ClasspMpdevSyncCompletion;
  v5[-1].Context = &Event;
  v5[-1].Control = -32;
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(v3 + 520), a2);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = a2->IoStatus.Status;
  }
  if ( Status >= 0 )
  {
    SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
    if ( SecurityContext )
      HIDWORD(SecurityContext->SecurityQos) |= 0x200u;
  }
  if ( ClassPnPETWEnabled )
  {
    v11 = 0;
    if ( (int)IoGetActivityIdIrp(a2, &v11) >= 0 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
      McTemplateK0qpd_EtwWriteTransfer(
        v8,
        (unsigned int)EventPnpRequestComplete,
        (unsigned int)&v11,
        *(_DWORD *)(v3 + 576),
        (char)a2,
        Status);
  }
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14005cce4  mov     [rsp+arg_10], rbx
0x14005cce9  push    rbp
0x14005ccea  push    rsi
0x14005cceb  push    rdi
0x14005ccec  sub     rsp, 60h
0x14005ccf0  mov     rax, cs:__security_cookie
0x14005ccf7  xor     rax, rsp
0x14005ccfa  mov     [rsp+78h+var_20], rax
0x14005ccff  mov     rsi, [rdx+0B8h]
0x14005cd06  xor     eax, eax
0x14005cd08  mov     rbp, [rcx+40h]
0x14005cd0c  xorps   xmm0, xmm0
0x14005cd0f  mov     [rdx+30h], eax
0x14005cd12  lea     rcx, [rsp+78h+Event]; Event
0x14005cd17  movups  xmmword ptr [rsp+78h+Event.Header.___u0], xmm0
0x14005cd1c  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x14005cd21  mov     rbx, rdx
0x14005cd24  movups  xmm0, xmmword ptr [rsi]
0x14005cd27  xor     r8d, r8d; State
0x14005cd2a  lea     edx, [rax+1]; Type
0x14005cd2d  movups  xmmword ptr [rsi-48h], xmm0
0x14005cd31  movups  xmm1, xmmword ptr [rsi+10h]
0x14005cd35  movups  xmmword ptr [rsi-38h], xmm1
0x14005cd39  movups  xmm0, xmmword ptr [rsi+20h]
0x14005cd3d  movups  xmmword ptr [rsi-28h], xmm0
0x14005cd41  movsd   xmm1, qword ptr [rsi+30h]
0x14005cd46  movsd   qword ptr [rsi-18h], xmm1
0x14005cd4b  mov     [rsi-45h], al
0x14005cd4e  call    cs:__imp_KeInitializeEvent
0x14005cd55  nop     dword ptr [rax+rax+00h]
0x14005cd5a  mov     rax, [rbx+0B8h]
0x14005cd61  lea     rcx, ClasspMpdevSyncCompletion
0x14005cd68  mov     rdx, rbx; Irp
0x14005cd6b  mov     [rax-10h], rcx
0x14005cd6f  lea     rcx, [rsp+78h+Event]
0x14005cd74  mov     [rax-8], rcx
0x14005cd78  mov     byte ptr [rax-45h], 0E0h
0x14005cd7c  mov     rcx, [rbp+208h]; DeviceObject
0x14005cd83  call    cs:__imp_IofCallDriver
0x14005cd8a  nop     dword ptr [rax+rax+00h]
0x14005cd8f  mov     edi, eax
0x14005cd91  cmp     eax, 103h
0x14005cd96  jnz     short loc_14005CDBD
0x14005cd98  xor     r9d, r9d; Alertable
0x14005cd9b  mov     [rsp+78h+Timeout], 0; Timeout
0x14005cda4  xor     r8d, r8d; WaitMode
0x14005cda7  lea     rcx, [rsp+78h+Event]; Object
0x14005cdac  xor     edx, edx; WaitReason
0x14005cdae  call    cs:__imp_KeWaitForSingleObject
0x14005cdb5  nop     dword ptr [rax+rax+00h]
0x14005cdba  mov     edi, [rbx+30h]
0x14005cdbd  test    edi, edi
0x14005cdbf  js      short loc_14005CDCF
0x14005cdc1  mov     rax, [rsi+8]
0x14005cdc5  test    rax, rax
0x14005cdc8  jz      short loc_14005CDCF
0x14005cdca  bts     dword ptr [rax+4], 9
0x14005cdcf  cmp     cs:ClassPnPETWEnabled, 0
0x14005cdd6  jz      short loc_14005CE22
0x14005cdd8  xorps   xmm0, xmm0
0x14005cddb  lea     rdx, [rsp+78h+var_30]
0x14005cde0  mov     rcx, rbx
0x14005cde3  movups  [rsp+78h+var_30], xmm0
0x14005cde8  call    cs:__imp_IoGetActivityIdIrp
0x14005cdef  nop     dword ptr [rax+rax+00h]
0x14005cdf4  test    eax, eax
0x14005cdf6  js      short loc_14005CE22
0x14005cdf8  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14005cdff  jz      short loc_14005CE22
0x14005ce01  mov     r9d, [rbp+240h]
0x14005ce08  lea     r8, [rsp+78h+var_30]
0x14005ce0d  mov     [rsp+78h+var_50], edi
0x14005ce11  lea     rdx, EventPnpRequestComplete
0x14005ce18  mov     [rsp+78h+Timeout], rbx
0x14005ce1d  call    McTemplateK0qpd_EtwWriteTransfer
0x14005ce22  xor     edx, edx; PriorityBoost
0x14005ce24  mov     [rbx+30h], edi
0x14005ce27  mov     rcx, rbx; Irp
0x14005ce2a  call    cs:__imp_IofCompleteRequest
0x14005ce31  nop     dword ptr [rax+rax+00h]
0x14005ce36  mov     eax, edi
0x14005ce38  mov     rcx, [rsp+78h+var_20]
0x14005ce3d  xor     rcx, rsp; StackCookie
0x14005ce40  call    __security_check_cookie
0x14005ce45  mov     rbx, [rsp+78h+arg_10]
0x14005ce4d  add     rsp, 60h
0x14005ce51  pop     rdi
0x14005ce52  pop     rsi
0x14005ce53  pop     rbp
0x14005ce54  retn
```
