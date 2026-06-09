# NlInitializeCNG(void)

- ea: `0x18003e584`
- end: `0x18003e834`
- name: `?NlInitializeCNG@@YAJXZ`
- size: `688`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800747cc`

## callees

- `0x180007518`
- `0x18003e584`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003e5aa`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003e675`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003e73e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003e800`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003e5aa`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003e675`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003e73e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003e800`
- `bcrypt!BCryptSetProperty` at `0x18003e5eb`
- `bcrypt!BCryptSetProperty` at `0x18003e5eb`
- `bcrypt!BCryptGetProperty` at `0x18003e638`
- `bcrypt!BCryptGetProperty` at `0x18003e6bd`
- `bcrypt!BCryptGetProperty` at `0x18003e707`
- `bcrypt!BCryptGetProperty` at `0x18003e786`
- `bcrypt!BCryptGetProperty` at `0x18003e7d0`
- `bcrypt!BCryptGetProperty` at `0x18003e638`
- `bcrypt!BCryptGetProperty` at `0x18003e6bd`
- `bcrypt!BCryptGetProperty` at `0x18003e707`
- `bcrypt!BCryptGetProperty` at `0x18003e786`
- `bcrypt!BCryptGetProperty` at `0x18003e7d0`

## string_xrefs

- `0x18003e5bc`: `NlInitializeCNG: Failed to open AES algorithm 0x%x\n`
- `0x18003e687`: `NlInitializeCNG: Failed to open SHA256 algorithm 0x%x\n`
- `0x18003e750`: `NlInitializeCNG: Failed to open SHA512 algorithm 0x%x\n`
- `0x18003e812`: `NlInitializeCNG: Failed to open SP800108 algorithm 0x%x\n`

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
0x18003e584  mov     [rsp+arg_8], rbx
0x18003e589  push    rsi
0x18003e58a  sub     rsp, 30h
0x18003e58e  xor     r9d, r9d; dwFlags
0x18003e591  mov     [rsp+38h+pcbResult], 0
0x18003e599  xor     r8d, r8d; pszImplementation
0x18003e59c  lea     rdx, pszAlgId; "AES"
0x18003e5a3  lea     rcx, ?NlGlobalAesHandle@@3PEAXEA; phAlgorithm
0x18003e5aa  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003e5b1  nop     dword ptr [rax+rax+00h]
0x18003e5b6  mov     ebx, eax
0x18003e5b8  test    eax, eax
0x18003e5ba  jns     short loc_18003E5C8
0x18003e5bc  lea     rdx, aNlinitializecn; "NlInitializeCNG: Failed to open AES alg"...
0x18003e5c3  jmp     loc_18003E819
0x18003e5c8  mov     rcx, cs:?NlGlobalAesHandle@@3PEAXEA; hObject
0x18003e5cf  lea     r8, pbInput; "ChainingModeCFB"
0x18003e5d6  mov     r9d, 20h ; ' '; cbInput
0x18003e5dc  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18003e5e4  lea     rdx, aChainingmode; "ChainingMode"
0x18003e5eb  call    cs:__imp_BCryptSetProperty
0x18003e5f2  nop     dword ptr [rax+rax+00h]
0x18003e5f7  mov     ebx, eax
0x18003e5f9  test    eax, eax
0x18003e5fb  jns     short loc_18003E609
0x18003e5fd  lea     rdx, aNlinitializecn_2; "NlInitializeCNG: Failed to set AES chai"...
0x18003e604  jmp     loc_18003E819
0x18003e609  mov     rcx, cs:?NlGlobalAesHandle@@3PEAXEA; hObject
0x18003e610  lea     rax, [rsp+38h+pcbResult]
0x18003e615  mov     esi, 4
0x18003e61a  mov     [rsp+38h+var_10], 0; dwFlags
0x18003e622  mov     r9d, esi; cbOutput
0x18003e625  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x18003e62a  lea     r8, ?NlGlobalAesKeyObjectSize@@3KA; pbOutput
0x18003e631  lea     rdx, aObjectlength; "ObjectLength"
0x18003e638  call    cs:__imp_BCryptGetProperty
0x18003e63f  nop     dword ptr [rax+rax+00h]
0x18003e644  mov     ebx, eax
0x18003e646  cmp     [rsp+38h+pcbResult], esi
0x18003e64a  jz      short loc_18003E656
0x18003e64c  mov     ebx, 0C00000E5h
0x18003e651  jmp     loc_18003E826
0x18003e656  test    eax, eax
0x18003e658  js      loc_18003E826
0x18003e65e  mov     r9d, 8; dwFlags
0x18003e664  lea     rdx, aSha256; "SHA256"
0x18003e66b  xor     r8d, r8d; pszImplementation
0x18003e66e  lea     rcx, ?NlGlobalSha256Handle@@3PEAXEA; phAlgorithm
0x18003e675  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003e67c  nop     dword ptr [rax+rax+00h]
0x18003e681  mov     ebx, eax
0x18003e683  test    eax, eax
0x18003e685  jns     short loc_18003E693
0x18003e687  lea     rdx, aNlinitializecn_1; "NlInitializeCNG: Failed to open SHA256 "...
0x18003e68e  jmp     loc_18003E819
0x18003e693  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hObject
0x18003e69a  lea     rax, [rsp+38h+pcbResult]
0x18003e69f  mov     [rsp+38h+var_10], 0; dwFlags
0x18003e6a7  lea     r8, ?NlGlobalSha256HashObjectSize@@3KA; pbOutput
0x18003e6ae  mov     r9d, esi; cbOutput
0x18003e6b1  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x18003e6b6  lea     rdx, aObjectlength; "ObjectLength"
0x18003e6bd  call    cs:__imp_BCryptGetProperty
0x18003e6c4  nop     dword ptr [rax+rax+00h]
0x18003e6c9  mov     ebx, eax
0x18003e6cb  cmp     [rsp+38h+pcbResult], esi
0x18003e6cf  jnz     loc_18003E64C
0x18003e6d5  test    eax, eax
0x18003e6d7  js      loc_18003E826
0x18003e6dd  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hObject
0x18003e6e4  lea     rax, [rsp+38h+pcbResult]
0x18003e6e9  mov     [rsp+38h+var_10], 0; dwFlags
0x18003e6f1  lea     r8, ?NlGlobalSha256HashSize@@3KA; pbOutput
0x18003e6f8  mov     r9d, esi; cbOutput
0x18003e6fb  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x18003e700  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18003e707  call    cs:__imp_BCryptGetProperty
0x18003e70e  nop     dword ptr [rax+rax+00h]
0x18003e713  mov     ebx, eax
0x18003e715  cmp     [rsp+38h+pcbResult], esi
0x18003e719  jnz     loc_18003E64C
0x18003e71f  test    eax, eax
0x18003e721  js      loc_18003E826
0x18003e727  mov     r9d, 8; dwFlags
0x18003e72d  lea     rdx, aSha512; "SHA512"
0x18003e734  xor     r8d, r8d; pszImplementation
0x18003e737  lea     rcx, ?NlGlobalSha512Handle@@3PEAXEA; phAlgorithm
0x18003e73e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003e745  nop     dword ptr [rax+rax+00h]
0x18003e74a  mov     ebx, eax
0x18003e74c  test    eax, eax
0x18003e74e  jns     short loc_18003E75C
0x18003e750  lea     rdx, aNlinitializecn_3; "NlInitializeCNG: Failed to open SHA512 "...
0x18003e757  jmp     loc_18003E819
0x18003e75c  mov     rcx, cs:?NlGlobalSha512Handle@@3PEAXEA; hObject
0x18003e763  lea     rax, [rsp+38h+pcbResult]
0x18003e768  mov     [rsp+38h+var_10], 0; dwFlags
0x18003e770  lea     r8, ?NlGlobalSha512HashObjectSize@@3KA; pbOutput
0x18003e777  mov     r9d, esi; cbOutput
0x18003e77a  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x18003e77f  lea     rdx, aObjectlength; "ObjectLength"
0x18003e786  call    cs:__imp_BCryptGetProperty
0x18003e78d  nop     dword ptr [rax+rax+00h]
0x18003e792  mov     ebx, eax
0x18003e794  cmp     [rsp+38h+pcbResult], esi
0x18003e798  jnz     loc_18003E64C
0x18003e79e  test    eax, eax
0x18003e7a0  js      loc_18003E826
0x18003e7a6  mov     rcx, cs:?NlGlobalSha512Handle@@3PEAXEA; hObject
0x18003e7ad  lea     rax, [rsp+38h+pcbResult]
0x18003e7b2  mov     [rsp+38h+var_10], 0; dwFlags
0x18003e7ba  lea     r8, ?NlGlobalSha512HashSize@@3KA; pbOutput
0x18003e7c1  mov     r9d, esi; cbOutput
0x18003e7c4  mov     qword ptr [rsp+38h+dwFlags], rax; pcbResult
0x18003e7c9  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18003e7d0  call    cs:__imp_BCryptGetProperty
0x18003e7d7  nop     dword ptr [rax+rax+00h]
0x18003e7dc  mov     ebx, eax
0x18003e7de  cmp     [rsp+38h+pcbResult], esi
0x18003e7e2  jnz     loc_18003E64C
0x18003e7e8  test    eax, eax
0x18003e7ea  js      short loc_18003E826
0x18003e7ec  xor     r9d, r9d; dwFlags
0x18003e7ef  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x18003e7f6  xor     r8d, r8d; pszImplementation
0x18003e7f9  lea     rcx, ?NlGlobalSP800108Handle@@3PEAXEA; phAlgorithm
0x18003e800  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003e807  nop     dword ptr [rax+rax+00h]
0x18003e80c  mov     ebx, eax
0x18003e80e  test    eax, eax
0x18003e810  jns     short loc_18003E826
0x18003e812  lea     rdx, aNlinitializecn_0; "NlInitializeCNG: Failed to open SP80010"...
0x18003e819  mov     r8d, eax
0x18003e81c  mov     ecx, 100h; unsigned int
0x18003e821  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003e826  mov     eax, ebx
0x18003e828  mov     rbx, [rsp+38h+arg_8]
0x18003e82d  add     rsp, 30h
0x18003e831  pop     rsi
0x18003e832  retn
```
