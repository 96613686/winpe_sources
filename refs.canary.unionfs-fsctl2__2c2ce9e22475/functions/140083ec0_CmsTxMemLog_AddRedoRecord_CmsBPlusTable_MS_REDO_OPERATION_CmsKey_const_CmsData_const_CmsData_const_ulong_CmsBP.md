# CmsTxMemLog::AddRedoRecord(CmsBPlusTable *,_MS_REDO_OPERATION,_CmsKey const *,_CmsData const *,_CmsData const *,ulong,CmsBPlusTable *,_EMS_REDO_FLAGS,uchar,long *)

- ea: `0x140083ec0`
- end: `0x140084738`
- name: `?AddRedoRecord@CmsTxMemLog@@QEAAJPEAVCmsBPlusTable@@W4_MS_REDO_OPERATION@@PEBU_CmsKey@@PEBU_CmsData@@3K0W4_EMS_REDO_FLAGS@@EPEAJ@Z`
- size: `2168`
- prototype: ``
- caller_count: `19`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140012e10`
- `0x140017c30`
- `0x14001a36c`
- `0x14001a680`
- `0x14001b120`
- `0x140024710`
- `0x140026350`
- `0x140027400`
- `0x140027540`
- `0x140027ee8`
- `0x140028040`
- `0x14006dc40`
- `0x1400825e0`
- `0x140082920`
- `0x140097970`
- `0x140098b90`
- `0x140099bb0`
- `0x140099ec4`
- `0x1400cc660`

## callees

- `0x14005e580`
- `0x140060a4c`
- `0x140083ec0`
- `0x140084740`
- `0x140084d5c`
- `0x140092220`
- `0x140096620`
- `0x1400c8574`
- `0x14014e60c`
- `0x14014e878`
- `0x1401556d4`
- `0x140172940`
- `0x1401e9ce0`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1401f7fb7`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f7fb7`
- `ntoskrnl!KeSetEvent` at `0x1400846a9`
- `ntoskrnl!KeSetEvent` at `0x1400846a9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008436e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008436e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008464a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008464a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400840c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400840c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008412e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008412e`
- `ntoskrnl!ExAllocatePool2` at `0x140084239`
- `ntoskrnl!ExAllocatePool2` at `0x1400842ae`
- `ntoskrnl!ExAllocatePool2` at `0x140084239`
- `ntoskrnl!ExAllocatePool2` at `0x1400842ae`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140084271`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140084271`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f7f6a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f7f6a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140084203`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140084203`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f7ffc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f7ffc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140084667`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140084667`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084336`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008437f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400846db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084336`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008437f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400846db`

## string_xrefs

