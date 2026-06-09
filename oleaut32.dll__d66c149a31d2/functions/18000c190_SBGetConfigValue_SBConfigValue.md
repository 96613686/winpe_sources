# SBGetConfigValue(SBConfigValue)

- ea: `0x18000c190`
- end: `0x18000c476`
- name: `?SBGetConfigValue@@YAHW4SBConfigValue@@@Z`
- size: `742`
- prototype: `__int64 __fastcall(int)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bc14`
- `0x18000bc34`
- `0x18000bcb0`
- `0x18001d734`
- `0x18001ea5c`
- `0x18004b3c8`
- `0x1800741fc`

## callees

- `0x18000c190`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c22e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c272`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c2b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c2fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c33e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c382`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c3c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c40a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c44e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c22e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c272`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c2b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c2fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c33e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c382`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c3c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c40a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c44e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c46b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c46b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c1df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c1df`

## pseudocode

```c
__int64 __fastcall SBGetConfigValue(int a1)
{
  __int64 v1; // rbx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v1 = a1;
  if ( !dword_1800C3680 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\OleAut", 0, 0x2000000u, &hKey) )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"DisableShield", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        dword_1800C4118[0] = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"Disable2GigRestriction", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        dword_1800C411C = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"DisableRemoteIRecordInfoCheck", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        dword_1800C4120 = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"AssertOnShieldReject", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        dword_1800C4124 = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"EnableUPS", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        dword_1800C4128 = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"DisableBSTRValidation", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        dword_1800C412C = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"User1", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        dword_1800C4130 = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"User2", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        dword_1800C4134 = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"User3", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        dword_1800C4138 = Data;
      RegCloseKey(hKey);
    }
    dword_1800C3680 = 1;
  }
  return (unsigned int)dword_1800C4118[v1];
}

