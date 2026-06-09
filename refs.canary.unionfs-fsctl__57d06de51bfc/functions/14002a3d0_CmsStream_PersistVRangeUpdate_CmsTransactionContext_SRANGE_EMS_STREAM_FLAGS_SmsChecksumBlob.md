# CmsStream::PersistVRangeUpdate(CmsTransactionContext *,_SRANGE,EMS_STREAM_FLAGS,SmsChecksumBlob *)

- ea: `0x14002a3d0`
- end: `0x14002b038`
- name: `?PersistVRangeUpdate@CmsStream@@AEAAJPEAVCmsTransactionContext@@U_SRANGE@@W4EMS_STREAM_FLAGS@@PEAUSmsChecksumBlob@@@Z`
- size: `3176`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002a0f0`
- `0x140141d5c`

## callees

- `0x140016a00`
- `0x14001cbc0`
- `0x14001db90`
- `0x1400233e0`
- `0x140023ac0`
- `0x140028a20`
- `0x140029570`
- `0x14002a3d0`
- `0x14002b110`
- `0x14003234c`
- `0x1400325d0`
- `0x140036df0`
- `0x14006dc40`
- `0x1400729a0`
- `0x140078b70`
- `0x14007aea0`
- `0x14007b060`
- `0x14007b360`
- `0x14008e2f0`
- `0x1400a1100`
- `0x1400ae69c`
- `0x1400aebe8`
- `0x1400b494c`
- `0x1400c4acc`
- `0x1400c8574`
- `0x14013bbd0`
- `0x14014f738`
- `0x1401e9ce0`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14002ab86`
- `ntoskrnl!KdDebuggerEnabled` at `0x14002ade4`
- `ntoskrnl!KdDebuggerEnabled` at `0x14002adfa`
- `ntoskrnl!KdDebuggerEnabled` at `0x14002ae10`
- `ntoskrnl!KdDebuggerEnabled` at `0x14002ae2a`
- `ntoskrnl!KdDebuggerEnabled` at `0x14002ae40`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002ae89`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002ae89`
- `ntoskrnl!ExAllocatePool2` at `0x14002a64b`
- `ntoskrnl!ExAllocatePool2` at `0x14002a64b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002a610`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002a610`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f11f4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f11f4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002aea6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002aea6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a81a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a81a`

## string_xrefs

