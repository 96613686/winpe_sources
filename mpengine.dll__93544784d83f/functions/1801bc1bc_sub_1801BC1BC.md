# sub_1801BC1BC

- ea: `0x1801bc1bc`
- end: `0x1801be204`
- name: `sub_1801BC1BC`
- size: `8264`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `65`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801a4b54`

## callees

- `0x1800030b0`
- `0x18001f740`
- `0x180078f38`
- `0x180079f60`
- `0x180079f80`
- `0x180079f88`
- `0x180079ff8`
- `0x18007d554`
- `0x18007e554`
- `0x18007e744`
- `0x18007f87c`
- `0x18007f8f4`
- `0x18007fd94`
- `0x18013f000`
- `0x18013f020`
- `0x1801655f0`
- `0x180165a14`
- `0x180165bbc`
- `0x180176270`
- `0x1801a08a8`
- `0x1801a1648`
- `0x1801a166c`
- `0x1801a4a54`
- `0x1801a5180`
- `0x1801a569c`
- `0x1801ad868`
- `0x1801adcd0`
- `0x1801ade20`
- `0x1801adf28`
- `0x1801ae0e8`
- `0x1801ae2c8`
- `0x1801ae3e8`
- `0x1801af2f0`
- `0x1801af950`
- `0x1801afb74`
- `0x1801afbd0`
- `0x1801b2ebc`
- `0x1801b47ec`
- `0x1801b48e0`
- `0x1801b689c`
- `0x1801b8bc8`
- `0x1801b9194`
- `0x1801bc1bc`
- `0x1801c6924`
- `0x1801c6a24`
- `0x1801c6f70`
- `0x1801c70e4`
- `0x1801c8060`
- `0x1801c8638`
- `0x1801ff6a0`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x1801bde77`
- `KERNEL32!GetComputerNameExW` at `0x1801bdee8`
- `KERNEL32!GetComputerNameExW` at `0x1801bde77`
- `KERNEL32!GetComputerNameExW` at `0x1801bdee8`
- `KERNEL32!ProcessIdToSessionId` at `0x1801bde05`
- `KERNEL32!ProcessIdToSessionId` at `0x1801bde05`
- `KERNEL32!GetSystemDefaultLCID` at `0x1801bc521`
- `KERNEL32!GetSystemDefaultLCID` at `0x1801bc521`
- `KERNEL32!GetSystemInfo` at `0x1801bc4fc`
- `KERNEL32!GetSystemInfo` at `0x1801bc4fc`
- `KERNEL32!GetProductInfo` at `0x1801bc4a6`
- `KERNEL32!GetProductInfo` at `0x1801bc4a6`
- `KERNEL32!GetCurrentProcessId` at `0x1801bddfa`
- `KERNEL32!GetCurrentProcessId` at `0x1801bddfa`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801bcdc5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801bcdc5`
- `KERNEL32!GetLastError` at `0x1801bde27`
- `KERNEL32!GetLastError` at `0x1801bde86`
- `KERNEL32!GetLastError` at `0x1801bdf04`
- `KERNEL32!GetLastError` at `0x1801bde27`
- `KERNEL32!GetLastError` at `0x1801bde86`
- `KERNEL32!GetLastError` at `0x1801bdf04`
- `ADVAPI32!RegCloseKey` at `0x1801bc441`
- `ADVAPI32!RegCloseKey` at `0x1801bcc3b`
- `ADVAPI32!RegCloseKey` at `0x1801bcc51`
- `ADVAPI32!RegCloseKey` at `0x1801bccc0`
- `ADVAPI32!RegCloseKey` at `0x1801bccd7`
- `ADVAPI32!RegCloseKey` at `0x1801bcd2f`
- `ADVAPI32!RegCloseKey` at `0x1801bcd97`
- `ADVAPI32!RegCloseKey` at `0x1801bcdab`
- `ADVAPI32!RegCloseKey` at `0x1801bd3cc`
- `ADVAPI32!RegCloseKey` at `0x1801bd7f0`
- `ADVAPI32!RegCloseKey` at `0x1801bd812`
- `ADVAPI32!RegCloseKey` at `0x1801be1d8`
- `ADVAPI32!RegCloseKey` at `0x1801bc441`
- `ADVAPI32!RegCloseKey` at `0x1801bcc3b`
- `ADVAPI32!RegCloseKey` at `0x1801bcc51`
- `ADVAPI32!RegCloseKey` at `0x1801bccc0`
- `ADVAPI32!RegCloseKey` at `0x1801bccd7`
- `ADVAPI32!RegCloseKey` at `0x1801bcd2f`
- `ADVAPI32!RegCloseKey` at `0x1801bcd97`
- `ADVAPI32!RegCloseKey` at `0x1801bcdab`
- `ADVAPI32!RegCloseKey` at `0x1801bd3cc`
- `ADVAPI32!RegCloseKey` at `0x1801bd7f0`
- `ADVAPI32!RegCloseKey` at `0x1801bd812`
- `ADVAPI32!RegCloseKey` at `0x1801be1d8`

## string_xrefs

- `0x1801bcd7e`: `InstallTime`

## pseudocode

```c
__int64 __fastcall sub_1801BC1BC(__int64 a1)
{
  __int64 v1; // r14
  char *v2; // rsi
  DWORD v3; // ebx
  int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // rax
  unsigned __int16 *v12; // rbx
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  HKEY v16; // rcx
  int v17; // eax
  char v18; // cl
  _DWORD *v19; // rbx
  char v20; // al
  int v21; // eax
  __int64 v22; // rdi
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 v34; // rbx
  __int64 v35; // rdx
  int v36; // ecx
  int v37; // eax
  int v38; // ecx
  int v39; // eax
  int v40; // edx
  int v41; // ecx
  int v42; // eax
  int v43; // ecx
  int v44; // eax
  int v45; // ecx
  int v46; // eax
  int v47; // ecx
  int v48; // edx
  __int64 v49; // rdi
  __int64 v50; // rdx
  int v51; // eax
  __int64 v52; // r8
  int v53; // ecx
  __int64 v54; // rcx
  unsigned __int8 *v55; // r9
  bool v56; // al
  __int16 v57; // ax
  int v58; // ecx
  __int64 v59; // r9
  HANDLE *v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rax
  bool v63; // dl
  int v64; // eax
  HKEY v65; // rcx
  int v66; // eax
  bool v67; // bl
  int v68; // eax
  HKEY v69; // rcx
  int v70; // eax
  bool v71; // bl
  int v72; // eax
  DWORD v73; // ebx
  HKEY v74; // rcx
  int v75; // eax
  int v76; // eax
  HKEY v77; // rcx
  int v78; // eax
  HKEY v79; // rbx
  __int64 v80; // rbx
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rdi
  _QWORD *v84; // rax
  char *v85; // rdi
  int v86; // eax
  HKEY v87; // rbx
  __int64 v88; // rax
  HKEY v89; // rdx
  HKEY v90; // rcx
  __int64 v91; // rax
  _QWORD *v92; // rcx
  __int64 v93; // rdx
  int v94; // eax
  int v95; // eax
  char v96; // al
  int v97; // eax
  bool v98; // zf
  char v99; // al
  _WORD *v100; // r8
  unsigned __int64 v101; // r9
  _QWORD *v102; // rcx
  __int64 v103; // rdx
  _QWORD *v104; // rcx
  __int64 v105; // rdx
  __int64 v106; // r9
  _WORD *v107; // r8
  unsigned __int64 v108; // r9
  volatile signed __int32 *v109; // rbx
  __int64 v110; // rcx
  unsigned int v111; // edx
  int v112; // eax
  int v113; // r8d
  unsigned int v114; // eax
  int v115; // r8d
  unsigned int v116; // eax
  __int64 v117; // rbx
  unsigned int v118; // edi
  volatile signed __int32 *v119; // rbx
  const wchar_t *v120; // r8
  unsigned __int64 i; // rbx
  __int64 v122; // rdx
  HKEY v123; // rax
  __int64 v124; // rdx
  struct _RTL_CRITICAL_SECTION *v125; // rbx
  unsigned __int16 *v126; // rdx
  __int64 v127; // rdx
  unsigned __int16 *v128; // rdx
  HKEY v129; // r8
  HKEY *j; // rbx
  char v131; // al
  __int64 v132; // rdx
  HKEY v133; // rcx
  HKEY v134; // rax
  __int64 v135; // rdx
  HKEY v136; // rcx
  HKEY v137; // rbx
  unsigned __int64 v138; // rcx
  __int64 v139; // rax
  HKEY v140; // rcx
  DWORD v141; // eax
  __m128i si128; // xmm6
  __int64 v143; // rbx
  __int64 v144; // rdx
  __int128 *v145; // rdx
  int v146; // ecx
  int v147; // ecx
  int v148; // ecx
  int v149; // ecx
  volatile signed __int32 *v150; // rbx
  DWORD CurrentProcessId; // eax
  DWORD LastError; // eax
  WCHAR **v153; // rdi
  unsigned __int64 k; // rbx
  __int64 v155; // rax
  WCHAR *v156; // rax
  DWORD v157; // eax
  __int64 v158; // rdx
  HKEY v159; // rcx
  __int64 v160; // rdx
  HKEY v161; // rcx
  __int64 v162; // rdx
  HKEY v163; // rcx
  HKEY v164; // rax
  volatile signed __int32 *v165; // rbx
  char v166; // al
  bool v167; // bl
  char v168[8]; // [rsp+B8h] [rbp-80h] BYREF
  __int128 v169; // [rsp+C0h] [rbp-78h] BYREF
  __int64 v170; // [rsp+D0h] [rbp-68h] BYREF
  int v171; // [rsp+D8h] [rbp-60h] BYREF
  int v172; // [rsp+DCh] [rbp-5Ch] BYREF
  int v173; // [rsp+E0h] [rbp-58h] BYREF
  int v174; // [rsp+E4h] [rbp-54h] BYREF
  int v175; // [rsp+E8h] [rbp-50h] BYREF
  char *v176; // [rsp+F0h] [rbp-48h] BYREF
  const char *v177; // [rsp+F8h] [rbp-40h] BYREF
  const char *v178; // [rsp+100h] [rbp-38h] BYREF
  __int64 v179; // [rsp+108h] [rbp-30h] BYREF
  __int64 v180; // [rsp+110h] [rbp-28h] BYREF
  __int64 v181; // [rsp+118h] [rbp-20h] BYREF
  __int64 v182; // [rsp+120h] [rbp-18h] BYREF
  __int64 v183; // [rsp+128h] [rbp-10h] BYREF
  __int64 v184; // [rsp+130h] [rbp-8h] BYREF
  __int64 v185; // [rsp+138h] [rbp+0h] BYREF
  __int64 v186; // [rsp+140h] [rbp+8h] BYREF
  _QWORD v187[2]; // [rsp+148h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+158h] [rbp+20h] BYREF
  HKEY v189; // [rsp+160h] [rbp+28h] BYREF
  DWORD nSize; // [rsp+168h] [rbp+30h] BYREF
  int v191; // [rsp+16Ch] [rbp+34h] BYREF
  int v192; // [rsp+170h] [rbp+38h] BYREF
  __int128 v193; // [rsp+178h] [rbp+40h] BYREF
  __m128i v194; // [rsp+188h] [rbp+50h]
  _SYSTEM_INFO SystemInfo; // [rsp+198h] [rbp+60h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+1C8h] [rbp+90h] BYREF
  unsigned __int16 v197; // [rsp+2DCh] [rbp+1A4h]
  unsigned __int16 v198; // [rsp+2DEh] [rbp+1A6h]
  __int16 v199; // [rsp+2E0h] [rbp+1A8h]
  char v200; // [rsp+2E2h] [rbp+1AAh]

  v1 = a1;
  v170 = a1;
  v2 = (char *)qword_18105B1D0;
  v176 = (char *)qword_18105B1D0;
  v3 = 0;
  if ( !qword_18105B1D0 )
    return 32780;
  v4 = sub_1801C70E4(qword_18105B1D0, a1);
  if ( v4 < 0 )
  {
    v5 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      return 32780;
    v6 = 222;
LABEL_14:
    sub_1801A166C(v5[2], v6, &stru_180C1BC18, (unsigned int)v4);
    return 32780;
  }
  v4 = sub_1801C6F70(v2, v1);
  if ( v4 < 0 )
  {
    v5 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      return 32780;
    v6 = 223;
    goto LABEL_14;
  }
  v4 = sub_1801C6924(v2, v1);
  if ( v4 < 0 )
  {
    v5 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      return 32780;
    v6 = 224;
    goto LABEL_14;
  }
  v8 = *(_QWORD *)(v1 + 136);
  v9 = -1;
  if ( v8 )
  {
    do
      ++v9;
    while ( *(_WORD *)(v8 + 2 * v9) );
    v10 = 2 * v9 + 2;
    v11 = sub_1801655F0(v10);
    v12 = (unsigned __int16 *)v11;
    if ( v11 )
      sub_180B74870(v11, v8, v10);
    *((_QWORD *)v2 + 11028) = v12;
    if ( !v12 )
      return 32775;
    v13 = sub_18007D554((UUID *)v2 + 5510, v12);
    v3 = 0;
    if ( v13 < 0 )
    {
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 2) != 0 )
        sub_1801A1648(*((_QWORD *)hDevice + 2), 225, &stru_180C1BC18);
      *((_OWORD *)v2 + 5510) = 0;
    }
  }
  sub_180B743D0(&VersionInformation, 0, 284);
  if ( (int)sub_180079FF8(&VersionInformation) < 0 )
  {
    v57 = sub_180079F88();
    v58 = HIBYTE(v57) | ((unsigned __int8)v57 << 16);
    *((_DWORD *)v2 + 728) = v58;
    *((_DWORD *)v2 + 737) = v58;
    *((_QWORD *)v2 + 369) = 0;
    *((_DWORD *)v2 + 740) = 0;
    v2[2876] = 0;
  }
  else
  {
    v14 = LOWORD(VersionInformation.dwMinorVersion) | (LOWORD(VersionInformation.dwMajorVersion) << 16);
    *((_DWORD *)v2 + 728) = v14;
    *((_DWORD *)v2 + 737) = v14;
    *((_DWORD *)v2 + 738) = v197;
    *((_DWORD *)v2 + 739) = VersionInformation.dwBuildNumber;
    hKey = 0;
    v15 = sub_18007FD94(&hKey, -2147483646, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 1);
    v16 = hKey;
    if ( v15 >= 0 )
    {
      nSize = 0;
      v17 = sub_18007F87C(hKey, L"UBR", &nSize);
      v16 = hKey;
      if ( v17 >= 0 )
        v3 = nSize;
    }
    if ( v16 )
      RegCloseKey(v16);
    *((_DWORD *)v2 + 740) = v3;
    v18 = v199;
    v2[2876] = (v199 & 0x40) != 0;
    v2[2879] = (v18 & 0x10) != 0;
    v2[2902] = v200 == 2;
    v19 = v2 + 2964;
    if ( GetProductInfo(
           VersionInformation.dwMajorVersion,
           VersionInformation.dwMinorVersion,
           v197,
           v198,
           (PDWORD)v2 + 741) )
    {
      if ( *v19 == 178 || (v20 = 0, *v19 == 179) )
        v20 = 1;
      v2[2880] = v20;
    }
    v21 = *(_DWORD *)(v1 + 376);
    if ( v21 == 1 )
    {
      v2[2878] = 1;
    }
    else if ( v21 == 2 || (v56 = v200 != 1, v2[2878] = v200 != 1, v56) && *v19 == 175 )
    {
      v2[2878] = 0;
    }
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  *((_DWORD *)v2 + 729) = SystemInfo.wProcessorArchitecture;
  *((_DWORD *)v2 + 730) = SystemInfo.dwPageSize;
  *((_DWORD *)v2 + 731) = SystemInfo.dwAllocationGranularity;
  *((_DWORD *)v2 + 727) = GetSystemDefaultLCID();
  *((_DWORD *)v2 + 743) = 8;
  v22 = *(_QWORD *)(v1 + 144);
  if ( v22 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(v22 + 2 * v23) );
    v189 = (HKEY)(2 * v23 + 2);
    v24 = sub_1801655F0(v189);
    v25 = v24;
    if ( v24 )
      sub_180B74870(v24, v22, v189);
    *((_QWORD *)v2 + 11029) = v25;
  }
  v26 = *(_QWORD *)(v1 + 152);
  if ( v26 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(v26 + 2 * v27) );
    v189 = (HKEY)(2 * v27 + 2);
    v28 = sub_1801655F0(v189);
    v29 = v28;
    if ( v28 )
      sub_180B74870(v28, v26, v189);
    *((_QWORD *)v2 + 11030) = v29;
  }
  v30 = *(_QWORD *)(v1 + 160);
  if ( v30 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *(_WORD *)(v30 + 2 * v31) );
    v189 = (HKEY)(2 * v31 + 2);
    v32 = sub_1801655F0(v189);
    v33 = v32;
    if ( v32 )
      sub_180B74870(v32, v30, v189);
    *((_QWORD *)v2 + 11031) = v33;
  }
  v34 = *((_QWORD *)v2 + 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(v34 + 24));
  v35 = *(_QWORD *)(v34 + 8);
  *(_DWORD *)(v35 + 16) = *(_DWORD *)(v1 + 88);
  *(_DWORD *)(v35 + 20) = *(_DWORD *)(v35 + 20) & 0xFFFFFFFE | (*(_DWORD *)(v1 + 48) >> 11) & 1;
  *(_BYTE *)(v35 + 31) = (*(_DWORD *)(v1 + 48) & 0x200000) != 0;
  *(_DWORD *)(v35 + 24) = *(_DWORD *)(v1 + 112);
  *(_BYTE *)(v35 + 28) = *(_DWORD *)(v1 + 220) != 0;
  *(_BYTE *)(v35 + 29) = (*(_BYTE *)(v1 + 216) & 1) == 0;
  *(_BYTE *)(v35 + 30) = (*(_DWORD *)(v1 + 216) & 2) == 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v34 + 24));
  v36 = *((_DWORD *)v2 + 692) ^ (*(_DWORD *)(v1 + 48) ^ *((_DWORD *)v2 + 692)) & 1;
  *((_DWORD *)v2 + 692) = v36;
  v37 = v36 ^ (*(_DWORD *)(v1 + 48) ^ v36) & 2;
  *((_DWORD *)v2 + 692) = v37;
  v38 = v37 ^ (*(_DWORD *)(v1 + 48) ^ v37) & 4;
  *((_DWORD *)v2 + 692) = v38;
  v39 = v38 ^ ((unsigned __int8)v38 ^ (unsigned __int8)(*(_DWORD *)(v1 + 48) >> 1)) & 8;
  *((_DWORD *)v2 + 692) = v39;
  v40 = v39 ^ ((unsigned __int8)v39 ^ (unsigned __int8)(*(_DWORD *)(v1 + 48) >> 1)) & 0x10;
  *((_DWORD *)v2 + 692) = v40;
  v41 = v40 ^ ((unsigned __int8)v40 ^ (unsigned __int8)(*(_DWORD *)(v1 + 48) >> 1)) & 0x20;
  *((_DWORD *)v2 + 692) = v41;
  v42 = v41 ^ ((unsigned __int8)v41 ^ (unsigned __int8)(*(_DWORD *)(v1 + 48) >> 1)) & 0x40;
  *((_DWORD *)v2 + 692) = v42;
  v43 = v42 ^ ((unsigned __int8)v42 ^ (unsigned __int8)(*(_DWORD *)(v1 + 48) >> 7)) & 0x80;
  *((_DWORD *)v2 + 692) = v43;
  v44 = v43 ^ (*(_DWORD *)(v1 + 48) ^ v43) & 0x100;
  *((_DWORD *)v2 + 692) = v44;
  v45 = v44 ^ (*(_DWORD *)(v1 + 48) ^ v44) & 0x200;
  *((_DWORD *)v2 + 692) = v45;
  v46 = v45 ^ (*(_DWORD *)(v1 + 48) ^ v45) & 0x400;
  *((_DWORD *)v2 + 692) = v46;
  v47 = v46 ^ ((unsigned __int16)v46 ^ (unsigned __int16)(*(_DWORD *)(v1 + 48) >> 1)) & 0x800;
  *((_DWORD *)v2 + 692) = v47;
  v48 = v47 ^ ((unsigned __int16)v47 ^ (unsigned __int16)(*(_DWORD *)(v1 + 48) >> 1)) & 0x1000;
  *((_DWORD *)v2 + 692) = v48;
  *((_DWORD *)v2 + 692) = v48 ^ ((unsigned __int16)v48 ^ (unsigned __int16)(*(_DWORD *)(v1 + 48) >> 2)) & 0x2000;
  v2[2899] = (*(_DWORD *)(v1 + 48) & 0x100000) != 0;
  v2[2900] = (*(_DWORD *)(v1 + 48) & 0x400000) != 0;
  v2[2901] = (*(_DWORD *)(v1 + 48) & 0x800000) != 0;
  v2[3024] = *(_BYTE *)(v1 + 51) & 1;
  v2[3026] = (*(_DWORD *)(v1 + 48) & 0x2000000) != 0;
  v2[2904] = sub_1801B48E0();
  v2[2905] = sub_1801B47EC();
  v49 = 0;
  v2[3025] = *(_DWORD *)(v1 + 416) != 0;
  LOBYTE(v50) = 1;
  v51 = sub_1801B8BC8(v1, v50);
  v53 = 0;
  if ( v51 == 32817 )
    v53 = 0x4000;
  v54 = *((_DWORD *)v2 + 692) & 0xFFFFBFFF | v53;
  *((_DWORD *)v2 + 692) = v54;
  LODWORD(v54) = v54 & 0xFFFF7FFF;
  *((_DWORD *)v2 + 692) = v54 | (*(_DWORD *)(v1 + 48) >> 3) & 0x8000;
  *((_DWORD *)v2 + 22103) = *(_DWORD *)(v1 + 320);
  *((_QWORD *)v2 + 352) = *(_QWORD *)(v1 + 96);
  *((_QWORD *)v2 + 354) = *(_QWORD *)(v1 + 104);
  v55 = (unsigned __int8 *)(v2 + 2800);
  v189 = (HKEY)(v2 + 2800);
  if ( v2 == (char *)-2800LL )
    goto LABEL_68;
  if ( v1 == -72 )
  {
    *(_OWORD *)v55 = 0;
LABEL_68:
    *(_DWORD *)sub_180165BBC(v54, 0x4000, v52) = 22;
    invalid_parameter_noinfo();
    v55 = (unsigned __int8 *)(v2 + 2800);
    goto LABEL_69;
  }
  *(_OWORD *)v55 = *(_OWORD *)(v1 + 72);
