# ClasspMpdevStartDevice

- ea: `0x14003b364`
- end: `0x14003b5fb`
- name: `ClasspMpdevStartDevice`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003a790`

## callees

- `0x14001fbf4`
- `0x14002249c`
- `0x14003b364`
- `0x14003e430`
- `0x14005e2e0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14003b420`
- `ntoskrnl!IofCallDriver` at `0x14003b420`
- `ntoskrnl!KeInitializeEvent` at `0x14003b3ec`
- `ntoskrnl!KeInitializeEvent` at `0x14003b3ec`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003b44a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003b44a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003b584`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003b584`
- `ntoskrnl!IofCompleteRequest` at `0x14003b5c8`
- `ntoskrnl!IofCompleteRequest` at `0x14003b5c8`

## pseudocode

```c
__int64 __fastcall ClasspMpdevStartDevice(__int64 a1, IRP *a2)
{
  __int64 v2; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v6; // rax
  NTSTATUS Status; // edi
  int v8; // ecx
  __int128 Buffer; // [rsp+40h] [rbp-9h] BYREF
  __int128 v11; // [rsp+50h] [rbp+7h]
  struct _KEVENT Event; // [rsp+60h] [rbp+17h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+78h] [rbp+2Fh] BYREF

  v2 = *(_QWORD *)(a1 + 64);
  *(_OWORD *)&Event.Header.Lock = 0;
  a2->IoStatus.Status = 0;
  Event.Header.WaitListHead.Blink = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Buffer = 0;
  v11 = 0;
  IoStatus = 0;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v6 = a2->Tail.Overlay.CurrentStackLocation;
  v6[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ClasspMpdevSyncCompletion;
  v6[-1].Context = &Event;
  v6[-1].Control = -32;
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 520), a2);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = a2->IoStatus.Status;
  }
  if ( Status >= 0 )
  {
    Status = 0;
    *(_DWORD *)(a1 + 48) |= *(_DWORD *)(*(_QWORD *)(v2 + 520) + 48LL);
    *(_DWORD *)(a1 + 52) |= *(_DWORD *)(*(_QWORD *)(v2 + 520) + 52LL);
    *(_BYTE *)(v2 + 581) = *(_BYTE *)(v2 + 580);
    *(_BYTE *)(v2 + 580) = 0;
    if ( !*(_BYTE *)(v2 + 583) )
    {
      if ( *(_QWORD *)(v2 + 568) )
      {
        *(_QWORD *)&Buffer = *(_QWORD *)(v2 + 8);
        *((_QWORD *)&Buffer + 1) = *(_QWORD *)(v2 + 528);
        *(_QWORD *)&v11 = ClasspMpdevDeviceRemovedNotify;
        ClassSendDeviceIoControlSynchronous(
          0x6D70C04Cu,
          *(PDEVICE_OBJECT *)(v2 + 568),
          &Buffer,
          0x18u,
          0x20u,
          1u,
          &IoStatus);
        Status = IoStatus.Status;
        if ( IoStatus.Status < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              28,
              WPP_a63e98891b663a71e40facba1bb231b0_Traceguids,
              (unsigned int)IoStatus.Status);
          }
          Status = 0;
        }
        else
        {
          *(_DWORD *)(v2 + 544) = DWORD2(Buffer);
          *(_QWORD *)(v2 + 536) = Buffer;
          *(_OWORD *)(v2 + 552) = v11;
          *(_BYTE *)(v2 + 583) = 1;
        }
      }
    }
  }
  if ( ClassPnPETWEnabled )
  {
    IoStatus = 0;
    if ( (int)IoGetActivityIdIrp(a2, &IoStatus) >= 0 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
      McTemplateK0qpd_EtwWriteTransfer(
        v8,
        (unsigned int)EventPnpRequestComplete,
        (unsigned int)&IoStatus,
        *(_DWORD *)(v2 + 576),
        (char)a2,
        a2->IoStatus.Status);
  }
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14003b364  mov     [rsp-8+arg_10], rbx
0x14003b369  mov     [rsp-8+arg_18], rsi
0x14003b36e  push    rbp
0x14003b36f  push    rdi
0x14003b370  push    r14
0x14003b372  lea     rbp, [rsp-47h]
0x14003b377  sub     rsp, 90h
0x14003b37e  mov     rax, cs:__security_cookie
0x14003b385  xor     rax, rsp
0x14003b388  mov     [rbp+57h+var_18], rax
0x14003b38c  mov     rbx, [rcx+40h]
0x14003b390  xorps   xmm0, xmm0
0x14003b393  movups  xmmword ptr [rbp+57h+Event.Header.___u0], xmm0
0x14003b397  xor     eax, eax
0x14003b399  xor     r8d, r8d; State
0x14003b39c  mov     [rdx+30h], eax
0x14003b39f  xorps   xmm1, xmm1
0x14003b3a2  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14003b3a6  mov     rsi, rdx
0x14003b3a9  mov     rax, [rdx+0B8h]
0x14003b3b0  mov     r14, rcx
0x14003b3b3  movups  [rbp+57h+Buffer], xmm1
0x14003b3b7  lea     edx, [r8+1]; Type
0x14003b3bb  movups  [rbp+57h+var_50], xmm1
0x14003b3bf  lea     rcx, [rbp+57h+Event]; Event
0x14003b3c3  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x14003b3c7  movups  xmm0, xmmword ptr [rax]
0x14003b3ca  movups  xmmword ptr [rax-48h], xmm0
0x14003b3ce  movups  xmm1, xmmword ptr [rax+10h]
0x14003b3d2  movups  xmmword ptr [rax-38h], xmm1
0x14003b3d6  movups  xmm0, xmmword ptr [rax+20h]
0x14003b3da  movups  xmmword ptr [rax-28h], xmm0
0x14003b3de  movsd   xmm1, qword ptr [rax+30h]
0x14003b3e3  movsd   qword ptr [rax-18h], xmm1
0x14003b3e8  mov     byte ptr [rax-45h], 0
0x14003b3ec  call    cs:__imp_KeInitializeEvent
0x14003b3f3  nop     dword ptr [rax+rax+00h]
0x14003b3f8  mov     rax, [rsi+0B8h]
0x14003b3ff  lea     rcx, ClasspMpdevSyncCompletion
0x14003b406  mov     rdx, rsi; Irp
0x14003b409  mov     [rax-10h], rcx
0x14003b40d  lea     rcx, [rbp+57h+Event]
0x14003b411  mov     [rax-8], rcx
0x14003b415  mov     byte ptr [rax-45h], 0E0h
0x14003b419  mov     rcx, [rbx+208h]; DeviceObject
0x14003b420  call    cs:__imp_IofCallDriver
0x14003b427  nop     dword ptr [rax+rax+00h]
0x14003b42c  mov     edi, eax
0x14003b42e  cmp     eax, 103h
0x14003b433  jnz     short loc_14003B459
0x14003b435  xor     r9d, r9d; Alertable
0x14003b438  mov     [rsp+0A0h+Timeout], 0; Timeout
0x14003b441  xor     r8d, r8d; WaitMode
0x14003b444  lea     rcx, [rbp+57h+Event]; Object
0x14003b448  xor     edx, edx; WaitReason
0x14003b44a  call    cs:__imp_KeWaitForSingleObject
0x14003b451  nop     dword ptr [rax+rax+00h]
0x14003b456  mov     edi, [rsi+30h]
0x14003b459  test    edi, edi
0x14003b45b  js      loc_14003B56D
0x14003b461  mov     rax, [rbx+208h]
0x14003b468  xor     edi, edi
0x14003b46a  mov     ecx, [rax+30h]
0x14003b46d  or      [r14+30h], ecx
0x14003b471  mov     rax, [rbx+208h]
0x14003b478  mov     ecx, [rax+34h]
0x14003b47b  or      [r14+34h], ecx
0x14003b47f  mov     al, [rbx+244h]
0x14003b485  mov     [rbx+245h], al
0x14003b48b  mov     byte ptr [rbx+244h], 0
0x14003b492  cmp     [rbx+247h], dil
0x14003b499  jnz     loc_14003B56D
0x14003b49f  cmp     [rbx+238h], rdi
0x14003b4a6  jz      loc_14003B56D
0x14003b4ac  mov     rax, [rbx+8]
0x14003b4b0  lea     r9d, [rdi+18h]; InputBufferLength
0x14003b4b4  mov     qword ptr [rbp+57h+Buffer], rax
0x14003b4b8  lea     r8, [rbp+57h+Buffer]; Buffer
0x14003b4bc  mov     rax, [rbx+210h]
0x14003b4c3  mov     ecx, 6D70C04Ch; IoControlCode
0x14003b4c8  mov     qword ptr [rbp+57h+Buffer+8], rax
0x14003b4cc  lea     rax, ClasspMpdevDeviceRemovedNotify
0x14003b4d3  mov     qword ptr [rbp+57h+var_50], rax
0x14003b4d7  lea     rax, [rbp+57h+var_28]
0x14003b4db  mov     rdx, [rbx+238h]; TargetDeviceObject
0x14003b4e2  mov     [rsp+0A0h+IoStatus], rax; IoStatus
0x14003b4e7  mov     [rsp+0A0h+InternalDeviceIoControl], 1; InternalDeviceIoControl
0x14003b4ec  mov     dword ptr [rsp+0A0h+Timeout], 20h ; ' '; OutputBufferLength
0x14003b4f4  call    ClassSendDeviceIoControlSynchronous
0x14003b4f9  mov     edi, dword ptr [rbp+57h+var_28]
0x14003b4fc  test    edi, edi
0x14003b4fe  js      short loc_14003B533
0x14003b500  mov     eax, dword ptr [rbp+57h+Buffer+8]
0x14003b503  mov     [rbx+220h], eax
0x14003b509  mov     rax, qword ptr [rbp+57h+Buffer]
0x14003b50d  mov     [rbx+218h], rax
0x14003b514  mov     rax, qword ptr [rbp+57h+var_50+8]
0x14003b518  mov     [rbx+230h], rax
0x14003b51f  mov     rax, qword ptr [rbp+57h+var_50]
0x14003b523  mov     [rbx+228h], rax
0x14003b52a  mov     byte ptr [rbx+247h], 1
0x14003b531  jmp     short loc_14003B56D
0x14003b533  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b53a  lea     rax, WPP_GLOBAL_Control
0x14003b541  cmp     rcx, rax
0x14003b544  jz      short loc_14003B56B
0x14003b546  mov     eax, [rcx+2Ch]
0x14003b549  test    al, 2
0x14003b54b  jz      short loc_14003B56B
0x14003b54d  cmp     byte ptr [rcx+29h], 4
0x14003b551  jb      short loc_14003B56B
0x14003b553  mov     rcx, [rcx+18h]
0x14003b557  lea     r8, WPP_a63e98891b663a71e40facba1bb231b0_Traceguids
0x14003b55e  mov     edx, 1Ch
0x14003b563  mov     r9d, edi
0x14003b566  call    WPP_SF_d
0x14003b56b  xor     edi, edi
0x14003b56d  cmp     cs:ClassPnPETWEnabled, 0
0x14003b574  jz      short loc_14003B5C0
0x14003b576  xorps   xmm0, xmm0
0x14003b579  lea     rdx, [rbp+57h+var_28]
0x14003b57d  mov     rcx, rsi
0x14003b580  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x14003b584  call    cs:__imp_IoGetActivityIdIrp
0x14003b58b  nop     dword ptr [rax+rax+00h]
0x14003b590  test    eax, eax
0x14003b592  js      short loc_14003B5C0
0x14003b594  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14003b59b  jz      short loc_14003B5C0
0x14003b59d  mov     eax, [rsi+30h]
0x14003b5a0  lea     r8, [rbp+57h+var_28]
0x14003b5a4  mov     r9d, [rbx+240h]
0x14003b5ab  lea     rdx, EventPnpRequestComplete
0x14003b5b2  mov     dword ptr [rsp+0A0h+InternalDeviceIoControl], eax
0x14003b5b6  mov     [rsp+0A0h+Timeout], rsi
0x14003b5bb  call    McTemplateK0qpd_EtwWriteTransfer
0x14003b5c0  xor     edx, edx; PriorityBoost
0x14003b5c2  mov     [rsi+30h], edi
0x14003b5c5  mov     rcx, rsi; Irp
0x14003b5c8  call    cs:__imp_IofCompleteRequest
0x14003b5cf  nop     dword ptr [rax+rax+00h]
0x14003b5d4  mov     eax, edi
0x14003b5d6  mov     rcx, [rbp+57h+var_18]
0x14003b5da  xor     rcx, rsp; StackCookie
0x14003b5dd  call    __security_check_cookie
0x14003b5e2  lea     r11, [rsp+0A0h+var_10]
0x14003b5ea  mov     rbx, [r11+30h]
0x14003b5ee  mov     rsi, [r11+38h]
0x14003b5f2  mov     rsp, r11
0x14003b5f5  pop     r14
0x14003b5f7  pop     rdi
0x14003b5f8  pop     rbp
0x14003b5f9  retn
```
