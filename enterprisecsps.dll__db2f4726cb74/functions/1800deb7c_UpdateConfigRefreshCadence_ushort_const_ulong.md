# UpdateConfigRefreshCadence(ushort const *,ulong)

- ea: `0x1800deb7c`
- end: `0x1800df465`
- name: `?UpdateConfigRefreshCadence@@YAJPEBGK@Z`
- size: `2281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c16c`
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
- `0x1800d8064`
- `0x1800deb7c`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800dee42`
- `OLEAUT32!__imp_SysFreeString` at `0x1800def54`
- `OLEAUT32!__imp_SysFreeString` at `0x1800deff1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df19f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df310`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dee42`
- `OLEAUT32!__imp_SysFreeString` at `0x1800def54`
- `OLEAUT32!__imp_SysFreeString` at `0x1800deff1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df19f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df310`
- `OLEAUT32!__imp_VariantInit` at `0x1800dece9`
- `OLEAUT32!__imp_VariantInit` at `0x1800ded04`
- `OLEAUT32!__imp_VariantInit` at `0x1800ded22`
- `OLEAUT32!__imp_VariantInit` at `0x1800ded41`
- `OLEAUT32!__imp_VariantInit` at `0x1800df21a`
- `OLEAUT32!__imp_VariantInit` at `0x1800df233`
- `OLEAUT32!__imp_VariantInit` at `0x1800dece9`
- `OLEAUT32!__imp_VariantInit` at `0x1800ded04`
- `OLEAUT32!__imp_VariantInit` at `0x1800ded22`
- `OLEAUT32!__imp_VariantInit` at `0x1800ded41`
- `OLEAUT32!__imp_VariantInit` at `0x1800df21a`
- `OLEAUT32!__imp_VariantInit` at `0x1800df233`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800df38c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800df38c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800deee5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800df411`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800deee5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800df411`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dec5a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dec5a`

## string_xrefs

- `0x1800def93`: `Schedule created by dm client to refresh settings`
- `0x1800df25f`: `Schedule created by dm client to refresh settings`
- `0x1800df374`: `24RegisterTaskDefinition`
- `0x1800df3a1`: `UpdateConfigRefreshCadence`

## pseudocode

```c
__int64 __fastcall UpdateConfigRefreshCadence(const unsigned __int16 *a1, unsigned int a2)
{
  int v4; // eax
  HRESULT v5; // ebx
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
  __int64 v39; // rbx
  __int64 (__fastcall *v40)(__int64, __int64); // rdi
  _bstr_t *v41; // rax
  __int64 v42; // rdx
  int v43; // eax
  BSTR *v44; // rbx
  BSTR v45; // rcx
  __int64 v46; // rbx
  __int64 (__fastcall *v47)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, VARIANTARG *, __int64 *); // rsi
  __int128 v48; // xmm6
  IRecordInfo *v49; // xmm7_8
  __int128 v50; // xmm8
  IRecordInfo *v51; // xmm9_8
  _variant_t *v52; // rax
  __int64 v53; // rdi
  __int128 v54; // xmm10
  IRecordInfo *v55; // xmm11_8
  _bstr_t *v56; // rax
  __int64 v57; // rdx
  int v58; // eax
  BSTR *v59; // rbx
  BSTR v60; // rcx
  CEnrollmentLogger *Logger; // rax
  int ppv; // [rsp+28h] [rbp-E0h]
  int *ppva; // [rsp+28h] [rbp-E0h]
  int Data; // [rsp+58h] [rbp-B0h] BYREF
  HRESULT Data_4; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v66; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v67; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v68; // [rsp+70h] [rbp-98h] BYREF
  __int64 v69; // [rsp+78h] [rbp-90h] BYREF
  LPVOID v70; // [rsp+80h] [rbp-88h] BYREF
  __int64 v71; // [rsp+88h] [rbp-80h] BYREF
  __int64 v72; // [rsp+90h] [rbp-78h] BYREF
  __int64 v73; // [rsp+98h] [rbp-70h] BYREF
  void *Block[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v75; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG v76; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v78; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v79; // [rsp+108h] [rbp+0h]
  __int128 v80; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v81; // [rsp+128h] [rbp+20h]
  VARIANTARG v82; // [rsp+138h] [rbp+30h] BYREF
  int v83[4]; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v84; // [rsp+168h] [rbp+60h]
  VARIANTARG v85; // [rsp+178h] [rbp+70h] BYREF
  VARIANTARG v86; // [rsp+190h] [rbp+88h] BYREF
  unsigned __int16 v87[264]; // [rsp+1A8h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+470h] [rbp+368h]

  Data = 0;
  v4 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&Data, a2);
  Data_4 = v4;
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17E6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
LABEL_91:
    if ( Data )
      CoUninitialize();
    return (unsigned int)v5;
  }
  v70 = 0;
  v73 = 0;
  v69 = 0;
  v68 = 0;
  v66 = 0;
  v67 = 0;
  v72 = 0;
  v71 = 0;
  v75 = 0;
  v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v70);
  if ( v5 < 0 )
  {
    v6 = 6134;
    goto LABEL_5;
  }
  v7 = v70;
  v8 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v70 + 80LL);
  VariantInit(&pvarg);
  v9 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v76);
  v11 = *(_OWORD *)&v76.vt;
  v12 = v76.pRecInfo;
  VariantInit(&v86);
  v13 = *(_OWORD *)&v86.vt;
  v14 = v86.pRecInfo;
  VariantInit(&v85);
  ppva = v83;
  v82 = v85;
  *(_OWORD *)v83 = v9;
  v84 = pRecInfo;
  v78 = v11;
  v79 = v12;
  v80 = v13;
  v81 = v14;
  v5 = v8(v7, &v82, &v80, &v78);
  _variant_t::~_variant_t((_variant_t *)&v85);
  _variant_t::~_variant_t((_variant_t *)&v86);
  _variant_t::~_variant_t((_variant_t *)&v76);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( v5 < 0 )
  {
    v6 = 6136;
    goto LABEL_5;
  }
  v15 = v70;
  v16 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v70 + 56LL);
  v17 = _bstr_t::_bstr_t((_bstr_t *)Block, L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical");
  if ( *(_QWORD *)v17 )
    v18 = **(_QWORD **)v17;
  else
    v18 = 0;
  v19 = v16(v15, v18, &v73);
  v20 = (BSTR *)Block[0];
  v21 = v19;
  if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v20 )
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
    v25 = v73;
    v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v73 + 72LL);
    v27 = _bstr_t::_bstr_t((_bstr_t *)Block, a1);
    if ( *(_QWORD *)v27 )
      v28 = **(_QWORD **)v27;
    else
      v28 = 0;
    v29 = v26(v25, v28, &v69);
    v30 = (BSTR *)Block[0];
    v21 = v29;
    if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v30 )
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
    if ( v21 >= 0 )
    {
      v32 = v69;
      v33 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v69 + 104LL);
      v34 = _bstr_t::_bstr_t((_bstr_t *)Block, L"Schedule created by dm client to refresh settings");
      if ( *(_QWORD *)v34 )
        v35 = **(_QWORD **)v34;
      else
        v35 = 0;
      v36 = v33(v32, v35, &v68);
      v37 = (BSTR *)Block[0];
      Data_4 = v36;
      if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v37 )
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
      if ( Data_4 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v68 + 152LL))(v68, &v66);
        if ( v5 >= 0 )
        {
          Data_4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v66 + 72LL))(v66, &v67);
          v5 = Data_4;
          if ( Data_4 >= 0 )
          {
            Data_4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v67 + 64LL))(v67, 1, &v72);
            v5 = Data_4;
            if ( Data_4 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v72 + 80LL))(v72, &v71);
              if ( v5 >= 0 )
              {
                LODWORD(v75) = 0;
                Data_4 = 0;
                WORD3(v75) = a2 / 0x3C / 0x18;
                WORD5(v75) = a2 % 0x3C;
                WORD4(v75) = a2 / 0x3C % 0x18;
                Data_4 = CreateScheduleTimeString(&v75, v87);
                v5 = Data_4;
                if ( Data_4 >= 0 )
                {
                  v39 = v71;
                  v40 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 64LL);
                  v41 = _bstr_t::_bstr_t((_bstr_t *)Block, v87);
                  if ( *(_QWORD *)v41 )
                    v42 = **(_QWORD **)v41;
                  else
                    v42 = 0;
                  v43 = v40(v39, v42);
                  v44 = (BSTR *)Block[0];
                  Data_4 = v43;
                  if ( Block[0]
                    && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1
                    && v44 )
                  {
                    if ( *v44 )
                    {
                      SysFreeString(*v44);
                      *v44 = 0;
                    }
                    v45 = v44[1];
                    if ( v45 )
                    {
                      operator delete(v45);
                      v44[1] = 0;
                    }
                    operator delete(v44);
                  }
                  v5 = Data_4;
                  if ( Data_4 >= 0 )
                  {
                    Data_4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 80LL))(v66, v67);
                    v5 = Data_4;
                    if ( Data_4 >= 0 )
                    {
                      v46 = v69;
                      v47 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, VARIANTARG *, __int64 *))(*(_QWORD *)v69 + 136LL);
                      VariantInit(&v76);
                      v48 = *(_OWORD *)&v76.vt;
                      v49 = v76.pRecInfo;
                      VariantInit(&pvarg);
                      v50 = *(_OWORD *)&pvarg.vt;
                      v51 = pvarg.pRecInfo;
                      v52 = _variant_t::_variant_t((_variant_t *)v83, L"S-1-5-18");
                      v53 = v66;
                      v54 = *(_OWORD *)v52;
                      v55 = (IRecordInfo *)*((_QWORD *)v52 + 2);
                      v56 = _bstr_t::_bstr_t((_bstr_t *)Block, L"Schedule created by dm client to refresh settings");
                      if ( *(_QWORD *)v56 )
                        v57 = **(_QWORD **)v56;
                      else
                        v57 = 0;
                      *(_OWORD *)&v82.vt = v48;
                      v82.pRecInfo = v49;
                      v80 = v50;
                      v81 = v51;
                      v78 = v54;
                      v79 = v55;
                      v58 = v47(v46, v57, v53, 6, &v78, &v80, 3, &v82, &v68);
                      v59 = (BSTR *)Block[0];
                      Data_4 = v58;
                      if ( Block[0] )
                      {
                        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v59 )
                        {
                          if ( *v59 )
                          {
                            SysFreeString(*v59);
                            *v59 = 0;
                          }
                          v60 = v59[1];
                          if ( v60 )
                          {
                            operator delete(v60);
                            v59[1] = 0;
                          }
                          operator delete(v59);
                        }
                        Block[0] = 0;
                      }
                      _variant_t::~_variant_t((_variant_t *)v83);
                      _variant_t::~_variant_t((_variant_t *)&pvarg);
                      _variant_t::~_variant_t((_variant_t *)&v76);
                      if ( Data_4 >= 0 )
                      {
                        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v71);
                        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v72);
                        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v67);
                        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v66);
                        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v68);
                        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v69);
                        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v73);
                        ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v70);
                        v5 = Data_4;
                        goto LABEL_91;
                      }
                      RegSetKeyValueW(
                        HKEY_LOCAL_MACHINE,
                        c_szEnrollmentDB,
                        L"24RegisterTaskDefinition",
                        4u,
                        &Data_4,
                        4u);
                      Logger = CEnrollmentLogger::GetLogger();
                      CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Data_4, "UpdateConfigRefreshCadence");
                      v5 = Data_4;
                      goto LABEL_6;
                    }
                    v6 = 6168;
                  }
                  else
                  {
                    v6 = 6165;
                  }
                }
                else
                {
                  v6 = 6162;
                }
              }
              else
              {
                v6 = 6156;
              }
            }
            else
            {
              v6 = 6153;
            }
          }
          else
          {
            v6 = 6149;
          }
        }
        else
        {
          v6 = 6145;
        }
      }
      else
      {
        v6 = 6143;
      }
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)(unsigned int)v5,
        (int)ppva);
