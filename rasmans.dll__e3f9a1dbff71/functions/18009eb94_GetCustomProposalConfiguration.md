# GetCustomProposalConfiguration

- ea: `0x18009eb94`
- end: `0x18009eed6`
- name: `GetCustomProposalConfiguration`
- size: `834`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18009e368`

## callees

- `0x18000bb90`
- `0x18009e9d0`
- `0x18009eb94`
- `0x18009f068`
- `0x18009f0bc`
- `0x1800e7260`

## import_xrefs

- `msvcrt!_stricmp` at `0x18009ecef`
- `msvcrt!_stricmp` at `0x18009ed0e`
- `msvcrt!_stricmp` at `0x18009ed2d`
- `msvcrt!_stricmp` at `0x18009ed4c`
- `msvcrt!_stricmp` at `0x18009ecef`
- `msvcrt!_stricmp` at `0x18009ed0e`
- `msvcrt!_stricmp` at `0x18009ed2d`
- `msvcrt!_stricmp` at `0x18009ed4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009ec13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009ecd5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009ed97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009ede1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009ee2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009ec13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009ecd5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009ed97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009ede1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18009ee2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18009ec9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18009ec9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ee4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009eea2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ee4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009eea2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009ec36`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009ec36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ee92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ee92`

## string_xrefs

- `0x18009ec5f`: `System\CurrentControlSet\Services\rasman\IKEv2`

## pseudocode

```c
_QWORD *__fastcall GetCustomProposalConfiguration(_DWORD *a1)
{
  _QWORD *i; // rdi
  HKEY CustomCofigurationKey; // r14
  unsigned int v4; // r15d
  __int64 *v5; // rdx
  int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  BYTE lpData[272]; // [rsp+40h] [rbp-C0h] BYREF
  char pszDest[272]; // [rsp+150h] [rbp+50h] BYREF

  i = 0;
  phkResult = 0;
  CustomCofigurationKey = (HKEY)GetCustomCofigurationKey();
  *a1 = 0;
  if ( CustomCofigurationKey )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( RegQueryValueExA(CustomCofigurationKey, "CustomProposalsCount", 0, 0, Data, &cbData) )
    {
LABEL_31:
      RegCloseKey(CustomCofigurationKey);
      return i;
    }
    if ( *(_DWORD *)Data )
    {
      v4 = 0;
      for ( i = LocalAlloc(0x40u, 32LL * *(unsigned int *)Data); v4 < *(_DWORD *)Data; ++v4 )
      {
        StringCchPrintfA(
          pszDest,
          0x104u,
          "%s\\%s\\%d",
          "System\\CurrentControlSet\\Services\\rasman\\IKEv2",
          "Proposals",
          v4);
        if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, pszDest, 0, 1u, &phkResult) )
        {
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "esp_encr", 0, 0, lpData, &cbData) )
          {
            if ( !_stricmp((const char *)lpData, "3DES") )
            {
              v5 = &qword_1800F8FB0;
            }
            else if ( !_stricmp((const char *)lpData, "DES") )
            {
              v5 = &qword_1800F8FD0;
            }
            else if ( !_stricmp((const char *)lpData, "AES_128") )
            {
              v5 = &qword_1800F8FE0;
            }
            else
            {
              v6 = _stricmp((const char *)lpData, "AES_256");
              v5 = &qword_1800F8FC8;
              if ( v6 )
                v5 = 0;
            }
            i[4 * (unsigned int)*a1 + 1] = v5;
          }
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "esp_auth", 0, 0, lpData, &cbData) )
          {
            v7 = 4LL * (unsigned int)*a1;
            i[v7 + 2] = StringToAuthTransform((char *)lpData);
          }
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "AH", 0, 0, lpData, &cbData) )
          {
            v8 = 4LL * (unsigned int)*a1;
            i[v8] = StringToAuthTransform((char *)lpData);
          }
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "PFS", 0, 0, lpData, &cbData) )
          {
            v9 = 4LL * (unsigned int)*a1;
            LODWORD(i[v9 + 3]) = StringToPFSTransform((char *)lpData);
          }
          RegCloseKey(phkResult);
          v10 = 4LL * (unsigned int)*a1;
          if ( i[v10] || i[v10 + 1] || i[v10 + 2] )
            ++*a1;
        }
      }
    }
  }
  if ( !*a1 && i )
  {
    LocalFree(i);
    i = 0;
  }
  if ( CustomCofigurationKey )
    goto LABEL_31;
  return i;
}

```

