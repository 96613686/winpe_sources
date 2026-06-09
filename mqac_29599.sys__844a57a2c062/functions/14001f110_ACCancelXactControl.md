# ACCancelXactControl

- ea: `0x14001f110`
- end: `0x14001f1bb`
- name: `ACCancelXactControl`
- size: `171`
- prototype: `void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003d84`
- `0x14001f110`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001f156`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001f156`
- `ntoskrnl!IofCompleteRequest` at `0x14001f1a1`
- `ntoskrnl!IofCompleteRequest` at `0x14001f1a1`

## pseudocode

```c
void __fastcall ACCancelXactControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
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
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, &WPP_2411d249fb60352b0c479e189fc20775_Traceguids, a2);
  }
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x14001f110  push    rbx
0x14001f112  sub     rsp, 20h
0x14001f116  mov     rbx, rdx
0x14001f119  test    rcx, rcx
0x14001f11c  jnz     short loc_14001F120
0x14001f11e  int     2Ch; Windows NT - assertion failure
0x14001f120  lea     rax, [rdx+0A8h]
0x14001f127  mov     rcx, [rax]
0x14001f12a  cmp     [rcx+8], rax
0x14001f12e  jnz     loc_14001F1B4
0x14001f134  mov     rdx, [rax+8]
0x14001f138  cmp     [rdx], rax
0x14001f13b  jnz     short loc_14001F1B4
0x14001f13d  mov     [rdx], rcx
0x14001f140  mov     [rcx+8], rdx
0x14001f144  mov     qword ptr [rax], 0
0x14001f14b  mov     qword ptr [rax+8], 0
0x14001f153  mov     cl, [rbx+45h]; Irql
0x14001f156  call    cs:__imp_IoReleaseCancelSpinLock
0x14001f15d  nop     dword ptr [rax+rax+00h]
0x14001f162  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f169  lea     rax, WPP_GLOBAL_Control
0x14001f170  cmp     rcx, rax
0x14001f173  jz      short loc_14001F194
0x14001f175  mov     eax, [rcx+6Ch]
0x14001f178  test    al, 4
0x14001f17a  jz      short loc_14001F194
0x14001f17c  mov     rcx, [rcx+58h]
0x14001f180  lea     r8, WPP_2411d249fb60352b0c479e189fc20775_Traceguids
0x14001f187  mov     edx, 0Ah
0x14001f18c  mov     r9, rbx
0x14001f18f  call    WPP_SF_q
0x14001f194  xor     edx, edx; PriorityBoost
0x14001f196  mov     qword ptr [rbx+38h], 0
0x14001f19e  mov     rcx, rbx; Irp
0x14001f1a1  call    cs:__imp_IofCompleteRequest
0x14001f1a8  nop     dword ptr [rax+rax+00h]
0x14001f1ad  add     rsp, 20h
0x14001f1b1  pop     rbx
0x14001f1b2  retn
0x14001f1b4  mov     ecx, 3
0x14001f1b9  int     29h; Win8: RtlFailFast(ecx)
```
