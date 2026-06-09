# OEMRegistrationInfo::Retrieve(ushort * *)

- ea: `0x180042310`
- end: `0x180042761`
- name: `?Retrieve@OEMRegistrationInfo@@UEAAJPEAPEAG@Z`
- size: `1105`
- prototype: `__int64 __fastcall(OEMRegistrationInfo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003470`
- `0x180007bbc`
- `0x180008544`
- `0x18000b358`
- `0x180019a38`
- `0x1800230b0`
- `0x180040a48`
- `0x180040ad0`
- `0x1800418d8`
- `0x180042068`
- `0x180042310`
- `0x180042e28`
- `0x180042f00`
- `0x1800432ac`
- `0x1800435fc`
- `0x180043974`
- `0x180043c58`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800426cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800426cd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800423fe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800423fe`

## string_xrefs

- `0x18004235a`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x1800423ae`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042411`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042475`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042500`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042584`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x1800425cd`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x1800425f9`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042625`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042654`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x1800426a8`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180042384`: `Windows.Data.Json.JsonObject`
- `0x1800423d3`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OEMRegistrationInfo::Retrieve(OEMRegistrationInfo *this, unsigned __int16 **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rbx
  int ActivationFactory; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, unsigned __int16 **); // rbx
  size_t v11; // rsi
  int v12; // eax
  OEMRegistrationInfo *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, unsigned __int16 **); // rbx
  int v17; // eax
  OEMRegistrationInfo *v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  OEMRegistrationInfo *v21; // rcx
  int v22; // eax
  int v23; // eax
  OEMRegistrationInfo *v24; // rcx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING *); // rbx
  int v31; // eax
  __int64 v32; // rdx
  const wchar_t *StringRawBuffer; // rax
  __int64 v34; // rdx
  unsigned __int64 v35; // rcx
  int v37; // [rsp+20h] [rbp-59h]
  int v38; // [rsp+20h] [rbp-59h]
  unsigned __int16 *v39; // [rsp+20h] [rbp-59h]
  struct Windows::Data::Json::IJsonValueStatics *v40; // [rsp+30h] [rbp-49h] BYREF
  struct Windows::Data::Json::IJsonObject *v41; // [rsp+38h] [rbp-41h] BYREF
  HSTRING string; // [rsp+40h] [rbp-39h] BYREF
  __int64 v43; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v44; // [rsp+50h] [rbp-29h] BYREF
  __int64 v45; // [rsp+58h] [rbp-21h]
  __int64 v46; // [rsp+60h] [rbp-19h]
  unsigned __int16 *v47; // [rsp+68h] [rbp-11h] BYREF
  __int64 v48; // [rsp+70h] [rbp-9h]
  __int64 v49; // [rsp+78h] [rbp-1h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  __int64 v51; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = 0;
  v4 = OEMRegistrationInfo::_InitializePlugin(this);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v41 = 0;
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v51, &v41);
    v5 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)v6,
        v37);
LABEL_39:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      return v5;
    }
    v40 = 0;
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    v7 = v51;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    ActivationFactory = RoGetActivationFactory(v7, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v40);
    v5 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v37);
LABEL_7:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      goto LABEL_39;
    }
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v9 = *((_QWORD *)this + 3);
    v10 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v9 + 24LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v44);
    v11 = -1;
    v45 = -1;
    v46 = -1;
    v12 = v10(v9, &v44);
    v5 = v12;
    if ( v12 < 0 )
    {
      v14 = 72;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
        (const char *)(unsigned int)v12,
        v37);
