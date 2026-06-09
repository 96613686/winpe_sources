# MSCryptRsaVerifySignature

- ea: `0x180049c80`
- end: `0x180049f3e`
- name: `MSCryptRsaVerifySignature`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800499d0`

## callees

- `0x18000bde4`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x18003da20`
- `0x180049c28`
- `0x180049c80`
- `0x180051dd0`
- `0x1800817f8`
- `0x180093a54`

## string_xrefs

- `0x180049cf0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180049d69`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180049df5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180049f02`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaVerifySignature(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  PVOID v7; // rdi
  unsigned int v8; // r14d
  unsigned int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // r15
  __int64 v13; // r9
  __int64 v14; // rcx
  unsigned int v15; // esi
  int HashOidList; // eax
  unsigned int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r9
  int v22; // [rsp+50h] [rbp-48h] BYREF
  PVOID P; // [rsp+58h] [rbp-40h] BYREF
  __int64 v24; // [rsp+60h] [rbp-38h] BYREF
  int v25; // [rsp+B0h] [rbp+18h]

  v25 = a3;
  v7 = 0;
  v24 = 0;
  v8 = a4;
  P = 0;
  v22 = 0;
  if ( (a7 & 0xFFFFFFE5) != 0 )
  {
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        142);
    return v10;
  }
  if ( a2 && a3 && a5 && a4 )
  {
    v11 = validateMSCryptRsaKey(a1);
    v12 = v11;
    if ( !v11 )
    {
      v13 = 2207;
LABEL_11:
      v10 = -1073741816;
      v14 = 3221225480LL;
LABEL_12:
      DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v13);
      return v10;
    }
    if ( !*(_DWORD *)(v11 + 16) )
    {
      v13 = 2215;
      goto LABEL_11;
    }
    v15 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(v11 + 32) + 16LL) + 7) >> 3;
    if ( a6 < v15 )
    {
      v10 = -1073741811;
      v13 = 2224;
      v14 = 3221225485LL;
      goto LABEL_12;
    }
    if ( (a7 & 0x12) != 0 )
    {
      if ( a6 > v15 )
      {
        v10 = -1073700864;
        v13 = 2245;
        v14 = 3221266432LL;
        goto LABEL_12;
      }
      HashOidList = GetHashOidList(a2, v8, &P, &v22);
      v10 = HashOidList;
      if ( HashOidList < 0 )
      {
        DebugTraceError(
          (unsigned int)HashOidList,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          2252);
        v7 = P;
        goto LABEL_35;
      }
      v7 = P;
      if ( v8 > v15 )
        v8 = v15;
      v17 = SymCryptRsaPkcs1Verify(*(_QWORD *)(v12 + 32), v25, v8, a5, v15);
    }
    else
    {
      v18 = CheckAndGetPssHashAlgorithm(a2, v8, &v24);
      v10 = v18;
      if ( v18 < 0 )
      {
        v13 = 2277;
        v14 = (unsigned int)v18;
        goto LABEL_12;
      }
      if ( v8 > v15 )
        v8 = v15;
      v17 = SymCryptRsaPssVerify(*(_QWORD *)(v12 + 32), v25, v8, a5, a6);
    }
    if ( !v17 )
    {
      v10 = 0;
      goto LABEL_35;
    }
    v10 = SymcryptErrorCodeToNtStatus(v17);
    v19 = v10;
    v20 = 2296;
  }
  else
  {
    v10 = -1073741811;
    v20 = 2198;
    v19 = 3221225485LL;
  }
  DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v20);
LABEL_35:
  if ( v7 )
    MSCryptFree(v7);
  return v10;
}

```

## disassembly