## disassembly

```asm
0x18009eb94  mov     [rsp-8+arg_8], rbx
0x18009eb99  mov     [rsp-8+arg_10], rsi
0x18009eb9e  push    rbp
0x18009eb9f  push    rdi
0x18009eba0  push    r13
0x18009eba2  push    r14
0x18009eba4  push    r15
0x18009eba6  lea     rbp, [rsp-170h]
0x18009ebae  sub     rsp, 270h
0x18009ebb5  mov     rax, cs:__security_cookie
0x18009ebbc  xor     rax, rsp
0x18009ebbf  mov     [rbp+190h+var_30], rax
0x18009ebc6  mov     rsi, rcx
0x18009ebc9  xor     edi, edi
0x18009ebcb  call    GetCustomCofigurationKey
0x18009ebd0  mov     [rsp+290h+phkResult], rdi
0x18009ebd5  mov     r14, rax
0x18009ebd8  mov     [rsi], edi
0x18009ebda  test    rax, rax
0x18009ebdd  jz      loc_18009EE85
0x18009ebe3  lea     rax, [rsp+290h+cbData]
0x18009ebe8  mov     dword ptr [rsp+290h+Data], edi
0x18009ebec  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18009ebf1  lea     rdx, aCustomproposal; "CustomProposalsCount"
0x18009ebf8  lea     rax, [rsp+290h+Data]
0x18009ebfd  mov     [rsp+290h+cbData], 4
0x18009ec05  xor     r9d, r9d; lpType
0x18009ec08  mov     [rsp+290h+lpData], rax; lpData
0x18009ec0d  xor     r8d, r8d; lpReserved
0x18009ec10  mov     rcx, r14; hKey
0x18009ec13  call    cs:__imp_RegQueryValueExA
0x18009ec19  test    eax, eax
0x18009ec1b  jnz     loc_18009EE9F
0x18009ec21  mov     eax, dword ptr [rsp+290h+Data]
0x18009ec25  test    eax, eax
0x18009ec27  jz      loc_18009EE85
0x18009ec2d  mov     edx, eax
0x18009ec2f  lea     ecx, [rdi+40h]; uFlags
0x18009ec32  shl     rdx, 5; uBytes
0x18009ec36  call    cs:__imp_LocalAlloc
0x18009ec3c  xor     r15d, r15d
0x18009ec3f  mov     rdi, rax
0x18009ec42  cmp     dword ptr [rsp+290h+Data], r15d
0x18009ec47  jbe     loc_18009EE85
0x18009ec4d  mov     r13d, 104h
0x18009ec53  lea     rax, aProposals; "Proposals"
0x18009ec5a  mov     dword ptr [rsp+290h+lpcbData], r15d
0x18009ec5f  lea     r9, aSystemCurrentc_26; "System\\CurrentControlSet\\Services\\ra"...
0x18009ec66  mov     [rsp+290h+lpData], rax
0x18009ec6b  lea     r8, aSSD; "%s\\%s\\%d"
0x18009ec72  mov     rdx, r13; cchDest
0x18009ec75  lea     rcx, [rbp+190h+pszDest]; pszDest
0x18009ec79  call    StringCchPrintfA
0x18009ec7e  lea     rax, [rsp+290h+phkResult]
0x18009ec83  mov     r9d, 1; samDesired
0x18009ec89  xor     r8d, r8d; ulOptions
0x18009ec8c  mov     [rsp+290h+lpData], rax; phkResult
0x18009ec91  lea     rdx, [rbp+190h+pszDest]; lpSubKey
0x18009ec95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009ec9c  call    cs:__imp_RegOpenKeyExA
0x18009eca2  test    eax, eax
0x18009eca4  jnz     loc_18009EE77
0x18009ecaa  mov     rcx, [rsp+290h+phkResult]; hKey
0x18009ecaf  lea     rax, [rsp+290h+cbData]
0x18009ecb4  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18009ecb9  lea     rdx, aEspEncr; "esp_encr"
0x18009ecc0  lea     rax, [rsp+290h+var_250]
0x18009ecc5  mov     [rsp+290h+cbData], r13d
0x18009ecca  xor     r9d, r9d; lpType
0x18009eccd  mov     [rsp+290h+lpData], rax; lpData
0x18009ecd2  xor     r8d, r8d; lpReserved
0x18009ecd5  call    cs:__imp_RegQueryValueExA
0x18009ecdb  test    eax, eax
0x18009ecdd  jnz     loc_18009ED6C
0x18009ece3  lea     rdx, a3des; "3DES"
0x18009ecea  lea     rcx, [rsp+290h+var_250]; String1
0x18009ecef  call    cs:__imp__stricmp
0x18009ecf5  test    eax, eax
0x18009ecf7  jnz     short loc_18009ED02
0x18009ecf9  lea     rdx, qword_1800F8FB0
0x18009ed00  jmp     short loc_18009ED61
0x18009ed02  lea     rdx, aDes; "DES"
0x18009ed09  lea     rcx, [rsp+290h+var_250]; String1
0x18009ed0e  call    cs:__imp__stricmp
0x18009ed14  test    eax, eax
0x18009ed16  jnz     short loc_18009ED21
0x18009ed18  lea     rdx, qword_1800F8FD0
0x18009ed1f  jmp     short loc_18009ED61
0x18009ed21  lea     rdx, aAes128; "AES_128"
0x18009ed28  lea     rcx, [rsp+290h+var_250]; String1
0x18009ed2d  call    cs:__imp__stricmp
0x18009ed33  test    eax, eax
0x18009ed35  jnz     short loc_18009ED40
0x18009ed37  lea     rdx, qword_1800F8FE0
0x18009ed3e  jmp     short loc_18009ED61
0x18009ed40  lea     rdx, aAes256; "AES_256"
0x18009ed47  lea     rcx, [rsp+290h+var_250]; String1
0x18009ed4c  call    cs:__imp__stricmp
0x18009ed52  xor     ecx, ecx
0x18009ed54  lea     rdx, qword_1800F8FC8
0x18009ed5b  test    eax, eax
0x18009ed5d  cmovnz  rdx, rcx
0x18009ed61  mov     eax, [rsi]
0x18009ed63  shl     rax, 5
0x18009ed67  mov     [rax+rdi+8], rdx
0x18009ed6c  mov     rcx, [rsp+290h+phkResult]; hKey
0x18009ed71  lea     rax, [rsp+290h+cbData]
0x18009ed76  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18009ed7b  lea     rdx, aEspAuth; "esp_auth"
0x18009ed82  lea     rax, [rsp+290h+var_250]
0x18009ed87  mov     [rsp+290h+cbData], r13d
0x18009ed8c  xor     r9d, r9d; lpType
0x18009ed8f  mov     [rsp+290h+lpData], rax; lpData
0x18009ed94  xor     r8d, r8d; lpReserved
0x18009ed97  call    cs:__imp_RegQueryValueExA
0x18009ed9d  test    eax, eax
0x18009ed9f  jnz     short loc_18009EDB6
0x18009eda1  mov     ebx, [rsi]
0x18009eda3  lea     rcx, [rsp+290h+var_250]; String1
0x18009eda8  shl     rbx, 5
0x18009edac  call    StringToAuthTransform
0x18009edb1  mov     [rbx+rdi+10h], rax
0x18009edb6  mov     rcx, [rsp+290h+phkResult]; hKey
0x18009edbb  lea     rax, [rsp+290h+cbData]
0x18009edc0  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18009edc5  lea     rdx, aAh; "AH"
0x18009edcc  lea     rax, [rsp+290h+var_250]
0x18009edd1  mov     [rsp+290h+cbData], r13d
0x18009edd6  xor     r9d, r9d; lpType
0x18009edd9  mov     [rsp+290h+lpData], rax; lpData
0x18009edde  xor     r8d, r8d; lpReserved
0x18009ede1  call    cs:__imp_RegQueryValueExA
0x18009ede7  test    eax, eax
0x18009ede9  jnz     short loc_18009EDFF
0x18009edeb  mov     ebx, [rsi]
0x18009eded  lea     rcx, [rsp+290h+var_250]; String1
0x18009edf2  shl     rbx, 5
0x18009edf6  call    StringToAuthTransform
0x18009edfb  mov     [rbx+rdi], rax
0x18009edff  mov     rcx, [rsp+290h+phkResult]; hKey
0x18009ee04  lea     rax, [rsp+290h+cbData]
0x18009ee09  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18009ee0e  lea     rdx, aPfs; "PFS"
0x18009ee15  lea     rax, [rsp+290h+var_250]
0x18009ee1a  mov     [rsp+290h+cbData], r13d
0x18009ee1f  xor     r9d, r9d; lpType
0x18009ee22  mov     [rsp+290h+lpData], rax; lpData
0x18009ee27  xor     r8d, r8d; lpReserved
0x18009ee2a  call    cs:__imp_RegQueryValueExA
0x18009ee30  test    eax, eax
0x18009ee32  jnz     short loc_18009EE48
0x18009ee34  mov     ebx, [rsi]
0x18009ee36  lea     rcx, [rsp+290h+var_250]; String1
0x18009ee3b  shl     rbx, 5
0x18009ee3f  call    StringToPFSTransform
0x18009ee44  mov     [rbx+rdi+18h], eax
0x18009ee48  mov     rcx, [rsp+290h+phkResult]; hKey
0x18009ee4d  call    cs:__imp_RegCloseKey
0x18009ee53  mov     ecx, [rsi]
0x18009ee55  mov     eax, ecx
0x18009ee57  shl     rax, 5
0x18009ee5b  cmp     qword ptr [rax+rdi], 0
0x18009ee60  jnz     short loc_18009EE72
0x18009ee62  cmp     qword ptr [rax+rdi+8], 0
0x18009ee68  jnz     short loc_18009EE72
0x18009ee6a  cmp     qword ptr [rax+rdi+10h], 0
0x18009ee70  jz      short loc_18009EE77
0x18009ee72  lea     eax, [rcx+1]
0x18009ee75  mov     [rsi], eax
0x18009ee77  inc     r15d
0x18009ee7a  cmp     r15d, dword ptr [rsp+290h+Data]
0x18009ee7f  jb      loc_18009EC53
0x18009ee85  cmp     dword ptr [rsi], 0
0x18009ee88  jnz     short loc_18009EE9A
0x18009ee8a  test    rdi, rdi
0x18009ee8d  jz      short loc_18009EE9A
0x18009ee8f  mov     rcx, rdi; hMem
0x18009ee92  call    cs:__imp_LocalFree
0x18009ee98  xor     edi, edi
0x18009ee9a  test    r14, r14
0x18009ee9d  jz      short loc_18009EEA8
0x18009ee9f  mov     rcx, r14; hKey
0x18009eea2  call    cs:__imp_RegCloseKey
0x18009eea8  mov     rax, rdi
0x18009eeab  mov     rcx, [rbp+190h+var_30]
0x18009eeb2  xor     rcx, rsp; StackCookie
0x18009eeb5  call    __security_check_cookie
0x18009eeba  lea     r11, [rsp+290h+var_20]
0x18009eec2  mov     rbx, [r11+38h]
0x18009eec6  mov     rsi, [r11+40h]
0x18009eeca  mov     rsp, r11
0x18009eecd  pop     r15
0x18009eecf  pop     r14
0x18009eed1  pop     r13
0x18009eed3  pop     rdi
0x18009eed4  pop     rbp
0x18009eed5  retn
```
