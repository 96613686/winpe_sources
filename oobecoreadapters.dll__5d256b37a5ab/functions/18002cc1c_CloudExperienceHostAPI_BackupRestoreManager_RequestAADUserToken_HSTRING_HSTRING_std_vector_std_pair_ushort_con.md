# CloudExperienceHostAPI::BackupRestoreManager::_RequestAADUserToken(HSTRING__ *,HSTRING__ *,std::vector<std::pair<ushort const *,ushort const *>,std::allocator<std::pair<ushort const *,ushort const *>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18002cc1c`
- end: `0x18002d65f`
- name: `?_RequestAADUserToken@BackupRestoreManager@CloudExperienceHostAPI@@CAJPEAUHSTRING__@@0AEBV?$vector@U?$pair@PEBGPEBG@std@@V?$allocator@U?$pair@PEBGPEBG@std@@@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `2627`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180024830`
- `0x180024a54`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009100`
- `0x180009760`
- `0x18000a4f8`
- `0x180011db0`
- `0x180015544`
- `0x18002045c`
- `0x18002059c`
- `0x180024258`
- `0x18002c984`
- `0x18002cc1c`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002cc81`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002ce1f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002cc81`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002ce1f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18002d120`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18002d120`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x18002d12e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x18002d12e`

## string_xrefs

- `0x18002d64d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002cc5d`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x18002cdf9`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x18002cc97`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002cd15`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002cd67`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002cdc2`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002ce35`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002ce88`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002ceda`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002cf8d`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002d005`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002d0ab`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002d1c2`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002d225`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002d2d3`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002d39d`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002d3e2`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002d4af`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002d51c`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall CloudExperienceHostAPI::BackupRestoreManager::_RequestAADUserToken(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  int ActivationFactory; // eax
  signed int v9; // ebx
  __int64 *v10; // rsi
  __int64 (__fastcall *v11)(__int64 *, _QWORD, __int64, __int64 *); // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdi
  int DefaultWebAccount; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r14
  __int64 v24; // r15
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rdi
  __int64 v32; // rdx
  unsigned __int64 v33; // r9
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r9
  bool v38; // sf
  HWND ForegroundWindow; // rbx
  int v40; // eax
  __int64 v41; // rax
  int v42; // eax
  __int64 v43; // rdi
  __int64 v44; // rdx
  unsigned __int64 v45; // r9
  int v46; // eax
  int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // r9
  bool v50; // sf
  int v51; // eax
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, __int64); // rbx
  __int64 v56; // rax
  int v57; // eax
  int v58; // eax
  __int64 v59; // rdx
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, __int64); // rbx
  __int64 v62; // rax
  int v64; // [rsp+20h] [rbp-E0h]
  __int64 v65; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v66; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v67; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v68; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v69; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v70; // [rsp+68h] [rbp-98h] BYREF
  __int64 v71; // [rsp+70h] [rbp-90h] BYREF
  __int64 v72; // [rsp+78h] [rbp-88h] BYREF
  __int64 v73; // [rsp+80h] [rbp-80h] BYREF
  __int64 v74; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v75; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v76[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v77; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v78; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v79; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v80; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v81; // [rsp+C0h] [rbp-40h] BYREF
  int v82; // [rsp+C8h] [rbp-38h] BYREF
  int v83; // [rsp+CCh] [rbp-34h] BYREF
  int v84; // [rsp+D0h] [rbp-30h] BYREF
  int v85; // [rsp+D4h] [rbp-2Ch] BYREF
  __int64 v86; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v87; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER v88; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v89; // [rsp+100h] [rbp+0h]
  __int64 *v90; // [rsp+108h] [rbp+8h] BYREF
  __int64 v91; // [rsp+110h] [rbp+10h] BYREF
  char v92; // [rsp+118h] [rbp+18h]
  HSTRING_HEADER hstringHeader; // [rsp+128h] [rbp+28h] BYREF
  __int64 v94; // [rsp+140h] [rbp+40h]
  _BYTE v95[32]; // [rsp+148h] [rbp+48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v94 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  v81 = 0;
  ActivationFactory = RoGetActivationFactory(v94, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v81);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x225,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v64);
