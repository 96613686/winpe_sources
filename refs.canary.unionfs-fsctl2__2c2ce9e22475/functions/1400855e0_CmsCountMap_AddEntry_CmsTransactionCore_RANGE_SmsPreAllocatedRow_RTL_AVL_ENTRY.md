# CmsCountMap::AddEntry(CmsTransactionCore *,_RANGE *,_SmsPreAllocatedRow *,_RTL_AVL_ENTRY * *)

- ea: `0x1400855e0`
- end: `0x140085e07`
- name: `?AddEntry@CmsCountMap@@QEAAJPEAVCmsTransactionCore@@PEAU_RANGE@@PEAU_SmsPreAllocatedRow@@PEAPEAU_RTL_AVL_ENTRY@@@Z`
- size: `2087`
- prototype: `__int64 __usercall@<rax>(CmsCountMap *__hidden this@<rcx>, struct CmsTransactionCore *@<rdx>, struct _RANGE *@<r8>, struct _SmsPreAllocatedRow *@<r9>, struct _RTL_AVL_ENTRY **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400c67ac`

## callees

- `0x14002b110`
- `0x140075200`
- `0x140075eb0`
- `0x1400855e0`
- `0x140085e10`
- `0x140085f10`
- `0x1400c8574`
- `0x1401e9ce0`
- `0x1401e9dc0`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140085d34`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140085d70`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140085d34`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140085d70`
- `ntoskrnl!ExAllocatePool2` at `0x140085a20`
- `ntoskrnl!ExAllocatePool2` at `0x140085a7f`
- `ntoskrnl!ExAllocatePool2` at `0x140085af6`
- `ntoskrnl!ExAllocatePool2` at `0x140085a20`
- `ntoskrnl!ExAllocatePool2` at `0x140085a7f`
- `ntoskrnl!ExAllocatePool2` at `0x140085af6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400859de`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140085a4d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400859de`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140085a4d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f8151`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f8163`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f8151`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f8163`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140085d51`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140085d8d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140085d51`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140085d8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008591a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008591a`

## string_xrefs

