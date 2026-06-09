# UlSendHttpResponseOrEntityBodyIoctl

- ea: `0x1400f1b08`
- end: `0x1400f2b18`
- name: `UlSendHttpResponseOrEntityBodyIoctl`
- size: `4112`
- prototype: `__int64 __fastcall(PIRP Irp, __int64, unsigned __int8)`
- caller_count: `2`
- callee_count: `41`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009ee50`
- `0x1400f1ae0`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x140019f88`
- `0x14001a794`
- `0x14001f2c0`
- `0x14001f9f4`
- `0x140020290`
- `0x140022610`
- `0x140033830`
- `0x1400354a0`
- `0x140035a50`
- `0x140039340`
- `0x140062bd0`
- `0x1400829a0`
- `0x14008aaf0`
- `0x14009da24`
- `0x1400a69ec`
- `0x1400b1acc`
- `0x1400b379c`
- `0x1400c8dd0`
- `0x1400d3cd0`
- `0x1400e35c0`
- `0x1400e36dc`
- `0x1400e3c84`
- `0x1400ee304`
- `0x1400f1b08`
- `0x1400f677c`
- `0x1400f71f0`
- `0x1400fb744`
- `0x1400fb7ec`
- `0x1400fce98`
- `0x140129028`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c37f8`
- `0x1401cdb74`
- `0x1401cdbcc`
- `0x1401cdfe8`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400f29b0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f29b0`
- `ntoskrnl!IofCompleteRequest` at `0x1400f2abd`
- `ntoskrnl!IofCompleteRequest` at `0x1400f2abd`
- `ntoskrnl!IoIs32bitProcess` at `0x1400f1c54`
- `ntoskrnl!IoIs32bitProcess` at `0x1400f1c54`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f1ecb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f1ecb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23d1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400f1e7e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400f1e7e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400f1ebf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400f1ebf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f1e63`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f1e63`

## pseudocode