LABEL_11:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v44);
      goto LABEL_7;
    }
    v12 = OEMRegistrationInfo::_AddStringValue(v13, v41, v40, L"title", v44);
    v5 = v12;
    if ( v12 < 0 )
    {
      v14 = 73;
      goto LABEL_10;
    }
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v15 = *((_QWORD *)this + 3);
    v16 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v15 + 32LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
    v48 = -1;
    v49 = -1;
    v17 = v16(v15, &v47);
    v5 = v17;
    if ( v17 >= 0 )
    {
      v17 = OEMRegistrationInfo::_AddStringValue(v18, v41, v40, L"subtitle", v47);
      v5 = v17;
      if ( v17 >= 0 )
      {
        v20 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 72LL))(*((_QWORD *)this + 3));
        v22 = OEMRegistrationInfo::_AddBooleanValue(v21, v41, v40, L"hideskip", v20 == 0);
        if ( v22 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x51,
            (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
            (const char *)(unsigned int)v22,
            v38);
        v23 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 80LL))(*((_QWORD *)this + 3));
        v25 = OEMRegistrationInfo::_AddBooleanValue(v24, v41, v40, L"showphonenumber", v23 == 0);
        if ( v25 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x54,
            (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
            (const char *)(unsigned int)v25,
            (int)v39);
        v26 = OEMRegistrationInfo::_AddCustomerInfo(this, v40, v41);
        if ( v26 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x57,
            (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
            (const char *)(unsigned int)v26,
            (int)v39);
        v27 = OEMRegistrationInfo::_AddCheckBoxAndLinkFields(this, v40, v41);
        if ( v27 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5A,
            (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
            (const char *)(unsigned int)v27,
            (int)v39);
        v43 = 0;
        v28 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
                (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v41,
                (__int64)&v43);
        v5 = v28;
        if ( v28 >= 0 )
        {
          string = 0;
          v29 = v43;
          v30 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 56LL);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
            &string,
            0);
          v31 = v30(v29, &string);
          v5 = v31;
          if ( v31 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            do
              ++v11;
            while ( StringRawBuffer[v11] );
            v31 = _AllocStringWorker<CTCoAllocPolicy>(v35, v34, StringRawBuffer, v11, (__int64)v39, (void **)a2);
            v5 = v31;
            if ( v31 >= 0 )
            {
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v44);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
              v5 = 0;
              goto LABEL_39;
            }
            v32 = 97;
          }
          else
          {
            v32 = 96;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v32,
            (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
            (const char *)(unsigned int)v31,
            (int)v39);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5E,
            (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
            (const char *)(unsigned int)v28,
            (int)v39);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        goto LABEL_17;
      }
      v19 = 78;
    }
    else
    {
      v19 = 77;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
      (const char *)(unsigned int)v17,
      v37);
LABEL_17:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3E,
    (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
    (const char *)(unsigned int)v4,
    v37);
  return v5;
}

