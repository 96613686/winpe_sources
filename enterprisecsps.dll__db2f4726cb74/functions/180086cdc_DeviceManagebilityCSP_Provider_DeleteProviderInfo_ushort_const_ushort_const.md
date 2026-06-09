# DeviceManagebilityCSP::Provider::DeleteProviderInfo(ushort const *,ushort const *)

- ea: `0x180086cdc`
- end: `0x180086e9b`
- name: `?DeleteProviderInfo@Provider@DeviceManagebilityCSP@@YAJPEBG0@Z`
- size: `447`
- prototype: `__int64 __fastcall(DeviceManagebilityCSP::Provider *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800853f0`

## callees

- `0x180008de0`
- `0x18000d4d4`
- `0x180025ac0`
- `0x18002aed0`
- `0x18002dcc8`
- `0x180086cdc`
- `0x18008737c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180086e5c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180086e5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180086e3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180086e3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180086d71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180086d71`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180086dad`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180086dad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeviceManagebilityCSP::Provider::DeleteProviderInfo(
        DeviceManagebilityCSP::Provider *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int CSPProviderIdRegPath; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  int v8; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  CSPProviderIdRegPath = DeviceManagebilityCSP::Provider::GetCSPProviderIdRegPath(
                           (DeviceManagebilityCSP::Provider *)SubKey,
                           a2,
                           (unsigned int)this,
                           a4);
  v6 = CSPProviderIdRegPath;
  if ( CSPProviderIdRegPath >= 0 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hKey);
    if ( v7 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xCC,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\providernodehelper.cpp",
             (const char *)v7,
             phkResulta);
    }
    else
    {
      v8 = OmaDmRegistryDeleteValue(hKey, 0, a2);
      v6 = v8;
      if ( v8 >= 0 )
      {
        cValues = 0;
        RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
        if ( !cValues )
          RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
        v6 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCE,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\providernodehelper.cpp",
          (const char *)(unsigned int)v8,
          phkResulta);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicemanageability\\providernodehelper.cpp",
      (const char *)(unsigned int)CSPProviderIdRegPath,
      phkResult);
  }
  return v6;
}

```

## disassembly

```asm
0x180086cdc  mov     [rsp-8+arg_10], rbx
0x180086ce1  mov     [rsp-8+arg_18], rdi
0x180086ce6  push    rbp
0x180086ce7  lea     rbp, [rsp-190h]
0x180086cef  sub     rsp, 290h
0x180086cf6  mov     rax, cs:__security_cookie
0x180086cfd  xor     rax, rsp
0x180086d00  mov     [rbp+190h+var_10], rax
0x180086d07  mov     rdi, rdx
0x180086d0a  mov     r8, rcx; unsigned int
0x180086d0d  lea     rcx, [rsp+290h+SubKey]; this
0x180086d12  call    ?GetCSPProviderIdRegPath@Provider@DeviceManagebilityCSP@@YAJPEAGKPEBG@Z; DeviceManagebilityCSP::Provider::GetCSPProviderIdRegPath(ushort *,ulong,ushort const *)
0x180086d17  mov     ebx, eax
0x180086d19  test    eax, eax
0x180086d1b  jns     short loc_180086D3D
0x180086d1d  mov     rcx, [rbp+198h]; this
0x180086d24  mov     r9d, eax; char *
0x180086d27  lea     r8, aOnecoreuapAdmi_72; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180086d2e  mov     edx, 0C4h; void *
0x180086d33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086d38  jmp     loc_180086E74
0x180086d3d  mov     [rsp+290h+hKey], 0
0x180086d46  xor     edx, edx
0x180086d48  lea     rcx, [rsp+290h+hKey]
0x180086d4d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180086d52  lea     rax, [rsp+290h+hKey]
0x180086d57  mov     [rsp+290h+phkResult], rax; int
0x180086d5c  mov     r9d, 2011Fh; samDesired
0x180086d62  xor     r8d, r8d; ulOptions
0x180086d65  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180086d6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180086d71  call    cs:__imp_RegOpenKeyExW
0x180086d78  nop     dword ptr [rax+rax+00h]
0x180086d7d  test    eax, eax
0x180086d7f  jz      short loc_180086DA3
0x180086d81  mov     rcx, [rbp+198h]; this
0x180086d88  mov     r9d, eax; char *
0x180086d8b  lea     r8, aOnecoreuapAdmi_72; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180086d92  mov     edx, 0CCh; void *
0x180086d97  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180086d9c  mov     ebx, eax
0x180086d9e  jmp     loc_180086E6A
0x180086da3  mov     r8, rdi
0x180086da6  xor     edx, edx
0x180086da8  mov     rcx, [rsp+290h+hKey]
0x180086dad  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x180086db4  nop     dword ptr [rax+rax+00h]
0x180086db9  mov     ebx, eax
0x180086dbb  test    eax, eax
0x180086dbd  jns     short loc_180086DDF
0x180086dbf  mov     rcx, [rbp+198h]; this
0x180086dc6  mov     r9d, eax; char *
0x180086dc9  lea     r8, aOnecoreuapAdmi_72; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180086dd0  mov     edx, 0CEh; void *
0x180086dd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086dda  jmp     loc_180086E6A
0x180086ddf  mov     [rsp+290h+cValues], 0
0x180086de7  mov     [rsp+290h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180086df0  mov     [rsp+290h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180086df9  mov     [rsp+290h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180086e02  mov     [rsp+290h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180086e0b  lea     rax, [rsp+290h+cValues]
0x180086e10  mov     [rsp+290h+lpcValues], rax; lpcValues
0x180086e15  mov     [rsp+290h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180086e1e  mov     [rsp+290h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180086e27  mov     [rsp+290h+phkResult], 0; lpcSubKeys
0x180086e30  xor     r9d, r9d; lpReserved
0x180086e33  xor     r8d, r8d; lpcchClass
0x180086e36  xor     edx, edx; lpClass
0x180086e38  mov     rcx, [rsp+290h+hKey]; hKey
0x180086e3d  call    cs:__imp_RegQueryInfoKeyW
0x180086e44  nop     dword ptr [rax+rax+00h]
0x180086e49  cmp     [rsp+290h+cValues], 0
0x180086e4e  jnz     short loc_180086E68
0x180086e50  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180086e55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180086e5c  call    cs:__imp_RegDeleteTreeW
0x180086e63  nop     dword ptr [rax+rax+00h]
0x180086e68  xor     ebx, ebx
0x180086e6a  lea     rcx, [rsp+290h+hKey]
0x180086e6f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180086e74  mov     eax, ebx
0x180086e76  mov     rcx, [rbp+190h+var_10]
0x180086e7d  xor     rcx, rsp; StackCookie
0x180086e80  call    __security_check_cookie
0x180086e85  lea     r11, [rsp+290h+var_s0]
0x180086e8d  mov     rbx, [r11+20h]
0x180086e91  mov     rdi, [r11+28h]
0x180086e95  mov     rsp, r11
0x180086e98  pop     rbp
0x180086e99  retn
```
