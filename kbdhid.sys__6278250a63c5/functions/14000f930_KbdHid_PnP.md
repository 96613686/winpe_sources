# KbdHid_PnP

- ea: `0x14000f930`
- end: `0x14000fd45`
- name: `KbdHid_PnP`
- size: `1045`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PVOID Tag)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001d30`
- `0x140004c20`
- `0x140005710`
- `0x140005a0c`
- `0x1400067e4`
- `0x14000f930`
- `0x14000ff70`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14000fced`
- `ntoskrnl!IoFreeMdl` at `0x14000fced`
- `ntoskrnl!IofCallDriver` at `0x14000fad4`
- `ntoskrnl!IofCallDriver` at `0x14000fb6c`
- `ntoskrnl!IofCallDriver` at `0x14000fc81`
- `ntoskrnl!IofCallDriver` at `0x14000fad4`
- `ntoskrnl!IofCallDriver` at `0x14000fb6c`
- `ntoskrnl!IofCallDriver` at `0x14000fc81`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fcd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fcfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fcd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fcfe`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000fb32`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000fba3`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000fb32`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000fba3`
- `ntoskrnl!IofCompleteRequest` at `0x14000f99b`
- `ntoskrnl!IofCompleteRequest` at `0x14000fa5a`
- `ntoskrnl!IofCompleteRequest` at `0x14000f99b`
- `ntoskrnl!IofCompleteRequest` at `0x14000fa5a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fafd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fc4f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fafd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fc4f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000fc2e`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000fc2e`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14000fc9f`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14000fc9f`
- `ntoskrnl!IoCancelIrp` at `0x14000fc5f`
- `ntoskrnl!IoCancelIrp` at `0x14000fc5f`
- `ntoskrnl!IoDetachDevice` at `0x14000fd16`
- `ntoskrnl!IoDetachDevice` at `0x14000fd16`
- `ntoskrnl!IoFreeIrp` at `0x14000fcaf`
- `ntoskrnl!IoFreeIrp` at `0x14000fcaf`
- `ntoskrnl!IoDeleteDevice` at `0x14000fd25`
- `ntoskrnl!IoDeleteDevice` at `0x14000fd25`
- `ntoskrnl!KeCancelTimer` at `0x14000fbfd`
- `ntoskrnl!KeCancelTimer` at `0x14000fbfd`
- `ntoskrnl!IoFreeWorkItem` at `0x14000fcc2`
- `ntoskrnl!IoFreeWorkItem` at `0x14000fcc2`
- `ntoskrnl!KeInitializeEvent` at `0x14000faa3`
- `ntoskrnl!KeInitializeEvent` at `0x14000faa3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000fb8a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000fb8a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000f97d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000f97d`

## pseudocode

