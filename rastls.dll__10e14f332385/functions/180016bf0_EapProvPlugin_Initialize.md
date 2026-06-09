# EapProvPlugin_Initialize

- ea: `0x180016bf0`
- end: `0x180016f83`
- name: `EapProvPlugin_Initialize`
- size: `915`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180005ac0`

## callees

- `0x180004bd0`
- `0x180016bf0`
- `0x180035680`
- `0x180036254`
- `0x18006564c`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016db0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016db0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016e7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016e7b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016f32`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016f32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016dc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016dc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e86`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180016e1c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180016e1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016f1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016f1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016c7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016c7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ccf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016d76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ccf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016d76`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180016d12`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180016d12`

## string_xrefs

- `0x180016c70`: `SYSTEM\CurrentControlSet\Services\EapHost\Parameters\EapProvPlugin`
- `0x180016d54`: `DllEntryPoint`

## pseudocode

```c
__int64 EapProvPlugin_Initialize()
{
  DWORD LastError; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v1; // rcx
  __int64 v2; // rdx
  FARPROC ProcAddress; // rax
  DWORD cbData; // [rsp+40h] [rbp-768h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-760h] BYREF
  CHAR MultiByteStr[272]; // [rsp+50h] [rbp-758h] BYREF
  WCHAR v8[264]; // [rsp+160h] [rbp-648h] BYREF
  WCHAR Data[264]; // [rsp+370h] [rbp-438h] BYREF
  WCHAR Dst[264]; // [rsp+580h] [rbp-228h] BYREF

  hKey = 0;
  memset_0(Data, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  memset_0(v8, 0, 0x208u);
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
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 20;
    goto LABEL_28;
  }
  LastError = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &cbData);
  if ( LastError )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 21;
    goto LABEL_28;
  }
  if ( !ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 22;
    goto LABEL_28;
  }
  cbData = 520;
  LastError = RegQueryValueExW(hKey, L"DllEntryPoint", 0, 0, (LPBYTE)v8, &cbData);
  if ( LastError )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 23;
    goto LABEL_28;
  }
  g_hEapProvPluginDll = LoadLibraryExW(Dst, 0, 0);
  if ( !g_hEapProvPluginDll )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 24;
    goto LABEL_28;
  }
  if ( WideCharToMultiByte(0xFDE9u, 0, v8, -1, MultiByteStr, 260, 0, 0) )
  {
    ProcAddress = GetProcAddress(g_hEapProvPluginDll, MultiByteStr);
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v2 = 26;
      goto LABEL_28;
    }
    LastError = ((__int64 (__fastcall *)(__int64 (**)(void)))ProcAddress)(&g_EapProvPluginDllFunctionTable);
    if ( LastError )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v2 = 27;
      goto LABEL_28;
    }
    if ( g_EapProvPluginDllFunctionTable )
    {
      LastError = g_EapProvPluginDllFunctionTable();
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v2 = 28;
LABEL_28:
        WPP_SF_d(*((_QWORD *)v1 + 2), v2, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, LastError);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids,
        LastError,
        (__int64)v8);
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
    qword_1800A5FC0 = 0;
    xmmword_1800A5FA0 = 0;
    xmmword_1800A5FB0 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x180016bf0  mov     [rsp+arg_0], rbx
0x180016bf5  push    rdi
0x180016bf6  sub     rsp, 7A0h
0x180016bfd  mov     rax, cs:__security_cookie
0x180016c04  xor     rax, rsp
0x180016c07  mov     [rsp+7A8h+var_18], rax
0x180016c0f  xor     edi, edi
0x180016c11  lea     rcx, [rsp+7A8h+Data]; void *
0x180016c19  xor     edx, edx; Val
0x180016c1b  mov     [rsp+7A8h+hKey], rdi
0x180016c20  mov     r8d, 208h; Size
0x180016c26  call    memset_0
0x180016c2b  xor     edx, edx; Val
0x180016c2d  lea     rcx, [rsp+7A8h+Dst]; void *
0x180016c35  mov     r8d, 208h; Size
0x180016c3b  call    memset_0
0x180016c40  xor     edx, edx; Val
0x180016c42  lea     rcx, [rsp+7A8h+var_648]; void *
0x180016c4a  mov     r8d, 208h; Size
0x180016c50  call    memset_0
0x180016c55  lea     rax, [rsp+7A8h+hKey]
0x180016c5a  mov     [rsp+7A8h+cbData], 208h
0x180016c62  mov     r9d, 1; samDesired
0x180016c68  mov     [rsp+7A8h+phkResult], rax; phkResult
0x180016c6d  xor     r8d, r8d; ulOptions
0x180016c70  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x180016c77  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016c7e  call    cs:__imp_RegOpenKeyExW
0x180016c84  mov     ebx, eax
0x180016c86  test    eax, eax
0x180016c88  jz      short loc_180016CAB
0x180016c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c91  lea     rax, WPP_GLOBAL_Control
0x180016c98  cmp     rcx, rax
0x180016c9b  jz      loc_180016F12
0x180016ca1  mov     edx, 14h
0x180016ca6  jmp     loc_180016EFF
0x180016cab  mov     rcx, [rsp+7A8h+hKey]; hKey
0x180016cb0  lea     rax, [rsp+7A8h+cbData]
0x180016cb5  mov     [rsp+7A8h+lpcbData], rax; lpcbData
0x180016cba  xor     r9d, r9d; lpType
0x180016cbd  lea     rax, [rsp+7A8h+Data]
0x180016cc5  xor     r8d, r8d; lpReserved
0x180016cc8  xor     edx, edx; lpValueName
0x180016cca  mov     [rsp+7A8h+phkResult], rax; lpData
0x180016ccf  call    cs:__imp_RegQueryValueExW
0x180016cd5  mov     ebx, eax
0x180016cd7  test    eax, eax
0x180016cd9  jz      short loc_180016CFC
0x180016cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ce2  lea     rax, WPP_GLOBAL_Control
0x180016ce9  cmp     rcx, rax
0x180016cec  jz      loc_180016F12
0x180016cf2  mov     edx, 15h
0x180016cf7  jmp     loc_180016EFF
0x180016cfc  mov     r8d, 104h; nSize
0x180016d02  lea     rdx, [rsp+7A8h+Dst]; lpDst
0x180016d0a  lea     rcx, [rsp+7A8h+Data]; lpSrc
0x180016d12  call    cs:__imp_ExpandEnvironmentStringsW
0x180016d18  test    eax, eax
0x180016d1a  jnz     short loc_180016D45
0x180016d1c  call    cs:__imp_GetLastError
0x180016d22  mov     ebx, eax
0x180016d24  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d2b  lea     rax, WPP_GLOBAL_Control
0x180016d32  cmp     rcx, rax
0x180016d35  jz      loc_180016F12
0x180016d3b  mov     edx, 16h
0x180016d40  jmp     loc_180016EFF
0x180016d45  mov     rcx, [rsp+7A8h+hKey]; hKey
0x180016d4a  lea     rax, [rsp+7A8h+cbData]
0x180016d4f  mov     [rsp+7A8h+lpcbData], rax; lpcbData
0x180016d54  lea     rdx, aDllentrypoint; "DllEntryPoint"
0x180016d5b  lea     rax, [rsp+7A8h+var_648]
0x180016d63  mov     [rsp+7A8h+cbData], 208h
0x180016d6b  xor     r9d, r9d; lpType
0x180016d6e  mov     [rsp+7A8h+phkResult], rax; lpData
0x180016d73  xor     r8d, r8d; lpReserved
0x180016d76  call    cs:__imp_RegQueryValueExW
0x180016d7c  mov     ebx, eax
0x180016d7e  test    eax, eax
0x180016d80  jz      short loc_180016DA3
0x180016d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d89  lea     rax, WPP_GLOBAL_Control
0x180016d90  cmp     rcx, rax
0x180016d93  jz      loc_180016F12
0x180016d99  mov     edx, 17h
0x180016d9e  jmp     loc_180016EFF
0x180016da3  xor     r8d, r8d; dwFlags
0x180016da6  lea     rcx, [rsp+7A8h+Dst]; lpLibFileName
0x180016dae  xor     edx, edx; hFile
0x180016db0  call    cs:__imp_LoadLibraryExW
0x180016db6  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hEapProvPluginDll
0x180016dbd  test    rax, rax
0x180016dc0  jnz     short loc_180016DEB
0x180016dc2  call    cs:__imp_GetLastError
0x180016dc8  mov     ebx, eax
0x180016dca  mov     rcx, cs:WPP_GLOBAL_Control
0x180016dd1  lea     rax, WPP_GLOBAL_Control
0x180016dd8  cmp     rcx, rax
0x180016ddb  jz      loc_180016F12
0x180016de1  mov     edx, 18h
0x180016de6  jmp     loc_180016EFF
0x180016deb  mov     [rsp+7A8h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180016df0  lea     rax, [rsp+7A8h+MultiByteStr]
0x180016df5  mov     [rsp+7A8h+lpDefaultChar], rdi; lpDefaultChar
0x180016dfa  lea     r8, [rsp+7A8h+var_648]; lpWideCharStr
0x180016e02  mov     dword ptr [rsp+7A8h+lpcbData], 104h; cbMultiByte
0x180016e0a  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180016e10  xor     edx, edx; dwFlags
0x180016e12  mov     [rsp+7A8h+phkResult], rax; lpMultiByteStr
0x180016e17  mov     ecx, 0FDE9h; CodePage
0x180016e1c  call    cs:__imp_WideCharToMultiByte
0x180016e22  test    eax, eax
0x180016e24  jnz     short loc_180016E6F
0x180016e26  call    cs:__imp_GetLastError
0x180016e2c  mov     ebx, eax
0x180016e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e35  lea     rax, WPP_GLOBAL_Control
0x180016e3c  cmp     rcx, rax
0x180016e3f  jz      loc_180016F12
0x180016e45  mov     rcx, [rcx+10h]
0x180016e49  lea     rax, [rsp+7A8h+var_648]
0x180016e51  mov     edx, 19h
0x180016e56  mov     [rsp+7A8h+phkResult], rax
0x180016e5b  mov     r9d, ebx
0x180016e5e  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180016e65  call    WPP_SF_DS
0x180016e6a  jmp     loc_180016F12
0x180016e6f  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hModule
0x180016e76  lea     rdx, [rsp+7A8h+MultiByteStr]; lpProcName
0x180016e7b  call    cs:__imp_GetProcAddress
0x180016e81  test    rax, rax
0x180016e84  jnz     short loc_180016EA8
0x180016e86  call    cs:__imp_GetLastError
0x180016e8c  mov     ebx, eax
0x180016e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e95  lea     rax, WPP_GLOBAL_Control
0x180016e9c  cmp     rcx, rax
0x180016e9f  jz      short loc_180016F12
0x180016ea1  mov     edx, 1Ah
0x180016ea6  jmp     short loc_180016EFF
0x180016ea8  lea     rcx, ?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180016eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016eb4  mov     ebx, eax
0x180016eb6  test    eax, eax
0x180016eb8  jz      short loc_180016ED4
0x180016eba  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ec1  lea     rax, WPP_GLOBAL_Control
0x180016ec8  cmp     rcx, rax
0x180016ecb  jz      short loc_180016F12
0x180016ecd  mov     edx, 1Bh
0x180016ed2  jmp     short loc_180016EFF
0x180016ed4  mov     rax, qword ptr cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180016edb  test    rax, rax
0x180016ede  jz      short loc_180016F12
0x180016ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ee5  mov     ebx, eax
0x180016ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180016eee  lea     rax, WPP_GLOBAL_Control
0x180016ef5  cmp     rcx, rax
0x180016ef8  jz      short loc_180016F12
0x180016efa  mov     edx, 1Ch
0x180016eff  mov     rcx, [rcx+10h]
0x180016f03  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180016f0a  mov     r9d, ebx
0x180016f0d  call    WPP_SF_d
0x180016f12  mov     rcx, [rsp+7A8h+hKey]; hKey
0x180016f17  test    rcx, rcx
0x180016f1a  jz      short loc_180016F22
0x180016f1c  call    cs:__imp_RegCloseKey
0x180016f22  test    ebx, ebx
0x180016f24  jz      short loc_180016F60
0x180016f26  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x180016f2d  test    rcx, rcx
0x180016f30  jz      short loc_180016F3F
0x180016f32  call    cs:__imp_FreeLibrary
0x180016f38  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hEapProvPluginDll
0x180016f3f  xorps   xmm0, xmm0
0x180016f42  xor     eax, eax
0x180016f44  movups  cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A, xmm0; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180016f4b  mov     cs:qword_1800A5FC0, rax
0x180016f52  movups  cs:xmmword_1800A5FA0, xmm0
0x180016f59  movups  cs:xmmword_1800A5FB0, xmm0
0x180016f60  mov     eax, ebx
0x180016f62  mov     rcx, [rsp+7A8h+var_18]
0x180016f6a  xor     rcx, rsp; StackCookie
0x180016f6d  call    __security_check_cookie
0x180016f72  mov     rbx, [rsp+7A8h+arg_0]
0x180016f7a  add     rsp, 7A0h
0x180016f81  pop     rdi
0x180016f82  retn
```
