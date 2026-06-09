# CmsBPlusTable::DeleteIndexEntry(CmsTransactionContext *,SmsLookupStack &,ulong)

- ea: `0x14003fb10`
- end: `0x14004028f`
- name: `?DeleteIndexEntry@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@AEAUSmsLookupStack@@K@Z`
- size: `1919`
- prototype: `__int64 __fastcall(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, struct SmsLookupStack *, unsigned int)`
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003ca00`
- `0x14003f39c`
- `0x14003f780`
- `0x14005e540`
- `0x140062700`

## callees

- `0x14002dd70`
- `0x14003f0f0`
- `0x14003fb10`
- `0x140068ef0`
- `0x140083220`
- `0x14009dec0`
- `0x1400aa3bc`
- `0x1400cbe48`
- `0x1400ceda0`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140040157`
- `ntoskrnl!KdDebuggerEnabled` at `0x14004017f`
- `ntoskrnl!KdDebuggerEnabled` at `0x14004018e`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400401a4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400401c8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040233`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400401c8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040233`
- `ntoskrnl!ExAllocatePool2` at `0x14003fbcc`
- `ntoskrnl!ExAllocatePool2` at `0x14003fd24`
- `ntoskrnl!ExAllocatePool2` at `0x14003fbcc`
- `ntoskrnl!ExAllocatePool2` at `0x14003fd24`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003fb90`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003fcb4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003fb90`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003fcb4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fc390`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fc40e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fc390`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fc40e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400401e5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140040250`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400401e5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140040250`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003fddd`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14003fddd`

## string_xrefs

