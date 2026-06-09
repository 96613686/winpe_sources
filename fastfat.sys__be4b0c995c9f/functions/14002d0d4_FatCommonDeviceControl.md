# FatCommonDeviceControl

- ea: `0x14002d0d4`
- end: `0x14002d3dc`
- name: `FatCommonDeviceControl`
- size: `776`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002d3f0`
- `0x1400438e0`

## callees

- `0x14002d0d4`
- `0x140038eb4`
- `0x14003d880`
- `0x14003f1bc`
- `0x1400465f4`
- `0x1400466c8`
- `0x140048740`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002d1dc`
- `ntoskrnl!KeInitializeEvent` at `0x14002d1dc`
- `ntoskrnl!IofCallDriver` at `0x14002d332`
- `ntoskrnl!IofCallDriver` at `0x14002d332`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002d362`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002d362`
- `ntoskrnl!IoIs32bitProcess` at `0x14002d29a`
- `ntoskrnl!IoIs32bitProcess` at `0x14002d29a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d381`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d3ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d381`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d3ab`

## pseudocode

```c
__int64 __fastcall FatCommonDeviceControl(PVOID Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  PIRP v3; // rbx
  PFILE_OBJECT FileObject; // rcx
  __int64 v6; // r9
  unsigned int v7; // edi
  struct _KEVENT *p_Event; // r12
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 i; // rdx
  __int64 NextFcbBottomUp; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdi
  struct _IO_STACK_LOCATION *v17; // rax
  struct _IO_STACK_LOCATION *v18; // rax
  __int64 v19; // r14
  bool v20; // zf
  int v21; // eax
  _BYTE *p_Information; // rax
  __int64 v23; // rcx
  __int64 v24; // r9
  unsigned int Status; // r14d
  __int64 j; // rdx
  __int64 v27; // rax
  __int64 v28; // rdi
  struct _KEVENT Event; // [rsp+30h] [rbp-20h] BYREF
  __int64 v30; // [rsp+98h] [rbp+48h] BYREF
  __int64 v31; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v32; // [rsp+A8h] [rbp+58h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = Irp;
  v31 = 0;
  v32 = 0;
  memset(&Event, 0, sizeof(Event));
  FileObject = CurrentStackLocation->FileObject;
  v30 = 0;
  if ( (unsigned int)FatDecodeFileObject(FileObject, &v31, &v32, &v30) != 4 )
  {
    v7 = -1073741811;
LABEL_3:
    FatCompleteRequest_Real(Entry, v3, v7, v6);
    return v7;
  }
  p_Event = 0;
  v10 = v31;
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 315396
    || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 315412
    || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 315460
    || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 315464 )
  {
    v19 = v30;
    if ( (CurrentStackLocation->FileObject->Flags & 0x1000) != 0 && (*(_DWORD *)(v30 + 4) & 0x40000) != 0
      || !v3->AssociatedIrp.MasterIrp )
    {
      goto LABEL_35;
    }
    v20 = IoIs32bitProcess(v3) == 0;
    v21 = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 315396;
    if ( v20 )
    {
      if ( (v21 & 0xFFFFFFEF) != 0 )
      {
        if ( CurrentStackLocation->Parameters.Create.Options < 0x40 )
          goto LABEL_35;
        p_Information = &v3->AssociatedIrp.MasterIrp->IoStatus.Information;
      }
      else
      {
        if ( CurrentStackLocation->Parameters.Create.Options < 0x38 )
          goto LABEL_35;
        p_Information = (char *)&v3->AssociatedIrp.MasterIrp->ThreadListEntry.Flink + 4;
      }
    }
    else if ( (v21 & 0xFFFFFFEF) != 0 )
    {
      if ( CurrentStackLocation->Parameters.Create.Options < 0x34 )
        goto LABEL_35;
      p_Information = &v3->AssociatedIrp.MasterIrp->IoStatus;
    }
    else
    {
      if ( CurrentStackLocation->Parameters.Create.Options < 0x2C )
        goto LABEL_35;
      p_Information = (char *)&v3->AssociatedIrp.MasterIrp->AssociatedIrp.SystemBuffer + 4;
    }
    if ( p_Information && *p_Information == 4 )
    {
      *(_DWORD *)(v19 + 4) |= 0x40000u;
      CurrentStackLocation->FileObject->Flags |= 0x1000u;
    }
    goto LABEL_35;
  }
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 508004 )
  {
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 5488640 )
    {
      *((_DWORD *)Entry + 17) |= 2u;
      FatAcquireExclusiveVcb_Real(Entry, v10, 0, v6);
      for ( i = 0; ; i = v16 )
      {
        NextFcbBottomUp = FatGetNextFcbBottomUp(v11, i, *(_QWORD *)(v10 + 208));
        v16 = NextFcbBottomUp;
        if ( !NextFcbBottomUp )
          break;
        FatAcquireExclusiveFcb(Entry, NextFcbBottomUp, v14, v15);
      }
      FatFlushAndCleanVolume((__int64)Entry, (__int64)v3, v10, 3u);
      KeInitializeEvent(&Event, NotificationEvent, 0);
      v17 = v3->Tail.Overlay.CurrentStackLocation;
      p_Event = &Event;
      *(_OWORD *)&v17[-1].MajorFunction = *(_OWORD *)&v17->MajorFunction;
      *(_OWORD *)&v17[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v17->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v17[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v17->Parameters.SetQuota + 6);
      v17[-1].FileObject = v17->FileObject;
      v17[-1].Control = 0;
      v18 = v3->Tail.Overlay.CurrentStackLocation;
      v18[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&FatDeviceControlCompletionRoutine;
      v18[-1].Context = &Event;
      v18[-1].Control = -32;
      goto LABEL_36;
    }
LABEL_35:
    ++v3->CurrentLocation;
    ++v3->Tail.Overlay.CurrentStackLocation;
    goto LABEL_36;
  }
  if ( (*(_DWORD *)(v31 + 200) & 1) == 0
    && (CurrentStackLocation->Flags & 0x10) == 0
    && (*(_DWORD *)(v30 + 4) & 0x10000) == 0 )
  {
    v7 = -1073741790;
    goto LABEL_3;
  }
LABEL_36:
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(v10 + 136), v3);
  if ( Status == 259 )
  {
    if ( p_Event )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v3->IoStatus.Status;
      goto LABEL_40;
    }
  }
  else if ( p_Event )
  {
LABEL_40:
    for ( j = 0; ; j = v28 )
    {
      v27 = FatGetNextFcbBottomUp(v23, j, *(_QWORD *)(v10 + 208));
      v28 = v27;
      if ( !v27 )
        break;
      ExReleaseResourceLite(*(PERESOURCE *)(v27 + 8));
    }
    ExReleaseResourceLite((PERESOURCE)(v10 + 520));
    goto LABEL_45;
  }
  v3 = 0;
LABEL_45:
  FatCompleteRequest_Real(Entry, v3, Status, v24);
  return Status;
}

```