LABEL_69:
  if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
  {
    sub_1801C8060(
      *((_QWORD *)hDevice + 2),
      227,
      (unsigned int)&stru_180C1BC18,
      *v55,
      *((_BYTE *)v189 + 1),
      *((_BYTE *)v189 + 2),
      *((_BYTE *)v189 + 3),
      v55[4],
      v55[5],
      v55[6],
      v55[7],
      v55[8],
      v55[9],
      v55[10],
      v55[11],
      v55[12],
      v55[13],
      v55[14],
      v55[15]);
    v2 = v176;
    v1 = v170;
    v49 = 0;
  }
  if ( !*(_DWORD *)(v1 + 168) )
  {
    v2[2872] = *(_BYTE *)(v1 + 50) & 1;
    goto LABEL_81;
  }
  v59 = *(unsigned int *)(v1 + 172);
  *((_DWORD *)v2 + 733) = v59;
  v2[2872] = *(_DWORD *)(v1 + 172) != 0;
  v60 = (HANDLE *)hDevice;
  if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
  {
    sub_1801A166C(*((_QWORD *)hDevice + 2), 228, &stru_180C1BC18, v59);
    v60 = (HANDLE *)hDevice;
  }
  if ( v2[2872] != (*(_BYTE *)(v1 + 50) & 1) )
  {
    if ( v60 == &hDevice )
      goto LABEL_85;
    if ( (*((_BYTE *)v60 + 28) & 8) != 0 )
    {
      sub_1801A166C(v60[2], 229, &stru_180C1BC18, *((unsigned int *)v2 + 733));
LABEL_81:
      v60 = (HANDLE *)hDevice;
    }
  }
  if ( v60 != &hDevice && (*((_BYTE *)v60 + 28) & 8) != 0 )
    sub_1801A166C(v60[2], 230, &stru_180C1BC18, (unsigned __int8)v2[2872]);
