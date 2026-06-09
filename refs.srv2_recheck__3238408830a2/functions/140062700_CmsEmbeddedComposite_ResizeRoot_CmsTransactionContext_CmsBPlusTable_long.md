# CmsEmbeddedComposite::ResizeRoot(CmsTransactionContext &,CmsBPlusTable &,long)

- ea: `0x140062700`
- end: `0x1400639d7`
- name: `?ResizeRoot@CmsEmbeddedComposite@@QEAAJAEAVCmsTransactionContext@@AEAVCmsBPlusTable@@J@Z`
- size: `4823`
- prototype: `int(CmsEmbeddedComposite *__hidden this, struct CmsTransactionContext *, struct CmsBPlusTable *, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140014d60`
- `0x140062690`

## callees

- `0x140012c34`
- `0x140016440`
- `0x14003bf40`
- `0x14003fb10`
- `0x14005c510`
- `0x140062700`
- `0x14007d820`
- `0x140091570`
- `0x140097e80`
- `0x1400cb544`
- `0x1400cbe48`
- `0x1400ceda0`
- `0x1400cfe9c`
- `0x1400d1e34`
- `0x140158de8`
- `0x1401f4090`
- `0x1401f4100`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140063478`
- `ntoskrnl!KdDebuggerEnabled` at `0x140063759`
- `ntoskrnl!KdDebuggerEnabled` at `0x14006376f`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400637ae`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400637c4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140063898`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140063898`
- `ntoskrnl!ExAllocatePool2` at `0x140062baa`
- `ntoskrnl!ExAllocatePool2` at `0x140062d3e`
- `ntoskrnl!ExAllocatePool2` at `0x140063329`
- `ntoskrnl!ExAllocatePool2` at `0x140062baa`
- `ntoskrnl!ExAllocatePool2` at `0x140062d3e`
- `ntoskrnl!ExAllocatePool2` at `0x140063329`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400632eb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400632eb`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fe3d4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fe3d4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400638b5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400638b5`
- `ntoskrnl!ExReleasePushLockEx` at `0x140063551`
- `ntoskrnl!ExReleasePushLockEx` at `0x140063551`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062dbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063794`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062dbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063794`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140063511`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140063511`

## string_xrefs

