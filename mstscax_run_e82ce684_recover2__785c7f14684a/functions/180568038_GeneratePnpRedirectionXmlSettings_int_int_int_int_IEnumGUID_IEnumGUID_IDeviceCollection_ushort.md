# GeneratePnpRedirectionXmlSettings(int,int,int,int,IEnumGUID *,IEnumGUID *,IDeviceCollection *,ushort * *)

- ea: `0x180568038`
- end: `0x1805692cc`
- name: `?GeneratePnpRedirectionXmlSettings@@YAJHHHHPEAUIEnumGUID@@0PEAUIDeviceCollection@@PEAPEAG@Z`
- size: `4756`
- prototype: `__int64 __fastcall(int, int, int, int, struct IEnumGUID *, struct IEnumGUID *, struct IDeviceCollection *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1802343e8`

## callees

- `0x1800186a0`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x180568038`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180568521`
- `OLEAUT32!__imp_SysAllocString` at `0x180568536`
- `OLEAUT32!__imp_SysAllocString` at `0x18056854b`
- `OLEAUT32!__imp_SysAllocString` at `0x180568560`
- `OLEAUT32!__imp_SysAllocString` at `0x180568521`
- `OLEAUT32!__imp_SysAllocString` at `0x180568536`
- `OLEAUT32!__imp_SysAllocString` at `0x18056854b`
- `OLEAUT32!__imp_SysAllocString` at `0x180568560`
- `OLEAUT32!__imp_SysFreeString` at `0x180568903`
- `OLEAUT32!__imp_SysFreeString` at `0x180568911`
- `OLEAUT32!__imp_SysFreeString` at `0x18056891f`
- `OLEAUT32!__imp_SysFreeString` at `0x180568931`
- `OLEAUT32!__imp_SysFreeString` at `0x180568903`
- `OLEAUT32!__imp_SysFreeString` at `0x180568911`
- `OLEAUT32!__imp_SysFreeString` at `0x18056891f`
- `OLEAUT32!__imp_SysFreeString` at `0x180568931`
- `OLEAUT32!__imp_VariantInit` at `0x180569036`
- `OLEAUT32!__imp_VariantInit` at `0x180569036`
- `OLEAUT32!__imp_VariantClear` at `0x1805690a8`
- `OLEAUT32!__imp_VariantClear` at `0x1805690a8`
- `OLE32!StringFromCLSID` at `0x180568685`
- `OLE32!StringFromCLSID` at `0x180568685`
- `OLE32!CoTaskMemFree` at `0x18056875a`
- `OLE32!CoTaskMemFree` at `0x180568d36`
- `OLE32!CoTaskMemFree` at `0x18056875a`
- `OLE32!CoTaskMemFree` at `0x180568d36`
- `OLE32!CoCreateInstance` at `0x1805680be`
- `OLE32!CoCreateInstance` at `0x18056812b`
- `OLE32!CoCreateInstance` at `0x1805680be`
- `OLE32!CoCreateInstance` at `0x18056812b`

## string_xrefs

- `0x1805688be`: `Failed to end Xml node`
- `0x180568d8a`: `Failed to end Xml node`
- `0x180568f7a`: `Failed to end Xml node`
- `0x180568101`: `Failed to cocreate MXXMLWritter`
- `0x18056816e`: `Failed to cocreate MXAttributes`
- `0x1805681d2`: `Failed to QI ISAXContentHandler from IMXXMLWriter`
- `0x1805682be`: `Failed to start Xml node`
- `0x180568aa8`: `Failed to start Xml node`
- `0x180569215`: `Failed to add Xml node`
- `0x180568e53`: `Failed to clear Xml attributes`
- `0x180568e10`: `Failed to add xml attribute`
- `0x18056908d`: `Failed to get XML output`
- `0x1805690d1`: `IMXXMLWriter did not retirn BSTR`

## pseudocode

