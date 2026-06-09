# FveLogMismatchedBindingInfoDatum

- ea: `0x1400b59f8`
- end: `0x1400b64e1`
- name: `FveLogMismatchedBindingInfoDatum`
- size: `2793`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x14009f0f0`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140001114`
- `0x140006730`
- `0x14000a540`
- `0x14000da14`
- `0x140017d48`
- `0x140017f08`
- `0x140018028`
- `0x140018100`
- `0x140022bf0`
- `0x140022d40`
- `0x140023040`
- `0x1400b59f8`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400b60d6`
- `ntoskrnl!EtwWrite` at `0x1400b60d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b6485`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b649e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b6485`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b649e`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5f39`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5ffe`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5f39`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5ffe`

## pseudocode

```c
__int64 __fastcall FveLogMismatchedBindingInfoDatum(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  NTSTATUS MustBe; // ebx
  __int64 v6; // r15
  __int64 v7; // r14
  void *v8; // r13
  void *v9; // rsi
  __int64 v10; // rax
  int v11; // r8d
  int v12; // r9d
  int v13; // r8d
  int v14; // r9d
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  int v18; // r8d
  int v19; // r9d
  int v20; // edx
  int v21; // eax
  int v22; // r8d
  int v23; // r9d
  ULONG v24; // r11d
  __int64 *v25; // r12
  __int64 *v26; // rax
  int v27; // ecx
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  __int64 v37; // rdx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  int v45; // ecx
  unsigned __int16 v46; // cx
  unsigned __int16 Length; // ax
  size_t v48; // rbx
  ULONG v49; // esi
  void *Pool2; // rax
  __int64 *v51; // rdx
  unsigned int v52; // esi
  unsigned __int16 v53; // ax
  size_t v54; // rbx
  ULONG v55; // r12d
  void *v56; // rax
  size_t v57; // r8
  void *v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rcx
  __int128 v62; // xmm1
  __int64 v63; // r10
  int v64; // r11d
  __int64 v65; // rdx
  __int64 v66; // r10
  __int64 v67; // r9
  int v68; // r11d
  unsigned __int16 v70; // [rsp+B0h] [rbp-80h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-78h] BYREF
  unsigned __int16 v72; // [rsp+C0h] [rbp-70h] BYREF
  unsigned __int16 v73; // [rsp+C4h] [rbp-6Ch] BYREF
  void *v74; // [rsp+C8h] [rbp-68h] BYREF
  ULONG v75; // [rsp+D0h] [rbp-60h] BYREF
  ULONG pulResult; // [rsp+D4h] [rbp-5Ch] BYREF
  __int16 v77; // [rsp+D8h] [rbp-58h] BYREF
  __int16 v78; // [rsp+DCh] [rbp-54h] BYREF
  __int16 v79; // [rsp+E0h] [rbp-50h] BYREF
  __int16 v80; // [rsp+E4h] [rbp-4Ch] BYREF
  int v81; // [rsp+E8h] [rbp-48h] BYREF
  int v82; // [rsp+ECh] [rbp-44h] BYREF
  __int64 v83; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v84; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v85; // [rsp+100h] [rbp-30h] BYREF
  int v86; // [rsp+108h] [rbp-28h] BYREF
  int v87; // [rsp+10Ch] [rbp-24h] BYREF
  int v88; // [rsp+110h] [rbp-20h] BYREF
  int v89; // [rsp+114h] [rbp-1Ch] BYREF
  __int64 v90; // [rsp+118h] [rbp-18h] BYREF
  __int64 v91; // [rsp+120h] [rbp-10h] BYREF
  __int64 v92; // [rsp+128h] [rbp-8h] BYREF
  __int64 v93; // [rsp+130h] [rbp+0h] BYREF
  __int128 v94; // [rsp+138h] [rbp+8h] BYREF
  __int128 v95; // [rsp+148h] [rbp+18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[27]; // [rsp+160h] [rbp+30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v97; // [rsp+310h] [rbp+1E0h] BYREF
  __int16 *v98; // [rsp+330h] [rbp+200h]
  __int64 v99; // [rsp+338h] [rbp+208h]
  int *v100; // [rsp+340h] [rbp+210h]
  __int64 v101; // [rsp+348h] [rbp+218h]
  __int128 *v102; // [rsp+350h] [rbp+220h]
  __int64 v103; // [rsp+358h] [rbp+228h]
  __int128 *v104; // [rsp+360h] [rbp+230h]
  __int64 v105; // [rsp+368h] [rbp+238h]
  int *v106; // [rsp+370h] [rbp+240h]
  __int64 v107; // [rsp+378h] [rbp+248h]
  __int64 *v108; // [rsp+380h] [rbp+250h]
  __int64 v109; // [rsp+388h] [rbp+258h]
  __int64 *v110; // [rsp+390h] [rbp+260h]
  __int64 v111; // [rsp+398h] [rbp+268h]
  int *v112; // [rsp+3A0h] [rbp+270h]
  __int64 v113; // [rsp+3A8h] [rbp+278h]
  int *v114; // [rsp+3B0h] [rbp+280h]
  __int64 v115; // [rsp+3B8h] [rbp+288h]
  __int64 *v116; // [rsp+3C0h] [rbp+290h]
  __int64 v117; // [rsp+3C8h] [rbp+298h]
  __int64 *v118; // [rsp+3D0h] [rbp+2A0h]
  __int64 v119; // [rsp+3D8h] [rbp+2A8h]
  __int64 *v120; // [rsp+3E0h] [rbp+2B0h]
  __int64 v121; // [rsp+3E8h] [rbp+2B8h]
  __int16 *v122; // [rsp+3F0h] [rbp+2C0h]
  __int64 v123; // [rsp+3F8h] [rbp+2C8h]
  __int16 *v124; // [rsp+400h] [rbp+2D0h]
  __int64 v125; // [rsp+408h] [rbp+2D8h]
  __int16 *v126; // [rsp+410h] [rbp+2E0h]
  __int64 v127; // [rsp+418h] [rbp+2E8h]
  ULONG *v128; // [rsp+420h] [rbp+2F0h]
  __int64 v129; // [rsp+428h] [rbp+2F8h]
  ULONG *p_pulResult; // [rsp+430h] [rbp+300h]
  __int64 v131; // [rsp+438h] [rbp+308h]
  void **v132; // [rsp+440h] [rbp+310h]
  __int64 v133; // [rsp+448h] [rbp+318h]
  __int64 *v134; // [rsp+450h] [rbp+320h]
  __int64 v135; // [rsp+458h] [rbp+328h]
  _DWORD *v136; // [rsp+460h] [rbp+330h]
  __int64 v137; // [rsp+468h] [rbp+338h]
  __int64 v138; // [rsp+470h] [rbp+340h]
  _DWORD v139[2]; // [rsp+478h] [rbp+348h] BYREF
  _DWORD *v140; // [rsp+480h] [rbp+350h]
  __int64 v141; // [rsp+488h] [rbp+358h]
  __int64 v142; // [rsp+490h] [rbp+360h]
  _DWORD v143[2]; // [rsp+498h] [rbp+368h] BYREF
  _BYTE v144[16]; // [rsp+4A0h] [rbp+370h] BYREF
  _BYTE v145[16]; // [rsp+4B0h] [rbp+380h] BYREF
  _DWORD *v146; // [rsp+4C0h] [rbp+390h]
  __int64 v147; // [rsp+4C8h] [rbp+398h]
  __int64 v148; // [rsp+4D0h] [rbp+3A0h]
  _DWORD v149[2]; // [rsp+4D8h] [rbp+3A8h] BYREF
  __int64 *v150; // [rsp+4E0h] [rbp+3B0h]
  __int64 v151; // [rsp+4E8h] [rbp+3B8h]

  memset(UserData, 0, sizeof(UserData));
  v81 = 0;
  v82 = 0;
  v91 = 0;
  MustBe = 0;
  v83 = 0;
  v6 = 0;
  v85 = 0;
  v7 = 0;
  pulResult = 0;
  v84 = 0;
  v8 = 0;
  v75 = 0;
  v9 = 0;
  v71 = 0;
  v70 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v94 = 0;
  v95 = 0;
  if ( !a1 )
    goto LABEL_66;
  v10 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL);
  v90 = v10;
  if ( !v10 )
    goto LABEL_66;
  if ( !*(_QWORD *)(v10 + 88) )
    goto LABEL_66;
  MustBe = FveDatumMustBe(a2, 31, v4, 0);
  if ( MustBe < 0 )
    goto LABEL_66;
  MustBe = FveAllPurposeArrayFromMismatchedBindingInfoByRole(a2, 36, v11, v12, (__int64)&v91);
  if ( MustBe < 0 )
    goto LABEL_66;
  MustBe = FveAllPurposeArrayFromMismatchedBindingInfoByRole(a2, 37, v13, v14, (__int64)&v83);
  if ( MustBe < 0 )
    goto LABEL_66;
  v17 = FveLabelFromMismatchedBindingInfoByRole(a2, 32, v15, v16, (__int64)&v85);
  v6 = v85;
  LOWORD(v20) = 33;
  if ( v17 < 0 )
    v6 = 0;
  v21 = FveLabelFromMismatchedBindingInfoByRole(a2, v20, v18, v19, (__int64)&v84);
  v7 = v84;
  if ( v21 < 0 )
    v7 = 0;
  MustBe = FveAllPurposeArrayFromMismatchedBindingInfoByRole(a2, 31, v22, v23, (__int64)&v71);
  if ( MustBe < 0 )
    goto LABEL_66;
  MustBe = FveDatumAllPurposeArrayGetBytesSize(v71, &v70);
  if ( MustBe < 0 )
    goto LABEL_66;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v25 = (__int64 *)(v7 + 8);
    if ( !v7 )
      v25 = &qword_140034CF0;
    v26 = (__int64 *)(v6 + 8);
    if ( !v6 )
      v26 = &qword_140034CF0;
    WPP_SF_LDIILllLLDDDDDLLSS(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned __int16 *)(a2 + 92),
      *(unsigned __int16 *)(a2 + 90),
      *(_DWORD *)(a2 + 10),
      *(_WORD *)(a2 + 46),
      *(_QWORD *)(a2 + 50),
      *(_QWORD *)(a2 + 58),
      *(_DWORD *)(a2 + 66),
      *(_DWORD *)(a2 + 70),
      *(_DWORD *)(a2 + 74),
      *(_DWORD *)(a2 + 78),
      *(_DWORD *)(a2 + 82),
      *(_WORD *)(a2 + 86),
      *(_WORD *)(a2 + 88),
      *(_WORD *)(a2 + 90),
      *(_WORD *)(a2 + 92),
      *(_WORD *)(a2 + 94),
      *(_DWORD *)(a2 + 96),
      *(_DWORD *)(a2 + 100),
      (__int64)v26,
      (__int64)v25);
    v24 = 0;
  }
  v27 = *(unsigned __int16 *)(a2 + 86);
  UserData[0].Ptr = a2 + 10;
  v28 = 4;
  v81 = v27;
  UserData[1].Ptr = a2 + 14;
  UserData[2].Ptr = a2 + 30;
  UserData[3].Ptr = a2 + 46;
  UserData[4].Ptr = a2 + 50;
  UserData[5].Ptr = a2 + 58;
  UserData[6].Ptr = a2 + 66;
  UserData[7].Ptr = a2 + 70;
  UserData[8].Ptr = a2 + 74;
  UserData[9].Ptr = a2 + 78;
  UserData[10].Ptr = a2 + 82;
  UserData[11].Ptr = (ULONGLONG)&v81;
  *(_QWORD *)&UserData[0].Size = 4;
  v29 = 64;
  *(_QWORD *)&UserData[1].Size = 16;
  *(_QWORD *)&UserData[2].Size = 16;
  *(_QWORD *)&UserData[3].Size = 4;
  *(_QWORD *)&UserData[4].Size = 8;
  *(_QWORD *)&UserData[5].Size = 8;
  *(_QWORD *)&UserData[6].Size = 4;
  *(_QWORD *)&UserData[7].Size = 4;
  *(_QWORD *)&UserData[8].Size = 4;
  *(_QWORD *)&UserData[9].Size = 4;
  *(_QWORD *)&UserData[10].Size = 4;
  *(_QWORD *)&UserData[11].Size = 4;
  v30 = v27 - 4;
  if ( !v30 )
  {
    v37 = 20;
    goto LABEL_34;
  }
  v31 = v30 - 7;
  if ( !v31 )
    goto LABEL_32;
  v32 = v31 - 1;
  if ( !v32 )
  {
LABEL_31:
    v37 = 48;
    goto LABEL_34;
  }
  v33 = v32 - 1;
  if ( !v33 )
  {
LABEL_30:
    v37 = 64;
    goto LABEL_34;
  }
  v34 = v33 - 5;
  if ( !v34 || (v35 = v34 - 21) == 0 )
  {
LABEL_32:
    v37 = 32;
    goto LABEL_34;
  }
  v36 = v35 - 1;
  if ( !v36 )
    goto LABEL_31;
  if ( v36 == 1 )
    goto LABEL_30;
  v37 = v24;
