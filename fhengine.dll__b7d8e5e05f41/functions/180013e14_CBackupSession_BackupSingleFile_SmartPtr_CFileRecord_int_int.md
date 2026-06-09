# CBackupSession::BackupSingleFile(SmartPtr<CFileRecord>,int,int)

- ea: `0x180013e14`
- end: `0x180016066`
- name: `?BackupSingleFile@CBackupSession@@AEAAJV?$SmartPtr@VCFileRecord@@@@HH@Z`
- size: `8786`
- prototype: `__int64 __fastcall(__int64, CFileRecord **, int, int)`
- caller_count: `1`
- callee_count: `54`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012b44`

## callees

- `0x1800025b0`
- `0x180002be4`
- `0x180002c24`
- `0x1800031b0`
- `0x1800062d0`
- `0x1800077f0`
- `0x180007818`
- `0x180007a1c`
- `0x180007a9c`
- `0x180007c08`
- `0x180007d5c`
- `0x18000815c`
- `0x18000835c`
- `0x1800091a4`
- `0x180009258`
- `0x18000935c`
- `0x1800093a8`
- `0x180009404`
- `0x1800094d0`
- `0x180009528`
- `0x18000960c`
- `0x180009920`
- `0x1800099ec`
- `0x180009a80`
- `0x180009d70`
- `0x18000a7d4`
- `0x18000baa8`
- `0x18000bca8`
- `0x18000bcd8`
- `0x18000c360`
- `0x18000c450`
- `0x18000d4f4`
- `0x180010844`
- `0x180012418`
- `0x1800124a0`
- `0x180012520`
- `0x1800125b8`
- `0x1800126f0`
- `0x1800127b0`
- `0x18001284c`
- `0x180013e14`
- `0x18001a4a8`
- `0x18001a6b0`
- `0x1800220a4`
- `0x180022124`
- `0x1800221c0`
- `0x180022298`
- `0x1800223d8`
- `0x180022558`
- `0x180022814`

## import_xrefs

- `msvcrt!towupper` at `0x1800141d6`
- `msvcrt!towupper` at `0x1800141d6`
- `msvcrt!iswalpha` at `0x180014194`
- `msvcrt!iswalpha` at `0x180014194`
- `ADVAPI32!SystemFunction036` at `0x1800149f7`
- `ADVAPI32!SystemFunction036` at `0x18001521b`
- `ADVAPI32!SystemFunction036` at `0x1800158ee`
- `ADVAPI32!SystemFunction036` at `0x180015d50`
- `ADVAPI32!SystemFunction036` at `0x1800149f7`
- `ADVAPI32!SystemFunction036` at `0x18001521b`
- `ADVAPI32!SystemFunction036` at `0x1800158ee`
- `ADVAPI32!SystemFunction036` at `0x180015d50`
- `ADVAPI32!SetThreadToken` at `0x1800144a6`
- `ADVAPI32!SetThreadToken` at `0x18001459c`
- `ADVAPI32!SetThreadToken` at `0x1800144a6`
- `ADVAPI32!SetThreadToken` at `0x18001459c`
- `KERNEL32!GetLastError` at `0x1800144c9`
- `KERNEL32!GetLastError` at `0x18001454d`
- `KERNEL32!GetLastError` at `0x1800145a6`
- `KERNEL32!GetLastError` at `0x180015b77`
- `KERNEL32!GetLastError` at `0x180015bae`
- `KERNEL32!GetLastError` at `0x1800144c9`
- `KERNEL32!GetLastError` at `0x18001454d`
- `KERNEL32!GetLastError` at `0x1800145a6`
- `KERNEL32!GetLastError` at `0x180015b77`
- `KERNEL32!GetLastError` at `0x180015bae`
- `KERNEL32!ResetEvent` at `0x180014b05`
- `KERNEL32!ResetEvent` at `0x180014b05`
- `KERNEL32!SetEvent` at `0x180014f87`
- `KERNEL32!SetEvent` at `0x180014f87`
- `KERNEL32!GetFileAttributesW` at `0x180015b5a`
- `KERNEL32!GetFileAttributesW` at `0x180015b5a`
- `KERNEL32!CreateFileW` at `0x180014524`
- `KERNEL32!CreateFileW` at `0x180014524`
- `OLEAUT32!__imp_SysStringLen` at `0x1800149db`
- `OLEAUT32!__imp_SysStringLen` at `0x180014a11`
- `OLEAUT32!__imp_SysStringLen` at `0x180014a32`
- `OLEAUT32!__imp_SysStringLen` at `0x180014a4c`
- `OLEAUT32!__imp_SysStringLen` at `0x180014a7f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800149db`
- `OLEAUT32!__imp_SysStringLen` at `0x180014a11`
- `OLEAUT32!__imp_SysStringLen` at `0x180014a32`
- `OLEAUT32!__imp_SysStringLen` at `0x180014a4c`
- `OLEAUT32!__imp_SysStringLen` at `0x180014a7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CBackupSession::BackupSingleFile(__int64 a1, CFileRecord **a2, int a3, int a4)
{
  LPCWSTR *v5; // r12
  __int64 v6; // r14
  __int64 v7; // rdx
  __int64 v8; // r9
  PVOID *v9; // r11
  __int64 v10; // r9
  WCHAR *v11; // r8
  int Name; // eax
  int v13; // esi
  _QWORD *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // rdi
  signed int v20; // esi
  CFileRecord ***v21; // r12
  LPCWSTR v22; // rax
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rbx
  wint_t v27; // ax
  wint_t v28; // ax
  wint_t v29; // ax
  char v30; // dl
  __int64 v31; // rbx
  __int64 Manager; // rdx
  ATL::CStringData *v33; // rcx
  const WCHAR *v34; // rbx
  LPCWSTR v35; // rax
  __int64 v36; // rbx
  CFileRecord *v37; // rcx
  int v38; // eax
  signed int v39; // r14d
  signed int LastError; // eax
  HANDLE FileW; // rax
  char v43; // al
  signed int v44; // eax
  __int64 v45; // rcx
  CNamespaceRecord **v46; // rbx
  CNamespaceRecord *v47; // rax
  __int64 v48; // rax
  int v49; // eax
  _QWORD *v50; // rcx
  __int64 v51; // rdx
  _QWORD *v52; // rcx
  int v53; // edx
  LPCWSTR v54; // rax
  __int64 v55; // r9
  LPCWSTR v56; // rcx
  __int64 v57; // r10
  LPCWSTR v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  int v62; // eax
  int v63; // eax
  LPCWSTR v64; // rcx
  __int64 v65; // r8
  unsigned int v66; // ecx
  _QWORD *v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rax
  int v71; // r8d
  PVOID v72; // rcx
  int v73; // eax
  void *v74; // r14
  _QWORD *v75; // rsi
  _DWORD *v76; // r12
  __int64 *v77; // r15
  LPCWSTR *v78; // rax
  void *v79; // r12
  _QWORD *v80; // rsi
  CNamespaceRecord *v81; // rax
  _QWORD *v82; // r13
  _DWORD *v83; // r15
  __int64 *v84; // r14
  LPCWSTR *v85; // rax
  int v86; // esi
  unsigned __int64 v87; // r9
  ATL::CStringData *v88; // rax
  __int64 v89; // r8
  int v90; // ecx
  unsigned __int64 v91; // rdx
  int v92; // ecx
  CFileRecord **v93; // rax
  CFileRecord **v94; // rax
  CFileRecord *v95; // r8
  bool v96; // zf
  unsigned int v97; // r8d
  _DWORD *v98; // rsi
  CFileRecord *v99; // r8
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  CFileRecord **v103; // rdx
  __int64 v104; // r8
  __int64 v105; // rsi
  __int64 v106; // rax
  CFileRecord **v107; // rax
  CFileRecord *v108; // rcx
  CFileRecord **v109; // rax
  CFileRecord *v110; // rcx
  _QWORD *v111; // rcx
  int v112; // edx
  CFileRecord *v113; // r9
  _QWORD *v114; // rcx
  int v115; // edx
  CFileRecord *v116; // rcx
  int v117; // edx
  CFileRecord **v118; // rax
  int v119; // r8d
  unsigned int v120; // esi
  __int64 v121; // rcx
  int v122; // edx
  PVOID v123; // rcx
  CFileRecord **v124; // rcx
  CFileRecord *v125; // rdx
  CFileRecord **v126; // rax
  const char *v127; // r9
  CFileRecord *v128; // rax
  int v129; // eax
  __int64 v130; // rax
  void (__fastcall ***v131)(_QWORD, _QWORD); // rsi
  signed int v132; // eax
  void (__fastcall *v133)(_QWORD, _QWORD); // r14
  signed int v134; // eax
  CFileRecord **v135; // rax
  CFileRecord *v136; // rcx
  CFileRecord **v137; // rax
  __int64 v138; // r8
  __int64 v139; // rax
  __int64 v140; // rdx
  PVOID v141; // rcx
  CFileRecord *v142; // rax
  int v143; // eax
  __int64 v144; // rax
  CFileRecord **v145; // rax
  CFileRecord *v146; // rcx
  CNamespaceRecord *v147; // r14
  CNamespaceRecord *v148; // rsi
  int dwCreationDisposition; // [rsp+20h] [rbp-178h]
  unsigned __int64 RandomBuffer; // [rsp+A0h] [rbp-F8h] BYREF
  signed int v151; // [rsp+A8h] [rbp-F0h]
  PVOID **v152; // [rsp+B0h] [rbp-E8h]
  LPCWSTR lpFileName; // [rsp+B8h] [rbp-E0h] BYREF
  int v154; // [rsp+C0h] [rbp-D8h]
  _DWORD *v155; // [rsp+C8h] [rbp-D0h] BYREF
  __int64 v156; // [rsp+D0h] [rbp-C8h] BYREF
  __int64 v157; // [rsp+D8h] [rbp-C0h] BYREF
  CBackupSession *v158; // [rsp+E0h] [rbp-B8h] BYREF
  __int64 v159; // [rsp+E8h] [rbp-B0h] BYREF
  unsigned __int64 v160; // [rsp+F0h] [rbp-A8h] BYREF
  CFileRecord **v161; // [rsp+F8h] [rbp-A0h] BYREF
  __int64 v162; // [rsp+100h] [rbp-98h] BYREF
  int v163; // [rsp+108h] [rbp-90h] BYREF
  int v164; // [rsp+10Ch] [rbp-8Ch]
  unsigned int v165; // [rsp+110h] [rbp-88h]
  __int64 v166; // [rsp+118h] [rbp-80h] BYREF
  __int64 *v167; // [rsp+120h] [rbp-78h] BYREF
  int v168; // [rsp+128h] [rbp-70h]
  unsigned __int64 v169; // [rsp+130h] [rbp-68h] BYREF
  CNamespaceRecord **v170; // [rsp+138h] [rbp-60h] BYREF
  _QWORD *v171; // [rsp+140h] [rbp-58h] BYREF
  __int64 v172; // [rsp+148h] [rbp-50h] BYREF
  ATL::CStringData *v173; // [rsp+150h] [rbp-48h]
  int v174[15]; // [rsp+15Ch] [rbp-3Ch] BYREF
  CFileRecord **v176; // [rsp+1A8h] [rbp+10h] BYREF
  int v177; // [rsp+1B0h] [rbp+18h]
  int v178; // [rsp+1B8h] [rbp+20h]

  v178 = a4;
  v177 = a3;
  v176 = a2;
  v5 = (LPCWSTR *)a2;
  v152 = (PVOID **)a2;
  v6 = a1;
  v168 = 0;
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v170);
  v172 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v159);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v156);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v166);
  v162 = 0;
  v163 = 0;
  v160 = 0;
  v158 = 0;
  if ( a3 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v10 = *(_QWORD *)*v5;
      WPP_SF_ddDddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        377,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        *(unsigned int *)(v10 + 16),
        *(unsigned __int16 *)(v10 + 40),
        *(unsigned __int16 *)(v10 + 42),
        *(_DWORD *)(v10 + 56),
        *(_DWORD *)(v10 + 60),
        *(_DWORD *)(v10 + 64));
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = (WCHAR *)*v5;
    if ( (unsigned __int16)(*(_WORD *)(*(_QWORD *)*v5 + 40LL) - 1) <= 2u )
      goto LABEL_6;
