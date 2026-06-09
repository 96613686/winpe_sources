# CSessionBaseRW::RefreshParentDirNamespaceRecords(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSessionBaseRW::ParentRefreshType,long)

- ea: `0x18000fde8`
- end: `0x18001083d`
- name: `?RefreshParentDirNamespaceRecords@CSessionBaseRW@@IEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4ParentRefreshType@1@J@Z`
- size: `2645`
- prototype: `__int64 __fastcall(CSessionBaseRW *, _QWORD *, int, int)`
- caller_count: `4`
- callee_count: `26`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000bcd8`
- `0x18000de68`
- `0x18001cb74`
- `0x18001eaf0`

## callees

- `0x1800025b0`
- `0x180002c24`
- `0x1800062d0`
- `0x180007a1c`
- `0x180007d5c`
- `0x180008fa0`
- `0x1800090f8`
- `0x1800091a4`
- `0x180009258`
- `0x1800093a8`
- `0x180009404`
- `0x1800094d0`
- `0x180009528`
- `0x1800095c8`
- `0x18000960c`
- `0x180009920`
- `0x18000a4ac`
- `0x18000baa8`
- `0x18000bca8`
- `0x18000de68`
- `0x18000fde8`
- `0x180012278`
- `0x18001239c`
- `0x1800127b0`
- `0x18003122c`
- `0x180031680`

## import_xrefs

- `msvcrt!iswalpha` at `0x18000fe60`
- `msvcrt!iswalpha` at `0x18000fe60`
- `KERNEL32!GetLastError` at `0x1800104d4`
- `KERNEL32!GetLastError` at `0x1800104ff`
- `KERNEL32!GetLastError` at `0x1800104d4`
- `KERNEL32!GetLastError` at `0x1800104ff`
- `KERNEL32!GetFileAttributesExW` at `0x1800104c6`
- `KERNEL32!GetFileAttributesExW` at `0x1800104c6`

## string_xrefs

- `0x180010764`: `updatedRecord`
- `0x1800103f4`: `Unexpected failure in ReadCurrentUsn`
- `0x180010400`: `hr == HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::RefreshParentDirNamespaceRecords(
        CSessionBaseRW *a1,
        const void **a2,
        int a3,
        int a4)
{
  const void **v5; // r12
  int CurrentUsn; // edi
  wint_t v7; // ax
  volatile signed __int32 *v8; // rcx
  const WCHAR *v9; // rbx
  int *v10; // rsi
  volatile signed __int32 *v11; // rbx
  int v12; // eax
  int v13; // r13d
  char *v14; // rdx
  volatile signed __int32 *v15; // rcx
  int *v16; // rdi
  volatile signed __int32 *v17; // rbx
  __int16 v18; // r13
  int v19; // edi
  unsigned int v20; // eax
  int LastNamespaceRecord; // eax
  BOOL v22; // edx
  _DWORD *v23; // rax
  int v24; // r8d
  CSessionBaseRW *v25; // r10
  int v26; // r9d
  int v27; // edx
  int v28; // edx
  PVOID *v29; // r10
  int v30; // eax
  CNamespaceRecord *v31; // rax
  CSessionBaseRW *v32; // rdi
  int v33; // edx
  CNamespaceRecord *v34; // rdi
  _QWORD *v35; // rax
  int v36; // eax
  CNamespaceRecord **v37; // rax
  CNamespaceRecord *v38; // rdi
  LPCWSTR *v39; // rax
  PVOID *v40; // rcx
  CNamespaceRecord *v41; // rcx
  CNamespaceRecord *v42; // rcx
  __int64 v43; // rax
  signed int LastError; // eax
  PVOID *v45; // rcx
  char v46; // al
  BOOL v47; // r13d
  int v48; // eax
  PVOID *v49; // r10
  CNamespaceRecord **v51; // [rsp+40h] [rbp-D8h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-D0h] BYREF
  _DWORD *v53; // [rsp+50h] [rbp-C8h] BYREF
  int v54; // [rsp+58h] [rbp-C0h]
  int v55; // [rsp+5Ch] [rbp-BCh]
  CSessionBaseRW *v56; // [rsp+60h] [rbp-B8h]
  BOOL v57; // [rsp+68h] [rbp-B0h]
  _DWORD *v58; // [rsp+70h] [rbp-A8h]
  const void **v59; // [rsp+78h] [rbp-A0h]
  int v60; // [rsp+80h] [rbp-98h] BYREF
  __int64 v61; // [rsp+88h] [rbp-90h] BYREF
  __int64 v62; // [rsp+90h] [rbp-88h] BYREF
  __int64 v63; // [rsp+98h] [rbp-80h] BYREF
  __int64 v64; // [rsp+A0h] [rbp-78h] BYREF
  __int128 FileInformation; // [rsp+A8h] [rbp-70h] BYREF
  __int128 v66; // [rsp+B8h] [rbp-60h]
  int v67; // [rsp+C8h] [rbp-50h]

  v54 = a4;
  v55 = a3;
  v5 = a2;
  v56 = a1;
  v59 = a2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
  CurrentUsn = 0;
  if ( *((int *)*v5 - 4) >= 260 )
  {
LABEL_144:
    v9 = lpFileName;
    goto LABEL_154;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( *((int *)*v5 - 4) < 2
      || (v7 = ATL::CSimpleStringT<unsigned short,0>::operator[](v5, 0), !iswalpha(v7))
      || (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::operator[](v5, 1) != 58
      || *((int *)*v5 - 4) >= 3
      && (*((int *)*v5 - 4) <= 3 || (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::operator[](v5, 2) != 92) )
    {
      CurrentUsn = -2147024809;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          (unsigned int)*v5,
          87);
      v9 = lpFileName;
      goto LABEL_154;
    }
    v8 = (volatile signed __int32 *)((char *)*v5 - 24);
    v9 = lpFileName;
    v10 = (int *)(lpFileName - 12);
    if ( v8 != (volatile signed __int32 *)(lpFileName - 12) )
    {
      if ( v10[4] >= 0 && *(_QWORD *)v8 == *(_QWORD *)v10 )
      {
        v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v8);
        ATL::CStringData::Release((ATL::CStringData *)v10);
        v9 = (const WCHAR *)(v11 + 6);
        lpFileName = v9;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)&lpFileName, *v5, *((_DWORD *)*v5 - 4));
        v9 = lpFileName;
      }
    }
    v57 = a3 != 1;
    while ( 1 )
    {
      FileInformation = 0;
      v66 = 0;
      v67 = 0;
      SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v53);
      SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v51);
      v12 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
              &lpFileName,
              92);
      v13 = v12;
      if ( v12 <= 0 )
        goto LABEL_139;
      v14 = (char *)*ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                       &lpFileName,
                       &v61,
                       v12);
      v15 = (volatile signed __int32 *)(v14 - 24);
      v16 = (int *)(v9 - 12);
      if ( v14 - 24 != (char *)(v9 - 12) )
      {
        if ( v16[4] >= 0 && *(_QWORD *)v15 == *(_QWORD *)v16 )
        {
          v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v15);
          ATL::CStringData::Release((ATL::CStringData *)v16);
          v9 = (const WCHAR *)(v17 + 6);
          lpFileName = v9;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)&lpFileName, v14, *((_DWORD *)v14 - 4));
          v9 = lpFileName;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v61 - 24));
      v18 = ATL::CSimpleStringT<unsigned short,0>::operator[](&lpFileName, (unsigned int)(v13 - 1));
      v19 = (int)v56;
      v20 = (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                            &v62,
                            &lpFileName);
      LastNamespaceRecord = CSessionBaseRO::GetLastNamespaceRecord(v19 + 8, v20, (int)&v53, 0, 1);
      CurrentUsn = LastNamespaceRecord;
      if ( LastNamespaceRecord < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            70,
            (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (_DWORD)v9,
            LastNamespaceRecord);
        goto LABEL_139;
      }
      v22 = 0;
      v23 = v53;
      if ( !v53 )
        goto LABEL_31;
      if ( *(_QWORD *)v53 && v57 )
        v22 = (*(_BYTE *)(*(_QWORD *)v53 + 40LL) & 4) != 0;
      if ( *(_QWORD *)v53 )
      {
        v24 = v55;
      }
      else
      {
LABEL_31:
        v24 = v55;
        if ( v55 == 3 )
        {
          v25 = v56;
          goto LABEL_33;
        }
      }
      if ( !v53 )
        goto LABEL_139;
      if ( *(_QWORD *)v53 && v24 == 1 && (v22 || (*(_BYTE *)(*(_QWORD *)v53 + 40LL) & 0x20) != 0) )
        goto LABEL_38;
      if ( !*(_QWORD *)v53 || (unsigned int)(v24 - 2) > 1 )
        goto LABEL_139;
      v25 = v56;
      if ( !v22 )
      {
        v28 = v54;
        if ( !v54 )
          v28 = *((_DWORD *)v56 + 9);
        if ( *(_DWORD *)(*(_QWORD *)v53 + 76LL) >= v28 )
          goto LABEL_139;
      }
      if ( v24 == 1 )
      {
LABEL_38:
        SmartPtr<CNamespaceRecord>::operator=(&v51, &v53);
        goto LABEL_96;
      }
      if ( (unsigned int)(v24 - 2) > 1 )
      {
        v26 = v54;
        goto LABEL_54;
      }
