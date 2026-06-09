# CArchiveTooling::saveUploadHrToSasUrlNodeInRegitry(long)

- ea: `0x1800f13e4`
- end: `0x1800f19d5`
- name: `?saveUploadHrToSasUrlNodeInRegitry@CArchiveTooling@@SAJJ@Z`
- size: `1521`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800fa41c`

## callees

- `0x1800e4628`
- `0x1800e7bac`
- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f0a00`
- `0x1800f1218`
- `0x1800f13e4`
- `0x180118954`
- `0x180191010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800f184b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800f184b`
- `OLEAUT32!__imp_VariantInit` at `0x1800f141e`
- `OLEAUT32!__imp_VariantInit` at `0x1800f141e`
- `OLEAUT32!__imp_VariantClear` at `0x1800f147b`
- `OLEAUT32!__imp_VariantClear` at `0x1800f18c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800f1977`
- `OLEAUT32!__imp_VariantClear` at `0x1800f147b`
- `OLEAUT32!__imp_VariantClear` at `0x1800f18c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800f1977`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800f15b9`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800f15b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f159b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f161d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f159b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f161d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f151f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f151f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800f187b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800f187b`

## string_xrefs

- `0x1800f145b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f1534`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f15d8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f178e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f15a8`: `Getting results registry value length failed`
- `0x1800f162a`: `Getting results registry value failed`
- `0x1800f1948`: `Result XML input document load failed`
- `0x1800f191d`: `Result XML input document retrieving root document element failed`
- `0x1800f1914`: `Result XML input document get_firstChild failed`
- `0x1800f171f`: `Result XML root node get Collections element failed`
- `0x1800f175b`: `Result XML get SasUrl element failed`
- `0x1800f17c2`: `Result XML conversion to element failed`
- `0x1800f1806`: `Result XML setAttribute HRESULT failed`
- `0x1800f183e`: `Result XML get_xml string failed`
- `0x1800f1888`: `Update the registry with results location failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CArchiveTooling::saveUploadHrToSasUrlNodeInRegitry(LONG a1)
{
  __int64 v2; // rsi
  unsigned int v3; // r14d
  __int64 v5; // rdi
  __int64 v6; // r9
  __int64 v7; // rdx
  HRESULT v8; // eax
  LSTATUS ValueW; // eax
  TelemetryWriter *v10; // rcx
  BSTR pvData; // rax
  BSTR v12; // rbx
  LSTATUS v13; // eax
  TelemetryWriter *v14; // rcx
  int v15; // eax
  TelemetryWriter *v16; // rcx
  unsigned int v17; // ebx
  LPVOID v18; // r14
  __int64 (__fastcall *v19)(LPVOID, __int64 *); // rbx
  int v20; // eax
  TelemetryWriter *v21; // rcx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, __int64 *); // r14
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, __int64, __int64 *); // r14
  const char *v26; // rdx
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, __int64, __int64 *); // rbx
  __int64 v29; // rbx
  int v30; // eax
  TelemetryWriter *v31; // rcx
  const char *v32; // rdx
  LPVOID v33; // rdi
  __int64 (__fastcall *v34)(LPVOID, BSTR *); // rbx
  UINT v35; // eax
  LSTATUS v36; // eax
  TelemetryWriter *v37; // rcx
  int ppv; // [rsp+20h] [rbp-89h]
  int ppva; // [rsp+20h] [rbp-89h]
  int ppvb; // [rsp+20h] [rbp-89h]
  LPVOID v41; // [rsp+40h] [rbp-69h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-61h] BYREF
  __int64 v43; // [rsp+50h] [rbp-59h] BYREF
  __int64 v44; // [rsp+58h] [rbp-51h] BYREF
  __int64 v45; // [rsp+60h] [rbp-49h] BYREF
  __int64 v46; // [rsp+68h] [rbp-41h] BYREF
  __int64 v47; // [rsp+70h] [rbp-39h] BYREF
  __int64 v48; // [rsp+78h] [rbp-31h] BYREF
  __int64 v49; // [rsp+80h] [rbp-29h] BYREF
  __int64 v50; // [rsp+88h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-19h] BYREF
  VARIANTARG v52; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  __int16 v54; // [rsp+110h] [rbp+67h] BYREF
  DWORD len; // [rsp+118h] [rbp+6Fh] BYREF
  DWORD pdwType; // [rsp+120h] [rbp+77h] BYREF
  BSTR v57; // [rsp+128h] [rbp+7Fh] BYREF

  v41 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  v48 = 0;
  pbstr = 0;
  VariantInit(&pvarg);
  pvarg.vt = 3;
  pvarg.lVal = a1;
  wil::make_bstr_nothrow(&v49, L"/Collection");
  v2 = v49;
  if ( !v49 )
  {
    v3 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4FF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
      (const char *)0x8007000ELL,
      ppv);
