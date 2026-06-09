# UpdateConfigRefreshPausePeriod(ushort const *,ulong)

- ea: `0x1800df46c`
- end: `0x1800dfd82`
- name: `?UpdateConfigRefreshPausePeriod@@YAJPEBGK@Z`
- size: `2326`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c270`
- `0x180033dc0`

## callees

- `0x180008de0`
- `0x1800091b0`
- `0x18000d4d4`
- `0x18001a4fc`
- `0x1800637f4`
- `0x180063870`
- `0x1800639d0`
- `0x1800d11a4`
- `0x1800d14ec`
- `0x1800d7e58`
- `0x1800d7e90`
- `0x1800df46c`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfa21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfa21`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df714`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df818`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df8b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dfad4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dfc34`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df714`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df818`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df8b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dfad4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dfc34`
- `OLEAUT32!__imp_VariantInit` at `0x1800df5c9`
- `OLEAUT32!__imp_VariantInit` at `0x1800df5e4`
- `OLEAUT32!__imp_VariantInit` at `0x1800df5ff`
- `OLEAUT32!__imp_VariantInit` at `0x1800df618`
- `OLEAUT32!__imp_VariantInit` at `0x1800dfb3c`
- `OLEAUT32!__imp_VariantInit` at `0x1800dfb55`
- `OLEAUT32!__imp_VariantInit` at `0x1800df5c9`
- `OLEAUT32!__imp_VariantInit` at `0x1800df5e4`
- `OLEAUT32!__imp_VariantInit` at `0x1800df5ff`
- `OLEAUT32!__imp_VariantInit` at `0x1800df618`
- `OLEAUT32!__imp_VariantInit` at `0x1800dfb3c`
- `OLEAUT32!__imp_VariantInit` at `0x1800dfb55`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800df981`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800df981`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dfcb1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dfcb1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800df999`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800df999`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800dfa11`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800dfa11`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800df7a8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800dfd2b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800df7a8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800dfd2b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800df546`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800df546`

## string_xrefs

- `0x1800df856`: `Schedule created by dm client to refresh settings`
- `0x1800dfb81`: `Schedule created by dm client to refresh settings`
- `0x1800dfc99`: `24RegisterTaskDefinition`
- `0x1800dfcc6`: `UpdateConfigRefreshPausePeriod`

## pseudocode

