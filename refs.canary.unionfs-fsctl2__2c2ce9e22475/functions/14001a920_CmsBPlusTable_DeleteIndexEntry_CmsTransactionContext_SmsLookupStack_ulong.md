# CmsBPlusTable::DeleteIndexEntry(CmsTransactionContext *,SmsLookupStack &,ulong)

- ea: `0x14001a920`
- end: `0x14001b09f`
- name: `?DeleteIndexEntry@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@AEAUSmsLookupStack@@K@Z`
- size: `1919`
- prototype: `__int64 __fastcall(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, struct SmsLookupStack *, unsigned int)`
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140017c30`
- `0x14001a36c`
- `0x14001a680`
- `0x14001b120`
- `0x14002c4e0`

## callees

- `0x140012660`
- `0x14001a0c0`
- `0x14001a920`
- `0x14001c2a0`
- `0x14001c480`
- `0x140023180`
- `0x1400a32d0`
- `0x1400c4acc`
- `0x1400c8574`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14001af67`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001af8f`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001af9e`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001afb4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001afd8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001b043`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001afd8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001b043`
- `ntoskrnl!ExAllocatePool2` at `0x14001a9dc`
- `ntoskrnl!ExAllocatePool2` at `0x14001ab34`
- `ntoskrnl!ExAllocatePool2` at `0x14001a9dc`
- `ntoskrnl!ExAllocatePool2` at `0x14001ab34`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001a9a0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001aac4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001a9a0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001aac4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eedb6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eee34`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eedb6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eee34`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001aff5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001b060`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001aff5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001b060`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14001abed`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14001abed`

## string_xrefs

