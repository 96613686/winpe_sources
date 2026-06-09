# sub_1804FBDB4

- ea: `0x1804fbdb4`
- end: `0x1804fe1fd`
- name: `sub_1804FBDB4`
- size: `9289`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, _OWORD *, unsigned __int8, char, char, char, char)`
- caller_count: `2`
- callee_count: `53`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1804f1148`
- `0x1804f64e0`

## callees

- `0x1800062d0`
- `0x18000b4cc`
- `0x180079f60`
- `0x180079f80`
- `0x18013f000`
- `0x18013f020`
- `0x18013f100`
- `0x18016d2c0`
- `0x1801a08a8`
- `0x1801a1648`
- `0x1801a4a54`
- `0x1801a5180`
- `0x1801a569c`
- `0x1801a5f5c`
- `0x1801a6064`
- `0x1801b12fc`
- `0x1801c8638`
- `0x1801c8694`
- `0x1801d6bb0`
- `0x1801ff6a0`
- `0x18023d234`
- `0x180259f24`
- `0x18028cd04`
- `0x18028f78c`
- `0x18029255c`
- `0x180292670`
- `0x1802d2bcc`
- `0x180343db0`
- `0x1803f7088`
- `0x1804ee6b8`
- `0x1804eec68`
- `0x1804fa100`
- `0x1804fab0c`
- `0x1804fadec`
- `0x1804fafec`
- `0x1804fb5fc`
- `0x1804fbb08`
- `0x1804fbdb4`
- `0x1805af44c`
- `0x1805c4988`
- `0x1805c49cc`
- `0x1805c4a50`
- `0x1805c58f0`
- `0x1805c84ac`
- `0x1805c91fc`
- `0x18060d58c`
- `0x18060da54`
- `0x18072e140`
- `0x180743020`
- `0x180743270`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x1804fcb71`
- `KERNEL32!SystemTimeToFileTime` at `0x1804fcb71`

## string_xrefs

- `0x1804fd9d6`: `MpDisableTrustedInstaller`
- `0x1804fdb19`: `BM_MpIsInstaller`
- `0x1804fddf1`: `BM_MpIsInstaller`
- `0x1804fda65`: `MpAllowHighTrustInstallerOnAllPaths`
- `0x1804fdb6b`: `BM_MpHighlyTrustedInstaller`
- `0x1804fdc97`: `BM_MpTrustedInstaller`
- `0x1804fdba6`: `%ls is a high trust installer.`
- `0x1804fdcd2`: `%ls is a trusted installer.`
- `0x1804fdaba`: `MpIsCreateProcessScan`
- `0x1804fd1f9`: `Engine.ValidateTrust.CatalogSignedPaths`
- `0x1804fd30e`: `Engine.ValidateTrust.CatalogSignedPaths`
- `0x1804fd41b`: `Engine.ValidateTrust.CatalogSignedPaths`
- `0x1804fc93d`: `IsTrusted - %ls - CI/EA: %d, ValidateTrust: %d (%d), FromCache: %d, FromSR: %d, Catalog: %d`
- `0x1804fdfd7`: `BUILTIN:MpLinkedToMicrosoftRoot`
- `0x1804fde93`: `BM_MpIsInstallerSignedUntrusted`
- `0x1804fdece`: `%ls is an installer (but not trusted).`
- `0x1804fdd38`: `BM_MpTrustedPotentialInstaller`
- `0x1804fdd75`: `%ls is a trusted file that might be an installer (allowing deeper analysis).`

## pseudocode

```c
__int64 __fastcall sub_1804FBDB4(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        _OWORD *a4,
        unsigned __int8 a5,
        char a6,
        char a7,
        char a8,
        char a9)
{
  __int64 v9; // rbx
  WCHAR *v10; // rdi
  char v11; // r15
  char v12; // al
  __int64 v13; // r8
  int v14; // r9d
  char v15; // dl
  char v16; // al
  unsigned int v17; // r15d
  char v18; // r13
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rdx
  struct _RTL_CRITICAL_SECTION *v24; // rbx
  __int64 v25; // rax
  __int64 v26; // r14
  int v27; // eax
  _QWORD *v28; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  _QWORD *v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // rcx
  void (__fastcall ***v34)(_QWORD, __int64); // rcx
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // r10d
  __int64 v39; // r8
  __int64 v40; // rax
  char *v41; // rax
  const char *v42; // r12
  HANDLE *v43; // rcx
  _QWORD *v44; // r13
  _QWORD *v45; // r14
  _QWORD *v46; // r15
  _QWORD *v47; // rax
  _QWORD *v48; // rax
  __int64 v49; // rax
  unsigned __int8 v50; // r14
  const char *v51; // r14
  const wchar_t *v52; // rbx
  const char *v53; // rcx
  const wchar_t *v54; // r9
  _WORD *v55; // r8
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 *v58; // rcx
  _OWORD *v59; // rdx
  char *v60; // rbx
  _QWORD *v61; // rax
  int v62; // eax
  struct _FILETIME v63; // rbx
  __int128 *v64; // rdx
  __int64 v65; // rdx
  struct _RTL_CRITICAL_SECTION *v66; // r14
  const char *v67; // rax
  char *v68; // rdx
  __int128 *v69; // rdx
  __int64 v70; // rdx
  __int128 *v71; // rdx
  __int64 v72; // rdx
  HANDLE *v73; // r14
  char v74; // r15
  char *v75; // rbx
  char *v76; // rcx
  char *v77; // rdx
  __int64 v78; // rcx
  char *v79; // r8
  __int64 v80; // rdx
  __int64 v81; // rcx
  _QWORD *v82; // rcx
  char *v83; // r9
  __int64 v84; // rdx
  __int64 v85; // rdx
  char *v86; // rax
  char *v87; // rcx
  __int64 v88; // rax
  char *v89; // r8
  unsigned int v90; // ebx
  __int64 v91; // r14
  int v92; // eax
  __int64 v93; // rbx
  __int64 v94; // rax
  int v95; // r14d
  __int64 v96; // rax
  const char *v97; // r10
  const char *v98; // r8
  const char *v99; // rax
  __int64 v100; // rax
  const wchar_t *v101; // rbx
  const wchar_t *v102; // r9
  void *v103; // rbx
  __int64 v105; // [rsp+20h] [rbp-110h]
  __int64 v106; // [rsp+30h] [rbp-100h]
  char v107; // [rsp+B0h] [rbp-80h]
  _BYTE v108[2]; // [rsp+B2h] [rbp-7Eh] BYREF
  unsigned int v109; // [rsp+B4h] [rbp-7Ch]
  __int64 *v110; // [rsp+B8h] [rbp-78h]
  _OWORD *v111; // [rsp+C0h] [rbp-70h]
  unsigned int v112; // [rsp+C8h] [rbp-68h] BYREF
  char v113; // [rsp+CCh] [rbp-64h]
  int v114; // [rsp+D0h] [rbp-60h] BYREF
  int v115; // [rsp+D4h] [rbp-5Ch] BYREF
  int v116; // [rsp+D8h] [rbp-58h] BYREF
  int v117; // [rsp+DCh] [rbp-54h] BYREF
  int v118; // [rsp+E0h] [rbp-50h] BYREF
  int v119; // [rsp+E4h] [rbp-4Ch] BYREF
  __int64 v120; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v121; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v122; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v123; // [rsp+100h] [rbp-30h] BYREF
  __int64 v124; // [rsp+108h] [rbp-28h] BYREF
  const char *v125; // [rsp+110h] [rbp-20h] BYREF
  __int64 v126; // [rsp+118h] [rbp-18h] BYREF
  int v127; // [rsp+120h] [rbp-10h]
  __int64 v128; // [rsp+128h] [rbp-8h] BYREF
  __int64 v129; // [rsp+130h] [rbp+0h] BYREF
  __int64 v130; // [rsp+138h] [rbp+8h] BYREF
  _QWORD v131[10]; // [rsp+140h] [rbp+10h] BYREF
  _QWORD v132[12]; // [rsp+190h] [rbp+60h] BYREF
  __int64 v133; // [rsp+1F0h] [rbp+C0h] BYREF
  const WCHAR *v134; // [rsp+1F8h] [rbp+C8h] BYREF
  void ***v135; // [rsp+200h] [rbp+D0h] BYREF
  __int64 v136; // [rsp+208h] [rbp+D8h] BYREF
  unsigned __int8 v137; // [rsp+210h] [rbp+E0h] BYREF
  char v138; // [rsp+211h] [rbp+E1h] BYREF
  unsigned __int8 v139; // [rsp+212h] [rbp+E2h] BYREF
  char v140; // [rsp+213h] [rbp+E3h] BYREF
  unsigned __int8 v141; // [rsp+214h] [rbp+E4h] BYREF
  unsigned __int8 v142; // [rsp+215h] [rbp+E5h] BYREF
  unsigned __int8 v143; // [rsp+216h] [rbp+E6h] BYREF
  struct _FILETIME FileTime; // [rsp+218h] [rbp+E8h] BYREF
  __int64 v145; // [rsp+220h] [rbp+F0h] BYREF
  __int128 v146; // [rsp+228h] [rbp+F8h] BYREF
  void ***v147; // [rsp+238h] [rbp+108h]
  unsigned __int64 v148; // [rsp+240h] [rbp+110h]
  LPVOID lpMem[2]; // [rsp+248h] [rbp+118h] BYREF
  __int128 v150; // [rsp+258h] [rbp+128h]
  const WCHAR *v151; // [rsp+268h] [rbp+138h] BYREF
  _QWORD v152[3]; // [rsp+270h] [rbp+140h] BYREF
  void **v153; // [rsp+288h] [rbp+158h] BYREF
  __int64 v154; // [rsp+290h] [rbp+160h]
  __int128 v155; // [rsp+298h] [rbp+168h]
  char v156; // [rsp+2A8h] [rbp+178h] BYREF
  _WORD v157[512]; // [rsp+2D0h] [rbp+1A0h] BYREF
  __int64 v158; // [rsp+738h] [rbp+608h] BYREF

  v158 = a2;
  v111 = a4;
  v110 = a3;
  v133 = a1;
  v9 = 0;
  v109 = 0;
  v137 = 0;
  v134 = 0;
  v10 = 0;
  v151 = 0;
  v150 = 0;
  lpMem[0] = &cert::`vftable';
  lpMem[1] = 0;
  LOWORD(v150) = 0;
  *(_QWORD *)((char *)&v150 + 4) = 4112;
  v138 = 0;
  if ( (int)sub_18028CD04(L"MpDisableTrustCheckGetBrokenCert", &v138) < 0
    && hDevice != &hDevice
    && (*((_BYTE *)hDevice + 28) & 2) != 0 )
  {
    sub_1801A1648(*((_QWORD *)hDevice + 2), 20, qword_180CDBCC8);
  }
  LOBYTE(v150) = v138 == 0;
  v113 = 0;
  v107 = 0;
  LOBYTE(v127) = 0;
  v138 = sub_1805C58F0(v133, 7);
  v11 = sub_1805C58F0(v133, 0);
  v12 = sub_1805C58F0(v133, 6);
  v140 = v12;
  v15 = v138;
  if ( !v138 && !v11 && !v12 )
    goto LABEL_8;
  v108[0] = 0;
  v19 = v133;
  v20 = *(_QWORD *)(v133 + 8384);
  if ( v20 )
  {
    if ( !(unsigned int)sub_180343DB0(v20 + 152, L"MpVolatileObject", v108) && v108[0] )
      goto LABEL_8;
    v15 = v138;
    v19 = v133;
  }
  if ( v15 )
  {
    if ( !wcsncmp(*(const wchar_t **)(v19 + 120), L"process://", 0xAu) )
    {
      v134 = (const WCHAR *)sub_18060DA54(*(_QWORD *)(v133 + 120) + 20LL);
      goto LABEL_51;
    }
LABEL_8:
    v16 = 1;
    v17 = v109;
LABEL_9:
    v18 = v17;
    goto LABEL_177;
  }
  v134 = (const WCHAR *)sub_18060DA54(*(_QWORD *)(v19 + 112));
  if ( sub_1805C4A50(v133) != 1 && !a6 && !byte_18105B1F4 )
  {
    if ( (unsigned int)dword_181011320 < 8 )
      v21 = 0x2000000;
    else
      v21 = *(_QWORD *)qword_181011318;
    v145 = 0;
    v22 = sub_1805C49CC(v133);
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 72LL))(v22, &v145) >= 0 && v21 && v145 >= v21 )
    {
      if ( (unsigned __int8)sub_1801A4A54(0, v23, "Engine.ValidateTrust.TrustSkipTooBig") )
      {
        v24 = lpCriticalSection;
        if ( lpCriticalSection )
        {
          EnterCriticalSection(lpCriticalSection);
          if ( (unsigned int)dword_18100A408 > 5
            && (qword_18100A418[0] & 0x400000000000LL) != 0
            && (qword_18100A418[1] & 0x400000000000LL) == qword_18100A418[1] )
          {
            v130 = (__int64)"SkipTooBig";
            v126 = (__int64)"TrustCheck";
            v112 = *(_DWORD *)(qword_181040D08 + 72);
            v114 = *(_DWORD *)(qword_181040D08 + 68);
            v115 = *(_DWORD *)(qword_181040D08 + 64);
            v116 = *(unsigned __int8 *)(qword_181040D08 + 60);
            v117 = *(unsigned __int8 *)(qword_181040D08 + 59);
            v118 = *(unsigned __int8 *)(qword_181040D08 + 58);
            v119 = *(unsigned __int8 *)(qword_181040D08 + 57);
            FileTime.dwLowDateTime = *(unsigned __int8 *)(qword_181040D08 + 56);
            v125 = *(const char **)(qword_181040D08 + 48);
            v124 = *(_QWORD *)(qword_181040D08 + 40);
            v123 = *(_QWORD *)(qword_181040D08 + 32);
            v122 = *(_QWORD *)(qword_181040D08 + 24);
            v121 = *(_QWORD *)(qword_181040D08 + 16);
            v120 = *(_QWORD *)(qword_181040D08 + 8);
            v128 = 0x1000000;
            v129 = 1;
            sub_1800062D0(
              (unsigned int)&dword_18100A408,
              (unsigned int)byte_180F5EBED,
              (unsigned int)&dword_18100A408,
              (unsigned int)&v129,
              (__int64)&v128,
              (__int64)&v120,
              (__int64)&v121,
              (__int64)&v122,
              (__int64)&v123,
              (__int64)&v124,
              (__int64)&v125,
              (__int64)&FileTime,
              (__int64)&v119,
              (__int64)&v118,
              (__int64)&v117,
              (__int64)&v116,
              (__int64)&v115,
              (__int64)&v114,
              (__int64)&v112,
              (__int64)&v126,
              (__int64)&v130);
          }
          LeaveCriticalSection(v24);
        }
      }
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
        sub_1801C8638(*((_QWORD *)hDevice + 2), 23, qword_180CDBCC8, *(_QWORD *)(v133 + 120));
      if ( (!dword_18100F574 || (unsigned __int8)(byte_18100F578 - 1) <= 2u) && !byte_18105B1F4 )
        goto LABEL_49;
      if ( (int)sub_1801A5F5C(
                  v157,
                  512,
                  L"File %ls is too large for the trusted check (container)",
                  *(_QWORD *)(v133 + 120)) < 0 )
      {
        if ( (dword_181042B40 & 1) == 0 && !byte_18105B1F4 )
          goto LABEL_49;
        *(_QWORD *)&v155 = L"String too long";
        *((_QWORD *)&v155 + 1) = 32;
      }
      else
      {
        if ( (dword_181042B40 & 1) == 0 && !byte_18105B1F4 )
          goto LABEL_49;
        v25 = -1;
        do
          ++v25;
        while ( v157[v25] );
        *(_QWORD *)&v155 = v157;
        *((_QWORD *)&v155 + 1) = (unsigned int)(2 * v25 + 2);
      }
      sub_1801A6064(&qword_18100F550, qword_180C18850, v13, 2, &v153);
LABEL_49:
      v16 = 1;
      v17 = 0;
      v18 = 0;
      goto LABEL_177;
    }
    v9 = 0;
  }
LABEL_51:
  v26 = sub_1805C4988(*(_QWORD *)(v133 + 8392));
  v135 = 0;
  v27 = sub_1805AF44C(&v151, v134);
  v10 = (WCHAR *)v151;
  if ( v27 >= 0 )
    v134 = v151;
  v136 = v158;
  v139 = 0;
  v143 = 0;
  v141 = 0;
  v142 = 0;
  v131[0] = &v141;
  v131[1] = &v138;
  v131[2] = &v135;
  v131[3] = &v134;
  v131[4] = lpMem;
  v131[5] = &v136;
  v131[6] = &a8;
  v131[7] = &v133;
  v131[8] = &a9;
  v131[9] = &v142;
  v152[0] = &v133;
  v152[1] = &v137;
  v152[2] = &v140;
  v132[0] = &v133;
  v132[1] = &v143;
  v132[2] = &v134;
  v132[3] = lpMem;
  v132[4] = &v138;
  v132[5] = &v135;
  v132[6] = &v156;
  v132[7] = &v136;
  v132[8] = &a9;
  v132[9] = &v139;
  v132[10] = v152;
  v132[11] = &v158;
  if ( v26 )
  {
    if ( !v11 )
    {
      v146 = 0;
      v147 = 0;
      sub_18029255C(&v146, v26);
      v153 = &FileOpenViaSysIo::`vftable';
      v154 = 0;
      v155 = (unsigned __int64)v26;
      v135 = &v153;
      sub_1804FADEC(v132);
      if ( !v137 && !v139 && !(unsigned __int8)sub_1804FAFEC(v131) )
      {
        if ( v154 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v154 + 8LL))(v154);
        goto LABEL_74;
      }
      if ( v154 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v154 + 8LL))(v154);
