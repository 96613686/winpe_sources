# _lambda_29850cdb69ecbcdc24300b9d2f158921_::operator()(Windows::Internal::CHSTRINGResult &)

- ea: `0x180039ef8`
- end: `0x18003a2fc`
- name: `??R_lambda_29850cdb69ecbcdc24300b9d2f158921_@@QEBAJAEAVCHSTRINGResult@Internal@Windows@@@Z`
- size: `1028`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180045440`

## callees

- `0x180002b60`
- `0x1800041b5`
- `0x1800076d4`
- `0x180009100`
- `0x180009760`
- `0x1800097f4`
- `0x180009814`
- `0x18000a4f8`
- `0x18000b200`
- `0x1800365c0`
- `0x180038c64`
- `0x180039ef8`
- `0x18003a984`
- `0x180044d8c`
- `0x1800455ac`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a098`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003a119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003a29c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003a119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003a29c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a061`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a0d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a10a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a28d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a061`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a0d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a10a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a28d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a07f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a07f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a153`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a177`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a153`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a177`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18003a15e`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18003a15e`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180039fc1`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180039fc1`
- `WINBRAND!GetEULAFile` at `0x18003a22a`
- `WINBRAND!GetEULAFile` at `0x18003a22a`

## string_xrefs

- `0x180039fa0`: `CloudExperienceHostAPI.OobeXmlAdapter`
- `0x180039f53`: `shellcommon\shell\oobe\core\components\winrt\oobeeulacore.cpp`
- `0x18003a02c`: `shellcommon\shell\oobe\core\components\winrt\oobeeulacore.cpp`
- `0x18003a0c0`: `shellcommon\shell\oobe\core\components\winrt\oobeeulacore.cpp`
- `0x18003a1e5`: `shellcommon\shell\oobe\core\components\winrt\oobeeulacore.cpp`
- `0x18003a246`: `shellcommon\shell\oobe\core\components\winrt\oobeeulacore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall _lambda_29850cdb69ecbcdc24300b9d2f158921_::operator()(_DWORD *a1, __int64 a2)
{
  int EulaParameters; // eax
  int EULAFile; // ebx
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, HSTRING, HSTRING *, _BYTE *); // rdi
  int v8; // eax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rdx
  HSTRING v11; // rdi
  HSTRING *v12; // rbx
  __int64 v13; // rax
  const WCHAR *StringRawBuffer; // rax
  unsigned __int16 v15; // bx
  const unsigned __int16 *v16; // rax
  __int64 v17; // rcx
  int HtmlFileWideCharContent; // eax
  HSTRING v19; // rdi
  HSTRING *v20; // rbx
  HSTRING_HEADER *p_hstringHeader; // [rsp+20h] [rbp-39h]
  _BYTE v23[8]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING v24; // [rsp+38h] [rbp-21h] BYREF
  unsigned __int16 *v25; // [rsp+40h] [rbp-19h] BYREF
  __int64 v26; // [rsp+48h] [rbp-11h] BYREF
  __int64 v27; // [rsp+50h] [rbp-9h] BYREF
  __int64 v28; // [rsp+58h] [rbp-1h] BYREF
  __int64 v29; // [rsp+60h] [rbp+7h] BYREF
  __int64 v30; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v31; // [rsp+70h] [rbp+17h] BYREF
  HSTRING string; // [rsp+78h] [rbp+1Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v28 = 0;
  v30 = 0;
  v29 = 0;
  EulaParameters = CloudExperienceHostAPI::OobeEulaManagerStaticsCore::GetEulaParameters(&v28, &v30, &v29);
  EULAFile = EulaParameters;
  if ( EulaParameters >= 0 )
  {
    v25 = 0;
    if ( *a1 )
    {
      if ( *a1 != 1 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
        EULAFile = -2147418113;
        goto LABEL_37;
      }
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        (HSTRING_HEADER *)&string,
        L"CloudExperienceHostAPI.OobeXmlAdapter",
        0x26u,
        0x25u);
      v27 = 0;
      v26 = 0;
      EULAFile = RoActivateInstance(*(_QWORD *)&hstringHeader.Reserved.Reserved2[16], &v26);
      if ( EULAFile >= 0 )
      {
        if ( !memcmp_0(&GUID_be3e7c84_d067_4a37_a11d_63c0d37dadc9, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
        {
          v27 = v26;
        }
        else
        {
          EULAFile = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v26)(
                       v26,
                       &GUID_be3e7c84_d067_4a37_a11d_63c0d37dadc9,
                       &v27);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
      }
      if ( EULAFile < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobeeulacore.cpp",
          (const char *)(unsigned int)EULAFile,
          (int)p_hstringHeader);
LABEL_12:
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
LABEL_31:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
        goto LABEL_37;
      }
      v23[0] = 0;
      v24 = 0;
      v6 = v27;
      v7 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *, _BYTE *))(*(_QWORD *)v27 + 56LL);
      WindowsDeleteString(0);
      v24 = 0;
      if ( WindowsCreateStringReference(L"oem/eulafilename", 0x10u, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v8 = v7(v6, string, &v24, v23);
      EULAFile = v8;
      if ( v8 < 0 )
      {
        v10 = 98;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobeeulacore.cpp",
          (const char *)(unsigned int)v8,
          (int)p_hstringHeader);
        WindowsDeleteString(v24);
        v24 = 0;
        goto LABEL_12;
      }
      if ( !v23[0] )
        goto LABEL_19;
      v26 = v28;
      v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, &v26);
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v13 + 24), 0);
      v15 = LocaleNameToLCID(StringRawBuffer, 0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v25,
        0);
      v16 = WindowsGetStringRawBuffer(v24, 0);
      v8 = TestForOOBEInfoFileLocalized(v16, v15, &v25);
      EULAFile = v8;
      if ( v8 == -2147023728 )
      {
LABEL_19:
        v11 = *(HSTRING *)Windows::Internal::StringReference::StringReference(
                            &string,
                            (const unsigned __int16 (*)[1])v9);
        v12 = (HSTRING *)(a2 + 16);
        if ( !v11 || v11 != *v12 )
        {
          WindowsDeleteString(*v12);
          *v12 = 0;
          WindowsDuplicateString(v11, (HSTRING *)(a2 + 16));
        }
        WindowsDeleteString(v24);
        v24 = 0;
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
        goto LABEL_36;
      }
      if ( v8 < 0 )
      {
        v10 = 116;
        goto LABEL_17;
      }
      WindowsDeleteString(v24);
      v24 = 0;
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
    }
    else
    {
      string = (HSTRING)&v25;
      hstringHeader.Reserved.Reserved1 = 0;
      hstringHeader.Reserved.Reserved2[8] = 1;
      p_hstringHeader = &hstringHeader;
      EULAFile = GetEULAFile(v28, v30, 0, v29);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&string);
      if ( EULAFile < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x56,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobeeulacore.cpp",
          (const char *)(unsigned int)EULAFile,
          (int)&hstringHeader);
        goto LABEL_31;
      }
    }
    v26 = 0;
    HtmlFileWideCharContent = GetHtmlFileWideCharContent(v17, v25, &v26);
    EULAFile = HtmlFileWideCharContent;
    if ( HtmlFileWideCharContent < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobeeulacore.cpp",
        (const char *)(unsigned int)HtmlFileWideCharContent,
        (int)p_hstringHeader);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
      goto LABEL_31;
    }
    v31 = v26;
    v19 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, &v31) + 24);
    v20 = (HSTRING *)(a2 + 16);
    if ( !v19 || v19 != *v20 )
    {
      WindowsDeleteString(*v20);
      *v20 = 0;
      WindowsDuplicateString(v19, (HSTRING *)(a2 + 16));
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
LABEL_36:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
    EULAFile = 0;
    goto LABEL_37;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4E,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobeeulacore.cpp",
    (const char *)(unsigned int)EulaParameters,
    (int)p_hstringHeader);
LABEL_37:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
  return (unsigned int)EULAFile;
}

```

