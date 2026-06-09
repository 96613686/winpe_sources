# CmsRangeMap::AddEntry(CmsTransactionCore *,SmsRangeMapEntry *,_SmsPreAllocatedRow *,unsigned __int64 *,SmsRangeMapEntry *,_SmsQuickIndex *,_RTL_AVL_ENTRY * *)

- ea: `0x1400760d0`
- end: `0x1400770bf`
- name: `?AddEntry@CmsRangeMap@@UEAAJPEAVCmsTransactionCore@@PEAUSmsRangeMapEntry@@PEAU_SmsPreAllocatedRow@@PEA_K1PEAU_SmsQuickIndex@@PEAPEAU_RTL_AVL_ENTRY@@@Z`
- size: `4079`
- prototype: `__int64 __fastcall(CmsRangeMap *__hidden this, struct CmsTransactionCore *, struct SmsRangeMapEntry *, struct _SmsPreAllocatedRow *, unsigned __int64 *, struct SmsRangeMapEntry *, struct _SmsQuickIndex *, struct _RTL_AVL_ENTRY **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x140074ee0`
- `0x140075200`
- `0x140075eb0`
- `0x1400760d0`
- `0x1400a2170`
- `0x1400c8574`
- `0x1401e9ce0`
- `0x1401e9dc0`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140076fb2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140076fef`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140076fb2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140076fef`
- `ntoskrnl!ExAllocatePool2` at `0x140076b2f`
- `ntoskrnl!ExAllocatePool2` at `0x140076c5f`
- `ntoskrnl!ExAllocatePool2` at `0x140076d01`
- `ntoskrnl!ExAllocatePool2` at `0x140076b2f`
- `ntoskrnl!ExAllocatePool2` at `0x140076c5f`
- `ntoskrnl!ExAllocatePool2` at `0x140076d01`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076aee`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076c2e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076aee`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076c2e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6fdb`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6fed`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6fdb`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6fed`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140076fcf`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007700c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140076fcf`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007700c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007654e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007654e`

## string_xrefs

- `0x1401f6fff`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsRangeMap::AddEntry(
        CmsRangeMap *this,
        struct CmsTransactionCore *a2,
        struct SmsRangeMapEntry *a3,
        struct _SmsPreAllocatedRow *a4,
        unsigned __int64 *a5,
        struct SmsRangeMapEntry *a6,
        __m128i *a7,
        struct _RTL_AVL_ENTRY **a8)
{
  unsigned __int64 v8; // r14
  char v9; // r11
  unsigned __int64 v10; // r10
  unsigned __int64 v11; // r15
  struct SmsRangeMapEntry *v12; // rbx
  __m128i v13; // xmm3
  __m128i v14; // xmm4
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rsi
  int v17; // r11d
  __m128i v18; // xmm6
  __m128i v19; // xmm7
  unsigned __int64 *v20; // rdx
  unsigned __int64 v21; // r8
  unsigned __int64 v22; // r8
  unsigned __int64 *v23; // rax
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rax
  __int32 v26; // eax
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rbx
  unsigned __int64 *v29; // r13
  char v30; // r8
  unsigned __int64 v31; // r14
  unsigned __int64 v32; // rax
  _QWORD *v33; // rax
  _QWORD *v34; // rcx
  _QWORD *v35; // rdx
  __m128i v36; // xmm8
  __m128i v37; // xmm9
  char v38; // r10
  int v39; // edi
  unsigned __int64 v40; // r15
  unsigned __int64 *v41; // r8
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // rax
  unsigned __int64 v44; // r9
  unsigned __int64 v45; // rdx
  int v46; // ebx
  struct SmsRangeMapEntry *v47; // rax
  __int16 v49; // r14
  struct _RTL_AVL_ENTRY *v50; // r15
  char v51; // r9
  struct _SmsPreAllocatedRow *v52; // r8
  struct CmsTransactionCore *v53; // r11
  unsigned __int64 v54; // r14
  unsigned int v55; // edx
  unsigned int v56; // eax
  unsigned __int8 v57; // dl
  char *v58; // rcx
  char *v59; // rcx
  char *v60; // rax
  __int64 v61; // rcx
  struct _RTL_AVL_ENTRY **v62; // rdx
  CmsRangeMap *v63; // r10
  unsigned __int64 *v64; // r12
  int v65; // eax
  __int32 v66; // eax
  _QWORD *v67; // rcx
  struct _RTL_AVL_ENTRY *v68; // rax
  _QWORD **v69; // rax
  _QWORD *v70; // rdx
  struct _RTL_AVL_ENTRY *v71; // r9
  unsigned __int64 v72; // rax
  _QWORD *v73; // rax
  _QWORD *v74; // rcx
  _QWORD *v75; // rdx
  int v76; // r12d
  __int64 v77; // rax
  __int128 v78; // xmm2
  _OWORD *v79; // rax
  __int32 v80; // eax
  unsigned __int64 v81; // r9
  unsigned __int64 v82; // rcx
  __int16 v83; // r15
  char v84; // r12
  unsigned int v85; // eax
  unsigned __int64 v86; // rbx
  unsigned int *v87; // r14
  unsigned __int64 v88; // rdx
  __int64 Pool2; // rax
  _WORD *v90; // rbx
  unsigned __int64 v91; // rdx
  unsigned __int64 *v92; // rax
  __int64 v93; // r14
  unsigned __int64 v94; // rdx
  __int64 v95; // rax
  int v96; // ecx
  int v97; // ecx
  unsigned __int64 v98; // rdx
  unsigned __int64 *v99; // rax
  unsigned __int64 v100; // rax
  unsigned __int64 v101; // r14
  unsigned __int64 v102; // rax
  unsigned __int64 v103; // rax
  struct _NPAGED_LOOKASIDE_LIST *v104; // rcx
  _WORD *v105; // rax
  struct _NPAGED_LOOKASIDE_LIST *v106; // rcx
  _WORD *v107; // rax
  unsigned __int64 i; // rdx
  bool v109; // zf
  char v110; // cl
  char v111; // al
  char v112; // [rsp+20h] [rbp-E0h]
  char v113; // [rsp+21h] [rbp-DFh]
  int v114; // [rsp+24h] [rbp-DCh]
  int v115; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v116; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v117; // [rsp+38h] [rbp-C8h]
  __m128i v118; // [rsp+40h] [rbp-C0h]
  __m128i v119; // [rsp+40h] [rbp-C0h]
  __m128i v120; // [rsp+40h] [rbp-C0h]
  __m128i v121; // [rsp+40h] [rbp-C0h]
  __m128i v122; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v124; // [rsp+68h] [rbp-98h]
  unsigned __int64 v125; // [rsp+70h] [rbp-90h]
  int v126; // [rsp+78h] [rbp-88h]
  __m128i v128; // [rsp+88h] [rbp-78h]
  __m128i v129; // [rsp+88h] [rbp-78h]
  __m128i v130; // [rsp+98h] [rbp-68h]
  __m128i v131; // [rsp+98h] [rbp-68h]
  struct _RTL_AVL_ENTRY *v132; // [rsp+A8h] [rbp-58h]
  __int64 v133; // [rsp+A8h] [rbp-58h]
  __int128 v134; // [rsp+D0h] [rbp-30h] BYREF
  void *Src[2]; // [rsp+E0h] [rbp-20h]
  struct _SmsPreAllocatedRow *v136; // [rsp+F0h] [rbp-10h]
  struct _RTL_AVL_ENTRY **v137; // [rsp+F8h] [rbp-8h]
  unsigned __int64 *v138; // [rsp+100h] [rbp+0h]
  struct SmsRangeMapEntry *v139; // [rsp+108h] [rbp+8h]
  int v140; // [rsp+120h] [rbp+20h]
  __int16 epi16; // [rsp+124h] [rbp+24h]
  __int16 v142; // [rsp+126h] [rbp+26h]
  unsigned __int64 v143; // [rsp+128h] [rbp+28h]
  int v144; // [rsp+130h] [rbp+30h]
  int v145; // [rsp+134h] [rbp+34h]
  unsigned __int64 *v146; // [rsp+138h] [rbp+38h]
  PVOID P; // [rsp+140h] [rbp+40h]
  char v148; // [rsp+148h] [rbp+48h]
  int v149; // [rsp+14Ch] [rbp+4Ch]
  char v150; // [rsp+150h] [rbp+50h] BYREF

  v8 = *(_QWORD *)a3;
  v9 = 0;
  v10 = *((_QWORD *)a3 + 2);
  v11 = *((_QWORD *)a3 + 1);
  v12 = a3;
  v139 = a6;
  v13 = 0;
  v14 = 0;
  v137 = a8;
  P = &v150;
  v134 = 0;
  v136 = a4;
  v140 = 0;
  epi16 = _mm_extract_epi16((__m128i)0LL, 2);
  v143 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  v142 = 0;
  v145 = HIDWORD(a6);
  v138 = a5;
  v149 = 32;
  v144 = 0;
  v146 = 0;
  v148 = 0;
  v124 = v8;
  v117 = v10;
  v112 = 0;
  v113 = 0;
  v122 = 0;
  if ( a5 )
    *a5 = 0;
  v125 = v11;
  if ( a4 )
  {
    *(_OWORD *)*((_QWORD *)a4 + 1) = *(_OWORD *)a3;
    v77 = *((_QWORD *)a4 + 3);
    *(_OWORD *)v77 = *(_OWORD *)a3;
    *(_QWORD *)(v77 + 16) = *((_QWORD *)a3 + 2);
    a3 = (struct SmsRangeMapEntry *)*((_QWORD *)a4 + 1);
    v78 = *(_OWORD *)a4;
    *(_OWORD *)Src = *((_OWORD *)a4 + 1);
    v134 = v78;
  }
  else
  {
    *((_QWORD *)&v134 + 1) = a3;
    LODWORD(v134) = 16;
    Src[1] = a3;
    LODWORD(Src[0]) = 24;
  }
  v114 = 2;
  if ( !a7 )
  {
    v15 = *((_QWORD *)this + 3);
    v116 = v15;
    if ( !v15 )
    {
      v16 = 0;
      v17 = 0;
      goto LABEL_8;
    }
    v22 = *(_QWORD *)a3;
    while ( 1 )
    {
      while ( 1 )
      {
        v23 = v15 ? (unsigned __int64 *)(v15 + *(unsigned __int8 *)(v15 + 26)) : 0LL;
        if ( v22 >= *v23 )
          break;
        v25 = *(_QWORD *)(v15 + 8);
        if ( !v25 )
        {
          v16 = 0;
          v121.m128i_i64[0] = 0;
          v17 = 2;
          v122.m128i_i32[0] = 2;
          v121.m128i_i64[1] = v15;
          v18 = v121;
          v122.m128i_i32[1] = *((_DWORD *)this + 12);
          v19 = v122;
          v115 = 2;
          goto LABEL_93;
        }
        v15 = *(_QWORD *)(v15 + 8);
        v116 = v25;
      }
      v16 = v15;
      if ( v22 < *v23 + v23[1] )
        break;
      v24 = *(_QWORD *)(v15 + 16);
      if ( !v24 )
      {
        v16 = 0;
        v17 = 3;
LABEL_8:
        v122.m128i_i32[1] = *((_DWORD *)this + 12);
        v118.m128i_i64[0] = 0;
        v118.m128i_i64[1] = v15;
        v18 = v118;
        v122.m128i_i32[0] = v17;
        v19 = v122;
        v115 = v17;
LABEL_219:
        v116 = v15;
LABEL_93:
        v29 = 0;
        v113 = 0;
LABEL_94:
        v131 = v19;
        if ( !v15 )
          goto LABEL_175;
        v67 = (_QWORD *)v15;
        if ( v17 == 1 )
        {
          v68 = *(struct _RTL_AVL_ENTRY **)(v15 + 8);
          if ( !v68 )
          {
            v69 = *(_QWORD ***)v15;
            if ( *(_QWORD *)(*(_QWORD *)v15 + 8LL) == v15 )
            {
              do
              {
                v70 = *v69;
                v67 = v69;
                v69 = (_QWORD **)v70;
              }
              while ( (_QWORD *)v70[1] == v67 );
            }
            else
            {
              v70 = *(_QWORD **)v15;
            }
            if ( (_QWORD *)v70[2] != v67 || (_QWORD *)*v70 == v70 )
              v67 = 0;
            else
              v67 = v70;
LABEL_137:
            if ( v67 )
            {
LABEL_138:
              v9 = v112;
              v140 = *((unsigned __int8 *)v67 + 27);
              v131.m128i_i32[0] = 1;
              v14 = v131;
              v143 = (unsigned __int64)v67 + *((unsigned __int8 *)v67 + 26);
              epi16 = 0;
              v144 = *((unsigned __int16 *)v67 + 15);
              v20 = (_QWORD *)((char *)v67 + *((unsigned __int8 *)v67 + 26));
              v129.m128i_i64[1] = (__int64)v67;
              v146 = v20;
              v129.m128i_i64[0] = (__int64)v67;
              v13 = v129;
              v21 = *v20;
              goto LABEL_139;
            }
LABEL_175:
            v9 = v112;
            v117 = v10;
LABEL_142:
            v28 = v8;
            goto LABEL_143;
          }
          for ( ; *((_QWORD *)v68 + 2); v68 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v68 + 2) )
            ;
        }
        else
        {
          if ( v17 != 2 )
            goto LABEL_138;
          v68 = RealPredecessor((struct _RTL_AVL_ENTRY *)v15);
        }
        v67 = v68;
        goto LABEL_137;
      }
      v15 = *(_QWORD *)(v15 + 16);
      v116 = v24;
    }
    v119.m128i_i64[0] = v15;
    v119.m128i_i64[1] = v15;
    v116 = v15;
    v115 = 1;
    v122.m128i_i32[0] = 1;
    v18 = v119;
    if ( !v15 )
    {
      v17 = 1;
      v122.m128i_i32[1] = *((_DWORD *)this + 12);
      v19 = v122;
      goto LABEL_219;
    }
    v140 = *(unsigned __int8 *)(v15 + 27);
    v143 = v15 + *(unsigned __int8 *)(v15 + 26);
    epi16 = 0;
    v144 = *(unsigned __int16 *)(v15 + 30);
    v26 = *((_DWORD *)this + 12);
    v20 = (unsigned __int64 *)(v15 + *(unsigned __int8 *)(v15 + 26));
    v146 = v20;
    v122.m128i_i32[1] = v26;
    v19 = v122;
    v21 = *v20;
    goto LABEL_25;
  }
  v18 = *a7;
  v19 = a7[1];
  v122.m128i_i64[1] = v19.m128i_i64[1];
  if ( !a7->m128i_i64[0] )
  {
    v112 = 1;
LABEL_133:
    v17 = _mm_cvtsi128_si32(v19);
    v29 = 0;
    v15 = _mm_srli_si128(v18, 8).m128i_u64[0];
    v113 = 1;
    v116 = v15;
    v16 = a7->m128i_i64[0];
    v114 = 2;
    v115 = v17;
    goto LABEL_94;
  }
  v20 = (unsigned __int64 *)(a7->m128i_i64[0] + *(unsigned __int8 *)(a7->m128i_i64[0] + 26));
  if ( !v20 )
  {
LABEL_59:
    v112 = 1;
    if ( v20 )
    {
      v17 = _mm_cvtsi128_si32(v19);
      v16 = a7->m128i_i64[0];
      v15 = _mm_srli_si128(v18, 8).m128i_u64[0];
      v115 = v17;
      goto LABEL_219;
    }
    goto LABEL_133;
  }
  v21 = *v20;
  if ( *v20 + v20[1] != *(_QWORD *)v12 )
  {
    if ( v21 <= *(_QWORD *)v12 )
    {
      v115 = v19.m128i_i32[0];
      v16 = a7->m128i_i64[0];
      v15 = _mm_srli_si128(v18, 8).m128i_u64[0];
      v116 = v15;
LABEL_25:
      v27 = v20[1];
      if ( v11 + v8 > v27 + v21 )
      {
        v20[1] = v11 + v8 - v21;
        v100 = v8 + v11 - (v27 + v21);
        v11 = v11 + v8 - v21;
        v125 = v100;
      }
      else
      {
        v125 = 0;
        v11 = v20[1];
      }
      v28 = *v20;
      v29 = v20;
      v30 = 0;
      v124 = *v20;
      v117 = v20[2];
      v114 = 2;
      v130 = v19;
      goto LABEL_28;
    }
    goto LABEL_59;
  }
  v114 = 2;
  v29 = 0;
  v15 = _mm_srli_si128(v18, 8).m128i_u64[0];
  v115 = v19.m128i_i32[0];
  v116 = v15;
  v16 = a7->m128i_i64[0];
LABEL_139:
  v81 = v20[1];
  if ( v81 + v21 < v8 )
    goto LABEL_142;
  v82 = v20[2];
  if ( *((_BYTE *)this + 56) )
  {
    if ( v82 != *((_QWORD *)v12 + 2) )
      goto LABEL_142;
  }
  else if ( v8 + v82 - v21 != *((_QWORD *)v12 + 2) )
  {
    goto LABEL_142;
  }
  v28 = *v20;
  v101 = v8 - (v81 + v21);
  v117 = v20[2];
  v29 = v20;
  v124 = *v20;
  v102 = v11 + v101;
  v11 += v101 + v81;
  v125 = v102;
  v20[1] = v11;
  if ( a7 )
  {
    *a7 = v13;
    a7[1] = v14;
  }
LABEL_143:
  v30 = v113;
  v36 = v18;
  v37 = v19;
  v128.m128i_i64[0] = v18.m128i_i64[0];
  v130 = v19;
  if ( v9 && !v113 )
  {
    v126 = v19.m128i_i32[0];
    v31 = _mm_srli_si128(v18, 8).m128i_u64[0];
    goto LABEL_37;
  }
LABEL_28:
  v31 = v15;
  if ( v15 )
  {
    if ( ((v115 - 1) & 0xFFFFFFFD) != 0 )
      goto LABEL_36;
    v32 = *(_QWORD *)(v15 + 16);
    if ( v32 )
    {
      for ( ; *(_QWORD *)(v32 + 8); v32 = *(_QWORD *)(v32 + 8) )
        ;
      v31 = v32;
    }
    else
    {
      v33 = *(_QWORD **)v15;
      if ( *(_QWORD *)(*(_QWORD *)v15 + 16LL) == v15 )
      {
        do
        {
          v34 = (_QWORD *)*v33;
          v35 = v33;
          v33 = v34;
        }
        while ( (_QWORD *)v34[2] == v35 );
      }
      else
      {
        v34 = *(_QWORD **)v15;
        v35 = (_QWORD *)v15;
      }
      v31 = 0;
      if ( (_QWORD *)v34[1] == v35 )
        v31 = (unsigned __int64)v34;
    }
    if ( v31 )
    {
LABEL_36:
      v128.m128i_i64[1] = v31;
      v128.m128i_i64[0] = v31;
      v36 = v128;
      v130.m128i_i32[0] = 1;
      v37 = v130;
      v126 = 1;
      v140 = *(unsigned __int8 *)(v31 + 27);
      v143 = v31 + *(unsigned __int8 *)(v31 + 26);
      epi16 = 0;
      v144 = *(unsigned __int16 *)(v31 + 30);
      v146 = (unsigned __int64 *)(v31 + *(unsigned __int8 *)(v31 + 26));
LABEL_37:
      v38 = 0;
      v39 = v126;
      v40 = v28 + v11;
      v132 = 0;
      while ( 1 )
      {
        if ( !v9 || v30 )
        {
          v41 = v146;
        }
        else
        {
          if ( v16 )
            v41 = (unsigned __int64 *)(v16 + *(unsigned __int8 *)(v16 + 26));
          else
            v41 = 0;
          v112 = 0;
        }
        v42 = *v41;
        if ( v40 < *v41 )
        {
LABEL_45:
          v15 = v116;
          goto LABEL_46;
        }
        v43 = v40 - v42;
        v44 = v41[1] + v42;
        if ( v44 <= v40 )
          v43 = v41[1];
        v125 -= v43;
        if ( *((_BYTE *)this + 56) )
        {
          if ( v117 != v41[2] )
            goto LABEL_45;
          v45 = v42 - v28;
        }
        else
        {
          v45 = v42 - v28;
          if ( v45 + v117 != v41[2] )
            goto LABEL_45;
        }
        if ( v29 )
        {
          if ( v44 > v40 )
            v29[1] += v44 - v40;
          v38 = 1;
          v71 = (struct _RTL_AVL_ENTRY *)_mm_srli_si128(v36, 8).m128i_u64[0];
          v132 = v71;
        }
        else
        {
          *v41 = v28;
          v103 = v40;
          v29 = v41;
          if ( v44 > v40 )
            v103 = v44;
          v41[1] = v103 - v28;
          if ( !*((_BYTE *)this + 56) )
            v41[2] -= v45;
          v71 = v132;
          if ( a7 )
          {
            *a7 = v36;
            a7[1] = v37;
          }
        }
        if ( !v31 )
          goto LABEL_187;
        if ( ((v39 - 1) & 0xFFFFFFFD) == 0 )
        {
          v72 = *(_QWORD *)(v31 + 16);
          if ( v72 )
          {
            for ( ; *(_QWORD *)(v72 + 8); v72 = *(_QWORD *)(v72 + 8) )
              ;
            v31 = v72;
          }
          else
          {
            v73 = *(_QWORD **)v31;
            if ( *(_QWORD *)(*(_QWORD *)v31 + 16LL) == v31 )
            {
              do
              {
                v74 = (_QWORD *)*v73;
                v75 = v73;
                v73 = v74;
              }
              while ( (_QWORD *)v74[2] == v75 );
            }
            else
            {
              v74 = *(_QWORD **)v31;
              v75 = (_QWORD *)v31;
            }
            v31 = 0;
            if ( (_QWORD *)v74[1] == v75 )
              v31 = (unsigned __int64)v74;
          }
          if ( !v31 )
            break;
        }
        v39 = 1;
        v140 = *(unsigned __int8 *)(v31 + 27);
        v130.m128i_i32[0] = 1;
        v37 = v130;
        v143 = v31 + *(unsigned __int8 *)(v31 + 26);
        epi16 = 0;
        v144 = *(unsigned __int16 *)(v31 + 30);
        v128.m128i_i64[1] = v31;
        v128.m128i_i64[0] = v31;
        v76 = 0;
        v36 = v128;
        v146 = (unsigned __int64 *)(v31 + *(unsigned __int8 *)(v31 + 26));
LABEL_114:
        if ( v38 )
        {
          ++*((_DWORD *)this + 11);
          DeleteNodeFromTree((CmsRangeMap *)((char *)this + 8), v71, 1u);
          --*((_DWORD *)this + 10);
          CmsAvlTableLite::FreeIndexEntry(v132);
          ++*((_DWORD *)this + 12);
          v28 = v124;
          v38 = 0;
        }
        v9 = v112;
        v30 = v113;
        if ( v76 < 0 )
          goto LABEL_45;
      }
      v36 = (__m128i)v128.m128i_u64[0];
LABEL_187:
      v76 = -1073741772;
      goto LABEL_114;
    }
  }
LABEL_46:
  if ( v29 )
  {
    v46 = 0;
    if ( v137 )
      *v137 = (struct _RTL_AVL_ENTRY *)(v29 - 4);
LABEL_49:
    if ( v138 )
      *v138 = v125;
    if ( v29 )
    {
      v47 = v139;
      if ( v139 )
      {
        *(_OWORD *)v139 = *(_OWORD *)v29;
        *((_QWORD *)v47 + 2) = v29[2];
      }
    }
    goto LABEL_54;
  }
  v49 = 0x8000;
  if ( v136 )
  {
    v50 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v136 + 4);
    v46 = 0;
    v133 = (__int64)v50;
    v51 = 0;
    v52 = v136;
    goto LABEL_63;
  }
  v83 = (__int16)Src[0];
  v84 = v134;
  v85 = ((LODWORD(Src[0]) + 7) & 0xFFFFFFF8) + 32;
  v86 = v85;
  if ( v85 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside2 )
  {
    if ( v85 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside1 )
    {
      v87 = (unsigned int *)(qword_140262458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v86 > *v87 )
      {
        v87 = 0;
        v88 = v86 + 16;
        goto LABEL_150;
      }
      if ( !*((_BYTE *)v87 + 8) )
      {
        if ( (int)*((_QWORD *)v87 + 11) > (int)HIDWORD(*((_QWORD *)v87 + 11)) )
        {
          v96 = _InterlockedDecrement((volatile signed __int32 *)v87 + 22);
          if ( v96 >= (int)v87[23] && v96 >= 0 )
          {
            v105 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v87 + 4);
            goto LABEL_208;
          }
          _InterlockedIncrement((volatile signed __int32 *)v87 + 22);
        }
LABEL_183:
        v88 = v87[1];
LABEL_150:
        Pool2 = ExAllocatePool2(66, v88, 1766871885);
        v90 = (_WORD *)Pool2;
        if ( (Pool2 & 0xF) == 0 )
        {
          if ( !Pool2 )
          {
LABEL_210:
            v49 = 0x2000;
            goto LABEL_211;
          }
LABEL_209:
          *(_QWORD *)v90 = v87;
          v90 += 8;
          goto LABEL_210;
        }
LABEL_252:
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      }
      v104 = (struct _NPAGED_LOOKASIDE_LIST *)(v87 + 16);
      if ( *((_BYTE *)v87 + 9) )
        v105 = ExAllocateFromNPagedLookasideList(v104);
      else
        v105 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v104);
LABEL_208:
      v90 = v105;
      if ( v105 )
        goto LABEL_209;
      goto LABEL_183;
    }
    KeGetCurrentProcessorNumberEx(0);
    v93 = qword_140262460;
    if ( v86 > *(unsigned int *)qword_140262460 )
    {
      v93 = 0;
      v94 = v86 + 16;
      goto LABEL_172;
    }
    if ( !*(_BYTE *)(qword_140262460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140262460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140262460 + 88)) )
      {
        v97 = _InterlockedDecrement((volatile signed __int32 *)(qword_140262460 + 88));
        if ( v97 >= *(_DWORD *)(v93 + 92) && v97 >= 0 )
        {
          v107 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v93 + 64));
          goto LABEL_213;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v93 + 88));
      }
LABEL_192:
      v94 = *(unsigned int *)(v93 + 4);
LABEL_172:
      v95 = ExAllocatePool2(66, v94, 1766871885);
      v90 = (_WORD *)v95;
      if ( (v95 & 0xF) != 0 )
        goto LABEL_252;
      if ( !v95 )
      {
LABEL_215:
        v49 = 0x4000;
LABEL_211:
        if ( v90 )
        {
          v133 = (__int64)v90;
          goto LABEL_185;
        }
        goto LABEL_194;
      }
LABEL_214:
      *(_QWORD *)v90 = v93;
      v90 += 8;
      goto LABEL_215;
    }
    v106 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140262460 + 64);
    if ( *(_BYTE *)(qword_140262460 + 9) )
      v107 = ExAllocateFromNPagedLookasideList(v106);
    else
      v107 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v106);
LABEL_213:
    v90 = v107;
    if ( v107 )
      goto LABEL_214;
    goto LABEL_192;
  }
  v133 = ExAllocatePool2(66, ((LODWORD(Src[0]) + 7) & 0xFFFFFFF8) + 32, 1766871885);
  v90 = (_WORD *)v133;
  if ( v133 )
  {
LABEL_185:
    v90[14] = 0;
    memmove(v90 + 16, Src[1], LODWORD(Src[0]));
    *((_BYTE *)v90 + 26) = 32;
    v52 = (struct _SmsPreAllocatedRow *)&v134;
    v90[14] |= v49;
    v51 = 1;
    v90[15] = v83;
    v50 = (struct _RTL_AVL_ENTRY *)v133;
    *((_BYTE *)v90 + 27) = v84;
    v46 = 0;
LABEL_63:
    v53 = a2;
    v54 = 0;
    v55 = *((unsigned __int8 *)a2 + 96);
    v56 = 5;
    if ( (*(_DWORD *)a2 & 0x8000LL) == 0 )
      v56 = 2;
    if ( v55 < v56 )
    {
      v57 = v55 + 1;
      *((_BYTE *)a2 + 96) = v57;
      if ( v57 <= 2u )
        v58 = (char *)a2 - 24;
      else
        v58 = (char *)a2 + 784;
      v59 = &v58[40 * v57];
      *(_QWORD *)v59 = v52;
      *((_WORD *)v59 + 16) = 0;
      *((_QWORD *)v59 + 1) = &CmsRangeMap::PropertyDef;
      *((_QWORD *)v59 + 2) = &off_140200A10;
      LOBYTE(v55) = *((_BYTE *)a2 + 96);
    }
    if ( v51 )
    {
      if ( (unsigned __int8)v55 <= 2u )
        v60 = (char *)a2 + 9;
      else
        v60 = (char *)a2 + 817;
      v60[40 * (unsigned __int8)v55] = 1;
    }
    v61 = *((unsigned __int8 *)a2 + 96);
    v62 = (struct _RTL_AVL_ENTRY **)((char *)a2 + 40 * v61);
    if ( (unsigned __int8)v61 > 2u )
      v62 += 101;
    v63 = this;
    *v62 = v50;
    v64 = (unsigned __int64 *)((char *)this + 24);
    if ( v15 )
    {
      if ( !v16 )
      {
        v65 = v115;
        v54 = v15;
        v114 = v115;
        goto LABEL_128;
      }
      if ( *v64 )
      {
        v91 = **((_QWORD **)v52 + 1);
        while ( 1 )
        {
          while ( 1 )
          {
            v92 = v16 ? (unsigned __int64 *)(v16 + *(unsigned __int8 *)(v16 + 26)) : 0LL;
            if ( v91 < *v92 )
              break;
            if ( v91 < v92[1] + *v92 )
              goto LABEL_205;
            if ( !*(_QWORD *)(v16 + 16) )
              goto LABEL_162;
            v16 = *(_QWORD *)(v16 + 16);
          }
          if ( !*(_QWORD *)(v16 + 8) )
            break;
          v16 = *(_QWORD *)(v16 + 8);
        }
        v54 = v16;
        v65 = 2;
LABEL_80:
        v16 = 0;
        goto LABEL_81;
      }
    }
    else
    {
      v16 = *v64;
      if ( *v64 )
      {
        v98 = **((_QWORD **)v52 + 1);
        while ( 1 )
        {
          while ( 1 )
          {
            v99 = v16 ? (unsigned __int64 *)(v16 + *(unsigned __int8 *)(v16 + 26)) : 0LL;
            if ( v98 >= *v99 )
              break;
            if ( !*(_QWORD *)(v16 + 8) )
            {
              v54 = v16;
              v65 = 2;
              goto LABEL_79;
            }
            v16 = *(_QWORD *)(v16 + 8);
          }
          if ( v98 < v99[1] + *v99 )
            break;
          if ( !*(_QWORD *)(v16 + 16) )
          {
LABEL_162:
            v54 = v16;
            v65 = 3;
            goto LABEL_79;
          }
          v16 = *(_QWORD *)(v16 + 16);
        }
LABEL_205:
        v65 = 1;
        v54 = v16;
        v114 = 1;
LABEL_81:
        if ( v16 )
        {
          v66 = *((_DWORD *)this + 12);
          --*((_BYTE *)a2 + 96);
          v120.m128i_i64[0] = v16;
          v120.m128i_i64[1] = v16;
          v122.m128i_i32[0] = 3;
          v122.m128i_i32[1] = v66;
          if ( v50 && v51 )
            CmsAvlTableLite::FreeIndexEntry(v50);
          v46 = -1073741771;
LABEL_84:
          v19 = v122;
          v18 = v120;
          goto LABEL_85;
        }
LABEL_128:
        ++*((_DWORD *)this + 12);
        if ( v65 != 1 )
        {
          v79 = (_OWORD *)((__int64 (__fastcall *)(char *, _QWORD, struct CmsTransactionCore *))qword_140262628)(
                            (char *)this + 8,
                            0,
                            a2);
          v63 = this;
          if ( v79 )
          {
            *v79 = 0;
            *(_OWORD *)((char *)v79 + 10) = 0;
            ++*((_DWORD *)this + 10);
            if ( v114 )
            {
              if ( v114 == 2 )
                *(_QWORD *)(v54 + 8) = v79;
              else
                *(_QWORD *)(v54 + 16) = v79;
              *(_QWORD *)v79 = v54;
              *((_BYTE *)this + 32) = -1;
              for ( i = *(_QWORD *)v79; ; v54 = i )
              {
                v109 = *(_QWORD *)(i + 8) == (_QWORD)v79;
                v110 = -1;
                v111 = *(_BYTE *)(v54 + 24);
                if ( !v109 )
                  v110 = 1;
                if ( v111 )
                  break;
                i = *(_QWORD *)v54;
                v79 = (_OWORD *)v54;
                *(_BYTE *)(v54 + 24) = v110;
              }
              v50 = (struct _RTL_AVL_ENTRY *)v133;
              if ( v111 == v110 )
              {
                RebalanceNode((struct _RTL_AVL_ENTRY *)v54);
                v63 = this;
              }
              else
              {
                *(_BYTE *)(v54 + 24) = 0;
              }
            }
            else
            {
              *v64 = (unsigned __int64)v79;
              *(_QWORD *)v79 = (char *)this + 8;
            }
          }
          v53 = a2;
        }
        v80 = *((_DWORD *)v63 + 12);
        v16 = (unsigned __int64)v50;
        --*((_BYTE *)v53 + 96);
        v122.m128i_i32[1] = v80;
        v120.m128i_i64[0] = (__int64)v50;
        v120.m128i_i64[1] = (__int64)v50;
        v122.m128i_i32[0] = 1;
        goto LABEL_84;
      }
    }
    v65 = 0;
LABEL_79:
    v114 = v65;
    goto LABEL_80;
  }
LABEL_194:
  v46 = -1073741670;
LABEL_85:
  if ( a7 )
  {
    *a7 = v18;
    a7[1] = v19;
  }
  if ( v136 && v46 >= 0 )
    *((_QWORD *)v136 + 4) = 0;
  if ( v137 )
    *v137 = (struct _RTL_AVL_ENTRY *)v16;
  if ( v46 >= 0 )
    goto LABEL_49;
LABEL_54:
  if ( (v148 & 1) != 0 && P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v46;
}

```

