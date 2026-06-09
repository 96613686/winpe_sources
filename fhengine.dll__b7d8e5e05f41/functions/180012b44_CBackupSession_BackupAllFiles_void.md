# CBackupSession::BackupAllFiles(void)

- ea: `0x180012b44`
- end: `0x180013e0d`
- name: `?BackupAllFiles@CBackupSession@@AEAAJXZ`
- size: `4809`
- prototype: `__int64 __fastcall(CBackupSession *__hidden this)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021240`

## callees

- `0x1800025b0`
- `0x180002c24`
- `0x1800062d0`
- `0x1800077f0`
- `0x180007818`
- `0x180007970`
- `0x1800079c0`
- `0x180007a9c`
- `0x180007ab8`
- `0x180007ae4`
- `0x18000815c`
- `0x180008484`
- `0x18000850c`
- `0x180008ac8`
- `0x180008d18`
- `0x180009258`
- `0x1800092d0`
- `0x18000935c`
- `0x1800093a8`
- `0x180009404`
- `0x1800094d0`
- `0x180009560`
- `0x180009a80`
- `0x180009d70`
- `0x18000c450`
- `0x180010de8`
- `0x1800126f0`
- `0x1800127b0`
- `0x180012b44`
- `0x180013e14`
- `0x180016aec`
- `0x18001a4a8`
- `0x18001a6b0`
- `0x18002204c`
- `0x18002247c`
- `0x18002259c`
- `0x1800309ac`
- `0x180030b88`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180012dd4`
- `ADVAPI32!RegGetValueW` at `0x180012dd4`
- `ADVAPI32!SetThreadToken` at `0x180012b94`
- `ADVAPI32!SetThreadToken` at `0x180013d92`
- `ADVAPI32!SetThreadToken` at `0x180012b94`
- `ADVAPI32!SetThreadToken` at `0x180013d92`
- `KERNEL32!GetLastError` at `0x180012bab`
- `KERNEL32!GetLastError` at `0x180013091`
- `KERNEL32!GetLastError` at `0x1800130cc`
- `KERNEL32!GetLastError` at `0x1800134dc`
- `KERNEL32!GetLastError` at `0x1800134eb`
- `KERNEL32!GetLastError` at `0x180013513`
- `KERNEL32!GetLastError` at `0x180013dae`
- `KERNEL32!GetLastError` at `0x180012bab`
- `KERNEL32!GetLastError` at `0x180013091`
- `KERNEL32!GetLastError` at `0x1800130cc`
- `KERNEL32!GetLastError` at `0x1800134dc`
- `KERNEL32!GetLastError` at `0x1800134eb`
- `KERNEL32!GetLastError` at `0x180013513`
- `KERNEL32!GetLastError` at `0x180013dae`
- `KERNEL32!GetFileAttributesExW` at `0x180013071`
- `KERNEL32!GetFileAttributesExW` at `0x1800134bc`
- `KERNEL32!GetFileAttributesExW` at `0x180013071`
- `KERNEL32!GetFileAttributesExW` at `0x1800134bc`
- `KERNEL32!GetFileAttributesW` at `0x180012cbe`
- `KERNEL32!GetFileAttributesW` at `0x180012cbe`

## string_xrefs

- `0x180013bc6`: `PerformDirectoryTreeOperation has failed`
- `0x18001355f`: `Unable to obtain the size of the current file copy`

## pseudocode

```c
__int64 __fastcall CBackupSession::BackupAllFiles(CBackupSession *this)
{
  int v2; // r13d
  signed int LastError; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  signed int v6; // esi
  CFileRecord *v7; // rax
  CFileRecord *v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // rax
  int v11; // eax
  ATL::CStringData *v12; // rcx
  FheFileOperations *v13; // rbx
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v15; // rdx
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  PVOID *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r8
  int v22; // r15d
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // r9
  int CurrentRecord; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // ebx
  signed __int64 v31; // r12
  int v32; // eax
  __int64 v33; // rax
  bool v34; // zf
  int Name; // eax
  LPCWSTR v36; // rbx
  signed int v37; // eax
  CBackupSession *v38; // rcx
  char v39; // al
  int v40; // ecx
  BOOL v41; // eax
  int v42; // eax
  int v43; // eax
  CFileRecord *v44; // rbx
  int v45; // r8d
  unsigned __int64 v46; // r15
  char *v47; // rcx
  __int64 v48; // r8
  int v49; // eax
  _QWORD *v50; // rcx
  __int64 v51; // rdx
  LPCWSTR v52; // rcx
  LPCWSTR v53; // rbx
  PVOID *v54; // rcx
  char v55; // al
  unsigned __int64 v56; // rdx
  int v57; // ecx
  BOOL v58; // eax
  int v59; // r15d
  int v60; // eax
  int v61; // r8d
  int v62; // eax
  PVOID *v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // r9
  ATL::CStringData *v67; // rcx
  _QWORD *v68; // rcx
  __int64 v69; // rdx
  __int64 v70; // r9
  int v71; // eax
  int v72; // ecx
  unsigned int v73; // ebx
  PVOID *v74; // rcx
  __int64 v75; // rcx
  signed int v76; // eax
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  int pvData; // [rsp+28h] [rbp-D8h]
  int v80; // [rsp+60h] [rbp-A0h]
  BOOL v81; // [rsp+64h] [rbp-9Ch]
  int v82; // [rsp+68h] [rbp-98h]
  int v83; // [rsp+6Ch] [rbp-94h]
  LPCWSTR lpFileName; // [rsp+70h] [rbp-90h] BYREF
  int v85[2]; // [rsp+78h] [rbp-88h] BYREF
  int v86; // [rsp+80h] [rbp-80h] BYREF
  int v87; // [rsp+84h] [rbp-7Ch]
  DWORD pcbData; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v89; // [rsp+90h] [rbp-70h] BYREF
  CFileRecord *v90; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v91; // [rsp+A0h] [rbp-60h] BYREF
  CFileRecord *v92; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v93[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v94[40]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v95; // [rsp+E8h] [rbp-18h]
  int v96; // [rsp+F8h] [rbp-8h]
  _BYTE v97[40]; // [rsp+110h] [rbp+10h] BYREF
  __int16 v98; // [rsp+138h] [rbp+38h]
  int v99; // [rsp+148h] [rbp+48h]
  __int128 FileInformation; // [rsp+160h] [rbp+60h] BYREF
  __int128 v101; // [rsp+170h] [rbp+70h]
  unsigned int v102; // [rsp+180h] [rbp+80h]
  _QWORD v103[2]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v104[16]; // [rsp+198h] [rbp+98h] BYREF
  _QWORD *v105; // [rsp+1A8h] [rbp+A8h]
  __int64 v106; // [rsp+1B0h] [rbp+B0h]
  _QWORD *v107; // [rsp+1B8h] [rbp+B8h]
  __int64 v108; // [rsp+1C0h] [rbp+C0h]

  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v92);
  v86 = 0;
  pcbData = 4;
  v2 = 1;
  if ( !SetThreadToken(0, *((HANDLE *)this + 48)) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)v6);
      goto LABEL_262;
    }
    goto LABEL_271;
  }
  v7 = (CFileRecord *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
    v7 = (CFileRecord *)CFileRecord::CFileRecord(v7);
  SmartPtr<CFileRecord>::operator=(&v92, v7);
  v8 = v92;
  if ( v92 && *(_QWORD *)v92 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
    v9 = *((_DWORD *)this + 11);
    v10 = SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(v103);
    v11 = CSessionBaseRO::ConstructStagingPath((char *)this + 16, v10, v9, &lpFileName);
    v6 = v11;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          144,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          *((unsigned int *)this + 11),
          v11);
      v12 = (ATL::CStringData *)(lpFileName - 12);
      goto LABEL_16;
    }
    v13 = (FheFileOperations *)lpFileName;
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW != -1 )
    {
      if ( (FileAttributesW & 0x10) != 0 )
      {
        v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                v103,
                &lpFileName);
        v18 = FheFileOperations::PerformDirectoryTreeOperation(v17, v16, 1, (int)this + 160, 0, 0, 0);
      }
      else
      {
        v18 = FheFileOperations::DeleteReadOnlyFile(v13, v15);
      }
      v6 = v18;
      if ( v18 == -2147023661 )
      {
        v12 = (FheFileOperations *)((char *)v13 - 24);
LABEL_16:
        ATL::CStringData::Release(v12);
        goto LABEL_262;
      }
      if ( v18 < 0 )
      {
        v19 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              145,
              &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
              *((unsigned int *)this + 11),
              v18);
            v19 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 )
            WPP_SF_ss(
              (unsigned int)v19[2],
              146,
              (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
              (unsigned int)"FALSE",
              (__int64)"Staging area cleanup should not fail or disk space is wasted");
        }
      }
    }
    ATL::CStringData::Release((FheFileOperations *)((char *)v13 - 24));
    if ( RegGetValueW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
           L"RestoreAllowed",
           0x10u,
           0,
           &v86,
           &pcbData)
      || pcbData != 4 )
    {
      v86 = 0;
    }
    if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v20, BackupAllFilesStart, v21, 1, v103);
    v22 = 0;
    v23 = 4;
    v87 = 4;
