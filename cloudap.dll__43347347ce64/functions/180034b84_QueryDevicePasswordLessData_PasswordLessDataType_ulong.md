# QueryDevicePasswordLessData(PasswordLessDataType,ulong *)

- ea: `0x180034b84`
- end: `0x180034d30`
- name: `?QueryDevicePasswordLessData@@YAJW4PasswordLessDataType@@PEAK@Z`
- size: `428`
- prototype: `int __high(enum PasswordLessDataType, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003be94`
- `0x180064c44`

## callees

- `0x180034b84`
- `0x180034d38`
- `0x18003b944`
- `0x18003b964`
- `0x18003bf28`
- `0x180040024`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034bf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034c58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034d1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034bf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034c58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034d1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034c2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034c2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034cb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034cb8`

## string_xrefs

- `0x180034bb7`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180034c6d`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180034cf0`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall QueryDevicePasswordLessData(__int64 a1, BYTE *a2)
{
  const WCHAR *StringName; // rsi
  unsigned int v4; // ebx
  HKEY v6; // rbx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  int phkResultb; // [rsp+20h] [rbp-20h]
  _BYTE v12[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  StringName = (const WCHAR *)GetStringName(a1);
  if ( !a2 )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)0x80004003LL,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v4;
  }
  *(_DWORD *)a2 = 0;
  v6 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v12);
    RegCloseKey(v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v12);
  }
  hKey = 0;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\Device",
         0,
         0x20019u,
         &hKey);
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( v4 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v4,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v4;
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
  Type = 0;
  cbData = 4;
  v8 = RegQueryValueExW(hKey, StringName, 0, &Type, a2, &cbData);
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( v4 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A0,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v4,
        phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v4;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 2147942402LL;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180034b84  mov     [rsp-18h+arg_0], rbx
0x180034b89  push    rbp
0x180034b8a  push    rsi
0x180034b8b  push    rdi
0x180034b8c  mov     rbp, rsp
0x180034b8f  sub     rsp, 40h
0x180034b93  mov     rdi, rdx
0x180034b96  mov     [rbp+hKey], 0
0x180034b9e  call    ?GetStringName@@YAPEBGW4PasswordLessDataType@@@Z; GetStringName(PasswordLessDataType)
0x180034ba3  mov     rsi, rax
0x180034ba6  test    rdi, rdi
0x180034ba9  jnz     short loc_180034BDA
0x180034bab  mov     rcx, [rbp+18h]; this
0x180034baf  mov     ebx, 80004003h
0x180034bb4  mov     r9d, ebx; char *
0x180034bb7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180034bbe  mov     edx, 189h; void *
0x180034bc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034bc8  nop
0x180034bc9  lea     rcx, [rbp+hKey]
0x180034bcd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180034bd2  nop
0x180034bd3  mov     eax, ebx
0x180034bd5  jmp     loc_180034D23
0x180034bda  mov     dword ptr [rdi], 0
0x180034be0  mov     rbx, [rbp+hKey]
0x180034be4  test    rbx, rbx
0x180034be7  jz      short loc_180034C05
0x180034be9  lea     rcx, [rbp+var_10]; this
0x180034bed  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180034bf2  mov     rcx, rbx; hKey
0x180034bf5  call    cs:__imp_RegCloseKey
0x180034bfb  lea     rcx, [rbp+var_10]; this
0x180034bff  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180034c04  nop
0x180034c05  mov     [rbp+hKey], 0
0x180034c0d  lea     rax, [rbp+hKey]
0x180034c11  mov     [rsp+40h+phkResult], rax; int
0x180034c16  mov     r9d, 20019h; samDesired
0x180034c1c  xor     r8d, r8d; ulOptions
0x180034c1f  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180034c26  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034c2d  call    cs:__imp_RegOpenKeyExW
0x180034c33  mov     ebx, eax
0x180034c35  test    eax, eax
0x180034c37  jle     short loc_180034C42
0x180034c39  movzx   ebx, ax
0x180034c3c  or      ebx, 80070000h
0x180034c42  test    ebx, ebx
0x180034c44  jns     short loc_180034C8E
0x180034c46  mov     edi, 80070002h
0x180034c4b  cmp     ebx, edi
0x180034c4d  jnz     short loc_180034C66
0x180034c4f  mov     rcx, [rbp+hKey]; hKey
0x180034c53  test    rcx, rcx
0x180034c56  jz      short loc_180034C5F
0x180034c58  call    cs:__imp_RegCloseKey
0x180034c5e  nop
0x180034c5f  mov     eax, edi
0x180034c61  jmp     loc_180034D23
0x180034c66  mov     rcx, [rbp+18h]; this
0x180034c6a  mov     r9d, ebx; char *
0x180034c6d  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180034c74  mov     edx, 193h; void *
0x180034c79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034c7e  nop
0x180034c7f  lea     rcx, [rbp+hKey]
0x180034c83  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180034c88  nop
0x180034c89  jmp     loc_180034BD3
0x180034c8e  mov     [rbp+Type], 0
0x180034c95  mov     [rbp+cbData], 4
0x180034c9c  lea     rax, [rbp+cbData]
0x180034ca0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180034ca5  mov     [rsp+40h+phkResult], rdi; int
0x180034caa  lea     r9, [rbp+Type]; lpType
0x180034cae  xor     r8d, r8d; lpReserved
0x180034cb1  mov     rdx, rsi; lpValueName
0x180034cb4  mov     rcx, [rbp+hKey]; hKey
0x180034cb8  call    cs:__imp_RegQueryValueExW
0x180034cbe  mov     ebx, eax
0x180034cc0  test    eax, eax
0x180034cc2  jle     short loc_180034CCD
0x180034cc4  movzx   ebx, ax
0x180034cc7  or      ebx, 80070000h
0x180034ccd  test    ebx, ebx
0x180034ccf  jns     short loc_180034D11
0x180034cd1  mov     edi, 80070002h
0x180034cd6  cmp     ebx, edi
0x180034cd8  jnz     short loc_180034CE9
0x180034cda  lea     rcx, [rbp+hKey]
0x180034cde  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180034ce3  nop
0x180034ce4  jmp     loc_180034C5F
0x180034ce9  mov     rcx, [rbp+18h]; this
0x180034ced  mov     r9d, ebx; char *
0x180034cf0  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180034cf7  mov     edx, 1A0h; void *
0x180034cfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034d01  nop
0x180034d02  lea     rcx, [rbp+hKey]
0x180034d06  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180034d0b  nop
0x180034d0c  jmp     loc_180034BD3
0x180034d11  mov     rcx, [rbp+hKey]; hKey
0x180034d15  test    rcx, rcx
0x180034d18  jz      short loc_180034D21
0x180034d1a  call    cs:__imp_RegCloseKey
0x180034d20  nop
0x180034d21  xor     eax, eax
0x180034d23  mov     rbx, [rsp+40h+arg_0]
0x180034d28  add     rsp, 40h
0x180034d2c  pop     rdi
0x180034d2d  pop     rsi
0x180034d2e  pop     rbp
0x180034d2f  retn
```
