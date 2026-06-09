# PcpLineLookupById

- ea: `0x140005b00`
- end: `0x140005c04`
- name: `PcpLineLookupById`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400057d0`
- `0x140005c10`

## callees

- `0x140003770`
- `0x140005b00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005b71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005bc7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005bde`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005b71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005bc7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005bde`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005b1b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005b1b`
- `NDIS!NdisAcquireRWLockRead` at `0x140005b89`
- `NDIS!NdisAcquireRWLockRead` at `0x140005b89`
- `NDIS!NdisReleaseRWLock` at `0x140005ba7`
- `NDIS!NdisReleaseRWLock` at `0x140005bee`
- `NDIS!NdisReleaseRWLock` at `0x140005ba7`
- `NDIS!NdisReleaseRWLock` at `0x140005bee`

## pseudocode

```c
__int64 __fastcall PcpLineLookupById(unsigned __int16 a1)
{
  __int64 v1; // rbx
  KIRQL v2; // al
  __int64 v3; // rbx
  struct _NDIS_RW_LOCK_EX *v4; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v2 = KeAcquireSpinLockRaiseToDpc(&PcgLineTableLock);
  NewIrql = v2;
  if ( !(_WORD)v1 || (unsigned __int16)v1 >= (unsigned __int16)PcgLineTableLen || !PcgLineTable )
  {
    KeReleaseSpinLock(&PcgLineTableLock, v2);
    return 0;
  }
  _mm_lfence();
  v3 = *((_QWORD *)PcgLineTable + v1);
  if ( v3 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 248));
    KeReleaseSpinLock(&PcgLineTableLock, NewIrql);
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v3 + 16), &LockState, 0);
    v4 = *(struct _NDIS_RW_LOCK_EX **)(v3 + 16);
    if ( *(_DWORD *)(v3 + 244) )
    {
      NdisReleaseRWLock(v4, &LockState);
      return v3;
    }
    NdisReleaseRWLock(v4, &LockState);
    PcpLineDereference((PVOID)v3);
    return 0;
  }
  KeReleaseSpinLock(&PcgLineTableLock, NewIrql);
  return 0;
}

```

## disassembly

```asm
0x140005b00  push    rbx
0x140005b02  sub     rsp, 20h
0x140005b06  xor     eax, eax
0x140005b08  movzx   ebx, cx
0x140005b0b  lea     rcx, PcgLineTableLock; SpinLock
0x140005b12  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x140005b17  mov     [rsp+28h+LockState.Flags], al
0x140005b1b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005b22  nop     dword ptr [rax+rax+00h]
0x140005b27  mov     cs:NewIrql, al
0x140005b2d  test    bx, bx
0x140005b30  jz      loc_140005BBD
0x140005b36  cmp     bx, cs:PcgLineTableLen
0x140005b3d  jnb     short loc_140005BBD
0x140005b3f  cmp     cs:PcgLineTable, 0
0x140005b47  jz      short loc_140005BBD
0x140005b49  lfence
0x140005b4c  mov     rax, cs:PcgLineTable
0x140005b53  lea     rcx, PcgLineTableLock; SpinLock
0x140005b5a  mov     rbx, [rax+rbx*8]
0x140005b5e  test    rbx, rbx
0x140005b61  jz      short loc_140005BD7
0x140005b63  lock inc dword ptr [rbx+0F8h]
0x140005b6a  movzx   edx, cs:NewIrql; NewIrql
0x140005b71  call    cs:__imp_KeReleaseSpinLock
0x140005b78  nop     dword ptr [rax+rax+00h]
0x140005b7d  mov     rcx, [rbx+10h]; Lock
0x140005b81  lea     rdx, [rsp+28h+LockState]; LockState
0x140005b86  xor     r8d, r8d; Flags
0x140005b89  call    cs:__imp_NdisAcquireRWLockRead
0x140005b90  nop     dword ptr [rax+rax+00h]
0x140005b95  cmp     dword ptr [rbx+0F4h], 0
0x140005b9c  lea     rdx, [rsp+28h+LockState]; LockState
0x140005ba1  mov     rcx, [rbx+10h]; Lock
0x140005ba5  jz      short loc_140005BEE
0x140005ba7  call    cs:__imp_NdisReleaseRWLock
0x140005bae  nop     dword ptr [rax+rax+00h]
0x140005bb3  mov     rax, rbx
0x140005bb6  add     rsp, 20h
0x140005bba  pop     rbx
0x140005bbb  retn
0x140005bbd  movzx   edx, al; NewIrql
0x140005bc0  lea     rcx, PcgLineTableLock; SpinLock
0x140005bc7  call    cs:__imp_KeReleaseSpinLock
0x140005bce  nop     dword ptr [rax+rax+00h]
0x140005bd3  xor     eax, eax
0x140005bd5  jmp     short loc_140005BB6
0x140005bd7  movzx   edx, cs:NewIrql; NewIrql
0x140005bde  call    cs:__imp_KeReleaseSpinLock
0x140005be5  nop     dword ptr [rax+rax+00h]
0x140005bea  xor     eax, eax
0x140005bec  jmp     short loc_140005BB6
0x140005bee  call    cs:__imp_NdisReleaseRWLock
0x140005bf5  nop     dword ptr [rax+rax+00h]
0x140005bfa  mov     rcx, rbx; P
0x140005bfd  call    PcpLineDereference
0x140005c02  jmp     short loc_140005BD3
```