LABEL_36:
    v80 = v22;
    v24 = *((_QWORD *)this + 3);
    if ( v22 >= v23 )
    {
      v103[0] = *((_QWORD *)this + 3);
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      CMultistateFileRecordQuery::CMultistateFileRecordQuery(v104, v103);
      LODWORD(pdwType) = 3;
      if ( (unsigned int)CMultistateFileRecordQuery::Query(v104, 0, 3, 2, pdwType, 5) == -2147023728 )
      {
        v71 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                v103,
                (char *)this + 64);
        v73 = FheFileOperations::PerformDirectoryTreeOperation(v72, v71, 0, (int)this + 160, 0, 0, 0);
        if ( (int)(v73 + 0x80000000) >= 0 && v73 != -2147023661 )
        {
          v74 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_ss(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                169,
                (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                (unsigned int)"FALSE",
                (__int64)"PerformDirectoryTreeOperation has failed");
              v74 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v74 != &WPP_GLOBAL_Control && (*((_BYTE *)v74 + 28) & 1) != 0 )
              WPP_SF_d(v74[2], 170, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v73);
          }
        }
      }
      v6 = 0;
      CMultistateFileRecordQuery::~CMultistateFileRecordQuery((CMultistateFileRecordQuery *)v104);
      if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
      {
        v93[0] = *((_DWORD *)this + 222) + *((_DWORD *)this + 223);
        v103[0] = *((_QWORD *)this + 52);
        v105 = v103;
        v106 = 8;
        v107 = v93;
        v108 = 8;
        McGenEventWrite_EventWriteTransfer(v75, BackupAllFilesStop, v5, 3, v104);
      }
      goto LABEL_262;
    }
    v89 = *((_QWORD *)this + 3);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
    CMultistateFileRecordQuery::CMultistateFileRecordQuery(v104, &v89);
    if ( v22 )
    {
      if ( v22 == 1 )
      {
        LODWORD(pdwType) = 2;
        v25 = CMultistateFileRecordQuery::Query(v104, 0, 2, 1, pdwType, pvData);
LABEL_52:
        v6 = v25;
        if ( v25 == -2147023728 )
          goto LABEL_204;
        v89 = -1;
        v83 = 0;
        v82 = 0;
        if ( v25 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              148,
              &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
              (unsigned int)v22,
              v25);
          goto LABEL_245;
        }
        while ( 1 )
        {
          if ( *((_DWORD *)this + 40) )
          {
            v63 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v65 = 149;
LABEL_208:
              WPP_SF_(v63[2], v65, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
              v63 = (PVOID *)WPP_GLOBAL_Control;
            }
LABEL_209:
            v87 = 0;
LABEL_210:
            CurrentRecord = 0;
            if ( v6 != -2147023728 )
              CurrentRecord = v6;
            v6 = CurrentRecord;
            if ( CurrentRecord < 0 )
            {
              if ( v63 != &WPP_GLOBAL_Control && (*((_BYTE *)v63 + 28) & 1) != 0 )
              {
                v64 = 167;
                goto LABEL_240;
              }
              goto LABEL_245;
            }
LABEL_199:
            if ( v82 > 0 && v63 != &WPP_GLOBAL_Control && (*((_BYTE *)v63 + 28) & 8) != 0 )
              WPP_SF_dd(v63[2], 168, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, (unsigned int)v82, v83);
            v2 = 1;
            v22 = v80;
LABEL_204:
            CMultistateFileRecordQuery::~CMultistateFileRecordQuery((CMultistateFileRecordQuery *)v104);
            ++v22;
            v23 = v87;
            goto LABEL_36;
          }
          if ( !*((_DWORD *)this + 39) && v22 < 3 )
          {
            v63 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
              v63 = (PVOID *)WPP_GLOBAL_Control;
            }
            v80 = 2;
            goto LABEL_210;
          }
          *(_QWORD *)v85 = v8;
          if ( v8 )
            ++*((_DWORD *)v8 + 2);
          CurrentRecord = CMultistateFileRecordQuery::LoadCurrentRecord(v104, v85);
          v6 = CurrentRecord;
          if ( CurrentRecord == -2147023728 )
          {
LABEL_188:
            v63 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_210;
          }
          if ( CurrentRecord < 0 )
          {
            v63 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v64 = 151;
LABEL_240:
              v66 = (unsigned int)CurrentRecord;
LABEL_241:
              WPP_SF_d(v63[2], v64, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v66);
            }
LABEL_245:
            CMultistateFileRecordQuery::~CMultistateFileRecordQuery((CMultistateFileRecordQuery *)v104);
LABEL_262:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  171,
                  &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  *((unsigned int *)this + 223),
                  *((_DWORD *)this + 222));
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_ii(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    172,
                    &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                    *((_QWORD *)this + 110),
                    *((_QWORD *)this + 109));
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_iiii(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v4,
                    v5,
                    *((_QWORD *)this + 22),
                    *((_QWORD *)this + 27),
                    *((_QWORD *)this + 23),
                    *((_QWORD *)this + 13));
              }
            }
            goto LABEL_271;
          }
          v30 = 0;
          v85[0] = 0;
          v81 = 0;
          v31 = 0;
          if ( v22 == 3 )
            break;
          v2 = 0;
          if ( !v22 )
            goto LABEL_104;
          v2 = 1;
          if ( (unsigned int)(v22 - 1) > 1 )
            goto LABEL_66;
          v32 = 1;