```asm
0x180049c80  mov     r11, rsp
0x180049c83  mov     [r11+8], rbx
0x180049c87  mov     [r11+10h], rbp
0x180049c8b  mov     [r11+18h], r8
0x180049c8f  push    rsi
0x180049c90  push    rdi
0x180049c91  push    r12
0x180049c93  push    r14
0x180049c95  push    r15
0x180049c97  sub     rsp, 70h
0x180049c9b  mov     ebp, [rsp+98h+arg_30]
0x180049ca2  xor     edi, edi
0x180049ca4  mov     qword ptr [r11-38h], 0
0x180049cac  mov     r14d, r9d
0x180049caf  mov     [r11-40h], rdi
0x180049cb3  mov     rax, r8
0x180049cb6  mov     [rsp+98h+var_48], edi
0x180049cba  mov     r12, rdx
0x180049cbd  test    ebp, 0FFFFFFE5h
0x180049cc3  jz      short loc_180049D1C
0x180049cc5  mov     ebx, 0C000000Dh
0x180049cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cd1  lea     rax, WPP_GLOBAL_Control
0x180049cd8  cmp     rcx, rax
0x180049cdb  jz      loc_180049F22
0x180049ce1  mov     eax, [rcx+2Ch]
0x180049ce4  test    al, 1
0x180049ce6  jz      loc_180049F22
0x180049cec  mov     rcx, [rcx+18h]
0x180049cf0  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049cf7  mov     dword ptr [rsp+98h+var_68], 88Eh
0x180049cff  lea     r9, aStatus; "Status"
0x180049d06  mov     [r11-70h], r8
0x180049d0a  mov     dword ptr [rsp+98h+var_78], 0C000000Dh
0x180049d12  call    WPP_SF_sDsd
0x180049d17  jmp     loc_180049F22
0x180049d1c  test    r12, r12
0x180049d1f  jz      loc_180049EF2
0x180049d25  test    rax, rax
0x180049d28  jz      loc_180049EF2
0x180049d2e  cmp     [rsp+98h+arg_20], rdi
0x180049d36  jz      loc_180049EF2
0x180049d3c  test    r14d, r14d
0x180049d3f  jz      loc_180049EF2
0x180049d45  call    validateMSCryptRsaKey
0x180049d4a  mov     r15, rax
0x180049d4d  test    rax, rax
0x180049d50  jnz     short loc_180049D7A
0x180049d52  mov     r9d, 89Fh
0x180049d58  mov     ebx, 0C0000008h
0x180049d5d  mov     ecx, 0C0000008h
0x180049d62  lea     rdx, aStatus; "Status"
0x180049d69  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049d70  call    DebugTraceError
0x180049d75  jmp     loc_180049F22
0x180049d7a  cmp     [rax+10h], edi
0x180049d7d  jnz     short loc_180049D87
0x180049d7f  mov     r9d, 8A7h
0x180049d85  jmp     short loc_180049D58
0x180049d87  mov     rax, [rax+20h]
0x180049d8b  mov     esi, [rax+10h]
0x180049d8e  add     esi, 7
0x180049d91  shr     esi, 3
0x180049d94  cmp     [rsp+98h+arg_28], esi
0x180049d9b  jnb     short loc_180049DAF
0x180049d9d  mov     ebx, 0C000000Dh
0x180049da2  mov     r9d, 8B0h
0x180049da8  mov     ecx, 0C000000Dh
0x180049dad  jmp     short loc_180049D62
0x180049daf  test    bpl, 12h
0x180049db3  jz      loc_180049E71
0x180049db9  cmp     [rsp+98h+arg_28], esi
0x180049dc0  jbe     short loc_180049DD4
0x180049dc2  mov     ebx, 0C000A000h
0x180049dc7  mov     r9d, 8C5h
0x180049dcd  mov     ecx, 0C000A000h
0x180049dd2  jmp     short loc_180049D62
0x180049dd4  lea     r9, [rsp+98h+var_48]
0x180049dd9  mov     edx, r14d
0x180049ddc  lea     r8, [rsp+98h+P]
0x180049de1  mov     rcx, r12
0x180049de4  call    GetHashOidList
0x180049de9  mov     ebx, eax
0x180049deb  test    eax, eax
0x180049ded  jns     short loc_180049E14
0x180049def  mov     r9d, 8CCh
0x180049df5  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049dfc  lea     rdx, aStatus; "Status"
0x180049e03  mov     ecx, eax
0x180049e05  call    DebugTraceError
0x180049e0a  mov     rdi, [rsp+98h+P]
0x180049e0f  jmp     loc_180049F15
0x180049e14  mov     rdi, [rsp+98h+P]
0x180049e19  shr     ebp, 3
0x180049e1c  and     ebp, 2
0x180049e1f  test    rdi, rdi
0x180049e22  jz      short loc_180049E28
0x180049e24  mov     eax, [rdi]
0x180049e26  jmp     short loc_180049E2A
0x180049e28  xor     eax, eax
0x180049e2a  test    rdi, rdi
0x180049e2d  jz      short loc_180049E35
0x180049e2f  mov     rdx, [rdi+8]
0x180049e33  jmp     short loc_180049E37
0x180049e35  xor     edx, edx
0x180049e37  mov     r9, [rsp+98h+arg_20]
0x180049e3f  cmp     r14d, esi
0x180049e42  mov     [rsp+98h+var_58], ebp
0x180049e46  mov     [rsp+98h+var_60], rax
0x180049e4b  cmova   r14d, esi
0x180049e4f  mov     [rsp+98h+var_68], rdx
0x180049e54  mov     rdx, [rsp+98h+arg_10]
0x180049e5c  mov     ecx, esi
0x180049e5e  mov     [rsp+98h+var_78], rcx
0x180049e63  mov     rcx, [r15+20h]
0x180049e67  mov     r8d, r14d
0x180049e6a  call    SymCryptRsaPkcs1Verify
0x180049e6f  jmp     short loc_180049ED7
0x180049e71  lea     r8, [rsp+98h+var_38]
0x180049e76  mov     edx, r14d
0x180049e79  mov     rcx, r12
0x180049e7c  call    CheckAndGetPssHashAlgorithm
0x180049e81  mov     ebx, eax
0x180049e83  test    eax, eax
0x180049e85  jns     short loc_180049E94
0x180049e87  mov     r9d, 8E5h
0x180049e8d  mov     ecx, eax
0x180049e8f  jmp     loc_180049D62
0x180049e94  mov     eax, [r12+8]
0x180049e99  cmp     r14d, esi
0x180049e9c  mov     ecx, [rsp+98h+arg_28]
0x180049ea3  mov     r9, [rsp+98h+arg_20]
0x180049eab  cmova   r14d, esi
0x180049eaf  mov     rdx, [rsp+98h+arg_10]
0x180049eb7  mov     [rsp+98h+var_60], rax
0x180049ebc  mov     rax, [rsp+98h+var_38]
0x180049ec1  mov     [rsp+98h+var_68], rax
0x180049ec6  mov     [rsp+98h+var_78], rcx
0x180049ecb  mov     rcx, [r15+20h]
0x180049ecf  mov     r8d, r14d
0x180049ed2  call    SymCryptRsaPssVerify
0x180049ed7  test    eax, eax
0x180049ed9  jz      short loc_180049EEE
0x180049edb  mov     ecx, eax
0x180049edd  call    SymcryptErrorCodeToNtStatus
0x180049ee2  mov     ebx, eax
0x180049ee4  mov     ecx, eax
0x180049ee6  mov     r9d, 8F8h
0x180049eec  jmp     short loc_180049F02
0x180049eee  xor     ebx, ebx
0x180049ef0  jmp     short loc_180049F15
0x180049ef2  mov     ebx, 0C000000Dh
0x180049ef7  mov     r9d, 896h
0x180049efd  mov     ecx, 0C000000Dh
0x180049f02  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049f09  lea     rdx, aStatus; "Status"
0x180049f10  call    DebugTraceError
0x180049f15  test    rdi, rdi
0x180049f18  jz      short loc_180049F22
0x180049f1a  mov     rcx, rdi; P
0x180049f1d  call    MSCryptFree
0x180049f22  lea     r11, [rsp+98h+var_28]
0x180049f27  mov     eax, ebx
0x180049f29  mov     rbx, [r11+30h]
0x180049f2d  mov     rbp, [r11+38h]
0x180049f31  mov     rsp, r11
0x180049f34  pop     r15
0x180049f36  pop     r14
0x180049f38  pop     r12
0x180049f3a  pop     rdi
0x180049f3b  pop     rsi
0x180049f3c  retn
```