```

## disassembly

```asm
0x18000c190  push    rbp
0x18000c192  push    rbx
0x18000c193  mov     rbp, rsp
0x18000c196  sub     rsp, 38h
0x18000c19a  cmp     cs:dword_1800C3680, 0
0x18000c1a1  movsxd  rbx, ecx
0x18000c1a4  jz      short loc_18000C1B7
0x18000c1a6  lea     rcx, dword_1800C4118
0x18000c1ad  mov     eax, [rcx+rbx*4]
0x18000c1b0  add     rsp, 38h
0x18000c1b4  pop     rbx
0x18000c1b5  pop     rbp
0x18000c1b6  retn
0x18000c1b7  lea     rax, [rbp+hKey]
0x18000c1bb  mov     [rbp+hKey], 0
0x18000c1c3  mov     r9d, 2000000h; samDesired
0x18000c1c9  mov     [rsp+38h+phkResult], rax; phkResult
0x18000c1ce  xor     r8d, r8d; ulOptions
0x18000c1d1  lea     rdx, SubKey; "Software\\Microsoft\\OleAut"
0x18000c1d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c1df  call    cs:__imp_RegOpenKeyExW
0x18000c1e5  test    eax, eax
0x18000c1e7  jz      short loc_18000C1F5
0x18000c1e9  mov     cs:dword_1800C3680, 1
0x18000c1f3  jmp     short loc_18000C1A6
0x18000c1f5  mov     rcx, [rbp+hKey]; hKey
0x18000c1f9  lea     rax, [rbp+cbData]
0x18000c1fd  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c202  lea     r9, [rbp+Type]; lpType
0x18000c206  lea     rax, [rbp+Data]
0x18000c20a  mov     [rbp+Type], 0
0x18000c211  xor     r8d, r8d; lpReserved
0x18000c214  mov     [rsp+38h+phkResult], rax; lpData
0x18000c219  lea     rdx, ValueName; "DisableShield"
0x18000c220  mov     [rbp+Data], 0
0x18000c227  mov     [rbp+cbData], 4
0x18000c22e  call    cs:__imp_RegQueryValueExW
0x18000c234  test    eax, eax
0x18000c236  jnz     short loc_18000C247
0x18000c238  cmp     [rbp+Type], 4
0x18000c23c  jnz     short loc_18000C247
0x18000c23e  mov     eax, [rbp+Data]
0x18000c241  mov     cs:dword_1800C4118, eax
0x18000c247  mov     rcx, [rbp+hKey]; hKey
0x18000c24b  lea     rax, [rbp+cbData]
0x18000c24f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c254  lea     r9, [rbp+Type]; lpType
0x18000c258  lea     rax, [rbp+Data]
0x18000c25c  mov     [rbp+cbData], 4
0x18000c263  xor     r8d, r8d; lpReserved
0x18000c266  mov     [rsp+38h+phkResult], rax; lpData
0x18000c26b  lea     rdx, aDisable2gigres; "Disable2GigRestriction"
0x18000c272  call    cs:__imp_RegQueryValueExW
0x18000c278  test    eax, eax
0x18000c27a  jnz     short loc_18000C28B
0x18000c27c  cmp     [rbp+Type], 4
0x18000c280  jnz     short loc_18000C28B
0x18000c282  mov     eax, [rbp+Data]
0x18000c285  mov     cs:dword_1800C411C, eax
0x18000c28b  mov     rcx, [rbp+hKey]; hKey
0x18000c28f  lea     rax, [rbp+cbData]
0x18000c293  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c298  lea     r9, [rbp+Type]; lpType
0x18000c29c  lea     rax, [rbp+Data]
0x18000c2a0  mov     [rbp+cbData], 4
0x18000c2a7  xor     r8d, r8d; lpReserved
0x18000c2aa  mov     [rsp+38h+phkResult], rax; lpData
0x18000c2af  lea     rdx, aDisableremotei; "DisableRemoteIRecordInfoCheck"
0x18000c2b6  call    cs:__imp_RegQueryValueExW
0x18000c2bc  test    eax, eax
0x18000c2be  jnz     short loc_18000C2CF
0x18000c2c0  cmp     [rbp+Type], 4
0x18000c2c4  jnz     short loc_18000C2CF
0x18000c2c6  mov     eax, [rbp+Data]
0x18000c2c9  mov     cs:dword_1800C4120, eax
0x18000c2cf  mov     rcx, [rbp+hKey]; hKey
0x18000c2d3  lea     rax, [rbp+cbData]
0x18000c2d7  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c2dc  lea     r9, [rbp+Type]; lpType
0x18000c2e0  lea     rax, [rbp+Data]
0x18000c2e4  mov     [rbp+cbData], 4
0x18000c2eb  xor     r8d, r8d; lpReserved
0x18000c2ee  mov     [rsp+38h+phkResult], rax; lpData
0x18000c2f3  lea     rdx, aAssertonshield; "AssertOnShieldReject"
0x18000c2fa  call    cs:__imp_RegQueryValueExW
0x18000c300  test    eax, eax
0x18000c302  jnz     short loc_18000C313
0x18000c304  cmp     [rbp+Type], 4
0x18000c308  jnz     short loc_18000C313
0x18000c30a  mov     eax, [rbp+Data]
0x18000c30d  mov     cs:dword_1800C4124, eax
0x18000c313  mov     rcx, [rbp+hKey]; hKey
0x18000c317  lea     rax, [rbp+cbData]
0x18000c31b  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c320  lea     r9, [rbp+Type]; lpType
0x18000c324  lea     rax, [rbp+Data]
0x18000c328  mov     [rbp+cbData], 4
0x18000c32f  xor     r8d, r8d; lpReserved
0x18000c332  mov     [rsp+38h+phkResult], rax; lpData
0x18000c337  lea     rdx, aEnableups; "EnableUPS"
0x18000c33e  call    cs:__imp_RegQueryValueExW
0x18000c344  test    eax, eax
0x18000c346  jnz     short loc_18000C357
0x18000c348  cmp     [rbp+Type], 4
0x18000c34c  jnz     short loc_18000C357
0x18000c34e  mov     eax, [rbp+Data]
0x18000c351  mov     cs:dword_1800C4128, eax
0x18000c357  mov     rcx, [rbp+hKey]; hKey
0x18000c35b  lea     rax, [rbp+cbData]
0x18000c35f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c364  lea     r9, [rbp+Type]; lpType
0x18000c368  lea     rax, [rbp+Data]
0x18000c36c  mov     [rbp+cbData], 4
0x18000c373  xor     r8d, r8d; lpReserved
0x18000c376  mov     [rsp+38h+phkResult], rax; lpData
0x18000c37b  lea     rdx, aDisablebstrval; "DisableBSTRValidation"
0x18000c382  call    cs:__imp_RegQueryValueExW
0x18000c388  test    eax, eax
0x18000c38a  jnz     short loc_18000C39B
0x18000c38c  cmp     [rbp+Type], 4
0x18000c390  jnz     short loc_18000C39B
0x18000c392  mov     eax, [rbp+Data]
0x18000c395  mov     cs:dword_1800C412C, eax
0x18000c39b  mov     rcx, [rbp+hKey]; hKey
0x18000c39f  lea     rax, [rbp+cbData]
0x18000c3a3  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c3a8  lea     r9, [rbp+Type]; lpType
0x18000c3ac  lea     rax, [rbp+Data]
0x18000c3b0  mov     [rbp+cbData], 4
0x18000c3b7  xor     r8d, r8d; lpReserved
0x18000c3ba  mov     [rsp+38h+phkResult], rax; lpData
0x18000c3bf  lea     rdx, aUser1; "User1"
0x18000c3c6  call    cs:__imp_RegQueryValueExW
0x18000c3cc  test    eax, eax
0x18000c3ce  jnz     short loc_18000C3DF
0x18000c3d0  cmp     [rbp+Type], 4
0x18000c3d4  jnz     short loc_18000C3DF
0x18000c3d6  mov     eax, [rbp+Data]
0x18000c3d9  mov     cs:dword_1800C4130, eax
0x18000c3df  mov     rcx, [rbp+hKey]; hKey
0x18000c3e3  lea     rax, [rbp+cbData]
0x18000c3e7  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c3ec  lea     r9, [rbp+Type]; lpType
0x18000c3f0  lea     rax, [rbp+Data]
0x18000c3f4  mov     [rbp+cbData], 4
0x18000c3fb  xor     r8d, r8d; lpReserved
0x18000c3fe  mov     [rsp+38h+phkResult], rax; lpData
0x18000c403  lea     rdx, aUser2; "User2"
0x18000c40a  call    cs:__imp_RegQueryValueExW
0x18000c410  test    eax, eax
0x18000c412  jnz     short loc_18000C423
0x18000c414  cmp     [rbp+Type], 4
0x18000c418  jnz     short loc_18000C423
0x18000c41a  mov     eax, [rbp+Data]
0x18000c41d  mov     cs:dword_1800C4134, eax
0x18000c423  mov     rcx, [rbp+hKey]; hKey
0x18000c427  lea     rax, [rbp+cbData]
0x18000c42b  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c430  lea     r9, [rbp+Type]; lpType
0x18000c434  lea     rax, [rbp+Data]
0x18000c438  mov     [rbp+cbData], 4
0x18000c43f  xor     r8d, r8d; lpReserved
0x18000c442  mov     [rsp+38h+phkResult], rax; lpData
0x18000c447  lea     rdx, aUser3; "User3"
0x18000c44e  call    cs:__imp_RegQueryValueExW
0x18000c454  test    eax, eax
0x18000c456  jnz     short loc_18000C467
0x18000c458  cmp     [rbp+Type], 4
0x18000c45c  jnz     short loc_18000C467
0x18000c45e  mov     eax, [rbp+Data]
0x18000c461  mov     cs:dword_1800C4138, eax
0x18000c467  mov     rcx, [rbp+hKey]; hKey
0x18000c46b  call    cs:__imp_RegCloseKey
0x18000c471  jmp     loc_18000C1E9
```
