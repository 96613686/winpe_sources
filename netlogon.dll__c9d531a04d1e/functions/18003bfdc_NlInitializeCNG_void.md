# NlInitializeCNG(void)

- ea: `0x18003bfdc`
- end: `0x18003c247`
- name: `?NlInitializeCNG@@YAJXZ`
- size: `619`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006f490`

## callees

- `0x180007278`
- `0x18003bfdc`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003c002`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003c0bb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003c16e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003c21a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003c002`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003c0bb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003c16e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003c21a`
- `bcrypt!BCryptSetProperty` at `0x18003c03d`
- `bcrypt!BCryptSetProperty` at `0x18003c03d`
- `bcrypt!BCryptGetProperty` at `0x18003c084`
- `bcrypt!BCryptGetProperty` at `0x18003c0fd`
- `bcrypt!BCryptGetProperty` at `0x18003c13d`
- `bcrypt!BCryptGetProperty` at `0x18003c1b0`
- `bcrypt!BCryptGetProperty` at `0x18003c1f0`
- `bcrypt!BCryptGetProperty` at `0x18003c084`
- `bcrypt!BCryptGetProperty` at `0x18003c0fd`
- `bcrypt!BCryptGetProperty` at `0x18003c13d`
- `bcrypt!BCryptGetProperty` at `0x18003c1b0`
- `bcrypt!BCryptGetProperty` at `0x18003c1f0`

## string_xrefs

- `0x18003c00e`: `NlInitializeCNG: Failed to open AES algorithm 0x%x\n`
- `0x18003c0c7`: `NlInitializeCNG: Failed to open SHA256 algorithm 0x%x\n`
- `0x18003c17a`: `NlInitializeCNG: Failed to open SHA512 algorithm 0x%x\n`
- `0x18003c226`: `NlInitializeCNG: Failed to open SP800108 algorithm 0x%x\n`

## pseudocode

```c
__int64 NlInitializeCNG(void)
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  NTSTATUS v2; // eax
  NTSTATUS Property; // eax
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  ULONG pcbResult; // [rsp+40h] [rbp+8h] BYREF

  pcbResult = 0;
  v0 = BCryptOpenAlgorithmProvider(&NlGlobalAesHandle, L"AES", 0, 0);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v2 = BCryptSetProperty(NlGlobalAesHandle, L"ChainingMode", (PUCHAR)L"ChainingModeCFB", 0x20u, 0);
    v1 = v2;
    if ( v2 >= 0 )
    {
      Property = BCryptGetProperty(
                   NlGlobalAesHandle,
                   L"ObjectLength",
                   (PUCHAR)&NlGlobalAesKeyObjectSize,
                   4u,
                   &pcbResult,
                   0);
      v1 = Property;
      if ( pcbResult != 4 )
        return (unsigned int)-1073741595;
      if ( Property < 0 )
        return v1;
      v4 = BCryptOpenAlgorithmProvider(&NlGlobalSha256Handle, L"SHA256", 0, 8u);
      v1 = v4;
      if ( v4 < 0 )
      {
        NlPrintRoutine(0x100u, L"NlInitializeCNG: Failed to open SHA256 algorithm 0x%x\n", (unsigned int)v4);
        return v1;
      }
      v5 = BCryptGetProperty(NlGlobalSha256Handle, L"ObjectLength", &NlGlobalSha256HashObjectSize, 4u, &pcbResult, 0);
      v1 = v5;
      if ( pcbResult != 4 )
        return (unsigned int)-1073741595;
      if ( v5 < 0 )
        return v1;
      v6 = BCryptGetProperty(NlGlobalSha256Handle, L"HashDigestLength", &NlGlobalSha256HashSize, 4u, &pcbResult, 0);
      v1 = v6;
      if ( pcbResult != 4 )
        return (unsigned int)-1073741595;
      if ( v6 < 0 )
        return v1;
      v7 = BCryptOpenAlgorithmProvider(&NlGlobalSha512Handle, L"SHA512", 0, 8u);
      v1 = v7;
      if ( v7 < 0 )
      {
        NlPrintRoutine(0x100u, L"NlInitializeCNG: Failed to open SHA512 algorithm 0x%x\n", (unsigned int)v7);
        return v1;
      }
      v8 = BCryptGetProperty(
             NlGlobalSha512Handle,
             L"ObjectLength",
             (PUCHAR)&NlGlobalSha512HashObjectSize,
             4u,
             &pcbResult,
             0);
      v1 = v8;
      if ( pcbResult != 4 )
        return (unsigned int)-1073741595;
      if ( v8 < 0 )
        return v1;
      v9 = BCryptGetProperty(
             NlGlobalSha512Handle,
             L"HashDigestLength",
             (PUCHAR)&NlGlobalSha512HashSize,
             4u,
             &pcbResult,
             0);
      v1 = v9;
      if ( pcbResult == 4 )
      {
        if ( v9 >= 0 )
        {
          v10 = BCryptOpenAlgorithmProvider(&NlGlobalSP800108Handle, L"SP800_108_CTR_HMAC", 0, 0);
          v1 = v10;
          if ( v10 < 0 )
            NlPrintRoutine(0x100u, L"NlInitializeCNG: Failed to open SP800108 algorithm 0x%x\n", (unsigned int)v10);
        }
      }
      else
      {
        return (unsigned int)-1073741595;
      }
    }
    else
    {
      NlPrintRoutine(0x100u, L"NlInitializeCNG: Failed to set AES chaining mode 0x%x\n", (unsigned int)v2);
    }
  }
  else
  {
    NlPrintRoutine(0x100u, L"NlInitializeCNG: Failed to open AES algorithm 0x%x\n", (unsigned int)v0);
  }
  return v1;
}

```