LABEL_85:
  *((_DWORD *)v2 + 22073) = 0;
  *((_DWORD *)v2 + 22080) = 0;
  v2[88280] = *(_DWORD *)v1 >= 0x8700u;
  v169 = 0;
  if ( qword_18105B1D0 && (v61 = *((_QWORD *)qword_18105B1D0 + 1)) != 0 )
    sub_1802ED594(v61, &v169);
  else
    v169 = 0;
  v62 = v169;
  if ( *(_DWORD *)(v169 + 16) == 3 )
    v2[2873] = 1;
  if ( (*(_DWORD *)(v62 + 32) & 0x1000) != 0 )
    v2[2874] = 1;
  if ( (*(_DWORD *)(v62 + 32) & 0x10000) == 0 )
    v2[2892] = 1;
  if ( (*(_DWORD *)(v62 + 32) & 0x8000) != 0 )
    v2[2891] = 1;
  if ( (*(_DWORD *)(v62 + 32) & 0x2000000) != 0 )
    v2[2893] = 1;
  if ( *((_WORD *)v2 + 1124) )
    v2[2875] = 1;
  sub_1801C6A24(v2, v1 + 72);
  v2[2877] = (*(_DWORD *)(v1 + 48) & 0x20000) != 0;
  v63 = (*(_DWORD *)(v1 + 48) & 0x80000) != 0;
  v2[2888] = v63;
  if ( *((_DWORD *)v2 + 712) != 1 )
  {
    if ( *((_DWORD *)v2 + 712) == 3
      || *((_DWORD *)v2 + 712) == 5
      || *((_DWORD *)v2 + 712) == 6
      || *((_DWORD *)v2 + 712) == 8
      || (v63 = 0, *((_DWORD *)v2 + 712) == 9) )
    {
      v63 = 1;
    }
  }
  v2[2881] = v63;
  hKey = 0;
  v64 = sub_18007FD94(&hKey, -2147483646, L"Software\\Policies\\Microsoft\\SQMClient", 1);
  v65 = hKey;
  if ( v64 >= 0 && (nSize = 0, v66 = sub_18007F87C(hKey, L"MSFTInternal", &nSize), v65 = hKey, v66 >= 0) )
  {
    v67 = nSize != 0;
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    if ( v65 )
      RegCloseKey(v65);
    v67 = 0;
  }
  v2[2882] = v67;
  *((_DWORD *)v2 + 734) = sub_1801AD868();
  v2[2896] = sub_1801AFB74(v2 + 2944);
  hKey = 0;
  v68 = sub_18007FD94(&hKey, -2147483646, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModelUnlock", 1);
  v69 = hKey;
  if ( v68 >= 0
    && (nSize = 0, v70 = sub_18007F87C(hKey, L"AllowDevelopmentWithoutDevLicense", &nSize), v69 = hKey, v70 >= 0) )
  {
    v71 = nSize == 1;
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    if ( v69 )
      RegCloseKey(v69);
    v71 = 0;
  }
  v2[2898] = v71;
  hKey = 0;
  v72 = sub_18007FD94(&hKey, -2147483646, L"SOFTWARE\\Policies\\Microsoft\\SQMClient\\WindowsPhone", 1);
  v73 = -1;
  v74 = hKey;
  if ( v72 >= 0 )
  {
    nSize = -1;
    v75 = sub_18007F87C(hKey, L"StudyId", &nSize);
    v74 = hKey;
    if ( v75 >= 0 )
      v73 = nSize;
  }
  if ( v74 )
    RegCloseKey(v74);
  *((_DWORD *)v2 + 735) = v73;
  if ( (unsigned int)sub_18007E744() )
    sub_1801AE2C8(v2 + 2897);
  hKey = 0;
  v76 = sub_18007FD94(&hKey, -2147483646, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 1);
  v77 = hKey;
  if ( v76 >= 0 && (v189 = 0, v78 = sub_18007F8F4(hKey, L"InstallTime", &v189), v77 = hKey, v78 >= 0) )
  {
    v79 = v189;
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    if ( v77 )
      RegCloseKey(v77);
    v79 = 0;
  }
  *((_QWORD *)v2 + 11033) = v79;
  if ( v79 )
  {
    hKey = 0;
    GetSystemTimeAsFileTime((LPFILETIME)&hKey);
    v189 = hKey;
    if ( (__int64)v79 < (__int64)hKey )
    {
      *((_QWORD *)v2 + 379) = ((char *)hKey - (char *)v79) / 0xC92A69C000uLL;
      *((_DWORD *)v2 + 760) = (unsigned __int64)v79 / 0x989680 + 1240428288;
    }
  }
  v80 = *(_QWORD *)(v1 + 192);
  if ( v80 )
  {
    v81 = -1;
    do
      ++v81;
    while ( *(_WORD *)(v80 + 2 * v81) );
    v189 = (HKEY)(2 * v81 + 2);
    v82 = sub_1801655F0(v189);
    v83 = v82;
    if ( v82 )
      sub_180B74870(v82, v80, v189);
    v84 = v2 + 88304;
    *((_QWORD *)v2 + 11038) = v83;
    v85 = 0;
    goto LABEL_159;
  }
  v189 = 0;
  v86 = sub_1801B2EBC(&v189);
  v87 = v189;
  if ( v86 < 0 )
  {
    v90 = (HKEY)sub_1801ADE20();
    hKey = v90;
    if ( v90 )
    {
      v91 = -1;
      do
        ++v91;
      while ( *((_WORD *)v90 + v91) );
      v189 = (HKEY)(2 * v91 + 2);
      v49 = sub_1801655F0(v189);
      if ( v49 )
      {
        v89 = hKey;
        goto LABEL_156;
      }
    }
  }
  else if ( v189 )
  {
    v88 = -1;
    do
      ++v88;
    while ( *((_WORD *)v189 + v88) );
    v189 = (HKEY)(2 * v88 + 2);
    v49 = sub_1801655F0(v189);
    if ( v49 )
    {
      v89 = v87;
LABEL_156:
      sub_180B74870(v49, v89, v189);
    }
  }
  v84 = v2 + 88304;
  *((_QWORD *)v2 + 11038) = v49;
  v85 = 0;
  if ( v87 )
  {
    sub_1801FF6A0(v87);
    v84 = v2 + 88304;
  }
LABEL_159:
  if ( !*v84 )
  {
    v92 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_466;
    v93 = 231;
    goto LABEL_465;
  }
  v2[2894] = *(_DWORD *)(v1 + 200) != 0;
  v94 = *(_DWORD *)(v1 + 184);
  if ( v94 )
  {
    v95 = v94 - 100;
    *((_DWORD *)v2 + 22071) = v95;
    v96 = v95 == 1 || v95 == 3;
  }
  else
  {
    *((_DWORD *)v2 + 22071) = -1;
    v96 = sub_1801AF2F0();
  }
  v2[2889] = v96;
  *((_DWORD *)v2 + 22072) = *(_DWORD *)(v1 + 188);
  v97 = *(_DWORD *)(v1 + 224);
  *((_DWORD *)v2 + 22074) = v97;
  if ( v97 == 1 || (v98 = v97 == 2, v99 = 0, v98) )
    v99 = 1;
  v2[2887] = v99;
  v2[2895] = *(_DWORD *)(v1 + 228) != 0;
  v2[89040] = *(_DWORD *)(v1 + 448) != 0;
  v2[89041] = *(_DWORD *)(v1 + 452) != 0;
  *((_WORD *)v2 + 44164) = 0;
  v100 = *(_WORD **)(v1 + 280);
  if ( v100 && *v100 )
  {
    v101 = -1;
    do
      ++v101;
    while ( v100[v101] );
    if ( v101 >= 0x13 )
    {
      v102 = hDevice;
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      {
        v103 = 232;
LABEL_193:
        sub_1801A1648(v102[2], v103, &stru_180C1BC18);
        goto LABEL_194;
      }
      goto LABEL_194;
    }
    _mm_lfence();
    if ( (unsigned int)sub_180176270(v2 + 88328, 19) )
    {
      v104 = hDevice;
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        goto LABEL_194;
      v105 = 233;
      v106 = *(_QWORD *)(v1 + 280);
      goto LABEL_184;
    }
  }
  *((_WORD *)v2 + 44521) = 0;
  v107 = *(_WORD **)(v1 + 472);
  if ( v107 && *v107 )
  {
    v108 = -1;
    do
      ++v108;
    while ( v107[v108] );
    if ( v108 >= 0x13 )
    {
      v102 = hDevice;
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      {
        v103 = 234;
        goto LABEL_193;
      }
LABEL_194:
      v109 = (volatile signed __int32 *)*((_QWORD *)&v169 + 1);
      if ( *((_QWORD *)&v169 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v109)(v109);
          if ( _InterlockedExchangeAdd(v109 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v109 + 8LL))(v109);
        }
      }
      return 32780;
    }
    _mm_lfence();
    if ( (unsigned int)sub_180176270(v2 + 89042, 19) )
    {
      v104 = hDevice;
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        goto LABEL_194;
      v105 = 235;
      v106 = *(_QWORD *)(v1 + 472);
LABEL_184:
      sub_1801C8638(v104[2], v105, &stru_180C1BC18, v106);
      goto LABEL_194;
    }
  }
  v2[88384] = *(_DWORD *)(v1 + 288) != 0;
  v2[2883] = *(_DWORD *)(v1 + 204) != 0;
  *((_DWORD *)v2 + 22097) = 0;
  *((_WORD *)v2 + 44196) = 0;
  v110 = *(_QWORD *)(v1 + 432);
  v111 = 0;
  if ( v110 )
  {
    do
    {
      v112 = *(_DWORD *)(v110 + 16);
      if ( v112 == 1 || v112 == 3 || v112 == 6 )
      {
        v2[88393] = 1;
      }
      else if ( ((v112 - 2) & 0xFFFFFFFD) == 0 )
      {
        v2[88392] = 1;
      }
      *((_DWORD *)v2 + 22097) = ++v111;
      v110 = *(_QWORD *)(v110 + 8);
    }
    while ( v110 );
  }
  else if ( *(_QWORD *)(v1 + 368) )
  {
    *((_DWORD *)v2 + 22097) = *(_DWORD *)(v1 + 360);
    if ( *(_DWORD *)(v1 + 360) )
    {
      v113 = 74;
      do
      {
        v110 = 32LL * v111;
        v114 = *(_DWORD *)(v110 + *(_QWORD *)(v1 + 368) + 4);
        if ( v114 <= 6 && _bittest(&v113, v114) )
        {
          v2[88393] = 1;
        }
        else if ( ((v114 - 2) & 0xFFFFFFFD) == 0 )
        {
          v2[88392] = 1;
        }
        ++v111;
      }
      while ( v111 < *(_DWORD *)(v1 + 360) );
    }
  }
  else
  {
    *((_DWORD *)v2 + 22097) = *(_DWORD *)(v1 + 232);
    if ( *(_DWORD *)(v1 + 232) )
    {
      v115 = 74;
      do
      {
        v110 = 5LL * v111;
        v116 = *(_DWORD *)(*(_QWORD *)(v1 + 240) + 20LL * v111);
        if ( v116 <= 6 && _bittest(&v115, v116) )
        {
          v2[88393] = 1;
        }
        else if ( ((v116 - 2) & 0xFFFFFFFD) == 0 )
        {
          v2[88392] = 1;
        }
        ++v111;
      }
      while ( v111 < *(_DWORD *)(v1 + 232) );
    }
  }
  *((_DWORD *)v2 + 22099) = *(_DWORD *)(v1 + 248);
  *((_DWORD *)v2 + 22100) = *(_DWORD *)(v1 + 292);
  v117 = *(_QWORD *)(v1 + 176);
  if ( qword_18105B7A8 )
    sub_1801A08A8(v110);
  if ( v117 )
  {
    v118 = sub_18028E008(v117);
    if ( v118 )
    {
      v119 = (volatile signed __int32 *)*((_QWORD *)&v169 + 1);
      if ( *((_QWORD *)&v169 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v119)(v119);
          if ( _InterlockedExchangeAdd(v119 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v119 + 8LL))(v119);
        }
      }
      return v118;
    }
    v85 = 0;
    goto LABEL_261;
  }
  if ( !v2[2875] && !v2[3026] && !byte_18105B228 )
  {
    switch ( *((_DWORD *)v2 + 712) )
    {
      case 1:
        v120 = L"SOFTWARE\\Policies\\Microsoft\\Windows Defender\\MpEngine";
        goto LABEL_249;
      case 4:
      case 6:
        goto LABEL_246;
      case 7:
        v120 = L"SOFTWARE\\Microsoft\\MpScan";
        goto LABEL_249;
      case 8:
LABEL_246:
        v120 = L"SOFTWARE\\Policies\\Microsoft\\Microsoft Antimalware\\MpEngine";
LABEL_249:
        hKey = 0;
        if ( (int)sub_18007FD94(&hKey, -2147483646, v120, 1) >= 0 )
        {
          for ( i = 0; i < 54; i += 3LL )
          {
            nSize = 0;
            if ( (int)sub_18007F87C(hKey, (&off_181010BD0)[i], &nSize) >= 0 )
            {
              if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
                sub_1801A569C(
                  *((_QWORD *)hDevice + 2),
                  36,
                  (unsigned int)&stru_180C7D2B0,
                  (unsigned int)(&off_181010BD0)[i],
                  nSize);
              HIDWORD(qword_181010BD8[i]) = nSize;
            }
          }
          v1 = v170;
        }
        if ( hKey )
          RegCloseKey(hKey);
        break;
    }
  }
