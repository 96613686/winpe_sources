# _OpenFalconKey(void)

- ea: `0x18000e9c4`
- end: `0x18000eaa9`
- name: `?_OpenFalconKey@@YAJXZ`
- size: `229`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000da54`

## callees

- `0x18000d890`
- `0x18000e9c4`
- `0x18000eb48`
- `0x18002f0e0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000ea45`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea74`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea45`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea74`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 _OpenFalconKey(void)
{
  int FalconSectionName; // eax
  __int64 v1; // rdx
  unsigned int v2; // ebx
  const WCHAR *v3; // rdx
  __int64 v4; // rdx
  const WCHAR *v5; // rdx
  _BYTE v7[8]; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v9; // [rsp+50h] [rbp-10h]

  v9 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  FalconSectionName = GetFalconSectionName(v7);
  if ( FalconSectionName >= 0 )
  {
    v3 = (const WCHAR *)lpSubKey;
    if ( v9 >= 8 )
      v3 = lpSubKey[0];
    v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x2001Fu, &g_hKeyFalcon);
    if ( v2 )
    {
      v5 = (const WCHAR *)lpSubKey;
      if ( v9 >= 8 )
        v5 = lpSubKey[0];
      v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &g_hKeyFalcon);
    }
    LOBYTE(v4) = 1;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v7, v4, 0);
  }
  else
  {
    v2 = (unsigned __int16)FalconSectionName;
    LOBYTE(v1) = 1;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v7, v1, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x18000e9c4  mov     [rsp-8+arg_0], rbx
0x18000e9c9  mov     [rsp-8+arg_8], rsi
0x18000e9ce  push    rbp
0x18000e9cf  mov     rbp, rsp
0x18000e9d2  sub     rsp, 60h
0x18000e9d6  mov     rax, cs:__security_cookie
0x18000e9dd  xor     rax, rsp
0x18000e9e0  mov     [rbp+var_8], rax
0x18000e9e4  mov     [rbp+var_10], 7
0x18000e9ec  mov     [rbp+var_18], 0
0x18000e9f4  xor     eax, eax
0x18000e9f6  mov     word ptr [rbp+lpSubKey], ax
0x18000e9fa  lea     rcx, [rbp+var_30]
0x18000e9fe  call    ?GetFalconSectionName@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z; GetFalconSectionName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> &)
0x18000ea03  test    eax, eax
0x18000ea05  jns     short loc_18000EA1B
0x18000ea07  movzx   ebx, ax
0x18000ea0a  xor     r8d, r8d
0x18000ea0d  mov     dl, 1
0x18000ea0f  lea     rcx, [rbp+var_30]
0x18000ea13  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18000ea18  nop
0x18000ea19  jmp     short loc_18000EA8B
0x18000ea1b  lea     rdx, [rbp+lpSubKey]
0x18000ea1f  cmp     [rbp+var_10], 8
0x18000ea24  cmovnb  rdx, [rbp+lpSubKey]; lpSubKey
0x18000ea29  lea     rsi, ?g_hKeyFalcon@@3VCAutoCloseRegHandle@@A; CAutoCloseRegHandle g_hKeyFalcon
0x18000ea30  mov     [rsp+60h+phkResult], rsi; phkResult
0x18000ea35  mov     r9d, 2001Fh; samDesired
0x18000ea3b  xor     r8d, r8d; ulOptions
0x18000ea3e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ea45  call    cs:__imp_RegOpenKeyExW
0x18000ea4b  mov     ebx, eax
0x18000ea4d  test    eax, eax
0x18000ea4f  jz      short loc_18000EA7C
0x18000ea51  lea     rdx, [rbp+lpSubKey]
0x18000ea55  cmp     [rbp+var_10], 8
0x18000ea5a  cmovnb  rdx, [rbp+lpSubKey]; lpSubKey
0x18000ea5f  mov     [rsp+60h+phkResult], rsi; phkResult
0x18000ea64  mov     r9d, 20019h; samDesired
0x18000ea6a  xor     r8d, r8d; ulOptions
0x18000ea6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ea74  call    cs:__imp_RegOpenKeyExW
0x18000ea7a  mov     ebx, eax
0x18000ea7c  xor     r8d, r8d
0x18000ea7f  mov     dl, 1
0x18000ea81  lea     rcx, [rbp+var_30]
0x18000ea85  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18000ea8a  nop
0x18000ea8b  mov     eax, ebx
0x18000ea8d  mov     rcx, [rbp+var_8]
0x18000ea91  xor     rcx, rsp; StackCookie
0x18000ea94  call    __security_check_cookie
0x18000ea99  mov     rbx, [rsp+60h+arg_0]
0x18000ea9e  mov     rsi, [rsp+60h+arg_8]
0x18000eaa3  add     rsp, 60h
0x18000eaa7  pop     rbp
0x18000eaa8  retn
```
