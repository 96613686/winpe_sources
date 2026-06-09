# CmsEmbeddedComposite::ResizeRoot(CmsTransactionContext &,CmsBPlusTable &,long)

- ea: `0x14001b120`
- end: `0x14001c299`
- name: `?ResizeRoot@CmsEmbeddedComposite@@QEAAJAEAVCmsTransactionContext@@AEAVCmsBPlusTable@@J@Z`
- size: `4473`
- prototype: `int(CmsEmbeddedComposite *__hidden this, struct CmsTransactionContext *, struct CmsBPlusTable *, int)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001b0b0`
- `0x14003586c`

## callees

- `0x14001a920`
- `0x14001b120`
- `0x14001cbc0`
- `0x14002b110`
- `0x14003234c`
- `0x140036df0`
- `0x140083ec0`
- `0x140097970`
- `0x1400c3a64`
- `0x1400c4acc`
- `0x1400c8574`
- `0x1400c9720`
- `0x1400cb7e0`
- `0x14014f738`
- `0x1401e9dc0`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14001be47`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001c05a`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001c070`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001c0af`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001c0c5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001c19b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001c19b`
- `ntoskrnl!ExAllocatePool2` at `0x14001b5c1`
- `ntoskrnl!ExAllocatePool2` at `0x14001b75a`
- `ntoskrnl!ExAllocatePool2` at `0x14001bd26`
- `ntoskrnl!ExAllocatePool2` at `0x14001b5c1`
- `ntoskrnl!ExAllocatePool2` at `0x14001b75a`
- `ntoskrnl!ExAllocatePool2` at `0x14001bd26`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001bce8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001bce8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eee54`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eee54`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001c1b8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001c1b8`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001bf21`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001bf21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b7d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c095`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b7d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c095`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001bee0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001bee0`

## string_xrefs