LABEL_33:
      v26 = v54;
      if ( !v53 )
        goto LABEL_68;
      if ( *(_QWORD *)v53 )
      {
        v27 = v54;
        if ( !v54 )
          v27 = *((_DWORD *)v25 + 9);
        if ( *(_DWORD *)(*(_QWORD *)v53 + 76LL) >= v27 )
          goto LABEL_38;
      }
LABEL_54:
      if ( *(_QWORD *)v53 )
      {
        if ( (*(_BYTE *)(*(_QWORD *)v53 + 40LL) & 2) == 0 && v24 != 3 )
        {
          v29 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v9);
              v23 = v53;
              v29 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 2) != 0 )
              WPP_SF_dDddi(
                v29[2],
                73,
                &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
                *(unsigned int *)(*(_QWORD *)v23 + 16LL),
                *(unsigned __int16 *)(*(_QWORD *)v23 + 40LL),
                *(_DWORD *)(*(_QWORD *)v23 + 76LL),
                *(_DWORD *)(*(_QWORD *)v23 + 80LL),
                *(_QWORD *)(*(_QWORD *)v23 + 48LL));
          }
          goto LABEL_139;
        }
        v58 = v53;
        ++v53[2];
        v30 = CSessionBaseRW::FinalizeNamespaceRecord(v56, v26);
        CurrentUsn = v30;
        if ( v30 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              71,
              (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
              (_DWORD)v9,
              v30);
          goto LABEL_139;
        }
      }
