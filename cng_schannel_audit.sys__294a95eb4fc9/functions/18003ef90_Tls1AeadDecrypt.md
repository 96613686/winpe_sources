# Tls1AeadDecrypt

- ea: `0x18003ef90`
- end: `0x18003f16e`
- name: `Tls1AeadDecrypt`
- size: `478`
- prototype: `__int64 __fastcall(__int64, char, int, UCHAR *, unsigned int, UCHAR *pbOutput, ULONG cbOutput, ULONG *pcbResult)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003e4f0`

## callees

- `0x18000743c`
- `0x180007b60`
- `0x1800082b0`
- `0x18003ef90`
- `0x18003f174`
- `0x18009d820`
- `0x18009dd40`

## string_xrefs

- `0x18003f106`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18003f155`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
0x18003ef90  mov     [rsp-8+arg_8], rbx
0x18003ef95  push    rbp
0x18003ef96  push    rsi
0x18003ef97  push    rdi
0x18003ef98  push    r12
0x18003ef9a  push    r13
0x18003ef9c  push    r14
0x18003ef9e  push    r15
0x18003efa0  lea     rbp, [rsp-7]
0x18003efa5  sub     rsp, 0F0h
0x18003efac  mov     rax, cs:__security_cookie
0x18003efb3  xor     rax, rsp
0x18003efb6  mov     [rbp+37h+var_40], rax
0x18003efba  mov     rax, [rbp+37h+arg_28]
0x18003efbe  mov     r13d, edx
0x18003efc1  mov     r14d, [rbp+37h+arg_20]
0x18003efc5  xor     edx, edx; Val
0x18003efc7  mov     rsi, [rbp+37h+arg_38]
0x18003efcb  mov     rbx, r8
0x18003efce  mov     r15, rcx
0x18003efd1  mov     [rsp+120h+var_D0], rax
0x18003efd6  lea     rcx, [rsp+120h+pPaddingInfo]; void *
0x18003efdb  mov     r12, r9
0x18003efde  lea     r8d, [rdx+58h]; Size
0x18003efe2  call    memset
0x18003efe7  cmp     r14d, 18h
0x18003efeb  jb      loc_18003F12C
0x18003eff1  movzx   r8d, word ptr [r15+8]
0x18003eff6  lea     rax, [rbp+37h+var_50]
0x18003effa  lea     edi, [r14-18h]
0x18003effe  mov     [rsp+120h+pbIV], rax
0x18003f003  movzx   r9d, di
0x18003f007  mov     dl, r13b
0x18003f00a  mov     rcx, rbx
0x18003f00d  call    Tls1BuildHmacHeader
0x18003f012  xor     r13d, r13d
0x18003f015  mov     ebx, eax
0x18003f017  test    eax, eax
0x18003f019  js      loc_18003F0E7
0x18003f01f  mov     eax, [r15+38h]
0x18003f023  lea     rdx, [r14-10h]
0x18003f027  mov     rcx, [r15+20h]; hKey
0x18003f02b  lea     r9, [rsp+120h+pPaddingInfo]; pPaddingInfo
0x18003f030  mov     [rbp+37h+var_60], eax
0x18003f033  add     rdx, r12
0x18003f036  mov     rax, [r12]
0x18003f03a  mov     r8d, edi; cbInput
0x18003f03d  mov     [rbp+37h+var_5C], rax
0x18003f041  lea     rax, [rbp+37h+var_60]
0x18003f045  mov     [rsp+120h+dwFlags], r13d; dwFlags
0x18003f04a  mov     [rsp+120h+var_B8], rax
0x18003f04f  lea     rax, [rbp+37h+var_50]
0x18003f053  mov     [rsp+120h+pcbResult], rsi; pcbResult
0x18003f058  mov     [rbp+37h+var_A8], rax
0x18003f05c  mov     eax, [rbp+37h+arg_30]
0x18003f05f  mov     [rsp+120h+cbOutput], eax; cbOutput
0x18003f063  mov     rax, [rsp+120h+var_D0]
0x18003f068  mov     [rsp+120h+pbOutput], rax; pbOutput
0x18003f06d  mov     [rbp+37h+var_98], rdx
0x18003f071  lea     rdx, [r12+8]; pbInput
0x18003f076  mov     [rsp+120h+cbIV], r13d; cbIV
0x18003f07b  mov     [rsp+120h+pbIV], r13; pbIV
0x18003f080  mov     [rsp+120h+pPaddingInfo], 58h ; 'X'
0x18003f088  mov     [rsp+120h+var_BC], 1
0x18003f090  mov     [rbp+37h+var_B0], 0Ch
0x18003f097  mov     [rbp+37h+var_A0], 0Dh
0x18003f09e  mov     [rbp+37h+var_90], 10h
0x18003f0a5  call    BCryptDecrypt
0x18003f0aa  test    eax, eax
0x18003f0ac  js      loc_18003F13E
0x18003f0b2  cmp     [rsi], edi
0x18003f0b4  jnz     loc_18003F166
0x18003f0ba  mov     ebx, r13d
0x18003f0bd  mov     eax, ebx
0x18003f0bf  mov     rcx, [rbp+37h+var_40]
0x18003f0c3  xor     rcx, rsp; StackCookie
0x18003f0c6  call    __security_check_cookie
0x18003f0cb  mov     rbx, [rsp+120h+arg_8]
0x18003f0d3  add     rsp, 0F0h
0x18003f0da  pop     r15
0x18003f0dc  pop     r14
0x18003f0de  pop     r13
0x18003f0e0  pop     r12
0x18003f0e2  pop     rdi
0x18003f0e3  pop     rsi
0x18003f0e4  pop     rbp
0x18003f0e5  retn
0x18003f0e7  mov     rax, cs:WPP_GLOBAL_Control
0x18003f0ee  lea     rcx, WPP_GLOBAL_Control
0x18003f0f5  cmp     rax, rcx
0x18003f0f8  jz      short loc_18003F0BD
0x18003f0fa  mov     ecx, [rax+2Ch]
0x18003f0fd  test    cl, 1
0x18003f100  jz      short loc_18003F0BD
0x18003f102  mov     rcx, [rax+18h]
0x18003f106  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f10d  mov     dword ptr [rsp+120h+pbOutput], 2CDh
0x18003f115  lea     r9, aStatus; "Status"
0x18003f11c  mov     qword ptr [rsp+120h+cbIV], r8
0x18003f121  mov     dword ptr [rsp+120h+pbIV], ebx
0x18003f125  call    WPP_SF_sDsd
0x18003f12a  jmp     short loc_18003F0BD
0x18003f12c  mov     ebx, 80090005h
0x18003f131  mov     r9d, 2B2h
0x18003f137  mov     ecx, 80090005h
0x18003f13c  jmp     short loc_18003F14E
0x18003f13e  mov     r9d, 2F9h
0x18003f144  mov     ebx, 8009002Ch
0x18003f149  mov     ecx, 8009002Ch
0x18003f14e  lea     rdx, aStatus; "Status"
0x18003f155  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f15c  call    DebugTraceError
0x18003f161  jmp     loc_18003F0BD
0x18003f166  mov     r9d, 300h
0x18003f16c  jmp     short loc_18003F144
```