```c
__int64 __fastcall UlSendHttpResponseOrEntityBodyIoctl(PIRP Irp, __int64 a2, unsigned __int8 a3)
{
  int v3; // r12d
  PIRP v5; // r13
  __int64 v6; // rsi
  unsigned __int16 v7; // bx
  __int64 v8; // rdx
  int ConsumerAndApiVersion; // edi
  unsigned int v10; // ebx
  int v11; // eax
  _WORD *v12; // r14
  char v13; // r15
  __int64 v14; // rcx
  __int64 *v15; // rdx
  int v16; // r8d
  int v17; // r9d
  bool v18; // di
  const char *v19; // r9
  __int64 v20; // rax
  int v21; // r10d
  __int16 v22; // cx
  char v23; // al
  bool v24; // dl
  char v25; // al
  bool v26; // r12
  bool v27; // r15
  bool v28; // r14
  __int16 v29; // ax
  int v30; // eax
  int v31; // ecx
  __int64 v32; // r15
  unsigned int v33; // eax
  __int64 v34; // r15
  PVOID v35; // rbx
  __int64 v36; // rdx
  char v37; // r13
  __int16 v38; // r14
  int v39; // eax
  __int64 v40; // r8
  int v41; // r9d
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // r9
  __int64 v48; // rdx
  bool v49; // zf
  int v50; // eax
  __int64 v51; // rbx
  unsigned int v52; // eax
  __int64 v53; // rbx
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r14
  int v57; // eax
  __int64 v58; // rcx
  ULONG_PTR v59; // rdx
  int v60; // eax
  __int64 v61; // rbx
  __int64 v62; // rsi
  __int64 v63; // r9
  __int16 v64; // bx
  __int64 v66; // [rsp+20h] [rbp-120h]
  int v67[2]; // [rsp+28h] [rbp-118h]
  int v68; // [rsp+40h] [rbp-100h]
  int v69; // [rsp+48h] [rbp-F8h]
  unsigned int v70; // [rsp+48h] [rbp-F8h]
  int v71; // [rsp+58h] [rbp-E8h]
  int v72; // [rsp+60h] [rbp-E0h]
  int v73; // [rsp+70h] [rbp-D0h]
  int v74; // [rsp+70h] [rbp-D0h]
  int v75; // [rsp+78h] [rbp-C8h]
  int v76; // [rsp+80h] [rbp-C0h]
  int v77; // [rsp+98h] [rbp-A8h]
  char v78; // [rsp+C0h] [rbp-80h]
  char v80; // [rsp+C3h] [rbp-7Dh]
  char v81; // [rsp+C4h] [rbp-7Ch] BYREF
  char v82[3]; // [rsp+C5h] [rbp-7Bh] BYREF
  PVOID P; // [rsp+C8h] [rbp-78h] BYREF
  __int64 v84; // [rsp+D0h] [rbp-70h] BYREF
  char v85; // [rsp+D8h] [rbp-68h] BYREF
  _BYTE v86[11]; // [rsp+D9h] [rbp-67h] BYREF
  int v87; // [rsp+E4h] [rbp-5Ch]
  int v88; // [rsp+E8h] [rbp-58h] BYREF
  PVOID v89; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v90; // [rsp+F8h] [rbp-48h]
  __int64 v91; // [rsp+100h] [rbp-40h] BYREF
  __int64 v92; // [rsp+108h] [rbp-38h] BYREF
  PIRP v93; // [rsp+110h] [rbp-30h]
  __int64 v94[2]; // [rsp+118h] [rbp-28h] BYREF
  __int128 v95; // [rsp+128h] [rbp-18h]
  __int128 v96; // [rsp+138h] [rbp-8h]
  __int64 v97; // [rsp+148h] [rbp+8h]
  __int64 v98; // [rsp+150h] [rbp+10h] BYREF
  __int64 v99[3]; // [rsp+158h] [rbp+18h] BYREF
  __int64 v100[18]; // [rsp+170h] [rbp+30h] BYREF
  _BYTE v101[576]; // [rsp+200h] [rbp+C0h] BYREF
  __int64 v102[18]; // [rsp+440h] [rbp+300h] BYREF
  __int128 v103; // [rsp+4D0h] [rbp+390h] BYREF
  __int64 v104; // [rsp+4E0h] [rbp+3A0h] BYREF
  __int128 v105; // [rsp+4E8h] [rbp+3A8h]
  __int64 v106; // [rsp+4F8h] [rbp+3B8h]
  _BYTE v107[288]; // [rsp+500h] [rbp+3C0h] BYREF

  v3 = a3;
  v93 = Irp;
  v5 = Irp;
  v98 = 0;
  v97 = 0;
  v6 = 0;
  *(_OWORD *)v94 = 0;
  v95 = 0;
  v96 = 0;
  memset(v101, 0, 0x238u);
  v89 = 0;
  v92 = 0;
  v106 = 0;
  v80 = 0;
  v86[3] = 0;
  v105 = 0;
  LODWORD(v104) = 0;
  memset(v107, 0, sizeof(v107));
  P = 0;
  v86[2] = 0;
  memset(v100, 0, sizeof(v100));
  v84 = 0;
  v7 = 0;
  *(_WORD *)&v86[7] = 0;
  v86[1] = 0;
  v88 = 0;
  v87 = 0;
  v103 = 0;
  v82[0] = 0;
  v81 = 0;
  v85 = 0;
  v91 = 0;
  memset(v102, 0, 0x88u);
  v86[4] = 0;
  v78 = 0;
  v90 = 0;
  v86[0] = 0;
  v99[0] = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqD(1033, 71, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, v5, a2, v3);
  IoIs32bitProcess(v5);
  ConsumerAndApiVersion = UlGetConsumerAndApiVersion(*(_QWORD *)(a2 + 48), v8, &v92, &v88);
  if ( ConsumerAndApiVersion >= 0 )
  {
    v10 = v88;
    v11 = UlParseHttpSendHttpResponseIoctls(
            v5,
            *(_QWORD *)(a2 + 32),
            *(_DWORD *)(a2 + 16),
            v88,
            0,
            (__int64)v94,
            v101,
            (__int64)v100,
            (__int64)&v89,
            (char)&v86[3],
            (__int64)v102,
            v73,
            (__int64)&v104,
            (__int64)&P,
            (__int64)&v86[2],
            (__int64)&v84,
            (__int64)&v86[1],
            (__int64)v86,
            (__int64)v99,
            (__int64)&v86[7]);
    v12 = v89;
    ConsumerAndApiVersion = v11;
    if ( v11 < 0 )
      goto LABEL_99;
    if ( v89 )
      v87 = *((unsigned __int16 *)v89 + 4);
    if ( (BYTE8(v96) & 2) != 0 )
    {
      v78 = 0;
      v13 = 0;
    }
    else
    {
      v13 = v96;
      v78 = 1;
      v90 = v96;
      *((_QWORD *)&v103 + 1) = *((_QWORD *)&UlEtwBaseOpaqueIdActivityGuid + 1);
      *(_QWORD *)&v103 = v96;
      v14 = *(_QWORD *)(*(_QWORD *)(v92 + 8) + 328LL);
      if ( (_BYTE)v3 )
      {
        if ( (*(_BYTE *)(v14 + 1760) & 4) == 0 )
          goto LABEL_15;
        v15 = HTTP_EVENT_RECEIVE_BODY_FROM_USERMODE_LEGACY;
        goto LABEL_11;
      }
      if ( (*(_BYTE *)(v14 + 1760) & 4) != 0 )
      {
        v15 = HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE_LEGACY;
LABEL_11:
        McTemplateK0x_EtwWriteTransfer(v14 + 1688, v15, &v103, v96);
      }
    }
LABEL_15:
    ConsumerAndApiVersion = UlGetRequest(v96, v92, &v98);
    if ( ConsumerAndApiVersion < 0 )
    {
      v6 = v98;
      goto LABEL_99;
    }
    v18 = 0;
    v6 = v98;
    if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
    {
      v19 = "entity body";
      if ( !(_BYTE)v3 )
        v19 = "response";
      WPP_SF_siDi(
        (unsigned int)"response",
        1,
        v16,
        (_DWORD)v19,
        v13,
        SBYTE8(v96),
        *(_QWORD *)(*(_QWORD *)(v98 + 24) + 48LL));
    }
    if ( (_BYTE)v3 )
    {
      if ( *(_QWORD *)(v6 + 2488) )
      {
        v88 = 0;
        KeEnterCriticalRegion();
        ExAcquirePushLockSharedEx(*(_QWORD *)(v6 + 24) + 576LL, 0);
        v20 = *(_QWORD *)(v6 + 2512);
        if ( v20 && !*(_DWORD *)(v20 + 136) )
        {
          v18 = *(_DWORD *)(v20 + 256) == 1;
          v88 = v18;
        }
        ExReleasePushLockSharedEx(*(_QWORD *)(v6 + 24) + 576LL, 0);
        KeLeaveCriticalRegion();
        if ( v18 )
          goto LABEL_35;
      }
      else
      {
        LOBYTE(v88) = 0;
      }
      if ( !*(_DWORD *)(v6 + 2212) )
      {
        v21 = DWORD2(v96);
        if ( (BYTE8(v96) & 4) != 0 || (unsigned __int8)UlAutomaticChunkingTransformationNeeded(v6, DWORD2(v96)) )
          goto LABEL_36;
        if ( (unsigned __int8)UxTpIsFastSendPossible(*(_QWORD *)(v6 + 24) + 976LL) )
        {
          v22 = *(_WORD *)&v86[7];
          if ( *(_WORD *)&v86[7] == 1 && !*(_DWORD *)P && (unsigned int)(*((_DWORD *)P + 4) - 1) <= 0xFFFF )
          {
            v21 = DWORD2(v96);
            v23 = 1;
            goto LABEL_37;
          }
        }
      }
LABEL_35:
      v21 = DWORD2(v96);
LABEL_36:
      v22 = *(_WORD *)&v86[7];
      v23 = 0;
LABEL_37:
      v24 = v78 || (v21 & 1) != 0;
      if ( v23 )
      {
        if ( !v22 )
        {
          v25 = 0;
          goto LABEL_76;
        }
LABEL_75:
        v25 = 1;
LABEL_76:
        LOBYTE(v17) = v12 != 0;
        v30 = UlCheckSendResponseFlags(v6, v21, (unsigned __int16)v87, v17, 0, v25);
        ConsumerAndApiVersion = v30;
        if ( v30 < 0 )
        {
          if ( (BYTE8(xmmword_1401A2C90) & 0x40) == 0 )
            goto LABEL_99;
          v36 = 73;
        }
        else
        {
          v30 = UlCheckForZombieConnection(v6, *(_QWORD *)(v6 + 24), DWORD2(v96), v97, v5->RequestorMode);
          ConsumerAndApiVersion = v30;
          if ( v30 >= 0 )
          {
            v31 = DWORD2(v96);
            if ( (WORD4(v96) & 0x100) != 0 )
            {
              v32 = *(_QWORD *)(v6 + 24);
              if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
                WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v32 + 496, 51, 0, 0, 0, 0);
              v33 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v32 + 504)
                                                                                               + 136LL))(
                      *(_QWORD *)(v32 + 496),
                      51,
                      0,
                      0,
                      0,
                      0);
              ConsumerAndApiVersion = v33;
              if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
                WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v33);
              v12 = v89;
              if ( ConsumerAndApiVersion < 0 )
              {
                v80 = 1;
                goto LABEL_99;
              }
              v31 = DWORD2(v96);
            }
            v34 = v84;
            v70 = v10;
            v35 = P;
            ConsumerAndApiVersion = UlFastSendHttpResponse(
                                      (_DWORD)v12,
                                      v97,
                                      (_DWORD)P,
                                      1,
                                      *((_DWORD *)P + 4),
                                      0,
                                      0,
                                      v31,
                                      v6,
                                      v70,
                                      (__int64)v5,
                                      v5->RequestorMode,
                                      v84,
                                      0,
                                      0,
                                      0);
LABEL_100:
            if ( v86[1] )
              ExFreePoolWithTag(*(PVOID *)(v34 + 16), 0);
            if ( v86[2] )
              ExFreePoolWithTag(v35, 0);
            if ( v86[3] )
              ExFreePoolWithTag(v12, 0);
            LOBYTE(v3) = a3;
            v7 = v87;
            goto LABEL_154;
          }
          if ( (BYTE8(xmmword_1401A2C90) & 0x40) == 0 )
            goto LABEL_99;
          v36 = 74;
        }
LABEL_89:
        WPP_SF_d(774, v36, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)v30);
        goto LABEL_99;
      }
      v26 = 0;
      v27 = 0;
      v28 = 0;
      goto LABEL_94;
    }
    v26 = 0;
    if ( DWORD2(v95) )
      v26 = (*(_DWORD *)(v6 + 2200) & 2) != 0;
    v27 = *(_QWORD *)(v6 + 2488)
       && (BYTE8(v96) & 0x10) == 0
       && (BYTE8(v96) & 0x40) == 0
       && ((unsigned __int16)v10 < 2u || !v12[276])
       && ((v29 = v12[4], v29 == 200) || v29 == 206)
       && *(_DWORD *)(v6 + 2676) <= 1u;
    if ( v26 )
      v28 = v26;
    else
      v28 = v27 && (*(_DWORD *)(v6 + 2200) & 4) != 0;
    ConsumerAndApiVersion = UlProcessResponseInfo(
                              v6,
                              v92,
                              (unsigned int)v102,
                              (unsigned int)&v103,
                              (__int64)&v81,
                              (__int64)&v85);
    if ( ConsumerAndApiVersion < 0 )
      goto LABEL_98;
    LOBYTE(v88) = 0;
    if ( !v27 && !v26 && !LOBYTE(v102[0]) )
    {
      v21 = DWORD2(v96);
      if ( (BYTE8(v96) & 4) != 0
        || (BYTE8(v96) & 0x20) != 0
        || (unsigned __int8)UlAutomaticChunkingTransformationNeeded(v6, DWORD2(v96)) )
      {
        goto LABEL_93;
      }
      if ( (unsigned __int8)UxTpIsFastSendPossible(*(_QWORD *)(v6 + 24) + 976LL)
        && *(_WORD *)&v86[7] == 1
        && !*(_DWORD *)P
        && (unsigned int)(*((_DWORD *)P + 4) - 1) <= 0xFFFF
        && !v81
        && !v85 )
      {
        v21 = DWORD2(v96);
        v12 = v89;
        goto LABEL_75;
      }
    }
    v21 = DWORD2(v96);
LABEL_93:
    v24 = 0;
LABEL_94:
    v37 = v86[0];
    LOBYTE(v77) = v81;
    LOBYTE(v76) = v86[0];
    LOBYTE(v75) = v24;
    LOBYTE(v74) = v27;
    LOBYTE(v72) = 0;
    LOBYTE(v71) = v28;
    v38 = *(_WORD *)&v86[7];
    LOBYTE(v69) = v93->RequestorMode;
    LOWORD(v67[0]) = *(_WORD *)&v86[7];
    v39 = UlCaptureHttpResponse(
            v92,
            v10,
            v89,
            v6,
            v93,
            v67[0],
            P,
            HIDWORD(v102[0]),
            v102[16],
            v69,
            v21,
            v71,
            v72,
            v97,
            v74,
            v75,
            v76,
            v99[0],
            v84,
            v77,
            &v91);
    ConsumerAndApiVersion = v39;
    if ( v39 < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
        WPP_SF_d(774, 75, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)v39);
      v5 = v93;
      goto LABEL_98;
    }
    if ( a3 )
    {
      if ( *(_DWORD *)(v6 + 2212) == 1 )
      {
        ConsumerAndApiVersion = 0;
        v5 = v93;
        v93->IoStatus.Information = *(_QWORD *)(v91 + 520);
LABEL_98:
        v12 = v89;
        goto LABEL_99;
      }
      v42 = *(_QWORD *)(v6 + 24);
      if ( v42 )
      {
        v43 = *(_QWORD *)(v42 + 1096);
        if ( (*(_BYTE *)(v43 + 1760) & 4) != 0
          && (!*(_QWORD *)(v43 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v6, v42, 0)) )
        {
          McTemplateK0xx_EtwWriteTransfer(
            *(_QWORD *)(*(_QWORD *)(v6 + 24) + 1096LL) + 1688LL,
            v42,
            v6 + 72,
            *(_QWORD *)(v6 + 56),
            *(_QWORD *)(*(_QWORD *)(v6 + 24) + 48LL));
        }
      }
    }
    else
    {
      v44 = *(_QWORD *)(v6 + 24);
      if ( v44 )
      {
        v45 = *(_QWORD *)(v44 + 1096);
        if ( (*(_BYTE *)(v45 + 1760) & 4) != 0
          && (!*(_QWORD *)(v45 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v6, v44, 0)) )
        {
          v46 = UlVerbToString(*(unsigned int *)(v91 + 156), v91, v40, *(_QWORD *)(v6 + 24));
          McTemplateK0xxhsqhq_EtwWriteTransfer(
            *(_QWORD *)(v47 + 1096) + 1688,
            (unsigned int)HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE,
            v6 + 72,
            *(_QWORD *)(v6 + 56),
            *(_QWORD *)(v47 + 48),
            *(_WORD *)(v48 + 152),
            v46,
            *(_DWORD *)(v48 + 168),
            v94[1],
            SBYTE8(v95));
        }
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
      {
        LOWORD(v68) = v94[1];
        LOWORD(v67[0]) = *(_WORD *)(v91 + 152);
        WPP_SF_iiHLLHL(
          v91,
          76,
          WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids,
          *(_QWORD *)(v6 + 56),
          *(_QWORD *)(*(_QWORD *)(v6 + 24) + 48LL),
          v67[0],
          *(_DWORD *)(v91 + 156),
          *(_DWORD *)(v91 + 168),
          v68,
          DWORD2(v95));
      }
    }
    v49 = v38 == 0;
    v12 = v89;
    LOBYTE(v41) = v89 != 0;
    v50 = UlCheckSendResponseFlags(v6, DWORD2(v96), (unsigned __int16)v87, v41, v37, !v49);
    ConsumerAndApiVersion = v50;
    if ( v50 < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
        WPP_SF_d(774, 77, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)v50);
      v5 = v93;
      goto LABEL_99;
    }
    v5 = v93;
    v30 = UlCheckForZombieConnection(v6, *(_QWORD *)(v6 + 24), DWORD2(v96), v97, v93->RequestorMode);
    ConsumerAndApiVersion = v30;
    if ( v30 < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) == 0 )
        goto LABEL_99;
      v36 = 78;
      goto LABEL_89;
    }
    if ( !v97 || !v78 || (v30 = UlCaptureUserLogData(v97, v6, v91 + 512), ConsumerAndApiVersion = v30, v30 >= 0) )
    {
      if ( (WORD4(v96) & 0x100) == 0 )
        goto LABEL_210;
      v51 = *(_QWORD *)(v6 + 24);
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v51 + 496, 51, 0, 0, 0, 0);
      *(_QWORD *)v67 = 0;
      v66 = 0;
      v52 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)(v51 + 504) + 136LL))(
              *(_QWORD *)(v51 + 496),
              51,
              0,
              0);
      ConsumerAndApiVersion = v52;
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v52);
      v12 = v89;
      if ( ConsumerAndApiVersion < 0 )
      {
        v80 = 1;
      }
      else
      {
LABEL_210:
        if ( (unsigned __int8)UlSetSendIrpCancelRoutine(*(_QWORD *)(v6 + 24), v5) )
        {
          *(_QWORD *)(v91 + 592) = v5;
          v53 = v91;
          v91 = 0;
          if ( a3 )
          {
            *(_BYTE *)(v53 + 51) = v88;
          }
          else if ( v27 )
          {
            *(_BYTE *)(v53 + 50) = UlpSetResponseCacheClassification(v6, v53, *((_QWORD *)&v95 + 1));
          }
          if ( !v26
            || (ConsumerAndApiVersion = UlCacheAndSendResponse(v6, v53, v92, DWORD2(v95), v66, v53, (__int64)v82),
                ConsumerAndApiVersion >= 0)
            && !v82[0] )
          {
            ConsumerAndApiVersion = UlSendHttpResponse(v6, v53, (unsigned int)UlRestartSendHttpResponseIoctl, v53, 0);
          }
          if ( ConsumerAndApiVersion != 259 )
          {
            UlRestartSendHttpResponseIoctl(v53, (unsigned int)ConsumerAndApiVersion, 0);
            v80 = 1;
            ConsumerAndApiVersion = 259;
          }
        }
        else
        {
          ConsumerAndApiVersion = -1073741536;
        }
      }
      goto LABEL_99;
    }
    if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
    {
      v36 = 79;
      goto LABEL_89;
    }
LABEL_99:
    v35 = P;
    v34 = v84;
    goto LABEL_100;
  }
LABEL_154:
  UlFreeResponseInfoParsedElements(v102);
  if ( !v6 )
  {
    v56 = v90;
    goto LABEL_183;
  }
  if ( !(_BYTE)v3 )
  {
    if ( !v82[0] && ConsumerAndApiVersion != -1073741766 )
      UlpFlushHttpPushList(v6, 0);
    if ( !v7 )
    {
      v7 = *(_WORD *)(v6 + 1690);
      v87 = v7;
    }
    if ( v78 )
    {
      if ( (int)(ConsumerAndApiVersion + 0x80000000) >= 0 && ConsumerAndApiVersion != -1073741766 )
      {
        v54 = *(_QWORD *)(v6 + 24);
        if ( v54
          && (v55 = *(_QWORD *)(v54 + 1096), (*(_BYTE *)(v55 + 1760) & 0x20) != 0)
          && (!*(_QWORD *)(v55 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v6, v54, 0)) )
        {
          v56 = v90;
          LOWORD(v66) = v7;
          McTemplateK0xh_EtwWriteTransfer(
            *(_QWORD *)(*(_QWORD *)(v6 + 24) + 1096LL) + 1688LL,
            HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY,
            &v103,
            v90,
            v66);
        }
        else
        {
          v56 = v90;
        }
        v86[4] = 1;
        goto LABEL_176;
      }
LABEL_173:
      v56 = v90;
      if ( !v80 )
        goto LABEL_177;
      goto LABEL_176;
    }
  }
  if ( (int)(ConsumerAndApiVersion + 0x80000000) < 0 || ConsumerAndApiVersion == -1073741766 )
    goto LABEL_173;
  v56 = v90;
LABEL_176:
  UlCloseConnection(*(_QWORD *)(v6 + 24));
LABEL_177:
  v57 = _InterlockedDecrement((volatile signed __int32 *)(v6 + 48));
  if ( UxDebugCheckRefcount && v57 <= -1 )
    UlBugCheckEx(3u, v6 + 48, 0xBu, v57);
  if ( !v57 )
    UlpQueueFreeHttpRequest(v6);
LABEL_183:
  v58 = v91;
  if ( v91 )
  {
    v59 = v91 + 20;
    v60 = _InterlockedDecrement((volatile signed __int32 *)(v91 + 20));
    if ( UxDebugCheckRefcount && v60 <= -1 )
      UlBugCheckEx(3u, v59, 1u, v60);
    if ( !v60 )
    {
      v61 = v58 + 608;
      *(_OWORD *)v99 = 0;
      if ( *(_QWORD *)(v58 + 608) || *(_QWORD *)(v58 + 624) || *(_QWORD *)(v58 + 640) )
        UlBugCheckEx(1u, v58 + 608, (ULONG_PTR)"minio\\http\\sys\\sendresponse.h", 0x453u);
      v62 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v58 + 24) + 24LL) + 1088LL);
      if ( KeGetCurrentIrql() )
      {
        v67[0] = -1;
        LOBYTE(v63) = 1;
        UlThreadPoolEnqueueWorkItem(0, v61, UlDestroyCapturedResponse, v63, v62, *(_QWORD *)v67);
      }
      else
      {
        UxPodAttachThread(v62, v99);
        UlDestroyCapturedResponse(v61);
        UxPodDetachThread(v99);
      }
    }
  }
  if ( v78 && ConsumerAndApiVersion < 0 )
  {
    if ( ConsumerAndApiVersion != -1073741766 )
    {
      v64 = v87;
      if ( !v86[4] )
      {
        v58 = *(_QWORD *)(*(_QWORD *)(v92 + 8) + 328LL);
        if ( (*(_BYTE *)(v58 + 1760) & 0x20) != 0 )
        {
          LOWORD(v66) = v87;
          McTemplateK0xh_EtwWriteTransfer(v58 + 1688, HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY, &v103, v56, v66);
        }
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
      {
        LOWORD(v67[0]) = v64;
        WPP_SF_diH(
          v58,
          80,
          WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids,
          (unsigned int)ConsumerAndApiVersion,
          v56,
          *(_QWORD *)v67);
      }
    }
  }
  else if ( ConsumerAndApiVersion == 259 )
  {
    goto LABEL_205;
  }
  v5->IoStatus.Status = ConsumerAndApiVersion;
  IofCompleteRequest(v5, 0);
LABEL_205:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1033, 81, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)ConsumerAndApiVersion);
  return (unsigned int)ConsumerAndApiVersion;
}

```

