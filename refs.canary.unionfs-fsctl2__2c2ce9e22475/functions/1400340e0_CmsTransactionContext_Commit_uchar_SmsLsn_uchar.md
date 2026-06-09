# CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)

- ea: `0x1400340e0`
- end: `0x140034a9f`
- name: `?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z`
- size: `2495`
- prototype: `__int64 __fastcall(CmsTransactionContext *__hidden this, unsigned __int8, struct _SmsLsn *, unsigned __int8)`
- caller_count: `91`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001395c`
- `0x140013bec`
- `0x140013dc4`
- `0x140013ee4`
- `0x140014060`
- `0x140014130`
- `0x140014428`
- `0x140014510`
- `0x1400145f4`
- `0x140033550`
- `0x140033b60`
- `0x14004b0a8`
- `0x1400523d0`
- `0x1400531a0`
- `0x140055200`
- `0x140055660`
- `0x140055af0`
- `0x140056ee0`
- `0x14005b1a0`
- `0x1400635c8`
- `0x1400638a0`
- `0x140064250`
- `0x140064480`
- `0x140065210`
- `0x140065c34`
- `0x14007141c`
- `0x1400821b0`
- `0x140083174`
- `0x14008de10`
- `0x14008fc90`
- `0x1400ac0c0`
- `0x1400bf27c`
- `0x1400c5f44`
- `0x1400cba18`
- `0x1400ccae0`
- `0x1400d0490`
- `0x1400d26b8`
- `0x1400d3a18`
- `0x1400d3b58`
- `0x1400d4788`
- `0x1401111a8`
- `0x140111b0c`
- `0x140113d90`
- `0x1401184a0`
- `0x1401184f0`
- `0x1401186f0`
- `0x14011b264`
- `0x14011f2c8`
- `0x140121058`
- `0x140121a00`

## callees

- `0x14001cbc0`
- `0x140024d20`
- `0x14002f4b0`
- `0x140031ae0`
- `0x140031d40`
- `0x1400340e0`
- `0x1400352e8`
- `0x140035300`
- `0x140036df0`
- `0x14005f694`
- `0x14005fa40`
- `0x1400770d0`
- `0x140078bd0`
- `0x1400823f8`
- `0x140087ea0`
- `0x14009c260`
- `0x1400c3a64`
- `0x1400cc588`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x1400343ed`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400348fd`
- `ntoskrnl!KdDebuggerEnabled` at `0x140034913`
- `ntoskrnl!KdDebuggerEnabled` at `0x140034929`
- `ntoskrnl!KdDebuggerEnabled` at `0x14003493f`
- `ntoskrnl!KdDebuggerEnabled` at `0x140034955`
- `ntoskrnl!KdDebuggerEnabled` at `0x14003496b`
- `ntoskrnl!KdDebuggerEnabled` at `0x140034981`
- `ntoskrnl!KdDebuggerEnabled` at `0x140034997`
- `ntoskrnl!KdDebuggerEnabled` at `0x140034a06`
- `ntoskrnl!KdDebuggerEnabled` at `0x140034a37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140034547`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140034547`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140034636`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140034636`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1e6e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1e6e`
- `ntoskrnl!KeInitializeEvent` at `0x140034678`
- `ntoskrnl!KeInitializeEvent` at `0x140034678`
- `ntoskrnl!ExReleaseFastResource` at `0x140034703`
- `ntoskrnl!ExReleaseFastResource` at `0x140034703`
- `ntoskrnl!ExReleasePushLockEx` at `0x140034a26`
- `ntoskrnl!ExReleasePushLockEx` at `0x140034a26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003433b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034a8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003433b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034a8e`

## pseudocode

```c
__int64 __fastcall CmsTransactionContext::Commit(
        CmsTransactionContext *this,
        struct CmsStream *a2,
        struct SmsPage **a3,
        __int64 a4)
{
  __int64 v4; // rax
  CmsTransactionContext **v5; // r14
  char v6; // r13
  unsigned int v8; // r12d
  volatile signed __int64 *v9; // rcx
  CmsReferenced **v10; // rdx
  unsigned __int64 v11; // rax
  int v12; // ecx
  __int64 v13; // rcx
  struct _LIST_ENTRY *v14; // rsi
  CmsTransactionContext *v15; // r15
  struct CmsBPlusTable *i; // r8
  unsigned __int8 v17; // r9
  CmsTxMemLog *v18; // rcx
  struct _SmsFlushWaiter *v19; // rdi
  CmsVolume *v20; // rsi
  CmsDurableLog *v21; // rcx
  CmsTransactionContext **v22; // rdi
  CmsTransactionContext *v23; // r15
  CmsTransactionContext ***v24; // rdi
  CmsTransactionContext ***v25; // rsi
  CmsTransactionContext **v26; // rax
  CmsTransactionContext **v27; // rcx
  CmsTransactionContext ***v28; // rcx
  __int64 v29; // rax
  CmsTransactionContext **v30; // rax
  bool v31; // zf
  char v32; // si
  __int64 v33; // rdi
  char *v34; // r14
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rcx
  CmsVolumeContainer *v40; // rcx
  struct SmsUndoRecord *v41; // rcx
  __int64 v42; // rax
  __int64 v44; // rsi
  struct _SLIST_ENTRY *v45; // r8
  struct _NPAGED_LOOKASIDE_LIST *v46; // rcx
  void *v47; // rdx
  struct _LIST_ENTRY *v48; // rdi
  struct _LIST_ENTRY *v49; // r14
  struct _LIST_ENTRY *v50; // rdx
  bool v51; // al
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  CmsTransactionContext *v60; // rax
  CmsTransactionContext **v61; // rcx
  CmsTransactionContext *v62; // rax
  struct _LIST_ENTRY *v63; // rax
  int v64; // eax
  __int64 v65; // rdi
  struct _LIST_ENTRY *v66; // r8
  CmsReferenced **v67; // r9
  __int64 v68; // rcx
  volatile signed __int32 *v69; // rdx
  CmsReferenced *v70; // rdi
  unsigned __int8 v71; // r8
  struct _LIST_ENTRY v72; // [rsp+40h] [rbp-89h] BYREF
  __int64 v73; // [rsp+50h] [rbp-79h]
  CmsVolume *v74; // [rsp+58h] [rbp-71h]
  CmsReferenced *v75; // [rsp+60h] [rbp-69h] BYREF
  CmsReferenced **v76; // [rsp+78h] [rbp-51h]
  _BYTE v77[96]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v78; // [rsp+E8h] [rbp+1Fh]
  struct _SmsFlushWaiter *v79; // [rsp+130h] [rbp+67h]
  char v80; // [rsp+138h] [rbp+6Fh]
  struct _SmsLsn *v81; // [rsp+140h] [rbp+77h]

  v81 = (struct _SmsLsn *)a3;
  v4 = *(_QWORD *)this;
  v5 = 0;
  LODWORD(a3) = (unsigned __int8)*(_QWORD *)this >> 7;
  v75 = 0;
  v6 = a4;
  v80 = (char)a3;
  v8 = 0;
  if ( (v4 & 0x20) != 0 && *((_QWORD *)this + 18) )
  {
    LOBYTE(a3) = 1;
    v80 = 1;
  }
  v9 = (volatile signed __int64 *)*((_QWORD *)this + 1);
  v74 = (CmsVolume *)v9;
  if ( !v9 )
    goto LABEL_24;
  memset(v77, 0, 24);
  v10 = &v75;
  if ( !(_BYTE)a3 )
    v10 = 0;
  v11 = *((_QWORD *)this + 25);
  v76 = v10;
  memset(&v77[24], 0, 56);
  if ( v11 )
    _InterlockedAdd64(v9 + 477, v11);
  *((_QWORD *)this + 25) = 0;
  if ( (_BYTE)a4 )
  {
    memset(v77, 0, 80);
    v79 = (struct _SmsFlushWaiter *)v77;
    KeInitializeEvent((PRKEVENT)&v77[32], NotificationEvent, 0);
  }
  else
  {
    v79 = 0;
  }
  if ( *((_BYTE *)this + 131) != *((_BYTE *)this + 130) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( *((_BYTE *)this + 131) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( *((_BYTE *)this + 132) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( *((_BYTE *)this + 130) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( (*((_WORD *)this + 106) || *((_WORD *)this + 107)) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v12 = *(_DWORD *)this;
  *(_WORD *)((char *)this + 131) = 0;
  v13 = v12 & 0x1000;
  *((_BYTE *)this + 130) = 0;
  v14 = (struct _LIST_ENTRY *)*((_QWORD *)this + 103);
  v15 = (CmsTransactionContext *)((char *)this + 824);
  v72.Blink = &v72;
  v72.Flink = &v72;
  v73 = (unsigned int)v13;
  while ( 1 )
  {
    while ( v14 != (struct _LIST_ENTRY *)v15 )
    {
      v48 = v14;
      v49 = v14 - 1;
      v50 = v14;
      v14 = v14->Flink;
      if ( v13 )
      {
LABEL_68:
        Flink = v48->Flink;
        if ( v48->Flink->Blink != v48
          || (Blink = v49[1].Blink, Blink->Flink != v50)
          || (Blink->Flink = Flink, Flink->Blink = Blink, v54 = v72.Flink, v72.Flink->Blink != &v72) )
        {
LABEL_71:
          __fastfail(3u);
        }
        v48->Flink = v72.Flink;
        v48->Blink = &v72;
        v54->Blink = v48;
        v72.Flink = v48;
        if ( LOBYTE(v49[9].Flink) )
          --*((_DWORD *)this + 215);
        else
          --*((_DWORD *)this + 214);
        v63 = v49[2].Flink;
        if ( v63[41].Blink == v49 )
          v63[41].Blink = 0;
        v64 = (int)v49[6].Blink;
        if ( (v64 & 4) != 0 )
        {
          v65 = *((_QWORD *)this + 108);
          LOBYTE(a4) = 1;
          v66 = v49[8].Flink;
          v78 = 0;
          MsDeleteElementGenericTableAvlEx<MST_AVL_DO_NOT_FREE_PROTOTYPE>(v65, v50, v66, a4);
          ++*(_DWORD *)(v65 + 40);
          LODWORD(v49[6].Blink) &= ~4u;
          v64 = (int)v49[6].Blink;
        }
        if ( (v64 & 0x10) != 0 )
          _InterlockedDecrement((volatile signed __int32 *)&v49[2].Flink[6].Flink[6].Blink + 1);
        LODWORD(v49[6].Blink) |= 0x20u;
        v13 = v73;
      }
      else
      {
        v51 = CmsPinCache::TransferOneCachedPin(
                (CmsTransactionContext *)((char *)this + 824),
                this,
                (struct CmsCachedPin *)v49,
                (struct CmsBPlusTable *)v49[2].Blink[2].Flink,
                &v72);
        v13 = v73;
        if ( !v51 )
        {
          v50 = v48;
          goto LABEL_68;
        }
      }
    }
    if ( v15 != (CmsTransactionContext *)((char *)this + 824) )
      break;
    v14 = (struct _LIST_ENTRY *)*((_QWORD *)this + 105);
    v15 = (CmsTransactionContext *)((char *)this + 840);
  }
  v5 = 0;
  v8 = 0;
  CmsPinCache::DeleteDoomedCachedPins(this, &v72);
  if ( *((_QWORD *)this + 18) )
  {
    v67 = v76;
    if ( v76 )
    {
      for ( i = 0;
            (unsigned int)i < 0xD && *((_QWORD *)this + (unsigned int)i + 53);
            i = (struct CmsBPlusTable *)(unsigned int)((_DWORD)i + 1) )
      {
        if ( !CmsBPlusTable::HasGlobalBindingSemantics(*((CmsBPlusTable **)this + (unsigned int)i + 53)) )
        {
          *v67 = (CmsReferenced *)v69;
          _InterlockedIncrement(v69 + 2);
          goto LABEL_159;
        }
      }
      *v67 = 0;
    }
LABEL_159:
    CmsBPlusTable::CommitUndoRecords(this, 0, i, (unsigned __int8)v67);
  }
  v18 = (CmsTxMemLog *)*((_QWORD *)this + 52);
  if ( *(_QWORD *)v18 || v6 )
  {
    v19 = v79;
    v20 = v74;
    CmsVolume::CommitTransactionLog(v74, this, v6, v17, v6, v79, v81);
  }
  else
  {
    v20 = v74;
    CmsTxMemLog::DiscardPendingRecords(v18, (CmsVolume *)((char *)v74 + 2880));
    v19 = v79;
  }
  if ( v19 )
    CmsDurableLog::WaitForLogFlush(v21, (struct _SmsFlushWaiter *)v77);
  if ( v6 && (*((_DWORD *)v20 + 865) & 0x20000000) != 0 )
    v8 = -1073741202;
LABEL_24:
  v22 = (CmsTransactionContext **)*((_QWORD *)this + 101);
  if ( v22 != (CmsTransactionContext **)((char *)this + 808) )
  {
    do
    {
      v23 = *v22;
      v5 = v22 - 14;
      if ( v22 != (CmsTransactionContext **)112 )
      {
        a3 = v5 + 19;
        if ( v5[19] )
          CmsVolume::Unpin(*((CmsVolumeContainer ***)this + 1), this, a3, 3u);
        v60 = *v22;
        if ( *v22 )
        {
          if ( *((CmsTransactionContext ***)v60 + 1) != v22 )
            goto LABEL_71;
          v61 = (CmsTransactionContext **)v22[1];
          if ( *v61 != (CmsTransactionContext *)v22 )
            goto LABEL_71;
          *v61 = v60;
          *((_QWORD *)v60 + 1) = v61;
          *(_OWORD *)v22 = 0;
        }
        v5[13] = 0;
        v5[12] = 0;
        v62 = v5[16];
        v5 = 0;
        if ( v62 )
          *(_QWORD *)v62 = 0;
      }
      v22 = (CmsTransactionContext **)v23;
    }
    while ( v23 != (CmsTransactionContext *)((char *)this + 808) );
  }
  if ( *((_DWORD *)this + 49) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v24 = (CmsTransactionContext ***)((char *)this + 664);
  v25 = (CmsTransactionContext ***)((char *)this + 792);
  while ( 1 )
  {
    v26 = *v25;
    if ( *v25 == (CmsTransactionContext **)v25 )
      break;
    if ( v26[1] != (CmsTransactionContext *)v25 )
      goto LABEL_71;
    v27 = (CmsTransactionContext **)*v26;
    if ( *((CmsTransactionContext ***)*v26 + 1) != v26 )
      goto LABEL_71;
    *v25 = v27;
    v27[1] = (CmsTransactionContext *)v25;
    v28 = (CmsTransactionContext ***)(v26 - 2);
    v29 = (__int64)*(v26 - 1);
    if ( v29 )
      *(_DWORD *)(v29 + 76) &= ~1u;
    v28[1] = v5;
    *v28 = v5;
    if ( v28 )
      ExFreePoolWithTag(v28, 0);
  }
  for ( ; v24 != v25; v24 += 4 )
  {
    v30 = v24[1];
    if ( v30 )
      *((_DWORD *)v30 + 19) &= ~1u;
    v24[1] = v5;
    *v24 = v5;
  }
  v31 = *((_QWORD *)this + 21) == 0;
  *((_DWORD *)this + 49) = (_DWORD)v5;
  *((_QWORD *)this + 13) = v5;
  if ( !v31 )
  {
    CmsTransactionContext::ReleaseReserveAllocationMap(this, a2);
    *((_QWORD *)this + 21) = v5;
  }
  v32 = (*(_QWORD *)this & 0x4000000000000LL) != 0;
  *(_QWORD *)this &= 0x13C023BC97BC31uLL;
  if ( *((_BYTE *)this + 131) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v33 = *((unsigned __int8 *)this + 132);
  if ( (unsigned int)v33 < 0xD )
  {
    do
    {
      v34 = (char *)this + 8 * v33;
      v35 = *((_QWORD *)v34 + 53);
      if ( !v35 )
        break;
      if ( *((_BYTE *)this + 2 * v33 + 528) || *((_BYTE *)this + 2 * v33 + 529) )
        ExReleasePushLockEx(*(_QWORD *)(v35 + 112) + 88LL, 0);
      v55 = *((_QWORD *)v34 + 53);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v55 + 8), 0xFFFFFFFF) == 1 && v55 )
        (**(void (__fastcall ***)(__int64, __int64))v55)(v55, 1);
      v33 = (unsigned int)(v33 + 1);
    }
    while ( (unsigned int)v33 < 0xD );
    v5 = 0;
  }
  v36 = *((unsigned __int8 *)this + 132);
  *((_QWORD *)this + v36 + 53) = v5;
  *((_WORD *)this + v36 + 264) = 0;
  if ( (_BYTE)KdDebuggerEnabled && *((_BYTE *)this + 131) != *((_BYTE *)this + 130) )
    __debugbreak();
  v37 = *((unsigned __int8 *)this + 131);
  if ( (unsigned int)v37 < *((unsigned __int8 *)this + 133) )
  {
    while ( 1 )
    {
      v56 = *((_QWORD *)this + v37 + 70);
      if ( !v56 )
      {
LABEL_95:
        v5 = 0;
        break;
      }
      if ( v56 == *((_QWORD *)this + 15) )
        *((_QWORD *)this + 15) = 0;
      v57 = *((_QWORD *)this + v37 + 70);
      if ( (*(_BYTE *)(v57 + 14) & 0x40) != 0 || (*(_DWORD *)(*(_QWORD *)(v57 + 24) + 44LL) & 0x80u) != 0 )
      {
        v31 = (*((_DWORD *)this + 48))-- == 1;
        if ( v31 )
          *(_QWORD *)this &= ~0x20000000000uLL;
      }
      v58 = *(_QWORD *)(*((_QWORD *)this + v37 + 70) + 72LL) + 8LL;
      a2 = (CmsTransactionContext *)((char *)this + 88 * (unsigned int)v37 + 1064);
      if ( a2 )
      {
        v31 = (*((_DWORD *)a2 + 18))-- == 1;
        if ( !v31 )
          goto LABEL_91;
        *((_DWORD *)a2 + 19) &= ~2u;
      }
      else
      {
        a2 = 0;
      }
      ExReleaseFastResource(v58, a2);
LABEL_91:
      v59 = *((_QWORD *)this + v37 + 70);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v59 + 8), 0xFFFFFFFF) == 1 && v59 )
        (**(void (__fastcall ***)(__int64, __int64))v59)(v59, 1);
      *((_QWORD *)this + v37 + 70) = 0;
      v37 = (unsigned int)(v37 + 1);
      if ( (unsigned int)v37 >= *((unsigned __int8 *)this + 133) )
        goto LABEL_95;
    }
  }
  v38 = *((unsigned __int8 *)this + 131);
  *((_QWORD *)this + 13) = v5;
  *((_QWORD *)this + v38 + 70) = v5;
  v39 = *((_QWORD *)this + 1);
  *((_BYTE *)this + 133) = *((_BYTE *)this + 131);
  if ( v39 )
  {
    v40 = *(CmsVolumeContainer **)(v39 + 3336);
    if ( v40 )
      CmsVolumeContainer::ReleasePinnedContainersAtEndOfTransaction(v40, this, v32);
  }
  if ( *((_DWORD *)this + 88) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( *((_DWORD *)this + 89) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v31 = *((_DWORD *)this + 48) == 0;
  *((_QWORD *)this + 44) = 0;
  if ( !v31 && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v41 = (struct SmsUndoRecord *)*((_QWORD *)this + 19);
  *((_QWORD *)this + 15) = v5;
  for ( *((_WORD *)this + 106) = (_WORD)v5; v41; v41 = (struct SmsUndoRecord *)*((_QWORD *)this + 19) )
  {
    *((_QWORD *)this + 19) = *(_QWORD *)v41;
    CmsBPlusTable::FreeUndoRecord(v41, a2, (unsigned int)a3);
  }
  *((_QWORD *)this + 20) = v5;
  v42 = *((_QWORD *)this + 34);
  if ( v42 )
  {
    if ( *((_BYTE *)this + 293) )
    {
      *((_BYTE *)this + 136) = 0;
    }
    else
    {
      v44 = *(_QWORD *)(v42 - 16);
      v45 = (struct _SLIST_ENTRY *)(v42 - 16);
      if ( !v44 )
        goto LABEL_152;
      if ( *(_BYTE *)(v44 + 8) )
      {
        v46 = (struct _NPAGED_LOOKASIDE_LIST *)(v44 + 64);
        v47 = (void *)(v42 - 16);
        if ( *(_BYTE *)(v44 + 9) )
          ExFreeToNPagedLookasideList(v46, v47);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v46, v47);
        goto LABEL_64;
      }
      v68 = *(_QWORD *)(v44 + 88);
      if ( (int)v68 < *(_DWORD *)(v44 + 80) || SHIDWORD(v68) >= (int)v68 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v44 + 64), v45);
        _InterlockedIncrement((volatile signed __int32 *)(v44 + 88));
      }
      else
      {
LABEL_152:
        ExFreePoolWithTag(v45, 0);
      }
    }
LABEL_64:
    CmsTransactionContext::_unnamed_type_RunCopies_::Reset((char *)this + 272);
  }
  *((_BYTE *)this + 129) = 0;
  *((_BYTE *)this + 135) = 0;
  *((_QWORD *)this + 14) = v5;
  if ( v80 )
  {
    v70 = v75;
    if ( v75 )
    {
      v8 = (*(__int64 (__fastcall **)(CmsReferenced *, CmsTransactionContext *, _QWORD, __int64, CmsTransactionContext **, CmsTransactionContext **))(*(_QWORD *)v75 + 64LL))(
             v75,
             this,
             0,
             1,
             v5,
             v5);
      CmsReferenced::Release(v70);
      CmsVolume::CommitTx(*((CmsVolume **)this + 1), this, v71, 0, (struct _SmsLsn *)v5, v5);
      CmsTransactionContext::ReuseTransaction(this);
    }
    CmsVolume::Flush(*((_QWORD *)this + 1), 1, 0, 0, v5, v5, v5);
  }
  return v8;
}

```

## disassembly

```asm
0x1400340e0  mov     [rsp-8+arg_10], r8
0x1400340e5  mov     [rsp-8+arg_8], dl
0x1400340e9  push    rbp
0x1400340ea  push    rbx
0x1400340eb  push    r12
0x1400340ed  push    r13
0x1400340ef  push    r14
0x1400340f1  lea     rbp, [rsp-37h]
0x1400340f6  sub     rsp, 100h
0x1400340fd  mov     rax, [rcx]
0x140034100  xor     r14d, r14d
0x140034103  movzx   r8d, al
0x140034107  mov     [rbp+57h+var_C0], r14
0x14003410b  shr     r8b, 7
0x14003410f  movzx   r13d, r9b
0x140034113  and     r8b, 1
0x140034117  mov     rbx, rcx
0x14003411a  mov     [rbp+57h+arg_8], r8b
0x14003411e  mov     r12d, r14d
0x140034121  test    al, 20h
0x140034123  jnz     loc_1400348C9
0x140034129  mov     rcx, [rcx+8]
0x14003412d  mov     [rsp+120h+arg_18], rsi
0x140034135  mov     [rsp+120h+var_28], rdi
0x14003413d  mov     [rsp+120h+var_30], r15
0x140034145  mov     [rbp+57h+var_C8], rcx
0x140034149  test    rcx, rcx
0x14003414c  jz      loc_1400342B4
0x140034152  xorps   xmm0, xmm0
0x140034155  mov     qword ptr [rbp+57h+var_90], r14
0x140034159  test    r8b, r8b
0x14003415c  movdqa  [rbp+57h+var_A0], xmm0
0x140034161  lea     rdx, [rbp+57h+var_C0]
0x140034165  cmovz   rdx, r14
0x140034169  xor     eax, eax
0x14003416b  mov     [rbp+57h+var_58], rax
0x14003416f  mov     rax, [rbx+0C8h]
0x140034176  mov     [rbp+57h+var_A8], rdx
0x14003417a  movups  [rbp+57h+var_90+8], xmm0
0x14003417e  movups  xmmword ptr [rbp+57h+Event.Header.WaitListHead.Flink], xmm0
0x140034182  movups  [rbp+57h+var_68], xmm0
0x140034186  test    rax, rax
0x140034189  jnz     loc_14003484E
0x14003418f  mov     [rbx+0C8h], r14
0x140034196  test    r13b, r13b
0x140034199  jnz     loc_140034653
0x14003419f  mov     [rbp+57h+arg_0], r14
0x1400341a3  movzx   eax, byte ptr [rbx+82h]
0x1400341aa  cmp     [rbx+83h], al
0x1400341b0  jnz     loc_1400348FD
0x1400341b6  cmp     [rbx+83h], r12b
0x1400341bd  jnz     loc_140034913
0x1400341c3  cmp     [rbx+84h], r12b
0x1400341ca  jnz     loc_140034929
0x1400341d0  cmp     [rbx+82h], r12b
0x1400341d7  jnz     loc_14003493F
0x1400341dd  cmp     [rbx+0D4h], r12w
0x1400341e5  jnz     loc_140034955
0x1400341eb  cmp     [rbx+0D6h], r12w
0x1400341f3  jnz     loc_140034955
0x1400341f9  mov     ecx, [rbx]
0x1400341fb  lea     rax, [rsp+120h+var_E0]
0x140034200  mov     [rbx+83h], r12w
0x140034208  and     ecx, 1000h
0x14003420e  mov     [rbx+82h], r12b
0x140034215  lea     r12, [rbx+338h]
0x14003421c  mov     rsi, [r12]
0x140034220  mov     r15, r12
0x140034223  mov     [rsp+120h+var_E0.Blink], rax
0x140034228  lea     rax, [rsp+120h+var_E0]
0x14003422d  mov     [rsp+120h+var_E0.Flink], rax
0x140034232  mov     [rbp+57h+var_D0], rcx
0x140034236  cmp     rsi, r15
0x140034239  jnz     loc_140034564
0x14003423f  cmp     r15, r12
0x140034242  jz      loc_140034627
0x140034248  xor     r14d, r14d
0x14003424b  lea     rdx, [rsp+120h+var_E0]; struct _LIST_ENTRY *
0x140034250  mov     rcx, rbx; struct CmsTransactionContext *
0x140034253  mov     r12d, r14d
0x140034256  call    ?DeleteDoomedCachedPins@CmsPinCache@@SAXPEAVCmsTransactionContext@@PEAU_LIST_ENTRY@@@Z; CmsPinCache::DeleteDoomedCachedPins(CmsTransactionContext *,_LIST_ENTRY *)
0x14003425b  cmp     [rbx+90h], r12
0x140034262  jnz     loc_1400349AD
0x140034268  mov     rcx, [rbx+1A0h]; this
0x14003426f  cmp     [rcx], r12
0x140034272  jz      loc_1400349C2
0x140034278  mov     rax, [rbp+57h+arg_10]
0x14003427c  movzx   r8d, r13b; unsigned __int8
0x140034280  mov     rdi, [rbp+57h+arg_0]
0x140034284  mov     rdx, rbx; struct CmsTransactionContext *
0x140034287  mov     rsi, [rbp+57h+var_C8]
0x14003428b  mov     [rsp+120h+var_F0], rax; struct _SmsLsn *
0x140034290  mov     rcx, rsi; this
0x140034293  mov     [rsp+120h+var_F8], rdi; struct _SmsFlushWaiter *
0x140034298  mov     byte ptr [rsp+120h+var_100], r13b; char
0x14003429d  call    ?CommitTransactionLog@CmsVolume@@QEAAXPEAVCmsTransactionContext@@EEEPEAU_SmsFlushWaiter@@PEAU_SmsLsn@@@Z; CmsVolume::CommitTransactionLog(CmsTransactionContext *,uchar,uchar,uchar,_SmsFlushWaiter *,_SmsLsn *)
0x1400342a2  test    rdi, rdi
0x1400342a5  jnz     loc_1400349E4
0x1400342ab  test    r13b, r13b
0x1400342ae  jnz     loc_1400348E2
0x1400342b4  lea     rsi, [rbx+328h]
0x1400342bb  mov     rdi, [rsi]
0x1400342be  cmp     rdi, rsi
0x1400342c1  jz      short loc_1400342DB
0x1400342c3  mov     r15, [rdi]
0x1400342c6  lea     r14, [rdi-70h]
0x1400342ca  test    r14, r14
0x1400342cd  jnz     loc_140034771
0x1400342d3  mov     rdi, r15
0x1400342d6  cmp     r15, rsi
0x1400342d9  jnz     short loc_1400342C3
0x1400342db  cmp     dword ptr [rbx+0C4h], 0
0x1400342e2  jnz     loc_14003496B
0x1400342e8  lea     rdi, [rbx+298h]
0x1400342ef  lea     rsi, [rdi+80h]
0x1400342f6  mov     rax, [rsi]
0x1400342f9  cmp     rax, rsi
0x1400342fc  jz      short loc_140034349
0x1400342fe  cmp     [rax+8], rsi
0x140034302  jnz     loc_1400345D5
0x140034308  mov     rcx, [rax]
0x14003430b  cmp     [rcx+8], rax
0x14003430f  jnz     loc_1400345D5
0x140034315  mov     [rsi], rcx
0x140034318  mov     [rcx+8], rsi
0x14003431c  lea     rcx, [rax-10h]; P
0x140034320  mov     rax, [rax-8]
0x140034324  test    rax, rax
0x140034327  jz      short loc_14003432D
0x140034329  and     dword ptr [rax+4Ch], 0FFFFFFFEh
0x14003432d  mov     [rcx+8], r14
0x140034331  mov     [rcx], r14
0x140034334  test    rcx, rcx
0x140034337  jz      short loc_1400342F6
0x140034339  xor     edx, edx; Tag
0x14003433b  call    cs:__imp_ExFreePoolWithTag
0x140034342  nop     dword ptr [rax+rax+00h]
0x140034347  jmp     short loc_1400342F6
0x140034349  cmp     rdi, rsi
0x14003434c  jz      short loc_14003436D
0x14003434e  xchg    ax, ax
0x140034350  mov     rax, [rdi+8]
0x140034354  test    rax, rax
0x140034357  jz      short loc_14003435D
0x140034359  and     dword ptr [rax+4Ch], 0FFFFFFFEh
0x14003435d  mov     [rdi+8], r14
0x140034361  mov     [rdi], r14
0x140034364  add     rdi, 20h ; ' '
0x140034368  cmp     rdi, rsi
0x14003436b  jnz     short loc_140034350
0x14003436d  cmp     qword ptr [rbx+0A8h], 0
0x140034375  mov     [rbx+0C4h], r14d
0x14003437c  mov     [rbx+68h], r14
0x140034380  jnz     loc_1400349F2
0x140034386  mov     rax, [rbx]
0x140034389  mov     rcx, 13C023BC97BC31h
0x140034393  mov     rsi, rax
0x140034396  and     rax, rcx
0x140034399  shr     rsi, 32h
0x14003439d  and     sil, 1
0x1400343a1  mov     [rbx], rax
0x1400343a4  cmp     byte ptr [rbx+83h], 0
0x1400343ab  jnz     loc_140034A06
0x1400343b1  movzx   edi, byte ptr [rbx+84h]
0x1400343b8  cmp     edi, 0Dh
0x1400343bb  jnb     short loc_1400343D4
0x1400343bd  lea     r14, [rbx+rdi*8]
0x1400343c1  mov     rcx, [r14+1A8h]
0x1400343c8  test    rcx, rcx
0x1400343cb  jnz     loc_1400345DC
0x1400343d1  xor     r14d, r14d
0x1400343d4  movzx   eax, byte ptr [rbx+84h]
0x1400343db  mov     [rbx+rax*8+1A8h], r14
0x1400343e3  mov     word ptr [rbx+rax*2+210h], 0
0x1400343ed  mov     rax, cs:KdDebuggerEnabled
0x1400343f4  cmp     byte ptr [rax], 0
0x1400343f7  jnz     loc_140034864
0x1400343fd  movzx   edi, byte ptr [rbx+83h]
0x140034404  movzx   eax, byte ptr [rbx+85h]
0x14003440b  cmp     edi, eax
0x14003440d  jb      loc_140034689
0x140034413  movzx   eax, byte ptr [rbx+83h]
0x14003441a  mov     [rbx+68h], r14
0x14003441e  mov     [rbx+rax*8+230h], r14
0x140034426  mov     rcx, [rbx+8]
0x14003442a  movzx   eax, byte ptr [rbx+83h]
0x140034431  mov     [rbx+85h], al
0x140034437  test    rcx, rcx
0x14003443a  jz      short loc_140034454
0x14003443c  mov     rcx, [rcx+0D08h]; this
0x140034443  test    rcx, rcx
0x140034446  jz      short loc_140034454
0x140034448  movzx   r8d, sil; unsigned __int8
0x14003444c  mov     rdx, rbx; struct CmsTransactionContext *
0x14003444f  call    ?ReleasePinnedContainersAtEndOfTransaction@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@E@Z; CmsVolumeContainer::ReleasePinnedContainersAtEndOfTransaction(CmsTransactionContext *,uchar)
0x140034454  cmp     dword ptr [rbx+160h], 0
0x14003445b  jnz     loc_140034981
0x140034461  cmp     dword ptr [rbx+164h], 0
0x140034468  jnz     loc_140034997
0x14003446e  cmp     dword ptr [rbx+0C0h], 0
0x140034475  mov     qword ptr [rbx+160h], 0
0x140034480  jnz     loc_140034A37
0x140034486  mov     rcx, [rbx+98h]; struct SmsUndoRecord *
0x14003448d  mov     [rbx+78h], r14
0x140034491  mov     [rbx+0D4h], r14w
0x140034499  test    rcx, rcx
0x14003449c  jnz     loc_140034A4D
0x1400344a2  mov     [rbx+0A0h], r14
0x1400344a9  mov     rax, [rbx+110h]
0x1400344b0  test    rax, rax
0x1400344b3  jnz     short loc_1400344FD
0x1400344b5  cmp     [rbp+57h+arg_8], 0
0x1400344b9  mov     byte ptr [rbx+81h], 0
0x1400344c0  mov     byte ptr [rbx+87h], 0
0x1400344c7  mov     [rbx+70h], r14
0x1400344cb  jnz     loc_1401F1E85
0x1400344d1  mov     r15, [rsp+120h+var_30]
0x1400344d9  mov     eax, r12d
0x1400344dc  mov     rdi, [rsp+120h+var_28]
0x1400344e4  mov     rsi, [rsp+120h+arg_18]
0x1400344ec  add     rsp, 100h
0x1400344f3  pop     r14
0x1400344f5  pop     r13
0x1400344f7  pop     r12
0x1400344f9  pop     rbx
0x1400344fa  pop     rbp
0x1400344fb  retn
0x1400344fd  cmp     byte ptr [rbx+125h], 0
0x140034504  jz      short loc_14003451B
0x140034506  mov     byte ptr [rbx+88h], 0
0x14003450d  lea     rcx, [rbx+110h]
0x140034514  call    CmsTransactionContext___unnamed_type_RunCopies___Reset
0x140034519  jmp     short loc_1400344B5
0x14003451b  mov     rsi, [rax-10h]
0x14003451f  lea     r8, [rax-10h]
0x140034523  test    rsi, rsi
0x140034526  jz      loc_140034A89
0x14003452c  cmp     byte ptr [rsi+8], 0
0x140034530  jz      loc_140034A6D
0x140034536  cmp     byte ptr [rsi+9], 0
0x14003453a  lea     rcx, [rsi+40h]; Lookaside
0x14003453e  mov     rdx, r8; Entry
0x140034541  jz      loc_140034636
0x140034547  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003454e  nop     dword ptr [rax+rax+00h]
0x140034553  lea     rcx, [rbx+110h]
0x14003455a  call    CmsTransactionContext___unnamed_type_RunCopies___Reset
0x14003455f  jmp     loc_1400344B5
0x140034564  mov     r14, rsi
0x140034567  mov     rdi, rsi
0x14003456a  add     r14, 0FFFFFFFFFFFFFFF0h
0x14003456e  mov     rdx, rsi
0x140034571  mov     rsi, [rsi]
0x140034574  test    rcx, rcx
0x140034577  jnz     short loc_1400345A8
0x140034579  mov     r9, [r14+28h]
0x14003457d  lea     rax, [rsp+120h+var_E0]
0x140034582  mov     r8, r14; struct CmsCachedPin *
0x140034585  mov     [rsp+120h+var_100], rax; struct _LIST_ENTRY *
0x14003458a  mov     rdx, rbx; struct CmsTransactionContext *
0x14003458d  mov     rcx, r12; this
0x140034590  mov     r9, [r9+20h]; struct CmsBPlusTable *
0x140034594  call    ?TransferOneCachedPin@CmsPinCache@@QEAAEPEAVCmsTransactionContext@@PEAVCmsCachedPin@@PEAVCmsBPlusTable@@PEAU_LIST_ENTRY@@@Z; CmsPinCache::TransferOneCachedPin(CmsTransactionContext *,CmsCachedPin *,CmsBPlusTable *,_LIST_ENTRY *)
0x140034599  mov     rcx, [rbp+57h+var_D0]
0x14003459d  test    al, al
0x14003459f  jnz     loc_140034236
0x1400345a5  mov     rdx, rdi
0x1400345a8  mov     rcx, [rdi]
0x1400345ab  cmp     [rcx+8], rdi
0x1400345af  jnz     short loc_1400345D5
0x1400345b1  mov     rax, [r14+18h]
0x1400345b5  cmp     [rax], rdx
0x1400345b8  jnz     short loc_1400345D5
0x1400345ba  mov     [rax], rcx
0x1400345bd  mov     [rcx+8], rax
0x1400345c1  lea     rcx, [rsp+120h+var_E0]
0x1400345c6  mov     rax, [rsp+120h+var_E0.Flink]
0x1400345cb  cmp     [rax+8], rcx
0x1400345cf  jz      loc_1400347D3
0x1400345d5  mov     ecx, 3
0x1400345da  int     29h; Win8: RtlFailFast(ecx)
0x1400345dc  cmp     byte ptr [rbx+rdi*2+210h], 0
0x1400345e4  jnz     loc_140034A1C
0x1400345ea  cmp     byte ptr [rbx+rdi*2+211h], 0
0x1400345f2  jnz     loc_140034A1C
0x1400345f8  mov     rcx, [r14+1A8h]
0x1400345ff  mov     eax, 0FFFFFFFFh
0x140034604  lock xadd [rcx+8], eax
0x140034609  cmp     eax, 1
0x14003460c  jnz     short loc_140034617
0x14003460e  test    rcx, rcx
0x140034611  jnz     loc_14003475C
0x140034617  inc     edi
0x140034619  cmp     edi, 0Dh
0x14003461c  jnb     loc_1400343D1
0x140034622  jmp     loc_1400343BD
0x140034627  mov     rsi, [r12+10h]
0x14003462c  lea     r15, [r12+10h]
0x140034631  jmp     loc_140034236
0x140034636  call    cs:__imp_ExFreeToPagedLookasideList
  ... truncated ...
```
