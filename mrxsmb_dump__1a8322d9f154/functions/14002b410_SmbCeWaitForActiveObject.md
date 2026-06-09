# SmbCeWaitForActiveObject

- ea: `0x14002b410`
- end: `0x14002b9d9`
- name: `SmbCeWaitForActiveObject`
- size: `1481`
- prototype: `__int64 __fastcall(PVOID pContext, PVOID)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000a260`

## callees

- `0x140005cd0`
- `0x140009360`
- `0x1400093a0`
- `0x14000a030`
- `0x14000c6a0`
- `0x14000da00`
- `0x14000df60`
- `0x14000e4c0`
- `0x14002b410`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b59d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b953`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b59d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b953`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b5d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b626`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b7b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b971`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b9aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b5d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b626`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b7b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b971`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b9aa`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002b56d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002b6aa`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002b93a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002b56d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002b6aa`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002b93a`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002b4f6`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002b4f6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002b506`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002b506`
- `rdbss!RxDiagnosticTrace` at `0x14002b67f`
- `rdbss!RxDiagnosticTrace` at `0x14002b6f5`
- `rdbss!RxDiagnosticTrace` at `0x14002b73b`
- `rdbss!RxDiagnosticTrace` at `0x14002b851`
- `rdbss!RxDiagnosticTrace` at `0x14002b8ab`
- `rdbss!RxDiagnosticTrace` at `0x14002b67f`
- `rdbss!RxDiagnosticTrace` at `0x14002b6f5`
- `rdbss!RxDiagnosticTrace` at `0x14002b73b`
- `rdbss!RxDiagnosticTrace` at `0x14002b851`
- `rdbss!RxDiagnosticTrace` at `0x14002b8ab`
- `rdbss!RxDispatchToWorkerThread` at `0x14002b768`
- `rdbss!RxDispatchToWorkerThread` at `0x14002b768`

## pseudocode

```c
__int64 __fastcall SmbCeWaitForActiveObject(unsigned __int16 *pContext, unsigned __int64 a2)
{
  int v3; // ebx
  __int64 v4; // rbp
  __int64 v6; // r15
  bool v7; // r13
  unsigned __int16 *v8; // rax
  unsigned int v9; // r14d
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rax
  __int64 v12; // rax
  char *v13; // r15
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  PRDBSS_DEVICE_OBJECT v18; // r13
  unsigned __int32 v19; // ebx
  unsigned __int32 v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned __int32 v24; // ebx
  __int64 v25; // r8
  NTSTATUS v26; // eax
  unsigned __int32 v27; // ebx
  unsigned __int32 v28; // ebx
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // rax
  KIRQL v32; // dl
  KIRQL v34; // [rsp+70h] [rbp+8h]
  PRDBSS_DEVICE_OBJECT pMRxDeviceObject; // [rsp+80h] [rbp+18h]

  v3 = *(_DWORD *)(a2 + 68) & 0x20;
  v4 = *(_QWORD *)(a2 + 56);
  v6 = *(_QWORD *)(*(_QWORD *)(a2 + 72) + 24LL);
  pMRxDeviceObject = (PRDBSS_DEVICE_OBJECT)v6;
  v7 = (*(_DWORD *)(a2 + 68) & 0x80u) != 0 || v4 && (*(_DWORD *)(v4 + 68) & 0x100) != 0;
  if ( *((_DWORD *)pContext + 3) || v3 )
  {
    v9 = -1073741300;
    v34 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920));
    *(_DWORD *)(v6 + 2352) = (unsigned int)PsGetCurrentThreadId();
    v12 = pContext[1];
    if ( (_WORD)v12 )
      v13 = (char *)pContext + v12;
    else
      v13 = 0;
    v14 = *((_DWORD *)pContext + 3);
    if ( !v14 )
    {
      if ( v3 )
      {
        v28 = _InterlockedExchange((volatile __int32 *)pContext + 3, 6);
        SmbEtwLogObjectStateTransition(pContext, v28, *((unsigned int *)pContext + 3), 3221225996LL);
        RxDiagnosticTrace(*((_QWORD *)pContext + 2), 1, "Transition %d --> %d", v28, *((_DWORD *)pContext + 3));
      }
      v29 = *(unsigned __int16 **)(a2 + 88);
      if ( pContext == v29 )
      {
        *(_DWORD *)(a2 + 112) = *((_DWORD *)v29 + 66);
        *(_DWORD *)(a2 + 108) = *(_DWORD *)(*(_QWORD *)(a2 + 80) + 264LL);
        *(_DWORD *)(a2 + 104) = *(_DWORD *)(*(_QWORD *)(a2 + 72) + 392LL);
      }
      else
      {
        v30 = *(unsigned __int16 **)(a2 + 80);
        if ( pContext == v30 )
        {
          *(_DWORD *)(a2 + 108) = *((_DWORD *)v30 + 66);
          *(_DWORD *)(a2 + 104) = *(_DWORD *)(*(_QWORD *)(a2 + 72) + 392LL);
        }
        else
        {
          v31 = *(unsigned __int16 **)(a2 + 72);
          if ( pContext == v31 )
            *(_DWORD *)(a2 + 104) = *((_DWORD *)v31 + 98);
        }
      }
      v9 = 0;
      LODWORD(pMRxDeviceObject[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Flink) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)&pMRxDeviceObject[1].SecurityDescriptor, v34);
      goto LABEL_54;
    }
    v15 = v14 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 && (v17 = v16 - 1) != 0 )
      {
        if ( v17 != 1 )
        {
LABEL_23:
          v18 = pMRxDeviceObject;
          goto LABEL_24;
        }
      }
      else if ( !v7 && !v3 )
      {
        goto LABEL_23;
      }
      if ( v4 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 4));
        *(_BYTE *)(v4 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 8));
        v9 = SmbCeSuspendExchangeLite(a2, v13 + 248, SmbCeCancelSuspendedExchange, 0);
        KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 8), *(_BYTE *)(v4 + 16));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 4), 0xFFFFFFFF) == 1 )
          SmbCsepFreeCompoundingKey((PVOID)v4);
      }
      else
      {
        SmbCeAcquireExchangeLock(a2);
        v9 = SmbCeSuspendExchangeLite(a2, v13 + 248, SmbCeCancelSuspendedExchange, 0);
        KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 24), *(_BYTE *)(a2 + 32));
        SmbCeDereferenceExchange(a2);
      }
      goto LABEL_23;
    }
    if ( !v7 )
      goto LABEL_23;
    if ( v3 )
    {
      v19 = _InterlockedExchange((volatile __int32 *)pContext + 3, 6);
      SmbEtwLogObjectStateTransition(pContext, v19, *((unsigned int *)pContext + 3), 3221225996LL);
      RxDiagnosticTrace(*((_QWORD *)pContext + 2), 1, "Transition %d --> %d", v19, *((_DWORD *)pContext + 3));
      v18 = pMRxDeviceObject;
LABEL_35:
      LODWORD(v18[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Flink) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)&v18[1].SecurityDescriptor, v34);
      return v9;
    }
    if ( *((int *)pContext + 1) >= 0 )
    {
      v24 = _InterlockedExchange((volatile __int32 *)pContext + 3, 3);
      SmbEtwLogObjectStateTransition(pContext, v24, *((unsigned int *)pContext + 3), 0);
      RxDiagnosticTrace(*((_QWORD *)pContext + 2), 1, "Transition %d --> %d", v24, *((_DWORD *)pContext + 3));
      v25 = *(_QWORD *)v13;
      v18 = pMRxDeviceObject;
      *((_QWORD *)v13 + 33) = a2;
      v26 = RxDispatchToWorkerThread(
              pMRxDeviceObject,
              NormalWorkQueue,
              *(PRX_WORKERTHREAD_ROUTINE *)(v25 + 24),
              pContext);
      v9 = v26;
      if ( v26 < 0 )
      {
        *((_QWORD *)v13 + 33) = 0;
        v27 = _InterlockedExchange((volatile __int32 *)pContext + 3, 1);
        SmbEtwLogObjectStateTransition(pContext, v27, *((unsigned int *)pContext + 3), (unsigned int)v26);
        RxDiagnosticTrace(*((_QWORD *)pContext + 2), 1, "Transition %d --> %d", v27, *((_DWORD *)pContext + 3));
        *((_DWORD *)v13 + 52) = v9;
        *((_DWORD *)v13 + 53) = 0;
        goto LABEL_35;
      }
      SmbCeReferenceExchange(a2);
    }
    else
    {
      v20 = _InterlockedExchange((volatile __int32 *)pContext + 3, 2);
      SmbEtwLogObjectStateTransition(pContext, v20, *((unsigned int *)pContext + 3), 3221225996LL);
      RxDiagnosticTrace(*((_QWORD *)pContext + 2), 1, "Transition %d --> %d", v20, *((_DWORD *)pContext + 3));
      v18 = pMRxDeviceObject;
    }
    if ( v4 )
    {
      SmbCeAcquireCompoundingKeyLock(v4, v21, v22, v23);
      v9 = SmbCeSuspendExchangeLite(a2, v13 + 248, SmbCeCancelSuspendedExchange, 0);
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 8), *(_BYTE *)(v4 + 16));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 4), 0xFFFFFFFF) == 1 )
        SmbCsepFreeCompoundingKey((PVOID)v4);
    }
    else
    {
      SmbCeAcquireExchangeLock(a2);
      v9 = SmbCeSuspendExchangeLite(a2, v13 + 248, SmbCeCancelSuspendedExchange, 0);
      SmbCeReleaseExchangeLock((PVOID)a2);
    }
