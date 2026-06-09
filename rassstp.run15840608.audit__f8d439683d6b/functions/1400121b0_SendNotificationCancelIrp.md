# SendNotificationCancelIrp

- ea: `0x1400121b0`
- end: `0x140012286`
- name: `SendNotificationCancelIrp`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002030`
- `0x140002bd8`
- `0x1400121b0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012208`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012208`
- `ntoskrnl!IofCompleteRequest` at `0x140012242`
- `ntoskrnl!IofCompleteRequest` at `0x140012242`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400121f4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400121f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012222`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012222`

## pseudocode

```c
void __fastcall SendNotificationCancelIrp(__int64 a1, IRP *a2)
{
  struct _LIST_ENTRY *Flink; // rdi
  KIRQL v4; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&Flink[2]);
  Flink[5].Flink = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)&Flink[2], v4);
  DereferenceRefCount(Flink);
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
}

```

## disassembly

```asm
0x1400121b0  push    rbx
0x1400121b2  push    rsi
0x1400121b3  push    rdi
0x1400121b4  push    r14
0x1400121b6  sub     rsp, 28h
0x1400121ba  mov     rsi, rdx
0x1400121bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400121c4  lea     r14, WPP_GLOBAL_Control
0x1400121cb  cmp     rcx, r14
0x1400121ce  jz      short loc_1400121F1
0x1400121d0  mov     eax, [rcx+2Ch]
0x1400121d3  and     eax, 82h
0x1400121d8  cmp     al, 82h
0x1400121da  jnz     short loc_1400121F1
0x1400121dc  mov     rcx, [rcx+18h]
0x1400121e0  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400121e7  mov     edx, 32h ; '2'
0x1400121ec  call    WPP_SF_
0x1400121f1  mov     cl, [rsi+45h]; Irql
0x1400121f4  call    cs:__imp_IoReleaseCancelSpinLock
0x1400121fb  nop     dword ptr [rax+rax+00h]
0x140012200  mov     rdi, [rsi+78h]
0x140012204  lea     rcx, [rdi+20h]; SpinLock
0x140012208  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001220f  nop     dword ptr [rax+rax+00h]
0x140012214  lea     rcx, [rdi+20h]; SpinLock
0x140012218  mov     qword ptr [rdi+50h], 0
0x140012220  mov     dl, al; NewIrql
0x140012222  call    cs:__imp_KeReleaseSpinLock
0x140012229  nop     dword ptr [rax+rax+00h]
0x14001222e  mov     rcx, rdi
0x140012231  call    DereferenceRefCount
0x140012236  mov     dl, 2; PriorityBoost
0x140012238  mov     dword ptr [rsi+30h], 0C0000120h
0x14001223f  mov     rcx, rsi; Irp
0x140012242  call    cs:__imp_IofCompleteRequest
0x140012249  nop     dword ptr [rax+rax+00h]
0x14001224e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012255  cmp     rcx, r14
0x140012258  jz      short loc_14001227B
0x14001225a  mov     eax, [rcx+2Ch]
0x14001225d  and     eax, 82h
0x140012262  cmp     al, 82h
0x140012264  jnz     short loc_14001227B
0x140012266  mov     rcx, [rcx+18h]
0x14001226a  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140012271  mov     edx, 33h ; '3'
0x140012276  call    WPP_SF_
0x14001227b  add     rsp, 28h
0x14001227f  pop     r14
0x140012281  pop     rdi
0x140012282  pop     rsi
0x140012283  pop     rbx
0x140012284  retn
```
