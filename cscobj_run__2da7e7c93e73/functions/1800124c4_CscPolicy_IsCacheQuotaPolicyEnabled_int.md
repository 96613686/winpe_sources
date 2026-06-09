# CscPolicy_IsCacheQuotaPolicyEnabled(int *)

- ea: `0x1800124c4`
- end: `0x180012630`
- name: `?CscPolicy_IsCacheQuotaPolicyEnabled@@YAJPEAH@Z`
- size: `364`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e990`

## callees

- `0x1800124c4`
- `0x1800138b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012554`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012588`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001260b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012554`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012588`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001260b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001251f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800125d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001251f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800125d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800125a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800125a2`

## string_xrefs

- `0x1800125e5`: `CacheQuotaEnabled`
- `0x18001253e`: `CacheQuotaLimit`
- `0x180012575`: `CacheQuotaLimitUnpinned`

## pseudocode

```c
__int64 __fastcall CscPolicy_IsCacheQuotaPolicyEnabled(int *a1)
{
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  int v5; // [rsp+68h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+30h] BYREF

  *a1 = 0;
  v5 = 0;
  if ( (int)CscPolicyp_GetServiceActivePolicyAuthority((enum POLICY_AUTHORITY *)&v5) >= 0 )
  {
    if ( v5 )
    {
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, (&lpSubKey)[v5], 0, 1u, &phkResult) )
      {
        LODWORD(hKey) = 0;
        Type = 0;
        cbData = 4;
        if ( !RegQueryValueExW(phkResult, L"CacheQuotaEnabled", 0, &Type, (LPBYTE)&hKey, &cbData)
          && Type == 4
          && (_DWORD)hKey == 1 )
        {
          *a1 = 1;
        }
      }
    }
    else
    {
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\NetCache", 0, 1u, &hKey) )
      {
        Type = 0;
        if ( !RegQueryValueExW(hKey, L"CacheQuotaLimit", 0, &Type, 0, 0)
          && Type == 4
          && !RegQueryValueExW(hKey, L"CacheQuotaLimitUnpinned", 0, &Type, 0, 0)
          && Type == 4 )
        {
          *a1 = 1;
        }
        RegCloseKey(hKey);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800124c4  push    rbp
0x1800124c6  push    rdi
0x1800124c7  mov     rbp, rsp
0x1800124ca  sub     rsp, 48h
0x1800124ce  mov     rdi, rcx
0x1800124d1  mov     dword ptr [rcx], 0
0x1800124d7  lea     rcx, [rbp+arg_8]; enum POLICY_AUTHORITY *
0x1800124db  mov     [rbp+arg_8], 0
0x1800124e2  call    ?CscPolicyp_GetServiceActivePolicyAuthority@@YAJPEAW4POLICY_AUTHORITY@@@Z; CscPolicyp_GetServiceActivePolicyAuthority(POLICY_AUTHORITY *)
0x1800124e7  test    eax, eax
0x1800124e9  js      loc_180012627
0x1800124ef  movsxd  rax, [rbp+arg_8]
0x1800124f3  xor     r8d, r8d; ulOptions
0x1800124f6  mov     r9d, 1; samDesired
0x1800124fc  test    eax, eax
0x1800124fe  jnz     loc_1800125AA
0x180012504  mov     rdx, cs:lpSubKey; lpSubKey
0x18001250b  lea     rax, [rbp+hKey]
0x18001250f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012516  mov     [rsp+48h+phkResult], rax; phkResult
0x18001251b  mov     [rbp+hKey], r8
0x18001251f  call    cs:__imp_RegOpenKeyExW
0x180012525  test    eax, eax
0x180012527  jnz     loc_180012627
0x18001252d  mov     rcx, [rbp+hKey]; hKey
0x180012531  lea     r9, [rbp+Type]; lpType
0x180012535  mov     [rsp+48h+lpcbData], 0; lpcbData
0x18001253e  lea     rdx, ValueName; "CacheQuotaLimit"
0x180012545  xor     r8d, r8d; lpReserved
0x180012548  mov     [rsp+48h+phkResult], 0; lpData
0x180012551  mov     [rbp+Type], eax
0x180012554  call    cs:__imp_RegQueryValueExW
0x18001255a  test    eax, eax
0x18001255c  jnz     short loc_18001259E
0x18001255e  cmp     [rbp+Type], 4
0x180012562  jnz     short loc_18001259E
0x180012564  mov     rcx, [rbp+hKey]; hKey
0x180012568  lea     r9, [rbp+Type]; lpType
0x18001256c  mov     [rsp+48h+lpcbData], 0; lpcbData
0x180012575  lea     rdx, aCachequotalimi; "CacheQuotaLimitUnpinned"
0x18001257c  xor     r8d, r8d; lpReserved
0x18001257f  mov     [rsp+48h+phkResult], 0; lpData
0x180012588  call    cs:__imp_RegQueryValueExW
0x18001258e  test    eax, eax
0x180012590  jnz     short loc_18001259E
0x180012592  cmp     [rbp+Type], 4
0x180012596  jnz     short loc_18001259E
0x180012598  mov     dword ptr [rdi], 1
0x18001259e  mov     rcx, [rbp+hKey]; hKey
0x1800125a2  call    cs:__imp_RegCloseKey
0x1800125a8  jmp     short loc_180012627
0x1800125aa  mov     rdx, rax
0x1800125ad  mov     [rbp+var_18], 0
0x1800125b5  lea     rcx, lpSubKey
0x1800125bc  lea     rax, [rbp+var_18]
0x1800125c0  mov     [rsp+48h+phkResult], rax; phkResult
0x1800125c5  mov     rdx, [rcx+rdx*8]; lpSubKey
0x1800125c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800125d0  call    cs:__imp_RegOpenKeyExW
0x1800125d6  test    eax, eax
0x1800125d8  jnz     short loc_180012627
0x1800125da  mov     rcx, [rbp+var_18]; hKey
0x1800125de  lea     r9, [rbp+Type]; lpType
0x1800125e2  mov     dword ptr [rbp+hKey], eax
0x1800125e5  lea     rdx, aCachequotaenab; "CacheQuotaEnabled"
0x1800125ec  mov     [rbp+Type], eax
0x1800125ef  xor     r8d, r8d; lpReserved
0x1800125f2  lea     rax, [rbp+cbData]
0x1800125f6  mov     [rbp+cbData], 4
0x1800125fd  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180012602  lea     rax, [rbp+hKey]
0x180012606  mov     [rsp+48h+phkResult], rax; lpData
0x18001260b  call    cs:__imp_RegQueryValueExW
0x180012611  test    eax, eax
0x180012613  jnz     short loc_180012627
0x180012615  cmp     [rbp+Type], 4
0x180012619  jnz     short loc_180012627
0x18001261b  cmp     dword ptr [rbp+hKey], 1
0x18001261f  jnz     short loc_180012627
0x180012621  mov     dword ptr [rdi], 1
0x180012627  xor     eax, eax
0x180012629  add     rsp, 48h
0x18001262d  pop     rdi
0x18001262e  pop     rbp
0x18001262f  retn
```