LABEL_124:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v81);
    return (unsigned int)v9;
  }
  v65 = 0;
  v10 = v81;
  v11 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64 *))(*v81 + 96);
  v65 = 0;
  v12 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v90, off_180087690) + 24);
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v95, off_1800876A0);
  v14 = v11(v10, *(_QWORD *)(v13 + 24), v12, &v65);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)v14,
      v64);
LABEL_123:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v65);
    goto LABEL_124;
  }
  v66 = 0;
  v15 = v65;
  v9 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(v65);
  if ( v9 >= 0 )
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 64LL))(v15, &v66);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)v9,
      v64);
LABEL_122:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v66);
    goto LABEL_123;
  }
  if ( !v66 )
  {
LABEL_10:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v66);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v65);
    v9 = -2147023728;
    goto LABEL_124;
  }
  v67 = 0;
  DefaultWebAccount = CloudExperienceHostAPI::BackupRestoreManager::_GetDefaultWebAccount(&v67);
  v9 = DefaultWebAccount;
  if ( DefaultWebAccount < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)DefaultWebAccount,
      v64);
LABEL_121:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v67);
    goto LABEL_122;
  }
  if ( !v67 )
  {
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v67);
    goto LABEL_10;
  }
  v89 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v88,
    L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
    0x39u,
    0x38u);
  v69 = 0;
  v17 = RoGetActivationFactory(v89, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v69);
  v9 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23A,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)v17,
      v64);
LABEL_120:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v69);
    v89 = 0;
    goto LABEL_121;
  }
  v68 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v69 + 56LL))(v69, v66, a2, a1);
  v9 = v18;
  if ( v18 < 0 )
  {
    v19 = (unsigned int)v18;
    v20 = 579;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)v19,
      0);
LABEL_119:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v68);
    goto LABEL_120;
  }
  if ( !v68 )
  {
    v9 = -2147024882;
    v19 = 2147942414LL;
    v20 = 580;
    goto LABEL_19;
  }
  v70 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v68 + 80LL))(v68, &v70);
  v9 = v21;
  if ( v21 < 0 )
  {
    v22 = 584;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)v21,
      0);
    goto LABEL_118;
  }
  v76[0] = 0;
  v23 = *a3;
  v24 = a3[1];
  while ( v23 != v24 )
  {
    v25 = v70;
    v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v70 + 80LL);
    v27 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v95, v23 + 8) + 24);
    v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v90, v23);
    v21 = v26(v25, *(_QWORD *)(v28 + 24), v27, v76);
    v9 = v21;
    if ( v21 < 0 )
    {
      v22 = 593;
      goto LABEL_24;
    }
    v23 += 16;
  }
  v72 = 0;
  v29 = *v81;
  v72 = 0;
  v30 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct Windows::Security::Credentials::IWebAccount *, __int64 *))(v29 + 56))(
          v81,
          v68,
          v67,
          &v72);
  v9 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x259,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)v30,
      0);
LABEL_117:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v72);
LABEL_118:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v70);
    goto LABEL_119;
  }
  v71 = 0;
  v90 = &v71;
  v91 = 0;
  v92 = 1;
  v31 = v72;
  v9 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(
         v72,
         8);
  if ( v9 >= 0 )
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 64LL))(v31, &v91);
  wil::details::out_param_t<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult,wil::err_exception_policy>>(&v90);
  if ( v9 < 0 )
  {
    v32 = 604;
LABEL_36:
    v33 = (unsigned int)v9;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)v33,
      0);
