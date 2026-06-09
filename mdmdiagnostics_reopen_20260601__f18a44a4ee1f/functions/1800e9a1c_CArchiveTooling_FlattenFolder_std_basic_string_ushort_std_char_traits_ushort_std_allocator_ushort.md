# CArchiveTooling::FlattenFolder(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800e9a1c`
- end: `0x1800ea27a`
- name: `?FlattenFolder@CArchiveTooling@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `2142`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f2b84`

## callees

- `0x180019080`
- `0x1800e6838`
- `0x1800e688c`
- `0x1800e68b0`
- `0x1800e7c78`
- `0x1800e7d84`
- `0x1800e8084`
- `0x1800e91f0`
- `0x1800e9a1c`
- `0x1800ed46c`
- `0x1800ef868`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00ac`
- `0x1800f00e4`
- `0x1800f1278`
- `0x1800f1b68`
- `0x18011a1f4`
- `0x18011a270`
- `0x18011d160`
- `0x18011e340`
- `0x18011e7a4`
- `0x180193010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800e9f9f`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800e9f9f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e9b8f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e9b8f`
- `OLEAUT32!__imp_VariantInit` at `0x1800e9f58`
- `OLEAUT32!__imp_VariantInit` at `0x1800e9f58`
- `OLEAUT32!__imp_VariantClear` at `0x1800e9b77`
- `OLEAUT32!__imp_VariantClear` at `0x1800e9bf9`
- `OLEAUT32!__imp_VariantClear` at `0x1800e9fb2`
- `OLEAUT32!__imp_VariantClear` at `0x1800e9b77`
- `OLEAUT32!__imp_VariantClear` at `0x1800e9bf9`
- `OLEAUT32!__imp_VariantClear` at `0x1800e9fb2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e9af5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e9af5`

## string_xrefs