LABEL_98:
      v153 = &CertFileOpenInterface::`vftable';
      sub_18023D234(&v146, v35, v36, v37);
      goto LABEL_102;
    }
    v28 = (_QWORD *)sub_1805C49CC(v133);
    v31 = v28;
    if ( v28 )
      sub_18013F100(*v28, 12000, 192);
    else
      v31 = 0;
    v32 = v31[110];
    if ( v32 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v32 + 24LL))(v32) )
    {
      v145 = 0;
      (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v31[110] + 160LL))(v31[110], &v145);
      v33 = v145;
      v9 = 0;
      if ( !v145 )
      {
LABEL_81:
        v146 = 0;
        v147 = 0;
        sub_180292670(&v146, v26, v29, v30);
        v153 = &FileOpenViaSysIo::`vftable';
        v154 = 0;
        v155 = (unsigned __int64)v26;
        v135 = &v153;
        sub_1804FADEC(v132);
        if ( !v137 && !v139 && !(unsigned __int8)sub_1804FAFEC(v131) )
        {
          if ( v154 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v154 + 8LL))(v154);
          goto LABEL_74;
        }
        if ( v154 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v154 + 8LL))(v154);
        goto LABEL_98;
      }
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(v145 + 72), 0, 0) )
        LOBYTE(v9) = 1;
      else
        sub_1801A08A8(v33);
      v34 = (void (__fastcall ***)(_QWORD, __int64))v145;
      if ( v145 && _InterlockedDecrement((volatile signed __int32 *)(v145 + 8)) <= 0 && v34 )
      {
        _mm_lfence();
        (**v34)(v34, 1);
      }
      if ( (_BYTE)v9 )
      {
        v146 = 0;
        v147 = 0;
        sub_1804FAB0C(&v146, v26);
        v153 = &FileOpenViaSysIo::`vftable';
        v9 = 0;
        v154 = 0;
        v155 = (unsigned __int64)v26;
        v135 = &v153;
        sub_1804FADEC(v132);
        if ( !v137 && !v139 && !(unsigned __int8)sub_1804FAFEC(v131) )
        {
          if ( v154 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v154 + 8LL))(v154);
LABEL_74:
          v153 = &CertFileOpenInterface::`vftable';
          sub_18023D234(&v146, v35, v36, v37);
LABEL_75:
          v17 = v109;
          v16 = v109;
          goto LABEL_9;
        }
        if ( v154 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v154 + 8LL))(v154);
        goto LABEL_98;
      }
    }
    v9 = 0;
    goto LABEL_81;
  }
  sub_1804FADEC(v132);
  if ( !v137 && !v139 && !(unsigned __int8)sub_1804FAFEC(v131) )
    goto LABEL_75;