LABEL_116:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v71);
    goto LABEL_117;
  }
  v82 = 0;
  v34 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v71 + 56LL))(v71, &v82);
  v9 = v34;
  if ( v34 < 0 )
  {
    v33 = (unsigned int)v34;
    v32 = 608;
    goto LABEL_37;
  }
  switch ( v82 )
  {
    case 0:
      v80 = 0;
      v57 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v71 + 48LL))(v71, &v80);
      v9 = v57;
      if ( v57 >= 0 )
      {
        v87 = 0;
        v58 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v80 + 48LL))(v80, 0, &v87);
        v9 = v58;
        if ( v58 >= 0 )
        {
          v60 = v87;
          v61 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 48LL);
          v62 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(a4);
          v58 = v61(v60, v62);
          v9 = v58;
          if ( v58 >= 0 )
          {
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v87);
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v80);
            goto LABEL_126;
          }
          v59 = 646;
        }
        else
        {
          v59 = 643;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v59,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
          (const char *)(unsigned int)v58,
          0);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v87);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27F,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
          (const char *)(unsigned int)v57,
          0);
      }
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v80);
      goto LABEL_116;
    case 1:
      v9 = -2147418113;
      v32 = 632;
      goto LABEL_36;
    case 2:
      v9 = -2147483636;
      v32 = 627;
      goto LABEL_36;
  }
  if ( v82 != 3 )
  {
    if ( (unsigned int)(v82 - 4) >= 2 )
    {
      v9 = -2147418113;
      v32 = 746;
      goto LABEL_36;
    }
    v83 = 0;
    v77 = 0;
    v35 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v71 + 64LL))(v71, &v77);
    v9 = v35;
    if ( v35 >= 0 )
    {
      if ( !v77 )
      {
        v9 = -2147418113;
        v37 = 2147549183LL;
        v36 = 622;
        goto LABEL_49;
      }
      v35 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v77 + 48LL))(v77, &v83);
      v9 = v35;
      if ( v35 >= 0 )
      {
        v9 = v83;
        v38 = v83 < 0;
        if ( v83 > 0 )
        {
          v9 = (unsigned __int16)v83 | 0x80070000;
          v38 = 1;
        }
        if ( !v38 )
          goto LABEL_50;
        v37 = (unsigned int)v9;
        v36 = 620;
LABEL_49:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v36,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
          (const char *)v37,
          0);
LABEL_50:
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v77);
        goto LABEL_116;
      }
      v36 = 619;
    }
    else
    {
      v36 = 616;
    }
    v37 = (unsigned int)v35;
    goto LABEL_49;
  }
  ForegroundWindow = GetForegroundWindow();
  if ( !ForegroundWindow )
  {
    ForegroundWindow = GetDesktopWindow();
    if ( !ForegroundWindow )
    {
      v9 = -2147024890;
      v32 = 666;
      goto LABEL_36;
    }
  }
  v75 = 0;
  v40 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 **))*v81)(
          v81,
          &GUID_f4b8e804_811e_4436_b69c_44cb67b72084,
          &v75);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v40,
      0);
  v74 = 0;
  v41 = *v75;
  v74 = 0;
  v42 = (*(__int64 (__fastcall **)(__int64 *, HWND, __int64, struct Windows::Security::Credentials::IWebAccount *))(v41 + 56))(
          v75,
          ForegroundWindow,
          v68,
          v67);
  v9 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)v42,
      (int)&GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
LABEL_65:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v74);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v75);
    goto LABEL_116;
  }
  v73 = 0;
  v43 = v74;
  v9 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(
         v74,
         0);
  if ( v9 >= 0 )
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 64LL))(v43, &v73);
  if ( v9 < 0 )
  {
    v44 = 683;
LABEL_70:
    v45 = (unsigned int)v9;
LABEL_71:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)v45,
      (int)&GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
LABEL_72:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v73);
    goto LABEL_65;
  }
  v84 = 0;
  v46 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v73 + 56LL))(v73, &v84);
  v9 = v46;
  if ( v46 < 0 )
  {
    v45 = (unsigned int)v46;
    v44 = 686;
    goto LABEL_71;
  }
  if ( v84 )
  {
    switch ( v84 )
    {
      case 1:
        v9 = -2147023673;
        v44 = 716;
        goto LABEL_70;
      case 2:
        v9 = -2147483636;
        v44 = 706;
        goto LABEL_70;
      case 3:
        v9 = -2147418113;
        v44 = 711;
        goto LABEL_70;
    }
    if ( (unsigned int)(v84 - 4) >= 2 )
    {
      v9 = -2147418113;
      v44 = 737;
      goto LABEL_70;
    }
    v85 = 0;
    v78 = 0;
    v47 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 64LL))(v73, &v78);
    v9 = v47;
    if ( v47 >= 0 )
    {
      if ( !v78 )
      {
        v9 = -2147418113;
        v49 = 2147549183LL;
        v48 = 701;
        goto LABEL_84;
      }
      v47 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v78 + 48LL))(v78, &v85);
      v9 = v47;
      if ( v47 >= 0 )
      {
        v9 = v85;
        v50 = v85 < 0;
        if ( v85 > 0 )
        {
          v9 = (unsigned __int16)v85 | 0x80070000;
          v50 = 1;
        }
        if ( !v50 )
          goto LABEL_85;
        v49 = (unsigned int)v9;
        v48 = 699;
LABEL_84:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v48,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
          (const char *)v49,
          (int)&GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
LABEL_85:
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v78);
        goto LABEL_72;
      }
      v48 = 698;
    }
    else
    {
      v48 = 695;
    }
    v49 = (unsigned int)v47;
    goto LABEL_84;
  }
  v79 = 0;
  v51 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 48LL))(v73, &v79);
  v9 = v51;
  if ( v51 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D3,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)v51,
      (int)&GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
