# TMetabase_XMLtable::PopulateCache(void)

- ea: `0x18000d110`
- end: `0x18000dfd2`
- name: `?PopulateCache@TMetabase_XMLtable@@UEAAJXZ`
- size: `3778`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002b90`
- `0x180002bc4`
- `0x18000584c`
- `0x180005c48`
- `0x180006710`
- `0x18000c008`
- `0x18000ce00`
- `0x18000d110`
- `0x18000e168`
- `0x180011b38`
- `0x180012734`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000d88e`
- `msvcrt!swprintf_s` at `0x18000ded5`
- `msvcrt!swprintf_s` at `0x18000d88e`
- `msvcrt!swprintf_s` at `0x18000ded5`
- `msvcrt!_wcsicmp` at `0x18000dad8`
- `msvcrt!_wcsicmp` at `0x18000db5a`
- `msvcrt!_wcsicmp` at `0x18000db8d`
- `msvcrt!_wcsicmp` at `0x18000dad8`
- `msvcrt!_wcsicmp` at `0x18000db5a`
- `msvcrt!_wcsicmp` at `0x18000db8d`
- `KERNEL32!GetFileAttributesW` at `0x18000d15f`
- `KERNEL32!GetFileAttributesW` at `0x18000d15f`
- `ole32!CoTaskMemFree` at `0x18000d261`
- `ole32!CoTaskMemFree` at `0x18000d33e`
- `ole32!CoTaskMemFree` at `0x18000d3aa`
- `ole32!CoTaskMemFree` at `0x18000d648`
- `ole32!CoTaskMemFree` at `0x18000d6b1`
- `ole32!CoTaskMemFree` at `0x18000d6fd`
- `ole32!CoTaskMemFree` at `0x18000d742`
- `ole32!CoTaskMemFree` at `0x18000d81c`
- `ole32!CoTaskMemFree` at `0x18000db11`
- `ole32!CoTaskMemFree` at `0x18000ddb3`
- `ole32!CoTaskMemFree` at `0x18000de68`
- `ole32!CoTaskMemFree` at `0x18000d261`
- `ole32!CoTaskMemFree` at `0x18000d33e`
- `ole32!CoTaskMemFree` at `0x18000d3aa`
- `ole32!CoTaskMemFree` at `0x18000d648`
- `ole32!CoTaskMemFree` at `0x18000d6b1`
- `ole32!CoTaskMemFree` at `0x18000d6fd`
- `ole32!CoTaskMemFree` at `0x18000d742`
- `ole32!CoTaskMemFree` at `0x18000d81c`
- `ole32!CoTaskMemFree` at `0x18000db11`
- `ole32!CoTaskMemFree` at `0x18000ddb3`
- `ole32!CoTaskMemFree` at `0x18000de68`
- `ole32!CoTaskMemAlloc` at `0x18000d2e6`
- `ole32!CoTaskMemAlloc` at `0x18000d2e6`
- `ole32!CoTaskMemRealloc` at `0x18000d724`
- `ole32!CoTaskMemRealloc` at `0x18000d724`

## string_xrefs