LABEL_16:
    v151 = 0;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
    {
      LOBYTE(v8) = v177;
      WPP_SF_cd(v9[2], v7, v11, v8, *(unsigned __int16 *)(*(_QWORD *)v11 + 40LL));
    }
    goto LABEL_19;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v17 = *(_QWORD *)*v5;
    WPP_SF_ddDddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      378,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      *(unsigned int *)(v17 + 16),
      *(unsigned __int16 *)(v17 + 40),
      *(unsigned __int16 *)(v17 + 42),
      *(_DWORD *)(v17 + 56),
      *(_DWORD *)(v17 + 60),
      *(_DWORD *)(v17 + 64));
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = (WCHAR *)*v5;
  v18 = *(_QWORD *)*v5;
  if ( *(_WORD *)(v18 + 40) != 1 && *(_WORD *)(v18 + 40) != 2 )
    goto LABEL_16;
LABEL_6:
  Name = CFileRecord::GetName(*(_QWORD *)v11, &v159);
  v13 = Name;
  v151 = Name;
  if ( Name < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v15 = *(_QWORD *)*v5;
    v16 = 380;
    dwCreationDisposition = Name;
LABEL_10:
    WPP_SF_dd(
      v14[2],
      v16,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      *(unsigned int *)(v15 + 16),
      dwCreationDisposition);
LABEL_19:
    v19 = v159;
    v20 = v151;
LABEL_20:
    v21 = (CFileRecord ***)v152;
    goto LABEL_49;
  }
  v22 = *v5;
  v23 = *(_QWORD *)*v5;
  if ( *(_WORD *)(v23 + 40) == 3 )
  {
    v24 = *(unsigned int *)(v23 + 60);
    lpFileName = *v5;
    ++*((_DWORD *)v22 + 2);
    v13 = CSessionBaseRO::ConstructStagingPath(v6 + 16, &lpFileName, v24, &v156);
    v151 = v13;
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v15 = *(_QWORD *)*v5;
      v16 = 381;
      dwCreationDisposition = v13;
      goto LABEL_10;
    }
    v19 = v159;
  }
  else
  {
    v19 = v159;
    v25 = v156 - 24;
    RandomBuffer = v156 - 24;
    if ( v159 - 24 != v156 - 24 )
    {
      if ( *(int *)(v25 + 16) >= 0 && *(_QWORD *)(v159 - 24) == *(_QWORD *)v25 )
      {
        v26 = ((__int64 (*)(void))ATL::CSimpleStringT<unsigned short,0>::CloneData)();
        ATL::CStringData::Release((ATL::CStringData *)RandomBuffer);
        v156 = v26 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v156, v159, *(unsigned int *)(v159 - 16));
      }
    }
  }
  if ( *(int *)(v156 - 16) > 1
    && (v27 = ATL::CSimpleStringT<unsigned short,0>::operator[](&v156, 0), iswalpha(v27))
    && (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::operator[](&v156, 1) == 58 )
  {
    v164 = 0;
    v28 = ATL::CSimpleStringT<unsigned short,0>::operator[](&v156, 0);
    v29 = towupper(v28);
    v30 = v29 - 65;
    v165 = v29 - 65;
    v167 = (__int64 *)(v6 + 8 * (v165 + 71LL));
    if ( *v167 == -1 )
    {
      v154 = 1 << v30;
      LODWORD(v169) = 1 << v30;
      v155 = (_DWORD *)(v6 + 560);
      if ( ((1 << v30) & *(_DWORD *)(v6 + 560)) == 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
        v31 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                &v156,
                &v171,
                2);
        Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(v31);
        ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v161, Manager);
        v168 = 1;
        ATL::CSimpleStringT<unsigned short,0>::Concatenate(&v161, L"\\\\.\\", 4);
        v33 = (ATL::CStringData *)(v161 - 3);
        RandomBuffer = (unsigned __int64)(v161 - 3);
        v34 = lpFileName;
        v35 = lpFileName - 12;
        v173 = (ATL::CStringData *)(lpFileName - 12);
        if ( v161 - 3 != (CFileRecord **)(lpFileName - 12) )
        {
          if ( *((int *)v35 + 4) >= 0 && *(_QWORD *)v33 == *(_QWORD *)v35 )
          {
            v36 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v33);
            ATL::CStringData::Release(v173);
            v34 = (const WCHAR *)(v36 + 24);
            lpFileName = v34;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&lpFileName, v161, *((unsigned int *)v161 - 4));
            v34 = lpFileName;
          }
          v33 = (ATL::CStringData *)RandomBuffer;
        }
        ATL::CStringData::Release(v33);
        ATL::CStringData::Release((ATL::CStringData *)(v171 - 3));
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              382,
              &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
              (unsigned int)v13);
          ATL::CStringData::Release((ATL::CStringData *)(v34 - 12));
          v20 = v151;