- `0x14002a662`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsStream::PersistVRangeUpdate(
        __int64 a1,
        unsigned __int64 *a2,
        __int64 *a3,
        int a4,
        struct SmsChecksumBlob *a5)
{
  __int64 v5; // r11
  char v9; // r12
  unsigned __int64 v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  bool v14; // zf
  unsigned __int64 v15; // rdx
  unsigned __int8 v16; // cl
  __int16 v17; // r10
  _QWORD *v18; // r9
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // r12
  __int64 v22; // rsi
  __int64 v23; // rdx
  __int64 Pool2; // rax
  _DWORD *v25; // rbx
  int v26; // ecx
  int v27; // ebx
  unsigned int v28; // esi
  unsigned __int64 v29; // xmm0_8
  unsigned int v30; // r12d
  unsigned __int64 v31; // r13
  char *v32; // r13
  unsigned __int64 v33; // rcx
  char v34; // al
  char v35; // cl
  unsigned __int8 v36; // al
  _QWORD *v38; // r9
  __int64 v39; // rdx
  _QWORD *v40; // rcx
  unsigned int v41; // eax
  __int64 *v42; // rcx
  char v43; // r8
  int v44; // r10d
  CmsTableSetBase *v45; // rcx
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // r12
  int v48; // eax
  struct SmsTableSetLookupStack *v49; // r8
  unsigned int v50; // r10d
  unsigned int v51; // eax
  int v52; // eax
  unsigned int v53; // r12d
  unsigned int v54; // ecx
  __int64 v55; // rcx
  CmsTableSetBase *v56; // rdx
  unsigned __int64 v57; // rdx
  char *v58; // r8
  unsigned __int64 v59; // rax
  unsigned __int64 v60; // rcx
  struct _SRANGE *v61; // rdx
  CmsTxMemLog *v62; // rcx
  _QWORD *v63; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v64; // rcx
  _DWORD *v65; // rax
  _QWORD *v66; // rcx
  struct CmsTransactionContext *v67; // rdx
  unsigned __int16 v68; // r9
  unsigned int v69; // r11d
  __int64 v70; // rcx
  unsigned __int64 v71; // xmm1_8
  unsigned __int64 v72; // rcx
  unsigned __int64 v73; // rax
  char v74; // cl
  unsigned __int64 v75; // rdx
  bool v76; // r8
  CmsTableSetBase *v77; // rcx
  struct SmsTableSetEntry *Entry; // rax
  CmsTableSetBase *v79; // r10
  unsigned int v80; // r11d
  unsigned __int64 v81; // r9
  unsigned __int64 v82; // r8
  int v83; // ecx
  int v84; // r10d
  __int64 v85; // rax
  __int64 v86; // r9
  int v87; // [rsp+20h] [rbp-E0h]
  struct CmsBPlusTable *v88; // [rsp+28h] [rbp-D8h]
  char v89; // [rsp+40h] [rbp-C0h]
  int v90; // [rsp+44h] [rbp-BCh]
  unsigned int v91; // [rsp+44h] [rbp-BCh]
  char v92; // [rsp+48h] [rbp-B8h]
  char v93; // [rsp+4Ch] [rbp-B4h]
  unsigned __int64 v94; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v95; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v96; // [rsp+60h] [rbp-A0h]
  int v97; // [rsp+68h] [rbp-98h]
  unsigned __int64 v98; // [rsp+70h] [rbp-90h]
  unsigned __int64 v99; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v100; // [rsp+80h] [rbp-80h]
  CmsTableSetBase *v101[2]; // [rsp+88h] [rbp-78h]
  _QWORD v102[3]; // [rsp+98h] [rbp-68h] BYREF
  __int16 v103; // [rsp+B0h] [rbp-50h]
  char v104; // [rsp+B2h] [rbp-4Eh]
  char v105; // [rsp+B3h] [rbp-4Dh]
  unsigned __int8 v106; // [rsp+B4h] [rbp-4Ch]
  unsigned __int64 v107; // [rsp+B8h] [rbp-48h]
  int v108; // [rsp+C0h] [rbp-40h]
  unsigned int v109; // [rsp+C8h] [rbp-38h] BYREF
  struct SmsChecksumBlob *v110; // [rsp+D0h] [rbp-30h]
  __int64 v111; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v112; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v113; // [rsp+E8h] [rbp-18h]
  __int64 Src; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v115; // [rsp+F8h] [rbp-8h] BYREF
  CmsTxMemLog *v116; // [rsp+100h] [rbp+0h]
  int v117[2]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 *v118; // [rsp+110h] [rbp+10h]
  _QWORD v119[2]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v120[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v121[3]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v122[24]; // [rsp+158h] [rbp+58h] BYREF
  __int16 v123; // [rsp+170h] [rbp+70h]
  char v124; // [rsp+172h] [rbp+72h]
  int v125; // [rsp+180h] [rbp+80h]
  __int128 v126; // [rsp+188h] [rbp+88h] BYREF
  int v127; // [rsp+198h] [rbp+98h]
  __int64 v128; // [rsp+1A0h] [rbp+A0h]
  _OWORD v129[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  char v130[16]; // [rsp+1C8h] [rbp+C8h] BYREF
  char v131[16]; // [rsp+1D8h] [rbp+D8h] BYREF
  char v132[40]; // [rsp+1E8h] [rbp+E8h] BYREF
  __int128 v133; // [rsp+210h] [rbp+110h] BYREF
  int v134; // [rsp+220h] [rbp+120h]
  int v135; // [rsp+224h] [rbp+124h]
  __int64 v136; // [rsp+228h] [rbp+128h]
  PVOID P; // [rsp+230h] [rbp+130h]
  char v138; // [rsp+238h] [rbp+138h]
  int v139; // [rsp+23Ch] [rbp+13Ch]
  char v140; // [rsp+240h] [rbp+140h] BYREF
  struct SmsPage *v141[2]; // [rsp+260h] [rbp+160h] BYREF
  __int128 v142; // [rsp+270h] [rbp+170h]
  __int64 v143; // [rsp+280h] [rbp+180h]
  __int64 v144; // [rsp+288h] [rbp+188h]
  int v145; // [rsp+290h] [rbp+190h]
  unsigned __int64 v146; // [rsp+298h] [rbp+198h]
  __int128 v147; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v148; // [rsp+2B0h] [rbp+1B0h]
  CmsTableSetBase **v149; // [rsp+2B8h] [rbp+1B8h]
  __int64 v150; // [rsp+2C0h] [rbp+1C0h]
  char v151; // [rsp+2C8h] [rbp+1C8h]
  int v152; // [rsp+2CCh] [rbp+1CCh]

  v5 = *a3;
  v110 = a5;
  v111 = v5;
  LODWORD(v5) = *((_DWORD *)a3 + 2);
  P = &v140;
  v135 = HIDWORD(v119[0]);
  v97 = a4;
  v139 = 32;
  v133 = 0;
  v134 = 0;
  v136 = 0;
  v138 = 0;
  v143 = 0;
  v144 = 0;
  v145 = 0;
  v146 = 0;
  v109 = v5;
  v103 = 0;
  v104 = 0;
  v108 = 0;
  *(_OWORD *)v101 = 0;
  *(_OWORD *)v141 = 0;
  v142 = 0;
  if ( (a4 & 0xC) != 0 )
  {
    *a2 |= 0x4000000u;
    v9 = 1;
  }
  else
  {
    v9 = 0;
  }
  v89 = v9;
  if ( (*(_DWORD *)a2 & 0x200000) != 0 && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v10 = *a2;
  ++*((_WORD *)a2 + 106);
  v11 = *((unsigned __int8 *)a2 + 131);
  v108 = *((unsigned __int16 *)a2 + 106);
  v102[0] = a2[18];
  v12 = (_QWORD *)(a2[52] + 8);
  v104 = 0;
  v13 = (_QWORD *)*v12;
  v14 = *v12 == 0;
  v107 = v10;
  v105 = v11;
  if ( v14 )
    v13 = v12;
  HIBYTE(v103) = 0;
  v102[2] = a2[25];
  v102[1] = v13;
  v15 = v10 & 0xFFFFEFFFFFFFFFFFuLL;
  v16 = *((_BYTE *)a2 + 132);
  *a2 = v15;
  v106 = v16;
  while ( 1 )
  {
    if ( (unsigned __int8)v11 >= 0xDu )
      goto LABEL_10;
    if ( !a2[(unsigned __int8)v11 + 70] )
      break;
    LOBYTE(v11) = v11 + 1;
  }
  *((_BYTE *)a2 + 131) = v11;
LABEL_10:
  while ( v16 < 0xDu )
  {
    if ( !a2[v16 + 53] )
    {
      *((_BYTE *)a2 + 132) = v16;
      break;
    }
    ++v16;
  }
  if ( *((_BYTE *)a2 + 131) < *((_BYTE *)a2 + 130) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v17 = v15;
  *((_BYTE *)a2 + 130) = *((_BYTE *)a2 + 131);
  if ( (v15 & 0x300000000000LL) != 0 )
    goto LABEL_32;
  v18 = (_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL);
  if ( (_QWORD *)*v18 == v18 )
  {
    v19 = 0;
  }
  else
  {
    v11 = *(_QWORD *)(a1 + 24);
    v19 = *v18 - 32LL;
    do
    {
      if ( *(_QWORD *)(v19 + 16) == v11 )
        break;
      v20 = *(_QWORD **)(v19 + 32);
      v19 = 0;
      if ( v20 != v18 )
        v19 = (__int64)(v20 - 4);
    }
    while ( v19 );
  }
  if ( (*(_BYTE *)(v19 + 48) & 2) != 0 )
  {
    v63 = *(_QWORD **)(v19 + 32);
    v19 = 0;
    if ( v63 != v18 )
      v19 = (__int64)(v63 - 4);
  }
  if ( (v17 & 0x1000) != 0 )
  {
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    LOBYTE(v11) = 1;
    CmsVolume::ChangeVolumeOptionDynamically(a2[1], 0x20000000, v11);
    goto LABEL_96;
  }
  v21 = *(_QWORD *)v19;
  v22 = qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v22 < 0x60u )
  {
    v22 = 0;
    v23 = 112;
    goto LABEL_25;
  }
  if ( *(_BYTE *)(v22 + 8) )
  {
    v64 = (struct _NPAGED_LOOKASIDE_LIST *)(v22 + 64);
    if ( *(_BYTE *)(v22 + 9) )
      v65 = ExAllocateFromNPagedLookasideList(v64);
    else
      v65 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v64);
LABEL_59:
    v25 = v65;
    if ( v65 )
    {
LABEL_60:
      *(_QWORD *)v25 = v22;
      v25 += 4;
      goto LABEL_61;
    }
    goto LABEL_31;
  }
  if ( (int)*(_QWORD *)(v22 + 88) > (int)HIDWORD(*(_QWORD *)(v22 + 88)) )
  {
    v26 = _InterlockedDecrement((volatile signed __int32 *)(v22 + 88));
    if ( v26 >= *(_DWORD *)(v22 + 92) && v26 >= 0 )
    {
      v65 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v22 + 64));
      goto LABEL_59;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v22 + 88));
  }
