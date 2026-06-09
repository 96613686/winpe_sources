# IsImageInDesktopSpotlightLocation(ushort const *)

- ea: `0x140092ab8`
- end: `0x140092fde`
- name: `?IsImageInDesktopSpotlightLocation@@YA_NPEBG@Z`
- size: `1318`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14017a3c0`

## callees

- `0x14000a150`
- `0x14000a3e0`
- `0x140034af0`
- `0x140063518`
- `0x140065b60`
- `0x140080a70`
- `0x14008925c`
- `0x140091984`
- `0x140091afc`
- `0x140091b18`
- `0x1400928e8`
- `0x140092ab8`
- `0x140092fe4`
- `0x140093070`
- `0x1400930dc`
- `0x140093158`
- `0x1400931a8`
- `0x1400931e4`
- `0x1400b5024`
- `0x1401040e0`
- `0x140187ed0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140092b51`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140092bc3`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140092c51`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140092d6a`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140092e2d`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140092f10`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x140092c02`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x140092c02`

## string_xrefs

- `0x140092ae9`: `com.microsoft.windows.extension.desktopspotlight`
- `0x140092fab`: `IsDesktopSpotlightImageByPath=%d %ws`
- `0x140092c87`: `IsDesktopSpotlightImageByPath=%d - image not located in LocalAppData %ws`
- `0x140092d83`: `irisservice`
- `0x140092e5f`: `IsDesktopSpotlightImageByPath=%d - image not located in microsoft folder %ws`
- `0x140092d9c`: `IsDesktopSpotlightImageByPath=%d - image not located in irisservice folder %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
bool __fastcall IsImageInDesktopSpotlightLocation(const unsigned __int16 *a1)
{
  bool v2; // di
  __int64 v3; // r8
  _QWORD *v4; // r9
  _QWORD *v5; // rax
  int v6; // r9d
  _QWORD *v7; // rdx
  winrt::hstring *v8; // rax
  const unsigned __int16 *v9; // rax
  __int64 v10; // r8
  _QWORD *v11; // r9
  _QWORD *v12; // rax
  int v13; // r9d
  _QWORD *v14; // rdx
  __int64 v15; // r8
  _QWORD *v16; // r9
  _QWORD *v17; // rax
  int v18; // r9d
  _QWORD *v19; // rdx
  __int64 v20; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // r8
  _QWORD *v26; // r9
  _QWORD *v27; // rax
  int v28; // r9d
  _QWORD *v29; // rdx
  _QWORD *v30; // rax
  __int64 v31; // r8
  _QWORD *v32; // r9
  _QWORD *v33; // rax
  int v34; // r9d
  _QWORD *v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rax
  _QWORD *v38; // rax
  __int64 v39; // r8
  _QWORD *v40; // r9
  _QWORD *v41; // rax
  int v42; // r9d
  _QWORD *v43; // rdx
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v45; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v46[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v47[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v48[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v49[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v50; // [rsp+70h] [rbp-90h]
  _QWORD v51[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v52; // [rsp+90h] [rbp-70h]
  _QWORD v53[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v54; // [rsp+B0h] [rbp-50h]
  _QWORD v55[3]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v56; // [rsp+D0h] [rbp-30h]
  _QWORD v57[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v58; // [rsp+F0h] [rbp-10h]
  _QWORD v59[3]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v60; // [rsp+110h] [rbp+10h]
  _BYTE v61[32]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v62[32]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v63[32]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v64[32]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v65[32]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v66[32]; // [rsp+1B8h] [rbp+B8h] BYREF

  v2 = 0;
  winrt::param::hstring::hstring((winrt::param::hstring *)v61, L"com.microsoft.windows.extension.desktopspotlight");
  winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::Find((const struct winrt::param::hstring *)&v45);
  if ( v45 )
  {
    std::wstring::wstring(v51, a1);
    v4 = v51;
    if ( v52 > 7 )
      v4 = (_QWORD *)v51[0];
    v5 = (_QWORD *)std::wstring::end(v51, v48, v3, v4);
    v7 = v51;
    if ( v52 > 7 )
      LODWORD(v7) = v51[0];
    std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
      (unsigned int)v46,
      (_DWORD)v7,
      *v5,
      v6,
      _o_towlower);
    v8 = (winrt::hstring *)winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension2<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension>::PackageFamilyName(
                             &v45,
                             v48);
    v9 = winrt::hstring::c_str(v8);
    std::wstring::wstring(v53, v9);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v48);
    v11 = v53;
    if ( v54 > 7 )
      v11 = (_QWORD *)v53[0];
    v12 = (_QWORD *)std::wstring::end(v53, v46, v10, v11);
    v14 = v53;
    if ( v54 > 7 )
      LODWORD(v14) = v53[0];
    std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
      (unsigned int)v47,
      (_DWORD)v14,
      *v12,
      v13,
      _o_towlower);
    ppszPath = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPath,
      0);
    if ( SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath) >= 0 )
    {
      std::wstring::wstring(v49, ppszPath);
      v16 = v49;
      if ( v50 > 7 )
        v16 = (_QWORD *)v49[0];
      v17 = (_QWORD *)std::wstring::end(v49, v47, v15, v16);
      v19 = v49;
      if ( v50 > 7 )
        LODWORD(v19) = v49[0];
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        (unsigned int)v46,
        (_DWORD)v19,
        *v17,
        v18,
        _o_towlower);
      if ( (unsigned int)std::wstring::compare(v51, v20, v49[2], v49) )
      {
        DesktopSpotlightLogonTelemetry::TraceLoggingInfo(
          "IsDesktopSpotlightImageByPath=%d - image not located in LocalAppData %ws",
          0,
          a1);
LABEL_17:
        std::wstring::~wstring(v49);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
        std::wstring::~wstring(v53);
        std::wstring::~wstring(v51);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v45);
        return 0;
      }
      v22 = std::filesystem::path::path(v64, v51);
      v23 = std::filesystem::path::parent_path(v22, v63);
      std::filesystem::path::parent_path(v23, v62);
      std::wstring::~wstring(v63);
      std::wstring::~wstring(v64);
      v24 = (_QWORD *)std::filesystem::path::filename(v62, v65);
      if ( v24[3] > 7u )
        v24 = (_QWORD *)*v24;
      std::wstring::wstring(v55, v24);
      std::wstring::~wstring(v65);
      v26 = v55;
      if ( v56 > 7 )
        v26 = (_QWORD *)v55[0];
      v27 = (_QWORD *)std::wstring::end(v55, v47, v25, v26);
      v29 = v55;
      if ( v56 > 7 )
        LODWORD(v29) = v55[0];
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        (unsigned int)v46,
        (_DWORD)v29,
        *v27,
        v28,
        _o_towlower);
      if ( (unsigned int)std::wstring::compare(v55, L"irisservice") )
      {
        DesktopSpotlightLogonTelemetry::TraceLoggingInfo(
          "IsDesktopSpotlightImageByPath=%d - image not located in irisservice folder %ws",
          0,
          a1);
LABEL_26:
        std::wstring::~wstring(v55);
        std::wstring::~wstring(v62);
        goto LABEL_17;
      }
      std::filesystem::path::parent_path(v62, v61);
      v30 = (_QWORD *)std::filesystem::path::filename(v61, v65);
      if ( v30[3] > 7u )
        v30 = (_QWORD *)*v30;
      std::wstring::wstring(v57, v30);
      std::wstring::~wstring(v65);
      v32 = v57;
      if ( v58 > 7 )
        v32 = (_QWORD *)v57[0];
      v33 = (_QWORD *)std::wstring::end(v57, v47, v31, v32);
      v35 = v57;
      if ( v58 > 7 )
        LODWORD(v35) = v57[0];
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        (unsigned int)v46,
        (_DWORD)v35,
        *v33,
        v34,
        _o_towlower);
      if ( (unsigned int)std::wstring::compare(v57, L"microsoft") )
      {
        DesktopSpotlightLogonTelemetry::TraceLoggingInfo(
          "IsDesktopSpotlightImageByPath=%d - image not located in microsoft folder %ws",
          0,
          a1);
        std::wstring::~wstring(v57);
        std::wstring::~wstring(v61);
        goto LABEL_26;
      }
      v36 = std::filesystem::path::parent_path(v61, v66);
      v37 = std::filesystem::path::parent_path(v36, v63);
      v38 = (_QWORD *)std::filesystem::path::filename(v37, v64);
      if ( v38[3] > 7u )
        v38 = (_QWORD *)*v38;
      std::wstring::wstring(v59, v38);
      std::wstring::~wstring(v64);
      std::wstring::~wstring(v63);
      std::wstring::~wstring(v66);
      v40 = v59;
      if ( v60 > 7 )
        v40 = (_QWORD *)v59[0];
      v41 = (_QWORD *)std::wstring::end(v59, v47, v39, v40);
      v43 = v59;
      if ( v60 > 7 )
        LODWORD(v43) = v59[0];
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        (unsigned int)v46,
        (_DWORD)v43,
        *v41,
        v42,
        _o_towlower);
      v2 = (unsigned int)std::wstring::compare(v59, v53) == 0;
      std::wstring::~wstring(v59);
      std::wstring::~wstring(v57);
      std::wstring::~wstring(v61);
      std::wstring::~wstring(v55);
      std::wstring::~wstring(v62);
      std::wstring::~wstring(v49);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    std::wstring::~wstring(v53);
    std::wstring::~wstring(v51);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v45);
  DesktopSpotlightLogonTelemetry::TraceLoggingInfo("IsDesktopSpotlightImageByPath=%d %ws", v2, a1);
  return v2;
}

```