```c
__int64 __fastcall KbdHid_PnP(PDEVICE_OBJECT DeviceObject, IRP *Tag)
{
  PDEVICE_OBJECT *DeviceExtension; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  PDEVICE_OBJECT v5; // r12
  NTSTATUS v7; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  NTSTATUS Status; // esi
  unsigned __int64 v12; // rdx
  struct _IO_STACK_LOCATION *v13; // rax
  struct _IO_STACK_LOCATION *v14; // rax
  int RemlockSize; // [rsp+20h] [rbp-68h]
  union _LARGE_INTEGER Interval; // [rsp+90h] [rbp+8h] BYREF

  DeviceExtension = (PDEVICE_OBJECT *)DeviceObject->DeviceExtension;
  CurrentStackLocation = Tag->Tail.Overlay.CurrentStackLocation;
  Interval.QuadPart = 0;
  v5 = DeviceExtension[14];
  v7 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 19), Tag, File, 1u, 0x20u);
  Status = v7;
  if ( v7 < 0 )
  {
    Tag->IoStatus.Information = 0;
    Tag->IoStatus.Status = v7;
    IofCompleteRequest(Tag, 0);
    return (unsigned int)Status;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqc(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      v9,
      v10,
      RemlockSize,
      (char)DeviceObject,
      (char)Tag,
      CurrentStackLocation->MinorFunction);
  if ( CurrentStackLocation->MinorFunction != 2 )
  {
    v12 = 0x140000000uLL;
    switch ( CurrentStackLocation->MinorFunction )
    {
      case 0u:
        if ( *((_BYTE *)DeviceExtension + 88) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = 4;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v12,
              5,
              20,
              (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids);
          }
          Status = 0;
          Tag->IoStatus.Status = 0;
LABEL_11:
          IofCompleteRequest(Tag, 0);
LABEL_24:
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 19), Tag, 0x20u);
          return (unsigned int)Status;
        }
        v13 = Tag->Tail.Overlay.CurrentStackLocation;
        *(_OWORD *)&v13[-1].MajorFunction = *(_OWORD *)&v13->MajorFunction;
        *(_OWORD *)&v13[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v13->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&v13[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v13->Parameters.SetQuota + 6);
        v13[-1].FileObject = v13->FileObject;
        v13[-1].Control = 0;
        KeInitializeEvent((PRKEVENT)DeviceExtension + 10, NotificationEvent, 0);
        v14 = Tag->Tail.Overlay.CurrentStackLocation;
        v14[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)KbdHid_PnPComplete;
        v14[-1].Context = DeviceExtension;
        v14[-1].Control = -32;
        Tag->IoStatus.Status = 0;
        Status = IofCallDriver(DeviceExtension[1], Tag);
        if ( Status == 259 )
        {
          KeWaitForSingleObject(DeviceExtension + 30, Executive, 0, 0, 0);
          Status = Tag->IoStatus.Status;
        }
        if ( Status < 0 || Tag->IoStatus.Status < 0 )
          goto LABEL_20;
        if ( *((_BYTE *)DeviceExtension + 90) )
          goto LABEL_19;
        Status = KbdHid_StartDevice(DeviceExtension);
        if ( Status >= 0 )
        {
          IoWMIRegistrationControl(DeviceObject, 1u);
          *((_BYTE *)DeviceExtension + 90) = 1;
LABEL_19:
          *((_BYTE *)DeviceExtension + 88) = 1;
        }
LABEL_20:
        Tag->IoStatus.Status = Status;
        Tag->IoStatus.Information = 0;
        goto LABEL_11;
      case 1u:
      case 3u:
      case 5u:
      case 6u:
      case 0x17u:
        goto LABEL_22;
      case 4u:
        *((_BYTE *)DeviceExtension + 88) = 0;
LABEL_22:
        Tag->IoStatus.Status = 0;
        goto LABEL_23;
      default:
LABEL_23:
        ++Tag->CurrentLocation;
        ++Tag->Tail.Overlay.CurrentStackLocation;
        Status = IofCallDriver(DeviceExtension[1], Tag);
        goto LABEL_24;
    }
  }
  IoWMIRegistrationControl(*DeviceExtension, 2u);
  Interval.QuadPart = (LONGLONG)DeviceExtension[62];
  if ( DeviceExtension[100] && (__int64)(MEMORY[0xFFFFF78000000014] - (_QWORD)DeviceExtension[100]) > 250 )
    TraceLoggingKeyRepeatOnRemoval();
  KbdHid_CancelAutoRepeatTimer(DeviceExtension);
  KeCancelTimer((PKTIMER)DeviceExtension + 9);
  if ( (__int64)DeviceExtension[80] < Interval.QuadPart )
    Interval.QuadPart = (LONGLONG)DeviceExtension[80];
  KeDelayExecutionThread(0, 0, &Interval);
  *((_BYTE *)DeviceExtension + 89) = 1;
  KeWaitForSingleObject(DeviceExtension + 8, Executive, 0, 0, 0);
  IoCancelIrp((PIRP)DeviceExtension[13]);
  ++Tag->CurrentLocation;
  ++Tag->Tail.Overlay.CurrentStackLocation;
  Tag->IoStatus.Status = 0;
  Status = IofCallDriver(DeviceExtension[1], Tag);
  IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)(DeviceExtension + 19), Tag, 0x20u);
  IoFreeIrp((PIRP)DeviceExtension[13]);
  IoFreeWorkItem((PIO_WORKITEM)DeviceExtension[95]);
  if ( v5 )
  {
    ExFreePoolWithTag(*(PVOID *)&v5->Type, 0);
    IoFreeMdl((PMDL)v5->Queue.Wcb.BufferChainingDpc);
    ExFreePoolWithTag(v5, 0);
  }
  FreeKeyboardUsageMappingList(DeviceExtension);
  IoDetachDevice(DeviceExtension[1]);
  IoDeleteDevice(*DeviceExtension);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000f930  push    rbx
0x14000f932  push    rbp
0x14000f933  push    rsi
0x14000f934  push    rdi
0x14000f935  push    r12
0x14000f937  push    r13
0x14000f939  push    r14
0x14000f93b  push    r15
0x14000f93d  sub     rsp, 48h
0x14000f941  mov     rdi, [rcx+40h]
0x14000f945  lea     r8, File; File
0x14000f94c  mov     r15, [rdx+0B8h]
0x14000f953  mov     r14, rcx
0x14000f956  xor     r13d, r13d
0x14000f959  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x14000f961  mov     qword ptr [rsp+88h+Interval], r13
0x14000f969  mov     r9d, 1; Line
0x14000f96f  mov     r12, [rdi+70h]
0x14000f973  lea     rcx, [rdi+98h]; RemoveLock
0x14000f97a  mov     rbx, rdx
0x14000f97d  call    cs:__imp_IoAcquireRemoveLockEx
0x14000f984  nop     dword ptr [rax+rax+00h]
0x14000f989  mov     esi, eax
0x14000f98b  test    eax, eax
0x14000f98d  jns     short loc_14000F9AC
0x14000f98f  xor     edx, edx; PriorityBoost
0x14000f991  mov     [rbx+38h], r13
0x14000f995  mov     rcx, rbx; Irp
0x14000f998  mov     [rbx+30h], eax
0x14000f99b  call    cs:__imp_IofCompleteRequest
0x14000f9a2  nop     dword ptr [rax+rax+00h]
0x14000f9a7  jmp     loc_14000FD31
0x14000f9ac  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000f9b3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000f9ba  jz      short loc_14000F9DF
0x14000f9bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f9c3  movzx   eax, byte ptr [r15+1]
0x14000f9c8  mov     [rsp+88h+var_50], al
0x14000f9cc  mov     [rsp+88h+var_58], rbx
0x14000f9d1  mov     rcx, [rcx+40h]
0x14000f9d5  mov     [rsp+88h+var_60], r14
0x14000f9da  call    WPP_RECORDER_SF_qqc
0x14000f9df  movzx   eax, byte ptr [r15+1]
0x14000f9e4  cmp     eax, 2
0x14000f9e7  jz      loc_14000FB9B
0x14000f9ed  cmp     eax, 17h; switch 24 cases
0x14000f9f0  ja      def_14000FA0F; jumptable 000000014000FA0F default case, cases 2,7-22
0x14000f9f6  lea     rdx, cs:140000000h
0x14000f9fd  movzx   eax, ds:(byte_140009614 - 140000000h)[rdx+rax]
0x14000fa05  mov     ecx, ds:(jpt_14000FA0F - 140000000h)[rdx+rax*4]
0x14000fa0c  add     rcx, rdx
0x14000fa0f  jmp     rcx; switch jump
0x14000fa15  cmp     [rdi+58h], r13b; jumptable 000000014000FA0F case 0
0x14000fa19  jz      short loc_14000FA6B
0x14000fa1b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14000fa22  jz      short loc_14000FA4E
0x14000fa24  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa2b  lea     rax, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x14000fa32  mov     r9d, 14h
0x14000fa38  mov     qword ptr [rsp+88h+RemlockSize], rax
0x14000fa3d  mov     r8d, 5
0x14000fa43  mov     dl, 4
0x14000fa45  mov     rcx, [rcx+40h]
0x14000fa49  call    WPP_RECORDER_SF_
0x14000fa4e  mov     esi, r13d
0x14000fa51  mov     [rbx+30h], r13d
0x14000fa55  xor     edx, edx; PriorityBoost
0x14000fa57  mov     rcx, rbx; Irp
0x14000fa5a  call    cs:__imp_IofCompleteRequest
0x14000fa61  nop     dword ptr [rax+rax+00h]
0x14000fa66  jmp     loc_14000FB7A
0x14000fa6b  mov     rax, [rbx+0B8h]
0x14000fa72  lea     rcx, [rdi+0F0h]; Event
0x14000fa79  xor     r8d, r8d; State
0x14000fa7c  xor     edx, edx; Type
0x14000fa7e  movups  xmm0, xmmword ptr [rax]
0x14000fa81  movups  xmmword ptr [rax-48h], xmm0
0x14000fa85  movups  xmm1, xmmword ptr [rax+10h]
0x14000fa89  movups  xmmword ptr [rax-38h], xmm1
0x14000fa8d  movups  xmm0, xmmword ptr [rax+20h]
0x14000fa91  movups  xmmword ptr [rax-28h], xmm0
0x14000fa95  movsd   xmm1, qword ptr [rax+30h]
0x14000fa9a  movsd   qword ptr [rax-18h], xmm1
0x14000fa9f  mov     [rax-45h], r13b
0x14000faa3  call    cs:__imp_KeInitializeEvent
0x14000faaa  nop     dword ptr [rax+rax+00h]
0x14000faaf  mov     rax, [rbx+0B8h]
0x14000fab6  lea     rcx, KbdHid_PnPComplete
0x14000fabd  mov     rdx, rbx; Irp
0x14000fac0  mov     [rax-10h], rcx
0x14000fac4  mov     [rax-8], rdi
0x14000fac8  mov     byte ptr [rax-45h], 0E0h
0x14000facc  mov     [rbx+30h], r13d
0x14000fad0  mov     rcx, [rdi+8]; DeviceObject
0x14000fad4  call    cs:__imp_IofCallDriver
0x14000fadb  nop     dword ptr [rax+rax+00h]
0x14000fae0  mov     esi, eax
0x14000fae2  cmp     eax, 103h
0x14000fae7  jnz     short loc_14000FB0C
0x14000fae9  xor     r9d, r9d; Alertable
0x14000faec  mov     qword ptr [rsp+88h+RemlockSize], r13; Timeout
0x14000faf1  xor     r8d, r8d; WaitMode
0x14000faf4  lea     rcx, [rdi+0F0h]; Object
0x14000fafb  xor     edx, edx; WaitReason
0x14000fafd  call    cs:__imp_KeWaitForSingleObject
0x14000fb04  nop     dword ptr [rax+rax+00h]
0x14000fb09  mov     esi, [rbx+30h]
0x14000fb0c  test    esi, esi
0x14000fb0e  js      short loc_14000FB46
0x14000fb10  cmp     [rbx+30h], r13d
0x14000fb14  jl      short loc_14000FB46
0x14000fb16  cmp     [rdi+5Ah], r13b
0x14000fb1a  jnz     short loc_14000FB42
0x14000fb1c  mov     rcx, rdi; Context
0x14000fb1f  call    KbdHid_StartDevice
0x14000fb24  mov     esi, eax
0x14000fb26  test    eax, eax
0x14000fb28  js      short loc_14000FB46
0x14000fb2a  mov     edx, 1; Action
0x14000fb2f  mov     rcx, r14; DeviceObject
0x14000fb32  call    cs:__imp_IoWMIRegistrationControl
0x14000fb39  nop     dword ptr [rax+rax+00h]
0x14000fb3e  mov     byte ptr [rdi+5Ah], 1
0x14000fb42  mov     byte ptr [rdi+58h], 1
0x14000fb46  mov     [rbx+30h], esi
0x14000fb49  mov     [rbx+38h], r13
0x14000fb4d  jmp     loc_14000FA55
0x14000fb52  mov     [rdi+58h], r13b; jumptable 000000014000FA0F case 4
0x14000fb56  mov     [rbx+30h], r13d; jumptable 000000014000FA0F cases 1,3,5,6,23
0x14000fb5a  inc     byte ptr [rbx+43h]; jumptable 000000014000FA0F default case, cases 2,7-22
0x14000fb5d  mov     rdx, rbx; Irp
0x14000fb60  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14000fb68  mov     rcx, [rdi+8]; DeviceObject
0x14000fb6c  call    cs:__imp_IofCallDriver
0x14000fb73  nop     dword ptr [rax+rax+00h]
0x14000fb78  mov     esi, eax
0x14000fb7a  mov     r8d, 20h ; ' '; RemlockSize
0x14000fb80  lea     rcx, [rdi+98h]; RemoveLock
0x14000fb87  mov     rdx, rbx; Tag
0x14000fb8a  call    cs:__imp_IoReleaseRemoveLockEx
0x14000fb91  nop     dword ptr [rax+rax+00h]
0x14000fb96  jmp     loc_14000FD31
0x14000fb9b  mov     rcx, [rdi]; DeviceObject
0x14000fb9e  mov     edx, 2; Action
0x14000fba3  call    cs:__imp_IoWMIRegistrationControl
0x14000fbaa  nop     dword ptr [rax+rax+00h]
0x14000fbaf  mov     rax, [rdi+1F0h]
0x14000fbb6  mov     qword ptr [rsp+88h+Interval], rax
0x14000fbbe  cmp     [rdi+320h], r13
0x14000fbc5  jz      short loc_14000FBE9
0x14000fbc7  mov     rdx, 0FFFFF78000000014h
0x14000fbd1  mov     rdx, [rdx]
0x14000fbd4  sub     rdx, [rdi+320h]
0x14000fbdb  cmp     rdx, 0FAh
0x14000fbe2  jle     short loc_14000FBE9
0x14000fbe4  call    TraceLoggingKeyRepeatOnRemoval
0x14000fbe9  mov     edx, 4
0x14000fbee  mov     rcx, rdi; Context
0x14000fbf1  call    KbdHid_CancelAutoRepeatTimer
0x14000fbf6  lea     rcx, [rdi+240h]; PKTIMER
0x14000fbfd  call    cs:__imp_KeCancelTimer
0x14000fc04  nop     dword ptr [rax+rax+00h]
0x14000fc09  mov     rax, [rdi+280h]
0x14000fc10  cmp     rax, qword ptr [rsp+88h+Interval]
0x14000fc18  jge     short loc_14000FC22
0x14000fc1a  mov     qword ptr [rsp+88h+Interval], rax
0x14000fc22  lea     r8, [rsp+88h+Interval]; Interval
0x14000fc2a  xor     edx, edx; Alertable
0x14000fc2c  xor     ecx, ecx; WaitMode
0x14000fc2e  call    cs:__imp_KeDelayExecutionThread
0x14000fc35  nop     dword ptr [rax+rax+00h]
0x14000fc3a  lea     rcx, [rdi+40h]; Object
0x14000fc3e  mov     byte ptr [rdi+59h], 1
0x14000fc42  xor     r9d, r9d; Alertable
0x14000fc45  mov     qword ptr [rsp+88h+RemlockSize], r13; Timeout
0x14000fc4a  xor     r8d, r8d; WaitMode
0x14000fc4d  xor     edx, edx; WaitReason
0x14000fc4f  call    cs:__imp_KeWaitForSingleObject
0x14000fc56  nop     dword ptr [rax+rax+00h]
0x14000fc5b  mov     rcx, [rdi+68h]; Irp
0x14000fc5f  call    cs:__imp_IoCancelIrp
0x14000fc66  nop     dword ptr [rax+rax+00h]
0x14000fc6b  inc     byte ptr [rbx+43h]
0x14000fc6e  mov     rdx, rbx; Irp
0x14000fc71  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14000fc79  mov     [rbx+30h], r13d
0x14000fc7d  mov     rcx, [rdi+8]; DeviceObject
0x14000fc81  call    cs:__imp_IofCallDriver
0x14000fc88  nop     dword ptr [rax+rax+00h]
0x14000fc8d  mov     r8d, 20h ; ' '; RemlockSize
0x14000fc93  lea     rcx, [rdi+98h]; RemoveLock
0x14000fc9a  mov     rdx, rbx; Tag
0x14000fc9d  mov     esi, eax
0x14000fc9f  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x14000fca6  nop     dword ptr [rax+rax+00h]
0x14000fcab  mov     rcx, [rdi+68h]; Irp
0x14000fcaf  call    cs:__imp_IoFreeIrp
0x14000fcb6  nop     dword ptr [rax+rax+00h]
0x14000fcbb  mov     rcx, [rdi+2F8h]; IoWorkItem
0x14000fcc2  call    cs:__imp_IoFreeWorkItem
0x14000fcc9  nop     dword ptr [rax+rax+00h]
0x14000fcce  test    r12, r12
0x14000fcd1  jz      short loc_14000FD0A
0x14000fcd3  mov     rcx, [r12]; P
0x14000fcd7  xor     edx, edx; Tag
0x14000fcd9  call    cs:__imp_ExFreePoolWithTag
0x14000fce0  nop     dword ptr [rax+rax+00h]
0x14000fce5  mov     rcx, [r12+90h]; Mdl
0x14000fced  call    cs:__imp_IoFreeMdl
0x14000fcf4  nop     dword ptr [rax+rax+00h]
0x14000fcf9  xor     edx, edx; Tag
0x14000fcfb  mov     rcx, r12; P
0x14000fcfe  call    cs:__imp_ExFreePoolWithTag
0x14000fd05  nop     dword ptr [rax+rax+00h]
0x14000fd0a  mov     rcx, rdi
0x14000fd0d  call    FreeKeyboardUsageMappingList
0x14000fd12  mov     rcx, [rdi+8]; TargetDevice
0x14000fd16  call    cs:__imp_IoDetachDevice
0x14000fd1d  nop     dword ptr [rax+rax+00h]
0x14000fd22  mov     rcx, [rdi]; DeviceObject
0x14000fd25  call    cs:__imp_IoDeleteDevice
0x14000fd2c  nop     dword ptr [rax+rax+00h]
0x14000fd31  mov     eax, esi
0x14000fd33  add     rsp, 48h
0x14000fd37  pop     r15
0x14000fd39  pop     r14
0x14000fd3b  pop     r13
0x14000fd3d  pop     r12
0x14000fd3f  pop     rdi
0x14000fd40  pop     rsi
0x14000fd41  pop     rbp
0x14000fd42  pop     rbx
0x14000fd43  retn
```
