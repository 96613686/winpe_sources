# CmsRangeMap::DeleteEntry(CmsTransactionCore *,SmsRangeMapEntry *,_SmsPreAllocatedRow *,uchar,_SmsQuickIndex *)

- ea: `0x1400754b0`
- end: `0x140075e9f`
- name: `?DeleteEntry@CmsRangeMap@@UEAAJPEAVCmsTransactionCore@@PEAUSmsRangeMapEntry@@PEAU_SmsPreAllocatedRow@@EPEAU_SmsQuickIndex@@@Z`
- size: `2543`
- prototype: `__int64 __fastcall(CmsRangeMap *__hidden this, struct CmsTransactionCore *, struct SmsRangeMapEntry *, struct _SmsPreAllocatedRow *, unsigned __int8, struct _SmsQuickIndex *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x14001e2c4`
- `0x140074ee0`
- `0x140075200`
- `0x1400754b0`
- `0x140075eb0`
- `0x1400c8574`
- `0x1401e9ce0`
- `0x1401e9dc0`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140075df4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140075df4`
- `ntoskrnl!ExAllocatePool2` at `0x140075849`
- `ntoskrnl!ExAllocatePool2` at `0x1400759a4`
- `ntoskrnl!ExAllocatePool2` at `0x140075849`
- `ntoskrnl!ExAllocatePool2` at `0x1400759a4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140075807`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140075807`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6f3e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6f3e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140075e11`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140075e11`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400756e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400758b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400756e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400758b5`

## string_xrefs

- `0x140075860`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsRangeMap::DeleteEntry(
        CmsRangeMap *this,
        struct CmsTransactionCore *a2,
        struct SmsRangeMapEntry *a3,
        struct _SmsPreAllocatedRow *a4,
        unsigned __int8 a5,
        struct _SmsQuickIndex *a6)
{
  struct _SmsPreAllocatedRow *v6; // rdi
  char v7; // r9
  _BYTE *v9; // r8
  struct SmsRangeMapEntry *v11; // rdx
  __m128i v12; // xmm6
  __int128 v13; // xmm7
  _QWORD *v14; // rsi
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  _QWORD *v19; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int64 v22; // r15
  unsigned __int64 v23; // rbx
  unsigned int v24; // r12d
  __int64 v25; // r8
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rcx
  char *v28; // rdi
  __int64 v30; // r13
  unsigned __int64 v31; // rdx
  __int64 v32; // r13
  bool v33; // zf
  unsigned int *v34; // r13
  __int64 v35; // rdx
  __int64 v36; // rax
  PSLIST_ENTRY v37; // rdi
  unsigned __int64 v38; // rdx
  unsigned __int64 *v39; // rax
  __int64 v40; // rax
  __int128 v41; // xmm0
  unsigned __int64 *v42; // rax
  struct _SmsPreAllocatedRow *v43; // r8
  char v44; // r11
  __int64 v45; // rax
  struct _RTL_AVL_ENTRY *v46; // r10
  __int128 v47; // xmm1
  __int16 v48; // r13
  unsigned __int64 v49; // rdi
  int v50; // r9d
  unsigned int v51; // edx
  unsigned int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rax
  char *v55; // rcx
  char *v56; // rcx
  struct CmsTransactionCore *v57; // r11
  char *v58; // rax
  __int64 v59; // rcx
  struct _RTL_AVL_ENTRY **v60; // rdx
  unsigned __int64 v61; // rdx
  unsigned __int64 *v62; // rax
  CmsRangeMap *v63; // r15
  _QWORD *v64; // rsi
  _OWORD *v65; // rax
  _OWORD *v66; // rcx
  struct _SmsPreAllocatedRow *v67; // rax
  unsigned __int64 v68; // rax
  int v69; // ecx
  unsigned __int64 v70; // rdx
  unsigned __int64 *v71; // rax
  unsigned __int64 v72; // rax
  struct _NPAGED_LOOKASIDE_LIST *v73; // rcx
  struct _SLIST_ENTRY *v74; // rax
  unsigned __int64 i; // rdx
  char v76; // al
  char v77; // cl
  char v78; // [rsp+20h] [rbp-E0h]
  __int64 v79; // [rsp+28h] [rbp-D8h]
  int v80; // [rsp+28h] [rbp-D8h]
  int v82; // [rsp+38h] [rbp-C8h]
  char *v83; // [rsp+38h] [rbp-C8h]
  __m128i v84; // [rsp+40h] [rbp-C0h]
  __m128i v85; // [rsp+40h] [rbp-C0h]
  __m128i v86; // [rsp+40h] [rbp-C0h]
  __int128 v87; // [rsp+50h] [rbp-B0h]
  __int64 Pool2; // [rsp+68h] [rbp-98h]
  __int128 v90; // [rsp+78h] [rbp-88h] BYREF
  void *Src[2]; // [rsp+88h] [rbp-78h]
  __int128 v92; // [rsp+98h] [rbp-68h] BYREF
  __int64 v93; // [rsp+A8h] [rbp-58h]
  struct _SmsPreAllocatedRow *v94; // [rsp+B0h] [rbp-50h]
  int v95; // [rsp+C0h] [rbp-40h]
  __int16 epi16; // [rsp+C4h] [rbp-3Ch]
  __int16 v97; // [rsp+C6h] [rbp-3Ah]
  unsigned __int64 v98; // [rsp+C8h] [rbp-38h]
  int v99; // [rsp+D0h] [rbp-30h]
  int v100; // [rsp+D4h] [rbp-2Ch]
  _QWORD *v101; // [rsp+D8h] [rbp-28h]
  PVOID P; // [rsp+E0h] [rbp-20h]
  char v103; // [rsp+E8h] [rbp-18h]
  int v104; // [rsp+ECh] [rbp-14h]
  _BYTE v105[32]; // [rsp+F0h] [rbp-10h] BYREF

  v94 = a4;
  v6 = a4;
  v7 = 0;
  epi16 = _mm_extract_epi16((__m128i)0LL, 2);
  v9 = v105;
  v97 = 0;
  v90 = 0;
  v100 = HIDWORD(v94);
  v95 = 0;
  v98 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  P = v105;
  v104 = 32;
  v99 = 0;
  v101 = 0;
  v103 = 0;
  v92 = 0u;
  v93 = 0;
  v87 = 0;
  if ( v6 )
  {
    *(_OWORD *)*((_QWORD *)v6 + 1) = *(_OWORD *)a3;
    v40 = *((_QWORD *)v6 + 3);
    *(_OWORD *)v40 = *(_OWORD *)a3;
    *(_QWORD *)(v40 + 16) = *((_QWORD *)a3 + 2);
    v11 = (struct SmsRangeMapEntry *)*((_QWORD *)v6 + 1);
    v41 = *((_OWORD *)v6 + 1);
    v7 = v103;
    v9 = P;
    v90 = *(_OWORD *)v6;
    *(_OWORD *)Src = v41;
  }
  else
  {
    v11 = a3;
    LODWORD(v90) = 16;
    *((_QWORD *)&v90 + 1) = a3;
    Src[1] = a3;
    LODWORD(Src[0]) = 24;
  }
  if ( a6 )
  {
    v12 = *(__m128i *)a6;
    v13 = *((_OWORD *)a6 + 1);
    *((_QWORD *)&v87 + 1) = *((_QWORD *)&v13 + 1);
    if ( *(_QWORD *)a6 )
      v14 = (_QWORD *)(*(_QWORD *)a6 + *(unsigned __int8 *)(*(_QWORD *)a6 + 26LL));
    else
      v14 = 0;
    v15 = (_QWORD *)*((_QWORD *)a6 + 1);
    if ( v15 )
    {
      if ( ((*((_DWORD *)a6 + 4) - 1) & 0xFFFFFFFD) != 0 )
        goto LABEL_14;
      v16 = (_QWORD *)v15[2];
      if ( v16 )
      {
        for ( ; v16[1]; v16 = (_QWORD *)v16[1] )
          ;
        v15 = v16;
      }
      else
      {
        v17 = (_QWORD *)*v15;
        if ( *(_QWORD **)(*v15 + 16LL) == v15 )
        {
          do
          {
            v18 = (_QWORD *)*v17;
            v19 = v17;
            v17 = v18;
          }
          while ( (_QWORD *)v18[2] == v19 );
        }
        else
        {
          v18 = (_QWORD *)*v15;
          v19 = (_QWORD *)*((_QWORD *)a6 + 1);
        }
        v15 = 0;
        if ( (_QWORD *)v18[1] == v19 )
          v15 = v18;
      }
      if ( v15 )
      {
LABEL_14:
        *((_DWORD *)a6 + 4) = 1;
        *((_QWORD *)a6 + 1) = v15;
        v95 = *((unsigned __int8 *)v15 + 27);
        v20 = (unsigned __int64)v15 + *((unsigned __int8 *)v15 + 26);
        epi16 = 0;
        v98 = v20;
        v99 = *((unsigned __int16 *)v15 + 15);
        v21 = *((unsigned __int8 *)v15 + 26);
        *(_QWORD *)a6 = v15;
        v101 = (_QWORD *)((char *)v15 + v21);
LABEL_15:
        v82 = v13;
        v22 = v12.m128i_i64[0];
        v23 = _mm_srli_si128(v12, 8).m128i_u64[0];
        goto LABEL_16;
      }
      *((_QWORD *)a6 + 1) = 0;
    }
    *(_QWORD *)a6 = 0;
    goto LABEL_15;
  }
  v23 = *((_QWORD *)this + 3);
  if ( !v23 )
  {
LABEL_43:
    if ( (v7 & 1) != 0 && v9 )
      ExFreePoolWithTag(v9, 0);
    return 3221225524LL;
  }
  v38 = *(_QWORD *)v11;
  while ( 1 )
  {
    v39 = (unsigned __int64 *)(v23 + *(unsigned __int8 *)(v23 + 26));
    if ( v38 < *v39 )
    {
      v23 = *(_QWORD *)(v23 + 8);
      goto LABEL_42;
    }
    v22 = v23;
    if ( v38 < v39[1] + *v39 )
      break;
    v23 = *(_QWORD *)(v23 + 16);
LABEL_42:
    if ( !v23 )
      goto LABEL_43;
  }
  v6 = v94;
  v95 = *(unsigned __int8 *)(v23 + 27);
  v72 = v23 + *(unsigned __int8 *)(v23 + 26);
  epi16 = 0;
  v98 = v72;
  v99 = *(unsigned __int16 *)(v23 + 30);
  v14 = (_QWORD *)(v23 + *(unsigned __int8 *)(v23 + 26));
  v86.m128i_i64[0] = v23;
  LODWORD(v87) = 1;
  v86.m128i_i64[1] = v23;
  v12 = v86;
  DWORD1(v87) = *((_DWORD *)this + 12);
  v13 = v87;
  v101 = v14;
  v82 = 1;
LABEL_16:
  v24 = 0;
  v25 = *v14;
  v26 = *((_QWORD *)a3 + 1);
  if ( *v14 != *(_QWORD *)a3 )
  {
    v30 = v14[1];
    v31 = *(_QWORD *)a3 + v26;
    ++*((_DWORD *)this + 11);
    v32 = v25 + v30;
    v79 = v32;
    if ( v32 == v31 )
    {
      v14[1] -= *((_QWORD *)a3 + 1);
      goto LABEL_19;
    }
    v14[1] = *(_QWORD *)a3 - *v14;
    *(_QWORD *)&v92 = v31;
    v33 = *((_BYTE *)this + 56) == 0;
    *((_QWORD *)&v92 + 1) = v32 - v31;
    if ( v33 )
      v93 = v14[2] + v31 - *v14;
    else
      v93 = v14[2];
    if ( v6 )
    {
      v42 = (unsigned __int64 *)*((_QWORD *)v6 + 1);
      v43 = v6;
      v44 = 0;
      *v42 = v31;
      v42[1] = v32 - v31;
      v45 = *((_QWORD *)v6 + 3);
      *(_OWORD *)v45 = v92;
      *(_QWORD *)(v45 + 16) = v93;
      v46 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v6 + 4);
      v47 = *((_OWORD *)v6 + 1);
      Pool2 = (__int64)v46;
      v90 = *(_OWORD *)v6;
      *(_OWORD *)Src = v47;
      goto LABEL_61;
    }
    LODWORD(v90) = 16;
    *((_QWORD *)&v90 + 1) = &v92;
    Src[1] = &v92;
    LODWORD(Src[0]) = 24;
    if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside2 < 0x38 )
    {
      Pool2 = ExAllocatePool2(66, 56, 1766871885);
      v37 = (PSLIST_ENTRY)Pool2;
      if ( Pool2 )
      {
        v48 = 0x8000;
LABEL_60:
        *((_WORD *)&v37[1].Next + 6) = 0;
        memmove(&v37[2], Src[1], LODWORD(Src[0]));
        v46 = (struct _RTL_AVL_ENTRY *)Pool2;
        v43 = (struct _SmsPreAllocatedRow *)&v90;
        *((_WORD *)&v37[1].Next + 5) = 4128;
        v44 = 1;
        *((_WORD *)&v37[1].Next + 6) |= v48;
        v32 = v79;
        *((_WORD *)&v37[1].Next + 7) = 24;
LABEL_61:
        v49 = 0;
        v50 = 2;
        v78 = v44;
        v80 = 2;
        v51 = *((unsigned __int8 *)a2 + 96);
        v52 = 5;
        if ( (*(_DWORD *)a2 & 0x8000LL) == 0 )
          v52 = 2;
        if ( v51 < v52 )
        {
          v53 = (unsigned __int8)(v51 + 1);
          v54 = 5 * v53;
          *((_BYTE *)a2 + 96) = v53;
          if ( (unsigned __int8)v53 <= 2u )
            v55 = (char *)a2 - 24;
          else
            v55 = (char *)a2 + 784;
          v56 = &v55[8 * v54];
          *(_QWORD *)v56 = v43;
          *((_WORD *)v56 + 16) = 0;
          *((_QWORD *)v56 + 1) = &CmsRangeMap::PropertyDef;
          *((_QWORD *)v56 + 2) = &off_140200A10;
          LOBYTE(v51) = *((_BYTE *)a2 + 96);
        }
        v33 = v44 == 0;
        v57 = a2;
        if ( !v33 )
        {
          if ( (unsigned __int8)v51 <= 2u )
            v58 = (char *)a2 + 9;
          else
            v58 = (char *)a2 + 817;
          v58[40 * (unsigned __int8)v51] = 1;
        }
        v59 = *((unsigned __int8 *)a2 + 96);
        v60 = (struct _RTL_AVL_ENTRY **)((char *)a2 + 40 * v59);
        if ( (unsigned __int8)v59 > 2u )
          v60 += 101;
        *v60 = v46;
        if ( v23 )
        {
          if ( !v22 )
          {
            v63 = this;
            v49 = v23;
            v50 = v82;
            v80 = v82;
            v64 = (_QWORD *)((char *)this + 24);
            goto LABEL_87;
          }
          v83 = (char *)this + 24;
          if ( *((_QWORD *)this + 3) )
          {
            v49 = v22;
            v61 = **((_QWORD **)v43 + 1);
            while ( 1 )
            {
              while ( 1 )
              {
                v62 = v49 ? (unsigned __int64 *)(v49 + *(unsigned __int8 *)(v49 + 26)) : 0LL;
                if ( v61 >= *v62 )
                  break;
                if ( !*(_QWORD *)(v49 + 8) )
                  goto LABEL_93;
                v49 = *(_QWORD *)(v49 + 8);
              }
              if ( v61 < v62[1] + *v62 )
                break;
              if ( !*(_QWORD *)(v49 + 16) )
              {
                v63 = this;
                v50 = 3;
                v80 = 3;
                v68 = 0;
                goto LABEL_98;
              }
              v49 = *(_QWORD *)(v49 + 16);
            }
            v50 = 1;
            v68 = v49;
            v80 = 1;
          }
          else
          {
            v50 = 0;
            v80 = 0;
LABEL_93:
            v68 = 0;
          }
          v63 = this;
        }
        else
        {
          v63 = this;
          v83 = (char *)this + 24;
          if ( *((_QWORD *)this + 3) )
          {
            v49 = *((_QWORD *)this + 3);
            v70 = **((_QWORD **)v43 + 1);
            while ( 1 )
            {
              while ( 1 )
              {
                v71 = v49 ? (unsigned __int64 *)(v49 + *(unsigned __int8 *)(v49 + 26)) : 0LL;
                if ( v70 >= *v71 )
                  break;
                if ( !*(_QWORD *)(v49 + 8) )
                  goto LABEL_96;
                v49 = *(_QWORD *)(v49 + 8);
              }
              if ( v70 < v71[1] + *v71 )
                break;
              if ( !*(_QWORD *)(v49 + 16) )
              {
                v50 = 3;
                goto LABEL_96;
              }
              v49 = *(_QWORD *)(v49 + 16);
            }
            v50 = 1;
            v68 = v49;
          }
          else
          {
            v50 = 0;
LABEL_96:
            v68 = 0;
          }
          v80 = v50;
        }
LABEL_98:
        if ( v68 )
        {
          v85.m128i_i64[0] = v68;
          v85.m128i_i64[1] = v68;
          DWORD1(v87) = *((_DWORD *)v63 + 12);
          LODWORD(v87) = 3;
          --*((_BYTE *)a2 + 96);
          if ( v46 && v78 )
            CmsAvlTableLite::FreeIndexEntry(v46);
          v13 = v87;
          v24 = -1073741771;
          v12 = v85;
          goto LABEL_101;
        }
        v64 = v83;
        v57 = a2;
LABEL_87:
        ++*((_DWORD *)v63 + 12);
        if ( v50 != 1 )
        {
          v65 = (_OWORD *)((__int64 (__fastcall *)(char *, _QWORD, struct CmsTransactionCore *))qword_140262628)(
                            (char *)v63 + 8,
                            0,
                            v57);
          v66 = v65;
          if ( v65 )
          {
            *v65 = 0;
            *(_OWORD *)((char *)v65 + 10) = 0;
            ++*((_DWORD *)v63 + 10);
            if ( v80 )
            {
              if ( v80 == 2 )
                *(_QWORD *)(v49 + 8) = v65;
              else
                *(_QWORD *)(v49 + 16) = v65;
              *(_QWORD *)v65 = v49;
              *((_BYTE *)v63 + 32) = -1;
              for ( i = *(_QWORD *)v65; ; v49 = i )
              {
                v33 = *(_QWORD *)(i + 8) == (_QWORD)v66;
                v76 = -1;
                v77 = *(_BYTE *)(v49 + 24);
                if ( !v33 )
                  v76 = 1;
                if ( v77 )
                  break;
                i = *(_QWORD *)v49;
                v66 = (_OWORD *)v49;
                *(_BYTE *)(v49 + 24) = v76;
              }
              if ( v77 == v76 )
                RebalanceNode((struct _RTL_AVL_ENTRY *)v49);
              else
                *(_BYTE *)(v49 + 24) = 0;
            }
            else
            {
              *v64 = v65;
              *(_QWORD *)v65 = (char *)v63 + 8;
            }
          }
          v46 = (struct _RTL_AVL_ENTRY *)Pool2;
        }
        DWORD1(v87) = *((_DWORD *)v63 + 12);
        v67 = v94;
        v84.m128i_i64[0] = (__int64)v46;
        --*((_BYTE *)a2 + 96);
        v84.m128i_i64[1] = (__int64)v46;
        LODWORD(v87) = 1;
        v13 = v87;
        v12 = v84;
        if ( v67 )
          *((_QWORD *)v67 + 4) = 0;
LABEL_102:
        if ( a6 )
          goto LABEL_26;
        goto LABEL_19;
      }
LABEL_144:
      v63 = this;
      v24 = -1073741670;
LABEL_101:
      v14[1] = v32 - *v14;
      --*((_DWORD *)v63 + 11);
      goto LABEL_102;
    }
    if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside1 < 0x38 )
    {
      v37 = CmsLookasides::Allocate(0x38u, 0xCu, 0);
      v48 = 0x4000;
LABEL_109:
      if ( v37 )
      {
        Pool2 = (__int64)v37;
        goto LABEL_60;
      }
      v32 = v79;
      goto LABEL_144;
    }
    v34 = (unsigned int *)(qword_140262458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( *v34 < 0x38uLL )
    {
      v34 = 0;
      v35 = 72;
      goto LABEL_35;
    }
    if ( !*((_BYTE *)v34 + 8) )
    {
      if ( (int)*((_QWORD *)v34 + 11) > (int)HIDWORD(*((_QWORD *)v34 + 11)) )
      {
        v69 = _InterlockedDecrement((volatile signed __int32 *)v34 + 22);
        if ( v69 >= (int)v34[23] && v69 >= 0 )
        {
          v74 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v34 + 4);
          goto LABEL_106;
        }
        _InterlockedIncrement((volatile signed __int32 *)v34 + 22);
      }
LABEL_115:
      v35 = v34[1];
LABEL_35:
      v36 = ExAllocatePool2(66, v35, 1766871885);
      v37 = (PSLIST_ENTRY)v36;
      if ( (v36 & 0xF) != 0 )
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      if ( !v36 )
        goto LABEL_108;
      goto LABEL_107;
    }
    v73 = (struct _NPAGED_LOOKASIDE_LIST *)(v34 + 16);
    if ( *((_BYTE *)v34 + 9) )
      v74 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v73);
    else
      v74 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v73);
LABEL_106:
    v37 = v74;
    if ( v74 )
    {
LABEL_107:
      v37->Next = (struct _SLIST_ENTRY *)v34;
      ++v37;
LABEL_108:
      v48 = 0x2000;
      goto LABEL_109;
    }
    goto LABEL_115;
  }
  v27 = v14[1];
  if ( v27 <= v26 )
  {
    ++*((_DWORD *)this + 11);
    v28 = (char *)this + 8;
    DeleteNodeFromTree((CmsRangeMap *)((char *)this + 8), (struct _RTL_AVL_ENTRY *)v23, 1u);
    --*((_DWORD *)v28 + 8);
    CmsAvlTableLite::FreeIndexEntry((struct _RTL_AVL_ENTRY *)v23);
    ++*((_DWORD *)v28 + 10);
    goto LABEL_19;
  }
  *v14 = v25 + v26;
  v14[1] = v27 - v26;
  if ( !*((_BYTE *)this + 56) )
    v14[2] += v26;
  ++*((_DWORD *)this + 11);
  if ( a6 )
  {
LABEL_26:
    *(__m128i *)a6 = v12;
    *((_OWORD *)a6 + 1) = v13;
  }
LABEL_19:
  if ( (v103 & 1) != 0 )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
  }
  return v24;
}

```