- `0x1800e9b44`: `results.xml`
- `0x1800e9b11`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800e9eea`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800e9f3a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800e9f88`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\archivetooling.cpp`
- `0x1800ea213`: `FlattenFolder: Unable to create HRESULT string. Folder will not be flattened.`
- `0x1800e9c09`: `FlattenFolder: Error loading results.xml from: `
- `0x1800e9c77`: `FlattenFolder: Error getting root element in results.xml from `
- `0x1800e9ce2`: `FlattenFolder: Error getting first child element in results.xml from `
- `0x1800e9d73`: `FlattenFolder: Error selecting Collection child nodes in results.xml from `
- `0x1800ea1eb`: `FlattenFolder: Results.xml in `
- `0x1800ea0bd`: `FlattenFolder: Folder flattening aborted due to invalid XML in results.xml. Error parsing XML document in results.xml from `
- `0x1800ea0b4`: `FlattenFolder: Folder flattening aborted due to an error iterating node names in results.xml. Error getting node name in results.xml from `
- `0x1800ea051`: `FlattenFolder: Folder flattening aborted due to an error iterating node values in results.xml. Error getting node value in results.xml from `

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall CArchiveTooling::FlattenFolder(__int64 a1)
{
  __int64 v2; // rbx
  int v3; // r12d
  const unsigned __int16 *v4; // rax
  TelemetryWriter *v5; // rcx
  int v6; // edi
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // r13d
  HRESULT v10; // eax
  LPVOID v11; // rsi
  __int64 v12; // r15
  const OLECHAR *v13; // rdi
  const unsigned __int16 *v14; // rax
  TelemetryWriter *v15; // rcx
  __int64 v16; // rax
  const unsigned __int16 *v17; // rax
  TelemetryWriter *v18; // rcx
  __int64 v19; // rax
  const unsigned __int16 *v20; // rax
  TelemetryWriter *v21; // rcx
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, __int64, __int64 **); // rdi
  __int64 v24; // rax
  const wchar_t *v25; // rdx
  const unsigned __int16 *v26; // rax
  TelemetryWriter *v27; // rcx
  int v28; // ecx
  unsigned int i; // r15d
  __int64 v30; // rax
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, __int64 *); // rdi
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, __int64 *); // rdi
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD **); // rsi
  _QWORD *v37; // rdx
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  int v41; // eax
  int v42; // edi
  int v43; // eax
  char v44; // al
  int v45; // ecx
  const wchar_t *v46; // rdx
  const unsigned __int16 *v47; // rax
  TelemetryWriter *v48; // rcx
  const unsigned __int16 *v49; // rax
  TelemetryWriter *v50; // rcx
  unsigned int v52; // ebx
  const unsigned __int16 *v53; // rax
  TelemetryWriter *v54; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v56; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v57; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v58; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v61[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v62; // [rsp+5Ch] [rbp-A4h] BYREF
  _QWORD *v63; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG *v64; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  __int64 v66; // [rsp+78h] [rbp-88h] BYREF
  __int64 v67; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v69; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v70[32]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v71; // [rsp+E8h] [rbp-18h]
  _BYTE v72[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v73[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v74[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v75[336]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v71 = a1;
  std::wstring::wstring(v72);
  wil::make_bstr_nothrow(&v67, L"HRESULT");
  v2 = v67;
  v3 = 0;
  if ( v67 )
  {
    if ( !*(_QWORD *)(a1 + 16) )
    {
      std::wstring::append(v72, L"FlattenFolder: OutputFolder cannot be empty. Folder will not be flattened.");
      v4 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      TelemetryWriter::Write(v5, v4);
      v6 = -2147418113;
LABEL_51:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v67);
      std::wstring::_Tidy_deallocate(v72);
      std::wstring::_Tidy_deallocate(a1);
      return (unsigned int)v6;
    }
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v8 = std::wstring::wstring(&v69, v7);
    FlattenOutputFolder::FlattenOutputFolder(v75, v8);
    v56 = 0;
    v9 = 1;
    v10 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &v56);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C8,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
        (const char *)(unsigned int)v10,
        ppv);
LABEL_50:
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v56);
      FlattenOutputFolder::~FlattenOutputFolder((FlattenOutputFolder *)v75);
      goto LABEL_51;
    }
    std::wstring::wstring(v73, a1);
    std::wstring::append(v73, L"\\");
    std::wstring::append(v73, L"results.xml");
    v61[0] = 0;
    v11 = v56;
    v12 = *(_QWORD *)v56;
    v13 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
    pvarg.vt = 0;
    VariantClear(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(v13);
    if ( !pvarg.llVal && v13 )
    {
      pvarg.vt = 10;
      pvarg.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v69 = pvarg;
    v6 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, _WORD *))(v12 + 464))(v11, &v69, v61);
    VariantClear(&pvarg);
    if ( v6 < 0 )
    {
      std::wstring::append(v72, L"FlattenFolder: Error loading results.xml from: ");
      std::wstring::append(v72, a1);
      std::wstring::append(v72, L". Folder flattening aborted. Error: ");
      v14 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      TelemetryWriter::Write(v15, v14, v6);
LABEL_49:
      std::wstring::_Tidy_deallocate(v73);
      goto LABEL_50;
    }
    v57 = 0;
    v16 = *(_QWORD *)v56;
    v57 = 0;
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 **))(v16 + 360))(v56, &v57);
    if ( v6 < 0 )
    {
      std::wstring::append(v72, L"FlattenFolder: Error getting root element in results.xml from ");
      std::wstring::append(v72, a1);
      std::wstring::append(v72, L". Folder flattening aborted. Error: ");
      v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      TelemetryWriter::Write(v18, v17, v6);
LABEL_48:
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v57);
      goto LABEL_49;
    }
    v59 = 0;
    v19 = *v57;
    v59 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 104))(v57, &v59);
    if ( v6 < 0 )
    {
      std::wstring::append(v72, L"FlattenFolder: Error getting first child element in results.xml from ");
      std::wstring::append(v72, a1);
      std::wstring::append(v72, L". Folder flattening aborted. Error: ");
      v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      TelemetryWriter::Write(v21, v20, v6);
LABEL_47:
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v59);
      goto LABEL_48;
    }
    std::wstring::wstring(v74, L"/Collection/*");
    v58 = 0;
    v22 = v59;
    v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v59 + 288LL);
    v58 = 0;
    v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v74);
    v6 = v23(v22, v24, &v58);
    if ( v6 < 0 )
    {
      std::wstring::append(v72, L"FlattenFolder: Error selecting Collection child nodes in results.xml from ");
      std::wstring::append(v72, a1);
      v25 = L".Folder flattening aborted.Error : ";
      goto LABEL_17;
    }
    v62 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v58 + 64))(v58, &v62);
    if ( v6 < 0 || (v28 = v62) == 0 )
    {
      std::wstring::append(v72, L"FlattenFolder: Results.xml in ");
      std::wstring::append(v72, a1);
      v25 = L" contains zero nodes. There are no folders to flatten. Folder flattening aborted. Error: ";
LABEL_17:
      std::wstring::append(v72, v25);
      v26 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      TelemetryWriter::Write(v27, v26, v6);
LABEL_46:
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v58);
      std::wstring::_Tidy_deallocate(v74);
      goto LABEL_47;
    }
    for ( i = 0; (int)i < v28; ++i )
    {
      v60 = 0;
      v30 = *v58;
      v60 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v30 + 56))(v58, i, &v60);
      if ( v6 < 0 )
      {
        std::wstring::append(
          v72,
          L"FlattenFolder: Folder flattening aborted due to invalid XML in results.xml. Error parsing XML document in results.xml from ");
        std::wstring::append(v72, a1);
        std::wstring::append(v72, L". Error: ");
        v49 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
        TelemetryWriter::Write(v50, v49, v6);
        goto LABEL_45;
      }
      v66 = 0;
      v65 = 0;
      v63 = 0;
      v31 = v60;
      v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 56LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v66,
        0);
      v6 = v32(v31, &v66);
      if ( v6 < 0 )
      {
        v46 = L"FlattenFolder: Folder flattening aborted due to an error iterating node names in results.xml. Error gettin"
               "g node name in results.xml from ";
LABEL_42:
        std::wstring::append(v72, v46);
        std::wstring::append(v72, a1);
        std::wstring::append(v72, L". Error: ");
        v47 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
        TelemetryWriter::Write(v48, v47, v6);
        wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v63);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v65);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
LABEL_45:
        wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v60);
        goto LABEL_46;
      }
      v33 = v60;
      v34 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 208LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v65,
        0);
      v6 = v34(v33, &v65);
      if ( v6 < 0 )
      {
        v46 = L"FlattenFolder: Folder flattening aborted due to an error iterating node values in results.xml. Error getti"
               "ng node value in results.xml from ";
        goto LABEL_42;
      }
      v35 = v60;
      v36 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v60 + 136LL);
      v37 = v63;
      v63 = 0;
      if ( v37 )
        (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
      v38 = v36(v35, &v63);
      if ( v38 >= 0 )
      {
        if ( v63 )
        {
          v64 = 0;
          v39 = *v63;
          v64 = 0;
          v40 = (*(__int64 (__fastcall **)(_QWORD *, __int64, VARIANTARG **))(v39 + 56))(v63, v2, &v64);
          if ( v40 >= 0 )
          {
            if ( v64 )
            {
              VariantInit(&pvarg);
              v41 = (*(__int64 (__fastcall **)(VARIANTARG *, VARIANTARG *))(*(_QWORD *)&v64->vt + 64LL))(v64, &pvarg);
              if ( v41 >= 0 )
                v3 = _o__wtol(pvarg.llVal);
              else
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x33C,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
                  (const char *)(unsigned int)v41,
                  ppv);
              VariantClear(&pvarg);
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x338,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
              (const char *)(unsigned int)v40,
              ppv);
          }
          wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v64);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x334,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\archivetooling.cpp",
          (const char *)(unsigned int)v38,
          ppv);
      }
      v64 = &v69;
      v42 = std::wstring::wstring(&v69, v65);
      v43 = std::wstring::wstring(v70, v66);
      v44 = FlattenOutputFolder::ProcessDirectiveNode((unsigned int)v75, v9, v43, v42, v3);
      v45 = v9 + 1;
      if ( v44 != 1 )
        v45 = v9;
      v9 = v45;
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v63);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v65);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v60);
      v28 = v62;
      v3 = 0;
    }
    v52 = FlattenOutputFolder::PerformFolderFlattening((FlattenOutputFolder *)v75);
    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v58);
    std::wstring::_Tidy_deallocate(v74);
    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v59);
    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v57);
    std::wstring::_Tidy_deallocate(v73);
    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v56);
    FlattenOutputFolder::~FlattenOutputFolder((FlattenOutputFolder *)v75);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v67);
    std::wstring::_Tidy_deallocate(v72);
    std::wstring::_Tidy_deallocate(a1);
    return v52;
  }
  else
  {
    std::wstring::append(v72, L"FlattenFolder: Unable to create HRESULT string. Folder will not be flattened.");
    v53 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
    TelemetryWriter::Write(v54, v53);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v67);
    std::wstring::_Tidy_deallocate(v72);
    std::wstring::_Tidy_deallocate(a1);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x1800e9a1c  push    rbp
0x1800e9a1e  push    rbx
0x1800e9a1f  push    rsi
0x1800e9a20  push    rdi
0x1800e9a21  push    r12
0x1800e9a23  push    r13
0x1800e9a25  push    r14
0x1800e9a27  push    r15
0x1800e9a29  lea     rbp, [rsp-1B8h]
0x1800e9a31  sub     rsp, 2B8h
0x1800e9a38  mov     rax, cs:__security_cookie
0x1800e9a3f  xor     rax, rsp
0x1800e9a42  mov     [rbp+1F0h+var_50], rax
0x1800e9a49  mov     r14, rcx
0x1800e9a4c  mov     [rbp+1F0h+var_208], rcx
0x1800e9a50  lea     rcx, [rbp+1F0h+var_200]
0x1800e9a54  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e9a59  nop
0x1800e9a5a  lea     rdx, aHresult; "HRESULT"
0x1800e9a61  lea     rcx, [rbp+1F0h+var_270]
0x1800e9a65  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800e9a6a  nop
0x1800e9a6b  mov     rbx, [rbp+1F0h+var_270]
0x1800e9a6f  xor     r12d, r12d
0x1800e9a72  test    rbx, rbx
0x1800e9a75  jz      loc_1800EA213
0x1800e9a7b  cmp     [r14+10h], r12
0x1800e9a7f  jnz     short loc_1800E9AAC
0x1800e9a81  lea     rdx, aFlattenfolderO; "FlattenFolder: OutputFolder cannot be e"...
0x1800e9a88  lea     rcx, [rbp+1F0h+var_200]
0x1800e9a8c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9a91  lea     rcx, [rbp+1F0h+var_200]
0x1800e9a95  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e9a9a  mov     rdx, rax; unsigned __int16 *
0x1800e9a9d  call    ?Write@TelemetryWriter@@QEAAXPEBG@Z; TelemetryWriter::Write(ushort const *)
0x1800e9aa2  mov     edi, 8000FFFFh
0x1800e9aa7  jmp     loc_1800EA153
0x1800e9aac  mov     rcx, r14
0x1800e9aaf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e9ab4  mov     rdx, rax
0x1800e9ab7  lea     rcx, [rbp+1F0h+var_250]
0x1800e9abb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e9ac0  mov     rdx, rax
0x1800e9ac3  lea     rcx, [rbp+1F0h+var_1A0]
0x1800e9ac7  call    ??0FlattenOutputFolder@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FlattenOutputFolder::FlattenOutputFolder(std::wstring)
0x1800e9acc  nop
0x1800e9acd  mov     [rsp+2F0h+var_2C0], r12
0x1800e9ad2  lea     rax, [rsp+2F0h+var_2C0]
0x1800e9ad7  mov     qword ptr [rsp+2F0h+ppv], rax; int
0x1800e9adc  lea     r9, IID_IXMLDOMDocument; riid
0x1800e9ae3  mov     r13d, 1
0x1800e9ae9  mov     r8d, r13d; dwClsContext
0x1800e9aec  xor     edx, edx; pUnkOuter
0x1800e9aee  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800e9af5  call    cs:__imp_CoCreateInstance
0x1800e9afc  nop     dword ptr [rax+rax+00h]
0x1800e9b01  mov     edi, eax
0x1800e9b03  test    eax, eax
0x1800e9b05  jns     short loc_1800E9B27
0x1800e9b07  mov     rcx, [rbp+1F8h]; this
0x1800e9b0e  mov     r9d, eax; char *
0x1800e9b11  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800e9b18  mov     edx, 2C8h; void *
0x1800e9b1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e9b22  jmp     loc_1800EA13E
0x1800e9b27  mov     rdx, r14
0x1800e9b2a  lea     rcx, [rbp+1F0h+var_1E0]
0x1800e9b2e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800e9b33  nop
0x1800e9b34  lea     rdx, psz; "\\"
0x1800e9b3b  lea     rcx, [rbp+1F0h+var_1E0]
0x1800e9b3f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9b44  lea     rdx, aResultsXml; "results.xml"
0x1800e9b4b  lea     rcx, [rbp+1F0h+var_1E0]
0x1800e9b4f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9b54  mov     [rsp+2F0h+var_298], r12w
0x1800e9b5a  mov     rsi, [rsp+2F0h+var_2C0]
0x1800e9b5f  mov     r15, [rsi]
0x1800e9b62  lea     rcx, [rbp+1F0h+var_1E0]
0x1800e9b66  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e9b6b  mov     rdi, rax
0x1800e9b6e  mov     word ptr [rbp+1F0h+pvarg], r12w
0x1800e9b73  lea     rcx, [rbp+1F0h+pvarg]; pvarg
0x1800e9b77  call    cs:__imp_VariantClear
0x1800e9b7e  nop     dword ptr [rax+rax+00h]
0x1800e9b83  mov     eax, 8
0x1800e9b88  mov     word ptr [rbp+1F0h+pvarg], ax
0x1800e9b8c  mov     rcx, rdi; psz
0x1800e9b8f  call    cs:__imp_SysAllocString
0x1800e9b96  nop     dword ptr [rax+rax+00h]
0x1800e9b9b  mov     dword ptr [rbp+1F0h+pvarg+8], eax
0x1800e9b9e  mov     rcx, rax
0x1800e9ba1  sar     rcx, 20h
0x1800e9ba5  mov     dword ptr [rbp+1F0h+pvarg+0Ch], ecx
0x1800e9ba8  test    rax, rax
0x1800e9bab  jnz     short loc_1800E9BC9
0x1800e9bad  test    rdi, rdi
0x1800e9bb0  jz      short loc_1800E9BC9
0x1800e9bb2  mov     eax, 0Ah
0x1800e9bb7  mov     word ptr [rbp+1F0h+pvarg], ax
0x1800e9bbb  mov     ecx, 8007000Eh; int
0x1800e9bc0  mov     dword ptr [rbp+1F0h+pvarg+8], ecx
0x1800e9bc3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800e9bc9  movups  xmm0, xmmword ptr [rbp+1F0h+pvarg]
0x1800e9bcd  movaps  [rbp+1F0h+var_250], xmm0
0x1800e9bd1  movsd   xmm1, qword ptr [rbp+1F0h+pvarg+10h]
0x1800e9bd6  movsd   [rbp+1F0h+var_240], xmm1
0x1800e9bdb  lea     r8, [rsp+2F0h+var_298]
0x1800e9be0  lea     rdx, [rbp+1F0h+var_250]
0x1800e9be4  mov     rcx, rsi
0x1800e9be7  mov     rax, [r15+1D0h]
0x1800e9bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9bf3  mov     edi, eax
0x1800e9bf5  lea     rcx, [rbp+1F0h+pvarg]; pvarg
0x1800e9bf9  call    cs:__imp_VariantClear
0x1800e9c00  nop     dword ptr [rax+rax+00h]
0x1800e9c05  test    edi, edi
0x1800e9c07  jns     short loc_1800E9C4E
0x1800e9c09  lea     rdx, aFlattenfolderE; "FlattenFolder: Error loading results.xm"...
0x1800e9c10  lea     rcx, [rbp+1F0h+var_200]
0x1800e9c14  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9c19  mov     rdx, r14
0x1800e9c1c  lea     rcx, [rbp+1F0h+var_200]
0x1800e9c20  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800e9c25  lea     rdx, aFolderFlatteni_0; ". Folder flattening aborted. Error: "
0x1800e9c2c  lea     rcx, [rbp+1F0h+var_200]
0x1800e9c30  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9c35  lea     rcx, [rbp+1F0h+var_200]
0x1800e9c39  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e9c3e  mov     rdx, rax; unsigned __int16 *
0x1800e9c41  mov     r8d, edi; int
0x1800e9c44  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x1800e9c49  jmp     loc_1800EA134
0x1800e9c4e  mov     [rsp+2F0h+var_2B8], r12
0x1800e9c53  mov     rcx, [rsp+2F0h+var_2C0]
0x1800e9c58  mov     rax, [rcx]
0x1800e9c5b  mov     [rsp+2F0h+var_2B8], r12
0x1800e9c60  lea     rdx, [rsp+2F0h+var_2B8]
0x1800e9c65  mov     rax, [rax+168h]
0x1800e9c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9c71  mov     edi, eax
0x1800e9c73  test    eax, eax
0x1800e9c75  jns     short loc_1800E9CBC
0x1800e9c77  lea     rdx, aFlattenfolderE_0; "FlattenFolder: Error getting root eleme"...
0x1800e9c7e  lea     rcx, [rbp+1F0h+var_200]
0x1800e9c82  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9c87  mov     rdx, r14
0x1800e9c8a  lea     rcx, [rbp+1F0h+var_200]
0x1800e9c8e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800e9c93  lea     rdx, aFolderFlatteni_0; ". Folder flattening aborted. Error: "
0x1800e9c9a  lea     rcx, [rbp+1F0h+var_200]
0x1800e9c9e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9ca3  lea     rcx, [rbp+1F0h+var_200]
0x1800e9ca7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e9cac  mov     rdx, rax; unsigned __int16 *
0x1800e9caf  mov     r8d, edi; int
0x1800e9cb2  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x1800e9cb7  jmp     loc_1800EA129
0x1800e9cbc  mov     [rsp+2F0h+var_2A8], r12
0x1800e9cc1  mov     rcx, [rsp+2F0h+var_2B8]
0x1800e9cc6  mov     rax, [rcx]
0x1800e9cc9  mov     [rsp+2F0h+var_2A8], r12
0x1800e9cce  lea     rdx, [rsp+2F0h+var_2A8]
0x1800e9cd3  mov     rax, [rax+68h]
0x1800e9cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9cdc  mov     edi, eax
0x1800e9cde  test    eax, eax
0x1800e9ce0  jns     short loc_1800E9D27
0x1800e9ce2  lea     rdx, aFlattenfolderE_2; "FlattenFolder: Error getting first chil"...
0x1800e9ce9  lea     rcx, [rbp+1F0h+var_200]
0x1800e9ced  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9cf2  mov     rdx, r14
0x1800e9cf5  lea     rcx, [rbp+1F0h+var_200]
0x1800e9cf9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800e9cfe  lea     rdx, aFolderFlatteni_0; ". Folder flattening aborted. Error: "
0x1800e9d05  lea     rcx, [rbp+1F0h+var_200]
0x1800e9d09  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9d0e  lea     rcx, [rbp+1F0h+var_200]
0x1800e9d12  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e9d17  mov     rdx, rax; unsigned __int16 *
0x1800e9d1a  mov     r8d, edi; int
0x1800e9d1d  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x1800e9d22  jmp     loc_1800EA11E
0x1800e9d27  lea     rdx, aCollection; "/Collection/*"
0x1800e9d2e  lea     rcx, [rbp+1F0h+var_1C0]
0x1800e9d32  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e9d37  nop
0x1800e9d38  mov     [rsp+2F0h+var_2B0], r12
0x1800e9d3d  mov     rsi, [rsp+2F0h+var_2A8]
0x1800e9d42  mov     rax, [rsi]
0x1800e9d45  mov     rdi, [rax+120h]
0x1800e9d4c  mov     [rsp+2F0h+var_2B0], r12
0x1800e9d51  lea     rcx, [rbp+1F0h+var_1C0]
0x1800e9d55  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e9d5a  mov     rdx, rax
0x1800e9d5d  lea     r8, [rsp+2F0h+var_2B0]
0x1800e9d62  mov     rcx, rsi
0x1800e9d65  mov     rax, rdi
0x1800e9d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9d6d  mov     edi, eax
0x1800e9d6f  test    eax, eax
0x1800e9d71  jns     short loc_1800E9DB8
0x1800e9d73  lea     rdx, aFlattenfolderE_1; "FlattenFolder: Error selecting Collecti"...
0x1800e9d7a  lea     rcx, [rbp+1F0h+var_200]
0x1800e9d7e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9d83  mov     rdx, r14
0x1800e9d86  lea     rcx, [rbp+1F0h+var_200]
0x1800e9d8a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800e9d8f  lea     rdx, aFolderFlatteni; ".Folder flattening aborted.Error : "
0x1800e9d96  lea     rcx, [rbp+1F0h+var_200]
0x1800e9d9a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800e9d9f  lea     rcx, [rbp+1F0h+var_200]
0x1800e9da3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e9da8  mov     rdx, rax; unsigned __int16 *
0x1800e9dab  mov     r8d, edi; int
0x1800e9dae  call    ?Write@TelemetryWriter@@QEAAXPEBGJ@Z; TelemetryWriter::Write(ushort const *,long)
0x1800e9db3  jmp     loc_1800EA109
0x1800e9db8  mov     [rsp+2F0h+var_294], r12d
0x1800e9dbd  mov     rcx, [rsp+2F0h+var_2B0]
0x1800e9dc2  mov     rax, [rcx]
0x1800e9dc5  lea     rdx, [rsp+2F0h+var_294]
0x1800e9dca  mov     rax, [rax+40h]
0x1800e9dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9dd3  mov     edi, eax
0x1800e9dd5  test    eax, eax
0x1800e9dd7  js      loc_1800EA1EB
0x1800e9ddd  mov     ecx, [rsp+2F0h+var_294]
0x1800e9de1  test    ecx, ecx
0x1800e9de3  jz      loc_1800EA1EB
0x1800e9de9  mov     r15d, r12d
0x1800e9dec  cmp     r15d, ecx
0x1800e9def  jge     loc_1800EA176
0x1800e9df5  mov     [rsp+2F0h+var_2A0], r12
0x1800e9dfa  mov     rcx, [rsp+2F0h+var_2B0]
0x1800e9dff  mov     rax, [rcx]
0x1800e9e02  mov     [rsp+2F0h+var_2A0], r12
0x1800e9e07  lea     r8, [rsp+2F0h+var_2A0]
0x1800e9e0c  mov     edx, r15d
0x1800e9e0f  mov     rax, [rax+38h]
0x1800e9e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9e18  mov     edi, eax
0x1800e9e1a  test    eax, eax
0x1800e9e1c  js      loc_1800EA0BD
0x1800e9e22  mov     [rsp+2F0h+var_278], r12
0x1800e9e27  mov     [rsp+2F0h+var_280], r12
0x1800e9e2c  mov     [rsp+2F0h+var_290], r12
0x1800e9e31  mov     rsi, [rsp+2F0h+var_2A0]
0x1800e9e36  mov     rax, [rsi]
0x1800e9e39  mov     rdi, [rax+38h]
0x1800e9e3d  xor     edx, edx
0x1800e9e3f  lea     rcx, [rsp+2F0h+var_278]
0x1800e9e44  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800e9e49  lea     rdx, [rsp+2F0h+var_278]
0x1800e9e4e  mov     rcx, rsi
0x1800e9e51  mov     rax, rdi
0x1800e9e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9e59  mov     edi, eax
0x1800e9e5b  test    eax, eax
0x1800e9e5d  js      loc_1800EA0B4
0x1800e9e63  mov     rsi, [rsp+2F0h+var_2A0]
0x1800e9e68  mov     rax, [rsi]
0x1800e9e6b  mov     rdi, [rax+0D0h]
0x1800e9e72  xor     edx, edx
0x1800e9e74  lea     rcx, [rsp+2F0h+var_280]
0x1800e9e79  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800e9e7e  lea     rdx, [rsp+2F0h+var_280]
0x1800e9e83  mov     rcx, rsi
0x1800e9e86  mov     rax, rdi
0x1800e9e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9e8e  mov     edi, eax
0x1800e9e90  test    eax, eax
0x1800e9e92  js      loc_1800EA051
0x1800e9e98  mov     rdi, [rsp+2F0h+var_2A0]
0x1800e9e9d  mov     rax, [rdi]
0x1800e9ea0  mov     rsi, [rax+88h]
0x1800e9ea7  mov     rdx, [rsp+2F0h+var_290]
0x1800e9eac  mov     [rsp+2F0h+var_290], 0
0x1800e9eb5  test    rdx, rdx
0x1800e9eb8  jz      short loc_1800E9ECA
0x1800e9eba  mov     rcx, [rdx]
0x1800e9ebd  mov     rax, [rcx+10h]
0x1800e9ec1  mov     rcx, rdx
0x1800e9ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9ec9  nop
0x1800e9eca  lea     rdx, [rsp+2F0h+var_290]
0x1800e9ecf  mov     rcx, rdi
0x1800e9ed2  mov     rax, rsi
0x1800e9ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9eda  mov     rcx, [rbp+1F8h]; this
0x1800e9ee1  xor     edi, edi
0x1800e9ee3  test    eax, eax
0x1800e9ee5  jns     short loc_1800E9F00
0x1800e9ee7  mov     r9d, eax; char *
0x1800e9eea  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1800e9ef1  mov     edx, 334h; void *
0x1800e9ef6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e9efb  jmp     loc_1800E9FC9
0x1800e9f00  mov     rcx, [rsp+2F0h+var_290]
0x1800e9f05  test    rcx, rcx
0x1800e9f08  jz      loc_1800E9FC9
  ... truncated ...
```
