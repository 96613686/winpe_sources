# MetaRefreshUrlFromWebResponse(char const *)

- ea: `0x1800453bc`
- end: `0x18004606f`
- name: `?MetaRefreshUrlFromWebResponse@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBD@Z`
- size: `3251`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037ac4`

## callees

- `0x18000e36c`
- `0x180021100`
- `0x1800212c8`
- `0x180027d10`
- `0x18002cd60`
- `0x18002e70c`
- `0x18003eca8`
- `0x1800442f8`
- `0x180044e34`
- `0x180044e8c`
- `0x1800453bc`
- `0x180046078`
- `0x1800461dc`
- `0x180046220`
- `0x180046278`
- `0x1800462e8`
- `0x180047240`
- `0x180047f6c`
- `0x180047f78`
- `0x18004f5f0`
- `0x18004f610`
- `0x18006e90c`
- `0x18006e9b0`
- `0x180070728`
- `0x180070780`
- `0x180070f3c`
- `0x180071264`
- `0x1800712bc`
- `0x1800713d4`
- `0x1800713f4`
- `0x180071ac0`
- `0x180075c98`
- `0x180075ec8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045a59`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045a59`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180045eab`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004600b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180045eab`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004600b`
- `OLEAUT32!__imp_SysFreeString` at `0x180045a17`
- `OLEAUT32!__imp_SysFreeString` at `0x180045a90`
- `OLEAUT32!__imp_SysFreeString` at `0x180045a17`
- `OLEAUT32!__imp_SysFreeString` at `0x180045a90`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180045451`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180045451`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180045eb5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180046015`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180045eb5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180046015`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004541a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004541a`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
_QWORD *__fastcall MetaRefreshUrlFromWebResponse(_QWORD *a1)
{
  SAFEARRAY *Vector; // rax
  const char *v3; // r9
  HRESULT v4; // eax
  __int64 v5; // rcx
  _QWORD *v6; // rax
  const char *v7; // r9
  __int64 (__fastcall ***v8)(_QWORD, GUID *, _QWORD *); // rbx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, __int64, _QWORD); // rsi
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD *); // rcx
  int v19; // eax
  int v20; // eax
  unsigned int i; // esi
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rbx
  int (__fastcall *v25)(__int64, BSTR *); // r12
  OLECHAR *v26; // r15
  __int64 v27; // r15
  int (__fastcall *v28)(__int64, BSTR *); // r12
  OLECHAR *v29; // rbx
  _QWORD *v30; // r9
  _QWORD *v31; // rcx
  int v32; // edx
  _QWORD *v33; // rcx
  __int128 v34; // xmm0
  __int64 v35; // rsi
  __int16 *v36; // rax
  __int16 *v37; // r8
  char *v38; // r9
  unsigned __int64 v39; // r11
  __int16 *v40; // rdx
  __int16 v41; // r9
  char *v42; // rax
  __int64 v43; // rdx
  unsigned __int64 v44; // rsi
  _QWORD *v45; // rax
  __int64 v46; // rbx
  char v47; // al
  char v48; // al
  int v50; // [rsp+20h] [rbp-1E8h]
  char v51[8]; // [rsp+30h] [rbp-1D8h] BYREF
  __int64 (__fastcall ***v52)(_QWORD, GUID *, _QWORD *); // [rsp+38h] [rbp-1D0h] BYREF
  __int128 v53; // [rsp+40h] [rbp-1C8h] BYREF
  _QWORD *v54; // [rsp+50h] [rbp-1B8h]
  _BYTE v55[16]; // [rsp+58h] [rbp-1B0h] BYREF
  SAFEARRAY **v56; // [rsp+68h] [rbp-1A0h]
  char v57; // [rsp+70h] [rbp-198h]
  void *ppvData; // [rsp+78h] [rbp-190h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-188h] BYREF
  __int64 (__fastcall ***v60)(_QWORD, GUID *, _QWORD *); // [rsp+88h] [rbp-180h] BYREF
  __int64 v61; // [rsp+90h] [rbp-178h] BYREF
  __int64 (__fastcall ***v62)(_QWORD, GUID *, _QWORD *); // [rsp+98h] [rbp-170h] BYREF
  __int64 (__fastcall ***v63)(_QWORD, GUID *, _QWORD *); // [rsp+A0h] [rbp-168h] BYREF
  __int64 (__fastcall ***v64)(_QWORD, GUID *, _QWORD *); // [rsp+A8h] [rbp-160h] BYREF
  int v65; // [rsp+B0h] [rbp-158h] BYREF
  __int64 *v66; // [rsp+B8h] [rbp-150h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-148h] BYREF
  __int64 v68; // [rsp+C8h] [rbp-140h] BYREF
  SAFEARRAY *v69; // [rsp+D0h] [rbp-138h] BYREF
  __int64 v70; // [rsp+D8h] [rbp-130h] BYREF
  __int64 v71; // [rsp+E0h] [rbp-128h] BYREF
  __int64 *v72; // [rsp+E8h] [rbp-120h] BYREF
  __int64 v73; // [rsp+F0h] [rbp-118h] BYREF
  __int64 v74; // [rsp+F8h] [rbp-110h] BYREF
  _QWORD v75[2]; // [rsp+100h] [rbp-108h] BYREF
  __int64 v76; // [rsp+110h] [rbp-F8h]
  unsigned __int64 v77; // [rsp+118h] [rbp-F0h]
  _QWORD v78[2]; // [rsp+120h] [rbp-E8h] BYREF
  __int64 v79; // [rsp+130h] [rbp-D8h]
  unsigned __int64 v80; // [rsp+138h] [rbp-D0h]
  __int64 v81; // [rsp+140h] [rbp-C8h] BYREF
  char v82; // [rsp+148h] [rbp-C0h]
  __int128 v83; // [rsp+150h] [rbp-B8h] BYREF
  __int64 v84; // [rsp+160h] [rbp-A8h]
  __int64 v85; // [rsp+168h] [rbp-A0h]
  __int64 v86; // [rsp+170h] [rbp-98h]
  char v87; // [rsp+178h] [rbp-90h]
  __int128 v88; // [rsp+180h] [rbp-88h]
  char v89; // [rsp+190h] [rbp-78h]
  __int64 v90; // [rsp+198h] [rbp-70h]
  __int64 v91; // [rsp+1A0h] [rbp-68h]
  char v92; // [rsp+1A8h] [rbp-60h]
  _OWORD v93[2]; // [rsp+1B0h] [rbp-58h] BYREF
  __int64 v94; // [rsp+1D0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v54 = a1;
  v70 = 0;
  BstrFromMultiByteString(&v70);
  Vector = SafeArrayCreateVector(0xCu, 0, 1u);
  v69 = Vector;
  if ( !Vector )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      v3);
  ppvData = 0;
  v4 = SafeArrayAccessData(Vector, &ppvData);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)(unsigned int)v4,
      v50);
  v56 = &v69;
  v57 = 1;
  *(_WORD *)ppvData = 8;
  v5 = v70;
  v70 = 0;
  *((_QWORD *)ppvData + 1) = v5;
  wil::CoInitializeEx(v51);
  v60 = 0;
  wil::CoCreateInstance<IHTMLDocument2,wil::err_exception_policy>((LPVOID *)&v60);
  v6 = Microsoft::WRL::Details::Make<NcsiClientSite,>(&v61);
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))*v6;
  *v6 = 0;
  v52 = v8;
  v9 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( !v8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      v7);
  v68 = 0;
  wil::com_ptr_t<NcsiClientSite,wil::err_exception_policy>::query<IOleClientSite>(&v52, &v68);
  if ( !v68 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)0x8007000DLL,
      v50);
  v74 = 0;
  wil::com_ptr_t<IHTMLDocument2,wil::err_exception_policy>::query<IOleObject>(&v60, &v74);
  if ( !v74 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)0x8007000DLL,
      v50);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v74 + 24LL))(v74, v68);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)(unsigned int)v10,
      v50);
  v73 = 0;
  wil::com_ptr_t<IHTMLDocument2,wil::err_exception_policy>::query<IOleControl>(&v60, &v73);
  if ( !v73 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)0x8007000DLL,
      v50);
  v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v73 + 40LL))(v73, 4294961784LL);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)(unsigned int)v11,
      v50);
  v12 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), SAFEARRAY *))(*v60)[59])(v60, v69);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)(unsigned int)v12,
      v50);
  v13 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v60)[62])(v60);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)(unsigned int)v13,
      v50);
  v72 = 0;
  wil::com_ptr_t<IHTMLDocument2,wil::err_exception_policy>::query<IHTMLDocument7>(&v60, &v72);
  if ( !v72 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)0x8007000DLL,
      v50);
  v64 = 0;
  v14 = *v72;
  v64 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(v14 + 880))(
          v72,
          &v64);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)(unsigned int)v15,
      v50);
  if ( !v64 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)0x8007000DLL,
      v50);
  v67 = 0;
  wil::com_ptr_t<IHTMLElement,wil::err_exception_policy>::query<IHTMLElement2>(&v64, &v67);
  if ( !v67 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)0x8007000DLL,
      v50);
  v62 = 0;
  v71 = 0;
  wil::make_bstr(&v71);
  v16 = v67;
  v17 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v67 + 832LL);
  v18 = v62;
  v62 = 0;
  if ( v18 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v18)[2])(v18);
  v19 = v17(v16, v71, &v62);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)(unsigned int)v19,
      v50);
  if ( !v62 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)0x8007000DLL,
      v50);
  v65 = 0;
  v66 = 0;
  wil::com_ptr_t<IHTMLElementCollection,wil::err_exception_policy>::query<IHTMLElementCollection4>(&v62, &v66);
  if ( !v66 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)0x8007000DLL,
      v50);
  v20 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v66 + 56))(v66, &v65);
  if ( v20 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
      (const char *)(unsigned int)v20,
      v50);
  for ( i = 0; ; ++i )
  {
    if ( (int)i >= v65 )
    {
      *a1 = 0;
      wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v66);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v71);
      wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v62);
      wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v67);
      wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v64);
      wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v72);
      wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v73);
      wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v74);
      wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v68);
      wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v52);
      wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v60);
      v48 = v51[0];
      v51[0] = 0;
      if ( v48 )
        CoUninitialize();
      goto LABEL_95;
    }
    v63 = 0;
    v22 = *v66;
    v63 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v22 + 64))(v66, i, &v63);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
        (const char *)(unsigned int)v23,
        v50);
    if ( !v63 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
        (const char *)0x8007000DLL,
        v50);
    bstrString = 0;
    v61 = 0;
    wil::com_ptr_t<IHTMLElement2,wil::err_exception_policy>::query<IHTMLMetaElement>(&v63, &v61);
    v24 = v61;
    if ( !v61 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\htmlutil.cpp",
        (const char *)0x8007000DLL,
        v50);
    v25 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v61 + 64LL);
    v26 = bstrString;
    if ( bstrString )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v55);
      SysFreeString(v26);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
    }
    bstrString = 0;
    if ( v25(v24, &bstrString) >= 0 && !(unsigned int)_o__wcsicmp(bstrString, L"refresh") )
    {
      v27 = v61;
      v28 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v61 + 80LL);
      v29 = bstrString;
      if ( bstrString )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v53);
        SysFreeString(v29);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v53);
      }
      bstrString = 0;
      if ( v28(v27, &bstrString) >= 0 )
        break;
    }