LABEL_34:
  v38 = *(unsigned __int16 *)(a2 + 88);
  UserData[12].Ptr = (ULONGLONG)&v72;
  v82 = v38;
  UserData[13].Ptr = (ULONGLONG)&v82;
  v72 = v37;
  *(_QWORD *)&UserData[12].Size = 2;
  *(_QWORD *)&UserData[13].Size = 4;
  v39 = v38 - 4;
  if ( !v39 )
  {
    v46 = 20;
    goto LABEL_47;
  }
  v40 = v39 - 7;
  if ( !v40 )
    goto LABEL_45;
  v41 = v40 - 1;
  if ( !v41 )
  {
LABEL_44:
    v46 = 48;
    goto LABEL_47;
  }
  v42 = v41 - 1;
  if ( !v42 )
  {
LABEL_43:
    v46 = 64;
    goto LABEL_47;
  }
  v43 = v42 - 5;
  if ( !v43 || (v44 = v43 - 21) == 0 )
  {
LABEL_45:
    v46 = 32;
    goto LABEL_47;
  }
  v45 = v44 - 1;
  if ( !v45 )
    goto LABEL_44;
  if ( v45 == 1 )
    goto LABEL_43;
  v46 = v24;
LABEL_47:
  v73 = v46;
  UserData[14].Ptr = (ULONGLONG)&v73;
  UserData[15].Ptr = a2 + 90;
  UserData[16].Ptr = a2 + 92;
  UserData[17].Ptr = a2 + 94;
  UserData[18].Ptr = a2 + 96;
  UserData[19].Ptr = a2 + 100;
  *(_QWORD *)&UserData[14].Size = 2;
  UserData[20].Ptr = v91 + 8;
  UserData[20].Size = (unsigned __int16)v37;
  *(_QWORD *)&UserData[15].Size = 2;
  UserData[21].Ptr = v83 + 8;
  UserData[21].Size = v46;
  *(_QWORD *)&UserData[16].Size = 2;
  *(_QWORD *)&UserData[17].Size = 2;
  *(_QWORD *)&UserData[18].Size = 4;
  *(_QWORD *)&UserData[19].Size = 4;
  UserData[20].Reserved = v24;
  UserData[21].Reserved = v24;
  if ( !v6 )
  {
    v52 = 22;
    v51 = FVE_KEYRING_MISMATCHED_BINDING_NOLABELS;
    goto LABEL_55;
  }
  Length = FveDatumUnicodeGetLength(v6, v37, 4, 64);
  MustBe = RtlULongLongToULong(2LL * Length, &pulResult);
  if ( MustBe >= 0 )
  {
    v48 = pulResult;
    v49 = pulResult + 2;
    if ( pulResult + 2 < pulResult )
    {
      MustBe = -1073741675;
      v9 = 0;
      goto LABEL_66;
    }
    Pool2 = (void *)ExAllocatePool2(64, v49, 809850438);
    v8 = Pool2;
    if ( !Pool2 )
    {
      MustBe = -1073741801;
      v9 = 0;
      goto LABEL_66;
    }
    memset(Pool2, 0, v49);
    memmove(v8, (const void *)(v6 + 8), v48);
    v24 = 0;
    UserData[22].Size = v49;
    UserData[22].Ptr = (ULONGLONG)v8;
    v51 = FVE_KEYRING_MISMATCHED_BINDING_EXPECTED_LABEL;
    UserData[22].Reserved = 0;
    v52 = 23;
LABEL_55:
    if ( v7 )
    {
      v53 = FveDatumUnicodeGetLength(v7, v51, v28, v29);
      MustBe = RtlULongLongToULong(2LL * v53, &v75);
      if ( MustBe < 0 )
      {
LABEL_65:
        v9 = v74;
        goto LABEL_66;
      }
      v54 = v75;
      v55 = v75 + 2;
      if ( v75 + 2 < v75 )
      {
LABEL_79:
        MustBe = -1073741675;
        goto LABEL_65;
      }
      v56 = (void *)ExAllocatePool2(64, v55, 809850438);
      v74 = v56;
      if ( !v56 )
      {
        MustBe = -1073741801;
        v9 = 0;
        goto LABEL_66;
      }
      memset(v56, 0, v55);
      v57 = v54;
      v58 = v74;
      memmove(v74, (const void *)(v7 + 8), v57);
      v51 = FVE_KEYRING_MISMATCHED_BINDING_EXPECTED_OBSERVED_LABELS;
      v59 = v52;
      v24 = 0;
      ++v52;
      UserData[v59].Ptr = (ULONGLONG)v58;
      UserData[v59].Size = v55;
      *(&UserData[0].Reserved + 1 * v59) = 0;
      if ( !v6 )
        v51 = (__int64 *)&FVE_KEYRING_MISMATCHED_BINDING_OBSERVED_LABEL;
    }
    v60 = v52;
    UserData[v60].Ptr = (ULONGLONG)&v70;
    *(_QWORD *)&UserData[v60].Size = 2;
    if ( v52 + 1 >= v52 )
    {
      v61 = v52 + 1;
      UserData[v61].Ptr = v71 + 8;
      UserData[v61].Size = v70;
      *(&UserData[0].Reserved + 1 * v61) = v24;
      if ( v52 + 2 >= v52 + 1 )
      {
        MustBe = EtwWrite(*(_QWORD *)(v90 + 88), (PCEVENT_DESCRIPTOR)v51, 0, v52 + 2, UserData);
        goto LABEL_65;
      }
    }
    goto LABEL_79;
  }
