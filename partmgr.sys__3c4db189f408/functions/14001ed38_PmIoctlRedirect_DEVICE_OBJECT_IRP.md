# PmIoctlRedirect(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001ed38`
- end: `0x14001ef1e`
- name: `?PmIoctlRedirect@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400068b0`
- `0x140024214`

## callees

- `0x14000a2b4`
- `0x14000beb4`
- `0x14001d894`
- `0x14001e468`
- `0x14001e6f0`
- `0x14001ed38`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001eec2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001eec2`
- `ntoskrnl!IofCallDriver` at `0x14001eefd`
- `ntoskrnl!IofCallDriver` at `0x14001eefd`
- `ntoskrnl!KeInitializeEvent` at `0x14001ee41`
- `ntoskrnl!KeInitializeEvent` at `0x14001ee41`
- `ntoskrnl!IofCompleteRequest` at `0x14001eedd`
- `ntoskrnl!IofCompleteRequest` at `0x14001eedd`

## pseudocode

```c
__int64 __fastcall PmIoctlRedirect(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PVOID DeviceExtension; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  __int64 v4; // r9
  unsigned __int64 v5; // r8
  unsigned __int8 v7; // dl
  unsigned __int8 v8; // r10
  int Status; // edi
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // eax
  struct _IO_STACK_LOCATION *v17; // rax
  struct _IO_STACK_LOCATION *v18; // rax
  struct _KEVENT Event; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 v21; // [rsp+70h] [rbp+20h] BYREF
  __int64 v22; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int64 v23; // [rsp+80h] [rbp+30h] BYREF

  DeviceExtension = a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = 0;
  v5 = 0;
  v22 = 0;
  v7 = 0;
  v23 = 0;
  v21 = 0;
  memset(&Event, 0, sizeof(Event));
  if ( (CurrentStackLocation->Flags & 0x10) != 0 || *((_DWORD *)DeviceExtension + 162) != 1 )
    goto LABEL_21;
  v8 = 0;
  Status = 0;
  v10 = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 315396;
  if ( !v10 || (v11 = v10 - 16) == 0 )
  {
    v8 = 1;
LABEL_13:
    v16 = PmIoctlPassThroughQuerySectorWriteScsi(a2, v8, &v21, &v22, &v23);
    goto LABEL_14;
  }
  v12 = v11 - 24;
  if ( !v12 || (v13 = v12 - 4) == 0 )
  {
    v16 = PmIoctlPassThroughQuerySectorWriteAta(a2, &v21, &v22, &v23);
    goto LABEL_14;
  }
  v14 = v13 - 20;
  if ( !v14 )
    goto LABEL_13;
  v15 = v14 - 4;
  if ( !v15 )
    goto LABEL_13;
  if ( v15 != 2671548 )
  {
LABEL_16:
    if ( v7 )
    {
      if ( PmIsOverlap((struct _DEVICE_EXTENSION *)DeviceExtension, v4, v5) )
      {
        KeInitializeEvent(&Event, NotificationEvent, 0);
        v17 = a2->Tail.Overlay.CurrentStackLocation;
        *(_OWORD *)&v17[-1].MajorFunction = *(_OWORD *)&v17->MajorFunction;
        *(_OWORD *)&v17[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v17->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&v17[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v17->Parameters.SetQuota + 6);
        v17[-1].FileObject = v17->FileObject;
        v17[-1].Control = 0;
        v18 = a2->Tail.Overlay.CurrentStackLocation;
        v18[-1].CompletionRoutine = PmSignalCompletion;
        v18[-1].Context = &Event;
        v18[-1].Control = -32;
        --a2->CurrentLocation;
        --a2->Tail.Overlay.CurrentStackLocation;
        PmRedirectRequest((struct _DEVICE_EXTENSION *)DeviceExtension, a2);
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        Status = a2->IoStatus.Status;
      }
      if ( Status < 0 )
        goto LABEL_20;
    }
LABEL_21:
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    return (unsigned int)IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
  }
  v16 = PmIoctlDsmQuerySectorWrite(a2, &v21, &v22, &v23);
LABEL_14:
  Status = v16;
  if ( v16 >= 0 )
  {
    v4 = v22;
    v7 = v21;
    v5 = v23;
    goto LABEL_16;
  }
LABEL_20:
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001ed38  mov     [rsp-18h+arg_18], rbx
0x14001ed3d  push    rbp
0x14001ed3e  push    rsi
0x14001ed3f  push    rdi
0x14001ed40  mov     rbp, rsp
0x14001ed43  sub     rsp, 50h
0x14001ed47  mov     rsi, [rcx+40h]
0x14001ed4b  xor     eax, eax
0x14001ed4d  mov     rcx, [rdx+0B8h]
0x14001ed54  xor     r9d, r9d
0x14001ed57  xor     r8d, r8d
0x14001ed5a  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14001ed5e  mov     rbx, rdx
0x14001ed61  mov     [rbp+arg_8], r9
0x14001ed65  xor     dl, dl
0x14001ed67  mov     [rbp+arg_10], r8
0x14001ed6b  xorps   xmm0, xmm0
0x14001ed6e  mov     [rbp+arg_0], dl
0x14001ed71  movups  xmmword ptr [rbp+Event.Header], xmm0
0x14001ed75  test    byte ptr [rcx+2], 10h
0x14001ed79  jnz     loc_14001EEEB
0x14001ed7f  cmp     dword ptr [rsi+288h], 1
0x14001ed86  jnz     loc_14001EEEB
0x14001ed8c  mov     ecx, [rcx+18h]
0x14001ed8f  xor     r10b, r10b
0x14001ed92  xor     edi, edi
0x14001ed94  sub     ecx, 4D004h
0x14001ed9a  jz      short loc_14001EDE9
0x14001ed9c  sub     ecx, 10h
0x14001ed9f  jz      short loc_14001EDE9
0x14001eda1  sub     ecx, 18h
0x14001eda4  jz      short loc_14001EDD3
0x14001eda6  sub     ecx, 4
0x14001eda9  jz      short loc_14001EDD3
0x14001edab  sub     ecx, 14h
0x14001edae  jz      short loc_14001EDEC
0x14001edb0  sub     ecx, 4
0x14001edb3  jz      short loc_14001EDEC
0x14001edb5  cmp     ecx, 28C3BCh
0x14001edbb  jnz     short loc_14001EE1D
0x14001edbd  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x14001edc1  mov     rcx, rbx; struct _IRP *
0x14001edc4  lea     r8, [rbp+arg_8]; __int64 *
0x14001edc8  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x14001edcc  call    ?PmIoctlDsmQuerySectorWrite@@YAJPEAU_IRP@@PEAEPEA_JPEA_K@Z; PmIoctlDsmQuerySectorWrite(_IRP *,uchar *,__int64 *,unsigned __int64 *)
0x14001edd1  jmp     short loc_14001EE08
0x14001edd3  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x14001edd7  mov     rcx, rbx; struct _IRP *
0x14001edda  lea     r8, [rbp+arg_8]; __int64 *
0x14001edde  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x14001ede2  call    ?PmIoctlPassThroughQuerySectorWriteAta@@YAJPEAU_IRP@@PEAEPEA_JPEA_K@Z; PmIoctlPassThroughQuerySectorWriteAta(_IRP *,uchar *,__int64 *,unsigned __int64 *)
0x14001ede7  jmp     short loc_14001EE08
0x14001ede9  mov     r10b, 1
0x14001edec  lea     rax, [rbp+arg_10]
0x14001edf0  mov     dl, r10b; unsigned __int8
0x14001edf3  lea     r9, [rbp+arg_8]; __int64 *
0x14001edf7  mov     [rsp+50h+Timeout], rax; unsigned __int64 *
0x14001edfc  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x14001ee00  mov     rcx, rbx; struct _IRP *
0x14001ee03  call    ?PmIoctlPassThroughQuerySectorWriteScsi@@YAJPEAU_IRP@@EPEAEPEA_JPEA_K@Z; PmIoctlPassThroughQuerySectorWriteScsi(_IRP *,uchar,uchar *,__int64 *,unsigned __int64 *)
0x14001ee08  mov     edi, eax
0x14001ee0a  test    eax, eax
0x14001ee0c  js      loc_14001EED5
0x14001ee12  mov     r9, [rbp+arg_8]
0x14001ee16  mov     dl, [rbp+arg_0]
0x14001ee19  mov     r8, [rbp+arg_10]; unsigned __int64
0x14001ee1d  test    dl, dl
0x14001ee1f  jz      loc_14001EEEB
0x14001ee25  mov     rdx, r9; __int64
0x14001ee28  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14001ee2b  call    ?PmIsOverlap@@YAEPEAU_DEVICE_EXTENSION@@_J_K@Z; PmIsOverlap(_DEVICE_EXTENSION *,__int64,unsigned __int64)
0x14001ee30  test    al, al
0x14001ee32  jz      loc_14001EED1
0x14001ee38  xor     r8d, r8d; State
0x14001ee3b  lea     rcx, [rbp+Event]; Event
0x14001ee3f  xor     edx, edx; Type
0x14001ee41  call    cs:__imp_KeInitializeEvent
0x14001ee48  nop     dword ptr [rax+rax+00h]
0x14001ee4d  mov     rax, [rbx+0B8h]
0x14001ee54  lea     rcx, ?PmSignalCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; PmSignalCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x14001ee5b  mov     rdx, rbx; struct _IRP *
0x14001ee5e  movups  xmm0, xmmword ptr [rax]
0x14001ee61  movups  xmmword ptr [rax-48h], xmm0
0x14001ee65  movups  xmm1, xmmword ptr [rax+10h]
0x14001ee69  movups  xmmword ptr [rax-38h], xmm1
0x14001ee6d  movups  xmm0, xmmword ptr [rax+20h]
0x14001ee71  movups  xmmword ptr [rax-28h], xmm0
0x14001ee75  movsd   xmm1, qword ptr [rax+30h]
0x14001ee7a  movsd   qword ptr [rax-18h], xmm1
0x14001ee7f  mov     byte ptr [rax-45h], 0
0x14001ee83  mov     rax, [rbx+0B8h]
0x14001ee8a  mov     [rax-10h], rcx
0x14001ee8e  lea     rcx, [rbp+Event]
0x14001ee92  mov     [rax-8], rcx
0x14001ee96  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14001ee99  mov     byte ptr [rax-45h], 0E0h
0x14001ee9d  dec     byte ptr [rbx+43h]
0x14001eea0  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14001eea8  call    ?PmRedirectRequest@@YAXPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z; PmRedirectRequest(_DEVICE_EXTENSION *,_IRP *)
0x14001eead  xor     r9d, r9d; Alertable
0x14001eeb0  mov     [rsp+50h+Timeout], 0; Timeout
0x14001eeb9  xor     r8d, r8d; WaitMode
0x14001eebc  lea     rcx, [rbp+Event]; Object
0x14001eec0  xor     edx, edx; WaitReason
0x14001eec2  call    cs:__imp_KeWaitForSingleObject
0x14001eec9  nop     dword ptr [rax+rax+00h]
0x14001eece  mov     edi, [rbx+30h]
0x14001eed1  test    edi, edi
0x14001eed3  jns     short loc_14001EEEB
0x14001eed5  xor     edx, edx; PriorityBoost
0x14001eed7  mov     [rbx+30h], edi
0x14001eeda  mov     rcx, rbx; Irp
0x14001eedd  call    cs:__imp_IofCompleteRequest
0x14001eee4  nop     dword ptr [rax+rax+00h]
0x14001eee9  jmp     short loc_14001EF0B
0x14001eeeb  inc     byte ptr [rbx+43h]
0x14001eeee  mov     rdx, rbx; Irp
0x14001eef1  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14001eef9  mov     rcx, [rsi+10h]; DeviceObject
0x14001eefd  call    cs:__imp_IofCallDriver
0x14001ef04  nop     dword ptr [rax+rax+00h]
0x14001ef09  mov     edi, eax
0x14001ef0b  mov     rbx, [rsp+50h+arg_18]
0x14001ef13  mov     eax, edi
0x14001ef15  add     rsp, 50h
0x14001ef19  pop     rdi
0x14001ef1a  pop     rsi
0x14001ef1b  pop     rbp
0x14001ef1c  retn
```