LABEL_68:
      v31 = (CNamespaceRecord *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
      v32 = v56;
      if ( v31 )
        v31 = CNamespaceRecord::CNamespaceRecord(v31, (__int64 *)v56 + 2, (__int64)v56 + 24);
      SmartPtr<CNamespaceRecord>::operator=(&v51, v31);
      if ( !v51 || !*v51 )
      {
        CurrentUsn = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            74,
            &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            "updatedRecord");
LABEL_139:
        SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v51);
        SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v53);
        goto LABEL_154;
      }
      v33 = v54;
      if ( !v54 )
        v33 = *((_DWORD *)v32 + 9);
      *((_DWORD *)*v51 + 19) = v33;
      *((_DWORD *)*v51 + 20) = -1;
      *((_WORD *)*v51 + 20) = 6;
      v34 = *v51;
      v35 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v63,
              &lpFileName);
      v36 = CNamespaceRecord::SetName(v34, v35);
      CurrentUsn = v36;
      if ( v36 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            75,
            (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (_DWORD)v9,
            v36);
        goto LABEL_139;
      }
      v37 = v51;
      if ( v18 == 58 )
        goto LABEL_95;
      v38 = *v51;
      v39 = (LPCWSTR *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                         &v64,
                         &lpFileName);
      CurrentUsn = FheFileOperations::ReadCurrentUsn((HANDLE)0xFFFFFFFFFFFFFFFFLL, v39, (_QWORD *)v38 + 6);
      if ( (unsigned int)(CurrentUsn + 2147024894) <= 1 )
      {
        v37 = v51;
        CurrentUsn = 0;
LABEL_95:
        *((_QWORD *)*v37 + 6) = 0;
        goto LABEL_96;
      }
      if ( CurrentUsn < 0 )
      {
        if ( CurrentUsn != -2147024891 )
        {
          v40 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          {
LABEL_93:
            CurrentUsn = 0;
            goto LABEL_139;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
LABEL_87:
            if ( v40 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v40 + 28) & 2) != 0 )
              {
                WPP_SF_Sd(
                  (unsigned int)v40[2],
                  77,
                  (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
                  (_DWORD)v9,
                  CurrentUsn);
                v40 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v40 != &WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 2) != 0 )
                WPP_SF_S(v40[2], 78, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v9);
            }
            goto LABEL_93;
          }
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            76,
            (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (unsigned int)"hr == HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)",
            (__int64)"Unexpected failure in ReadCurrentUsn");
        }
        v40 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_87;
      }
