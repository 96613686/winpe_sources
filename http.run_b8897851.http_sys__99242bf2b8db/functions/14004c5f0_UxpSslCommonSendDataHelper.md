# UxpSslCommonSendDataHelper

- ea: `0x14004c5f0`
- end: `0x14004d14a`
- name: `UxpSslCommonSendDataHelper`
- size: `2906`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004ec00`

## callees

- `0x14000a350`
- `0x140049d28`
- `0x14004ba90`
- `0x14004bdb0`
- `0x14004c5f0`
- `0x14004d150`
- `0x140051410`
- `0x14013b034`
- `0x140155a68`
- `0x1401677e0`
- `0x140167840`
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

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14004cbca`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14004cbca`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004c988`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004c988`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c7ac`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004caa8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004cd4e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004c7ac`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004caa8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004cd4e`
- `ntoskrnl!MmSizeOfMdl` at `0x14004c725`
- `ntoskrnl!MmSizeOfMdl` at `0x14004c725`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cef3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf24`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf55`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf86`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cef3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf24`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf55`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14004cf86`
- `ntoskrnl!ExAllocatePool3` at `0x1401764f3`
- `ntoskrnl!ExAllocatePool3` at `0x1401764f3`

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
0x14004c5f0  mov     [rsp-8+MemoryDescriptorList], r9
0x14004c5f5  mov     [rsp-8+arg_10], r8d
0x14004c5fa  mov     [rsp-8+arg_8], dl
0x14004c5fe  push    rbp
0x14004c5ff  push    rsi
0x14004c600  push    rdi
0x14004c601  push    r13
0x14004c603  push    r14
0x14004c605  push    r15
0x14004c607  lea     rbp, [rsp-7]
0x14004c60c  sub     rsp, 0E8h
0x14004c613  xor     r11d, r11d
0x14004c616  mov     r13, rcx
0x14004c619  mov     [rbp+2Fh+var_60], r11
0x14004c61d  mov     [rbp+2Fh+var_98], r11
0x14004c621  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c628  mov     r14, [rbp+2Fh+arg_28]
0x14004c62c  jnz     loc_140176486
0x14004c632  test    r14, 7FFFh
0x14004c639  mov     [rsp+110h+arg_0], rbx
0x14004c641  mov     rsi, r11
0x14004c644  mov     [rsp+110h+var_30], r12
0x14004c64c  setnbe  sil
0x14004c650  mov     [rbp+2Fh+P], r11
0x14004c654  mov     rax, r14
0x14004c657  mov     [rbp+2Fh+var_58], r11
0x14004c65b  shr     rax, 0Fh
0x14004c65f  mov     r15, r11
0x14004c662  mov     rdi, r11
0x14004c665  add     rsi, rax
0x14004c668  jz      loc_140176535
0x14004c66e  mov     eax, 8000h
0x14004c673  mov     ebx, 1
0x14004c678  nop     dword ptr [rax+rax+00000000h]
0x14004c680  cmp     r14, rax
0x14004c683  mov     [rbp+2Fh+var_A4], r11d
0x14004c687  mov     r9d, r14d
0x14004c68a  cmova   r9d, eax
0x14004c68e  mov     dword ptr [rbp+2Fh+arg_28], r9d
0x14004c692  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c699  jnz     loc_14004CFC3
0x14004c69f  mov     r8d, [r13+1C8h]
0x14004c6a6  mov     rdi, r11
0x14004c6a9  mov     [rbp+2Fh+var_98], r11
0x14004c6ad  cmp     r8d, 10000h
0x14004c6b4  jnb     loc_14004CCC3
0x14004c6ba  mov     ecx, [r13+1CCh]
0x14004c6c1  cmp     ecx, 10000h
0x14004c6c7  jnb     loc_14004CCC3
0x14004c6cd  mov     r10d, [r13+1D0h]
0x14004c6d4  xor     edx, edx
0x14004c6d6  mov     eax, r9d
0x14004c6d9  mov     dword ptr [rbp+2Fh+Size], r10d
0x14004c6dd  div     r10d
0x14004c6e0  mov     r10d, r11d
0x14004c6e3  test    edx, edx
0x14004c6e5  mov     edx, r9d
0x14004c6e8  mov     [rbp+2Fh+var_90], rdx
0x14004c6ec  setnz   r10b
0x14004c6f0  add     rcx, r8
0x14004c6f3  add     r10d, eax
0x14004c6f6  mov     eax, r10d
0x14004c6f9  imul    rax, rcx
0x14004c6fd  mov     [rbp+2Fh+var_A8], r10d
0x14004c701  add     rax, rdx
0x14004c704  mov     r12d, eax
0x14004c707  cmp     r12, rax
0x14004c70a  jnz     loc_14004CCD0
0x14004c710  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c717  jnz     loc_14004CECE
0x14004c71d  mov     rdx, r12; Length
0x14004c720  mov     ecx, 0FFFh; Base
0x14004c725  call    cs:__imp_MmSizeOfMdl
0x14004c72c  nop     dword ptr [rax+rax+00h]
0x14004c731  lea     ecx, [r12+50h]
0x14004c736  cmp     ecx, 50h ; 'P'
0x14004c739  jb      loc_14004C802
0x14004c73f  lea     ecx, [rax+7]
0x14004c742  and     ecx, 0FFFFFFF8h
0x14004c745  mov     [rbp+2Fh+var_AC], ecx
0x14004c748  lea     eax, [rcx+50h]
0x14004c74b  add     eax, r12d
0x14004c74e  cmp     eax, ecx
0x14004c750  jb      loc_14004C802
0x14004c756  cmp     r12d, 905h
0x14004c75d  ja      loc_14004CA45
0x14004c763  mov     ebx, gs:1A4h
0x14004c76b  cmp     cs:UxDebugDisableLookaside, 0
0x14004c772  mov     [rsp+110h+var_B0], ebx
0x14004c776  jnz     loc_14004CCDD
0x14004c77c  cmp     cs:UxCompactMode, 0
0x14004c783  jnz     loc_14004CEEC
0x14004c789  mov     rcx, cs:qword_1401A0610
0x14004c790  inc     ebx
0x14004c792  shl     rbx, 7
0x14004c796  add     rbx, rcx
0x14004c799  movzx   eax, byte ptr [rbx+0B0h]
0x14004c7a0  test    al, al
0x14004c7a2  jz      loc_14004CF0F
0x14004c7a8  lea     rcx, [rbx+40h]; Lookaside
0x14004c7ac  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004c7b3  nop     dword ptr [rax+rax+00h]
0x14004c7b8  mov     ebx, [rsp+110h+var_B0]
0x14004c7bc  mov     rdi, rax
0x14004c7bf  test    rax, rax
0x14004c7c2  jz      short loc_14004C802
0x14004c7c4  xor     eax, eax
0x14004c7c6  mov     [rdi+4], rax
0x14004c7ca  mov     [rdi+0Ch], eax
0x14004c7cd  mov     [rdi+18h], rax
0x14004c7d1  mov     [rdi+20h], rax
0x14004c7d5  mov     [rdi+28h], rax
0x14004c7d9  mov     [rdi+30h], rax
0x14004c7dd  mov     [rdi+38h], eax
0x14004c7e0  mov     [rdi+48h], rax
0x14004c7e4  mov     [rdi], ebx
0x14004c7e6  mov     ecx, [rbp+2Fh+var_AC]
0x14004c7e9  add     rcx, 50h ; 'P'
0x14004c7ed  mov     dword ptr [rdi+10h], 53537855h
0x14004c7f4  add     rcx, rdi
0x14004c7f7  mov     [rdi+14h], eax
0x14004c7fa  mov     [rdi+40h], rcx
0x14004c7fe  mov     [rdi+3Ch], r12d
0x14004c802  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c809  jnz     loc_14004CFFC
0x14004c80f  test    rdi, rdi
0x14004c812  jz      loc_14004D01A
0x14004c818  mov     rax, [rbp+2Fh+var_90]
0x14004c81c  xor     r11d, r11d
0x14004c81f  mov     r12, [rdi+40h]
0x14004c823  mov     ebx, r11d
0x14004c826  mov     r9d, [rdi+3Ch]
0x14004c82a  mov     r10d, [rbp+2Fh+var_A8]
0x14004c82e  mov     [rbp+2Fh+var_90], rax
0x14004c832  mov     [rbp+2Fh+var_AC], r9d
0x14004c836  mov     [rbp+2Fh+var_70], r12
0x14004c83a  test    r10d, r10d
0x14004c83d  jnz     short loc_14004C8A6
0x14004c83f  sub     r12d, [rdi+40h]
0x14004c843  mov     r15, [rbp+2Fh+P]
0x14004c847  mov     [rdi+38h], r12d
0x14004c84b  mov     r12, [rbp+2Fh+var_90]
0x14004c84f  mov     [rbp+2Fh+var_98], rdi
0x14004c853  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c85a  jnz     loc_14004CA1F
0x14004c860  test    ebx, ebx
0x14004c862  js      loc_14004CAF0
0x14004c868  test    r15, r15
0x14004c86b  jnz     loc_14004D0EC
0x14004c871  mov     r15, rdi
0x14004c874  mov     [rbp+2Fh+P], rdi
0x14004c878  sub     r14, r12
0x14004c87b  mov     [rbp+2Fh+var_58], rdi
0x14004c87f  mov     ebx, 1
0x14004c884  mov     eax, 8000h
0x14004c889  mov     r11d, 0
0x14004c88f  sub     rsi, 1
0x14004c893  jnz     loc_14004C680
0x14004c899  movzx   edx, [rbp+2Fh+arg_8]
0x14004c89d  mov     r8d, [rbp+2Fh+arg_10]
0x14004c8a1  jmp     loc_140176535
0x14004c8a6  mov     r8d, dword ptr [rbp+2Fh+arg_28]
0x14004c8aa  mov     r15d, r8d
0x14004c8ad  cmp     r8d, dword ptr [rbp+2Fh+Size]
0x14004c8b1  cmova   r15d, dword ptr [rbp+2Fh+Size]
0x14004c8b6  mov     [rbp+2Fh+var_A0], r15d
0x14004c8ba  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c8c1  jnz     loc_14004D02C
0x14004c8c7  mov     ecx, [r13+1C8h]
0x14004c8ce  mov     eax, [r13+1CCh]
0x14004c8d5  add     eax, ecx
0x14004c8d7  add     eax, r15d
0x14004c8da  mov     dword ptr [rbp+2Fh+Size+4], eax
0x14004c8dd  cmp     eax, r9d
0x14004c8e0  ja      loc_14004D095
0x14004c8e6  mov     r10, [rbp+2Fh+MemoryDescriptorList]
0x14004c8ea  lea     r9, [r12+rcx]
0x14004c8ee  mov     r8d, [rbp+2Fh+arg_20]
0x14004c8f2  mov     [rbp+2Fh+var_78], r10
0x14004c8f6  mov     [rsp+110h+var_B0], r8d
0x14004c8fb  mov     [rbp+2Fh+var_80], r9
0x14004c8ff  test    r15d, r15d
0x14004c902  jz      loc_14004C9A9
0x14004c908  test    byte ptr [r10+0Ah], 5
0x14004c90d  jz      short loc_14004C96D
0x14004c90f  mov     rax, [r10+18h]
0x14004c913  test    rax, rax
0x14004c916  jz      loc_14004D077
0x14004c91c  mov     r12d, [r10+28h]
0x14004c920  mov     edx, r8d
0x14004c923  sub     r12d, r8d
0x14004c926  add     rdx, rax; Src
0x14004c929  cmp     r12d, r15d
0x14004c92c  jbe     short loc_14004C95F
0x14004c92e  add     r8d, r15d
0x14004c931  mov     r12d, r15d
0x14004c934  mov     [rsp+110h+var_B0], r8d
0x14004c939  mov     r8d, r12d; Size
0x14004c93c  mov     rcx, r9; void *
0x14004c93f  mov     ebx, r12d
0x14004c942  call    memmove
0x14004c947  mov     r9, [rbp+2Fh+var_80]
0x14004c94b  sub     r15d, r12d
0x14004c94e  mov     r10, [rbp+2Fh+var_78]
0x14004c952  add     r9, rbx
0x14004c955  mov     r8d, [rsp+110h+var_B0]
0x14004c95a  xor     r11d, r11d
0x14004c95d  jmp     short loc_14004C8FB
0x14004c95f  mov     r10, [r10]
0x14004c962  mov     [rbp+2Fh+var_78], r10
0x14004c966  mov     [rsp+110h+var_B0], r11d
0x14004c96b  jmp     short loc_14004C939
0x14004c96d  mov     [rsp+110h+Priority], 40000000h; Priority
0x14004c975  xor     r9d, r9d; RequestedAddress
0x14004c978  xor     edx, edx; AccessMode
0x14004c97a  mov     [rsp+110h+BugCheckOnFailure], r11d; BugCheckOnFailure
0x14004c97f  mov     r8d, 1; CacheType
0x14004c985  mov     rcx, r10; MemoryDescriptorList
0x14004c988  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004c98f  nop     dword ptr [rax+rax+00h]
0x14004c994  mov     r10, [rbp+2Fh+var_78]
0x14004c998  xor     r11d, r11d
0x14004c99b  mov     r8d, [rsp+110h+var_B0]
0x14004c9a0  mov     r9, [rbp+2Fh+var_80]
0x14004c9a4  jmp     loc_14004C913
0x14004c9a9  mov     r12, [rbp+2Fh+var_70]
0x14004c9ad  lea     rax, [rbp+2Fh+var_A4]
0x14004c9b1  mov     [rbp+2Fh+arg_20], r8d
0x14004c9b5  mov     rdx, r12
0x14004c9b8  mov     r8d, dword ptr [rbp+2Fh+Size+4]
0x14004c9bc  xor     r9d, r9d
0x14004c9bf  mov     rcx, r13
0x14004c9c2  mov     [rbp+2Fh+MemoryDescriptorList], r10
0x14004c9c6  mov     qword ptr [rsp+110h+BugCheckOnFailure], rax
0x14004c9cb  call    UxpSslSealMessage
0x14004c9d0  mov     r8d, dword ptr [rbp+2Fh+arg_28]
0x14004c9d4  mov     ebx, eax
0x14004c9d6  mov     r9d, [rbp+2Fh+var_AC]
0x14004c9da  mov     r10d, [rbp+2Fh+var_A8]
0x14004c9de  mov     r15d, [rbp+2Fh+var_A0]
0x14004c9e2  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004c9e9  jnz     loc_14004D09F
0x14004c9ef  test    ebx, ebx
0x14004c9f1  js      loc_14004D0D3
0x14004c9f7  mov     ecx, [rbp+2Fh+var_A4]
0x14004c9fa  cmp     ecx, r9d
0x14004c9fd  ja      loc_14004D0CE
0x14004ca03  sub     r8d, r15d
0x14004ca06  dec     r10d
0x14004ca09  add     r12, rcx
0x14004ca0c  mov     dword ptr [rbp+2Fh+arg_28], r8d
0x14004ca10  sub     r9d, ecx
0x14004ca13  mov     [rbp+2Fh+var_A8], r10d
0x14004ca17  xor     r11d, r11d
0x14004ca1a  jmp     loc_14004C832
0x14004ca1f  mov     edx, 22h ; '"'
0x14004ca24  mov     [rsp+110h+BugCheckOnFailure], ebx
0x14004ca28  mov     ecx, 411h
0x14004ca2d  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14004ca34  mov     r9, rdi
0x14004ca37  call    WPP_SF_qD
0x14004ca3c  mov     rdi, [rbp+2Fh+var_98]
0x14004ca40  jmp     loc_14004C860
0x14004ca45  cmp     r12d, 2105h
0x14004ca4c  jbe     loc_14004CD05
0x14004ca52  cmp     r12d, 4105h
0x14004ca59  ja      loc_14004CDE6
0x14004ca5f  mov     ebx, gs:1A4h
0x14004ca67  cmp     cs:UxDebugDisableLookaside, 0
0x14004ca6e  mov     [rsp+110h+var_B0], ebx
0x14004ca72  jnz     loc_14004CD96
0x14004ca78  cmp     cs:UxCompactMode, 0
0x14004ca7f  jnz     loc_14004CF4E
0x14004ca85  mov     rcx, cs:qword_1401A0670
0x14004ca8c  inc     ebx
0x14004ca8e  shl     rbx, 7
0x14004ca92  add     rbx, rcx
0x14004ca95  movzx   eax, byte ptr [rbx+0B0h]
0x14004ca9c  test    al, al
0x14004ca9e  jz      loc_14004CF71
0x14004caa4  lea     rcx, [rbx+40h]; Lookaside
0x14004caa8  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004caaf  nop     dword ptr [rax+rax+00h]
0x14004cab4  mov     ebx, [rsp+110h+var_B0]
0x14004cab8  mov     rdi, rax
0x14004cabb  test    rax, rax
0x14004cabe  jz      loc_14004C802
0x14004cac4  xor     eax, eax
0x14004cac6  mov     [rdi+4], rax
0x14004caca  mov     [rdi+0Ch], eax
0x14004cacd  mov     [rdi+18h], rax
0x14004cad1  mov     [rdi+20h], rax
0x14004cad5  mov     [rdi+28h], rax
0x14004cad9  mov     [rdi+30h], rax
0x14004cadd  mov     [rdi+38h], eax
0x14004cae0  mov     [rdi+48h], rax
0x14004cae4  mov     eax, 2
0x14004cae9  mov     [rdi], ebx
0x14004caeb  jmp     loc_14004C7E6
0x14004caf0  mov     rcx, r15; P
  ... truncated ...
```