```c
__int64 __fastcall UpdateConfigRefreshPausePeriod(const unsigned __int16 *a1, unsigned int a2)
{
  __int64 v3; // rsi
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v9; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v11; // xmm8
  IRecordInfo *v12; // xmm9_8
  __int128 v13; // xmm6
  IRecordInfo *v14; // xmm7_8
  LPVOID v15; // rbx
  __int64 (__fastcall *v16)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v17; // rax
  __int64 v18; // rdx
  int v19; // eax
  BSTR *v20; // rbx
  int v21; // edi
  BSTR v22; // rcx
  __int64 v23; // rdx
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, __int64, __int64 *); // rdi
  _bstr_t *v27; // rax
  __int64 v28; // rdx
  int v29; // eax
  BSTR *v30; // rbx
  BSTR v31; // rcx
  __int64 v32; // rbx
  __int64 (__fastcall *v33)(__int64, __int64, __int64 *); // rdi
  _bstr_t *v34; // rax
  __int64 v35; // rdx
  int v36; // eax
  BSTR *v37; // rbx
  BSTR v38; // rcx
  BOOL v39; // eax
  void *v40; // rax
  unsigned int v41; // r8d
  signed int LastError; // eax
  __int64 v43; // rbx
  __int64 (__fastcall *v44)(__int64, __int64); // rdi
  _bstr_t *v45; // rax
  __int64 v46; // rdx
  int v47; // eax
  BSTR *v48; // rbx
  BSTR v49; // rcx
  __int64 v50; // rbx
  __int64 (__fastcall *v51)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, VARIANTARG *, __int64 *); // rsi
  __int128 v52; // xmm6
  IRecordInfo *v53; // xmm7_8
  __int128 v54; // xmm8
  IRecordInfo *v55; // xmm9_8
  _variant_t *v56; // rax
  __int64 v57; // rdi
  __int128 v58; // xmm10
  IRecordInfo *v59; // xmm11_8
  _bstr_t *v60; // rax
  __int64 v61; // rdx
  int v62; // eax
  BSTR *v63; // rbx
  BSTR v64; // rcx
  CEnrollmentLogger *Logger; // rax
  int ppv; // [rsp+28h] [rbp-E0h]
  int *ppva; // [rsp+28h] [rbp-E0h]
  int Data; // [rsp+58h] [rbp-B0h] BYREF
  int Data_4; // [rsp+5Ch] [rbp-ACh] BYREF
  void *Block; // [rsp+60h] [rbp-A8h] BYREF
  struct _FILETIME FileTime; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v72; // [rsp+70h] [rbp-98h] BYREF
  __int64 v73; // [rsp+78h] [rbp-90h] BYREF
  __int64 v74; // [rsp+80h] [rbp-88h] BYREF
  __int64 v75; // [rsp+88h] [rbp-80h] BYREF
  LPVOID v76; // [rsp+90h] [rbp-78h] BYREF
  __int64 v77; // [rsp+98h] [rbp-70h] BYREF
  __int64 v78; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG v79; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v81; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v82; // [rsp+E8h] [rbp-20h]
  __int128 v83; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v84; // [rsp+108h] [rbp+0h]
  VARIANTARG v85; // [rsp+118h] [rbp+10h] BYREF
  int v86[4]; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v87; // [rsp+148h] [rbp+40h]
  VARIANTARG v88; // [rsp+158h] [rbp+50h] BYREF
  VARIANTARG v89; // [rsp+170h] [rbp+68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+188h] [rbp+80h] BYREF
  unsigned __int16 v91[264]; // [rsp+198h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+450h] [rbp+348h]

  v3 = a2;
  Data = 0;
  v4 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&Data, a2);
  Data_4 = v4;
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1832,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
LABEL_97:
    if ( Data )
      CoUninitialize();
    return (unsigned int)v5;
  }
  v76 = 0;
  v78 = 0;
  v75 = 0;
  v74 = 0;
  v72 = 0;
  v73 = 0;
  v77 = 0;
  SystemTime = 0;
  v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v76);
  if ( v5 < 0 )
  {
    v6 = 6209;
    goto LABEL_5;
  }
  v7 = v76;
  v8 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v76 + 80LL);
  VariantInit(&pvarg);
  v9 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v79);
  v11 = *(_OWORD *)&v79.vt;
  v12 = v79.pRecInfo;
  VariantInit(&v89);
  v13 = *(_OWORD *)&v89.vt;
  v14 = v89.pRecInfo;
  VariantInit(&v88);
  ppva = v86;
  v85 = v88;
  *(_OWORD *)v86 = v9;
  v87 = pRecInfo;
  v81 = v11;
  v82 = v12;
  v83 = v13;
  v84 = v14;
  v5 = v8(v7, &v85, &v83, &v81);
  _variant_t::~_variant_t((_variant_t *)&v88);
  _variant_t::~_variant_t((_variant_t *)&v89);
  _variant_t::~_variant_t((_variant_t *)&v79);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( v5 < 0 )
  {
    v6 = 6211;
    goto LABEL_5;
  }
  v15 = v76;
  v16 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v76 + 56LL);
  v17 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical");
  if ( *(_QWORD *)v17 )
    v18 = **(_QWORD **)v17;
  else
    v18 = 0;
  v19 = v16(v15, v18, &v78);
  v20 = (BSTR *)Block;
  v21 = v19;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v20 )
  {
    if ( *v20 )
    {
      SysFreeString(*v20);
      *v20 = 0;
    }
    v22 = v20[1];
    if ( v22 )
    {
      operator delete(v22);
      v20[1] = 0;
    }
    operator delete(v20);
  }
  if ( v21 >= 0 )
  {
    v25 = v78;
    v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v78 + 72LL);
    v27 = _bstr_t::_bstr_t((_bstr_t *)&Block, a1);
    if ( *(_QWORD *)v27 )
      v28 = **(_QWORD **)v27;
    else
      v28 = 0;
    v29 = v26(v25, v28, &v75);
    v30 = (BSTR *)Block;
    v21 = v29;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v30 )
    {
      if ( *v30 )
      {
        SysFreeString(*v30);
        *v30 = 0;
      }
      v31 = v30[1];
      if ( v31 )
      {
        operator delete(v31);
        v30[1] = 0;
      }
      operator delete(v30);
    }
    if ( v21 < 0 )
    {
      v23 = 6215;
      goto LABEL_22;
    }
    v32 = v75;
    v33 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v75 + 104LL);
    v34 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Schedule created by dm client to refresh settings");
    if ( *(_QWORD *)v34 )
      v35 = **(_QWORD **)v34;
    else
      v35 = 0;
    v36 = v33(v32, v35, &v74);
    v37 = (BSTR *)Block;
    Data_4 = v36;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v37 )
    {
      if ( *v37 )
      {
        SysFreeString(*v37);
        *v37 = 0;
      }
      v38 = v37[1];
      if ( v38 )
      {
        operator delete(v38);
        v37[1] = 0;
      }
      operator delete(v37);
    }
    v5 = Data_4;
    if ( Data_4 < 0 )
    {
      v6 = 6218;
      goto LABEL_5;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v74 + 152LL))(v74, &v72);
    if ( v5 < 0 )
    {
      v6 = 6220;
      goto LABEL_5;
    }
    Data_4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v72 + 72LL))(v72, &v73);
    v5 = Data_4;
    if ( Data_4 < 0 )
    {
      v6 = 6224;
      goto LABEL_5;
    }
    Data_4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v73 + 64LL))(v73, 1, &v77);
    v5 = Data_4;
    if ( Data_4 < 0 )
    {
      v6 = 6228;
      goto LABEL_5;
    }
    FileTime = 0;
    GetSystemTime(&SystemTime);
    v39 = SystemTimeToFileTime(&SystemTime, &FileTime);
    if ( (_DWORD)v3 )
    {
      if ( v39 )
      {
        Block = (void *)FileTime;
        v40 = (void *)(600000000 * v3 + *(_QWORD *)&FileTime);
LABEL_62:
        Block = v40;
        v5 = 0;
        FileTime = (struct _FILETIME)v40;
        if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
          goto LABEL_65;
      }
    }
    else if ( v39 )
    {
      Block = (void *)FileTime;
      v40 = (void *)(*(_QWORD *)&FileTime + 600000000LL);
      goto LABEL_62;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_65:
    Data_4 = v5;
    if ( v5 >= 0 )
    {
      Data_4 = CreateDelayTimeString(&SystemTime, v91, v41);
      v5 = Data_4;
      if ( Data_4 >= 0 )
      {
        v43 = v77;
        v44 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v77 + 120LL);
        v45 = _bstr_t::_bstr_t((_bstr_t *)&Block, v91);
        if ( *(_QWORD *)v45 )
          v46 = **(_QWORD **)v45;
        else
          v46 = 0;
        v47 = v44(v43, v46);
        v48 = (BSTR *)Block;
        Data_4 = v47;
        if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v48 )
        {
          if ( *v48 )
          {
            SysFreeString(*v48);
            *v48 = 0;
          }
          v49 = v48[1];
          if ( v49 )
          {
            operator delete(v49);
            v48[1] = 0;
          }
          operator delete(v48);
        }
        Data_4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 80LL))(v72, v73);
        v5 = Data_4;
        if ( Data_4 >= 0 )
        {
          v50 = v75;
          v51 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, VARIANTARG *, __int64 *))(*(_QWORD *)v75 + 136LL);
          VariantInit(&v79);
          v52 = *(_OWORD *)&v79.vt;
          v53 = v79.pRecInfo;
          VariantInit(&pvarg);
          v54 = *(_OWORD *)&pvarg.vt;
          v55 = pvarg.pRecInfo;
          v56 = _variant_t::_variant_t((_variant_t *)v86, L"S-1-5-18");
          v57 = v72;
          v58 = *(_OWORD *)v56;
          v59 = (IRecordInfo *)*((_QWORD *)v56 + 2);
          v60 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Schedule created by dm client to refresh settings");
          if ( *(_QWORD *)v60 )
            v61 = **(_QWORD **)v60;
          else
            v61 = 0;
          *(_OWORD *)&v85.vt = v52;
          v85.pRecInfo = v53;
          v83 = v54;
          v84 = v55;
          v81 = v58;
          v82 = v59;
          v62 = v51(v50, v61, v57, 6, &v81, &v83, 3, &v85, &v74);
          v63 = (BSTR *)Block;
          Data_4 = v62;
          if ( Block )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v63 )
            {
              if ( *v63 )
              {
                SysFreeString(*v63);
                *v63 = 0;
              }
              v64 = v63[1];
              if ( v64 )
              {
                operator delete(v64);
                v63[1] = 0;
              }
              operator delete(v63);
            }
            Block = 0;
          }
          _variant_t::~_variant_t((_variant_t *)v86);
          _variant_t::~_variant_t((_variant_t *)&pvarg);
          _variant_t::~_variant_t((_variant_t *)&v79);
          if ( Data_4 >= 0 )
          {
            ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v77);
            ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v73);
            ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v72);
            ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v74);
            ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v75);
            ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v78);
            ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v76);
            v5 = Data_4;
            goto LABEL_97;
          }
          RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"24RegisterTaskDefinition", 4u, &Data_4, 4u);
          Logger = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Data_4, "UpdateConfigRefreshPausePeriod");
          v5 = Data_4;
          goto LABEL_6;
        }
        v6 = 6247;
      }
      else
      {
        v6 = 6242;
      }
    }
    else
    {
      v6 = 6239;
    }
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v5,
      (int)ppva);
LABEL_6:
    ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v77);
    ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v73);
    ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v72);
    ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v74);
    ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v75);
    ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v78);
    ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v76);
    goto LABEL_97;
  }
  v23 = 6213;
LABEL_22:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
    (const char *)(unsigned int)v21,
    (int)v86);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v77);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v73);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v72);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v74);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v75);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v78);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v76);
  if ( Data )
    CoUninitialize();
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1800df46c  mov     rax, rsp
0x1800df46f  mov     [rax+18h], rbx
0x1800df473  push    rbp
0x1800df474  push    rsi
0x1800df475  push    rdi
0x1800df476  push    r12
0x1800df478  push    r13
0x1800df47a  push    r14
0x1800df47c  push    r15
0x1800df47e  lea     rbp, [rax-348h]
0x1800df485  sub     rsp, 410h
0x1800df48c  movaps  xmmword ptr [rax-48h], xmm6
0x1800df490  movaps  xmmword ptr [rax-58h], xmm7
0x1800df494  movaps  xmmword ptr [rax-68h], xmm8
0x1800df499  movaps  xmmword ptr [rax-78h], xmm9
0x1800df49e  movaps  xmmword ptr [rax-88h], xmm10
0x1800df4a6  movaps  xmmword ptr [rax-98h], xmm11
0x1800df4ae  mov     rax, cs:__security_cookie
0x1800df4b5  xor     rax, rsp
0x1800df4b8  mov     [rbp+340h+var_A0], rax
0x1800df4bf  mov     r14, rcx
0x1800df4c2  mov     esi, edx
0x1800df4c4  xor     r15d, r15d
0x1800df4c7  lea     rcx, [rsp+440h+Data]; this
0x1800df4cc  mov     dword ptr [rsp+440h+Data], r15d
0x1800df4d1  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800df4d6  mov     dword ptr [rsp+440h+Data+4], eax
0x1800df4da  mov     ebx, eax
0x1800df4dc  test    eax, eax
0x1800df4de  jns     short loc_1800DF500
0x1800df4e0  mov     rcx, [rbp+348h]; this
0x1800df4e7  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800df4ee  mov     r9d, eax; char *
0x1800df4f1  mov     edx, 1832h; void *
0x1800df4f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df4fb  jmp     loc_1800DFD24
0x1800df500  xor     edx, edx; pUnkOuter
0x1800df502  mov     [rbp+340h+var_3B8], r15
0x1800df506  xorps   xmm0, xmm0
0x1800df509  mov     [rbp+340h+var_3A8], r15
0x1800df50d  lea     rax, [rbp+340h+var_3B8]
0x1800df511  mov     [rbp+340h+var_3C0], r15
0x1800df515  lea     r9, IID_ITaskService; riid
0x1800df51c  mov     [rsp+440h+var_3C8], r15
0x1800df521  lea     r8d, [rdx+1]; dwClsContext
0x1800df525  mov     [rsp+440h+var_3D8], r15
0x1800df52a  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800df531  mov     [rsp+440h+var_3D0], r15
0x1800df536  mov     [rbp+340h+var_3B0], r15
0x1800df53a  movups  xmmword ptr [rbp+340h+SystemTime.wYear], xmm0
0x1800df541  mov     [rsp+440h+ppv], rax; int
0x1800df546  call    cs:__imp_CoCreateInstance
0x1800df54d  nop     dword ptr [rax+rax+00h]
0x1800df552  mov     ebx, eax
0x1800df554  test    eax, eax
0x1800df556  jns     short loc_1800DF5BA
0x1800df558  mov     edx, 1841h; void *
0x1800df55d  mov     rcx, [rbp+348h]; this
0x1800df564  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800df56b  mov     r9d, ebx; char *
0x1800df56e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df573  lea     rcx, [rbp+340h+var_3B0]
0x1800df577  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df57c  lea     rcx, [rsp+440h+var_3D0]
0x1800df581  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df586  lea     rcx, [rsp+440h+var_3D8]
0x1800df58b  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df590  lea     rcx, [rsp+440h+var_3C8]
0x1800df595  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df59a  lea     rcx, [rbp+340h+var_3C0]
0x1800df59e  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df5a3  lea     rcx, [rbp+340h+var_3A8]
0x1800df5a7  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df5ac  lea     rcx, [rbp+340h+var_3B8]
0x1800df5b0  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df5b5  jmp     loc_1800DFD24
0x1800df5ba  mov     rdi, [rbp+340h+var_3B8]
0x1800df5be  lea     rcx, [rbp+340h+pvarg]; pvarg
0x1800df5c2  mov     rax, [rdi]
0x1800df5c5  mov     rbx, [rax+50h]
0x1800df5c9  call    cs:__imp_VariantInit
0x1800df5d0  nop     dword ptr [rax+rax+00h]
0x1800df5d5  movups  xmm10, xmmword ptr [rbp+340h+pvarg]
0x1800df5da  lea     rcx, [rbp+340h+var_3A0]; pvarg
0x1800df5de  movsd   xmm11, qword ptr [rbp+340h+pvarg+10h]
0x1800df5e4  call    cs:__imp_VariantInit
0x1800df5eb  nop     dword ptr [rax+rax+00h]
0x1800df5f0  movups  xmm8, xmmword ptr [rbp+340h+var_3A0]
0x1800df5f5  lea     rcx, [rbp+340h+var_2D8]; pvarg
0x1800df5f9  movsd   xmm9, qword ptr [rbp+340h+var_3A0+10h]
0x1800df5ff  call    cs:__imp_VariantInit
0x1800df606  nop     dword ptr [rax+rax+00h]
0x1800df60b  movups  xmm6, xmmword ptr [rbp+340h+var_2D8]
0x1800df60f  lea     rcx, [rbp+340h+var_2F0]; pvarg
0x1800df613  movsd   xmm7, qword ptr [rbp+340h+var_2D8+10h]
0x1800df618  call    cs:__imp_VariantInit
0x1800df61f  nop     dword ptr [rax+rax+00h]
0x1800df624  movups  xmm0, xmmword ptr [rbp+340h+var_2F0]
0x1800df628  lea     rax, [rbp+340h+var_310]
0x1800df62c  mov     rcx, rdi
0x1800df62f  movsd   xmm1, qword ptr [rbp+340h+var_2F0+10h]
0x1800df634  lea     r9, [rbp+340h+var_370]
0x1800df638  mov     [rsp+440h+ppv], rax; int
0x1800df63d  lea     r8, [rbp+340h+var_350]
0x1800df641  mov     rax, rbx
0x1800df644  movaps  [rbp+340h+var_330], xmm0
0x1800df648  lea     rdx, [rbp+340h+var_330]
0x1800df64c  movaps  xmmword ptr [rbp+340h+var_310], xmm10
0x1800df651  movsd   [rbp+340h+var_300], xmm11
0x1800df657  movaps  [rbp+340h+var_370], xmm8
0x1800df65c  movsd   [rbp+340h+var_360], xmm9
0x1800df662  movaps  [rbp+340h+var_350], xmm6
0x1800df666  movsd   [rbp+340h+var_340], xmm7
0x1800df66b  movsd   [rbp+340h+var_320], xmm1
0x1800df670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df675  lea     rcx, [rbp+340h+var_2F0]; this
0x1800df679  mov     ebx, eax
0x1800df67b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800df680  lea     rcx, [rbp+340h+var_2D8]; this
0x1800df684  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800df689  lea     rcx, [rbp+340h+var_3A0]; this
0x1800df68d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800df692  lea     rcx, [rbp+340h+pvarg]; this
0x1800df696  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800df69b  test    ebx, ebx
0x1800df69d  jns     short loc_1800DF6A9
0x1800df69f  mov     edx, 1843h
0x1800df6a4  jmp     loc_1800DF55D
0x1800df6a9  mov     rbx, [rbp+340h+var_3B8]
0x1800df6ad  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x1800df6b4  lea     rcx, [rsp+440h+Block]; this
0x1800df6b9  mov     rax, [rbx]
0x1800df6bc  mov     rdi, [rax+38h]
0x1800df6c0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800df6c5  mov     rcx, [rax]
0x1800df6c8  test    rcx, rcx
0x1800df6cb  jz      short loc_1800DF6D2
0x1800df6cd  mov     rdx, [rcx]
0x1800df6d0  jmp     short loc_1800DF6D5
0x1800df6d2  mov     rdx, r15
0x1800df6d5  lea     r8, [rbp+340h+var_3A8]
0x1800df6d9  mov     rcx, rbx
0x1800df6dc  mov     rax, rdi
0x1800df6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df6e4  mov     rbx, [rsp+440h+Block]
0x1800df6e9  or      r12d, 0FFFFFFFFh
0x1800df6ed  mov     edi, eax
0x1800df6ef  mov     r13d, 18h
0x1800df6f5  test    rbx, rbx
0x1800df6f8  jz      short loc_1800DF740
0x1800df6fa  mov     ecx, r12d
0x1800df6fd  lock xadd [rbx+10h], ecx
0x1800df702  add     ecx, r12d
0x1800df705  jnz     short loc_1800DF740
0x1800df707  test    rbx, rbx
0x1800df70a  jz      short loc_1800DF740
0x1800df70c  mov     rcx, [rbx]; bstrString
0x1800df70f  test    rcx, rcx
0x1800df712  jz      short loc_1800DF723
0x1800df714  call    cs:__imp_SysFreeString
0x1800df71b  nop     dword ptr [rax+rax+00h]
0x1800df720  mov     [rbx], r15
0x1800df723  mov     rcx, [rbx+8]; Block
0x1800df727  test    rcx, rcx
0x1800df72a  jz      short loc_1800DF735
0x1800df72c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800df731  mov     [rbx+8], r15
0x1800df735  mov     rdx, r13
0x1800df738  mov     rcx, rbx; Block
0x1800df73b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800df740  test    edi, edi
0x1800df742  jns     short loc_1800DF7BB
0x1800df744  mov     edx, 1845h; void *
0x1800df749  mov     rcx, [rbp+348h]; this
0x1800df750  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800df757  mov     r9d, edi; char *
0x1800df75a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df75f  lea     rcx, [rbp+340h+var_3B0]
0x1800df763  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df768  lea     rcx, [rsp+440h+var_3D0]
0x1800df76d  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df772  lea     rcx, [rsp+440h+var_3D8]
0x1800df777  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df77c  lea     rcx, [rsp+440h+var_3C8]
0x1800df781  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df786  lea     rcx, [rbp+340h+var_3C0]
0x1800df78a  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df78f  lea     rcx, [rbp+340h+var_3A8]
0x1800df793  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df798  lea     rcx, [rbp+340h+var_3B8]
0x1800df79c  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800df7a1  cmp     dword ptr [rsp+440h+Data], r15d
0x1800df7a6  jz      short loc_1800DF7B4
0x1800df7a8  call    cs:__imp_CoUninitialize
0x1800df7af  nop     dword ptr [rax+rax+00h]
0x1800df7b4  mov     eax, edi
0x1800df7b6  jmp     loc_1800DFD39
0x1800df7bb  mov     rbx, [rbp+340h+var_3A8]
0x1800df7bf  lea     rcx, [rsp+440h+Block]; this
0x1800df7c4  mov     rdx, r14; unsigned __int16 *
0x1800df7c7  mov     rax, [rbx]
0x1800df7ca  mov     rdi, [rax+48h]
0x1800df7ce  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800df7d3  mov     rdx, [rax]
0x1800df7d6  test    rdx, rdx
0x1800df7d9  jz      short loc_1800DF7E0
0x1800df7db  mov     rdx, [rdx]
0x1800df7de  jmp     short loc_1800DF7E3
0x1800df7e0  mov     rdx, r15
0x1800df7e3  lea     r8, [rbp+340h+var_3C0]
0x1800df7e7  mov     rcx, rbx
0x1800df7ea  mov     rax, rdi
0x1800df7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df7f2  mov     rbx, [rsp+440h+Block]
0x1800df7f7  mov     edi, eax
0x1800df7f9  test    rbx, rbx
0x1800df7fc  jz      short loc_1800DF844
0x1800df7fe  mov     ecx, r12d
0x1800df801  lock xadd [rbx+10h], ecx
0x1800df806  add     ecx, r12d
0x1800df809  jnz     short loc_1800DF844
0x1800df80b  test    rbx, rbx
0x1800df80e  jz      short loc_1800DF844
0x1800df810  mov     rcx, [rbx]; bstrString
0x1800df813  test    rcx, rcx
0x1800df816  jz      short loc_1800DF827
0x1800df818  call    cs:__imp_SysFreeString
0x1800df81f  nop     dword ptr [rax+rax+00h]
0x1800df824  mov     [rbx], r15
0x1800df827  mov     rcx, [rbx+8]; Block
0x1800df82b  test    rcx, rcx
0x1800df82e  jz      short loc_1800DF839
0x1800df830  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800df835  mov     [rbx+8], r15
0x1800df839  mov     rdx, r13
0x1800df83c  mov     rcx, rbx; Block
0x1800df83f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800df844  test    edi, edi
0x1800df846  jns     short loc_1800DF852
0x1800df848  mov     edx, 1847h
0x1800df84d  jmp     loc_1800DF749
0x1800df852  mov     rbx, [rbp+340h+var_3C0]
0x1800df856  lea     rdx, aScheduleCreate; "Schedule created by dm client to refres"...
0x1800df85d  lea     rcx, [rsp+440h+Block]; this
0x1800df862  mov     rax, [rbx]
0x1800df865  mov     rdi, [rax+68h]
0x1800df869  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800df86e  mov     rdx, [rax]
0x1800df871  test    rdx, rdx
0x1800df874  jz      short loc_1800DF87B
0x1800df876  mov     rdx, [rdx]
0x1800df879  jmp     short loc_1800DF87E
0x1800df87b  mov     rdx, r15
0x1800df87e  lea     r8, [rsp+440h+var_3C8]
0x1800df883  mov     rcx, rbx
0x1800df886  mov     rax, rdi
0x1800df889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df88e  mov     rbx, [rsp+440h+Block]
0x1800df893  mov     dword ptr [rsp+440h+Data+4], eax
0x1800df897  test    rbx, rbx
0x1800df89a  jz      short loc_1800DF8E2
0x1800df89c  mov     eax, r12d
0x1800df89f  lock xadd [rbx+10h], eax
0x1800df8a4  add     eax, r12d
0x1800df8a7  jnz     short loc_1800DF8E2
0x1800df8a9  test    rbx, rbx
0x1800df8ac  jz      short loc_1800DF8E2
0x1800df8ae  mov     rcx, [rbx]; bstrString
0x1800df8b1  test    rcx, rcx
0x1800df8b4  jz      short loc_1800DF8C5
0x1800df8b6  call    cs:__imp_SysFreeString
0x1800df8bd  nop     dword ptr [rax+rax+00h]
0x1800df8c2  mov     [rbx], r15
0x1800df8c5  mov     rcx, [rbx+8]; Block
0x1800df8c9  test    rcx, rcx
0x1800df8cc  jz      short loc_1800DF8D7
0x1800df8ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800df8d3  mov     [rbx+8], r15
0x1800df8d7  mov     rdx, r13
0x1800df8da  mov     rcx, rbx; Block
0x1800df8dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800df8e2  mov     ebx, dword ptr [rsp+440h+Data+4]
0x1800df8e6  test    ebx, ebx
0x1800df8e8  jns     short loc_1800DF8F4
0x1800df8ea  mov     edx, 184Ah
0x1800df8ef  jmp     loc_1800DF55D
0x1800df8f4  mov     rcx, [rsp+440h+var_3C8]
0x1800df8f9  lea     rdx, [rsp+440h+var_3D8]
0x1800df8fe  mov     rax, [rcx]
0x1800df901  mov     rax, [rax+98h]
0x1800df908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df90d  mov     ebx, eax
0x1800df90f  test    eax, eax
0x1800df911  jns     short loc_1800DF91D
0x1800df913  mov     edx, 184Ch
0x1800df918  jmp     loc_1800DF55D
0x1800df91d  mov     rcx, [rsp+440h+var_3D8]
0x1800df922  lea     rdx, [rsp+440h+var_3D0]
0x1800df927  mov     rax, [rcx]
0x1800df92a  mov     rax, [rax+48h]
  ... truncated ...
```