LABEL_3:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v49);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v41);
    return v3;
  }
  wil::make_bstr_nothrow(&v50, L"SasUrl");
  v5 = v50;
  if ( !v50 )
  {
    v3 = -2147024882;
    v6 = 2147942414LL;
    v7 = 1282;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
      (const char *)v6,
      ppv);
LABEL_42:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
    goto LABEL_3;
  }
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v41);
  v8 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &v41);
  v3 = v8;
  if ( v8 < 0 )
  {
    v6 = (unsigned int)v8;
    v7 = 1285;
    goto LABEL_8;
  }
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v41 + 504LL))(v41, 0);
  len = 0;
  pdwType = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, c_RegistryLastRunKey, L"Results", 2u, &pdwType, 0, &len);
  if ( ValueW )
    TelemetryWriter::Write(v10, "Getting results registry value length failed", ValueW);
  pvData = SysAllocStringByteLen(0, len);
  v12 = pvData;
  v57 = pvData;
  if ( !pvData )
  {
    v3 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
      (const char *)0x8007000ELL,
      ppva);
LABEL_41:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v57);
    goto LABEL_42;
  }
  v13 = RegGetValueW(HKEY_LOCAL_MACHINE, c_RegistryLastRunKey, L"Results", 2u, &pdwType, pvData, &len);
  if ( v13 )
  {
    TelemetryWriter::Write(v14, "Getting results registry value failed", v13);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v57);
    v3 = 0;
    goto LABEL_42;
  }
  v54 = -1;
  v15 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)v41 + 520LL))(v41, v12, &v54);
  v17 = v15;
  if ( v15 >= 0 && v54 )
  {
    v18 = v41;
    v19 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v41 + 360LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
    v20 = v19(v18, &v46);
    v3 = v20;
    if ( v20 < 0 || (v22 = v46) == 0 )
    {
      v26 = "Result XML input document retrieving root document element failed";
      goto LABEL_40;
    }
    v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 104LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
    v20 = v23(v22, &v45);
    v3 = v20;
    if ( v20 < 0 || (v24 = v45) == 0 )
    {
      v26 = "Result XML input document get_firstChild failed";
      goto LABEL_40;
    }
    v25 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v45 + 296LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
    v20 = v25(v24, v2, &v44);
    v3 = v20;
    if ( v20 < 0 )
    {
      v26 = "Result XML root node get Collections element failed";
LABEL_40:
      TelemetryWriter::Write(v21, v26, v20);
      goto LABEL_41;
    }
    v27 = v44;
    v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v44 + 296LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
    v20 = v28(v27, v5, &v43);
    v3 = v20;
    if ( v20 < 0 )
    {
      v26 = "Result XML get SasUrl element failed";
      goto LABEL_40;
    }
    wil::make_bstr_nothrow(&v47, L"HRESULT");
    v29 = v47;
    if ( !v47 )
    {
      v3 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x557,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
        (const char *)0x8007000ELL,
        ppvb);
LABEL_27:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
      goto LABEL_41;
    }
    v30 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v43, &v48);
    v3 = v30;
    if ( v30 < 0 )
    {
      v32 = "Result XML conversion to element failed";
LABEL_30:
      TelemetryWriter::Write(v31, v32, v30);
      goto LABEL_27;
    }
    v52 = pvarg;
    v30 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v48 + 360LL))(v48, v29, &v52);
    v3 = v30;
    if ( v30 < 0 )
    {
      v32 = "Result XML setAttribute HRESULT failed";
      goto LABEL_30;
    }
    v33 = v41;
    v34 = *(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)v41 + 272LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pbstr,
      0);
    v30 = v34(v33, &pbstr);
    v3 = v30;
    if ( v30 < 0 )
    {
      v32 = "Result XML get_xml string failed";
      goto LABEL_30;
    }
    v35 = SysStringLen(pbstr);
    v36 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_RegistryLastRunKey, L"Results", 1u, pbstr, 2 * v35);
    if ( v36 )
      TelemetryWriter::Write(v37, "Update the registry with results location failed", v36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v57);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v49);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v41);
    return 0;
  }
  else
  {
    TelemetryWriter::Write(v16, "Result XML input document load failed", v15);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v57);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v49);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v41);
    return v17;
  }
}

