# FveLogMismatchedBindingInfoDatum

- ea: `0x1400b4720`
- end: `0x1400b51eb`
- name: `FveLogMismatchedBindingInfoDatum`
- size: `2763`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x14009e1b0`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x14000110c`
- `0x140006670`
- `0x14000a480`
- `0x14000d884`
- `0x140017338`
- `0x1400174f8`
- `0x140017618`
- `0x1400176f0`
- `0x1400218c0`
- `0x140021a00`
- `0x140021d00`
- `0x1400b4720`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400b4dfe`
- `ntoskrnl!EtwWrite` at `0x1400b4dfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b518f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b51a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b518f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b51a8`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4c61`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4d26`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4c61`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4d26`

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
      v25 = &qword_140033D40;
    v26 = (__int64 *)(v6 + 8);
    if ( !v6 )
      v26 = &qword_140033D40;
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
    if ( (unsigned int)dword_140045040 > 4 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
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
          (__int64)&dword_140045040,
          (unsigned __int8 *)byte_14003BE8F,
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
0x1400b4720  mov     [rsp-8+arg_10], rbx
0x1400b4725  push    rbp
0x1400b4726  push    rsi
0x1400b4727  push    rdi
0x1400b4728  push    r12
0x1400b472a  push    r13
0x1400b472c  push    r14
0x1400b472e  push    r15
0x1400b4730  lea     rbp, [rsp-3D0h]
0x1400b4738  sub     rsp, 500h
0x1400b473f  mov     rax, cs:__security_cookie
0x1400b4746  xor     rax, rsp
0x1400b4749  mov     [rbp+400h+var_40], rax
0x1400b4750  mov     rdi, rdx
0x1400b4753  mov     r12, rcx
0x1400b4756  xor     edx, edx; Val
0x1400b4758  lea     rcx, [rbp+400h+var_3D0]; void *
0x1400b475c  mov     r8d, 1B0h; Size
0x1400b4762  call    memset
0x1400b4767  xor     r11d, r11d
0x1400b476a  lea     r10, qword_140033D40
0x1400b4771  mov     [rbp+400h+var_448], r11d
0x1400b4775  xorps   xmm0, xmm0
0x1400b4778  mov     [rbp+400h+var_444], r11d
0x1400b477c  xorps   xmm1, xmm1
0x1400b477f  mov     [rbp+400h+var_410], r11
0x1400b4783  mov     ebx, r11d
0x1400b4786  mov     [rbp+400h+var_440], r11
0x1400b478a  mov     r15d, r11d
0x1400b478d  mov     [rbp+400h+var_430], r11
0x1400b4791  mov     r14d, r11d
0x1400b4794  mov     [rbp+400h+pulResult], r11d
0x1400b4798  mov     r9d, r11d
0x1400b479b  mov     [rbp+400h+var_438], r11
0x1400b479f  mov     r13d, r11d
0x1400b47a2  mov     [rbp+400h+var_460], r11d
0x1400b47a6  mov     esi, r11d
0x1400b47a9  mov     [rbp+400h+var_478], r11
0x1400b47ad  mov     [rbp+400h+var_480], r11w
0x1400b47b2  mov     [rbp+400h+var_470], r11w
0x1400b47b7  mov     [rbp+400h+var_46C], r11w
0x1400b47bc  mov     [rbp+400h+var_468], r11
0x1400b47c0  movups  [rbp+400h+var_3F8], xmm0
0x1400b47c4  movups  [rbp+400h+var_3E8], xmm1
0x1400b47c8  test    r12, r12
0x1400b47cb  jz      loc_1400B4E1E
0x1400b47d1  mov     rax, [r12+40h]
0x1400b47d6  mov     rax, [rax+8]
0x1400b47da  mov     [rbp+400h+var_418], rax
0x1400b47de  test    rax, rax
0x1400b47e1  jz      loc_1400B4E1E
0x1400b47e7  cmp     [rax+58h], r11
0x1400b47eb  jz      loc_1400B4E1E
0x1400b47f1  lea     edx, [r11+1Fh]
0x1400b47f5  mov     rcx, rdi
0x1400b47f8  call    FveDatumMustBe
0x1400b47fd  xor     r11d, r11d
0x1400b4800  mov     ebx, eax
0x1400b4802  test    eax, eax
0x1400b4804  js      loc_1400B4E13
0x1400b480a  lea     rax, [rbp+400h+var_410]
0x1400b480e  mov     rcx, rdi
0x1400b4811  lea     edx, [rsi+24h]
0x1400b4814  mov     [rsp+530h+UserData], rax
0x1400b4819  call    FveAllPurposeArrayFromMismatchedBindingInfoByRole
0x1400b481e  xor     r11d, r11d
0x1400b4821  mov     ebx, eax
0x1400b4823  test    eax, eax
0x1400b4825  js      loc_1400B4E13
0x1400b482b  lea     rax, [rbp+400h+var_440]
0x1400b482f  mov     rcx, rdi
0x1400b4832  lea     edx, [rsi+25h]
0x1400b4835  mov     [rsp+530h+UserData], rax
0x1400b483a  call    FveAllPurposeArrayFromMismatchedBindingInfoByRole
0x1400b483f  xor     r11d, r11d
0x1400b4842  mov     ebx, eax
0x1400b4844  test    eax, eax
0x1400b4846  js      loc_1400B4E13
0x1400b484c  lea     rax, [rbp+400h+var_430]
0x1400b4850  mov     rcx, rdi
0x1400b4853  lea     r12d, [rsi+20h]
0x1400b4857  mov     [rsp+530h+UserData], rax
0x1400b485c  movzx   edx, r12w
0x1400b4860  call    FveLabelFromMismatchedBindingInfoByRole
0x1400b4865  mov     r15, [rbp+400h+var_430]
0x1400b4869  xor     ecx, ecx
0x1400b486b  test    eax, eax
0x1400b486d  mov     dx, 21h ; '!'
0x1400b4871  lea     rax, [rbp+400h+var_438]
0x1400b4875  cmovs   r15, rcx
0x1400b4879  mov     [rsp+530h+UserData], rax
0x1400b487e  mov     rcx, rdi
0x1400b4881  call    FveLabelFromMismatchedBindingInfoByRole
0x1400b4886  mov     r14, [rbp+400h+var_438]
0x1400b488a  lea     edx, [rsi+1Fh]
0x1400b488d  xor     ecx, ecx
0x1400b488f  test    eax, eax
0x1400b4891  lea     rax, [rbp+400h+var_478]
0x1400b4895  mov     [rsp+530h+UserData], rax
0x1400b489a  cmovs   r14, rcx
0x1400b489e  mov     rcx, rdi
0x1400b48a1  call    FveAllPurposeArrayFromMismatchedBindingInfoByRole
0x1400b48a6  mov     r9, [rbp+400h+var_478]
0x1400b48aa  xor     r11d, r11d
0x1400b48ad  mov     ebx, eax
0x1400b48af  test    eax, eax
0x1400b48b1  js      loc_1400B4E17
0x1400b48b7  lea     rdx, [rbp+400h+var_480]
0x1400b48bb  mov     rcx, r9
0x1400b48be  call    FveDatumAllPurposeArrayGetBytesSize
0x1400b48c3  mov     ebx, eax
0x1400b48c5  test    eax, eax
0x1400b48c7  js      loc_1400B4E17
0x1400b48cd  mov     rbx, cs:WPP_GLOBAL_Control
0x1400b48d4  lea     rax, WPP_GLOBAL_Control
0x1400b48db  cmp     rbx, rax
0x1400b48de  jz      loc_1400B49C3
0x1400b48e4  test    dword ptr [rbx+2Ch], 8000h
0x1400b48eb  jz      loc_1400B49C3
0x1400b48f1  cmp     byte ptr [rbx+29h], 5
0x1400b48f5  jb      loc_1400B49C3
0x1400b48fb  lea     r12, [r14+8]
0x1400b48ff  test    r14, r14
0x1400b4902  jnz     short loc_1400B490B
0x1400b4904  lea     r12, qword_140033D40
0x1400b490b  lea     rax, [r15+8]
0x1400b490f  test    r15, r15
0x1400b4912  jnz     short loc_1400B491B
0x1400b4914  lea     rax, qword_140033D40
0x1400b491b  movzx   ecx, word ptr [rdi+5Eh]
0x1400b491f  movzx   r9d, word ptr [rdi+58h]
0x1400b4924  movzx   edx, word ptr [rdi+5Ch]
0x1400b4928  movzx   r8d, word ptr [rdi+5Ah]
0x1400b492d  movzx   r10d, word ptr [rdi+56h]
0x1400b4932  movzx   r11d, word ptr [rdi+2Eh]
0x1400b4937  mov     [rsp+530h+var_490], r12
0x1400b493f  mov     [rsp+530h+var_498], rax
0x1400b4947  mov     eax, [rdi+64h]
0x1400b494a  mov     [rsp+530h+var_4A0], eax
0x1400b4951  mov     eax, [rdi+60h]
0x1400b4954  mov     [rsp+530h+var_4A8], eax
0x1400b495b  mov     eax, [rdi+52h]
0x1400b495e  mov     [rsp+530h+var_4B0], ecx
0x1400b4965  mov     rcx, [rbx+18h]
0x1400b4969  mov     [rsp+530h+var_4B8], edx
0x1400b496d  mov     [rsp+530h+var_4C0], r8d
0x1400b4972  mov     [rsp+530h+var_4C8], r9d
0x1400b4977  mov     r9d, [rdi+0Ah]
0x1400b497b  mov     [rsp+530h+var_4D0], r10d
0x1400b4980  mov     [rsp+530h+var_4D8], eax
0x1400b4984  mov     eax, [rdi+4Eh]
0x1400b4987  mov     [rsp+530h+var_4E0], eax
0x1400b498b  mov     eax, [rdi+4Ah]
0x1400b498e  mov     [rsp+530h+var_4E8], eax
0x1400b4992  mov     eax, [rdi+46h]
0x1400b4995  mov     [rsp+530h+var_4F0], eax
0x1400b4999  mov     eax, [rdi+42h]
0x1400b499c  mov     [rsp+530h+var_4F8], eax
0x1400b49a0  mov     rax, [rdi+3Ah]
0x1400b49a4  mov     [rsp+530h+var_500], rax
0x1400b49a9  mov     rax, [rdi+32h]
0x1400b49ad  mov     [rsp+530h+var_508], rax
0x1400b49b2  mov     dword ptr [rsp+530h+UserData], r11d
0x1400b49b7  call    WPP_SF_LDIILllLLDDDDDLLSS
0x1400b49bc  xor     r11d, r11d
0x1400b49bf  lea     r12d, [r11+20h]
0x1400b49c3  movzx   ecx, word ptr [rdi+56h]
0x1400b49c7  lea     rax, [rdi+0Ah]
0x1400b49cb  mov     [rbp+400h+var_3D0.Ptr], rax
0x1400b49cf  mov     r8d, 4
0x1400b49d5  lea     rax, [rdi+0Eh]
0x1400b49d9  mov     [rbp+400h+var_448], ecx
0x1400b49dc  mov     [rbp+400h+var_3C0], rax
0x1400b49e0  lea     rax, [rdi+1Eh]
0x1400b49e4  mov     [rbp+400h+var_3B0], rax
0x1400b49e8  lea     rax, [rdi+2Eh]
0x1400b49ec  mov     [rbp+400h+var_3A0], rax
0x1400b49f0  lea     rax, [rdi+32h]
0x1400b49f4  mov     [rbp+400h+var_390], rax
0x1400b49f8  lea     rax, [rdi+3Ah]
0x1400b49fc  mov     [rbp+400h+var_380], rax
0x1400b4a03  lea     rax, [rdi+42h]
0x1400b4a07  mov     [rbp+400h+var_370], rax
0x1400b4a0e  lea     rax, [rdi+46h]
0x1400b4a12  mov     [rbp+400h+var_360], rax
0x1400b4a19  lea     rax, [rdi+4Ah]
0x1400b4a1d  mov     [rbp+400h+var_350], rax
0x1400b4a24  lea     rax, [rdi+4Eh]
0x1400b4a28  mov     [rbp+400h+var_340], rax
0x1400b4a2f  lea     rax, [rdi+52h]
0x1400b4a33  mov     [rbp+400h+var_330], rax
0x1400b4a3a  lea     rax, [rbp+400h+var_448]
0x1400b4a3e  mov     [rbp+400h+var_320], rax
0x1400b4a45  lea     eax, [r8+10h]
0x1400b4a49  mov     qword ptr [rbp+400h+var_3D0.Size], r8
0x1400b4a4d  lea     r9d, [r8+3Ch]
0x1400b4a51  mov     [rbp+400h+var_3B8], 10h
0x1400b4a59  lea     r10d, [r8+2Ch]
0x1400b4a5d  mov     [rbp+400h+var_3A8], 10h
0x1400b4a65  mov     [rbp+400h+var_398], r8
0x1400b4a69  mov     [rbp+400h+var_388], 8
0x1400b4a71  mov     [rbp+400h+var_378], 8
0x1400b4a7c  mov     [rbp+400h+var_368], r8
0x1400b4a83  mov     [rbp+400h+var_358], r8
0x1400b4a8a  mov     [rbp+400h+var_348], r8
0x1400b4a91  mov     [rbp+400h+var_338], r8
0x1400b4a98  mov     [rbp+400h+var_328], r8
0x1400b4a9f  mov     [rbp+400h+var_318], r8
0x1400b4aa6  sub     ecx, r8d
0x1400b4aa9  jz      short loc_1400B4AE5
0x1400b4aab  sub     ecx, 7
0x1400b4aae  jz      short loc_1400B4ADF
0x1400b4ab0  sub     ecx, 1
0x1400b4ab3  jz      short loc_1400B4AD9
0x1400b4ab5  sub     ecx, 1
0x1400b4ab8  jz      short loc_1400B4AD3
0x1400b4aba  sub     ecx, 5
0x1400b4abd  jz      short loc_1400B4ADF
0x1400b4abf  sub     ecx, 15h
0x1400b4ac2  jz      short loc_1400B4ADF
0x1400b4ac4  sub     ecx, 1
0x1400b4ac7  jz      short loc_1400B4AD9
0x1400b4ac9  cmp     ecx, 1
0x1400b4acc  jz      short loc_1400B4AD3
0x1400b4ace  mov     edx, r11d
0x1400b4ad1  jmp     short loc_1400B4AE8
0x1400b4ad3  movzx   edx, r9w
0x1400b4ad7  jmp     short loc_1400B4AE8
0x1400b4ad9  movzx   edx, r10w
0x1400b4add  jmp     short loc_1400B4AE8
0x1400b4adf  movzx   edx, r12w
0x1400b4ae3  jmp     short loc_1400B4AE8
0x1400b4ae5  movzx   edx, ax
0x1400b4ae8  movzx   ecx, word ptr [rdi+58h]
0x1400b4aec  lea     rax, [rbp+400h+var_470]
0x1400b4af0  mov     [rbp+400h+var_310], rax
0x1400b4af7  lea     rax, [rbp+400h+var_444]
0x1400b4afb  mov     [rbp+400h+var_444], ecx
0x1400b4afe  mov     [rbp+400h+var_300], rax
0x1400b4b05  mov     [rbp+400h+var_470], dx
0x1400b4b09  mov     [rbp+400h+var_308], 2
0x1400b4b14  mov     [rbp+400h+var_2F8], r8
0x1400b4b1b  sub     ecx, r8d
0x1400b4b1e  jz      short loc_1400B4B5A
0x1400b4b20  sub     ecx, 7
0x1400b4b23  jz      short loc_1400B4B54
0x1400b4b25  sub     ecx, 1
0x1400b4b28  jz      short loc_1400B4B4E
0x1400b4b2a  sub     ecx, 1
0x1400b4b2d  jz      short loc_1400B4B48
0x1400b4b2f  sub     ecx, 5
0x1400b4b32  jz      short loc_1400B4B54
0x1400b4b34  sub     ecx, 15h
0x1400b4b37  jz      short loc_1400B4B54
0x1400b4b39  sub     ecx, 1
0x1400b4b3c  jz      short loc_1400B4B4E
0x1400b4b3e  cmp     ecx, 1
0x1400b4b41  jz      short loc_1400B4B48
0x1400b4b43  mov     ecx, r11d
0x1400b4b46  jmp     short loc_1400B4B5F
0x1400b4b48  movzx   ecx, r9w
0x1400b4b4c  jmp     short loc_1400B4B5F
0x1400b4b4e  movzx   ecx, r10w
0x1400b4b52  jmp     short loc_1400B4B5F
0x1400b4b54  movzx   ecx, r12w
0x1400b4b58  jmp     short loc_1400B4B5F
0x1400b4b5a  mov     ecx, 14h
0x1400b4b5f  lea     rax, [rbp+400h+var_46C]
0x1400b4b63  mov     [rbp+400h+var_46C], cx
0x1400b4b67  mov     [rbp+400h+var_2F0], rax
0x1400b4b6e  lea     rax, [rdi+5Ah]
0x1400b4b72  mov     [rbp+400h+var_2E0], rax
0x1400b4b79  lea     rax, [rdi+5Ch]
0x1400b4b7d  mov     [rbp+400h+var_2D0], rax
0x1400b4b84  lea     rax, [rdi+5Eh]
0x1400b4b88  mov     [rbp+400h+var_2C0], rax
0x1400b4b8f  lea     rax, [rdi+60h]
0x1400b4b93  mov     [rbp+400h+var_2B0], rax
0x1400b4b9a  lea     rax, [rdi+64h]
0x1400b4b9e  mov     [rbp+400h+var_2A0], rax
0x1400b4ba5  mov     rax, [rbp+400h+var_410]
0x1400b4ba9  add     rax, 8
0x1400b4bad  mov     [rbp+400h+var_2E8], 2
0x1400b4bb8  mov     [rbp+400h+var_290], rax
0x1400b4bbf  movzx   eax, dx
0x1400b4bc2  mov     [rbp+400h+var_288], eax
0x1400b4bc8  mov     rax, [rbp+400h+var_440]
0x1400b4bcc  add     rax, 8
0x1400b4bd0  mov     [rbp+400h+var_2D8], 2
0x1400b4bdb  mov     [rbp+400h+var_280], rax
0x1400b4be2  movzx   eax, cx
0x1400b4be5  mov     [rbp+400h+var_278], eax
0x1400b4beb  mov     [rbp+400h+var_2C8], 2
0x1400b4bf6  mov     [rbp+400h+var_2B8], 2
0x1400b4c01  mov     [rbp+400h+var_2A8], r8
0x1400b4c08  mov     [rbp+400h+var_298], r8
0x1400b4c0f  mov     [rbp+400h+var_284], r11d
0x1400b4c16  mov     [rbp+400h+var_274], r11d
0x1400b4c1d  test    r15, r15
0x1400b4c20  jz      loc_1400B4CD2
  ... truncated ...
```
