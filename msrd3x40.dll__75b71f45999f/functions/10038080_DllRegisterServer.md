# DllRegisterServer()

- ea: `0x10038080`
- end: `0x1003861d`
- name: `_DllRegisterServer@0`
- size: `1437`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x100084f0`
- `0x10037ca0`
- `0x10038080`
- `0x1005d6b4`
- `0x1005d909`
- `0x1005dd1d`
- `0x1005ddb4`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100382e3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10038319`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100382e3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10038319`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x10038243`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x10038243`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1003832c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10038408`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10038414`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100385f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1003832c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10038408`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10038414`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100385f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10038377`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10038377`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100382b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100383b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100383e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100383fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100382b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100383b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100383e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100383fc`

## string_xrefs

- `0x100383d5`: `UserCommitSync`
- `0x100383f1`: `ImplicitCommitSync`
- `0x100385bb`: `CreateDBOnExport`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  int v0; // esi
  WCHAR *v1; // ecx
  const wchar_t *v2; // edi
  int v3; // edx
  WCHAR *v4; // eax
  int v5; // ecx
  WCHAR *v6; // eax
  int v7; // ecx
  WCHAR *v8; // eax
  int v9; // ecx
  WCHAR *v10; // eax
  unsigned int v11; // kr00_4
  HKEY v12; // edi
  LSTATUS v13; // esi
  int v15; // esi
  int v16; // esi
  WCHAR *v17; // ecx
  const wchar_t *v18; // edi
  int v19; // edx
  wchar_t v20; // ax
  WCHAR *v21; // eax
  int v22; // ecx
  WCHAR *v23; // eax
  int v24; // ecx
  WCHAR *v25; // eax
  int v26; // ecx
  WCHAR *v27; // eax
  int v28; // esi
  LSTATUS v29; // eax
  const wchar_t *v30; // [esp+0h] [ebp-724h]
  size_t v31; // [esp+4h] [ebp-720h]
  DWORD dwDisposition; // [esp+Ch] [ebp-718h] BYREF
  BYTE v33[4]; // [esp+10h] [ebp-714h] BYREF
  BYTE v34[4]; // [esp+14h] [ebp-710h] BYREF
  HKEY phkResult; // [esp+18h] [ebp-70Ch] BYREF
  HKEY hKey; // [esp+1Ch] [ebp-708h] BYREF
  BYTE v37; // [esp+23h] [ebp-701h] BYREF
  int v38; // [esp+24h] [ebp-700h] BYREF
  LPCSTR lpValueName; // [esp+28h] [ebp-6FCh]
  char v40; // [esp+2Ch] [ebp-6F8h] BYREF
  int v41; // [esp+238h] [ebp-4ECh] BYREF
  BYTE *lpData; // [esp+23Ch] [ebp-4E8h]
  char v43; // [esp+240h] [ebp-4E4h] BYREF
  int v44; // [esp+448h] [ebp-2DCh]
  WCHAR Data[262]; // [esp+44Ch] [ebp-2D8h] BYREF
  WCHAR SubKey[100]; // [esp+658h] [ebp-CCh] BYREF

  hKey = 0;
  v37 = 0;
  *(_DWORD *)v33 = 0;
  DllUnregisterServer();
  if ( !JetGetModuleFileNameW(hModule, Data, 0x105u) )
    return -2147467259;
  v0 = 2147483646;
  v1 = SubKey;
  v2 = L"Software\\Microsoft\\Jet\\4.0";
  v3 = 100;
  do
  {
    if ( !v0 )
      break;
    if ( !*v2 )
      break;
    *v1++ = *v2++;
    --v0;
    --v3;
  }
  while ( v3 );
  v4 = v1 - 1;
  if ( v3 )
    v4 = v1;
  *v4 = 0;
  v5 = 100;
  v6 = SubKey;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  if ( v5 )
    StringCopyWorkerW((STRSAFE_LPWSTR)v5, (size_t)L"\\Engines", (size_t *)v5, v30, v31);
  v7 = 100;
  v8 = SubKey;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  if ( v7 )
    StringCopyWorkerW((STRSAFE_LPWSTR)v7, (size_t)L"\\", (size_t *)v7, v30, v31);
  v9 = 100;
  v10 = SubKey;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  if ( v9 )
    StringCopyWorkerW((STRSAFE_LPWSTR)v9, (size_t)L"Jet 3.x", (size_t *)v9, v30, v31);
  if ( JetRegCreateKeyW(HKEY_LOCAL_MACHINE, SubKey, &hKey) )
    return -2147467259;
  v11 = wcslen(Data);
  v12 = hKey;
  if ( wrap )
  {
    v13 = RegSetValueExW(hKey, L"win32", 0, 1u, (const BYTE *)Data, 2 * v11);
  }
  else
  {
    v38 = 0;
    lpValueName = 0;
    CStrIn::Init((CStrIn *)&v38, L"win32", -1);
    v41 = 0;
    lpData = 0;
    CStrIn::Init((CStrIn *)&v41, Data, (2 * v11) >> 1);
    v13 = RegSetValueExA(v12, lpValueName, 0, 1u, lpData, v44 + 1);
    if ( lpData != (BYTE *)&v43 && (unsigned int)lpData >> 16 && v41 != -1 )
      _free(lpData);
    lpData = 0;
    if ( lpValueName != &v40 && (unsigned int)lpValueName >> 16 && v38 != -1 )
      _free((void *)lpValueName);
  }
  if ( v13
    || (phkResult = 0,
        RegCreateKeyExA(
          HKEY_LOCAL_MACHINE,
          "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines\\Jet 3.x",
          0,
          0,
          0,
          0x20006u,
          0,
          &phkResult,
          &dwDisposition)) )
  {
    RegCloseKey(hKey);
    return -2147467259;
  }
  v15 = 0;
  if ( ::lpValueName )
  {
    do
    {
      *(_DWORD *)v34 = dword_100661F4[2 * v15];
      RegSetValueExA(phkResult, (&::lpValueName)[2 * v15++], 0, 4u, v34, 4u);
    }
    while ( (&::lpValueName)[2 * v15] );
  }
  RegSetValueExA(phkResult, "UserCommitSync", 0, 1u, "yes", 4u);
  RegSetValueExA(phkResult, "ImplicitCommitSync", 0, 1u, "no", 3u);
  RegCloseKey(phkResult);
  RegCloseKey(hKey);
  v16 = 2147483646;
  v17 = SubKey;
  v18 = L"Software\\Microsoft\\Jet\\4.0";
  v19 = 100;
  do
  {
    if ( !v16 )
      break;
    v20 = *v18;
    *(_DWORD *)v34 = *v18;
    if ( !v20 )
      break;
    *v17 = v20;
    ++v18;
    ++v17;
    --v16;
    --v19;
  }
  while ( v19 );
  v21 = v17 - 1;
  if ( v19 )
    v21 = v17;
  *v21 = 0;
  v22 = 100;
  v23 = SubKey;
  do
  {
    if ( !*v23 )
      break;
    ++v23;
    --v22;
  }
  while ( v22 );
  if ( v22 )
    StringCopyWorkerW((STRSAFE_LPWSTR)v22, (size_t)L"\\ISAM Formats", (size_t *)v22, v30, v31);
  v24 = 100;
  v25 = SubKey;
  do
  {
    if ( !*v25 )
      break;
    ++v25;
    --v24;
  }
  while ( v24 );
  if ( v24 )
    StringCopyWorkerW((STRSAFE_LPWSTR)v24, (size_t)L"\\", (size_t *)v24, v30, v31);
  v26 = 100;
  v27 = SubKey;
  do
  {
    if ( !*v27 )
      break;
    ++v27;
    --v26;
  }
  while ( v26 );
  if ( v26 )
    StringCopyWorkerW((STRSAFE_LPWSTR)v26, (size_t)L"Jet 3.x", (size_t *)v26, v30, v31);
  if ( JetRegCreateKeyW(HKEY_LOCAL_MACHINE, SubKey, &hKey) )
    return -2147467259;
  v28 = JetRegSetValueExW(hKey, L"Engine", 0, 1u, (BYTE *)L"Jet 3.x", 0xEu);
  if ( !v28 )
  {
    v28 = JetRegSetValueExW(hKey, L"OneTablePerFile", 0, 3u, &v37, 1u);
    if ( !v28 )
    {
      v28 = JetRegSetValueExW(hKey, L"IndexDialog", 0, 3u, &v37, 1u);
      if ( !v28 )
      {
        v28 = JetRegSetValueExW(hKey, L"CreateDBOnExport", 0, 3u, &v37, 1u);
        if ( !v28 )
          v28 = JetRegSetValueExW(hKey, L"IsamType", 0, 4u, v33, 4u);
      }
    }
  }
  v29 = RegCloseKey(hKey);
  if ( v28 )
    return -2147467259;
  return v29 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x10038080  mov     edi, edi