LABEL_66:
  if ( a2 )
  {
    v62 = *(_OWORD *)(a2 + 30);
    v94 = *(_OWORD *)(a2 + 14);
    v95 = v62;
    if ( (unsigned int)dword_140046040 > 4 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140046040, 0x400000000000LL) )
      {
        v77 = *(_WORD *)(a2 + 8);
        v98 = &v77;
        v86 = *(_DWORD *)(a2 + 10);
        v100 = &v86;
        v102 = &v94;
        v104 = &v95;
        v87 = *(_DWORD *)(a2 + 46);
        v106 = &v87;
        v92 = *(_QWORD *)(a2 + 50);
        v108 = &v92;
        v93 = *(_QWORD *)(a2 + 58);
        v110 = &v93;
        v88 = *(_DWORD *)(a2 + 66);
        v112 = &v88;
        v89 = *(_DWORD *)(a2 + 70);
        v114 = &v89;
        LODWORD(v90) = *(_DWORD *)(a2 + 74);
        v116 = &v90;
        LODWORD(v84) = *(_DWORD *)(a2 + 78);
        v118 = &v84;
        LODWORD(v85) = *(_DWORD *)(a2 + 82);
        v120 = &v85;
        v78 = *(_WORD *)(a2 + 86);
        v122 = &v78;
        v79 = *(_WORD *)(a2 + 88);
        v124 = &v79;
        v80 = *(_WORD *)(a2 + 90);
        v126 = &v80;
        LOWORD(v75) = *(_WORD *)(a2 + 92);
        v128 = &v75;
        LOWORD(pulResult) = *(_WORD *)(a2 + 94);
        p_pulResult = &pulResult;
        v99 = 2;
        v101 = 4;
        v103 = 16;
        v105 = 16;
        v107 = 4;
        v109 = 8;
        v111 = 8;
        v113 = 4;
        v115 = 4;
        v117 = 4;
        v119 = 4;
        v121 = 4;
        v123 = 2;
        v125 = 2;
        v127 = 2;
        v129 = 2;
        v131 = 2;
        v65 = v6 + 8;
        LODWORD(v74) = *(_DWORD *)(a2 + 96);
        v132 = &v74;
        LODWORD(v71) = *(_DWORD *)(a2 + 100);
        v134 = &v71;
        v136 = v139;
        v133 = 4;
        v138 = v91 + 8;
        v139[0] = v72;
        v140 = v143;
        v135 = 4;
        v142 = v83 + 8;
        v143[0] = v73;
        v137 = 2;
        v139[1] = v64;
        v141 = 2;
        v143[1] = v64;
        if ( !v6 )
          v65 = v63;
        tlgCreate1Sz_wchar_t(v144, v65);
        if ( v7 )
          v66 = v7 + 8;
        tlgCreate1Sz_wchar_t(v145, v66);
        v147 = 2;
        v148 = v67 + 8;
        v149[0] = v70;
        v146 = v149;
        v150 = &v83;
        v149[1] = v68;
        v83 = 0x1000000;
        v151 = 8;
        tlgWriteTransfer_EtwWriteTransfer(
          (__int64)&dword_140046040,
          (unsigned __int8 *)byte_14003CF0F,
          0,
          0,
          0x1Eu,
          &v97);
      }
    }
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0x30455646u);
  if ( v9 )
    ExFreePoolWithTag(v9, 0x30455646u);
  return (unsigned int)MustBe;
}