- `0x1401eee46`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::DeleteIndexEntry(
        CmsBPlusTable *this,
        struct CmsTransactionContext *a2,
        struct SmsLookupStack *a3,
        int a4)
{
  __int64 v6; // r8
  __int64 v8; // r15
  int v9; // esi
  unsigned int v10; // r15d
  unsigned __int64 v11; // rbx
  unsigned int *v12; // rdi
  unsigned __int64 v13; // rdx
  __int64 Pool2; // rax
  __int64 Undo; // rbx
  int v16; // ecx
  unsigned int v17; // ecx
  int v18; // edx
  int v19; // r15d
  __int64 v20; // rcx
  unsigned int v21; // esi
  unsigned __int64 v22; // rbx
  unsigned int *v23; // rdi
  int v24; // ecx
  unsigned __int64 v25; // rdx
  __int64 v26; // rax
  CmsBPlusTable *v27; // rcx
  unsigned int *v28; // rdi
  char *v29; // r15
  unsigned int v30; // eax
  __int64 v31; // rsi
  __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // r9d
  __int64 v35; // r10
  int v36; // r11d
  __int64 v37; // rax
  unsigned int v38; // eax
  unsigned int *v39; // rcx
  char v40; // r8
  __int64 v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // r8
  unsigned int v44; // eax
  int v45; // edx
  bool v46; // zf
  unsigned int *v48; // rdi
  unsigned int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // r8
  int v52; // r9d
  __int64 v53; // r10
  int v54; // r11d
  __int64 v55; // rax
  unsigned int v56; // eax
  unsigned int *v57; // rcx
  unsigned int *v58; // rcx
  unsigned int v59; // eax
  struct _NPAGED_LOOKASIDE_LIST *v60; // rcx
  void *v61; // rax
  struct _NPAGED_LOOKASIDE_LIST *v62; // rcx
  void *v63; // rax
  char v64; // cl
  __int64 v65; // rdx
  __int64 v66; // rcx
  int v67; // [rsp+20h] [rbp-68h]
  struct _SmsIndexEntry *v68; // [rsp+A0h] [rbp+18h]

  v6 = *((_QWORD *)a3 + 1);
  if ( (*(_BYTE *)(v6 + 13) & 1) == 0 || (v17 = *(_DWORD *)(v6 + 20), v18 = *((_DWORD *)a3 + 6), v18 != v17 - 1) )
  {
    v8 = *((_QWORD *)a3 + 2);
    v9 = (a4 != 0) + 2;
    if ( (*(_BYTE *)(v8 + 8) & 0x40) != 0 )
      v10 = (*(unsigned __int16 *)(v8 + 10) + 7) & 0xFFFFFFF8;
    else
      v10 = *(_DWORD *)v8;
    if ( (*((_BYTE *)this + 14) & 7) != 0 )
    {
      v9 = 2;
    }
    else if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 2) != 0 && !a4 )
    {
      v9 = 30;
      v10 *= 2;
    }
    if ( (*(_DWORD *)a2 & 0x1000LL) != 0 )
    {
      if ( (_BYTE)KdDebuggerEnabled )
LABEL_104:
        __debugbreak();
LABEL_101:
      LOBYTE(v6) = 1;
      CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)a2 + 1), 0x20000000, v6);
      return 3221225626LL;
    }
    v11 = ((v10 + 7) & 0xFFFFFFF8) + 88;
    v12 = (unsigned int *)(qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( v11 > *v12 )
    {
      v12 = 0;
      v13 = v11 + 16;
      goto LABEL_9;
    }
    if ( !*((_BYTE *)v12 + 8) )
    {
      if ( (int)*((_QWORD *)v12 + 11) > (int)HIDWORD(*((_QWORD *)v12 + 11)) )
      {
        v16 = _InterlockedDecrement((volatile signed __int32 *)v12 + 22);
        if ( v16 >= (int)v12[23] && v16 >= 0 )
        {
          v63 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v12 + 4);
          goto LABEL_34;
        }
        _InterlockedIncrement((volatile signed __int32 *)v12 + 22);
      }
LABEL_17:
      v13 = v12[1];
LABEL_9:
      Pool2 = ExAllocatePool2(66, v13, 1766871885);
      Undo = Pool2;
      if ( (Pool2 & 0xF) != 0 )
        goto LABEL_128;
      if ( !Pool2 )
      {
LABEL_36:
        if ( Undo )
        {
          *(_DWORD *)(Undo + 16) = v9;
          *(_QWORD *)(Undo + 40) = this;
          *(_DWORD *)(Undo + 12) = v10;
          *(_DWORD *)(Undo + 8) = v10;
          *(_WORD *)(Undo + 20) = 0;
          *(_OWORD *)(Undo + 48) = 0;
          *(_OWORD *)(Undo + 64) = 0;
          *(_QWORD *)(Undo + 80) = 0;
          *(_DWORD *)(Undo + 32) = 0;
          if ( v10 )
          {
            *(_QWORD *)(Undo + 24) = Undo + 88;
            memset((void *)(Undo + 88), 0, v10);
          }
          else
          {
            *(_QWORD *)(Undo + 24) = 0;
          }
          v28 = (unsigned int *)*((_QWORD *)a3 + 2);
          v29 = (char *)a3 + 16;
          if ( (v28[2] & 0x40) != 0 )
            v30 = (*((unsigned __int16 *)v28 + 5) + 7) & 0xFFFFFFF8;
          else
            v30 = *v28;
          *(_DWORD *)(Undo + 8) = v30;
          *(_DWORD *)(Undo + 32) = 0;
          *(_QWORD *)(Undo + 40) = this;
          v31 = *(_QWORD *)a3;
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)a3 + 380LL));
          if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v31 + 560) )
            ++*(_DWORD *)(v31 + 384);
          else
            SmsPageLatch::AcquireShared((SmsPageLatch *)(v31 + 560), a2, 1);
          if ( *(char *)(*(_QWORD *)(v31 + 96) + 14LL) >= 0 )
            ++*((_DWORD *)a2 + 49);
          ++*(_DWORD *)(v31 + 388);
          v32 = *((_QWORD *)a3 + 1);
          v33 = *(_QWORD *)v29;
          v34 = *((_DWORD *)a3 + 6);
          v35 = *((_QWORD *)a3 + 4);
          v36 = *((_DWORD *)a3 + 7);
          if ( *(_QWORD *)(Undo + 48) && (_BYTE)KdDebuggerEnabled )
            __debugbreak();
          *(_QWORD *)(Undo + 48) = *(_QWORD *)a3;
          *(_QWORD *)(Undo + 56) = v32;
          *(_QWORD *)(Undo + 64) = v33;
          *(_DWORD *)(Undo + 72) = v34;
          *(_QWORD *)(Undo + 80) = v35;
          *(_DWORD *)(Undo + 76) = v36;
          v37 = *(_QWORD *)a3;
          if ( *(_QWORD *)a3
            && (!*(_BYTE *)(v37 + 392) && *(CmsBPlusTable **)(v37 + 96) == this || !*((_BYTE *)this + 212)) )
          {
            *(_BYTE *)(Undo + 20) |= 1u;
          }
          v38 = *(_DWORD *)(Undo + 8);
          if ( v38 )
          {
            v39 = *(unsigned int **)(Undo + 24);
            if ( v28 )
            {
              if ( v28 != v39 )
                memmove(v39, v28, v38);
            }
            else
            {
              memset(v39, 0, *(unsigned int *)(Undo + 8));
            }
          }
          v40 = 0;
          *(_QWORD *)Undo = *((_QWORD *)a2 + 18);
          *((_QWORD *)a2 + 18) = Undo;
          goto LABEL_58;
        }
        return 3221225626LL;
      }
