# ACCancelRemoteQueueOperation

- ea: `0x14001b640`
- end: `0x14001b6eb`
- name: `ACCancelRemoteQueueOperation`
- size: `171`
- prototype: `void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003d84`
- `0x14001b640`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001b686`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001b686`
- `ntoskrnl!IofCompleteRequest` at `0x14001b6d1`
- `ntoskrnl!IofCompleteRequest` at `0x14001b6d1`

## pseudocode

```c
void __fastcall ACCancelRemoteQueueOperation(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rax
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *Blink; // rdx

  if ( !a1 )
    __int2c();
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
  p_ListEntry->ListEntry.Flink = 0;
  p_ListEntry->ListEntry.Blink = 0;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 11, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids, a2);
  }
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x14001b640  push    rbx
0x14001b642  sub     rsp, 20h
0x14001b646  mov     rbx, rdx
0x14001b649  test    rcx, rcx
0x14001b64c  jnz     short loc_14001B650
0x14001b64e  int     2Ch; Windows NT - assertion failure
0x14001b650  lea     rax, [rdx+0A8h]
0x14001b657  mov     rcx, [rax]
0x14001b65a  cmp     [rcx+8], rax
0x14001b65e  jnz     loc_14001B6E4
0x14001b664  mov     rdx, [rax+8]
0x14001b668  cmp     [rdx], rax
0x14001b66b  jnz     short loc_14001B6E4
0x14001b66d  mov     [rdx], rcx
0x14001b670  mov     [rcx+8], rdx
0x14001b674  mov     qword ptr [rax], 0
0x14001b67b  mov     qword ptr [rax+8], 0
0x14001b683  mov     cl, [rbx+45h]; Irql
0x14001b686  call    cs:__imp_IoReleaseCancelSpinLock
0x14001b68d  nop     dword ptr [rax+rax+00h]
0x14001b692  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b699  lea     rax, WPP_GLOBAL_Control
0x14001b6a0  cmp     rcx, rax
0x14001b6a3  jz      short loc_14001B6C4
0x14001b6a5  mov     eax, [rcx+6Ch]
0x14001b6a8  test    al, 4
0x14001b6aa  jz      short loc_14001B6C4
0x14001b6ac  mov     rcx, [rcx+58h]
0x14001b6b0  lea     r8, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids
0x14001b6b7  mov     edx, 0Bh
0x14001b6bc  mov     r9, rbx
0x14001b6bf  call    WPP_SF_q
0x14001b6c4  xor     edx, edx; PriorityBoost
0x14001b6c6  mov     qword ptr [rbx+38h], 0
0x14001b6ce  mov     rcx, rbx; Irp
0x14001b6d1  call    cs:__imp_IofCompleteRequest
0x14001b6d8  nop     dword ptr [rax+rax+00h]
0x14001b6dd  add     rsp, 20h
0x14001b6e1  pop     rbx
0x14001b6e2  retn
0x14001b6e4  mov     ecx, 3
0x14001b6e9  int     29h; Win8: RtlFailFast(ecx)
```
