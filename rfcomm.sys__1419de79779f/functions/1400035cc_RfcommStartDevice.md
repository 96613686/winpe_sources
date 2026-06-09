# RfcommStartDevice

- ea: `0x1400035cc`
- end: `0x140003811`
- name: `RfcommStartDevice`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400011ac`

## callees

- `0x1400035cc`
- `0x140003cb4`
- `0x140004a68`
- `0x1400051b4`
- `0x14000916c`
- `0x14000d740`
- `0x14000d83c`
- `0x14000ef48`
- `0x14001bfa8`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140003760`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x140003760`
- `ntoskrnl!IofCompleteRequest` at `0x1400037a6`
- `ntoskrnl!IofCompleteRequest` at `0x1400037a6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400037bf`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400037bf`
- `ntoskrnl!IofCallDriver` at `0x140003697`
- `ntoskrnl!IofCallDriver` at `0x140003697`
- `ntoskrnl!KeInitializeEvent` at `0x140003639`
- `ntoskrnl!KeInitializeEvent` at `0x140003639`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400036b9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400036b9`

## pseudocode

```c
__int64 __fastcall RfcommStartDevice(__int64 a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v5; // rax
  int Status; // edi
  int v7; // eax
  int v8; // edx
  __int64 v9; // rax
  NTSTATUS v10; // eax
  int v11; // edx
  void *DeviceExtension; // rbx
  const char *v13; // rax
  int v14; // edx
  struct _KEVENT Event; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      18,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      a1);
  a2->IoStatus.Status = 0;
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v5 = a2->Tail.Overlay.CurrentStackLocation;
  v5[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ForwardAndWaitComplete;
  v5[-1].Context = &Event;
  v5[-1].Control = -32;
  IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 88), a2);
  KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  Status = a2->IoStatus.Status;
  if ( Status >= 0 )
  {
    if ( *(_DWORD *)(a1 + 112) != 2 )
    {
      v7 = RfcommRegisterProfileDriver(a1);
      Status = v7;
      if ( v7 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            1,
            19,
            (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
            v7);
        goto LABEL_14;
      }
      Status = BrbL2capRegisterServer(a1);
      if ( Status < 0 )
        goto LABEL_14;
      TdiEnsureReservedChannelTableLoaded(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 16LL));
      v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 16LL) + 64LL);
      *(_DWORD *)(v9 + 48) &= ~0x80u;
    }
    Status = BrbGetLocalAddr(a1, a1 + 120);
    if ( Status >= 0 )
    {
      v10 = IoSetDeviceInterfaceState((PUNICODE_STRING)(a1 + 344), 1u);
      Status = v10;
      if ( v10 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          3,
          20,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          v10);
    }
  }
LABEL_14:
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 40), a2, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v13 = NtStatusTxt(Status);
    WPP_RECORDER_SF_s(
      (_DWORD)DeviceExtension,
      v14,
      3,
      21,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      (__int64)v13);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400035cc  push    rbx
