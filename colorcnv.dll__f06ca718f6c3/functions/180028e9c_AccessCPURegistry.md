# AccessCPURegistry

- ea: `0x180028e9c`
- end: `0x18002900e`
- name: `AccessCPURegistry`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a2b4`

## callees

- `0x180028e9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028ee6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f4a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028ee6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028f4a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028f7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028fbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028f7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028fbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028fdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028fea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028ff9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028fdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028fea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028ff9`

## string_xrefs

- `0x180028f76`: `NumThreads`

## pseudocode

```c
__int64 __fastcall AccessCPURegistry(int a1, BYTE *a2)
{
  unsigned int v2; // ebx
  HKEY v6; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD Type; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  cbData = 4;
  Type = 0;
  v6 = 0;
  phkResult = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE", 0, 1u, &hKey)
    || !hKey
    || RegOpenKeyExW(hKey, L"Microsoft", 0, 1u, &phkResult)
    || !phkResult
    || RegOpenKeyExW(phkResult, L"Scrunch", 0, 1u, &v6) )
  {
    goto LABEL_15;
  }
  if ( !a1 )
  {
    if ( !RegQueryValueExW(v6, L"CPU Downgrade Level", 0, &Type, a2, &cbData) && Type == 4 )
      goto LABEL_15;
LABEL_14:
    v2 = -1;
    goto LABEL_15;
  }
  if ( a1 != 1 || RegQueryValueExW(v6, L"NumThreads", 0, &Type, a2, &cbData) || Type != 4 )
    goto LABEL_14;
  if ( (unsigned int)(*(_DWORD *)a2 - 65) <= 0xFFFFFFBD )
    *(_DWORD *)a2 = 64;
LABEL_15:
  if ( v6 )
    RegCloseKey(v6);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180028e9c  mov     [rsp-18h+arg_0], rbx
0x180028ea1  push    rbp
0x180028ea2  push    rsi
0x180028ea3  push    rdi
0x180028ea4  mov     rbp, rsp
0x180028ea7  sub     rsp, 50h
0x180028eab  xor     ebx, ebx
0x180028ead  mov     [rbp+cbData], 4
0x180028eb4  mov     rsi, rdx
0x180028eb7  mov     [rbp+Type], ebx
0x180028eba  mov     edi, ecx
0x180028ebc  mov     [rbp+var_20], rbx
0x180028ec0  lea     rax, [rbp+hKey]
0x180028ec4  mov     [rbp+var_18], rbx
0x180028ec8  lea     r9d, [rbx+1]; samDesired
0x180028ecc  mov     [rbp+hKey], rbx
0x180028ed0  xor     r8d, r8d; ulOptions
0x180028ed3  mov     [rsp+50h+phkResult], rax; phkResult
0x180028ed8  lea     rdx, SubKey; "SOFTWARE"
0x180028edf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180028ee6  call    cs:__imp_RegOpenKeyExW
0x180028eec  test    eax, eax
0x180028eee  jnz     loc_180028FD2
0x180028ef4  mov     rcx, [rbp+hKey]; hKey
0x180028ef8  test    rcx, rcx
0x180028efb  jz      loc_180028FD2
0x180028f01  lea     rax, [rbp+var_18]
0x180028f05  xor     r8d, r8d; ulOptions
0x180028f08  lea     r9d, [rbx+1]; samDesired
0x180028f0c  mov     [rsp+50h+phkResult], rax; phkResult
0x180028f11  lea     rdx, aMicrosoft; "Microsoft"
0x180028f18  call    cs:__imp_RegOpenKeyExW
0x180028f1e  test    eax, eax
0x180028f20  jnz     loc_180028FD2
0x180028f26  mov     rcx, [rbp+var_18]; hKey
0x180028f2a  test    rcx, rcx
0x180028f2d  jz      loc_180028FD2
0x180028f33  lea     rax, [rbp+var_20]
0x180028f37  xor     r8d, r8d; ulOptions
0x180028f3a  lea     r9d, [rbx+1]; samDesired
0x180028f3e  mov     [rsp+50h+phkResult], rax; phkResult
0x180028f43  lea     rdx, aScrunch; "Scrunch"
0x180028f4a  call    cs:__imp_RegOpenKeyExW
0x180028f50  test    eax, eax
0x180028f52  jnz     short loc_180028FD2
0x180028f54  test    edi, edi
0x180028f56  jz      short loc_180028F9F
0x180028f58  cmp     edi, 1
0x180028f5b  jnz     short loc_180028FCF
0x180028f5d  mov     rcx, [rbp+var_20]; hKey
0x180028f61  lea     rax, [rbp+cbData]
0x180028f65  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180028f6a  lea     r9, [rbp+Type]; lpType
0x180028f6e  xor     r8d, r8d; lpReserved
0x180028f71  mov     [rsp+50h+phkResult], rsi; lpData
0x180028f76  lea     rdx, aNumthreads; "NumThreads"
0x180028f7d  call    cs:__imp_RegQueryValueExW
0x180028f83  test    eax, eax
0x180028f85  jnz     short loc_180028FCF
0x180028f87  cmp     [rbp+Type], 4
0x180028f8b  jnz     short loc_180028FCF
0x180028f8d  mov     eax, [rsi]
0x180028f8f  sub     eax, 41h ; 'A'
0x180028f92  cmp     eax, 0FFFFFFBDh
0x180028f95  ja      short loc_180028FD2
0x180028f97  mov     dword ptr [rsi], 40h ; '@'
0x180028f9d  jmp     short loc_180028FD2
0x180028f9f  mov     rcx, [rbp+var_20]; hKey
0x180028fa3  lea     rax, [rbp+cbData]
0x180028fa7  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180028fac  lea     r9, [rbp+Type]; lpType
0x180028fb0  xor     r8d, r8d; lpReserved
0x180028fb3  mov     [rsp+50h+phkResult], rsi; lpData
0x180028fb8  lea     rdx, aCpuDowngradeLe; "CPU Downgrade Level"
0x180028fbf  call    cs:__imp_RegQueryValueExW
0x180028fc5  test    eax, eax
0x180028fc7  jnz     short loc_180028FCF
0x180028fc9  cmp     [rbp+Type], 4
0x180028fcd  jz      short loc_180028FD2
0x180028fcf  or      ebx, 0FFFFFFFFh
0x180028fd2  mov     rcx, [rbp+var_20]; hKey
0x180028fd6  test    rcx, rcx
0x180028fd9  jz      short loc_180028FE1
0x180028fdb  call    cs:__imp_RegCloseKey
0x180028fe1  mov     rcx, [rbp+var_18]; hKey
0x180028fe5  test    rcx, rcx
0x180028fe8  jz      short loc_180028FF0
0x180028fea  call    cs:__imp_RegCloseKey
0x180028ff0  mov     rcx, [rbp+hKey]; hKey
0x180028ff4  test    rcx, rcx
0x180028ff7  jz      short loc_180028FFF
0x180028ff9  call    cs:__imp_RegCloseKey
0x180028fff  mov     eax, ebx
0x180029001  mov     rbx, [rsp+50h+arg_0]
0x180029006  add     rsp, 50h
0x18002900a  pop     rdi
0x18002900b  pop     rsi
0x18002900c  pop     rbp
0x18002900d  retn
```
