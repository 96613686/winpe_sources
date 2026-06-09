# StateRepoPackageInformation::LoadStateRepoPackageProperties(void)

- ea: `0x1800988a0`
- end: `0x1800993aa`
- name: `?LoadStateRepoPackageProperties@StateRepoPackageInformation@@AEAAXXZ`
- size: `2826`
- prototype: `void __fastcall(StateRepoPackageInformation *__hidden this)`
- caller_count: `5`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180097760`
- `0x180097830`
- `0x180097ac0`
- `0x180097f00`
- `0x1800997f0`

## callees

- `0x1800053a0`
- `0x180008524`
- `0x180010a84`
- `0x1800148e8`
- `0x180014f4c`
- `0x18001748c`
- `0x18001ec94`
- `0x180038318`
- `0x18003ddd0`
- `0x180096cdc`
- `0x180096d7c`
- `0x180097270`
- `0x180097424`
- `0x180097d00`
- `0x1800988a0`
- `0x180099518`
- `0x180099884`
- `0x180099dc0`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098de4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180098e03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180098e03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180098cd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180098d51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180098cd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180098d51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098df5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098e8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098df5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098e8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098e53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098e53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098bfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098c98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098bfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098c98`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x180098c1e`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x180098c1e`

## string_xrefs

- `0x180099271`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800992cd`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180099329`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180099383`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180099398`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800989ab`: `FileSystemWriteVirtualization`
- `0x1800989ee`: `RegistryWriteVirtualization`
- `0x1800989c1`: `ExcludedDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=45
void __fastcall StateRepoPackageInformation::LoadStateRepoPackageProperties(StateRepoPackageInformation *this)
{
  StateRepoPackageInformation *v1; // r12
  unsigned int v2; // r14d
  __int64 v3; // rbx
  __int64 (__fastcall *v4)(__int64, _QWORD, __int64 *); // rdi
  _QWORD *v5; // rax
  __int64 v6; // rax
  int v7; // eax
  unsigned __int8 (__fastcall **v8)(StateRepoPackageInformation *); // r13
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD, __int64 *); // rdi
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
  __int64 *v24; // rdi
  __int64 v25; // rax
  int v26; // eax
  void *v27; // rcx
  int v28; // eax
  int v29; // eax
  wil::details::in1diag3 *v30; // rcx
  int v31; // r14d
  void *v32; // rcx
  __int64 *v33; // rbx
  __int64 (__fastcall *v34)(__int64 *, HSTRING, char *); // rsi
  HRESULT v35; // eax
  int v36; // edx
  unsigned int v37; // r8d
  int v38; // eax
  __int64 *v39; // rbx
  __int64 (__fastcall *v40)(__int64 *, HSTRING, struct IInspectable **); // rsi
  HRESULT v41; // eax
  int v42; // edx
  unsigned int v43; // r8d
  int v44; // eax
  int v45; // eax
  __int64 v46; // rbx
  __int64 (__fastcall *v47)(__int64, HSTRING *); // r12
  HSTRING v48; // r15
  DWORD LastError; // esi
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
  char v63; // si
  struct IInspectable **v64; // rbx
  struct IInspectable **v65; // r15
  char v66; // cl
  __int64 *v67; // rcx
  _QWORD *v68; // rbx
  _QWORD *v69; // rdi
  int v70; // [rsp+28h] [rbp-E0h]
  char v71; // [rsp+38h] [rbp-D0h] BYREF
  char v72; // [rsp+39h] [rbp-CFh] BYREF
  char v73; // [rsp+3Ah] [rbp-CEh] BYREF
  bool v74; // [rsp+3Bh] [rbp-CDh]
  unsigned int v75; // [rsp+3Ch] [rbp-CCh]
  struct IInspectable *v76; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v77; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v78; // [rsp+50h] [rbp-B8h] BYREF
  __int64 *v79; // [rsp+58h] [rbp-B0h] BYREF
  int v80; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v81; // [rsp+64h] [rbp-A4h] BYREF
  HSTRING v82; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v83; // [rsp+70h] [rbp-98h] BYREF
  _QWORD *v84; // [rsp+78h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-88h] BYREF
  __int64 *v86; // [rsp+88h] [rbp-80h] BYREF
  __int64 v87; // [rsp+90h] [rbp-78h] BYREF
  __int64 v88; // [rsp+98h] [rbp-70h]
  unsigned int v89; // [rsp+A0h] [rbp-68h]
  __int64 *v90; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v91; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v92; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD *v93; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int64 v94; // [rsp+C8h] [rbp-40h]
  struct IInspectable **v95; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int64 v96; // [rsp+D8h] [rbp-30h]
  StateRepoPackageInformation *v97; // [rsp+E0h] [rbp-28h]
  _QWORD v98[12]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v99[3]; // [rsp+148h] [rbp+40h] BYREF
  int v100; // [rsp+160h] [rbp+58h]
  __int64 v101; // [rsp+168h] [rbp+60h]
  HSTRING_HEADER hstringHeader; // [rsp+170h] [rbp+68h] BYREF
  HSTRING string; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v104[24]; // [rsp+190h] [rbp+88h] BYREF
  __int64 v105; // [rsp+1A8h] [rbp+A0h]
  _QWORD v106[42]; // [rsp+1B8h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+340h] [rbp+238h]

  v1 = this;
  v97 = this;
  v2 = 0;
  v75 = 0;
  if ( !*((_BYTE *)this + 148) )
  {
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v106,
      "LoadStateRepoPackageProperties");
    v106[0] = &DesktopAppXProvider::LoadStateRepoPackageProperties::`vftable';
    DesktopAppXProvider::LoadStateRepoPackageProperties::StartActivity((DesktopAppXProvider::LoadStateRepoPackageProperties *)v106);
    wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(&v92);
    v87 = 0;
    v3 = v92;
    v4 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v92 + 176LL);
    v87 = 0;
    v5 = (_QWORD *)((char *)v1 + 8);
    if ( *((_QWORD *)v1 + 4) > 7u )
      v5 = (_QWORD *)*v5;
    v84 = v5;
    v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v104, &v84);
    v7 = v4(v3, *(_QWORD *)(v6 + 24), &v87);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x180,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
        (const char *)(unsigned int)v7,
        v70);
    wil::GetActivationFactory<Windows::Internal::StateRepository::IPackagePropertyStatics>(&v91);
    v98[0] =  StateRepoPackageInformation::`vcall'{56,{flat}};
    v98[1] = (char *)v1 + 149;
    v98[2] = L"FileSystemWriteVirtualization";
    v98[3] = L"ExcludedDirectories";
    v98[4] = L"ExcludedDirectory";
    v98[5] = StateRepoPackageInformation::ParseAndAddExcludedDirectoryElementContent;
    v98[6] =  StateRepoPackageInformation::`vcall'{88,{flat}};
    v98[7] = (char *)v1 + 150;
    v98[8] = L"RegistryWriteVirtualization";
    v98[9] = L"ExcludedKeys";
    v98[10] = L"ExcludedKey";
    v98[11] = StateRepoPackageInformation::ParseAndAddExcludedKeyElementContent;
    v8 = (unsigned __int8 (__fastcall **)(StateRepoPackageInformation *))v98;
    do
    {
      if ( (*v8)(v1) )
      {
        v83 = 0;
        v9 = v91;
        v10 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v91 + 144LL);
        v83 = 0;
        v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v104, v8 + 2);
        v12 = v10(v9, v87, *(_QWORD *)(v11 + 24), &v83);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
            (const char *)(unsigned int)v12,
            v70);
        v99[0] = 0;
        v80 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v83 + 56LL))(v83, &v80);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1AF,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
            (const char *)(unsigned int)v13,
            v70);
        if ( v80 )
        {
          v74 = 0;
          v93 = 0;
          v14 = 0;
          v94 = 0;
          v15 = v83;
          v88 = v83;
          v89 = 0;
          v90 = 0;
          LODWORD(v78) = 0;
          v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v83 + 56LL))(v83, &v78);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1C60,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v16,
              v70);
          v99[2] = v15;
          v17 = v78;
          v100 = v78;
          v101 = 0;
          v2 |= 4u;
          v75 = v2;
          v18 = v89;
          while ( (_DWORD)v18 != v17 )
          {
            v19 = v88;
            v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v88 + 48LL);
            v21 = v90;
            if ( v90 )
            {
              v90 = 0;
              (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
              v18 = v89;
            }
            v22 = v20(v19, v18, &v90);
            v23 = retaddr;
            if ( v22 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1C60,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                (const char *)(unsigned int)v22,
                v70);
            v24 = v90;
            v99[1] = v90;
            if ( v90 )
              (*(void (__fastcall **)(__int64 *))(*v90 + 8))(v90);
            if ( !(unsigned __int8)IsSRDictionaryToPropertySetPresent(v23) )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x48,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                (const char *)0x8000FFFFLL,
                v70);
            v81 = 0;
            pv = 0;
            v25 = *v24;
            hstringHeader.Reserved.Reserved1 = &pv;
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
            hstringHeader.Reserved.Reserved2[16] = 1;
            v26 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, char *))(v25 + 128))(
                    v24,
                    &v81,
                    &hstringHeader.Reserved.Reserved2[8]);
            if ( v26 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4C,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                (const char *)(unsigned int)v26,
                v70);
            if ( hstringHeader.Reserved.Reserved2[16] )
            {
              v27 = *(void **)hstringHeader.Reserved.Reserved1;
              *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
              if ( v27 )
                CoTaskMemFree(v27);
            }
            v84 = 0;
            v28 = SRDictionaryToPropertySet(v81, pv, &v84);
            if ( v28 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4F,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                (const char *)(unsigned int)v28,
                v70);
            v79 = 0;
            v29 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 **))*v84)(
                    v84,
                    &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                    &v79);
            v30 = retaddr;
            if ( v29 < 0 )
              goto LABEL_105;
            v31 = v2 | 0x18;
            v75 = v31;
            if ( v84 )
              (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
            v32 = pv;
            pv = 0;
            if ( v32 )
              CoTaskMemFree(v32);
            v71 = 0;
            v33 = v79;
            v34 = *(__int64 (__fastcall **)(__int64 *, HSTRING, char *))(*v79 + 64);
            string = 0;
            v35 = WindowsCreateStringReference(L"#text", 5u, &hstringHeader, &string);
            if ( v35 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v35, v36, v37);
LABEL_105:
              wil::details::in1diag3::Throw_Hr(
                v30,
                (void *)0x1C60,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                (const char *)(unsigned int)v29,
                v70);
            }
            v38 = v34(v33, string, &v71);
            if ( v38 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1D9,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                (const char *)(unsigned int)v38,
                v70);
            if ( v71 )
            {
              v76 = 0;
              v39 = v79;
              v40 = *(__int64 (__fastcall **)(__int64 *, HSTRING, struct IInspectable **))(*v79 + 48);
              v76 = 0;
              string = 0;
              v41 = WindowsCreateStringReference(L"#text", 5u, &hstringHeader, &string);
              if ( v41 < 0 )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v41, v42, v43);
LABEL_98:
                wil::details::in1diag3::Throw_Hr(
                  v62,
                  (void *)0x20D,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v61,
                  v70);
              }
              v44 = v40(v39, string, &v76);
              if ( v44 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1DE,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v44,
                  v70);
              v82 = 0;
              v77 = 0;
              v45 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))v76->lpVtbl->QueryInterface)(
                      v76,
                      &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
                      &v77);
              if ( v45 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1C60,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                  (const char *)(unsigned int)v45,
                  v70);
              v31 |= 0x20u;
              v75 = v31;
              v46 = v77;
              v47 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v77 + 152LL);
              v48 = v82;
              if ( v82 )
              {
                LastError = GetLastError();
                WindowsDeleteString(v48);
                SetLastError(LastError);
              }
              v82 = 0;
              v50 = v47(v46, &v82);
              if ( v50 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1E1,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v50,
                  v70);
              if ( v77 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
              StringRawBuffer = WindowsGetStringRawBuffer(v82, 0);
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
              v74 = v54 == 0;
              if ( v82 )
                WindowsDeleteString(v82);
              if ( v76 )
                ((void (__fastcall *)(struct IInspectable *))v76->lpVtbl->Release)(v76);
              v1 = v97;
            }
            else
            {
              Microsoft::WRL::Wrappers::HStringReference::HStringReference(v104, v8 + 3);
              v72 = 0;
              v55 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *))(*v79 + 64))(v79, v105, &v72);
              if ( v55 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1ED,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v55,
                  v70);
              if ( v72 )
              {
                v77 = 0;
                v56 = *v79;
                v77 = 0;
                v57 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v56 + 48))(v79, v105, &v77);
                if ( v57 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1FC,
                    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                    (const char *)(unsigned int)v57,
                    v70);
                v86 = 0;
                v58 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v77)(
                        v77,
                        &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                        &v86);
                if ( v58 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1C60,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                    (const char *)(unsigned int)v58,
                    v70);
                v31 |= 0x40u;
                v75 = v31;
                Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v8 + 4);
                v73 = 0;
                v59 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, char *))(*v86 + 64))(v86, string, &v73);
                if ( v59 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x207,
                    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                    (const char *)(unsigned int)v59,
                    v70);
                if ( v73 )
                {
                  v76 = 0;
                  v60 = *v86;
                  v76 = 0;
                  v61 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct IInspectable **))(v60 + 48))(
                          v86,
                          string,
                          &v76);
                  v62 = retaddr;
                  if ( v61 < 0 )
                    goto LABEL_98;
                  ReservedForLocalUse::GetPropertyRepresentingObjectsAsInspectableArray(
                    (ReservedForLocalUse *)&v95,
                    v76);
                  if ( v96 > v14 )
                  {
                    v63 = 1;
                    v64 = v95;
                    v65 = &v95[v96];
                    if ( v95 != v65 )
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
                          &v93,
                          &v95);
                    }
                  }
                  wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v95);
                  if ( v76 )
                    ((void (__fastcall *)(struct IInspectable *))v76->lpVtbl->Release)(v76);
                }
                string = 0;
                if ( v86 )
                  (*(void (__fastcall **)(__int64 *))(*v86 + 16))(v86);
                if ( v77 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
              }
            }
            v2 = v31 & 0xFFFFFFF7;
            v75 = v2;
            if ( v79 )
              (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
            (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
            v18 = ++v89;
            v14 = v94;
            v17 = v78;
          }
          v67 = v90;
          if ( v90 )
          {
            v90 = 0;
            (*(void (__fastcall **)(__int64 *))(*v67 + 16))(v67);
          }
          v68 = v93;
          if ( v93 )
          {
            v69 = &v93[v14];
            while ( v68 != v69 )
              StateRepoPackageInformation::ParseAndAddWriteVirtualizationExcludedItemElement(v1, *v68++, v8[5]);
          }
          else if ( v74 )
          {
            *(_BYTE *)v8[1] = 1;
          }
          wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v93);
        }
        else
        {
          *(_BYTE *)v8[1] = 1;
        }
        if ( v83 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      }
      v8 += 6;
    }
    while ( v8 != v99 );
    *((_BYTE *)v1 + 148) = 1;
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v106, 0);
    if ( v91 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    if ( v87 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
    if ( v92 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    v106[0] = &DesktopAppXProvider::LoadStateRepoPackageProperties::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v106);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v106);
  }
}

```