- `0x1401fc420`: `Lookaside list allocation must be double quad aligned.`

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
  __int64 v13; // r9
  unsigned __int64 v14; // rdx
  __int64 Pool2; // rax
  __int64 Undo; // rbx
  int v17; // ecx
  unsigned int v18; // ecx
  int v19; // edx
  int v20; // r15d
  __int64 v21; // rcx
  unsigned int v22; // esi
  unsigned __int64 v23; // rbx
  unsigned int *v24; // rdi
  __int64 v25; // r9
  int v26; // ecx
  unsigned __int64 v27; // rdx
  __int64 v28; // rax
  CmsBPlusTable *v29; // rcx
  unsigned int *v30; // rdi
  char *v31; // r15
  unsigned int v32; // eax
  __int64 v33; // rsi
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // r9d
  __int64 v37; // r10
  int v38; // r11d
  __int64 v39; // rax
  unsigned int v40; // eax
  unsigned int *v41; // rcx
  char v42; // r8
  __int64 v43; // rcx
  __int64 v44; // rbx
  __int64 v45; // r8
  unsigned int v46; // eax
  int v47; // edx
  bool v48; // zf
  unsigned int *v50; // rdi
  unsigned int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // r8
  int v54; // r9d
  __int64 v55; // r10
  int v56; // r11d
  __int64 v57; // rax
  unsigned int v58; // eax
  unsigned int *v59; // rcx
  unsigned int *v60; // rcx
  unsigned int v61; // eax
  struct _NPAGED_LOOKASIDE_LIST *v62; // rcx
  void *v63; // rax
  struct _NPAGED_LOOKASIDE_LIST *v64; // rcx
  void *v65; // rax
  char v66; // cl
  __int64 v67; // rdx
  __int64 v68; // rcx
  int v69; // [rsp+20h] [rbp-68h]
  struct _SmsIndexEntry *v70; // [rsp+A0h] [rbp+18h]

  v6 = *((_QWORD *)a3 + 1);
  if ( (*(_BYTE *)(v6 + 13) & 1) == 0 || (v18 = *(_DWORD *)(v6 + 20), v19 = *((_DWORD *)a3 + 6), v19 != v18 - 1) )
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
    v12 = (unsigned int *)(qword_140269410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( v11 > *v12 )
    {
      v12 = 0;
      v14 = v11 + 16;
      goto LABEL_9;
    }
    if ( !*((_BYTE *)v12 + 8) )
    {
      if ( (int)*((_QWORD *)v12 + 11) > (int)HIDWORD(*((_QWORD *)v12 + 11)) )
      {
        v17 = _InterlockedDecrement((volatile signed __int32 *)v12 + 22);
        if ( v17 >= (int)v12[23] && v17 >= 0 )
        {
          v65 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v12 + 4);
          goto LABEL_34;
        }
        _InterlockedIncrement((volatile signed __int32 *)v12 + 22);
      }
LABEL_17:
      v14 = v12[1];
LABEL_9:
      Pool2 = ExAllocatePool2(66, v14, 1766871885, v13);
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
          v30 = (unsigned int *)*((_QWORD *)a3 + 2);
          v31 = (char *)a3 + 16;
          if ( (v30[2] & 0x40) != 0 )
            v32 = (*((unsigned __int16 *)v30 + 5) + 7) & 0xFFFFFFF8;
          else
            v32 = *v30;
          *(_DWORD *)(Undo + 8) = v32;
          *(_DWORD *)(Undo + 32) = 0;
          *(_QWORD *)(Undo + 40) = this;
          v33 = *(_QWORD *)a3;
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)a3 + 380LL));
          if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v33 + 560) )
            ++*(_DWORD *)(v33 + 384);
          else
            SmsPageLatch::AcquireShared((SmsPageLatch *)(v33 + 560), a2, 1);
          if ( *(char *)(*(_QWORD *)(v33 + 96) + 14LL) >= 0 )
            ++*((_DWORD *)a2 + 49);
          ++*(_DWORD *)(v33 + 388);
          v34 = *((_QWORD *)a3 + 1);
          v35 = *(_QWORD *)v31;
          v36 = *((_DWORD *)a3 + 6);
          v37 = *((_QWORD *)a3 + 4);
          v38 = *((_DWORD *)a3 + 7);
          if ( *(_QWORD *)(Undo + 48) && (_BYTE)KdDebuggerEnabled )
            __debugbreak();
          *(_QWORD *)(Undo + 48) = *(_QWORD *)a3;
          *(_QWORD *)(Undo + 56) = v34;
          *(_QWORD *)(Undo + 64) = v35;
          *(_DWORD *)(Undo + 72) = v36;
          *(_QWORD *)(Undo + 80) = v37;
          *(_DWORD *)(Undo + 76) = v38;
          v39 = *(_QWORD *)a3;
          if ( *(_QWORD *)a3
            && (!*(_BYTE *)(v39 + 392) && *(CmsBPlusTable **)(v39 + 96) == this || !*((_BYTE *)this + 212)) )
          {
            *(_BYTE *)(Undo + 20) |= 1u;
          }
          v40 = *(_DWORD *)(Undo + 8);
          if ( v40 )
          {
            v41 = *(unsigned int **)(Undo + 24);
            if ( v30 )
            {
              if ( v30 != v41 )
                memmove(v41, v30, v40);
            }
            else
            {
              memset(v41, 0, *(unsigned int *)(Undo + 8));
            }
          }
          v42 = 0;
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
    v64 = (struct _NPAGED_LOOKASIDE_LIST *)(v12 + 16);
    if ( *((_BYTE *)v12 + 9) )
      v65 = ExAllocateFromNPagedLookasideList(v64);
    else
      v65 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v64);