LABEL_24:
    LODWORD(v18[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Flink) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)&v18[1].SecurityDescriptor, v34);
    if ( v9 )
      return v9;
    goto LABEL_54;
  }
  v8 = *(unsigned __int16 **)(a2 + 88);
  if ( pContext == v8 )
  {
    v9 = 0;
    *(_DWORD *)(a2 + 112) = *((_DWORD *)v8 + 66);
    *(_DWORD *)(a2 + 108) = *(_DWORD *)(*(_QWORD *)(a2 + 80) + 264LL);
    *(_DWORD *)(a2 + 104) = *(_DWORD *)(*(_QWORD *)(a2 + 72) + 392LL);
  }
  else
  {
    v10 = *(unsigned __int16 **)(a2 + 80);
    if ( pContext == v10 )
    {
      v9 = 0;
      *(_DWORD *)(a2 + 108) = *((_DWORD *)v10 + 66);
      *(_DWORD *)(a2 + 104) = *(_DWORD *)(*(_QWORD *)(a2 + 72) + 392LL);
    }
    else
    {
      v11 = *(unsigned __int16 **)(a2 + 72);
      if ( pContext == v11 )
        *(_DWORD *)(a2 + 104) = *((_DWORD *)v11 + 98);
      v9 = 0;
    }
  }