## disassembly

```asm
0x1400754b0  push    rbp
0x1400754b2  push    rdi
0x1400754b3  push    r12
0x1400754b5  push    r13
0x1400754b7  push    r14
0x1400754b9  lea     rbp, [rsp-50h]
0x1400754be  sub     rsp, 150h
0x1400754c5  mov     rax, cs:__security_cookie
0x1400754cc  xor     rax, rsp
0x1400754cf  mov     [rbp+70h+var_60], rax
0x1400754d3  mov     r14, [rbp+70h+arg_28]
0x1400754da  xorps   xmm0, xmm0
0x1400754dd  pextrw  eax, xmm0, 2
0x1400754e2  xor     r13d, r13d
0x1400754e5  mov     [rbp+70h+var_C0], r9
0x1400754e9  movups  [rsp+170h+var_108], xmm0
0x1400754ee  mov     rdi, r9
0x1400754f1  xor     r9b, r9b
0x1400754f4  mov     [rbp+70h+var_AC], ax
0x1400754f8  mov     r10, r8
0x1400754fb  movzx   eax, word ptr [rsp+170h+var_108+6]
0x140075500  lea     r8, [rbp+70h+var_80]
0x140075504  mov     [rbp+70h+var_AA], ax
0x140075508  mov     r11, rcx
0x14007550b  mov     eax, dword ptr [rbp+70h+var_C0+4]
0x14007550e  movups  [rsp+170h+var_F8], xmm0
0x140075513  mov     [rbp+70h+var_9C], eax
0x140075516  xor     eax, eax
0x140075518  movss   [rbp+70h+var_B0], xmm0
0x14007551d  psrldq  xmm0, 8
0x140075522  movq    [rbp+70h+var_A8], xmm0
0x140075527  xorps   xmm0, xmm0
0x14007552a  mov     [rsp+170h+var_140], rdx
0x14007552f  mov     [rsp+170h+var_110], rcx
0x140075534  mov     [rbp+70h+P], r8
0x140075538  mov     [rbp+70h+var_84], 20h ; ' '
0x14007553f  mov     [rbp+70h+var_A0], r13d
0x140075543  mov     [rbp+70h+var_98], r13
0x140075547  mov     [rbp+70h+var_88], r9b
0x14007554b  mov     qword ptr [rbp+70h+var_D8], r13
0x14007554f  mov     qword ptr [rbp+70h+var_D8+8], r13
0x140075553  mov     [rbp+70h+var_C8], rax
0x140075557  movups  [rsp+170h+var_130], xmm0
0x14007555c  movups  [rsp+170h+var_120], xmm0
0x140075561  test    rdi, rdi
0x140075564  jnz     loc_140075912
0x14007556a  mov     rdx, r10
0x14007556d  mov     dword ptr [rsp+170h+var_F8], 10h
0x140075575  mov     qword ptr [rbp+70h+var_F8+8], rdx
0x140075579  mov     [rbp+70h+Src+8], r10
0x14007557d  mov     dword ptr [rbp+70h+Src], 18h
0x140075584  mov     [rsp+170h+arg_10], rbx
0x14007558c  mov     r12d, 1
0x140075592  mov     [rsp+170h+var_28], rsi
0x14007559a  mov     [rsp+170h+var_30], r15
0x1400755a2  movaps  [rsp+170h+var_40], xmm6
0x1400755aa  movaps  [rsp+170h+var_50], xmm7
0x1400755b2  test    r14, r14
0x1400755b5  jz      loc_14007586D
0x1400755bb  movups  xmm6, xmmword ptr [r14]
0x1400755bf  mov     rax, [r14]
0x1400755c2  movups  xmm7, xmmword ptr [r14+10h]
0x1400755c7  movups  [rsp+170h+var_130], xmm6
0x1400755cc  movups  [rsp+170h+var_120], xmm7
0x1400755d1  test    rax, rax
0x1400755d4  jz      loc_1400758F1
0x1400755da  movzx   esi, byte ptr [rax+1Ah]
0x1400755de  add     rsi, rax
0x1400755e1  mov     rcx, [r14+8]
0x1400755e5  test    rcx, rcx
0x1400755e8  jz      loc_14007590A
0x1400755ee  mov     eax, [r14+10h]
0x1400755f2  dec     eax
0x1400755f4  test    eax, 0FFFFFFFDh
0x1400755f9  jnz     short loc_140075638
0x1400755fb  mov     rax, [rcx+10h]
0x1400755ff  test    rax, rax
0x140075602  jnz     loc_1400758D9
0x140075608  mov     rax, [rcx]
0x14007560b  cmp     [rax+10h], rcx
0x14007560f  jnz     loc_1400758CE
0x140075615  mov     rdx, [rax]
0x140075618  mov     r8, rax
0x14007561b  mov     rax, rdx
0x14007561e  cmp     [rdx+10h], r8
0x140075622  jz      short loc_140075615
0x140075624  cmp     [rdx+8], r8
0x140075628  mov     rcx, r13
0x14007562b  cmovz   rcx, rdx
0x14007562f  test    rcx, rcx
0x140075632  jz      loc_140075906
0x140075638  mov     [r14+10h], r12d
0x14007563c  mov     [r14+8], rcx
0x140075640  movzx   eax, byte ptr [rcx+1Bh]
0x140075644  mov     [rbp+70h+var_B0], eax
0x140075647  movzx   eax, byte ptr [rcx+1Ah]
0x14007564b  add     rax, rcx
0x14007564e  mov     [rbp+70h+var_AC], r13w
0x140075653  mov     [rbp+70h+var_A8], rax
0x140075657  movzx   eax, word ptr [rcx+1Eh]
0x14007565b  mov     [rbp+70h+var_A0], eax
0x14007565e  movzx   eax, byte ptr [rcx+1Ah]
0x140075662  add     rax, rcx
0x140075665  mov     [r14], rcx
0x140075668  mov     [rbp+70h+var_98], rax
0x14007566c  movdqa  xmm0, xmm6
0x140075670  movss   dword ptr [rsp+170h+var_138], xmm7
0x140075676  psrldq  xmm0, 8
0x14007567b  movq    r15, xmm6
0x140075680  movq    rbx, xmm0
0x140075685  mov     rcx, [r10]
0x140075688  mov     r12d, r13d
0x14007568b  mov     r8, [rsi]
0x14007568e  mov     rdx, [r10+8]
0x140075692  cmp     r8, rcx
0x140075695  jnz     loc_140075769
0x14007569b  mov     rcx, [rsi+8]
0x14007569f  cmp     rcx, rdx
0x1400756a2  ja      loc_140075736
0x1400756a8  inc     dword ptr [r11+2Ch]
0x1400756ac  lea     rdi, [r11+8]
0x1400756b0  mov     rcx, rdi; struct _MS_AVL_TABLE *
0x1400756b3  mov     r8b, 1; unsigned __int8
0x1400756b6  mov     rdx, rbx; struct _RTL_AVL_ENTRY *
0x1400756b9  call    ?DeleteNodeFromTree@@YAXPEAU_MS_AVL_TABLE@@PEAU_RTL_AVL_ENTRY@@E@Z; DeleteNodeFromTree(_MS_AVL_TABLE *,_RTL_AVL_ENTRY *,uchar)
0x1400756be  mov     eax, [rdi+20h]
0x1400756c1  mov     rcx, rbx; struct _RTL_AVL_ENTRY *
0x1400756c4  dec     eax
0x1400756c6  mov     [rdi+20h], eax
0x1400756c9  call    ?FreeIndexEntry@CmsAvlTableLite@@CAXPEAU_RTL_AVL_ENTRY@@@Z; CmsAvlTableLite::FreeIndexEntry(_RTL_AVL_ENTRY *)
0x1400756ce  inc     dword ptr [rdi+28h]
0x1400756d1  test    [rbp+70h+var_88], 1
0x1400756d5  jz      short loc_1400756EE
0x1400756d7  mov     rcx, [rbp+70h+P]; P
0x1400756db  test    rcx, rcx
0x1400756de  jz      short loc_1400756EE
0x1400756e0  xor     edx, edx; Tag
0x1400756e2  call    cs:__imp_ExFreePoolWithTag
0x1400756e9  nop     dword ptr [rax+rax+00h]
0x1400756ee  mov     eax, r12d
0x1400756f1  movaps  xmm7, [rsp+170h+var_50]
0x1400756f9  movaps  xmm6, [rsp+170h+var_40]
0x140075701  mov     r15, [rsp+170h+var_30]
0x140075709  mov     rsi, [rsp+170h+var_28]
0x140075711  mov     rbx, [rsp+170h+arg_10]
0x140075719  mov     rcx, [rbp+70h+var_60]
0x14007571d  xor     rcx, rsp; StackCookie
0x140075720  call    __security_check_cookie
0x140075725  add     rsp, 150h
0x14007572c  pop     r14
0x14007572e  pop     r13
0x140075730  pop     r12
0x140075732  pop     rdi
0x140075733  pop     rbp
0x140075734  retn
0x140075736  sub     rcx, rdx
0x140075739  lea     rax, [r8+rdx]
0x14007573d  mov     [rsi], rax
0x140075740  mov     [rsi+8], rcx
0x140075744  cmp     [r11+38h], r13b
0x140075748  jz      loc_140075CE1
0x14007574e  inc     dword ptr [r11+2Ch]
0x140075752  test    r14, r14
0x140075755  jz      loc_1400756D1
0x14007575b  movups  xmmword ptr [r14], xmm6
0x14007575f  movups  xmmword ptr [r14+10h], xmm7
0x140075764  jmp     loc_1400756D1
0x140075769  mov     r13, [rsi+8]
0x14007576d  add     rdx, rcx
0x140075770  inc     dword ptr [r11+2Ch]
0x140075774  add     r13, r8
0x140075777  mov     [rsp+170h+var_148], r13
0x14007577c  cmp     r13, rdx
0x14007577f  jz      loc_1400758F9
0x140075785  mov     rcx, [r10]
0x140075788  sub     rcx, [rsi]
0x14007578b  mov     [rsi+8], rcx
0x14007578f  mov     rcx, r13
0x140075792  sub     rcx, rdx
0x140075795  mov     qword ptr [rbp+70h+var_D8], rdx
0x140075799  cmp     byte ptr [r11+38h], 0
0x14007579e  mov     qword ptr [rbp+70h+var_D8+8], rcx
0x1400757a2  mov     r8, [rsi+10h]
0x1400757a6  jnz     loc_140075DDC
0x1400757ac  mov     rax, rdx
0x1400757af  sub     rax, [rsi]
0x1400757b2  add     rax, r8
0x1400757b5  mov     [rbp+70h+var_C8], rax
0x1400757b9  test    rdi, rdi
0x1400757bc  jnz     loc_140075955
0x1400757c2  lea     rax, [rbp+70h+var_D8]
0x1400757c6  mov     dword ptr [rsp+170h+var_F8], 10h
0x1400757ce  mov     qword ptr [rbp+70h+var_F8+8], rax
0x1400757d2  lea     rax, [rbp+70h+var_D8]
0x1400757d6  mov     [rbp+70h+Src+8], rax
0x1400757da  mov     eax, 18h
0x1400757df  mov     dword ptr [rbp+70h+Src], eax
0x1400757e2  add     eax, 7
0x1400757e5  and     eax, 0FFFFFFF8h
0x1400757e8  add     eax, 20h ; ' '
0x1400757eb  cmp     eax, cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x1400757f1  mov     edi, eax
0x1400757f3  ja      loc_140075996
0x1400757f9  cmp     eax, cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x1400757ff  ja      loc_140075C59
0x140075805  xor     ecx, ecx; ProcNumber
0x140075807  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007580e  nop     dword ptr [rax+rax+00h]
0x140075813  xor     edx, edx
0x140075815  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14007581b  lea     r13, [rdx+rdx*2]
0x14007581f  shl     r13, 6
0x140075823  add     r13, cs:qword_140262458
0x14007582a  mov     eax, [r13+0]
0x14007582e  cmp     rdi, rax
0x140075831  jbe     loc_140075C9C
0x140075837  xor     r13d, r13d
0x14007583a  lea     rdx, [rdi+10h]
0x14007583e  mov     ecx, 42h ; 'B'
0x140075843  mov     r8d, 6950534Dh
0x140075849  call    cs:__imp_ExAllocatePool2
0x140075850  nop     dword ptr [rax+rax+00h]
0x140075855  mov     rdi, rax
0x140075858  test    al, 0Fh
0x14007585a  jz      loc_1401F6F50
0x140075860  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140075867  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14007586d  mov     rbx, [rcx+18h]
0x140075871  mov     edi, 0C0000034h
0x140075876  test    rbx, rbx
0x140075879  jz      short loc_1400758A6
0x14007587b  mov     rdx, [rdx]
0x14007587e  movzx   eax, byte ptr [rbx+1Ah]
0x140075882  add     rax, rbx
0x140075885  mov     rcx, [rax]
0x140075888  cmp     rdx, rcx
0x14007588b  jb      short loc_1400758C8
0x14007588d  add     rcx, [rax+8]
0x140075891  mov     r15, rbx
0x140075894  cmp     rdx, rcx
0x140075897  jb      loc_140075D5A
0x14007589d  mov     rbx, [rbx+10h]
0x1400758a1  test    rbx, rbx
0x1400758a4  jnz     short loc_14007587E
0x1400758a6  test    r12b, r9b
0x1400758a9  jz      short loc_1400758C1
0x1400758ab  test    r8, r8
0x1400758ae  jz      short loc_1400758C1
0x1400758b0  xor     edx, edx; Tag
0x1400758b2  mov     rcx, r8; P
0x1400758b5  call    cs:__imp_ExFreePoolWithTag
0x1400758bc  nop     dword ptr [rax+rax+00h]
0x1400758c1  mov     eax, edi
0x1400758c3  jmp     loc_1400756F1
0x1400758c8  mov     rbx, [rbx+8]
0x1400758cc  jmp     short loc_1400758A1
0x1400758ce  mov     rdx, rax
0x1400758d1  mov     r8, rcx
0x1400758d4  jmp     loc_140075624
0x1400758d9  cmp     [rax+8], r13
0x1400758dd  jz      short loc_1400758E9
0x1400758df  mov     rax, [rax+8]
0x1400758e3  cmp     [rax+8], r13
0x1400758e7  jnz     short loc_1400758DF
0x1400758e9  mov     rcx, rax
0x1400758ec  jmp     loc_14007562F
0x1400758f1  mov     rsi, r13
0x1400758f4  jmp     loc_1400755E1
0x1400758f9  mov     rax, [r10+8]
0x1400758fd  sub     [rsi+8], rax
0x140075901  jmp     loc_1400756D1
0x140075906  mov     [r14+8], r13
0x14007590a  mov     [r14], r13
0x14007590d  jmp     loc_14007566C
0x140075912  mov     rax, [rdi+8]
0x140075916  movups  xmm0, xmmword ptr [r10]
0x14007591a  movups  xmmword ptr [rax], xmm0
0x14007591d  mov     rax, [rdi+18h]
0x140075921  movups  xmm0, xmmword ptr [r10]
0x140075925  movups  xmmword ptr [rax], xmm0
0x140075928  movsd   xmm1, qword ptr [r10+10h]
0x14007592e  movsd   qword ptr [rax+10h], xmm1
0x140075933  movups  xmm2, xmmword ptr [rdi]
0x140075936  mov     rdx, [rdi+8]
0x14007593a  movups  xmm0, xmmword ptr [rdi+10h]
0x14007593e  movzx   r9d, [rbp+70h+var_88]
0x140075943  mov     r8, [rbp+70h+P]
0x140075947  movups  [rsp+170h+var_F8], xmm2
0x14007594c  movups  xmmword ptr [rbp+70h+Src], xmm0
0x140075950  jmp     loc_140075584
0x140075955  mov     rax, [rdi+8]
0x140075959  mov     r8, rdi
0x14007595c  xor     r11b, r11b
0x14007595f  mov     [rax], rdx
0x140075962  mov     [rax+8], rcx
0x140075966  movups  xmm0, [rbp+70h+var_D8]
0x14007596a  mov     rax, [rdi+18h]
0x14007596e  movups  xmmword ptr [rax], xmm0
0x140075971  movsd   xmm1, [rbp+70h+var_C8]
0x140075976  movsd   qword ptr [rax+10h], xmm1
  ... truncated ...
```
