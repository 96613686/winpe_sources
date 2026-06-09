# PcpFilterStatusWanLineDown

- ea: `0x14000eca0`
- end: `0x14000ee81`
- name: `PcpFilterStatusWanLineDown`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140001d40`

## callees

- `0x14000287c`
- `0x140002c1c`
- `0x140003770`
- `0x14000eca0`
- `0x1400131e0`

## import_xrefs

- `NDIS!NdisFIndicateStatus` at `0x14000ee2b`
- `NDIS!NdisFIndicateStatus` at `0x14000ee5f`
- `NDIS!NdisFIndicateStatus` at `0x14000ee2b`
- `NDIS!NdisFIndicateStatus` at `0x14000ee5f`
- `NDIS!NdisAcquireRWLockRead` at `0x14000ed02`
- `NDIS!NdisAcquireRWLockRead` at `0x14000ed9c`
- `NDIS!NdisAcquireRWLockRead` at `0x14000ed02`
- `NDIS!NdisAcquireRWLockRead` at `0x14000ed9c`
- `NDIS!NdisReleaseRWLock` at `0x14000ed38`
- `NDIS!NdisReleaseRWLock` at `0x14000ed81`
- `NDIS!NdisReleaseRWLock` at `0x14000edd3`
- `NDIS!NdisReleaseRWLock` at `0x14000ee48`
- `NDIS!NdisReleaseRWLock` at `0x14000ed38`
- `NDIS!NdisReleaseRWLock` at `0x14000ed81`
- `NDIS!NdisReleaseRWLock` at `0x14000edd3`
- `NDIS!NdisReleaseRWLock` at `0x14000ee48`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000ed50`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000ed50`

## pseudocode

```c
__int64 __fastcall PcpFilterStatusWanLineDown(__int64 a1, struct _NDIS_STATUS_INDICATION *a2)
{
  bool v3; // cf
  _WORD *StatusBuffer; // r14
  volatile signed __int32 *v7; // rdi
  volatile signed __int32 *v8; // rbx
  struct _LOCK_STATE_EX LockState; // [rsp+68h] [rbp+10h] BYREF

  v3 = a2->StatusBufferSize < 0xC;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( v3 )
    return 3221225485LL;
  if ( *(_DWORD *)(a1 + 16) == 3 && *(_WORD *)(a1 + 212) == 2048 )
  {
    StatusBuffer = a2->StatusBuffer;
    NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
    v7 = (volatile signed __int32 *)PcgLineList;
    while ( v7 != (volatile signed __int32 *)&PcgLineList )
    {
      _InterlockedIncrement(v7 + 62);
      NdisReleaseRWLock(PcgLineListLock, &LockState);
      NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)v7 + 2), &LockState, 0);
      if ( !memcmp((const void *)(v7 + 82), StatusBuffer, 6u) )
      {
        *StatusBuffer = *((_WORD *)v7 + 120);
        StatusBuffer[3] = *((_WORD *)v7 + 167);
        NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)v7 + 2), &LockState);
        PcpTraceLineUpDownEvent(
          (_DWORD)v7 + 296,
          *(_DWORD *)(a1 + 16),
          *((_QWORD *)v7 + 34),
          *((unsigned __int16 *)v7 + 132),
          *((_QWORD *)v7 + 36),
          *((unsigned __int16 *)v7 + 140),
          17);
        PcpLineDestroy((PVOID)v7);
        NdisFIndicateStatus(*(NDIS_HANDLE *)(a1 + 40), a2);
        PcpLineDereference((PVOID)v7);
        return 0;
      }
      v8 = v7;
      NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)v7 + 2), &LockState);
      NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
      v7 = *(volatile signed __int32 **)v7;
      PcpLineDereference((PVOID)v8);
    }
    NdisReleaseRWLock(PcgLineListLock, &LockState);
    return 3221225473LL;
  }
  else
  {
    NdisFIndicateStatus(*(NDIS_HANDLE *)(a1 + 40), a2);
    return 0;
  }
}

