# CmsCountMap::AddEntry(CmsTransactionCore *,_RANGE *,_SmsPreAllocatedRow *,_RTL_AVL_ENTRY * *)

- ea: `0x14007a200`
- end: `0x14007aa27`
- name: `?AddEntry@CmsCountMap@@QEAAJPEAVCmsTransactionCore@@PEAU_RANGE@@PEAU_SmsPreAllocatedRow@@PEAPEAU_RTL_AVL_ENTRY@@@Z`
- size: `2087`
- prototype: `__int64 __usercall@<rax>(CmsCountMap *__hidden this@<rcx>, struct CmsTransactionCore *@<rdx>, struct _RANGE *@<r8>, struct _SmsPreAllocatedRow *@<r9>, struct _RTL_AVL_ENTRY **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400cd694`

## callees

- `0x14003bf40`
- `0x14004b8d0`
- `0x14004c580`
- `0x14007a200`
- `0x14007aa30`
- `0x14007ab30`
- `0x1400ceda0`
- `0x1401f3fb0`
- `0x1401f4090`
- `0x1401f4100`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007a954`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007a990`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007a954`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007a990`
- `ntoskrnl!ExAllocatePool2` at `0x14007a640`
- `ntoskrnl!ExAllocatePool2` at `0x14007a69f`
- `ntoskrnl!ExAllocatePool2` at `0x14007a716`
- `ntoskrnl!ExAllocatePool2` at `0x14007a640`
- `ntoskrnl!ExAllocatePool2` at `0x14007a69f`
- `ntoskrnl!ExAllocatePool2` at `0x14007a716`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007a5fe`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007a66d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007a5fe`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007a66d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ff719`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ff72b`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ff719`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ff72b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007a971`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007a9ad`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007a971`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007a9ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a53a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a53a`

## string_xrefs

- `0x1401ff73d`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsCountMap::AddEntry(
        CmsCountMap *this,
        struct CmsTransactionCore *a2,
        struct _RANGE *a3,
        struct _SmsPreAllocatedRow *a4,
        struct _RTL_AVL_ENTRY **a5)
{
  struct _SmsPreAllocatedRow *v5; // r12
  unsigned int v9; // r13d
  unsigned int v10; // ecx
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  char *v14; // rcx
  char *v15; // rcx
  __int64 v16; // r15
  __int128 v17; // xmm1
  __int64 v18; // rcx
  struct CmsTransactionCore *v19; // rdx
  int v20; // eax
  __int64 v21; // r9
  struct _RTL_AVL_ENTRY *v22; // rsi
  struct _RTL_AVL_ENTRY *v23; // rdi
  int v24; // r14d
  char v25; // r10
  struct _SmsPreAllocatedRow *v26; // r8
  unsigned int v27; // edx
  unsigned __int8 v28; // dl
  char *v29; // rcx
  char *v30; // rcx
  char *v31; // rax
  __int64 v32; // rcx
  struct _RTL_AVL_ENTRY **v33; // rdx
  CmsCountMap *v34; // r13
  int NodeOrParentIn; // eax
  struct _RTL_AVL_ENTRY *v36; // rdx
  int v37; // r15d
  struct _RTL_AVL_ENTRY *v38; // rcx
  struct _RTL_AVL_ENTRY *v40; // rax
  unsigned int v41; // eax
  unsigned __int64 v42; // r14
  __int64 v43; // r9
  unsigned int *v44; // r13
  unsigned __int64 v45; // rdx
  __int64 v46; // rax
  __int64 Pool2; // r14
  __int64 v48; // r9
  __int64 v49; // r13
  unsigned __int64 v50; // rdx
  __int64 v51; // rax
  int v52; // ecx
  __int16 v53; // r12
  __int16 v54; // ax
  int v55; // ecx
  __int64 v56; // rax
  __int64 v57; // rcx
  struct CmsTransactionCore *v58; // rdx
  int v59; // eax
  int v60; // eax
  struct _NPAGED_LOOKASIDE_LIST *v61; // rcx
  void *v62; // rax
  struct _NPAGED_LOOKASIDE_LIST *v63; // rcx
  void *v64; // rax
  __int64 v65; // rax
  _QWORD *v66; // rcx
  __int64 i; // rdx
  bool v68; // zf
  char v69; // cl
  char v70; // al
  char v71; // [rsp+30h] [rbp-D0h]
  char v72; // [rsp+30h] [rbp-D0h]
  int v73; // [rsp+34h] [rbp-CCh]
  __int64 v74; // [rsp+38h] [rbp-C8h]
  struct _RTL_AVL_ENTRY *v75[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v76; // [rsp+50h] [rbp-B0h]
  int v77; // [rsp+60h] [rbp-A0h]
  CmsCountMap *v78; // [rsp+68h] [rbp-98h]
  struct _SmsPreAllocatedRow *v79; // [rsp+70h] [rbp-90h]
  __int128 v80; // [rsp+78h] [rbp-88h] BYREF
  void *Src[2]; // [rsp+88h] [rbp-78h]
  struct _RTL_AVL_ENTRY **v82; // [rsp+98h] [rbp-68h]
  int v83; // [rsp+B0h] [rbp-50h] BYREF
  __int16 epi16; // [rsp+B4h] [rbp-4Ch]
  __int16 v85; // [rsp+B6h] [rbp-4Ah]
  unsigned __int64 v86; // [rsp+B8h] [rbp-48h]
  int v87; // [rsp+C0h] [rbp-40h]
  int v88; // [rsp+C4h] [rbp-3Ch]
  _QWORD *v89; // [rsp+C8h] [rbp-38h]
  PVOID P; // [rsp+D0h] [rbp-30h]
  char v91; // [rsp+D8h] [rbp-28h]
  int v92; // [rsp+DCh] [rbp-24h]
  char v93; // [rsp+E0h] [rbp-20h] BYREF

  v82 = a5;
  P = &v93;
  v5 = a4;
  v83 = 0;
  v79 = a4;
  v78 = this;
  v92 = 32;
  v87 = 0;
  v89 = 0;
  v91 = 0;
  *(_OWORD *)v75 = 0;
  v80 = 0;
  epi16 = _mm_extract_epi16((__m128i)0LL, 2);
  v85 = 0;
  v88 = HIDWORD(a5);
  v86 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( a4 )
  {
    *(_OWORD *)*((_QWORD *)a4 + 1) = *(_OWORD *)a3;
    *(_OWORD *)*((_QWORD *)a4 + 3) = *(_OWORD *)a3;
    v17 = *(_OWORD *)a4;
    *(_OWORD *)Src = *((_OWORD *)a4 + 1);
    v80 = v17;
  }
  else
  {
    *((_QWORD *)&v80 + 1) = a3;
    WORD2(v80) = 0;
    LODWORD(v80) = 16;
    Src[1] = a3;
    LODWORD(Src[0]) = 16;
  }
  v9 = 5;
  v10 = *((unsigned __int8 *)a2 + 96);
  v11 = 5;
  if ( (*(_DWORD *)a2 & 0x8000LL) == 0 )
    v11 = 2;
  if ( v10 < v11 )
  {
    v12 = (unsigned __int8)(v10 + 1);
    *((_BYTE *)a2 + 96) = v12;
    v13 = 5 * v12;
    if ( (unsigned __int8)v12 <= 2u )
      v14 = (char *)a2 - 24;
    else
      v14 = (char *)a2 + 784;
    v15 = &v14[8 * v13];
    *((_QWORD *)v15 + 1) = &CmsCountMap::PropertyDef;
    *(_QWORD *)v15 = &v80;
    *((_WORD *)v15 + 16) = 0;
    *((_QWORD *)v15 + 2) = &off_140207A10;
  }
  v16 = *((_QWORD *)this + 2);
  if ( !v16 )
  {
    v73 = 0;
    goto LABEL_21;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v18 = *((unsigned __int8 *)a2 + 96);
      v19 = (unsigned __int8)v18 <= 2u
          ? (struct CmsTransactionCore *)((char *)a2 - 24)
          : (struct CmsTransactionCore *)((char *)a2 + 784);
      LODWORD(v75[0]) = *(unsigned __int8 *)(v16 + 27);
      v75[1] = (struct _RTL_AVL_ENTRY *)(v16 + *(unsigned __int8 *)(v16 + 26));
      WORD2(v75[0]) = 0;
      v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _RTL_AVL_ENTRY **))(**((_QWORD **)v19 + 5 * v18 + 2) + 8LL))(
              *((_QWORD *)v19 + 5 * v18 + 2),
              (__int64)v19 + 40 * v18,
              v75);
      if ( v20 )
        break;
      if ( !*(_QWORD *)(v16 + 8) )
      {
        v73 = 2;
LABEL_21:
        --*((_BYTE *)a2 + 96);
        v21 = 0;
        v74 = 0;
        v22 = 0;
        goto LABEL_22;
      }
      v16 = *(_QWORD *)(v16 + 8);
    }
    if ( v20 != 1 )
      break;
    if ( !*(_QWORD *)(v16 + 16) )
    {
      v73 = 3;
      goto LABEL_21;
    }
    v16 = *(_QWORD *)(v16 + 16);
  }
  --*((_BYTE *)a2 + 96);
  v74 = v16;
  if ( !v16 )
  {
    v22 = 0;
    v73 = 1;
    v74 = 0;
    v21 = 0;
    goto LABEL_22;
  }
  v22 = (struct _RTL_AVL_ENTRY *)v16;
  v83 = *(unsigned __int8 *)(v16 + 27);
  v86 = v16 + *(unsigned __int8 *)(v16 + 26);
  epi16 = 0;
  v87 = *(unsigned __int16 *)(v16 + 30);
  v65 = *(_QWORD *)a3;
  v66 = (_QWORD *)(v16 + *(unsigned __int8 *)(v16 + 26));
  v89 = v66;
  if ( *v66 != v65 || v66[1] != *((_QWORD *)a3 + 1) )
  {
    if ( v66 )
    {
      *(_OWORD *)v75 = 0;
      v76 = 0;
      v60 = CmsAvlTableLite::AddToIndexEx(
              this,
              a2,
              (const struct SmsInternalPropertyDef *)&CmsCountMap::PropertyDef,
              (unsigned __int64)&v80,
              (struct _SmsQuickIndex *)v75,
              (struct _RTL_AVL_ENTRY **)v5);
      v22 = v75[0];
      v24 = v60;
LABEL_45:
      if ( v24 >= 0 )
      {
        if ( v82 )
          *v82 = v22;
        if ( v5 )
          *((_QWORD *)v5 + 4) = 0;
      }
      if ( (v91 & 1) != 0 )
      {
        if ( P )
          ExFreePoolWithTag(P, 0);
      }
      return (unsigned int)v24;
    }
    v73 = 1;
    v21 = v16;
LABEL_22:
    v23 = 0;
    v75[0] = 0;
    if ( v5 )
    {
      v22 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v5 + 4);
      v24 = 0;
      v25 = 0;
      v26 = v5;
      goto LABEL_24;
    }
    v77 = (int)Src[0];
    v72 = v80;
    v41 = ((LODWORD(Src[0]) + 7) & 0xFFFFFFF8) + 32;
    v42 = v41;
    if ( v41 > CmsAvlTableLite::SizeOfAllocationsOnLookaside2 )
    {
      Pool2 = ExAllocatePool2(66, ((LODWORD(Src[0]) + 7) & 0xFFFFFFF8) + 32, 1766871885, v21);
      if ( Pool2 )
      {
        v53 = 0x8000;
LABEL_77:
        *(_WORD *)(Pool2 + 28) = 0;
        v22 = (struct _RTL_AVL_ENTRY *)Pool2;
        memmove((void *)(Pool2 + 32), Src[1], LODWORD(Src[0]));
        v54 = v77;
        v26 = (struct _SmsPreAllocatedRow *)&v80;
        v21 = v74;
        v25 = 1;
        *(_BYTE *)(Pool2 + 26) = 32;
        *(_WORD *)(Pool2 + 28) |= v53;
        v5 = v79;
        *(_WORD *)(Pool2 + 30) = v54;
        *(_BYTE *)(Pool2 + 27) = v72;
        v24 = 0;
LABEL_24:
        v27 = *((unsigned __int8 *)a2 + 96);
        if ( (*(_DWORD *)a2 & 0x8000LL) == 0 )
          v9 = 2;
        v71 = v25;
        if ( v27 < v9 )
        {
          v28 = v27 + 1;
          *((_BYTE *)a2 + 96) = v28;
          if ( v28 <= 2u )
            v29 = (char *)a2 - 24;
          else
            v29 = (char *)a2 + 784;
          v30 = &v29[40 * v28];
          *(_QWORD *)v30 = v26;
          *((_WORD *)v30 + 16) = 0;
          *((_QWORD *)v30 + 1) = &CmsCountMap::PropertyDef;
          *((_QWORD *)v30 + 2) = &off_140207A10;
          LOBYTE(v27) = *((_BYTE *)a2 + 96);
        }
        if ( v25 )
        {
          if ( (unsigned __int8)v27 <= 2u )
            v31 = (char *)a2 + 9;
          else
            v31 = (char *)a2 + 817;
          v31[40 * (unsigned __int8)v27] = 1;
        }
        v32 = *((unsigned __int8 *)a2 + 96);
        v33 = (struct _RTL_AVL_ENTRY **)((char *)a2 + 40 * v32);
        if ( (unsigned __int8)v32 > 2u )
          v33 += 101;
        v34 = v78;
        *v33 = v22;
        if ( v16 )
        {
          if ( !v21 )
          {
            v23 = (struct _RTL_AVL_ENTRY *)v16;
            v37 = v73;
            goto LABEL_51;
          }
          NodeOrParentIn = FindNodeOrParentInSubtree<MST_AVL_DEFAULT_PROTOTYPE>(
                             (_DWORD)v34,
                             (_DWORD)a2,
                             (_DWORD)v26,
                             v21,
                             (__int64)v75);
          v23 = v75[0];
          v36 = v75[0];
          v37 = NodeOrParentIn;
          if ( NodeOrParentIn != 1 )
            v36 = 0;
        }
        else
        {
          v56 = *((_QWORD *)v34 + 2);
          if ( v56 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                v57 = *((unsigned __int8 *)a2 + 96);
                v23 = (struct _RTL_AVL_ENTRY *)v56;
                v58 = (unsigned __int8)v57 <= 2u
                    ? (struct CmsTransactionCore *)((char *)a2 - 24)
                    : (struct CmsTransactionCore *)((char *)a2 + 784);
                LODWORD(v75[0]) = *(unsigned __int8 *)(v56 + 27);
                v75[1] = (struct _RTL_AVL_ENTRY *)(v56 + *(unsigned __int8 *)(v56 + 26));
                WORD2(v75[0]) = 0;
                v59 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _RTL_AVL_ENTRY **))(**((_QWORD **)v58
                                                                                              + 5 * v57
                                                                                              + 2)
                                                                                           + 8LL))(
                        *((_QWORD *)v58 + 5 * v57 + 2),
                        (__int64)v58 + 40 * v57,
                        v75);
                if ( v59 )
                  break;
                v56 = *((_QWORD *)v23 + 1);
                if ( !v56 )
                {
                  v37 = 2;
                  goto LABEL_41;
                }
              }
              if ( v59 != 1 )
                break;
              v56 = *((_QWORD *)v23 + 2);
              if ( !v56 )
              {
                v37 = 3;
                goto LABEL_41;
              }
            }
            v37 = 1;
            v36 = v23;
          }
          else
          {
            v37 = 0;
LABEL_41:
            v36 = 0;
          }
        }
        if ( v36 )
        {
          --*((_BYTE *)a2 + 96);
          v38 = v22;
          v22 = v36;
          if ( v38 && v71 )
            CmsAvlTableLite::FreeIndexEntry(v38);
          v24 = -1073741771;
          goto LABEL_45;
        }
LABEL_51:
        ++*((_DWORD *)v34 + 10);
        if ( v37 != 1 )
        {
          v40 = (struct _RTL_AVL_ENTRY *)((__int64 (__fastcall *)(CmsCountMap *, _QWORD, struct CmsTransactionCore *))qword_1402692F0)(
                                           v34,
                                           0,
                                           a2);
          if ( v40 )
          {
            *(_OWORD *)v40 = 0;
            *(_OWORD *)((char *)v40 + 10) = 0;
            ++*((_DWORD *)v34 + 8);
            if ( v37 )
            {
              if ( v37 == 2 )
                *((_QWORD *)v23 + 1) = v40;
              else
                *((_QWORD *)v23 + 2) = v40;
              *(_QWORD *)v40 = v23;
              *((_BYTE *)v34 + 24) = -1;
              for ( i = *(_QWORD *)v40; ; v23 = (struct _RTL_AVL_ENTRY *)i )
              {
                v68 = *(_QWORD *)(i + 8) == (_QWORD)v40;
                v69 = -1;
                v70 = *((_BYTE *)v23 + 24);
                if ( !v68 )
                  v69 = 1;
                if ( v70 )
                  break;
                i = *(_QWORD *)v23;
                v40 = v23;
                *((_BYTE *)v23 + 24) = v69;
              }
              v5 = v79;
              if ( v70 == v69 )
                RebalanceNode(v23);
              else
                *((_BYTE *)v23 + 24) = 0;
            }
            else
            {
              *((_QWORD *)v34 + 2) = v40;
              *(_QWORD *)v40 = v34;
            }
          }
        }
        --*((_BYTE *)a2 + 96);
        goto LABEL_45;
      }
      goto LABEL_126;
    }
    if ( v41 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside1 )
    {
      v44 = (unsigned int *)(qword_140269458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v42 > *v44 )
      {
        v44 = 0;
        v45 = v42 + 16;
        goto LABEL_62;
      }
      if ( !*((_BYTE *)v44 + 8) )
      {
        if ( (int)*((_QWORD *)v44 + 11) > (int)HIDWORD(*((_QWORD *)v44 + 11)) )
        {
          v52 = _InterlockedDecrement((volatile signed __int32 *)v44 + 22);
          if ( v52 >= (int)v44[23] && v52 >= 0 )
          {
            v62 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v44 + 4);
            goto LABEL_97;
          }
          _InterlockedIncrement((volatile signed __int32 *)v44 + 22);
        }
LABEL_74:
        v45 = v44[1];
LABEL_62:
        v46 = ExAllocatePool2(66, v45, 1766871885, v43);
        Pool2 = v46;
        if ( (v46 & 0xF) == 0 )
        {
          if ( !v46 )
          {
LABEL_99:
            v53 = 0x2000;
LABEL_100:
            if ( Pool2 )
            {
              v9 = 5;
              goto LABEL_77;
            }
            v5 = v79;
LABEL_126:
            v24 = -1073741670;
            goto LABEL_45;
          }
LABEL_98:
          *(_QWORD *)Pool2 = v44;
          Pool2 += 16;
          goto LABEL_99;
        }
LABEL_134:
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      }
      v61 = (struct _NPAGED_LOOKASIDE_LIST *)(v44 + 16);
      if ( *((_BYTE *)v44 + 9) )
        v62 = ExAllocateFromNPagedLookasideList(v61);
      else
        v62 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v61);
LABEL_97:
      Pool2 = (__int64)v62;
      if ( v62 )
        goto LABEL_98;
      goto LABEL_74;
    }
    KeGetCurrentProcessorNumberEx(0);
    v49 = qword_140269460;
    if ( v42 > *(unsigned int *)qword_140269460 )
    {
      v49 = 0;
      v50 = v42 + 16;
      goto LABEL_67;
    }
    if ( !*(_BYTE *)(qword_140269460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140269460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140269460 + 88)) )
      {
        v55 = _InterlockedDecrement((volatile signed __int32 *)(qword_140269460 + 88));
        if ( v55 >= *(_DWORD *)(v49 + 92) && v55 >= 0 )
        {
          v64 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v49 + 64));
          goto LABEL_102;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v49 + 88));
      }
LABEL_83:
      v50 = *(unsigned int *)(v49 + 4);
LABEL_67:
      v51 = ExAllocatePool2(66, v50, 1766871885, v48);
      Pool2 = v51;
      if ( (v51 & 0xF) != 0 )
        goto LABEL_134;
      if ( !v51 )
      {
LABEL_104:
        v53 = 0x4000;
        goto LABEL_100;
      }
LABEL_103:
      *(_QWORD *)Pool2 = v49;
      Pool2 += 16;
      goto LABEL_104;
    }
    v63 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140269460 + 64);
    if ( *(_BYTE *)(qword_140269460 + 9) )
      v64 = ExAllocateFromNPagedLookasideList(v63);
    else
      v64 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v63);
LABEL_102:
    Pool2 = (__int64)v64;
    if ( v64 )
      goto LABEL_103;
    goto LABEL_83;
  }
  if ( v82 )
    *v82 = (struct _RTL_AVL_ENTRY *)v16;
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v83);
  return 0;
}

```

