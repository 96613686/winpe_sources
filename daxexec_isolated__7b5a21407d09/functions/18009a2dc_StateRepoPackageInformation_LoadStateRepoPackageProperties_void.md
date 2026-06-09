# StateRepoPackageInformation::LoadStateRepoPackageProperties(void)

- ea: `0x18009a2dc`
- end: `0x18009adb0`
- name: `?LoadStateRepoPackageProperties@StateRepoPackageInformation@@AEAAXXZ`
- size: `2772`
- prototype: `void __fastcall(StateRepoPackageInformation *__hidden this)`
- caller_count: `5`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180099090`
- `0x180099160`
- `0x180099400`
- `0x180099850`
- `0x18009b230`

## callees

- `0x180004f70`
- `0x180007ee4`
- `0x1800125f4`
- `0x1800164f8`
- `0x180016b98`
- `0x1800190e0`
- `0x18001f808`
- `0x180039d1c`
- `0x18003fd60`
- `0x180098704`
- `0x1800987a8`
- `0x180098bec`
- `0x180098db0`
- `0x180099638`
- `0x18009a2dc`
- `0x18009af44`
- `0x18009b2c4`
- `0x18009b7f8`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a81c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a7fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a7fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a6c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a6c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009a6fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009a770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009a6fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009a770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a8a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a8a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009a86d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009a86d`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18009a651`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18009a651`

## string_xrefs