- `0x14001bd3d`: `Lookaside list allocation must be double quad aligned.`

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
  CmsEmbeddedComposite *v6; // r15
  int v7; // r14d
  bool v9; // zf
  int v10; // ecx
  int v11; // eax
  __int64 v12; // rcx
  CmsRowWithBuffer *v13; // r12
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned __int8 v17; // bl
  _QWORD *v18; // rax
  _QWORD *v19; // rcx
  unsigned __int8 v20; // cl
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
  CmsVolume *v32; // rcx
  unsigned __int8 v34; // cl
  unsigned __int8 v35; // al
  struct SmsPage *v36; // rsi
  char *v37; // rbx
  size_t v38; // r15
  char *v39; // rsi
  __int64 v40; // r9
  __int16 v41; // r10
  size_t v42; // r12
  int v43; // ecx
  char v44; // dl
  unsigned __int16 v45; // ax
  CmsRowWithBuffer *v46; // r11
  unsigned int v47; // eax
  __int64 v48; // rax
  unsigned __int64 v49; // kr00_8
  __int64 Pool2; // rax
  __int64 v51; // rcx
  __int16 v52; // r10
  size_t v53; // r8
  unsigned __int16 v54; // r9
  int v55; // ecx
  size_t v56; // r8
  __int64 v57; // r8
  char *v58; // r15
  unsigned int v59; // esi
  char *v60; // rbx
  int v61; // r12d
  unsigned int v62; // r12d
  unsigned __int64 v63; // rax
  struct _SmsRedoMarker *v64; // rax
  struct _SmsRedoMarker *v65; // rbx
  char *v66; // rsi
  CmsRowWithBuffer *v67; // rdx
  struct _SmsRedoMarker *v68; // rax
  char v69; // cl
  void *v70; // rcx
  unsigned int *v71; // r12
  __int64 v72; // rbx
  CmsEmbeddedComposite *v73; // rsi
  _DWORD *v74; // rbx
  _DWORD *v75; // rdx
  unsigned int v76; // eax
  _DWORD *v77; // rcx
  _DWORD **v78; // rdx
  unsigned int v79; // r8d
  char *v80; // rbx
  __int64 v81; // r10
  int v82; // edx
  char v83; // r9
  char v84; // r11
  __int64 v85; // rsi
  __int64 v86; // rax
  unsigned int v87; // r12d
  int v88; // r13d
  __int64 v89; // rdi
  unsigned int v90; // ecx
  __int64 v91; // rax
  __int64 v92; // r14
  unsigned int *v93; // rdx
  char *v94; // rsi
  unsigned int v95; // eax
  __int64 v96; // rdx
  __int16 v97; // ax
  char *v98; // rax
  __int16 v99; // ax
  unsigned int v100; // ecx
  unsigned int v101; // ecx
  unsigned int v102; // ecx
  __int16 v103; // bx
  __int64 v104; // r14
  __int16 v105; // r8
  int v106; // eax
  char v107; // r15
  struct SmsPage *v108; // rbx
  __int64 v109; // rdx
  __int64 v110; // rcx
  __int64 v111; // rax
  __int64 v112; // r8
  signed __int32 v113; // eax
  __int64 v114; // rsi
  __int64 v115; // rdx
  __int64 v116; // rax
  __int64 v117; // r10
  struct _SmsRedoMarker *v118; // rcx
  __int16 v119; // bx
  CmsTxMemLog *v120; // rax
  __int64 v121; // rax
  int v122; // ecx
  struct _SmsRedoMarker *v123; // rbx
  int v124; // r15d
  __int64 *v125; // r8
  __int64 *v126; // r9
  signed __int32 v127; // edx
  signed __int32 v128; // ebx
  signed __int32 v129; // ecx
  CmsVolume *v130; // rcx
  __int64 v131; // rax
  __int32 v132; // rdx^4
  __m128i v133; // rt0
  unsigned __int8 v134; // tt
  CmsTxMemLog *v135; // rax
  struct CmsDurableLog *v136; // rdx
  void *v137; // rcx
  __int64 v138; // r11
  unsigned int *v139; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v140; // rcx
  _DWORD *v141; // rax
  struct SmsPage *v142; // rax
  signed __int64 v143; // rax
  int v144; // ecx
  __int64 v145; // [rsp+40h] [rbp-C0h]
  CmsRowWithBuffer *v146; // [rsp+60h] [rbp-A0h]
  __int16 v147; // [rsp+68h] [rbp-98h]
  char v148; // [rsp+6Ah] [rbp-96h]
  struct _SmsRedoMarker *v149; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v150; // [rsp+78h] [rbp-88h]
  unsigned int v151; // [rsp+7Ch] [rbp-84h]
  __int64 v152; // [rsp+80h] [rbp-80h]
  _QWORD v153[3]; // [rsp+88h] [rbp-78h] BYREF
  __int16 v154; // [rsp+A0h] [rbp-60h]
  char v155; // [rsp+A2h] [rbp-5Eh]
  unsigned __int8 v156; // [rsp+A3h] [rbp-5Dh]
  unsigned __int8 v157; // [rsp+A4h] [rbp-5Ch]
  __int64 v158; // [rsp+A8h] [rbp-58h]
  int v159; // [rsp+B0h] [rbp-50h]
  int v160; // [rsp+B8h] [rbp-48h] BYREF
  struct SmsPage *v161[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v162; // [rsp+D0h] [rbp-30h]
  __int64 v163; // [rsp+E0h] [rbp-20h]
  int v164; // [rsp+E8h] [rbp-18h] BYREF
  __int16 v165; // [rsp+ECh] [rbp-14h]
  CmsTxMemLog *v166; // [rsp+F0h] [rbp-10h]
  struct SmsPage *v167; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v168; // [rsp+100h] [rbp+0h]
  __m128i v169; // [rsp+110h] [rbp+10h]
  __int128 v170; // [rsp+120h] [rbp+20h]
  int v171; // [rsp+134h] [rbp+34h]
  CmsEmbeddedComposite *v172; // [rsp+180h] [rbp+80h]
  char v175; // [rsp+198h] [rbp+98h]
  unsigned int v176; // [rsp+198h] [rbp+98h]

  v172 = this;
  v163 = 0;
  v4 = a2;
  v5 = *((_DWORD *)a2 + 56);
  v6 = this;
  v7 = a4;
  v9 = !_BitScanForward((unsigned int *)&this, ~(_BYTE)v5 & 0x3F);
  *(_OWORD *)v161 = 0;
  v160 = v10;
  v162 = 0;
  if ( v9 )
  {
    v13 = 0;
  }
  else
  {
    v11 = 1 << (char)this;
    v12 = 80LL * (_QWORD)this;
    *((_DWORD *)v4 + 56) = v5 | v11;
    v13 = (struct CmsTransactionContext *)((char *)v4 + v12 + 2816);
    v14 = v171;
    v170 = 0;
    *(_OWORD *)v13 = 0;
    *(_DWORD *)((char *)v4 + v12 + 2832) = 0;
    *(_DWORD *)((char *)v4 + v12 + 2836) = v14;
    *(_QWORD *)((char *)v4 + v12 + 2840) = 0;
  }
  v15 = *(_QWORD *)v4;
  v146 = v13;
  v16 = *(_QWORD *)v4 & 0x2000000000LL;
  v154 = 0;
  v155 = 0;
  v159 = 0;
  v168 = v16;
  if ( (v15 & 0x200000) != 0 && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  ++*((_WORD *)v4 + 106);
  v17 = *((_BYTE *)v4 + 132);
  v159 = *((unsigned __int16 *)v4 + 106);
  v153[0] = *((_QWORD *)v4 + 18);
  v18 = (_QWORD *)(*((_QWORD *)v4 + 52) + 8LL);
  v155 = 0;
  v19 = (_QWORD *)*v18;
  v9 = *v18 == 0;
  v158 = v15;
  v157 = v17;
  if ( v9 )
    v19 = v18;
  HIBYTE(v154) = 0;
  v153[2] = *((_QWORD *)v4 + 25);
  v153[1] = v19;
  v20 = *((_BYTE *)v4 + 131);
  *(_QWORD *)v4 = v15 & 0xFFFFEFFFFFFFFFFFuLL;
  v156 = v20;
  while ( 1 )
  {
    if ( v20 >= 0xDu )
      goto LABEL_10;
    if ( !*((_QWORD *)v4 + v20 + 70) )
      break;
    ++v20;
  }
  *((_BYTE *)v4 + 131) = v20;
LABEL_10:
  while ( v17 < 0xDu )
  {
    if ( !*((_QWORD *)v4 + v17 + 53) )
    {
      *((_BYTE *)v4 + 132) = v17;
      break;
    }
    ++v17;
  }
  if ( *((_BYTE *)v4 + 131) < *((_BYTE *)v4 + 130) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  *(_QWORD *)v4 |= 0x2000000000uLL;
  *((_BYTE *)v4 + 130) = *((_BYTE *)v4 + 131);
  v21 = *((_DWORD *)v6 + 7);
  v22 = a4 + v21 < 0;
  v23 = a4 + v21;
  v150 = v23;
  if ( v22 )
  {
    v31 = -1073741811;
    goto LABEL_28;
  }
  if ( (a4 & 7) != 0 )
    goto LABEL_237;
  v24 = (_DWORD *)*((_QWORD *)a3 + 3);
  if ( (v24[11] & 0x1000) != 0 )
  {
    v25 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a3 + 14) + 16LL) + 3608LL);
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
      v28 = *(_DWORD *)(*((_QWORD *)v6 + 2) + 3396LL) - 80;
  }
  if ( v23 < v28 )
    goto LABEL_237;
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
      v30 = *(_DWORD *)(*((_QWORD *)v6 + 2) + 3396LL) - 80;
  }
  if ( v23 > v30 )
    goto LABEL_237;
  v31 = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, __int64, __int64, struct SmsPage **, _QWORD))(***((_QWORD ***)v6 + 4) + 80LL))(
          **((_QWORD **)v6 + 4),
          v4,
          *((_QWORD *)v6 + 4) + 8LL,
          1,
          v161,
          0);
  if ( v31 < 0 )
    goto LABEL_28;
  v36 = v161[0];
  if ( (*((_DWORD *)v161[0] + 138) & 0x200000) != 0 )
  {
    v123 = (struct _SmsRedoMarker *)v162;
    v124 = 0;
    v149 = (struct _SmsRedoMarker *)v162;
    ExAcquirePushLockExclusiveEx((char *)v161[0] + 272, 0);
    v125 = (__int64 *)*((_QWORD *)v36 + 35);
    v126 = (__int64 *)*((_QWORD *)v36 + 36);
    while ( v125 != v126 )
    {
      v138 = *v125;
      if ( !v123
        || (v139 = *(unsigned int **)(v138 + 16), v139 >= (unsigned int *)v123)
        && ((v139[2] & 0x40) == 0 ? (v131 = *v139) : (v131 = (*((unsigned __int16 *)v139 + 5) + 7) & 0xFFFFFFF8),
            v139 < (unsigned int *)((char *)v139 + v131)) )
      {
        do
        {
          v169 = *(__m128i *)v138;
          v133.m128i_i64[0] = v169.m128i_i64[0];
          v133.m128i_i64[1] = _mm_srli_si128(v169, 8).m128i_u64[0];
          v134 = _InterlockedCompareExchange128((volatile signed __int64 *)v138, 0, 0, v133.m128i_i64);
          v132 = v133.m128i_i32[3];
          v169 = v133;
        }
        while ( !v134 );
        v123 = v149;
        v124 += v132;
      }
      ++v125;
    }
    utl::erase_if_SmsPersistentQuickIndex___utl::allocator_SmsPersistentQuickIndex_____SmsPage::InvalidateAllPersistentQIs_::_2_::_lambda_1___(
      (char *)v36 + 280,
      v123);
    ExReleasePushLockEx((char *)v36 + 272, 0);
    v7 = a4;
    if ( v124 )
    {
      do
      {
        v128 = *((_DWORD *)v36 + 95) - v124;
        v129 = v128;
        if ( !v128 )
          v129 = 1;
        v127 = *((_DWORD *)v36 + 95);
      }
      while ( v127 != _InterlockedCompareExchange((volatile signed __int32 *)v36 + 95, v129, v127) );
      v7 = a4;
      if ( !v128 )
      {
        v130 = (CmsVolume *)*((_QWORD *)v4 + 1);
        v167 = v36;
        CmsVolume::Unpin(v130, v4, &v167, 2u);
      }
    }
  }
  v37 = (char *)(v162 + *(unsigned __int16 *)(v162 + 10));
  v38 = *(unsigned int *)(v162 + 12);
  v39 = (char *)(v162 + *(unsigned __int16 *)(v162 + 4));
  v40 = *(unsigned __int16 *)(v162 + 6);
  v41 = *(_WORD *)(v162 + 8);
  LODWORD(v149) = *(_DWORD *)v37;
  v147 = v40;
  v148 = v41;
  if ( (_DWORD)v38 )
  {
    if ( v39 >= v37 )
    {
      v42 = (unsigned int)v38;
      if ( v39 <= &v37[v38] )
      {
        v43 = 0;
LABEL_50:
        v44 = 1;
        goto LABEL_60;
      }
    }
  }
  v42 = v38;
  if ( (_WORD)v40 && (_DWORD)v38 && &v39[v40] >= v37 && &v39[v40] <= &v37[v38] )
    v45 = (_WORD)v37 - (_WORD)v39;
  else
    v45 = (v40 + 7) & 0xFFF8;
  v43 = v45;
  if ( (_DWORD)v38 && v39 >= v37 && v39 <= &v37[v38] )
    goto LABEL_50;
  v44 = 0;
