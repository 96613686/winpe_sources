# UxpSslCommonSendDataHelper

- ea: `0x14004c5d0`
- end: `0x14004d12a`
- name: `UxpSslCommonSendDataHelper`
- size: `2906`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004ebe0`

## callees

- `0x14000a350`
- `0x140049d08`
- `0x14004ba70`
- `0x14004bd90`
- `0x14004c5d0`
- `0x14004d130`
- `0x1400513f0`
- `0x14013b124`
- `0x140155b78`
- `0x1401678f0`
- `0x140167940`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d58d4`
- `0x1401d5988`
- `0x1401d5a48`
- `0x1401d5b20`
- `0x1401d9e44`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14004cbaa`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14004cbaa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004c968`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004c968`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c78c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004ca88`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004cd2e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c78c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004ca88`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004cd2e`
- `ntoskrnl!MmSizeOfMdl` at `0x14004c705`
- `ntoskrnl!MmSizeOfMdl` at `0x14004c705`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004ced3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf04`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf35`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf66`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004ced3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf04`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf35`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf66`
- `ntoskrnl!ExAllocatePool3` at `0x1401765f3`
- `ntoskrnl!ExAllocatePool3` at `0x1401765f3`

## pseudocode

```c
__int64 __fastcall UxpSslCommonSendDataHelper(
        unsigned __int64 a1,
        int a2,
        __int64 a3,
        struct _MDL *a4,
        int a5,
        unsigned __int64 a6,
        __int64 (__fastcall *a7)(PVOID P),
        __int64 a8,
        __int64 a9)
{
  char *v9; // r13
  unsigned __int64 v10; // r14
  _QWORD *v11; // r15
  _QWORD *v12; // rdi
  unsigned __int64 v13; // rsi
  unsigned int v14; // r9d
  SIZE_T v15; // r12
  int v16; // eax
  unsigned int v17; // eax
  int v18; // ebx
  unsigned __int64 v19; // rbx
  _QWORD *v20; // rax
  int v21; // eax
  __int64 v22; // r12
  int v23; // ebx
  unsigned int v24; // r9d
  unsigned int i; // r10d
  __int64 v26; // r12
  int v27; // r8d
  unsigned int v28; // r15d
  __int64 v29; // rcx
  PMDL v30; // r10
  char *v31; // r9
  int v32; // r8d
  char *MappedSystemVa; // rax
  unsigned int v34; // r12d
  int v35; // eax
  int v36; // ebx
  unsigned __int64 v37; // rbx
  _QWORD *v38; // rax
  unsigned int v39; // ebx
  __int64 v40; // r14
  _QWORD *v41; // rdi
  __int64 v42; // rsi
  int v43; // r12d
  _QWORD *v44; // rbx
  __int64 v45; // r8
  _QWORD *v46; // r14
  __int64 v47; // r9
  char v48; // bl
  __int64 v49; // rax
  __int64 v50; // rcx
  int LockArray_high; // ebx
  unsigned __int64 v53; // rbx
  _QWORD *v54; // rax
  unsigned int v55; // ebx
  __int64 v56; // rax
  __int64 v57; // rbx
  USHORT v58; // ax
  __int64 v59; // rbx
  USHORT CurrentNodeNumber; // ax
  __int64 v61; // rbx
  USHORT v62; // ax
  __int64 v63; // rbx
  USHORT v64; // ax
  __int64 Pool3; // rax
  __int64 v66; // [rsp+38h] [rbp-A9h]
  __int64 v67; // [rsp+48h] [rbp-99h]
  int v68; // [rsp+60h] [rbp-81h]
  int j; // [rsp+60h] [rbp-81h]
  int v70; // [rsp+60h] [rbp-81h]
  int v71; // [rsp+60h] [rbp-81h]
  unsigned int v72; // [rsp+64h] [rbp-7Dh]
  unsigned int v73; // [rsp+64h] [rbp-7Dh]
  unsigned int v74; // [rsp+68h] [rbp-79h]
  unsigned int v75; // [rsp+6Ch] [rbp-75h] BYREF
  unsigned int v76; // [rsp+70h] [rbp-71h]
  _QWORD *v77; // [rsp+78h] [rbp-69h] BYREF
  __int64 v78; // [rsp+80h] [rbp-61h]
  unsigned int Size; // [rsp+88h] [rbp-59h]
  unsigned int Size_4; // [rsp+8Ch] [rbp-55h]
  char *v81; // [rsp+90h] [rbp-51h]
  PMDL Next; // [rsp+98h] [rbp-49h]
  __int64 v83; // [rsp+A0h] [rbp-41h]
  PVOID P; // [rsp+A8h] [rbp-39h]
  _QWORD *v85; // [rsp+B0h] [rbp-31h] BYREF
  _QWORD *v86; // [rsp+B8h] [rbp-29h]
  __int128 v87; // [rsp+C0h] [rbp-21h] BYREF
  __int128 v88; // [rsp+D0h] [rbp-11h]
  unsigned __int8 v89; // [rsp+128h] [rbp+47h]
  unsigned int v90; // [rsp+130h] [rbp+4Fh]
  PMDL MemoryDescriptorList; // [rsp+138h] [rbp+57h] BYREF

  MemoryDescriptorList = a4;
  v90 = a3;
  v89 = a2;
  v9 = (char *)a1;
  v85 = 0;
  v77 = 0;
  v10 = a6;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
  {
    WPP_SF_qlLqLPqqq((unsigned __int8)a2, 29, a3, a1, (unsigned __int8)a2, a3, a4, a5, a6, a7, a8, a9);
    LOWORD(a2) = v89;
    LODWORD(a3) = v90;
  }
  P = 0;
  v86 = 0;
  v11 = 0;
  v12 = 0;
  v13 = (v10 >> 15) + ((v10 & 0x7FFF) != 0);
  if ( v13 )
  {
    while ( 1 )
    {
      v75 = 0;
      v14 = v10;
      if ( v10 > 0x8000 )
        v14 = 0x8000;
      LODWORD(a6) = v14;
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      {
        LODWORD(v66) = 0;
        WPP_SF_qqqLlq(a1, (_WORD)a2, a3, (_DWORD)v9, (char)&MemoryDescriptorList, (char)&a5, v14, v66, &v77);
        v14 = a6;
      }
      a3 = *((unsigned int *)v9 + 114);
      v12 = 0;
      v77 = 0;
      if ( (unsigned int)a3 >= 0x10000 || (a1 = *((unsigned int *)v9 + 115), (unsigned int)a1 >= 0x10000) )
      {
        v23 = -1073741811;
        v26 = v14;
      }
      else
      {
        Size = *((_DWORD *)v9 + 116);
        LOWORD(a2) = v14;
        v78 = v14;
        a1 += a3;
        v74 = v14 / Size + (v14 % Size != 0);
        v15 = v14 + (_DWORD)a1 * v74;
        if ( v15 == v14 + a1 * v74 )
        {
          if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
            WPP_SF_d(1041, 14, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, (unsigned int)v15);
          v16 = MmSizeOfMdl((PVOID)0xFFF, v15);
          LODWORD(a1) = v15 + 80;
          if ( (unsigned int)v15 < 0xFFFFFFB0 )
          {
            LODWORD(a1) = (v16 + 7) & 0xFFFFFFF8;
            v72 = a1;
            v17 = v15 + a1 + 80;
            if ( v17 >= (unsigned int)a1 )
            {
              if ( (unsigned int)v15 > 0x905 )
              {
                if ( (unsigned int)v15 <= 0x2105 )
                {
                  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
                  v71 = LockArray_high;
                  if ( UxDebugDisableLookaside )
                  {
                    v54 = (_QWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0660)(
                                      (unsigned int)dword_1401A0648,
                                      qword_1401A0650,
                                      (unsigned int)dword_1401A0658,
                                      0);
                  }
                  else
                  {
                    if ( UxCompactMode )
                    {
                      v59 = qword_1401A0640;
                      CurrentNodeNumber = KeGetCurrentNodeNumber();
                      v54 = (_QWORD *)PplAllocateFromLookasideListProcessor(v59, CurrentNodeNumber);
                    }
                    else
                    {
                      v53 = qword_1401A0640 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
                      if ( !*(_BYTE *)(v53 + 176) )
                        PplpLazyInitializeLookasideList(qword_1401A0640, v53 + 64);
                      v54 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v53 + 64));
                    }
                    LockArray_high = v71;
                  }
                  v12 = v54;
                  if ( !v54 )
                    goto LABEL_25;
                  *(_QWORD *)((char *)v54 + 4) = 0;
                  *((_DWORD *)v54 + 3) = 0;
                  v54[3] = 0;
                  v54[4] = 0;
                  v54[5] = 0;
                  v54[6] = 0;
                  *((_DWORD *)v54 + 14) = 0;
                  v54[9] = 0;
                  v21 = 1;
                  *(_DWORD *)v12 = LockArray_high;
                }
                else if ( (unsigned int)v15 > 0x4105 )
                {
                  if ( UxSslLargeBufferEnabled && (unsigned int)v15 <= 0x820A )
                  {
                    v55 = HIDWORD(KeGetPcr()[1].LockArray);
                    v76 = v55;
                    if ( UxDebugDisableLookaside )
                    {
                      v56 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A06C0)(
                              (unsigned int)dword_1401A06A8,
                              qword_1401A06B0,
                              (unsigned int)dword_1401A06B8,
                              0);
                    }
                    else if ( UxCompactMode )
                    {
                      v63 = qword_1401A06A0;
                      v64 = KeGetCurrentNodeNumber();
                      v56 = PplAllocateFromLookasideListProcessor(v63, v64);
                      v55 = v76;
                    }
                    else
                    {
                      v56 = PplAllocateFromLookasideListProcessor(qword_1401A06A0, v55);
                    }
                    v12 = (_QWORD *)v56;
                    if ( !v56 )
                      goto LABEL_25;
                    *(_QWORD *)(v56 + 4) = 0;
                    *(_DWORD *)(v56 + 12) = 0;
                    *(_QWORD *)(v56 + 24) = 0;
                    *(_QWORD *)(v56 + 32) = 0;
                    *(_QWORD *)(v56 + 40) = 0;
                    *(_QWORD *)(v56 + 48) = 0;
                    *(_DWORD *)(v56 + 56) = 0;
                    *(_QWORD *)(v56 + 72) = 0;
                    v21 = 3;
                    *(_DWORD *)v12 = v55;
                  }
                  else
                  {
                    Pool3 = ExAllocatePool3(66, v17, 1397979221, UxLowPriorityPool, 1);
                    v12 = (_QWORD *)Pool3;
                    if ( !Pool3 )
                      goto LABEL_25;
                    *(_QWORD *)Pool3 = 0;
                    *(_QWORD *)(Pool3 + 8) = 0;
                    *(_QWORD *)(Pool3 + 24) = 0;
                    *(_QWORD *)(Pool3 + 32) = 0;
                    *(_QWORD *)(Pool3 + 40) = 0;
                    *(_QWORD *)(Pool3 + 48) = 0;
                    *(_DWORD *)(Pool3 + 56) = 0;
                    *(_QWORD *)(Pool3 + 72) = 0;
                    v21 = 4;
                  }
                }
                else
                {
                  v36 = HIDWORD(KeGetPcr()[1].LockArray);
                  v70 = v36;
                  if ( UxDebugDisableLookaside )
                  {
                    v38 = (_QWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0690)(
                                      (unsigned int)dword_1401A0678,
                                      qword_1401A0680,
                                      (unsigned int)dword_1401A0688,
                                      0);
                  }
                  else
                  {
                    if ( UxCompactMode )
                    {
                      v61 = qword_1401A0670;
                      v62 = KeGetCurrentNodeNumber();
                      v38 = (_QWORD *)PplAllocateFromLookasideListProcessor(v61, v62);
                    }
                    else
                    {
                      v37 = qword_1401A0670 + ((unsigned __int64)(unsigned int)(v36 + 1) << 7);
                      if ( !*(_BYTE *)(v37 + 176) )
                        PplpLazyInitializeLookasideList(qword_1401A0670, v37 + 64);
                      v38 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v37 + 64));
                    }
                    v36 = v70;
                  }
                  v12 = v38;
                  if ( !v38 )
                    goto LABEL_25;
                  *(_QWORD *)((char *)v38 + 4) = 0;
                  *((_DWORD *)v38 + 3) = 0;
                  v38[3] = 0;
                  v38[4] = 0;
                  v38[5] = 0;
                  v38[6] = 0;
                  *((_DWORD *)v38 + 14) = 0;
                  v38[9] = 0;
                  v21 = 2;
                  *(_DWORD *)v12 = v36;
                }
LABEL_24:
                *((_DWORD *)v12 + 4) = 1397979221;
                a1 = (unsigned __int64)v12 + v72 + 80;
                *((_DWORD *)v12 + 5) = v21;
                v12[8] = a1;
                *((_DWORD *)v12 + 15) = v15;
                goto LABEL_25;
              }
              v18 = HIDWORD(KeGetPcr()[1].LockArray);
              v68 = v18;
              if ( UxDebugDisableLookaside )
              {
                v20 = (_QWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0630)(
                                  (unsigned int)dword_1401A0618,
                                  qword_1401A0620,
                                  (unsigned int)dword_1401A0628,
                                  0);
              }
              else
              {
                if ( UxCompactMode )
                {
                  v57 = qword_1401A0610;
                  v58 = KeGetCurrentNodeNumber();
                  v20 = (_QWORD *)PplAllocateFromLookasideListProcessor(v57, v58);
                }
                else
                {
                  v19 = qword_1401A0610 + ((unsigned __int64)(unsigned int)(v18 + 1) << 7);
                  if ( !*(_BYTE *)(v19 + 176) )
                    PplpLazyInitializeLookasideList(qword_1401A0610, v19 + 64);
                  v20 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v19 + 64));
                }
                v18 = v68;
              }
              v12 = v20;
              if ( v20 )
              {
                v21 = 0;
                *(_QWORD *)((char *)v12 + 4) = 0;
                *((_DWORD *)v12 + 3) = 0;
                v12[3] = 0;
                v12[4] = 0;
                v12[5] = 0;
                v12[6] = 0;
                *((_DWORD *)v12 + 14) = 0;
                v12[9] = 0;
                *(_DWORD *)v12 = v18;
                goto LABEL_24;
              }
            }
          }
LABEL_25:
          if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
            WPP_SF_q(1041, 15, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v12);
          if ( v12 )
          {
            v22 = v12[8];
            v23 = 0;
            v24 = *((_DWORD *)v12 + 15);
            for ( i = v74; ; v74 = i )
            {
              v73 = v24;
              v83 = v22;
              if ( !i )
              {
                v11 = P;
                *((_DWORD *)v12 + 14) = v22 - *((_DWORD *)v12 + 16);
                v26 = v78;
                v77 = v12;
                goto LABEL_31;
              }
              v27 = a6;
              v28 = a6;
              if ( (unsigned int)a6 > Size )
                v28 = Size;
              v76 = v28;
              if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
              {
                LODWORD(v67) = 0;
                WPP_SF_qqLqqLlq(
                  a1,
                  a2,
                  a6,
                  (_DWORD)v9,
                  v22,
                  v24,
                  (char)&MemoryDescriptorList,
                  (char)&a5,
                  v28,
                  v67,
                  &v75);
                v27 = a6;
                v24 = v73;
                i = v74;
              }
              v29 = *((unsigned int *)v9 + 114);
              Size_4 = v28 + v29 + *((_DWORD *)v9 + 115);
              if ( Size_4 > v24 )
              {
                v23 = -1073741789;
              }
              else
              {
                v30 = MemoryDescriptorList;
                v31 = (char *)(v22 + v29);
                v32 = a5;
                Next = MemoryDescriptorList;
                for ( j = a5; ; v32 = j )
                {
                  v81 = v31;
                  if ( !v28 )
                  {
                    v22 = v83;
                    a5 = v32;
                    MemoryDescriptorList = v30;
                    v35 = UxpSslSealMessage((_DWORD)v9, v83, Size_4, 0, (__int64)&v75);
                    v27 = a6;
                    v23 = v35;
                    v24 = v73;
                    i = v74;
                    v28 = v76;
                    goto LABEL_54;
                  }
                  if ( (v30->MdlFlags & 5) != 0 )
                  {
                    MappedSystemVa = (char *)v30->MappedSystemVa;
                  }
                  else
                  {
                    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v30, 0, MmCached, 0, 0, 0x40000000u);
                    v30 = Next;
                    v32 = j;
                    v31 = v81;
                  }
                  if ( !MappedSystemVa )
                    break;
                  v34 = v30->ByteCount - v32;
                  if ( v34 <= v28 )
                  {
                    Next = v30->Next;
                    j = 0;
                  }
                  else
                  {
                    v34 = v28;
                    j = v28 + v32;
                  }
                  memmove(v31, &MappedSystemVa[v32], v34);
                  v28 -= v34;
                  v30 = Next;
                  v31 = &v81[v34];
                }
                v27 = a6;
                v23 = -1073741670;
                v28 = v76;
                v22 = v83;
                v24 = v73;
                i = v74;
              }
LABEL_54:
              if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
              {
                WPP_SF_Dd(1041, 36, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v75, v23);
                v27 = a6;
                v24 = v73;
                i = v74;
              }
              if ( v23 < 0 )
                break;
              LODWORD(a1) = v75;
              if ( v75 > v24 )
              {
                v23 = -1073741675;
                break;
              }
              LODWORD(a3) = v27 - v28;
              --i;
              v22 += v75;
              LODWORD(a6) = a3;
              v24 -= v75;
            }
            UxSslFreeSendBufferList(v12);
            v12 = v77;
            v11 = P;
            v26 = v78;
          }
          else
          {
            v26 = v78;
            v23 = -1073741670;
            v12 = v77;
          }
          goto LABEL_31;
        }
        v23 = -1073741675;
        v26 = v14;
      }
LABEL_31:
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      {
        WPP_SF_qD(1041, 34, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v12, v23);
        v12 = v77;
      }
      if ( v23 < 0 )
        goto LABEL_69;
      if ( v11 )
      {
        v86[3] = v12;
        v12 = v77;
      }
      else
      {
        v11 = v12;
        P = v12;
      }
      v10 -= v26;
      v86 = v12;
      if ( !--v13 )
      {
        LOWORD(a2) = v89;
        LODWORD(a3) = v90;
        break;
      }
    }
  }
  if ( (_BYTE)a2 && *(_BYTE *)(*((_QWORD *)v9 + 212) + 8162LL) )
  {
    v23 = UxpSslGenerateCloseNotify(v9, &v85);
    if ( v23 < 0 )
    {
LABEL_69:
      UxSslFreeSendBufferList(v11);
      v39 = UlInvokeCompletionRoutine((unsigned int)v23, 0, a7, a8);
      goto LABEL_88;
    }
    LOWORD(a2) = v89;
    LODWORD(a3) = v90;
    if ( v11 )
      v12[3] = v85;
    else
      v11 = v85;
  }
  v87 = 0;
  v88 = 0;
  v40 = a8;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qlLqqqq((_DWORD)a7, (_WORD)a2, a3, (_DWORD)v9, a2, a3, (char)v11, (char)a7, a8, a9);
  v41 = 0;
  v42 = 0;
  if ( v11 )
  {
    v11[4] = v9;
    v43 = _InterlockedIncrement((volatile signed __int32 *)v9 + 5);
    if ( UxDebugCheckRefcount && v43 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v9 + 20), 0x2Bu, v43);
    v44 = v11;
    v11[5] = a7;
    v11[6] = a8;
    a7 = UxSslRestartSendRawData;
    do
    {
      v45 = v44[8];
      v46 = v44 + 9;
      v47 = *((unsigned int *)v44 + 14);
      v44[9] = 0;
      *((_WORD *)v44 + 41) = 0;
      *((_DWORD *)v44 + 28) = v47;
      v44[13] = v45 & 0xFFFFFFFFFFFFF000uLL;
      *((_WORD *)v44 + 40) = 8 * (((v47 + (unsigned __int64)(v45 & 0xFFF) + 4095) >> 12) + 6);
      *((_DWORD *)v44 + 29) = v45 & 0xFFF;
      MmBuildMdlForNonPagedPool((PMDL)(v44 + 9));
      v42 += *((unsigned int *)v44 + 14);
      if ( v41 )
        *v41 = v46;
      v44 = (_QWORD *)v44[3];
      v41 = v46;
    }
    while ( v44 );
    v41 = v11 + 9;
    v40 = (__int64)v11;
  }
  v48 = byte_1401A3780;
  LODWORD(v87) = 0;
  *((_QWORD *)&v87 + 1) = v41;
  LODWORD(v88) = 0;
  *((_QWORD *)&v88 + 1) = v42;
  if ( SBYTE2(xmmword_1401A2CA0) < 0 )
    WPP_SF_d(1047, 10, WPP_b6616b8acc683c557a6f97eb9025b7cb_Traceguids, (unsigned __int8)byte_1401A3780);
  if ( v48 )
    UxPktMonTraceSslSend(v9);
  v49 = *((_QWORD *)v9 + 7);
  v50 = *((_QWORD *)v9 + 6);
  if ( v89 )
    (*(void (__fastcall **)(__int64, _QWORD, __int128 *, __int64 (__fastcall *)(PVOID), __int64, __int64))(v49 + 88))(
      v50,
      v90,
      &v87,
      a7,
      v40,
      a9);
  else
    (*(void (__fastcall **)(__int64, _QWORD, __int128 *, __int64 (__fastcall *)(PVOID), __int64, __int64))(v49 + 96))(
      v50,
      v90,
      &v87,
      a7,
      v40,
      a9);
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1041, 19, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids);
  v39 = 259;
LABEL_88:
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 30, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v39);
  return v39;
}

```

