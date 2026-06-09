# OEMRegistrationInfo::Save(ushort const *)

- ea: `0x180042820`
- end: `0x180042dfe`
- name: `?Save@OEMRegistrationInfo@@UEAAJPEBG@Z`
- size: `1502`
- prototype: `int(OEMRegistrationInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003470`
- `0x180007bbc`
- `0x180008544`
- `0x180019a38`
- `0x1800230b0`
- `0x180040898`
- `0x180040a80`
- `0x180040b20`
- `0x180040ca8`
- `0x1800418d8`
- `0x180041e60`
- `0x180042068`
- `0x1800420b0`
- `0x180042820`
- `0x180043824`
- `0x180043974`
- `0x180043c58`
- `0x180044d50`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004286d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042894`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004286d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800428c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800428c9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180042932`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180042932`

## string_xrefs

- `0x1800428dc`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042945`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x1800429a2`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042a1a`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042a51`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042af7`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042b1d`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042b6d`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042bed`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042c78`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042ce7`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042905`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall OEMRegistrationInfo::Save(OEMRegistrationInfo *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int *v7; // rbx
  int ActivationFactory; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING, struct Windows::Data::Json::IJsonObject **, _BYTE *); // rbx
  int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  struct Windows::Data::Json::IJsonObject *v14; // rdi
  __int64 (__fastcall *v15)(struct Windows::Data::Json::IJsonObject *, PVOID, _QWORD); // rbx
  char v16; // r8
  HSTRING_HEADER *v17; // rax
  int v18; // eax
  int v19; // eax
  OEMRegistrationInfo *v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64 *); // rbx
  int v26; // eax
  int v27; // r9d
  int Instance; // eax
  int v29; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  _BYTE v33[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::Data::Json::IJsonObject *v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-A8h] BYREF
  struct IOOBECheckboxFieldItem *v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  __int64 v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  int v42; // [rsp+88h] [rbp-78h] BYREF
  int v43; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+98h] [rbp-68h]
  __int64 v46; // [rsp+A0h] [rbp-60h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-58h] BYREF
  int *v48; // [rsp+C0h] [rbp-40h]
  int *v49; // [rsp+C8h] [rbp-38h]
  __int128 v50; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v51; // [rsp+E0h] [rbp-20h]
  _OWORD v52[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v53; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  OEMRegistrationInfo::DeleteOemRegistration(this);
  if ( CompareStringOrdinal(a2, -1, L"{}", -1, 1) != 2 && CompareStringOrdinal(a2, -1, (LPCWCH)&Class, -1, 1) != 2 )
  {
    string = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = WindowsCreateString(a2, v4, &string);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)v5,
        bIgnoreCase);
LABEL_34:
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      return v6;
    }
    v35 = 0;
    v48 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v7 = v48;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    ActivationFactory = RoGetActivationFactory(v7, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v35);
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)ActivationFactory,
        bIgnoreCase);
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      goto LABEL_34;
    }
    v34 = 0;
    v33[0] = 0;
    v9 = v35;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Data::Json::IJsonObject **, _BYTE *))(*(_QWORD *)v35 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v11 = v10(v9, string, &v34, v33);
    v6 = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
      v13 = 141;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)v12,
        bIgnoreCase);
LABEL_32:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      goto LABEL_33;
    }
    if ( !v33[0] )
    {
      v6 = -2147024809;
      v12 = 2147942487LL;
      v13 = 142;
      goto LABEL_11;
    }
    v36 = 0;
    v14 = v34;
    v15 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, _QWORD))(*(_QWORD *)v34 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_1800D1458,
            v16);
    v18 = v15(v14, v17[1].Reserved.Reserved1, &v36);
    v6 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)v18,
        bIgnoreCase);
LABEL_31:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      goto LABEL_32;
    }
    v38 = 0;
    v19 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
            &v36,
            (__int64)&v38);
    v6 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)v19,
        bIgnoreCase);