- `0x140063340`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsEmbeddedComposite::ResizeRoot(
        CmsEmbeddedComposite *this,
        struct CmsTransactionContext *a2,
        struct CmsBPlusTable *a3,
        int a4)
{
  struct CmsTransactionContext *v4; // rdi
  int v5; // edx
  CmsEmbeddedComposite *v6; // r12
  bool v9; // zf
  int v10; // ecx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  unsigned __int8 v16; // bl
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  unsigned __int8 v19; // cl
  unsigned int v20; // edx
  int v21; // r8d
  bool v22; // sf
  unsigned int v23; // r8d
  _DWORD *v24; // rdx
  __int64 v25; // rax
  unsigned __int64 v26; // rax
  unsigned int *v27; // rcx
  unsigned int v28; // eax
  CmsEmbeddedComposite *v29; // rcx
  unsigned int v30; // edx
  int v31; // esi
  struct SmsPage *v32; // r8
  CmsVolume *v33; // rcx
  unsigned __int8 v35; // cl
  unsigned __int8 v36; // al
  struct SmsPage *v37; // rsi
  char *v38; // rbx
  size_t v39; // r15
  char *v40; // rsi
  __int64 v41; // r9
  __int16 v42; // r10
  size_t v43; // r12
  int v44; // ecx
  char v45; // dl
  unsigned __int16 v46; // ax
  CmsRowWithBuffer *v47; // r11
  unsigned int v48; // eax
  __int64 v49; // rax
  unsigned __int64 v50; // kr00_8
  __int64 Pool2; // rax
  __int64 v52; // rcx
  __int16 v53; // r10
  size_t v54; // r8
  unsigned __int16 v55; // r9
  CmsRowWithBuffer *v56; // r15
  int v57; // ecx
  CmsRowWithBuffer *v58; // r8
  __int64 v59; // r9
  char *v60; // r12
  unsigned int v61; // esi
  char *v62; // rbx
  int v63; // r15d
  unsigned int v64; // r15d
  unsigned __int64 v65; // rax
  struct _SmsRedoMarker *v66; // rax
  struct _SmsRedoMarker *v67; // rbx
  char *v68; // rsi
  CmsRowWithBuffer *v69; // rdx
  struct _SmsRedoMarker *v70; // rax
  char v71; // cl
  void *v72; // rcx
  CmsVolume *v73; // r12
  struct SmsPage *v74; // r14
  struct SmsPage *v75; // rbx
  unsigned int v76; // r15d
  unsigned int *v77; // r15
  __int64 v78; // rbx
  CmsEmbeddedComposite *v79; // rsi
  _DWORD *v80; // rbx
  _DWORD *v81; // rdx
  unsigned int v82; // eax
  _DWORD *v83; // rcx
  _DWORD **v84; // rdx
  unsigned int v85; // r8d
  char *v86; // rbx
  __int64 v87; // r10
  int v88; // edx
  char v89; // r9
  char v90; // r11
  __int64 v91; // rsi
  __int64 v92; // rax
  unsigned int v93; // r15d
  int v94; // r13d
  __int64 v95; // rdi
  unsigned int v96; // ecx
  __int64 v97; // rax
  __int64 v98; // r14
  unsigned int *v99; // rdx
  char *v100; // rsi
  unsigned int v101; // eax
  __int64 v102; // rdx
  __int16 v103; // ax
  char *v104; // rax
  __int16 v105; // ax
  unsigned int v106; // ecx
  unsigned int v107; // ecx
  unsigned int v108; // ecx
  __int16 v109; // bx
  __int64 v110; // r14
  __int16 v111; // r8
  int v112; // eax
  char v113; // r15
  struct SmsPage *v114; // rbx
  __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // rax
  __int64 v118; // r8
  signed __int32 v119; // eax
  struct SmsPage *v120; // r8
  int v121; // eax
  __int64 v122; // rsi
  __int64 v123; // r9
  __int64 v124; // rdx
  __int64 v125; // rax
  CmsVolume *v126; // r13
  unsigned int v127; // r9d
  struct SmsPage *v128; // r15
  struct SmsPage *v129; // rbx
  unsigned int v130; // r12d
  __int64 v131; // r10
  struct _SmsRedoMarker *v132; // rcx
  __int16 v133; // bx
  CmsTxMemLog *v134; // rax
  __int64 v135; // rax
  int v136; // ecx
  struct _SmsRedoMarker *v137; // rbx
  unsigned int v138; // r12d
  __int64 *v139; // r8
  __int64 *v140; // r9
  _DWORD *v141; // rcx
  int v142; // eax
  _DWORD *v143; // rcx
  int v144; // eax
  __int64 v145; // rax
  __int32 v146; // rdx^4
  __m128i v147; // rt0
  unsigned __int8 v148; // tt
  CmsTxMemLog *v149; // rax
  struct CmsDurableLog *v150; // rdx
  void *v151; // rcx
  __int64 v152; // r11
  unsigned int *v153; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v154; // rcx
  _DWORD *v155; // rax
  __int64 v156; // rax
  signed __int64 v157; // rax
  int v158; // ecx
  __int64 v159; // [rsp+40h] [rbp-C0h]
  CmsRowWithBuffer *v160; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v161; // [rsp+68h] [rbp-98h]
  char v162; // [rsp+6Ah] [rbp-96h]
  struct _SmsRedoMarker *v163; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v164; // [rsp+78h] [rbp-88h]
  unsigned int v165; // [rsp+7Ch] [rbp-84h]
  __int64 v166; // [rsp+80h] [rbp-80h]
  _QWORD v167[3]; // [rsp+88h] [rbp-78h] BYREF
  __int16 v168; // [rsp+A0h] [rbp-60h]
  char v169; // [rsp+A2h] [rbp-5Eh]
  unsigned __int8 v170; // [rsp+A3h] [rbp-5Dh]
  unsigned __int8 v171; // [rsp+A4h] [rbp-5Ch]
  __int64 v172; // [rsp+A8h] [rbp-58h]
  int v173; // [rsp+B0h] [rbp-50h]
  int v174; // [rsp+B8h] [rbp-48h] BYREF
  struct SmsPage *v175[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v176; // [rsp+D0h] [rbp-30h]
  __int64 v177; // [rsp+E0h] [rbp-20h]
  int v178; // [rsp+E8h] [rbp-18h] BYREF
  __int16 v179; // [rsp+ECh] [rbp-14h]
  CmsTxMemLog *v180; // [rsp+F0h] [rbp-10h]
  __int64 v181; // [rsp+F8h] [rbp-8h]
  __m128i v182; // [rsp+100h] [rbp+0h]
  __int128 v183; // [rsp+110h] [rbp+10h]
  int v184; // [rsp+124h] [rbp+24h]
  CmsEmbeddedComposite *v185; // [rsp+170h] [rbp+70h]
  char v187; // [rsp+188h] [rbp+88h]
  unsigned int v188; // [rsp+188h] [rbp+88h]

  v185 = this;
  v177 = 0;
  v4 = a2;
  v5 = *((_DWORD *)a2 + 56);
  v6 = this;
  v9 = !_BitScanForward((unsigned int *)&this, ~(_BYTE)v5 & 0x3F);
  *(_OWORD *)v175 = 0;
  v174 = v10;
  v176 = 0;
  if ( v9 )
  {
    v160 = 0;
  }
  else
  {
    v11 = 1 << (char)this;
    v12 = 80LL * (_QWORD)this;
    *((_DWORD *)v4 + 56) = v5 | v11;
    v13 = v184;
    v183 = 0;
    v160 = (struct CmsTransactionContext *)((char *)v4 + v12 + 2816);
    *(_OWORD *)v160 = 0;
    *(_DWORD *)((char *)v4 + v12 + 2832) = 0;
    *(_DWORD *)((char *)v4 + v12 + 2836) = v13;
    *(_QWORD *)((char *)v4 + v12 + 2840) = 0;
  }
  v14 = *(_QWORD *)v4;
  v15 = *(_QWORD *)v4;
  v168 = 0;
  v169 = 0;
  v173 = 0;
  v181 = v15 & 0x2000000000LL;
  if ( (v14 & 0x200000) != 0 && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  ++*((_WORD *)v4 + 106);
  v16 = *((_BYTE *)v4 + 132);
  v173 = *((unsigned __int16 *)v4 + 106);
  v167[0] = *((_QWORD *)v4 + 18);
  v17 = (_QWORD *)(*((_QWORD *)v4 + 52) + 8LL);
  v169 = 0;
  v18 = (_QWORD *)*v17;
  v9 = *v17 == 0;
  v172 = v14;
  v171 = v16;
  if ( v9 )
    v18 = v17;
  HIBYTE(v168) = 0;
  v167[2] = *((_QWORD *)v4 + 25);
  v167[1] = v18;
  v19 = *((_BYTE *)v4 + 131);
  *(_QWORD *)v4 = v14 & 0xFFFFEFFFFFFFFFFFuLL;
  v170 = v19;
  while ( 1 )
  {
    if ( v19 >= 0xDu )
      goto LABEL_10;
    if ( !*((_QWORD *)v4 + v19 + 70) )
      break;
    ++v19;
  }
  *((_BYTE *)v4 + 131) = v19;
LABEL_10:
  while ( v16 < 0xDu )
  {
    if ( !*((_QWORD *)v4 + v16 + 53) )
    {
      *((_BYTE *)v4 + 132) = v16;
      break;
    }
    ++v16;
  }
  if ( *((_BYTE *)v4 + 131) < *((_BYTE *)v4 + 130) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  *(_QWORD *)v4 |= 0x2000000000uLL;
  v20 = 3;
  *((_BYTE *)v4 + 130) = *((_BYTE *)v4 + 131);
  v21 = *((_DWORD *)v6 + 7);
  v22 = a4 + v21 < 0;
  v23 = a4 + v21;
  v164 = v23;
  if ( v22 )
  {
    v31 = -1073741811;
    goto LABEL_29;
  }
  if ( (a4 & 7) != 0 )
  {
LABEL_100:
    v31 = -1073741823;
    goto LABEL_29;
  }
  v24 = (_DWORD *)*((_QWORD *)a3 + 3);
  if ( (v24[11] & 0x1000) != 0 )
  {
    v25 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a3 + 14) + 16LL) + 3536LL);
    if ( *(_WORD *)(v25 + 8) )
      v26 = (unsigned __int64)*(unsigned int *)(v25 + 16) >> ((unsigned __int8)*(_WORD *)(v25 + 20)
                                                            - *(_BYTE *)(v25 + 12));
    else
      LODWORD(v26) = 0;
    v27 = v24 + 6;
    v28 = (((v26 + 67) & 0xFFFFFFF8) + v24[7] + 87) & 0xFFFFFFF8;
  }
  else
  {
    v28 = v24[6];
    v27 = v24 + 6;
    if ( !v28 )
      v28 = *(_DWORD *)(*((_QWORD *)v6 + 2) + 3332LL) - 80;
  }
  if ( v23 < v28 )
    goto LABEL_99;
  if ( (v24[11] & 0x1000) != 0 )
  {
    v29 = v6;
    v30 = v24[10];
    if ( *((_BYTE *)v6 + 11) )
      v29 = 0;
    if ( v29 )
      v30 -= *(_DWORD *)(*((_QWORD *)v29 + 4) + 8LL);
  }
  else
  {
    v30 = *v27;
    if ( !*v27 )
      v30 = *(_DWORD *)(*((_QWORD *)v6 + 2) + 3332LL) - 80;
  }
  if ( v23 > v30 )
  {
LABEL_99:
    v20 = 3;
    goto LABEL_100;
  }
  v31 = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, __int64, __int64, struct SmsPage **, _QWORD))(***((_QWORD ***)v6 + 4) + 80LL))(
          **((_QWORD **)v6 + 4),
          v4,
          *((_QWORD *)v6 + 4) + 8LL,
          1,
          v175,
          0);
  if ( v31 < 0 )
  {
LABEL_28:
    v20 = 3;
    goto LABEL_29;
  }
  v37 = v175[0];
  if ( (*((_DWORD *)v175[0] + 138) & 0x200000) != 0 )
  {
    v137 = (struct _SmsRedoMarker *)v176;
    v138 = 0;
    v163 = (struct _SmsRedoMarker *)v176;
    ExAcquirePushLockExclusiveEx((char *)v175[0] + 272, 0);
    v139 = (__int64 *)*((_QWORD *)v37 + 35);
    v140 = (__int64 *)*((_QWORD *)v37 + 36);
    while ( v139 != v140 )
    {
      v152 = *v139;
      if ( !v137
        || (v153 = *(unsigned int **)(v152 + 16), v153 >= (unsigned int *)v137)
        && ((v153[2] & 0x40) == 0 ? (v145 = *v153) : (v145 = (*((unsigned __int16 *)v153 + 5) + 7) & 0xFFFFFFF8),
            v153 < (unsigned int *)((char *)v153 + v145)) )
      {
        do
        {
          v182 = *(__m128i *)v152;
          v147.m128i_i64[0] = v182.m128i_i64[0];
          v147.m128i_i64[1] = _mm_srli_si128(v182, 8).m128i_u64[0];
          v148 = _InterlockedCompareExchange128((volatile signed __int64 *)v152, 0, 0, v147.m128i_i64);
          v146 = v147.m128i_i32[3];
          v182 = v147;
        }
        while ( !v148 );
        v137 = v163;
        v138 += v146;
      }
      ++v139;
    }
    utl::erase_if_SmsPersistentQuickIndex___utl::allocator_SmsPersistentQuickIndex_____SmsPage::InvalidateAllPersistentQIs_::_2_::_lambda_1___(
      (char *)v37 + 280,
      v137);
    ExReleasePushLockEx((char *)v37 + 272, 0);
    v4 = a2;
    if ( v138 )
      SmsPage::BatchUnpin(v37, a2, v138, 2);
  }
  v38 = (char *)(v176 + *(unsigned __int16 *)(v176 + 10));
  v39 = *(unsigned int *)(v176 + 12);
  v40 = (char *)(v176 + *(unsigned __int16 *)(v176 + 4));
  v41 = *(unsigned __int16 *)(v176 + 6);
  v42 = *(_WORD *)(v176 + 8);
  LODWORD(v163) = *(_DWORD *)v38;
  v161 = v41;
  v162 = v42;
  if ( (_DWORD)v39 )
  {
    if ( v40 >= v38 )
    {
      v43 = (unsigned int)v39;
      if ( v40 <= &v38[v39] )
      {
        v44 = 0;
LABEL_50:
        v45 = 1;
        goto LABEL_60;
      }
    }
  }
  v43 = v39;
  if ( (_WORD)v41 && (_DWORD)v39 && &v40[v41] >= v38 && &v40[v41] <= &v38[v39] )
    v46 = (_WORD)v38 - (_WORD)v40;
  else
    v46 = (v41 + 7) & 0xFFF8;
  v44 = v46;
  if ( (_DWORD)v39 && v40 >= v38 && v40 <= &v38[v39] )
    goto LABEL_50;
  v45 = 0;
