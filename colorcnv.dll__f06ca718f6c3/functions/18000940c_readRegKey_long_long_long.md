# readRegKey(long *,long *,long *)

- ea: `0x18000940c`
- end: `0x1800095c0`
- name: `?readRegKey@@YAHPEAJ00@Z`
- size: `436`
- prototype: `__int64 __fastcall(int *, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010bec`

## callees

- `0x18000940c`
- `0x18000ab30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800094fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009533`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000956d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800094fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009533`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000956d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009580`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000958a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009594`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000959e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009580`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000958a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009594`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000959e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000946e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000948b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800094a8`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800094c5`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000946e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000948b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800094a8`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800094c5`

## string_xrefs

- `0x1800094ee`: `Force NumThreads`

## pseudocode

```c
__int64 __fastcall readRegKey(int *a1, int *a2, int *a3)
{
  unsigned int v3; // ebx
  DWORD cbData; // [rsp+30h] [rbp-59h] BYREF
  DWORD Type; // [rsp+34h] [rbp-55h] BYREF
  HKEY v10; // [rsp+38h] [rbp-51h] BYREF
  HKEY v11; // [rsp+40h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-41h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-39h] BYREF
  BYTE Data[80]; // [rsp+60h] [rbp-29h] BYREF

  v3 = 0;
  cbData = 80;
  phkResult = 0;
  *a1 = -1;
  *a2 = -1;
  *a3 = -1;
  hKey = 0;
  v11 = 0;
  v10 = 0;
  Type = 0;
  if ( !RegOpenKeyW(HKEY_CURRENT_USER, L"SOFTWARE", &phkResult) )
  {
    if ( !RegOpenKeyW(phkResult, L"Microsoft", &hKey) )
    {
      if ( !RegOpenKeyW(hKey, L"Scrunch", &v11) )
      {
        if ( !RegOpenKeyW(v11, L"WMVideo", &v10) )
        {
          v3 = 1;
          if ( !RegQueryValueExW(v10, L"Force NumThreads", 0, &Type, Data, &cbData) )
            *a1 = *(_DWORD *)Data;
          if ( cbData < 0x50 )
          {
            if ( !RegQueryValueExW(v10, L"Force UVBilinearFilter", 0, &Type, Data, &cbData) )
              *a2 = *(_DWORD *)Data;
            if ( cbData < 0x50 && !RegQueryValueExW(v10, L"Force LongFilter", 0, &Type, Data, &cbData) )
              *a3 = *(_DWORD *)Data;
          }
          RegCloseKey(v10);
        }
        RegCloseKey(v11);
      }
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
  }
  return v3;
}

```

## disassembly

```asm
0x18000940c  push    rbp
0x18000940e  push    rbx
0x18000940f  push    rsi
0x180009410  push    rdi
0x180009411  push    r14
0x180009413  lea     rbp, [rsp-37h]
0x180009418  sub     rsp, 0C0h
0x18000941f  mov     rax, cs:__security_cookie
0x180009426  xor     rax, rsp
0x180009429  mov     [rbp+57h+var_30], rax
0x18000942d  xor     ebx, ebx
0x18000942f  mov     [rbp+57h+cbData], 50h ; 'P'
0x180009436  or      eax, 0FFFFFFFFh
0x180009439  mov     [rbp+57h+phkResult], rbx
0x18000943d  mov     [rcx], eax
0x18000943f  mov     rsi, r8
0x180009442  mov     [rdx], eax
0x180009444  mov     r14, rdx
0x180009447  mov     [r8], eax
0x18000944a  lea     rdx, SubKey; "SOFTWARE"
0x180009451  mov     rdi, rcx
0x180009454  mov     [rbp+57h+hKey], rbx
0x180009458  lea     r8, [rbp+57h+phkResult]; phkResult
0x18000945c  mov     [rbp+57h+var_A0], rbx
0x180009460  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009467  mov     [rbp+57h+var_A8], rbx
0x18000946b  mov     [rbp+57h+Type], ebx
0x18000946e  call    cs:__imp_RegOpenKeyW
0x180009474  test    eax, eax
0x180009476  jnz     loc_1800095A4
0x18000947c  mov     rcx, [rbp+57h+phkResult]; hKey
0x180009480  lea     r8, [rbp+57h+hKey]; phkResult
0x180009484  lea     rdx, aMicrosoft; "Microsoft"
0x18000948b  call    cs:__imp_RegOpenKeyW
0x180009491  test    eax, eax
0x180009493  jnz     loc_18000959A
0x180009499  mov     rcx, [rbp+57h+hKey]; hKey
0x18000949d  lea     r8, [rbp+57h+var_A0]; phkResult
0x1800094a1  lea     rdx, aScrunch; "Scrunch"
0x1800094a8  call    cs:__imp_RegOpenKeyW
0x1800094ae  test    eax, eax
0x1800094b0  jnz     loc_180009590
0x1800094b6  mov     rcx, [rbp+57h+var_A0]; hKey
0x1800094ba  lea     r8, [rbp+57h+var_A8]; phkResult
0x1800094be  lea     rdx, aWmvideo; "WMVideo"
0x1800094c5  call    cs:__imp_RegOpenKeyW
0x1800094cb  test    eax, eax
0x1800094cd  jnz     loc_180009586
0x1800094d3  mov     rcx, [rbp+57h+var_A8]; hKey
0x1800094d7  lea     ebx, [rax+1]
0x1800094da  lea     rax, [rbp+57h+cbData]
0x1800094de  xor     r8d, r8d; lpReserved
0x1800094e1  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800094e6  lea     r9, [rbp+57h+Type]; lpType
0x1800094ea  lea     rax, [rbp+57h+Data]
0x1800094ee  lea     rdx, ValueName; "Force NumThreads"
0x1800094f5  mov     [rsp+0E0h+lpData], rax; lpData
0x1800094fa  call    cs:__imp_RegQueryValueExW
0x180009500  test    eax, eax
0x180009502  jnz     short loc_180009509
0x180009504  mov     eax, dword ptr [rbp+57h+Data]
0x180009507  mov     [rdi], eax
0x180009509  cmp     [rbp+57h+cbData], 50h ; 'P'
0x18000950d  jnb     short loc_18000957C
0x18000950f  mov     rcx, [rbp+57h+var_A8]; hKey
0x180009513  lea     rax, [rbp+57h+cbData]
0x180009517  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x18000951c  lea     r9, [rbp+57h+Type]; lpType
0x180009520  lea     rax, [rbp+57h+Data]
0x180009524  xor     r8d, r8d; lpReserved
0x180009527  lea     rdx, aForceUvbilinea; "Force UVBilinearFilter"
0x18000952e  mov     [rsp+0E0h+lpData], rax; lpData
0x180009533  call    cs:__imp_RegQueryValueExW
0x180009539  test    eax, eax
0x18000953b  jnz     short loc_180009543
0x18000953d  mov     eax, dword ptr [rbp+57h+Data]
0x180009540  mov     [r14], eax
0x180009543  cmp     [rbp+57h+cbData], 50h ; 'P'
0x180009547  jnb     short loc_18000957C
0x180009549  mov     rcx, [rbp+57h+var_A8]; hKey
0x18000954d  lea     rax, [rbp+57h+cbData]
0x180009551  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180009556  lea     r9, [rbp+57h+Type]; lpType
0x18000955a  lea     rax, [rbp+57h+Data]
0x18000955e  xor     r8d, r8d; lpReserved
0x180009561  lea     rdx, aForceLongfilte; "Force LongFilter"
0x180009568  mov     [rsp+0E0h+lpData], rax; lpData
0x18000956d  call    cs:__imp_RegQueryValueExW
0x180009573  test    eax, eax
0x180009575  jnz     short loc_18000957C
0x180009577  mov     eax, dword ptr [rbp+57h+Data]
0x18000957a  mov     [rsi], eax
0x18000957c  mov     rcx, [rbp+57h+var_A8]; hKey
0x180009580  call    cs:__imp_RegCloseKey
0x180009586  mov     rcx, [rbp+57h+var_A0]; hKey
0x18000958a  call    cs:__imp_RegCloseKey
0x180009590  mov     rcx, [rbp+57h+hKey]; hKey
0x180009594  call    cs:__imp_RegCloseKey
0x18000959a  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000959e  call    cs:__imp_RegCloseKey
0x1800095a4  mov     eax, ebx
0x1800095a6  mov     rcx, [rbp+57h+var_30]
0x1800095aa  xor     rcx, rsp; StackCookie
0x1800095ad  call    __security_check_cookie
0x1800095b2  add     rsp, 0C0h
0x1800095b9  pop     r14
0x1800095bb  pop     rdi
0x1800095bc  pop     rsi
0x1800095bd  pop     rbx
0x1800095be  pop     rbp
0x1800095bf  retn
```
