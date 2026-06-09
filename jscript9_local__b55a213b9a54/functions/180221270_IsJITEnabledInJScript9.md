# IsJITEnabledInJScript9

- ea: `0x180221270`
- end: `0x1802213ec`
- name: `IsJITEnabledInJScript9`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180221d84`

## callees

- `0x180221270`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180221310`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1802213bd`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180221310`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1802213bd`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1802212b5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180221360`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1802212b5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180221360`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1802212fd`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1802213aa`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1802212fd`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1802213aa`

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
0x180221270  mov     rax, rsp
0x180221273  mov     [rax+10h], rbx
0x180221277  mov     [rax+18h], rsi
0x18022127b  mov     [rax+8], rcx
0x18022127f  push    rdi
0x180221280  sub     rsp, 50h
0x180221284  xor     esi, esi
0x180221286  mov     rdi, rcx
0x180221289  mov     [rax-18h], rsi
0x18022128d  mov     r9d, 20019h; samDesired
0x180221293  mov     [rax-28h], esi
0x180221296  xor     r8d, r8d; ulOptions
0x180221299  mov     [rax-24h], esi
0x18022129c  lea     rax, [rax-18h]
0x1802212a0  mov     [rcx], esi
0x1802212a2  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x1802212a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802212b0  mov     [rsp+58h+phkResult], rax; phkResult
0x1802212b5  call    cs:__imp_RegOpenKeyExW
0x1802212bc  nop     dword ptr [rax+rax+00h]
0x1802212c1  test    eax, eax
0x1802212c3  js      short loc_18022133F
0x1802212c5  mov     rcx, [rsp+58h+hKey]; hKey
0x1802212ca  lea     rax, [rsp+58h+cbData]
0x1802212cf  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1802212d4  lea     r9, [rsp+58h+Type]; lpType
0x1802212d9  lea     rax, [rsp+58h+Data]
0x1802212de  mov     [rsp+58h+Type], 4
0x1802212e6  xor     r8d, r8d; lpReserved
0x1802212e9  mov     [rsp+58h+phkResult], rax; lpData
0x1802212ee  lea     rdx, aEnablejitinjsc; "EnableJITInJScript9"
0x1802212f5  mov     [rsp+58h+cbData], 4
0x1802212fd  call    cs:__imp_RegQueryValueExW
0x180221304  nop     dword ptr [rax+rax+00h]
0x180221309  mov     rcx, [rsp+58h+hKey]; hKey
0x18022130e  mov     ebx, eax
0x180221310  call    cs:__imp_RegCloseKey
0x180221317  nop     dword ptr [rax+rax+00h]
0x18022131c  test    ebx, ebx
0x18022131e  js      short loc_18022133F
0x180221320  cmp     dword ptr [rsp+58h+Data], 1
0x180221325  mov     eax, esi
0x180221327  setz    al
0x18022132a  mov     [rdi], eax
0x18022132c  xor     eax, eax
0x18022132e  mov     rbx, [rsp+58h+arg_8]
0x180221333  mov     rsi, [rsp+58h+arg_10]
0x180221338  add     rsp, 50h
0x18022133c  pop     rdi
0x18022133d  retn
0x18022133f  lea     rax, [rsp+58h+hKey]
0x180221344  mov     r9d, 20019h; samDesired
0x18022134a  xor     r8d, r8d; ulOptions
0x18022134d  mov     [rsp+58h+phkResult], rax; phkResult
0x180221352  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x180221359  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180221360  call    cs:__imp_RegOpenKeyExW
0x180221367  nop     dword ptr [rax+rax+00h]
0x18022136c  mov     ebx, eax
0x18022136e  test    eax, eax
0x180221370  js      short loc_1802213D9
0x180221372  mov     rcx, [rsp+58h+hKey]; hKey
0x180221377  lea     rax, [rsp+58h+Type]
0x18022137c  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180221381  lea     r9, [rsp+58h+cbData]; lpType
0x180221386  lea     rax, [rsp+58h+var_24]
0x18022138b  mov     [rsp+58h+cbData], 4
0x180221393  xor     r8d, r8d; lpReserved
0x180221396  mov     [rsp+58h+phkResult], rax; lpData
0x18022139b  lea     rdx, aEnablejitinjsc; "EnableJITInJScript9"
0x1802213a2  mov     [rsp+58h+Type], 4
0x1802213aa  call    cs:__imp_RegQueryValueExW
0x1802213b1  nop     dword ptr [rax+rax+00h]
0x1802213b6  mov     rcx, [rsp+58h+hKey]; hKey
0x1802213bb  mov     ebx, eax
0x1802213bd  call    cs:__imp_RegCloseKey
0x1802213c4  nop     dword ptr [rax+rax+00h]
0x1802213c9  test    ebx, ebx
0x1802213cb  js      short loc_1802213D9
0x1802213cd  cmp     dword ptr [rsp+58h+var_24], 1
0x1802213d2  mov     eax, esi
0x1802213d4  setz    al
0x1802213d7  mov     [rdi], eax
0x1802213d9  mov     rsi, [rsp+58h+arg_10]
0x1802213de  mov     eax, ebx
0x1802213e0  mov     rbx, [rsp+58h+arg_8]
0x1802213e5  add     rsp, 50h
0x1802213e9  pop     rdi
0x1802213ea  retn
```
