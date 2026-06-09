# UtilsDeleteRegistryTree(HKEY__ *,ushort const *)

- ea: `0x1800824d0`
- end: `0x1800826fc`
- name: `?UtilsDeleteRegistryTree@@YAJPEAUHKEY__@@PEBG@Z`
- size: `556`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18007ea20`

## callees

- `0x180008de0`
- `0x18000f0c8`
- `0x180019fd8`
- `0x18002031c`
- `0x180023f1c`
- `0x180023f6c`
- `0x180025824`
- `0x180025ac0`
- `0x18002dcc8`
- `0x1800824d0`
- `0x180083cec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180082538`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180082538`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18008267e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18008267e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180082643`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180082643`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800825c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800825c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall UtilsDeleteRegistryTree(HKEY hKey, LPCWSTR lpSubKey)
{
  int v4; // esi
  unsigned int v5; // ebx
  __int64 last_of; // rdi
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  bool v9; // cc
  const WCHAR *v10; // rax
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A8h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-A4h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-A0h] BYREF
  HKEY hKeya; // [rsp+70h] [rbp-98h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v17[32]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v18[32]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v19[32]; // [rsp+C0h] [rbp-48h] BYREF

  v4 = 0;
  v5 = 0;
  hKeya = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  std::wstring::wstring(v18, lpSubKey);
  std::wstring::wstring(v17, lpSubKey);
  RegDeleteTreeW(hKey, lpSubKey);
  while ( 1 )
  {
    last_of = std::wstring::find_last_of(v18);
    std::wstring::wstring(v19, v18, 0, last_of);
    std::wstring::operator=(v17, v19);
    std::wstring::~wstring(v19);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKeya,
      0);
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
    v8 = RegOpenKeyExW(hKey, v7, 0, 0xF003Fu, &hKeya);
    v9 = v8 <= 0;
    if ( v8 )
      break;
    v8 = RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    v9 = v8 <= 0;
    if ( v8 )
      break;
    if ( !cSubKeys && !cValues )
    {
      v4 |= 1u;
      v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
      RegDeleteKeyExW(hKey, v10, 0xF003Fu, 0);
      std::wstring::operator=(v18, v17);
      if ( last_of != -1 )
        continue;
    }
    goto LABEL_10;
  }
  if ( v9 )
    v5 = v8;
  else
    v5 = (unsigned __int16)v8 | 0x80070000;
LABEL_10:
  std::wstring::~wstring(v17);
  std::wstring::~wstring(v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
  return v5;
}

