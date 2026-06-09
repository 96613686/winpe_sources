# DllUnregisterServer()

- ea: `0x10037ca0`
- end: `0x10038074`
- name: `_DllUnregisterServer@0`
- size: `980`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x10038080`

## callees

- `0x100084f0`
- `0x10037ca0`
- `0x1005d6b4`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037dda`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037e5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037f95`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10038036`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037dda`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037e5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037f95`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10038036`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10037daf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10037f6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10037daf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10037f6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10037e6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10037fc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10038045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10037e6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10037fc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10038045`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x10037d64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x10037f1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x10037d64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x10037f1f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x10037e35`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x1003800d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x10037e35`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x1003800d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x10037e00`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x10037fbb`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x10037e00`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x10037fbb`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  int v0; // edx
  WCHAR *v1; // ecx
  const wchar_t *v2; // edi
  int v3; // esi
  WCHAR *v4; // eax
  int v5; // ecx
  WCHAR *v6; // eax
  LSTATUS v7; // esi
  HKEY v8; // esi
  int v9; // edx
  WCHAR *v10; // ecx
  const wchar_t *v11; // edi
  int v12; // esi
  WCHAR *v13; // eax
  int v14; // ecx
  WCHAR *v15; // eax
  LSTATUS v16; // esi
  HKEY v17; // esi
  const wchar_t *v19; // [esp+0h] [ebp-92Ch]
  size_t v20; // [esp+4h] [ebp-928h]
  HKEY phkResult; // [esp+Ch] [ebp-920h] BYREF
  int v22; // [esp+10h] [ebp-91Ch] BYREF
  LPCSTR v23; // [esp+14h] [ebp-918h]
  char v24; // [esp+18h] [ebp-914h] BYREF
  int v25; // [esp+224h] [ebp-708h] BYREF
  LPCSTR v26; // [esp+228h] [ebp-704h]
  char v27; // [esp+22Ch] [ebp-700h] BYREF
  int v28; // [esp+438h] [ebp-4F4h] BYREF
  LPCSTR v29; // [esp+43Ch] [ebp-4F0h]
  char v30; // [esp+440h] [ebp-4ECh] BYREF
  int v31; // [esp+64Ch] [ebp-2E0h] BYREF
  LPCSTR lpSubKey; // [esp+650h] [ebp-2DCh]
  char v33; // [esp+654h] [ebp-2D8h] BYREF
  WCHAR SubKey[100]; // [esp+860h] [ebp-CCh] BYREF

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
    StringCopyWorkerW((STRSAFE_LPWSTR)v5, (size_t)L"\\Engines", (size_t *)v5, v19, v20);
  if ( wrap )
  {
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &phkResult);
  }
  else
  {
    v31 = 0;
    lpSubKey = 0;
    CStrIn::Init((CStrIn *)&v31, SubKey, -1);
    v7 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &phkResult);
    if ( lpSubKey != &v33 && (unsigned int)lpSubKey >> 16 && v31 != -1 )
      _free((void *)lpSubKey);
  }
  if ( v7 )
    return -2147467259;
  v8 = phkResult;
  if ( wrap )
  {
    RegDeleteKeyW(phkResult, L"Jet 3.x");
  }
  else
  {
    v28 = 0;
    v29 = 0;
    CStrIn::Init((CStrIn *)&v28, L"Jet 3.x", -1);
    RegDeleteKeyA(v8, v29);
    if ( v29 != &v30 && (unsigned int)v29 >> 16 && v28 != -1 )
      _free((void *)v29);
  }
  RegCloseKey(phkResult);
  v9 = 2147483646;
  v10 = SubKey;
  v11 = L"Software\\Microsoft\\Jet\\4.0";
  v12 = 100;
  do
  {
    if ( !v9 )
      break;
    if ( !*v11 )
      break;
    *v10++ = *v11++;
    --v9;
    --v12;
  }
  while ( v12 );
  v13 = v10 - 1;
  if ( v12 )
    v13 = v10;
  *v13 = 0;
  v14 = 100;
  v15 = SubKey;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  if ( v14 )
    StringCopyWorkerW((STRSAFE_LPWSTR)v14, (size_t)L"\\ISAM Formats", (size_t *)v14, v19, v20);
  if ( wrap )
  {
    v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &phkResult);
  }
  else
  {
    v25 = 0;
    v26 = 0;
    CStrIn::Init((CStrIn *)&v25, SubKey, -1);
    v16 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, v26, 0, 0x20019u, &phkResult);
    if ( v26 != &v27 && (unsigned int)v26 >> 16 && v25 != -1 )
      _free((void *)v26);
  }
  if ( v16 )
    return -2147467259;
  v17 = phkResult;
  if ( wrap )
  {
    RegDeleteKeyW(phkResult, L"Jet 3.x");
    RegCloseKey(phkResult);
    return 0;
  }
  else
  {
    v22 = 0;
    v23 = 0;
    CStrIn::Init((CStrIn *)&v22, L"Jet 3.x", -1);
    RegDeleteKeyA(v17, v23);
    if ( v23 != &v24 && (unsigned int)v23 >> 16 && v22 != -1 )
      _free((void *)v23);
    RegCloseKey(phkResult);
    return 0;
  }
}