0x1400035ce  push    rsi
0x1400035cf  push    rdi
0x1400035d0  push    r14
0x1400035d2  push    r15
0x1400035d4  sub     rsp, 50h
0x1400035d8  mov     rsi, rdx
0x1400035db  mov     rbx, rcx
0x1400035de  lea     r14, WPP_RECORDER_INITIALIZED
0x1400035e5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400035ec  lea     r15, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x1400035f3  jz      short loc_140003619
0x1400035f5  mov     [rsp+78h+var_50], rcx
0x1400035fa  mov     r9d, 12h
0x140003600  mov     rcx, cs:WPP_GLOBAL_Control
0x140003607  mov     [rsp+78h+Timeout], r15
0x14000360c  lea     r8d, [r9-0Fh]
0x140003610  mov     rcx, [rcx+40h]
0x140003614  call    WPP_RECORDER_SF_q
0x140003619  xorps   xmm0, xmm0
0x14000361c  mov     dword ptr [rsi+30h], 0
0x140003623  xor     eax, eax
0x140003625  lea     rcx, [rsp+78h+Event]; Event
0x14000362a  xor     r8d, r8d; State
0x14000362d  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x140003632  xor     edx, edx; Type
0x140003634  movups  xmmword ptr [rsp+78h+Event.Header.___u0], xmm0
0x140003639  call    cs:__imp_KeInitializeEvent
0x140003640  nop     dword ptr [rax+rax+00h]
0x140003645  mov     rax, [rsi+0B8h]
0x14000364c  lea     rcx, ForwardAndWaitComplete
0x140003653  mov     rdx, rsi; Irp
0x140003656  movups  xmm0, xmmword ptr [rax]
0x140003659  movups  xmmword ptr [rax-48h], xmm0
0x14000365d  movups  xmm1, xmmword ptr [rax+10h]
0x140003661  movups  xmmword ptr [rax-38h], xmm1
0x140003665  movups  xmm0, xmmword ptr [rax+20h]
0x140003669  movups  xmmword ptr [rax-28h], xmm0
0x14000366d  movsd   xmm1, qword ptr [rax+30h]
0x140003672  movsd   qword ptr [rax-18h], xmm1
0x140003677  mov     byte ptr [rax-45h], 0
0x14000367b  mov     rax, [rsi+0B8h]
0x140003682  mov     [rax-10h], rcx
0x140003686  lea     rcx, [rsp+78h+Event]
0x14000368b  mov     [rax-8], rcx
0x14000368f  mov     byte ptr [rax-45h], 0E0h
0x140003693  mov     rcx, [rbx+58h]; DeviceObject
0x140003697  call    cs:__imp_IofCallDriver
0x14000369e  nop     dword ptr [rax+rax+00h]
0x1400036a3  xor     r9d, r9d; Alertable
0x1400036a6  mov     [rsp+78h+Timeout], 0; Timeout
0x1400036af  xor     r8d, r8d; WaitMode
0x1400036b2  lea     rcx, [rsp+78h+Event]; Object
0x1400036b7  xor     edx, edx; WaitReason
0x1400036b9  call    cs:__imp_KeWaitForSingleObject
0x1400036c0  nop     dword ptr [rax+rax+00h]
0x1400036c5  mov     edi, [rsi+30h]
0x1400036c8  test    edi, edi
0x1400036ca  js      loc_14000379E
0x1400036d0  cmp     dword ptr [rbx+70h], 2
0x1400036d4  jz      short loc_140003745
0x1400036d6  mov     rcx, rbx
0x1400036d9  call    RfcommRegisterProfileDriver
0x1400036de  mov     edi, eax
0x1400036e0  test    eax, eax
0x1400036e2  jns     short loc_140003719
0x1400036e4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400036eb  jz      loc_14000379E
0x1400036f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036f8  mov     r9d, 13h
0x1400036fe  mov     dword ptr [rsp+78h+var_50], eax
0x140003702  mov     [rsp+78h+Timeout], r15
0x140003707  mov     rcx, [rcx+40h]
0x14000370b  lea     r8d, [r9-12h]
0x14000370f  call    WPP_RECORDER_SF_d
0x140003714  jmp     loc_14000379E
0x140003719  mov     rcx, rbx
0x14000371c  call    BrbL2capRegisterServer
0x140003721  mov     edi, eax
0x140003723  test    eax, eax
0x140003725  js      short loc_14000379E
0x140003727  mov     rcx, [rbx+60h]
0x14000372b  mov     rcx, [rcx+10h]
0x14000372f  call    TdiEnsureReservedChannelTableLoaded
0x140003734  mov     rax, [rbx+60h]
0x140003738  mov     rcx, [rax+10h]
0x14000373c  mov     rax, [rcx+40h]
0x140003740  btr     dword ptr [rax+30h], 7
0x140003745  lea     rdx, [rbx+78h]
0x140003749  mov     rcx, rbx
0x14000374c  call    BrbGetLocalAddr
0x140003751  mov     edi, eax
0x140003753  test    eax, eax
0x140003755  js      short loc_14000379E
0x140003757  lea     rcx, [rbx+158h]; SymbolicLinkName
0x14000375e  mov     dl, 1; Enable
0x140003760  call    cs:__imp_IoSetDeviceInterfaceState
0x140003767  nop     dword ptr [rax+rax+00h]
0x14000376c  mov     edi, eax
0x14000376e  test    eax, eax
0x140003770  jns     short loc_14000379E
0x140003772  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140003779  jz      short loc_14000379E
0x14000377b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003782  mov     r9d, 14h
0x140003788  mov     dword ptr [rsp+78h+var_50], eax
0x14000378c  mov     [rsp+78h+Timeout], r15
0x140003791  mov     rcx, [rcx+40h]
0x140003795  lea     r8d, [r9-11h]
0x140003799  call    WPP_RECORDER_SF_d
0x14000379e  xor     edx, edx; PriorityBoost
0x1400037a0  mov     [rsi+30h], edi
0x1400037a3  mov     rcx, rsi; Irp
0x1400037a6  call    cs:__imp_IofCompleteRequest
0x1400037ad  nop     dword ptr [rax+rax+00h]
0x1400037b2  lea     rcx, [rbx+28h]; RemoveLock
0x1400037b6  mov     r8d, 20h ; ' '; RemlockSize
0x1400037bc  mov     rdx, rsi; Tag
0x1400037bf  call    cs:__imp_IoReleaseRemoveLockEx
0x1400037c6  nop     dword ptr [rax+rax+00h]
0x1400037cb  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400037d2  jz      short loc_140003802
0x1400037d4  mov     rax, cs:WPP_GLOBAL_Control
0x1400037db  mov     ecx, edi
0x1400037dd  mov     rbx, [rax+40h]
0x1400037e1  call    NtStatusTxt
0x1400037e6  mov     r9d, 15h
0x1400037ec  mov     [rsp+78h+var_50], rax
0x1400037f1  mov     rcx, rbx
0x1400037f4  mov     [rsp+78h+Timeout], r15
0x1400037f9  lea     r8d, [r9-12h]
0x1400037fd  call    WPP_RECORDER_SF_s
0x140003802  mov     eax, edi
0x140003804  add     rsp, 50h
0x140003808  pop     r15
0x14000380a  pop     r14
0x14000380c  pop     rdi
0x14000380d  pop     rsi
0x14000380e  pop     rbx
0x14000380f  retn
```