LABEL_102:
  if ( dword_18100F574 && (unsigned __int8)(byte_18100F578 - 1) > 2u || byte_18105B1F4 )
  {
    if ( lpMem[1] )
      v38 = *((unsigned __int8 *)lpMem[1] + 730);
    else
      v38 = -1;
    if ( (int)sub_1801A5F5C(
                v157,
                512,
                L"IsTrusted - %ls - CI/EA: %d, ValidateTrust: %d (%d), FromCache: %d, FromSR: %d, Catalog: %d",
                v134,
                v137,
                v141,
                v142,
                v139,
                v143,
                v38) < 0 )
    {
      if ( (dword_181042B40 & 1) != 0 || byte_18105B1F4 )
      {
        *(_QWORD *)&v155 = L"String too long";
        *((_QWORD *)&v155 + 1) = 32;
LABEL_117:
        sub_1801A6064(&qword_18100F550, qword_180C18850, v39, 2, &v153);
      }
    }
    else if ( (dword_181042B40 & 1) != 0 || byte_18105B1F4 )
    {
      v40 = -1;
      do
        ++v40;
      while ( v157[v40] );
      *(_QWORD *)&v155 = v157;
      *((_QWORD *)&v155 + 1) = (unsigned int)(2 * v40 + 2);
      goto LABEL_117;
    }
  }
  v41 = (char *)lpMem[1];
  if ( lpMem[1] )
  {
    v42 = (char *)lpMem[1] + 208;
    if ( *((_QWORD *)lpMem[1] + 29) > 7u )
      v42 = *(const char **)v42;
    if ( v42 )
      goto LABEL_126;
  }
  else
  {
    v42 = 0;
  }
  v43 = (HANDLE *)hDevice;
  if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
  {
    sub_1801C8638(*((_QWORD *)hDevice + 2), 36, qword_180CDBCC8, v134);
    v41 = (char *)lpMem[1];
LABEL_126:
    v43 = (HANDLE *)hDevice;
  }
  if ( !v41 )
  {
    v44 = 0;
LABEL_132:
    if ( v43 != &hDevice && (*((_BYTE *)v43 + 28) & 8) != 0 )
    {
      sub_1801C8638(v43[2], 37, qword_180CDBCC8, v134);
      v41 = (char *)lpMem[1];
      v43 = (HANDLE *)hDevice;
    }
    goto LABEL_135;
  }
  v44 = v41 + 176;
  if ( *((_QWORD *)v41 + 25) > 7u )
    v44 = (_QWORD *)*v44;
  if ( !v44 )
    goto LABEL_132;
LABEL_135:
  if ( !v41 )
  {
    LODWORD(v45) = 0;
    v130 = 0;
LABEL_140:
    if ( v43 != &hDevice && (*((_BYTE *)v43 + 28) & 8) != 0 )
    {
      sub_1801C8638(v43[2], 38, qword_180CDBCC8, v134);
      v41 = (char *)lpMem[1];
    }
    goto LABEL_143;
  }
  v45 = v41 + 112;
  v130 = (__int64)(v41 + 112);
  if ( *((_QWORD *)v41 + 17) > 7u )
  {
    v45 = (_QWORD *)*v45;
    v130 = (__int64)v45;
  }
  if ( !v45 )
    goto LABEL_140;