```

## disassembly

```asm
0x10037ca0  mov     edi, edi
0x10037ca2  push    ebp
0x10037ca3  mov     ebp, esp
0x10037ca5  sub     esp, 920h
0x10037cab  mov     eax, ___security_cookie
0x10037cb0  xor     eax, ebp
0x10037cb2  mov     [ebp+var_4], eax
0x10037cb5  push    ebx
0x10037cb6  push    esi; cchToCopy
0x10037cb7  push    edi; pszSrc
0x10037cb8  mov     edx, 7FFFFFFEh
0x10037cbd  lea     ecx, [ebp+SubKey]
0x10037cc3  mov     edi, offset aSoftwareMicros_0; "Software\\Microsoft\\Jet\\4.0"
0x10037cc8  mov     esi, 64h ; 'd'
0x10037ccd  nop     dword ptr [eax]
0x10037cd0  test    edx, edx
0x10037cd2  jz      short loc_10037CED
0x10037cd4  movzx   eax, word ptr [edi]
0x10037cd7  mov     ebx, eax
0x10037cd9  test    ax, ax
0x10037cdc  jz      short loc_10037CED
0x10037cde  mov     [ecx], bx
0x10037ce1  add     edi, 2
0x10037ce4  add     ecx, 2
0x10037ce7  dec     edx
0x10037ce8  sub     esi, 1
0x10037ceb  jnz     short loc_10037CD0
0x10037ced  lea     eax, [ecx-2]
0x10037cf0  test    esi, esi
0x10037cf2  cmovnz  eax, ecx
0x10037cf5  xor     ecx, ecx
0x10037cf7  mov     [eax], cx
0x10037cfa  mov     ecx, 64h ; 'd'
0x10037cff  lea     eax, [ebp+SubKey]
0x10037d05  cmp     word ptr [eax], 0
0x10037d09  jz      short loc_10037D13
0x10037d0b  add     eax, 2
0x10037d0e  sub     ecx, 1
0x10037d11  jnz     short loc_10037D05
0x10037d13  mov     ebx, 64h ; 'd'
0x10037d18  mov     esi, ecx
0x10037d1a  mov     eax, ebx
0x10037d1c  sub     eax, ecx
0x10037d1e  neg     esi
0x10037d20  sbb     esi, esi
0x10037d22  and     esi, eax
0x10037d24  test    ecx, ecx
0x10037d26  jz      short loc_10037D41
0x10037d28  push    ecx; pcchNewDestLength
0x10037d29  push    offset aEngines; "\\Engines"
0x10037d2e  push    ecx; pszDest
0x10037d2f  mov     edx, ebx
0x10037d31  lea     ecx, [ebp+SubKey]
0x10037d37  sub     edx, esi
0x10037d39  lea     ecx, [ecx+esi*2]
0x10037d3c  call    StringCopyWorkerW
0x10037d41  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10037d48  jz      short loc_10037D6E
0x10037d4a  lea     eax, [ebp+phkResult]
0x10037d50  push    eax; phkResult
0x10037d51  push    20019h; samDesired
0x10037d56  push    0; ulOptions
0x10037d58  lea     eax, [ebp+SubKey]
0x10037d5e  push    eax; lpSubKey
0x10037d5f  push    80000002h; hKey
0x10037d64  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10037d6a  mov     esi, eax
0x10037d6c  jmp     short loc_10037DE3
0x10037d6e  push    0FFFFFFFFh; int
0x10037d70  lea     eax, [ebp+SubKey]
0x10037d76  mov     [ebp+var_2E0], 0
0x10037d80  push    eax; lpWideCharStr
0x10037d81  lea     ecx, [ebp+var_2E0]; this
0x10037d87  mov     [ebp+lpSubKey], 0
0x10037d91  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x10037d96  lea     eax, [ebp+phkResult]
0x10037d9c  push    eax; phkResult
0x10037d9d  push    20019h; samDesired
0x10037da2  push    0; ulOptions
0x10037da4  push    [ebp+lpSubKey]; lpSubKey
0x10037daa  push    80000002h; hKey
0x10037daf  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10037db5  mov     ecx, [ebp+lpSubKey]
0x10037dbb  mov     esi, eax
0x10037dbd  lea     eax, [ebp+var_2D8]
0x10037dc3  cmp     ecx, eax
0x10037dc5  jz      short loc_10037DE3
0x10037dc7  mov     eax, ecx
0x10037dc9  shr     eax, 10h
0x10037dcc  test    eax, eax
0x10037dce  jz      short loc_10037DE3
0x10037dd0  cmp     [ebp+var_2E0], 0FFFFFFFFh
0x10037dd7  jz      short loc_10037DE3
0x10037dd9  push    ecx; Block
0x10037dda  call    ds:__imp__free
0x10037de0  add     esp, 4
0x10037de3  test    esi, esi
0x10037de5  jnz     loc_1003805E
0x10037deb  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10037df2  mov     esi, [ebp+phkResult]
0x10037df8  jz      short loc_10037E08
0x10037dfa  push    offset WideCharStr; "Jet 3.x"
0x10037dff  push    esi; hKey
0x10037e00  call    ds:__imp__RegDeleteKeyW@8; RegDeleteKeyW(x,x)
0x10037e06  jmp     short loc_10037E67
0x10037e08  push    0FFFFFFFFh; int
0x10037e0a  push    offset WideCharStr; "Jet 3.x"
0x10037e0f  lea     ecx, [ebp+var_4F4]; this
0x10037e15  mov     [ebp+var_4F4], 0
0x10037e1f  mov     [ebp+var_4F0], 0
0x10037e29  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x10037e2e  push    [ebp+var_4F0]; lpSubKey
0x10037e34  push    esi; hKey
0x10037e35  call    ds:__imp__RegDeleteKeyA@8; RegDeleteKeyA(x,x)
0x10037e3b  mov     ecx, [ebp+var_4F0]
0x10037e41  lea     eax, [ebp+var_4EC]
0x10037e47  cmp     ecx, eax
0x10037e49  jz      short loc_10037E67
0x10037e4b  mov     eax, ecx
0x10037e4d  shr     eax, 10h
0x10037e50  test    eax, eax
0x10037e52  jz      short loc_10037E67
0x10037e54  cmp     [ebp+var_4F4], 0FFFFFFFFh
0x10037e5b  jz      short loc_10037E67
0x10037e5d  push    ecx; Block
0x10037e5e  call    ds:__imp__free
0x10037e64  add     esp, 4
0x10037e67  push    [ebp+phkResult]; hKey
0x10037e6d  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10037e73  mov     edx, 7FFFFFFEh
0x10037e78  lea     ecx, [ebp+SubKey]
0x10037e7e  mov     edi, offset aSoftwareMicros_0; "Software\\Microsoft\\Jet\\4.0"
0x10037e83  mov     esi, ebx
0x10037e85  test    edx, edx
0x10037e87  jz      short loc_10037EA2
0x10037e89  movzx   eax, word ptr [edi]
0x10037e8c  mov     ebx, eax
0x10037e8e  test    ax, ax
0x10037e91  jz      short loc_10037EA2
0x10037e93  mov     [ecx], bx
0x10037e96  add     edi, 2
0x10037e99  add     ecx, 2
0x10037e9c  dec     edx
0x10037e9d  sub     esi, 1
0x10037ea0  jnz     short loc_10037E85
0x10037ea2  lea     eax, [ecx-2]
0x10037ea5  test    esi, esi
0x10037ea7  cmovnz  eax, ecx
0x10037eaa  xor     ecx, ecx
0x10037eac  mov     [eax], cx
0x10037eaf  mov     ecx, 64h ; 'd'
0x10037eb4  lea     eax, [ebp+SubKey]
0x10037eba  nop     word ptr [eax+eax+00h]
0x10037ec0  cmp     word ptr [eax], 0
0x10037ec4  jz      short loc_10037ECE
0x10037ec6  add     eax, 2
0x10037ec9  sub     ecx, 1
0x10037ecc  jnz     short loc_10037EC0
0x10037ece  mov     ebx, 64h ; 'd'
0x10037ed3  mov     esi, ecx
0x10037ed5  mov     eax, ebx
0x10037ed7  sub     eax, ecx
0x10037ed9  neg     esi
0x10037edb  sbb     esi, esi
0x10037edd  and     esi, eax
0x10037edf  test    ecx, ecx
0x10037ee1  jz      short loc_10037EFC
0x10037ee3  push    ecx; pcchNewDestLength
0x10037ee4  push    offset aIsamFormats; "\\ISAM Formats"
0x10037ee9  push    ecx; pszDest
0x10037eea  sub     ebx, esi
0x10037eec  lea     ecx, [ebp+SubKey]
0x10037ef2  lea     ecx, [ecx+esi*2]
0x10037ef5  mov     edx, ebx
0x10037ef7  call    StringCopyWorkerW
0x10037efc  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10037f03  jz      short loc_10037F29
0x10037f05  lea     eax, [ebp+phkResult]
0x10037f0b  push    eax; phkResult
0x10037f0c  push    20019h; samDesired
0x10037f11  push    0; ulOptions
0x10037f13  lea     eax, [ebp+SubKey]
0x10037f19  push    eax; lpSubKey
0x10037f1a  push    80000002h; hKey
0x10037f1f  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10037f25  mov     esi, eax
0x10037f27  jmp     short loc_10037F9E
0x10037f29  push    0FFFFFFFFh; int
0x10037f2b  lea     eax, [ebp+SubKey]
0x10037f31  mov     [ebp+var_708], 0
0x10037f3b  push    eax; lpWideCharStr
0x10037f3c  lea     ecx, [ebp+var_708]; this
0x10037f42  mov     [ebp+var_704], 0
0x10037f4c  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x10037f51  lea     eax, [ebp+phkResult]
0x10037f57  push    eax; phkResult
0x10037f58  push    20019h; samDesired
0x10037f5d  push    0; ulOptions
0x10037f5f  push    [ebp+var_704]; lpSubKey
0x10037f65  push    80000002h; hKey
0x10037f6a  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10037f70  mov     ecx, [ebp+var_704]
0x10037f76  mov     esi, eax
0x10037f78  lea     eax, [ebp+var_700]
0x10037f7e  cmp     ecx, eax
0x10037f80  jz      short loc_10037F9E
0x10037f82  mov     eax, ecx
0x10037f84  shr     eax, 10h
0x10037f87  test    eax, eax
0x10037f89  jz      short loc_10037F9E
0x10037f8b  cmp     [ebp+var_708], 0FFFFFFFFh
0x10037f92  jz      short loc_10037F9E
0x10037f94  push    ecx; Block
0x10037f95  call    ds:__imp__free
0x10037f9b  add     esp, 4
0x10037f9e  test    esi, esi
0x10037fa0  jnz     loc_1003805E
0x10037fa6  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10037fad  mov     esi, [ebp+phkResult]
0x10037fb3  jz      short loc_10037FE0
0x10037fb5  push    offset WideCharStr; "Jet 3.x"
0x10037fba  push    esi; hKey
0x10037fbb  call    ds:__imp__RegDeleteKeyW@8; RegDeleteKeyW(x,x)
0x10037fc1  push    [ebp+phkResult]; hKey
0x10037fc7  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10037fcd  pop     edi
0x10037fce  pop     esi
0x10037fcf  xor     eax, eax
0x10037fd1  pop     ebx
0x10037fd2  mov     ecx, [ebp+var_4]
0x10037fd5  xor     ecx, ebp; StackCookie
0x10037fd7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037fdc  mov     esp, ebp
0x10037fde  pop     ebp
0x10037fdf  retn
0x10037fe0  push    0FFFFFFFFh; int
0x10037fe2  push    offset WideCharStr; "Jet 3.x"
0x10037fe7  lea     ecx, [ebp+var_91C]; this
0x10037fed  mov     [ebp+var_91C], 0
0x10037ff7  mov     [ebp+var_918], 0
0x10038001  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x10038006  push    [ebp+var_918]; lpSubKey
0x1003800c  push    esi; hKey
0x1003800d  call    ds:__imp__RegDeleteKeyA@8; RegDeleteKeyA(x,x)
0x10038013  mov     ecx, [ebp+var_918]
0x10038019  lea     eax, [ebp+var_914]
0x1003801f  cmp     ecx, eax
0x10038021  jz      short loc_1003803F
0x10038023  mov     eax, ecx
0x10038025  shr     eax, 10h
0x10038028  test    eax, eax
0x1003802a  jz      short loc_1003803F
0x1003802c  cmp     [ebp+var_91C], 0FFFFFFFFh
0x10038033  jz      short loc_1003803F
0x10038035  push    ecx; Block
0x10038036  call    ds:__imp__free
0x1003803c  add     esp, 4
0x1003803f  push    [ebp+phkResult]; hKey
0x10038045  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1003804b  pop     edi
0x1003804c  pop     esi
0x1003804d  xor     eax, eax
0x1003804f  pop     ebx
0x10038050  mov     ecx, [ebp+var_4]
0x10038053  xor     ecx, ebp; StackCookie
0x10038055  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003805a  mov     esp, ebp
0x1003805c  pop     ebp
0x1003805d  retn
0x1003805e  mov     ecx, [ebp+var_4]
0x10038061  mov     eax, 80004005h
0x10038066  pop     edi
0x10038067  pop     esi
0x10038068  xor     ecx, ebp; StackCookie
0x1003806a  pop     ebx
0x1003806b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10038070  mov     esp, ebp
0x10038072  pop     ebp
0x10038073  retn
```
