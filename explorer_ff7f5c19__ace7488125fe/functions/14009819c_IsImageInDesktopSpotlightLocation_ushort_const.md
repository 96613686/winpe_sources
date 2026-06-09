# IsImageInDesktopSpotlightLocation(ushort const *)

- ea: `0x14009819c`
- end: `0x1400986c9`
- name: `?IsImageInDesktopSpotlightLocation@@YA_NPEBG@Z`
- size: `1325`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140185eb0`

## callees

- `0x140005810`
- `0x14000d980`
- `0x14000dc10`
- `0x14000fbdc`
- `0x140066e28`
- `0x140086bc0`
- `0x14008ed2c`
- `0x140096e78`
- `0x140096f2c`
- `0x140096f74`
- `0x140097fcc`
- `0x14009819c`
- `0x1400986d0`
- `0x140098780`
- `0x1400987f4`
- `0x140098874`
- `0x1400988c4`
- `0x140098900`
- `0x1400bafd4`
- `0x14010e160`
- `0x140194070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140098235`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1400982a7`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14009833b`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140098454`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x140098517`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1400985fa`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1400982e6`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1400982e6`

## string_xrefs

- `0x1400981cd`: `com.microsoft.windows.extension.desktopspotlight`
- `0x140098695`: `IsDesktopSpotlightImageByPath=%d %ws`
- `0x140098549`: `IsDesktopSpotlightImageByPath=%d - image not located in microsoft folder %ws`
- `0x140098486`: `IsDesktopSpotlightImageByPath=%d - image not located in irisservice folder %ws`
- `0x140098371`: `IsDesktopSpotlightImageByPath=%d - image not located in LocalAppData %ws`
- `0x14009846d`: `irisservice`

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
0x14009819c  mov     [rsp-8+arg_8], rbx
0x1400981a1  mov     [rsp-8+arg_10], rdi
0x1400981a6  push    rbp
0x1400981a7  lea     rbp, [rsp-0E0h]
0x1400981af  sub     rsp, 1E0h
0x1400981b6  mov     rax, cs:__security_cookie
0x1400981bd  xor     rax, rsp
0x1400981c0  mov     [rbp+0E0h+var_8], rax
0x1400981c7  mov     rbx, rcx
0x1400981ca  xor     dil, dil
0x1400981cd  lea     rdx, aComMicrosoftWi; "com.microsoft.windows.extension.desktop"...
0x1400981d4  lea     rcx, [rbp+0E0h+var_C8]; this
0x1400981d8  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1400981dd  lea     rdx, [rbp+0E0h+var_C8]
0x1400981e1  lea     rcx, [rsp+1E0h+var_1A8]; struct winrt::param::hstring *
0x1400981e6  call    ?Find@AppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::Find(winrt::param::hstring const &)
0x1400981eb  nop
0x1400981ec  cmp     [rsp+1E0h+var_1A8], 0
0x1400981f2  jz      loc_140098684
0x1400981f8  mov     rdx, rbx
0x1400981fb  lea     rcx, [rsp+1E0h+var_168]
0x140098200  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140098205  nop
0x140098206  lea     r9, [rsp+1E0h+var_168]
0x14009820b  cmp     [rbp+0E0h+var_150], 7
0x140098210  cmova   r9, [rsp+1E0h+var_168]
0x140098216  lea     rdx, [rsp+1E0h+var_190]
0x14009821b  lea     rcx, [rsp+1E0h+var_168]
0x140098220  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x140098225  lea     rdx, [rsp+1E0h+var_168]
0x14009822a  cmp     [rbp+0E0h+var_150], 7
0x14009822f  cmova   rdx, [rsp+1E0h+var_168]
0x140098235  mov     rcx, cs:__imp__o_towlower
0x14009823c  mov     [rsp+1E0h+var_1C0], rcx
0x140098241  mov     r8, [rax]
0x140098244  lea     rcx, [rsp+1E0h+var_1A0]
0x140098249  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x14009824e  lea     rdx, [rsp+1E0h+var_190]
0x140098253  lea     rcx, [rsp+1E0h+var_1A8]
0x140098258  call    ?PackageFamilyName@?$consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension2@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension2<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension>::PackageFamilyName(void)
0x14009825d  nop
0x14009825e  mov     rcx, rax; this
0x140098261  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x140098266  mov     rdx, rax
0x140098269  lea     rcx, [rbp+0E0h+var_148]
0x14009826d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140098272  nop
0x140098273  lea     rcx, [rsp+1E0h+var_190]
0x140098278  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x14009827d  lea     r9, [rbp+0E0h+var_148]
0x140098281  cmp     [rbp+0E0h+var_130], 7
0x140098286  cmova   r9, [rbp+0E0h+var_148]
0x14009828b  lea     rdx, [rsp+1E0h+var_1A0]
0x140098290  lea     rcx, [rbp+0E0h+var_148]
0x140098294  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x140098299  lea     rdx, [rbp+0E0h+var_148]
0x14009829d  cmp     [rbp+0E0h+var_130], 7
0x1400982a2  cmova   rdx, [rbp+0E0h+var_148]
0x1400982a7  mov     rcx, cs:__imp__o_towlower
0x1400982ae  mov     [rsp+1E0h+var_1C0], rcx
0x1400982b3  mov     r8, [rax]
0x1400982b6  lea     rcx, [rsp+1E0h+var_198]
0x1400982bb  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x1400982c0  mov     [rsp+1E0h+ppszPath], 0
0x1400982c9  xor     edx, edx
0x1400982cb  lea     rcx, [rsp+1E0h+ppszPath]
0x1400982d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400982d5  lea     r9, [rsp+1E0h+ppszPath]; ppszPath
0x1400982da  xor     r8d, r8d; hToken
0x1400982dd  xor     edx, edx; dwFlags
0x1400982df  lea     rcx, FOLDERID_LocalAppData; rfid
0x1400982e6  call    cs:__imp_SHGetKnownFolderPath
0x1400982ed  nop     dword ptr [rax+rax+00h]
0x1400982f2  test    eax, eax
0x1400982f4  js      loc_140098664
0x1400982fa  mov     rdx, [rsp+1E0h+ppszPath]
0x1400982ff  lea     rcx, [rsp+1E0h+var_188]
0x140098304  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140098309  nop
0x14009830a  lea     r9, [rsp+1E0h+var_188]
0x14009830f  cmp     [rsp+1E0h+var_170], 7
0x140098315  cmova   r9, [rsp+1E0h+var_188]
0x14009831b  lea     rdx, [rsp+1E0h+var_198]
0x140098320  lea     rcx, [rsp+1E0h+var_188]
0x140098325  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x14009832a  lea     rdx, [rsp+1E0h+var_188]
0x14009832f  cmp     [rsp+1E0h+var_170], 7
0x140098335  cmova   rdx, [rsp+1E0h+var_188]
0x14009833b  mov     rcx, cs:__imp__o_towlower
0x140098342  mov     [rsp+1E0h+var_1C0], rcx
0x140098347  mov     r8, [rax]
0x14009834a  lea     rcx, [rsp+1E0h+var_1A0]
0x14009834f  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x140098354  lea     r9, [rsp+1E0h+var_188]
0x140098359  mov     r8, [rsp+1E0h+var_178]
0x14009835e  lea     rcx, [rsp+1E0h+var_168]
0x140098363  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0AEBV12@@Z; std::wstring::compare(unsigned __int64,unsigned __int64,std::wstring const &)
0x140098368  test    eax, eax
0x14009836a  jz      short loc_1400983BA
0x14009836c  mov     r8, rbx
0x14009836f  xor     edx, edx
0x140098371  lea     rcx, aIsdesktopspotl_2; "IsDesktopSpotlightImageByPath=%d - imag"...
0x140098378  call    ?TraceLoggingInfo@DesktopSpotlightLogonTelemetry@@SAXPEBDZZ; DesktopSpotlightLogonTelemetry::TraceLoggingInfo(char const *,...)
0x14009837d  nop
0x14009837e  lea     rcx, [rsp+1E0h+var_188]; void *
0x140098383  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140098388  nop
0x140098389  lea     rcx, [rsp+1E0h+ppszPath]
0x14009838e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140098393  nop
0x140098394  lea     rcx, [rbp+0E0h+var_148]; void *
0x140098398  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009839d  nop
0x14009839e  lea     rcx, [rsp+1E0h+var_168]; void *
0x1400983a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400983a8  nop
0x1400983a9  lea     rcx, [rsp+1E0h+var_1A8]
0x1400983ae  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1400983b3  xor     al, al
0x1400983b5  jmp     loc_1400986A4
0x1400983ba  lea     rdx, [rsp+1E0h+var_168]
0x1400983bf  lea     rcx, [rbp+0E0h+var_68]
0x1400983c3  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x1400983c8  nop
0x1400983c9  lea     rdx, [rbp+0E0h+var_88]
0x1400983cd  mov     rcx, rax
0x1400983d0  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x1400983d5  nop
0x1400983d6  lea     rdx, [rbp+0E0h+var_A8]
0x1400983da  mov     rcx, rax
0x1400983dd  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x1400983e2  nop
0x1400983e3  lea     rcx, [rbp+0E0h+var_88]; void *
0x1400983e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400983ec  nop
0x1400983ed  lea     rcx, [rbp+0E0h+var_68]; void *
0x1400983f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400983f6  lea     rdx, [rbp+0E0h+var_48]
0x1400983fd  lea     rcx, [rbp+0E0h+var_A8]
0x140098401  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x140098406  nop
0x140098407  cmp     qword ptr [rax+18h], 7
0x14009840c  jbe     short loc_140098411
0x14009840e  mov     rax, [rax]
0x140098411  mov     rdx, rax
0x140098414  lea     rcx, [rbp+0E0h+var_128]
0x140098418  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14009841d  nop
0x14009841e  lea     rcx, [rbp+0E0h+var_48]; void *
0x140098425  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009842a  lea     r9, [rbp+0E0h+var_128]
0x14009842e  cmp     [rbp+0E0h+var_110], 7
0x140098433  cmova   r9, [rbp+0E0h+var_128]
0x140098438  lea     rdx, [rsp+1E0h+var_198]
0x14009843d  lea     rcx, [rbp+0E0h+var_128]
0x140098441  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x140098446  lea     rdx, [rbp+0E0h+var_128]
0x14009844a  cmp     [rbp+0E0h+var_110], 7
0x14009844f  cmova   rdx, [rbp+0E0h+var_128]
0x140098454  mov     rcx, cs:__imp__o_towlower
0x14009845b  mov     [rsp+1E0h+var_1C0], rcx
0x140098460  mov     r8, [rax]
0x140098463  lea     rcx, [rsp+1E0h+var_1A0]
0x140098468  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x14009846d  lea     rdx, aIrisservice; "irisservice"
0x140098474  lea     rcx, [rbp+0E0h+var_128]
0x140098478  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x14009847d  test    eax, eax
0x14009847f  jz      short loc_1400984AB
0x140098481  mov     r8, rbx
0x140098484  xor     edx, edx
0x140098486  lea     rcx, aIsdesktopspotl; "IsDesktopSpotlightImageByPath=%d - imag"...
0x14009848d  call    ?TraceLoggingInfo@DesktopSpotlightLogonTelemetry@@SAXPEBDZZ; DesktopSpotlightLogonTelemetry::TraceLoggingInfo(char const *,...)
0x140098492  nop
0x140098493  lea     rcx, [rbp+0E0h+var_128]; void *
0x140098497  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009849c  nop
0x14009849d  lea     rcx, [rbp+0E0h+var_A8]; void *
0x1400984a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400984a6  jmp     loc_14009837E
0x1400984ab  lea     rdx, [rbp+0E0h+var_C8]
0x1400984af  lea     rcx, [rbp+0E0h+var_A8]
0x1400984b3  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x1400984b8  nop
0x1400984b9  lea     rdx, [rbp+0E0h+var_48]
0x1400984c0  lea     rcx, [rbp+0E0h+var_C8]
0x1400984c4  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x1400984c9  nop
0x1400984ca  cmp     qword ptr [rax+18h], 7
0x1400984cf  jbe     short loc_1400984D4
0x1400984d1  mov     rax, [rax]
0x1400984d4  mov     rdx, rax
0x1400984d7  lea     rcx, [rbp+0E0h+var_108]
0x1400984db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400984e0  nop
0x1400984e1  lea     rcx, [rbp+0E0h+var_48]; void *
0x1400984e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400984ed  lea     r9, [rbp+0E0h+var_108]
0x1400984f1  cmp     [rbp+0E0h+var_F0], 7
0x1400984f6  cmova   r9, [rbp+0E0h+var_108]
0x1400984fb  lea     rdx, [rsp+1E0h+var_198]
0x140098500  lea     rcx, [rbp+0E0h+var_108]
0x140098504  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x140098509  lea     rdx, [rbp+0E0h+var_108]
0x14009850d  cmp     [rbp+0E0h+var_F0], 7
0x140098512  cmova   rdx, [rbp+0E0h+var_108]
0x140098517  mov     rcx, cs:__imp__o_towlower
0x14009851e  mov     [rsp+1E0h+var_1C0], rcx
0x140098523  mov     r8, [rax]
0x140098526  lea     rcx, [rsp+1E0h+var_1A0]
0x14009852b  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x140098530  lea     rdx, aMicrosoft; "microsoft"
0x140098537  lea     rcx, [rbp+0E0h+var_108]
0x14009853b  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x140098540  test    eax, eax
0x140098542  jz      short loc_14009856E
0x140098544  mov     r8, rbx
0x140098547  xor     edx, edx
0x140098549  lea     rcx, aIsdesktopspotl_3; "IsDesktopSpotlightImageByPath=%d - imag"...
0x140098550  call    ?TraceLoggingInfo@DesktopSpotlightLogonTelemetry@@SAXPEBDZZ; DesktopSpotlightLogonTelemetry::TraceLoggingInfo(char const *,...)
0x140098555  nop
0x140098556  lea     rcx, [rbp+0E0h+var_108]; void *
0x14009855a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009855f  nop
0x140098560  lea     rcx, [rbp+0E0h+var_C8]; void *
0x140098564  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140098569  jmp     loc_140098493
0x14009856e  lea     rdx, [rbp+0E0h+var_28]
0x140098575  lea     rcx, [rbp+0E0h+var_C8]
0x140098579  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x14009857e  nop
0x14009857f  lea     rdx, [rbp+0E0h+var_88]
0x140098583  mov     rcx, rax
0x140098586  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x14009858b  nop
0x14009858c  lea     rdx, [rbp+0E0h+var_68]
0x140098590  mov     rcx, rax
0x140098593  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x140098598  nop
0x140098599  cmp     qword ptr [rax+18h], 7
0x14009859e  jbe     short loc_1400985A3
0x1400985a0  mov     rax, [rax]
0x1400985a3  mov     rdx, rax
0x1400985a6  lea     rcx, [rbp+0E0h+var_E8]
0x1400985aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400985af  nop
0x1400985b0  lea     rcx, [rbp+0E0h+var_68]; void *
0x1400985b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400985b9  nop
0x1400985ba  lea     rcx, [rbp+0E0h+var_88]; void *
0x1400985be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400985c3  nop
0x1400985c4  lea     rcx, [rbp+0E0h+var_28]; void *
0x1400985cb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400985d0  lea     r9, [rbp+0E0h+var_E8]
0x1400985d4  cmp     [rbp+0E0h+var_D0], 7
0x1400985d9  cmova   r9, [rbp+0E0h+var_E8]
0x1400985de  lea     rdx, [rsp+1E0h+var_198]
0x1400985e3  lea     rcx, [rbp+0E0h+var_E8]
0x1400985e7  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1400985ec  lea     rdx, [rbp+0E0h+var_E8]
0x1400985f0  cmp     [rbp+0E0h+var_D0], 7
0x1400985f5  cmova   rdx, [rbp+0E0h+var_E8]
0x1400985fa  mov     rcx, cs:__imp__o_towlower
0x140098601  mov     [rsp+1E0h+var_1C0], rcx
0x140098606  mov     r8, [rax]
0x140098609  lea     rcx, [rsp+1E0h+var_1A0]
0x14009860e  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x140098613  lea     rdx, [rbp+0E0h+var_148]
0x140098617  lea     rcx, [rbp+0E0h+var_E8]
0x14009861b  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x140098620  nop
0x140098621  test    eax, eax
0x140098623  setz    dil
0x140098627  lea     rcx, [rbp+0E0h+var_E8]; void *
0x14009862b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140098630  nop
0x140098631  lea     rcx, [rbp+0E0h+var_108]; void *
0x140098635  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009863a  nop
0x14009863b  lea     rcx, [rbp+0E0h+var_C8]; void *
0x14009863f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140098644  nop
0x140098645  lea     rcx, [rbp+0E0h+var_128]; void *
0x140098649  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009864e  nop
0x14009864f  lea     rcx, [rbp+0E0h+var_A8]; void *
0x140098653  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140098658  nop
0x140098659  lea     rcx, [rsp+1E0h+var_188]; void *
0x14009865e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140098663  nop
0x140098664  lea     rcx, [rsp+1E0h+ppszPath]
0x140098669  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14009866e  nop
0x14009866f  lea     rcx, [rbp+0E0h+var_148]; void *
0x140098673  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140098678  nop
0x140098679  lea     rcx, [rsp+1E0h+var_168]; void *
0x14009867e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
