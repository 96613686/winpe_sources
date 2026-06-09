# TxfTransMgrAbort

- ea: `0x1401d60b8`
- end: `0x1401d6942`
- name: `TxfTransMgrAbort`
- size: `2186`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400f9d48`
- `0x1401d97f0`
- `0x1402670c0`

## callees

- `0x1400082b0`
- `0x140010be0`
- `0x140012ab0`
- `0x140012b50`
- `0x140016ea0`
- `0x140017030`
- `0x1400291f0`
- `0x140029d80`
- `0x140038908`
- `0x140052074`
- `0x140053bb4`
- `0x140059250`
- `0x1400596c0`
- `0x1400b62e4`
- `0x14012e4f0`
- `0x140140f5c`
- `0x140188ce4`
- `0x14018e638`
- `0x1401c2ae8`
- `0x1401d60b8`
- `0x1401d8340`
- `0x1401da930`
- `0x1401daa68`
- `0x1401db344`
- `0x1401dc54c`
- `0x1402056bc`
- `0x140209910`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401d686a`
- `ntoskrnl!KeSetEvent` at `0x1401d686a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401d6383`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401d6383`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d6248`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d6248`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d6152`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d6152`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d61c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d6206`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d61c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d6206`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d63ad`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d659a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d63ad`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d659a`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d63cc`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d65b9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d63cc`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d65b9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6512`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d657f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6624`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6512`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d657f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6624`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReserveAndAppendLog` at `0x1401d675e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReserveAndAppendLog` at `0x1401d675e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d654b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d654b`

## pseudocode

```c
__int64 __fastcall TxfTransMgrAbort(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  CLFS_LSN *v3; // rdi
  __int64 v4; // r13
  struct _ERESOURCE *v5; // rcx
  int Undo; // ebx
  volatile signed __int32 *v8; // rsi
  int v9; // eax
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  _QWORD *v13; // rcx
  int v14; // eax
  unsigned __int64 v15; // rcx
  __int64 v16; // r8
  unsigned __int8 v17; // cf
  int v18; // eax
  unsigned __int64 v19; // rax
  __int64 v20; // r8
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  unsigned __int64 v25; // rax
  __int64 v26; // r8
  volatile signed __int32 *v27; // r12
  int v28; // eax
  NTSTATUS appended; // eax
  NTSTATUS v30; // edx
  unsigned __int64 v31; // rcx
  __int64 v32; // r8
  unsigned __int64 v33; // rax
  __int64 v34; // rcx
  int v35; // eax
  char v36; // [rsp+50h] [rbp-128h]
  __int64 rgcbReservation; // [rsp+58h] [rbp-120h] BYREF
  CLFS_LSN plsn; // [rsp+60h] [rbp-118h] BYREF
  CLFS_LSN v39; // [rsp+68h] [rbp-110h] BYREF
  CLFS_LSN *v40; // [rsp+70h] [rbp-108h] BYREF
  volatile signed __int32 *v41; // [rsp+78h] [rbp-100h] BYREF
  __int64 v42[4]; // [rsp+80h] [rbp-F8h] BYREF
  CLFS_WRITE_ENTRY v43; // [rsp+A0h] [rbp-D8h] BYREF
  _OWORD v44[2]; // [rsp+B0h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+D0h] [rbp-A8h]
  _WORD v46[48]; // [rsp+E0h] [rbp-98h] BYREF

  v2 = a2;
  rgcbReservation = a2;
  v3 = (CLFS_LSN *)a1;
  v40 = (CLFS_LSN *)a1;
  v42[2] = a2;
  memset(v44, 0, sizeof(v44));
  v45 = 0;
  plsn.ullOffset = 0;
  v42[0] = a2 + 208;
  v4 = *(_QWORD *)(a2 + 208);
  v39.ullOffset = 0;
  TxfTransFreeze(a2, 1);
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v2 + 24) + 80LL), 1u);
  if ( (!v3 || (v3[2].offset.idxRecord & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
  {
    McTemplateU0spjpj_EtwWriteTransfer(
      v4 + 672,
      (const EVENT_DESCRIPTOR *)txftrans_c7455,
      "TxfTransMgrAbort",
      v4,
      v4 + 672,
      v2,
      v2 + 256);
  }
  v5 = (struct _ERESOURCE *)(*(_QWORD *)(v2 + 24) + 80LL);
  if ( (*(_DWORD *)(v2 + 16) & 0x2000) != 0 )
  {
    ExReleaseResourceLite(v5);
    v41 = (volatile signed __int32 *)v2;
    TxfDereferenceTransaction((__int64 *)&v41, 1);
    return 0;
  }
  v42[1] = v4;
  v36 = 0;
  Undo = 0;
  v42[3] = v2 + 16;
  ExReleaseResourceLite(v5);
  v41 = (volatile signed __int32 *)(v4 + 232);
  if ( _InterlockedIncrement((volatile signed __int32 *)(v4 + 232)) > 10 )
  {
    v8 = (volatile signed __int32 *)(v4 + 232);
    do
    {
      _InterlockedDecrement(v8);
      KeWaitForSingleObject((PVOID)(*(_QWORD *)(v4 + 24) + 72LL), Executive, 0, 0, 0);
    }
    while ( _InterlockedIncrement(v8) > 10 );
    v2 = rgcbReservation;
  }
  if ( !v3 )
  {
    rgcbReservation = NtfsInitializeTopLevelIrp((__int64)v44, 3, *(_QWORD *)(v4 + 16));
    Undo = NtfsInitializeIrpContextInternal(0, 1, 0, (__int64 *)&v40);
    v3 = v40;
    if ( !v40 )
    {
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
        McTemplateU0sdpjpj_EtwWriteTransfer(
          v2 + 256,
          (const EVENT_DESCRIPTOR *)txftrans_c7553,
          "TxfTransMgrAbort",
          Undo,
          v2,
          v2 + 256,
          v4,
          v4 + 672);
      goto LABEL_79;
    }
    NtfsUpdateIrpContextWithTopLevel((__int64)v40, rgcbReservation);
    v36 = 1;
  }
  NtfsSetIrpContextVcb((__int64)v3, *(_QWORD *)(v4 + 16));
  v3[1].offset.cidContainer |= 0x10001u;
  v3[54].offset.cidContainer |= 0x100000u;
  v3[54].offset.cidContainer |= 0x80008u;
  v9 = *(_DWORD *)(v2 + 16);
  if ( (v9 & 0x40) == 0 )
    goto LABEL_79;
  if ( (v9 & 8) == 0 )
  {
    while ( 1 )
    {
      v10 = (_QWORD *)(v2 + 176);
      v11 = *(_QWORD **)(v2 + 176);
      if ( v11 == (_QWORD *)(v2 + 176) )
        break;
      if ( (_QWORD *)v11[1] != v10 || (v12 = *v11, *(_QWORD **)(*v11 + 8LL) != v11) )
        __fastfail(3u);
      *v10 = v12;
      *(_QWORD *)(v12 + 8) = v10;
      v13 = (_QWORD *)v11[4];
      if ( v13 )
        TxfDereferenceTxfFcb(v13, 0);
      ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, v11);
    }
  }
  if ( (*(_DWORD *)(v2 + 16) & 0x20) == 0 )
    v3[54].offset.cidContainer |= 0x40u;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v4 + 8912));
  v39 = *(CLFS_LSN *)(v4 + 8920);
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v4 + 8912));
  v14 = TxfActOnAllStreamsForTransaction((_DWORD)v3, 2, &v39);
  Undo = v14;
  if ( v14 >= 0 )
  {
    TxfTransCleanupTxfWriterInformation((__int64)v3, v2, 0);
    v18 = TxfUsnProcessingForFilesOnModifiedListAtEOT((int)v3);
    Undo = v18;
    if ( v18 < 0 )
    {
      if ( v18 != -1073741801 )
      {
        v19 = (unsigned int)(v18 + 1073741697);
        if ( (unsigned int)v19 > 0x22 || (v20 = 0x408000001LL, !_bittest64(&v20, v19)) )
        {
          if ( Undo == -1072037845
            || Undo == -1073741202
            || Undo == -1073741435
            || Undo == -1073741496
            || (v21 = (unsigned int)(Undo + 1073741667), (unsigned int)v21 <= 0x23)
            && (v22 = 0x800000041LL, _bittest64(&v22, v21))
            || (unsigned int)(Undo + 1073741811) <= 0x15 && (v23 = 2097219, _bittest(&v23, Undo + 1073741811))
            || Undo == -2147483626
            || Undo == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          goto LABEL_79;
        }
      }
      goto LABEL_32;
    }
    _InterlockedOr((volatile signed __int32 *)(v2 + 16), 8u);
    plsn = *(CLFS_LSN *)(v2 + 48);
    if ( ClfsLsnNull(&plsn) )
    {
      ProcessSavepointListForCurrentLogRec((const CLFS_LSN *)v2);
    }
    else
    {
      do
      {
        if ( ClfsLsnNull(&plsn) )
          break;
        NtfsPurgeFileRecordCache((__int64)v3);
        Undo = TxfTransDoNextUndo((int)v3, v2);
      }
      while ( Undo >= 0 );
    }
    if ( *(_QWORD *)(v2 + 224) )
    {
      NtfsPurgeFileRecordCache((__int64)v3);
      v3->offset.cidContainer |= 0x200u;
      ClfsTerminateReadLog(*(PVOID *)(v2 + 224));
      v3->offset.cidContainer &= ~0x200u;
      *(_QWORD *)(v2 + 224) = 0;
      _InterlockedDecrement((volatile signed __int32 *)(v4 + 528));
    }
    if ( Undo < 0 )
      goto LABEL_79;
    _InterlockedOr((volatile signed __int32 *)(v2 + 16), 0x100u);
    if ( !ClfsLsnNull((const CLFS_LSN *)(v2 + 40)) )
    {
      ExAcquireFastMutex(*(PFAST_MUTEX *)(v4 + 8912));
      v39 = *(CLFS_LSN *)(v4 + 8920);
      ExReleaseFastMutex(*(PFAST_MUTEX *)(v4 + 8912));
      v24 = TxfActOnAllStreamsForTransaction((_DWORD)v3, 9, &v39);
      Undo = v24;
      if ( v24 < 0 )
      {
        if ( v24 == -1073741801 )
          goto LABEL_32;
        v25 = (unsigned int)(v24 + 1073741697);
        if ( (unsigned int)v25 > 0x22 )
          goto LABEL_79;
        v26 = 0x408000001LL;
        v17 = _bittest64(&v26, v25);
LABEL_31:
        if ( v17 )
          goto LABEL_32;
        goto LABEL_79;
      }
      LfsQueryLastLsn(*(_QWORD *)(v3[13].ullOffset + 232));
      LfsFlushToLsn(*(_QWORD *)(v3[13].ullOffset + 232), NtfsLargeMax);
      *(_DWORD *)(v3[18].ullOffset + 24) = 0;
    }
    memset(v46, 0, sizeof(v46));
    v46[0] = 8;
    v27 = (volatile signed __int32 *)(v2 + 16);
    v28 = *(_DWORD *)(v2 + 16) & 0x20;
    v43.Buffer = v46;
    v43.ByteLength = 96;
    TxfTransWriteLogArray(v2, &v43, 1u, v28 != 0 ? 2 : 6, v3, 0, 0, 0, 0);
    if ( (*(_DWORD *)(v2 + 16) & 0x61) == 0x40 )
    {
      rgcbReservation = -96;
      NtfsPurgeFileRecordCache((__int64)v3);
      v3->offset.cidContainer |= 0x200u;
      appended = ClfsReserveAndAppendLog(*(PVOID *)(v4 + 512), 0, 0, 0, 0, 1u, &rgcbReservation, 0, 0);
      v30 = appended;
      v3->offset.cidContainer &= ~0x200u;
      if ( appended )
      {
        if ( appended == -1073741801
          || (v31 = (unsigned int)(appended + 1073741697), (unsigned int)v31 <= 0x22)
          && (v32 = 0x408000001LL, _bittest64(&v32, v31)) )
        {
          ++HIDWORD((*TxfData)[1]);
        }
        else if ( appended == -1072037845
               || appended == -1073741202
               || appended == -1073741435
               || appended == -1073741496
               || (v33 = (unsigned int)(appended + 1073741667), (unsigned int)v33 <= 0x23)
               && (v34 = 0x800000041LL, _bittest64(&v34, v33))
               || (unsigned int)(v30 + 1073741811) <= 0x15 && (v35 = 2097219, _bittest(&v35, v30 + 1073741811))
               || v30 == -2147483626
               || v30 == -1072037841 )
        {
          ++LODWORD((*TxfData)[2]);
        }
      }
    }
    goto LABEL_80;
  }
  if ( v14 == -1073741801 )
  {
LABEL_32:
    ++HIDWORD((*TxfData)[1]);
    goto LABEL_79;
  }
  v15 = (unsigned int)(v14 + 1073741697);
  if ( (unsigned int)v15 <= 0x22 )
  {
    v16 = 0x408000001LL;
    v17 = _bittest64(&v16, v15);
    goto LABEL_31;
  }
LABEL_79:
  v27 = (volatile signed __int32 *)(v2 + 16);
LABEL_80:
  _InterlockedDecrement(v41);
  KeSetEvent((PRKEVENT)(*(_QWORD *)(v4 + 24) + 72LL), 0, 0);
  if ( Undo < 0 )
  {
    TxfSetupForDeferredAbortPriv(v2, Undo, "TxfTransMgrAbort", "txftrans.c", 185);
  }
  else
  {
    TxfTransCleanupOnTransEnd((_DWORD)v3, v2, 0, 0, 0);
    _InterlockedAnd(v27, 0xFFFFFFFE);
    TxfRemoveTransactionFromList(v2);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)v42[0] + 248LL), 1u);
  }
  v42[0] = v2;
  TxfDereferenceTransaction(v42, 1);
  if ( v36 )
    v3[1].offset.cidContainer &= ~0x10000u;
  NtfsExtendedCompleteRequestInternal((__int64)v3, 0, 0, 1u, 1);
  return (unsigned int)Undo;
}