- `0x18000d4c6`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000d59b`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000d973`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000da5b`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000dc78`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000dd60`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`
- `0x18000df77`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall TMetabase_XMLtable::PopulateCache(const WCHAR *this)
{
  __int64 result; // rax
  char *v3; // r13
  int v4; // eax
  int v5; // ebx
  int v6; // ebx
  __int64 i; // rsi
  unsigned int v8; // edx
  LPVOID v9; // rax
  struct IXMLDOMDocument *v10; // rbx
  int v11; // esi
  unsigned int v12; // eax
  _DWORD *v13; // r12
  __int64 v14; // r12
  unsigned int v15; // eax
  CErrorInterceptor *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // r12
  unsigned int v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // r13d
  unsigned int v22; // r8d
  __int64 v23; // rdx
  int v24; // esi
  __int64 v25; // rcx
  unsigned int v26; // eax
  CErrorInterceptor *v27; // rcx
  unsigned int v28; // esi
  unsigned int v29; // r15d
  wchar_t *v30; // r13
  unsigned int v31; // eax
  CErrorInterceptor *v32; // rcx
  unsigned int v33; // edx
  unsigned int j; // r9d
  int v35; // r8d
  unsigned int v36; // r10d
  TMetabase_XMLtable::TLocation *v37; // rcx
  struct IXMLDOMDocument *v38; // [rsp+B0h] [rbp-198h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-190h] BYREF
  __int64 v40; // [rsp+C0h] [rbp-188h]
  int v41; // [rsp+C8h] [rbp-180h]
  int v42; // [rsp+CCh] [rbp-17Ch]
  int v43; // [rsp+D0h] [rbp-178h]
  unsigned int v44; // [rsp+D4h] [rbp-174h]
  unsigned int v45; // [rsp+D8h] [rbp-170h]
  int v46; // [rsp+DCh] [rbp-16Ch]
  unsigned int v47; // [rsp+E0h] [rbp-168h]
  __int64 v48; // [rsp+E8h] [rbp-160h]
  int v49; // [rsp+F0h] [rbp-158h] BYREF
  wchar_t *v50; // [rsp+F8h] [rbp-150h]
  wchar_t *String2; // [rsp+100h] [rbp-148h]
  char v52[8]; // [rsp+110h] [rbp-138h] BYREF
  __int64 v53; // [rsp+118h] [rbp-130h]
  char v54[8]; // [rsp+120h] [rbp-128h] BYREF
  __int64 v55; // [rsp+128h] [rbp-120h]
  char v56[8]; // [rsp+130h] [rbp-118h] BYREF
  __int64 v57; // [rsp+138h] [rbp-110h]
  char v58[8]; // [rsp+140h] [rbp-108h] BYREF
  __int64 v59; // [rsp+148h] [rbp-100h]
  char v60[8]; // [rsp+150h] [rbp-F8h] BYREF
  __int64 v61; // [rsp+158h] [rbp-F0h]
  char v62[8]; // [rsp+160h] [rbp-E8h] BYREF
  __int64 v63; // [rsp+168h] [rbp-E0h]
  wchar_t *String1; // [rsp+170h] [rbp-D8h] BYREF
  _DWORD *v65; // [rsp+198h] [rbp-B0h]
  _DWORD *v66; // [rsp+1B0h] [rbp-98h]
  GUID v67; // [rsp+1C0h] [rbp-88h] BYREF
  wchar_t Buffer[12]; // [rsp+1D0h] [rbp-78h] BYREF
  wchar_t v69[20]; // [rsp+1E8h] [rbp-60h] BYREF

  result = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD))(*(_QWORD *)this + 72LL))(this, 0);
  if ( (int)result >= 0 )
  {
    v3 = (char *)(this + 16);
    if ( GetFileAttributesW(this + 16) == -1 )
      return 2147942402LL;
    v4 = (*(__int64 (__fastcall **)(char *, char *, char *))(*((_QWORD *)this + 244) + 72LL))(
           (char *)this + 1952,
           (char *)this + 16,
           (char *)this + 32);
    if ( v4 && v4 != -2145319657 )
    {
      v38 = 0;
      v67 = TMSXMLBase::m_CLSID_DOMDocument30;
      v5 = (**((__int64 (__fastcall ***)(char *, GUID *, _QWORD, __int64, GUID *, struct IXMLDOMDocument **))this + 2))(
             (char *)this + 16,
             &v67,
             0,
             1,
             &IID_IXMLDOMDocument,
             &v38);
      if ( v5 >= 0 )
      {
        v6 = TMetabase_XMLtable::ParseXMLFile((TMetabase_XMLtable *)(this - 4), v38, *((_BYTE *)this + 1617));
        ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(&v38);
        if ( v6 >= 0 )
          return 2149647636LL;
        else
          return (unsigned int)v6;
      }
      else
      {
        ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(&v38);
        return (unsigned int)v5;
      }
    }
    for ( i = 0; i != 9; ++i )
    {
      CoTaskMemFree(*(LPVOID *)&this[8 * i + 692]);
      *(_QWORD *)&this[8 * i + 692] = 0;
      *(_QWORD *)&this[8 * i + 696] = 0;
    }
    result = (*(__int64 (__fastcall **)(const WCHAR *))(*(_QWORD *)this + 80LL))(this);
    if ( (int)result >= 0 )
    {
      if ( !*((_BYTE *)this + 1616) )
        goto LABEL_83;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, _QWORD))(**((_QWORD **)this + 222) + 40LL))(
        *((_QWORD *)this + 222),
        0,
        0,
        (char *)this + 1640,
        0);
      v9 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 410), 4u));
      *((_QWORD *)this + 197) = v9;
      if ( !v9 )
        return 2147942414LL;
      v10 = 0;
      v38 = 0;
      pv = 0;
      v40 = 0;
      v11 = CCfgArray<TMetabase_XMLtable::TProperty>::SetSize(&pv, *((unsigned int *)this + 408));
      if ( v11 < 0 )
      {
LABEL_72:
        CoTaskMemFree(pv);
        TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v38);
        return (unsigned int)v11;
      }
      v45 = 0;
      v47 = 0;
      v12 = 0;
      v13 = pv;
