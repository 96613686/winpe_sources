# NbtProcessTcpDirectQuery

- ea: `0x140024ed8`
- end: `0x14002506f`
- name: `NbtProcessTcpDirectQuery`
- size: `407`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140047f20`

## callees

- `0x140024ed8`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x140024f8f`
- `ntoskrnl!ObfReferenceObject` at `0x140024f8f`
- `ntoskrnl!IofCallDriver` at `0x140025029`
- `ntoskrnl!IofCallDriver` at `0x140025029`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140024fc6`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140025017`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140024fc6`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140025017`
- `ntoskrnl!IofCompleteRequest` at `0x140025053`
- `ntoskrnl!IofCompleteRequest` at `0x140025053`
- `ntoskrnl!ObfDereferenceObject` at `0x140025038`
- `ntoskrnl!ObfDereferenceObject` at `0x140025038`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140024f59`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140024f59`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140024ff2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140024ff2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140024f1e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140024f1e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024f44`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025008`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024f44`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025008`

## pseudocode

```c
__int64 __fastcall NbtProcessTcpDirectQuery(PIRP Irp, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rsi
  KIRQL v7; // al
  __int64 v8; // rcx
  KIRQL v9; // r15
  __int64 v10; // rsi
  struct _FILE_OBJECT *v11; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v13; // rbx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  struct _DEVICE_OBJECT *v15; // rax

  if ( Irp->RequestorMode )
  {
    v4 = -1073741790;
LABEL_9:
    Irp->IoStatus.Status = v4;
    IofCompleteRequest(Irp, 0);
    return v4;
  }
  v5 = *(_QWORD *)(a2 + 48);
  v6 = *(_QWORD *)(v5 + 24);
  if ( !v6 || *(_QWORD *)(v5 + 32) != 2 )
  {
    v4 = -1073741504;
    goto LABEL_9;
  }
  v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v8 = *(_QWORD *)(v6 + 24);
  v9 = v7;
  if ( !v8 )
  {
    v4 = -1073741504;
    KeReleaseSpinLock(&SpinLock, v7);
    goto LABEL_9;
  }
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 104));
  v10 = *(_QWORD *)(v6 + 24);
  v11 = *(struct _FILE_OBJECT **)(((~*(_DWORD *)(a2 + 8) & 0x10000000 | 0x60000000uLL) >> 25) + v10);
  *(_DWORD *)(a2 + 8) &= ~0x10000000u;
  ObfReferenceObject(v11);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = 0;
  CurrentStackLocation[-1].Context = 0;
  CurrentStackLocation[-1].Control = 0;
  v13 = Irp->Tail.Overlay.CurrentStackLocation;
  *(_WORD *)&v13[-1].MajorFunction = 3087;
  RelatedDeviceObject = IoGetRelatedDeviceObject(v11);
  v13[-1].FileObject = v11;
  v13[-1].DeviceObject = RelatedDeviceObject;
  v13[-1].Parameters.Read.Length = *(_DWORD *)(a2 + 8);
  v13[-1].Parameters.QueryDirectory.FileName = 0;
  v4 = 259;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v10 + 104));
  KeReleaseSpinLock(&SpinLock, v9);
  v15 = IoGetRelatedDeviceObject(v11);
  IofCallDriver(v15, Irp);
  ObfDereferenceObject(v11);
  return v4;
}

```

## disassembly

