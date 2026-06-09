# SmbCeSubmitTransactionRequest

- ea: `0x14004bce0`
- end: `0x14004bf88`
- name: `SmbCeSubmitTransactionRequest`
- size: `680`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14004b5f0`

## callees

- `0x1400054b0`
- `0x140009340`
- `0x1400098d0`
- `0x14004bce0`
- `0x14004bf90`
- `0x14004ccf0`
- `0x14004dd50`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14004beb2`
- `ntoskrnl!DbgPrint` at `0x14004bef8`
- `ntoskrnl!DbgPrint` at `0x14004bf66`
- `ntoskrnl!DbgPrint` at `0x14004beb2`
- `ntoskrnl!DbgPrint` at `0x14004bef8`
- `ntoskrnl!DbgPrint` at `0x14004bf66`
- `rdbss!RxPostToWorkerThread` at `0x14004bdd4`
- `rdbss!RxPostToWorkerThread` at `0x14004bdd4`
- `mrxsmb!MRxSmbDeviceObject` at `0x14004bdb2`

## pseudocode

```c
__int64 __fastcall SmbCeSubmitTransactionRequest(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rcx
  __int64 v10; // rax
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 result; // rax
  unsigned __int8 *pContext; // rdi
  __int64 v15; // r14
  unsigned int v16; // esi
  int v17; // eax
  PVOID v18; // [rsp+60h] [rbp+8h] BYREF

  v6 = *(_QWORD *)(a1 + 64);
  v18 = 0;
  if ( v6 )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL);
    if ( *(_WORD *)v10 != 0xEB12 )
      v10 = *(_QWORD *)(*(_QWORD *)(v6 + 32) + 40LL);
  }
  else
  {
    if ( *(_BYTE *)(a1 + 32) )
      goto LABEL_5;
    v10 = *(_QWORD *)(a1 + 656);
  }
  if ( !v10 )
  {
LABEL_5:
    LODWORD(v11) = 0;
    v12 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 120LL) + 32LL) + 32LL);
    goto LABEL_6;
  }
  v11 = *(_QWORD *)(v10 + 40);
  LODWORD(v12) = 0;
LABEL_6:
  result = SmbCepInitializeExchange((unsigned int)&v18, a1, v12, v11, 2, (__int64)&TransactExchangeDispatch);
  if ( !(_DWORD)result )
  {
    pContext = (unsigned __int8 *)v18;
    v15 = a5;
    v16 = SmbCeInitializeTransactExchange((_DWORD)v18, a1, a2, a3, a4, a5);
    if ( v16 )
    {
      *(_QWORD *)(a1 + 224) = 0;
      if ( (*((_DWORD *)pContext + 18) & 1) != 0 )
        SmbCeDissociateMidFromExchange(*((_QWORD *)pContext + 10), pContext);
      RxPostToWorkerThread(
        MRxSmbDeviceObject,
        NormalWorkQueue,
        (PRX_WORK_QUEUE_ITEM)(pContext + 176),
        SmbCeDiscardExchangeWorkerThreadRoutine,
        pContext);
      return v16;
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)pContext + 1);
      if ( SmbCeTraceExchangeReferenceCount )
        DbgPrint(
          "Reference Exchange %p Type(%ld) %s %ld %ld\n",
          pContext,
          *pContext,
          "SmbCeSubmitTransactionRequest",
          510,
          *((_DWORD *)pContext + 1));
      if ( _bittest16((const signed __int16 *)(a2 + 2), 8u) )
      {
        _InterlockedIncrement((volatile signed __int32 *)pContext + 1);
        if ( SmbCeTraceExchangeReferenceCount )
          DbgPrint(
            "Reference Exchange %p Type(%ld) %s %ld %ld\n",
            pContext,
            *pContext,
            "SmbCeSubmitTransactionRequest",
            514,
            *((_DWORD *)pContext + 1));
      }
      if ( _bittest16((const signed __int16 *)pContext + 255, 0xBu) )
        *((_DWORD *)pContext + 18) |= 0x40u;
      *(_QWORD *)v15 = pContext;
      *(_DWORD *)(v15 + 12) = 0;
      SmbCeIncrementPendingOperations(pContext, 1);
      v17 = SmbCeInitiateExchange(pContext);
      if ( v17 != 259 )
      {
        *((_DWORD *)pContext + 12) = v17;
        if ( !*((_DWORD *)pContext + 10) )
          *((_DWORD *)pContext + 10) = v17;
        if ( _bittest16((const signed __int16 *)(a2 + 2), 8u) )
        {
          *(_QWORD *)(a1 + 224) = 0;
          _InterlockedDecrement((volatile signed __int32 *)pContext + 1);
          if ( SmbCeTraceExchangeReferenceCount )
            DbgPrint(
              "Dereference Exchange %p Type(%ld) %s %ld %ld\n",
              pContext,
              *pContext,
              "SmbCeSubmitTransactionRequest",
              543,
              *((_DWORD *)pContext + 1));
        }
      }
      SmbCeDecrementPendingOperationsAndFinalize(pContext);
      return 259;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14004bce0  push    rbx
0x14004bce2  push    rbp
0x14004bce3  push    rsi
0x14004bce4  push    r12
0x14004bce6  push    r15
0x14004bce8  sub     rsp, 30h
0x14004bcec  xor     r12d, r12d
0x14004bcef  mov     rbx, rcx
0x14004bcf2  mov     rcx, [rcx+40h]
0x14004bcf6  mov     rsi, r9
0x14004bcf9  mov     [rsp+58h+arg_0], r12
0x14004bcfe  mov     r15, r8
0x14004bd01  mov     rbp, rdx
0x14004bd04  test    rcx, rcx
0x14004bd07  jz      loc_14004BE6B
0x14004bd0d  mov     rax, [rbx+48h]
0x14004bd11  mov     edx, 0EB12h
0x14004bd16  mov     rax, [rax+28h]
0x14004bd1a  cmp     [rax], dx
0x14004bd1d  jnz     loc_14004BE81
0x14004bd23  test    rax, rax
0x14004bd26  jnz     loc_14004BDF9
0x14004bd2c  mov     rax, [rbx+38h]
0x14004bd30  mov     r9, r12
0x14004bd33  mov     rcx, [rax+78h]
0x14004bd37  mov     rax, [rcx+20h]
0x14004bd3b  mov     r8, [rax+20h]
0x14004bd3f  lea     rax, TransactExchangeDispatch
0x14004bd46  mov     rdx, rbx
0x14004bd49  mov     [rsp+58h+var_30], rax
0x14004bd4e  lea     rcx, [rsp+58h+arg_0]
0x14004bd53  mov     dword ptr [rsp+58h+pContext], 2
0x14004bd5b  call    SmbCepInitializeExchange
0x14004bd60  test    eax, eax
0x14004bd62  jnz     loc_14004BDEC
0x14004bd68  mov     [rsp+58h+arg_8], rdi
0x14004bd6d  mov     r9, r15
0x14004bd70  mov     rdi, [rsp+58h+arg_0]
0x14004bd75  mov     r8, rbp
0x14004bd78  mov     [rsp+58h+arg_10], r14
0x14004bd7d  mov     rdx, rbx
0x14004bd80  mov     r14, [rsp+58h+arg_20]
0x14004bd88  mov     rcx, rdi
0x14004bd8b  mov     [rsp+58h+var_30], r14
0x14004bd90  mov     [rsp+58h+pContext], rsi
0x14004bd95  call    SmbCeInitializeTransactExchange
0x14004bd9a  mov     esi, eax
0x14004bd9c  test    eax, eax
0x14004bd9e  jz      short loc_14004BE05
0x14004bda0  mov     [rbx+0E0h], r12
0x14004bda7  mov     eax, [rdi+48h]
0x14004bdaa  test    al, 1
0x14004bdac  jnz     loc_14004BF77
0x14004bdb2  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14004bdb9  lea     r8, [rdi+0B0h]; pWorkQueueItem
0x14004bdc0  lea     r9, SmbCeDiscardExchangeWorkerThreadRoutine; Routine
0x14004bdc7  mov     [rsp+58h+pContext], rdi; pContext
0x14004bdcc  mov     edx, 3; WorkQueueType
0x14004bdd1  mov     rcx, [rcx]; pMRxDeviceObject
0x14004bdd4  call    cs:__imp_RxPostToWorkerThread
0x14004bddb  nop     dword ptr [rax+rax+00h]
0x14004bde0  mov     eax, esi
0x14004bde2  mov     rdi, [rsp+58h+arg_8]
0x14004bde7  mov     r14, [rsp+58h+arg_10]
0x14004bdec  add     rsp, 30h
0x14004bdf0  pop     r15
0x14004bdf2  pop     r12
0x14004bdf4  pop     rsi
0x14004bdf5  pop     rbp
0x14004bdf6  pop     rbx
0x14004bdf7  retn
0x14004bdf9  mov     r9, [rax+28h]
0x14004bdfd  mov     r8, r12
0x14004be00  jmp     loc_14004BD3F
0x14004be05  lock inc dword ptr [rdi+4]
0x14004be09  cmp     cs:SmbCeTraceExchangeReferenceCount, r12d
0x14004be10  jnz     short loc_14004BE8E
0x14004be12  bt      word ptr [rbp+2], 8
0x14004be18  jb      loc_14004BEC3
0x14004be1e  bt      word ptr [rdi+1FEh], 0Bh
0x14004be27  jb      loc_14004BF09
0x14004be2d  mov     edx, 1
0x14004be32  mov     [r14], rdi
0x14004be35  mov     rcx, rdi
0x14004be38  mov     [r14+0Ch], r12d
0x14004be3c  call    SmbCeIncrementPendingOperations
0x14004be41  mov     rcx, rdi
0x14004be44  call    SmbCeInitiateExchange
0x14004be49  cmp     eax, 103h
0x14004be4e  jnz     loc_14004BF12
0x14004be54  mov     edx, 1
0x14004be59  mov     rcx, rdi; pContext
0x14004be5c  call    SmbCeDecrementPendingOperationsAndFinalize
0x14004be61  mov     eax, 103h
0x14004be66  jmp     loc_14004BDE2
0x14004be6b  cmp     [rbx+20h], r12b
0x14004be6f  jnz     loc_14004BD2C
0x14004be75  mov     rax, [rbx+290h]
0x14004be7c  jmp     loc_14004BD23
0x14004be81  mov     rax, [rcx+20h]
0x14004be85  mov     rax, [rax+28h]
0x14004be89  jmp     loc_14004BD23
0x14004be8e  mov     eax, [rdi+4]
0x14004be91  lea     r9, aSmbcesubmittra; "SmbCeSubmitTransactionRequest"
0x14004be98  movzx   r8d, byte ptr [rdi]
0x14004be9c  lea     rcx, aReferenceExcha; "Reference Exchange %p Type(%ld) %s %ld "...
0x14004bea3  mov     dword ptr [rsp+58h+var_30], eax
0x14004bea7  mov     rdx, rdi
0x14004beaa  mov     dword ptr [rsp+58h+pContext], 1FEh
0x14004beb2  call    cs:__imp_DbgPrint
0x14004beb9  nop     dword ptr [rax+rax+00h]
0x14004bebe  jmp     loc_14004BE12
0x14004bec3  lock inc dword ptr [rdi+4]
0x14004bec7  cmp     cs:SmbCeTraceExchangeReferenceCount, r12d
0x14004bece  jz      loc_14004BE1E
0x14004bed4  mov     eax, [rdi+4]
0x14004bed7  lea     r9, aSmbcesubmittra; "SmbCeSubmitTransactionRequest"
0x14004bede  movzx   r8d, byte ptr [rdi]
0x14004bee2  lea     rcx, aReferenceExcha; "Reference Exchange %p Type(%ld) %s %ld "...
0x14004bee9  mov     dword ptr [rsp+58h+var_30], eax
0x14004beed  mov     rdx, rdi
0x14004bef0  mov     dword ptr [rsp+58h+pContext], 202h
0x14004bef8  call    cs:__imp_DbgPrint
0x14004beff  nop     dword ptr [rax+rax+00h]
0x14004bf04  jmp     loc_14004BE1E
0x14004bf09  or      dword ptr [rdi+48h], 40h
0x14004bf0d  jmp     loc_14004BE2D
0x14004bf12  mov     [rdi+30h], eax
0x14004bf15  cmp     [rdi+28h], r12d
0x14004bf19  jnz     short loc_14004BF1E
0x14004bf1b  mov     [rdi+28h], eax
0x14004bf1e  bt      word ptr [rbp+2], 8
0x14004bf24  jnb     loc_14004BE54
0x14004bf2a  mov     [rbx+0E0h], r12
0x14004bf31  lock dec dword ptr [rdi+4]
0x14004bf35  cmp     cs:SmbCeTraceExchangeReferenceCount, r12d
0x14004bf3c  jz      loc_14004BE54
0x14004bf42  mov     ecx, [rdi+4]
0x14004bf45  lea     r9, aSmbcesubmittra; "SmbCeSubmitTransactionRequest"
0x14004bf4c  movzx   r8d, byte ptr [rdi]
0x14004bf50  mov     rdx, rdi
0x14004bf53  mov     dword ptr [rsp+58h+var_30], ecx
0x14004bf57  lea     rcx, aDereferenceExc; "Dereference Exchange %p Type(%ld) %s %l"...
0x14004bf5e  mov     dword ptr [rsp+58h+pContext], 21Fh
0x14004bf66  call    cs:__imp_DbgPrint
0x14004bf6d  nop     dword ptr [rax+rax+00h]
0x14004bf72  jmp     loc_14004BE54
0x14004bf77  mov     rcx, [rdi+50h]
0x14004bf7b  mov     rdx, rdi
0x14004bf7e  call    SmbCeDissociateMidFromExchange
0x14004bf83  jmp     loc_14004BDB2
```