LABEL_30:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      goto LABEL_31;
    }
    memset(v52, 0, sizeof(v52));
    v53 = 0;
    v42 = 0;
    v50 = 0;
    v51 = 0;
    v43 = 0;
    hstringHeader.Reserved.Reserved1 = this;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v52;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v50;
    v48 = &v42;
    v49 = &v43;
    IterateOverVector<Windows::Data::Json::IJsonValue,_lambda_3ff8f20150595569f851b45acf98ca6e_>(
      v38,
      (__int64)&hstringHeader);
    hstringHeader.Reserved.Reserved1 = v52;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v50;
    hstringHeader.Reserved.Reserved2[16] = 1;
    v37 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    v21 = OEMRegistrationInfo::_CreateCustomerInfo(v20, v34, &v37);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDF,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)v21,
        bIgnoreCase);
    v22 = OEMRegistrationInfo::_InitializePlugin(this);
    v6 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)v22,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      hstringHeader.Reserved.Reserved2[16] = 0;
      _lambda_cb7e458ee6d0cc43f02cc262a65ec96b_::operator()(&hstringHeader);
      goto LABEL_30;
    }
    v39 = 0;
    v23 = Microsoft::WRL::ComPtr<IOOBEOEMRegistrationPlugin>::As<IOOBEOEMRegistrationPluginPrivate>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 3,
            (__int64)&v39);
    v6 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE4,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)v23,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      hstringHeader.Reserved.Reserved2[16] = 0;
      _lambda_cb7e458ee6d0cc43f02cc262a65ec96b_::operator()(&hstringHeader);
      goto LABEL_30;
    }
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v24 = v39;
    v25 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 24LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v44);
    v45 = -1;
    v46 = -1;
    v26 = v25(v24, &v44);
    v6 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)v26,
        bIgnoreCase);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      hstringHeader.Reserved.Reserved2[16] = 0;
      _lambda_cb7e458ee6d0cc43f02cc262a65ec96b_::operator()(&hstringHeader);
      goto LABEL_30;
    }
    v40 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    Instance = CWriteOEMDataTask_CreateInstance(
                 (unsigned int)v52,
                 (unsigned int)&v40,
                 (unsigned int)&v50,
                 v27,
                 (char)v37,
                 v44,
                 (__int64)&v40);
    v6 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)Instance,
        bIgnoreCasea);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      hstringHeader.Reserved.Reserved2[16] = 0;
      _lambda_cb7e458ee6d0cc43f02cc262a65ec96b_::operator()(&hstringHeader);
      goto LABEL_30;
    }
    v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 32LL))(v40);
    v6 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)v29,
        bIgnoreCasea);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      hstringHeader.Reserved.Reserved2[16] = 0;
      _lambda_cb7e458ee6d0cc43f02cc262a65ec96b_::operator()(&hstringHeader);
      goto LABEL_30;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    hstringHeader.Reserved.Reserved2[16] = 0;
    _lambda_cb7e458ee6d0cc43f02cc262a65ec96b_::operator()(&hstringHeader);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
  }
  return 0;
}