LABEL_48:
          v21 = (CFileRecord ***)v152;
          goto LABEL_49;
        }
        if ( !SetThreadToken(0, 0)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            383,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            (unsigned int)LastError);
        }
        FileW = CreateFileW(v34, 0x100001u, 7u, 0, 3u, 0, 0);
        *v167 = (__int64)FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v43 = GetLastError();
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              384,
              (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
              (int)v34,
              v43);
          }
          *v155 |= v154;
        }
        if ( !SetThreadToken(0, *(HANDLE *)(v6 + 384)) )
        {
          v44 = GetLastError();
          v20 = v44;
          if ( v44 > 0 )
            v20 = (unsigned __int16)v44 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              385,
              &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
              (unsigned int)v20);
          ATL::CStringData::Release((ATL::CStringData *)(v34 - 12));
          goto LABEL_48;
        }
        ATL::CStringData::Release((ATL::CStringData *)(v34 - 12));
      }
    }
  }
  else
  {
    v165 = 0;
    v164 = 1;
  }
  v45 = *(_QWORD *)*v5;
  if ( *(_WORD *)(v45 + 40) != 1 )
  {
    lpFileName = (LPCWSTR)-1LL;
    if ( *(_WORD *)(v45 + 40) != 2 )
    {
      v46 = v170;
      goto LABEL_104;
    }
  }
  v47 = (CNamespaceRecord *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v47 )
    v48 = CNamespaceRecord::CNamespaceRecord(v47);
  else
    v48 = 0;
  SmartPtr<CNamespaceRecord>::operator=(&v170, v48);
  v46 = v170;
  if ( !v170 || !*v170 )
  {
    v20 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        386,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        "namespaceRecord");
    goto LABEL_20;
  }
  v49 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(v6 + 24) + 240LL))(
          *(_QWORD *)(v6 + 24),
          *(unsigned int *)(*(_QWORD *)*v5 + 16LL),
          &v172);
  v20 = v49;
  if ( v49 < 0 )
  {
    if ( v49 == -2147023728 )
    {
      v52 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_96;
      v53 = 390;
      goto LABEL_95;
    }
    v50 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v51 = 391;
LABEL_90:
    WPP_SF_d(v50[2], v51, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, (unsigned int)v49);
    goto LABEL_20;
  }
  v49 = CNamespaceRecord::LoadCurrentFromEnum(*v46, &v172);
  v20 = v49;
  if ( v49 < 0 )
  {
    v50 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v51 = 387;
    goto LABEL_90;
  }
  v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v172 + 32LL))(v172);
  v20 = v49;
  if ( v49 >= 0 )
  {
    v52 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_96;
    v53 = 388;
LABEL_95:
    WPP_SF_dS(
      v52[2],
      v53,
      (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      *(_DWORD *)(*(_QWORD *)*v5 + 16LL),
      v19);
LABEL_96:
    v54 = *v5;
    v176 = (CFileRecord **)*v5;
    if ( v176 )
      ++*((_DWORD *)v54 + 2);
    CSessionBaseRW::RemoveFileRecord(v6 + 8, &v176, 0, 0);
    v20 = 0;
    goto LABEL_20;
  }
  if ( v49 != -2147023728 )
  {
    v50 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v51 = 389;
    goto LABEL_90;
  }
  lpFileName = (LPCWSTR)(*((unsigned int *)*v46 + 15) + ((unsigned __int64)*((unsigned int *)*v46 + 16) << 32));
LABEL_104:
  v55 = *(_QWORD *)*v5;
  if ( (*(_BYTE *)(v55 + 42) & 0x20) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        392,
        (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        *(_DWORD *)(v55 + 16),
        v19);
    v56 = *v5;
    v57 = v6 + 8;
    if ( (*(_BYTE *)(*(_QWORD *)*v5 + 42LL) & 0x18) != 0 )
    {
      RandomBuffer = (unsigned __int64)*v5;
      ++*((_DWORD *)v56 + 2);
      v49 = CSessionBaseRW::CleanupFileRecord(v6 + 8, &RandomBuffer, 1, 1);
      v20 = v49;
      if ( v49 < 0 )
      {
        v50 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_20;
        v51 = 393;
        goto LABEL_90;
      }
      v57 = v6 + 8;
    }
    v58 = *v5;
    RandomBuffer = (unsigned __int64)v58;
    if ( v58 )
      ++*((_DWORD *)v58 + 2);
    CSessionBaseRW::ChangeFileRecordStatus(v57, &RandomBuffer, 32);
    v59 = *(_QWORD *)*v5;
    *(_DWORD *)(v59 + 76) = 1;
    *(_QWORD *)(v59 + 48) = -1;
    v60 = *(_QWORD *)*v5;
    *(_DWORD *)(v60 + 76) = 1;
    *(_DWORD *)(v60 + 60) = 0;
  }
  v61 = *(_QWORD *)*v5;
  if ( !*(_DWORD *)(v61 + 60) )
  {
    v62 = *(_DWORD *)(v6 + 44);
    *(_DWORD *)(v61 + 76) = 1;
    *(_DWORD *)(v61 + 60) = v62;
  }
  v63 = v177;
  *(_DWORD *)(v6 + 472) = v177;
  v157 = v6 + 16;
  v64 = *v5;
  v65 = *(unsigned int *)(*(_QWORD *)*v5 + 60LL);
  RandomBuffer = (unsigned __int64)*v5;
  if ( v63 )
  {
    if ( v64 )
      ++*((_DWORD *)v64 + 2);
    v20 = CSessionBaseRO::ConstructTargetPath((int)v6 + 16, (int)&RandomBuffer, v65, (int)&v166, 0);
    v151 = v20;
    if ( v20 < 0 )
    {
      v67 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v68 = 394;
      goto LABEL_126;
    }
    if ( v20 == 1 )
    {
      RandomBuffer = 1;
      if ( SysStringLen(*(BSTR *)(*(_QWORD *)*v5 + 24LL)) == *(_DWORD *)(v6 + 992) )
      {
        SystemFunction036(&RandomBuffer, 8u);
        ++*(_DWORD *)(v6 + 996);
      }
      else if ( SysStringLen(*(BSTR *)(*(_QWORD *)*v5 + 24LL)) > *(_DWORD *)(v6 + 992) )
      {
        *(_DWORD *)(v6 + 996) = 1;
      }
      if ( SysStringLen(*(BSTR *)(*(_QWORD *)*v5 + 24LL)) > *(_DWORD *)(v6 + 992)
        || SysStringLen(*(BSTR *)(*(_QWORD *)*v5 + 24LL)) == *(_DWORD *)(v6 + 992)
        && (v66 = *(_DWORD *)(v6 + 996), !(RandomBuffer % v66)) )
      {
        if ( __eh34_try(-1, 2) )
        {
          __eh34_scope_strut(2);
          *(_DWORD *)(v6 + 992) = SysStringLen(*(BSTR *)(*(_QWORD *)*v5 + 24LL));
          v69 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  &v155,
                  *(_QWORD *)(*(_QWORD *)*v5 + 24LL));
          FheFileOperations::ExtractTruncatedFileExt(v69, v6 + 1008);
        }
        if ( __eh34_catch(2) )
        {
          if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)v174) )
          {
            v151 = v174[0];
            if ( v174[0] < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  395,
                  &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  (unsigned int)v174[0]);
              v21 = (CFileRecord ***)v176;
              v19 = v159;
              v20 = v151;
              __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_180014B49);
              goto LABEL_49;
            }
            v5 = (LPCWSTR *)v176;
            v152 = (PVOID **)v176;
            v46 = v170;
            v19 = v159;
            v6 = a1;
            __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_180014B6C);
          }
        }
      }
    }
  }
  else
  {
    if ( v64 )
      ++*((_DWORD *)v64 + 2);
    v20 = CSessionBaseRO::ConstructStagingPath(v6 + 16, &RandomBuffer, v65, &v166);
    v151 = v20;
    if ( v20 < 0 )
    {
      v67 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v68 = 396;
LABEL_126:
      WPP_SF_dd(
        v67[2],
        v68,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        *(unsigned int *)(*(_QWORD *)*v5 + 16LL),
        v20);
      goto LABEL_20;
    }
  }
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
  {
    v70 = *(_QWORD *)*v5;
    *(_DWORD *)(v70 + 76) = 1;
    McTemplateU0zzi_EventWriteTransfer(v66, (int)BackupOneFileStart, v156, v166, *(_QWORD *)(v70 + 48));
  }
  v71 = v177;
  if ( v177 )
  {
    ResetEvent(*(HANDLE *)(v6 + 168));
    if ( !*(_DWORD *)(v6 + 156) )
    {
      v158 = (CBackupSession *)0x100000000LL;
      v73 = -2147024893;
      v154 = -2147024893;
      v162 = 0;
      v21 = (CFileRecord ***)v152;
      goto LABEL_155;
    }
    v71 = v177;
  }
  if ( (unsigned __int16)(*(_WORD *)(*(_QWORD *)*v5 + 40LL) - 1) > 1u )
  {
    v74 = *(void **)(v6 + 280);
    v75 = (_QWORD *)(a1 + (-(__int64)(v71 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 904);
    v76 = (_DWORD *)((v71 != 0 ? 0xF0 : 0) + a1 + 160);
    v171 = &v155;
    v77 = (__int64 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                       &v155,
                       &v166);
    v78 = (LPCWSTR *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                       &v167,
                       &v156);
    v73 = FheFileOperations::CopyFileWithBackoff(
            v78,
            v77,
            a1 + 348,
            0,
            v178,
            1,
            a1 + 448,
            v76,
            0,
            0,
            0,
            0,
            0,
            &v162,
            (unsigned int *)&v158,
            (int *)&v158 + 1,
            &v163,
            v75,
            &v160,
            v74);
    v154 = v73;
    v21 = (CFileRecord ***)v152;
LABEL_154:
    v6 = a1;
    goto LABEL_155;
  }
  v169 = 0;
  RandomBuffer = -1;
  v169 = ((unsigned __int64)*((unsigned int *)*v46 + 18) << 32) + *((unsigned int *)*v46 + 17);
  v79 = *(void **)(v6 + 280);
  v80 = (_QWORD *)(v6 + (-(__int64)(v71 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 904);
  v81 = *v46;
  v82 = (_QWORD *)((char *)*v46 + 68);
  v171 = (_QWORD *)((char *)*v46 + 60);
  v173 = (CNamespaceRecord *)((char *)v81 + 56);
  v83 = (_DWORD *)(v6 + (v71 != 0 ? 400LL : 160LL));
  v161 = (CFileRecord **)&v155;
  v84 = (__int64 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                     &v155,
                     &v166);
  v85 = (LPCWSTR *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                     &v167,
                     &v156);
  v73 = FheFileOperations::CopyFileWithBackoff(
          v85,
          v84,
          a1 + 348,
          1,
          v178,
          1,
          a1 + 448,
          v83,
          &RandomBuffer,
          v173,
          v171,
          v82,
          &v169,
          &v162,
          (unsigned int *)&v158,
          (int *)&v158 + 1,
          &v163,
          v80,
          &v160,
          v79);
  v86 = v73;
  v154 = v73;
  v87 = RandomBuffer;
  v21 = (CFileRecord ***)v152;
  if ( RandomBuffer == -1 )
    goto LABEL_154;
  v72 = **v152;
  v88 = (ATL::CStringData *)*((_QWORD *)v72 + 6);
  if ( v88 == (ATL::CStringData *)RandomBuffer )
  {
LABEL_153:
    v73 = v154;
    goto LABEL_154;
  }
  if ( v88 == (ATL::CStringData *)-1LL )
  {
    *((_DWORD *)v72 + 19) = 1;
    *((_QWORD *)v72 + 6) = v87;
    goto LABEL_153;
  }
  if ( v86 < 0 )
    goto LABEL_153;
  v72 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_ii(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      397,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      RandomBuffer,
      v88);
  v6 = a1;
  v73 = v154;
LABEL_155:
  *(_DWORD *)(v6 + 360) |= CBackupSession::IsChkDskRequired((CBackupSession *)v72, v73);
  v90 = v177;
  if ( v177 )
  {
    SetEvent(*(HANDLE *)(v6 + 168));
    v90 = v177;
  }
  if ( v154 < 0 && HIDWORD(v158) && v90 && *(_DWORD *)(v6 + 824) == -1 )
    *(_DWORD *)(v6 + 824) = v154;
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
    McTemplateU0zzi_EventWriteTransfer(v90, (int)BackupOneFileStop, v156, v166, v160);
  _InterlockedAdd64((volatile signed __int64 *)(v6 + 416), v160);
  v91 = *(_QWORD *)(v6 + 416);
  _m_prefetchw((const void *)(v6 + 432));
  if ( _InterlockedOr64((volatile signed __int64 *)(v6 + 432), 0) <= v91 )
  {
    _InterlockedExchange64((volatile __int64 *)(v6 + 432), v91);
    *(_DWORD *)(v6 + 440) = 1;
  }
  v92 = v177;
  if ( v177 )
    *(_QWORD *)(v6 + 872) += v160;
  else
    *(_QWORD *)(v6 + 880) += v160;
  if ( v163 )
  {
    if ( v163 <= 0 )
    {
      v94 = *v21;
      RandomBuffer = (unsigned __int64)v94;
      if ( v94 )
        ++*((_DWORD *)v94 + 2);
      LOWORD(v89) = v92 != 0 ? 8 : 16;
    }
    else
    {
      v93 = *v21;
      RandomBuffer = (unsigned __int64)v93;
      if ( v93 )
        ++*((_DWORD *)v93 + 2);
      v89 = 0;
    }
    CSessionBaseRW::ChangeFileRecordStatus(v6 + 8, &RandomBuffer, v89);
    v92 = v177;
    v95 = **v21;
    if ( (unsigned __int16)(*((_WORD *)v95 + 20) - 1) <= 1u )
    {
      v96 = (*((_WORD *)v95 + 21) & 0x10) == 0;
      *((_DWORD *)v95 + 19) = 1;
      if ( v96 )
        *((_WORD *)v95 + 20) = 1;
      else
        *((_WORD *)v95 + 20) = 2;
    }
  }
  v97 = v154;
  if ( v154 >= 0 )
  {
    RandomBuffer = v6 + 892;
    v98 = (_DWORD *)(v6 + 888);
    if ( v92 )
    {
      ++*v98;
    }
    else
    {
      ++*(_DWORD *)(v6 + 892);
      RandomBuffer = v6 + 892;
    }
    v99 = **v21;
    if ( (unsigned __int16)(*((_WORD *)v99 + 20) - 1) <= 1u )
    {
      v161 = 0;
      v100 = *((_QWORD *)v99 + 6);
      if ( v100 > *(_QWORD *)(v6 + 920) )
      {
        *(_QWORD *)(v6 + 920) = v100;
        *(_QWORD *)(v6 + 944) = lpFileName;
        v101 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                 &v155,
                 &v156);
        FheFileOperations::ExtractTruncatedFileExt(v101, v6 + 976);
      }
      SystemFunction036(&v161, 8u);
      if ( !((unsigned __int64)v161 % (*v98 + *(_DWORD *)RandomBuffer)) )
      {
        *(_QWORD *)(v6 + 912) = *((_QWORD *)**v21 + 6);
        *(_QWORD *)(v6 + 936) = lpFileName;
        v102 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                 &v155,
                 &v156);
        FheFileOperations::ExtractTruncatedFileExt(v102, v6 + 968);
      }
      v92 = v177;
    }
    if ( v92 && (*((_BYTE *)**v21 + 42) & 0x10) != 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
      v103 = *v21;
      v104 = *((unsigned int *)**v21 + 15);
      RandomBuffer = (unsigned __int64)v103;
      if ( v103 )
        ++*((_DWORD *)v103 + 2);
      v20 = CSessionBaseRO::ConstructStagingPath(v157, &RandomBuffer, v104, &lpFileName);
      if ( v20 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            398,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            *((unsigned int *)**v21 + 4),
            v20);
        ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
        goto LABEL_49;
      }
      v167 = &v157;
      v105 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
               &v157,
               v6 + 64);
      v106 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
               &v155,
               &lpFileName);
      if ( (int)FheFileOperations::DeleteFileWithEmptyParents(v106, v105) < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          399,
          (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (int)"SUCCEEDED(hr)",
          (__int64)"Deletion of a fully backed up staged file should not fail");
      }
      v107 = *v21;
      v176 = v107;
      if ( v107 )
        ++*((_DWORD *)v107 + 2);
      CSessionBaseRW::ChangeFileRecordStatus(v6 + 8, &v176, 16);
      ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
    }
    v108 = **v21;
    if ( (*((_BYTE *)v108 + 42) & 2) != 0 )
    {
      if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(v108, FileNotice_BackupSucceeded, v19);
      v109 = *v21;
      v176 = v109;
      if ( v109 )
        ++*((_DWORD *)v109 + 2);
      CSessionBaseRW::ChangeFileRecordStatus(v6 + 8, &v176, 2);
    }
    v110 = **v21;
    *((_DWORD *)v110 + 19) = 1;
    if ( v177 )
      *((_WORD *)v110 + 20) = 4;
    else
      *((_WORD *)v110 + 20) = 3;
    v20 = CFileRecord::Commit(**v21);
    if ( v20 < 0 )
    {
      v111 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_49;
      v112 = 400;
      goto LABEL_225;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v113 = **v21;
      WPP_SF_ddDddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        401,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        *((unsigned int *)v113 + 4),
        *((unsigned __int16 *)v113 + 20),
        *((unsigned __int16 *)v113 + 21),
        *((_DWORD *)v113 + 14),
        *((_DWORD *)v113 + 15),
        *((_DWORD *)v113 + 16));
    }
    if ( v46 && *v46 && (*((_BYTE *)*v46 + 40) & 0x10) != 0 )
    {
      *((_QWORD *)*v46 + 6) = v162;
      v176 = v46;
      ++*((_DWORD *)v46 + 2);
      v20 = CSessionBaseRW::ActivateNamespaceRecord(v6 + 8, &v176, 0);
      if ( v20 < 0 )
      {
        v114 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_49;
        v115 = 402;
        goto LABEL_236;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_dDddid(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          403,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          *((unsigned int *)*v46 + 4),
          *((unsigned __int16 *)*v46 + 20),
          *((_DWORD *)*v46 + 19),
          *((_DWORD *)*v46 + 20),
          *((_QWORD *)*v46 + 6),
          *((_DWORD *)*v46 + 21));
    }
LABEL_240:
    v20 = 0;
    goto LABEL_49;
  }
  v116 = **v21;
  if ( (unsigned __int16)(*((_WORD *)v116 + 20) - 1) > 1u )
  {
    v117 = (int)v158;
  }
  else if ( v154 == -2147220476 || (v117 = (int)v158) != 0 && (unsigned int)(v154 + 2147024894) <= 1 )
  {
    *((_DWORD *)v116 + 19) = 1;
    *((_WORD *)v116 + 20) = 5;
    if ( v97 == -2147220476 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 404, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      *(_QWORD *)((char *)*v46 + 68) = v162;
      v20 = CNamespaceRecord::Commit(*v46);
      if ( v20 < 0 )
      {
        v114 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_49;
        v115 = 405;
        goto LABEL_236;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 406, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      v118 = *v21;
      v176 = v118;
      if ( v118 )
        ++*((_DWORD *)v118 + 2);
      CSessionBaseRW::ChangeFileRecordStatus(v6 + 8, &v176, 0);
      if ( !v164 )
        *(_DWORD *)(v6 + 560) |= 1 << v165;
    }
    v20 = CFileRecord::Commit(**v21);
    if ( v20 < 0 )
    {
      v111 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_49;
      v112 = 407;
      goto LABEL_225;
    }
LABEL_275:
    v20 = 0;
    goto LABEL_49;
  }
  if ( v154 == -2147220477 || v154 == -2147024596 || v117 && (unsigned int)(v154 + 2147024864) <= 1 )
  {
    lpFileName = 0;
    SystemFunction036(&lpFileName, 8u);
    if ( v154 == -2147220477 || v154 == -2147024596 )
    {
      if ( (unsigned __int64)lpFileName % (int)++*(_DWORD *)(v6 + 1044) )
        goto LABEL_353;
      v139 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
               &v157,
               &v156);
      v140 = v6 + 1056;
    }
    else
    {
      if ( (unsigned __int64)lpFileName % (int)++*(_DWORD *)(v6 + 1048) )
        goto LABEL_353;
      v139 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
               &v157,
               &v156);
      v140 = v6 + 1064;
    }
    FheFileOperations::ExtractTruncatedFileExt(v139, v140);