LABEL_261:
  if ( v2[2883] )
    goto LABEL_265;
  if ( !byte_18105B228 && (int)sub_18028CC38(L"MpSevilleEnable", v2 + 2883) < 0 )
    goto LABEL_407;
  if ( v2[2883] )
LABEL_265:
    v2[2884] = sub_1801AF950();
  v122 = *(_QWORD *)(v1 + 208);
  v189 = 0;
  if ( v122 )
  {
    sub_180078F38((__int64)&v189, v122);
    v123 = v189;
    *((_QWORD *)v2 + 11039) = v189;
    if ( !v123 )
    {
      v92 = hDevice;
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        goto LABEL_466;
      v93 = 236;
      goto LABEL_465;
    }
  }
  else if ( (unsigned __int8)sub_1801AE0E8(&v189) )
  {
    *((_QWORD *)v2 + 11039) = v189;
  }
  else
  {
    if ( v2[2883] )
    {
      if ( (unsigned __int8)sub_1801A4A54(0, v124, "Engine.Maps.OrgidMissing") )
      {
        v125 = lpCriticalSection;
        if ( lpCriticalSection )
        {
          EnterCriticalSection(lpCriticalSection);
          if ( (unsigned int)dword_18100A408 > 5
            && (qword_18100A418[0] & 0x400000000000LL) != 0
            && (qword_18100A418[1] & 0x400000000000LL) == qword_18100A418[1] )
          {
            v177 = "OrgIDMissing";
            v178 = "MAPS";
            nSize = *(_DWORD *)(qword_181040D08 + 72);
            v171 = *(_DWORD *)(qword_181040D08 + 68);
            v172 = *(_DWORD *)(qword_181040D08 + 64);
            v173 = *(unsigned __int8 *)(qword_181040D08 + 60);
            v174 = *(unsigned __int8 *)(qword_181040D08 + 59);
            v175 = *(unsigned __int8 *)(qword_181040D08 + 58);
            LODWORD(v176) = *(unsigned __int8 *)(qword_181040D08 + 57);
            LODWORD(v170) = *(unsigned __int8 *)(qword_181040D08 + 56);
            v179 = *(_QWORD *)(qword_181040D08 + 48);
            v180 = *(_QWORD *)(qword_181040D08 + 40);
            v181 = *(_QWORD *)(qword_181040D08 + 32);
            v182 = *(_QWORD *)(qword_181040D08 + 24);
            v183 = *(_QWORD *)(qword_181040D08 + 16);
            v184 = *(_QWORD *)(qword_181040D08 + 8);
            v185 = 0x1000000;
            LODWORD(hKey) = 1;
            v186 = 1;
            sub_1800030B0(
              (unsigned int)&dword_18100A408,
              (unsigned int)&unk_180F51EF8,
              (unsigned int)&dword_18100A408,
              (unsigned int)&v186,
              (__int64)&hKey,
              (__int64)&v185,
              (__int64)&v184,
              (__int64)&v183,
              (__int64)&v182,
              (__int64)&v181,
              (__int64)&v180,
              (__int64)&v179,
              (__int64)&v170,
              (__int64)&v176,
              (__int64)&v175,
              (__int64)&v174,
              (__int64)&v173,
              (__int64)&v172,
              (__int64)&v171,
              (__int64)&nSize,
              (__int64)&v178,
              (__int64)&v177);
          }
          LeaveCriticalSection(v125);
        }
      }
    }
    if ( v189 )
      sub_1801FF6A0(v189);
  }
  v126 = (unsigned __int16 *)*((_QWORD *)v2 + 11039);
  if ( v126 && (int)sub_18007D554((UUID *)v2 + 5511, v126) < 0 )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 2) != 0 )
      sub_1801A1648(*((_QWORD *)hDevice + 2), 237, &stru_180C1BC18);
    *((_OWORD *)v2 + 5511) = 0;
  }
  v127 = *(_QWORD *)(v1 + 424);
  if ( v127 )
  {
    v189 = 0;
    sub_180078F38((__int64)&v189, v127);
    v128 = (unsigned __int16 *)v189;
    *((_QWORD *)v2 + 11128) = v189;
    if ( !v128 )
    {
      v92 = hDevice;
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        goto LABEL_466;
      v93 = 238;
      goto LABEL_465;
    }
    if ( (int)sub_18007D554((UUID *)v2 + 5512, v128) < 0 )
    {
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 2) != 0 )
        sub_1801A1648(*((_QWORD *)hDevice + 2), 239, &stru_180C1BC18);
      *((_OWORD *)v2 + 5512) = 0;
    }
  }
  v129 = (HKEY)L"SOFTWARE\\Microsoft\\InetStp";
  v187[0] = L"SOFTWARE\\Microsoft\\InetStp";
  v187[1] = L"SOFTWARE\\Wow6432Node\\Microsoft\\InetStp";
  for ( j = (HKEY *)v187; ; v129 = *j )
  {
    v189 = 0;
    if ( (int)sub_18007FD94(&v189, -2147483646, v129, 0x80000000LL) >= 0 )
      break;
    if ( v189 )
      RegCloseKey(v189);
    if ( ++j == &hKey )
    {
      v131 = 0;
      goto LABEL_309;
    }
  }
  if ( v189 )
    RegCloseKey(v189);
  v131 = 1;
