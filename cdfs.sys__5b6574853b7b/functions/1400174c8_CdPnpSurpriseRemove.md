# CdPnpSurpriseRemove

- ea: `0x1400174c8`
- end: `0x14001762f`
- name: `CdPnpSurpriseRemove`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140016fe8`

## callees

- `0x140001160`
- `0x1400024e0`
- `0x1400174c8`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001750a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001750a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017531`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017531`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400175f4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017607`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400175f4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017607`
- `ntoskrnl!KeInitializeEvent` at `0x140017573`
- `ntoskrnl!KeInitializeEvent` at `0x140017573`
- `ntoskrnl!IofCallDriver` at `0x1400175a5`
- `ntoskrnl!IofCallDriver` at `0x1400175a5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400175d0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400175d0`

## pseudocode

```c
__int64 __fastcall CdPnpSurpriseRemove(void *a1, IRP *a2, __int64 a3)
{
  struct _ERESOURCE *v3; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v8; // rax
  unsigned int Status; // edi
  struct _KEVENT Event; // [rsp+30h] [rbp-48h] BYREF

  v3 = (struct _ERESOURCE *)(a3 + 128);
  memset(&Event, 0, sizeof(Event));
  CdAcquireResource(a1, a3 + 128, 0, 0);
  ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
  if ( *(_DWORD *)(a3 + 52) != 4 )
    *(_DWORD *)(a3 + 52) = 3;
  *(_QWORD *)(a3 + 392) = 0;
  ExReleaseFastMutex((PFAST_MUTEX)(a3 + 336));
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v8 = a2->Tail.Overlay.CurrentStackLocation;
  v8[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CdSyncCompletionRoutine;
  v8[-1].Context = &Event;
  v8[-1].Control = -32;
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
0x1400174c8  push    rbx
0x1400174ca  push    rbp
0x1400174cb  push    rsi
0x1400174cc  push    rdi
0x1400174cd  push    r14
0x1400174cf  sub     rsp, 50h
0x1400174d3  lea     r14, [r8+80h]
0x1400174da  mov     rbx, r8
0x1400174dd  mov     rsi, rdx
0x1400174e0  xorps   xmm0, xmm0
0x1400174e3  xor     eax, eax
0x1400174e5  mov     rdx, r14
0x1400174e8  xor     r9d, r9d
0x1400174eb  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x1400174f0  xor     r8d, r8d
0x1400174f3  mov     rbp, rcx
0x1400174f6  movups  xmmword ptr [rsp+78h+Event.Header], xmm0
0x1400174fb  call    CdAcquireResource
0x140017500  lea     rdi, [rbx+150h]
0x140017507  mov     rcx, rdi; FastMutex
0x14001750a  call    cs:__imp_ExAcquireFastMutex
0x140017511  nop     dword ptr [rax+rax+00h]
0x140017516  cmp     dword ptr [rbx+34h], 4
0x14001751a  jz      short loc_140017523
0x14001751c  mov     dword ptr [rbx+34h], 3
0x140017523  mov     rcx, rdi; FastMutex
0x140017526  mov     qword ptr [rbx+188h], 0
0x140017531  call    cs:__imp_ExReleaseFastMutex
0x140017538  nop     dword ptr [rax+rax+00h]
0x14001753d  mov     rax, [rsi+0B8h]
0x140017544  lea     rcx, [rsp+78h+Event]; Event
0x140017549  xor     r8d, r8d; State
0x14001754c  xor     edx, edx; Type
0x14001754e  movups  xmm0, xmmword ptr [rax]
0x140017551  movups  xmmword ptr [rax-48h], xmm0
0x140017555  movups  xmm1, xmmword ptr [rax+10h]
0x140017559  movups  xmmword ptr [rax-38h], xmm1
0x14001755d  movups  xmm0, xmmword ptr [rax+20h]
0x140017561  movups  xmmword ptr [rax-28h], xmm0
0x140017565  movsd   xmm1, qword ptr [rax+30h]
0x14001756a  movsd   qword ptr [rax-18h], xmm1
0x14001756f  mov     byte ptr [rax-45h], 0
0x140017573  call    cs:__imp_KeInitializeEvent
0x14001757a  nop     dword ptr [rax+rax+00h]
0x14001757f  mov     rax, [rsi+0B8h]
0x140017586  lea     rcx, CdSyncCompletionRoutine
0x14001758d  mov     rdx, rsi; Irp
0x140017590  mov     [rax-10h], rcx
0x140017594  lea     rcx, [rsp+78h+Event]
0x140017599  mov     [rax-8], rcx
0x14001759d  mov     byte ptr [rax-45h], 0E0h
0x1400175a1  mov     rcx, [rbx+10h]; DeviceObject
0x1400175a5  call    cs:__imp_IofCallDriver
0x1400175ac  nop     dword ptr [rax+rax+00h]
0x1400175b1  mov     edi, eax
0x1400175b3  cmp     eax, 103h
0x1400175b8  jnz     short loc_1400175DF
0x1400175ba  xor     r9d, r9d; Alertable
0x1400175bd  mov     [rsp+78h+Timeout], 0; Timeout
0x1400175c6  xor     r8d, r8d; WaitMode
0x1400175c9  lea     rcx, [rsp+78h+Event]; Object
0x1400175ce  xor     edx, edx; WaitReason
0x1400175d0  call    cs:__imp_KeWaitForSingleObject
0x1400175d7  nop     dword ptr [rax+rax+00h]
0x1400175dc  mov     edi, [rsi+30h]
0x1400175df  mov     r8b, 1
0x1400175e2  mov     rdx, rbx
0x1400175e5  mov     rcx, rbp
0x1400175e8  call    CdCheckForDismount
0x1400175ed  test    al, al
0x1400175ef  jz      short loc_140017600
0x1400175f1  mov     rcx, r14; Resource
0x1400175f4  call    cs:__imp_ExReleaseResourceLite
0x1400175fb  nop     dword ptr [rax+rax+00h]
0x140017600  lea     rcx, Resource; Resource
0x140017607  call    cs:__imp_ExReleaseResourceLite
0x14001760e  nop     dword ptr [rax+rax+00h]
0x140017613  mov     r8d, edi
0x140017616  mov     rdx, rsi
0x140017619  mov     rcx, rbp
0x14001761c  call    CdCompleteRequest
0x140017621  mov     eax, edi
0x140017623  add     rsp, 50h
0x140017627  pop     r14
0x140017629  pop     rdi
0x14001762a  pop     rsi
0x14001762b  pop     rbp
0x14001762c  pop     rbx
0x14001762d  retn
```
