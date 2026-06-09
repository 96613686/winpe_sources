# CscSetFileInformation

- ea: `0x1400837e0`
- end: `0x140085611`
- name: `CscSetFileInformation`
- size: `7729`
- prototype: `__int64 __fastcall(__int64)`
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
  __int64 v10; // r8
  int v11; // r9d
  __int64 v12; // r9
  int NRNameFromAbsoluteName; // edi
  int v14; // ebx
  char v15; // si
  __int64 v16; // r9
  char v17; // bl
  char v18; // bl
  char v19; // bl
  USHORT v20; // cx
  USHORT v21; // ax
  int v22; // eax
  int v23; // eax
  char v24; // al
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int16 v28; // dx
  PWSTR v29; // rax
  int v30; // eax
  char v31; // dl
  __int64 v32; // rbx
  char v33; // cl
  char v34; // dl
  __int64 v35; // r13
  int v36; // r15d
  _DWORD *v37; // rbx
  int v38; // r13d
  __int64 v39; // rdi
  int v40; // r13d
  __int64 v41; // r9
  UNICODE_STRING *v42; // r8
  unsigned int v43; // eax
  int v44; // ecx
  int InformationEntry; // ebx
  int TunneledInfo; // ebx
  int v47; // r14d
  __int64 Pool2; // rax
  int v49; // edx
  __int64 v50; // r15
  int v51; // ecx
  __int64 v52; // rdx
  char v53; // r12
  __int64 v54; // r8
  __int64 v55; // r14
  __int64 v56; // rax
  unsigned int v57; // r13d
  __int64 v58; // r8
  char v59; // dl
  char v60; // al
  __int64 v61; // r14
  char v62; // bl
  __int64 v63; // r8
  char v64; // bl
  unsigned __int16 *v65; // rbx
  unsigned int v66; // edx
  __int64 v67; // rcx
  int v68; // ebx
  UNICODE_STRING *v69; // rdx
  int v70; // eax
  UNICODE_STRING *p_Source; // r8
  int Entry; // eax
  __int64 v73; // rbx
  int v74; // eax
  _WORD *v75; // rbx
  __int64 v76; // r14
  unsigned int v77; // eax
  __int64 v78; // rdx
  __int64 v79; // r8
  int v80; // edx
  __int64 v81; // r14
  int v82; // r12d
  int v83; // ebx
  __int64 v84; // rcx
  __int64 v85; // r12
  __int64 v86; // r8
  __int64 v87; // rdx
  char v88; // al
  unsigned int v89; // eax
  char Only; // r14
  int v91; // eax
  int v92; // edx
  __int64 v93; // rcx
  int v94; // eax
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rcx
  int v99; // eax
  unsigned int v100; // eax
  __int64 v101; // r14
  char v103; // [rsp+50h] [rbp-B0h]
  char v104; // [rsp+50h] [rbp-B0h]
  int v105; // [rsp+54h] [rbp-ACh]
  char v106; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v107[7]; // [rsp+59h] [rbp-A7h] BYREF
  __int64 v108; // [rsp+60h] [rbp-A0h] BYREF
  char v109; // [rsp+68h] [rbp-98h]
  __int64 v110; // [rsp+70h] [rbp-90h]
  char v111; // [rsp+78h] [rbp-88h] BYREF
  char v112; // [rsp+79h] [rbp-87h] BYREF
  char v113; // [rsp+7Ah] [rbp-86h]
  int v114; // [rsp+7Ch] [rbp-84h]
  int v115; // [rsp+80h] [rbp-80h] BYREF
  int v116[2]; // [rsp+88h] [rbp-78h]
  __int64 v117; // [rsp+90h] [rbp-70h] BYREF
  __int64 v118; // [rsp+98h] [rbp-68h] BYREF
  UNICODE_STRING Source; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v120; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING SourceString; // [rsp+B8h] [rbp-48h] BYREF
  PVOID P[3]; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING v123; // [rsp+E0h] [rbp-20h] BYREF
  int v124[2]; // [rsp+F0h] [rbp-10h]
  __int64 v125; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v126; // [rsp+100h] [rbp+0h] BYREF
  int v127; // [rsp+108h] [rbp+8h] BYREF
  int v128[4]; // [rsp+110h] [rbp+10h] BYREF
  int v129[2]; // [rsp+120h] [rbp+20h]
  __int64 v130; // [rsp+128h] [rbp+28h]
  __int128 v131; // [rsp+130h] [rbp+30h] BYREF
  __int128 v132; // [rsp+140h] [rbp+40h]
  __int64 v133; // [rsp+158h] [rbp+58h] BYREF
  int v134; // [rsp+160h] [rbp+60h]
  int v135; // [rsp+164h] [rbp+64h] BYREF
  __int128 v136; // [rsp+168h] [rbp+68h] BYREF
  __int128 v137; // [rsp+178h] [rbp+78h] BYREF
  __int128 v138; // [rsp+188h] [rbp+88h] BYREF
  __int64 v139; // [rsp+198h] [rbp+98h] BYREF
  __int128 v140; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v141; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v142; // [rsp+1C0h] [rbp+C0h] BYREF
  _QWORD v143[10]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v144; // [rsp+220h] [rbp+120h] BYREF
  __int128 v145; // [rsp+230h] [rbp+130h]
  __int128 v146; // [rsp+240h] [rbp+140h]
  __int64 v147; // [rsp+250h] [rbp+150h]
  _DWORD v148[20]; // [rsp+260h] [rbp+160h] BYREF
  _OWORD v149[3]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v150; // [rsp+2E0h] [rbp+1E0h]
  _DWORD v151[20]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v2 = *(_QWORD *)(a1 + 72);
  v3 = *(_QWORD *)(a1 + 456);
  v110 = a1;
  *(_QWORD *)v128 = *(_QWORD *)(v1 + 128);
  v5 = *(_QWORD *)(v1 + 120);
  *(_QWORD *)v116 = v1;
  *(_QWORD *)v129 = v2;
  *(_QWORD *)v124 = v3;
  *(_QWORD *)&v137 = *(_QWORD *)(v5 + 32);
  v105 = *(_DWORD *)(a1 + 448);
  v134 = *(_DWORD *)(a1 + 472);
  v147 = 0;
  v135 = 0;
  v144 = 0;
  v139 = 0;
  v145 = 0;
  v109 = 0;
  v146 = 0;
  v111 = 0;
  v113 = 0;
  v115 = 0;
  v123 = 0;
  Source = 0;
  SourceString = 0;
  v141 = 0;
  v136 = 0;
  v138 = 0;
  v130 = RxFcbTableNameFromFcb(v1);
  v131 = 0;
  v6 = (unsigned __int16 *)v130;
  v132 = 0;
  v142 = 0;
  memset(v143, 0, sizeof(v143));
  memset(v151, 0, sizeof(v151));
  v7 = *(_QWORD *)(a1 + 80) == (_QWORD)CscDeviceObject;
  v8 = 0;
  v112 = 0;
  v120 = 0;
  v107[0] = 0;
  v127 = 0;
  v117 = 0;
  v125 = 0;
  v108 = 0;
  v126 = 0;
  v118 = 0;
  v133 = 0;
  v114 = 0;
  v140 = 0;
  v9 = !v7 | (unsigned __int8)(*(_WORD *)v1 != 0xEC21 ? 0 : 0x10);
  CscGetContexts(a1, &v131, v10, 1);
  CscUpdateAndCaptureConnectionStateEx(v1, v2, a1, v11, (__int64)&v142, v11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v12) = (v9 & 1) != 0 ? 89 : 78;
    WPP_SF_cqD(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, v12, v2, v105);
  }
  if ( (BYTE1(v142) & 0x40) != 0 )
  {
    NRNameFromAbsoluteName = CscDetermineAbortStatus(&v142);
    v14 = 1547;
LABEL_6:
    v15 = BYTE1(v114);
    goto LABEL_62;
  }
  if ( !(_QWORD)v132 || (*(_DWORD *)(v132 + 24) & 0x809) != 0 )
  {
    v14 = 1557;
    NRNameFromAbsoluteName = -1073741811;
    goto LABEL_6;
  }
  v16 = 92;
  if ( (unsigned int)(v105 - 10) > 1 )
  {
    NRNameFromAbsoluteName = 0;
    v15 = BYTE1(v114);
    v23 = v105;
    v103 = BYTE2(v114);
LABEL_178:
    if ( v23 != 13 )
    {
LABEL_140:
      v36 = -1073741823;
      if ( (v142 & 0x10) != 0 )
      {
        v55 = *(_QWORD *)v124;
        goto LABEL_210;
      }
      v37 = 0;
      v38 = 0;
      if ( (v15 & 4) != 0 && (unsigned int)(v23 - 10) <= 1 )
      {
        v39 = *(_QWORD *)v124;
        v40 = v128[0];
        LODWORD(P[0]) = 0;
        if ( (unsigned int)CscSetInfopGetNRNameFromAbsoluteName(v1, v129[0], v128[0], v124[0], 0, (__int64)P) != -2147483643 )
        {
          NRNameFromAbsoluteName = -1073740768;
          v14 = 2569;
          goto LABEL_61;
        }
        v47 = LODWORD(P[0]) + 24;
        Pool2 = ExAllocatePool2(258, (unsigned int)(LODWORD(P[0]) + 24), 1061124178, v41);
        v37 = (_DWORD *)Pool2;
        if ( !Pool2 )
        {
          NRNameFromAbsoluteName = -1073741670;
          v14 = 2583;
          goto LABEL_61;
        }
        v49 = v129[0];
        v50 = Pool2 + 20;
        v51 = v116[0];
        *(_OWORD *)Pool2 = *(_OWORD *)v39;
        *(_QWORD *)(Pool2 + 16) = *(_QWORD *)(v39 + 16);
        NRNameFromAbsoluteName = CscSetInfopGetNRNameFromAbsoluteName(
                                   v51,
                                   v49,
                                   v40,
                                   v39,
                                   (void *)(Pool2 + 20),
                                   (__int64)P);
        if ( NRNameFromAbsoluteName < 0 )
        {
          v14 = 2604;
          goto LABEL_61;
        }
        v52 = v110;
        v15 |= 2u;
        v37[4] = P[0];
        *(_OWORD *)v128 = 0;
        v38 = *(_DWORD *)(v52 + 472);
        *(_DWORD *)(v52 + 472) = v47;
        *(_QWORD *)(v52 + 456) = v37;
        LOWORD(v128[0]) = *((_WORD *)v37 + 8);
        *(_QWORD *)&v128[2] = v50;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
        {
          goto LABEL_199;
        }
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, v128);
      }
      v52 = v110;
LABEL_199:
      v53 = v9 | 2;
      if ( (v142 & 0x20) != 0 && (BYTE1(v142) & 2) == 0 )
        *(_DWORD *)(v52 + 120) |= 0x10000000u;
      v54 = v137;
      if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v137 + 48) + 352LL) + 208LL) )
      {
        if ( (*(_DWORD *)(v52 + 128) & 2) != 0 )
        {
          NRNameFromAbsoluteName = -1073741536;
        }
        else
        {
          *(_OWORD *)(v52 + 208) = 0;
          *(_OWORD *)(v52 + 224) = 0;
          *(_QWORD *)(v52 + 240) = 0;
          NRNameFromAbsoluteName = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v54 + 48) + 352LL)
                                                                      + 208LL))(v52);
        }
      }
      else
      {
        NRNameFromAbsoluteName = -1073741822;
      }
      v36 = NRNameFromAbsoluteName;
      LOBYTE(v9) = v53
                 ^ (v53
                  ^ (4
                   * CscCheckRdrStatusTransitionIfNetErr((unsigned int)NRNameFromAbsoluteName, &v142, *(_QWORD *)v116)))
                 & 4;
      v55 = *(_QWORD *)v124;
      if ( (v15 & 2) != 0 )
      {
        v56 = v110;
        *(_QWORD *)(v110 + 456) = *(_QWORD *)v124;
        *(_DWORD *)(v56 + 472) = v38;
        ExFreePoolWithTag(v37, 0);
      }
