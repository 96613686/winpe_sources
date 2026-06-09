# CommitProtectPCSettingsCore(bool *,bool *,uint,OOBE_PROTECTPC_COMMIT_ENTRY const *,bool,bool)

- ea: `0x180009b90`
- end: `0x18000a3be`
- name: `?CommitProtectPCSettingsCore@@YAJPEA_N0IPEBUOOBE_PROTECTPC_COMMIT_ENTRY@@_N2@Z`
- size: `2094`
- prototype: `__int64 __fastcall(bool *, bool *, unsigned int, const struct OOBE_PROTECTPC_COMMIT_ENTRY *, bool, bool)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a3d0`

## callees

- `0x180002b60`
- `0x180003230`
- `0x180009100`
- `0x18000953c`
- `0x180009760`
- `0x180009784`
- `0x1800097f4`
- `0x180009814`
- `0x180009834`
- `0x180009b90`
- `0x18000a4f8`
- `0x18000a788`
- `0x18000ac18`
- `0x18000ac54`
- `0x18000ae3c`
- `0x18000b098`
- `0x18000b0c8`
- `0x18000b200`
- `0x18000b254`
- `0x180069304`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fd9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a30e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a30e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a2b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a2b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009f6a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009f6a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009dc0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009dc0`

## string_xrefs

- `0x18000a171`: `ProtectPC Task - setting %s value to (%d)`
- `0x18000a25b`: `ProtectPC Task - setting %s value for Wow64`
- `0x18000a065`: `ProtectPC Task - setting %s value to (%s)`
- `0x180009e2b`: `ProtectPC Task - setting %s capability to value %s via CAM %s`
- `0x180009d74`: `ProtectPC Task - setting %s to value %s via custom commit function %s with 0x%d`
- `0x180009cd6`: `ProtectPC Task - Encountered unexpected entryType (%d)`
- `0x180009c65`: `ProtectPC Task - Leaving default state in place for %s value`
- `0x180009da0`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CommitProtectPCSettingsCore(
        bool *a1,
        bool *a2,
        __int64 a3,
        const struct OOBE_PROTECTPC_COMMIT_ENTRY *a4,
        bool a5,
        bool a6)
{
  __int64 v7; // r15
  __m128i v8; // xmm6
  __m128i v9; // xmm7
  __m128i v10; // xmm8
  __m128i v11; // xmm2
  __m128i v12; // xmm1
  __int64 (__fastcall *v13)(_QWORD); // xmm3_8
  int v14; // eax
  __int64 v15; // r12
  char v16; // di
  bool v17; // dl
  HKEY v18; // rsi
  __int64 v19; // rcx
  signed int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // rdx
  const wchar_t *v23; // rax
  const wchar_t *v24; // r9
  int ActivationFactory; // eax
  unsigned __int8 v26; // cl
  const wchar_t *v27; // rax
  const wchar_t *v28; // r9
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, BYTE *); // rbx
  __int64 v31; // rax
  int v32; // eax
  char v33; // al
  int v34; // esi
  int v35; // eax
  int token_information; // eax
  void *v37; // r14
  BOOL v38; // ebx
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, _QWORD, _QWORD); // rbx
  __int64 v41; // rax
  int v42; // eax
  signed int LastError; // eax
  const unsigned __int16 *v44; // rdi
  unsigned __int64 v45; // xmm2_8
  const unsigned __int16 *v46; // r14
  int v47; // eax
  int v48; // eax
  __int64 v49; // rdx
  int v50; // r9d
  int v51; // eax
  const unsigned __int16 *v52; // r14
  int v53; // eax
  int RedirectionKeyPath; // eax
  __int64 v55; // rdx
  LSTATUS v56; // eax
  unsigned int v57; // eax
  void (__fastcall *v58)(_QWORD, __int64); // xmm8_8
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  __int64 samDesired; // [rsp+28h] [rbp-D8h]
  bool v63; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v65; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v66; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v69; // [rsp+80h] [rbp-80h] BYREF
  bool *v70; // [rsp+88h] [rbp-78h]
  __m128i v71; // [rsp+90h] [rbp-70h]
  _OWORD v72[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 (__fastcall *v73)(_QWORD); // [rsp+E0h] [rbp-20h]
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v75; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v70 = a2;
  v7 = 0;
  v65 = 0;
  do
  {
    v8 = *(__m128i *)&qword_18006F320[11 * v7];
    v71 = v8;
    v9 = *(__m128i *)&off_18006F330[11 * v7];
    v72[0] = v9;
    v10 = *(__m128i *)&qword_18006F340[11 * v7];
    v72[1] = v10;
    v11 = *(__m128i *)&qword_18006F350[11 * v7];
    v72[2] = v11;
    v12 = *(__m128i *)&qword_18006F350[11 * v7 + 2];
    v72[3] = v12;
    v13 = (__int64 (__fastcall *)(_QWORD))qword_18006F368[11 * v7 + 1];
    v73 = v13;
    v14 = _mm_cvtsi128_si32(v8);
    v15 = v14;
    if ( !a2[v14] )
      goto LABEL_5;
    v16 = _mm_cvtsi128_si32(_mm_srli_si128(v12, 8));
    if ( a6 )
    {
      if ( (v16 & 4) == 0 )
        goto LABEL_5;
    }
    else if ( (v16 & 8) == 0 )
    {
      goto LABEL_5;
    }
    v17 = a1[v14];
    if ( !v17 && (v16 & 1) != 0 && !a5 )
    {
LABEL_5:
      UnattendLogW(
        0,
        L"ProtectPC Task - Leaving default state in place for %s value",
        _mm_srli_si128(v9, 8).m128i_u64[0],
        a4);
      goto LABEL_91;
    }
    v18 = (HKEY)(a6 - 0x7FFFFFFFLL);
    if ( !v8.m128i_i32[1] )
    {
      v50 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 4));
      v51 = _mm_cvtsi128_si32(v11);
      if ( v17 )
        v50 = v51;
      *(_DWORD *)Data = v50;
      v52 = (const unsigned __int16 *)_mm_srli_si128(v9, 8).m128i_u64[0];
      UnattendLogW(0, L"ProtectPC Task - setting %s value to (%d)", v52);
      v53 = SHRegSetDWORD(v18, (const unsigned __int16 *)v9.m128i_i64[0], v52, *(unsigned int *)Data);
      v20 = v53;
      if ( v53 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC6,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
          (const char *)(unsigned int)v53,
          dwOptions);
      if ( !a6 )
        goto LABEL_79;
      v66 = 0;
      v63 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v66,
        0);
      RedirectionKeyPath = Details::TryGetRedirectionKeyPath(
                             (const unsigned __int16 *)_mm_srli_si128(v8, 8).m128i_i64[0],
                             (const unsigned __int16 *)v9.m128i_i64[0],
                             &v66,
                             &v63);
      v20 = RedirectionKeyPath;
      if ( RedirectionKeyPath >= 0 )
      {
        if ( !v63 )
          goto LABEL_78;
        RedirectionKeyPath = SHRegSetDWORD(v18, v66, v52, *(unsigned int *)Data);
        v20 = RedirectionKeyPath;
        if ( RedirectionKeyPath >= 0 )
          goto LABEL_78;
        v55 = 211;
      }
      else
      {
        v55 = 207;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v55,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
        (const char *)(unsigned int)RedirectionKeyPath,
        dwOptions);
LABEL_78:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
LABEL_79:
      if ( (v16 & 2) != 0 )
      {
        UnattendLogW(0, L"ProtectPC Task - setting %s value for Wow64", v52);
        hKey = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
        v56 = RegCreateKeyExW(v18, (LPCWSTR)v9.m128i_i64[0], 0, 0, 0, 0x202u, 0, &hKey, 0);
        v20 = v56;
        if ( v56 > 0 )
          v20 = (unsigned __int16)v56 | 0x80070000;
        if ( v20 >= 0 )
        {
          v57 = RegSetValueExW(hKey, v52, 0, 4u, Data, 4u);
          v20 = v57;
          if ( v57 )
          {
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0xDE,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
              (const char *)v57,
              dwOptions);
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xDC,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
            (const char *)(unsigned int)v20,
            dwOptionsa);
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      }
      goto LABEL_88;
    }
    if ( v8.m128i_i32[1] != 1 )
    {
      if ( v8.m128i_i32[1] != 2 )
      {
        v19 = (unsigned int)(v8.m128i_i32[1] - 3);
        if ( v8.m128i_i32[1] == 3 )
        {
          LODWORD(v19) = v17;
          v20 = ((__int64 (__fastcall *)(__int64))v10.m128i_i64[0])(v19);
          if ( v20 < 0 )
          {
            v22 = 297;
            goto LABEL_20;
          }
        }
        else
        {
          if ( v8.m128i_i32[1] != 4 )
          {
            v20 = 0;
            UnattendLogW(1, L"ProtectPC Task - Encountered unexpected entryType (%d)", HIDWORD(v8.m128i_i64[0]), a4);
            goto LABEL_89;
          }
          v20 = v13(a1[v14]);
          if ( v20 < 0 )
          {
            v22 = 304;
LABEL_20:
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v22,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
              (const char *)(unsigned int)v20,
              dwOptions);
          }
        }
        v23 = L"succeeded";
        if ( v20 < 0 )
          v23 = L"failed";
        v24 = L"enabled";
        if ( !a1[v15] )
          v24 = L"disabled";
        LODWORD(samDesired) = v20;
        UnattendLogW(
          (v20 >> 31) & 2,
          L"ProtectPC Task - setting %s to value %s via custom commit function %s with 0x%d",
          `CanonicalNameFromProtectPcId'::`2'::canonicalNames[v15],
          v24,
          v23,
          samDesired);
        goto LABEL_89;
      }
      v65 = 0;
      v75 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
        0x46u,
        0x45u);
      ActivationFactory = RoGetActivationFactory(v75, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v65);
      v20 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        *(_QWORD *)Data = 0;
        v29 = v65;
        v30 = *(__int64 (__fastcall **)(__int64, _QWORD, BYTE *))(*(_QWORD *)v65 + 48LL);
        *(_QWORD *)Data = 0;
        v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (char *)v72 + 8);
        v32 = v30(v29, *(_QWORD *)(v31 + 24), Data);
        v20 = v32;
        if ( v32 >= 0 )
        {
          v33 = 1;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x105,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
            (const char *)(unsigned int)v32,
            dwOptions);
          v33 = 0;
        }
        if ( v33 )
        {
          v34 = -a1[v15];
          if ( a6 )
          {
            v35 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)Data + 112LL))(
                    *(_QWORD *)Data,
                    2 - (unsigned int)a1[v15]);
            v20 = v35;
            if ( v35 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x10D,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
                (const char *)(unsigned int)v35,
                dwOptions);
          }
          else
          {
            Block = 0;
            token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, 0);
            v20 = token_information;
            v37 = Block;
            if ( token_information >= 0 )
            {
              v66 = 0;
              *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)&v66;
              hstringHeader.Reserved.Reserved2[16] = 1;
              v38 = ConvertSidToStringSidW(*(PSID *)Block, (LPWSTR *)&hstringHeader.Reserved.Reserved2[8]);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
              if ( v38 )
              {
                v39 = *(_QWORD *)Data;
                v40 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(**(_QWORD **)Data + 120LL);
                v69 = v66;
                v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v69);
                v42 = v40(v39, *(_QWORD *)(v41 + 24), (unsigned int)(v34 + 2));
                v20 = v42;
                if ( v42 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x117,
                    (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
                    (const char *)(unsigned int)v42,
                    dwOptions);
              }
              else
              {
                LastError = GetLastError();
                v20 = LastError;
                if ( LastError > 0 )
                  v20 = (unsigned __int16)LastError | 0x80070000;
                wil::details::in1diag3::Log_Hr(
                  retaddr,
                  (void *)0x11C,
                  (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
                  (const char *)(unsigned int)v20,
                  dwOptions);
              }
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v66);
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x112,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
                (const char *)(unsigned int)token_information,
                dwOptions);
            }
            if ( v37 )
              operator delete(v37);
          }
        }
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(Data);
        if ( v20 >= 0 )
        {
          v26 = 1;
          goto LABEL_29;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x102,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
          (const char *)(unsigned int)ActivationFactory,
          dwOptions);
      }
      v26 = 0;