LABEL_34:
    Undo = (__int64)v65;
    if ( v65 )
      goto LABEL_35;
    goto LABEL_17;
  }
  v20 = (a4 != 0) + 2;
  if ( v18 > 1 )
  {
    v21 = v6 + *(unsigned __int16 *)(v6 + *(unsigned int *)(v6 + 16) + 4LL * (unsigned int)(v19 - 1));
    v70 = (struct _SmsIndexEntry *)v21;
    if ( (*(_BYTE *)(v21 + 8) & 0x40) != 0 )
      v22 = (*(unsigned __int16 *)(v21 + 10) + 7) & 0xFFFFFFF8;
    else
      v22 = *(_DWORD *)v21;
    if ( (*(_DWORD *)a2 & 0x1000LL) == 0 )
    {
      v23 = ((v22 + 7) & 0xFFFFFFF8) + 88;
      v24 = (unsigned int *)(qword_140269410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v23 > *v24 )
      {
        v24 = 0;
        v27 = v23 + 16;
LABEL_29:
        v28 = ExAllocatePool2(66, v27, 1766871885, v25);
        Undo = v28;
        if ( (v28 & 0xF) == 0 )
        {
          if ( !v28 )
            goto LABEL_75;
          goto LABEL_74;
        }
LABEL_128:
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      }
      if ( !*((_BYTE *)v24 + 8) )
      {
        if ( (int)*((_QWORD *)v24 + 11) > (int)HIDWORD(*((_QWORD *)v24 + 11)) )
        {
          v26 = _InterlockedDecrement((volatile signed __int32 *)v24 + 22);
          if ( v26 >= (int)v24[23] && v26 >= 0 )
          {
            v63 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v24 + 4);
            goto LABEL_73;
          }
          _InterlockedIncrement((volatile signed __int32 *)v24 + 22);
        }
LABEL_28:
        v27 = v24[1];
        goto LABEL_29;
      }
      v62 = (struct _NPAGED_LOOKASIDE_LIST *)(v24 + 16);
      if ( *((_BYTE *)v24 + 9) )
        v63 = ExAllocateFromNPagedLookasideList(v62);
      else
        v63 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v62);