LABEL_92:
    wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v61);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
    wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v63);
  }
  memset(v93, 0, sizeof(v93));
  v94 = 0;
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(v93);
  std::wstring::wstring(v78, bstrString);
  memset_0(&v81, 0, 0x70u);
  v81 = 0;
  v82 = 0;
  std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(&v83);
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  if ( v80 <= 7 )
  {
    v30 = v78;
    v31 = v78;
  }
  else
  {
    v30 = (_QWORD *)v78[0];
    LODWORD(v31) = v78[0];
  }
  v32 = (_DWORD)v31 + 2 * v79;
  v33 = v78;
  if ( v80 > 7 )
    LODWORD(v33) = v78[0];
  std::_Regex_search2<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>,unsigned short,std::regex_traits<unsigned short>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
    (_DWORD)v33,
    v32,
    (unsigned int)&v81,
    (unsigned int)v93,
    v50,
    (__int64)v30);
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v83 + 1) - v83) >> 3) <= 2 )
  {
    if ( (_QWORD)v83 )
    {
      std::_Deallocate<16>((void *)v83, 8 * ((v84 - (__int64)v83) >> 3));
      v83 = 0;
      v84 = 0;
    }
    std::wstring::_Tidy_deallocate(v78);
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v93);
    goto LABEL_92;
  }
  if ( *(_BYTE *)(v83 + 64) )
    v34 = *(_OWORD *)(v83 + 48);
  else
    v34 = 0;
  v53 = v34;
  std::wstring::wstring(v75, v34, *((_QWORD *)&v34 + 1));
  v35 = *(_QWORD *)std::wstring::end(v75, &v53);
  v36 = *(__int16 **)std::wstring::end(v75, v55);
  v37 = (__int16 *)v75;
  v38 = (char *)v75[0];
  v39 = v77;
  if ( v77 > 7 )
    v37 = (__int16 *)v75[0];
  while ( v37 != v36 )
  {
    if ( ((*v37 - 9) & 0xFFFA) == 0 && *v37 != 14 )
    {
      if ( v37 != v36 )
      {
        v40 = v37 + 1;
        if ( v37 + 1 != v36 )
        {
          do
          {
            v41 = *v40;
            if ( ((*v40 - 9) & 0xFFFA) != 0 || v41 == 14 )
              *v37++ = v41;
            ++v40;
          }
          while ( v40 != v36 );
          v39 = v77;
          v38 = (char *)v75[0];
        }
      }
      break;
    }
    ++v37;
  }
  v42 = (char *)v75;
  if ( v39 > 7 )
    v42 = v38;
  v43 = ((char *)v37 - v42) >> 1;
  v44 = (v35 - (__int64)v37) >> 1;
  if ( v76 - v43 < v44 )
    v44 = v76 - v43;
  v45 = v75;
  if ( v39 > 7 )
    v45 = v38;
  v46 = v76 - v44;
  memmove_0((char *)v45 + 2 * v43, (char *)v45 + 2 * v43 + 2 * v44, 2 * (v76 - v44 - v43) + 2);
  v76 = v46;
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(a1);
  std::wstring::_Tidy_deallocate(v75);
  if ( (_QWORD)v83 )
  {
    std::_Deallocate<16>((void *)v83, 8 * ((v84 - (__int64)v83) >> 3));
    v83 = 0;
    v84 = 0;
  }
  std::wstring::_Tidy_deallocate(v78);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v93);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v61);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v63);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v66);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v71);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v62);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v67);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v64);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v72);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v73);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v74);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v68);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v52);
  wil::com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>::~com_ptr_t<IHTMLMetaElement,wil::err_exception_policy>(&v60);
  v47 = v51[0];
  v51[0] = 0;
  if ( v47 )
    CoUninitialize();
