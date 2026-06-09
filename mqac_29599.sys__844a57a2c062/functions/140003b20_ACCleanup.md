# ACCleanup

- ea: `0x140003b20`
- end: `0x140003d7c`
- name: `ACCleanup`
- size: `604`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1400010a4`
- `0x140001c04`
- `0x140003a48`
- `0x140003ad0`
- `0x140003b20`
- `0x140003d84`
- `0x14000f320`
- `0x140012754`
- `0x140024bf0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140003b6a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003b6a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140003b7a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140003b7a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140003d50`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140003d50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003d5c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003d5c`
- `ntoskrnl!IofCompleteRequest` at `0x140003d40`
- `ntoskrnl!IofCompleteRequest` at `0x140003d40`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140003c09`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140003c09`

## pseudocode

```c
__int64 __fastcall ACCleanup(struct _DEVICE_OBJECT *a1, PIRP Irp)
{
  char *DeviceExtension; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PFILE_OBJECT FileObject; // rbp
  CBaseObject *FsContext; // rdi
  QueueHandleDescriptor *FsContext2; // r14
  __int64 v9; // r15
  __int64 v10; // r8
  KIRQL Irql; // [rsp+70h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, &WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids);
  }
  DeviceExtension = (char *)a1->DeviceExtension;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  FsContext = (CBaseObject *)FileObject->FsContext;
  if ( FsContext )
  {
    (*(void (__fastcall **)(PVOID, PFILE_OBJECT, _QWORD))(*(_QWORD *)FsContext + 16LL))(
      FileObject->FsContext,
      CurrentStackLocation->FileObject,
      *((_DWORD *)FileObject->FsContext2 + 5) & 1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        11,
        &WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids,
        FsContext);
    }
  }
  FsContext2 = (QueueHandleDescriptor *)FileObject->FsContext2;
  if ( FsContext2 )
  {
    if ( !FsContext )
    {
      v9 = *(_QWORD *)FsContext2;
      if ( *(_QWORD *)FsContext2 )
      {
        Irql = 0;
        IoAcquireCancelSpinLock(&Irql);
        LOBYTE(v10) = Irql;
        ACCancelIrp(*((_QWORD *)DeviceExtension + 9), *(_QWORD *)(v9 + 16), v10, 3221225760LL);
      }
    }
    FileObject->FsContext2 = 0;
    QueueHandleDescriptor::~QueueHandleDescriptor(FsContext2);
    operator delete(FsContext2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 12, &WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids);
    }
  }
  if ( FsContext )
  {
    FileObject->FsContext = 0;
    CBaseObject::Release(FsContext);
  }
  if ( *((PFILE_OBJECT *)DeviceExtension + 11) != FileObject )
    goto LABEL_24;
  ACpDestroyHeap(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 13, &WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids);
  }
  *((_QWORD *)DeviceExtension + 10) = 0;
  *((_QWORD *)DeviceExtension + 11) = 0;
  *((_QWORD *)DeviceExtension + 118) = 0;
  *((_QWORD *)DeviceExtension + 119) = 0;
  *((_QWORD *)DeviceExtension + 120) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 14, &WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids);
LABEL_24:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 15, &WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids, Irp);
    }
  }
  Irp->IoStatus.Information = 0;
  Irp->IoStatus.Status = 0;
  IofCompleteRequest(Irp, 0);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x140003b20  push    rbx
0x140003b22  push    rbp
0x140003b23  push    rsi
0x140003b24  push    rdi
0x140003b25  push    r12
0x140003b27  push    r13
0x140003b29  push    r14
0x140003b2b  push    r15
0x140003b2d  sub     rsp, 28h
0x140003b31  mov     rsi, rdx
0x140003b34  mov     r13, rcx
0x140003b37  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b3e  lea     r14, WPP_GLOBAL_Control
0x140003b45  cmp     rcx, r14
0x140003b48  jz      short loc_140003B66
0x140003b4a  mov     eax, [rcx+6Ch]
0x140003b4d  test    al, 4
0x140003b4f  jz      short loc_140003B66
0x140003b51  mov     rcx, [rcx+58h]
0x140003b55  lea     r8, WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids
0x140003b5c  mov     edx, 0Ah
0x140003b61  call    WPP_SF_
0x140003b66  mov     rbx, [r13+40h]
0x140003b6a  call    cs:__imp_KeEnterCriticalRegion
0x140003b71  nop     dword ptr [rax+rax+00h]
0x140003b76  lea     rcx, [rbx+8]; FastMutex
0x140003b7a  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140003b81  nop     dword ptr [rax+rax+00h]
0x140003b86  mov     rax, [rsi+0B8h]
0x140003b8d  xor     r15d, r15d
0x140003b90  mov     rbp, [rax+30h]
0x140003b94  mov     rdi, [rbp+18h]
0x140003b98  test    rdi, rdi
0x140003b9b  jz      short loc_140003BE5
0x140003b9d  mov     rax, [rbp+20h]
0x140003ba1  mov     rdx, rbp
0x140003ba4  mov     rcx, [rdi]
0x140003ba7  mov     r8d, [rax+14h]
0x140003bab  mov     rax, [rcx+10h]
0x140003baf  and     r8d, 1
0x140003bb3  mov     rcx, rdi
0x140003bb6  call    _guard_dispatch_icall
0x140003bbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bc2  cmp     rcx, r14
0x140003bc5  jz      short loc_140003BE5
0x140003bc7  mov     eax, [rcx+6Ch]
0x140003bca  test    al, 4
0x140003bcc  jz      short loc_140003BE5
0x140003bce  mov     rcx, [rcx+58h]
0x140003bd2  lea     edx, [r15+0Bh]
0x140003bd6  mov     r9, rdi
0x140003bd9  lea     r8, WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids
0x140003be0  call    WPP_SF_q
0x140003be5  mov     r14, [rbp+20h]
0x140003be9  test    r14, r14
0x140003bec  jz      loc_140003C75
0x140003bf2  test    rdi, rdi
0x140003bf5  jnz     short loc_140003C30
0x140003bf7  mov     r15, [r14]
0x140003bfa  test    r15, r15
0x140003bfd  jz      short loc_140003C2D
0x140003bff  lea     rcx, [rsp+68h+Irql]; Irql
0x140003c04  mov     [rsp+68h+Irql], dil
0x140003c09  call    cs:__imp_IoAcquireCancelSpinLock
0x140003c10  nop     dword ptr [rax+rax+00h]
0x140003c15  mov     r8b, [rsp+68h+Irql]
0x140003c1a  mov     r9d, 0C0000120h
0x140003c20  mov     rdx, [r15+10h]
0x140003c24  mov     rcx, [rbx+48h]
0x140003c28  call    ACCancelIrp
0x140003c2d  xor     r15d, r15d
0x140003c30  mov     rcx, r14; this
0x140003c33  mov     [rbp+20h], r15
0x140003c37  call    ??1QueueHandleDescriptor@@QEAA@XZ; QueueHandleDescriptor::~QueueHandleDescriptor(void)
0x140003c3c  mov     rcx, r14; void *
0x140003c3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003c44  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c4b  lea     r14, WPP_GLOBAL_Control
0x140003c52  cmp     rcx, r14
0x140003c55  jz      short loc_140003C7C
0x140003c57  mov     eax, [rcx+6Ch]
0x140003c5a  test    al, 4
0x140003c5c  jz      short loc_140003C7C
0x140003c5e  mov     rcx, [rcx+58h]
0x140003c62  lea     r8, WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids
0x140003c69  mov     edx, 0Ch
0x140003c6e  call    WPP_SF_
0x140003c73  jmp     short loc_140003C7C
0x140003c75  lea     r14, WPP_GLOBAL_Control
0x140003c7c  test    rdi, rdi
0x140003c7f  jz      short loc_140003C8D
0x140003c81  mov     rcx, rdi; this
0x140003c84  mov     [rbp+18h], r15
0x140003c88  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140003c8d  cmp     [rbx+58h], rbp
0x140003c91  jnz     short loc_140003D08
0x140003c93  mov     rcx, r13; struct _DEVICE_OBJECT *
0x140003c96  call    ?ACpDestroyHeap@@YAXPEAU_DEVICE_OBJECT@@@Z; ACpDestroyHeap(_DEVICE_OBJECT *)
0x140003c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ca2  cmp     rcx, r14
0x140003ca5  jz      short loc_140003CC3
0x140003ca7  mov     eax, [rcx+6Ch]
0x140003caa  test    al, 4
0x140003cac  jz      short loc_140003CC3
0x140003cae  mov     rcx, [rcx+58h]
0x140003cb2  lea     r8, WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids
0x140003cb9  mov     edx, 0Dh
0x140003cbe  call    WPP_SF_
0x140003cc3  mov     [rbx+50h], r15
0x140003cc7  mov     [rbx+58h], r15
0x140003ccb  mov     [rbx+3B0h], r15
0x140003cd2  mov     [rbx+3B8h], r15
0x140003cd9  mov     [rbx+3C0h], r15
0x140003ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ce7  cmp     rcx, r14
0x140003cea  jz      short loc_140003D33
0x140003cec  mov     eax, [rcx+6Ch]
0x140003cef  test    al, 4
0x140003cf1  jz      short loc_140003D08
0x140003cf3  mov     rcx, [rcx+58h]
0x140003cf7  lea     r8, WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids
0x140003cfe  mov     edx, 0Eh
0x140003d03  call    WPP_SF_
0x140003d08  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d0f  cmp     rcx, r14
0x140003d12  jz      short loc_140003D33
0x140003d14  mov     eax, [rcx+6Ch]
0x140003d17  test    al, 4
0x140003d19  jz      short loc_140003D33
0x140003d1b  mov     rcx, [rcx+58h]
0x140003d1f  lea     r8, WPP_1488e3d4c3f737afff5c17d483dc3dbd_Traceguids
0x140003d26  mov     edx, 0Fh
0x140003d2b  mov     r9, rsi
0x140003d2e  call    WPP_SF_q
0x140003d33  xor     edx, edx; PriorityBoost
0x140003d35  mov     [rsi+38h], r15
0x140003d39  mov     rcx, rsi; Irp
0x140003d3c  mov     [rsi+30h], r15d
0x140003d40  call    cs:__imp_IofCompleteRequest
0x140003d47  nop     dword ptr [rax+rax+00h]
0x140003d4c  lea     rcx, [rbx+8]; FastMutex
0x140003d50  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140003d57  nop     dword ptr [rax+rax+00h]
0x140003d5c  call    cs:__imp_KeLeaveCriticalRegion
0x140003d63  nop     dword ptr [rax+rax+00h]
0x140003d68  xor     eax, eax
0x140003d6a  add     rsp, 28h
0x140003d6e  pop     r15
0x140003d70  pop     r14
0x140003d72  pop     r13
0x140003d74  pop     r12
0x140003d76  pop     rdi
0x140003d77  pop     rsi
0x140003d78  pop     rbp
0x140003d79  pop     rbx
0x140003d7a  retn
```