```

## disassembly

```asm
0x1400b59f8  mov     [rsp-8+arg_10], rbx
0x1400b59fd  push    rbp
0x1400b59fe  push    rsi
0x1400b59ff  push    rdi
0x1400b5a00  push    r12
0x1400b5a02  push    r13
0x1400b5a04  push    r14
0x1400b5a06  push    r15
0x1400b5a08  lea     rbp, [rsp-3D0h]
0x1400b5a10  sub     rsp, 500h
0x1400b5a17  mov     rax, cs:__security_cookie
0x1400b5a1e  xor     rax, rsp
0x1400b5a21  mov     [rbp+400h+var_40], rax
0x1400b5a28  mov     rdi, rdx
0x1400b5a2b  mov     r12, rcx
0x1400b5a2e  xor     edx, edx; Val
0x1400b5a30  lea     rcx, [rbp+400h+var_3D0]; void *
0x1400b5a34  mov     r8d, 1B0h; Size
0x1400b5a3a  call    memset
0x1400b5a3f  xor     r11d, r11d
0x1400b5a42  lea     r10, qword_140034CF0
0x1400b5a49  mov     [rbp+400h+var_448], r11d
0x1400b5a4d  xorps   xmm0, xmm0
0x1400b5a50  mov     [rbp+400h+var_444], r11d
0x1400b5a54  xorps   xmm1, xmm1
0x1400b5a57  mov     [rbp+400h+var_410], r11
0x1400b5a5b  mov     ebx, r11d
0x1400b5a5e  mov     [rbp+400h+var_440], r11
0x1400b5a62  mov     r15d, r11d
0x1400b5a65  mov     [rbp+400h+var_430], r11
0x1400b5a69  mov     r14d, r11d
0x1400b5a6c  mov     [rbp+400h+pulResult], r11d
0x1400b5a70  mov     r9d, r11d
0x1400b5a73  mov     [rbp+400h+var_438], r11
0x1400b5a77  mov     r13d, r11d
0x1400b5a7a  mov     [rbp+400h+var_460], r11d
0x1400b5a7e  mov     esi, r11d
0x1400b5a81  mov     [rbp+400h+var_478], r11
0x1400b5a85  mov     [rbp+400h+var_480], r11w
0x1400b5a8a  mov     [rbp+400h+var_470], r11w
0x1400b5a8f  mov     [rbp+400h+var_46C], r11w
0x1400b5a94  mov     [rbp+400h+var_468], r11
0x1400b5a98  movups  [rbp+400h+var_3F8], xmm0
0x1400b5a9c  movups  [rbp+400h+var_3E8], xmm1
0x1400b5aa0  test    r12, r12
0x1400b5aa3  jz      loc_1400B60F6
0x1400b5aa9  mov     rax, [r12+40h]
0x1400b5aae  mov     rax, [rax+8]
0x1400b5ab2  mov     [rbp+400h+var_418], rax
0x1400b5ab6  test    rax, rax
0x1400b5ab9  jz      loc_1400B60F6
0x1400b5abf  cmp     [rax+58h], r11
0x1400b5ac3  jz      loc_1400B60F6
0x1400b5ac9  lea     edx, [r11+1Fh]
0x1400b5acd  mov     rcx, rdi
0x1400b5ad0  call    FveDatumMustBe
0x1400b5ad5  xor     r11d, r11d
0x1400b5ad8  mov     ebx, eax
0x1400b5ada  test    eax, eax
0x1400b5adc  js      loc_1400B60EB
0x1400b5ae2  lea     rax, [rbp+400h+var_410]
0x1400b5ae6  mov     rcx, rdi
0x1400b5ae9  lea     edx, [rsi+24h]
0x1400b5aec  mov     [rsp+530h+UserData], rax
0x1400b5af1  call    FveAllPurposeArrayFromMismatchedBindingInfoByRole
0x1400b5af6  xor     r11d, r11d
0x1400b5af9  mov     ebx, eax
0x1400b5afb  test    eax, eax
0x1400b5afd  js      loc_1400B60EB
0x1400b5b03  lea     rax, [rbp+400h+var_440]
0x1400b5b07  mov     rcx, rdi
0x1400b5b0a  lea     edx, [rsi+25h]
0x1400b5b0d  mov     [rsp+530h+UserData], rax
0x1400b5b12  call    FveAllPurposeArrayFromMismatchedBindingInfoByRole
0x1400b5b17  xor     r11d, r11d
0x1400b5b1a  mov     ebx, eax
0x1400b5b1c  test    eax, eax
0x1400b5b1e  js      loc_1400B60EB
0x1400b5b24  lea     rax, [rbp+400h+var_430]
0x1400b5b28  mov     rcx, rdi
0x1400b5b2b  lea     r12d, [rsi+20h]
0x1400b5b2f  mov     [rsp+530h+UserData], rax
0x1400b5b34  movzx   edx, r12w
0x1400b5b38  call    FveLabelFromMismatchedBindingInfoByRole
0x1400b5b3d  mov     r15, [rbp+400h+var_430]
0x1400b5b41  xor     ecx, ecx
0x1400b5b43  test    eax, eax
0x1400b5b45  mov     dx, 21h ; '!'
0x1400b5b49  lea     rax, [rbp+400h+var_438]
0x1400b5b4d  cmovs   r15, rcx
0x1400b5b51  mov     [rsp+530h+UserData], rax
0x1400b5b56  mov     rcx, rdi
0x1400b5b59  call    FveLabelFromMismatchedBindingInfoByRole
0x1400b5b5e  mov     r14, [rbp+400h+var_438]
0x1400b5b62  lea     edx, [rsi+1Fh]
0x1400b5b65  xor     ecx, ecx
0x1400b5b67  test    eax, eax
0x1400b5b69  lea     rax, [rbp+400h+var_478]
0x1400b5b6d  mov     [rsp+530h+UserData], rax
0x1400b5b72  cmovs   r14, rcx
0x1400b5b76  mov     rcx, rdi
0x1400b5b79  call    FveAllPurposeArrayFromMismatchedBindingInfoByRole
0x1400b5b7e  mov     r9, [rbp+400h+var_478]
0x1400b5b82  xor     r11d, r11d
0x1400b5b85  mov     ebx, eax
0x1400b5b87  test    eax, eax
0x1400b5b89  js      loc_1400B60EF
0x1400b5b8f  lea     rdx, [rbp+400h+var_480]
0x1400b5b93  mov     rcx, r9
0x1400b5b96  call    FveDatumAllPurposeArrayGetBytesSize
0x1400b5b9b  mov     ebx, eax
0x1400b5b9d  test    eax, eax
0x1400b5b9f  js      loc_1400B60EF
0x1400b5ba5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400b5bac  lea     rax, WPP_GLOBAL_Control
0x1400b5bb3  cmp     rbx, rax
0x1400b5bb6  jz      loc_1400B5C9B
0x1400b5bbc  test    dword ptr [rbx+2Ch], 8000h
0x1400b5bc3  jz      loc_1400B5C9B
0x1400b5bc9  cmp     byte ptr [rbx+29h], 5
0x1400b5bcd  jb      loc_1400B5C9B
0x1400b5bd3  lea     r12, [r14+8]
0x1400b5bd7  test    r14, r14
0x1400b5bda  jnz     short loc_1400B5BE3
0x1400b5bdc  lea     r12, qword_140034CF0
0x1400b5be3  lea     rax, [r15+8]
0x1400b5be7  test    r15, r15
0x1400b5bea  jnz     short loc_1400B5BF3
0x1400b5bec  lea     rax, qword_140034CF0
0x1400b5bf3  movzx   ecx, word ptr [rdi+5Eh]
0x1400b5bf7  movzx   r9d, word ptr [rdi+58h]
0x1400b5bfc  movzx   edx, word ptr [rdi+5Ch]
0x1400b5c00  movzx   r8d, word ptr [rdi+5Ah]
0x1400b5c05  movzx   r10d, word ptr [rdi+56h]
0x1400b5c0a  movzx   r11d, word ptr [rdi+2Eh]
0x1400b5c0f  mov     [rsp+530h+var_490], r12
0x1400b5c17  mov     [rsp+530h+var_498], rax
0x1400b5c1f  mov     eax, [rdi+64h]
0x1400b5c22  mov     [rsp+530h+var_4A0], eax
0x1400b5c29  mov     eax, [rdi+60h]
0x1400b5c2c  mov     [rsp+530h+var_4A8], eax
0x1400b5c33  mov     eax, [rdi+52h]
0x1400b5c36  mov     [rsp+530h+var_4B0], ecx
0x1400b5c3d  mov     rcx, [rbx+18h]
0x1400b5c41  mov     [rsp+530h+var_4B8], edx
0x1400b5c45  mov     [rsp+530h+var_4C0], r8d
0x1400b5c4a  mov     [rsp+530h+var_4C8], r9d
0x1400b5c4f  mov     r9d, [rdi+0Ah]
0x1400b5c53  mov     [rsp+530h+var_4D0], r10d
0x1400b5c58  mov     [rsp+530h+var_4D8], eax
0x1400b5c5c  mov     eax, [rdi+4Eh]
0x1400b5c5f  mov     [rsp+530h+var_4E0], eax
0x1400b5c63  mov     eax, [rdi+4Ah]
0x1400b5c66  mov     [rsp+530h+var_4E8], eax
0x1400b5c6a  mov     eax, [rdi+46h]
0x1400b5c6d  mov     [rsp+530h+var_4F0], eax
0x1400b5c71  mov     eax, [rdi+42h]
0x1400b5c74  mov     [rsp+530h+var_4F8], eax
0x1400b5c78  mov     rax, [rdi+3Ah]
0x1400b5c7c  mov     [rsp+530h+var_500], rax
0x1400b5c81  mov     rax, [rdi+32h]
0x1400b5c85  mov     [rsp+530h+var_508], rax
0x1400b5c8a  mov     dword ptr [rsp+530h+UserData], r11d
0x1400b5c8f  call    WPP_SF_LDIILllLLDDDDDLLSS
0x1400b5c94  xor     r11d, r11d
0x1400b5c97  lea     r12d, [r11+20h]
0x1400b5c9b  movzx   ecx, word ptr [rdi+56h]
0x1400b5c9f  lea     rax, [rdi+0Ah]
0x1400b5ca3  mov     [rbp+400h+var_3D0.Ptr], rax
0x1400b5ca7  mov     r8d, 4
0x1400b5cad  lea     rax, [rdi+0Eh]
0x1400b5cb1  mov     [rbp+400h+var_448], ecx
0x1400b5cb4  mov     [rbp+400h+var_3C0], rax
0x1400b5cb8  lea     rax, [rdi+1Eh]
0x1400b5cbc  mov     [rbp+400h+var_3B0], rax
0x1400b5cc0  lea     rax, [rdi+2Eh]
0x1400b5cc4  mov     [rbp+400h+var_3A0], rax
0x1400b5cc8  lea     rax, [rdi+32h]
0x1400b5ccc  mov     [rbp+400h+var_390], rax
0x1400b5cd0  lea     rax, [rdi+3Ah]
0x1400b5cd4  mov     [rbp+400h+var_380], rax
0x1400b5cdb  lea     rax, [rdi+42h]
0x1400b5cdf  mov     [rbp+400h+var_370], rax
0x1400b5ce6  lea     rax, [rdi+46h]
0x1400b5cea  mov     [rbp+400h+var_360], rax
0x1400b5cf1  lea     rax, [rdi+4Ah]
0x1400b5cf5  mov     [rbp+400h+var_350], rax
0x1400b5cfc  lea     rax, [rdi+4Eh]
0x1400b5d00  mov     [rbp+400h+var_340], rax
0x1400b5d07  lea     rax, [rdi+52h]
0x1400b5d0b  mov     [rbp+400h+var_330], rax
0x1400b5d12  lea     rax, [rbp+400h+var_448]
0x1400b5d16  mov     [rbp+400h+var_320], rax
0x1400b5d1d  lea     eax, [r8+10h]
0x1400b5d21  mov     qword ptr [rbp+400h+var_3D0.Size], r8
0x1400b5d25  lea     r9d, [r8+3Ch]
0x1400b5d29  mov     [rbp+400h+var_3B8], 10h
0x1400b5d31  lea     r10d, [r8+2Ch]
0x1400b5d35  mov     [rbp+400h+var_3A8], 10h
0x1400b5d3d  mov     [rbp+400h+var_398], r8
0x1400b5d41  mov     [rbp+400h+var_388], 8
0x1400b5d49  mov     [rbp+400h+var_378], 8
0x1400b5d54  mov     [rbp+400h+var_368], r8
0x1400b5d5b  mov     [rbp+400h+var_358], r8
0x1400b5d62  mov     [rbp+400h+var_348], r8
0x1400b5d69  mov     [rbp+400h+var_338], r8
0x1400b5d70  mov     [rbp+400h+var_328], r8
0x1400b5d77  mov     [rbp+400h+var_318], r8
0x1400b5d7e  sub     ecx, r8d
0x1400b5d81  jz      short loc_1400B5DBD
0x1400b5d83  sub     ecx, 7
0x1400b5d86  jz      short loc_1400B5DB7
0x1400b5d88  sub     ecx, 1
0x1400b5d8b  jz      short loc_1400B5DB1
0x1400b5d8d  sub     ecx, 1
0x1400b5d90  jz      short loc_1400B5DAB
0x1400b5d92  sub     ecx, 5
0x1400b5d95  jz      short loc_1400B5DB7
0x1400b5d97  sub     ecx, 15h
0x1400b5d9a  jz      short loc_1400B5DB7
0x1400b5d9c  sub     ecx, 1
0x1400b5d9f  jz      short loc_1400B5DB1
0x1400b5da1  cmp     ecx, 1
0x1400b5da4  jz      short loc_1400B5DAB
0x1400b5da6  mov     edx, r11d
0x1400b5da9  jmp     short loc_1400B5DC0
0x1400b5dab  movzx   edx, r9w
0x1400b5daf  jmp     short loc_1400B5DC0
0x1400b5db1  movzx   edx, r10w
0x1400b5db5  jmp     short loc_1400B5DC0
0x1400b5db7  movzx   edx, r12w
0x1400b5dbb  jmp     short loc_1400B5DC0
0x1400b5dbd  movzx   edx, ax
0x1400b5dc0  movzx   ecx, word ptr [rdi+58h]
0x1400b5dc4  lea     rax, [rbp+400h+var_470]
0x1400b5dc8  mov     [rbp+400h+var_310], rax
0x1400b5dcf  lea     rax, [rbp+400h+var_444]
0x1400b5dd3  mov     [rbp+400h+var_444], ecx
0x1400b5dd6  mov     [rbp+400h+var_300], rax
0x1400b5ddd  mov     [rbp+400h+var_470], dx
0x1400b5de1  mov     [rbp+400h+var_308], 2
0x1400b5dec  mov     [rbp+400h+var_2F8], r8
0x1400b5df3  sub     ecx, r8d
0x1400b5df6  jz      short loc_1400B5E32
0x1400b5df8  sub     ecx, 7
0x1400b5dfb  jz      short loc_1400B5E2C
0x1400b5dfd  sub     ecx, 1
0x1400b5e00  jz      short loc_1400B5E26
0x1400b5e02  sub     ecx, 1
0x1400b5e05  jz      short loc_1400B5E20
0x1400b5e07  sub     ecx, 5
0x1400b5e0a  jz      short loc_1400B5E2C
0x1400b5e0c  sub     ecx, 15h
0x1400b5e0f  jz      short loc_1400B5E2C
0x1400b5e11  sub     ecx, 1
0x1400b5e14  jz      short loc_1400B5E26
0x1400b5e16  cmp     ecx, 1
0x1400b5e19  jz      short loc_1400B5E20
0x1400b5e1b  mov     ecx, r11d
0x1400b5e1e  jmp     short loc_1400B5E37
0x1400b5e20  movzx   ecx, r9w
0x1400b5e24  jmp     short loc_1400B5E37
0x1400b5e26  movzx   ecx, r10w
0x1400b5e2a  jmp     short loc_1400B5E37
0x1400b5e2c  movzx   ecx, r12w
0x1400b5e30  jmp     short loc_1400B5E37
0x1400b5e32  mov     ecx, 14h
0x1400b5e37  lea     rax, [rbp+400h+var_46C]
0x1400b5e3b  mov     [rbp+400h+var_46C], cx
0x1400b5e3f  mov     [rbp+400h+var_2F0], rax
0x1400b5e46  lea     rax, [rdi+5Ah]
0x1400b5e4a  mov     [rbp+400h+var_2E0], rax
0x1400b5e51  lea     rax, [rdi+5Ch]
0x1400b5e55  mov     [rbp+400h+var_2D0], rax
0x1400b5e5c  lea     rax, [rdi+5Eh]
0x1400b5e60  mov     [rbp+400h+var_2C0], rax
0x1400b5e67  lea     rax, [rdi+60h]
0x1400b5e6b  mov     [rbp+400h+var_2B0], rax
0x1400b5e72  lea     rax, [rdi+64h]
0x1400b5e76  mov     [rbp+400h+var_2A0], rax
0x1400b5e7d  mov     rax, [rbp+400h+var_410]
0x1400b5e81  add     rax, 8
0x1400b5e85  mov     [rbp+400h+var_2E8], 2
0x1400b5e90  mov     [rbp+400h+var_290], rax
0x1400b5e97  movzx   eax, dx
0x1400b5e9a  mov     [rbp+400h+var_288], eax
0x1400b5ea0  mov     rax, [rbp+400h+var_440]
0x1400b5ea4  add     rax, 8
0x1400b5ea8  mov     [rbp+400h+var_2D8], 2
0x1400b5eb3  mov     [rbp+400h+var_280], rax
0x1400b5eba  movzx   eax, cx
0x1400b5ebd  mov     [rbp+400h+var_278], eax
0x1400b5ec3  mov     [rbp+400h+var_2C8], 2
0x1400b5ece  mov     [rbp+400h+var_2B8], 2
0x1400b5ed9  mov     [rbp+400h+var_2A8], r8
0x1400b5ee0  mov     [rbp+400h+var_298], r8
0x1400b5ee7  mov     [rbp+400h+var_284], r11d
0x1400b5eee  mov     [rbp+400h+var_274], r11d
0x1400b5ef5  test    r15, r15
0x1400b5ef8  jz      loc_1400B5FAA
  ... truncated ...
```
