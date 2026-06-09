# SetDevicePasswordLessData(PasswordLessDataType,ulong)

- ea: `0x180064f34`
- end: `0x18006504c`
- name: `?SetDevicePasswordLessData@@YAJW4PasswordLessDataType@@K@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bd64`

## callees

- `0x180034d38`
- `0x18003dd9c`
- `0x180040024`
- `0x18004af14`
- `0x180064f34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180064fa7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180064fa7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180065001`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180065001`

## string_xrefs

- `0x180064fb9`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180065013`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SetDevicePasswordLessData()
{
  const WCHAR *StringName; // rbx
  unsigned int v1; // eax
  unsigned int v2; // ebx
  unsigned int v4; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-48h]
  int Data[6]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  Data[0] = 2;
  hKey = 0;
  StringName = (const WCHAR *)GetStringName(0);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\Device",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v1 )
  {
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x170,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v1,
           dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v2;
  }
  v4 = RegSetValueExW(hKey, StringName, 0, 4u, (const BYTE *)Data, 4u);
  if ( v4 )
  {
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x178,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v4,
           dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v2;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180064f34  mov     rax, rsp
0x180064f37  push    rbx
0x180064f38  sub     rsp, 60h
0x180064f3c  mov     dword ptr [rax-18h], 2
0x180064f43  mov     qword ptr [rax+18h], 0
0x180064f4b  xor     ecx, ecx
0x180064f4d  call    ?GetStringName@@YAPEBGW4PasswordLessDataType@@@Z; GetStringName(PasswordLessDataType)
0x180064f52  mov     rbx, rax
0x180064f55  xor     edx, edx
0x180064f57  lea     rcx, [rsp+68h+hKey]
0x180064f5f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180064f64  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180064f6d  lea     rax, [rsp+68h+hKey]
0x180064f75  mov     [rsp+68h+phkResult], rax; phkResult
0x180064f7a  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180064f83  mov     [rsp+68h+samDesired], 20006h; samDesired
0x180064f8b  mov     [rsp+68h+dwOptions], 0; unsigned int
0x180064f93  xor     r9d, r9d; lpClass
0x180064f96  xor     r8d, r8d; Reserved
0x180064f99  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180064fa0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180064fa7  call    cs:__imp_RegCreateKeyExW
0x180064fad  test    eax, eax
0x180064faf  jz      short loc_180064FDE
0x180064fb1  mov     rcx, [rsp+68h]; this
0x180064fb6  mov     r9d, eax; char *
0x180064fb9  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180064fc0  mov     edx, 170h; void *
0x180064fc5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180064fca  mov     ebx, eax
0x180064fcc  lea     rcx, [rsp+68h+hKey]
0x180064fd4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180064fd9  nop
0x180064fda  mov     eax, ebx
0x180064fdc  jmp     short loc_180065046
0x180064fde  mov     r9d, 4; dwType
0x180064fe4  mov     [rsp+68h+samDesired], r9d; cbData
0x180064fe9  lea     rax, [rsp+68h+Data]
0x180064fee  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int
0x180064ff3  xor     r8d, r8d; Reserved
0x180064ff6  mov     rdx, rbx; lpValueName
0x180064ff9  mov     rcx, [rsp+68h+hKey]; hKey
0x180065001  call    cs:__imp_RegSetValueExW
0x180065007  test    eax, eax
0x180065009  jz      short loc_180065036
0x18006500b  mov     rcx, [rsp+68h]; this
0x180065010  mov     r9d, eax; char *
0x180065013  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18006501a  mov     edx, 178h; void *
0x18006501f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180065024  mov     ebx, eax
0x180065026  lea     rcx, [rsp+68h+hKey]
0x18006502e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180065033  nop
0x180065034  jmp     short loc_180064FDA
0x180065036  lea     rcx, [rsp+68h+hKey]
0x18006503e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180065043  nop
0x180065044  xor     eax, eax
0x180065046  add     rsp, 60h
0x18006504a  pop     rbx
0x18006504b  retn
```
