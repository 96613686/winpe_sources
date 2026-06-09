# EapProvPlugin_Initialize

- ea: `0x180031fe4`
- end: `0x180032373`
- name: `EapProvPlugin_Initialize`
- size: `911`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800226a0`

## callees

- `0x180002a90`
- `0x18000343c`
- `0x180009dec`
- `0x180009fd0`
- `0x180031fe4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003219b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003219b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003231b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003231b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032264`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003210f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003226f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003210f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003226f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180032209`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180032209`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032074`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032074`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800320c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032162`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800320c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032162`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032305`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032305`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032105`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032105`

## string_xrefs

- `0x180032066`: `SYSTEM\CurrentControlSet\Services\EapHost\Parameters\EapProvPlugin`
- `0x180032147`: `DllEntryPoint`

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
    qword_18004EBB0 = 0;
    xmmword_18004EB90 = 0;
    xmmword_18004EBA0 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x180031fe4  mov     [rsp-8+arg_0], rbx
0x180031fe9  mov     [rsp-8+arg_8], r14
0x180031fee  push    rbp
0x180031fef  lea     rbp, [rsp-6A0h]
0x180031ff7  sub     rsp, 7A0h
0x180031ffe  mov     rax, cs:__security_cookie
0x180032005  xor     rax, rsp
0x180032008  mov     [rbp+6A0h+var_10], rax
0x18003200f  mov     r14d, 208h
0x180032015  mov     [rsp+7A0h+hKey], 0
0x18003201e  mov     r8d, r14d; Size
0x180032021  lea     rcx, [rbp+6A0h+Data]; void *
0x180032028  xor     edx, edx; Val
0x18003202a  call    memset_0
0x18003202f  mov     r8d, r14d; Size
0x180032032  lea     rcx, [rbp+6A0h+Dst]; void *
0x180032039  xor     edx, edx; Val
0x18003203b  call    memset_0
0x180032040  mov     r8d, r14d; Size
0x180032043  lea     rcx, [rbp+6A0h+var_640]; void *
0x180032047  xor     edx, edx; Val
0x180032049  call    memset_0
0x18003204e  lea     rax, [rsp+7A0h+hKey]
0x180032053  mov     [rsp+7A0h+cbData], r14d
0x180032058  mov     r9d, 1; samDesired
0x18003205e  mov     [rsp+7A0h+phkResult], rax; phkResult
0x180032063  xor     r8d, r8d; ulOptions
0x180032066  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x18003206d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032074  call    cs:__imp_RegOpenKeyExW
0x18003207a  mov     ebx, eax
0x18003207c  test    eax, eax
0x18003207e  jz      short loc_1800320A1
0x180032080  mov     rcx, cs:WPP_GLOBAL_Control
0x180032087  lea     rax, WPP_GLOBAL_Control
0x18003208e  cmp     rcx, rax
0x180032091  jz      loc_1800322FB
0x180032097  mov     edx, 14h
0x18003209c  jmp     loc_1800322E8
0x1800320a1  mov     rcx, [rsp+7A0h+hKey]; hKey
0x1800320a6  lea     rax, [rsp+7A0h+cbData]
0x1800320ab  mov     [rsp+7A0h+lpcbData], rax; lpcbData
0x1800320b0  xor     r9d, r9d; lpType
0x1800320b3  lea     rax, [rbp+6A0h+Data]
0x1800320ba  xor     r8d, r8d; lpReserved
0x1800320bd  xor     edx, edx; lpValueName
0x1800320bf  mov     [rsp+7A0h+phkResult], rax; lpData
0x1800320c4  call    cs:__imp_RegQueryValueExW
0x1800320ca  mov     ebx, eax
0x1800320cc  test    eax, eax
0x1800320ce  jz      short loc_1800320F1
0x1800320d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800320d7  lea     rax, WPP_GLOBAL_Control
0x1800320de  cmp     rcx, rax
0x1800320e1  jz      loc_1800322FB
0x1800320e7  mov     edx, 15h
0x1800320ec  jmp     loc_1800322E8
0x1800320f1  mov     r8d, 104h; nSize
0x1800320f7  lea     rdx, [rbp+6A0h+Dst]; lpDst
0x1800320fe  lea     rcx, [rbp+6A0h+Data]; lpSrc
0x180032105  call    cs:__imp_ExpandEnvironmentStringsW
0x18003210b  test    eax, eax
0x18003210d  jnz     short loc_180032138
0x18003210f  call    cs:__imp_GetLastError
0x180032115  mov     ebx, eax
0x180032117  mov     rcx, cs:WPP_GLOBAL_Control
0x18003211e  lea     rax, WPP_GLOBAL_Control
0x180032125  cmp     rcx, rax
0x180032128  jz      loc_1800322FB
0x18003212e  mov     edx, 16h
0x180032133  jmp     loc_1800322E8
0x180032138  mov     rcx, [rsp+7A0h+hKey]; hKey
0x18003213d  lea     rax, [rsp+7A0h+cbData]
0x180032142  mov     [rsp+7A0h+lpcbData], rax; lpcbData
0x180032147  lea     rdx, ValueName; "DllEntryPoint"
0x18003214e  lea     rax, [rbp+6A0h+var_640]
0x180032152  mov     [rsp+7A0h+cbData], r14d
0x180032157  xor     r9d, r9d; lpType
0x18003215a  mov     [rsp+7A0h+phkResult], rax; lpData
0x18003215f  xor     r8d, r8d; lpReserved
0x180032162  call    cs:__imp_RegQueryValueExW
0x180032168  mov     ebx, eax
0x18003216a  test    eax, eax
0x18003216c  jz      short loc_18003218F
0x18003216e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032175  lea     rax, WPP_GLOBAL_Control
0x18003217c  cmp     rcx, rax
0x18003217f  jz      loc_1800322FB
0x180032185  mov     edx, 17h
0x18003218a  jmp     loc_1800322E8
0x18003218f  xor     r8d, r8d; dwFlags
0x180032192  lea     rcx, [rbp+6A0h+Dst]; lpLibFileName
0x180032199  xor     edx, edx; hFile
0x18003219b  call    cs:__imp_LoadLibraryExW
0x1800321a1  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hEapProvPluginDll
0x1800321a8  test    rax, rax
0x1800321ab  jnz     short loc_1800321D6
0x1800321ad  call    cs:__imp_GetLastError
0x1800321b3  mov     ebx, eax
0x1800321b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800321bc  lea     rax, WPP_GLOBAL_Control
0x1800321c3  cmp     rcx, rax
0x1800321c6  jz      loc_1800322FB
0x1800321cc  mov     edx, 18h
0x1800321d1  jmp     loc_1800322E8
0x1800321d6  mov     [rsp+7A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800321df  lea     rax, [rsp+7A0h+MultiByteStr]
0x1800321e4  mov     [rsp+7A0h+lpDefaultChar], 0; lpDefaultChar
0x1800321ed  lea     r8, [rbp+6A0h+var_640]; lpWideCharStr
0x1800321f1  mov     dword ptr [rsp+7A0h+lpcbData], 104h; cbMultiByte
0x1800321f9  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800321fd  xor     edx, edx; dwFlags
0x1800321ff  mov     [rsp+7A0h+phkResult], rax; lpMultiByteStr
0x180032204  mov     ecx, 0FDE9h; CodePage
0x180032209  call    cs:__imp_WideCharToMultiByte
0x18003220f  test    eax, eax
0x180032211  jnz     short loc_180032258
0x180032213  call    cs:__imp_GetLastError
0x180032219  mov     ebx, eax
0x18003221b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032222  lea     rax, WPP_GLOBAL_Control
0x180032229  cmp     rcx, rax
0x18003222c  jz      loc_1800322FB
0x180032232  mov     rcx, [rcx+10h]
0x180032236  lea     rax, [rbp+6A0h+var_640]
0x18003223a  mov     edx, 19h
0x18003223f  mov     [rsp+7A0h+phkResult], rax
0x180032244  mov     r9d, ebx
0x180032247  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18003224e  call    WPP_SF_dS
0x180032253  jmp     loc_1800322FB
0x180032258  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hModule
0x18003225f  lea     rdx, [rsp+7A0h+MultiByteStr]; lpProcName
0x180032264  call    cs:__imp_GetProcAddress
0x18003226a  test    rax, rax
0x18003226d  jnz     short loc_180032291
0x18003226f  call    cs:__imp_GetLastError
0x180032275  mov     ebx, eax
0x180032277  mov     rcx, cs:WPP_GLOBAL_Control
0x18003227e  lea     rax, WPP_GLOBAL_Control
0x180032285  cmp     rcx, rax
0x180032288  jz      short loc_1800322FB
0x18003228a  mov     edx, 1Ah
0x18003228f  jmp     short loc_1800322E8
0x180032291  lea     rcx, ?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180032298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003229d  mov     ebx, eax
0x18003229f  test    eax, eax
0x1800322a1  jz      short loc_1800322BD
0x1800322a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800322aa  lea     rax, WPP_GLOBAL_Control
0x1800322b1  cmp     rcx, rax
0x1800322b4  jz      short loc_1800322FB
0x1800322b6  mov     edx, 1Bh
0x1800322bb  jmp     short loc_1800322E8
0x1800322bd  mov     rax, qword ptr cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x1800322c4  test    rax, rax
0x1800322c7  jz      short loc_1800322FB
0x1800322c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322ce  mov     ebx, eax
0x1800322d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800322d7  lea     rax, WPP_GLOBAL_Control
0x1800322de  cmp     rcx, rax
0x1800322e1  jz      short loc_1800322FB
0x1800322e3  mov     edx, 1Ch
0x1800322e8  mov     rcx, [rcx+10h]
0x1800322ec  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800322f3  mov     r9d, ebx
0x1800322f6  call    WPP_SF_d
0x1800322fb  mov     rcx, [rsp+7A0h+hKey]; hKey
0x180032300  test    rcx, rcx
0x180032303  jz      short loc_18003230B
0x180032305  call    cs:__imp_RegCloseKey
0x18003230b  test    ebx, ebx
0x18003230d  jz      short loc_18003234D
0x18003230f  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x180032316  test    rcx, rcx
0x180032319  jz      short loc_18003232C
0x18003231b  call    cs:__imp_FreeLibrary
0x180032321  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hEapProvPluginDll
0x18003232c  xorps   xmm0, xmm0
0x18003232f  xor     eax, eax
0x180032331  movups  cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A, xmm0; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180032338  mov     cs:qword_18004EBB0, rax
0x18003233f  movups  cs:xmmword_18004EB90, xmm0
0x180032346  movups  cs:xmmword_18004EBA0, xmm0
0x18003234d  mov     eax, ebx
0x18003234f  mov     rcx, [rbp+6A0h+var_10]
0x180032356  xor     rcx, rsp; StackCookie
0x180032359  call    __security_check_cookie
0x18003235e  lea     r11, [rsp+7A0h+var_s0]
0x180032366  mov     rbx, [r11+10h]
0x18003236a  mov     r14, [r11+18h]
0x18003236e  mov     rsp, r11
0x180032371  pop     rbp
0x180032372  retn
```
