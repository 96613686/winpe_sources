# GetUserNgcWasEnrolledRegKey(ushort const *,int *)

- ea: `0x18003db68`
- end: `0x18003dd94`
- name: `?GetUserNgcWasEnrolledRegKey@@YAJPEBGPEAH@Z`
- size: `556`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180041de0`

## callees

- `0x18003bf28`
- `0x18003db68`
- `0x18003dd9c`
- `0x180040024`
- `0x180042410`
- `0x180045b04`
- `0x180045b80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dc71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dc71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003dcf9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003dcf9`

## string_xrefs

- `0x18003dbe6`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18003dc27`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18003dcaf`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18003dd35`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetUserNgcWasEnrolledRegKey(const unsigned __int16 *a1, int *a2)
{
  int v3; // eax
  unsigned __int64 v4; // rdx
  const unsigned __int16 *v5; // r11
  unsigned int v6; // ebx
  int v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD Type[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *(_DWORD *)Data = 0;
  cbData = 4;
  Type[0] = 0;
  hKey = 0;
  *a2 = 0;
  v3 = StringCchCopyW(SubKey, 0x104u, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\NgcStatus\\");
  v6 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v3,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v6;
  }
  v8 = StringCchCatW(SubKey, v4, v5);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v8,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v6;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( v6 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v6,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v6;
    }
    goto LABEL_10;
  }
  v10 = RegQueryValueExW(hKey, L"NgcSetup", 0, Type, Data, &cbData);
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( v6 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v6,
        phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v6;
    }
LABEL_10:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 2147942402LL;
  }
  *a2 = *(_DWORD *)Data == 1;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18003db68  mov     [rsp-8+arg_10], rbx
