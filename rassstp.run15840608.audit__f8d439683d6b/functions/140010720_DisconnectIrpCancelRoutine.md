# DisconnectIrpCancelRoutine

- ea: `0x140010720`
- end: `0x140010818`
- name: `DisconnectIrpCancelRoutine`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400018b0`
- `0x140002030`
- `0x140002bd8`
- `0x140010720`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010778`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010778`
- `ntoskrnl!IofCompleteRequest` at `0x1400107cc`
- `ntoskrnl!IofCompleteRequest` at `0x1400107cc`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010764`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010764`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400107b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400107b4`

## pseudocode

```c
__int64 __fastcall DisconnectIrpCancelRoutine(__int64 a1, IRP *a2)
{
  __int64 Flink; // rbx
  KIRQL v4; // al
  __int64 v5; // r8
  bool v6; // zf
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  Flink = (__int64)a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(Flink + 32));
  *(_DWORD *)(Flink + 21088) &= ~0x20u;
  v6 = *(_BYTE *)(Flink + 21092) == 0;
  *(_QWORD *)(Flink + 72) = 0;
  if ( v6 )
  {
    LOBYTE(v5) = v4;
    InitiateSstpContextCleanup(Flink, 2, v5);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(Flink + 32), v4);
  }
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 2);
  result = DereferenceRefCount(Flink);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer) & 0x82;
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140010720  push    rbx
0x140010722  push    rsi
0x140010723  push    rdi
0x140010724  push    r14
0x140010726  sub     rsp, 28h
0x14001072a  mov     rdi, rdx
0x14001072d  mov     rcx, cs:WPP_GLOBAL_Control
0x140010734  lea     r14, WPP_GLOBAL_Control
0x14001073b  cmp     rcx, r14
0x14001073e  jz      short loc_140010761
0x140010740  mov     eax, [rcx+2Ch]
0x140010743  and     eax, 82h
0x140010748  cmp     al, 82h
0x14001074a  jnz     short loc_140010761
0x14001074c  mov     rcx, [rcx+18h]
0x140010750  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140010757  mov     edx, 17h
0x14001075c  call    WPP_SF_
0x140010761  mov     cl, [rdi+45h]; Irql
0x140010764  call    cs:__imp_IoReleaseCancelSpinLock
0x14001076b  nop     dword ptr [rax+rax+00h]
0x140010770  mov     rbx, [rdi+78h]
0x140010774  lea     rcx, [rbx+20h]; SpinLock
0x140010778  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001077f  nop     dword ptr [rax+rax+00h]
0x140010784  and     dword ptr [rbx+5260h], 0FFFFFFDFh
0x14001078b  cmp     byte ptr [rbx+5264h], 0
0x140010792  mov     qword ptr [rbx+48h], 0
0x14001079a  jnz     short loc_1400107AE
0x14001079c  mov     r8b, al
0x14001079f  mov     edx, 2
0x1400107a4  mov     rcx, rbx
0x1400107a7  call    InitiateSstpContextCleanup
0x1400107ac  jmp     short loc_1400107C0
0x1400107ae  mov     dl, al; NewIrql
0x1400107b0  lea     rcx, [rbx+20h]; SpinLock
0x1400107b4  call    cs:__imp_KeReleaseSpinLock
0x1400107bb  nop     dword ptr [rax+rax+00h]
0x1400107c0  mov     dl, 2; PriorityBoost
0x1400107c2  mov     dword ptr [rdi+30h], 0C0000120h
0x1400107c9  mov     rcx, rdi; Irp
0x1400107cc  call    cs:__imp_IofCompleteRequest
0x1400107d3  nop     dword ptr [rax+rax+00h]
0x1400107d8  mov     rcx, rbx
0x1400107db  call    DereferenceRefCount
0x1400107e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400107e7  cmp     rcx, r14
0x1400107ea  jz      short loc_14001080D
0x1400107ec  mov     eax, [rcx+2Ch]
0x1400107ef  and     eax, 82h
0x1400107f4  cmp     al, 82h
0x1400107f6  jnz     short loc_14001080D
0x1400107f8  mov     rcx, [rcx+18h]
0x1400107fc  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140010803  mov     edx, 18h
0x140010808  call    WPP_SF_
0x14001080d  add     rsp, 28h
0x140010811  pop     r14
0x140010813  pop     rdi
0x140010814  pop     rsi
0x140010815  pop     rbx
0x140010816  retn
```
