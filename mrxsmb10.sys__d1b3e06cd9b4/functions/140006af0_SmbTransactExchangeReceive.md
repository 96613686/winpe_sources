# SmbTransactExchangeReceive

- ea: `0x140006af0`
- end: `0x140007814`
- name: `SmbTransactExchangeReceive`
- size: `3364`
- prototype: `__int64 __fastcall(unsigned int *pContext, unsigned int, __int64, unsigned int *, __int64, _QWORD *, _DWORD *, __int16)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x140014200`

## callees

- `0x140006af0`
- `0x140007820`
- `0x1400098d0`
- `0x14000a700`
- `0x14000be94`
- `0x14000dc44`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e01c`
- `0x14000ebd8`
- `0x140010358`
- `0x140012fb4`
- `0x1400147ac`
- `0x1400148c4`
- `0x140014a04`
- `0x140016560`
- `0x1400166c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000704a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000704a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140007377`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140007711`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140007377`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140007711`
- `ntoskrnl!DbgPrint` at `0x140007147`
- `ntoskrnl!DbgPrint` at `0x140007147`
- `ntoskrnl!ExAllocatePool2` at `0x14000768b`
- `ntoskrnl!ExAllocatePool2` at `0x14000768b`
- `rdbss!RxPostToWorkerThread` at `0x1400074fc`
- `rdbss!RxPostToWorkerThread` at `0x1400074fc`
- `mrxsmb!MRxSmbDeviceObject` at `0x1400074da`

## pseudocode