```

## disassembly

```asm
0x180042310  mov     [rsp-8+arg_10], rbx
0x180042315  mov     [rsp-8+arg_18], rsi
0x18004231a  push    rbp
0x18004231b  push    rdi
0x18004231c  push    r12
0x18004231e  push    r14
0x180042320  push    r15
0x180042322  lea     rbp, [rsp-37h]
0x180042327  sub     rsp, 0B0h
0x18004232e  mov     rax, cs:__security_cookie
0x180042335  xor     rax, rsp
0x180042338  mov     [rbp+57h+var_30], rax
0x18004233c  mov     r15, rdx
0x18004233f  mov     r14, rcx
0x180042342  xor     r12d, r12d
0x180042345  mov     [rdx], r12
0x180042348  call    ?_InitializePlugin@OEMRegistrationInfo@@AEAAJXZ; OEMRegistrationInfo::_InitializePlugin(void)
0x18004234d  mov     ebx, eax
0x18004234f  test    eax, eax
0x180042351  jns     short loc_180042370
0x180042353  mov     rcx, [rbp+5Fh]; this
0x180042357  mov     r9d, eax; char *
0x18004235a  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042361  lea     edx, [r12+3Eh]; void *
0x180042366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004236b  jmp     loc_180042737
0x180042370  mov     [rbp+57h+var_98], r12
0x180042374  mov     [rbp+57h+var_38], r12
0x180042378  mov     edi, 1Ch
0x18004237d  mov     r9d, edi; unsigned int
0x180042380  lea     r8d, [rdi+1]; unsigned int
0x180042384  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18004238b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004238f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180042394  lea     rdx, [rbp+57h+var_98]
0x180042398  mov     rcx, [rbp+57h+var_38]
0x18004239c  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800423a1  mov     ebx, eax
0x1800423a3  test    eax, eax
0x1800423a5  jns     short loc_1800423C2
0x1800423a7  mov     rcx, [rbp+5Fh]; this
0x1800423ab  mov     r9d, eax; char *
0x1800423ae  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x1800423b5  lea     edx, [rdi+26h]; void *
0x1800423b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800423bd  jmp     loc_18004272E
0x1800423c2  mov     [rbp+57h+var_A0], r12
0x1800423c6  mov     [rbp+57h+var_38], r12
0x1800423ca  mov     r9d, 1Bh; unsigned int
0x1800423d0  mov     r8d, edi; unsigned int
0x1800423d3  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800423da  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800423de  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800423e3  mov     rbx, [rbp+57h+var_38]
0x1800423e7  lea     rcx, [rbp+57h+var_A0]
0x1800423eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800423f0  lea     r8, [rbp+57h+var_A0]
0x1800423f4  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800423fb  mov     rcx, rbx
0x1800423fe  call    cs:__imp_RoGetActivationFactory
0x180042404  mov     ebx, eax
0x180042406  test    eax, eax
0x180042408  jns     short loc_180042431
0x18004240a  mov     rcx, [rbp+5Fh]; this
0x18004240e  mov     r9d, eax; char *
0x180042411  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042418  mov     edx, 44h ; 'D'; void *
0x18004241d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042422  nop
0x180042423  lea     rcx, [rbp+57h+var_A0]
0x180042427  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004242c  jmp     loc_18004272E
0x180042431  mov     [rbp+57h+var_80], r12
0x180042435  mov     [rbp+57h+var_78], r12
0x180042439  mov     [rbp+57h+var_70], r12
0x18004243d  mov     rdi, [r14+18h]
0x180042441  mov     rax, [rdi]
0x180042444  mov     rbx, [rax+18h]
0x180042448  lea     rcx, [rbp+57h+var_80]
0x18004244c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042451  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180042455  mov     [rbp+57h+var_78], rsi
0x180042459  mov     [rbp+57h+var_70], rsi
0x18004245d  lea     rdx, [rbp+57h+var_80]
0x180042461  mov     rcx, rdi
0x180042464  mov     rax, rbx
0x180042467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004246c  mov     ebx, eax
0x18004246e  test    eax, eax
0x180042470  jns     short loc_180042494
0x180042472  lea     edx, [rsi+49h]; void *
0x180042475  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x18004247c  mov     r9d, eax; char *
0x18004247f  mov     rcx, [rbp+5Fh]; this
0x180042483  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042488  nop
0x180042489  lea     rcx, [rbp+57h+var_80]
0x18004248d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042492  jmp     short loc_180042423
0x180042494  mov     rax, [rbp+57h+var_80]
0x180042498  mov     [rsp+0D0h+var_B0], rax; int
0x18004249d  lea     r9, aTitle; "title"
0x1800424a4  mov     r8, [rbp+57h+var_A0]; struct Windows::Data::Json::IJsonValueStatics *
0x1800424a8  mov     rdx, [rbp+57h+var_98]; struct Windows::Data::Json::IJsonObject *
0x1800424ac  call    ?_AddStringValue@OEMRegistrationInfo@@AEAAJPEAUIJsonObject@Json@Data@Windows@@PEAUIJsonValueStatics@345@PEBG2@Z; OEMRegistrationInfo::_AddStringValue(Windows::Data::Json::IJsonObject *,Windows::Data::Json::IJsonValueStatics *,ushort const *,ushort const *)
0x1800424b1  mov     ebx, eax
0x1800424b3  test    eax, eax
0x1800424b5  jns     short loc_1800424BE
0x1800424b7  mov     edx, 49h ; 'I'
0x1800424bc  jmp     short loc_180042475
0x1800424be  mov     [rbp+57h+var_68], r12
0x1800424c2  mov     [rbp+57h+var_60], r12
0x1800424c6  mov     [rbp+57h+var_58], r12
0x1800424ca  mov     rdi, [r14+18h]
0x1800424ce  mov     rax, [rdi]
0x1800424d1  mov     rbx, [rax+20h]
0x1800424d5  lea     rcx, [rbp+57h+var_68]
0x1800424d9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800424de  mov     [rbp+57h+var_60], rsi
0x1800424e2  mov     [rbp+57h+var_58], rsi
0x1800424e6  lea     rdx, [rbp+57h+var_68]
0x1800424ea  mov     rcx, rdi
0x1800424ed  mov     rax, rbx
0x1800424f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424f5  mov     ebx, eax
0x1800424f7  test    eax, eax
0x1800424f9  jns     short loc_180042522
0x1800424fb  mov     edx, 4Dh ; 'M'; void *
0x180042500  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042507  mov     r9d, eax; char *
0x18004250a  mov     rcx, [rbp+5Fh]; this
0x18004250e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042513  nop
0x180042514  lea     rcx, [rbp+57h+var_68]
0x180042518  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004251d  jmp     loc_180042489
0x180042522  mov     rax, [rbp+57h+var_68]
0x180042526  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x18004252b  lea     r9, aSubtitle; "subtitle"
0x180042532  mov     r8, [rbp+57h+var_A0]; struct Windows::Data::Json::IJsonValueStatics *
0x180042536  mov     rdx, [rbp+57h+var_98]; struct Windows::Data::Json::IJsonObject *
0x18004253a  call    ?_AddStringValue@OEMRegistrationInfo@@AEAAJPEAUIJsonObject@Json@Data@Windows@@PEAUIJsonValueStatics@345@PEBG2@Z; OEMRegistrationInfo::_AddStringValue(Windows::Data::Json::IJsonObject *,Windows::Data::Json::IJsonValueStatics *,ushort const *,ushort const *)
0x18004253f  mov     ebx, eax
0x180042541  test    eax, eax
0x180042543  jns     short loc_18004254C
0x180042545  mov     edx, 4Eh ; 'N'
0x18004254a  jmp     short loc_180042500
0x18004254c  mov     rcx, [r14+18h]
0x180042550  mov     rax, [rcx]
0x180042553  mov     rax, [rax+48h]
0x180042557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004255c  test    eax, eax
0x18004255e  setz    al
0x180042561  mov     byte ptr [rsp+0D0h+var_B0], al; int
0x180042565  lea     r9, aHideskip; "hideskip"
0x18004256c  mov     r8, [rbp+57h+var_A0]; struct Windows::Data::Json::IJsonValueStatics *
0x180042570  mov     rdx, [rbp+57h+var_98]; struct Windows::Data::Json::IJsonObject *
0x180042574  call    ?_AddBooleanValue@OEMRegistrationInfo@@AEAAJPEAUIJsonObject@Json@Data@Windows@@PEAUIJsonValueStatics@345@PEBG_N@Z; OEMRegistrationInfo::_AddBooleanValue(Windows::Data::Json::IJsonObject *,Windows::Data::Json::IJsonValueStatics *,ushort const *,bool)
0x180042579  mov     rcx, [rbp+5Fh]; this
0x18004257d  test    eax, eax
0x18004257f  jns     short loc_180042595
0x180042581  mov     r9d, eax; char *
0x180042584  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x18004258b  mov     edx, 51h ; 'Q'; void *
0x180042590  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042595  mov     rcx, [r14+18h]
0x180042599  mov     rax, [rcx]
0x18004259c  mov     rax, [rax+50h]
0x1800425a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425a5  test    eax, eax
0x1800425a7  setz    al
0x1800425aa  mov     byte ptr [rsp+0D0h+var_B0], al; int
0x1800425ae  lea     r9, aShowphonenumbe; "showphonenumber"
0x1800425b5  mov     r8, [rbp+57h+var_A0]; struct Windows::Data::Json::IJsonValueStatics *
0x1800425b9  mov     rdx, [rbp+57h+var_98]; struct Windows::Data::Json::IJsonObject *
0x1800425bd  call    ?_AddBooleanValue@OEMRegistrationInfo@@AEAAJPEAUIJsonObject@Json@Data@Windows@@PEAUIJsonValueStatics@345@PEBG_N@Z; OEMRegistrationInfo::_AddBooleanValue(Windows::Data::Json::IJsonObject *,Windows::Data::Json::IJsonValueStatics *,ushort const *,bool)
0x1800425c2  mov     rcx, [rbp+5Fh]; this
0x1800425c6  test    eax, eax
0x1800425c8  jns     short loc_1800425DE
0x1800425ca  mov     r9d, eax; char *
0x1800425cd  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x1800425d4  mov     edx, 54h ; 'T'; void *
0x1800425d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800425de  mov     r8, [rbp+57h+var_98]; struct Windows::Data::Json::IJsonObject *
0x1800425e2  mov     rdx, [rbp+57h+var_A0]; struct Windows::Data::Json::IJsonValueStatics *
0x1800425e6  mov     rcx, r14; this
0x1800425e9  call    ?_AddCustomerInfo@OEMRegistrationInfo@@AEAAJPEAUIJsonValueStatics@Json@Data@Windows@@PEAUIJsonObject@345@@Z; OEMRegistrationInfo::_AddCustomerInfo(Windows::Data::Json::IJsonValueStatics *,Windows::Data::Json::IJsonObject *)
0x1800425ee  mov     rcx, [rbp+5Fh]; this
0x1800425f2  test    eax, eax
0x1800425f4  jns     short loc_18004260A
0x1800425f6  mov     r9d, eax; char *
0x1800425f9  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180042600  mov     edx, 57h ; 'W'; void *
0x180042605  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004260a  mov     r8, [rbp+57h+var_98]; struct Windows::Data::Json::IJsonObject *
0x18004260e  mov     rdx, [rbp+57h+var_A0]; struct Windows::Data::Json::IJsonValueStatics *
0x180042612  mov     rcx, r14; this
0x180042615  call    ?_AddCheckBoxAndLinkFields@OEMRegistrationInfo@@AEAAJPEAUIJsonValueStatics@Json@Data@Windows@@PEAUIJsonObject@345@@Z; OEMRegistrationInfo::_AddCheckBoxAndLinkFields(Windows::Data::Json::IJsonValueStatics *,Windows::Data::Json::IJsonObject *)
0x18004261a  mov     rcx, [rbp+5Fh]; this
0x18004261e  test    eax, eax
0x180042620  jns     short loc_180042636
0x180042622  mov     r9d, eax; char *
0x180042625  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x18004262c  mov     edx, 5Ah ; 'Z'; void *
0x180042631  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042636  mov     [rbp+57h+var_88], r12
0x18004263a  lea     rdx, [rbp+57h+var_88]
0x18004263e  lea     rcx, [rbp+57h+var_98]
0x180042642  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180042647  mov     ebx, eax
0x180042649  test    eax, eax
0x18004264b  jns     short loc_180042674
0x18004264d  mov     rcx, [rbp+5Fh]; this
0x180042651  mov     r9d, eax; char *
0x180042654  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x18004265b  mov     edx, 5Eh ; '^'; void *
0x180042660  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042665  nop
0x180042666  lea     rcx, [rbp+57h+var_88]
0x18004266a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004266f  jmp     loc_180042514
0x180042674  mov     [rbp+57h+string], r12
0x180042678  mov     rdi, [rbp+57h+var_88]
0x18004267c  mov     rax, [rdi]
0x18004267f  mov     rbx, [rax+38h]
0x180042683  xor     edx, edx
0x180042685  lea     rcx, [rbp+57h+string]
0x180042689  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18004268e  lea     rdx, [rbp+57h+string]
0x180042692  mov     rcx, rdi
0x180042695  mov     rax, rbx
0x180042698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004269d  mov     ebx, eax
0x18004269f  test    eax, eax
0x1800426a1  jns     short loc_1800426C7
0x1800426a3  mov     edx, 60h ; '`'; void *
0x1800426a8  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x1800426af  mov     r9d, eax; char *
0x1800426b2  mov     rcx, [rbp+5Fh]; this
0x1800426b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800426bb  nop
0x1800426bc  lea     rcx, [rbp+57h+string]; this
0x1800426c0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800426c5  jmp     short loc_180042666
0x1800426c7  xor     edx, edx; length
0x1800426c9  mov     rcx, [rbp+57h+string]; string
0x1800426cd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800426d3  inc     rsi
0x1800426d6  cmp     [rax+rsi*2], r12w
0x1800426db  jnz     short loc_1800426D3
0x1800426dd  mov     [rsp+0D0h+var_A8], r15
0x1800426e2  mov     r9, rsi
0x1800426e5  mov     r8, rax
0x1800426e8  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800426ed  mov     ebx, eax
0x1800426ef  test    eax, eax
0x1800426f1  jns     short loc_1800426FA
0x1800426f3  mov     edx, 61h ; 'a'
0x1800426f8  jmp     short loc_1800426A8
0x1800426fa  lea     rcx, [rbp+57h+string]; this
0x1800426fe  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180042703  nop
0x180042704  lea     rcx, [rbp+57h+var_88]
0x180042708  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004270d  nop
0x18004270e  lea     rcx, [rbp+57h+var_68]
0x180042712  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042717  nop
0x180042718  lea     rcx, [rbp+57h+var_80]
0x18004271c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042721  nop
0x180042722  lea     rcx, [rbp+57h+var_A0]
0x180042726  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004272b  mov     ebx, r12d
0x18004272e  lea     rcx, [rbp+57h+var_98]
0x180042732  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042737  mov     eax, ebx
0x180042739  mov     rcx, [rbp+57h+var_30]
0x18004273d  xor     rcx, rsp; StackCookie
0x180042740  call    __security_check_cookie
0x180042745  lea     r11, [rsp+0D0h+var_20]
0x18004274d  mov     rbx, [r11+40h]
0x180042751  mov     rsi, [r11+48h]
0x180042755  mov     rsp, r11
0x180042758  pop     r15
0x18004275a  pop     r14
0x18004275c  pop     r12
0x18004275e  pop     rdi
0x18004275f  pop     rbp
0x180042760  retn
```