LABEL_353:
    v141 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 408, v138, v160);
    v142 = **v21;
    if ( (*((_BYTE *)v142 + 42) & 2) != 0 )
    {
      v143 = *((_DWORD *)v142 + 15);
      if ( v143 > 0 && v143 < *(_DWORD *)(v6 + 1032) )
      {
        *(_DWORD *)(v6 + 1036) = v154;
        *(_DWORD *)(v6 + 1032) = *((_DWORD *)**v21 + 15);
        v144 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                 &v157,
                 &v156);
        FheFileOperations::ExtractTruncatedFileExt(v144, v6 + 1024);
      }
    }
    else
    {
      if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(v141, FileWarning_Locked, v19);
      v145 = *v21;
      RandomBuffer = (unsigned __int64)v145;
      if ( v145 )
        ++*((_DWORD *)v145 + 2);
      CSessionBaseRW::ChangeFileRecordStatus(v6 + 8, &RandomBuffer, 0);
    }
    v146 = **v21;
    *((_DWORD *)v146 + 19) = 1;
    *((_WORD *)v146 + 20) = 5;
    v20 = CFileRecord::Commit(**v21);
    if ( v20 >= 0 )
    {
      SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&RandomBuffer);
      if ( v46 )
        v147 = *v46;
      else
        v147 = 0;
      if ( RandomBuffer )
        v148 = *(CNamespaceRecord **)RandomBuffer;
      else
        v148 = 0;
      SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&RandomBuffer);
      if ( v147 == v148 )
        goto LABEL_240;
      *(_QWORD *)((char *)*v46 + 68) = v162;
      v20 = CNamespaceRecord::Commit(*v46);
      if ( v20 >= 0 )
        goto LABEL_240;
      v114 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_49;
      v115 = 410;
