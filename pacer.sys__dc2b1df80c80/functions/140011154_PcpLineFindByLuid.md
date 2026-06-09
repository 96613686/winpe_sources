# PcpLineFindByLuid

- ea: `0x140011154`
- end: `0x14001126c`
- name: `PcpLineFindByLuid`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ab0`
- `0x140005578`
- `0x140005c10`
- `0x140007f90`
- `0x1400085c0`
- `0x14000cce0`

## callees

- `0x140003770`
- `0x140011154`

## import_xrefs

- `NDIS!NdisAcquireRWLockRead` at `0x140011180`
- `NDIS!NdisAcquireRWLockRead` at `0x1400111ce`
- `NDIS!NdisAcquireRWLockRead` at `0x140011210`
- `NDIS!NdisAcquireRWLockRead` at `0x140011180`
- `NDIS!NdisAcquireRWLockRead` at `0x1400111ce`
- `NDIS!NdisAcquireRWLockRead` at `0x140011210`
- `NDIS!NdisReleaseRWLock` at `0x1400111b6`
- `NDIS!NdisReleaseRWLock` at `0x1400111f5`
- `NDIS!NdisReleaseRWLock` at `0x140011235`
- `NDIS!NdisReleaseRWLock` at `0x14001124d`
- `NDIS!NdisReleaseRWLock` at `0x1400111b6`
- `NDIS!NdisReleaseRWLock` at `0x1400111f5`
- `NDIS!NdisReleaseRWLock` at `0x140011235`
- `NDIS!NdisReleaseRWLock` at `0x14001124d`

## pseudocode

```c
PVOID *__fastcall PcpLineFindByLuid(PVOID a1)
{
  PVOID *v2; // rsi
  PVOID *v3; // rdi
  struct _LOCK_STATE_EX LockState; // [rsp+38h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
  v2 = (PVOID *)PcgLineList;
  while ( v2 != &PcgLineList )
  {
    _InterlockedIncrement((volatile signed __int32 *)v2 + 62);
    NdisReleaseRWLock(PcgLineListLock, &LockState);
    NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v2[2], &LockState, 0);
    if ( *((_DWORD *)v2 + 61) == 2 && v2[3] == a1 )
    {
      NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v2[2], &LockState);
      return v2;
    }
    v3 = v2;
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v2[2], &LockState);
    NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
    v2 = (PVOID *)*v2;
    PcpLineDereference(v3);
  }
  NdisReleaseRWLock(PcgLineListLock, &LockState);
  return 0;
}

```

## disassembly

```asm
0x140011154  mov     [rsp+arg_0], rbx
0x140011159  mov     [rsp+arg_10], rsi
0x14001115e  push    rdi
0x14001115f  sub     rsp, 20h
0x140011163  xor     eax, eax
0x140011165  lea     rdx, [rsp+28h+LockState]; LockState
0x14001116a  mov     rbx, rcx
0x14001116d  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x140011172  mov     rcx, cs:PcgLineListLock; Lock
0x140011179  xor     r8d, r8d; Flags
0x14001117c  mov     [rsp+28h+LockState.Flags], al
0x140011180  call    cs:__imp_NdisAcquireRWLockRead
0x140011187  nop     dword ptr [rax+rax+00h]
0x14001118c  mov     rsi, cs:PcgLineList
0x140011193  lea     rax, PcgLineList
0x14001119a  lea     rdx, [rsp+28h+LockState]; LockState
0x14001119f  cmp     rsi, rax
0x1400111a2  jz      loc_140011246
0x1400111a8  lock inc dword ptr [rsi+0F8h]
0x1400111af  mov     rcx, cs:PcgLineListLock; Lock
0x1400111b6  call    cs:__imp_NdisReleaseRWLock
0x1400111bd  nop     dword ptr [rax+rax+00h]
0x1400111c2  mov     rcx, [rsi+10h]; Lock
0x1400111c6  lea     rdx, [rsp+28h+LockState]; LockState
0x1400111cb  xor     r8d, r8d; Flags
0x1400111ce  call    cs:__imp_NdisAcquireRWLockRead
0x1400111d5  nop     dword ptr [rax+rax+00h]
0x1400111da  cmp     dword ptr [rsi+0F4h], 2
0x1400111e1  jnz     short loc_1400111E9
0x1400111e3  cmp     [rsi+18h], rbx
0x1400111e7  jz      short loc_14001122C
0x1400111e9  mov     rcx, [rsi+10h]; Lock
0x1400111ed  lea     rdx, [rsp+28h+LockState]; LockState
0x1400111f2  mov     rdi, rsi
0x1400111f5  call    cs:__imp_NdisReleaseRWLock
0x1400111fc  nop     dword ptr [rax+rax+00h]
0x140011201  mov     rcx, cs:PcgLineListLock; Lock
0x140011208  lea     rdx, [rsp+28h+LockState]; LockState
0x14001120d  xor     r8d, r8d; Flags
0x140011210  call    cs:__imp_NdisAcquireRWLockRead
0x140011217  nop     dword ptr [rax+rax+00h]
0x14001121c  mov     rsi, [rsi]
0x14001121f  mov     rcx, rdi; P
0x140011222  call    PcpLineDereference
0x140011227  jmp     loc_140011193
0x14001122c  mov     rcx, [rsi+10h]; Lock
0x140011230  lea     rdx, [rsp+28h+LockState]; LockState
0x140011235  call    cs:__imp_NdisReleaseRWLock
0x14001123c  nop     dword ptr [rax+rax+00h]
0x140011241  mov     rax, rsi
0x140011244  jmp     short loc_14001125B
0x140011246  mov     rcx, cs:PcgLineListLock; Lock
0x14001124d  call    cs:__imp_NdisReleaseRWLock
0x140011254  nop     dword ptr [rax+rax+00h]
0x140011259  xor     eax, eax
0x14001125b  mov     rbx, [rsp+28h+arg_0]
0x140011260  mov     rsi, [rsp+28h+arg_10]
0x140011265  add     rsp, 20h
0x140011269  pop     rdi
0x14001126a  retn
```