- `0x1401f8175`: `Lookaside list allocation must be double quad aligned.`

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
  unsigned int *v43; // r13
  unsigned __int64 v44; // rdx
  __int64 v45; // rax
  __int64 Pool2; // r14
  __int64 v47; // r13
  unsigned __int64 v48; // rdx
  __int64 v49; // rax
  int v50; // ecx
  __int16 v51; // r12
  __int16 v52; // ax
  int v53; // ecx
  __int64 v54; // rax
  __int64 v55; // rcx
  struct CmsTransactionCore *v56; // rdx
  int v57; // eax
  int v58; // eax
  struct _NPAGED_LOOKASIDE_LIST *v59; // rcx
  void *v60; // rax
  struct _NPAGED_LOOKASIDE_LIST *v61; // rcx
  void *v62; // rax
  __int64 v63; // rax
  _QWORD *v64; // rcx
  __int64 i; // rdx
  bool v66; // zf
  char v67; // cl
  char v68; // al
  char v69; // [rsp+30h] [rbp-D0h]
  char v70; // [rsp+30h] [rbp-D0h]
  int v71; // [rsp+34h] [rbp-CCh]
  __int64 v72; // [rsp+38h] [rbp-C8h]
  struct _RTL_AVL_ENTRY *v73[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v74; // [rsp+50h] [rbp-B0h]
  int v75; // [rsp+60h] [rbp-A0h]
  CmsCountMap *v76; // [rsp+68h] [rbp-98h]
  struct _SmsPreAllocatedRow *v77; // [rsp+70h] [rbp-90h]
  __int128 v78; // [rsp+78h] [rbp-88h] BYREF
  void *Src[2]; // [rsp+88h] [rbp-78h]
  struct _RTL_AVL_ENTRY **v80; // [rsp+98h] [rbp-68h]
  int v81; // [rsp+B0h] [rbp-50h] BYREF
  __int16 epi16; // [rsp+B4h] [rbp-4Ch]
  __int16 v83; // [rsp+B6h] [rbp-4Ah]
  unsigned __int64 v84; // [rsp+B8h] [rbp-48h]
  int v85; // [rsp+C0h] [rbp-40h]
  int v86; // [rsp+C4h] [rbp-3Ch]
  _QWORD *v87; // [rsp+C8h] [rbp-38h]
  PVOID P; // [rsp+D0h] [rbp-30h]
  char v89; // [rsp+D8h] [rbp-28h]
  int v90; // [rsp+DCh] [rbp-24h]
  char v91; // [rsp+E0h] [rbp-20h] BYREF

  v80 = a5;
  P = &v91;
  v5 = a4;
  v81 = 0;
  v77 = a4;
  v76 = this;
  v90 = 32;
  v85 = 0;
  v87 = 0;
  v89 = 0;
  *(_OWORD *)v73 = 0;
  v78 = 0;
  epi16 = _mm_extract_epi16((__m128i)0LL, 2);
  v83 = 0;
  v86 = HIDWORD(a5);
  v84 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( a4 )
  {
    *(_OWORD *)*((_QWORD *)a4 + 1) = *(_OWORD *)a3;
    *(_OWORD *)*((_QWORD *)a4 + 3) = *(_OWORD *)a3;
    v17 = *(_OWORD *)a4;
    *(_OWORD *)Src = *((_OWORD *)a4 + 1);
    v78 = v17;
  }
  else
  {
    *((_QWORD *)&v78 + 1) = a3;
    WORD2(v78) = 0;
    LODWORD(v78) = 16;
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
    *(_QWORD *)v15 = &v78;
    *((_WORD *)v15 + 16) = 0;
    *((_QWORD *)v15 + 2) = &off_140200A80;
  }
  v16 = *((_QWORD *)this + 2);
  if ( !v16 )
  {
    v71 = 0;
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
      LODWORD(v73[0]) = *(unsigned __int8 *)(v16 + 27);
      v73[1] = (struct _RTL_AVL_ENTRY *)(v16 + *(unsigned __int8 *)(v16 + 26));
      WORD2(v73[0]) = 0;
      v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _RTL_AVL_ENTRY **))(**((_QWORD **)v19 + 5 * v18 + 2) + 8LL))(
              *((_QWORD *)v19 + 5 * v18 + 2),
              (__int64)v19 + 40 * v18,
              v73);
      if ( v20 )
        break;
      if ( !*(_QWORD *)(v16 + 8) )
      {
        v71 = 2;
LABEL_21:
        --*((_BYTE *)a2 + 96);
        v21 = 0;
        v72 = 0;
        v22 = 0;
        goto LABEL_22;
      }
      v16 = *(_QWORD *)(v16 + 8);
    }
    if ( v20 != 1 )
      break;
    if ( !*(_QWORD *)(v16 + 16) )
    {
      v71 = 3;
      goto LABEL_21;
    }
    v16 = *(_QWORD *)(v16 + 16);
  }
  --*((_BYTE *)a2 + 96);
  v72 = v16;
  if ( !v16 )
  {
    v22 = 0;
    v71 = 1;
    v72 = 0;
    v21 = 0;
    goto LABEL_22;
  }
  v22 = (struct _RTL_AVL_ENTRY *)v16;
  v81 = *(unsigned __int8 *)(v16 + 27);
  v84 = v16 + *(unsigned __int8 *)(v16 + 26);
  epi16 = 0;
  v85 = *(unsigned __int16 *)(v16 + 30);
  v63 = *(_QWORD *)a3;
  v64 = (_QWORD *)(v16 + *(unsigned __int8 *)(v16 + 26));
  v87 = v64;
  if ( *v64 != v63 || v64[1] != *((_QWORD *)a3 + 1) )
  {
    if ( v64 )
    {
      *(_OWORD *)v73 = 0;
      v74 = 0;
      v58 = CmsAvlTableLite::AddToIndexEx(
              this,
              a2,
              (const struct SmsInternalPropertyDef *)&CmsCountMap::PropertyDef,
              (unsigned __int64)&v78,
              (struct _SmsQuickIndex *)v73,
              (struct _RTL_AVL_ENTRY **)v5);
      v22 = v73[0];
      v24 = v58;
LABEL_45:
      if ( v24 >= 0 )
      {
        if ( v80 )
          *v80 = v22;
        if ( v5 )
          *((_QWORD *)v5 + 4) = 0;
      }
      if ( (v89 & 1) != 0 )
      {
        if ( P )
          ExFreePoolWithTag(P, 0);
      }
      return (unsigned int)v24;
    }
    v71 = 1;
    v21 = v16;
LABEL_22:
    v23 = 0;
    v73[0] = 0;
    if ( v5 )
    {
      v22 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v5 + 4);
      v24 = 0;
      v25 = 0;
      v26 = v5;
      goto LABEL_24;
    }
    v75 = (int)Src[0];
    v70 = v78;
    v41 = ((LODWORD(Src[0]) + 7) & 0xFFFFFFF8) + 32;
    v42 = v41;
    if ( v41 > CmsAvlTableLite::SizeOfAllocationsOnLookaside2 )
    {
      Pool2 = ExAllocatePool2(66, ((LODWORD(Src[0]) + 7) & 0xFFFFFFF8) + 32, 1766871885);
      if ( Pool2 )
      {
        v51 = 0x8000;
LABEL_77:
        *(_WORD *)(Pool2 + 28) = 0;
        v22 = (struct _RTL_AVL_ENTRY *)Pool2;
        memmove((void *)(Pool2 + 32), Src[1], LODWORD(Src[0]));
        v52 = v75;
        v26 = (struct _SmsPreAllocatedRow *)&v78;
        v21 = v72;
        v25 = 1;
        *(_BYTE *)(Pool2 + 26) = 32;
        *(_WORD *)(Pool2 + 28) |= v51;
        v5 = v77;
        *(_WORD *)(Pool2 + 30) = v52;
        *(_BYTE *)(Pool2 + 27) = v70;
        v24 = 0;
LABEL_24:
        v27 = *((unsigned __int8 *)a2 + 96);
        if ( (*(_DWORD *)a2 & 0x8000LL) == 0 )
          v9 = 2;
        v69 = v25;
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
          *((_QWORD *)v30 + 2) = &off_140200A80;
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
        v34 = v76;
        *v33 = v22;
        if ( v16 )
        {
          if ( !v21 )
          {
            v23 = (struct _RTL_AVL_ENTRY *)v16;
            v37 = v71;
            goto LABEL_51;
          }
          NodeOrParentIn = FindNodeOrParentInSubtree<MST_AVL_DEFAULT_PROTOTYPE>(
                             (_DWORD)v34,
                             (_DWORD)a2,
                             (_DWORD)v26,
                             v21,
                             (__int64)v73);
          v23 = v73[0];
          v36 = v73[0];
          v37 = NodeOrParentIn;
          if ( NodeOrParentIn != 1 )
            v36 = 0;
        }
        else
        {
          v54 = *((_QWORD *)v34 + 2);
          if ( v54 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                v55 = *((unsigned __int8 *)a2 + 96);
                v23 = (struct _RTL_AVL_ENTRY *)v54;
                v56 = (unsigned __int8)v55 <= 2u
                    ? (struct CmsTransactionCore *)((char *)a2 - 24)
                    : (struct CmsTransactionCore *)((char *)a2 + 784);
                LODWORD(v73[0]) = *(unsigned __int8 *)(v54 + 27);
                v73[1] = (struct _RTL_AVL_ENTRY *)(v54 + *(unsigned __int8 *)(v54 + 26));
                WORD2(v73[0]) = 0;
                v57 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _RTL_AVL_ENTRY **))(**((_QWORD **)v56
                                                                                              + 5 * v55
                                                                                              + 2)
                                                                                           + 8LL))(
                        *((_QWORD *)v56 + 5 * v55 + 2),
                        (__int64)v56 + 40 * v55,
                        v73);
                if ( v57 )
                  break;
                v54 = *((_QWORD *)v23 + 1);
                if ( !v54 )
                {
                  v37 = 2;
                  goto LABEL_41;
                }
              }
              if ( v57 != 1 )
                break;
              v54 = *((_QWORD *)v23 + 2);
              if ( !v54 )
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
          if ( v38 && v69 )
            CmsAvlTableLite::FreeIndexEntry(v38);
          v24 = -1073741771;
          goto LABEL_45;
        }
