# SslOpenProvider

- ea: `0x18005d420`
- end: `0x18005d66a`
- name: `SslOpenProvider`
- size: `586`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180025c00`
- `0x18003af6c`
- `0x18003d980`
- `0x18005d420`
- `0x18009f650`
- `0x18009f6d0`
- `0x18009fa80`

## string_xrefs

- `0x18005d4f3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18005d5f9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18005d480`: `Microsoft SSL Protocol Provider`

## pseudocode

```c
__int64 __fastcall SslOpenProvider(__int64 **a1, const WCHAR *a2, unsigned int a3)
{
  __int64 *v3; // rbx
  const WCHAR *v6; // r12
  __int64 v7; // rdx
  NTSTATUS v8; // edi
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 *v13; // rax
  int Provider; // eax
  __int64 v15; // rcx
  PCRYPT_PROVIDER_REFS ppBuffer; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pcbBuffer; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[512]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = 0;
  pcbBuffer = 512;
  ppBuffer = (PCRYPT_PROVIDER_REFS)v19;
  if ( !a1 || (a3 & 0xFFFFFFFE) != 0 )
  {
    v8 = -1073741811;
    v11 = 2979;
    v12 = 3221225485LL;
    goto LABEL_21;
  }
  v6 = L"Microsoft SSL Protocol Provider";
  if ( a2 )
    v6 = a2;
  while ( 1 )
  {
    v8 = BCryptResolveProviders(0, 0x10002u, 0, v6, 2u, 0, &pcbBuffer, &ppBuffer);
    if ( v8 != -1073741789 )
      break;
    if ( ppBuffer != (PCRYPT_PROVIDER_REFS)v19 )
      MSCryptFree(ppBuffer);
    ppBuffer = (PCRYPT_PROVIDER_REFS)MSCryptAlloc(pcbBuffer, v7, v9, v10);
    if ( !ppBuffer )
    {
      v8 = -1073741801;
      DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3028);
      if ( !ppBuffer )
        break;
    }
  }
  if ( v8 < 0 )
  {
    v11 = 3035;
    v12 = (unsigned int)v8;
LABEL_21:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v11);
    goto LABEL_22;
  }
  v13 = (__int64 *)MSCryptAlloc(432, v7, v9, v10);
  v3 = v13;
  if ( !v13 )
  {
    v8 = -1073741801;
    v11 = 3056;
    v12 = 3221225495LL;
    goto LABEL_21;
  }
  memset(v13, 0, 0x1B0u);
  Provider = LoadProviderEx(*(int **)ppBuffer->rgpProviders, (__int64)(v3 + 4), 0x188u, v3 + 3, v3 + 4);
  v8 = Provider;
  if ( Provider < 0 )
  {
    v11 = 3077;
LABEL_16:
    v12 = (unsigned int)Provider;
    goto LABEL_21;
  }
  Provider = ((__int64 (__fastcall *)(__int64 *, const WCHAR *, _QWORD))v3[25])(v3 + 53, v6, a3);
  v8 = Provider;
  if ( Provider < 0 )
  {
    v11 = 3093;
    goto LABEL_16;
  }
  *(_DWORD *)v3 = 432;
  *((_DWORD *)v3 + 1) = 1145324609;
  *((_DWORD *)v3 + 2) = a3;
  *((_DWORD *)v3 + 4) = 1;
  *((_DWORD *)v3 + 3) = 0;
  *a1 = v3;
  v3 = 0;
  v8 = 0;
