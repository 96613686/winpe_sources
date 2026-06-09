# Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::AddRedirectedOrGroupPolicyValues(void)

- ea: `0x18011535c`
- end: `0x1801158e4`
- name: `?AddRedirectedOrGroupPolicyValues@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ`
- size: `1416`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180116280`

## callees

- `0x180019000`
- `0x180019024`
- `0x1800e691c`
- `0x1800e7124`
- `0x1800e7bac`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ee898`
- `0x18010450c`
- `0x180115044`
- `0x18011535c`
- `0x1801166a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801155fb`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801155fb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18011568d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18011568d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801154b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801154b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180115476`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180115476`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180115514`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801155af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801156e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180115514`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801155af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801156e1`
- `DMCmnUtils!OmaDmRegistryRetrieveCurrentUsersHKCU` at `0x1801153ac`
- `DMCmnUtils!OmaDmRegistryRetrieveCurrentUsersHKCU` at `0x1801153ac`

## string_xrefs

- `0x1801155cd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x180115705`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x180115793`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x1801153ce`: `Impersonation Failure`

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
    if ( (byte_1802668C1 & 0x40) == 0 )
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
    if ( (byte_1802668C1 & 0x40) == 0 )
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
0x18011535c  mov     [rsp+arg_8], rbx
0x180115361  mov     [rsp+arg_10], rsi
0x180115366  push    rdi
0x180115367  push    r12
0x180115369  push    r13
0x18011536b  push    r14
0x18011536d  push    r15
0x18011536f  sub     rsp, 290h
0x180115376  mov     rax, cs:__security_cookie
0x18011537d  xor     rax, rsp
0x180115380  mov     [rsp+2B8h+var_38], rax
0x180115388  mov     r14, rcx
0x18011538b  xor     ebx, ebx
0x18011538d  mov     [rsp+2B8h+var_268], rbx
0x180115392  mov     r13b, bl
0x180115395  cmp     [rcx+83Ch], ebx
0x18011539b  jz      short loc_1801153E3
0x18011539d  mov     [rsp+2B8h+var_268], rbx
0x1801153a2  lea     rdx, [rsp+2B8h+var_268]
0x1801153a7  mov     ecx, 20019h
0x1801153ac  call    cs:__imp_?OmaDmRegistryRetrieveCurrentUsersHKCU@@YAJKPEAPEAUHKEY__@@@Z; OmaDmRegistryRetrieveCurrentUsersHKCU(ulong,HKEY__ * *)
0x1801153b2  test    eax, eax
0x1801153b4  js      short loc_1801153C2
0x1801153b6  mov     r13b, 1
0x1801153b9  mov     rsi, 0FFFFFFFF80000001h
0x1801153c0  jmp     short loc_1801153EA
0x1801153c2  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1801153c9  jz      short loc_1801153B9
0x1801153cb  mov     r9d, eax
0x1801153ce  lea     r8, aImpersonationF; "Impersonation Failure"
0x1801153d5  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsGetDiagnosticsDataFailure
0x1801153dc  call    McTemplateU0zd_EventWriteTransfer
0x1801153e1  jmp     short loc_1801153B9
0x1801153e3  mov     rsi, 0FFFFFFFF80000002h
0x1801153ea  mov     [rsp+2B8h+hKey], rbx
0x1801153ef  cmp     [r14+834h], ebx
0x1801153f6  jz      short loc_180115409
0x1801153f8  cmp     [r14+838h], ebx
0x1801153ff  mov     [rsp+2B8h+var_278], 1
0x180115407  jnz     short loc_18011540D
0x180115409  mov     [rsp+2B8h+var_278], ebx
0x18011540d  xorps   xmm0, xmm0
0x180115410  movdqu  xmmword ptr [rsp+2B8h+var_258], xmm0
0x180115416  mov     ecx, 428h; Size
0x18011541b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180115420  mov     rdi, rax
0x180115423  mov     dword ptr [rax+8], 1
0x18011542a  mov     dword ptr [rax+0Ch], 1
0x180115431  lea     rax, ??_7?$_Ref_count_obj2@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::`vftable'
0x180115438  mov     [rdi], rax
0x18011543b  lea     r12, [rdi+10h]
0x18011543f  mov     [r12+410h], rbx
0x180115447  mov     [r12], bx
0x18011544c  mov     [r12+208h], bx
0x180115455  mov     [rsp+2B8h+var_258], r12
0x18011545a  mov     [rsp+2B8h+var_258+8], rdi
0x18011545f  mov     r15, [rsp+2B8h+hKey]
0x180115464  test    r15, r15
0x180115467  jz      short loc_180115486
0x180115469  lea     rcx, [rsp+2B8h+var_288]; this
0x18011546e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180115473  mov     rcx, r15; hKey
0x180115476  call    cs:__imp_RegCloseKey
0x18011547c  lea     rcx, [rsp+2B8h+var_288]; this
0x180115481  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180115486  mov     [rsp+2B8h+hKey], rbx
0x18011548b  lea     r15, [r14+620h]
0x180115492  test    r13b, r13b
0x180115495  cmovnz  rsi, [rsp+2B8h+var_268]
0x18011549b  lea     rax, [rsp+2B8h+hKey]
0x1801154a0  mov     [rsp+2B8h+phkResult], rax; phkResult
0x1801154a5  mov     r9d, 20019h; samDesired
0x1801154ab  xor     r8d, r8d; ulOptions
0x1801154ae  mov     rdx, r15; lpSubKey
0x1801154b1  mov     rcx, rsi; hKey
0x1801154b4  call    cs:__imp_RegOpenKeyExW
0x1801154ba  mov     esi, eax
0x1801154bc  mov     r13d, 80070000h
0x1801154c2  test    eax, eax
0x1801154c4  jle     short loc_1801154CC
0x1801154c6  movzx   esi, ax
0x1801154c9  or      esi, r13d
0x1801154cc  test    esi, esi
0x1801154ce  jns     short loc_1801154E2
0x1801154d0  test    cs:byte_1802668C1, 40h
0x1801154d7  jz      short loc_180115546
0x1801154d9  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsOpeningRedirectedRegKeyFailure
0x1801154e0  jmp     short loc_18011553A
0x1801154e2  mov     [rsp+2B8h+Type], ebx
0x1801154e6  mov     [rsp+2B8h+cbData], 104h
0x1801154ee  lea     r15, [r14+418h]
0x1801154f5  lea     rax, [rsp+2B8h+cbData]
0x1801154fa  mov     [rsp+2B8h+lpcbData], rax; lpcbData
0x1801154ff  mov     [rsp+2B8h+phkResult], rbx; lpData
0x180115504  lea     r9, [rsp+2B8h+Type]; lpType
0x180115509  xor     r8d, r8d; lpReserved
0x18011550c  mov     rdx, r15; lpValueName
0x18011550f  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180115514  call    cs:__imp_RegQueryValueExW
0x18011551a  mov     esi, eax
0x18011551c  test    eax, eax
0x18011551e  jle     short loc_180115526
0x180115520  movzx   esi, ax
0x180115523  or      esi, r13d
0x180115526  test    esi, esi
0x180115528  jns     short loc_18011555C
0x18011552a  test    cs:byte_1802668C1, 40h
0x180115531  jz      short loc_180115546
0x180115533  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsOpeningRedirectedRegValueFailure
0x18011553a  mov     r8, r15
0x18011553d  mov     r9d, esi
0x180115540  call    McTemplateU0zd_EventWriteTransfer
0x180115545  nop
0x180115546  test    rdi, rdi
0x180115549  jz      loc_180115875
0x18011554f  mov     rcx, rdi; this
0x180115552  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180115557  jmp     loc_180115875
0x18011555c  mov     ecx, [rsp+2B8h+Type]
0x180115560  lea     eax, [rcx-1]
0x180115563  cmp     eax, 1
0x180115566  jbe     loc_180115675
0x18011556c  cmp     ecx, 7
0x18011556f  jz      loc_180115675
0x180115575  cmp     ecx, 4
0x180115578  jnz     loc_180115644
0x18011557e  mov     dword ptr [rsp+2B8h+Data], ebx
0x180115582  mov     [rsp+2B8h+var_288], ecx
0x180115586  mov     [rsp+2B8h+var_248], bx
0x18011558b  lea     rax, [rsp+2B8h+var_288]
0x180115590  mov     [rsp+2B8h+lpcbData], rax; lpcbData
0x180115595  lea     rax, [rsp+2B8h+Data]
0x18011559a  mov     [rsp+2B8h+phkResult], rax; int
0x18011559f  lea     r9, [rsp+2B8h+Type]; lpType
0x1801155a4  xor     r8d, r8d; lpReserved
0x1801155a7  mov     rdx, r15; lpValueName
0x1801155aa  mov     rcx, [rsp+2B8h+hKey]; hKey
0x1801155af  call    cs:__imp_RegQueryValueExW
0x1801155b5  mov     esi, eax
0x1801155b7  test    eax, eax
0x1801155b9  jle     short loc_1801155C1
0x1801155bb  movzx   esi, ax
0x1801155be  or      esi, r13d
0x1801155c1  test    esi, esi
0x1801155c3  jns     short loc_1801155E6
0x1801155c5  mov     edx, 18Ah; void *
0x1801155ca  mov     r9d, esi; char *
0x1801155cd  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801155d4  mov     rcx, [rsp+2B8h]; this
0x1801155dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801155e1  jmp     loc_180115546
0x1801155e6  mov     r9d, 0Ah
0x1801155ec  mov     r8d, 104h
0x1801155f2  lea     rdx, [rsp+2B8h+var_248]
0x1801155f7  mov     ecx, dword ptr [rsp+2B8h+Data]
0x1801155fb  call    cs:__imp__o__itow_s
0x180115601  mov     esi, eax
0x180115603  test    eax, eax
0x180115605  jle     short loc_18011560D
0x180115607  movzx   esi, ax
0x18011560a  or      esi, r13d
0x18011560d  test    esi, esi
0x18011560f  jns     short loc_180115618
0x180115611  mov     edx, 18Ch
0x180115616  jmp     short loc_1801155CA
0x180115618  lea     r8, [r14+210h]; unsigned __int16 *
0x18011561f  lea     rdx, [r14+8]; unsigned __int16 *
0x180115623  lea     r9, [rsp+2B8h+var_248]; unsigned __int16 *
0x180115628  mov     rcx, r12; this
0x18011562b  call    ?SaveRedirectedValue@RedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBG00@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies::SaveRedirectedValue(ushort const *,ushort const *,ushort const *)
0x180115630  mov     esi, eax
0x180115632  test    eax, eax
0x180115634  jns     loc_1801157BE
0x18011563a  mov     r9d, eax
0x18011563d  mov     edx, 18Dh
0x180115642  jmp     short loc_1801155CD
0x180115644  lea     r8, [r14+210h]; unsigned __int16 *
0x18011564b  lea     rdx, [r14+8]; unsigned __int16 *
0x18011564f  lea     r9, aUnknown_0; "(Unknown)"
0x180115656  mov     rcx, r12; this
0x180115659  call    ?SaveRedirectedValue@RedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBG00@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies::SaveRedirectedValue(ushort const *,ushort const *,ushort const *)
0x18011565e  mov     esi, eax
0x180115660  test    eax, eax
0x180115662  jns     loc_1801157BE
0x180115668  mov     r9d, eax
0x18011566b  mov     edx, 191h
0x180115670  jmp     loc_1801155CD
0x180115675  mov     esi, [rsp+2B8h+cbData]
0x180115679  cmp     esi, 2
0x18011567c  jnb     short loc_180115687
0x18011567e  mov     esi, 2
0x180115683  mov     [rsp+2B8h+cbData], esi
0x180115687  shr     esi, 1
0x180115689  mov     edx, esi; ui
0x18011568b  xor     ecx, ecx; strIn
0x18011568d  call    cs:__imp_SysAllocStringLen
0x180115693  mov     r12, rax
0x180115696  mov     qword ptr [rsp+2B8h+var_288], rax
0x18011569b  test    rax, rax
0x18011569e  jnz     short loc_1801156C2
0x1801156a0  lea     rcx, [rsp+2B8h+var_288]
0x1801156a5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801156aa  nop
0x1801156ab  test    rdi, rdi
0x1801156ae  jz      short loc_1801156B8
0x1801156b0  mov     rcx, rdi; this
0x1801156b3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801156b8  mov     esi, 8007000Eh
0x1801156bd  jmp     loc_180115875
0x1801156c2  lea     rax, [rsp+2B8h+cbData]
0x1801156c7  mov     [rsp+2B8h+lpcbData], rax; lpcbData
0x1801156cc  mov     [rsp+2B8h+phkResult], r12; int
0x1801156d1  lea     r9, [rsp+2B8h+Type]; lpType
0x1801156d6  xor     r8d, r8d; lpReserved
0x1801156d9  mov     rdx, r15; lpValueName
0x1801156dc  mov     rcx, [rsp+2B8h+hKey]; hKey
0x1801156e1  call    cs:__imp_RegQueryValueExW
0x1801156e7  mov     r15d, eax
0x1801156ea  test    eax, eax
0x1801156ec  jle     short loc_1801156F5
0x1801156ee  movzx   r15d, ax
0x1801156f2  or      r15d, r13d
0x1801156f5  test    r15d, r15d
0x1801156f8  jns     short loc_180115736
0x1801156fa  mov     rcx, [rsp+2B8h]; this
0x180115702  mov     r9d, r15d; char *
0x180115705  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011570c  mov     edx, 169h; void *
0x180115711  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115716  lea     rcx, [rsp+2B8h+var_288]
0x18011571b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180115720  nop
0x180115721  test    rdi, rdi
0x180115724  jz      short loc_18011572E
0x180115726  mov     rcx, rdi; this
0x180115729  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011572e  mov     esi, r15d
0x180115731  jmp     loc_180115875
0x180115736  lea     eax, [rsi-1]
0x180115739  mov     [r12+rax*2], bx
0x18011573e  cmp     [rsp+2B8h+Type], 7
0x180115743  jnz     short loc_18011576B
0x180115745  cmp     esi, 2
0x180115748  jbe     short loc_18011576B
0x18011574a  lea     ecx, [rsi-2]
0x18011574d  mov     rax, rbx
0x180115750  test    rcx, rcx
0x180115753  jz      short loc_18011576B
0x180115755  cmp     [r12+rax*2], bx
0x18011575a  jnz     short loc_180115763
0x18011575c  mov     word ptr [r12+rax*2], 3Bh ; ';'
0x180115763  inc     rax
0x180115766  cmp     rax, rcx
0x180115769  jb      short loc_180115755
0x18011576b  lea     r8, [r14+210h]; unsigned __int16 *
0x180115772  lea     rdx, [r14+8]; unsigned __int16 *
0x180115776  mov     r9, r12; unsigned __int16 *
0x180115779  lea     rcx, [rdi+10h]; this
0x18011577d  call    ?SaveRedirectedValue@RedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBG00@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies::SaveRedirectedValue(ushort const *,ushort const *,ushort const *)
0x180115782  mov     esi, eax
0x180115784  test    eax, eax
0x180115786  jns     short loc_1801157B3
0x180115788  mov     rcx, [rsp+2B8h]; this
0x180115790  mov     r9d, eax; char *
0x180115793  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011579a  mov     edx, 17Ah; void *
0x18011579f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801157a4  lea     rcx, [rsp+2B8h+var_288]
0x1801157a9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801157ae  jmp     loc_180115546
0x1801157b3  lea     rcx, [rsp+2B8h+var_288]
0x1801157b8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801157bd  nop
0x1801157be  cmp     [rsp+2B8h+var_278], ebx
0x1801157c2  jz      short loc_1801157FE
0x1801157c4  mov     rcx, [r14+868h]
0x1801157cb  cmp     rcx, [r14+870h]
0x1801157d2  jz      short loc_1801157E8
0x1801157d4  lea     rdx, [rsp+2B8h+var_258]
0x1801157d9  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x1801157de  add     qword ptr [r14+868h], 10h
0x1801157e6  jmp     short loc_18011583B
0x1801157e8  lea     r8, [rsp+2B8h+var_258]
0x1801157ed  mov     rdx, rcx
0x1801157f0  lea     rcx, [r14+860h]
0x1801157f7  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> const &>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> * const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> const &)
0x1801157fc  jmp     short loc_180115836
0x1801157fe  mov     rcx, [r14+850h]
0x180115805  cmp     rcx, [r14+858h]
0x18011580c  jz      short loc_180115822
0x18011580e  lea     rdx, [rsp+2B8h+var_258]
0x180115813  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180115818  add     qword ptr [r14+850h], 10h
0x180115820  jmp     short loc_18011583B
0x180115822  lea     r8, [rsp+2B8h+var_258]
0x180115827  mov     rdx, rcx
0x18011582a  lea     rcx, [r14+848h]
0x180115831  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> const &>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> * const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy> const &)
0x180115836  mov     rdi, [rsp+2B8h+var_258+8]
0x18011583b  test    rdi, rdi
  ... truncated ...
```