LABEL_96:
      v41 = *v51;
      if ( (*((_BYTE *)*v51 + 40) & 2) == 0 )
        goto LABEL_139;
      if ( v18 == 58 )
        goto LABEL_98;
      if ( GetFileAttributesExW(v9, GetFileExInfoStandard, &FileInformation) )
      {
        *((_DWORD *)*v51 + 14) = FileInformation;
        *(_QWORD *)((char *)*v51 + 60) = *(_QWORD *)((char *)&FileInformation + 4);
        v42 = *v51;
        v43 = *(_QWORD *)((char *)&v66 + 4);
        goto LABEL_118;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError != -2147024894 )
      {
        v45 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_110;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v46 = GetLastError();
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (_DWORD)v9,
            v46);
          v45 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v45 == &WPP_GLOBAL_Control || (*((_BYTE *)v45 + 28) & 2) == 0 )
          goto LABEL_110;
        WPP_SF_S(v45[2], 80, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v9);
      }
      v45 = (PVOID *)WPP_GLOBAL_Control;
LABEL_110:
      if ( !v53 || !*(_QWORD *)v53 )
      {
        if ( v45 != &WPP_GLOBAL_Control && (*((_BYTE *)v45 + 28) & 2) != 0 )
          WPP_SF_S(v45[2], 81, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v9);
        v41 = *v51;
LABEL_98:
        *((_DWORD *)v41 + 14) = 16;
        *(_QWORD *)((char *)*v51 + 60) = 0;
        v42 = *v51;
        v43 = 0;
        goto LABEL_118;
      }
      *((_DWORD *)*v51 + 14) = *(_DWORD *)(*(_QWORD *)v53 + 56LL);
      *(_QWORD *)((char *)*v51 + 60) = *(_QWORD *)(*(_QWORD *)v53 + 60LL);
      v42 = *v51;
      v43 = *(_QWORD *)(*(_QWORD *)v53 + 68LL);
LABEL_118:
      *(_QWORD *)((char *)v42 + 68) = v43;
      *((_WORD *)*v51 + 20) &= ~0x20u;
      v47 = v57;
      if ( v57 )
        *((_WORD *)*v51 + 20) &= ~4u;
      v48 = CNamespaceRecord::Commit(*v51);
      CurrentUsn = v48;
      if ( v48 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            82,
            (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (_DWORD)v9,
            v48);
        goto LABEL_139;
      }
      v49 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v9);
          v49 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v49 != &WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 8) != 0 )
          WPP_SF_dDddi(
            v49[2],
            84,
            &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            *((unsigned int *)*v51 + 4),
            *((unsigned __int16 *)*v51 + 20),
            *((_DWORD *)*v51 + 19),
            *((_DWORD *)*v51 + 20),
            *((_QWORD *)*v51 + 6));
      }
      if ( v53 )
      {
        if ( *(_QWORD *)v53 )
          v47 = 0;
        v57 = v47;
      }
      SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v51);
      SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v53);
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v60) )
    {
      v55 = v60;
      if ( v60 >= 0 )
      {
        v5 = v59;
        CurrentUsn = v55;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800107F3);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            85,
            &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (unsigned int)v60);
        v5 = v59;
        CurrentUsn = v55;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800107F1);
      }
      goto LABEL_144;
    }
  }
