# NbtWorkItemPostClientIrpToProvider

- ea: `0x140014610`
- end: `0x140014753`
- name: `NbtWorkItemPostClientIrpToProvider`
- size: `323`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140010988`
- `0x140013184`
- `0x140014610`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140014699`
- `ntoskrnl!IofCallDriver` at `0x140014699`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140014687`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140014687`
- `ntoskrnl!IoFreeWorkItem` at `0x140014625`
- `ntoskrnl!IoFreeWorkItem` at `0x140014625`
- `ntoskrnl!IofCompleteRequest` at `0x140014710`
- `ntoskrnl!IofCompleteRequest` at `0x140014710`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014638`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014638`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014678`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400146ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014678`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400146ef`

## pseudocode

```c
__int64 __fastcall NbtWorkItemPostClientIrpToProvider(__int64 a1, __int64 a2)
{
  KIRQL v3; // al
  bool v4; // zf
  IRP *v5; // r14
  void *v6; // rdi
  struct _FILE_OBJECT *v7; // rbx
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rax
  void *v10; // rbx
  int v11; // edx
  int v12; // r8d

  IoFreeWorkItem(*(PIO_WORKITEM *)(a2 + 224));
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 104));
  v4 = *(_QWORD *)(a2 + 24) == 0;
  v5 = *(IRP **)(a2 + 216);
  *(_QWORD *)(a2 + 224) = 0;
  if ( v4 || *(_DWORD *)(a2 + 88) != 7 )
  {
    v5->MdlAddress = *(PMDL *)(a2 + 288);
    v10 = *(void **)(a2 + 32);
    *(_QWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 288) = 0;
    *(_QWORD *)(a2 + 216) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 104), v3);
    v5->IoStatus.Status = -1073741299;
    v5->IoStatus.Information = 0;
    IofCompleteRequest(v5, 2);
    NbtDereferenceConnection(v10);
    return NbtDereferenceLowerConnection(a2, v11, v12, 504, (__int64)"minio\\netbt\\sys\\nt\\tdihndlr.c");
  }
  else
  {
    v6 = *(void **)(a2 + 32);
    v7 = *(struct _FILE_OBJECT **)(a2 + 48);
    *(_QWORD *)(a2 + 32) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 104), v3);
    RelatedDeviceObject = IoGetRelatedDeviceObject(v7);
    IofCallDriver(RelatedDeviceObject, v5);
    return NbtDereferenceConnection(v6);
  }
}

```

## disassembly

```asm
0x140014610  push    rbx
0x140014612  push    rbp
0x140014613  push    rsi
0x140014614  push    rdi
0x140014615  push    r14
0x140014617  sub     rsp, 30h
0x14001461b  mov     rcx, [rdx+0E0h]; IoWorkItem
0x140014622  mov     rsi, rdx
0x140014625  call    cs:__imp_IoFreeWorkItem
0x14001462c  nop     dword ptr [rax+rax+00h]
0x140014631  lea     rbp, [rsi+68h]
0x140014635  mov     rcx, rbp; SpinLock
0x140014638  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001463f  nop     dword ptr [rax+rax+00h]
0x140014644  cmp     qword ptr [rsi+18h], 0
0x140014649  mov     dl, al; NewIrql
0x14001464b  mov     r14, [rsi+0D8h]
0x140014652  mov     qword ptr [rsi+0E0h], 0
0x14001465d  jz      short loc_1400146BF
0x14001465f  cmp     dword ptr [rsi+58h], 7
0x140014663  jnz     short loc_1400146BF
0x140014665  mov     rdi, [rsi+20h]
0x140014669  mov     rcx, rbp; SpinLock
0x14001466c  mov     rbx, [rsi+30h]
0x140014670  mov     qword ptr [rsi+20h], 0
0x140014678  call    cs:__imp_KeReleaseSpinLock
0x14001467f  nop     dword ptr [rax+rax+00h]
0x140014684  mov     rcx, rbx; FileObject
0x140014687  call    cs:__imp_IoGetRelatedDeviceObject
0x14001468e  nop     dword ptr [rax+rax+00h]
0x140014693  mov     rcx, rax; DeviceObject
0x140014696  mov     rdx, r14; Irp
0x140014699  call    cs:__imp_IofCallDriver
0x1400146a0  nop     dword ptr [rax+rax+00h]
0x1400146a5  lea     r9, aMinioNetbtSysN_2; "minio\\netbt\\sys\\nt\\tdihndlr.c"
0x1400146ac  mov     r8d, 208h
0x1400146b2  mov     rcx, rdi; P
0x1400146b5  call    NbtDereferenceConnection
0x1400146ba  jmp     loc_140014747
0x1400146bf  mov     rax, [rsi+120h]
0x1400146c6  mov     rcx, rbp; SpinLock
0x1400146c9  mov     [r14+8], rax
0x1400146cd  mov     rbx, [rsi+20h]
0x1400146d1  mov     qword ptr [rsi+20h], 0
0x1400146d9  mov     qword ptr [rsi+120h], 0
0x1400146e4  mov     qword ptr [rsi+0D8h], 0
0x1400146ef  call    cs:__imp_KeReleaseSpinLock
0x1400146f6  nop     dword ptr [rax+rax+00h]
0x1400146fb  mov     dl, 2; PriorityBoost
0x1400146fd  mov     dword ptr [r14+30h], 0C000020Dh
0x140014705  mov     rcx, r14; Irp
0x140014708  mov     qword ptr [r14+38h], 0
0x140014710  call    cs:__imp_IofCompleteRequest
0x140014717  nop     dword ptr [rax+rax+00h]
0x14001471c  lea     rbp, aMinioNetbtSysN_2; "minio\\netbt\\sys\\nt\\tdihndlr.c"
0x140014723  mov     r8d, 1F7h
0x140014729  mov     r9, rbp
0x14001472c  mov     rcx, rbx; P
0x14001472f  call    NbtDereferenceConnection
0x140014734  mov     r9d, 1F8h
0x14001473a  mov     [rsp+58h+var_38], rbp
0x14001473f  mov     rcx, rsi
0x140014742  call    NbtDereferenceLowerConnection
0x140014747  add     rsp, 30h
0x14001474b  pop     r14
0x14001474d  pop     rdi
0x14001474e  pop     rsi
0x14001474f  pop     rbp
0x140014750  pop     rbx
0x140014751  retn
```
