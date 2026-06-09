# Tls1AeadEncrypt

- ea: `0x18003ed70`
- end: `0x18003ef87`
- name: `Tls1AeadEncrypt`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003e9dc`

## callees

- `0x1800071b0`
- `0x18000743c`
- `0x1800082b0`
- `0x18003ed70`
- `0x18003f174`
- `0x18009d820`
- `0x18009dd40`

## string_xrefs

- `0x18003eef3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18003ef43`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18003ef76`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls1AeadEncrypt(__int64 a1, char a2, __int64 a3, UCHAR *a4, ULONG cbInput, __int64 a6, int a7)
{
  int v11; // edx
  int v12; // eax
  NTSTATUS v13; // ebx
  __int64 v14; // rax
  void *v15; // rcx
  int v16; // edx
  __int64 v18; // r9
  __int64 v19; // rcx
  ULONG pcbResult[4]; // [rsp+50h] [rbp-81h] BYREF
  _QWORD pPaddingInfo[12]; // [rsp+60h] [rbp-71h] BYREF
  int v22; // [rsp+C0h] [rbp-11h] BYREF
  __int64 v23; // [rsp+C4h] [rbp-Dh]
  _QWORD v24[2]; // [rsp+D0h] [rbp-1h] BYREF

  memset(pPaddingInfo, 0, 0x58u);
  pcbResult[0] = 0;
  if ( a7 == cbInput + 24 )
  {
    v12 = Tls1BuildHmacHeader(a3, a2, *(_WORD *)(a1 + 8), cbInput, v24);
    v13 = v12;
    if ( v12 < 0 )
    {
      v18 = 587;
      v19 = (unsigned int)v12;
      goto LABEL_16;
    }
    v22 = *(_DWORD *)(a1 + 56);
    v14 = v24[0];
    *(_QWORD *)a6 = v24[0];
    v15 = *(void **)(a1 + 32);
    v23 = v14;
    pPaddingInfo[1] = &v22;
    pPaddingInfo[3] = v24;
    pPaddingInfo[5] = a6 + cbInput + 8LL;
    pPaddingInfo[0] = 0x100000058LL;
    LODWORD(pPaddingInfo[2]) = 12;
    LODWORD(pPaddingInfo[4]) = 13;
    LODWORD(pPaddingInfo[6]) = 16;
    v13 = BCryptEncrypt(v15, a4, cbInput, pPaddingInfo, 0, 0, (PUCHAR)(a6 + 8), cbInput, pcbResult, 0);
    if ( v13 >= 0 )
    {
      if ( pcbResult[0] == cbInput )
        return 0;
      v13 = -2146893792;
      v18 = 647;
      v19 = 2148073504LL;
LABEL_16:
      DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v18);
      return (unsigned int)v13;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v16,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        (unsigned int)"Status",
        v13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        128);
  }
  else
  {
    v13 = -2146893779;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v11,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        (unsigned int)"Status",
        45,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        52);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18003ed70  mov     [rsp-8+arg_8], rbx