```c
__int64 __fastcall GeneratePnpRedirectionXmlSettings(
        int a1,
        int a2,
        int a3,
        int a4,
        struct IEnumGUID *a5,
        struct IEnumGUID *a6,
        struct IDeviceCollection *a7,
        unsigned __int16 **a8)
{
  HRESULT v12; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v14; // edx
  const char *v15; // rcx
  const OLECHAR *v16; // rdx
  __int64 v17; // r8
  const OLECHAR *v18; // rdx
  __int64 v19; // r8
  const OLECHAR *v20; // rdx
  __int64 v21; // r8
  OLECHAR *v22; // r14
  OLECHAR *v23; // rsi
  int v24; // r15d
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r12
  __int64 v28; // rbx
  int v29; // eax
  __int64 v30; // rdx
  const wchar_t *v31; // rsi
  __int64 v32; // r8
  __int64 v33; // rdx
  const wchar_t *v34; // rbx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  unsigned int v38; // eax
  int v39; // edx
  const char *v40; // rcx
  OLECHAR *v41; // r12
  LPVOID v42; // rsi
  unsigned int v43; // ebx
  BSTR v44; // rdx
  __int64 v45; // r8
  unsigned int v46; // eax
  int v47; // edx
  const char *v48; // rcx
  unsigned int v49; // eax
  int v50; // edx
  const char *v51; // rcx
  unsigned int v52; // eax
  unsigned int v53; // eax
  __int64 v54; // rcx
  __int64 *v55; // rcx
  LPVOID v56; // rcx
  LPVOID v57; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  BSTR v60; // [rsp+50h] [rbp-B0h]
  BSTR v61; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v62; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v63; // [rsp+68h] [rbp-98h] BYREF
  LPOLESTR lpsz; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v65; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v66; // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  __int64 v68; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 **v71; // [rsp+B8h] [rbp-48h]
  const wchar_t *v72; // [rsp+C0h] [rbp-40h]
  const wchar_t *v73; // [rsp+C8h] [rbp-38h]
  _QWORD v74[2]; // [rsp+D0h] [rbp-30h]
  _QWORD v75[2]; // [rsp+E0h] [rbp-20h]
  IID rclsid; // [rsp+F0h] [rbp-10h] BYREF

  pv = a7;
  v71 = a8;
  v66 = 0;
  v65 = 0;
  v63 = 0;
  v68 = 0;
  v12 = CoCreateInstance(&CLSID_MXXMLWriter60, 0, 1u, &IID_IMXWriter, &v66);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 69;
      v15 = "Failed to cocreate MXXMLWritter";
LABEL_221:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)WPP_eabf5a8452d737beba746ca7a18862b7_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v15,
        v12);
      goto LABEL_222;
    }
    goto LABEL_222;
  }
  v12 = CoCreateInstance(&CLSID_SAXAttributes60, 0, 1u, &IID_IMXAttributes, &v65);
  if ( v12 >= 0 )
  {
    v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 **))v66)(v66, &IID_ISAXContentHandler, &v63);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 71;
        v15 = "Failed to QI ISAXContentHandler from IMXXMLWriter";
        goto LABEL_221;
      }
      goto LABEL_222;
    }
    v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v65)(v65, &IID_ISAXAttributes, &v68);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 72;
        v15 = "Failed to QI ISAXAttributes from IMXAttributes";
        goto LABEL_221;
      }
      goto LABEL_222;
    }
    v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int, _QWORD))(*v63 + 64))(
            v63,
            &sourceString,
            0,
            &sourceString,
            0,
            L"PnpRedirectionSettings",
            22,
            0);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 73;
        v15 = "Failed to start Xml node";
        goto LABEL_221;
      }
      goto LABEL_222;
    }
    v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int, _QWORD))(*v63 + 64))(
            v63,
            &sourceString,
            0,
            &sourceString,
            0,
            L"ForceDisablePnpDeviceRedirection",
            32,
            0);
    if ( v12 < 0 )
      goto LABEL_218;
    v16 = L"true";
    if ( !a1 )
      v16 = L"false";
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    v12 = (*(__int64 (__fastcall **)(__int64 *))(*v63 + 80))(v63);
    if ( v12 < 0
      || (v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int))(*v63 + 72))(
                  v63,
                  &sourceString,
                  0,
                  &sourceString,
                  0,
                  L"ForceDisablePnpDeviceRedirection",
                  32),
          v12 < 0) )
    {
LABEL_218:
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_222;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 74;
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int, _QWORD))(*v63 + 64))(
              v63,
              &sourceString,
              0,
              &sourceString,
              0,
              L"EnableDynamicDeviceRedirection",
              30,
              0);
      if ( v12 < 0 )
        goto LABEL_214;
      v18 = L"true";
      if ( !a2 )
        v18 = L"false";
      v19 = -1;
      do
        ++v19;
      while ( v18[v19] );
      v12 = (*(__int64 (__fastcall **)(__int64 *))(*v63 + 80))(v63);
      if ( v12 < 0
        || (v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int))(*v63 + 72))(
                    v63,
                    &sourceString,
                    0,
                    &sourceString,
                    0,
                    L"EnableDynamicDeviceRedirection",
                    30),
            v12 < 0) )
      {
LABEL_214:
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_222;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 75;
      }
      else
      {
        v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int, _QWORD))(*v63 + 64))(
                v63,
                &sourceString,
                0,
                &sourceString,
                0,
                L"EnableTsRedirectFlag",
                20,
                0);
        if ( v12 >= 0 )
        {
          v20 = L"true";
          if ( !a3 )
            v20 = L"false";
          v21 = -1;
          do
            ++v21;
          while ( v20[v21] );
          v12 = (*(__int64 (__fastcall **)(__int64 *))(*v63 + 80))(v63);
          if ( v12 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int))(*v63 + 72))(
                    v63,
                    &sourceString,
                    0,
                    &sourceString,
                    0,
                    L"EnableTsRedirectFlag",
                    20);
            if ( v12 >= 0 )
            {
              v62 = SysAllocString(L"Enabled");
              v61 = SysAllocString(L"true");
              v22 = v61;
              v60 = SysAllocString(L"false");
              v23 = v60;
              bstrString = SysAllocString(&sourceString);
              if ( !v62 || !v61 || !v60 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v53 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    77,
                    (unsigned int)WPP_eabf5a8452d737beba746ca7a18862b7_Traceguids,
                    v53,
                    (__int64)"Failed to allocate attribute BSTRs",
                    14);
                }
                v41 = v62;
                v12 = -2147024882;
                goto LABEL_92;
              }
              v75[0] = a5;
              v74[0] = L"Interfaces";
              v75[1] = a6;
              v74[1] = L"SetupClasses";
              v24 = 0;
              v72 = L"InterfaceGuid";
              v73 = L"SetupClassGuid";
              while ( 1 )
              {
                v25 = *v63;
                if ( v24 >= 2 )
                  break;
                v26 = -1;
                v27 = v74[v24];
                do
                  ++v26;
                while ( *(_WORD *)(v27 + 2 * v26) );
                v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, __int64, _DWORD, _QWORD))(v25 + 64))(
                        v63,
                        &sourceString,
                        0,
                        &sourceString,
                        0,
                        v27,
                        v26,
                        0);
                if ( v12 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v38 = RdpWppGetCurrentThreadActivityIdPrefix();
                    v39 = 78;
                    goto LABEL_124;
                  }
                  goto LABEL_90;
                }
                v28 = v75[v24];
                if ( v28 )
                {
                  v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v28 + 40LL))(v75[v24]);
                  if ( v12 >= 0 )
                  {
                    do
                    {
                      lpsz = 0;
                      rclsid = 0;
                      v29 = (*(__int64 (__fastcall **)(__int64, __int64, IID *))(*(_QWORD *)v28 + 24LL))(
                              v28,
                              1,
                              &rclsid);
                      v12 = v29;
                      if ( v29 < 0 )
                      {
                        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          v38 = RdpWppGetCurrentThreadActivityIdPrefix();
                          v39 = 80;
                          v40 = "Failed to get next elem";
                          goto LABEL_89;
                        }
                        goto LABEL_90;
                      }
                      if ( v29 == 1 )
                        break;
                      v12 = StringFromCLSID(&rclsid, &lpsz);
                      if ( v12 < 0 )
                      {
                        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          v38 = RdpWppGetCurrentThreadActivityIdPrefix();
                          v39 = 81;
                          v40 = "Failed to get string for GUID";
                          goto LABEL_89;
                        }
                        goto LABEL_90;
                      }
                      v30 = -1;
                      v31 = (&v72)[v24];
                      do
                        ++v30;
                      while ( v31[v30] );
                      v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, _DWORD, _QWORD))(*v63 + 64))(
                              v63,
                              &sourceString,
                              0,
                              &sourceString,
                              0,
                              v31,
                              v30,
                              0);
                      if ( v12 >= 0 )
                      {
                        v32 = -1;
                        do
                          ++v32;
                        while ( lpsz[v32] );
                        v12 = (*(__int64 (__fastcall **)(__int64 *, LPOLESTR, __int64, _QWORD))(*v63 + 80))(
                                v63,
                                lpsz,
                                v32,
                                0);
                        if ( v12 >= 0 )
                        {
                          v33 = -1;
                          do
                            ++v33;
                          while ( v31[v33] );
                          v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, _DWORD))(*v63 + 72))(
                                  v63,
                                  &sourceString,
                                  0,
                                  &sourceString,
                                  0,
                                  v31,
                                  v33);
                        }
                      }
                      CoTaskMemFree(lpsz);
                      if ( v12 < 0 )
                      {
                        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          v38 = RdpWppGetCurrentThreadActivityIdPrefix();
                          v39 = 82;
                          goto LABEL_88;
                        }
                        goto LABEL_90;
                      }
                    }
                    while ( v12 != 1 );
                    if ( v24 != 1 )
                      goto LABEL_80;
                    if ( !a4 )
                      goto LABEL_80;
                    v34 = v73;
                    v35 = -1;
                    do
                      ++v35;
                    while ( v73[v35] );
                    v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, _DWORD, _QWORD))(*v63 + 64))(
                            v63,
                            &sourceString,
                            0,
                            &sourceString,
                            0,
                            v73,
                            v35,
                            0);
                    if ( v12 >= 0 )
                    {
                      v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64))(*v63 + 80))(
                              v63,
                              L"{745A17A0-74D3-11D0-B6FE-00A0C90F57DA}",
                              38);
                      if ( v12 >= 0 )
                      {
                        v36 = -1;
                        do
                          ++v36;
                        while ( v34[v36] );
                        v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, _DWORD))(*v63 + 72))(
                                v63,
                                &sourceString,
                                0,
                                &sourceString,
                                0,
                                v34,
                                v36);
                        if ( v12 >= 0 )
                          goto LABEL_80;
                      }
                    }
                    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v38 = RdpWppGetCurrentThreadActivityIdPrefix();
                      v39 = 83;
                      goto LABEL_88;
                    }
                    goto LABEL_90;
                  }
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
LABEL_90:
                    v41 = v62;
                    v22 = v61;
                    goto LABEL_91;
                  }
                  v38 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v39 = 79;
                  v40 = "Failed to reset enumeration";
LABEL_89:
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v39,
                    (unsigned int)WPP_eabf5a8452d737beba746ca7a18862b7_Traceguids,
                    v38,
                    (__int64)v40,
                    v12);
                  goto LABEL_90;
                }
LABEL_80:
                v37 = -1;
                do
                  ++v37;
                while ( *(_WORD *)(v27 + 2 * v37) );
                v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, __int64, _DWORD))(*v63 + 72))(
                        v63,
                        &sourceString,
                        0,
                        &sourceString,
                        0,
                        v27,
                        v37);
                if ( v12 < 0 )
                {
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_90;
                  }
                  v38 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v39 = 84;
LABEL_88:
                  v40 = "Failed to end Xml node";
                  goto LABEL_89;
                }
                ++v24;
              }
              v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int, _QWORD))(v25 + 64))(
                      v63,
                      &sourceString,
                      0,
                      &sourceString,
                      0,
                      L"Instances",
                      9,
                      0);
              if ( v12 < 0 )
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_90;
                }
                v38 = RdpWppGetCurrentThreadActivityIdPrefix();
                v39 = 85;
LABEL_124:
                v40 = "Failed to start Xml node";
                goto LABEL_89;
              }
              v42 = pv;
              if ( pv )
              {
                LODWORD(lpsz) = 0;
                v12 = (*(__int64 (__fastcall **)(LPVOID, LPOLESTR *))(*(_QWORD *)pv + 120LL))(pv, &lpsz);
                if ( v12 >= 0 )
                {
                  v22 = v61;
                  v43 = 0;
                  v41 = v62;
                  while ( 1 )
                  {
                    if ( v43 >= (unsigned int)lpsz )
                      goto LABEL_179;
                    v61 = 0;
                    pv = 0;
                    LODWORD(v62) = 0;
                    v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, BSTR *))(*(_QWORD *)v42 + 104LL))(v42, v43, &v61);
                    if ( v12 < 0 )
                      break;
                    v12 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)v61 + 144LL))(v61, &v62);
                    if ( v12 < 0 )
                    {
                      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                      {
                        goto LABEL_177;
                      }
                      v46 = RdpWppGetCurrentThreadActivityIdPrefix();
                      v47 = 88;
                      v48 = "Failed to get device redirection state";
                      goto LABEL_176;
                    }
                    v12 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v65 + 72LL))(v65);
                    if ( v12 < 0 )
                    {
                      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                      {
                        goto LABEL_177;
                      }
                      v46 = RdpWppGetCurrentThreadActivityIdPrefix();
                      v47 = 89;
                      v48 = "Failed to clear Xml attributes";
                      goto LABEL_176;
                    }
                    v44 = v60;
                    if ( (_DWORD)v62 )
                      v44 = v22;
                    v12 = (*(__int64 (__fastcall **)(LPVOID, BSTR, BSTR, OLECHAR *, BSTR, BSTR))(*(_QWORD *)v65 + 56LL))(
                            v65,
                            bstrString,
                            bstrString,
                            v41,
                            bstrString,
                            v44);
                    if ( v12 < 0 )
                    {
                      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
                        v47 = 90;
                        v48 = "Failed to add xml attribute";
                        goto LABEL_176;
                      }
LABEL_177:
                      TCntPtr<ITSViewerRecorder>::SafeRelease(&v61);
                      v23 = v60;
                      goto LABEL_92;
                    }
                    v12 = (*(__int64 (__fastcall **)(BSTR, LPVOID *))(*(_QWORD *)v61 + 96LL))(v61, &pv);
                    if ( v12 < 0 )
                    {
                      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
                        v47 = 91;
                        v48 = "Failed to get device instanceId";
                        goto LABEL_176;
                      }
                      goto LABEL_177;
                    }
                    LODWORD(ppv) = 0;
                    v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, LPVOID *, const wchar_t *, int, __int64))(*v63 + 64))(
                            v63,
                            &sourceString,
                            0,
                            &sourceString,
                            ppv,
                            L"InstanceId",
                            10,
                            v68);
                    if ( v12 >= 0 )
                    {
                      v45 = -1;
                      do
                        ++v45;
                      while ( *((_WORD *)pv + v45) );
                      v12 = (*(__int64 (__fastcall **)(__int64 *, LPVOID))(*v63 + 80))(v63, pv);
                      if ( v12 >= 0 )
                        v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int))(*v63 + 72))(
                                v63,
                                &sourceString,
                                0,
                                &sourceString,
                                0,
                                L"InstanceId",
                                10);
                    }
                    CoTaskMemFree(pv);
                    if ( v12 < 0 )
                    {
                      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
                        v47 = 92;
                        v48 = "Failed to end Xml node";
                        goto LABEL_176;
                      }
                      goto LABEL_177;
                    }
                    TCntPtr<ITSViewerRecorder>::SafeRelease(&v61);
                    ++v43;
                  }
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_177;
                  }
                  v46 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v47 = 87;
                  v48 = "Failed to get device from collection";
LABEL_176:
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v47,
                    (unsigned int)WPP_eabf5a8452d737beba746ca7a18862b7_Traceguids,
                    v46,
                    (__int64)v48,
                    v12);
                  goto LABEL_177;
                }
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_90;
                }
                v38 = RdpWppGetCurrentThreadActivityIdPrefix();
                v39 = 86;
                v40 = "Failed to get device count of device collection";
                goto LABEL_89;
              }
              v22 = v61;
              v41 = v62;
LABEL_179:
              v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int))(*v63 + 72))(
                      v63,
                      &sourceString,
                      0,
                      &sourceString,
                      0,
                      L"Instances",
                      9);
              if ( v12 >= 0 )
              {
                v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD, const wchar_t *, _DWORD, const wchar_t *, int))(*v63 + 72))(
                        v63,
                        &sourceString,
                        0,
                        &sourceString,
                        0,
                        L"PnpRedirectionSettings",
                        22);
                if ( v12 >= 0 )
                {
                  memset(&pvarg, 0, sizeof(pvarg));
                  VariantInit(&pvarg);
                  v12 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)v66 + 64LL))(v66, &pvarg);
                  if ( v12 >= 0 )
                  {
                    if ( pvarg.vt == 8 )
                    {
                      *v71 = pvarg.bstrVal;
                    }
                    else
                    {
                      VariantClear(&pvarg);
                      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v52 = RdpWppGetCurrentThreadActivityIdPrefix();
                        WPP_SF_DsD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          96,
                          (unsigned int)WPP_eabf5a8452d737beba746ca7a18862b7_Traceguids,
                          v52,
                          (__int64)"IMXXMLWriter did not retirn BSTR",
                          5);
                      }
                      v12 = -2147467259;
                    }
                    goto LABEL_91;
                  }
                  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
LABEL_91:
                    v23 = v60;
LABEL_92:
                    if ( bstrString )
                      SysFreeString(bstrString);
                    if ( v23 )
                      SysFreeString(v23);
                    if ( v22 )
                      SysFreeString(v22);
                    if ( v41 )
                      SysFreeString(v41);
                    goto LABEL_222;
                  }
                  v49 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v50 = 95;
                  v51 = "Failed to get XML output";
LABEL_185:
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v50,
                    (unsigned int)WPP_eabf5a8452d737beba746ca7a18862b7_Traceguids,
                    v49,
                    (__int64)v51,
                    v12);
                  goto LABEL_91;
                }
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_91;
                }
                v49 = RdpWppGetCurrentThreadActivityIdPrefix();
                v50 = 94;
              }
              else
              {
                if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
                  || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_91;
                }
                v49 = RdpWppGetCurrentThreadActivityIdPrefix();
                v50 = 93;
              }
              v51 = "Failed to end Xml node";
              goto LABEL_185;
            }
          }
        }
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_222;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 76;
      }
    }
    v15 = "Failed to add Xml node";
    goto LABEL_221;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 70;
    v15 = "Failed to cocreate MXAttributes";
    goto LABEL_221;
  }
LABEL_222:
  v54 = v68;
  if ( v68 )
  {
    v68 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  }
  v55 = v63;
  if ( v63 )
  {
    v63 = 0;
    (*(void (__fastcall **)(__int64 *))(*v55 + 16))(v55);
  }
  v56 = v65;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v56 + 16LL))(v56);
  }
  v57 = v66;
  if ( v66 )
  {
    v66 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v57 + 16LL))(v57);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180568038  push    rbp
0x18056803a  push    rbx
0x18056803b  push    rsi
0x18056803c  push    rdi
0x18056803d  push    r12
0x18056803f  push    r13
0x180568041  push    r14
0x180568043  push    r15
0x180568045  lea     rbp, [rsp-18h]
0x18056804a  sub     rsp, 118h
0x180568051  mov     rax, cs:__security_cookie
0x180568058  xor     rax, rsp
0x18056805b  mov     [rbp+50h+var_50], rax
0x18056805f  mov     rax, [rbp+50h+arg_30]
0x180568066  mov     esi, edx
0x180568068  mov     r15, [rbp+50h+arg_20]
0x18056806f  xor     edx, edx; pUnkOuter
0x180568071  mov     r12, [rbp+50h+arg_28]
0x180568078  mov     r13d, r9d
0x18056807b  mov     [rbp+50h+pv], rax
0x18056807f  lea     r9, IID_IMXWriter; riid
0x180568086  mov     rax, [rbp+50h+arg_38]
0x18056808d  mov     r14d, r8d
0x180568090  mov     [rbp+50h+var_98], rax
0x180568094  lea     r8d, [rdx+1]; dwClsContext
0x180568098  xor     eax, eax
0x18056809a  mov     ebx, ecx
0x18056809c  mov     [rbp+50h+var_D0], rax
0x1805680a0  lea     rcx, CLSID_MXXMLWriter60; rclsid
0x1805680a7  mov     [rsp+150h+var_D8], rax
0x1805680ac  mov     [rsp+150h+var_E8], rax
0x1805680b1  mov     [rbp+50h+var_C0], rax
0x1805680b5  lea     rax, [rbp+50h+var_D0]
0x1805680b9  mov     [rsp+150h+ppv], rax; ppv
0x1805680be  call    cs:__imp_CoCreateInstance
0x1805680c4  mov     edi, eax
0x1805680c6  test    eax, eax
0x1805680c8  jns     short loc_18056810D
0x1805680ca  mov     rax, cs:WPP_GLOBAL_Control
0x1805680d1  lea     rcx, WPP_GLOBAL_Control
0x1805680d8  cmp     rax, rcx
0x1805680db  jz      loc_18056923F
0x1805680e1  mov     ebx, 8
0x1805680e6  test    [rax+1Ch], bl
0x1805680e9  jz      loc_18056923F
0x1805680ef  cmp     byte ptr [rax+19h], 2
0x1805680f3  jb      loc_18056923F
0x1805680f9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805680fe  lea     edx, [rbx+3Dh]
0x180568101  lea     rcx, aFailedToCocrea; "Failed to cocreate MXXMLWritter"
0x180568108  jmp     loc_18056921C
0x18056810d  xor     edx, edx; pUnkOuter
0x18056810f  lea     rax, [rsp+150h+var_D8]
0x180568114  lea     r9, IID_IMXAttributes; riid
0x18056811b  mov     [rsp+150h+ppv], rax; ppv
0x180568120  lea     rcx, CLSID_SAXAttributes60; rclsid
0x180568127  lea     r8d, [rdx+1]; dwClsContext
0x18056812b  call    cs:__imp_CoCreateInstance
0x180568131  mov     edi, eax
0x180568133  test    eax, eax
0x180568135  jns     short loc_18056817A
0x180568137  mov     rax, cs:WPP_GLOBAL_Control
0x18056813e  lea     rcx, WPP_GLOBAL_Control
0x180568145  cmp     rax, rcx
0x180568148  jz      loc_18056923F
0x18056814e  mov     ebx, 8
0x180568153  test    [rax+1Ch], bl
0x180568156  jz      loc_18056923F
0x18056815c  cmp     byte ptr [rax+19h], 2
0x180568160  jb      loc_18056923F
0x180568166  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056816b  lea     edx, [rbx+3Eh]
0x18056816e  lea     rcx, aFailedToCocrea_0; "Failed to cocreate MXAttributes"
0x180568175  jmp     loc_18056921C
0x18056817a  mov     rcx, [rbp+50h+var_D0]
0x18056817e  lea     r8, [rsp+150h+var_E8]
0x180568183  lea     rdx, IID_ISAXContentHandler
0x18056818a  mov     rax, [rcx]
0x18056818d  mov     rax, [rax]
0x180568190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180568195  mov     edi, eax
0x180568197  test    eax, eax
0x180568199  jns     short loc_1805681DE
0x18056819b  mov     rax, cs:WPP_GLOBAL_Control
0x1805681a2  lea     rcx, WPP_GLOBAL_Control
0x1805681a9  cmp     rax, rcx
0x1805681ac  jz      loc_18056923F
0x1805681b2  mov     ebx, 8
0x1805681b7  test    [rax+1Ch], bl
0x1805681ba  jz      loc_18056923F
0x1805681c0  cmp     byte ptr [rax+19h], 2
0x1805681c4  jb      loc_18056923F
0x1805681ca  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805681cf  lea     edx, [rbx+3Fh]
0x1805681d2  lea     rcx, aFailedToQiIsax_0; "Failed to QI ISAXContentHandler from IM"...
0x1805681d9  jmp     loc_18056921C
0x1805681de  mov     rcx, [rsp+150h+var_D8]
0x1805681e3  lea     r8, [rbp+50h+var_C0]
0x1805681e7  lea     rdx, IID_ISAXAttributes
0x1805681ee  mov     rax, [rcx]
0x1805681f1  mov     rax, [rax]
0x1805681f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805681f9  xor     edx, edx
0x1805681fb  mov     edi, eax
0x1805681fd  test    eax, eax
0x1805681ff  jns     short loc_180568242
0x180568201  mov     rax, cs:WPP_GLOBAL_Control
0x180568208  lea     rcx, WPP_GLOBAL_Control
0x18056820f  cmp     rax, rcx
0x180568212  jz      loc_18056923F
0x180568218  lea     ebx, [rdx+8]
0x18056821b  test    [rax+1Ch], bl
0x18056821e  jz      loc_18056923F
0x180568224  cmp     byte ptr [rax+19h], 2
0x180568228  jb      loc_18056923F
0x18056822e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180568233  lea     edx, [rbx+40h]
0x180568236  lea     rcx, aFailedToQiIsax; "Failed to QI ISAXAttributes from IMXAtt"...
0x18056823d  jmp     loc_18056921C
0x180568242  mov     rcx, [rsp+150h+var_E8]
0x180568247  lea     r8, aPnpredirection; "PnpRedirectionSettings"
0x18056824e  mov     [rsp+150h+var_118], rdx
0x180568253  lea     r9, sourceString
0x18056825a  mov     [rsp+150h+var_120], 16h
0x180568262  mov     [rsp+150h+var_128], r8
0x180568267  xor     r8d, r8d
0x18056826a  mov     rax, [rcx]
0x18056826d  mov     dword ptr [rsp+150h+ppv], edx
0x180568271  lea     rdx, sourceString
0x180568278  mov     rax, [rax+40h]
0x18056827c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180568281  xor     edx, edx
0x180568283  mov     edi, eax
0x180568285  test    eax, eax
0x180568287  jns     short loc_1805682CA
0x180568289  mov     rax, cs:WPP_GLOBAL_Control
0x180568290  lea     rcx, WPP_GLOBAL_Control
0x180568297  cmp     rax, rcx
0x18056829a  jz      loc_18056923F
0x1805682a0  lea     ebx, [rdx+8]
0x1805682a3  test    [rax+1Ch], bl
0x1805682a6  jz      loc_18056923F
0x1805682ac  cmp     byte ptr [rax+19h], 2
0x1805682b0  jb      loc_18056923F
0x1805682b6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805682bb  lea     edx, [rbx+41h]
0x1805682be  lea     rcx, aFailedToStartX; "Failed to start Xml node"
0x1805682c5  jmp     loc_18056921C
0x1805682ca  mov     rcx, [rsp+150h+var_E8]
0x1805682cf  lea     r8, aForcedisablepn_0; "ForceDisablePnpDeviceRedirection"
0x1805682d6  mov     [rsp+150h+var_118], rdx
0x1805682db  lea     r9, sourceString
0x1805682e2  mov     [rsp+150h+var_120], 20h ; ' '
0x1805682ea  mov     [rsp+150h+var_128], r8
0x1805682ef  xor     r8d, r8d
0x1805682f2  mov     rax, [rcx]
0x1805682f5  mov     dword ptr [rsp+150h+ppv], edx
0x1805682f9  lea     rdx, sourceString
0x180568300  mov     rax, [rax+40h]
0x180568304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180568309  mov     edi, eax
0x18056830b  test    eax, eax
0x18056830d  js      loc_1805691EA
0x180568313  mov     rcx, [rsp+150h+var_E8]
0x180568318  lea     r9, aFalse_0; "false"
0x18056831f  test    ebx, ebx
0x180568321  lea     rdx, aTrue; "true"
0x180568328  cmovz   rdx, r9
0x18056832c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180568330  mov     rax, [rcx]
0x180568333  xor     ebx, ebx
0x180568335  inc     r8
0x180568338  cmp     [rdx+r8*2], bx
0x18056833d  jnz     short loc_180568335
0x18056833f  mov     rax, [rax+50h]
0x180568343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180568348  mov     edi, eax
0x18056834a  test    eax, eax
0x18056834c  js      loc_1805691EA
0x180568352  mov     rcx, [rsp+150h+var_E8]
0x180568357  lea     rdx, aForcedisablepn_0; "ForceDisablePnpDeviceRedirection"
0x18056835e  mov     [rsp+150h+var_120], 20h ; ' '
0x180568366  lea     r9, sourceString
0x18056836d  mov     [rsp+150h+var_128], rdx
0x180568372  xor     r8d, r8d
0x180568375  lea     rdx, sourceString
0x18056837c  mov     dword ptr [rsp+150h+ppv], ebx
0x180568380  mov     rax, [rcx]
0x180568383  mov     rax, [rax+48h]
0x180568387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18056838c  mov     edi, eax
0x18056838e  test    eax, eax
0x180568390  js      loc_1805691EA
0x180568396  mov     rcx, [rsp+150h+var_E8]
0x18056839b  lea     rdx, aEnabledynamicd; "EnableDynamicDeviceRedirection"
0x1805683a2  mov     [rsp+150h+var_118], rbx
0x1805683a7  lea     r9, sourceString
0x1805683ae  mov     [rsp+150h+var_120], 1Eh
0x1805683b6  xor     r8d, r8d
0x1805683b9  mov     [rsp+150h+var_128], rdx
0x1805683be  lea     rdx, sourceString
0x1805683c5  mov     rax, [rcx]
0x1805683c8  mov     dword ptr [rsp+150h+ppv], ebx
0x1805683cc  mov     rax, [rax+40h]
0x1805683d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805683d5  mov     edi, eax
0x1805683d7  test    eax, eax
0x1805683d9  js      loc_1805691BD
0x1805683df  mov     rcx, [rsp+150h+var_E8]
0x1805683e4  lea     r8, aFalse_0; "false"
0x1805683eb  test    esi, esi
0x1805683ed  lea     rdx, aTrue; "true"
0x1805683f4  cmovz   rdx, r8
0x1805683f8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1805683fc  mov     rax, [rcx]
0x1805683ff  inc     r8
0x180568402  cmp     [rdx+r8*2], bx
0x180568407  jnz     short loc_1805683FF
0x180568409  mov     rax, [rax+50h]
0x18056840d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180568412  mov     edi, eax
0x180568414  test    eax, eax
0x180568416  js      loc_1805691BD
0x18056841c  mov     rcx, [rsp+150h+var_E8]
0x180568421  lea     rdx, aEnabledynamicd; "EnableDynamicDeviceRedirection"
0x180568428  mov     [rsp+150h+var_120], 1Eh
0x180568430  lea     rsi, sourceString
0x180568437  mov     [rsp+150h+var_128], rdx
0x18056843c  mov     r9, rsi
0x18056843f  xor     r8d, r8d
0x180568442  mov     dword ptr [rsp+150h+ppv], ebx
0x180568446  mov     rax, [rcx]
0x180568449  mov     rdx, rsi
0x18056844c  mov     rax, [rax+48h]
0x180568450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180568455  mov     edi, eax
0x180568457  test    eax, eax
0x180568459  js      loc_1805691BD
0x18056845f  mov     rcx, [rsp+150h+var_E8]
0x180568464  lea     rdx, aEnabletsredire; "EnableTsRedirectFlag"
0x18056846b  mov     [rsp+150h+var_118], rbx
0x180568470  mov     r9, rsi
0x180568473  mov     [rsp+150h+var_120], 14h
0x18056847b  xor     r8d, r8d
0x18056847e  mov     [rsp+150h+var_128], rdx
0x180568483  mov     rdx, rsi
0x180568486  mov     rax, [rcx]
0x180568489  mov     dword ptr [rsp+150h+ppv], ebx
0x18056848d  mov     rax, [rax+40h]
0x180568491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180568496  mov     edi, eax
0x180568498  test    eax, eax
0x18056849a  js      loc_180569184
0x1805684a0  mov     rcx, [rsp+150h+var_E8]
0x1805684a5  lea     r8, aFalse_0; "false"
0x1805684ac  test    r14d, r14d
0x1805684af  lea     rdx, aTrue; "true"
0x1805684b6  cmovz   rdx, r8
0x1805684ba  or      r8, 0FFFFFFFFFFFFFFFFh
0x1805684be  mov     rax, [rcx]
0x1805684c1  inc     r8
0x1805684c4  cmp     [rdx+r8*2], bx
0x1805684c9  jnz     short loc_1805684C1
0x1805684cb  mov     rax, [rax+50h]
0x1805684cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805684d4  mov     edi, eax
0x1805684d6  test    eax, eax
0x1805684d8  js      loc_180569184
0x1805684de  mov     rcx, [rsp+150h+var_E8]
0x1805684e3  lea     rdx, aEnabletsredire; "EnableTsRedirectFlag"
0x1805684ea  mov     [rsp+150h+var_120], 14h
0x1805684f2  mov     r9, rsi
0x1805684f5  mov     [rsp+150h+var_128], rdx
0x1805684fa  xor     r8d, r8d
0x1805684fd  mov     rdx, rsi
0x180568500  mov     dword ptr [rsp+150h+ppv], ebx
0x180568504  mov     rax, [rcx]
0x180568507  mov     rax, [rax+48h]
0x18056850b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180568510  mov     edi, eax
0x180568512  test    eax, eax
0x180568514  js      loc_180569184
0x18056851a  lea     rcx, aEnabled; "Enabled"
0x180568521  call    cs:__imp_SysAllocString
0x180568527  lea     rcx, aTrue; "true"
0x18056852e  mov     [rsp+150h+var_F0], rax
0x180568533  mov     rbx, rax
0x180568536  call    cs:__imp_SysAllocString
0x18056853c  lea     rcx, aFalse_0; "false"
0x180568543  mov     [rsp+150h+var_F8], rax
0x180568548  mov     r14, rax
0x18056854b  call    cs:__imp_SysAllocString
0x180568551  lea     rcx, sourceString; psz
0x180568558  mov     [rsp+150h+var_100], rax
0x18056855d  mov     rsi, rax
0x180568560  call    cs:__imp_SysAllocString
0x180568566  mov     [rbp+50h+bstrString], rax
0x18056856a  test    rbx, rbx
0x18056856d  jz      loc_18056911C
0x180568573  test    r14, r14
  ... truncated ...
```
