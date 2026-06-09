# KfdGetBatchUpdateContext

- ea: `0x14000c4e0`
- end: `0x14000c745`
- name: `KfdGetBatchUpdateContext`
- size: `613`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140047dc0`
- `0x140048db0`
- `0x1400611d0`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14000afa0`
- `0x14000c4e0`
- `0x14000c74c`
- `0x14000ca00`
- `0x14001cfe0`
- `0x140061bc0`
- `0x140078100`
- `0x140078400`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000c5f6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000c5f6`
- `NDIS!NdisReleaseRWLock` at `0x14000c627`
- `NDIS!NdisReleaseRWLock` at `0x14000c627`

## string_xrefs

- `0x14000c545`: `FeAcquireWriteEngineLock`
- `0x14000c6f6`: `FeAcquireWriteEngineLock`
- `0x14000c731`: `KfdGetBatchUpdateContext`

## pseudocode

```c
__int64 __fastcall KfdGetBatchUpdateContext(_QWORD *a1)
{
  __int64 CurrentThreadCompartmentId; // rsi
  __int64 v3; // rbx
  void *v4; // rdi
  PNPAGED_LOOKASIDE_LIST v5; // rdi
  _DWORD *v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // r8
  void *v10; // rdi
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF
  void *v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = 0;
  *a1 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  CurrentThreadCompartmentId = (unsigned int)NdisGetCurrentThreadCompartmentId();
  v3 = 0;
  WfpAcquireFastWriteLock((PNDIS_RW_LOCK_EX *)&gWfpGlobal[1], &LockState);
  if ( LODWORD(gWfpGlobal[1].L.ListEntry.Flink) == 2 )
  {
    v3 = WfpReportSysErrorAsNtStatus(gWfpGlobal, "FeAcquireWriteEngineLock", 3221225473LL, 1);
    if ( v3 )
    {
      WfpReleaseFastWriteLock(&gWfpGlobal[1], &LockState);
      WfpReportError(v3, "FeAcquireWriteEngineLock");
      goto LABEL_12;
    }
  }
  if ( (unsigned int)CurrentThreadCompartmentId >= gBatchUpdates )
  {
    v3 = WfpPoolAllocNonPaged(8LL * (unsigned int)(CurrentThreadCompartmentId + 5), 1399875159, &v12);
    if ( v3 )
      goto LABEL_8;
    v10 = v12;
    memset(v12, 0, 8LL * (unsigned int)(CurrentThreadCompartmentId + 5));
    memmove(v10, Src, 8LL * (unsigned int)gBatchUpdates);
    Src = v10;
    gBatchUpdates = CurrentThreadCompartmentId + 5;
  }
  v4 = (void *)*((_QWORD *)Src + CurrentThreadCompartmentId);
  v12 = v4;
  if ( !v4 )
  {
    v3 = WfpPoolAllocNonPaged(128, 1399875159, &v12);
    if ( v3 )
      goto LABEL_8;
    v4 = v12;
    memset(v12, 0, 0x80u);
    *((_QWORD *)Src + CurrentThreadCompartmentId) = v4;
  }
  *a1 = v4;
LABEL_8:
  v5 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v6 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v6 == 4 )
      *v6 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v5[1].L.ListHead.Alignment, &LockState);
LABEL_12:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
  {
    WPP_SF_Dqd(WPP_GLOBAL_Control->AttachedDevice, v7, v8, (unsigned int)CurrentThreadCompartmentId, a1, v3);
  }
  if ( v3 )
    WfpReportError(v3, "KfdGetBatchUpdateContext");
  return v3;
}