LABEL_236:
      WPP_SF_dSd(v114[2], v115, (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, *((_DWORD *)*v46 + 4), v19, v20);
      goto LABEL_49;
    }
    v111 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_49;
    v112 = 409;
    goto LABEL_225;
  }
  if ( v154 != -2147024809 && v154 != -2147024814 )
  {
    if ( v154 == -2147021846 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 413, (unsigned int)v154, v160);
      goto LABEL_275;
    }
    v20 = -2147023661;
    if ( v154 == -2147023661 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 414, (unsigned int)v154, v160);
      goto LABEL_49;
    }
    RandomBuffer = 0;
    ++*(_DWORD *)(v6 + 1040);
    SystemFunction036(&RandomBuffer, 8u);
    v120 = v154;
    if ( !(RandomBuffer % *(int *)(v6 + 1040)) )
      *(_DWORD *)(v6 + 1052) = v154;
    v121 = (unsigned int)v158;
    if ( (_DWORD)v158 && (unsigned int)CBackupSession::IsFailurePermanent((CBackupSession *)(unsigned int)v158, v120) )
    {
      v123 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_ddS(*((_QWORD *)WPP_GLOBAL_Control + 2), v122, v119, v120, *((_DWORD *)**v21 + 4), v19);
      if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(v123, FileFailure_PermanentError, v19, v120);
      v124 = *v21;
      v125 = **v21;
      if ( (unsigned __int16)(*((_WORD *)v125 + 20) - 1) > 1u )
      {
        v176 = *v21;
        ++*((_DWORD *)v124 + 2);
        CSessionBaseRW::DeleteFileVersion((CSessionBaseRW *)(v6 + 8));
        goto LABEL_324;
      }
      if ( v164 )
      {
        v176 = *v21;
        ++*((_DWORD *)v124 + 2);
        CSessionBaseRW::RemoveFileRecord(v6 + 8, &v176, 1, 0);
      }
      else
      {
        *((_DWORD *)v125 + 19) = 1;
        *((_WORD *)v125 + 20) = 5;
        v126 = *v21;
        v176 = v126;
        if ( v126 )
          ++*((_DWORD *)v126 + 2);
        CSessionBaseRW::ChangeFileRecordStatus(v6 + 8, &v176, 0);
        v20 = CFileRecord::Commit(**v21);
        if ( v20 < 0 )
        {
          v111 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_49;
          v112 = 416;
          goto LABEL_225;
        }
        *(_DWORD *)(v6 + 560) |= 1 << v165;
      }
LABEL_324:
      v20 = -2147024784;
      if ( v154 != -2147024784 )
        v20 = 0;
      goto LABEL_49;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      if ( (_DWORD)v121 )
      {
        v127 = "transient";
      }
      else
      {
        v127 = "target";
        if ( !HIDWORD(v158) )
          v127 = "unknown";
      }
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 417, v119, (int)v127, v120);
      v121 = (unsigned int)v158;
    }
    v128 = **v21;
    if ( (*((_BYTE *)v128 + 42) & 2) != 0 )
    {
      if ( !(_DWORD)v121 || (v129 = *((_DWORD *)v128 + 15), v129 <= 0) || v129 >= *(_DWORD *)(v6 + 1032) )
      {
LABEL_313:
        v131 = (void (__fastcall ***)(_QWORD, _QWORD))(v6 + 8);
        if ( v177 && !(_DWORD)v121 && GetFileAttributesW(*(LPCWSTR *)(v6 + 80)) == -1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v132 = GetLastError();
            if ( v132 > 0 )
              v132 = (unsigned __int16)v132 | 0x80070000;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              419,
              &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
              (unsigned int)v132);
          }
          v133 = **v131;
          v134 = GetLastError();
          if ( v134 > 0 )
            v134 = (unsigned __int16)v134 | 0x80070000;
          v133(v131, (unsigned int)v134);
        }
        goto LABEL_324;
      }
      *(_DWORD *)(v6 + 1036) = v120;
      *(_DWORD *)(v6 + 1032) = *((_DWORD *)**v21 + 15);
      v130 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
               &v157,
               &v156);
      FheFileOperations::ExtractTruncatedFileExt(v130, v6 + 1024);