LABEL_35:
      *(_QWORD *)Undo = v12;
      Undo += 16;
      goto LABEL_36;
    }
    v62 = (struct _NPAGED_LOOKASIDE_LIST *)(v12 + 16);
    if ( *((_BYTE *)v12 + 9) )
      v63 = ExAllocateFromNPagedLookasideList(v62);
    else
      v63 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v62);
LABEL_34:
    Undo = (__int64)v63;
    if ( v63 )
      goto LABEL_35;
    goto LABEL_17;
  }
  v19 = (a4 != 0) + 2;
  if ( v17 > 1 )
  {
    v20 = v6 + *(unsigned __int16 *)(v6 + *(unsigned int *)(v6 + 16) + 4LL * (unsigned int)(v18 - 1));
    v68 = (struct _SmsIndexEntry *)v20;
    if ( (*(_BYTE *)(v20 + 8) & 0x40) != 0 )
      v21 = (*(unsigned __int16 *)(v20 + 10) + 7) & 0xFFFFFFF8;
    else
      v21 = *(_DWORD *)v20;
    if ( (*(_DWORD *)a2 & 0x1000LL) == 0 )
    {
      v22 = ((v21 + 7) & 0xFFFFFFF8) + 88;
      v23 = (unsigned int *)(qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v22 > *v23 )
      {
        v23 = 0;
        v25 = v22 + 16;
LABEL_29:
        v26 = ExAllocatePool2(66, v25, 1766871885);
        Undo = v26;
        if ( (v26 & 0xF) == 0 )
        {
          if ( !v26 )
            goto LABEL_75;
          goto LABEL_74;
        }
LABEL_128:
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      }
      if ( !*((_BYTE *)v23 + 8) )
      {
        if ( (int)*((_QWORD *)v23 + 11) > (int)HIDWORD(*((_QWORD *)v23 + 11)) )
        {
          v24 = _InterlockedDecrement((volatile signed __int32 *)v23 + 22);
          if ( v24 >= (int)v23[23] && v24 >= 0 )
          {
            v61 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v23 + 4);
            goto LABEL_73;
          }
          _InterlockedIncrement((volatile signed __int32 *)v23 + 22);
        }
LABEL_28:
        v25 = v23[1];
        goto LABEL_29;
      }
      v60 = (struct _NPAGED_LOOKASIDE_LIST *)(v23 + 16);
      if ( *((_BYTE *)v23 + 9) )
        v61 = ExAllocateFromNPagedLookasideList(v60);
      else
        v61 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v60);
