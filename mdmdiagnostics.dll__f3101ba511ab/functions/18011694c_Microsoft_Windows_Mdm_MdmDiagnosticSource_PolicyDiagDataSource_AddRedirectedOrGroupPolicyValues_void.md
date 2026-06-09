# Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::AddRedirectedOrGroupPolicyValues(void)

- ea: `0x18011694c`
- end: `0x180116f05`
- name: `?AddRedirectedOrGroupPolicyValues@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ`
- size: `1465`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180117900`

## callees

- `0x180019080`
- `0x1800190a4`
- `0x1800e6b14`
- `0x1800e734c`
- `0x1800e7d84`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800eef28`
- `0x180105744`
- `0x180116630`
- `0x18011694c`
- `0x180117d2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180116c09`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180116c09`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180116ca1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180116ca1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180116ab0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180116ab0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180116a6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180116a6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180116b16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180116bb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180116cfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180116b16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180116bb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180116cfb`
- `DMCmnUtils!OmaDmRegistryRetrieveCurrentUsersHKCU` at `0x18011699c`
- `DMCmnUtils!OmaDmRegistryRetrieveCurrentUsersHKCU` at `0x18011699c`

## string_xrefs

- `0x180116bdb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x180116d25`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x180116db3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x1801169c4`: `Impersonation Failure`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::AddRedirectedOrGroupPolicyValues(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *this)
{
  char v2; // r13
  int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // rsi
  bool v6; // zf
  std::_Ref_count_base *v7; // rdi
  Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies *v8; // r12
  HKEY v9; // r15
  char *v10; // r15
  LSTATUS v11; // eax
  __int64 v12; // rcx
  const char *v13; // r9
  signed int v14; // esi
  __int64 *v15; // rdx
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  int v20; // eax
  int v21; // eax
  int v22; // eax
  DWORD v23; // esi
  UINT v24; // esi
  BYTE *v25; // r12
  LSTATUS v26; // eax
  signed int v27; // r15d
  unsigned __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rcx
  const char *v31; // r9
  __int64 v32; // rcx
  int phkResult; // [rsp+20h] [rbp-298h]
  int phkResulta; // [rsp+20h] [rbp-298h]
  DWORD lpcbData[2]; // [rsp+30h] [rbp-288h] BYREF
  DWORD Type; // [rsp+38h] [rbp-280h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-27Ch] BYREF
  int v39; // [rsp+40h] [rbp-278h]
  HKEY hKey; // [rsp+48h] [rbp-270h] BYREF
  HKEY v41; // [rsp+50h] [rbp-268h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-260h] BYREF
  std::_Ref_count_base *v43[2]; // [rsp+60h] [rbp-258h] BYREF
  unsigned __int16 v44[264]; // [rsp+70h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  v41 = 0;
  v2 = 0;
  if ( *((_DWORD *)this + 527) )
  {
    v41 = 0;
    v3 = OmaDmRegistryRetrieveCurrentUsersHKCU(0x20019u, &v41);
    if ( v3 < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v4,
          EnterpriseDiagnosticsMdmDiagnosticsGetDiagnosticsDataFailure,
          L"Impersonation Failure",
          (unsigned int)v3);
    }
    else
    {
      v2 = 1;
    }
    v5 = -2147483647;
  }
  else
  {
    v5 = -2147483646;
  }
  hKey = 0;
  if ( !*((_DWORD *)this + 525) || (v6 = *((_DWORD *)this + 526) == 0, v39 = 1, v6) )
    v39 = 0;
  try
  {
    *(_OWORD *)v43 = 0;
    v7 = (std::_Ref_count_base *)operator new(0x428u);
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::`vftable';
    v8 = (std::_Ref_count_base *)((char *)v7 + 16);
    *((_QWORD *)v7 + 132) = 0;
    *((_WORD *)v7 + 8) = 0;
    *((_WORD *)v7 + 268) = 0;
    v43[0] = (std::_Ref_count_base *)((char *)v7 + 16);
    v43[1] = v7;
    v9 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)lpcbData);
      RegCloseKey(v9);
      wil::last_error_context::~last_error_context((wil::last_error_context *)lpcbData);
    }
    hKey = 0;
    v10 = (char *)this + 1568;
    if ( v2 )
      v5 = (__int64)v41;
    v11 = RegOpenKeyExW((HKEY)v5, (LPCWSTR)this + 784, 0, 0x20019u, &hKey);
    v14 = v11;
    if ( v11 > 0 )
      v14 = (unsigned __int16)v11 | 0x80070000;
  }
  catch ( ... )
  {
    lpcbData[0] = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x132,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
                    v13);
    if ( v43[1] )
      std::_Ref_count_base::_Decref(v43[1]);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
    return lpcbData[0];
  }
  if ( v14 < 0 )
  {
    if ( (byte_180268981 & 0x40) == 0 )
      goto LABEL_26;
    v15 = EnterpriseDiagnosticsMdmDiagnosticsOpeningRedirectedRegKeyFailure;
LABEL_25:
    McTemplateU0zd_EventWriteTransfer(v12, v15, v10, (unsigned int)v14);
    goto LABEL_26;
  }
  Type = 0;
  cbData = 260;
  v10 = (char *)this + 1048;
  v16 = RegQueryValueExW(hKey, (LPCWSTR)this + 524, 0, &Type, 0, &cbData);
  v14 = v16;
  if ( v16 > 0 )
    v14 = (unsigned __int16)v16 | 0x80070000;
  if ( v14 < 0 )
  {
    if ( (byte_180268981 & 0x40) == 0 )
      goto LABEL_26;
    v15 = EnterpriseDiagnosticsMdmDiagnosticsOpeningRedirectedRegValueFailure;
    goto LABEL_25;
  }
  if ( Type - 1 <= 1 || Type == 7 )
  {
    v23 = cbData;
    if ( cbData < 2 )
    {
      v23 = 2;
      cbData = 2;
    }
    v24 = v23 >> 1;
    v25 = (BYTE *)SysAllocStringLen(0, v24);
    *(_QWORD *)lpcbData = v25;
    if ( !v25 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpcbData);
      if ( v7 )
        std::_Ref_count_base::_Decref(v7);
      v14 = -2147024882;
      goto LABEL_80;
    }
    v26 = RegQueryValueExW(hKey, (LPCWSTR)this + 524, 0, &Type, v25, &cbData);
    v27 = v26;
    if ( v26 > 0 )
      v27 = (unsigned __int16)v26 | 0x80070000;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x169,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
        (const char *)(unsigned int)v27,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpcbData);
      if ( v7 )
        std::_Ref_count_base::_Decref(v7);
      v14 = v27;
      goto LABEL_80;
    }
    *(_WORD *)&v25[2 * v24 - 2] = 0;
    if ( Type == 7 && v24 > 2 )
    {
      v28 = 0;
      do
      {
        if ( !*(_WORD *)&v25[2 * v28] )
          *(_WORD *)&v25[2 * v28] = 59;
        ++v28;
      }
      while ( v28 < v24 - 2 );
    }
    v29 = Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies::SaveRedirectedValue(
            (std::_Ref_count_base *)((char *)v7 + 16),
            (const unsigned __int16 *)this + 4,
            (const unsigned __int16 *)this + 264,
            (const unsigned __int16 *)v25);
    v14 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
        (const char *)(unsigned int)v29,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpcbData);