## disassembly

```asm
0x14007a200  mov     [rsp-8+arg_10], rbx
0x14007a205  push    rbp
0x14007a206  push    rsi
0x14007a207  push    rdi
0x14007a208  push    r12
0x14007a20a  push    r13
0x14007a20c  push    r14
0x14007a20e  push    r15
0x14007a210  lea     rbp, [rsp-10h]
0x14007a215  sub     rsp, 110h
0x14007a21c  mov     rax, cs:__security_cookie
0x14007a223  xor     rax, rsp
0x14007a226  mov     [rbp+40h+var_40], rax
0x14007a22a  mov     rax, [rbp+40h+arg_20]
0x14007a22e  xorps   xmm0, xmm0
0x14007a231  mov     [rbp+40h+var_A8], rax
0x14007a235  lea     rax, [rbp+40h+var_60]
0x14007a239  mov     [rbp+40h+P], rax
0x14007a23d  mov     r12, r9
0x14007a240  movss   [rbp+40h+var_90], xmm0
0x14007a245  mov     rdi, r8
0x14007a248  mov     [rsp+140h+var_D0], r9
0x14007a24d  mov     rbx, rdx
0x14007a250  mov     [rsp+140h+var_D8], rcx
0x14007a255  mov     r14, rcx
0x14007a258  mov     [rbp+40h+var_64], 20h ; ' '
0x14007a25f  mov     [rbp+40h+var_80], 0
0x14007a266  mov     [rbp+40h+var_78], 0
0x14007a26e  mov     [rbp+40h+var_68], 0
0x14007a272  pextrw  eax, xmm0, 2
0x14007a277  movups  xmmword ptr [rsp+140h+var_100], xmm0
0x14007a27c  movups  [rsp+140h+var_C8], xmm0
0x14007a281  mov     [rbp+40h+var_8C], ax
0x14007a285  movzx   eax, word ptr [rsp+140h+var_100+6]
0x14007a28a  mov     [rbp+40h+var_8A], ax
0x14007a28e  mov     eax, dword ptr [rbp+40h+var_A8+4]
0x14007a291  psrldq  xmm0, 8
0x14007a296  mov     [rbp+40h+var_7C], eax
0x14007a299  movq    [rbp+40h+var_88], xmm0
0x14007a29e  test    r9, r9
0x14007a2a1  jnz     loc_14007A33D
0x14007a2a7  xor     eax, eax
0x14007a2a9  mov     qword ptr [rbp+40h+var_C8+8], r8
0x14007a2ad  mov     word ptr [rsp+140h+var_C8+4], ax
0x14007a2b2  mov     dword ptr [rsp+140h+var_C8], 10h
0x14007a2ba  mov     [rbp+40h+Src+8], r8
0x14007a2be  mov     dword ptr [rbp+40h+Src], 10h
0x14007a2c5  mov     eax, [rdx]
0x14007a2c7  mov     r13d, 5
0x14007a2cd  movzx   ecx, byte ptr [rdx+60h]
0x14007a2d1  bt      rax, 0Fh
0x14007a2d6  mov     eax, r13d
0x14007a2d9  lea     rdx, ?PropertyDef@CmsCountMap@@0USmsInternalPropertyDef@@B; SmsInternalPropertyDef const CmsCountMap::PropertyDef
0x14007a2e0  mov     esi, 2
0x14007a2e5  cmovnb  eax, esi
0x14007a2e8  cmp     ecx, eax
0x14007a2ea  jnb     short loc_14007A329
0x14007a2ec  inc     cl
0x14007a2ee  movzx   ecx, cl
0x14007a2f1  mov     [rbx+60h], cl
0x14007a2f4  lea     rax, [rcx+rcx*4]
0x14007a2f8  cmp     cl, sil
0x14007a2fb  jbe     loc_14007A924
0x14007a301  lea     rcx, [rbx+310h]
0x14007a308  lea     rcx, [rcx+rax*8]
0x14007a30c  lea     rax, [rsp+140h+var_C8]
0x14007a311  mov     [rcx+8], rdx
0x14007a315  mov     [rcx], rax
0x14007a318  xor     eax, eax
0x14007a31a  mov     [rcx+20h], ax
0x14007a31e  mov     rax, cs:off_140205258
0x14007a325  mov     [rcx+10h], rax
0x14007a329  mov     r15, [r14+10h]
0x14007a32d  test    r15, r15
0x14007a330  jnz     short loc_14007A370
0x14007a332  xor     ecx, ecx
0x14007a334  mov     [rsp+140h+var_10C], ecx
0x14007a338  jmp     loc_14007A3F3
0x14007a33d  mov     rax, [r9+8]
0x14007a341  movups  xmm0, xmmword ptr [r8]
0x14007a345  movups  xmmword ptr [rax], xmm0
0x14007a348  mov     rax, [r9+18h]
0x14007a34c  movups  xmm0, xmmword ptr [r8]
0x14007a350  movups  xmmword ptr [rax], xmm0
0x14007a353  movups  xmm0, xmmword ptr [r9+10h]
0x14007a358  movups  xmm1, xmmword ptr [r9]
0x14007a35c  movups  xmmword ptr [rbp+40h+Src], xmm0
0x14007a360  movss   dword ptr [rbp+40h+Src], xmm0
0x14007a365  movups  [rsp+140h+var_C8], xmm1
0x14007a36a  jmp     loc_14007A2C5
0x14007a370  movzx   ecx, byte ptr [rbx+60h]
0x14007a374  lea     rax, [rcx+rcx*4]
0x14007a378  cmp     cl, sil
0x14007a37b  jbe     loc_14007A92D
0x14007a381  lea     rdx, [rbx+310h]
0x14007a388  lea     rdx, [rdx+rax*8]
0x14007a38c  movzx   eax, byte ptr [r15+1Bh]
0x14007a391  mov     dword ptr [rsp+140h+var_100], eax
0x14007a395  lea     r8, [rsp+140h+var_100]
0x14007a39a  movzx   eax, byte ptr [r15+1Ah]
0x14007a39f  add     rax, r15
0x14007a3a2  mov     [rsp+140h+var_100+8], rax
0x14007a3a7  xor     eax, eax
0x14007a3a9  mov     word ptr [rsp+140h+var_100+4], ax
0x14007a3ae  mov     rcx, [rdx+10h]
0x14007a3b2  mov     rax, [rcx]
0x14007a3b5  mov     rax, [rax+8]
0x14007a3b9  call    _guard_dispatch_icall
0x14007a3be  test    eax, eax
0x14007a3c0  jnz     short loc_14007A3D4
0x14007a3c2  mov     rax, [r15+8]
0x14007a3c6  test    rax, rax
0x14007a3c9  jz      loc_14007A785
0x14007a3cf  mov     r15, rax
0x14007a3d2  jmp     short loc_14007A370
0x14007a3d4  cmp     eax, 1
0x14007a3d7  jnz     loc_14007A7D2
0x14007a3dd  mov     rax, [r15+10h]
0x14007a3e1  test    rax, rax
0x14007a3e4  jz      short loc_14007A3EB
0x14007a3e6  mov     r15, rax
0x14007a3e9  jmp     short loc_14007A370
0x14007a3eb  mov     [rsp+140h+var_10C], 3
0x14007a3f3  dec     byte ptr [rbx+60h]
0x14007a3f6  xor     r9d, r9d
0x14007a3f9  mov     [rsp+140h+var_108], r9
0x14007a3fe  xor     esi, esi
0x14007a400  xor     edi, edi
0x14007a402  mov     [rsp+140h+var_100], rdi
0x14007a407  test    r12, r12
0x14007a40a  jz      loc_14007A5CC
0x14007a410  mov     rsi, [r12+20h]
0x14007a415  xor     r14d, r14d
0x14007a418  xor     r10b, r10b
0x14007a41b  mov     r8, r12
0x14007a41e  mov     eax, [rbx]
0x14007a420  bt      rax, 0Fh
0x14007a425  movzx   edx, byte ptr [rbx+60h]
0x14007a429  mov     eax, 2
0x14007a42e  cmovnb  r13d, eax
0x14007a432  mov     [rsp+140h+var_110], r10b
0x14007a437  cmp     edx, r13d
0x14007a43a  jnb     short loc_14007A47F
0x14007a43c  inc     dl
0x14007a43e  movzx   ecx, dl
0x14007a441  mov     [rbx+60h], cl
0x14007a444  lea     rax, [rcx+rcx*4]
0x14007a448  cmp     cl, 2
0x14007a44b  jbe     loc_14007A9BE
0x14007a451  lea     rcx, [rbx+310h]
0x14007a458  lea     rcx, [rcx+rax*8]
0x14007a45c  xor     eax, eax
0x14007a45e  mov     [rcx], r8
0x14007a461  mov     [rcx+20h], ax
0x14007a465  lea     rax, ?PropertyDef@CmsCountMap@@0USmsInternalPropertyDef@@B; SmsInternalPropertyDef const CmsCountMap::PropertyDef
0x14007a46c  mov     [rcx+8], rax
0x14007a470  mov     rax, cs:off_140205258
0x14007a477  mov     [rcx+10h], rax
0x14007a47b  movzx   edx, byte ptr [rbx+60h]
0x14007a47f  test    r10b, r10b
0x14007a482  jz      short loc_14007A4A2
0x14007a484  movzx   eax, dl
0x14007a487  lea     rcx, [rax+rax*4]
0x14007a48b  cmp     dl, 2
0x14007a48e  jbe     loc_14007A9C7
0x14007a494  lea     rax, [rbx+331h]
0x14007a49b  lea     rax, [rax+rcx*8]
0x14007a49f  mov     byte ptr [rax], 1
0x14007a4a2  movzx   ecx, byte ptr [rbx+60h]
0x14007a4a6  lea     rax, [rcx+rcx*4]
0x14007a4aa  lea     rdx, [rbx+rax*8]
0x14007a4ae  cmp     cl, 2
0x14007a4b1  jbe     short loc_14007A4BA
0x14007a4b3  add     rdx, 328h
0x14007a4ba  mov     r13, [rsp+140h+var_D8]
0x14007a4bf  mov     [rdx], rsi
0x14007a4c2  test    r15, r15
0x14007a4c5  jz      loc_14007A7FE
0x14007a4cb  test    r9, r9
0x14007a4ce  jz      loc_14007A571
0x14007a4d4  lea     rax, [rsp+140h+var_100]
0x14007a4d9  mov     rdx, rbx
0x14007a4dc  mov     rcx, r13
0x14007a4df  mov     [rsp+140h+var_120], rax
0x14007a4e4  call    ??$FindNodeOrParentInSubtree@UMST_AVL_DEFAULT_PROTOTYPE@@@@YA?AW4_TABLE_SEARCH_RESULT@@PEAU_MS_AVL_TABLE@@PEAX1PEAU_RTL_AVL_ENTRY@@PEAPEAU2@@Z; FindNodeOrParentInSubtree<MST_AVL_DEFAULT_PROTOTYPE>(_MS_AVL_TABLE *,void *,void *,_RTL_AVL_ENTRY *,_RTL_AVL_ENTRY * *)
0x14007a4e9  mov     rdi, [rsp+140h+var_100]
0x14007a4ee  xor     ecx, ecx
0x14007a4f0  cmp     eax, 1
0x14007a4f3  mov     rdx, rdi
0x14007a4f6  mov     r15d, eax
0x14007a4f9  cmovnz  rdx, rcx
0x14007a4fd  jmp     short loc_14007A507
0x14007a4ff  mov     r15d, 3
0x14007a505  xor     edx, edx
0x14007a507  test    rdx, rdx
0x14007a50a  jz      short loc_14007A579
0x14007a50c  dec     byte ptr [rbx+60h]
0x14007a50f  mov     rcx, rsi; struct _RTL_AVL_ENTRY *
0x14007a512  mov     rsi, rdx
0x14007a515  test    rcx, rcx
0x14007a518  jnz     loc_14007AA02
0x14007a51e  mov     r14d, 0C0000035h
0x14007a524  test    r14d, r14d
0x14007a527  jns     short loc_14007A5A8
0x14007a529  test    [rbp+40h+var_68], 1
0x14007a52d  jz      short loc_14007A546
0x14007a52f  mov     rcx, [rbp+40h+P]; P
0x14007a533  test    rcx, rcx
0x14007a536  jz      short loc_14007A546
0x14007a538  xor     edx, edx; Tag
0x14007a53a  call    cs:__imp_ExFreePoolWithTag
0x14007a541  nop     dword ptr [rax+rax+00h]
0x14007a546  mov     eax, r14d
0x14007a549  mov     rcx, [rbp+40h+var_40]
0x14007a54d  xor     rcx, rsp; StackCookie
0x14007a550  call    __security_check_cookie
0x14007a555  mov     rbx, [rsp+140h+arg_10]
0x14007a55d  add     rsp, 110h
0x14007a564  pop     r15
0x14007a566  pop     r14
0x14007a568  pop     r13
0x14007a56a  pop     r12
0x14007a56c  pop     rdi
0x14007a56d  pop     rsi
0x14007a56e  pop     rbp
0x14007a56f  retn
0x14007a571  mov     rdi, r15
0x14007a574  mov     r15d, [rsp+140h+var_10C]
0x14007a579  inc     dword ptr [r13+28h]
0x14007a57d  cmp     r15d, 1
0x14007a581  jz      short loc_14007A5A0
0x14007a583  mov     rax, cs:qword_1402692F0
0x14007a58a  mov     r8, rbx
0x14007a58d  xor     edx, edx
0x14007a58f  mov     rcx, r13
0x14007a592  call    _guard_dispatch_icall
0x14007a597  test    rax, rax
0x14007a59a  jnz     loc_14007A9D9
0x14007a5a0  dec     byte ptr [rbx+60h]
0x14007a5a3  jmp     loc_14007A524
0x14007a5a8  mov     rax, [rbp+40h+var_A8]
0x14007a5ac  test    rax, rax
0x14007a5af  jnz     loc_14007A665
0x14007a5b5  test    r12, r12
0x14007a5b8  jz      loc_14007A529
0x14007a5be  mov     qword ptr [r12+20h], 0
0x14007a5c7  jmp     loc_14007A529
0x14007a5cc  mov     eax, dword ptr [rbp+40h+Src]
0x14007a5cf  movzx   ecx, byte ptr [rsp+140h+var_C8]
0x14007a5d4  mov     [rsp+140h+var_E0], eax
0x14007a5d8  add     eax, 7
0x14007a5db  and     eax, 0FFFFFFF8h
0x14007a5de  mov     [rsp+140h+var_110], cl
0x14007a5e2  add     eax, 20h ; ' '
0x14007a5e5  cmp     eax, cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x14007a5eb  mov     r14d, eax
0x14007a5ee  ja      loc_14007A708
0x14007a5f4  xor     ecx, ecx; ProcNumber
0x14007a5f6  cmp     eax, cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x14007a5fc  ja      short loc_14007A66D
0x14007a5fe  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007a605  nop     dword ptr [rax+rax+00h]
0x14007a60a  xor     edx, edx
0x14007a60c  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14007a612  lea     r13, [rdx+rdx*2]
0x14007a616  shl     r13, 6
0x14007a61a  add     r13, cs:qword_140269458
0x14007a621  mov     eax, [r13+0]
0x14007a625  cmp     r14, rax
0x14007a628  jbe     loc_14007A6C4
0x14007a62e  xor     r13d, r13d
0x14007a631  lea     rdx, [r14+10h]
0x14007a635  mov     ecx, 42h ; 'B'
0x14007a63a  mov     r8d, 6950534Dh
0x14007a640  call    cs:__imp_ExAllocatePool2
0x14007a647  nop     dword ptr [rax+rax+00h]
0x14007a64c  mov     r14, rax
0x14007a64f  test    al, 0Fh
0x14007a651  jnz     loc_1401FF73D
0x14007a657  test    rax, rax
0x14007a65a  jz      loc_14007A8AA
0x14007a660  jmp     loc_14007A8A3
0x14007a665  mov     [rax], rsi
0x14007a668  jmp     loc_14007A5B5
0x14007a66d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007a674  nop     dword ptr [rax+rax+00h]
0x14007a679  mov     r13, cs:qword_140269460
0x14007a680  mov     eax, [r13+0]
0x14007a684  cmp     r14, rax
0x14007a687  jbe     loc_14007A78E
0x14007a68d  xor     r13d, r13d
0x14007a690  lea     rdx, [r14+10h]
0x14007a694  mov     ecx, 42h ; 'B'
0x14007a699  mov     r8d, 6950534Dh
0x14007a69f  call    cs:__imp_ExAllocatePool2
0x14007a6a6  nop     dword ptr [rax+rax+00h]
0x14007a6ab  mov     r14, rax
0x14007a6ae  test    al, 0Fh
0x14007a6b0  jnz     loc_1401FF73D
0x14007a6b6  test    rax, rax
  ... truncated ...
```
