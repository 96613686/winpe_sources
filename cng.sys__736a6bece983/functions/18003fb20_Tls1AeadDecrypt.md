# Tls1AeadDecrypt

- ea: `0x18003fb20`
- end: `0x18003fcfe`
- name: `Tls1AeadDecrypt`
- size: `478`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, ULONG, ULONG *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003f080`

## callees

- `0x18000743c`
- `0x180007b60`
- `0x1800082b0`
- `0x18003fb20`
- `0x18003fd04`
- `0x18009f650`
- `0x18009fa80`

## string_xrefs

- `0x18003fc96`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18003fce5`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls1AeadDecrypt(
        __int64 a1,
        char a2,
        int a3,
        UCHAR *a4,
        unsigned int a5,
        UCHAR *pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult)
{
  int v12; // edx
  ULONG v13; // edi
  int v14; // edx
  int v15; // ebx
  void *v16; // rcx
  __int64 v18; // r9
  __int64 v19; // rcx
  _QWORD pPaddingInfo[12]; // [rsp+60h] [rbp-89h] BYREF
  int v21; // [rsp+C0h] [rbp-29h] BYREF
  __int64 v22; // [rsp+C4h] [rbp-25h]
  _BYTE v23[16]; // [rsp+D0h] [rbp-19h] BYREF

  memset(pPaddingInfo, 0, 0x58u);
  if ( a5 < 0x18 )
  {
    v15 = -2146893819;
    v18 = 690;
    v19 = 2148073477LL;
    goto LABEL_13;
  }
  v13 = a5 - 24;
  LOBYTE(v12) = a2;
  v15 = Tls1BuildHmacHeader(a3, v12, *(unsigned __int16 *)(a1 + 8), (unsigned __int16)(a5 - 24), (__int64)v23);
  if ( v15 >= 0 )
  {
    v16 = *(void **)(a1 + 32);
    v21 = *(_DWORD *)(a1 + 56);
    v22 = *(_QWORD *)a4;
    pPaddingInfo[1] = &v21;
    pPaddingInfo[3] = v23;
    pPaddingInfo[5] = &a4[a5 - 16];
    pPaddingInfo[0] = 0x100000058LL;
    LODWORD(pPaddingInfo[2]) = 12;
    LODWORD(pPaddingInfo[4]) = 13;
    LODWORD(pPaddingInfo[6]) = 16;
    if ( BCryptDecrypt(v16, a4 + 8, v13, pPaddingInfo, 0, 0, pbOutput, cbOutput, pcbResult, 0) < 0 )
    {
      v18 = 761;
    }
    else
    {
      if ( *pcbResult == v13 )
        return 0;
      v18 = 768;
    }
    v15 = -2146893780;
    v19 = 2148073516LL;
LABEL_13:
    DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v18);
    return (unsigned int)v15;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v14,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      (unsigned int)"Status",
      v15,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      205);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18003fb20  mov     [rsp-8+arg_8], rbx