LABEL_68:
          *((_DWORD *)this + 118) = v32;
          v34 = v32 == 0;
          v33 = *(_QWORD *)v8;
          if ( v34 )
            v34 = (*(_BYTE *)(v33 + 42) & 0x10) == 0;
          else
            v34 = (*(_BYTE *)(v33 + 42) & 8) == 0;
          if ( v34 )
            v2 = 0;
          *((_QWORD *)this + 57) = 0x7FFFFFFFFFFFFFFFLL;
          CBackupSession::CalculateTransferQuotas(this, v2 ^ 1);
          if ( *((_DWORD *)this + 110) )
          {
            v63 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v65 = 152;
              goto LABEL_208;
            }
            goto LABEL_209;
          }
          if ( (*(_BYTE *)(*(_QWORD *)v8 + 42LL) & 0x20) != 0 || (v31 = *(_QWORD *)(*(_QWORD *)v8 + 48LL), v31 < 0) )
          {
            FileInformation = 0;
            v101 = 0;
            v102 = 0;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v91);
            Name = CFileRecord::GetName(*(_QWORD *)v8, &v91);
            v6 = Name;
            if ( Name < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  153,
                  &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  *(unsigned int *)(*(_QWORD *)v8 + 16LL),
                  Name);
              v52 = v91;
              goto LABEL_224;
            }
            v36 = v91;
            if ( GetFileAttributesExW(v91, GetFileExInfoStandard, &FileInformation) )
            {
              v31 = v102 + ((unsigned __int64)HIDWORD(v101) << 32);
            }
            else
            {
              v37 = GetLastError();
              if ( v37 > 0 )
                v37 = (unsigned __int16)v37 | 0x80070000;
              if ( (unsigned int)CBackupSession::IsFailurePermanent(v38, v37) )
              {
                v31 = 0;
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v39 = GetLastError();
                  WPP_SF_Sdd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    154,
                    (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                    (_DWORD)v36,
                    v80,
                    v39);
                }
                v31 = -1;
                v85[0] = 1;
              }
            }
            ATL::CStringData::Release((ATL::CStringData *)(v36 - 12));
            v30 = v85[0];
            if ( v31 < 0 )
              goto LABEL_91;
          }
          if ( v89 == -1 || (v28 = (v89 * (unsigned __int128)0x47AE147AE147AE15uLL) >> 64, v31 < 99 * (v89 / 0x64)) )
          {
LABEL_91:
            if ( v30 )
              goto LABEL_111;
            if ( v31 >= 0 && v31 > *((_QWORD *)this + 57) )
            {
              if ( *((_DWORD *)this + 118) )
              {
                v6 = CSessionBaseRW::RetireFileVersionsOnTarget(
                       (CBackupSession *)((char *)this + 8),
                       v31,
                       *((_QWORD *)this + 60),
                       *((_DWORD *)this + 58),
                       *((_DWORD *)this + 50),
                       0,
                       0,
                       (int *)this + 269,
                       (int *)this + 270,
                       (int *)this + 268,
                       (__int64 *)this + 136,
                       0);
                *((_DWORD *)this + 89) |= v6 == -2147024784;
                *((_DWORD *)this + 90) |= CBackupSession::IsChkDskRequired((CBackupSession *)0x80070070LL, v6);
                v41 = v6 == v40 && *((_DWORD *)this + 48) == *((_DWORD *)this + 50);
                *((_DWORD *)this + 94) |= v41;
                if ( v6 != v40 && v6 != -2147023661 )
                {
                  if ( v6 < 0 )
                  {
                    v63 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v64 = 155;
LABEL_219:
                    v66 = (unsigned int)v6;
                    goto LABEL_241;
                  }
                  CBackupSession::CalculateTransferQuotas(this, v2 ^ 1);
                  v81 = 0;
                  goto LABEL_103;
                }
              }
              else
              {
                *((_DWORD *)this + 88) |= *((_DWORD *)this + 39) == 0;
                v6 = -2147024784;
              }
              v81 = v6 == -2147024784;
LABEL_111:
              v2 = 1;
              goto LABEL_112;
            }
LABEL_103:
            v22 = v80;
LABEL_104:
            CFileRecord::CFileRecord((CFileRecord *)v94);
            v42 = CFileRecord::LoadFromCatalog((CFileRecord *)v94, *(_DWORD *)(*(_QWORD *)v8 + 16LL));
            if ( v42 >= 0 )
            {
              if ( v95 != *(_WORD *)(*(_QWORD *)v8 + 40LL) || v96 != *(_DWORD *)(*(_QWORD *)v8 + 56LL) )
                goto LABEL_115;
            }
            else
            {
              if ( v42 != -2147023728
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  156,
                  &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  "SUCCEEDED(hr) || (hr == HRESULT_FROM_WIN32(ERROR_NOT_FOUND))");
              }
LABEL_115:
              v30 = 1;
              v85[0] = 1;
            }
            CFileRecord::~CFileRecord((CFileRecord *)v94);
            if ( !v30 )
            {
              if ( v82 > 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    157,
                    &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                    (unsigned int)v82,
                    v83);
                v83 = 0;
                v82 = 0;
              }
              v90 = v8;
              if ( v22 )
              {
                v45 = *((_DWORD *)this + 118);
                v44 = v8;
                ++*((_DWORD *)v8 + 2);
                v43 = CBackupSession::BackupSingleFile((__int64)this, &v90, v45, 0);
              }
              else
              {
                ++*((_DWORD *)v8 + 2);
                v43 = CSessionBaseRW::CleanupFileRecord((char *)this + 8, &v90, 0, 1);
                v44 = v8;
              }
              v6 = v43;
              if ( v43 == -2147023661 )
                goto LABEL_181;
              if ( !v22 || v43 != -2147024784 )
              {
                if ( v43 < 0 )
                {
                  v63 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_245;
                  v64 = 165;
                  goto LABEL_219;
                }
LABEL_181:
                v2 = 1;
                goto LABEL_182;
              }
              FileInformation = 0;
              v101 = 0;
              v102 = 0;
              v46 = 0;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
              if ( v2 )
              {
                v47 = (char *)this + 16;
                v48 = *(unsigned int *)(*(_QWORD *)v8 + 60LL);
                if ( *((_DWORD *)this + 118) )
                {
                  v93[0] = v8;
                  ++*((_DWORD *)v44 + 2);
                  v49 = CSessionBaseRO::ConstructTargetPath(
                          (_DWORD)v47,
                          (unsigned int)v93,
                          v48,
                          (unsigned int)&lpFileName,
                          0);
                  v6 = v49;
                  if ( v49 < 0 )
                  {
                    v50 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v51 = 158;
                      goto LABEL_134;
                    }
                    goto LABEL_135;
                  }
                }
                else
                {
                  v103[0] = v8;
                  ++*((_DWORD *)v44 + 2);
                  v49 = CSessionBaseRO::ConstructStagingPath(v47, v103, v48, &lpFileName);
                  v6 = v49;
                  if ( v49 < 0 )
                  {
                    v50 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v51 = 159;
LABEL_134:
                      WPP_SF_dd(
                        v50[2],
                        v51,
                        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                        *(unsigned int *)(*(_QWORD *)v8 + 16LL),
                        v49);
                    }
LABEL_135:
                    v52 = lpFileName;
LABEL_224:
                    v67 = (ATL::CStringData *)(v52 - 12);
                    goto LABEL_225;
                  }
                }
                v53 = lpFileName;
                if ( GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
                {
                  v46 = v102 + ((unsigned __int64)HIDWORD(v101) << 32);
                }
                else if ( GetLastError() != 3 && GetLastError() != 2 )
                {
                  v54 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v55 = GetLastError();
                      WPP_SF_Sd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        160,
                        (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                        (_DWORD)v53,
                        v55);
                      v54 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( v54 != &WPP_GLOBAL_Control && (*((_BYTE *)v54 + 28) & 4) != 0 )
                      WPP_SF_ss(
                        (unsigned int)v54[2],
                        161,
                        (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                        (unsigned int)"FALSE",
                        (__int64)"Unable to obtain the size of the current file copy");
                  }
                }
              }
              else
              {
                v53 = lpFileName;
              }
              if ( v46 >= v31 )
                v56 = 0;
              else
                v56 = v31 - v46;
              v2 = 1;
              if ( *((_DWORD *)this + 118) )
              {
                v6 = CSessionBaseRW::RetireFileVersionsOnTarget(
                       (CBackupSession *)((char *)this + 8),
                       v56,
                       *((_QWORD *)this + 60),
                       *((_DWORD *)this + 58),
                       *((_DWORD *)this + 50),
                       1,
                       0,
                       (int *)this + 269,
                       (int *)this + 270,
                       (int *)this + 268,
                       (__int64 *)this + 136,
                       0);
                *((_DWORD *)this + 89) |= v6 == -2147024784;
                *((_DWORD *)this + 90) |= CBackupSession::IsChkDskRequired((CBackupSession *)0x80070070LL, v6);
                v58 = v6 == v57 && *((_DWORD *)this + 48) == *((_DWORD *)this + 50);
                *((_DWORD *)this + 94) |= v58;
                if ( v6 != v57 && v6 != -2147023661 )
                {
                  if ( v6 < 0 )
                  {
                    v68 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v69 = 162;
                      v70 = (unsigned int)v6;
                      goto LABEL_232;
                    }
LABEL_233:
                    v67 = (ATL::CStringData *)(v53 - 12);
LABEL_225:
                    ATL::CStringData::Release(v67);
                    goto LABEL_245;
                  }
                  v59 = v85[0];
LABEL_162:
                  if ( !v59 )
                  {
                    CFileRecord::CFileRecord((CFileRecord *)v97);
                    v60 = CFileRecord::LoadFromCatalog((CFileRecord *)v97, *(_DWORD *)(*(_QWORD *)v8 + 16LL));
                    if ( v60 >= 0 )
                    {
                      if ( v98 != *(_WORD *)(*(_QWORD *)v8 + 40LL) || v99 != *(_DWORD *)(*(_QWORD *)v8 + 56LL) )
                        goto LABEL_170;
                    }
                    else
                    {
                      if ( v60 != -2147023728
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                      {
                        WPP_SF_s(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          163,
                          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                          "SUCCEEDED(hr) || (hr == HRESULT_FROM_WIN32(ERROR_NOT_FOUND))");
                      }
LABEL_170:
                      v59 = 1;
                    }
                    CFileRecord::~CFileRecord((CFileRecord *)v97);
                    if ( !v59 )
                    {
                      CBackupSession::CalculateTransferQuotas(this, 0);
                      v61 = *((_DWORD *)this + 118);
                      v90 = v8;
                      ++*((_DWORD *)v8 + 2);
                      v62 = CBackupSession::BackupSingleFile((__int64)this, &v90, v61, 1);
                      v6 = v62;
                      if ( v62 != -2147024784 && v62 != -2147023661 && v62 < 0 )
                      {
                        v68 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        {
                          v69 = 164;
                          v70 = (unsigned int)v62;
LABEL_232:
                          WPP_SF_d(v68[2], v69, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v70);
                        }
                        goto LABEL_233;
                      }
                    }
                  }
                  ATL::CStringData::Release((ATL::CStringData *)(v53 - 12));
                  goto LABEL_176;
                }
              }
              else
              {
                *((_DWORD *)this + 88) |= *((_DWORD *)this + 39) == 0;
                v57 = -2147024784;
                v6 = -2147024784;
              }
              v81 = v6 == v57;
              v59 = v6 != v57;
              goto LABEL_162;
            }
            goto LABEL_111;
          }
          v2 = 1;
          ++v83;
