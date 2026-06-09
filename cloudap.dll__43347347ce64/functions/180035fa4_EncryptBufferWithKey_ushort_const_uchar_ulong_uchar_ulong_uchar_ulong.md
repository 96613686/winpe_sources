# EncryptBufferWithKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180035fa4`
- end: `0x1800362d1`
- name: `?EncryptBufferWithKey@@YAJPEBGPEAEK1KPEAPEAEPEAK@Z`
- size: `813`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 *, ULONG, unsigned __int8 *, ULONG cbSecret, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180024bb0`
- `0x18003c598`
- `0x18005fe44`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180022f40`
- `0x1800293c0`
- `0x180035fa4`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003629c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003629c`
- `bcrypt!BCryptEncrypt` at `0x1800360eb`
- `bcrypt!BCryptEncrypt` at `0x1800361ac`
- `bcrypt!BCryptEncrypt` at `0x1800360eb`
- `bcrypt!BCryptEncrypt` at `0x1800361ac`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180036078`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180036078`
- `bcrypt!BCryptDestroyKey` at `0x1800362ab`
- `bcrypt!BCryptDestroyKey` at `0x1800362ab`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003601a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003601a`

## string_xrefs

- `0x180036026`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180036084`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x1800360f7`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18003613b`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x1800361b8`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x1800361f4`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180036240`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180036041`: `BCryptOpenAlgorithmProvider`

## pseudocode

```c
__int64 __fastcall EncryptBufferWithKey(
        const unsigned __int16 *a1,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned __int8 *a4,
        ULONG cbSecret,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  UCHAR *Memory; // rdi
  unsigned __int8 **v11; // rsi
  unsigned int *v12; // r14
  unsigned int v13; // ebx
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // r9
  const char *v18; // r9
  ULONG v19; // eax
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // rax
  bool v23; // zf
  PUCHAR pbSecret; // [rsp+20h] [rbp-58h]
  PUCHAR pbSecreta; // [rsp+20h] [rbp-58h]
  PUCHAR pbSecretb; // [rsp+20h] [rbp-58h]
  ULONG v28; // [rsp+50h] [rbp-28h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+C0h] [rbp+48h] BYREF
  int v32; // [rsp+C4h] [rbp+4Ch]

  v32 = HIDWORD(a1);
  phAlgorithm = 0;
  phKey = 0;
  pcbResult = 0;
  Memory = 0;
  v28 = 0;
  if ( a2 && a4 && (v11 = a6) != 0 && (v12 = a7) != 0 )
  {
    *a6 = 0;
    *v12 = 0;
    v13 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
    if ( v13 )
    {
      v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v14, 106, "BCryptOpenAlgorithmProvider", &Class);
    }
    else
    {
      v13 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, a4, cbSecret, 0);
      if ( v13 )
      {
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
        LODWORD(pbSecret) = 117;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v15, pbSecret, "BCryptGenerateSymmetricKey", &Class);
      }
      else
      {
        v13 = BCryptEncrypt(phKey, a2, a3, 0, 0, 0, 0, 0, &pcbResult, 1u);
        if ( v13 )
        {
          v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
          LODWORD(pbSecreta) = 131;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v16, pbSecreta, "BCryptEncrypt", &Class);
        }
        else
        {
          Memory = (UCHAR *)AllocateMemory(pcbResult);
          if ( Memory )
          {
            v13 = BCryptEncrypt(phKey, a2, a3, 0, 0, 0, Memory, pcbResult, &v28, 1u);
            if ( v13 )
            {
              v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
              LODWORD(pbSecretb) = 153;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v18, pbSecretb, "BCryptEncrypt", &Class);
            }
            else
            {
              v19 = pcbResult;
              if ( pcbResult == v28 )
              {
                *v11 = Memory;
                Memory = 0;
                *v12 = v19;
              }
              else
              {
                v13 = -1073741595;
                v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
                LODWORD(pbSecretb) = 158;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v20, pbSecretb, "BCryptEncrypt", &Class);
              }
            }
          }
          else
          {
            v13 = -1073741801;
            v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
            LODWORD(pbSecreta) = 138;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v17, pbSecreta, "AllocateMemory", &Class);
          }
        }
      }
    }
  }
  else
  {
    v13 = -1073741811;
    v21 = "";
    while ( 1 )
    {
      v22 = v21--;
      v23 = *v21 == 92;
      if ( *v21 == 92 )
        break;
      if ( v21 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
      {
        v23 = *v21 == 92;
        break;
      }
    }
    if ( v23 )
      v21 = v22;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v21, 94, "InvalidArgs", &Class);
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( Memory )
    FreeMemory(Memory);
  return v13;
}