```c
__int64 __fastcall SmbTransactExchangeReceive(
        unsigned int *pContext,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        _QWORD *a6,
        _DWORD *a7,
        __int16 a8)
{
  unsigned int v9; // r15d
  unsigned __int64 v10; // r13
  _QWORD *v11; // rdx
  unsigned int v13; // edi
  __int64 v14; // r8
  PMDL *v15; // r12
  unsigned __int64 v16; // rcx
  unsigned int v17; // ecx
  char v18; // cl
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // esi
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  int v24; // eax
  __int64 v25; // rdx
  unsigned int v26; // r9d
  unsigned int v27; // r11d
  char v28; // r12
  unsigned int v29; // r10d
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned int v32; // r12d
  PVOID v33; // rax
  __int64 v34; // rcx
  unsigned __int16 *v35; // r8
  int v36; // ecx
  int v37; // edx
  int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // edx
  unsigned int v41; // edx
  __int64 v42; // r12
  struct _MDL *v43; // rdx
  struct _MDL *i; // rcx
  _DWORD *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rdx
  bool v48; // zf
  unsigned int v49; // eax
  __int64 Pool2; // rax
  unsigned int *v51; // rax
  __int64 v52; // rdx
  int BugCheckOnFailure; // [rsp+20h] [rbp-91h]
  unsigned int Priority; // [rsp+28h] [rbp-89h]
  unsigned int v56; // [rsp+48h] [rbp-69h]
  int v57; // [rsp+4Ch] [rbp-65h] BYREF
  unsigned int v58; // [rsp+50h] [rbp-61h]
  _DWORD v59[2]; // [rsp+54h] [rbp-5Dh] BYREF
  unsigned int v60; // [rsp+5Ch] [rbp-55h]
  unsigned int v61; // [rsp+60h] [rbp-51h]
  int v62; // [rsp+64h] [rbp-4Dh]
  struct _MDL *v63; // [rsp+68h] [rbp-49h] BYREF
  _DWORD *v64; // [rsp+70h] [rbp-41h]
  __int128 v65; // [rsp+78h] [rbp-39h] BYREF
  _OWORD v66[2]; // [rsp+88h] [rbp-29h] BYREF

  v64 = a7;
  v9 = a3;
  v10 = a2;
  v11 = a6;
  memset(v66, 0, 28);
  memset(v59, 0, 5);
  v57 = 0;
  v63 = 0;
  v65 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, 32);
      v11 = a6;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_qlq(WPP_GLOBAL_Control->AttachedDevice, v11, a3, a5, *a4, *v11);
  }
  v13 = SmbCeParseSmbHeader((_DWORD)pContext, a5, (unsigned int)v59, (int)pContext + 40, v9, v10, (__int64)a4);
  if ( v13 )
    goto LABEL_8;
  if ( !*(_BYTE *)(a5 + 32) && pContext[90] != 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, pContext[10]);
    if ( (pContext[10] & 0x80000000) == 0 )
    {
      v15 = (PMDL *)a6;
      v13 = -1073741629;
      goto LABEL_185;
    }
  }
  if ( LOBYTE(v59[0]) )
  {
    if ( BYTE1(v59[0]) == 51 || BYTE1(v59[0]) == 37 || BYTE1(v59[0]) == 38 || BYTE1(v59[0]) == 50 )
    {
      v16 = 53;
    }
    else if ( (unsigned int)BYTE1(v59[0]) - 160 < 2 )
    {
      v16 = 69;
    }
    else
    {
      v13 = -1073741629;
      v16 = 0x10000001FLL;
    }
    if ( v10 >= v16 )
    {
      v17 = pContext[90];
      if ( v17 == 6 )
        goto LABEL_59;
      goto LABEL_50;
    }
    pContext[10] = -1073741629;
LABEL_29:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        48,
        WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids,
        v13,
        pContext[10]);
    v15 = (PMDL *)a6;
    v18 = 1;
    goto LABEL_33;
  }
  if ( pContext[90] != 3 )
    goto LABEL_29;
  v17 = pContext[90];
LABEL_50:
  v22 = v17 - 3;
  if ( !v22 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
    v46 = *a4;
    v47 = (unsigned int)(v46 + 3);
    if ( (unsigned int)v47 <= (unsigned int)v10 )
    {
      if ( (pContext[10] & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
        }
        v13 = pContext[10];
      }
      else if ( *(_BYTE *)(a5 + 4) != *((_BYTE *)pContext + 509) || *(_BYTE *)(v46 + a5) || *(_WORD *)(v46 + a5 + 1) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
        {
          goto LABEL_69;
        }
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
        v13 = -1073741629;
      }
      else
      {
        *a4 = v47;
        v48 = (*((_BYTE *)pContext + 510) & 2) == 0;
        pContext[90] = 4;
        if ( v48 )
          v13 = SmbCeReceive(pContext, v47, v14);
        if ( v13 )
        {
          pContext[12] = v13;
        }
        else
        {
          v13 = 0;
          SmbCeIncrementPendingOperations(pContext, 1);
          RxPostToWorkerThread(
            MRxSmbDeviceObject,
            DelayedWorkQueue,
            (PRX_WORK_QUEUE_ITEM)(pContext + 44),
            SendSecondaryRequests,
            pContext);
        }
      }
      goto LABEL_140;
    }
    goto LABEL_139;
  }
  v23 = v22 - 1;
  if ( v23 )
  {
    if ( v23 != 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
      }
      goto LABEL_140;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_62;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
  }
LABEL_59:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
LABEL_62:
  v24 = *(unsigned __int8 *)(a5 + 4);
  if ( (_BYTE)v24 == *((_BYTE *)pContext + 509) )
  {
    v25 = 0;
    v26 = 0;
    v14 = 0;
    v56 = 0;
    v27 = 0;
    v58 = 0;
    v28 = 0;
    v60 = 0;
    v61 = 0;
    v29 = 21;
    v62 = 21;
    if ( v24 != 51 )
    {
      v30 = a5 + *(unsigned __int16 *)((char *)v59 + 3);
      if ( v24 != 37 )
      {
        if ( v24 == 38 )
        {
          v25 = 0;
          goto LABEL_74;
        }
        if ( v24 != 50 )
        {
          v29 = 37;
          v62 = 37;
          if ( v24 == 160 )
          {
            v28 = 1;
            v14 = *(unsigned int *)(v30 + 4);
            v26 = 2 * *(unsigned __int8 *)(v30 + 36);
            v27 = *(_DWORD *)(v30 + 8);
            v58 = v26;
            v56 = 37;
            v60 = v14;
            v61 = v27;
          }
          else if ( v24 != 161 )
          {
            goto LABEL_69;
          }
          v25 = v56;
          goto LABEL_74;
        }
      }
      v28 = 1;
      v14 = *(unsigned __int16 *)(v30 + 1);
      v26 = 2 * *(unsigned __int8 *)(v30 + 19);
      v27 = *(unsigned __int16 *)(v30 + 3);
      v58 = v26;
      v56 = 21;
      v60 = v14;
      v61 = v27;
      v25 = 21;
    }
LABEL_74:
    if ( v13 )
    {
LABEL_140:
      v15 = (PMDL *)a6;
      goto LABEL_141;
    }
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        Priority = v27;
        BugCheckOnFailure = v14;
        WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, 40);
        v14 = v60;
        v26 = v58;
        v29 = v62;
        v27 = v61;
        v25 = v56;
      }
      if ( (unsigned int)v14 > pContext[108] || v27 > pContext[98] || v26 > pContext[116] )
        goto LABEL_8;
      pContext[108] = v14;
      pContext[98] = v27;
    }
    if ( *a4 + v29 <= (unsigned int)v10 )
    {
      if ( !v28 || !v26 )
        goto LABEL_104;
      v31 = *((_QWORD *)pContext + 57);
      v32 = v10 - v25;
      if ( v26 < (int)v10 - (int)v25 )
        v32 = v26;
      if ( v31 )
      {
        if ( (*(_BYTE *)(v31 + 10) & 5) != 0 )
        {
          v33 = *(PVOID *)(v31 + 24);
        }
        else
        {
          v33 = MmMapLockedPagesSpecifyCache((PMDL)v31, 0, MmCached, 0, 0, 0x40000000u);
          v26 = v58;
          v25 = v56;
        }
        if ( v33 )
        {
          if ( v26 == v32 )
          {
            memmove(v33, (const void *)(a5 + v25), v32);
            pContext[117] = v58 - v32;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
            }
            v13 = -1073741629;
          }
        }
        else
        {
          v13 = -1073741670;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v32);
      }
      if ( !v13 )
      {
LABEL_104:
        pContext[90] = 6;
        memset(v66, 0, 28);
        v65 = 0;
        if ( (unsigned int)v10 < 0x36 )
        {
LABEL_8:
          v15 = (PMDL *)a6;
          v13 = -1073741629;
          goto LABEL_185;
        }
        v34 = *(unsigned __int8 *)(a5 + 32);
        LODWORD(v65) = *(unsigned __int8 *)(a5 + 32);
        v35 = (unsigned __int16 *)(a5 + 33 + 2 * v34);
        if ( 2 * (int)v34 + 35 > (unsigned int)v10 )
        {
          DbgPrint("ExtraTransactBytes wc,bcp,smbh %lx,%p,%p\n", v34, v35, (const void *)a5);
          goto LABEL_8;
        }
        DWORD1(v66[1]) = *v35;
        DWORD2(v66[1]) = 2 * v34 + 33 + DWORD1(v66[1]) + 2;
        if ( (_BYTE)v34 )
        {
          switch ( *(_BYTE *)(a5 + 4) )
          {
            case 0x25:
            case 0x26:
            case 0x32:
            case 0x33:
              v36 = *(unsigned __int16 *)(a5 + 39);
              v37 = *(unsigned __int16 *)(a5 + 45);
              DWORD1(v65) = *(unsigned __int16 *)(a5 + 33);
              DWORD2(v65) = *(unsigned __int16 *)(a5 + 35);
              LODWORD(v66[0]) = *(unsigned __int16 *)(a5 + 41);
              DWORD1(v66[0]) = *(unsigned __int16 *)(a5 + 43);
              HIDWORD(v66[0]) = *(unsigned __int16 *)(a5 + 47);
              v38 = *(unsigned __int16 *)(a5 + 49);
              break;
            case 0xA0:
            case 0xA1:
              v36 = *(_DWORD *)(a5 + 44);
              v37 = *(_DWORD *)(a5 + 56);
              *(_QWORD *)((char *)&v65 + 4) = *(_QWORD *)(a5 + 36);
              *(_QWORD *)&v66[0] = *(_QWORD *)(a5 + 48);
              HIDWORD(v66[0]) = *(_DWORD *)(a5 + 60);
              v38 = *(_DWORD *)(a5 + 64);
              break;
            default:
              goto LABEL_8;
          }
          pContext[124] += v36;
          pContext[125] += v37;
          LODWORD(v66[1]) = v38;
          DWORD2(v66[0]) = v37;
          HIDWORD(v65) = v36;
        }
        v39 = ParseTransactResponse((__int64)pContext, (char *)&v65, v10, v9, a4, a5, &v63, &v57);
        v40 = DWORD2(v66[1]);
        v13 = v39;
        v14 = *a4;
        if ( v9 > DWORD2(v66[1]) )
          v40 = v9;
        if ( v40 < (int)v14 + v57 )
        {
          v15 = (PMDL *)a6;
          v13 = -1073741629;
          goto LABEL_185;
        }
        v41 = v40 - v14 - v57;
        v42 = v41;
        if ( v41 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              43,
              WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids,
              pContext,
              v41);
          }
          if ( v57 )
          {
            if ( (unsigned int)v42 > 8 )
            {
              v15 = (PMDL *)a6;
              v13 = -1073741629;
              goto LABEL_185;
            }
            *((_QWORD *)pContext + 67) = 0;
            *((_WORD *)pContext + 273) = 0;
            pContext[144] = v42;
            *((_QWORD *)pContext + 71) = (unsigned __int64)(pContext + 184) & 0xFFFFFFFFFFFFF000uLL;
            pContext[145] = ((_WORD)pContext + 736) & 0xFFF;
            *((_WORD *)pContext + 272) = 8
                                       * (((v42 + (unsigned __int64)(((_WORD)pContext + 736) & 0xFFF) + 4095) >> 12) + 6);
            MmBuildMdlForNonPagedPool((PMDL)(pContext + 134));
            v43 = v63;
            for ( i = v63->Next; i; i = i->Next )
              v43 = i;
            v43->Next = (struct _MDL *)(pContext + 134);
            v57 += v42;
          }
          else
          {
            if ( *a4 > v9 )
            {
              v15 = (PMDL *)a6;
              v13 = -1073741629;
              goto LABEL_185;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
            }
            *a4 = v9;
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v13);
        }
      }
      v15 = (PMDL *)a6;
      v45 = v64;
      *a6 = v63;
      *v45 = v57;
LABEL_141:
      v18 = 0;
      goto LABEL_33;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v29, *a4);
LABEL_139:
    v13 = -1073741802;
    goto LABEL_140;
  }
LABEL_69:
  v15 = (PMDL *)a6;
  v13 = -1073741629;
  v18 = 0;
LABEL_33:
  if ( (v13 || pContext[109] != pContext[108] || pContext[99] != pContext[98] || pContext[126]) && v18 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v13);
    if ( v9 <= (unsigned int)v10 && (a8 & 0x400) != 0 )
      goto LABEL_185;
    v13 = SmbTransactAccrueAndValidateFormatData(pContext, a5, (unsigned int)v10, &v65, BugCheckOnFailure, Priority);
    if ( v13 )
      goto LABEL_185;
    v21 = DWORD2(v66[1]);
    if ( v9 > DWORD2(v66[1]) )
      v21 = v9;
    if ( v21 > 0x10000 )
    {
      v13 = -1073741629;
      goto LABEL_185;
    }
    if ( pContext[124] >= HIDWORD(v65) && pContext[125] >= DWORD2(v66[0]) )
      goto LABEL_192;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          51,
          WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids,
          pContext,
          pContext[124],
          pContext[125]);
      }
    }
    v49 = SmbCeReceive(pContext, v19, v20);
    if ( v49 )
    {
      v13 = v49;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, pContext);
      }
    }
    else
    {
LABEL_192:
      if ( v21 <= (unsigned int)v10 )
        goto LABEL_185;
      Pool2 = ExAllocatePool2(66, v21, 1918135635);
      *((_QWORD *)pContext + 91) = Pool2;
      if ( !Pool2 )
        goto LABEL_185;
      v51 = v64;
      *a4 = 0;
      *v51 = v21;
      *v15 = (PMDL)(pContext + 134);
      v52 = *((_QWORD *)pContext + 91);
      *((_QWORD *)pContext + 67) = 0;
      *((_WORD *)pContext + 273) = 0;
      pContext[144] = v21;
      *((_QWORD *)pContext + 71) = v52 & 0xFFFFFFFFFFFFF000uLL;
      pContext[145] = v52 & 0xFFF;
      *((_WORD *)pContext + 272) = 8 * (((v21 + (unsigned __int64)(v52 & 0xFFF) + 4095) >> 12) + 6);
      MmBuildMdlForNonPagedPool(*v15);
      pContext[180] = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, pContext, 0);
      }
      v13 = -1073741802;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_lLqL(WPP_GLOBAL_Control->AttachedDevice, &WPP_GLOBAL_Control, v14, *a4, v13, *v15, *v64);
  if ( !v13 || v13 == -1073741802 )
    return v13;
LABEL_185:
  *a4 = v9;
  *v15 = 0;
  pContext[12] = v13;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v13);
  return 0;
}

```