LABEL_26:
      if ( v7 )
        std::_Ref_count_base::_Decref(v7);
LABEL_80:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
      return (unsigned int)v14;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpcbData);
  }
  else if ( Type == 4 )
  {
    *(_DWORD *)Data = 0;
    lpcbData[0] = 4;
    v44[0] = 0;
    v17 = RegQueryValueExW(hKey, (LPCWSTR)this + 524, 0, &Type, Data, lpcbData);
    v14 = v17;
    if ( v17 > 0 )
      v14 = (unsigned __int16)v17 | 0x80070000;
    if ( v14 < 0 )
    {
      v18 = 394;
LABEL_35:
      v19 = (unsigned int)v14;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
        (const char *)v19,
        phkResult);
      goto LABEL_26;
    }
    v20 = _o__itow_s(*(unsigned int *)Data, v44, 260, 10);
    v14 = v20;
    if ( v20 > 0 )
      v14 = (unsigned __int16)v20 | 0x80070000;
    if ( v14 < 0 )
    {
      v18 = 396;
      goto LABEL_35;
    }
    v21 = Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies::SaveRedirectedValue(
            v8,
            (const unsigned __int16 *)this + 4,
            (const unsigned __int16 *)this + 264,
            v44);
    v14 = v21;
    if ( v21 < 0 )
    {
      v19 = (unsigned int)v21;
      v18 = 397;
      goto LABEL_36;
    }
  }
  else
  {
    v22 = Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies::SaveRedirectedValue(
            v8,
            (const unsigned __int16 *)this + 4,
            (const unsigned __int16 *)this + 264,
            L"(Unknown)");
    v14 = v22;
    if ( v22 < 0 )
    {
      v19 = (unsigned int)v22;
      v18 = 401;
      goto LABEL_36;
    }
  }
  try
  {
    if ( v39 )
    {
      v30 = *((_QWORD *)this + 269);
      if ( v30 != *((_QWORD *)this + 270) )
      {
        std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
          v30,
          v43);
        *((_QWORD *)this + 269) += 16LL;
        goto LABEL_93;
      }
      std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> const &>(
        (char *)this + 2144,
        *((_QWORD *)this + 269),
        v43);
    }
    else
    {
      v32 = *((_QWORD *)this + 266);
      if ( v32 != *((_QWORD *)this + 267) )
      {
        std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
          v32,
          v43);
        *((_QWORD *)this + 266) += 16LL;
        goto LABEL_93;
      }
      std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> const &>(
        (char *)this + 2120,
        *((_QWORD *)this + 266),
        v43);
    }
    v7 = v43[1];
  }
  catch ( ... )
  {
    v39 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x19F,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
            v31);
    if ( v43[1] )
      std::_Ref_count_base::_Decref(v43[1]);
    v14 = v39;
    goto LABEL_80;
  }