LABEL_112:
          ++v82;
LABEL_176:
          v22 = v80;
LABEL_182:
          if ( v81 && v31 >= 0 && v31 < v89 )
          {
            if ( (unsigned __int64)v31 < 0x100000 )
            {
              v63 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                pdwType = (LPDWORD)v31;
                WPP_SF_di(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v29, (unsigned int)v22);
                v63 = (PVOID *)WPP_GLOBAL_Control;
              }
              goto LABEL_199;
            }
            v89 = v31;
          }
          v6 = CMultistateFileRecordQuery::MoveNext((CMultistateFileRecordQuery *)v104);
          if ( v6 < 0 )
            goto LABEL_188;
        }
        if ( (*(_BYTE *)(*(_QWORD *)v8 + 42LL) & 4) != 0 )
          goto LABEL_112;
LABEL_66:
        v32 = 0;
        goto LABEL_68;
      }
      if ( v22 != 2 )
      {
        if ( v22 != 3 )
          goto LABEL_204;
        if ( !v86 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
          goto LABEL_204;
        }
        LODWORD(pdwType) = 2;
        v25 = CMultistateFileRecordQuery::Query(v104, 1, 2, 1, pdwType, pvData);
        goto LABEL_52;
      }
      v26 = 3;
    }
    else
    {
      v26 = 6;
    }
    v25 = CMultistateFileRecordQuery::Query(v104, 0, 1, v26, pdwType, pvData);
    goto LABEL_52;
  }
  v6 = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, "fileRecord");
    goto LABEL_262;
  }
