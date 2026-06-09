# CQMInterface::HoldService(_IRP *)

- ea: `0x14001ad2c`
- end: `0x14001ada6`
- name: `?HoldService@CQMInterface@@AEAAXPEAU_IRP@@@Z`
- size: `122`
- prototype: `void __fastcall(CQMInterface *__hidden this, struct _IRP *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14001aaf8`
- `0x14001b270`

## callees

- `0x14001268c`
- `0x14001a840`
- `0x14001ad2c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001ad7e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001ad7e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001ad46`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001ad46`

## pseudocode

```c
void __fastcall CQMInterface::HoldService(CQMInterface *this, struct _IRP *a2)
{
  IRP *v4; // rdx
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  Irql = 0;
  IoAcquireCancelSpinLock(&Irql);
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  XList<_IRP,168>::insert((char *)this + 40, a2);
  if ( a2->Cancel )
  {
    a2->CancelIrql = Irql;
    ACCancelServiceRequest(0, v4);
  }
  else
  {
    _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, (__int64)ACCancelServiceRequest);
    IoReleaseCancelSpinLock(Irql);
  }
}

```

## disassembly

```asm
0x14001ad2c  mov     [rsp+arg_8], rbx
0x14001ad31  push    rdi
0x14001ad32  sub     rsp, 20h
0x14001ad36  mov     rbx, rcx
0x14001ad39  mov     [rsp+28h+Irql], 0
0x14001ad3e  lea     rcx, [rsp+28h+Irql]; Irql
0x14001ad43  mov     rdi, rdx
0x14001ad46  call    cs:__imp_IoAcquireCancelSpinLock
0x14001ad4d  nop     dword ptr [rax+rax+00h]
0x14001ad52  mov     rax, [rdi+0B8h]
0x14001ad59  lea     rcx, [rbx+28h]
0x14001ad5d  mov     rdx, rdi
0x14001ad60  or      byte ptr [rax+3], 1
0x14001ad64  call    ?insert@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z; XList<_IRP,168>::insert(_IRP *)
0x14001ad69  cmp     byte ptr [rdi+44h], 0
0x14001ad6d  jnz     short loc_14001AD8C
0x14001ad6f  lea     rax, ACCancelServiceRequest
0x14001ad76  xchg    rax, [rdi+68h]
0x14001ad7a  mov     cl, [rsp+28h+Irql]; Irql
0x14001ad7e  call    cs:__imp_IoReleaseCancelSpinLock
0x14001ad85  nop     dword ptr [rax+rax+00h]
0x14001ad8a  jmp     short loc_14001AD9A
0x14001ad8c  mov     al, [rsp+28h+Irql]
0x14001ad90  xor     ecx, ecx
0x14001ad92  mov     [rdi+45h], al
0x14001ad95  call    ACCancelServiceRequest
0x14001ad9a  mov     rbx, [rsp+28h+arg_8]
0x14001ad9f  add     rsp, 20h
0x14001ada3  pop     rdi
0x14001ada4  retn
```
