# ProtectSessionTicket

- ea: `0x180021170`
- end: `0x18002145c`
- name: `ProtectSessionTicket`
- size: `748`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f2c0`

## callees

- `0x18000b654`
- `0x180020ccc`
- `0x180021170`
- `0x180024ef0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x1800213b9`
- `bcrypt!BCryptHashData` at `0x1800213b9`
- `bcrypt!BCryptEncrypt` at `0x180021281`
- `bcrypt!BCryptEncrypt` at `0x180021363`
- `bcrypt!BCryptEncrypt` at `0x180021281`
- `bcrypt!BCryptEncrypt` at `0x180021363`
- `bcrypt!BCryptCreateHash` at `0x180021398`
- `bcrypt!BCryptCreateHash` at `0x180021398`
- `bcrypt!BCryptFinishHash` at `0x1800213dc`
- `bcrypt!BCryptFinishHash` at `0x1800213dc`
- `bcrypt!BCryptDestroyHash` at `0x180021410`
- `bcrypt!BCryptDestroyHash` at `0x180021410`
- `bcrypt!BCryptGenRandom` at `0x180021301`
- `bcrypt!BCryptGenRandom` at `0x180021301`

## string_xrefs

- `0x18002122b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`
- `0x180021293`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`
- `0x1800212c4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`
- `0x1800213ee`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`
- `0x180021421`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`

## pseudocode

```c
__int64 __fastcall ProtectSessionTicket(
        __int64 a1,
        int a2,
        void *a3,
        UCHAR *a4,
        ULONG cbSecret,
        UCHAR *pbInput,
        ULONG cbInput,
        PUCHAR a8,
        ULONG *a9)
{
  unsigned int v10; // edx
  _OWORD *v11; // r10
  void *v12; // r11
  NTSTATUS v14; // eax
  unsigned int v15; // ebx
  NTSTATUS v16; // eax
  __int64 v17; // r9
  ULONG pcbResult; // [rsp+50h] [rbp-30h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-28h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+60h] [rbp-20h]
  UCHAR pbBuffer[16]; // [rsp+68h] [rbp-18h] BYREF

  hKey = a3;
  phHash = 0;
  pcbResult = 0;
  *(_OWORD *)pbBuffer = 0;
  if ( a3 && a1 && a2 == 16 && a4 && cbSecret && cbInput && (!a8 || pbInput) && a9 )
  {
    if ( !(unsigned int)AreBuffersAlignedForProtect(a8, *a9, pbInput, cbInput) )
    {
      DebugTraceError(
        2148073515LL,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c",
        335);
      return 2148073515LL;
    }
    if ( !a8 )
    {
      v14 = BCryptEncrypt(v12, 0, cbInput, 0, 0, 0, 0, 0, &pcbResult, 1u);
      v15 = v14;
      if ( v14 >= 0 )
        *a9 = pcbResult + 68;
      else
        DebugTraceError(
          (unsigned int)v14,
          "status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c",
          355);
      return v15;
    }
    if ( v10 <= 0x44 )
    {
      DebugTraceError(
        2148073512LL,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c",
        366);
      return 2148073512LL;
    }
    *(_DWORD *)a8 = 0;
    *(_OWORD *)(a8 + 4) = *v11;
    v16 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
    v15 = v16;
    if ( v16 >= 0 )
    {
      *(_OWORD *)(a8 + 20) = *(_OWORD *)pbBuffer;
      v16 = BCryptEncrypt(hKey, pbInput, cbInput, 0, pbBuffer, 0x10u, a8 + 68, *a9 - 68, &pcbResult, 1u);
      v15 = v16;
      if ( v16 >= 0 )
      {
        v16 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0xB1, &phHash, 0, 0, a4, cbSecret, 0);
        v15 = v16;
        if ( v16 >= 0 )
        {
          v16 = BCryptHashData(phHash, a8, *a9, 0);
          v15 = v16;
          if ( v16 >= 0 )
          {
            v16 = BCryptFinishHash(phHash, a8 + 36, 0x20u, 0);
            v15 = v16;
            if ( v16 >= 0 )
              goto LABEL_30;
            v17 = 437;
          }
          else
          {
            v17 = 430;
          }
        }
        else
        {
          v17 = 419;
        }
      }
      else
      {
        v17 = 402;
      }
    }
    else
    {
      v17 = 384;
    }
    DebugTraceError(
      (unsigned int)v16,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c",
      v17);
LABEL_30:
    if ( phHash )
      BCryptDestroyHash(phHash);
    return v15;
  }
  DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c", 324);
  return 2148073511LL;
}

```

## disassembly