LABEL_309:
  v2[88409] = v131;
  if ( !v2[2883] )
    goto LABEL_335;
  v132 = *(_QWORD *)(v1 + 328);
  if ( v132 )
  {
    hKey = 0;
    if ( (int)sub_180078F38((__int64)&hKey, v132) < 0 )
    {
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
        sub_1801A1648(*((_QWORD *)hDevice + 2), 240, &stru_180C1BC18);
      v133 = hKey;
      goto LABEL_324;
    }
    v134 = hKey;
  }
  else
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 2) != 0 )
      sub_1801A1648(*((_QWORD *)hDevice + 2), 241, &stru_180C1BC18);
    v189 = 0;
    if ( !(unsigned __int8)sub_1801AE3E8(&v189) )
    {
      v133 = v189;
      goto LABEL_324;
    }
    v134 = v189;
  }
  v133 = 0;
  *((_QWORD *)v2 + 11046) = v134;
LABEL_324:
  if ( v133 )
    sub_1801FF6A0(v133);
  v135 = *(_QWORD *)(v1 + 336);
  if ( v135 )
  {
    hKey = 0;
    if ( (int)sub_180078F38((__int64)&hKey, v135) >= 0 )
    {
      v136 = 0;
      *((_QWORD *)v2 + 11047) = hKey;
    }
    else
    {
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
        sub_1801A1648(*((_QWORD *)hDevice + 2), 242, &stru_180C1BC18);
      v136 = hKey;
    }
    if ( v136 )
      sub_1801FF6A0(v136);
  }