## disassembly

```asm
0x1800988a0  mov     rax, rsp
0x1800988a3  mov     [rax+10h], rbx
0x1800988a7  mov     [rax+18h], rsi
0x1800988ab  mov     [rax+20h], rdi
0x1800988af  push    rbp
0x1800988b0  push    r12
0x1800988b2  push    r13
0x1800988b4  push    r14
0x1800988b6  push    r15
0x1800988b8  lea     rbp, [rax-238h]
0x1800988bf  sub     rsp, 310h
0x1800988c6  mov     rax, cs:__security_cookie
0x1800988cd  xor     rax, rsp
0x1800988d0  mov     [rbp+230h+var_30], rax
0x1800988d7  mov     r12, rcx
0x1800988da  mov     [rbp+230h+var_258], rcx
0x1800988de  xor     esi, esi
0x1800988e0  mov     r14d, esi
0x1800988e3  mov     dword ptr [rsp+330h+var_300+4], esi
0x1800988e7  cmp     [rcx+94h], sil
0x1800988ee  jnz     loc_1800991E9
0x1800988f4  lea     rdx, aLoadstaterepop; "LoadStateRepoPackageProperties"
0x1800988fb  lea     rcx, [rbp+230h+var_180]
0x180098902  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180098907  lea     rax, ??_7LoadStateRepoPackageProperties@DesktopAppXProvider@@6B@; const DesktopAppXProvider::LoadStateRepoPackageProperties::`vftable'
0x18009890e  mov     [rbp+230h+var_180], rax
0x180098915  lea     rcx, [rbp+230h+var_180]; this
0x18009891c  call    ?StartActivity@LoadStateRepoPackageProperties@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::LoadStateRepoPackageProperties::StartActivity(void)
0x180098921  nop
0x180098922  lea     rcx, [rbp+230h+var_280]
0x180098926  call    ??$GetActivationFactory@UIPackageStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(ushort const *)
0x18009892b  nop
0x18009892c  mov     [rbp+230h+var_2A8], rsi
0x180098930  mov     rbx, [rbp+230h+var_280]
0x180098934  mov     rax, [rbx]
0x180098937  mov     rdi, [rax+0B0h]
0x18009893e  mov     [rbp+230h+var_2A8], rsi
0x180098942  lea     rax, [r12+8]
0x180098947  cmp     qword ptr [rax+18h], 7
0x18009894c  jbe     short loc_180098951
0x18009894e  mov     rax, [rax]
0x180098951  mov     [rsp+330h+var_2C0], rax
0x180098956  lea     rdx, [rsp+330h+var_2C0]
0x18009895b  lea     rcx, [rbp+230h+var_1A8]
0x180098962  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180098967  nop
0x180098968  lea     r8, [rbp+230h+var_2A8]
0x18009896c  mov     rdx, [rax+18h]
0x180098970  mov     rcx, rbx
0x180098973  mov     rax, rdi
0x180098976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009897b  mov     rcx, [rbp+238h]; this
0x180098982  test    eax, eax
0x180098984  js      loc_180099244
0x18009898a  lea     rcx, [rbp+230h+var_288]
0x18009898e  call    ??$GetActivationFactory@UIPackagePropertyStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackagePropertyStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IPackagePropertyStatics>(ushort const *)
0x180098993  nop
0x180098994  lea     rax, ??_9StateRepoPackageInformation@@$BDI@AA; [thunk]: StateRepoPackageInformation::`vcall'{56,{flat}}
0x18009899b  mov     [rbp+230h+var_250], rax
0x18009899f  lea     rax, [r12+95h]
0x1800989a7  mov     [rbp+230h+var_248], rax
0x1800989ab  lea     rax, aFilesystemwrit; "FileSystemWriteVirtualization"
0x1800989b2  mov     [rbp+230h+var_240], rax
0x1800989b6  lea     rax, aExcludeddirect_0; "ExcludedDirectories"
0x1800989bd  mov     [rbp+230h+var_238], rax
0x1800989c1  lea     rax, aExcludeddirect; "ExcludedDirectory"
0x1800989c8  mov     [rbp+230h+var_230], rax
0x1800989cc  lea     rax, ?ParseAndAddExcludedDirectoryElementContent@StateRepoPackageInformation@@AEAAXPEBG@Z; StateRepoPackageInformation::ParseAndAddExcludedDirectoryElementContent(ushort const *)
0x1800989d3  mov     [rbp+230h+var_228], rax
0x1800989d7  lea     rax, ??_9StateRepoPackageInformation@@$BFI@AA; [thunk]: StateRepoPackageInformation::`vcall'{88,{flat}}
0x1800989de  mov     [rbp+230h+var_220], rax
0x1800989e2  lea     rax, [r12+96h]
0x1800989ea  mov     [rbp+230h+var_218], rax
0x1800989ee  lea     rax, aRegistrywritev; "RegistryWriteVirtualization"
0x1800989f5  mov     [rbp+230h+var_210], rax
0x1800989f9  lea     rax, aExcludedkeys; "ExcludedKeys"
0x180098a00  mov     [rbp+230h+var_208], rax
0x180098a04  lea     rax, aExcludedkey; "ExcludedKey"
0x180098a0b  mov     [rbp+230h+var_200], rax
0x180098a0f  lea     rax, ?ParseAndAddExcludedKeyElementContent@StateRepoPackageInformation@@AEAAXPEBG@Z; StateRepoPackageInformation::ParseAndAddExcludedKeyElementContent(ushort const *)
0x180098a16  mov     [rbp+230h+var_1F8], rax
0x180098a1a  lea     r13, [rbp+230h+var_250]
0x180098a1e  mov     rcx, r12
0x180098a21  mov     rax, [r13+0]
0x180098a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098a2a  test    al, al
0x180098a2c  jz      loc_180099158
0x180098a32  mov     [rsp+330h+var_2C8], rsi
0x180098a37  mov     rbx, [rbp+230h+var_288]
0x180098a3b  mov     rax, [rbx]
0x180098a3e  mov     rdi, [rax+90h]
0x180098a45  mov     [rsp+330h+var_2C8], rsi
0x180098a4a  lea     rdx, [r13+10h]
0x180098a4e  lea     rcx, [rbp+230h+var_1A8]
0x180098a55  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180098a5a  nop
0x180098a5b  lea     r9, [rsp+330h+var_2C8]
0x180098a60  mov     r8, [rax+18h]
0x180098a64  mov     rdx, [rbp+230h+var_2A8]
0x180098a68  mov     rcx, rbx
0x180098a6b  mov     rax, rdi
0x180098a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098a73  mov     rcx, [rbp+238h]; this
0x180098a7a  test    eax, eax
0x180098a7c  js      loc_18009922F
0x180098a82  mov     [rbp+230h+var_1F0], rsi
0x180098a86  mov     dword ptr [rsp+330h+var_2D8], esi
0x180098a8a  mov     rcx, [rsp+330h+var_2C8]
0x180098a8f  mov     rax, [rcx]
0x180098a92  lea     rdx, [rsp+330h+var_2D8]
0x180098a97  mov     rax, [rax+38h]
0x180098a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098aa0  mov     rcx, [rbp+238h]; this
0x180098aa7  test    eax, eax
0x180098aa9  js      loc_18009921A
0x180098aaf  cmp     dword ptr [rsp+330h+var_2D8], esi
0x180098ab3  jnz     short loc_180098AC1
0x180098ab5  mov     rax, [r13+8]
0x180098ab9  mov     byte ptr [rax], 1
0x180098abc  jmp     loc_180099141
0x180098ac1  mov     byte ptr [rsp+330h+var_300+3], sil
0x180098ac6  mov     [rbp+230h+var_278], rsi
0x180098aca  mov     r15, rsi
0x180098acd  mov     [rbp+230h+var_270], rsi
0x180098ad1  mov     rbx, [rsp+330h+var_2C8]
0x180098ad6  mov     [rbp+230h+var_2A0], rbx
0x180098ada  mov     [rbp+230h+var_298], esi
0x180098add  mov     [rbp+230h+var_290], rsi
0x180098ae1  mov     dword ptr [rsp+330h+var_2E8], esi
0x180098ae5  mov     rax, [rbx]
0x180098ae8  lea     rdx, [rsp+330h+var_2E8]
0x180098aed  mov     rcx, rbx
0x180098af0  mov     rax, [rax+38h]
0x180098af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098af9  mov     rcx, [rbp+238h]; this
0x180098b00  test    eax, eax
0x180098b02  js      loc_180099395
0x180098b08  mov     [rbp+230h+var_1E0], rbx
0x180098b0c  mov     eax, dword ptr [rsp+330h+var_2E8]
0x180098b10  mov     [rbp+230h+var_1D8], eax
0x180098b13  mov     [rbp+230h+var_1D0], rsi
0x180098b17  or      r14d, 4
0x180098b1b  mov     dword ptr [rsp+330h+var_300+4], r14d
0x180098b20  mov     edx, [rbp+230h+var_298]
0x180098b23  cmp     edx, eax
0x180098b25  jz      loc_1800990E6
0x180098b2b  mov     rbx, [rbp+230h+var_2A0]
0x180098b2f  mov     rax, [rbx]
0x180098b32  mov     rdi, [rax+30h]
0x180098b36  mov     rcx, [rbp+230h+var_290]
0x180098b3a  test    rcx, rcx
0x180098b3d  jz      short loc_180098B52
0x180098b3f  mov     [rbp+230h+var_290], rsi
0x180098b43  mov     rdx, [rcx]
0x180098b46  mov     rax, [rdx+10h]
0x180098b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098b4f  mov     edx, [rbp+230h+var_298]
0x180098b52  lea     r8, [rbp+230h+var_290]
0x180098b56  mov     rcx, rbx
0x180098b59  mov     rax, rdi
0x180098b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098b61  mov     rcx, [rbp+238h]; this
0x180098b68  test    eax, eax
0x180098b6a  js      loc_180099380
0x180098b70  mov     rdi, [rbp+230h+var_290]
0x180098b74  mov     [rbp+230h+var_1E8], rdi
0x180098b78  test    rdi, rdi
0x180098b7b  jz      short loc_180098B8D
0x180098b7d  mov     rax, [rdi]
0x180098b80  mov     rcx, rdi
0x180098b83  mov     rax, [rax+8]
0x180098b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098b8c  nop
0x180098b8d  mov     rbx, [rbp+238h]
0x180098b94  call    IsSRDictionaryToPropertySetPresent
0x180098b99  test    al, al
0x180098b9b  jz      loc_180099365
0x180098ba1  mov     dword ptr [rsp+330h+var_2D8+4], esi
0x180098ba5  mov     [rsp+330h+pv], rsi
0x180098baa  mov     rax, [rdi]
0x180098bad  lea     rcx, [rsp+330h+pv]
0x180098bb2  mov     qword ptr [rbp+230h+hstringHeader.Reserved], rcx
0x180098bb6  mov     qword ptr [rbp+230h+hstringHeader.Reserved+8], rsi
0x180098bba  mov     byte ptr [rbp+230h+hstringHeader.Reserved+10h], 1
0x180098bbe  lea     r8, [rbp+230h+hstringHeader.Reserved+8]
0x180098bc2  lea     rdx, [rsp+330h+var_2D8+4]
0x180098bc7  mov     rcx, rdi
0x180098bca  mov     rax, [rax+80h]
0x180098bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098bd6  mov     rcx, [rbp+238h]; this
0x180098bdd  test    eax, eax
0x180098bdf  js      loc_180099350
0x180098be5  cmp     byte ptr [rbp+230h+hstringHeader.Reserved+10h], sil
0x180098be9  jz      short loc_180098C0B
0x180098beb  mov     rdx, qword ptr [rbp+230h+hstringHeader.Reserved]
0x180098bef  mov     rcx, [rdx]; pv
0x180098bf2  mov     rax, qword ptr [rbp+230h+hstringHeader.Reserved+8]
0x180098bf6  mov     [rdx], rax
0x180098bf9  test    rcx, rcx
0x180098bfc  jz      short loc_180098C0B
0x180098bfe  call    cs:__imp_CoTaskMemFree
0x180098c05  nop     dword ptr [rax+rax+00h]
0x180098c0a  nop
0x180098c0b  mov     [rsp+330h+var_2C0], rsi
0x180098c10  lea     r8, [rsp+330h+var_2C0]
0x180098c15  mov     rdx, [rsp+330h+pv]
0x180098c1a  mov     ecx, dword ptr [rsp+330h+var_2D8+4]
0x180098c1e  call    cs:__imp_SRDictionaryToPropertySet
0x180098c25  nop     dword ptr [rax+rax+00h]
0x180098c2a  mov     rcx, [rbp+238h]; this
0x180098c31  test    eax, eax
0x180098c33  js      loc_18009933B
0x180098c39  mov     [rsp+330h+var_2E0], rsi
0x180098c3e  mov     rcx, [rsp+330h+var_2C0]
0x180098c43  mov     rax, [rcx]
0x180098c46  lea     r8, [rsp+330h+var_2E0]
0x180098c4b  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180098c52  mov     rax, [rax]
0x180098c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c5a  mov     rcx, [rbp+238h]
0x180098c61  test    eax, eax
0x180098c63  js      loc_180099326
0x180098c69  or      r14d, 18h
0x180098c6d  mov     dword ptr [rsp+330h+var_300+4], r14d
0x180098c72  mov     rcx, [rsp+330h+var_2C0]
0x180098c77  test    rcx, rcx
0x180098c7a  jz      short loc_180098C89
0x180098c7c  mov     rax, [rcx]
0x180098c7f  mov     rax, [rax+10h]
0x180098c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c88  nop
0x180098c89  mov     rcx, [rsp+330h+pv]; pv
0x180098c8e  mov     [rsp+330h+pv], rsi
0x180098c93  test    rcx, rcx
0x180098c96  jz      short loc_180098CA4
0x180098c98  call    cs:__imp_CoTaskMemFree
0x180098c9f  nop     dword ptr [rax+rax+00h]
0x180098ca4  mov     byte ptr [rsp+330h+var_300], sil
0x180098ca9  mov     rbx, [rsp+330h+var_2E0]
0x180098cae  mov     rax, [rbx]
0x180098cb1  mov     rsi, [rax+40h]
0x180098cb5  and     [rbp+230h+string], 0
0x180098cbd  lea     r9, [rbp+230h+string]; string
0x180098cc4  lea     r8, [rbp+230h+hstringHeader]; hstringHeader
0x180098cc8  mov     edx, 5; length
0x180098ccd  lea     rcx, aText; "#text"
0x180098cd4  call    cs:__imp_WindowsCreateStringReference
0x180098cdb  nop     dword ptr [rax+rax+00h]
0x180098ce0  test    eax, eax
0x180098ce2  js      loc_18009931E
0x180098ce8  lea     r8, [rsp+330h+var_300]
0x180098ced  mov     rdx, [rbp+230h+string]
0x180098cf4  mov     rcx, rbx
0x180098cf7  mov     rax, rsi
0x180098cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098cff  mov     rcx, [rbp+238h]; this
0x180098d06  xor     esi, esi
0x180098d08  test    eax, eax
0x180098d0a  js      loc_180099309
0x180098d10  cmp     byte ptr [rsp+330h+var_300], sil
0x180098d15  jz      loc_180098EBB
0x180098d1b  mov     [rsp+330h+var_2F8], rsi
0x180098d20  mov     rbx, [rsp+330h+var_2E0]
0x180098d25  mov     rax, [rbx]
0x180098d28  mov     rsi, [rax+30h]
0x180098d2c  and     [rsp+330h+var_2F8], 0
0x180098d32  and     [rbp+230h+string], 0
0x180098d3a  lea     r9, [rbp+230h+string]; string
0x180098d41  lea     r8, [rbp+230h+hstringHeader]; hstringHeader
0x180098d45  mov     edx, 5; length
0x180098d4a  lea     rcx, aText; "#text"
0x180098d51  call    cs:__imp_WindowsCreateStringReference
0x180098d58  nop     dword ptr [rax+rax+00h]
0x180098d5d  test    eax, eax
0x180098d5f  js      loc_180099298
0x180098d65  lea     r8, [rsp+330h+var_2F8]
0x180098d6a  mov     rdx, [rbp+230h+string]
0x180098d71  mov     rcx, rbx
0x180098d74  mov     rax, rsi
0x180098d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098d7c  mov     rcx, [rbp+238h]; this
0x180098d83  xor     esi, esi
0x180098d85  test    eax, eax
0x180098d87  js      loc_180099283
0x180098d8d  mov     [rsp+330h+var_2D0], rsi
0x180098d92  mov     [rsp+330h+var_2F0], rsi
0x180098d97  mov     rcx, [rsp+330h+var_2F8]
0x180098d9c  mov     rax, [rcx]
0x180098d9f  lea     r8, [rsp+330h+var_2F0]
0x180098da4  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180098dab  mov     rax, [rax]
0x180098dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098db3  mov     rcx, [rbp+238h]; this
0x180098dba  test    eax, eax
0x180098dbc  js      loc_18009926E
0x180098dc2  or      r14d, 20h
0x180098dc6  mov     dword ptr [rsp+330h+var_300+4], r14d
0x180098dcb  mov     rbx, [rsp+330h+var_2F0]
0x180098dd0  mov     rax, [rbx]
0x180098dd3  mov     r12, [rax+98h]
  ... truncated ...
```