LABEL_210:
      v57 = 0;
      if ( v105 == 10 )
      {
        if ( (v9 & 2) == 0 )
        {
LABEL_284:
          if ( NRNameFromAbsoluteName >= 0 )
          {
LABEL_285:
            v75 = *(_WORD **)v116;
            v76 = v110;
            if ( HIBYTE(v114) )
              CscDisconnectOpens(v110, *(_QWORD *)v116, CscCheckPrefetchOpenPerFobxCallback);
            if ( (v142 & 0x10) != 0 )
            {
              if ( v109 || (v77 = 4, (v15 & 0x40) != 0) )
                v77 = 2;
              CscNotifyReportChange(v76, (unsigned int)(*v75 == 0xEC21) + 1, v77);
              if ( (v15 & 0x40) != 0 )
              {
                v78 = 252;
                v79 = 3;
              }
              else
              {
                v80 = 0;
                v79 = 1;
                if ( !v109 )
                  v79 = 5;
                LOBYTE(v80) = *v75 == 0xEC21;
                v78 = (unsigned int)(v80 + 1);
              }
              CscNotifyReportChange(v76, v78, v79);
              CscNotifyCleanupAllFcbNotifications(v75);
            }
          }
LABEL_297:
          v81 = v110;
LABEL_298:
          v82 = v105;
LABEL_299:
          v14 = 0;
          if ( (v142 & 0x10) != 0 && NRNameFromAbsoluteName >= 0 && v82 != 10 )
            CscNotifyReportChange(v81, v57, 3);
          goto LABEL_61;
        }
        v58 = 1;
        v59 = v103 & 1;
        v104 = v59;
        v60 = v9 & 4;
        if ( v59 )
        {
          if ( v60 )
          {
            v14 = 2701;
            goto LABEL_61;
          }
        }
        else if ( v60 )
        {
          v61 = *(_QWORD *)v116;
          if ( (v9 & 0x80u) != 0LL && (v115 & 1) == 0 && **(_WORD **)v116 != 0xEC21 )
          {
            v62 = 1;
LABEL_226:
            if ( (int)CscStoreFindEntry(&v108, 0, &SourceString) < 0 )
            {
              v14 = 2739;
              goto LABEL_61;
            }
            v15 |= 8u;
            if ( v62 )
            {
              LOBYTE(v63) = (v9 & 0x10) != 0;
              if ( (int)CscCheckTargetAccess(v110, v108, v63) < 0 )
              {
                LOBYTE(v9) = v9 | 8;
                NRNameFromAbsoluteName = -1073741790;
              }
              if ( (v15 & 4) != 0 )
              {
                CscStoreDereferenceEntry(&v108);
                v15 &= ~8u;
              }
            }
            v59 = v104;
            v58 = 1;
LABEL_233:
            v64 = v9 & 4;
            if ( (v9 & 0x80u) == 0LL || (v64 || v36 >= 0) && (v9 & 8) == 0 && (v9 & 0x14) != 20 )
            {
              if ( v36 >= 0 && (v15 & 1) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
                }
                v8 = v108;
                p_Source = &Source;
                if ( (v15 & 4) != 0 )
                  p_Source = &v123;
                Entry = CscStoreFindEntry(&v118, v108, p_Source);
                if ( Entry < 0 )
                {
                  NRNameFromAbsoluteName = Entry;
                  v14 = 2954;
                  goto LABEL_62;
                }
                v106 = 1;
                CscStoreSetInformationEntry(v118, 0, 0, 0, 0, &v106, 0);
                CscStoreDereferenceEntry(&v118);
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
                if ( v36 >= 0 && v59 )
                {
                  LOBYTE(v58) = 1;
                  RxAcquireExclusiveFcbPagingInMRx(0, v61, v58);
                  if ( (v142 & 0x20) != 0 )
                  {
                    v73 = *((_QWORD *)&v131 + 1);
                    v106 = 1;
                    CscStoreSetInformationEntry(*(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL), 0, 0, 0, 0, &v106, 0);
                    v74 = CscForceFcbStoreEntryClosed(v110, 0);
                    *(_QWORD *)(v73 + 56) = 0;
                    LOBYTE(v142) = v142 & 0xDF;
                    if ( v74 < 0 )
                      _InterlockedOr8((volatile signed __int8 *)(v61 + 256), 2u);
                  }
                  RxReleaseFcbPagingInMRx(0, v61);
                }
              }
            }
            else
            {
              v137 = 0;
              *(_OWORD *)v128 = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
              }
              if ( v64 && *(_WORD *)v61 == 0xEC21 )
                NRNameFromAbsoluteName = (v115 & 1) != 0 ? -1073741766 : -1073741108;
              if ( (v15 & 0x20) != 0 )
              {
                v106 = 1;
                CscStoreSetInformationEntry(v126, 0, 0, 0, 0, &v106, 0);
                CscStoreDereferenceEntry(&v126);
                v15 &= ~0x20u;
              }
              v65 = (unsigned __int16 *)v130;
              RxLastComponentUnicodeString(v130, 92, &v138);
              v66 = *v65;
              v67 = *((_QWORD *)v65 + 1);
              HIWORD(v128[0]) = v138;
              LOWORD(v128[0]) = v138;
              *((_QWORD *)&v137 + 1) = v67;
              WORD1(v137) = v66 - v138;
              LOWORD(v137) = v66 - v138;
              *(_QWORD *)&v128[2] = v67 + v66 - (unsigned __int64)(unsigned __int16)v138;
              v68 = CscStoreFindEntry(&v133, 0, &v137);
              if ( v68 < 0 )
                goto LABEL_258;
              v68 = CscStoreRenameEntry(
                      *(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL),
                      v133,
                      (unsigned int)v128,
                      0,
                      0,
                      1,
                      0,
                      0);
              if ( v68 >= 0 && v15 < 0 )
              {
                v69 = &Source;
                if ( (v15 & 4) != 0 )
                  v69 = &v123;
                CscCreateTombstone(v108, v69, &v151[4], *(_QWORD *)(*(_QWORD *)v129 + 40LL) + 112LL);
              }
              CscStoreDereferenceEntry(&v133);
              if ( v68 < 0 )
              {
LABEL_258:
                CscTransitionFcbOffline(v61, 0, 1024);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    40,
                    WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
                    (unsigned int)v68);
                }
                NRNameFromAbsoluteName = 0;
              }
              else if ( (v115 & 1) != 0 )
              {
                v70 = CscStoreDeleteEntryPath(v117, v125);
                v115 = 0;
                if ( v70 < 0
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
          if ( (v15 & 1) == 0 && (v36 >= 0 || (v9 & 0x80u) == 0LL) )
            goto LABEL_233;
          if ( (v15 & 4) != 0 )
            goto LABEL_233;
          v62 = 0;
          if ( v59 )
            goto LABEL_233;
          goto LABEL_226;
        }
        v61 = *(_QWORD *)v116;
        goto LABEL_221;
      }
      v82 = v105;
      if ( (v142 & 0x20) == 0 || (v142 & 0x10) == 0 && v36 < 0 && (v36 != -1073741567 || v105 != 13) )
        goto LABEL_399;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
      if ( v105 == 4 )
        goto LABEL_365;
      if ( v105 != 13 )
      {
        if ( v105 == 19 )
        {
          CscStoreQueryLocalInformationEntry(
            *(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL),
            20,
            8,
            (unsigned int)&v139,
            (__int64)&v135);
          if ( *(_QWORD *)v55 >= v139 )
            goto LABEL_297;
          v83 = 20;
          v105 = 20;
LABEL_366:
          CscStoreQueryInformationEntryEx(*(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL), 0, (__int64)v143, 0, 0, 0, 0);
          if ( (v142 & 0x10) != 0 && (v143[0] & 0x20) != 0 )
          {
            NRNameFromAbsoluteName = -1073741108;
            v14 = 3193;
            goto LABEL_61;
          }
          v93 = *(_QWORD *)(v132 + 8);
          if ( !v93 )
            v93 = *(_QWORD *)(v132 + 16);
          LOBYTE(v92) = (v142 & 0x10) != 0;
          v94 = CscStoreSetInformationEntryHandle(v93, v92, v83, v134, v55, (__int64)&v120);
          if ( v94 < 0 )
          {
            if ( (v142 & 0x10) != 0 )
            {
              NRNameFromAbsoluteName = v94;
            }
            else
            {
              if ( (*(_DWORD *)(*(_QWORD *)v116 + 156LL) & 4) == 0 )
                CscHandleStoreError(v110, 0, (unsigned int)v94);
              NRNameFromAbsoluteName = v36;
            }
            v14 = 3239;
            goto LABEL_61;
          }
          v57 = v120;
          if ( (v142 & 0x10) == 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
            }
            if ( v83 == 4 )
            {
              v95 = v143[2];
              if ( (unsigned __int64)(*(_QWORD *)v55 + 1LL) > 1 )
                v95 = *(_QWORD *)v55;
              v143[2] = v95;
              v96 = v143[5];
              if ( (unsigned __int64)(*(_QWORD *)(v55 + 24) + 1LL) > 1 )
                v96 = *(_QWORD *)(v55 + 24);
              v143[5] = v96;
              v97 = v143[4];
              if ( (unsigned __int64)(*(_QWORD *)(v55 + 16) + 1LL) > 1 )
                v97 = *(_QWORD *)(v55 + 16);
              v143[4] = v97;
              v98 = v143[3];
              if ( (unsigned __int64)(*(_QWORD *)(v55 + 8) + 1LL) > 1 )
                v98 = *(_QWORD *)(v55 + 8);
              v143[3] = v98;
              v99 = *(_DWORD *)(v55 + 32);
              if ( v99 )
              {
                LODWORD(v143[8]) = *(_DWORD *)(v55 + 32);
                if ( **(_WORD **)v116 == 0xEC21 )
                  v100 = v99 | 0x10;
                else
                  v100 = v99 & 0xFFFFFFEF;
                LODWORD(v143[8]) = v100;
              }
            }
            else
            {
              v143[7] = *(_QWORD *)(*(_QWORD *)v116 + 32LL);
              v143[6] = *(_QWORD *)(*(_QWORD *)v116 + 24LL);
            }
            CscStoreSetInformationEntry(
              *(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL),
              0,
              0,
              0,
              (__int64)&v143[2],
              0,
              (int *)&v120);
            v57 |= v120;
          }
          goto LABEL_297;
        }
        if ( v105 != 20 )
        {
          v81 = v110;
          v82 = v105;
          if ( (v142 & 0x10) != 0 )
            NRNameFromAbsoluteName = -1073741822;
          goto LABEL_299;
        }