## disassembly

```asm
0x18003bfdc  mov     [rsp+arg_8], rbx
0x18003bfe1  push    rsi
0x18003bfe2  sub     rsp, 30h
0x18003bfe6  xor     r9d, r9d; dwFlags
0x18003bfe9  mov     [rsp+38h+pcbResult], 0
0x18003bff1  xor     r8d, r8d; pszImplementation
0x18003bff4  lea     rdx, pszAlgId; "AES"
0x18003bffb  lea     rcx, ?NlGlobalAesHandle@@3PEAXEA; phAlgorithm
0x18003c002  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003c008  mov     ebx, eax
0x18003c00a  test    eax, eax
0x18003c00c  jns     short loc_18003C01A
0x18003c00e  lea     rdx, aNlinitializecn; "NlInitializeCNG: Failed to open AES alg"...
0x18003c015  jmp     loc_18003C22D
0x18003c01a  mov     rcx, cs:?NlGlobalAesHandle@@3PEAXEA; hObject
0x18003c021  lea     r8, pbInput; "ChainingModeCFB"
0x18003c028  mov     r9d, 20h ; ' '; cbInput
0x18003c02e  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18003c036  lea     rdx, aChainingmode; "ChainingMode"
0x18003c03d  call    cs:__imp_BCryptSetProperty
0x18003c043  mov     ebx, eax
0x18003c045  test    eax, eax
0x18003c047  jns     short loc_18003C055
0x18003c049  lea     rdx, aNlinitializecn_2; "NlInitializeCNG: Failed to set AES chai"...
0x18003c050  jmp     loc_18003C22D
0x18003c055  mov     rcx, cs:?NlGlobalAesHandle@@3PEAXEA; hObject
0x18003c05c  lea     rax, [rsp+38h+pcbResult]
0x18003c061  mov     esi, 4
0x18003c066  mov     [rsp+38h+var_10], 0; dwFlags
0x18003c06e  mov     r9d, esi; cbOutput
0x18003c071  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x18003c076  lea     r8, ?NlGlobalAesKeyObjectSize@@3KA; pbOutput
0x18003c07d  lea     rdx, aObjectlength; "ObjectLength"
0x18003c084  call    cs:__imp_BCryptGetProperty
0x18003c08a  mov     ebx, eax
0x18003c08c  cmp     [rsp+38h+pcbResult], esi
0x18003c090  jz      short loc_18003C09C
0x18003c092  mov     ebx, 0C00000E5h
0x18003c097  jmp     loc_18003C23A
0x18003c09c  test    eax, eax
0x18003c09e  js      loc_18003C23A
0x18003c0a4  mov     r9d, 8; dwFlags
0x18003c0aa  lea     rdx, aSha256; "SHA256"
0x18003c0b1  xor     r8d, r8d; pszImplementation
0x18003c0b4  lea     rcx, ?NlGlobalSha256Handle@@3PEAXEA; phAlgorithm
0x18003c0bb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003c0c1  mov     ebx, eax
0x18003c0c3  test    eax, eax
0x18003c0c5  jns     short loc_18003C0D3
0x18003c0c7  lea     rdx, aNlinitializecn_1; "NlInitializeCNG: Failed to open SHA256 "...
0x18003c0ce  jmp     loc_18003C22D
0x18003c0d3  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hObject
0x18003c0da  lea     rax, [rsp+38h+pcbResult]
0x18003c0df  mov     [rsp+38h+var_10], 0; dwFlags
0x18003c0e7  lea     r8, ?NlGlobalSha256HashObjectSize@@3KA; pbOutput
0x18003c0ee  mov     r9d, esi; cbOutput
0x18003c0f1  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x18003c0f6  lea     rdx, aObjectlength; "ObjectLength"
0x18003c0fd  call    cs:__imp_BCryptGetProperty
0x18003c103  mov     ebx, eax
0x18003c105  cmp     [rsp+38h+pcbResult], esi
0x18003c109  jnz     short loc_18003C092
0x18003c10b  test    eax, eax
0x18003c10d  js      loc_18003C23A
0x18003c113  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hObject
0x18003c11a  lea     rax, [rsp+38h+pcbResult]
0x18003c11f  mov     [rsp+38h+var_10], 0; dwFlags
0x18003c127  lea     r8, ?NlGlobalSha256HashSize@@3KA; pbOutput
0x18003c12e  mov     r9d, esi; cbOutput
0x18003c131  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x18003c136  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18003c13d  call    cs:__imp_BCryptGetProperty
0x18003c143  mov     ebx, eax
0x18003c145  cmp     [rsp+38h+pcbResult], esi
0x18003c149  jnz     loc_18003C092
0x18003c14f  test    eax, eax
0x18003c151  js      loc_18003C23A
0x18003c157  mov     r9d, 8; dwFlags
0x18003c15d  lea     rdx, aSha512; "SHA512"
0x18003c164  xor     r8d, r8d; pszImplementation
0x18003c167  lea     rcx, ?NlGlobalSha512Handle@@3PEAXEA; phAlgorithm
0x18003c16e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003c174  mov     ebx, eax
0x18003c176  test    eax, eax
0x18003c178  jns     short loc_18003C186
0x18003c17a  lea     rdx, aNlinitializecn_3; "NlInitializeCNG: Failed to open SHA512 "...
0x18003c181  jmp     loc_18003C22D
0x18003c186  mov     rcx, cs:?NlGlobalSha512Handle@@3PEAXEA; hObject
0x18003c18d  lea     rax, [rsp+38h+pcbResult]
0x18003c192  mov     [rsp+38h+var_10], 0; dwFlags
0x18003c19a  lea     r8, ?NlGlobalSha512HashObjectSize@@3KA; pbOutput
0x18003c1a1  mov     r9d, esi; cbOutput
0x18003c1a4  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x18003c1a9  lea     rdx, aObjectlength; "ObjectLength"
0x18003c1b0  call    cs:__imp_BCryptGetProperty
0x18003c1b6  mov     ebx, eax
0x18003c1b8  cmp     [rsp+38h+pcbResult], esi
0x18003c1bc  jnz     loc_18003C092
0x18003c1c2  test    eax, eax
0x18003c1c4  js      short loc_18003C23A
0x18003c1c6  mov     rcx, cs:?NlGlobalSha512Handle@@3PEAXEA; hObject
0x18003c1cd  lea     rax, [rsp+38h+pcbResult]
0x18003c1d2  mov     [rsp+38h+var_10], 0; dwFlags
0x18003c1da  lea     r8, ?NlGlobalSha512HashSize@@3KA; pbOutput
0x18003c1e1  mov     r9d, esi; cbOutput
0x18003c1e4  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x18003c1e9  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18003c1f0  call    cs:__imp_BCryptGetProperty
0x18003c1f6  mov     ebx, eax
0x18003c1f8  cmp     [rsp+38h+pcbResult], esi
0x18003c1fc  jnz     loc_18003C092
0x18003c202  test    eax, eax
0x18003c204  js      short loc_18003C23A
0x18003c206  xor     r9d, r9d; dwFlags
0x18003c209  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x18003c210  xor     r8d, r8d; pszImplementation
0x18003c213  lea     rcx, ?NlGlobalSP800108Handle@@3PEAXEA; phAlgorithm
0x18003c21a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003c220  mov     ebx, eax
0x18003c222  test    eax, eax
0x18003c224  jns     short loc_18003C23A
0x18003c226  lea     rdx, aNlinitializecn_0; "NlInitializeCNG: Failed to open SP80010"...
0x18003c22d  mov     r8d, eax
0x18003c230  mov     ecx, 100h; unsigned int
0x18003c235  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003c23a  mov     eax, ebx
0x18003c23c  mov     rbx, [rsp+38h+arg_8]
0x18003c241  add     rsp, 30h
0x18003c245  pop     rsi
0x18003c246  retn
```