```

## disassembly

```asm
0x1800824d0  mov     r11, rsp
0x1800824d3  mov     [r11+18h], rbx
0x1800824d7  push    rsi
0x1800824d8  push    rdi
0x1800824d9  push    r14
0x1800824db  sub     rsp, 0F0h
0x1800824e2  mov     rax, cs:__security_cookie
0x1800824e9  xor     rax, rsp
0x1800824ec  mov     [rsp+108h+var_28], rax
0x1800824f4  mov     rdi, rdx
0x1800824f7  mov     r14, rcx
0x1800824fa  xor     esi, esi
0x1800824fc  mov     [rsp+108h+cbMaxSubKeyLen], esi
0x180082500  xor     ebx, ebx
0x180082502  mov     [rsp+108h+hKey], rbx
0x180082507  mov     [rsp+108h+cSubKeys], ebx
0x18008250b  mov     [rsp+108h+cbMaxSubKeyLen], ebx
0x18008250f  mov     [rsp+108h+cValues], ebx
0x180082513  mov     [rsp+108h+cbMaxValueNameLen], ebx
0x180082517  lea     rcx, [r11-68h]
0x18008251b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180082520  nop
0x180082521  mov     rdx, rdi
0x180082524  lea     rcx, [rsp+108h+var_88]
0x18008252c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180082531  nop
0x180082532  mov     rdx, rdi; lpSubKey
0x180082535  mov     rcx, r14; hKey
0x180082538  call    cs:__imp_RegDeleteTreeW
0x18008253f  nop     dword ptr [rax+rax+00h]
0x180082544  lea     rcx, [rsp+108h+var_68]
0x18008254c  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x180082551  mov     rdi, rax
0x180082554  mov     r9, rax
0x180082557  xor     r8d, r8d
0x18008255a  lea     rdx, [rsp+108h+var_68]
0x180082562  lea     rcx, [rsp+108h+var_48]
0x18008256a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x18008256f  lea     rdx, [rsp+108h+var_48]
0x180082577  lea     rcx, [rsp+108h+var_88]
0x18008257f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180082584  lea     rcx, [rsp+108h+var_48]
0x18008258c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180082591  xor     edx, edx
0x180082593  lea     rcx, [rsp+108h+hKey]
0x180082598  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008259d  lea     rcx, [rsp+108h+var_88]
0x1800825a5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800825aa  mov     rdx, rax; lpSubKey
0x1800825ad  lea     rax, [rsp+108h+hKey]
0x1800825b2  mov     [rsp+108h+phkResult], rax; phkResult
0x1800825b7  mov     r9d, 0F003Fh; samDesired
0x1800825bd  xor     r8d, r8d; ulOptions
0x1800825c0  mov     rcx, r14; hKey
0x1800825c3  call    cs:__imp_RegOpenKeyExW
0x1800825ca  nop     dword ptr [rax+rax+00h]
0x1800825cf  test    eax, eax
0x1800825d1  jz      short loc_1800825EA
0x1800825d3  jg      short loc_1800825DC
0x1800825d5  mov     ebx, eax
0x1800825d7  jmp     loc_1800826A9
0x1800825dc  movzx   ebx, ax
0x1800825df  or      ebx, 80070000h
0x1800825e5  jmp     loc_1800826A9
0x1800825ea  mov     [rsp+108h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800825f3  mov     [rsp+108h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800825fc  mov     [rsp+108h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180082605  lea     rax, [rsp+108h+cbMaxValueNameLen]
0x18008260a  mov     [rsp+108h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18008260f  lea     rax, [rsp+108h+cValues]
0x180082614  mov     [rsp+108h+lpcValues], rax; lpcValues
0x180082619  mov     [rsp+108h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180082622  lea     rax, [rsp+108h+cbMaxSubKeyLen]
0x180082627  mov     [rsp+108h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18008262c  lea     rax, [rsp+108h+cSubKeys]
0x180082631  mov     [rsp+108h+phkResult], rax; lpcSubKeys
0x180082636  xor     r9d, r9d; lpReserved
0x180082639  xor     r8d, r8d; lpcchClass
0x18008263c  xor     edx, edx; lpClass
0x18008263e  mov     rcx, [rsp+108h+hKey]; hKey
0x180082643  call    cs:__imp_RegQueryInfoKeyW
0x18008264a  nop     dword ptr [rax+rax+00h]
0x18008264f  test    eax, eax
0x180082651  jnz     short loc_1800825D3
0x180082653  cmp     [rsp+108h+cSubKeys], eax
0x180082657  jnz     short loc_1800826A9
0x180082659  cmp     [rsp+108h+cValues], eax
0x18008265d  jnz     short loc_1800826A9
0x18008265f  or      esi, 1
0x180082662  lea     rcx, [rsp+108h+var_88]
0x18008266a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008266f  mov     rdx, rax; lpSubKey
0x180082672  xor     r9d, r9d; Reserved
0x180082675  mov     r8d, 0F003Fh; samDesired
0x18008267b  mov     rcx, r14; hKey
0x18008267e  call    cs:__imp_RegDeleteKeyExW
0x180082685  nop     dword ptr [rax+rax+00h]
0x18008268a  lea     rdx, [rsp+108h+var_88]
0x180082692  lea     rcx, [rsp+108h+var_68]
0x18008269a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008269f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800826a3  jnz     loc_180082544
0x1800826a9  lea     rcx, [rsp+108h+var_88]
0x1800826b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800826b6  nop
0x1800826b7  lea     rcx, [rsp+108h+var_68]
0x1800826bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800826c4  nop
0x1800826c5  lea     rcx, [rsp+108h+hKey]
0x1800826ca  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800826cf  mov     eax, ebx
0x1800826d1  jmp     short loc_1800826D7
0x1800826d3  mov     eax, [rsp+108h+cbMaxSubKeyLen]
0x1800826d7  mov     rcx, [rsp+108h+var_28]
0x1800826df  xor     rcx, rsp; StackCookie
0x1800826e2  call    __security_check_cookie
0x1800826e7  mov     rbx, [rsp+108h+arg_10]
0x1800826ef  add     rsp, 0F0h
0x1800826f6  pop     r14
0x1800826f8  pop     rdi
0x1800826f9  pop     rsi
0x1800826fa  retn
```
