# CBackupSession::ProcessSingleFileEvent(_DPEL_EVENT *,ATL::CAtlArray<long,ATL::CElementTraits<long>> &)

- ea: `0x18001cb74`
- end: `0x18001eae7`
- name: `?ProcessSingleFileEvent@CBackupSession@@AEAAJPEAU_DPEL_EVENT@@AEAV?$CAtlArray@JV?$CElementTraits@J@ATL@@@ATL@@@Z`
- size: `8051`
- prototype: `__int64 __fastcall(CBackupSession *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `48`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fee4`

## callees

- `0x1800025b0`
- `0x1800042e8`
- `0x1800077f0`
- `0x180007818`
- `0x180007a1c`
- `0x180007a9c`
- `0x180007c08`
- `0x180007d5c`
- `0x180009008`
- `0x1800090f8`
- `0x180009258`
- `0x18000935c`
- `0x1800093a8`
- `0x1800094d0`
- `0x180009528`
- `0x180009560`
- `0x1800095c8`
- `0x18000960c`
- `0x18000a42c`
- `0x18000a4ac`
- `0x18000a818`
- `0x18000c360`
- `0x18000c450`
- `0x18000d0fc`
- `0x18000de68`
- `0x18000f728`
- `0x18000fde8`
- `0x180010844`
- `0x180010b18`
- `0x180012278`
- `0x180012418`
- `0x1800124a0`
- `0x180012520`
- `0x1800125b8`
- `0x18001284c`
- `0x18001990c`
- `0x180019cfc`
- `0x18001a7d0`
- `0x18001cb74`
- `0x1800220a4`
- `0x1800222f0`
- `0x18002235c`
- `0x180022608`
- `0x1800226ec`
- `0x18002acd4`
- `0x180030aac`
- `0x180031642`
- `0x180031680`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001d14c`
- `msvcrt!_wcsnicmp` at `0x18001d14c`
- `ADVAPI32!SystemFunction036` at `0x18001dddc`
- `ADVAPI32!SystemFunction036` at `0x18001dddc`
- `KERNEL32!GetLastError` at `0x18001cf4c`
- `KERNEL32!GetLastError` at `0x18001cf4c`
- `KERNEL32!GetFileAttributesExW` at `0x18001cf37`
- `KERNEL32!GetFileAttributesExW` at `0x18001cf37`
- `KERNEL32!CompareStringOrdinal` at `0x18001ccc9`
- `KERNEL32!CompareStringOrdinal` at `0x18001ccc9`
- `KERNEL32!FindFirstFileW` at `0x18001d17c`
- `KERNEL32!FindFirstFileW` at `0x18001d17c`
- `ntdll!RtlIsPartialPlaceholder` at `0x18001d19a`
- `ntdll!RtlIsPartialPlaceholder` at `0x18001d19a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d0c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d0c4`
- `SHELL32!SHGetKnownFolderPath` at `0x18001d086`
- `SHELL32!SHGetKnownFolderPath` at `0x18001d086`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CBackupSession::ProcessSingleFileEvent(CBackupSession *a1, _QWORD *a2, __int64 a3)
{
  unsigned __int16 *v5; // rdx
  int v6; // r8d
  int v7; // eax
  int v8; // r14d
  int v9; // eax
  LPCWSTR *v10; // r8
  const WCHAR *v11; // rcx
  CBackupSession *v12; // rcx
  PVOID v13; // rcx
  unsigned __int16 *v14; // r14
  PVOID v15; // rcx
  unsigned __int16 *v16; // rbx
  int PreviousVersionStats; // eax
  PVOID *v18; // r10
  int v19; // edx
  __int64 v20; // r9
  __int16 v21; // ax
  _QWORD *v22; // rax
  char v23; // r14
  LPCWSTR v24; // rbx
  unsigned __int64 v25; // rax
  size_t v26; // r8
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  int v29; // r14d
  bool v30; // zf
  __int64 *v31; // rbx
  const unsigned __int16 *v32; // rdx
  int v33; // eax
  int LastNamespaceRecord; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  _DWORD *v37; // rbx
  int PreviousNamespaceRecord; // eax
  unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  int v42; // eax
  __int64 v43; // r9
  __int64 v44; // rax
  __int64 *v45; // rdi
  CSessionBaseRW *v46; // rcx
  _DWORD *v47; // rdi
  __int16 v48; // cx
  CSessionBaseRW *v49; // rcx
  PVOID *v50; // rcx
  __int64 v51; // r9
  CSessionBaseRW *v52; // rcx
  CBackupSession *v53; // rbx
  CSessionBaseRW *v54; // rcx
  int v55; // eax
  _QWORD *v56; // rcx
  CFileRecord *v57; // r9
  __int64 v58; // rdx
  CFileRecord **v59; // rsi
  CSessionBaseRW *v60; // rcx
  int v61; // eax
  unsigned __int16 *v62; // rax
  char *v63; // rcx
  int v64; // eax
  CFileRecord *v65; // r9
  __int64 v66; // rdx
  CFileRecord *v67; // rsi
  __int64 v68; // rax
  CBackupSession *v69; // r14
  __int64 v70; // rax
  int v71; // ecx
  CFileRecord *v72; // rax
  CFileRecord *v73; // rcx
  int v74; // eax
  CFileRecord *v75; // r9
  int v76; // edx
  _QWORD *v77; // r8
  CFileRecord *v78; // rdi
  __int64 v79; // rax
  _QWORD *v80; // rdx
  __int64 v81; // rdx
  _QWORD *v82; // r8
  CSessionBaseRW *v83; // rcx
  int v84; // eax
  int v85; // r9d
  __int64 v86; // rax
  CSessionBaseRW *v87; // rcx
  int v88; // eax
  int v89; // ecx
  __int64 v90; // rax
  __int64 v91; // rax
  CNamespaceRecord *v92; // rax
  CBackupSession *v93; // r14
  CNamespaceRecord *v94; // rax
  CNamespaceRecord **v95; // rsi
  int v96; // ecx
  CNamespaceRecord *v97; // rbx
  int v98; // edi
  __int64 v99; // rax
  __int64 v100; // r8
  int v101; // edi
  __int64 v102; // rcx
  unsigned __int64 v103; // rbx
  int v104; // ebx
  __int64 v105; // rax
  const unsigned __int16 *v106; // rdi
  _QWORD *v107; // rax
  int NamespaceFilePair; // eax
  __int64 ***v109; // rbx
  __int64 **v110; // rdx
  __int64 **v111; // rax
  CNamespaceRecord **v112; // rdi
  _QWORD *v113; // r8
  PVOID *v114; // r11
  unsigned __int64 RandomBuffer; // [rsp+50h] [rbp-3A8h] BYREF
  int v117; // [rsp+58h] [rbp-3A0h]
  CBackupSession *v118; // [rsp+60h] [rbp-398h]
  _QWORD *v119; // [rsp+68h] [rbp-390h] BYREF
  unsigned __int16 *v120; // [rsp+70h] [rbp-388h]
  LPCWSTR lpFileName; // [rsp+78h] [rbp-380h]
  _DWORD *v122; // [rsp+80h] [rbp-378h] BYREF
  __int64 *v123; // [rsp+88h] [rbp-370h] BYREF
  __int64 v124; // [rsp+90h] [rbp-368h] BYREF
  int v125; // [rsp+98h] [rbp-360h]
  _DWORD *v126; // [rsp+A0h] [rbp-358h] BYREF
  int v127; // [rsp+A8h] [rbp-350h]
  BOOL FileAttributes; // [rsp+ACh] [rbp-34Ch]
  _QWORD *v129; // [rsp+B0h] [rbp-348h]
  PWSTR ppszPath; // [rsp+C0h] [rbp-338h] BYREF
  CNamespaceRecord **v131; // [rsp+C8h] [rbp-330h] BYREF
  int v132; // [rsp+D0h] [rbp-328h] BYREF
  const unsigned __int16 **v133; // [rsp+D8h] [rbp-320h]
  __int64 ***v134; // [rsp+E0h] [rbp-318h] BYREF
  char *v135; // [rsp+E8h] [rbp-310h]
  CBackupSession *v136; // [rsp+F0h] [rbp-308h]
  __int64 v137; // [rsp+F8h] [rbp-300h] BYREF
  __int64 v138; // [rsp+100h] [rbp-2F8h]
  _QWORD *v139; // [rsp+108h] [rbp-2F0h]
  int v140; // [rsp+114h] [rbp-2E4h] BYREF
  int v141; // [rsp+118h] [rbp-2E0h] BYREF
  int v142; // [rsp+11Ch] [rbp-2DCh] BYREF
  unsigned __int16 *v143; // [rsp+120h] [rbp-2D8h]
  __int64 v144; // [rsp+128h] [rbp-2D0h]
  __int128 FileInformation; // [rsp+130h] [rbp-2C8h] BYREF
  __int128 v146; // [rsp+140h] [rbp-2B8h]
  unsigned int v147; // [rsp+150h] [rbp-2A8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+160h] [rbp-298h] BYREF

  v139 = (_QWORD *)a3;
  v123 = a2;
  v118 = a1;
  v144 = a3;
  v119 = a2;
  v136 = a1;
  v129 = a2;
  v138 = a3;
  FileInformation = 0;
  v146 = 0;
  v147 = 0;
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v122);
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v131);
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v126);
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v134);
  v137 = -1;
  v132 = 0;
  v5 = (unsigned __int16 *)(a2 + 2);
  v120 = (unsigned __int16 *)(a2 + 2);
  v6 = *((_DWORD *)a2 + 4);
  if ( (v6 & 8) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_iiiiDSS(*((_QWORD *)WPP_GLOBAL_Control + 2), a2[5], a2[6], a2[3], v6, *a2, a2[1]);
    v7 = CompareStringOrdinal((LPCWCH)*a2, -1, (LPCWCH)a2[1], -1, 1);
    v5 = v120;
    if ( v7 == 2 )
    {
      if ( *(_DWORD *)v120 == 8 )
      {
        v8 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
        goto LABEL_423;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
        v5 = v120;
      }
      *(_DWORD *)v5 &= ~8u;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_iiiiDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, v6, a2[4], a2[5], a2[6], a2[3], v6, *a2);
    v5 = v120;
  }
  v143 = v5;
  FileAttributes = 0;
  v117 = 0;
  v127 = 0;
  v125 = 0;
  v9 = *(_DWORD *)v5;
  v10 = (LPCWSTR *)(a2 + 1);
  v133 = (const unsigned __int16 **)(a2 + 1);
  RandomBuffer = (unsigned __int64)(a2 + 1);
  if ( (v9 & 8) != 0 )
    v11 = *v10;
  else
    v11 = (const WCHAR *)*a2;
  lpFileName = v11;
  v12 = v118;
  *((_DWORD *)v118 + 211) += v9 & 1;
  *((_DWORD *)v12 + 212) += (*(_DWORD *)v5 >> 1) & 1;
  *((_DWORD *)v12 + 213) += (*(_DWORD *)v5 >> 3) & 1;
  *((_DWORD *)v12 + 214) += (*(_DWORD *)v5 >> 2) & 1;
  *((_DWORD *)v12 + 215) += (*((_DWORD *)a2 + 14) >> 14) & 1;
  ++*((_DWORD *)v12 + 216);
  if ( (*(_BYTE *)v5 & 8) != 0 )
  {
    if ( !FhePathOperations::IsSourcePathSupported(*v10, v5) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(v13, FileFailure_NameNotSupported, *v133);
      v14 = v120;
      *(_DWORD *)v120 = 4;
      goto LABEL_37;
    }
LABEL_36:
    v14 = v120;
    goto LABEL_37;
  }
  if ( FhePathOperations::IsSourcePathSupported((LPCWSTR)*a2, v5) )
    goto LABEL_36;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(v15, FileFailure_NameNotSupported, *a2);
  v14 = v120;
  *(_DWORD *)v120 = 4;
  if ( !a2[5] )
    a2[5] = a2[3];
LABEL_37:
  if ( (*(_BYTE *)v14 & 0xB) == 0 || (*(_BYTE *)v14 & 4) != 0 )
  {
LABEL_40:
    v16 = v120;
    goto LABEL_41;
  }
  FileAttributes = GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation);
  if ( FileAttributes )
  {
    v21 = FileInformation;
    if ( (FileInformation & 0x4000) == 0 || *((_DWORD *)v118 + 92) )
      goto LABEL_55;
  }
  else if ( GetLastError() != 5 )
  {
    goto LABEL_40;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
  v22 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                    (__int64)&v124,
                    lpFileName);
  CBackupSession::LogFilePermissionFailure((__int64)v118, v22);
  *(_DWORD *)v14 = 4;
  if ( !a2[5] )
    a2[5] = a2[3];
  if ( !FileAttributes )
    goto LABEL_40;
  v21 = FileInformation;
LABEL_55:
  if ( (v21 & 0x400) == 0 )
    goto LABEL_40;
  v23 = 1;
  ppszPath = 0;
  if ( SHGetKnownFolderPath(&FOLDERID_SkyDrive, 0x4000u, 0, &ppszPath) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
    goto LABEL_60;
  }
  v25 = -1;
  v26 = -1;
  do
    ++v26;
  while ( ppszPath[v26] );
  do
    ++v25;
  while ( lpFileName[v25] );
  if ( v26 > v25 )
    goto LABEL_60;
  if ( _wcsnicmp(ppszPath, lpFileName, v26) )
    goto LABEL_60;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( FindFirstFileW(lpFileName, &FindFileData) == (HANDLE)-1LL )
    goto LABEL_60;
  if ( !(unsigned __int8)RtlIsPartialPlaceholder(FindFileData.dwFileAttributes, FindFileData.dwReserved0) )
  {
    v23 = 0;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v28 = 226;
      goto LABEL_77;
    }
LABEL_60:
    v24 = lpFileName;
    goto LABEL_61;
  }
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    goto LABEL_60;
  v28 = 225;
LABEL_77:
  v24 = lpFileName;
  WPP_SF_S(v27[2], v28, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, lpFileName);
LABEL_61:
  CoTaskMemFree(ppszPath);
  if ( !v23 )
    goto LABEL_40;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v24);
  v16 = v120;
  *(_DWORD *)v120 = 4;
  if ( !a2[5] )
    a2[5] = a2[3];
LABEL_41:
  PreviousVersionStats = CBackupSession::GetPreviousVersionStats(
                           v118,
                           (struct _DPEL_EVENT *)a2,
                           (struct _WIN32_FILE_ATTRIBUTE_DATA *)((unsigned __int64)&FileInformation
                                                               & -(__int64)FileAttributes),
                           &v137,
                           &v132);
  v8 = PreviousVersionStats;
  if ( PreviousVersionStats < 0 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_423;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_414;
    v19 = 228;
LABEL_45:
    v20 = *v123;
LABEL_412:
    WPP_SF_Sd(
      (unsigned int)v18[2],
      v19,
      (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      v20,
      PreviousVersionStats);
    goto LABEL_413;
  }
  v29 = (_DWORD)v118 + 16;
  v135 = (char *)v118 + 16;
  v30 = (*(_BYTE *)v16 & 0xC) == 0;
  v31 = v123;
  v32 = (const unsigned __int16 *)*v123;
  if ( !v30 )
  {
    v33 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v124,
            v32);
    LastNamespaceRecord = CSessionBaseRO::GetLastNamespaceRecord(v29, v33, (int)&v122, 1, 0);
    v8 = LastNamespaceRecord;
    if ( LastNamespaceRecord < 0 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          229,
          (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          *v31,
          LastNamespaceRecord);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_414;
    }
    while ( 1 )
    {
      v37 = v122;
      if ( !v122 || !*(_QWORD *)v122 || (__int64)(*(_QWORD *)(*(_QWORD *)v122 + 48LL) - a2[5]) <= 0 )
        break;
      SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&ppszPath);
      v117 = *(_DWORD *)(*(_QWORD *)v37 + 76LL);
      v127 = v117;
      v124 = (__int64)v37;
      if ( v37 )
        ++v37[2];
      PreviousNamespaceRecord = CSessionBaseRO::GetPreviousNamespaceRecord(v135, &v124, &ppszPath, 1);
      v8 = PreviousNamespaceRecord;
      if ( PreviousNamespaceRecord < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            230,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            *(unsigned int *)(*(_QWORD *)v37 + 16LL),
            PreviousNamespaceRecord);
        SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&ppszPath);
        v18 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_414;
      }
      SmartPtr<CNamespaceRecord>::operator=(&v122, &ppszPath);
      SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&ppszPath);
    }
    v39 = v120;
    if ( (*(_BYTE *)v120 & 1) != 0 )
    {
      if ( v122 )
      {
        if ( *(_QWORD *)v122 )
        {
          v40 = *(_QWORD *)(*(_QWORD *)v122 + 48LL);
          if ( v40 - a2[4] < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
            SmartPtr<CNamespaceRecord>::operator=(&v122, 0);
            v117 = 0;
            v127 = 0;
            v37 = v122;
            v39 = v120;
          }
        }
      }
    }
    if ( *(_DWORD *)v39 == 5 )
    {
      *(_DWORD *)v39 = 4;
      v18 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_118;
    }
    goto LABEL_117;
  }
  v41 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v124,
          v32);
  v42 = CSessionBaseRO::GetLastNamespaceRecord(v29, v41, (int)&v122, 1, 0);
  v8 = v42;
  if ( v42 < 0 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        232,
        (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        *v31,
        v42);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_414;
  }
  v37 = v122;
  if ( !v122
    || !*(_QWORD *)v122
    || (v43 = *(_QWORD *)v122, *(_DWORD *)(*(_QWORD *)v122 + 80LL) == -1) && (*(_BYTE *)(v43 + 40) & 1) == 0 )
  {
LABEL_117:
    v18 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_118;
  }
  v44 = a2[3];
  if ( *(_QWORD *)(v43 + 48) != v44 )
  {
    SmartPtr<CNamespaceRecord>::operator=(&v122, 0);
    v37 = v122;
    goto LABEL_117;
  }
  v125 = 1;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    v45 = v123;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        233,
        (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        *(_DWORD *)(v43 + 16),
        *v123);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_122;
  }
LABEL_118:
  v45 = v123;
LABEL_122:
  if ( !v37 )
    goto LABEL_185;
  if ( *(_QWORD *)v37 && (*(_BYTE *)(*(_QWORD *)v37 + 40LL) & 2) != 0 )
  {
    if ( v18 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v18 + 28) & 2) != 0 )
      {
        WPP_SF_dDdd(
          v18[2],
          v35,
          v36,
          *(unsigned int *)(*(_QWORD *)v37 + 16LL),
          *(unsigned __int16 *)(*(_QWORD *)v37 + 40LL),
          *(_DWORD *)(*(_QWORD *)v37 + 76LL),
          *(_DWORD *)(*(_QWORD *)v37 + 80LL));
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 )
        WPP_SF_d(
          v18[2],
          236,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          *(unsigned int *)(*(_QWORD *)v37 + 16LL));
    }
    v46 = (CBackupSession *)((char *)v118 + 8);
    RandomBuffer = (unsigned __int64)v37;
    ++v37[2];
    PreviousVersionStats = CSessionBaseRW::FinalizeNamespaceRecord(v46, v117);
    v8 = PreviousVersionStats;
    if ( PreviousVersionStats < 0 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_423;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_414;
      v19 = 237;
LABEL_135:
      v20 = *v45;
      goto LABEL_412;
    }
    SmartPtr<CNamespaceRecord>::operator=(&v122, 0);
    v47 = v126;
    goto LABEL_137;
  }
  if ( !*(_QWORD *)v37 || (*(_BYTE *)(*(_QWORD *)v37 + 40LL) & 2) != 0 )
  {
LABEL_185:
    v47 = v126;
    goto LABEL_139;
  }
  RandomBuffer = (unsigned __int64)v37;
  ++v37[2];
  PreviousVersionStats = CSessionBaseRO::GetFileRecord(v135, &RandomBuffer, &v126);
  v8 = PreviousVersionStats;
  if ( PreviousVersionStats < 0 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_423;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_414;
    v19 = 238;
    goto LABEL_135;
  }
  v47 = v126;
  if ( !v126 || !*(_QWORD *)v126 )
  {
    v50 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_dDddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        239,
        *(unsigned __int16 *)(*(_QWORD *)v37 + 40LL),
        *(unsigned int *)(*(_QWORD *)v37 + 16LL),
        *(unsigned __int16 *)(*(_QWORD *)v37 + 40LL),
        *(_DWORD *)(*(_QWORD *)v37 + 76LL),
        *(_DWORD *)(*(_QWORD *)v37 + 80LL),
        *(_DWORD *)(*(_QWORD *)v37 + 84LL));
      v50 = (PVOID *)WPP_GLOBAL_Control;
    }
    v51 = *(unsigned int *)(*(_QWORD *)v37 + 84LL);
    if ( (_DWORD)v51 )
    {
      if ( v50 != &WPP_GLOBAL_Control && (*((_BYTE *)v50 + 28) & 2) != 0 )
        WPP_SF_d(v50[2], 240, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v51);
      PreviousVersionStats = CSessionBaseRW::RemoveNamespaceRecordsByFileRecordRef(
                               (CBackupSession *)((char *)v118 + 8),
                               *(_DWORD *)(*(_QWORD *)v37 + 84LL),
                               0,
                               v117);
      v8 = PreviousVersionStats;
      if ( PreviousVersionStats < 0 )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_423;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_414;
        v19 = 241;
        goto LABEL_45;
      }
    }
    else
    {
      if ( v50 != &WPP_GLOBAL_Control && (*((_BYTE *)v50 + 28) & 2) != 0 )
        WPP_SF_d(
          v50[2],
          242,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          *(unsigned int *)(*(_QWORD *)v37 + 16LL));
      v52 = (CBackupSession *)((char *)v118 + 8);
      RandomBuffer = (unsigned __int64)v37;
      ++v37[2];
      PreviousVersionStats = CSessionBaseRW::FinalizeNamespaceRecord(v52, v117);
      v8 = PreviousVersionStats;
      if ( PreviousVersionStats < 0 )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_423;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_414;
        v19 = 243;
        goto LABEL_45;
      }
    }
    SmartPtr<CNamespaceRecord>::operator=(&v122, 0);
LABEL_137:
    v37 = v122;
LABEL_138:
    v18 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_139;
  }
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_ddDddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        244,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        *(unsigned int *)(*(_QWORD *)v126 + 16LL),
        *(unsigned __int16 *)(*(_QWORD *)v126 + 40LL),
        *(unsigned __int16 *)(*(_QWORD *)v126 + 42LL),
        *(_DWORD *)(*(_QWORD *)v126 + 56LL),
        *(_DWORD *)(*(_QWORD *)v126 + 60LL),
        *(_DWORD *)(*(_QWORD *)v126 + 64LL));
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
    {
      WPP_SF_dDddid(
        v18[2],
        245,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        *(unsigned int *)(*(_QWORD *)v37 + 16LL),
        *(unsigned __int16 *)(*(_QWORD *)v37 + 40LL),
        *(_DWORD *)(*(_QWORD *)v37 + 76LL),
        *(_DWORD *)(*(_QWORD *)v37 + 80LL),
        *(_QWORD *)(*(_QWORD *)v37 + 48LL),
        *(_DWORD *)(*(_QWORD *)v37 + 84LL));
      goto LABEL_138;
    }
  }
LABEL_139:
  if ( !v47 || !*(_QWORD *)v47 )
  {
    if ( (*(_BYTE *)v120 & 1) == 0 )
    {
      if ( (*(_BYTE *)v120 & 0xA) == 0 )
      {
        if ( *(_DWORD *)v120 == 4 )
        {
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
          {
            v81 = 247;
            goto LABEL_271;
          }
        }
        else if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
        {
          v81 = 248;
          goto LABEL_271;
        }
        goto LABEL_396;
      }
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 )
      {
        WPP_SF_(v18[2], 246, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    goto LABEL_379;
  }
  v48 = *(_WORD *)(*(_QWORD *)v47 + 40LL);
  if ( (unsigned __int16)(v48 - 3) <= 1u )
  {
    v82 = v129;
    if ( (v129[2] & 0xC) != 0 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
        WPP_SF_(v18[2], 249, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      v83 = (CBackupSession *)((char *)v118 + 8);
      RandomBuffer = (unsigned __int64)v37;
      v124 = (__int64)(v37 + 2);
      if ( v37 )
        ++v37[2];
      else
        v124 = 8;
      PreviousVersionStats = CSessionBaseRW::FinalizeNamespaceRecord(v83, v117);
      v8 = PreviousVersionStats;
      if ( PreviousVersionStats < 0 )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_423;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_414;
        v19 = 250;
        goto LABEL_45;
      }
      RandomBuffer = (unsigned __int64)v37;
      if ( v37 )
        ++*(_DWORD *)v124;
      v84 = CSessionBaseRW::NotifySearch((CBackupSession *)((char *)v118 + 8));
      v8 = v84;
      if ( v84 >= 0 )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      else
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            251,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            (unsigned int)v84);
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
        v8 = 0;
      }
      v82 = v129;
      if ( (v129[2] & 4) == 0 )
        goto LABEL_317;
    }
    else
    {
      v85 = v125;
      if ( v125 )
        goto LABEL_318;
      if ( (v129[2] & 1) == 0 )
        goto LABEL_318;
      if ( (*(_BYTE *)(*(_QWORD *)v37 + 40LL) & 8) != 0 )
      {
        v86 = *(_QWORD *)(*(_QWORD *)v37 + 48LL);
        if ( v86 - v129[6] >= 0 )
          goto LABEL_318;
      }
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
        WPP_SF_(v18[2], 252, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      v87 = (CBackupSession *)((char *)v118 + 8);
      RandomBuffer = (unsigned __int64)v37;
      if ( v37 )
        ++v37[2];
      PreviousVersionStats = CSessionBaseRW::FinalizeNamespaceRecord(v87, v117);
      v8 = PreviousVersionStats;
      if ( PreviousVersionStats < 0 )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_423;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_414;
        v19 = 253;
        goto LABEL_45;
      }
      RandomBuffer = (unsigned __int64)v37;
      if ( v37 )
        ++v37[2];
      v88 = CSessionBaseRW::NotifySearch((CBackupSession *)((char *)v118 + 8));
      v8 = v88;
      if ( v88 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            254,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            (unsigned int)v88);
        v8 = 0;
      }
    }
    SmartPtr<CNamespaceRecord>::operator=(&v122, 0);
    SmartPtr<CFileRecord>::operator=(&v126, 0);
    v82 = v129;
    v18 = (PVOID *)WPP_GLOBAL_Control;
    v47 = v126;
    v37 = v122;
LABEL_317:
    v85 = v125;
LABEL_318:
    v89 = *((_DWORD *)v82 + 4);
    if ( v89 == 8 || (v89 & 8) != 0 && (v90 = *(_QWORD *)(*(_QWORD *)v37 + 48LL), v90 - v82[6] >= 0) || v85 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
        WPP_SF_dS(
          (int)v18[2],
          255,
          (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          *(_DWORD *)(*(_QWORD *)v47 + 16LL),
          v82[1]);
      v92 = (CNamespaceRecord *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
      v93 = v118;
      if ( v92 )
        v94 = CNamespaceRecord::CNamespaceRecord(v92, (__int64 *)v118 + 3, (__int64)v118 + 32);
      else
        v94 = 0;
      SmartPtr<CNamespaceRecord>::operator=(&v131, v94);
      v95 = v131;
      if ( !v131 || !*v131 )
      {
        v8 = -2147024882;
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_423;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_414;
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          256,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          "newNamespaceRecord");
        goto LABEL_413;
      }
      *((_WORD *)*v131 + 20) = 4;
      *((_QWORD *)*v95 + 6) = v129[3];
      *((_DWORD *)*v95 + 14) = *(_DWORD *)(*(_QWORD *)v37 + 56LL);
      *(_QWORD *)((char *)*v95 + 60) = *(_QWORD *)(*(_QWORD *)v37 + 60LL);
      *(_QWORD *)((char *)*v95 + 68) = *(_QWORD *)(*(_QWORD *)v37 + 68LL);
      v96 = v117;
      if ( !v117 )
        v96 = *((_DWORD *)v93 + 11);
      *((_DWORD *)*v95 + 19) = v96;
      *((_DWORD *)*v95 + 20) = -1;
      *((_DWORD *)*v95 + 21) = *(_DWORD *)(*(_QWORD *)v47 + 16LL);
      v97 = *v95;
      v98 = (int)lpFileName;
      v99 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64)&v119,
              lpFileName);
      PreviousVersionStats = CNamespaceRecord::SetName(v97, v99);
      v8 = PreviousVersionStats;
      if ( PreviousVersionStats >= 0 )
      {
        PreviousVersionStats = CNamespaceRecord::Commit(*v95);
        v8 = PreviousVersionStats;
        if ( PreviousVersionStats >= 0 )
        {
          try
          {
            v101 = *((_DWORD *)*v95 + 4);
            v102 = v138;
            v103 = *(_QWORD *)(v138 + 8);
            if ( v103 >= *(_QWORD *)(v138 + 16) )
            {
              if ( !ATL::CAtlArray<long,ATL::CElementTraits<long>>::GrowBuffer(v138, v103 + 1) )
                ATL::AtlThrowImpl(-2147024882);
              v102 = v138;
            }
            *(_DWORD *)(*v139 + 4 * v103) = v101;
            ++*(_QWORD *)(v102 + 8);
          }
          catch ( ATL::CAtlException v141 )
          {
            LODWORD(v120) = v141;
            if ( v141 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_dSd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  259,
                  (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  *((_DWORD *)*v131 + 4),
                  (__int64)lpFileName,
                  v141);
              v8 = (int)v120;
              goto LABEL_395;
            }
            v95 = v131;
            v117 = v127;
            v8 = (int)v120;
            v118 = v136;
          }
          v104 = (int)lpFileName;
          if ( v125 )
          {
            v105 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                     (__int64)&v119,
                     lpFileName);
            PreviousVersionStats = CSessionBaseRW::RefreshParentDirNamespaceRecords(
                                     (CBackupSession *)((char *)v118 + 8),
                                     (_QWORD *)v105,
                                     2,
                                     v117);
            v8 = PreviousVersionStats;
            if ( PreviousVersionStats < 0 )
            {
              v18 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                goto LABEL_423;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_414;
              v19 = 260;
              LODWORD(v20) = v104;
              goto LABEL_412;
            }
          }
          v18 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_dDddd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              261,
              v100,
              *((unsigned int *)*v95 + 4),
              *((unsigned __int16 *)*v95 + 20),
              *((_DWORD *)*v95 + 19),
              *((_DWORD *)*v95 + 20),
              *((_DWORD *)*v95 + 21));
            goto LABEL_395;
          }
          goto LABEL_396;
        }
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_423;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_414;
        v19 = 258;
      }
      else
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_423;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_414;
        v19 = 257;
      }
      LODWORD(v20) = v98;
      goto LABEL_412;
    }
    if ( (v89 & 3) == 0 )
    {
      if ( v89 != 4 )
      {
        if ( v89 == 32 )
        {
          *(_QWORD *)(*(_QWORD *)v37 + 48LL) = v82[3];
          PreviousVersionStats = CNamespaceRecord::Commit(*(CNamespaceRecord **)v37);
          v8 = PreviousVersionStats;
          if ( PreviousVersionStats >= 0 )
            goto LABEL_423;
          v18 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_423;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_414;
          v19 = 263;
          goto LABEL_411;
        }
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
        {
          v81 = 264;
          goto LABEL_271;
        }
      }
      goto LABEL_396;
    }
    if ( (v89 & 8) == 0 )
    {
      if ( v37 )
      {
        if ( *(_QWORD *)v37 )
        {
          v91 = *(_QWORD *)(*(_QWORD *)v37 + 48LL);
          if ( v91 - v82[6] >= 0 )
          {
            if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
            {
              v81 = 262;
              goto LABEL_271;
            }
            goto LABEL_396;
          }
        }
      }
    }
LABEL_379:
    v53 = v118;
LABEL_380:
    v106 = lpFileName;
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
      WPP_SF_S(v18[2], 282, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, lpFileName);
    try
    {
      v107 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                         (__int64)&v119,
                         v106);
      NamespaceFilePair = CSessionBaseRW::CreateNamespaceFilePair(
                            (__int64)v53 + 8,
                            v107,
                            v117,
                            (__int64 **)&v131,
                            (__int64 **)&v134);
    }
    catch ( ATL::CAtlException v142 )
    {
      LODWORD(v120) = v142;
      if ( v142 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            284,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            (unsigned int)v142);
        v8 = (int)v120;
        goto LABEL_395;
      }
      LODWORD(v106) = (_DWORD)lpFileName;
      goto LABEL_398;
    }
    v8 = NamespaceFilePair;
    if ( NamespaceFilePair < 0 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          283,
          (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (_DWORD)v106,
          NamespaceFilePair);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_414;
    }
LABEL_398:
    v109 = v134;
    if ( FileAttributes )
    {
      v110 = *v134;
      *((_DWORD *)v110 + 19) = 1;
      v110[6] = (__int64 *)(v147 + ((unsigned __int64)HIDWORD(v146) << 32));
    }
    if ( v132 && (v129[2] & 8) == 0 )
    {
      v111 = *v109;
      *((_DWORD *)v111 + 19) = 1;
      *((_WORD *)v111 + 21) |= 2u;
    }
    PreviousVersionStats = CFileRecord::Commit(*v109);
    v8 = PreviousVersionStats;
    if ( PreviousVersionStats < 0 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_423;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_414;
      v19 = 285;
      LODWORD(v20) = (_DWORD)v106;
      goto LABEL_412;
    }
    v112 = v131;
    v113 = v129;
    *((_QWORD *)*v131 + 6) = v129[3];
    *(_QWORD *)((char *)*v112 + 60) = v137;
    *(_QWORD *)((char *)*v112 + 68) = v113[3];
    *((_DWORD *)*v112 + 21) = *((_DWORD *)*v109 + 4);
    PreviousVersionStats = CNamespaceRecord::Commit(*v112);
    v8 = PreviousVersionStats;
    if ( PreviousVersionStats >= 0 )
    {
      v114 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_ddDddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            287,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            *((unsigned int *)*v109 + 4),
            *((unsigned __int16 *)*v109 + 20),
            *((unsigned __int16 *)*v109 + 21),
            *((_DWORD *)*v109 + 14),
            *((_DWORD *)*v109 + 15),
            *((_DWORD *)*v109 + 16));
          v114 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v114 != &WPP_GLOBAL_Control && (*((_BYTE *)v114 + 28) & 8) != 0 )
          WPP_SF_dDddid(
            v114[2],
            288,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            *((unsigned int *)*v112 + 4),
            *((unsigned __int16 *)*v112 + 20),
            *((_DWORD *)*v112 + 19),
            *((_DWORD *)*v112 + 20),
            *((_QWORD *)*v112 + 6),
            *((_DWORD *)*v112 + 21));
      }
      goto LABEL_423;
    }
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_423;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_414;
    v19 = 286;
LABEL_411:
    LODWORD(v20) = (_DWORD)lpFileName;
    goto LABEL_412;
  }
  if ( ((v48 - 1) & 0xFFFA) != 0 || v48 == 6 )
  {
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
    {
      v81 = 281;
      goto LABEL_271;
    }
LABEL_396:
    if ( v8 >= 0 )
      goto LABEL_423;
    goto LABEL_414;
  }
  if ( (*(_BYTE *)v120 & 4) == 0 )
  {
    if ( (*(_BYTE *)v120 & 1) != 0 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
        WPP_SF_(v18[2], 267, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      v53 = v118;
      v54 = (CBackupSession *)((char *)v118 + 8);
      RandomBuffer = (unsigned __int64)v47;
      ++v47[2];
      PreviousVersionStats = CSessionBaseRW::RemoveFileRecord(v54, &RandomBuffer, 1, v117);
      v8 = PreviousVersionStats;
      if ( PreviousVersionStats < 0 )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_423;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_414;
        v19 = 268;
        goto LABEL_45;
      }
      SmartPtr<CNamespaceRecord>::operator=(&v122, 0);
      SmartPtr<CFileRecord>::operator=(&v126, 0);
      v18 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_380;
    }
    if ( (*(_BYTE *)v120 & 0xA) != 0 )
    {
      if ( (*(_BYTE *)v120 & 8) != 0 )
      {
        SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v123);
        RandomBuffer = (unsigned __int64)v37;
        if ( v37 )
          ++v37[2];
        v55 = CSessionBaseRO::GetPreviousNamespaceRecord(v135, &RandomBuffer, &v123, 0);
        v8 = v55;
        if ( v55 < 0 )
        {
          v56 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_205;
          v57 = *(CFileRecord **)v37;
          v58 = 269;
LABEL_204:
          WPP_SF_dd(v56[2], v58, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, *((unsigned int *)v57 + 4), v55);
LABEL_205:
          SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v123);
LABEL_413:
          v18 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_414;
        }
        v59 = (CFileRecord **)v123;
        if ( v123 && *v123 )
        {
          v60 = (CBackupSession *)((char *)v118 + 8);
          RandomBuffer = (unsigned __int64)v123;
          v124 = (__int64)(v123 + 1);
          ++*((_DWORD *)v123 + 2);
          v55 = CSessionBaseRW::FinalizeNamespaceRecord(v60, v117);
          v8 = v55;
          if ( v55 < 0 )
          {
            v56 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_205;
            v57 = *v59;
            v58 = 270;
            goto LABEL_204;
          }
          RandomBuffer = (unsigned __int64)v59;
          if ( v59 )
            ++*(_DWORD *)v124;
          v61 = CSessionBaseRW::NotifySearch((CBackupSession *)((char *)v118 + 8));
          if ( v61 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              271,
              &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
              (unsigned int)v61);
        }
        SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v123);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
        WPP_SF_S(v18[2], 272, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, lpFileName);
      v62 = v120;
      if ( (*(_BYTE *)v120 & 8) != 0 )
      {
        v63 = (char *)v118 + 8;
        RandomBuffer = (unsigned __int64)v47;
        v124 = (__int64)(v47 + 2);
        ++v47[2];
        v64 = CSessionBaseRW::CleanupFileRecord((__int64)v63, (CFileRecord ***)&RandomBuffer, 1, 0);
        v8 = v64;
        if ( v64 < 0 )
        {
          v18 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_423;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_414;
          v65 = *(CFileRecord **)v47;
          v66 = 273;
LABEL_227:
          WPP_SF_dd(v18[2], v66, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, *((unsigned int *)v65 + 4), v64);
          goto LABEL_413;
        }
        RandomBuffer = (unsigned __int64)v47;
        ++*(_DWORD *)v124;
        CSessionBaseRW::ChangeFileRecordStatus((char *)v118 + 8, &RandomBuffer, 1);
        v67 = *(CFileRecord **)v47;
        v68 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)&v119,
                *v133);
        v64 = CFileRecord::SetName(v67, v68);
        v8 = v64;
        if ( v64 < 0 )
        {
          v18 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_423;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_414;
          v65 = *(CFileRecord **)v47;
          v66 = 274;
          goto LABEL_227;
        }
        v62 = v120;
      }
      if ( (*(_BYTE *)v62 & 2) != 0 )
      {
        if ( (*(_BYTE *)(*(_QWORD *)v47 + 42LL) & 0x18) != 0 )
        {
          try
          {
            RandomBuffer = 0;
            SystemFunction036(&RandomBuffer, 8u);
            v69 = v118;
            ++*((_DWORD *)v118 + 250);
            if ( !(RandomBuffer % *((unsigned int *)v69 + 250)) )
            {
              v70 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                      (__int64)&v119,
                      lpFileName);
              FheFileOperations::ExtractTruncatedFileExt(v70, (char *)v69 + 1016);
            }
          }
          catch ( ATL::CAtlException v140 )
          {
            LODWORD(v120) = v140;
            if ( v140 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  275,
                  &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  (unsigned int)v140);
              v8 = (int)v120;
              goto LABEL_395;
            }
            v37 = v122;
            v47 = v126;
            v117 = v127;
            v69 = v136;
            v118 = v136;
          }
        }
        else
        {
          v69 = v118;
        }
        v71 = *((_DWORD *)v69 + 11);
        v72 = *(CFileRecord **)v47;
        *((_DWORD *)v72 + 19) = 1;
        *((_DWORD *)v72 + 16) = v71;
        RandomBuffer = (unsigned __int64)v47;
        if ( v47 )
          ++v47[2];
        CSessionBaseRW::ChangeFileRecordStatus((char *)v69 + 8, &RandomBuffer, 4);
        v73 = *(CFileRecord **)v47;
        if ( *(_WORD *)(*(_QWORD *)v47 + 40LL) == 5 )
        {
          v30 = (*((_WORD *)v73 + 21) & 0x10) == 0;
          *((_DWORD *)v73 + 19) = 1;
          if ( v30 )
            *((_WORD *)v73 + 20) = 1;
          else
            *((_WORD *)v73 + 20) = 2;
        }
      }
      v74 = CFileRecord::Commit(*(__int64 ***)v47);
      v8 = v74;
      if ( v74 >= 0 )
      {
        if ( !v117 )
          v117 = *((_DWORD *)v118 + 11);
        *(_DWORD *)(*(_QWORD *)v37 + 76LL) = v117;
        v77 = v129;
        *(_QWORD *)(*(_QWORD *)v37 + 48LL) = v129[3];
        *(_QWORD *)(*(_QWORD *)v37 + 60LL) = v137;
        *(_QWORD *)(*(_QWORD *)v37 + 68LL) = v77[3];
        if ( (v77[2] & 2) != 0 )
          *(_WORD *)(*(_QWORD *)v37 + 40LL) &= ~4u;
        if ( (v77[2] & 8) != 0 )
        {
          v78 = *(CFileRecord **)v37;
          v79 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  (__int64)&v119,
                  (const unsigned __int16 *)v77[1]);
          v64 = CNamespaceRecord::SetName(v78, v79);
          v8 = v64;
          if ( v64 < 0 )
          {
            v18 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              goto LABEL_423;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_414;
            v65 = *(CFileRecord **)v37;
            v66 = 277;
            goto LABEL_227;
          }
        }
        v74 = CNamespaceRecord::Commit(*(CNamespaceRecord **)v37);
        v8 = v74;
        if ( v74 >= 0 )
          goto LABEL_423;
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_423;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_414;
        v75 = *(CFileRecord **)v37;
        v76 = 278;
      }
      else
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_423;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_414;
        v75 = *(CFileRecord **)v47;
        v76 = 276;
      }
      WPP_SF_dSd(
        (int)v18[2],
        v76,
        (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        *((_DWORD *)v75 + 4),
        (__int64)lpFileName,
        v74);
      goto LABEL_413;
    }
    if ( *(_DWORD *)v120 == 32 )
    {
      v80 = v129;
      *(_QWORD *)(*(_QWORD *)v37 + 48LL) = v129[3];
      *(_QWORD *)(*(_QWORD *)v37 + 68LL) = v80[3];
      PreviousVersionStats = CNamespaceRecord::Commit(*(CNamespaceRecord **)v37);
      v8 = PreviousVersionStats;
      if ( PreviousVersionStats >= 0 )
        goto LABEL_423;
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_423;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_414;
      v19 = 279;
      goto LABEL_411;
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
    {
      v81 = 280;
LABEL_271:
      WPP_SF_(v18[2], v81, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
LABEL_395:
      v18 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_396;
    }
    goto LABEL_396;
  }
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
    WPP_SF_(v18[2], 265, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
  v49 = (CBackupSession *)((char *)v118 + 8);
  RandomBuffer = (unsigned __int64)v47;
  ++v47[2];
  PreviousVersionStats = CSessionBaseRW::RemoveFileRecord(v49, &RandomBuffer, 1, v117);
  v8 = PreviousVersionStats;
  if ( PreviousVersionStats >= 0 )
  {
    SmartPtr<CNamespaceRecord>::operator=(&v122, 0);
    SmartPtr<CFileRecord>::operator=(&v126, 0);
    goto LABEL_423;
  }
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_414:
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 4) != 0 )
        WPP_SF_s(v18[2], 289, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, "SUCCEEDED(hr)");
      goto LABEL_423;
    }
    v19 = 266;
    goto LABEL_45;
  }
LABEL_423:
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(&v134);
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(&v126);
  SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v131);
  SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v122);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001cb74  push    rbx
0x18001cb76  push    rsi
0x18001cb77  push    rdi
0x18001cb78  push    r12
0x18001cb7a  push    r13
0x18001cb7c  push    r14
0x18001cb7e  push    r15
0x18001cb80  sub     rsp, 3C0h
0x18001cb87  mov     rax, cs:__security_cookie
0x18001cb8e  xor     rax, rsp
0x18001cb91  mov     [rsp+3F8h+var_48], rax
0x18001cb99  mov     [rsp+3F8h+var_2F0], r8
0x18001cba1  mov     r14, rdx
0x18001cba4  mov     [rsp+3F8h+var_370], rdx
0x18001cbac  mov     [rsp+3F8h+var_398], rcx
0x18001cbb1  mov     [rsp+3F8h+var_2D0], r8
0x18001cbb9  mov     [rsp+3F8h+var_390], rdx
0x18001cbbe  mov     [rsp+3F8h+var_308], rcx
0x18001cbc6  mov     rdi, rdx
0x18001cbc9  mov     [rsp+3F8h+var_348], rdx
0x18001cbd1  mov     [rsp+3F8h+var_2F8], r8
0x18001cbd9  xorps   xmm0, xmm0
0x18001cbdc  xor     eax, eax
0x18001cbde  movups  [rsp+3F8h+FileInformation], xmm0
0x18001cbe6  movups  [rsp+3F8h+var_2B8], xmm0
0x18001cbee  mov     [rsp+3F8h+var_2A8], eax
0x18001cbf5  lea     rcx, [rsp+3F8h+var_378]
0x18001cbfd  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18001cc02  nop
0x18001cc03  lea     rcx, [rsp+3F8h+var_330]
0x18001cc0b  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18001cc10  nop
0x18001cc11  lea     rcx, [rsp+3F8h+var_358]
0x18001cc19  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18001cc1e  nop
0x18001cc1f  lea     rcx, [rsp+3F8h+var_318]
0x18001cc27  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18001cc2c  nop
0x18001cc2d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001cc31  mov     [rsp+3F8h+var_300], rsi
0x18001cc39  xor     r15d, r15d
0x18001cc3c  mov     [rsp+3F8h+var_328], r15d
0x18001cc44  lea     rdx, [rdi+10h]
0x18001cc48  mov     [rsp+3F8h+var_388], rdx
0x18001cc4d  mov     r8d, [rdx]
0x18001cc50  lea     ebx, [rsi+9]
0x18001cc53  test    bl, r8b
0x18001cc56  jz      loc_18001CD47
0x18001cc5c  lea     r13, WPP_GLOBAL_Control
0x18001cc63  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc6a  cmp     rcx, r13
0x18001cc6d  jz      short loc_18001CCB2
0x18001cc6f  test    [rcx+1Ch], bl
0x18001cc72  jz      short loc_18001CCB2
0x18001cc74  mov     rax, [rdi+8]
0x18001cc78  mov     [rsp+3F8h+var_3B0], rax; __int64
0x18001cc7d  mov     rax, [rdi]
0x18001cc80  mov     [rsp+3F8h+var_3B8], rax; __int64
0x18001cc85  mov     dword ptr [rsp+3F8h+var_3C0], r8d; char
0x18001cc8a  mov     rax, [rdi+18h]
0x18001cc8e  mov     qword ptr [rsp+3F8h+var_3C8], rax; char
0x18001cc93  mov     rax, [rdi+30h]
0x18001cc97  mov     qword ptr [rsp+3F8h+var_3D0], rax; char
0x18001cc9c  mov     rax, [rdi+28h]
0x18001cca0  mov     qword ptr [rsp+3F8h+bIgnoreCase], rax; char
0x18001cca5  mov     r9, [rdi+20h]
0x18001cca9  mov     rcx, [rcx+10h]; LoggerHandle
0x18001ccad  call    WPP_SF_iiiiDSS
0x18001ccb2  mov     r12d, 1
0x18001ccb8  mov     [rsp+3F8h+bIgnoreCase], r12d; bIgnoreCase
0x18001ccbd  mov     r9d, esi; cchCount2
0x18001ccc0  mov     r8, [r14+8]; lpString2
0x18001ccc4  mov     edx, esi; cchCount1
0x18001ccc6  mov     rcx, [r14]; lpString1
0x18001ccc9  call    cs:__imp_CompareStringOrdinal
0x18001cccf  mov     rdx, [rsp+3F8h+var_388]
0x18001ccd4  cmp     eax, 2
0x18001ccd7  jnz     loc_18001CDA4
0x18001ccdd  cmp     [rdx], ebx
0x18001ccdf  jnz     short loc_18001CD17
0x18001cce1  mov     r14d, r15d
0x18001cce4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cceb  cmp     rcx, r13
0x18001ccee  jz      loc_18001EA8A
0x18001ccf4  test    [rcx+1Ch], bl
0x18001ccf7  jz      loc_18001EA8A
0x18001ccfd  mov     edx, 0DAh
0x18001cd02  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001cd09  mov     rcx, [rcx+10h]
0x18001cd0d  call    WPP_SF_
0x18001cd12  jmp     loc_18001EA8A
0x18001cd17  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd1e  cmp     rcx, r13
0x18001cd21  jz      short loc_18001CD42
0x18001cd23  test    [rcx+1Ch], bl
0x18001cd26  jz      short loc_18001CD42
0x18001cd28  mov     edx, 0DBh
0x18001cd2d  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001cd34  mov     rcx, [rcx+10h]
0x18001cd38  call    WPP_SF_
0x18001cd3d  mov     rdx, [rsp+3F8h+var_388]
0x18001cd42  and     dword ptr [rdx], 0FFFFFFF7h
0x18001cd45  jmp     short loc_18001CDA4
0x18001cd47  lea     r13, WPP_GLOBAL_Control
0x18001cd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd55  cmp     rcx, r13
0x18001cd58  jz      short loc_18001CD9E
0x18001cd5a  test    [rcx+1Ch], bl
0x18001cd5d  jz      short loc_18001CD9E
0x18001cd5f  mov     edx, 0DCh
0x18001cd64  mov     rax, [r14]
0x18001cd67  mov     [rsp+3F8h+var_3B8], rax
0x18001cd6c  mov     dword ptr [rsp+3F8h+var_3C0], r8d
0x18001cd71  mov     rax, [r14+18h]
0x18001cd75  mov     qword ptr [rsp+3F8h+var_3C8], rax
0x18001cd7a  mov     rax, [r14+30h]
0x18001cd7e  mov     qword ptr [rsp+3F8h+var_3D0], rax
0x18001cd83  mov     rax, [r14+28h]
0x18001cd87  mov     qword ptr [rsp+3F8h+bIgnoreCase], rax
0x18001cd8c  mov     r9, [r14+20h]
0x18001cd90  mov     rcx, [rcx+10h]
0x18001cd94  call    WPP_SF_iiiiDS
0x18001cd99  mov     rdx, [rsp+3F8h+var_388]; unsigned __int16 *
0x18001cd9e  mov     r12d, 1
0x18001cda4  lea     rsi, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001cdab  mov     [rsp+3F8h+var_2D8], rdx
0x18001cdb3  mov     [rsp+3F8h+var_34C], r15d
0x18001cdbb  mov     eax, r15d
0x18001cdbe  mov     [rsp+3F8h+var_3A0], eax
0x18001cdc2  mov     [rsp+3F8h+var_350], eax
0x18001cdc9  mov     [rsp+3F8h+var_360], r15d
0x18001cdd1  mov     eax, [rdx]
0x18001cdd3  lea     r8, [r14+8]
0x18001cdd7  mov     [rsp+3F8h+var_320], r8
0x18001cddf  mov     [rsp+3F8h+RandomBuffer], r8
0x18001cde4  test    bl, al
0x18001cde6  jz      short loc_18001CDED
0x18001cde8  mov     rcx, [r8]
0x18001cdeb  jmp     short loc_18001CDF0
0x18001cded  mov     rcx, [r14]
0x18001cdf0  mov     [rsp+3F8h+lpFileName], rcx
0x18001cdf5  and     eax, r12d
0x18001cdf8  mov     rcx, [rsp+3F8h+var_398]
0x18001cdfd  add     [rcx+34Ch], eax
0x18001ce03  mov     eax, [rdx]
0x18001ce05  shr     eax, 1
0x18001ce07  and     eax, r12d
0x18001ce0a  add     [rcx+350h], eax
0x18001ce10  mov     eax, [rdx]
0x18001ce12  shr     eax, 3
0x18001ce15  and     eax, r12d
0x18001ce18  add     [rcx+354h], eax
0x18001ce1e  mov     eax, [rdx]
0x18001ce20  shr     eax, 2
0x18001ce23  and     eax, r12d
0x18001ce26  add     [rcx+358h], eax
0x18001ce2c  mov     eax, [r14+38h]
0x18001ce30  shr     eax, 0Eh
0x18001ce33  and     eax, r12d
0x18001ce36  add     [rcx+35Ch], eax
0x18001ce3c  add     [rcx+360h], r12d
0x18001ce43  test    [rdx], bl
0x18001ce45  jz      short loc_18001CEA9
0x18001ce47  mov     rcx, [r8]; lpString
0x18001ce4a  call    ?IsSourcePathSupported@FhePathOperations@@YAHPEBG@Z; FhePathOperations::IsSourcePathSupported(ushort const *)
0x18001ce4f  test    eax, eax
0x18001ce51  jnz     loc_18001CF0D
0x18001ce57  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce5e  cmp     rcx, r13
0x18001ce61  jz      short loc_18001CE7A
0x18001ce63  test    byte ptr [rcx+1Ch], 2
0x18001ce67  jz      short loc_18001CE7A
0x18001ce69  mov     edx, 0DDh
0x18001ce6e  mov     r8, rsi
0x18001ce71  mov     rcx, [rcx+10h]
0x18001ce75  call    WPP_SF_
0x18001ce7a  test    cs:Microsoft_Windows_FileHistory_EngineEnableBits, 2
0x18001ce81  jz      short loc_18001CE9A
0x18001ce83  mov     r8, [rsp+3F8h+var_320]
0x18001ce8b  mov     r8, [r8]
0x18001ce8e  lea     rdx, FileFailure_NameNotSupported
0x18001ce95  call    McTemplateU0z_EventWriteTransfer
0x18001ce9a  mov     eax, 4
0x18001ce9f  mov     r14, [rsp+3F8h+var_388]
0x18001cea4  mov     [r14], eax
0x18001cea7  jmp     short loc_18001CF17
0x18001cea9  mov     rcx, [r14]; lpString
0x18001ceac  call    ?IsSourcePathSupported@FhePathOperations@@YAHPEBG@Z; FhePathOperations::IsSourcePathSupported(ushort const *)
0x18001ceb1  test    eax, eax
0x18001ceb3  jnz     short loc_18001CF0D
0x18001ceb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cebc  cmp     rcx, r13
0x18001cebf  jz      short loc_18001CED8
0x18001cec1  test    byte ptr [rcx+1Ch], 2
0x18001cec5  jz      short loc_18001CED8
0x18001cec7  mov     edx, 0DEh
0x18001cecc  mov     r8, rsi
0x18001cecf  mov     rcx, [rcx+10h]
0x18001ced3  call    WPP_SF_
0x18001ced8  test    cs:Microsoft_Windows_FileHistory_EngineEnableBits, 2
0x18001cedf  jz      short loc_18001CEF0
0x18001cee1  mov     r8, [r14]
0x18001cee4  lea     rdx, FileFailure_NameNotSupported
0x18001ceeb  call    McTemplateU0z_EventWriteTransfer
0x18001cef0  mov     eax, 4
0x18001cef5  mov     r14, [rsp+3F8h+var_388]
0x18001cefa  mov     [r14], eax
0x18001cefd  cmp     [rdi+28h], r15
0x18001cf01  jnz     short loc_18001CF17
0x18001cf03  mov     rax, [rdi+18h]
0x18001cf07  mov     [rdi+28h], rax
0x18001cf0b  jmp     short loc_18001CF12
0x18001cf0d  mov     r14, [rsp+3F8h+var_388]
0x18001cf12  mov     eax, 4
0x18001cf17  test    byte ptr [r14], 0Bh
0x18001cf1b  setnz   cl
0x18001cf1e  test    [r14], al
0x18001cf21  setz    al
0x18001cf24  test    al, cl
0x18001cf26  jz      short loc_18001CF5B
0x18001cf28  lea     r8, [rsp+3F8h+FileInformation]; lpFileInformation
0x18001cf30  xor     edx, edx; fInfoLevelId
0x18001cf32  mov     rcx, [rsp+3F8h+lpFileName]; lpFileName
0x18001cf37  call    cs:__imp_GetFileAttributesExW
0x18001cf3d  mov     [rsp+3F8h+var_34C], eax
0x18001cf44  test    eax, eax
0x18001cf46  jnz     loc_18001CFD3
0x18001cf4c  call    cs:__imp_GetLastError
0x18001cf52  cmp     eax, 5
0x18001cf55  jz      loc_18001CFEE
0x18001cf5b  mov     rbx, [rsp+3F8h+var_388]
0x18001cf60  mov     eax, [rsp+3F8h+var_34C]
0x18001cf67  neg     eax
0x18001cf69  sbb     r8, r8
0x18001cf6c  lea     rax, [rsp+3F8h+FileInformation]
0x18001cf74  and     r8, rax; struct _WIN32_FILE_ATTRIBUTE_DATA *
0x18001cf77  lea     rax, [rsp+3F8h+var_328]
0x18001cf7f  mov     qword ptr [rsp+3F8h+bIgnoreCase], rax; RandomBuffer
0x18001cf84  lea     r9, [rsp+3F8h+var_300]; __int64 *
0x18001cf8c  mov     rdx, rdi; struct _DPEL_EVENT *
0x18001cf8f  mov     rcx, [rsp+3F8h+var_398]; this
0x18001cf94  call    ?GetPreviousVersionStats@CBackupSession@@AEAAJPEAU_DPEL_EVENT@@PEAU_WIN32_FILE_ATTRIBUTE_DATA@@AEA_JAEAH@Z; CBackupSession::GetPreviousVersionStats(_DPEL_EVENT *,_WIN32_FILE_ATTRIBUTE_DATA *,__int64 &,int &)
0x18001cf99  mov     r14d, eax
0x18001cf9c  test    eax, eax
0x18001cf9e  jns     loc_18001D1FF
0x18001cfa4  mov     r10, cs:WPP_GLOBAL_Control
0x18001cfab  cmp     r10, r13
0x18001cfae  jz      loc_18001EA8A
0x18001cfb4  test    [r10+1Ch], r12b
0x18001cfb8  jz      loc_18001E9A4
0x18001cfbe  mov     edx, 0E4h
0x18001cfc3  mov     rbx, [rsp+3F8h+var_370]
0x18001cfcb  mov     r9, [rbx]
0x18001cfce  jmp     loc_18001E98D
0x18001cfd3  mov     eax, dword ptr [rsp+3F8h+FileInformation]
0x18001cfda  bt      eax, 0Eh
0x18001cfde  jnb     short loc_18001D05A
0x18001cfe0  mov     rcx, [rsp+3F8h+var_398]
0x18001cfe5  cmp     [rcx+170h], r15d
0x18001cfec  jnz     short loc_18001D05A
0x18001cfee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cff5  cmp     rcx, r13
0x18001cff8  jz      short loc_18001D011
0x18001cffa  test    byte ptr [rcx+1Ch], 2
0x18001cffe  jz      short loc_18001D011
0x18001d000  mov     edx, 0DFh
0x18001d005  mov     r8, rsi
0x18001d008  mov     rcx, [rcx+10h]
0x18001d00c  call    WPP_SF_
0x18001d011  mov     rdx, [rsp+3F8h+lpFileName]
0x18001d016  lea     rcx, [rsp+3F8h+var_368]
0x18001d01e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001d023  mov     rdx, rax
0x18001d026  mov     rcx, [rsp+3F8h+var_398]
0x18001d02b  call    ?LogFilePermissionFailure@CBackupSession@@AEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CBackupSession::LogFilePermissionFailure(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18001d030  mov     dword ptr [r14], 4
0x18001d037  cmp     [rdi+28h], r15
0x18001d03b  jnz     short loc_18001D045
0x18001d03d  mov     rax, [rdi+18h]
0x18001d041  mov     [rdi+28h], rax
0x18001d045  cmp     [rsp+3F8h+var_34C], r15d
0x18001d04d  jz      loc_18001CF5B
0x18001d053  mov     eax, dword ptr [rsp+3F8h+FileInformation]
0x18001d05a  bt      eax, 0Ah
0x18001d05e  jnb     loc_18001CF5B
0x18001d064  mov     r14b, r12b
0x18001d067  mov     [rsp+3F8h+ppszPath], r15
0x18001d06f  lea     r9, [rsp+3F8h+ppszPath]; ppszPath
0x18001d077  xor     r8d, r8d; hToken
0x18001d07a  mov     edx, 4000h; dwFlags
0x18001d07f  lea     rcx, FOLDERID_SkyDrive; rfid
0x18001d086  call    cs:__imp_SHGetKnownFolderPath
0x18001d08c  test    eax, eax
0x18001d08e  jns     loc_18001D11B
0x18001d094  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d09b  cmp     rcx, r13
0x18001d09e  jz      short loc_18001D0B7
0x18001d0a0  test    [rcx+1Ch], r12b
0x18001d0a4  jz      short loc_18001D0B7
0x18001d0a6  mov     edx, 0E0h
  ... truncated ...
```