## disassembly

```asm
0x180039ef8  mov     [rsp-8+arg_0], rbx
0x180039efd  mov     [rsp-8+arg_10], rsi
0x180039f02  push    rbp
0x180039f03  push    rdi
0x180039f04  push    r14
0x180039f06  lea     rbp, [rsp-47h]
0x180039f0b  sub     rsp, 0A0h
0x180039f12  mov     rax, cs:__security_cookie
0x180039f19  xor     rax, rsp
0x180039f1c  mov     [rbp+57h+var_18], rax
0x180039f20  mov     rsi, rdx
0x180039f23  mov     rdi, rcx
0x180039f26  xor     r14d, r14d
0x180039f29  mov     [rbp+57h+var_58], r14
0x180039f2d  mov     [rbp+57h+var_48], r14
0x180039f31  mov     [rbp+57h+var_50], r14
0x180039f35  lea     r8, [rbp+57h+var_50]
0x180039f39  lea     rdx, [rbp+57h+var_48]
0x180039f3d  lea     rcx, [rbp+57h+var_58]
0x180039f41  call    ?GetEulaParameters@OobeEulaManagerStaticsCore@CloudExperienceHostAPI@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@00@Z; CloudExperienceHostAPI::OobeEulaManagerStaticsCore::GetEulaParameters(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180039f46  mov     ebx, eax
0x180039f48  test    eax, eax
0x180039f4a  jns     short loc_180039F68
0x180039f4c  mov     rcx, [rbp+5Fh]; this
0x180039f50  mov     r9d, eax; char *
0x180039f53  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\oobe\\core\\compone"...
0x180039f5a  lea     edx, [r14+4Eh]; void *
0x180039f5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039f63  jmp     loc_18003A2B9
0x180039f68  mov     [rbp+57h+var_70], r14
0x180039f6c  mov     ecx, [rdi]
0x180039f6e  test    ecx, ecx
0x180039f70  jz      loc_18003A202
0x180039f76  cmp     ecx, 1
0x180039f79  jz      short loc_180039F8E
0x180039f7b  lea     rcx, [rbp+57h+var_70]
0x180039f7f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039f84  mov     ebx, 8000FFFFh
0x180039f89  jmp     loc_18003A2B9
0x180039f8e  mov     [rbp+57h+var_60], r14
0x180039f92  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r14
0x180039f96  mov     r9d, 25h ; '%'; unsigned int
0x180039f9c  lea     r8d, [r9+1]; unsigned int
0x180039fa0  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_OobeXmlAdapter@@3QBGB; "CloudExperienceHostAPI.OobeXmlAdapter"
0x180039fa7  lea     rcx, [rbp+57h+string]; hstringHeader
0x180039fab  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180039fb0  nop
0x180039fb1  mov     [rbp+57h+var_60], r14
0x180039fb5  mov     [rbp+57h+var_68], r14
0x180039fb9  lea     rdx, [rbp+57h+var_68]
0x180039fbd  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x180039fc1  call    cs:__imp_RoActivateInstance
0x180039fc7  mov     ebx, eax
0x180039fc9  test    eax, eax
0x180039fcb  js      short loc_18003A021
0x180039fcd  mov     r8d, 10h; Size
0x180039fd3  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180039fda  lea     rcx, _GUID_be3e7c84_d067_4a37_a11d_63c0d37dadc9; Buf1
0x180039fe1  call    memcmp_0
0x180039fe6  test    eax, eax
0x180039fe8  jnz     short loc_180039FF4
0x180039fea  mov     rax, [rbp+57h+var_68]
0x180039fee  mov     [rbp+57h+var_60], rax
0x180039ff2  jmp     short loc_18003A021
0x180039ff4  mov     rcx, [rbp+57h+var_68]
0x180039ff8  mov     rax, [rcx]
0x180039ffb  lea     r8, [rbp+57h+var_60]
0x180039fff  lea     rdx, _GUID_be3e7c84_d067_4a37_a11d_63c0d37dadc9
0x18003a006  mov     rax, [rax]
0x18003a009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a00e  mov     ebx, eax
0x18003a010  mov     rcx, [rbp+57h+var_68]
0x18003a014  mov     rax, [rcx]
0x18003a017  mov     rax, [rax+10h]
0x18003a01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a020  nop
0x18003a021  test    ebx, ebx
0x18003a023  jns     short loc_18003A04C
0x18003a025  mov     rcx, [rbp+5Fh]; this
0x18003a029  mov     r9d, ebx; char *
0x18003a02c  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\oobe\\core\\compone"...
0x18003a033  mov     edx, 5Eh ; '^'; void *
0x18003a038  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a03d  nop
0x18003a03e  lea     rcx, [rbp+57h+var_60]
0x18003a042  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18003a047  jmp     loc_18003A258
0x18003a04c  mov     [rbp+57h+var_80], r14b
0x18003a050  mov     [rbp+57h+var_78], r14
0x18003a054  mov     rbx, [rbp+57h+var_60]
0x18003a058  mov     rax, [rbx]
0x18003a05b  mov     rdi, [rax+38h]
0x18003a05f  xor     ecx, ecx; string
0x18003a061  call    cs:__imp_WindowsDeleteString
0x18003a067  mov     [rbp+57h+var_78], r14
0x18003a06b  lea     r9, [rbp+57h+string]; string
0x18003a06f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003a073  mov     edx, 10h; length
0x18003a078  lea     rcx, aOemEulafilenam; "oem/eulafilename"
0x18003a07f  call    cs:__imp_WindowsCreateStringReference
0x18003a085  test    eax, eax
0x18003a087  jns     short loc_18003A09E
0x18003a089  xor     r9d, r9d; lpArguments
0x18003a08c  xor     r8d, r8d; nNumberOfArguments
0x18003a08f  lea     edx, [r9+1]; dwExceptionFlags
0x18003a093  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003a098  call    cs:__imp_RaiseException
0x18003a09e  lea     r9, [rbp+57h+var_80]
0x18003a0a2  lea     r8, [rbp+57h+var_78]
0x18003a0a6  mov     rdx, [rbp+57h+string]
0x18003a0aa  mov     rcx, rbx
0x18003a0ad  mov     rax, rdi
0x18003a0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0b5  mov     ebx, eax
0x18003a0b7  test    eax, eax
0x18003a0b9  jns     short loc_18003A0E7
0x18003a0bb  mov     edx, 62h ; 'b'; void *
0x18003a0c0  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\oobe\\core\\compone"...
0x18003a0c7  mov     r9d, eax; char *
0x18003a0ca  mov     rcx, [rbp+5Fh]; this
0x18003a0ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a0d3  nop
0x18003a0d4  mov     rcx, [rbp+57h+var_78]; string
0x18003a0d8  call    cs:__imp_WindowsDeleteString
0x18003a0de  mov     [rbp+57h+var_78], r14
0x18003a0e2  jmp     loc_18003A03E
0x18003a0e7  lea     rcx, [rbp+57h+string]; string
0x18003a0eb  cmp     [rbp+57h+var_80], r14b
0x18003a0ef  jnz     short loc_18003A13C
0x18003a0f1  call    ??$?0$00@StringReference@Internal@Windows@@QEAA@AEAY00$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[1])
0x18003a0f6  mov     rdi, [rax]
0x18003a0f9  test    rdi, rdi
0x18003a0fc  lea     rbx, [rsi+10h]
0x18003a100  jz      short loc_18003A107
0x18003a102  cmp     rdi, [rbx]
0x18003a105  jz      short loc_18003A120
0x18003a107  mov     rcx, [rbx]; string
0x18003a10a  call    cs:__imp_WindowsDeleteString
0x18003a110  mov     [rbx], r14
0x18003a113  mov     rdx, rbx; newString
0x18003a116  mov     rcx, rdi; string
0x18003a119  call    cs:__imp_WindowsDuplicateString
0x18003a11f  nop
0x18003a120  mov     rcx, [rbp+57h+var_78]; string
0x18003a124  call    cs:__imp_WindowsDeleteString
0x18003a12a  mov     [rbp+57h+var_78], r14
0x18003a12e  lea     rcx, [rbp+57h+var_60]
0x18003a132  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18003a137  jmp     loc_18003A2AD
0x18003a13c  mov     rax, [rbp+57h+var_58]
0x18003a140  mov     [rbp+57h+var_68], rax
0x18003a144  lea     rdx, [rbp+57h+var_68]
0x18003a148  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003a14d  xor     edx, edx; length
0x18003a14f  mov     rcx, [rax+18h]; string
0x18003a153  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a159  mov     rcx, rax; lpName
0x18003a15c  xor     edx, edx; dwFlags
0x18003a15e  call    cs:__imp_LocaleNameToLCID
0x18003a164  mov     ebx, eax
0x18003a166  xor     edx, edx
0x18003a168  lea     rcx, [rbp+57h+var_70]
0x18003a16c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003a171  xor     edx, edx; length
0x18003a173  mov     rcx, [rbp+57h+var_78]; string
0x18003a177  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a17d  movzx   edx, bx; unsigned __int16
0x18003a180  lea     r8, [rbp+57h+var_70]; unsigned __int16 **
0x18003a184  mov     rcx, rax; unsigned __int16 *
0x18003a187  call    ?TestForOOBEInfoFileLocalized@@YAJPEBGGPEAPEAG@Z; TestForOOBEInfoFileLocalized(ushort const *,ushort,ushort * *)
0x18003a18c  mov     ebx, eax
0x18003a18e  cmp     eax, 80070490h
0x18003a193  jnz     short loc_18003A19E
0x18003a195  lea     rcx, [rbp+57h+string]
0x18003a199  jmp     loc_18003A0F1
0x18003a19e  test    eax, eax
0x18003a1a0  jns     short loc_18003A1AC
0x18003a1a2  mov     edx, 74h ; 't'
0x18003a1a7  jmp     loc_18003A0C0
0x18003a1ac  mov     rcx, [rbp+57h+var_78]; string
0x18003a1b0  call    cs:__imp_WindowsDeleteString
0x18003a1b6  mov     [rbp+57h+var_78], r14
0x18003a1ba  lea     rcx, [rbp+57h+var_60]
0x18003a1be  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18003a1c3  mov     [rbp+57h+var_68], r14
0x18003a1c7  lea     r8, [rbp+57h+var_68]
0x18003a1cb  mov     rdx, [rbp+57h+var_70]
0x18003a1cf  call    ?GetHtmlFileWideCharContent@@YAJIPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetHtmlFileWideCharContent(uint,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003a1d4  mov     ebx, eax
0x18003a1d6  test    eax, eax
0x18003a1d8  jns     loc_18003A263
0x18003a1de  mov     rcx, [rbp+5Fh]; this
0x18003a1e2  mov     r9d, eax; char *
0x18003a1e5  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\oobe\\core\\compone"...
0x18003a1ec  mov     edx, 7Dh ; '}'; void *
0x18003a1f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a1f6  nop
0x18003a1f7  lea     rcx, [rbp+57h+var_68]
0x18003a1fb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a200  jmp     short loc_18003A258
0x18003a202  lea     rax, [rbp+57h+var_70]
0x18003a206  mov     [rbp+57h+string], rax
0x18003a20a  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r14
0x18003a20e  mov     byte ptr [rbp+57h+hstringHeader.Reserved+8], 1
0x18003a212  lea     rax, [rbp+57h+hstringHeader]
0x18003a216  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18003a21b  mov     r9, [rbp+57h+var_50]
0x18003a21f  xor     r8d, r8d
0x18003a222  mov     rdx, [rbp+57h+var_48]
0x18003a226  mov     rcx, [rbp+57h+var_58]
0x18003a22a  call    cs:__imp_GetEULAFile
0x18003a230  mov     ebx, eax
0x18003a232  lea     rcx, [rbp+57h+string]
0x18003a236  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18003a23b  test    ebx, ebx
0x18003a23d  jns     short loc_18003A1C3
0x18003a23f  mov     rcx, [rbp+5Fh]; this
0x18003a243  mov     r9d, ebx; char *
0x18003a246  lea     r8, aShellcommonShe_22; "shellcommon\\shell\\oobe\\core\\compone"...
0x18003a24d  mov     edx, 56h ; 'V'; void *
0x18003a252  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a257  nop
0x18003a258  lea     rcx, [rbp+57h+var_70]
0x18003a25c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a261  jmp     short loc_18003A2B9
0x18003a263  mov     rax, [rbp+57h+var_68]
0x18003a267  mov     [rbp+57h+var_40], rax
0x18003a26b  lea     rdx, [rbp+57h+var_40]
0x18003a26f  lea     rcx, [rbp+57h+string]
0x18003a273  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003a278  mov     rdi, [rax+18h]
0x18003a27c  lea     rbx, [rsi+10h]
0x18003a280  test    rdi, rdi
0x18003a283  jz      short loc_18003A28A
0x18003a285  cmp     rdi, [rbx]
0x18003a288  jz      short loc_18003A2A3
0x18003a28a  mov     rcx, [rbx]; string
0x18003a28d  call    cs:__imp_WindowsDeleteString
0x18003a293  mov     [rbx], r14
0x18003a296  mov     rdx, rbx; newString
0x18003a299  mov     rcx, rdi; string
0x18003a29c  call    cs:__imp_WindowsDuplicateString
0x18003a2a2  nop
0x18003a2a3  lea     rcx, [rbp+57h+var_68]
0x18003a2a7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a2ac  nop
0x18003a2ad  lea     rcx, [rbp+57h+var_70]
0x18003a2b1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a2b6  mov     ebx, r14d
0x18003a2b9  lea     rcx, [rbp+57h+var_50]
0x18003a2bd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a2c2  nop
0x18003a2c3  lea     rcx, [rbp+57h+var_48]
0x18003a2c7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a2cc  nop
0x18003a2cd  lea     rcx, [rbp+57h+var_58]
0x18003a2d1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a2d6  mov     eax, ebx
0x18003a2d8  mov     rcx, [rbp+57h+var_18]
0x18003a2dc  xor     rcx, rsp; StackCookie
0x18003a2df  call    __security_check_cookie
0x18003a2e4  lea     r11, [rsp+0B0h+var_10]
0x18003a2ec  mov     rbx, [r11+20h]
0x18003a2f0  mov     rsi, [r11+30h]
0x18003a2f4  mov     rsp, r11
0x18003a2f7  pop     r14
0x18003a2f9  pop     rdi
0x18003a2fa  pop     rbp
0x18003a2fb  retn
```
