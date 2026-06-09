# PcpLineFindByInstanceName

- ea: `0x140002d48`
- end: `0x140002e6f`
- name: `PcpLineFindByInstanceName`
- size: `295`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140003ab0`
- `0x140005578`
- `0x14001f2a0`

## callees

- `0x140002d48`
- `0x140003770`
- `0x1400131e0`

## import_xrefs

- `NDIS!NdisAcquireRWLockRead` at `0x140002d71`
- `NDIS!NdisAcquireRWLockRead` at `0x140002dbf`
- `NDIS!NdisAcquireRWLockRead` at `0x140002dfb`
- `NDIS!NdisAcquireRWLockRead` at `0x140002d71`
- `NDIS!NdisAcquireRWLockRead` at `0x140002dbf`
- `NDIS!NdisAcquireRWLockRead` at `0x140002dfb`
- `NDIS!NdisReleaseRWLock` at `0x140002da7`
- `NDIS!NdisReleaseRWLock` at `0x140002de0`
- `NDIS!NdisReleaseRWLock` at `0x140002e3f`
- `NDIS!NdisReleaseRWLock` at `0x140002e57`
- `NDIS!NdisReleaseRWLock` at `0x140002da7`
- `NDIS!NdisReleaseRWLock` at `0x140002de0`
- `NDIS!NdisReleaseRWLock` at `0x140002e3f`
- `NDIS!NdisReleaseRWLock` at `0x140002e57`

## pseudocode

```c
PVOID *__fastcall PcpLineFindByInstanceName(void *Buf1, unsigned __int16 a2)
{
  size_t v2; // rsi
  PVOID *v4; // rdi
  PVOID *v5; // rbx
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

  v2 = a2;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
  v4 = (PVOID *)PcgLineList;
  while ( v4 != &PcgLineList )
  {
    _InterlockedIncrement((volatile signed __int32 *)v4 + 62);
    NdisReleaseRWLock(PcgLineListLock, &LockState);
    NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v4[2], &LockState, 0);
    if ( *((_DWORD *)v4 + 61) == 2 && (_WORD)v2 == *((_WORD *)v4 + 132) && !memcmp(Buf1, v4[34], v2) )
    {
      NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v4[2], &LockState);
      return v4;
    }
    v5 = v4;
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v4[2], &LockState);
    NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
    v4 = (PVOID *)*v4;
    PcpLineDereference(v5);
  }
  NdisReleaseRWLock(PcgLineListLock, &LockState);
  return 0;
}

```

## disassembly

```asm
0x140002d48  push    rbx
0x140002d4a  push    rbp
0x140002d4b  push    rsi
0x140002d4c  push    rdi
0x140002d4d  sub     rsp, 28h
0x140002d51  xor     eax, eax
0x140002d53  movzx   esi, dx
0x140002d56  mov     rbp, rcx
0x140002d59  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140002d5e  mov     rcx, cs:PcgLineListLock; Lock
0x140002d65  lea     rdx, [rsp+48h+LockState]; LockState
0x140002d6a  xor     r8d, r8d; Flags
0x140002d6d  mov     [rsp+48h+LockState.Flags], al
0x140002d71  call    cs:__imp_NdisAcquireRWLockRead
0x140002d78  nop     dword ptr [rax+rax+00h]
0x140002d7d  mov     rdi, cs:PcgLineList
0x140002d84  lea     rax, PcgLineList
0x140002d8b  lea     rdx, [rsp+48h+LockState]; LockState
0x140002d90  cmp     rdi, rax
0x140002d93  jz      loc_140002E50
0x140002d99  lock inc dword ptr [rdi+0F8h]
0x140002da0  mov     rcx, cs:PcgLineListLock; Lock
0x140002da7  call    cs:__imp_NdisReleaseRWLock
0x140002dae  nop     dword ptr [rax+rax+00h]
0x140002db3  mov     rcx, [rdi+10h]; Lock
0x140002db7  lea     rdx, [rsp+48h+LockState]; LockState
0x140002dbc  xor     r8d, r8d; Flags
0x140002dbf  call    cs:__imp_NdisAcquireRWLockRead
0x140002dc6  nop     dword ptr [rax+rax+00h]
0x140002dcb  cmp     dword ptr [rdi+0F4h], 2
0x140002dd2  jz      short loc_140002E17
0x140002dd4  mov     rcx, [rdi+10h]; Lock
0x140002dd8  lea     rdx, [rsp+48h+LockState]; LockState
0x140002ddd  mov     rbx, rdi
0x140002de0  call    cs:__imp_NdisReleaseRWLock
0x140002de7  nop     dword ptr [rax+rax+00h]
0x140002dec  mov     rcx, cs:PcgLineListLock; Lock
0x140002df3  lea     rdx, [rsp+48h+LockState]; LockState
0x140002df8  xor     r8d, r8d; Flags
0x140002dfb  call    cs:__imp_NdisAcquireRWLockRead
0x140002e02  nop     dword ptr [rax+rax+00h]
0x140002e07  mov     rdi, [rdi]
0x140002e0a  mov     rcx, rbx; P
0x140002e0d  call    PcpLineDereference
0x140002e12  jmp     loc_140002D84
0x140002e17  cmp     si, [rdi+108h]
0x140002e1e  jnz     short loc_140002DD4
0x140002e20  mov     rdx, [rdi+110h]; Buf2
0x140002e27  mov     r8, rsi; Size
0x140002e2a  mov     rcx, rbp; Buf1
0x140002e2d  call    memcmp
0x140002e32  test    eax, eax
0x140002e34  jnz     short loc_140002DD4
0x140002e36  mov     rcx, [rdi+10h]; Lock
0x140002e3a  lea     rdx, [rsp+48h+LockState]; LockState
0x140002e3f  call    cs:__imp_NdisReleaseRWLock
0x140002e46  nop     dword ptr [rax+rax+00h]
0x140002e4b  mov     rax, rdi
0x140002e4e  jmp     short loc_140002E65
0x140002e50  mov     rcx, cs:PcgLineListLock; Lock
0x140002e57  call    cs:__imp_NdisReleaseRWLock
0x140002e5e  nop     dword ptr [rax+rax+00h]
0x140002e63  xor     eax, eax
0x140002e65  add     rsp, 28h
0x140002e69  pop     rdi
0x140002e6a  pop     rsi
0x140002e6b  pop     rbp
0x140002e6c  pop     rbx
0x140002e6d  retn
```
