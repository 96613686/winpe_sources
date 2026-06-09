# UnprotectSessionTicket

- ea: `0x180021464`
- end: `0x180021706`
- name: `UnprotectSessionTicket`
- size: `674`
- prototype: `__int64 __usercall@<rax>(BCRYPT_KEY_HANDLE hKey@<rcx>, ULONG cbInput, PUCHAR pbOutput, ULONG *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f3b0`

## callees

- `0x18000b654`
- `0x180020ccc`
- `0x180021464`
- `0x180024ef0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x1800215da`
- `bcrypt!BCryptHashData` at `0x1800215da`
- `bcrypt!BCryptCreateHash` at `0x1800215b6`
- `bcrypt!BCryptCreateHash` at `0x1800215b6`
- `bcrypt!BCryptDecrypt` at `0x180021689`
- `bcrypt!BCryptDecrypt` at `0x180021689`
- `bcrypt!BCryptFinishHash` at `0x1800215ff`
- `bcrypt!BCryptFinishHash` at `0x1800215ff`
- `bcrypt!BCryptDestroyHash` at `0x1800216b9`
- `bcrypt!BCryptDestroyHash` at `0x1800216b9`

## string_xrefs

- `0x180021510`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`
- `0x18002153d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`
- `0x18002169d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`
- `0x1800216c9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`

## pseudocode

```c
__int64 __fastcall UnprotectSessionTicket(
        BCRYPT_KEY_HANDLE hKey,
        __int64 a2,
        int a3,
        __int64 a4,
        ULONG cbInput,
        PUCHAR pbOutput,
        ULONG *pcbResult)
{
  __int64 v9; // r9
  UCHAR *pbSecret; // r10
  ULONG cbSecret; // r11d
  unsigned int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int128 v16; // xmm1
  NTSTATUS v17; // eax
  char v18; // r8
  __int64 i; // rdx
  char v20; // cl
  char v21; // al
  ULONG cbOutput; // [rsp+38h] [rbp-59h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-41h] BYREF
  _OWORD v24[2]; // [rsp+58h] [rbp-39h]
  UCHAR pbIV[16]; // [rsp+78h] [rbp-19h] BYREF

  phHash = 0;
  *(_OWORD *)pbIV = 0;
  if ( !hKey || !a2 || !a3 || !a4 || !cbInput || !pbOutput || !pcbResult || (v9 = *pcbResult, !(_DWORD)v9) )
  {
    DebugTraceError(
      2148073511LL,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c",
      481);
    return 2148073511LL;
  }
  if ( !(unsigned int)AreBuffersAlignedForProtect(a4, cbInput, pbOutput, v9) )
  {
    DebugTraceError(
      2148073515LL,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c",
      492);
    return 2148073515LL;
  }
  if ( cbInput <= 0x44 )
  {
    DebugTraceError(
      2148073512LL,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c",
      499);
    return 2148073512LL;
  }
  if ( *(_DWORD *)a4 )
  {
    v13 = -2146893785;
    v14 = 509;
    v15 = 2148073511LL;
LABEL_28:
    DebugTraceError(v15, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c", v14);
    goto LABEL_29;
  }
  v16 = *(_OWORD *)(a4 + 52);
  v24[0] = *(_OWORD *)(a4 + 36);
  *(_OWORD *)(a4 + 36) = 0;
  *(_OWORD *)(a4 + 52) = 0;
  v24[1] = v16;
  v17 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0xB1, &phHash, 0, 0, pbSecret, cbSecret, 0);
  v13 = v17;
  if ( v17 < 0 )
  {
    v14 = 528;
LABEL_27:
    v15 = (unsigned int)v17;
    goto LABEL_28;
  }
  v17 = BCryptHashData(phHash, (PUCHAR)a4, cbInput, 0);
  v13 = v17;
  if ( v17 < 0 )
  {
    v14 = 539;
    goto LABEL_27;
  }
  v17 = BCryptFinishHash(phHash, (PUCHAR)(a4 + 36), 0x20u, 0);
  v13 = v17;
  if ( v17 < 0 )
  {
    v14 = 546;
    goto LABEL_27;
  }
  v18 = 0;
  for ( i = 0; i != 32; ++i )
  {
    v20 = *(_BYTE *)(i + a4 + 36);
    v21 = *((_BYTE *)v24 + i);
    v18 |= v21 ^ v20;
  }
  if ( v18 )
  {
    v13 = -2146893822;
    v14 = 553;
    v15 = 2148073474LL;
    goto LABEL_28;
  }
  cbOutput = *pcbResult;
  *(_OWORD *)pbIV = *(_OWORD *)(a4 + 20);
  v17 = BCryptDecrypt(hKey, (PUCHAR)(a4 + 68), cbInput - 68, 0, pbIV, 0x10u, pbOutput, cbOutput, pcbResult, 1u);
  v13 = v17;
  if ( v17 < 0 )
  {
    v14 = 574;
    goto LABEL_27;
  }
LABEL_29:
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v13;
}