LABEL_143:
  if ( !v41 || !*((_QWORD *)v41 + 36) )
  {
    v46 = 0;
    goto LABEL_148;
  }
  v46 = v41 + 272;
  v145 = (__int64)(v41 + 272);
  if ( *((_QWORD *)v41 + 37) > 7u )
  {
    v46 = (_QWORD *)*v46;
LABEL_148:
    v145 = (__int64)v46;
  }
  if ( !a7 )
  {
    FileTime = 0;
    if ( v41 && v41 != (char *)-696LL && SystemTimeToFileTime((const SYSTEMTIME *)(v41 + 696), &FileTime) )
      v9 = (__int64)FileTime;
    if ( (unsigned __int8)sub_1804FA100(v133, (_DWORD)v44, (_DWORD)v45, (_DWORD)v42, (__int64)v46, v9) )
    {
      v113 = 1;
      v17 = 0;
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
      {
        if ( lpMem[1] )
        {
          v47 = (char *)lpMem[1] + 504;
          if ( *((_QWORD *)lpMem[1] + 66) > 7u )
            v47 = (_QWORD *)*v47;
        }
        else
        {
          v47 = 0;
        }
        sub_1801C8694(*((_QWORD *)hDevice + 2), 39, (unsigned int)qword_180CDBCC8, (_DWORD)v134, (__int64)v47);
      }
      if ( (!dword_18100F574 || (unsigned __int8)(byte_18100F578 - 1) <= 2u) && !byte_18105B1F4 )
        goto LABEL_176;
      if ( lpMem[1] )
      {
        v48 = (char *)lpMem[1] + 504;
        if ( *((_QWORD *)lpMem[1] + 66) > 7u )
          v48 = (_QWORD *)*v48;
      }
      else
      {
        v48 = 0;
      }
      if ( (int)sub_1801A5F5C(
                  v157,
                  512,
                  L"%ls is not trusted, because the certificate is revoked. Signing time = %ls",
                  v134,
                  v48) < 0 )
      {
        if ( (dword_181042B40 & 1) == 0 && !byte_18105B1F4 )
          goto LABEL_176;
        *(_QWORD *)&v155 = L"String too long";
        *((_QWORD *)&v155 + 1) = 32;
      }
      else
      {
        if ( (dword_181042B40 & 1) == 0 && !byte_18105B1F4 )
          goto LABEL_176;
        v49 = -1;
        do
          ++v49;
        while ( v157[v49] );
        *(_QWORD *)&v155 = v157;
        *((_QWORD *)&v155 + 1) = (unsigned int)(2 * v49 + 2);
      }
      sub_1801A6064(&qword_18100F550, qword_180C18850, v13, 2, &v153);
LABEL_176:
      v18 = 0;
      v16 = 0;
      goto LABEL_177;
    }
  }
  FileTime = 0;
  v146 = xmmword_180C1BC40;
  LODWORD(v147) = 151509167;
  if ( (unsigned int)sub_1804EE6B8(v133, v42, &FileTime, &v146) == 1 )
  {
    v18 = 1;
    if ( (!dword_18100F574 || (unsigned __int8)(byte_18100F578 - 1) <= 2u) && !byte_18105B1F4 )
      goto LABEL_217;
    if ( (int)sub_1801A5F5C(
                v157,
                512,
                L"%ls is not trusted, because the certificate is excluded (thumbprint=%ls, sigseq=0x%016llx).",
                v134,
                v42,
                FileTime) < 0 )
    {
      if ( (dword_181042B40 & 1) == 0 && !byte_18105B1F4 )
        goto LABEL_217;
      *(_QWORD *)&v155 = L"String too long";
      *((_QWORD *)&v155 + 1) = 32;
    }
    else
    {
      if ( (dword_181042B40 & 1) == 0 && !byte_18105B1F4 )
        goto LABEL_217;
      v57 = -1;
      do
        ++v57;
      while ( v157[v57] );
      *(_QWORD *)&v155 = v157;
      *((_QWORD *)&v155 + 1) = (unsigned int)(2 * v57 + 2);
    }
    sub_1801A6064(&qword_18100F550, qword_180C18850, v13, 2, &v153);
LABEL_217:
    v17 = 0;
    *v110 = 0;
    v16 = 0;
LABEL_177:
    v50 = a5;
    if ( !a5 )
      goto LABEL_178;
    goto LABEL_223;
  }
  v50 = a5;
  if ( !a5 )
  {
    v17 = 1;
    goto LABEL_179;
  }
  if ( !v137 )
  {
    v61 = lpMem[1];
    if ( !lpMem[1] || !*((_BYTE *)lpMem[1] + 730) )
    {
LABEL_283:
      v73 = (HANDLE *)hDevice;
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
      {
        sub_1801C8694(*((_QWORD *)hDevice + 2), 43, (unsigned int)qword_180CDBCC8, (_DWORD)v134, (__int64)v44);
        v61 = lpMem[1];
        v73 = (HANDLE *)hDevice;
      }
      v112 = 0;
      v74 = 0;
      if ( !v61 )
        goto LABEL_339;
      v75 = (char *)(v61 + 67);
      v76 = (char *)(v61 + 67);
      if ( v61[70] > 7u )
        v76 = *(char **)v75;
      if ( !v76 )
        goto LABEL_312;
      v77 = (char *)(v61 + 67);
      if ( v61[70] > 7u )
        v77 = *(char **)v75;
      v78 = -1;
      do
        ++v78;
      while ( *(_WORD *)&v77[2 * v78] );
      if ( v78 == 64 )
      {
        v79 = (char *)(v61 + 67);
        if ( v61[70] > 7u )
          v79 = *(char **)v75;
        if ( (unsigned __int8)sub_1808AC8D8(&v153, 32, v79) )
        {
          if ( qword_181052D80 )
          {
            *(_QWORD *)&v146 = 0;
            DWORD2(v146) = 156;
            v147 = &v153;
            if ( (unsigned int)sub_18072E140(v81, v80, &v146, &v112) == 1 )
            {
              v82 = hDevice;
              if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 2) == 0 )
                goto LABEL_332;
              if ( lpMem[1] )
              {
                v83 = (char *)lpMem[1] + 536;
                if ( *((_QWORD *)lpMem[1] + 70) > 7u )
                  v83 = *(char **)v83;
              }
              else
              {
                v83 = 0;
              }
              v84 = 44;
LABEL_331:
              sub_1801C8638(v82[2], v84, qword_180CDBCC8, v83);
LABEL_332:
              v74 = 1;
              v90 = 0;
              v107 = 1;
              LOBYTE(v127) = 0;
              v91 = v130;
              goto LABEL_342;
            }
          }
          goto LABEL_339;
        }
        if ( v73 == &hDevice || (*((_BYTE *)v73 + 28) & 2) == 0 )
          goto LABEL_339;
        if ( *((_QWORD *)v75 + 3) > 7u )
          v75 = *(char **)v75;
        v85 = 45;
      }
      else
      {
LABEL_312:
        v75 = (char *)(v61 + 71);
        v86 = v75;
        if ( *((_QWORD *)v75 + 3) > 7u )
          v86 = *(char **)v75;
        if ( !v86 )
          goto LABEL_339;
        v87 = v75;
        if ( *((_QWORD *)v75 + 3) > 7u )
          v87 = *(char **)v75;
        v88 = -1;
        do
          ++v88;
        while ( *(_WORD *)&v87[2 * v88] );
        if ( v88 != 40 )
          goto LABEL_339;
        v89 = v75;
        if ( *((_QWORD *)v75 + 3) > 7u )
          v89 = *(char **)v75;
        if ( (unsigned __int8)sub_1808AC8D8(&v146, 20, v89) )
        {
          if ( (unsigned int)sub_180743270(156, &v112, &v146, 0) == 1 )
          {
            v82 = hDevice;
            if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 2) == 0 )
              goto LABEL_332;
            if ( lpMem[1] )
            {
              v83 = (char *)lpMem[1] + 568;
              if ( *((_QWORD *)lpMem[1] + 74) > 7u )
                v83 = *(char **)v83;
            }
            else
            {
              v83 = 0;
            }
            v84 = 46;
            goto LABEL_331;
          }
LABEL_339:
          v91 = v130;
          v90 = sub_1804EEC68(v133, (_DWORD)v44, v130, (_DWORD)v42, v145, (__int64)v110, (__int64)v111, (__int64)&v112);
          v92 = (unsigned __int8)v127;
          if ( v90 == 1 )
            v92 = 1;
          v127 = v92;
LABEL_342:
          v109 = v90;
          v108[0] = 1;
          if ( (int)sub_18028CD04(L"MpDisableTrustedInstaller", v108) < 0
            && hDevice != &hDevice
            && (*((_BYTE *)hDevice + 28) & 2) != 0 )
          {
            sub_1801A1648(*((_QWORD *)hDevice + 2), 48, qword_180CDBCC8);
          }
          if ( v90 == 1 )
          {
            if ( v108[0] )
            {
LABEL_375:
              v16 = 0;
LABEL_376:
              v50 = a5;
              v17 = v109;
              v18 = v107;
              goto LABEL_223;
            }
            v93 = v112;
            if ( !v112 )
              goto LABEL_358;
            v94 = sub_1801D6BB0(v112);
            FileTime.dwLowDateTime = 0;
            v95 = sub_180743020(132, &FileTime, v94);
            v108[0] = 0;
            if ( (int)sub_18028CD04(L"MpAllowHighTrustInstallerOnAllPaths", v108) < 0
              && hDevice != &hDevice
              && (*((_BYTE *)hDevice + 28) & 2) != 0 )
            {
              sub_1801A1648(*((_QWORD *)hDevice + 2), 49, qword_180CDBCC8);
            }
            if ( !v140
              || (v95 != 1 || !v108[0])
              && !(unsigned __int8)sub_1805C84AC(v133, "MpIsCreateProcessScan", 0)
              && *(_DWORD *)(v133 + 8616) != 16 )
            {
              goto LABEL_358;
            }
            if ( *(_DWORD *)(v133 + 8552) == 2048 )
            {
              sub_1804FBB08(v133, (unsigned int)v93);
              goto LABEL_358;
            }
            if ( (unsigned __int8)sub_1805C84AC(v133, "BM_MpIsInstaller", 0) )
            {
              if ( v95 == 1 )
              {
                sub_180B1E5DC(v134, (unsigned int)v93, 64, 0);
                sub_1805C91FC(
                  v133,
                  (unsigned int)"BM_MpHighlyTrustedInstaller",
                  0,
                  (unsigned int)&xmmword_180C1BC40,
                  -1,
                  0);
                if ( (!dword_18100F574 || (unsigned __int8)(byte_18100F578 - 1) <= 2u) && !byte_18105B1F4 )
                  goto LABEL_375;
                if ( (int)sub_1801A5F5C(v157, 512, L"%ls is a high trust installer.", v134) >= 0 )
                {
                  if ( (dword_181042B40 & 1) == 0 && !byte_18105B1F4 )
                    goto LABEL_375;
                  v96 = -1;
                  do
                    ++v96;
                  while ( v157[v96] );
                  goto LABEL_373;
                }
LABEL_377:
                if ( (dword_181042B40 & 1) == 0 && !byte_18105B1F4 )
                  goto LABEL_375;
                *(_QWORD *)&v155 = L"String too long";
                *((_QWORD *)&v155 + 1) = 32;
                goto LABEL_374;
              }
              sub_180B1E5DC(v134, (unsigned int)v93, 8, 0);
              sub_1805C91FC(v133, (unsigned int)"BM_MpTrustedInstaller", 0, (unsigned int)&xmmword_180C1BC40, -1, 0);
              if ( (!dword_18100F574 || (unsigned __int8)(byte_18100F578 - 1) <= 2u) && !byte_18105B1F4 )
                goto LABEL_375;
              if ( (int)sub_1801A5F5C(v157, 512, L"%ls is a trusted installer.", v134) < 0 )
                goto LABEL_377;
              if ( (dword_181042B40 & 1) == 0 && !byte_18105B1F4 )
                goto LABEL_375;
              v96 = -1;
              do
                ++v96;
              while ( v157[v96] );
            }
            else
            {
              sub_1805C91FC(v133, (unsigned int)"BM_MpTrustedPotentialInstaller", *v110, (_DWORD)v111, -1, v93);
              if ( (!dword_18100F574 || (unsigned __int8)(byte_18100F578 - 1) <= 2u) && !byte_18105B1F4 )
                goto LABEL_375;
              if ( (int)sub_1801A5F5C(
                          v157,
                          512,
                          L"%ls is a trusted file that might be an installer (allowing deeper analysis).",
                          v134) < 0 )
                goto LABEL_377;
              if ( (dword_181042B40 & 1) == 0 && !byte_18105B1F4 )
                goto LABEL_375;
              v96 = -1;
              do
                ++v96;
              while ( v157[v96] );
            }
LABEL_373:
            *(_QWORD *)&v155 = v157;
            *((_QWORD *)&v155 + 1) = (unsigned int)(2 * v96 + 2);
LABEL_374:
            sub_1801A6064(&qword_18100F550, qword_180C18850, v13, 2, &v153);
            goto LABEL_375;
          }
          if ( v90 )
            goto LABEL_358;
          if ( lpMem[1] && *((_BYTE *)lpMem[1] + 728) && !v74 )
          {
LABEL_426:
            if ( !lpMem[1] || !*((_BYTE *)lpMem[1] + 728) )
            {
              v17 = v109;
              v16 = 0;
              goto LABEL_360;
            }
            if ( (*(_QWORD *)(v133 + 10640) & 0x4000000000000LL) == 0 )
            {
              v17 = 1;
              v58 = v110;
              *v110 = 0x7000000000LL;
              v59 = v111;
              *v111 = xmmword_180C1BC40;
              *((_DWORD *)v59 + 4) = 151509167;
              if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 8) == 0 )
              {
                v50 = a5;
                v16 = 0;
                v18 = v107;
                goto LABEL_225;
              }
              sub_1801A1648(*((_QWORD *)hDevice + 2), 51, qword_180CDBCC8);
              goto LABEL_359;
            }
            sub_1801B12FC(v133, L"BUILTIN:MpLinkedToMicrosoftRoot", 0x7000000000LL, &xmmword_180C1BC40);
