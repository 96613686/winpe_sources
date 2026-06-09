# SmbCeDataReadyInd

- ea: `0x14000c270`
- end: `0x14000c68b`
- name: `SmbCeDataReadyInd`
- size: `1051`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140011910`
- `0x14001a950`

## callees

- `0x1400060bc`
- `0x140006680`
- `0x1400093a0`
- `0x140009fc0`
- `0x14000c030`
- `0x14000c270`
- `0x14000c6a0`
- `0x14000d300`
- `0x14000d910`
- `0x14000df60`
- `0x14000df90`
- `0x140014370`
- `0x1400147b0`
- `0x1400148f0`
- `0x1400149d0`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c2e5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c2e5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c4e8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c4e8`
- `ntoskrnl!IofCompleteRequest` at `0x14000c67a`
- `ntoskrnl!IofCompleteRequest` at `0x14000c67a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c328`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c3f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c328`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c3f9`
- `ntoskrnl!KeBugCheckEx` at `0x14000c668`
- `ntoskrnl!KeBugCheckEx` at `0x14000c668`
- `rdbss!RxPostToWorkerThread` at `0x14000c548`
- `rdbss!RxPostToWorkerThread` at `0x14000c548`

## pseudocode

```c
__int64 __fastcall SmbCeDataReadyInd(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  ULONG_PTR pContext; // rbx
  bool v5; // r12
  IRP *v6; // r15
  unsigned int v7; // ebp
  __int64 v10; // rsi
  __int64 v11; // r14
  __int64 v12; // rax
  unsigned int v13; // r14d
  bool v14; // r9
  int v16; // eax
  __int64 v17; // rsi
  struct _RDBSS_DEVICE_OBJECT *v18; // rdi
  __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rax
  __int64 (__fastcall *v22)(ULONG_PTR); // rax
  __int64 v23; // rax

  pContext = *(_QWORD *)(a2 + 56);
  v5 = 0;
  v6 = 0;
  v7 = a4;
  v10 = *(_QWORD *)(pContext + 56);
  v11 = *(_QWORD *)(pContext + 72);
  if ( (Microsoft_Windows_SMBClientEnableBits & 4) != 0 )
    McTemplateK0qp_EtwWriteTransfer(
      a1,
      &SmbDataReady,
      pContext + 312,
      a4,
      *(_QWORD *)(*(_QWORD *)(pContext + 96) + 392LL));
  v12 = *(_QWORD *)(v11 + 56);
  if ( v12 && (v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(v12 + 888))(a2, v7, a3), v16 < 0) )
  {
    v13 = v16;
  }
  else
  {
    v13 = v7;
    if ( !v7 )
      goto LABEL_5;
    v16 = v7;
    if ( v7 == 259 )
      goto LABEL_5;
  }
  _InterlockedExchange64((volatile __int64 *)(a2 + 48), (unsigned int)v16);
  SmbCeUpdateExchangeHistory(*(_QWORD *)(a2 + 56), (unsigned int)v16);
LABEL_5:
  if ( v10 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 4));
    *(_BYTE *)(v10 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 8));
  }
  else
  {
    SmbCeAcquireExchangeLock(pContext);
  }
  if ( !*(_BYTE *)(a2 + 87) )
    __int2c();
  *(_BYTE *)(a2 + 87) = 0;
  if ( *(_QWORD *)(*(_QWORD *)(pContext + 232) + 16LL) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(pContext + 36));
    if ( v10 )
    {
      SmbCeReleaseCompoundingKeyLock(v10);
      (*(void (__fastcall **)(ULONG_PTR, __int64, _QWORD, _QWORD))(*(_QWORD *)(pContext + 232) + 16LL))(
        pContext,
        a2,
        a3,
        v13);
      SmbCeAcquireCompoundingKeyLock(v10);
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(pContext + 24), *(_BYTE *)(pContext + 32));
      SmbCeDereferenceExchange((PVOID)pContext);
      (*(void (__fastcall **)(ULONG_PTR, __int64, _QWORD, _QWORD))(*(_QWORD *)(pContext + 232) + 16LL))(
        pContext,
        a2,
        a3,
        v13);
      SmbCeAcquireExchangeLock(pContext);
    }
    v14 = _InterlockedAdd((volatile signed __int32 *)(pContext + 36), 0xFFFFFFFF) == 0;
  }
  else
  {
    v14 = 1;
  }
  if ( *(_QWORD *)(a2 + 840) )
    *(_QWORD *)(a1 + 312) = ((MEMORY[0xFFFFF78000000008] - *(_QWORD *)(a2 + 840)) / 0xAuLL
                           + *(_QWORD *)(a1 + 312) * *(unsigned int *)(*(_QWORD *)(a1 + 512) + 80LL))
                          / (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 512) + 80LL) + 1);
  if ( !v7 )
    *(_DWORD *)(a2 + 4) |= 0x400u;
  if ( v14 )
  {
    if ( (unsigned __int8)SmbCepCheckExchangeForDeferredAbortOrIfFinalizable(pContext) )
    {
      v6 = (IRP *)SmbCepTryTurboCompleteExchangeLite(pContext);
      if ( !v6 )
        v5 = (unsigned int)SmbCepCompleteExchangeLiteEx((char *)pContext, (char *)(v10 == 0)) == -1073741802;
    }
  }
  if ( v10 )
  {
    SmbCeReleaseCompoundingKeyLock(v10);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(pContext + 24), *(_BYTE *)(pContext + 32));
    SmbCeDereferenceExchange((PVOID)pContext);
  }
  if ( v5 )
  {
    v17 = *(_QWORD *)(pContext + 72);
    v18 = *(struct _RDBSS_DEVICE_OBJECT **)(v17 + 24);
    if ( KeGetCurrentIrql() >= 2u )
    {
      v20 = 0;
      if ( (*(_DWORD *)(pContext + 68) & 0x40000) == 0 )
        goto LABEL_35;
    }
    if ( (v21 = *(_QWORD *)(v17 + 56)) != 0
      && (v22 = *(__int64 (__fastcall **)(ULONG_PTR))(v21 + 912)) != 0
      && (v20 = v22(pContext), v20 == -1069481981)
      || (v23 = *(_QWORD *)(pContext + 232),
          *(_QWORD *)(pContext + 208) = 0,
          *(_DWORD *)(pContext + 40) = 8,
          v20 = (*(__int64 (__fastcall **)(ULONG_PTR))(v23 + 32))(pContext),
          v20 == -1069481981) )
    {
LABEL_35:
      if ( (*(_DWORD *)(pContext + 68) & 1) != 0 )
        KeBugCheckEx(0x27u, 0x43584D5Fu, pContext, v20, 0);
      LOBYTE(v19) = 20;
      RDR_PERF_ENTER(pContext + 512, v19);
      SmbCeIncrementTeardownOpCounter(v18, pContext, 7);
      RxPostToWorkerThread(
        v18,
        NormalWorkQueue,
        (PRX_WORK_QUEUE_ITEM)(pContext + 240),
        SmbCepFinalizeExchangeWorker,
        (PVOID)pContext);
    }
    else
    {
      RDR_PERF_EXIT(pContext + 512);
      RDR_PERF_OUTPUT_ETW(pContext + 512);
      RDR_PERF_FREE(pContext + 512);
      SmbCeDereferenceExchange((PVOID)pContext);
    }
  }
  if ( v6 )
    IofCompleteRequest(v6, 1);
  return 0;
}

```

