# CscBackPatchObject

- ea: `0x140088890`
- end: `0x14008930e`
- name: `CscBackPatchObject`
- size: `2686`
- prototype: `__int64 __fastcall(__int64, char *, __int64)`
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x140062b70`
- `0x14006e884`
- `0x14007fc40`

## callees

- `0x1400017c0`
- `0x14000dedc`
- `0x14000f8b0`
- `0x140014da4`
- `0x1400169d4`
- `0x140018930`
- `0x14001a494`
- `0x14001a624`
- `0x14001ac1c`
- `0x14001c8f0`
- `0x14001cc14`
- `0x14002f010`
- `0x14002f440`
- `0x14004f884`
- `0x14004faf4`
- `0x1400501e8`
- `0x140088580`
- `0x140088890`

## import_xrefs

- `rdbss!RxFlushFcbInSystemCache` at `0x140088b7b`
- `rdbss!RxFlushFcbInSystemCache` at `0x140088b7b`
- `rdbss!RxCloseAndFreeMRxStateOnFcb` at `0x140088a54`
- `rdbss!RxCloseAndFreeMRxStateOnFcb` at `0x140088e48`
- `rdbss!RxCloseAndFreeMRxStateOnFcb` at `0x140088a54`
- `rdbss!RxCloseAndFreeMRxStateOnFcb` at `0x140088e48`
- `rdbss!RxFinishFcbInitialization` at `0x140089161`
- `rdbss!RxFinishFcbInitialization` at `0x140089161`
- `rdbss!RxUpdateOplockStateOnCreate` at `0x14008900c`
- `rdbss!RxUpdateOplockStateOnCreate` at `0x14008924a`
- `rdbss!RxUpdateOplockStateOnCreate` at `0x14008900c`
- `rdbss!RxUpdateOplockStateOnCreate` at `0x14008924a`
- `rdbss!RxIterateOnFcbOpens` at `0x140088c89`
- `rdbss!RxIterateOnFcbOpens` at `0x140088da4`
- `rdbss!RxIterateOnFcbOpens` at `0x140088c89`
- `rdbss!RxIterateOnFcbOpens` at `0x140088da4`
- `rdbss!RxSetFcbNameTargetType` at `0x140088ada`
- `rdbss!RxSetFcbNameTargetType` at `0x140088d35`
- `rdbss!RxSetFcbNameTargetType` at `0x140088ada`
- `rdbss!RxSetFcbNameTargetType` at `0x140088d35`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140088ab7`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140088ab7`
- `rdbss!RxReleaseFcbPagingInMRx` at `0x140088a98`
- `rdbss!RxReleaseFcbPagingInMRx` at `0x140088a98`
- `rdbss!RxPurgeFcbInSystemCache` at `0x140088f4e`
- `rdbss!RxPurgeFcbInSystemCache` at `0x140088f4e`
- `rdbss!RxCreateRxContext` at `0x140088c0d`
- `rdbss!RxCreateRxContext` at `0x140088c0d`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x1400889ad`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x1400889ad`

## pseudocode

```c
__int64 __fastcall CscBackPatchObject(__int64 a1, char *a2, __int64 a3)
{
  struct _FCB *v3; // r14
  int v4; // esi
  PRX_CONTEXT RxContext; // r15
  __int64 v9; // r8
  bool v10; // zf
  bool v11; // bl
  char v12; // dl
  NTSTATUS InformationEntry; // ebx
  __int64 v14; // r8
  int v15; // ecx
  char v16; // dl
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // r8d
  __int64 v20; // rax
  __int16 v21; // ax
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // r12
  char v26; // r9
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rax
  int v33; // [rsp+28h] [rbp-D8h]
  int v34; // [rsp+28h] [rbp-D8h]
  char v35; // [rsp+41h] [rbp-BFh] BYREF
  char v36; // [rsp+42h] [rbp-BEh]
  CSHORT NodeTypeCode; // [rsp+44h] [rbp-BCh]
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v39[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE InitPacket[80]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v41[20]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v42; // [rsp+150h] [rbp+50h] BYREF
  __int128 v43; // [rsp+160h] [rbp+60h]
  unsigned __int64 v44; // [rsp+170h] [rbp+70h]
  _OWORD v45[3]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v46; // [rsp+1A8h] [rbp+A8h]
  _DWORD v47[20]; // [rsp+1B0h] [rbp+B0h] BYREF

  v3 = *(struct _FCB **)(a1 + 56);
  v4 = 0;
  v38 = a1;
  RxContext = 0;
  memset(v47, 0, sizeof(v47));
  v46 = 0;
  memset(v45, 0, sizeof(v45));
  v44 = 0;
  v42 = 0;
  v43 = 0;
  memset(v41, 0, 0x98u);
  v9 = *(_QWORD *)(a3 + 8);
  v35 = 0;
  NodeTypeCode = v3->Header.NodeTypeCode;
  v10 = *(_QWORD *)(a1 + 80) == (_QWORD)CscDeviceObject;
  v36 = 0;
  v11 = !v10;
  v39[0] = 0;
  if ( !v9 )
  {
    v12 = 0;
    InformationEntry = -1073741811;
    v4 = 2798;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_qDdd(
      WPP_GLOBAL_Control->AttachedDevice,
      WPP_GLOBAL_Control,
      v9,
      v3,
      *(_DWORD *)(v9 + 4),
      *(_DWORD *)(v9 + 40),
      *(_DWORD *)(*(_QWORD *)(a3 + 24) + 8LL));
  LOBYTE(v9) = 1;
  RxAcquireExclusiveFcbPagingInMRx(0, v3, v9);
  v12 = 1;
  if ( !v11 || (v14 = *(_QWORD *)(a3 + 8), v15 = *(_DWORD *)(v14 + 4), (v15 & 0x60) != 0) )
  {
    InformationEntry = -1073741581;
    goto LABEL_125;
  }
  v16 = *a2;
  if ( (*a2 & 1) != 0 && (a2[1] & 0x14) != 0x14 )
  {
    InformationEntry = -1073741580;
LABEL_11:
    v12 = 1;
LABEL_125:
    v4 = 2863;
    goto LABEL_26;
  }
  if ( (v15 & 0x1000) != 0 )
  {
    InformationEntry = -1073741576;
    goto LABEL_11;
  }
  if ( (v15 & 0x1166F) == 0 )
  {
    InformationEntry = -1073741575;
    goto LABEL_11;
  }
  if ( (v16 & 0x40) != 0 )
  {
    InformationEntry = -1073741579;
    goto LABEL_11;
  }
  if ( (v16 & 0x20) == 0 )
  {
    InformationEntry = -1073741574;
    goto LABEL_11;
  }
  if ( (v15 & 0x80000) != 0 )
  {
    InformationEntry = -1073741225;
    *(_DWORD *)(v14 + 4) = v15 & 0xFFF7FFFF;
    goto LABEL_11;
  }
  if ( (v15 & 0x10) != 0 )
  {
    InformationEntry = RxCloseAndFreeMRxStateOnFcb(v3, 0, 0);
    if ( InformationEntry < 0 )
    {
      v4 = 2884;
      *(_DWORD *)(*(_QWORD *)(a3 + 8) + 4LL) |= 0x400u;
LABEL_25:
      v12 = 1;
      goto LABEL_26;
    }
  }
  InformationEntry = CscStoreQueryInformationEntryEx(
                       *(_QWORD *)(*(_QWORD *)(a3 + 8) + 56LL),
                       0,
                       (unsigned int)v47,
                       (unsigned int)v45,
                       (__int64)&v35,
                       0,
                       0);
  if ( InformationEntry < 0 )
  {
    v4 = 2905;
    goto LABEL_25;
  }
  if ( (*((_DWORD *)&v3->1 + 39) & 1) != 0 )
  {
    InformationEntry = -1073741738;
    v4 = 2916;
    goto LABEL_25;
  }
  InformationEntry = RxFlushFcbInSystemCache(v3, 0);
  if ( InformationEntry < 0 )
  {
    v4 = 2931;
    goto LABEL_25;
  }
  *((_DWORD *)&v3->1 + 41) &= ~2u;
  InformationEntry = CscStoreQueryInformationEntryEx(
                       *(_QWORD *)(*(_QWORD *)(a3 + 8) + 56LL),
                       0,
                       (unsigned int)v47,
                       (unsigned int)v45,
                       (__int64)&v35,
                       0,
                       0);
  if ( InformationEntry < 0 )
  {
    v4 = 2949;
    goto LABEL_25;
  }
  if ( (v47[0] & 0x80417) != 0 && (v46 & 0x10) == 0 )
  {
    InformationEntry = -1073741560;
    v4 = 2961;
    goto LABEL_25;
  }
  RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(a1 + 80), 2u);
  if ( !RxContext )
  {
    InformationEntry = -1073741670;
    goto LABEL_25;
  }
  if ( *(_BYTE *)(a1 + 32) )
    v20 = *((_QWORD *)&v3->1 + 16);
  else
    v20 = *(_QWORD *)(a1 + 664);
  *(_QWORD *)&RxContext->TrackerHistory[1].AcquireRelease = v20;
  LOWORD(RxContext->RealDevice) = 0;
  RxContext->pFcb = (PMRX_FCB)&v3->Header;
  RxContext->CurrentIrp = *(PIRP *)(a1 + 40);
  memset(v41, 0, 0x98u);
  LOBYTE(v33) = 0;
  RxIterateOnFcbOpens(RxContext, v3, 0, CscCountFobxCallback, v41, v33);
  *(_DWORD *)(*(_QWORD *)(a3 + 8) + 4LL) |= 0x200u;
  *(_DWORD *)(*(_QWORD *)(a3 + 8) + 4LL) &= 0xFFFEFBF4;
  *(_DWORD *)(*(_QWORD *)(a3 + 8) + 4LL) |= 0x8000u;
  if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v3->1 + 15) + 32LL) + 96LL) & 0x20) == 0
    && LODWORD(v41[13]) > 1
    && NodeTypeCode != -5087 )
  {
    v21 = WORD1(RxContext->TrackerHistory[4].FileName);
    if ( (v41[15] & 2) != 0 )
    {
      WORD1(RxContext->TrackerHistory[4].FileName) = v21 | 0x800;
      LOBYTE(v41[18]) |= 1u;
    }
    else
    {
      WORD1(RxContext->TrackerHistory[4].FileName) = v21 | 0x400;
    }
  }
  v41[0] = a2;
  v41[3] = v47;
  v41[1] = a3;
  v41[4] = v45;
  v41[2] = v3;
  LODWORD(v41[12]) = 0;
  *((_DWORD *)&v3->1 + 39) &= ~0x40000u;
  RxSetFcbNameTargetType(v3, 0);
  v36 = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_ddDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v22,
      v23,
      HIDWORD(v41[12]),
      v41[13],
      v41[15],
      WORD1(RxContext->TrackerHistory[4].FileName));
  LOBYTE(v34) = 0;
  v24 = RxIterateOnFcbOpens(RxContext, v3, 0, CscBackPatchFobxCallback, v41, v34);
  v25 = v38;
  InformationEntry = v24;
  if ( v24 >= 0 && !(unsigned __int8)CscBackpatchRemainingBackpatchedFobxs(v38, a3, v41) )
  {
    InformationEntry = -1073741579;
    v4 = 3104;
    goto LABEL_25;
  }
  if ( NodeTypeCode == -5087 )
  {
    if ( InformationEntry < 0 )
      goto LABEL_74;
    goto LABEL_103;
  }
  if ( InformationEntry < 0 )
    goto LABEL_74;
  if ( v41[17] )
  {
    v26 = v41[12];
    if ( (v41[12] & 4) != 0 && !LOBYTE(v3->PagingIoResourceFile) )
      goto LABEL_80;
    InformationEntry = CscBackpatchReAcquireLocks(RxContext);
    if ( InformationEntry < 0 )
    {
      v4 = 3130;
      goto LABEL_74;
    }
  }
  v26 = v41[12];