```

## disassembly

```asm
0x180021464  push    rbp
0x180021466  push    rbx
0x180021467  push    rsi
0x180021468  push    rdi
0x180021469  push    r12
0x18002146b  push    r13
0x18002146d  push    r14
0x18002146f  push    r15
0x180021471  lea     rbp, [rsp-7]
0x180021476  sub     rsp, 98h
0x18002147d  mov     rax, cs:__security_cookie
0x180021484  xor     rax, rsp
0x180021487  mov     [rbp+3Fh+var_48], rax
0x18002148b  mov     r12, [rbp+3Fh+pbOutput]
0x18002148f  xor     ebx, ebx
0x180021491  mov     r15, [rbp+3Fh+arg_30]
0x180021495  xorps   xmm0, xmm0
0x180021498  mov     [rbp+3Fh+phHash], rbx
0x18002149c  mov     rdi, r9
0x18002149f  mov     r11d, r8d
0x1800214a2  mov     r10, rdx
0x1800214a5  mov     r13, rcx
0x1800214a8  movups  xmmword ptr [rbp+3Fh+pbIV], xmm0
0x1800214ac  test    rcx, rcx
0x1800214af  jz      loc_1800216C3
0x1800214b5  test    rdx, rdx
0x1800214b8  jz      loc_1800216C3
0x1800214be  test    r8d, r8d
0x1800214c1  jz      loc_1800216C3
0x1800214c7  test    r9, r9
0x1800214ca  jz      loc_1800216C3
0x1800214d0  mov     esi, [rbp+3Fh+cbInput]
0x1800214d3  test    esi, esi
0x1800214d5  jz      loc_1800216C3
0x1800214db  test    r12, r12
0x1800214de  jz      loc_1800216C3
0x1800214e4  test    r15, r15
0x1800214e7  jz      loc_1800216C3
0x1800214ed  mov     r9d, [r15]
0x1800214f0  test    r9d, r9d
0x1800214f3  jz      loc_1800216C3
0x1800214f9  mov     r8, r12
0x1800214fc  mov     edx, esi
0x1800214fe  mov     rcx, rdi
0x180021501  call    AreBuffersAlignedForProtect
0x180021506  test    eax, eax
0x180021508  jnz     short loc_180021532
0x18002150a  mov     r9d, 1ECh
0x180021510  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021517  lea     rdx, aStatus_0; "status"
0x18002151e  mov     ecx, 8009002Bh
0x180021523  call    DebugTraceError
0x180021528  mov     eax, 8009002Bh
0x18002152d  jmp     loc_1800216E6
0x180021532  cmp     esi, 44h ; 'D'
0x180021535  ja      short loc_18002155F
0x180021537  mov     r9d, 1F3h
0x18002153d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021544  lea     rdx, aStatus_0; "status"
0x18002154b  mov     ecx, 80090028h
0x180021550  call    DebugTraceError
0x180021555  mov     eax, 80090028h
0x18002155a  jmp     loc_1800216E6
0x18002155f  cmp     [rdi], ebx
0x180021561  jz      short loc_180021578
0x180021563  mov     ebx, 80090027h
0x180021568  mov     r9d, 1FDh
0x18002156e  mov     ecx, 80090027h
0x180021573  jmp     loc_18002169D
0x180021578  lea     r14, [rdi+24h]
0x18002157c  mov     [rsp+0D0h+dwFlags], ebx; dwFlags
0x180021580  movups  xmm0, xmmword ptr [r14]
0x180021584  mov     [rsp+0D0h+cbSecret], r11d; cbSecret
0x180021589  xor     r9d, r9d; cbHashObject
0x18002158c  movups  xmm1, xmmword ptr [r14+10h]
0x180021591  xor     r8d, r8d; pbHashObject
0x180021594  lea     rdx, [rbp+3Fh+phHash]; phHash
0x180021598  movups  [rbp+3Fh+var_78], xmm0
0x18002159c  mov     [rsp+0D0h+pbSecret], r10; pbSecret
0x1800215a1  mov     ecx, 0B1h; hAlgorithm
0x1800215a6  xorps   xmm0, xmm0
0x1800215a9  movups  xmmword ptr [r14], xmm0
0x1800215ad  movups  xmmword ptr [r14+10h], xmm0
0x1800215b2  movups  [rbp+3Fh+var_68], xmm1
0x1800215b6  call    cs:__imp_BCryptCreateHash
0x1800215bc  mov     ebx, eax
0x1800215be  test    eax, eax
0x1800215c0  jns     short loc_1800215CD
0x1800215c2  mov     r9d, 210h
0x1800215c8  jmp     loc_18002169B
0x1800215cd  mov     rcx, [rbp+3Fh+phHash]; hHash
0x1800215d1  xor     r9d, r9d; dwFlags
0x1800215d4  mov     r8d, esi; cbInput
0x1800215d7  mov     rdx, rdi; pbInput
0x1800215da  call    cs:__imp_BCryptHashData
0x1800215e0  mov     ebx, eax
0x1800215e2  test    eax, eax
0x1800215e4  jns     short loc_1800215F1
0x1800215e6  mov     r9d, 21Bh
0x1800215ec  jmp     loc_18002169B
0x1800215f1  mov     rcx, [rbp+3Fh+phHash]; hHash
0x1800215f5  xor     r9d, r9d; dwFlags
0x1800215f8  mov     rdx, r14; pbOutput
0x1800215fb  lea     r8d, [r9+20h]; cbOutput
0x1800215ff  call    cs:__imp_BCryptFinishHash
0x180021605  mov     ebx, eax
0x180021607  test    eax, eax
0x180021609  jns     short loc_180021616
0x18002160b  mov     r9d, 222h
0x180021611  jmp     loc_18002169B
0x180021616  xor     r8b, r8b
0x180021619  xor     edx, edx
0x18002161b  mov     cl, [rdx+r14]
0x18002161f  mov     al, byte ptr [rbp+rdx+3Fh+var_78]
0x180021623  inc     rdx
0x180021626  xor     cl, al
0x180021628  or      r8b, cl
0x18002162b  cmp     rdx, 20h ; ' '
0x18002162f  jnz     short loc_18002161B
0x180021631  test    r8b, r8b
0x180021634  jz      short loc_180021648
0x180021636  mov     ebx, 80090002h
0x18002163b  mov     r9d, 229h
0x180021641  mov     ecx, 80090002h
0x180021646  jmp     short loc_18002169D
0x180021648  mov     eax, [r15]
0x18002164b  lea     r8d, [rsi-44h]; cbInput
0x18002164f  movups  xmm0, xmmword ptr [rdi+14h]
0x180021653  mov     [rsp+0D0h+var_88], 1; dwFlags
0x18002165b  lea     rdx, [rdi+44h]; pbInput
0x18002165f  mov     [rsp+0D0h+pcbResult], r15; pcbResult
0x180021664  xor     r9d, r9d; pPaddingInfo
0x180021667  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x18002166b  mov     rcx, r13; hKey
0x18002166e  mov     qword ptr [rsp+0D0h+dwFlags], r12; pbOutput
0x180021673  lea     rax, [rbp+3Fh+pbIV]
0x180021677  mov     [rsp+0D0h+cbSecret], 10h; cbIV
0x18002167f  mov     [rsp+0D0h+pbSecret], rax; pbIV
0x180021684  movdqu  xmmword ptr [rbp+3Fh+pbIV], xmm0
0x180021689  call    cs:__imp_BCryptDecrypt
0x18002168f  mov     ebx, eax
0x180021691  test    eax, eax
0x180021693  jns     short loc_1800216B0
0x180021695  mov     r9d, 23Eh
0x18002169b  mov     ecx, eax
0x18002169d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800216a4  lea     rdx, aStatus_0; "status"
0x1800216ab  call    DebugTraceError
0x1800216b0  mov     rcx, [rbp+3Fh+phHash]; hHash
0x1800216b4  test    rcx, rcx
0x1800216b7  jz      short loc_1800216BF
0x1800216b9  call    cs:__imp_BCryptDestroyHash
0x1800216bf  mov     eax, ebx
0x1800216c1  jmp     short loc_1800216E6
0x1800216c3  mov     r9d, 1E1h
0x1800216c9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800216d0  lea     rdx, aStatus_0; "status"
0x1800216d7  mov     ecx, 80090027h
0x1800216dc  call    DebugTraceError
0x1800216e1  mov     eax, 80090027h
0x1800216e6  mov     rcx, [rbp+3Fh+var_48]
0x1800216ea  xor     rcx, rsp; StackCookie
0x1800216ed  call    __security_check_cookie
0x1800216f2  add     rsp, 98h
0x1800216f9  pop     r15
0x1800216fb  pop     r14
0x1800216fd  pop     r13
0x1800216ff  pop     r12
0x180021701  pop     rdi
0x180021702  pop     rsi
0x180021703  pop     rbx
0x180021704  pop     rbp
0x180021705  retn
```
