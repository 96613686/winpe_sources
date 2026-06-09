# ACCancelRemoteReader

- ea: `0x14001b700`
- end: `0x14001b864`
- name: `ACCancelRemoteReader`
- size: `356`
- prototype: `void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001b700`
- `0x14001bc6c`
- `0x14001c468`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001b74b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001b74b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b7eb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b7eb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001b7fb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001b7fb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001b820`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001b820`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b82c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b82c`
- `ntoskrnl!IofCompleteRequest` at `0x14001b845`
- `ntoskrnl!IofCompleteRequest` at `0x14001b845`

## pseudocode

```c
void __fastcall ACCancelRemoteReader(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rax
  struct _LIST_ENTRY *Flink; // r8
  struct _LIST_ENTRY *Blink; // rdx
  char *DeviceExtension; // rbx
  const char *v7; // r9
  int v8; // r8d
  unsigned int v9; // ecx

  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink,
        (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink != p_ListEntry) )
  {
    __fastfail(3u);
  }
  DeviceExtension = (char *)a1->DeviceExtension;
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  p_ListEntry->ListEntry.Flink = 0;
  p_ListEntry->ListEntry.Blink = 0;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    v7 = "Done";
    if ( (*(_DWORD *)(&a2->Tail.CompletionKey + 3) & 0x40) == 0 )
      v7 = "Cancel";
    v8 = (unsigned __int16)(*((_DWORD *)&a2->Tail.CompletionKey + 6) >> 8);
    WPP_SF_sqqdD(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      *((_DWORD *)&a2->Tail.CompletionKey + 6) >> 6,
      v8,
      (_DWORD)v7,
      (char)a2,
      (char)a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink,
      v8,
      a2->IoStatus.Status);
  }
  v9 = *((_DWORD *)&a2->Tail.CompletionKey + 6);
  if ( (v9 & 0x40) == 0 )
  {
    if ( (v9 & 0x10) != 0 )
    {
      CProxy::IssueCancelRemoteRead(
        (CProxy *)a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink,
        (unsigned __int16)(v9 >> 8));
      *((_DWORD *)&a2->Tail.CompletionKey + 6) &= ~0x10u;
    }
    else
    {
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
      CProxy::IssueCancelRemoteRead(
        (CProxy *)a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink,
        (unsigned __int16)(*((_DWORD *)&a2->Tail.CompletionKey + 6) >> 8));
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
      KeLeaveCriticalRegion();
    }
  }
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x14001b700  mov     [rsp+arg_0], rbx
0x14001b705  push    rdi
0x14001b706  sub     rsp, 40h
0x14001b70a  lea     rax, [rdx+0A8h]
0x14001b711  mov     rdi, rdx
0x14001b714  mov     r8, [rax]
0x14001b717  cmp     [r8+8], rax
0x14001b71b  jnz     loc_14001B85D
0x14001b721  mov     rdx, [rax+8]
0x14001b725  cmp     [rdx], rax
0x14001b728  jnz     loc_14001B85D
0x14001b72e  mov     rbx, [rcx+40h]
0x14001b732  mov     [rdx], r8
0x14001b735  mov     [r8+8], rdx
0x14001b739  mov     qword ptr [rax], 0
0x14001b740  mov     qword ptr [rax+8], 0
0x14001b748  mov     cl, [rdi+45h]; Irql
0x14001b74b  call    cs:__imp_IoReleaseCancelSpinLock
0x14001b752  nop     dword ptr [rax+rax+00h]
0x14001b757  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b75e  lea     rax, WPP_GLOBAL_Control
0x14001b765  cmp     rcx, rax
0x14001b768  jz      short loc_14001B7BB
0x14001b76a  mov     eax, [rcx+6Ch]
0x14001b76d  test    al, 4
0x14001b76f  jz      short loc_14001B7BB
0x14001b771  mov     edx, [rdi+90h]
0x14001b777  lea     r9, aDone; "Done"
0x14001b77e  mov     rcx, [rcx+58h]
0x14001b782  mov     eax, edx
0x14001b784  shr     eax, 8
0x14001b787  movzx   r8d, ax
0x14001b78b  lea     rax, aCancel; "Cancel"
0x14001b792  shr     edx, 6
0x14001b795  test    dl, 1
0x14001b798  cmovz   r9, rax
0x14001b79c  mov     eax, [rdi+30h]
0x14001b79f  mov     [rsp+48h+var_10], eax
0x14001b7a3  mov     rax, [rdi+78h]
0x14001b7a7  mov     [rsp+48h+var_18], r8d
0x14001b7ac  mov     [rsp+48h+var_20], rax
0x14001b7b1  mov     [rsp+48h+var_28], rdi
0x14001b7b6  call    WPP_SF_sqqdD
0x14001b7bb  mov     ecx, [rdi+90h]
0x14001b7c1  mov     eax, ecx
0x14001b7c3  shr     eax, 6
0x14001b7c6  test    al, 1
0x14001b7c8  jnz     short loc_14001B838
0x14001b7ca  mov     eax, ecx
0x14001b7cc  shr     eax, 4
0x14001b7cf  test    al, 1
0x14001b7d1  jz      short loc_14001B7EB
0x14001b7d3  shr     ecx, 8
0x14001b7d6  movzx   edx, cx; unsigned int
0x14001b7d9  mov     rcx, [rdi+78h]; this
0x14001b7dd  call    ?IssueCancelRemoteRead@CProxy@@AEBAJK@Z; CProxy::IssueCancelRemoteRead(ulong)
0x14001b7e2  and     dword ptr [rdi+90h], 0FFFFFFEFh
0x14001b7e9  jmp     short loc_14001B838
0x14001b7eb  call    cs:__imp_KeEnterCriticalRegion
0x14001b7f2  nop     dword ptr [rax+rax+00h]
0x14001b7f7  lea     rcx, [rbx+8]; FastMutex
0x14001b7fb  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001b802  nop     dword ptr [rax+rax+00h]
0x14001b807  mov     eax, [rdi+90h]
0x14001b80d  mov     rcx, [rdi+78h]; this
0x14001b811  shr     eax, 8
0x14001b814  movzx   edx, ax; unsigned int
0x14001b817  call    ?IssueCancelRemoteRead@CProxy@@AEBAJK@Z; CProxy::IssueCancelRemoteRead(ulong)
0x14001b81c  lea     rcx, [rbx+8]; FastMutex
0x14001b820  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001b827  nop     dword ptr [rax+rax+00h]
0x14001b82c  call    cs:__imp_KeLeaveCriticalRegion
0x14001b833  nop     dword ptr [rax+rax+00h]
0x14001b838  xor     edx, edx; PriorityBoost
0x14001b83a  mov     qword ptr [rdi+38h], 0
0x14001b842  mov     rcx, rdi; Irp
0x14001b845  call    cs:__imp_IofCompleteRequest
0x14001b84c  nop     dword ptr [rax+rax+00h]
0x14001b851  mov     rbx, [rsp+48h+arg_0]
0x14001b856  add     rsp, 40h
0x14001b85a  pop     rdi
0x14001b85b  retn
0x14001b85d  mov     ecx, 3
0x14001b862  int     29h; Win8: RtlFailFast(ecx)
```
