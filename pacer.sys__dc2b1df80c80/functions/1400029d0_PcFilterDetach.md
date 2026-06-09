# PcFilterDetach

- ea: `0x1400029d0`
- end: `0x140002bd7`
- name: `PcFilterDetach`
- size: `519`
- prototype: `__int64 __fastcall(PVOID VirtualAddress)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001820`
- `0x14000287c`
- `0x1400029d0`
- `0x140002c1c`
- `0x140003770`
- `0x1400039a0`

## import_xrefs

- `NDIS!NdisFreeNetBufferListPool` at `0x140002a7a`
- `NDIS!NdisFreeNetBufferListPool` at `0x140002a7a`
- `NDIS!NdisWaitEvent` at `0x140002b58`
- `NDIS!NdisWaitEvent` at `0x140002b58`
- `NDIS!NdisFreeMemoryWithTag` at `0x140002b7c`
- `NDIS!NdisFreeMemoryWithTag` at `0x140002b7c`
- `NDIS!NdisFreeRWLock` at `0x140002b68`
- `NDIS!NdisFreeRWLock` at `0x140002b68`
- `NDIS!NdisResetEvent` at `0x140002a10`
- `NDIS!NdisResetEvent` at `0x140002a10`
- `NDIS!NdisReleaseRWLock` at `0x140002a25`
- `NDIS!NdisReleaseRWLock` at `0x140002ace`
- `NDIS!NdisReleaseRWLock` at `0x140002b2d`
- `NDIS!NdisReleaseRWLock` at `0x140002a25`
- `NDIS!NdisReleaseRWLock` at `0x140002ace`
- `NDIS!NdisReleaseRWLock` at `0x140002b2d`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400029f9`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002a95`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002b02`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400029f9`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002a95`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002b02`

## pseudocode

```c
void __fastcall PcFilterDetach(char *VirtualAddress)
{
  struct _NDIS_RW_LOCK_EX *v2; // rcx
  __int64 v3; // r8
  _QWORD *v4; // rcx
  PVOID *v5; // rax
  void *v6; // rcx
  PVOID *v7; // rdi
  PVOID *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  PVOID *v11; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  v2 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)VirtualAddress + 4);
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(v2, &LockState, 0);
  *((_DWORD *)VirtualAddress + 6) = 5;
  NdisResetEvent((PNDIS_EVENT)(VirtualAddress + 104));
  NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)VirtualAddress + 4), &LockState);
  v3 = *((_QWORD *)VirtualAddress + 20);
  PcpTraceLineUpDownEvent(
    v3 + 296,
    *((_DWORD *)VirtualAddress + 4),
    *(_QWORD *)(v3 + 272),
    *(unsigned __int16 *)(v3 + 264),
    *(_QWORD *)(v3 + 288),
    *(unsigned __int16 *)(v3 + 280),
    16);
  NdisFreeNetBufferListPool(*((NDIS_HANDLE *)VirtualAddress + 6));
  NdisAcquireRWLockWrite(PcgFilterDriverContext, &LockState, 0);
  v4 = *(_QWORD **)VirtualAddress;
  if ( *(char **)(*(_QWORD *)VirtualAddress + 8LL) != VirtualAddress
    || (v5 = (PVOID *)*((_QWORD *)VirtualAddress + 1), *v5 != VirtualAddress) )
  {
    __fastfail(3u);
  }
  *v5 = v4;
  v4[1] = v5;
  NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
  v6 = (void *)*((_QWORD *)VirtualAddress + 20);
  *((_QWORD *)VirtualAddress + 20) = 0;
  PcpLineDestroy(v6);
  while ( 1 )
  {
    v7 = 0;
    NdisAcquireRWLockWrite(PcgLineListLock, &LockState, 0);
    v8 = (PVOID *)PcgLineList;
    while ( v8 != &PcgLineList )
    {
      v11 = v8;
      v8 = (PVOID *)*v8;
      if ( v11[32] == VirtualAddress )
      {
        _InterlockedIncrement((volatile signed __int32 *)v11 + 62);
        v7 = v11;
        break;
      }
    }
    NdisReleaseRWLock(PcgLineListLock, &LockState);
    if ( !v7 )
      break;
    PcpLineDestroy(v7);
    PcpLineDereference(v7);
  }
  PcpInitializeDSCPToUPMappings(VirtualAddress + 214);
  PcpFilterDecrementDetachCount(VirtualAddress, v9, v10);
  NdisWaitEvent((PNDIS_EVENT)(VirtualAddress + 104), 0);
  NdisFreeRWLock(*((PNDIS_RW_LOCK_EX *)VirtualAddress + 4));
  NdisFreeMemoryWithTag(VirtualAddress, 0x63666350u);
}

```

## disassembly

