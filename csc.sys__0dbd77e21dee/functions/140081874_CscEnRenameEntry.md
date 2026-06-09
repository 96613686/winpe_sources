# CscEnRenameEntry

- ea: `0x140081874`
- end: `0x1400829da`
- name: `CscEnRenameEntry`
- size: `4454`
- prototype: ``
- caller_count: `3`
- callee_count: `50`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14005b074`
- `0x14005d3d0`
- `0x1400817ec`

## callees

- `0x1400052c0`
- `0x140005390`
- `0x140007420`
- `0x1400082c0`
- `0x14000a64c`
- `0x140010b00`
- `0x140010f6c`
- `0x140012c60`
- `0x140012d20`
- `0x140016634`
- `0x1400169d4`
- `0x140016a48`
- `0x140017908`
- `0x140018260`
- `0x140018930`
- `0x140018bec`
- `0x14001a69c`
- `0x14001d854`
- `0x140025e98`
- `0x1400266b8`
- `0x140026874`
- `0x140026b58`
- `0x140026be4`
- `0x140026d34`
- `0x140027d90`
- `0x14002992c`
- `0x140029cf0`
- `0x14002a780`
- `0x14002b8cc`
- `0x14002f010`
- `0x14002f440`
- `0x140046aac`
- `0x1400470ec`
- `0x140047980`
- `0x140048450`
- `0x140049b80`
- `0x14004a778`
- `0x14005c34c`
- `0x14005cca8`
- `0x14005d1a0`
- `0x14005d268`
- `0x14005ffa8`
- `0x140060154`
- `0x1400689ec`
- `0x14006bc40`
- `0x14007d934`
- `0x140081874`
- `0x1400829e0`
- `0x14008acf4`
- `0x14008c4d0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140082802`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140082802`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140081ffc`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140081ffc`

## pseudocode