LABEL_93:
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
  return 0;
}

```

## disassembly

```asm
0x18011694c  mov     [rsp+arg_8], rbx
0x180116951  mov     [rsp+arg_10], rsi
0x180116956  push    rdi
0x180116957  push    r12
0x180116959  push    r13
0x18011695b  push    r14
0x18011695d  push    r15
0x18011695f  sub     rsp, 290h
0x180116966  mov     rax, cs:__security_cookie
0x18011696d  xor     rax, rsp
0x180116970  mov     [rsp+2B8h+var_38], rax
0x180116978  mov     r14, rcx
0x18011697b  xor     ebx, ebx
0x18011697d  mov     [rsp+2B8h+var_268], rbx
0x180116982  mov     r13b, bl
0x180116985  cmp     [rcx+83Ch], ebx
0x18011698b  jz      short loc_1801169D9
0x18011698d  mov     [rsp+2B8h+var_268], rbx
0x180116992  lea     rdx, [rsp+2B8h+var_268]
0x180116997  mov     ecx, 20019h
0x18011699c  call    cs:__imp_?OmaDmRegistryRetrieveCurrentUsersHKCU@@YAJKPEAPEAUHKEY__@@@Z; OmaDmRegistryRetrieveCurrentUsersHKCU(ulong,HKEY__ * *)
0x1801169a3  nop     dword ptr [rax+rax+00h]
0x1801169a8  test    eax, eax
0x1801169aa  js      short loc_1801169B8
0x1801169ac  mov     r13b, 1
0x1801169af  mov     rsi, 0FFFFFFFF80000001h
0x1801169b6  jmp     short loc_1801169E0
0x1801169b8  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1801169bf  jz      short loc_1801169AF
0x1801169c1  mov     r9d, eax
0x1801169c4  lea     r8, aImpersonationF; "Impersonation Failure"
0x1801169cb  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsGetDiagnosticsDataFailure
0x1801169d2  call    McTemplateU0zd_EventWriteTransfer
0x1801169d7  jmp     short loc_1801169AF
0x1801169d9  mov     rsi, 0FFFFFFFF80000002h
0x1801169e0  mov     [rsp+2B8h+hKey], rbx
0x1801169e5  cmp     [r14+834h], ebx
0x1801169ec  jz      short loc_1801169FF
0x1801169ee  cmp     [r14+838h], ebx
0x1801169f5  mov     [rsp+2B8h+var_278], 1
0x1801169fd  jnz     short loc_180116A03
0x1801169ff  mov     [rsp+2B8h+var_278], ebx
0x180116a03  xorps   xmm0, xmm0
0x180116a06  movdqu  xmmword ptr [rsp+2B8h+var_258], xmm0
0x180116a0c  mov     ecx, 428h; Size
0x180116a11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180116a16  mov     rdi, rax
0x180116a19  mov     dword ptr [rax+8], 1
0x180116a20  mov     dword ptr [rax+0Ch], 1
0x180116a27  lea     rax, ??_7?$_Ref_count_obj2@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::`vftable'
0x180116a2e  mov     [rdi], rax
0x180116a31  lea     r12, [rdi+10h]
0x180116a35  mov     [r12+410h], rbx
0x180116a3d  mov     [r12], bx
0x180116a42  mov     [r12+208h], bx
0x180116a4b  mov     [rsp+2B8h+var_258], r12
0x180116a50  mov     [rsp+2B8h+var_258+8], rdi
0x180116a55  mov     r15, [rsp+2B8h+hKey]
0x180116a5a  test    r15, r15
0x180116a5d  jz      short loc_180116A82
0x180116a5f  lea     rcx, [rsp+2B8h+var_288]; this
0x180116a64  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180116a69  mov     rcx, r15; hKey
0x180116a6c  call    cs:__imp_RegCloseKey
0x180116a73  nop     dword ptr [rax+rax+00h]
0x180116a78  lea     rcx, [rsp+2B8h+var_288]; this
0x180116a7d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180116a82  mov     [rsp+2B8h+hKey], rbx
0x180116a87  lea     r15, [r14+620h]
0x180116a8e  test    r13b, r13b
0x180116a91  cmovnz  rsi, [rsp+2B8h+var_268]
0x180116a97  lea     rax, [rsp+2B8h+hKey]
0x180116a9c  mov     [rsp+2B8h+phkResult], rax; phkResult
0x180116aa1  mov     r9d, 20019h; samDesired
0x180116aa7  xor     r8d, r8d; ulOptions
0x180116aaa  mov     rdx, r15; lpSubKey
0x180116aad  mov     rcx, rsi; hKey
0x180116ab0  call    cs:__imp_RegOpenKeyExW
0x180116ab7  nop     dword ptr [rax+rax+00h]
0x180116abc  mov     esi, eax
0x180116abe  mov     r13d, 80070000h
0x180116ac4  test    eax, eax
0x180116ac6  jle     short loc_180116ACE
0x180116ac8  movzx   esi, ax
0x180116acb  or      esi, r13d
0x180116ace  test    esi, esi
0x180116ad0  jns     short loc_180116AE4
0x180116ad2  test    cs:byte_180268981, 40h
0x180116ad9  jz      short loc_180116B4E
0x180116adb  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsOpeningRedirectedRegKeyFailure
0x180116ae2  jmp     short loc_180116B42
0x180116ae4  mov     [rsp+2B8h+Type], ebx
0x180116ae8  mov     [rsp+2B8h+cbData], 104h
0x180116af0  lea     r15, [r14+418h]
0x180116af7  lea     rax, [rsp+2B8h+cbData]
0x180116afc  mov     [rsp+2B8h+lpcbData], rax; lpcbData
0x180116b01  mov     [rsp+2B8h+phkResult], rbx; lpData
0x180116b06  lea     r9, [rsp+2B8h+Type]; lpType
0x180116b0b  xor     r8d, r8d; lpReserved
0x180116b0e  mov     rdx, r15; lpValueName
0x180116b11  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180116b16  call    cs:__imp_RegQueryValueExW
0x180116b1d  nop     dword ptr [rax+rax+00h]
0x180116b22  mov     esi, eax
0x180116b24  test    eax, eax
0x180116b26  jle     short loc_180116B2E
0x180116b28  movzx   esi, ax
0x180116b2b  or      esi, r13d
0x180116b2e  test    esi, esi
0x180116b30  jns     short loc_180116B64
0x180116b32  test    cs:byte_180268981, 40h
0x180116b39  jz      short loc_180116B4E
0x180116b3b  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsOpeningRedirectedRegValueFailure
0x180116b42  mov     r8, r15
0x180116b45  mov     r9d, esi
0x180116b48  call    McTemplateU0zd_EventWriteTransfer
0x180116b4d  nop
0x180116b4e  test    rdi, rdi
0x180116b51  jz      loc_180116E95
0x180116b57  mov     rcx, rdi; this
0x180116b5a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180116b5f  jmp     loc_180116E95
0x180116b64  mov     ecx, [rsp+2B8h+Type]
0x180116b68  lea     eax, [rcx-1]
0x180116b6b  cmp     eax, 1
0x180116b6e  jbe     loc_180116C89
0x180116b74  cmp     ecx, 7
0x180116b77  jz      loc_180116C89
0x180116b7d  cmp     ecx, 4
0x180116b80  jnz     loc_180116C58
0x180116b86  mov     dword ptr [rsp+2B8h+Data], ebx
0x180116b8a  mov     [rsp+2B8h+var_288], ecx
0x180116b8e  mov     [rsp+2B8h+var_248], bx
0x180116b93  lea     rax, [rsp+2B8h+var_288]
0x180116b98  mov     [rsp+2B8h+lpcbData], rax; lpcbData
0x180116b9d  lea     rax, [rsp+2B8h+Data]
0x180116ba2  mov     [rsp+2B8h+phkResult], rax; int
0x180116ba7  lea     r9, [rsp+2B8h+Type]; lpType
0x180116bac  xor     r8d, r8d; lpReserved
0x180116baf  mov     rdx, r15; lpValueName
0x180116bb2  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180116bb7  call    cs:__imp_RegQueryValueExW
0x180116bbe  nop     dword ptr [rax+rax+00h]
0x180116bc3  mov     esi, eax
0x180116bc5  test    eax, eax
0x180116bc7  jle     short loc_180116BCF
0x180116bc9  movzx   esi, ax
0x180116bcc  or      esi, r13d
0x180116bcf  test    esi, esi
0x180116bd1  jns     short loc_180116BF4
0x180116bd3  mov     edx, 18Ah; void *
0x180116bd8  mov     r9d, esi; char *
0x180116bdb  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180116be2  mov     rcx, [rsp+2B8h]; this
0x180116bea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116bef  jmp     loc_180116B4E
0x180116bf4  mov     r9d, 0Ah
0x180116bfa  mov     r8d, 104h
0x180116c00  lea     rdx, [rsp+2B8h+var_248]
0x180116c05  mov     ecx, dword ptr [rsp+2B8h+Data]
0x180116c09  call    cs:__imp__o__itow_s
0x180116c10  nop     dword ptr [rax+rax+00h]
0x180116c15  mov     esi, eax
0x180116c17  test    eax, eax
0x180116c19  jle     short loc_180116C21
0x180116c1b  movzx   esi, ax
0x180116c1e  or      esi, r13d
0x180116c21  test    esi, esi
0x180116c23  jns     short loc_180116C2C
0x180116c25  mov     edx, 18Ch
0x180116c2a  jmp     short loc_180116BD8
0x180116c2c  lea     r8, [r14+210h]; unsigned __int16 *
0x180116c33  lea     rdx, [r14+8]; unsigned __int16 *
0x180116c37  lea     r9, [rsp+2B8h+var_248]; unsigned __int16 *
0x180116c3c  mov     rcx, r12; this
0x180116c3f  call    ?SaveRedirectedValue@RedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBG00@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies::SaveRedirectedValue(ushort const *,ushort const *,ushort const *)
0x180116c44  mov     esi, eax
0x180116c46  test    eax, eax
0x180116c48  jns     loc_180116DDE
0x180116c4e  mov     r9d, eax
0x180116c51  mov     edx, 18Dh
0x180116c56  jmp     short loc_180116BDB
0x180116c58  lea     r8, [r14+210h]; unsigned __int16 *
0x180116c5f  lea     rdx, [r14+8]; unsigned __int16 *
0x180116c63  lea     r9, aUnknown_0; "(Unknown)"
0x180116c6a  mov     rcx, r12; this
0x180116c6d  call    ?SaveRedirectedValue@RedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBG00@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies::SaveRedirectedValue(ushort const *,ushort const *,ushort const *)
0x180116c72  mov     esi, eax
0x180116c74  test    eax, eax
0x180116c76  jns     loc_180116DDE
0x180116c7c  mov     r9d, eax
0x180116c7f  mov     edx, 191h
0x180116c84  jmp     loc_180116BDB
0x180116c89  mov     esi, [rsp+2B8h+cbData]
0x180116c8d  cmp     esi, 2
0x180116c90  jnb     short loc_180116C9B
0x180116c92  mov     esi, 2
0x180116c97  mov     [rsp+2B8h+cbData], esi
0x180116c9b  shr     esi, 1
0x180116c9d  mov     edx, esi; ui
0x180116c9f  xor     ecx, ecx; strIn
0x180116ca1  call    cs:__imp_SysAllocStringLen
0x180116ca8  nop     dword ptr [rax+rax+00h]
0x180116cad  mov     r12, rax
0x180116cb0  mov     qword ptr [rsp+2B8h+var_288], rax
0x180116cb5  test    rax, rax
0x180116cb8  jnz     short loc_180116CDC
0x180116cba  lea     rcx, [rsp+2B8h+var_288]
0x180116cbf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180116cc4  nop
0x180116cc5  test    rdi, rdi
0x180116cc8  jz      short loc_180116CD2
0x180116cca  mov     rcx, rdi; this
0x180116ccd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180116cd2  mov     esi, 8007000Eh
0x180116cd7  jmp     loc_180116E95
0x180116cdc  lea     rax, [rsp+2B8h+cbData]
0x180116ce1  mov     [rsp+2B8h+lpcbData], rax; lpcbData
0x180116ce6  mov     [rsp+2B8h+phkResult], r12; int
0x180116ceb  lea     r9, [rsp+2B8h+Type]; lpType
0x180116cf0  xor     r8d, r8d; lpReserved
0x180116cf3  mov     rdx, r15; lpValueName
0x180116cf6  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180116cfb  call    cs:__imp_RegQueryValueExW
0x180116d02  nop     dword ptr [rax+rax+00h]
0x180116d07  mov     r15d, eax
0x180116d0a  test    eax, eax
0x180116d0c  jle     short loc_180116D15
0x180116d0e  movzx   r15d, ax
0x180116d12  or      r15d, r13d
0x180116d15  test    r15d, r15d
0x180116d18  jns     short loc_180116D56
0x180116d1a  mov     rcx, [rsp+2B8h]; this
0x180116d22  mov     r9d, r15d; char *
0x180116d25  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180116d2c  mov     edx, 169h; void *
0x180116d31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116d36  lea     rcx, [rsp+2B8h+var_288]
0x180116d3b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180116d40  nop
0x180116d41  test    rdi, rdi
0x180116d44  jz      short loc_180116D4E
0x180116d46  mov     rcx, rdi; this
0x180116d49  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180116d4e  mov     esi, r15d
0x180116d51  jmp     loc_180116E95
0x180116d56  lea     eax, [rsi-1]
0x180116d59  mov     [r12+rax*2], bx
0x180116d5e  cmp     [rsp+2B8h+Type], 7
0x180116d63  jnz     short loc_180116D8B
0x180116d65  cmp     esi, 2
0x180116d68  jbe     short loc_180116D8B
0x180116d6a  lea     ecx, [rsi-2]
0x180116d6d  mov     rax, rbx
0x180116d70  test    rcx, rcx
0x180116d73  jz      short loc_180116D8B
0x180116d75  cmp     [r12+rax*2], bx
0x180116d7a  jnz     short loc_180116D83
0x180116d7c  mov     word ptr [r12+rax*2], 3Bh ; ';'
0x180116d83  inc     rax
0x180116d86  cmp     rax, rcx
0x180116d89  jb      short loc_180116D75
0x180116d8b  lea     r8, [r14+210h]; unsigned __int16 *
0x180116d92  lea     rdx, [r14+8]; unsigned __int16 *
0x180116d96  mov     r9, r12; unsigned __int16 *
0x180116d99  lea     rcx, [rdi+10h]; this
0x180116d9d  call    ?SaveRedirectedValue@RedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBG00@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies::SaveRedirectedValue(ushort const *,ushort const *,ushort const *)
0x180116da2  mov     esi, eax
0x180116da4  test    eax, eax
0x180116da6  jns     short loc_180116DD3
0x180116da8  mov     rcx, [rsp+2B8h]; this
0x180116db0  mov     r9d, eax; char *
0x180116db3  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180116dba  mov     edx, 17Ah; void *
0x180116dbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116dc4  lea     rcx, [rsp+2B8h+var_288]
0x180116dc9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180116dce  jmp     loc_180116B4E
0x180116dd3  lea     rcx, [rsp+2B8h+var_288]
0x180116dd8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180116ddd  nop
0x180116dde  cmp     [rsp+2B8h+var_278], ebx
0x180116de2  jz      short loc_180116E1E
0x180116de4  mov     rcx, [r14+868h]
0x180116deb  cmp     rcx, [r14+870h]
0x180116df2  jz      short loc_180116E08
0x180116df4  lea     rdx, [rsp+2B8h+var_258]
0x180116df9  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180116dfe  add     qword ptr [r14+868h], 10h
0x180116e06  jmp     short loc_180116E5B
0x180116e08  lea     r8, [rsp+2B8h+var_258]
0x180116e0d  mov     rdx, rcx
0x180116e10  lea     rcx, [r14+860h]
0x180116e17  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> const &>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> * const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> const &)
0x180116e1c  jmp     short loc_180116E56
0x180116e1e  mov     rcx, [r14+850h]
0x180116e25  cmp     rcx, [r14+858h]
0x180116e2c  jz      short loc_180116E42
0x180116e2e  lea     rdx, [rsp+2B8h+var_258]
0x180116e33  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
  ... truncated ...
```
