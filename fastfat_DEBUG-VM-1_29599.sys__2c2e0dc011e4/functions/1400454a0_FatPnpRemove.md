# FatPnpRemove

- ea: `0x1400454a0`
- end: `0x1400455ed`
- name: `FatPnpRemove`
- size: `333`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140044ff8`

## callees

- `0x140005eb4`
- `0x140006350`
- `0x140038eb4`
- `0x14003f1bc`
- `0x1400454a0`
- `0x1400455f4`
- `0x1400466c8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140045516`
- `ntoskrnl!KeInitializeEvent` at `0x140045516`
- `ntoskrnl!IofCallDriver` at `0x14004554b`
- `ntoskrnl!IofCallDriver` at `0x14004554b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045576`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045576`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400455b3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400455c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400455b3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400455c6`

## pseudocode

```c
__int64 __fastcall FatPnpRemove(PVOID Entry, PIRP Irp, __int64 a3)
{
  __int64 v6; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v8; // rax
  unsigned int Status; // esi
  __int64 v10; // r9
  struct _KEVENT Event; // [rsp+38h] [rbp-40h] BYREF

  memset(&Event, 0, sizeof(Event));
  FatAcquireExclusiveVcb_Real(Entry, a3, 0);
  FatUnlockVolumeInternal(v6, a3, 0);
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
0x1400454a0  mov     [rsp+arg_10], r8
0x1400454a5  push    rbx
0x1400454a6  push    rsi
0x1400454a7  push    rdi
0x1400454a8  push    r14
0x1400454aa  sub     rsp, 58h
0x1400454ae  mov     rbx, r8
0x1400454b1  mov     rdi, rdx
0x1400454b4  mov     r14, rcx
0x1400454b7  xorps   xmm0, xmm0
0x1400454ba  xor     eax, eax
0x1400454bc  movups  xmmword ptr [rsp+78h+Event.Header], xmm0
0x1400454c1  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x1400454c6  mov     [rsp+78h+var_48], al
0x1400454ca  xor     r8d, r8d
0x1400454cd  mov     rdx, rbx
0x1400454d0  call    FatAcquireExclusiveVcb_Real
0x1400454d5  xor     r8d, r8d
0x1400454d8  mov     rdx, rbx
0x1400454db  call    FatUnlockVolumeInternal
0x1400454e0  mov     rax, [rdi+0B8h]
0x1400454e7  movups  xmm0, xmmword ptr [rax]
0x1400454ea  movups  xmmword ptr [rax-48h], xmm0
0x1400454ee  movups  xmm1, xmmword ptr [rax+10h]
0x1400454f2  movups  xmmword ptr [rax-38h], xmm1
0x1400454f6  movups  xmm0, xmmword ptr [rax+20h]
0x1400454fa  movups  xmmword ptr [rax-28h], xmm0
0x1400454fe  movsd   xmm1, qword ptr [rax+30h]
0x140045503  movsd   qword ptr [rax-18h], xmm1
0x140045508  mov     byte ptr [rax-45h], 0
0x14004550c  xor     r8d, r8d; State
0x14004550f  xor     edx, edx; Type
0x140045511  lea     rcx, [rsp+78h+Event]; Event
0x140045516  call    cs:__imp_KeInitializeEvent
0x14004551d  nop     dword ptr [rax+rax+00h]
0x140045522  mov     rax, [rdi+0B8h]
0x140045529  lea     rcx, FatCallSelfCompletionRoutine
0x140045530  mov     [rax-10h], rcx
0x140045534  lea     rcx, [rsp+78h+Event]
0x140045539  mov     [rax-8], rcx
0x14004553d  mov     byte ptr [rax-45h], 0E0h
0x140045541  mov     rdx, rdi; Irp
0x140045544  mov     rcx, [rbx+88h]; DeviceObject
0x14004554b  call    cs:__imp_IofCallDriver
0x140045552  nop     dword ptr [rax+rax+00h]
0x140045557  mov     esi, eax
0x140045559  cmp     eax, 103h
0x14004555e  jnz     short loc_140045585
0x140045560  mov     [rsp+78h+Timeout], 0; Timeout
0x140045569  xor     r9d, r9d; Alertable
0x14004556c  xor     r8d, r8d; WaitMode
0x14004556f  xor     edx, edx; WaitReason
0x140045571  lea     rcx, [rsp+78h+Event]; Object
0x140045576  call    cs:__imp_KeWaitForSingleObject
0x14004557d  nop     dword ptr [rax+rax+00h]
0x140045582  mov     esi, [rdi+30h]
0x140045585  xor     r9d, r9d
0x140045588  mov     r8, rbx
0x14004558b  mov     rdx, rdi
0x14004558e  mov     rcx, r14
0x140045591  call    FatFlushAndCleanVolume
0x140045596  mov     r8b, 1
0x140045599  mov     rdx, rbx
0x14004559c  mov     rcx, r14
0x14004559f  call    FatCheckForDismount
0x1400455a4  mov     [rsp+78h+var_48], al
0x1400455a8  test    al, al
0x1400455aa  jnz     short loc_1400455BF
0x1400455ac  lea     rcx, [rbx+208h]; Resource
0x1400455b3  call    cs:__imp_ExReleaseResourceLite
0x1400455ba  nop     dword ptr [rax+rax+00h]
0x1400455bf  lea     rcx, Resource; Resource
0x1400455c6  call    cs:__imp_ExReleaseResourceLite
0x1400455cd  nop     dword ptr [rax+rax+00h]
0x1400455d2  mov     r8d, esi
0x1400455d5  mov     rdx, rdi; Irp
0x1400455d8  mov     rcx, r14; Entry
0x1400455db  call    FatCompleteRequest_Real
0x1400455e0  mov     eax, esi
0x1400455e2  add     rsp, 58h
0x1400455e6  pop     r14
0x1400455e8  pop     rdi
0x1400455e9  pop     rsi
0x1400455ea  pop     rbx
0x1400455eb  retn
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
