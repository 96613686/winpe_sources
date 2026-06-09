# FatPnpQueryRemove

- ea: `0x1400452a0`
- end: `0x14004549a`
- name: `FatPnpQueryRemove`
- size: `506`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140044ff8`

## callees

- `0x140005a94`
- `0x140005fd8`
- `0x140006350`
- `0x140038eb4`
- `0x14003f1bc`
- `0x1400452a0`
- `0x1400466c8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400453b7`
- `ntoskrnl!KeInitializeEvent` at `0x1400453b7`
- `ntoskrnl!IofCallDriver` at `0x1400453f8`
- `ntoskrnl!IofCallDriver` at `0x1400453f8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045427`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045427`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004533b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004533b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400452e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045320`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004545c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004546f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f68e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f6a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400452e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045320`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004545c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004546f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f68e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f6a8`

## pseudocode

```c
__int64 __fastcall FatPnpQueryRemove(_DWORD *Entry, PIRP Irp, __int64 a3, __int64 a4)
{
  char v7; // r14
  __int64 v8; // r9
  int Status; // ebx
  __int64 v10; // r9
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v12; // rax
  __int64 v13; // r9
  struct _KEVENT Event; // [rsp+38h] [rbp-50h] BYREF

  memset(&Event, 0, sizeof(Event));
  v7 = 0;
  FatAcquireExclusiveVcb_Real(Entry, a3, 0, a4);
  ExReleaseResourceLite(&Resource);
  Status = FatLockVolumeInternal((__int64)Entry, a3, 0, v8);
  FatPnpAdjustVpbRefCount(a3, 1);
  ExReleaseResourceLite((PERESOURCE)(a3 + 520));
  ExAcquireResourceExclusiveLite(&Resource, (Entry[17] & 2) != 0);
  FatAcquireExclusiveVcb_Real(Entry, a3, 0, v10);
  FatPnpAdjustVpbRefCount(a3, 0xFFFFFFFFLL);
  if ( Status >= 0 )
  {
    FatFlushAndCleanVolume((__int64)Entry, (__int64)Irp, a3, 1u);
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v12 = Irp->Tail.Overlay.CurrentStackLocation;
    v12[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&FatCallSelfCompletionRoutine;
    v12[-1].Context = &Event;
    v12[-1].Control = 0;
    v12[-1].Control = 64;
    v12[-1].Control = -64;
    v12[-1].Control = -32;
    Status = IofCallDriver(*(PDEVICE_OBJECT *)(a3 + 136), Irp);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = Irp->IoStatus.Status;
    }
    if ( Status >= 0 )
      v7 = FatCheckForDismount((__int64)Entry, a3, 1);
  }
  if ( !v7 )
    ExReleaseResourceLite((PERESOURCE)(a3 + 520));
  ExReleaseResourceLite(&Resource);
  FatCompleteRequest_Real(Entry, Irp, (unsigned int)Status, v13);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400452a0  mov     [rsp+arg_10], r8
0x1400452a5  push    rbx
0x1400452a6  push    rsi
0x1400452a7  push    rdi
0x1400452a8  push    r12
0x1400452aa  push    r14
0x1400452ac  push    r15
0x1400452ae  sub     rsp, 58h
0x1400452b2  mov     rdi, r8
0x1400452b5  mov     r15, rdx
0x1400452b8  mov     rsi, rcx
0x1400452bb  xorps   xmm0, xmm0
0x1400452be  xor     eax, eax
0x1400452c0  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x1400452c5  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x1400452ca  xor     r14b, r14b
0x1400452cd  mov     [rsp+88h+var_58], r14b
0x1400452d2  xor     r8d, r8d
0x1400452d5  mov     rdx, rdi
0x1400452d8  call    FatAcquireExclusiveVcb_Real
0x1400452dd  lea     rcx, Resource; Resource
0x1400452e4  call    cs:__imp_ExReleaseResourceLite
0x1400452eb  nop     dword ptr [rax+rax+00h]
0x1400452f0  mov     [rsp+88h+var_57], r14b
0x1400452f5  xor     r8d, r8d
0x1400452f8  mov     rdx, rdi
0x1400452fb  mov     rcx, rsi
0x1400452fe  call    FatLockVolumeInternal
0x140045303  mov     ebx, eax
0x140045305  mov     [rsp+88h+var_54], eax
0x140045309  mov     edx, 1
0x14004530e  mov     rcx, rdi
0x140045311  call    FatPnpAdjustVpbRefCount
0x140045316  lea     r12, [rdi+208h]
0x14004531d  mov     rcx, r12; Resource
0x140045320  call    cs:__imp_ExReleaseResourceLite
0x140045327  nop     dword ptr [rax+rax+00h]
0x14004532c  mov     edx, [rsi+44h]
0x14004532f  shr     edx, 1
0x140045331  and     dl, 1; Wait
0x140045334  lea     rcx, Resource; Resource
0x14004533b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140045342  nop     dword ptr [rax+rax+00h]
0x140045347  mov     [rsp+88h+var_57], 1
0x14004534c  xor     r8d, r8d
0x14004534f  mov     rdx, rdi
0x140045352  mov     rcx, rsi
0x140045355  call    FatAcquireExclusiveVcb_Real
0x14004535a  or      edx, 0FFFFFFFFh
0x14004535d  mov     rcx, rdi
0x140045360  call    FatPnpAdjustVpbRefCount
0x140045365  test    ebx, ebx
0x140045367  js      loc_140045454
0x14004536d  mov     r9d, 1
0x140045373  mov     r8, rdi
0x140045376  mov     rdx, r15
0x140045379  mov     rcx, rsi
0x14004537c  call    FatFlushAndCleanVolume
0x140045381  mov     rax, [r15+0B8h]
0x140045388  movups  xmm0, xmmword ptr [rax]
0x14004538b  movups  xmmword ptr [rax-48h], xmm0
0x14004538f  movups  xmm1, xmmword ptr [rax+10h]
0x140045393  movups  xmmword ptr [rax-38h], xmm1
0x140045397  movups  xmm0, xmmword ptr [rax+20h]
0x14004539b  movups  xmmword ptr [rax-28h], xmm0
0x14004539f  movsd   xmm1, qword ptr [rax+30h]
0x1400453a4  movsd   qword ptr [rax-18h], xmm1
0x1400453a9  mov     [rax-45h], r14b
0x1400453ad  xor     r8d, r8d; State
0x1400453b0  xor     edx, edx; Type
0x1400453b2  lea     rcx, [rsp+88h+Event]; Event
0x1400453b7  call    cs:__imp_KeInitializeEvent
0x1400453be  nop     dword ptr [rax+rax+00h]
0x1400453c3  mov     rax, [r15+0B8h]
0x1400453ca  lea     rcx, FatCallSelfCompletionRoutine
0x1400453d1  mov     [rax-10h], rcx
0x1400453d5  lea     rcx, [rsp+88h+Event]
0x1400453da  mov     [rax-8], rcx
0x1400453de  mov     [rax-45h], r14b
0x1400453e2  mov     byte ptr [rax-45h], 40h ; '@'
0x1400453e6  mov     byte ptr [rax-45h], 0C0h
0x1400453ea  mov     byte ptr [rax-45h], 0E0h
0x1400453ee  mov     rdx, r15; Irp
0x1400453f1  mov     rcx, [rdi+88h]; DeviceObject
0x1400453f8  call    cs:__imp_IofCallDriver
0x1400453ff  nop     dword ptr [rax+rax+00h]
0x140045404  mov     ebx, eax
0x140045406  mov     [rsp+88h+var_54], eax
0x14004540a  cmp     eax, 103h
0x14004540f  jnz     short loc_14004543B
0x140045411  mov     [rsp+88h+Timeout], 0; Timeout
0x14004541a  xor     r9d, r9d; Alertable
0x14004541d  xor     r8d, r8d; WaitMode
0x140045420  xor     edx, edx; WaitReason
0x140045422  lea     rcx, [rsp+88h+Event]; Object
0x140045427  call    cs:__imp_KeWaitForSingleObject
0x14004542e  nop     dword ptr [rax+rax+00h]
0x140045433  mov     ebx, [r15+30h]
0x140045437  mov     [rsp+88h+var_54], ebx
0x14004543b  test    ebx, ebx
0x14004543d  js      short loc_140045454
0x14004543f  mov     r8b, 1
0x140045442  mov     rdx, rdi
0x140045445  mov     rcx, rsi
0x140045448  call    FatCheckForDismount
0x14004544d  mov     r14b, al
0x140045450  mov     [rsp+88h+var_58], al
0x140045454  test    r14b, r14b
0x140045457  jnz     short loc_140045468
0x140045459  mov     rcx, r12; Resource
0x14004545c  call    cs:__imp_ExReleaseResourceLite
0x140045463  nop     dword ptr [rax+rax+00h]
0x140045468  lea     rcx, Resource; Resource
0x14004546f  call    cs:__imp_ExReleaseResourceLite
0x140045476  nop     dword ptr [rax+rax+00h]
0x14004547b  mov     r8d, ebx
0x14004547e  mov     rdx, r15; Irp
0x140045481  mov     rcx, rsi; Entry
0x140045484  call    FatCompleteRequest_Real
0x140045489  mov     eax, ebx
0x14004548b  add     rsp, 58h
0x14004548f  pop     r15
0x140045491  pop     r14
0x140045493  pop     r12
0x140045495  pop     rdi
0x140045496  pop     rsi
0x140045497  pop     rbx
0x140045498  retn
0x14005f671  push    rbp
0x14005f673  sub     rsp, 30h
0x14005f677  mov     rbp, rdx
0x14005f67a  cmp     byte ptr [rbp+30h], 0
0x14005f67e  jnz     short loc_14005F69B
0x14005f680  mov     rcx, [rbp+0A0h]
0x14005f687  add     rcx, 208h; Resource
0x14005f68e  call    cs:__imp_ExReleaseResourceLite
0x14005f695  nop     dword ptr [rax+rax+00h]
0x14005f69a  nop
0x14005f69b  cmp     byte ptr [rbp+31h], 0
0x14005f69f  jz      short loc_14005F6B5
0x14005f6a1  lea     rcx, Resource; Resource
0x14005f6a8  call    cs:__imp_ExReleaseResourceLite
0x14005f6af  nop     dword ptr [rax+rax+00h]
0x14005f6b4  nop
0x14005f6b5  add     rsp, 30h
0x14005f6b9  pop     rbp
0x14005f6ba  retn
```