LABEL_365:
        v83 = v105;
        goto LABEL_366;
      }
      v84 = *((_QWORD *)&v131 + 1);
      if ( v36 == -1073741567 )
      {
        if ( (*(_DWORD *)(*((_QWORD *)&v131 + 1) + 4LL) & 0x1000000) == 0 )
        {
          v85 = *(_QWORD *)v116;
          if ( v127 )
          {
            LOBYTE(v142) = v142 | 0x10;
            CscTransitionFcbOffline(*(_QWORD *)v116, 0, 8);
            NRNameFromAbsoluteName = 0;
            goto LABEL_323;
          }
          goto LABEL_345;
        }
      }
      else if ( v36 >= 0 && (*(_DWORD *)(*((_QWORD *)&v131 + 1) + 4LL) & 0x1000000) != 0 )
      {
        if ( (int)CscStoreQueryInformationEntryEx(
                    *(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL),
                    1,
                    0,
                    0,
                    0,
                    (__int64)&v112,
                    0) < 0 )
        {
          v14 = 3377;
          goto LABEL_61;
        }
        v86 = 60449;
        v85 = *(_QWORD *)v116;
        if ( v112 || **(_WORD **)v116 != 0xEC21 )
          goto LABEL_324;
        v89 = CscEnWalkDirectoryTreeToDelete(*(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL), 0, 60449);
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
LABEL_323:
          v86 = 60449;
LABEL_324:
          v84 = *((_QWORD *)&v131 + 1);
LABEL_325:
          v87 = 1;
          v88 = (*(_BYTE *)v55 & 1) << 6;
          if ( (v142 & 0x10) != 0 )
          {
            if ( !v88 )
            {
              if ( v84 )
              {
                v91 = *(_DWORD *)(v85 + 156);
                v81 = v110;
                v82 = v105;
                if ( (v91 & 1) != 0 )
                  *(_DWORD *)(v84 + 40) = 0;
                goto LABEL_299;
              }
              goto LABEL_297;
            }
            v107[0] = 1;
            if ( *(_WORD *)v85 == 0xEC21 )
            {
              CscStoreQueryInformationEntryEx(*(_QWORD *)(v84 + 56), 1, (__int64)v143, 0, 0, (__int64)v107, 0);
              if ( (v142 & 0x10) != 0 && (v143[0] & 0x4000) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
                }
                NRNameFromAbsoluteName = -1073741637;
                v14 = 3439;
LABEL_334:
                v8 = v108;
                goto LABEL_62;
              }
              NRNameFromAbsoluteName = CscIsDirectoryRenameDeleteAllowed(v110, v143);
              if ( NRNameFromAbsoluteName < 0 )
              {
                v14 = 3448;
                goto LABEL_61;
              }
            }
            Only = CscEnDbIsCacheReadOnly(*(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL), v87, v86, v16);
            if ( (unsigned __int8)CscStoreIsEntryReadOnly() || Only )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                LOBYTE(v16) = Only != 0 ? 89 : 78;
                WPP_SF_c(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, v16);
              }
              v14 = 3471;
              NRNameFromAbsoluteName = Only != 0 ? -1073741662 : -1073741535;
              goto LABEL_334;
            }
            if ( !v107[0] )
            {
              NRNameFromAbsoluteName = -1073741567;
              v14 = 3481;
              goto LABEL_61;
            }
          }
          else if ( !v88 )
          {
            goto LABEL_297;
          }
          if ( *(_WORD *)v85 == 0xEC21 )
          {
            if ( v36 >= 0 )
            {
              v81 = v110;
              LOBYTE(v16) = 1;
              CscNotifyFullChangeDirectory(v110, 0, 0, v16);
              goto LABEL_298;
            }
            goto LABEL_297;
          }
          v82 = v105;