```

## disassembly

```asm
0x1800f13e4  push    rbp
0x1800f13e6  push    rbx
0x1800f13e7  push    rsi
0x1800f13e8  push    rdi
0x1800f13e9  push    r14
0x1800f13eb  push    r15
0x1800f13ed  lea     rbp, [rsp-2Fh]
0x1800f13f2  sub     rsp, 0D8h
0x1800f13f9  mov     ebx, ecx
0x1800f13fb  xor     r15d, r15d
0x1800f13fe  mov     [rbp+57h+var_C0], r15
0x1800f1402  mov     [rbp+57h+var_98], r15
0x1800f1406  mov     [rbp+57h+var_A0], r15
0x1800f140a  mov     [rbp+57h+var_A8], r15
0x1800f140e  mov     [rbp+57h+var_B0], r15
0x1800f1412  mov     [rbp+57h+var_88], r15
0x1800f1416  mov     [rbp+57h+pbstr], r15
0x1800f141a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800f141e  call    cs:__imp_VariantInit
0x1800f1424  nop
0x1800f1425  lea     eax, [r15+3]
0x1800f1429  mov     word ptr [rbp+57h+pvarg], ax
0x1800f142d  mov     dword ptr [rbp+57h+pvarg+8], ebx
0x1800f1430  lea     rdx, aCollection_0; "/Collection"
0x1800f1437  lea     rcx, [rbp+57h+var_80]
0x1800f143b  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800f1440  nop
0x1800f1441  mov     rsi, [rbp+57h+var_80]
0x1800f1445  test    rsi, rsi
0x1800f1448  jnz     loc_1800F14CF
0x1800f144e  mov     rcx, [rbp+5Fh]; this
0x1800f1452  mov     r14d, 8007000Eh
0x1800f1458  mov     r9d, r14d; char *
0x1800f145b  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f1462  mov     edx, 4FFh; void *
0x1800f1467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f146c  nop
0x1800f146d  lea     rcx, [rbp+57h+var_80]
0x1800f1471  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f1476  nop
0x1800f1477  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800f147b  call    cs:__imp_VariantClear
0x1800f1481  nop
0x1800f1482  lea     rcx, [rbp+57h+pbstr]
0x1800f1486  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f148b  nop
0x1800f148c  lea     rcx, [rbp+57h+var_88]
0x1800f1490  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1495  nop
0x1800f1496  lea     rcx, [rbp+57h+var_B0]
0x1800f149a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f149f  nop
0x1800f14a0  lea     rcx, [rbp+57h+var_A8]
0x1800f14a4  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f14a9  nop
0x1800f14aa  lea     rcx, [rbp+57h+var_A0]
0x1800f14ae  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f14b3  nop
0x1800f14b4  lea     rcx, [rbp+57h+var_98]
0x1800f14b8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f14bd  nop
0x1800f14be  lea     rcx, [rbp+57h+var_C0]
0x1800f14c2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f14c7  mov     eax, r14d
0x1800f14ca  jmp     loc_1800F19C5
0x1800f14cf  lea     rdx, aSasurl; "SasUrl"
0x1800f14d6  lea     rcx, [rbp+57h+var_78]
0x1800f14da  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800f14df  nop
0x1800f14e0  mov     rdi, [rbp+57h+var_78]
0x1800f14e4  test    rdi, rdi
0x1800f14e7  jnz     short loc_1800F14F9
0x1800f14e9  mov     r14d, 8007000Eh
0x1800f14ef  mov     r9d, r14d
0x1800f14f2  mov     edx, 502h
0x1800f14f7  jmp     short loc_1800F1534
0x1800f14f9  lea     rcx, [rbp+57h+var_C0]
0x1800f14fd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1502  lea     rax, [rbp+57h+var_C0]
0x1800f1506  mov     [rsp+100h+ppv], rax; int
0x1800f150b  lea     r9, IID_IXMLDOMDocument; riid
0x1800f1512  xor     edx, edx; pUnkOuter
0x1800f1514  lea     r8d, [rdx+1]; dwClsContext
0x1800f1518  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800f151f  call    cs:__imp_CoCreateInstance
0x1800f1525  mov     r14d, eax
0x1800f1528  test    eax, eax
0x1800f152a  jns     short loc_1800F1549
0x1800f152c  mov     r9d, eax; char *
0x1800f152f  mov     edx, 505h; void *
0x1800f1534  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f153b  mov     rcx, [rbp+5Fh]; this
0x1800f153f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1544  jmp     loc_1800F1937
0x1800f1549  mov     rcx, [rbp+57h+var_C0]
0x1800f154d  mov     rax, [rcx]
0x1800f1550  xor     edx, edx
0x1800f1552  mov     rax, [rax+1F8h]
0x1800f1559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f155e  mov     [rbp+57h+len], r15d
0x1800f1562  mov     [rbp+57h+pdwType], r15d
0x1800f1566  lea     rax, [rbp+57h+len]
0x1800f156a  mov     [rsp+100h+pcbData], rax; pcbData
0x1800f156f  mov     [rsp+100h+pvData], r15; pvData
0x1800f1574  lea     rax, [rbp+57h+pdwType]
0x1800f1578  mov     [rsp+100h+ppv], rax; int
0x1800f157d  mov     r14d, 2
0x1800f1583  mov     r9d, r14d; dwFlags
0x1800f1586  lea     r8, ValueName; "Results"
0x1800f158d  mov     rdx, cs:?c_RegistryLastRunKey@@3PEAGEA; lpSubKey
0x1800f1594  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f159b  call    cs:__imp_RegGetValueW
0x1800f15a1  test    eax, eax
0x1800f15a3  jz      short loc_1800F15B4
0x1800f15a5  mov     r8d, eax; int
0x1800f15a8  lea     rdx, aGettingResults; "Getting results registry value length f"...
0x1800f15af  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800f15b4  mov     edx, [rbp+57h+len]; len
0x1800f15b7  xor     ecx, ecx; psz
0x1800f15b9  call    cs:__imp_SysAllocStringByteLen
0x1800f15bf  mov     rbx, rax
0x1800f15c2  mov     [rbp+57h+arg_18], rax
0x1800f15c6  test    rax, rax
0x1800f15c9  jnz     short loc_1800F15EE
0x1800f15cb  mov     rcx, [rbp+5Fh]; this
0x1800f15cf  mov     r14d, 8007000Eh
0x1800f15d5  mov     r9d, r14d; char *
0x1800f15d8  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f15df  mov     edx, 51Ah; void *
0x1800f15e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f15e9  jmp     loc_1800F192D
0x1800f15ee  lea     rax, [rbp+57h+len]
0x1800f15f2  mov     [rsp+100h+pcbData], rax; pcbData
0x1800f15f7  mov     [rsp+100h+pvData], rbx; pvData
0x1800f15fc  lea     rax, [rbp+57h+pdwType]
0x1800f1600  mov     [rsp+100h+ppv], rax; int
0x1800f1605  mov     r9d, r14d; dwFlags
0x1800f1608  lea     r8, ValueName; "Results"
0x1800f160f  mov     rdx, cs:?c_RegistryLastRunKey@@3PEAGEA; lpSubKey
0x1800f1616  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f161d  call    cs:__imp_RegGetValueW
0x1800f1623  test    eax, eax
0x1800f1625  jz      short loc_1800F1648
0x1800f1627  mov     r8d, eax; int
0x1800f162a  lea     rdx, aGettingResults_0; "Getting results registry value failed"
0x1800f1631  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800f1636  nop
0x1800f1637  lea     rcx, [rbp+57h+arg_18]
0x1800f163b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f1640  mov     r14d, r15d
0x1800f1643  jmp     loc_1800F1937
0x1800f1648  or      eax, 0FFFFFFFFh
0x1800f164b  mov     [rbp+57h+arg_0], ax
0x1800f164f  mov     rcx, [rbp+57h+var_C0]
0x1800f1653  mov     rax, [rcx]
0x1800f1656  lea     r8, [rbp+57h+arg_0]
0x1800f165a  mov     rdx, rbx
0x1800f165d  mov     rax, [rax+208h]
0x1800f1664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1669  mov     ebx, eax
0x1800f166b  test    eax, eax
0x1800f166d  js      loc_1800F1945
0x1800f1673  cmp     [rbp+57h+arg_0], r15w
0x1800f1678  jz      loc_1800F1945
0x1800f167e  mov     r14, [rbp+57h+var_C0]
0x1800f1682  mov     rax, [r14]
0x1800f1685  mov     rbx, [rax+168h]
0x1800f168c  lea     rcx, [rbp+57h+var_98]
0x1800f1690  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1695  lea     rdx, [rbp+57h+var_98]
0x1800f1699  mov     rcx, r14
0x1800f169c  mov     rax, rbx
0x1800f169f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f16a4  mov     r14d, eax
0x1800f16a7  test    eax, eax
0x1800f16a9  js      loc_1800F191D
0x1800f16af  mov     rbx, [rbp+57h+var_98]
0x1800f16b3  test    rbx, rbx
0x1800f16b6  jz      loc_1800F191D
0x1800f16bc  mov     rax, [rbx]
0x1800f16bf  mov     r14, [rax+68h]
0x1800f16c3  lea     rcx, [rbp+57h+var_A0]
0x1800f16c7  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f16cc  lea     rdx, [rbp+57h+var_A0]
0x1800f16d0  mov     rcx, rbx
0x1800f16d3  mov     rax, r14
0x1800f16d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f16db  mov     r14d, eax
0x1800f16de  test    eax, eax
0x1800f16e0  js      loc_1800F1914
0x1800f16e6  mov     rbx, [rbp+57h+var_A0]
0x1800f16ea  test    rbx, rbx
0x1800f16ed  jz      loc_1800F1914
0x1800f16f3  mov     rax, [rbx]
0x1800f16f6  mov     r14, [rax+128h]
0x1800f16fd  lea     rcx, [rbp+57h+var_A8]
0x1800f1701  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1706  lea     r8, [rbp+57h+var_A8]
0x1800f170a  mov     rdx, rsi
0x1800f170d  mov     rcx, rbx
0x1800f1710  mov     rax, r14
0x1800f1713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1718  mov     r14d, eax
0x1800f171b  test    eax, eax
0x1800f171d  jns     short loc_1800F172B
0x1800f171f  lea     rdx, aResultXmlRootN; "Result XML root node get Collections el"...
0x1800f1726  jmp     loc_1800F1924
0x1800f172b  mov     rsi, [rbp+57h+var_A8]
0x1800f172f  mov     rax, [rsi]
0x1800f1732  mov     rbx, [rax+128h]
0x1800f1739  lea     rcx, [rbp+57h+var_B0]
0x1800f173d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1742  lea     r8, [rbp+57h+var_B0]
0x1800f1746  mov     rdx, rdi
0x1800f1749  mov     rcx, rsi
0x1800f174c  mov     rax, rbx
0x1800f174f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1754  mov     r14d, eax
0x1800f1757  test    eax, eax
0x1800f1759  jns     short loc_1800F1767
0x1800f175b  lea     rdx, aResultXmlGetSa; "Result XML get SasUrl element failed"
0x1800f1762  jmp     loc_1800F1924
0x1800f1767  lea     rdx, aHresult; "HRESULT"
0x1800f176e  lea     rcx, [rbp+57h+var_90]
0x1800f1772  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800f1777  nop
0x1800f1778  mov     rbx, [rbp+57h+var_90]
0x1800f177c  test    rbx, rbx
0x1800f177f  jnz     short loc_1800F17AE
0x1800f1781  mov     rcx, [rbp+5Fh]; this
0x1800f1785  mov     r14d, 8007000Eh
0x1800f178b  mov     r9d, r14d; char *
0x1800f178e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f1795  mov     edx, 557h; void *
0x1800f179a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f179f  nop
0x1800f17a0  lea     rcx, [rbp+57h+var_90]
0x1800f17a4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f17a9  jmp     loc_1800F192D
0x1800f17ae  lea     rdx, [rbp+57h+var_88]
0x1800f17b2  lea     rcx, [rbp+57h+var_B0]
0x1800f17b6  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x1800f17bb  mov     r14d, eax
0x1800f17be  test    eax, eax
0x1800f17c0  jns     short loc_1800F17D3
0x1800f17c2  lea     rdx, aResultXmlConve; "Result XML conversion to element failed"
0x1800f17c9  mov     r8d, eax; int
0x1800f17cc  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800f17d1  jmp     short loc_1800F17A0
0x1800f17d3  mov     rcx, [rbp+57h+var_88]
0x1800f17d7  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800f17db  movaps  [rbp+57h+var_50], xmm0
0x1800f17df  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800f17e4  movsd   [rbp+57h+var_40], xmm1
0x1800f17e9  mov     rax, [rcx]
0x1800f17ec  lea     r8, [rbp+57h+var_50]
0x1800f17f0  mov     rdx, rbx
0x1800f17f3  mov     rax, [rax+168h]
0x1800f17fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f17ff  mov     r14d, eax
0x1800f1802  test    eax, eax
0x1800f1804  jns     short loc_1800F180F
0x1800f1806  lea     rdx, aResultXmlSetat; "Result XML setAttribute HRESULT failed"
0x1800f180d  jmp     short loc_1800F17C9
0x1800f180f  mov     rdi, [rbp+57h+var_C0]
0x1800f1813  mov     rax, [rdi]
0x1800f1816  mov     rbx, [rax+110h]
0x1800f181d  xor     edx, edx
0x1800f181f  lea     rcx, [rbp+57h+pbstr]
0x1800f1823  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f1828  lea     rdx, [rbp+57h+pbstr]
0x1800f182c  mov     rcx, rdi
0x1800f182f  mov     rax, rbx
0x1800f1832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1837  mov     r14d, eax
0x1800f183a  test    eax, eax
0x1800f183c  jns     short loc_1800F1847
0x1800f183e  lea     rdx, aResultXmlGetXm; "Result XML get_xml string failed"
0x1800f1845  jmp     short loc_1800F17C9
0x1800f1847  mov     rcx, [rbp+57h+pbstr]; pbstr
0x1800f184b  call    cs:__imp_SysStringLen
0x1800f1851  add     eax, eax
0x1800f1853  mov     r10, [rbp+57h+pbstr]
0x1800f1857  mov     dword ptr [rsp+100h+pvData], eax; cbData
0x1800f185b  mov     [rsp+100h+ppv], r10; lpData
0x1800f1860  mov     r9d, 1; dwType
0x1800f1866  lea     r8, ValueName; "Results"
0x1800f186d  mov     rdx, cs:?c_RegistryLastRunKey@@3PEAGEA; lpSubKey
0x1800f1874  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f187b  call    cs:__imp_RegSetKeyValueW
0x1800f1881  test    eax, eax
0x1800f1883  jz      short loc_1800F1895
0x1800f1885  mov     r8d, eax; int
0x1800f1888  lea     rdx, aUpdateTheRegis_0; "Update the registry with results locati"...
0x1800f188f  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800f1894  nop
0x1800f1895  lea     rcx, [rbp+57h+var_90]
0x1800f1899  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f189e  nop
0x1800f189f  lea     rcx, [rbp+57h+arg_18]
  ... truncated ...
```