- `0x18009ac77`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009acd3`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009ad2f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009ad89`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009ad9e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009a3df`: `FileSystemWriteVirtualization`
- `0x18009a422`: `RegistryWriteVirtualization`
- `0x18009a3f5`: `ExcludedDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=44
void __fastcall StateRepoPackageInformation::LoadStateRepoPackageProperties(StateRepoPackageInformation *this)
{
  StateRepoPackageInformation *v1; // r12
  unsigned int v2; // esi
  __int64 v3; // rbx
  __int64 (__fastcall *v4)(__int64, _QWORD, __int64 *); // rdi
  _QWORD *v5; // rax
  __int64 v6; // rax
  int v7; // eax
  unsigned __int8 (__fastcall **v8)(StateRepoPackageInformation *); // r13
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD, __int64 *); // rbx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  unsigned __int64 v14; // r15
  __int64 v15; // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, __int64, __int64 **); // rdi
  __int64 *v21; // rcx
  int v22; // eax
  wil::details::in1diag3 *v23; // rcx
  __int64 *v24; // rbx
  __int64 v25; // rax
  int v26; // eax
  void *v27; // rcx
  int v28; // eax
  int v29; // eax
  wil::details::in1diag3 *v30; // rcx
  int v31; // esi
  void *v32; // rcx
  __int64 *v33; // rdi
  __int64 v34; // r14
  HRESULT v35; // eax
  int v36; // edx
  unsigned int v37; // r8d
  int v38; // eax
  __int64 *v39; // rdi
  __int64 v40; // r14
  HRESULT v41; // eax
  int v42; // edx
  unsigned int v43; // r8d
  int v44; // eax
  int v45; // eax
  __int64 v46; // r15
  __int64 (__fastcall *v47)(__int64, HSTRING *); // r12
  HSTRING v48; // r14
  DWORD LastError; // edi
  int v50; // eax
  PCWSTR StringRawBuffer; // rax
  char *v52; // r8
  int v53; // ecx
  int v54; // edx
  int v55; // eax
  __int64 v56; // rax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  __int64 v60; // rax
  int v61; // eax
  wil::details::in1diag3 *v62; // rcx
  char v63; // r14
  struct IInspectable **v64; // rdi
  struct IInspectable **v65; // r15
  char v66; // cl
  __int64 *v67; // rcx
  _QWORD *v68; // rbx
  _QWORD *v69; // rdi
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  int v73; // [rsp+20h] [rbp-E0h]
  char v74; // [rsp+30h] [rbp-D0h] BYREF
  char v75; // [rsp+31h] [rbp-CFh] BYREF
  char v76; // [rsp+32h] [rbp-CEh] BYREF
  bool v77; // [rsp+33h] [rbp-CDh]
  unsigned int v78; // [rsp+34h] [rbp-CCh]
  struct IInspectable *v79; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v80; // [rsp+40h] [rbp-C0h] BYREF
  int v81; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v82; // [rsp+50h] [rbp-B0h] BYREF
  int v83; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v84; // [rsp+5Ch] [rbp-A4h] BYREF
  HSTRING v85; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v87; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v89; // [rsp+80h] [rbp-80h] BYREF
  __int64 v90; // [rsp+88h] [rbp-78h] BYREF
  __int64 v91; // [rsp+90h] [rbp-70h]
  unsigned int v92; // [rsp+98h] [rbp-68h]
  __int64 *v93; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v94; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v95; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v96; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v97; // [rsp+C0h] [rbp-40h]
  struct IInspectable **v98; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v99; // [rsp+D0h] [rbp-30h]
  StateRepoPackageInformation *v100; // [rsp+D8h] [rbp-28h]
  _QWORD v101[12]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v102[2]; // [rsp+140h] [rbp+40h] BYREF
  int v103; // [rsp+150h] [rbp+50h]
  __int64 v104; // [rsp+158h] [rbp+58h]
  HSTRING_HEADER hstringHeader; // [rsp+160h] [rbp+60h] BYREF
  HSTRING string; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v107[24]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v108; // [rsp+198h] [rbp+98h]
  _QWORD v109[42]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v1 = this;
  v100 = this;
  v2 = 0;
  v78 = 0;
  if ( !*((_BYTE *)this + 156) )
  {
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v109,
      "LoadStateRepoPackageProperties");
    v109[0] = &DesktopAppXProvider::LoadStateRepoPackageProperties::`vftable';
    DesktopAppXProvider::LoadStateRepoPackageProperties::StartActivity((DesktopAppXProvider::LoadStateRepoPackageProperties *)v109);
    wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(&v95);
    v90 = 0;
    v3 = v95;
    v4 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v95 + 176LL);
    v90 = 0;
    v5 = (_QWORD *)((char *)v1 + 8);
    if ( *((_QWORD *)v1 + 4) > 7u )
      v5 = (_QWORD *)*v5;
    v87 = v5;
    v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v107, &v87);
    v7 = v4(v3, *(_QWORD *)(v6 + 24), &v90);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x180,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
        (const char *)(unsigned int)v7,
        v73);
    wil::GetActivationFactory<Windows::Internal::StateRepository::IPackagePropertyStatics>(&v94);
    v101[0] =  StateRepoPackageInformation::`vcall'{56,{flat}};
    v101[1] = (char *)v1 + 157;
    v101[2] = L"FileSystemWriteVirtualization";
    v101[3] = L"ExcludedDirectories";
    v101[4] = L"ExcludedDirectory";
    v101[5] = StateRepoPackageInformation::ParseAndAddExcludedDirectoryElementContent;
    v101[6] =  StateRepoPackageInformation::`vcall'{88,{flat}};
    v101[7] = (char *)v1 + 158;
    v101[8] = L"RegistryWriteVirtualization";
    v101[9] = L"ExcludedKeys";
    v101[10] = L"ExcludedKey";
    v101[11] = StateRepoPackageInformation::ParseAndAddExcludedKeyElementContent;
    v8 = (unsigned __int8 (__fastcall **)(StateRepoPackageInformation *))v101;
    do
    {
      if ( (*v8)(v1) )
      {
        v86 = 0;
        v9 = v94;
        v10 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v94 + 144LL);
        v86 = 0;
        v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v107, v8 + 2);
        v12 = v10(v9, v90, *(_QWORD *)(v11 + 24), &v86);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
            (const char *)(unsigned int)v12,
            v73);
        v83 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v86 + 56LL))(v86, &v83);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1AD,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
            (const char *)(unsigned int)v13,
            v73);
        if ( v83 )
        {
          v96 = 0;
          v14 = 0;
          v97 = 0;
          v15 = v86;
          v91 = v86;
          v92 = 0;
          v93 = 0;
          v81 = 0;
          v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v86 + 56LL))(v86, &v81);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v16,
              v73);
          v77 = 0;
          v102[1] = v15;
          v17 = v81;
          v103 = v81;
          v104 = 0;
          v2 |= 4u;
          v78 = v2;
          v18 = v92;
          while ( (_DWORD)v18 != v17 )
          {
            v19 = v91;
            v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v91 + 48LL);
            v21 = v93;
            if ( v93 )
            {
              v93 = 0;
              (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
              v18 = v92;
            }
            v22 = v20(v19, v18, &v93);
            v23 = retaddr;
            if ( v22 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1CBE,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                (const char *)(unsigned int)v22,
                v73);
            v24 = v93;
            v102[0] = v93;
            if ( v93 )
              (*(void (__fastcall **)(__int64 *))(*v93 + 8))(v93);
            if ( !(unsigned __int8)IsSRDictionaryToPropertySetPresent(v23) )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x48,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                (const char *)0x8000FFFFLL,
                v73);
            v84 = 0;
            pv = 0;
            v25 = *v24;
            hstringHeader.Reserved.Reserved1 = &pv;
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
            hstringHeader.Reserved.Reserved2[16] = 1;
            v26 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, char *))(v25 + 128))(
                    v24,
                    &v84,
                    &hstringHeader.Reserved.Reserved2[8]);
            if ( v26 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4C,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                (const char *)(unsigned int)v26,
                v73);
            if ( hstringHeader.Reserved.Reserved2[16] )
            {
              v27 = *(void **)hstringHeader.Reserved.Reserved1;
              *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
              if ( v27 )
                CoTaskMemFree(v27);
            }
            v87 = 0;
            v28 = SRDictionaryToPropertySet(v84, pv, &v87);
            if ( v28 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4F,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                (const char *)(unsigned int)v28,
                v73);
            v82 = 0;
            v29 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 **))*v87)(
                    v87,
                    &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                    &v82);
            v30 = retaddr;
            if ( v29 < 0 )
              goto LABEL_107;
            v31 = v2 | 0x18;
            v78 = v31;
            if ( v87 )
              (*(void (__fastcall **)(_QWORD *))(*v87 + 16LL))(v87);
            v32 = pv;
            pv = 0;
            if ( v32 )
              CoTaskMemFree(v32);
            v74 = 0;
            v33 = v82;
            v34 = *v82;
            string = 0;
            v35 = WindowsCreateStringReference(L"#text", 5u, &hstringHeader, &string);
            if ( v35 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v35, v36, v37);
LABEL_107:
              wil::details::in1diag3::Throw_Hr(
                v30,
                (void *)0x1CBE,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                (const char *)(unsigned int)v29,
                v73);
            }
            v38 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, char *))(v34 + 64))(v33, string, &v74);
            if ( v38 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1D7,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                (const char *)(unsigned int)v38,
                v73);
            if ( v74 )
            {
              v79 = 0;
              v39 = v82;
              v40 = *v82;
              v79 = 0;
              string = 0;
              v41 = WindowsCreateStringReference(L"#text", 5u, &hstringHeader, &string);
              if ( v41 < 0 )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v41, v42, v43);
LABEL_100:
                wil::details::in1diag3::Throw_Hr(
                  v62,
                  (void *)0x20B,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v61,
                  v73);
              }
              v44 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct IInspectable **))(v40 + 48))(
                      v39,
                      string,
                      &v79);
              if ( v44 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1DC,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v44,
                  v73);
              v85 = 0;
              v80 = 0;
              v45 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))v79->lpVtbl->QueryInterface)(
                      v79,
                      &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
                      &v80);
              if ( v45 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1CBE,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                  (const char *)(unsigned int)v45,
                  v73);
              v31 |= 0x20u;
              v78 = v31;
              v46 = v80;
              v47 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v80 + 152LL);
              v48 = v85;
              if ( v85 )
              {
                LastError = GetLastError();
                WindowsDeleteString(v48);
                SetLastError(LastError);
              }
              v85 = 0;
              v50 = v47(v46, &v85);
              if ( v50 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1DF,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v50,
                  v73);
              if ( v80 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
              StringRawBuffer = WindowsGetStringRawBuffer(v85, 0);
              v52 = (char *)((char *)L"disabled" - (char *)StringRawBuffer);
              do
              {
                v53 = *(unsigned __int16 *)&v52[(_QWORD)StringRawBuffer];
                v54 = *StringRawBuffer - v53;
                if ( v54 )
                  break;
                ++StringRawBuffer;
              }
              while ( v53 );
              v77 = v54 == 0;
              if ( v85 )
                WindowsDeleteString(v85);
              if ( v79 )
                ((void (__fastcall *)(struct IInspectable *))v79->lpVtbl->Release)(v79);
              v1 = v100;
            }
            else
            {
              Microsoft::WRL::Wrappers::HStringReference::HStringReference(v107, v8 + 3);
              v75 = 0;
              v55 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *))(*v82 + 64))(v82, v108, &v75);
              if ( v55 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1EB,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v55,
                  v73);
              if ( v75 )
              {
                v80 = 0;
                v56 = *v82;
                v80 = 0;
                v57 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v56 + 48))(v82, v108, &v80);
                if ( v57 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1FA,
                    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                    (const char *)(unsigned int)v57,
                    v73);
                v89 = 0;
                v58 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v80)(
                        v80,
                        &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                        &v89);
                if ( v58 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1CBE,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                    (const char *)(unsigned int)v58,
                    v73);
                v31 |= 0x40u;
                v78 = v31;
                Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v8 + 4);
                v76 = 0;
                v59 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, char *))(*v89 + 64))(v89, string, &v76);
                if ( v59 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x205,
                    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                    (const char *)(unsigned int)v59,
                    v73);
                if ( v76 )
                {
                  v79 = 0;
                  v60 = *v89;
                  v79 = 0;
                  v61 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct IInspectable **))(v60 + 48))(
                          v89,
                          string,
                          &v79);
                  v62 = retaddr;
                  if ( v61 < 0 )
                    goto LABEL_100;
                  ReservedForLocalUse::GetPropertyRepresentingObjectsAsInspectableArray(
                    (ReservedForLocalUse *)&v98,
                    v79);
                  if ( v99 > v14 )
                  {
                    v63 = 1;
                    v64 = v98;
                    v65 = &v98[v99];
                    if ( v98 != v65 )
                    {
                      do
                      {
                        v66 = StateRepoPackageInformation::ShouldIgnoreExclusion(v1, *v64) ? v63 : 0;
                        v63 = v66;
                        ++v64;
                      }
                      while ( v64 != v65 );
                      if ( !v66 )
                        wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator=(
                          &v96,
                          &v98);
                    }
                  }
                  wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v98);
                  if ( v79 )
                    ((void (__fastcall *)(struct IInspectable *))v79->lpVtbl->Release)(v79);
                }
                string = 0;
                if ( v89 )
                  (*(void (__fastcall **)(__int64 *))(*v89 + 16))(v89);
                if ( v80 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
              }
            }
            v2 = v31 & 0xFFFFFFF7;
            v78 = v2;
            if ( v82 )
              (*(void (__fastcall **)(__int64 *))(*v82 + 16))(v82);
            if ( v24 )
              (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
            v18 = ++v92;
            v14 = v97;
            v17 = v81;
          }
          v67 = v93;
          if ( v93 )
          {
            v93 = 0;
            (*(void (__fastcall **)(__int64 *))(*v67 + 16))(v67);
          }
          v68 = v96;
          if ( v96 )
          {
            v69 = &v96[v14];
            while ( v68 != v69 )
              StateRepoPackageInformation::ParseAndAddWriteVirtualizationExcludedItemElement(v1, *v68++, v8[5]);
          }
          else if ( v77 )
          {
            *(_BYTE *)v8[1] = 1;
          }
          wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v96);
        }
        else
        {
          *(_BYTE *)v8[1] = 1;
        }
        if ( v86 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      }
      v8 += 6;
    }
    while ( v8 != v102 );
    *((_BYTE *)v1 + 156) = 1;
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v109, 0);
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    if ( v90 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    if ( v95 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    v109[0] = &DesktopAppXProvider::LoadStateRepoPackageProperties::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v109, v70, v71, v72);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v109);
  }
}

```

