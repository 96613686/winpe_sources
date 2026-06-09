# ReadRegistryValues(void)

- ea: `0x180029064`
- end: `0x18002920a`
- name: `?ReadRegistryValues@@YAHXZ`
- size: `422`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011d1c`

## callees

- `0x180029064`
- `0x18002bccc`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800290fc`
- `ADVAPI32!RegQueryValueExW` at `0x180029187`
- `ADVAPI32!RegQueryValueExW` at `0x1800291d2`
- `ADVAPI32!RegQueryValueExW` at `0x1800290fc`
- `ADVAPI32!RegQueryValueExW` at `0x180029187`
- `ADVAPI32!RegQueryValueExW` at `0x1800291d2`
- `ADVAPI32!RegOpenKeyExW` at `0x1800290b0`
- `ADVAPI32!RegOpenKeyExW` at `0x180029137`
- `ADVAPI32!RegOpenKeyExW` at `0x1800290b0`
- `ADVAPI32!RegOpenKeyExW` at `0x180029137`
- `ADVAPI32!RegCloseKey` at `0x1800291f4`
- `ADVAPI32!RegCloseKey` at `0x1800291f4`

## string_xrefs

- `0x180029129`: `SOFTWARE\Microsoft\DataAccess\Session Pooling`
- `0x18002908f`: `SOFTWARE\Microsoft\DataAccess\Udl Pooling`
- `0x1800290e6`: `Cache Size`

## pseudocode

```c
__int64 ReadRegistryValues(void)
{
  HKEY v0; // rbx
  int v1; // eax
  int v2; // eax
  _QWORD v4[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF
  DWORD Type; // [rsp+70h] [rbp+20h] BYREF

  v0 = 0;
  memset(v4, 0, 24);
  Data = 0;
  hKey = 0;
  *(_OWORD *)&g_RegValues = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\DataAccess\\Udl Pooling", 0, 0x20019u, &hKey) )
  {
    v1 = ATL::CRegKey::Close((ATL::CRegKey *)v4);
    v0 = hKey;
    v4[0] = hKey;
    if ( !v1 )
    {
      Type = 0;
      LODWORD(hKey) = 4;
      if ( !RegQueryValueExW(v0, L"Cache Size", 0, &Type, (LPBYTE)&Data, (LPDWORD)&hKey) )
        g_RegValues = Data;
    }
  }
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\DataAccess\\Session Pooling", 0, 0x20019u, &hKey) )
  {
    v2 = ATL::CRegKey::Close((ATL::CRegKey *)v4);
    v0 = hKey;
    if ( !v2 )
    {
      Type = 0;
      LODWORD(hKey) = 4;
      if ( !RegQueryValueExW(v0, L"Retry Wait", 0, &Type, (LPBYTE)&Data, (LPDWORD)&hKey) )
      {
        *(&g_RegValues + 3) |= 1u;
        *(&g_RegValues + 1) = Data;
      }
      Type = 0;
      LODWORD(hKey) = 4;
      if ( !RegQueryValueExW(v0, L"ExpBackOff", 0, &Type, (LPBYTE)&Data, (LPDWORD)&hKey) )
      {
        *(&g_RegValues + 3) |= 2u;
        *(&g_RegValues + 2) = Data;
      }
    }
  }
  if ( v0 )
    RegCloseKey(v0);
  return 1;
}

```

## disassembly

