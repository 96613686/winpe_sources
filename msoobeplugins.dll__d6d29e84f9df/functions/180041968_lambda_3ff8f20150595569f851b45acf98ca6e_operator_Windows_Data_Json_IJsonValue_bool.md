# _lambda_3ff8f20150595569f851b45acf98ca6e_::operator()(Windows::Data::Json::IJsonValue *,bool *)

- ea: `0x180041968`
- end: `0x180041dc0`
- name: `??R_lambda_3ff8f20150595569f851b45acf98ca6e_@@QEBAJPEAUIJsonValue@Json@Data@Windows@@PEA_N@Z`
- size: `1112`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180040bf4`

## callees

- `0x180003470`
- `0x180007bbc`
- `0x180008544`
- `0x18001a46c`
- `0x180040898`
- `0x1800418d8`
- `0x180041968`
- `0x1800436ec`
- `0x180043c58`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041aca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041b91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041aca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041b91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041aaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041afd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041b74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041bc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041c72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041aaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041afd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041b74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041bc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041c72`

## string_xrefs

- `0x1800419c4`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180041a29`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180041a8e`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180041b20`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180041be5`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180041c48`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`
- `0x180041ccd`: `shell\oobe\machine\plugins\oemregistration\oemregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall _lambda_3ff8f20150595569f851b45acf98ca6e_::operator()(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, struct Windows::Data::Json::IJsonObject **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  struct Windows::Data::Json::IJsonObject *v7; // rdi
  __int64 (__fastcall *v8)(struct Windows::Data::Json::IJsonObject *, PVOID, HSTRING *); // rbx
  char v9; // r8
  HSTRING_HEADER *v10; // rax
  int v11; // eax
  struct Windows::Data::Json::IJsonObject *v12; // rdi
  __int64 (__fastcall *v13)(struct Windows::Data::Json::IJsonObject *, PVOID, HSTRING *); // rbx
  char v14; // r8
  HSTRING_HEADER *v15; // rax
  int v16; // eax
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v18; // rax
  OEMRegistrationInfo *v19; // rcx
  int v20; // eax
  struct IOOBECheckboxFieldItem *v21; // rdx
  const WCHAR *v22; // rax
  const unsigned __int16 *v23; // rax
  int v24; // eax
  struct Windows::Data::Json::IJsonObject *v25; // rdi
  __int64 (__fastcall *v26)(struct Windows::Data::Json::IJsonObject *, PVOID, HSTRING *); // rbx
  char v27; // r8
  HSTRING_HEADER *v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  struct CTextboxField *v31; // rdi
  __int64 (__fastcall *v32)(char *, PCWSTR); // rbx
  PCWSTR v33; // rax
  int v34; // eax
  __int64 v36; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-29h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-29h]
  BOOL bIgnoreCaseb; // [rsp+20h] [rbp-29h]
  HSTRING v40; // [rsp+30h] [rbp-19h] BYREF
  HSTRING string; // [rsp+38h] [rbp-11h] BYREF
  struct CTextboxField *v42; // [rsp+40h] [rbp-9h] BYREF
  struct Windows::Data::Json::IJsonObject *v43; // [rsp+48h] [rbp-1h] BYREF
  HSTRING v44; // [rsp+50h] [rbp+7h] BYREF
  struct IOOBECheckboxFieldItem *v45; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v46; // [rsp+60h] [rbp+17h] BYREF
  HSTRING_HEADER v47; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v43 = 0;
  v4 = *(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonObject **))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  v5 = v4(a2, &v43);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
LABEL_27:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    return v6;
  }
  v40 = 0;
  v7 = v43;
  v8 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, HSTRING *))(*(_QWORD *)v43 + 80LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v40,
    0);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v47, (const WCHAR **)off_1800D1450, v9);
  v11 = v8(v7, v10[1].Reserved.Reserved1, &v40);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
LABEL_26:
    Windows::Internal::String::~String((Windows::Internal::String *)&v40);
    goto LABEL_27;
  }
  string = 0;
  v12 = v43;
  v13 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, HSTRING *))(*(_QWORD *)v43 + 80LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &string,
    0);
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v47, (const WCHAR **)off_1800D1440, v14);
  v16 = v13(v12, v15[1].Reserved.Reserved1, &string);
  v6 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
      (const char *)(unsigned int)v16,
      bIgnoreCase);
LABEL_25:
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    goto LABEL_26;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"checkbox", -1, 1) == 2 )
  {
    if ( **(_DWORD **)(a1 + 32) < 3u )
    {
      v45 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      v18 = WindowsGetStringRawBuffer(v40, 0);
      v20 = OEMRegistrationInfo::_CreateCheckBoxItem(v19, v43, v18, &v45);
      v6 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB0,
          (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
          (const char *)(unsigned int)v20,
          bIgnoreCasea);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        goto LABEL_25;
      }
      v21 = v45;
      v45 = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL * (unsigned int)(**(_DWORD **)(a1 + 32))++) = v21;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    }
    goto LABEL_29;
  }
  v22 = WindowsGetStringRawBuffer(string, 0);
  if ( CompareStringOrdinal(v22, -1, L"textbox", -1, 1) == 2 )
  {
    if ( **(_DWORD **)(a1 + 24) < 5u )
    {
      v42 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      v23 = WindowsGetStringRawBuffer(v40, 0);
      v24 = CTextboxField::s_Create(v23, IS_DEFAULT, &v42);
      v6 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB9,
          (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
          (const char *)(unsigned int)v24,
          bIgnoreCaseb);
LABEL_24:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
        goto LABEL_25;
      }
      v44 = 0;
      v25 = v43;
      v26 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, HSTRING *))(*(_QWORD *)v43 + 80LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v44,
        0);
      v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v47, (const WCHAR **)off_1800D1448, v27);
      v29 = v26(v25, v28[1].Reserved.Reserved1, &v44);
      v6 = v29;
      if ( v29 < 0 )
      {
        v30 = 187;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
          (const char *)(unsigned int)v29,
          bIgnoreCaseb);
LABEL_23:
        Windows::Internal::String::~String((Windows::Internal::String *)&v44);
        goto LABEL_24;
      }
      v31 = v42;
      v32 = *(__int64 (__fastcall **)(char *, PCWSTR))(*((_QWORD *)v42 + 3) + 48LL);
      v33 = WindowsGetStringRawBuffer(v44, 0);
      v29 = v32((char *)v31 + 24, v33);
      v6 = v29;
      if ( v29 < 0 )
      {
        v30 = 188;
        goto LABEL_18;
      }
      v46 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      v34 = (**(__int64 (__fastcall ***)(struct CTextboxField *, GUID *, __int64 *))v42)(
              v42,
              &GUID_806925ad_98e5_4e7a_8200_6b83f9f8e52d,
              &v46);
      v6 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"shell\\oobe\\machine\\plugins\\oemregistration\\oemregistration.cpp",
          (const char *)(unsigned int)v34,
          bIgnoreCaseb);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        goto LABEL_23;
      }
      v36 = v46;
      v46 = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * (unsigned int)(**(_DWORD **)(a1 + 24))++) = v36;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      Windows::Internal::String::~String((Windows::Internal::String *)&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    }
LABEL_29:
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Windows::Internal::String::~String((Windows::Internal::String *)&v40);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    return 0;
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  Windows::Internal::String::~String((Windows::Internal::String *)&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180041968  mov     [rsp-8+arg_10], rbx
0x18004196d  push    rbp
0x18004196e  push    rsi
0x18004196f  push    rdi
0x180041970  lea     rbp, [rsp-47h]
0x180041975  sub     rsp, 90h
0x18004197c  mov     rax, cs:__security_cookie
0x180041983  xor     rax, rsp
0x180041986  mov     [rbp+57h+var_18], rax
0x18004198a  mov     rdi, rdx
0x18004198d  mov     rsi, rcx
0x180041990  mov     [rbp+57h+var_58], 0
0x180041998  mov     rax, [rdx]
0x18004199b  mov     rbx, [rax+60h]
0x18004199f  lea     rcx, [rbp+57h+var_58]
0x1800419a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800419a8  lea     rdx, [rbp+57h+var_58]
0x1800419ac  mov     rcx, rdi
0x1800419af  mov     rax, rbx
0x1800419b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419b7  mov     ebx, eax
0x1800419b9  test    eax, eax
0x1800419bb  jns     short loc_1800419DA
0x1800419bd  mov     rcx, [rbp+5Fh]; this
0x1800419c1  mov     r9d, eax; char *
0x1800419c4  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x1800419cb  mov     edx, 0A0h; void *
0x1800419d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800419d5  jmp     loc_180041D10
0x1800419da  mov     [rbp+57h+var_70], 0
0x1800419e2  mov     rdi, [rbp+57h+var_58]
0x1800419e6  mov     rax, [rdi]
0x1800419e9  mov     rbx, [rax+50h]
0x1800419ed  xor     edx, edx
0x1800419ef  lea     rcx, [rbp+57h+var_70]
0x1800419f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800419f8  lea     rdx, off_1800D1450; "label"
0x1800419ff  lea     rcx, [rbp+57h+var_38]
0x180041a03  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180041a08  nop
0x180041a09  lea     r8, [rbp+57h+var_70]
0x180041a0d  mov     rdx, [rax+18h]
0x180041a11  mov     rcx, rdi
0x180041a14  mov     rax, rbx
0x180041a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a1c  mov     ebx, eax
0x180041a1e  test    eax, eax
0x180041a20  jns     short loc_180041A3F
0x180041a22  mov     rcx, [rbp+5Fh]; this
0x180041a26  mov     r9d, eax; char *
0x180041a29  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180041a30  mov     edx, 0A4h; void *
0x180041a35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041a3a  jmp     loc_180041D06
0x180041a3f  mov     [rbp+57h+string], 0
0x180041a47  mov     rdi, [rbp+57h+var_58]
0x180041a4b  mov     rax, [rdi]
0x180041a4e  mov     rbx, [rax+50h]
0x180041a52  xor     edx, edx
0x180041a54  lea     rcx, [rbp+57h+string]
0x180041a58  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180041a5d  lea     rdx, off_1800D1440; "type"
0x180041a64  lea     rcx, [rbp+57h+var_38]
0x180041a68  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180041a6d  nop
0x180041a6e  lea     r8, [rbp+57h+string]
0x180041a72  mov     rdx, [rax+18h]
0x180041a76  mov     rcx, rdi
0x180041a79  mov     rax, rbx
0x180041a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a81  mov     ebx, eax
0x180041a83  test    eax, eax
0x180041a85  jns     short loc_180041AA4
0x180041a87  mov     rcx, [rbp+5Fh]; this
0x180041a8b  mov     r9d, eax; char *
0x180041a8e  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180041a95  mov     edx, 0A8h; void *
0x180041a9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041a9f  jmp     loc_180041CFC
0x180041aa4  xor     edx, edx; length
0x180041aa6  mov     rcx, [rbp+57h+string]; string
0x180041aaa  call    cs:__imp_WindowsGetStringRawBuffer
0x180041ab0  mov     [rsp+0A0h+bIgnoreCase], 1; int
0x180041ab8  or      ebx, 0FFFFFFFFh
0x180041abb  mov     r9d, ebx; cchCount2
0x180041abe  lea     r8, aCheckbox; "checkbox"
0x180041ac5  mov     edx, ebx; cchCount1
0x180041ac7  mov     rcx, rax; lpString1
0x180041aca  call    cs:__imp_CompareStringOrdinal
0x180041ad0  cmp     eax, 2
0x180041ad3  jnz     loc_180041B6E
0x180041ad9  mov     rax, [rsi+20h]
0x180041add  cmp     dword ptr [rax], 3
0x180041ae0  jnb     loc_180041D5E
0x180041ae6  mov     [rbp+57h+var_48], 0
0x180041aee  lea     rcx, [rbp+57h+var_48]
0x180041af2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041af7  xor     edx, edx; length
0x180041af9  mov     rcx, [rbp+57h+var_70]; string
0x180041afd  call    cs:__imp_WindowsGetStringRawBuffer
0x180041b03  lea     r9, [rbp+57h+var_48]; struct IOOBECheckboxFieldItem **
0x180041b07  mov     r8, rax; unsigned __int16 *
0x180041b0a  mov     rdx, [rbp+57h+var_58]; struct Windows::Data::Json::IJsonObject *
0x180041b0e  call    ?_CreateCheckBoxItem@OEMRegistrationInfo@@AEAAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAPEAUIOOBECheckboxFieldItem@@@Z; OEMRegistrationInfo::_CreateCheckBoxItem(Windows::Data::Json::IJsonObject *,ushort const *,IOOBECheckboxFieldItem * *)
0x180041b13  mov     ebx, eax
0x180041b15  test    eax, eax
0x180041b17  jns     short loc_180041B40
0x180041b19  mov     rcx, [rbp+5Fh]; this
0x180041b1d  mov     r9d, eax; char *
0x180041b20  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180041b27  mov     edx, 0B0h; void *
0x180041b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041b31  nop
0x180041b32  lea     rcx, [rbp+57h+var_48]
0x180041b36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041b3b  jmp     loc_180041CFC
0x180041b40  mov     rdx, [rbp+57h+var_48]
0x180041b44  mov     [rbp+57h+var_48], 0
0x180041b4c  mov     rax, [rsi+20h]
0x180041b50  mov     ecx, [rax]
0x180041b52  mov     rax, [rsi+10h]
0x180041b56  mov     [rax+rcx*8], rdx
0x180041b5a  mov     rax, [rsi+20h]
0x180041b5e  inc     dword ptr [rax]
0x180041b60  lea     rcx, [rbp+57h+var_48]
0x180041b64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041b69  jmp     loc_180041D5E
0x180041b6e  xor     edx, edx; length
0x180041b70  mov     rcx, [rbp+57h+string]; string
0x180041b74  call    cs:__imp_WindowsGetStringRawBuffer
0x180041b7a  mov     [rsp+0A0h+bIgnoreCase], 1; int
0x180041b82  mov     r9d, ebx; cchCount2
0x180041b85  lea     r8, aTextbox; "textbox"
0x180041b8c  mov     edx, ebx; cchCount1
0x180041b8e  mov     rcx, rax; lpString1
0x180041b91  call    cs:__imp_CompareStringOrdinal
0x180041b97  cmp     eax, 2
0x180041b9a  jnz     loc_180041D7F
0x180041ba0  mov     rax, [rsi+18h]
0x180041ba4  cmp     dword ptr [rax], 5
0x180041ba7  jnb     loc_180041D5E
0x180041bad  mov     [rbp+57h+var_60], 0
0x180041bb5  lea     rcx, [rbp+57h+var_60]
0x180041bb9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041bbe  xor     edx, edx; length
0x180041bc0  mov     rcx, [rbp+57h+var_70]; string
0x180041bc4  call    cs:__imp_WindowsGetStringRawBuffer
0x180041bca  lea     r8, [rbp+57h+var_60]; struct CTextboxField **
0x180041bce  xor     edx, edx; enum __MIDL___MIDL_itf_inputscope_0000_0000_0001
0x180041bd0  mov     rcx, rax; unsigned __int16 *
0x180041bd3  call    ?s_Create@CTextboxField@@SAJPEBGW4__MIDL___MIDL_itf_inputscope_0000_0000_0001@@PEAPEAV1@@Z; CTextboxField::s_Create(ushort const *,__MIDL___MIDL_itf_inputscope_0000_0000_0001,CTextboxField * *)
0x180041bd8  mov     ebx, eax
0x180041bda  test    eax, eax
0x180041bdc  jns     short loc_180041BFB
0x180041bde  mov     rcx, [rbp+5Fh]; this
0x180041be2  mov     r9d, eax; char *
0x180041be5  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180041bec  mov     edx, 0B9h; void *
0x180041bf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041bf6  jmp     loc_180041CF2
0x180041bfb  mov     [rbp+57h+var_50], 0
0x180041c03  mov     rdi, [rbp+57h+var_58]
0x180041c07  mov     rax, [rdi]
0x180041c0a  mov     rbx, [rax+50h]
0x180041c0e  xor     edx, edx
0x180041c10  lea     rcx, [rbp+57h+var_50]
0x180041c14  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180041c19  lea     rdx, off_1800D1448; "value"
0x180041c20  lea     rcx, [rbp+57h+var_38]
0x180041c24  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180041c29  nop
0x180041c2a  lea     r8, [rbp+57h+var_50]
0x180041c2e  mov     rdx, [rax+18h]
0x180041c32  mov     rcx, rdi
0x180041c35  mov     rax, rbx
0x180041c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c3d  mov     ebx, eax
0x180041c3f  test    eax, eax
0x180041c41  jns     short loc_180041C60
0x180041c43  mov     edx, 0BBh; void *
0x180041c48  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180041c4f  mov     r9d, eax; char *
0x180041c52  mov     rcx, [rbp+5Fh]; this
0x180041c56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041c5b  jmp     loc_180041CE8
0x180041c60  mov     rdi, [rbp+57h+var_60]
0x180041c64  mov     rax, [rdi+18h]
0x180041c68  mov     rbx, [rax+30h]
0x180041c6c  xor     edx, edx; length
0x180041c6e  mov     rcx, [rbp+57h+var_50]; string
0x180041c72  call    cs:__imp_WindowsGetStringRawBuffer
0x180041c78  mov     rdx, rax
0x180041c7b  lea     rcx, [rdi+18h]
0x180041c7f  mov     rax, rbx
0x180041c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c87  mov     ebx, eax
0x180041c89  test    eax, eax
0x180041c8b  jns     short loc_180041C94
0x180041c8d  mov     edx, 0BCh
0x180041c92  jmp     short loc_180041C48
0x180041c94  mov     [rbp+57h+var_40], 0
0x180041c9c  lea     rcx, [rbp+57h+var_40]
0x180041ca0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041ca5  nop
0x180041ca6  mov     rcx, [rbp+57h+var_60]
0x180041caa  mov     rax, [rcx]
0x180041cad  lea     r8, [rbp+57h+var_40]
0x180041cb1  lea     rdx, _GUID_806925ad_98e5_4e7a_8200_6b83f9f8e52d
0x180041cb8  mov     rax, [rax]
0x180041cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041cc0  mov     ebx, eax
0x180041cc2  test    eax, eax
0x180041cc4  jns     short loc_180041D20
0x180041cc6  mov     rcx, [rbp+5Fh]; this
0x180041cca  mov     r9d, eax; char *
0x180041ccd  lea     r8, aShellOobeMachi_38; "shell\\oobe\\machine\\plugins\\oemregis"...
0x180041cd4  mov     edx, 0BEh; void *
0x180041cd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041cde  lea     rcx, [rbp+57h+var_40]
0x180041ce2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041ce7  nop
0x180041ce8  lea     rcx, [rbp+57h+var_50]; this
0x180041cec  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180041cf1  nop
0x180041cf2  lea     rcx, [rbp+57h+var_60]
0x180041cf6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041cfb  nop
0x180041cfc  lea     rcx, [rbp+57h+string]; this
0x180041d00  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180041d05  nop
0x180041d06  lea     rcx, [rbp+57h+var_70]; this
0x180041d0a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180041d0f  nop
0x180041d10  lea     rcx, [rbp+57h+var_58]
0x180041d14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041d19  mov     eax, ebx
0x180041d1b  jmp     loc_180041DA1
0x180041d20  mov     rdx, [rbp+57h+var_40]
0x180041d24  mov     [rbp+57h+var_40], 0
0x180041d2c  mov     rax, [rsi+18h]
0x180041d30  mov     ecx, [rax]
0x180041d32  mov     rax, [rsi+8]
0x180041d36  mov     [rax+rcx*8], rdx
0x180041d3a  mov     rax, [rsi+18h]
0x180041d3e  inc     dword ptr [rax]
0x180041d40  lea     rcx, [rbp+57h+var_40]
0x180041d44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041d49  nop
0x180041d4a  lea     rcx, [rbp+57h+var_50]; this
0x180041d4e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180041d53  nop
0x180041d54  lea     rcx, [rbp+57h+var_60]
0x180041d58  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041d5d  nop
0x180041d5e  lea     rcx, [rbp+57h+string]; this
0x180041d62  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180041d67  nop
0x180041d68  lea     rcx, [rbp+57h+var_70]; this
0x180041d6c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180041d71  nop
0x180041d72  lea     rcx, [rbp+57h+var_58]
0x180041d76  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041d7b  xor     eax, eax
0x180041d7d  jmp     short loc_180041DA1
0x180041d7f  lea     rcx, [rbp+57h+string]; this
0x180041d83  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180041d88  nop
0x180041d89  lea     rcx, [rbp+57h+var_70]; this
0x180041d8d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180041d92  nop
0x180041d93  lea     rcx, [rbp+57h+var_58]
0x180041d97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041d9c  mov     eax, 8000FFFFh
0x180041da1  mov     rcx, [rbp+57h+var_18]
0x180041da5  xor     rcx, rsp; StackCookie
0x180041da8  call    __security_check_cookie
0x180041dad  mov     rbx, [rsp+0A0h+arg_10]
0x180041db5  add     rsp, 90h
0x180041dbc  pop     rdi
0x180041dbd  pop     rsi
0x180041dbe  pop     rbp
0x180041dbf  retn
```
