# EapProvPlugin_Initialize

- ea: `0x18003323c`
- end: `0x18003361a`
- name: `EapProvPlugin_Initialize`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180023318`

## callees

- `0x180002af0`
- `0x1800034cc`
- `0x18000a24c`
- `0x18000a44c`
- `0x18003323c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033411`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033411`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800335bb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800335bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800334f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800334f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003349b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003349b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033503`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003348b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003348b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800332cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800332cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033322`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800333d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033322`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800333d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003359f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003359f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180033369`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180033369`

## string_xrefs

- `0x1800333b7`: `DllEntryPoint`
- `0x1800332be`: `SYSTEM\CurrentControlSet\Services\EapHost\Parameters\EapProvPlugin`

## pseudocode

```c
__int64 EapProvPlugin_Initialize()
{
  DWORD LastError; // ebx
  EapHost::Peer::Host *v1; // rcx
  __int64 v2; // rdx
  FARPROC ProcAddress; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  CHAR MultiByteStr[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v8[264]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR Data[264]; // [rsp+370h] [rbp+270h] BYREF
  WCHAR Dst[264]; // [rsp+580h] [rbp+480h] BYREF

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
    if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 20;
    goto LABEL_28;
  }
  LastError = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &cbData);
  if ( LastError )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 21;
    goto LABEL_28;
  }
  if ( !ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 22;
    goto LABEL_28;
  }
  cbData = 520;
  LastError = RegQueryValueExW(hKey, L"DllEntryPoint", 0, 0, (LPBYTE)v8, &cbData);
  if ( LastError )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v2 = 23;
    goto LABEL_28;
  }
  g_hEapProvPluginDll = LoadLibraryExW(Dst, 0, 0);
  if ( !g_hEapProvPluginDll )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control )
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
      if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v2 = 26;
      goto LABEL_28;
    }
    LastError = ((__int64 (__fastcall *)(__int64 (**)(void)))ProcAddress)(&g_EapProvPluginDllFunctionTable);
    if ( LastError )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v2 = 27;
      goto LABEL_28;
    }
    if ( g_EapProvPluginDllFunctionTable )
    {
      LastError = g_EapProvPluginDllFunctionTable();
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control )
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
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control )
      WPP_SF_dS(
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
    qword_18004FCE8 = 0;
    xmmword_18004FCC8 = 0;
    xmmword_18004FCD8 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18003323c  mov     [rsp-8+arg_0], rbx
0x180033241  mov     [rsp-8+arg_8], r14
0x180033246  push    rbp
0x180033247  lea     rbp, [rsp-6A0h]
0x18003324f  sub     rsp, 7A0h
0x180033256  mov     rax, cs:__security_cookie
0x18003325d  xor     rax, rsp
0x180033260  mov     [rbp+6A0h+var_10], rax
0x180033267  mov     r14d, 208h
0x18003326d  mov     [rsp+7A0h+hKey], 0
0x180033276  mov     r8d, r14d; Size
0x180033279  lea     rcx, [rbp+6A0h+Data]; void *
0x180033280  xor     edx, edx; Val
0x180033282  call    memset_0
0x180033287  mov     r8d, r14d; Size
0x18003328a  lea     rcx, [rbp+6A0h+Dst]; void *
0x180033291  xor     edx, edx; Val
0x180033293  call    memset_0
0x180033298  mov     r8d, r14d; Size
0x18003329b  lea     rcx, [rbp+6A0h+var_640]; void *
0x18003329f  xor     edx, edx; Val
0x1800332a1  call    memset_0
0x1800332a6  lea     rax, [rsp+7A0h+hKey]
0x1800332ab  mov     [rsp+7A0h+cbData], r14d
0x1800332b0  mov     r9d, 1; samDesired
0x1800332b6  mov     [rsp+7A0h+phkResult], rax; phkResult
0x1800332bb  xor     r8d, r8d; ulOptions
0x1800332be  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x1800332c5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800332cc  call    cs:__imp_RegOpenKeyExW
0x1800332d3  nop     dword ptr [rax+rax+00h]
0x1800332d8  mov     ebx, eax
0x1800332da  test    eax, eax
0x1800332dc  jz      short loc_1800332FF
0x1800332de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800332e5  lea     rax, WPP_GLOBAL_Control
0x1800332ec  cmp     rcx, rax
0x1800332ef  jz      loc_180033595
0x1800332f5  mov     edx, 14h
0x1800332fa  jmp     loc_180033582
0x1800332ff  mov     rcx, [rsp+7A0h+hKey]; hKey
0x180033304  lea     rax, [rsp+7A0h+cbData]
0x180033309  mov     [rsp+7A0h+lpcbData], rax; lpcbData
0x18003330e  xor     r9d, r9d; lpType
0x180033311  lea     rax, [rbp+6A0h+Data]
0x180033318  xor     r8d, r8d; lpReserved
0x18003331b  xor     edx, edx; lpValueName
0x18003331d  mov     [rsp+7A0h+phkResult], rax; lpData
0x180033322  call    cs:__imp_RegQueryValueExW
0x180033329  nop     dword ptr [rax+rax+00h]
0x18003332e  mov     ebx, eax
0x180033330  test    eax, eax
0x180033332  jz      short loc_180033355
0x180033334  mov     rcx, cs:WPP_GLOBAL_Control
0x18003333b  lea     rax, WPP_GLOBAL_Control
0x180033342  cmp     rcx, rax
0x180033345  jz      loc_180033595
0x18003334b  mov     edx, 15h
0x180033350  jmp     loc_180033582
0x180033355  mov     r8d, 104h; nSize
0x18003335b  lea     rdx, [rbp+6A0h+Dst]; lpDst
0x180033362  lea     rcx, [rbp+6A0h+Data]; lpSrc
0x180033369  call    cs:__imp_ExpandEnvironmentStringsW
0x180033370  nop     dword ptr [rax+rax+00h]
0x180033375  test    eax, eax
0x180033377  jnz     short loc_1800333A8
0x180033379  call    cs:__imp_GetLastError
0x180033380  nop     dword ptr [rax+rax+00h]
0x180033385  mov     ebx, eax
0x180033387  mov     rcx, cs:WPP_GLOBAL_Control
0x18003338e  lea     rax, WPP_GLOBAL_Control
0x180033395  cmp     rcx, rax
0x180033398  jz      loc_180033595
0x18003339e  mov     edx, 16h
0x1800333a3  jmp     loc_180033582
0x1800333a8  mov     rcx, [rsp+7A0h+hKey]; hKey
0x1800333ad  lea     rax, [rsp+7A0h+cbData]
0x1800333b2  mov     [rsp+7A0h+lpcbData], rax; lpcbData
0x1800333b7  lea     rdx, ValueName; "DllEntryPoint"
0x1800333be  lea     rax, [rbp+6A0h+var_640]
0x1800333c2  mov     [rsp+7A0h+cbData], r14d
0x1800333c7  xor     r9d, r9d; lpType
0x1800333ca  mov     [rsp+7A0h+phkResult], rax; lpData
0x1800333cf  xor     r8d, r8d; lpReserved
0x1800333d2  call    cs:__imp_RegQueryValueExW
0x1800333d9  nop     dword ptr [rax+rax+00h]
0x1800333de  mov     ebx, eax
0x1800333e0  test    eax, eax
0x1800333e2  jz      short loc_180033405
0x1800333e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333eb  lea     rax, WPP_GLOBAL_Control
0x1800333f2  cmp     rcx, rax
0x1800333f5  jz      loc_180033595
0x1800333fb  mov     edx, 17h
0x180033400  jmp     loc_180033582
0x180033405  xor     r8d, r8d; dwFlags
0x180033408  lea     rcx, [rbp+6A0h+Dst]; lpLibFileName
0x18003340f  xor     edx, edx; hFile
0x180033411  call    cs:__imp_LoadLibraryExW
0x180033418  nop     dword ptr [rax+rax+00h]
0x18003341d  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hEapProvPluginDll
0x180033424  test    rax, rax
0x180033427  jnz     short loc_180033458
0x180033429  call    cs:__imp_GetLastError
0x180033430  nop     dword ptr [rax+rax+00h]
0x180033435  mov     ebx, eax
0x180033437  mov     rcx, cs:WPP_GLOBAL_Control
0x18003343e  lea     rax, WPP_GLOBAL_Control
0x180033445  cmp     rcx, rax
0x180033448  jz      loc_180033595
0x18003344e  mov     edx, 18h
0x180033453  jmp     loc_180033582
0x180033458  mov     [rsp+7A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180033461  lea     rax, [rsp+7A0h+MultiByteStr]
0x180033466  mov     [rsp+7A0h+lpDefaultChar], 0; lpDefaultChar
0x18003346f  lea     r8, [rbp+6A0h+var_640]; lpWideCharStr
0x180033473  mov     dword ptr [rsp+7A0h+lpcbData], 104h; cbMultiByte
0x18003347b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18003347f  xor     edx, edx; dwFlags
0x180033481  mov     [rsp+7A0h+phkResult], rax; lpMultiByteStr
0x180033486  mov     ecx, 0FDE9h; CodePage
0x18003348b  call    cs:__imp_WideCharToMultiByte
0x180033492  nop     dword ptr [rax+rax+00h]
0x180033497  test    eax, eax
0x180033499  jnz     short loc_1800334E6
0x18003349b  call    cs:__imp_GetLastError
0x1800334a2  nop     dword ptr [rax+rax+00h]
0x1800334a7  mov     ebx, eax
0x1800334a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334b0  lea     rax, WPP_GLOBAL_Control
0x1800334b7  cmp     rcx, rax
0x1800334ba  jz      loc_180033595
0x1800334c0  mov     rcx, [rcx+10h]
0x1800334c4  lea     rax, [rbp+6A0h+var_640]
0x1800334c8  mov     edx, 19h
0x1800334cd  mov     [rsp+7A0h+phkResult], rax
0x1800334d2  mov     r9d, ebx
0x1800334d5  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800334dc  call    WPP_SF_dS
0x1800334e1  jmp     loc_180033595
0x1800334e6  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hModule
0x1800334ed  lea     rdx, [rsp+7A0h+MultiByteStr]; lpProcName
0x1800334f2  call    cs:__imp_GetProcAddress
0x1800334f9  nop     dword ptr [rax+rax+00h]
0x1800334fe  test    rax, rax
0x180033501  jnz     short loc_18003352B
0x180033503  call    cs:__imp_GetLastError
0x18003350a  nop     dword ptr [rax+rax+00h]
0x18003350f  mov     ebx, eax
0x180033511  mov     rcx, cs:WPP_GLOBAL_Control
0x180033518  lea     rax, WPP_GLOBAL_Control
0x18003351f  cmp     rcx, rax
0x180033522  jz      short loc_180033595
0x180033524  mov     edx, 1Ah
0x180033529  jmp     short loc_180033582
0x18003352b  lea     rcx, ?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180033532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033537  mov     ebx, eax
0x180033539  test    eax, eax
0x18003353b  jz      short loc_180033557
0x18003353d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033544  lea     rax, WPP_GLOBAL_Control
0x18003354b  cmp     rcx, rax
0x18003354e  jz      short loc_180033595
0x180033550  mov     edx, 1Bh
0x180033555  jmp     short loc_180033582
0x180033557  mov     rax, qword ptr cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x18003355e  test    rax, rax
0x180033561  jz      short loc_180033595
0x180033563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033568  mov     ebx, eax
0x18003356a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033571  lea     rax, WPP_GLOBAL_Control
0x180033578  cmp     rcx, rax
0x18003357b  jz      short loc_180033595
0x18003357d  mov     edx, 1Ch
0x180033582  mov     rcx, [rcx+10h]
0x180033586  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18003358d  mov     r9d, ebx
0x180033590  call    WPP_SF_d
0x180033595  mov     rcx, [rsp+7A0h+hKey]; hKey
0x18003359a  test    rcx, rcx
0x18003359d  jz      short loc_1800335AB
0x18003359f  call    cs:__imp_RegCloseKey
0x1800335a6  nop     dword ptr [rax+rax+00h]
0x1800335ab  test    ebx, ebx
0x1800335ad  jz      short loc_1800335F3
0x1800335af  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800335b6  test    rcx, rcx
0x1800335b9  jz      short loc_1800335D2
0x1800335bb  call    cs:__imp_FreeLibrary
0x1800335c2  nop     dword ptr [rax+rax+00h]
0x1800335c7  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hEapProvPluginDll
0x1800335d2  xorps   xmm0, xmm0
0x1800335d5  xor     eax, eax
0x1800335d7  movups  cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A, xmm0; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x1800335de  mov     cs:qword_18004FCE8, rax
0x1800335e5  movups  cs:xmmword_18004FCC8, xmm0
0x1800335ec  movups  cs:xmmword_18004FCD8, xmm0
0x1800335f3  mov     eax, ebx
0x1800335f5  mov     rcx, [rbp+6A0h+var_10]
0x1800335fc  xor     rcx, rsp; StackCookie
0x1800335ff  call    __security_check_cookie
0x180033604  lea     r11, [rsp+7A0h+var_s0]
0x18003360c  mov     rbx, [r11+10h]
0x180033610  mov     r14, [r11+18h]
0x180033614  mov     rsp, r11
0x180033617  pop     rbp
0x180033618  retn
```
