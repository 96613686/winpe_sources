# CSessionBaseRW::FlushAndBackupCatalog(int,_PRIORITY_HINT const *,int *,int *)

- ea: `0x18000e078`
- end: `0x18000edbb`
- name: `?FlushAndBackupCatalog@CSessionBaseRW@@IEAAJHPEBW4_PRIORITY_HINT@@PEAH1@Z`
- size: `3395`
- prototype: `__int64 __fastcall(CSessionBaseRW *__hidden this, int, const enum _PRIORITY_HINT *, int *, struct _FILETIME SystemTimeAsFileTime)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000eed8`
- `0x180018ee0`
- `0x180023330`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x180006914`
- `0x180007818`
- `0x1800091a4`
- `0x180009404`
- `0x1800094ec`
- `0x180009920`
- `0x18000e078`
- `0x18000edc4`
- `0x1800122d8`
- `0x1800127b0`
- `0x18002f970`
- `0x180034010`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x18000e7da`
- `KERNEL32!ResetEvent` at `0x18000e7da`
- `KERNEL32!SetEvent` at `0x18000e8cd`
- `KERNEL32!SetEvent` at `0x18000e8cd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000ec15`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000ec15`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e100`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e186`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e20c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e295`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e31e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e3a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e430`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e4d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e555`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e70d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e9e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ead5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb32`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ebe4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec81`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed4b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed80`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e100`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e186`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e20c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e295`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e31e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e3a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e430`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e4d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e555`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e70d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e9e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ead5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb32`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ebe4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec81`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed4b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed80`

## string_xrefs

- `0x18000e3f6`: `RetentionIncomplete`
- `0x18000e494`: `LastUpdatedTargetCatalog`
- `0x18000e51d`: `LastUpdatedTargetCatalog`
- `0x18000e9a8`: `LastUpdatedTargetCatalog`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::FlushAndBackupCatalog(
        CSessionBaseRW *this,
        int a2,
        const enum _PRIORITY_HINT *a3,
        int *a4,
        struct _FILETIME SystemTimeAsFileTime)
{
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD, char *, __int64); // rsi
  _QWORD *v11; // rax
  unsigned int v12; // esi
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, _QWORD, char *, __int64); // rsi
  _QWORD *v15; // rax
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, _QWORD, char *, __int64); // rsi
  _QWORD *v18; // rax
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, _QWORD, char *, __int64); // rdi
  _QWORD *v21; // rax
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, _QWORD, char *, __int64); // rdi
  _QWORD *v24; // rax
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, _QWORD, char *, __int64); // rdi
  _QWORD *v27; // rax
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, _QWORD, char *, __int64); // rdi
  _QWORD *v30; // rax
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, _QWORD, int *, __int64, int *); // rdi
  _QWORD *v33; // rax
  int v34; // ecx
  __int64 v35; // rbx
  __int64 (__fastcall *v36)(__int64, _QWORD, int *, __int64); // rdi
  _QWORD *v37; // rax
  int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rdx
  _QWORD *v41; // rcx
  __int64 v42; // rbx
  int *v43; // rdi
  __int64 v44; // rbx
  int v45; // eax
  __int64 v46; // r8
  __int64 v47; // rcx
  int v48; // eax
  PVOID *v49; // rcx
  void *v50; // rdi
  __int64 *v51; // rsi
  LPCWSTR *v52; // rax
  __int64 v53; // rcx
  int v54; // r12d
  int v55; // eax
  PVOID *v56; // rcx
  __int64 v57; // rdi
  __int64 v58; // rsi
  __int64 (__fastcall *v59)(__int64, _QWORD, int *, __int64); // r13
  _QWORD *v60; // rax
  PVOID *v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // r9
  int v64; // eax
  __int64 v65; // rdi
  __int64 (__fastcall *v66)(__int64, _QWORD, char *, __int64); // rsi
  _QWORD *v67; // rax
  __int64 v68; // rdi
  __int64 (__fastcall *v69)(__int64, _QWORD, BSTR *, __int64); // rsi
  _QWORD *v70; // rax
  int v71; // eax
  BSTR bstrString; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v74; // [rsp+A8h] [rbp-70h] BYREF
  BSTR v75; // [rsp+B0h] [rbp-68h] BYREF
  int v76; // [rsp+B8h] [rbp-60h] BYREF
  int v77; // [rsp+BCh] [rbp-5Ch] BYREF
  BSTR v78; // [rsp+C0h] [rbp-58h] BYREF
  __int64 v79; // [rsp+C8h] [rbp-50h] BYREF
  int v80; // [rsp+D0h] [rbp-48h] BYREF
  int v81; // [rsp+D4h] [rbp-44h] BYREF
  unsigned int v82; // [rsp+D8h] [rbp-40h] BYREF
  signed int v83; // [rsp+DCh] [rbp-3Ch] BYREF
  BSTR *p_bstrString; // [rsp+E0h] [rbp-38h]
  int v85; // [rsp+120h] [rbp+8h] BYREF
  int *v86; // [rsp+138h] [rbp+20h]

  v86 = a4;
  try
  {
    v76 = 0;
    v85 = 0;
    v77 = 1;
    *(_DWORD *)SystemTimeAsFileTime.dwLowDateTime = 0;
    v9 = *((_QWORD *)this + 2);
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v9 + 168LL);
    v11 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"UnprotectedFileRecords");
    v12 = v10(v9, *v11, (char *)this + 24, 4);
    SysFreeString(bstrString);
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
      return v12;
    }
    v13 = *((_QWORD *)this + 2);
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v13 + 168LL);
    v15 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"PartiallyProtectedFileRecords");
    v12 = v14(v13, *v15, (char *)this + 28, 4);
    SysFreeString(bstrString);
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
      return v12;
    }
    v16 = *((_QWORD *)this + 2);
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v16 + 168LL);
    v18 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"FullyProtectedFileRecords");
    v12 = v17(v16, *v18, (char *)this + 32, 4);
    SysFreeString(bstrString);
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
      return v12;
    }
    v19 = *((_QWORD *)this + 2);
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v19 + 168LL);
    v21 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"TotalBytesInStaging");
    v12 = v20(v19, *v21, (char *)this + 168, 8);
    SysFreeString(bstrString);
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
      return v12;
    }
    v22 = *((_QWORD *)this + 2);
    v23 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v22 + 168LL);
    v24 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"TotalBytesOnDefaultTarget");
    v12 = v23(v22, *v24, (char *)this + 176, 8);
    SysFreeString(bstrString);
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
      return v12;
    }
    v25 = *((_QWORD *)this + 2);
    v26 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v25 + 168LL);
    v27 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"OldestPresentBSet");
    v12 = v26(v25, *v27, (char *)this + 184, 4);
    SysFreeString(bstrString);
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
      return v12;
    }
    v28 = *((_QWORD *)this + 2);
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v28 + 168LL);
    v30 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"RetentionIncomplete");
    v12 = v29(v28, *v30, (char *)this + 188, 1);
    SysFreeString(bstrString);
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
      return v12;
    }
    if ( a2 )
    {
      v76 = 4;
      v31 = *((_QWORD *)this + 2);
      v32 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64, int *))(*(_QWORD *)v31 + 176LL);
      v33 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"LastUpdatedTargetCatalog");
      LODWORD(v31) = v32(v31, *v33, &v85, 4, &v76);
      SysFreeString(bstrString);
      if ( (int)v31 >= 0 && v76 == 4 )
      {
        v34 = v85;
      }
      else
      {
        v34 = 0;
        v85 = 0;
      }
      v77 = (v34 == 1) + 1;
      v35 = *((_QWORD *)this + 2);
      v36 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64))(*(_QWORD *)v35 + 168LL);
      v37 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"LastUpdatedTargetCatalog");
      v12 = v36(v35, *v37, &v77, 4);
      SysFreeString(bstrString);
      if ( (v12 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
        return v12;
      }
    }
    v38 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2), 1);
    v12 = v38;
    if ( v38 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          (unsigned int)v38);
      return v12;
    }
    if ( !a2 )
      return v12;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v74);
    v75 = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v79);
    v82 = 0;
    v80 = 0;
    v81 = 0;
    v39 = 88;
    if ( v77 == 1 )
      v39 = 80;
    v40 = *(_QWORD *)((char *)this + v39);
    v41 = (_QWORD *)(v40 - 24);
    v42 = v79;
    v43 = (int *)(v79 - 24);
    if ( v40 - 24 != v79 - 24 )
    {
      if ( v43[4] >= 0 && *v41 == *(_QWORD *)v43 )
      {
        v44 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v41);
        ATL::CStringData::Release((ATL::CStringData *)v43);
        v42 = v44 + 24;
        v79 = v42;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v79, v40, *(unsigned int *)(v40 - 16));
        v42 = v79;
      }
    }
    v45 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 2) + 72LL))(*((_QWORD *)this + 2), &v75);
    v12 = v45;
    if ( v45 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          (unsigned int)v45);
LABEL_123:
      ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
      SysFreeString(v75);
      ATL::CStringData::Release((ATL::CStringData *)(v74 - 24));
      return v12;
    }
    v46 = (unsigned int)ocslen(v75);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v74, v47, v46);
    v48 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 40LL))(*((_QWORD *)this + 2));
    if ( v48 < 0 )
    {
      v49 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (unsigned int)v48);
          v49 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v49 != &WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 4) != 0 )
          WPP_SF_ss(
            (int)v49[2],
            32,
            (int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (int)"FALSE",
            (__int64)"Catalog detach should not fail under these conditions");
      }
    }
    ResetEvent(*((HANDLE *)this + 20));
    v50 = (void *)*((_QWORD *)this + 34);
    p_bstrString = &bstrString;
    v51 = (__int64 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                       &bstrString,
                       &v79);
    v52 = (LPCWSTR *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                       &v78,
                       &v74);
    v54 = FheFileOperations::CopyFileWithBackoff(
            v52,
            v51,
            (__int64)a3,
            0,
            1,
            0,
            0,
            a4,
            0,
            0,
            0,
            0,
            0,
            0,
            &v82,
            &v80,
            &v81,
            0,
            0,
            v50);
    if ( v54 >= 0 )
      v54 = CSessionBaseRW::FlushFile(v53, &v79);
    SetEvent(*((HANDLE *)this + 20));
    v55 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 48LL))(*((_QWORD *)this + 2));
    if ( v55 < 0 )
    {
      v56 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_82;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          (unsigned int)v55);
        v56 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v56 == &WPP_GLOBAL_Control || (*((_BYTE *)v56 + 28) & 4) == 0 )
        goto LABEL_82;
      WPP_SF_ss(
        (int)v56[2],
        34,
        (int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
        (int)"FALSE",
        (__int64)"Catalog reattach should not fail under these conditions");
    }
    v56 = (PVOID *)WPP_GLOBAL_Control;
LABEL_82:
    if ( v54 >= 0 )
    {
      SystemTimeAsFileTime = 0;
      bstrString = 0;
      v65 = *((_QWORD *)this + 2);
      v66 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v65 + 168LL);
      v67 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v78, L"LastCatalogBackup");
      v12 = v66(v65, *v67, (char *)this + 36, 4);
      SysFreeString(v78);
      if ( (v12 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
        goto LABEL_123;
      }
      *((_DWORD *)this + 48) = *((_DWORD *)this + 9);
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      bstrString = (BSTR)(SystemTimeAsFileTime.dwLowDateTime
                        + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32));
      v68 = *((_QWORD *)this + 2);
      v69 = *(__int64 (__fastcall **)(__int64, _QWORD, BSTR *, __int64))(*(_QWORD *)v68 + 168LL);
      v70 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v78, L"LastCatalogBackupTime");
      v12 = v69(v68, *v70, &bstrString, 8);
      SysFreeString(v78);
      if ( (v12 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
        goto LABEL_123;
      }
      *((_QWORD *)this + 25) = bstrString;
      v71 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2), 1);
      v12 = v71;
      if ( v71 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (unsigned int)v71);
        goto LABEL_123;
      }
      v57 = v74;
      goto LABEL_125;
    }
    if ( v56 == &WPP_GLOBAL_Control || (*((_BYTE *)v56 + 28) & 1) == 0 )
    {
      v57 = v74;
    }
    else
    {
      v57 = v74;
      WPP_SF_SSd(
        (unsigned int)v56[2],
        35,
        (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
        v74,
        v42,
        v54);
    }
    v58 = *((_QWORD *)this + 2);
    v59 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64))(*(_QWORD *)v58 + 168LL);
    v60 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v78, L"LastUpdatedTargetCatalog");
    v12 = v59(v58, *v60, &v85, 4);
    SysFreeString(v78);
    if ( (v12 & 0x80000000) != 0 )
    {
      v61 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_99;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_96;
      v62 = 36;
      v63 = v12;
      goto LABEL_95;
    }
    v64 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2), 1);
    v12 = v64;
    if ( v64 < 0 )
    {
      v61 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_99;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_96:
        if ( v61 != &WPP_GLOBAL_Control && (*((_BYTE *)v61 + 28) & 4) != 0 )
        {
          WPP_SF_ss(
            (int)v61[2],
            38,
            (int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (int)"FALSE",
            (__int64)"Unable to roll back globals related to Catalog backup");
          v61 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_99:
        if ( (v12 & 0x80000000) != 0 )
        {
          if ( v61 != &WPP_GLOBAL_Control && (*((_BYTE *)v61 + 28) & 1) != 0 )
            WPP_SF_d(v61[2], 39, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v12);
          ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
          SysFreeString(v75);
          ATL::CStringData::Release((ATL::CStringData *)(v57 - 24));
          return v12;
        }
LABEL_125:
        ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
        SysFreeString(v75);
        ATL::CStringData::Release((ATL::CStringData *)(v57 - 24));
        return v12;
      }
      v62 = 37;
      v63 = (unsigned int)v64;
LABEL_95:
      WPP_SF_d(v61[2], v62, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v63);
      v61 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_96;
    }
    if ( *v86 )
    {
      v12 = -2147220479;
    }
    else
    {
      v12 = v54;
      if ( v80 )
        v12 = -2147220478;
    }
    *(_DWORD *)SystemTimeAsFileTime.dwLowDateTime = 1;
    ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
    SysFreeString(v75);
    ATL::CStringData::Release((ATL::CStringData *)(v57 - 24));
  }
  catch ( ATL::CAtlException v83 )
  {
    SystemTimeAsFileTime.dwLowDateTime = v83;
    if ( v83 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          (unsigned int)v83);
      return SystemTimeAsFileTime.dwLowDateTime;
    }
    return SystemTimeAsFileTime.dwLowDateTime;
  }
  v76 = 0;
}

```