LABEL_73:
      Undo = (__int64)v61;
      if ( v61 )
      {
LABEL_74:
        *(_QWORD *)Undo = v23;
        Undo += 16;
LABEL_75:
        if ( Undo )
        {
          *(_DWORD *)(Undo + 16) = v19;
          *(_QWORD *)(Undo + 40) = this;
          *(_DWORD *)(Undo + 12) = v21;
          *(_DWORD *)(Undo + 8) = v21;
          *(_WORD *)(Undo + 20) = 0;
          *(_OWORD *)(Undo + 48) = 0;
          *(_OWORD *)(Undo + 64) = 0;
          *(_QWORD *)(Undo + 80) = 0;
          *(_DWORD *)(Undo + 32) = 0;
          if ( v21 )
          {
            *(_QWORD *)(Undo + 24) = Undo + 88;
            memset((void *)(Undo + 88), 0, v21);
          }
          else
          {
            *(_QWORD *)(Undo + 24) = 0;
          }
          v29 = (char *)a3 + 16;
          CmsBPlusTable::SwapDirectorData(v27, v68, *((struct _SmsIndexEntry **)a3 + 2));
          v48 = (unsigned int *)(*((_QWORD *)a3 + 1)
                               + *(unsigned __int16 *)(*((_QWORD *)a3 + 1)
                                                     + *(unsigned int *)(*((_QWORD *)a3 + 1) + 16LL)
                                                     + 4LL * (unsigned int)--*((_DWORD *)a3 + 6)));
          *((_QWORD *)a3 + 2) = v48;
          if ( (v48[2] & 0x40) != 0 )
            v49 = (*((unsigned __int16 *)v48 + 5) + 7) & 0xFFFFFFF8;
          else
            v49 = *v48;
          *(_DWORD *)(Undo + 8) = v49;
          *(_DWORD *)(Undo + 32) = 0;
          *(_QWORD *)(Undo + 40) = this;
          SmsPage::Repin(*(_QWORD *)a3, a2, 2);
          v50 = *((_QWORD *)a3 + 1);
          v51 = *(_QWORD *)v29;
          v52 = *((_DWORD *)a3 + 6);
          v53 = *((_QWORD *)a3 + 4);
          v54 = *((_DWORD *)a3 + 7);
          if ( *(_QWORD *)(Undo + 48) && (_BYTE)KdDebuggerEnabled )
            __debugbreak();
          *(_QWORD *)(Undo + 48) = *(_QWORD *)a3;
          *(_QWORD *)(Undo + 56) = v50;
          *(_QWORD *)(Undo + 64) = v51;
          *(_DWORD *)(Undo + 72) = v52;
          *(_QWORD *)(Undo + 80) = v53;
          *(_DWORD *)(Undo + 76) = v54;
          v55 = *(_QWORD *)a3;
          if ( *(_QWORD *)a3
            && (!*(_BYTE *)(v55 + 392) && *(CmsBPlusTable **)(v55 + 96) == this || !*((_BYTE *)this + 212)) )
          {
            *(_BYTE *)(Undo + 20) |= 1u;
          }
          v56 = *(_DWORD *)(Undo + 8);
          if ( v56 )
          {
            v57 = *(unsigned int **)(Undo + 24);
            if ( v48 )
            {
              if ( v48 != v57 )
                memmove(v57, v48, v56);
            }
            else
            {
              memset(v57, 0, *(unsigned int *)(Undo + 8));
            }
          }
          *(_QWORD *)Undo = *((_QWORD *)a2 + 18);
          *((_QWORD *)a2 + 18) = Undo;
          goto LABEL_90;
        }
        return 3221225626LL;
      }
      goto LABEL_28;
    }
    if ( (_BYTE)KdDebuggerEnabled )
      goto LABEL_104;
    goto LABEL_101;
  }
  v29 = (char *)a3 + 16;
  Undo = CmsBPlusTable::AllocateUndo(this, a2, (unsigned int)(a4 != 0) + 2);
  if ( !Undo )
    return 3221225626LL;
  v58 = *(unsigned int **)v29;
  if ( (*(_BYTE *)(*(_QWORD *)v29 + 8LL) & 0x40) != 0 )
    v59 = (*((unsigned __int16 *)v58 + 5) + 7) & 0xFFFFFFF8;
  else
    v59 = *v58;
  CmsBPlusTable::FormatUndoRecord(this, a2, (struct SmsUndoRecord *)Undo, a3, v58, v59, 0);
  *(_BYTE *)(Undo + 21) = 0;
  v64 = *((_BYTE *)this + 212);
  if ( v64 == *(_BYTE *)(*((_QWORD *)a3 + 1) + 12LL) )
  {
    *(_BYTE *)(Undo + 21) = v64;
    v65 = *((_QWORD *)this + 3);
    *((_BYTE *)this + 212) = 0;
    v66 = *((_QWORD *)a3 + 1);
    LOBYTE(v67) = *(_BYTE *)(v66 + 13) & 0xF6;
    _SmsIndexHeader::InitializeIndexHeader(v66, v65, *(unsigned int *)(v66 + 32), 0, v67, 0);
    v40 = 1;
    goto LABEL_91;
  }
LABEL_90:
  v40 = 0;
LABEL_91:
  *(_BYTE *)(Undo + 20) |= 2u;
