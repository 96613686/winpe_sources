# VmbusTlpActivateDeliveryQueue

- ea: `0x140003bc8`
- end: `0x140003c6a`
- name: `VmbusTlpActivateDeliveryQueue`
- size: `162`
- prototype: `void __fastcall(__int64, char)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400020c4`
- `0x140003cec`
- `0x140007794`
- `0x140007b00`

## callees

- `0x14000309c`
- `0x140003bc8`
- `0x140009c38`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003be1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003be1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003c22`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003c22`

## pseudocode

```c
void __fastcall VmbusTlpActivateDeliveryQueue(__int64 a1, char a2)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v5; // al
  int v6; // ecx
  char v7; // di

  v2 = (KSPIN_LOCK *)(a1 + 744);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 744));
  v6 = *(_DWORD *)(a1 + 772);
  v7 = 1;
  if ( (unsigned int)(v6 - 2) <= 1 || a2 && v6 == 1 )
    *(_DWORD *)(a1 + 772) = 3;
  else
    v7 = *(_BYTE *)(a1 + 776);
  KeReleaseSpinLock(v2, v5);
  if ( v7 )
  {
    VmbusTlDeliverDataIndications(a1, 0);
  }
  else if ( (unsigned int)dword_140013058 > 4 )
  {
    HvsocketTraceEndpointUlongMessage(
      (const int *)"VmbusTlpActivateDeliveryQueue: Delivery queue not processing.",
      a1,
      *(unsigned int *)(a1 + 772));
  }
}

```

## disassembly

```asm
0x140003bc8  push    rbx
0x140003bca  push    rbp
0x140003bcb  push    rsi
0x140003bcc  push    rdi
0x140003bcd  sub     rsp, 28h
0x140003bd1  lea     rsi, [rcx+2E8h]
0x140003bd8  mov     rbx, rcx
0x140003bdb  mov     rcx, rsi; SpinLock
0x140003bde  mov     bpl, dl
0x140003be1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003be8  nop     dword ptr [rax+rax+00h]
0x140003bed  mov     ecx, [rbx+304h]
0x140003bf3  mov     edi, 1
0x140003bf8  lea     r8d, [rcx-2]
0x140003bfc  cmp     r8d, edi
0x140003bff  jbe     short loc_140003C13
0x140003c01  test    bpl, bpl
0x140003c04  jz      short loc_140003C0A
0x140003c06  cmp     ecx, edi
0x140003c08  jz      short loc_140003C13
0x140003c0a  mov     dil, [rbx+308h]
0x140003c11  jmp     short loc_140003C1D
0x140003c13  mov     dword ptr [rbx+304h], 3
0x140003c1d  mov     dl, al; NewIrql
0x140003c1f  mov     rcx, rsi; SpinLock
0x140003c22  call    cs:__imp_KeReleaseSpinLock
0x140003c29  nop     dword ptr [rax+rax+00h]
0x140003c2e  test    dil, dil
0x140003c31  jz      short loc_140003C3F
0x140003c33  xor     edx, edx
0x140003c35  mov     rcx, rbx
0x140003c38  call    VmbusTlDeliverDataIndications
0x140003c3d  jmp     short loc_140003C60
0x140003c3f  mov     eax, cs:dword_140013058
0x140003c45  cmp     eax, 4
0x140003c48  jbe     short loc_140003C60
0x140003c4a  mov     r8d, [rbx+304h]
0x140003c51  lea     rcx, aVmbustlpactiva; "VmbusTlpActivateDeliveryQueue: Delivery"...
0x140003c58  mov     rdx, rbx
0x140003c5b  call    HvsocketTraceEndpointUlongMessage
0x140003c60  add     rsp, 28h
0x140003c64  pop     rdi
0x140003c65  pop     rsi
0x140003c66  pop     rbp
0x140003c67  pop     rbx
0x140003c68  retn
```
