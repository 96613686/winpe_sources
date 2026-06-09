# MouHid_PnP

- ea: `0x14000b730`
- end: `0x14000baea`
- name: `MouHid_PnP`
- size: `954`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PVOID Tag)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001464`
- `0x140002c2c`
- `0x14000b730`
- `0x14000baf0`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x14000b88e`
- `ntoskrnl!IoCancelIrp` at `0x14000b88e`
- `ntoskrnl!IoDetachDevice` at `0x14000b91f`
- `ntoskrnl!IoDetachDevice` at `0x14000b91f`
- `ntoskrnl!IoFreeIrp` at `0x14000b8d4`
- `ntoskrnl!IoFreeIrp` at `0x14000b8d4`
- `ntoskrnl!IoDeleteDevice` at `0x14000b92e`
- `ntoskrnl!IoDeleteDevice` at `0x14000b92e`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14000b8c4`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14000b8c4`
- `ntoskrnl!IoFreeMdl` at `0x14000b8fe`
- `ntoskrnl!IoFreeMdl` at `0x14000b8fe`
- `ntoskrnl!KeInitializeEvent` at `0x14000b9c8`
- `ntoskrnl!KeInitializeEvent` at `0x14000b9c8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b87e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ba1d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b87e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ba1d`
- `ntoskrnl!IofCompleteRequest` at `0x14000b799`
- `ntoskrnl!IofCompleteRequest` at `0x14000b981`
- `ntoskrnl!IofCompleteRequest` at `0x14000b799`
- `ntoskrnl!IofCompleteRequest` at `0x14000b981`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000b857`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000ba52`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000b857`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000ba52`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b90f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b8eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b90f`
- `ntoskrnl!IofCallDriver` at `0x14000b8ac`
- `ntoskrnl!IofCallDriver` at `0x14000b9f8`
- `ntoskrnl!IofCallDriver` at `0x14000bab0`
- `ntoskrnl!IofCallDriver` at `0x14000b8ac`
- `ntoskrnl!IofCallDriver` at `0x14000b9f8`
- `ntoskrnl!IofCallDriver` at `0x14000bab0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000baca`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000baca`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000b77b`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000b77b`

## pseudocode

