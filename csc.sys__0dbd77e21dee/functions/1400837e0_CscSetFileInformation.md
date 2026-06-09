# CscSetFileInformation

- ea: `0x1400837e0`
- end: `0x140085611`
- name: `CscSetFileInformation`
- size: `7729`
- prototype: ``
- caller_count: `0`
- callee_count: `51`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x1400017c0`
- `0x140003a00`
- `0x1400084f0`
- `0x14000a634`
- `0x14000e100`
- `0x14000f8b0`
- `0x140010040`
- `0x140010ae8`
- `0x1400119d0`
- `0x1400125d8`
- `0x14001328c`
- `0x14001404c`
- `0x1400151e4`
- `0x140015c44`
- `0x1400169d4`
- `0x1400179f8`
- `0x140018260`
- `0x140018930`
- `0x140018b50`
- `0x1400190ec`
- `0x140019204`
- `0x140019548`
- `0x14001a624`
- `0x14001aa9c`
- `0x14001baf4`
- `0x14001c7e4`
- `0x14001f854`
- `0x140022b68`
- `0x140022fe8`
- `0x1400232b0`
- `0x1400232c4`
- `0x14002de24`
- `0x14002f010`
- `0x14002f0f0`
- `0x14002f440`
- `0x140048e8c`
- `0x14004fca4`
- `0x14004fe58`
- `0x140050874`
- `0x14005096c`
- `0x140050c48`
- `0x140050dc0`
- `0x140051cac`
- `0x14005dad4`
- `0x14007172c`
- `0x1400801c0`
- `0x1400817ec`
- `0x1400837e0`
- `0x140088580`
- `0x14008c2d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400847a7`
- `ntoskrnl!ExAllocatePool2` at `0x1400847a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083c7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084955`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083c7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084955`
- `rdbss!RxRemoveDollarDataSuffix` at `0x140083b0f`
- `rdbss!RxRemoveDollarDataSuffix` at `0x140083b0f`
- `rdbss!RxLastComponentUnicodeString` at `0x140083a98`
- `rdbss!RxLastComponentUnicodeString` at `0x140083b49`
- `rdbss!RxLastComponentUnicodeString` at `0x140084b3f`
- `rdbss!RxLastComponentUnicodeString` at `0x140083a98`
- `rdbss!RxLastComponentUnicodeString` at `0x140083b49`
- `rdbss!RxLastComponentUnicodeString` at `0x140084b3f`
- `rdbss!RxSubjectContextFromRxContext` at `0x140083d82`
- `rdbss!RxSubjectContextFromRxContext` at `0x140083d82`
- `rdbss!RxReleaseFcbPagingInMRx` at `0x140084e41`
- `rdbss!RxReleaseFcbPagingInMRx` at `0x140084e41`
- `rdbss!RxFcbTableNameFromFcb` at `0x1400838c0`
- `rdbss!RxFcbTableNameFromFcb` at `0x1400838c0`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x140084dd2`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x140084dd2`

## pseudocode

