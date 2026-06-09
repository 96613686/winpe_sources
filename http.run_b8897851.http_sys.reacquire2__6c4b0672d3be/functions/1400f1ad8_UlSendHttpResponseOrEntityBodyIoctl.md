# UlSendHttpResponseOrEntityBodyIoctl

- ea: `0x1400f1ad8`
- end: `0x1400f2ae8`
- name: `UlSendHttpResponseOrEntityBodyIoctl`
- size: `4112`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `2`
- callee_count: `41`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14009ee70`
- `0x1400f1ab0`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x140019f88`
- `0x14001a794`
- `0x14001f2c0`
- `0x14001f9f4`
- `0x140020290`
- `0x140022610`
- `0x140033850`
- `0x1400354c0`
- `0x140035a70`
- `0x140039360`
- `0x140062bf0`
- `0x1400829c0`
- `0x14008ab10`
- `0x14009da44`
- `0x1400a6a0c`
- `0x1400b1bac`
- `0x1400b387c`
- `0x1400c8eb0`
- `0x1400d3db0`
- `0x1400e3590`
- `0x1400e36ac`
- `0x1400e3c44`
- `0x1400ee2d4`
- `0x1400f1ad8`
- `0x1400f674c`
- `0x1400f71c0`
- `0x1400fb714`
- `0x1400fb7bc`
- `0x1400fce68`
- `0x140128f38`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c37f8`
- `0x1401cdb74`
- `0x1401cdbcc`
- `0x1401cdfe8`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400f2980`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f2980`
- `ntoskrnl!IofCompleteRequest` at `0x1400f2a8d`
- `ntoskrnl!IofCompleteRequest` at `0x1400f2a8d`
- `ntoskrnl!IoIs32bitProcess` at `0x1400f1c24`
- `ntoskrnl!IoIs32bitProcess` at `0x1400f1c24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f1e9b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f1e9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f2370`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f238a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f2370`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f238a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f23a1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400f1e4e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400f1e4e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400f1e8f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400f1e8f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f1e33`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f1e33`

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
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r14
  ULONG_PTR v59; // rdx
  int v60; // eax
  __int64 v61; // rcx
  ULONG_PTR v62; // rdx
  int v63; // eax
  __int64 v64; // rbx
  __int64 v65; // rsi
  __int64 v66; // r9
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int16 v70; // bx
  __int64 v72; // [rsp+20h] [rbp-120h]
  int v73[2]; // [rsp+28h] [rbp-118h]
  int v74; // [rsp+40h] [rbp-100h]
  int v75; // [rsp+48h] [rbp-F8h]
  unsigned int v76; // [rsp+48h] [rbp-F8h]
  int v77; // [rsp+58h] [rbp-E8h]
  int v78; // [rsp+60h] [rbp-E0h]
  int v79; // [rsp+70h] [rbp-D0h]
  int v80; // [rsp+70h] [rbp-D0h]
  int v81; // [rsp+78h] [rbp-C8h]
  int v82; // [rsp+80h] [rbp-C0h]
  int v83; // [rsp+98h] [rbp-A8h]
  char v84; // [rsp+C0h] [rbp-80h]
  char v86; // [rsp+C3h] [rbp-7Dh]
  char v87; // [rsp+C4h] [rbp-7Ch] BYREF
  char v88[3]; // [rsp+C5h] [rbp-7Bh] BYREF
  PVOID P; // [rsp+C8h] [rbp-78h] BYREF
  __int64 v90; // [rsp+D0h] [rbp-70h] BYREF
  char v91; // [rsp+D8h] [rbp-68h] BYREF
  _BYTE v92[11]; // [rsp+D9h] [rbp-67h] BYREF
  int v93; // [rsp+E4h] [rbp-5Ch]
  int v94; // [rsp+E8h] [rbp-58h] BYREF
  PVOID v95; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v96; // [rsp+F8h] [rbp-48h]
  __int64 v97; // [rsp+100h] [rbp-40h] BYREF
  __int64 v98; // [rsp+108h] [rbp-38h] BYREF
  PIRP v99; // [rsp+110h] [rbp-30h]
  __int64 v100[2]; // [rsp+118h] [rbp-28h] BYREF
  __int128 v101; // [rsp+128h] [rbp-18h]
  __int128 v102; // [rsp+138h] [rbp-8h]
  __int64 v103; // [rsp+148h] [rbp+8h]
  __int64 v104; // [rsp+150h] [rbp+10h] BYREF
  __int64 v105[3]; // [rsp+158h] [rbp+18h] BYREF
  __int64 v106[18]; // [rsp+170h] [rbp+30h] BYREF
  _BYTE v107[576]; // [rsp+200h] [rbp+C0h] BYREF
  __int64 v108[18]; // [rsp+440h] [rbp+300h] BYREF
  __int128 v109; // [rsp+4D0h] [rbp+390h] BYREF
  __int64 v110; // [rsp+4E0h] [rbp+3A0h] BYREF
  __int128 v111; // [rsp+4E8h] [rbp+3A8h]
  __int64 v112; // [rsp+4F8h] [rbp+3B8h]
  _BYTE v113[288]; // [rsp+500h] [rbp+3C0h] BYREF

  v3 = a3;
  v99 = Irp;
  v5 = Irp;
  v104 = 0;
  v103 = 0;
  v6 = 0;
  *(_OWORD *)v100 = 0;
  v101 = 0;
  v102 = 0;
  memset(v107, 0, 0x238u);
  v95 = 0;
  v98 = 0;
  v112 = 0;
  v86 = 0;
  v92[3] = 0;
  v111 = 0;
  LODWORD(v110) = 0;
  memset(v113, 0, sizeof(v113));
  P = 0;
  v92[2] = 0;
  memset(v106, 0, sizeof(v106));
  v90 = 0;
  v7 = 0;
  *(_WORD *)&v92[7] = 0;
  v92[1] = 0;
  v94 = 0;
  v93 = 0;
  v109 = 0;
  v88[0] = 0;
  v87 = 0;
  v91 = 0;
  v97 = 0;
  memset(v108, 0, 0x88u);
  v92[4] = 0;
  v84 = 0;
  v96 = 0;
  v92[0] = 0;
  v105[0] = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqD(1033, 71, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, v5, a2, v3);
  IoIs32bitProcess(v5);
  ConsumerAndApiVersion = UlGetConsumerAndApiVersion(*(_QWORD *)(a2 + 48), v8, &v98, &v94);
  if ( ConsumerAndApiVersion >= 0 )
  {
    v10 = v94;
    v11 = UlParseHttpSendHttpResponseIoctls(
            v5,
            *(_QWORD *)(a2 + 32),
            *(_DWORD *)(a2 + 16),
            v94,
            0,
            (__int64)v100,
            v107,
            (__int64)v106,
            (__int64)&v95,
            (char)&v92[3],
            (__int64)v108,
            v79,
            (__int64)&v110,
            (__int64)&P,
            (__int64)&v92[2],
            (__int64)&v90,
            (__int64)&v92[1],
            (__int64)v92,
            (__int64)v105,
            (__int64)&v92[7]);
    v12 = v95;
    ConsumerAndApiVersion = v11;
    if ( v11 < 0 )
      goto LABEL_99;
    if ( v95 )
      v93 = *((unsigned __int16 *)v95 + 4);
    if ( (BYTE8(v102) & 2) != 0 )
    {
      v84 = 0;
      v13 = 0;
    }
    else
    {
      v13 = v102;
      v84 = 1;
      v96 = v102;
      *((_QWORD *)&v109 + 1) = *((_QWORD *)&UlEtwBaseOpaqueIdActivityGuid + 1);
      *(_QWORD *)&v109 = v102;
      v14 = *(_QWORD *)(*(_QWORD *)(v98 + 8) + 328LL);
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
        McTemplateK0x_EtwWriteTransfer(v14 + 1688, v15, &v109, v102);
      }
    }
