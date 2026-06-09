# FltpPerformPostCallbacksWorker

- ea: `0x1800069e0`
- end: `0x180007222`
- name: `FltpPerformPostCallbacksWorker`
- size: `2114`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800064c0`
- `0x180006590`
- `0x18001c230`

## callees

- `0x1800069e0`
- `0x180009a00`
- `0x180010400`
- `0x180014340`
- `0x180014e90`
- `0x180015db0`
- `0x180017080`
- `0x180019800`
- `0x180024880`
- `0x180060930`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x180006e11`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x180006e11`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180006e41`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1800255dc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180006e41`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1800255dc`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180006d6e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x180006d6e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x180007128`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x180007128`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180007138`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180007138`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x180006b74`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x180006b74`
- `HAL!KeQueryPerformanceCounter` at `0x180006fea`
- `HAL!KeQueryPerformanceCounter` at `0x180006fea`

## pseudocode

```c
__int64 __fastcall FltpPerformPostCallbacksWorker(__int64 a1)
{
  __int64 v1; // r11
  __int64 v2; // rsi
  int v3; // edx
  int **v4; // r15
  __int64 v6; // rcx
  int *v7; // r8
  PMDL *v8; // r12
  __int64 v9; // rax
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rax
  char v13; // r13
  unsigned __int64 v14; // r14
  KSPIN_LOCK *v15; // rcx
  _QWORD *v16; // r9
  __int64 v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rax
  char v20; // cl
  struct _FILE_OBJECT *v21; // rcx
  PTXN_PARAMETER_BLOCK TransactionParameterBlock; // rax
  PTXN_PARAMETER_BLOCK v23; // rcx
  USHORT TxFsContext; // ax
  __int64 v25; // rax
  int v26; // r8d
  int v27; // r8d
  void (__fastcall *v28)(_OWORD *, __int64, __int64, __int64); // r10
  __int64 v29; // rax
  __int64 v30; // r9
  __int64 v31; // rcx
  unsigned int v32; // eax
  unsigned int v33; // ebx
  __int64 v34; // rax
  unsigned __int64 v35; // rdx
  _QWORD *v36; // rcx
  int v37; // eax
  unsigned int v38; // ebx
  unsigned int v39; // ebx
  __int16 v41; // ax
  int *v42; // rdx
  __int64 v43; // rax
  int v44; // ecx
  int v45; // ecx
  __int64 v46; // rax
  PMDL v47; // rax
  int v48; // edx
  int v49; // r8d
  PMDL v50; // r10
  int *v51; // rdx
  __int64 v52; // rax
  int v53; // ecx
  int v54; // ecx
  __int64 v55; // rax
  PMDL *v56; // rcx
  struct _MDL *v57; // rcx
  __int64 v58; // [rsp+30h] [rbp-79h]
  __int128 v59; // [rsp+40h] [rbp-69h] BYREF
  __int128 v60; // [rsp+50h] [rbp-59h]
  __int128 v61; // [rsp+60h] [rbp-49h]
  __int64 v62; // [rsp+70h] [rbp-39h]
  _OWORD v63[3]; // [rsp+78h] [rbp-31h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A8h] [rbp-1h] BYREF
  char v65; // [rsp+110h] [rbp+67h]
  _QWORD *Irql; // [rsp+118h] [rbp+6Fh] BYREF
  PMDL v67; // [rsp+120h] [rbp+77h]
  int **v68; // [rsp+128h] [rbp+7Fh]

  v1 = *(_QWORD *)(a1 + 48);
  v2 = a1 + 232;
  v3 = *(_DWORD *)(a1 + 232);
  v4 = (int **)(a1 + 248);
  v68 = (int **)(a1 + 248);
  v58 = v1;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (v3 & 0x80000) == 0 )
  {
    if ( (v3 & 1) != 0 )
    {
      if ( !*((_BYTE *)*v4 + 4) )
      {
        v6 = *(_QWORD *)(v1 + 160);
LABEL_4:
        *(_QWORD *)(v2 + 40) = v6;
        if ( (*(_DWORD *)v2 & 1) != 0 )
        {
          v48 = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 16LL);
          v49 = **v4;
          if ( v48 != v49 && (v48 & 0x70) == 0x70 && (v49 & 0x70) == 0 )
            *(_DWORD *)v2 |= 0x100000u;
        }
        FltpTraceIOStatusOnFailure(a1, 0, 0);
        *(_DWORD *)v2 |= 0x80000u;
        v3 = *(_DWORD *)v2;
        v1 = v58;
        goto LABEL_6;
      }
      v68 = (int **)(a1 + 248);
    }
    v6 = 0;
    goto LABEL_4;
  }
LABEL_6:
  v7 = *v4;
  v8 = 0;
  v67 = 0;
  v9 = *((unsigned __int8 *)v7 + 4);
  if ( (unsigned __int8)v9 <= 0x1Bu )
  {
    v10 = qword_18003FC40[v9];
    if ( v10 != 255 )
    {
      v11 = v10 - 253;
      if ( !v11 )
        goto LABEL_87;
      if ( v11 != 1 )
      {
        v12 = BYTE4(qword_18003FC40[v9]);
        if ( (_BYTE)v12 != 0xFF )
          v8 = (PMDL *)((char *)v7 + v12 + 24);
LABEL_12:
        if ( v8 )
        {
          if ( v1 )
            v8 = (PMDL *)(v1 + 8);
          v67 = *v8;
        }
        goto LABEL_13;
      }
      if ( (*((_BYTE *)v7 + 5) & 0xFB) == 0 )
      {
LABEL_87:
        if ( (v3 & 2) == 0 && (v7[10] & 3) != 0 )
          v8 = (PMDL *)(v7 + 16);
        goto LABEL_12;
      }
    }
  }
LABEL_13:
  v13 = 0;
  v65 = 0;
  while ( *(_BYTE *)(a1 + 15) )
  {
    v14 = ((unsigned __int64)*(unsigned __int8 *)(a1 + 15) << 7) + *(_QWORD *)(a1 + 16) - 128LL;
    v15 = *(KSPIN_LOCK **)(v14 + 32);
    if ( !v15 )
      goto LABEL_16;
    KeAcquireInStackQueuedSpinLock(v15, &LockHandle);
    v41 = *(_WORD *)(v14 + 120);
    if ( (v41 & 0x10) != 0 )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      FltpFreeCompletionNodeTracking(*(_QWORD *)(*(_QWORD *)(v14 + 32) + 40LL));
      if ( *(char *)(v14 + 120) < 0 )
      {
        FltpReinstateNameCachingAllFrames(*(PVOID *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 64LL) + 80LL), a1);
        *(_WORD *)(v14 + 120) &= ~0x80u;
      }
      --*(_BYTE *)(a1 + 15);
    }
    else
    {
      if ( (v41 & 0x20) != 0 )
      {
        LOBYTE(Irql) = 0;
        IoAcquireCancelSpinLock((PKIRQL)&Irql);
        IoReleaseCancelSpinLock((KIRQL)Irql);
      }
      if ( (*(_BYTE *)(v14 + 120) & 6) != 0 )
        FltpUnlinkCompletionNodeFromInstanceLocked(v14);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_16:
      v16 = *(_QWORD **)(v14 + 8);
      Irql = v16;
      v17 = v16[2];
      *v4 = (int *)(v14 + 48);
      v18 = *(_QWORD *)(v14 + 56);
      *(_QWORD *)(a1 + 112) = v18;
      v19 = *(_QWORD *)(v17 + 64);
      v62 = v17;
      *(_QWORD *)(a1 + 104) = *(_QWORD *)(v19 + 64);
      v20 = *((_BYTE *)*v4 + 4);
      if ( v20 == 2 )
      {
        *(_QWORD *)(v18 + 24) = 0;
      }
      else if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(v20 + 22)) & 2) != 0
             && (*(_DWORD *)(v18 + 80) & 0x200000) == 0 )
      {
        v37 = *(_DWORD *)(v2 + 24);
        if ( v37 < 0 || v37 == 260 )
          *(_QWORD *)(*(_QWORD *)(a1 + 112) + 24LL) = 0;
      }
      v21 = *(struct _FILE_OBJECT **)(a1 + 112);
      if ( v21 && *(_DWORD *)(*(_QWORD *)(v17 + 64) + 60LL) == 2 )
      {
        TransactionParameterBlock = IoGetTransactionParameterBlock(v21);
        v16 = Irql;
        v23 = TransactionParameterBlock;
      }
      else
      {
        v23 = 0;
      }
      LOWORD(v59) = 48;
      *((_QWORD *)&v59 + 1) = *(_QWORD *)(v17 + 72);
      *(_QWORD *)&v60 = *(_QWORD *)(v17 + 64);
      *(_QWORD *)&v61 = *(_QWORD *)(a1 + 112);
      *((_QWORD *)&v60 + 1) = v17;
      if ( v23 )
      {
        *((_QWORD *)&v61 + 1) = v23->TransactionObject;
        TxFsContext = v23->TxFsContext;
      }
      else
      {
        *((_QWORD *)&v61 + 1) = 0;
        TxFsContext = 0;
      }
      WORD1(v59) = TxFsContext;
      if ( v8 )
      {
        v42 = *v4;
        v8 = 0;
        v43 = *((unsigned __int8 *)*v4 + 4);
        if ( (unsigned __int8)v43 <= 0x1Bu )
        {
          v7 = (int *)(8 * v43);
          v44 = qword_18003FC40[v43];
          if ( v44 != 255 )
          {
            v45 = v44 - 253;
            if ( !v45 )
              goto LABEL_95;
            if ( v45 != 1 )
            {
              v46 = *((unsigned __int8 *)qword_18003FC40 + (_QWORD)v7 + 4);
              if ( (_BYTE)v46 != 0xFF )
                v8 = (PMDL *)((char *)v42 + v46 + 24);
              goto LABEL_79;
            }
            if ( (*((_BYTE *)v42 + 5) & 0xFB) == 0 )
            {
LABEL_95:
              if ( (*(_DWORD *)v2 & 2) == 0 && (v42[10] & 3) != 0 )
                v8 = (PMDL *)(v42 + 16);
            }
          }
        }
LABEL_79:
        v47 = v67;
        if ( (*(_BYTE *)(v14 + 120) & 8) != 0 )
        {
          v65 = 1;
        }
        else
        {
          *v8 = v67;
          v47 = 0;
          v65 = 0;
        }
        *(_QWORD *)(a1 + 88) = v47;
        *(_DWORD *)(a1 + 4) &= ~0x20u;
      }
      if ( (*(_BYTE *)(v14 + 120) & 0x40) == 0 )
      {
        v25 = *(_QWORD *)(qword_18003FD98 + 24);
        if ( v25 || *(_QWORD *)(qword_18003FD98 + 32) || *(_QWORD *)(qword_18003FD98 + 16) )
        {
          v26 = *(_DWORD *)v2;
          memset(v63, 0, 44);
          v27 = v26 & 1;
          if ( !v27 )
            v25 = *(_QWORD *)(qword_18003FD98 + 32);
          if ( v25 )
          {
            (*(void (__fastcall **)(__int64, _QWORD))qword_18003FD98)(a1 + 192, ((v27 ^ 1u) + 2049) << 20);
            v16 = Irql;
          }
          v28 = *(void (__fastcall **)(_OWORD *, __int64, __int64, __int64))(qword_18003FD98 + 16);
          if ( v28 && (*(_DWORD *)v2 & 1) != 0 )
          {
            if ( (*(_DWORD *)v2 & 0x80000) != 0 )
            {
              v29 = v16[4];
              v30 = 1121;
            }
            else
            {
              v29 = v16[3];
              v30 = 1120;
            }
            v31 = *(_QWORD *)(a1 + 112);
            *(_QWORD *)&v63[0] = v29;
            DWORD2(v63[2]) = *(unsigned __int8 *)(a1 + 12);
            *((_QWORD *)&v63[0] + 1) = v31;
            if ( v31 )
              *(_QWORD *)&v63[1] = *(_QWORD *)(v31 + 24);
            *((_QWORD *)&v63[1] + 1) = *(_QWORD *)(a1 + 48);
            *(_QWORD *)&v63[2] = v2;
            v28(v63, 44, 2148007936LL, v30);
            v16 = Irql;
          }
        }
        FltpTraceIOStatusOnFailure(a1, v16, 0);
        if ( *(_DWORD *)(v17 + 708) >= *(_DWORD *)(v17 + 712) )
        {
          *(_DWORD *)(v17 + 708) = 0;
          *(LARGE_INTEGER *)(a1 + 392) = KeQueryPerformanceCounter(0);
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)(v17 + 708));
          *(_QWORD *)(a1 + 392) = 0;
        }
        v32 = ((__int64 (__fastcall *)(__int64, __int128 *, _QWORD, _QWORD))Irql[4])(v2, &v59, *(_QWORD *)(v14 + 40), 0);
        v33 = v32;
        if ( v32 == 2 )
          goto LABEL_40;
        if ( v32 == 1 )
          goto LABEL_60;
        if ( *(_QWORD *)(a1 + 392) )
          FltpIoPerfBucketizeIo(a1, v62, v32, 1);
        v38 = v33 - 1;
        if ( !v38 )
        {
LABEL_60:
          v39 = -1073741802;
          goto LABEL_61;
        }
        if ( v38 == 1 )
        {
LABEL_40:
          v13 = 1;
          *(_DWORD *)(v2 + 24) = -1071906812;
        }
        v4 = v68;
      }
      if ( *(_QWORD *)(qword_18003FD98 + 24) || *(_QWORD *)(qword_18003FD98 + 32) )
      {
        LOBYTE(v7) = 1;
        FltpPerfTraceOperationCallback(a1, Irql, v7);
      }
      LOBYTE(v7) = 1;
      FltpTraceIOStatusOnFailure(a1, Irql, v7);
      if ( *(char *)(v14 + 120) < 0 )
      {
        FltpReinstateNameCachingAllFrames(*(PVOID *)(*(_QWORD *)(v14 + 64) + 64LL), a1);
        *(_WORD *)(v14 + 120) &= ~0x80u;
      }
      if ( v8 )
      {
        if ( v65 )
        {
          if ( (*(_DWORD *)(a1 + 4) & 0x20) == 0 )
          {
            v57 = *(struct _MDL **)(a1 + 88);
            if ( v57 )
            {
              FltpFreeMdlChain(v57);
              *(_QWORD *)(a1 + 88) = 0;
            }
          }
          if ( v58 && *(_QWORD *)(v58 + 8) )
            *(_QWORD *)(v58 + 8) = 0;
        }
        v67 = *v8;
      }
      v34 = *(_QWORD *)(a1 + 16);
      v35 = (unsigned __int64)*(unsigned __int8 *)(a1 + 15) << 7;
      v36 = *(_QWORD **)(v35 + v34 - 120);
      if ( (*(_BYTE *)(v35 + v34 - 8) & 1) != 0 )
        FltObjectDereference(v36);
      else
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v36[2] + 56LL), 1u);
      --*(_BYTE *)(a1 + 15);
    }
  }
  v39 = 0;
  if ( (*(_DWORD *)v2 & 0x10000) != 0 )
    *v4 = (int *)(a1 + 320);
  if ( v8 )
  {
    if ( v58 )
    {
      v50 = v67;
      if ( (*(_DWORD *)v2 & 0x10000) == 0 )
        *(_QWORD *)(v58 + 8) = v67;
      v51 = *v4;
      v52 = *((unsigned __int8 *)*v4 + 4);
      if ( (unsigned __int8)v52 <= 0x1Bu )
      {
        v53 = qword_18003FC40[v52];
        if ( v53 != 255 )
        {
          v54 = v53 - 253;
          if ( !v54 )
            goto LABEL_119;
          if ( v54 != 1 )
          {
            v55 = BYTE4(qword_18003FC40[v52]);
            if ( (_BYTE)v55 == 0xFF )
              v56 = 0;
            else
              v56 = (PMDL *)((char *)v51 + v55 + 24);
            goto LABEL_114;
          }
          if ( (*((_BYTE *)v51 + 5) & 0xFB) == 0 )
          {
LABEL_119:
            v56 = 0;
            if ( (*(_DWORD *)v2 & 2) == 0 && (v51[10] & 3) != 0 )
              v56 = (PMDL *)(v51 + 16);
LABEL_114:
            if ( v56 )
              *v56 = v50;
          }
        }
      }
    }
    else if ( *v8 )
    {
      FltpFreeMdlChain(*v8);
      *v8 = 0;
    }
  }
LABEL_61:
  if ( v13 )
    return (unsigned int)-1071906812;
  return v39;
}

```