LABEL_60:
  v47 = v160;
  v187 = v45;
  v48 = v44 + ((v39 + 7) & 0xFFFFFFF8);
  v9 = *((_QWORD *)v160 + 4) == 0;
  v165 = v48;
  if ( v9 )
  {
    CmsRowWithBuffer::Reset(v160);
    v48 = v165;
    v45 = v187;
    v41 = v161;
    LOBYTE(v42) = v162;
    v47 = v160;
  }
  if ( v48 > *((_DWORD *)v47 + 11) )
  {
    v50 = (unsigned __int64)v48 >> 3;
    v49 = 8 * v50;
    if ( !is_mul_ok(v50, 8u) )
      v49 = -1;
    Pool2 = ExAllocatePool2(66, v49, 1766871885, v41);
    v166 = Pool2;
    if ( !Pool2 )
      goto LABEL_196;
    v47 = v160;
    if ( (*((_BYTE *)v160 + 40) & 1) != 0 )
    {
      v151 = (void *)*((_QWORD *)v160 + 4);
      if ( v151 )
      {
        ExFreePoolWithTag(v151, 0);
        Pool2 = v166;
        v47 = v160;
      }
    }
    *((_BYTE *)v47 + 40) |= 1u;
    v45 = v187;
    LOWORD(v41) = v161;
    LOBYTE(v42) = v162;
    *((_QWORD *)v47 + 4) = Pool2;
    *((_DWORD *)v47 + 11) = v165;
  }
  v52 = *((_QWORD *)v47 + 4);
  v53 = v42 & 3 | 4;
  v54 = (unsigned __int16)v41;
  *((_QWORD *)v47 + 1) = v52;
  *(_DWORD *)v47 = (unsigned __int16)v41;
  *((_QWORD *)v47 + 3) = v52;
  *((_DWORD *)v47 + 4) = v39;
  if ( v45 )
  {
    v56 = v160;
    v52 += (unsigned int)((_DWORD)v40 - (_DWORD)v38);
    *((_QWORD *)v160 + 1) = v52;
  }
  else
  {
    if ( (_WORD)v41 && (_DWORD)v39 && &v40[(unsigned __int16)v41] >= v38 && &v40[(unsigned __int16)v41] <= &v38[v43] )
      v55 = (_WORD)v38 - (_WORD)v40;
    else
      v55 = (v41 + 7) & 0xFFF8;
    v56 = v160;
    *((_QWORD *)v160 + 3) = v52 + v55;
  }
  if ( (_DWORD)v54 )
    *(_QWORD *)((((_DWORD)v54 + 7) & 0xFFFFFFF8) + v52 - 8) = 0;
  v57 = *((_DWORD *)v56 + 4);
  if ( v57 )
    *(_QWORD *)(((v57 + 7) & 0xFFFFFFF8) + *((_QWORD *)v56 + 3) - 8LL) = 0;
  *((_WORD *)v56 + 2) = v53;
  if ( (unsigned __int64)(v40 - 2) <= 2 )
    *((_QWORD *)v56 + 1) = v40;
  else
    memmove(*((void **)v56 + 1), v40, v54);
  memmove(*((void **)v56 + 3), v38, v43);
  v60 = &v38[(unsigned int)v163];
  if ( a4 <= 0 )
  {
    if ( (unsigned int)-a4 <= *((_DWORD *)v60 + 2) )
      goto LABEL_102;
    v6 = v185;
    goto LABEL_99;
  }
  v61 = *(_DWORD *)v56;
  v62 = (char *)*((_QWORD *)v56 + 1);
  if ( (*((_BYTE *)v56 + 40) & 2) != 0 )
  {
    v61 += 8;
    v62 -= 8;
  }
  v63 = *((_DWORD *)v56 + 4) + 7;
  v166 = v61 + 7;
  v58 = v160;
  v64 = ((v61 + 7) & 0xFFFFFFF8) + ((a4 + v63) & 0xFFFFFFF8);
  if ( v64 <= *((_DWORD *)v160 + 11) )
  {
    v56 = v160;
  }
  else
  {
    v65 = 8 * ((unsigned __int64)v64 >> 3);
    if ( !is_mul_ok((unsigned __int64)v64 >> 3, 8u) )
      v65 = -1;
    v66 = (struct _SmsRedoMarker *)ExAllocatePool2(66, v65, 1766871885, v59);
    v163 = v66;
    if ( !v66 )
      goto LABEL_196;
    memmove(v66, v62, v61);
    v67 = v163;
    v68 = (char *)v163 + ((unsigned int)v166 & 0xFFFFFFF8);
    memmove(v68, *((const void **)v160 + 3), *((unsigned int *)v160 + 4));
    v69 = v160;
    v70 = (struct _SmsRedoMarker *)((char *)v163 + 8);
    v71 = *((_BYTE *)v160 + 40);
    if ( (v71 & 2) == 0 )
      v70 = v163;
    *((_QWORD *)v160 + 1) = v70;
    *((_QWORD *)v160 + 3) = v68;
    if ( (v71 & 1) != 0 )
    {
      v72 = (void *)*((_QWORD *)v160 + 4);
      if ( v72 )
      {
        ExFreePoolWithTag(v72, 0);
        v69 = v160;
      }
    }
    *((_DWORD *)v69 + 11) = v64;
    v56 = v160;
    *((_QWORD *)v69 + 4) = v67;
    *((_BYTE *)v160 + 40) |= 1u;
  }