LABEL_335:
  *((_DWORD *)v2 + 22101) = 0;
  v2[88984] = *(_DWORD *)(v1 + 380) != 0;
  *((_DWORD *)v2 + 22247) = *(_DWORD *)(v1 + 464);
  if ( !*(_QWORD *)(v1 + 440) )
  {
    v137 = 0;
LABEL_371:
    *((_QWORD *)v2 + 11129) = v137;
    v146 = *(_DWORD *)(v1 + 356);
    v2[3012] = v146 != 0;
    if ( !v146 )
      v2[3012] = sub_1802B7B94();
    *((_DWORD *)v2 + 744) = sub_1802B797C(L"MpEngineRing");
    *((_DWORD *)v2 + 745) = sub_1802B797C(L"MpCampRing");
    *((_DWORD *)v2 + 746) = sub_1802B797C(L"MpSignatureRing");
    v147 = *(_DWORD *)(v1 + 348);
    if ( !v147 || v147 == -1 )
      v147 = 0;
    *((_DWORD *)v2 + 749) = v147;
    if ( v147 )
      sub_1802B8B94();
    v148 = *(_DWORD *)(v1 + 344);
    if ( !v148 || v148 == -1 )
      v148 = 0;
    *((_DWORD *)v2 + 750) = v148;
    if ( v148 )
      sub_1802B8EB4();
    v149 = *(_DWORD *)(v1 + 352);
    if ( !v149 || v149 == -1 )
      v149 = 0;
    *((_DWORD *)v2 + 751) = v149;
    if ( v149 )
      sub_1802B8FCC();
    *((_DWORD *)v2 + 752) = sub_1801ADF28();
    v191 = 0;
    v192 = 0;
    if ( (unsigned __int8)sub_1802B7C38(&v191, &v192) )
    {
      *((_DWORD *)v2 + 747) = v191;
      *((_DWORD *)v2 + 748) = v192;
    }
    else
    {
      *(_QWORD *)(v2 + 2988) = 0;
    }
    sub_1801B689C(v1, v2);
    if ( !v2[2887] )
    {
      if ( (int)sub_18028CC38(L"MpEnablePUS", v2 + 2887) < 0 )
        goto LABEL_407;
      if ( v2[2887] )
        *((_DWORD *)v2 + 22074) = 1;
    }
    if ( (int)sub_18028CC38(L"MpEnablePUSRemoval", v2 + 2890) < 0 )
      goto LABEL_407;
    v168[0] = 0;
    if ( (int)sub_18028CC38(L"MpContinueOnDetection", v168) >= 0 && v168[0] )
      *((_DWORD *)qword_18105B1D0 + 692) |= 0x10000u;
    v168[0] = 0;
    if ( (int)sub_18028CC38(L"MpForceDelayReporting", v168) >= 0 && v168[0] )
      *((_DWORD *)qword_18105B1D0 + 692) |= 0x80000u;
    if ( (int)sub_18028CCA0(L"MpEnableTest", v2 + 2928) < 0
      || (int)sub_18028CC38(L"MpForceThrottledSigs", v2 + 2903) < 0
      || (int)sub_18028CC38(L"MpEnableMBA", v2 + 2886) < 0 )
    {
      goto LABEL_407;
    }
    if ( byte_18105B228 )
    {
      *((_DWORD *)v2 + 742) = *(_DWORD *)(v1 + 384);
    }
    else if ( (int)sub_18028CCA0(L"MpCloudBlockLevel", v2 + 2968) < 0 )
    {
LABEL_407:
      v150 = (volatile signed __int32 *)*((_QWORD *)&v169 + 1);
      if ( *((_QWORD *)&v169 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v150)(v150);
          if ( _InterlockedExchangeAdd(v150 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v150 + 8LL))(v150);
        }
      }
      return 32769;
    }
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, (DWORD *)v2 + 22081) )
    {
      *((_DWORD *)v2 + 22081) = -1;
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        sub_1801A166C(*((_QWORD *)hDevice + 2), 246, &stru_180C1BC18, LastError);
      }
    }
    if ( !byte_18105B228 )
    {
      v153 = (WCHAR **)(v2 + 88952);
      for ( k = 0; k < 6; k += 2LL )
      {
        nSize = 0;
        if ( GetComputerNameExW(*(COMPUTER_NAME_FORMAT *)&asc_180C19DA8[k], 0, &nSize) || GetLastError() != 234 )
        {
          if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 2) != 0 )
            sub_1801A1648(*((_QWORD *)hDevice + 2), 247, &stru_180C1BC18);
        }
        else if ( nSize )
        {
          v155 = 2LL * (nSize + 1);
          if ( !is_mul_ok(nSize + 1, 2u) )
            v155 = -1;
          v156 = (WCHAR *)sub_18001F740(v155, qword_180BE0980);
          *v153 = v156;
          if ( !v156 )
            goto LABEL_466;
          if ( !GetComputerNameExW(*(COMPUTER_NAME_FORMAT *)&asc_180C19DA8[k], v156, &nSize)
            && hDevice != &hDevice
            && (*((_BYTE *)hDevice + 28) & 2) != 0 )
          {
            v157 = GetLastError();
            sub_1801A166C(*((_QWORD *)hDevice + 2), 248, &stru_180C1BC18, v157);
          }
        }
        ++v153;
      }
    }
    *((_DWORD *)v2 + 22236) = sub_1801ADCD0();
    v2[88948] = *(_DWORD *)(v1 + 324) != 0;
    v158 = *(_QWORD *)(v1 + 392);
    if ( v158 )
    {
      hKey = 0;
      if ( (int)sub_180078F38((__int64)&hKey, v158) >= 0 )
      {
        v159 = 0;
        *((_QWORD *)v2 + 11124) = hKey;
      }
      else
      {
        if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
          sub_1801A1648(*((_QWORD *)hDevice + 2), 249, &stru_180C1BC18);
        v159 = hKey;
      }
      if ( v159 )
        sub_1801FF6A0(v159);
    }
    v160 = *(_QWORD *)(v1 + 400);
    if ( v160 )
    {
      hKey = 0;
      if ( (int)sub_180078F38((__int64)&hKey, v160) >= 0 )
      {
        v161 = 0;
        *((_QWORD *)v2 + 11125) = hKey;
      }
      else
      {
        if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
          sub_1801A1648(*((_QWORD *)hDevice + 2), 250, &stru_180C1BC18);
        v161 = hKey;
      }
      if ( v161 )
        sub_1801FF6A0(v161);
    }
    v162 = *(_QWORD *)(v1 + 408);
    if ( v162 )
    {
      hKey = 0;
      if ( (int)sub_180078F38((__int64)&hKey, v162) >= 0 )
      {
        v163 = 0;
        *((_QWORD *)v2 + 11126) = hKey;
      }
      else
      {
        if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
          sub_1801A1648(*((_QWORD *)hDevice + 2), 251, &stru_180C1BC18);
        v163 = hKey;
      }
      if ( v163 )
        sub_1801FF6A0(v163);
    }
    *((_DWORD *)v2 + 22270) = *(_DWORD *)(v1 + 480);
    v2[89016] = 0;
    v2[89084] = *(_DWORD *)(v1 + 484) != 0;
    *((_DWORD *)v2 + 22272) = *(_DWORD *)(v1 + 488);
    *((_DWORD *)v2 + 22273) = *(_DWORD *)(v1 + 492);
    *((_DWORD *)v2 + 22275) = *(_DWORD *)(v1 + 500);
    *((_DWORD *)v2 + 22274) = *(_DWORD *)(v1 + 496);
    if ( v1 == -504
      || (v189 = 0, sub_180078F38((__int64)&v189, v1 + 504), v164 = v189, *((_QWORD *)v2 + 11138) = v189, v164) )
    {
      if ( !(unsigned __int8)sub_18007E554() || (v166 = 1, !*(_DWORD *)(v1 + 1528)) )
        v166 = 0;
      v2[89112] = v166;
      v189 = 0;
      v167 = (int)sub_18007FD94(&v189, -2147483646, L"SOFTWARE\\Microsoft\\SenseAP", 1) >= 0;
      if ( v189 )
        RegCloseKey(v189);
      v2[2885] = v167;
      v2[89113] = sub_1801AFBD0();
      if ( *((_QWORD *)&v169 + 1) )
        sub_1801B9194();
      return 0;
    }
    v92 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_466;
    v93 = 252;
LABEL_465:
    sub_1801A1648(v92[2], v93, &stru_180C1BC18);
    goto LABEL_466;
  }
  v137 = (HKEY)sub_18001F740(16, qword_180BE0980);
  hKey = v137;
  if ( !v137 )
  {
    v92 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_466;
    v93 = 243;
    goto LABEL_465;
  }
  v138 = **(unsigned int **)(v1 + 440);
  *(_DWORD *)v137 = v138;
  if ( !(_DWORD)v138 )
    goto LABEL_370;
  v139 = 32 * v138;
  if ( !is_mul_ok(v138, 0x20u) )
    v139 = -1;
  v85 = (char *)sub_18001F740(v139, qword_180BE0980);
  if ( !v85 )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      sub_1801A1648(*((_QWORD *)hDevice + 2), 244, &stru_180C1BC18);
    v140 = v137;
    goto LABEL_349;
  }
  v141 = 0;
  nSize = 0;
  if ( !*(_DWORD *)v137 )
  {
LABEL_370:
    *((_QWORD *)v137 + 1) = v85;
    goto LABEL_371;
  }
  si128 = _mm_load_si128((const __m128i *)&xmmword_180EDC660);
  while ( 1 )
  {
    v143 = 32LL * v141;
    *(_DWORD *)&v85[v143] = *(_DWORD *)(v143 + *(_QWORD *)(*(_QWORD *)(v1 + 440) + 8LL));
    *(_DWORD *)&v85[v143 + 4] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 440) + 8LL) + v143 + 4);
    *(_DWORD *)&v85[v143 + 8] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 440) + 8LL) + v143 + 8);
    *(_DWORD *)&v85[v143 + 12] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 440) + 8LL) + v143 + 12);
    *(_DWORD *)&v85[v143 + 16] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 440) + 8LL) + v143 + 16);
    v144 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 440) + 8LL) + v143 + 24);
    if ( !v144 )
    {
      *(_QWORD *)&v85[v143 + 24] = 0;
      goto LABEL_356;
    }
    v189 = 0;
    if ( (int)sub_180078F38((__int64)&v189, v144) < 0 )
      break;
    *(_QWORD *)&v85[v143 + 24] = v189;