LABEL_54:
  if ( v4 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 4));
    *(_BYTE *)(v4 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 8));
    *(_DWORD *)(a2 + 40) = 4;
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 8), *(_BYTE *)(v4 + 16));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 4), 0xFFFFFFFF) == 1 )
      SmbCsepFreeCompoundingKey((PVOID)v4);
  }
  else
  {
    SmbCeAcquireExchangeLock(a2);
    v32 = *(_BYTE *)(a2 + 32);
    *(_DWORD *)(a2 + 40) = 4;
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 24), v32);
    SmbCeDereferenceExchange(a2);
  }
  return v9;
}

```

## disassembly

```asm
0x14002b410  push    rbx
0x14002b412  push    rbp
0x14002b413  push    rsi
0x14002b414  push    rdi
0x14002b415  push    r12
0x14002b417  push    r13
0x14002b419  push    r15
0x14002b41b  sub     rsp, 30h
0x14002b41f  mov     ebx, [rdx+44h]
0x14002b422  mov     rdi, rdx
0x14002b425  mov     rax, [rdx+48h]
0x14002b429  and     ebx, 20h
0x14002b42c  mov     rbp, [rdx+38h]
0x14002b430  mov     rsi, rcx
0x14002b433  mov     r15, [rax+18h]
0x14002b437  mov     eax, [rdx+44h]
0x14002b43a  mov     [rsp+68h+pMRxDeviceObject], r15
0x14002b442  test    al, al
0x14002b444  js      short loc_14002B459
0x14002b446  test    rbp, rbp
0x14002b449  jz      short loc_14002B454
0x14002b44b  test    dword ptr [rbp+44h], 100h
0x14002b452  jnz     short loc_14002B459
0x14002b454  xor     r13b, r13b
0x14002b457  jmp     short loc_14002B45C
0x14002b459  mov     r13b, 1
0x14002b45c  cmp     dword ptr [rcx+0Ch], 0
0x14002b460  mov     r12d, 0FFFFFFFFh
0x14002b466  mov     [rsp+68h+arg_18], r14
0x14002b46e  jnz     short loc_14002B4E9
0x14002b470  test    ebx, ebx
0x14002b472  jnz     short loc_14002B4E9
0x14002b474  mov     rax, [rdx+58h]
0x14002b478  cmp     rsi, rax
0x14002b47b  jnz     short loc_14002B4A8
0x14002b47d  mov     eax, [rax+108h]
0x14002b483  xor     r14d, r14d
0x14002b486  mov     [rdx+70h], eax
0x14002b489  mov     rax, [rdx+50h]
0x14002b48d  mov     ecx, [rax+108h]
0x14002b493  mov     [rdx+6Ch], ecx
0x14002b496  mov     rax, [rdx+48h]
0x14002b49a  mov     ecx, [rax+188h]
0x14002b4a0  mov     [rdx+68h], ecx
0x14002b4a3  jmp     loc_14002B946
0x14002b4a8  mov     rax, [rdx+50h]
0x14002b4ac  cmp     rsi, rax
0x14002b4af  jnz     short loc_14002B4CF
0x14002b4b1  mov     eax, [rax+108h]
0x14002b4b7  xor     r14d, r14d
0x14002b4ba  mov     [rdx+6Ch], eax
0x14002b4bd  mov     rax, [rdx+48h]
0x14002b4c1  mov     ecx, [rax+188h]
0x14002b4c7  mov     [rdx+68h], ecx
0x14002b4ca  jmp     loc_14002B946
0x14002b4cf  mov     rax, [rdx+48h]
0x14002b4d3  cmp     rsi, rax
0x14002b4d6  jnz     short loc_14002B4E1
0x14002b4d8  mov     eax, [rax+188h]
0x14002b4de  mov     [rdx+68h], eax
0x14002b4e1  xor     r14d, r14d
0x14002b4e4  jmp     loc_14002B946
0x14002b4e9  lea     rcx, [r15+780h]; SpinLock
0x14002b4f0  mov     r14d, 0C000020Ch
0x14002b4f6  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002b4fd  nop     dword ptr [rax+rax+00h]
0x14002b502  mov     [rsp+68h+arg_0], al
0x14002b506  call    cs:__imp_PsGetCurrentThreadId
0x14002b50d  nop     dword ptr [rax+rax+00h]
0x14002b512  mov     [r15+930h], eax
0x14002b519  movzx   eax, word ptr [rsi+2]
0x14002b51d  test    ax, ax
0x14002b520  jnz     short loc_14002B527
0x14002b522  xor     r15d, r15d
0x14002b525  jmp     short loc_14002B52B
0x14002b527  lea     r15, [rsi+rax]
0x14002b52b  mov     ecx, [rsi+0Ch]
0x14002b52e  test    ecx, ecx
0x14002b530  jz      loc_14002B874
0x14002b536  sub     ecx, 1
0x14002b539  jz      loc_14002B63F
0x14002b53f  sub     ecx, 1
0x14002b542  jz      short loc_14002B587
0x14002b544  sub     ecx, 1
0x14002b547  jz      short loc_14002B587
0x14002b549  cmp     ecx, 1
0x14002b54c  jz      short loc_14002B590
0x14002b54e  mov     r13, [rsp+68h+pMRxDeviceObject]
0x14002b556  movzx   edx, [rsp+68h+arg_0]; OldIrql
0x14002b55b  lea     rcx, [r13+780h]; SpinLock
0x14002b562  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14002b56d  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002b574  nop     dword ptr [rax+rax+00h]
0x14002b579  test    r14d, r14d
0x14002b57c  jz      loc_14002B946
0x14002b582  jmp     loc_14002B9BE
0x14002b587  test    r13b, r13b
0x14002b58a  jnz     short loc_14002B590
0x14002b58c  test    ebx, ebx
0x14002b58e  jz      short loc_14002B54E
0x14002b590  test    rbp, rbp
0x14002b593  jz      short loc_14002B5FA
0x14002b595  lock inc dword ptr [rbp+4]
0x14002b599  lea     rcx, [rbp+8]; SpinLock
0x14002b59d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002b5a4  nop     dword ptr [rax+rax+00h]
0x14002b5a9  lea     rdx, [r15+0F8h]
0x14002b5b0  xor     r9d, r9d
0x14002b5b3  lea     r8, SmbCeCancelSuspendedExchange
0x14002b5ba  mov     [rbp+10h], al
0x14002b5bd  mov     rcx, rdi
0x14002b5c0  call    SmbCeSuspendExchangeLite
0x14002b5c5  movzx   edx, byte ptr [rbp+10h]; NewIrql
0x14002b5c9  lea     rcx, [rbp+8]; SpinLock
0x14002b5cd  mov     r14d, eax
0x14002b5d0  call    cs:__imp_KeReleaseSpinLock
0x14002b5d7  nop     dword ptr [rax+rax+00h]
0x14002b5dc  mov     eax, r12d
0x14002b5df  lock xadd [rbp+4], eax
0x14002b5e4  cmp     eax, 1
0x14002b5e7  jnz     loc_14002B54E
0x14002b5ed  mov     rcx, rbp; P
0x14002b5f0  call    SmbCsepFreeCompoundingKey
0x14002b5f5  jmp     loc_14002B54E
0x14002b5fa  mov     rcx, rdi
0x14002b5fd  call    SmbCeAcquireExchangeLock
0x14002b602  lea     rdx, [r15+0F8h]
0x14002b609  xor     r9d, r9d
0x14002b60c  lea     r8, SmbCeCancelSuspendedExchange
0x14002b613  mov     rcx, rdi
0x14002b616  call    SmbCeSuspendExchangeLite
0x14002b61b  movzx   edx, byte ptr [rdi+20h]; NewIrql
0x14002b61f  lea     rcx, [rdi+18h]; SpinLock
0x14002b623  mov     r14d, eax
0x14002b626  call    cs:__imp_KeReleaseSpinLock
0x14002b62d  nop     dword ptr [rax+rax+00h]
0x14002b632  mov     rcx, rdi; pContext
0x14002b635  call    SmbCeDereferenceExchange
0x14002b63a  jmp     loc_14002B54E
0x14002b63f  test    r13b, r13b
0x14002b642  jz      loc_14002B54E
0x14002b648  mov     rcx, rsi
0x14002b64b  test    ebx, ebx
0x14002b64d  jz      short loc_14002B6BB
0x14002b64f  mov     ebx, 6
0x14002b654  mov     r9d, r14d
0x14002b657  xchg    ebx, [rsi+0Ch]
0x14002b65a  mov     r8d, [rsi+0Ch]
0x14002b65e  mov     edx, ebx
0x14002b660  call    SmbEtwLogObjectStateTransition
0x14002b665  mov     edx, [rsi+0Ch]
0x14002b668  lea     r8, aTransitionDD; "Transition %d --> %d"
0x14002b66f  mov     rcx, [rsi+10h]
0x14002b673  mov     r9d, ebx
0x14002b676  mov     [rsp+68h+var_48], edx
0x14002b67a  mov     edx, 1
0x14002b67f  call    cs:__imp_RxDiagnosticTrace
0x14002b686  nop     dword ptr [rax+rax+00h]
0x14002b68b  mov     r13, [rsp+68h+pMRxDeviceObject]
0x14002b693  movzx   edx, [rsp+68h+arg_0]; OldIrql
0x14002b698  lea     rcx, [r13+780h]; SpinLock
0x14002b69f  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14002b6aa  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002b6b1  nop     dword ptr [rax+rax+00h]
0x14002b6b6  jmp     loc_14002B9BE
0x14002b6bb  mov     eax, [rsi+4]
0x14002b6be  shr     eax, 1Fh
0x14002b6c1  test    al, al
0x14002b6c3  jz      short loc_14002B70B
0x14002b6c5  mov     ebx, 2
0x14002b6ca  mov     r9d, r14d
0x14002b6cd  xchg    ebx, [rsi+0Ch]
0x14002b6d0  mov     r8d, [rsi+0Ch]
0x14002b6d4  mov     edx, ebx
0x14002b6d6  call    SmbEtwLogObjectStateTransition
0x14002b6db  mov     eax, [rsi+0Ch]
0x14002b6de  lea     r8, aTransitionDD; "Transition %d --> %d"
0x14002b6e5  mov     rcx, [rsi+10h]
0x14002b6e9  mov     r9d, ebx
0x14002b6ec  mov     edx, 1
0x14002b6f1  mov     [rsp+68h+var_48], eax
0x14002b6f5  call    cs:__imp_RxDiagnosticTrace
0x14002b6fc  nop     dword ptr [rax+rax+00h]
0x14002b701  mov     r13, [rsp+68h+pMRxDeviceObject]
0x14002b709  jmp     short loc_14002B787
0x14002b70b  mov     ebx, 3
0x14002b710  xor     r9d, r9d
0x14002b713  xchg    ebx, [rsi+0Ch]
0x14002b716  mov     r8d, [rsi+0Ch]
0x14002b71a  mov     edx, ebx
0x14002b71c  call    SmbEtwLogObjectStateTransition
0x14002b721  mov     eax, [rsi+0Ch]
0x14002b724  lea     r8, aTransitionDD; "Transition %d --> %d"
0x14002b72b  mov     rcx, [rsi+10h]
0x14002b72f  mov     r9d, ebx
0x14002b732  mov     edx, 1
0x14002b737  mov     [rsp+68h+var_48], eax
0x14002b73b  call    cs:__imp_RxDiagnosticTrace
0x14002b742  nop     dword ptr [rax+rax+00h]
0x14002b747  mov     r8, [r15]
0x14002b74a  mov     r9, rsi; pContext
0x14002b74d  mov     r13, [rsp+68h+pMRxDeviceObject]
0x14002b755  mov     edx, 3; WorkQueueType
0x14002b75a  mov     [r15+108h], rdi
0x14002b761  mov     rcx, r13; pMRxDeviceObject
0x14002b764  mov     r8, [r8+18h]; Routine
0x14002b768  call    cs:__imp_RxDispatchToWorkerThread
0x14002b76f  nop     dword ptr [rax+rax+00h]
0x14002b774  mov     r14d, eax
0x14002b777  test    eax, eax
0x14002b779  js      loc_14002B813
0x14002b77f  mov     rcx, rdi
0x14002b782  call    SmbCeReferenceExchange
0x14002b787  test    rbp, rbp
0x14002b78a  jz      short loc_14002B7E2
0x14002b78c  mov     rcx, rbp
0x14002b78f  call    SmbCeAcquireCompoundingKeyLock
0x14002b794  lea     rdx, [r15+0F8h]
0x14002b79b  xor     r9d, r9d
0x14002b79e  lea     r8, SmbCeCancelSuspendedExchange
0x14002b7a5  mov     rcx, rdi
0x14002b7a8  call    SmbCeSuspendExchangeLite
0x14002b7ad  movzx   edx, byte ptr [rbp+10h]; NewIrql
0x14002b7b1  lea     rcx, [rbp+8]; SpinLock
0x14002b7b5  mov     r14d, eax
0x14002b7b8  call    cs:__imp_KeReleaseSpinLock
0x14002b7bf  nop     dword ptr [rax+rax+00h]
0x14002b7c4  mov     eax, r12d
0x14002b7c7  lock xadd [rbp+4], eax
0x14002b7cc  cmp     eax, 1
0x14002b7cf  jnz     loc_14002B556
0x14002b7d5  mov     rcx, rbp; P
0x14002b7d8  call    SmbCsepFreeCompoundingKey
0x14002b7dd  jmp     loc_14002B556
0x14002b7e2  mov     rcx, rdi
0x14002b7e5  call    SmbCeAcquireExchangeLock
0x14002b7ea  lea     rdx, [r15+0F8h]
0x14002b7f1  xor     r9d, r9d
0x14002b7f4  lea     r8, SmbCeCancelSuspendedExchange
0x14002b7fb  mov     rcx, rdi
0x14002b7fe  call    SmbCeSuspendExchangeLite
0x14002b803  mov     rcx, rdi
0x14002b806  mov     r14d, eax
0x14002b809  call    SmbCeReleaseExchangeLock
0x14002b80e  jmp     loc_14002B556
0x14002b813  mov     qword ptr [r15+108h], 0
0x14002b81e  mov     ebx, 1
0x14002b823  xchg    ebx, [rsi+0Ch]
0x14002b826  mov     r8d, [rsi+0Ch]
0x14002b82a  mov     edx, ebx
0x14002b82c  mov     r9d, r14d
0x14002b82f  mov     rcx, rsi
0x14002b832  call    SmbEtwLogObjectStateTransition
0x14002b837  mov     eax, [rsi+0Ch]
0x14002b83a  lea     r8, aTransitionDD; "Transition %d --> %d"
0x14002b841  mov     rcx, [rsi+10h]
0x14002b845  mov     r9d, ebx
0x14002b848  mov     edx, 1
0x14002b84d  mov     [rsp+68h+var_48], eax
0x14002b851  call    cs:__imp_RxDiagnosticTrace
0x14002b858  nop     dword ptr [rax+rax+00h]
0x14002b85d  mov     [r15+0D0h], r14d
0x14002b864  mov     dword ptr [r15+0D4h], 0
0x14002b86f  jmp     loc_14002B693
0x14002b874  test    ebx, ebx
0x14002b876  jz      short loc_14002B8B7
0x14002b878  mov     ebx, 6
0x14002b87d  mov     r9d, r14d
0x14002b880  xchg    ebx, [rsi+0Ch]
0x14002b883  mov     r8d, [rsi+0Ch]
0x14002b887  mov     edx, ebx
0x14002b889  mov     rcx, rsi
0x14002b88c  call    SmbEtwLogObjectStateTransition
0x14002b891  mov     eax, [rsi+0Ch]
0x14002b894  lea     r8, aTransitionDD; "Transition %d --> %d"
0x14002b89b  mov     rcx, [rsi+10h]
0x14002b89f  mov     r9d, ebx
0x14002b8a2  mov     edx, 1
0x14002b8a7  mov     [rsp+68h+var_48], eax
0x14002b8ab  call    cs:__imp_RxDiagnosticTrace
0x14002b8b2  nop     dword ptr [rax+rax+00h]
0x14002b8b7  mov     rax, [rdi+58h]
0x14002b8bb  cmp     rsi, rax
0x14002b8be  jnz     short loc_14002B8E5
0x14002b8c0  mov     eax, [rax+108h]
0x14002b8c6  mov     [rdi+70h], eax
0x14002b8c9  mov     rax, [rdi+50h]
0x14002b8cd  mov     ecx, [rax+108h]
0x14002b8d3  mov     [rdi+6Ch], ecx
0x14002b8d6  mov     rax, [rdi+48h]
0x14002b8da  mov     ecx, [rax+188h]
0x14002b8e0  mov     [rdi+68h], ecx
0x14002b8e3  jmp     short loc_14002B918
0x14002b8e5  mov     rax, [rdi+50h]
0x14002b8e9  cmp     rsi, rax
0x14002b8ec  jnz     short loc_14002B906
0x14002b8ee  mov     eax, [rax+108h]
0x14002b8f4  mov     [rdi+6Ch], eax
0x14002b8f7  mov     rax, [rdi+48h]
0x14002b8fb  mov     ecx, [rax+188h]
  ... truncated ...
```
