# CArchiveTooling::saveUploadHrToSasUrlNodeInRegitry(long)

- ea: `0x1800f1d50`
- end: `0x1800f237e`
- name: `?saveUploadHrToSasUrlNodeInRegitry@CArchiveTooling@@SAJJ@Z`
- size: `1582`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800fb4ac`

## callees

- `0x1800e4744`
- `0x1800e7d84`
- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f1278`
- `0x1800f1b68`
- `0x1800f1d50`
- `0x18011a15c`
- `0x180193010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800f21db`
- `OLEAUT32!__imp_SysStringLen` at `0x1800f21db`
- `OLEAUT32!__imp_VariantInit` at `0x1800f1d8a`
- `OLEAUT32!__imp_VariantInit` at `0x1800f1d8a`
- `OLEAUT32!__imp_VariantClear` at `0x1800f1ded`
- `OLEAUT32!__imp_VariantClear` at `0x1800f225d`
- `OLEAUT32!__imp_VariantClear` at `0x1800f2319`
- `OLEAUT32!__imp_VariantClear` at `0x1800f1ded`
- `OLEAUT32!__imp_VariantClear` at `0x1800f225d`
- `OLEAUT32!__imp_VariantClear` at `0x1800f2319`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800f1f3d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800f1f3d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1f19`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1fa7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1f19`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1fa7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f1e97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f1e97`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800f2211`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800f2211`

## string_xrefs

- `0x1800f1dcd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f1eb2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f1f62`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f211e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800f1f2c`: `Getting results registry value length failed`
- `0x1800f1fba`: `Getting results registry value failed`
- `0x1800f22ea`: `Result XML input document load failed`
- `0x1800f22bf`: `Result XML input document retrieving root document element failed`
- `0x1800f22b6`: `Result XML input document get_firstChild failed`
- `0x1800f20af`: `Result XML root node get Collections element failed`
- `0x1800f20eb`: `Result XML get SasUrl element failed`
- `0x1800f2152`: `Result XML conversion to element failed`
- `0x1800f2196`: `Result XML setAttribute HRESULT failed`
- `0x1800f21ce`: `Result XML get_xml string failed`
- `0x1800f2224`: `Update the registry with results location failed`

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
0x1800f1d50  push    rbp
0x1800f1d52  push    rbx
0x1800f1d53  push    rsi
0x1800f1d54  push    rdi
0x1800f1d55  push    r14
0x1800f1d57  push    r15
0x1800f1d59  lea     rbp, [rsp-2Fh]
0x1800f1d5e  sub     rsp, 0D8h
0x1800f1d65  mov     ebx, ecx
0x1800f1d67  xor     r15d, r15d
0x1800f1d6a  mov     [rbp+57h+var_C0], r15
0x1800f1d6e  mov     [rbp+57h+var_98], r15
0x1800f1d72  mov     [rbp+57h+var_A0], r15
0x1800f1d76  mov     [rbp+57h+var_A8], r15
0x1800f1d7a  mov     [rbp+57h+var_B0], r15
0x1800f1d7e  mov     [rbp+57h+var_88], r15
0x1800f1d82  mov     [rbp+57h+pbstr], r15
0x1800f1d86  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800f1d8a  call    cs:__imp_VariantInit
0x1800f1d91  nop     dword ptr [rax+rax+00h]
0x1800f1d96  nop
0x1800f1d97  lea     eax, [r15+3]
0x1800f1d9b  mov     word ptr [rbp+57h+pvarg], ax
0x1800f1d9f  mov     dword ptr [rbp+57h+pvarg+8], ebx
0x1800f1da2  lea     rdx, aCollection_0; "/Collection"
0x1800f1da9  lea     rcx, [rbp+57h+var_80]
0x1800f1dad  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800f1db2  nop
0x1800f1db3  mov     rsi, [rbp+57h+var_80]
0x1800f1db7  test    rsi, rsi
0x1800f1dba  jnz     loc_1800F1E47
0x1800f1dc0  mov     rcx, [rbp+5Fh]; this
0x1800f1dc4  mov     r14d, 8007000Eh
0x1800f1dca  mov     r9d, r14d; char *
0x1800f1dcd  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f1dd4  mov     edx, 4FFh; void *
0x1800f1dd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1dde  nop
0x1800f1ddf  lea     rcx, [rbp+57h+var_80]
0x1800f1de3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f1de8  nop
0x1800f1de9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800f1ded  call    cs:__imp_VariantClear
0x1800f1df4  nop     dword ptr [rax+rax+00h]
0x1800f1df9  nop
0x1800f1dfa  lea     rcx, [rbp+57h+pbstr]
0x1800f1dfe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f1e03  nop
0x1800f1e04  lea     rcx, [rbp+57h+var_88]
0x1800f1e08  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1e0d  nop
0x1800f1e0e  lea     rcx, [rbp+57h+var_B0]
0x1800f1e12  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1e17  nop
0x1800f1e18  lea     rcx, [rbp+57h+var_A8]
0x1800f1e1c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1e21  nop
0x1800f1e22  lea     rcx, [rbp+57h+var_A0]
0x1800f1e26  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1e2b  nop
0x1800f1e2c  lea     rcx, [rbp+57h+var_98]
0x1800f1e30  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1e35  nop
0x1800f1e36  lea     rcx, [rbp+57h+var_C0]
0x1800f1e3a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1e3f  mov     eax, r14d
0x1800f1e42  jmp     loc_1800F236D
0x1800f1e47  lea     rdx, aSasurl; "SasUrl"
0x1800f1e4e  lea     rcx, [rbp+57h+var_78]
0x1800f1e52  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800f1e57  nop
0x1800f1e58  mov     rdi, [rbp+57h+var_78]
0x1800f1e5c  test    rdi, rdi
0x1800f1e5f  jnz     short loc_1800F1E71
0x1800f1e61  mov     r14d, 8007000Eh
0x1800f1e67  mov     r9d, r14d
0x1800f1e6a  mov     edx, 502h
0x1800f1e6f  jmp     short loc_1800F1EB2
0x1800f1e71  lea     rcx, [rbp+57h+var_C0]
0x1800f1e75  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f1e7a  lea     rax, [rbp+57h+var_C0]
0x1800f1e7e  mov     [rsp+100h+ppv], rax; int
0x1800f1e83  lea     r9, IID_IXMLDOMDocument; riid
0x1800f1e8a  xor     edx, edx; pUnkOuter
0x1800f1e8c  lea     r8d, [rdx+1]; dwClsContext
0x1800f1e90  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800f1e97  call    cs:__imp_CoCreateInstance
0x1800f1e9e  nop     dword ptr [rax+rax+00h]
0x1800f1ea3  mov     r14d, eax
0x1800f1ea6  test    eax, eax
0x1800f1ea8  jns     short loc_1800F1EC7
0x1800f1eaa  mov     r9d, eax; char *
0x1800f1ead  mov     edx, 505h; void *
0x1800f1eb2  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f1eb9  mov     rcx, [rbp+5Fh]; this
0x1800f1ebd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1ec2  jmp     loc_1800F22D9
0x1800f1ec7  mov     rcx, [rbp+57h+var_C0]
0x1800f1ecb  mov     rax, [rcx]
0x1800f1ece  xor     edx, edx
0x1800f1ed0  mov     rax, [rax+1F8h]
0x1800f1ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1edc  mov     [rbp+57h+len], r15d
0x1800f1ee0  mov     [rbp+57h+pdwType], r15d
0x1800f1ee4  lea     rax, [rbp+57h+len]
0x1800f1ee8  mov     [rsp+100h+pcbData], rax; pcbData
0x1800f1eed  mov     [rsp+100h+pvData], r15; pvData
0x1800f1ef2  lea     rax, [rbp+57h+pdwType]
0x1800f1ef6  mov     [rsp+100h+ppv], rax; int
0x1800f1efb  mov     r14d, 2
0x1800f1f01  mov     r9d, r14d; dwFlags
0x1800f1f04  lea     r8, ValueName; "Results"
0x1800f1f0b  mov     rdx, cs:?c_RegistryLastRunKey@@3PEAGEA; lpSubKey
0x1800f1f12  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f1f19  call    cs:__imp_RegGetValueW
0x1800f1f20  nop     dword ptr [rax+rax+00h]
0x1800f1f25  test    eax, eax
0x1800f1f27  jz      short loc_1800F1F38
0x1800f1f29  mov     r8d, eax; int
0x1800f1f2c  lea     rdx, aGettingResults; "Getting results registry value length f"...
0x1800f1f33  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800f1f38  mov     edx, [rbp+57h+len]; len
0x1800f1f3b  xor     ecx, ecx; psz
0x1800f1f3d  call    cs:__imp_SysAllocStringByteLen
0x1800f1f44  nop     dword ptr [rax+rax+00h]
0x1800f1f49  mov     rbx, rax
0x1800f1f4c  mov     [rbp+57h+arg_18], rax
0x1800f1f50  test    rax, rax
0x1800f1f53  jnz     short loc_1800F1F78
0x1800f1f55  mov     rcx, [rbp+5Fh]; this
0x1800f1f59  mov     r14d, 8007000Eh
0x1800f1f5f  mov     r9d, r14d; char *
0x1800f1f62  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f1f69  mov     edx, 51Ah; void *
0x1800f1f6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1f73  jmp     loc_1800F22CF
0x1800f1f78  lea     rax, [rbp+57h+len]
0x1800f1f7c  mov     [rsp+100h+pcbData], rax; pcbData
0x1800f1f81  mov     [rsp+100h+pvData], rbx; pvData
0x1800f1f86  lea     rax, [rbp+57h+pdwType]
0x1800f1f8a  mov     [rsp+100h+ppv], rax; int
0x1800f1f8f  mov     r9d, r14d; dwFlags
0x1800f1f92  lea     r8, ValueName; "Results"
0x1800f1f99  mov     rdx, cs:?c_RegistryLastRunKey@@3PEAGEA; lpSubKey
0x1800f1fa0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f1fa7  call    cs:__imp_RegGetValueW
0x1800f1fae  nop     dword ptr [rax+rax+00h]
0x1800f1fb3  test    eax, eax
0x1800f1fb5  jz      short loc_1800F1FD8
0x1800f1fb7  mov     r8d, eax; int
0x1800f1fba  lea     rdx, aGettingResults_0; "Getting results registry value failed"
0x1800f1fc1  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800f1fc6  nop
0x1800f1fc7  lea     rcx, [rbp+57h+arg_18]
0x1800f1fcb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f1fd0  mov     r14d, r15d
0x1800f1fd3  jmp     loc_1800F22D9
0x1800f1fd8  or      eax, 0FFFFFFFFh
0x1800f1fdb  mov     [rbp+57h+arg_0], ax
0x1800f1fdf  mov     rcx, [rbp+57h+var_C0]
0x1800f1fe3  mov     rax, [rcx]
0x1800f1fe6  lea     r8, [rbp+57h+arg_0]
0x1800f1fea  mov     rdx, rbx
0x1800f1fed  mov     rax, [rax+208h]
0x1800f1ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1ff9  mov     ebx, eax
0x1800f1ffb  test    eax, eax
0x1800f1ffd  js      loc_1800F22E7
0x1800f2003  cmp     [rbp+57h+arg_0], r15w
0x1800f2008  jz      loc_1800F22E7
0x1800f200e  mov     r14, [rbp+57h+var_C0]
0x1800f2012  mov     rax, [r14]
0x1800f2015  mov     rbx, [rax+168h]
0x1800f201c  lea     rcx, [rbp+57h+var_98]
0x1800f2020  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f2025  lea     rdx, [rbp+57h+var_98]
0x1800f2029  mov     rcx, r14
0x1800f202c  mov     rax, rbx
0x1800f202f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2034  mov     r14d, eax
0x1800f2037  test    eax, eax
0x1800f2039  js      loc_1800F22BF
0x1800f203f  mov     rbx, [rbp+57h+var_98]
0x1800f2043  test    rbx, rbx
0x1800f2046  jz      loc_1800F22BF
0x1800f204c  mov     rax, [rbx]
0x1800f204f  mov     r14, [rax+68h]
0x1800f2053  lea     rcx, [rbp+57h+var_A0]
0x1800f2057  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f205c  lea     rdx, [rbp+57h+var_A0]
0x1800f2060  mov     rcx, rbx
0x1800f2063  mov     rax, r14
0x1800f2066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f206b  mov     r14d, eax
0x1800f206e  test    eax, eax
0x1800f2070  js      loc_1800F22B6
0x1800f2076  mov     rbx, [rbp+57h+var_A0]
0x1800f207a  test    rbx, rbx
0x1800f207d  jz      loc_1800F22B6
0x1800f2083  mov     rax, [rbx]
0x1800f2086  mov     r14, [rax+128h]
0x1800f208d  lea     rcx, [rbp+57h+var_A8]
0x1800f2091  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f2096  lea     r8, [rbp+57h+var_A8]
0x1800f209a  mov     rdx, rsi
0x1800f209d  mov     rcx, rbx
0x1800f20a0  mov     rax, r14
0x1800f20a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f20a8  mov     r14d, eax
0x1800f20ab  test    eax, eax
0x1800f20ad  jns     short loc_1800F20BB
0x1800f20af  lea     rdx, aResultXmlRootN; "Result XML root node get Collections el"...
0x1800f20b6  jmp     loc_1800F22C6
0x1800f20bb  mov     rsi, [rbp+57h+var_A8]
0x1800f20bf  mov     rax, [rsi]
0x1800f20c2  mov     rbx, [rax+128h]
0x1800f20c9  lea     rcx, [rbp+57h+var_B0]
0x1800f20cd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f20d2  lea     r8, [rbp+57h+var_B0]
0x1800f20d6  mov     rdx, rdi
0x1800f20d9  mov     rcx, rsi
0x1800f20dc  mov     rax, rbx
0x1800f20df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f20e4  mov     r14d, eax
0x1800f20e7  test    eax, eax
0x1800f20e9  jns     short loc_1800F20F7
0x1800f20eb  lea     rdx, aResultXmlGetSa; "Result XML get SasUrl element failed"
0x1800f20f2  jmp     loc_1800F22C6
0x1800f20f7  lea     rdx, aHresult; "HRESULT"
0x1800f20fe  lea     rcx, [rbp+57h+var_90]
0x1800f2102  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800f2107  nop
0x1800f2108  mov     rbx, [rbp+57h+var_90]
0x1800f210c  test    rbx, rbx
0x1800f210f  jnz     short loc_1800F213E
0x1800f2111  mov     rcx, [rbp+5Fh]; this
0x1800f2115  mov     r14d, 8007000Eh
0x1800f211b  mov     r9d, r14d; char *
0x1800f211e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800f2125  mov     edx, 557h; void *
0x1800f212a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f212f  nop
0x1800f2130  lea     rcx, [rbp+57h+var_90]
0x1800f2134  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f2139  jmp     loc_1800F22CF
0x1800f213e  lea     rdx, [rbp+57h+var_88]
0x1800f2142  lea     rcx, [rbp+57h+var_B0]
0x1800f2146  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x1800f214b  mov     r14d, eax
0x1800f214e  test    eax, eax
0x1800f2150  jns     short loc_1800F2163
0x1800f2152  lea     rdx, aResultXmlConve; "Result XML conversion to element failed"
0x1800f2159  mov     r8d, eax; int
0x1800f215c  call    ?Write@TelemetryWriter@@QEAAXPEBDJ@Z; TelemetryWriter::Write(char const *,long)
0x1800f2161  jmp     short loc_1800F2130
0x1800f2163  mov     rcx, [rbp+57h+var_88]
0x1800f2167  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800f216b  movaps  [rbp+57h+var_50], xmm0
0x1800f216f  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800f2174  movsd   [rbp+57h+var_40], xmm1
0x1800f2179  mov     rax, [rcx]
0x1800f217c  lea     r8, [rbp+57h+var_50]
0x1800f2180  mov     rdx, rbx
0x1800f2183  mov     rax, [rax+168h]
0x1800f218a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f218f  mov     r14d, eax
0x1800f2192  test    eax, eax
0x1800f2194  jns     short loc_1800F219F
0x1800f2196  lea     rdx, aResultXmlSetat; "Result XML setAttribute HRESULT failed"
0x1800f219d  jmp     short loc_1800F2159
0x1800f219f  mov     rdi, [rbp+57h+var_C0]
0x1800f21a3  mov     rax, [rdi]
0x1800f21a6  mov     rbx, [rax+110h]
0x1800f21ad  xor     edx, edx
0x1800f21af  lea     rcx, [rbp+57h+pbstr]
0x1800f21b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f21b8  lea     rdx, [rbp+57h+pbstr]
0x1800f21bc  mov     rcx, rdi
0x1800f21bf  mov     rax, rbx
0x1800f21c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f21c7  mov     r14d, eax
0x1800f21ca  test    eax, eax
0x1800f21cc  jns     short loc_1800F21D7
0x1800f21ce  lea     rdx, aResultXmlGetXm; "Result XML get_xml string failed"
0x1800f21d5  jmp     short loc_1800F2159
0x1800f21d7  mov     rcx, [rbp+57h+pbstr]; pbstr
0x1800f21db  call    cs:__imp_SysStringLen
0x1800f21e2  nop     dword ptr [rax+rax+00h]
0x1800f21e7  add     eax, eax
0x1800f21e9  mov     r10, [rbp+57h+pbstr]
0x1800f21ed  mov     dword ptr [rsp+100h+pvData], eax; cbData
0x1800f21f1  mov     [rsp+100h+ppv], r10; lpData
0x1800f21f6  mov     r9d, 1; dwType
0x1800f21fc  lea     r8, ValueName; "Results"
0x1800f2203  mov     rdx, cs:?c_RegistryLastRunKey@@3PEAGEA; lpSubKey
0x1800f220a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f2211  call    cs:__imp_RegSetKeyValueW
0x1800f2218  nop     dword ptr [rax+rax+00h]
0x1800f221d  test    eax, eax
0x1800f221f  jz      short loc_1800F2231
  ... truncated ...
```