LABEL_399:
          v81 = v110;
          goto LABEL_299;
        }
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, v89);
          goto LABEL_323;
        }
        v84 = *((_QWORD *)&v131 + 1);
LABEL_345:
        v86 = 60449;
        goto LABEL_325;
      }
      v85 = *(_QWORD *)v116;
      goto LABEL_345;
    }
    if ( (v142 & 0x20) == 0 )
      goto LABEL_139;
    if ( *(_WORD *)v1 != 0xEC21 )
      goto LABEL_139;
    if ( (v142 & 0x10) != 0 )
      goto LABEL_139;
    LOBYTE(v9) = ((*(_BYTE *)v3 & 1) << 6) | v9;
    if ( (*(_BYTE *)v3 & 1) == 0 )
      goto LABEL_139;
    memset(v148, 0, sizeof(v148));
    NRNameFromAbsoluteName = CscStoreQueryInformationEntryEx(
                               *(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL),
                               0,
                               (__int64)v148,
                               0,
                               0,
                               (__int64)v107,
                               (__int64)&v127);
    if ( NRNameFromAbsoluteName < 0 )
    {
      v14 = 2492;
      goto LABEL_62;
    }
    if ( v107[0] || (v148[0] & 0x800000) != 0 )
    {
LABEL_139:
      v23 = v105;
      goto LABEL_140;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
    NRNameFromAbsoluteName = -1073741567;
    v14 = 2524;
    goto LABEL_62;
  }
  if ( (unsigned int)(*(_DWORD *)(v3 + 16) - 2) > 0xFFFC )
  {
    NRNameFromAbsoluteName = -1073741811;
    v14 = 1575;
    goto LABEL_6;
  }
  v15 = BYTE1(v114) & 0xFB | (*(_WORD *)(v3 + 20) != 92 ? 0 : 4);
  v123.MaximumLength = *(_WORD *)(v3 + 16);
  v123.Length = v123.MaximumLength;
  v123.Buffer = (PWSTR)(v3 + 20);
  if ( (v15 & 4) != 0 )
  {
    RxLastComponentUnicodeString(&v123, 92, &v138);
    v17 = BYTE2(v114);
    Source.MaximumLength = v138;
    Source.Length = v138;
    SourceString.Buffer = v123.Buffer;
    Source.Buffer = (PWSTR)((char *)v123.Buffer + v123.Length - (unsigned __int64)(unsigned __int16)v138);
    SourceString.MaximumLength = v123.Length - v138;
    SourceString.Length = v123.Length - v138;
    v103 = BYTE2(v114);
  }
  else
  {
    v18 = BYTE2(v114) & 0xFE | (*(_WORD *)(v3 + 20) == 58);
    v103 = v18;
    if ( *(_WORD *)(v3 + 20) == 58 )
    {
      RxRemoveDollarDataSuffix(&v123, &v111, 1, 92);
      if ( v111 )
      {
        v18 &= ~1u;
        v103 = v18;
      }
    }
    v19 = v18 & 1;
    if ( v19 )
    {
      v20 = 0;
    }
    else
    {
      RxLastComponentUnicodeString(v6, 92, &v138);
      Source.MaximumLength = v138;
      v20 = v138;
      Source.Length = v138;
      Source.Buffer = (PWSTR)(*((_QWORD *)v6 + 1) + *v6 - (unsigned __int64)(unsigned __int16)v138);
    }
    Source.Length = v20;
    SourceString.Buffer = (PWSTR)*((_QWORD *)v6 + 1);
    v21 = *v6 - v20;
    Source = v123;
    SourceString.MaximumLength = v21;
    SourceString.Length = v21;
    if ( (v142 & 0x10) != 0 && v19 )
    {
      NRNameFromAbsoluteName = -1073741108;
      v14 = 1726;
      goto LABEL_62;
    }
    v17 = v103;
  }
  *(_OWORD *)P = 0;
  NRNameFromAbsoluteName = CscPathUtilsAllocFullPathFromParentPathAndLeafFile(
                             (PUNICODE_STRING)P,
                             &SourceString,
                             &Source);
  if ( NRNameFromAbsoluteName < 0 )
  {
    v14 = 1742;
    goto LABEL_62;
  }
  NRNameFromAbsoluteName = CscExclusionListCheckRenameAndHardLinkCreate(v1, v130, P);
  if ( NRNameFromAbsoluteName == -1073739772 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, P);
    v22 = CscDclNotifyExcludedFileType(1, v130, P);
    if ( v22 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
        (unsigned int)v22);
    }
  }
  ExFreePoolWithTag(P[1], 0);
  if ( NRNameFromAbsoluteName < 0 )
  {
    v14 = 1767;
    goto LABEL_62;
  }
  v23 = v105;
  if ( v105 != 10 )
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
        (__int64)&v123);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_ZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        (unsigned int)WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
        (unsigned int)&SourceString,
        (__int64)&Source);
  }
  if ( (v142 & 0x20) == 0 )
  {
    if ( (v17 & 1) == 0 )
    {
      if ( (v15 & 4) != 0 )
        goto LABEL_149;
      if ( (int)CscStoreFindEntry(&v108, 0, &SourceString) >= 0 )
      {
        v15 |= 8u;
LABEL_149:
        memset(v148, 0, sizeof(v148));
        v35 = v108;
        v42 = &Source;
        v150 = 0;
        v149[0] = 0;
        if ( (v15 & 4) != 0 )
          v42 = &v123;
        memset(&v149[1], 0, 32);
        v43 = CscStoreFindEntry(&v118, v108, v42);
        if ( (unsigned __int8)CscStoreIsAttached(v43) )
        {
          if ( v44 < 0 )
          {
            if ( v44 != -1073741809 )
            {
              if ( v44 == -1073741772 )
              {
LABEL_170:
                if ( (v15 & 4) == 0 )
                  goto LABEL_134;
                P[0] = 0;
                if ( (int)CscStoreFindEntry(P, 0, &SourceString) < 0 )
                  goto LABEL_134;
                TunneledInfo = CscStoreGetTunneledInfo(P[0], &Source, v148);
                CscStoreDereferenceEntry(P);
                if ( TunneledInfo < 0 )
                  goto LABEL_134;
LABEL_173:
                NRNameFromAbsoluteName = CscSetInfopCanFlowRenameToServer(v110, &v142, &SourceString, &Source, 0, v148);
                if ( NRNameFromAbsoluteName < 0 )
                {
                  v14 = 2451;
                  goto LABEL_61;
                }
                goto LABEL_134;
              }
              if ( v44 != -1073741766 )
              {
                NRNameFromAbsoluteName = v44;
                v14 = 2336;
                goto LABEL_61;
              }
            }
LABEL_169:
            if ( v44 != -1073741772 )
              goto LABEL_134;
            goto LABEL_170;
          }
        }
        else if ( v44 < 0 )
        {
          goto LABEL_169;
        }
        InformationEntry = CscStoreQueryInformationEntryEx(v118, 0, (__int64)v148, (__int64)v149, 0, 0, 0);
        CscStoreDereferenceEntry(&v118);
        if ( InformationEntry < 0 )
        {
          v15 |= 1u;
          goto LABEL_134;
        }
        if ( (((unsigned __int8)v9 >> 4) & 1) == ((v150 & 0x10) != 0) )
        {
          if ( (v150 & 0x10) == 0 )
          {
            if ( (v148[0] & 0x20) == 0 && !**(_BYTE **)v124 )
            {
              NRNameFromAbsoluteName = -1073741771;
              v14 = 2388;
              goto LABEL_61;
            }
            v15 |= 1u;
            goto LABEL_173;
          }
          v14 = 2404;
        }
        else
        {
          v14 = 2369;
        }
        NRNameFromAbsoluteName = (v148[0] & 0x10) != 0 ? -1073741108 : -1073741790;
        goto LABEL_61;
      }
    }
LABEL_133:
    v35 = v108;
LABEL_134:
    if ( (v15 & 8) != 0 )
    {
      if ( (v115 & 1) != 0 )
      {
        v125 = v35;
        CscStoreReferenceEntry(v35);
      }
      CscStoreDereferenceEntry(&v108);
      v15 &= ~8u;
    }
    LODWORD(v1) = v116[0];
    goto LABEL_139;
  }
  NRNameFromAbsoluteName = CscStoreQueryInformationEntryEx(
                             *(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL),
                             0,
                             (__int64)v143,
                             0,
                             0,
                             0,
                             0);
  if ( NRNameFromAbsoluteName < 0 )
  {
    v14 = 1815;
    goto LABEL_62;
  }
  *(_QWORD *)&v140 = v110;
  NRNameFromAbsoluteName = RxSubjectContextFromRxContext(v110, (char *)&v140 + 8);
  if ( NRNameFromAbsoluteName < 0 )
  {
    v14 = 1826;
    goto LABEL_62;
  }
  if ( (v143[0] & 0x4840) != 0 )
  {
    NRNameFromAbsoluteName = -1073741811;
    v14 = 1836;
    goto LABEL_62;
  }
  if ( *(_WORD *)v1 == 0xEC22 )
  {
    v24 = HIBYTE(v114);
    if ( (v143[0] & 0x800000) != 0 )
      v24 = 1;
    HIBYTE(v114) = v24;
  }
  if ( (v17 & 1) != 0 )
    goto LABEL_133;
  v106 = 0;
  v25 = CscStoreFindEntryEx((unsigned int)&v108, 0, (unsigned int)&SourceString, 0, (__int64)&v106);
  NRNameFromAbsoluteName = v25;
  if ( v25 < 0 )
  {
    if ( (v142 & 0x10) != 0 )
    {
      if ( v25 == -1073741766 || v25 == -1073741809 || v25 == -1073741772 )
        NRNameFromAbsoluteName = -1073741766;
      v14 = 1875;
      goto LABEL_61;
    }
    if ( v25 != -1073741766 && v25 != -1073741809 && v25 != -1073741772 )
    {
      v14 = 1880;
LABEL_61:
      v8 = v108;
      goto LABEL_62;
    }
    if ( v106 )
    {
      NRNameFromAbsoluteName = -1073741766;
      v14 = 1891;
      goto LABEL_61;
    }
    NRNameFromAbsoluteName = CscStoreFindLongestPrefixEntry(&v117, v26, &SourceString, &v141);
    if ( NRNameFromAbsoluteName < 0 )
    {
      v14 = 1908;
      goto LABEL_61;
    }
    if ( (_WORD)v141 == SourceString.Length )
    {
      v8 = v117;
      v108 = v117;
      v117 = 0;
      goto LABEL_82;
    }
    v28 = SourceString.Length - v141;
    v29 = (PWSTR)((char *)SourceString.Buffer + (unsigned __int16)v141);
    LOWORD(v136) = SourceString.Length - v141;
    WORD1(v136) = SourceString.Length - v141;
    *((_QWORD *)&v136 + 1) = v29;
    if ( *v29 == 92 )
    {
      LOWORD(v136) = v28 - 2;
      *((_QWORD *)&v136 + 1) = v29 + 1;
      WORD1(v136) = v28 - 2;
    }
    v147 = 16;
    *(_QWORD *)&v145 = 0;
    *((_QWORD *)&v145 + 1) = MEMORY[0xFFFFF78000000014];
    *((_QWORD *)&v144 + 1) = MEMORY[0xFFFFF78000000014];
    *(_QWORD *)&v144 = MEMORY[0xFFFFF78000000014];
    v146 = 0;
    NRNameFromAbsoluteName = CscStoreFindOrCreateEntry(
                               (unsigned int)&v108,
                               (unsigned int)&v115,
                               v117,
                               (unsigned int)&v136,
                               524291,
                               (__int64)&v144,
                               0,
                               0);
    if ( NRNameFromAbsoluteName < 0 )
    {
      v14 = 1957;
      goto LABEL_61;
    }
    v113 = 1;
  }
  v8 = v108;
