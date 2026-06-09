# ACCancelCreatePacketNotification(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140011e00`
- end: `0x140011f1d`
- name: `?ACCancelCreatePacketNotification@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `285`
- prototype: `void __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001c04`
- `0x140003d84`
- `0x140009adc`
- `0x140011e00`
- `0x14001206c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011e50`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011e50`
- `ntoskrnl!IofCompleteRequest` at `0x140011ef8`
- `ntoskrnl!IofCompleteRequest` at `0x140011ef8`

## pseudocode

```c
void __fastcall ACCancelCreatePacketNotification(struct _DEVICE_OBJECT *a1, PIRP Irp)
{
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rax
  struct _LIST_ENTRY *Flink; // r8
  struct _LIST_ENTRY *Blink; // rdx
  struct CPacket *v7; // rax

  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&Irp->Tail.Overlay.ListEntry;
  Flink = Irp->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)Flink->Blink != &Irp->Tail.CompletionKey + 6
    || (Blink = Irp->Tail.Overlay.ListEntry.Blink,
        (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink != p_ListEntry) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  p_ListEntry->ListEntry.Flink = 0;
  p_ListEntry->ListEntry.Blink = 0;
  IoReleaseCancelSpinLock(Irp->CancelIrql);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 14, &WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids, Irp);
  }
  v7 = CPacketHandleToCPacket(
         a1,
         (struct CPacket *)Irp->Tail.Overlay.CurrentStackLocation->Parameters.CreatePipe.Parameters);
  if ( v7 )
  {
    ACpCompleteCreatePacket(a1, v7, 3221225760LL, 0);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 15, &WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids);
  }
  Irp->IoStatus.Information = 0;
  Irp->IoStatus.Status = -1073741536;
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x140011e00  mov     [rsp+arg_0], rbx
0x140011e05  mov     [rsp+arg_8], rdi
0x140011e0a  push    r14
0x140011e0c  sub     rsp, 20h
0x140011e10  lea     rax, [rdx+0A8h]
0x140011e17  mov     rbx, rdx
0x140011e1a  mov     r8, [rax]
0x140011e1d  mov     rdi, rcx
0x140011e20  cmp     [r8+8], rax
0x140011e24  jnz     loc_140011F16
0x140011e2a  mov     rdx, [rax+8]
0x140011e2e  cmp     [rdx], rax
0x140011e31  jnz     loc_140011F16
0x140011e37  mov     [rdx], r8
0x140011e3a  mov     [r8+8], rdx
0x140011e3e  mov     qword ptr [rax], 0
0x140011e45  mov     qword ptr [rax+8], 0
0x140011e4d  mov     cl, [rbx+45h]; Irql
0x140011e50  call    cs:__imp_IoReleaseCancelSpinLock
0x140011e57  nop     dword ptr [rax+rax+00h]
0x140011e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e63  lea     r14, WPP_GLOBAL_Control
0x140011e6a  cmp     rcx, r14
0x140011e6d  jz      short loc_140011E8E
0x140011e6f  mov     eax, [rcx+6Ch]
0x140011e72  test    al, 4
0x140011e74  jz      short loc_140011E8E
0x140011e76  mov     rcx, [rcx+58h]
0x140011e7a  lea     r8, WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids
0x140011e81  mov     edx, 0Eh
0x140011e86  mov     r9, rbx
0x140011e89  call    WPP_SF_q
0x140011e8e  mov     rdx, [rbx+0B8h]
0x140011e95  mov     rcx, rdi; struct _DEVICE_OBJECT *
0x140011e98  mov     rdx, [rdx+20h]; struct CPacket *
0x140011e9c  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAU_DEVICE_OBJECT@@PEAV1@@Z; CPacketHandleToCPacket(_DEVICE_OBJECT *,CPacket *)
0x140011ea1  test    rax, rax
0x140011ea4  jz      short loc_140011EBC
0x140011ea6  xor     r9d, r9d
0x140011ea9  mov     r8d, 0C0000120h
0x140011eaf  mov     rdx, rax
0x140011eb2  mov     rcx, rdi
0x140011eb5  call    ACpCompleteCreatePacket
0x140011eba  jmp     short loc_140011EE4
0x140011ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ec3  cmp     rcx, r14
0x140011ec6  jz      short loc_140011EE4
0x140011ec8  mov     eax, [rcx+6Ch]
0x140011ecb  test    al, 1
0x140011ecd  jz      short loc_140011EE4
0x140011ecf  mov     rcx, [rcx+58h]
0x140011ed3  lea     r8, WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids
0x140011eda  mov     edx, 0Fh
0x140011edf  call    WPP_SF_
0x140011ee4  xor     edx, edx; PriorityBoost
0x140011ee6  mov     qword ptr [rbx+38h], 0
0x140011eee  mov     rcx, rbx; Irp
0x140011ef1  mov     dword ptr [rbx+30h], 0C0000120h
0x140011ef8  call    cs:__imp_IofCompleteRequest
0x140011eff  nop     dword ptr [rax+rax+00h]
0x140011f04  mov     rbx, [rsp+28h+arg_0]
0x140011f09  mov     rdi, [rsp+28h+arg_8]
0x140011f0e  add     rsp, 20h
0x140011f12  pop     r14
0x140011f14  retn
0x140011f16  mov     ecx, 3
0x140011f1b  int     29h; Win8: RtlFailFast(ecx)
```