0x18003ed75  mov     [rsp-8+arg_10], rsi
0x18003ed7a  push    rbp
0x18003ed7b  push    rdi
0x18003ed7c  push    r12
0x18003ed7e  push    r14
0x18003ed80  push    r15
0x18003ed82  lea     rbp, [rsp-1Fh]
0x18003ed87  sub     rsp, 0F0h
0x18003ed8e  mov     rax, cs:__security_cookie
0x18003ed95  xor     rax, rsp
0x18003ed98  mov     [rbp+3Fh+var_30], rax
0x18003ed9c  mov     edi, [rbp+3Fh+cbInput]
0x18003ed9f  mov     r15d, edx
0x18003eda2  mov     r14, [rbp+3Fh+arg_28]
0x18003eda6  xor     edx, edx; Val
0x18003eda8  mov     rbx, r8
0x18003edab  mov     rsi, rcx
0x18003edae  lea     rcx, [rbp+3Fh+pPaddingInfo]; void *
0x18003edb2  mov     r12, r9
0x18003edb5  lea     r8d, [rdx+58h]; Size
0x18003edb9  call    memset
0x18003edbe  lea     eax, [rdi+18h]
0x18003edc1  mov     [rsp+110h+var_C0], 0
0x18003edc9  cmp     [rbp+3Fh+arg_30], eax
0x18003edcc  jnz     loc_18003EECC
0x18003edd2  movzx   r8d, word ptr [rsi+8]
0x18003edd7  lea     rax, [rbp+3Fh+var_40]
0x18003eddb  movzx   r9d, di
0x18003eddf  mov     [rsp+110h+pbIV], rax
0x18003ede4  mov     dl, r15b
0x18003ede7  mov     rcx, rbx
0x18003edea  call    Tls1BuildHmacHeader
0x18003edef  mov     ebx, eax
0x18003edf1  test    eax, eax
0x18003edf3  js      loc_18003EF55
0x18003edf9  mov     eax, [rsi+38h]
0x18003edfc  lea     rcx, [rsp+110h+var_C0]
0x18003ee01  mov     [rbp+3Fh+var_50], eax
0x18003ee04  lea     r8, [rdi+8]
0x18003ee08  mov     rax, [rbp+3Fh+var_40]
0x18003ee0c  lea     r9, [rbp+3Fh+pPaddingInfo]; pPaddingInfo
0x18003ee10  mov     [r14], rax
0x18003ee13  add     r8, r14
0x18003ee16  mov     [rsp+110h+dwFlags], 0; dwFlags
0x18003ee1e  mov     rdx, r12; pbInput
0x18003ee21  mov     [rsp+110h+pcbResult], rcx; pcbResult
0x18003ee26  mov     rcx, [rsi+20h]; hKey
0x18003ee2a  mov     [rbp+3Fh+var_4C], rax
0x18003ee2e  lea     rax, [rbp+3Fh+var_50]
0x18003ee32  mov     [rbp+3Fh+var_A8], rax
0x18003ee36  lea     rax, [rbp+3Fh+var_40]
0x18003ee3a  mov     [rsp+110h+cbOutput], edi; cbOutput
0x18003ee3e  mov     [rbp+3Fh+var_98], rax
0x18003ee42  lea     rax, [r14+8]
0x18003ee46  mov     [rsp+110h+pbOutput], rax; pbOutput
0x18003ee4b  mov     [rbp+3Fh+var_88], r8
0x18003ee4f  mov     r8d, edi; cbInput
0x18003ee52  mov     [rsp+110h+cbIV], 0; cbIV
0x18003ee5a  mov     [rsp+110h+pbIV], 0; pbIV
0x18003ee63  mov     [rbp+3Fh+pPaddingInfo], 58h ; 'X'
0x18003ee6a  mov     [rbp+3Fh+var_AC], 1
0x18003ee71  mov     [rbp+3Fh+var_A0], 0Ch
0x18003ee78  mov     [rbp+3Fh+var_90], 0Dh
0x18003ee7f  mov     [rbp+3Fh+var_80], 10h
0x18003ee86  call    BCryptEncrypt
0x18003ee8b  mov     ebx, eax
0x18003ee8d  test    eax, eax
0x18003ee8f  js      loc_18003EF19
0x18003ee95  cmp     [rsp+110h+var_C0], edi
0x18003ee99  jnz     loc_18003EF5F
0x18003ee9f  xor     ebx, ebx
0x18003eea1  mov     eax, ebx
0x18003eea3  mov     rcx, [rbp+3Fh+var_30]
0x18003eea7  xor     rcx, rsp; StackCookie
0x18003eeaa  call    __security_check_cookie
0x18003eeaf  lea     r11, [rsp+110h+var_20]
0x18003eeb7  mov     rbx, [r11+38h]
0x18003eebb  mov     rsi, [r11+40h]
0x18003eebf  mov     rsp, r11
0x18003eec2  pop     r15
0x18003eec4  pop     r14
0x18003eec6  pop     r12
0x18003eec8  pop     rdi
0x18003eec9  pop     rbp
0x18003eeca  retn
0x18003eecc  mov     ebx, 8009002Dh
0x18003eed1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eed8  lea     rax, WPP_GLOBAL_Control
0x18003eedf  cmp     rcx, rax
0x18003eee2  jz      short loc_18003EEA1
0x18003eee4  mov     eax, [rcx+2Ch]
0x18003eee7  test    al, 1
0x18003eee9  jz      short loc_18003EEA1
0x18003eeeb  mov     dword ptr [rsp+110h+pbOutput], 234h
0x18003eef3  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003eefa  mov     qword ptr [rsp+110h+cbIV], r8
0x18003eeff  mov     dword ptr [rsp+110h+pbIV], 8009002Dh
0x18003ef07  mov     rcx, [rcx+18h]
0x18003ef0b  lea     r9, aStatus; "Status"
0x18003ef12  call    WPP_SF_sDsd
0x18003ef17  jmp     short loc_18003EEA1
0x18003ef19  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef20  lea     rax, WPP_GLOBAL_Control
0x18003ef27  cmp     rcx, rax
0x18003ef2a  jz      loc_18003EEA1
0x18003ef30  mov     eax, [rcx+2Ch]
0x18003ef33  test    al, 1
0x18003ef35  jz      loc_18003EEA1
0x18003ef3b  mov     dword ptr [rsp+110h+pbOutput], 280h
0x18003ef43  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003ef4a  mov     qword ptr [rsp+110h+cbIV], r8
0x18003ef4f  mov     dword ptr [rsp+110h+pbIV], ebx
0x18003ef53  jmp     short loc_18003EF07
0x18003ef55  mov     r9d, 24Bh
0x18003ef5b  mov     ecx, eax
0x18003ef5d  jmp     short loc_18003EF6F
0x18003ef5f  mov     ebx, 80090020h
0x18003ef64  mov     r9d, 287h
0x18003ef6a  mov     ecx, 80090020h
0x18003ef6f  lea     rdx, aStatus; "Status"
0x18003ef76  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003ef7d  call    DebugTraceError
0x18003ef82  jmp     loc_18003EEA1
```