## disassembly

```asm
0x1400760d0  push    rbp
0x1400760d2  push    rbx
0x1400760d3  push    rdi
0x1400760d4  push    r12
0x1400760d6  push    r13
0x1400760d8  push    r14
0x1400760da  push    r15
0x1400760dc  lea     rbp, [rsp-0C0h]
0x1400760e4  sub     rsp, 1C0h
0x1400760eb  mov     rax, cs:__security_cookie
0x1400760f2  xor     rax, rsp
0x1400760f5  mov     [rbp+0F0h+var_80], rax
0x1400760f9  mov     rax, [rbp+0F0h+arg_28]
0x140076100  xorps   xmm0, xmm0
0x140076103  mov     r14, [r8]
0x140076106  xor     r11b, r11b
0x140076109  mov     r10, [r8+10h]
0x14007610d  mov     rdi, r9
0x140076110  mov     r15, [r8+8]
0x140076114  mov     rbx, r8
0x140076117  mov     [rbp+0F0h+var_E8], rax
0x14007611b  xorps   xmm3, xmm3
0x14007611e  mov     rax, [rbp+0F0h+arg_38]
0x140076125  xorps   xmm4, xmm4
0x140076128  mov     [rbp+0F0h+var_F8], rax
0x14007612c  lea     rax, [rbp+0F0h+var_A0]
0x140076130  movups  xmmword ptr [rbp+0F0h+var_148], xmm0
0x140076134  mov     [rbp+0F0h+P], rax
0x140076138  pextrw  eax, xmm0, 2
0x14007613d  movups  [rbp+0F0h+var_120], xmm0
0x140076141  mov     [rbp+0F0h+var_100], r9
0x140076145  mov     r9, rcx
0x140076148  movss   [rbp+0F0h+var_D0], xmm0
0x14007614d  mov     [rbp+0F0h+var_CC], ax
0x140076151  movzx   eax, word ptr [rbp+0F0h+var_148+6]
0x140076155  psrldq  xmm0, 8
0x14007615a  mov     [rbp+0F0h+var_170], rdx
0x14007615e  mov     rdx, [rbp+0F0h+arg_20]
0x140076165  mov     [rsp+1F0h+var_190], rcx
0x14007616a  mov     rcx, [rbp+0F0h+arg_30]
0x140076171  movq    [rbp+0F0h+var_C8], xmm0
0x140076176  xorps   xmm0, xmm0
0x140076179  mov     [rbp+0F0h+var_CA], ax
0x14007617d  mov     eax, dword ptr [rbp+0F0h+var_E8+4]
0x140076180  mov     [rbp+0F0h+var_BC], eax
0x140076183  mov     [rbp+0F0h+var_128], rcx
0x140076187  mov     [rbp+0F0h+var_F0], rdx
0x14007618b  mov     [rbp+0F0h+var_A4], 20h ; ' '
0x140076192  mov     [rbp+0F0h+var_C0], 0
0x140076199  mov     [rbp+0F0h+var_B8], 0
0x1400761a1  mov     [rbp+0F0h+var_A8], 0
0x1400761a5  mov     [rsp+1F0h+var_188], r14
0x1400761aa  mov     [rsp+1F0h+var_1B8], r10
0x1400761af  mov     [rsp+1F0h+var_1D0], r11b
0x1400761b4  mov     [rsp+1F0h+var_1CF], r11b
0x1400761b9  movups  [rsp+1F0h+var_1B0], xmm0
0x1400761be  movups  [rsp+1F0h+var_1A0], xmm0
0x1400761c3  movups  xmmword ptr [rbp+0F0h+var_148], xmm0
0x1400761c7  test    rdx, rdx
0x1400761ca  jnz     loc_140076E84
0x1400761d0  mov     [rsp+1F0h+var_180], r15
0x1400761d5  test    rdi, rdi
0x1400761d8  jnz     loc_1400768F4
0x1400761de  mov     qword ptr [rbp+0F0h+var_120+8], rbx
0x1400761e2  mov     dword ptr [rbp+0F0h+var_120], 10h
0x1400761e9  mov     [rbp+0F0h+Src+8], rbx
0x1400761ed  mov     dword ptr [rbp+0F0h+Src], 18h
0x1400761f4  mov     [rsp+1F0h+arg_10], rsi
0x1400761fc  mov     r13d, 2
0x140076202  movaps  [rsp+1F0h+var_40], xmm6
0x14007620a  mov     r12d, 1
0x140076210  movaps  [rsp+1F0h+var_50], xmm7
0x140076218  movaps  [rsp+1F0h+var_60], xmm8
0x140076221  movaps  [rsp+1F0h+var_70], xmm9
0x14007622a  mov     [rsp+1F0h+var_1CC], r13d
0x14007622f  test    rcx, rcx
0x140076232  jnz     short loc_140076276
0x140076234  mov     rdi, [r9+18h]
0x140076238  mov     [rsp+1F0h+var_1C0], rdi
0x14007623d  test    rdi, rdi
0x140076240  jnz     loc_1400762E2
0x140076246  xor     esi, esi
0x140076248  xor     r11d, r11d
0x14007624b  mov     eax, [r9+30h]
0x14007624f  mov     dword ptr [rsp+1F0h+var_1A0+4], eax
0x140076253  mov     qword ptr [rsp+1F0h+var_1B0], rsi
0x140076258  mov     qword ptr [rsp+1F0h+var_1B0+8], rdi
0x14007625d  movups  xmm6, [rsp+1F0h+var_1B0]
0x140076262  mov     dword ptr [rsp+1F0h+var_1A0], r11d
0x140076267  movups  xmm7, [rsp+1F0h+var_1A0]
0x14007626c  mov     [rsp+1F0h+var_1C8], r11d
0x140076271  jmp     loc_140076EEB
0x140076276  movups  xmm6, xmmword ptr [rcx]
0x140076279  movups  xmm7, xmmword ptr [rcx+10h]
0x14007627d  mov     rcx, [rcx]
0x140076280  movups  [rsp+1F0h+var_1B0], xmm6
0x140076285  movups  [rsp+1F0h+var_1A0], xmm7
0x14007628a  test    rcx, rcx
0x14007628d  jz      loc_140076996
0x140076293  movzx   edx, byte ptr [rcx+1Ah]
0x140076297  add     rdx, rcx
0x14007629a  jz      loc_1400765A1
0x1400762a0  mov     r8, [rdx]
0x1400762a3  mov     rcx, [rdx+8]
0x1400762a7  mov     r9, [rbx]
0x1400762aa  add     rcx, r8
0x1400762ad  cmp     rcx, r9
0x1400762b0  jz      loc_140076E90
0x1400762b6  cmp     r8, r9
0x1400762b9  ja      loc_1400765A1
0x1400762bf  movdqa  xmm0, xmm6
0x1400762c3  movss   [rsp+1F0h+var_1C8], xmm7
0x1400762c9  psrldq  xmm0, 8
0x1400762ce  movq    rsi, xmm6
0x1400762d3  movq    rdi, xmm0
0x1400762d8  mov     [rsp+1F0h+var_1C0], rdi
0x1400762dd  jmp     loc_14007639B
0x1400762e2  mov     r8, [r8]
0x1400762e5  test    rdi, rdi
0x1400762e8  jz      loc_140076C27
0x1400762ee  movzx   eax, byte ptr [rdi+1Ah]
0x1400762f2  add     rax, rdi
0x1400762f5  mov     rdx, [rax]
0x1400762f8  cmp     r8, rdx
0x1400762fb  jb      short loc_140076323
0x1400762fd  mov     rax, [rax+8]
0x140076301  mov     rsi, rdi
0x140076304  add     rax, rdx
0x140076307  cmp     r8, rax
0x14007630a  jb      short loc_14007633A
0x14007630c  mov     rax, [rdi+10h]
0x140076310  test    rax, rax
0x140076313  jz      loc_140076594
0x140076319  mov     rdi, rax
0x14007631c  mov     [rsp+1F0h+var_1C0], rax
0x140076321  jmp     short loc_1400762E5
0x140076323  mov     rax, [rdi+8]
0x140076327  test    rax, rax
0x14007632a  jz      loc_140076740
0x140076330  mov     rdi, rax
0x140076333  mov     [rsp+1F0h+var_1C0], rax
0x140076338  jmp     short loc_1400762E5
0x14007633a  mov     qword ptr [rsp+1F0h+var_1B0], rdi
0x14007633f  mov     qword ptr [rsp+1F0h+var_1B0+8], rdi
0x140076344  mov     [rsp+1F0h+var_1C0], rdi
0x140076349  mov     [rsp+1F0h+var_1C8], r12d
0x14007634e  mov     dword ptr [rsp+1F0h+var_1A0], r12d
0x140076353  movups  xmm6, [rsp+1F0h+var_1B0]
0x140076358  test    rdi, rdi
0x14007635b  jz      loc_140076EDB
0x140076361  movzx   eax, byte ptr [rdi+1Bh]
0x140076365  mov     [rbp+0F0h+var_D0], eax
0x140076368  movzx   eax, byte ptr [rdi+1Ah]
0x14007636c  add     rax, rdi
0x14007636f  mov     [rbp+0F0h+var_C8], rax
0x140076373  xor     eax, eax
0x140076375  mov     [rbp+0F0h+var_CC], ax
0x140076379  movzx   eax, word ptr [rdi+1Eh]
0x14007637d  mov     [rbp+0F0h+var_C0], eax
0x140076380  movzx   edx, byte ptr [rdi+1Ah]
0x140076384  mov     eax, [r9+30h]
0x140076388  add     rdx, rdi
0x14007638b  mov     [rbp+0F0h+var_B8], rdx
0x14007638f  mov     dword ptr [rsp+1F0h+var_1A0+4], eax
0x140076393  movups  xmm7, [rsp+1F0h+var_1A0]
0x140076398  mov     r8, [rdx]
0x14007639b  mov     rax, [rdx+8]
0x14007639f  lea     rcx, [r15+r14]
0x1400763a3  lea     r9, [rax+r8]
0x1400763a7  cmp     rcx, r9
0x1400763aa  ja      loc_140076EBE
0x1400763b0  mov     [rsp+1F0h+var_180], 0
0x1400763b9  mov     r15, rax
0x1400763bc  mov     rbx, [rdx]
0x1400763bf  mov     r13, rdx
0x1400763c2  mov     rcx, [rdx+10h]
0x1400763c6  xor     r8b, r8b
0x1400763c9  mov     [rsp+1F0h+var_188], rbx
0x1400763ce  mov     [rsp+1F0h+var_1B8], rcx
0x1400763d3  movups  [rbp+0F0h+var_168], xmm6
0x1400763d7  mov     [rsp+1F0h+var_1CC], 2
0x1400763df  movups  [rbp+0F0h+var_158], xmm7
0x1400763e3  mov     r14, rdi
0x1400763e6  test    rdi, rdi
0x1400763e9  jz      loc_1400764F4
0x1400763ef  mov     eax, [rsp+1F0h+var_1C8]
0x1400763f3  dec     eax
0x1400763f5  test    eax, 0FFFFFFFDh
0x1400763fa  jnz     short loc_140076439
0x1400763fc  mov     rax, [rdi+10h]
0x140076400  test    rax, rax
0x140076403  jnz     loc_1400768DA
0x140076409  mov     rax, [rdi]
0x14007640c  cmp     [rax+10h], rdi
0x140076410  jnz     loc_1400768AA
0x140076416  mov     rcx, [rax]
0x140076419  mov     rdx, rax
0x14007641c  mov     rax, rcx
0x14007641f  cmp     [rcx+10h], rdx
0x140076423  jz      short loc_140076416
0x140076425  xor     r14d, r14d
0x140076428  cmp     [rcx+8], rdx
0x14007642c  cmovz   r14, rcx
0x140076430  test    r14, r14
0x140076433  jz      loc_1400764F4
0x140076439  mov     r12d, 1
0x14007643f  mov     qword ptr [rbp+0F0h+var_168+8], r14
0x140076443  mov     eax, r12d
0x140076446  mov     qword ptr [rbp+0F0h+var_168], r14
0x14007644a  movups  xmm8, [rbp+0F0h+var_168]
0x14007644f  mov     dword ptr [rbp+0F0h+var_158], eax
0x140076452  movups  xmm9, [rbp+0F0h+var_158]
0x140076457  mov     [rsp+1F0h+var_178], eax
0x14007645b  movzx   eax, byte ptr [r14+1Bh]
0x140076460  mov     [rbp+0F0h+var_D0], eax
0x140076463  movzx   eax, byte ptr [r14+1Ah]
0x140076468  add     rax, r14
0x14007646b  mov     [rbp+0F0h+var_C8], rax
0x14007646f  xor     eax, eax
0x140076471  mov     [rbp+0F0h+var_CC], ax
0x140076475  movzx   eax, word ptr [r14+1Eh]
0x14007647a  mov     [rbp+0F0h+var_C0], eax
0x14007647d  movzx   eax, byte ptr [r14+1Ah]
0x140076482  add     rax, r14
0x140076485  mov     [rbp+0F0h+var_B8], rax
0x140076489  mov     r9, [rbp+0F0h+var_148+8]
0x14007648d  xor     r10b, r10b
0x140076490  mov     edi, [rsp+1F0h+var_178]
0x140076494  add     r15, rbx
0x140076497  mov     [rbp+0F0h+var_148], r9
0x14007649b  test    r11b, r11b
0x14007649e  jnz     loc_1400768B5
0x1400764a4  mov     r8, [rbp+0F0h+var_B8]
0x1400764a8  mov     rdx, [r8]
0x1400764ab  cmp     r15, rdx
0x1400764ae  jb      short loc_1400764EF
0x1400764b0  mov     rcx, [r8+8]
0x1400764b4  mov     rax, r15
0x1400764b7  mov     r11, [rsp+1F0h+var_190]
0x1400764bc  sub     rax, rdx
0x1400764bf  lea     r9, [rcx+rdx]
0x1400764c3  cmp     r9, r15
0x1400764c6  cmovbe  rax, rcx
0x1400764ca  sub     [rsp+1F0h+var_180], rax
0x1400764cf  cmp     byte ptr [r11+38h], 0
0x1400764d4  mov     rax, [rsp+1F0h+var_1B8]
0x1400764d9  jnz     loc_140076F5A
0x1400764df  sub     rdx, rbx
0x1400764e2  add     rax, rdx
0x1400764e5  cmp     rax, [r8+10h]
0x1400764e9  jz      loc_1400767BF
0x1400764ef  mov     rdi, [rsp+1F0h+var_1C0]
0x1400764f4  movaps  xmm9, [rsp+1F0h+var_70]
0x1400764fd  movaps  xmm8, [rsp+1F0h+var_60]
0x140076506  test    r13, r13
0x140076509  jz      loc_1400765D1
0x14007650f  mov     rcx, [rbp+0F0h+var_F8]
0x140076513  xor     ebx, ebx
0x140076515  test    rcx, rcx
0x140076518  jnz     loc_14007708E
0x14007651e  mov     rax, [rbp+0F0h+var_F0]
0x140076522  test    rax, rax
0x140076525  jnz     loc_14007709A
0x14007652b  test    r13, r13
0x14007652e  jz      short loc_14007653D
0x140076530  mov     rax, [rbp+0F0h+var_E8]
0x140076534  test    rax, rax
0x140076537  jnz     loc_1400770A7
0x14007653d  test    [rbp+0F0h+var_A8], 1
0x140076541  jz      short loc_14007655A
0x140076543  mov     rcx, [rbp+0F0h+P]; P
0x140076547  test    rcx, rcx
0x14007654a  jz      short loc_14007655A
0x14007654c  xor     edx, edx; Tag
0x14007654e  call    cs:__imp_ExFreePoolWithTag
0x140076555  nop     dword ptr [rax+rax+00h]
0x14007655a  movaps  xmm7, [rsp+1F0h+var_50]
0x140076562  mov     eax, ebx
0x140076564  movaps  xmm6, [rsp+1F0h+var_40]
0x14007656c  mov     rsi, [rsp+1F0h+arg_10]
0x140076574  mov     rcx, [rbp+0F0h+var_80]
0x140076578  xor     rcx, rsp; StackCookie
0x14007657b  call    __security_check_cookie
0x140076580  add     rsp, 1C0h
0x140076587  pop     r15
0x140076589  pop     r14
0x14007658b  pop     r13
0x14007658d  pop     r12
0x14007658f  pop     rdi
0x140076590  pop     rbx
0x140076591  pop     rbp
0x140076592  retn
0x140076594  xor     esi, esi
0x140076596  mov     r11d, 3
0x14007659c  jmp     loc_14007624B
0x1400765a1  mov     [rsp+1F0h+var_1D0], r12b
0x1400765a6  test    rdx, rdx
0x1400765a9  jz      loc_14007699B
0x1400765af  movd    r11d, xmm7
0x1400765b4  movdqa  xmm0, xmm6
  ... truncated ...
```
