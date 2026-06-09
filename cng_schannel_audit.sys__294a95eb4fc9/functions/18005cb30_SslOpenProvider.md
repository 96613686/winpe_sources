# SslOpenProvider

- ea: `0x18005cb30`
- end: `0x18005cd7a`
- name: `SslOpenProvider`
- size: `586`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180028b40`
- `0x18003a46c`
- `0x18003cdf4`
- `0x18005cb30`
- `0x18009d820`
- `0x18009d860`
- `0x18009dd40`

## string_xrefs

- `0x18005cc03`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18005cd09`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18005cb90`: `Microsoft SSL Protocol Provider`

## pseudocode

```c
__int64 __fastcall SslOpenProvider(_QWORD *a1, const WCHAR *a2, unsigned int a3)
{
  char *v3; // rbx
  const WCHAR *v6; // r12
  __int64 v7; // rdx
  NTSTATUS v8; // edi
  __int64 v9; // r9
  __int64 v10; // rcx
  char *v11; // rax
  int Provider; // eax
  PCRYPT_PROVIDER_REFS ppBuffer; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pcbBuffer; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[512]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = 0;
  pcbBuffer = 512;
  ppBuffer = (PCRYPT_PROVIDER_REFS)v16;
  if ( !a1 || (a3 & 0xFFFFFFFE) != 0 )
  {
    v8 = -1073741811;
    v9 = 2979;
    v10 = 3221225485LL;
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
    if ( ppBuffer != (PCRYPT_PROVIDER_REFS)v16 )
      MSCryptFree(ppBuffer);
    ppBuffer = (PCRYPT_PROVIDER_REFS)MSCryptAlloc(pcbBuffer, v7);
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
    v9 = 3035;
    v10 = (unsigned int)v8;
LABEL_21:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v9);
    goto LABEL_22;
  }
  v11 = (char *)MSCryptAlloc(432, v7);
  v3 = v11;
  if ( !v11 )
  {
    v8 = -1073741801;
    v9 = 3056;
    v10 = 3221225495LL;
    goto LABEL_21;
  }
  memset(v11, 0, 0x1B0u);
  Provider = LoadProviderEx(*ppBuffer->rgpProviders, v3 + 32, 392, v3 + 24, v3 + 32);
  v8 = Provider;
  if ( Provider < 0 )
  {
    v9 = 3077;
LABEL_16:
    v10 = (unsigned int)Provider;
    goto LABEL_21;
  }
  Provider = (*((__int64 (__fastcall **)(char *, const WCHAR *, _QWORD))v3 + 25))(v3 + 424, v6, a3);
  v8 = Provider;
  if ( Provider < 0 )
  {
    v9 = 3093;
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
  if ( ppBuffer && ppBuffer != (PCRYPT_PROVIDER_REFS)v16 )
    MSCryptFree(ppBuffer);
  if ( v3 )
  {
    if ( *((_QWORD *)v3 + 3) )
      UnloadProvider();
    MSCryptFree(v3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005cb30  mov     [rsp-8+arg_18], rbx
0x18005cb35  push    rbp
0x18005cb36  push    rdi
0x18005cb37  push    r12
0x18005cb39  push    r13
0x18005cb3b  push    r15
0x18005cb3d  lea     rbp, [rsp-160h]
0x18005cb45  sub     rsp, 260h
0x18005cb4c  mov     rax, cs:__security_cookie
0x18005cb53  xor     rax, rsp
0x18005cb56  mov     [rbp+180h+var_30], rax
0x18005cb5d  xor     ebx, ebx
0x18005cb5f  mov     [rsp+280h+var_238], 200h
0x18005cb67  lea     rax, [rsp+280h+var_230]
0x18005cb6c  mov     r15d, r8d
0x18005cb6f  mov     [rsp+280h+var_240], rax
0x18005cb74  mov     r13, rcx
0x18005cb77  test    rcx, rcx
0x18005cb7a  jz      loc_18005CCF9
0x18005cb80  test    r8d, 0FFFFFFFEh
0x18005cb87  jnz     loc_18005CCF9
0x18005cb8d  test    rdx, rdx
0x18005cb90  lea     r12, aMicrosoftSslPr; "Microsoft SSL Protocol Provider"
0x18005cb97  cmovnz  r12, rdx
0x18005cb9b  lea     rax, [rsp+280h+var_240]
0x18005cba0  mov     r9, r12; pszProvider
0x18005cba3  mov     [rsp+280h+ppBuffer], rax; ppBuffer
0x18005cba8  xor     r8d, r8d; pszFunction
0x18005cbab  lea     rax, [rsp+280h+var_238]
0x18005cbb0  mov     edx, 10002h; dwInterface
0x18005cbb5  mov     [rsp+280h+pcbBuffer], rax; pcbBuffer
0x18005cbba  xor     ecx, ecx; pszContext
0x18005cbbc  mov     [rsp+280h+dwFlags], ebx; dwFlags
0x18005cbc0  mov     [rsp+280h+dwMode], 2; dwMode
0x18005cbc8  call    BCryptResolveProviders
0x18005cbcd  mov     edi, eax
0x18005cbcf  cmp     eax, 0C0000023h
0x18005cbd4  jnz     short loc_18005CC2E
0x18005cbd6  mov     rcx, [rsp+280h+var_240]; P
0x18005cbdb  lea     rax, [rsp+280h+var_230]
0x18005cbe0  cmp     rcx, rax
0x18005cbe3  jz      short loc_18005CBEA
0x18005cbe5  call    MSCryptFree
0x18005cbea  mov     ecx, [rsp+280h+var_238]
0x18005cbee  call    MSCryptAlloc
0x18005cbf3  mov     [rsp+280h+var_240], rax
0x18005cbf8  test    rax, rax
0x18005cbfb  jnz     short loc_18005CB9B
0x18005cbfd  mov     r9d, 0BD4h
0x18005cc03  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cc0a  lea     rdx, aStatus; "Status"
0x18005cc11  mov     ecx, 0C0000017h
0x18005cc16  mov     edi, 0C0000017h
0x18005cc1b  call    DebugTraceError
0x18005cc20  mov     rax, [rsp+280h+var_240]
0x18005cc25  test    rax, rax
0x18005cc28  jnz     loc_18005CB9B
0x18005cc2e  test    edi, edi
0x18005cc30  jns     short loc_18005CC3F
0x18005cc32  mov     r9d, 0BDBh
0x18005cc38  mov     ecx, edi
0x18005cc3a  jmp     loc_18005CD09
0x18005cc3f  mov     edi, 1B0h
0x18005cc44  mov     ecx, edi
0x18005cc46  call    MSCryptAlloc
0x18005cc4b  mov     rbx, rax
0x18005cc4e  test    rax, rax
0x18005cc51  jnz     short loc_18005CC68
0x18005cc53  mov     edi, 0C0000017h
0x18005cc58  mov     r9d, 0BF0h
0x18005cc5e  mov     ecx, 0C0000017h
0x18005cc63  jmp     loc_18005CD09
0x18005cc68  mov     r8, rdi; Size
0x18005cc6b  xor     edx, edx; Val
0x18005cc6d  mov     rcx, rbx; void *
0x18005cc70  call    memset
0x18005cc75  mov     rax, [rsp+280h+var_240]
0x18005cc7a  lea     rdx, [rbx+20h]
0x18005cc7e  lea     r9, [rbx+18h]
0x18005cc82  mov     qword ptr [rsp+280h+dwMode], rdx
0x18005cc87  mov     r8d, 188h
0x18005cc8d  mov     rcx, [rax+8]
0x18005cc91  mov     rcx, [rcx]
0x18005cc94  call    LoadProviderEx
0x18005cc99  mov     edi, eax
0x18005cc9b  test    eax, eax
0x18005cc9d  jns     short loc_18005CCA9
0x18005cc9f  mov     r9d, 0C05h
0x18005cca5  mov     ecx, eax
0x18005cca7  jmp     short loc_18005CD09
0x18005cca9  mov     rax, [rbx+0C8h]
0x18005ccb0  lea     rcx, [rbx+1A8h]
0x18005ccb7  mov     r8d, r15d
0x18005ccba  mov     rdx, r12
0x18005ccbd  call    _guard_dispatch_icall
0x18005ccc2  mov     edi, eax
0x18005ccc4  test    eax, eax
0x18005ccc6  jns     short loc_18005CCD0
0x18005ccc8  mov     r9d, 0C15h
0x18005ccce  jmp     short loc_18005CCA5
0x18005ccd0  mov     dword ptr [rbx], 1B0h
0x18005ccd6  mov     dword ptr [rbx+4], 44444441h
0x18005ccdd  mov     [rbx+8], r15d
0x18005cce1  mov     dword ptr [rbx+10h], 1
0x18005cce8  mov     dword ptr [rbx+0Ch], 0
0x18005ccef  mov     [r13+0], rbx
0x18005ccf3  xor     ebx, ebx
0x18005ccf5  xor     edi, edi
0x18005ccf7  jmp     short loc_18005CD1C
0x18005ccf9  mov     edi, 0C000000Dh
0x18005ccfe  mov     r9d, 0BA3h
0x18005cd04  mov     ecx, 0C000000Dh
0x18005cd09  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cd10  lea     rdx, aStatus; "Status"
0x18005cd17  call    DebugTraceError
0x18005cd1c  mov     rcx, [rsp+280h+var_240]; P
0x18005cd21  test    rcx, rcx
0x18005cd24  jz      short loc_18005CD35
0x18005cd26  lea     rax, [rsp+280h+var_230]
0x18005cd2b  cmp     rcx, rax
0x18005cd2e  jz      short loc_18005CD35
0x18005cd30  call    MSCryptFree
0x18005cd35  test    rbx, rbx
0x18005cd38  jz      short loc_18005CD50
0x18005cd3a  mov     rcx, [rbx+18h]
0x18005cd3e  test    rcx, rcx
0x18005cd41  jz      short loc_18005CD48
0x18005cd43  call    UnloadProvider
0x18005cd48  mov     rcx, rbx; P
0x18005cd4b  call    MSCryptFree
0x18005cd50  mov     eax, edi
0x18005cd52  mov     rcx, [rbp+180h+var_30]
0x18005cd59  xor     rcx, rsp; StackCookie
0x18005cd5c  call    __security_check_cookie
0x18005cd61  mov     rbx, [rsp+280h+arg_18]
0x18005cd69  add     rsp, 260h
0x18005cd70  pop     r15
0x18005cd72  pop     r13
0x18005cd74  pop     r12
0x18005cd76  pop     rdi
0x18005cd77  pop     rbp
0x18005cd78  retn
```