```asm
0x180021170  push    rbp
0x180021172  push    rbx
0x180021173  push    rsi
0x180021174  push    rdi
0x180021175  push    r12
0x180021177  push    r13
0x180021179  push    r15
0x18002117b  mov     rbp, rsp
0x18002117e  sub     rsp, 80h
0x180021185  mov     rax, cs:__security_cookie
0x18002118c  xor     rax, rsp
0x18002118f  mov     [rbp+var_8], rax
0x180021193  mov     rdi, [rbp+arg_38]
0x180021197  xor     ebx, ebx
0x180021199  mov     r12, [rbp+pbInput]
0x18002119d  xorps   xmm0, xmm0
0x1800211a0  mov     rsi, [rbp+arg_40]
0x1800211a7  mov     r13, r9
0x1800211aa  mov     [rbp+hKey], r8
0x1800211ae  mov     r11, r8
0x1800211b1  mov     [rbp+phHash], rbx
0x1800211b5  mov     r10, rcx
0x1800211b8  mov     [rbp+var_30], ebx
0x1800211bb  movups  xmmword ptr [rbp+pbBuffer], xmm0
0x1800211bf  test    r8, r8
0x1800211c2  jz      loc_18002141B
0x1800211c8  test    rcx, rcx
0x1800211cb  jz      loc_18002141B
0x1800211d1  cmp     edx, 10h
0x1800211d4  jnz     loc_18002141B
0x1800211da  test    r9, r9
0x1800211dd  jz      loc_18002141B
0x1800211e3  mov     r15d, [rbp+cbSecret]
0x1800211e7  test    r15d, r15d
0x1800211ea  jz      loc_18002141B
0x1800211f0  cmp     [rbp+cbInput], ebx
0x1800211f3  jz      loc_18002141B
0x1800211f9  test    rdi, rdi
0x1800211fc  jz      short loc_180021207
0x1800211fe  test    r12, r12
0x180021201  jz      loc_18002141B
0x180021207  test    rsi, rsi
0x18002120a  jz      loc_18002141B
0x180021210  mov     r9d, [rbp+cbInput]
0x180021214  mov     r8, r12
0x180021217  mov     edx, [rsi]
0x180021219  mov     rcx, rdi
0x18002121c  call    AreBuffersAlignedForProtect
0x180021221  test    eax, eax
0x180021223  jnz     short loc_18002124D
0x180021225  mov     r9d, 14Fh
0x18002122b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021232  lea     rdx, aStatus_0; "status"
0x180021239  mov     ecx, 8009002Bh
0x18002123e  call    DebugTraceError
0x180021243  mov     eax, 8009002Bh
0x180021248  jmp     loc_18002143E
0x18002124d  test    rdi, rdi
0x180021250  jnz     short loc_1800212B9
0x180021252  mov     r8d, [rbp+cbInput]; cbInput
0x180021256  lea     rax, [rbp+var_30]
0x18002125a  mov     [rsp+80h+dwFlags], 1; dwFlags
0x180021262  xor     r9d, r9d; pPaddingInfo
0x180021265  mov     [rsp+80h+pcbResult], rax; pcbResult
0x18002126a  xor     edx, edx; pbInput
0x18002126c  mov     [rsp+80h+cbOutput], ebx; cbOutput
0x180021270  mov     rcx, r11; hKey
0x180021273  mov     [rsp+80h+pbOutput], rbx; pbOutput
0x180021278  mov     [rsp+80h+cbIV], ebx; cbIV
0x18002127c  mov     [rsp+80h+pbIV], rbx; pbIV
0x180021281  call    cs:__imp_BCryptEncrypt
0x180021287  mov     ebx, eax
0x180021289  test    eax, eax
0x18002128b  jns     short loc_1800212AA
0x18002128d  mov     r9d, 163h
0x180021293  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002129a  lea     rdx, aStatus_0; "status"
0x1800212a1  mov     ecx, eax
0x1800212a3  call    DebugTraceError
0x1800212a8  jmp     short loc_1800212B2
0x1800212aa  mov     eax, [rbp+var_30]
0x1800212ad  add     eax, 44h ; 'D'
0x1800212b0  mov     [rsi], eax
0x1800212b2  mov     eax, ebx
0x1800212b4  jmp     loc_18002143E
0x1800212b9  cmp     edx, 44h ; 'D'
0x1800212bc  ja      short loc_1800212E6
0x1800212be  mov     r9d, 16Eh
0x1800212c4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800212cb  lea     rdx, aStatus_0; "status"
0x1800212d2  mov     ecx, 80090028h
0x1800212d7  call    DebugTraceError
0x1800212dc  mov     eax, 80090028h
0x1800212e1  jmp     loc_18002143E
0x1800212e6  mov     [rdi], ebx
0x1800212e8  lea     rdx, [rbp+pbBuffer]; pbBuffer
0x1800212ec  movups  xmm0, xmmword ptr [r10]
0x1800212f0  mov     r9d, 2; dwFlags
0x1800212f6  xor     ecx, ecx; hAlgorithm
0x1800212f8  movdqu  xmmword ptr [rdi+4], xmm0
0x1800212fd  lea     r8d, [r9+0Eh]; cbBuffer
0x180021301  call    cs:__imp_BCryptGenRandom
0x180021307  mov     ebx, eax
0x180021309  test    eax, eax
0x18002130b  jns     short loc_180021318
0x18002130d  mov     r9d, 180h
0x180021313  jmp     loc_1800213EE
0x180021318  movups  xmm0, xmmword ptr [rbp+pbBuffer]
0x18002131c  mov     r8d, [rbp+cbInput]; cbInput
0x180021320  lea     rdx, [rbp+var_30]
0x180021324  mov     [rsp+80h+dwFlags], 1; dwFlags
0x18002132c  lea     rax, [rdi+44h]
0x180021330  mov     [rsp+80h+pcbResult], rdx; pcbResult
0x180021335  xor     r9d, r9d; pPaddingInfo
0x180021338  movdqu  xmmword ptr [rdi+14h], xmm0
0x18002133d  mov     ecx, [rsi]
0x18002133f  mov     rdx, r12; pbInput
0x180021342  sub     ecx, 44h ; 'D'
0x180021345  mov     [rsp+80h+cbOutput], ecx; cbOutput
0x180021349  mov     rcx, [rbp+hKey]; hKey
0x18002134d  mov     [rsp+80h+pbOutput], rax; pbOutput
0x180021352  lea     rax, [rbp+pbBuffer]
0x180021356  mov     [rsp+80h+cbIV], 10h; cbIV
0x18002135e  mov     [rsp+80h+pbIV], rax; pbIV
0x180021363  call    cs:__imp_BCryptEncrypt
0x180021369  mov     ebx, eax
0x18002136b  test    eax, eax
0x18002136d  jns     short loc_180021377
0x18002136f  mov     r9d, 192h
0x180021375  jmp     short loc_1800213EE
0x180021377  mov     dword ptr [rsp+80h+pbOutput], 0; dwFlags
0x18002137f  lea     rdx, [rbp+phHash]; phHash
0x180021383  mov     [rsp+80h+cbIV], r15d; cbSecret
0x180021388  xor     r9d, r9d; cbHashObject
0x18002138b  xor     r8d, r8d; pbHashObject
0x18002138e  mov     [rsp+80h+pbIV], r13; pbSecret
0x180021393  mov     ecx, 0B1h; hAlgorithm
0x180021398  call    cs:__imp_BCryptCreateHash
0x18002139e  mov     ebx, eax
0x1800213a0  test    eax, eax
0x1800213a2  jns     short loc_1800213AC
0x1800213a4  mov     r9d, 1A3h
0x1800213aa  jmp     short loc_1800213EE
0x1800213ac  mov     r8d, [rsi]; cbInput
0x1800213af  xor     r9d, r9d; dwFlags
0x1800213b2  mov     rcx, [rbp+phHash]; hHash
0x1800213b6  mov     rdx, rdi; pbInput
0x1800213b9  call    cs:__imp_BCryptHashData
0x1800213bf  mov     ebx, eax
0x1800213c1  test    eax, eax
0x1800213c3  jns     short loc_1800213CD
0x1800213c5  mov     r9d, 1AEh
0x1800213cb  jmp     short loc_1800213EE
0x1800213cd  mov     rcx, [rbp+phHash]; hHash
0x1800213d1  lea     rdx, [rdi+24h]; pbOutput
0x1800213d5  xor     r9d, r9d; dwFlags
0x1800213d8  lea     r8d, [r9+20h]; cbOutput
0x1800213dc  call    cs:__imp_BCryptFinishHash
0x1800213e2  mov     ebx, eax
0x1800213e4  test    eax, eax
0x1800213e6  jns     short loc_180021403
0x1800213e8  mov     r9d, 1B5h
0x1800213ee  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800213f5  mov     ecx, eax
0x1800213f7  lea     rdx, aStatus_0; "status"
0x1800213fe  call    DebugTraceError
0x180021403  mov     rcx, [rbp+phHash]; hHash
0x180021407  test    rcx, rcx
0x18002140a  jz      loc_1800212B2
0x180021410  call    cs:__imp_BCryptDestroyHash
0x180021416  jmp     loc_1800212B2
0x18002141b  mov     r9d, 144h
0x180021421  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021428  lea     rdx, aStatus_0; "status"
0x18002142f  mov     ecx, 80090027h
0x180021434  call    DebugTraceError
0x180021439  mov     eax, 80090027h
0x18002143e  mov     rcx, [rbp+var_8]
0x180021442  xor     rcx, rsp; StackCookie
0x180021445  call    __security_check_cookie
0x18002144a  add     rsp, 80h
0x180021451  pop     r15
0x180021453  pop     r13
0x180021455  pop     r12
0x180021457  pop     rdi
0x180021458  pop     rsi
0x180021459  pop     rbx
0x18002145a  pop     rbp
0x18002145b  retn
```