LABEL_29:
      v27 = L"succeeded";
      if ( !v26 )
        v27 = L"failed";
      v28 = L"Allow";
      if ( !a1[v15] )
        v28 = L"Deny";
      UnattendLogW(
        2 * (v26 ^ 1u),
        L"ProtectPC Task - setting %s capability to value %s via CAM %s",
        _mm_srli_si128(v9, 8).m128i_u64[0],
        v28,
        v27);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v65);
      goto LABEL_89;
    }
    v44 = (const unsigned __int16 *)v12.m128i_i64[0];
    v45 = _mm_srli_si128(v11, 8).m128i_u64[0];
    if ( v17 )
      v44 = (const unsigned __int16 *)v45;
    v46 = (const unsigned __int16 *)_mm_srli_si128(v9, 8).m128i_u64[0];
    UnattendLogW(0, L"ProtectPC Task - setting %s value to (%s)", v46, v44);
    v47 = SHRegSetString(v18, (const unsigned __int16 *)v9.m128i_i64[0], v46, v44);
    v20 = v47;
    if ( v47 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
        (const char *)(unsigned int)v47,
        dwOptions);
    if ( a6 )
    {
      *(_QWORD *)Data = 0;
      v63 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        Data,
        0);
      v48 = Details::TryGetRedirectionKeyPath(
              (const unsigned __int16 *)_mm_srli_si128(v8, 8).m128i_i64[0],
              (const unsigned __int16 *)v9.m128i_i64[0],
              (unsigned __int16 **)Data,
              &v63);
      v20 = v48;
      if ( v48 < 0 )
      {
        v49 = 242;
        goto LABEL_65;
      }
      if ( v63 )
      {
        v48 = SHRegSetString(v18, *(const unsigned __int16 **)Data, v46, v44);
        v20 = v48;
        if ( v48 < 0 )
        {
          v49 = 246;
LABEL_65:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v49,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\oobesettingsutil.h",
            (const char *)(unsigned int)v48,
            dwOptions);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Data);
    }