LABEL_82:
  v15 |= 8u;
  if ( (v115 & 1) != 0 )
    goto LABEL_109;
  memset(v148, 0, sizeof(v148));
  CscStoreQueryInformationEntryEx(v8, 0, (__int64)v148, 0, 0, 0, 0);
  if ( (unsigned __int8)CscStoreIsEntryDirectory(v8) && (v148[0] & 0x10) == 0 )
  {
    v30 = CscStoreFindEntry(&v118, v8, &Source);
    if ( v30 >= 0 )
    {
      NRNameFromAbsoluteName = CscStoreQueryInformationEntryEx(v118, 0, (__int64)v151, 0, 0, 0, 0);
      LODWORD(v9) = (unsigned __int8)(v9 | (32 * (CscStoreIsEntryDirectory(v118) & 1)));
      CscStoreDereferenceEntry(&v118);
      if ( NRNameFromAbsoluteName < 0 )
      {
        v14 = 2038;
        goto LABEL_62;
      }
      v31 = v151[0];
      if ( (v151[0] & 0x10) != 0 )
      {
        if ( (unsigned __int8)v9 >= 0x20u )
        {
          if ( (v142 & 0x10) == 0 )
          {
            LOBYTE(v142) = v142 | 0x10;
            CscTransitionFcbOffline(*(_QWORD *)v116, 0, 8);
            v31 = v151[0];
          }
        }
        else
        {
          v15 |= 0x80u;
        }
        if ( (((unsigned int)v9 >> 4) & 1) != (unsigned __int8)v9 >= 0x20u )
        {
          v14 = 2082;
          NRNameFromAbsoluteName = (v31 & 0x10) != 0 ? -1073741108 : -1073741790;
          goto LABEL_62;
        }
      }
      else
      {
        if ( (unsigned __int8)v9 >= 0x20u || (v9 & 0x10) != 0 )
        {
          NRNameFromAbsoluteName = -1073741771;
          v14 = 2093;
          goto LABEL_62;
        }
        v15 |= 0x40u;
      }
      goto LABEL_103;
    }
    if ( v30 == -1073741772 && (v9 & 0x10) == 0 && (int)CscStoreGetTunneledInfo(v8, &Source, v151) >= 0 )
    {
LABEL_103:
      v32 = v110;
      NRNameFromAbsoluteName = CscSetInfopCanFlowRenameToServer(v110, &v142, &SourceString, &Source, v143, v151);
      if ( NRNameFromAbsoluteName < 0 )
      {
        v14 = 2140;
        goto LABEL_62;
      }
      goto LABEL_110;
    }
LABEL_109:
    v32 = v110;
LABEL_110:
    v33 = v142;
    if ( ((unsigned __int8)v9 & (unsigned __int8)v142 & 0x10) != 0 )
    {
      NRNameFromAbsoluteName = CscIsDirectoryRenameDeleteAllowed(v32, v143);
      if ( NRNameFromAbsoluteName < 0 )
      {
        v14 = 2153;
        goto LABEL_62;
      }
      v33 = v142;
    }
    if ( (v33 & 0x10) == 0 || (v143[0] & 0x400) != 0 )
      v34 = 0;
    else
      v34 = 16;
    v15 = v34 | v15 & 0xEF;
    if ( (v33 & 0x10) != 0 )
    {
      LOBYTE(v27) = (v9 & 0x10) != 0;
      NRNameFromAbsoluteName = CscCheckTargetAccess(v32, v8, v27);
      if ( NRNameFromAbsoluteName < 0 )
      {
        v14 = 2174;
        goto LABEL_62;
      }
      v33 = v142;
    }
    NRNameFromAbsoluteName = CscStoreRenameEntry(
                               *(_QWORD *)(*((_QWORD *)&v131 + 1) + 56LL),
                               v8,
                               (unsigned int)&Source,
                               (unsigned int)CscDirectoryRenameItemValidateCallback,
                               (__int64)&v140,
                               *(_BYTE *)v3,
                               (v15 & 0x10) != 0,
                               (v33 & 0x10) != 0);
    if ( NRNameFromAbsoluteName < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
      v14 = 2202;
      goto LABEL_62;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      LOBYTE(v16) = (v15 & 0x10) != 0 ? 89 : 78;
      WPP_SF_c(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids, v16);
    }
    LOBYTE(v9) = v9 | 0x80;
    if ( (v15 & 0x10) != 0 && (int)CscStoreFindEntry(&v126, 0, v130) >= 0 )
    {
      v15 |= 0x20u;
      CscStoreSetExplicitAccessEntry(v126, 0, *(_QWORD *)(*(_QWORD *)v129 + 40LL) + 112, 2032127, 3);
    }
    goto LABEL_133;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
  NRNameFromAbsoluteName = -1073741766;
  v14 = 2012;
LABEL_62:
  if ( (v115 & 1) == 0 || NRNameFromAbsoluteName >= 0 || !v113 )
  {
LABEL_406:
    if ( v125 )
      CscStoreDereferenceEntry(&v125);
    goto LABEL_408;
  }
  if ( v125 )
  {
    CscStoreDeleteEntryPath(v117, v125);
    goto LABEL_406;
  }
  if ( v8 )
  {
    v101 = v117;
    CscStoreDeleteEntryPath(v117, v8);
    goto LABEL_409;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids);
    goto LABEL_406;
  }
LABEL_408:
  v101 = v117;
LABEL_409:
  if ( (v15 & 0x20) != 0 )
    CscStoreDereferenceEntry(&v126);
  if ( (v15 & 8) != 0 )
    CscStoreDereferenceEntry(&v108);
  if ( v101 )
  {
    if ( NRNameFromAbsoluteName >= 0 && ((v115 & 1) != 0 || (v115 & 2) != 0) )
      CscBumpGlobalNewlyCachedEpoch();
    CscStoreDereferenceEntry(&v117);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      48,
      WPP_fc552437fd36310995f06fcf4e8436b8_Traceguids,
      (unsigned int)NRNameFromAbsoluteName,
      v14);
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