LABEL_102:
  v77 = (unsigned int *)*((_QWORD *)v56 + 3);
  v78 = *v77;
  v188 = *v77;
  if ( (*(_QWORD *)v4 & 2) == 0 )
  {
    if ( (*(_QWORD *)v4 & 0x1000LL) != 0 )
    {
      if ( (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      LOBYTE(v58) = 1;
      CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)v4 + 1), 0x20000000, v58);
      goto LABEL_196;
    }
    v122 = qword_140269410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
    if ( *(_DWORD *)v122 < 0x60u )
    {
      v122 = 0;
      v124 = 112;
      goto LABEL_171;
    }
    if ( !*(_BYTE *)(v122 + 8) )
    {
      if ( (int)*(_QWORD *)(v122 + 88) > (int)HIDWORD(*(_QWORD *)(v122 + 88)) )
      {
        v136 = _InterlockedDecrement((volatile signed __int32 *)(v122 + 88));
        if ( v136 >= *(_DWORD *)(v122 + 92) && v136 >= 0 )
        {
          v155 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v122 + 64));
          goto LABEL_105;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v122 + 88));
      }
LABEL_201:
      v124 = *(unsigned int *)(v122 + 4);
LABEL_171:
      v125 = ExAllocatePool2(66, v124, 1766871885, v123);
      v80 = (_DWORD *)v125;
      if ( (v125 & 0xF) != 0 )
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      if ( !v125 )
      {
LABEL_107:
        if ( v80 )
        {
          v80[4] = 52;
          *((_QWORD *)v80 + 5) = a3;
          v80[3] = 4;
          v80[2] = 4;
          *((_WORD *)v80 + 10) = 0;
          *((_OWORD *)v80 + 3) = 0;
          *((_OWORD *)v80 + 4) = 0;
          *((_QWORD *)v80 + 10) = 0;
          v80[8] = 0;
          v79 = v185;
          *((_QWORD *)v80 + 3) = v80 + 22;
          v80[22] = 0;
          v81 = (_DWORD *)*((_QWORD *)v80 + 3);
          *v81 = *((_DWORD *)v185 + 7);
          v80[2] = 4;
          v80[8] = 0;
          *((_QWORD *)v80 + 5) = a3;
          *((_OWORD *)v80 + 3) = 0;
          *((_OWORD *)v80 + 4) = 0;
          *((_QWORD *)v80 + 10) = 0;
          v82 = v80[2];
          if ( v82 )
          {
            v83 = (_DWORD *)*((_QWORD *)v80 + 3);
            if ( v81 )
            {
              if ( v81 != v83 )
                memmove(v83, v81, v82);
            }
            else
            {
              memset(v83, 0, (unsigned int)v80[2]);
            }
          }
          *(_QWORD *)v80 = *((_QWORD *)v4 + 18);
          *((_QWORD *)v4 + 18) = v80;
          v78 = v188;
          goto LABEL_113;
        }
LABEL_196:
        v6 = v185;
        v31 = -1073741670;
        v20 = 3;
        goto LABEL_29;
      }
LABEL_106:
      *(_QWORD *)v80 = v122;
      v80 += 4;
      goto LABEL_107;
    }
    v154 = (struct _NPAGED_LOOKASIDE_LIST *)(v122 + 64);
    if ( *(_BYTE *)(v122 + 9) )
      v155 = ExAllocateFromNPagedLookasideList(v154);
    else
      v155 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v154);
LABEL_105:
    v80 = v155;
    if ( v155 )
      goto LABEL_106;
    goto LABEL_201;
  }
  v79 = v185;