## disassembly

```asm
0x18000e078  mov     r11, rsp
0x18000e07b  mov     [r11+10h], rbx
0x18000e07f  mov     [r11+18h], rsi
0x18000e083  mov     [r11+20h], r9
0x18000e087  push    rdi
0x18000e088  push    r12
0x18000e08a  push    r13
0x18000e08c  push    r14
0x18000e08e  push    r15
0x18000e090  sub     rsp, 0F0h
0x18000e097  mov     r13, r9
0x18000e09a  mov     r12, r8
0x18000e09d  mov     r14d, edx
0x18000e0a0  mov     r15, rcx
0x18000e0a3  xor     ecx, ecx
0x18000e0a5  mov     [r11-60h], ecx
0x18000e0a9  mov     [r11+8], ecx
0x18000e0ad  mov     dword ptr [r11-5Ch], 1
0x18000e0b5  mov     rax, qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime]
0x18000e0bd  mov     [rax], ecx
0x18000e0bf  mov     rbx, [r15+10h]
0x18000e0c3  mov     rax, [rbx]
0x18000e0c6  mov     rsi, [rax+0A8h]
0x18000e0cd  lea     rdx, aUnprotectedfil; "UnprotectedFileRecords"
0x18000e0d4  lea     rcx, [r11-78h]; this
0x18000e0d8  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000e0dd  nop
0x18000e0de  mov     r9d, 4
0x18000e0e4  lea     r8, [r15+18h]
0x18000e0e8  mov     rdx, [rax]
0x18000e0eb  mov     rcx, rbx
0x18000e0ee  mov     rax, rsi
0x18000e0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0f6  mov     esi, eax
0x18000e0f8  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000e100  call    cs:__imp_SysFreeString
0x18000e106  test    esi, esi
0x18000e108  jns     short loc_18000E141
0x18000e10a  lea     r14, WPP_GLOBAL_Control
0x18000e111  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e118  cmp     rcx, r14
0x18000e11b  jz      short loc_18000E13C
0x18000e11d  test    byte ptr [rcx+1Ch], 1
0x18000e121  jz      short loc_18000E13C
0x18000e123  mov     edx, 15h
0x18000e128  mov     r9d, esi
0x18000e12b  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000e132  mov     rcx, [rcx+10h]
0x18000e136  call    WPP_SF_d
0x18000e13b  nop
0x18000e13c  jmp     loc_18000ED9C
0x18000e141  mov     rbx, [r15+10h]
0x18000e145  mov     rax, [rbx]
0x18000e148  mov     rsi, [rax+0A8h]
0x18000e14f  lea     rdx, aPartiallyprote; "PartiallyProtectedFileRecords"
0x18000e156  lea     rcx, [rsp+118h+bstrString]; this
0x18000e15e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000e163  nop
0x18000e164  lea     r8, [r15+1Ch]
0x18000e168  mov     r9d, 4
0x18000e16e  mov     rdx, [rax]
0x18000e171  mov     rcx, rbx
0x18000e174  mov     rax, rsi
0x18000e177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e17c  mov     esi, eax
0x18000e17e  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000e186  call    cs:__imp_SysFreeString
0x18000e18c  test    esi, esi
0x18000e18e  jns     short loc_18000E1C7
0x18000e190  lea     r14, WPP_GLOBAL_Control
0x18000e197  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e19e  cmp     rcx, r14
0x18000e1a1  jz      short loc_18000E1C2
0x18000e1a3  test    byte ptr [rcx+1Ch], 1
0x18000e1a7  jz      short loc_18000E1C2
0x18000e1a9  mov     edx, 16h
0x18000e1ae  mov     r9d, esi
0x18000e1b1  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000e1b8  mov     rcx, [rcx+10h]
0x18000e1bc  call    WPP_SF_d
0x18000e1c1  nop
0x18000e1c2  jmp     loc_18000ED9C
0x18000e1c7  mov     rbx, [r15+10h]
0x18000e1cb  mov     rax, [rbx]
0x18000e1ce  mov     rsi, [rax+0A8h]
0x18000e1d5  lea     rdx, aFullyprotected; "FullyProtectedFileRecords"
0x18000e1dc  lea     rcx, [rsp+118h+bstrString]; this
0x18000e1e4  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000e1e9  nop
0x18000e1ea  lea     r8, [r15+20h]
0x18000e1ee  mov     r9d, 4
0x18000e1f4  mov     rdx, [rax]
0x18000e1f7  mov     rcx, rbx
0x18000e1fa  mov     rax, rsi
0x18000e1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e202  mov     esi, eax
0x18000e204  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000e20c  call    cs:__imp_SysFreeString
0x18000e212  test    esi, esi
0x18000e214  jns     short loc_18000E24D
0x18000e216  lea     r14, WPP_GLOBAL_Control
0x18000e21d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e224  cmp     rcx, r14
0x18000e227  jz      short loc_18000E248
0x18000e229  test    byte ptr [rcx+1Ch], 1
0x18000e22d  jz      short loc_18000E248
0x18000e22f  mov     edx, 17h
0x18000e234  mov     r9d, esi
0x18000e237  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000e23e  mov     rcx, [rcx+10h]
0x18000e242  call    WPP_SF_d
0x18000e247  nop
0x18000e248  jmp     loc_18000ED9C
0x18000e24d  mov     rbx, [r15+10h]
0x18000e251  mov     rax, [rbx]
0x18000e254  mov     rdi, [rax+0A8h]
0x18000e25b  lea     rdx, aTotalbytesinst; "TotalBytesInStaging"
0x18000e262  lea     rcx, [rsp+118h+bstrString]; this
0x18000e26a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000e26f  nop
0x18000e270  lea     r8, [r15+0A8h]
0x18000e277  mov     r9d, 8
0x18000e27d  mov     rdx, [rax]
0x18000e280  mov     rcx, rbx
0x18000e283  mov     rax, rdi
0x18000e286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e28b  mov     esi, eax
0x18000e28d  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000e295  call    cs:__imp_SysFreeString
0x18000e29b  test    esi, esi
0x18000e29d  jns     short loc_18000E2D6
0x18000e29f  lea     r14, WPP_GLOBAL_Control
0x18000e2a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2ad  cmp     rcx, r14
0x18000e2b0  jz      short loc_18000E2D1
0x18000e2b2  test    byte ptr [rcx+1Ch], 1
0x18000e2b6  jz      short loc_18000E2D1
0x18000e2b8  mov     edx, 18h
0x18000e2bd  mov     r9d, esi
0x18000e2c0  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000e2c7  mov     rcx, [rcx+10h]
0x18000e2cb  call    WPP_SF_d
0x18000e2d0  nop
0x18000e2d1  jmp     loc_18000ED9C
0x18000e2d6  mov     rbx, [r15+10h]
0x18000e2da  mov     rax, [rbx]
0x18000e2dd  mov     rdi, [rax+0A8h]
0x18000e2e4  lea     rdx, aTotalbytesonde; "TotalBytesOnDefaultTarget"
0x18000e2eb  lea     rcx, [rsp+118h+bstrString]; this
0x18000e2f3  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000e2f8  nop
0x18000e2f9  lea     r8, [r15+0B0h]
0x18000e300  mov     r9d, 8
0x18000e306  mov     rdx, [rax]
0x18000e309  mov     rcx, rbx
0x18000e30c  mov     rax, rdi
0x18000e30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e314  mov     esi, eax
0x18000e316  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000e31e  call    cs:__imp_SysFreeString
0x18000e324  test    esi, esi
0x18000e326  jns     short loc_18000E35F
0x18000e328  lea     r14, WPP_GLOBAL_Control
0x18000e32f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e336  cmp     rcx, r14
0x18000e339  jz      short loc_18000E35A
0x18000e33b  test    byte ptr [rcx+1Ch], 1
0x18000e33f  jz      short loc_18000E35A
0x18000e341  mov     edx, 19h
0x18000e346  mov     r9d, esi
0x18000e349  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000e350  mov     rcx, [rcx+10h]
0x18000e354  call    WPP_SF_d
0x18000e359  nop
0x18000e35a  jmp     loc_18000ED9C
0x18000e35f  mov     rbx, [r15+10h]
0x18000e363  mov     rax, [rbx]
0x18000e366  mov     rdi, [rax+0A8h]
0x18000e36d  lea     rdx, aOldestpresentb; "OldestPresentBSet"
0x18000e374  lea     rcx, [rsp+118h+bstrString]; this
0x18000e37c  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000e381  nop
0x18000e382  lea     r8, [r15+0B8h]
0x18000e389  mov     r9d, 4
0x18000e38f  mov     rdx, [rax]
0x18000e392  mov     rcx, rbx
0x18000e395  mov     rax, rdi
0x18000e398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e39d  mov     esi, eax
0x18000e39f  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000e3a7  call    cs:__imp_SysFreeString
0x18000e3ad  test    esi, esi
0x18000e3af  jns     short loc_18000E3E8
0x18000e3b1  lea     r14, WPP_GLOBAL_Control
0x18000e3b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3bf  cmp     rcx, r14
0x18000e3c2  jz      short loc_18000E3E3
0x18000e3c4  test    byte ptr [rcx+1Ch], 1
0x18000e3c8  jz      short loc_18000E3E3
0x18000e3ca  mov     edx, 1Ah
0x18000e3cf  mov     r9d, esi
0x18000e3d2  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000e3d9  mov     rcx, [rcx+10h]
0x18000e3dd  call    WPP_SF_d
0x18000e3e2  nop
0x18000e3e3  jmp     loc_18000ED9C
0x18000e3e8  mov     rbx, [r15+10h]
0x18000e3ec  mov     rax, [rbx]
0x18000e3ef  mov     rdi, [rax+0A8h]
0x18000e3f6  lea     rdx, aRetentionincom; "RetentionIncomplete"
0x18000e3fd  lea     rcx, [rsp+118h+bstrString]; this
0x18000e405  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000e40a  nop
0x18000e40b  lea     r8, [r15+0BCh]
0x18000e412  mov     r9d, 1
0x18000e418  mov     rdx, [rax]
0x18000e41b  mov     rcx, rbx
0x18000e41e  mov     rax, rdi
0x18000e421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e426  mov     esi, eax
0x18000e428  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000e430  call    cs:__imp_SysFreeString
0x18000e436  test    esi, esi
0x18000e438  jns     short loc_18000E471
0x18000e43a  lea     r14, WPP_GLOBAL_Control
0x18000e441  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e448  cmp     rcx, r14
0x18000e44b  jz      short loc_18000E46C
0x18000e44d  test    byte ptr [rcx+1Ch], 1
0x18000e451  jz      short loc_18000E46C
0x18000e453  mov     edx, 1Bh
0x18000e458  mov     r9d, esi
0x18000e45b  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000e462  mov     rcx, [rcx+10h]
0x18000e466  call    WPP_SF_d
0x18000e46b  nop
0x18000e46c  jmp     loc_18000ED9C
0x18000e471  test    r14d, r14d
0x18000e474  jz      loc_18000E596
0x18000e47a  mov     esi, 4
0x18000e47f  mov     [rsp+118h+var_60], esi
0x18000e486  mov     rbx, [r15+10h]
0x18000e48a  mov     rax, [rbx]
0x18000e48d  mov     rdi, [rax+0B0h]
0x18000e494  lea     rdx, aLastupdatedtar; "LastUpdatedTargetCatalog"
0x18000e49b  lea     rcx, [rsp+118h+bstrString]; this
0x18000e4a3  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000e4a8  nop
0x18000e4a9  lea     rcx, [rsp+118h+var_60]
0x18000e4b1  mov     [rsp+118h+var_F8], rcx
0x18000e4b6  mov     r9d, esi
0x18000e4b9  lea     r8, [rsp+118h+arg_0]
0x18000e4c1  mov     rdx, [rax]
0x18000e4c4  mov     rcx, rbx
0x18000e4c7  mov     rax, rdi
0x18000e4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4cf  mov     ebx, eax
0x18000e4d1  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000e4d9  call    cs:__imp_SysFreeString
0x18000e4df  test    ebx, ebx
0x18000e4e1  js      short loc_18000E4F5
0x18000e4e3  cmp     [rsp+118h+var_60], esi
0x18000e4ea  jnz     short loc_18000E4F5
0x18000e4ec  mov     ecx, [rsp+118h+arg_0]
0x18000e4f3  jmp     short loc_18000E4FE
0x18000e4f5  xor     ecx, ecx
0x18000e4f7  mov     [rsp+118h+arg_0], ecx
0x18000e4fe  xor     eax, eax
0x18000e500  cmp     ecx, 1
0x18000e503  setz    al
0x18000e506  inc     eax
0x18000e508  mov     [rsp+118h+var_5C], eax
0x18000e50f  mov     rbx, [r15+10h]
0x18000e513  mov     rax, [rbx]
0x18000e516  mov     rdi, [rax+0A8h]
0x18000e51d  lea     rdx, aLastupdatedtar; "LastUpdatedTargetCatalog"
0x18000e524  lea     rcx, [rsp+118h+bstrString]; this
0x18000e52c  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000e531  nop
0x18000e532  mov     r9d, esi
0x18000e535  lea     r8, [rsp+118h+var_5C]
0x18000e53d  mov     rdx, [rax]
0x18000e540  mov     rcx, rbx
0x18000e543  mov     rax, rdi
0x18000e546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e54b  mov     esi, eax
0x18000e54d  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000e555  call    cs:__imp_SysFreeString
0x18000e55b  test    esi, esi
0x18000e55d  jns     short loc_18000E596
0x18000e55f  lea     r14, WPP_GLOBAL_Control
0x18000e566  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e56d  cmp     rcx, r14
0x18000e570  jz      short loc_18000E591
0x18000e572  test    byte ptr [rcx+1Ch], 1
0x18000e576  jz      short loc_18000E591
0x18000e578  mov     edx, 1Ch
0x18000e57d  mov     r9d, esi
0x18000e580  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000e587  mov     rcx, [rcx+10h]
  ... truncated ...
```