LABEL_19:
      v44 = v12;
      if ( v12 < *((_DWORD *)this + 423) )
      {
        v11 = CCfgArray<TMetabase_XMLtable::TProperty>::SetSize(&pv, 0);
        if ( v11 < 0 )
          goto LABEL_72;
        v14 = v44;
        if ( v44
          && (unsigned int)TMetabase_XMLtable::TLocation::CompareLocation(
                             (TMetabase_XMLtable::TLocation *)(*((_QWORD *)this + 210) + 24LL * v44),
                             (const struct TMetabase_XMLtable::TLocation *)(*((_QWORD *)this + 210) + 24LL * (v44 - 1))) == 2 )
        {
          v15 = *((_DWORD *)this + 406);
          if ( v15 < 0x32 )
          {
            *((_DWORD *)this + 406) = v15 + 1;
            v53 = 0;
            CErrorInterceptor::Init(
              v52,
              this + 896,
              *((_QWORD *)this + 213),
              2149647651LL,
              2,
              -2147348267,
              *(_QWORD *)(*((_QWORD *)this + 210) + 24 * v14),
              0,
              0,
              0,
              14,
              L"MBProperty",
              1,
              -1,
              -1,
              v3,
              2);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)v52,
              L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
              1255,
              *((_DWORD *)this + 413));
            v16 = (CErrorInterceptor *)v52;
            goto LABEL_27;
          }
          if ( v15 == 50 )
          {
            *((_DWORD *)this + 406) = 51;
            v55 = 0;
            CErrorInterceptor::Init(
              v54,
              this + 896,
              *((_QWORD *)this + 213),
              2149647651LL,
              2,
              -1073606423,
              v3,
              0,
              0,
              0,
              14,
              L"MBProperty",
              1,
              -1,
              -1,
              v3,
              2);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)v54,
              L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
              1255,
              *((_DWORD *)this + 413));
            v16 = (CErrorInterceptor *)v54;
