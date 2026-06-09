# GetCustomProposalConfiguration

- ea: `0x1800a41d8`
- end: `0x1800a456f`
- name: `GetCustomProposalConfiguration`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800a3928`

## callees

- `0x18000bf74`
- `0x1800a3ff4`
- `0x1800a41d8`
- `0x1800a4728`
- `0x1800a4788`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800a434b`
- `msvcrt!_stricmp` at `0x1800a4370`
- `msvcrt!_stricmp` at `0x1800a4395`
- `msvcrt!_stricmp` at `0x1800a43ba`
- `msvcrt!_stricmp` at `0x1800a434b`
- `msvcrt!_stricmp` at `0x1800a4370`
- `msvcrt!_stricmp` at `0x1800a4395`
- `msvcrt!_stricmp` at `0x1800a43ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a42ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a42ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a4257`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a432b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a440b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a445b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a44aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a4257`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a432b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a440b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a445b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a44aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a44d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4534`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a44d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4534`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a4280`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a4280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a451e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a451e`

## string_xrefs

- `0x1800a42af`: `System\CurrentControlSet\Services\rasman\IKEv2`

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
              v5 = &qword_1800FAF48;
            }
            else if ( !_stricmp((const char *)lpData, "DES") )
            {
              v5 = &qword_1800FAF68;
            }
            else if ( !_stricmp((const char *)lpData, "AES_128") )
            {
              v5 = &qword_1800FAF78;
            }
            else
            {
              v6 = _stricmp((const char *)lpData, "AES_256");
              v5 = &qword_1800FAF70;
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
0x1800a41d8  mov     [rsp-8+arg_8], rbx
0x1800a41dd  mov     [rsp-8+arg_10], rsi
0x1800a41e2  push    rbp
0x1800a41e3  push    rdi
0x1800a41e4  push    r13
0x1800a41e6  push    r14
0x1800a41e8  push    r15
0x1800a41ea  lea     rbp, [rsp-170h]
0x1800a41f2  sub     rsp, 270h
0x1800a41f9  mov     rax, cs:__security_cookie
0x1800a4200  xor     rax, rsp
0x1800a4203  mov     [rbp+190h+var_30], rax
0x1800a420a  mov     rsi, rcx
0x1800a420d  xor     edi, edi
0x1800a420f  call    GetCustomCofigurationKey
0x1800a4214  mov     [rsp+290h+phkResult], rdi
0x1800a4219  mov     r14, rax
0x1800a421c  mov     [rsi], edi
0x1800a421e  test    rax, rax
0x1800a4221  jz      loc_1800A4511
0x1800a4227  lea     rax, [rsp+290h+cbData]
0x1800a422c  mov     dword ptr [rsp+290h+Data], edi
0x1800a4230  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800a4235  lea     rdx, aCustomproposal; "CustomProposalsCount"
0x1800a423c  lea     rax, [rsp+290h+Data]
0x1800a4241  mov     [rsp+290h+cbData], 4
0x1800a4249  xor     r9d, r9d; lpType
0x1800a424c  mov     [rsp+290h+lpData], rax; lpData
0x1800a4251  xor     r8d, r8d; lpReserved
0x1800a4254  mov     rcx, r14; hKey
0x1800a4257  call    cs:__imp_RegQueryValueExA
0x1800a425e  nop     dword ptr [rax+rax+00h]
0x1800a4263  test    eax, eax
0x1800a4265  jnz     loc_1800A4531
0x1800a426b  mov     eax, dword ptr [rsp+290h+Data]
0x1800a426f  test    eax, eax
0x1800a4271  jz      loc_1800A4511
0x1800a4277  mov     edx, eax
0x1800a4279  lea     ecx, [rdi+40h]; uFlags
0x1800a427c  shl     rdx, 5; uBytes
0x1800a4280  call    cs:__imp_LocalAlloc
0x1800a4287  nop     dword ptr [rax+rax+00h]
0x1800a428c  xor     r15d, r15d
0x1800a428f  mov     rdi, rax
0x1800a4292  cmp     dword ptr [rsp+290h+Data], r15d
0x1800a4297  jbe     loc_1800A4511
0x1800a429d  mov     r13d, 104h
0x1800a42a3  lea     rax, aProposals; "Proposals"
0x1800a42aa  mov     dword ptr [rsp+290h+lpcbData], r15d
0x1800a42af  lea     r9, aSystemCurrentc_26; "System\\CurrentControlSet\\Services\\ra"...
0x1800a42b6  mov     [rsp+290h+lpData], rax
0x1800a42bb  lea     r8, aSSD; "%s\\%s\\%d"
0x1800a42c2  mov     rdx, r13; cchDest
0x1800a42c5  lea     rcx, [rbp+190h+pszDest]; pszDest
0x1800a42c9  call    StringCchPrintfA
0x1800a42ce  lea     rax, [rsp+290h+phkResult]
0x1800a42d3  mov     r9d, 1; samDesired
0x1800a42d9  xor     r8d, r8d; ulOptions
0x1800a42dc  mov     [rsp+290h+lpData], rax; phkResult
0x1800a42e1  lea     rdx, [rbp+190h+pszDest]; lpSubKey
0x1800a42e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a42ec  call    cs:__imp_RegOpenKeyExA
0x1800a42f3  nop     dword ptr [rax+rax+00h]
0x1800a42f8  test    eax, eax
0x1800a42fa  jnz     loc_1800A4503
0x1800a4300  mov     rcx, [rsp+290h+phkResult]; hKey
0x1800a4305  lea     rax, [rsp+290h+cbData]
0x1800a430a  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800a430f  lea     rdx, aEspEncr; "esp_encr"
0x1800a4316  lea     rax, [rsp+290h+var_250]
0x1800a431b  mov     [rsp+290h+cbData], r13d
0x1800a4320  xor     r9d, r9d; lpType
0x1800a4323  mov     [rsp+290h+lpData], rax; lpData
0x1800a4328  xor     r8d, r8d; lpReserved
0x1800a432b  call    cs:__imp_RegQueryValueExA
0x1800a4332  nop     dword ptr [rax+rax+00h]
0x1800a4337  test    eax, eax
0x1800a4339  jnz     loc_1800A43E0
0x1800a433f  lea     rdx, a3des; "3DES"
0x1800a4346  lea     rcx, [rsp+290h+var_250]; String1
0x1800a434b  call    cs:__imp__stricmp
0x1800a4352  nop     dword ptr [rax+rax+00h]
0x1800a4357  test    eax, eax
0x1800a4359  jnz     short loc_1800A4364
0x1800a435b  lea     rdx, qword_1800FAF48
0x1800a4362  jmp     short loc_1800A43D5
0x1800a4364  lea     rdx, aDes; "DES"
0x1800a436b  lea     rcx, [rsp+290h+var_250]; String1
0x1800a4370  call    cs:__imp__stricmp
0x1800a4377  nop     dword ptr [rax+rax+00h]
0x1800a437c  test    eax, eax
0x1800a437e  jnz     short loc_1800A4389
0x1800a4380  lea     rdx, qword_1800FAF68
0x1800a4387  jmp     short loc_1800A43D5
0x1800a4389  lea     rdx, aAes128; "AES_128"
0x1800a4390  lea     rcx, [rsp+290h+var_250]; String1
0x1800a4395  call    cs:__imp__stricmp
0x1800a439c  nop     dword ptr [rax+rax+00h]
0x1800a43a1  test    eax, eax
0x1800a43a3  jnz     short loc_1800A43AE
0x1800a43a5  lea     rdx, qword_1800FAF78
0x1800a43ac  jmp     short loc_1800A43D5
0x1800a43ae  lea     rdx, aAes256; "AES_256"
0x1800a43b5  lea     rcx, [rsp+290h+var_250]; String1
0x1800a43ba  call    cs:__imp__stricmp
0x1800a43c1  nop     dword ptr [rax+rax+00h]
0x1800a43c6  xor     ecx, ecx
0x1800a43c8  lea     rdx, qword_1800FAF70
0x1800a43cf  test    eax, eax
0x1800a43d1  cmovnz  rdx, rcx
0x1800a43d5  mov     eax, [rsi]
0x1800a43d7  shl     rax, 5
0x1800a43db  mov     [rax+rdi+8], rdx
0x1800a43e0  mov     rcx, [rsp+290h+phkResult]; hKey
0x1800a43e5  lea     rax, [rsp+290h+cbData]
0x1800a43ea  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800a43ef  lea     rdx, aEspAuth; "esp_auth"
0x1800a43f6  lea     rax, [rsp+290h+var_250]
0x1800a43fb  mov     [rsp+290h+cbData], r13d
0x1800a4400  xor     r9d, r9d; lpType
0x1800a4403  mov     [rsp+290h+lpData], rax; lpData
0x1800a4408  xor     r8d, r8d; lpReserved
0x1800a440b  call    cs:__imp_RegQueryValueExA
0x1800a4412  nop     dword ptr [rax+rax+00h]
0x1800a4417  test    eax, eax
0x1800a4419  jnz     short loc_1800A4430
0x1800a441b  mov     ebx, [rsi]
0x1800a441d  lea     rcx, [rsp+290h+var_250]; String1
0x1800a4422  shl     rbx, 5
0x1800a4426  call    StringToAuthTransform
0x1800a442b  mov     [rbx+rdi+10h], rax
0x1800a4430  mov     rcx, [rsp+290h+phkResult]; hKey
0x1800a4435  lea     rax, [rsp+290h+cbData]
0x1800a443a  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800a443f  lea     rdx, aAh; "AH"
0x1800a4446  lea     rax, [rsp+290h+var_250]
0x1800a444b  mov     [rsp+290h+cbData], r13d
0x1800a4450  xor     r9d, r9d; lpType
0x1800a4453  mov     [rsp+290h+lpData], rax; lpData
0x1800a4458  xor     r8d, r8d; lpReserved
0x1800a445b  call    cs:__imp_RegQueryValueExA
0x1800a4462  nop     dword ptr [rax+rax+00h]
0x1800a4467  test    eax, eax
0x1800a4469  jnz     short loc_1800A447F
0x1800a446b  mov     ebx, [rsi]
0x1800a446d  lea     rcx, [rsp+290h+var_250]; String1
0x1800a4472  shl     rbx, 5
0x1800a4476  call    StringToAuthTransform
0x1800a447b  mov     [rbx+rdi], rax
0x1800a447f  mov     rcx, [rsp+290h+phkResult]; hKey
0x1800a4484  lea     rax, [rsp+290h+cbData]
0x1800a4489  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800a448e  lea     rdx, aPfs; "PFS"
0x1800a4495  lea     rax, [rsp+290h+var_250]
0x1800a449a  mov     [rsp+290h+cbData], r13d
0x1800a449f  xor     r9d, r9d; lpType
0x1800a44a2  mov     [rsp+290h+lpData], rax; lpData
0x1800a44a7  xor     r8d, r8d; lpReserved
0x1800a44aa  call    cs:__imp_RegQueryValueExA
0x1800a44b1  nop     dword ptr [rax+rax+00h]
0x1800a44b6  test    eax, eax
0x1800a44b8  jnz     short loc_1800A44CE
0x1800a44ba  mov     ebx, [rsi]
0x1800a44bc  lea     rcx, [rsp+290h+var_250]; String1
0x1800a44c1  shl     rbx, 5
0x1800a44c5  call    StringToPFSTransform
0x1800a44ca  mov     [rbx+rdi+18h], eax
0x1800a44ce  mov     rcx, [rsp+290h+phkResult]; hKey
0x1800a44d3  call    cs:__imp_RegCloseKey
0x1800a44da  nop     dword ptr [rax+rax+00h]
0x1800a44df  mov     ecx, [rsi]
0x1800a44e1  mov     eax, ecx
0x1800a44e3  shl     rax, 5
0x1800a44e7  cmp     qword ptr [rax+rdi], 0
0x1800a44ec  jnz     short loc_1800A44FE
0x1800a44ee  cmp     qword ptr [rax+rdi+8], 0
0x1800a44f4  jnz     short loc_1800A44FE
0x1800a44f6  cmp     qword ptr [rax+rdi+10h], 0
0x1800a44fc  jz      short loc_1800A4503
0x1800a44fe  lea     eax, [rcx+1]
0x1800a4501  mov     [rsi], eax
0x1800a4503  inc     r15d
0x1800a4506  cmp     r15d, dword ptr [rsp+290h+Data]
0x1800a450b  jb      loc_1800A42A3
0x1800a4511  cmp     dword ptr [rsi], 0
0x1800a4514  jnz     short loc_1800A452C
0x1800a4516  test    rdi, rdi
0x1800a4519  jz      short loc_1800A452C
0x1800a451b  mov     rcx, rdi; hMem
0x1800a451e  call    cs:__imp_LocalFree
0x1800a4525  nop     dword ptr [rax+rax+00h]
0x1800a452a  xor     edi, edi
0x1800a452c  test    r14, r14
0x1800a452f  jz      short loc_1800A4540
0x1800a4531  mov     rcx, r14; hKey
0x1800a4534  call    cs:__imp_RegCloseKey
0x1800a453b  nop     dword ptr [rax+rax+00h]
0x1800a4540  mov     rax, rdi
0x1800a4543  mov     rcx, [rbp+190h+var_30]
0x1800a454a  xor     rcx, rsp; StackCookie
0x1800a454d  call    __security_check_cookie
0x1800a4552  lea     r11, [rsp+290h+var_20]
0x1800a455a  mov     rbx, [r11+38h]
0x1800a455e  mov     rsi, [r11+40h]
0x1800a4562  mov     rsp, r11
0x1800a4565  pop     r15
0x1800a4567  pop     r14
0x1800a4569  pop     r13
0x1800a456b  pop     rdi
0x1800a456c  pop     rbp
0x1800a456d  retn
```