```c
__int64 __fastcall MouHid_PnP(PDEVICE_OBJECT DeviceObject, IRP *Tag)
{
  char *DeviceExtension; // rdi
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 v7; // rbp
  NTSTATUS v8; // eax
  int v9; // r9d
  int v10; // edx
  NTSTATUS Status; // esi
  char *p_MinorFunction; // rsi
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *v13; // r14
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  struct _IO_STACK_LOCATION *v19; // rax
  struct _IO_STACK_LOCATION *v20; // rax
  int RemlockSize; // [rsp+20h] [rbp-68h]

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&Tag->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation = Tag->Tail.Overlay.CurrentStackLocation;
  v7 = *((_QWORD *)DeviceExtension + 27);
  v8 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 240), Tag, File, 1u, 0x20u);
  v10 = 0;
  Status = v8;
  if ( v8 < 0 )
  {
    Tag->IoStatus.Information = 0;
    Tag->IoStatus.Status = v8;
    IofCompleteRequest(Tag, 0);
    return (unsigned int)Status;
  }
  p_MinorFunction = (char *)&CurrentStackLocation->MinorFunction;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = p_CurrentStackLocation;
  }
  else
  {
    WPP_RECORDER_SF_qqc(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      v9,
      RemlockSize,
      (char)DeviceObject,
      (char)Tag,
      *p_MinorFunction);
    v10 = 0;
    v13 = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&Tag->Tail.Overlay.CurrentStackLocation;
  }
  v14 = (unsigned __int8)*p_MinorFunction;
  if ( v14 > 9 )
  {
    if ( v14 != 23 )
      goto LABEL_35;
    goto LABEL_34;
  }
  if ( v14 == 9 )
    goto LABEL_35;
  if ( !*p_MinorFunction )
  {
    if ( DeviceExtension[32] )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          5,
          22,
          (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids);
      }
      Status = 0;
      Tag->IoStatus.Status = 0;
      goto LABEL_23;
    }
    v19 = v13->CurrentStackLocation;
    *(_OWORD *)&v19[-1].MajorFunction = *(_OWORD *)&v13->CurrentStackLocation->MajorFunction;
    *(_OWORD *)&v19[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v19->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v19[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v19->Parameters.SetQuota + 6);
    v19[-1].FileObject = v19->FileObject;
    v19[-1].Control = 0;
    KeInitializeEvent((PRKEVENT)(DeviceExtension + 328), NotificationEvent, 0);
    v20 = v13->CurrentStackLocation;
    v20[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)MouHid_PnPComplete;
    v20[-1].Context = DeviceExtension;
    v20[-1].Control = -32;
    Tag->IoStatus.Status = 0;
    Status = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 1), Tag);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(DeviceExtension + 328, Executive, 0, 0, 0);
      Status = Tag->IoStatus.Status;
    }
    if ( Status >= 0 && Tag->IoStatus.Status >= 0 )
    {
      if ( DeviceExtension[34] )
      {
LABEL_31:
        DeviceExtension[32] = 1;
        goto LABEL_32;
      }
      Status = MouHid_StartDevice(DeviceExtension);
      if ( Status >= 0 )
      {
        IoWMIRegistrationControl(DeviceObject, 1u);
        DeviceExtension[34] = 1;
        goto LABEL_31;
      }
    }
LABEL_32:
    Tag->IoStatus.Status = Status;
    Tag->IoStatus.Information = 0;
LABEL_23:
    IofCompleteRequest(Tag, 0);
LABEL_37:
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 240), Tag, 0x20u);
    return (unsigned int)Status;
  }
  v15 = v14 - 1;
  if ( !v15 )
    goto LABEL_34;
  v16 = v15 - 1;
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( !v18 )
      {
        DeviceExtension[32] = 0;
        ++v13->CurrentStackLocation;
        Tag->IoStatus.Status = 0;
LABEL_36:
        ++Tag->CurrentLocation;
        Status = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 1), Tag);
        goto LABEL_37;
      }
      if ( v18 - 1 >= 2 )
      {
LABEL_35:
        ++p_CurrentStackLocation->CurrentStackLocation;
        goto LABEL_36;
      }
    }
LABEL_34:
    Tag->IoStatus.Status = 0;
    goto LABEL_35;
  }
  IoWMIRegistrationControl(*(PDEVICE_OBJECT *)DeviceExtension, 2u);
  DeviceExtension[33] = 1;
  KeWaitForSingleObject(DeviceExtension + 168, Executive, 0, 0, 0);
  IoCancelIrp(*((PIRP *)DeviceExtension + 14));
  ++Tag->CurrentLocation;
  ++v13->CurrentStackLocation;
  Tag->IoStatus.Status = 0;
  Status = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 1), Tag);
  IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)(DeviceExtension + 240), Tag, 0x20u);
  IoFreeIrp(*((PIRP *)DeviceExtension + 14));
  if ( v7 )
  {
    ExFreePoolWithTag(*(PVOID *)(v7 + 32), 0);
    IoFreeMdl(*(PMDL *)(v7 + 144));
    ExFreePoolWithTag((PVOID)v7, 0);
  }
  IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 1));
  IoDeleteDevice(*(PDEVICE_OBJECT *)DeviceExtension);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000b730  push    rbx
0x14000b732  push    rbp
0x14000b733  push    rsi
0x14000b734  push    rdi
0x14000b735  push    r12
0x14000b737  push    r13
0x14000b739  push    r14
0x14000b73b  push    r15
0x14000b73d  sub     rsp, 48h
0x14000b741  mov     rdi, [rcx+40h]
0x14000b745  lea     r15, [rdx+0B8h]
0x14000b74c  mov     r14, [r15]
0x14000b74f  lea     r8, File; File
0x14000b756  mov     r13, rcx
0x14000b759  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x14000b761  mov     r9d, 1; Line
0x14000b767  mov     rbx, rdx
0x14000b76a  mov     rbp, [rdi+0D8h]
0x14000b771  lea     r12, [rdi+0F0h]
0x14000b778  mov     rcx, r12; RemoveLock
0x14000b77b  call    cs:__imp_IoAcquireRemoveLockEx
0x14000b782  nop     dword ptr [rax+rax+00h]
0x14000b787  xor     edx, edx; PriorityBoost
0x14000b789  mov     esi, eax
0x14000b78b  test    eax, eax
0x14000b78d  jns     short loc_14000B7AA
0x14000b78f  mov     rcx, rbx; Irp
0x14000b792  mov     [rbx+38h], rdx
0x14000b796  mov     [rbx+30h], eax
0x14000b799  call    cs:__imp_IofCompleteRequest
0x14000b7a0  nop     dword ptr [rax+rax+00h]
0x14000b7a5  jmp     loc_14000BAD6
0x14000b7aa  lea     r8, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b7b1  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14000b7b8  lea     rsi, [r14+1]
0x14000b7bc  jz      short loc_14000B7F0
0x14000b7be  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b7c5  mov     al, [rsi]
0x14000b7c7  mov     [rsp+88h+var_50], al
0x14000b7cb  mov     [rsp+88h+var_58], rbx
0x14000b7d0  mov     rcx, [rcx+40h]
0x14000b7d4  mov     [rsp+88h+var_60], r13
0x14000b7d9  call    WPP_RECORDER_SF_qqc
0x14000b7de  xor     edx, edx
0x14000b7e0  lea     r8, WPP_RECORDER_INITIALIZED
0x14000b7e7  lea     r14, [rbx+0B8h]
0x14000b7ee  jmp     short loc_14000B7F3
0x14000b7f0  mov     r14, r15
0x14000b7f3  movzx   ecx, byte ptr [rsi]
0x14000b7f6  cmp     ecx, 9
0x14000b7f9  ja      loc_14000BA72
0x14000b7ff  jz      loc_14000BAA2
0x14000b805  test    ecx, ecx
0x14000b807  jz      loc_14000B93F
0x14000b80d  sub     ecx, 1
0x14000b810  jz      loc_14000BA9F
0x14000b816  sub     ecx, 1
0x14000b819  jz      short loc_14000B84F
0x14000b81b  sub     ecx, 1
0x14000b81e  jz      loc_14000BA9F
0x14000b824  sub     ecx, 1
0x14000b827  jz      short loc_14000B840
0x14000b829  sub     ecx, 1
0x14000b82c  jz      loc_14000BA9F
0x14000b832  sub     ecx, 1
0x14000b835  jz      loc_14000BA9F
0x14000b83b  jmp     loc_14000BAA2
0x14000b840  mov     [rdi+20h], dl
0x14000b843  add     qword ptr [r14], 48h ; 'H'
0x14000b847  mov     [rbx+30h], edx
0x14000b84a  jmp     loc_14000BAA6
0x14000b84f  mov     rcx, [rdi]; DeviceObject
0x14000b852  mov     edx, 2; Action
0x14000b857  call    cs:__imp_IoWMIRegistrationControl
0x14000b85e  nop     dword ptr [rax+rax+00h]
0x14000b863  xor     r15d, r15d
0x14000b866  mov     byte ptr [rdi+21h], 1
0x14000b86a  lea     rcx, [rdi+0A8h]; Object
0x14000b871  mov     qword ptr [rsp+88h+RemlockSize], r15; Timeout
0x14000b876  xor     r9d, r9d; Alertable
0x14000b879  xor     r8d, r8d; WaitMode
0x14000b87c  xor     edx, edx; WaitReason
0x14000b87e  call    cs:__imp_KeWaitForSingleObject
0x14000b885  nop     dword ptr [rax+rax+00h]
0x14000b88a  mov     rcx, [rdi+70h]; Irp
0x14000b88e  call    cs:__imp_IoCancelIrp
0x14000b895  nop     dword ptr [rax+rax+00h]
0x14000b89a  inc     byte ptr [rbx+43h]
0x14000b89d  mov     rdx, rbx; Irp
0x14000b8a0  add     qword ptr [r14], 48h ; 'H'
0x14000b8a4  mov     [rbx+30h], r15d
0x14000b8a8  mov     rcx, [rdi+8]; DeviceObject
0x14000b8ac  call    cs:__imp_IofCallDriver
0x14000b8b3  nop     dword ptr [rax+rax+00h]
0x14000b8b8  lea     r8d, [r15+20h]; RemlockSize
0x14000b8bc  mov     rdx, rbx; Tag
0x14000b8bf  mov     rcx, r12; RemoveLock
0x14000b8c2  mov     esi, eax
0x14000b8c4  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x14000b8cb  nop     dword ptr [rax+rax+00h]
0x14000b8d0  mov     rcx, [rdi+70h]; Irp
0x14000b8d4  call    cs:__imp_IoFreeIrp
0x14000b8db  nop     dword ptr [rax+rax+00h]
0x14000b8e0  test    rbp, rbp
0x14000b8e3  jz      short loc_14000B91B
0x14000b8e5  mov     rcx, [rbp+20h]; P
0x14000b8e9  xor     edx, edx; Tag
0x14000b8eb  call    cs:__imp_ExFreePoolWithTag
0x14000b8f2  nop     dword ptr [rax+rax+00h]
0x14000b8f7  mov     rcx, [rbp+90h]; Mdl
0x14000b8fe  call    cs:__imp_IoFreeMdl
0x14000b905  nop     dword ptr [rax+rax+00h]
0x14000b90a  xor     edx, edx; Tag
0x14000b90c  mov     rcx, rbp; P
0x14000b90f  call    cs:__imp_ExFreePoolWithTag
0x14000b916  nop     dword ptr [rax+rax+00h]
0x14000b91b  mov     rcx, [rdi+8]; TargetDevice
0x14000b91f  call    cs:__imp_IoDetachDevice
0x14000b926  nop     dword ptr [rax+rax+00h]
0x14000b92b  mov     rcx, [rdi]; DeviceObject
0x14000b92e  call    cs:__imp_IoDeleteDevice
0x14000b935  nop     dword ptr [rax+rax+00h]
0x14000b93a  jmp     loc_14000BAD6
0x14000b93f  cmp     [rdi+20h], dl
0x14000b942  jz      short loc_14000B992
0x14000b944  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x14000b94b  jz      short loc_14000B977
0x14000b94d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b954  lea     rax, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x14000b95b  mov     r9d, 16h
0x14000b961  mov     qword ptr [rsp+88h+RemlockSize], rax
0x14000b966  mov     dl, 4
0x14000b968  mov     rcx, [rcx+40h]
0x14000b96c  lea     r8d, [r9-11h]
0x14000b970  call    WPP_RECORDER_SF_
0x14000b975  xor     edx, edx
0x14000b977  mov     esi, edx
0x14000b979  mov     [rbx+30h], edx
0x14000b97c  xor     edx, edx; PriorityBoost
0x14000b97e  mov     rcx, rbx; Irp
0x14000b981  call    cs:__imp_IofCompleteRequest
0x14000b988  nop     dword ptr [rax+rax+00h]
0x14000b98d  jmp     loc_14000BABE
0x14000b992  mov     rax, [r14]
0x14000b995  lea     rbp, [rdi+148h]
0x14000b99c  xor     r8d, r8d; State
0x14000b99f  mov     rcx, rbp; Event
0x14000b9a2  movups  xmm0, xmmword ptr [rax]
0x14000b9a5  movups  xmmword ptr [rax-48h], xmm0
0x14000b9a9  movups  xmm1, xmmword ptr [rax+10h]
0x14000b9ad  movups  xmmword ptr [rax-38h], xmm1
0x14000b9b1  movups  xmm0, xmmword ptr [rax+20h]
0x14000b9b5  movups  xmmword ptr [rax-28h], xmm0
0x14000b9b9  movsd   xmm1, qword ptr [rax+30h]
0x14000b9be  movsd   qword ptr [rax-18h], xmm1
0x14000b9c3  mov     [rax-45h], dl
0x14000b9c6  xor     edx, edx; Type
0x14000b9c8  call    cs:__imp_KeInitializeEvent
0x14000b9cf  nop     dword ptr [rax+rax+00h]
0x14000b9d4  mov     rax, [r14]
0x14000b9d7  lea     rcx, MouHid_PnPComplete
0x14000b9de  xor     r15d, r15d
0x14000b9e1  mov     rdx, rbx; Irp
0x14000b9e4  mov     [rax-10h], rcx
0x14000b9e8  mov     [rax-8], rdi
0x14000b9ec  mov     byte ptr [rax-45h], 0E0h
0x14000b9f0  mov     [rbx+30h], r15d
0x14000b9f4  mov     rcx, [rdi+8]; DeviceObject
0x14000b9f8  call    cs:__imp_IofCallDriver
0x14000b9ff  nop     dword ptr [rax+rax+00h]
0x14000ba04  mov     esi, eax
0x14000ba06  cmp     eax, 103h
0x14000ba0b  jnz     short loc_14000BA2C
0x14000ba0d  xor     r9d, r9d; Alertable
0x14000ba10  mov     qword ptr [rsp+88h+RemlockSize], r15; Timeout
0x14000ba15  xor     r8d, r8d; WaitMode
0x14000ba18  xor     edx, edx; WaitReason
0x14000ba1a  mov     rcx, rbp; Object
0x14000ba1d  call    cs:__imp_KeWaitForSingleObject
0x14000ba24  nop     dword ptr [rax+rax+00h]
0x14000ba29  mov     esi, [rbx+30h]
0x14000ba2c  test    esi, esi
0x14000ba2e  js      short loc_14000BA66
0x14000ba30  cmp     [rbx+30h], r15d
0x14000ba34  jl      short loc_14000BA66
0x14000ba36  cmp     [rdi+22h], r15b
0x14000ba3a  jnz     short loc_14000BA62
0x14000ba3c  mov     rcx, rdi
0x14000ba3f  call    MouHid_StartDevice
0x14000ba44  mov     esi, eax
0x14000ba46  test    eax, eax
0x14000ba48  js      short loc_14000BA66
0x14000ba4a  mov     edx, 1; Action
0x14000ba4f  mov     rcx, r13; DeviceObject
0x14000ba52  call    cs:__imp_IoWMIRegistrationControl
0x14000ba59  nop     dword ptr [rax+rax+00h]
0x14000ba5e  mov     byte ptr [rdi+22h], 1
0x14000ba62  mov     byte ptr [rdi+20h], 1
0x14000ba66  mov     [rbx+30h], esi
0x14000ba69  mov     [rbx+38h], r15
0x14000ba6d  jmp     loc_14000B97C
0x14000ba72  sub     ecx, 0Ah
0x14000ba75  jz      short loc_14000BAA2
0x14000ba77  sub     ecx, 1
0x14000ba7a  jz      short loc_14000BAA2
0x14000ba7c  sub     ecx, 4
0x14000ba7f  jz      short loc_14000BAA2
0x14000ba81  sub     ecx, 1
0x14000ba84  jz      short loc_14000BAA2
0x14000ba86  sub     ecx, 1
0x14000ba89  jz      short loc_14000BAA2
0x14000ba8b  sub     ecx, 1
0x14000ba8e  jz      short loc_14000BAA2
0x14000ba90  sub     ecx, 1
0x14000ba93  jz      short loc_14000BAA2
0x14000ba95  sub     ecx, 1
0x14000ba98  jz      short loc_14000BAA2
0x14000ba9a  cmp     ecx, 3
0x14000ba9d  jnz     short loc_14000BAA2
0x14000ba9f  mov     [rbx+30h], edx
0x14000baa2  add     qword ptr [r15], 48h ; 'H'
0x14000baa6  inc     byte ptr [rbx+43h]
0x14000baa9  mov     rdx, rbx; Irp
0x14000baac  mov     rcx, [rdi+8]; DeviceObject
0x14000bab0  call    cs:__imp_IofCallDriver
0x14000bab7  nop     dword ptr [rax+rax+00h]
0x14000babc  mov     esi, eax
0x14000babe  mov     r8d, 20h ; ' '; RemlockSize
0x14000bac4  mov     rdx, rbx; Tag
0x14000bac7  mov     rcx, r12; RemoveLock
0x14000baca  call    cs:__imp_IoReleaseRemoveLockEx
0x14000bad1  nop     dword ptr [rax+rax+00h]
0x14000bad6  mov     eax, esi
0x14000bad8  add     rsp, 48h
0x14000badc  pop     r15
0x14000bade  pop     r14
0x14000bae0  pop     r13
0x14000bae2  pop     r12
0x14000bae4  pop     rdi
0x14000bae5  pop     rsi
0x14000bae6  pop     rbp
0x14000bae7  pop     rbx
0x14000bae8  retn
```
