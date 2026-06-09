# NatpNotificationCancelRoutine

- ea: `0x140011510`
- end: `0x14001161e`
- name: `NatpNotificationCancelRoutine`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000218c`
- `0x140011510`
- `0x140011624`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011555`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011555`
- `ntoskrnl!IofCompleteRequest` at `0x1400115cc`
- `ntoskrnl!IofCompleteRequest` at `0x1400115cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400115ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400115ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011568`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011568`

## pseudocode

```c
__int64 __fastcall NatpNotificationCancelRoutine(__int64 a1, IRP *a2)
{
  KIRQL v3; // al
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rdx
  struct _LIST_ENTRY *Flink; // r9
  struct _LIST_ENTRY *Blink; // r8
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
  }
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v3 = KeAcquireSpinLockRaiseToDpc(&NotificationLock);
  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink,
        (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink != p_ListEntry) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  a2->Tail.Overlay.ListEntry.Blink = &a2->Tail.Overlay.ListEntry;
  p_ListEntry->ListEntry.Flink = &p_ListEntry->ListEntry;
  KeReleaseSpinLock(&NotificationLock, v3);
  a2->IoStatus.Status = -1073741536;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  result = ReleaseComponentReference();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140011510  mov     [rsp+arg_0], rbx
0x140011515  push    rdi
0x140011516  sub     rsp, 20h
0x14001151a  mov     rbx, rdx
0x14001151d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011524  lea     rdi, WPP_GLOBAL_Control
0x14001152b  cmp     rcx, rdi
0x14001152e  jz      short loc_140011552
0x140011530  mov     eax, [rcx+2Ch]
0x140011533  test    al, 1
0x140011535  jz      short loc_140011552
0x140011537  cmp     byte ptr [rcx+29h], 6
0x14001153b  jb      short loc_140011552
0x14001153d  mov     rcx, [rcx+18h]
0x140011541  lea     r8, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids
0x140011548  mov     edx, 11h
0x14001154d  call    WPP_SF_
0x140011552  mov     cl, [rbx+45h]; Irql
0x140011555  call    cs:__imp_IoReleaseCancelSpinLock
0x14001155c  nop     dword ptr [rax+rax+00h]
0x140011561  lea     rcx, NotificationLock; SpinLock
0x140011568  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001156f  nop     dword ptr [rax+rax+00h]
0x140011574  lea     rdx, [rbx+0A8h]
0x14001157b  mov     r9, [rdx]
0x14001157e  cmp     [r9+8], rdx
0x140011582  jnz     loc_140011617
0x140011588  mov     r8, [rdx+8]
0x14001158c  cmp     [r8], rdx
0x14001158f  jnz     loc_140011617
0x140011595  mov     [r8], r9
0x140011598  lea     rcx, NotificationLock; SpinLock
0x14001159f  mov     [r9+8], r8
0x1400115a3  mov     [rdx+8], rdx
0x1400115a7  mov     [rdx], rdx
0x1400115aa  mov     dl, al; NewIrql
0x1400115ac  call    cs:__imp_KeReleaseSpinLock
0x1400115b3  nop     dword ptr [rax+rax+00h]
0x1400115b8  xor     edx, edx; PriorityBoost
0x1400115ba  mov     dword ptr [rbx+30h], 0C0000120h
0x1400115c1  mov     rcx, rbx; Irp
0x1400115c4  mov     qword ptr [rbx+38h], 0
0x1400115cc  call    cs:__imp_IofCompleteRequest
0x1400115d3  nop     dword ptr [rax+rax+00h]
0x1400115d8  call    ReleaseComponentReference
0x1400115dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400115e4  cmp     rcx, rdi
0x1400115e7  jz      short loc_14001160B
0x1400115e9  mov     eax, [rcx+2Ch]
0x1400115ec  test    al, 1
0x1400115ee  jz      short loc_14001160B
0x1400115f0  cmp     byte ptr [rcx+29h], 6
0x1400115f4  jb      short loc_14001160B
0x1400115f6  mov     rcx, [rcx+18h]
0x1400115fa  lea     r8, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids
0x140011601  mov     edx, 12h
0x140011606  call    WPP_SF_
0x14001160b  mov     rbx, [rsp+28h+arg_0]
0x140011610  add     rsp, 20h
0x140011614  pop     rdi
0x140011615  retn
0x140011617  mov     ecx, 3
0x14001161c  int     29h; Win8: RtlFailFast(ecx)
```