## disassembly

```asm
0x14002d0d4  push    rbp
0x14002d0d6  push    rbx
0x14002d0d7  push    rsi
0x14002d0d8  push    rdi
0x14002d0d9  push    r12
0x14002d0db  push    r14
0x14002d0dd  push    r15
0x14002d0df  mov     rbp, rsp
0x14002d0e2  sub     rsp, 50h
0x14002d0e6  mov     rdi, [rdx+0B8h]
0x14002d0ed  lea     r9, [rbp+arg_8]
0x14002d0f1  xor     eax, eax
0x14002d0f3  lea     r8, [rbp+arg_18]
0x14002d0f7  xorps   xmm0, xmm0
0x14002d0fa  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14002d0fe  mov     rbx, rdx
0x14002d101  mov     [rbp+arg_10], rax
0x14002d105  mov     r15, rcx
0x14002d108  mov     [rbp+arg_18], rax
0x14002d10c  movups  xmmword ptr [rbp+Event.Header], xmm0
0x14002d110  mov     rcx, [rdi+30h]
0x14002d114  lea     rdx, [rbp+arg_10]
0x14002d118  mov     [rbp+arg_8], rax
0x14002d11c  call    FatDecodeFileObject
0x14002d121  cmp     eax, 4
0x14002d124  jz      short loc_14002D140
0x14002d126  mov     edi, 0C000000Dh
0x14002d12b  mov     r8d, edi
0x14002d12e  mov     rdx, rbx; Irp
0x14002d131  mov     rcx, r15; Entry
0x14002d134  call    FatCompleteRequest_Real
0x14002d139  mov     eax, edi
0x14002d13b  jmp     loc_14002D3CC
0x14002d140  mov     ecx, [rdi+18h]
0x14002d143  xor     r12d, r12d
0x14002d146  mov     rsi, [rbp+arg_10]
0x14002d14a  sub     ecx, 4D004h
0x14002d150  jz      loc_14002D26E
0x14002d156  sub     ecx, 10h
0x14002d159  jz      loc_14002D26E
0x14002d15f  sub     ecx, 30h ; '0'
0x14002d162  jz      loc_14002D26E
0x14002d168  sub     ecx, 4
0x14002d16b  jz      loc_14002D26E
0x14002d171  sub     ecx, 2F01Ch
0x14002d177  jz      loc_14002D23B
0x14002d17d  cmp     ecx, 4BFF9Ch
0x14002d183  jnz     loc_14002D31D
0x14002d189  or      dword ptr [r15+44h], 2
0x14002d18e  xor     r8d, r8d
0x14002d191  mov     rdx, rsi
0x14002d194  mov     rcx, r15
0x14002d197  call    FatAcquireExclusiveVcb_Real
0x14002d19c  xor     edx, edx
0x14002d19e  jmp     short loc_14002D1AB
0x14002d1a0  mov     rdx, rdi
0x14002d1a3  call    FatAcquireExclusiveFcb
0x14002d1a8  mov     rdx, rdi
0x14002d1ab  mov     r8, [rsi+0D0h]
0x14002d1b2  call    FatGetNextFcbBottomUp
0x14002d1b7  mov     rdi, rax
0x14002d1ba  mov     rcx, r15
0x14002d1bd  test    rax, rax
0x14002d1c0  jnz     short loc_14002D1A0
0x14002d1c2  mov     r9d, 3
0x14002d1c8  mov     r8, rsi
0x14002d1cb  mov     rdx, rbx
0x14002d1ce  call    FatFlushAndCleanVolume
0x14002d1d3  xor     r8d, r8d; State
0x14002d1d6  lea     rcx, [rbp+Event]; Event
0x14002d1da  xor     edx, edx; Type
0x14002d1dc  call    cs:__imp_KeInitializeEvent
0x14002d1e3  nop     dword ptr [rax+rax+00h]
0x14002d1e8  mov     rax, [rbx+0B8h]
0x14002d1ef  lea     rcx, FatDeviceControlCompletionRoutine
0x14002d1f6  lea     r12, [rbp+Event]
0x14002d1fa  movups  xmm0, xmmword ptr [rax]
0x14002d1fd  movups  xmmword ptr [rax-48h], xmm0
0x14002d201  movups  xmm1, xmmword ptr [rax+10h]
0x14002d205  movups  xmmword ptr [rax-38h], xmm1
0x14002d209  movups  xmm0, xmmword ptr [rax+20h]
0x14002d20d  movups  xmmword ptr [rax-28h], xmm0
0x14002d211  movsd   xmm1, qword ptr [rax+30h]
0x14002d216  movsd   qword ptr [rax-18h], xmm1
0x14002d21b  mov     byte ptr [rax-45h], 0
0x14002d21f  mov     rax, [rbx+0B8h]
0x14002d226  mov     [rax-10h], rcx
0x14002d22a  lea     rcx, [rbp+Event]
0x14002d22e  mov     [rax-8], rcx
0x14002d232  mov     byte ptr [rax-45h], 0E0h
0x14002d236  jmp     loc_14002D328
0x14002d23b  mov     eax, [rsi+0C8h]
0x14002d241  test    al, 1
0x14002d243  jnz     loc_14002D328
0x14002d249  test    byte ptr [rdi+2], 10h
0x14002d24d  jnz     loc_14002D328
0x14002d253  mov     rax, [rbp+arg_8]
0x14002d257  test    dword ptr [rax+4], 10000h
0x14002d25e  jnz     loc_14002D328
0x14002d264  mov     edi, 0C0000022h
0x14002d269  jmp     loc_14002D12B
0x14002d26e  mov     rax, [rdi+30h]
0x14002d272  mov     r14, [rbp+arg_8]
0x14002d276  mov     ecx, [rax+50h]
0x14002d279  bt      ecx, 0Ch
0x14002d27d  jnb     short loc_14002D28D
0x14002d27f  test    dword ptr [r14+4], 40000h
0x14002d287  jnz     loc_14002D31D
0x14002d28d  cmp     [rbx+18h], r12
0x14002d291  jz      loc_14002D31D
0x14002d297  mov     rcx, rbx; Irp
0x14002d29a  call    cs:__imp_IoIs32bitProcess
0x14002d2a1  nop     dword ptr [rax+rax+00h]
0x14002d2a6  mov     ecx, [rdi+18h]
0x14002d2a9  test    al, al
0x14002d2ab  lea     eax, [rcx-4D004h]
0x14002d2b1  jz      short loc_14002D2DA
0x14002d2b3  test    eax, 0FFFFFFEFh
0x14002d2b8  jz      short loc_14002D2CA
0x14002d2ba  cmp     dword ptr [rdi+10h], 34h ; '4'
0x14002d2be  jb      short loc_14002D31D
0x14002d2c0  mov     rax, [rbx+18h]
0x14002d2c4  add     rax, 30h ; '0'
0x14002d2c8  jmp     short loc_14002D2FF
0x14002d2ca  cmp     dword ptr [rdi+10h], 2Ch ; ','
0x14002d2ce  jb      short loc_14002D31D
0x14002d2d0  mov     rax, [rbx+18h]
0x14002d2d4  add     rax, 1Ch
0x14002d2d8  jmp     short loc_14002D2FF
0x14002d2da  test    eax, 0FFFFFFEFh
0x14002d2df  jz      short loc_14002D2F1
0x14002d2e1  cmp     dword ptr [rdi+10h], 40h ; '@'
0x14002d2e5  jb      short loc_14002D31D
0x14002d2e7  mov     rax, [rbx+18h]
0x14002d2eb  add     rax, 38h ; '8'
0x14002d2ef  jmp     short loc_14002D2FF
0x14002d2f1  cmp     dword ptr [rdi+10h], 38h ; '8'
0x14002d2f5  jb      short loc_14002D31D
0x14002d2f7  mov     rax, [rbx+18h]
0x14002d2fb  add     rax, 24h ; '$'
0x14002d2ff  test    rax, rax
0x14002d302  jz      short loc_14002D31D
0x14002d304  cmp     byte ptr [rax], 4
0x14002d307  jnz     short loc_14002D31D
0x14002d309  bts     dword ptr [r14+4], 12h
0x14002d30f  mov     rcx, [rdi+30h]
0x14002d313  mov     eax, [rcx+50h]
0x14002d316  bts     eax, 0Ch
0x14002d31a  mov     [rcx+50h], eax
0x14002d31d  inc     byte ptr [rbx+43h]
0x14002d320  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14002d328  mov     rcx, [rsi+88h]; DeviceObject
0x14002d32f  mov     rdx, rbx; Irp
0x14002d332  call    cs:__imp_IofCallDriver
0x14002d339  nop     dword ptr [rax+rax+00h]
0x14002d33e  mov     r14d, eax
0x14002d341  cmp     eax, 103h
0x14002d346  jnz     short loc_14002D374
0x14002d348  test    r12, r12
0x14002d34b  jz      short loc_14002D3B9
0x14002d34d  xor     r9d, r9d; Alertable
0x14002d350  mov     [rsp+50h+Timeout], 0; Timeout
0x14002d359  xor     r8d, r8d; WaitMode
0x14002d35c  lea     rcx, [rbp+Event]; Object
0x14002d360  xor     edx, edx; WaitReason
0x14002d362  call    cs:__imp_KeWaitForSingleObject
0x14002d369  nop     dword ptr [rax+rax+00h]
0x14002d36e  mov     r14d, [rbx+30h]
0x14002d372  jmp     short loc_14002D379
0x14002d374  test    r12, r12
0x14002d377  jz      short loc_14002D3B9
0x14002d379  xor     edx, edx
0x14002d37b  jmp     short loc_14002D390
0x14002d37d  mov     rcx, [rdi+8]; Resource
0x14002d381  call    cs:__imp_ExReleaseResourceLite
0x14002d388  nop     dword ptr [rax+rax+00h]
0x14002d38d  mov     rdx, rdi
0x14002d390  mov     r8, [rsi+0D0h]
0x14002d397  call    FatGetNextFcbBottomUp
0x14002d39c  mov     rdi, rax
0x14002d39f  test    rax, rax
0x14002d3a2  jnz     short loc_14002D37D
0x14002d3a4  lea     rcx, [rsi+208h]; Resource
0x14002d3ab  call    cs:__imp_ExReleaseResourceLite
0x14002d3b2  nop     dword ptr [rax+rax+00h]
0x14002d3b7  jmp     short loc_14002D3BB
0x14002d3b9  xor     ebx, ebx
0x14002d3bb  mov     r8d, r14d
0x14002d3be  mov     rdx, rbx; Irp
0x14002d3c1  mov     rcx, r15; Entry
0x14002d3c4  call    FatCompleteRequest_Real
0x14002d3c9  mov     eax, r14d
0x14002d3cc  add     rsp, 50h
0x14002d3d0  pop     r15
0x14002d3d2  pop     r14
0x14002d3d4  pop     r12
0x14002d3d6  pop     rdi
0x14002d3d7  pop     rsi
0x14002d3d8  pop     rbx
0x14002d3d9  pop     rbp
0x14002d3da  retn
```
