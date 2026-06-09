# MSCryptRsaVerifySignature

- ea: `0x180040850`
- end: `0x180040b0e`
- name: `MSCryptRsaVerifySignature`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800405a0`

## callees

- `0x180001cc4`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x1800344b0`
- `0x1800407f8`
- `0x180040850`
- `0x180048770`
- `0x180078068`
- `0x18008aa34`

## string_xrefs

- `0x1800408c0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180040939`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800409c5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180040ad2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

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
0x180040850  mov     r11, rsp
0x180040853  mov     [r11+8], rbx
0x180040857  mov     [r11+10h], rbp
0x18004085b  mov     [r11+18h], r8
0x18004085f  push    rsi
0x180040860  push    rdi
0x180040861  push    r12
0x180040863  push    r14
0x180040865  push    r15
0x180040867  sub     rsp, 70h
0x18004086b  mov     ebp, [rsp+98h+arg_30]
0x180040872  xor     edi, edi
0x180040874  mov     qword ptr [r11-38h], 0
0x18004087c  mov     r14d, r9d
0x18004087f  mov     [r11-40h], rdi
0x180040883  mov     rax, r8
0x180040886  mov     [rsp+98h+var_48], edi
0x18004088a  mov     r12, rdx
0x18004088d  test    ebp, 0FFFFFFE5h
0x180040893  jz      short loc_1800408EC
0x180040895  mov     ebx, 0C000000Dh
0x18004089a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800408a1  lea     rax, WPP_GLOBAL_Control
0x1800408a8  cmp     rcx, rax
0x1800408ab  jz      loc_180040AF2
0x1800408b1  mov     eax, [rcx+2Ch]
0x1800408b4  test    al, 1
0x1800408b6  jz      loc_180040AF2
0x1800408bc  mov     rcx, [rcx+18h]
0x1800408c0  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800408c7  mov     dword ptr [rsp+98h+var_68], 88Eh
0x1800408cf  lea     r9, aStatus; "Status"
0x1800408d6  mov     [r11-70h], r8
0x1800408da  mov     dword ptr [rsp+98h+var_78], 0C000000Dh
0x1800408e2  call    WPP_SF_sDsd
0x1800408e7  jmp     loc_180040AF2
0x1800408ec  test    r12, r12
0x1800408ef  jz      loc_180040AC2
0x1800408f5  test    rax, rax
0x1800408f8  jz      loc_180040AC2
0x1800408fe  cmp     [rsp+98h+arg_20], rdi
0x180040906  jz      loc_180040AC2
0x18004090c  test    r14d, r14d
0x18004090f  jz      loc_180040AC2
0x180040915  call    validateMSCryptRsaKey
0x18004091a  mov     r15, rax
0x18004091d  test    rax, rax
0x180040920  jnz     short loc_18004094A
0x180040922  mov     r9d, 89Fh
0x180040928  mov     ebx, 0C0000008h
0x18004092d  mov     ecx, 0C0000008h
0x180040932  lea     rdx, aStatus; "Status"
0x180040939  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040940  call    DebugTraceError
0x180040945  jmp     loc_180040AF2
0x18004094a  cmp     [rax+10h], edi
0x18004094d  jnz     short loc_180040957
0x18004094f  mov     r9d, 8A7h
0x180040955  jmp     short loc_180040928
0x180040957  mov     rax, [rax+20h]
0x18004095b  mov     esi, [rax+10h]
0x18004095e  add     esi, 7
0x180040961  shr     esi, 3
0x180040964  cmp     [rsp+98h+arg_28], esi
0x18004096b  jnb     short loc_18004097F
0x18004096d  mov     ebx, 0C000000Dh
0x180040972  mov     r9d, 8B0h
0x180040978  mov     ecx, 0C000000Dh
0x18004097d  jmp     short loc_180040932
0x18004097f  test    bpl, 12h
0x180040983  jz      loc_180040A41
0x180040989  cmp     [rsp+98h+arg_28], esi
0x180040990  jbe     short loc_1800409A4
0x180040992  mov     ebx, 0C000A000h
0x180040997  mov     r9d, 8C5h
0x18004099d  mov     ecx, 0C000A000h
0x1800409a2  jmp     short loc_180040932
0x1800409a4  lea     r9, [rsp+98h+var_48]
0x1800409a9  mov     edx, r14d
0x1800409ac  lea     r8, [rsp+98h+P]
0x1800409b1  mov     rcx, r12
0x1800409b4  call    GetHashOidList
0x1800409b9  mov     ebx, eax
0x1800409bb  test    eax, eax
0x1800409bd  jns     short loc_1800409E4
0x1800409bf  mov     r9d, 8CCh
0x1800409c5  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800409cc  lea     rdx, aStatus; "Status"
0x1800409d3  mov     ecx, eax
0x1800409d5  call    DebugTraceError
0x1800409da  mov     rdi, [rsp+98h+P]
0x1800409df  jmp     loc_180040AE5
0x1800409e4  mov     rdi, [rsp+98h+P]
0x1800409e9  shr     ebp, 3
0x1800409ec  and     ebp, 2
0x1800409ef  test    rdi, rdi
0x1800409f2  jz      short loc_1800409F8
0x1800409f4  mov     eax, [rdi]
0x1800409f6  jmp     short loc_1800409FA
0x1800409f8  xor     eax, eax
0x1800409fa  test    rdi, rdi
0x1800409fd  jz      short loc_180040A05
0x1800409ff  mov     rdx, [rdi+8]
0x180040a03  jmp     short loc_180040A07
0x180040a05  xor     edx, edx
0x180040a07  mov     r9, [rsp+98h+arg_20]
0x180040a0f  cmp     r14d, esi
0x180040a12  mov     [rsp+98h+var_58], ebp
0x180040a16  mov     [rsp+98h+var_60], rax
0x180040a1b  cmova   r14d, esi
0x180040a1f  mov     [rsp+98h+var_68], rdx
0x180040a24  mov     rdx, [rsp+98h+arg_10]
0x180040a2c  mov     ecx, esi
0x180040a2e  mov     [rsp+98h+var_78], rcx
0x180040a33  mov     rcx, [r15+20h]
0x180040a37  mov     r8d, r14d
0x180040a3a  call    SymCryptRsaPkcs1Verify
0x180040a3f  jmp     short loc_180040AA7
0x180040a41  lea     r8, [rsp+98h+var_38]
0x180040a46  mov     edx, r14d
0x180040a49  mov     rcx, r12
0x180040a4c  call    CheckAndGetPssHashAlgorithm
0x180040a51  mov     ebx, eax
0x180040a53  test    eax, eax
0x180040a55  jns     short loc_180040A64
0x180040a57  mov     r9d, 8E5h
0x180040a5d  mov     ecx, eax
0x180040a5f  jmp     loc_180040932
0x180040a64  mov     eax, [r12+8]
0x180040a69  cmp     r14d, esi
0x180040a6c  mov     ecx, [rsp+98h+arg_28]
0x180040a73  mov     r9, [rsp+98h+arg_20]
0x180040a7b  cmova   r14d, esi
0x180040a7f  mov     rdx, [rsp+98h+arg_10]
0x180040a87  mov     [rsp+98h+var_60], rax
0x180040a8c  mov     rax, [rsp+98h+var_38]
0x180040a91  mov     [rsp+98h+var_68], rax
0x180040a96  mov     [rsp+98h+var_78], rcx
0x180040a9b  mov     rcx, [r15+20h]
0x180040a9f  mov     r8d, r14d
0x180040aa2  call    SymCryptRsaPssVerify
0x180040aa7  test    eax, eax
0x180040aa9  jz      short loc_180040ABE
0x180040aab  mov     ecx, eax
0x180040aad  call    SymcryptErrorCodeToNtStatus
0x180040ab2  mov     ebx, eax
0x180040ab4  mov     ecx, eax
0x180040ab6  mov     r9d, 8F8h
0x180040abc  jmp     short loc_180040AD2
0x180040abe  xor     ebx, ebx
0x180040ac0  jmp     short loc_180040AE5
0x180040ac2  mov     ebx, 0C000000Dh
0x180040ac7  mov     r9d, 896h
0x180040acd  mov     ecx, 0C000000Dh
0x180040ad2  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040ad9  lea     rdx, aStatus; "Status"
0x180040ae0  call    DebugTraceError
0x180040ae5  test    rdi, rdi
0x180040ae8  jz      short loc_180040AF2
0x180040aea  mov     rcx, rdi; P
0x180040aed  call    MSCryptFree
0x180040af2  lea     r11, [rsp+98h+var_28]
0x180040af7  mov     eax, ebx
0x180040af9  mov     rbx, [r11+30h]
0x180040afd  mov     rbp, [r11+38h]
0x180040b01  mov     rsp, r11
0x180040b04  pop     r15
0x180040b06  pop     r14
0x180040b08  pop     r12
0x180040b0a  pop     rdi
0x180040b0b  pop     rsi
0x180040b0c  retn
```