## disassembly

```asm
0x14000c270  mov     [rsp+arg_10], rbx
0x14000c275  mov     [rsp+arg_0], rcx
0x14000c27a  push    rbp
0x14000c27b  push    rsi
0x14000c27c  push    rdi
0x14000c27d  push    r12
0x14000c27f  push    r13
0x14000c281  push    r14
0x14000c283  push    r15
0x14000c285  sub     rsp, 30h
0x14000c289  mov     rbx, [rdx+38h]
0x14000c28d  xor     r12b, r12b
0x14000c290  xor     r15d, r15d
0x14000c293  mov     ebp, r9d
0x14000c296  test    cs:Microsoft_Windows_SMBClientEnableBits, 4
0x14000c29d  mov     r13d, r8d
0x14000c2a0  mov     rdi, rdx
0x14000c2a3  mov     rsi, [rbx+38h]
0x14000c2a7  mov     r14, [rbx+48h]
0x14000c2ab  jnz     loc_14000C5E2
0x14000c2b1  mov     rax, [r14+38h]
0x14000c2b5  test    rsi, rsi
0x14000c2b8  setz    [rsp+68h+arg_18]
0x14000c2c0  test    rax, rax
0x14000c2c3  jnz     loc_14000C447
0x14000c2c9  mov     r14d, ebp
0x14000c2cc  test    ebp, ebp
0x14000c2ce  jnz     loc_14000C468
0x14000c2d4  test    rsi, rsi
0x14000c2d7  jz      loc_14000C43A
0x14000c2dd  lock inc dword ptr [rsi+4]
0x14000c2e1  lea     rcx, [rsi+8]; SpinLock
0x14000c2e5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c2ec  nop     dword ptr [rax+rax+00h]
0x14000c2f1  mov     [rsi+10h], al
0x14000c2f4  cmp     [rdi+57h], r12b
0x14000c2f8  jbe     loc_14000C60A
0x14000c2fe  mov     [rdi+57h], r12b
0x14000c302  mov     rax, [rbx+0E8h]
0x14000c309  cmp     [rax+10h], r15
0x14000c30d  jz      loc_14000C4D2
0x14000c313  lock inc dword ptr [rbx+24h]
0x14000c317  test    rsi, rsi
0x14000c31a  jnz     loc_14000C611
0x14000c320  movzx   edx, byte ptr [rbx+20h]; NewIrql
0x14000c324  lea     rcx, [rbx+18h]; SpinLock
0x14000c328  call    cs:__imp_KeReleaseSpinLock
0x14000c32f  nop     dword ptr [rax+rax+00h]
0x14000c334  mov     rcx, rbx; pContext
0x14000c337  call    SmbCeDereferenceExchange
0x14000c33c  mov     rax, [rbx+0E8h]
0x14000c343  mov     r9d, r14d
0x14000c346  mov     r8d, r13d
0x14000c349  mov     rdx, rdi
0x14000c34c  mov     rcx, rbx
0x14000c34f  mov     rax, [rax+10h]
0x14000c353  call    _guard_dispatch_icall
0x14000c358  mov     rcx, rbx
0x14000c35b  call    SmbCeAcquireExchangeLock
0x14000c360  lock add dword ptr [rbx+24h], 0FFFFFFFFh
0x14000c365  movzx   eax, r12b
0x14000c369  mov     r14d, 1
0x14000c36f  movzx   r9d, al
0x14000c373  cmovz   r9d, r14d
0x14000c377  cmp     [rdi+348h], r15
0x14000c37e  jz      short loc_14000C3D4
0x14000c380  mov     r10, [rsp+68h+arg_0]
0x14000c385  mov     rcx, 0FFFFF78000000008h
0x14000c38f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000c399  mov     rcx, [rcx]
0x14000c39c  sub     rcx, [rdi+348h]
0x14000c3a3  mul     rcx
0x14000c3a6  mov     rax, [r10+200h]
0x14000c3ad  shr     rdx, 3
0x14000c3b1  mov     eax, [rax+50h]
0x14000c3b4  mov     r8d, eax
0x14000c3b7  imul    r8, [r10+138h]
0x14000c3bf  lea     ecx, [rax+1]
0x14000c3c2  add     r8, rdx
0x14000c3c5  xor     edx, edx
0x14000c3c7  mov     rax, r8
0x14000c3ca  div     rcx
0x14000c3cd  mov     [r10+138h], rax
0x14000c3d4  test    ebp, ebp
0x14000c3d6  jnz     short loc_14000C3DF
0x14000c3d8  or      dword ptr [rdi+4], 400h
0x14000c3df  test    r9b, r9b
0x14000c3e2  jnz     loc_14000C48C
0x14000c3e8  test    rsi, rsi
0x14000c3eb  jnz     loc_14000C642
0x14000c3f1  movzx   edx, byte ptr [rbx+20h]; NewIrql
0x14000c3f5  lea     rcx, [rbx+18h]; SpinLock
0x14000c3f9  call    cs:__imp_KeReleaseSpinLock
0x14000c400  nop     dword ptr [rax+rax+00h]
0x14000c405  mov     rcx, rbx; pContext
0x14000c408  call    SmbCeDereferenceExchange
0x14000c40d  test    r12b, r12b
0x14000c410  jnz     loc_14000C4E0
0x14000c416  test    r15, r15
0x14000c419  jnz     loc_14000C675
0x14000c41f  mov     rbx, [rsp+68h+arg_10]
0x14000c427  xor     eax, eax
0x14000c429  add     rsp, 30h
0x14000c42d  pop     r15
0x14000c42f  pop     r14
0x14000c431  pop     r13
0x14000c433  pop     r12
0x14000c435  pop     rdi
0x14000c436  pop     rsi
0x14000c437  pop     rbp
0x14000c438  retn
0x14000c43a  mov     rcx, rbx
0x14000c43d  call    SmbCeAcquireExchangeLock
0x14000c442  jmp     loc_14000C2F4
0x14000c447  mov     rax, [rax+378h]
0x14000c44e  mov     r8d, r13d
0x14000c451  mov     edx, ebp
0x14000c453  mov     rcx, rdi
0x14000c456  call    _guard_dispatch_icall
0x14000c45b  test    eax, eax
0x14000c45d  jns     loc_14000C2C9
0x14000c463  mov     r14d, eax
0x14000c466  jmp     short loc_14000C476
0x14000c468  mov     eax, ebp
0x14000c46a  cmp     ebp, 103h
0x14000c470  jz      loc_14000C2D4
0x14000c476  mov     edx, eax
0x14000c478  mov     eax, eax
0x14000c47a  xchg    rax, [rdi+30h]
0x14000c47e  mov     rcx, [rdi+38h]
0x14000c482  call    SmbCeUpdateExchangeHistory
0x14000c487  jmp     loc_14000C2D4
0x14000c48c  mov     rcx, rbx
0x14000c48f  call    SmbCepCheckExchangeForDeferredAbortOrIfFinalizable
0x14000c494  test    al, al
0x14000c496  jz      loc_14000C3E8
0x14000c49c  mov     rcx, rbx
0x14000c49f  call    SmbCepTryTurboCompleteExchangeLite
0x14000c4a4  mov     r15, rax
0x14000c4a7  test    rax, rax
0x14000c4aa  jnz     loc_14000C3E8
0x14000c4b0  movzx   edx, [rsp+68h+arg_18]
0x14000c4b8  mov     rcx, rbx; pContext
0x14000c4bb  call    SmbCepCompleteExchangeLiteEx
0x14000c4c0  cmp     eax, 0C0000016h
0x14000c4c5  movzx   r12d, r12b
0x14000c4c9  cmovz   r12d, r14d
0x14000c4cd  jmp     loc_14000C3E8
0x14000c4d2  mov     r9b, 1
0x14000c4d5  mov     r14d, 1
0x14000c4db  jmp     loc_14000C377
0x14000c4e0  mov     rsi, [rbx+48h]
0x14000c4e4  mov     rdi, [rsi+18h]
0x14000c4e8  call    cs:__imp_KeGetCurrentIrql
0x14000c4ef  nop     dword ptr [rax+rax+00h]
0x14000c4f4  cmp     al, 2
0x14000c4f6  jb      short loc_14000C559
0x14000c4f8  mov     eax, [rbx+44h]
0x14000c4fb  xor     ecx, ecx
0x14000c4fd  bt      eax, 12h
0x14000c501  jb      short loc_14000C559
0x14000c503  mov     eax, [rbx+44h]
0x14000c506  test    al, 1
0x14000c508  jnz     loc_14000C64F
0x14000c50e  lea     rcx, [rbx+200h]
0x14000c515  mov     dl, 14h
0x14000c517  call    RDR_PERF_ENTER
0x14000c51c  mov     r8d, 7
0x14000c522  mov     rdx, rbx
0x14000c525  mov     rcx, rdi
0x14000c528  call    SmbCeIncrementTeardownOpCounter
0x14000c52d  lea     r8, [rbx+0F0h]; pWorkQueueItem
0x14000c534  mov     [rsp+68h+pContext], rbx; pContext
0x14000c539  lea     r9, SmbCepFinalizeExchangeWorker; Routine
0x14000c540  mov     edx, 3; WorkQueueType
0x14000c545  mov     rcx, rdi; pMRxDeviceObject
0x14000c548  call    cs:__imp_RxPostToWorkerThread
0x14000c54f  nop     dword ptr [rax+rax+00h]
0x14000c554  jmp     loc_14000C416
0x14000c559  mov     rax, [rsi+38h]
0x14000c55d  test    rax, rax
0x14000c560  jz      short loc_14000C57F
0x14000c562  mov     rax, [rax+390h]
0x14000c569  test    rax, rax
0x14000c56c  jz      short loc_14000C57F
0x14000c56e  mov     rcx, rbx
0x14000c571  call    _guard_dispatch_icall
0x14000c576  mov     ecx, eax
0x14000c578  cmp     eax, 0C0410003h
0x14000c57d  jz      short loc_14000C503
0x14000c57f  mov     rax, [rbx+0E8h]
0x14000c586  mov     rcx, rbx
0x14000c589  mov     qword ptr [rbx+0D0h], 0
0x14000c594  mov     dword ptr [rbx+28h], 8
0x14000c59b  mov     rax, [rax+20h]
0x14000c59f  call    _guard_dispatch_icall
0x14000c5a4  mov     ecx, eax
0x14000c5a6  cmp     eax, 0C0410003h
0x14000c5ab  jz      loc_14000C503
0x14000c5b1  lea     rcx, [rbx+200h]
0x14000c5b8  call    RDR_PERF_EXIT
0x14000c5bd  lea     rcx, [rbx+200h]
0x14000c5c4  call    RDR_PERF_OUTPUT_ETW
0x14000c5c9  lea     rcx, [rbx+200h]
0x14000c5d0  call    RDR_PERF_FREE
0x14000c5d5  mov     rcx, rbx; pContext
0x14000c5d8  call    SmbCeDereferenceExchange
0x14000c5dd  jmp     loc_14000C416
0x14000c5e2  mov     rax, [rbx+60h]
0x14000c5e6  lea     r8, [rbx+138h]
0x14000c5ed  lea     rdx, SmbDataReady
0x14000c5f4  mov     rax, [rax+188h]
0x14000c5fb  mov     [rsp+68h+pContext], rax
0x14000c600  call    McTemplateK0qp_EtwWriteTransfer
0x14000c605  jmp     loc_14000C2B1
0x14000c60a  int     2Ch; Windows NT - assertion failure
0x14000c60c  jmp     loc_14000C2FE
0x14000c611  mov     rcx, rsi
0x14000c614  call    SmbCeReleaseCompoundingKeyLock
0x14000c619  mov     rax, [rbx+0E8h]
0x14000c620  mov     r9d, r14d
0x14000c623  mov     r8d, r13d
0x14000c626  mov     rdx, rdi
0x14000c629  mov     rcx, rbx
0x14000c62c  mov     rax, [rax+10h]
0x14000c630  call    _guard_dispatch_icall
0x14000c635  mov     rcx, rsi
0x14000c638  call    SmbCeAcquireCompoundingKeyLock
0x14000c63d  jmp     loc_14000C360
0x14000c642  mov     rcx, rsi
0x14000c645  call    SmbCeReleaseCompoundingKeyLock
0x14000c64a  jmp     loc_14000C40D
0x14000c64f  movsxd  r9, ecx; BugCheckParameter3
0x14000c652  mov     r8, rbx; BugCheckParameter2
0x14000c655  mov     ecx, 27h ; '''; BugCheckCode
0x14000c65a  mov     [rsp+68h+pContext], 0; BugCheckParameter4
0x14000c663  mov     edx, 43584D5Fh; BugCheckParameter1
0x14000c668  call    cs:__imp_KeBugCheckEx
0x14000c675  mov     dl, 1; PriorityBoost
0x14000c677  mov     rcx, r15; Irp
0x14000c67a  call    cs:__imp_IofCompleteRequest
0x14000c681  nop     dword ptr [rax+rax+00h]
0x14000c686  jmp     loc_14000C41F
```
