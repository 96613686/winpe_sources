# GetHashOidList

- ea: `0x18000bde4`
- end: `0x18000c09a`
- name: `GetHashOidList`
- size: `694`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180049c80`
- `0x180081fd0`

## callees

- `0x18000bde4`
- `0x18000c650`
- `0x18000e090`
- `0x18000e440`
- `0x18000f6b0`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`

## string_xrefs

- `0x18000bf4f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000bfa3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000bfd2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000c00f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000c048`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18000c078`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall GetHashOidList(_QWORD *a1, int a2, _QWORD *a3, _DWORD *a4)
{
  int v7; // eax
  int HashProperty; // eax
  int v9; // ebx
  __int64 v10; // rdx
  _QWORD *v11; // rdi
  int v12; // edx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // [rsp+40h] [rbp-10h] BYREF
  _DWORD *v17; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v18; // [rsp+70h] [rbp+20h] BYREF

  v17 = 0;
  LODWORD(v16) = 0;
  v18 = 0;
  if ( !a1 )
  {
    v9 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 149);
    return (unsigned int)v9;
  }
  if ( !*a1 )
  {
    *a3 = 0;
    v9 = 0;
    *a4 = 0;
    return (unsigned int)v9;
  }
  v7 = MSCryptOpenHashProvider(&v17, *a1, 0);
  if ( v7 < 0 )
  {
    DebugTraceError((unsigned int)v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 169);
    v9 = -1073741637;
    goto LABEL_11;
  }
  HashProperty = MSCryptGetHashProperty(v17, L"HashDigestLength", &v16, 4u, &v18, 0);
  v9 = HashProperty;
  if ( HashProperty < 0 )
  {
    v14 = 183;
    v15 = (unsigned int)HashProperty;
LABEL_26:
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v14);
    goto LABEL_11;
  }
  if ( (_DWORD)v16 != a2 )
  {
    v9 = -1073741811;
    v14 = 190;
    v15 = 3221225485LL;
    goto LABEL_26;
  }
  v9 = MSCryptGetHashProperty(v17, L"HashOIDList", 0, 0, &v18, 0);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v10,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        v9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        203);
    goto LABEL_11;
  }
  v11 = (_QWORD *)MSCryptAlloc(v18, v10);
  if ( !v11 )
  {
    v9 = -1073741801;
    v14 = 212;
    v15 = 3221225495LL;
    goto LABEL_26;
  }
  v9 = MSCryptGetHashProperty(v17, L"HashOIDList", v11, v18, &v18, 0);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v12,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        v9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        225);
  }
  else
  {
    if ( *(_DWORD *)v11 )
    {
      v9 = 0;
      *a4 = v18;
      *a3 = v11;
      goto LABEL_11;
    }
    v9 = -1073741595;
    DebugTraceError(3221225701LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 234);
  }
  MSCryptFree(v11);
LABEL_11:
  if ( v17 )
    MSCryptCloseHashProvider(v17, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000bde4  mov     [rsp-18h+arg_8], rbx
0x18000bde9  mov     [rsp-18h+arg_10], rdi
0x18000bdee  push    rbp
0x18000bdef  push    r14
0x18000bdf1  push    r15
0x18000bdf3  mov     rbp, rsp
0x18000bdf6  sub     rsp, 50h
0x18000bdfa  mov     [rbp+var_8], 0
0x18000be02  mov     r14, r9
0x18000be05  mov     dword ptr [rbp+var_10], 0
0x18000be0c  mov     r15, r8
0x18000be0f  mov     [rbp+arg_0], 0
0x18000be16  mov     edi, edx
0x18000be18  test    rcx, rcx
0x18000be1b  jz      loc_18000BFCC
0x18000be21  mov     rdx, [rcx]
0x18000be24  test    rdx, rdx
0x18000be27  jz      loc_18000BFF4
0x18000be2d  xor     r8d, r8d
0x18000be30  lea     rcx, [rbp+var_8]
0x18000be34  call    MSCryptOpenHashProvider
0x18000be39  test    eax, eax
0x18000be3b  js      loc_18000C009
0x18000be41  mov     rcx, [rbp+var_8]
0x18000be45  lea     rax, [rbp+arg_0]
0x18000be49  mov     dword ptr [rsp+50h+var_28], 0
0x18000be51  lea     r8, [rbp+var_10]
0x18000be55  mov     r9d, 4
0x18000be5b  mov     [rsp+50h+var_30], rax
0x18000be60  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000be67  call    MSCryptGetHashProperty
0x18000be6c  mov     ebx, eax
0x18000be6e  test    eax, eax
0x18000be70  js      loc_18000C02E
0x18000be76  cmp     dword ptr [rbp+var_10], edi
0x18000be79  jnz     loc_18000C060
0x18000be7f  mov     rcx, [rbp+var_8]
0x18000be83  lea     rax, [rbp+arg_0]
0x18000be87  mov     dword ptr [rsp+50h+var_28], 0
0x18000be8f  lea     rdx, aHashoidlist; "HashOIDList"
0x18000be96  xor     r9d, r9d
0x18000be99  mov     [rsp+50h+var_30], rax
0x18000be9e  xor     r8d, r8d
0x18000bea1  call    MSCryptGetHashProperty
0x18000bea6  mov     ebx, eax
0x18000bea8  test    eax, eax
0x18000beaa  js      loc_18000BF7D
0x18000beb0  mov     ecx, [rbp+arg_0]
0x18000beb3  call    MSCryptAlloc
0x18000beb8  mov     rdi, rax
0x18000bebb  test    rax, rax
0x18000bebe  jz      loc_18000C038
0x18000bec4  mov     r9d, [rbp+arg_0]
0x18000bec8  lea     rax, [rbp+arg_0]
0x18000becc  mov     rcx, [rbp+var_8]
0x18000bed0  lea     rdx, aHashoidlist; "HashOIDList"
0x18000bed7  mov     dword ptr [rsp+50h+var_28], 0
0x18000bedf  mov     r8, rdi
0x18000bee2  mov     [rsp+50h+var_30], rax
0x18000bee7  call    MSCryptGetHashProperty
0x18000beec  mov     ebx, eax
0x18000beee  test    eax, eax
0x18000bef0  js      short loc_18000BF31
0x18000bef2  cmp     dword ptr [rdi], 0
0x18000bef5  jz      loc_18000C072
0x18000befb  mov     eax, [rbp+arg_0]
0x18000befe  xor     ebx, ebx
0x18000bf00  mov     [r14], eax
0x18000bf03  mov     [r15], rdi
0x18000bf06  cmp     [rbp+var_8], 0
0x18000bf0b  jz      short loc_18000BF18
0x18000bf0d  mov     rcx, [rbp+var_8]
0x18000bf11  xor     edx, edx
0x18000bf13  call    MSCryptCloseHashProvider
0x18000bf18  lea     r11, [rsp+50h+var_s0]
0x18000bf1d  mov     eax, ebx
0x18000bf1f  mov     rbx, [r11+28h]
0x18000bf23  mov     rdi, [r11+30h]
0x18000bf27  mov     rsp, r11
0x18000bf2a  pop     r15
0x18000bf2c  pop     r14
0x18000bf2e  pop     rbp
0x18000bf2f  retn
0x18000bf31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf38  lea     rax, WPP_GLOBAL_Control
0x18000bf3f  cmp     rcx, rax
0x18000bf42  jz      short loc_18000BF73
0x18000bf44  mov     eax, [rcx+2Ch]
0x18000bf47  test    al, 1
0x18000bf49  jz      short loc_18000BF73
0x18000bf4b  mov     rcx, [rcx+18h]
0x18000bf4f  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bf56  mov     [rsp+50h+var_20], 0E1h
0x18000bf5e  lea     r9, aStatus; "Status"
0x18000bf65  mov     [rsp+50h+var_28], r8
0x18000bf6a  mov     dword ptr [rsp+50h+var_30], ebx
0x18000bf6e  call    WPP_SF_sDsd
0x18000bf73  mov     rcx, rdi; P
0x18000bf76  call    MSCryptFree
0x18000bf7b  jmp     short loc_18000BF06
0x18000bf7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf84  lea     rax, WPP_GLOBAL_Control
0x18000bf8b  cmp     rcx, rax
0x18000bf8e  jz      loc_18000BF06
0x18000bf94  mov     eax, [rcx+2Ch]
0x18000bf97  test    al, 1
0x18000bf99  jz      loc_18000BF06
0x18000bf9f  mov     rcx, [rcx+18h]
0x18000bfa3  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bfaa  mov     [rsp+50h+var_20], 0CBh
0x18000bfb2  lea     r9, aStatus; "Status"
0x18000bfb9  mov     [rsp+50h+var_28], r8
0x18000bfbe  mov     dword ptr [rsp+50h+var_30], ebx
0x18000bfc2  call    WPP_SF_sDsd
0x18000bfc7  jmp     loc_18000BF06
0x18000bfcc  mov     r9d, 95h
0x18000bfd2  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bfd9  lea     rdx, aStatus; "Status"
0x18000bfe0  mov     ecx, 0C000000Dh
0x18000bfe5  mov     ebx, 0C000000Dh
0x18000bfea  call    DebugTraceError
0x18000bfef  jmp     loc_18000BF18
0x18000bff4  mov     qword ptr [r8], 0
0x18000bffb  xor     ebx, ebx
0x18000bffd  mov     dword ptr [r9], 0
0x18000c004  jmp     loc_18000BF18
0x18000c009  mov     r9d, 0A9h
0x18000c00f  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c016  lea     rdx, aStatus; "Status"
0x18000c01d  mov     ecx, eax
0x18000c01f  call    DebugTraceError
0x18000c024  mov     ebx, 0C00000BBh
0x18000c029  jmp     loc_18000BF06
0x18000c02e  mov     r9d, 0B7h
0x18000c034  mov     ecx, eax
0x18000c036  jmp     short loc_18000C048
0x18000c038  mov     ebx, 0C0000017h
0x18000c03d  mov     r9d, 0D4h
0x18000c043  mov     ecx, 0C0000017h
0x18000c048  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c04f  lea     rdx, aStatus; "Status"
0x18000c056  call    DebugTraceError
0x18000c05b  jmp     loc_18000BF06
0x18000c060  mov     ebx, 0C000000Dh
0x18000c065  mov     r9d, 0BEh
0x18000c06b  mov     ecx, 0C000000Dh
0x18000c070  jmp     short loc_18000C048
0x18000c072  mov     r9d, 0EAh
0x18000c078  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c07f  lea     rdx, aStatus; "Status"
0x18000c086  mov     ecx, 0C00000E5h
0x18000c08b  mov     ebx, 0C00000E5h
0x18000c090  call    DebugTraceError
0x18000c095  jmp     loc_18000BF73
```
