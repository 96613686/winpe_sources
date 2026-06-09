# GetL2tpConfigParams

- ea: `0x1800b1984`
- end: `0x1800b1b9e`
- name: `GetL2tpConfigParams`
- size: `538`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a117c`

## callees

- `0x1800ab634`
- `0x1800b1894`
- `0x1800b1984`
- `0x1800b1ba4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b1ae1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b1ae1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1b0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1b0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b1a24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b1a6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b1b5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b1a24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b1a6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b1b5b`

## pseudocode

```c
__int64 __fastcall GetL2tpConfigParams(HKEY hKey, char a2, __int64 a3, DWORD a4)
{
  unsigned int i; // edi
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  __int64 v9; // xmm1_8
  void *v10; // rdi
  HKEY v11; // rcx
  LSTATUS v12; // eax
  void *v13; // rax
  BYTE *lpData; // r14
  HKEY phkResult; // [rsp+30h] [rbp-50h] BYREF
  __int128 v17; // [rsp+38h] [rbp-48h] BYREF
  __int64 v18; // [rsp+48h] [rbp-38h]
  LPCWSTR lpValueName; // [rsp+50h] [rbp-30h]
  LPBYTE v20[5]; // [rsp+58h] [rbp-28h]
  DWORD cbData; // [rsp+B8h] [rbp+38h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+48h] BYREF

  Type = a4;
  LOBYTE(cbData) = a2;
  lpValueName = L"idleTimeout";
  v20[0] = (LPBYTE)&v17;
  v20[1] = (LPBYTE)L"saLifeTime";
  v20[2] = (LPBYTE)&v17 + 8;
  v20[3] = (LPBYTE)L"saDataSize";
  v20[4] = (LPBYTE)&v17 + 12;
  v17 = 0;
  v18 = 0;
  for ( i = 0; i < 3; ++i )
  {
    cbData = 4;
    Type = 4;
    v7 = RegQueryValueExW(hKey, (LPCWSTR)v20[2 * i - 1], 0, &Type, v20[2 * i], &cbData);
    if ( v7 )
      return v7;
  }
  cbData = 4;
  Type = 4;
  v8 = RegQueryValueExW(hKey, L"mmSaLifeTime", 0, &Type, (LPBYTE)(a3 + 24), &cbData);
  v7 = v8;
  if ( v8 )
  {
    if ( v8 != 2 )
      return v7;
    *(_DWORD *)(a3 + 24) = 28800;
  }
  v9 = v18;
  *(_OWORD *)a3 = v17;
  *(_QWORD *)(a3 + 16) = v9;
  v10 = (void *)MprCommonAlloc(24);
  if ( !v10 )
    return 8;
  v11 = 0;
  phkResult = 0;
  if ( hKey )
  {
    v12 = RegOpenKeyExW(hKey, L"L2TPCustomPolicy", 0, 0x20019u, &phkResult);
    v11 = phkResult;
    v7 = v12;
    if ( !v12 )
    {
      GetCustomPolicyRegParams(phkResult, v10);
      v11 = phkResult;
    }
  }
  else
  {
    v7 = 87;
  }
  if ( v11 )
    RegCloseKey(v11);
  if ( v7 )
  {
    if ( v7 != 2 )
    {
LABEL_22:
      MprCommonFree(v10);
      return v7;
    }
    v13 = 0;
  }
  else
  {
    v13 = v10;
    v10 = 0;
  }
  *(_QWORD *)(a3 + 16) = v13;
  cbData = 4;
  lpData = (BYTE *)(a3 + 4);
  Type = 4;
  v7 = RegQueryValueExW(hKey, L"EncryptionType", 0, &Type, lpData, &cbData);
  if ( v7 == 2 )
  {
    v7 = 0;
    *(_DWORD *)lpData = 1;
  }
  if ( v10 )
    goto LABEL_22;
  return v7;
}

