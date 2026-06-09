# DmIsNgcCertPayloadReceived

- ea: `0x1800b8f38`
- end: `0x1800b9380`
- name: `DmIsNgcCertPayloadReceived`
- size: `1096`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003de20`

## callees

- `0x18001378c`
- `0x18002b9b4`
- `0x18002dd24`
- `0x180043e34`
- `0x180044300`
- `0x180044d30`
- `0x1800b8ef4`
- `0x1800b8f18`
- `0x1800b8f38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b906d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b912f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b92c0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b931c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b906d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b912f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b92c0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b931c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b8ff2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b90b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b91d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b8ff2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b90b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b91d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b9234`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b9234`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800b8f8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800b8f8e`

## string_xrefs

- `0x1800b916f`: `Install`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall DmIsNgcCertPayloadReceived(_BYTE *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // r8d
  unsigned int v4; // eax
  unsigned int v5; // r8d
  DWORD v6; // r14d
  LSTATUS v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // r8d
  DWORD v10; // esi
  const WCHAR *v11; // rdx
  LSTATUS v12; // ebx
  unsigned int v14; // [rsp+20h] [rbp-AE8h]
  unsigned int v15; // [rsp+20h] [rbp-AE8h]
  unsigned int v16; // [rsp+20h] [rbp-AE8h]
  DWORD v17; // [rsp+40h] [rbp-AC8h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-AC4h] BYREF
  DWORD Type; // [rsp+48h] [rbp-AC0h] BYREF
  HKEY v20; // [rsp+50h] [rbp-AB8h] BYREF
  HKEY v21; // [rsp+58h] [rbp-AB0h] BYREF
  HKEY *p_hKey; // [rsp+60h] [rbp-AA8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-AA0h] BYREF
  char v24; // [rsp+70h] [rbp-A98h]
  BYTE Data[8]; // [rsp+78h] [rbp-A90h] BYREF
  HKEY v26; // [rsp+80h] [rbp-A88h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-A80h] BYREF
  DWORD cbData; // [rsp+90h] [rbp-A78h] BYREF
  LPCWSTR lpSubKey[5]; // [rsp+98h] [rbp-A70h] BYREF
  WCHAR Name; // [rsp+C0h] [rbp-A48h] BYREF
  _BYTE v31[526]; // [rsp+C2h] [rbp-A46h] BYREF
  WCHAR v32; // [rsp+2D0h] [rbp-838h] BYREF
  _BYTE v33[2062]; // [rsp+2D2h] [rbp-836h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B08h] [rbp+0h]

  hKey = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v24 = 1;
  v2 = RegOpenCurrentUser(0x20019u, &phkResult);
  if ( v2 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x20, v3, (const char *)v2, v14);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  v21 = 0;
  p_hKey = &v21;
  phkResult = 0;
  v24 = 1;
  v4 = RegOpenKeyExW(hKey, L"Software\\Microsoft\\SCEP\\", 0, 0x20019u, &phkResult);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x24, v5, (const char *)v4, v15);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  v6 = 0;
  cchName = 261;
  Name = 0;
  memset_0(v31, 0, 0x208u);
  v7 = RegEnumKeyExW(v21, 0, &Name, &cchName, 0, 0, 0, 0);
  while ( !v7 )
  {
    v20 = 0;
    p_hKey = &v20;
    phkResult = 0;
    v24 = 1;
    v8 = RegOpenKeyExW(v21, &Name, 0, 0x20019u, &phkResult);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x32, v9, (const char *)v8, v16);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    v10 = 0;
    v17 = 1025;
    v32 = 0;
    memset_0(v33, 0, 0x800u);
    RegEnumKeyExW(v20, 0, &v32, &v17, 0, 0, 0, 0);
    while ( !v7 )
    {
      std::wstring::wstring((__int64)lpSubKey, (__int64)&v32);
      std::wstring::_Append<unsigned short>(lpSubKey);
      std::wstring::_Append<unsigned short>(lpSubKey);
      v26 = 0;
      p_hKey = &v26;
      phkResult = 0;
      v24 = 1;
      v11 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v11 = lpSubKey[0];
      v12 = RegOpenKeyExW(v20, v11, 0, 0x20019u, &phkResult);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
      if ( !v12 )
      {
        *(_DWORD *)Data = 0;
        Type = 4;
        cbData = 4;
        if ( !RegQueryValueExW(v26, L"KeyProtection", 0, &Type, Data, &cbData) && *(_DWORD *)Data == 4 )
        {
          *a1 = 1;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
          std::wstring::_Tidy_deallocate((__int64)lpSubKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return 0;
        }
      }
      ++v10;
      v17 = 1025;
      v7 = RegEnumKeyExW(v20, v10, &v32, &v17, 0, 0, 0, 0);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      std::wstring::_Tidy_deallocate((__int64)lpSubKey);
    }
    ++v6;
    cchName = 261;
    v7 = RegEnumKeyExW(v21, v6, &Name, &cchName, 0, 0, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
  }
  *a1 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1800b8f38  mov     r11, rsp
0x1800b8f3b  mov     [r11+10h], rbx
0x1800b8f3f  mov     [r11+18h], rsi
0x1800b8f43  push    rdi
0x1800b8f44  push    r14
0x1800b8f46  push    r15
0x1800b8f48  sub     rsp, 0AF0h
0x1800b8f4f  mov     rax, cs:__security_cookie
0x1800b8f56  xor     rax, rsp
0x1800b8f59  mov     [rsp+0B08h+var_28], rax
0x1800b8f61  mov     rdi, rcx
0x1800b8f64  xor     r15d, r15d
0x1800b8f67  mov     [r11-0A80h], r15
0x1800b8f6e  lea     rax, [r11-0A80h]
0x1800b8f75  mov     [rsp+0B08h+var_AA8], rax
0x1800b8f7a  mov     [rsp+0B08h+phkResult], r15
0x1800b8f7f  mov     [rsp+0B08h+var_A98], 1
0x1800b8f84  lea     rdx, [rsp+0B08h+phkResult]; phkResult
0x1800b8f89  mov     ecx, 20019h; samDesired
0x1800b8f8e  call    cs:__imp_RegOpenCurrentUser
0x1800b8f94  mov     rcx, [rsp+0B08h]; this
0x1800b8f9c  test    eax, eax
0x1800b8f9e  jz      short loc_1800B8FAD
0x1800b8fa0  mov     r9d, eax; char *
0x1800b8fa3  lea     edx, [r15+20h]; void *
0x1800b8fa7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b8fad  lea     rcx, [rsp+0B08h+var_AA8]
0x1800b8fb2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800b8fb7  mov     [rsp+0B08h+var_AB0], r15
0x1800b8fbc  lea     rax, [rsp+0B08h+var_AB0]
0x1800b8fc1  mov     [rsp+0B08h+var_AA8], rax
0x1800b8fc6  mov     [rsp+0B08h+phkResult], r15
0x1800b8fcb  mov     [rsp+0B08h+var_A98], 1
0x1800b8fd0  lea     rax, [rsp+0B08h+phkResult]
0x1800b8fd5  mov     [rsp+0B08h+var_AE8], rax; unsigned int
0x1800b8fda  mov     r9d, 20019h; samDesired
0x1800b8fe0  xor     r8d, r8d; ulOptions
0x1800b8fe3  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\SCEP\\"
0x1800b8fea  mov     rcx, [rsp+0B08h+hKey]; hKey
0x1800b8ff2  call    cs:__imp_RegOpenKeyExW
0x1800b8ff8  mov     rcx, [rsp+0B08h]; this
0x1800b9000  test    eax, eax
0x1800b9002  jz      short loc_1800B9012
0x1800b9004  mov     r9d, eax; char *
0x1800b9007  mov     edx, 24h ; '$'; void *
0x1800b900c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b9012  lea     rcx, [rsp+0B08h+var_AA8]
0x1800b9017  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800b901c  mov     r14d, r15d
0x1800b901f  mov     [rsp+0B08h+cchName], 105h
0x1800b9027  mov     [rsp+0B08h+Name], r15w
0x1800b9030  xor     edx, edx; Val
0x1800b9032  mov     r8d, 208h; Size
0x1800b9038  lea     rcx, [rsp+0B08h+var_A46]; void *
0x1800b9040  call    memset_0
0x1800b9045  mov     [rsp+0B08h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800b904a  mov     [rsp+0B08h+lpcchClass], r15; lpcchClass
0x1800b904f  mov     [rsp+0B08h+lpClass], r15; lpClass
0x1800b9054  mov     [rsp+0B08h+var_AE8], r15; lpReserved
0x1800b9059  lea     r9, [rsp+0B08h+cchName]; lpcchName
0x1800b905e  lea     r8, [rsp+0B08h+Name]; lpName
0x1800b9066  xor     edx, edx; dwIndex
0x1800b9068  mov     rcx, [rsp+0B08h+var_AB0]; hKey
0x1800b906d  call    cs:__imp_RegEnumKeyExW
0x1800b9073  mov     ebx, eax
0x1800b9075  test    ebx, ebx
0x1800b9077  jnz     loc_1800B9333
0x1800b907d  mov     [rsp+0B08h+var_AB8], r15
0x1800b9082  lea     rax, [rsp+0B08h+var_AB8]
0x1800b9087  mov     [rsp+0B08h+var_AA8], rax
0x1800b908c  mov     [rsp+0B08h+phkResult], r15
0x1800b9091  mov     [rsp+0B08h+var_A98], 1
0x1800b9096  lea     rax, [rsp+0B08h+phkResult]
0x1800b909b  mov     [rsp+0B08h+var_AE8], rax; unsigned int
0x1800b90a0  mov     r9d, 20019h; samDesired
0x1800b90a6  xor     r8d, r8d; ulOptions
0x1800b90a9  lea     rdx, [rsp+0B08h+Name]; lpSubKey
0x1800b90b1  mov     rcx, [rsp+0B08h+var_AB0]; hKey
0x1800b90b6  call    cs:__imp_RegOpenKeyExW
0x1800b90bc  mov     rcx, [rsp+0B08h]; this
0x1800b90c4  test    eax, eax
0x1800b90c6  jz      short loc_1800B90D4
0x1800b90c8  mov     r9d, eax; char *
0x1800b90cb  lea     edx, [rbx+32h]; void *
0x1800b90ce  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b90d4  lea     rcx, [rsp+0B08h+var_AA8]
0x1800b90d9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800b90de  mov     esi, r15d
0x1800b90e1  mov     [rsp+0B08h+var_AC8], 401h
0x1800b90e9  mov     [rsp+0B08h+var_838], r15w
0x1800b90f2  xor     edx, edx; Val
0x1800b90f4  mov     r8d, 800h; Size
0x1800b90fa  lea     rcx, [rsp+0B08h+var_836]; void *
0x1800b9102  call    memset_0
0x1800b9107  mov     [rsp+0B08h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800b910c  mov     [rsp+0B08h+lpcchClass], r15; lpcchClass
0x1800b9111  mov     [rsp+0B08h+lpClass], r15; lpClass
0x1800b9116  mov     [rsp+0B08h+var_AE8], r15; lpReserved
0x1800b911b  lea     r9, [rsp+0B08h+var_AC8]; lpcchName
0x1800b9120  lea     r8, [rsp+0B08h+var_838]; lpName
0x1800b9128  xor     edx, edx; dwIndex
0x1800b912a  mov     rcx, [rsp+0B08h+var_AB8]; hKey
0x1800b912f  call    cs:__imp_RegEnumKeyExW
0x1800b9135  test    ebx, ebx
0x1800b9137  jnz     loc_1800B92E8
0x1800b913d  lea     rdx, [rsp+0B08h+var_838]
0x1800b9145  lea     rcx, [rsp+0B08h+lpSubKey]
0x1800b914d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b9152  nop
0x1800b9153  lea     r8d, [rbx+1]
0x1800b9157  lea     rdx, asc_1800D720C; "\\"
0x1800b915e  lea     rcx, [rsp+0B08h+lpSubKey]; Src
0x1800b9166  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b916b  lea     r8d, [rbx+7]
0x1800b916f  lea     rdx, aInstall; "Install"
0x1800b9176  lea     rcx, [rsp+0B08h+lpSubKey]; Src
0x1800b917e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b9183  mov     [rsp+0B08h+var_A88], r15
0x1800b918b  lea     rax, [rsp+0B08h+var_A88]
0x1800b9193  mov     [rsp+0B08h+var_AA8], rax
0x1800b9198  mov     [rsp+0B08h+phkResult], r15
0x1800b919d  mov     [rsp+0B08h+var_A98], 1
0x1800b91a2  lea     rdx, [rsp+0B08h+lpSubKey]
0x1800b91aa  cmp     [rsp+0B08h+var_A58], 7
0x1800b91b3  cmova   rdx, [rsp+0B08h+lpSubKey]; lpSubKey
0x1800b91bc  lea     rax, [rsp+0B08h+phkResult]
0x1800b91c1  mov     [rsp+0B08h+var_AE8], rax; phkResult
0x1800b91c6  mov     r9d, 20019h; samDesired
0x1800b91cc  xor     r8d, r8d; ulOptions
0x1800b91cf  mov     rcx, [rsp+0B08h+var_AB8]; hKey
0x1800b91d4  call    cs:__imp_RegOpenKeyExW
0x1800b91da  mov     ebx, eax
0x1800b91dc  lea     rcx, [rsp+0B08h+var_AA8]
0x1800b91e1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800b91e6  test    ebx, ebx
0x1800b91e8  jnz     loc_1800B928E
0x1800b91ee  mov     dword ptr [rsp+0B08h+Data], r15d
0x1800b91f3  mov     [rsp+0B08h+Type], 4
0x1800b91fb  mov     [rsp+0B08h+cbData], 4
0x1800b9206  lea     rax, [rsp+0B08h+cbData]
0x1800b920e  mov     [rsp+0B08h+lpClass], rax; lpcbData
0x1800b9213  lea     rax, [rsp+0B08h+Data]
0x1800b9218  mov     [rsp+0B08h+var_AE8], rax; lpData
0x1800b921d  lea     r9, [rsp+0B08h+Type]; lpType
0x1800b9222  xor     r8d, r8d; lpReserved
0x1800b9225  lea     rdx, aKeyprotection; "KeyProtection"
0x1800b922c  mov     rcx, [rsp+0B08h+var_A88]; hKey
0x1800b9234  call    cs:__imp_RegQueryValueExW
0x1800b923a  test    eax, eax
0x1800b923c  jnz     short loc_1800B928E
0x1800b923e  cmp     dword ptr [rsp+0B08h+Data], 4
0x1800b9243  jnz     short loc_1800B928E
0x1800b9245  mov     byte ptr [rdi], 1
0x1800b9248  lea     rcx, [rsp+0B08h+var_A88]
0x1800b9250  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b9255  nop
0x1800b9256  lea     rcx, [rsp+0B08h+lpSubKey]
0x1800b925e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b9263  nop
0x1800b9264  lea     rcx, [rsp+0B08h+var_AB8]
0x1800b9269  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b926e  nop
0x1800b926f  lea     rcx, [rsp+0B08h+var_AB0]
0x1800b9274  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b9279  nop
0x1800b927a  lea     rcx, [rsp+0B08h+hKey]
0x1800b9282  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b9287  xor     eax, eax
0x1800b9289  jmp     loc_1800B9356
0x1800b928e  inc     esi
0x1800b9290  mov     [rsp+0B08h+var_AC8], 401h
0x1800b9298  mov     [rsp+0B08h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800b929d  mov     [rsp+0B08h+lpcchClass], r15; lpcchClass
0x1800b92a2  mov     [rsp+0B08h+lpClass], r15; lpClass
0x1800b92a7  mov     [rsp+0B08h+var_AE8], r15; lpReserved
0x1800b92ac  lea     r9, [rsp+0B08h+var_AC8]; lpcchName
0x1800b92b1  lea     r8, [rsp+0B08h+var_838]; lpName
0x1800b92b9  mov     edx, esi; dwIndex
0x1800b92bb  mov     rcx, [rsp+0B08h+var_AB8]; hKey
0x1800b92c0  call    cs:__imp_RegEnumKeyExW
0x1800b92c6  mov     ebx, eax
0x1800b92c8  lea     rcx, [rsp+0B08h+var_A88]
0x1800b92d0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b92d5  nop
0x1800b92d6  lea     rcx, [rsp+0B08h+lpSubKey]
0x1800b92de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b92e3  jmp     loc_1800B9135
0x1800b92e8  inc     r14d
0x1800b92eb  mov     [rsp+0B08h+cchName], 105h
0x1800b92f3  mov     [rsp+0B08h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800b92f8  mov     [rsp+0B08h+lpcchClass], r15; lpcchClass
0x1800b92fd  mov     [rsp+0B08h+lpClass], r15; lpClass
0x1800b9302  mov     [rsp+0B08h+var_AE8], r15; lpReserved
0x1800b9307  lea     r9, [rsp+0B08h+cchName]; lpcchName
0x1800b930c  lea     r8, [rsp+0B08h+Name]; lpName
0x1800b9314  mov     edx, r14d; dwIndex
0x1800b9317  mov     rcx, [rsp+0B08h+var_AB0]; hKey
0x1800b931c  call    cs:__imp_RegEnumKeyExW
0x1800b9322  mov     ebx, eax
0x1800b9324  lea     rcx, [rsp+0B08h+var_AB8]
0x1800b9329  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b932e  jmp     loc_1800B9075
0x1800b9333  mov     [rdi], r15b
0x1800b9336  lea     rcx, [rsp+0B08h+var_AB0]
0x1800b933b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b9340  nop
0x1800b9341  lea     rcx, [rsp+0B08h+hKey]
0x1800b9349  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b934e  xor     eax, eax
0x1800b9350  jmp     short loc_1800B9356
0x1800b9352  mov     eax, [rsp+0B08h+Type]
0x1800b9356  mov     rcx, [rsp+0B08h+var_28]
0x1800b935e  xor     rcx, rsp; StackCookie
0x1800b9361  call    __security_check_cookie
0x1800b9366  lea     r11, [rsp+0B08h+var_18]
0x1800b936e  mov     rbx, [r11+28h]
0x1800b9372  mov     rsi, [r11+30h]
0x1800b9376  mov     rsp, r11
0x1800b9379  pop     r15
0x1800b937b  pop     r14
0x1800b937d  pop     rdi
0x1800b937e  retn
```