LABEL_80:
  v28 = v41[16];
  if ( v41[16] && (v26 & 2) == 0 && (v26 & 1) == 0 )
  {
    if ( !(unsigned __int8)CscOKToMarkSparseOnOplockBreak(
                             *(_QWORD *)(*(_QWORD *)(v41[16] + 32LL) + 80LL),
                             *(_QWORD *)(a3 + 8)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          48,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v41[16] + 32LL) + 80LL));
      InformationEntry = -1073741577;
      v4 = 3177;
      *(_QWORD *)(*(_QWORD *)(a3 + 8) + 64LL) = MEMORY[0xFFFFF78000000014];
      *(_QWORD *)(*(_QWORD *)(a3 + 8) + 64LL) += 100000000LL;
      *(_DWORD *)(*(_QWORD *)(a3 + 8) + 4LL) |= 8u;
      goto LABEL_74;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
    LOBYTE(v41[18]) |= 1u;
    v28 = v41[16];
    v26 = v41[12];
  }
  if ( NodeTypeCode == -5087 )
    goto LABEL_103;
  if ( (v41[18] & 1) == 0 )
    goto LABEL_100;
  if ( !v28 )
  {
LABEL_103:
    if ( (v41[18] & 1) != 0 )
    {
      v38 = 0x2000080417LL;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      CscStoreSetInformationEntry(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 56LL), (__int64)&v38, 0, 0, 0, 0, 0);
    }
    if ( (v41[18] & 2) != 0 )
    {
      memset(InitPacket, 0, 0x4Cu);
      LODWORD(v38) = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      *((_DWORD *)&v3->1 + 39) &= ~0x40000u;
      *(_QWORD *)&InitPacket[8] = &v41[11];
      *(_DWORD *)InitPacket = 0;
      *(_QWORD *)&InitPacket[16] = &v38;
      *(_QWORD *)&InitPacket[24] = &v41[5];
      *(_QWORD *)&InitPacket[32] = &v41[6];
      *(_QWORD *)&InitPacket[40] = &v41[7];
      *(_QWORD *)&InitPacket[48] = &v41[8];
      *(_QWORD *)&InitPacket[56] = &v41[9];
      *(_QWORD *)&InitPacket[64] = &v41[10];
      *(_QWORD *)&InitPacket[72] = &v41[10];
      RxFinishFcbInitialization(
        (PMRX_FCB)&v3->Header,
        (RX_FILE_TYPE)((NodeTypeCode != -5087) + 60449),
        (PFCB_INIT_PACKET)InitPacket);
      if ( (int)CscStoreSetInformationEntry(
                  *(_QWORD *)(*(_QWORD *)(v41[1] + 8LL) + 56LL),
                  0,
                  0,
                  0,
                  (__int64)&v41[5],
                  0,
                  0) >= 0 )
      {
        v29 = *(_QWORD *)(a3 + 8);
        v42 = *(_OWORD *)&v41[5];
        v44 = __PAIR64__(HIDWORD(v41[9]), v41[11]);
        v43 = *(_OWORD *)&v41[7];
        CscStoreUpdateLocalBasicInformationEntry(*(_QWORD *)(v29 + 56), 0, &v42, v39);
        if ( v39[0] )
          CscNotifyReportChange(v25, v39[0], 3);
      }
    }
    InformationEntry = -1073741613;
    *(_DWORD *)(*(_QWORD *)(a3 + 8) + 36LL) = *(_DWORD *)(*(_QWORD *)(a3 + 24) + 8LL);
    *(_DWORD *)(*(_QWORD *)(a3 + 8) + 4LL) &= ~0x200u;
    v30 = *(_QWORD *)(a3 + 24);
    if ( *(_DWORD *)(v30 + 8) > *(_DWORD *)(v30 + 12) && v41[17] )
      CscNotifyLViewReconnect(v30, v3, a3);
    goto LABEL_25;
  }
  if ( (v26 & 1) == 0 )
  {
LABEL_100:
    if ( v28 )
      RxUpdateOplockStateOnCreate(v25, v3, 0);
    goto LABEL_103;
  }
  InformationEntry = RxPurgeFcbInSystemCache(v3, 0, 0, 0, 0);
  if ( InformationEntry >= 0 )
  {
    if ( !(unsigned __int8)CscBackpatchRemainingBackpatchedFobxs(v25, a3, v41) )
    {
      InformationEntry = -1073741579;
      v4 = 3218;
      goto LABEL_25;
    }
    v28 = v41[16];
    goto LABEL_100;
  }