- `0x1400842be`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsTxMemLog::AddRedoRecord(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        _DWORD *a4,
        _DWORD *a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        char a10,
        volatile signed __int32 *a11)
{
  __int64 v12; // r11
  __int64 v13; // r12
  _DWORD *v14; // r10
  __int64 v15; // rax
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rax
  _DWORD *v19; // rcx
  __int64 v20; // r15
  int v21; // edi
  unsigned int v22; // ebx
  __int64 v23; // rdx
  __int64 v24; // r8
  struct _SmsRedoBlock *v25; // r13
  unsigned int v26; // ebx
  __int64 v27; // rcx
  __int64 v28; // r14
  char v29; // di
  __int64 v30; // rcx
  unsigned int v31; // esi
  __int64 v32; // r12
  __int64 v33; // rbx
  KSPIN_LOCK *v34; // rdi
  KIRQL v35; // al
  __int64 v36; // r10
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned int v39; // r11d
  unsigned __int64 v40; // rbx
  unsigned __int64 v41; // rbx
  __int64 v42; // r8
  __int64 v43; // rbx
  struct _SLIST_ENTRY *v44; // r8
  struct _NPAGED_LOOKASIDE_LIST *v45; // rcx
  struct _SmsRedoBlock *Pool2; // rax
  __int64 EntryHeaderSize; // rdi
  __int64 v48; // rbx
  __int64 v49; // rdx
  __int64 v50; // rax
  bool v51; // zf
  __int64 v52; // rax
  __int64 v53; // rdx
  int v55; // ecx
  _QWORD *v56; // r9
  unsigned __int8 v57; // r8
  unsigned int v58; // edi
  __int64 v59; // rcx
  int v60; // r10d
  __int16 v61; // dx
  __int64 v62; // r11
  __int64 v63; // r8
  __int64 v64; // rax
  unsigned int v65; // ecx
  __int64 v66; // rax
  __int128 v67; // xmm1
  __int64 v68; // rdx
  int *v69; // rax
  __int64 v70; // rax
  __int64 LogMetadataAddress; // rax
  int v72; // ecx
  int v73; // eax
  struct _SmsRedoBlock *PreallocatedRedo; // rax
  struct _NPAGED_LOOKASIDE_LIST *v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // r14
  __int64 v78; // rsi
  __int64 v79; // rdi
  char LogFullPercentage; // bl
  int ActivityIdThread; // eax
  char v82; // [rsp+60h] [rbp-A0h]
  char v83; // [rsp+61h] [rbp-9Fh]
  char v84; // [rsp+62h] [rbp-9Eh]
  unsigned int v85; // [rsp+64h] [rbp-9Ch]
  unsigned __int64 v87; // [rsp+70h] [rbp-90h]
  struct _SmsRedoBlock **v89; // [rsp+90h] [rbp-70h] BYREF
  volatile signed __int32 *v90; // [rsp+98h] [rbp-68h]
  _QWORD *v91; // [rsp+A0h] [rbp-60h]
  __int64 v92; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v93; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v94; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v95; // [rsp+C0h] [rbp-40h]
  __int128 v96; // [rsp+D0h] [rbp-30h]
  int v97; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v98; // [rsp+E4h] [rbp-1Ch]
  __int16 v99; // [rsp+E6h] [rbp-1Ah]
  __int64 v100; // [rsp+E8h] [rbp-18h]
  _QWORD v101[10]; // [rsp+F0h] [rbp-10h]
  unsigned __int8 v102; // [rsp+140h] [rbp+40h]

  v12 = a6;
  v13 = a1;
  v90 = a11;
  v14 = a4;
  v15 = a2[3];
  v16 = a8;
  v91 = a2;
  v17 = a2[14];
  v18 = *(_QWORD *)(v15 + 72);
  v94 = a1;
  v19 = a5;
  v20 = v18 + 2880;
  v92 = v17;
  v93 = v18;
  v84 = 0;
  if ( a2 == *(_QWORD **)(v13 + 40) )
  {
    v82 = 1;
    v21 = 0;
    v22 = 56;
  }
  else
  {
    v56 = a2;
    v102 = *(_BYTE *)(v17 + 8) + 1;
    v57 = v102;
    v58 = v102 - 1;
    if ( v102 == 1 )
    {
      v82 = 0;
      v22 = 56;
    }
    else
    {
      do
      {
        v22 = 56;
        v82 = 0;
        v59 = *(_QWORD *)(v56[14] + 32LL);
        v60 = *(_DWORD *)(v59 + 8);
        v61 = *(_WORD *)(v59 + 12);
        v62 = *(_QWORD *)(v59 + 16);
        v63 = *(_QWORD *)(*(_QWORD *)v59 + 24LL);
        if ( (*(_DWORD *)(v63 + 44) & 1) != 0 )
        {
          v60 -= 8;
          v61 &= ~4u;
          v62 += 8;
        }
        WORD3(v95) = *(_WORD *)(v59 + 14);
        *(_QWORD *)&v96 = *(unsigned int *)(v63 + 16);
        v64 = v56[3];
        LODWORD(v95) = v60;
        WORD2(v95) = v61;
        *((_QWORD *)&v95 + 1) = v62;
        v65 = *(_DWORD *)(v64 + 16);
        v66 = 4LL * v58;
        *((_QWORD *)&v96 + 1) = v65;
        v67 = v96;
        *(_OWORD *)((char *)&v97 + v66 * 8) = v95;
        *(_OWORD *)&v101[v66] = v67;
        v56 = **(_QWORD ***)(v56[14] + 32LL);
        --v58;
      }
      while ( v58 );
      v57 = v102;
      v14 = a4;
      v12 = a6;
    }
    v21 = 0;
    v68 = v56[9] + 376LL;
    v101[1] = *(unsigned int *)(v56[3] + 16LL);
    v99 = WORD3(v95);
    v69 = &v97;
    v97 = 16;
    v98 = 0;
    v100 = v68;
    v101[0] = 57392;
    while ( v69 != &v97 + 8 * v57 )
    {
      v21 += ((*v69 + 23) & 0xFFFFFFF8) + 8;
      v69 += 8;
    }
    v19 = a5;
    v16 = a8;
  }
  if ( v14 )
    v22 = ((*v14 + 7) & 0xFFFFFFF8) + 64;
  if ( v19 )
    v22 += ((*v19 + 7) & 0xFFFFFFF8) + 8;
  v23 = 0;
  v24 = 0;
  if ( v12 )
    v23 = a7;
  if ( (_DWORD)v23 )
  {
    do
    {
      v70 = 2LL * (unsigned int)v24;
      v24 = (unsigned int)(v24 + 1);
      v22 += ((*(_DWORD *)(v12 + 8 * v70) + 7) & 0xFFFFFFF8) + 8;
    }
    while ( (unsigned int)v24 < (unsigned int)v23 );
  }
  if ( v16 )
  {
    v73 = CanonicalKeyLength(v16, v23, v24);
    v14 = a4;
    v16 = a8;
    v12 = a6;
    v22 += ((v73 + 15) & 0xFFFFFFF8) + 8;
  }
  v25 = *(struct _SmsRedoBlock **)(v13 + 32);
  v26 = (v21 + v22 + 7) & 0xFFFFFFF8;
  v85 = v26;
  if ( v25 && (v27 = *((unsigned int *)v25 + 7), *((_DWORD *)v25 + 6) - (int)v27 > v26) )
  {
    v28 = v27 + *((_QWORD *)v25 + 1);
    v29 = 1;
    v83 = 1;
    *(_OWORD *)v28 = 0;
    *(_OWORD *)(v28 + 16) = 0;
    *(_OWORD *)(v28 + 32) = 0;
    *(_QWORD *)(v28 + 48) = 0;
  }
  else
  {
    v29 = 0;
    v83 = 0;
    if ( !a10 )
      goto LABEL_39;
    v89 = 0;
    PreallocatedRedo = FindPreallocatedRedo((struct _SmsRedoBlock **)(v13 + 16), v26, &v89);
    v25 = PreallocatedRedo;
    if ( !PreallocatedRedo )
      goto LABEL_39;
    v14 = a4;
    v16 = a8;
    v12 = a6;
    *v89 = (struct _SmsRedoBlock *)*((_QWORD *)PreallocatedRedo + 6);
    v28 = *((_QWORD *)PreallocatedRedo + 2);
    *((_QWORD *)PreallocatedRedo + 6) = 0;
    v84 = 1;
  }
  if ( v28 )
    goto LABEL_17;
LABEL_39:
  Pool2 = (struct _SmsRedoBlock *)ExAllocatePool2(66, 72, 1766871885);
  v25 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, 0x48u);
  EntryHeaderSize = (unsigned int)LogGetEntryHeaderSize(*(_QWORD *)(v20 + 72), v26 + 8);
  v48 = qword_140262440 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( (unsigned int)EntryHeaderSize > *(_DWORD *)v48 )
  {
    v48 = 0;
    v49 = EntryHeaderSize + 16;
    goto LABEL_42;
  }
  if ( *(_BYTE *)(v48 + 8) )
  {
    v75 = (struct _NPAGED_LOOKASIDE_LIST *)(v48 + 64);
    if ( *(_BYTE *)(v48 + 9) )
      v50 = (__int64)ExAllocateFromNPagedLookasideList(v75);
    else
      v50 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v75);
