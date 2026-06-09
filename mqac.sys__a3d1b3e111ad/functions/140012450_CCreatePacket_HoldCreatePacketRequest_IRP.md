# CCreatePacket::HoldCreatePacketRequest(_IRP *)

- ea: `0x140012450`
- end: `0x1400124c7`
- name: `?HoldCreatePacketRequest@CCreatePacket@@QEAAXPEAU_IRP@@@Z`
- size: `119`
- prototype: `void __fastcall(CCreatePacket *__hidden this, struct _IRP *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140017694`
- `0x14001dfb4`

## callees

- `0x140012450`
- `0x14001268c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400124af`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400124af`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140012465`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140012465`

## pseudocode

```c
void __fastcall CCreatePacket::HoldCreatePacketRequest(CCreatePacket *this, struct _IRP *a2)
{
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  IoAcquireCancelSpinLock(&Irql);
  XList<_IRP,168>::insert(this, a2);
  if ( (*(_DWORD *)(&a2->Tail.CompletionKey + 3) & 0x80) != 0 )
    *(_BYTE *)(a2->IoStatus.Information + 24) = 1;
  _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, (__int64)ACCancelSender);
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  IoReleaseCancelSpinLock(Irql);
}

```

## disassembly

```asm
0x140012450  mov     [rsp+arg_8], rbx
0x140012455  push    rdi
0x140012456  sub     rsp, 20h
0x14001245a  mov     rbx, rcx
0x14001245d  mov     rdi, rdx
0x140012460  lea     rcx, [rsp+28h+Irql]; Irql
0x140012465  call    cs:__imp_IoAcquireCancelSpinLock
0x14001246c  nop     dword ptr [rax+rax+00h]
0x140012471  mov     rdx, rdi
0x140012474  mov     rcx, rbx
0x140012477  call    ?insert@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z; XList<_IRP,168>::insert(_IRP *)
0x14001247c  mov     r9d, [rdi+90h]
0x140012483  shr     r9d, 7
0x140012487  test    r9b, 1
0x14001248b  jz      short loc_140012495
0x14001248d  mov     rax, [rdi+38h]
0x140012491  mov     byte ptr [rax+18h], 1
0x140012495  lea     rax, ACCancelSender
0x14001249c  xchg    rax, [rdi+68h]
0x1400124a0  mov     rcx, [rdi+0B8h]
0x1400124a7  or      byte ptr [rcx+3], 1
0x1400124ab  mov     cl, [rsp+28h+Irql]; Irql
0x1400124af  call    cs:__imp_IoReleaseCancelSpinLock
0x1400124b6  nop     dword ptr [rax+rax+00h]
0x1400124bb  mov     rbx, [rsp+28h+arg_8]
0x1400124c0  add     rsp, 20h
0x1400124c4  pop     rdi
0x1400124c5  retn
```