LABEL_51:
        ++*((_DWORD *)v34 + 10);
        if ( v37 != 1 )
        {
          v40 = (struct _RTL_AVL_ENTRY *)((__int64 (__fastcall *)(CmsCountMap *, _QWORD, struct CmsTransactionCore *))qword_140262628)(
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
                v66 = *(_QWORD *)(i + 8) == (_QWORD)v40;
                v67 = -1;
                v68 = *((_BYTE *)v23 + 24);
                if ( !v66 )
                  v67 = 1;
                if ( v68 )
                  break;
                i = *(_QWORD *)v23;
                v40 = v23;
                *((_BYTE *)v23 + 24) = v67;
              }
              v5 = v77;
              if ( v68 == v67 )
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
      v43 = (unsigned int *)(qword_140262458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v42 > *v43 )
      {
        v43 = 0;
        v44 = v42 + 16;
        goto LABEL_62;
      }
      if ( !*((_BYTE *)v43 + 8) )
      {
        if ( (int)*((_QWORD *)v43 + 11) > (int)HIDWORD(*((_QWORD *)v43 + 11)) )
        {
          v50 = _InterlockedDecrement((volatile signed __int32 *)v43 + 22);
          if ( v50 >= (int)v43[23] && v50 >= 0 )
          {
            v60 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v43 + 4);
            goto LABEL_97;
          }
          _InterlockedIncrement((volatile signed __int32 *)v43 + 22);
        }
LABEL_74:
        v44 = v43[1];
LABEL_62:
        v45 = ExAllocatePool2(66, v44, 1766871885);
        Pool2 = v45;
        if ( (v45 & 0xF) == 0 )
        {
          if ( !v45 )
          {
LABEL_99:
            v51 = 0x2000;
LABEL_100:
            if ( Pool2 )
            {
              v9 = 5;
              goto LABEL_77;
            }
            v5 = v77;
LABEL_126:
            v24 = -1073741670;
            goto LABEL_45;
          }
LABEL_98:
          *(_QWORD *)Pool2 = v43;
          Pool2 += 16;
          goto LABEL_99;
        }
LABEL_134:
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      }
      v59 = (struct _NPAGED_LOOKASIDE_LIST *)(v43 + 16);
      if ( *((_BYTE *)v43 + 9) )
        v60 = ExAllocateFromNPagedLookasideList(v59);
      else
        v60 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v59);
