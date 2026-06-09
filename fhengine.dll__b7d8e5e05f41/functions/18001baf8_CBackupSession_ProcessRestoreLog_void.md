# CBackupSession::ProcessRestoreLog(void)

- ea: `0x18001baf8`
- end: `0x18001c70c`
- name: `?ProcessRestoreLog@CBackupSession@@AEAAJXZ`
- size: `3092`
- prototype: `__int64 __fastcall(CBackupSession *__hidden this)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001fee4`

## callees

- `0x180002524`
- `0x1800025b0`
- `0x180002c24`
- `0x1800062d0`
- `0x180006914`
- `0x1800077f0`
- `0x180007818`
- `0x180007a1c`
- `0x180007a9c`
- `0x180007d5c`
- `0x1800090f8`
- `0x1800091a4`
- `0x180009258`
- `0x18000935c`
- `0x1800093a8`
- `0x180009404`
- `0x1800094d0`
- `0x1800094ec`
- `0x180009528`
- `0x18000960c`
- `0x18000a2f8`
- `0x18000a4ac`
- `0x18000bcd8`
- `0x18000d348`
- `0x180010d48`
- `0x180012418`
- `0x1800124a0`
- `0x180012520`
- `0x1800127b0`
- `0x18001baf8`
- `0x180031642`
- `0x180034010`

## import_xrefs

- `msvcrt!fclose` at `0x18001c674`
- `msvcrt!fclose` at `0x18001c674`
- `msvcrt!swscanf_s` at `0x18001c000`
- `msvcrt!swscanf_s` at `0x18001c000`
- `msvcrt!wcschr` at `0x18001bf74`
- `msvcrt!wcschr` at `0x18001bf74`
- `msvcrt!fgetws` at `0x18001bf20`
- `msvcrt!fgetws` at `0x18001bf20`
- `msvcrt!feof` at `0x18001be6d`
- `msvcrt!feof` at `0x18001be6d`
- `msvcrt!_errno` at `0x18001bcd5`
- `msvcrt!_errno` at `0x18001bcd5`
- `msvcrt!_wfopen` at `0x18001bca1`
- `msvcrt!_wfopen` at `0x18001bca1`
- `msvcrt!wcsrchr` at `0x18001bf5d`
- `msvcrt!wcsrchr` at `0x18001bf5d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c687`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c695`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c687`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c695`
- `KERNEL32!GetLastError` at `0x18001bb69`
- `KERNEL32!GetLastError` at `0x18001bb69`
- `KERNEL32!CloseHandle` at `0x18001bd4f`
- `KERNEL32!CloseHandle` at `0x18001bd4f`
- `KERNEL32!CreateFileW` at `0x18001bb52`
- `KERNEL32!CreateFileW` at `0x18001bb52`
- `KERNEL32!DeleteFileW` at `0x18001bc50`
- `KERNEL32!DeleteFileW` at `0x18001bd38`
- `KERNEL32!DeleteFileW` at `0x18001bc50`
- `KERNEL32!DeleteFileW` at `0x18001bd38`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c5f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c5f6`

## string_xrefs