```

## disassembly

```asm
0x180035fa4  mov     qword ptr [rsp-40h+arg_0], rcx
0x180035fa9  push    rbp
0x180035faa  push    rbx
0x180035fab  push    rsi
0x180035fac  push    rdi
0x180035fad  push    r12
0x180035faf  push    r13
0x180035fb1  push    r14
0x180035fb3  push    r15
0x180035fb5  mov     rbp, rsp
0x180035fb8  sub     rsp, 78h
0x180035fbc  xor     eax, eax
0x180035fbe  mov     r15, r9
0x180035fc1  mov     [rbp+phAlgorithm], rax
0x180035fc5  mov     r13d, r8d
0x180035fc8  mov     [rbp+phKey], rax
0x180035fcc  mov     r12, rdx
0x180035fcf  mov     [rbp+arg_0], eax
0x180035fd2  mov     edi, eax
0x180035fd4  mov     [rbp+var_28], eax
0x180035fd7  test    rdx, rdx
0x180035fda  jz      loc_180036234
0x180035fe0  test    r9, r9
0x180035fe3  jz      loc_180036234
0x180035fe9  mov     rsi, [rbp+arg_28]
0x180035fed  test    rsi, rsi
0x180035ff0  jz      loc_180036234
0x180035ff6  mov     r14, [rbp+arg_30]
0x180035ffa  test    r14, r14
0x180035ffd  jz      loc_180036234
0x180036003  mov     [rsi], rax
0x180036006  lea     rdx, aAes; "AES"
0x18003600d  xor     r9d, r9d; dwFlags
0x180036010  mov     [r14], eax
0x180036013  xor     r8d, r8d; pszImplementation
0x180036016  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18003601a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180036020  mov     ebx, eax
0x180036022  test    eax, eax
0x180036024  jz      short loc_18003605A
0x180036026  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18003602d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180036032  mov     r9, rax
0x180036035  lea     rax, Class
0x18003603c  mov     qword ptr [rsp+78h+dwFlags], rax
0x180036041  lea     rax, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x180036048  mov     qword ptr [rsp+78h+cbSecret], rax
0x18003604d  mov     dword ptr [rsp+78h+pbSecret], 6Ah ; 'j'
0x180036055  jmp     loc_180036280
0x18003605a  mov     eax, [rbp+arg_20]
0x18003605d  lea     rdx, [rbp+phKey]; phKey
0x180036061  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180036065  xor     r9d, r9d; cbKeyObject
0x180036068  mov     [rsp+78h+dwFlags], edi; dwFlags
0x18003606c  xor     r8d, r8d; pbKeyObject
0x18003606f  mov     [rsp+78h+cbSecret], eax; cbSecret
0x180036073  mov     [rsp+78h+pbSecret], r15; pbSecret
0x180036078  call    cs:__imp_BCryptGenerateSymmetricKey
0x18003607e  mov     ebx, eax
0x180036080  test    eax, eax
0x180036082  jz      short loc_1800360B8
0x180036084  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18003608b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180036090  mov     r9, rax
0x180036093  lea     rax, Class
0x18003609a  mov     qword ptr [rsp+78h+dwFlags], rax
0x18003609f  lea     rax, aBcryptgenerate; "BCryptGenerateSymmetricKey"
0x1800360a6  mov     qword ptr [rsp+78h+cbSecret], rax
0x1800360ab  mov     dword ptr [rsp+78h+pbSecret], 75h ; 'u'
0x1800360b3  jmp     loc_180036280
0x1800360b8  mov     rcx, [rbp+phKey]; hKey
0x1800360bc  lea     rax, [rbp+arg_0]
0x1800360c0  mov     r15d, 1
0x1800360c6  xor     r9d, r9d; pPaddingInfo
0x1800360c9  mov     [rsp+78h+var_30], r15d; dwFlags
0x1800360ce  mov     r8d, r13d; cbInput
0x1800360d1  mov     [rsp+78h+pcbResult], rax; pcbResult
0x1800360d6  mov     rdx, r12; pbInput
0x1800360d9  mov     [rsp+78h+cbOutput], edi; cbOutput
0x1800360dd  mov     qword ptr [rsp+78h+dwFlags], rdi; pbOutput
0x1800360e2  mov     [rsp+78h+cbSecret], edi; cbIV
0x1800360e6  mov     [rsp+78h+pbSecret], rdi; pbIV
0x1800360eb  call    cs:__imp_BCryptEncrypt
0x1800360f1  mov     ebx, eax
0x1800360f3  test    eax, eax
0x1800360f5  jz      short loc_18003612B
0x1800360f7  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800360fe  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180036103  mov     r9, rax
0x180036106  lea     rax, Class
0x18003610d  mov     qword ptr [rsp+78h+dwFlags], rax
0x180036112  lea     rax, aBcryptencrypt; "BCryptEncrypt"
0x180036119  mov     qword ptr [rsp+78h+cbSecret], rax
0x18003611e  mov     dword ptr [rsp+78h+pbSecret], 83h
0x180036126  jmp     loc_180036280
0x18003612b  mov     ecx, [rbp+arg_0]; uBytes
0x18003612e  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x180036133  mov     rdi, rax
0x180036136  test    rax, rax
0x180036139  jnz     short loc_180036174
0x18003613b  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180036142  mov     ebx, 0C0000017h
0x180036147  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003614c  mov     r9, rax
0x18003614f  lea     rax, Class
0x180036156  mov     qword ptr [rsp+78h+dwFlags], rax
0x18003615b  lea     rax, aAllocatememory; "AllocateMemory"
0x180036162  mov     qword ptr [rsp+78h+cbSecret], rax
0x180036167  mov     dword ptr [rsp+78h+pbSecret], 8Ah
0x18003616f  jmp     loc_180036280
0x180036174  mov     rcx, [rbp+phKey]; hKey
0x180036178  lea     rax, [rbp+var_28]
0x18003617c  mov     [rsp+78h+var_30], r15d; dwFlags
0x180036181  xor     r9d, r9d; pPaddingInfo
0x180036184  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180036189  mov     r8d, r13d; cbInput
0x18003618c  mov     eax, [rbp+arg_0]
0x18003618f  mov     rdx, r12; pbInput
0x180036192  mov     [rsp+78h+cbOutput], eax; cbOutput
0x180036196  mov     qword ptr [rsp+78h+dwFlags], rdi; pbOutput
0x18003619b  mov     [rsp+78h+cbSecret], 0; cbIV
0x1800361a3  mov     [rsp+78h+pbSecret], 0; pbIV
0x1800361ac  call    cs:__imp_BCryptEncrypt
0x1800361b2  mov     ebx, eax
0x1800361b4  test    eax, eax
0x1800361b6  jz      short loc_1800361EC
0x1800361b8  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800361bf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800361c4  mov     r9, rax
0x1800361c7  lea     rax, Class
0x1800361ce  mov     qword ptr [rsp+78h+dwFlags], rax
0x1800361d3  lea     rax, aBcryptencrypt; "BCryptEncrypt"
0x1800361da  mov     qword ptr [rsp+78h+cbSecret], rax
0x1800361df  mov     dword ptr [rsp+78h+pbSecret], 99h
0x1800361e7  jmp     loc_180036280
0x1800361ec  mov     eax, [rbp+arg_0]
0x1800361ef  cmp     eax, [rbp+var_28]
0x1800361f2  jz      short loc_18003622A
0x1800361f4  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800361fb  mov     ebx, 0C00000E5h
0x180036200  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180036205  mov     r9, rax
0x180036208  lea     rax, Class
0x18003620f  mov     qword ptr [rsp+78h+dwFlags], rax
0x180036214  lea     rax, aBcryptencrypt; "BCryptEncrypt"
0x18003621b  mov     qword ptr [rsp+78h+cbSecret], rax
0x180036220  mov     dword ptr [rsp+78h+pbSecret], 9Eh
0x180036228  jmp     short loc_180036280
0x18003622a  mov     [rsi], rdi
0x18003622d  xor     edi, edi
0x18003622f  mov     [r14], eax
0x180036232  jmp     short loc_180036291
0x180036234  mov     ebx, 0C000000Dh
0x180036239  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x180036240  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180036247  mov     rax, r9
0x18003624a  dec     r9
0x18003624d  cmp     byte ptr [r9], 5Ch ; '\'
0x180036251  jz      short loc_18003625C
0x180036253  cmp     r9, rcx
0x180036256  ja      short loc_180036247
0x180036258  cmp     byte ptr [r9], 5Ch ; '\'
0x18003625c  cmovz   r9, rax
0x180036260  lea     rax, Class
0x180036267  mov     qword ptr [rsp+78h+dwFlags], rax
0x18003626c  lea     rax, aInvalidargs; "InvalidArgs"
0x180036273  mov     qword ptr [rsp+78h+cbSecret], rax
0x180036278  mov     dword ptr [rsp+78h+pbSecret], 5Eh ; '^'
0x180036280  mov     r8d, ebx
0x180036283  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003628a  xor     ecx, ecx
0x18003628c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180036291  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180036295  test    rcx, rcx
0x180036298  jz      short loc_1800362A2
0x18003629a  xor     edx, edx; dwFlags
0x18003629c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800362a2  mov     rcx, [rbp+phKey]; hKey
0x1800362a6  test    rcx, rcx
0x1800362a9  jz      short loc_1800362B1
0x1800362ab  call    cs:__imp_BCryptDestroyKey
0x1800362b1  test    rdi, rdi
0x1800362b4  jz      short loc_1800362BE
0x1800362b6  mov     rcx, rdi; void *
0x1800362b9  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x1800362be  mov     eax, ebx
0x1800362c0  add     rsp, 78h
0x1800362c4  pop     r15
0x1800362c6  pop     r14
0x1800362c8  pop     r13
0x1800362ca  pop     r12
0x1800362cc  pop     rdi
0x1800362cd  pop     rsi
0x1800362ce  pop     rbx
0x1800362cf  pop     rbp
0x1800362d0  retn
```
