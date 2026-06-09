# GetProtocolInfo

- ea: `0x14000176c`
- end: `0x1400017ef`
- name: `GetProtocolInfo`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400010c0`
- `0x14000e400`
- `0x140035ad8`

## callees

- `0x14000176c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400017d4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400017d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001783`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001783`

## pseudocode

```c
char __fastcall GetProtocolInfo(__int64 a1)
{
  char v2; // di
  KIRQL v3; // cl
  unsigned int v4; // r8d
  unsigned int v5; // r9d
  KSPIN_LOCK v6; // rdx
  int v7; // eax

  v2 = 0;
  v3 = KeAcquireSpinLockRaiseToDpc(ProtocolInfoTable);
  v4 = 0;
  v5 = *((_DWORD *)ProtocolInfoTable + 5);
  v6 = ProtocolInfoTable[5];
  *((_BYTE *)ProtocolInfoTable + 8) = v3;
  while ( v4 < v5 )
  {
    if ( *(_WORD *)v6 == *(_WORD *)a1 )
    {
      v7 = *(_DWORD *)(v6 + 16);
      v2 = 1;
      *(_OWORD *)a1 = *(_OWORD *)v6;
      *(_DWORD *)(a1 + 16) = v7;
      break;
    }
    ++v4;
    v6 += 20LL;
  }
  KeReleaseSpinLock(ProtocolInfoTable, v3);
  return v2;
}

```

## disassembly

```asm
0x14000176c  mov     [rsp+arg_0], rbx
0x140001771  push    rdi
0x140001772  sub     rsp, 20h
0x140001776  mov     rbx, rcx
0x140001779  xor     dil, dil
0x14000177c  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x140001783  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000178a  nop     dword ptr [rax+rax+00h]
0x14000178f  mov     cl, al
0x140001791  xor     r8d, r8d
0x140001794  mov     rax, cs:ProtocolInfoTable
0x14000179b  mov     r9d, [rax+14h]
0x14000179f  mov     rdx, [rax+28h]
0x1400017a3  mov     [rax+8], cl
0x1400017a6  cmp     r8d, r9d
0x1400017a9  jnb     short loc_1400017CB
0x1400017ab  movzx   eax, word ptr [rbx]
0x1400017ae  cmp     [rdx], ax
0x1400017b1  jz      short loc_1400017BC
0x1400017b3  inc     r8d
0x1400017b6  add     rdx, 14h
0x1400017ba  jmp     short loc_1400017A6
0x1400017bc  movups  xmm0, xmmword ptr [rdx]
0x1400017bf  mov     eax, [rdx+10h]
0x1400017c2  mov     dil, 1
0x1400017c5  movups  xmmword ptr [rbx], xmm0
0x1400017c8  mov     [rbx+10h], eax
0x1400017cb  mov     dl, cl; NewIrql
0x1400017cd  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x1400017d4  call    cs:__imp_KeReleaseSpinLock
0x1400017db  nop     dword ptr [rax+rax+00h]
0x1400017e0  mov     rbx, [rsp+28h+arg_0]
0x1400017e5  mov     al, dil
0x1400017e8  add     rsp, 20h
0x1400017ec  pop     rdi
0x1400017ed  retn
```