LABEL_6:
      ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v71);
      ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v72);
      ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v67);
      ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v66);
      ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v68);
      ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v69);
      ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v73);
      ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v70);
      goto LABEL_91;
    }
    v23 = 6140;
  }
  else
  {
    v23 = 6138;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
    (const char *)(unsigned int)v21,
    (int)v83);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v71);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v72);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v67);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v66);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v68);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v69);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v73);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v70);
  if ( Data )
    CoUninitialize();
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1800deb7c  mov     rax, rsp
0x1800deb7f  push    rbp
0x1800deb80  push    rbx
0x1800deb81  push    rsi
0x1800deb82  push    rdi
0x1800deb83  push    r12
0x1800deb85  push    r13
0x1800deb87  push    r14
0x1800deb89  push    r15
0x1800deb8b  lea     rbp, [rax-368h]
0x1800deb92  sub     rsp, 428h
0x1800deb99  movaps  xmmword ptr [rax-58h], xmm6
0x1800deb9d  movaps  xmmword ptr [rax-68h], xmm7
0x1800deba1  movaps  xmmword ptr [rax-78h], xmm8
0x1800deba6  movaps  xmmword ptr [rax-88h], xmm9
0x1800debae  movaps  xmmword ptr [rax-98h], xmm10
0x1800debb6  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800debbe  mov     rax, cs:__security_cookie
0x1800debc5  xor     rax, rsp
0x1800debc8  mov     [rbp+360h+var_B0], rax
0x1800debcf  mov     r14, rcx
0x1800debd2  xor     r15d, r15d
0x1800debd5  lea     rcx, [rsp+460h+Data]; this
0x1800debda  mov     dword ptr [rsp+460h+Data], r15d
0x1800debdf  mov     esi, edx
0x1800debe1  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800debe6  mov     dword ptr [rsp+460h+Data+4], eax
0x1800debea  mov     ebx, eax
0x1800debec  test    eax, eax
0x1800debee  jns     short loc_1800DEC10
0x1800debf0  mov     rcx, [rbp+368h]; this
0x1800debf7  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800debfe  mov     r9d, eax; char *
0x1800dec01  mov     edx, 17E6h; void *
0x1800dec06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dec0b  jmp     loc_1800DF40A
0x1800dec10  xor     edx, edx; pUnkOuter
0x1800dec12  mov     [rsp+460h+var_3E8], r15
0x1800dec17  xorps   xmm0, xmm0
0x1800dec1a  mov     [rbp+360h+var_3D0], r15
0x1800dec1e  lea     rax, [rsp+460h+var_3E8]
0x1800dec23  mov     [rsp+460h+var_3F0], r15
0x1800dec28  lea     r9, IID_ITaskService; riid
0x1800dec2f  mov     [rsp+460h+var_3F8], r15
0x1800dec34  lea     r8d, [rdx+1]; dwClsContext
0x1800dec38  mov     [rsp+460h+var_408], r15
0x1800dec3d  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800dec44  mov     [rsp+460h+var_400], r15
0x1800dec49  mov     [rbp+360h+var_3D8], r15
0x1800dec4d  mov     [rbp+360h+var_3E0], r15
0x1800dec51  movups  [rbp+360h+var_3B8], xmm0
0x1800dec55  mov     [rsp+460h+ppv], rax; int
0x1800dec5a  call    cs:__imp_CoCreateInstance
0x1800dec61  nop     dword ptr [rax+rax+00h]
0x1800dec66  mov     ebx, eax
0x1800dec68  test    eax, eax
0x1800dec6a  jns     short loc_1800DECD9
0x1800dec6c  mov     edx, 17F6h; void *
0x1800dec71  mov     rcx, [rbp+368h]; this
0x1800dec78  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800dec7f  mov     r9d, ebx; char *
0x1800dec82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dec87  lea     rcx, [rbp+360h+var_3E0]
0x1800dec8b  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dec90  lea     rcx, [rbp+360h+var_3D8]
0x1800dec94  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dec99  lea     rcx, [rsp+460h+var_400]
0x1800dec9e  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800deca3  lea     rcx, [rsp+460h+var_408]
0x1800deca8  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800decad  lea     rcx, [rsp+460h+var_3F8]
0x1800decb2  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800decb7  lea     rcx, [rsp+460h+var_3F0]
0x1800decbc  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800decc1  lea     rcx, [rbp+360h+var_3D0]
0x1800decc5  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800decca  lea     rcx, [rsp+460h+var_3E8]
0x1800deccf  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800decd4  jmp     loc_1800DF40A
0x1800decd9  mov     rdi, [rsp+460h+var_3E8]
0x1800decde  lea     rcx, [rbp+360h+pvarg]; pvarg
0x1800dece2  mov     rax, [rdi]
0x1800dece5  mov     rbx, [rax+50h]
0x1800dece9  call    cs:__imp_VariantInit
0x1800decf0  nop     dword ptr [rax+rax+00h]
0x1800decf5  movups  xmm10, xmmword ptr [rbp+360h+pvarg]
0x1800decfa  lea     rcx, [rbp+360h+var_3A8]; pvarg
0x1800decfe  movsd   xmm11, qword ptr [rbp+360h+pvarg+10h]
0x1800ded04  call    cs:__imp_VariantInit
0x1800ded0b  nop     dword ptr [rax+rax+00h]
0x1800ded10  movups  xmm8, xmmword ptr [rbp+360h+var_3A8]
0x1800ded15  lea     rcx, [rbp+360h+var_2D8]; pvarg
0x1800ded1c  movsd   xmm9, qword ptr [rbp+360h+var_3A8+10h]
0x1800ded22  call    cs:__imp_VariantInit
0x1800ded29  nop     dword ptr [rax+rax+00h]
0x1800ded2e  movups  xmm6, xmmword ptr [rbp+360h+var_2D8]
0x1800ded35  lea     rcx, [rbp+360h+var_2F0]; pvarg
0x1800ded39  movsd   xmm7, qword ptr [rbp+360h+var_2D8+10h]
0x1800ded41  call    cs:__imp_VariantInit
0x1800ded48  nop     dword ptr [rax+rax+00h]
0x1800ded4d  movups  xmm0, xmmword ptr [rbp+360h+var_2F0]
0x1800ded51  lea     rax, [rbp+360h+var_310]
0x1800ded55  mov     rcx, rdi
0x1800ded58  movsd   xmm1, qword ptr [rbp+360h+var_2F0+10h]
0x1800ded60  lea     r9, [rbp+360h+var_370]
0x1800ded64  mov     [rsp+460h+ppv], rax; int
0x1800ded69  lea     r8, [rbp+360h+var_350]
0x1800ded6d  mov     rax, rbx
0x1800ded70  movaps  [rbp+360h+var_330], xmm0
0x1800ded74  lea     rdx, [rbp+360h+var_330]
0x1800ded78  movaps  xmmword ptr [rbp+360h+var_310], xmm10
0x1800ded7d  movsd   [rbp+360h+var_300], xmm11
0x1800ded83  movaps  [rbp+360h+var_370], xmm8
0x1800ded88  movsd   [rbp+360h+var_360], xmm9
0x1800ded8e  movaps  [rbp+360h+var_350], xmm6
0x1800ded92  movsd   [rbp+360h+var_340], xmm7
0x1800ded97  movsd   [rbp+360h+var_320], xmm1
0x1800ded9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deda1  lea     rcx, [rbp+360h+var_2F0]; this
0x1800deda5  mov     ebx, eax
0x1800deda7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800dedac  lea     rcx, [rbp+360h+var_2D8]; this
0x1800dedb3  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800dedb8  lea     rcx, [rbp+360h+var_3A8]; this
0x1800dedbc  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800dedc1  lea     rcx, [rbp+360h+pvarg]; this
0x1800dedc5  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800dedca  test    ebx, ebx
0x1800dedcc  jns     short loc_1800DEDD8
0x1800dedce  mov     edx, 17F8h
0x1800dedd3  jmp     loc_1800DEC71
0x1800dedd8  mov     rbx, [rsp+460h+var_3E8]
0x1800deddd  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x1800dede4  lea     rcx, [rbp+360h+Block]; this
0x1800dede8  mov     rax, [rbx]
0x1800dedeb  mov     rdi, [rax+38h]
0x1800dedef  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800dedf4  mov     rcx, [rax]
0x1800dedf7  test    rcx, rcx
0x1800dedfa  jz      short loc_1800DEE01
0x1800dedfc  mov     rdx, [rcx]
0x1800dedff  jmp     short loc_1800DEE04
0x1800dee01  mov     rdx, r15
0x1800dee04  lea     r8, [rbp+360h+var_3D0]
0x1800dee08  mov     rcx, rbx
0x1800dee0b  mov     rax, rdi
0x1800dee0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dee13  mov     rbx, [rbp+360h+Block]
0x1800dee17  or      r12d, 0FFFFFFFFh
0x1800dee1b  mov     edi, eax
0x1800dee1d  mov     r13d, 18h
0x1800dee23  test    rbx, rbx
0x1800dee26  jz      short loc_1800DEE6E
0x1800dee28  mov     ecx, r12d
0x1800dee2b  lock xadd [rbx+10h], ecx
0x1800dee30  add     ecx, r12d
0x1800dee33  jnz     short loc_1800DEE6E
0x1800dee35  test    rbx, rbx
0x1800dee38  jz      short loc_1800DEE6E
0x1800dee3a  mov     rcx, [rbx]; bstrString
0x1800dee3d  test    rcx, rcx
0x1800dee40  jz      short loc_1800DEE51
0x1800dee42  call    cs:__imp_SysFreeString
0x1800dee49  nop     dword ptr [rax+rax+00h]
0x1800dee4e  mov     [rbx], r15
0x1800dee51  mov     rcx, [rbx+8]; Block
0x1800dee55  test    rcx, rcx
0x1800dee58  jz      short loc_1800DEE63
0x1800dee5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dee5f  mov     [rbx+8], r15
0x1800dee63  mov     rdx, r13
0x1800dee66  mov     rcx, rbx; Block
0x1800dee69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dee6e  test    edi, edi
0x1800dee70  jns     loc_1800DEEF8
0x1800dee76  mov     edx, 17FAh; void *
0x1800dee7b  mov     rcx, [rbp+368h]; this
0x1800dee82  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800dee89  mov     r9d, edi; char *
0x1800dee8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dee91  lea     rcx, [rbp+360h+var_3E0]
0x1800dee95  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dee9a  lea     rcx, [rbp+360h+var_3D8]
0x1800dee9e  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800deea3  lea     rcx, [rsp+460h+var_400]
0x1800deea8  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800deead  lea     rcx, [rsp+460h+var_408]
0x1800deeb2  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800deeb7  lea     rcx, [rsp+460h+var_3F8]
0x1800deebc  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800deec1  lea     rcx, [rsp+460h+var_3F0]
0x1800deec6  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800deecb  lea     rcx, [rbp+360h+var_3D0]
0x1800deecf  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800deed4  lea     rcx, [rsp+460h+var_3E8]
0x1800deed9  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800deede  cmp     dword ptr [rsp+460h+Data], r15d
0x1800deee3  jz      short loc_1800DEEF1
0x1800deee5  call    cs:__imp_CoUninitialize
0x1800deeec  nop     dword ptr [rax+rax+00h]
0x1800deef1  mov     eax, edi
0x1800deef3  jmp     loc_1800DF41F
0x1800deef8  mov     rbx, [rbp+360h+var_3D0]
0x1800deefc  lea     rcx, [rbp+360h+Block]; this
0x1800def00  mov     rdx, r14; unsigned __int16 *
0x1800def03  mov     rax, [rbx]
0x1800def06  mov     rdi, [rax+48h]
0x1800def0a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800def0f  mov     rdx, [rax]
0x1800def12  test    rdx, rdx
0x1800def15  jz      short loc_1800DEF1C
0x1800def17  mov     rdx, [rdx]
0x1800def1a  jmp     short loc_1800DEF1F
0x1800def1c  mov     rdx, r15
0x1800def1f  lea     r8, [rsp+460h+var_3F0]
0x1800def24  mov     rcx, rbx
0x1800def27  mov     rax, rdi
0x1800def2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800def2f  mov     rbx, [rbp+360h+Block]
0x1800def33  mov     edi, eax
0x1800def35  test    rbx, rbx
0x1800def38  jz      short loc_1800DEF80
0x1800def3a  mov     ecx, r12d
0x1800def3d  lock xadd [rbx+10h], ecx
0x1800def42  add     ecx, r12d
0x1800def45  jnz     short loc_1800DEF80
0x1800def47  test    rbx, rbx
0x1800def4a  jz      short loc_1800DEF80
0x1800def4c  mov     rcx, [rbx]; bstrString
0x1800def4f  test    rcx, rcx
0x1800def52  jz      short loc_1800DEF63
0x1800def54  call    cs:__imp_SysFreeString
0x1800def5b  nop     dword ptr [rax+rax+00h]
0x1800def60  mov     [rbx], r15
0x1800def63  mov     rcx, [rbx+8]; Block
0x1800def67  test    rcx, rcx
0x1800def6a  jz      short loc_1800DEF75
0x1800def6c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800def71  mov     [rbx+8], r15
0x1800def75  mov     rdx, r13
0x1800def78  mov     rcx, rbx; Block
0x1800def7b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800def80  test    edi, edi
0x1800def82  jns     short loc_1800DEF8E
0x1800def84  mov     edx, 17FCh
0x1800def89  jmp     loc_1800DEE7B
0x1800def8e  mov     rbx, [rsp+460h+var_3F0]
0x1800def93  lea     rdx, aScheduleCreate; "Schedule created by dm client to refres"...
0x1800def9a  lea     rcx, [rbp+360h+Block]; this
0x1800def9e  mov     rax, [rbx]
0x1800defa1  mov     rdi, [rax+68h]
0x1800defa5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800defaa  mov     rdx, [rax]
0x1800defad  test    rdx, rdx
0x1800defb0  jz      short loc_1800DEFB7
0x1800defb2  mov     rdx, [rdx]
0x1800defb5  jmp     short loc_1800DEFBA
0x1800defb7  mov     rdx, r15
0x1800defba  lea     r8, [rsp+460h+var_3F8]
0x1800defbf  mov     rcx, rbx
0x1800defc2  mov     rax, rdi
0x1800defc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800defca  mov     rbx, [rbp+360h+Block]
0x1800defce  mov     dword ptr [rsp+460h+Data+4], eax
0x1800defd2  test    rbx, rbx
0x1800defd5  jz      short loc_1800DF01D
0x1800defd7  mov     eax, r12d
0x1800defda  lock xadd [rbx+10h], eax
0x1800defdf  add     eax, r12d
0x1800defe2  jnz     short loc_1800DF01D
0x1800defe4  test    rbx, rbx
0x1800defe7  jz      short loc_1800DF01D
0x1800defe9  mov     rcx, [rbx]; bstrString
0x1800defec  test    rcx, rcx
0x1800defef  jz      short loc_1800DF000
0x1800deff1  call    cs:__imp_SysFreeString
0x1800deff8  nop     dword ptr [rax+rax+00h]
0x1800deffd  mov     [rbx], r15
0x1800df000  mov     rcx, [rbx+8]; Block
0x1800df004  test    rcx, rcx
0x1800df007  jz      short loc_1800DF012
0x1800df009  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800df00e  mov     [rbx+8], r15
0x1800df012  mov     rdx, r13
0x1800df015  mov     rcx, rbx; Block
0x1800df018  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800df01d  mov     ebx, dword ptr [rsp+460h+Data+4]
0x1800df021  test    ebx, ebx
0x1800df023  jns     short loc_1800DF02F
0x1800df025  mov     edx, 17FFh
0x1800df02a  jmp     loc_1800DEC71
0x1800df02f  mov     rcx, [rsp+460h+var_3F8]
0x1800df034  lea     rdx, [rsp+460h+var_408]
0x1800df039  mov     rax, [rcx]
0x1800df03c  mov     rax, [rax+98h]
0x1800df043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df048  mov     ebx, eax
0x1800df04a  test    eax, eax
0x1800df04c  jns     short loc_1800DF058
0x1800df04e  mov     edx, 1801h
  ... truncated ...
```