LABEL_99:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v79);
    goto LABEL_72;
  }
  v86 = 0;
  v52 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v79 + 48LL))(v79, 0, &v86);
  v9 = v52;
  if ( v52 < 0 )
  {
    v53 = 727;
LABEL_102:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v53,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)v52,
      (int)&GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v86);
    goto LABEL_99;
  }
  v54 = v86;
  v55 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v86 + 48LL);
  v56 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(a4);
  v52 = v55(v54, v56);
  v9 = v52;
  if ( v52 < 0 )
  {
    v53 = 730;
    goto LABEL_102;
  }
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v86);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v79);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v73);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v74);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v75);
LABEL_126:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v71);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v72);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v70);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v68);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v69);
  v89 = 0;
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v67);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v66);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v65);
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v81);
  return 0;
}

```

## disassembly

```asm
0x18002cc1c  push    rbp
0x18002cc1e  push    rbx
0x18002cc1f  push    rsi
0x18002cc20  push    rdi
0x18002cc21  push    r12
0x18002cc23  push    r13
0x18002cc25  push    r14
0x18002cc27  push    r15
0x18002cc29  lea     rbp, [rsp-78h]
0x18002cc2e  sub     rsp, 178h
0x18002cc35  mov     rax, cs:__security_cookie
0x18002cc3c  xor     rax, rsp
0x18002cc3f  mov     [rbp+0B0h+var_48], rax
0x18002cc43  mov     r13, r9
0x18002cc46  mov     r15, r8
0x18002cc49  mov     r12, rdx
0x18002cc4c  mov     r14, rcx
0x18002cc4f  xor     edi, edi
0x18002cc51  mov     [rbp+0B0h+var_70], rdi
0x18002cc55  lea     r9d, [rdi+45h]; unsigned int
0x18002cc59  lea     r8d, [rdi+46h]; unsigned int
0x18002cc5d  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18002cc64  lea     rcx, [rbp+0B0h+hstringHeader]; hstringHeader
0x18002cc68  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002cc6d  nop
0x18002cc6e  mov     [rbp+0B0h+var_F0], rdi
0x18002cc72  lea     r8, [rbp+0B0h+var_F0]
0x18002cc76  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x18002cc7d  mov     rcx, [rbp+0B0h+var_70]
0x18002cc81  call    cs:__imp_RoGetActivationFactory
0x18002cc87  mov     ebx, eax
0x18002cc89  test    eax, eax
0x18002cc8b  jns     short loc_18002CCAD
0x18002cc8d  mov     rcx, [rbp+0B8h]; this
0x18002cc94  mov     r9d, eax; char *
0x18002cc97  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002cc9e  mov     edx, 225h; void *
0x18002cca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cca8  jmp     loc_18002D5A0
0x18002ccad  mov     [rsp+1B0h+var_170], rdi
0x18002ccb2  mov     rsi, [rbp+0B0h+var_F0]
0x18002ccb6  mov     rax, [rsi]
0x18002ccb9  mov     rdi, [rax+60h]
0x18002ccbd  mov     [rsp+1B0h+var_170], 0
0x18002ccc6  lea     rdx, off_180087690; "organizations"
0x18002cccd  lea     rcx, [rbp+0B0h+var_A8]
0x18002ccd1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002ccd6  nop
0x18002ccd7  mov     rbx, [rax+18h]
0x18002ccdb  lea     rdx, off_1800876A0; "https://login.microsoft.com"
0x18002cce2  lea     rcx, [rbp+0B0h+var_68]
0x18002cce6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002cceb  nop
0x18002ccec  lea     r9, [rsp+1B0h+var_170]
0x18002ccf1  mov     r8, rbx
0x18002ccf4  mov     rdx, [rax+18h]
0x18002ccf8  mov     rcx, rsi
0x18002ccfb  mov     rax, rdi
0x18002ccfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd03  mov     ebx, eax
0x18002cd05  xor     esi, esi
0x18002cd07  test    eax, eax
0x18002cd09  jns     short loc_18002CD2B
0x18002cd0b  mov     rcx, [rbp+0B8h]; this
0x18002cd12  mov     r9d, eax; char *
0x18002cd15  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002cd1c  mov     edx, 22Ch; void *
0x18002cd21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd26  jmp     loc_18002D595
0x18002cd2b  mov     [rsp+1B0h+var_168], rsi
0x18002cd30  mov     rdi, [rsp+1B0h+var_170]
0x18002cd35  mov     rcx, rdi
0x18002cd38  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18002cd3d  mov     ebx, eax
0x18002cd3f  test    eax, eax
0x18002cd41  js      short loc_18002CD59
0x18002cd43  mov     rax, [rdi]
0x18002cd46  lea     rdx, [rsp+1B0h+var_168]
0x18002cd4b  mov     rcx, rdi
0x18002cd4e  mov     rax, [rax+40h]
0x18002cd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd57  mov     ebx, eax
0x18002cd59  test    ebx, ebx
0x18002cd5b  jns     short loc_18002CD7D
0x18002cd5d  mov     rcx, [rbp+0B8h]; this
0x18002cd64  mov     r9d, ebx; char *
0x18002cd67  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002cd6e  mov     edx, 22Fh; void *
0x18002cd73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd78  jmp     loc_18002D58A
0x18002cd7d  cmp     [rsp+1B0h+var_168], rsi
0x18002cd82  jnz     short loc_18002CDA3
0x18002cd84  lea     rcx, [rsp+1B0h+var_168]
0x18002cd89  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002cd8e  nop
0x18002cd8f  lea     rcx, [rsp+1B0h+var_170]
0x18002cd94  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002cd99  mov     ebx, 80070490h
0x18002cd9e  jmp     loc_18002D5A0
0x18002cda3  mov     [rsp+1B0h+var_160], rsi
0x18002cda8  lea     rcx, [rsp+1B0h+var_160]; struct Windows::Security::Credentials::IWebAccount **
0x18002cdad  call    ?_GetDefaultWebAccount@BackupRestoreManager@CloudExperienceHostAPI@@CAJPEAPEAUIWebAccount@Credentials@Security@Windows@@@Z; CloudExperienceHostAPI::BackupRestoreManager::_GetDefaultWebAccount(Windows::Security::Credentials::IWebAccount * *)
0x18002cdb2  mov     ebx, eax
0x18002cdb4  test    eax, eax
0x18002cdb6  jns     short loc_18002CDD8
0x18002cdb8  mov     rcx, [rbp+0B8h]; this
0x18002cdbf  mov     r9d, eax; char *
0x18002cdc2  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002cdc9  mov     edx, 234h; void *
0x18002cdce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cdd3  jmp     loc_18002D57F
0x18002cdd8  cmp     [rsp+1B0h+var_160], rsi
0x18002cddd  jnz     short loc_18002CDEB
0x18002cddf  lea     rcx, [rsp+1B0h+var_160]
0x18002cde4  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002cde9  jmp     short loc_18002CD84
0x18002cdeb  mov     [rbp+0B0h+var_B0], rsi
0x18002cdef  mov     r9d, 38h ; '8'; unsigned int
0x18002cdf5  lea     r8d, [r9+1]; unsigned int
0x18002cdf9  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18002ce00  lea     rcx, [rbp+0B0h+var_C8]; hstringHeader
0x18002ce04  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002ce09  nop
0x18002ce0a  mov     [rsp+1B0h+var_150], rsi
0x18002ce0f  lea     r8, [rsp+1B0h+var_150]
0x18002ce14  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x18002ce1b  mov     rcx, [rbp+0B0h+var_B0]
0x18002ce1f  call    cs:__imp_RoGetActivationFactory
0x18002ce25  mov     ebx, eax
0x18002ce27  test    eax, eax
0x18002ce29  jns     short loc_18002CE4B
0x18002ce2b  mov     rcx, [rbp+0B8h]; this
0x18002ce32  mov     r9d, eax; char *
0x18002ce35  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002ce3c  mov     edx, 23Ah; void *
0x18002ce41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce46  jmp     loc_18002D570
0x18002ce4b  mov     [rsp+1B0h+var_158], rsi
0x18002ce50  mov     rcx, [rsp+1B0h+var_150]
0x18002ce55  mov     rax, [rcx]
0x18002ce58  lea     rdx, [rsp+1B0h+var_158]
0x18002ce5d  mov     [rsp+1B0h+var_188], rdx
0x18002ce62  mov     [rsp+1B0h+var_190], esi; int
0x18002ce66  mov     r9, r14
0x18002ce69  mov     r8, r12
0x18002ce6c  mov     rdx, [rsp+1B0h+var_168]
0x18002ce71  mov     rax, [rax+38h]
0x18002ce75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce7a  mov     ebx, eax
0x18002ce7c  test    eax, eax
0x18002ce7e  jns     short loc_18002CEA0
0x18002ce80  mov     r9d, eax; char *
0x18002ce83  mov     edx, 243h; void *
0x18002ce88  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002ce8f  mov     rcx, [rbp+0B8h]; this
0x18002ce96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce9b  jmp     loc_18002D565
0x18002cea0  mov     rcx, [rsp+1B0h+var_158]
0x18002cea5  test    rcx, rcx
0x18002cea8  jnz     short loc_18002CEB9
0x18002ceaa  mov     ebx, 8007000Eh
0x18002ceaf  mov     r9d, ebx
0x18002ceb2  mov     edx, 244h
0x18002ceb7  jmp     short loc_18002CE88
0x18002ceb9  mov     [rsp+1B0h+var_148], rsi
0x18002cebe  mov     rax, [rcx]
0x18002cec1  lea     rdx, [rsp+1B0h+var_148]
0x18002cec6  mov     rax, [rax+50h]
0x18002ceca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cecf  mov     ebx, eax
0x18002ced1  test    eax, eax
0x18002ced3  jns     short loc_18002CEF5
0x18002ced5  mov     edx, 248h; void *
0x18002ceda  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002cee1  mov     r9d, eax; char *
0x18002cee4  mov     rcx, [rbp+0B8h]; this
0x18002ceeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cef0  jmp     loc_18002D55A
0x18002cef5  mov     [rbp+0B0h+var_118], sil
0x18002cef9  mov     r14, [r15]
0x18002cefc  mov     r15, [r15+8]
0x18002cf00  jmp     short loc_18002CF4F
0x18002cf02  mov     rsi, [rsp+1B0h+var_148]
0x18002cf07  mov     rax, [rsi]
0x18002cf0a  mov     rdi, [rax+50h]
0x18002cf0e  lea     rdx, [r14+8]
0x18002cf12  lea     rcx, [rbp+0B0h+var_68]
0x18002cf16  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002cf1b  nop
0x18002cf1c  mov     rbx, [rax+18h]
0x18002cf20  mov     rdx, r14
0x18002cf23  lea     rcx, [rbp+0B0h+var_A8]
0x18002cf27  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002cf2c  nop
0x18002cf2d  lea     r9, [rbp+0B0h+var_118]
0x18002cf31  mov     r8, rbx
0x18002cf34  mov     rdx, [rax+18h]
0x18002cf38  mov     rcx, rsi
0x18002cf3b  mov     rax, rdi
0x18002cf3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf43  mov     ebx, eax
0x18002cf45  xor     esi, esi
0x18002cf47  test    eax, eax
0x18002cf49  js      short loc_18002CFA3
0x18002cf4b  add     r14, 10h
0x18002cf4f  cmp     r14, r15
0x18002cf52  jnz     short loc_18002CF02
0x18002cf54  mov     [rsp+1B0h+var_138], rsi
0x18002cf59  mov     rcx, [rbp+0B0h+var_F0]
0x18002cf5d  mov     rax, [rcx]
0x18002cf60  mov     [rsp+1B0h+var_138], rsi
0x18002cf65  lea     r9, [rsp+1B0h+var_138]
0x18002cf6a  mov     r8, [rsp+1B0h+var_160]
0x18002cf6f  mov     rdx, [rsp+1B0h+var_158]
0x18002cf74  mov     rax, [rax+38h]
0x18002cf78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf7d  mov     ebx, eax
0x18002cf7f  test    eax, eax
0x18002cf81  jns     short loc_18002CFAD
0x18002cf83  mov     rcx, [rbp+0B8h]; this
0x18002cf8a  mov     r9d, eax; char *
0x18002cf8d  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002cf94  mov     edx, 259h; void *
0x18002cf99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cf9e  jmp     loc_18002D54F
0x18002cfa3  mov     edx, 251h
0x18002cfa8  jmp     loc_18002CEDA
0x18002cfad  mov     [rsp+1B0h+var_140], rsi
0x18002cfb2  lea     rax, [rsp+1B0h+var_140]
0x18002cfb7  mov     [rbp+0B0h+var_A8], rax
0x18002cfbb  mov     [rbp+0B0h+var_A0], rsi
0x18002cfbf  mov     [rbp+0B0h+var_98], 1
0x18002cfc3  mov     rdi, [rsp+1B0h+var_138]
0x18002cfc8  mov     edx, 8
0x18002cfcd  mov     rcx, rdi
0x18002cfd0  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18002cfd5  mov     ebx, eax
0x18002cfd7  test    eax, eax
0x18002cfd9  js      short loc_18002CFF0
0x18002cfdb  mov     rax, [rdi]
0x18002cfde  lea     rdx, [rbp+0B0h+var_A0]
0x18002cfe2  mov     rcx, rdi
0x18002cfe5  mov     rax, [rax+40h]
0x18002cfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfee  mov     ebx, eax
0x18002cff0  lea     rcx, [rbp+0B0h+var_A8]
0x18002cff4  call    ??1?$out_param_t@V?$com_ptr_t@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult,wil::err_exception_policy>>(void)
0x18002cff9  test    ebx, ebx
0x18002cffb  jns     short loc_18002D01D
0x18002cffd  mov     edx, 25Ch; void *
0x18002d002  mov     r9d, ebx; char *
0x18002d005  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002d00c  mov     rcx, [rbp+0B8h]; this
0x18002d013  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d018  jmp     loc_18002D544
0x18002d01d  mov     [rbp+0B0h+var_E8], esi
0x18002d020  mov     rcx, [rsp+1B0h+var_140]
0x18002d025  mov     rax, [rcx]
0x18002d028  lea     rdx, [rbp+0B0h+var_E8]
0x18002d02c  mov     rax, [rax+38h]
0x18002d030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d035  mov     ebx, eax
0x18002d037  test    eax, eax
0x18002d039  jns     short loc_18002D045
0x18002d03b  mov     r9d, eax
0x18002d03e  mov     edx, 260h
0x18002d043  jmp     short loc_18002D005
0x18002d045  mov     ecx, [rbp+0B0h+var_E8]
0x18002d048  test    ecx, ecx
0x18002d04a  jz      loc_18002D486
0x18002d050  sub     ecx, 1
0x18002d053  jz      loc_18002D477
0x18002d059  sub     ecx, 1
0x18002d05c  jz      loc_18002D468
0x18002d062  sub     ecx, 1
0x18002d065  jz      loc_18002D120
0x18002d06b  sub     ecx, 1
0x18002d06e  jz      short loc_18002D081
0x18002d070  cmp     ecx, 1
0x18002d073  jz      short loc_18002D081
0x18002d075  mov     ebx, 8000FFFFh
0x18002d07a  mov     edx, 2EAh
0x18002d07f  jmp     short loc_18002D002
0x18002d081  mov     [rbp+0B0h+var_E4], esi
0x18002d084  mov     [rbp+0B0h+var_110], rsi
0x18002d088  mov     rcx, [rsp+1B0h+var_140]
0x18002d08d  mov     rax, [rcx]
0x18002d090  lea     rdx, [rbp+0B0h+var_110]
0x18002d094  mov     rax, [rax+40h]
0x18002d098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d09d  mov     ebx, eax
0x18002d09f  test    eax, eax
0x18002d0a1  jns     short loc_18002D0CD
0x18002d0a3  mov     edx, 268h; void *
0x18002d0a8  mov     r9d, eax; char *
0x18002d0ab  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002d0b2  mov     rcx, [rbp+0B8h]; this
0x18002d0b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d0be  nop
0x18002d0bf  lea     rcx, [rbp+0B0h+var_110]
  ... truncated ...
```