LABEL_31:
  v23 = *(unsigned int *)(v22 + 4);
LABEL_25:
  Pool2 = ExAllocatePool2(66, v23, 1766871885);
  v25 = (_DWORD *)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( Pool2 )
    goto LABEL_60;
LABEL_61:
  if ( !v25 )
  {
    v9 = v89;
LABEL_96:
    v27 = -1073741670;
    goto LABEL_45;
  }
  v25[4] = 21;
  *((_QWORD *)v25 + 5) = v21;
  v25[3] = 8;
  v25[2] = 8;
  *((_WORD *)v25 + 10) = 0;
  *((_OWORD *)v25 + 3) = 0;
  *((_OWORD *)v25 + 4) = 0;
  *((_QWORD *)v25 + 10) = 0;
  v25[8] = 0;
  *((_QWORD *)v25 + 3) = v25 + 22;
  *((_QWORD *)v25 + 11) = 0;
  Src = a1;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  v38 = (_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL);
  if ( (_QWORD *)*v38 == v38 )
  {
    v39 = 0;
  }
  else
  {
    v39 = *v38 - 32LL;
    do
    {
      if ( *(_QWORD *)(v39 + 16) == *(_QWORD *)(a1 + 24) )
        break;
      v40 = *(_QWORD **)(v39 + 32);
      v39 = 0;
      if ( v40 != v38 )
        v39 = (__int64)(v40 - 4);
    }
    while ( v39 );
  }
  if ( (*(_BYTE *)(v39 + 48) & 2) != 0 )
  {
    v66 = *(_QWORD **)(v39 + 32);
    v39 = 0;
    if ( v66 != v38 )
      v39 = (__int64)(v66 - 4);
  }
  *((_QWORD *)v25 + 5) = *(_QWORD *)v39;
  v25[2] = 8;
  v25[8] = 0;
  *((_OWORD *)v25 + 3) = 0;
  *((_OWORD *)v25 + 4) = 0;
  *((_QWORD *)v25 + 10) = 0;
  v41 = v25[2];
  if ( v41 )
  {
    v42 = (__int64 *)*((_QWORD *)v25 + 3);
    if ( &Src != v42 )
      memmove(v42, &Src, v41);
  }
  a4 = v97;
  *(_QWORD *)v25 = a2[18];
  *a2 |= 0x100000000000uLL;
  v9 = v89;
  a2[18] = (unsigned __int64)v25;