LABEL_97:
      Pool2 = (__int64)v60;
      if ( v60 )
        goto LABEL_98;
      goto LABEL_74;
    }
    KeGetCurrentProcessorNumberEx(0);
    v47 = qword_140262460;
    if ( v42 > *(unsigned int *)qword_140262460 )
    {
      v47 = 0;
      v48 = v42 + 16;
      goto LABEL_67;
    }
    if ( !*(_BYTE *)(qword_140262460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140262460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140262460 + 88)) )
      {
        v53 = _InterlockedDecrement((volatile signed __int32 *)(qword_140262460 + 88));
        if ( v53 >= *(_DWORD *)(v47 + 92) && v53 >= 0 )
        {
          v62 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v47 + 64));
          goto LABEL_102;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v47 + 88));
      }
LABEL_83:
      v48 = *(unsigned int *)(v47 + 4);
LABEL_67:
      v49 = ExAllocatePool2(66, v48, 1766871885);
      Pool2 = v49;
      if ( (v49 & 0xF) != 0 )
        goto LABEL_134;
      if ( !v49 )
      {
LABEL_104:
        v51 = 0x4000;
        goto LABEL_100;
      }
LABEL_103:
      *(_QWORD *)Pool2 = v47;
      Pool2 += 16;
      goto LABEL_104;
    }
    v61 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140262460 + 64);
    if ( *(_BYTE *)(qword_140262460 + 9) )
      v62 = ExAllocateFromNPagedLookasideList(v61);
    else
      v62 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v61);
LABEL_102:
    Pool2 = (__int64)v62;
    if ( v62 )
      goto LABEL_103;
    goto LABEL_83;
  }
  if ( v80 )
    *v80 = (struct _RTL_AVL_ENTRY *)v16;
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v81);
  return 0;
}