```c
__int64 __fastcall CscEnRenameEntry(
        __int64 a1,
        _QWORD *a2,
        unsigned __int16 *a3,
        __int64 (__fastcall *a4)(_QWORD, _QWORD, _QWORD),
        __int64 a5,
        char a6,
        bool *a7)
{
  int v7; // eax
  char v10; // r14
  _DWORD *v11; // rbx
  int v12; // r8d
  int EntryFullPath; // ebx
  int v14; // edi
  unsigned __int64 v15; // rax
  _WORD *v16; // rcx
  _WORD *v17; // rdx
  int v18; // r15d
  char v19; // r14
  unsigned __int8 v20; // r12
  _QWORD *v21; // rdi
  int Entry; // eax
  int v23; // eax
  __int64 v24; // r15
  char v25; // r14
  __int16 v26; // ax
  char v27; // di
  __int64 v28; // rdx
  int v29; // ecx
  int v30; // ecx
  int v31; // r9d
  __m128i v32; // xmm2
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  unsigned int v36; // ecx
  unsigned int v37; // edi
  __int128 v38; // xmm1
  __int64 v39; // xmm1_8
  __int128 v40; // xmm1
  _QWORD *v41; // rdi
  int v42; // r8d
  __int64 v43; // rdx
  __int64 v44; // r8
  __int16 v45; // ax
  char v46; // r14
  char v47; // al
  int v48; // r9d
  __int64 v49; // r15
  __int64 v50; // r13
  __int64 v51; // rdi
  int v52; // r15d
  __int64 v53; // r13
  _DWORD *v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rdx
  _DWORD *v59; // r13
  __int64 v60; // rdx
  PDEVICE_OBJECT v61; // rcx
  __int64 v62; // rdx
  bool v63; // al
  char v64; // r15
  int v65; // edx
  __int64 v66; // r10
  unsigned __int64 v67; // r11
  __int64 v68; // rdx
  __int64 v69; // rdx
  __int64 v70; // rdx
  __int64 v71; // rdx
  __int64 v72; // r15
  char v73; // r14
  bool *v74; // rdx
  bool v75; // al
  __int64 v76; // r9
  char v78[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v79; // [rsp+58h] [rbp-A8h] BYREF
  char v80; // [rsp+60h] [rbp-A0h] BYREF
  char v81; // [rsp+61h] [rbp-9Fh] BYREF
  char v82[2]; // [rsp+62h] [rbp-9Eh] BYREF
  unsigned int v83; // [rsp+64h] [rbp-9Ch]
  _DWORD *v84; // [rsp+68h] [rbp-98h] BYREF
  int v85; // [rsp+70h] [rbp-90h]
  int v86; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v87; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v88; // [rsp+80h] [rbp-80h]
  int v89; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v90; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v91; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v92; // [rsp+98h] [rbp-68h]
  __int64 v93; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v94; // [rsp+A8h] [rbp-58h]
  __int64 v95; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v96; // [rsp+B8h] [rbp-48h]
  __int64 v97; // [rsp+C0h] [rbp-40h]
  __int64 v98; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING StringOut; // [rsp+D0h] [rbp-30h] BYREF
  __int64 (__fastcall *v100)(_QWORD, _QWORD, _QWORD); // [rsp+E0h] [rbp-20h]
  unsigned __int64 v101; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v102; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v103; // [rsp+F8h] [rbp-8h]
  __int64 v104; // [rsp+100h] [rbp+0h] BYREF
  __int64 v105; // [rsp+108h] [rbp+8h] BYREF
  __int128 v106; // [rsp+110h] [rbp+10h] BYREF
  __int64 v107; // [rsp+120h] [rbp+20h]
  __int64 v108; // [rsp+128h] [rbp+28h]
  bool *v109; // [rsp+130h] [rbp+30h]
  struct _UNICODE_STRING v110; // [rsp+138h] [rbp+38h] BYREF
  __int128 v111; // [rsp+148h] [rbp+48h] BYREF
  __int128 v112; // [rsp+158h] [rbp+58h]
  __int128 v113; // [rsp+168h] [rbp+68h] BYREF
  __int64 v114; // [rsp+178h] [rbp+78h]
  _OWORD v115[5]; // [rsp+180h] [rbp+80h] BYREF
  _OWORD v116[6]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v117[80]; // [rsp+230h] [rbp+130h] BYREF

  v7 = a5;
  v108 = a5;
  LOBYTE(v7) = 0;
  v96 = a3;
  v10 = (char)a2;
  v88 = a2;
  v109 = a7;
  v11 = 0;
  v100 = a4;
  v84 = 0;
  v79 = 0;
  v98 = 0;
  v85 = v7;
  v78[0] = 0;
  v82[0] = 0;
  v80 = 0;
  memset(v115, 0, sizeof(v115));
  StringOut = 0;
  memset(v116, 0, 0x58u);
  v110 = 0;
  memset(v117, 0, sizeof(v117));
  v89 = 0;
  v86 = 0;
  v114 = 0;
  v111 = 0;
  v94 = 0;
  v112 = 0;
  v107 = 0;
  v113 = 0;
  v97 = 0;
  v106 = 0;
  v102 = 0;
  v93 = 0;
  v105 = 0;
  v104 = 0;
  v81 = 0;
  v87 = 0;
  v95 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v101 = 0;
  LOWORD(v83) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    WPP_SF_qqZD(WPP_GLOBAL_Control->AttachedDevice, 0, v12, a1, v10, (__int64)a3, a6);
    v11 = v84;
  }
  if ( !(unsigned __int8)CscStUtIsValidStoreEntryName(a3, 0) )
  {
    EntryFullPath = -1073741773;
    v14 = 12929;
LABEL_169:
    v20 = BYTE1(v83);
    v19 = v83;
    goto LABEL_170;
  }
  if ( !a3 )
    goto LABEL_168;
  v15 = *a3;
  if ( !(_WORD)v15 )
    goto LABEL_168;
  v16 = (_WORD *)*((_QWORD *)a3 + 1);
  v17 = &v16[v15 >> 1];
  while ( v16 < v17 )
  {
    if ( *v16 == 92 )
      goto LABEL_168;
    ++v16;
  }
  if ( (a6 & 0xC0) != 0 )
  {
LABEL_168:
    EntryFullPath = -1073740768;
    v14 = 12936;
    goto LABEL_169;
  }
  v18 = *(_DWORD *)(a1 + 336) & 0x10;
  v19 = v18 != 0 ? 0x40 : 0;
  v20 = (2 * (a6 & 0x1E | (2 * (a6 & 0xE0)))) | ((BYTE1(v83) & 0xFC | 1) ^ (2 * (a6 & 1))) & 0x43;
  if ( ((2 * (a6 & 0x1E | (unsigned __int8)(2 * (a6 & 0xE0)))) & 0x30) == 0x10 )
  {
    EntryFullPath = -1073740768;
    v14 = 12954;
LABEL_170:
    v59 = (_DWORD *)v79;
    goto LABEL_171;
  }
  if ( ((v20 >> 2) & (v18 != 0)) != 0 && !v100 )
  {
    EntryFullPath = -1073740768;
    v14 = 12967;
    goto LABEL_170;
  }
  v21 = v88;
  if ( ((2 * (a6 & 0x1E | (unsigned __int8)(2 * (a6 & 0xE0)))) & 0x10) == 0 )
  {
    Entry = CscEnFindEntry(&v84, v88, a3);
    EntryFullPath = Entry;
    if ( Entry < 0 && Entry != -1073741772 && Entry != -1073741809 )
    {
      v14 = 12986;
      goto LABEL_170;
    }
    v11 = v84;
    if ( v84 )
    {
      CscEnpMainAcquireExclusive((__int64)v84);
      v11 = v84;
      if ( (v84[84] & 0x10) != 0 && (v84[48] & 0x10) == 0 )
      {
        EntryFullPath = -1073741790;
        v14 = 13005;
        goto LABEL_170;
      }
      if ( v84[1] != 1 )
      {
        EntryFullPath = -1073741790;
        v14 = 13014;
        goto LABEL_170;
      }
    }
  }
  if ( ((2 * (a6 & 0x1E | (unsigned __int8)(2 * (a6 & 0xE0)))) & 0x20) != 0 )
  {
    v24 = *(_QWORD *)(a1 + 24);
    v79 = v24;
    if ( v24 )
    {
      CscEnReferenceEntry(v24);
      v11 = v84;
    }
    v23 = (unsigned __int8)v85;
    if ( (_QWORD *)v24 == v21 )
      v23 = 1;
  }
  else
  {
    v23 = CscEnpAcquireRenameLocks((_QWORD *)a1, v21, v78, v82, &v79);
    EntryFullPath = v23;
    if ( v23 < 0 )
    {
      LOBYTE(v18) = v78[0];
      v14 = 13030;
      v85 = v18;
      goto LABEL_170;
    }
    v11 = v84;
    LOBYTE(v23) = v78[0];
    v19 = v18 != 0 ? 65 : 1;
  }
  v85 = v23;
  v103 = 0;
  if ( v11 )
  {
    if ( v11[1] != 1 )
    {
      EntryFullPath = -1073741790;
      v14 = 13056;
      goto LABEL_170;
    }
    if ( ((v19 & 0x40) != 0) != ((v11[84] >> 4) & 1) )
    {
      if ( (v19 & 0x40) == 0 || (v11[48] & 0x10) == 0 )
      {
        v14 = 13095;
        EntryFullPath = (v11[48] & 0x10) != 0 ? -1073741108 : -1073741790;
        goto LABEL_170;
      }
      v19 |= 0x80u;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids);
        v11 = v84;
      }
    }
    v25 = v19 | 2;
    *(_QWORD *)&v116[5] = *((_QWORD *)v11 + 36);
    v116[0] = *((_OWORD *)v11 + 12);
    v116[1] = *((_OWORD *)v11 + 13);
    v116[2] = *((_OWORD *)v11 + 14);
    v116[3] = *((_OWORD *)v11 + 15);
    v116[4] = *((_OWORD *)v11 + 16);
    v103 = *((_QWORD *)v11 + 43);
    v26 = *((_WORD *)v11 + 132);
    if ( v26 )
      LOBYTE(v26) = 8;
    v19 = v26 | v25 & 0xF7;
    v27 = v19 & 0x40;
    if ( (v11[48] & 0x10) != 0 )
    {
      if ( !v27 )
      {
        v20 |= 2u;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids);
          v11 = v84;
        }
      }
    }
    else if ( v27 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 144, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids);
      }
      EntryFullPath = -1073741790;
      v14 = 13143;
      goto LABEL_170;
    }
    v86 = v11[32];
    v93 = *((_QWORD *)v11 + 17);
    if ( !v27 || v19 < 0 )
    {
      CscEnpMainRelease((__int64)v11);
      LOBYTE(v28) = 1;
      CscEnpDereferenceEntryEx((__int64)&v84, v28);
    }
  }
  EntryFullPath = CscEnpCheckState(a1);
  if ( EntryFullPath < 0 )
  {
    v14 = 13174;
    goto LABEL_170;
  }
  v29 = *(_DWORD *)(a1 + 16);
  if ( !v29 )
  {
    EntryFullPath = -1073741811;
    v14 = 13195;
    goto LABEL_170;
  }
  v30 = v29 - 1;
  if ( v30 && (unsigned int)(v30 - 1) >= 2 )
  {
    EntryFullPath = -1073740768;
    v14 = 13200;
    goto LABEL_170;
  }
  if ( (*(_DWORD *)(a1 + 336) & 0x10) == 0 )
  {
    EntryFullPath = CscEnpEntryToTunnel(a1);
    if ( EntryFullPath < 0 )
    {
      v14 = 13218;
      goto LABEL_170;
    }
  }
  LOBYTE(v83) = 0;
  if ( (v20 & 4) != 0 )
  {
    if ( (v19 & 0x40) != 0 )
    {
      EntryFullPath = CscEnCreateTombstoneTree(a1, (__int64)v84, v100, v108, &v87, &v90, &v91);
      if ( EntryFullPath < 0 )
      {
        v14 = 13236;
        goto LABEL_170;
      }
      CscEnpQuotaComputeChangeForTombstone(v90, v91, &v102, &v101);
      LOBYTE(v31) = 1;
      v92 = v101;
      v97 = v102;
      EntryFullPath = CscEnpQuotaPrepareChange(a1, v102, v101, v31, 0, (__int64)&v106);
      if ( EntryFullPath < 0 )
      {
        v14 = 13254;
        v94 = v107;
        goto LABEL_170;
      }
      v32 = *(__m128i *)(a1 + 192);
      v33 = *(_OWORD *)(a1 + 208);
      v115[2] = *(_OWORD *)(a1 + 224);
      v34 = *(_OWORD *)(a1 + 256);
      v115[0] = v32;
      LODWORD(v115[0]) = _mm_cvtsi128_si32(v32) & 0xFFFFFFCE | 0x10;
      v115[1] = v33;
      v35 = *(_OWORD *)(a1 + 240);
      v94 = v107;
      v115[4] = v34;
    }
    else
    {
      v36 = *(_DWORD *)(a1 + 192);
      v37 = v36 >> 15;
      LOBYTE(v37) = (v36 >> 13) & 2 | (v36 >> 15) & 0x10 | 0xC;
      v83 = v37;
      if ( (v36 & 0x40000) != 0 )
      {
        v38 = *(_OWORD *)(a1 + 224);
        v115[1] = *(_OWORD *)(a1 + 208);
        v35 = *(_OWORD *)(a1 + 240);
        v115[2] = v38;
        v39 = *(_QWORD *)(a1 + 256);
      }
      else
      {
        v40 = *(_OWORD *)(a1 + 304);
        v115[1] = *(_OWORD *)(a1 + 288);
        v35 = *(_OWORD *)(a1 + 320);
        v115[2] = v40;
        v39 = *(_QWORD *)(a1 + 336);
      }
      WORD4(v115[4]) = *(_WORD *)(a1 + 264);
      *(_QWORD *)&v115[4] = v39;
    }
    v115[3] = v35;
    EntryFullPath = RtlDuplicateUnicodeString(0, (PCUNICODE_STRING)(a1 + 48), &StringOut);
    if ( EntryFullPath < 0 )
    {
      v14 = 13301;
      goto LABEL_170;
    }
  }
  EntryFullPath = CscEnpGetEntryFullPath(a1, &v110);
  if ( EntryFullPath < 0 )
  {
    v14 = 13309;
    goto LABEL_170;
  }
  v41 = v88;
  v42 = *(_DWORD *)(a1 + 336) >> 4;
  LOBYTE(v42) = (*(_DWORD *)(a1 + 336) & 0x10) != 0;
  EntryFullPath = CscEnpGetTunnelInformationForEntry(
                    (_DWORD)v88,
                    *(_DWORD *)(a1 + 16),
                    v42,
                    *(_DWORD *)(a1 + 192),
                    (__int64)v96,
                    (v20 & 8) != 0,
                    (unsigned __int64)v116 & -(__int64)((v19 & 2) != 0),
                    (__int64)v117,
                    (__int64)&v111);
  if ( EntryFullPath < 0 )
  {
    v14 = 13330;
    goto LABEL_170;
  }
  if ( CscEnDbIsCacheReadOnly(a1) && (_QWORD)v111 && (*(_DWORD *)(v111 + 4) & 0x80417) != 0 )
  {
    EntryFullPath = -1073741662;
    v14 = 13342;
    goto LABEL_170;
  }
  LOBYTE(v43) = (v19 & 0x40) != 0;
  EntryFullPath = CscEnpQueryPinInheritance(v41, v43, &v89);
  if ( EntryFullPath < 0 )
  {
    v14 = 13353;
    goto LABEL_170;
  }
  if ( *((_QWORD *)&v112 + 1) )
    v45 = **((_WORD **)&v112 + 1);
  else
    v45 = *(_WORD *)(a1 + 264);
  if ( v45 )
    LOBYTE(v45) = 4;
  v46 = v45 | v19 & 0xFB;
  if ( (v46 & 4) != 0 || BYTE1(v89) || HIBYTE(v89) )
    v47 = 4;
  else
    v47 = 0;
  v19 = v47 | v46 & 0xFB;
  LOBYTE(v44) = (v19 & 8) != 0;
  CscEnpQuotaComputeChangeForRename(
    a1,
    v103,
    v44,
    (v20 & 4) != 0 && (v19 & 0x40) == 0,
    (v19 & 4) != 0,
    &v105,
    &v104,
    &v81);
  LOBYTE(v48) = 1;
  EntryFullPath = CscEnpQuotaPrepareChange(a1, v105, v104, v48, 1, (__int64)&v113);
  if ( EntryFullPath < 0 )
  {
    v14 = 13400;
    goto LABEL_170;
  }
  if ( (v19 & 0x40) != 0 )
  {
    if ( v84 )
    {
      EntryFullPath = CscEnMergeTreeForRename(a1, (__int64)v84);
      if ( EntryFullPath < 0 )
      {
        v14 = 13417;
        goto LABEL_170;
      }
      v20 &= ~1u;
      v19 |= 0x20u;
    }
    else if ( (v20 & 8) != 0 && (*(_DWORD *)(a1 + 192) & 0x400) == 0 )
    {
      EntryFullPath = CscEnMarkDirtyCreatedTree(a1, 0);
      if ( EntryFullPath < 0 )
      {
        v14 = 13432;
        goto LABEL_170;
      }
    }
  }
  if ( (v20 & 1) != 0 )
  {
    v49 = (__int64)v96;
    v50 = (__int64)v88;
    EntryFullPath = CscStorepLowIoRenameFilePoster(*(_QWORD *)(a1 + 144), v88[18], (__int64)v96, (v20 & 2) != 0);
    if ( EntryFullPath < 0 )
    {
      v14 = 13455;
      goto LABEL_170;
    }
    v19 |= 0x10u;
  }
  else
  {
    v51 = *(_QWORD *)(a1 + 144);
    v52 = *(_DWORD *)(a1 + 128);
    v53 = *(_QWORD *)(a1 + 136);
    EntryFullPath = CscStorepLowIoOpenFileByFileId((unsigned int)&v95, v51, v93, 1245592, 7, 1);
    if ( EntryFullPath < 0 )
    {
      v14 = 13481;
      goto LABEL_170;
    }
    EntryFullPath = CscStOrphanerAddTemporaryFile(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 64LL), v51);
    if ( EntryFullPath < 0 )
    {
      v14 = 13489;
      goto LABEL_170;
    }
    v54 = v84;
    *(_QWORD *)(a1 + 144) = v95;
    *(_QWORD *)(a1 + 136) = v93;
    *(_DWORD *)(a1 + 128) = v86;
    v95 = 0;
    *(_OWORD *)(a1 + 368) = *((_OWORD *)v54 + 23);
    *(_DWORD *)(a1 + 384) = v54[96];
    CscEnpMainRelease((__int64)v54);
    LOBYTE(v55) = 1;
    CscEnpDereferenceEntryEx((__int64)&v84, v55);
    LOBYTE(v56) = 1;
    EntryFullPath = CscStorepLowIoSetDeleteDisposition(v51, v56);
    if ( EntryFullPath < 0 )
    {
      v14 = 13510;
      goto LABEL_170;
    }
    CscStorepLowIoClosePoster(v51, v57);
    v93 = v53;
    v20 |= 0x40u;
    v50 = (__int64)v88;
    v86 = v52;
    v49 = (__int64)v96;
  }
  if ( *(_WORD *)(a1 + 264) )
  {
    EntryFullPath = CscEnDecrementPinnedDescendantCountOnUnpinOrRename((__m128i *)a1, 1);
    if ( EntryFullPath < 0 )
    {
      v14 = 13551;
      goto LABEL_170;
    }
  }
  EntryFullPath = CscEnpChangeChildCountEx(*(_QWORD *)(a1 + 24), a1 + 192, 2);
  if ( EntryFullPath < 0 )
  {
    v14 = 13560;
    goto LABEL_170;
  }
  CscEnpRenameFixParent(a1, v50, &v80);
  EntryFullPath = CscEnpRenameFixNames((struct _UNICODE_STRING *)a1, v49);
  if ( EntryFullPath < 0 )
  {
    v14 = 13579;
    goto LABEL_170;
  }
  if ( *(_WORD *)(a1 + 264) )
  {
    EntryFullPath = CscEnIncrementPinnedDescendantCountOnPinOrRename(a1, 0, 1);
    if ( EntryFullPath < 0 )
    {
      v14 = 13610;
      goto LABEL_170;
    }
  }
  EntryFullPath = CscEnpChangeChildCountEx(*(_QWORD *)(a1 + 24), a1 + 192, 1);
  if ( EntryFullPath < 0 )
  {
    v14 = 13621;
    goto LABEL_170;
  }
  LOBYTE(v58) = (v20 & 8) != 0;
  EntryFullPath = CscEnpSetTunneledInformationOnEntry(a1, v58, &v111);
  if ( EntryFullPath < 0 )
  {
    v14 = 13634;
    goto LABEL_170;
  }
  EntryFullPath = CscEnpWriteQid(a1);
  if ( EntryFullPath < 0 )
  {
    v14 = 13645;
    goto LABEL_170;
  }
  EntryFullPath = CscEnpRenameApplyTargetDirPinFlags(a1, v50, v20 >> 7);
  if ( EntryFullPath < 0 )
  {
    v14 = 13657;
    goto LABEL_170;
  }
  v59 = (_DWORD *)v79;
  v14 = 0;
  if ( (v20 & 4) != 0 )
  {
    if ( (v19 & 0x40) != 0 )
    {
      EntryFullPath = CscStorepLowIoRenameFilePoster(v87, *(_QWORD *)(v79 + 144), (__int64)&StringOut, 0);
      if ( EntryFullPath < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
LABEL_159:
          EntryFullPath = 0;
          goto LABEL_160;
        }
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
          WPP_SF_ZD(
            WPP_GLOBAL_Control->AttachedDevice,
            146,
            (unsigned int)WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
            (unsigned int)&StringOut,
            EntryFullPath);
      }
      else
      {
        CscStorepLowIoClosePoster(v87, v60);
        v87 = 0;
        EntryFullPath = CscEnpChangeChildCountEx(v59, v115, 1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
        {
          WPP_SF_ZD(
            WPP_GLOBAL_Control->AttachedDevice,
            145,
            (unsigned int)WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
            (unsigned int)&StringOut,
            EntryFullPath);
        }
        if ( WORD4(v115[4]) )
          EntryFullPath = CscEnIncrementPinnedDescendantCountOnPinOrRename((__int64)v59, 1, 1);
      }
      v61 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0 )
      {
        goto LABEL_159;
      }
      v62 = 147;
    }
    else
    {
      v78[0] = 0;
      EntryFullPath = CscEnpCreateChild(
                        v79,
                        (__int64)&StringOut,
                        v83,
                        WORD4(v115[4]),
                        (__int64)&v115[1],
                        (__int64)v78,
                        &v98);
      if ( EntryFullPath >= 0 )
        goto LABEL_160;
      v61 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) == 0 )
      {
        goto LABEL_159;
      }
      v62 = 148;
    }
    WPP_SF_d(v61->AttachedDevice, v62, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, (unsigned int)EntryFullPath);
    goto LABEL_159;
  }
LABEL_160:
  if ( (v20 & 8) != 0 )
    CscDiffTransferInvalidateState(a1);
  CscEnpNotifyItemChangedEx(a1, 64, &v110);
LABEL_171:
  CscEnpQuotaCommitChange(a1, EntryFullPath >= 0, (char *)&v113, 0, 0, v81);
  v63 = EntryFullPath >= 0 && !v87;
  v64 = v106;
  if ( (v106 & 1) == 0 )
    goto LABEL_199;
  v65 = 0;
  if ( v63 )
  {
    if ( v106 >= 0 )
      v66 = *((_QWORD *)&v106 + 1) - v97;
    else
      v66 = v97;
    if ( v94 >= 0 )
      v92 = v94 - v92;
    v67 = v92;
    if ( v90 )
      v65 = v90;
    goto LABEL_192;
  }
  if ( (v106 & 4) != 0 )
  {
    if ( *((__int64 *)&v106 + 1) <= 0 )
      v66 = 0;
    else
      v66 = -*((_QWORD *)&v106 + 1);
    if ( v94 > 0 )
    {
      v67 = -v94;
      goto LABEL_192;
    }
  }
  else
  {
    v66 = 0;
  }
  v67 = 0;
LABEL_192:
  if ( (v106 & 2) != 0 || v66 || v67 || v65 )
    CscEnpQuotapUpdateDbInfo(
      a1,
      v66,
      v67 & -(__int64)((v106 & 0x10) != 0),
      v67 & -(__int64)((v106 & 0x20) != 0),
      0,
      0,
      ((v106 & 2) == 0) - 1,
      v65);
  if ( (v64 & 8) == 0 )
    *(_DWORD *)(a1 + 20) &= ~0x100u;
LABEL_199:
  CscEnpFreeEntryFullPath((__int64)&v110, 0);
  RtlFreeUnicodeString(&StringOut);
  if ( v84 )
  {
    CscEnpMainRelease((__int64)v84);
    LOBYTE(v69) = v19 & 1;
    CscEnpDereferenceEntryEx((__int64)&v84, v69);
  }
  if ( v87 )
  {
    CscStorepLowDeleteTree(v87, 0);
    LOBYTE(v70) = 1;
    CscStorepLowIoSetDeleteDisposition(v87, v70);
    CscStorepLowIoClosePoster(v87, v71);
  }
  if ( (v20 & 0x40) != 0 || (v19 & 0x12) == 0x12 )
    CscEnpDeletePQEntry(a1, 0, &v86, &v93);
  if ( (v19 & 2) != 0 && (v19 & 0x30) != 0 )
  {
    if ( (v19 & 0x20) != 0 )
      LODWORD(v116[0]) &= ~0x10u;
    v72 = (__int64)v88;
    CscEnpChangeChildCountEx(v88, v116, 2);
    if ( WORD4(v116[4]) )
      CscEnDecrementPinnedDescendantCountOnUnpinOrRename((__m128i *)a1, 1);
  }
  else
  {
    v72 = (__int64)v88;
  }
  if ( (v19 & 1) != 0 )
  {
    v73 = v85;
    CscEnpReleaseRenameLocks(a1, v72, v85, v82[0], v80, &v79);
  }
  else
  {
    if ( v59 )
    {
      if ( v80 )
      {
        v84 = v59;
        CscEnDereferenceEntry((__int64)&v84);
      }
      CscEnDereferenceEntry((__int64)&v79);
    }
    v73 = v85;
  }
  if ( v98 )
    CscEnpDereferenceEntryEx((__int64)&v98, 0);
  if ( v95 )
    CscStorepLowIoClosePoster(v95, v68);
  v74 = v109;
  if ( v109 )
  {
    v75 = EntryFullPath >= 0 && v73 == 0;
    *v109 = v75;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    if ( v74 )
      v76 = *v74 ? 89 : 78;
    else
      v76 = 63;
    WPP_SF_cDD(
      WPP_GLOBAL_Control->AttachedDevice,
      150,
      WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
      v76,
      EntryFullPath,
      v14);
  }
  return (unsigned int)EntryFullPath;
}

```