LABEL_15:
    ConsumerAndApiVersion = UlGetRequest(v102, v98, &v104);
    if ( ConsumerAndApiVersion < 0 )
    {
      v6 = v104;
      goto LABEL_99;
    }
    v18 = 0;
    v6 = v104;
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
        SBYTE8(v102),
        *(_QWORD *)(*(_QWORD *)(v104 + 24) + 48LL));
    }
    if ( (_BYTE)v3 )
    {
      if ( *(_QWORD *)(v6 + 2488) )
      {
        v94 = 0;
        KeEnterCriticalRegion();
        ExAcquirePushLockSharedEx(*(_QWORD *)(v6 + 24) + 576LL, 0);
        v20 = *(_QWORD *)(v6 + 2512);
        if ( v20 && !*(_DWORD *)(v20 + 136) )
        {
          v18 = *(_DWORD *)(v20 + 256) == 1;
          v94 = v18;
        }
        ExReleasePushLockSharedEx(*(_QWORD *)(v6 + 24) + 576LL, 0);
        KeLeaveCriticalRegion();
        if ( v18 )
          goto LABEL_35;
      }
      else
      {
        LOBYTE(v94) = 0;
      }
      if ( !*(_DWORD *)(v6 + 2212) )
      {
        v21 = DWORD2(v102);
        if ( (BYTE8(v102) & 4) != 0 || (unsigned __int8)UlAutomaticChunkingTransformationNeeded(v6, DWORD2(v102)) )
          goto LABEL_36;
        if ( UxTpIsFastSendPossible(*(_QWORD *)(v6 + 24) + 976LL) )
        {
          v22 = *(_WORD *)&v92[7];
          if ( *(_WORD *)&v92[7] == 1 && !*(_DWORD *)P && (unsigned int)(*((_DWORD *)P + 4) - 1) <= 0xFFFF )
          {
            v21 = DWORD2(v102);
            v23 = 1;
            goto LABEL_37;
          }
        }
      }
LABEL_35:
      v21 = DWORD2(v102);
LABEL_36:
      v22 = *(_WORD *)&v92[7];
      v23 = 0;
LABEL_37:
      v24 = v84 || (v21 & 1) != 0;
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
        v30 = UlCheckSendResponseFlags(v6, v21, (unsigned __int16)v93, v17, 0, v25);
        ConsumerAndApiVersion = v30;
        if ( v30 < 0 )
        {
          if ( (BYTE8(xmmword_1401A2C90) & 0x40) == 0 )
            goto LABEL_99;
          v36 = 73;
        }
        else
        {
          v30 = UlCheckForZombieConnection(v6, *(_QWORD *)(v6 + 24), DWORD2(v102), v103, v5->RequestorMode);
          ConsumerAndApiVersion = v30;
          if ( v30 >= 0 )
          {
            v31 = DWORD2(v102);
            if ( (WORD4(v102) & 0x100) != 0 )
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
              v12 = v95;
              if ( ConsumerAndApiVersion < 0 )
              {
                v86 = 1;
                goto LABEL_99;
              }
              v31 = DWORD2(v102);
            }
            v34 = v90;
            v76 = v10;
            v35 = P;
            ConsumerAndApiVersion = UlFastSendHttpResponse(
                                      (_DWORD)v12,
                                      v103,
                                      (_DWORD)P,
                                      1,
                                      *((_DWORD *)P + 4),
                                      0,
                                      0,
                                      v31,
                                      v6,
                                      v76,
                                      (__int64)v5,
                                      v5->RequestorMode,
                                      v90,
                                      0,
                                      0,
                                      0);
LABEL_100:
            if ( v92[1] )
              ExFreePoolWithTag(*(PVOID *)(v34 + 16), 0);
            if ( v92[2] )
              ExFreePoolWithTag(v35, 0);
            if ( v92[3] )
              ExFreePoolWithTag(v12, 0);
            LOBYTE(v3) = a3;
            v7 = v93;
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
    if ( DWORD2(v101) )
      v26 = (*(_DWORD *)(v6 + 2200) & 2) != 0;
    v27 = *(_QWORD *)(v6 + 2488)
       && (BYTE8(v102) & 0x10) == 0
       && (BYTE8(v102) & 0x40) == 0
       && ((unsigned __int16)v10 < 2u || !v12[276])
       && ((v29 = v12[4], v29 == 200) || v29 == 206)
       && *(_DWORD *)(v6 + 2676) <= 1u;
    if ( v26 )
      v28 = v26;
    else
      v28 = v27 && (*(_DWORD *)(v6 + 2200) & 4) != 0;
    ConsumerAndApiVersion = UlProcessResponseInfo(
                              v6,
                              v98,
                              (unsigned int)v108,
                              (unsigned int)&v109,
                              (__int64)&v87,
                              (__int64)&v91);
    if ( ConsumerAndApiVersion < 0 )
      goto LABEL_98;
    LOBYTE(v94) = 0;
    if ( !v27 && !v26 && !LOBYTE(v108[0]) )
    {
      v21 = DWORD2(v102);
      if ( (BYTE8(v102) & 4) != 0
        || (BYTE8(v102) & 0x20) != 0
        || (unsigned __int8)UlAutomaticChunkingTransformationNeeded(v6, DWORD2(v102)) )
      {
        goto LABEL_93;
      }
      if ( UxTpIsFastSendPossible(*(_QWORD *)(v6 + 24) + 976LL)
        && *(_WORD *)&v92[7] == 1
        && !*(_DWORD *)P
        && (unsigned int)(*((_DWORD *)P + 4) - 1) <= 0xFFFF
        && !v87
        && !v91 )
      {
        v21 = DWORD2(v102);
        v12 = v95;
        goto LABEL_75;
      }
    }
    v21 = DWORD2(v102);
LABEL_93:
    v24 = 0;
LABEL_94:
    v37 = v92[0];
    LOBYTE(v83) = v87;
    LOBYTE(v82) = v92[0];
    LOBYTE(v81) = v24;
    LOBYTE(v80) = v27;
    LOBYTE(v78) = 0;
    LOBYTE(v77) = v28;
    v38 = *(_WORD *)&v92[7];
    LOBYTE(v75) = v99->RequestorMode;
    LOWORD(v73[0]) = *(_WORD *)&v92[7];
    v39 = UlCaptureHttpResponse(
            v98,
            v10,
            v95,
            v6,
            v99,
            v73[0],
            P,
            HIDWORD(v108[0]),
            v108[16],
            v75,
            v21,
            v77,
            v78,
            v103,
            v80,
            v81,
            v82,
            v105[0],
            v90,
            v83,
            &v97);
    ConsumerAndApiVersion = v39;
    if ( v39 < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
        WPP_SF_d(774, 75, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)v39);
      v5 = v99;
      goto LABEL_98;
    }
    if ( a3 )
    {
      if ( *(_DWORD *)(v6 + 2212) == 1 )
      {
        ConsumerAndApiVersion = 0;
        v5 = v99;
        v99->IoStatus.Information = *(_QWORD *)(v97 + 520);
LABEL_98:
        v12 = v95;
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
          v46 = UlVerbToString(*(unsigned int *)(v97 + 156), v97, v40, *(_QWORD *)(v6 + 24));
          McTemplateK0xxhsqhq_EtwWriteTransfer(
            *(_QWORD *)(v47 + 1096) + 1688,
            (unsigned int)HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE,
            v6 + 72,
            *(_QWORD *)(v6 + 56),
            *(_QWORD *)(v47 + 48),
            *(_WORD *)(v48 + 152),
            v46,
            *(_DWORD *)(v48 + 168),
            v100[1],
            SBYTE8(v101));
        }
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
      {
        LOWORD(v74) = v100[1];
        LOWORD(v73[0]) = *(_WORD *)(v97 + 152);
        WPP_SF_iiHLLHL(
          v97,
          76,
          WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids,
          *(_QWORD *)(v6 + 56),
          *(_QWORD *)(*(_QWORD *)(v6 + 24) + 48LL),
          v73[0],
          *(_DWORD *)(v97 + 156),
          *(_DWORD *)(v97 + 168),
          v74,
          DWORD2(v101));
      }
    }
    v49 = v38 == 0;
    v12 = v95;
    LOBYTE(v41) = v95 != 0;
    v50 = UlCheckSendResponseFlags(v6, DWORD2(v102), (unsigned __int16)v93, v41, v37, !v49);
    ConsumerAndApiVersion = v50;
    if ( v50 < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
        WPP_SF_d(774, 77, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)v50);
      v5 = v99;
      goto LABEL_99;
    }
    v5 = v99;
    v30 = UlCheckForZombieConnection(v6, *(_QWORD *)(v6 + 24), DWORD2(v102), v103, v99->RequestorMode);
    ConsumerAndApiVersion = v30;
    if ( v30 < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) == 0 )
        goto LABEL_99;
      v36 = 78;
      goto LABEL_89;
    }
    if ( !v103 || !v84 || (v30 = UlCaptureUserLogData(v103, v6, v97 + 512), ConsumerAndApiVersion = v30, v30 >= 0) )
    {
      if ( (WORD4(v102) & 0x100) == 0 )
        goto LABEL_210;
      v51 = *(_QWORD *)(v6 + 24);
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v51 + 496, 51, 0, 0, 0, 0);
      *(_QWORD *)v73 = 0;
      v72 = 0;
      v52 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)(v51 + 504) + 136LL))(
              *(_QWORD *)(v51 + 496),
              51,
              0,
              0);
      ConsumerAndApiVersion = v52;
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v52);
      v12 = v95;
      if ( ConsumerAndApiVersion < 0 )
      {
        v86 = 1;
      }
      else
      {
LABEL_210:
        if ( (unsigned __int8)UlSetSendIrpCancelRoutine(*(_QWORD *)(v6 + 24), v5) )
        {
          *(_QWORD *)(v97 + 592) = v5;
          v53 = v97;
          v97 = 0;
          if ( a3 )
          {
            *(_BYTE *)(v53 + 51) = v94;
          }
          else if ( v27 )
          {
            *(_BYTE *)(v53 + 50) = UlpSetResponseCacheClassification(v6, v53, *((_QWORD *)&v101 + 1));
          }
          if ( !v26
            || (ConsumerAndApiVersion = UlCacheAndSendResponse(v6, v53, v98, DWORD2(v101), v72, v53, (__int64)v88),
                ConsumerAndApiVersion >= 0)
            && !v88[0] )
          {
            ConsumerAndApiVersion = UlSendHttpResponse(v6, v53, (unsigned int)UlRestartSendHttpResponseIoctl, v53, 0);
          }
          if ( ConsumerAndApiVersion != 259 )
          {
            UlRestartSendHttpResponseIoctl(v53, ConsumerAndApiVersion, 0);
            v86 = 1;
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
    v34 = v90;
    goto LABEL_100;
  }
LABEL_154:
  UlFreeResponseInfoParsedElements(v108);
  if ( !v6 )
  {
    v58 = v96;
    goto LABEL_183;
  }
  if ( !(_BYTE)v3 )
  {
    if ( !v88[0] && ConsumerAndApiVersion != -1073741766 )
      UlpFlushHttpPushList(v6, 0);
    if ( !v7 )
    {
      v7 = *(_WORD *)(v6 + 1690);
      v93 = v7;
    }
    if ( v84 )
    {
      if ( (int)(ConsumerAndApiVersion + 0x80000000) >= 0 && ConsumerAndApiVersion != -1073741766 )
      {
        v56 = *(_QWORD *)(v6 + 24);
        if ( v56
          && (v57 = *(_QWORD *)(v56 + 1096), (*(_BYTE *)(v57 + 1760) & 0x20) != 0)
          && (!*(_QWORD *)(v57 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v6, v56, 0)) )
        {
          v58 = v96;
          LOWORD(v72) = v7;
          McTemplateK0xh_EtwWriteTransfer(
            *(_QWORD *)(*(_QWORD *)(v6 + 24) + 1096LL) + 1688LL,
            HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY,
            &v109,
            v96,
            v72);
        }
        else
        {
          v58 = v96;
        }
        v92[4] = 1;
        goto LABEL_176;
      }
LABEL_173:
      v58 = v96;
      if ( !v86 )
        goto LABEL_177;
      goto LABEL_176;
    }
  }
  if ( (int)(ConsumerAndApiVersion + 0x80000000) < 0 || ConsumerAndApiVersion == -1073741766 )
    goto LABEL_173;
  v58 = v96;
LABEL_176:
  UlCloseConnection(*(_QWORD *)(v6 + 24));
LABEL_177:
  v59 = v6 + 48;
  v60 = _InterlockedDecrement((volatile signed __int32 *)(v6 + 48));
  if ( UxDebugCheckRefcount && v60 <= -1 )
    UlBugCheckEx(3u, v59, 0xBu, v60);
  if ( !v60 )
    UlpQueueFreeHttpRequest(v6, v59, v54, v55);
LABEL_183:
  v61 = v97;
  if ( v97 )
  {
    v62 = v97 + 20;
    v63 = _InterlockedDecrement((volatile signed __int32 *)(v97 + 20));
    if ( UxDebugCheckRefcount && v63 <= -1 )
      UlBugCheckEx(3u, v62, 1u, v63);
    if ( !v63 )
    {
      v64 = v61 + 608;
      *(_OWORD *)v105 = 0;
      if ( *(_QWORD *)(v61 + 608) || *(_QWORD *)(v61 + 624) || *(_QWORD *)(v61 + 640) )
        UlBugCheckEx(1u, v61 + 608, (ULONG_PTR)"minio\\http\\sys\\sendresponse.h", 0x453u);
      v65 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v61 + 24) + 24LL) + 1088LL);
      if ( KeGetCurrentIrql() )
      {
        LOBYTE(v66) = 1;
        UlThreadPoolEnqueueWorkItem(0, v64, UlDestroyCapturedResponse, v66, v65, -1);
      }
      else
      {
        UxPodAttachThread(v65, v105);
        UlDestroyCapturedResponse(v64, v67, v68, v69);
        UxPodDetachThread(v105);
      }
    }
  }
  if ( v84 && ConsumerAndApiVersion < 0 )
  {
    if ( ConsumerAndApiVersion != -1073741766 )
    {
      v70 = v93;
      if ( !v92[4] )
      {
        v61 = *(_QWORD *)(*(_QWORD *)(v98 + 8) + 328LL);
        if ( (*(_BYTE *)(v61 + 1760) & 0x20) != 0 )
        {
          LOWORD(v72) = v93;
          McTemplateK0xh_EtwWriteTransfer(v61 + 1688, HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY, &v109, v58, v72);
        }
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
      {
        LOWORD(v73[0]) = v70;
        WPP_SF_diH(
          v61,
          80,
          WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids,
          (unsigned int)ConsumerAndApiVersion,
          v58,
          *(_QWORD *)v73);
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
0x1400f1ad8  mov     [rsp-8+arg_18], rbx
0x1400f1add  push    rbp
0x1400f1ade  push    rsi
0x1400f1adf  push    rdi
0x1400f1ae0  push    r12
0x1400f1ae2  push    r13
0x1400f1ae4  push    r14
0x1400f1ae6  push    r15
0x1400f1ae8  lea     rbp, [rsp-4F0h]
0x1400f1af0  sub     rsp, 630h
0x1400f1af7  mov     rax, cs:__security_cookie
0x1400f1afe  xor     rax, rsp
0x1400f1b01  mov     [rbp+520h+var_40], rax
0x1400f1b08  xorps   xmm0, xmm0
0x1400f1b0b  movzx   r12d, r8b
0x1400f1b0f  mov     r14, rdx
0x1400f1b12  mov     [rbp+520h+var_550], rcx
0x1400f1b16  mov     r13, rcx
0x1400f1b19  mov     [rbp+520h+var_59E], r12b
0x1400f1b1d  xor     edi, edi
0x1400f1b1f  lea     rcx, [rbp+520h+var_460]; void *
0x1400f1b26  xor     eax, eax
0x1400f1b28  mov     [rbp+520h+var_510], rdi
0x1400f1b2c  xor     edx, edx; Val
0x1400f1b2e  mov     [rbp+520h+var_518], rax
0x1400f1b32  mov     r8d, 238h; Size
0x1400f1b38  mov     esi, edi
0x1400f1b3a  movups  xmmword ptr [rbp+520h+var_548], xmm0
0x1400f1b3e  movups  [rbp+520h+var_538], xmm0
0x1400f1b42  movups  [rbp+520h+var_528], xmm0
0x1400f1b46  call    memset
0x1400f1b4b  xorps   xmm0, xmm0
0x1400f1b4e  mov     [rbp+520h+var_570], rdi
0x1400f1b52  xor     eax, eax
0x1400f1b54  mov     [rbp+520h+var_558], rdi
0x1400f1b58  xor     edx, edx; Val
0x1400f1b5a  mov     [rbp+520h+var_168], rax
0x1400f1b61  mov     r8d, 120h; Size
0x1400f1b67  mov     [rbp+520h+var_59D], dil
0x1400f1b6b  lea     rcx, [rbp+520h+var_160]; void *
0x1400f1b72  mov     [rbp+520h+var_587+3], dil
0x1400f1b76  movups  [rbp+520h+var_178], xmm0
0x1400f1b7d  mov     dword ptr [rbp+520h+var_180], edi
0x1400f1b83  call    memset
0x1400f1b88  xor     edx, edx; Val
0x1400f1b8a  mov     [rbp+520h+P], rdi
0x1400f1b8e  mov     r8d, 90h; Size
0x1400f1b94  mov     [rbp+520h+var_587+2], dil
0x1400f1b98  lea     rcx, [rbp+520h+var_4F0]; void *
0x1400f1b9c  call    memset
0x1400f1ba1  xorps   xmm0, xmm0
0x1400f1ba4  mov     [rbp+520h+var_590], rdi
0x1400f1ba8  mov     ebx, edi
0x1400f1baa  mov     word ptr [rbp+520h+var_587+7], di
0x1400f1bae  xor     edx, edx; Val
0x1400f1bb0  mov     [rbp+520h+var_587+1], dil
0x1400f1bb4  mov     r8d, 88h; Size
0x1400f1bba  mov     [rbp+520h+var_578], edi
0x1400f1bbd  lea     rcx, [rbp+520h+var_220]; void *
0x1400f1bc4  mov     [rbp+520h+var_57C], ebx
0x1400f1bc7  movups  [rbp+520h+var_190], xmm0
0x1400f1bce  mov     [rbp+520h+var_59B], dil
0x1400f1bd2  mov     [rbp+520h+var_59C], dil
0x1400f1bd6  mov     [rbp+520h+var_588], dil
0x1400f1bda  mov     [rbp+520h+var_560], rdi
0x1400f1bde  call    memset
0x1400f1be3  mov     [rbp+520h+var_587+4], dil
0x1400f1be7  mov     [rbp+520h+var_5A0], dil
0x1400f1beb  mov     [rbp+520h+var_568], rdi
0x1400f1bef  mov     [rbp+520h+var_587], dil
0x1400f1bf3  mov     [rbp+520h+var_508], rdi
0x1400f1bf7  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400f1bfe  jz      short loc_1400F1C21
0x1400f1c00  lea     edx, [rdi+47h]
0x1400f1c03  mov     [rsp+660h+var_638], r12d
0x1400f1c08  mov     ecx, 409h
0x1400f1c0d  mov     [rsp+660h+var_640], r14
0x1400f1c12  mov     r9, r13
0x1400f1c15  lea     r8, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids
0x1400f1c1c  call    WPP_SF_qqD
0x1400f1c21  mov     rcx, r13; Irp
0x1400f1c24  call    cs:__imp_IoIs32bitProcess
0x1400f1c2b  nop     dword ptr [rax+rax+00h]
0x1400f1c30  mov     rcx, [r14+30h]
0x1400f1c34  lea     r9, [rbp+520h+var_578]
0x1400f1c38  lea     r8, [rbp+520h+var_558]
0x1400f1c3c  mov     r15b, al
0x1400f1c3f  call    UlGetConsumerAndApiVersion
0x1400f1c44  xor     ecx, ecx
0x1400f1c46  mov     edi, eax
0x1400f1c48  test    eax, eax
0x1400f1c4a  js      loc_1400F27C4
0x1400f1c50  mov     ebx, [rbp+520h+var_578]
0x1400f1c53  lea     rax, [rbp+520h+var_587+7]
0x1400f1c57  mov     [rsp+660h+var_5B0], rax; __int64
0x1400f1c5f  mov     r9b, r12b
0x1400f1c62  mov     dl, [r13+40h]
0x1400f1c66  lea     rax, [rbp+520h+var_508]
0x1400f1c6a  mov     [rsp+660h+var_5B8], rax; __int64
0x1400f1c72  mov     r8b, r15b
0x1400f1c75  lea     rax, [rbp+520h+var_587]
0x1400f1c79  mov     [rsp+660h+var_5C0], rax; __int64
0x1400f1c81  lea     rax, [rbp+520h+var_587+1]
0x1400f1c85  mov     [rsp+660h+var_5C8], rax; __int64
0x1400f1c8d  lea     rax, [rbp+520h+var_590]
0x1400f1c91  mov     [rsp+660h+var_5D0], rax; __int64
0x1400f1c99  lea     rax, [rbp+520h+var_587+2]
0x1400f1c9d  mov     [rsp+660h+var_5D8], rax; __int64
0x1400f1ca5  lea     rax, [rbp+520h+P]
0x1400f1ca9  mov     [rsp+660h+var_5E0], rax; __int64
0x1400f1cb1  lea     rax, [rbp+520h+var_180]
0x1400f1cb8  mov     [rsp+660h+var_5E8], rax; __int64
0x1400f1cbd  lea     rax, [rbp+520h+var_220]
0x1400f1cc4  mov     [rsp+660h+var_5F8], rax; __int64
0x1400f1cc9  lea     rax, [rbp+520h+var_587+3]
0x1400f1ccd  mov     qword ptr [rsp+660h+var_600], rax; char
0x1400f1cd2  lea     rax, [rbp+520h+var_570]
0x1400f1cd6  mov     [rsp+660h+var_608], rax; __int64
0x1400f1cdb  lea     rax, [rbp+520h+var_4F0]
0x1400f1cdf  mov     [rsp+660h+var_610], rax; __int64
0x1400f1ce4  lea     rax, [rbp+520h+var_460]
0x1400f1ceb  mov     [rsp+660h+var_618], rax; void *
0x1400f1cf0  lea     rax, [rbp+520h+var_548]
0x1400f1cf4  mov     [rsp+660h+var_620], rax; __int64
0x1400f1cf9  mov     eax, [r14+10h]
0x1400f1cfd  mov     [rsp+660h+var_628], cl; char
0x1400f1d01  mov     rcx, r13; Irp
0x1400f1d04  mov     [rsp+660h+var_630], ebx; int
0x1400f1d08  mov     [rsp+660h+var_638], eax; int
0x1400f1d0c  mov     rax, [r14+20h]
0x1400f1d10  mov     [rsp+660h+var_640], rax; __int64
0x1400f1d15  call    UlParseHttpSendHttpResponseIoctls
0x1400f1d1a  mov     r14, [rbp+520h+var_570]
0x1400f1d1e  mov     edi, eax
0x1400f1d20  test    eax, eax
0x1400f1d22  js      loc_1400F235C
0x1400f1d28  test    r14, r14
0x1400f1d2b  jz      short loc_1400F1D35
0x1400f1d2d  movzx   eax, word ptr [r14+8]
0x1400f1d32  mov     [rbp+520h+var_57C], eax
0x1400f1d35  test    byte ptr [rbp+520h+var_528+8], 2
0x1400f1d39  jnz     short loc_1400F1DAB
0x1400f1d3b  mov     r15, qword ptr [rbp+520h+var_528]
0x1400f1d3f  mov     rax, [rbp+520h+var_558]
0x1400f1d43  mov     [rbp+520h+var_5A0], 1
0x1400f1d47  mov     [rbp+520h+var_568], r15
0x1400f1d4b  movups  xmm0, cs:UlEtwBaseOpaqueIdActivityGuid
0x1400f1d52  movdqu  [rbp+520h+var_190], xmm0
0x1400f1d5a  mov     qword ptr [rbp+520h+var_190], r15
0x1400f1d61  mov     rcx, [rax+8]
0x1400f1d65  mov     rcx, [rcx+148h]
0x1400f1d6c  test    r12b, r12b
0x1400f1d6f  jz      short loc_1400F1D99
0x1400f1d71  test    byte ptr [rcx+6E0h], 4
0x1400f1d78  jz      short loc_1400F1DB2
0x1400f1d7a  lea     rdx, HTTP_EVENT_RECEIVE_BODY_FROM_USERMODE_LEGACY
0x1400f1d81  lea     r8, [rbp+520h+var_190]
0x1400f1d88  mov     r9, r15
0x1400f1d8b  add     rcx, 698h
0x1400f1d92  call    McTemplateK0x_EtwWriteTransfer
0x1400f1d97  jmp     short loc_1400F1DB2
0x1400f1d99  test    byte ptr [rcx+6E0h], 4
0x1400f1da0  jz      short loc_1400F1DB2
0x1400f1da2  lea     rdx, HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE_LEGACY
0x1400f1da9  jmp     short loc_1400F1D81
0x1400f1dab  mov     [rbp+520h+var_5A0], sil
0x1400f1daf  mov     r15, rsi
0x1400f1db2  mov     rdx, [rbp+520h+var_558]
0x1400f1db6  lea     r8, [rbp+520h+var_510]
0x1400f1dba  mov     rcx, qword ptr [rbp+520h+var_528]
0x1400f1dbe  call    UlGetRequest
0x1400f1dc3  mov     edi, eax
0x1400f1dc5  test    eax, eax
0x1400f1dc7  js      loc_1400F27BB
0x1400f1dcd  xor     edi, edi
0x1400f1dcf  mov     [rbp+520h+var_59F], dil
0x1400f1dd3  mov     rsi, [rbp+520h+var_510]
0x1400f1dd7  lea     edx, [rdi+1]
0x1400f1dda  test    byte ptr cs:xmmword_1401A2CA0+2, dl
0x1400f1de0  jz      short loc_1400F1E18
0x1400f1de2  mov     rax, [rsi+18h]
0x1400f1de6  lea     rcx, aResponse; "response"
0x1400f1ded  test    r12b, r12b
0x1400f1df0  lea     r9, aEntityBody; "entity body"
0x1400f1df7  cmovz   r9, rcx
0x1400f1dfb  mov     rax, [rax+30h]
0x1400f1dff  mov     qword ptr [rsp+660h+var_630], rax
0x1400f1e04  mov     eax, dword ptr [rbp+520h+var_528+8]
0x1400f1e07  mov     [rsp+660h+var_638], eax
0x1400f1e0b  mov     [rsp+660h+var_640], r15
0x1400f1e10  call    WPP_SF_siDi
0x1400f1e15  lea     edx, [rdi+1]
0x1400f1e18  test    r12b, r12b
0x1400f1e1b  jz      loc_1400F1F5C
0x1400f1e21  cmp     [rsi+9B8h], rdi
0x1400f1e28  jnz     short loc_1400F1E30
0x1400f1e2a  mov     byte ptr [rbp+520h+var_578], dil
0x1400f1e2e  jmp     short loc_1400F1EAE
0x1400f1e30  mov     [rbp+520h+var_578], edi
0x1400f1e33  call    cs:__imp_KeEnterCriticalRegion
0x1400f1e3a  nop     dword ptr [rax+rax+00h]
0x1400f1e3f  mov     rcx, [rsi+18h]
0x1400f1e43  mov     r12d, 240h
0x1400f1e49  add     rcx, r12
0x1400f1e4c  xor     edx, edx
0x1400f1e4e  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400f1e55  nop     dword ptr [rax+rax+00h]
0x1400f1e5a  mov     rax, [rsi+9D0h]
0x1400f1e61  xor     r15d, r15d
0x1400f1e64  test    rax, rax
0x1400f1e67  jz      short loc_1400F1E86
0x1400f1e69  cmp     [rax+88h], r15d
0x1400f1e70  jnz     short loc_1400F1E86
0x1400f1e72  lea     ecx, [r15+1]
0x1400f1e76  movzx   edi, dil
0x1400f1e7a  cmp     [rax+100h], ecx
0x1400f1e80  cmovz   edi, ecx
0x1400f1e83  mov     [rbp+520h+var_578], edi
0x1400f1e86  mov     rcx, [rsi+18h]
0x1400f1e8a  xor     edx, edx
0x1400f1e8c  add     rcx, r12
0x1400f1e8f  call    cs:__imp_ExReleasePushLockSharedEx
0x1400f1e96  nop     dword ptr [rax+rax+00h]
0x1400f1e9b  call    cs:__imp_KeLeaveCriticalRegion
0x1400f1ea2  nop     dword ptr [rax+rax+00h]
0x1400f1ea7  test    dil, dil
0x1400f1eaa  jnz     short loc_1400F1F13
0x1400f1eac  xor     edi, edi
0x1400f1eae  cmp     [rsi+8A4h], edi
0x1400f1eb4  jnz     short loc_1400F1F15
0x1400f1eb6  mov     r10d, dword ptr [rbp+520h+var_528+8]
0x1400f1eba  test    r10b, 4
0x1400f1ebe  jnz     short loc_1400F1F19
0x1400f1ec0  mov     edx, r10d
0x1400f1ec3  mov     rcx, rsi
0x1400f1ec6  call    UlAutomaticChunkingTransformationNeeded
0x1400f1ecb  test    al, al
0x1400f1ecd  jnz     short loc_1400F1F19
0x1400f1ecf  mov     rcx, [rsi+18h]
0x1400f1ed3  add     rcx, 3D0h
0x1400f1eda  call    UxTpIsFastSendPossible
0x1400f1edf  test    al, al
0x1400f1ee1  jz      short loc_1400F1F15
0x1400f1ee3  movzx   ecx, word ptr [rbp+520h+var_587+7]
0x1400f1ee7  mov     r12d, 1
0x1400f1eed  cmp     cx, r12w
0x1400f1ef1  jnz     short loc_1400F1F15
0x1400f1ef3  mov     r8, [rbp+520h+P]
0x1400f1ef7  cmp     [r8], edi
0x1400f1efa  jnz     short loc_1400F1F15
0x1400f1efc  mov     eax, [r8+10h]
0x1400f1f00  sub     eax, r12d
0x1400f1f03  cmp     eax, 0FFFFh
0x1400f1f08  ja      short loc_1400F1F15
0x1400f1f0a  mov     r10d, dword ptr [rbp+520h+var_528+8]
0x1400f1f0e  mov     al, r12b
0x1400f1f11  jmp     short loc_1400F1F26
0x1400f1f13  xor     edi, edi
0x1400f1f15  mov     r10d, dword ptr [rbp+520h+var_528+8]
0x1400f1f19  movzx   ecx, word ptr [rbp+520h+var_587+7]
0x1400f1f1d  mov     al, dil
0x1400f1f20  mov     r12d, 1
0x1400f1f26  cmp     [rbp+520h+var_5A0], dil
0x1400f1f2a  jnz     short loc_1400F1F31
0x1400f1f2c  test    r12b, r10b
0x1400f1f2f  jz      short loc_1400F1F36
0x1400f1f31  mov     dl, r12b
0x1400f1f34  jmp     short loc_1400F1F39
0x1400f1f36  mov     dl, [rbp+520h+var_59F]
0x1400f1f39  test    al, al
0x1400f1f3b  jz      short loc_1400F1F4E
0x1400f1f3d  test    cx, cx
0x1400f1f40  jnz     loc_1400F20C8
0x1400f1f46  mov     al, dil
0x1400f1f49  jmp     loc_1400F20CB
0x1400f1f4e  mov     r12b, dil
0x1400f1f51  mov     r15b, dil
0x1400f1f54  mov     r14b, dil
0x1400f1f57  jmp     loc_1400F227E
0x1400f1f5c  mov     r12b, dil
0x1400f1f5f  cmp     dword ptr [rbp+520h+var_538+8], edi
0x1400f1f62  jz      short loc_1400F1F71
0x1400f1f64  mov     r12d, [rsi+898h]
0x1400f1f6b  shr     r12d, 1
0x1400f1f6e  and     r12b, dl
0x1400f1f71  cmp     [rsi+9B8h], rdi
0x1400f1f78  jnz     short loc_1400F1F7F
0x1400f1f7a  mov     r15b, dil
0x1400f1f7d  jmp     short loc_1400F1FBE
0x1400f1f7f  test    byte ptr [rbp+520h+var_528+8], 10h
0x1400f1f83  jnz     short loc_1400F1F7A
0x1400f1f85  test    byte ptr [rbp+520h+var_528+8], 40h
0x1400f1f89  jnz     short loc_1400F1F7A
0x1400f1f8b  cmp     bx, 2
0x1400f1f8f  jb      short loc_1400F1F9B
0x1400f1f91  cmp     [r14+228h], di
0x1400f1f99  ja      short loc_1400F1F7A
0x1400f1f9b  movzx   eax, word ptr [r14+8]
0x1400f1fa0  mov     ecx, 0C8h
0x1400f1fa5  cmp     ax, cx
  ... truncated ...
```
