# ACCancelServiceRequest

- ea: `0x14001a840`
- end: `0x14001a8f2`
- name: `ACCancelServiceRequest`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001ad2c`

## callees

- `0x140003d84`
- `0x14001a840`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001a886`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001a886`
- `ntoskrnl!IofCompleteRequest` at `0x14001a8d8`
- `ntoskrnl!IofCompleteRequest` at `0x14001a8d8`

## pseudocode

```c
void __fastcall ACCancelServiceRequest(__int64 a1, IRP *a2)
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
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids, a2);
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x14001a840  push    rbx
0x14001a842  sub     rsp, 20h
0x14001a846  mov     rbx, rdx
0x14001a849  test    rcx, rcx
0x14001a84c  jnz     short loc_14001A850
0x14001a84e  int     2Ch; Windows NT - assertion failure
0x14001a850  lea     rax, [rdx+0A8h]
0x14001a857  mov     rcx, [rax]
0x14001a85a  cmp     [rcx+8], rax
0x14001a85e  jnz     loc_14001A8EB
0x14001a864  mov     rdx, [rax+8]
0x14001a868  cmp     [rdx], rax
0x14001a86b  jnz     short loc_14001A8EB
0x14001a86d  mov     [rdx], rcx
0x14001a870  mov     [rcx+8], rdx
0x14001a874  mov     qword ptr [rax], 0
0x14001a87b  mov     qword ptr [rax+8], 0
0x14001a883  mov     cl, [rbx+45h]; Irql
0x14001a886  call    cs:__imp_IoReleaseCancelSpinLock
0x14001a88d  nop     dword ptr [rax+rax+00h]
0x14001a892  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a899  lea     rax, WPP_GLOBAL_Control
0x14001a8a0  cmp     rcx, rax
0x14001a8a3  jz      short loc_14001A8C4
0x14001a8a5  mov     eax, [rcx+6Ch]
0x14001a8a8  test    al, 4
0x14001a8aa  jz      short loc_14001A8C4
0x14001a8ac  mov     rcx, [rcx+58h]
0x14001a8b0  lea     r8, WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids
0x14001a8b7  mov     edx, 0Ah
0x14001a8bc  mov     r9, rbx
0x14001a8bf  call    WPP_SF_q
0x14001a8c4  xor     edx, edx; PriorityBoost
0x14001a8c6  mov     qword ptr [rbx+38h], 0
0x14001a8ce  mov     rcx, rbx; Irp
0x14001a8d1  mov     dword ptr [rbx+30h], 0C0000120h
0x14001a8d8  call    cs:__imp_IofCompleteRequest
0x14001a8df  nop     dword ptr [rax+rax+00h]
0x14001a8e4  add     rsp, 20h
0x14001a8e8  pop     rbx
0x14001a8e9  retn
0x14001a8eb  mov     ecx, 3
0x14001a8f0  int     29h; Win8: RtlFailFast(ecx)
```