## disassembly

```asm
0x1400f1b08  mov     [rsp-8+arg_18], rbx
0x1400f1b0d  push    rbp
0x1400f1b0e  push    rsi
0x1400f1b0f  push    rdi
0x1400f1b10  push    r12
0x1400f1b12  push    r13
0x1400f1b14  push    r14
0x1400f1b16  push    r15
0x1400f1b18  lea     rbp, [rsp-4F0h]
0x1400f1b20  sub     rsp, 630h
0x1400f1b27  mov     rax, cs:__security_cookie
0x1400f1b2e  xor     rax, rsp
0x1400f1b31  mov     [rbp+520h+var_40], rax
0x1400f1b38  xorps   xmm0, xmm0
0x1400f1b3b  movzx   r12d, r8b
0x1400f1b3f  mov     r14, rdx
0x1400f1b42  mov     [rbp+520h+var_550], rcx
0x1400f1b46  mov     r13, rcx
0x1400f1b49  mov     [rbp+520h+var_59E], r12b
0x1400f1b4d  xor     edi, edi
0x1400f1b4f  lea     rcx, [rbp+520h+var_460]; void *
0x1400f1b56  xor     eax, eax
0x1400f1b58  mov     [rbp+520h+var_510], rdi
0x1400f1b5c  xor     edx, edx; Val
0x1400f1b5e  mov     [rbp+520h+var_518], rax
0x1400f1b62  mov     r8d, 238h; Size
0x1400f1b68  mov     esi, edi
0x1400f1b6a  movups  xmmword ptr [rbp+520h+var_548], xmm0
0x1400f1b6e  movups  [rbp+520h+var_538], xmm0
0x1400f1b72  movups  [rbp+520h+var_528], xmm0
0x1400f1b76  call    memset
0x1400f1b7b  xorps   xmm0, xmm0
0x1400f1b7e  mov     [rbp+520h+var_570], rdi
0x1400f1b82  xor     eax, eax
0x1400f1b84  mov     [rbp+520h+var_558], rdi
0x1400f1b88  xor     edx, edx; Val
0x1400f1b8a  mov     [rbp+520h+var_168], rax
0x1400f1b91  mov     r8d, 120h; Size
0x1400f1b97  mov     [rbp+520h+var_59D], dil
0x1400f1b9b  lea     rcx, [rbp+520h+var_160]; void *
0x1400f1ba2  mov     [rbp+520h+var_587+3], dil
0x1400f1ba6  movups  [rbp+520h+var_178], xmm0
0x1400f1bad  mov     dword ptr [rbp+520h+var_180], edi
0x1400f1bb3  call    memset
0x1400f1bb8  xor     edx, edx; Val
0x1400f1bba  mov     [rbp+520h+P], rdi
0x1400f1bbe  mov     r8d, 90h; Size
0x1400f1bc4  mov     [rbp+520h+var_587+2], dil
0x1400f1bc8  lea     rcx, [rbp+520h+var_4F0]; void *
0x1400f1bcc  call    memset
0x1400f1bd1  xorps   xmm0, xmm0
0x1400f1bd4  mov     [rbp+520h+var_590], rdi
0x1400f1bd8  mov     ebx, edi
0x1400f1bda  mov     word ptr [rbp+520h+var_587+7], di
0x1400f1bde  xor     edx, edx; Val
0x1400f1be0  mov     [rbp+520h+var_587+1], dil
0x1400f1be4  mov     r8d, 88h; Size
0x1400f1bea  mov     [rbp+520h+var_578], edi
0x1400f1bed  lea     rcx, [rbp+520h+var_220]; void *
0x1400f1bf4  mov     [rbp+520h+var_57C], ebx
0x1400f1bf7  movups  [rbp+520h+var_190], xmm0
0x1400f1bfe  mov     [rbp+520h+var_59B], dil
0x1400f1c02  mov     [rbp+520h+var_59C], dil
0x1400f1c06  mov     [rbp+520h+var_588], dil
0x1400f1c0a  mov     [rbp+520h+var_560], rdi
0x1400f1c0e  call    memset
0x1400f1c13  mov     [rbp+520h+var_587+4], dil
0x1400f1c17  mov     [rbp+520h+var_5A0], dil
0x1400f1c1b  mov     [rbp+520h+var_568], rdi
0x1400f1c1f  mov     [rbp+520h+var_587], dil
0x1400f1c23  mov     [rbp+520h+var_508], rdi
0x1400f1c27  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400f1c2e  jz      short loc_1400F1C51
0x1400f1c30  lea     edx, [rdi+47h]
0x1400f1c33  mov     [rsp+660h+var_638], r12d
0x1400f1c38  mov     ecx, 409h
0x1400f1c3d  mov     [rsp+660h+var_640], r14
0x1400f1c42  mov     r9, r13
0x1400f1c45  lea     r8, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids
0x1400f1c4c  call    WPP_SF_qqD
0x1400f1c51  mov     rcx, r13; Irp
0x1400f1c54  call    cs:__imp_IoIs32bitProcess
0x1400f1c5b  nop     dword ptr [rax+rax+00h]
0x1400f1c60  mov     rcx, [r14+30h]
0x1400f1c64  lea     r9, [rbp+520h+var_578]
0x1400f1c68  lea     r8, [rbp+520h+var_558]
0x1400f1c6c  mov     r15b, al
0x1400f1c6f  call    UlGetConsumerAndApiVersion
0x1400f1c74  xor     ecx, ecx
0x1400f1c76  mov     edi, eax
0x1400f1c78  test    eax, eax
0x1400f1c7a  js      loc_1400F27F4
0x1400f1c80  mov     ebx, [rbp+520h+var_578]
0x1400f1c83  lea     rax, [rbp+520h+var_587+7]
0x1400f1c87  mov     [rsp+660h+var_5B0], rax; __int64
0x1400f1c8f  mov     r9b, r12b
0x1400f1c92  mov     dl, [r13+40h]
0x1400f1c96  lea     rax, [rbp+520h+var_508]
0x1400f1c9a  mov     [rsp+660h+var_5B8], rax; __int64
0x1400f1ca2  mov     r8b, r15b
0x1400f1ca5  lea     rax, [rbp+520h+var_587]
0x1400f1ca9  mov     [rsp+660h+var_5C0], rax; __int64
0x1400f1cb1  lea     rax, [rbp+520h+var_587+1]
0x1400f1cb5  mov     [rsp+660h+var_5C8], rax; __int64
0x1400f1cbd  lea     rax, [rbp+520h+var_590]
0x1400f1cc1  mov     [rsp+660h+var_5D0], rax; __int64
0x1400f1cc9  lea     rax, [rbp+520h+var_587+2]
0x1400f1ccd  mov     [rsp+660h+var_5D8], rax; __int64
0x1400f1cd5  lea     rax, [rbp+520h+P]
0x1400f1cd9  mov     [rsp+660h+var_5E0], rax; __int64
0x1400f1ce1  lea     rax, [rbp+520h+var_180]
0x1400f1ce8  mov     [rsp+660h+var_5E8], rax; __int64
0x1400f1ced  lea     rax, [rbp+520h+var_220]
0x1400f1cf4  mov     [rsp+660h+var_5F8], rax; __int64
0x1400f1cf9  lea     rax, [rbp+520h+var_587+3]
0x1400f1cfd  mov     qword ptr [rsp+660h+var_600], rax; char
0x1400f1d02  lea     rax, [rbp+520h+var_570]
0x1400f1d06  mov     [rsp+660h+var_608], rax; __int64
0x1400f1d0b  lea     rax, [rbp+520h+var_4F0]
0x1400f1d0f  mov     [rsp+660h+var_610], rax; __int64
0x1400f1d14  lea     rax, [rbp+520h+var_460]
0x1400f1d1b  mov     [rsp+660h+var_618], rax; void *
0x1400f1d20  lea     rax, [rbp+520h+var_548]
0x1400f1d24  mov     [rsp+660h+var_620], rax; __int64
0x1400f1d29  mov     eax, [r14+10h]
0x1400f1d2d  mov     [rsp+660h+var_628], cl; char
0x1400f1d31  mov     rcx, r13; Irp
0x1400f1d34  mov     [rsp+660h+var_630], ebx; int
0x1400f1d38  mov     [rsp+660h+var_638], eax; int
0x1400f1d3c  mov     rax, [r14+20h]
0x1400f1d40  mov     [rsp+660h+var_640], rax; __int64
0x1400f1d45  call    UlParseHttpSendHttpResponseIoctls
0x1400f1d4a  mov     r14, [rbp+520h+var_570]
0x1400f1d4e  mov     edi, eax
0x1400f1d50  test    eax, eax
0x1400f1d52  js      loc_1400F238C
0x1400f1d58  test    r14, r14
0x1400f1d5b  jz      short loc_1400F1D65
0x1400f1d5d  movzx   eax, word ptr [r14+8]
0x1400f1d62  mov     [rbp+520h+var_57C], eax
0x1400f1d65  test    byte ptr [rbp+520h+var_528+8], 2
0x1400f1d69  jnz     short loc_1400F1DDB
0x1400f1d6b  mov     r15, qword ptr [rbp+520h+var_528]
0x1400f1d6f  mov     rax, [rbp+520h+var_558]
0x1400f1d73  mov     [rbp+520h+var_5A0], 1
0x1400f1d77  mov     [rbp+520h+var_568], r15
0x1400f1d7b  movups  xmm0, cs:UlEtwBaseOpaqueIdActivityGuid
0x1400f1d82  movdqu  [rbp+520h+var_190], xmm0
0x1400f1d8a  mov     qword ptr [rbp+520h+var_190], r15
0x1400f1d91  mov     rcx, [rax+8]
0x1400f1d95  mov     rcx, [rcx+148h]
0x1400f1d9c  test    r12b, r12b
0x1400f1d9f  jz      short loc_1400F1DC9
0x1400f1da1  test    byte ptr [rcx+6E0h], 4
0x1400f1da8  jz      short loc_1400F1DE2
0x1400f1daa  lea     rdx, HTTP_EVENT_RECEIVE_BODY_FROM_USERMODE_LEGACY
0x1400f1db1  lea     r8, [rbp+520h+var_190]
0x1400f1db8  mov     r9, r15
0x1400f1dbb  add     rcx, 698h
0x1400f1dc2  call    McTemplateK0x_EtwWriteTransfer
0x1400f1dc7  jmp     short loc_1400F1DE2
0x1400f1dc9  test    byte ptr [rcx+6E0h], 4
0x1400f1dd0  jz      short loc_1400F1DE2
0x1400f1dd2  lea     rdx, HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE_LEGACY
0x1400f1dd9  jmp     short loc_1400F1DB1
0x1400f1ddb  mov     [rbp+520h+var_5A0], sil
0x1400f1ddf  mov     r15, rsi
0x1400f1de2  mov     rdx, [rbp+520h+var_558]
0x1400f1de6  lea     r8, [rbp+520h+var_510]
0x1400f1dea  mov     rcx, qword ptr [rbp+520h+var_528]
0x1400f1dee  call    UlGetRequest
0x1400f1df3  mov     edi, eax
0x1400f1df5  test    eax, eax
0x1400f1df7  js      loc_1400F27EB
0x1400f1dfd  xor     edi, edi
0x1400f1dff  mov     [rbp+520h+var_59F], dil
0x1400f1e03  mov     rsi, [rbp+520h+var_510]
0x1400f1e07  lea     edx, [rdi+1]
0x1400f1e0a  test    byte ptr cs:xmmword_1401A2CA0+2, dl
0x1400f1e10  jz      short loc_1400F1E48
0x1400f1e12  mov     rax, [rsi+18h]
0x1400f1e16  lea     rcx, aResponse; "response"
0x1400f1e1d  test    r12b, r12b
0x1400f1e20  lea     r9, aEntityBody; "entity body"
0x1400f1e27  cmovz   r9, rcx
0x1400f1e2b  mov     rax, [rax+30h]
0x1400f1e2f  mov     qword ptr [rsp+660h+var_630], rax
0x1400f1e34  mov     eax, dword ptr [rbp+520h+var_528+8]
0x1400f1e37  mov     [rsp+660h+var_638], eax
0x1400f1e3b  mov     [rsp+660h+var_640], r15
0x1400f1e40  call    WPP_SF_siDi
0x1400f1e45  lea     edx, [rdi+1]
0x1400f1e48  test    r12b, r12b
0x1400f1e4b  jz      loc_1400F1F8C
0x1400f1e51  cmp     [rsi+9B8h], rdi
0x1400f1e58  jnz     short loc_1400F1E60
0x1400f1e5a  mov     byte ptr [rbp+520h+var_578], dil
0x1400f1e5e  jmp     short loc_1400F1EDE
0x1400f1e60  mov     [rbp+520h+var_578], edi
0x1400f1e63  call    cs:__imp_KeEnterCriticalRegion
0x1400f1e6a  nop     dword ptr [rax+rax+00h]
0x1400f1e6f  mov     rcx, [rsi+18h]
0x1400f1e73  mov     r12d, 240h
0x1400f1e79  add     rcx, r12
0x1400f1e7c  xor     edx, edx
0x1400f1e7e  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400f1e85  nop     dword ptr [rax+rax+00h]
0x1400f1e8a  mov     rax, [rsi+9D0h]
0x1400f1e91  xor     r15d, r15d
0x1400f1e94  test    rax, rax
0x1400f1e97  jz      short loc_1400F1EB6
0x1400f1e99  cmp     [rax+88h], r15d
0x1400f1ea0  jnz     short loc_1400F1EB6
0x1400f1ea2  lea     ecx, [r15+1]
0x1400f1ea6  movzx   edi, dil
0x1400f1eaa  cmp     [rax+100h], ecx
0x1400f1eb0  cmovz   edi, ecx
0x1400f1eb3  mov     [rbp+520h+var_578], edi
0x1400f1eb6  mov     rcx, [rsi+18h]
0x1400f1eba  xor     edx, edx
0x1400f1ebc  add     rcx, r12
0x1400f1ebf  call    cs:__imp_ExReleasePushLockSharedEx
0x1400f1ec6  nop     dword ptr [rax+rax+00h]
0x1400f1ecb  call    cs:__imp_KeLeaveCriticalRegion
0x1400f1ed2  nop     dword ptr [rax+rax+00h]
0x1400f1ed7  test    dil, dil
0x1400f1eda  jnz     short loc_1400F1F43
0x1400f1edc  xor     edi, edi
0x1400f1ede  cmp     [rsi+8A4h], edi
0x1400f1ee4  jnz     short loc_1400F1F45
0x1400f1ee6  mov     r10d, dword ptr [rbp+520h+var_528+8]
0x1400f1eea  test    r10b, 4
0x1400f1eee  jnz     short loc_1400F1F49
0x1400f1ef0  mov     edx, r10d
0x1400f1ef3  mov     rcx, rsi
0x1400f1ef6  call    UlAutomaticChunkingTransformationNeeded
0x1400f1efb  test    al, al
0x1400f1efd  jnz     short loc_1400F1F49
0x1400f1eff  mov     rcx, [rsi+18h]
0x1400f1f03  add     rcx, 3D0h
0x1400f1f0a  call    UxTpIsFastSendPossible
0x1400f1f0f  test    al, al
0x1400f1f11  jz      short loc_1400F1F45
0x1400f1f13  movzx   ecx, word ptr [rbp+520h+var_587+7]
0x1400f1f17  mov     r12d, 1
0x1400f1f1d  cmp     cx, r12w
0x1400f1f21  jnz     short loc_1400F1F45
0x1400f1f23  mov     r8, [rbp+520h+P]
0x1400f1f27  cmp     [r8], edi
0x1400f1f2a  jnz     short loc_1400F1F45
0x1400f1f2c  mov     eax, [r8+10h]
0x1400f1f30  sub     eax, r12d
0x1400f1f33  cmp     eax, 0FFFFh
0x1400f1f38  ja      short loc_1400F1F45
0x1400f1f3a  mov     r10d, dword ptr [rbp+520h+var_528+8]
0x1400f1f3e  mov     al, r12b
0x1400f1f41  jmp     short loc_1400F1F56
0x1400f1f43  xor     edi, edi
0x1400f1f45  mov     r10d, dword ptr [rbp+520h+var_528+8]
0x1400f1f49  movzx   ecx, word ptr [rbp+520h+var_587+7]
0x1400f1f4d  mov     al, dil
0x1400f1f50  mov     r12d, 1
0x1400f1f56  cmp     [rbp+520h+var_5A0], dil
0x1400f1f5a  jnz     short loc_1400F1F61
0x1400f1f5c  test    r12b, r10b
0x1400f1f5f  jz      short loc_1400F1F66
0x1400f1f61  mov     dl, r12b
0x1400f1f64  jmp     short loc_1400F1F69
0x1400f1f66  mov     dl, [rbp+520h+var_59F]
0x1400f1f69  test    al, al
0x1400f1f6b  jz      short loc_1400F1F7E
0x1400f1f6d  test    cx, cx
0x1400f1f70  jnz     loc_1400F20F8
0x1400f1f76  mov     al, dil
0x1400f1f79  jmp     loc_1400F20FB
0x1400f1f7e  mov     r12b, dil
0x1400f1f81  mov     r15b, dil
0x1400f1f84  mov     r14b, dil
0x1400f1f87  jmp     loc_1400F22AE
0x1400f1f8c  mov     r12b, dil
0x1400f1f8f  cmp     dword ptr [rbp+520h+var_538+8], edi
0x1400f1f92  jz      short loc_1400F1FA1
0x1400f1f94  mov     r12d, [rsi+898h]
0x1400f1f9b  shr     r12d, 1
0x1400f1f9e  and     r12b, dl
0x1400f1fa1  cmp     [rsi+9B8h], rdi
0x1400f1fa8  jnz     short loc_1400F1FAF
0x1400f1faa  mov     r15b, dil
0x1400f1fad  jmp     short loc_1400F1FEE
0x1400f1faf  test    byte ptr [rbp+520h+var_528+8], 10h
0x1400f1fb3  jnz     short loc_1400F1FAA
0x1400f1fb5  test    byte ptr [rbp+520h+var_528+8], 40h
0x1400f1fb9  jnz     short loc_1400F1FAA
0x1400f1fbb  cmp     bx, 2
0x1400f1fbf  jb      short loc_1400F1FCB
0x1400f1fc1  cmp     [r14+228h], di
0x1400f1fc9  ja      short loc_1400F1FAA
0x1400f1fcb  movzx   eax, word ptr [r14+8]
0x1400f1fd0  mov     ecx, 0C8h
0x1400f1fd5  cmp     ax, cx
  ... truncated ...
```