LABEL_22:
  if ( ppBuffer && ppBuffer != (PCRYPT_PROVIDER_REFS)v19 )
    MSCryptFree(ppBuffer);
  if ( v3 )
  {
    v15 = v3[3];
    if ( v15 )
      UnloadProvider(v15);
    MSCryptFree(v3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005d420  mov     [rsp-8+arg_18], rbx
0x18005d425  push    rbp
0x18005d426  push    rdi
0x18005d427  push    r12
0x18005d429  push    r13
0x18005d42b  push    r15
0x18005d42d  lea     rbp, [rsp-160h]
0x18005d435  sub     rsp, 260h
0x18005d43c  mov     rax, cs:__security_cookie
0x18005d443  xor     rax, rsp
0x18005d446  mov     [rbp+180h+var_30], rax
0x18005d44d  xor     ebx, ebx
0x18005d44f  mov     [rsp+280h+var_238], 200h
0x18005d457  lea     rax, [rsp+280h+var_230]
0x18005d45c  mov     r15d, r8d
0x18005d45f  mov     [rsp+280h+var_240], rax
0x18005d464  mov     r13, rcx
0x18005d467  test    rcx, rcx
0x18005d46a  jz      loc_18005D5E9
0x18005d470  test    r8d, 0FFFFFFFEh
0x18005d477  jnz     loc_18005D5E9
0x18005d47d  test    rdx, rdx
0x18005d480  lea     r12, aMicrosoftSslPr; "Microsoft SSL Protocol Provider"
0x18005d487  cmovnz  r12, rdx
0x18005d48b  lea     rax, [rsp+280h+var_240]
0x18005d490  mov     r9, r12; pszProvider
0x18005d493  mov     [rsp+280h+ppBuffer], rax; ppBuffer
0x18005d498  xor     r8d, r8d; pszFunction
0x18005d49b  lea     rax, [rsp+280h+var_238]
0x18005d4a0  mov     edx, 10002h; dwInterface
0x18005d4a5  mov     [rsp+280h+pcbBuffer], rax; pcbBuffer
0x18005d4aa  xor     ecx, ecx; pszContext
0x18005d4ac  mov     [rsp+280h+dwFlags], ebx; dwFlags
0x18005d4b0  mov     [rsp+280h+dwMode], 2; dwMode
0x18005d4b8  call    BCryptResolveProviders
0x18005d4bd  mov     edi, eax
0x18005d4bf  cmp     eax, 0C0000023h
0x18005d4c4  jnz     short loc_18005D51E
0x18005d4c6  mov     rcx, [rsp+280h+var_240]; P
0x18005d4cb  lea     rax, [rsp+280h+var_230]
0x18005d4d0  cmp     rcx, rax
0x18005d4d3  jz      short loc_18005D4DA
0x18005d4d5  call    MSCryptFree
0x18005d4da  mov     ecx, [rsp+280h+var_238]
0x18005d4de  call    MSCryptAlloc
0x18005d4e3  mov     [rsp+280h+var_240], rax
0x18005d4e8  test    rax, rax
0x18005d4eb  jnz     short loc_18005D48B
0x18005d4ed  mov     r9d, 0BD4h
0x18005d4f3  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005d4fa  lea     rdx, aStatus; "Status"
0x18005d501  mov     ecx, 0C0000017h
0x18005d506  mov     edi, 0C0000017h
0x18005d50b  call    DebugTraceError
0x18005d510  mov     rax, [rsp+280h+var_240]
0x18005d515  test    rax, rax
0x18005d518  jnz     loc_18005D48B
0x18005d51e  test    edi, edi
0x18005d520  jns     short loc_18005D52F
0x18005d522  mov     r9d, 0BDBh
0x18005d528  mov     ecx, edi
0x18005d52a  jmp     loc_18005D5F9
0x18005d52f  mov     edi, 1B0h
0x18005d534  mov     ecx, edi
0x18005d536  call    MSCryptAlloc
0x18005d53b  mov     rbx, rax
0x18005d53e  test    rax, rax
0x18005d541  jnz     short loc_18005D558
0x18005d543  mov     edi, 0C0000017h
0x18005d548  mov     r9d, 0BF0h
0x18005d54e  mov     ecx, 0C0000017h
0x18005d553  jmp     loc_18005D5F9
0x18005d558  mov     r8, rdi; Size
0x18005d55b  xor     edx, edx; Val
0x18005d55d  mov     rcx, rbx; void *
0x18005d560  call    memset
0x18005d565  mov     rax, [rsp+280h+var_240]
0x18005d56a  lea     rdx, [rbx+20h]
0x18005d56e  lea     r9, [rbx+18h]
0x18005d572  mov     qword ptr [rsp+280h+dwMode], rdx
0x18005d577  mov     r8d, 188h
0x18005d57d  mov     rcx, [rax+8]
0x18005d581  mov     rcx, [rcx]
0x18005d584  call    LoadProviderEx
0x18005d589  mov     edi, eax
0x18005d58b  test    eax, eax
0x18005d58d  jns     short loc_18005D599
0x18005d58f  mov     r9d, 0C05h
0x18005d595  mov     ecx, eax
0x18005d597  jmp     short loc_18005D5F9
0x18005d599  mov     rax, [rbx+0C8h]
0x18005d5a0  lea     rcx, [rbx+1A8h]
0x18005d5a7  mov     r8d, r15d
0x18005d5aa  mov     rdx, r12
0x18005d5ad  call    _guard_dispatch_icall
0x18005d5b2  mov     edi, eax
0x18005d5b4  test    eax, eax
0x18005d5b6  jns     short loc_18005D5C0
0x18005d5b8  mov     r9d, 0C15h
0x18005d5be  jmp     short loc_18005D595
0x18005d5c0  mov     dword ptr [rbx], 1B0h
0x18005d5c6  mov     dword ptr [rbx+4], 44444441h
0x18005d5cd  mov     [rbx+8], r15d
0x18005d5d1  mov     dword ptr [rbx+10h], 1
0x18005d5d8  mov     dword ptr [rbx+0Ch], 0
0x18005d5df  mov     [r13+0], rbx
0x18005d5e3  xor     ebx, ebx
0x18005d5e5  xor     edi, edi
0x18005d5e7  jmp     short loc_18005D60C
0x18005d5e9  mov     edi, 0C000000Dh
0x18005d5ee  mov     r9d, 0BA3h
0x18005d5f4  mov     ecx, 0C000000Dh
0x18005d5f9  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005d600  lea     rdx, aStatus; "Status"
0x18005d607  call    DebugTraceError
0x18005d60c  mov     rcx, [rsp+280h+var_240]; P
0x18005d611  test    rcx, rcx
0x18005d614  jz      short loc_18005D625
0x18005d616  lea     rax, [rsp+280h+var_230]
0x18005d61b  cmp     rcx, rax
0x18005d61e  jz      short loc_18005D625
0x18005d620  call    MSCryptFree
0x18005d625  test    rbx, rbx
0x18005d628  jz      short loc_18005D640
0x18005d62a  mov     rcx, [rbx+18h]
0x18005d62e  test    rcx, rcx
0x18005d631  jz      short loc_18005D638
0x18005d633  call    UnloadProvider
0x18005d638  mov     rcx, rbx; P
0x18005d63b  call    MSCryptFree
0x18005d640  mov     eax, edi
0x18005d642  mov     rcx, [rbp+180h+var_30]
0x18005d649  xor     rcx, rsp; StackCookie
0x18005d64c  call    __security_check_cookie
0x18005d651  mov     rbx, [rsp+280h+arg_18]
0x18005d659  add     rsp, 260h
0x18005d660  pop     r15
0x18005d662  pop     r13
0x18005d664  pop     r12
0x18005d666  pop     rdi
0x18005d667  pop     rbp
0x18005d668  retn
```