0x18003fb25  push    rbp
0x18003fb26  push    rsi
0x18003fb27  push    rdi
0x18003fb28  push    r12
0x18003fb2a  push    r13
0x18003fb2c  push    r14
0x18003fb2e  push    r15
0x18003fb30  lea     rbp, [rsp-7]
0x18003fb35  sub     rsp, 0F0h
0x18003fb3c  mov     rax, cs:__security_cookie
0x18003fb43  xor     rax, rsp
0x18003fb46  mov     [rbp+37h+var_40], rax
0x18003fb4a  mov     rax, [rbp+37h+arg_28]
0x18003fb4e  mov     r13d, edx
0x18003fb51  mov     r14d, [rbp+37h+arg_20]
0x18003fb55  xor     edx, edx; Val
0x18003fb57  mov     rsi, [rbp+37h+arg_38]
0x18003fb5b  mov     rbx, r8
0x18003fb5e  mov     r15, rcx
0x18003fb61  mov     [rsp+120h+var_D0], rax
0x18003fb66  lea     rcx, [rsp+120h+pPaddingInfo]; void *
0x18003fb6b  mov     r12, r9
0x18003fb6e  lea     r8d, [rdx+58h]; Size
0x18003fb72  call    memset
0x18003fb77  cmp     r14d, 18h
0x18003fb7b  jb      loc_18003FCBC
0x18003fb81  movzx   r8d, word ptr [r15+8]
0x18003fb86  lea     rax, [rbp+37h+var_50]
0x18003fb8a  lea     edi, [r14-18h]
0x18003fb8e  mov     [rsp+120h+pbIV], rax
0x18003fb93  movzx   r9d, di
0x18003fb97  mov     dl, r13b
0x18003fb9a  mov     rcx, rbx
0x18003fb9d  call    Tls1BuildHmacHeader
0x18003fba2  xor     r13d, r13d
0x18003fba5  mov     ebx, eax
0x18003fba7  test    eax, eax
0x18003fba9  js      loc_18003FC77
0x18003fbaf  mov     eax, [r15+38h]
0x18003fbb3  lea     rdx, [r14-10h]
0x18003fbb7  mov     rcx, [r15+20h]; hKey
0x18003fbbb  lea     r9, [rsp+120h+pPaddingInfo]; pPaddingInfo
0x18003fbc0  mov     [rbp+37h+var_60], eax
0x18003fbc3  add     rdx, r12
0x18003fbc6  mov     rax, [r12]
0x18003fbca  mov     r8d, edi; cbInput
0x18003fbcd  mov     [rbp+37h+var_5C], rax
0x18003fbd1  lea     rax, [rbp+37h+var_60]
0x18003fbd5  mov     [rsp+120h+dwFlags], r13d; dwFlags
0x18003fbda  mov     [rsp+120h+var_B8], rax
0x18003fbdf  lea     rax, [rbp+37h+var_50]
0x18003fbe3  mov     [rsp+120h+pcbResult], rsi; pcbResult
0x18003fbe8  mov     [rbp+37h+var_A8], rax
0x18003fbec  mov     eax, [rbp+37h+arg_30]
0x18003fbef  mov     [rsp+120h+cbOutput], eax; cbOutput
0x18003fbf3  mov     rax, [rsp+120h+var_D0]
0x18003fbf8  mov     [rsp+120h+pbOutput], rax; pbOutput
0x18003fbfd  mov     [rbp+37h+var_98], rdx
0x18003fc01  lea     rdx, [r12+8]; pbInput
0x18003fc06  mov     [rsp+120h+cbIV], r13d; cbIV
0x18003fc0b  mov     [rsp+120h+pbIV], r13; pbIV
0x18003fc10  mov     [rsp+120h+pPaddingInfo], 58h ; 'X'
0x18003fc18  mov     [rsp+120h+var_BC], 1
0x18003fc20  mov     [rbp+37h+var_B0], 0Ch
0x18003fc27  mov     [rbp+37h+var_A0], 0Dh
0x18003fc2e  mov     [rbp+37h+var_90], 10h
0x18003fc35  call    BCryptDecrypt
0x18003fc3a  test    eax, eax
0x18003fc3c  js      loc_18003FCCE
0x18003fc42  cmp     [rsi], edi
0x18003fc44  jnz     loc_18003FCF6
0x18003fc4a  mov     ebx, r13d
0x18003fc4d  mov     eax, ebx
0x18003fc4f  mov     rcx, [rbp+37h+var_40]
0x18003fc53  xor     rcx, rsp; StackCookie
0x18003fc56  call    __security_check_cookie
0x18003fc5b  mov     rbx, [rsp+120h+arg_8]
0x18003fc63  add     rsp, 0F0h
0x18003fc6a  pop     r15
0x18003fc6c  pop     r14
0x18003fc6e  pop     r13
0x18003fc70  pop     r12
0x18003fc72  pop     rdi
0x18003fc73  pop     rsi
0x18003fc74  pop     rbp
0x18003fc75  retn
0x18003fc77  mov     rax, cs:WPP_GLOBAL_Control
0x18003fc7e  lea     rcx, WPP_GLOBAL_Control
0x18003fc85  cmp     rax, rcx
0x18003fc88  jz      short loc_18003FC4D
0x18003fc8a  mov     ecx, [rax+2Ch]
0x18003fc8d  test    cl, 1
0x18003fc90  jz      short loc_18003FC4D
0x18003fc92  mov     rcx, [rax+18h]
0x18003fc96  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003fc9d  mov     dword ptr [rsp+120h+pbOutput], 2CDh
0x18003fca5  lea     r9, aStatus; "Status"
0x18003fcac  mov     qword ptr [rsp+120h+cbIV], r8
0x18003fcb1  mov     dword ptr [rsp+120h+pbIV], ebx
0x18003fcb5  call    WPP_SF_sDsd
0x18003fcba  jmp     short loc_18003FC4D
0x18003fcbc  mov     ebx, 80090005h
0x18003fcc1  mov     r9d, 2B2h
0x18003fcc7  mov     ecx, 80090005h
0x18003fccc  jmp     short loc_18003FCDE
0x18003fcce  mov     r9d, 2F9h
0x18003fcd4  mov     ebx, 8009002Ch
0x18003fcd9  mov     ecx, 8009002Ch
0x18003fcde  lea     rdx, aStatus; "Status"
0x18003fce5  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003fcec  call    DebugTraceError
0x18003fcf1  jmp     loc_18003FC4D
0x18003fcf6  mov     r9d, 300h
0x18003fcfc  jmp     short loc_18003FCD4
```
