# DecryptBufferWithKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180035c54`
- end: `0x180035f73`
- name: `?DecryptBufferWithKey@@YAJPEBGPEAEK1KPEAPEAEPEAK@Z`
- size: `799`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 *, ULONG, unsigned __int8 *, ULONG cbSecret, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e130`
- `0x18003cd70`
- `0x18005fe44`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180022f40`
- `0x1800293c0`
- `0x180035c54`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180035f27`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180035f27`
- `bcrypt!BCryptDecrypt` at `0x180035dae`
- `bcrypt!BCryptDecrypt` at `0x180035e6b`
- `bcrypt!BCryptDecrypt` at `0x180035dae`
- `bcrypt!BCryptDecrypt` at `0x180035e6b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180035d28`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180035d28`
- `bcrypt!BCryptDestroyKey` at `0x180035f36`
- `bcrypt!BCryptDestroyKey` at `0x180035f36`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180035cca`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180035cca`

## string_xrefs

- `0x180035cd6`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180035d37`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180035dba`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180035dfe`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180035e77`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180035ec8`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180035cf1`: `BCryptOpenAlgorithmProvider`

## pseudocode

```c
__int64 __fastcall DecryptBufferWithKey(
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
  const char *v21; // rax
  bool v22; // zf
  __int64 v23; // rax
  UCHAR *v24; // rcx
  PUCHAR pbSecret; // [rsp+20h] [rbp-58h]
  PUCHAR pbSecreta; // [rsp+20h] [rbp-58h]
  PUCHAR pbSecretb; // [rsp+20h] [rbp-58h]
  ULONG v29; // [rsp+50h] [rbp-28h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+C0h] [rbp+48h] BYREF
  int v33; // [rsp+C4h] [rbp+4Ch]

  v33 = HIDWORD(a1);
  phAlgorithm = 0;
  phKey = 0;
  pcbResult = 0;
  Memory = 0;
  v29 = 0;
  if ( a2 && a4 && (v11 = a6) != 0 && (v12 = a7) != 0 )
  {
    *a6 = 0;
    *v12 = 0;
    v13 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
    if ( v13 )
    {
      v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v14, 295, "BCryptOpenAlgorithmProvider", &Class);
    }
    else
    {
      v13 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, a4, cbSecret, 0);
      if ( v13 )
      {
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
        LODWORD(pbSecret) = 306;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v15, pbSecret, "BCryptGenerateSymmetricKey", &Class);
      }
      else
      {
        v13 = BCryptDecrypt(phKey, a2, a3, 0, 0, 0, 0, 0, &pcbResult, 1u);
        if ( v13 )
        {
          v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
          LODWORD(pbSecreta) = 320;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v16, pbSecreta, "BCryptDecrypt", &Class);
        }
        else
        {
          Memory = (UCHAR *)AllocateMemory(pcbResult);
          if ( Memory )
          {
            v13 = BCryptDecrypt(phKey, a2, a3, 0, 0, 0, Memory, pcbResult, &v29, 1u);
            if ( v13 )
            {
              v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
              LODWORD(pbSecretb) = 342;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v18, pbSecretb, "BCryptDecrypt", &Class);
            }
            else
            {
              v19 = v29;
              *v11 = Memory;
              Memory = 0;
              pcbResult = v19;
              *v12 = v19;
            }
          }
          else
          {
            v13 = -1073741801;
            v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
            LODWORD(pbSecreta) = 327;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v17, pbSecreta, "AllocateMemory", &Class);
          }
        }
      }
    }
  }
  else
  {
    v13 = -1073741811;
    v20 = "";
    while ( 1 )
    {
      v21 = v20--;
      v22 = *v20 == 92;
      if ( *v20 == 92 )
        break;
      if ( v20 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
      {
        v22 = *v20 == 92;
        break;
      }
    }
    if ( v22 )
      v20 = v21;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v20, 283, "InvalidArgs", &Class);
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( Memory )
  {
    v23 = pcbResult;
    v24 = Memory;
    if ( pcbResult )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    FreeMemory(Memory);
  }
  return v13;
}