## disassembly

```asm
0x14004c5d0  mov     [rsp-8+MemoryDescriptorList], r9
0x14004c5d5  mov     [rsp-8+arg_10], r8d
0x14004c5da  mov     [rsp-8+arg_8], dl
0x14004c5de  push    rbp
0x14004c5df  push    rsi
0x14004c5e0  push    rdi
0x14004c5e1  push    r13
0x14004c5e3  push    r14
0x14004c5e5  push    r15
0x14004c5e7  lea     rbp, [rsp-7]
0x14004c5ec  sub     rsp, 0E8h
0x14004c5f3  xor     r11d, r11d
0x14004c5f6  mov     r13, rcx
0x14004c5f9  mov     [rbp+2Fh+var_60], r11
0x14004c5fd  mov     [rbp+2Fh+var_98], r11
0x14004c601  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c608  mov     r14, [rbp+2Fh+arg_28]
0x14004c60c  jnz     loc_140176586
0x14004c612  test    r14, 7FFFh
0x14004c619  mov     [rsp+110h+arg_0], rbx
0x14004c621  mov     rsi, r11
0x14004c624  mov     [rsp+110h+var_30], r12
0x14004c62c  setnbe  sil
0x14004c630  mov     [rbp+2Fh+P], r11
0x14004c634  mov     rax, r14
0x14004c637  mov     [rbp+2Fh+var_58], r11
0x14004c63b  shr     rax, 0Fh
0x14004c63f  mov     r15, r11
0x14004c642  mov     rdi, r11
0x14004c645  add     rsi, rax
0x14004c648  jz      loc_140176635
0x14004c64e  mov     eax, 8000h
0x14004c653  mov     ebx, 1
0x14004c658  nop     dword ptr [rax+rax+00000000h]
0x14004c660  cmp     r14, rax
0x14004c663  mov     [rbp+2Fh+var_A4], r11d
0x14004c667  mov     r9d, r14d
0x14004c66a  cmova   r9d, eax
0x14004c66e  mov     dword ptr [rbp+2Fh+arg_28], r9d
0x14004c672  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c679  jnz     loc_14004CFA3
0x14004c67f  mov     r8d, [r13+1C8h]
0x14004c686  mov     rdi, r11
0x14004c689  mov     [rbp+2Fh+var_98], r11
0x14004c68d  cmp     r8d, 10000h
0x14004c694  jnb     loc_14004CCA3
0x14004c69a  mov     ecx, [r13+1CCh]
0x14004c6a1  cmp     ecx, 10000h
0x14004c6a7  jnb     loc_14004CCA3
0x14004c6ad  mov     r10d, [r13+1D0h]
0x14004c6b4  xor     edx, edx
0x14004c6b6  mov     eax, r9d
0x14004c6b9  mov     dword ptr [rbp+2Fh+Size], r10d
0x14004c6bd  div     r10d
0x14004c6c0  mov     r10d, r11d
0x14004c6c3  test    edx, edx
0x14004c6c5  mov     edx, r9d
0x14004c6c8  mov     [rbp+2Fh+var_90], rdx
0x14004c6cc  setnz   r10b
0x14004c6d0  add     rcx, r8
0x14004c6d3  add     r10d, eax
0x14004c6d6  mov     eax, r10d
0x14004c6d9  imul    rax, rcx
0x14004c6dd  mov     [rbp+2Fh+var_A8], r10d
0x14004c6e1  add     rax, rdx
0x14004c6e4  mov     r12d, eax
0x14004c6e7  cmp     r12, rax
0x14004c6ea  jnz     loc_14004CCB0
0x14004c6f0  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c6f7  jnz     loc_14004CEAE
0x14004c6fd  mov     rdx, r12; Length
0x14004c700  mov     ecx, 0FFFh; Base
0x14004c705  call    cs:__imp_MmSizeOfMdl
0x14004c70c  nop     dword ptr [rax+rax+00h]
0x14004c711  lea     ecx, [r12+50h]
0x14004c716  cmp     ecx, 50h ; 'P'
0x14004c719  jb      loc_14004C7E2
0x14004c71f  lea     ecx, [rax+7]
0x14004c722  and     ecx, 0FFFFFFF8h
0x14004c725  mov     [rbp+2Fh+var_AC], ecx
0x14004c728  lea     eax, [rcx+50h]
0x14004c72b  add     eax, r12d
0x14004c72e  cmp     eax, ecx
0x14004c730  jb      loc_14004C7E2
0x14004c736  cmp     r12d, 905h
0x14004c73d  ja      loc_14004CA25
0x14004c743  mov     ebx, gs:1A4h
0x14004c74b  cmp     cs:UxDebugDisableLookaside, 0
0x14004c752  mov     [rsp+110h+var_B0], ebx
0x14004c756  jnz     loc_14004CCBD
0x14004c75c  cmp     cs:UxCompactMode, 0
0x14004c763  jnz     loc_14004CECC
0x14004c769  mov     rcx, cs:qword_1401A0610
0x14004c770  inc     ebx
0x14004c772  shl     rbx, 7
0x14004c776  add     rbx, rcx
0x14004c779  movzx   eax, byte ptr [rbx+0B0h]
0x14004c780  test    al, al
0x14004c782  jz      loc_14004CEEF
0x14004c788  lea     rcx, [rbx+40h]; Lookaside
0x14004c78c  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004c793  nop     dword ptr [rax+rax+00h]
0x14004c798  mov     ebx, [rsp+110h+var_B0]
0x14004c79c  mov     rdi, rax
0x14004c79f  test    rax, rax
0x14004c7a2  jz      short loc_14004C7E2
0x14004c7a4  xor     eax, eax
0x14004c7a6  mov     [rdi+4], rax
0x14004c7aa  mov     [rdi+0Ch], eax
0x14004c7ad  mov     [rdi+18h], rax
0x14004c7b1  mov     [rdi+20h], rax
0x14004c7b5  mov     [rdi+28h], rax
0x14004c7b9  mov     [rdi+30h], rax
0x14004c7bd  mov     [rdi+38h], eax
0x14004c7c0  mov     [rdi+48h], rax
0x14004c7c4  mov     [rdi], ebx
0x14004c7c6  mov     ecx, [rbp+2Fh+var_AC]
0x14004c7c9  add     rcx, 50h ; 'P'
0x14004c7cd  mov     dword ptr [rdi+10h], 53537855h
0x14004c7d4  add     rcx, rdi
0x14004c7d7  mov     [rdi+14h], eax
0x14004c7da  mov     [rdi+40h], rcx
0x14004c7de  mov     [rdi+3Ch], r12d
0x14004c7e2  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c7e9  jnz     loc_14004CFDC
0x14004c7ef  test    rdi, rdi
0x14004c7f2  jz      loc_14004CFFA
0x14004c7f8  mov     rax, [rbp+2Fh+var_90]
0x14004c7fc  xor     r11d, r11d
0x14004c7ff  mov     r12, [rdi+40h]
0x14004c803  mov     ebx, r11d
0x14004c806  mov     r9d, [rdi+3Ch]
0x14004c80a  mov     r10d, [rbp+2Fh+var_A8]
0x14004c80e  mov     [rbp+2Fh+var_90], rax
0x14004c812  mov     [rbp+2Fh+var_AC], r9d
0x14004c816  mov     [rbp+2Fh+var_70], r12
0x14004c81a  test    r10d, r10d
0x14004c81d  jnz     short loc_14004C886
0x14004c81f  sub     r12d, [rdi+40h]
0x14004c823  mov     r15, [rbp+2Fh+P]
0x14004c827  mov     [rdi+38h], r12d
0x14004c82b  mov     r12, [rbp+2Fh+var_90]
0x14004c82f  mov     [rbp+2Fh+var_98], rdi
0x14004c833  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c83a  jnz     loc_14004C9FF
0x14004c840  test    ebx, ebx
0x14004c842  js      loc_14004CAD0
0x14004c848  test    r15, r15
0x14004c84b  jnz     loc_14004D0CC
0x14004c851  mov     r15, rdi
0x14004c854  mov     [rbp+2Fh+P], rdi
0x14004c858  sub     r14, r12
0x14004c85b  mov     [rbp+2Fh+var_58], rdi
0x14004c85f  mov     ebx, 1
0x14004c864  mov     eax, 8000h
0x14004c869  mov     r11d, 0
0x14004c86f  sub     rsi, 1
0x14004c873  jnz     loc_14004C660
0x14004c879  movzx   edx, [rbp+2Fh+arg_8]
0x14004c87d  mov     r8d, [rbp+2Fh+arg_10]
0x14004c881  jmp     loc_140176635
0x14004c886  mov     r8d, dword ptr [rbp+2Fh+arg_28]
0x14004c88a  mov     r15d, r8d
0x14004c88d  cmp     r8d, dword ptr [rbp+2Fh+Size]
0x14004c891  cmova   r15d, dword ptr [rbp+2Fh+Size]
0x14004c896  mov     [rbp+2Fh+var_A0], r15d
0x14004c89a  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c8a1  jnz     loc_14004D00C
0x14004c8a7  mov     ecx, [r13+1C8h]
0x14004c8ae  mov     eax, [r13+1CCh]
0x14004c8b5  add     eax, ecx
0x14004c8b7  add     eax, r15d
0x14004c8ba  mov     dword ptr [rbp+2Fh+Size+4], eax
0x14004c8bd  cmp     eax, r9d
0x14004c8c0  ja      loc_14004D075
0x14004c8c6  mov     r10, [rbp+2Fh+MemoryDescriptorList]
0x14004c8ca  lea     r9, [r12+rcx]
0x14004c8ce  mov     r8d, [rbp+2Fh+arg_20]
0x14004c8d2  mov     [rbp+2Fh+var_78], r10
0x14004c8d6  mov     [rsp+110h+var_B0], r8d
0x14004c8db  mov     [rbp+2Fh+var_80], r9
0x14004c8df  test    r15d, r15d
0x14004c8e2  jz      loc_14004C989
0x14004c8e8  test    byte ptr [r10+0Ah], 5
0x14004c8ed  jz      short loc_14004C94D
0x14004c8ef  mov     rax, [r10+18h]
0x14004c8f3  test    rax, rax
0x14004c8f6  jz      loc_14004D057
0x14004c8fc  mov     r12d, [r10+28h]
0x14004c900  mov     edx, r8d
0x14004c903  sub     r12d, r8d
0x14004c906  add     rdx, rax; Src
0x14004c909  cmp     r12d, r15d
0x14004c90c  jbe     short loc_14004C93F
0x14004c90e  add     r8d, r15d
0x14004c911  mov     r12d, r15d
0x14004c914  mov     [rsp+110h+var_B0], r8d
0x14004c919  mov     r8d, r12d; Size
0x14004c91c  mov     rcx, r9; void *
0x14004c91f  mov     ebx, r12d
0x14004c922  call    memmove
0x14004c927  mov     r9, [rbp+2Fh+var_80]
0x14004c92b  sub     r15d, r12d
0x14004c92e  mov     r10, [rbp+2Fh+var_78]
0x14004c932  add     r9, rbx
0x14004c935  mov     r8d, [rsp+110h+var_B0]
0x14004c93a  xor     r11d, r11d
0x14004c93d  jmp     short loc_14004C8DB
0x14004c93f  mov     r10, [r10]
0x14004c942  mov     [rbp+2Fh+var_78], r10
0x14004c946  mov     [rsp+110h+var_B0], r11d
0x14004c94b  jmp     short loc_14004C919
0x14004c94d  mov     [rsp+110h+Priority], 40000000h; Priority
0x14004c955  xor     r9d, r9d; RequestedAddress
0x14004c958  xor     edx, edx; AccessMode
0x14004c95a  mov     [rsp+110h+BugCheckOnFailure], r11d; BugCheckOnFailure
0x14004c95f  mov     r8d, 1; CacheType
0x14004c965  mov     rcx, r10; MemoryDescriptorList
0x14004c968  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004c96f  nop     dword ptr [rax+rax+00h]
0x14004c974  mov     r10, [rbp+2Fh+var_78]
0x14004c978  xor     r11d, r11d
0x14004c97b  mov     r8d, [rsp+110h+var_B0]
0x14004c980  mov     r9, [rbp+2Fh+var_80]
0x14004c984  jmp     loc_14004C8F3
0x14004c989  mov     r12, [rbp+2Fh+var_70]
0x14004c98d  lea     rax, [rbp+2Fh+var_A4]
0x14004c991  mov     [rbp+2Fh+arg_20], r8d
0x14004c995  mov     rdx, r12
0x14004c998  mov     r8d, dword ptr [rbp+2Fh+Size+4]
0x14004c99c  xor     r9d, r9d
0x14004c99f  mov     rcx, r13
0x14004c9a2  mov     [rbp+2Fh+MemoryDescriptorList], r10
0x14004c9a6  mov     qword ptr [rsp+110h+BugCheckOnFailure], rax
0x14004c9ab  call    UxpSslSealMessage
0x14004c9b0  mov     r8d, dword ptr [rbp+2Fh+arg_28]
0x14004c9b4  mov     ebx, eax
0x14004c9b6  mov     r9d, [rbp+2Fh+var_AC]
0x14004c9ba  mov     r10d, [rbp+2Fh+var_A8]
0x14004c9be  mov     r15d, [rbp+2Fh+var_A0]
0x14004c9c2  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c9c9  jnz     loc_14004D07F
0x14004c9cf  test    ebx, ebx
0x14004c9d1  js      loc_14004D0B3
0x14004c9d7  mov     ecx, [rbp+2Fh+var_A4]
0x14004c9da  cmp     ecx, r9d
0x14004c9dd  ja      loc_14004D0AE
0x14004c9e3  sub     r8d, r15d
0x14004c9e6  dec     r10d
0x14004c9e9  add     r12, rcx
0x14004c9ec  mov     dword ptr [rbp+2Fh+arg_28], r8d
0x14004c9f0  sub     r9d, ecx
0x14004c9f3  mov     [rbp+2Fh+var_A8], r10d
0x14004c9f7  xor     r11d, r11d
0x14004c9fa  jmp     loc_14004C812
0x14004c9ff  mov     edx, 22h ; '"'
0x14004ca04  mov     [rsp+110h+BugCheckOnFailure], ebx
0x14004ca08  mov     ecx, 411h
0x14004ca0d  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14004ca14  mov     r9, rdi
0x14004ca17  call    WPP_SF_qD
0x14004ca1c  mov     rdi, [rbp+2Fh+var_98]
0x14004ca20  jmp     loc_14004C840
0x14004ca25  cmp     r12d, 2105h
0x14004ca2c  jbe     loc_14004CCE5
0x14004ca32  cmp     r12d, 4105h
0x14004ca39  ja      loc_14004CDC6
0x14004ca3f  mov     ebx, gs:1A4h
0x14004ca47  cmp     cs:UxDebugDisableLookaside, 0
0x14004ca4e  mov     [rsp+110h+var_B0], ebx
0x14004ca52  jnz     loc_14004CD76
0x14004ca58  cmp     cs:UxCompactMode, 0
0x14004ca5f  jnz     loc_14004CF2E
0x14004ca65  mov     rcx, cs:qword_1401A0670
0x14004ca6c  inc     ebx
0x14004ca6e  shl     rbx, 7
0x14004ca72  add     rbx, rcx
0x14004ca75  movzx   eax, byte ptr [rbx+0B0h]
0x14004ca7c  test    al, al
0x14004ca7e  jz      loc_14004CF51
0x14004ca84  lea     rcx, [rbx+40h]; Lookaside
0x14004ca88  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004ca8f  nop     dword ptr [rax+rax+00h]
0x14004ca94  mov     ebx, [rsp+110h+var_B0]
0x14004ca98  mov     rdi, rax
0x14004ca9b  test    rax, rax
0x14004ca9e  jz      loc_14004C7E2
0x14004caa4  xor     eax, eax
0x14004caa6  mov     [rdi+4], rax
0x14004caaa  mov     [rdi+0Ch], eax
0x14004caad  mov     [rdi+18h], rax
0x14004cab1  mov     [rdi+20h], rax
0x14004cab5  mov     [rdi+28h], rax
0x14004cab9  mov     [rdi+30h], rax
0x14004cabd  mov     [rdi+38h], eax
0x14004cac0  mov     [rdi+48h], rax
0x14004cac4  mov     eax, 2
0x14004cac9  mov     [rdi], ebx
0x14004cacb  jmp     loc_14004C7C6
0x14004cad0  mov     rcx, r15; P
  ... truncated ...
```