LABEL_154:
  ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
  ATL::CStringData::Release((ATL::CStringData *)((char *)*v5 - 24));
  return (unsigned int)CurrentUsn;
}

```

## disassembly

```asm
0x18000fde8  push    rbx
0x18000fdea  push    rsi
0x18000fdeb  push    rdi
0x18000fdec  push    r12
0x18000fdee  push    r13
0x18000fdf0  push    r14
0x18000fdf2  push    r15
0x18000fdf4  sub     rsp, 0E0h
0x18000fdfb  mov     rax, cs:__security_cookie
0x18000fe02  xor     rax, rsp
0x18000fe05  mov     [rsp+118h+var_48], rax
0x18000fe0d  mov     [rsp+118h+var_C0], r9d
0x18000fe12  mov     r14d, r8d
0x18000fe15  mov     [rsp+118h+var_BC], r8d
0x18000fe1a  mov     r12, rdx
0x18000fe1d  mov     [rsp+118h+var_B8], rcx
0x18000fe22  mov     [rsp+118h+var_A0], rdx
0x18000fe27  lea     rcx, [rsp+118h+lpFileName]
0x18000fe2c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000fe31  nop
0x18000fe32  xor     edi, edi
0x18000fe34  mov     rax, [r12]
0x18000fe38  cmp     dword ptr [rax-10h], 104h
0x18000fe3f  jge     loc_1800107FC
0x18000fe45  mov     rax, [r12]
0x18000fe49  cmp     dword ptr [rax-10h], 2
0x18000fe4d  jl      loc_1800107A8
0x18000fe53  xor     edx, edx
0x18000fe55  mov     rcx, r12
0x18000fe58  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x18000fe5d  movzx   ecx, ax; C
0x18000fe60  call    cs:__imp_iswalpha
0x18000fe66  test    eax, eax
0x18000fe68  jz      loc_1800107A8
0x18000fe6e  lea     r15d, [rdi+1]
0x18000fe72  mov     edx, r15d
0x18000fe75  mov     rcx, r12
0x18000fe78  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x18000fe7d  cmp     ax, 3Ah ; ':'
0x18000fe81  jnz     loc_1800107AE
0x18000fe87  mov     rax, [r12]
0x18000fe8b  cmp     dword ptr [rax-10h], 3
0x18000fe8f  jl      short loc_18000FEB2
0x18000fe91  jle     loc_1800107AE
0x18000fe97  lea     edx, [rdi+2]
0x18000fe9a  mov     rcx, r12
0x18000fe9d  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x18000fea2  lea     r13d, [rdi+5Ch]
0x18000fea6  cmp     ax, r13w
0x18000feaa  jnz     loc_1800107AE
0x18000feb0  jmp     short loc_18000FEB8
0x18000feb2  mov     r13d, 5Ch ; '\'
0x18000feb8  mov     rdx, [r12]
0x18000febc  lea     rcx, [rdx-18h]
0x18000fec0  mov     rbx, [rsp+118h+lpFileName]
0x18000fec5  lea     rsi, [rbx-18h]
0x18000fec9  cmp     rcx, rsi
0x18000fecc  jz      short loc_18000FF0A
0x18000fece  cmp     dword ptr [rsi+10h], 0
0x18000fed2  jl      short loc_18000FEF7
0x18000fed4  mov     rax, [rsi]
0x18000fed7  cmp     [rcx], rax
0x18000feda  jnz     short loc_18000FEF7
0x18000fedc  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000fee1  mov     rbx, rax
0x18000fee4  mov     rcx, rsi; this
0x18000fee7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000feec  add     rbx, 18h
0x18000fef0  mov     [rsp+118h+lpFileName], rbx
0x18000fef5  jmp     short loc_18000FF0A
0x18000fef7  mov     r8d, [rdx-10h]
0x18000fefb  lea     rcx, [rsp+118h+lpFileName]
0x18000ff00  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000ff05  mov     rbx, [rsp+118h+lpFileName]
0x18000ff0a  xor     eax, eax
0x18000ff0c  cmp     r14d, r15d
0x18000ff0f  setnz   al
0x18000ff12  mov     [rsp+118h+var_B0], eax
0x18000ff16  lea     rsi, WPP_GLOBAL_Control
0x18000ff1d  lea     r14, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000ff24  xorps   xmm0, xmm0
0x18000ff27  xor     eax, eax
0x18000ff29  movups  [rsp+118h+FileInformation], xmm0
0x18000ff31  movups  [rsp+118h+var_60], xmm0
0x18000ff39  mov     [rsp+118h+var_50], eax
0x18000ff40  lea     rcx, [rsp+118h+var_C8]
0x18000ff45  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18000ff4a  nop
0x18000ff4b  lea     rcx, [rsp+118h+var_D8]
0x18000ff50  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18000ff55  nop
0x18000ff56  mov     edx, r13d
0x18000ff59  lea     rcx, [rsp+118h+lpFileName]
0x18000ff5e  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x18000ff63  mov     r13d, eax
0x18000ff66  test    eax, eax
0x18000ff68  jle     loc_180010790
0x18000ff6e  mov     r8d, eax
0x18000ff71  lea     rdx, [rsp+118h+var_90]
0x18000ff79  lea     rcx, [rsp+118h+lpFileName]
0x18000ff7e  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x18000ff83  nop
0x18000ff84  mov     rdx, [rax]
0x18000ff87  lea     rcx, [rdx-18h]
0x18000ff8b  lea     rdi, [rbx-18h]
0x18000ff8f  cmp     rcx, rdi
0x18000ff92  jz      short loc_18000FFD0
0x18000ff94  cmp     dword ptr [rdi+10h], 0
0x18000ff98  jl      short loc_18000FFBD
0x18000ff9a  mov     rax, [rdi]
0x18000ff9d  cmp     [rcx], rax
0x18000ffa0  jnz     short loc_18000FFBD
0x18000ffa2  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000ffa7  mov     rbx, rax
0x18000ffaa  mov     rcx, rdi; this
0x18000ffad  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000ffb2  add     rbx, 18h
0x18000ffb6  mov     [rsp+118h+lpFileName], rbx
0x18000ffbb  jmp     short loc_18000FFD0
0x18000ffbd  mov     r8d, [rdx-10h]
0x18000ffc1  lea     rcx, [rsp+118h+lpFileName]
0x18000ffc6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000ffcb  mov     rbx, [rsp+118h+lpFileName]
0x18000ffd0  mov     rcx, [rsp+118h+var_90]
0x18000ffd8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000ffdc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000ffe1  lea     edx, [r13-1]
0x18000ffe5  lea     rcx, [rsp+118h+lpFileName]
0x18000ffea  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x18000ffef  movzx   r13d, ax
0x18000fff3  mov     rdi, [rsp+118h+var_B8]
0x18000fff8  lea     rdx, [rsp+118h+lpFileName]
0x18000fffd  lea     rcx, [rsp+118h+var_88]
0x180010005  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001000a  mov     dword ptr [rsp+118h+var_F8], r15d
0x18001000f  xor     r9d, r9d
0x180010012  lea     r8, [rsp+118h+var_C8]
0x180010017  mov     rdx, rax
0x18001001a  lea     rcx, [rdi+8]
0x18001001e  call    ?GetLastNamespaceRecord@CSessionBaseRO@@IEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$SmartPtr@VCNamespaceRecord@@@@HH@Z; CSessionBaseRO::GetLastNamespaceRecord(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CNamespaceRecord> &,int,int)
0x180010023  mov     edi, eax
0x180010025  xor     r11d, r11d
0x180010028  test    eax, eax
0x18001002a  jns     short loc_180010071
0x18001002c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010033  cmp     rcx, rsi
0x180010036  jz      short loc_180010056
0x180010038  test    [rcx+1Ch], r15b
0x18001003c  jz      short loc_180010056
0x18001003e  lea     edx, [r11+46h]
0x180010042  mov     dword ptr [rsp+118h+var_F8], eax
0x180010046  mov     r9, rbx
0x180010049  mov     r8, r14
0x18001004c  mov     rcx, [rcx+10h]
0x180010050  call    WPP_SF_Sd
0x180010055  nop
0x180010056  lea     rcx, [rsp+118h+var_D8]
0x18001005b  call    ??1?$SmartPtr@VCNamespaceRecord@@@@QEAA@XZ; SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(void)
0x180010060  nop
0x180010061  lea     rcx, [rsp+118h+var_C8]
0x180010066  call    ??1?$SmartPtr@VCNamespaceRecord@@@@QEAA@XZ; SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(void)
0x18001006b  nop
0x18001006c  jmp     loc_180010801
0x180010071  mov     edx, r11d
0x180010074  mov     rax, [rsp+118h+var_C8]
0x180010079  test    rax, rax
0x18001007c  jz      short loc_18001009F
0x18001007e  cmp     [rax], r11
0x180010081  jz      short loc_180010095
0x180010083  cmp     [rsp+118h+var_B0], r11d
0x180010088  jz      short loc_180010095
0x18001008a  mov     rcx, [rax]
0x18001008d  test    byte ptr [rcx+28h], 4
0x180010091  cmovnz  edx, r15d
0x180010095  test    rax, rax
0x180010098  jz      short loc_18001009F
0x18001009a  cmp     [rax], r11
0x18001009d  jnz     short loc_1800100F2
0x18001009f  mov     r8d, [rsp+118h+var_BC]
0x1800100a4  cmp     r8d, 3
0x1800100a8  jnz     short loc_1800100F7
0x1800100aa  mov     r10, [rsp+118h+var_B8]
0x1800100af  mov     r9d, [rsp+118h+var_C0]
0x1800100b4  test    rax, rax
0x1800100b7  jz      loc_180010297
0x1800100bd  cmp     [rax], r11
0x1800100c0  jz      loc_180010170
0x1800100c6  test    r9d, r9d
0x1800100c9  mov     edx, r9d
0x1800100cc  jnz     short loc_1800100D2
0x1800100ce  mov     edx, [r10+24h]
0x1800100d2  mov     rcx, [rax]
0x1800100d5  cmp     [rcx+4Ch], edx
0x1800100d8  jl      loc_180010170
0x1800100de  lea     rdx, [rsp+118h+var_C8]
0x1800100e3  lea     rcx, [rsp+118h+var_D8]
0x1800100e8  call    ??4?$SmartPtr@VCNamespaceRecord@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<CNamespaceRecord>::operator=(SmartPtr<CNamespaceRecord> const &)
0x1800100ed  jmp     loc_18001047C
0x1800100f2  mov     r8d, [rsp+118h+var_BC]
0x1800100f7  test    rax, rax
0x1800100fa  jz      loc_180010790
0x180010100  cmp     [rax], r11
0x180010103  jz      short loc_180010117
0x180010105  cmp     r8d, r15d
0x180010108  jnz     short loc_180010117
0x18001010a  test    edx, edx
0x18001010c  jnz     short loc_1800100DE
0x18001010e  mov     rcx, [rax]
0x180010111  test    byte ptr [rcx+28h], 20h
0x180010115  jnz     short loc_1800100DE
0x180010117  test    rax, rax
0x18001011a  jz      loc_180010790
0x180010120  cmp     [rax], r11
0x180010123  jz      loc_180010790
0x180010129  lea     ecx, [r8-2]
0x18001012d  cmp     ecx, r15d
0x180010130  ja      loc_180010790
0x180010136  mov     r10, [rsp+118h+var_B8]
0x18001013b  test    edx, edx
0x18001013d  jnz     short loc_180010159
0x18001013f  mov     ecx, [rsp+118h+var_C0]
0x180010143  test    ecx, ecx
0x180010145  mov     edx, ecx
0x180010147  jnz     short loc_18001014D
0x180010149  mov     edx, [r10+24h]
0x18001014d  mov     rcx, [rax]
0x180010150  cmp     [rcx+4Ch], edx
0x180010153  jge     loc_180010790
0x180010159  cmp     r8d, r15d
0x18001015c  jz      short loc_1800100DE
0x18001015e  lea     ecx, [r8-2]
0x180010162  cmp     ecx, r15d
0x180010165  jbe     loc_1800100AF
0x18001016b  mov     r9d, [rsp+118h+var_C0]
0x180010170  test    rax, rax
0x180010173  jz      loc_180010297
0x180010179  cmp     [rax], r11
0x18001017c  jz      loc_180010297
0x180010182  mov     rcx, [rax]
0x180010185  test    byte ptr [rcx+28h], 2
0x180010189  jnz     loc_180010223
0x18001018f  cmp     r8d, 3
0x180010193  jz      loc_180010223
0x180010199  mov     r10, cs:WPP_GLOBAL_Control
0x1800101a0  cmp     r10, rsi
0x1800101a3  jz      loc_180010790
0x1800101a9  test    byte ptr [r10+1Ch], 2
0x1800101ae  jz      short loc_1800101D0
0x1800101b0  mov     edx, 48h ; 'H'
0x1800101b5  mov     r9, rbx
0x1800101b8  mov     r8, r14
0x1800101bb  mov     rcx, [r10+10h]
0x1800101bf  call    WPP_SF_S
0x1800101c4  mov     rax, [rsp+118h+var_C8]
0x1800101c9  mov     r10, cs:WPP_GLOBAL_Control
0x1800101d0  cmp     r10, rsi
0x1800101d3  jz      loc_180010790
0x1800101d9  test    byte ptr [r10+1Ch], 2
0x1800101de  jz      loc_180010790
0x1800101e4  mov     r9, [rax]
0x1800101e7  movzx   ecx, word ptr [r9+28h]
0x1800101ec  mov     edx, 49h ; 'I'
0x1800101f1  mov     rax, [r9+30h]
0x1800101f5  mov     [rsp+118h+var_E0], rax
0x1800101fa  mov     eax, [r9+50h]
0x1800101fe  mov     [rsp+118h+var_E8], eax
0x180010202  mov     eax, [r9+4Ch]
0x180010206  mov     [rsp+118h+var_F0], eax
0x18001020a  mov     dword ptr [rsp+118h+var_F8], ecx
0x18001020e  mov     r9d, [r9+10h]
0x180010212  mov     r8, r14
0x180010215  mov     rcx, [r10+10h]
0x180010219  call    WPP_SF_dDddi
0x18001021e  jmp     loc_180010790
0x180010223  mov     [rsp+118h+var_A8], rax
0x180010228  test    rax, rax
0x18001022b  jz      short loc_180010231
0x18001022d  add     [rax+8], r15d
0x180010231  mov     dword ptr [rsp+118h+var_F8], r9d
0x180010236  xor     r9d, r9d
0x180010239  xor     r8d, r8d
0x18001023c  lea     rdx, [rsp+118h+var_A8]
0x180010241  mov     rcx, [rsp+118h+var_B8]
0x180010246  call    ?FinalizeNamespaceRecord@CSessionBaseRW@@IEAAJV?$SmartPtr@VCNamespaceRecord@@@@HW4ParentRefreshType@1@J@Z; CSessionBaseRW::FinalizeNamespaceRecord(SmartPtr<CNamespaceRecord>,int,CSessionBaseRW::ParentRefreshType,long)
0x18001024b  mov     edi, eax
0x18001024d  test    eax, eax
0x18001024f  jns     short loc_180010297
0x180010251  mov     rcx, cs:WPP_GLOBAL_Control
0x180010258  cmp     rcx, rsi
0x18001025b  jz      short loc_18001027C
0x18001025d  test    [rcx+1Ch], r15b
0x180010261  jz      short loc_18001027C
0x180010263  mov     edx, 47h ; 'G'
0x180010268  mov     dword ptr [rsp+118h+var_F8], eax
0x18001026c  mov     r9, rbx
0x18001026f  mov     r8, r14
0x180010272  mov     rcx, [rcx+10h]
0x180010276  call    WPP_SF_Sd
0x18001027b  nop
0x18001027c  lea     rcx, [rsp+118h+var_D8]
  ... truncated ...
```