LABEL_60:
  v46 = v146;
  v175 = v44;
  v47 = v43 + ((v38 + 7) & 0xFFFFFFF8);
  v9 = *((_QWORD *)v146 + 4) == 0;
  v151 = v47;
  if ( v9 )
  {
    CmsRowWithBuffer::Reset(v146);
    v47 = v151;
    v44 = v175;
    LOWORD(v40) = v147;
    LOBYTE(v41) = v148;
    v46 = v146;
  }
  if ( v47 > *((_DWORD *)v46 + 11) )
  {
    v49 = (unsigned __int64)v47 >> 3;
    v48 = 8 * v49;
    if ( !is_mul_ok(v49, 8u) )
      v48 = -1;
    Pool2 = ExAllocatePool2(66, v48, 1766871885);
    v152 = Pool2;
    if ( !Pool2 )
      goto LABEL_186;
    v46 = v146;
    if ( (*((_BYTE *)v146 + 40) & 1) != 0 )
    {
      v137 = (void *)*((_QWORD *)v146 + 4);
      if ( v137 )
      {
        ExFreePoolWithTag(v137, 0);
        Pool2 = v152;
        v46 = v146;
      }
    }
    *((_BYTE *)v46 + 40) |= 1u;
    v44 = v175;
    LOWORD(v40) = v147;
    LOBYTE(v41) = v148;
    *((_QWORD *)v46 + 4) = Pool2;
    *((_DWORD *)v46 + 11) = v151;
  }
  v51 = *((_QWORD *)v46 + 4);
  v52 = v41 & 3 | 4;
  v53 = (unsigned __int16)v40;
  *((_QWORD *)v46 + 1) = v51;
  *(_DWORD *)v46 = (unsigned __int16)v40;
  *((_QWORD *)v46 + 3) = v51;
  *((_DWORD *)v46 + 4) = v38;
  if ( v44 )
  {
    v51 += (unsigned int)((_DWORD)v39 - (_DWORD)v37);
    *((_QWORD *)v46 + 1) = v51;
  }
  else
  {
    if ( (_WORD)v40 && (_DWORD)v38 && &v39[(unsigned __int16)v40] >= v37 && &v39[(unsigned __int16)v40] <= &v37[v42] )
      v54 = (_WORD)v37 - (_WORD)v39;
    else
      v54 = (v40 + 7) & 0xFFF8;
    *((_QWORD *)v46 + 3) = v51 + v54;
  }
  if ( (_DWORD)v53 )
    *(_QWORD *)((((_DWORD)v53 + 7) & 0xFFFFFFF8) + v51 - 8) = 0;
  v55 = *((_DWORD *)v46 + 4);
  if ( v55 )
    *(_QWORD *)(((v55 + 7) & 0xFFFFFFF8) + *((_QWORD *)v46 + 3) - 8LL) = 0;
  *((_WORD *)v46 + 2) = v52;
  if ( (unsigned __int64)(v39 - 2) <= 2 )
    *((_QWORD *)v46 + 1) = v39;
  else
    memmove(*((void **)v46 + 1), v39, v53);
  v56 = v42;
  v13 = v146;
  memmove(*((void **)v146 + 3), v37, v56);
  v58 = &v37[(unsigned int)v149];
  if ( v7 <= 0 )
  {
    if ( (unsigned int)-v7 <= *((_DWORD *)v58 + 2) )
      goto LABEL_96;
    v6 = v172;
LABEL_237:
    v31 = -1073741823;
    goto LABEL_28;
  }
  v59 = *(_DWORD *)v146;
  v60 = (char *)*((_QWORD *)v146 + 1);
  if ( (*((_BYTE *)v146 + 40) & 2) != 0 )
  {
    v59 += 8;
    v60 -= 8;
  }
  v61 = *((_DWORD *)v146 + 4) + 7;
  v152 = v59 + 7;
  v57 = 4294967288LL;
  v62 = ((v59 + 7) & 0xFFFFFFF8) + ((v7 + v61) & 0xFFFFFFF8);
  if ( v62 <= *((_DWORD *)v146 + 11) )
  {
    v13 = v146;
  }
  else
  {
    v63 = 8 * ((unsigned __int64)v62 >> 3);
    if ( !is_mul_ok((unsigned __int64)v62 >> 3, 8u) )
      v63 = -1;
    v64 = (struct _SmsRedoMarker *)ExAllocatePool2(66, v63, 1766871885);
    v149 = v64;
    if ( !v64 )
      goto LABEL_186;
    memmove(v64, v60, v59);
    v65 = v149;
    v66 = (char *)v149 + ((unsigned int)v152 & 0xFFFFFFF8);
    memmove(v66, *((const void **)v146 + 3), *((unsigned int *)v146 + 4));
    v67 = v146;
    v68 = (struct _SmsRedoMarker *)((char *)v149 + 8);
    v69 = *((_BYTE *)v146 + 40);
    if ( (v69 & 2) == 0 )
      v68 = v149;
    *((_QWORD *)v146 + 1) = v68;
    *((_QWORD *)v146 + 3) = v66;
    if ( (v69 & 1) != 0 )
    {
      v70 = (void *)*((_QWORD *)v146 + 4);
      if ( v70 )
      {
        ExFreePoolWithTag(v70, 0);
        v67 = v146;
      }
    }
    *((_DWORD *)v67 + 11) = v62;
    v13 = v146;
    *((_QWORD *)v67 + 4) = v65;
    *((_BYTE *)v146 + 40) |= 1u;
  }
