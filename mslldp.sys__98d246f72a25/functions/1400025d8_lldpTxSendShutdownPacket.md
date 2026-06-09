# lldpTxSendShutdownPacket

- ea: `0x1400025d8`
- end: `0x1400026b2`
- name: `lldpTxSendShutdownPacket`
- size: `218`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001330`
- `0x140002180`
- `0x140002500`

## callees

- `0x1400025d8`
- `0x1400026c0`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140002695`
- `ntoskrnl!KeLowerIrql` at `0x140002695`
- `ntoskrnl!KfRaiseIrql` at `0x14000262b`
- `ntoskrnl!KfRaiseIrql` at `0x14000262b`
- `NDIS!NdisReleaseRWLock` at `0x14000267c`
- `NDIS!NdisReleaseRWLock` at `0x14000267c`
- `NDIS!NdisAcquireRWLockRead` at `0x140002648`
- `NDIS!NdisAcquireRWLockRead` at `0x140002648`

## pseudocode

```c
void __fastcall lldpTxSendShutdownPacket(__int64 a1)
{
  signed __int32 v2; // eax
  signed __int32 v3; // ett
  KIRQL v4; // bl
  __int64 v5; // r8
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  _m_prefetchw((const void *)(a1 + 304));
  v2 = *(_DWORD *)(a1 + 304);
  do
  {
    v3 = v2;
    v2 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 304), v2, v2);
  }
  while ( v3 != v2 );
  if ( (v2 & 2) == 0 && _InterlockedExchange((volatile __int32 *)(a1 + 184), 1) != 1 )
  {
    v4 = KfRaiseIrql(2u);
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 976), &LockState, 1u);
    v5 = *(_QWORD *)(a1 + 208);
    *(_DWORD *)v5 = *(_DWORD *)(a1 + 144);
    *(_WORD *)(v5 + 4) = *(_WORD *)(a1 + 148);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 976), &LockState);
    lldpTransmitNblOnPort(a1, a1 + 184);
    KeLowerIrql(v4);
  }
}

```

## disassembly

```asm
0x1400025d8  mov     [rsp+arg_8], rbx
0x1400025dd  mov     [rsp+arg_10], rsi
0x1400025e2  push    rdi
0x1400025e3  sub     rsp, 20h
0x1400025e7  xor     eax, eax
0x1400025e9  mov     rdi, rcx
0x1400025ec  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x1400025f1  mov     [rsp+28h+LockState.Flags], al
0x1400025f5  prefetchw byte ptr [rcx+130h]
0x1400025fc  mov     eax, [rcx+130h]
0x140002602  mov     edx, eax
0x140002604  lock cmpxchg [rcx+130h], edx
0x14000260c  jnz     short loc_140002602
0x14000260e  mov     cl, 2; NewIrql
0x140002610  test    cl, al
0x140002612  jnz     loc_1400026A1
0x140002618  lea     rsi, [rdi+0B8h]
0x14000261f  mov     eax, 1
0x140002624  xchg    eax, [rsi]
0x140002626  cmp     eax, 1
0x140002629  jz      short loc_1400026A1
0x14000262b  call    cs:__imp_KfRaiseIrql
0x140002632  nop     dword ptr [rax+rax+00h]
0x140002637  mov     rcx, [rdi+3D0h]; Lock
0x14000263e  lea     rdx, [rsp+28h+LockState]; LockState
0x140002643  mov     r8b, 1; Flags
0x140002646  mov     bl, al
0x140002648  call    cs:__imp_NdisAcquireRWLockRead
0x14000264f  nop     dword ptr [rax+rax+00h]
0x140002654  mov     ecx, [rdi+90h]
0x14000265a  lea     rdx, [rsp+28h+LockState]; LockState
0x14000265f  mov     r8, [rdi+0D0h]
0x140002666  mov     [r8], ecx
0x140002669  movzx   ecx, word ptr [rdi+94h]
0x140002670  mov     [r8+4], cx
0x140002675  mov     rcx, [rdi+3D0h]; Lock
0x14000267c  call    cs:__imp_NdisReleaseRWLock
0x140002683  nop     dword ptr [rax+rax+00h]
0x140002688  mov     rdx, rsi
0x14000268b  mov     rcx, rdi
0x14000268e  call    lldpTransmitNblOnPort
0x140002693  mov     cl, bl; NewIrql
0x140002695  call    cs:__imp_KeLowerIrql
0x14000269c  nop     dword ptr [rax+rax+00h]
0x1400026a1  mov     rbx, [rsp+28h+arg_8]
0x1400026a6  mov     rsi, [rsp+28h+arg_10]
0x1400026ab  add     rsp, 20h
0x1400026af  pop     rdi
0x1400026b0  retn
```