LABEL_58:
  if ( (*(_BYTE *)(*((_QWORD *)a3 + 1) + 13LL) & 1) != 0 )
    *(_BYTE *)(Undo + 20) |= 8u;
  if ( !v40 )
  {
    v41 = *(_QWORD *)v29;
    v42 = *((_QWORD *)a3 + 1);
    v43 = *((unsigned int *)a3 + 6);
    *(_WORD *)(v41 + 8) |= 4u;
    if ( (*(_WORD *)(v41 + 8) & 0x40) != 0 )
      v44 = (*(unsigned __int16 *)(v41 + 10) + 7) & 0xFFFFFFF8;
    else
      v44 = *(_DWORD *)v41;
    v45 = *(_DWORD *)(v42 + 4);
    if ( v44 + (_DWORD)v41 - (_DWORD)v42 == v45 )
      *(_DWORD *)(v42 + 4) = v45 - v44;
    *(_DWORD *)(v42 + 8) += v44 + 4;
    if ( (_DWORD)v43 )
      memmove(
        (void *)(v42 + *(unsigned int *)(v42 + 16) + 4),
        (const void *)(v42 + *(unsigned int *)(v42 + 16)),
        4 * v43);
    *(_DWORD *)(v42 + 16) += 4;
    v46 = (*(_DWORD *)(v42 + 20))-- == 1;
    if ( v46 || (*(_BYTE *)(v42 + 13) & 1) != 0 && *(_DWORD *)(v42 + 20) == 1 )
    {
      *(_BYTE *)(v42 + 13) &= ~8u;
      *(_QWORD *)(v42 + 24) = 0;
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)a3 + 372LL));
  return 0;
}