```

## disassembly

```asm
0x1401d60b8  mov     [rsp+arg_10], rbx
0x1401d60bd  mov     [rsp+arg_18], rsi
0x1401d60c2  push    rdi
0x1401d60c3  push    r12
0x1401d60c5  push    r13
0x1401d60c7  push    r14
0x1401d60c9  push    r15
0x1401d60cb  sub     rsp, 150h
0x1401d60d2  mov     rax, cs:__security_cookie
0x1401d60d9  xor     rax, rsp
0x1401d60dc  mov     [rsp+178h+var_38], rax
0x1401d60e4  mov     rsi, rdx
0x1401d60e7  mov     [rsp+178h+var_120], rdx
0x1401d60ec  mov     rdi, rcx
0x1401d60ef  mov     [rsp+178h+var_108], rcx
0x1401d60f4  mov     [rsp+178h+var_E8], rdx
0x1401d60fc  xorps   xmm0, xmm0
0x1401d60ff  xor     eax, eax
0x1401d6101  movups  [rsp+178h+var_C8], xmm0
0x1401d6109  movups  [rsp+178h+var_B8], xmm0
0x1401d6111  mov     [rsp+178h+var_A8], rax
0x1401d6119  xor     r14d, r14d
0x1401d611c  mov     qword ptr [rsp+178h+plsn], r14
0x1401d6121  lea     rax, [rdx+0D0h]
0x1401d6128  mov     [rsp+178h+var_F8], rax
0x1401d6130  mov     r13, [rax]
0x1401d6133  mov     [rsp+178h+var_110], r14
0x1401d6138  lea     r15d, [r14+1]
0x1401d613c  mov     edx, r15d
0x1401d613f  mov     rcx, rsi
0x1401d6142  call    TxfTransFreeze
0x1401d6147  mov     rcx, [rsi+18h]
0x1401d614b  add     rcx, 50h ; 'P'; Resource
0x1401d614f  mov     dl, r15b; Wait
0x1401d6152  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d6159  nop     dword ptr [rax+rax+00h]
0x1401d615e  test    rdi, rdi
0x1401d6161  jz      short loc_1401D6173
0x1401d6163  mov     eax, [rdi+10h]
0x1401d6166  bt      rax, 14h
0x1401d616b  jnb     short loc_1401D6173
0x1401d616d  lea     r12d, [r14+8]
0x1401d6171  jmp     short loc_1401D61B5
0x1401d6173  mov     r12d, 8
0x1401d6179  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, r12b
0x1401d6180  jz      short loc_1401D61B5
0x1401d6182  lea     rax, [rsi+100h]
0x1401d6189  lea     rcx, [r13+2A0h]
0x1401d6190  mov     [rsp+178h+rgcbReservation], rax
0x1401d6195  mov     qword ptr [rsp+178h+cReserveRecords], rsi
0x1401d619a  mov     [rsp+178h+Timeout], rcx
0x1401d619f  mov     r9, r13
0x1401d61a2  lea     r8, aTxftransmgrabo; "TxfTransMgrAbort"
0x1401d61a9  lea     rdx, txftrans_c7455
0x1401d61b0  call    McTemplateU0spjpj_EtwWriteTransfer
0x1401d61b5  lea     rdx, [rsi+10h]
0x1401d61b9  mov     rcx, [rsi+18h]
0x1401d61bd  add     rcx, 50h ; 'P'; Resource
0x1401d61c1  test    dword ptr [rdx], 2000h
0x1401d61c7  jz      short loc_1401D61EE
0x1401d61c9  call    cs:__imp_ExReleaseResourceLite
0x1401d61d0  nop     dword ptr [rax+rax+00h]
0x1401d61d5  mov     [rsp+178h+var_100], rsi
0x1401d61da  mov     dl, r15b
0x1401d61dd  lea     rcx, [rsp+178h+var_100]
0x1401d61e2  call    TxfDereferenceTransaction
0x1401d61e7  xor     eax, eax
0x1401d61e9  jmp     loc_1401D6914
0x1401d61ee  mov     [rsp+178h+var_F0], r13
0x1401d61f6  mov     [rsp+178h+var_128], r14b
0x1401d61fb  mov     ebx, r14d
0x1401d61fe  mov     [rsp+178h+var_E0], rdx
0x1401d6206  call    cs:__imp_ExReleaseResourceLite
0x1401d620d  nop     dword ptr [rax+rax+00h]
0x1401d6212  lea     rcx, [r13+0E8h]
0x1401d6219  mov     [rsp+178h+var_100], rcx
0x1401d621e  mov     eax, r15d
0x1401d6221  lock xadd [rcx], eax
0x1401d6225  add     eax, r15d
0x1401d6228  cmp     eax, 0Ah
0x1401d622b  jle     short loc_1401D6268
0x1401d622d  mov     rsi, rcx
0x1401d6230  lock dec dword ptr [rsi]
0x1401d6233  mov     rcx, [r13+18h]
0x1401d6237  add     rcx, 48h ; 'H'; Object
0x1401d623b  mov     [rsp+178h+Timeout], r14; Timeout
0x1401d6240  xor     r9d, r9d; Alertable
0x1401d6243  xor     r8d, r8d; WaitMode
0x1401d6246  xor     edx, edx; WaitReason
0x1401d6248  call    cs:__imp_KeWaitForSingleObject
0x1401d624f  nop     dword ptr [rax+rax+00h]
0x1401d6254  mov     eax, r15d
0x1401d6257  lock xadd [rsi], eax
0x1401d625b  add     eax, r15d
0x1401d625e  cmp     eax, 0Ah
0x1401d6261  jg      short loc_1401D6230
0x1401d6263  mov     rsi, [rsp+178h+var_120]
0x1401d6268  test    rdi, rdi
0x1401d626b  jnz     loc_1401D6308
0x1401d6271  mov     r8, [r13+10h]
0x1401d6275  lea     edx, [rdi+3]
0x1401d6278  lea     rcx, [rsp+178h+var_C8]
0x1401d6280  call    NtfsInitializeTopLevelIrp
0x1401d6285  mov     [rsp+178h+var_120], rax
0x1401d628a  lea     r9, [rsp+178h+var_108]
0x1401d628f  xor     r8d, r8d
0x1401d6292  mov     dl, r15b
0x1401d6295  xor     ecx, ecx; Irp
0x1401d6297  call    NtfsInitializeIrpContextInternal
0x1401d629c  mov     ebx, eax
0x1401d629e  mov     [rsp+178h+var_124], eax
0x1401d62a2  mov     rdi, [rsp+178h+var_108]
0x1401d62a7  test    rdi, rdi
0x1401d62aa  jnz     short loc_1401D62F6
0x1401d62ac  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, r12b
0x1401d62b3  jz      loc_1401D6818
0x1401d62b9  lea     rax, [r13+2A0h]
0x1401d62c0  lea     rcx, [rsi+100h]
0x1401d62c7  mov     qword ptr [rsp+178h+fFlags], rax
0x1401d62cc  mov     [rsp+178h+rgcbReservation], r13
0x1401d62d1  mov     qword ptr [rsp+178h+cReserveRecords], rcx
0x1401d62d6  mov     [rsp+178h+Timeout], rsi
0x1401d62db  mov     r9d, ebx
0x1401d62de  lea     r8, aTxftransmgrabo; "TxfTransMgrAbort"
0x1401d62e5  lea     rdx, txftrans_c7553
0x1401d62ec  call    McTemplateU0sdpjpj_EtwWriteTransfer
0x1401d62f1  jmp     loc_1401D6818
0x1401d62f6  mov     rdx, [rsp+178h+var_120]
0x1401d62fb  mov     rcx, rdi
0x1401d62fe  call    NtfsUpdateIrpContextWithTopLevel
0x1401d6303  mov     [rsp+178h+var_128], r15b
0x1401d6308  mov     rdx, [r13+10h]
0x1401d630c  mov     rcx, rdi
0x1401d630f  call    NtfsSetIrpContextVcb
0x1401d6314  or      dword ptr [rdi+0Ch], 10001h
0x1401d631b  bts     dword ptr [rdi+1B4h], 14h
0x1401d6323  mov     eax, [rdi+1B4h]
0x1401d6329  or      eax, 80008h
0x1401d632e  mov     [rdi+1B4h], eax
0x1401d6334  mov     eax, [rsi+10h]
0x1401d6337  test    al, 40h
0x1401d6339  jz      loc_1401D6818
0x1401d633f  test    r12b, al
0x1401d6342  jnz     short loc_1401D6398
0x1401d6344  lea     rax, [rsi+0B0h]
0x1401d634b  mov     rbx, [rax]
0x1401d634e  cmp     rbx, rax
0x1401d6351  jz      short loc_1401D6398
0x1401d6353  cmp     [rbx+8], rax
0x1401d6357  jnz     short loc_1401D6391
0x1401d6359  mov     rcx, [rbx]
0x1401d635c  cmp     [rcx+8], rbx
0x1401d6360  jnz     short loc_1401D6391
0x1401d6362  mov     [rax], rcx
0x1401d6365  mov     [rcx+8], rax
0x1401d6369  mov     rcx, [rbx+20h]
0x1401d636d  test    rcx, rcx
0x1401d6370  jz      short loc_1401D6379
0x1401d6372  xor     edx, edx
0x1401d6374  call    TxfDereferenceTxfFcb
0x1401d6379  mov     rdx, rbx; Entry
0x1401d637c  lea     rcx, TxfDeletedLinkLookasideList; Lookaside
0x1401d6383  call    cs:__imp_ExFreeToLookasideListEx
0x1401d638a  nop     dword ptr [rax+rax+00h]
0x1401d638f  jmp     short loc_1401D6344
0x1401d6391  mov     ecx, 3
0x1401d6396  int     29h; Win8: RtlFailFast(ecx)
0x1401d6398  mov     eax, [rsi+10h]
0x1401d639b  test    al, 20h
0x1401d639d  jnz     short loc_1401D63A6
0x1401d639f  or      dword ptr [rdi+1B4h], 40h
0x1401d63a6  mov     rcx, [r13+22D0h]; FastMutex
0x1401d63ad  call    cs:__imp_ExAcquireFastMutex
0x1401d63b4  nop     dword ptr [rax+rax+00h]
0x1401d63b9  mov     rax, [r13+22D8h]
0x1401d63c0  mov     [rsp+178h+var_110], rax
0x1401d63c5  mov     rcx, [r13+22D0h]; FastMutex
0x1401d63cc  call    cs:__imp_ExReleaseFastMutex
0x1401d63d3  nop     dword ptr [rax+rax+00h]
0x1401d63d8  lea     rax, [rsp+178h+var_110]
0x1401d63dd  mov     qword ptr [rsp+178h+cReserveRecords], rax
0x1401d63e2  mov     r8d, 2
0x1401d63e8  mov     dword ptr [rsp+178h+Timeout], r8d
0x1401d63ed  lea     r9d, [r8+9]
0x1401d63f1  mov     rdx, rsi
0x1401d63f4  mov     rcx, rdi
0x1401d63f7  call    TxfActOnAllStreamsForTransaction
0x1401d63fc  mov     ebx, eax
0x1401d63fe  mov     [rsp+178h+var_124], eax
0x1401d6402  test    eax, eax
0x1401d6404  jns     short loc_1401D6440
0x1401d6406  cmp     eax, 0C0000017h
0x1401d640b  jz      short loc_1401D6430
0x1401d640d  lea     ecx, [rax+3FFFFF81h]
0x1401d6413  cmp     ecx, 22h ; '"'
0x1401d6416  ja      loc_1401D6818
0x1401d641c  mov     r8, 408000001h
0x1401d6426  bt      r8, rcx
0x1401d642a  jnb     loc_1401D6818
0x1401d6430  mov     rax, cs:TxfData
0x1401d6437  add     [rax+0Ch], r15d
0x1401d643b  jmp     loc_1401D6818
0x1401d6440  xor     r8d, r8d
0x1401d6443  mov     rdx, rsi
0x1401d6446  mov     rcx, rdi
0x1401d6449  call    TxfTransCleanupTxfWriterInformation
0x1401d644e  xor     r8d, r8d
0x1401d6451  mov     rdx, rsi
0x1401d6454  mov     rcx, rdi; int
0x1401d6457  call    TxfUsnProcessingForFilesOnModifiedListAtEOT
0x1401d645c  mov     ebx, eax
0x1401d645e  mov     [rsp+178h+var_124], eax
0x1401d6462  test    eax, eax
0x1401d6464  jns     loc_1401D64FF
0x1401d646a  cmp     eax, 0C0000017h
0x1401d646f  jz      short loc_1401D6430
0x1401d6471  add     eax, 3FFFFF81h
0x1401d6476  cmp     eax, 22h ; '"'
0x1401d6479  ja      short loc_1401D648B
0x1401d647b  mov     r8, 408000001h
0x1401d6485  bt      r8, rax
0x1401d6489  jb      short loc_1401D6430
0x1401d648b  cmp     ebx, 0C01A002Bh
0x1401d6491  jz      short loc_1401D64EF
0x1401d6493  cmp     ebx, 0C000026Eh
0x1401d6499  jz      short loc_1401D64EF
0x1401d649b  cmp     ebx, 0C0000185h
0x1401d64a1  jz      short loc_1401D64EF
0x1401d64a3  cmp     ebx, 0C0000148h
0x1401d64a9  jz      short loc_1401D64EF
0x1401d64ab  lea     eax, [rbx+3FFFFF63h]
0x1401d64b1  cmp     eax, 23h ; '#'
0x1401d64b4  ja      short loc_1401D64C6
0x1401d64b6  mov     rcx, 800000041h
0x1401d64c0  bt      rcx, rax
0x1401d64c4  jb      short loc_1401D64EF
0x1401d64c6  lea     ecx, [rbx+3FFFFFF3h]
0x1401d64cc  cmp     ecx, 15h
0x1401d64cf  ja      short loc_1401D64DB
0x1401d64d1  mov     eax, 200043h
0x1401d64d6  bt      eax, ecx
0x1401d64d9  jb      short loc_1401D64EF
0x1401d64db  cmp     ebx, 80000016h
0x1401d64e1  jz      short loc_1401D64EF
0x1401d64e3  cmp     ebx, 0C01A002Fh
0x1401d64e9  jnz     loc_1401D6818
0x1401d64ef  mov     rax, cs:TxfData
0x1401d64f6  add     [rax+10h], r15d
0x1401d64fa  jmp     loc_1401D6818
0x1401d64ff  lock or [rsi+10h], r12d
0x1401d6504  mov     rax, [rsi+30h]
0x1401d6508  mov     qword ptr [rsp+178h+plsn], rax
0x1401d650d  lea     rcx, [rsp+178h+plsn]; plsn
0x1401d6512  call    cs:__imp_ClfsLsnNull
0x1401d6519  nop     dword ptr [rax+rax+00h]
0x1401d651e  test    al, al
0x1401d6520  jz      loc_1401D661F
0x1401d6526  mov     rcx, rsi
0x1401d6529  call    ProcessSavepointListForCurrentLogRec
0x1401d652e  cmp     [rsi+0E0h], r14
0x1401d6535  jz      short loc_1401D656B
0x1401d6537  mov     rcx, rdi
0x1401d653a  call    NtfsPurgeFileRecordCache
0x1401d653f  bts     dword ptr [rdi+4], 9
0x1401d6544  mov     rcx, [rsi+0E0h]; pvCursorContext
0x1401d654b  call    cs:__imp_ClfsTerminateReadLog
0x1401d6552  nop     dword ptr [rax+rax+00h]
0x1401d6557  btr     dword ptr [rdi+4], 9
0x1401d655c  mov     [rsi+0E0h], r14
0x1401d6563  lock dec dword ptr [r13+210h]
0x1401d656b  test    ebx, ebx
0x1401d656d  js      loc_1401D6818
0x1401d6573  lock or dword ptr [rsi+10h], 100h
0x1401d657b  lea     rcx, [rsi+28h]; plsn
0x1401d657f  call    cs:__imp_ClfsLsnNull
0x1401d6586  nop     dword ptr [rax+rax+00h]
0x1401d658b  test    al, al
0x1401d658d  jnz     loc_1401D6692
0x1401d6593  mov     rcx, [r13+22D0h]; FastMutex
0x1401d659a  call    cs:__imp_ExAcquireFastMutex
0x1401d65a1  nop     dword ptr [rax+rax+00h]
0x1401d65a6  mov     rax, [r13+22D8h]
0x1401d65ad  mov     [rsp+178h+var_110], rax
0x1401d65b2  mov     rcx, [r13+22D0h]; FastMutex
0x1401d65b9  call    cs:__imp_ExReleaseFastMutex
0x1401d65c0  nop     dword ptr [rax+rax+00h]
0x1401d65c5  lea     rax, [rsp+178h+var_110]
0x1401d65ca  mov     qword ptr [rsp+178h+cReserveRecords], rax
0x1401d65cf  mov     dword ptr [rsp+178h+Timeout], 9
0x1401d65d7  xor     r9d, r9d
0x1401d65da  lea     r8d, [r9+64h]
0x1401d65de  mov     rdx, rsi
0x1401d65e1  mov     rcx, rdi
0x1401d65e4  call    TxfActOnAllStreamsForTransaction
0x1401d65e9  mov     ebx, eax
0x1401d65eb  mov     [rsp+178h+var_124], eax
0x1401d65ef  test    eax, eax
0x1401d65f1  jns     short loc_1401D6660
0x1401d65f3  cmp     eax, 0C0000017h
0x1401d65f8  jz      loc_1401D6430
  ... truncated ...
```