LABEL_113:
  v84 = (_DWORD **)*((_QWORD *)v79 + 4);
  v85 = v164;
  *((_DWORD *)v79 + 7) = v164;
  if ( (*(_DWORD *)(*((_QWORD *)*v84 + 3) + 44LL) & 1) != 0 )
    *v84[2] = v85;
  v86 = (char *)v77 + v78;
  v87 = *((_QWORD *)v60 + 3);
  v88 = a4 + *((_DWORD *)v60 + 8);
  v89 = v60[13];
  v90 = v60[12];
  v91 = *((_QWORD *)a3 + 3);
  if ( (unsigned int)(v88 - 40) > 8 )
    *(_QWORD *)&v86[v88 - 8] = 0;
  *(_DWORD *)v86 = 40;
  *((_WORD *)v86 + 7) = 0;
  *((_DWORD *)v86 + 1) = 40;
  *((_DWORD *)v86 + 2) = v88 - 40;
  v86[12] = v90;
  v86[13] = v89;
  *((_DWORD *)v86 + 4) = v88;
  *((_DWORD *)v86 + 8) = v88;
  *((_DWORD *)v86 + 5) = 0;
  *((_DWORD *)v86 + 9) = 0;
  *((_QWORD *)v86 + 3) = v87;
  if ( (*(_DWORD *)(v91 + 44) & 2) != 0 )
    v86[13] = v89 | 4;
  v92 = *((_QWORD *)a3 + 3);
  v93 = 0;
  v94 = *((_DWORD *)v60 + 5);
  v166 = v92;
  *((_DWORD *)v86 + 5) = v94;
  *((_DWORD *)v86 + 4) = v88 - 4 * v94;
  if ( v94 )
  {
    v95 = v166;
    do
    {
      v96 = v93;
      v97 = v93++;
      v98 = (unsigned int)v97;
      if ( v96 >= *((_DWORD *)v60 + 5) )
      {
        v99 = 0;
      }
      else
      {
        _mm_lfence();
        v99 = (unsigned int *)&v60[*(unsigned __int16 *)&v60[4 * v97 + *((unsigned int *)v60 + 4)]];
      }
      v100 = &v86[*((unsigned int *)v86 + 1)];
      if ( (v99[2] & 0x40) != 0 )
        v101 = (*((unsigned __int16 *)v99 + 5) + 7) & 0xFFFFFFF8;
      else
        v101 = *v99;
      memmove(&v86[*((unsigned int *)v86 + 1)], v99, v101);
      v102 = *((unsigned int *)v86 + 4) + 4 * v98;
      *(_WORD *)&v86[v102] = (_WORD)v100 - (_WORD)v86;
      if ( (((unsigned __int8)v86[13] >> 3) & ((*(_BYTE *)(v95 + 44) & 2) != 0)) == 0
        || (v103 = *((_WORD *)v100 + 4), (v103 & 2) != 0) )
      {
        v105 = -1;
      }
      else
      {
        if ( (v103 & 0x40) != 0 )
          v104 = v100 + 12;
        else
          v104 = &v100[*((unsigned __int16 *)v100 + 2)];
        v105 = *(_WORD *)v104 - *((_WORD *)v86 + 12);
      }
      *(_WORD *)&v86[v102 + 2] = v105;
      if ( (v100[8] & 0x40) != 0 )
        v106 = (*((unsigned __int16 *)v100 + 5) + 7) & 0xFFFFFFF8;
      else
        v106 = *(_DWORD *)v100;
      *((_DWORD *)v86 + 1) += v106;
      if ( (v100[8] & 0x40) != 0 )
        v107 = (*((unsigned __int16 *)v100 + 5) + 7) & 0xFFFFFFF8;
      else
        v107 = *(_DWORD *)v100;
      *((_DWORD *)v86 + 2) = *((_DWORD *)v86 + 2) - v107 - 4;
      --v94;
    }
    while ( v94 );
    v4 = a2;
  }
  v6 = v185;
  v108 = v164;
  if ( (*(_DWORD *)(*(_QWORD *)(**((_QWORD **)v185 + 4) + 24LL) + 44LL) & 1) != 0 )
    **((_DWORD **)v160 + 1) = v164;
  *((_DWORD *)v160 + 4) = v108;
  v109 = *(_WORD *)(v176 + 8);
  v110 = **((_QWORD **)v185 + 4);
  v111 = v109 & 0x40;
  if ( (v109 & 0x40) != 0 )
    v112 = *(unsigned __int16 *)(v176 + 10);
  else
    v112 = *(_DWORD *)(v176 + 12);
  if ( v108 == v112 )
  {
    v121 = CmsBPlusTable::UpdateInIndex((CmsBPlusTable *)v110, (__int64)v4, (__int64)v160, (__int64 *)v175, 0);
LABEL_162:
    v31 = v121;
    goto LABEL_28;
  }
  v163 = 0;
  v113 = *((_BYTE *)v175[1] + 13) & 2;
  if ( (*(_BYTE *)(v110 + 15) & 0x40) != 0 )
    goto LABEL_291;
  v131 = *((_QWORD *)v4 + 52);
  v132 = *(struct _SmsRedoMarker **)(v131 + 8);
  if ( !v132 )
    v132 = (struct _SmsRedoMarker *)(v131 + 8);
  v133 = v109 & 3;
  v163 = v132;
  if ( v111 )
  {
    v178 = 12;
    v134 = (CmsTxMemLog *)(v176 + 12);
  }
  else
  {
    v133 |= 4u;
    v178 = *(unsigned __int16 *)(v176 + 6);
    v134 = (CmsTxMemLog *)(v176 + *(unsigned __int16 *)(v176 + 4));
  }
  v180 = v134;
  v179 = v133;
  if ( MsDisableRedoLogging )
    goto LABEL_291;
  if ( (*(_QWORD *)v4 & 0x2000000000LL) != 0 )
    goto LABEL_291;
  if ( (*(_QWORD *)v4 & 0x20) != 0 )
    goto LABEL_291;
  v135 = *((_QWORD *)v4 + 1);
  if ( v135 )
  {
    if ( (*(_DWORD *)(v135 + 3396) & 0x400001) != 0 )
      goto LABEL_291;
  }
  v31 = CmsTxMemLog::AddRedoRecord(v131, (_QWORD *)v110, 2u, &v178, 0, 0, 0, 0, v159, 0, 0);
  if ( CmsBPlusTable::HasGlobalBindingSemantics((CmsBPlusTable *)v110) )
  {
    *((_QWORD *)v4 + 14) = v110;
    *(_QWORD *)v4 |= 0x80000000000uLL;
  }
  if ( v31 >= 0 )
  {
LABEL_291:
    v31 = CmsBPlusTable::DeleteIndexEntry((CmsBPlusTable *)v110, v4, (struct SmsLookupStack *)v175, 0);
    if ( v31 >= 0 )
    {
      if ( 100 * *((_DWORD *)v175[1] + 2) / (unsigned int)(*((_DWORD *)v175[1] + 8) - *(_DWORD *)v175[1]) >= 0x19 )
      {
        v114 = v175[0];
        v115 = *((_QWORD *)v175[0] + 12);
        v116 = *(_QWORD *)(v115 + 160);
        if ( (*(_QWORD *)v4 & 0x800LL) != 0 && (*(_QWORD *)v4 & 0x200LL) == 0 )
          v116 = *(_QWORD *)(v115 + 168);
        v117 = *((_QWORD *)v175[0] + 12);
        if ( *(_QWORD *)(v115 + 64) != v115 )
        {
          do
            v117 = *(_QWORD *)(v117 + 64);
          while ( *(_QWORD *)(v117 + 64) != v117 );
        }
        if ( *(_BYTE *)(*(_QWORD *)(v117 + 112) + 11LL) != 2
          && *(_QWORD *)(*(_QWORD *)(v115 + 32) + 40LL)
          && (v116 != *(_QWORD *)(v115 + 168) || *(_QWORD *)(v115 + 160) == *(_QWORD *)(v115 + 168))
          && !*((_BYTE *)v175[0] + 392)
          && (*((_DWORD *)v175[0] + 138) & 0x100000) == 0 )
        {
          v118 = *(_QWORD *)(*(_QWORD *)(v115 + 32) + 40LL);
          while ( 1 )
          {
            v119 = *((_DWORD *)v114 + 138);
            if ( (v119 & 0x20000) != 0 )
              break;
            if ( v119 == _InterlockedCompareExchange((volatile signed __int32 *)v114 + 138, v119 | 0x20000, v119) )
            {
              do
              {
                v157 = *(_QWORD *)(v118 + 64);
                *((_QWORD *)v114 + 86) = v157;
                if ( v157 )
                  v158 = *(_DWORD *)(v157 + 696) + 1;
                else
                  v158 = 1;
                *((_DWORD *)v114 + 174) = v158;
              }
              while ( _InterlockedCompareExchange64((volatile signed __int64 *)(v118 + 64), (signed __int64)v114, v157) != *((_QWORD *)v114 + 86) );
              if ( (*(_DWORD *)(v115 + 188) & 1) == 0 )
                _InterlockedOr((volatile signed __int32 *)(v115 + 188), 1u);
              break;
            }
          }
        }
      }
      if ( (*(_DWORD *)(*(_QWORD *)(v110 + 24) + 44LL) & 0x1000) != 0 && v113 && (*(_DWORD *)(v110 + 188) & 0x80u) == 0 )
        _InterlockedOr((volatile signed __int32 *)(v110 + 188), 0x80u);
      if ( !*((_BYTE *)v175[1] + 12) && _InterlockedDecrement64((volatile signed __int64 *)(v110 + 48)) < 0 )
        _InterlockedIncrement64((volatile signed __int64 *)(v110 + 48));
    }
  }
  v120 = v175[0];
  if ( !v175[0] )
    goto LABEL_160;
  v126 = (CmsVolume *)*((_QWORD *)v4 + 1);
  v127 = 3;
  do
  {
    while ( 1 )
    {
      v128 = (struct SmsPage *)*((_QWORD *)v120 + 38);
      v129 = 0;
      v130 = v127;
      if ( !v128 )
        goto LABEL_179;
      if ( (v127 & 1) == 0 || *((_DWORD *)v120 + 96) != *((_DWORD *)v120 + 78) )
        break;
      v129 = (struct SmsPage *)*((_QWORD *)v120 + 38);
      if ( (v127 & 4) == 0 )
        goto LABEL_221;
      v141 = (_DWORD *)((char *)v120 + 316);
      v142 = *((_DWORD *)v120 + 79);
      if ( *((_DWORD *)v120 + 97) != v142 )
      {
        v130 = v127 & 0xFFFFFFFB;
        goto LABEL_221;
      }
LABEL_287:
      *v141 = v142 - 1;
LABEL_221:
      v9 = (*((_DWORD *)v120 + 78))-- == 1;
      if ( !v9 )
        goto LABEL_179;
      *((_QWORD *)v120 + 38) = 0;
      CmsVolume::UnpinInternal(v126, v4, v120, v127);
      v120 = v128;
      v127 = v130;
    }
    if ( (v127 & 4) != 0 && *((_DWORD *)v120 + 97) == *((_DWORD *)v120 + 79) )
    {
      v141 = (_DWORD *)((char *)v120 + 316);
      v129 = (struct SmsPage *)*((_QWORD *)v120 + 38);
      v142 = *((_DWORD *)v120 + 79);
      goto LABEL_287;
    }
LABEL_179:
    CmsVolume::UnpinInternal(v126, v4, v120, v127);
    v120 = v129;
    v127 = v130;
  }
  while ( v129 );
  v6 = v185;
  v175[0] = 0;