LABEL_358:
            v17 = v109;
LABEL_359:
            v16 = 0;
LABEL_360:
            v50 = a5;
            v18 = v107;
            goto LABEL_223;
          }
          if ( (unsigned __int8)sub_1805C84AC(v133, "BM_MpIsInstaller", 0) )
          {
            if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 4) != 0 )
            {
              v97 = L"n/a";
              if ( v145 )
                v97 = (const char *)v145;
              v98 = L"n/a";
              if ( v42 )
                v98 = v42;
              v99 = L"n/a";
              if ( v91 )
                v99 = (const char *)v91;
              sub_18028F78C(*((_QWORD *)hDevice + 2), (__int64)v99, (__int64)v98, (__int64)v97);
            }
            if ( (sub_1805C91FC(
                    v133,
                    (unsigned int)"BM_MpIsInstallerSignedUntrusted",
                    0,
                    (unsigned int)&xmmword_180C1BC40,
                    -1,
                    0),
                  dword_18100F574)
              && (unsigned __int8)(byte_18100F578 - 1) > 2u
              || byte_18105B1F4 )
            {
              if ( (int)sub_1801A5F5C(v157, 512, L"%ls is an installer (but not trusted).", v134) < 0 )
              {
                if ( (dword_181042B40 & 1) != 0 || byte_18105B1F4 )
                {
                  *(_QWORD *)&v155 = L"String too long";
                  *((_QWORD *)&v155 + 1) = 32;
LABEL_424:
                  sub_1801A6064(&qword_18100F550, qword_180C18850, v13, 2, &v153);
                }
              }
              else if ( (dword_181042B40 & 1) != 0 || byte_18105B1F4 )
              {
                v100 = -1;
                do
                  ++v100;
                while ( v157[v100] );
                *(_QWORD *)&v155 = v157;
                *((_QWORD *)&v155 + 1) = (unsigned int)(2 * v100 + 2);
                goto LABEL_424;
              }
            }
          }
          if ( v74 )
          {
            v16 = 0;
            goto LABEL_376;
          }
          goto LABEL_426;
        }
        if ( v73 == &hDevice || (*((_BYTE *)v73 + 28) & 2) == 0 )
          goto LABEL_339;
        if ( *((_QWORD *)v75 + 3) > 7u )
          v75 = *(char **)v75;
        v85 = 47;
      }
      sub_1801C8638(v73[2], v85, qword_180CDBCC8, v75);
      goto LABEL_339;
    }
    sub_18060D58C((WCHAR *)&v146, v134, 0);
    if ( !v147 )
    {
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 2) != 0 )
        sub_1801C8638(*((_QWORD *)hDevice + 2), 41, qword_180CDBCC8, v10);
LABEL_282:
      sub_1801A5180(&v146);
      v61 = lpMem[1];
      goto LABEL_283;
    }
    FileTime = 0;
    v62 = sub_1803F7088(&FileTime);
    v63 = FileTime;
    if ( v62 >= 0 )
    {
      v64 = &v146;
      if ( v148 > 7 )
        v64 = (__int128 *)v146;
      if ( (*(unsigned __int8 (__fastcall **)(struct _FILETIME, __int128 *))(**(_QWORD **)&FileTime + 48LL))(
             FileTime,
             v64) )
      {
        if ( (unsigned __int8)sub_1801A4A54(0, v65, "Engine.ValidateTrust.CatalogSignedPaths") )
        {
          v66 = lpCriticalSection;
          if ( lpCriticalSection )
          {
            EnterCriticalSection(lpCriticalSection);
            if ( (unsigned int)dword_18100A408 <= 5
              || (qword_18100A418[0] & 0x400000000000LL) == 0
              || (qword_18100A418[1] & 0x400000000000LL) != qword_18100A418[1] )
            {
              goto LABEL_279;
            }
            FileTime.dwLowDateTime = *(_DWORD *)(qword_181040D08 + 72);
            v119 = *(_DWORD *)(qword_181040D08 + 68);
            v118 = *(_DWORD *)(qword_181040D08 + 64);
            v117 = *(unsigned __int8 *)(qword_181040D08 + 60);
            v116 = *(unsigned __int8 *)(qword_181040D08 + 59);
            v115 = *(unsigned __int8 *)(qword_181040D08 + 58);
            v114 = *(unsigned __int8 *)(qword_181040D08 + 57);
            v112 = *(unsigned __int8 *)(qword_181040D08 + 56);
            v129 = *(_QWORD *)(qword_181040D08 + 48);
            v128 = *(_QWORD *)(qword_181040D08 + 40);
            v120 = *(_QWORD *)(qword_181040D08 + 32);
            v121 = *(_QWORD *)(qword_181040D08 + 24);
            v122 = *(_QWORD *)(qword_181040D08 + 16);
            v123 = *(_QWORD *)(qword_181040D08 + 8);
            v67 = "WinDir";
            v68 = (char *)&dword_180F5EAE4;
LABEL_278:
            v125 = v67;
            v126 = 1;
            v124 = 0x1000000;
            sub_18000B4CC(
              (unsigned int)&dword_18100A408,
              (_DWORD)v68,
              (unsigned int)&dword_18100A408,
              (unsigned int)&v126,
              (__int64)&v125,
              (__int64)&v124,
              (__int64)&v123,
              (__int64)&v122,
              (__int64)&v121,
              (__int64)&v120,
              (__int64)&v128,
              (__int64)&v129,
              (__int64)&v112,
              (__int64)&v114,
              (__int64)&v115,
              (__int64)&v116,
              (__int64)&v117,
              (__int64)&v118,
              (__int64)&v119,
              (__int64)&FileTime);
LABEL_279:
            LeaveCriticalSection(v66);
          }
        }
      }
      else
      {
        v69 = &v146;
        if ( v148 > 7 )
          v69 = (__int128 *)v146;
        if ( (*(unsigned __int8 (__fastcall **)(struct _FILETIME, __int128 *))(**(_QWORD **)&v63 + 56LL))(v63, v69) )
        {
          if ( (unsigned __int8)sub_1801A4A54(0, v70, "Engine.ValidateTrust.CatalogSignedPaths") )
          {
            v66 = lpCriticalSection;
            if ( lpCriticalSection )
            {
              EnterCriticalSection(lpCriticalSection);
              if ( (unsigned int)dword_18100A408 <= 5
                || (qword_18100A418[0] & 0x400000000000LL) == 0
                || (qword_18100A418[1] & 0x400000000000LL) != qword_18100A418[1] )
              {
                goto LABEL_279;
              }
              FileTime.dwLowDateTime = *(_DWORD *)(qword_181040D08 + 72);
              v119 = *(_DWORD *)(qword_181040D08 + 68);
              v118 = *(_DWORD *)(qword_181040D08 + 64);
              v117 = *(unsigned __int8 *)(qword_181040D08 + 60);
              v116 = *(unsigned __int8 *)(qword_181040D08 + 59);
              v115 = *(unsigned __int8 *)(qword_181040D08 + 58);
              v114 = *(unsigned __int8 *)(qword_181040D08 + 57);
              v112 = *(unsigned __int8 *)(qword_181040D08 + 56);
              v129 = *(_QWORD *)(qword_181040D08 + 48);
              v128 = *(_QWORD *)(qword_181040D08 + 40);
              v120 = *(_QWORD *)(qword_181040D08 + 32);
              v121 = *(_QWORD *)(qword_181040D08 + 24);
              v122 = *(_QWORD *)(qword_181040D08 + 16);
              v123 = *(_QWORD *)(qword_181040D08 + 8);
              v67 = "ProgramFiles";
              v68 = byte_180F5E9DB;
              goto LABEL_278;
            }
          }
        }
        else
        {
          v71 = &v146;
          if ( v148 > 7 )
            v71 = (__int128 *)v146;
          if ( (*(unsigned __int8 (__fastcall **)(struct _FILETIME, __int128 *))(**(_QWORD **)&v63 + 64LL))(v63, v71) )
          {
            if ( (unsigned __int8)sub_1801A4A54(0, v72, "Engine.ValidateTrust.CatalogSignedPaths") )
            {
              v66 = lpCriticalSection;
              if ( lpCriticalSection )
              {
                EnterCriticalSection(lpCriticalSection);
                if ( (unsigned int)dword_18100A408 <= 5
                  || (qword_18100A418[0] & 0x400000000000LL) == 0
                  || (qword_18100A418[1] & 0x400000000000LL) != qword_18100A418[1] )
                {
                  goto LABEL_279;
                }
                FileTime.dwLowDateTime = *(_DWORD *)(qword_181040D08 + 72);
                v119 = *(_DWORD *)(qword_181040D08 + 68);
                v118 = *(_DWORD *)(qword_181040D08 + 64);
                v117 = *(unsigned __int8 *)(qword_181040D08 + 60);
                v116 = *(unsigned __int8 *)(qword_181040D08 + 59);
                v115 = *(unsigned __int8 *)(qword_181040D08 + 58);
                v114 = *(unsigned __int8 *)(qword_181040D08 + 57);
                v112 = *(unsigned __int8 *)(qword_181040D08 + 56);
                v129 = *(_QWORD *)(qword_181040D08 + 48);
                v128 = *(_QWORD *)(qword_181040D08 + 40);
                v120 = *(_QWORD *)(qword_181040D08 + 32);
                v121 = *(_QWORD *)(qword_181040D08 + 24);
                v122 = *(_QWORD *)(qword_181040D08 + 16);
                v123 = *(_QWORD *)(qword_181040D08 + 8);
                v67 = "ProgramFilesX86";
                v68 = (char *)word_180F5ECFA;
                goto LABEL_278;
              }
            }
          }
          else if ( (unsigned __int8)sub_1801A4A54(0, v72, "Engine.ValidateTrust.CatalogSignedPaths") )
          {
            v66 = lpCriticalSection;
            if ( lpCriticalSection )
            {
              EnterCriticalSection(lpCriticalSection);
              if ( (unsigned int)dword_18100A408 <= 5
                || (qword_18100A418[0] & 0x400000000000LL) == 0
                || (qword_18100A418[1] & 0x400000000000LL) != qword_18100A418[1] )
              {
                goto LABEL_279;
              }
              FileTime.dwLowDateTime = *(_DWORD *)(qword_181040D08 + 72);
              v119 = *(_DWORD *)(qword_181040D08 + 68);
              v118 = *(_DWORD *)(qword_181040D08 + 64);
              v117 = *(unsigned __int8 *)(qword_181040D08 + 60);
              v116 = *(unsigned __int8 *)(qword_181040D08 + 59);
              v115 = *(unsigned __int8 *)(qword_181040D08 + 58);
              v114 = *(unsigned __int8 *)(qword_181040D08 + 57);
              v112 = *(unsigned __int8 *)(qword_181040D08 + 56);
              v129 = *(_QWORD *)(qword_181040D08 + 48);
              v128 = *(_QWORD *)(qword_181040D08 + 40);
              v120 = *(_QWORD *)(qword_181040D08 + 32);
              v121 = *(_QWORD *)(qword_181040D08 + 24);
              v122 = *(_QWORD *)(qword_181040D08 + 16);
              v123 = *(_QWORD *)(qword_181040D08 + 8);
              v67 = "Other";
              v68 = byte_180F5EE03;
              goto LABEL_278;
            }
          }
        }
      }
    }
    if ( v63 )
      (*(void (__fastcall **)(struct _FILETIME))(**(_QWORD **)&v63 + 8LL))(v63);
    goto LABEL_282;
  }
  if ( (*(_QWORD *)(v133 + 10640) & 0x4000000000000LL) != 0 )
  {
    sub_1801B12FC(v133, L"BUILTIN:MpTrustedContent", 0x7000000001LL, &xmmword_180C1BC40);
    v17 = v109;
    v16 = v109;
    v18 = v109;
  }
  else
  {
    v17 = 1;
    v58 = v110;
    *v110 = 0x7000000001LL;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 8) == 0 )
    {
      v16 = 0;
      v18 = 0;
      goto LABEL_224;
    }
    sub_1801A1648(*((_QWORD *)hDevice + 2), 40, qword_180CDBCC8);
    v16 = 0;
    v18 = 0;
  }
