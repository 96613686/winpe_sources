# DeviceManageabilityCSP::Serializer::Serialize(void)

- ea: `0x18008c814`
- end: `0x18008cc53`
- name: `?Serialize@Serializer@DeviceManageabilityCSP@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ`
- size: `1087`
- prototype: `LPWSTR *__fastcall(__int64, LPWSTR *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800882f8`

## callees

- `0x180008de0`
- `0x18000921c`
- `0x18000caf4`
- `0x180019fd8`
- `0x18002031c`
- `0x180020424`
- `0x1800232e4`
- `0x180023874`
- `0x180083ca8`
- `0x180083d18`
- `0x180088254`
- `0x18008acfc`
- `0x18008b944`
- `0x18008be90`
- `0x18008bec0`
- `0x18008c814`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cbe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cbe0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008cb8d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008cbd0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008cb8d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008cbd0`
- `XmlLite!CreateXmlWriter` at `0x18008c8b0`
- `XmlLite!CreateXmlWriter` at `0x18008c8b0`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18008c908`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18008c908`

## pseudocode

```c
LPWSTR *__fastcall DeviceManageabilityCSP::Serializer::Serialize(__int64 a1, LPWSTR *a2)
{
  IUnknown *v4; // r14
  HRESULT v5; // eax
  const WCHAR *v6; // rax
  HRESULT v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r10
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r10
  int v18; // eax
  __int64 v19; // rcx
  _QWORD *v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // rdx
  const CHAR *v23; // rsi
  int v24; // edi
  __int64 cchWideChar; // rbx
  __int64 v26; // rcx
  signed int LastError; // eax
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  int lpWideCharStra; // [rsp+20h] [rbp-E0h]
  char v31; // [rsp+30h] [rbp-D0h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-C8h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+48h] [rbp-B8h]
  _QWORD v35[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPCCH lpMultiByteStr; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+68h] [rbp-98h]
  LPWSTR *v38; // [rsp+78h] [rbp-88h]
  IUnknown *v39; // [rsp+80h] [rbp-80h]
  _BYTE v40[8]; // [rsp+88h] [rbp-78h] BYREF
  void **p_ppvObject; // [rsp+90h] [rbp-70h]
  char v42; // [rsp+98h] [rbp-68h]
  _BYTE v43[16]; // [rsp+A0h] [rbp-60h] BYREF
  void *v44; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[32]; // [rsp+B8h] [rbp-48h] BYREF
  void *v46; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v47[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v48[112]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v38 = a2;
  v34 = 0;
  v4 = (IUnknown *)operator new(0x28u);
  ppOutput = v4;
  v4->lpVtbl = (struct IUnknownVtbl *)&DeviceManageabilityCSP::StringStream::`vftable';
  std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(&v4[1]);
  LODWORD(v4[4].lpVtbl) = 0;
  v39 = v4;
  ((void (__fastcall *)(IUnknown *))v4->lpVtbl->AddRef)(v4);
  ppvObject = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
  v5 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\serializer.cpp",
      (const char *)(unsigned int)v5,
      lpWideCharStr);
  ppOutput = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180157C70);
  v7 = CreateXmlWriterOutputWithEncodingName(v4, 0, v6, &ppOutput);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\serializer.cpp",
      (const char *)(unsigned int)v7,
      lpWideCharStr);
  v8 = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppOutput);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\serializer.cpp",
      (const char *)(unsigned int)v8,
      lpWideCharStr);
  v9 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\serializer.cpp",
      (const char *)(unsigned int)v9,
      lpWideCharStr);
  v10 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject + 208LL))(ppvObject, 0);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\serializer.cpp",
      (const char *)(unsigned int)v10,
      lpWideCharStr);
  p_ppvObject = &ppvObject;
  v42 = 1;
  DeviceManageabilityCSP::RootElement::RootElement(
    (DeviceManageabilityCSP::RootElement *)v48,
    (struct IXmlWriter *)ppvObject);
  v46 = ppvObject;
  std::wstring::wstring(v47, L"Capabilities");
  v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(v12 + 216))(v13, 0, v11, 0);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\capabilityParser.h",
      (const char *)(unsigned int)v14,
      lpWideCharStr);
  v44 = ppvObject;
  std::wstring::wstring(v45, L"CSPVersions");
  v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(v16 + 216))(v17, 0, v15, 0);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\capabilityParser.h",
      (const char *)(unsigned int)v18,
      lpWideCharStr);
  v31 = 0;
  v19 = *(_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(v19 + 8) )
  {
    v20 = (_QWORD *)std::vector<NetworkIdentifier>::begin(v19, v40);
    v22 = (_QWORD *)*v21;
    v35[0] = &ppvObject;
    v35[1] = &v31;
    std::for_each_std::_Tree_const_iterator_std::_Tree_val_std::_Tree_simple_types_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____________lambda_cc1afec9576a41777b969c08e17dd150___(
      v43,
      *v22,
      *v20,
      v35);
  }
  DeviceManageabilityCSP::VersionsElement::~VersionsElement((DeviceManageabilityCSP::VersionsElement *)&v44);
  DeviceManageabilityCSP::VersionsElement::~VersionsElement((DeviceManageabilityCSP::VersionsElement *)&v46);
  DeviceManageabilityCSP::RootElement::~RootElement((DeviceManageabilityCSP::RootElement *)v48);
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 112LL))(ppvObject);
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
  std::vector<unsigned char>::vector<unsigned char>(&lpMultiByteStr, &v4[1]);
  v23 = lpMultiByteStr;
  v24 = v37 - (_DWORD)lpMultiByteStr;
  cchWideChar = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, v37 - (_DWORD)lpMultiByteStr, 0, 0);
  std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(a2);
  v34 = 3;
  std::vector<unsigned char>::resize(v26, 2 * cchWideChar);
  if ( !MultiByteToWideChar(0xFDE9u, 0, v23, v24, *a2, cchWideChar) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\serializer.cpp",
        (const char *)(unsigned int)LastError,
        lpWideCharStra);
  }
  std::vector<unsigned char>::_Tidy(&lpMultiByteStr);
  ((void (__fastcall *)(IUnknown *))v4->lpVtbl->Release)(v4);
  return a2;
}

```

## disassembly

```asm
0x18008c814  push    rbp
0x18008c816  push    rbx
0x18008c817  push    rsi
0x18008c818  push    rdi
0x18008c819  push    r14
0x18008c81b  push    r15
0x18008c81d  lea     rbp, [rsp-88h]
0x18008c825  sub     rsp, 188h
0x18008c82c  mov     rax, cs:__security_cookie
0x18008c833  xor     rax, rsp
0x18008c836  mov     [rbp+0B0h+var_40], rax
0x18008c83a  mov     r15, rdx
0x18008c83d  mov     rbx, rcx
0x18008c840  mov     [rsp+1B0h+var_138], rdx
0x18008c845  mov     [rsp+1B0h+var_168], 0
0x18008c84d  mov     ecx, 28h ; '('; Size
0x18008c852  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008c857  mov     r14, rax
0x18008c85a  mov     [rsp+1B0h+ppOutput], rax
0x18008c85f  lea     rax, ??_7StringStream@DeviceManageabilityCSP@@6B@; const DeviceManageabilityCSP::StringStream::`vftable'
0x18008c866  mov     [r14], rax
0x18008c869  lea     rcx, [r14+8]
0x18008c86d  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x18008c872  mov     dword ptr [r14+20h], 0
0x18008c87a  mov     [rbp+0B0h+var_130], r14
0x18008c87e  mov     rax, [r14]
0x18008c881  mov     rcx, r14
0x18008c884  mov     rax, [rax+8]
0x18008c888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c88d  nop
0x18008c88e  mov     [rsp+1B0h+ppvObject], 0
0x18008c897  lea     rcx, [rsp+1B0h+ppvObject]
0x18008c89c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18008c8a1  xor     r8d, r8d; pMalloc
0x18008c8a4  lea     rdx, [rsp+1B0h+ppvObject]; ppvObject
0x18008c8a9  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18008c8b0  call    cs:__imp_CreateXmlWriter
0x18008c8b7  nop     dword ptr [rax+rax+00h]
0x18008c8bc  mov     rcx, [rbp+0B8h]; this
0x18008c8c3  test    eax, eax
0x18008c8c5  jns     short loc_18008C8DC
0x18008c8c7  mov     r9d, eax; char *
0x18008c8ca  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18008c8d1  mov     edx, 38h ; '8'; void *
0x18008c8d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008c8dc  mov     [rsp+1B0h+ppOutput], 0
0x18008c8e5  lea     rcx, [rsp+1B0h+ppOutput]
0x18008c8ea  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18008c8ef  lea     rcx, qword_180157C70
0x18008c8f6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008c8fb  mov     r8, rax; pwszEncodingName
0x18008c8fe  lea     r9, [rsp+1B0h+ppOutput]; ppOutput
0x18008c903  xor     edx, edx; pMalloc
0x18008c905  mov     rcx, r14; pOutputStream
0x18008c908  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18008c90f  nop     dword ptr [rax+rax+00h]
0x18008c914  mov     rcx, [rbp+0B8h]; this
0x18008c91b  test    eax, eax
0x18008c91d  jns     short loc_18008C934
0x18008c91f  mov     r9d, eax; char *
0x18008c922  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18008c929  mov     edx, 3Bh ; ';'; void *
0x18008c92e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008c934  mov     rcx, [rsp+1B0h+ppvObject]
0x18008c939  mov     rax, [rcx]
0x18008c93c  mov     rdx, [rsp+1B0h+ppOutput]
0x18008c941  mov     rax, [rax+18h]
0x18008c945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c94a  mov     rcx, [rbp+0B8h]; this
0x18008c951  test    eax, eax
0x18008c953  jns     short loc_18008C96A
0x18008c955  mov     r9d, eax; char *
0x18008c958  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18008c95f  mov     edx, 3Dh ; '='; void *
0x18008c964  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008c96a  mov     rcx, [rsp+1B0h+ppvObject]
0x18008c96f  mov     rax, [rcx]
0x18008c972  mov     esi, 1
0x18008c977  mov     r8d, esi
0x18008c97a  mov     edx, esi
0x18008c97c  mov     rax, [rax+28h]
0x18008c980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c985  mov     rcx, [rbp+0B8h]; this
0x18008c98c  test    eax, eax
0x18008c98e  jns     short loc_18008C9A3
0x18008c990  mov     r9d, eax; char *
0x18008c993  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18008c99a  lea     edx, [rsi+3Dh]; void *
0x18008c99d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008c9a3  mov     rcx, [rsp+1B0h+ppvObject]
0x18008c9a8  mov     rax, [rcx]
0x18008c9ab  xor     edx, edx
0x18008c9ad  mov     rax, [rax+0D0h]
0x18008c9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c9b9  mov     rcx, [rbp+0B8h]; this
0x18008c9c0  test    eax, eax
0x18008c9c2  jns     short loc_18008C9D9
0x18008c9c4  mov     r9d, eax; char *
0x18008c9c7  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18008c9ce  mov     edx, 40h ; '@'; void *
0x18008c9d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008c9d9  lea     rax, [rsp+1B0h+ppvObject]
0x18008c9de  mov     [rbp+0B0h+var_120], rax
0x18008c9e2  mov     [rbp+0B0h+var_118], sil
0x18008c9e6  mov     rdx, [rsp+1B0h+ppvObject]; struct IXmlWriter *
0x18008c9eb  lea     rcx, [rbp+0B0h+var_B0]; this
0x18008c9ef  call    ??0RootElement@DeviceManageabilityCSP@@QEAA@PEAUIXmlWriter@@@Z; DeviceManageabilityCSP::RootElement::RootElement(IXmlWriter *)
0x18008c9f4  nop
0x18008c9f5  mov     rax, [rsp+1B0h+ppvObject]
0x18008c9fa  mov     [rbp+0B0h+var_D8], rax
0x18008c9fe  lea     rdx, aCapabilities; "Capabilities"
0x18008ca05  lea     rcx, [rbp+0B0h+var_D0]
0x18008ca09  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008ca0e  nop
0x18008ca0f  mov     r10, [rbp+0B0h+var_D8]
0x18008ca13  mov     rdx, [r10]
0x18008ca16  lea     rcx, [rbp+0B0h+var_D0]
0x18008ca1a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008ca1f  mov     r8, rax
0x18008ca22  mov     rax, [rdx+0D8h]
0x18008ca29  xor     r9d, r9d
0x18008ca2c  xor     edx, edx
0x18008ca2e  mov     rcx, r10
0x18008ca31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ca36  mov     rcx, [rbp+0B8h]; this
0x18008ca3d  test    eax, eax
0x18008ca3f  jns     short loc_18008CA56
0x18008ca41  mov     r9d, eax; char *
0x18008ca44  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18008ca4b  mov     edx, 30h ; '0'; void *
0x18008ca50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008ca56  mov     rax, [rsp+1B0h+ppvObject]
0x18008ca5b  mov     [rbp+0B0h+var_100], rax
0x18008ca5f  lea     rdx, aCspversions; "CSPVersions"
0x18008ca66  lea     rcx, [rbp+0B0h+var_F8]
0x18008ca6a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008ca6f  nop
0x18008ca70  mov     r10, [rbp+0B0h+var_100]
0x18008ca74  mov     rdx, [r10]
0x18008ca77  lea     rcx, [rbp+0B0h+var_F8]
0x18008ca7b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008ca80  mov     r8, rax
0x18008ca83  mov     rax, [rdx+0D8h]
0x18008ca8a  xor     r9d, r9d
0x18008ca8d  xor     edx, edx
0x18008ca8f  mov     rcx, r10
0x18008ca92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ca97  mov     rcx, [rbp+0B8h]; this
0x18008ca9e  test    eax, eax
0x18008caa0  jns     short loc_18008CAB7
0x18008caa2  mov     r9d, eax; char *
0x18008caa5  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18008caac  mov     edx, 45h ; 'E'; void *
0x18008cab1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008cab7  mov     [rsp+1B0h+var_180], 0
0x18008cabc  mov     rcx, [rbx+8]
0x18008cac0  cmp     qword ptr [rcx+8], 0
0x18008cac5  jz      short loc_18008CAFC
0x18008cac7  lea     rdx, [rbp+0B0h+var_128]
0x18008cacb  call    ?begin@?$vector@VNetworkIdentifier@@V?$allocator@VNetworkIdentifier@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VNetworkIdentifier@@@std@@@std@@@2@XZ; std::vector<NetworkIdentifier>::begin(void)
0x18008cad0  mov     rdx, [rcx]
0x18008cad3  lea     rcx, [rsp+1B0h+ppvObject]
0x18008cad8  mov     [rsp+1B0h+var_160], rcx
0x18008cadd  lea     rcx, [rsp+1B0h+var_180]
0x18008cae2  mov     [rsp+1B0h+var_158], rcx
0x18008cae7  lea     r9, [rsp+1B0h+var_160]
0x18008caec  mov     r8, [rax]
0x18008caef  mov     rdx, [rdx]
0x18008caf2  lea     rcx, [rbp+0B0h+var_110]
0x18008caf6  call    std__for_each_std___Tree_const_iterator_std___Tree_val_std___Tree_simple_types_std__pair_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____const__std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____________lambda_cc1afec9576a41777b969c08e17dd150___
0x18008cafb  nop
0x18008cafc  lea     rcx, [rbp+0B0h+var_100]; this
0x18008cb00  call    ??1VersionsElement@DeviceManageabilityCSP@@QEAA@XZ; DeviceManageabilityCSP::VersionsElement::~VersionsElement(void)
0x18008cb05  nop
0x18008cb06  lea     rcx, [rbp+0B0h+var_D8]; this
0x18008cb0a  call    ??1VersionsElement@DeviceManageabilityCSP@@QEAA@XZ; DeviceManageabilityCSP::VersionsElement::~VersionsElement(void)
0x18008cb0f  nop
0x18008cb10  lea     rcx, [rbp+0B0h+var_B0]; this
0x18008cb14  call    ??1RootElement@DeviceManageabilityCSP@@QEAA@XZ; DeviceManageabilityCSP::RootElement::~RootElement(void)
0x18008cb19  nop
0x18008cb1a  mov     rcx, [rsp+1B0h+ppvObject]
0x18008cb1f  mov     rax, [rcx]
0x18008cb22  mov     rax, [rax+70h]
0x18008cb26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cb2b  mov     rcx, [rsp+1B0h+ppvObject]
0x18008cb30  mov     rax, [rcx]
0x18008cb33  mov     rax, [rax+0F8h]
0x18008cb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cb3f  nop
0x18008cb40  lea     rcx, [rsp+1B0h+ppOutput]
0x18008cb45  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18008cb4a  nop
0x18008cb4b  lea     rcx, [rsp+1B0h+ppvObject]
0x18008cb50  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18008cb55  lea     rdx, [r14+8]
0x18008cb59  lea     rcx, [rsp+1B0h+lpMultiByteStr]
0x18008cb5e  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18008cb63  nop
0x18008cb64  mov     rsi, [rsp+1B0h+lpMultiByteStr]
0x18008cb69  mov     edi, [rsp+1B0h+var_148]
0x18008cb6d  sub     edi, esi
0x18008cb6f  mov     [rsp+1B0h+cchWideChar], 0; cchWideChar
0x18008cb77  mov     [rsp+1B0h+lpWideCharStr], 0; lpWideCharStr
0x18008cb80  mov     r9d, edi; cbMultiByte
0x18008cb83  mov     r8, rsi; lpMultiByteStr
0x18008cb86  xor     edx, edx; dwFlags
0x18008cb88  mov     ecx, 0FDE9h; CodePage
0x18008cb8d  call    cs:__imp_MultiByteToWideChar
0x18008cb94  nop     dword ptr [rax+rax+00h]
0x18008cb99  movsxd  rbx, eax
0x18008cb9c  mov     rcx, r15
0x18008cb9f  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x18008cba4  mov     [rsp+1B0h+var_168], 3
0x18008cbac  mov     rdx, rbx
0x18008cbaf  add     rdx, rdx
0x18008cbb2  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18008cbb7  mov     [rsp+1B0h+cchWideChar], ebx; cchWideChar
0x18008cbbb  mov     rax, [r15]
0x18008cbbe  mov     [rsp+1B0h+lpWideCharStr], rax; int
0x18008cbc3  mov     r9d, edi; cbMultiByte
0x18008cbc6  mov     r8, rsi; lpMultiByteStr
0x18008cbc9  xor     edx, edx; dwFlags
0x18008cbcb  mov     ecx, 0FDE9h; CodePage
0x18008cbd0  call    cs:__imp_MultiByteToWideChar
0x18008cbd7  nop     dword ptr [rax+rax+00h]
0x18008cbdc  test    eax, eax
0x18008cbde  jnz     short loc_18008CC18
0x18008cbe0  call    cs:__imp_GetLastError
0x18008cbe7  nop     dword ptr [rax+rax+00h]
0x18008cbec  test    eax, eax
0x18008cbee  jle     short loc_18008CBF8
0x18008cbf0  movzx   eax, ax
0x18008cbf3  or      eax, 80070000h
0x18008cbf8  mov     rcx, [rbp+0B8h]; this
0x18008cbff  test    eax, eax
0x18008cc01  jns     short loc_18008CC18
0x18008cc03  mov     r9d, eax; char *
0x18008cc06  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18008cc0d  mov     edx, 60h ; '`'; void *
0x18008cc12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008cc18  lea     rcx, [rsp+1B0h+lpMultiByteStr]
0x18008cc1d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008cc22  nop
0x18008cc23  mov     rcx, [r14]
0x18008cc26  mov     rax, [rcx+10h]
0x18008cc2a  mov     rcx, r14
0x18008cc2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc32  nop
0x18008cc33  mov     rax, r15
0x18008cc36  mov     rcx, [rbp+0B0h+var_40]
0x18008cc3a  xor     rcx, rsp; StackCookie
0x18008cc3d  call    __security_check_cookie
0x18008cc42  add     rsp, 188h
0x18008cc49  pop     r15
0x18008cc4b  pop     r14
0x18008cc4d  pop     rdi
0x18008cc4e  pop     rsi
0x18008cc4f  pop     rbx
0x18008cc50  pop     rbp
0x18008cc51  retn
```