LABEL_77:
    if ( v50 )
      goto LABEL_78;
    goto LABEL_65;
  }
  if ( (int)*(_QWORD *)(v48 + 88) > (int)HIDWORD(*(_QWORD *)(v48 + 88)) )
  {
    v55 = _InterlockedDecrement((volatile signed __int32 *)(v48 + 88));
    if ( v55 >= *(_DWORD *)(v48 + 92) && v55 >= 0 )
    {
      v50 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v48 + 64));
      goto LABEL_77;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v48 + 88));
  }
LABEL_65:
  v49 = *(unsigned int *)(v48 + 4);
LABEL_42:
  v50 = ExAllocatePool2(66, v49, 1766871885);
  if ( (v50 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( !v50 )
    goto LABEL_57;
LABEL_78:
  *(_QWORD *)v50 = v48;
  if ( v50 == -16 )
  {
LABEL_57:
    ExFreePoolWithTag(v25, 0);
    return 3221225626LL;
  }
  *(_QWORD *)v25 = v50 + 16;
  LogMetadataAddress = MlLogGetLogMetadataAddress(*(_QWORD *)(v20 + 72));
  *((_QWORD *)v25 + 1) = LogMetadataAddress;
  LogMetadataAddress += 8;
  *((_QWORD *)v25 + 2) = LogMetadataAddress;
  *(_OWORD *)LogMetadataAddress = 0;
  *(_OWORD *)(LogMetadataAddress + 16) = 0;
  *(_OWORD *)(LogMetadataAddress + 32) = 0;
  *(_QWORD *)(LogMetadataAddress + 48) = 0;
  v72 = EntryHeaderSize + *(_DWORD *)v25 - *((_DWORD *)v25 + 2);
  *(_QWORD *)((char *)v25 + 28) = 8;
  *((_DWORD *)v25 + 6) = v72;
  *((_DWORD *)v25 + 9) = EntryHeaderSize;
  v28 = *((_QWORD *)v25 + 2);
  if ( !v28 )
    return 3221225626LL;
  v26 = v85;
  v14 = a4;
  v16 = a8;
  v12 = a6;
  v29 = v83;
LABEL_17:
  FormatRedoRecord(v28, v91, v26, a3, *(unsigned __int8 *)(v92 + 8), v14, a5, v12, a7, v16, v82);
  v30 = v93;
  *(_DWORD *)(v28 + 44) = 0;
  *(_QWORD *)(v28 + 24) = *(_QWORD *)(v30 + 2112);
  *(_QWORD *)(v28 + 32) = *(_QWORD *)(v30 + 2120);
  if ( v84 )
  {
    if ( !v90 )
      goto LABEL_45;
LABEL_94:
    _InterlockedAdd(v90, 0xFFFFF000);
    *(_DWORD *)(v13 + 48) += 4096;
    *((_DWORD *)v25 + 10) = 4096;
    goto LABEL_45;
  }
  if ( v90 )
    goto LABEL_94;
  if ( !v29 )
  {
    v31 = (*((_DWORD *)v25 + 6) + 4095) & 0xFFFFF000;
    while ( 1 )
    {
      v32 = *(unsigned int *)(v20 + 288);
      v33 = *(_QWORD *)(v20 + 72);
      v34 = (KSPIN_LOCK *)(v33 + 3776);
      v35 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v33 + 3776));
      v36 = *(_QWORD *)(v33 + 3704);
      v37 = *(unsigned int *)(v33 + 32);
      if ( ML_LSN_INVALID == v36 )
      {
        v38 = *(unsigned int *)(v33 + 24);
        v39 = *(_DWORD *)(v33 + 3664);
        v87 = v39 * ((unsigned int)v37 - v38);
      }
      else
      {
        v87 = *(unsigned int *)(v33 + 3664) * (v37 + (unsigned int)v36 - (unsigned __int64)*(unsigned int *)(v33 + 24));
        v39 = *(_DWORD *)(v33 + 3664);
        LODWORD(v38) = *(_DWORD *)(v33 + 24);
      }
      v40 = ML_LSN_INVALID == v36
          ? (unsigned int)v38 + *(unsigned int *)(v33 + 3696) - (unsigned __int64)(unsigned int)v37
          : (unsigned int)v38 - (unsigned __int64)(unsigned int)v37;
      v41 = v39 * v40;
      KeReleaseSpinLock(v34, v35);
      if ( v31 + (unsigned int)v32 > v41 && !DbgIgnoreLogFull )
        break;
      if ( !*(_BYTE *)(*(_QWORD *)(v20 + 80) + 2816LL)
        && 100 * (v87 + v32) / (v41 + v87) >= (unsigned __int8)byte_14026207A )
      {
        KeSetEvent(&LazyWriterScanEvent, 0, 0);
      }
      if ( (_DWORD)v32 == _InterlockedCompareExchange((volatile signed __int32 *)(v20 + 288), v31 + v32, v32) )
      {
        v13 = v94;
        v26 = v85;
        v29 = v83;
        *(_DWORD *)(v94 + 48) += v31;
        *((_DWORD *)v25 + 10) = v31;
        goto LABEL_45;
      }
    }
    if ( dword_1402403A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
    {
      v77 = *(_QWORD *)CmsDurableLog::LastWrittenLsn(v20, &v94);
      v78 = *(_QWORD *)CmsDurableLog::GetOldestRecordReference(v20, &v93, 0);
      v79 = *(_QWORD *)CmsDurableLog::BaseLsn(v20, &v92);
      LogFullPercentage = CmsDurableLog::GetLogFullPercentage((CmsDurableLog *)v20);
      ActivityIdThread = IoGetActivityIdThread();
      McTemplateK0qqiii_EtwWriteTransfer(
        (unsigned int)MinstoreEventProvider_Context,
        (unsigned int)LogFullRedoLog,
        ActivityIdThread,
        v32,
        LogFullPercentage,
        v79,
        v78,
        v77);
    }
    v42 = *(_QWORD *)v25;
    if ( !*(_QWORD *)v25 )
      goto LABEL_60;
    v43 = *(_QWORD *)(v42 - 16);
    v44 = (struct _SLIST_ENTRY *)(v42 - 16);
    if ( !v43 )
      goto LABEL_93;
    if ( *(_BYTE *)(v43 + 8) )
    {
      v45 = (struct _NPAGED_LOOKASIDE_LIST *)(v43 + 64);
      if ( *(_BYTE *)(v43 + 9) )
        ExFreeToNPagedLookasideList(v45, v44);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v45, v44);
      goto LABEL_60;
    }
    v76 = *(_QWORD *)(v43 + 88);
    if ( (int)v76 < *(_DWORD *)(v43 + 80) || SHIDWORD(v76) >= (int)v76 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v43 + 64), v44);
      _InterlockedIncrement((volatile signed __int32 *)(v43 + 88));
    }
    else
    {
LABEL_93:
      ExFreePoolWithTag(v44, 0);
    }
