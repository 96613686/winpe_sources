# EnterpriseProvisioningPlugin::_ConsolidateRebootRequests(void)

- ea: `0x180047828`
- end: `0x1800479a7`
- name: `?_ConsolidateRebootRequests@EnterpriseProvisioningPlugin@@AEAAJXZ`
- size: `383`
- prototype: `__int64 __fastcall(EnterpriseProvisioningPlugin *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180047d68`
- `0x180047e44`

## callees

- `0x180008544`
- `0x18001ea00`
- `0x1800235c8`
- `0x180047300`
- `0x180047828`
- `0x1800bf178`
- `0x1800bf3e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047883`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047883`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047870`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800478e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047870`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800478e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004790f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004790f`

## string_xrefs

- `0x180047920`: `shell\oobe\machine\plugins\provisioning\enterpriseprovisioningplugin.cpp`
- `0x18004797a`: `shell\oobe\machine\plugins\provisioning\enterpriseprovisioningplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseProvisioningPlugin::_ConsolidateRebootRequests(EnterpriseProvisioningPlugin *this)
{
  bool v2; // di
  const WCHAR *v3; // rbx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  HKEY v9[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HKEY hKey; // [rsp+68h] [rbp+28h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  v2 = 1;
  if ( !`ProvIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    hKey = 0;
    `ProvIsStateSeparationEnabled'::`2'::s_Redirection = RegOpenKeyExW(
                                                           HKEY_LOCAL_MACHINE,
                                                           L"Software\\Microsoft\\Provisioning\\StateSeparationMode",
                                                           0,
                                                           0x20119u,
                                                           &hKey) == 0;
    RegCloseKey(hKey);
    `ProvIsStateSeparationEnabled'::`2'::s_HasRun = 1;
  }
  v3 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\ReloadsForced";
  if ( !`ProvIsStateSeparationEnabled'::`2'::s_Redirection )
    v3 = L"SOFTWARE\\Microsoft\\Provisioning\\ReloadsForced";
  Data = 0;
  v9[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    v9,
    0);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 1u, 0x20019u, v9)
    || (cbData = 4, (v4 = RegQueryValueExW(v9[0], 0, 0, 0, (LPBYTE)&Data, &cbData)) == 0) )
  {
    LOBYTE(hKey) = 0;
    CBasePlugin::_GetGlobalSettingBool(this, L"REBOOT", (bool *)&hKey);
    if ( !(_BYTE)hKey && !Data )
      v2 = 0;
    v6 = CBasePlugin::_SetGlobalSettingBool(this, L"REBOOT", v2);
    v5 = v6;
    if ( v6 >= 0 )
      v5 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"shell\\oobe\\machine\\plugins\\provisioning\\enterpriseprovisioningplugin.cpp",
        (const char *)(unsigned int)v6,
        phkResult);
  }
  else
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x72,
           (unsigned int)"shell\\oobe\\machine\\plugins\\provisioning\\enterpriseprovisioningplugin.cpp",
           (const char *)v4,
           phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v9);
  return v5;
}

