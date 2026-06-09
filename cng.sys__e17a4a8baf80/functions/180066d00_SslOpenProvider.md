# SslOpenProvider

- ea: `0x180066d00`
- end: `0x180066f4a`
- name: `SslOpenProvider`
- size: `586`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x180032c70`
- `0x1800444fc`
- `0x180046db4`
- `0x180066d00`
- `0x1800a4260`
- `0x1800a4300`
- `0x1800a4380`

## string_xrefs

- `0x180066dd3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180066ed9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180066d60`: `Microsoft SSL Protocol Provider`

## pseudocode

```c
__int64 __fastcall SslOpenProvider(__int64 **a1, const WCHAR *a2, unsigned int a3)
{
  __int64 *v3; // rbx
  const WCHAR *v6; // r12
  __int64 v7; // rdx
  NTSTATUS v8; // edi
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 *v11; // rax
  int Provider; // eax
  __int64 v13; // rcx
  PCRYPT_PROVIDER_REFS ppBuffer; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pcbBuffer; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v17[512]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = 0;
  pcbBuffer = 512;
  ppBuffer = (PCRYPT_PROVIDER_REFS)v17;
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
    if ( ppBuffer != (PCRYPT_PROVIDER_REFS)v17 )
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
  v11 = (__int64 *)MSCryptAlloc(432, v7);
  v3 = v11;
  if ( !v11 )
  {
    v8 = -1073741801;
    v9 = 3056;
    v10 = 3221225495LL;
    goto LABEL_21;
  }
  memset(v11, 0, 0x1B0u);
  Provider = LoadProviderEx(*(int **)ppBuffer->rgpProviders, (__int64)(v3 + 4), 0x188u, v3 + 3, v3 + 4);
  v8 = Provider;
  if ( Provider < 0 )
  {
    v9 = 3077;
LABEL_16:
    v10 = (unsigned int)Provider;
    goto LABEL_21;
  }
  Provider = ((__int64 (__fastcall *)(__int64 *, const WCHAR *, _QWORD))v3[25])(v3 + 53, v6, a3);
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
  if ( ppBuffer && ppBuffer != (PCRYPT_PROVIDER_REFS)v17 )
    MSCryptFree(ppBuffer);
  if ( v3 )
  {
    v13 = v3[3];
    if ( v13 )
      UnloadProvider(v13);
    MSCryptFree(v3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180066d00  mov     [rsp-8+arg_18], rbx
0x180066d05  push    rbp
0x180066d06  push    rdi
0x180066d07  push    r12
0x180066d09  push    r13
0x180066d0b  push    r15
0x180066d0d  lea     rbp, [rsp-160h]
0x180066d15  sub     rsp, 260h
0x180066d1c  mov     rax, cs:__security_cookie
0x180066d23  xor     rax, rsp
0x180066d26  mov     [rbp+180h+var_30], rax
0x180066d2d  xor     ebx, ebx
0x180066d2f  mov     [rsp+280h+var_238], 200h
0x180066d37  lea     rax, [rsp+280h+var_230]
0x180066d3c  mov     r15d, r8d
0x180066d3f  mov     [rsp+280h+var_240], rax
0x180066d44  mov     r13, rcx
0x180066d47  test    rcx, rcx
0x180066d4a  jz      loc_180066EC9
0x180066d50  test    r8d, 0FFFFFFFEh
0x180066d57  jnz     loc_180066EC9
0x180066d5d  test    rdx, rdx
0x180066d60  lea     r12, aMicrosoftSslPr; "Microsoft SSL Protocol Provider"
0x180066d67  cmovnz  r12, rdx
0x180066d6b  lea     rax, [rsp+280h+var_240]
0x180066d70  mov     r9, r12; pszProvider
0x180066d73  mov     [rsp+280h+ppBuffer], rax; ppBuffer
0x180066d78  xor     r8d, r8d; pszFunction
0x180066d7b  lea     rax, [rsp+280h+var_238]
0x180066d80  mov     edx, 10002h; dwInterface
0x180066d85  mov     [rsp+280h+pcbBuffer], rax; pcbBuffer
0x180066d8a  xor     ecx, ecx; pszContext
0x180066d8c  mov     [rsp+280h+dwFlags], ebx; dwFlags
0x180066d90  mov     [rsp+280h+dwMode], 2; dwMode
0x180066d98  call    BCryptResolveProviders
0x180066d9d  mov     edi, eax
0x180066d9f  cmp     eax, 0C0000023h
0x180066da4  jnz     short loc_180066DFE
0x180066da6  mov     rcx, [rsp+280h+var_240]; P
0x180066dab  lea     rax, [rsp+280h+var_230]
0x180066db0  cmp     rcx, rax
0x180066db3  jz      short loc_180066DBA
0x180066db5  call    MSCryptFree
0x180066dba  mov     ecx, [rsp+280h+var_238]
0x180066dbe  call    MSCryptAlloc
0x180066dc3  mov     [rsp+280h+var_240], rax
0x180066dc8  test    rax, rax
0x180066dcb  jnz     short loc_180066D6B
0x180066dcd  mov     r9d, 0BD4h
0x180066dd3  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180066dda  lea     rdx, aStatus; "Status"
0x180066de1  mov     ecx, 0C0000017h
0x180066de6  mov     edi, 0C0000017h
0x180066deb  call    DebugTraceError
0x180066df0  mov     rax, [rsp+280h+var_240]
0x180066df5  test    rax, rax
0x180066df8  jnz     loc_180066D6B
0x180066dfe  test    edi, edi
0x180066e00  jns     short loc_180066E0F
0x180066e02  mov     r9d, 0BDBh
0x180066e08  mov     ecx, edi
0x180066e0a  jmp     loc_180066ED9
0x180066e0f  mov     edi, 1B0h
0x180066e14  mov     ecx, edi
0x180066e16  call    MSCryptAlloc
0x180066e1b  mov     rbx, rax
0x180066e1e  test    rax, rax
0x180066e21  jnz     short loc_180066E38
0x180066e23  mov     edi, 0C0000017h
0x180066e28  mov     r9d, 0BF0h
0x180066e2e  mov     ecx, 0C0000017h
0x180066e33  jmp     loc_180066ED9
0x180066e38  mov     r8, rdi; Size
0x180066e3b  xor     edx, edx; Val
0x180066e3d  mov     rcx, rbx; void *
0x180066e40  call    memset
0x180066e45  mov     rax, [rsp+280h+var_240]
0x180066e4a  lea     rdx, [rbx+20h]
0x180066e4e  lea     r9, [rbx+18h]
0x180066e52  mov     qword ptr [rsp+280h+dwMode], rdx
0x180066e57  mov     r8d, 188h
0x180066e5d  mov     rcx, [rax+8]
0x180066e61  mov     rcx, [rcx]
0x180066e64  call    LoadProviderEx
0x180066e69  mov     edi, eax
0x180066e6b  test    eax, eax
0x180066e6d  jns     short loc_180066E79
0x180066e6f  mov     r9d, 0C05h
0x180066e75  mov     ecx, eax
0x180066e77  jmp     short loc_180066ED9
0x180066e79  mov     rax, [rbx+0C8h]
0x180066e80  lea     rcx, [rbx+1A8h]
0x180066e87  mov     r8d, r15d
0x180066e8a  mov     rdx, r12
0x180066e8d  call    _guard_dispatch_icall
0x180066e92  mov     edi, eax
0x180066e94  test    eax, eax
0x180066e96  jns     short loc_180066EA0
0x180066e98  mov     r9d, 0C15h
0x180066e9e  jmp     short loc_180066E75
0x180066ea0  mov     dword ptr [rbx], 1B0h
0x180066ea6  mov     dword ptr [rbx+4], 44444441h
0x180066ead  mov     [rbx+8], r15d
0x180066eb1  mov     dword ptr [rbx+10h], 1
0x180066eb8  mov     dword ptr [rbx+0Ch], 0
0x180066ebf  mov     [r13+0], rbx
0x180066ec3  xor     ebx, ebx
0x180066ec5  xor     edi, edi
0x180066ec7  jmp     short loc_180066EEC
0x180066ec9  mov     edi, 0C000000Dh
0x180066ece  mov     r9d, 0BA3h
0x180066ed4  mov     ecx, 0C000000Dh
0x180066ed9  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180066ee0  lea     rdx, aStatus; "Status"
0x180066ee7  call    DebugTraceError
0x180066eec  mov     rcx, [rsp+280h+var_240]; P
0x180066ef1  test    rcx, rcx
0x180066ef4  jz      short loc_180066F05
0x180066ef6  lea     rax, [rsp+280h+var_230]
0x180066efb  cmp     rcx, rax
0x180066efe  jz      short loc_180066F05
0x180066f00  call    MSCryptFree
0x180066f05  test    rbx, rbx
0x180066f08  jz      short loc_180066F20
0x180066f0a  mov     rcx, [rbx+18h]
0x180066f0e  test    rcx, rcx
0x180066f11  jz      short loc_180066F18
0x180066f13  call    UnloadProvider
0x180066f18  mov     rcx, rbx; P
0x180066f1b  call    MSCryptFree
0x180066f20  mov     eax, edi
0x180066f22  mov     rcx, [rbp+180h+var_30]
0x180066f29  xor     rcx, rsp; StackCookie
0x180066f2c  call    __security_check_cookie
0x180066f31  mov     rbx, [rsp+280h+arg_18]
0x180066f39  add     rsp, 260h
0x180066f40  pop     r15
0x180066f42  pop     r13
0x180066f44  pop     r12
0x180066f46  pop     rdi
0x180066f47  pop     rbp
0x180066f48  retn
```