```asm
0x1400029d0  mov     [rsp+arg_8], rbx
0x1400029d5  mov     [rsp+arg_10], rsi
0x1400029da  push    rdi
0x1400029db  sub     rsp, 40h
0x1400029df  xor     eax, eax
0x1400029e1  lea     rdx, [rsp+48h+LockState]; LockState
0x1400029e6  mov     rbx, rcx
0x1400029e9  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x1400029ee  mov     rcx, [rcx+20h]; Lock
0x1400029f2  xor     r8d, r8d; Flags
0x1400029f5  mov     [rsp+48h+LockState.Flags], al
0x1400029f9  call    cs:__imp_NdisAcquireRWLockWrite
0x140002a00  nop     dword ptr [rax+rax+00h]
0x140002a05  lea     rcx, [rbx+68h]; Event
0x140002a09  mov     dword ptr [rbx+18h], 5
0x140002a10  call    cs:__imp_NdisResetEvent
0x140002a17  nop     dword ptr [rax+rax+00h]
0x140002a1c  mov     rcx, [rbx+20h]; Lock
0x140002a20  lea     rdx, [rsp+48h+LockState]; LockState
0x140002a25  call    cs:__imp_NdisReleaseRWLock
0x140002a2c  nop     dword ptr [rax+rax+00h]
0x140002a31  mov     r8, [rbx+0A0h]
0x140002a38  mov     edx, [rbx+10h]
0x140002a3b  mov     [rsp+48h+var_18], 10h
0x140002a43  movzx   eax, word ptr [r8+118h]
0x140002a4b  lea     rcx, [r8+128h]
0x140002a52  movzx   r9d, word ptr [r8+108h]
0x140002a5a  mov     [rsp+48h+var_20], eax
0x140002a5e  mov     rax, [r8+120h]
0x140002a65  mov     r8, [r8+110h]
0x140002a6c  mov     [rsp+48h+var_28], rax
0x140002a71  call    PcpTraceLineUpDownEvent
0x140002a76  mov     rcx, [rbx+30h]; PoolHandle
0x140002a7a  call    cs:__imp_NdisFreeNetBufferListPool
0x140002a81  nop     dword ptr [rax+rax+00h]
0x140002a86  mov     rcx, cs:PcgFilterDriverContext; Lock
0x140002a8d  lea     rdx, [rsp+48h+LockState]; LockState
0x140002a92  xor     r8d, r8d; Flags
0x140002a95  call    cs:__imp_NdisAcquireRWLockWrite
0x140002a9c  nop     dword ptr [rax+rax+00h]
0x140002aa1  mov     rcx, [rbx]
0x140002aa4  cmp     [rcx+8], rbx
0x140002aa8  jnz     loc_140002BD0
0x140002aae  mov     rax, [rbx+8]
0x140002ab2  cmp     [rax], rbx
0x140002ab5  jnz     loc_140002BD0
0x140002abb  mov     [rax], rcx
0x140002abe  lea     rdx, [rsp+48h+LockState]; LockState
0x140002ac3  mov     [rcx+8], rax
0x140002ac7  mov     rcx, cs:PcgFilterDriverContext; Lock
0x140002ace  call    cs:__imp_NdisReleaseRWLock
0x140002ad5  nop     dword ptr [rax+rax+00h]
0x140002ada  mov     rcx, [rbx+0A0h]; P
0x140002ae1  mov     qword ptr [rbx+0A0h], 0
0x140002aec  call    PcpLineDestroy
0x140002af1  mov     rcx, cs:PcgLineListLock; Lock
0x140002af8  lea     rdx, [rsp+48h+LockState]; LockState
0x140002afd  xor     edi, edi
0x140002aff  xor     r8d, r8d; Flags
0x140002b02  call    cs:__imp_NdisAcquireRWLockWrite
0x140002b09  nop     dword ptr [rax+rax+00h]
0x140002b0e  mov     rcx, cs:PcgLineList
0x140002b15  lea     rax, PcgLineList
0x140002b1c  cmp     rcx, rax
0x140002b1f  jnz     short loc_140002B99
0x140002b21  mov     rcx, cs:PcgLineListLock; Lock
0x140002b28  lea     rdx, [rsp+48h+LockState]; LockState
0x140002b2d  call    cs:__imp_NdisReleaseRWLock
0x140002b34  nop     dword ptr [rax+rax+00h]
0x140002b39  test    rdi, rdi
0x140002b3c  jnz     short loc_140002BBB
0x140002b3e  lea     rcx, [rbx+0D6h]
0x140002b45  call    PcpInitializeDSCPToUPMappings
0x140002b4a  mov     rcx, rbx
0x140002b4d  call    PcpFilterDecrementDetachCount
0x140002b52  xor     edx, edx; MsToWait
0x140002b54  lea     rcx, [rbx+68h]; Event
0x140002b58  call    cs:__imp_NdisWaitEvent
0x140002b5f  nop     dword ptr [rax+rax+00h]
0x140002b64  mov     rcx, [rbx+20h]; Lock
0x140002b68  call    cs:__imp_NdisFreeRWLock
0x140002b6f  nop     dword ptr [rax+rax+00h]
0x140002b74  mov     edx, 63666350h; Tag
0x140002b79  mov     rcx, rbx; VirtualAddress
0x140002b7c  call    cs:__imp_NdisFreeMemoryWithTag
0x140002b83  nop     dword ptr [rax+rax+00h]
0x140002b88  mov     rbx, [rsp+48h+arg_8]
0x140002b8d  mov     rsi, [rsp+48h+arg_10]
0x140002b92  add     rsp, 40h
0x140002b96  pop     rdi
0x140002b97  retn
0x140002b99  mov     rax, rcx
0x140002b9c  mov     rcx, [rcx]
0x140002b9f  cmp     [rax+100h], rbx
0x140002ba6  jnz     loc_140002B15
0x140002bac  lock inc dword ptr [rax+0F8h]
0x140002bb3  mov     rdi, rax
0x140002bb6  jmp     loc_140002B21
0x140002bbb  mov     rcx, rdi; P
0x140002bbe  call    PcpLineDestroy
0x140002bc3  mov     rcx, rdi; P
0x140002bc6  call    PcpLineDereference
0x140002bcb  jmp     loc_140002AF1
0x140002bd0  mov     ecx, 3
0x140002bd5  int     29h; Win8: RtlFailFast(ecx)
```