```c
__int64 __fastcall CscSetFileInformation(__int64 a1)
{
  __int64 v1; // r14
  __int64 v2; // rsi
  __int64 v3; // r13
  __int64 v5; // rax
  unsigned __int16 *v6; // rdi
  bool v7; // zf
  __int64 v8; // r15
  __int64 v9; // r12
  int v10; // r9d
  __int64 v11; // r9
  int NRNameFromAbsoluteName; // edi
  int v13; // ebx
  char v14; // si
  int v15; // edx
  __int64 v16; // r9
  char v17; // bl
  char v18; // bl
  char v19; // bl
  USHORT v20; // cx
  USHORT v21; // ax
  __int64 v22; // r9
  int v23; // eax
  int v24; // eax
  char v25; // al
  int v26; // eax
  __int64 v27; // rdx
  __int16 v28; // dx
  PWSTR v29; // rax
  __int64 v30; // r9
  int v31; // eax
  char v32; // dl
  __int64 v33; // rbx
  char v34; // cl
  char v35; // dl
  __int64 v36; // r13
  int v37; // r15d
  _DWORD *v38; // rbx
  int v39; // r13d
  __int64 v40; // rdi
  int v41; // r13d
  __int64 v42; // r9
  UNICODE_STRING *v43; // r8
  unsigned int v44; // eax
  int v45; // ecx
  int InformationEntry; // ebx
  int TunneledInfo; // ebx
  int v48; // r14d
  __int64 Pool2; // rax
  int v50; // edx
  __int64 v51; // r15
  int v52; // ecx
  __int64 v53; // rdx
  char v54; // r12
  __int64 v55; // r8
  __int64 v56; // r14
  __int64 v57; // rax
  unsigned int v58; // r13d
  __int64 v59; // r8
  char v60; // dl
  char v61; // al
  __int64 v62; // r14
  char v63; // bl
  char v64; // bl
  unsigned __int16 *v65; // rbx
  unsigned int v66; // edx
  __int64 v67; // rcx
  __int64 v68; // r9
  int v69; // ebx
  UNICODE_STRING *v70; // rdx
  int v71; // eax
  UNICODE_STRING *p_Source; // r8
  int Entry; // eax
  __int64 v74; // rbx
  int v75; // eax
  _WORD *v76; // rbx
  __int64 v77; // r14
  unsigned int v78; // eax
  __int64 v79; // rdx
  __int64 v80; // r8
  int v81; // edx
  __int64 v82; // r14
  int v83; // r12d
  int v84; // ebx
  __int64 v85; // rcx
  __int64 v86; // r12
  char v87; // al
  unsigned int v88; // eax
  bool Only; // r14
  int v90; // eax
  int v91; // edx
  __int64 v92; // rcx
  int v93; // eax
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  int v98; // eax
  unsigned int v99; // eax
  __int64 v100; // r14
  char v102; // [rsp+50h] [rbp-B0h]
  char v103; // [rsp+50h] [rbp-B0h]
  int v104; // [rsp+54h] [rbp-ACh]
  char v105; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v106[7]; // [rsp+59h] [rbp-A7h] BYREF
  __int64 v107; // [rsp+60h] [rbp-A0h] BYREF
  char v108; // [rsp+68h] [rbp-98h]
  __int64 v109; // [rsp+70h] [rbp-90h]
  char v110; // [rsp+78h] [rbp-88h] BYREF
  char v111; // [rsp+79h] [rbp-87h] BYREF
  char v112; // [rsp+7Ah] [rbp-86h]
  int v113; // [rsp+7Ch] [rbp-84h]
  int v114; // [rsp+80h] [rbp-80h] BYREF
  int v115[2]; // [rsp+88h] [rbp-78h]
  __int64 v116; // [rsp+90h] [rbp-70h] BYREF
  __int64 v117; // [rsp+98h] [rbp-68h] BYREF
  UNICODE_STRING Source; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v119; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING SourceString; // [rsp+B8h] [rbp-48h] BYREF
  PVOID P[3]; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING v122; // [rsp+E0h] [rbp-20h] BYREF
  int v123[2]; // [rsp+F0h] [rbp-10h]
  __int64 v124; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v125; // [rsp+100h] [rbp+0h] BYREF
  int v126; // [rsp+108h] [rbp+8h] BYREF
  int v127[4]; // [rsp+110h] [rbp+10h] BYREF
  int v128[2]; // [rsp+120h] [rbp+20h]
  __int64 v129; // [rsp+128h] [rbp+28h]
  __int128 v130; // [rsp+130h] [rbp+30h] BYREF
  __int128 v131; // [rsp+140h] [rbp+40h]
  __int64 v132; // [rsp+158h] [rbp+58h] BYREF
  int v133; // [rsp+160h] [rbp+60h]
  int v134; // [rsp+164h] [rbp+64h] BYREF
  __int128 v135; // [rsp+168h] [rbp+68h] BYREF
  __int128 v136; // [rsp+178h] [rbp+78h] BYREF
  __int128 v137; // [rsp+188h] [rbp+88h] BYREF
  __int64 v138; // [rsp+198h] [rbp+98h] BYREF
  __int128 v139; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v140; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v141; // [rsp+1C0h] [rbp+C0h] BYREF
  _QWORD v142[10]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v143; // [rsp+220h] [rbp+120h] BYREF
  __int128 v144; // [rsp+230h] [rbp+130h]
  __int128 v145; // [rsp+240h] [rbp+140h]
  __int64 v146; // [rsp+250h] [rbp+150h]
  _DWORD v147[20]; // [rsp+260h] [rbp+160h] BYREF
  _OWORD v148[3]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v149; // [rsp+2E0h] [rbp+1E0h]
  _DWORD v150[20]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v2 = *(_QWORD *)(a1 + 72);
  v3 = *(_QWORD *)(a1 + 456);
  v109 = a1;
  *(_QWORD *)v127 = *(_QWORD *)(v1 + 128);
  v5 = *(_QWORD *)(v1 + 120);
  *(_QWORD *)v115 = v1;
  *(_QWORD *)v128 = v2;
  *(_QWORD *)v123 = v3;
  *(_QWORD *)&v136 = *(_QWORD *)(v5 + 32);
  v104 = *(_DWORD *)(a1 + 448);
  v133 = *(_DWORD *)(a1 + 472);
  v146 = 0;
  v134 = 0;
  v143 = 0;
  v138 = 0;
  v144 = 0;
  v108 = 0;
  v145 = 0;
  v110 = 0;
  v112 = 0;
  v114 = 0;
  v122 = 0;
  Source = 0;
  SourceString = 0;
  v140 = 0;
  v135 = 0;
  v137 = 0;
  v129 = RxFcbTableNameFromFcb(v1);
  v130 = 0;
  v6 = (unsigned __int16 *)v129;
  v131 = 0;
  v141 = 0;
  memset(v142, 0, sizeof(v142));
  memset(v150, 0, sizeof(v150));
  v7 = *(_QWORD *)(a1 + 80) == (_QWORD)CscDeviceObject;
  v8 = 0;
  v111 = 0;
  v119 = 0;
  v106[0] = 0;
  v126 = 0;
  v116 = 0;
  v124 = 0;
  v107 = 0;
  v125 = 0;
  v117 = 0;
  v132 = 0;
  v113 = 0;
  v139 = 0;
  v9 = !v7 | (unsigned __int8)(*(_WORD *)v1 != 0xEC21 ? 0 : 0x10);
  CscGetContexts(a1, &v130);
  CscUpdateAndCaptureConnectionStateEx(v1, v2, a1, v10, (__int64)&v141, v10);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v11) = (v9 & 1) != 0 ? 89 : 78;
    WPP_SF_cqD(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, v11, v2, v104);
  }
  if ( (BYTE1(v141) & 0x40) != 0 )
  {
    NRNameFromAbsoluteName = CscDetermineAbortStatus((__int64)&v141);
    v13 = 1547;
LABEL_6:
    v14 = BYTE1(v113);
    goto LABEL_62;
  }
  if ( !(_QWORD)v131 || (*(_DWORD *)(v131 + 24) & 0x809) != 0 )
  {
    v13 = 1557;
    NRNameFromAbsoluteName = -1073741811;
    goto LABEL_6;
  }
  v15 = 4;
  v16 = 92;
  if ( (unsigned int)(v104 - 10) > 1 )
  {
    NRNameFromAbsoluteName = 0;
    v14 = BYTE1(v113);
    v24 = v104;
    v102 = BYTE2(v113);
LABEL_178:
    if ( v24 != 13 )
    {
LABEL_140:
      v37 = -1073741823;
      if ( (v141 & 0x10) != 0 )
      {
        v56 = *(_QWORD *)v123;
        goto LABEL_210;
      }
      v38 = 0;
      v39 = 0;
      if ( (v14 & 4) != 0 && (unsigned int)(v24 - 10) <= 1 )
      {
        v40 = *(_QWORD *)v123;
        v41 = v127[0];
        LODWORD(P[0]) = 0;
        if ( (unsigned int)CscSetInfopGetNRNameFromAbsoluteName(v1, v128[0], v127[0], v123[0], 0, (__int64)P) != -2147483643 )
        {
          NRNameFromAbsoluteName = -1073740768;
          v13 = 2569;
          goto LABEL_61;
        }
        v48 = LODWORD(P[0]) + 24;
        Pool2 = ExAllocatePool2(258, (unsigned int)(LODWORD(P[0]) + 24), 1061124178);
        v38 = (_DWORD *)Pool2;
        if ( !Pool2 )
        {
          NRNameFromAbsoluteName = -1073741670;
          v13 = 2583;
          goto LABEL_61;
        }
        v50 = v128[0];
        v51 = Pool2 + 20;
        v52 = v115[0];
        *(_OWORD *)Pool2 = *(_OWORD *)v40;
        *(_QWORD *)(Pool2 + 16) = *(_QWORD *)(v40 + 16);
        NRNameFromAbsoluteName = CscSetInfopGetNRNameFromAbsoluteName(
                                   v52,
                                   v50,
                                   v41,
                                   v40,
                                   (void *)(Pool2 + 20),
                                   (__int64)P);
        if ( NRNameFromAbsoluteName < 0 )
        {
          v13 = 2604;
          goto LABEL_61;
        }
        v53 = v109;
        v14 |= 2u;
        v38[4] = P[0];
        *(_OWORD *)v127 = 0;
        v39 = *(_DWORD *)(v53 + 472);
        *(_DWORD *)(v53 + 472) = v48;
        *(_QWORD *)(v53 + 456) = v38;
        LOWORD(v127[0]) = *((_WORD *)v38 + 8);
        *(_QWORD *)&v127[2] = v51;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
        {
          goto LABEL_199;
        }
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, v127);
      }
      v53 = v109;
LABEL_199:
      v54 = v9 | 2;
      if ( (v141 & 0x20) != 0 && (BYTE1(v141) & 2) == 0 )
        *(_DWORD *)(v53 + 120) |= 0x10000000u;
      v55 = v136;
      if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v136 + 48) + 352LL) + 208LL) )
      {
        if ( (*(_DWORD *)(v53 + 128) & 2) != 0 )
        {
          NRNameFromAbsoluteName = -1073741536;
        }
        else
        {
          *(_OWORD *)(v53 + 208) = 0;
          *(_OWORD *)(v53 + 224) = 0;
          *(_QWORD *)(v53 + 240) = 0;
          NRNameFromAbsoluteName = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v55 + 48) + 352LL)
                                                                      + 208LL))(v53);
        }
      }
      else
      {
        NRNameFromAbsoluteName = -1073741822;
      }
      v37 = NRNameFromAbsoluteName;
      LOBYTE(v9) = v54
                 ^ (v54
                  ^ (4 * CscCheckRdrStatusTransitionIfNetErr(NRNameFromAbsoluteName, &v141, *(__int64 *)v115)))
                 & 4;
      v56 = *(_QWORD *)v123;
      if ( (v14 & 2) != 0 )
      {
        v57 = v109;
        *(_QWORD *)(v109 + 456) = *(_QWORD *)v123;
        *(_DWORD *)(v57 + 472) = v39;
        ExFreePoolWithTag(v38, 0);
      }
LABEL_210:
      v58 = 0;
      if ( v104 == 10 )
      {
        if ( (v9 & 2) == 0 )
        {
LABEL_284:
          if ( NRNameFromAbsoluteName >= 0 )
          {
LABEL_285:
            v76 = *(_WORD **)v115;
            v77 = v109;
            if ( HIBYTE(v113) )
              CscDisconnectOpens(v109, *(struct _MRX_FCB_ **)v115, (__int64)CscCheckPrefetchOpenPerFobxCallback);
            if ( (v141 & 0x10) != 0 )
            {
              if ( v108 || (v78 = 4, (v14 & 0x40) != 0) )
                v78 = 2;
              CscNotifyReportChange(v77, (unsigned int)(*v76 == 0xEC21) + 1, v78);
              if ( (v14 & 0x40) != 0 )
              {
                v79 = 252;
                v80 = 3;
              }
              else
              {
                v81 = 0;
                v80 = 1;
                if ( !v108 )
                  v80 = 5;
                LOBYTE(v81) = *v76 == 0xEC21;
                v79 = (unsigned int)(v81 + 1);
              }
              CscNotifyReportChange(v77, v79, v80);
              CscNotifyCleanupAllFcbNotifications(v76);
            }
          }
LABEL_297:
          v82 = v109;
LABEL_298:
          v83 = v104;
LABEL_299:
          v13 = 0;
          if ( (v141 & 0x10) != 0 && NRNameFromAbsoluteName >= 0 && v83 != 10 )
            CscNotifyReportChange(v82, v58, 3);
          goto LABEL_61;
        }
        v59 = 1;
        v60 = v102 & 1;
        v103 = v60;
        v61 = v9 & 4;
        if ( v60 )
        {
          if ( v61 )
          {
            v13 = 2701;
            goto LABEL_61;
          }
        }
        else if ( v61 )
        {
          v62 = *(_QWORD *)v115;
          if ( (v9 & 0x80u) != 0LL && (v114 & 1) == 0 && **(_WORD **)v115 != 0xEC21 )
          {
            v63 = 1;
LABEL_226:
            if ( (int)CscStoreFindEntry(&v107, 0, &SourceString, v16) < 0 )
            {
              v13 = 2739;
              goto LABEL_61;
            }
            v14 |= 8u;
            if ( v63 )
            {
              if ( (int)CscCheckTargetAccess(v109, v107, (v9 & 0x10) != 0) < 0 )
              {
                LOBYTE(v9) = v9 | 8;
                NRNameFromAbsoluteName = -1073741790;
              }
              if ( (v14 & 4) != 0 )
              {
                CscStoreDereferenceEntry(&v107);
                v14 &= ~8u;
              }
            }
            v60 = v103;
            v59 = 1;
LABEL_233:
            v64 = v9 & 4;
            if ( (v9 & 0x80u) == 0LL || (v64 || v37 >= 0) && (v9 & 8) == 0 && (v9 & 0x14) != 20 )
            {
              if ( v37 >= 0 && (v14 & 1) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
                }
                v8 = v107;
                p_Source = &Source;
                if ( (v14 & 4) != 0 )
                  p_Source = &v122;
                Entry = CscStoreFindEntry(&v117, v107, p_Source, v16);
                if ( Entry < 0 )
                {
                  NRNameFromAbsoluteName = Entry;
                  v13 = 2954;
                  goto LABEL_62;
                }
                v105 = 1;
                CscStoreSetInformationEntry(v117, 0, 0, 0, 0, &v105, 0);
                CscStoreDereferenceEntry(&v117);
              }
              else
              {
                if ( v64 && (v9 & 0x80u) != 0LL )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                  {
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
                  }
                  NRNameFromAbsoluteName = 0;
                  goto LABEL_285;
                }
                if ( v37 >= 0 && v60 )
                {
                  LOBYTE(v59) = 1;
                  RxAcquireExclusiveFcbPagingInMRx(0, v62, v59);
                  if ( (v141 & 0x20) != 0 )
                  {
                    v74 = *((_QWORD *)&v130 + 1);
                    v105 = 1;
                    CscStoreSetInformationEntry(*(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL), 0, 0, 0, 0, &v105, 0);
                    v75 = CscForceFcbStoreEntryClosed(v109, 0);
                    *(_QWORD *)(v74 + 56) = 0;
                    LOBYTE(v141) = v141 & 0xDF;
                    if ( v75 < 0 )
                      _InterlockedOr8((volatile signed __int8 *)(v62 + 256), 2u);
                  }
                  RxReleaseFcbPagingInMRx(0, v62);
                }
              }
            }
            else
            {
              v136 = 0;
              *(_OWORD *)v127 = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
              }
              if ( v64 && *(_WORD *)v62 == 0xEC21 )
                NRNameFromAbsoluteName = (v114 & 1) != 0 ? -1073741766 : -1073741108;
              if ( (v14 & 0x20) != 0 )
              {
                v105 = 1;
                CscStoreSetInformationEntry(v125, 0, 0, 0, 0, &v105, 0);
                CscStoreDereferenceEntry(&v125);
                v14 &= ~0x20u;
              }
              v65 = (unsigned __int16 *)v129;
              RxLastComponentUnicodeString(v129, 92, &v137);
              v66 = *v65;
              v67 = *((_QWORD *)v65 + 1);
              HIWORD(v127[0]) = v137;
              LOWORD(v127[0]) = v137;
              *((_QWORD *)&v136 + 1) = v67;
              WORD1(v136) = v66 - v137;
              LOWORD(v136) = v66 - v137;
              *(_QWORD *)&v127[2] = v67 + v66 - (unsigned __int64)(unsigned __int16)v137;
              v69 = CscStoreFindEntry(&v132, 0, &v136, v68);
              if ( v69 < 0 )
                goto LABEL_258;
              v69 = CscStoreRenameEntry(
                      *(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL),
                      v132,
                      (unsigned int)v127,
                      0,
                      0,
                      1,
                      0,
                      0);
              if ( v69 >= 0 && v14 < 0 )
              {
                v70 = &Source;
                if ( (v14 & 4) != 0 )
                  v70 = &v122;
                CscCreateTombstone(v107, (int)v70, (__int64)&v150[4], *(_DWORD *)(*(_QWORD *)v128 + 40LL) + 112);
              }
              CscStoreDereferenceEntry(&v132);
              if ( v69 < 0 )
              {
LABEL_258:
                CscTransitionFcbOffline(v62, 0, 1024, 0);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    40,
                    WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
                    (unsigned int)v69);
                }
                NRNameFromAbsoluteName = 0;
              }
              else if ( (v114 & 1) != 0 )
              {
                v71 = CscStoreDeleteEntryPath(v116, v124);
                v114 = 0;
                if ( v71 < 0
                  && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
                }
              }
            }
            goto LABEL_284;
          }
LABEL_221:
          if ( (v14 & 1) == 0 && (v37 >= 0 || (v9 & 0x80u) == 0LL) )
            goto LABEL_233;
          if ( (v14 & 4) != 0 )
            goto LABEL_233;
          v63 = 0;
          if ( v60 )
            goto LABEL_233;
          goto LABEL_226;
        }
        v62 = *(_QWORD *)v115;
        goto LABEL_221;
      }
      v83 = v104;
      if ( (v141 & 0x20) == 0 || (v141 & 0x10) == 0 && v37 < 0 && (v37 != -1073741567 || v104 != 13) )
        goto LABEL_398;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
      if ( v104 == 4 )
        goto LABEL_364;
      if ( v104 != 13 )
      {
        if ( v104 == 19 )
        {
          CscStoreQueryLocalInformationEntry(
            *(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL),
            20,
            8,
            (unsigned int)&v138,
            (__int64)&v134);
          if ( *(_QWORD *)v56 >= v138 )
            goto LABEL_297;
          v84 = 20;
          v104 = 20;
LABEL_365:
          CscStoreQueryInformationEntryEx(*(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL), 0, (unsigned int)v142, 0, 0, 0, 0);
          if ( (v141 & 0x10) != 0 && (v142[0] & 0x20) != 0 )
          {
            NRNameFromAbsoluteName = -1073741108;
            v13 = 3193;
            goto LABEL_61;
          }
          v92 = *(_QWORD *)(v131 + 8);
          if ( !v92 )
            v92 = *(_QWORD *)(v131 + 16);
          LOBYTE(v91) = (v141 & 0x10) != 0;
          v93 = CscStoreSetInformationEntryHandle(v92, v91, v84, v133, v56, (__int64)&v119);
          if ( v93 < 0 )
          {
            if ( (v141 & 0x10) != 0 )
            {
              NRNameFromAbsoluteName = v93;
            }
            else
            {
              if ( (*(_DWORD *)(*(_QWORD *)v115 + 156LL) & 4) == 0 )
                CscHandleStoreError(v109, 0, (unsigned int)v93);
              NRNameFromAbsoluteName = v37;
            }
            v13 = 3239;
            goto LABEL_61;
          }
          v58 = v119;
          if ( (v141 & 0x10) == 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
            }
            if ( v84 == 4 )
            {
              v94 = v142[2];
              if ( (unsigned __int64)(*(_QWORD *)v56 + 1LL) > 1 )
                v94 = *(_QWORD *)v56;
              v142[2] = v94;
              v95 = v142[5];
              if ( (unsigned __int64)(*(_QWORD *)(v56 + 24) + 1LL) > 1 )
                v95 = *(_QWORD *)(v56 + 24);
              v142[5] = v95;
              v96 = v142[4];
              if ( (unsigned __int64)(*(_QWORD *)(v56 + 16) + 1LL) > 1 )
                v96 = *(_QWORD *)(v56 + 16);
              v142[4] = v96;
              v97 = v142[3];
              if ( (unsigned __int64)(*(_QWORD *)(v56 + 8) + 1LL) > 1 )
                v97 = *(_QWORD *)(v56 + 8);
              v142[3] = v97;
              v98 = *(_DWORD *)(v56 + 32);
              if ( v98 )
              {
                LODWORD(v142[8]) = *(_DWORD *)(v56 + 32);
                if ( **(_WORD **)v115 == 0xEC21 )
                  v99 = v98 | 0x10;
                else
                  v99 = v98 & 0xFFFFFFEF;
                LODWORD(v142[8]) = v99;
              }
            }
            else
            {
              v142[7] = *(_QWORD *)(*(_QWORD *)v115 + 32LL);
              v142[6] = *(_QWORD *)(*(_QWORD *)v115 + 24LL);
            }
            CscStoreSetInformationEntry(
              *(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL),
              0,
              0,
              0,
              (__int64)&v142[2],
              0,
              (int *)&v119);
            v58 |= v119;
          }
          goto LABEL_297;
        }
        if ( v104 != 20 )
        {
          v82 = v109;
          v83 = v104;
          if ( (v141 & 0x10) != 0 )
            NRNameFromAbsoluteName = -1073741822;
          goto LABEL_299;
        }
LABEL_364:
        v84 = v104;
        goto LABEL_365;
      }
      v85 = *((_QWORD *)&v130 + 1);
      if ( v37 == -1073741567 )
      {
        if ( (*(_DWORD *)(*((_QWORD *)&v130 + 1) + 4LL) & 0x1000000) == 0 )
        {
          v86 = *(_QWORD *)v115;
          if ( !v126 )
            goto LABEL_324;
          LOBYTE(v141) = v141 | 0x10;
          CscTransitionFcbOffline(*(_QWORD *)v115, 0, 8, 0);
          NRNameFromAbsoluteName = 0;
          goto LABEL_323;
        }
      }
      else if ( v37 >= 0 && (*(_DWORD *)(*((_QWORD *)&v130 + 1) + 4LL) & 0x1000000) != 0 )
      {
        LOBYTE(v15) = 1;
        if ( (int)CscStoreQueryInformationEntryEx(
                    *(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL),
                    v15,
                    0,
                    0,
                    0,
                    (__int64)&v111,
                    0) < 0 )
        {
          v13 = 3377;
          goto LABEL_61;
        }
        v86 = *(_QWORD *)v115;
        if ( !v111 && **(_WORD **)v115 == 0xEC21 )
        {
          v88 = CscEnWalkDirectoryTreeToDelete(*(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL), 0);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0 )
            {
              v85 = *((_QWORD *)&v130 + 1);
              goto LABEL_324;
            }
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, v88);
          }
        }
LABEL_323:
        v85 = *((_QWORD *)&v130 + 1);
LABEL_324:
        v87 = (*(_BYTE *)v56 & 1) << 6;
        if ( (v141 & 0x10) != 0 )
        {
          if ( !v87 )
          {
            if ( v85 )
            {
              v90 = *(_DWORD *)(v86 + 156);
              v82 = v109;
              v83 = v104;
              if ( (v90 & 1) != 0 )
                *(_DWORD *)(v85 + 40) = 0;
              goto LABEL_299;
            }
            goto LABEL_297;
          }
          v106[0] = 1;
          if ( *(_WORD *)v86 == 0xEC21 )
          {
            CscStoreQueryInformationEntryEx(*(_QWORD *)(v85 + 56), 1, (unsigned int)v142, 0, 0, (__int64)v106, 0);
            if ( (v141 & 0x10) != 0 && (v142[0] & 0x4000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
              }
              NRNameFromAbsoluteName = -1073741637;
              v13 = 3439;
LABEL_333:
              v8 = v107;
              goto LABEL_62;
            }
            NRNameFromAbsoluteName = CscIsDirectoryRenameDeleteAllowed(v109, v142);
            if ( NRNameFromAbsoluteName < 0 )
            {
              v13 = 3448;
              goto LABEL_61;
            }
          }
          Only = CscEnDbIsCacheReadOnly(*(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL));
          if ( (unsigned __int8)CscStoreIsEntryReadOnly() || Only )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              LOBYTE(v16) = Only ? 89 : 78;
              WPP_SF_c(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, v16);
            }
            v13 = 3471;
            NRNameFromAbsoluteName = Only ? -1073741662 : -1073741535;
            goto LABEL_333;
          }
          if ( !v106[0] )
          {
            NRNameFromAbsoluteName = -1073741567;
            v13 = 3481;
            goto LABEL_61;
          }
        }
        else if ( !v87 )
        {
          goto LABEL_297;
        }
        if ( *(_WORD *)v86 == 0xEC21 )
        {
          if ( v37 >= 0 )
          {
            v82 = v109;
            LOBYTE(v16) = 1;
            CscNotifyFullChangeDirectory(v109, 0, 0, v16);
            goto LABEL_298;
          }
          goto LABEL_297;
        }
        v83 = v104;
LABEL_398:
        v82 = v109;
        goto LABEL_299;
      }
      v86 = *(_QWORD *)v115;
      goto LABEL_324;
    }
    if ( (v141 & 0x20) == 0 )
      goto LABEL_139;
    if ( *(_WORD *)v1 != 0xEC21 )
      goto LABEL_139;
    if ( (v141 & 0x10) != 0 )
      goto LABEL_139;
    LOBYTE(v9) = ((*(_BYTE *)v3 & 1) << 6) | v9;
    if ( (*(_BYTE *)v3 & 1) == 0 )
      goto LABEL_139;
    memset(v147, 0, sizeof(v147));
    NRNameFromAbsoluteName = CscStoreQueryInformationEntryEx(
                               *(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL),
                               0,
                               (unsigned int)v147,
                               0,
                               0,
                               (__int64)v106,
                               (__int64)&v126);
    if ( NRNameFromAbsoluteName < 0 )
    {
      v13 = 2492;
      goto LABEL_62;
    }
    if ( v106[0] || (v147[0] & 0x800000) != 0 )
    {
LABEL_139:
      v24 = v104;
      goto LABEL_140;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
    NRNameFromAbsoluteName = -1073741567;
    v13 = 2524;
    goto LABEL_62;
  }
  if ( (unsigned int)(*(_DWORD *)(v3 + 16) - 2) > 0xFFFC )
  {
    NRNameFromAbsoluteName = -1073741811;
    v13 = 1575;
    goto LABEL_6;
  }
  v14 = BYTE1(v113) & 0xFB | (*(_WORD *)(v3 + 20) != 92 ? 0 : 4);
  v122.MaximumLength = *(_WORD *)(v3 + 16);
  v122.Length = v122.MaximumLength;
  v122.Buffer = (PWSTR)(v3 + 20);
  if ( (v14 & 4) != 0 )
  {
    RxLastComponentUnicodeString(&v122, 92, &v137);
    v17 = BYTE2(v113);
    Source.MaximumLength = v137;
    Source.Length = v137;
    SourceString.Buffer = v122.Buffer;
    Source.Buffer = (PWSTR)((char *)v122.Buffer + v122.Length - (unsigned __int64)(unsigned __int16)v137);
    SourceString.MaximumLength = v122.Length - v137;
    SourceString.Length = v122.Length - v137;
    v102 = BYTE2(v113);
  }
  else
  {
    v18 = BYTE2(v113) & 0xFE | (*(_WORD *)(v3 + 20) == 58);
    v102 = v18;
    if ( *(_WORD *)(v3 + 20) == 58 )
    {
      RxRemoveDollarDataSuffix(&v122, &v110, 1, 92);
      if ( v110 )
      {
        v18 &= ~1u;
        v102 = v18;
      }
    }
    v19 = v18 & 1;
    if ( v19 )
    {
      v20 = 0;
    }
    else
    {
      RxLastComponentUnicodeString(v6, 92, &v137);
      Source.MaximumLength = v137;
      v20 = v137;
      Source.Length = v137;
      Source.Buffer = (PWSTR)(*((_QWORD *)v6 + 1) + *v6 - (unsigned __int64)(unsigned __int16)v137);
    }
    Source.Length = v20;
    SourceString.Buffer = (PWSTR)*((_QWORD *)v6 + 1);
    v21 = *v6 - v20;
    Source = v122;
    SourceString.MaximumLength = v21;
    SourceString.Length = v21;
    if ( (v141 & 0x10) != 0 && v19 )
    {
      NRNameFromAbsoluteName = -1073741108;
      v13 = 1726;
      goto LABEL_62;
    }
    v17 = v102;
  }
  *(_OWORD *)P = 0;
  NRNameFromAbsoluteName = CscPathUtilsAllocFullPathFromParentPathAndLeafFile(
                             (PUNICODE_STRING)P,
                             &SourceString,
                             &Source);
  if ( NRNameFromAbsoluteName < 0 )
  {
    v13 = 1742;
    goto LABEL_62;
  }
  NRNameFromAbsoluteName = CscExclusionListCheckRenameAndHardLinkCreate(v1, v129, P);
  if ( NRNameFromAbsoluteName == -1073739772 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, P);
    v23 = CscDclNotifyExcludedFileType(1, v129, P, v22);
    if ( v23 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
        (unsigned int)v23);
    }
  }
  ExFreePoolWithTag(P[1], 0);
  if ( NRNameFromAbsoluteName < 0 )
  {
    v13 = 1767;
    goto LABEL_62;
  }
  v24 = v104;
  if ( v104 != 10 )
    goto LABEL_178;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      LOBYTE(v16) = *(_BYTE *)v3 != 0 ? 89 : 78;
      WPP_SF_cZ(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        (unsigned int)WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
        v16,
        (__int64)&v122);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_ZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        (unsigned int)WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
        (unsigned int)&SourceString,
        (__int64)&Source);
  }
  if ( (v141 & 0x20) == 0 )
  {
    if ( (v17 & 1) == 0 )
    {
      if ( (v14 & 4) != 0 )
        goto LABEL_149;
      if ( (int)CscStoreFindEntry(&v107, 0, &SourceString, v16) >= 0 )
      {
        v14 |= 8u;
LABEL_149:
        memset(v147, 0, sizeof(v147));
        v36 = v107;
        v43 = &Source;
        v149 = 0;
        v148[0] = 0;
        if ( (v14 & 4) != 0 )
          v43 = &v122;
        memset(&v148[1], 0, 32);
        v44 = CscStoreFindEntry(&v117, v107, v43, v42);
        if ( (unsigned __int8)CscStoreIsAttached(v44) )
        {
          if ( v45 < 0 )
          {
            if ( v45 != -1073741809 )
            {
              if ( v45 == -1073741772 )
              {
LABEL_170:
                if ( (v14 & 4) == 0 )
                  goto LABEL_134;
                P[0] = 0;
                if ( (int)CscStoreFindEntry(P, 0, &SourceString, v16) < 0 )
                  goto LABEL_134;
                TunneledInfo = CscStoreGetTunneledInfo(P[0], &Source, v147);
                CscStoreDereferenceEntry(P);
                if ( TunneledInfo < 0 )
                  goto LABEL_134;
LABEL_173:
                NRNameFromAbsoluteName = CscSetInfopCanFlowRenameToServer(v109, &v141, &SourceString, &Source, 0, v147);
                if ( NRNameFromAbsoluteName < 0 )
                {
                  v13 = 2451;
                  goto LABEL_61;
                }
                goto LABEL_134;
              }
              if ( v45 != -1073741766 )
              {
                NRNameFromAbsoluteName = v45;
                v13 = 2336;
                goto LABEL_61;
              }
            }
LABEL_169:
            if ( v45 != -1073741772 )
              goto LABEL_134;
            goto LABEL_170;
          }
        }
        else if ( v45 < 0 )
        {
          goto LABEL_169;
        }
        InformationEntry = CscStoreQueryInformationEntryEx(v117, 0, (unsigned int)v147, (unsigned int)v148, 0, 0, 0);
        CscStoreDereferenceEntry(&v117);
        if ( InformationEntry < 0 )
        {
          v14 |= 1u;
          goto LABEL_134;
        }
        if ( (((unsigned __int8)v9 >> 4) & 1) == ((v149 & 0x10) != 0) )
        {
          if ( (v149 & 0x10) == 0 )
          {
            if ( (v147[0] & 0x20) == 0 && !**(_BYTE **)v123 )
            {
              NRNameFromAbsoluteName = -1073741771;
              v13 = 2388;
              goto LABEL_61;
            }
            v14 |= 1u;
            goto LABEL_173;
          }
          v13 = 2404;
        }
        else
        {
          v13 = 2369;
        }
        NRNameFromAbsoluteName = (v147[0] & 0x10) != 0 ? -1073741108 : -1073741790;
        goto LABEL_61;
      }
    }
LABEL_133:
    v36 = v107;
LABEL_134:
    if ( (v14 & 8) != 0 )
    {
      if ( (v114 & 1) != 0 )
      {
        v124 = v36;
        CscStoreReferenceEntry(v36);
      }
      CscStoreDereferenceEntry(&v107);
      v14 &= ~8u;
    }
    LODWORD(v1) = v115[0];
    goto LABEL_139;
  }
  NRNameFromAbsoluteName = CscStoreQueryInformationEntryEx(
                             *(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL),
                             0,
                             (unsigned int)v142,
                             0,
                             0,
                             0,
                             0);
  if ( NRNameFromAbsoluteName < 0 )
  {
    v13 = 1815;
    goto LABEL_62;
  }
  *(_QWORD *)&v139 = v109;
  NRNameFromAbsoluteName = RxSubjectContextFromRxContext(v109, (char *)&v139 + 8);
  if ( NRNameFromAbsoluteName < 0 )
  {
    v13 = 1826;
    goto LABEL_62;
  }
  if ( (v142[0] & 0x4840) != 0 )
  {
    NRNameFromAbsoluteName = -1073741811;
    v13 = 1836;
    goto LABEL_62;
  }
  if ( *(_WORD *)v1 == 0xEC22 )
  {
    v25 = HIBYTE(v113);
    if ( (v142[0] & 0x800000) != 0 )
      v25 = 1;
    HIBYTE(v113) = v25;
  }
  if ( (v17 & 1) != 0 )
    goto LABEL_133;
  v105 = 0;
  v26 = CscStoreFindEntryEx((unsigned int)&v107, 0, (unsigned int)&SourceString, 0, (__int64)&v105);
  NRNameFromAbsoluteName = v26;
  if ( v26 < 0 )
  {
    if ( (v141 & 0x10) != 0 )
    {
      if ( v26 == -1073741766 || v26 == -1073741809 || v26 == -1073741772 )
        NRNameFromAbsoluteName = -1073741766;
      v13 = 1875;
      goto LABEL_61;
    }
    if ( v26 != -1073741766 && v26 != -1073741809 && v26 != -1073741772 )
    {
      v13 = 1880;
LABEL_61:
      v8 = v107;
      goto LABEL_62;
    }
    if ( v105 )
    {
      NRNameFromAbsoluteName = -1073741766;
      v13 = 1891;
      goto LABEL_61;
    }
    NRNameFromAbsoluteName = CscStoreFindLongestPrefixEntry(&v116, v27, &SourceString, &v140);
    if ( NRNameFromAbsoluteName < 0 )
    {
      v13 = 1908;
      goto LABEL_61;
    }
    if ( (_WORD)v140 == SourceString.Length )
    {
      v8 = v116;
      v107 = v116;
      v116 = 0;
      goto LABEL_82;
    }
    v28 = SourceString.Length - v140;
    v29 = (PWSTR)((char *)SourceString.Buffer + (unsigned __int16)v140);
    LOWORD(v135) = SourceString.Length - v140;
    WORD1(v135) = SourceString.Length - v140;
    *((_QWORD *)&v135 + 1) = v29;
    if ( *v29 == 92 )
    {
      LOWORD(v135) = v28 - 2;
      *((_QWORD *)&v135 + 1) = v29 + 1;
      WORD1(v135) = v28 - 2;
    }
    v146 = 16;
    *(_QWORD *)&v144 = 0;
    *((_QWORD *)&v144 + 1) = MEMORY[0xFFFFF78000000014];
    *((_QWORD *)&v143 + 1) = MEMORY[0xFFFFF78000000014];
    *(_QWORD *)&v143 = MEMORY[0xFFFFF78000000014];
    v145 = 0;
    NRNameFromAbsoluteName = CscStoreFindOrCreateEntry(
                               (unsigned int)&v107,
                               (unsigned int)&v114,
                               v116,
                               (unsigned int)&v135,
                               524291,
                               (__int64)&v143,
                               0,
                               0);
    if ( NRNameFromAbsoluteName < 0 )
    {
      v13 = 1957;
      goto LABEL_61;
    }
    v112 = 1;
  }
  v8 = v107;
LABEL_82:
  v14 |= 8u;
  if ( (v114 & 1) != 0 )
    goto LABEL_109;
  memset(v147, 0, sizeof(v147));
  CscStoreQueryInformationEntryEx(v8, 0, (unsigned int)v147, 0, 0, 0, 0);
  if ( (unsigned __int8)CscStoreIsEntryDirectory(v8) && (v147[0] & 0x10) == 0 )
  {
    v31 = CscStoreFindEntry(&v117, v8, &Source, v30);
    if ( v31 >= 0 )
    {
      NRNameFromAbsoluteName = CscStoreQueryInformationEntryEx(v117, 0, (unsigned int)v150, 0, 0, 0, 0);
      LODWORD(v9) = (unsigned __int8)(v9 | (32 * (CscStoreIsEntryDirectory(v117) & 1)));
      CscStoreDereferenceEntry(&v117);
      if ( NRNameFromAbsoluteName < 0 )
      {
        v13 = 2038;
        goto LABEL_62;
      }
      v32 = v150[0];
      if ( (v150[0] & 0x10) != 0 )
      {
        if ( (unsigned __int8)v9 >= 0x20u )
        {
          if ( (v141 & 0x10) == 0 )
          {
            LOBYTE(v141) = v141 | 0x10;
            CscTransitionFcbOffline(*(_QWORD *)v115, 0, 8, 0);
            v32 = v150[0];
          }
        }
        else
        {
          v14 |= 0x80u;
        }
        if ( (((unsigned int)v9 >> 4) & 1) != (unsigned __int8)v9 >= 0x20u )
        {
          v13 = 2082;
          NRNameFromAbsoluteName = (v32 & 0x10) != 0 ? -1073741108 : -1073741790;
          goto LABEL_62;
        }
      }
      else
      {
        if ( (unsigned __int8)v9 >= 0x20u || (v9 & 0x10) != 0 )
        {
          NRNameFromAbsoluteName = -1073741771;
          v13 = 2093;
          goto LABEL_62;
        }
        v14 |= 0x40u;
      }
      goto LABEL_103;
    }
    if ( v31 == -1073741772 && (v9 & 0x10) == 0 && (int)CscStoreGetTunneledInfo(v8, &Source, v150) >= 0 )
    {
LABEL_103:
      v33 = v109;
      NRNameFromAbsoluteName = CscSetInfopCanFlowRenameToServer(v109, &v141, &SourceString, &Source, v142, v150);
      if ( NRNameFromAbsoluteName < 0 )
      {
        v13 = 2140;
        goto LABEL_62;
      }
      goto LABEL_110;
    }
LABEL_109:
    v33 = v109;
LABEL_110:
    v34 = v141;
    if ( ((unsigned __int8)v9 & (unsigned __int8)v141 & 0x10) != 0 )
    {
      NRNameFromAbsoluteName = CscIsDirectoryRenameDeleteAllowed(v33, v142);
      if ( NRNameFromAbsoluteName < 0 )
      {
        v13 = 2153;
        goto LABEL_62;
      }
      v34 = v141;
    }
    if ( (v34 & 0x10) == 0 || (v142[0] & 0x400) != 0 )
      v35 = 0;
    else
      v35 = 16;
    v14 = v35 | v14 & 0xEF;
    if ( (v34 & 0x10) != 0 )
    {
      NRNameFromAbsoluteName = CscCheckTargetAccess(v33, v8, (v9 & 0x10) != 0);
      if ( NRNameFromAbsoluteName < 0 )
      {
        v13 = 2174;
        goto LABEL_62;
      }
      v34 = v141;
    }
    NRNameFromAbsoluteName = CscStoreRenameEntry(
                               *(_QWORD *)(*((_QWORD *)&v130 + 1) + 56LL),
                               v8,
                               (unsigned int)&Source,
                               (unsigned int)CscDirectoryRenameItemValidateCallback,
                               (__int64)&v139,
                               *(_BYTE *)v3,
                               (v14 & 0x10) != 0,
                               (v34 & 0x10) != 0);
    if ( NRNameFromAbsoluteName < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
      v13 = 2202;
      goto LABEL_62;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      LOBYTE(v16) = (v14 & 0x10) != 0 ? 89 : 78;
      WPP_SF_c(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, v16);
    }
    LOBYTE(v9) = v9 | 0x80;
    if ( (v14 & 0x10) != 0 && (int)CscStoreFindEntry(&v125, 0, v129, v16) >= 0 )
    {
      v14 |= 0x20u;
      CscStoreSetExplicitAccessEntry(v125, 0, *(_QWORD *)(*(_QWORD *)v128 + 40LL) + 112, 2032127, 3);
    }
    goto LABEL_133;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
  NRNameFromAbsoluteName = -1073741766;
  v13 = 2012;
LABEL_62:
  if ( (v114 & 1) == 0 || NRNameFromAbsoluteName >= 0 || !v112 )
  {
LABEL_405:
    if ( v124 )
      CscStoreDereferenceEntry(&v124);
    goto LABEL_407;
  }
  if ( v124 )
  {
    CscStoreDeleteEntryPath(v116, v124);
    goto LABEL_405;
  }
  if ( v8 )
  {
    v100 = v116;
    CscStoreDeleteEntryPath(v116, v8);
    goto LABEL_408;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
    goto LABEL_405;
  }
LABEL_407:
  v100 = v116;
LABEL_408:
  if ( (v14 & 0x20) != 0 )
    CscStoreDereferenceEntry(&v125);
  if ( (v14 & 8) != 0 )
    CscStoreDereferenceEntry(&v107);
  if ( v100 )
  {
    if ( NRNameFromAbsoluteName >= 0 && ((v114 & 1) != 0 || (v114 & 2) != 0) )
      CscBumpGlobalNewlyCachedEpoch();
    CscStoreDereferenceEntry(&v116);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      48,
      WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
      (unsigned int)NRNameFromAbsoluteName,
      v13);
  return (unsigned int)NRNameFromAbsoluteName;
}

```

