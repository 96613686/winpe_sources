# IsJITEnabledInJScript9

- ea: `0x18021d570`
- end: `0x18021d6c6`
- name: `IsJITEnabledInJScript9`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18021e040`

## callees

- `0x18021d570`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18021d604`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18021d69e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18021d604`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x18021d69e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18021d5b5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18021d64d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18021d5b5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x18021d64d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18021d5f7`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18021d691`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18021d5f7`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x18021d691`

## pseudocode

```c
__int64 __fastcall IsJITEnabledInJScript9(_DWORD *a1)
{
  LSTATUS v2; // ebx
  LSTATUS v4; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-28h] BYREF
  BYTE v6[4]; // [rsp+34h] [rbp-24h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-1Ch] BYREF
  HKEY hKey[3]; // [rsp+40h] [rbp-18h] BYREF

  hKey[0] = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v6 = 0;
  *a1 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, hKey) < 0
    || (Type = 4,
        cbData = 4,
        v2 = RegQueryValueExW(hKey[0], L"EnableJITInJScript9", 0, &Type, Data, &cbData),
        RegCloseKey(hKey[0]),
        v2 < 0) )
  {
    v4 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, hKey);
    if ( v4 >= 0 )
    {
      cbData = 4;
      Type = 4;
      v4 = RegQueryValueExW(hKey[0], L"EnableJITInJScript9", 0, &cbData, v6, &Type);
      RegCloseKey(hKey[0]);
      if ( v4 >= 0 )
        *a1 = *(_DWORD *)v6 == 1;
    }
    return (unsigned int)v4;
  }
  else
  {
    *a1 = *(_DWORD *)Data == 1;
    return 0;
  }
}

```

## disassembly

```asm
0x18021d570  mov     rax, rsp
0x18021d573  mov     [rax+10h], rbx
0x18021d577  mov     [rax+18h], rsi
0x18021d57b  mov     [rax+8], rcx
0x18021d57f  push    rdi
0x18021d580  sub     rsp, 50h
0x18021d584  xor     esi, esi
0x18021d586  mov     rdi, rcx
0x18021d589  mov     [rax-18h], rsi
0x18021d58d  mov     r9d, 20019h; samDesired
0x18021d593  mov     [rax-28h], esi
0x18021d596  xor     r8d, r8d; ulOptions
0x18021d599  mov     [rax-24h], esi
0x18021d59c  lea     rax, [rax-18h]
0x18021d5a0  mov     [rcx], esi
0x18021d5a2  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x18021d5a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18021d5b0  mov     [rsp+58h+phkResult], rax; phkResult
0x18021d5b5  call    cs:__imp_RegOpenKeyExW
0x18021d5bb  test    eax, eax
0x18021d5bd  js      short loc_18021D62C
0x18021d5bf  mov     rcx, [rsp+58h+hKey]; hKey
0x18021d5c4  lea     rax, [rsp+58h+cbData]
0x18021d5c9  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18021d5ce  lea     r9, [rsp+58h+Type]; lpType
0x18021d5d3  lea     rax, [rsp+58h+Data]
0x18021d5d8  mov     [rsp+58h+Type], 4
0x18021d5e0  xor     r8d, r8d; lpReserved
0x18021d5e3  mov     [rsp+58h+phkResult], rax; lpData
0x18021d5e8  lea     rdx, aEnablejitinjsc; "EnableJITInJScript9"
0x18021d5ef  mov     [rsp+58h+cbData], 4
0x18021d5f7  call    cs:__imp_RegQueryValueExW
0x18021d5fd  mov     rcx, [rsp+58h+hKey]; hKey
0x18021d602  mov     ebx, eax
0x18021d604  call    cs:__imp_RegCloseKey
0x18021d60a  test    ebx, ebx
0x18021d60c  js      short loc_18021D62C
0x18021d60e  cmp     dword ptr [rsp+58h+Data], 1
0x18021d613  mov     eax, esi
0x18021d615  setz    al
0x18021d618  mov     [rdi], eax
0x18021d61a  xor     eax, eax
0x18021d61c  mov     rbx, [rsp+58h+arg_8]
0x18021d621  mov     rsi, [rsp+58h+arg_10]
0x18021d626  add     rsp, 50h
0x18021d62a  pop     rdi
0x18021d62b  retn
0x18021d62c  lea     rax, [rsp+58h+hKey]
0x18021d631  mov     r9d, 20019h; samDesired
0x18021d637  xor     r8d, r8d; ulOptions
0x18021d63a  mov     [rsp+58h+phkResult], rax; phkResult
0x18021d63f  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x18021d646  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18021d64d  call    cs:__imp_RegOpenKeyExW
0x18021d653  mov     ebx, eax
0x18021d655  test    eax, eax
0x18021d657  js      short loc_18021D6B4
0x18021d659  mov     rcx, [rsp+58h+hKey]; hKey
0x18021d65e  lea     rax, [rsp+58h+Type]
0x18021d663  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18021d668  lea     r9, [rsp+58h+cbData]; lpType
0x18021d66d  lea     rax, [rsp+58h+var_24]
0x18021d672  mov     [rsp+58h+cbData], 4
0x18021d67a  xor     r8d, r8d; lpReserved
0x18021d67d  mov     [rsp+58h+phkResult], rax; lpData
0x18021d682  lea     rdx, aEnablejitinjsc; "EnableJITInJScript9"
0x18021d689  mov     [rsp+58h+Type], 4
0x18021d691  call    cs:__imp_RegQueryValueExW
0x18021d697  mov     rcx, [rsp+58h+hKey]; hKey
0x18021d69c  mov     ebx, eax
0x18021d69e  call    cs:__imp_RegCloseKey
0x18021d6a4  test    ebx, ebx
0x18021d6a6  js      short loc_18021D6B4
0x18021d6a8  cmp     dword ptr [rsp+58h+var_24], 1
0x18021d6ad  mov     eax, esi
0x18021d6af  setz    al
0x18021d6b2  mov     [rdi], eax
0x18021d6b4  mov     rsi, [rsp+58h+arg_10]
0x18021d6b9  mov     eax, ebx
0x18021d6bb  mov     rbx, [rsp+58h+arg_8]
0x18021d6c0  add     rsp, 50h
0x18021d6c4  pop     rdi
0x18021d6c5  retn
```