- `0x18001bc29`: `Restore Log is expected to be accessible during backup cycles`
- `0x18001bd11`: `Restore Log is expected to be accessible during backup cycles`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CBackupSession::ProcessRestoreLog(CBackupSession *this)
{
  CBackupSession *v1; // r13
  unsigned int v2; // esi
  HANDLE FileW; // rax
  signed int LastError; // eax
  __int64 v5; // r9
  PVOID *v6; // rcx
  PVOID *v7; // rcx
  PVOID *v8; // rcx
  int *v9; // rax
  void *v10; // rcx
  wchar_t *v11; // rbx
  unsigned __int16 *v12; // rbx
  int v13; // r14d
  unsigned __int16 *v14; // rdi
  unsigned __int64 v15; // rdi
  wchar_t *v16; // rax
  wchar_t *v17; // rcx
  bool v18; // cf
  unsigned int v19; // eax
  int FileRecord; // eax
  _QWORD *v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // eax
  int LastNamespaceRecord; // eax
  _QWORD *v27; // rcx
  int v28; // edx
  OLECHAR *v29; // rbx
  _DWORD *v30; // rdx
  CNamespaceRecord *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 v34; // rax
  int v35; // eax
  int NewBackupSet; // eax
  __int64 v37; // r14
  _QWORD *v38; // rax
  __int64; // rax
  HANDLE hTemplateFile; // [rsp+30h] [rbp-E8h]
  unsigned __int16 *v41; // [rsp+60h] [rbp-B8h]
  OLECHAR *v42; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+70h] [rbp-A8h] BYREF
  int v44; // [rsp+78h] [rbp-A0h] BYREF
  int v45; // [rsp+7Ch] [rbp-9Ch] BYREF
  int v46; // [rsp+80h] [rbp-98h] BYREF
  __int64 v47; // [rsp+88h] [rbp-90h] BYREF
  __int64 v48; // [rsp+90h] [rbp-88h] BYREF
  FILE *Stream; // [rsp+98h] [rbp-80h]
  wchar_t *v50; // [rsp+A0h] [rbp-78h]
  _QWORD *v51; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-68h] BYREF
  int v53; // [rsp+B8h] [rbp-60h] BYREF
  int v54; // [rsp+BCh] [rbp-5Ch] BYREF
  _BYTE v55[8]; // [rsp+C0h] [rbp-58h] BYREF
  CBackupSession *v56; // [rsp+C8h] [rbp-50h]
  _BYTE v57[72]; // [rsp+D0h] [rbp-48h] BYREF
  __int64 (__fastcall *v59)(__int64, _QWORD, char *, __int64); // [rsp+128h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+130h] [rbp+18h] BYREF
  int v61; // [rsp+138h] [rbp+20h]

  v1 = this;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v43);
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v51);
  v2 = 0;
  FileW = CreateFileW(*((LPCWSTR *)v1 + 15), 0x80000000, 5u, 0, 3u, 0x200080u, 0);
  *((_QWORD *)v1 + 51) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v5 = (unsigned int)LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)(v5 + 2147024894) <= 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
    }
    else if ( (_DWORD)v5 == -2147024864 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      v2 = -2147220475;
LABEL_133:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
        WPP_SF_s(
          v6[2],
          208,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          "SUCCEEDED(hr) || hr == FHE_E_SESSION_CANCELLED");
    }
    else
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 187, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v5);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
          WPP_SF_ss(
            (int)v7[2],
            188,
            (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            (int)"FALSE",
            (__int64)"Restore Log is expected to be accessible during backup cycles");
      }
      DeleteFileW(*((LPCWSTR *)v1 + 15));
    }
    goto LABEL_136;
  }
  Stream = _wfopen(*((const wchar_t **)v1 + 15), L"rb");
  if ( !Stream )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = _errno();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          189,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)*v9);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
        WPP_SF_ss(
          (int)v8[2],
          190,
          (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (int)"FALSE",
          (__int64)"Restore Log is expected to be accessible during backup cycles");
    }
    DeleteFileW(*((LPCWSTR *)v1 + 15));
    v10 = (void *)*((_QWORD *)v1 + 51);
    if ( v10 != (void *)-1LL )
    {
      CloseHandle(v10);
      *((_QWORD *)v1 + 51) = -1;
    }
    goto LABEL_136;
  }
  v11 = (wchar_t *)operator new[](0x200C0u, (const struct std::nothrow_t *)&std::nothrow);
  v50 = v11;
  if ( !v11 )
  {
    v12 = 0;
    v13 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, "logString");
    goto LABEL_126;
  }
  v14 = (unsigned __int16 *)operator new[](0x20002u, (const struct std::nothrow_t *)&std::nothrow);
  v41 = v14;
  if ( !v14 )
  {
    v13 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        192,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        "fileNameBuffer");
      goto LABEL_125;
    }
    v12 = 0;
    goto LABEL_126;
  }
  v56 = v1;
  v61 = 0;
  while ( !feof(Stream) )
  {
    v44 = 0;
    v45 = 0;
    LODWORD(v59) = 0;
    v46 = 0;
    v52 = 0;
    v47 = 0;
    v48 = 0;
    if ( *((_DWORD *)v1 + 40) )
    {
      *((_DWORD *)v1 + 38) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      v13 = -2147220479;
      goto LABEL_125;
    }
    memset_0(v11, 0, 0x200C0u);
    memset_0(v14, 0, 0x20002u);
    fgetws(v11, 65631, Stream);
    v15 = -1;
    do
      ++v15;
    while ( v11[v15] );
    if ( v15
      && (v11[v15 - 1] != 10 || (v11[v15 - 1] = 0, --v15, v15))
      && wcsrchr(v11, 0x3Cu) == v11
      && (v16 = wcschr(v11, 0x3Eu), v17 = &v11[v15 - 1], v16 == v17) )
    {
      v18 = v15 < 2;
      v14 = v41;
      if ( !v18 )
      {
        *v17 = 0;
        LODWORD(hTemplateFile) = 65537;
        if ( swscanf_s(
               v11 + 1,
               L"%x %x %x %s %I64x %x %I64x %I64x",
               &v44,
               &v45,
               &v59,
               v41,
               hTemplateFile,
               &v52,
               &v46,
               &v47,
               &v48) == 8
          && v44 == 1
          && v45 > *((_DWORD *)v1 + 15) )
        {
          v19 = ocslen(v41);
          if ( __eh34_try(-1, 0) )
          {
            __eh34_scope_strut(0);
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v43, v41, v19);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
              &v43,
              42,
              32);
          }
          if ( __eh34_catch(0) )
          {
            if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v53) )
            {
              LODWORD(bstrString) = v53;
              if ( v53 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    194,
                    &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                    (unsigned int)v53);
                v13 = (int)bstrString;
                __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001C05D);
                goto LABEL_125;
              }
              v1 = this;
              v14 = v41;
              v11 = v50;
              __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001C076);
              goto LABEL_59;
            }
          }
          LODWORD(bstrString) = 0;
