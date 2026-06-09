# Tls1AeadEncrypt

- ea: `0x18003f900`
- end: `0x18003fb17`
- name: `Tls1AeadEncrypt`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003f56c`

## callees

- `0x1800071b0`
- `0x18000743c`
- `0x1800082b0`
- `0x18003f900`
- `0x18003fd04`
- `0x18009f650`
- `0x18009fa80`

## string_xrefs

- `0x18003fa83`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18003fad3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18003fb06`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
0x18003f900  mov     [rsp-8+arg_8], rbx
0x18003f905  mov     [rsp-8+arg_10], rsi
0x18003f90a  push    rbp
0x18003f90b  push    rdi
0x18003f90c  push    r12
0x18003f90e  push    r14
0x18003f910  push    r15
0x18003f912  lea     rbp, [rsp-1Fh]
0x18003f917  sub     rsp, 0F0h
0x18003f91e  mov     rax, cs:__security_cookie
0x18003f925  xor     rax, rsp
0x18003f928  mov     [rbp+3Fh+var_30], rax
0x18003f92c  mov     edi, [rbp+3Fh+cbInput]
0x18003f92f  mov     r15d, edx
0x18003f932  mov     r14, [rbp+3Fh+arg_28]
0x18003f936  xor     edx, edx; Val
0x18003f938  mov     rbx, r8
0x18003f93b  mov     rsi, rcx
0x18003f93e  lea     rcx, [rbp+3Fh+pPaddingInfo]; void *
0x18003f942  mov     r12, r9
0x18003f945  lea     r8d, [rdx+58h]; Size
0x18003f949  call    memset
0x18003f94e  lea     eax, [rdi+18h]
0x18003f951  mov     [rsp+110h+var_C0], 0
0x18003f959  cmp     [rbp+3Fh+arg_30], eax
0x18003f95c  jnz     loc_18003FA5C
0x18003f962  movzx   r8d, word ptr [rsi+8]
0x18003f967  lea     rax, [rbp+3Fh+var_40]
0x18003f96b  movzx   r9d, di
0x18003f96f  mov     [rsp+110h+pbIV], rax
0x18003f974  mov     dl, r15b
0x18003f977  mov     rcx, rbx
0x18003f97a  call    Tls1BuildHmacHeader
0x18003f97f  mov     ebx, eax
0x18003f981  test    eax, eax
0x18003f983  js      loc_18003FAE5
0x18003f989  mov     eax, [rsi+38h]
0x18003f98c  lea     rcx, [rsp+110h+var_C0]
0x18003f991  mov     [rbp+3Fh+var_50], eax
0x18003f994  lea     r8, [rdi+8]
0x18003f998  mov     rax, [rbp+3Fh+var_40]
0x18003f99c  lea     r9, [rbp+3Fh+pPaddingInfo]; pPaddingInfo
0x18003f9a0  mov     [r14], rax
0x18003f9a3  add     r8, r14
0x18003f9a6  mov     [rsp+110h+dwFlags], 0; dwFlags
0x18003f9ae  mov     rdx, r12; pbInput
0x18003f9b1  mov     [rsp+110h+pcbResult], rcx; pcbResult
0x18003f9b6  mov     rcx, [rsi+20h]; hKey
0x18003f9ba  mov     [rbp+3Fh+var_4C], rax
0x18003f9be  lea     rax, [rbp+3Fh+var_50]
0x18003f9c2  mov     [rbp+3Fh+var_A8], rax
0x18003f9c6  lea     rax, [rbp+3Fh+var_40]
0x18003f9ca  mov     [rsp+110h+cbOutput], edi; cbOutput
0x18003f9ce  mov     [rbp+3Fh+var_98], rax
0x18003f9d2  lea     rax, [r14+8]
0x18003f9d6  mov     [rsp+110h+pbOutput], rax; pbOutput
0x18003f9db  mov     [rbp+3Fh+var_88], r8
0x18003f9df  mov     r8d, edi; cbInput
0x18003f9e2  mov     [rsp+110h+cbIV], 0; cbIV
0x18003f9ea  mov     [rsp+110h+pbIV], 0; pbIV
0x18003f9f3  mov     [rbp+3Fh+pPaddingInfo], 58h ; 'X'
0x18003f9fa  mov     [rbp+3Fh+var_AC], 1
0x18003fa01  mov     [rbp+3Fh+var_A0], 0Ch
0x18003fa08  mov     [rbp+3Fh+var_90], 0Dh
0x18003fa0f  mov     [rbp+3Fh+var_80], 10h
0x18003fa16  call    BCryptEncrypt
0x18003fa1b  mov     ebx, eax
0x18003fa1d  test    eax, eax
0x18003fa1f  js      loc_18003FAA9
0x18003fa25  cmp     [rsp+110h+var_C0], edi
0x18003fa29  jnz     loc_18003FAEF
0x18003fa2f  xor     ebx, ebx
0x18003fa31  mov     eax, ebx
0x18003fa33  mov     rcx, [rbp+3Fh+var_30]
0x18003fa37  xor     rcx, rsp; StackCookie
0x18003fa3a  call    __security_check_cookie
0x18003fa3f  lea     r11, [rsp+110h+var_20]
0x18003fa47  mov     rbx, [r11+38h]
0x18003fa4b  mov     rsi, [r11+40h]
0x18003fa4f  mov     rsp, r11
0x18003fa52  pop     r15
0x18003fa54  pop     r14
0x18003fa56  pop     r12
0x18003fa58  pop     rdi
0x18003fa59  pop     rbp
0x18003fa5a  retn
0x18003fa5c  mov     ebx, 8009002Dh
0x18003fa61  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa68  lea     rax, WPP_GLOBAL_Control
0x18003fa6f  cmp     rcx, rax
0x18003fa72  jz      short loc_18003FA31
0x18003fa74  mov     eax, [rcx+2Ch]
0x18003fa77  test    al, 1
0x18003fa79  jz      short loc_18003FA31
0x18003fa7b  mov     dword ptr [rsp+110h+pbOutput], 234h
0x18003fa83  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003fa8a  mov     qword ptr [rsp+110h+cbIV], r8
0x18003fa8f  mov     dword ptr [rsp+110h+pbIV], 8009002Dh
0x18003fa97  mov     rcx, [rcx+18h]
0x18003fa9b  lea     r9, aStatus; "Status"
0x18003faa2  call    WPP_SF_sDsd
0x18003faa7  jmp     short loc_18003FA31
0x18003faa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fab0  lea     rax, WPP_GLOBAL_Control
0x18003fab7  cmp     rcx, rax
0x18003faba  jz      loc_18003FA31
0x18003fac0  mov     eax, [rcx+2Ch]
0x18003fac3  test    al, 1
0x18003fac5  jz      loc_18003FA31
0x18003facb  mov     dword ptr [rsp+110h+pbOutput], 280h
0x18003fad3  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003fada  mov     qword ptr [rsp+110h+cbIV], r8
0x18003fadf  mov     dword ptr [rsp+110h+pbIV], ebx
0x18003fae3  jmp     short loc_18003FA97
0x18003fae5  mov     r9d, 24Bh
0x18003faeb  mov     ecx, eax
0x18003faed  jmp     short loc_18003FAFF
0x18003faef  mov     ebx, 80090020h
0x18003faf4  mov     r9d, 287h
0x18003fafa  mov     ecx, 80090020h
0x18003faff  lea     rdx, aStatus; "Status"
0x18003fb06  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003fb0d  call    DebugTraceError
0x18003fb12  jmp     loc_18003FA31
```
