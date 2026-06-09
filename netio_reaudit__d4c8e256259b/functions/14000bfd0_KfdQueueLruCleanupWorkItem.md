# KfdQueueLruCleanupWorkItem

- ea: `0x14000bfd0`
- end: `0x14000c1d6`
- name: `KfdQueueLruCleanupWorkItem`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140015320`

## callees

- `0x14000afa0`
- `0x14000bfd0`
- `0x14000c210`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000c0ae`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000c104`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000c0ae`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000c104`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c069`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c069`
- `NDIS!NdisReleaseRWLock` at `0x14000c135`
- `NDIS!NdisReleaseRWLock` at `0x14000c135`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000c087`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000c087`

## pseudocode

```c
void KfdQueueLruCleanupWorkItem()
{
  unsigned __int64 v0; // rbp
  unsigned __int64 v1; // rbx
  PNPAGED_LOOKASIDE_LIST v2; // rsi
  KIRQL CurrentIrql; // di
  __int64 v4; // rdx
  PNPAGED_LOOKASIDE_LIST v5; // rbx
  _DWORD *v6; // rdx
  _OWORD *v7; // r8
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF
  _OWORD *v9; // [rsp+48h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v9 = 0;
  if ( LODWORD(gWfpGlobal[1].L.FreeEx) )
  {
    v0 = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
    v1 = v0 - _InterlockedExchangeAdd64((volatile signed __int64 *)&gWfpGlobal[10], 0);
    if ( v1 >= 0x2710 )
    {
      v2 = gWfpGlobal;
      CurrentIrql = KeGetCurrentIrql();
      NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v2[13].L.ListEntry.Flink, &LockState, 0);
      if ( CurrentIrql != 2 && gWfpPerProContext )
      {
        v4 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        *(_QWORD *)(v4 + 8) = MEMORY[0xFFFFF78000000008];
        *(_DWORD *)v4 = 4;
      }
      if ( !LOBYTE(gWfpGlobal[9].L.Future[8]) && !WfpPoolAllocNonPaged(16, 1282434647, &v9) )
      {
        v7 = v9;
        *v9 = 0;
        *((_DWORD *)v7 + 2) = v1 / 0x3E8 / 0xA;
        NetioInsertWorkQueue(&gWfpGlobal[10].L.SingleListHead + 1);
        LOBYTE(gWfpGlobal[9].L.Future[8]) = 1;
        _InterlockedExchange64((volatile __int64 *)&gWfpGlobal[10], v0);
      }
      v5 = gWfpGlobal;
      if ( gWfpPerProContext )
      {
        v6 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        if ( *v6 == 4 )
          *v6 = 0;
      }
      NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v5[13].L.ListEntry.Flink, &LockState);
    }
  }
}

