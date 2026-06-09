# ASN1p_ReadConfig

- ea: `0x1800088a0`
- end: `0x18000899b`
- name: `ASN1p_ReadConfig`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800087e0`

## callees

- `0x1800088a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180008982`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180008982`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180008925`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180008925`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008993`

## pseudocode

```c
LSTATUS ASN1p_ReadConfig()
{
  LSTATUS result; // eax
  __int64 i; // rbx
  LPCSTR lpValueName; // [rsp+30h] [rbp-30h]
  LPBYTE lpData[5]; // [rsp+38h] [rbp-28h]
  DWORD cbData; // [rsp+70h] [rbp+10h] BYREF
  DWORD Type; // [rsp+78h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+20h] BYREF

  cbData = 0;
  lpValueName = "MaxRecursionLevel";
  Type = 0;
  lpData[0] = (LPBYTE)&g_dwMaxRecursionLevel;
  hKey = 0;
  lpData[1] = (LPBYTE)"MaxDecodeBufferSize";
  lpData[2] = (LPBYTE)&g_dwMaxDecodeBufferSize;
  lpData[3] = (LPBYTE)"DecodingRules";
  lpData[4] = (LPBYTE)&g_dwDecodingRules;
  result = RegOpenKeyExA(
             HKEY_LOCAL_MACHINE,
             "SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\msasn1",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    for ( i = 0; i != 3; ++i )
    {
      cbData = 4;
      result = RegQueryValueExA(hKey, (LPCSTR)lpData[2 * i - 1], 0, &Type, lpData[2 * i], &cbData);
    }
  }
  if ( hKey )
    result = RegCloseKey(hKey);
  g_bIsConfigInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x1800088a0  mov     [rsp-8+arg_18], rbx
0x1800088a5  push    rbp
0x1800088a6  mov     rbp, rsp
0x1800088a9  sub     rsp, 60h
0x1800088ad  lea     rax, aMaxrecursionle; "MaxRecursionLevel"
0x1800088b4  mov     [rbp+cbData], 0
0x1800088bb  mov     [rbp+lpValueName], rax
0x1800088bf  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800088c6  lea     rax, g_dwMaxRecursionLevel
0x1800088cd  mov     [rbp+Type], 0
0x1800088d4  mov     [rbp+lpData], rax
0x1800088d8  mov     r9d, 20019h; samDesired
0x1800088de  lea     rax, aMaxdecodebuffe; "MaxDecodeBufferSize"
0x1800088e5  mov     [rbp+hKey], 0
0x1800088ed  mov     [rbp+var_20], rax
0x1800088f1  xor     r8d, r8d; ulOptions
0x1800088f4  lea     rax, g_dwMaxDecodeBufferSize
0x1800088fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008902  mov     [rbp+var_18], rax
0x180008906  lea     rax, aDecodingrules; "DecodingRules"
0x18000890d  mov     [rbp+var_10], rax
0x180008911  lea     rax, g_dwDecodingRules
0x180008918  mov     [rbp+var_8], rax
0x18000891c  lea     rax, [rbp+hKey]
0x180008920  mov     [rsp+60h+phkResult], rax; phkResult
0x180008925  call    cs:__imp_RegOpenKeyExA
0x18000892b  test    eax, eax
0x18000892d  jz      short loc_180008950
0x18000892f  mov     rcx, [rbp+hKey]; hKey
0x180008933  test    rcx, rcx
0x180008936  jnz     short loc_180008993
0x180008938  mov     rbx, [rsp+60h+arg_18]
0x180008940  mov     cs:g_bIsConfigInitialized, 1
0x18000894a  add     rsp, 60h
0x18000894e  pop     rbp
0x18000894f  retn
0x180008950  xor     ebx, ebx
0x180008952  mov     rcx, [rbp+hKey]; hKey
0x180008956  lea     rax, [rbp+cbData]
0x18000895a  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000895f  lea     r9, [rbp+Type]; lpType
0x180008963  mov     rdx, rbx
0x180008966  mov     [rbp+cbData], 4
0x18000896d  add     rdx, rdx
0x180008970  xor     r8d, r8d; lpReserved
0x180008973  mov     rax, [rbp+rdx*8+lpData]
0x180008978  mov     rdx, [rbp+rdx*8+lpValueName]; lpValueName
0x18000897d  mov     [rsp+60h+phkResult], rax; lpData
0x180008982  call    cs:__imp_RegQueryValueExA
0x180008988  inc     rbx
0x18000898b  cmp     rbx, 3
0x18000898f  jnz     short loc_180008952
0x180008991  jmp     short loc_18000892F
0x180008993  call    cs:__imp_RegCloseKey
0x180008999  jmp     short loc_180008938
```