LABEL_312:
      LODWORD(v121) = (_DWORD)v158;
      goto LABEL_313;
    }
    if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 4) != 0 )
      McTemplateU0zq_EventWriteTransfer(v121, FileWarning_TransientError, v19, v120);
    v135 = *v21;
    v161 = v135;
    if ( v135 )
      ++*((_DWORD *)v135 + 2);
    CSessionBaseRW::ChangeFileRecordStatus(v6 + 8, &v161, 0);
    v20 = CFileRecord::Commit(**v21);
    if ( v20 >= 0 )
      goto LABEL_312;
    v111 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_49;
    v112 = 418;
LABEL_225:
    WPP_SF_dSd(v111[2], v112, (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, *((_DWORD *)**v21 + 4), v19, v20);
    goto LABEL_49;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      411,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      (unsigned int)v154);
    v97 = v154;
  }
  *(_DWORD *)(v6 + 372) = 1;
  v136 = **v21;
  if ( (*((_BYTE *)v136 + 42) & 2) != 0 )
  {
    v20 = v151;
    goto LABEL_49;
  }
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 4) != 0 )
    McTemplateU0zq_EventWriteTransfer(v136, FileWarning_TransientError, v19, v97);
  v137 = *v21;
  v176 = v137;
  if ( v137 )
    ++*((_DWORD *)v137 + 2);
  CSessionBaseRW::ChangeFileRecordStatus(v6 + 8, &v176, 0);
  v20 = CFileRecord::Commit(**v21);
  if ( v20 < 0 )
  {
    v111 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v112 = 412;
      goto LABEL_225;
    }
  }
