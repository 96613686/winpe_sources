# MSCryptRsaVerifySignature

- ea: `0x18003fcc0`
- end: `0x18003ff7e`
- name: `MSCryptRsaVerifySignature`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003fa10`

## callees

- `0x180001cc4`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x1800339b0`
- `0x18003fc68`
- `0x18003fcc0`
- `0x180047ce0`
- `0x180077658`
- `0x180089a24`

## string_xrefs

- `0x18003fd30`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003fda9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003fe35`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003ff42`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

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
0x18003fcc0  mov     r11, rsp
0x18003fcc3  mov     [r11+8], rbx
0x18003fcc7  mov     [r11+10h], rbp
0x18003fccb  mov     [r11+18h], r8
0x18003fccf  push    rsi
0x18003fcd0  push    rdi
0x18003fcd1  push    r12
0x18003fcd3  push    r14
0x18003fcd5  push    r15
0x18003fcd7  sub     rsp, 70h
0x18003fcdb  mov     ebp, [rsp+98h+arg_30]
0x18003fce2  xor     edi, edi
0x18003fce4  mov     qword ptr [r11-38h], 0
0x18003fcec  mov     r14d, r9d
0x18003fcef  mov     [r11-40h], rdi
0x18003fcf3  mov     rax, r8
0x18003fcf6  mov     [rsp+98h+var_48], edi
0x18003fcfa  mov     r12, rdx
0x18003fcfd  test    ebp, 0FFFFFFE5h
0x18003fd03  jz      short loc_18003FD5C
0x18003fd05  mov     ebx, 0C000000Dh
0x18003fd0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fd11  lea     rax, WPP_GLOBAL_Control
0x18003fd18  cmp     rcx, rax
0x18003fd1b  jz      loc_18003FF62
0x18003fd21  mov     eax, [rcx+2Ch]
0x18003fd24  test    al, 1
0x18003fd26  jz      loc_18003FF62
0x18003fd2c  mov     rcx, [rcx+18h]
0x18003fd30  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003fd37  mov     dword ptr [rsp+98h+var_68], 88Eh
0x18003fd3f  lea     r9, aStatus; "Status"
0x18003fd46  mov     [r11-70h], r8
0x18003fd4a  mov     dword ptr [rsp+98h+var_78], 0C000000Dh
0x18003fd52  call    WPP_SF_sDsd
0x18003fd57  jmp     loc_18003FF62
0x18003fd5c  test    r12, r12
0x18003fd5f  jz      loc_18003FF32
0x18003fd65  test    rax, rax
0x18003fd68  jz      loc_18003FF32
0x18003fd6e  cmp     [rsp+98h+arg_20], rdi
0x18003fd76  jz      loc_18003FF32
0x18003fd7c  test    r14d, r14d
0x18003fd7f  jz      loc_18003FF32
0x18003fd85  call    validateMSCryptRsaKey
0x18003fd8a  mov     r15, rax
0x18003fd8d  test    rax, rax
0x18003fd90  jnz     short loc_18003FDBA
0x18003fd92  mov     r9d, 89Fh
0x18003fd98  mov     ebx, 0C0000008h
0x18003fd9d  mov     ecx, 0C0000008h
0x18003fda2  lea     rdx, aStatus; "Status"
0x18003fda9  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003fdb0  call    DebugTraceError
0x18003fdb5  jmp     loc_18003FF62
0x18003fdba  cmp     [rax+10h], edi
0x18003fdbd  jnz     short loc_18003FDC7
0x18003fdbf  mov     r9d, 8A7h
0x18003fdc5  jmp     short loc_18003FD98
0x18003fdc7  mov     rax, [rax+20h]
0x18003fdcb  mov     esi, [rax+10h]
0x18003fdce  add     esi, 7
0x18003fdd1  shr     esi, 3
0x18003fdd4  cmp     [rsp+98h+arg_28], esi
0x18003fddb  jnb     short loc_18003FDEF
0x18003fddd  mov     ebx, 0C000000Dh
0x18003fde2  mov     r9d, 8B0h
0x18003fde8  mov     ecx, 0C000000Dh
0x18003fded  jmp     short loc_18003FDA2
0x18003fdef  test    bpl, 12h
0x18003fdf3  jz      loc_18003FEB1
0x18003fdf9  cmp     [rsp+98h+arg_28], esi
0x18003fe00  jbe     short loc_18003FE14
0x18003fe02  mov     ebx, 0C000A000h
0x18003fe07  mov     r9d, 8C5h
0x18003fe0d  mov     ecx, 0C000A000h
0x18003fe12  jmp     short loc_18003FDA2
0x18003fe14  lea     r9, [rsp+98h+var_48]
0x18003fe19  mov     edx, r14d
0x18003fe1c  lea     r8, [rsp+98h+P]
0x18003fe21  mov     rcx, r12
0x18003fe24  call    GetHashOidList
0x18003fe29  mov     ebx, eax
0x18003fe2b  test    eax, eax
0x18003fe2d  jns     short loc_18003FE54
0x18003fe2f  mov     r9d, 8CCh
0x18003fe35  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003fe3c  lea     rdx, aStatus; "Status"
0x18003fe43  mov     ecx, eax
0x18003fe45  call    DebugTraceError
0x18003fe4a  mov     rdi, [rsp+98h+P]
0x18003fe4f  jmp     loc_18003FF55
0x18003fe54  mov     rdi, [rsp+98h+P]
0x18003fe59  shr     ebp, 3
0x18003fe5c  and     ebp, 2
0x18003fe5f  test    rdi, rdi
0x18003fe62  jz      short loc_18003FE68
0x18003fe64  mov     eax, [rdi]
0x18003fe66  jmp     short loc_18003FE6A
0x18003fe68  xor     eax, eax
0x18003fe6a  test    rdi, rdi
0x18003fe6d  jz      short loc_18003FE75
0x18003fe6f  mov     rdx, [rdi+8]
0x18003fe73  jmp     short loc_18003FE77
0x18003fe75  xor     edx, edx
0x18003fe77  mov     r9, [rsp+98h+arg_20]
0x18003fe7f  cmp     r14d, esi
0x18003fe82  mov     [rsp+98h+var_58], ebp
0x18003fe86  mov     [rsp+98h+var_60], rax
0x18003fe8b  cmova   r14d, esi
0x18003fe8f  mov     [rsp+98h+var_68], rdx
0x18003fe94  mov     rdx, [rsp+98h+arg_10]
0x18003fe9c  mov     ecx, esi
0x18003fe9e  mov     [rsp+98h+var_78], rcx
0x18003fea3  mov     rcx, [r15+20h]
0x18003fea7  mov     r8d, r14d
0x18003feaa  call    SymCryptRsaPkcs1Verify
0x18003feaf  jmp     short loc_18003FF17
0x18003feb1  lea     r8, [rsp+98h+var_38]
0x18003feb6  mov     edx, r14d
0x18003feb9  mov     rcx, r12
0x18003febc  call    CheckAndGetPssHashAlgorithm
0x18003fec1  mov     ebx, eax
0x18003fec3  test    eax, eax
0x18003fec5  jns     short loc_18003FED4
0x18003fec7  mov     r9d, 8E5h
0x18003fecd  mov     ecx, eax
0x18003fecf  jmp     loc_18003FDA2
0x18003fed4  mov     eax, [r12+8]
0x18003fed9  cmp     r14d, esi
0x18003fedc  mov     ecx, [rsp+98h+arg_28]
0x18003fee3  mov     r9, [rsp+98h+arg_20]
0x18003feeb  cmova   r14d, esi
0x18003feef  mov     rdx, [rsp+98h+arg_10]
0x18003fef7  mov     [rsp+98h+var_60], rax
0x18003fefc  mov     rax, [rsp+98h+var_38]
0x18003ff01  mov     [rsp+98h+var_68], rax
0x18003ff06  mov     [rsp+98h+var_78], rcx
0x18003ff0b  mov     rcx, [r15+20h]
0x18003ff0f  mov     r8d, r14d
0x18003ff12  call    SymCryptRsaPssVerify
0x18003ff17  test    eax, eax
0x18003ff19  jz      short loc_18003FF2E
0x18003ff1b  mov     ecx, eax
0x18003ff1d  call    SymcryptErrorCodeToNtStatus
0x18003ff22  mov     ebx, eax
0x18003ff24  mov     ecx, eax
0x18003ff26  mov     r9d, 8F8h
0x18003ff2c  jmp     short loc_18003FF42
0x18003ff2e  xor     ebx, ebx
0x18003ff30  jmp     short loc_18003FF55
0x18003ff32  mov     ebx, 0C000000Dh
0x18003ff37  mov     r9d, 896h
0x18003ff3d  mov     ecx, 0C000000Dh
0x18003ff42  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003ff49  lea     rdx, aStatus; "Status"
0x18003ff50  call    DebugTraceError
0x18003ff55  test    rdi, rdi
0x18003ff58  jz      short loc_18003FF62
0x18003ff5a  mov     rcx, rdi; P
0x18003ff5d  call    MSCryptFree
0x18003ff62  lea     r11, [rsp+98h+var_28]
0x18003ff67  mov     eax, ebx
0x18003ff69  mov     rbx, [r11+30h]
0x18003ff6d  mov     rbp, [r11+38h]
0x18003ff71  mov     rsp, r11
0x18003ff74  pop     r15
0x18003ff76  pop     r14
0x18003ff78  pop     r12
0x18003ff7a  pop     rdi
0x18003ff7b  pop     rsi
0x18003ff7c  retn
```