LABEL_88:
    v7 = v65;
LABEL_89:
    v58 = (void (__fastcall *)(_QWORD, __int64))_mm_srli_si128(v10, 8).m128i_u64[0];
    if ( v58 )
    {
      LOBYTE(v21) = a1[v15];
      v58((unsigned int)v20, v21);
    }
LABEL_91:
    v65 = ++v7;
    a2 = v70;
  }
  while ( v7 != 14 );
  return 0;
}

```

## disassembly

```asm
0x180009b90  mov     rax, rsp
0x180009b93  push    rbp
0x180009b94  push    rbx
0x180009b95  push    rsi
0x180009b96  push    rdi
0x180009b97  push    r12
0x180009b99  push    r13
0x180009b9b  push    r14
0x180009b9d  push    r15
0x180009b9f  lea     rbp, [rsp-58h]
0x180009ba4  sub     rsp, 158h
0x180009bab  movaps  xmmword ptr [rax-58h], xmm6
0x180009baf  movaps  xmmword ptr [rax-68h], xmm7
0x180009bb3  movaps  xmmword ptr [rax-78h], xmm8
0x180009bb8  mov     rax, cs:__security_cookie
0x180009bbf  xor     rax, rsp
0x180009bc2  mov     [rbp+90h+var_80], rax
0x180009bc6  mov     [rbp+90h+var_108], rdx
0x180009bca  mov     r13, rcx
0x180009bcd  xor     r15d, r15d
0x180009bd0  mov     [rsp+190h+var_130], r15
0x180009bd5  lea     r14, __ImageBase
0x180009bdc  imul    rax, r15, 58h ; 'X'
0x180009be0  movups  xmm6, xmmword ptr [rax+r14+6F320h]
0x180009be9  movaps  [rbp+90h+var_100], xmm6
0x180009bed  movups  xmm7, xmmword ptr [rax+r14+6F330h]
0x180009bf6  movaps  [rbp+90h+var_F0], xmm7
0x180009bfa  movups  xmm8, xmmword ptr [rax+r14+6F340h]
0x180009c03  movaps  [rbp+90h+var_E0], xmm8
0x180009c08  movups  xmm2, xmmword ptr [rax+r14+6F350h]
0x180009c11  movaps  [rbp+90h+var_D0], xmm2
0x180009c15  movups  xmm1, xmmword ptr [rax+r14+6F360h]
0x180009c1e  movaps  [rbp+90h+var_C0], xmm1
0x180009c22  movsd   xmm3, qword ptr [rax+r14+6F370h]
0x180009c2c  movsd   [rbp+90h+var_B0], xmm3
0x180009c31  movd    eax, xmm6
0x180009c35  movsxd  r12, eax
0x180009c38  cmp     byte ptr [r12+rdx], 0
0x180009c3d  jz      short loc_180009C5B
0x180009c3f  movdqa  xmm0, xmm1
0x180009c43  psrldq  xmm0, 8
0x180009c48  movd    edi, xmm0
0x180009c4c  cmp     [rbp+90h+arg_28], 0
0x180009c53  jz      short loc_180009C78
0x180009c55  test    dil, 4
0x180009c59  jnz     short loc_180009C7E
0x180009c5b  psrldq  xmm7, 8
0x180009c60  movq    r8, xmm7
0x180009c65  lea     rdx, aProtectpcTaskL; "ProtectPC Task - Leaving default state "...
0x180009c6c  xor     ecx, ecx
0x180009c6e  call    UnattendLogW
0x180009c73  jmp     loc_18000A373
0x180009c78  test    dil, 8
0x180009c7c  jz      short loc_180009C5B
0x180009c7e  movzx   edx, byte ptr [r12+r13]
0x180009c83  test    dl, dl
0x180009c85  jnz     short loc_180009C95
0x180009c87  test    dil, 1
0x180009c8b  jz      short loc_180009C95
0x180009c8d  cmp     [rbp+90h+arg_20], dl
0x180009c93  jz      short loc_180009C5B
0x180009c95  movzx   esi, [rbp+90h+arg_28]
0x180009c9c  add     rsi, 0FFFFFFFF80000001h
0x180009ca3  movq    r8, xmm6
0x180009ca8  shr     r8, 20h
0x180009cac  mov     ecx, r8d
0x180009caf  test    r8d, r8d
0x180009cb2  jz      loc_18000A143
0x180009cb8  sub     ecx, 1
0x180009cbb  jz      loc_18000A03C
0x180009cc1  sub     ecx, 1
0x180009cc4  jz      loc_180009D85
0x180009cca  sub     ecx, 1
0x180009ccd  jz      short loc_180009D03
0x180009ccf  cmp     ecx, 1
0x180009cd2  jz      short loc_180009CEA
0x180009cd4  xor     ebx, ebx
0x180009cd6  lea     rdx, aProtectpcTaskE; "ProtectPC Task - Encountered unexpected"...
0x180009cdd  lea     ecx, [rbx+1]
0x180009ce0  call    UnattendLogW
0x180009ce5  jmp     loc_18000A351
0x180009cea  mov     ecx, edx
0x180009cec  movq    rax, xmm3
0x180009cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cf6  mov     ebx, eax
0x180009cf8  test    eax, eax
0x180009cfa  jns     short loc_180009D30
0x180009cfc  mov     edx, 130h
0x180009d01  jmp     short loc_180009D1A
0x180009d03  movq    rax, xmm8
0x180009d08  mov     cl, dl
0x180009d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d0f  mov     ebx, eax
0x180009d11  test    eax, eax
0x180009d13  jns     short loc_180009D30
0x180009d15  mov     edx, 129h; void *
0x180009d1a  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x180009d21  mov     r9d, ebx; char *
0x180009d24  mov     rcx, [rbp+98h]; this
0x180009d2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009d30  lea     rax, aSucceeded; "succeeded"
0x180009d37  test    ebx, ebx
0x180009d39  lea     rcx, aFailed; "failed"
0x180009d40  cmovs   rax, rcx
0x180009d44  lea     r9, aEnabled_0; "enabled"
0x180009d4b  cmp     byte ptr [r12+r13], 0
0x180009d50  lea     rcx, aDisabled; "disabled"
0x180009d57  cmovz   r9, rcx
0x180009d5b  mov     ecx, ebx
0x180009d5d  sar     ecx, 1Fh
0x180009d60  and     ecx, 2
0x180009d63  mov     dword ptr [rsp+190h+samDesired], ebx
0x180009d67  mov     qword ptr [rsp+190h+dwOptions], rax
0x180009d6c  mov     r8, ds:rva ?canonicalNames@?1??CanonicalNameFromProtectPcId@@YAQEBGW4OOBE_PROTECTPC_BOOLEAN_SETTING@@@Z@4QBQEBGB[r14+r12*8]; ushort const * const near * const `CanonicalNameFromProtectPcId(OOBE_PROTECTPC_BOOLEAN_SETTING)'::`2'::canonicalNames ...
0x180009d74  lea     rdx, aProtectpcTaskS_0; "ProtectPC Task - setting %s to value %s"...
0x180009d7b  call    UnattendLogW
0x180009d80  jmp     loc_18000A351
0x180009d85  mov     [rsp+190h+var_130], 0
0x180009d8e  mov     [rbp+90h+var_88], 0
0x180009d96  mov     r9d, 45h ; 'E'; unsigned int
0x180009d9c  lea     r8d, [r9+1]; unsigned int
0x180009da0  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x180009da7  lea     rcx, [rbp+90h+hstringHeader]; hstringHeader
0x180009dab  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180009db0  lea     r8, [rsp+190h+var_130]
0x180009db5  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x180009dbc  mov     rcx, [rbp+90h+var_88]
0x180009dc0  call    cs:__imp_RoGetActivationFactory
0x180009dc6  mov     ebx, eax
0x180009dc8  mov     rcx, [rbp+98h]; this
0x180009dcf  test    eax, eax
0x180009dd1  jns     short loc_180009E47
0x180009dd3  mov     r9d, eax; char *
0x180009dd6  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x180009ddd  mov     edx, 102h; void *
0x180009de2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009de7  xor     cl, cl
0x180009de9  lea     rax, aSucceeded; "succeeded"
0x180009df0  test    cl, cl
0x180009df2  lea     rdx, aFailed; "failed"
0x180009df9  cmovz   rax, rdx
0x180009dfd  lea     rdx, aDeny; "Deny"
0x180009e04  lea     r9, aAllow; "Allow"
0x180009e0b  cmp     byte ptr [r12+r13], 0
0x180009e10  cmovz   r9, rdx
0x180009e14  movzx   ecx, cl
0x180009e17  xor     ecx, 1
0x180009e1a  add     ecx, ecx
0x180009e1c  mov     qword ptr [rsp+190h+dwOptions], rax
0x180009e21  psrldq  xmm7, 8
0x180009e26  movq    r8, xmm7
0x180009e2b  lea     rdx, aProtectpcTaskS_3; "ProtectPC Task - setting %s capability "...
0x180009e32  call    UnattendLogW
0x180009e37  nop
0x180009e38  lea     rcx, [rsp+190h+var_130]
0x180009e3d  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180009e42  jmp     loc_18000A351
0x180009e47  mov     qword ptr [rsp+190h+Data], 0
0x180009e50  mov     rdi, [rsp+190h+var_130]
0x180009e55  mov     rax, [rdi]
0x180009e58  mov     rbx, [rax+30h]
0x180009e5c  mov     qword ptr [rsp+190h+Data], 0
0x180009e65  lea     rdx, [rbp+90h+var_F0+8]
0x180009e69  lea     rcx, [rbp+90h+hstringHeader]
0x180009e6d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180009e72  nop
0x180009e73  lea     r8, [rsp+190h+Data]
0x180009e78  mov     rdx, [rax+18h]
0x180009e7c  mov     rcx, rdi
0x180009e7f  mov     rax, rbx
0x180009e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e87  mov     ebx, eax
0x180009e89  mov     rcx, [rbp+98h]; this
0x180009e90  test    eax, eax
0x180009e92  jns     short loc_180009EAC
0x180009e94  mov     r9d, eax; char *
0x180009e97  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x180009e9e  mov     edx, 105h; void *
0x180009ea3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009ea8  xor     al, al
0x180009eaa  jmp     short loc_180009EAE
0x180009eac  mov     al, 1
0x180009eae  test    al, al
0x180009eb0  jz      loc_18000A023
0x180009eb6  mov     al, [r12+r13]
0x180009eba  neg     al
0x180009ebc  sbb     esi, esi
0x180009ebe  cmp     [rbp+90h+arg_28], 0
0x180009ec5  jz      short loc_180009F05
0x180009ec7  mov     rcx, qword ptr [rsp+190h+Data]
0x180009ecc  mov     rax, [rcx]
0x180009ecf  lea     edx, [rsi+2]
0x180009ed2  mov     rax, [rax+70h]
0x180009ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009edb  mov     ebx, eax
0x180009edd  mov     rcx, [rbp+98h]; this
0x180009ee4  test    eax, eax
0x180009ee6  jns     loc_18000A023
0x180009eec  mov     r9d, eax; char *
0x180009eef  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x180009ef6  mov     edx, 10Dh; void *
0x180009efb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009f00  jmp     loc_18000A023
0x180009f05  mov     [rsp+190h+Block], 0
0x180009f0e  xor     edx, edx
0x180009f10  lea     rcx, [rsp+190h+Block]
0x180009f15  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180009f1a  mov     ebx, eax
0x180009f1c  mov     rcx, [rbp+98h]; this
0x180009f23  mov     r14, [rsp+190h+Block]
0x180009f28  test    eax, eax
0x180009f2a  jns     short loc_180009F45
0x180009f2c  mov     r9d, eax; char *
0x180009f2f  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x180009f36  mov     edx, 112h; void *
0x180009f3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009f40  jmp     loc_18000A015
0x180009f45  mov     [rsp+190h+var_128], 0
0x180009f4e  lea     rax, [rsp+190h+var_128]
0x180009f53  mov     qword ptr [rbp+90h+hstringHeader.Reserved], rax
0x180009f57  mov     qword ptr [rbp+90h+hstringHeader.Reserved+8], 0
0x180009f5f  mov     byte ptr [rbp+90h+hstringHeader.Reserved+10h], 1
0x180009f63  lea     rdx, [rbp+90h+hstringHeader.Reserved+8]; StringSid
0x180009f67  mov     rcx, [r14]; Sid
0x180009f6a  call    cs:__imp_ConvertSidToStringSidW
0x180009f70  mov     ebx, eax
0x180009f72  lea     rcx, [rbp+90h+hstringHeader]
0x180009f76  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180009f7b  test    ebx, ebx
0x180009f7d  jz      short loc_180009FD9
0x180009f7f  mov     rdi, qword ptr [rsp+190h+Data]
0x180009f84  mov     rax, [rdi]
0x180009f87  mov     rbx, [rax+78h]
0x180009f8b  mov     rdx, [rsp+190h+var_128]
0x180009f90  mov     [rbp+90h+var_110], rdx
0x180009f94  lea     rdx, [rbp+90h+var_110]
0x180009f98  lea     rcx, [rbp+90h+hstringHeader]
0x180009f9c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180009fa1  nop
0x180009fa2  lea     r8d, [rsi+2]
0x180009fa6  mov     rdx, [rax+18h]
0x180009faa  mov     rcx, rdi
0x180009fad  mov     rax, rbx
0x180009fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fb5  mov     ebx, eax
0x180009fb7  mov     rcx, [rbp+98h]; this
0x180009fbe  test    eax, eax
0x180009fc0  jns     short loc_180009FD7
0x180009fc2  mov     r9d, eax; char *
0x180009fc5  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x180009fcc  mov     edx, 117h; void *
0x180009fd1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009fd6  nop
0x180009fd7  jmp     short loc_18000A00A
0x180009fd9  call    cs:__imp_GetLastError
0x180009fdf  mov     ebx, eax
0x180009fe1  test    eax, eax
0x180009fe3  jle     short loc_180009FEE
0x180009fe5  movzx   ebx, ax
0x180009fe8  or      ebx, 80070000h
0x180009fee  mov     rcx, [rbp+98h]; this
0x180009ff5  mov     r9d, ebx; char *
0x180009ff8  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\oobes"...
0x180009fff  mov     edx, 11Ch; void *
0x18000a004  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000a009  nop
0x18000a00a  lea     rcx, [rsp+190h+var_128]
0x18000a00f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000a014  nop
0x18000a015  test    r14, r14
0x18000a018  jz      short loc_18000A023
0x18000a01a  mov     rcx, r14; Block
0x18000a01d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a022  nop
0x18000a023  lea     rcx, [rsp+190h+Data]
0x18000a028  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000a02d  test    ebx, ebx
0x18000a02f  js      loc_180009DE7
0x18000a035  mov     cl, 1
0x18000a037  jmp     loc_180009DE9
0x18000a03c  movq    rdi, xmm1
0x18000a041  psrldq  xmm2, 8
0x18000a046  movq    rax, xmm2
0x18000a04b  test    dl, dl
0x18000a04d  cmovnz  rdi, rax
0x18000a051  mov     r9, rdi
0x18000a054  movdqa  xmm0, xmm7
0x18000a058  psrldq  xmm0, 8
0x18000a05d  movq    r14, xmm0
0x18000a062  mov     r8, r14
0x18000a065  lea     rdx, aProtectpcTaskS_2; "ProtectPC Task - setting %s value to (%"...
0x18000a06c  xor     ecx, ecx
0x18000a06e  call    UnattendLogW
0x18000a073  mov     r9, rdi; unsigned __int16 *
0x18000a076  mov     r8, r14; unsigned __int16 *
0x18000a079  movq    rdx, xmm7; unsigned __int16 *
0x18000a07e  mov     rcx, rsi; HKEY
0x18000a081  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000a086  mov     ebx, eax
0x18000a088  test    eax, eax
  ... truncated ...
```