LABEL_223:
  v58 = v110;
LABEL_224:
  v59 = v111;
LABEL_225:
  if ( !a7 && !v16 )
  {
    if ( !lpMem[1] || (v60 = (char *)lpMem[1] + 768, *((_QWORD *)lpMem[1] + 96) == *((_QWORD *)lpMem[1] + 97)) )
      v60 = 0;
    v106 = (__int64)v59;
    LOBYTE(v14) = v113;
    LOBYTE(v13) = v18;
    LOBYTE(v59) = v137;
    if ( (int)sub_1804FB5FC(v133, (_DWORD)v59, v13, v14, v127, *v58, v106, HIDWORD(v150), (__int64)v60) < 0
      && hDevice != &hDevice
      && (*((_BYTE *)hDevice + 28) & 8) != 0 )
    {
      sub_1801A1648(*((_QWORD *)hDevice + 2), 52, qword_180CDBCC8);
    }
  }
LABEL_178:
  if ( v17 == 1 )
  {
LABEL_179:
    v51 = "CI/EA";
    v52 = L"Unset";
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
    {
      v53 = "CI/EA";
      if ( !v137 )
        v53 = "DigitalSignature";
      v54 = L"Unset";
      if ( v134 )
        LODWORD(v54) = (_DWORD)v134;
      sub_180259F24(*((_QWORD *)hDevice + 2), 53, (unsigned int)qword_180CDBCC8, (_DWORD)v54, (__int64)v53);
    }
    if ( (!dword_18100F574 || (unsigned __int8)(byte_18100F578 - 1) <= 2u) && !byte_18105B1F4 )
      goto LABEL_456;
    if ( !v137 )
      v51 = "DigitalSignature";
    if ( v134 )
      v52 = v134;
    if ( (int)sub_1801A5F5C(v157, 512, L"%ls is trusted - %hs", v52, v51) >= 0 )
    {
      if ( (dword_181042B40 & 1) != 0 || byte_18105B1F4 )
      {
        v56 = -1;
        do
          ++v56;
        while ( v157[v56] );
        v55 = v157;
        *(_QWORD *)&v155 = v157;
LABEL_199:
        *((_QWORD *)&v155 + 1) = (unsigned int)(2 * v56 + 2);
LABEL_455:
        sub_1801A6064(&qword_18100F550, qword_180C18850, v55, 2, &v153);
        goto LABEL_456;
      }
      goto LABEL_456;
    }
LABEL_452:
    if ( (dword_181042B40 & 1) != 0 || byte_18105B1F4 )
    {
      *((_QWORD *)&v155 + 1) = 32;
      *(_QWORD *)&v155 = L"String too long";
      goto LABEL_455;
    }
    goto LABEL_456;
  }
  v101 = L"Unset";
  if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
  {
    v102 = L"Unset";
    if ( v134 )
      LODWORD(v102) = (_DWORD)v134;
    sub_1801A569C(*((_QWORD *)hDevice + 2), 54, (unsigned int)qword_180CDBCC8, (_DWORD)v102, v50);
  }
  if ( (!dword_18100F574 || (unsigned __int8)(byte_18100F578 - 1) <= 2u) && !byte_18105B1F4 )
    goto LABEL_456;
  if ( v134 )
    v101 = v134;
  LODWORD(v105) = v50;
  if ( (int)sub_1801A5F5C(v157, 512, L"%ls is NOT trusted. Checking Trust? %d", v101, v105) < 0 )
    goto LABEL_452;
  if ( (dword_181042B40 & 1) != 0 || byte_18105B1F4 )
  {
    v56 = -1;
    do
      ++v56;
    while ( v157[v56] );
    *(_QWORD *)&v155 = v157;
    goto LABEL_199;
  }
LABEL_456:
  lpMem[0] = &cert::`vftable';
  v103 = lpMem[1];
  if ( lpMem[1] )
  {
    sub_1802D2BCC(lpMem[1]);
    sub_18013F020(v103);
  }
  if ( v10 )
    sub_1801FF6A0(v10);
  return v17;
}

```

## disassembly

