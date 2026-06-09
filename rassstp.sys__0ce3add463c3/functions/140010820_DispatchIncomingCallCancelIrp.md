# DispatchIncomingCallCancelIrp

- ea: `0x140010820`
- end: `0x1400108f6`
- name: `DispatchIncomingCallCancelIrp`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002030`
- `0x140002bd8`
- `0x140010820`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010878`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010878`
- `ntoskrnl!IofCompleteRequest` at `0x1400108b2`
- `ntoskrnl!IofCompleteRequest` at `0x1400108b2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010864`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010864`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010892`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010892`

## pseudocode

```c
void __fastcall DispatchIncomingCallCancelIrp(__int64 a1, IRP *a2)
{
  struct _LIST_ENTRY *Flink; // rdi
  KIRQL v4; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&Flink[2]);
  Flink[3].Blink = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)&Flink[2], v4);
  DereferenceRefCount(Flink);
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
}

```

## disassembly

```asm
0x140010820  push    rbx
0x140010822  push    rsi
0x140010823  push    rdi
0x140010824  push    r14
0x140010826  sub     rsp, 28h
0x14001082a  mov     rsi, rdx
0x14001082d  mov     rcx, cs:WPP_GLOBAL_Control
0x140010834  lea     r14, WPP_GLOBAL_Control
0x14001083b  cmp     rcx, r14
0x14001083e  jz      short loc_140010861
0x140010840  mov     eax, [rcx+2Ch]
0x140010843  and     eax, 82h
0x140010848  cmp     al, 82h
0x14001084a  jnz     short loc_140010861
0x14001084c  mov     rcx, [rcx+18h]
0x140010850  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140010857  mov     edx, 1Fh
0x14001085c  call    WPP_SF_
0x140010861  mov     cl, [rsi+45h]; Irql
0x140010864  call    cs:__imp_IoReleaseCancelSpinLock
0x14001086b  nop     dword ptr [rax+rax+00h]
0x140010870  mov     rdi, [rsi+78h]
0x140010874  lea     rcx, [rdi+20h]; SpinLock
0x140010878  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001087f  nop     dword ptr [rax+rax+00h]
0x140010884  lea     rcx, [rdi+20h]; SpinLock
0x140010888  mov     qword ptr [rdi+38h], 0
0x140010890  mov     dl, al; NewIrql
0x140010892  call    cs:__imp_KeReleaseSpinLock
0x140010899  nop     dword ptr [rax+rax+00h]
0x14001089e  mov     rcx, rdi
0x1400108a1  call    DereferenceRefCount
0x1400108a6  mov     dl, 2; PriorityBoost
0x1400108a8  mov     dword ptr [rsi+30h], 0C0000120h
0x1400108af  mov     rcx, rsi; Irp
0x1400108b2  call    cs:__imp_IofCompleteRequest
0x1400108b9  nop     dword ptr [rax+rax+00h]
0x1400108be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400108c5  cmp     rcx, r14
0x1400108c8  jz      short loc_1400108EB
0x1400108ca  mov     eax, [rcx+2Ch]
0x1400108cd  and     eax, 82h
0x1400108d2  cmp     al, 82h
0x1400108d4  jnz     short loc_1400108EB
0x1400108d6  mov     rcx, [rcx+18h]
0x1400108da  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400108e1  mov     edx, 20h ; ' '
0x1400108e6  call    WPP_SF_
0x1400108eb  add     rsp, 28h
0x1400108ef  pop     r14
0x1400108f1  pop     rdi
0x1400108f2  pop     rsi
0x1400108f3  pop     rbx
0x1400108f4  retn
```
