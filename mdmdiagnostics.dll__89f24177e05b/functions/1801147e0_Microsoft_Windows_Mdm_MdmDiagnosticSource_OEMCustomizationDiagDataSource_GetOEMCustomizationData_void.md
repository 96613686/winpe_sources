# Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::GetOEMCustomizationData(void)

- ea: `0x1801147e0`
- end: `0x180114d83`
- name: `?GetOEMCustomizationData@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ`
- size: `1443`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180114750`

## callees

- `0x180019000`
- `0x180019514`
- `0x18001a0a0`
- `0x18001a634`
- `0x1800e7c08`
- `0x1800ece5c`
- `0x180104108`
- `0x180107e60`
- `0x18011461c`
- `0x180114660`
- `0x1801147e0`
- `0x180114e5c`
- `0x180114ea8`
- `0x180114f38`
- `0x180191010`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1801148a4`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1801148a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180114915`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180114a25`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180114915`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180114a25`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801149a3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801149a3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180114a90`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180114a90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011487e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801149d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011487e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801149d0`
- `policymanager!PolicyManager_GetPolicy` at `0x180114b28`
- `policymanager!PolicyManager_GetPolicy` at `0x180114b28`

## string_xrefs

- `0x180114826`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180114926`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180114c08`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180114c3a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180114c56`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180114c81`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180114ca9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180114ce1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180114d35`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x1801148be`: `\nFailed to collect OEM Customizations. Cannot open c_PolicyManagerFeatureTeamProviderKey. HResult:0x%08x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::GetOEMCustomizationData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  LSTATUS v5; // eax
  unsigned int v6; // eax
  WCHAR *v7; // r15
  DWORD v8; // r14d
  unsigned int v9; // eax
  unsigned int v10; // eax
  WCHAR *v11; // r12
  DWORD i; // esi
  unsigned int v13; // eax
  int v14; // eax
  int Policy; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  int v19; // eax
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  WCHAR *v26; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v27; // [rsp+68h] [rbp-98h] BYREF
  WCHAR *v28; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  DWORD cSubKeys; // [rsp+88h] [rbp-78h] BYREF
  DWORD cValues; // [rsp+8Ch] [rbp-74h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  DWORD cchName; // [rsp+98h] [rbp-68h] BYREF
  DWORD cchValueName; // [rsp+9Ch] [rbp-64h] BYREF
  _DWORD v37[4]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v38[32]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v2 = Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteStartElement(
         this,
         L"OEMCustomizations");
  v3 = v2;
  if ( v2 >= 0 )
  {
    if ( !(unsigned __int8)IsPolicyManager_GetPolicyPresent() )
    {
      wprintf(L"\nFailed to collect OEM Customizations. PolicyManager not supported!\n");
      return 2147942450LL;
    }
    hKey = 0;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\PolicyManager\\providers\\82965F5A-6C65-4B7A-8075-488FCCE07D4E\\default\\device",
           0,
           0x20019u,
           &hKey);
    v3 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      LODWORD(v26) = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v26, 0);
      if ( (_DWORD)v26 == 16 || (_DWORD)v26 == 10 )
        wprintf(
          L"\nFailed to collect OEM Customizations. Cannot open c_PolicyManagerFeatureTeamProviderKey. HResult:0x%08x\n",
          v3);
      goto LABEL_62;
    }
    cbMaxSubKeyLen = 0;
    cSubKeys = 0;
    v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v6 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x92,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\oemcustomizationdiagdata.cpp",
             (const char *)v6,
             phkResulta);
LABEL_62:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v3;
    }
    v7 = (WCHAR *)operator new[](saturated_mul(++cbMaxSubKeyLen, 2u));
    v26 = v7;
    v8 = 0;
LABEL_14:
    if ( v8 >= cSubKeys )
    {
      v19 = Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteEndElement(this);
      v3 = v19;
      if ( v19 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 112LL))(*((_QWORD *)this + 1));
        if ( (v3 & 0x80000000) == 0 )
        {
          v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 248LL))(*((_QWORD *)this + 1));
          if ( (v3 & 0x80000000) == 0 )
          {
            std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v26);
            v3 = 0;
            goto LABEL_62;
          }
          v22 = 87;
        }
        else
        {
          v22 = 86;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\oemcustomizationdiagdata.cpp",
          (const char *)v3,
          phkResulta);
        v20 = v3;
        v21 = 205;
      }
      else
      {
        v20 = (unsigned int)v19;
        v21 = 204;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\oemcustomizationdiagdata.cpp",
        (const char *)v20,
        phkResulta);
      goto LABEL_52;
    }
    cchName = cbMaxSubKeyLen;
    v9 = RegEnumKeyExW(hKey, v8, v7, &cchName, 0, 0, 0, 0);
    if ( v9 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x99,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\oemcustomizationdiagdata.cpp",
             (const char *)v9,
             phkResultb);
      goto LABEL_52;
    }
    v27 = 0;
    v10 = RegOpenKeyExW(hKey, v7, 0, 0x20019u, &v27);
    if ( v10 )
    {
      v18 = 157;
    }
    else
    {
      cValues = 0;
      cbMaxValueNameLen = 0;
      v10 = RegQueryInfoKeyW(v27, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
      if ( !v10 )
      {
        v11 = (WCHAR *)operator new[](saturated_mul(++cbMaxValueNameLen, 2u));
        v28 = v11;
        for ( i = 0; ; ++i )
        {
          if ( i >= cValues )
          {
            std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v28);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
            ++v8;
            goto LABEL_14;
          }
          cchValueName = cbMaxValueNameLen;
          v13 = RegEnumValueW(v27, i, v11, &cchValueName, 0, 0, 0, 0);
          if ( v13 )
            break;
          v14 = Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteStartElement(
                  this,
                  L"Customization");
          v3 = v14;
          if ( v14 < 0 )
          {
            v17 = 172;
            goto LABEL_44;
          }
          v14 = Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(
                  this,
                  L"Area",
                  v7);
          v3 = v14;
          if ( v14 < 0 )
          {
            v17 = 173;
            goto LABEL_44;
          }
          v14 = Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(
                  this,
                  L"Name",
                  v11);
          v3 = v14;
          if ( v14 < 0 )
          {
            v17 = 174;
            goto LABEL_44;
          }
          v14 = Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteStartElement(
                  this,
                  L"ProviderValues");
          v3 = v14;
          if ( v14 < 0 )
          {
            v17 = 175;
LABEL_44:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v17,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\oemcustomizationdiagdata.cpp",
              (const char *)(unsigned int)v14,
              phkResulta);
            goto LABEL_46;
          }
          v37[0] = 1;
          v37[1] = 2;
          v31 = 0;
          Policy = PolicyManager_GetPolicy(v7, v11, v37, &v31);
          v3 = Policy;
          if ( Policy < 0 )
          {
            v16 = 182;
            goto LABEL_39;
          }
          if ( *(_DWORD *)(v31 + 8) == 1 )
          {
            swprintf_s<32>(v38, L"%u", *(unsigned int *)(v31 + 16));
            Policy = Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(
                       this,
                       L"Current",
                       v38);
            v3 = Policy;
            if ( Policy < 0 )
            {
              v16 = 192;
              goto LABEL_39;
            }
          }
          else if ( *(_DWORD *)(v31 + 8) == 2 )
          {
            Policy = Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(
                       this,
                       L"Current",
                       *(const unsigned __int16 **)(v31 + 16));
            v3 = Policy;
            if ( Policy < 0 )
            {
              v16 = 187;
LABEL_39:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v16,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\oemcustomizationdiagdata.cpp",
                (const char *)(unsigned int)Policy,
                phkResulta);
              wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(&v31);
              goto LABEL_46;
            }
          }
          Policy = Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteEndElement(this);
          v3 = Policy;
          if ( Policy < 0 )
          {
            v16 = 198;
            goto LABEL_39;
          }
          Policy = Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteEndElement(this);
          v3 = Policy;
          if ( Policy < 0 )
          {
            v16 = 200;
            goto LABEL_39;
          }
          wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(&v31);
        }
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xAA,
               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\oemcustomizationdiagdata.cpp",
               (const char *)v13,
               phkResulta);
LABEL_46:
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v28);
        goto LABEL_50;
      }
      v18 = 162;
    }
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v18,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\oemcustomizationdiagdata.cpp",
           (const char *)v10,
           phkResulta);
LABEL_50:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
LABEL_52:
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v26);
    goto LABEL_62;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x75,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\oemcustomizationdiagdata.cpp",
    (const char *)(unsigned int)v2,
    phkResult);
  return v3;
}

```

