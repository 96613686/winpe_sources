# FatPnpSurpriseRemove

- ea: `0x1400455f4`
- end: `0x140045736`
- name: `FatPnpSurpriseRemove`
- size: `322`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140044ff8`

## callees

- `0x140006350`
- `0x140038eb4`
- `0x14003f1bc`
- `0x1400455f4`
- `0x1400466c8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14004565f`
- `ntoskrnl!KeInitializeEvent` at `0x14004565f`
- `ntoskrnl!IofCallDriver` at `0x140045694`
- `ntoskrnl!IofCallDriver` at `0x140045694`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400456bf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400456bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400456fc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004570f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f6df`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f6f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400456fc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004570f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f6df`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f6f3`

## pseudocode

```c
__int64 __fastcall FatPnpSurpriseRemove(PVOID Entry, PIRP Irp, __int64 a3, __int64 a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v8; // rax
  unsigned int Status; // edi
  __int64 v10; // r9
  struct _KEVENT Event; // [rsp+38h] [rbp-40h] BYREF

  memset(&Event, 0, sizeof(Event));
  FatAcquireExclusiveVcb_Real(Entry, a3, 0, a4);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v8 = Irp->Tail.Overlay.CurrentStackLocation;
  v8[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&FatCallSelfCompletionRoutine;
  v8[-1].Context = &Event;
  v8[-1].Control = -32;
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(a3 + 136), Irp);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = Irp->IoStatus.Status;
  }
  FatFlushAndCleanVolume((__int64)Entry, (__int64)Irp, a3, 0);
  if ( !FatCheckForDismount((__int64)Entry, a3, 1) )
    ExReleaseResourceLite((PERESOURCE)(a3 + 520));
  ExReleaseResourceLite(&Resource);
  FatCompleteRequest_Real(Entry, Irp, Status, v10);
  return Status;
}

```

## disassembly

```asm
0x1400455f4  mov     [rsp+arg_10], r8
0x1400455f9  push    rbx
0x1400455fa  push    rsi
0x1400455fb  push    rdi
0x1400455fc  push    r14
0x1400455fe  sub     rsp, 58h
0x140045602  mov     rsi, r8
0x140045605  mov     rbx, rdx
0x140045608  mov     r14, rcx
0x14004560b  xorps   xmm0, xmm0
0x14004560e  xor     eax, eax
0x140045610  movups  xmmword ptr [rsp+78h+Event.Header], xmm0
0x140045615  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x14004561a  mov     [rsp+78h+var_48], al
0x14004561e  xor     r8d, r8d
0x140045621  mov     rdx, rsi
0x140045624  call    FatAcquireExclusiveVcb_Real
0x140045629  mov     rax, [rbx+0B8h]
0x140045630  movups  xmm0, xmmword ptr [rax]
0x140045633  movups  xmmword ptr [rax-48h], xmm0
0x140045637  movups  xmm1, xmmword ptr [rax+10h]
0x14004563b  movups  xmmword ptr [rax-38h], xmm1
0x14004563f  movups  xmm0, xmmword ptr [rax+20h]
0x140045643  movups  xmmword ptr [rax-28h], xmm0
0x140045647  movsd   xmm1, qword ptr [rax+30h]
0x14004564c  movsd   qword ptr [rax-18h], xmm1
0x140045651  mov     byte ptr [rax-45h], 0
0x140045655  xor     r8d, r8d; State
0x140045658  xor     edx, edx; Type
0x14004565a  lea     rcx, [rsp+78h+Event]; Event
0x14004565f  call    cs:__imp_KeInitializeEvent
0x140045666  nop     dword ptr [rax+rax+00h]
0x14004566b  mov     rax, [rbx+0B8h]
0x140045672  lea     rcx, FatCallSelfCompletionRoutine
0x140045679  mov     [rax-10h], rcx
0x14004567d  lea     rcx, [rsp+78h+Event]
0x140045682  mov     [rax-8], rcx
0x140045686  mov     byte ptr [rax-45h], 0E0h
0x14004568a  mov     rdx, rbx; Irp
0x14004568d  mov     rcx, [rsi+88h]; DeviceObject
0x140045694  call    cs:__imp_IofCallDriver
0x14004569b  nop     dword ptr [rax+rax+00h]
0x1400456a0  mov     edi, eax
0x1400456a2  cmp     eax, 103h
0x1400456a7  jnz     short loc_1400456CE
0x1400456a9  mov     [rsp+78h+Timeout], 0; Timeout
0x1400456b2  xor     r9d, r9d; Alertable
0x1400456b5  xor     r8d, r8d; WaitMode
0x1400456b8  xor     edx, edx; WaitReason
0x1400456ba  lea     rcx, [rsp+78h+Event]; Object
0x1400456bf  call    cs:__imp_KeWaitForSingleObject
0x1400456c6  nop     dword ptr [rax+rax+00h]
0x1400456cb  mov     edi, [rbx+30h]
0x1400456ce  xor     r9d, r9d
0x1400456d1  mov     r8, rsi
0x1400456d4  mov     rdx, rbx
0x1400456d7  mov     rcx, r14
0x1400456da  call    FatFlushAndCleanVolume
0x1400456df  mov     r8b, 1
0x1400456e2  mov     rdx, rsi
0x1400456e5  mov     rcx, r14
0x1400456e8  call    FatCheckForDismount
0x1400456ed  mov     [rsp+78h+var_48], al
0x1400456f1  test    al, al
0x1400456f3  jnz     short loc_140045708
0x1400456f5  lea     rcx, [rsi+208h]; Resource
0x1400456fc  call    cs:__imp_ExReleaseResourceLite
0x140045703  nop     dword ptr [rax+rax+00h]
0x140045708  lea     rcx, Resource; Resource
0x14004570f  call    cs:__imp_ExReleaseResourceLite
0x140045716  nop     dword ptr [rax+rax+00h]
0x14004571b  mov     r8d, edi
0x14004571e  mov     rdx, rbx; Irp
0x140045721  mov     rcx, r14; Entry
0x140045724  call    FatCompleteRequest_Real
0x140045729  mov     eax, edi
0x14004572b  add     rsp, 58h
0x14004572f  pop     r14
0x140045731  pop     rdi
0x140045732  pop     rsi
0x140045733  pop     rbx
0x140045734  retn
0x14005f6c2  push    rbp
0x14005f6c4  sub     rsp, 30h
0x14005f6c8  mov     rbp, rdx
0x14005f6cb  cmp     byte ptr [rbp+30h], 0
0x14005f6cf  jnz     short loc_14005F6EC
0x14005f6d1  mov     rcx, [rbp+90h]
0x14005f6d8  add     rcx, 208h; Resource
0x14005f6df  call    cs:__imp_ExReleaseResourceLite
0x14005f6e6  nop     dword ptr [rax+rax+00h]
0x14005f6eb  nop
0x14005f6ec  lea     rcx, Resource; Resource
0x14005f6f3  call    cs:__imp_ExReleaseResourceLite
0x14005f6fa  nop     dword ptr [rax+rax+00h]
0x14005f6ff  nop
0x14005f700  add     rsp, 30h
0x14005f704  pop     rbp
0x14005f705  retn
```