```

## disassembly

```asm
0x14000c4e0  push    rbx
0x14000c4e2  sub     rsp, 50h
0x14000c4e6  xor     eax, eax
0x14000c4e8  mov     [rsp+58h+arg_18], rsi
0x14000c4ed  mov     [rsp+58h+var_18], r12
0x14000c4f2  xor     r12d, r12d
0x14000c4f5  mov     [rsp+58h+var_28], r15
0x14000c4fa  mov     r15, rcx
0x14000c4fd  mov     [rsp+58h+arg_8], r12
0x14000c502  mov     [rcx], r12
0x14000c505  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x14000c50a  mov     [rsp+58h+LockState.Flags], al
0x14000c50e  call    NdisGetCurrentThreadCompartmentId
0x14000c513  mov     rcx, cs:gWfpGlobal
0x14000c51a  lea     rdx, [rsp+58h+LockState]
0x14000c51f  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000c523  mov     esi, eax
0x14000c525  mov     ebx, r12d
0x14000c528  call    WfpAcquireFastWriteLock
0x14000c52d  mov     rcx, cs:gWfpGlobal
0x14000c534  mov     edx, [rcx+0C0h]
0x14000c53a  cmp     edx, 2
0x14000c53d  jnz     short loc_14000C563
0x14000c53f  mov     r9d, 1
0x14000c545  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x14000c54c  mov     r8d, 0C0000001h
0x14000c552  call    WfpReportSysErrorAsNtStatus
0x14000c557  mov     rbx, rax
0x14000c55a  test    rax, rax
0x14000c55d  jnz     loc_14000C6E1
0x14000c563  cmp     esi, cs:gBatchUpdates
0x14000c569  mov     [rsp+58h+arg_10], rbp
0x14000c56e  mov     [rsp+58h+var_10], rdi
0x14000c573  jnb     loc_14000C67C
0x14000c579  mov     rax, cs:Src
0x14000c580  mov     [rsp+58h+var_20], r14
0x14000c585  lea     r14, ds:0[rsi*8]
0x14000c58d  mov     rdi, [r14+rax]
0x14000c591  mov     [rsp+58h+arg_8], rdi
0x14000c596  test    rdi, rdi
0x14000c599  jnz     short loc_14000C5D7
0x14000c59b  lea     r8, [rsp+58h+arg_8]
0x14000c5a0  mov     edx, 53706657h
0x14000c5a5  mov     ecx, 80h
0x14000c5aa  call    WfpPoolAllocNonPaged
0x14000c5af  mov     rbx, rax
0x14000c5b2  test    rax, rax
0x14000c5b5  jnz     short loc_14000C5DA
0x14000c5b7  mov     rdi, [rsp+58h+arg_8]
0x14000c5bc  xor     edx, edx; Val
0x14000c5be  mov     rcx, rdi; void *
0x14000c5c1  mov     r8d, 80h; Size
0x14000c5c7  call    memset
0x14000c5cc  mov     rax, cs:Src
0x14000c5d3  mov     [r14+rax], rdi
0x14000c5d7  mov     [r15], rdi
0x14000c5da  mov     r14, [rsp+58h+var_20]
0x14000c5df  cmp     cs:gWfpPerProContext, r12
0x14000c5e6  mov     rdi, cs:gWfpGlobal
0x14000c5ed  mov     rbp, [rsp+58h+arg_10]
0x14000c5f2  jz      short loc_14000C61B
0x14000c5f4  xor     ecx, ecx; ProcNumber
0x14000c5f6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000c5fd  nop     dword ptr [rax+rax+00h]
0x14000c602  imul    eax, cs:gWfpPerProContextSize
0x14000c609  mov     ecx, eax
0x14000c60b  mov     rax, cs:gWfpPerProContext
0x14000c612  mov     rdx, [rcx+rax]
0x14000c616  cmp     dword ptr [rdx], 4
0x14000c619  jz      short loc_14000C677
0x14000c61b  mov     rcx, [rdi+80h]; Lock
0x14000c622  lea     rdx, [rsp+58h+LockState]; LockState
0x14000c627  call    cs:__imp_NdisReleaseRWLock
0x14000c62e  nop     dword ptr [rax+rax+00h]
0x14000c633  mov     rdi, [rsp+58h+var_10]
0x14000c638  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c63f  lea     rax, WPP_GLOBAL_Control
0x14000c646  mov     r12, [rsp+58h+var_18]
0x14000c64b  cmp     rcx, rax
0x14000c64e  jz      short loc_14000C65A
0x14000c650  cmp     byte ptr [rcx+29h], 5
0x14000c654  jnb     loc_14000C70A
0x14000c65a  mov     r15, [rsp+58h+var_28]
0x14000c65f  mov     rsi, [rsp+58h+arg_18]
0x14000c664  test    rbx, rbx
0x14000c667  jnz     loc_14000C731
0x14000c66d  mov     rax, rbx
0x14000c670  add     rsp, 50h
0x14000c674  pop     rbx
0x14000c675  retn
0x14000c677  mov     [rdx], r12d
0x14000c67a  jmp     short loc_14000C61B
0x14000c67c  lea     ebp, [rsi+5]
0x14000c67f  mov     edx, 53706657h
0x14000c684  mov     edi, ebp
0x14000c686  lea     r8, [rsp+58h+arg_8]
0x14000c68b  shl     rdi, 3
0x14000c68f  mov     rcx, rdi
0x14000c692  call    WfpPoolAllocNonPaged
0x14000c697  mov     rbx, rax
0x14000c69a  test    rax, rax
0x14000c69d  jnz     loc_14000C5DF
0x14000c6a3  mov     r8, rdi; Size
0x14000c6a6  xor     edx, edx; Val
0x14000c6a8  mov     rdi, [rsp+58h+arg_8]
0x14000c6ad  mov     rcx, rdi; void *
0x14000c6b0  call    memset
0x14000c6b5  mov     r8d, cs:gBatchUpdates
0x14000c6bc  mov     rcx, rdi; void *
0x14000c6bf  mov     rdx, cs:Src; Src
0x14000c6c6  shl     r8, 3; Size
0x14000c6ca  call    memmove
0x14000c6cf  mov     cs:Src, rdi
0x14000c6d6  mov     cs:gBatchUpdates, ebp
0x14000c6dc  jmp     loc_14000C579
0x14000c6e1  mov     rcx, cs:gWfpGlobal
0x14000c6e8  lea     rdx, [rsp+58h+LockState]
0x14000c6ed  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000c6f1  call    WfpReleaseFastWriteLock
0x14000c6f6  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x14000c6fd  mov     rcx, rbx
0x14000c700  call    WfpReportError
0x14000c705  jmp     loc_14000C638
0x14000c70a  test    dword ptr [rcx+2Ch], 2000h
0x14000c711  jz      loc_14000C65A
0x14000c717  mov     rcx, [rcx+18h]
0x14000c71b  mov     r9d, esi
0x14000c71e  mov     [rsp+58h+var_30], ebx
0x14000c722  mov     [rsp+58h+var_38], r15
0x14000c727  call    WPP_SF_Dqd
0x14000c72c  jmp     loc_14000C65A
0x14000c731  lea     rdx, aKfdgetbatchupd; "KfdGetBatchUpdateContext"
0x14000c738  mov     rcx, rbx
0x14000c73b  call    WfpReportError
0x14000c740  jmp     loc_14000C66D
```