0x18003db6d  mov     [rsp-8+arg_18], rdi
0x18003db72  push    rbp
0x18003db73  lea     rbp, [rsp-170h]
0x18003db7b  sub     rsp, 270h
0x18003db82  mov     rax, cs:__security_cookie
0x18003db89  xor     rax, rsp
0x18003db8c  mov     [rbp+170h+var_10], rax
0x18003db93  mov     rdi, rdx
0x18003db96  mov     r11, rcx
0x18003db99  mov     dword ptr [rsp+270h+Data], 0
0x18003dba1  mov     [rsp+270h+cbData], 4
0x18003dba9  mov     [rsp+270h+Type], 0
0x18003dbb1  mov     [rsp+270h+hKey], 0
0x18003dbba  mov     dword ptr [rdx], 0
0x18003dbc0  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003dbc7  mov     edx, 104h; unsigned __int64
0x18003dbcc  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x18003dbd1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003dbd6  mov     ebx, eax
0x18003dbd8  test    eax, eax
0x18003dbda  jns     short loc_18003DC0A
0x18003dbdc  mov     rcx, [rbp+178h]; this
0x18003dbe3  mov     r9d, eax; char *
0x18003dbe6  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18003dbed  mov     edx, 96h; void *
0x18003dbf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dbf7  nop
0x18003dbf8  lea     rcx, [rsp+270h+hKey]
0x18003dbfd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003dc02  nop
0x18003dc03  mov     eax, ebx
0x18003dc05  jmp     loc_18003DD70
0x18003dc0a  mov     r8, r11; unsigned __int16 *
0x18003dc0d  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x18003dc12  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003dc17  mov     ebx, eax
0x18003dc19  test    eax, eax
0x18003dc1b  jns     short loc_18003DC46
0x18003dc1d  mov     rcx, [rbp+178h]; this
0x18003dc24  mov     r9d, eax; char *
0x18003dc27  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18003dc2e  mov     edx, 98h; void *
0x18003dc33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dc38  nop
0x18003dc39  lea     rcx, [rsp+270h+hKey]
0x18003dc3e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003dc43  nop
0x18003dc44  jmp     short loc_18003DC03
0x18003dc46  xor     edx, edx
0x18003dc48  lea     rcx, [rsp+270h+hKey]
0x18003dc4d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003dc52  lea     rax, [rsp+270h+hKey]
0x18003dc57  mov     [rsp+270h+phkResult], rax; int
0x18003dc5c  mov     r9d, 20019h; samDesired
0x18003dc62  xor     r8d, r8d; ulOptions
0x18003dc65  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x18003dc6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003dc71  call    cs:__imp_RegOpenKeyExW
0x18003dc77  mov     ebx, eax
0x18003dc79  test    eax, eax
0x18003dc7b  jle     short loc_18003DC86
0x18003dc7d  movzx   ebx, ax
0x18003dc80  or      ebx, 80070000h
0x18003dc86  test    ebx, ebx
0x18003dc88  jns     short loc_18003DCD1
0x18003dc8a  mov     edi, 80070002h
0x18003dc8f  cmp     ebx, edi
0x18003dc91  jnz     short loc_18003DCA5
0x18003dc93  lea     rcx, [rsp+270h+hKey]
0x18003dc98  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003dc9d  nop
0x18003dc9e  mov     eax, edi
0x18003dca0  jmp     loc_18003DD70
0x18003dca5  mov     rcx, [rbp+178h]; this
0x18003dcac  mov     r9d, ebx; char *
0x18003dcaf  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18003dcb6  mov     edx, 9Ch; void *
0x18003dcbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dcc0  nop
0x18003dcc1  lea     rcx, [rsp+270h+hKey]
0x18003dcc6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003dccb  nop
0x18003dccc  jmp     loc_18003DC03
0x18003dcd1  lea     rax, [rsp+270h+cbData]
0x18003dcd6  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18003dcdb  lea     rax, [rsp+270h+Data]
0x18003dce0  mov     [rsp+270h+phkResult], rax; int
0x18003dce5  lea     r9, [rsp+270h+Type]; lpType
0x18003dcea  xor     r8d, r8d; lpReserved
0x18003dced  lea     rdx, aNgcsetup; "NgcSetup"
0x18003dcf4  mov     rcx, [rsp+270h+hKey]; hKey
0x18003dcf9  call    cs:__imp_RegQueryValueExW
0x18003dcff  mov     ebx, eax
0x18003dd01  test    eax, eax
0x18003dd03  jle     short loc_18003DD0E
0x18003dd05  movzx   ebx, ax
0x18003dd08  or      ebx, 80070000h
0x18003dd0e  test    ebx, ebx
0x18003dd10  jns     short loc_18003DD57
0x18003dd12  mov     edi, 80070002h
0x18003dd17  cmp     ebx, edi
0x18003dd19  jnz     short loc_18003DD2B
0x18003dd1b  lea     rcx, [rsp+270h+hKey]
0x18003dd20  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003dd25  nop
0x18003dd26  jmp     loc_18003DC9E
0x18003dd2b  mov     rcx, [rbp+178h]; this
0x18003dd32  mov     r9d, ebx; char *
0x18003dd35  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18003dd3c  mov     edx, 0A0h; void *
0x18003dd41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dd46  nop
0x18003dd47  lea     rcx, [rsp+270h+hKey]
0x18003dd4c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003dd51  nop
0x18003dd52  jmp     loc_18003DC03
0x18003dd57  xor     eax, eax
0x18003dd59  cmp     dword ptr [rsp+270h+Data], 1
0x18003dd5e  setz    al
0x18003dd61  mov     [rdi], eax
0x18003dd63  lea     rcx, [rsp+270h+hKey]
0x18003dd68  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003dd6d  nop
0x18003dd6e  xor     eax, eax
0x18003dd70  mov     rcx, [rbp+170h+var_10]
0x18003dd77  xor     rcx, rsp; StackCookie
0x18003dd7a  call    __security_check_cookie
0x18003dd7f  lea     r11, [rsp+270h+var_s0]
0x18003dd87  mov     rbx, [r11+20h]
0x18003dd8b  mov     rdi, [r11+28h]
0x18003dd8f  mov     rsp, r11
0x18003dd92  pop     rbp
0x18003dd93  retn
```