```asm
0x140024ed8  push    rbx
0x140024eda  push    rbp
0x140024edb  push    rsi
0x140024edc  push    rdi
0x140024edd  push    r14
0x140024edf  push    r15
0x140024ee1  sub     rsp, 28h
0x140024ee5  cmp     byte ptr [rcx+40h], 0
0x140024ee9  mov     r14, rdx
0x140024eec  mov     rbp, rcx
0x140024eef  jz      short loc_140024EFB
0x140024ef1  mov     ebx, 0C0000022h
0x140024ef6  jmp     loc_14002504B
0x140024efb  mov     rax, [rdx+30h]
0x140024eff  mov     rsi, [rax+18h]
0x140024f03  test    rsi, rsi
0x140024f06  jz      loc_140025046
0x140024f0c  cmp     qword ptr [rax+20h], 2
0x140024f11  jnz     loc_140025046
0x140024f17  lea     rcx, SpinLock; SpinLock
0x140024f1e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140024f25  nop     dword ptr [rax+rax+00h]
0x140024f2a  mov     rcx, [rsi+18h]
0x140024f2e  mov     r15b, al
0x140024f31  test    rcx, rcx
0x140024f34  jnz     short loc_140024F55
0x140024f36  mov     dl, al; NewIrql
0x140024f38  lea     rcx, SpinLock; SpinLock
0x140024f3f  mov     ebx, 0C0000140h
0x140024f44  call    cs:__imp_KeReleaseSpinLock
0x140024f4b  nop     dword ptr [rax+rax+00h]
0x140024f50  jmp     loc_14002504B
0x140024f55  add     rcx, 68h ; 'h'; SpinLock
0x140024f59  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140024f60  nop     dword ptr [rax+rax+00h]
0x140024f65  mov     ecx, [r14+8]
0x140024f69  mov     eax, ecx
0x140024f6b  mov     rsi, [rsi+18h]
0x140024f6f  not     eax
0x140024f71  and     eax, 10000000h
0x140024f76  btr     ecx, 1Ch
0x140024f7a  or      rax, 60000000h
0x140024f80  shr     rax, 19h
0x140024f84  mov     rdi, [rax+rsi]
0x140024f88  mov     [r14+8], ecx
0x140024f8c  mov     rcx, rdi; Object
0x140024f8f  call    cs:__imp_ObfReferenceObject
0x140024f96  nop     dword ptr [rax+rax+00h]
0x140024f9b  mov     rax, [rbp+0B8h]
0x140024fa2  mov     rcx, rdi; FileObject
0x140024fa5  mov     qword ptr [rax-10h], 0
0x140024fad  mov     qword ptr [rax-8], 0
0x140024fb5  mov     byte ptr [rax-45h], 0
0x140024fb9  mov     rbx, [rbp+0B8h]
0x140024fc0  mov     word ptr [rbx-48h], 0C0Fh
0x140024fc6  call    cs:__imp_IoGetRelatedDeviceObject
0x140024fcd  nop     dword ptr [rax+rax+00h]
0x140024fd2  mov     [rbx-18h], rdi
0x140024fd6  lea     rcx, [rsi+68h]; SpinLock
0x140024fda  mov     [rbx-20h], rax
0x140024fde  mov     eax, [r14+8]
0x140024fe2  mov     [rbx-40h], eax
0x140024fe5  mov     qword ptr [rbx-38h], 0
0x140024fed  mov     ebx, 103h
0x140024ff2  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140024ff9  nop     dword ptr [rax+rax+00h]
0x140024ffe  mov     dl, r15b; NewIrql
0x140025001  lea     rcx, SpinLock; SpinLock
0x140025008  call    cs:__imp_KeReleaseSpinLock
0x14002500f  nop     dword ptr [rax+rax+00h]
0x140025014  mov     rcx, rdi; FileObject
0x140025017  call    cs:__imp_IoGetRelatedDeviceObject
0x14002501e  nop     dword ptr [rax+rax+00h]
0x140025023  mov     rcx, rax; DeviceObject
0x140025026  mov     rdx, rbp; Irp
0x140025029  call    cs:__imp_IofCallDriver
0x140025030  nop     dword ptr [rax+rax+00h]
0x140025035  mov     rcx, rdi; Object
0x140025038  call    cs:__imp_ObfDereferenceObject
0x14002503f  nop     dword ptr [rax+rax+00h]
0x140025044  jmp     short loc_14002505F
0x140025046  mov     ebx, 0C0000140h
0x14002504b  xor     edx, edx; PriorityBoost
0x14002504d  mov     [rbp+30h], ebx
0x140025050  mov     rcx, rbp; Irp
0x140025053  call    cs:__imp_IofCompleteRequest
0x14002505a  nop     dword ptr [rax+rax+00h]
0x14002505f  mov     eax, ebx
0x140025061  add     rsp, 28h
0x140025065  pop     r15
0x140025067  pop     r14
0x140025069  pop     rdi
0x14002506a  pop     rsi
0x14002506b  pop     rbp
0x14002506c  pop     rbx
0x14002506d  retn
```