```

## disassembly

```asm
0x180035c54  mov     qword ptr [rsp-40h+arg_0], rcx
0x180035c59  push    rbp
0x180035c5a  push    rbx
0x180035c5b  push    rsi
0x180035c5c  push    rdi
0x180035c5d  push    r12
0x180035c5f  push    r13
0x180035c61  push    r14
0x180035c63  push    r15
0x180035c65  mov     rbp, rsp
0x180035c68  sub     rsp, 78h
0x180035c6c  xor     eax, eax
0x180035c6e  mov     r12, r9
0x180035c71  mov     [rbp+phAlgorithm], rax
0x180035c75  mov     r13d, r8d
0x180035c78  mov     [rbp+phKey], rax
0x180035c7c  mov     r15, rdx
0x180035c7f  mov     [rbp+arg_0], eax
0x180035c82  mov     edi, eax
0x180035c84  mov     [rbp+var_28], eax
0x180035c87  test    rdx, rdx
0x180035c8a  jz      loc_180035EBC
0x180035c90  test    r9, r9
0x180035c93  jz      loc_180035EBC
0x180035c99  mov     rsi, [rbp+arg_28]
0x180035c9d  test    rsi, rsi
0x180035ca0  jz      loc_180035EBC
0x180035ca6  mov     r14, [rbp+arg_30]
0x180035caa  test    r14, r14
0x180035cad  jz      loc_180035EBC
0x180035cb3  mov     [rsi], rax
0x180035cb6  lea     rdx, aAes; "AES"
0x180035cbd  xor     r9d, r9d; dwFlags
0x180035cc0  mov     [r14], eax
0x180035cc3  xor     r8d, r8d; pszImplementation
0x180035cc6  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180035cca  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180035cd0  mov     ebx, eax
0x180035cd2  test    eax, eax
0x180035cd4  jz      short loc_180035D0A
0x180035cd6  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180035cdd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035ce2  mov     r9, rax
0x180035ce5  lea     rax, Class
0x180035cec  mov     qword ptr [rsp+78h+dwFlags], rax
0x180035cf1  lea     rax, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x180035cf8  mov     qword ptr [rsp+78h+cbSecret], rax
0x180035cfd  mov     dword ptr [rsp+78h+pbSecret], 127h
0x180035d05  jmp     loc_180035F08
0x180035d0a  mov     eax, [rbp+arg_20]
0x180035d0d  lea     rdx, [rbp+phKey]; phKey
0x180035d11  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180035d15  xor     r9d, r9d; cbKeyObject
0x180035d18  mov     [rsp+78h+dwFlags], edi; dwFlags
0x180035d1c  xor     r8d, r8d; pbKeyObject
0x180035d1f  mov     [rsp+78h+cbSecret], eax; cbSecret
0x180035d23  mov     [rsp+78h+pbSecret], r12; pbSecret
0x180035d28  call    cs:__imp_BCryptGenerateSymmetricKey
0x180035d2e  xor     r12d, r12d
0x180035d31  mov     ebx, eax
0x180035d33  test    eax, eax
0x180035d35  jz      short loc_180035D7C
0x180035d37  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180035d3e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035d43  mov     r9, rax
0x180035d46  lea     rax, Class
0x180035d4d  mov     qword ptr [rsp+78h+dwFlags], rax
0x180035d52  lea     rax, aBcryptgenerate; "BCryptGenerateSymmetricKey"
0x180035d59  mov     qword ptr [rsp+78h+cbSecret], rax
0x180035d5e  mov     dword ptr [rsp+78h+pbSecret], 132h
0x180035d66  mov     r8d, ebx
0x180035d69  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180035d70  xor     ecx, ecx
0x180035d72  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180035d77  jmp     loc_180035F1C
0x180035d7c  mov     rcx, [rbp+phKey]; hKey
0x180035d80  lea     rax, [rbp+arg_0]
0x180035d84  mov     [rsp+78h+var_30], 1; dwFlags
0x180035d8c  xor     r9d, r9d; pPaddingInfo
0x180035d8f  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180035d94  mov     r8d, r13d; cbInput
0x180035d97  mov     [rsp+78h+cbOutput], r12d; cbOutput
0x180035d9c  mov     rdx, r15; pbInput
0x180035d9f  mov     qword ptr [rsp+78h+dwFlags], r12; pbOutput
0x180035da4  mov     [rsp+78h+cbSecret], r12d; cbIV
0x180035da9  mov     [rsp+78h+pbSecret], r12; pbIV
0x180035dae  call    cs:__imp_BCryptDecrypt
0x180035db4  mov     ebx, eax
0x180035db6  test    eax, eax
0x180035db8  jz      short loc_180035DEE
0x180035dba  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180035dc1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035dc6  mov     r9, rax
0x180035dc9  lea     rax, Class
0x180035dd0  mov     qword ptr [rsp+78h+dwFlags], rax
0x180035dd5  lea     rax, aBcryptdecrypt; "BCryptDecrypt"
0x180035ddc  mov     qword ptr [rsp+78h+cbSecret], rax
0x180035de1  mov     dword ptr [rsp+78h+pbSecret], 140h
0x180035de9  jmp     loc_180035D66
0x180035dee  mov     ecx, [rbp+arg_0]; uBytes
0x180035df1  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x180035df6  mov     rdi, rax
0x180035df9  test    rax, rax
0x180035dfc  jnz     short loc_180035E37
0x180035dfe  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180035e05  mov     ebx, 0C0000017h
0x180035e0a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035e0f  mov     r9, rax
0x180035e12  lea     rax, Class
0x180035e19  mov     qword ptr [rsp+78h+dwFlags], rax
0x180035e1e  lea     rax, aAllocatememory; "AllocateMemory"
0x180035e25  mov     qword ptr [rsp+78h+cbSecret], rax
0x180035e2a  mov     dword ptr [rsp+78h+pbSecret], 147h
0x180035e32  jmp     loc_180035D66
0x180035e37  mov     rcx, [rbp+phKey]; hKey
0x180035e3b  lea     rax, [rbp+var_28]
0x180035e3f  mov     [rsp+78h+var_30], 1; dwFlags
0x180035e47  xor     r9d, r9d; pPaddingInfo
0x180035e4a  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180035e4f  mov     r8d, r13d; cbInput
0x180035e52  mov     eax, [rbp+arg_0]
0x180035e55  mov     rdx, r15; pbInput
0x180035e58  mov     [rsp+78h+cbOutput], eax; cbOutput
0x180035e5c  mov     qword ptr [rsp+78h+dwFlags], rdi; pbOutput
0x180035e61  mov     [rsp+78h+cbSecret], r12d; cbIV
0x180035e66  mov     [rsp+78h+pbSecret], r12; pbIV
0x180035e6b  call    cs:__imp_BCryptDecrypt
0x180035e71  mov     ebx, eax
0x180035e73  test    eax, eax
0x180035e75  jz      short loc_180035EAB
0x180035e77  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180035e7e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180035e83  mov     r9, rax
0x180035e86  lea     rax, Class
0x180035e8d  mov     qword ptr [rsp+78h+dwFlags], rax
0x180035e92  lea     rax, aBcryptdecrypt; "BCryptDecrypt"
0x180035e99  mov     qword ptr [rsp+78h+cbSecret], rax
0x180035e9e  mov     dword ptr [rsp+78h+pbSecret], 156h
0x180035ea6  jmp     loc_180035D66
0x180035eab  mov     eax, [rbp+var_28]
0x180035eae  mov     [rsi], rdi
0x180035eb1  mov     rdi, r12
0x180035eb4  mov     [rbp+arg_0], eax
0x180035eb7  mov     [r14], eax
0x180035eba  jmp     short loc_180035F1C
0x180035ebc  mov     ebx, 0C000000Dh
0x180035ec1  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x180035ec8  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180035ecf  mov     rax, r9
0x180035ed2  dec     r9
0x180035ed5  cmp     byte ptr [r9], 5Ch ; '\'
0x180035ed9  jz      short loc_180035EE4
0x180035edb  cmp     r9, rcx
0x180035ede  ja      short loc_180035ECF
0x180035ee0  cmp     byte ptr [r9], 5Ch ; '\'
0x180035ee4  cmovz   r9, rax
0x180035ee8  lea     rax, Class
0x180035eef  mov     qword ptr [rsp+78h+dwFlags], rax
0x180035ef4  lea     rax, aInvalidargs; "InvalidArgs"
0x180035efb  mov     qword ptr [rsp+78h+cbSecret], rax
0x180035f00  mov     dword ptr [rsp+78h+pbSecret], 11Bh
0x180035f08  mov     r8d, ebx
0x180035f0b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180035f12  xor     ecx, ecx
0x180035f14  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180035f19  xor     r12d, r12d
0x180035f1c  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180035f20  test    rcx, rcx
0x180035f23  jz      short loc_180035F2D
0x180035f25  xor     edx, edx; dwFlags
0x180035f27  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180035f2d  mov     rcx, [rbp+phKey]; hKey
0x180035f31  test    rcx, rcx
0x180035f34  jz      short loc_180035F3C
0x180035f36  call    cs:__imp_BCryptDestroyKey
0x180035f3c  test    rdi, rdi
0x180035f3f  jz      short loc_180035F60
0x180035f41  mov     eax, [rbp+arg_0]
0x180035f44  mov     rcx, rdi
0x180035f47  test    rax, rax
0x180035f4a  jz      short loc_180035F58
0x180035f4c  mov     [rcx], r12b
0x180035f4f  inc     rcx
0x180035f52  sub     rax, 1
0x180035f56  jnz     short loc_180035F4C
0x180035f58  mov     rcx, rdi; void *
0x180035f5b  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x180035f60  mov     eax, ebx
0x180035f62  add     rsp, 78h
0x180035f66  pop     r15
0x180035f68  pop     r14
0x180035f6a  pop     r13
0x180035f6c  pop     r12
0x180035f6e  pop     rdi
0x180035f6f  pop     rsi
0x180035f70  pop     rbx
0x180035f71  pop     rbp
0x180035f72  retn
```