```

## disassembly

```asm
0x1400855e0  mov     [rsp-8+arg_10], rbx
0x1400855e5  push    rbp
0x1400855e6  push    rsi
0x1400855e7  push    rdi
0x1400855e8  push    r12
0x1400855ea  push    r13
0x1400855ec  push    r14
0x1400855ee  push    r15
0x1400855f0  lea     rbp, [rsp-10h]
0x1400855f5  sub     rsp, 110h
0x1400855fc  mov     rax, cs:__security_cookie
0x140085603  xor     rax, rsp
0x140085606  mov     [rbp+40h+var_40], rax
0x14008560a  mov     rax, [rbp+40h+arg_20]
0x14008560e  xorps   xmm0, xmm0
0x140085611  mov     [rbp+40h+var_A8], rax
0x140085615  lea     rax, [rbp+40h+var_60]
0x140085619  mov     [rbp+40h+P], rax
0x14008561d  mov     r12, r9
0x140085620  movss   [rbp+40h+var_90], xmm0
0x140085625  mov     rdi, r8
0x140085628  mov     [rsp+140h+var_D0], r9
0x14008562d  mov     rbx, rdx
0x140085630  mov     [rsp+140h+var_D8], rcx
0x140085635  mov     r14, rcx
0x140085638  mov     [rbp+40h+var_64], 20h ; ' '
0x14008563f  mov     [rbp+40h+var_80], 0
0x140085646  mov     [rbp+40h+var_78], 0
0x14008564e  mov     [rbp+40h+var_68], 0
0x140085652  pextrw  eax, xmm0, 2
0x140085657  movups  xmmword ptr [rsp+140h+var_100], xmm0
0x14008565c  movups  [rsp+140h+var_C8], xmm0
0x140085661  mov     [rbp+40h+var_8C], ax
0x140085665  movzx   eax, word ptr [rsp+140h+var_100+6]
0x14008566a  mov     [rbp+40h+var_8A], ax
0x14008566e  mov     eax, dword ptr [rbp+40h+var_A8+4]
0x140085671  psrldq  xmm0, 8
0x140085676  mov     [rbp+40h+var_7C], eax
0x140085679  movq    [rbp+40h+var_88], xmm0
0x14008567e  test    r9, r9
0x140085681  jnz     loc_14008571D
0x140085687  xor     eax, eax
0x140085689  mov     qword ptr [rbp+40h+var_C8+8], r8
0x14008568d  mov     word ptr [rsp+140h+var_C8+4], ax
0x140085692  mov     dword ptr [rsp+140h+var_C8], 10h
0x14008569a  mov     [rbp+40h+Src+8], r8
0x14008569e  mov     dword ptr [rbp+40h+Src], 10h
0x1400856a5  mov     eax, [rdx]
0x1400856a7  mov     r13d, 5
0x1400856ad  movzx   ecx, byte ptr [rdx+60h]
0x1400856b1  bt      rax, 0Fh
0x1400856b6  mov     eax, r13d
0x1400856b9  lea     rdx, ?PropertyDef@CmsCountMap@@0USmsInternalPropertyDef@@B; SmsInternalPropertyDef const CmsCountMap::PropertyDef
0x1400856c0  mov     esi, 2
0x1400856c5  cmovnb  eax, esi
0x1400856c8  cmp     ecx, eax
0x1400856ca  jnb     short loc_140085709
0x1400856cc  inc     cl
0x1400856ce  movzx   ecx, cl
0x1400856d1  mov     [rbx+60h], cl
0x1400856d4  lea     rax, [rcx+rcx*4]
0x1400856d8  cmp     cl, sil
0x1400856db  jbe     loc_140085D04
0x1400856e1  lea     rcx, [rbx+310h]
0x1400856e8  lea     rcx, [rcx+rax*8]
0x1400856ec  lea     rax, [rsp+140h+var_C8]
0x1400856f1  mov     [rcx+8], rdx
0x1400856f5  mov     [rcx], rax
0x1400856f8  xor     eax, eax
0x1400856fa  mov     [rcx+20h], ax
0x1400856fe  mov     rax, cs:off_1401FE258
0x140085705  mov     [rcx+10h], rax
0x140085709  mov     r15, [r14+10h]
0x14008570d  test    r15, r15
0x140085710  jnz     short loc_140085750
0x140085712  xor     ecx, ecx
0x140085714  mov     [rsp+140h+var_10C], ecx
0x140085718  jmp     loc_1400857D3
0x14008571d  mov     rax, [r9+8]
0x140085721  movups  xmm0, xmmword ptr [r8]
0x140085725  movups  xmmword ptr [rax], xmm0
0x140085728  mov     rax, [r9+18h]
0x14008572c  movups  xmm0, xmmword ptr [r8]
0x140085730  movups  xmmword ptr [rax], xmm0
0x140085733  movups  xmm0, xmmword ptr [r9+10h]
0x140085738  movups  xmm1, xmmword ptr [r9]
0x14008573c  movups  xmmword ptr [rbp+40h+Src], xmm0
0x140085740  movss   dword ptr [rbp+40h+Src], xmm0
0x140085745  movups  [rsp+140h+var_C8], xmm1
0x14008574a  jmp     loc_1400856A5
0x140085750  movzx   ecx, byte ptr [rbx+60h]
0x140085754  lea     rax, [rcx+rcx*4]
0x140085758  cmp     cl, sil
0x14008575b  jbe     loc_140085D0D
0x140085761  lea     rdx, [rbx+310h]
0x140085768  lea     rdx, [rdx+rax*8]
0x14008576c  movzx   eax, byte ptr [r15+1Bh]
0x140085771  mov     dword ptr [rsp+140h+var_100], eax
0x140085775  lea     r8, [rsp+140h+var_100]
0x14008577a  movzx   eax, byte ptr [r15+1Ah]
0x14008577f  add     rax, r15
0x140085782  mov     [rsp+140h+var_100+8], rax
0x140085787  xor     eax, eax
0x140085789  mov     word ptr [rsp+140h+var_100+4], ax
0x14008578e  mov     rcx, [rdx+10h]
0x140085792  mov     rax, [rcx]
0x140085795  mov     rax, [rax+8]
0x140085799  call    _guard_dispatch_icall
0x14008579e  test    eax, eax
0x1400857a0  jnz     short loc_1400857B4
0x1400857a2  mov     rax, [r15+8]
0x1400857a6  test    rax, rax
0x1400857a9  jz      loc_140085B65
0x1400857af  mov     r15, rax
0x1400857b2  jmp     short loc_140085750
0x1400857b4  cmp     eax, 1
0x1400857b7  jnz     loc_140085BB2
0x1400857bd  mov     rax, [r15+10h]
0x1400857c1  test    rax, rax
0x1400857c4  jz      short loc_1400857CB
0x1400857c6  mov     r15, rax
0x1400857c9  jmp     short loc_140085750
0x1400857cb  mov     [rsp+140h+var_10C], 3
0x1400857d3  dec     byte ptr [rbx+60h]
0x1400857d6  xor     r9d, r9d
0x1400857d9  mov     [rsp+140h+var_108], r9
0x1400857de  xor     esi, esi
0x1400857e0  xor     edi, edi
0x1400857e2  mov     [rsp+140h+var_100], rdi
0x1400857e7  test    r12, r12
0x1400857ea  jz      loc_1400859AC
0x1400857f0  mov     rsi, [r12+20h]
0x1400857f5  xor     r14d, r14d
0x1400857f8  xor     r10b, r10b
0x1400857fb  mov     r8, r12
0x1400857fe  mov     eax, [rbx]
0x140085800  bt      rax, 0Fh
0x140085805  movzx   edx, byte ptr [rbx+60h]
0x140085809  mov     eax, 2
0x14008580e  cmovnb  r13d, eax
0x140085812  mov     [rsp+140h+var_110], r10b
0x140085817  cmp     edx, r13d
0x14008581a  jnb     short loc_14008585F
0x14008581c  inc     dl
0x14008581e  movzx   ecx, dl
0x140085821  mov     [rbx+60h], cl
0x140085824  lea     rax, [rcx+rcx*4]
0x140085828  cmp     cl, 2
0x14008582b  jbe     loc_140085D9E
0x140085831  lea     rcx, [rbx+310h]
0x140085838  lea     rcx, [rcx+rax*8]
0x14008583c  xor     eax, eax
0x14008583e  mov     [rcx], r8
0x140085841  mov     [rcx+20h], ax
0x140085845  lea     rax, ?PropertyDef@CmsCountMap@@0USmsInternalPropertyDef@@B; SmsInternalPropertyDef const CmsCountMap::PropertyDef
0x14008584c  mov     [rcx+8], rax
0x140085850  mov     rax, cs:off_1401FE258
0x140085857  mov     [rcx+10h], rax
0x14008585b  movzx   edx, byte ptr [rbx+60h]
0x14008585f  test    r10b, r10b
0x140085862  jz      short loc_140085882
0x140085864  movzx   eax, dl
0x140085867  lea     rcx, [rax+rax*4]
0x14008586b  cmp     dl, 2
0x14008586e  jbe     loc_140085DA7
0x140085874  lea     rax, [rbx+331h]
0x14008587b  lea     rax, [rax+rcx*8]
0x14008587f  mov     byte ptr [rax], 1
0x140085882  movzx   ecx, byte ptr [rbx+60h]
0x140085886  lea     rax, [rcx+rcx*4]
0x14008588a  lea     rdx, [rbx+rax*8]
0x14008588e  cmp     cl, 2
0x140085891  jbe     short loc_14008589A
0x140085893  add     rdx, 328h
0x14008589a  mov     r13, [rsp+140h+var_D8]
0x14008589f  mov     [rdx], rsi
0x1400858a2  test    r15, r15
0x1400858a5  jz      loc_140085BDE
0x1400858ab  test    r9, r9
0x1400858ae  jz      loc_140085951
0x1400858b4  lea     rax, [rsp+140h+var_100]
0x1400858b9  mov     rdx, rbx
0x1400858bc  mov     rcx, r13
0x1400858bf  mov     [rsp+140h+var_120], rax
0x1400858c4  call    ??$FindNodeOrParentInSubtree@UMST_AVL_DEFAULT_PROTOTYPE@@@@YA?AW4_TABLE_SEARCH_RESULT@@PEAU_MS_AVL_TABLE@@PEAX1PEAU_RTL_AVL_ENTRY@@PEAPEAU2@@Z; FindNodeOrParentInSubtree<MST_AVL_DEFAULT_PROTOTYPE>(_MS_AVL_TABLE *,void *,void *,_RTL_AVL_ENTRY *,_RTL_AVL_ENTRY * *)
0x1400858c9  mov     rdi, [rsp+140h+var_100]
0x1400858ce  xor     ecx, ecx
0x1400858d0  cmp     eax, 1
0x1400858d3  mov     rdx, rdi
0x1400858d6  mov     r15d, eax
0x1400858d9  cmovnz  rdx, rcx
0x1400858dd  jmp     short loc_1400858E7
0x1400858df  mov     r15d, 3
0x1400858e5  xor     edx, edx
0x1400858e7  test    rdx, rdx
0x1400858ea  jz      short loc_140085959
0x1400858ec  dec     byte ptr [rbx+60h]
0x1400858ef  mov     rcx, rsi; struct _RTL_AVL_ENTRY *
0x1400858f2  mov     rsi, rdx
0x1400858f5  test    rcx, rcx
0x1400858f8  jnz     loc_140085DE2
0x1400858fe  mov     r14d, 0C0000035h
0x140085904  test    r14d, r14d
0x140085907  jns     short loc_140085988
0x140085909  test    [rbp+40h+var_68], 1
0x14008590d  jz      short loc_140085926
0x14008590f  mov     rcx, [rbp+40h+P]; P
0x140085913  test    rcx, rcx
0x140085916  jz      short loc_140085926
0x140085918  xor     edx, edx; Tag
0x14008591a  call    cs:__imp_ExFreePoolWithTag
0x140085921  nop     dword ptr [rax+rax+00h]
0x140085926  mov     eax, r14d
0x140085929  mov     rcx, [rbp+40h+var_40]
0x14008592d  xor     rcx, rsp; StackCookie
0x140085930  call    __security_check_cookie
0x140085935  mov     rbx, [rsp+140h+arg_10]
0x14008593d  add     rsp, 110h
0x140085944  pop     r15
0x140085946  pop     r14
0x140085948  pop     r13
0x14008594a  pop     r12
0x14008594c  pop     rdi
0x14008594d  pop     rsi
0x14008594e  pop     rbp
0x14008594f  retn
0x140085951  mov     rdi, r15
0x140085954  mov     r15d, [rsp+140h+var_10C]
0x140085959  inc     dword ptr [r13+28h]
0x14008595d  cmp     r15d, 1
0x140085961  jz      short loc_140085980
0x140085963  mov     rax, cs:qword_140262628
0x14008596a  mov     r8, rbx
0x14008596d  xor     edx, edx
0x14008596f  mov     rcx, r13
0x140085972  call    _guard_dispatch_icall
0x140085977  test    rax, rax
0x14008597a  jnz     loc_140085DB9
0x140085980  dec     byte ptr [rbx+60h]
0x140085983  jmp     loc_140085904
0x140085988  mov     rax, [rbp+40h+var_A8]
0x14008598c  test    rax, rax
0x14008598f  jnz     loc_140085A45
0x140085995  test    r12, r12
0x140085998  jz      loc_140085909
0x14008599e  mov     qword ptr [r12+20h], 0
0x1400859a7  jmp     loc_140085909
0x1400859ac  mov     eax, dword ptr [rbp+40h+Src]
0x1400859af  movzx   ecx, byte ptr [rsp+140h+var_C8]
0x1400859b4  mov     [rsp+140h+var_E0], eax
0x1400859b8  add     eax, 7
0x1400859bb  and     eax, 0FFFFFFF8h
0x1400859be  mov     [rsp+140h+var_110], cl
0x1400859c2  add     eax, 20h ; ' '
0x1400859c5  cmp     eax, cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x1400859cb  mov     r14d, eax
0x1400859ce  ja      loc_140085AE8
0x1400859d4  xor     ecx, ecx; ProcNumber
0x1400859d6  cmp     eax, cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x1400859dc  ja      short loc_140085A4D
0x1400859de  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400859e5  nop     dword ptr [rax+rax+00h]
0x1400859ea  xor     edx, edx
0x1400859ec  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400859f2  lea     r13, [rdx+rdx*2]
0x1400859f6  shl     r13, 6
0x1400859fa  add     r13, cs:qword_140262458
0x140085a01  mov     eax, [r13+0]
0x140085a05  cmp     r14, rax
0x140085a08  jbe     loc_140085AA4
0x140085a0e  xor     r13d, r13d
0x140085a11  lea     rdx, [r14+10h]
0x140085a15  mov     ecx, 42h ; 'B'
0x140085a1a  mov     r8d, 6950534Dh
0x140085a20  call    cs:__imp_ExAllocatePool2
0x140085a27  nop     dword ptr [rax+rax+00h]
0x140085a2c  mov     r14, rax
0x140085a2f  test    al, 0Fh
0x140085a31  jnz     loc_1401F8175
0x140085a37  test    rax, rax
0x140085a3a  jz      loc_140085C8A
0x140085a40  jmp     loc_140085C83
0x140085a45  mov     [rax], rsi
0x140085a48  jmp     loc_140085995
0x140085a4d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140085a54  nop     dword ptr [rax+rax+00h]
0x140085a59  mov     r13, cs:qword_140262460
0x140085a60  mov     eax, [r13+0]
0x140085a64  cmp     r14, rax
0x140085a67  jbe     loc_140085B6E
0x140085a6d  xor     r13d, r13d
0x140085a70  lea     rdx, [r14+10h]
0x140085a74  mov     ecx, 42h ; 'B'
0x140085a79  mov     r8d, 6950534Dh
0x140085a7f  call    cs:__imp_ExAllocatePool2
0x140085a86  nop     dword ptr [rax+rax+00h]
0x140085a8b  mov     r14, rax
0x140085a8e  test    al, 0Fh
0x140085a90  jnz     loc_1401F8175
0x140085a96  test    rax, rax
  ... truncated ...
```
