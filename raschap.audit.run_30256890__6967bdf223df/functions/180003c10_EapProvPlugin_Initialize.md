# EapProvPlugin_Initialize

- ea: `0x180003c10`
- end: `0x180003f97`
- name: `EapProvPlugin_Initialize`
- size: `903`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800042f0`

## callees

- `0x180003bd0`
- `0x180003c10`
- `0x180013b20`
- `0x180014610`
- `0x1800235ac`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003dd0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003dd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003e8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003e8f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003f46`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003f46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003cef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003d96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003cef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003d96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003c9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003c9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003f30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003f30`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003e3c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003e3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e9a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003d32`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003d32`

## string_xrefs

- `0x180003c90`: `SYSTEM\CurrentControlSet\Services\EapHost\Parameters\EapProvPlugin`
- `0x180003d74`: `DllEntryPoint`

## pseudocode

```c
__int64 EapProvPlugin_Initialize()
{
  DWORD LastError; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  int v3; // edx
  int v4; // r8d
  FARPROC ProcAddress; // rax
  DWORD cbData; // [rsp+40h] [rbp-768h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-760h] BYREF
  CHAR MultiByteStr[272]; // [rsp+50h] [rbp-758h] BYREF
  WCHAR v10[264]; // [rsp+160h] [rbp-648h] BYREF
  WCHAR Data[264]; // [rsp+370h] [rbp-438h] BYREF
  WCHAR Dst[264]; // [rsp+580h] [rbp-228h] BYREF

  hKey = 0;
  memset_0(Data, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  memset_0(v10, 0, 0x208u);
  cbData = 520;
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SYSTEM\\CurrentControlSet\\Services\\EapHost\\Parameters\\EapProvPlugin",
                0,
                1u,
                &hKey);
  if ( LastError )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 20;
    goto LABEL_28;
  }
  LastError = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &cbData);
  if ( LastError )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 21;
    goto LABEL_28;
  }
  if ( !ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 22;
    goto LABEL_28;
  }
  cbData = 520;
  LastError = RegQueryValueExW(hKey, L"DllEntryPoint", 0, 0, (LPBYTE)v10, &cbData);
  if ( LastError )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 23;
    goto LABEL_28;
  }
  g_hEapProvPluginDll = LoadLibraryExW(Dst, 0, 0);
  if ( !g_hEapProvPluginDll )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 24;
    goto LABEL_28;
  }
  if ( WideCharToMultiByte(0xFDE9u, 0, v10, -1, MultiByteStr, 260, 0, 0) )
  {
    ProcAddress = GetProcAddress(g_hEapProvPluginDll, MultiByteStr);
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v2 = 26;
      goto LABEL_28;
    }
    LastError = ((__int64 (__fastcall *)(__int64 (**)(void)))ProcAddress)(&g_EapProvPluginDllFunctionTable);
    if ( LastError )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v2 = 27;
      goto LABEL_28;
    }
    if ( g_EapProvPluginDllFunctionTable )
    {
      LastError = g_EapProvPluginDllFunctionTable();
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v2 = 28;
LABEL_28:
        WPP_SF_d(v1[2], v2, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, LastError);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, LastError, (__int64)v10);
  }
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  if ( LastError )
  {
    if ( g_hEapProvPluginDll )
    {
      FreeLibrary(g_hEapProvPluginDll);
      g_hEapProvPluginDll = 0;
    }
    *(_OWORD *)&g_EapProvPluginDllFunctionTable = 0;
    qword_1800339A8 = 0;
    xmmword_180033988 = 0;
    xmmword_180033998 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x180003c10  mov     [rsp+arg_0], rbx
0x180003c15  push    rdi
0x180003c16  sub     rsp, 7A0h
0x180003c1d  mov     rax, cs:__security_cookie
0x180003c24  xor     rax, rsp
0x180003c27  mov     [rsp+7A8h+var_18], rax
0x180003c2f  xor     edi, edi
0x180003c31  lea     rcx, [rsp+7A8h+Data]; void *
0x180003c39  xor     edx, edx; Val
0x180003c3b  mov     [rsp+7A8h+hKey], rdi
0x180003c40  mov     r8d, 208h; Size
0x180003c46  call    memset_0
0x180003c4b  xor     edx, edx; Val
0x180003c4d  lea     rcx, [rsp+7A8h+Dst]; void *
0x180003c55  mov     r8d, 208h; Size
0x180003c5b  call    memset_0
0x180003c60  xor     edx, edx; Val
0x180003c62  lea     rcx, [rsp+7A8h+var_648]; void *
0x180003c6a  mov     r8d, 208h; Size
0x180003c70  call    memset_0
0x180003c75  lea     rax, [rsp+7A8h+hKey]
0x180003c7a  mov     [rsp+7A8h+cbData], 208h
0x180003c82  mov     r9d, 1; samDesired
0x180003c88  mov     [rsp+7A8h+phkResult], rax; phkResult
0x180003c8d  xor     r8d, r8d; ulOptions
0x180003c90  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x180003c97  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003c9e  call    cs:__imp_RegOpenKeyExW
0x180003ca4  mov     ebx, eax
0x180003ca6  test    eax, eax
0x180003ca8  jz      short loc_180003CCB
0x180003caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cb1  lea     rax, WPP_GLOBAL_Control
0x180003cb8  cmp     rcx, rax
0x180003cbb  jz      loc_180003F26
0x180003cc1  mov     edx, 14h
0x180003cc6  jmp     loc_180003F13
0x180003ccb  mov     rcx, [rsp+7A8h+hKey]; hKey
0x180003cd0  lea     rax, [rsp+7A8h+cbData]
0x180003cd5  mov     [rsp+7A8h+lpcbData], rax; lpcbData
0x180003cda  xor     r9d, r9d; lpType
0x180003cdd  lea     rax, [rsp+7A8h+Data]
0x180003ce5  xor     r8d, r8d; lpReserved
0x180003ce8  xor     edx, edx; lpValueName
0x180003cea  mov     [rsp+7A8h+phkResult], rax; lpData
0x180003cef  call    cs:__imp_RegQueryValueExW
0x180003cf5  mov     ebx, eax
0x180003cf7  test    eax, eax
0x180003cf9  jz      short loc_180003D1C
0x180003cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d02  lea     rax, WPP_GLOBAL_Control
0x180003d09  cmp     rcx, rax
0x180003d0c  jz      loc_180003F26
0x180003d12  mov     edx, 15h
0x180003d17  jmp     loc_180003F13
0x180003d1c  mov     r8d, 104h; nSize
0x180003d22  lea     rdx, [rsp+7A8h+Dst]; lpDst
0x180003d2a  lea     rcx, [rsp+7A8h+Data]; lpSrc
0x180003d32  call    cs:__imp_ExpandEnvironmentStringsW
0x180003d38  test    eax, eax
0x180003d3a  jnz     short loc_180003D65
0x180003d3c  call    cs:__imp_GetLastError
0x180003d42  mov     ebx, eax
0x180003d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d4b  lea     rax, WPP_GLOBAL_Control
0x180003d52  cmp     rcx, rax
0x180003d55  jz      loc_180003F26
0x180003d5b  mov     edx, 16h
0x180003d60  jmp     loc_180003F13
0x180003d65  mov     rcx, [rsp+7A8h+hKey]; hKey
0x180003d6a  lea     rax, [rsp+7A8h+cbData]
0x180003d6f  mov     [rsp+7A8h+lpcbData], rax; lpcbData
0x180003d74  lea     rdx, ValueName; "DllEntryPoint"
0x180003d7b  lea     rax, [rsp+7A8h+var_648]
0x180003d83  mov     [rsp+7A8h+cbData], 208h
0x180003d8b  xor     r9d, r9d; lpType
0x180003d8e  mov     [rsp+7A8h+phkResult], rax; lpData
0x180003d93  xor     r8d, r8d; lpReserved
0x180003d96  call    cs:__imp_RegQueryValueExW
0x180003d9c  mov     ebx, eax
0x180003d9e  test    eax, eax
0x180003da0  jz      short loc_180003DC3
0x180003da2  mov     rcx, cs:WPP_GLOBAL_Control
0x180003da9  lea     rax, WPP_GLOBAL_Control
0x180003db0  cmp     rcx, rax
0x180003db3  jz      loc_180003F26
0x180003db9  mov     edx, 17h
0x180003dbe  jmp     loc_180003F13
0x180003dc3  xor     r8d, r8d; dwFlags
0x180003dc6  lea     rcx, [rsp+7A8h+Dst]; lpLibFileName
0x180003dce  xor     edx, edx; hFile
0x180003dd0  call    cs:__imp_LoadLibraryExW
0x180003dd6  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hEapProvPluginDll
0x180003ddd  test    rax, rax
0x180003de0  jnz     short loc_180003E0B
0x180003de2  call    cs:__imp_GetLastError
0x180003de8  mov     ebx, eax
0x180003dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180003df1  lea     rax, WPP_GLOBAL_Control
0x180003df8  cmp     rcx, rax
0x180003dfb  jz      loc_180003F26
0x180003e01  mov     edx, 18h
0x180003e06  jmp     loc_180003F13
0x180003e0b  mov     [rsp+7A8h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180003e10  lea     rax, [rsp+7A8h+MultiByteStr]
0x180003e15  mov     [rsp+7A8h+lpDefaultChar], rdi; lpDefaultChar
0x180003e1a  lea     r8, [rsp+7A8h+var_648]; lpWideCharStr
0x180003e22  mov     dword ptr [rsp+7A8h+lpcbData], 104h; cbMultiByte
0x180003e2a  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180003e30  xor     edx, edx; dwFlags
0x180003e32  mov     [rsp+7A8h+phkResult], rax; lpMultiByteStr
0x180003e37  mov     ecx, 0FDE9h; CodePage
0x180003e3c  call    cs:__imp_WideCharToMultiByte
0x180003e42  test    eax, eax
0x180003e44  jnz     short loc_180003E83
0x180003e46  call    cs:__imp_GetLastError
0x180003e4c  mov     ebx, eax
0x180003e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e55  lea     rax, WPP_GLOBAL_Control
0x180003e5c  cmp     rcx, rax
0x180003e5f  jz      loc_180003F26
0x180003e65  mov     rcx, [rcx+10h]
0x180003e69  lea     rax, [rsp+7A8h+var_648]
0x180003e71  mov     r9d, ebx
0x180003e74  mov     [rsp+7A8h+phkResult], rax
0x180003e79  call    WPP_SF_DS
0x180003e7e  jmp     loc_180003F26
0x180003e83  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hModule
0x180003e8a  lea     rdx, [rsp+7A8h+MultiByteStr]; lpProcName
0x180003e8f  call    cs:__imp_GetProcAddress
0x180003e95  test    rax, rax
0x180003e98  jnz     short loc_180003EBC
0x180003e9a  call    cs:__imp_GetLastError
0x180003ea0  mov     ebx, eax
0x180003ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ea9  lea     rax, WPP_GLOBAL_Control
0x180003eb0  cmp     rcx, rax
0x180003eb3  jz      short loc_180003F26
0x180003eb5  mov     edx, 1Ah
0x180003eba  jmp     short loc_180003F13
0x180003ebc  lea     rcx, ?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180003ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec8  mov     ebx, eax
0x180003eca  test    eax, eax
0x180003ecc  jz      short loc_180003EE8
0x180003ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ed5  lea     rax, WPP_GLOBAL_Control
0x180003edc  cmp     rcx, rax
0x180003edf  jz      short loc_180003F26
0x180003ee1  mov     edx, 1Bh
0x180003ee6  jmp     short loc_180003F13
0x180003ee8  mov     rax, qword ptr cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180003eef  test    rax, rax
0x180003ef2  jz      short loc_180003F26
0x180003ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ef9  mov     ebx, eax
0x180003efb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f02  lea     rax, WPP_GLOBAL_Control
0x180003f09  cmp     rcx, rax
0x180003f0c  jz      short loc_180003F26
0x180003f0e  mov     edx, 1Ch
0x180003f13  mov     rcx, [rcx+10h]
0x180003f17  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180003f1e  mov     r9d, ebx
0x180003f21  call    WPP_SF_d
0x180003f26  mov     rcx, [rsp+7A8h+hKey]; hKey
0x180003f2b  test    rcx, rcx
0x180003f2e  jz      short loc_180003F36
0x180003f30  call    cs:__imp_RegCloseKey
0x180003f36  test    ebx, ebx
0x180003f38  jz      short loc_180003F74
0x180003f3a  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x180003f41  test    rcx, rcx
0x180003f44  jz      short loc_180003F53
0x180003f46  call    cs:__imp_FreeLibrary
0x180003f4c  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hEapProvPluginDll
0x180003f53  xorps   xmm0, xmm0
0x180003f56  xor     eax, eax
0x180003f58  movups  cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A, xmm0; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180003f5f  mov     cs:qword_1800339A8, rax
0x180003f66  movups  cs:xmmword_180033988, xmm0
0x180003f6d  movups  cs:xmmword_180033998, xmm0
0x180003f74  mov     eax, ebx
0x180003f76  mov     rcx, [rsp+7A8h+var_18]
0x180003f7e  xor     rcx, rsp; StackCookie
0x180003f81  call    __security_check_cookie
0x180003f86  mov     rbx, [rsp+7A8h+arg_0]
0x180003f8e  add     rsp, 7A0h
0x180003f95  pop     rdi
0x180003f96  retn
```
