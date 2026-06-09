# Tls1AeadDecrypt

- ea: `0x180048f50`
- end: `0x18004912e`
- name: `Tls1AeadDecrypt`
- size: `478`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, ULONG, ULONG *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800484b0`

## callees

- `0x18001155c`
- `0x180011c80`
- `0x1800123d0`
- `0x180048f50`
- `0x180049134`
- `0x1800a4260`
- `0x1800a4380`

## string_xrefs

- `0x1800490c6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180049115`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
0x180048f50  mov     [rsp-8+arg_8], rbx
0x180048f55  push    rbp
0x180048f56  push    rsi
0x180048f57  push    rdi
0x180048f58  push    r12
0x180048f5a  push    r13
0x180048f5c  push    r14
0x180048f5e  push    r15
0x180048f60  lea     rbp, [rsp-7]
0x180048f65  sub     rsp, 0F0h
0x180048f6c  mov     rax, cs:__security_cookie
0x180048f73  xor     rax, rsp
0x180048f76  mov     [rbp+37h+var_40], rax
0x180048f7a  mov     rax, [rbp+37h+arg_28]
0x180048f7e  mov     r13d, edx
0x180048f81  mov     r14d, [rbp+37h+arg_20]
0x180048f85  xor     edx, edx; Val
0x180048f87  mov     rsi, [rbp+37h+arg_38]
0x180048f8b  mov     rbx, r8
0x180048f8e  mov     r15, rcx
0x180048f91  mov     [rsp+120h+var_D0], rax
0x180048f96  lea     rcx, [rsp+120h+pPaddingInfo]; void *
0x180048f9b  mov     r12, r9
0x180048f9e  lea     r8d, [rdx+58h]; Size
0x180048fa2  call    memset
0x180048fa7  cmp     r14d, 18h
0x180048fab  jb      loc_1800490EC
0x180048fb1  movzx   r8d, word ptr [r15+8]
0x180048fb6  lea     rax, [rbp+37h+var_50]
0x180048fba  lea     edi, [r14-18h]
0x180048fbe  mov     [rsp+120h+pbIV], rax
0x180048fc3  movzx   r9d, di
0x180048fc7  mov     dl, r13b
0x180048fca  mov     rcx, rbx
0x180048fcd  call    Tls1BuildHmacHeader
0x180048fd2  xor     r13d, r13d
0x180048fd5  mov     ebx, eax
0x180048fd7  test    eax, eax
0x180048fd9  js      loc_1800490A7
0x180048fdf  mov     eax, [r15+38h]
0x180048fe3  lea     rdx, [r14-10h]
0x180048fe7  mov     rcx, [r15+20h]; hKey
0x180048feb  lea     r9, [rsp+120h+pPaddingInfo]; pPaddingInfo
0x180048ff0  mov     [rbp+37h+var_60], eax
0x180048ff3  add     rdx, r12
0x180048ff6  mov     rax, [r12]
0x180048ffa  mov     r8d, edi; cbInput
0x180048ffd  mov     [rbp+37h+var_5C], rax
0x180049001  lea     rax, [rbp+37h+var_60]
0x180049005  mov     [rsp+120h+dwFlags], r13d; dwFlags
0x18004900a  mov     [rsp+120h+var_B8], rax
0x18004900f  lea     rax, [rbp+37h+var_50]
0x180049013  mov     [rsp+120h+pcbResult], rsi; pcbResult
0x180049018  mov     [rbp+37h+var_A8], rax
0x18004901c  mov     eax, [rbp+37h+arg_30]
0x18004901f  mov     [rsp+120h+cbOutput], eax; cbOutput
0x180049023  mov     rax, [rsp+120h+var_D0]
0x180049028  mov     [rsp+120h+pbOutput], rax; pbOutput
0x18004902d  mov     [rbp+37h+var_98], rdx
0x180049031  lea     rdx, [r12+8]; pbInput
0x180049036  mov     [rsp+120h+cbIV], r13d; cbIV
0x18004903b  mov     [rsp+120h+pbIV], r13; pbIV
0x180049040  mov     [rsp+120h+pPaddingInfo], 58h ; 'X'
0x180049048  mov     [rsp+120h+var_BC], 1
0x180049050  mov     [rbp+37h+var_B0], 0Ch
0x180049057  mov     [rbp+37h+var_A0], 0Dh
0x18004905e  mov     [rbp+37h+var_90], 10h
0x180049065  call    BCryptDecrypt
0x18004906a  test    eax, eax
0x18004906c  js      loc_1800490FE
0x180049072  cmp     [rsi], edi
0x180049074  jnz     loc_180049126
0x18004907a  mov     ebx, r13d
0x18004907d  mov     eax, ebx
0x18004907f  mov     rcx, [rbp+37h+var_40]
0x180049083  xor     rcx, rsp; StackCookie
0x180049086  call    __security_check_cookie
0x18004908b  mov     rbx, [rsp+120h+arg_8]
0x180049093  add     rsp, 0F0h
0x18004909a  pop     r15
0x18004909c  pop     r14
0x18004909e  pop     r13
0x1800490a0  pop     r12
0x1800490a2  pop     rdi
0x1800490a3  pop     rsi
0x1800490a4  pop     rbp
0x1800490a5  retn
0x1800490a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800490ae  lea     rcx, WPP_GLOBAL_Control
0x1800490b5  cmp     rax, rcx
0x1800490b8  jz      short loc_18004907D
0x1800490ba  mov     ecx, [rax+2Ch]
0x1800490bd  test    cl, 1
0x1800490c0  jz      short loc_18004907D
0x1800490c2  mov     rcx, [rax+18h]
0x1800490c6  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800490cd  mov     dword ptr [rsp+120h+pbOutput], 2CDh
0x1800490d5  lea     r9, aStatus; "Status"
0x1800490dc  mov     qword ptr [rsp+120h+cbIV], r8
0x1800490e1  mov     dword ptr [rsp+120h+pbIV], ebx
0x1800490e5  call    WPP_SF_sDsd
0x1800490ea  jmp     short loc_18004907D
0x1800490ec  mov     ebx, 80090005h
0x1800490f1  mov     r9d, 2B2h
0x1800490f7  mov     ecx, 80090005h
0x1800490fc  jmp     short loc_18004910E
0x1800490fe  mov     r9d, 2F9h
0x180049104  mov     ebx, 8009002Ch
0x180049109  mov     ecx, 8009002Ch
0x18004910e  lea     rdx, aStatus; "Status"
0x180049115  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004911c  call    DebugTraceError
0x180049121  jmp     loc_18004907D
0x180049126  mov     r9d, 300h
0x18004912c  jmp     short loc_180049104
```