LABEL_356:
    if ( *(_DWORD *)&v85[v143 + 4] == 4 )
    {
      v193 = 0;
      v194 = si128;
      LOWORD(v193) = 0;
      if ( (int)sub_180625BBC(*(unsigned int *)&v85[v143], &v193) >= 0 )
      {
        v145 = &v193;
        if ( v194.m128i_i64[1] > 7uLL )
          v145 = (__int128 *)v193;
        sub_180624490(0, v145);
      }
      sub_1801A5180(&v193);
    }
    v141 = nSize + 1;
    nSize = v141;
    v137 = hKey;
    if ( v141 >= *(_DWORD *)hKey )
      goto LABEL_370;
  }
  if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
    sub_1801A1648(*((_QWORD *)hDevice + 2), 245, &stru_180C1BC18);
  if ( v189 )
    sub_1801FF6A0(v189);
  sub_18013F020(v85);
  v140 = hKey;
LABEL_349:
  sub_18013F020(v140);
LABEL_466:
  v165 = (volatile signed __int32 *)*((_QWORD *)&v169 + 1);
  if ( *((_QWORD *)&v169 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v169 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v165)(v165);
      if ( _InterlockedExchangeAdd(v165 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v165 + 8LL))(v165);
    }
  }
  return 32775;
}