LABEL_74:
  *(_DWORD *)(*(_QWORD *)(a3 + 8) + 4LL) |= 0x400u;
  if ( (*(_DWORD *)(*(_QWORD *)(a3 + 8) + 4LL) & 0x10) != 0 )
  {
    v27 = RxCloseAndFreeMRxStateOnFcb(v3, 0, 0);
    if ( v27 >= 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        49,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        (unsigned int)v27);
    }
  }
  if ( v41[16] )
  {
    RxUpdateOplockStateOnCreate(v25, v3, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v3,
        *((_DWORD *)&v3->1 + 41));
  }
  v12 = 1;
  if ( !v4 )
    v4 = 3276;
LABEL_26:
  v17 = *(_QWORD *)(a3 + 8);
  if ( v17 )
    *(_DWORD *)(v17 + 4) &= ~0x8000u;
  if ( v12 )
    RxReleaseFcbPagingInMRx(0, v3);
  if ( RxContext )
  {
    *(_QWORD *)&RxContext->TrackerHistory[1].AcquireRelease = 0;
    RxDereferenceAndDeleteRxContext_Real(RxContext);
  }
  if ( v36 && InformationEntry != -1073741613 )
    RxSetFcbNameTargetType(v3, 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    v18 = *(_QWORD *)(a3 + 8);
    if ( v18 )
      v19 = *(_DWORD *)(v18 + 4);
    else
      v19 = 0;
    WPP_SF_DDd(
      WPP_GLOBAL_Control->AttachedDevice,
      53,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)InformationEntry,
      v4,
      v19);
  }
  v31 = *(_QWORD *)(a3 + 8);
  if ( v31 )
    *(_DWORD *)(v31 + 48) = InformationEntry;
  return (unsigned int)InformationEntry;
}