```asm
0x1804fbdb4  mov     [rsp-8+arg_8], rdx
0x1804fbdb9  push    rbp
0x1804fbdba  push    rbx
0x1804fbdbb  push    rsi
0x1804fbdbc  push    rdi
0x1804fbdbd  push    r12
0x1804fbdbf  push    r13
0x1804fbdc1  push    r14
0x1804fbdc3  push    r15
0x1804fbdc5  lea     rbp, [rsp-5B8h]
0x1804fbdcd  sub     rsp, 6E8h
0x1804fbdd4  mov     rax, cs:__security_cookie
0x1804fbddb  xor     rax, rsp
0x1804fbdde  mov     [rbp+5F0h+var_50], rax
0x1804fbde5  mov     [rbp+5F0h+var_660], r9
0x1804fbde9  mov     [rbp+5F0h+var_668], r8
0x1804fbded  mov     [rbp+5F0h+var_530], rcx
0x1804fbdf4  xor     ebx, ebx
0x1804fbdf6  mov     [rbp+5F0h+var_66C], ebx
0x1804fbdf9  mov     [rbp+5F0h+var_510], bl
0x1804fbdff  mov     [rbp+5F0h+var_528], rbx
0x1804fbe06  mov     edi, ebx
0x1804fbe08  mov     [rbp+5F0h+var_4B8], rbx
0x1804fbe0f  xorps   xmm0, xmm0
0x1804fbe12  movups  xmmword ptr [rbp+5F0h+lpMem], xmm0
0x1804fbe19  movups  [rbp+5F0h+var_4C8], xmm0
0x1804fbe20  lea     rax, ??_7cert@@6B@; const cert::`vftable'
0x1804fbe27  mov     [rbp+5F0h+lpMem], rax
0x1804fbe2e  mov     [rbp+5F0h+lpMem+8], rbx
0x1804fbe35  mov     word ptr [rbp+5F0h+var_4C8], bx
0x1804fbe3c  mov     qword ptr [rbp+5F0h+var_4C8+4], 1010h
0x1804fbe47  mov     [rbp+5F0h+var_50F], bl
0x1804fbe4d  lea     rdx, [rbp+5F0h+var_50F]
0x1804fbe54  lea     rcx, aMpdisabletrust_4; "MpDisableTrustCheckGetBrokenCert"
0x1804fbe5b  call    sub_18028CD04
0x1804fbe60  lea     rdx, hDevice
0x1804fbe67  lea     r13d, [rbx+2]
0x1804fbe6b  test    eax, eax
0x1804fbe6d  jns     short loc_1804FBE94
0x1804fbe6f  mov     rcx, cs:hDevice
0x1804fbe76  cmp     rcx, rdx
0x1804fbe79  jz      short loc_1804FBE94
0x1804fbe7b  test    [rcx+1Ch], r13b
0x1804fbe7f  jz      short loc_1804FBE94
0x1804fbe81  lea     edx, [rbx+14h]
0x1804fbe84  lea     r8, qword_180CDBCC8
0x1804fbe8b  mov     rcx, [rcx+10h]
0x1804fbe8f  call    sub_1801A1648
0x1804fbe94  cmp     [rbp+5F0h+var_50F], bl
0x1804fbe9a  setz    byte ptr [rbp+5F0h+var_4C8]
0x1804fbea1  mov     [rbp+5F0h+var_654], bl
0x1804fbea4  mov     [rbp+5F0h+var_670], bl
0x1804fbea7  mov     byte ptr [rbp+5F0h+var_600], bl
0x1804fbeaa  mov     [rbp+5F0h+var_66F], bl
0x1804fbead  mov     edx, 7
0x1804fbeb2  mov     rcx, [rbp+5F0h+var_530]
0x1804fbeb9  call    sub_1805C58F0
0x1804fbebe  mov     [rbp+5F0h+var_50F], al
0x1804fbec4  xor     edx, edx
0x1804fbec6  mov     rcx, [rbp+5F0h+var_530]
0x1804fbecd  call    sub_1805C58F0
0x1804fbed2  mov     r15b, al
0x1804fbed5  mov     edx, 6
0x1804fbeda  mov     rcx, [rbp+5F0h+var_530]
0x1804fbee1  call    sub_1805C58F0
0x1804fbee6  mov     [rbp+5F0h+var_50D], al
0x1804fbeec  or      r12, 0FFFFFFFFFFFFFFFFh
0x1804fbef0  mov     dl, [rbp+5F0h+var_50F]
0x1804fbef6  test    dl, dl
0x1804fbef8  jnz     short loc_1804FBF17
0x1804fbefa  test    r15b, r15b
0x1804fbefd  jnz     short loc_1804FBF17
0x1804fbeff  test    al, al
0x1804fbf01  jnz     short loc_1804FBF17
0x1804fbf03  mov     esi, 1
0x1804fbf08  mov     al, sil
0x1804fbf0b  mov     r15d, [rbp+5F0h+var_66C]
0x1804fbf0f  mov     r13b, r15b
0x1804fbf12  jmp     loc_1804FCCF1
0x1804fbf17  mov     [rbp+5F0h+var_66E], bl
0x1804fbf1a  mov     rcx, [rbp+5F0h+var_530]
0x1804fbf21  mov     rax, [rcx+20C0h]
0x1804fbf28  test    rax, rax
0x1804fbf2b  jz      short loc_1804FBF5A
0x1804fbf2d  lea     rcx, [rax+98h]
0x1804fbf34  lea     r8, [rbp+5F0h+var_66E]
0x1804fbf38  lea     rdx, aMpvolatileobje; "MpVolatileObject"
0x1804fbf3f  call    sub_180343DB0
0x1804fbf44  test    eax, eax
0x1804fbf46  jnz     short loc_1804FBF4D
0x1804fbf48  cmp     [rbp+5F0h+var_66E], bl
0x1804fbf4b  jnz     short loc_1804FBF03
0x1804fbf4d  mov     dl, [rbp+5F0h+var_50F]
0x1804fbf53  mov     rcx, [rbp+5F0h+var_530]
0x1804fbf5a  mov     esi, 1
0x1804fbf5f  test    dl, dl
0x1804fbf61  jz      short loc_1804FBF9B
0x1804fbf63  lea     r8d, [rsi+9]; MaxCount
0x1804fbf67  lea     rdx, aProcess_1; "process://"
0x1804fbf6e  mov     rcx, [rcx+78h]; Str1
0x1804fbf72  call    wcsncmp
0x1804fbf77  test    eax, eax
0x1804fbf79  jnz     short loc_1804FBF08
0x1804fbf7b  mov     rax, [rbp+5F0h+var_530]
0x1804fbf82  mov     rcx, [rax+78h]
0x1804fbf86  add     rcx, 14h
0x1804fbf8a  call    sub_18060DA54
0x1804fbf8f  mov     [rbp+5F0h+var_528], rax
0x1804fbf96  jmp     loc_1804FC326
0x1804fbf9b  mov     rcx, [rcx+70h]
0x1804fbf9f  call    sub_18060DA54
0x1804fbfa4  mov     [rbp+5F0h+var_528], rax
0x1804fbfab  mov     rcx, [rbp+5F0h+var_530]
0x1804fbfb2  call    sub_1805C4A50
0x1804fbfb7  cmp     rax, rsi
0x1804fbfba  jz      loc_1804FC326
0x1804fbfc0  cmp     [rbp+5F0h+arg_28], bl
0x1804fbfc6  jnz     loc_1804FC326
0x1804fbfcc  cmp     cs:byte_18105B1F4, bl
0x1804fbfd2  jnz     loc_1804FC326
0x1804fbfd8  cmp     cs:dword_181011320, 8
0x1804fbfdf  jb      short loc_1804FBFED
0x1804fbfe1  mov     rax, cs:qword_181011318
0x1804fbfe8  mov     rbx, [rax]
0x1804fbfeb  jmp     short loc_1804FBFF2
0x1804fbfed  mov     ebx, 2000000h
0x1804fbff2  xor     r14d, r14d
0x1804fbff5  mov     [rbp+5F0h+var_500], r14
0x1804fbffc  mov     rcx, [rbp+5F0h+var_530]
0x1804fc003  call    sub_1805C49CC
0x1804fc008  mov     rcx, rax
0x1804fc00b  mov     rax, [rax]
0x1804fc00e  lea     rdx, [rbp+5F0h+var_500]
0x1804fc015  mov     rax, [rax+48h]
0x1804fc019  call    cs:__guard_dispatch_icall_fptr
0x1804fc01f  test    eax, eax
0x1804fc021  js      loc_1804FC324
0x1804fc027  test    rbx, rbx
0x1804fc02a  jz      loc_1804FC324
0x1804fc030  cmp     [rbp+5F0h+var_500], rbx
0x1804fc037  jb      loc_1804FC324
0x1804fc03d  lea     r8, aEngineValidate_0; "Engine.ValidateTrust.TrustSkipTooBig"
0x1804fc044  xor     ecx, ecx
0x1804fc046  call    sub_1801A4A54
0x1804fc04b  xor     ebx, ebx
0x1804fc04d  test    al, al
0x1804fc04f  jz      loc_1804FC1FC
0x1804fc055  mov     rbx, cs:lpCriticalSection
0x1804fc05c  test    rbx, rbx
0x1804fc05f  jz      loc_1804FC1FA
0x1804fc065  mov     rcx, rbx; lpCriticalSection
0x1804fc068  call    EnterCriticalSection
0x1804fc06d  mov     r8, cs:off_180BC77E0
0x1804fc074  cmp     dword ptr [r8], 5
0x1804fc078  jbe     loc_1804FC1F2
0x1804fc07e  mov     rcx, 400000000000h
0x1804fc088  test    [r8+10h], rcx
0x1804fc08c  jz      loc_1804FC1F2
0x1804fc092  mov     rax, [r8+18h]
0x1804fc096  and     rax, rcx
0x1804fc099  cmp     rax, [r8+18h]
0x1804fc09d  jnz     loc_1804FC1F2
0x1804fc0a3  lea     rax, aSkiptoobig; "SkipTooBig"
0x1804fc0aa  mov     [rbp+5F0h+var_5E8], rax
0x1804fc0ae  lea     rax, aTrustcheck; "TrustCheck"
0x1804fc0b5  mov     [rbp+5F0h+var_608], rax
0x1804fc0b9  mov     rcx, cs:qword_181040D08
0x1804fc0c0  mov     eax, [rcx+48h]
0x1804fc0c3  mov     [rbp+5F0h+var_658], eax
0x1804fc0c6  mov     eax, [rcx+44h]
0x1804fc0c9  mov     [rbp+5F0h+var_650], eax
0x1804fc0cc  mov     eax, [rcx+40h]
0x1804fc0cf  mov     [rbp+5F0h+var_64C], eax
0x1804fc0d2  movzx   eax, byte ptr [rcx+3Ch]
0x1804fc0d6  mov     [rbp+5F0h+var_648], eax
0x1804fc0d9  movzx   eax, byte ptr [rcx+3Bh]
0x1804fc0dd  mov     [rbp+5F0h+var_644], eax
0x1804fc0e0  movzx   eax, byte ptr [rcx+3Ah]
0x1804fc0e4  mov     [rbp+5F0h+var_640], eax
0x1804fc0e7  movzx   eax, byte ptr [rcx+39h]
0x1804fc0eb  mov     [rbp+5F0h+var_63C], eax
0x1804fc0ee  movzx   eax, byte ptr [rcx+38h]
0x1804fc0f2  mov     [rbp+5F0h+FileTime.dwLowDateTime], eax
0x1804fc0f8  mov     rax, [rcx+30h]
0x1804fc0fc  mov     [rbp+5F0h+var_610], rax
0x1804fc100  mov     rax, [rcx+28h]
0x1804fc104  mov     [rbp+5F0h+var_618], rax
0x1804fc108  mov     rax, [rcx+20h]
0x1804fc10c  mov     [rbp+5F0h+var_620], rax
0x1804fc110  mov     rax, [rcx+18h]
0x1804fc114  mov     [rbp+5F0h+var_628], rax
0x1804fc118  mov     rax, [rcx+10h]
0x1804fc11c  mov     [rbp+5F0h+var_630], rax
0x1804fc120  mov     rax, [rcx+8]
0x1804fc124  mov     [rbp+5F0h+var_638], rax
0x1804fc128  mov     [rbp+5F0h+var_5F8], 1000000h
0x1804fc130  mov     [rbp+5F0h+var_5F0], rsi
0x1804fc134  lea     rax, [rbp+5F0h+var_5E8]
0x1804fc138  mov     [rsp+720h+var_680], rax
0x1804fc140  lea     rax, [rbp+5F0h+var_608]
0x1804fc144  mov     [rsp+720h+var_688], rax
0x1804fc14c  lea     rax, [rbp+5F0h+var_658]
0x1804fc150  mov     [rsp+720h+var_690], rax
0x1804fc158  lea     rax, [rbp+5F0h+var_650]
0x1804fc15c  mov     [rsp+720h+var_698], rax
0x1804fc164  lea     rax, [rbp+5F0h+var_64C]
0x1804fc168  mov     [rsp+720h+var_6A0], rax
0x1804fc170  lea     rax, [rbp+5F0h+var_648]
0x1804fc174  mov     [rsp+720h+var_6A8], rax
0x1804fc179  lea     rax, [rbp+5F0h+var_644]
0x1804fc17d  mov     [rsp+720h+var_6B0], rax
0x1804fc182  lea     rax, [rbp+5F0h+var_640]
0x1804fc186  mov     [rsp+720h+var_6B8], rax
0x1804fc18b  lea     rax, [rbp+5F0h+var_63C]
0x1804fc18f  mov     [rsp+720h+var_6C0], rax
0x1804fc194  lea     rax, [rbp+5F0h+FileTime]
0x1804fc19b  mov     [rsp+720h+var_6C8], rax
0x1804fc1a0  lea     rax, [rbp+5F0h+var_610]
0x1804fc1a4  mov     [rsp+720h+var_6D0], rax
0x1804fc1a9  lea     rax, [rbp+5F0h+var_618]
0x1804fc1ad  mov     [rsp+720h+var_6D8], rax
0x1804fc1b2  lea     rax, [rbp+5F0h+var_620]
0x1804fc1b6  mov     [rsp+720h+var_6E0], rax
0x1804fc1bb  lea     rax, [rbp+5F0h+var_628]
0x1804fc1bf  mov     [rsp+720h+var_6E8], rax
0x1804fc1c4  lea     rax, [rbp+5F0h+var_630]
0x1804fc1c8  mov     [rsp+720h+var_6F0], rax
0x1804fc1cd  lea     rax, [rbp+5F0h+var_638]
0x1804fc1d1  mov     [rsp+720h+var_6F8], rax
0x1804fc1d6  lea     rax, [rbp+5F0h+var_5F8]
0x1804fc1da  mov     [rsp+720h+var_700], rax
0x1804fc1df  lea     r9, [rbp+5F0h+var_5F0]
0x1804fc1e3  lea     rdx, byte_180F5EBED
0x1804fc1ea  mov     rcx, r8
0x1804fc1ed  call    sub_1800062D0
0x1804fc1f2  mov     rcx, rbx; lpCriticalSection
0x1804fc1f5  call    LeaveCriticalSection
0x1804fc1fa  xor     ebx, ebx
0x1804fc1fc  mov     r10, cs:hDevice
0x1804fc203  lea     rdx, hDevice
0x1804fc20a  cmp     r10, rdx
0x1804fc20d  jz      short loc_1804FC236
0x1804fc20f  test    byte ptr [r10+1Ch], 8
0x1804fc214  jz      short loc_1804FC236
0x1804fc216  mov     edx, 17h
0x1804fc21b  mov     r9, [rbp+5F0h+var_530]
0x1804fc222  mov     r9, [r9+78h]
0x1804fc226  lea     r8, qword_180CDBCC8
0x1804fc22d  mov     rcx, [r10+10h]
0x1804fc231  call    sub_1801C8638
0x1804fc236  cmp     cs:dword_18100F574, ebx
0x1804fc23c  jz      short loc_1804FC24C
0x1804fc23e  mov     al, cs:byte_18100F578
0x1804fc244  sub     al, sil
0x1804fc247  cmp     al, r13b
0x1804fc24a  ja      short loc_1804FC258
0x1804fc24c  cmp     cs:byte_18105B1F4, bl
0x1804fc252  jz      loc_1804FC316
0x1804fc258  mov     r9, [rbp+5F0h+var_530]
0x1804fc25f  mov     r9, [r9+78h]
0x1804fc263  lea     r8, aFileLsIsTooLar; "File %ls is too large for the trusted c"...
0x1804fc26a  mov     edx, 200h
0x1804fc26f  lea     rcx, [rbp+5F0h+var_450]
0x1804fc276  call    sub_1801A5F5C
0x1804fc27b  test    eax, eax
0x1804fc27d  js      short loc_1804FC2CA
0x1804fc27f  test    byte ptr cs:dword_181042B40, sil
0x1804fc286  jnz     short loc_1804FC294
0x1804fc288  cmp     cs:byte_18105B1F4, bl
0x1804fc28e  jz      loc_1804FC316
0x1804fc294  lea     rcx, [rbp+5F0h+var_450]
0x1804fc29b  mov     rax, r12
0x1804fc29e  inc     rax
0x1804fc2a1  cmp     [rcx+rax*2], bx
0x1804fc2a5  jnz     short loc_1804FC29E
0x1804fc2a7  lea     rcx, [rbp+5F0h+var_450]
0x1804fc2ae  mov     qword ptr [rbp+5F0h+var_488], rcx
0x1804fc2b5  lea     eax, ds:2[rax*2]
0x1804fc2bc  mov     dword ptr [rbp+5F0h+var_488+8], eax
0x1804fc2c2  mov     dword ptr [rbp+5F0h+var_488+0Ch], ebx
0x1804fc2c8  jmp     short loc_1804FC2F4
0x1804fc2ca  test    byte ptr cs:dword_181042B40, sil
0x1804fc2d1  jnz     short loc_1804FC2DB
0x1804fc2d3  cmp     cs:byte_18105B1F4, bl
0x1804fc2d9  jz      short loc_1804FC316
0x1804fc2db  lea     rax, aStringTooLong_0; "String too long"
0x1804fc2e2  mov     qword ptr [rbp+5F0h+var_488], rax
0x1804fc2e9  mov     qword ptr [rbp+5F0h+var_488+8], 20h ; ' '
0x1804fc2f4  lea     rax, [rbp+5F0h+var_498]
0x1804fc2fb  mov     [rsp+720h+var_700], rax
0x1804fc300  mov     r9d, r13d
0x1804fc303  lea     rdx, qword_180C18850
0x1804fc30a  lea     rcx, qword_18100F550
0x1804fc311  call    sub_1801A6064
0x1804fc316  mov     al, sil
0x1804fc319  mov     r15d, r14d
0x1804fc31c  mov     r13b, r14b
0x1804fc31f  jmp     loc_1804FCCF1
0x1804fc324  xor     ebx, ebx
0x1804fc326  mov     rcx, [rbp+5F0h+var_530]
  ... truncated ...
```