## disassembly

```asm
0x140081874  push    rbp
0x140081876  push    rbx
0x140081877  push    rsi
0x140081878  push    rdi
0x140081879  push    r12
0x14008187b  push    r13
0x14008187d  push    r14
0x14008187f  push    r15
0x140081881  lea     rbp, [rsp-198h]
0x140081889  sub     rsp, 298h
0x140081890  mov     rax, cs:__security_cookie
0x140081897  xor     rax, rsp
0x14008189a  mov     [rbp+1D0h+var_50], rax
0x1400818a1  mov     rax, [rbp+1D0h+arg_20]
0x1400818a8  xor     r12d, r12d
0x1400818ab  mov     rsi, rcx
0x1400818ae  mov     [rbp+1D0h+var_1A8], rax
0x1400818b2  mov     rcx, [rbp+1D0h+arg_30]
0x1400818b9  mov     al, r12b
0x1400818bc  mov     r13, r8
0x1400818bf  mov     [rbp+1D0h+var_218], r8
0x1400818c3  mov     r14, rdx
0x1400818c6  mov     [rbp+1D0h+var_250], rdx
0x1400818ca  mov     [rbp+1D0h+var_1A0], rcx
0x1400818ce  lea     edi, [r12+50h]
0x1400818d3  mov     ebx, r12d
0x1400818d6  mov     [rbp+1D0h+var_1F0], r9
0x1400818da  mov     r8d, edi; Size
0x1400818dd  mov     [rsp+2D0h+var_268], rbx
0x1400818e2  xor     edx, edx; Val
0x1400818e4  mov     [rsp+2D0h+var_278], r12
0x1400818e9  lea     rcx, [rbp+1D0h+var_150]; void *
0x1400818f0  mov     [rbp+1D0h+var_208], r12
0x1400818f4  mov     [rsp+2D0h+var_260], eax
0x1400818f8  mov     [rsp+2D0h+var_280], al
0x1400818fc  mov     [rsp+2D0h+var_26E], r12b
0x140081901  mov     [rsp+2D0h+var_270], r12b
0x140081906  call    memset
0x14008190b  xorps   xmm0, xmm0
0x14008190e  lea     r8d, [r12+58h]; Size
0x140081913  xor     edx, edx; Val
0x140081915  lea     rcx, [rbp+1D0h+var_100]; void *
0x14008191c  movups  xmmword ptr [rbp+1D0h+StringOut.Length], xmm0
0x140081920  call    memset
0x140081925  xorps   xmm0, xmm0
0x140081928  lea     rcx, [rbp+1D0h+var_A0]; void *
0x14008192f  mov     r8d, edi; Size
0x140081932  xor     edx, edx; Val
0x140081934  movups  [rbp+1D0h+var_198], xmm0
0x140081938  call    memset
0x14008193d  xorps   xmm0, xmm0
0x140081940  mov     [rbp+1D0h+var_248], r12d
0x140081944  xor     eax, eax
0x140081946  mov     [rsp+2D0h+var_25C], r12d
0x14008194b  mov     edx, r12d
0x14008194e  mov     [rbp+1D0h+var_158], rax
0x140081952  movups  [rbp+1D0h+var_188], xmm0
0x140081956  mov     [rbp+1D0h+var_228], rax
0x14008195a  movups  [rbp+1D0h+var_178], xmm0
0x14008195e  mov     [rbp+1D0h+var_1B0], rax
0x140081962  movups  [rbp+1D0h+var_168], xmm0
0x140081966  mov     [rbp+1D0h+var_210], rdx
0x14008196a  movups  [rbp+1D0h+var_1C0], xmm0
0x14008196e  mov     [rbp+1D0h+var_1E0], rdx
0x140081972  mov     [rbp+1D0h+var_230], r12
0x140081976  mov     [rbp+1D0h+var_1C8], r12
0x14008197a  mov     [rbp+1D0h+var_1D0], r12
0x14008197e  mov     [rsp+2D0h+var_26F], r12b
0x140081983  mov     [rsp+2D0h+var_258], r12
0x140081988  mov     [rbp+1D0h+var_220], r12
0x14008198c  mov     [rbp+1D0h+var_244], r12d
0x140081990  mov     [rbp+1D0h+var_240], r12d
0x140081994  mov     [rbp+1D0h+var_238], r12
0x140081998  mov     [rbp+1D0h+var_1E8], r12
0x14008199c  mov     word ptr [rsp+2D0h+var_26C], r12w
0x1400819a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400819a9  lea     r15, WPP_GLOBAL_Control
0x1400819b0  movzx   edi, [rbp+1D0h+arg_28]
0x1400819b7  cmp     rcx, r15
0x1400819ba  jz      short loc_1400819E4
0x1400819bc  test    dword ptr [rcx+2Ch], 40000h
0x1400819c3  jz      short loc_1400819E4
0x1400819c5  mov     rcx, [rcx+18h]
0x1400819c9  mov     r9, rsi
0x1400819cc  mov     dword ptr [rsp+2D0h+var_2A0], edi
0x1400819d0  mov     [rsp+2D0h+var_2A8], r13
0x1400819d5  mov     [rsp+2D0h+var_2B0], r14
0x1400819da  call    WPP_SF_qqZD
0x1400819df  mov     rbx, [rsp+2D0h+var_268]
0x1400819e4  xor     edx, edx
0x1400819e6  mov     rcx, r13
0x1400819e9  call    CscStUtIsValidStoreEntryName
0x1400819ee  test    al, al
0x1400819f0  jnz     short loc_140081A01
0x1400819f2  mov     ebx, 0C0000033h
0x1400819f7  mov     edi, 3281h
0x1400819fc  jmp     loc_1400826C6
0x140081a01  test    r13, r13
0x140081a04  jz      loc_1400826BC
0x140081a0a  movzx   eax, word ptr [r13+0]
0x140081a0f  test    ax, ax
0x140081a12  jz      loc_1400826BC
0x140081a18  mov     rcx, [r13+8]
0x140081a1c  shr     rax, 1
0x140081a1f  lea     rdx, [rcx+rax*2]
0x140081a23  cmp     rcx, rdx
0x140081a26  jnb     short loc_140081A3C
0x140081a28  mov     eax, 5Ch ; '\'
0x140081a2d  cmp     ax, [rcx]
0x140081a30  jz      loc_1400826BC
0x140081a36  add     rcx, 2
0x140081a3a  jmp     short loc_140081A23
0x140081a3c  test    dil, 0C0h
0x140081a40  jnz     loc_1400826BC
0x140081a46  mov     r15d, [rsi+150h]
0x140081a4d  mov     edx, 1
0x140081a52  and     r15d, 10h
0x140081a56  mov     r12b, dil
0x140081a59  mov     eax, r15d
0x140081a5c  neg     eax
0x140081a5e  mov     al, byte ptr [rsp+2D0h+var_26C+1]
0x140081a62  sbb     r14b, r14b
0x140081a65  or      al, dl
0x140081a67  and     al, 0FDh
0x140081a69  and     r12b, dl
0x140081a6c  add     r12b, r12b
0x140081a6f  and     r14b, 40h
0x140081a73  xor     r12b, al
0x140081a76  mov     al, dil
0x140081a79  and     al, 0E0h
0x140081a7b  and     dil, 1Eh
0x140081a7f  add     al, al
0x140081a81  and     r12b, 43h
0x140081a85  or      al, dil
0x140081a88  add     al, al
0x140081a8a  or      r12b, al
0x140081a8d  mov     al, r12b
0x140081a90  and     al, 30h
0x140081a92  cmp     al, 10h
0x140081a94  jnz     short loc_140081AA5
0x140081a96  mov     ebx, 0C0000420h
0x140081a9b  mov     edi, 329Ah
0x140081aa0  jmp     loc_1400826D0
0x140081aa5  test    r15d, r15d
0x140081aa8  mov     al, r12b
0x140081aab  setnz   cl
0x140081aae  shr     al, 2
0x140081ab1  and     cl, al
0x140081ab3  test    dl, cl
0x140081ab5  jz      short loc_140081ACD
0x140081ab7  cmp     [rbp+1D0h+var_1F0], 0
0x140081abc  jnz     short loc_140081ACD
0x140081abe  mov     ebx, 0C0000420h
0x140081ac3  mov     edi, 32A7h
0x140081ac8  jmp     loc_1400826D0
0x140081acd  mov     rdi, [rbp+1D0h+var_250]
0x140081ad1  test    r12b, 10h
0x140081ad5  jnz     loc_140081B5E
0x140081adb  mov     r8, r13
0x140081ade  lea     rcx, [rsp+2D0h+var_268]
0x140081ae3  mov     rdx, rdi
0x140081ae6  call    CscEnFindEntry
0x140081aeb  mov     ebx, eax
0x140081aed  test    eax, eax
0x140081aef  jns     short loc_140081B09
0x140081af1  cmp     eax, 0C0000034h
0x140081af6  jz      short loc_140081B09
0x140081af8  cmp     eax, 0C000000Fh
0x140081afd  jz      short loc_140081B09
0x140081aff  mov     edi, 32BAh
0x140081b04  jmp     loc_1400826D0
0x140081b09  mov     rbx, [rsp+2D0h+var_268]
0x140081b0e  test    rbx, rbx
0x140081b11  jz      short loc_140081B63
0x140081b13  mov     rcx, rbx
0x140081b16  call    CscEnpMainAcquireExclusive
0x140081b1b  mov     rbx, [rsp+2D0h+var_268]
0x140081b20  mov     eax, [rbx+150h]
0x140081b26  test    al, 10h
0x140081b28  jz      short loc_140081B43
0x140081b2a  mov     eax, [rbx+0C0h]
0x140081b30  test    al, 10h
0x140081b32  jnz     short loc_140081B43
0x140081b34  mov     ebx, 0C0000022h
0x140081b39  mov     edi, 32CDh
0x140081b3e  jmp     loc_1400826D0
0x140081b43  mov     r13d, 1
0x140081b49  cmp     [rbx+4], r13d
0x140081b4d  jz      short loc_140081B69
0x140081b4f  mov     ebx, 0C0000022h
0x140081b54  mov     edi, 32D6h
0x140081b59  jmp     loc_1400826D0
0x140081b5e  mov     r13d, edx
0x140081b61  jmp     short loc_140081B69
0x140081b63  mov     r13d, 1
0x140081b69  test    r12b, 20h
0x140081b6d  jnz     short loc_140081BC0
0x140081b6f  lea     rax, [rsp+2D0h+var_278]
0x140081b74  mov     rdx, rdi
0x140081b77  lea     r9, [rsp+2D0h+var_26E]
0x140081b7c  mov     [rsp+2D0h+var_2B0], rax
0x140081b81  lea     r8, [rsp+2D0h+var_280]
0x140081b86  mov     rcx, rsi
0x140081b89  call    CscEnpAcquireRenameLocks
0x140081b8e  mov     ebx, eax
0x140081b90  test    eax, eax
0x140081b92  jns     short loc_140081BA8
0x140081b94  mov     r15b, [rsp+2D0h+var_280]
0x140081b99  mov     edi, 32E6h
0x140081b9e  mov     [rsp+2D0h+var_260], r15d
0x140081ba3  jmp     loc_1400826D0
0x140081ba8  mov     rbx, [rsp+2D0h+var_268]
0x140081bad  neg     r15d
0x140081bb0  mov     al, [rsp+2D0h+var_280]
0x140081bb4  sbb     r14b, r14b
0x140081bb7  and     r14b, 40h
0x140081bbb  add     r14b, r13b
0x140081bbe  jmp     short loc_140081BE9
0x140081bc0  mov     r15, [rsi+18h]
0x140081bc4  mov     [rsp+2D0h+var_278], r15
0x140081bc9  test    r15, r15
0x140081bcc  jz      short loc_140081BDB
0x140081bce  mov     rcx, r15
0x140081bd1  call    CscEnReferenceEntry
0x140081bd6  mov     rbx, [rsp+2D0h+var_268]
0x140081bdb  mov     eax, [rsp+2D0h+var_260]
0x140081bdf  cmp     r15, rdi
0x140081be2  movzx   eax, al
0x140081be5  cmovz   eax, r13d
0x140081be9  mov     [rsp+2D0h+var_260], eax
0x140081bed  mov     [rbp+1D0h+var_1D8], 0
0x140081bf5  test    rbx, rbx
0x140081bf8  jz      loc_140081DA5
0x140081bfe  cmp     [rbx+4], r13d
0x140081c02  jz      short loc_140081C13
0x140081c04  mov     ebx, 0C0000022h
0x140081c09  mov     edi, 3300h
0x140081c0e  jmp     loc_1400826D0
0x140081c13  mov     ecx, [rbx+150h]
0x140081c19  xor     eax, eax
0x140081c1b  shr     ecx, 4
0x140081c1e  mov     dl, r14b
0x140081c21  and     ecx, r13d
0x140081c24  and     dl, 40h
0x140081c27  setnz   al
0x140081c2a  cmp     eax, ecx
0x140081c2c  jz      short loc_140081C9B
0x140081c2e  test    dl, dl
0x140081c30  jz      short loc_140081C78
0x140081c32  mov     eax, [rbx+0C0h]
0x140081c38  test    al, 10h
0x140081c3a  jz      short loc_140081C78
0x140081c3c  or      r14b, 80h
0x140081c40  mov     rcx, cs:WPP_GLOBAL_Control
0x140081c47  lea     r15, WPP_GLOBAL_Control
0x140081c4e  cmp     rcx, r15
0x140081c51  jz      short loc_140081CA2
0x140081c53  test    dword ptr [rcx+2Ch], 40000h
0x140081c5a  jz      short loc_140081CA2
0x140081c5c  mov     rcx, [rcx+18h]
0x140081c60  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x140081c67  mov     edx, 8Eh
0x140081c6c  call    WPP_SF_
0x140081c71  mov     rbx, [rsp+2D0h+var_268]
0x140081c76  jmp     short loc_140081CA2
0x140081c78  mov     eax, [rbx+0C0h]
0x140081c7e  mov     edi, 3327h
0x140081c83  and     al, 10h
0x140081c85  mov     ebx, 0C0000022h
0x140081c8a  neg     al
0x140081c8c  sbb     ecx, ecx
0x140081c8e  and     ecx, 2AAh
0x140081c94  add     ebx, ecx
0x140081c96  jmp     loc_1400826D0
0x140081c9b  lea     r15, WPP_GLOBAL_Control
0x140081ca2  mov     rax, [rbx+120h]
0x140081ca9  or      r14b, 2
0x140081cad  mov     [rbp+1D0h+var_B0], rax
0x140081cb4  movups  xmm0, xmmword ptr [rbx+0C0h]
0x140081cbb  movaps  [rbp+1D0h+var_100], xmm0
0x140081cc2  movups  xmm1, xmmword ptr [rbx+0D0h]
0x140081cc9  movaps  [rbp+1D0h+var_F0], xmm1
0x140081cd0  movups  xmm0, xmmword ptr [rbx+0E0h]
0x140081cd7  movaps  [rbp+1D0h+var_E0], xmm0
0x140081cde  movups  xmm1, xmmword ptr [rbx+0F0h]
0x140081ce5  movaps  [rbp+1D0h+var_D0], xmm1
0x140081cec  movups  xmm0, xmmword ptr [rbx+100h]
0x140081cf3  movaps  [rbp+1D0h+var_C0], xmm0
0x140081cfa  mov     rax, [rbx+158h]
0x140081d01  mov     [rbp+1D0h+var_1D8], rax
0x140081d05  movzx   eax, word ptr [rbx+108h]
0x140081d0c  movzx   ecx, ax
0x140081d0f  shr     cx, 8
0x140081d13  test    cl, cl
0x140081d15  jnz     short loc_140081D1B
0x140081d17  test    al, al
0x140081d19  jz      short loc_140081D1D
0x140081d1b  mov     al, 8
0x140081d1d  and     r14b, 0F7h
0x140081d21  or      r14b, al
  ... truncated ...
```