LABEL_160:
  if ( v31 >= 0 )
  {
    v121 = (*(__int64 (__fastcall **)(__int64, struct CmsTransactionContext *, CmsRowWithBuffer *, __int64, _DWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v110 + 88LL))(
             v110,
             v4,
             v160,
             50,
             0,
             0,
             0,
             0);
    goto LABEL_162;
  }
  CmsTxMemLog::DiscardPendingRecordsFrom(*((CmsTxMemLog **)v4 + 52), &v163);
  v20 = 3;
LABEL_29:
  v32 = v175[0];
  if ( !v175[0] )
    goto LABEL_30;
  v73 = (CmsVolume *)*((_QWORD *)v4 + 1);
  while ( 2 )
  {
    while ( 1 )
    {
      v74 = (struct SmsPage *)*((_QWORD *)v32 + 38);
      v75 = 0;
      v76 = v20;
      if ( !v74 )
        break;
      if ( (v20 & 1) != 0 && *((_DWORD *)v32 + 96) == *((_DWORD *)v32 + 78) )
      {
        v75 = (struct SmsPage *)*((_QWORD *)v32 + 38);
        if ( (v20 & 4) == 0 )
          goto LABEL_224;
        v143 = (_DWORD *)((char *)v32 + 316);
        v144 = *((_DWORD *)v32 + 79);
        if ( *((_DWORD *)v32 + 97) != v144 )
        {
          v76 = v20 & 0xFFFFFFFB;
          goto LABEL_224;
        }
      }
      else
      {
        if ( (v20 & 4) == 0 || *((_DWORD *)v32 + 97) != *((_DWORD *)v32 + 79) )
          break;
        v143 = (_DWORD *)((char *)v32 + 316);
        v75 = (struct SmsPage *)*((_QWORD *)v32 + 38);
        v144 = *((_DWORD *)v32 + 79);
      }
      *v143 = v144 - 1;
LABEL_224:
      v9 = (*((_DWORD *)v32 + 78))-- == 1;
      if ( !v9 )
        break;
      *((_QWORD *)v32 + 38) = 0;
      CmsVolume::UnpinInternal(v73, v4, v32, v20);
      v32 = v74;
      v20 = v76;
    }
    CmsVolume::UnpinInternal(v73, v4, v32, v20);
    v32 = v75;
    v20 = v76;
    if ( v75 )
      continue;
    break;
  }
  v6 = v185;
  v175[0] = 0;
LABEL_30:
  v33 = (CmsVolume *)*((_QWORD *)v6 + 2);
  if ( v31 >= 0 )
  {
    --*((_WORD *)v4 + 106);
    v173 = 0;
    if ( v169 )
      --*((_WORD *)v4 + 107);
    if ( HIBYTE(v168) )
    {
      v149 = (CmsTxMemLog *)*((_QWORD *)v4 + 52);
      v150 = (CmsVolume *)((char *)v33 + 2816);
      if ( *(_QWORD *)v149 )
        CmsTxMemLog::MergeTxLog(v180, (struct CmsTxMemLog *)&v174, v150);
      else
        CmsTxMemLog::DiscardPendingRecords(v149, v150);
      if ( (v172 & 0x80000000000LL) != 0 )
      {
        v156 = v181;
        *(_QWORD *)v4 |= 0x80000000000uLL;
        *((_QWORD *)v4 + 14) = v156;
      }
      *((_QWORD *)v4 + 52) = v180;
    }
    *(_QWORD *)v4 |= v172 & 0x100000000000LL;
    if ( *((_BYTE *)v4 + 131) != *((_BYTE *)v4 + 130) && (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    v35 = v170;
    v36 = v171;
    *((_BYTE *)v4 + 131) = v170;
    *((_BYTE *)v4 + 132) = v36;
    *((_BYTE *)v4 + 130) = v35;
  }
  else
  {
    CmsVolume::AbortTopLevelAction(v33, v4, (struct _SmsTopLevelAction *)v167);
  }
  if ( v160 )
  {
    *(_DWORD *)v160 = 0;
    *((_DWORD *)v4 + 56) &= ~(1 << ((v160 - v4 - 2816) / 80));
  }
  if ( !v181 )
    *(_QWORD *)v4 &= ~0x2000000000uLL;
  if ( v175[0] && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x140062700  mov     [rsp-8+arg_8], rdx
0x140062705  mov     [rsp-8+arg_0], rcx
0x14006270a  push    rbp
0x14006270b  push    rbx
0x14006270c  push    rdi
0x14006270d  push    r12
0x14006270f  push    r13
0x140062711  push    r14
0x140062713  push    r15
0x140062715  lea     rbp, [rsp-30h]
0x14006271a  sub     rsp, 130h
0x140062721  xor     eax, eax
0x140062723  xorps   xmm0, xmm0
0x140062726  mov     [rbp+60h+var_80], rax
0x14006272a  mov     rdi, rdx
0x14006272d  mov     edx, [rdx+0E0h]
0x140062733  xor     r10d, r10d
0x140062736  mov     eax, edx
0x140062738  mov     r12, rcx
0x14006273b  not     eax
0x14006273d  mov     r14d, r9d
0x140062740  and     eax, 3Fh
0x140062743  mov     r13, r8
0x140062746  bsf     ecx, eax
0x140062749  movups  xmmword ptr [rbp+60h+var_A0], xmm0
0x14006274d  mov     [rbp+60h+var_A8], ecx
0x140062750  mov     r9d, 1
0x140062756  movups  [rbp+60h+var_90], xmm0
0x14006275a  jz      loc_1400637DA
0x140062760  mov     eax, r9d
0x140062763  lea     r15, [rdi+0B00h]
0x14006276a  shl     eax, cl
0x14006276c  lea     rcx, [rcx+rcx*4]
0x140062770  shl     rcx, 4
0x140062774  or      eax, edx
0x140062776  mov     [rdi+0E0h], eax
0x14006277c  add     r15, rcx
0x14006277f  mov     eax, [rbp+60h+var_3C]
0x140062782  movups  [rbp+60h+var_50], xmm0
0x140062786  mov     [rsp+160h+var_100], r15
0x14006278b  movups  xmmword ptr [r15], xmm0
0x14006278f  mov     [rcx+rdi+0B10h], r10d
0x140062797  mov     [rcx+rdi+0B14h], eax
0x14006279e  mov     [rcx+rdi+0B18h], r10
0x1400627a6  mov     rdx, [rdi]
0x1400627a9  mov     r8, 2000000000h
0x1400627b3  mov     rax, rdx
0x1400627b6  mov     [rbp+60h+var_C0], r10w
0x1400627bb  and     rax, r8
0x1400627be  mov     [rbp+60h+var_BE], r10b
0x1400627c2  mov     [rbp+60h+var_B0], r10d
0x1400627c6  mov     [rbp+60h+var_68], rax
0x1400627ca  bt      rdx, 15h
0x1400627cf  jb      loc_140063759
0x1400627d5  inc     word ptr [rdi+0D4h]
0x1400627dc  movzx   eax, word ptr [rdi+0D4h]
0x1400627e3  movzx   ebx, byte ptr [rdi+84h]
0x1400627ea  mov     [rbp+60h+var_B0], eax
0x1400627ed  mov     rax, [rdi+90h]
0x1400627f4  mov     [rbp+60h+var_D8], rax
0x1400627f8  mov     rax, [rdi+1A0h]
0x1400627ff  add     rax, 8
0x140062803  mov     [rbp+60h+var_BE], r10b
0x140062807  mov     rcx, [rax]
0x14006280a  test    rcx, rcx
0x14006280d  mov     [rbp+60h+var_B8], rdx
0x140062811  mov     [rbp+60h+var_BC], bl
0x140062814  cmovz   rcx, rax
0x140062818  mov     byte ptr [rbp+60h+var_C0+1], r10b
0x14006281c  mov     rax, [rdi+0C8h]
0x140062823  mov     [rbp+60h+var_C8], rax
0x140062827  mov     rax, 0FFFFEFFFFFFFFFFFh
0x140062831  mov     [rbp+60h+var_D0], rcx
0x140062835  and     rdx, rax
0x140062838  movzx   ecx, byte ptr [rdi+83h]
0x14006283f  mov     [rdi], rdx
0x140062842  mov     [rbp+60h+var_BD], cl
0x140062845  cmp     cl, 0Dh
0x140062848  jnb     short loc_140062861
0x14006284a  movzx   eax, cl
0x14006284d  cmp     [rdi+rax*8+230h], r10
0x140062855  jnz     loc_1400633E9
0x14006285b  mov     [rdi+83h], cl
0x140062861  cmp     bl, 0Dh
0x140062864  jnb     short loc_14006287D
0x140062866  movzx   eax, bl
0x140062869  cmp     [rdi+rax*8+1A8h], r10
0x140062871  jnz     loc_140062E79
0x140062877  mov     [rdi+84h], bl
0x14006287d  movzx   eax, byte ptr [rdi+82h]
0x140062884  cmp     [rdi+83h], al
0x14006288a  jb      loc_14006376F
0x140062890  or      [rdi], r8
0x140062893  mov     edx, 3
0x140062898  movzx   eax, byte ptr [rdi+83h]
0x14006289f  mov     [rdi+82h], al
0x1400628a5  mov     r8d, [r12+1Ch]
0x1400628aa  add     r8d, r14d
0x1400628ad  mov     [rsp+160h+arg_10], rsi
0x1400628b5  mov     [rsp+160h+var_E8], r8d
0x1400628ba  js      loc_1400637E4
0x1400628c0  test    r14b, 7
0x1400628c4  jnz     loc_140062E3E
0x1400628ca  mov     rdx, [r13+18h]
0x1400628ce  mov     r11d, 0FFFFFFF8h
0x1400628d4  mov     ebx, [rdx+2Ch]
0x1400628d7  and     ebx, 1000h
0x1400628dd  jz      loc_1400637EE
0x1400628e3  mov     rax, [r13+70h]
0x1400628e7  mov     rcx, [rax+10h]
0x1400628eb  mov     rax, [rcx+0DD0h]
0x1400628f2  cmp     [rax+8], r10w
0x1400628f7  jnz     loc_140062E27
0x1400628fd  mov     rax, r10
0x140062900  lea     ecx, [rax+43h]
0x140062903  mov     eax, [rdx+1Ch]
0x140062906  and     ecx, r11d
0x140062909  add     eax, 57h ; 'W'
0x14006290c  add     eax, ecx
0x14006290e  lea     rcx, [rdx+18h]
0x140062912  and     eax, r11d
0x140062915  cmp     r8d, eax
0x140062918  jb      loc_140062E39
0x14006291e  test    ebx, ebx
0x140062920  jz      loc_140062A88
0x140062926  cmp     [r12+0Bh], r10b
0x14006292b  mov     rcx, r12
0x14006292e  mov     edx, [rdx+28h]
0x140062931  cmovnz  rcx, r10
0x140062935  test    rcx, rcx
0x140062938  jz      short loc_140062941
0x14006293a  mov     rax, [rcx+20h]
0x14006293e  sub     edx, [rax+8]
0x140062941  cmp     r8d, edx
0x140062944  ja      loc_140062E39
0x14006294a  mov     r8, [r12+20h]
0x14006294f  lea     rdx, [rbp+60h+var_A0]
0x140062953  mov     [rsp+160h+var_138], r10
0x140062958  mov     qword ptr [rsp+160h+var_140], rdx
0x14006295d  mov     rdx, rdi
0x140062960  mov     rcx, [r8]
0x140062963  add     r8, 8
0x140062967  mov     rax, [rcx]
0x14006296a  mov     rax, [rax+50h]
0x14006296e  call    _guard_dispatch_icall
0x140062973  mov     esi, eax
0x140062975  test    eax, eax
0x140062977  jns     loc_140062AA5
0x14006297d  mov     edx, 3
0x140062982  xor     r10d, r10d
0x140062985  mov     r8, [rbp+60h+var_A0]; struct SmsPage *
0x140062989  test    r8, r8
0x14006298c  jnz     loc_140062DE1
0x140062992  mov     rcx, [r12+10h]; this
0x140062997  test    esi, esi
0x140062999  jns     loc_140062A23
0x14006299f  lea     r8, [rbp+60h+var_D8]; struct _SmsTopLevelAction *
0x1400629a3  mov     rdx, rdi; struct CmsTransactionContext *
0x1400629a6  call    ?AbortTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@@Z; CmsVolume::AbortTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *)
0x1400629ab  mov     rcx, [rsp+160h+var_100]
0x1400629b0  test    rcx, rcx
0x1400629b3  jz      short loc_1400629EF
0x1400629b5  mov     dword ptr [rcx], 0
0x1400629bb  mov     rax, 6666666666666667h
0x1400629c5  sub     rcx, rdi
0x1400629c8  sub     rcx, 0B00h
0x1400629cf  imul    rcx
0x1400629d2  mov     eax, 1
0x1400629d7  sar     rdx, 5
0x1400629db  mov     rcx, rdx
0x1400629de  shr     rcx, 3Fh
0x1400629e2  add     rcx, rdx
0x1400629e5  shl     eax, cl
0x1400629e7  not     eax
0x1400629e9  and     [rdi+0E0h], eax
0x1400629ef  cmp     [rbp+60h+var_68], 0
0x1400629f4  jz      loc_1400639C5
0x1400629fa  cmp     [rbp+60h+var_A0], 0
0x1400629ff  jnz     loc_1400637C4
0x140062a05  mov     eax, esi
0x140062a07  mov     rsi, [rsp+160h+arg_10]
0x140062a0f  add     rsp, 130h
0x140062a16  pop     r15
0x140062a18  pop     r14
0x140062a1a  pop     r13
0x140062a1c  pop     r12
0x140062a1e  pop     rdi
0x140062a1f  pop     rbx
0x140062a20  pop     rbp
0x140062a21  retn
0x140062a23  dec     word ptr [rdi+0D4h]
0x140062a2a  cmp     [rbp+60h+var_BE], 0
0x140062a2e  mov     [rbp+60h+var_B0], r10d
0x140062a32  jnz     loc_14006398F
0x140062a38  cmp     byte ptr [rbp+60h+var_C0+1], 0
0x140062a3c  jnz     loc_140063715
0x140062a42  mov     rax, [rbp+60h+var_B8]
0x140062a46  mov     rcx, 100000000000h
0x140062a50  and     rax, rcx
0x140062a53  or      [rdi], rax
0x140062a56  movzx   eax, byte ptr [rdi+82h]
0x140062a5d  cmp     [rdi+83h], al
0x140062a63  jnz     loc_1400637AE
0x140062a69  movzx   ecx, [rbp+60h+var_BD]
0x140062a6d  movzx   eax, [rbp+60h+var_BC]
0x140062a71  mov     [rdi+83h], cl
0x140062a77  mov     [rdi+84h], al
0x140062a7d  mov     [rdi+82h], cl
0x140062a83  jmp     loc_1400629AB
0x140062a88  mov     edx, [rcx]
0x140062a8a  test    edx, edx
0x140062a8c  jnz     loc_140062941
0x140062a92  mov     rax, [r12+10h]
0x140062a97  mov     edx, [rax+0D04h]
0x140062a9d  sub     edx, 50h ; 'P'
0x140062aa0  jmp     loc_140062941
0x140062aa5  mov     rsi, [rbp+60h+var_A0]
0x140062aa9  test    dword ptr [rsi+228h], 200000h
0x140062ab3  jnz     loc_1400634FC
0x140062ab9  mov     rcx, qword ptr [rbp+60h+var_90]
0x140062abd  movzx   ebx, word ptr [rcx+0Ah]
0x140062ac1  movzx   esi, word ptr [rcx+4]
0x140062ac5  add     rbx, rcx
0x140062ac8  mov     r15d, [rcx+0Ch]
0x140062acc  add     rsi, rcx
0x140062acf  movzx   r9d, word ptr [rcx+6]
0x140062ad4  movzx   r10d, word ptr [rcx+8]
0x140062ad9  mov     ecx, 0FFF8h
0x140062ade  mov     eax, [rbx]
0x140062ae0  mov     dword ptr [rsp+160h+var_F0], eax
0x140062ae4  mov     [rsp+160h+var_F8], r9w
0x140062aea  mov     word ptr [rsp+160h+var_F6], r10w
0x140062af0  test    r15d, r15d
0x140062af3  jz      short loc_140062B0C
0x140062af5  cmp     rsi, rbx
0x140062af8  jb      short loc_140062B0C
0x140062afa  lea     rax, [r15+rbx]
0x140062afe  mov     r12d, r15d
0x140062b01  cmp     rsi, rax
0x140062b04  ja      short loc_140062B0C
0x140062b06  xor     ecx, ecx
0x140062b08  mov     dl, 1
0x140062b0a  jmp     short loc_140062B54
0x140062b0c  mov     r12, r15
0x140062b0f  test    r9w, r9w
0x140062b13  jz      short loc_140062B35
0x140062b15  test    r15d, r15d
0x140062b18  jz      short loc_140062B35
0x140062b1a  lea     rcx, [rsi+r9]
0x140062b1e  cmp     rcx, rbx
0x140062b21  jb      short loc_140062B30
0x140062b23  lea     rax, [r15+rbx]
0x140062b27  cmp     rcx, rax
0x140062b2a  jbe     loc_14006382E
0x140062b30  mov     ecx, 0FFF8h
0x140062b35  lea     eax, [r9+7]
0x140062b39  and     ax, cx
0x140062b3c  movzx   ecx, ax
0x140062b3f  test    r15d, r15d
0x140062b42  jz      short loc_140062B52
0x140062b44  cmp     rsi, rbx
0x140062b47  jb      short loc_140062B52
0x140062b49  lea     rax, [r15+rbx]
0x140062b4d  cmp     rsi, rax
0x140062b50  jbe     short loc_140062B08
0x140062b52  xor     dl, dl
0x140062b54  mov     r11, [rsp+160h+var_100]
0x140062b59  lea     eax, [r15+7]
0x140062b5d  mov     r8d, 0FFFFFFF8h
0x140062b63  mov     byte ptr [rbp+60h+arg_18], dl
0x140062b69  and     eax, r8d
0x140062b6c  add     eax, ecx
0x140062b6e  cmp     qword ptr [r11+20h], 0
0x140062b73  mov     [rsp+160h+var_E4], eax
0x140062b77  jz      loc_140063839
0x140062b7d  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140062b84  cmp     eax, [r11+2Ch]
0x140062b88  jbe     short loc_140062BF7
0x140062b8a  mov     ecx, eax
0x140062b8c  mov     eax, 8
0x140062b91  shr     rcx, 3
0x140062b95  mul     rcx
0x140062b98  mov     ecx, 42h ; 'B'
0x140062b9d  cmovb   rax, r8
0x140062ba1  mov     r8d, 6950534Dh
0x140062ba7  mov     rdx, rax
0x140062baa  call    cs:__imp_ExAllocatePool2
0x140062bb1  nop     dword ptr [rax+rax+00h]
0x140062bb6  mov     [rbp+60h+var_E0], rax
0x140062bba  test    rax, rax
0x140062bbd  jz      loc_140063499
0x140062bc3  mov     r11, [rsp+160h+var_100]
0x140062bc8  test    byte ptr [r11+28h], 1
0x140062bcd  jnz     loc_140063785
0x140062bd3  or      byte ptr [r11+28h], 1
0x140062bd8  movzx   edx, byte ptr [rbp+60h+arg_18]
0x140062bdf  movzx   r9d, [rsp+160h+var_F8]
0x140062be5  movzx   r10d, word ptr [rsp+160h+var_F6]
0x140062beb  mov     [r11+20h], rax
0x140062bef  mov     eax, [rsp+160h+var_E4]
  ... truncated ...
```