LABEL_59:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              195,
              (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
              (int)v59,
              (__int64)v14);
          if ( (int)bstrString >= 0 )
          {
            FileRecord = CSessionBaseRO::GetFileRecord((char *)v1 + 16, (unsigned int)v59, &v51);
            if ( FileRecord >= 0 )
            {
              v21 = v51;
              if ( v51 && *v51 )
              {
                v22 = *v51;
                *(_DWORD *)(v22 + 76) = 1;
                if ( *(_WORD *)(v22 + 40) == 4 || (v23 = *v21, *(_DWORD *)(v23 + 76) = 1, *(_WORD *)(v23 + 40) == 3) )
                {
                  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v42);
                  v25 = (__int64)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                   v55,
                                   &v43);
                  LastNamespaceRecord = CSessionBaseRO::GetLastNamespaceRecord(
                                          (int)v1 + 16,
                                          v25,
                                          (unsigned int)&v42,
                                          0,
                                          1);
                  v13 = LastNamespaceRecord;
                  if ( LastNamespaceRecord < 0 )
                  {
                    v27 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v28 = 199;
                      goto LABEL_78;
                    }
                    goto LABEL_79;
                  }
                  v29 = v42;
                  if ( !v42
                    || !*(_QWORD *)v42
                    || (v30 = (_DWORD *)((char *)v1 + 44), *(_DWORD *)(*(_QWORD *)v42 + 76LL) < *((_DWORD *)v1 + 11)) )
                  {
                    v31 = (CNamespaceRecord *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
                    if ( v31 )
                      v32 = ((__int64 (__fastcall *)(CNamespaceRecord *))CNamespaceRecord::CNamespaceRecord)(v31);
                    else
                      v32 = 0;
                    SmartPtr<CNamespaceRecord>::operator=(&v42, (CNamespaceRecord *)v32);
                    v29 = v42;
                    if ( !v42 || !*(_QWORD *)v42 )
                    {
                      v13 = -2147024882;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        WPP_SF_s(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          200,
                          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                          "namespaceRecord");
                      goto LABEL_79;
                    }
                    v30 = (_DWORD *)((char *)v56 + 44);
                  }
                  *(_WORD *)(*(_QWORD *)v29 + 40LL) = 8;
                  *(_QWORD *)(*(_QWORD *)v29 + 48LL) = v52;
                  *(_DWORD *)(*(_QWORD *)v29 + 56LL) = v46;
                  *(_QWORD *)(*(_QWORD *)v29 + 60LL) = v47;
                  *(_QWORD *)(*(_QWORD *)v29 + 68LL) = v48;
                  *(_DWORD *)(*(_QWORD *)v29 + 76LL) = *v30;
                  *(_DWORD *)(*(_QWORD *)v29 + 80LL) = -1;
                  *(_DWORD *)(*(_QWORD *)v29 + 84LL) = *(_DWORD *)(*v21 + 16LL);
                  v33 = *(_QWORD *)v29;
                  v34 = (__int64)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                   v57,
                                   &v43);
                  LastNamespaceRecord = CNamespaceRecord::SetName(v33, v34);
                  v13 = LastNamespaceRecord;
                  if ( LastNamespaceRecord < 0 )
                  {
                    v27 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v28 = 201;
                      goto LABEL_78;
                    }
                    goto LABEL_79;
                  }
                  LastNamespaceRecord = CNamespaceRecord::Commit(*(CNamespaceRecord **)v29);
                  v13 = LastNamespaceRecord;
                  if ( LastNamespaceRecord < 0 )
                  {
                    v27 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v28 = 202;
LABEL_78:
                      WPP_SF_Sd(
                        v27[2],
                        v28,
                        (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                        v43,
                        LastNamespaceRecord);
                    }
LABEL_79:
                    SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v42);
                    goto LABEL_125;
                  }
                  bstrString = v29;
                  if ( v29 )
                    ++*((_DWORD *)v29 + 2);
                  v35 = CSessionBaseRW::ActivateNamespaceRecord((char *)v1 + 8, &bstrString, 1);
                  v13 = v35;
                  if ( v35 < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      WPP_SF_dSd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        203,
                        (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                        *(_DWORD *)(*(_QWORD *)v29 + 16LL),
                        v43,
                        v35);
                    goto LABEL_79;
                  }
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_dDddid(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      204,
                      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                      *(unsigned int *)(*(_QWORD *)v29 + 16LL),
                      *(unsigned __int16 *)(*(_QWORD *)v29 + 40LL),
                      *(_DWORD *)(*(_QWORD *)v29 + 76LL),
                      *(_DWORD *)(*(_QWORD *)v29 + 80LL),
                      *(_QWORD *)(*(_QWORD *)v29 + 48LL),
                      *(_DWORD *)(*(_QWORD *)v29 + 84LL));
                  SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v42);
                  ++v61;
                  v11 = v50;
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v24 = *v21;
                  *(_DWORD *)(v24 + 76) = 1;
                  WPP_SF_dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    198,
                    &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                    (unsigned int)v59,
                    *(unsigned __int16 *)(v24 + 40));
                }
                goto LABEL_39;
              }
              v14 = v41;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  197,
                  &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  (unsigned int)v59);
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                196,
                &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                (unsigned int)v59,
                FileRecord);
            }
          }
        }
      }
    }
    else
    {
LABEL_39:
      v14 = v41;
    }
  }
  v13 = 0;
  if ( v61 > 0 )
  {
    NewBackupSet = CSessionBaseRW::CreateNewBackupSet((CBackupSession *)((char *)v1 + 8));
    v13 = NewBackupSet;
    if ( NewBackupSet < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          205,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)NewBackupSet);
      v12 = v41;
      goto LABEL_126;
    }
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      ++*((_DWORD *)v1 + 15);
      v37 = *((_QWORD *)v1 + 3);
      v59 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v37 + 168LL);
      v38 = (_QWORD *)((_QWORD (__stdcall *)(ATL::CComBSTR *, const unsigned __int16 *))ATL::CComBSTR::CComBSTR)(
                        (ATL::CComBSTR *)&bstrString,
                        L"LastRSet");
      v13 = v59(v37, *v38, (char *)v1 + 60, 4);
      SysFreeString(bstrString);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v54) )
      {
        LODWORD(bstrString) = v54;
        if ( v54 >= 0 )
        {
          v1 = this;
          v13 = (int)bstrString;
          __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001C63F);
          goto LABEL_124;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            207,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            (unsigned int)v54);
        v13 = (int)bstrString;
        __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001C63A);