LABEL_95:
  SafeArrayUnaccessData(v69);
  wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>(&v69);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v70);
  return a1;
}

```

## disassembly

```asm
0x1800453bc  mov     r11, rsp
0x1800453bf  mov     [r11+18h], rbx
0x1800453c3  mov     [r11+20h], rsi
0x1800453c7  push    rdi
0x1800453c8  push    r12
0x1800453ca  push    r13
0x1800453cc  push    r14
0x1800453ce  push    r15
0x1800453d0  sub     rsp, 1E0h
0x1800453d7  mov     rax, cs:__security_cookie
0x1800453de  xor     rax, rsp
0x1800453e1  mov     [rsp+208h+var_30], rax
0x1800453e9  mov     r14, rcx
0x1800453ec  mov     [rsp+208h+var_1B8], rcx
0x1800453f1  xor     r13d, r13d
0x1800453f4  mov     [r11-130h], r13
0x1800453fb  lea     rcx, [r11-130h]
0x180045402  call    ?BstrFromMultiByteString@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBD@Z; BstrFromMultiByteString(char const *)
0x180045407  nop
0x180045408  mov     [rsp+208h+var_138], r13
0x180045410  lea     ecx, [r13+0Ch]; vt
0x180045414  xor     edx, edx; lLbound
0x180045416  lea     r8d, [r13+1]; cElements
0x18004541a  call    cs:__imp_SafeArrayCreateVector
0x180045420  mov     [rsp+208h+var_138], rax
0x180045428  mov     rcx, [rsp+208h]; this
0x180045430  test    rax, rax
0x180045433  jnz     short loc_180045444
0x180045435  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x18004543c  lea     edx, [rax+67h]; void *
0x18004543f  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180045444  mov     [rsp+208h+ppvData], r13
0x180045449  lea     rdx, [rsp+208h+ppvData]; ppvData
0x18004544e  mov     rcx, rax; psa
0x180045451  call    cs:__imp_SafeArrayAccessData
0x180045457  mov     rcx, [rsp+208h]; this
0x18004545f  test    eax, eax
0x180045461  jns     short loc_180045477
0x180045463  mov     r9d, eax; char *
0x180045466  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x18004546d  mov     edx, 6Ah ; 'j'; void *
0x180045472  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180045477  lea     rdi, [rsp+208h+var_138]
0x18004547f  mov     [rsp+208h+var_1A0], rdi
0x180045484  mov     [rsp+208h+var_198], 1
0x180045489  mov     rax, [rsp+208h+ppvData]
0x18004548e  mov     word ptr [rax], 8
0x180045493  mov     rcx, [rsp+208h+var_130]
0x18004549b  mov     [rsp+208h+var_130], r13
0x1800454a3  mov     rax, [rsp+208h+ppvData]
0x1800454a8  mov     [rax+8], rcx
0x1800454ac  lea     rcx, [rsp+208h+var_1D8]
0x1800454b1  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x1800454b6  nop
0x1800454b7  mov     [rsp+208h+var_180], r13
0x1800454bf  lea     rcx, [rsp+208h+var_180]
0x1800454c7  call    ??$CoCreateInstance@UIHTMLDocument2@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIHTMLDocument2@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IHTMLDocument2,wil::err_exception_policy>(_GUID const &,ulong)
0x1800454cc  nop
0x1800454cd  lea     rcx, [rsp+208h+var_178]
0x1800454d5  call    ??$Make@VNcsiClientSite@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VNcsiClientSite@@@12@XZ; Microsoft::WRL::Details::Make<NcsiClientSite,>(void)
0x1800454da  mov     rbx, [rax]
0x1800454dd  mov     [rax], r13
0x1800454e0  mov     [rsp+208h+var_1D0], rbx
0x1800454e5  mov     rcx, [rsp+208h+var_178]
0x1800454ed  test    rcx, rcx
0x1800454f0  jz      short loc_180045507
0x1800454f2  mov     [rsp+208h+var_178], r13
0x1800454fa  mov     rax, [rcx]
0x1800454fd  mov     rax, [rax+10h]
0x180045501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045506  nop
0x180045507  mov     rcx, [rsp+208h]; this
0x18004550f  test    rbx, rbx
0x180045512  jnz     short loc_180045523
0x180045514  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x18004551b  lea     edx, [rbx+78h]; void *
0x18004551e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180045523  mov     [rsp+208h+var_140], r13
0x18004552b  lea     rdx, [rsp+208h+var_140]
0x180045533  lea     rcx, [rsp+208h+var_1D0]
0x180045538  call    ??$query@UIOleClientSite@@@?$com_ptr_t@VNcsiClientSite@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIOleClientSite@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<NcsiClientSite,wil::err_exception_policy>::query<IOleClientSite>(void)
0x18004553d  nop
0x18004553e  mov     rcx, [rsp+208h]; this
0x180045546  cmp     [rsp+208h+var_140], r13
0x18004554e  jnz     short loc_180045567
0x180045550  mov     r9d, 8007000Dh; char *
0x180045556  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x18004555d  mov     edx, 7Ah ; 'z'; void *
0x180045562  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180045567  mov     [rsp+208h+var_110], r13
0x18004556f  lea     rdx, [rsp+208h+var_110]
0x180045577  lea     rcx, [rsp+208h+var_180]
0x18004557f  call    ??$query@UIOleObject@@@?$com_ptr_t@UIHTMLDocument2@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIOleObject@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IHTMLDocument2,wil::err_exception_policy>::query<IOleObject>(void)
0x180045584  nop
0x180045585  mov     rax, [rsp+208h]
0x18004558d  mov     rcx, [rsp+208h+var_110]
0x180045595  test    rcx, rcx
0x180045598  jnz     short loc_1800455B2
0x18004559a  mov     r9d, 8007000Dh; char *
0x1800455a0  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x1800455a7  lea     edx, [rcx+7Dh]; void *
0x1800455aa  mov     rcx, rax; this
0x1800455ad  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800455b2  mov     rax, [rcx]
0x1800455b5  mov     rdx, [rsp+208h+var_140]
0x1800455bd  mov     rax, [rax+18h]
0x1800455c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455c6  mov     rcx, [rsp+208h]; this
0x1800455ce  test    eax, eax
0x1800455d0  jns     short loc_1800455E6
0x1800455d2  mov     r9d, eax; char *
0x1800455d5  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x1800455dc  mov     edx, 7Eh ; '~'; void *
0x1800455e1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800455e6  mov     [rsp+208h+var_118], r13
0x1800455ee  lea     rdx, [rsp+208h+var_118]
0x1800455f6  lea     rcx, [rsp+208h+var_180]
0x1800455fe  call    ??$query@UIOleControl@@@?$com_ptr_t@UIHTMLDocument2@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIOleControl@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IHTMLDocument2,wil::err_exception_policy>::query<IOleControl>(void)
0x180045603  nop
0x180045604  mov     rax, [rsp+208h]
0x18004560c  mov     rcx, [rsp+208h+var_118]
0x180045614  test    rcx, rcx
0x180045617  jnz     short loc_180045633
0x180045619  mov     r9d, 8007000Dh; char *
0x18004561f  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x180045626  mov     edx, 81h; void *
0x18004562b  mov     rcx, rax; this
0x18004562e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180045633  mov     rax, [rcx]
0x180045636  mov     edx, 0FFFFEA78h
0x18004563b  mov     rax, [rax+28h]
0x18004563f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045644  mov     rcx, [rsp+208h]; this
0x18004564c  test    eax, eax
0x18004564e  jns     short loc_180045664
0x180045650  mov     r9d, eax; char *
0x180045653  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x18004565a  mov     edx, 82h; void *
0x18004565f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180045664  mov     rcx, [rsp+208h+var_180]
0x18004566c  mov     rax, [rcx]
0x18004566f  mov     rdx, [rsp+208h+var_138]
0x180045677  mov     rax, [rax+1D8h]
0x18004567e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045683  mov     rcx, [rsp+208h]; this
0x18004568b  test    eax, eax
0x18004568d  jns     short loc_1800456A3
0x18004568f  mov     r9d, eax; char *
0x180045692  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x180045699  mov     edx, 85h; void *
0x18004569e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800456a3  mov     rcx, [rsp+208h+var_180]
0x1800456ab  mov     rax, [rcx]
0x1800456ae  mov     rax, [rax+1F0h]
0x1800456b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800456ba  mov     rcx, [rsp+208h]; this
0x1800456c2  test    eax, eax
0x1800456c4  jns     short loc_1800456DA
0x1800456c6  mov     r9d, eax; char *
0x1800456c9  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x1800456d0  mov     edx, 86h; void *
0x1800456d5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800456da  mov     [rsp+208h+var_120], r13
0x1800456e2  lea     rdx, [rsp+208h+var_120]
0x1800456ea  lea     rcx, [rsp+208h+var_180]
0x1800456f2  call    ??$query@UIHTMLDocument7@@@?$com_ptr_t@UIHTMLDocument2@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIHTMLDocument7@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IHTMLDocument2,wil::err_exception_policy>::query<IHTMLDocument7>(void)
0x1800456f7  nop
0x1800456f8  mov     rax, [rsp+208h]
0x180045700  mov     rcx, [rsp+208h+var_120]
0x180045708  test    rcx, rcx
0x18004570b  jnz     short loc_180045727
0x18004570d  mov     r9d, 8007000Dh; char *
0x180045713  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x18004571a  mov     edx, 8Ah; void *
0x18004571f  mov     rcx, rax; this
0x180045722  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180045727  mov     [rsp+208h+var_160], r13
0x18004572f  mov     rax, [rcx]
0x180045732  mov     [rsp+208h+var_160], r13
0x18004573a  lea     rdx, [rsp+208h+var_160]
0x180045742  mov     rax, [rax+370h]
0x180045749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004574e  mov     rcx, [rsp+208h]; this
0x180045756  test    eax, eax
0x180045758  jns     short loc_18004576E
0x18004575a  mov     r9d, eax; char *
0x18004575d  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x180045764  mov     edx, 8Ch; void *
0x180045769  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004576e  mov     rcx, [rsp+208h]; this
0x180045776  cmp     [rsp+208h+var_160], r13
0x18004577e  jnz     short loc_180045797
0x180045780  mov     r9d, 8007000Dh; char *
0x180045786  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x18004578d  mov     edx, 8Dh; void *
0x180045792  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180045797  mov     [rsp+208h+var_148], r13
0x18004579f  lea     rdx, [rsp+208h+var_148]
0x1800457a7  lea     rcx, [rsp+208h+var_160]
0x1800457af  call    ??$query@UIHTMLElement2@@@?$com_ptr_t@UIHTMLElement@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIHTMLElement2@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IHTMLElement,wil::err_exception_policy>::query<IHTMLElement2>(void)
0x1800457b4  nop
0x1800457b5  mov     rcx, [rsp+208h]; this
0x1800457bd  cmp     [rsp+208h+var_148], r13
0x1800457c5  jnz     short loc_1800457DE
0x1800457c7  mov     r9d, 8007000Dh; char *
0x1800457cd  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x1800457d4  mov     edx, 91h; void *
0x1800457d9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800457de  mov     [rsp+208h+var_170], r13
0x1800457e6  mov     [rsp+208h+var_128], r13
0x1800457ee  lea     rcx, [rsp+208h+var_128]
0x1800457f6  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800457fb  nop
0x1800457fc  mov     rbx, [rsp+208h+var_148]
0x180045804  mov     rax, [rbx]
0x180045807  mov     rsi, [rax+340h]
0x18004580e  mov     rcx, [rsp+208h+var_170]
0x180045816  mov     [rsp+208h+var_170], r13
0x18004581e  test    rcx, rcx
0x180045821  jz      short loc_180045830
0x180045823  mov     rax, [rcx]
0x180045826  mov     rax, [rax+10h]
0x18004582a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004582f  nop
0x180045830  lea     r8, [rsp+208h+var_170]
0x180045838  mov     rdx, [rsp+208h+var_128]
0x180045840  mov     rcx, rbx
0x180045843  mov     rax, rsi
0x180045846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004584b  mov     rcx, [rsp+208h]; this
0x180045853  test    eax, eax
0x180045855  jns     short loc_18004586B
0x180045857  mov     r9d, eax; char *
0x18004585a  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x180045861  mov     edx, 94h; void *
0x180045866  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004586b  mov     rcx, [rsp+208h]; this
0x180045873  cmp     [rsp+208h+var_170], r13
0x18004587b  jnz     short loc_180045894
0x18004587d  mov     r9d, 8007000Dh; char *
0x180045883  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x18004588a  mov     edx, 95h; void *
0x18004588f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180045894  mov     [rsp+208h+var_158], r13d
0x18004589c  mov     [rsp+208h+var_150], r13
0x1800458a4  lea     rdx, [rsp+208h+var_150]
0x1800458ac  lea     rcx, [rsp+208h+var_170]
0x1800458b4  call    ??$query@UIHTMLElementCollection4@@@?$com_ptr_t@UIHTMLElementCollection@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIHTMLElementCollection4@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IHTMLElementCollection,wil::err_exception_policy>::query<IHTMLElementCollection4>(void)
0x1800458b9  nop
0x1800458ba  mov     rax, [rsp+208h]
0x1800458c2  mov     rcx, [rsp+208h+var_150]
0x1800458ca  test    rcx, rcx
0x1800458cd  jnz     short loc_1800458E9
0x1800458cf  mov     r9d, 8007000Dh; char *
0x1800458d5  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x1800458dc  mov     edx, 9Ah; void *
0x1800458e1  mov     rcx, rax; this
0x1800458e4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800458e9  mov     rax, [rcx]
0x1800458ec  lea     rdx, [rsp+208h+var_158]
0x1800458f4  mov     rax, [rax+38h]
0x1800458f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458fd  mov     rcx, [rsp+208h]; this
0x180045905  test    eax, eax
0x180045907  jns     short loc_18004591D
0x180045909  mov     r9d, eax; char *
0x18004590c  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x180045913  mov     edx, 9Bh; void *
0x180045918  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004591d  mov     esi, r13d
0x180045920  cmp     esi, [rsp+208h+var_158]
0x180045927  jge     loc_180045F64
0x18004592d  mov     [rsp+208h+var_168], r13
0x180045935  mov     rcx, [rsp+208h+var_150]
0x18004593d  mov     rax, [rcx]
0x180045940  mov     [rsp+208h+var_168], r13
0x180045948  lea     r8, [rsp+208h+var_168]
0x180045950  mov     edx, esi
0x180045952  mov     rax, [rax+40h]
0x180045956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004595b  mov     rcx, [rsp+208h]; this
0x180045963  test    eax, eax
0x180045965  jns     short loc_18004597B
0x180045967  mov     r9d, eax; char *
0x18004596a  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x180045971  mov     edx, 0A1h; void *
0x180045976  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004597b  mov     rcx, [rsp+208h]; this
0x180045983  cmp     [rsp+208h+var_168], r13
0x18004598b  jnz     short loc_1800459A4
0x18004598d  mov     r9d, 8007000Dh; char *
0x180045993  lea     r8, aOnecoreNetDiag_12; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x18004599a  mov     edx, 0A2h; void *
0x18004599f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800459a4  mov     [rsp+208h+bstrString], r13
0x1800459ac  mov     [rsp+208h+var_178], r13
0x1800459b4  lea     rdx, [rsp+208h+var_178]
0x1800459bc  lea     rcx, [rsp+208h+var_168]
0x1800459c4  call    ??$query@UIHTMLMetaElement@@@?$com_ptr_t@UIHTMLElement2@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIHTMLMetaElement@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IHTMLElement2,wil::err_exception_policy>::query<IHTMLMetaElement>(void)
0x1800459c9  nop
  ... truncated ...
```
