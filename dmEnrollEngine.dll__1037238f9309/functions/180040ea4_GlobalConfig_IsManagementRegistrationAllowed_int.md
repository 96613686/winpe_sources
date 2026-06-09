# GlobalConfig::IsManagementRegistrationAllowed(int *)

- ea: `0x180040ea4`
- end: `0x180041076`
- name: `?IsManagementRegistrationAllowed@GlobalConfig@@QEBAJPEAH@Z`
- size: `466`
- prototype: `__int64 __fastcall(GlobalConfig *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800411d0`

## callees

- `0x1800071c0`
- `0x18000e0d0`
- `0x180040ea4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040f0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040f0f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040f56`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040ff7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040f56`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040ff7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041039`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041063`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041039`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041063`

## pseudocode

```c
__int64 __fastcall GlobalConfig::IsManagementRegistrationAllowed(GlobalConfig *this, int *a2)
{
  int v3; // ebx
  LSTATUS v4; // eax
  LSTATUS ValueW; // eax
  BOOL v6; // r14d
  LSTATUS v7; // eax
  BOOL v8; // edi
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-8h] BYREF
  GlobalConfig *pvData; // [rsp+80h] [rbp+30h] BYREF
  int v13; // [rsp+88h] [rbp+38h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD v15; // [rsp+98h] [rbp+48h] BYREF

  pvData = this;
  hkey = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  *a2 = 1;
  LODWORD(pvData) = 0;
  pcbData = 4;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\MDM",
         0,
         0x20119u,
         &hkey);
  v3 = v4;
  if ( v4 > 0 )
    v3 = (unsigned __int16)v4 | 0x80070000;
  if ( v3 >= 0 )
  {
    ValueW = RegGetValueW(hkey, 0, L"DisableRegistration", 0x18u, 0, &pvData, &pcbData);
    v3 = ValueW;
    if ( ValueW > 0 )
      v3 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( v3 == -2147024894 || v3 == -2147023267 )
  {
    v6 = 0;
LABEL_13:
    hKey = 0;
    v13 = 0;
    v15 = 4;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v3 = EEDBManager::OpenEnrollmentsHKEY(131097, &hKey);
    if ( v3 >= 0 )
    {
      v7 = RegGetValueW(hKey, 0, L"ExternallyManaged", 0x18u, 0, &v13, &v15);
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
    }
    if ( v3 == -2147024894 || v3 == -2147023267 )
    {
      v8 = 0;
      v3 = 0;
    }
    else
    {
      v8 = 1;
      if ( v3 >= 0 )
        v8 = v13 != 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v3 >= 0 )
      *a2 = !v6 && !v8;
    goto LABEL_28;
  }
  if ( v3 >= 0 )
  {
    v6 = (_DWORD)pvData != 0;
    goto LABEL_13;
  }
LABEL_28:
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180040ea4  mov     [rsp-28h+arg_0], rcx
0x180040ea9  push    rbp
0x180040eaa  push    rbx
0x180040eab  push    rsi
0x180040eac  push    rdi
0x180040ead  push    r14
0x180040eaf  mov     rbp, rsp
0x180040eb2  sub     rsp, 50h
0x180040eb6  mov     [rbp+hkey], 0
0x180040ebe  mov     rsi, rdx
0x180040ec1  test    rdx, rdx
0x180040ec4  jnz     short loc_180040ED0
0x180040ec6  mov     ebx, 80070057h
0x180040ecb  jmp     loc_180041069
0x180040ed0  mov     dword ptr [rdx], 1
0x180040ed6  lea     rcx, [rbp+hkey]
0x180040eda  xor     edx, edx
0x180040edc  mov     dword ptr [rbp+arg_0], 0
0x180040ee3  mov     [rbp+arg_10], 4
0x180040eea  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040eef  lea     rax, [rbp+hkey]
0x180040ef3  mov     r9d, 20119h; samDesired
0x180040ef9  xor     r8d, r8d; ulOptions
0x180040efc  mov     [rsp+50h+phkResult], rax; phkResult
0x180040f01  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180040f08  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040f0f  call    cs:__imp_RegOpenKeyExW
0x180040f15  mov     ebx, eax
0x180040f17  test    eax, eax
0x180040f19  jle     short loc_180040F24
0x180040f1b  movzx   ebx, ax
0x180040f1e  or      ebx, 80070000h
0x180040f24  test    ebx, ebx
0x180040f26  js      short loc_180040F6B
0x180040f28  mov     rcx, [rbp+hkey]; hkey
0x180040f2c  lea     rax, [rbp+arg_10]
0x180040f30  mov     [rsp+50h+pcbData], rax; pcbData
0x180040f35  lea     r8, aDisableregistr; "DisableRegistration"
0x180040f3c  lea     rax, [rbp+arg_0]
0x180040f40  mov     r9d, 18h; dwFlags
0x180040f46  mov     [rsp+50h+pvData], rax; pvData
0x180040f4b  xor     edx, edx; lpSubKey
0x180040f4d  mov     [rsp+50h+phkResult], 0; pdwType
0x180040f56  call    cs:__imp_RegGetValueW
0x180040f5c  mov     ebx, eax
0x180040f5e  test    eax, eax
0x180040f60  jle     short loc_180040F6B
0x180040f62  movzx   ebx, ax
0x180040f65  or      ebx, 80070000h
0x180040f6b  mov     edi, 8007065Dh
0x180040f70  cmp     ebx, 80070002h
0x180040f76  jz      short loc_180040F91
0x180040f78  cmp     ebx, edi
0x180040f7a  jz      short loc_180040F91
0x180040f7c  test    ebx, ebx
0x180040f7e  js      loc_18004105A
0x180040f84  xor     r14d, r14d
0x180040f87  cmp     dword ptr [rbp+arg_0], r14d
0x180040f8b  setnz   r14b
0x180040f8f  jmp     short loc_180040F94
0x180040f91  xor     r14d, r14d
0x180040f94  xor     edx, edx
0x180040f96  mov     [rbp+hKey], 0
0x180040f9e  lea     rcx, [rbp+hKey]
0x180040fa2  mov     [rbp+arg_8], 0
0x180040fa9  mov     [rbp+arg_18], 4
0x180040fb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040fb5  lea     rdx, [rbp+hKey]; HKEY *
0x180040fb9  mov     ecx, 20019h; unsigned int
0x180040fbe  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x180040fc3  mov     ebx, eax
0x180040fc5  test    eax, eax
0x180040fc7  js      short loc_18004100C
0x180040fc9  mov     rcx, [rbp+hKey]; hkey
0x180040fcd  lea     rax, [rbp+arg_18]
0x180040fd1  mov     [rsp+50h+pcbData], rax; pcbData
0x180040fd6  lea     r8, aExternallymana; "ExternallyManaged"
0x180040fdd  lea     rax, [rbp+arg_8]
0x180040fe1  mov     r9d, 18h; dwFlags
0x180040fe7  mov     [rsp+50h+pvData], rax; pvData
0x180040fec  xor     edx, edx; lpSubKey
0x180040fee  mov     [rsp+50h+phkResult], 0; pdwType
0x180040ff7  call    cs:__imp_RegGetValueW
0x180040ffd  mov     ebx, eax
0x180040fff  test    eax, eax
0x180041001  jle     short loc_18004100C
0x180041003  movzx   ebx, ax
0x180041006  or      ebx, 80070000h
0x18004100c  cmp     ebx, 80070002h
0x180041012  jz      short loc_18004102C
0x180041014  cmp     ebx, edi
0x180041016  jz      short loc_18004102C
0x180041018  mov     edi, 1
0x18004101d  test    ebx, ebx
0x18004101f  js      short loc_180041030
0x180041021  xor     edi, edi
0x180041023  cmp     [rbp+arg_8], edi
0x180041026  setnz   dil
0x18004102a  jmp     short loc_180041030
0x18004102c  xor     edi, edi
0x18004102e  xor     ebx, ebx
0x180041030  mov     rcx, [rbp+hKey]; hKey
0x180041034  test    rcx, rcx
0x180041037  jz      short loc_18004103F
0x180041039  call    cs:__imp_RegCloseKey
0x18004103f  test    ebx, ebx
0x180041041  js      short loc_18004105A
0x180041043  test    r14d, r14d
0x180041046  jnz     short loc_180041054
0x180041048  test    edi, edi
0x18004104a  jnz     short loc_180041054
0x18004104c  mov     dword ptr [rsi], 1
0x180041052  jmp     short loc_18004105A
0x180041054  mov     dword ptr [rsi], 0
0x18004105a  mov     rcx, [rbp+hkey]; hKey
0x18004105e  test    rcx, rcx
0x180041061  jz      short loc_180041069
0x180041063  call    cs:__imp_RegCloseKey
0x180041069  mov     eax, ebx
0x18004106b  add     rsp, 50h
0x18004106f  pop     r14
0x180041071  pop     rdi
0x180041072  pop     rsi
0x180041073  pop     rbx
0x180041074  pop     rbp
0x180041075  retn
```