LABEL_125:
        v12 = v41;
LABEL_126:
        fclose(Stream);
        if ( v50 )
          operator delete[](v50);
        if ( v12 )
          operator delete[](v12);
        v2 = v13;
        if ( v13 < 0 && v13 != -2147220479 )
        {
          v6 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_133;
        }
LABEL_136:
        SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(&v51);
        ATL::CStringData::Release((ATL::CStringData *)(v43 - 24));
         = v2;
      }
    }
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          206,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)v13);
      v12 = v41;
      goto LABEL_126;
    }
  }
LABEL_124:
  *((_DWORD *)v1 + 101) = 1;
  goto LABEL_125;
}

```

## disassembly

```asm
0x18001baf8  mov     [rsp+arg_0], rcx
0x18001bafd  push    rbx
0x18001bafe  push    rsi
0x18001baff  push    rdi
0x18001bb00  push    r12
0x18001bb02  push    r13
0x18001bb04  push    r14
0x18001bb06  push    r15
0x18001bb08  sub     rsp, 0E0h
0x18001bb0f  mov     r13, rcx
0x18001bb12  lea     rcx, [rsp+118h+var_A8]
0x18001bb17  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001bb1c  nop
0x18001bb1d  lea     rcx, [rsp+118h+var_70]
0x18001bb25  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18001bb2a  nop
0x18001bb2b  xor     esi, esi
0x18001bb2d  mov     [rsp+118h+hTemplateFile], rsi; hTemplateFile
0x18001bb32  mov     [rsp+118h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x18001bb3a  mov     [rsp+118h+dwCreationDisposition], 3; dwCreationDisposition
0x18001bb42  xor     r9d, r9d; lpSecurityAttributes
0x18001bb45  mov     edx, 80000000h; dwDesiredAccess
0x18001bb4a  lea     r8d, [rsi+5]; dwShareMode
0x18001bb4e  mov     rcx, [r13+78h]; lpFileName
0x18001bb52  call    cs:__imp_CreateFileW
0x18001bb58  mov     [r13+198h], rax
0x18001bb5f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bb63  jnz     loc_18001BC96
0x18001bb69  call    cs:__imp_GetLastError
0x18001bb6f  mov     r9d, eax
0x18001bb72  test    eax, eax
0x18001bb74  jle     short loc_18001BB81
0x18001bb76  movzx   r9d, ax
0x18001bb7a  or      r9d, 80070000h
0x18001bb81  lea     eax, [r9+7FF8FFFEh]
0x18001bb88  mov     r15d, 1
0x18001bb8e  cmp     eax, r15d
0x18001bb91  jbe     loc_18001BC5B
0x18001bb97  cmp     r9d, 80070020h
0x18001bb9e  jnz     short loc_18001BBE4
0x18001bba0  lea     r12, WPP_GLOBAL_Control
0x18001bba7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbae  cmp     rcx, r12
0x18001bbb1  jz      short loc_18001BBD5
0x18001bbb3  test    [rcx+1Ch], r15b
0x18001bbb7  jz      short loc_18001BBD5
0x18001bbb9  mov     edx, 0BAh
0x18001bbbe  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001bbc5  mov     rcx, [rcx+10h]
0x18001bbc9  call    WPP_SF_
0x18001bbce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbd5  mov     esi, 80040405h
0x18001bbda  mov     edi, 4
0x18001bbdf  jmp     loc_18001C6B3
0x18001bbe4  lea     r12, WPP_GLOBAL_Control
0x18001bbeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbf2  cmp     rcx, r12
0x18001bbf5  jz      short loc_18001BC4C
0x18001bbf7  test    [rcx+1Ch], r15b
0x18001bbfb  jz      short loc_18001BC19
0x18001bbfd  mov     edx, 0BBh
0x18001bc02  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001bc09  mov     rcx, [rcx+10h]
0x18001bc0d  call    WPP_SF_d
0x18001bc12  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc19  cmp     rcx, r12
0x18001bc1c  jz      short loc_18001BC4C
0x18001bc1e  test    byte ptr [rcx+1Ch], 4
0x18001bc22  jz      short loc_18001BC4C
0x18001bc24  mov     edx, 0BCh
0x18001bc29  lea     rax, aRestoreLogIsEx; "Restore Log is expected to be accessibl"...
0x18001bc30  mov     qword ptr [rsp+118h+dwCreationDisposition], rax
0x18001bc35  lea     r9, aFalse; "FALSE"
0x18001bc3c  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001bc43  mov     rcx, [rcx+10h]
0x18001bc47  call    WPP_SF_ss
0x18001bc4c  mov     rcx, [r13+78h]; lpFileName
0x18001bc50  call    cs:__imp_DeleteFileW
0x18001bc56  jmp     loc_18001C6DB
0x18001bc5b  lea     r12, WPP_GLOBAL_Control
0x18001bc62  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc69  cmp     rcx, r12
0x18001bc6c  jz      loc_18001C6DB
0x18001bc72  test    byte ptr [rcx+1Ch], 8
0x18001bc76  jz      loc_18001C6DB
0x18001bc7c  mov     edx, 0B9h
0x18001bc81  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001bc88  mov     rcx, [rcx+10h]
0x18001bc8c  call    WPP_SF_
0x18001bc91  jmp     loc_18001C6DB
0x18001bc96  lea     rdx, aRb; "rb"
0x18001bc9d  mov     rcx, [r13+78h]; FileName
0x18001bca1  call    cs:__imp__wfopen
0x18001bca7  mov     [rsp+118h+Stream], rax
0x18001bcaf  test    rax, rax
0x18001bcb2  jnz     loc_18001BD65
0x18001bcb8  lea     r12, WPP_GLOBAL_Control
0x18001bcbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcc6  cmp     rcx, r12
0x18001bcc9  jz      short loc_18001BD34
0x18001bccb  lea     r15d, [rax+1]
0x18001bccf  test    [rcx+1Ch], r15b
0x18001bcd3  jz      short loc_18001BD01
0x18001bcd5  call    cs:__imp__errno
0x18001bcdb  mov     edx, 0BDh
0x18001bce0  mov     r9d, [rax]
0x18001bce3  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001bcea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcf1  mov     rcx, [rcx+10h]
0x18001bcf5  call    WPP_SF_d
0x18001bcfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd01  cmp     rcx, r12
0x18001bd04  jz      short loc_18001BD34
0x18001bd06  test    byte ptr [rcx+1Ch], 4
0x18001bd0a  jz      short loc_18001BD34
0x18001bd0c  mov     edx, 0BEh
0x18001bd11  lea     rax, aRestoreLogIsEx; "Restore Log is expected to be accessibl"...
0x18001bd18  mov     qword ptr [rsp+118h+dwCreationDisposition], rax
0x18001bd1d  lea     r9, aFalse; "FALSE"
0x18001bd24  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001bd2b  mov     rcx, [rcx+10h]
0x18001bd2f  call    WPP_SF_ss
0x18001bd34  mov     rcx, [r13+78h]; lpFileName
0x18001bd38  call    cs:__imp_DeleteFileW
0x18001bd3e  mov     rcx, [r13+198h]; hObject
0x18001bd45  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001bd49  jz      loc_18001C6DB
0x18001bd4f  call    cs:__imp_CloseHandle
0x18001bd55  mov     qword ptr [r13+198h], 0FFFFFFFFFFFFFFFFh
0x18001bd60  jmp     loc_18001C6DB
0x18001bd65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bd6c  mov     ecx, 200C0h; unsigned __int64
0x18001bd71  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001bd76  mov     rbx, rax
0x18001bd79  mov     [rsp+118h+var_78], rax
0x18001bd81  test    rax, rax
0x18001bd84  jnz     short loc_18001BDD2
0x18001bd86  mov     rbx, rsi
0x18001bd89  mov     r14d, 8007000Eh
0x18001bd8f  lea     r12, WPP_GLOBAL_Control
0x18001bd96  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd9d  cmp     rcx, r12
0x18001bda0  jz      short loc_18001BDC8
0x18001bda2  lea     r15d, [rax+1]
0x18001bda6  test    [rcx+1Ch], r15b
0x18001bdaa  jz      short loc_18001BDC8
0x18001bdac  mov     edx, 0BFh
0x18001bdb1  lea     r9, aLogstring; "logString"
0x18001bdb8  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001bdbf  mov     rcx, [rcx+10h]
0x18001bdc3  call    WPP_SF_s
0x18001bdc8  mov     edi, 4
0x18001bdcd  jmp     loc_18001C66C
0x18001bdd2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bdd9  mov     ecx, 20002h; unsigned __int64
0x18001bdde  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001bde3  mov     rdi, rax
0x18001bde6  mov     [rsp+118h+var_B8], rax
0x18001bdeb  test    rax, rax
0x18001bdee  jnz     short loc_18001BE3E
0x18001bdf0  mov     r14d, 8007000Eh
0x18001bdf6  lea     r12, WPP_GLOBAL_Control
0x18001bdfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be04  cmp     rcx, r12
0x18001be07  jz      short loc_18001BE39
0x18001be09  lea     r15d, [rax+1]
0x18001be0d  test    [rcx+1Ch], r15b
0x18001be11  jz      short loc_18001BE39
0x18001be13  mov     edx, 0C0h
0x18001be18  lea     r9, aFilenamebuffer; "fileNameBuffer"
0x18001be1f  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001be26  mov     rcx, [rcx+10h]
0x18001be2a  call    WPP_SF_s
0x18001be2f  mov     edi, 4
0x18001be34  jmp     loc_18001C667
0x18001be39  mov     rbx, rax
0x18001be3c  jmp     short loc_18001BDC8
0x18001be3e  mov     [rsp+118h+var_50], r13
0x18001be46  mov     [rsp+118h+arg_18], esi
0x18001be4d  mov     r15d, 1
0x18001be53  lea     r12, WPP_GLOBAL_Control
0x18001be5a  lea     r14d, [r15+3]
0x18001be5e  jmp     short loc_18001BE65
0x18001be60  mov     rdi, [rsp+118h+var_B8]
0x18001be65  mov     rcx, [rsp+118h+Stream]; Stream
0x18001be6d  call    cs:__imp_feof
0x18001be73  test    eax, eax
0x18001be75  jnz     loc_18001C541
0x18001be7b  mov     [rsp+118h+var_A0], esi
0x18001be7f  mov     [rsp+118h+var_9C], esi
0x18001be83  mov     dword ptr [rsp+118h+arg_8], esi
0x18001be8a  mov     [rsp+118h+var_98], esi
0x18001be91  mov     [rsp+118h+var_68], rsi
0x18001be99  mov     [rsp+118h+var_90], rsi
0x18001bea1  mov     [rsp+118h+var_88], rsi
0x18001bea9  cmp     [r13+0A0h], esi
0x18001beb0  jz      short loc_18001BEF0
0x18001beb2  mov     [r13+98h], r15d
0x18001beb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bec0  cmp     rcx, r12
0x18001bec3  jz      short loc_18001BEE0
0x18001bec5  test    byte ptr [rcx+1Ch], 8
0x18001bec9  jz      short loc_18001BEE0
0x18001becb  mov     edx, 0C1h
0x18001bed0  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001bed7  mov     rcx, [rcx+10h]
0x18001bedb  call    WPP_SF_
0x18001bee0  mov     edi, 4
0x18001bee5  mov     r14d, 80040401h
0x18001beeb  jmp     loc_18001C667
0x18001bef0  xor     edx, edx; Val
0x18001bef2  mov     r8d, 200C0h; Size
0x18001bef8  mov     rcx, rbx; void *
0x18001befb  call    memset_0
0x18001bf00  xor     edx, edx; Val
0x18001bf02  mov     r8d, 20002h; Size
0x18001bf08  mov     rcx, rdi; void *
0x18001bf0b  call    memset_0
0x18001bf10  mov     r8, [rsp+118h+Stream]; Stream
0x18001bf18  mov     edx, 1005Fh; BufferCount
0x18001bf1d  mov     rcx, rbx; Buffer
0x18001bf20  call    cs:__imp_fgetws
0x18001bf26  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001bf2a  inc     rdi
0x18001bf2d  cmp     [rbx+rdi*2], si
0x18001bf31  jnz     short loc_18001BF2A
0x18001bf33  test    rdi, rdi
0x18001bf36  jz      loc_18001BE60
0x18001bf3c  cmp     word ptr [rbx+rdi*2-2], 0Ah
0x18001bf42  jnz     short loc_18001BF55
0x18001bf44  mov     [rbx+rdi*2-2], si
0x18001bf49  dec     rdi
0x18001bf4c  test    rdi, rdi
0x18001bf4f  jz      loc_18001BE60
0x18001bf55  mov     edx, 3Ch ; '<'; Ch
0x18001bf5a  mov     rcx, rbx; Str
0x18001bf5d  call    cs:__imp_wcsrchr
0x18001bf63  cmp     rax, rbx
0x18001bf66  jnz     loc_18001BE60
0x18001bf6c  mov     edx, 3Eh ; '>'; Ch
0x18001bf71  mov     rcx, rbx; Str
0x18001bf74  call    cs:__imp_wcschr
0x18001bf7a  lea     rcx, [rdi-1]
0x18001bf7e  lea     rcx, [rbx+rcx*2]
0x18001bf82  cmp     rax, rcx
0x18001bf85  jnz     loc_18001BE60
0x18001bf8b  cmp     rdi, 2
0x18001bf8f  mov     rdi, [rsp+118h+var_B8]
0x18001bf94  jb      loc_18001BE65
0x18001bf9a  mov     [rcx], si
0x18001bf9d  lea     rcx, [rbx+2]; Buffer
0x18001bfa1  lea     rax, [rsp+118h+var_88]
0x18001bfa9  mov     [rsp+118h+var_C8], rax
0x18001bfae  lea     rax, [rsp+118h+var_90]
0x18001bfb6  mov     [rsp+118h+var_D0], rax
0x18001bfbb  lea     rax, [rsp+118h+var_98]
0x18001bfc3  mov     [rsp+118h+var_D8], rax
0x18001bfc8  lea     rax, [rsp+118h+var_68]
0x18001bfd0  mov     [rsp+118h+var_E0], rax
0x18001bfd5  mov     dword ptr [rsp+118h+hTemplateFile], 10001h
0x18001bfdd  mov     qword ptr [rsp+118h+dwFlagsAndAttributes], rdi
0x18001bfe2  lea     rax, [rsp+118h+arg_8]
0x18001bfea  mov     qword ptr [rsp+118h+dwCreationDisposition], rax
0x18001bfef  lea     r9, [rsp+118h+var_9C]
0x18001bff4  lea     r8, [rsp+118h+var_A0]
0x18001bff9  lea     rdx, aXXXSI64xXI64xI; "%x %x %x %s %I64x %x %I64x %I64x"
0x18001c000  call    cs:__imp_swscanf_s
0x18001c006  cmp     eax, 8
0x18001c009  jnz     loc_18001BE65
0x18001c00f  cmp     [rsp+118h+var_A0], r15d
0x18001c014  jnz     loc_18001BE65
0x18001c01a  mov     eax, [r13+3Ch]
0x18001c01e  cmp     [rsp+118h+var_9C], eax
0x18001c022  jle     loc_18001BE65
0x18001c028  mov     rcx, rdi; unsigned __int16 *
0x18001c02b  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18001c030  mov     r8d, eax
0x18001c033  mov     rdx, rdi
0x18001c036  lea     rcx, [rsp+118h+var_A8]
0x18001c03b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001c040  mov     edx, 2Ah ; '*'
0x18001c045  lea     r8d, [rdx-0Ah]
0x18001c049  lea     rcx, [rsp+118h+var_A8]
0x18001c04e  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort,ushort)
0x18001c053  nop
0x18001c054  mov     dword ptr [rsp+118h+bstrString], esi
0x18001c05b  jmp     short loc_18001C0AA
0x18001c05d  lea     r12, WPP_GLOBAL_Control
0x18001c064  mov     edi, 4
0x18001c069  mov     r14d, dword ptr [rsp+118h+bstrString]
0x18001c071  jmp     loc_18001C667
0x18001c076  xor     esi, esi
0x18001c078  lea     r15d, [rsi+1]
0x18001c07c  lea     r12, WPP_GLOBAL_Control
0x18001c083  lea     r14d, [rsi+4]
0x18001c087  mov     r13, [rsp+118h+arg_0]
0x18001c08f  mov     rdi, [rsp+118h+var_B8]
0x18001c094  mov     ecx, dword ptr [rsp+118h+bstrString]
0x18001c09b  mov     dword ptr [rsp+118h+bstrString], ecx
0x18001c0a2  mov     rbx, [rsp+118h+var_78]
  ... truncated ...
```
