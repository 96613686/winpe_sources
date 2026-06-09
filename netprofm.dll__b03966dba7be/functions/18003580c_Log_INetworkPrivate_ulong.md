# Log(INetworkPrivate *,ulong)

- ea: `0x18003580c`
- end: `0x180036406`
- name: `?Log@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkPrivate@@K@Z`
- size: `3066`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800104b8`
- `0x180010ce0`

## callees

- `0x18000e310`
- `0x18000f388`
- `0x1800100d8`
- `0x180010124`
- `0x180011614`
- `0x1800120d0`
- `0x180034d8c`
- `0x180034dac`
- `0x18003580c`
- `0x18003640c`
- `0x180036950`
- `0x180036a3c`
- `0x180037e38`
- `0x18003816c`
- `0x18003830c`
- `0x180038338`
- `0x1800384d0`
- `0x18003a2ac`
- `0x18003a37c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003638d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003638d`

## string_xrefs

- `0x180035b45`: `  ! <INetworkPrivate::GetTimeCreatedAndConnected failed (0x%x)>`
- `0x180035cb8`: `onecore\net\netprofiles\service\src\netshnlmplugin\privatenetworklistmanager.cpp`
- `0x180035df8`: `onecore\net\netprofiles\service\src\netshnlmplugin\privatenetworklistmanager.cpp`
- `0x1800361d8`: `\n >>>>>> INetwork [%u] <<<<<< \n    Category: %ws\n    Description: %ws\n    Icon: %ws\n    NetworkId: %ws\n    NetworkName: %ws\n    NetworkState: %ws\n    TimeCreated: %ws\n    TimeConnected: %ws\n    NetworkType: %ws\n    NetworkSignatures (%u):\n    %ws    NetworkInterfaces (%u):\n    %ws%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=44
__int64 __fastcall Log(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v5; // r15
  __m128i si128; // xmm6
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // r14d
  int (__fastcall *v16)(__int64, __int64, __int64 *); // rbx
  __int64 v17; // rax
  const char *v18; // rbx
  __int64 v19; // rcx
  int v20; // ebx
  __int64 v21; // rax
  const char *v22; // rsi
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rsi
  __int64 v28; // r13
  const wchar_t *v29; // r8
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  const wchar_t *v35; // r8
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rcx
  const char *v40; // [rsp+30h] [rbp-E8h]
  _BYTE v41[32]; // [rsp+98h] [rbp-80h] BYREF
  __int64 v42; // [rsp+B8h] [rbp-60h]
  __int64 v43; // [rsp+C0h] [rbp-58h]
  __int64 v44; // [rsp+D0h] [rbp-48h]
  __int64 v45; // [rsp+D8h] [rbp-40h]
  __int64 v46; // [rsp+E0h] [rbp-38h]
  __int64 v47; // [rsp+E8h] [rbp-30h]
  _BYTE v48[32]; // [rsp+F0h] [rbp-28h] BYREF
  _BYTE v49[32]; // [rsp+110h] [rbp-8h] BYREF
  _BYTE v50[32]; // [rsp+130h] [rbp+18h] BYREF
  _BYTE v51[32]; // [rsp+150h] [rbp+38h] BYREF
  _BYTE v52[32]; // [rsp+170h] [rbp+58h] BYREF
  _BYTE v53[32]; // [rsp+190h] [rbp+78h] BYREF
  _BYTE v54[32]; // [rsp+1B0h] [rbp+98h] BYREF
  _BYTE v55[32]; // [rsp+1D0h] [rbp+B8h] BYREF
  _BYTE v56[32]; // [rsp+1F0h] [rbp+D8h] BYREF
  _BYTE v57[32]; // [rsp+210h] [rbp+F8h] BYREF
  _BYTE v58[32]; // [rsp+230h] [rbp+118h] BYREF
  _BYTE v59[32]; // [rsp+250h] [rbp+138h] BYREF
  _BYTE v60[32]; // [rsp+270h] [rbp+158h] BYREF
  _BYTE v61[32]; // [rsp+290h] [rbp+178h] BYREF
  _BYTE v62[32]; // [rsp+2B0h] [rbp+198h] BYREF
  int v63; // [rsp+2D0h] [rbp+1B8h] BYREF
  unsigned int v64; // [rsp+2D4h] [rbp+1BCh] BYREF
  unsigned int v65; // [rsp+2D8h] [rbp+1C0h] BYREF
  int v66; // [rsp+2DCh] [rbp+1C4h] BYREF
  __int64 v67; // [rsp+2E0h] [rbp+1C8h] BYREF
  __int64 v68; // [rsp+2E8h] [rbp+1D0h] BYREF
  __int64 v69; // [rsp+2F0h] [rbp+1D8h] BYREF
  __int64 v70; // [rsp+2F8h] [rbp+1E0h] BYREF
  __int64 v71; // [rsp+300h] [rbp+1E8h] BYREF
  void *v72; // [rsp+308h] [rbp+1F0h] BYREF
  void *v73; // [rsp+310h] [rbp+1F8h] BYREF
  __int64 v74; // [rsp+318h] [rbp+200h] BYREF
  __int64 v75; // [rsp+320h] [rbp+208h] BYREF
  LPVOID pv[2]; // [rsp+328h] [rbp+210h] BYREF
  _OWORD v77[2]; // [rsp+338h] [rbp+220h] BYREF
  _OWORD v78[2]; // [rsp+358h] [rbp+240h] BYREF
  _OWORD v79[2]; // [rsp+378h] [rbp+260h] BYREF
  _OWORD v80[2]; // [rsp+398h] [rbp+280h] BYREF
  _OWORD v81[2]; // [rsp+3B8h] [rbp+2A0h] BYREF
  _OWORD v82[2]; // [rsp+3D8h] [rbp+2C0h] BYREF
  _OWORD v83[2]; // [rsp+3F8h] [rbp+2E0h] BYREF
  _OWORD v84[2]; // [rsp+418h] [rbp+300h] BYREF
  __int128 v85; // [rsp+438h] [rbp+320h] BYREF
  _OWORD v86[2]; // [rsp+448h] [rbp+330h] BYREF
  _OWORD v87[2]; // [rsp+468h] [rbp+350h] BYREF
  _OWORD v88[2]; // [rsp+488h] [rbp+370h] BYREF
  _OWORD v89[2]; // [rsp+4A8h] [rbp+390h] BYREF
  _OWORD v90[2]; // [rsp+4C8h] [rbp+3B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+540h] [rbp+428h]

  v5 = a1;
  v42 = a1;
  v43 = a1;
  v83[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v83[1] = si128;
  LOWORD(v83[0]) = 0;
  v66 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 104LL))(a2, &v66) < 0 )
  {
    v7 = wil::str_printf<std::wstring>((__int64)v41, (__int64)L"  ! <INetworkPrivate::GetCategory failed (0x%x)>", 1);
    std::wstring::operator=((__int64)v83, v7);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v82[0] = 0;
  v82[1] = si128;
  LOWORD(v82[0]) = 0;
  v72 = 0;
  if ( (*(int (__fastcall **)(__int64, void **))(*(_QWORD *)a2 + 32LL))(a2, &v72) < 0 )
  {
    v8 = wil::str_printf<std::wstring>((__int64)v41, (__int64)L"  ! <INetworkPrivate::GetDescription failed (0x%x)>", 1);
    std::wstring::operator=((__int64)v82, v8);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v81[0] = 0;
  v81[1] = si128;
  LOWORD(v81[0]) = 0;
  v65 = 0;
  pv[0] = 0;
  pv[1] = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, unsigned int *, LPVOID *))(*(_QWORD *)a2 + 64LL))(a2, 48, &v65, pv) < 0 )
  {
    v9 = wil::str_printf<std::wstring>((__int64)v41, (__int64)L"  ! <INetworkPrivate::GetIcon failed (0x%x)>", 1);
    std::wstring::operator=((__int64)v81, v9);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v80[0] = 0;
  v80[1] = si128;
  LOWORD(v80[0]) = 0;
  v85 = 0;
  if ( (*(int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 48LL))(a2, &v85) < 0 )
  {
    v10 = wil::str_printf<std::wstring>((__int64)v41, (__int64)L"  ! <INetworkPrivate::GetId failed (0x%x)>", 1);
    std::wstring::operator=((__int64)v80, v10);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v79[0] = 0;
  v79[1] = si128;
  LOWORD(v79[0]) = 0;
  v73 = 0;
  if ( (*(int (__fastcall **)(__int64, void **))(*(_QWORD *)a2 + 24LL))(a2, &v73) < 0 )
  {
    v11 = wil::str_printf<std::wstring>((__int64)v41, (__int64)L"  ! <INetworkPrivate::GetName failed (0x%x)>", 1);
    std::wstring::operator=((__int64)v79, v11);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v90[0] = 0;
  v90[1] = si128;
  LOWORD(v90[0]) = 0;
  v64 = 0;
  if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 96LL))(a2, &v64) < 0 )
  {
    v12 = wil::str_printf<std::wstring>((__int64)v41, (__int64)L"  ! <INetworkPrivate::GetState failed (0x%x)>", 1);
    std::wstring::operator=((__int64)v90, v12);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v78[0] = 0;
  v78[1] = si128;
  LOWORD(v78[0]) = 0;
  v74 = 0;
  v75 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64 *, char *, __int64 *, char *))(*(_QWORD *)a2 + 88LL))(
         a2,
         &v74,
         (char *)&v74 + 4,
         &v75,
         (char *)&v75 + 4) < 0 )
  {
    v13 = wil::str_printf<std::wstring>(
            (__int64)v41,
            (__int64)L"  ! <INetworkPrivate::GetTimeCreatedAndConnected failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v78, v13);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v89[0] = 0;
  v89[1] = si128;
  LOWORD(v89[0]) = 0;
  v63 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 80LL))(a2, &v63) < 0 )
  {
    v14 = wil::str_printf<std::wstring>((__int64)v41, (__int64)L"  ! <INetworkPrivate::GetType failed (0x%x)>", 1);
    std::wstring::operator=((__int64)v89, v14);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v15 = 0;
  v88[0] = 0;
  v88[1] = si128;
  LOWORD(v88[0]) = 0;
  v87[0] = 0;
  v87[1] = si128;
  LOWORD(v87[0]) = 0;
  v70 = 0;
  v16 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)a2 + 128LL);
  Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(&v70);
  if ( v16(a2, 3, &v70) >= 0 )
  {
    do
    {
      LODWORD(v68) = 0;
      v67 = 0;
      v18 = (const char *)(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v70 + 24LL))(
                            v70,
                            1,
                            &v67,
                            &v68);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x36B,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\privatenetworklistmanager.cpp",
        v18,
        (int)"IEnumNetworkInterfacePrivate::Next",
        v40);
      if ( !(_DWORD)v18 )
      {
        Log(v41, v67, (unsigned int)++v15);
        std::wstring::append();
        std::wstring::_Tidy_deallocate((__int64)v41);
      }
      v19 = v67;
      if ( v67 )
      {
        v67 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    while ( !(_DWORD)v18 );
    v5 = v42;
  }
  else
  {
    v17 = wil::str_printf<std::wstring>(
            (__int64)v41,
            (__int64)L"  ! <INetworkPrivate::EnumNetworkSignatures failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v87, v17);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v20 = 0;
  v86[0] = 0;
  v86[1] = si128;
  LOWORD(v86[0]) = 0;
  v84[0] = 0;
  v84[1] = si128;
  LOWORD(v84[0]) = 0;
  v71 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 120LL))(a2, &v71) >= 0 )
  {
    do
    {
      LODWORD(v68) = 0;
      v67 = 0;
      v22 = (const char *)(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v71 + 24LL))(
                            v71,
                            1,
                            &v67,
                            &v68);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x384,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\privatenetworklistmanager.cpp",
        v22,
        (int)"IEnumNetworkInterfacePrivate::Next",
        v40);
      if ( !(_DWORD)v22 )
      {
        LogINetworkInterface1(v41, v67, (unsigned int)++v20);
        std::wstring::append();
        std::wstring::_Tidy_deallocate((__int64)v41);
      }
      v23 = v67;
      if ( v67 )
      {
        v67 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
    while ( !(_DWORD)v22 );
    v5 = v42;
  }
  else
  {
    v21 = wil::str_printf<std::wstring>(
            (__int64)v41,
            (__int64)L"  ! <INetworkPrivate::EnumNetworkInterfaces failed (0x%x)>",
            1);
    std::wstring::operator=((__int64)v84, v21);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v77[0] = 0;
  v77[1] = si128;
  LOWORD(v77[0]) = 0;
  v69 = 0;
  v24 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a2)(
          a2,
          &GUID_f548ddde_05e4_4356_8b42_bb69bb7c195f,
          &v69);
  if ( v24 < 0 )
  {
    v25 = wil::str_printf<std::wstring>(
            (__int64)v41,
            (__int64)L"  ! <INetworkPrivate2::QueryInterface(INetworkPrivate2) failed (0x%x)>",
            (unsigned int)v24);
    std::wstring::operator=((__int64)v77, v25);
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  if ( v69 )
  {
    std::wstring::push_back(v77);
    LogINetwork2_0(v41, v69, a3);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)v41);
  }
  v26 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToStringCheckingErrors(v62, v84, v86);
  v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToStringCheckingErrors(v61, v87, v88);
  v28 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( v63 )
  {
    if ( v63 == 1 )
      v29 = L"Managed";
    else
      v29 = L"(unknown NP_NETWORK_TYPE)";
  }
  else
  {
    v29 = L"Unmanaged";
  }
  ToStringCheckingErrors(v60, v89, v29);
  v42 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v30 = ToString(v59, &v75);
  ToStringCheckingErrors(v49, v78, v30);
  v67 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v31 = ToString(v50, &v74);
  ToStringCheckingErrors(v48, v78, v31);
  v68 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v32 = ToString(v51, v64);
  ToStringCheckingErrors(v52, v90, v32);
  v44 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToStringCheckingErrors(v53, v79, v73);
  v45 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v33 = ToString(v54, &v85);
  ToStringCheckingErrors(v55, v80, v33);
  v46 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v34 = wil::str_printf<std::wstring>((__int64)v56, (__int64)L"%u bytes", v65);
  ToStringCheckingErrors(v57, v81, v34);
  v47 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToStringCheckingErrors(v58, v82, v72);
  v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( v66 )
  {
    if ( v66 == 1 )
    {
      v35 = L"Private";
    }
    else if ( v66 == 2 )
    {
      v35 = L"Authenticated";
    }
    else
    {
      v35 = L"(unknown NP_NETWORK_CATEGORY)";
    }
  }
  else
  {
    v35 = L"Public";
  }
  ToStringCheckingErrors(v41, v83, v35);
  v36 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>(
    v5,
    (__int64)L"\n"
              " >>>>>> INetwork [%u] <<<<<< \n"
              "    Category: %ws\n"
              "    Description: %ws\n"
              "    Icon: %ws\n"
              "    NetworkId: %ws\n"
              "    NetworkName: %ws\n"
              "    NetworkState: %ws\n"
              "    TimeCreated: %ws\n"
              "    TimeConnected: %ws\n"
              "    NetworkType: %ws\n"
              "    NetworkSignatures (%u):\n"
              "    %ws    NetworkInterfaces (%u):\n"
              "    %ws%ws",
    a3,
    v36,
    v43,
    v47,
    v46,
    v45,
    v44,
    v68,
    v67,
    v42,
    v15,
    v28,
    v20,
    v27,
    v26);
  std::wstring::_Tidy_deallocate((__int64)v41);
  std::wstring::_Tidy_deallocate((__int64)v58);
  std::wstring::_Tidy_deallocate((__int64)v57);
  std::wstring::_Tidy_deallocate((__int64)v56);
  std::wstring::_Tidy_deallocate((__int64)v55);
  std::wstring::_Tidy_deallocate((__int64)v54);
  std::wstring::_Tidy_deallocate((__int64)v53);
  std::wstring::_Tidy_deallocate((__int64)v52);
  std::wstring::_Tidy_deallocate((__int64)v51);
  std::wstring::_Tidy_deallocate((__int64)v48);
  std::wstring::_Tidy_deallocate((__int64)v50);
  std::wstring::_Tidy_deallocate((__int64)v49);
  std::wstring::_Tidy_deallocate((__int64)v59);
  std::wstring::_Tidy_deallocate((__int64)v60);
  std::wstring::_Tidy_deallocate((__int64)v61);
  std::wstring::_Tidy_deallocate((__int64)v62);
  v37 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  std::wstring::_Tidy_deallocate((__int64)v77);
  v38 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  std::wstring::_Tidy_deallocate((__int64)v84);
  std::wstring::_Tidy_deallocate((__int64)v86);
  Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(&v70);
  std::wstring::_Tidy_deallocate((__int64)v87);
  std::wstring::_Tidy_deallocate((__int64)v88);
  std::wstring::_Tidy_deallocate((__int64)v89);
  std::wstring::_Tidy_deallocate((__int64)v78);
  std::wstring::_Tidy_deallocate((__int64)v90);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v73);
  std::wstring::_Tidy_deallocate((__int64)v79);
  std::wstring::_Tidy_deallocate((__int64)v80);
  if ( pv[0] )
  {
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    pv[1] = 0;
  }
  std::wstring::_Tidy_deallocate((__int64)v81);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v72);
  std::wstring::_Tidy_deallocate((__int64)v82);
  std::wstring::_Tidy_deallocate((__int64)v83);
  return v5;
}