0x10038082  push    ebp
0x10038083  mov     ebp, esp
0x10038085  sub     esp, 718h
0x1003808b  mov     eax, ___security_cookie
0x10038090  xor     eax, ebp
0x10038092  mov     [ebp+var_4], eax
0x10038095  push    ebx
0x10038096  push    esi; cchToCopy
0x10038097  push    edi; pszSrc
0x10038098  mov     [ebp+hKey], 0
0x100380a2  mov     [ebp+var_701], 0
0x100380a9  mov     dword ptr [ebp+var_714], 0
0x100380b3  call    _DllUnregisterServer@0; DllUnregisterServer()
0x100380b8  push    105h; nSize
0x100380bd  lea     eax, [ebp+Data]
0x100380c3  push    eax; lpFilename
0x100380c4  push    hModule; hModule
0x100380ca  call    _JetGetModuleFileNameW@12; JetGetModuleFileNameW(x,x,x)
0x100380cf  test    eax, eax
0x100380d1  jz      loc_10038332
0x100380d7  mov     esi, 7FFFFFFEh
0x100380dc  lea     ecx, [ebp+SubKey]
0x100380e2  mov     edi, offset aSoftwareMicros_0; "Software\\Microsoft\\Jet\\4.0"
0x100380e7  mov     edx, 64h ; 'd'
0x100380ec  nop     dword ptr [eax+00h]
0x100380f0  test    esi, esi
0x100380f2  jz      short loc_1003810D
0x100380f4  movzx   eax, word ptr [edi]
0x100380f7  mov     ebx, eax
0x100380f9  test    ax, ax
0x100380fc  jz      short loc_1003810D
0x100380fe  mov     [ecx], bx
0x10038101  add     edi, 2
0x10038104  add     ecx, 2
0x10038107  dec     esi
0x10038108  sub     edx, 1
0x1003810b  jnz     short loc_100380F0
0x1003810d  lea     eax, [ecx-2]
0x10038110  test    edx, edx
0x10038112  cmovnz  eax, ecx
0x10038115  xor     ecx, ecx
0x10038117  mov     [eax], cx
0x1003811a  mov     ecx, 64h ; 'd'
0x1003811f  lea     eax, [ebp+SubKey]
0x10038125  cmp     word ptr [eax], 0
0x10038129  jz      short loc_10038133
0x1003812b  add     eax, 2
0x1003812e  sub     ecx, 1
0x10038131  jnz     short loc_10038125
0x10038133  mov     ebx, 64h ; 'd'
0x10038138  mov     esi, ecx
0x1003813a  mov     eax, ebx
0x1003813c  sub     eax, ecx
0x1003813e  neg     esi
0x10038140  sbb     esi, esi
0x10038142  and     esi, eax
0x10038144  test    ecx, ecx
0x10038146  jz      short loc_10038161
0x10038148  push    ecx; pcchNewDestLength
0x10038149  push    offset aEngines; "\\Engines"
0x1003814e  push    ecx; pszDest
0x1003814f  mov     edx, ebx
0x10038151  lea     ecx, [ebp+SubKey]
0x10038157  sub     edx, esi
0x10038159  lea     ecx, [ecx+esi*2]
0x1003815c  call    StringCopyWorkerW
0x10038161  mov     ecx, ebx
0x10038163  lea     eax, [ebp+SubKey]
0x10038169  nop     dword ptr [eax+00000000h]
0x10038170  cmp     word ptr [eax], 0
0x10038174  jz      short loc_1003817E
0x10038176  add     eax, 2
0x10038179  sub     ecx, 1
0x1003817c  jnz     short loc_10038170
0x1003817e  mov     eax, ebx
0x10038180  mov     esi, ecx
0x10038182  sub     eax, ecx
0x10038184  neg     esi
0x10038186  sbb     esi, esi
0x10038188  and     esi, eax
0x1003818a  test    ecx, ecx
0x1003818c  jz      short loc_100381A7
0x1003818e  push    ecx; pcchNewDestLength
0x1003818f  push    offset asc_10003F7C; "\\"
0x10038194  push    ecx; pszDest
0x10038195  mov     edx, ebx
0x10038197  lea     ecx, [ebp+SubKey]
0x1003819d  sub     edx, esi
0x1003819f  lea     ecx, [ecx+esi*2]
0x100381a2  call    StringCopyWorkerW
0x100381a7  mov     ecx, ebx
0x100381a9  lea     eax, [ebp+SubKey]
0x100381af  nop
0x100381b0  cmp     word ptr [eax], 0
0x100381b4  jz      short loc_100381BE
0x100381b6  add     eax, 2
0x100381b9  sub     ecx, 1
0x100381bc  jnz     short loc_100381B0
0x100381be  mov     eax, ebx
0x100381c0  mov     esi, ecx
0x100381c2  sub     eax, ecx
0x100381c4  neg     esi
0x100381c6  sbb     esi, esi
0x100381c8  and     esi, eax
0x100381ca  test    ecx, ecx
0x100381cc  jz      short loc_100381E7
0x100381ce  push    ecx; pcchNewDestLength
0x100381cf  push    offset WideCharStr; "Jet 3.x"
0x100381d4  push    ecx; pszDest
0x100381d5  mov     edx, ebx
0x100381d7  lea     ecx, [ebp+SubKey]
0x100381dd  sub     edx, esi
0x100381df  lea     ecx, [ecx+esi*2]
0x100381e2  call    StringCopyWorkerW
0x100381e7  lea     eax, [ebp+hKey]
0x100381ed  push    eax; phkResult
0x100381ee  lea     eax, [ebp+SubKey]
0x100381f4  push    eax; lpSubKey
0x100381f5  push    80000002h; hKey
0x100381fa  call    _JetRegCreateKeyW@12; JetRegCreateKeyW(x,x,x)
0x100381ff  test    eax, eax
0x10038201  jnz     loc_10038332
0x10038207  lea     ecx, [ebp+Data]
0x1003820d  lea     edx, [ecx+2]
0x10038210  mov     ax, [ecx]
0x10038213  add     ecx, 2
0x10038216  test    ax, ax
0x10038219  jnz     short loc_10038210
0x1003821b  mov     edi, [ebp+hKey]
0x10038221  sub     ecx, edx
0x10038223  sar     ecx, 1
0x10038225  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1003822c  lea     esi, [ecx+ecx]
0x1003822f  jz      short loc_10038250
0x10038231  push    esi; cbData
0x10038232  lea     eax, [ebp+Data]
0x10038238  push    eax; lpData
0x10038239  push    1; dwType
0x1003823b  push    0; Reserved
0x1003823d  push    offset ValueName; "win32"
0x10038242  push    edi; hKey
0x10038243  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x10038249  mov     esi, eax
0x1003824b  jmp     loc_10038322
0x10038250  push    0FFFFFFFFh; int
0x10038252  push    offset ValueName; "win32"
0x10038257  lea     ecx, [ebp+var_700]; this
0x1003825d  mov     [ebp+var_700], 0
0x10038267  mov     [ebp+lpValueName], 0
0x10038271  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x10038276  shr     esi, 1
0x10038278  lea     eax, [ebp+Data]
0x1003827e  push    esi; int
0x1003827f  push    eax; lpWideCharStr
0x10038280  lea     ecx, [ebp+var_4EC]; this
0x10038286  mov     [ebp+var_4EC], 0
0x10038290  mov     [ebp+lpData], 0
0x1003829a  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x1003829f  mov     eax, [ebp+var_2DC]
0x100382a5  inc     eax
0x100382a6  push    eax; cbData
0x100382a7  push    [ebp+lpData]; lpData
0x100382ad  push    1; dwType
0x100382af  push    0; Reserved
0x100382b1  push    [ebp+lpValueName]; lpValueName
0x100382b7  push    edi; hKey
0x100382b8  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x100382be  mov     ecx, [ebp+lpData]
0x100382c4  mov     esi, eax
0x100382c6  lea     eax, [ebp+var_4E4]
0x100382cc  cmp     ecx, eax
0x100382ce  jz      short loc_100382EC
0x100382d0  mov     eax, ecx
0x100382d2  shr     eax, 10h
0x100382d5  test    eax, eax
0x100382d7  jz      short loc_100382EC
0x100382d9  cmp     [ebp+var_4EC], 0FFFFFFFFh
0x100382e0  jz      short loc_100382EC
0x100382e2  push    ecx; Block
0x100382e3  call    ds:__imp__free
0x100382e9  add     esp, 4
0x100382ec  mov     ecx, [ebp+lpValueName]
0x100382f2  lea     eax, [ebp+var_6F8]
0x100382f8  mov     [ebp+lpData], 0
0x10038302  cmp     ecx, eax
0x10038304  jz      short loc_10038322
0x10038306  mov     eax, ecx
0x10038308  shr     eax, 10h
0x1003830b  test    eax, eax
0x1003830d  jz      short loc_10038322
0x1003830f  cmp     [ebp+var_700], 0FFFFFFFFh
0x10038316  jz      short loc_10038322
0x10038318  push    ecx; Block
0x10038319  call    ds:__imp__free
0x1003831f  add     esp, 4
0x10038322  test    esi, esi
0x10038324  jz      short loc_10038348
0x10038326  push    [ebp+hKey]; hKey
0x1003832c  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10038332  pop     edi
0x10038333  pop     esi
0x10038334  mov     eax, 80004005h
0x10038339  pop     ebx
0x1003833a  mov     ecx, [ebp+var_4]
0x1003833d  xor     ecx, ebp; StackCookie
0x1003833f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038344  mov     esp, ebp
0x10038346  pop     ebp
0x10038347  retn
0x10038348  lea     eax, [ebp+dwDisposition]
0x1003834e  mov     [ebp+phkResult], 0
0x10038358  push    eax; lpdwDisposition
0x10038359  lea     eax, [ebp+phkResult]
0x1003835f  push    eax; phkResult
0x10038360  push    0; lpSecurityAttributes
0x10038362  push    20006h; samDesired
0x10038367  push    0; dwOptions
0x10038369  push    0; lpClass
0x1003836b  push    0; Reserved
0x1003836d  push    offset SubKey; "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines"...
0x10038372  push    80000002h; hKey
0x10038377  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x1003837d  test    eax, eax
0x1003837f  jnz     short loc_10038326
0x10038381  xor     esi, esi
0x10038383  cmp     lpValueName, esi
0x10038389  jz      short loc_100383CA
0x1003838b  nop     dword ptr [eax+eax+00h]
0x10038390  mov     eax, dword_100661F4[esi*8]
0x10038397  push    4; cbData
0x10038399  mov     dword ptr [ebp+var_710], eax
0x1003839f  lea     eax, [ebp+var_710]
0x100383a5  push    eax; lpData
0x100383a6  push    4; dwType
0x100383a8  push    0; Reserved
0x100383aa  push    lpValueName[esi*8]; lpValueName
0x100383b1  push    [ebp+phkResult]; hKey
0x100383b7  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x100383bd  lea     esi, [esi+1]
0x100383c0  cmp     lpValueName[esi*8], 0
0x100383c8  jnz     short loc_10038390
0x100383ca  push    4; cbData
0x100383cc  push    offset Data; "yes"
0x100383d1  push    1; dwType
0x100383d3  push    0; Reserved
0x100383d5  push    offset aUsercommitsync; "UserCommitSync"
0x100383da  push    [ebp+phkResult]; hKey
0x100383e0  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x100383e6  push    3; cbData
0x100383e8  push    offset aNo_0; "no"
0x100383ed  push    1; dwType
0x100383ef  push    0; Reserved
0x100383f1  push    offset aImplicitcommit; "ImplicitCommitSync"
0x100383f6  push    [ebp+phkResult]; hKey
0x100383fc  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10038402  push    [ebp+phkResult]; hKey
0x10038408  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1003840e  push    [ebp+hKey]; hKey
0x10038414  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1003841a  mov     esi, 7FFFFFFEh
0x1003841f  lea     ecx, [ebp+SubKey]
0x10038425  mov     edi, offset aSoftwareMicros_0; "Software\\Microsoft\\Jet\\4.0"
0x1003842a  mov     edx, ebx
0x1003842c  nop     dword ptr [eax+00h]
0x10038430  test    esi, esi
0x10038432  jz      short loc_10038453
0x10038434  movzx   eax, word ptr [edi]
0x10038437  mov     ebx, eax
0x10038439  mov     dword ptr [ebp+var_710], ebx
0x1003843f  test    ax, ax
0x10038442  jz      short loc_10038453
0x10038444  mov     [ecx], ax
0x10038447  add     edi, 2
0x1003844a  add     ecx, 2
0x1003844d  dec     esi
0x1003844e  sub     edx, 1
0x10038451  jnz     short loc_10038430
0x10038453  lea     eax, [ecx-2]
0x10038456  test    edx, edx
0x10038458  cmovnz  eax, ecx
0x1003845b  xor     ecx, ecx
0x1003845d  mov     [eax], cx
0x10038460  mov     ecx, 64h ; 'd'
0x10038465  lea     eax, [ebp+SubKey]
0x1003846b  mov     ebx, ecx
0x1003846d  nop     dword ptr [eax]
0x10038470  cmp     word ptr [eax], 0
0x10038474  jz      short loc_1003847E
0x10038476  add     eax, 2
0x10038479  sub     ecx, 1
0x1003847c  jnz     short loc_10038470
0x1003847e  mov     eax, ebx
0x10038480  mov     esi, ecx
0x10038482  sub     eax, ecx
0x10038484  neg     esi
0x10038486  sbb     esi, esi
0x10038488  and     esi, eax
0x1003848a  test    ecx, ecx
0x1003848c  jz      short loc_100384A7
  ... truncated ...
```