```

## disassembly

```asm
0x14001a920  push    rbx
0x14001a922  push    rbp
0x14001a923  push    rsi
0x14001a924  push    rdi
0x14001a925  push    r12
0x14001a927  push    r13
0x14001a929  push    r14
0x14001a92b  push    r15
0x14001a92d  sub     rsp, 48h
0x14001a931  mov     r14, r8
0x14001a934  mov     r12, rdx
0x14001a937  mov     r8, [r8+8]
0x14001a93b  mov     rbp, rcx
0x14001a93e  test    byte ptr [r8+0Dh], 1
0x14001a943  jnz     loc_14001AA50
0x14001a949  mov     r15, [r14+10h]
0x14001a94d  xor     r13d, r13d
0x14001a950  test    r9d, r9d
0x14001a953  mov     esi, r13d
0x14001a956  setnz   sil
0x14001a95a  add     esi, 2
0x14001a95d  test    byte ptr [r15+8], 40h
0x14001a962  jnz     loc_14001AA01
0x14001a968  mov     r15d, [r15]
0x14001a96b  test    byte ptr [rbp+0Eh], 7
0x14001a96f  jnz     loc_14001B015
0x14001a975  mov     rax, [rbp+18h]
0x14001a979  mov     ecx, [rax+2Ch]
0x14001a97c  test    cl, 2
0x14001a97f  jnz     loc_14001B01F
0x14001a985  mov     eax, [r12]
0x14001a989  bt      rax, 0Ch
0x14001a98e  jb      loc_14001AF67
0x14001a994  lea     ebx, [r15+7]
0x14001a998  xor     ecx, ecx; ProcNumber
0x14001a99a  and     ebx, 0FFFFFFF8h
0x14001a99d  add     ebx, 58h ; 'X'
0x14001a9a0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001a9a7  nop     dword ptr [rax+rax+00h]
0x14001a9ac  xor     edx, edx
0x14001a9ae  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14001a9b4  lea     rdi, [rdx+rdx*2]
0x14001a9b8  shl     rdi, 6
0x14001a9bc  add     rdi, cs:qword_140262410
0x14001a9c3  mov     eax, [rdi]
0x14001a9c5  cmp     rbx, rax
0x14001a9c8  jbe     short loc_14001AA13
0x14001a9ca  mov     rdi, r13
0x14001a9cd  lea     rdx, [rbx+10h]
0x14001a9d1  mov     ecx, 42h ; 'B'
0x14001a9d6  mov     r8d, 6950534Dh
0x14001a9dc  call    cs:__imp_ExAllocatePool2
0x14001a9e3  nop     dword ptr [rax+rax+00h]
0x14001a9e8  mov     rbx, rax
0x14001a9eb  test    al, 0Fh
0x14001a9ed  jnz     loc_1401EEE46
0x14001a9f3  test    rax, rax
0x14001a9f6  jz      loc_14001AB84
0x14001a9fc  jmp     loc_14001AB7D
0x14001aa01  movzx   r15d, word ptr [r15+0Ah]
0x14001aa06  add     r15d, 7
0x14001aa0a  and     r15d, 0FFFFFFF8h
0x14001aa0e  jmp     loc_14001A96B
0x14001aa13  cmp     [rdi+8], r13b
0x14001aa17  jnz     loc_14001B035
0x14001aa1d  mov     rcx, [rdi+58h]
0x14001aa21  mov     rax, rcx
0x14001aa24  shr     rax, 20h
0x14001aa28  cmp     ecx, eax
0x14001aa2a  jle     short loc_14001AA4B
0x14001aa2c  nop
0x14001aa2d  mov     ecx, 0FFFFFFFFh
0x14001aa32  lock xadd [rdi+58h], ecx
0x14001aa37  nop
0x14001aa38  dec     ecx
0x14001aa3a  mov     eax, [rdi+5Ch]
0x14001aa3d  cmp     ecx, eax
0x14001aa3f  jge     loc_14001B054
0x14001aa45  nop
0x14001aa46  lock inc dword ptr [rdi+58h]
0x14001aa4a  nop
0x14001aa4b  mov     edx, [rdi+4]
0x14001aa4e  jmp     short loc_14001A9D1
0x14001aa50  mov     ecx, [r8+14h]
0x14001aa54  mov     edx, [r14+18h]
0x14001aa58  lea     eax, [rcx-1]
0x14001aa5b  cmp     edx, eax
0x14001aa5d  jnz     loc_14001A949
0x14001aa63  xor     r13d, r13d
0x14001aa66  test    r9d, r9d
0x14001aa69  mov     r15d, r13d
0x14001aa6c  setnz   r15b
0x14001aa70  add     r15d, 2
0x14001aa74  mov     dword ptr [rsp+88h+arg_10], r15d
0x14001aa7c  cmp     ecx, 1
0x14001aa7f  jbe     loc_14001AF08
0x14001aa85  mov     ecx, [r8+10h]
0x14001aa89  lea     eax, [rdx-1]
0x14001aa8c  add     rcx, r8
0x14001aa8f  movzx   ecx, word ptr [rcx+rax*4]
0x14001aa93  add     rcx, r8
0x14001aa96  mov     [rsp+88h+arg_10], rcx
0x14001aa9e  test    byte ptr [rcx+8], 40h
0x14001aaa2  jnz     loc_14001AB62
0x14001aaa8  mov     esi, [rcx]
0x14001aaaa  mov     eax, [r12]
0x14001aaae  bt      rax, 0Ch
0x14001aab3  jb      loc_14001AF8F
0x14001aab9  lea     ebx, [rsi+7]
0x14001aabc  xor     ecx, ecx; ProcNumber
0x14001aabe  and     ebx, 0FFFFFFF8h
0x14001aac1  add     ebx, 58h ; 'X'
0x14001aac4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001aacb  nop     dword ptr [rax+rax+00h]
0x14001aad0  xor     edx, edx
0x14001aad2  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14001aad8  lea     rdi, [rdx+rdx*2]
0x14001aadc  shl     rdi, 6
0x14001aae0  add     rdi, cs:qword_140262410
0x14001aae7  mov     eax, [rdi]
0x14001aae9  cmp     rbx, rax
0x14001aaec  ja      short loc_14001AB59
0x14001aaee  cmp     [rdi+8], r13b
0x14001aaf2  jnz     loc_14001AFCA
0x14001aaf8  mov     rcx, [rdi+58h]
0x14001aafc  mov     rax, rcx
0x14001aaff  shr     rax, 20h
0x14001ab03  cmp     ecx, eax
0x14001ab05  jle     short loc_14001AB26
0x14001ab07  nop
0x14001ab08  mov     ecx, 0FFFFFFFFh
0x14001ab0d  lock xadd [rdi+58h], ecx
0x14001ab12  nop
0x14001ab13  dec     ecx
0x14001ab15  mov     eax, [rdi+5Ch]
0x14001ab18  cmp     ecx, eax
0x14001ab1a  jge     loc_14001AFE9
0x14001ab20  nop
0x14001ab21  lock inc dword ptr [rdi+58h]
0x14001ab25  nop
0x14001ab26  mov     edx, [rdi+4]
0x14001ab29  mov     ecx, 42h ; 'B'
0x14001ab2e  mov     r8d, 6950534Dh
0x14001ab34  call    cs:__imp_ExAllocatePool2
0x14001ab3b  nop     dword ptr [rax+rax+00h]
0x14001ab40  mov     rbx, rax
0x14001ab43  test    al, 0Fh
0x14001ab45  jnz     loc_1401EEE46
0x14001ab4b  test    rax, rax
0x14001ab4e  jz      loc_14001ADAB
0x14001ab54  jmp     loc_14001ADA4
0x14001ab59  mov     rdi, r13
0x14001ab5c  lea     rdx, [rbx+10h]
0x14001ab60  jmp     short loc_14001AB29
0x14001ab62  movzx   esi, word ptr [rcx+0Ah]
0x14001ab66  add     esi, 7
0x14001ab69  and     esi, 0FFFFFFF8h
0x14001ab6c  jmp     loc_14001AAAA
0x14001ab71  mov     rbx, rax
0x14001ab74  test    rax, rax
0x14001ab77  jz      loc_14001AA4B
0x14001ab7d  mov     [rbx], rdi
0x14001ab80  add     rbx, 10h
0x14001ab84  test    rbx, rbx
0x14001ab87  jz      loc_14001AF85
0x14001ab8d  mov     [rbx+10h], esi
0x14001ab90  xorps   xmm0, xmm0
0x14001ab93  mov     [rbx+28h], rbp
0x14001ab97  xor     eax, eax
0x14001ab99  mov     [rbx+0Ch], r15d
0x14001ab9d  mov     [rbx+8], r15d
0x14001aba1  mov     [rbx+14h], r13w
0x14001aba6  movups  xmmword ptr [rbx+30h], xmm0
0x14001abaa  movups  xmmword ptr [rbx+40h], xmm0
0x14001abae  mov     [rbx+50h], rax
0x14001abb2  mov     [rbx+20h], r13d
0x14001abb6  test    r15d, r15d
0x14001abb9  jnz     short loc_14001AC11
0x14001abbb  mov     [rbx+18h], r13
0x14001abbf  mov     rdi, [r14+10h]
0x14001abc3  lea     r15, [r14+10h]
0x14001abc7  test    byte ptr [rdi+8], 40h
0x14001abcb  jnz     short loc_14001AC25
0x14001abcd  mov     eax, [rdi]
0x14001abcf  mov     [rbx+8], eax
0x14001abd2  mov     [rbx+20h], r13d
0x14001abd6  mov     [rbx+28h], rbp
0x14001abda  mov     rsi, [r14]
0x14001abdd  nop
0x14001abde  lock inc dword ptr [rsi+17Ch]
0x14001abe5  lea     rcx, [rsi+230h]
0x14001abec  nop
0x14001abed  call    cs:__imp_ExIsFastResourceHeldExclusive
0x14001abf4  nop     dword ptr [rax+rax+00h]
0x14001abf9  test    al, al
0x14001abfb  jnz     short loc_14001AC31
0x14001abfd  mov     r8b, 1; bool
0x14001ac00  lea     rcx, [rsi+230h]; this
0x14001ac07  mov     rdx, r12; struct CmsTransactionContext *
0x14001ac0a  call    ?AcquireShared@SmsPageLatch@@QEAA_NAEAVCmsTransactionContext@@_N@Z; SmsPageLatch::AcquireShared(CmsTransactionContext &,bool)
0x14001ac0f  jmp     short loc_14001AC37
0x14001ac11  lea     rcx, [rbx+58h]; void *
0x14001ac15  mov     r8d, r15d; Size
0x14001ac18  xor     edx, edx; Val
0x14001ac1a  mov     [rbx+18h], rcx
0x14001ac1e  call    memset
0x14001ac23  jmp     short loc_14001ABBF
0x14001ac25  movzx   eax, word ptr [rdi+0Ah]
0x14001ac29  add     eax, 7
0x14001ac2c  and     eax, 0FFFFFFF8h
0x14001ac2f  jmp     short loc_14001ABCF
0x14001ac31  inc     dword ptr [rsi+180h]
0x14001ac37  mov     rax, [rsi+60h]
0x14001ac3b  cmp     [rax+0Eh], r13b
0x14001ac3f  jl      short loc_14001AC49
0x14001ac41  inc     dword ptr [r12+0C4h]
0x14001ac49  inc     dword ptr [rsi+184h]
0x14001ac4f  mov     rcx, [r14]
0x14001ac52  mov     rdx, [r14+8]
0x14001ac56  mov     r8, [r15]
0x14001ac59  mov     r9d, [r14+18h]
0x14001ac5d  mov     r10, [r14+20h]
0x14001ac61  mov     r11d, [r14+1Ch]
0x14001ac65  cmp     [rbx+30h], r13
0x14001ac69  jnz     loc_14001AFB4
0x14001ac6f  mov     [rbx+30h], rcx
0x14001ac73  mov     [rbx+38h], rdx
0x14001ac77  mov     [rbx+40h], r8
0x14001ac7b  mov     [rbx+48h], r9d
0x14001ac7f  mov     [rbx+50h], r10
0x14001ac83  mov     [rbx+4Ch], r11d
0x14001ac87  mov     rax, [r14]
0x14001ac8a  test    rax, rax
0x14001ac8d  jz      short loc_14001ACAA
0x14001ac8f  cmp     [rax+188h], r13b
0x14001ac96  jnz     loc_14001AD86
0x14001ac9c  cmp     [rax+60h], rbp
0x14001aca0  jnz     loc_14001AD86
0x14001aca6  or      byte ptr [rbx+14h], 1
0x14001acaa  mov     eax, [rbx+8]
0x14001acad  test    eax, eax
0x14001acaf  jz      short loc_14001ACCE
0x14001acb1  mov     rcx, [rbx+18h]; void *
0x14001acb5  test    rdi, rdi
0x14001acb8  jz      loc_14001B071
0x14001acbe  cmp     rdi, rcx
0x14001acc1  jz      short loc_14001ACCE
0x14001acc3  mov     r8d, eax; Size
0x14001acc6  mov     rdx, rdi; Src
0x14001acc9  call    memmove
0x14001acce  mov     rax, [r12+90h]
0x14001acd6  xor     r8b, r8b
0x14001acd9  mov     [rbx], rax
0x14001acdc  mov     [r12+90h], rbx
0x14001ace4  mov     rax, [r14+8]
0x14001ace8  test    byte ptr [rax+0Dh], 1
0x14001acec  jnz     loc_14001B080
0x14001acf2  test    r8b, r8b
0x14001acf5  jnz     short loc_14001AD5A
0x14001acf7  mov     rcx, [r15]
0x14001acfa  mov     rbx, [r14+8]
0x14001acfe  mov     r8d, [r14+18h]
0x14001ad02  or      word ptr [rcx+8], 4
0x14001ad07  movzx   eax, word ptr [rcx+8]
0x14001ad0b  test    al, 40h
0x14001ad0d  jnz     short loc_14001AD7A
0x14001ad0f  mov     eax, [rcx]
0x14001ad11  mov     edx, [rbx+4]
0x14001ad14  sub     ecx, ebx
0x14001ad16  add     ecx, eax
0x14001ad18  cmp     ecx, edx
0x14001ad1a  jnz     short loc_14001AD21
0x14001ad1c  sub     edx, eax
0x14001ad1e  mov     [rbx+4], edx
0x14001ad21  add     eax, 4
0x14001ad24  add     [rbx+8], eax
0x14001ad27  test    r8d, r8d
0x14001ad2a  jz      short loc_14001AD3F
0x14001ad2c  mov     edx, [rbx+10h]
0x14001ad2f  add     rdx, rbx; Src
0x14001ad32  shl     r8, 2; Size
0x14001ad36  lea     rcx, [rdx+4]; void *
0x14001ad3a  call    memmove
0x14001ad3f  add     dword ptr [rbx+10h], 4
0x14001ad43  add     dword ptr [rbx+14h], 0FFFFFFFFh
0x14001ad47  mov     ecx, [rbx+14h]
0x14001ad4a  jz      loc_14001B092
0x14001ad50  test    byte ptr [rbx+0Dh], 1
0x14001ad54  jnz     loc_14001B089
0x14001ad5a  mov     rax, [r14]
0x14001ad5d  nop
0x14001ad5e  lock inc dword ptr [rax+174h]
0x14001ad65  nop
0x14001ad66  xor     eax, eax
0x14001ad68  add     rsp, 48h
0x14001ad6c  pop     r15
0x14001ad6e  pop     r14
0x14001ad70  pop     r13
0x14001ad72  pop     r12
0x14001ad74  pop     rdi
  ... truncated ...
```