LABEL_73:
      Undo = (__int64)v63;
      if ( v63 )
      {
LABEL_74:
        *(_QWORD *)Undo = v24;
        Undo += 16;
LABEL_75:
        if ( Undo )
        {
          *(_DWORD *)(Undo + 16) = v20;
          *(_QWORD *)(Undo + 40) = this;
          *(_DWORD *)(Undo + 12) = v22;
          *(_DWORD *)(Undo + 8) = v22;
          *(_WORD *)(Undo + 20) = 0;
          *(_OWORD *)(Undo + 48) = 0;
          *(_OWORD *)(Undo + 64) = 0;
          *(_QWORD *)(Undo + 80) = 0;
          *(_DWORD *)(Undo + 32) = 0;
          if ( v22 )
          {
            *(_QWORD *)(Undo + 24) = Undo + 88;
            memset((void *)(Undo + 88), 0, v22);
          }
          else
          {
            *(_QWORD *)(Undo + 24) = 0;
          }
          v31 = (char *)a3 + 16;
          CmsBPlusTable::SwapDirectorData(v29, v70, *((struct _SmsIndexEntry **)a3 + 2));
          v50 = (unsigned int *)(*((_QWORD *)a3 + 1)
                               + *(unsigned __int16 *)(*((_QWORD *)a3 + 1)
                                                     + *(unsigned int *)(*((_QWORD *)a3 + 1) + 16LL)
                                                     + 4LL * (unsigned int)--*((_DWORD *)a3 + 6)));
          *((_QWORD *)a3 + 2) = v50;
          if ( (v50[2] & 0x40) != 0 )
            v51 = (*((unsigned __int16 *)v50 + 5) + 7) & 0xFFFFFFF8;
          else
            v51 = *v50;
          *(_DWORD *)(Undo + 8) = v51;
          *(_DWORD *)(Undo + 32) = 0;
          *(_QWORD *)(Undo + 40) = this;
          SmsPage::Repin(*(_QWORD *)a3, a2, 2);
          v52 = *((_QWORD *)a3 + 1);
          v53 = *(_QWORD *)v31;
          v54 = *((_DWORD *)a3 + 6);
          v55 = *((_QWORD *)a3 + 4);
          v56 = *((_DWORD *)a3 + 7);
          if ( *(_QWORD *)(Undo + 48) && (_BYTE)KdDebuggerEnabled )
            __debugbreak();
          *(_QWORD *)(Undo + 48) = *(_QWORD *)a3;
          *(_QWORD *)(Undo + 56) = v52;
          *(_QWORD *)(Undo + 64) = v53;
          *(_DWORD *)(Undo + 72) = v54;
          *(_QWORD *)(Undo + 80) = v55;
          *(_DWORD *)(Undo + 76) = v56;
          v57 = *(_QWORD *)a3;
          if ( *(_QWORD *)a3
            && (!*(_BYTE *)(v57 + 392) && *(CmsBPlusTable **)(v57 + 96) == this || !*((_BYTE *)this + 212)) )
          {
            *(_BYTE *)(Undo + 20) |= 1u;
          }
          v58 = *(_DWORD *)(Undo + 8);
          if ( v58 )
          {
            v59 = *(unsigned int **)(Undo + 24);
            if ( v50 )
            {
              if ( v50 != v59 )
                memmove(v59, v50, v58);
            }
            else
            {
              memset(v59, 0, *(unsigned int *)(Undo + 8));
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
  v31 = (char *)a3 + 16;
  Undo = CmsBPlusTable::AllocateUndo(this, a2, (unsigned int)(a4 != 0) + 2);
  if ( !Undo )
    return 3221225626LL;
  v60 = *(unsigned int **)v31;
  if ( (*(_BYTE *)(*(_QWORD *)v31 + 8LL) & 0x40) != 0 )
    v61 = (*((unsigned __int16 *)v60 + 5) + 7) & 0xFFFFFFF8;
  else
    v61 = *v60;
  CmsBPlusTable::FormatUndoRecord(this, a2, (struct SmsUndoRecord *)Undo, a3, v60, v61, 0);
  *(_BYTE *)(Undo + 21) = 0;
  v66 = *((_BYTE *)this + 212);
  if ( v66 == *(_BYTE *)(*((_QWORD *)a3 + 1) + 12LL) )
  {
    *(_BYTE *)(Undo + 21) = v66;
    v67 = *((_QWORD *)this + 3);
    *((_BYTE *)this + 212) = 0;
    v68 = *((_QWORD *)a3 + 1);
    LOBYTE(v69) = *(_BYTE *)(v68 + 13) & 0xF6;
    _SmsIndexHeader::InitializeIndexHeader(v68, v67, *(unsigned int *)(v68 + 32), 0, v69, 0);
    v42 = 1;
    goto LABEL_91;
  }
LABEL_90:
  v42 = 0;
LABEL_91:
  *(_BYTE *)(Undo + 20) |= 2u;
LABEL_58:
  if ( (*(_BYTE *)(*((_QWORD *)a3 + 1) + 13LL) & 1) != 0 )
    *(_BYTE *)(Undo + 20) |= 8u;
  if ( !v42 )
  {
    v43 = *(_QWORD *)v31;
    v44 = *((_QWORD *)a3 + 1);
    v45 = *((unsigned int *)a3 + 6);
    *(_WORD *)(v43 + 8) |= 4u;
    if ( (*(_WORD *)(v43 + 8) & 0x40) != 0 )
      v46 = (*(unsigned __int16 *)(v43 + 10) + 7) & 0xFFFFFFF8;
    else
      v46 = *(_DWORD *)v43;
    v47 = *(_DWORD *)(v44 + 4);
    if ( v46 + (_DWORD)v43 - (_DWORD)v44 == v47 )
      *(_DWORD *)(v44 + 4) = v47 - v46;
    *(_DWORD *)(v44 + 8) += v46 + 4;
    if ( (_DWORD)v45 )
      memmove(
        (void *)(v44 + *(unsigned int *)(v44 + 16) + 4),
        (const void *)(v44 + *(unsigned int *)(v44 + 16)),
        4 * v45);
    *(_DWORD *)(v44 + 16) += 4;
    v48 = (*(_DWORD *)(v44 + 20))-- == 1;
    if ( v48 || (*(_BYTE *)(v44 + 13) & 1) != 0 && *(_DWORD *)(v44 + 20) == 1 )
    {
      *(_BYTE *)(v44 + 13) &= ~8u;
      *(_QWORD *)(v44 + 24) = 0;
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)a3 + 372LL));
  return 0;
}

```

## disassembly

```asm
0x14003fb10  push    rbx
0x14003fb12  push    rbp
0x14003fb13  push    rsi
0x14003fb14  push    rdi
0x14003fb15  push    r12
0x14003fb17  push    r13
0x14003fb19  push    r14
0x14003fb1b  push    r15
0x14003fb1d  sub     rsp, 48h
0x14003fb21  mov     r14, r8
0x14003fb24  mov     r12, rdx
0x14003fb27  mov     r8, [r8+8]
0x14003fb2b  mov     rbp, rcx
0x14003fb2e  test    byte ptr [r8+0Dh], 1
0x14003fb33  jnz     loc_14003FC40
0x14003fb39  mov     r15, [r14+10h]
0x14003fb3d  xor     r13d, r13d
0x14003fb40  test    r9d, r9d
0x14003fb43  mov     esi, r13d
0x14003fb46  setnz   sil
0x14003fb4a  add     esi, 2
0x14003fb4d  test    byte ptr [r15+8], 40h
0x14003fb52  jnz     loc_14003FBF1
0x14003fb58  mov     r15d, [r15]
0x14003fb5b  test    byte ptr [rbp+0Eh], 7
0x14003fb5f  jnz     loc_140040205
0x14003fb65  mov     rax, [rbp+18h]
0x14003fb69  mov     ecx, [rax+2Ch]
0x14003fb6c  test    cl, 2
0x14003fb6f  jnz     loc_14004020F
0x14003fb75  mov     eax, [r12]
0x14003fb79  bt      rax, 0Ch
0x14003fb7e  jb      loc_140040157
0x14003fb84  lea     ebx, [r15+7]
0x14003fb88  xor     ecx, ecx; ProcNumber
0x14003fb8a  and     ebx, 0FFFFFFF8h
0x14003fb8d  add     ebx, 58h ; 'X'
0x14003fb90  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14003fb97  nop     dword ptr [rax+rax+00h]
0x14003fb9c  xor     edx, edx
0x14003fb9e  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14003fba4  lea     rdi, [rdx+rdx*2]
0x14003fba8  shl     rdi, 6
0x14003fbac  add     rdi, cs:qword_140269410
0x14003fbb3  mov     eax, [rdi]
0x14003fbb5  cmp     rbx, rax
0x14003fbb8  jbe     short loc_14003FC03
0x14003fbba  mov     rdi, r13
0x14003fbbd  lea     rdx, [rbx+10h]
0x14003fbc1  mov     ecx, 42h ; 'B'
0x14003fbc6  mov     r8d, 6950534Dh
0x14003fbcc  call    cs:__imp_ExAllocatePool2
0x14003fbd3  nop     dword ptr [rax+rax+00h]
0x14003fbd8  mov     rbx, rax
0x14003fbdb  test    al, 0Fh
0x14003fbdd  jnz     loc_1401FC420
0x14003fbe3  test    rax, rax
0x14003fbe6  jz      loc_14003FD74
0x14003fbec  jmp     loc_14003FD6D
0x14003fbf1  movzx   r15d, word ptr [r15+0Ah]
0x14003fbf6  add     r15d, 7
0x14003fbfa  and     r15d, 0FFFFFFF8h
0x14003fbfe  jmp     loc_14003FB5B
0x14003fc03  cmp     [rdi+8], r13b
0x14003fc07  jnz     loc_140040225
0x14003fc0d  mov     rcx, [rdi+58h]
0x14003fc11  mov     rax, rcx
0x14003fc14  shr     rax, 20h
0x14003fc18  cmp     ecx, eax
0x14003fc1a  jle     short loc_14003FC3B
0x14003fc1c  nop
0x14003fc1d  mov     ecx, 0FFFFFFFFh
0x14003fc22  lock xadd [rdi+58h], ecx
0x14003fc27  nop
0x14003fc28  dec     ecx
0x14003fc2a  mov     eax, [rdi+5Ch]
0x14003fc2d  cmp     ecx, eax
0x14003fc2f  jge     loc_140040244
0x14003fc35  nop
0x14003fc36  lock inc dword ptr [rdi+58h]
0x14003fc3a  nop
0x14003fc3b  mov     edx, [rdi+4]
0x14003fc3e  jmp     short loc_14003FBC1
0x14003fc40  mov     ecx, [r8+14h]
0x14003fc44  mov     edx, [r14+18h]
0x14003fc48  lea     eax, [rcx-1]
0x14003fc4b  cmp     edx, eax
0x14003fc4d  jnz     loc_14003FB39
0x14003fc53  xor     r13d, r13d
0x14003fc56  test    r9d, r9d
0x14003fc59  mov     r15d, r13d
0x14003fc5c  setnz   r15b
0x14003fc60  add     r15d, 2
0x14003fc64  mov     dword ptr [rsp+88h+arg_10], r15d
0x14003fc6c  cmp     ecx, 1
0x14003fc6f  jbe     loc_1400400F8
0x14003fc75  mov     ecx, [r8+10h]
0x14003fc79  lea     eax, [rdx-1]
0x14003fc7c  add     rcx, r8
0x14003fc7f  movzx   ecx, word ptr [rcx+rax*4]
0x14003fc83  add     rcx, r8
0x14003fc86  mov     [rsp+88h+arg_10], rcx
0x14003fc8e  test    byte ptr [rcx+8], 40h
0x14003fc92  jnz     loc_14003FD52
0x14003fc98  mov     esi, [rcx]
0x14003fc9a  mov     eax, [r12]
0x14003fc9e  bt      rax, 0Ch
0x14003fca3  jb      loc_14004017F
0x14003fca9  lea     ebx, [rsi+7]
0x14003fcac  xor     ecx, ecx; ProcNumber
0x14003fcae  and     ebx, 0FFFFFFF8h
0x14003fcb1  add     ebx, 58h ; 'X'
0x14003fcb4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14003fcbb  nop     dword ptr [rax+rax+00h]
0x14003fcc0  xor     edx, edx
0x14003fcc2  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14003fcc8  lea     rdi, [rdx+rdx*2]
0x14003fccc  shl     rdi, 6
0x14003fcd0  add     rdi, cs:qword_140269410
0x14003fcd7  mov     eax, [rdi]
0x14003fcd9  cmp     rbx, rax
0x14003fcdc  ja      short loc_14003FD49
0x14003fcde  cmp     [rdi+8], r13b
0x14003fce2  jnz     loc_1400401BA
0x14003fce8  mov     rcx, [rdi+58h]
0x14003fcec  mov     rax, rcx
0x14003fcef  shr     rax, 20h
0x14003fcf3  cmp     ecx, eax
0x14003fcf5  jle     short loc_14003FD16
0x14003fcf7  nop
0x14003fcf8  mov     ecx, 0FFFFFFFFh
0x14003fcfd  lock xadd [rdi+58h], ecx
0x14003fd02  nop
0x14003fd03  dec     ecx
0x14003fd05  mov     eax, [rdi+5Ch]
0x14003fd08  cmp     ecx, eax
0x14003fd0a  jge     loc_1400401D9
0x14003fd10  nop
0x14003fd11  lock inc dword ptr [rdi+58h]
0x14003fd15  nop
0x14003fd16  mov     edx, [rdi+4]
0x14003fd19  mov     ecx, 42h ; 'B'
0x14003fd1e  mov     r8d, 6950534Dh
0x14003fd24  call    cs:__imp_ExAllocatePool2
0x14003fd2b  nop     dword ptr [rax+rax+00h]
0x14003fd30  mov     rbx, rax
0x14003fd33  test    al, 0Fh
0x14003fd35  jnz     loc_1401FC420
0x14003fd3b  test    rax, rax
0x14003fd3e  jz      loc_14003FF9B
0x14003fd44  jmp     loc_14003FF94
0x14003fd49  mov     rdi, r13
0x14003fd4c  lea     rdx, [rbx+10h]
0x14003fd50  jmp     short loc_14003FD19
0x14003fd52  movzx   esi, word ptr [rcx+0Ah]
0x14003fd56  add     esi, 7
0x14003fd59  and     esi, 0FFFFFFF8h
0x14003fd5c  jmp     loc_14003FC9A
0x14003fd61  mov     rbx, rax
0x14003fd64  test    rax, rax
0x14003fd67  jz      loc_14003FC3B
0x14003fd6d  mov     [rbx], rdi
0x14003fd70  add     rbx, 10h
0x14003fd74  test    rbx, rbx
0x14003fd77  jz      loc_140040175
0x14003fd7d  mov     [rbx+10h], esi
0x14003fd80  xorps   xmm0, xmm0
0x14003fd83  mov     [rbx+28h], rbp
0x14003fd87  xor     eax, eax
0x14003fd89  mov     [rbx+0Ch], r15d
0x14003fd8d  mov     [rbx+8], r15d
0x14003fd91  mov     [rbx+14h], r13w
0x14003fd96  movups  xmmword ptr [rbx+30h], xmm0
0x14003fd9a  movups  xmmword ptr [rbx+40h], xmm0
0x14003fd9e  mov     [rbx+50h], rax
0x14003fda2  mov     [rbx+20h], r13d
0x14003fda6  test    r15d, r15d
0x14003fda9  jnz     short loc_14003FE01
0x14003fdab  mov     [rbx+18h], r13
0x14003fdaf  mov     rdi, [r14+10h]
0x14003fdb3  lea     r15, [r14+10h]
0x14003fdb7  test    byte ptr [rdi+8], 40h
0x14003fdbb  jnz     short loc_14003FE15
0x14003fdbd  mov     eax, [rdi]
0x14003fdbf  mov     [rbx+8], eax
0x14003fdc2  mov     [rbx+20h], r13d
0x14003fdc6  mov     [rbx+28h], rbp
0x14003fdca  mov     rsi, [r14]
0x14003fdcd  nop
0x14003fdce  lock inc dword ptr [rsi+17Ch]
0x14003fdd5  lea     rcx, [rsi+230h]
0x14003fddc  nop
0x14003fddd  call    cs:__imp_ExIsFastResourceHeldExclusive
0x14003fde4  nop     dword ptr [rax+rax+00h]
0x14003fde9  test    al, al
0x14003fdeb  jnz     short loc_14003FE21
0x14003fded  mov     r8b, 1; bool
0x14003fdf0  lea     rcx, [rsi+230h]; this
0x14003fdf7  mov     rdx, r12; struct CmsTransactionContext *
0x14003fdfa  call    ?AcquireShared@SmsPageLatch@@QEAA_NAEAVCmsTransactionContext@@_N@Z; SmsPageLatch::AcquireShared(CmsTransactionContext &,bool)
0x14003fdff  jmp     short loc_14003FE27
0x14003fe01  lea     rcx, [rbx+58h]; void *
0x14003fe05  mov     r8d, r15d; Size
0x14003fe08  xor     edx, edx; Val
0x14003fe0a  mov     [rbx+18h], rcx
0x14003fe0e  call    memset
0x14003fe13  jmp     short loc_14003FDAF
0x14003fe15  movzx   eax, word ptr [rdi+0Ah]
0x14003fe19  add     eax, 7
0x14003fe1c  and     eax, 0FFFFFFF8h
0x14003fe1f  jmp     short loc_14003FDBF
0x14003fe21  inc     dword ptr [rsi+180h]
0x14003fe27  mov     rax, [rsi+60h]
0x14003fe2b  cmp     [rax+0Eh], r13b
0x14003fe2f  jl      short loc_14003FE39
0x14003fe31  inc     dword ptr [r12+0C4h]
0x14003fe39  inc     dword ptr [rsi+184h]
0x14003fe3f  mov     rcx, [r14]
0x14003fe42  mov     rdx, [r14+8]
0x14003fe46  mov     r8, [r15]
0x14003fe49  mov     r9d, [r14+18h]
0x14003fe4d  mov     r10, [r14+20h]
0x14003fe51  mov     r11d, [r14+1Ch]
0x14003fe55  cmp     [rbx+30h], r13
0x14003fe59  jnz     loc_1400401A4
0x14003fe5f  mov     [rbx+30h], rcx
0x14003fe63  mov     [rbx+38h], rdx
0x14003fe67  mov     [rbx+40h], r8
0x14003fe6b  mov     [rbx+48h], r9d
0x14003fe6f  mov     [rbx+50h], r10
0x14003fe73  mov     [rbx+4Ch], r11d
0x14003fe77  mov     rax, [r14]
0x14003fe7a  test    rax, rax
0x14003fe7d  jz      short loc_14003FE9A
0x14003fe7f  cmp     [rax+188h], r13b
0x14003fe86  jnz     loc_14003FF76
0x14003fe8c  cmp     [rax+60h], rbp
0x14003fe90  jnz     loc_14003FF76
0x14003fe96  or      byte ptr [rbx+14h], 1
0x14003fe9a  mov     eax, [rbx+8]
0x14003fe9d  test    eax, eax
0x14003fe9f  jz      short loc_14003FEBE
0x14003fea1  mov     rcx, [rbx+18h]; void *
0x14003fea5  test    rdi, rdi
0x14003fea8  jz      loc_140040261
0x14003feae  cmp     rdi, rcx
0x14003feb1  jz      short loc_14003FEBE
0x14003feb3  mov     r8d, eax; Size
0x14003feb6  mov     rdx, rdi; Src
0x14003feb9  call    memmove
0x14003febe  mov     rax, [r12+90h]
0x14003fec6  xor     r8b, r8b
0x14003fec9  mov     [rbx], rax
0x14003fecc  mov     [r12+90h], rbx
0x14003fed4  mov     rax, [r14+8]
0x14003fed8  test    byte ptr [rax+0Dh], 1
0x14003fedc  jnz     loc_140040270
0x14003fee2  test    r8b, r8b
0x14003fee5  jnz     short loc_14003FF4A
0x14003fee7  mov     rcx, [r15]
0x14003feea  mov     rbx, [r14+8]
0x14003feee  mov     r8d, [r14+18h]
0x14003fef2  or      word ptr [rcx+8], 4
0x14003fef7  movzx   eax, word ptr [rcx+8]
0x14003fefb  test    al, 40h
0x14003fefd  jnz     short loc_14003FF6A
0x14003feff  mov     eax, [rcx]
0x14003ff01  mov     edx, [rbx+4]
0x14003ff04  sub     ecx, ebx
0x14003ff06  add     ecx, eax
0x14003ff08  cmp     ecx, edx
0x14003ff0a  jnz     short loc_14003FF11
0x14003ff0c  sub     edx, eax
0x14003ff0e  mov     [rbx+4], edx
0x14003ff11  add     eax, 4
0x14003ff14  add     [rbx+8], eax
0x14003ff17  test    r8d, r8d
0x14003ff1a  jz      short loc_14003FF2F
0x14003ff1c  mov     edx, [rbx+10h]
0x14003ff1f  add     rdx, rbx; Src
0x14003ff22  shl     r8, 2; Size
0x14003ff26  lea     rcx, [rdx+4]; void *
0x14003ff2a  call    memmove
0x14003ff2f  add     dword ptr [rbx+10h], 4
0x14003ff33  add     dword ptr [rbx+14h], 0FFFFFFFFh
0x14003ff37  mov     ecx, [rbx+14h]
0x14003ff3a  jz      loc_140040282
0x14003ff40  test    byte ptr [rbx+0Dh], 1
0x14003ff44  jnz     loc_140040279
0x14003ff4a  mov     rax, [r14]
0x14003ff4d  nop
0x14003ff4e  lock inc dword ptr [rax+174h]
0x14003ff55  nop
0x14003ff56  xor     eax, eax
0x14003ff58  add     rsp, 48h
0x14003ff5c  pop     r15
0x14003ff5e  pop     r14
0x14003ff60  pop     r13
0x14003ff62  pop     r12
0x14003ff64  pop     rdi
  ... truncated ...
```