LABEL_27:
            CErrorInterceptor::~CErrorInterceptor(v16);
          }
          *((_DWORD *)this + 410) -= *(_DWORD *)(*((_QWORD *)this + 210) + 24 * v14 + 8);
          v13 = pv;
          goto LABEL_81;
        }
        memset_0(&String1, 0, 0x48u);
        v17 = *((_QWORD *)this + 222);
        v18 = 3 * v14;
        v48 = v18;
        v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v17 + 32LL))(
                v17,
                *(unsigned int *)(*((_QWORD *)this + 210) + 8 * v18 + 12),
                9);
        if ( v11 < 0 )
          goto LABEL_72;
        v67.Data1 = *(_DWORD *)(*((_QWORD *)this + 210) + 8 * v18 + 12);
        *(_QWORD *)v67.Data4 = String1;
        v11 = CCfgArray<TMetabase_XMLtable::TProperty>::InsertAt(&pv, &v67, HIDWORD(v40));
        if ( v11 < 0 )
          goto LABEL_72;
        v19 = *(_DWORD *)(*((_QWORD *)this + 210) + 8 * v18 + 8);
        if ( v45 < v19 )
        {
          v20 = (v19 + 63) & 0xFFFFFFC0;
          v45 = v20;
          if ( v20 >= 0x3FFFFFFF )
          {
            CoTaskMemFree(pv);
            TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v38);
            return 2147942934LL;
          }
          v10 = (struct IXMLDOMDocument *)CoTaskMemRealloc(v10, 4LL * v20);
          v38 = v10;
          if ( !v10 )
          {
            CoTaskMemFree(pv);
            TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v38);
            return 2147942414LL;
          }
        }
        v21 = 0;
        v42 = 0;
        if ( *v66 == TMetabase_XMLtable::m_kMBProperty_Custom )
        {
          LODWORD(v10->lpVtbl) = *v65;
          v21 = 1;
          v42 = 1;
        }
        v41 = 1;
        v22 = 1;
        v46 = 1;
        v23 = (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 210) + 8 * v18 + 12) + 1);
        v13 = pv;
        while ( 1 )
        {
          v43 = v23;
          if ( v22 >= *(_DWORD *)(*((_QWORD *)this + 210) + 8 * v48 + 8) )
          {
            v33 = 0;
            for ( j = HIDWORD(v40); v33 < j; ++v33 )
            {
              v35 = v13[4 * v33];
              if ( v35 != -1 )
              {
                v36 = v47;
                *(_DWORD *)(*((_QWORD *)this + 197) + 4LL * v47) = v35;
                v47 = v36 + 1;
              }
            }
            v3 = (char *)(this + 16);
LABEL_81:
            v12 = v44 + 1;
            goto LABEL_19;
          }
          v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 222) + 32LL))(
                  *((_QWORD *)this + 222),
                  v23,
                  9);
          if ( v24 < 0 )
          {
            CoTaskMemFree(v13);
            TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v38);
            return (unsigned int)v24;
          }
          if ( *v66 == TMetabase_XMLtable::m_kMBProperty_Custom )
          {
            if ( v21 )
            {
              v25 = 0;
              do
              {
                if ( *v65 == *((_DWORD *)&v10->lpVtbl + v25) )
                  break;
                v25 = (unsigned int)(v25 + 1);
              }
              while ( (unsigned int)v25 < v21 );
              if ( (unsigned int)v25 < v21 )
              {
                swprintf_s(Buffer, 0xCu, L"%d");
                v26 = *((_DWORD *)this + 406);
                if ( v26 < 0x32 )
                {
                  *((_DWORD *)this + 406) = v26 + 1;
                  v57 = 0;
                  CErrorInterceptor::Init(
                    v56,
                    this + 896,
                    *((_QWORD *)this + 213),
                    2149647651LL,
                    2,
                    -1073606421,
                    Buffer,
                    *(_QWORD *)(*((_QWORD *)this + 210) + 8 * v48),
                    0,
                    0,
                    14,
                    L"MBProperty",
                    1,
                    -1,
                    -1,
                    this + 16,
                    2);
                  CErrorInterceptor::WriteToLog(
                    (CErrorInterceptor *)v56,
                    L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
                    1315,
                    *((_DWORD *)this + 413));
                  v27 = (CErrorInterceptor *)v56;
                  goto LABEL_50;
                }
                if ( v26 == 50 )
                {
                  *((_DWORD *)this + 406) = 51;
                  v59 = 0;
                  CErrorInterceptor::Init(
                    v58,
                    this + 896,
                    *((_QWORD *)this + 213),
                    2149647651LL,
                    2,
                    -1073606423,
                    this + 16,
                    0,
                    0,
                    0,
                    14,
                    L"MBProperty",
                    1,
                    -1,
                    -1,
                    this + 16,
                    2);
                  CErrorInterceptor::WriteToLog(
                    (CErrorInterceptor *)v58,
                    L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
                    1315,
                    *((_DWORD *)this + 413));
                  v27 = (CErrorInterceptor *)v58;
LABEL_50:
                  CErrorInterceptor::~CErrorInterceptor(v27);
                }
                --*((_DWORD *)this + 410);
                goto LABEL_75;
              }
            }
            *((_DWORD *)&v10->lpVtbl + v21) = *v65;
            v42 = v21 + 1;
          }
          v49 = v43;
          String2 = String1;
          v50 = String1;
          if ( _wcsicmp(String1, *(const wchar_t **)&v13[4 * (v41 - 1) + 2]) > 0 )
          {
            v11 = CCfgArray<TMetabase_XMLtable::TProperty>::InsertAt(&pv, &v49, HIDWORD(v40));
            if ( v11 < 0 )
              goto LABEL_72;
LABEL_73:
            v13 = pv;
            ++v41;
            goto LABEL_74;
          }
          v28 = 0;
          v29 = HIDWORD(v40);
          while ( v28 < v29 )
          {
            if ( _wcsicmp(*(const wchar_t **)&v13[4 * v28 + 2 + 4 * ((v29 - v28) >> 1)], String2) <= 0 )
              v28 += ((v29 - v28) >> 1) + 1;
            else
              v29 = v28 + ((v29 - v28) >> 1);
          }
          if ( !v28 || (v30 = String2, _wcsicmp(String2, *(const wchar_t **)&v13[4 * v28 - 2])) )
          {
            v11 = CCfgArray<TMetabase_XMLtable::TProperty>::InsertAt(&pv, &v49, v28);
            if ( v11 < 0 )
              goto LABEL_72;
            goto LABEL_73;
          }
          v31 = *((_DWORD *)this + 406);
          if ( v31 >= 0x32 )
          {
            if ( v31 != 50 )
              goto LABEL_70;
            *((_DWORD *)this + 406) = 51;
            v63 = 0;
            CErrorInterceptor::Init(
              v62,
              this + 896,
              *((_QWORD *)this + 213),
              2149647651LL,
              2,
              -1073606423,
              this + 16,
              0,
              0,
              0,
              14,
              L"MBProperty",
              1,
              -1,
              -1,
              this + 16,
              2);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)v62,
              L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
              1339,
              *((_DWORD *)this + 413));
            v32 = (CErrorInterceptor *)v62;
          }
          else
          {
            *((_DWORD *)this + 406) = v31 + 1;
            v61 = 0;
            CErrorInterceptor::Init(
              v60,
              this + 896,
              *((_QWORD *)this + 213),
              2149647651LL,
              2,
              -1073606424,
              v30,
              *(_QWORD *)(*((_QWORD *)this + 210) + 8 * v48),
              0,
              0,
              14,
              L"MBProperty",
              1,
              -1,
              -1,
              this + 16,
              2);
            CErrorInterceptor::WriteToLog(
              (CErrorInterceptor *)v60,
              L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
              1339,
              *((_DWORD *)this + 413));
            v32 = (CErrorInterceptor *)v60;
          }
          CErrorInterceptor::~CErrorInterceptor(v32);