LABEL_271:
  if ( !SetThreadToken(0, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v76 = GetLastError();
    if ( v76 > 0 )
      v76 = (unsigned __int16)v76 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      174,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      (unsigned int)v76);
  }
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(&v92);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012b44  push    rbp
0x180012b46  push    rbx
0x180012b47  push    rsi
0x180012b48  push    rdi
0x180012b49  push    r12
0x180012b4b  push    r13
0x180012b4d  push    r14
0x180012b4f  push    r15
0x180012b51  lea     rbp, [rsp-0D8h]
0x180012b59  sub     rsp, 1D8h
0x180012b60  mov     rax, cs:__security_cookie
0x180012b67  xor     rax, rsp
0x180012b6a  mov     [rbp+110h+var_48], rax
0x180012b71  mov     r14, rcx
0x180012b74  lea     rcx, [rbp+110h+var_168]
0x180012b78  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x180012b7d  mov     [rbp+110h+var_190], 0
0x180012b84  mov     [rbp+110h+var_188], 4
0x180012b8b  mov     rdx, [r14+180h]; Token
0x180012b92  xor     ecx, ecx; Thread
0x180012b94  call    cs:__imp_SetThreadToken
0x180012b9a  mov     r13d, 1
0x180012ba0  lea     r12, WPP_GLOBAL_Control
0x180012ba7  test    eax, eax
0x180012ba9  jnz     short loc_180012BF7
0x180012bab  call    cs:__imp_GetLastError
0x180012bb1  mov     esi, eax
0x180012bb3  test    eax, eax
0x180012bb5  jle     short loc_180012BC0
0x180012bb7  movzx   esi, ax
0x180012bba  or      esi, 80070000h
0x180012bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bc7  cmp     rcx, r12
0x180012bca  jz      loc_180013D8E
0x180012bd0  test    [rcx+1Ch], r13b
0x180012bd4  jz      loc_180013CD4
0x180012bda  mov     edx, 8Eh
0x180012bdf  mov     r9d, esi
0x180012be2  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180012be9  mov     rcx, [rcx+10h]
0x180012bed  call    WPP_SF_d
0x180012bf2  jmp     loc_180013CD4
0x180012bf7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012bfe  mov     ecx, 50h ; 'P'; unsigned __int64
0x180012c03  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012c08  test    rax, rax
0x180012c0b  jz      short loc_180012C1D
0x180012c0d  lea     r8, [r14+20h]
0x180012c11  lea     rdx, [r14+18h]
0x180012c15  mov     rcx, rax; this
0x180012c18  call    ??0CFileRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z; CFileRecord::CFileRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)
0x180012c1d  mov     rdx, rax
0x180012c20  lea     rcx, [rbp+110h+var_168]
0x180012c24  call    ??4?$SmartPtr@VCFileRecord@@@@QEAAAEAV0@PEAVCFileRecord@@@Z; SmartPtr<CFileRecord>::operator=(CFileRecord *)
0x180012c29  mov     rdi, [rbp+110h+var_168]
0x180012c2d  test    rdi, rdi
0x180012c30  jz      loc_180013C9D
0x180012c36  cmp     qword ptr [rdi], 0
0x180012c3a  jz      loc_180013C9D
0x180012c40  lea     rcx, [rsp+210h+lpFileName]
0x180012c45  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180012c4a  mov     ebx, [r14+2Ch]
0x180012c4e  lea     rcx, [rbp+110h+var_88]
0x180012c55  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x180012c5a  lea     rcx, [r14+10h]
0x180012c5e  lea     r9, [rsp+210h+lpFileName]
0x180012c63  mov     r8d, ebx
0x180012c66  mov     rdx, rax
0x180012c69  call    ?ConstructStagingPath@CSessionBaseRO@@IEAAJV?$SmartPtr@VCFileRecord@@@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CSessionBaseRO::ConstructStagingPath(SmartPtr<CFileRecord>,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180012c6e  mov     esi, eax
0x180012c70  test    eax, eax
0x180012c72  jns     short loc_180012CB6
0x180012c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c7b  cmp     rcx, r12
0x180012c7e  jz      short loc_180012CA3
0x180012c80  test    [rcx+1Ch], r13b
0x180012c84  jz      short loc_180012CA3
0x180012c86  mov     edx, 90h
0x180012c8b  mov     dword ptr [rsp+210h+pdwType], eax
0x180012c8f  mov     r9d, [r14+2Ch]
0x180012c93  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180012c9a  mov     rcx, [rcx+10h]
0x180012c9e  call    WPP_SF_dd
0x180012ca3  mov     rcx, [rsp+210h+lpFileName]
0x180012ca8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180012cac  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012cb1  jmp     loc_180013CD4
0x180012cb6  mov     rbx, [rsp+210h+lpFileName]
0x180012cbb  mov     rcx, rbx; lpFileName
0x180012cbe  call    cs:__imp_GetFileAttributesW
0x180012cc4  cmp     eax, 0FFFFFFFFh
0x180012cc7  jz      loc_180012D95
0x180012ccd  test    al, 10h
0x180012ccf  jz      short loc_180012D11
0x180012cd1  lea     rdx, [rsp+210h+lpFileName]
0x180012cd6  lea     rcx, [rbp+110h+var_88]
0x180012cdd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180012ce2  mov     rdx, rax
0x180012ce5  mov     [rsp+210h+pcbData], 0
0x180012cee  mov     [rsp+210h+pvData], 0
0x180012cf7  mov     [rsp+210h+pdwType], 0
0x180012d00  lea     r9, [r14+0A0h]
0x180012d07  mov     r8d, r13d
0x180012d0a  call    ?PerformDirectoryTreeOperation@FheFileOperations@@YAJW4DirectoryTreeOp@1@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEAHPEAJPEA_JPEAUIFhEngineCleanupProgressEvent@@@Z; FheFileOperations::PerformDirectoryTreeOperation(FheFileOperations::DirectoryTreeOp,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int,int *,long *,__int64 *,IFhEngineCleanupProgressEvent *)
0x180012d0f  jmp     short loc_180012D19
0x180012d11  mov     rcx, rbx; this
0x180012d14  call    ?DeleteReadOnlyFile@FheFileOperations@@YAJPEBG@Z; FheFileOperations::DeleteReadOnlyFile(ushort const *)
0x180012d19  mov     esi, eax
0x180012d1b  cmp     eax, 800704D3h
0x180012d20  jnz     short loc_180012D28
0x180012d22  lea     rcx, [rbx-18h]
0x180012d26  jmp     short loc_180012CAC
0x180012d28  test    esi, esi
0x180012d2a  jns     short loc_180012D95
0x180012d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d33  cmp     rcx, r12
0x180012d36  jz      short loc_180012D95
0x180012d38  test    byte ptr [rcx+1Ch], 2
0x180012d3c  jz      short loc_180012D62
0x180012d3e  mov     edx, 91h
0x180012d43  mov     dword ptr [rsp+210h+pdwType], esi
0x180012d47  mov     r9d, [r14+2Ch]
0x180012d4b  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180012d52  mov     rcx, [rcx+10h]
0x180012d56  call    WPP_SF_dd
0x180012d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d62  cmp     rcx, r12
0x180012d65  jz      short loc_180012D95
0x180012d67  test    byte ptr [rcx+1Ch], 4
0x180012d6b  jz      short loc_180012D95
0x180012d6d  mov     edx, 92h
0x180012d72  lea     rax, aStagingAreaCle; "Staging area cleanup should not fail or"...
0x180012d79  mov     [rsp+210h+pdwType], rax
0x180012d7e  lea     r9, aFalse; "FALSE"
0x180012d85  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180012d8c  mov     rcx, [rcx+10h]
0x180012d90  call    WPP_SF_ss
0x180012d95  lea     rcx, [rbx-18h]; this
0x180012d99  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012d9e  lea     rax, [rbp+110h+var_188]
0x180012da2  mov     [rsp+210h+pcbData], rax; pcbData
0x180012da7  lea     rax, [rbp+110h+var_190]
0x180012dab  mov     [rsp+210h+pvData], rax; pvData
0x180012db0  mov     [rsp+210h+pdwType], 0; pdwType
0x180012db9  mov     r9d, 10h; dwFlags
0x180012dbf  lea     r8, ValueName; "RestoreAllowed"
0x180012dc6  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180012dcd  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180012dd4  call    cs:__imp_RegGetValueW
0x180012dda  test    eax, eax
0x180012ddc  jnz     short loc_180012DE4
0x180012dde  cmp     [rbp+110h+var_188], 4
0x180012de2  jz      short loc_180012DEB
0x180012de4  mov     [rbp+110h+var_190], 0
0x180012deb  test    cs:Microsoft_Windows_FileHistory_EngineEnableBits, r13b
0x180012df2  jz      short loc_180012E0F
0x180012df4  lea     rax, [rbp+110h+var_88]
0x180012dfb  mov     [rsp+210h+pdwType], rax
0x180012e00  mov     r9d, r13d
0x180012e03  lea     rdx, BackupAllFilesStart
0x180012e0a  call    McGenEventWrite_EventWriteTransfer
0x180012e0f  xor     r15d, r15d
0x180012e12  lea     eax, [r15+4]
0x180012e16  mov     [rbp+110h+var_18C], eax
0x180012e19  lea     rcx, [r14+18h]
0x180012e1d  mov     [rsp+210h+var_1B0], r15d
0x180012e22  mov     rcx, [rcx]
0x180012e25  cmp     r15d, eax
0x180012e28  jge     loc_180013AFF
0x180012e2e  mov     [rbp+110h+var_180], rcx
0x180012e32  test    rcx, rcx
0x180012e35  jz      short loc_180012E44
0x180012e37  mov     rax, [rcx]
0x180012e3a  mov     rax, [rax+8]
0x180012e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e43  nop
0x180012e44  lea     rdx, [rbp+110h+var_180]
0x180012e48  lea     rcx, [rbp+110h+var_78]
0x180012e4f  call    ??0CMultistateFileRecordQuery@@QEAA@V?$CComPtr@UIFhCatalog@@@ATL@@@Z; CMultistateFileRecordQuery::CMultistateFileRecordQuery(ATL::CComPtr<IFhCatalog>)
0x180012e54  mov     ecx, r15d
0x180012e57  test    r15d, r15d
0x180012e5a  jz      loc_180012EF4
0x180012e60  sub     ecx, 1
0x180012e63  jz      short loc_180012ED5
0x180012e65  sub     ecx, 1
0x180012e68  jz      short loc_180012ECD
0x180012e6a  cmp     ecx, 1
0x180012e6d  jnz     loc_1800138FA
0x180012e73  cmp     [rbp+110h+var_190], 0
0x180012e77  jz      short loc_180012E99
0x180012e79  mov     dword ptr [rsp+210h+pdwType], 2
0x180012e81  mov     r9d, r13d
0x180012e84  lea     r8d, [rcx+1]
0x180012e88  mov     edx, r13d
0x180012e8b  lea     rcx, [rbp+110h+var_78]
0x180012e92  call    ?Query@CMultistateFileRecordQuery@@QEAAJW4_FhFileRecordSortOrder@@JZZ; CMultistateFileRecordQuery::Query(_FhFileRecordSortOrder,long,...)
0x180012e97  jmp     short loc_180012F0B
0x180012e99  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ea0  cmp     rcx, r12
0x180012ea3  jz      loc_1800138FA
0x180012ea9  test    byte ptr [rcx+1Ch], 8
0x180012ead  jz      loc_1800138FA
0x180012eb3  mov     edx, 93h
0x180012eb8  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180012ebf  mov     rcx, [rcx+10h]
0x180012ec3  call    WPP_SF_
0x180012ec8  jmp     loc_1800138FA
0x180012ecd  mov     r9d, 3
0x180012ed3  jmp     short loc_180012EFA
0x180012ed5  mov     dword ptr [rsp+210h+pdwType], 2
0x180012edd  mov     r9d, r13d
0x180012ee0  xor     edx, edx
0x180012ee2  lea     r8d, [rdx+2]
0x180012ee6  lea     rcx, [rbp+110h+var_78]
0x180012eed  call    ?Query@CMultistateFileRecordQuery@@QEAAJW4_FhFileRecordSortOrder@@JZZ; CMultistateFileRecordQuery::Query(_FhFileRecordSortOrder,long,...)
0x180012ef2  jmp     short loc_180012F0B
0x180012ef4  mov     r9d, 6
0x180012efa  mov     r8d, r13d
0x180012efd  xor     edx, edx
0x180012eff  lea     rcx, [rbp+110h+var_78]
0x180012f06  call    ?Query@CMultistateFileRecordQuery@@QEAAJW4_FhFileRecordSortOrder@@JZZ; CMultistateFileRecordQuery::Query(_FhFileRecordSortOrder,long,...)
0x180012f0b  mov     esi, eax
0x180012f0d  cmp     eax, 80070490h
0x180012f12  jz      loc_1800138FA
0x180012f18  mov     [rbp+110h+var_180], 0FFFFFFFFFFFFFFFFh
0x180012f20  mov     [rsp+210h+var_1A4], 0
0x180012f28  xor     eax, eax
0x180012f2a  mov     [rsp+210h+var_1A8], eax
0x180012f2e  test    esi, esi
0x180012f30  js      loc_180013AC0
0x180012f36  cmp     dword ptr [r14+0A0h], 0
0x180012f3e  jnz     loc_180013911
0x180012f44  cmp     dword ptr [r14+9Ch], 0
0x180012f4c  jnz     short loc_180012F58
0x180012f4e  cmp     r15d, 3
0x180012f52  jl      loc_180013815
0x180012f58  mov     qword ptr [rsp+210h+var_198], rdi
0x180012f5d  test    rdi, rdi
0x180012f60  jz      short loc_180012F66
0x180012f62  add     [rdi+8], r13d
0x180012f66  lea     rdx, [rsp+210h+var_198]
0x180012f6b  lea     rcx, [rbp+110h+var_78]
0x180012f72  call    ?LoadCurrentRecord@CMultistateFileRecordQuery@@QEAAJV?$SmartPtr@VCFileRecord@@@@@Z; CMultistateFileRecordQuery::LoadCurrentRecord(SmartPtr<CFileRecord>)
0x180012f77  mov     esi, eax
0x180012f79  cmp     eax, 80070490h
0x180012f7e  jz      loc_180013802
0x180012f84  test    eax, eax
0x180012f86  js      loc_180013A8D
0x180012f8c  xor     ebx, ebx
0x180012f8e  mov     [rsp+210h+var_198], ebx
0x180012f92  mov     [rsp+210h+var_1AC], ebx
0x180012f96  xor     r12d, r12d
0x180012f99  cmp     r15d, 3
0x180012f9d  jnz     short loc_180012FAD
0x180012f9f  mov     rax, [rdi]
0x180012fa2  test    byte ptr [rax+2Ah], 4
0x180012fa6  jz      short loc_180012FC8
0x180012fa8  jmp     loc_180013304
0x180012fad  xor     r13d, r13d
0x180012fb0  test    r15d, r15d
0x180012fb3  jz      loc_180013271
0x180012fb9  lea     eax, [r15-1]
0x180012fbd  mov     r13d, 1
0x180012fc3  cmp     eax, r13d
0x180012fc6  jbe     short loc_180012FCC
0x180012fc8  xor     eax, eax
0x180012fca  jmp     short loc_180012FCF
0x180012fcc  mov     eax, r13d
0x180012fcf  mov     [r14+1D8h], eax
0x180012fd6  test    eax, eax
0x180012fd8  mov     rax, [rdi]
0x180012fdb  jz      short loc_180012FE3
0x180012fdd  test    byte ptr [rax+2Ah], 8
0x180012fe1  jmp     short loc_180012FE7
0x180012fe3  test    byte ptr [rax+2Ah], 10h
0x180012fe7  jnz     short loc_180012FEC
0x180012fe9  xor     r13d, r13d
0x180012fec  mov     rax, 7FFFFFFFFFFFFFFFh
0x180012ff6  mov     [r14+1C8h], rax
0x180012ffd  mov     r15d, r13d
0x180013000  xor     r15d, 1
0x180013004  mov     edx, r15d; int
0x180013007  mov     rcx, r14; this
0x18001300a  call    ?CalculateTransferQuotas@CBackupSession@@AEAAXH@Z; CBackupSession::CalculateTransferQuotas(int)
0x18001300f  cmp     [r14+1B8h], ebx
0x180013016  jnz     loc_180013857
0x18001301c  mov     rax, [rdi]
0x18001301f  test    byte ptr [rax+2Ah], 20h
0x180013023  jnz     short loc_180013032
0x180013025  mov     r12, [rax+30h]
0x180013029  test    r12, r12
0x18001302c  jns     loc_180013127
0x180013032  xorps   xmm0, xmm0
0x180013035  xor     eax, eax
0x180013037  movups  [rbp+110h+FileInformation], xmm0
0x18001303b  movups  [rbp+110h+var_A0], xmm0
0x18001303f  mov     [rbp+110h+var_90], eax
0x180013045  lea     rcx, [rbp+110h+var_170]
0x180013049  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001304e  lea     rdx, [rbp+110h+var_170]
  ... truncated ...
```