## disassembly

```asm
0x1800069e0  push    rbp
0x1800069e2  push    rbx
0x1800069e3  push    rsi
0x1800069e4  push    rdi
0x1800069e5  push    r12
0x1800069e7  push    r13
0x1800069e9  push    r15
0x1800069eb  lea     rbp, [rsp-27h]
0x1800069f0  sub     rsp, 0D0h
0x1800069f7  mov     r11, [rcx+30h]
0x1800069fb  lea     rsi, [rcx+0E8h]
0x180006a02  mov     edx, [rsi]
0x180006a04  lea     r15, [rsi+10h]
0x180006a08  xorps   xmm0, xmm0
0x180006a0b  mov     [rbp+57h+arg_18], r15
0x180006a0f  xor     eax, eax
0x180006a11  mov     [rbp+57h+var_D0], r11
0x180006a15  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x180006a19  mov     rdi, rcx
0x180006a1c  movups  [rbp+57h+var_C0], xmm0
0x180006a20  movups  [rbp+57h+var_B0], xmm0
0x180006a24  movups  [rbp+57h+var_A0], xmm0
0x180006a28  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x180006a2c  bt      edx, 13h
0x180006a30  jb      short loc_180006A6D
0x180006a32  test    dl, 1
0x180006a35  jnz     loc_180006EF8
0x180006a3b  xor     ecx, ecx
0x180006a3d  mov     eax, 28h ; '('
0x180006a42  mov     rdx, rsi
0x180006a45  mov     [rax+rdx], rcx
0x180006a49  mov     ecx, [rsi]
0x180006a4b  test    cl, 1
0x180006a4e  jnz     loc_180006F52
0x180006a54  xor     r8d, r8d
0x180006a57  xor     edx, edx
0x180006a59  mov     rcx, rdi
0x180006a5c  call    FltpTraceIOStatusOnFailure
0x180006a61  or      dword ptr [rsi], 80000h
0x180006a67  mov     edx, [rsi]
0x180006a69  mov     r11, [rbp+57h+var_D0]
0x180006a6d  mov     r8, [r15]
0x180006a70  xor     r10d, r10d
0x180006a73  xor     r12d, r12d
0x180006a76  mov     [rbp+57h+arg_10], r10
0x180006a7a  lea     r10, cs:180000000h
0x180006a81  movzx   eax, byte ptr [r8+4]
0x180006a86  cmp     al, 1Bh
0x180006a88  ja      short loc_180006AD4
0x180006a8a  lea     r9, ds:0[rax*8]
0x180006a92  mov     ecx, [r9+r10+3FC40h]
0x180006a9a  cmp     ecx, 0FFh
0x180006aa0  jz      short loc_180006AD4
0x180006aa2  sub     ecx, 0FDh
0x180006aa8  jz      loc_180006F23
0x180006aae  cmp     ecx, 1
0x180006ab1  jz      loc_180006F18
0x180006ab7  movzx   eax, byte ptr [r9+r10+3FC44h]
0x180006ac0  cmp     al, 0FFh
0x180006ac2  jz      short loc_180006ACB
0x180006ac4  lea     r12, [rax+18h]
0x180006ac8  add     r12, r8
0x180006acb  test    r12, r12
0x180006ace  jnz     loc_180007108
0x180006ad4  xor     r13b, r13b
0x180006ad7  mov     [rsp+100h+var_38], r14
0x180006adf  mov     [rbp+57h+arg_0], r13b
0x180006ae3  mov     ebx, 0FF7Fh
0x180006ae8  movzx   eax, byte ptr [rdi+0Fh]
0x180006aec  test    al, al
0x180006aee  jz      loc_18000701F
0x180006af4  mov     r14, [rdi+10h]
0x180006af8  mov     ecx, eax
0x180006afa  shl     rcx, 7
0x180006afe  add     r14, 0FFFFFFFFFFFFFF80h
0x180006b02  add     r14, rcx
0x180006b05  mov     [rbp+57h+var_C8], r14
0x180006b09  mov     rcx, [r14+20h]; SpinLock
0x180006b0d  test    rcx, rcx
0x180006b10  jnz     loc_180006E0D
0x180006b16  mov     r9, [r14+8]
0x180006b1a  lea     rax, [r14+30h]
0x180006b1e  mov     [rbp+57h+Irql], r9
0x180006b22  mov     rbx, [r9+10h]
0x180006b26  mov     [r15], rax
0x180006b29  mov     rdx, [r14+38h]
0x180006b2d  mov     [rdi+70h], rdx
0x180006b31  mov     rax, [rbx+40h]
0x180006b35  mov     [rbp+57h+var_90], rbx
0x180006b39  mov     rcx, [rax+40h]
0x180006b3d  mov     [rdi+68h], rcx
0x180006b41  mov     rax, [r15]
0x180006b44  movzx   ecx, byte ptr [rax+4]
0x180006b48  cmp     cl, 2
0x180006b4b  jnz     loc_180006D89
0x180006b51  mov     qword ptr [rdx+18h], 0
0x180006b59  mov     rcx, [rdi+70h]; FileObject
0x180006b5d  test    rcx, rcx
0x180006b60  jz      loc_180006F11
0x180006b66  mov     rax, [rbx+40h]
0x180006b6a  cmp     dword ptr [rax+3Ch], 2
0x180006b6e  jnz     loc_180006F11
0x180006b74  call    cs:__imp_IoGetTransactionParameterBlock
0x180006b7b  nop     dword ptr [rax+rax+00h]
0x180006b80  mov     r9, [rbp+57h+Irql]
0x180006b84  mov     rcx, rax
0x180006b87  mov     eax, 30h ; '0'
0x180006b8c  mov     word ptr [rbp+57h+var_C0], ax
0x180006b90  mov     rax, [rbx+48h]
0x180006b94  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180006b98  mov     rax, [rbx+40h]
0x180006b9c  mov     qword ptr [rbp+57h+var_B0], rax
0x180006ba0  mov     rax, [rdi+70h]
0x180006ba4  mov     qword ptr [rbp+57h+var_A0], rax
0x180006ba8  mov     qword ptr [rbp+57h+var_B0+8], rbx
0x180006bac  test    rcx, rcx
0x180006baf  jnz     loc_180007149
0x180006bb5  mov     qword ptr [rbp+57h+var_A0+8], rcx
0x180006bb9  xor     eax, eax
0x180006bbb  mov     word ptr [rbp+57h+var_C0+2], ax
0x180006bbf  test    r12, r12
0x180006bc2  jnz     loc_180006E74
0x180006bc8  test    byte ptr [r14+78h], 40h
0x180006bcd  jnz     loc_180006CF0
0x180006bd3  mov     rdx, cs:qword_18003FD98
0x180006bda  mov     rax, [rdx+18h]
0x180006bde  test    rax, rax
0x180006be1  jz      loc_180006E59
0x180006be7  mov     r8d, [rsi]
0x180006bea  xorps   xmm0, xmm0
0x180006bed  movups  [rbp+57h+var_78], xmm0
0x180006bf1  movups  [rbp+57h+var_78+0Ch], xmm0
0x180006bf5  movups  [rbp+57h+var_88], xmm0
0x180006bf9  and     r8d, 1
0x180006bfd  jnz     short loc_180006C03
0x180006bff  mov     rax, [rdx+20h]
0x180006c03  test    rax, rax
0x180006c06  jnz     loc_180007163
0x180006c0c  mov     rax, cs:qword_18003FD98
0x180006c13  mov     r10, [rax+10h]
0x180006c17  test    r10, r10
0x180006c1a  jz      short loc_180006C79
0x180006c1c  mov     eax, [rsi]
0x180006c1e  test    al, 1
0x180006c20  jz      short loc_180006C79
0x180006c22  bt      eax, 13h
0x180006c26  jnb     loc_18000718D
0x180006c2c  mov     rax, [r9+20h]
0x180006c30  mov     r9d, 461h
0x180006c36  mov     rcx, [rdi+70h]
0x180006c3a  mov     qword ptr [rbp+57h+var_88], rax
0x180006c3e  movzx   eax, byte ptr [rdi+0Ch]
0x180006c42  mov     [rbp+57h+var_60], eax
0x180006c45  mov     qword ptr [rbp+57h+var_88+8], rcx
0x180006c49  test    rcx, rcx
0x180006c4c  jnz     loc_18000719C
0x180006c52  mov     rcx, [rdi+30h]
0x180006c56  mov     edx, 2Ch ; ','
0x180006c5b  mov     qword ptr [rbp+57h+var_78+8], rcx
0x180006c5f  mov     r8d, 80080000h
0x180006c65  lea     rcx, [rbp+57h+var_88]
0x180006c69  mov     [rbp+57h+var_68], rsi
0x180006c6d  mov     rax, r10
0x180006c70  call    _guard_dispatch_icall
0x180006c75  mov     r9, [rbp+57h+Irql]
0x180006c79  xor     r8d, r8d
0x180006c7c  mov     rdx, r9
0x180006c7f  mov     rcx, rdi
0x180006c82  call    FltpTraceIOStatusOnFailure
0x180006c87  mov     eax, [rbx+2C4h]
0x180006c8d  cmp     eax, [rbx+2C8h]
0x180006c93  jnb     loc_180006FDE
0x180006c99  lock inc dword ptr [rbx+2C4h]
0x180006ca0  mov     qword ptr [rdi+188h], 0
0x180006cab  mov     rax, [rbp+57h+Irql]
0x180006caf  lea     rdx, [rbp+57h+var_C0]
0x180006cb3  mov     r8, [rbp+57h+var_C8]
0x180006cb7  xor     r9d, r9d
0x180006cba  mov     rcx, rsi
0x180006cbd  mov     r15d, 188h
0x180006cc3  mov     r14, rdi
0x180006cc6  mov     rax, [rax+20h]
0x180006cca  mov     r8, [r8+28h]
0x180006cce  call    _guard_dispatch_icall
0x180006cd3  mov     ebx, eax
0x180006cd5  cmp     eax, 2
0x180006cd8  jnz     loc_180006DC7
0x180006cde  mov     r13b, 1
0x180006ce1  mov     dword ptr [rsi+18h], 0C01C0004h
0x180006ce8  mov     r15, [rbp+57h+arg_18]
0x180006cec  mov     r14, [rbp+57h+var_C8]
0x180006cf0  mov     rax, cs:qword_18003FD98
0x180006cf7  cmp     qword ptr [rax+18h], 0
0x180006cfc  jnz     loc_1800071B7
0x180006d02  cmp     qword ptr [rax+20h], 0
0x180006d07  jnz     loc_1800071B7
0x180006d0d  mov     rdx, [rbp+57h+Irql]
0x180006d11  mov     r8b, 1
0x180006d14  mov     rcx, rdi
0x180006d17  call    FltpTraceIOStatusOnFailure
0x180006d1c  movzx   eax, byte ptr [r14+78h]
0x180006d21  test    al, al
0x180006d23  js      loc_1800071CB
0x180006d29  mov     ebx, 0FF7Fh
0x180006d2e  test    r12, r12
0x180006d31  jz      short loc_180006D45
0x180006d33  cmp     [rbp+57h+arg_0], 0
0x180006d37  jnz     loc_1800071F8
0x180006d3d  mov     rax, [r12]
0x180006d41  mov     [rbp+57h+arg_10], rax
0x180006d45  mov     rax, [rdi+10h]
0x180006d49  movzx   edx, byte ptr [rdi+0Fh]
0x180006d4d  shl     rdx, 7
0x180006d51  test    byte ptr [rdx+rax-8], 1
0x180006d56  mov     rcx, [rdx+rax-78h]; FltObject
0x180006d5b  jnz     loc_180007002
0x180006d61  mov     rcx, [rcx+10h]
0x180006d65  mov     edx, 1; Count
0x180006d6a  mov     rcx, [rcx+38h]; RunRef
0x180006d6e  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x180006d75  nop     dword ptr [rax+rax+00h]
0x180006d7a  dec     byte ptr [rdi+0Fh]
0x180006d7d  lea     r10, cs:180000000h
0x180006d84  jmp     loc_180006AE8
0x180006d89  add     cl, 16h
0x180006d8c  movzx   eax, cl
0x180006d8f  test    byte ptr [rax+r10+28CB0h], 2
0x180006d98  jz      loc_180006B59
0x180006d9e  mov     eax, [rdx+50h]
0x180006da1  bt      eax, 15h
0x180006da5  jb      loc_180006B59
0x180006dab  mov     eax, [rsi+18h]
0x180006dae  test    eax, eax
0x180006db0  jns     loc_180006FCE
0x180006db6  mov     rax, [rdi+70h]
0x180006dba  mov     qword ptr [rax+18h], 0
0x180006dc2  jmp     loc_180006B59
0x180006dc7  cmp     ebx, 1
0x180006dca  jz      short loc_180006DE0
0x180006dcc  cmp     qword ptr [r14+r15], 0
0x180006dd1  jnz     loc_180006F88
0x180006dd7  sub     ebx, 1
0x180006dda  jnz     loc_1800071A9
0x180006de0  mov     ebx, 0C0000016h
0x180006de5  mov     r14, [rsp+100h+var_38]
0x180006ded  mov     eax, 0C01C0004h
0x180006df2  test    r13b, r13b
0x180006df5  cmovnz  ebx, eax
0x180006df8  mov     eax, ebx
0x180006dfa  add     rsp, 0D0h
0x180006e01  pop     r15
0x180006e03  pop     r13
0x180006e05  pop     r12
0x180006e07  pop     rdi
0x180006e08  pop     rsi
0x180006e09  pop     rbx
0x180006e0a  pop     rbp
0x180006e0b  retn
0x180006e0d  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x180006e11  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x180006e18  nop     dword ptr [rax+rax+00h]
0x180006e1d  movzx   eax, word ptr [r14+78h]
0x180006e22  test    al, 10h
0x180006e24  jnz     loc_1800255D8
0x180006e2a  test    al, 20h
0x180006e2c  jnz     loc_180007120
0x180006e32  test    byte ptr [r14+78h], 6
0x180006e37  jnz     loc_180006F45
0x180006e3d  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x180006e41  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x180006e48  nop     dword ptr [rax+rax+00h]
0x180006e4d  lea     r10, cs:180000000h
0x180006e54  jmp     loc_180006B16
0x180006e59  cmp     qword ptr [rdx+20h], 0
0x180006e5e  jnz     loc_180006BE7
0x180006e64  cmp     qword ptr [rdx+10h], 0
0x180006e69  jz      loc_180006C79
0x180006e6f  jmp     loc_180006BE7
0x180006e74  mov     rdx, [r15]
0x180006e77  xor     r12d, r12d
0x180006e7a  movzx   eax, byte ptr [rdx+4]
0x180006e7e  cmp     al, 1Bh
0x180006e80  ja      short loc_180006ECA
0x180006e82  lea     r8, ds:0[rax*8]
0x180006e8a  lea     r11, cs:180000000h
0x180006e91  mov     ecx, [r8+r11+3FC40h]
0x180006e99  cmp     ecx, 0FFh
0x180006e9f  jz      short loc_180006ECA
0x180006ea1  sub     ecx, 0FDh
0x180006ea7  jz      loc_180006FAC
0x180006ead  cmp     ecx, 1
0x180006eb0  jz      loc_180006FA2
0x180006eb6  movzx   eax, byte ptr [r8+r11+3FC44h]
0x180006ebf  cmp     al, 0FFh
0x180006ec1  jz      short loc_180006ECA
0x180006ec3  lea     r12, [rax+18h]
0x180006ec7  add     r12, rdx
0x180006eca  test    byte ptr [r14+78h], 8
0x180006ecf  mov     rcx, rdi
0x180006ed2  mov     rax, [rbp+57h+arg_10]
  ... truncated ...
```