## disassembly

```asm
0x18009a2dc  push    rbp
0x18009a2de  push    rbx
0x18009a2df  push    rsi
0x18009a2e0  push    rdi
0x18009a2e1  push    r12
0x18009a2e3  push    r13
0x18009a2e5  push    r14
0x18009a2e7  push    r15
0x18009a2e9  lea     rbp, [rsp-208h]
0x18009a2f1  sub     rsp, 308h
0x18009a2f8  mov     rax, cs:__security_cookie
0x18009a2ff  xor     rax, rsp
0x18009a302  mov     [rbp+240h+var_50], rax
0x18009a309  mov     r12, rcx
0x18009a30c  mov     [rbp+240h+var_268], rcx
0x18009a310  xor     r14d, r14d
0x18009a313  mov     esi, r14d
0x18009a316  mov     [rsp+340h+var_30C], r14d
0x18009a31b  cmp     [rcx+9Ch], r14b
0x18009a322  jnz     loc_18009ABFC
0x18009a328  lea     rdx, aLoadstaterepop; "LoadStateRepoPackageProperties"
0x18009a32f  lea     rcx, [rbp+240h+var_1A0]
0x18009a336  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009a33b  lea     rax, ??_7LoadStateRepoPackageProperties@DesktopAppXProvider@@6B@; const DesktopAppXProvider::LoadStateRepoPackageProperties::`vftable'
0x18009a342  mov     [rbp+240h+var_1A0], rax
0x18009a349  lea     rcx, [rbp+240h+var_1A0]; this
0x18009a350  call    ?StartActivity@LoadStateRepoPackageProperties@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::LoadStateRepoPackageProperties::StartActivity(void)
0x18009a355  nop
0x18009a356  lea     rcx, [rbp+240h+var_290]
0x18009a35a  call    ??$GetActivationFactory@UIPackageStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(ushort const *)
0x18009a35f  nop
0x18009a360  mov     [rbp+240h+var_2B8], r14
0x18009a364  mov     rbx, [rbp+240h+var_290]
0x18009a368  mov     rax, [rbx]
0x18009a36b  mov     rdi, [rax+0B0h]
0x18009a372  mov     [rbp+240h+var_2B8], r14
0x18009a376  lea     rax, [r12+8]
0x18009a37b  cmp     qword ptr [rax+18h], 7
0x18009a380  jbe     short loc_18009A385
0x18009a382  mov     rax, [rax]
0x18009a385  mov     [rsp+340h+var_2D0], rax
0x18009a38a  lea     rdx, [rsp+340h+var_2D0]
0x18009a38f  lea     rcx, [rbp+240h+var_1C0]
0x18009a396  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009a39b  nop
0x18009a39c  lea     r8, [rbp+240h+var_2B8]
0x18009a3a0  mov     rdx, [rax+18h]
0x18009a3a4  mov     rcx, rbx
0x18009a3a7  mov     rax, rdi
0x18009a3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a3af  mov     rcx, [rbp+248h]; this
0x18009a3b6  test    eax, eax
0x18009a3b8  js      loc_18009AC4A
0x18009a3be  lea     rcx, [rbp+240h+var_298]
0x18009a3c2  call    ??$GetActivationFactory@UIPackagePropertyStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackagePropertyStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IPackagePropertyStatics>(ushort const *)
0x18009a3c7  nop
0x18009a3c8  lea     rax, ??_9StateRepoPackageInformation@@$BDI@AA; [thunk]: StateRepoPackageInformation::`vcall'{56,{flat}}
0x18009a3cf  mov     [rbp+240h+var_260], rax
0x18009a3d3  lea     rax, [r12+9Dh]
0x18009a3db  mov     [rbp+240h+var_258], rax
0x18009a3df  lea     rax, aFilesystemwrit; "FileSystemWriteVirtualization"
0x18009a3e6  mov     [rbp+240h+var_250], rax
0x18009a3ea  lea     rax, aExcludeddirect_0; "ExcludedDirectories"
0x18009a3f1  mov     [rbp+240h+var_248], rax
0x18009a3f5  lea     rax, aExcludeddirect; "ExcludedDirectory"
0x18009a3fc  mov     [rbp+240h+var_240], rax
0x18009a400  lea     rax, ?ParseAndAddExcludedDirectoryElementContent@StateRepoPackageInformation@@AEAAXPEBG@Z; StateRepoPackageInformation::ParseAndAddExcludedDirectoryElementContent(ushort const *)
0x18009a407  mov     [rbp+240h+var_238], rax
0x18009a40b  lea     rax, ??_9StateRepoPackageInformation@@$BFI@AA; [thunk]: StateRepoPackageInformation::`vcall'{88,{flat}}
0x18009a412  mov     [rbp+240h+var_230], rax
0x18009a416  lea     rax, [r12+9Eh]
0x18009a41e  mov     [rbp+240h+var_228], rax
0x18009a422  lea     rax, aRegistrywritev; "RegistryWriteVirtualization"
0x18009a429  mov     [rbp+240h+var_220], rax
0x18009a42d  lea     rax, aExcludedkeys; "ExcludedKeys"
0x18009a434  mov     [rbp+240h+var_218], rax
0x18009a438  lea     rax, aExcludedkey; "ExcludedKey"
0x18009a43f  mov     [rbp+240h+var_210], rax
0x18009a443  lea     rax, ?ParseAndAddExcludedKeyElementContent@StateRepoPackageInformation@@AEAAXPEBG@Z; StateRepoPackageInformation::ParseAndAddExcludedKeyElementContent(ushort const *)
0x18009a44a  mov     [rbp+240h+var_208], rax
0x18009a44e  lea     r13, [rbp+240h+var_260]
0x18009a452  mov     rcx, r12
0x18009a455  mov     rax, [r13+0]
0x18009a459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a45e  test    al, al
0x18009a460  jz      loc_18009AB6B
0x18009a466  mov     [rsp+340h+var_2D8], r14
0x18009a46b  mov     rdi, [rbp+240h+var_298]
0x18009a46f  mov     rax, [rdi]
0x18009a472  mov     rbx, [rax+90h]
0x18009a479  mov     [rsp+340h+var_2D8], r14
0x18009a47e  lea     rdx, [r13+10h]
0x18009a482  lea     rcx, [rbp+240h+var_1C0]
0x18009a489  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009a48e  nop
0x18009a48f  lea     r9, [rsp+340h+var_2D8]
0x18009a494  mov     r8, [rax+18h]
0x18009a498  mov     rdx, [rbp+240h+var_2B8]
0x18009a49c  mov     rcx, rdi
0x18009a49f  mov     rax, rbx
0x18009a4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a4a7  mov     rcx, [rbp+248h]; this
0x18009a4ae  test    eax, eax
0x18009a4b0  js      loc_18009AC35
0x18009a4b6  mov     [rsp+340h+var_2E8], r14d
0x18009a4bb  mov     rcx, [rsp+340h+var_2D8]
0x18009a4c0  mov     rax, [rcx]
0x18009a4c3  lea     rdx, [rsp+340h+var_2E8]
0x18009a4c8  mov     rax, [rax+38h]
0x18009a4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a4d1  mov     rcx, [rbp+248h]; this
0x18009a4d8  test    eax, eax
0x18009a4da  js      loc_18009AC20
0x18009a4e0  cmp     [rsp+340h+var_2E8], r14d
0x18009a4e5  jnz     short loc_18009A4F3
0x18009a4e7  mov     rax, [r13+8]
0x18009a4eb  mov     byte ptr [rax], 1
0x18009a4ee  jmp     loc_18009AB54
0x18009a4f3  mov     [rbp+240h+var_288], r14
0x18009a4f7  mov     r15, r14
0x18009a4fa  mov     [rbp+240h+var_280], r14
0x18009a4fe  mov     rbx, [rsp+340h+var_2D8]
0x18009a503  mov     [rbp+240h+var_2B0], rbx
0x18009a507  mov     [rbp+240h+var_2A8], r14d
0x18009a50b  mov     [rbp+240h+var_2A0], r14
0x18009a50f  mov     [rsp+340h+var_2F8], r14d
0x18009a514  mov     rax, [rbx]
0x18009a517  lea     rdx, [rsp+340h+var_2F8]
0x18009a51c  mov     rcx, rbx
0x18009a51f  mov     rax, [rax+38h]
0x18009a523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a528  mov     rcx, [rbp+248h]; this
0x18009a52f  test    eax, eax
0x18009a531  js      loc_18009AD9B
0x18009a537  mov     [rsp+340h+var_30D], r14b
0x18009a53c  mov     [rbp+240h+var_1F8], rbx
0x18009a540  mov     eax, [rsp+340h+var_2F8]
0x18009a544  mov     [rbp+240h+var_1F0], eax
0x18009a547  mov     [rbp+240h+var_1E8], r14
0x18009a54b  or      esi, 4
0x18009a54e  mov     [rsp+340h+var_30C], esi
0x18009a552  mov     edx, [rbp+240h+var_2A8]
0x18009a555  cmp     edx, eax
0x18009a557  jz      loc_18009AAF9
0x18009a55d  mov     rbx, [rbp+240h+var_2B0]
0x18009a561  mov     rax, [rbx]
0x18009a564  mov     rdi, [rax+30h]
0x18009a568  mov     rcx, [rbp+240h+var_2A0]
0x18009a56c  test    rcx, rcx
0x18009a56f  jz      short loc_18009A584
0x18009a571  mov     [rbp+240h+var_2A0], r14
0x18009a575  mov     rax, [rcx]
0x18009a578  mov     rax, [rax+10h]
0x18009a57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a581  mov     edx, [rbp+240h+var_2A8]
0x18009a584  lea     r8, [rbp+240h+var_2A0]
0x18009a588  mov     rcx, rbx
0x18009a58b  mov     rax, rdi
0x18009a58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a593  mov     rcx, [rbp+248h]; this
0x18009a59a  test    eax, eax
0x18009a59c  js      loc_18009AD86
0x18009a5a2  mov     rbx, [rbp+240h+var_2A0]
0x18009a5a6  mov     [rbp+240h+var_200], rbx
0x18009a5aa  test    rbx, rbx
0x18009a5ad  jz      short loc_18009A5BF
0x18009a5af  mov     rax, [rbx]
0x18009a5b2  mov     rcx, rbx
0x18009a5b5  mov     rax, [rax+8]
0x18009a5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a5be  nop
0x18009a5bf  mov     rdi, [rbp+248h]
0x18009a5c6  call    IsSRDictionaryToPropertySetPresent
0x18009a5cb  test    al, al
0x18009a5cd  jz      loc_18009AD6B
0x18009a5d3  mov     [rsp+340h+var_2E4], r14d
0x18009a5d8  mov     [rsp+340h+pv], r14
0x18009a5dd  mov     rax, [rbx]
0x18009a5e0  lea     rcx, [rsp+340h+pv]
0x18009a5e5  mov     qword ptr [rbp+240h+hstringHeader.Reserved], rcx
0x18009a5e9  mov     qword ptr [rbp+240h+hstringHeader.Reserved+8], r14
0x18009a5ed  mov     byte ptr [rbp+240h+hstringHeader.Reserved+10h], 1
0x18009a5f1  lea     r8, [rbp+240h+hstringHeader.Reserved+8]
0x18009a5f5  lea     rdx, [rsp+340h+var_2E4]
0x18009a5fa  mov     rcx, rbx
0x18009a5fd  mov     rax, [rax+80h]
0x18009a604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a609  mov     rcx, [rbp+248h]; this
0x18009a610  test    eax, eax
0x18009a612  js      loc_18009AD56
0x18009a618  cmp     byte ptr [rbp+240h+hstringHeader.Reserved+10h], r14b
0x18009a61c  jz      short loc_18009A63E
0x18009a61e  mov     rdx, qword ptr [rbp+240h+hstringHeader.Reserved]
0x18009a622  mov     rcx, [rdx]; pv
0x18009a625  mov     rax, qword ptr [rbp+240h+hstringHeader.Reserved+8]
0x18009a629  mov     [rdx], rax
0x18009a62c  test    rcx, rcx
0x18009a62f  jz      short loc_18009A63E
0x18009a631  call    cs:__imp_CoTaskMemFree
0x18009a638  nop     dword ptr [rax+rax+00h]
0x18009a63d  nop
0x18009a63e  mov     [rsp+340h+var_2D0], r14
0x18009a643  lea     r8, [rsp+340h+var_2D0]
0x18009a648  mov     rdx, [rsp+340h+pv]
0x18009a64d  mov     ecx, [rsp+340h+var_2E4]
0x18009a651  call    cs:__imp_SRDictionaryToPropertySet
0x18009a658  nop     dword ptr [rax+rax+00h]
0x18009a65d  mov     rcx, [rbp+248h]; this
0x18009a664  test    eax, eax
0x18009a666  js      loc_18009AD41
0x18009a66c  mov     rcx, [rsp+340h+var_2D0]
0x18009a671  mov     [rsp+340h+var_2F0], r14
0x18009a676  mov     rax, [rcx]
0x18009a679  lea     r8, [rsp+340h+var_2F0]
0x18009a67e  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18009a685  mov     rax, [rax]
0x18009a688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a68d  mov     rcx, [rbp+248h]
0x18009a694  test    eax, eax
0x18009a696  js      loc_18009AD2C
0x18009a69c  or      esi, 18h
0x18009a69f  mov     [rsp+340h+var_30C], esi
0x18009a6a3  mov     rcx, [rsp+340h+var_2D0]
0x18009a6a8  test    rcx, rcx
0x18009a6ab  jz      short loc_18009A6BA
0x18009a6ad  mov     rax, [rcx]
0x18009a6b0  mov     rax, [rax+10h]
0x18009a6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a6b9  nop
0x18009a6ba  mov     rcx, [rsp+340h+pv]; pv
0x18009a6bf  mov     [rsp+340h+pv], r14
0x18009a6c4  test    rcx, rcx
0x18009a6c7  jz      short loc_18009A6D5
0x18009a6c9  call    cs:__imp_CoTaskMemFree
0x18009a6d0  nop     dword ptr [rax+rax+00h]
0x18009a6d5  mov     [rsp+340h+var_310], r14b
0x18009a6da  mov     rdi, [rsp+340h+var_2F0]
0x18009a6df  mov     r14, [rdi]
0x18009a6e2  mov     [rbp+240h+string], 0
0x18009a6ea  lea     r9, [rbp+240h+string]; string
0x18009a6ee  lea     r8, [rbp+240h+hstringHeader]; hstringHeader
0x18009a6f2  mov     edx, 5; length
0x18009a6f7  lea     rcx, aText; "#text"
0x18009a6fe  call    cs:__imp_WindowsCreateStringReference
0x18009a705  nop     dword ptr [rax+rax+00h]
0x18009a70a  test    eax, eax
0x18009a70c  js      loc_18009AD24
0x18009a712  lea     r8, [rsp+340h+var_310]
0x18009a717  mov     rdx, [rbp+240h+string]
0x18009a71b  mov     rcx, rdi
0x18009a71e  mov     rax, [r14+40h]
0x18009a722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a727  mov     rcx, [rbp+248h]; this
0x18009a72e  xor     r14d, r14d
0x18009a731  test    eax, eax
0x18009a733  js      loc_18009AD0F
0x18009a739  cmp     [rsp+340h+var_310], r14b
0x18009a73e  jz      loc_18009A8D5
0x18009a744  mov     [rsp+340h+var_308], r14
0x18009a749  mov     rdi, [rsp+340h+var_2F0]
0x18009a74e  mov     r14, [rdi]
0x18009a751  xor     r15d, r15d
0x18009a754  mov     [rsp+340h+var_308], r15
0x18009a759  mov     [rbp+240h+string], r15
0x18009a75d  lea     r9, [rbp+240h+string]; string
0x18009a761  lea     r8, [rbp+240h+hstringHeader]; hstringHeader
0x18009a765  lea     edx, [r15+5]; length
0x18009a769  lea     rcx, aText; "#text"
0x18009a770  call    cs:__imp_WindowsCreateStringReference
0x18009a777  nop     dword ptr [rax+rax+00h]
0x18009a77c  test    eax, eax
0x18009a77e  js      loc_18009AC9E
0x18009a784  lea     r8, [rsp+340h+var_308]
0x18009a789  mov     rdx, [rbp+240h+string]
0x18009a78d  mov     rcx, rdi
0x18009a790  mov     rax, [r14+30h]
0x18009a794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a799  mov     rcx, [rbp+248h]; this
0x18009a7a0  test    eax, eax
0x18009a7a2  js      loc_18009AC89
0x18009a7a8  mov     [rsp+340h+var_2E0], r15
0x18009a7ad  mov     rcx, [rsp+340h+var_308]
0x18009a7b2  mov     [rsp+340h+var_300], r15
0x18009a7b7  mov     rax, [rcx]
0x18009a7ba  lea     r8, [rsp+340h+var_300]
0x18009a7bf  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18009a7c6  mov     rax, [rax]
0x18009a7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a7ce  mov     rcx, [rbp+248h]; this
0x18009a7d5  test    eax, eax
0x18009a7d7  js      loc_18009AC74
0x18009a7dd  or      esi, 20h
0x18009a7e0  mov     [rsp+340h+var_30C], esi
0x18009a7e4  mov     r15, [rsp+340h+var_300]
0x18009a7e9  mov     rax, [r15]
0x18009a7ec  mov     r12, [rax+98h]
0x18009a7f3  mov     r14, [rsp+340h+var_2E0]
0x18009a7f8  test    r14, r14
0x18009a7fb  jz      short loc_18009A828
0x18009a7fd  call    cs:__imp_GetLastError
  ... truncated ...
```