LABEL_32:
  v27 = 0;
  if ( a2[21] && a2[22] != a1 )
  {
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    v27 = -1073741436;
    goto LABEL_45;
  }
  while ( 1 )
  {
    v28 = *((_DWORD *)a3 + 2);
    if ( !v28 )
      break;
    v29 = *a3;
    v99 = 0;
    v30 = v28;
    v100 = 0;
    v31 = a2[21];
    v90 = a4;
    v94 = v29;
    v95 = v28;
    v101[0] = (CmsTableSetBase *)v31;
    if ( !v31 || a2[22] != a1 )
    {
      v32 = (char *)v28;
      v96 = v94;
      v93 = 0;
      v95 = v28;
      goto LABEL_36;
    }
    v96 = v94;
    v148 = 0;
    v149 = 0;
    v150 = 0;
    v151 = 0;
    v152 = 0;
    v147 = 0;
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v147);
    v121[1] = v28;
    v127 = 0;
    v128 = 0;
    v121[2] = 0;
    v126 = 0;
    v121[0] = v96;
    memset(v129, 0, sizeof(v129));
    v98 = v28 + v96;
    SetRangeMapEntryRowHlpr((struct _CmsRow *)&v126, (struct SmsRangeMapEntry *)v121, 0);
    if ( CmsAvlTableLite::PinInIndexEx(
           (CmsAvlTableLite *)(v31 + 8),
           (struct CmsTransactionCore *)a2,
           (const struct SmsInternalPropertyDef *)&CmsRangeMap::PropertyDef,
           (struct _CmsRow *)&v126,
           (struct _CmsRow *)&v147,
           (struct _SmsQuickIndex *)v129) )
    {
      v101[0] = (CmsTableSetBase *)-1LL;
      if ( (unsigned int)CmsAvlTableLite::PinNextInIndex(v55, 1, &v147, 0, v129) )
        v56 = v101[0];
      else
        v56 = *v149;
      v32 = (char *)v28;
      if ( (unsigned __int64)v56 < v98 )
      {
        v32 = (char *)v56 - v96;
        v30 = (_DWORD)v56 - v96;
      }
      v43 = 0;
      v98 = v96;
    }
    else
    {
      v32 = (char *)v28;
      v57 = (unsigned __int64)v149[2];
      v58 = (char *)v149[1] + (_QWORD)*v149;
      v59 = v96;
      if ( !*((_BYTE *)v101[0] + 56) )
        v57 = v96 + v57 - (_QWORD)*v149;
      v98 = v57;
      v96 = v57;
      if ( v28 + v59 > (unsigned __int64)v58 )
      {
        v32 = &v58[-v59];
        v30 = (_DWORD)v58 - v59;
      }
      v43 = 1;
    }
    v93 = v43;
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v147);
    v95 = (unsigned int)v32;
    if ( v93 )
    {
      v92 = 0;
      v96 = v98 & 0x3FFFFFFFFFFFFFFLL;
      if ( (v98 & 0x2000000000000000LL) != 0 )
      {
        v44 = v97 | 0x40;
        v90 = v97 | 0x40;
      }
      else
      {
        v44 = v90;
      }
      if ( (v98 & 0x4000000000000000LL) != 0 )
        v90 = v44 | 0x1000000;
      v74 = v93;
      if ( (v98 & 0x8000000000000000uLL) != 0LL )
        v74 = 0;
      v93 = v74;
LABEL_78:
      if ( v110
        && v30 > CmsStream::IdealClustersPerRun(
                   (CmsStream *)a1,
                   (struct CmsTransactionContext *)a2,
                   *((unsigned __int8 *)v110 + 2)) )
      {
        v95 = CmsStream::IdealClustersPerRun((CmsStream *)a1, v67, v68);
      }
      v45 = *(CmsTableSetBase **)(a1 + 16);
      v27 = 0;
      v46 = *(_QWORD *)(a1 + 24);
      v47 = 0;
      v101[0] = v45;
      v98 = v46;
      v112 = 0;
      v113 = 0;
      if ( v141[0]
        || (LOWORD(v117[1]) = 0,
            v117[0] = 12,
            v118 = &v94,
            v48 = TmsTableSet<CmsStreamSetCallbacks>::PinRow(
                    (int)v45,
                    (int)a2,
                    v46,
                    (int)v117,
                    1025,
                    (CmsRowWithBuffer *)&v133,
                    0),
            v50 = v90,
            v27 = v48,
            v48 >= 0) )
      {
        v70 = *(_QWORD *)(SmsTableSetLookupStack::ToKey(&v133, v130) + 8);
        v71 = *(_QWORD *)v70;
        v113 = *(_DWORD *)(v70 + 8);
        v47 = v71;
        v112 = v71;
        if ( v71 >= v94 + v69 )
          goto LABEL_82;
      }
      else
      {
        if ( v48 == -1073741197 )
          goto LABEL_82;
        v69 = v95;
      }
      if ( v27 == -1073741772 )
      {
        v75 = v94 + v69;
        if ( v75 >= v146 )
          v75 = v146;
        v146 = v75;
        goto LABEL_82;
      }
      if ( v27 < 0 )
        goto LABEL_91;
      if ( !(unsigned __int8)IsRangeWithinBoundaries<_SRANGE,_SRANGE>(&v94, &v112) )
      {
        v77 = v101[0];
        v101[0] = *(CmsTableSetBase **)(*(_QWORD *)(*((_QWORD *)v101[0] + 31) + 24LL) + 72LL);
        Entry = CmsTableSetBase::GetEntry(v77, v98, v76);
        CmsTableSetBase::GetMergeTargetEntry(v79, Entry);
        v81 = v47;
        if ( v94 > v47 )
          v81 = v94;
        v82 = v94 + v80;
        v115 = v81;
        LOBYTE(v88) = 0;
        LODWORD(v98) = *((_DWORD *)v141[0] + 97);
        if ( v82 >= v47 + v113 )
          LODWORD(v82) = v47 + v113;
        v123 = 0;
        v124 = 0;
        LODWORD(v116) = v82 - v81;
        v125 = 0;
        LOBYTE(v87) = 0;
        CmsVolume::BeginTopLevelActionInternal(v94, a2, v122, 0, v87, (_DWORD)v88);
        v27 = TmsTableSet<CmsStreamSetCallbacks>::SliceRangeRow(
                v83,
                (_DWORD)a2,
                v84,
                (unsigned int)v141,
                (__int64)&v115,
                (__int64)v141);
        if ( v27 < 0 )
        {
          CmsVolume::AbortTopLevelAction(v101[0], (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v122);
          v50 = v90;
LABEL_91:
          if ( v27 != -1073741772 )
            goto LABEL_44;
LABEL_82:
          v51 = v146 - v94;
          v99 = v96;
          v91 = v50;
          if ( (unsigned __int64)v32 < v146 - v94 )
            v51 = (unsigned int)v32;
          v95 = v51;
          v100 = v51;
          v52 = CmsStream::PersistFastRunInsertion(
                  (CmsStream *)a1,
                  (struct CmsTransactionContext *)a2,
                  v49,
                  (const struct _SRANGE *)&v94,
                  (const struct _SRANGE *)&v99,
                  v50,
                  v110,
                  v94 - v111);
          v53 = v91;
          goto LABEL_85;
        }
        if ( (_DWORD)v98 )
          CmsVolume::FoldTopLevelAction(v101[0], (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v122);
        else
          CmsVolume::CommitTopLevelAction(
            v101[0],
            (struct CmsTransactionContext *)a2,
            (struct _SmsTopLevelAction *)v122,
            0);
        v85 = _SmsIndexEntry::ToKey(v142, v131);
        v146 = **(_QWORD **)(v85 + 8) + *(unsigned int *)(*(_QWORD *)(v85 + 8) + 8LL);
      }
      v53 = v90;
      v86 = *(_QWORD *)(SmsTableSetLookupStack::ToRow(&v133, v132) + 24);
      if ( v92 && _bittest16((const signed __int16 *)(v86 + 8), 0xBu) )
        v53 = v90 | 0x1000000;
      v60 = *(unsigned int *)(v86 + 20);
      v61 = (struct _SRANGE *)&v99;
      if ( (unsigned __int64)v32 < v60 )
        LODWORD(v60) = (_DWORD)v32;
      v100 = v60;
      v95 = v60;
      if ( !v93 )
        v61 = 0;
      v99 = v96;
      v52 = CmsStream::PersistFastRunUpdate(
              (CmsStream *)a1,
              (struct CmsTransactionContext *)a2,
              (struct SmsTableSetLookupStack *)&v133,
              (struct SmsRun *)v86,
              v61,
              v53,
              v110,
              v94 - v111);
LABEL_85:
      v27 = v52;
      if ( v52 < 0 )
        goto LABEL_44;
      if ( (v53 & 0x2000000) != 0 )
      {
        v72 = a2[1];
        v120[0] = v99;
        v120[1] = v100;
        v27 = CmsBlockRefcount::IncrementRefcount(
                *(CmsBlockRefcount **)(v72 + 3368),
                (struct CmsTransactionContext *)a2,
                (const struct _RANGE *)v120,
                0,
                0,
                v88);
        if ( v27 < 0 )
          goto LABEL_44;
      }
      v54 = v95;
      *a3 += v95;
      v14 = v141[0] == 0;
      *((_DWORD *)a3 + 2) = v28 - v54;
      if ( !v14 )
        CmsVolume::Unpin((CmsVolume *)a2[1], (struct CmsTransactionCore *)a2, v141, 3u);
      a4 = v97;
      v144 = 0;
      v145 = 0;
      v146 = 0;
    }
    else
    {
      a4 = v97;
LABEL_36:
      if ( (a4 & 0x1000040) != 0 )
      {
        v92 = 1;
        goto LABEL_78;
      }
      *a3 += v30;
      *((_DWORD *)a3 + 2) = v28 - v30;
    }
  }
  v119[0] = v111;
  v119[1] = v109;
  CmsStream::RemoveRangeFromCache(a1, a2, v119);
  --*((_WORD *)a2 + 106);
  v108 = 0;
  if ( v104 )
    --*((_WORD *)a2 + 107);
  if ( HIBYTE(v103) )
  {
    v62 = (CmsTxMemLog *)a2[52];
    if ( *(_QWORD *)v62 )
      CmsTxMemLog::MergeTxLog(v116, (struct CmsTxMemLog *)&v109, (struct CmsDurableLog *)(a2[1] + 2880));
    else
      CmsTxMemLog::DiscardPendingRecords(v62, (struct CmsDurableLog *)(a2[1] + 2880));
    v33 = v107;
    if ( (v107 & 0x80000000000LL) != 0 )
    {
      v73 = *(_QWORD *)v117;
      *a2 |= 0x80000000000uLL;
      a2[14] = v73;
    }
    a2[52] = (unsigned __int64)v116;
  }
  else
  {
    v33 = v107;
  }
  v34 = *((_BYTE *)a2 + 130);
  *a2 |= v33 & 0x100000000000LL;
  if ( *((_BYTE *)a2 + 131) != v34 && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v35 = v105;
  v36 = v106;
  *((_BYTE *)a2 + 131) = v105;
  *((_BYTE *)a2 + 132) = v36;
  *((_BYTE *)a2 + 130) = v35;
LABEL_44:
  v9 = v89;
LABEL_45:
  if ( v141[0] )
    CmsVolume::Unpin((CmsVolume *)a2[1], (struct CmsTransactionCore *)a2, v141, 3u);
  v144 = 0;
  v145 = 0;
  v146 = 0;
  if ( v27 < 0 )
    CmsVolume::AbortTopLevelAction(
      (CmsVolume *)a2[1],
      (struct CmsTransactionContext *)a2,
      (struct _SmsTopLevelAction *)v102);
  if ( v9 )
    *a2 &= ~0x4000000uLL;
  if ( v141[0] && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  if ( (v138 & 1) != 0 && P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x14002a3d0  push    rbp
0x14002a3d2  push    rdi
0x14002a3d3  push    r12
0x14002a3d5  push    r13
0x14002a3d7  push    r14
0x14002a3d9  push    r15
0x14002a3db  lea     rbp, [rsp-208h]
0x14002a3e3  sub     rsp, 308h
0x14002a3ea  mov     rax, cs:__security_cookie
0x14002a3f1  xor     rax, rsp
0x14002a3f4  mov     [rbp+230h+var_40], rax
0x14002a3fb  mov     rax, [rbp+230h+arg_20]
0x14002a402  xor     r13d, r13d
0x14002a405  mov     r11, [r8]
0x14002a408  xorps   xmm0, xmm0
0x14002a40b  mov     [rbp+230h+var_260], rax
0x14002a40f  mov     r15, r8
0x14002a412  lea     rax, [rbp+230h+var_F0]
0x14002a419  mov     [rbp+230h+var_258], r11
0x14002a41d  mov     r11d, [r8+8]
0x14002a421  mov     rdi, rdx
0x14002a424  mov     [rbp+230h+P], rax
0x14002a42b  mov     r14, rcx
0x14002a42e  mov     eax, dword ptr [rbp+230h+var_210+4]
0x14002a431  mov     [rbp+230h+var_10C], eax
0x14002a437  xor     eax, eax
0x14002a439  mov     [rsp+330h+var_2C8], r9d
0x14002a43e  mov     [rbp+230h+var_F4], 20h ; ' '
0x14002a448  movaps  [rbp+230h+var_120], xmm0
0x14002a44f  mov     [rbp+230h+var_110], r13d
0x14002a456  mov     [rbp+230h+var_108], r13
0x14002a45d  mov     [rbp+230h+var_F8], r13b
0x14002a464  mov     [rbp+230h+var_B0], rax
0x14002a46b  mov     [rbp+230h+var_A8], r13
0x14002a472  mov     [rbp+230h+var_A0], r13d
0x14002a479  mov     [rbp+230h+var_98], r13
0x14002a480  mov     [rbp+230h+var_268], r11d
0x14002a484  mov     [rbp+230h+var_280], ax
0x14002a488  mov     [rbp+230h+var_27E], al
0x14002a48b  mov     [rbp+230h+var_270], r13d
0x14002a48f  movups  xmmword ptr [rbp+230h+var_2A8], xmm0
0x14002a493  movups  xmmword ptr [rbp+230h+var_D0], xmm0
0x14002a49a  movups  [rbp+230h+var_C0], xmm0
0x14002a4a1  test    r9b, 0Ch
0x14002a4a5  jz      loc_14002AE56
0x14002a4ab  or      qword ptr [rdx], 4000000h
0x14002a4b2  mov     r12b, 1
0x14002a4b5  mov     eax, [rdx]
0x14002a4b7  mov     [rsp+330h+var_2F0], r12b
0x14002a4bc  bt      rax, 15h
0x14002a4c1  jb      loc_14002ADE4
0x14002a4c7  mov     rdx, [rdx]
0x14002a4ca  inc     word ptr [rdi+0D4h]
0x14002a4d1  movzx   eax, word ptr [rdi+0D4h]
0x14002a4d8  movzx   r8d, byte ptr [rdi+83h]
0x14002a4e0  mov     [rbp+230h+var_270], eax
0x14002a4e3  mov     rax, [rdi+90h]
0x14002a4ea  mov     [rbp+230h+var_298], rax
0x14002a4ee  mov     rax, [rdi+1A0h]
0x14002a4f5  add     rax, 8
0x14002a4f9  mov     [rbp+230h+var_27E], r13b
0x14002a4fd  mov     rcx, [rax]
0x14002a500  test    rcx, rcx
0x14002a503  mov     [rbp+230h+var_278], rdx
0x14002a507  mov     [rbp+230h+var_27D], r8b
0x14002a50b  cmovz   rcx, rax
0x14002a50f  mov     byte ptr [rbp+230h+var_280+1], r13b
0x14002a513  mov     rax, [rdi+0C8h]
0x14002a51a  mov     [rbp+230h+var_288], rax
0x14002a51e  mov     rax, 0FFFFEFFFFFFFFFFFh
0x14002a528  mov     [rbp+230h+var_290], rcx
0x14002a52c  and     rdx, rax
0x14002a52f  movzx   ecx, byte ptr [rdi+84h]
0x14002a536  mov     [rdi], rdx
0x14002a539  mov     [rbp+230h+var_27C], cl
0x14002a53c  cmp     r8b, 0Dh
0x14002a540  jnb     short loc_14002A55B
0x14002a542  movzx   eax, r8b
0x14002a546  cmp     [rdi+rax*8+230h], r13
0x14002a54e  jnz     loc_14002A87F
0x14002a554  mov     [rdi+83h], r8b
0x14002a55b  cmp     cl, 0Dh
0x14002a55e  jnb     short loc_14002A577
0x14002a560  movzx   eax, cl
0x14002a563  cmp     [rdi+rax*8+1A8h], r13
0x14002a56b  jnz     loc_14002A878
0x14002a571  mov     [rdi+84h], cl
0x14002a577  movzx   eax, byte ptr [rdi+82h]
0x14002a57e  cmp     [rdi+83h], al
0x14002a584  jb      loc_14002ADFA
0x14002a58a  movzx   eax, byte ptr [rdi+83h]
0x14002a591  mov     r10, rdx
0x14002a594  mov     [rdi+82h], al
0x14002a59a  mov     rax, 300000000000h
0x14002a5a4  mov     [rsp+330h+arg_18], rbx
0x14002a5ac  mov     [rsp+330h+var_30], rsi
0x14002a5b4  test    rax, rdx
0x14002a5b7  jnz     loc_14002A6AC
0x14002a5bd  mov     r9, [r14+10h]
0x14002a5c1  add     r9, 10h
0x14002a5c5  mov     rdx, [r9]
0x14002a5c8  cmp     rdx, r9
0x14002a5cb  jz      loc_14002A887
0x14002a5d1  mov     r8, [r14+18h]
0x14002a5d5  add     rdx, 0FFFFFFFFFFFFFFE0h
0x14002a5d9  cmp     [rdx+10h], r8
0x14002a5dd  jz      short loc_14002A5F6
0x14002a5df  mov     rcx, [rdx+20h]
0x14002a5e3  mov     rdx, r13
0x14002a5e6  cmp     rcx, r9
0x14002a5e9  lea     rax, [rcx-20h]
0x14002a5ed  cmovnz  rdx, rax
0x14002a5f1  test    rdx, rdx
0x14002a5f4  jnz     short loc_14002A5D9
0x14002a5f6  test    byte ptr [rdx+30h], 2
0x14002a5fa  jnz     loc_14002AE5E
0x14002a600  bt      r10, 0Ch
0x14002a605  jb      loc_14002AB86
0x14002a60b  mov     r12, [rdx]
0x14002a60e  xor     ecx, ecx; ProcNumber
0x14002a610  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14002a617  nop     dword ptr [rax+rax+00h]
0x14002a61c  xor     edx, edx
0x14002a61e  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14002a624  lea     rsi, [rdx+rdx*2]
0x14002a628  shl     rsi, 6
0x14002a62c  add     rsi, cs:qword_140262410
0x14002a633  cmp     dword ptr [rsi], 60h ; '`'
0x14002a636  jnb     short loc_14002A66F
0x14002a638  mov     rsi, r13
0x14002a63b  mov     edx, 70h ; 'p'
0x14002a640  mov     ecx, 42h ; 'B'
0x14002a645  mov     r8d, 6950534Dh
0x14002a64b  call    cs:__imp_ExAllocatePool2
0x14002a652  nop     dword ptr [rax+rax+00h]
0x14002a657  mov     rbx, rax
0x14002a65a  test    al, 0Fh
0x14002a65c  jz      loc_1401F1206
0x14002a662  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14002a669  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14002a66f  cmp     [rsi+8], r13b
0x14002a673  jnz     loc_14002AE7B
0x14002a679  mov     rcx, [rsi+58h]
0x14002a67d  mov     rax, rcx
0x14002a680  shr     rax, 20h
0x14002a684  cmp     ecx, eax
0x14002a686  jle     short loc_14002A6A7
0x14002a688  nop
0x14002a689  mov     ecx, 0FFFFFFFFh
0x14002a68e  lock xadd [rsi+58h], ecx
0x14002a693  nop
0x14002a694  dec     ecx
0x14002a696  mov     eax, [rsi+5Ch]
0x14002a699  cmp     ecx, eax
0x14002a69b  jge     loc_14002AE9A
0x14002a6a1  nop
0x14002a6a2  lock inc dword ptr [rsi+58h]
0x14002a6a6  nop
0x14002a6a7  mov     edx, [rsi+4]
0x14002a6aa  jmp     short loc_14002A640
0x14002a6ac  mov     ebx, r13d
0x14002a6af  cmp     [rdi+0A8h], r13
0x14002a6b6  jnz     loc_14002AED9
0x14002a6bc  nop     dword ptr [rax+00h]
0x14002a6c0  mov     esi, [r15+8]
0x14002a6c4  test    esi, esi
0x14002a6c6  jz      short loc_14002A73A
0x14002a6c8  movsd   xmm0, qword ptr [r15]
0x14002a6cd  mov     r10d, r9d
0x14002a6d0  mov     eax, esi
0x14002a6d2  mov     [rsp+330h+var_2B8], r13
0x14002a6d7  mov     r12d, eax
0x14002a6da  mov     [rbp+230h+var_2B0], r13d
0x14002a6de  mov     r13, [rdi+0A8h]
0x14002a6e5  mov     dword ptr [rsp+330h+var_2EC], r9d
0x14002a6ea  movsd   [rsp+330h+var_2E0], xmm0
0x14002a6f0  mov     [rsp+330h+var_2D8], eax
0x14002a6f4  mov     [rbp+230h+var_2A8], r13
0x14002a6f8  test    r13, r13
0x14002a6fb  jnz     loc_14002AEF1
0x14002a701  mov     rdx, [rsp+330h+var_2E0]
0x14002a706  mov     r13, r12
0x14002a709  mov     [rsp+330h+var_2D0], rdx
0x14002a70e  mov     r11d, r12d
0x14002a711  mov     byte ptr [rsp+330h+var_2E4], 0
0x14002a716  mov     [rsp+330h+var_2D8], r12d
0x14002a71b  test    r9d, 1000040h
0x14002a722  jnz     loc_1401F123E
0x14002a728  sub     esi, r12d
0x14002a72b  mov     eax, r12d
0x14002a72e  add     [r15], rax
0x14002a731  xor     r13d, r13d
0x14002a734  mov     [r15+8], esi
0x14002a738  jmp     short loc_14002A6C0
0x14002a73a  mov     rax, [rbp+230h+var_258]
0x14002a73e  lea     r8, [rbp+230h+var_210]
0x14002a742  mov     [rbp+230h+var_210], rax
0x14002a746  mov     rdx, rdi
0x14002a749  mov     eax, [rbp+230h+var_268]
0x14002a74c  mov     rcx, r14
0x14002a74f  mov     [rbp+230h+var_208], rax
0x14002a753  call    ?RemoveRangeFromCache@CmsStream@@AEAAXPEAVCmsTransactionContext@@U_RANGE@@@Z; CmsStream::RemoveRangeFromCache(CmsTransactionContext *,_RANGE)
0x14002a758  dec     word ptr [rdi+0D4h]
0x14002a75f  cmp     [rbp+230h+var_27E], 0
0x14002a763  mov     [rbp+230h+var_270], r13d
0x14002a767  jnz     loc_14002AFED
0x14002a76d  cmp     byte ptr [rbp+230h+var_280+1], 0
0x14002a771  jnz     loc_14002AD9C
0x14002a777  mov     rcx, [rbp+230h+var_278]
0x14002a77b  mov     rax, 100000000000h
0x14002a785  and     rcx, rax
0x14002a788  movzx   eax, byte ptr [rdi+82h]
0x14002a78f  or      [rdi], rcx
0x14002a792  cmp     [rdi+83h], al
0x14002a798  jnz     loc_14002AE2A
0x14002a79e  movzx   ecx, [rbp+230h+var_27D]
0x14002a7a2  movzx   eax, [rbp+230h+var_27C]
0x14002a7a6  mov     [rdi+83h], cl
0x14002a7ac  mov     [rdi+84h], al
0x14002a7b2  mov     [rdi+82h], cl
0x14002a7b8  movzx   r12d, [rsp+330h+var_2F0]
0x14002a7be  cmp     [rbp+230h+var_D0], 0
0x14002a7c6  jnz     loc_14002A85A
0x14002a7cc  mov     [rbp+230h+var_A8], r13
0x14002a7d3  mov     [rbp+230h+var_A0], r13d
0x14002a7da  mov     [rbp+230h+var_98], r13
0x14002a7e1  test    ebx, ebx
0x14002a7e3  js      loc_14002B023
0x14002a7e9  test    r12b, r12b
0x14002a7ec  jz      short loc_14002A7F5
0x14002a7ee  and     qword ptr [rdi], 0FFFFFFFFFBFFFFFFh
0x14002a7f5  cmp     [rbp+230h+var_D0], 0
0x14002a7fd  jnz     loc_14002AE40
0x14002a803  test    [rbp+230h+var_F8], 1
0x14002a80a  jz      short loc_14002A826
0x14002a80c  mov     rcx, [rbp+230h+P]; P
0x14002a813  test    rcx, rcx
0x14002a816  jz      short loc_14002A826
0x14002a818  xor     edx, edx; Tag
0x14002a81a  call    cs:__imp_ExFreePoolWithTag
0x14002a821  nop     dword ptr [rax+rax+00h]
0x14002a826  mov     rsi, [rsp+330h+var_30]
0x14002a82e  mov     eax, ebx
0x14002a830  mov     rbx, [rsp+330h+arg_18]
0x14002a838  mov     rcx, [rbp+230h+var_40]
0x14002a83f  xor     rcx, rsp; StackCookie
0x14002a842  call    __security_check_cookie
0x14002a847  add     rsp, 308h
0x14002a84e  pop     r15
0x14002a850  pop     r14
0x14002a852  pop     r13
0x14002a854  pop     r12
0x14002a856  pop     rdi
0x14002a857  pop     rbp
0x14002a858  retn
0x14002a85a  mov     rcx, [rdi+8]; this
0x14002a85e  lea     r8, [rbp+230h+var_D0]; struct SmsPage **
0x14002a865  mov     r9d, 3; unsigned int
0x14002a86b  mov     rdx, rdi; struct CmsTransactionCore *
0x14002a86e  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
0x14002a873  jmp     loc_14002A7CC
0x14002a878  inc     cl
0x14002a87a  jmp     loc_14002A55B
0x14002a87f  inc     r8b
0x14002a882  jmp     loc_14002A53C
0x14002a887  mov     rdx, r13
0x14002a88a  jmp     loc_14002A5F6
0x14002a88f  mov     rbx, rax
0x14002a892  test    rax, rax
0x14002a895  jz      loc_14002A6A7
0x14002a89b  mov     [rbx], rsi
0x14002a89e  add     rbx, 10h
0x14002a8a2  test    rbx, rbx
0x14002a8a5  jz      loc_14002AEB7
0x14002a8ab  mov     dword ptr [rbx+10h], 15h
0x14002a8b2  xor     eax, eax
0x14002a8b4  mov     [rbx+28h], r12
0x14002a8b8  xorps   xmm0, xmm0
0x14002a8bb  mov     dword ptr [rbx+0Ch], 8
0x14002a8c2  xor     ecx, ecx
0x14002a8c4  mov     dword ptr [rbx+8], 8
0x14002a8cb  mov     [rbx+14h], r13w
0x14002a8d0  movups  xmmword ptr [rbx+30h], xmm0
0x14002a8d4  movups  xmmword ptr [rbx+40h], xmm0
0x14002a8d8  mov     [rbx+50h], rax
0x14002a8dc  lea     rax, [rbx+58h]
0x14002a8e0  mov     [rbx+20h], r13d
0x14002a8e4  mov     [rbx+18h], rax
0x14002a8e8  mov     [rax], rcx
0x14002a8eb  mov     [rbp+230h+Src], r14
0x14002a8ef  lock inc dword ptr [r14+8]
0x14002a8f4  mov     r9, [r14+10h]
0x14002a8f8  add     r9, 10h
0x14002a8fc  mov     rdx, [r9]
0x14002a8ff  cmp     rdx, r9
0x14002a902  jz      loc_14002A9A8
0x14002a908  mov     r8, [r14+18h]
0x14002a90c  add     rdx, 0FFFFFFFFFFFFFFE0h
0x14002a910  cmp     [rdx+10h], r8
0x14002a914  jz      short loc_14002A92D
  ... truncated ...
```
