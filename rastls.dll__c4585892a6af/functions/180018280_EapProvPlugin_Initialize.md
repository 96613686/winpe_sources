# EapProvPlugin_Initialize

- ea: `0x180018280`
- end: `0x180018662`
- name: `EapProvPlugin_Initialize`
- size: `994`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180005f80`

## callees

- `0x180005010`
- `0x180018280`
- `0x180038270`
- `0x180038e64`
- `0x180069258`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001845e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001845e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018541`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018541`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001860a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001860a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018552`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800184d6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800184d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800185ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800185ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001830e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001830e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018365`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001841e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018365`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001841e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800183ae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800183ae`

## string_xrefs

- `0x180018300`: `SYSTEM\CurrentControlSet\Services\EapHost\Parameters\EapProvPlugin`
- `0x1800183fc`: `DllEntryPoint`

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
    qword_1800AC090 = 0;
    xmmword_1800AC070 = 0;
    xmmword_1800AC080 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x180018280  mov     [rsp+arg_0], rbx
0x180018285  push    rdi
0x180018286  sub     rsp, 7A0h
0x18001828d  mov     rax, cs:__security_cookie
0x180018294  xor     rax, rsp
0x180018297  mov     [rsp+7A8h+var_18], rax
0x18001829f  xor     edi, edi
0x1800182a1  lea     rcx, [rsp+7A8h+Data]; void *
0x1800182a9  xor     edx, edx; Val
0x1800182ab  mov     [rsp+7A8h+hKey], rdi
0x1800182b0  mov     r8d, 208h; Size
0x1800182b6  call    memset_0
0x1800182bb  xor     edx, edx; Val
0x1800182bd  lea     rcx, [rsp+7A8h+Dst]; void *
0x1800182c5  mov     r8d, 208h; Size
0x1800182cb  call    memset_0
0x1800182d0  xor     edx, edx; Val
0x1800182d2  lea     rcx, [rsp+7A8h+var_648]; void *
0x1800182da  mov     r8d, 208h; Size
0x1800182e0  call    memset_0
0x1800182e5  lea     rax, [rsp+7A8h+hKey]
0x1800182ea  mov     [rsp+7A8h+cbData], 208h
0x1800182f2  mov     r9d, 1; samDesired
0x1800182f8  mov     [rsp+7A8h+phkResult], rax; phkResult
0x1800182fd  xor     r8d, r8d; ulOptions
0x180018300  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x180018307  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001830e  call    cs:__imp_RegOpenKeyExW
0x180018315  nop     dword ptr [rax+rax+00h]
0x18001831a  mov     ebx, eax
0x18001831c  test    eax, eax
0x18001831e  jz      short loc_180018341
0x180018320  mov     rcx, cs:WPP_GLOBAL_Control
0x180018327  lea     rax, WPP_GLOBAL_Control
0x18001832e  cmp     rcx, rax
0x180018331  jz      loc_1800185E4
0x180018337  mov     edx, 14h
0x18001833c  jmp     loc_1800185D1
0x180018341  mov     rcx, [rsp+7A8h+hKey]; hKey
0x180018346  lea     rax, [rsp+7A8h+cbData]
0x18001834b  mov     [rsp+7A8h+lpcbData], rax; lpcbData
0x180018350  xor     r9d, r9d; lpType
0x180018353  lea     rax, [rsp+7A8h+Data]
0x18001835b  xor     r8d, r8d; lpReserved
0x18001835e  xor     edx, edx; lpValueName
0x180018360  mov     [rsp+7A8h+phkResult], rax; lpData
0x180018365  call    cs:__imp_RegQueryValueExW
0x18001836c  nop     dword ptr [rax+rax+00h]
0x180018371  mov     ebx, eax
0x180018373  test    eax, eax
0x180018375  jz      short loc_180018398
0x180018377  mov     rcx, cs:WPP_GLOBAL_Control
0x18001837e  lea     rax, WPP_GLOBAL_Control
0x180018385  cmp     rcx, rax
0x180018388  jz      loc_1800185E4
0x18001838e  mov     edx, 15h
0x180018393  jmp     loc_1800185D1
0x180018398  mov     r8d, 104h; nSize
0x18001839e  lea     rdx, [rsp+7A8h+Dst]; lpDst
0x1800183a6  lea     rcx, [rsp+7A8h+Data]; lpSrc
0x1800183ae  call    cs:__imp_ExpandEnvironmentStringsW
0x1800183b5  nop     dword ptr [rax+rax+00h]
0x1800183ba  test    eax, eax
0x1800183bc  jnz     short loc_1800183ED
0x1800183be  call    cs:__imp_GetLastError
0x1800183c5  nop     dword ptr [rax+rax+00h]
0x1800183ca  mov     ebx, eax
0x1800183cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183d3  lea     rax, WPP_GLOBAL_Control
0x1800183da  cmp     rcx, rax
0x1800183dd  jz      loc_1800185E4
0x1800183e3  mov     edx, 16h
0x1800183e8  jmp     loc_1800185D1
0x1800183ed  mov     rcx, [rsp+7A8h+hKey]; hKey
0x1800183f2  lea     rax, [rsp+7A8h+cbData]
0x1800183f7  mov     [rsp+7A8h+lpcbData], rax; lpcbData
0x1800183fc  lea     rdx, aDllentrypoint; "DllEntryPoint"
0x180018403  lea     rax, [rsp+7A8h+var_648]
0x18001840b  mov     [rsp+7A8h+cbData], 208h
0x180018413  xor     r9d, r9d; lpType
0x180018416  mov     [rsp+7A8h+phkResult], rax; lpData
0x18001841b  xor     r8d, r8d; lpReserved
0x18001841e  call    cs:__imp_RegQueryValueExW
0x180018425  nop     dword ptr [rax+rax+00h]
0x18001842a  mov     ebx, eax
0x18001842c  test    eax, eax
0x18001842e  jz      short loc_180018451
0x180018430  mov     rcx, cs:WPP_GLOBAL_Control
0x180018437  lea     rax, WPP_GLOBAL_Control
0x18001843e  cmp     rcx, rax
0x180018441  jz      loc_1800185E4
0x180018447  mov     edx, 17h
0x18001844c  jmp     loc_1800185D1
0x180018451  xor     r8d, r8d; dwFlags
0x180018454  lea     rcx, [rsp+7A8h+Dst]; lpLibFileName
0x18001845c  xor     edx, edx; hFile
0x18001845e  call    cs:__imp_LoadLibraryExW
0x180018465  nop     dword ptr [rax+rax+00h]
0x18001846a  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hEapProvPluginDll
0x180018471  test    rax, rax
0x180018474  jnz     short loc_1800184A5
0x180018476  call    cs:__imp_GetLastError
0x18001847d  nop     dword ptr [rax+rax+00h]
0x180018482  mov     ebx, eax
0x180018484  mov     rcx, cs:WPP_GLOBAL_Control
0x18001848b  lea     rax, WPP_GLOBAL_Control
0x180018492  cmp     rcx, rax
0x180018495  jz      loc_1800185E4
0x18001849b  mov     edx, 18h
0x1800184a0  jmp     loc_1800185D1
0x1800184a5  mov     [rsp+7A8h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800184aa  lea     rax, [rsp+7A8h+MultiByteStr]
0x1800184af  mov     [rsp+7A8h+lpDefaultChar], rdi; lpDefaultChar
0x1800184b4  lea     r8, [rsp+7A8h+var_648]; lpWideCharStr
0x1800184bc  mov     dword ptr [rsp+7A8h+lpcbData], 104h; cbMultiByte
0x1800184c4  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1800184ca  xor     edx, edx; dwFlags
0x1800184cc  mov     [rsp+7A8h+phkResult], rax; lpMultiByteStr
0x1800184d1  mov     ecx, 0FDE9h; CodePage
0x1800184d6  call    cs:__imp_WideCharToMultiByte
0x1800184dd  nop     dword ptr [rax+rax+00h]
0x1800184e2  test    eax, eax
0x1800184e4  jnz     short loc_180018535
0x1800184e6  call    cs:__imp_GetLastError
0x1800184ed  nop     dword ptr [rax+rax+00h]
0x1800184f2  mov     ebx, eax
0x1800184f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184fb  lea     rax, WPP_GLOBAL_Control
0x180018502  cmp     rcx, rax
0x180018505  jz      loc_1800185E4
0x18001850b  mov     rcx, [rcx+10h]
0x18001850f  lea     rax, [rsp+7A8h+var_648]
0x180018517  mov     edx, 19h
0x18001851c  mov     [rsp+7A8h+phkResult], rax
0x180018521  mov     r9d, ebx
0x180018524  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18001852b  call    WPP_SF_DS
0x180018530  jmp     loc_1800185E4
0x180018535  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hModule
0x18001853c  lea     rdx, [rsp+7A8h+MultiByteStr]; lpProcName
0x180018541  call    cs:__imp_GetProcAddress
0x180018548  nop     dword ptr [rax+rax+00h]
0x18001854d  test    rax, rax
0x180018550  jnz     short loc_18001857A
0x180018552  call    cs:__imp_GetLastError
0x180018559  nop     dword ptr [rax+rax+00h]
0x18001855e  mov     ebx, eax
0x180018560  mov     rcx, cs:WPP_GLOBAL_Control
0x180018567  lea     rax, WPP_GLOBAL_Control
0x18001856e  cmp     rcx, rax
0x180018571  jz      short loc_1800185E4
0x180018573  mov     edx, 1Ah
0x180018578  jmp     short loc_1800185D1
0x18001857a  lea     rcx, ?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180018581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018586  mov     ebx, eax
0x180018588  test    eax, eax
0x18001858a  jz      short loc_1800185A6
0x18001858c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018593  lea     rax, WPP_GLOBAL_Control
0x18001859a  cmp     rcx, rax
0x18001859d  jz      short loc_1800185E4
0x18001859f  mov     edx, 1Bh
0x1800185a4  jmp     short loc_1800185D1
0x1800185a6  mov     rax, qword ptr cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x1800185ad  test    rax, rax
0x1800185b0  jz      short loc_1800185E4
0x1800185b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185b7  mov     ebx, eax
0x1800185b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185c0  lea     rax, WPP_GLOBAL_Control
0x1800185c7  cmp     rcx, rax
0x1800185ca  jz      short loc_1800185E4
0x1800185cc  mov     edx, 1Ch
0x1800185d1  mov     rcx, [rcx+10h]
0x1800185d5  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800185dc  mov     r9d, ebx
0x1800185df  call    WPP_SF_d
0x1800185e4  mov     rcx, [rsp+7A8h+hKey]; hKey
0x1800185e9  test    rcx, rcx
0x1800185ec  jz      short loc_1800185FA
0x1800185ee  call    cs:__imp_RegCloseKey
0x1800185f5  nop     dword ptr [rax+rax+00h]
0x1800185fa  test    ebx, ebx
0x1800185fc  jz      short loc_18001863E
0x1800185fe  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x180018605  test    rcx, rcx
0x180018608  jz      short loc_18001861D
0x18001860a  call    cs:__imp_FreeLibrary
0x180018611  nop     dword ptr [rax+rax+00h]
0x180018616  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hEapProvPluginDll
0x18001861d  xorps   xmm0, xmm0
0x180018620  xor     eax, eax
0x180018622  movups  cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A, xmm0; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180018629  mov     cs:qword_1800AC090, rax
0x180018630  movups  cs:xmmword_1800AC070, xmm0
0x180018637  movups  cs:xmmword_1800AC080, xmm0
0x18001863e  mov     eax, ebx
0x180018640  mov     rcx, [rsp+7A8h+var_18]
0x180018648  xor     rcx, rsp; StackCookie
0x18001864b  call    __security_check_cookie
0x180018650  mov     rbx, [rsp+7A8h+arg_0]
0x180018658  add     rsp, 7A0h
0x18001865f  pop     rdi
0x180018660  retn
```