```

## disassembly

```asm
0x180047828  mov     [rsp-18h+arg_0], rbx
0x18004782d  push    rbp
0x18004782e  push    rsi
0x18004782f  push    rdi
0x180047830  mov     rbp, rsp
0x180047833  sub     rsp, 40h
0x180047837  mov     rsi, rcx
0x18004783a  mov     edi, 1
0x18004783f  cmp     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180047846  jnz     short loc_180047890
0x180047848  mov     [rbp+hKey], 0
0x180047850  lea     rax, [rbp+hKey]
0x180047854  mov     [rsp+40h+phkResult], rax; phkResult
0x180047859  mov     r9d, 20119h; samDesired
0x18004785f  xor     r8d, r8d; ulOptions
0x180047862  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\Provisioning\\Stat"...
0x180047869  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047870  call    cs:__imp_RegOpenKeyExW
0x180047876  test    eax, eax
0x180047878  setz    cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18004787f  mov     rcx, [rbp+hKey]; hKey
0x180047883  call    cs:__imp_RegCloseKey
0x180047889  mov     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, dil; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180047890  mov     al, cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180047896  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Provisioning\\Relo"...
0x18004789d  lea     rbx, aOsdataSoftware; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800478a4  test    al, al
0x1800478a6  cmovz   rbx, rdx
0x1800478aa  mov     [rbp+Data], 0
0x1800478b1  mov     [rbp+var_10], 0
0x1800478b9  xor     edx, edx
0x1800478bb  lea     rcx, [rbp+var_10]
0x1800478bf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800478c4  lea     rax, [rbp+var_10]
0x1800478c8  mov     [rsp+40h+phkResult], rax; int
0x1800478cd  mov     r9d, 20019h; samDesired
0x1800478d3  mov     r8d, edi; ulOptions
0x1800478d6  mov     rdx, rbx; lpSubKey
0x1800478d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800478e0  call    cs:__imp_RegOpenKeyExW
0x1800478e6  test    eax, eax
0x1800478e8  jnz     short loc_180047935
0x1800478ea  mov     [rbp+cbData], 4
0x1800478f1  lea     rax, [rbp+cbData]
0x1800478f5  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800478fa  lea     rax, [rbp+Data]
0x1800478fe  mov     [rsp+40h+phkResult], rax; unsigned int
0x180047903  xor     r9d, r9d; lpType
0x180047906  xor     r8d, r8d; lpReserved
0x180047909  xor     edx, edx; lpValueName
0x18004790b  mov     rcx, [rbp+var_10]; hKey
0x18004790f  call    cs:__imp_RegQueryValueExW
0x180047915  test    eax, eax
0x180047917  jz      short loc_180047935
0x180047919  mov     rcx, [rbp+18h]; this
0x18004791d  mov     r9d, eax; char *
0x180047920  lea     r8, aShellOobeMachi_43; "shell\\oobe\\machine\\plugins\\provisio"...
0x180047927  mov     edx, 72h ; 'r'; void *
0x18004792c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180047931  mov     ebx, eax
0x180047933  jmp     short loc_18004798F
0x180047935  mov     byte ptr [rbp+hKey], 0
0x180047939  lea     r8, [rbp+hKey]; bool *
0x18004793d  lea     rdx, aReboot; "REBOOT"
0x180047944  mov     rcx, rsi; this
0x180047947  call    ?_GetGlobalSettingBool@CBasePlugin@@IEAAJPEBGPEA_N@Z; CBasePlugin::_GetGlobalSettingBool(ushort const *,bool *)
0x18004794c  cmp     byte ptr [rbp+hKey], 0
0x180047950  jnz     short loc_18004795B
0x180047952  cmp     [rbp+Data], 0
0x180047956  ja      short loc_18004795B
0x180047958  xor     dil, dil
0x18004795b  mov     r8b, dil; bool
0x18004795e  lea     rdx, aReboot; "REBOOT"
0x180047965  mov     rcx, rsi; this
0x180047968  call    ?_SetGlobalSettingBool@CBasePlugin@@IEAAJPEBG_N@Z; CBasePlugin::_SetGlobalSettingBool(ushort const *,bool)
0x18004796d  mov     ebx, eax
0x18004796f  test    eax, eax
0x180047971  jns     short loc_18004798D
0x180047973  mov     rcx, [rbp+18h]; this
0x180047977  mov     r9d, eax; char *
0x18004797a  lea     r8, aShellOobeMachi_43; "shell\\oobe\\machine\\plugins\\provisio"...
0x180047981  mov     edx, 77h ; 'w'; void *
0x180047986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004798b  jmp     short loc_18004798F
0x18004798d  xor     ebx, ebx
0x18004798f  lea     rcx, [rbp+var_10]
0x180047993  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180047998  mov     eax, ebx
0x18004799a  mov     rbx, [rsp+40h+arg_0]
0x18004799f  add     rsp, 40h
0x1800479a3  pop     rdi
0x1800479a4  pop     rsi
0x1800479a5  pop     rbp
0x1800479a6  retn
```