## disassembly

```asm
0x1801147e0  push    rbp
0x1801147e2  push    rbx
0x1801147e3  push    rsi
0x1801147e4  push    rdi
0x1801147e5  push    r12
0x1801147e7  push    r13
0x1801147e9  push    r14
0x1801147eb  push    r15
0x1801147ed  lea     rbp, [rsp-8]
0x1801147f2  sub     rsp, 108h
0x1801147f9  mov     rax, cs:__security_cookie
0x180114800  xor     rax, rsp
0x180114803  mov     [rbp+40h+var_50], rax
0x180114807  mov     rdi, rcx
0x18011480a  lea     rdx, aOemcustomizati_0; "OEMCustomizations"
0x180114811  call    ?WriteStartElement@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteStartElement(ushort const *)
0x180114816  mov     ebx, eax
0x180114818  xor     r13d, r13d
0x18011481b  test    eax, eax
0x18011481d  jns     short loc_18011483B
0x18011481f  mov     rcx, [rbp+48h]; this
0x180114823  mov     r9d, eax; char *
0x180114826  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011482d  lea     edx, [r13+75h]; void *
0x180114831  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114836  jmp     loc_180114D61
0x18011483b  call    IsPolicyManager_GetPolicyPresent
0x180114840  test    al, al
0x180114842  jnz     short loc_18011485A
0x180114844  lea     rcx, aFailedToCollec; "\nFailed to collect OEM Customizations."...
0x18011484b  call    wprintf
0x180114850  mov     eax, 80070032h
0x180114855  jmp     loc_180114D63
0x18011485a  mov     [rbp+40h+hKey], r13
0x18011485e  lea     rax, [rbp+40h+hKey]
0x180114862  mov     [rsp+140h+phkResult], rax; phkResult
0x180114867  mov     r9d, 20019h; samDesired
0x18011486d  xor     r8d, r8d; ulOptions
0x180114870  lea     rdx, SubKey; "Software\\Microsoft\\PolicyManager\\pro"...
0x180114877  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18011487e  call    cs:__imp_RegOpenKeyExW
0x180114884  mov     ebx, eax
0x180114886  test    eax, eax
0x180114888  jz      short loc_1801148CF
0x18011488a  jle     short loc_180114895
0x18011488c  movzx   ebx, ax
0x18011488f  or      ebx, 80070000h
0x180114895  mov     dword ptr [rsp+140h+var_E0], r13d
0x18011489a  xor     r8d, r8d
0x18011489d  lea     rdx, [rsp+140h+var_E0]
0x1801148a2  xor     ecx, ecx
0x1801148a4  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1801148aa  cmp     dword ptr [rsp+140h+var_E0], 10h
0x1801148af  jz      short loc_1801148BC
0x1801148b1  cmp     dword ptr [rsp+140h+var_E0], 0Ah
0x1801148b6  jnz     loc_180114D58
0x1801148bc  mov     edx, ebx
0x1801148be  lea     rcx, aFailedToCollec_7; "\nFailed to collect OEM Customizations."...
0x1801148c5  call    wprintf
0x1801148ca  jmp     loc_180114D58
0x1801148cf  mov     [rsp+140h+cbMaxSubKeyLen], r13d
0x1801148d4  mov     [rbp+40h+cSubKeys], r13d
0x1801148d8  mov     [rsp+140h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1801148dd  mov     [rsp+140h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1801148e2  mov     [rsp+140h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1801148e7  mov     [rsp+140h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1801148ec  mov     [rsp+140h+lpcValues], r13; lpcValues
0x1801148f1  mov     [rsp+140h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1801148f6  lea     rax, [rsp+140h+cbMaxSubKeyLen]
0x1801148fb  mov     [rsp+140h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180114900  lea     rax, [rbp+40h+cSubKeys]
0x180114904  mov     [rsp+140h+phkResult], rax; int
0x180114909  xor     r9d, r9d; lpReserved
0x18011490c  xor     r8d, r8d; lpcchClass
0x18011490f  xor     edx, edx; lpClass
0x180114911  mov     rcx, [rbp+40h+hKey]; hKey
0x180114915  call    cs:__imp_RegQueryInfoKeyW
0x18011491b  test    eax, eax
0x18011491d  jz      short loc_18011493E
0x18011491f  mov     rcx, [rbp+48h]; this
0x180114923  mov     r9d, eax; char *
0x180114926  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011492d  mov     edx, 92h; void *
0x180114932  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180114937  mov     ebx, eax
0x180114939  jmp     loc_180114D58
0x18011493e  mov     eax, [rsp+140h+cbMaxSubKeyLen]
0x180114942  inc     eax
0x180114944  mov     [rsp+140h+cbMaxSubKeyLen], eax
0x180114948  mov     ecx, eax
0x18011494a  mov     eax, 2
0x18011494f  mul     rcx
0x180114952  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180114959  cmovb   rax, rbx
0x18011495d  mov     rcx, rax; unsigned __int64
0x180114960  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180114965  mov     r15, rax
0x180114968  mov     [rsp+140h+var_E0], rax
0x18011496d  mov     r14d, r13d
0x180114970  cmp     r14d, [rbp+40h+cSubKeys]
0x180114974  jnb     loc_180114CCB
0x18011497a  mov     ecx, [rsp+140h+cbMaxSubKeyLen]
0x18011497e  mov     [rbp+40h+cchName], ecx
0x180114981  mov     [rsp+140h+lpcValues], r13; lpftLastWriteTime
0x180114986  mov     [rsp+140h+lpcbMaxClassLen], r13; lpcchClass
0x18011498b  mov     [rsp+140h+lpcbMaxSubKeyLen], r13; lpClass
0x180114990  mov     [rsp+140h+phkResult], r13; unsigned int
0x180114995  lea     r9, [rbp+40h+cchName]; lpcchName
0x180114999  mov     r8, r15; lpName
0x18011499c  mov     edx, r14d; dwIndex
0x18011499f  mov     rcx, [rbp+40h+hKey]; hKey
0x1801149a3  call    cs:__imp_RegEnumKeyExW
0x1801149a9  test    eax, eax
0x1801149ab  jnz     loc_180114CA2
0x1801149b1  mov     [rsp+140h+var_D8], r13
0x1801149b6  lea     rax, [rsp+140h+var_D8]
0x1801149bb  mov     [rsp+140h+phkResult], rax; unsigned int
0x1801149c0  mov     r9d, 20019h; samDesired
0x1801149c6  xor     r8d, r8d; ulOptions
0x1801149c9  mov     rdx, r15; lpSubKey
0x1801149cc  mov     rcx, [rbp+40h+hKey]; hKey
0x1801149d0  call    cs:__imp_RegOpenKeyExW
0x1801149d6  test    eax, eax
0x1801149d8  jnz     loc_180114C7C
0x1801149de  mov     [rbp+40h+cValues], r13d
0x1801149e2  mov     [rsp+140h+cbMaxValueNameLen], r13d
0x1801149e7  mov     [rsp+140h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1801149ec  mov     [rsp+140h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1801149f1  mov     [rsp+140h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1801149f6  lea     rax, [rsp+140h+cbMaxValueNameLen]
0x1801149fb  mov     [rsp+140h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180114a00  lea     rax, [rbp+40h+cValues]
0x180114a04  mov     [rsp+140h+lpcValues], rax; lpcValues
0x180114a09  mov     [rsp+140h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180114a0e  mov     [rsp+140h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180114a13  mov     [rsp+140h+phkResult], r13; lpcSubKeys
0x180114a18  xor     r9d, r9d; lpReserved
0x180114a1b  xor     r8d, r8d; lpcchClass
0x180114a1e  xor     edx, edx; lpClass
0x180114a20  mov     rcx, [rsp+140h+var_D8]; hKey
0x180114a25  call    cs:__imp_RegQueryInfoKeyW
0x180114a2b  test    eax, eax
0x180114a2d  jnz     loc_180114C75
0x180114a33  mov     eax, [rsp+140h+cbMaxValueNameLen]
0x180114a37  inc     eax
0x180114a39  mov     [rsp+140h+cbMaxValueNameLen], eax
0x180114a3d  mov     ecx, eax
0x180114a3f  mov     eax, 2
0x180114a44  mul     rcx
0x180114a47  cmovb   rax, rbx
0x180114a4b  mov     rcx, rax; unsigned __int64
0x180114a4e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180114a53  mov     r12, rax
0x180114a56  mov     [rsp+140h+var_D0], rax
0x180114a5b  mov     esi, r13d
0x180114a5e  cmp     esi, [rbp+40h+cValues]
0x180114a61  jnb     loc_180114BC6
0x180114a67  mov     ecx, [rsp+140h+cbMaxValueNameLen]
0x180114a6b  mov     [rbp+40h+cchValueName], ecx
0x180114a6e  mov     [rsp+140h+lpcValues], r13; lpcbData
0x180114a73  mov     [rsp+140h+lpcbMaxClassLen], r13; lpData
0x180114a78  mov     [rsp+140h+lpcbMaxSubKeyLen], r13; lpType
0x180114a7d  mov     [rsp+140h+phkResult], r13; unsigned int
0x180114a82  lea     r9, [rbp+40h+cchValueName]; lpcchValueName
0x180114a86  mov     r8, r12; lpValueName
0x180114a89  mov     edx, esi; dwIndex
0x180114a8b  mov     rcx, [rsp+140h+var_D8]; hKey
0x180114a90  call    cs:__imp_RegEnumValueW
0x180114a96  test    eax, eax
0x180114a98  jnz     loc_180114C4F
0x180114a9e  lea     rdx, aCustomization; "Customization"
0x180114aa5  mov     rcx, rdi; this
0x180114aa8  call    ?WriteStartElement@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteStartElement(ushort const *)
0x180114aad  mov     ebx, eax
0x180114aaf  test    eax, eax
0x180114ab1  js      loc_180114C35
0x180114ab7  mov     r8, r15; unsigned __int16 *
0x180114aba  lea     rdx, aArea; "Area"
0x180114ac1  mov     rcx, rdi; this
0x180114ac4  call    ?WriteSingleLineData@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180114ac9  mov     ebx, eax
0x180114acb  test    eax, eax
0x180114acd  js      loc_180114C2E
0x180114ad3  mov     r8, r12; unsigned __int16 *
0x180114ad6  lea     rdx, aName; "Name"
0x180114add  mov     rcx, rdi; this
0x180114ae0  call    ?WriteSingleLineData@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180114ae5  mov     ebx, eax
0x180114ae7  test    eax, eax
0x180114ae9  js      loc_180114C27
0x180114aef  lea     rdx, aProvidervalues; "ProviderValues"
0x180114af6  mov     rcx, rdi; this
0x180114af9  call    ?WriteStartElement@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteStartElement(ushort const *)
0x180114afe  mov     ebx, eax
0x180114b00  test    eax, eax
0x180114b02  js      loc_180114C20
0x180114b08  mov     [rbp+40h+var_A0], 1
0x180114b0f  mov     [rbp+40h+var_9C], 2
0x180114b16  mov     [rbp+40h+var_C0], r13
0x180114b1a  lea     r9, [rbp+40h+var_C0]
0x180114b1e  lea     r8, [rbp+40h+var_A0]
0x180114b22  mov     rdx, r12
0x180114b25  mov     rcx, r15
0x180114b28  call    cs:__imp_PolicyManager_GetPolicy
0x180114b2e  mov     ebx, eax
0x180114b30  test    eax, eax
0x180114b32  js      loc_180114BFC
0x180114b38  mov     r8, [rbp+40h+var_C0]
0x180114b3c  mov     ecx, [r8+8]
0x180114b40  sub     ecx, 1
0x180114b43  jz      short loc_180114B6D
0x180114b45  cmp     ecx, 1
0x180114b48  jnz     short loc_180114B9A
0x180114b4a  mov     r8, [r8+10h]; unsigned __int16 *
0x180114b4e  lea     rdx, aCurrent; "Current"
0x180114b55  mov     rcx, rdi; this
0x180114b58  call    ?WriteSingleLineData@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180114b5d  mov     ebx, eax
0x180114b5f  test    eax, eax
0x180114b61  jns     short loc_180114B9A
0x180114b63  mov     edx, 0BBh
0x180114b68  jmp     loc_180114C01
0x180114b6d  mov     r8d, [r8+10h]
0x180114b71  lea     rdx, aU; "%u"
0x180114b78  lea     rcx, [rbp+40h+var_90]
0x180114b7c  call    ??$swprintf_s@$0CA@@@YAHAEAY0CA@GPEBGZZ; swprintf_s<32>(ushort (&)[32],ushort const *,...)
0x180114b81  lea     r8, [rbp+40h+var_90]; unsigned __int16 *
0x180114b85  lea     rdx, aCurrent; "Current"
0x180114b8c  mov     rcx, rdi; this
0x180114b8f  call    ?WriteSingleLineData@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180114b94  mov     ebx, eax
0x180114b96  test    eax, eax
0x180114b98  js      short loc_180114BF5
0x180114b9a  mov     rcx, rdi; this
0x180114b9d  call    ?WriteEndElement@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteEndElement(void)
0x180114ba2  mov     ebx, eax
0x180114ba4  test    eax, eax
0x180114ba6  js      short loc_180114BEE
0x180114ba8  mov     rcx, rdi; this
0x180114bab  call    ?WriteEndElement@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteEndElement(void)
0x180114bb0  mov     ebx, eax
0x180114bb2  test    eax, eax
0x180114bb4  js      short loc_180114BE7
0x180114bb6  lea     rcx, [rbp+40h+var_C0]
0x180114bba  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x180114bbf  inc     esi
0x180114bc1  jmp     loc_180114A5E
0x180114bc6  lea     rcx, [rsp+140h+var_D0]
0x180114bcb  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180114bd0  nop
0x180114bd1  lea     rcx, [rsp+140h+var_D8]
0x180114bd6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180114bdb  inc     r14d
0x180114bde  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180114be2  jmp     loc_180114970
0x180114be7  mov     edx, 0C8h
0x180114bec  jmp     short loc_180114C01
0x180114bee  mov     edx, 0C6h
0x180114bf3  jmp     short loc_180114C01
0x180114bf5  mov     edx, 0C0h
0x180114bfa  jmp     short loc_180114C01
0x180114bfc  mov     edx, 0B6h; void *
0x180114c01  mov     rcx, [rbp+48h]; this
0x180114c05  mov     r9d, eax; char *
0x180114c08  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180114c0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114c14  nop
0x180114c15  lea     rcx, [rbp+40h+var_C0]
0x180114c19  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x180114c1e  jmp     short loc_180114C69
0x180114c20  mov     edx, 0AFh
0x180114c25  jmp     short loc_180114C3A
0x180114c27  mov     edx, 0AEh
0x180114c2c  jmp     short loc_180114C3A
0x180114c2e  mov     edx, 0ADh
0x180114c33  jmp     short loc_180114C3A
0x180114c35  mov     edx, 0ACh; void *
0x180114c3a  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180114c41  mov     r9d, eax; char *
0x180114c44  mov     rcx, [rbp+48h]; this
0x180114c48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114c4d  jmp     short loc_180114C69
0x180114c4f  mov     rcx, [rbp+48h]; this
0x180114c53  mov     r9d, eax; char *
0x180114c56  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180114c5d  mov     edx, 0AAh; void *
0x180114c62  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180114c67  mov     ebx, eax
0x180114c69  lea     rcx, [rsp+140h+var_D0]
0x180114c6e  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180114c73  jmp     short loc_180114C96
0x180114c75  mov     edx, 0A2h
0x180114c7a  jmp     short loc_180114C81
0x180114c7c  mov     edx, 9Dh; void *
0x180114c81  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180114c88  mov     r9d, eax; char *
0x180114c8b  mov     rcx, [rbp+48h]; this
0x180114c8f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180114c94  mov     ebx, eax
0x180114c96  lea     rcx, [rsp+140h+var_D8]
  ... truncated ...
```