LABEL_96:
  v71 = (unsigned int *)*((_QWORD *)v13 + 3);
  v72 = *v71;
  v176 = *v71;
  if ( (*(_QWORD *)v4 & 2) != 0 )
  {
    v73 = v172;
    goto LABEL_107;
  }
  if ( (*(_QWORD *)v4 & 0x1000LL) != 0 )
  {
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    LOBYTE(v57) = 1;
    CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)v4 + 1), 0x20000000, v57);
    goto LABEL_186;
  }
  v114 = qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v114 < 0x60u )
  {
    v114 = 0;
    v115 = 112;
    goto LABEL_165;
  }
  if ( *(_BYTE *)(v114 + 8) )
  {
    v140 = (struct _NPAGED_LOOKASIDE_LIST *)(v114 + 64);
    if ( *(_BYTE *)(v114 + 9) )
      v141 = ExAllocateFromNPagedLookasideList(v140);
    else
      v141 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v140);
LABEL_99:
    v74 = v141;
    if ( v141 )
    {
LABEL_100:
      *(_QWORD *)v74 = v114;
      v74 += 4;
      goto LABEL_101;
    }
    goto LABEL_191;
  }
  if ( (int)*(_QWORD *)(v114 + 88) > (int)HIDWORD(*(_QWORD *)(v114 + 88)) )
  {
    v122 = _InterlockedDecrement((volatile signed __int32 *)(v114 + 88));
    if ( v122 >= *(_DWORD *)(v114 + 92) && v122 >= 0 )
    {
      v141 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v114 + 64));
      goto LABEL_99;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v114 + 88));
  }
LABEL_191:
  v115 = *(unsigned int *)(v114 + 4);