LABEL_60:
    ExFreePoolWithTag(v25, 0);
    return 3221225864LL;
  }
LABEL_45:
  *((_DWORD *)v25 + 7) += v26;
  v51 = *(_QWORD *)v13 == 0;
  *(_QWORD *)(v13 + 40) = v91;
  if ( v51 )
    *(_QWORD *)v13 = v28;
  v52 = *(_QWORD *)(v13 + 8);
  if ( v52 )
    *(_QWORD *)(v52 + 48) = v28;
  *(_QWORD *)(v13 + 8) = v28;
  if ( !v29 )
  {
    if ( !*(_QWORD *)(v13 + 24) )
      *(_QWORD *)(v13 + 24) = v25;
    v53 = *(_QWORD *)(v13 + 32);
    if ( v53 )
    {
      **(_DWORD **)(v53 + 8) = *(_DWORD *)(v53 + 28) - 8;
      *(_DWORD *)(*(_QWORD *)(v53 + 8) + 4LL) = *(_DWORD *)(v53 + 16) - *(_DWORD *)(v53 + 8);
      *(_DWORD *)(v53 + 32) = *(_DWORD *)(v53 + 28);
      *(_QWORD *)(*(_QWORD *)(v13 + 32) + 48LL) = v25;
    }
    *(_QWORD *)(v13 + 32) = v25;
  }
  return 0;
}