```

## disassembly

```asm
0x1801bc1bc  mov     rax, rsp
0x1801bc1bf  mov     [rax+10h], rbx
0x1801bc1c3  mov     [rax+18h], rsi
0x1801bc1c7  mov     [rax+20h], rdi
0x1801bc1cb  push    rbp
0x1801bc1cc  push    r12
0x1801bc1ce  push    r13
0x1801bc1d0  push    r14
0x1801bc1d2  push    r15
0x1801bc1d4  lea     rbp, [rax-1F8h]
0x1801bc1db  sub     rsp, 300h
0x1801bc1e2  movaps  xmmword ptr [rax-38h], xmm6
0x1801bc1e6  mov     rax, cs:__security_cookie
0x1801bc1ed  xor     rax, rsp
0x1801bc1f0  mov     [rbp+1F0h+var_40], rax
0x1801bc1f7  mov     r14, rcx
0x1801bc1fa  mov     [rbp+1F0h+var_258], rcx
0x1801bc1fe  mov     rsi, cs:qword_18105B1D0
0x1801bc205  mov     [rbp+1F0h+var_238], rsi
0x1801bc209  xor     ebx, ebx
0x1801bc20b  test    rsi, rsi
0x1801bc20e  jz      loc_1801BC2B2
0x1801bc214  mov     rdx, rcx
0x1801bc217  mov     rcx, rsi
0x1801bc21a  call    sub_1801C70E4
0x1801bc21f  test    eax, eax
0x1801bc221  jns     short loc_1801BC243
0x1801bc223  lea     rdx, hDevice
0x1801bc22a  mov     rcx, cs:hDevice
0x1801bc231  cmp     rcx, rdx
0x1801bc234  jz      short loc_1801BC2B2
0x1801bc236  test    byte ptr [rcx+1Ch], 1
0x1801bc23a  jz      short loc_1801BC2B2
0x1801bc23c  mov     edx, 0DEh
0x1801bc241  jmp     short loc_1801BC29F
0x1801bc243  mov     rdx, r14
0x1801bc246  mov     rcx, rsi
0x1801bc249  call    sub_1801C6F70
0x1801bc24e  test    eax, eax
0x1801bc250  jns     short loc_1801BC272
0x1801bc252  lea     rdx, hDevice
0x1801bc259  mov     rcx, cs:hDevice
0x1801bc260  cmp     rcx, rdx
0x1801bc263  jz      short loc_1801BC2B2
0x1801bc265  test    byte ptr [rcx+1Ch], 1
0x1801bc269  jz      short loc_1801BC2B2
0x1801bc26b  mov     edx, 0DFh
0x1801bc270  jmp     short loc_1801BC29F
0x1801bc272  mov     rdx, r14
0x1801bc275  mov     rcx, rsi
0x1801bc278  call    sub_1801C6924
0x1801bc27d  test    eax, eax
0x1801bc27f  jns     short loc_1801BC2EC
0x1801bc281  lea     rdx, hDevice
0x1801bc288  mov     rcx, cs:hDevice
0x1801bc28f  cmp     rcx, rdx
0x1801bc292  jz      short loc_1801BC2B2
0x1801bc294  test    byte ptr [rcx+1Ch], 1
0x1801bc298  jz      short loc_1801BC2B2
0x1801bc29a  mov     edx, 0E0h
0x1801bc29f  mov     r9d, eax
0x1801bc2a2  lea     r8, stru_180C1BC18
0x1801bc2a9  mov     rcx, [rcx+10h]
0x1801bc2ad  call    sub_1801A166C
0x1801bc2b2  mov     eax, 800Ch
0x1801bc2b7  mov     rcx, [rbp+1F0h+var_40]
0x1801bc2be  xor     rcx, rsp; StackCookie
0x1801bc2c1  call    __security_check_cookie
0x1801bc2c6  lea     r11, [rsp+320h+var_20]
0x1801bc2ce  mov     rbx, [r11+38h]
0x1801bc2d2  mov     rsi, [r11+40h]
0x1801bc2d6  mov     rdi, [r11+48h]
0x1801bc2da  movaps  xmm6, xmmword ptr [r11-10h]
0x1801bc2df  mov     rsp, r11
0x1801bc2e2  pop     r15
0x1801bc2e4  pop     r14
0x1801bc2e6  pop     r13
0x1801bc2e8  pop     r12
0x1801bc2ea  pop     rbp
0x1801bc2eb  retn
0x1801bc2ec  mov     rdi, [r14+88h]
0x1801bc2f3  lea     r12, hDevice
0x1801bc2fa  lea     r13, stru_180C1BC18
0x1801bc301  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801bc305  test    rdi, rdi
0x1801bc308  jz      loc_1801BC38E
0x1801bc30e  inc     rax
0x1801bc311  cmp     [rdi+rax*2], bx
0x1801bc315  jnz     short loc_1801BC30E
0x1801bc317  lea     r15, ds:2[rax*2]
0x1801bc31f  mov     rcx, r15
0x1801bc322  call    sub_1801655F0
0x1801bc327  mov     rbx, rax
0x1801bc32a  test    rax, rax
0x1801bc32d  jz      short loc_1801BC33D
0x1801bc32f  mov     r8, r15
0x1801bc332  mov     rdx, rdi
0x1801bc335  mov     rcx, rax
0x1801bc338  call    sub_180B74870
0x1801bc33d  mov     [rsi+158A0h], rbx
0x1801bc344  test    rbx, rbx
0x1801bc347  jz      loc_1801BE181
0x1801bc34d  lea     rdi, [rsi+15860h]
0x1801bc354  mov     rdx, rbx; StringUuid
0x1801bc357  mov     rcx, rdi; Uuid
0x1801bc35a  call    sub_18007D554
0x1801bc35f  xor     ebx, ebx
0x1801bc361  test    eax, eax
0x1801bc363  jns     short loc_1801BC38E
0x1801bc365  mov     rcx, cs:hDevice
0x1801bc36c  cmp     rcx, r12
0x1801bc36f  jz      short loc_1801BC388
0x1801bc371  test    byte ptr [rcx+1Ch], 2
0x1801bc375  jz      short loc_1801BC388
0x1801bc377  mov     edx, 0E1h
0x1801bc37c  mov     r8, r13
0x1801bc37f  mov     rcx, [rcx+10h]
0x1801bc383  call    sub_1801A1648
0x1801bc388  xorps   xmm0, xmm0
0x1801bc38b  movups  xmmword ptr [rdi], xmm0
0x1801bc38e  xor     edx, edx
0x1801bc390  mov     r8d, 11Ch
0x1801bc396  lea     rcx, [rbp+1F0h+VersionInformation]
0x1801bc39d  call    sub_180B743D0
0x1801bc3a2  lea     rcx, [rbp+1F0h+VersionInformation]; lpVersionInformation
0x1801bc3a9  call    sub_180079FF8
0x1801bc3ae  shr     eax, 1Fh
0x1801bc3b1  mov     r15d, 1
0x1801bc3b7  xor     al, r15b
0x1801bc3ba  jz      loc_1801BC8EB
0x1801bc3c0  movzx   ecx, word ptr [rbp+1F0h+VersionInformation.dwMajorVersion]
0x1801bc3c7  shl     ecx, 10h
0x1801bc3ca  movzx   eax, word ptr [rbp+1F0h+VersionInformation.dwMinorVersion]
0x1801bc3d1  or      ecx, eax
0x1801bc3d3  mov     [rsi+0B60h], ecx
0x1801bc3d9  mov     [rsi+0B84h], ecx
0x1801bc3df  movzx   eax, [rbp+1F0h+var_4C]
0x1801bc3e6  mov     [rsi+0B88h], eax
0x1801bc3ec  mov     eax, [rbp+1F0h+VersionInformation.dwBuildNumber]
0x1801bc3f2  mov     [rsi+0B8Ch], eax
0x1801bc3f8  mov     [rbp+1F0h+hKey], rbx
0x1801bc3fc  mov     r9d, r15d
0x1801bc3ff  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x1801bc406  mov     rdx, 0FFFFFFFF80000002h
0x1801bc40d  lea     rcx, [rbp+1F0h+hKey]
0x1801bc411  call    sub_18007FD94
0x1801bc416  mov     rcx, [rbp+1F0h+hKey]
0x1801bc41a  test    eax, eax
0x1801bc41c  js      short loc_1801BC43C
0x1801bc41e  mov     [rbp+1F0h+nSize], ebx
0x1801bc421  lea     r8, [rbp+1F0h+nSize]
0x1801bc425  lea     rdx, aUbr; "UBR"
0x1801bc42c  call    sub_18007F87C
0x1801bc431  mov     rcx, [rbp+1F0h+hKey]; hKey
0x1801bc435  test    eax, eax
0x1801bc437  js      short loc_1801BC43C
0x1801bc439  mov     ebx, [rbp+1F0h+nSize]
0x1801bc43c  test    rcx, rcx
0x1801bc43f  jz      short loc_1801BC447
0x1801bc441  call    cs:__imp_RegCloseKey
0x1801bc447  mov     [rsi+0B90h], ebx
0x1801bc44d  movzx   ecx, [rbp+1F0h+var_48]
0x1801bc454  mov     al, cl
0x1801bc456  shr     al, 6
0x1801bc459  and     al, r15b
0x1801bc45c  mov     [rsi+0B3Ch], al
0x1801bc462  shr     cl, 4
0x1801bc465  and     cl, r15b
0x1801bc468  mov     [rsi+0B3Fh], cl
0x1801bc46e  cmp     [rbp+1F0h+var_46], 2
0x1801bc475  setz    al
0x1801bc478  mov     [rsi+0B56h], al
0x1801bc47e  lea     rbx, [rsi+0B94h]
0x1801bc485  movzx   r9d, [rbp+1F0h+var_4A]; dwSpMinorVersion
0x1801bc48d  movzx   r8d, [rbp+1F0h+var_4C]; dwSpMajorVersion
0x1801bc495  mov     [rsp+320h+pdwReturnedProductType], rbx; pdwReturnedProductType
0x1801bc49a  mov     edx, [rbp+1F0h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x1801bc4a0  mov     ecx, [rbp+1F0h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x1801bc4a6  call    cs:GetProductInfo
0x1801bc4ac  xor     ecx, ecx
0x1801bc4ae  test    eax, eax
0x1801bc4b0  jz      short loc_1801BC4CD
0x1801bc4b2  cmp     dword ptr [rbx], 0B2h
0x1801bc4b8  jz      short loc_1801BC4C4
0x1801bc4ba  cmp     dword ptr [rbx], 0B3h
0x1801bc4c0  mov     al, cl
0x1801bc4c2  jnz     short loc_1801BC4C7
0x1801bc4c4  mov     al, r15b
0x1801bc4c7  mov     [rsi+0B40h], al
0x1801bc4cd  mov     eax, [r14+178h]
0x1801bc4d4  cmp     eax, r15d
0x1801bc4d7  jnz     loc_1801BC8B5
0x1801bc4dd  mov     [rsi+0B3Eh], r15b
0x1801bc4e4  xor     ebx, ebx
0x1801bc4e6  xorps   xmm0, xmm0
0x1801bc4e9  movups  xmmword ptr [rbp+1F0h+SystemInfo], xmm0
0x1801bc4ed  movups  xmmword ptr [rbp+1F0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1801bc4f1  movups  xmmword ptr [rbp+1F0h+SystemInfo.dwNumberOfProcessors], xmm0
0x1801bc4f8  lea     rcx, [rbp+1F0h+SystemInfo]; lpSystemInfo
0x1801bc4fc  call    cs:__imp_GetSystemInfo
0x1801bc502  movzx   eax, word ptr [rbp+1F0h+SystemInfo]
0x1801bc506  mov     [rsi+0B64h], eax
0x1801bc50c  mov     eax, [rbp+1F0h+SystemInfo.dwPageSize]
0x1801bc50f  mov     [rsi+0B68h], eax
0x1801bc515  mov     eax, [rbp+1F0h+SystemInfo.dwAllocationGranularity]
0x1801bc51b  mov     [rsi+0B6Ch], eax
0x1801bc521  call    cs:GetSystemDefaultLCID
0x1801bc527  mov     [rsi+0B5Ch], eax
0x1801bc52d  mov     dword ptr [rsi+0B9Ch], 8
0x1801bc537  mov     rdi, [r14+90h]
0x1801bc53e  test    rdi, rdi
0x1801bc541  jz      short loc_1801BC582
0x1801bc543  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801bc547  inc     rax
0x1801bc54a  cmp     [rdi+rax*2], bx
0x1801bc54e  jnz     short loc_1801BC547
0x1801bc550  lea     rax, ds:2[rax*2]
0x1801bc558  mov     [rbp+1F0h+var_1C8], rax
0x1801bc55c  mov     rcx, rax
0x1801bc55f  call    sub_1801655F0
0x1801bc564  mov     rbx, rax
0x1801bc567  test    rax, rax
0x1801bc56a  jz      short loc_1801BC57B
0x1801bc56c  mov     r8, [rbp+1F0h+var_1C8]
0x1801bc570  mov     rdx, rdi
0x1801bc573  mov     rcx, rax
0x1801bc576  call    sub_180B74870
0x1801bc57b  mov     [rsi+158A8h], rbx
0x1801bc582  mov     rbx, [r14+98h]
0x1801bc589  xor     ecx, ecx
0x1801bc58b  test    rbx, rbx
0x1801bc58e  jz      short loc_1801BC5D3
0x1801bc590  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801bc594  inc     rax
0x1801bc597  cmp     [rbx+rax*2], cx
0x1801bc59b  jnz     short loc_1801BC594
0x1801bc59d  lea     rax, ds:2[rax*2]
0x1801bc5a5  mov     [rbp+1F0h+var_1C8], rax
0x1801bc5a9  mov     rcx, rax
0x1801bc5ac  call    sub_1801655F0
0x1801bc5b1  mov     rdi, rax
0x1801bc5b4  xor     ecx, ecx
0x1801bc5b6  test    rax, rax
0x1801bc5b9  jz      short loc_1801BC5CC
0x1801bc5bb  mov     r8, [rbp+1F0h+var_1C8]
0x1801bc5bf  mov     rdx, rbx
0x1801bc5c2  mov     rcx, rax
0x1801bc5c5  call    sub_180B74870
0x1801bc5ca  xor     ecx, ecx
0x1801bc5cc  mov     [rsi+158B0h], rdi
0x1801bc5d3  mov     rbx, [r14+0A0h]
0x1801bc5da  test    rbx, rbx
0x1801bc5dd  jz      short loc_1801BC61E
0x1801bc5df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801bc5e3  inc     rax
0x1801bc5e6  cmp     [rbx+rax*2], cx
0x1801bc5ea  jnz     short loc_1801BC5E3
0x1801bc5ec  lea     rax, ds:2[rax*2]
0x1801bc5f4  mov     [rbp+1F0h+var_1C8], rax
0x1801bc5f8  mov     rcx, rax
0x1801bc5fb  call    sub_1801655F0
0x1801bc600  mov     rdi, rax
0x1801bc603  test    rax, rax
0x1801bc606  jz      short loc_1801BC617
0x1801bc608  mov     r8, [rbp+1F0h+var_1C8]
0x1801bc60c  mov     rdx, rbx
0x1801bc60f  mov     rcx, rax
0x1801bc612  call    sub_180B74870
0x1801bc617  mov     [rsi+158B8h], rdi
0x1801bc61e  mov     rbx, [rsi+8]
0x1801bc622  lea     rcx, [rbx+18h]; lpCriticalSection
0x1801bc626  call    EnterCriticalSection
0x1801bc62b  mov     rdx, [rbx+8]
0x1801bc62f  mov     eax, [r14+58h]
0x1801bc633  mov     [rdx+10h], eax
0x1801bc636  mov     ecx, [r14+30h]
0x1801bc63a  shr     ecx, 0Bh
0x1801bc63d  and     ecx, r15d
0x1801bc640  mov     eax, [rdx+14h]
0x1801bc643  and     eax, 0FFFFFFFEh
0x1801bc646  or      ecx, eax
0x1801bc648  mov     [rdx+14h], ecx
0x1801bc64b  mov     eax, [r14+30h]
0x1801bc64f  shr     eax, 15h
0x1801bc652  and     al, r15b
0x1801bc655  mov     [rdx+1Fh], al
0x1801bc658  mov     eax, [r14+70h]
0x1801bc65c  mov     [rdx+18h], eax
0x1801bc65f  xor     eax, eax
0x1801bc661  cmp     [r14+0DCh], eax
0x1801bc668  setnz   al
0x1801bc66b  mov     [rdx+1Ch], al
0x1801bc66e  mov     al, [r14+0D8h]
0x1801bc675  not     al
0x1801bc677  and     al, r15b
0x1801bc67a  mov     [rdx+1Dh], al
0x1801bc67d  mov     eax, [r14+0D8h]
0x1801bc684  shr     eax, 1
0x1801bc686  not     al
0x1801bc688  and     al, r15b
  ... truncated ...
```
