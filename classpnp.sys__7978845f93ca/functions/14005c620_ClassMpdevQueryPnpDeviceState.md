# ClassMpdevQueryPnpDeviceState

- ea: `0x14005c620`
- end: `0x14005c799`
- name: `ClassMpdevQueryPnpDeviceState`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003a790`

## callees

- `0x14002249c`
- `0x14003e430`
- `0x14005c620`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14005c6c3`
- `ntoskrnl!IofCallDriver` at `0x14005c6c3`
- `ntoskrnl!KeInitializeEvent` at `0x14005c68e`
- `ntoskrnl!KeInitializeEvent` at `0x14005c68e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005c6ec`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005c6ec`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005c729`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005c729`
- `ntoskrnl!IofCompleteRequest` at `0x14005c76b`
- `ntoskrnl!IofCompleteRequest` at `0x14005c76b`

## pseudocode

```c
__int64 __fastcall ClassMpdevQueryPnpDeviceState(__int64 a1, IRP *a2)
{
  __int64 v2; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v5; // rax
  int Status; // edi
  int v7; // ecx
  struct _KEVENT Object; // [rsp+30h] [rbp-38h] BYREF
  __int128 v10; // [rsp+48h] [rbp-20h] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  *(_OWORD *)&Object.Header.Lock = 0;
  a2->IoStatus.Status = 0;
  Object.Header.WaitListHead.Blink = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  KeInitializeEvent(&Object, SynchronizationEvent, 0);
  v5 = a2->Tail.Overlay.CurrentStackLocation;
  v5[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ClasspMpdevSyncCompletion;
  v5[-1].Context = &Object;
  v5[-1].Control = -32;
  if ( IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 520), a2) == 259 )
    KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
  Status = a2->IoStatus.Status;
  if ( Status < 0 )
  {
    Status = 0;
    a2->IoStatus.Information = 2;
  }
  else
  {
    a2->IoStatus.Information |= 2uLL;
  }
  if ( ClassPnPETWEnabled )
  {
    v10 = 0;
    if ( (int)IoGetActivityIdIrp(a2, &v10) >= 0 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
      McTemplateK0qpd_EtwWriteTransfer(
        v7,
        (unsigned int)EventPnpRequestComplete,
        (unsigned int)&v10,
        *(_DWORD *)(v2 + 576),
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
0x14005c620  mov     r11, rsp
0x14005c623  mov     [r11+18h], rbx
0x14005c627  mov     [r11+20h], rsi
0x14005c62b  push    rdi
0x14005c62c  sub     rsp, 60h
0x14005c630  mov     rax, cs:__security_cookie
0x14005c637  xor     rax, rsp
0x14005c63a  mov     [rsp+68h+var_10], rax
0x14005c63f  mov     rsi, [rcx+40h]
0x14005c643  xorps   xmm0, xmm0
0x14005c646  movups  xmmword ptr [rsp+68h+Object], xmm0
0x14005c64b  xor     eax, eax
0x14005c64d  lea     rcx, [r11-38h]; Event
0x14005c651  mov     [rdx+30h], eax
0x14005c654  xor     r8d, r8d; State
0x14005c657  mov     [r11-28h], rax
0x14005c65b  mov     rbx, rdx
0x14005c65e  mov     rax, [rdx+0B8h]
0x14005c665  lea     edx, [r8+1]; Type
0x14005c669  movups  xmm0, xmmword ptr [rax]
0x14005c66c  movups  xmmword ptr [rax-48h], xmm0
0x14005c670  movups  xmm1, xmmword ptr [rax+10h]
0x14005c674  movups  xmmword ptr [rax-38h], xmm1
0x14005c678  movups  xmm0, xmmword ptr [rax+20h]
0x14005c67c  movups  xmmword ptr [rax-28h], xmm0
0x14005c680  movsd   xmm1, qword ptr [rax+30h]
0x14005c685  movsd   qword ptr [rax-18h], xmm1
0x14005c68a  mov     byte ptr [rax-45h], 0
0x14005c68e  call    cs:__imp_KeInitializeEvent
0x14005c695  nop     dword ptr [rax+rax+00h]
0x14005c69a  mov     rax, [rbx+0B8h]
0x14005c6a1  lea     rcx, ClasspMpdevSyncCompletion
0x14005c6a8  mov     rdx, rbx; Irp
0x14005c6ab  mov     [rax-10h], rcx
0x14005c6af  lea     rcx, [rsp+68h+Object]
0x14005c6b4  mov     [rax-8], rcx
0x14005c6b8  mov     byte ptr [rax-45h], 0E0h
0x14005c6bc  mov     rcx, [rsi+208h]; DeviceObject
0x14005c6c3  call    cs:__imp_IofCallDriver
0x14005c6ca  nop     dword ptr [rax+rax+00h]
0x14005c6cf  cmp     eax, 103h
0x14005c6d4  jnz     short loc_14005C6F8
0x14005c6d6  xor     r9d, r9d; Alertable
0x14005c6d9  mov     [rsp+68h+Timeout], 0; Timeout
0x14005c6e2  xor     r8d, r8d; WaitMode
0x14005c6e5  lea     rcx, [rsp+68h+Object]; Object
0x14005c6ea  xor     edx, edx; WaitReason
0x14005c6ec  call    cs:__imp_KeWaitForSingleObject
0x14005c6f3  nop     dword ptr [rax+rax+00h]
0x14005c6f8  mov     edi, [rbx+30h]
0x14005c6fb  test    edi, edi
0x14005c6fd  js      short loc_14005C706
0x14005c6ff  or      qword ptr [rbx+38h], 2
0x14005c704  jmp     short loc_14005C710
0x14005c706  xor     edi, edi
0x14005c708  mov     qword ptr [rbx+38h], 2
0x14005c710  cmp     cs:ClassPnPETWEnabled, 0
0x14005c717  jz      short loc_14005C763
0x14005c719  xorps   xmm0, xmm0
0x14005c71c  lea     rdx, [rsp+68h+var_20]
0x14005c721  mov     rcx, rbx
0x14005c724  movups  [rsp+68h+var_20], xmm0
0x14005c729  call    cs:__imp_IoGetActivityIdIrp
0x14005c730  nop     dword ptr [rax+rax+00h]
0x14005c735  test    eax, eax
0x14005c737  js      short loc_14005C763
0x14005c739  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14005c740  jz      short loc_14005C763
0x14005c742  mov     r9d, [rsi+240h]
0x14005c749  lea     r8, [rsp+68h+var_20]
0x14005c74e  mov     [rsp+68h+var_40], edi
0x14005c752  lea     rdx, EventPnpRequestComplete
0x14005c759  mov     [rsp+68h+Timeout], rbx
0x14005c75e  call    McTemplateK0qpd_EtwWriteTransfer
0x14005c763  xor     edx, edx; PriorityBoost
0x14005c765  mov     [rbx+30h], edi
0x14005c768  mov     rcx, rbx; Irp
0x14005c76b  call    cs:__imp_IofCompleteRequest
0x14005c772  nop     dword ptr [rax+rax+00h]
0x14005c777  mov     eax, edi
0x14005c779  mov     rcx, [rsp+68h+var_10]
0x14005c77e  xor     rcx, rsp; StackCookie
0x14005c781  call    __security_check_cookie
0x14005c786  lea     r11, [rsp+68h+var_8]
0x14005c78b  mov     rbx, [r11+20h]
0x14005c78f  mov     rsi, [r11+28h]
0x14005c793  mov     rsp, r11
0x14005c796  pop     rdi
0x14005c797  retn
```