## disassembly

```asm
0x140006af0  push    rbp
0x140006af2  push    rbx
0x140006af3  push    rsi
0x140006af4  push    rdi
0x140006af5  push    r12
0x140006af7  push    r13
0x140006af9  push    r14
0x140006afb  push    r15
0x140006afd  lea     rbp, [rsp-7]
0x140006b02  sub     rsp, 0B8h
0x140006b09  mov     rax, cs:__security_cookie
0x140006b10  xor     rax, rsp
0x140006b13  mov     [rbp+3Fh+var_48], rax
0x140006b17  mov     rax, [rbp+3Fh+arg_30]
0x140006b1b  xorps   xmm0, xmm0
0x140006b1e  mov     rsi, [rbp+3Fh+arg_20]
0x140006b22  mov     r14, r9
0x140006b25  mov     [rbp+3Fh+var_80], rax
0x140006b29  mov     r15d, r8d
0x140006b2c  xor     eax, eax
0x140006b2e  mov     r13d, edx
0x140006b31  mov     rdx, [rbp+3Fh+arg_28]
0x140006b35  mov     rbx, rcx
0x140006b38  movups  [rbp+3Fh+var_68], xmm0
0x140006b3c  mov     [rbp+3Fh+var_9C], eax
0x140006b3f  mov     [rbp+3Fh+var_98], al
0x140006b42  mov     [rbp+3Fh+var_A4], eax
0x140006b45  mov     [rbp+3Fh+var_88], rax
0x140006b49  mov     [rbp+3Fh+var_B0], rdx
0x140006b4d  movups  [rbp+3Fh+var_78], xmm0
0x140006b51  movups  [rbp+3Fh+var_68+0Ch], xmm0
0x140006b55  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006b5c  lea     rdi, WPP_GLOBAL_Control
0x140006b63  cmp     rcx, rdi
0x140006b66  jz      short loc_140006BC5
0x140006b68  test    dword ptr [rcx+2Ch], 400h
0x140006b6f  jz      short loc_140006B95
0x140006b71  mov     eax, [rbx+168h]
0x140006b77  mov     edx, 20h ; ' '
0x140006b7c  mov     rcx, [rcx+18h]
0x140006b80  mov     r9d, r8d
0x140006b83  mov     [rsp+0F0h+Priority], eax
0x140006b87  mov     [rsp+0F0h+BugCheckOnFailure], r13d
0x140006b8c  call    WPP_SF_lll
0x140006b91  mov     rdx, [rbp+3Fh+var_B0]
0x140006b95  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006b9c  cmp     rcx, rdi
0x140006b9f  jz      short loc_140006BC5
0x140006ba1  test    dword ptr [rcx+2Ch], 400h
0x140006ba8  jz      short loc_140006BC5
0x140006baa  mov     rax, [rdx]
0x140006bad  mov     r9, rsi
0x140006bb0  mov     rcx, [rcx+18h]
0x140006bb4  mov     qword ptr [rsp+0F0h+Priority], rax
0x140006bb9  mov     eax, [r14]
0x140006bbc  mov     [rsp+0F0h+BugCheckOnFailure], eax
0x140006bc0  call    WPP_SF_qlq
0x140006bc5  mov     [rsp+0F0h+var_C0], r14
0x140006bca  lea     r9, [rbx+28h]
0x140006bce  mov     [rsp+0F0h+Priority], r13d
0x140006bd3  lea     r8, [rbp+3Fh+var_9C]
0x140006bd7  mov     rdx, rsi
0x140006bda  mov     [rsp+0F0h+BugCheckOnFailure], r15d
0x140006bdf  mov     rcx, rbx
0x140006be2  call    SmbCeParseSmbHeader
0x140006be7  mov     edi, eax
0x140006be9  test    eax, eax
0x140006beb  jz      short loc_140006BFB
0x140006bed  mov     r12, [rbp+3Fh+var_B0]; jumptable 000000014000719A default case, cases 39-49,52-159
0x140006bf1  mov     edi, 0C00000C3h
0x140006bf6  jmp     loc_1400077AB
0x140006bfb  cmp     byte ptr [rsi+20h], 0
0x140006bff  jnz     short loc_140006C5A
0x140006c01  cmp     dword ptr [rbx+168h], 3
0x140006c08  jz      short loc_140006C5A
0x140006c0a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006c11  lea     rdx, WPP_GLOBAL_Control
0x140006c18  cmp     rcx, rdx
0x140006c1b  jz      short loc_140006C46
0x140006c1d  test    dword ptr [rcx+2Ch], 400h
0x140006c24  jz      short loc_140006C46
0x140006c26  mov     r9d, [rbx+28h]
0x140006c2a  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140006c31  mov     rcx, [rcx+18h]
0x140006c35  mov     edx, 22h ; '"'
0x140006c3a  call    WPP_SF_d
0x140006c3f  lea     rdx, WPP_GLOBAL_Control
0x140006c46  cmp     dword ptr [rbx+28h], 0
0x140006c4a  jl      short loc_140006C61
0x140006c4c  mov     r12, [rbp+3Fh+var_B0]
0x140006c50  mov     edi, 0C00000C3h
0x140006c55  jmp     loc_1400077AB
0x140006c5a  lea     rdx, WPP_GLOBAL_Control
0x140006c61  cmp     byte ptr [rbp+3Fh+var_9C], 0
0x140006c65  jbe     loc_140006DBD
0x140006c6b  movzx   ecx, byte ptr [rbp+3Fh+var_9C+1]
0x140006c6f  cmp     ecx, 33h ; '3'
0x140006c72  jz      short loc_140006CA5
0x140006c74  sub     ecx, 25h ; '%'
0x140006c77  jz      short loc_140006CA5
0x140006c79  sub     ecx, 1
0x140006c7c  jz      short loc_140006CA5
0x140006c7e  sub     ecx, 0Ch
0x140006c81  jz      short loc_140006CA5
0x140006c83  sub     ecx, 6Eh ; 'n'
0x140006c86  jz      short loc_140006C9E
0x140006c88  cmp     ecx, 1
0x140006c8b  jz      short loc_140006C9E
0x140006c8d  mov     edi, 0C00000C3h
0x140006c92  mov     rcx, 10000001Fh
0x140006c9c  jmp     short loc_140006CAA
0x140006c9e  mov     ecx, 45h ; 'E'
0x140006ca3  jmp     short loc_140006CAA
0x140006ca5  mov     ecx, 35h ; '5'
0x140006caa  cmp     r13, rcx
0x140006cad  jb      short loc_140006CC3
0x140006caf  mov     ecx, [rbx+168h]
0x140006cb5  cmp     ecx, 6
0x140006cb8  jnz     loc_140006DD0
0x140006cbe  jmp     loc_140006E52
0x140006cc3  mov     dword ptr [rbx+28h], 0C00000C3h
0x140006cca  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006cd1  cmp     rcx, rdx
0x140006cd4  jz      short loc_140006D05
0x140006cd6  test    dword ptr [rcx+2Ch], 400h
0x140006cdd  jz      short loc_140006D05
0x140006cdf  mov     eax, [rbx+28h]
0x140006ce2  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140006ce9  mov     rcx, [rcx+18h]
0x140006ced  mov     edx, 30h ; '0'
0x140006cf2  mov     r9d, edi
0x140006cf5  mov     [rsp+0F0h+BugCheckOnFailure], eax
0x140006cf9  call    WPP_SF_Dd
0x140006cfe  lea     rdx, WPP_GLOBAL_Control
0x140006d05  mov     r12, [rbp+3Fh+var_B0]
0x140006d09  mov     cl, 1
0x140006d0b  test    edi, edi
0x140006d0d  jnz     short loc_140006D37
0x140006d0f  mov     eax, [rbx+1B0h]
0x140006d15  cmp     [rbx+1B4h], eax
0x140006d1b  jnz     short loc_140006D37
0x140006d1d  mov     eax, [rbx+188h]
0x140006d23  cmp     [rbx+18Ch], eax
0x140006d29  jnz     short loc_140006D37
0x140006d2b  cmp     [rbx+1F8h], edi
0x140006d31  jz      loc_140007767
0x140006d37  test    cl, cl
0x140006d39  jz      loc_140007767
0x140006d3f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006d46  cmp     rcx, rdx
0x140006d49  jz      short loc_140006D6C
0x140006d4b  test    dword ptr [rcx+2Ch], 400h
0x140006d52  jz      short loc_140006D6C
0x140006d54  mov     rcx, [rcx+18h]
0x140006d58  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140006d5f  mov     edx, 31h ; '1'
0x140006d64  mov     r9d, edi
0x140006d67  call    WPP_SF_d
0x140006d6c  cmp     r15d, r13d
0x140006d6f  ja      short loc_140006D81
0x140006d71  test    [rbp+3Fh+arg_38], 400h
0x140006d7b  jnz     loc_1400077AB
0x140006d81  lea     r9, [rbp+3Fh+var_78]
0x140006d85  mov     r8d, r13d
0x140006d88  mov     rdx, rsi
0x140006d8b  mov     rcx, rbx
0x140006d8e  call    SmbTransactAccrueAndValidateFormatData
0x140006d93  mov     edi, eax
0x140006d95  test    eax, eax
0x140006d97  jnz     loc_1400077AB
0x140006d9d  mov     esi, [rbp+3Fh+var_50]
0x140006da0  cmp     r15d, esi
0x140006da3  cmova   esi, r15d
0x140006da7  cmp     esi, 10000h
0x140006dad  jbe     loc_140007589
0x140006db3  mov     edi, 0C00000C3h
0x140006db8  jmp     loc_1400077AB
0x140006dbd  cmp     dword ptr [rbx+168h], 3
0x140006dc4  jnz     loc_140006CCA
0x140006dca  mov     ecx, [rbx+168h]
0x140006dd0  sub     ecx, 3
0x140006dd3  jz      loc_140007446
0x140006dd9  sub     ecx, 1
0x140006ddc  jz      short loc_140006E21
0x140006dde  cmp     ecx, 1
0x140006de1  jz      short loc_140006E52
0x140006de3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006dea  lea     rax, WPP_GLOBAL_Control
0x140006df1  cmp     rcx, rax
0x140006df4  jz      loc_140007434
0x140006dfa  test    dword ptr [rcx+2Ch], 400h
0x140006e01  jz      loc_140007434
0x140006e07  mov     rcx, [rcx+18h]
0x140006e0b  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140006e12  mov     edx, 2Fh ; '/'
0x140006e17  call    WPP_SF_
0x140006e1c  jmp     loc_140007434
0x140006e21  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006e28  lea     rax, WPP_GLOBAL_Control
0x140006e2f  cmp     rcx, rax
0x140006e32  jz      short loc_140006E83
0x140006e34  test    dword ptr [rcx+2Ch], 400h
0x140006e3b  jz      short loc_140006E52
0x140006e3d  mov     rcx, [rcx+18h]
0x140006e41  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140006e48  mov     edx, 26h ; '&'
0x140006e4d  call    WPP_SF_
0x140006e52  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006e59  lea     rax, WPP_GLOBAL_Control
0x140006e60  cmp     rcx, rax
0x140006e63  jz      short loc_140006E83
0x140006e65  test    dword ptr [rcx+2Ch], 400h
0x140006e6c  jz      short loc_140006E83
0x140006e6e  mov     rcx, [rcx+18h]
0x140006e72  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140006e79  mov     edx, 27h ; '''
0x140006e7e  call    WPP_SF_
0x140006e83  movzx   eax, byte ptr [rsi+4]
0x140006e87  cmp     al, [rbx+1FDh]
0x140006e8d  jnz     short loc_140006EEF
0x140006e8f  xor     edx, edx
0x140006e91  xor     r9d, r9d
0x140006e94  xor     r8d, r8d
0x140006e97  mov     [rbp+3Fh+var_A8], edx
0x140006e9a  xor     r11d, r11d
0x140006e9d  mov     [rbp+3Fh+var_A0], r9d
0x140006ea1  xor     r12b, r12b
0x140006ea4  mov     [rbp+3Fh+var_94], r8d
0x140006ea8  mov     [rbp+3Fh+var_90], r11d
0x140006eac  mov     r10d, 15h
0x140006eb2  mov     [rbp+3Fh+var_8C], r10d
0x140006eb6  mov     ecx, eax
0x140006eb8  cmp     eax, 33h ; '3'
0x140006ebb  jz      loc_140006F5B
0x140006ec1  movzx   edx, word ptr [rbp+3Fh+var_9C+3]
0x140006ec5  add     rdx, rsi
0x140006ec8  sub     ecx, 25h ; '%'
0x140006ecb  jz      short loc_140006F2E
0x140006ecd  sub     ecx, 1
0x140006ed0  jz      loc_140006F58
0x140006ed6  sub     ecx, 0Ch
0x140006ed9  jz      short loc_140006F2E
0x140006edb  mov     r10d, 25h ; '%'
0x140006ee1  mov     [rbp+3Fh+var_8C], r10d
0x140006ee5  sub     ecx, 6Eh ; 'n'
0x140006ee8  jz      short loc_140006F06
0x140006eea  cmp     ecx, 1
0x140006eed  jz      short loc_140006F29
0x140006eef  mov     r12, [rbp+3Fh+var_B0]
0x140006ef3  lea     rdx, WPP_GLOBAL_Control
0x140006efa  mov     edi, 0C00000C3h
0x140006eff  xor     cl, cl
0x140006f01  jmp     loc_140006D0B
0x140006f06  movzx   r9d, byte ptr [rdx+24h]
0x140006f0b  mov     r12b, 1
0x140006f0e  mov     r8d, [rdx+4]
0x140006f12  add     r9d, r9d
0x140006f15  mov     r11d, [rdx+8]
0x140006f19  mov     [rbp+3Fh+var_A0], r9d
0x140006f1d  mov     [rbp+3Fh+var_A8], r10d
0x140006f21  mov     [rbp+3Fh+var_94], r8d
0x140006f25  mov     [rbp+3Fh+var_90], r11d
0x140006f29  mov     edx, [rbp+3Fh+var_A8]
0x140006f2c  jmp     short loc_140006F5B
0x140006f2e  movzx   r9d, byte ptr [rdx+13h]
0x140006f33  mov     r12b, 1
0x140006f36  movzx   r8d, word ptr [rdx+1]
0x140006f3b  add     r9d, r9d
0x140006f3e  movzx   r11d, word ptr [rdx+3]
0x140006f43  mov     [rbp+3Fh+var_A0], r9d
0x140006f47  mov     [rbp+3Fh+var_A8], r10d
0x140006f4b  mov     [rbp+3Fh+var_94], r8d
0x140006f4f  mov     [rbp+3Fh+var_90], r11d
0x140006f53  mov     edx, r10d
0x140006f56  jmp     short loc_140006F5B
0x140006f58  mov     edx, r8d
0x140006f5b  test    edi, edi
0x140006f5d  jnz     loc_140007434
0x140006f63  test    r12b, r12b
0x140006f66  jz      short loc_140006FE4
0x140006f68  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006f6f  lea     rax, WPP_GLOBAL_Control
0x140006f76  cmp     rcx, rax
0x140006f79  jz      short loc_140006FAF
0x140006f7b  test    dword ptr [rcx+2Ch], 400h
0x140006f82  jz      short loc_140006FAF
0x140006f84  mov     rcx, [rcx+18h]
0x140006f88  mov     edx, 28h ; '('
0x140006f8d  mov     [rsp+0F0h+Priority], r11d
0x140006f92  mov     [rsp+0F0h+BugCheckOnFailure], r8d
0x140006f97  call    WPP_SF_lll
0x140006f9c  mov     r8d, [rbp+3Fh+var_94]
0x140006fa0  mov     r9d, [rbp+3Fh+var_A0]
0x140006fa4  mov     r10d, [rbp+3Fh+var_8C]
0x140006fa8  mov     r11d, [rbp+3Fh+var_90]
0x140006fac  mov     edx, [rbp+3Fh+var_A8]
0x140006faf  cmp     r8d, [rbx+1B0h]
0x140006fb6  ja      def_14000719A; jumptable 000000014000719A default case, cases 39-49,52-159
0x140006fbc  cmp     r11d, [rbx+188h]
0x140006fc3  ja      def_14000719A; jumptable 000000014000719A default case, cases 39-49,52-159
  ... truncated ...
```