```

## disassembly

```asm
0x140083ec0  push    rbp
0x140083ec2  push    rbx
0x140083ec3  push    rsi
0x140083ec4  push    rdi
0x140083ec5  push    r12
0x140083ec7  push    r13
0x140083ec9  push    r15
0x140083ecb  lea     rbp, [rsp-60h]
0x140083ed0  sub     rsp, 160h
0x140083ed7  mov     rax, cs:__security_cookie
0x140083ede  xor     rax, rsp
0x140083ee1  mov     [rbp+90h+var_40], rax
0x140083ee5  mov     rax, [rbp+90h+arg_50]
0x140083eec  mov     rbx, rdx
0x140083eef  mov     r11, [rbp+90h+arg_28]
0x140083ef6  mov     r12, rcx
0x140083ef9  mov     [rbp+90h+var_F8], rax
0x140083efd  mov     r10, r9
0x140083f00  mov     [rsp+190h+var_118], r9
0x140083f05  mov     rax, [rbx+18h]
0x140083f09  mov     r9, [rbp+90h+arg_38]
0x140083f10  mov     [rbp+90h+var_F0], rdx
0x140083f14  mov     rdx, [rdx+70h]
0x140083f18  mov     rax, [rax+48h]
0x140083f1c  mov     [rbp+90h+var_D8], rcx
0x140083f20  mov     rcx, [rbp+90h+arg_20]
0x140083f27  mov     [rsp+190h+var_128], r8d
0x140083f2c  lea     r15, [rax+0B40h]
0x140083f33  mov     [rsp+190h+var_120], rcx
0x140083f38  mov     [rbp+90h+var_108], r11
0x140083f3c  mov     [rbp+90h+var_110], r9
0x140083f40  mov     [rbp+90h+var_E8], rdx
0x140083f44  mov     [rbp+90h+var_E0], rax
0x140083f48  mov     [rsp+190h+var_12E], 0
0x140083f4d  cmp     rbx, [r12+28h]
0x140083f52  jnz     loc_1400843D2
0x140083f58  xor     esi, esi
0x140083f5a  mov     [rsp+190h+var_130], 1
0x140083f5f  mov     edi, esi
0x140083f61  mov     ebx, 38h ; '8'
0x140083f66  jmp     short loc_140083F71
0x140083f68  mov     rcx, [rsp+190h+var_120]
0x140083f6d  mov     r9, [rbp+90h+var_110]
0x140083f71  test    r10, r10
0x140083f74  jz      short loc_140083F82
0x140083f76  mov     ebx, [r10]
0x140083f79  add     ebx, 7
0x140083f7c  and     ebx, 0FFFFFFF8h
0x140083f7f  add     ebx, 40h ; '@'
0x140083f82  test    rcx, rcx
0x140083f85  jz      short loc_140083F94
0x140083f87  mov     eax, [rcx]
0x140083f89  add     ebx, 8
0x140083f8c  add     eax, 7
0x140083f8f  and     eax, 0FFFFFFF8h
0x140083f92  add     ebx, eax
0x140083f94  test    r11, r11
0x140083f97  mov     edx, esi
0x140083f99  mov     r8d, esi
0x140083f9c  cmovnz  edx, [rbp+90h+arg_30]
0x140083fa3  test    edx, edx
0x140083fa5  jnz     loc_140084510
0x140083fab  test    r9, r9
0x140083fae  jnz     loc_1400845CD
0x140083fb4  mov     r13, [r12+20h]
0x140083fb9  add     ebx, 7
0x140083fbc  add     ebx, edi
0x140083fbe  mov     [rsp+190h+arg_10], r14
0x140083fc6  and     ebx, 0FFFFFFF8h
0x140083fc9  mov     [rsp+190h+var_12C], ebx
0x140083fcd  test    r13, r13
0x140083fd0  jz      loc_140084214
0x140083fd6  mov     ecx, [r13+1Ch]
0x140083fda  mov     eax, [r13+18h]
0x140083fde  sub     eax, ecx
0x140083fe0  cmp     eax, ebx
0x140083fe2  jbe     loc_140084214
0x140083fe8  mov     r14, [r13+8]
0x140083fec  xorps   xmm0, xmm0
0x140083fef  add     r14, rcx
0x140083ff2  mov     dil, 1
0x140083ff5  xor     eax, eax
0x140083ff7  mov     [rsp+190h+var_12F], dil
0x140083ffc  movups  xmmword ptr [r14], xmm0
0x140084000  movups  xmmword ptr [r14+10h], xmm0
0x140084005  movups  xmmword ptr [r14+20h], xmm0
0x14008400a  mov     [r14+30h], rax
0x14008400e  test    r14, r14
0x140084011  jz      loc_140084229
0x140084017  movzx   ecx, [rsp+190h+var_130]
0x14008401c  mov     r8d, ebx
0x14008401f  mov     rax, [rbp+90h+var_E8]
0x140084023  mov     rdx, [rbp+90h+var_F0]
0x140084027  mov     [rsp+190h+var_140], cl
0x14008402b  mov     ecx, [rbp+90h+arg_30]
0x140084031  movzx   eax, byte ptr [rax+8]
0x140084035  mov     [rsp+190h+var_148], r9
0x14008403a  mov     r9d, [rsp+190h+var_128]
0x14008403f  mov     [rsp+190h+var_150], ecx
0x140084043  mov     rcx, [rsp+190h+var_120]
0x140084048  mov     [rsp+190h+var_158], r11
0x14008404d  mov     [rsp+190h+var_160], rcx
0x140084052  mov     rcx, r14
0x140084055  mov     [rsp+190h+var_168], r10
0x14008405a  mov     [rsp+190h+var_170], eax
0x14008405e  call    ?FormatRedoRecord@@YAXPEAU_SmsRedoRecord@@PEAVCmsBPlusTable@@KW4_MS_REDO_OPERATION@@KPEBU_CmsKey@@PEBU_CmsData@@4K1E@Z; FormatRedoRecord(_SmsRedoRecord *,CmsBPlusTable *,ulong,_MS_REDO_OPERATION,ulong,_CmsKey const *,_CmsData const *,_CmsData const *,ulong,CmsBPlusTable *,uchar)
0x140084063  cmp     [rsp+190h+var_12E], 0
0x140084068  mov     rcx, [rbp+90h+var_E0]
0x14008406c  mov     [r14+2Ch], esi
0x140084070  mov     rax, [rcx+840h]
0x140084077  mov     [r14+18h], rax
0x14008407b  mov     rax, [rcx+848h]
0x140084082  mov     [r14+20h], rax
0x140084086  mov     rax, [rbp+90h+var_F8]
0x14008408a  jnz     loc_1400842CB
0x140084090  test    rax, rax
0x140084093  jnz     loc_1400846EC
0x140084099  test    dil, dil
0x14008409c  jnz     loc_1400842D4
0x1400840a2  mov     esi, [r13+18h]
0x1400840a6  add     esi, 0FFFh
0x1400840ac  and     esi, 0FFFFF000h
0x1400840b2  mov     r12d, [r15+120h]
0x1400840b9  mov     rbx, [r15+48h]
0x1400840bd  lea     rdi, [rbx+0EC0h]
0x1400840c4  mov     rcx, rdi; SpinLock
0x1400840c7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400840ce  nop     dword ptr [rax+rax+00h]
0x1400840d3  mov     r10, [rbx+0E78h]
0x1400840da  movzx   r9d, al
0x1400840de  mov     rcx, cs:ML_LSN_INVALID
0x1400840e5  mov     edx, [rbx+20h]
0x1400840e8  cmp     rcx, r10
0x1400840eb  jnz     loc_14008418D
0x1400840f1  mov     r8d, [rbx+18h]
0x1400840f5  mov     eax, edx
0x1400840f7  mov     r11d, [rbx+0E50h]
0x1400840fe  sub     rax, r8
0x140084101  imul    rax, r11
0x140084105  mov     [rsp+190h+var_120], rax
0x14008410a  mov     eax, edx
0x14008410c  cmp     rcx, r10
0x14008410f  jnz     short loc_140084185
0x140084111  mov     ebx, [rbx+0E70h]
0x140084117  sub     rbx, rax
0x14008411a  mov     eax, r8d
0x14008411d  add     rbx, rax
0x140084120  mov     eax, r11d
0x140084123  movzx   edx, r9b; NewIrql
0x140084127  mov     rcx, rdi; SpinLock
0x14008412a  imul    rbx, rax
0x14008412e  call    cs:__imp_KeReleaseSpinLock
0x140084135  nop     dword ptr [rax+rax+00h]
0x14008413a  lea     edi, [rsi+r12]
0x14008413e  mov     eax, edi
0x140084140  cmp     rax, rbx
0x140084143  ja      short loc_1400841B4
0x140084145  mov     rax, [r15+50h]
0x140084149  cmp     byte ptr [rax+0B00h], 0
0x140084150  jz      loc_140084678
0x140084156  nop
0x140084157  mov     eax, r12d
0x14008415a  lock cmpxchg [r15+120h], edi
0x140084163  nop
0x140084164  jnz     loc_1400840B2
0x14008416a  mov     r12, [rbp+90h+var_D8]
0x14008416e  mov     ebx, [rsp+190h+var_12C]
0x140084172  movzx   edi, [rsp+190h+var_12F]
0x140084177  add     [r12+30h], esi
0x14008417c  mov     [r13+28h], esi
0x140084180  jmp     loc_1400842D4
0x140084185  mov     ebx, r8d
0x140084188  sub     rbx, rax
0x14008418b  jmp     short loc_140084120
0x14008418d  mov     r8d, [rbx+0E50h]
0x140084194  mov     eax, [rbx+18h]
0x140084197  mov     r11d, r10d
0x14008419a  sub     r11, rax
0x14008419d  add     r11, rdx
0x1400841a0  imul    r11, r8
0x1400841a4  mov     [rsp+190h+var_120], r11
0x1400841a9  mov     r11d, r8d
0x1400841ac  mov     r8d, eax
0x1400841af  jmp     loc_14008410A
0x1400841b4  cmp     cs:?DbgIgnoreLogFull@@3KA, 0; ulong DbgIgnoreLogFull
0x1400841bb  jnz     short loc_140084145
0x1400841bd  cmp     cs:dword_1402403A4, 1
0x1400841c4  jz      loc_1400845BB
0x1400841ca  mov     r8, [r13+0]
0x1400841ce  test    r8, r8
0x1400841d1  jz      loc_14008437A
0x1400841d7  mov     rbx, [r8-10h]
0x1400841db  add     r8, 0FFFFFFFFFFFFFFF0h
0x1400841df  test    rbx, rbx
0x1400841e2  jz      loc_1400846D6
0x1400841e8  cmp     byte ptr [rbx+8], 0
0x1400841ec  jz      loc_1400846BA
0x1400841f2  cmp     byte ptr [rbx+9], 0
0x1400841f6  lea     rcx, [rbx+40h]; Lookaside
0x1400841fa  mov     rdx, r8; Entry
0x1400841fd  jnz     loc_14008436E
0x140084203  call    cs:__imp_ExFreeToPagedLookasideList
0x14008420a  nop     dword ptr [rax+rax+00h]
0x14008420f  jmp     loc_14008437A
0x140084214  xor     dil, dil
0x140084217  mov     [rsp+190h+var_12F], dil
0x14008421c  cmp     [rbp+90h+arg_48], dil
0x140084223  jnz     loc_1400845F2
0x140084229  mov     edx, 48h ; 'H'
0x14008422e  mov     ecx, 42h ; 'B'
0x140084233  mov     r8d, 6950534Dh
0x140084239  call    cs:__imp_ExAllocatePool2
0x140084240  nop     dword ptr [rax+rax+00h]
0x140084245  mov     r13, rax
0x140084248  test    rax, rax
0x14008424b  jz      loc_140084342
0x140084251  xor     edx, edx; Val
0x140084253  mov     r8d, 48h ; 'H'; Size
0x140084259  mov     rcx, rax; void *
0x14008425c  call    memset
0x140084261  mov     rcx, [r15+48h]
0x140084265  lea     edx, [rbx+8]
0x140084268  call    LogGetEntryHeaderSize
0x14008426d  xor     ecx, ecx; ProcNumber
0x14008426f  mov     edi, eax
0x140084271  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140084278  nop     dword ptr [rax+rax+00h]
0x14008427d  xor     edx, edx
0x14008427f  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140084285  lea     rbx, [rdx+rdx*2]
0x140084289  shl     rbx, 6
0x14008428d  add     rbx, cs:qword_140262440
0x140084294  cmp     edi, [rbx]
0x140084296  jbe     loc_140084392
0x14008429c  mov     rbx, rsi
0x14008429f  lea     rdx, [rdi+10h]
0x1400842a3  mov     ecx, 42h ; 'B'
0x1400842a8  mov     r8d, 6950534Dh
0x1400842ae  call    cs:__imp_ExAllocatePool2
0x1400842b5  nop     dword ptr [rax+rax+00h]
0x1400842ba  test    al, 0Fh
0x1400842bc  jz      short loc_140084328
0x1400842be  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1400842c5  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x1400842cb  test    rax, rax
0x1400842ce  jnz     loc_1400846EC
0x1400842d4  add     [r13+1Ch], ebx
0x1400842d8  cmp     qword ptr [r12], 0
0x1400842dd  mov     rax, [rbp+90h+var_F0]
0x1400842e1  mov     [r12+28h], rax
0x1400842e6  jnz     short loc_1400842EC
0x1400842e8  mov     [r12], r14
0x1400842ec  mov     rax, [r12+8]
0x1400842f1  test    rax, rax
0x1400842f4  jz      short loc_1400842FA
0x1400842f6  mov     [rax+30h], r14
0x1400842fa  mov     [r12+8], r14
0x1400842ff  test    dil, dil
0x140084302  jnz     short loc_140084324
0x140084304  cmp     qword ptr [r12+18h], 0
0x14008430a  jnz     short loc_140084311
0x14008430c  mov     [r12+18h], r13
0x140084311  mov     rdx, [r12+20h]
0x140084316  test    rdx, rdx
0x140084319  jnz     loc_14008470B
0x14008431f  mov     [r12+20h], r13
0x140084324  xor     eax, eax
0x140084326  jmp     short loc_140084347
0x140084328  test    rax, rax
0x14008432b  jnz     loc_14008453C
0x140084331  xor     edx, edx; Tag
0x140084333  mov     rcx, r13; P
0x140084336  call    cs:__imp_ExFreePoolWithTag
0x14008433d  nop     dword ptr [rax+rax+00h]
0x140084342  mov     eax, 0C000009Ah
0x140084347  mov     r14, [rsp+190h+arg_10]
0x14008434f  mov     rcx, [rbp+90h+var_40]
0x140084353  xor     rcx, rsp; StackCookie
0x140084356  call    __security_check_cookie
0x14008435b  add     rsp, 160h
0x140084362  pop     r15
0x140084364  pop     r13
0x140084366  pop     r12
0x140084368  pop     rdi
0x140084369  pop     rsi
0x14008436a  pop     rbx
0x14008436b  pop     rbp
0x14008436c  retn
0x14008436e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140084375  nop     dword ptr [rax+rax+00h]
0x14008437a  xor     edx, edx; Tag
0x14008437c  mov     rcx, r13; P
0x14008437f  call    cs:__imp_ExFreePoolWithTag
0x140084386  nop     dword ptr [rax+rax+00h]
0x14008438b  mov     eax, 0C0000188h
0x140084390  jmp     short loc_140084347
0x140084392  cmp     byte ptr [rbx+8], 0
0x140084396  jnz     loc_14008463C
0x14008439c  mov     rcx, [rbx+58h]
0x1400843a0  mov     rax, rcx
  ... truncated ...
```
