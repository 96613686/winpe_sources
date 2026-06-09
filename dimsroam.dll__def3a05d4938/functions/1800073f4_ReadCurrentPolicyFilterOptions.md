# ReadCurrentPolicyFilterOptions

- ea: `0x1800073f4`
- end: `0x18000759f`
- name: `ReadCurrentPolicyFilterOptions`
- size: `427`
- prototype: `char __fastcall(LPCWSTR lpSubKey, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800071d0`

## callees

- `0x1800073f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800074c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007511`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000755c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800074c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007511`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000755c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007450`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000748c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007450`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000748c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180007461`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180007461`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007582`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007591`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007582`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007591`

## pseudocode

```c
char __fastcall ReadCurrentPolicyFilterOptions(LPCWSTR lpSubKey, __int64 a2)
{
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF

  phkResult = 0;
  *(_QWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  Data = 0;
  if ( lpSubKey )
    v3 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &hKey);
  else
    v3 = RegOpenCurrentUser(0x20019u, &hKey);
  if ( !v3 )
  {
    v3 = RegOpenKeyExW(hKey, L"Software\\Policies\\Microsoft\\Cryptography\\AutoEnrollment", 0, 0x20019u, &phkResult);
    if ( !v3 )
    {
      Type = 0;
      cbData = 4;
      v4 = RegQueryValueExW(phkResult, L"RoamSmartCardCertificates", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( !v4 && Type == 4 && cbData == 4 )
      {
        LOBYTE(v4) = Data != 0;
        *(_DWORD *)a2 = v4;
      }
      Type = 0;
      cbData = 4;
      v5 = RegQueryValueExW(phkResult, L"RoamUnusedDpapiKeys", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( !v5 && Type == 4 && cbData == 4 )
      {
        LOBYTE(v5) = Data != 0;
        *(_DWORD *)(a2 + 8) = v5;
      }
      Type = 0;
      cbData = 4;
      v3 = RegQueryValueExW(phkResult, L"RoamUnaffiliatedKeys", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( !v3 && Type == 4 && cbData == 4 )
      {
        LOBYTE(v3) = Data != 0;
        *(_DWORD *)(a2 + 4) = v3;
      }
    }
  }
  if ( phkResult )
    LOBYTE(v3) = RegCloseKey(phkResult);
  if ( hKey )
    LOBYTE(v3) = RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x1800073f4  push    rbp
0x1800073f6  push    rbx
0x1800073f7  push    rsi
0x1800073f8  mov     rbp, rsp
0x1800073fb  sub     rsp, 40h
0x1800073ff  xor     eax, eax
0x180007401  mov     [rbp+var_10], 0
0x180007409  mov     [rdx], rax
0x18000740c  mov     rbx, rdx
0x18000740f  mov     [rdx+8], eax
0x180007412  mov     [rbp+hKey], 0
0x18000741a  mov     [rbp+cbData], 0
0x180007421  mov     [rbp+Type], 0
0x180007428  mov     [rbp+Data], 0
0x18000742f  test    rcx, rcx
0x180007432  jz      short loc_180007458
0x180007434  lea     rax, [rbp+hKey]
0x180007438  mov     rdx, rcx; lpSubKey
0x18000743b  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180007442  mov     [rsp+40h+phkResult], rax; phkResult
0x180007447  mov     r9d, 20019h; samDesired
0x18000744d  xor     r8d, r8d; ulOptions
0x180007450  call    cs:__imp_RegOpenKeyExW
0x180007456  jmp     short loc_180007467
0x180007458  lea     rdx, [rbp+hKey]; phkResult
0x18000745c  mov     ecx, 20019h; samDesired
0x180007461  call    cs:__imp_RegOpenCurrentUser
0x180007467  test    eax, eax
0x180007469  jnz     loc_180007579
0x18000746f  mov     rcx, [rbp+hKey]; hKey
0x180007473  lea     rax, [rbp+var_10]
0x180007477  mov     r9d, 20019h; samDesired
0x18000747d  mov     [rsp+40h+phkResult], rax; phkResult
0x180007482  xor     r8d, r8d; ulOptions
0x180007485  lea     rdx, DRR_POLICY_KEY; "Software\\Policies\\Microsoft\\Cryptogr"...
0x18000748c  call    cs:__imp_RegOpenKeyExW
0x180007492  test    eax, eax
0x180007494  jnz     loc_180007579
0x18000749a  mov     rcx, [rbp+var_10]; hKey
0x18000749e  lea     esi, [rax+4]
0x1800074a1  mov     [rbp+Type], eax
0x1800074a4  lea     r9, [rbp+Type]; lpType
0x1800074a8  lea     rax, [rbp+cbData]
0x1800074ac  mov     [rbp+cbData], esi
0x1800074af  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800074b4  lea     rdx, DRR_POLICY_ROAM_SCCERTS; "RoamSmartCardCertificates"
0x1800074bb  lea     rax, [rbp+Data]
0x1800074bf  xor     r8d, r8d; lpReserved
0x1800074c2  mov     [rsp+40h+phkResult], rax; lpData
0x1800074c7  call    cs:__imp_RegQueryValueExW
0x1800074cd  test    eax, eax
0x1800074cf  jnz     short loc_1800074E3
0x1800074d1  cmp     [rbp+Type], esi
0x1800074d4  jnz     short loc_1800074E3
0x1800074d6  cmp     [rbp+cbData], esi
0x1800074d9  jnz     short loc_1800074E3
0x1800074db  cmp     [rbp+Data], eax
0x1800074de  setnz   al
0x1800074e1  mov     [rbx], eax
0x1800074e3  mov     rcx, [rbp+var_10]; hKey
0x1800074e7  lea     rax, [rbp+cbData]
0x1800074eb  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800074f0  lea     r9, [rbp+Type]; lpType
0x1800074f4  lea     rax, [rbp+Data]
0x1800074f8  mov     [rbp+Type], 0
0x1800074ff  xor     r8d, r8d; lpReserved
0x180007502  mov     [rsp+40h+phkResult], rax; lpData
0x180007507  lea     rdx, DRR_POLICY_ROAM_UNAFF_DPAPI_KEYS; "RoamUnusedDpapiKeys"
0x18000750e  mov     [rbp+cbData], esi
0x180007511  call    cs:__imp_RegQueryValueExW
0x180007517  test    eax, eax
0x180007519  jnz     short loc_18000752E
0x18000751b  cmp     [rbp+Type], esi
0x18000751e  jnz     short loc_18000752E
0x180007520  cmp     [rbp+cbData], esi
0x180007523  jnz     short loc_18000752E
0x180007525  cmp     [rbp+Data], eax
0x180007528  setnz   al
0x18000752b  mov     [rbx+8], eax
0x18000752e  mov     rcx, [rbp+var_10]; hKey
0x180007532  lea     rax, [rbp+cbData]
0x180007536  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000753b  lea     r9, [rbp+Type]; lpType
0x18000753f  lea     rax, [rbp+Data]
0x180007543  mov     [rbp+Type], 0
0x18000754a  xor     r8d, r8d; lpReserved
0x18000754d  mov     [rsp+40h+phkResult], rax; lpData
0x180007552  lea     rdx, DRR_POLICY_ROAM_UNAFF_KEYS; "RoamUnaffiliatedKeys"
0x180007559  mov     [rbp+cbData], esi
0x18000755c  call    cs:__imp_RegQueryValueExW
0x180007562  test    eax, eax
0x180007564  jnz     short loc_180007579
0x180007566  cmp     [rbp+Type], esi
0x180007569  jnz     short loc_180007579
0x18000756b  cmp     [rbp+cbData], esi
0x18000756e  jnz     short loc_180007579
0x180007570  cmp     [rbp+Data], eax
0x180007573  setnz   al
0x180007576  mov     [rbx+4], eax
0x180007579  mov     rcx, [rbp+var_10]; hKey
0x18000757d  test    rcx, rcx
0x180007580  jz      short loc_180007588
0x180007582  call    cs:__imp_RegCloseKey
0x180007588  mov     rcx, [rbp+hKey]; hKey
0x18000758c  test    rcx, rcx
0x18000758f  jz      short loc_180007597
0x180007591  call    cs:__imp_RegCloseKey
0x180007597  add     rsp, 40h
0x18000759b  pop     rsi
0x18000759c  pop     rbx
0x18000759d  pop     rbp
0x18000759e  retn
```