## disassembly

```asm
0x140092ab8  mov     [rsp-8+arg_8], rbx
0x140092abd  mov     [rsp-8+arg_10], rdi
0x140092ac2  push    rbp
0x140092ac3  lea     rbp, [rsp-0E0h]
0x140092acb  sub     rsp, 1E0h
0x140092ad2  mov     rax, cs:__security_cookie
0x140092ad9  xor     rax, rsp
0x140092adc  mov     [rbp+0E0h+var_8], rax
0x140092ae3  mov     rbx, rcx
0x140092ae6  xor     dil, dil
0x140092ae9  lea     rdx, aComMicrosoftWi; "com.microsoft.windows.extension.desktop"...
0x140092af0  lea     rcx, [rbp+0E0h+var_C8]; this
0x140092af4  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x140092af9  lea     rdx, [rbp+0E0h+var_C8]
0x140092afd  lea     rcx, [rsp+1E0h+var_1A8]; struct winrt::param::hstring *
0x140092b02  call    ?Find@AppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::Find(winrt::param::hstring const &)
0x140092b07  nop
0x140092b08  cmp     [rsp+1E0h+var_1A8], 0
0x140092b0e  jz      loc_140092F9A
0x140092b14  mov     rdx, rbx
0x140092b17  lea     rcx, [rsp+1E0h+var_168]
0x140092b1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140092b21  nop
0x140092b22  lea     r9, [rsp+1E0h+var_168]
0x140092b27  cmp     [rbp+0E0h+var_150], 7
0x140092b2c  cmova   r9, [rsp+1E0h+var_168]
0x140092b32  lea     rdx, [rsp+1E0h+var_190]
0x140092b37  lea     rcx, [rsp+1E0h+var_168]
0x140092b3c  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x140092b41  lea     rdx, [rsp+1E0h+var_168]
0x140092b46  cmp     [rbp+0E0h+var_150], 7
0x140092b4b  cmova   rdx, [rsp+1E0h+var_168]
0x140092b51  mov     rcx, cs:__imp__o_towlower
0x140092b58  mov     [rsp+1E0h+var_1C0], rcx
0x140092b5d  mov     r8, [rax]
0x140092b60  lea     rcx, [rsp+1E0h+var_1A0]
0x140092b65  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x140092b6a  lea     rdx, [rsp+1E0h+var_190]
0x140092b6f  lea     rcx, [rsp+1E0h+var_1A8]
0x140092b74  call    ?PackageFamilyName@?$consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension2@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension2<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension>::PackageFamilyName(void)
0x140092b79  nop
0x140092b7a  mov     rcx, rax; this
0x140092b7d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x140092b82  mov     rdx, rax
0x140092b85  lea     rcx, [rbp+0E0h+var_148]
0x140092b89  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140092b8e  nop
0x140092b8f  lea     rcx, [rsp+1E0h+var_190]
0x140092b94  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x140092b99  lea     r9, [rbp+0E0h+var_148]
0x140092b9d  cmp     [rbp+0E0h+var_130], 7
0x140092ba2  cmova   r9, [rbp+0E0h+var_148]
0x140092ba7  lea     rdx, [rsp+1E0h+var_1A0]
0x140092bac  lea     rcx, [rbp+0E0h+var_148]
0x140092bb0  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x140092bb5  lea     rdx, [rbp+0E0h+var_148]
0x140092bb9  cmp     [rbp+0E0h+var_130], 7
0x140092bbe  cmova   rdx, [rbp+0E0h+var_148]
0x140092bc3  mov     rcx, cs:__imp__o_towlower
0x140092bca  mov     [rsp+1E0h+var_1C0], rcx
0x140092bcf  mov     r8, [rax]
0x140092bd2  lea     rcx, [rsp+1E0h+var_198]
0x140092bd7  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x140092bdc  mov     [rsp+1E0h+ppszPath], 0
0x140092be5  xor     edx, edx
0x140092be7  lea     rcx, [rsp+1E0h+ppszPath]
0x140092bec  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140092bf1  lea     r9, [rsp+1E0h+ppszPath]; ppszPath
0x140092bf6  xor     r8d, r8d; hToken
0x140092bf9  xor     edx, edx; dwFlags
0x140092bfb  lea     rcx, FOLDERID_LocalAppData; rfid
0x140092c02  call    cs:__imp_SHGetKnownFolderPath
0x140092c08  test    eax, eax
0x140092c0a  js      loc_140092F7A
0x140092c10  mov     rdx, [rsp+1E0h+ppszPath]
0x140092c15  lea     rcx, [rsp+1E0h+var_188]
0x140092c1a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140092c1f  nop
0x140092c20  lea     r9, [rsp+1E0h+var_188]
0x140092c25  cmp     [rsp+1E0h+var_170], 7
0x140092c2b  cmova   r9, [rsp+1E0h+var_188]
0x140092c31  lea     rdx, [rsp+1E0h+var_198]
0x140092c36  lea     rcx, [rsp+1E0h+var_188]
0x140092c3b  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x140092c40  lea     rdx, [rsp+1E0h+var_188]
0x140092c45  cmp     [rsp+1E0h+var_170], 7
0x140092c4b  cmova   rdx, [rsp+1E0h+var_188]
0x140092c51  mov     rcx, cs:__imp__o_towlower
0x140092c58  mov     [rsp+1E0h+var_1C0], rcx
0x140092c5d  mov     r8, [rax]
0x140092c60  lea     rcx, [rsp+1E0h+var_1A0]
0x140092c65  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x140092c6a  lea     r9, [rsp+1E0h+var_188]
0x140092c6f  mov     r8, [rsp+1E0h+var_178]
0x140092c74  lea     rcx, [rsp+1E0h+var_168]
0x140092c79  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0AEBV12@@Z; std::wstring::compare(unsigned __int64,unsigned __int64,std::wstring const &)
0x140092c7e  test    eax, eax
0x140092c80  jz      short loc_140092CD0
0x140092c82  mov     r8, rbx
0x140092c85  xor     edx, edx
0x140092c87  lea     rcx, aIsdesktopspotl_2; "IsDesktopSpotlightImageByPath=%d - imag"...
0x140092c8e  call    ?TraceLoggingInfo@DesktopSpotlightLogonTelemetry@@SAXPEBDZZ; DesktopSpotlightLogonTelemetry::TraceLoggingInfo(char const *,...)
0x140092c93  nop
0x140092c94  lea     rcx, [rsp+1E0h+var_188]; void *
0x140092c99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092c9e  nop
0x140092c9f  lea     rcx, [rsp+1E0h+ppszPath]
0x140092ca4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140092ca9  nop
0x140092caa  lea     rcx, [rbp+0E0h+var_148]; void *
0x140092cae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092cb3  nop
0x140092cb4  lea     rcx, [rsp+1E0h+var_168]; void *
0x140092cb9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092cbe  nop
0x140092cbf  lea     rcx, [rsp+1E0h+var_1A8]
0x140092cc4  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140092cc9  xor     al, al
0x140092ccb  jmp     loc_140092FBA
0x140092cd0  lea     rdx, [rsp+1E0h+var_168]
0x140092cd5  lea     rcx, [rbp+0E0h+var_68]
0x140092cd9  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x140092cde  nop
0x140092cdf  lea     rdx, [rbp+0E0h+var_88]
0x140092ce3  mov     rcx, rax
0x140092ce6  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x140092ceb  nop
0x140092cec  lea     rdx, [rbp+0E0h+var_A8]
0x140092cf0  mov     rcx, rax
0x140092cf3  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x140092cf8  nop
0x140092cf9  lea     rcx, [rbp+0E0h+var_88]; void *
0x140092cfd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092d02  nop
0x140092d03  lea     rcx, [rbp+0E0h+var_68]; void *
0x140092d07  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092d0c  lea     rdx, [rbp+0E0h+var_48]
0x140092d13  lea     rcx, [rbp+0E0h+var_A8]
0x140092d17  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x140092d1c  nop
0x140092d1d  cmp     qword ptr [rax+18h], 7
0x140092d22  jbe     short loc_140092D27
0x140092d24  mov     rax, [rax]
0x140092d27  mov     rdx, rax
0x140092d2a  lea     rcx, [rbp+0E0h+var_128]
0x140092d2e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140092d33  nop
0x140092d34  lea     rcx, [rbp+0E0h+var_48]; void *
0x140092d3b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092d40  lea     r9, [rbp+0E0h+var_128]
0x140092d44  cmp     [rbp+0E0h+var_110], 7
0x140092d49  cmova   r9, [rbp+0E0h+var_128]
0x140092d4e  lea     rdx, [rsp+1E0h+var_198]
0x140092d53  lea     rcx, [rbp+0E0h+var_128]
0x140092d57  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x140092d5c  lea     rdx, [rbp+0E0h+var_128]
0x140092d60  cmp     [rbp+0E0h+var_110], 7
0x140092d65  cmova   rdx, [rbp+0E0h+var_128]
0x140092d6a  mov     rcx, cs:__imp__o_towlower
0x140092d71  mov     [rsp+1E0h+var_1C0], rcx
0x140092d76  mov     r8, [rax]
0x140092d79  lea     rcx, [rsp+1E0h+var_1A0]
0x140092d7e  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x140092d83  lea     rdx, aIrisservice; "irisservice"
0x140092d8a  lea     rcx, [rbp+0E0h+var_128]
0x140092d8e  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x140092d93  test    eax, eax
0x140092d95  jz      short loc_140092DC1
0x140092d97  mov     r8, rbx
0x140092d9a  xor     edx, edx
0x140092d9c  lea     rcx, aIsdesktopspotl; "IsDesktopSpotlightImageByPath=%d - imag"...
0x140092da3  call    ?TraceLoggingInfo@DesktopSpotlightLogonTelemetry@@SAXPEBDZZ; DesktopSpotlightLogonTelemetry::TraceLoggingInfo(char const *,...)
0x140092da8  nop
0x140092da9  lea     rcx, [rbp+0E0h+var_128]; void *
0x140092dad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092db2  nop
0x140092db3  lea     rcx, [rbp+0E0h+var_A8]; void *
0x140092db7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092dbc  jmp     loc_140092C94
0x140092dc1  lea     rdx, [rbp+0E0h+var_C8]
0x140092dc5  lea     rcx, [rbp+0E0h+var_A8]
0x140092dc9  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x140092dce  nop
0x140092dcf  lea     rdx, [rbp+0E0h+var_48]
0x140092dd6  lea     rcx, [rbp+0E0h+var_C8]
0x140092dda  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x140092ddf  nop
0x140092de0  cmp     qword ptr [rax+18h], 7
0x140092de5  jbe     short loc_140092DEA
0x140092de7  mov     rax, [rax]
0x140092dea  mov     rdx, rax
0x140092ded  lea     rcx, [rbp+0E0h+var_108]
0x140092df1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140092df6  nop
0x140092df7  lea     rcx, [rbp+0E0h+var_48]; void *
0x140092dfe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092e03  lea     r9, [rbp+0E0h+var_108]
0x140092e07  cmp     [rbp+0E0h+var_F0], 7
0x140092e0c  cmova   r9, [rbp+0E0h+var_108]
0x140092e11  lea     rdx, [rsp+1E0h+var_198]
0x140092e16  lea     rcx, [rbp+0E0h+var_108]
0x140092e1a  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x140092e1f  lea     rdx, [rbp+0E0h+var_108]
0x140092e23  cmp     [rbp+0E0h+var_F0], 7
0x140092e28  cmova   rdx, [rbp+0E0h+var_108]
0x140092e2d  mov     rcx, cs:__imp__o_towlower
0x140092e34  mov     [rsp+1E0h+var_1C0], rcx
0x140092e39  mov     r8, [rax]
0x140092e3c  lea     rcx, [rsp+1E0h+var_1A0]
0x140092e41  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x140092e46  lea     rdx, aMicrosoft; "microsoft"
0x140092e4d  lea     rcx, [rbp+0E0h+var_108]
0x140092e51  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x140092e56  test    eax, eax
0x140092e58  jz      short loc_140092E84
0x140092e5a  mov     r8, rbx
0x140092e5d  xor     edx, edx
0x140092e5f  lea     rcx, aIsdesktopspotl_3; "IsDesktopSpotlightImageByPath=%d - imag"...
0x140092e66  call    ?TraceLoggingInfo@DesktopSpotlightLogonTelemetry@@SAXPEBDZZ; DesktopSpotlightLogonTelemetry::TraceLoggingInfo(char const *,...)
0x140092e6b  nop
0x140092e6c  lea     rcx, [rbp+0E0h+var_108]; void *
0x140092e70  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092e75  nop
0x140092e76  lea     rcx, [rbp+0E0h+var_C8]; void *
0x140092e7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092e7f  jmp     loc_140092DA9
0x140092e84  lea     rdx, [rbp+0E0h+var_28]
0x140092e8b  lea     rcx, [rbp+0E0h+var_C8]
0x140092e8f  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x140092e94  nop
0x140092e95  lea     rdx, [rbp+0E0h+var_88]
0x140092e99  mov     rcx, rax
0x140092e9c  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x140092ea1  nop
0x140092ea2  lea     rdx, [rbp+0E0h+var_68]
0x140092ea6  mov     rcx, rax
0x140092ea9  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x140092eae  nop
0x140092eaf  cmp     qword ptr [rax+18h], 7
0x140092eb4  jbe     short loc_140092EB9
0x140092eb6  mov     rax, [rax]
0x140092eb9  mov     rdx, rax
0x140092ebc  lea     rcx, [rbp+0E0h+var_E8]
0x140092ec0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140092ec5  nop
0x140092ec6  lea     rcx, [rbp+0E0h+var_68]; void *
0x140092eca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092ecf  nop
0x140092ed0  lea     rcx, [rbp+0E0h+var_88]; void *
0x140092ed4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092ed9  nop
0x140092eda  lea     rcx, [rbp+0E0h+var_28]; void *
0x140092ee1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092ee6  lea     r9, [rbp+0E0h+var_E8]
0x140092eea  cmp     [rbp+0E0h+var_D0], 7
0x140092eef  cmova   r9, [rbp+0E0h+var_E8]
0x140092ef4  lea     rdx, [rsp+1E0h+var_198]
0x140092ef9  lea     rcx, [rbp+0E0h+var_E8]
0x140092efd  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x140092f02  lea     rdx, [rbp+0E0h+var_E8]
0x140092f06  cmp     [rbp+0E0h+var_D0], 7
0x140092f0b  cmova   rdx, [rbp+0E0h+var_E8]
0x140092f10  mov     rcx, cs:__imp__o_towlower
0x140092f17  mov     [rsp+1E0h+var_1C0], rcx
0x140092f1c  mov     r8, [rax]
0x140092f1f  lea     rcx, [rsp+1E0h+var_1A0]
0x140092f24  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x140092f29  lea     rdx, [rbp+0E0h+var_148]
0x140092f2d  lea     rcx, [rbp+0E0h+var_E8]
0x140092f31  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x140092f36  nop
0x140092f37  test    eax, eax
0x140092f39  setz    dil
0x140092f3d  lea     rcx, [rbp+0E0h+var_E8]; void *
0x140092f41  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092f46  nop
0x140092f47  lea     rcx, [rbp+0E0h+var_108]; void *
0x140092f4b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092f50  nop
0x140092f51  lea     rcx, [rbp+0E0h+var_C8]; void *
0x140092f55  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092f5a  nop
0x140092f5b  lea     rcx, [rbp+0E0h+var_128]; void *
0x140092f5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092f64  nop
0x140092f65  lea     rcx, [rbp+0E0h+var_A8]; void *
0x140092f69  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092f6e  nop
0x140092f6f  lea     rcx, [rsp+1E0h+var_188]; void *
0x140092f74  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092f79  nop
0x140092f7a  lea     rcx, [rsp+1E0h+ppszPath]
0x140092f7f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140092f84  nop
0x140092f85  lea     rcx, [rbp+0E0h+var_148]; void *
0x140092f89  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092f8e  nop
0x140092f8f  lea     rcx, [rsp+1E0h+var_168]; void *
0x140092f94  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140092f99  nop
  ... truncated ...
```