```asm
0x180029064  mov     [rsp-8+arg_18], rbx
0x180029069  push    rbp
0x18002906a  mov     rbp, rsp
0x18002906d  sub     rsp, 50h
0x180029071  xor     ebx, ebx
0x180029073  lea     rax, [rbp+hKey]
0x180029077  xorps   xmm0, xmm0
0x18002907a  mov     [rbp+var_20], rbx
0x18002907e  mov     r9d, 20019h; samDesired
0x180029084  mov     [rbp+var_18], rbx
0x180029088  xor     r8d, r8d; ulOptions
0x18002908b  mov     [rbp+var_10], rbx
0x18002908f  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\DataAccess\\Udl Po"...
0x180029096  mov     [rbp+Data], ebx
0x180029099  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800290a0  mov     [rbp+hKey], rbx
0x1800290a4  movups  cs:?g_RegValues@@3U_RegValues@@A, xmm0; _RegValues g_RegValues
0x1800290ab  mov     [rsp+50h+phkResult], rax; phkResult
0x1800290b0  call    cs:__imp_RegOpenKeyExW
0x1800290b6  test    eax, eax
0x1800290b8  jnz     short loc_18002910F
0x1800290ba  lea     rcx, [rbp+var_20]; this
0x1800290be  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800290c3  mov     rbx, [rbp+hKey]
0x1800290c7  mov     [rbp+var_20], rbx
0x1800290cb  test    eax, eax
0x1800290cd  jnz     short loc_18002910F
0x1800290cf  mov     [rbp+Type], eax
0x1800290d2  lea     r9, [rbp+Type]; lpType
0x1800290d6  lea     rax, [rbp+hKey]
0x1800290da  mov     dword ptr [rbp+hKey], 4
0x1800290e1  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800290e6  lea     rdx, aCacheSize; "Cache Size"
0x1800290ed  lea     rax, [rbp+Data]
0x1800290f1  xor     r8d, r8d; lpReserved
0x1800290f4  mov     rcx, rbx; hKey
0x1800290f7  mov     [rsp+50h+phkResult], rax; lpData
0x1800290fc  call    cs:__imp_RegQueryValueExW
0x180029102  test    eax, eax
0x180029104  jnz     short loc_18002910F
0x180029106  mov     eax, [rbp+Data]
0x180029109  mov     dword ptr cs:?g_RegValues@@3U_RegValues@@A, eax; _RegValues g_RegValues
0x18002910f  lea     rax, [rbp+hKey]
0x180029113  mov     [rbp+hKey], 0
0x18002911b  mov     r9d, 20019h; samDesired
0x180029121  mov     [rsp+50h+phkResult], rax; phkResult
0x180029126  xor     r8d, r8d; ulOptions
0x180029129  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\DataAccess\\Sessio"...
0x180029130  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029137  call    cs:__imp_RegOpenKeyExW
0x18002913d  test    eax, eax
0x18002913f  jnz     loc_1800291EC
0x180029145  lea     rcx, [rbp+var_20]; this
0x180029149  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002914e  mov     rbx, [rbp+hKey]
0x180029152  test    eax, eax
0x180029154  jnz     loc_1800291EC
0x18002915a  mov     [rbp+Type], eax
0x18002915d  lea     r9, [rbp+Type]; lpType
0x180029161  lea     rax, [rbp+hKey]
0x180029165  mov     dword ptr [rbp+hKey], 4
0x18002916c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180029171  lea     rdx, aRetryWait; "Retry Wait"
0x180029178  lea     rax, [rbp+Data]
0x18002917c  xor     r8d, r8d; lpReserved
0x18002917f  mov     rcx, rbx; hKey
0x180029182  mov     [rsp+50h+phkResult], rax; lpData
0x180029187  call    cs:__imp_RegQueryValueExW
0x18002918d  test    eax, eax
0x18002918f  jnz     short loc_1800291A1
0x180029191  mov     eax, [rbp+Data]
0x180029194  or      dword ptr cs:?g_RegValues@@3U_RegValues@@A+0Ch, 1; _RegValues g_RegValues
0x18002919b  mov     dword ptr cs:?g_RegValues@@3U_RegValues@@A+4, eax; _RegValues g_RegValues
0x1800291a1  lea     rax, [rbp+hKey]
0x1800291a5  mov     [rbp+Type], 0
0x1800291ac  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800291b1  lea     r9, [rbp+Type]; lpType
0x1800291b5  lea     rax, [rbp+Data]
0x1800291b9  mov     dword ptr [rbp+hKey], 4
0x1800291c0  xor     r8d, r8d; lpReserved
0x1800291c3  mov     [rsp+50h+phkResult], rax; lpData
0x1800291c8  lea     rdx, aExpbackoff; "ExpBackOff"
0x1800291cf  mov     rcx, rbx; hKey
0x1800291d2  call    cs:__imp_RegQueryValueExW
0x1800291d8  test    eax, eax
0x1800291da  jnz     short loc_1800291EC
0x1800291dc  mov     edx, [rbp+Data]
0x1800291df  or      dword ptr cs:?g_RegValues@@3U_RegValues@@A+0Ch, 2; _RegValues g_RegValues
0x1800291e6  mov     dword ptr cs:?g_RegValues@@3U_RegValues@@A+8, edx; _RegValues g_RegValues
0x1800291ec  test    rbx, rbx
0x1800291ef  jz      short loc_1800291FA
0x1800291f1  mov     rcx, rbx; hKey
0x1800291f4  call    cs:__imp_RegCloseKey
0x1800291fa  mov     rbx, [rsp+50h+arg_18]
0x1800291ff  mov     eax, 1
0x180029204  add     rsp, 50h
0x180029208  pop     rbp
0x180029209  retn
```