```

## disassembly

```asm
0x18003580c  mov     rax, rsp
0x18003580f  mov     [rax+20h], rbx
0x180035813  push    rbp
0x180035814  push    rsi
0x180035815  push    rdi
0x180035816  push    r12
0x180035818  push    r13
0x18003581a  push    r14
0x18003581c  push    r15
0x18003581e  lea     rbp, [rax-428h]
0x180035825  sub     rsp, 500h
0x18003582c  movaps  xmmword ptr [rax-48h], xmm6
0x180035830  mov     rax, cs:__security_cookie
0x180035837  xor     rax, rsp
0x18003583a  mov     [rbp+420h+var_50], rax
0x180035841  mov     r12d, r8d
0x180035844  mov     rdi, rdx
0x180035847  mov     r15, rcx
0x18003584a  mov     [rbp+420h+var_480], rcx
0x18003584e  mov     [rbp+420h+var_478], rcx
0x180035852  xor     r13d, r13d
0x180035855  xorps   xmm0, xmm0
0x180035858  movups  [rbp+420h+var_140], xmm0
0x18003585f  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180035867  movdqu  [rbp+420h+var_130], xmm6
0x18003586f  mov     word ptr [rbp+420h+var_140], r13w
0x180035877  mov     [rbp+420h+var_25C], r13d
0x18003587e  mov     rax, [rdx]
0x180035881  lea     rdx, [rbp+420h+var_25C]
0x180035888  mov     rcx, rdi
0x18003588b  mov     rax, [rax+68h]
0x18003588f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035894  lea     esi, [r13+1]
0x180035898  test    eax, eax
0x18003589a  jns     short loc_1800358C7
0x18003589c  mov     r8d, esi
0x18003589f  lea     rdx, aInetworkprivat_0; "  ! <INetworkPrivate::GetCategory faile"...
0x1800358a6  lea     rcx, [rbp+420h+var_4A0]
0x1800358aa  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x1800358af  mov     rdx, rax
0x1800358b2  lea     rcx, [rbp+420h+var_140]
0x1800358b9  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800358be  lea     rcx, [rbp+420h+var_4A0]
0x1800358c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800358c7  xorps   xmm0, xmm0
0x1800358ca  movups  [rbp+420h+var_160], xmm0
0x1800358d1  movdqu  [rbp+420h+var_150], xmm6
0x1800358d9  mov     word ptr [rbp+420h+var_160], r13w
0x1800358e1  mov     [rbp+420h+var_230], r13
0x1800358e8  mov     rax, [rdi]
0x1800358eb  lea     rdx, [rbp+420h+var_230]
0x1800358f2  mov     rcx, rdi
0x1800358f5  mov     rax, [rax+20h]
0x1800358f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358fe  test    eax, eax
0x180035900  jns     short loc_18003592D
0x180035902  mov     r8d, esi
0x180035905  lea     rdx, aInetworkprivat; "  ! <INetworkPrivate::GetDescription fa"...
0x18003590c  lea     rcx, [rbp+420h+var_4A0]
0x180035910  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180035915  mov     rdx, rax
0x180035918  lea     rcx, [rbp+420h+var_160]
0x18003591f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035924  lea     rcx, [rbp+420h+var_4A0]
0x180035928  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003592d  xorps   xmm0, xmm0
0x180035930  movups  [rbp+420h+var_180], xmm0
0x180035937  movdqu  [rbp+420h+var_170], xmm6
0x18003593f  mov     word ptr [rbp+420h+var_180], r13w
0x180035947  mov     [rbp+420h+var_260], r13d
0x18003594e  movups  xmmword ptr [rbp+420h+pv], xmm0
0x180035955  mov     [rbp+420h+pv], r13
0x18003595c  mov     [rbp+420h+pv+8], r13
0x180035963  mov     rax, [rdi]
0x180035966  lea     r9, [rbp+420h+pv]
0x18003596d  lea     r8, [rbp+420h+var_260]
0x180035974  mov     edx, 30h ; '0'
0x180035979  mov     rcx, rdi
0x18003597c  mov     rax, [rax+40h]
0x180035980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035985  test    eax, eax
0x180035987  jns     short loc_1800359B4
0x180035989  mov     r8d, esi
0x18003598c  lea     rdx, aInetworkprivat_7; "  ! <INetworkPrivate::GetIcon failed (0"...
0x180035993  lea     rcx, [rbp+420h+var_4A0]
0x180035997  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003599c  mov     rdx, rax
0x18003599f  lea     rcx, [rbp+420h+var_180]
0x1800359a6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800359ab  lea     rcx, [rbp+420h+var_4A0]
0x1800359af  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800359b4  xorps   xmm0, xmm0
0x1800359b7  movups  [rbp+420h+var_1A0], xmm0
0x1800359be  movdqu  [rbp+420h+var_190], xmm6
0x1800359c6  mov     word ptr [rbp+420h+var_1A0], r13w
0x1800359ce  movups  [rbp+420h+var_100], xmm0
0x1800359d5  mov     rax, [rdi]
0x1800359d8  lea     rdx, [rbp+420h+var_100]
0x1800359df  mov     rcx, rdi
0x1800359e2  mov     rax, [rax+30h]
0x1800359e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359eb  test    eax, eax
0x1800359ed  jns     short loc_180035A1A
0x1800359ef  mov     r8d, esi
0x1800359f2  lea     rdx, aInetworkprivat_3; "  ! <INetworkPrivate::GetId failed (0x%"...
0x1800359f9  lea     rcx, [rbp+420h+var_4A0]
0x1800359fd  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180035a02  mov     rdx, rax
0x180035a05  lea     rcx, [rbp+420h+var_1A0]
0x180035a0c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035a11  lea     rcx, [rbp+420h+var_4A0]
0x180035a15  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035a1a  xorps   xmm0, xmm0
0x180035a1d  movups  [rbp+420h+var_1C0], xmm0
0x180035a24  movdqu  [rbp+420h+var_1B0], xmm6
0x180035a2c  mov     word ptr [rbp+420h+var_1C0], r13w
0x180035a34  mov     [rbp+420h+var_228], r13
0x180035a3b  mov     rax, [rdi]
0x180035a3e  lea     rdx, [rbp+420h+var_228]
0x180035a45  mov     rcx, rdi
0x180035a48  mov     rax, [rax+18h]
0x180035a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a51  test    eax, eax
0x180035a53  jns     short loc_180035A80
0x180035a55  mov     r8d, esi
0x180035a58  lea     rdx, aInetworkprivat_11; "  ! <INetworkPrivate::GetName failed (0"...
0x180035a5f  lea     rcx, [rbp+420h+var_4A0]
0x180035a63  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180035a68  mov     rdx, rax
0x180035a6b  lea     rcx, [rbp+420h+var_1C0]
0x180035a72  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035a77  lea     rcx, [rbp+420h+var_4A0]
0x180035a7b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035a80  xorps   xmm0, xmm0
0x180035a83  movups  [rbp+420h+var_70], xmm0
0x180035a8a  movdqu  [rbp+420h+var_60], xmm6
0x180035a92  mov     word ptr [rbp+420h+var_70], r13w
0x180035a9a  mov     [rbp+420h+var_264], r13d
0x180035aa1  mov     rax, [rdi]
0x180035aa4  lea     rdx, [rbp+420h+var_264]
0x180035aab  mov     rcx, rdi
0x180035aae  mov     rax, [rax+60h]
0x180035ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ab7  test    eax, eax
0x180035ab9  jns     short loc_180035AE6
0x180035abb  mov     r8d, esi
0x180035abe  lea     rdx, aInetworkprivat_1; "  ! <INetworkPrivate::GetState failed ("...
0x180035ac5  lea     rcx, [rbp+420h+var_4A0]
0x180035ac9  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180035ace  mov     rdx, rax
0x180035ad1  lea     rcx, [rbp+420h+var_70]
0x180035ad8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035add  lea     rcx, [rbp+420h+var_4A0]
0x180035ae1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035ae6  xorps   xmm0, xmm0
0x180035ae9  movups  [rbp+420h+var_1E0], xmm0
0x180035af0  movdqu  [rbp+420h+var_1D0], xmm6
0x180035af8  mov     word ptr [rbp+420h+var_1E0], r13w
0x180035b00  mov     [rbp+420h+var_220], r13
0x180035b07  mov     [rbp+420h+var_218], r13
0x180035b0e  mov     rax, [rdi]
0x180035b11  lea     rcx, [rbp+420h+var_218+4]
0x180035b18  mov     qword ptr [rsp+530h+var_510], rcx
0x180035b1d  lea     r9, [rbp+420h+var_218]
0x180035b24  lea     r8, [rbp+420h+var_220+4]
0x180035b2b  lea     rdx, [rbp+420h+var_220]
0x180035b32  mov     rcx, rdi
0x180035b35  mov     rax, [rax+58h]
0x180035b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b3e  test    eax, eax
0x180035b40  jns     short loc_180035B6D
0x180035b42  mov     r8d, esi
0x180035b45  lea     rdx, aInetworkprivat_4; "  ! <INetworkPrivate::GetTimeCreatedAnd"...
0x180035b4c  lea     rcx, [rbp+420h+var_4A0]
0x180035b50  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180035b55  mov     rdx, rax
0x180035b58  lea     rcx, [rbp+420h+var_1E0]
0x180035b5f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035b64  lea     rcx, [rbp+420h+var_4A0]
0x180035b68  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035b6d  xorps   xmm0, xmm0
0x180035b70  movups  [rbp+420h+var_90], xmm0
0x180035b77  movdqu  [rbp+420h+var_80], xmm6
0x180035b7f  mov     word ptr [rbp+420h+var_90], r13w
0x180035b87  mov     [rbp+420h+var_268], r13d
0x180035b8e  mov     rax, [rdi]
0x180035b91  lea     rdx, [rbp+420h+var_268]
0x180035b98  mov     rcx, rdi
0x180035b9b  mov     rax, [rax+50h]
0x180035b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ba4  test    eax, eax
0x180035ba6  jns     short loc_180035BD3
0x180035ba8  mov     r8d, esi
0x180035bab  lea     rdx, aInetworkprivat_5; "  ! <INetworkPrivate::GetType failed (0"...
0x180035bb2  lea     rcx, [rbp+420h+var_4A0]
0x180035bb6  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180035bbb  mov     rdx, rax
0x180035bbe  lea     rcx, [rbp+420h+var_90]
0x180035bc5  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035bca  lea     rcx, [rbp+420h+var_4A0]
0x180035bce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035bd3  mov     r14d, r13d
0x180035bd6  xorps   xmm0, xmm0
0x180035bd9  movups  [rbp+420h+var_B0], xmm0
0x180035be0  movdqu  [rbp+420h+var_A0], xmm6
0x180035be8  mov     word ptr [rbp+420h+var_B0], r13w
0x180035bf0  movups  [rbp+420h+var_D0], xmm0
0x180035bf7  movdqu  [rbp+420h+var_C0], xmm6
0x180035bff  mov     word ptr [rbp+420h+var_D0], r13w
0x180035c07  mov     [rbp+420h+var_240], r13
0x180035c0e  mov     rax, [rdi]
0x180035c11  mov     rbx, [rax+80h]
0x180035c18  lea     rcx, [rbp+420h+var_240]
0x180035c1f  call    ?InternalRelease@?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyBag>::InternalRelease(void)
0x180035c24  lea     r8, [rbp+420h+var_240]
0x180035c2b  mov     edx, 3
0x180035c30  mov     rcx, rdi
0x180035c33  mov     rax, rbx
0x180035c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c3b  test    eax, eax
0x180035c3d  jns     short loc_180035C6F
0x180035c3f  mov     r8d, esi
0x180035c42  lea     rdx, aInetworkprivat_10; "  ! <INetworkPrivate::EnumNetworkSignat"...
0x180035c49  lea     rcx, [rbp+420h+var_4A0]
0x180035c4d  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180035c52  mov     rdx, rax
0x180035c55  lea     rcx, [rbp+420h+var_D0]
0x180035c5c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035c61  lea     rcx, [rbp+420h+var_4A0]
0x180035c65  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035c6a  jmp     loc_180035D2A
0x180035c6f  lea     r15, aIenumnetworkin; "IEnumNetworkInterfacePrivate::Next"
0x180035c76  mov     dword ptr [rbp+420h+var_250], r13d
0x180035c7d  mov     [rbp+420h+var_258], r13
0x180035c84  mov     rcx, [rbp+420h+var_240]
0x180035c8b  mov     rax, [rcx]
0x180035c8e  lea     r9, [rbp+420h+var_250]
0x180035c95  lea     r8, [rbp+420h+var_258]
0x180035c9c  mov     edx, esi
0x180035c9e  mov     rax, [rax+18h]
0x180035ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ca7  mov     ebx, eax
0x180035ca9  mov     rcx, [rbp+428h]; this
0x180035cb0  mov     qword ptr [rsp+530h+var_510], r15; int
0x180035cb5  mov     r9d, eax; char *
0x180035cb8  lea     r8, aOnecoreNetNetp_3; "onecore\\net\\netprofiles\\service\\src"...
0x180035cbf  mov     edx, 36Bh; void *
0x180035cc4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180035cc9  test    ebx, ebx
0x180035ccb  jnz     short loc_180035CFE
0x180035ccd  add     r14d, esi
0x180035cd0  mov     r8d, r14d
0x180035cd3  mov     rdx, [rbp+420h+var_258]
0x180035cda  lea     rcx, [rbp+420h+var_4A0]
0x180035cde  call    ?Log@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkSignaturePrivate@@K@Z; Log(INetworkSignaturePrivate *,ulong)
0x180035ce3  nop
0x180035ce4  mov     rdx, rax
0x180035ce7  lea     rcx, [rbp+420h+var_B0]
0x180035cee  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180035cf3  nop
0x180035cf4  lea     rcx, [rbp+420h+var_4A0]
0x180035cf8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035cfd  nop
0x180035cfe  mov     rcx, [rbp+420h+var_258]
0x180035d05  test    rcx, rcx
0x180035d08  jz      short loc_180035D1E
0x180035d0a  mov     [rbp+420h+var_258], r13
0x180035d11  mov     rax, [rcx]
0x180035d14  mov     rax, [rax+10h]
0x180035d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d1d  nop
0x180035d1e  test    ebx, ebx
0x180035d20  jz      loc_180035C76
0x180035d26  mov     r15, [rbp+420h+var_480]
0x180035d2a  mov     ebx, r13d
0x180035d2d  xorps   xmm0, xmm0
0x180035d30  movups  [rbp+420h+var_F0], xmm0
0x180035d37  movdqu  [rbp+420h+var_E0], xmm6
0x180035d3f  mov     word ptr [rbp+420h+var_F0], r13w
0x180035d47  movups  [rbp+420h+var_120], xmm0
0x180035d4e  movdqu  [rbp+420h+var_110], xmm6
0x180035d56  mov     word ptr [rbp+420h+var_120], r13w
0x180035d5e  mov     [rbp+420h+var_238], r13
0x180035d65  mov     rax, [rdi]
0x180035d68  lea     rdx, [rbp+420h+var_238]
0x180035d6f  mov     rcx, rdi
0x180035d72  mov     rax, [rax+78h]
0x180035d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d7b  test    eax, eax
0x180035d7d  jns     short loc_180035DAF
0x180035d7f  mov     r8d, esi
0x180035d82  lea     rdx, aInetworkprivat_9; "  ! <INetworkPrivate::EnumNetworkInterf"...
0x180035d89  lea     rcx, [rbp+420h+var_4A0]
0x180035d8d  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180035d92  mov     rdx, rax
0x180035d95  lea     rcx, [rbp+420h+var_120]
0x180035d9c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035da1  lea     rcx, [rbp+420h+var_4A0]
0x180035da5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035daa  jmp     loc_180035E6E
  ... truncated ...
```
