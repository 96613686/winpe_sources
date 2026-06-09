# CPacket::HoldWriteRequest(_IRP *)

- ea: `0x140017970`
- end: `0x140017a24`
- name: `?HoldWriteRequest@CPacket@@AEAAXPEAU_IRP@@@Z`
- size: `180`
- prototype: `void __fastcall(CPacket *__hidden this, struct _IRP *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140014c48`
- `0x140014ef8`
- `0x140018644`
- `0x140019454`

## callees

- `0x14001268c`
- `0x140017970`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140017a02`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140017a02`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400179b7`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400179b7`

## pseudocode

```c
void __fastcall CPacket::HoldWriteRequest(CPacket *this, struct _IRP *a2)
{
  ULONG_PTR Information; // rax
  __int64 v5; // rbx
  KIRQL Irql; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    if ( (*(_DWORD *)(&a2->Tail.CompletionKey + 3) & 0x80) == 0
      || (Information = a2->IoStatus.Information) == 0
      || !*(_BYTE *)(Information + 24) )
    {
      v5 = *(_QWORD *)(*((_QWORD *)this + 13) + 64LL);
      IoAcquireCancelSpinLock(&Irql);
      XList<_IRP,168>::insert(v5 + 368, a2);
      if ( (*(_DWORD *)(&a2->Tail.CompletionKey + 3) & 0x80) != 0 )
        *(_BYTE *)(a2->IoStatus.Information + 24) = 1;
      _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, (__int64)ACCancelWriter);
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      IoReleaseCancelSpinLock(Irql);
    }
    *((_DWORD *)this + 13) |= 0x80000u;
  }
}

```

## disassembly

```asm
0x140017970  test    rdx, rdx
0x140017973  jz      locret_140017A22
0x140017979  mov     [rsp+arg_0], rbx
0x14001797e  mov     [rsp+arg_10], rsi
0x140017983  push    rdi
0x140017984  sub     rsp, 20h
0x140017988  mov     eax, [rdx+90h]
0x14001798e  mov     rdi, rdx
0x140017991  shr     eax, 7
0x140017994  mov     rsi, rcx
0x140017997  test    al, 1
0x140017999  jz      short loc_1400179AA
0x14001799b  mov     rax, [rdx+38h]
0x14001799f  test    rax, rax
0x1400179a2  jz      short loc_1400179AA
0x1400179a4  cmp     byte ptr [rax+18h], 0
0x1400179a8  jnz     short loc_140017A0E
0x1400179aa  mov     rax, [rcx+68h]
0x1400179ae  lea     rcx, [rsp+28h+Irql]; Irql
0x1400179b3  mov     rbx, [rax+40h]
0x1400179b7  call    cs:__imp_IoAcquireCancelSpinLock
0x1400179be  nop     dword ptr [rax+rax+00h]
0x1400179c3  mov     rdx, rdi
0x1400179c6  lea     rcx, [rbx+170h]
0x1400179cd  call    ?insert@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z; XList<_IRP,168>::insert(_IRP *)
0x1400179d2  mov     edx, [rdi+90h]
0x1400179d8  shr     edx, 7
0x1400179db  test    dl, 1
0x1400179de  jz      short loc_1400179E8
0x1400179e0  mov     rax, [rdi+38h]
0x1400179e4  mov     byte ptr [rax+18h], 1
0x1400179e8  lea     rax, ACCancelWriter
0x1400179ef  xchg    rax, [rdi+68h]
0x1400179f3  mov     rcx, [rdi+0B8h]
0x1400179fa  or      byte ptr [rcx+3], 1
0x1400179fe  mov     cl, [rsp+28h+Irql]; Irql
0x140017a02  call    cs:__imp_IoReleaseCancelSpinLock
0x140017a09  nop     dword ptr [rax+rax+00h]
0x140017a0e  bts     dword ptr [rsi+34h], 13h
0x140017a13  mov     rsi, [rsp+28h+arg_10]
0x140017a18  mov     rbx, [rsp+28h+arg_0]
0x140017a1d  add     rsp, 20h
0x140017a21  pop     rdi
0x140017a22  retn
```
