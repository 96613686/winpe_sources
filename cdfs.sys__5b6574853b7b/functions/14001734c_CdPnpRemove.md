# CdPnpRemove

- ea: `0x14001734c`
- end: `0x1400174c2`
- name: `CdPnpRemove`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140016fe8`

## callees

- `0x140001160`
- `0x1400021c4`
- `0x1400024e0`
- `0x14001734c`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001739d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001739d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400173c4`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400173c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017487`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001749a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017487`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001749a`
- `ntoskrnl!KeInitializeEvent` at `0x140017406`
- `ntoskrnl!KeInitializeEvent` at `0x140017406`
- `ntoskrnl!IofCallDriver` at `0x140017438`
- `ntoskrnl!IofCallDriver` at `0x140017438`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017463`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017463`

## pseudocode

```c
__int64 __fastcall CdPnpRemove(void *a1, IRP *a2, __int64 a3)
{
  struct _ERESOURCE *v3; // r14
  __int64 v7; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v9; // rax
  unsigned int Status; // edi
  struct _KEVENT Event; // [rsp+30h] [rbp-48h] BYREF

  v3 = (struct _ERESOURCE *)(a3 + 128);
  memset(&Event, 0, sizeof(Event));
  CdAcquireResource(a1, a3 + 128, 0, 0);
  if ( (int)CdUnlockVolumeInternal(v7, a3, 0) < 0 )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
    if ( *(_DWORD *)(a3 + 52) != 4 )
      *(_DWORD *)(a3 + 52) = 3;
    *(_QWORD *)(a3 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a3 + 336));
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v9 = a2->Tail.Overlay.CurrentStackLocation;
  v9[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CdSyncCompletionRoutine;
  v9[-1].Context = &Event;
  v9[-1].Control = -32;
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(a3 + 16), a2);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = a2->IoStatus.Status;
  }
  if ( CdCheckForDismount((__int64)a1, a3, 1) )
    ExReleaseResourceLite(v3);
  ExReleaseResourceLite(&Resource);
  CdCompleteRequest(a1, a2, Status);
  return Status;
}

```

## disassembly

```asm
0x14001734c  push    rbx
0x14001734e  push    rbp
0x14001734f  push    rsi
0x140017350  push    rdi
0x140017351  push    r14
0x140017353  sub     rsp, 50h
0x140017357  lea     r14, [r8+80h]
0x14001735e  mov     rbx, r8
0x140017361  mov     rsi, rdx
0x140017364  xorps   xmm0, xmm0
0x140017367  xor     eax, eax
0x140017369  mov     rdx, r14
0x14001736c  xor     r9d, r9d
0x14001736f  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x140017374  xor     r8d, r8d
0x140017377  mov     rbp, rcx
0x14001737a  movups  xmmword ptr [rsp+78h+Event.Header], xmm0
0x14001737f  call    CdAcquireResource
0x140017384  xor     r8d, r8d
0x140017387  mov     rdx, rbx
0x14001738a  call    CdUnlockVolumeInternal
0x14001738f  test    eax, eax
0x140017391  jns     short loc_1400173D0
0x140017393  lea     rdi, [rbx+150h]
0x14001739a  mov     rcx, rdi; FastMutex
0x14001739d  call    cs:__imp_ExAcquireFastMutex
0x1400173a4  nop     dword ptr [rax+rax+00h]
0x1400173a9  cmp     dword ptr [rbx+34h], 4
0x1400173ad  jz      short loc_1400173B6
0x1400173af  mov     dword ptr [rbx+34h], 3
0x1400173b6  mov     rcx, rdi; FastMutex
0x1400173b9  mov     qword ptr [rbx+188h], 0
0x1400173c4  call    cs:__imp_ExReleaseFastMutex
0x1400173cb  nop     dword ptr [rax+rax+00h]
0x1400173d0  mov     rax, [rsi+0B8h]
0x1400173d7  lea     rcx, [rsp+78h+Event]; Event
0x1400173dc  xor     r8d, r8d; State
0x1400173df  xor     edx, edx; Type
0x1400173e1  movups  xmm0, xmmword ptr [rax]
0x1400173e4  movups  xmmword ptr [rax-48h], xmm0
0x1400173e8  movups  xmm1, xmmword ptr [rax+10h]
0x1400173ec  movups  xmmword ptr [rax-38h], xmm1
0x1400173f0  movups  xmm0, xmmword ptr [rax+20h]
0x1400173f4  movups  xmmword ptr [rax-28h], xmm0
0x1400173f8  movsd   xmm1, qword ptr [rax+30h]
0x1400173fd  movsd   qword ptr [rax-18h], xmm1
0x140017402  mov     byte ptr [rax-45h], 0
0x140017406  call    cs:__imp_KeInitializeEvent
0x14001740d  nop     dword ptr [rax+rax+00h]
0x140017412  mov     rax, [rsi+0B8h]
0x140017419  lea     rcx, CdSyncCompletionRoutine
0x140017420  mov     rdx, rsi; Irp
0x140017423  mov     [rax-10h], rcx
0x140017427  lea     rcx, [rsp+78h+Event]
0x14001742c  mov     [rax-8], rcx
0x140017430  mov     byte ptr [rax-45h], 0E0h
0x140017434  mov     rcx, [rbx+10h]; DeviceObject
0x140017438  call    cs:__imp_IofCallDriver
0x14001743f  nop     dword ptr [rax+rax+00h]
0x140017444  mov     edi, eax
0x140017446  cmp     eax, 103h
0x14001744b  jnz     short loc_140017472
0x14001744d  xor     r9d, r9d; Alertable
0x140017450  mov     [rsp+78h+Timeout], 0; Timeout
0x140017459  xor     r8d, r8d; WaitMode
0x14001745c  lea     rcx, [rsp+78h+Event]; Object
0x140017461  xor     edx, edx; WaitReason
0x140017463  call    cs:__imp_KeWaitForSingleObject
0x14001746a  nop     dword ptr [rax+rax+00h]
0x14001746f  mov     edi, [rsi+30h]
0x140017472  mov     r8b, 1
0x140017475  mov     rdx, rbx
0x140017478  mov     rcx, rbp
0x14001747b  call    CdCheckForDismount
0x140017480  test    al, al
0x140017482  jz      short loc_140017493
0x140017484  mov     rcx, r14; Resource
0x140017487  call    cs:__imp_ExReleaseResourceLite
0x14001748e  nop     dword ptr [rax+rax+00h]
0x140017493  lea     rcx, Resource; Resource
0x14001749a  call    cs:__imp_ExReleaseResourceLite
0x1400174a1  nop     dword ptr [rax+rax+00h]
0x1400174a6  mov     r8d, edi
0x1400174a9  mov     rdx, rsi
0x1400174ac  mov     rcx, rbp
0x1400174af  call    CdCompleteRequest
0x1400174b4  mov     eax, edi
0x1400174b6  add     rsp, 50h
0x1400174ba  pop     r14
0x1400174bc  pop     rdi
0x1400174bd  pop     rsi
0x1400174be  pop     rbp
0x1400174bf  pop     rbx
0x1400174c0  retn
```
