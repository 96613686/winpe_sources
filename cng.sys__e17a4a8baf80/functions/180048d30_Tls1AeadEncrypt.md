# Tls1AeadEncrypt

- ea: `0x180048d30`
- end: `0x180048f47`
- name: `Tls1AeadEncrypt`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004899c`

## callees

- `0x1800112d0`
- `0x18001155c`
- `0x1800123d0`
- `0x180048d30`
- `0x180049134`
- `0x1800a4260`
- `0x1800a4380`

## string_xrefs

- `0x180048eb3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180048f03`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180048f36`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls1AeadEncrypt(__int64 a1, char a2, int a3, UCHAR *a4, ULONG cbInput, __int64 a6, int a7)
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
    LOBYTE(v11) = a2;
    v12 = Tls1BuildHmacHeader(a3, v11, *(unsigned __int16 *)(a1 + 8), (unsigned __int16)cbInput, (__int64)v24);
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
0x180048d30  mov     [rsp-8+arg_8], rbx
0x180048d35  mov     [rsp-8+arg_10], rsi
0x180048d3a  push    rbp
0x180048d3b  push    rdi
0x180048d3c  push    r12
0x180048d3e  push    r14
0x180048d40  push    r15
0x180048d42  lea     rbp, [rsp-1Fh]
0x180048d47  sub     rsp, 0F0h
0x180048d4e  mov     rax, cs:__security_cookie
0x180048d55  xor     rax, rsp
0x180048d58  mov     [rbp+3Fh+var_30], rax
0x180048d5c  mov     edi, [rbp+3Fh+cbInput]
0x180048d5f  mov     r15d, edx
0x180048d62  mov     r14, [rbp+3Fh+arg_28]
0x180048d66  xor     edx, edx; Val
0x180048d68  mov     rbx, r8
0x180048d6b  mov     rsi, rcx
0x180048d6e  lea     rcx, [rbp+3Fh+pPaddingInfo]; void *
0x180048d72  mov     r12, r9
0x180048d75  lea     r8d, [rdx+58h]; Size
0x180048d79  call    memset
0x180048d7e  lea     eax, [rdi+18h]
0x180048d81  mov     [rsp+110h+var_C0], 0
0x180048d89  cmp     [rbp+3Fh+arg_30], eax
0x180048d8c  jnz     loc_180048E8C
0x180048d92  movzx   r8d, word ptr [rsi+8]
0x180048d97  lea     rax, [rbp+3Fh+var_40]
0x180048d9b  movzx   r9d, di
0x180048d9f  mov     [rsp+110h+pbIV], rax
0x180048da4  mov     dl, r15b
0x180048da7  mov     rcx, rbx
0x180048daa  call    Tls1BuildHmacHeader
0x180048daf  mov     ebx, eax
0x180048db1  test    eax, eax
0x180048db3  js      loc_180048F15
0x180048db9  mov     eax, [rsi+38h]
0x180048dbc  lea     rcx, [rsp+110h+var_C0]
0x180048dc1  mov     [rbp+3Fh+var_50], eax
0x180048dc4  lea     r8, [rdi+8]
0x180048dc8  mov     rax, [rbp+3Fh+var_40]
0x180048dcc  lea     r9, [rbp+3Fh+pPaddingInfo]; pPaddingInfo
0x180048dd0  mov     [r14], rax
0x180048dd3  add     r8, r14
0x180048dd6  mov     [rsp+110h+dwFlags], 0; dwFlags
0x180048dde  mov     rdx, r12; pbInput
0x180048de1  mov     [rsp+110h+pcbResult], rcx; pcbResult
0x180048de6  mov     rcx, [rsi+20h]; hKey
0x180048dea  mov     [rbp+3Fh+var_4C], rax
0x180048dee  lea     rax, [rbp+3Fh+var_50]
0x180048df2  mov     [rbp+3Fh+var_A8], rax
0x180048df6  lea     rax, [rbp+3Fh+var_40]
0x180048dfa  mov     [rsp+110h+cbOutput], edi; cbOutput
0x180048dfe  mov     [rbp+3Fh+var_98], rax
0x180048e02  lea     rax, [r14+8]
0x180048e06  mov     [rsp+110h+pbOutput], rax; pbOutput
0x180048e0b  mov     [rbp+3Fh+var_88], r8
0x180048e0f  mov     r8d, edi; cbInput
0x180048e12  mov     [rsp+110h+cbIV], 0; cbIV
0x180048e1a  mov     [rsp+110h+pbIV], 0; pbIV
0x180048e23  mov     [rbp+3Fh+pPaddingInfo], 58h ; 'X'
0x180048e2a  mov     [rbp+3Fh+var_AC], 1
0x180048e31  mov     [rbp+3Fh+var_A0], 0Ch
0x180048e38  mov     [rbp+3Fh+var_90], 0Dh
0x180048e3f  mov     [rbp+3Fh+var_80], 10h
0x180048e46  call    BCryptEncrypt
0x180048e4b  mov     ebx, eax
0x180048e4d  test    eax, eax
0x180048e4f  js      loc_180048ED9
0x180048e55  cmp     [rsp+110h+var_C0], edi
0x180048e59  jnz     loc_180048F1F
0x180048e5f  xor     ebx, ebx
0x180048e61  mov     eax, ebx
0x180048e63  mov     rcx, [rbp+3Fh+var_30]
0x180048e67  xor     rcx, rsp; StackCookie
0x180048e6a  call    __security_check_cookie
0x180048e6f  lea     r11, [rsp+110h+var_20]
0x180048e77  mov     rbx, [r11+38h]
0x180048e7b  mov     rsi, [r11+40h]
0x180048e7f  mov     rsp, r11
0x180048e82  pop     r15
0x180048e84  pop     r14
0x180048e86  pop     r12
0x180048e88  pop     rdi
0x180048e89  pop     rbp
0x180048e8a  retn
0x180048e8c  mov     ebx, 8009002Dh
0x180048e91  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e98  lea     rax, WPP_GLOBAL_Control
0x180048e9f  cmp     rcx, rax
0x180048ea2  jz      short loc_180048E61
0x180048ea4  mov     eax, [rcx+2Ch]
0x180048ea7  test    al, 1
0x180048ea9  jz      short loc_180048E61
0x180048eab  mov     dword ptr [rsp+110h+pbOutput], 234h
0x180048eb3  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048eba  mov     qword ptr [rsp+110h+cbIV], r8
0x180048ebf  mov     dword ptr [rsp+110h+pbIV], 8009002Dh
0x180048ec7  mov     rcx, [rcx+18h]
0x180048ecb  lea     r9, aStatus; "Status"
0x180048ed2  call    WPP_SF_sDsd
0x180048ed7  jmp     short loc_180048E61
0x180048ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180048ee0  lea     rax, WPP_GLOBAL_Control
0x180048ee7  cmp     rcx, rax
0x180048eea  jz      loc_180048E61
0x180048ef0  mov     eax, [rcx+2Ch]
0x180048ef3  test    al, 1
0x180048ef5  jz      loc_180048E61
0x180048efb  mov     dword ptr [rsp+110h+pbOutput], 280h
0x180048f03  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048f0a  mov     qword ptr [rsp+110h+cbIV], r8
0x180048f0f  mov     dword ptr [rsp+110h+pbIV], ebx
0x180048f13  jmp     short loc_180048EC7
0x180048f15  mov     r9d, 24Bh
0x180048f1b  mov     ecx, eax
0x180048f1d  jmp     short loc_180048F2F
0x180048f1f  mov     ebx, 80090020h
0x180048f24  mov     r9d, 287h
0x180048f2a  mov     ecx, 80090020h
0x180048f2f  lea     rdx, aStatus; "Status"
0x180048f36  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048f3d  call    DebugTraceError
0x180048f42  jmp     loc_180048E61
```