```

## disassembly

```asm
0x14000eca0  mov     [rsp+arg_0], rbx
0x14000eca5  mov     [rsp+arg_10], rbp
0x14000ecaa  push    rsi
0x14000ecab  push    rdi
0x14000ecac  push    r14
0x14000ecae  sub     rsp, 40h
0x14000ecb2  xor     eax, eax
0x14000ecb4  mov     rbp, rdx
0x14000ecb7  cmp     dword ptr [rdx+38h], 0Ch
0x14000ecbb  mov     rsi, rcx
0x14000ecbe  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x14000ecc3  mov     [rsp+58h+LockState.Flags], al
0x14000ecc7  jnb     short loc_14000ECD3
0x14000ecc9  mov     eax, 0C000000Dh
0x14000ecce  jmp     loc_14000EE6D
0x14000ecd3  cmp     dword ptr [rcx+10h], 3
0x14000ecd7  jnz     loc_14000EE5B
0x14000ecdd  mov     eax, 800h
0x14000ece2  cmp     [rcx+0D4h], ax
0x14000ece9  jnz     loc_14000EE5B
0x14000ecef  mov     r14, [rdx+30h]
0x14000ecf3  xor     r8d, r8d; Flags
0x14000ecf6  mov     rcx, cs:PcgLineListLock; Lock
0x14000ecfd  lea     rdx, [rsp+58h+LockState]; LockState
0x14000ed02  call    cs:__imp_NdisAcquireRWLockRead
0x14000ed09  nop     dword ptr [rax+rax+00h]
0x14000ed0e  mov     rdi, cs:PcgLineList
0x14000ed15  lea     rax, PcgLineList
0x14000ed1c  lea     rdx, [rsp+58h+LockState]; LockState
0x14000ed21  cmp     rdi, rax
0x14000ed24  jz      loc_14000EE41
0x14000ed2a  lock inc dword ptr [rdi+0F8h]
0x14000ed31  mov     rcx, cs:PcgLineListLock; Lock
0x14000ed38  call    cs:__imp_NdisReleaseRWLock
0x14000ed3f  nop     dword ptr [rax+rax+00h]
0x14000ed44  mov     rcx, [rdi+10h]; Lock
0x14000ed48  lea     rdx, [rsp+58h+LockState]; LockState
0x14000ed4d  xor     r8d, r8d; Flags
0x14000ed50  call    cs:__imp_NdisAcquireRWLockWrite
0x14000ed57  nop     dword ptr [rax+rax+00h]
0x14000ed5c  lea     rcx, [rdi+148h]; Buf1
0x14000ed63  mov     r8d, 6; Size
0x14000ed69  mov     rdx, r14; Buf2
0x14000ed6c  call    memcmp
0x14000ed71  lea     rdx, [rsp+58h+LockState]; LockState
0x14000ed76  test    eax, eax
0x14000ed78  jz      short loc_14000EDB8
0x14000ed7a  mov     rcx, [rdi+10h]; Lock
0x14000ed7e  mov     rbx, rdi
0x14000ed81  call    cs:__imp_NdisReleaseRWLock
0x14000ed88  nop     dword ptr [rax+rax+00h]
0x14000ed8d  mov     rcx, cs:PcgLineListLock; Lock
0x14000ed94  lea     rdx, [rsp+58h+LockState]; LockState
0x14000ed99  xor     r8d, r8d; Flags
0x14000ed9c  call    cs:__imp_NdisAcquireRWLockRead
0x14000eda3  nop     dword ptr [rax+rax+00h]
0x14000eda8  mov     rdi, [rdi]
0x14000edab  mov     rcx, rbx; P
0x14000edae  call    PcpLineDereference
0x14000edb3  jmp     loc_14000ED15
0x14000edb8  movzx   eax, word ptr [rdi+0F0h]
0x14000edbf  mov     [r14], ax
0x14000edc3  movzx   eax, word ptr [rdi+14Eh]
0x14000edca  mov     [r14+6], ax
0x14000edcf  mov     rcx, [rdi+10h]; Lock
0x14000edd3  call    cs:__imp_NdisReleaseRWLock
0x14000edda  nop     dword ptr [rax+rax+00h]
0x14000eddf  movzx   eax, word ptr [rdi+118h]
0x14000ede6  lea     rcx, [rdi+128h]
0x14000eded  movzx   r9d, word ptr [rdi+108h]
0x14000edf5  mov     r8, [rdi+110h]
0x14000edfc  mov     edx, [rsi+10h]
0x14000edff  mov     [rsp+58h+var_28], 11h
0x14000ee07  mov     [rsp+58h+var_30], eax
0x14000ee0b  mov     rax, [rdi+120h]
0x14000ee12  mov     [rsp+58h+var_38], rax
0x14000ee17  call    PcpTraceLineUpDownEvent
0x14000ee1c  mov     rcx, rdi; P
0x14000ee1f  call    PcpLineDestroy
0x14000ee24  mov     rcx, [rsi+28h]; NdisFilterHandle
0x14000ee28  mov     rdx, rbp; StatusIndication
0x14000ee2b  call    cs:__imp_NdisFIndicateStatus
0x14000ee32  nop     dword ptr [rax+rax+00h]
0x14000ee37  mov     rcx, rdi; P
0x14000ee3a  call    PcpLineDereference
0x14000ee3f  jmp     short loc_14000EE6B
0x14000ee41  mov     rcx, cs:PcgLineListLock; Lock
0x14000ee48  call    cs:__imp_NdisReleaseRWLock
0x14000ee4f  nop     dword ptr [rax+rax+00h]
0x14000ee54  mov     eax, 0C0000001h
0x14000ee59  jmp     short loc_14000EE6D
0x14000ee5b  mov     rcx, [rcx+28h]; NdisFilterHandle
0x14000ee5f  call    cs:__imp_NdisFIndicateStatus
0x14000ee66  nop     dword ptr [rax+rax+00h]
0x14000ee6b  xor     eax, eax
0x14000ee6d  mov     rbx, [rsp+58h+arg_0]
0x14000ee72  mov     rbp, [rsp+58h+arg_10]
0x14000ee77  add     rsp, 40h
0x14000ee7b  pop     r14
0x14000ee7d  pop     rdi
0x14000ee7e  pop     rsi
0x14000ee7f  retn
```
