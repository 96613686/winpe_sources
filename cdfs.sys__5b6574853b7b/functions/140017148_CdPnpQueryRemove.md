# CdPnpQueryRemove

- ea: `0x140017148`
- end: `0x140017345`
- name: `CdPnpQueryRemove`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140016fe8`

## callees

- `0x140001160`
- `0x140001fd0`
- `0x1400024e0`
- `0x140017148`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001718c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017210`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001718c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017210`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400171a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001722d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400171a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001722d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400171bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400171db`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017308`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001731b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400171bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400171db`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017308`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001731b`
- `ntoskrnl!KeInitializeEvent` at `0x140017277`
- `ntoskrnl!KeInitializeEvent` at `0x140017277`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400171f0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400171f0`
- `ntoskrnl!IofCallDriver` at `0x1400172a9`
- `ntoskrnl!IofCallDriver` at `0x1400172a9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400172d4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400172d4`

## pseudocode

```c
__int64 __fastcall CdPnpQueryRemove(void *a1, IRP *a2, __int64 a3)
{
  struct _ERESOURCE *v3; // r15
  NTSTATUS Status; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v9; // rax
  struct _KEVENT Event; // [rsp+30h] [rbp-58h] BYREF

  v3 = (struct _ERESOURCE *)(a3 + 128);
  memset(&Event, 0, sizeof(Event));
  CdAcquireResource(a1, a3 + 128, 0, 0);
  ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
  ++*(_DWORD *)(a3 + 60);
  *(_QWORD *)(a3 + 392) = 0;
  ExReleaseFastMutex((PFAST_MUTEX)(a3 + 336));
  ExReleaseResourceLite(&Resource);
  Status = CdLockVolumeInternal((__int64)a1, a3, 0);
  ExReleaseResourceLite(v3);
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  CdAcquireResource(a1, v3, 0, 0);
  ExAcquireFastMutex((PFAST_MUTEX)(a3 + 336));
  --*(_DWORD *)(a3 + 60);
  *(_QWORD *)(a3 + 392) = 0;
  ExReleaseFastMutex((PFAST_MUTEX)(a3 + 336));
  if ( Status < 0 )
    goto LABEL_8;
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
  if ( Status < 0 )
    goto LABEL_8;
  if ( CdCheckForDismount((__int64)a1, a3, 1) )
  {
    if ( *(_DWORD *)(a3 + 60) )
      Status = -2147483631;
LABEL_8:
    ExReleaseResourceLite(v3);
  }
  ExReleaseResourceLite(&Resource);
  CdCompleteRequest(a1, a2, Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140017148  push    rbx
0x14001714a  push    rbp
0x14001714b  push    rsi
0x14001714c  push    rdi
0x14001714d  push    r14
0x14001714f  push    r15
0x140017151  sub     rsp, 58h
0x140017155  lea     r15, [r8+80h]
0x14001715c  mov     rsi, r8
0x14001715f  mov     rbp, rdx
0x140017162  xorps   xmm0, xmm0
0x140017165  xor     eax, eax
0x140017167  mov     rdx, r15
0x14001716a  xor     r9d, r9d
0x14001716d  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140017172  xor     r8d, r8d
0x140017175  mov     r14, rcx
0x140017178  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14001717d  call    CdAcquireResource
0x140017182  lea     rbx, [rsi+150h]
0x140017189  mov     rcx, rbx; FastMutex
0x14001718c  call    cs:__imp_ExAcquireFastMutex
0x140017193  nop     dword ptr [rax+rax+00h]
0x140017198  inc     dword ptr [rsi+3Ch]
0x14001719b  mov     rcx, rbx; FastMutex
0x14001719e  mov     qword ptr [rsi+188h], 0
0x1400171a9  call    cs:__imp_ExReleaseFastMutex
0x1400171b0  nop     dword ptr [rax+rax+00h]
0x1400171b5  lea     rcx, Resource; Resource
0x1400171bc  call    cs:__imp_ExReleaseResourceLite
0x1400171c3  nop     dword ptr [rax+rax+00h]
0x1400171c8  xor     r8d, r8d
0x1400171cb  mov     rdx, rsi
0x1400171ce  mov     rcx, r14
0x1400171d1  call    CdLockVolumeInternal
0x1400171d6  mov     rcx, r15; Resource
0x1400171d9  mov     edi, eax
0x1400171db  call    cs:__imp_ExReleaseResourceLite
0x1400171e2  nop     dword ptr [rax+rax+00h]
0x1400171e7  mov     dl, 1; Wait
0x1400171e9  lea     rcx, Resource; Resource
0x1400171f0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400171f7  nop     dword ptr [rax+rax+00h]
0x1400171fc  xor     r9d, r9d
0x1400171ff  xor     r8d, r8d
0x140017202  mov     rdx, r15
0x140017205  mov     rcx, r14
0x140017208  call    CdAcquireResource
0x14001720d  mov     rcx, rbx; FastMutex
0x140017210  call    cs:__imp_ExAcquireFastMutex
0x140017217  nop     dword ptr [rax+rax+00h]
0x14001721c  dec     dword ptr [rsi+3Ch]
0x14001721f  mov     rcx, rbx; FastMutex
0x140017222  mov     qword ptr [rsi+188h], 0
0x14001722d  call    cs:__imp_ExReleaseFastMutex
0x140017234  nop     dword ptr [rax+rax+00h]
0x140017239  test    edi, edi
0x14001723b  js      loc_140017305
0x140017241  mov     rax, [rbp+0B8h]
0x140017248  lea     rcx, [rsp+88h+Event]; Event
0x14001724d  xor     r8d, r8d; State
0x140017250  xor     edx, edx; Type
0x140017252  movups  xmm0, xmmword ptr [rax]
0x140017255  movups  xmmword ptr [rax-48h], xmm0
0x140017259  movups  xmm1, xmmword ptr [rax+10h]
0x14001725d  movups  xmmword ptr [rax-38h], xmm1
0x140017261  movups  xmm0, xmmword ptr [rax+20h]
0x140017265  movups  xmmword ptr [rax-28h], xmm0
0x140017269  movsd   xmm1, qword ptr [rax+30h]
0x14001726e  movsd   qword ptr [rax-18h], xmm1
0x140017273  mov     byte ptr [rax-45h], 0
0x140017277  call    cs:__imp_KeInitializeEvent
0x14001727e  nop     dword ptr [rax+rax+00h]
0x140017283  mov     rax, [rbp+0B8h]
0x14001728a  lea     rcx, CdSyncCompletionRoutine
0x140017291  mov     rdx, rbp; Irp
0x140017294  mov     [rax-10h], rcx
0x140017298  lea     rcx, [rsp+88h+Event]
0x14001729d  mov     [rax-8], rcx
0x1400172a1  mov     byte ptr [rax-45h], 0E0h
0x1400172a5  mov     rcx, [rsi+10h]; DeviceObject
0x1400172a9  call    cs:__imp_IofCallDriver
0x1400172b0  nop     dword ptr [rax+rax+00h]
0x1400172b5  mov     edi, eax
0x1400172b7  cmp     eax, 103h
0x1400172bc  jnz     short loc_1400172E3
0x1400172be  xor     r9d, r9d; Alertable
0x1400172c1  mov     [rsp+88h+Timeout], 0; Timeout
0x1400172ca  xor     r8d, r8d; WaitMode
0x1400172cd  lea     rcx, [rsp+88h+Event]; Object
0x1400172d2  xor     edx, edx; WaitReason
0x1400172d4  call    cs:__imp_KeWaitForSingleObject
0x1400172db  nop     dword ptr [rax+rax+00h]
0x1400172e0  mov     edi, [rbp+30h]
0x1400172e3  test    edi, edi
0x1400172e5  js      short loc_140017305
0x1400172e7  mov     r8b, 1
0x1400172ea  mov     rdx, rsi
0x1400172ed  mov     rcx, r14
0x1400172f0  call    CdCheckForDismount
0x1400172f5  test    al, al
0x1400172f7  jz      short loc_140017314
0x1400172f9  cmp     dword ptr [rsi+3Ch], 0
0x1400172fd  mov     eax, 80000011h
0x140017302  cmovnz  edi, eax
0x140017305  mov     rcx, r15; Resource
0x140017308  call    cs:__imp_ExReleaseResourceLite
0x14001730f  nop     dword ptr [rax+rax+00h]
0x140017314  lea     rcx, Resource; Resource
0x14001731b  call    cs:__imp_ExReleaseResourceLite
0x140017322  nop     dword ptr [rax+rax+00h]
0x140017327  mov     r8d, edi
0x14001732a  mov     rdx, rbp
0x14001732d  mov     rcx, r14
0x140017330  call    CdCompleteRequest
0x140017335  mov     eax, edi
0x140017337  add     rsp, 58h
0x14001733b  pop     r15
0x14001733d  pop     r14
0x14001733f  pop     rdi
0x140017340  pop     rsi
0x140017341  pop     rbp
0x140017342  pop     rbx
0x140017343  retn
```