```

## disassembly

```asm
0x180042820  mov     [rsp-8+arg_10], rbx
0x180042825  push    rbp
0x180042826  push    rsi
0x180042827  push    rdi
0x180042828  push    r14
0x18004282a  push    r15
0x18004282c  lea     rbp, [rsp-20h]
0x180042831  sub     rsp, 120h
0x180042838  mov     rax, cs:__security_cookie
0x18004283f  xor     rax, rsp
0x180042842  mov     [rbp+40h+var_30], rax
0x180042846  mov     rbx, rdx
0x180042849  mov     rsi, rcx
0x18004284c  call    ?DeleteOemRegistration@OEMRegistrationInfo@@QEAAXXZ; OEMRegistrationInfo::DeleteOemRegistration(void)
0x180042851  mov     [rsp+140h+bIgnoreCase], 1; bIgnoreCase
0x180042859  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004285d  mov     r9d, r15d; cchCount2
0x180042860  lea     r8, asc_1800E34E0; "{}"
0x180042867  mov     edx, r15d; cchCount1
0x18004286a  mov     rcx, rbx; lpString1
0x18004286d  call    cs:__imp_CompareStringOrdinal
0x180042873  cmp     eax, 2
0x180042876  jz      loc_180042DD9
0x18004287c  mov     [rsp+140h+bIgnoreCase], 1; int
0x180042884  mov     r9d, r15d; cchCount2
0x180042887  lea     r8, Class; lpString2
0x18004288e  mov     edx, r15d; cchCount1
0x180042891  mov     rcx, rbx; lpString1
0x180042894  call    cs:__imp_CompareStringOrdinal
0x18004289a  cmp     eax, 2
0x18004289d  jz      loc_180042DD9
0x1800428a3  xor     r14d, r14d
0x1800428a6  mov     [rbp+40h+string], r14
0x1800428aa  xor     edx, edx
0x1800428ac  lea     rcx, [rbp+40h+string]
0x1800428b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800428b5  mov     rdx, r15
0x1800428b8  inc     rdx; length
0x1800428bb  cmp     [rbx+rdx*2], r14w
0x1800428c0  jnz     short loc_1800428B8
0x1800428c2  lea     r8, [rbp+40h+string]; string
0x1800428c6  mov     rcx, rbx; sourceString
0x1800428c9  call    cs:__imp_WindowsCreateString
0x1800428cf  mov     ebx, eax
0x1800428d1  test    eax, eax
0x1800428d3  jns     short loc_1800428F2
0x1800428d5  mov     rcx, [rbp+48h]; this
0x1800428d9  mov     r9d, eax; char *
0x1800428dc  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x1800428e3  mov     edx, 86h; void *
0x1800428e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800428ed  jmp     loc_180042D5E
0x1800428f2  mov     [rsp+140h+var_F0], r14
0x1800428f7  mov     [rbp+40h+var_80], r14
0x1800428fb  mov     r9d, 1Ch; unsigned int
0x180042901  lea     r8d, [r9+1]; unsigned int
0x180042905  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18004290c  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x180042910  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180042915  mov     rbx, [rbp+40h+var_80]
0x180042919  lea     rcx, [rsp+140h+var_F0]
0x18004291e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042923  lea     r8, [rsp+140h+var_F0]
0x180042928  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18004292f  mov     rcx, rbx
0x180042932  call    cs:__imp_RoGetActivationFactory
0x180042938  mov     ebx, eax
0x18004293a  test    eax, eax
0x18004293c  jns     short loc_18004295B
0x18004293e  mov     rcx, [rbp+48h]; this
0x180042942  mov     r9d, eax; char *
0x180042945  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x18004294c  mov     edx, 88h; void *
0x180042951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042956  jmp     loc_180042D53
0x18004295b  mov     [rsp+140h+var_F8], r14
0x180042960  mov     [rsp+140h+var_100], r14b
0x180042965  mov     rdi, [rsp+140h+var_F0]
0x18004296a  mov     rax, [rdi]
0x18004296d  mov     rbx, [rax+38h]
0x180042971  lea     rcx, [rsp+140h+var_F8]
0x180042976  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004297b  lea     r9, [rsp+140h+var_100]
0x180042980  lea     r8, [rsp+140h+var_F8]
0x180042985  mov     rdx, [rbp+40h+string]
0x180042989  mov     rcx, rdi
0x18004298c  mov     rax, rbx
0x18004298f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042994  mov     ebx, eax
0x180042996  test    eax, eax
0x180042998  jns     short loc_1800429B7
0x18004299a  mov     r9d, eax; char *
0x18004299d  mov     edx, 8Dh; void *
0x1800429a2  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x1800429a9  mov     rcx, [rbp+48h]; this
0x1800429ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800429b2  jmp     loc_180042D48
0x1800429b7  cmp     [rsp+140h+var_100], r14b
0x1800429bc  jnz     short loc_1800429CD
0x1800429be  mov     ebx, 80070057h
0x1800429c3  mov     r9d, ebx
0x1800429c6  mov     edx, 8Eh
0x1800429cb  jmp     short loc_1800429A2
0x1800429cd  mov     [rsp+140h+var_E8], r14
0x1800429d2  mov     rdi, [rsp+140h+var_F8]
0x1800429d7  mov     rax, [rdi]
0x1800429da  mov     rbx, [rax+48h]
0x1800429de  lea     rcx, [rsp+140h+var_E8]
0x1800429e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800429e8  lea     rdx, off_1800D1458; "fields"
0x1800429ef  lea     rcx, [rbp+40h+hstringHeader]
0x1800429f3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800429f8  nop
0x1800429f9  lea     r8, [rsp+140h+var_E8]
0x1800429fe  mov     rdx, [rax+18h]
0x180042a02  mov     rcx, rdi
0x180042a05  mov     rax, rbx
0x180042a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a0d  mov     ebx, eax
0x180042a0f  test    eax, eax
0x180042a11  jns     short loc_180042A30
0x180042a13  mov     rcx, [rbp+48h]; this
0x180042a17  mov     r9d, eax; char *
0x180042a1a  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042a21  mov     edx, 92h; void *
0x180042a26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042a2b  jmp     loc_180042D3D
0x180042a30  mov     [rsp+140h+var_D8], r14
0x180042a35  lea     rdx, [rsp+140h+var_D8]
0x180042a3a  lea     rcx, [rsp+140h+var_E8]
0x180042a3f  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180042a44  mov     ebx, eax
0x180042a46  test    eax, eax
0x180042a48  jns     short loc_180042A67
0x180042a4a  mov     rcx, [rbp+48h]; this
0x180042a4e  mov     r9d, eax; char *
0x180042a51  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042a58  mov     edx, 94h; void *
0x180042a5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042a62  jmp     loc_180042D32
0x180042a67  xorps   xmm0, xmm0
0x180042a6a  xor     eax, eax
0x180042a6c  movups  [rbp+40h+var_58], xmm0
0x180042a70  movups  [rbp+40h+var_48], xmm0
0x180042a74  mov     [rbp+40h+var_38], rax
0x180042a78  mov     [rbp+40h+var_B8], r14d
0x180042a7c  movups  [rbp+40h+var_70], xmm0
0x180042a80  mov     [rbp+40h+var_60], rax
0x180042a84  mov     [rbp+40h+var_B4], r14d
0x180042a88  mov     qword ptr [rbp+40h+hstringHeader.Reserved], rsi
0x180042a8c  lea     rax, [rbp+40h+var_58]
0x180042a90  mov     qword ptr [rbp+40h+hstringHeader.Reserved+8], rax
0x180042a94  lea     rax, [rbp+40h+var_70]
0x180042a98  mov     qword ptr [rbp+40h+hstringHeader.Reserved+10h], rax
0x180042a9c  lea     rax, [rbp+40h+var_B8]
0x180042aa0  mov     [rbp+40h+var_80], rax
0x180042aa4  lea     rax, [rbp+40h+var_B4]
0x180042aa8  mov     [rbp+40h+var_78], rax
0x180042aac  lea     rdx, [rbp+40h+hstringHeader]
0x180042ab0  mov     rcx, [rsp+140h+var_D8]
0x180042ab5  call    ??$IterateOverVector@UIJsonValue@Json@Data@Windows@@V_lambda_3ff8f20150595569f851b45acf98ca6e_@@@@YAJPEAU?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@$$QEAV_lambda_3ff8f20150595569f851b45acf98ca6e_@@@Z; IterateOverVector<Windows::Data::Json::IJsonValue,_lambda_3ff8f20150595569f851b45acf98ca6e_>(Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *> *,_lambda_3ff8f20150595569f851b45acf98ca6e_ &&)
0x180042aba  lea     rax, [rbp+40h+var_58]
0x180042abe  mov     qword ptr [rbp+40h+hstringHeader.Reserved], rax
0x180042ac2  lea     rax, [rbp+40h+var_70]
0x180042ac6  mov     qword ptr [rbp+40h+hstringHeader.Reserved+8], rax
0x180042aca  mov     byte ptr [rbp+40h+hstringHeader.Reserved+10h], 1
0x180042ace  mov     [rsp+140h+var_E0], r14
0x180042ad3  lea     rcx, [rsp+140h+var_E0]
0x180042ad8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042add  lea     r8, [rsp+140h+var_E0]; struct IOOBECheckboxFieldItem **
0x180042ae2  mov     rdx, [rsp+140h+var_F8]; struct Windows::Data::Json::IJsonObject *
0x180042ae7  call    ?_CreateCustomerInfo@OEMRegistrationInfo@@AEAAJPEAUIJsonObject@Json@Data@Windows@@PEAPEAUIOOBECheckboxFieldItem@@@Z; OEMRegistrationInfo::_CreateCustomerInfo(Windows::Data::Json::IJsonObject *,IOOBECheckboxFieldItem * *)
0x180042aec  mov     rcx, [rbp+48h]; this
0x180042af0  test    eax, eax
0x180042af2  jns     short loc_180042B08
0x180042af4  mov     r9d, eax; char *
0x180042af7  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042afe  mov     edx, 0DFh; void *
0x180042b03  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042b08  mov     rcx, rsi; this
0x180042b0b  call    ?_InitializePlugin@OEMRegistrationInfo@@AEAAJXZ; OEMRegistrationInfo::_InitializePlugin(void)
0x180042b10  mov     ebx, eax
0x180042b12  test    eax, eax
0x180042b14  jns     short loc_180042B4D
0x180042b16  mov     rcx, [rbp+48h]; this
0x180042b1a  mov     r9d, eax; char *
0x180042b1d  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042b24  mov     edx, 0E2h; void *
0x180042b29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042b2e  nop
0x180042b2f  lea     rcx, [rsp+140h+var_E0]
0x180042b34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042b39  nop
0x180042b3a  mov     byte ptr [rbp+40h+hstringHeader.Reserved+10h], r14b
0x180042b3e  lea     rcx, [rbp+40h+hstringHeader]
0x180042b42  call    ??R_lambda_cb7e458ee6d0cc43f02cc262a65ec96b_@@QEBA@XZ; _lambda_cb7e458ee6d0cc43f02cc262a65ec96b_::operator()(void)
0x180042b47  nop
0x180042b48  jmp     loc_180042D32
0x180042b4d  mov     [rsp+140h+var_D0], r14
0x180042b52  lea     rcx, [rsi+18h]
0x180042b56  lea     rdx, [rsp+140h+var_D0]
0x180042b5b  call    ??$As@UIOOBEOEMRegistrationPluginPrivate@@@?$ComPtr@UIOOBEOEMRegistrationPlugin@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIOOBEOEMRegistrationPluginPrivate@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IOOBEOEMRegistrationPlugin>::As<IOOBEOEMRegistrationPluginPrivate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IOOBEOEMRegistrationPluginPrivate>>)
0x180042b60  mov     ebx, eax
0x180042b62  test    eax, eax
0x180042b64  jns     short loc_180042BA8
0x180042b66  mov     rcx, [rbp+48h]; this
0x180042b6a  mov     r9d, eax; char *
0x180042b6d  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042b74  mov     edx, 0E4h; void *
0x180042b79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042b7e  nop
0x180042b7f  lea     rcx, [rsp+140h+var_D0]
0x180042b84  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042b89  nop
0x180042b8a  lea     rcx, [rsp+140h+var_E0]
0x180042b8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042b94  nop
0x180042b95  mov     byte ptr [rbp+40h+hstringHeader.Reserved+10h], r14b
0x180042b99  lea     rcx, [rbp+40h+hstringHeader]
0x180042b9d  call    ??R_lambda_cb7e458ee6d0cc43f02cc262a65ec96b_@@QEBA@XZ; _lambda_cb7e458ee6d0cc43f02cc262a65ec96b_::operator()(void)
0x180042ba2  nop
0x180042ba3  jmp     loc_180042D32
0x180042ba8  mov     [rbp+40h+var_B0], r14
0x180042bac  mov     [rbp+40h+var_A8], r14
0x180042bb0  mov     [rbp+40h+var_A0], r14
0x180042bb4  mov     rdi, [rsp+140h+var_D0]
0x180042bb9  mov     rax, [rdi]
0x180042bbc  mov     rbx, [rax+18h]
0x180042bc0  lea     rcx, [rbp+40h+var_B0]
0x180042bc4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042bc9  mov     [rbp+40h+var_A8], r15
0x180042bcd  mov     [rbp+40h+var_A0], r15
0x180042bd1  lea     rdx, [rbp+40h+var_B0]
0x180042bd5  mov     rcx, rdi
0x180042bd8  mov     rax, rbx
0x180042bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042be0  mov     ebx, eax
0x180042be2  test    eax, eax
0x180042be4  jns     short loc_180042C32
0x180042be6  mov     rcx, [rbp+48h]; this
0x180042bea  mov     r9d, eax; char *
0x180042bed  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042bf4  mov     edx, 0E6h; void *
0x180042bf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042bfe  nop
0x180042bff  lea     rcx, [rbp+40h+var_B0]
0x180042c03  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042c08  nop
0x180042c09  lea     rcx, [rsp+140h+var_D0]
0x180042c0e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042c13  nop
0x180042c14  lea     rcx, [rsp+140h+var_E0]
0x180042c19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042c1e  nop
0x180042c1f  mov     byte ptr [rbp+40h+hstringHeader.Reserved+10h], r14b
0x180042c23  lea     rcx, [rbp+40h+hstringHeader]
0x180042c27  call    ??R_lambda_cb7e458ee6d0cc43f02cc262a65ec96b_@@QEBA@XZ; _lambda_cb7e458ee6d0cc43f02cc262a65ec96b_::operator()(void)
0x180042c2c  nop
0x180042c2d  jmp     loc_180042D32
0x180042c32  mov     [rsp+140h+var_C8], r14
0x180042c37  lea     rcx, [rsp+140h+var_C8]
0x180042c3c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042c41  mov     rax, [rbp+40h+var_B0]
0x180042c45  mov     rcx, [rsp+140h+var_E0]
0x180042c4a  lea     rdx, [rsp+140h+var_C8]
0x180042c4f  mov     [rsp+140h+var_110], rdx
0x180042c54  mov     [rsp+140h+var_118], rax
0x180042c59  mov     qword ptr [rsp+140h+bIgnoreCase], rcx; int
0x180042c5e  lea     r8, [rbp+40h+var_70]
0x180042c62  lea     rcx, [rbp+40h+var_58]
0x180042c66  call    CWriteOEMDataTask_CreateInstance
0x180042c6b  mov     ebx, eax
0x180042c6d  test    eax, eax
0x180042c6f  jns     short loc_180042CC5
0x180042c71  mov     rcx, [rbp+48h]; this
0x180042c75  mov     r9d, eax; char *
0x180042c78  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042c7f  mov     edx, 0E9h; void *
0x180042c84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042c89  nop
0x180042c8a  lea     rcx, [rsp+140h+var_C8]
0x180042c8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042c94  nop
0x180042c95  lea     rcx, [rbp+40h+var_B0]
0x180042c99  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042c9e  nop
0x180042c9f  lea     rcx, [rsp+140h+var_D0]
0x180042ca4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042ca9  nop
0x180042caa  lea     rcx, [rsp+140h+var_E0]
0x180042caf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042cb4  nop
0x180042cb5  mov     byte ptr [rbp+40h+hstringHeader.Reserved+10h], r14b
0x180042cb9  lea     rcx, [rbp+40h+hstringHeader]
0x180042cbd  call    ??R_lambda_cb7e458ee6d0cc43f02cc262a65ec96b_@@QEBA@XZ; _lambda_cb7e458ee6d0cc43f02cc262a65ec96b_::operator()(void)
0x180042cc2  nop
0x180042cc3  jmp     short loc_180042D32
0x180042cc5  mov     rcx, [rsp+140h+var_C8]
0x180042cca  mov     rax, [rcx]
0x180042ccd  mov     rax, [rax+20h]
  ... truncated ...
```