## disassembly

```asm
0x1400837e0  push    rbp
0x1400837e2  push    rbx
0x1400837e3  push    rsi
0x1400837e4  push    rdi
0x1400837e5  push    r12
0x1400837e7  push    r13
0x1400837e9  push    r14
0x1400837eb  push    r15
0x1400837ed  lea     rbp, [rsp-258h]
0x1400837f5  sub     rsp, 358h
0x1400837fc  mov     rax, cs:__security_cookie
0x140083803  xor     rax, rsp
0x140083806  mov     [rbp+290h+var_50], rax
0x14008380d  mov     r14, [rcx+38h]
0x140083811  xorps   xmm0, xmm0
0x140083814  mov     rsi, [rcx+48h]
0x140083818  xor     r12d, r12d
0x14008381b  mov     r13, [rcx+1C8h]
0x140083822  xorps   xmm1, xmm1
0x140083825  mov     rbx, rcx
0x140083828  mov     [rsp+390h+var_320], rcx
0x14008382d  mov     rax, [r14+80h]
0x140083834  mov     qword ptr [rbp+290h+var_280], rax
0x140083838  mov     rax, [r14+78h]
0x14008383c  mov     qword ptr [rbp+290h+var_308], r14
0x140083840  mov     qword ptr [rbp+290h+var_270], rsi
0x140083844  mov     qword ptr [rbp+290h+var_2A0], r13
0x140083848  mov     rax, [rax+20h]
0x14008384c  mov     qword ptr [rbp+290h+var_218], rax
0x140083850  mov     eax, [rcx+1C0h]
0x140083856  mov     [rsp+390h+var_33C], eax
0x14008385a  mov     eax, [rcx+1D8h]
0x140083860  mov     rcx, r14
0x140083863  mov     [rbp+290h+var_230], eax
0x140083866  xor     eax, eax
0x140083868  mov     [rbp+290h+var_140], rax
0x14008386f  mov     [rbp+290h+var_22C], r12d
0x140083873  movups  [rbp+290h+var_170], xmm0
0x14008387a  mov     [rbp+290h+var_1F8], r12
0x140083881  movups  [rbp+290h+var_160], xmm0
0x140083888  mov     [rsp+390h+var_328], r12b
0x14008388d  movups  [rbp+290h+var_150], xmm0
0x140083894  mov     [rsp+390h+var_318], r12b
0x140083899  mov     [rsp+390h+var_316], r12b
0x14008389e  mov     [rbp+290h+var_310], r12d
0x1400838a2  movups  [rbp+290h+var_2B0], xmm0
0x1400838a6  movups  xmmword ptr [rbp+290h+Source.Length], xmm1
0x1400838aa  movups  xmmword ptr [rbp+290h+SourceString.Length], xmm0
0x1400838ae  movups  [rbp+290h+var_1E0], xmm1
0x1400838b5  movups  [rbp+290h+var_228], xmm0
0x1400838b9  movups  [rbp+290h+var_208], xmm1
0x1400838c0  call    cs:__imp_RxFcbTableNameFromFcb
0x1400838c7  nop     dword ptr [rax+rax+00h]
0x1400838cc  xorps   xmm0, xmm0
0x1400838cf  lea     r15d, [r12+50h]
0x1400838d4  lea     rcx, [rbp+290h+var_1C0]; void *
0x1400838db  mov     [rbp+290h+var_268], rax
0x1400838df  mov     r8d, r15d; Size
0x1400838e2  xor     edx, edx; Val
0x1400838e4  movups  [rbp+290h+var_260], xmm0
0x1400838e8  mov     rdi, rax
0x1400838eb  movups  [rbp+290h+var_250], xmm0
0x1400838ef  movups  [rbp+290h+var_1D0], xmm0
0x1400838f6  call    memset
0x1400838fb  mov     r8d, r15d; Size
0x1400838fe  lea     rcx, [rbp+290h+var_A0]; void *
0x140083905  xor     edx, edx; Val
0x140083907  call    memset
0x14008390c  mov     rax, cs:CscDeviceObject
0x140083913  lea     rdx, [rbp+290h+var_260]
0x140083917  cmp     [rbx+50h], rax
0x14008391b  mov     r15d, r12d
0x14008391e  mov     [rsp+390h+var_317], r12b
0x140083923  mov     ecx, 0EC21h
0x140083928  mov     [rbp+290h+var_2E0], r12d
0x14008392c  setnz   al
0x14008392f  mov     [rsp+390h+var_337], r12b
0x140083934  xorps   xmm0, xmm0
0x140083937  mov     [rbp+290h+var_288], r12d
0x14008393b  lea     r9d, [r15+1]
0x14008393f  mov     [rbp+290h+var_300], r12
0x140083943  mov     [rbp+290h+var_298], r12
0x140083947  mov     [rsp+390h+var_330], r12
0x14008394c  mov     [rbp+290h+var_290], r12
0x140083950  mov     [rbp+290h+var_2F8], r12
0x140083954  mov     [rbp+290h+var_238], r12
0x140083958  mov     [rsp+390h+var_314], r12d
0x14008395d  movups  [rbp+290h+var_1F0], xmm0
0x140083964  cmp     [r14], cx
0x140083968  mov     rcx, rbx
0x14008396b  setnz   r12b
0x14008396f  sub     r12b, r9b
0x140083972  and     r12b, 10h
0x140083976  or      r12b, al
0x140083979  call    CscGetContexts
0x14008397e  lea     rax, [rbp+290h+var_1D0]
0x140083985  mov     byte ptr [rsp+390h+var_368], r9b
0x14008398a  mov     r8, rbx
0x14008398d  mov     [rsp+390h+var_370], rax
0x140083992  mov     rdx, rsi
0x140083995  mov     rcx, r14
0x140083998  call    CscUpdateAndCaptureConnectionStateEx
0x14008399d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400839a4  lea     rax, WPP_GLOBAL_Control
0x1400839ab  mov     ebx, [rsp+390h+var_33C]
0x1400839af  cmp     rcx, rax
0x1400839b2  jz      short loc_1400839EA
0x1400839b4  mov     eax, [rcx+2Ch]
0x1400839b7  test    al, 20h
0x1400839b9  jz      short loc_1400839EA
0x1400839bb  mov     rcx, [rcx+18h]
0x1400839bf  lea     edx, [r15+1Ch]
0x1400839c3  mov     al, r12b
0x1400839c6  mov     dword ptr [rsp+390h+var_368], ebx
0x1400839ca  and     al, 1
0x1400839cc  mov     [rsp+390h+var_370], rsi
0x1400839d1  neg     al
0x1400839d3  lea     r8, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids
0x1400839da  sbb     r9b, r9b
0x1400839dd  and     r9b, 0Bh
0x1400839e1  add     r9b, 4Eh ; 'N'
0x1400839e5  call    WPP_SF_cqD
0x1400839ea  test    byte ptr [rbp+290h+var_1D0+1], 40h
0x1400839f1  mov     ecx, 2
0x1400839f6  jz      short loc_140083A15
0x1400839f8  lea     rcx, [rbp+290h+var_1D0]
0x1400839ff  call    CscDetermineAbortStatus
0x140083a04  mov     edi, eax
0x140083a06  mov     ebx, 60Bh
0x140083a0b  mov     sil, byte ptr [rsp+390h+var_314+1]
0x140083a10  jmp     loc_140083E44
0x140083a15  mov     rax, qword ptr [rbp+290h+var_250]
0x140083a19  test    rax, rax
0x140083a1c  jz      loc_140085519
0x140083a22  test    dword ptr [rax+18h], 809h
0x140083a29  jnz     loc_140085519
0x140083a2f  mov     edx, 4
0x140083a34  lea     eax, [rbx-0Ah]
0x140083a37  lea     r8d, [rdx-3]
0x140083a3b  lea     r9d, [rdx+58h]
0x140083a3f  cmp     eax, r8d
0x140083a42  ja      loc_14008468D
0x140083a48  mov     eax, [r13+10h]
0x140083a4c  sub     eax, ecx
0x140083a4e  cmp     eax, 0FFFCh
0x140083a53  ja      loc_14008467E
0x140083a59  mov     al, byte ptr [rsp+390h+var_314+1]
0x140083a5d  lea     rcx, [r13+14h]
0x140083a61  cmp     r9w, [rcx]
0x140083a65  setnz   sil
0x140083a69  and     al, 0FBh
0x140083a6b  sub     sil, r8b
0x140083a6e  and     sil, dl
0x140083a71  or      sil, al
0x140083a74  movzx   eax, word ptr [r13+10h]
0x140083a79  mov     word ptr [rbp+290h+var_2B0+2], ax
0x140083a7d  mov     word ptr [rbp+290h+var_2B0], ax
0x140083a81  mov     qword ptr [rbp+290h+var_2B0+8], rcx
0x140083a85  test    dl, sil
0x140083a88  jz      short loc_140083AEA
0x140083a8a  mov     edx, r9d
0x140083a8d  lea     r8, [rbp+290h+var_208]
0x140083a94  lea     rcx, [rbp+290h+var_2B0]
0x140083a98  call    cs:__imp_RxLastComponentUnicodeString
0x140083a9f  nop     dword ptr [rax+rax+00h]
0x140083aa4  movzx   eax, word ptr [rbp+290h+var_208]
0x140083aab  movzx   r8d, word ptr [rbp+290h+var_2B0]
0x140083ab0  mov     edx, eax
0x140083ab2  mov     bl, byte ptr [rsp+390h+var_314+2]
0x140083ab6  mov     ecx, r8d
0x140083ab9  sub     rcx, rax
0x140083abc  mov     [rbp+290h+Source.MaximumLength], ax
0x140083ac0  mov     [rbp+290h+Source.Length], ax
0x140083ac4  mov     rax, qword ptr [rbp+290h+var_2B0+8]
0x140083ac8  add     rcx, rax
0x140083acb  mov     [rbp+290h+SourceString.Buffer], rax
0x140083acf  sub     r8w, dx
0x140083ad3  mov     [rbp+290h+Source.Buffer], rcx
0x140083ad7  mov     [rbp+290h+SourceString.MaximumLength], r8w
0x140083adc  mov     [rbp+290h+SourceString.Length], r8w
0x140083ae1  mov     [rsp+390h+var_340], bl
0x140083ae5  jmp     loc_140083BB7
0x140083aea  mov     eax, 3Ah ; ':'
0x140083aef  cmp     ax, [rcx]
0x140083af2  mov     al, byte ptr [rsp+390h+var_314+2]
0x140083af6  setz    bl
0x140083af9  and     al, 0FEh
0x140083afb  or      bl, al
0x140083afd  mov     [rsp+390h+var_340], bl
0x140083b01  test    r8b, bl
0x140083b04  jz      short loc_140083B33
0x140083b06  lea     rdx, [rsp+390h+var_318]
0x140083b0b  lea     rcx, [rbp+290h+var_2B0]
0x140083b0f  call    cs:__imp_RxRemoveDollarDataSuffix
0x140083b16  nop     dword ptr [rax+rax+00h]
0x140083b1b  mov     r8d, 1
0x140083b21  lea     r9d, [r8+5Bh]
0x140083b25  cmp     [rsp+390h+var_318], r15b
0x140083b2a  jz      short loc_140083B33
0x140083b2c  and     bl, 0FEh
0x140083b2f  mov     [rsp+390h+var_340], bl
0x140083b33  and     bl, r8b
0x140083b36  jz      short loc_140083B3C
0x140083b38  xor     ecx, ecx
0x140083b3a  jmp     short loc_140083B74
0x140083b3c  mov     edx, r9d
0x140083b3f  lea     r8, [rbp+290h+var_208]
0x140083b46  mov     rcx, rdi
0x140083b49  call    cs:__imp_RxLastComponentUnicodeString
0x140083b50  nop     dword ptr [rax+rax+00h]
0x140083b55  movzx   eax, word ptr [rbp+290h+var_208]
0x140083b5c  mov     [rbp+290h+Source.MaximumLength], ax
0x140083b60  mov     ecx, eax
0x140083b62  mov     [rbp+290h+Source.Length], ax
0x140083b66  movzx   eax, word ptr [rdi]
0x140083b69  sub     rax, rcx
0x140083b6c  add     rax, [rdi+8]
0x140083b70  mov     [rbp+290h+Source.Buffer], rax
0x140083b74  movaps  xmm0, [rbp+290h+var_2B0]
0x140083b78  mov     [rbp+290h+Source.Length], cx
0x140083b7c  mov     rax, [rdi+8]
0x140083b80  mov     [rbp+290h+SourceString.Buffer], rax
0x140083b84  movzx   eax, word ptr [rdi]
0x140083b87  sub     ax, cx
0x140083b8a  movdqa  xmmword ptr [rbp+290h+Source.Length], xmm0
0x140083b8f  test    byte ptr [rbp+290h+var_1D0], 10h
0x140083b96  mov     [rbp+290h+SourceString.MaximumLength], ax
0x140083b9a  mov     [rbp+290h+SourceString.Length], ax
0x140083b9e  jz      short loc_140083BB3
0x140083ba0  test    bl, bl
0x140083ba2  jz      short loc_140083BB3
0x140083ba4  mov     edi, 0C00002CCh
0x140083ba9  mov     ebx, 6BEh
0x140083bae  jmp     loc_140083E44
0x140083bb3  mov     bl, [rsp+390h+var_340]
0x140083bb7  xorps   xmm0, xmm0
0x140083bba  lea     r8, [rbp+290h+Source]; Source
0x140083bbe  lea     rdx, [rbp+290h+SourceString]; SourceString
0x140083bc2  lea     rcx, [rbp+290h+P]; Destination
0x140083bc6  movups  xmmword ptr [rbp+290h+P], xmm0
0x140083bca  call    CscPathUtilsAllocFullPathFromParentPathAndLeafFile
0x140083bcf  mov     edi, eax
0x140083bd1  test    eax, eax
0x140083bd3  jns     short loc_140083BDF
0x140083bd5  mov     ebx, 6CEh
0x140083bda  jmp     loc_140083E44
0x140083bdf  mov     rdx, [rbp+290h+var_268]
0x140083be3  lea     r8, [rbp+290h+P]
0x140083be7  mov     rcx, r14
0x140083bea  call    CscExclusionListCheckRenameAndHardLinkCreate
0x140083bef  mov     edi, eax
0x140083bf1  cmp     eax, 0C0000804h
0x140083bf6  jnz     short loc_140083C75
0x140083bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x140083bff  lea     rax, WPP_GLOBAL_Control
0x140083c06  cmp     rcx, rax
0x140083c09  jz      short loc_140083C2B
0x140083c0b  mov     eax, [rcx+2Ch]
0x140083c0e  test    al, 20h
0x140083c10  jz      short loc_140083C2B
0x140083c12  mov     rcx, [rcx+18h]
0x140083c16  lea     r9, [rbp+290h+P]
0x140083c1a  mov     edx, 1Dh
0x140083c1f  lea     r8, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids
0x140083c26  call    WPP_SF_Z
0x140083c2b  mov     rdx, [rbp+290h+var_268]
0x140083c2f  lea     r8, [rbp+290h+P]
0x140083c33  mov     ecx, 1
0x140083c38  call    CscDclNotifyExcludedFileType
0x140083c3d  test    eax, eax
0x140083c3f  jns     short loc_140083C75
0x140083c41  mov     r10, cs:WPP_GLOBAL_Control
0x140083c48  lea     rcx, WPP_GLOBAL_Control
0x140083c4f  cmp     r10, rcx
0x140083c52  jz      short loc_140083C75
0x140083c54  mov     ecx, [r10+2Ch]
0x140083c58  test    cl, 40h
0x140083c5b  jz      short loc_140083C75
0x140083c5d  mov     rcx, [r10+18h]
0x140083c61  lea     r8, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids
0x140083c68  mov     edx, 1Eh
0x140083c6d  mov     r9d, eax
0x140083c70  call    WPP_SF_d
0x140083c75  mov     rcx, [rbp+290h+P+8]; P
0x140083c79  xor     edx, edx; Tag
0x140083c7b  call    cs:__imp_ExFreePoolWithTag
0x140083c82  nop     dword ptr [rax+rax+00h]
0x140083c87  test    edi, edi
0x140083c89  jns     short loc_140083C95
0x140083c8b  mov     ebx, 6E7h
0x140083c90  jmp     loc_140083E44
0x140083c95  mov     eax, [rsp+390h+var_33C]
0x140083c99  cmp     eax, 0Ah
0x140083c9c  jnz     loc_140084676
0x140083ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x140083ca9  lea     rax, WPP_GLOBAL_Control
0x140083cb0  cmp     rcx, rax
0x140083cb3  jz      short loc_140083D27
0x140083cb5  mov     eax, [rcx+2Ch]
0x140083cb8  test    al, 20h
  ... truncated ...
```
