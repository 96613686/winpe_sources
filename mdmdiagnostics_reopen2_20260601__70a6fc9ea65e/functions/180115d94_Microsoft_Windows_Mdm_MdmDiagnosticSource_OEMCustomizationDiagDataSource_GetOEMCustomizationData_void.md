# Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::GetOEMCustomizationData(void)

- ea: `0x180115d94`
- end: `0x180116368`
- name: `?GetOEMCustomizationData@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ`
- size: `1492`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180115d00`

## callees

- `0x180019080`
- `0x180019594`
- `0x18001a130`
- `0x18001a6c4`
- `0x1800e7de8`
- `0x1800ed46c`
- `0x180105294`
- `0x180109140`
- `0x180115bd0`
- `0x180115c14`
- `0x180115d94`
- `0x180116448`
- `0x180116494`
- `0x180116524`
- `0x180193010`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180115e5e`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180115e5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180115ed5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180115ff7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180115ed5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180115ff7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180115f69`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180115f69`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180116068`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180116068`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180115e32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180115f9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180115e32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180115f9c`
- `policymanager!PolicyManager_GetPolicy` at `0x180116106`
- `policymanager!PolicyManager_GetPolicy` at `0x180116106`

## string_xrefs

- `0x180115dda`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180115eec`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x1801161ec`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x18011621e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x18011623a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180116265`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x18011628d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x1801162c5`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180116319`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\oemcustomizationdiagdata.cpp`
- `0x180115e7e`: `\nFailed to collect OEM Customizations. Cannot open c_PolicyManagerFeatureTeamProviderKey. HResult:0x%08x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180115d94  push    rbp
0x180115d96  push    rbx
0x180115d97  push    rsi
0x180115d98  push    rdi
0x180115d99  push    r12
0x180115d9b  push    r13
0x180115d9d  push    r14
0x180115d9f  push    r15
0x180115da1  lea     rbp, [rsp-8]
0x180115da6  sub     rsp, 108h
0x180115dad  mov     rax, cs:__security_cookie
0x180115db4  xor     rax, rsp
0x180115db7  mov     [rbp+40h+var_50], rax
0x180115dbb  mov     rdi, rcx
0x180115dbe  lea     rdx, aOemcustomizati_0; "OEMCustomizations"
0x180115dc5  call    ?WriteStartElement@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteStartElement(ushort const *)
0x180115dca  mov     ebx, eax
0x180115dcc  xor     r13d, r13d
0x180115dcf  test    eax, eax
0x180115dd1  jns     short loc_180115DEF
0x180115dd3  mov     rcx, [rbp+48h]; this
0x180115dd7  mov     r9d, eax; char *
0x180115dda  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180115de1  lea     edx, [r13+75h]; void *
0x180115de5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115dea  jmp     loc_180116345
0x180115def  call    IsPolicyManager_GetPolicyPresent
0x180115df4  test    al, al
0x180115df6  jnz     short loc_180115E0E
0x180115df8  lea     rcx, aFailedToCollec; "\nFailed to collect OEM Customizations."...
0x180115dff  call    wprintf
0x180115e04  mov     eax, 80070032h
0x180115e09  jmp     loc_180116347
0x180115e0e  mov     [rbp+40h+hKey], r13
0x180115e12  lea     rax, [rbp+40h+hKey]
0x180115e16  mov     [rsp+140h+phkResult], rax; phkResult
0x180115e1b  mov     r9d, 20019h; samDesired
0x180115e21  xor     r8d, r8d; ulOptions
0x180115e24  lea     rdx, SubKey; "Software\\Microsoft\\PolicyManager\\pro"...
0x180115e2b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180115e32  call    cs:__imp_RegOpenKeyExW
0x180115e39  nop     dword ptr [rax+rax+00h]
0x180115e3e  mov     ebx, eax
0x180115e40  test    eax, eax
0x180115e42  jz      short loc_180115E8F
0x180115e44  jle     short loc_180115E4F
0x180115e46  movzx   ebx, ax
0x180115e49  or      ebx, 80070000h
0x180115e4f  mov     dword ptr [rsp+140h+var_E0], r13d
0x180115e54  xor     r8d, r8d
0x180115e57  lea     rdx, [rsp+140h+var_E0]
0x180115e5c  xor     ecx, ecx
0x180115e5e  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180115e65  nop     dword ptr [rax+rax+00h]
0x180115e6a  cmp     dword ptr [rsp+140h+var_E0], 10h
0x180115e6f  jz      short loc_180115E7C
0x180115e71  cmp     dword ptr [rsp+140h+var_E0], 0Ah
0x180115e76  jnz     loc_18011633C
0x180115e7c  mov     edx, ebx
0x180115e7e  lea     rcx, aFailedToCollec_7; "\nFailed to collect OEM Customizations."...
0x180115e85  call    wprintf
0x180115e8a  jmp     loc_18011633C
0x180115e8f  mov     [rsp+140h+cbMaxSubKeyLen], r13d
0x180115e94  mov     [rbp+40h+cSubKeys], r13d
0x180115e98  mov     [rsp+140h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180115e9d  mov     [rsp+140h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180115ea2  mov     [rsp+140h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180115ea7  mov     [rsp+140h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180115eac  mov     [rsp+140h+lpcValues], r13; lpcValues
0x180115eb1  mov     [rsp+140h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180115eb6  lea     rax, [rsp+140h+cbMaxSubKeyLen]
0x180115ebb  mov     [rsp+140h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180115ec0  lea     rax, [rbp+40h+cSubKeys]
0x180115ec4  mov     [rsp+140h+phkResult], rax; int
0x180115ec9  xor     r9d, r9d; lpReserved
0x180115ecc  xor     r8d, r8d; lpcchClass
0x180115ecf  xor     edx, edx; lpClass
0x180115ed1  mov     rcx, [rbp+40h+hKey]; hKey
0x180115ed5  call    cs:__imp_RegQueryInfoKeyW
0x180115edc  nop     dword ptr [rax+rax+00h]
0x180115ee1  test    eax, eax
0x180115ee3  jz      short loc_180115F04
0x180115ee5  mov     rcx, [rbp+48h]; this
0x180115ee9  mov     r9d, eax; char *
0x180115eec  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180115ef3  mov     edx, 92h; void *
0x180115ef8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180115efd  mov     ebx, eax
0x180115eff  jmp     loc_18011633C
0x180115f04  mov     eax, [rsp+140h+cbMaxSubKeyLen]
0x180115f08  inc     eax
0x180115f0a  mov     [rsp+140h+cbMaxSubKeyLen], eax
0x180115f0e  mov     ecx, eax
0x180115f10  mov     eax, 2
0x180115f15  mul     rcx
0x180115f18  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180115f1f  cmovb   rax, rbx
0x180115f23  mov     rcx, rax; unsigned __int64
0x180115f26  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180115f2b  mov     r15, rax
0x180115f2e  mov     [rsp+140h+var_E0], rax
0x180115f33  mov     r14d, r13d
0x180115f36  cmp     r14d, [rbp+40h+cSubKeys]
0x180115f3a  jnb     loc_1801162AF
0x180115f40  mov     ecx, [rsp+140h+cbMaxSubKeyLen]
0x180115f44  mov     [rbp+40h+cchName], ecx
0x180115f47  mov     [rsp+140h+lpcValues], r13; lpftLastWriteTime
0x180115f4c  mov     [rsp+140h+lpcbMaxClassLen], r13; lpcchClass
0x180115f51  mov     [rsp+140h+lpcbMaxSubKeyLen], r13; lpClass
0x180115f56  mov     [rsp+140h+phkResult], r13; unsigned int
0x180115f5b  lea     r9, [rbp+40h+cchName]; lpcchName
0x180115f5f  mov     r8, r15; lpName
0x180115f62  mov     edx, r14d; dwIndex
0x180115f65  mov     rcx, [rbp+40h+hKey]; hKey
0x180115f69  call    cs:__imp_RegEnumKeyExW
0x180115f70  nop     dword ptr [rax+rax+00h]
0x180115f75  test    eax, eax
0x180115f77  jnz     loc_180116286
0x180115f7d  mov     [rsp+140h+var_D8], r13
0x180115f82  lea     rax, [rsp+140h+var_D8]
0x180115f87  mov     [rsp+140h+phkResult], rax; unsigned int
0x180115f8c  mov     r9d, 20019h; samDesired
0x180115f92  xor     r8d, r8d; ulOptions
0x180115f95  mov     rdx, r15; lpSubKey
0x180115f98  mov     rcx, [rbp+40h+hKey]; hKey
0x180115f9c  call    cs:__imp_RegOpenKeyExW
0x180115fa3  nop     dword ptr [rax+rax+00h]
0x180115fa8  test    eax, eax
0x180115faa  jnz     loc_180116260
0x180115fb0  mov     [rbp+40h+cValues], r13d
0x180115fb4  mov     [rsp+140h+cbMaxValueNameLen], r13d
0x180115fb9  mov     [rsp+140h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180115fbe  mov     [rsp+140h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180115fc3  mov     [rsp+140h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180115fc8  lea     rax, [rsp+140h+cbMaxValueNameLen]
0x180115fcd  mov     [rsp+140h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180115fd2  lea     rax, [rbp+40h+cValues]
0x180115fd6  mov     [rsp+140h+lpcValues], rax; lpcValues
0x180115fdb  mov     [rsp+140h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180115fe0  mov     [rsp+140h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180115fe5  mov     [rsp+140h+phkResult], r13; lpcSubKeys
0x180115fea  xor     r9d, r9d; lpReserved
0x180115fed  xor     r8d, r8d; lpcchClass
0x180115ff0  xor     edx, edx; lpClass
0x180115ff2  mov     rcx, [rsp+140h+var_D8]; hKey
0x180115ff7  call    cs:__imp_RegQueryInfoKeyW
0x180115ffe  nop     dword ptr [rax+rax+00h]
0x180116003  test    eax, eax
0x180116005  jnz     loc_180116259
0x18011600b  mov     eax, [rsp+140h+cbMaxValueNameLen]
0x18011600f  inc     eax
0x180116011  mov     [rsp+140h+cbMaxValueNameLen], eax
0x180116015  mov     ecx, eax
0x180116017  mov     eax, 2
0x18011601c  mul     rcx
0x18011601f  cmovb   rax, rbx
0x180116023  mov     rcx, rax; unsigned __int64
0x180116026  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18011602b  mov     r12, rax
0x18011602e  mov     [rsp+140h+var_D0], rax
0x180116033  mov     esi, r13d
0x180116036  cmp     esi, [rbp+40h+cValues]
0x180116039  jnb     loc_1801161AA
0x18011603f  mov     ecx, [rsp+140h+cbMaxValueNameLen]
0x180116043  mov     [rbp+40h+cchValueName], ecx
0x180116046  mov     [rsp+140h+lpcValues], r13; lpcbData
0x18011604b  mov     [rsp+140h+lpcbMaxClassLen], r13; lpData
0x180116050  mov     [rsp+140h+lpcbMaxSubKeyLen], r13; lpType
0x180116055  mov     [rsp+140h+phkResult], r13; unsigned int
0x18011605a  lea     r9, [rbp+40h+cchValueName]; lpcchValueName
0x18011605e  mov     r8, r12; lpValueName
0x180116061  mov     edx, esi; dwIndex
0x180116063  mov     rcx, [rsp+140h+var_D8]; hKey
0x180116068  call    cs:__imp_RegEnumValueW
0x18011606f  nop     dword ptr [rax+rax+00h]
0x180116074  test    eax, eax
0x180116076  jnz     loc_180116233
0x18011607c  lea     rdx, aCustomization; "Customization"
0x180116083  mov     rcx, rdi; this
0x180116086  call    ?WriteStartElement@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteStartElement(ushort const *)
0x18011608b  mov     ebx, eax
0x18011608d  test    eax, eax
0x18011608f  js      loc_180116219
0x180116095  mov     r8, r15; unsigned __int16 *
0x180116098  lea     rdx, aArea; "Area"
0x18011609f  mov     rcx, rdi; this
0x1801160a2  call    ?WriteSingleLineData@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x1801160a7  mov     ebx, eax
0x1801160a9  test    eax, eax
0x1801160ab  js      loc_180116212
0x1801160b1  mov     r8, r12; unsigned __int16 *
0x1801160b4  lea     rdx, aName; "Name"
0x1801160bb  mov     rcx, rdi; this
0x1801160be  call    ?WriteSingleLineData@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x1801160c3  mov     ebx, eax
0x1801160c5  test    eax, eax
0x1801160c7  js      loc_18011620B
0x1801160cd  lea     rdx, aProvidervalues; "ProviderValues"
0x1801160d4  mov     rcx, rdi; this
0x1801160d7  call    ?WriteStartElement@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteStartElement(ushort const *)
0x1801160dc  mov     ebx, eax
0x1801160de  test    eax, eax
0x1801160e0  js      loc_180116204
0x1801160e6  mov     [rbp+40h+var_A0], 1
0x1801160ed  mov     [rbp+40h+var_9C], 2
0x1801160f4  mov     [rbp+40h+var_C0], r13
0x1801160f8  lea     r9, [rbp+40h+var_C0]
0x1801160fc  lea     r8, [rbp+40h+var_A0]
0x180116100  mov     rdx, r12
0x180116103  mov     rcx, r15
0x180116106  call    cs:__imp_PolicyManager_GetPolicy
0x18011610d  nop     dword ptr [rax+rax+00h]
0x180116112  mov     ebx, eax
0x180116114  test    eax, eax
0x180116116  js      loc_1801161E0
0x18011611c  mov     r8, [rbp+40h+var_C0]
0x180116120  mov     ecx, [r8+8]
0x180116124  sub     ecx, 1
0x180116127  jz      short loc_180116151
0x180116129  cmp     ecx, 1
0x18011612c  jnz     short loc_18011617E
0x18011612e  mov     r8, [r8+10h]; unsigned __int16 *
0x180116132  lea     rdx, aCurrent; "Current"
0x180116139  mov     rcx, rdi; this
0x18011613c  call    ?WriteSingleLineData@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180116141  mov     ebx, eax
0x180116143  test    eax, eax
0x180116145  jns     short loc_18011617E
0x180116147  mov     edx, 0BBh
0x18011614c  jmp     loc_1801161E5
0x180116151  mov     r8d, [r8+10h]
0x180116155  lea     rdx, aU; "%u"
0x18011615c  lea     rcx, [rbp+40h+var_90]
0x180116160  call    ??$swprintf_s@$0CA@@@YAHAEAY0CA@GPEBGZZ; swprintf_s<32>(ushort (&)[32],ushort const *,...)
0x180116165  lea     r8, [rbp+40h+var_90]; unsigned __int16 *
0x180116169  lea     rdx, aCurrent; "Current"
0x180116170  mov     rcx, rdi; this
0x180116173  call    ?WriteSingleLineData@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180116178  mov     ebx, eax
0x18011617a  test    eax, eax
0x18011617c  js      short loc_1801161D9
0x18011617e  mov     rcx, rdi; this
0x180116181  call    ?WriteEndElement@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteEndElement(void)
0x180116186  mov     ebx, eax
0x180116188  test    eax, eax
0x18011618a  js      short loc_1801161D2
0x18011618c  mov     rcx, rdi; this
0x18011618f  call    ?WriteEndElement@OEMCustomizationDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::OEMCustomizationDiagDataSource::WriteEndElement(void)
0x180116194  mov     ebx, eax
0x180116196  test    eax, eax
0x180116198  js      short loc_1801161CB
0x18011619a  lea     rcx, [rbp+40h+var_C0]
0x18011619e  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x1801161a3  inc     esi
0x1801161a5  jmp     loc_180116036
0x1801161aa  lea     rcx, [rsp+140h+var_D0]
0x1801161af  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1801161b4  nop
0x1801161b5  lea     rcx, [rsp+140h+var_D8]
0x1801161ba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801161bf  inc     r14d
0x1801161c2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801161c6  jmp     loc_180115F36
0x1801161cb  mov     edx, 0C8h
0x1801161d0  jmp     short loc_1801161E5
0x1801161d2  mov     edx, 0C6h
0x1801161d7  jmp     short loc_1801161E5
0x1801161d9  mov     edx, 0C0h
0x1801161de  jmp     short loc_1801161E5
0x1801161e0  mov     edx, 0B6h; void *
0x1801161e5  mov     rcx, [rbp+48h]; this
0x1801161e9  mov     r9d, eax; char *
0x1801161ec  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801161f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801161f8  nop
0x1801161f9  lea     rcx, [rbp+40h+var_C0]
0x1801161fd  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x180116202  jmp     short loc_18011624D
0x180116204  mov     edx, 0AFh
0x180116209  jmp     short loc_18011621E
0x18011620b  mov     edx, 0AEh
0x180116210  jmp     short loc_18011621E
0x180116212  mov     edx, 0ADh
0x180116217  jmp     short loc_18011621E
0x180116219  mov     edx, 0ACh; void *
0x18011621e  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180116225  mov     r9d, eax; char *
0x180116228  mov     rcx, [rbp+48h]; this
0x18011622c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116231  jmp     short loc_18011624D
0x180116233  mov     rcx, [rbp+48h]; this
0x180116237  mov     r9d, eax; char *
0x18011623a  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180116241  mov     edx, 0AAh; void *
0x180116246  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18011624b  mov     ebx, eax
0x18011624d  lea     rcx, [rsp+140h+var_D0]
0x180116252  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180116257  jmp     short loc_18011627A
0x180116259  mov     edx, 0A2h
  ... truncated ...
```