```

## disassembly

```asm
0x140088890  mov     [rsp-8+arg_18], rbx
0x140088895  push    rbp
0x140088896  push    rsi
0x140088897  push    rdi
0x140088898  push    r12
0x14008889a  push    r13
0x14008889c  push    r14
0x14008889e  push    r15
0x1400888a0  lea     rbp, [rsp-110h]
0x1400888a8  sub     rsp, 210h
0x1400888af  mov     rax, cs:__security_cookie
0x1400888b6  xor     rax, rsp
0x1400888b9  mov     [rbp+140h+var_40], rax
0x1400888c0  mov     r14, [rcx+38h]
0x1400888c4  xor     esi, esi
0x1400888c6  mov     rdi, r8
0x1400888c9  mov     [rsp+240h+var_1F8], rcx
0x1400888ce  mov     r12, rdx
0x1400888d1  mov     r13, rcx
0x1400888d4  xor     edx, edx; Val
0x1400888d6  lea     rcx, [rbp+140h+var_90]; void *
0x1400888dd  lea     r8d, [rsi+50h]; Size
0x1400888e1  mov     r15d, esi
0x1400888e4  call    memset
0x1400888e9  xorps   xmm0, xmm0
0x1400888ec  lea     rcx, [rbp+140h+var_190]; void *
0x1400888f0  xor     eax, eax
0x1400888f2  xor     edx, edx; Val
0x1400888f4  mov     r8d, 98h; Size
0x1400888fa  mov     [rbp+140h+var_98], rax
0x140088901  movups  [rbp+140h+var_C8], xmm0
0x140088905  mov     [rbp+140h+var_D0], rax
0x140088909  movups  [rbp+140h+var_B8], xmm0
0x140088910  movups  [rbp+140h+var_A8], xmm0
0x140088917  movups  [rbp+140h+var_F0], xmm0
0x14008891b  movups  [rbp+140h+var_E0], xmm0
0x14008891f  call    memset
0x140088924  mov     r8, [rdi+8]
0x140088928  mov     [rsp+240h+var_1FF], sil
0x14008892d  movzx   eax, word ptr [r14]
0x140088931  mov     [rsp+240h+var_1FC], ax
0x140088936  mov     rax, cs:CscDeviceObject
0x14008893d  cmp     [r13+50h], rax
0x140088941  lea     rax, WPP_GLOBAL_Control
0x140088948  mov     [rsp+240h+var_1FE], sil
0x14008894d  setnz   bl
0x140088950  mov     [rsp+240h+var_1F0], esi
0x140088954  test    r8, r8
0x140088957  jnz     short loc_14008896B
0x140088959  mov     dl, sil
0x14008895c  mov     ebx, 0C000000Dh
0x140088961  mov     esi, 0AEEh
0x140088966  jmp     loc_140088A81
0x14008896b  mov     rdx, cs:WPP_GLOBAL_Control
0x140088972  cmp     rdx, rax
0x140088975  jz      short loc_1400889A5
0x140088977  mov     eax, [rdx+2Ch]
0x14008897a  test    al, 20h
0x14008897c  jz      short loc_1400889A5
0x14008897e  mov     rax, [rdi+18h]
0x140088982  mov     r9, r14
0x140088985  mov     ecx, [rax+8]
0x140088988  mov     eax, [r8+28h]
0x14008898c  mov     dword ptr [rsp+240h+var_210], ecx
0x140088990  mov     rcx, [rdx+18h]
0x140088994  mov     dword ptr [rsp+240h+var_218], eax
0x140088998  mov     eax, [r8+4]
0x14008899c  mov     dword ptr [rsp+240h+FlushFile], eax
0x1400889a0  call    WPP_SF_qDdd
0x1400889a5  mov     r8b, 1
0x1400889a8  mov     rdx, r14
0x1400889ab  xor     ecx, ecx
0x1400889ad  call    cs:__imp_RxAcquireExclusiveFcbPagingInMRx
0x1400889b4  nop     dword ptr [rax+rax+00h]
0x1400889b9  mov     dl, 1
0x1400889bb  mov     [rsp+240h+var_200], dl
0x1400889bf  test    bl, bl
0x1400889c1  jz      loc_1400892A2
0x1400889c7  mov     r8, [rdi+8]
0x1400889cb  mov     ecx, [r8+4]
0x1400889cf  test    cl, 60h
0x1400889d2  jnz     loc_1400892A2
0x1400889d8  mov     dl, [r12]
0x1400889dc  test    dl, 1
0x1400889df  jz      short loc_1400889FA
0x1400889e1  mov     al, [r12+1]
0x1400889e6  and     al, 14h
0x1400889e8  cmp     al, 14h
0x1400889ea  jz      short loc_1400889FA
0x1400889ec  mov     ebx, 0C00000F4h
0x1400889f1  mov     dl, [rsp+240h+var_200]
0x1400889f5  jmp     loc_1400892A7
0x1400889fa  bt      ecx, 0Ch
0x1400889fe  jnb     short loc_140088A07
0x140088a00  mov     ebx, 0C00000F8h
0x140088a05  jmp     short loc_1400889F1
0x140088a07  test    ecx, 1166Fh
0x140088a0d  jnz     short loc_140088A16
0x140088a0f  mov     ebx, 0C00000F9h
0x140088a14  jmp     short loc_1400889F1
0x140088a16  test    dl, 40h
0x140088a19  jz      short loc_140088A22
0x140088a1b  mov     ebx, 0C00000F5h
0x140088a20  jmp     short loc_1400889F1
0x140088a22  test    dl, 20h
0x140088a25  jnz     short loc_140088A2E
0x140088a27  mov     ebx, 0C00000FAh
0x140088a2c  jmp     short loc_1400889F1
0x140088a2e  bt      ecx, 13h
0x140088a32  jnb     short loc_140088A43
0x140088a34  btr     ecx, 13h
0x140088a38  mov     ebx, 0C0000257h
0x140088a3d  mov     [r8+4], ecx
0x140088a41  jmp     short loc_1400889F1
0x140088a43  test    cl, 10h
0x140088a46  jz      loc_140088B1E
0x140088a4c  xor     r8d, r8d
0x140088a4f  xor     edx, edx
0x140088a51  mov     rcx, r14
0x140088a54  call    cs:__imp_RxCloseAndFreeMRxStateOnFcb
0x140088a5b  nop     dword ptr [rax+rax+00h]
0x140088a60  mov     ebx, eax
0x140088a62  test    eax, eax
0x140088a64  jns     loc_140088B1E
0x140088a6a  mov     rax, [rdi+8]
0x140088a6e  mov     r13d, 400h
0x140088a74  mov     esi, 0B44h
0x140088a79  or      [rax+4], r13d
0x140088a7d  mov     dl, [rsp+240h+var_200]
0x140088a81  mov     rax, [rdi+8]
0x140088a85  test    rax, rax
0x140088a88  jz      short loc_140088A8F
0x140088a8a  btr     dword ptr [rax+4], 0Fh
0x140088a8f  test    dl, dl
0x140088a91  jz      short loc_140088AA4
0x140088a93  mov     rdx, r14
0x140088a96  xor     ecx, ecx
0x140088a98  call    cs:__imp_RxReleaseFcbPagingInMRx
0x140088a9f  nop     dword ptr [rax+rax+00h]
0x140088aa4  test    r15, r15
0x140088aa7  jz      short loc_140088AC3
0x140088aa9  mov     rcx, r15; RxContext
0x140088aac  mov     qword ptr [r15+298h], 0
0x140088ab7  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140088abe  nop     dword ptr [rax+rax+00h]
0x140088ac3  cmp     [rsp+240h+var_1FE], 0
0x140088ac8  jz      short loc_140088AE6
0x140088aca  cmp     ebx, 0C00000D3h
0x140088ad0  jz      short loc_140088AE6
0x140088ad2  mov     edx, 1
0x140088ad7  mov     rcx, r14
0x140088ada  call    cs:__imp_RxSetFcbNameTargetType
0x140088ae1  nop     dword ptr [rax+rax+00h]
0x140088ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x140088aed  lea     rax, WPP_GLOBAL_Control
0x140088af4  cmp     rcx, rax
0x140088af7  jz      loc_1400892D5
0x140088afd  mov     eax, [rcx+2Ch]
0x140088b00  test    al, 20h
0x140088b02  jz      loc_1400892D5
0x140088b08  mov     rax, [rdi+8]
0x140088b0c  test    rax, rax
0x140088b0f  jz      loc_1400892B1
0x140088b15  mov     r8d, [rax+4]
0x140088b19  jmp     loc_1400892B4
0x140088b1e  mov     rcx, [rdi+8]
0x140088b22  lea     rax, [rsp+240h+var_1FF]
0x140088b27  mov     [rsp+240h+var_210], rsi
0x140088b2c  lea     r9, [rbp+140h+var_C8]
0x140088b30  mov     [rsp+240h+var_218], rsi
0x140088b35  lea     r8, [rbp+140h+var_90]
0x140088b3c  xor     edx, edx
0x140088b3e  mov     qword ptr [rsp+240h+FlushFile], rax
0x140088b43  mov     rcx, [rcx+38h]
0x140088b47  call    CscStoreQueryInformationEntryEx
0x140088b4c  mov     ebx, eax
0x140088b4e  test    eax, eax
0x140088b50  jns     short loc_140088B5C
0x140088b52  mov     esi, 0B59h
0x140088b57  jmp     loc_140088A7D
0x140088b5c  mov     eax, [r14+9Ch]
0x140088b63  test    al, 1
0x140088b65  jz      short loc_140088B76
0x140088b67  mov     ebx, 0C0000056h
0x140088b6c  mov     esi, 0B64h
0x140088b71  jmp     loc_140088A7D
0x140088b76  xor     edx, edx; SynchronizeWithLazyWriter
0x140088b78  mov     rcx, r14; Fcb
0x140088b7b  call    cs:__imp_RxFlushFcbInSystemCache
0x140088b82  nop     dword ptr [rax+rax+00h]
0x140088b87  mov     ebx, eax
0x140088b89  test    eax, eax
0x140088b8b  jns     short loc_140088B97
0x140088b8d  mov     esi, 0B73h
0x140088b92  jmp     loc_140088A7D
0x140088b97  and     dword ptr [r14+0A4h], 0FFFFFFFDh
0x140088b9f  lea     rax, [rsp+240h+var_1FF]
0x140088ba4  mov     rcx, [rdi+8]
0x140088ba8  lea     r9, [rbp+140h+var_C8]
0x140088bac  mov     [rsp+240h+var_210], rsi
0x140088bb1  lea     r8, [rbp+140h+var_90]
0x140088bb8  mov     [rsp+240h+var_218], rsi
0x140088bbd  xor     edx, edx
0x140088bbf  mov     qword ptr [rsp+240h+FlushFile], rax
0x140088bc4  mov     rcx, [rcx+38h]
0x140088bc8  call    CscStoreQueryInformationEntryEx
0x140088bcd  mov     ebx, eax
0x140088bcf  test    eax, eax
0x140088bd1  jns     short loc_140088BDD
0x140088bd3  mov     esi, 0B85h
0x140088bd8  jmp     loc_140088A7D
0x140088bdd  test    [rbp+140h+var_90], 80417h
0x140088be7  jz      short loc_140088C01
0x140088be9  test    byte ptr [rbp+140h+var_98], 10h
0x140088bf0  jnz     short loc_140088C01
0x140088bf2  mov     ebx, 0C0000108h
0x140088bf7  mov     esi, 0B91h
0x140088bfc  jmp     loc_140088A7D
0x140088c01  mov     rdx, [r13+50h]; RxDeviceObject
0x140088c05  mov     r8d, 2; InitialContextFlags
0x140088c0b  xor     ecx, ecx; Irp
0x140088c0d  call    cs:__imp_RxCreateRxContext
0x140088c14  nop     dword ptr [rax+rax+00h]
0x140088c19  xor     ebx, ebx
0x140088c1b  mov     r15, rax
0x140088c1e  test    rax, rax
0x140088c21  jnz     short loc_140088C2D
0x140088c23  mov     ebx, 0C000009Ah
0x140088c28  jmp     loc_140088A7D
0x140088c2d  cmp     [r13+20h], bl
0x140088c31  jnz     short loc_140088C3C
0x140088c33  mov     rax, [r13+298h]
0x140088c3a  jmp     short loc_140088C43
0x140088c3c  mov     rax, [r14+80h]
0x140088c43  mov     [r15+298h], rax
0x140088c4a  lea     rcx, [rbp+140h+var_190]; void *
0x140088c4e  mov     [r15+20h], bx
0x140088c53  xor     edx, edx; Val
0x140088c55  mov     [r15+38h], r14
0x140088c59  mov     r8d, 98h; Size
0x140088c5f  mov     rax, [r13+28h]
0x140088c63  mov     [r15+28h], rax
0x140088c67  call    memset
0x140088c6c  lea     rax, [rbp+140h+var_190]
0x140088c70  mov     byte ptr [rsp+240h+var_218], bl
0x140088c74  lea     r9, CscCountFobxCallback
0x140088c7b  mov     qword ptr [rsp+240h+FlushFile], rax
0x140088c80  xor     r8d, r8d
0x140088c83  mov     rdx, r14
0x140088c86  mov     rcx, r15
0x140088c89  call    cs:__imp_RxIterateOnFcbOpens
0x140088c90  nop     dword ptr [rax+rax+00h]
0x140088c95  mov     rax, [rdi+8]
0x140088c99  mov     r13d, 400h
0x140088c9f  bts     dword ptr [rax+4], 9
0x140088ca4  mov     rax, [rdi+8]
0x140088ca8  and     dword ptr [rax+4], 0FFFEFBF4h
0x140088caf  mov     rax, [rdi+8]
0x140088cb3  bts     dword ptr [rax+4], 0Fh
0x140088cb8  mov     rax, [r14+78h]
0x140088cbc  mov     rcx, [rax+20h]
0x140088cc0  mov     eax, [rcx+60h]
0x140088cc3  mov     ecx, 0EC21h
0x140088cc8  test    al, 20h
0x140088cca  jnz     short loc_140088D05
0x140088ccc  cmp     [rbp+140h+var_128], 1
0x140088cd0  jbe     short loc_140088D05
0x140088cd2  cmp     [rsp+240h+var_1FC], cx
0x140088cd7  jz      short loc_140088D05
0x140088cd9  test    byte ptr [rbp+140h+var_118], 2
0x140088cdd  movzx   eax, word ptr [r15+2EAh]
0x140088ce5  jnz     short loc_140088CF5
0x140088ce7  or      ax, r13w
0x140088ceb  mov     [r15+2EAh], ax
0x140088cf3  jmp     short loc_140088D05
0x140088cf5  or      ax, 800h
0x140088cf9  mov     [r15+2EAh], ax
0x140088d01  or      [rbp+140h+var_100], 1
0x140088d05  lea     rax, [rbp+140h+var_90]
0x140088d0c  mov     [rbp+140h+var_190], r12
0x140088d10  mov     [rbp+140h+var_178], rax
0x140088d14  xor     edx, edx
0x140088d16  lea     rax, [rbp+140h+var_C8]
0x140088d1a  mov     [rbp+140h+var_188], rdi
0x140088d1e  mov     [rbp+140h+var_170], rax
0x140088d22  mov     rcx, r14
0x140088d25  mov     [rbp+140h+var_180], r14
0x140088d29  mov     [rbp+140h+var_130], ebx
0x140088d2c  btr     dword ptr [r14+9Ch], 12h
0x140088d35  call    cs:__imp_RxSetFcbNameTargetType
0x140088d3c  nop     dword ptr [rax+rax+00h]
0x140088d41  mov     [rsp+240h+var_1FE], 1
0x140088d46  mov     rcx, cs:WPP_GLOBAL_Control
0x140088d4d  lea     rax, WPP_GLOBAL_Control
0x140088d54  cmp     rcx, rax
0x140088d57  jz      short loc_140088D87
0x140088d59  mov     eax, [rcx+2Ch]
0x140088d5c  test    al, 40h
0x140088d5e  jz      short loc_140088D87
0x140088d60  movzx   eax, word ptr [r15+2EAh]
  ... truncated ...
```
