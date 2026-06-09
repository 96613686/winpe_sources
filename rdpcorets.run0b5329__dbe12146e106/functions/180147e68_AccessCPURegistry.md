# AccessCPURegistry

- ea: `0x180147e68`
- end: `0x180147fda`
- name: `AccessCPURegistry`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180148158`

## callees

- `0x180147e68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180147f49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180147f8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180147f49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180147f8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180147fa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180147fb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180147fc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180147fa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180147fb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180147fc5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180147eb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180147ee4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180147f16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180147eb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180147ee4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180147f16`

## string_xrefs

- `0x180147f42`: `NumThreads`

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
0x180147e68  mov     [rsp-18h+arg_0], rbx
0x180147e6d  push    rbp
0x180147e6e  push    rsi
0x180147e6f  push    rdi
0x180147e70  mov     rbp, rsp
0x180147e73  sub     rsp, 50h
0x180147e77  xor     ebx, ebx
0x180147e79  mov     [rbp+cbData], 4
0x180147e80  mov     rsi, rdx
0x180147e83  mov     [rbp+Type], ebx
0x180147e86  mov     edi, ecx
0x180147e88  mov     [rbp+var_20], rbx
0x180147e8c  lea     rax, [rbp+hKey]
0x180147e90  mov     [rbp+var_18], rbx
0x180147e94  lea     r9d, [rbx+1]; samDesired
0x180147e98  mov     [rbp+hKey], rbx
0x180147e9c  xor     r8d, r8d; ulOptions
0x180147e9f  mov     [rsp+50h+phkResult], rax; phkResult
0x180147ea4  lea     rdx, aSoftware; "SOFTWARE"
0x180147eab  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180147eb2  call    cs:__imp_RegOpenKeyExW
0x180147eb8  test    eax, eax
0x180147eba  jnz     loc_180147F9E
0x180147ec0  mov     rcx, [rbp+hKey]; hKey
0x180147ec4  test    rcx, rcx
0x180147ec7  jz      loc_180147F9E
0x180147ecd  lea     rax, [rbp+var_18]
0x180147ed1  xor     r8d, r8d; ulOptions
0x180147ed4  lea     r9d, [rbx+1]; samDesired
0x180147ed8  mov     [rsp+50h+phkResult], rax; phkResult
0x180147edd  lea     rdx, aMicrosoft; "Microsoft"
0x180147ee4  call    cs:__imp_RegOpenKeyExW
0x180147eea  test    eax, eax
0x180147eec  jnz     loc_180147F9E
0x180147ef2  mov     rcx, [rbp+var_18]; hKey
0x180147ef6  test    rcx, rcx
0x180147ef9  jz      loc_180147F9E
0x180147eff  lea     rax, [rbp+var_20]
0x180147f03  xor     r8d, r8d; ulOptions
0x180147f06  lea     r9d, [rbx+1]; samDesired
0x180147f0a  mov     [rsp+50h+phkResult], rax; phkResult
0x180147f0f  lea     rdx, aScrunch; "Scrunch"
0x180147f16  call    cs:__imp_RegOpenKeyExW
0x180147f1c  test    eax, eax
0x180147f1e  jnz     short loc_180147F9E
0x180147f20  test    edi, edi
0x180147f22  jz      short loc_180147F6B
0x180147f24  cmp     edi, 1
0x180147f27  jnz     short loc_180147F9B
0x180147f29  mov     rcx, [rbp+var_20]; hKey
0x180147f2d  lea     rax, [rbp+cbData]
0x180147f31  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180147f36  lea     r9, [rbp+Type]; lpType
0x180147f3a  xor     r8d, r8d; lpReserved
0x180147f3d  mov     [rsp+50h+phkResult], rsi; lpData
0x180147f42  lea     rdx, aNumthreads; "NumThreads"
0x180147f49  call    cs:__imp_RegQueryValueExW
0x180147f4f  test    eax, eax
0x180147f51  jnz     short loc_180147F9B
0x180147f53  cmp     [rbp+Type], 4
0x180147f57  jnz     short loc_180147F9B
0x180147f59  mov     eax, [rsi]
0x180147f5b  sub     eax, 41h ; 'A'
0x180147f5e  cmp     eax, 0FFFFFFBDh
0x180147f61  ja      short loc_180147F9E
0x180147f63  mov     dword ptr [rsi], 40h ; '@'
0x180147f69  jmp     short loc_180147F9E
0x180147f6b  mov     rcx, [rbp+var_20]; hKey
0x180147f6f  lea     rax, [rbp+cbData]
0x180147f73  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180147f78  lea     r9, [rbp+Type]; lpType
0x180147f7c  xor     r8d, r8d; lpReserved
0x180147f7f  mov     [rsp+50h+phkResult], rsi; lpData
0x180147f84  lea     rdx, aCpuDowngradeLe; "CPU Downgrade Level"
0x180147f8b  call    cs:__imp_RegQueryValueExW
0x180147f91  test    eax, eax
0x180147f93  jnz     short loc_180147F9B
0x180147f95  cmp     [rbp+Type], 4
0x180147f99  jz      short loc_180147F9E
0x180147f9b  or      ebx, 0FFFFFFFFh
0x180147f9e  mov     rcx, [rbp+var_20]; hKey
0x180147fa2  test    rcx, rcx
0x180147fa5  jz      short loc_180147FAD
0x180147fa7  call    cs:__imp_RegCloseKey
0x180147fad  mov     rcx, [rbp+var_18]; hKey
0x180147fb1  test    rcx, rcx
0x180147fb4  jz      short loc_180147FBC
0x180147fb6  call    cs:__imp_RegCloseKey
0x180147fbc  mov     rcx, [rbp+hKey]; hKey
0x180147fc0  test    rcx, rcx
0x180147fc3  jz      short loc_180147FCB
0x180147fc5  call    cs:__imp_RegCloseKey
0x180147fcb  mov     eax, ebx
0x180147fcd  mov     rbx, [rsp+50h+arg_0]
0x180147fd2  add     rsp, 50h
0x180147fd6  pop     rdi
0x180147fd7  pop     rsi
0x180147fd8  pop     rbp
0x180147fd9  retn
```