```

## disassembly

```asm
0x1800b1984  mov     [rsp-28h+arg_0], rbx
0x1800b1989  mov     [rsp-28h+Type], r9d
0x1800b198e  mov     byte ptr [rsp-28h+cbData], dl
0x1800b1992  push    rbp
0x1800b1993  push    rsi
0x1800b1994  push    rdi
0x1800b1995  push    r14
0x1800b1997  push    r15
0x1800b1999  mov     rbp, rsp
0x1800b199c  sub     rsp, 80h
0x1800b19a3  lea     rax, aIdletimeout; "idleTimeout"
0x1800b19aa  xorps   xmm0, xmm0
0x1800b19ad  mov     [rbp+lpValueName], rax
0x1800b19b1  mov     r14, r8
0x1800b19b4  lea     rax, [rbp+var_48]
0x1800b19b8  mov     rsi, rcx
0x1800b19bb  mov     [rbp+var_28], rax
0x1800b19bf  lea     rax, aSalifetime; "saLifeTime"
0x1800b19c6  mov     [rbp+var_20], rax
0x1800b19ca  lea     rax, [rbp+var_48+8]
0x1800b19ce  mov     [rbp+var_18], rax
0x1800b19d2  lea     rax, aSadatasize; "saDataSize"
0x1800b19d9  mov     [rbp+var_10], rax
0x1800b19dd  lea     rax, [rbp+var_48+0Ch]
0x1800b19e1  mov     [rbp+var_8], rax
0x1800b19e5  xor     eax, eax
0x1800b19e7  movups  [rbp+var_48], xmm0
0x1800b19eb  mov     [rbp+var_38], rax
0x1800b19ef  xor     edi, edi
0x1800b19f1  lea     r15d, [rax+4]
0x1800b19f5  lea     rax, [rbp+cbData]
0x1800b19f9  mov     edx, edi
0x1800b19fb  add     rdx, rdx
0x1800b19fe  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800b1a03  lea     r9, [rbp+Type]; lpType
0x1800b1a07  mov     [rbp+cbData], r15d
0x1800b1a0b  xor     r8d, r8d; lpReserved
0x1800b1a0e  mov     [rbp+Type], r15d
0x1800b1a12  mov     rcx, rsi; hKey
0x1800b1a15  mov     rax, [rbp+rdx*8+var_28]
0x1800b1a1a  mov     rdx, [rbp+rdx*8+lpValueName]; lpValueName
0x1800b1a1f  mov     [rsp+80h+lpData], rax; lpData
0x1800b1a24  call    cs:__imp_RegQueryValueExW
0x1800b1a2b  nop     dword ptr [rax+rax+00h]
0x1800b1a30  mov     ebx, eax
0x1800b1a32  test    eax, eax
0x1800b1a34  jnz     loc_1800B1B84
0x1800b1a3a  inc     edi
0x1800b1a3c  cmp     edi, 3
0x1800b1a3f  jb      short loc_1800B19F5
0x1800b1a41  lea     rax, [rbp+cbData]
0x1800b1a45  mov     [rbp+cbData], r15d
0x1800b1a49  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800b1a4e  lea     rdi, [r14+18h]
0x1800b1a52  lea     r9, [rbp+Type]; lpType
0x1800b1a56  mov     [rsp+80h+lpData], rdi; lpData
0x1800b1a5b  xor     r8d, r8d; lpReserved
0x1800b1a5e  mov     [rbp+Type], r15d
0x1800b1a62  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x1800b1a69  mov     rcx, rsi; hKey
0x1800b1a6c  call    cs:__imp_RegQueryValueExW
0x1800b1a73  nop     dword ptr [rax+rax+00h]
0x1800b1a78  mov     ebx, eax
0x1800b1a7a  test    eax, eax
0x1800b1a7c  jz      short loc_1800B1A8D
0x1800b1a7e  cmp     eax, 2
0x1800b1a81  jnz     loc_1800B1B84
0x1800b1a87  mov     dword ptr [rdi], 7080h
0x1800b1a8d  movups  xmm0, [rbp+var_48]
0x1800b1a91  mov     ecx, 18h
0x1800b1a96  movsd   xmm1, [rbp+var_38]
0x1800b1a9b  movups  xmmword ptr [r14], xmm0
0x1800b1a9f  movsd   qword ptr [r14+10h], xmm1
0x1800b1aa5  call    MprCommonAlloc
0x1800b1aaa  mov     rdi, rax
0x1800b1aad  test    rax, rax
0x1800b1ab0  jnz     short loc_1800B1ABA
0x1800b1ab2  lea     ebx, [rax+8]
0x1800b1ab5  jmp     loc_1800B1B84
0x1800b1aba  xor     ecx, ecx; hKey
0x1800b1abc  mov     [rbp+phkResult], rcx
0x1800b1ac0  test    rsi, rsi
0x1800b1ac3  jz      short loc_1800B1B05
0x1800b1ac5  lea     rax, [rbp+phkResult]
0x1800b1ac9  mov     r9d, 20019h; samDesired
0x1800b1acf  xor     r8d, r8d; ulOptions
0x1800b1ad2  mov     [rsp+80h+lpData], rax; phkResult
0x1800b1ad7  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x1800b1ade  mov     rcx, rsi; hKey
0x1800b1ae1  call    cs:__imp_RegOpenKeyExW
0x1800b1ae8  nop     dword ptr [rax+rax+00h]
0x1800b1aed  mov     rcx, [rbp+phkResult]
0x1800b1af1  mov     ebx, eax
0x1800b1af3  test    eax, eax
0x1800b1af5  jnz     short loc_1800B1B0A
0x1800b1af7  mov     rdx, rdi
0x1800b1afa  call    GetCustomPolicyRegParams
0x1800b1aff  mov     rcx, [rbp+phkResult]
0x1800b1b03  jmp     short loc_1800B1B0A
0x1800b1b05  mov     ebx, 57h ; 'W'
0x1800b1b0a  test    rcx, rcx
0x1800b1b0d  jz      short loc_1800B1B1B
0x1800b1b0f  call    cs:__imp_RegCloseKey
0x1800b1b16  nop     dword ptr [rax+rax+00h]
0x1800b1b1b  test    ebx, ebx
0x1800b1b1d  jz      short loc_1800B1B28
0x1800b1b1f  cmp     ebx, 2
0x1800b1b22  jnz     short loc_1800B1B7C
0x1800b1b24  xor     eax, eax
0x1800b1b26  jmp     short loc_1800B1B2D
0x1800b1b28  mov     rax, rdi
0x1800b1b2b  xor     edi, edi
0x1800b1b2d  mov     [r14+10h], rax
0x1800b1b31  lea     r9, [rbp+Type]; lpType
0x1800b1b35  lea     rax, [rbp+cbData]
0x1800b1b39  mov     [rbp+cbData], r15d
0x1800b1b3d  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800b1b42  lea     rdx, aEncryptiontype; "EncryptionType"
0x1800b1b49  add     r14, r15
0x1800b1b4c  mov     [rbp+Type], r15d
0x1800b1b50  xor     r8d, r8d; lpReserved
0x1800b1b53  mov     [rsp+80h+lpData], r14; lpData
0x1800b1b58  mov     rcx, rsi; hKey
0x1800b1b5b  call    cs:__imp_RegQueryValueExW
0x1800b1b62  nop     dword ptr [rax+rax+00h]
0x1800b1b67  mov     ebx, eax
0x1800b1b69  cmp     eax, 2
0x1800b1b6c  jnz     short loc_1800B1B77
0x1800b1b6e  xor     ebx, ebx
0x1800b1b70  mov     dword ptr [r14], 1
0x1800b1b77  test    rdi, rdi
0x1800b1b7a  jz      short loc_1800B1B84
0x1800b1b7c  mov     rcx, rdi; lpMem
0x1800b1b7f  call    MprCommonFree
0x1800b1b84  mov     eax, ebx
0x1800b1b86  mov     rbx, [rsp+80h+arg_0]
0x1800b1b8e  add     rsp, 80h
0x1800b1b95  pop     r15
0x1800b1b97  pop     r14
0x1800b1b99  pop     rdi
0x1800b1b9a  pop     rsi
0x1800b1b9b  pop     rbp
0x1800b1b9c  retn
```