LABEL_49:
  v37 = **v21;
  if ( *((_DWORD *)v37 + 19) )
  {
    v38 = CFileRecord::Commit(v37);
    v39 = v38;
    if ( v38 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          420,
          (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          *((_DWORD *)**v21 + 4),
          v19,
          v38);
      if ( v20 >= 0 )
        v20 = v39;
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v166 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v156 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
  ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&v172);
  SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v170);
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(v21);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180013e14  mov     rax, rsp
0x180013e17  mov     [rax+20h], r9d
0x180013e1b  mov     [rax+18h], r8d
0x180013e1f  mov     [rax+10h], rdx
0x180013e23  mov     [rax+8], rcx
0x180013e27  push    rbx
0x180013e28  push    rsi
0x180013e29  push    rdi
0x180013e2a  push    r12
0x180013e2c  push    r13
0x180013e2e  push    r14
0x180013e30  push    r15
0x180013e32  sub     rsp, 160h
0x180013e39  mov     ebx, r8d
0x180013e3c  mov     r12, rdx
0x180013e3f  mov     [rax-0E8h], rdx
0x180013e46  mov     r14, rcx
0x180013e49  xor     r13d, r13d
0x180013e4c  mov     [rax-70h], r13d
0x180013e50  lea     rcx, [rax-60h]
0x180013e54  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x180013e59  nop
0x180013e5a  mov     [rsp+198h+var_50], r13
0x180013e62  lea     rcx, [rsp+198h+var_B0]
0x180013e6a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013e6f  nop
0x180013e70  lea     rcx, [rsp+198h+var_C8]
0x180013e78  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013e7d  nop
0x180013e7e  lea     rcx, [rsp+198h+var_80]
0x180013e86  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013e8b  nop
0x180013e8c  mov     [rsp+198h+var_98], r13
0x180013e94  mov     [rsp+198h+var_90], r13d
0x180013e9c  mov     [rsp+198h+var_A8], r13
0x180013ea4  mov     dword ptr [rsp+198h+var_B8], r13d
0x180013eac  mov     dword ptr [rsp+198h+var_B8+4], r13d
0x180013eb4  test    ebx, ebx
0x180013eb6  jz      loc_180013FAF
0x180013ebc  lea     rbx, WPP_GLOBAL_Control
0x180013ec3  mov     r11, cs:WPP_GLOBAL_Control
0x180013eca  cmp     r11, rbx
0x180013ecd  jz      short loc_180013F29
0x180013ecf  test    byte ptr [r11+1Ch], 8
0x180013ed4  jz      short loc_180013F29
0x180013ed6  mov     rax, [r12]
0x180013eda  mov     r9, [rax]
0x180013edd  movzx   r8d, word ptr [r9+2Ah]
0x180013ee2  movzx   r10d, word ptr [r9+28h]
0x180013ee7  mov     edx, 179h
0x180013eec  mov     eax, [r9+40h]
0x180013ef0  mov     dword ptr [rsp+198h+var_158], eax
0x180013ef4  mov     eax, [r9+3Ch]
0x180013ef8  mov     dword ptr [rsp+198h+var_160], eax
0x180013efc  mov     eax, [r9+38h]
0x180013f00  mov     dword ptr [rsp+198h+hTemplateFile], eax
0x180013f04  mov     [rsp+198h+dwFlagsAndAttributes], r8d
0x180013f09  mov     [rsp+198h+dwCreationDisposition], r10d
0x180013f0e  mov     r9d, [r9+10h]
0x180013f12  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180013f19  mov     rcx, [r11+10h]
0x180013f1d  call    WPP_SF_ddDddd
0x180013f22  mov     r11, cs:WPP_GLOBAL_Control
0x180013f29  mov     r8, [r12]
0x180013f2d  mov     rax, [r8]
0x180013f30  movzx   ecx, word ptr [rax+28h]
0x180013f34  mov     r15d, 1
0x180013f3a  sub     cx, r15w
0x180013f3e  lea     edi, [r15+1]
0x180013f42  cmp     cx, di
0x180013f45  ja      loc_180014041
0x180013f4b  lea     rdx, [rsp+198h+var_B0]
0x180013f53  mov     rcx, [r8]
0x180013f56  call    ?GetName@CFileRecord@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CFileRecord::GetName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180013f5b  mov     esi, eax
0x180013f5d  mov     [rsp+198h+var_F0], eax
0x180013f64  test    eax, eax
0x180013f66  jns     loc_18001408C
0x180013f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f73  cmp     rcx, rbx
0x180013f76  jz      loc_180014070
0x180013f7c  test    [rcx+1Ch], r15b
0x180013f80  jz      loc_180014070
0x180013f86  mov     rdx, [r12]
0x180013f8a  mov     r9, [rdx]
0x180013f8d  mov     edx, 17Ch
0x180013f92  mov     [rsp+198h+dwCreationDisposition], eax
0x180013f96  mov     r9d, [r9+10h]
0x180013f9a  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180013fa1  mov     rcx, [rcx+10h]
0x180013fa5  call    WPP_SF_dd
0x180013faa  jmp     loc_180014070
0x180013faf  lea     rbx, WPP_GLOBAL_Control
0x180013fb6  mov     r11, cs:WPP_GLOBAL_Control
0x180013fbd  cmp     r11, rbx
0x180013fc0  jz      short loc_18001401B
0x180013fc2  test    byte ptr [r11+1Ch], 8
0x180013fc7  jz      short loc_18001401B
0x180013fc9  mov     rax, [r12]
0x180013fcd  mov     r9, [rax]
0x180013fd0  movzx   ecx, word ptr [r9+2Ah]
0x180013fd5  movzx   r8d, word ptr [r9+28h]
0x180013fda  mov     edx, 17Ah
0x180013fdf  mov     eax, [r9+40h]
0x180013fe3  mov     dword ptr [rsp+198h+var_158], eax
0x180013fe7  mov     eax, [r9+3Ch]
0x180013feb  mov     dword ptr [rsp+198h+var_160], eax
0x180013fef  mov     eax, [r9+38h]
0x180013ff3  mov     dword ptr [rsp+198h+hTemplateFile], eax
0x180013ff7  mov     [rsp+198h+dwFlagsAndAttributes], ecx
0x180013ffb  mov     [rsp+198h+dwCreationDisposition], r8d
0x180014000  mov     r9d, [r9+10h]
0x180014004  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001400b  mov     rcx, [r11+10h]
0x18001400f  call    WPP_SF_ddDddd
0x180014014  mov     r11, cs:WPP_GLOBAL_Control
0x18001401b  mov     r8, [r12]
0x18001401f  mov     rax, [r8]
0x180014022  mov     r15d, 1
0x180014028  cmp     [rax+28h], r15w
0x18001402d  jz      loc_180013F4B
0x180014033  lea     edi, [r15+1]
0x180014037  cmp     [rax+28h], di
0x18001403b  jz      loc_180013F4B
0x180014041  mov     [rsp+198h+var_F0], r13d
0x180014049  cmp     r11, rbx
0x18001404c  jz      short loc_180014070
0x18001404e  test    [r11+1Ch], dil
0x180014052  jz      short loc_180014070
0x180014054  mov     rax, [r8]
0x180014057  movzx   ecx, word ptr [rax+28h]
0x18001405b  mov     r9b, byte ptr [rsp+198h+arg_10]
0x180014063  mov     [rsp+198h+dwCreationDisposition], ecx
0x180014067  mov     rcx, [r11+10h]
0x18001406b  call    WPP_SF_cd
0x180014070  mov     rdi, [rsp+198h+var_B0]
0x180014078  mov     esi, [rsp+198h+var_F0]
0x18001407f  mov     r12, [rsp+198h+var_E8]
0x180014087  jmp     loc_1800143E1
0x18001408c  mov     rax, [r12]
0x180014090  mov     r8, [rax]
0x180014093  mov     ecx, 3
0x180014098  cmp     [r8+28h], cx
0x18001409d  jnz     short loc_180014106
0x18001409f  mov     r8d, [r8+3Ch]
0x1800140a3  mov     [rsp+198h+lpFileName], rax
0x1800140ab  add     [rax+8], r15d
0x1800140af  lea     rcx, [r14+10h]
0x1800140b3  lea     r9, [rsp+198h+var_C8]
0x1800140bb  lea     rdx, [rsp+198h+lpFileName]
0x1800140c3  call    ?ConstructStagingPath@CSessionBaseRO@@IEAAJV?$SmartPtr@VCFileRecord@@@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CSessionBaseRO::ConstructStagingPath(SmartPtr<CFileRecord>,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800140c8  mov     esi, eax
0x1800140ca  mov     [rsp+198h+var_F0], eax
0x1800140d1  test    eax, eax
0x1800140d3  jns     short loc_1800140FC
0x1800140d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140dc  cmp     rcx, rbx
0x1800140df  jz      short loc_180014070
0x1800140e1  test    [rcx+1Ch], r15b
0x1800140e5  jz      short loc_180014070
0x1800140e7  mov     rax, [r12]
0x1800140eb  mov     r9, [rax]
0x1800140ee  mov     edx, 17Dh
0x1800140f3  mov     [rsp+198h+dwCreationDisposition], esi
0x1800140f7  jmp     loc_180013F96
0x1800140fc  mov     rdi, [rsp+198h+var_B0]
0x180014104  jmp     short loc_180014170
0x180014106  mov     rdi, [rsp+198h+var_B0]
0x18001410e  lea     rcx, [rdi-18h]
0x180014112  mov     rax, [rsp+198h+var_C8]
0x18001411a  add     rax, 0FFFFFFFFFFFFFFE8h
0x18001411e  mov     [rsp+198h+RandomBuffer], rax
0x180014126  cmp     rcx, rax
0x180014129  jz      short loc_180014170
0x18001412b  cmp     [rax+10h], r13d
0x18001412f  jl      short loc_18001415C
0x180014131  mov     rax, [rax]
0x180014134  cmp     [rcx], rax
0x180014137  jnz     short loc_18001415C
0x180014139  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001413e  mov     rbx, rax
0x180014141  mov     rcx, [rsp+198h+RandomBuffer]; this
0x180014149  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001414e  lea     rax, [rbx+18h]
0x180014152  mov     [rsp+198h+var_C8], rax
0x18001415a  jmp     short loc_180014170
0x18001415c  mov     r8d, [rdi-10h]
0x180014160  mov     rdx, rdi
0x180014163  lea     rcx, [rsp+198h+var_C8]
0x18001416b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180014170  mov     rax, [rsp+198h+var_C8]
0x180014178  cmp     [rax-10h], r15d
0x18001417c  jle     loc_180014606
0x180014182  xor     edx, edx
0x180014184  lea     rcx, [rsp+198h+var_C8]
0x18001418c  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x180014191  movzx   ecx, ax; C
0x180014194  call    cs:__imp_iswalpha
0x18001419a  test    eax, eax
0x18001419c  jz      loc_180014606
0x1800141a2  mov     edx, r15d
0x1800141a5  lea     rcx, [rsp+198h+var_C8]
0x1800141ad  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x1800141b2  cmp     ax, 3Ah ; ':'
0x1800141b6  jnz     loc_180014606
0x1800141bc  mov     [rsp+198h+var_8C], r13d
0x1800141c4  xor     edx, edx
0x1800141c6  lea     rcx, [rsp+198h+var_C8]
0x1800141ce  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x1800141d3  movzx   ecx, ax; C
0x1800141d6  call    cs:__imp_towupper
0x1800141dc  movzx   edx, ax
0x1800141df  add     edx, 0FFFFFFBFh
0x1800141e2  mov     [rsp+198h+var_88], edx
0x1800141e9  mov     eax, edx
0x1800141eb  add     rax, 47h ; 'G'
0x1800141ef  lea     rax, [r14+rax*8]
0x1800141f3  mov     [rsp+198h+var_78], rax
0x1800141fb  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800141ff  jnz     loc_180014616
0x180014205  mov     ecx, edx
0x180014207  mov     eax, r15d
0x18001420a  shl     eax, cl
0x18001420c  mov     [rsp+198h+var_D8], eax
0x180014213  mov     dword ptr [rsp+198h+var_68], eax
0x18001421a  lea     rcx, [r14+230h]
0x180014221  mov     [rsp+198h+var_D0], rcx
0x180014229  test    [rcx], eax
0x18001422b  jnz     loc_180014616
0x180014231  lea     rcx, [rsp+198h+lpFileName]
0x180014239  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001423e  nop
0x18001423f  mov     r8d, 2
0x180014245  lea     rdx, [rsp+198h+var_58]
0x18001424d  lea     rcx, [rsp+198h+var_C8]
0x180014255  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x18001425a  mov     rbx, rax
0x18001425d  mov     rcx, rax
0x180014260  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x180014265  nop
0x180014266  mov     rdx, rax
0x180014269  lea     rcx, [rsp+198h+var_A0]
0x180014271  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x180014276  nop
0x180014277  mov     [rsp+198h+var_70], r15d
0x18001427f  mov     r9, [rbx]
0x180014282  mov     eax, [r9-10h]
0x180014286  mov     [rsp+198h+dwCreationDisposition], eax
0x18001428a  mov     r8d, 4
0x180014290  lea     rdx, asc_180038B28; "\\\\.\\"
0x180014297  lea     rcx, [rsp+198h+var_A0]
0x18001429f  call    ?Concatenate@?$CSimpleStringT@G$0A@@ATL@@KAXAEAV12@PEBGH1H@Z; ATL::CSimpleStringT<ushort,0>::Concatenate(ATL::CSimpleStringT<ushort,0> &,ushort const *,int,ushort const *,int)
0x1800142a4  mov     rdx, [rsp+198h+var_A0]
0x1800142ac  lea     rcx, [rdx-18h]
0x1800142b0  mov     [rsp+198h+RandomBuffer], rcx
0x1800142b8  mov     rbx, [rsp+198h+lpFileName]
0x1800142c0  lea     rax, [rbx-18h]
0x1800142c4  mov     [rsp+198h+var_48], rax
0x1800142cc  cmp     rcx, rax
0x1800142cf  jz      short loc_180014323
0x1800142d1  cmp     [rax+10h], r13d
0x1800142d5  jl      short loc_180014302
0x1800142d7  mov     rax, [rax]
0x1800142da  cmp     [rcx], rax
0x1800142dd  jnz     short loc_180014302
0x1800142df  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800142e4  mov     rbx, rax
0x1800142e7  mov     rcx, [rsp+198h+var_48]; this
0x1800142ef  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800142f4  add     rbx, 18h
0x1800142f8  mov     [rsp+198h+lpFileName], rbx
0x180014300  jmp     short loc_18001431B
0x180014302  mov     r8d, [rdx-10h]
0x180014306  lea     rcx, [rsp+198h+lpFileName]
0x18001430e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180014313  mov     rbx, [rsp+198h+lpFileName]
0x18001431b  mov     rcx, [rsp+198h+RandomBuffer]; this
0x180014323  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014328  nop
0x180014329  mov     rcx, [rsp+198h+var_58]
0x180014331  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180014335  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001433a  nop
0x18001433b  jmp     short loc_180014388
0x18001433d  xor     r13d, r13d
0x180014340  lea     r15d, [r13+1]
0x180014344  mov     r12, [rsp+198h+arg_8]
0x18001434c  mov     [rsp+198h+var_E8], r12
0x180014354  mov     rdi, [rsp+198h+var_B0]
0x18001435c  mov     esi, [rsp+198h+var_F0]
0x180014363  mov     [rsp+198h+var_F0], esi
0x18001436a  mov     rbx, [rsp+198h+lpFileName]
0x180014372  mov     ecx, dword ptr [rsp+198h+var_68]
0x180014379  mov     [rsp+198h+var_D8], ecx
0x180014380  mov     r14, [rsp+198h+arg_0]
0x180014388  lea     rax, WPP_GLOBAL_Control
0x18001438f  test    esi, esi
0x180014391  jns     loc_1800144A2
0x180014397  mov     rcx, cs:WPP_GLOBAL_Control
0x18001439e  cmp     rcx, rax
  ... truncated ...
```