LABEL_70:
          --*((_DWORD *)this + 410);
LABEL_74:
          v21 = v42;
LABEL_75:
          v23 = (unsigned int)(v43 + 1);
          v22 = ++v46;
        }
      }
      CoTaskMemFree(v13);
      TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v38);
LABEL_83:
      v37 = (TMetabase_XMLtable::TLocation *)*((_QWORD *)this + 210);
      if ( v37 )
        TMetabase_XMLtable::TLocation::`vector deleting destructor'(v37, v8);
      *((_QWORD *)this + 210) = 0;
      *((_QWORD *)this + 211) = 0;
      if ( *((_DWORD *)this + 406) )
      {
        swprintf_s(v69, 0x14u, L"(%d)");
        v50 = 0;
        CErrorInterceptor::Init(
          &v49,
          this + 896,
          *((_QWORD *)this + 213),
          2149647651LL,
          2,
          -1073559533,
          &word_180034198,
          0,
          0,
          0,
          14,
          L"MBProperty",
          1,
          -1,
          -1,
          v3,
          2);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)&v49,
          L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
          1386,
          12582912);
        CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v49);
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d110  mov     [rsp+arg_8], rbx
0x18000d115  mov     [rsp+arg_10], rsi
0x18000d11a  push    rdi
0x18000d11b  push    r12
0x18000d11d  push    r13
0x18000d11f  push    r14
0x18000d121  push    r15
0x18000d123  sub     rsp, 220h
0x18000d12a  mov     rax, cs:__security_cookie
0x18000d131  xor     rax, rsp
0x18000d134  mov     [rsp+248h+var_38], rax
0x18000d13c  mov     rdi, rcx
0x18000d13f  mov     rax, [rcx]
0x18000d142  xor     edx, edx
0x18000d144  mov     rax, [rax+48h]
0x18000d148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d14d  xor     r12d, r12d
0x18000d150  test    eax, eax
0x18000d152  js      loc_18000DFA4
0x18000d158  lea     r13, [rdi+20h]
0x18000d15c  mov     rcx, r13; lpFileName
0x18000d15f  call    cs:__imp_GetFileAttributesW
0x18000d165  cmp     eax, 0FFFFFFFFh
0x18000d168  jnz     short loc_18000D174
0x18000d16a  mov     eax, 80070002h
0x18000d16f  jmp     loc_18000DFA4
0x18000d174  lea     rcx, [rdi+7A0h]
0x18000d17b  lea     rbx, [rdi+10h]
0x18000d17f  mov     rax, [rcx]
0x18000d182  mov     r8, r13
0x18000d185  mov     rdx, rbx
0x18000d188  mov     rax, [rax+48h]
0x18000d18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d191  test    eax, eax
0x18000d193  jz      loc_18000D24A
0x18000d199  cmp     eax, 80210517h
0x18000d19e  jz      loc_18000D24A
0x18000d1a4  mov     [rsp+248h+var_198], r12
0x18000d1ac  movups  xmm0, xmmword ptr cs:?m_CLSID_DOMDocument30@TMSXMLBase@@1U_GUID@@A.Data1; _GUID TMSXMLBase::m_CLSID_DOMDocument30 ...
0x18000d1b3  movdqu  [rsp+248h+var_88], xmm0
0x18000d1bc  mov     rax, [rbx]
0x18000d1bf  lea     rcx, [rsp+248h+var_198]
0x18000d1c7  mov     [rsp+248h+var_220], rcx
0x18000d1cc  lea     rcx, IID_IXMLDOMDocument
0x18000d1d3  mov     [rsp+248h+var_228], rcx
0x18000d1d8  mov     r9d, 1
0x18000d1de  xor     r8d, r8d
0x18000d1e1  lea     rdx, [rsp+248h+var_88]
0x18000d1e9  mov     rcx, rbx
0x18000d1ec  mov     rax, [rax]
0x18000d1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1f4  mov     ebx, eax
0x18000d1f6  test    eax, eax
0x18000d1f8  jns     short loc_18000D20E
0x18000d1fa  lea     rcx, [rsp+248h+var_198]
0x18000d202  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x18000d207  mov     eax, ebx
0x18000d209  jmp     loc_18000DFA4
0x18000d20e  lea     rcx, [rdi-8]; this
0x18000d212  mov     r8b, [rdi+651h]; bool
0x18000d219  mov     rdx, [rsp+248h+var_198]; struct IXMLDOMDocument *
0x18000d221  call    ?ParseXMLFile@TMetabase_XMLtable@@AEAAJPEAUIXMLDOMDocument@@_N@Z; TMetabase_XMLtable::ParseXMLFile(IXMLDOMDocument *,bool)
0x18000d226  mov     ebx, eax
0x18000d228  lea     rcx, [rsp+248h+var_198]
0x18000d230  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x18000d235  test    ebx, ebx
0x18000d237  jns     short loc_18000D240
0x18000d239  mov     eax, ebx
0x18000d23b  jmp     loc_18000DFA4
0x18000d240  mov     eax, 80210514h
0x18000d245  jmp     loc_18000DFA4
0x18000d24a  mov     rsi, r12
0x18000d24d  mov     r14d, 1
0x18000d253  mov     rbx, rsi
0x18000d256  add     rbx, rbx
0x18000d259  mov     rcx, [rdi+rbx*8+568h]; pv
0x18000d261  call    cs:__imp_CoTaskMemFree
0x18000d267  mov     [rdi+rbx*8+568h], r12
0x18000d26f  lea     rax, [rsi+57h]
0x18000d273  add     rax, rax
0x18000d276  mov     [rdi+rax*8], r12
0x18000d27a  add     rsi, r14
0x18000d27d  cmp     rsi, 9
0x18000d281  jnz     short loc_18000D253
0x18000d283  mov     rax, [rdi]
0x18000d286  mov     rcx, rdi
0x18000d289  mov     rax, [rax+50h]
0x18000d28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d292  test    eax, eax
0x18000d294  js      loc_18000DFA4
0x18000d29a  cmp     [rdi+650h], r12b
0x18000d2a1  jz      loc_18000DE81
0x18000d2a7  mov     rcx, [rdi+6F0h]
0x18000d2ae  lea     rbx, [rdi+668h]
0x18000d2b5  mov     rax, [rcx]
0x18000d2b8  mov     [rsp+248h+var_228], r12
0x18000d2bd  mov     r9, rbx
0x18000d2c0  xor     r8d, r8d
0x18000d2c3  xor     edx, edx
0x18000d2c5  mov     rax, [rax+28h]
0x18000d2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2ce  mov     ecx, [rbx]
0x18000d2d0  mov     eax, 4
0x18000d2d5  mul     rcx
0x18000d2d8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d2df  cmovb   rax, rcx
0x18000d2e3  mov     rcx, rax; cb
0x18000d2e6  call    cs:__imp_CoTaskMemAlloc
0x18000d2ec  mov     [rdi+628h], rax
0x18000d2f3  test    rax, rax
0x18000d2f6  jnz     short loc_18000D302
0x18000d2f8  mov     eax, 8007000Eh
0x18000d2fd  jmp     loc_18000DFA4
0x18000d302  mov     rbx, r12
0x18000d305  mov     [rsp+248h+var_198], rbx
0x18000d30d  mov     [rsp+248h+pv], r12
0x18000d315  mov     [rsp+248h+var_188], r12
0x18000d31d  mov     edx, [rdi+660h]
0x18000d323  lea     rcx, [rsp+248h+pv]
0x18000d32b  call    ?SetSize@?$CCfgArray@VTProperty@TMetabase_XMLtable@@@@QEAAJK@Z; CCfgArray<TMetabase_XMLtable::TProperty>::SetSize(ulong)
0x18000d330  mov     esi, eax
0x18000d332  test    eax, eax
0x18000d334  jns     short loc_18000D359
0x18000d336  mov     rcx, [rsp+248h+pv]; pv
0x18000d33e  call    cs:__imp_CoTaskMemFree
0x18000d344  nop
0x18000d345  lea     rcx, [rsp+248h+var_198]
0x18000d34d  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x18000d352  mov     eax, esi
0x18000d354  jmp     loc_18000DFA4
0x18000d359  mov     [rsp+248h+var_170], r12d
0x18000d361  mov     [rsp+248h+var_168], r12d
0x18000d369  mov     eax, r12d
0x18000d36c  mov     r15d, 2
0x18000d372  mov     r12, [rsp+248h+pv]
0x18000d37a  mov     [rsp+248h+var_174], eax
0x18000d381  cmp     eax, [rdi+69Ch]
0x18000d387  jnb     loc_18000DE65
0x18000d38d  xor     edx, edx
0x18000d38f  lea     rcx, [rsp+248h+pv]
0x18000d397  call    ?SetSize@?$CCfgArray@VTProperty@TMetabase_XMLtable@@@@QEAAJK@Z; CCfgArray<TMetabase_XMLtable::TProperty>::SetSize(ulong)
0x18000d39c  mov     esi, eax
0x18000d39e  test    eax, eax
0x18000d3a0  jns     short loc_18000D3C5
0x18000d3a2  mov     rcx, [rsp+248h+pv]; pv
0x18000d3aa  call    cs:__imp_CoTaskMemFree
0x18000d3b0  nop
0x18000d3b1  lea     rcx, [rsp+248h+var_198]
0x18000d3b9  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x18000d3be  mov     eax, esi
0x18000d3c0  jmp     loc_18000DFA4
0x18000d3c5  mov     r12d, [rsp+248h+var_174]
0x18000d3cd  test    r12d, r12d
0x18000d3d0  jz      loc_18000D5DB
0x18000d3d6  mov     r8, [rdi+690h]
0x18000d3dd  lea     rsi, [r12+r12*2]
0x18000d3e1  lea     eax, [r12-1]
0x18000d3e6  lea     rax, [rax+rax*2]
0x18000d3ea  lea     rdx, [r8+rax*8]; struct TMetabase_XMLtable::TLocation *
0x18000d3ee  lea     rcx, [r8+rsi*8]; this
0x18000d3f2  call    ?CompareLocation@TLocation@TMetabase_XMLtable@@AEBAHAEBV12@@Z; TMetabase_XMLtable::TLocation::CompareLocation(TMetabase_XMLtable::TLocation const &)
0x18000d3f7  cmp     eax, r15d
0x18000d3fa  jnz     loc_18000D5DB
0x18000d400  mov     eax, [rdi+658h]
0x18000d406  cmp     eax, 32h ; '2'
0x18000d409  jnb     loc_18000D4E8
0x18000d40f  inc     eax
0x18000d411  mov     [rdi+658h], eax
0x18000d417  xor     r8d, r8d
0x18000d41a  mov     [rsp+248h+var_130], r8
0x18000d422  mov     rcx, [rdi+690h]
0x18000d429  lea     rdx, [rdi+700h]
0x18000d430  or      r9d, 0FFFFFFFFh
0x18000d434  mov     [rsp+248h+var_1A8], r9d
0x18000d43c  mov     eax, [rdi+6A0h]
0x18000d442  mov     [rsp+248h+var_1B0], eax
0x18000d449  mov     [rsp+248h+var_1C8], r15d
0x18000d451  mov     [rsp+248h+var_1D0], r13
0x18000d456  mov     [rsp+248h+var_1D8], r9d
0x18000d45b  mov     [rsp+248h+var_1E0], r9d
0x18000d460  mov     [rsp+248h+var_1E8], r14d
0x18000d465  lea     rax, aMbproperty; "MBProperty"
0x18000d46c  mov     [rsp+248h+var_1F0], rax
0x18000d471  mov     [rsp+248h+var_1F8], 0Eh
0x18000d479  mov     [rsp+248h+var_200], r8
0x18000d47e  mov     [rsp+248h+var_208], r8
0x18000d483  mov     [rsp+248h+var_210], r8
0x18000d488  mov     rax, [rcx+rsi*8]
0x18000d48c  mov     [rsp+248h+var_218], rax
0x18000d491  mov     dword ptr [rsp+248h+var_220], 800210D5h
0x18000d499  mov     dword ptr [rsp+248h+var_228], r15d
0x18000d49e  mov     r9d, 80210523h
0x18000d4a4  mov     r8, [rdi+6A8h]
0x18000d4ab  lea     rcx, [rsp+248h+var_138]
0x18000d4b3  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000d4b8  nop
0x18000d4b9  mov     r9d, [rdi+674h]; unsigned int
0x18000d4c0  mov     r8d, 4E7h; unsigned int
0x18000d4c6  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000d4cd  lea     rcx, [rsp+248h+var_138]; this
0x18000d4d5  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000d4da  nop
0x18000d4db  lea     rcx, [rsp+248h+var_138]
0x18000d4e3  jmp     loc_18000D5B8
0x18000d4e8  jnz     loc_18000D5BD
0x18000d4ee  mov     dword ptr [rdi+658h], 33h ; '3'
0x18000d4f8  xor     ecx, ecx
0x18000d4fa  mov     [rsp+248h+var_120], rcx
0x18000d502  lea     rdx, [rdi+700h]
0x18000d509  or      r8d, 0FFFFFFFFh
0x18000d50d  mov     [rsp+248h+var_1A8], r8d
0x18000d515  mov     eax, [rdi+6A0h]
0x18000d51b  mov     [rsp+248h+var_1B0], eax
0x18000d522  mov     [rsp+248h+var_1C8], r15d
0x18000d52a  mov     [rsp+248h+var_1D0], r13
0x18000d52f  mov     [rsp+248h+var_1D8], r8d
0x18000d534  mov     [rsp+248h+var_1E0], r8d
0x18000d539  mov     [rsp+248h+var_1E8], r14d
0x18000d53e  lea     rax, aMbproperty; "MBProperty"
0x18000d545  mov     [rsp+248h+var_1F0], rax
0x18000d54a  mov     [rsp+248h+var_1F8], 0Eh
0x18000d552  mov     [rsp+248h+var_200], rcx
0x18000d557  mov     [rsp+248h+var_208], rcx
0x18000d55c  mov     [rsp+248h+var_210], rcx
0x18000d561  mov     [rsp+248h+var_218], r13
0x18000d566  mov     dword ptr [rsp+248h+var_220], 0C00210E9h
0x18000d56e  mov     dword ptr [rsp+248h+var_228], r15d
0x18000d573  mov     r9d, 80210523h
0x18000d579  mov     r8, [rdi+6A8h]
0x18000d580  lea     rcx, [rsp+248h+var_128]
0x18000d588  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000d58d  nop
0x18000d58e  mov     r9d, [rdi+674h]; unsigned int
0x18000d595  mov     r8d, 4E7h; unsigned int
0x18000d59b  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000d5a2  lea     rcx, [rsp+248h+var_128]; this
0x18000d5aa  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000d5af  nop
0x18000d5b0  lea     rcx, [rsp+248h+var_128]; this
0x18000d5b8  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18000d5bd  mov     rax, [rdi+690h]
0x18000d5c4  mov     ecx, [rax+rsi*8+8]
0x18000d5c8  sub     [rdi+668h], ecx
0x18000d5ce  mov     r12, [rsp+248h+pv]
0x18000d5d6  jmp     loc_18000DE56
0x18000d5db  xor     edx, edx; Val
0x18000d5dd  lea     r8d, [rdx+48h]; Size
0x18000d5e1  lea     rcx, [rsp+248h+String1]; void *
0x18000d5e9  call    memset_0
0x18000d5ee  mov     rcx, [rdi+6F0h]
0x18000d5f5  lea     r12, [r12+r12*2]
0x18000d5f9  mov     [rsp+248h+var_160], r12
0x18000d601  mov     rax, [rcx]
0x18000d604  mov     rdx, [rdi+690h]
0x18000d60b  lea     r8, [rsp+248h+String1]
0x18000d613  mov     [rsp+248h+var_220], r8
0x18000d618  lea     r8, [rsp+248h+var_60]
0x18000d620  mov     [rsp+248h+var_228], r8
0x18000d625  xor     r9d, r9d
0x18000d628  lea     r8d, [r9+9]
0x18000d62c  mov     edx, [rdx+r12*8+0Ch]
0x18000d631  mov     rax, [rax+20h]
0x18000d635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d63a  mov     esi, eax
0x18000d63c  test    eax, eax
0x18000d63e  jns     short loc_18000D663
0x18000d640  mov     rcx, [rsp+248h+pv]; pv
0x18000d648  call    cs:__imp_CoTaskMemFree
0x18000d64e  nop
0x18000d64f  lea     rcx, [rsp+248h+var_198]
0x18000d657  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x18000d65c  mov     eax, esi
0x18000d65e  jmp     loc_18000DFA4
0x18000d663  mov     rax, [rdi+690h]
0x18000d66a  mov     ecx, [rax+r12*8+0Ch]
0x18000d66f  mov     dword ptr [rsp+248h+var_88], ecx
0x18000d676  mov     rax, [rsp+248h+String1]
0x18000d67e  mov     qword ptr [rsp+248h+var_88+8], rax
0x18000d686  mov     r8d, dword ptr [rsp+248h+var_188+4]
0x18000d68e  lea     rdx, [rsp+248h+var_88]
0x18000d696  lea     rcx, [rsp+248h+pv]
0x18000d69e  call    ?InsertAt@?$CCfgArray@VTProperty@TMetabase_XMLtable@@@@QEAAJAEBVTProperty@TMetabase_XMLtable@@K@Z; CCfgArray<TMetabase_XMLtable::TProperty>::InsertAt(TMetabase_XMLtable::TProperty const &,ulong)
0x18000d6a3  mov     esi, eax
0x18000d6a5  test    eax, eax
0x18000d6a7  jns     short loc_18000D6CC
0x18000d6a9  mov     rcx, [rsp+248h+pv]; pv
0x18000d6b1  call    cs:__imp_CoTaskMemFree
0x18000d6b7  nop
0x18000d6b8  lea     rcx, [rsp+248h+var_198]
0x18000d6c0  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x18000d6c5  mov     eax, esi
0x18000d6c7  jmp     loc_18000DFA4
0x18000d6cc  mov     rax, [rdi+690h]
0x18000d6d3  mov     ecx, [rax+r12*8+8]
0x18000d6d8  cmp     [rsp+248h+var_170], ecx
0x18000d6df  jnb     short loc_18000D760
0x18000d6e1  lea     eax, [rcx+3Fh]
0x18000d6e4  and     eax, 0FFFFFFC0h
0x18000d6e7  mov     [rsp+248h+var_170], eax
0x18000d6ee  cmp     eax, 3FFFFFFFh
  ... truncated ...
```