LABEL_165:
  v116 = ExAllocatePool2(66, v115, 1766871885);
  v74 = (_DWORD *)v116;
  if ( (v116 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( v116 )
    goto LABEL_100;
LABEL_101:
  if ( !v74 )
  {
LABEL_186:
    v13 = v146;
    v31 = -1073741670;
    v6 = v172;
    goto LABEL_28;
  }
  v74[4] = 52;
  *((_QWORD *)v74 + 5) = a3;
  v74[3] = 4;
  v74[2] = 4;
  *((_WORD *)v74 + 10) = 0;
  *((_OWORD *)v74 + 3) = 0;
  *((_OWORD *)v74 + 4) = 0;
  *((_QWORD *)v74 + 10) = 0;
  v74[8] = 0;
  v73 = v172;
  *((_QWORD *)v74 + 3) = v74 + 22;
  v74[22] = 0;
  v75 = (_DWORD *)*((_QWORD *)v74 + 3);
  *v75 = *((_DWORD *)v172 + 7);
  v74[2] = 4;
  v74[8] = 0;
  *((_QWORD *)v74 + 5) = a3;
  *((_OWORD *)v74 + 3) = 0;
  *((_OWORD *)v74 + 4) = 0;
  *((_QWORD *)v74 + 10) = 0;
  v76 = v74[2];
  if ( v76 )
  {
    v77 = (_DWORD *)*((_QWORD *)v74 + 3);
    if ( v75 )
    {
      if ( v75 != v77 )
        memmove(v77, v75, v76);
    }
    else
    {
      memset(v77, 0, (unsigned int)v74[2]);
    }
  }
  *(_QWORD *)v74 = *((_QWORD *)v4 + 18);
  *((_QWORD *)v4 + 18) = v74;
  v72 = v176;
LABEL_107:
  v78 = (_DWORD **)*((_QWORD *)v73 + 4);
  v79 = v150;
  *((_DWORD *)v73 + 7) = v150;
  if ( (*(_DWORD *)(*((_QWORD *)*v78 + 3) + 44LL) & 1) != 0 )
    *v78[2] = v79;
  v80 = (char *)v71 + v72;
  v81 = *((_QWORD *)v58 + 3);
  v82 = v7 + *((_DWORD *)v58 + 8);
  v83 = v58[13];
  v84 = v58[12];
  v85 = *((_QWORD *)a3 + 3);
  if ( (unsigned int)(v82 - 40) > 8 )
    *(_QWORD *)&v80[v82 - 8] = 0;
  *(_DWORD *)v80 = 40;
  *((_WORD *)v80 + 7) = 0;
  *((_DWORD *)v80 + 1) = 40;
  *((_DWORD *)v80 + 2) = v82 - 40;
  v80[12] = v84;
  v80[13] = v83;
  *((_DWORD *)v80 + 4) = v82;
  *((_DWORD *)v80 + 8) = v82;
  *((_DWORD *)v80 + 5) = 0;
  *((_DWORD *)v80 + 9) = 0;
  *((_QWORD *)v80 + 3) = v81;
  if ( (*(_DWORD *)(v85 + 44) & 2) != 0 )
    v80[13] = v83 | 4;
  v86 = *((_QWORD *)a3 + 3);
  v87 = 0;
  v88 = *((_DWORD *)v58 + 5);
  v152 = v86;
  *((_DWORD *)v80 + 5) = v88;
  *((_DWORD *)v80 + 4) = v82 - 4 * v88;
  if ( v88 )
  {
    v89 = v152;
    do
    {
      v90 = v87;
      v91 = v87++;
      v92 = (unsigned int)v91;
      if ( v90 >= *((_DWORD *)v58 + 5) )
      {
        v93 = 0;
      }
      else
      {
        _mm_lfence();
        v93 = (unsigned int *)&v58[*(unsigned __int16 *)&v58[4 * v91 + *((unsigned int *)v58 + 4)]];
      }
      v94 = &v80[*((unsigned int *)v80 + 1)];
      if ( (v93[2] & 0x40) != 0 )
        v95 = (*((unsigned __int16 *)v93 + 5) + 7) & 0xFFFFFFF8;
      else
        v95 = *v93;
      memmove(&v80[*((unsigned int *)v80 + 1)], v93, v95);
      v96 = *((unsigned int *)v80 + 4) + 4 * v92;
      *(_WORD *)&v80[v96] = (_WORD)v94 - (_WORD)v80;
      if ( (((*(_BYTE *)(v89 + 44) & 2) != 0) & ((unsigned __int8)v80[13] >> 3)) == 0
        || (v97 = *((_WORD *)v94 + 4), (v97 & 2) != 0) )
      {
        v99 = -1;
      }
      else
      {
        if ( (v97 & 0x40) != 0 )
          v98 = v94 + 12;
        else
          v98 = &v94[*((unsigned __int16 *)v94 + 2)];
        v99 = *(_WORD *)v98 - *((_WORD *)v80 + 12);
      }
      *(_WORD *)&v80[v96 + 2] = v99;
      if ( (v94[8] & 0x40) != 0 )
        v100 = (*((unsigned __int16 *)v94 + 5) + 7) & 0xFFFFFFF8;
      else
        v100 = *(_DWORD *)v94;
      *((_DWORD *)v80 + 1) += v100;
      if ( (v94[8] & 0x40) != 0 )
        v101 = (*((unsigned __int16 *)v94 + 5) + 7) & 0xFFFFFFF8;
      else
        v101 = *(_DWORD *)v94;
      *((_DWORD *)v80 + 2) = *((_DWORD *)v80 + 2) - v101 - 4;
      --v88;
    }
    while ( v88 );
    v4 = a2;
  }
  v6 = v172;
  v13 = v146;
  v102 = v150;
  if ( (*(_DWORD *)(*(_QWORD *)(**((_QWORD **)v172 + 4) + 24LL) + 44LL) & 1) != 0 )
    **((_DWORD **)v146 + 1) = v150;
  *((_DWORD *)v146 + 4) = v102;
  v103 = *(_WORD *)(v162 + 8);
  v104 = **((_QWORD **)v172 + 4);
  v105 = v103 & 0x40;
  if ( (v103 & 0x40) != 0 )
    v106 = *(unsigned __int16 *)(v162 + 10);
  else
    v106 = *(_DWORD *)(v162 + 12);
  if ( v102 == v106 )
  {
    v31 = CmsBPlusTable::UpdateInIndex((CmsBPlusTable *)v104, (__int64)v4, (__int64)v146, v161, 0);
  }
  else
  {
    v149 = 0;
    v107 = *((_BYTE *)v161[1] + 13) & 2;
    if ( (*(_BYTE *)(v104 + 15) & 0x40) != 0 )
      goto LABEL_264;
    v117 = *((_QWORD *)v4 + 52);
    v118 = *(struct _SmsRedoMarker **)(v117 + 8);
    if ( !v118 )
      v118 = (struct _SmsRedoMarker *)(v117 + 8);
    v119 = v103 & 3;
    v149 = v118;
    if ( v105 )
    {
      v164 = 12;
      v120 = (CmsTxMemLog *)(v162 + 12);
    }
    else
    {
      v119 |= 4u;
      v164 = *(unsigned __int16 *)(v162 + 6);
      v120 = (CmsTxMemLog *)(v162 + *(unsigned __int16 *)(v162 + 4));
    }
    v166 = v120;
    v165 = v119;
    if ( MsDisableRedoLogging )
      goto LABEL_264;
    if ( (*(_QWORD *)v4 & 0x2000000000LL) != 0 )
      goto LABEL_264;
    if ( (*(_QWORD *)v4 & 0x20) != 0 )
      goto LABEL_264;
    v121 = *((_QWORD *)v4 + 1);
    if ( v121 )
    {
      if ( (*(_DWORD *)(v121 + 3460) & 0x400001) != 0 )
        goto LABEL_264;
    }
    v31 = CmsTxMemLog::AddRedoRecord(v117, (_QWORD *)v104, 2u, &v164, 0, 0, 0, 0, v145, 0, 0);
    if ( CmsBPlusTable::HasGlobalBindingSemantics((CmsBPlusTable *)v104) )
    {
      *(_QWORD *)v4 |= 0x80000000000uLL;
      *((_QWORD *)v4 + 14) = v104;
    }
    if ( v31 >= 0 )
    {
LABEL_264:
      v31 = CmsBPlusTable::DeleteIndexEntry((CmsBPlusTable *)v104, v4, (struct SmsLookupStack *)v161, 0);
      if ( v31 >= 0 )
      {
        if ( 100 * *((_DWORD *)v161[1] + 2) / (unsigned int)(*((_DWORD *)v161[1] + 8) - *(_DWORD *)v161[1]) >= 0x19 )
        {
          v108 = v161[0];
          v109 = *((_QWORD *)v161[0] + 12);
          v110 = *(_QWORD *)(v109 + 160);
          if ( (*(_QWORD *)v4 & 0x800LL) != 0 && (*(_QWORD *)v4 & 0x200LL) == 0 )
            v110 = *(_QWORD *)(v109 + 168);
          v111 = *((_QWORD *)v161[0] + 12);
          if ( *(_QWORD *)(v109 + 64) != v109 )
          {
            do
              v111 = *(_QWORD *)(v111 + 64);
            while ( *(_QWORD *)(v111 + 64) != v111 );
          }
          if ( *(_BYTE *)(*(_QWORD *)(v111 + 112) + 11LL) != 2
            && *(_QWORD *)(*(_QWORD *)(v109 + 32) + 40LL)
            && (v110 != *(_QWORD *)(v109 + 168) || *(_QWORD *)(v109 + 160) == *(_QWORD *)(v109 + 168))
            && !*((_BYTE *)v161[0] + 392)
            && (*((_DWORD *)v161[0] + 138) & 0x100000) == 0 )
          {
            v112 = *(_QWORD *)(*(_QWORD *)(v109 + 32) + 40LL);
            while ( 1 )
            {
              v113 = *((_DWORD *)v108 + 138);
              if ( (v113 & 0x20000) != 0 )
                break;
              if ( v113 == _InterlockedCompareExchange((volatile signed __int32 *)v108 + 138, v113 | 0x20000, v113) )
              {
                do
                {
                  v143 = *(_QWORD *)(v112 + 64);
                  *((_QWORD *)v108 + 86) = v143;
                  if ( v143 )
                    v144 = *(_DWORD *)(v143 + 696) + 1;
                  else
                    v144 = 1;
                  *((_DWORD *)v108 + 174) = v144;
                }
                while ( _InterlockedCompareExchange64(
                          (volatile signed __int64 *)(v112 + 64),
                          (signed __int64)v108,
                          v143) != *((_QWORD *)v108 + 86) );
                if ( (*(_DWORD *)(v109 + 188) & 1) == 0 )
                  _InterlockedOr((volatile signed __int32 *)(v109 + 188), 1u);
                break;
              }
            }
          }
        }
        if ( (*(_DWORD *)(*(_QWORD *)(v104 + 24) + 44LL) & 0x1000) != 0
          && v107
          && (*(_DWORD *)(v104 + 188) & 0x80u) == 0 )
        {
          _InterlockedOr((volatile signed __int32 *)(v104 + 188), 0x80u);
        }
        if ( !*((_BYTE *)v161[1] + 12) && _InterlockedDecrement64((volatile signed __int64 *)(v104 + 48)) < 0 )
          _InterlockedIncrement64((volatile signed __int64 *)(v104 + 48));
      }
    }
    if ( v161[0] )
      CmsVolume::Unpin(*((CmsVolume **)v4 + 1), v4, v161, 3u);
    if ( v31 < 0 )
    {
      CmsTxMemLog::DiscardPendingRecordsFrom(*((CmsTxMemLog **)v4 + 52), &v149);
      v6 = v172;
    }
    else
    {
      v6 = v172;
      v31 = (*(__int64 (__fastcall **)(__int64, struct CmsTransactionContext *, CmsRowWithBuffer *, __int64, _DWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v104 + 88LL))(
              v104,
              v4,
              v146,
              50,
              0,
              0,
              0,
              0);
    }
  }
LABEL_28:
  if ( v161[0] )
    CmsVolume::Unpin(*((CmsVolume **)v4 + 1), v4, v161, 3u);
  v32 = (CmsVolume *)*((_QWORD *)v6 + 2);
  if ( v31 >= 0 )
  {
    v159 = 0;
    --*((_WORD *)v4 + 106);
    if ( v155 )
      --*((_WORD *)v4 + 107);
    if ( HIBYTE(v154) )
    {
      v135 = (CmsTxMemLog *)*((_QWORD *)v4 + 52);
      v136 = (CmsVolume *)((char *)v32 + 2880);
      if ( *(_QWORD *)v135 )
        CmsTxMemLog::MergeTxLog(v166, (struct CmsTxMemLog *)&v160, v136);
      else
        CmsTxMemLog::DiscardPendingRecords(v135, v136);
      if ( (v158 & 0x80000000000LL) != 0 )
      {
        v142 = v167;
        *(_QWORD *)v4 |= 0x80000000000uLL;
        *((_QWORD *)v4 + 14) = v142;
      }
      *((_QWORD *)v4 + 52) = v166;
    }
    *(_QWORD *)v4 |= v158 & 0x100000000000LL;
    if ( *((_BYTE *)v4 + 131) != *((_BYTE *)v4 + 130) && (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    v34 = v156;
    v35 = v157;
    *((_BYTE *)v4 + 131) = v156;
    *((_BYTE *)v4 + 132) = v35;
    *((_BYTE *)v4 + 130) = v34;
  }
  else
  {
    CmsVolume::AbortTopLevelAction(v32, v4, (struct _SmsTopLevelAction *)v153);
  }
  if ( v13 )
  {
    *(_DWORD *)v13 = 0;
    *((_DWORD *)v4 + 56) &= ~(1 << ((v13 - v4 - 2816) / 80));
  }
  if ( !v168 )
    *(_QWORD *)v4 &= ~0x2000000000uLL;
  if ( v161[0] && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x14001b120  mov     [rsp-8+arg_18], r9d
0x14001b125  mov     [rsp-8+arg_8], rdx
0x14001b12a  mov     [rsp-8+arg_0], rcx
0x14001b12f  push    rbp
0x14001b130  push    rbx
0x14001b131  push    rdi
0x14001b132  push    r12
0x14001b134  push    r13
0x14001b136  push    r14
0x14001b138  push    r15
0x14001b13a  lea     rbp, [rsp-40h]
0x14001b13f  sub     rsp, 140h
0x14001b146  xor     eax, eax
0x14001b148  xorps   xmm0, xmm0
0x14001b14b  mov     [rbp+70h+var_90], rax
0x14001b14f  mov     rdi, rdx
0x14001b152  mov     edx, [rdx+0E0h]
0x14001b158  xor     r10d, r10d
0x14001b15b  mov     eax, edx
0x14001b15d  mov     r15, rcx
0x14001b160  not     eax
0x14001b162  mov     r14d, r9d
0x14001b165  and     eax, 3Fh
0x14001b168  mov     r13, r8
0x14001b16b  bsf     ecx, eax
0x14001b16e  movups  xmmword ptr [rbp+70h+var_B0], xmm0
0x14001b172  mov     [rbp+70h+var_B8], ecx
0x14001b175  mov     r9d, 1
0x14001b17b  movups  [rbp+70h+var_A0], xmm0
0x14001b17f  jz      loc_14001C0DB
0x14001b185  mov     eax, r9d
0x14001b188  lea     r12, [rdi+0B00h]
0x14001b18f  shl     eax, cl
0x14001b191  lea     rcx, [rcx+rcx*4]
0x14001b195  shl     rcx, 4
0x14001b199  or      eax, edx
0x14001b19b  mov     [rdi+0E0h], eax
0x14001b1a1  add     r12, rcx
0x14001b1a4  mov     eax, [rbp+70h+var_3C]
0x14001b1a7  movups  [rbp+70h+var_50], xmm0
0x14001b1ab  movups  xmmword ptr [r12], xmm0
0x14001b1b0  mov     [rcx+rdi+0B10h], r10d
0x14001b1b8  mov     [rcx+rdi+0B14h], eax
0x14001b1bf  mov     [rcx+rdi+0B18h], r10
0x14001b1c7  mov     rdx, [rdi]
0x14001b1ca  mov     r8, 2000000000h
0x14001b1d4  mov     rax, rdx
0x14001b1d7  mov     [rsp+170h+var_110], r12
0x14001b1dc  and     rax, r8
0x14001b1df  mov     [rbp+70h+var_D0], r10w
0x14001b1e4  mov     [rbp+70h+var_CE], r10b
0x14001b1e8  mov     [rbp+70h+var_C0], r10d
0x14001b1ec  mov     [rbp+70h+var_70], rax
0x14001b1f0  bt      rdx, 15h
0x14001b1f5  jb      loc_14001C05A
0x14001b1fb  inc     word ptr [rdi+0D4h]
0x14001b202  movzx   eax, word ptr [rdi+0D4h]
0x14001b209  movzx   ebx, byte ptr [rdi+84h]
0x14001b210  mov     [rbp+70h+var_C0], eax
0x14001b213  mov     rax, [rdi+90h]
0x14001b21a  mov     [rbp+70h+var_E8], rax
0x14001b21e  mov     rax, [rdi+1A0h]
0x14001b225  add     rax, 8
0x14001b229  mov     [rbp+70h+var_CE], r10b
0x14001b22d  mov     rcx, [rax]
0x14001b230  test    rcx, rcx
0x14001b233  mov     [rbp+70h+var_C8], rdx
0x14001b237  mov     [rbp+70h+var_CC], bl
0x14001b23a  cmovz   rcx, rax
0x14001b23e  mov     byte ptr [rbp+70h+var_D0+1], r10b
0x14001b242  mov     rax, [rdi+0C8h]
0x14001b249  mov     [rbp+70h+var_D8], rax
0x14001b24d  mov     rax, 0FFFFEFFFFFFFFFFFh
0x14001b257  mov     [rbp+70h+var_E0], rcx
0x14001b25b  and     rdx, rax
0x14001b25e  movzx   ecx, byte ptr [rdi+83h]
0x14001b265  mov     [rdi], rdx
0x14001b268  mov     [rbp+70h+var_CD], cl
0x14001b26b  cmp     cl, 0Dh
0x14001b26e  jnb     short loc_14001B287
0x14001b270  movzx   eax, cl
0x14001b273  cmp     [rdi+rax*8+230h], r10
0x14001b27b  jnz     loc_14001BDB8
0x14001b281  mov     [rdi+83h], cl
0x14001b287  cmp     bl, 0Dh
0x14001b28a  jnb     short loc_14001B2A3
0x14001b28c  movzx   eax, bl
0x14001b28f  cmp     [rdi+rax*8+1A8h], r10
0x14001b297  jnz     loc_14001B860
0x14001b29d  mov     [rdi+84h], bl
0x14001b2a3  movzx   eax, byte ptr [rdi+82h]
0x14001b2aa  cmp     [rdi+83h], al
0x14001b2b0  jb      loc_14001C070
0x14001b2b6  or      [rdi], r8
0x14001b2b9  movzx   eax, byte ptr [rdi+83h]
0x14001b2c0  mov     [rdi+82h], al
0x14001b2c6  mov     r8d, [r15+1Ch]
0x14001b2ca  add     r8d, r14d
0x14001b2cd  mov     [rsp+170h+arg_10], rsi
0x14001b2d5  mov     [rsp+170h+var_F8], r8d
0x14001b2da  js      loc_14001C0E3
0x14001b2e0  test    r14b, 7
0x14001b2e4  jnz     loc_14001C17D
0x14001b2ea  mov     rdx, [r13+18h]
0x14001b2ee  mov     r11d, 0FFFFFFF8h
0x14001b2f4  mov     ebx, [rdx+2Ch]
0x14001b2f7  and     ebx, 1000h
0x14001b2fd  jz      loc_14001C0ED
0x14001b303  mov     rax, [r13+70h]
0x14001b307  mov     rcx, [rax+10h]
0x14001b30b  mov     rax, [rcx+0E18h]
0x14001b312  cmp     [rax+8], r10w
0x14001b317  jnz     loc_14001B819
0x14001b31d  mov     rax, r10
0x14001b320  lea     ecx, [rax+43h]
0x14001b323  mov     eax, [rdx+1Ch]
0x14001b326  and     ecx, r11d
0x14001b329  add     eax, 57h ; 'W'
0x14001b32c  add     eax, ecx
0x14001b32e  lea     rcx, [rdx+18h]
0x14001b332  and     eax, r11d
0x14001b335  cmp     r8d, eax
0x14001b338  jb      loc_14001C17D
0x14001b33e  test    ebx, ebx
0x14001b340  jz      loc_14001B4A0
0x14001b346  cmp     [r15+0Bh], r10b
0x14001b34a  mov     rcx, r15
0x14001b34d  mov     edx, [rdx+28h]
0x14001b350  cmovnz  rcx, r10
0x14001b354  test    rcx, rcx
0x14001b357  jz      short loc_14001B360
0x14001b359  mov     rax, [rcx+20h]
0x14001b35d  sub     edx, [rax+8]
0x14001b360  cmp     r8d, edx
0x14001b363  ja      loc_14001C17D
0x14001b369  mov     r8, [r15+20h]
0x14001b36d  lea     rdx, [rbp+70h+var_B0]
0x14001b371  mov     [rsp+170h+var_148], r10
0x14001b376  mov     qword ptr [rsp+170h+var_150], rdx
0x14001b37b  mov     rdx, rdi
0x14001b37e  mov     rcx, [r8]
0x14001b381  add     r8, 8
0x14001b385  mov     rax, [rcx]
0x14001b388  mov     rax, [rax+50h]
0x14001b38c  call    _guard_dispatch_icall
0x14001b391  mov     esi, eax
0x14001b393  test    eax, eax
0x14001b395  jns     loc_14001B4BC
0x14001b39b  mov     r13, 80000000000h
0x14001b3a5  xor     ebx, ebx
0x14001b3a7  cmp     [rbp+70h+var_B0], 0
0x14001b3ac  jnz     loc_14001B7FE
0x14001b3b2  mov     rcx, [r15+10h]; this
0x14001b3b6  test    esi, esi
0x14001b3b8  jns     short loc_14001B437
0x14001b3ba  lea     r8, [rbp+70h+var_E8]; struct _SmsTopLevelAction *
0x14001b3be  mov     rdx, rdi; struct CmsTransactionContext *
0x14001b3c1  call    ?AbortTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@@Z; CmsVolume::AbortTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *)
0x14001b3c6  test    r12, r12
0x14001b3c9  jz      short loc_14001B403
0x14001b3cb  mov     [r12], ebx
0x14001b3cf  mov     rax, 6666666666666667h
0x14001b3d9  sub     r12, rdi
0x14001b3dc  sub     r12, 0B00h
0x14001b3e3  imul    r12
0x14001b3e6  mov     eax, 1
0x14001b3eb  sar     rdx, 5
0x14001b3ef  mov     rcx, rdx
0x14001b3f2  shr     rcx, 3Fh
0x14001b3f6  add     rcx, rdx
0x14001b3f9  shl     eax, cl
0x14001b3fb  not     eax
0x14001b3fd  and     [rdi+0E0h], eax
0x14001b403  cmp     [rbp+70h+var_70], 0
0x14001b408  jz      loc_14001C287
0x14001b40e  cmp     [rbp+70h+var_B0], 0
0x14001b413  jnz     loc_14001C0C5
0x14001b419  mov     eax, esi
0x14001b41b  mov     rsi, [rsp+170h+arg_10]
0x14001b423  add     rsp, 140h
0x14001b42a  pop     r15
0x14001b42c  pop     r14
0x14001b42e  pop     r13
0x14001b430  pop     r12
0x14001b432  pop     rdi
0x14001b433  pop     rbx
0x14001b434  pop     rbp
0x14001b435  retn
0x14001b437  mov     eax, 0FFFFh
0x14001b43c  mov     [rbp+70h+var_C0], ebx
0x14001b43f  add     [rdi+0D4h], ax
0x14001b446  cmp     [rbp+70h+var_CE], 0
0x14001b44a  jnz     loc_14001C256
0x14001b450  cmp     byte ptr [rbp+70h+var_D0+1], 0
0x14001b454  jnz     loc_14001C020
0x14001b45a  mov     rax, [rbp+70h+var_C8]
0x14001b45e  mov     rcx, 100000000000h
0x14001b468  and     rax, rcx
0x14001b46b  or      [rdi], rax
0x14001b46e  movzx   eax, byte ptr [rdi+82h]
0x14001b475  cmp     [rdi+83h], al
0x14001b47b  jnz     loc_14001C0AF
0x14001b481  movzx   ecx, [rbp+70h+var_CD]
0x14001b485  movzx   eax, [rbp+70h+var_CC]
0x14001b489  mov     [rdi+83h], cl
0x14001b48f  mov     [rdi+84h], al
0x14001b495  mov     [rdi+82h], cl
0x14001b49b  jmp     loc_14001B3C6
0x14001b4a0  mov     edx, [rcx]
0x14001b4a2  test    edx, edx
0x14001b4a4  jnz     loc_14001B360
0x14001b4aa  mov     rax, [r15+10h]
0x14001b4ae  mov     edx, [rax+0D44h]
0x14001b4b4  sub     edx, 50h ; 'P'
0x14001b4b7  jmp     loc_14001B360
0x14001b4bc  mov     rsi, [rbp+70h+var_B0]
0x14001b4c0  test    dword ptr [rsi+228h], 200000h
0x14001b4ca  jnz     loc_14001BECB
0x14001b4d0  mov     rcx, qword ptr [rbp+70h+var_A0]
0x14001b4d4  movzx   ebx, word ptr [rcx+0Ah]
0x14001b4d8  movzx   esi, word ptr [rcx+4]
0x14001b4dc  add     rbx, rcx
0x14001b4df  mov     r15d, [rcx+0Ch]
0x14001b4e3  add     rsi, rcx
0x14001b4e6  movzx   r9d, word ptr [rcx+6]
0x14001b4eb  movzx   r10d, word ptr [rcx+8]
0x14001b4f0  mov     ecx, 0FFF8h
0x14001b4f5  mov     eax, [rbx]
0x14001b4f7  mov     dword ptr [rsp+170h+var_100], eax
0x14001b4fb  mov     [rsp+170h+var_108], r9w
0x14001b501  mov     word ptr [rsp+170h+var_106], r10w
0x14001b507  test    r15d, r15d
0x14001b50a  jz      short loc_14001B523
0x14001b50c  cmp     rsi, rbx
0x14001b50f  jb      short loc_14001B523
0x14001b511  lea     rax, [rbx+r15]
0x14001b515  mov     r12d, r15d
0x14001b518  cmp     rsi, rax
0x14001b51b  ja      short loc_14001B523
0x14001b51d  xor     ecx, ecx
0x14001b51f  mov     dl, 1
0x14001b521  jmp     short loc_14001B56B
0x14001b523  mov     r12, r15
0x14001b526  test    r9w, r9w
0x14001b52a  jz      short loc_14001B54C
0x14001b52c  test    r15d, r15d
0x14001b52f  jz      short loc_14001B54C
0x14001b531  lea     rcx, [rsi+r9]
0x14001b535  cmp     rcx, rbx
0x14001b538  jb      short loc_14001B547
0x14001b53a  lea     rax, [rbx+r15]
0x14001b53e  cmp     rcx, rax
0x14001b541  jbe     loc_14001C12C
0x14001b547  mov     ecx, 0FFF8h
0x14001b54c  lea     eax, [r9+7]
0x14001b550  and     ax, cx
0x14001b553  movzx   ecx, ax
0x14001b556  test    r15d, r15d
0x14001b559  jz      short loc_14001B569
0x14001b55b  cmp     rsi, rbx
0x14001b55e  jb      short loc_14001B569
0x14001b560  lea     rax, [rbx+r15]
0x14001b564  cmp     rsi, rax
0x14001b567  jbe     short loc_14001B51F
0x14001b569  xor     dl, dl
0x14001b56b  mov     r11, [rsp+170h+var_110]
0x14001b570  lea     eax, [r15+7]
0x14001b574  mov     r8d, 0FFFFFFF8h
0x14001b57a  mov     byte ptr [rbp+70h+arg_18], dl
0x14001b580  and     eax, r8d
0x14001b583  add     eax, ecx
0x14001b585  cmp     qword ptr [r11+20h], 0
0x14001b58a  mov     [rsp+170h+var_F4], eax
0x14001b58e  jz      loc_14001C137
0x14001b594  mov     r8, 0FFFFFFFFFFFFFFFFh
0x14001b59b  cmp     eax, [r11+2Ch]
0x14001b59f  jbe     short loc_14001B60E
0x14001b5a1  mov     ecx, eax
0x14001b5a3  mov     eax, 8
0x14001b5a8  shr     rcx, 3
0x14001b5ac  mul     rcx
0x14001b5af  mov     ecx, 42h ; 'B'
0x14001b5b4  cmovb   rax, r8
0x14001b5b8  mov     r8d, 6950534Dh
0x14001b5be  mov     rdx, rax
0x14001b5c1  call    cs:__imp_ExAllocatePool2
0x14001b5c8  nop     dword ptr [rax+rax+00h]
0x14001b5cd  mov     [rbp+70h+var_F0], rax
0x14001b5d1  test    rax, rax
0x14001b5d4  jz      loc_14001BE68
0x14001b5da  mov     r11, [rsp+170h+var_110]
0x14001b5df  test    byte ptr [r11+28h], 1
0x14001b5e4  jnz     loc_14001C086
0x14001b5ea  or      byte ptr [r11+28h], 1
0x14001b5ef  movzx   edx, byte ptr [rbp+70h+arg_18]
0x14001b5f6  movzx   r9d, [rsp+170h+var_108]
0x14001b5fc  movzx   r10d, word ptr [rsp+170h+var_106]
0x14001b602  mov     [r11+20h], rax
0x14001b606  mov     eax, [rsp+170h+var_F4]
0x14001b60a  mov     [r11+2Ch], eax
  ... truncated ...
```