```

## disassembly

```asm
0x14000bfd0  push    r14
0x14000bfd2  sub     rsp, 30h
0x14000bfd6  xor     eax, eax
0x14000bfd8  xor     r14d, r14d
0x14000bfdb  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x14000bfe0  mov     [rsp+38h+LockState.Flags], al
0x14000bfe4  mov     rax, cs:gWfpGlobal
0x14000bfeb  mov     [rsp+38h+arg_8], r14
0x14000bff0  cmp     [rax+0B8h], r14d
0x14000bff7  jz      short loc_14000C050
0x14000bff9  mov     rcx, 0FFFFF78000000008h
0x14000c003  mov     [rsp+38h+arg_10], rbx
0x14000c008  mov     [rsp+38h+arg_18], rbp
0x14000c00d  mov     rax, 346DC5D63886594Bh
0x14000c017  mov     rcx, [rcx]
0x14000c01a  mul     rcx
0x14000c01d  mov     rax, cs:gWfpGlobal
0x14000c024  mov     ecx, r14d
0x14000c027  mov     rbp, rdx
0x14000c02a  shr     rbp, 0Bh
0x14000c02e  lock xadd [rax+500h], rcx
0x14000c037  mov     rbx, rbp
0x14000c03a  sub     rbx, rcx
0x14000c03d  cmp     rbx, 2710h
0x14000c044  jnb     short loc_14000C058
0x14000c046  mov     rbx, [rsp+38h+arg_10]
0x14000c04b  mov     rbp, [rsp+38h+arg_18]
0x14000c050  add     rsp, 30h
0x14000c054  pop     r14
0x14000c056  retn
0x14000c058  mov     [rsp+38h+var_10], rsi
0x14000c05d  mov     rsi, cs:gWfpGlobal
0x14000c064  mov     [rsp+38h+var_18], rdi
0x14000c069  call    cs:__imp_KeGetCurrentIrql
0x14000c070  nop     dword ptr [rax+rax+00h]
0x14000c075  mov     rcx, [rsi+6C0h]; Lock
0x14000c07c  lea     rdx, [rsp+38h+LockState]; LockState
0x14000c081  xor     r8d, r8d; Flags
0x14000c084  movzx   edi, al
0x14000c087  call    cs:__imp_NdisAcquireRWLockWrite
0x14000c08e  nop     dword ptr [rax+rax+00h]
0x14000c093  mov     rsi, [rsp+38h+var_10]
0x14000c098  cmp     dil, 2
0x14000c09c  mov     rdi, [rsp+38h+var_18]
0x14000c0a1  jz      short loc_14000C0E2
0x14000c0a3  cmp     cs:gWfpPerProContext, r14
0x14000c0aa  jz      short loc_14000C0E2
0x14000c0ac  xor     ecx, ecx; ProcNumber
0x14000c0ae  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000c0b5  nop     dword ptr [rax+rax+00h]
0x14000c0ba  imul    eax, cs:gWfpPerProContextSize
0x14000c0c1  mov     ecx, eax
0x14000c0c3  mov     rax, cs:gWfpPerProContext
0x14000c0ca  mov     rdx, [rcx+rax]
0x14000c0ce  mov     rax, ds:0FFFFF78000000008h
0x14000c0d8  mov     [rdx+8], rax
0x14000c0dc  mov     dword ptr [rdx], 4
0x14000c0e2  mov     rax, cs:gWfpGlobal
0x14000c0e9  cmp     [rax+4F8h], r14b
0x14000c0f0  jz      short loc_14000C14B
0x14000c0f2  cmp     cs:gWfpPerProContext, r14
0x14000c0f9  mov     rbx, cs:gWfpGlobal
0x14000c100  jz      short loc_14000C129
0x14000c102  xor     ecx, ecx; ProcNumber
0x14000c104  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000c10b  nop     dword ptr [rax+rax+00h]
0x14000c110  imul    eax, cs:gWfpPerProContextSize
0x14000c117  mov     ecx, eax
0x14000c119  mov     rax, cs:gWfpPerProContext
0x14000c120  mov     rdx, [rcx+rax]
0x14000c124  cmp     dword ptr [rdx], 4
0x14000c127  jz      short loc_14000C146
0x14000c129  mov     rcx, [rbx+6C0h]; Lock
0x14000c130  lea     rdx, [rsp+38h+LockState]; LockState
0x14000c135  call    cs:__imp_NdisReleaseRWLock
0x14000c13c  nop     dword ptr [rax+rax+00h]
0x14000c141  jmp     loc_14000C046
0x14000c146  mov     [rdx], r14d
0x14000c149  jmp     short loc_14000C129
0x14000c14b  lea     r8, [rsp+38h+arg_8]
0x14000c150  mov     edx, 4C706657h
0x14000c155  mov     ecx, 10h
0x14000c15a  call    WfpPoolAllocNonPaged
0x14000c15f  test    rax, rax
0x14000c162  jnz     short loc_14000C0F2
0x14000c164  mov     r8, [rsp+38h+arg_8]
0x14000c169  mov     rax, 624DD2F1A9FBE77h
0x14000c173  mul     rbx
0x14000c176  xorps   xmm0, xmm0
0x14000c179  movups  xmmword ptr [r8], xmm0
0x14000c17d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000c187  sub     rbx, rdx
0x14000c18a  shr     rbx, 1
0x14000c18d  add     rbx, rdx
0x14000c190  shr     rbx, 9
0x14000c194  mul     rbx
0x14000c197  shr     rdx, 3
0x14000c19b  mov     [r8+8], edx
0x14000c19f  mov     rdx, r8
0x14000c1a2  mov     rcx, cs:gWfpGlobal
0x14000c1a9  add     rcx, 508h; Context
0x14000c1b0  call    NetioInsertWorkQueue
0x14000c1b5  mov     rax, cs:gWfpGlobal
0x14000c1bc  mov     byte ptr [rax+4F8h], 1
0x14000c1c3  mov     rax, cs:gWfpGlobal
0x14000c1ca  xchg    rbp, [rax+500h]
0x14000c1d1  jmp     loc_14000C0F2
```
