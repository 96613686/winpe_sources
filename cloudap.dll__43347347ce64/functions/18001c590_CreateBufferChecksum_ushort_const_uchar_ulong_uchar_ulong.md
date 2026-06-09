# CreateBufferChecksum(ushort const *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001c590`
- end: `0x18001c9c8`
- name: `?CreateBufferChecksum@@YAJPEBGPEAEKPEAPEAEPEAK@Z`
- size: `1080`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 *, ULONG, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001c000`
- `0x18002e3e0`
- `0x180061600`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18001c590`
- `0x1800293c0`
- `0x180081010`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001c737`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001c737`
- `bcrypt!BCryptDestroyHash` at `0x18001c758`
- `bcrypt!BCryptDestroyHash` at `0x18001c758`
- `bcrypt!BCryptFinishHash` at `0x18001c6f0`
- `bcrypt!BCryptFinishHash` at `0x18001c6f0`
- `bcrypt!BCryptGetProperty` at `0x18001c649`
- `bcrypt!BCryptGetProperty` at `0x18001c649`
- `bcrypt!BCryptCreateHash` at `0x18001c6af`
- `bcrypt!BCryptCreateHash` at `0x18001c6af`
- `bcrypt!BCryptHashData` at `0x18001c6cd`
- `bcrypt!BCryptHashData` at `0x18001c6cd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001c610`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001c610`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c8f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c8f7`

## string_xrefs

- `0x18001c864`: `BCryptCreateHash`
- `0x18001c775`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c7f5`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c83b`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c884`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c902`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c93b`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c96f`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c9af`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c81e`: `BCryptOpenAlgorithmProvider`

## pseudocode

```c
__int64 __fastcall CreateBufferChecksum(
        const unsigned __int16 *a1,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  UCHAR *v8; // rsi
  unsigned int *v9; // rdi
  unsigned int Property; // ebx
  UCHAR *v11; // rax
  ULONG v12; // eax
  const char *v14; // r9
  char v15; // al
  const char *v16; // rdx
  bool v17; // zf
  char v18; // al
  char v19; // al
  char v20; // al
  char v21; // al
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  ULONG *pcbResult; // [rsp+20h] [rbp-68h]
  const char *dwFlags; // [rsp+28h] [rbp-60h]
  ULONG v27; // [rsp+40h] [rbp-48h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-38h] BYREF
  ULONG pbOutput; // [rsp+90h] [rbp+8h] BYREF
  int v31; // [rsp+94h] [rbp+Ch]

  v31 = HIDWORD(a1);
  hObject = 0;
  v8 = 0;
  phHash = 0;
  pbOutput = 0;
  v27 = 0;
  if ( a2 && a4 && (v9 = a5) != 0 )
  {
    *a4 = 0;
    *v9 = 0;
    Property = BCryptOpenAlgorithmProvider(&hObject, L"SHA256", 0, 0);
    if ( Property )
    {
      v14 = "";
      while ( 1 )
      {
        v18 = *(v14 - 1);
        v16 = v14--;
        v17 = v18 == 92;
        if ( v18 == 92 )
          break;
        if ( v14 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
        {
          v17 = v18 == 92;
          break;
        }
      }
      dwFlags = "BCryptOpenAlgorithmProvider";
      LODWORD(pcbResult) = 566;
    }
    else
    {
      Property = BCryptGetProperty(hObject, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &v27, 0);
      if ( Property )
      {
        v14 = "";
        while ( 1 )
        {
          v20 = *(v14 - 1);
          v16 = v14--;
          v17 = v20 == 92;
          if ( v20 == 92 )
            break;
          if ( v14 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
          {
            v17 = v20 == 92;
            break;
          }
        }
        dwFlags = "BCryptGetProperty";
        LODWORD(pcbResult) = 576;
      }
      else if ( v27 == 4 )
      {
        if ( g_pLsaFunctionTable )
          v11 = (UCHAR *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(pbOutput);
        else
          v11 = (UCHAR *)LocalAlloc(0x40u, pbOutput);
        v8 = v11;
        if ( !v11 )
        {
          Property = -1073741801;
          v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
          LODWORD(pcbResult) = 588;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v22, pcbResult, "AllocateMemory", &Class);
          goto LABEL_14;
        }
        Property = BCryptCreateHash(hObject, &phHash, 0, 0, 0, 0, 0);
        if ( !Property )
        {
          Property = BCryptHashData(phHash, a2, a3, 0);
          if ( Property )
          {
            v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
            LODWORD(pcbResult) = 607;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v23, pcbResult, "BCryptHashData", &Class);
          }
          else
          {
            Property = BCryptFinishHash(phHash, v8, pbOutput, 0);
            if ( Property )
            {
              v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
              LODWORD(pcbResult) = 615;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v24, pcbResult, "BCryptFinishHash", &Class);
            }
            else
            {
              v12 = pbOutput;
              *a4 = v8;
              v8 = 0;
              *v9 = v12;
            }
          }
          goto LABEL_14;
        }
        v14 = "";
        while ( 1 )
        {
          v19 = *(v14 - 1);
          v16 = v14--;
          v17 = v19 == 92;
          if ( v19 == 92 )
            break;
          if ( v14 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
          {
            v17 = v19 == 92;
            break;
          }
        }
        dwFlags = "BCryptCreateHash";
        LODWORD(pcbResult) = 599;
      }
      else
      {
        Property = -1073741595;
        v14 = "";
        while ( 1 )
        {
          v15 = *(v14 - 1);
          v16 = v14--;
          v17 = v15 == 92;
          if ( v15 == 92 )
            break;
          if ( v14 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
          {
            v17 = v15 == 92;
            break;
          }
        }
        dwFlags = "BCryptGetProperty";
        LODWORD(pcbResult) = 581;
      }
    }
  }
  else
  {
    Property = -1073741811;
    v14 = "";
    while ( 1 )
    {
      v21 = *(v14 - 1);
      v16 = v14--;
      v17 = v21 == 92;
      if ( v21 == 92 )
        break;
      if ( v14 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
      {
        v17 = v21 == 92;
        break;
      }
    }
    dwFlags = "InvalidArgs";
    LODWORD(pcbResult) = 554;
  }
  if ( v17 )
    v14 = v16;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v14, pcbResult, dwFlags, &Class);
LABEL_14:
  if ( hObject )
    BCryptCloseAlgorithmProvider(hObject, 0);
  if ( v8 )
    FreeMemory(v8);
  if ( phHash )
    BCryptDestroyHash(phHash);
  return Property;
}

```

## disassembly

```asm
0x18001c590  mov     rax, rsp
0x18001c593  mov     [rax+8], rcx
0x18001c597  push    rbx
0x18001c598  sub     rsp, 80h
0x18001c59f  mov     [rax+10h], rbp
0x18001c5a3  mov     rbp, rdx
0x18001c5a6  mov     [rax+18h], rsi
0x18001c5aa  mov     [rax-10h], rdi
0x18001c5ae  mov     [rax-18h], r12
0x18001c5b2  xor     r12d, r12d
0x18001c5b5  mov     [rax-20h], r14
0x18001c5b9  mov     r14, r9
0x18001c5bc  mov     [rax-28h], r15
0x18001c5c0  mov     r15d, r8d
0x18001c5c3  mov     [rax-40h], r12
0x18001c5c7  mov     esi, r12d
0x18001c5ca  mov     [rax-38h], r12
0x18001c5ce  mov     [rax+8], r12d
0x18001c5d2  mov     [rax-48h], r12d
0x18001c5d6  test    rdx, rdx
0x18001c5d9  jz      loc_18001C9A3
0x18001c5df  test    r9, r9
0x18001c5e2  jz      loc_18001C9A3
0x18001c5e8  mov     rdi, [rsp+88h+arg_20]
0x18001c5f0  test    rdi, rdi
0x18001c5f3  jz      loc_18001C9A3
0x18001c5f9  mov     [r9], r12
0x18001c5fc  lea     rdx, pszAlgId; "SHA256"
0x18001c603  xor     r9d, r9d; dwFlags
0x18001c606  mov     [rdi], r12d
0x18001c609  xor     r8d, r8d; pszImplementation
0x18001c60c  lea     rcx, [rax-40h]; phAlgorithm
0x18001c610  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001c616  mov     ebx, eax
0x18001c618  test    eax, eax
0x18001c61a  jnz     loc_18001C7EE
0x18001c620  mov     rcx, [rsp+88h+hObject]; hObject
0x18001c625  lea     rax, [rsp+88h+var_48]
0x18001c62a  mov     [rsp+88h+dwFlags], r12d; dwFlags
0x18001c62f  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x18001c637  mov     r9d, 4; cbOutput
0x18001c63d  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18001c642  lea     rdx, pszProperty; "HashDigestLength"
0x18001c649  call    cs:__imp_BCryptGetProperty
0x18001c64f  mov     ebx, eax
0x18001c651  test    eax, eax
0x18001c653  jnz     loc_18001C87D
0x18001c659  cmp     [rsp+88h+var_48], 4
0x18001c65e  jnz     loc_18001C769
0x18001c664  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001c66b  mov     ecx, [rsp+88h+pbOutput]
0x18001c672  test    rax, rax
0x18001c675  jz      loc_18001C8EF
0x18001c67b  mov     rax, [rax+28h]
0x18001c67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c684  mov     rsi, rax
0x18001c687  test    rax, rax
0x18001c68a  jz      loc_18001C902
0x18001c690  mov     rcx, [rsp+88h+hObject]; hAlgorithm
0x18001c695  lea     rdx, [rsp+88h+phHash]; phHash
0x18001c69a  mov     [rsp+88h+var_58], r12d; dwFlags
0x18001c69f  xor     r9d, r9d; cbHashObject
0x18001c6a2  mov     [rsp+88h+dwFlags], r12d; cbSecret
0x18001c6a7  xor     r8d, r8d; pbHashObject
0x18001c6aa  mov     [rsp+88h+pcbResult], r12; pbSecret
0x18001c6af  call    cs:__imp_BCryptCreateHash
0x18001c6b5  mov     ebx, eax
0x18001c6b7  test    eax, eax
0x18001c6b9  jnz     loc_18001C834
0x18001c6bf  mov     rcx, [rsp+88h+phHash]; hHash
0x18001c6c4  xor     r9d, r9d; dwFlags
0x18001c6c7  mov     r8d, r15d; cbInput
0x18001c6ca  mov     rdx, rbp; pbInput
0x18001c6cd  call    cs:__imp_BCryptHashData
0x18001c6d3  mov     ebx, eax
0x18001c6d5  test    eax, eax
0x18001c6d7  jnz     loc_18001C93B
0x18001c6dd  mov     r8d, [rsp+88h+pbOutput]; cbOutput
0x18001c6e5  xor     r9d, r9d; dwFlags
0x18001c6e8  mov     rcx, [rsp+88h+phHash]; hHash
0x18001c6ed  mov     rdx, rsi; pbOutput
0x18001c6f0  call    cs:__imp_BCryptFinishHash
0x18001c6f6  mov     ebx, eax
0x18001c6f8  test    eax, eax
0x18001c6fa  jnz     loc_18001C96F
0x18001c700  mov     eax, [rsp+88h+pbOutput]
0x18001c707  mov     [r14], rsi
0x18001c70a  mov     rsi, r12
0x18001c70d  mov     [rdi], eax
0x18001c70f  mov     rcx, [rsp+88h+hObject]; hAlgorithm
0x18001c714  mov     r15, [rsp+88h+var_28]
0x18001c719  mov     r14, [rsp+88h+var_20]
0x18001c71e  mov     r12, [rsp+88h+var_18]
0x18001c723  mov     rdi, [rsp+88h+var_10]
0x18001c728  mov     rbp, [rsp+88h+arg_8]
0x18001c730  test    rcx, rcx
0x18001c733  jz      short loc_18001C73D
0x18001c735  xor     edx, edx; dwFlags
0x18001c737  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001c73d  test    rsi, rsi
0x18001c740  jnz     loc_18001C9BB
0x18001c746  mov     rcx, [rsp+88h+phHash]; hHash
0x18001c74b  mov     rsi, [rsp+88h+arg_10]
0x18001c753  test    rcx, rcx
0x18001c756  jz      short loc_18001C75E
0x18001c758  call    cs:__imp_BCryptDestroyHash
0x18001c75e  mov     eax, ebx
0x18001c760  add     rsp, 80h
0x18001c767  pop     rbx
0x18001c768  retn
0x18001c769  mov     ebx, 0C00000E5h
0x18001c76e  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18001c775  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c77c  movzx   eax, byte ptr [r9-1]
0x18001c781  mov     rdx, r9
0x18001c784  dec     r9
0x18001c787  cmp     al, 5Ch ; '\'
0x18001c789  jz      short loc_18001C792
0x18001c78b  cmp     r9, rcx
0x18001c78e  ja      short loc_18001C77C
0x18001c790  cmp     al, 5Ch ; '\'
0x18001c792  lea     rax, Class
0x18001c799  mov     qword ptr [rsp+88h+var_58], rax
0x18001c79e  lea     rax, aBcryptgetprope; "BCryptGetProperty"
0x18001c7a5  mov     qword ptr [rsp+88h+dwFlags], rax
0x18001c7aa  mov     dword ptr [rsp+88h+pcbResult], 245h
0x18001c7b2  jmp     short loc_18001C7D4
0x18001c7b4  lea     rax, Class
0x18001c7bb  mov     qword ptr [rsp+88h+var_58], rax
0x18001c7c0  lea     rax, aInvalidargs; "InvalidArgs"
0x18001c7c7  mov     qword ptr [rsp+88h+dwFlags], rax
0x18001c7cc  mov     dword ptr [rsp+88h+pcbResult], 22Ah
0x18001c7d4  cmovz   r9, rdx
0x18001c7d8  mov     r8d, ebx
0x18001c7db  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001c7e2  xor     ecx, ecx
0x18001c7e4  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001c7e9  jmp     loc_18001C70F
0x18001c7ee  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18001c7f5  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c7fc  movzx   eax, byte ptr [r9-1]
0x18001c801  mov     rdx, r9
0x18001c804  dec     r9
0x18001c807  cmp     al, 5Ch ; '\'
0x18001c809  jz      short loc_18001C812
0x18001c80b  cmp     r9, rcx
0x18001c80e  ja      short loc_18001C7FC
0x18001c810  cmp     al, 5Ch ; '\'
0x18001c812  lea     rax, Class
0x18001c819  mov     qword ptr [rsp+88h+var_58], rax
0x18001c81e  lea     rax, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x18001c825  mov     qword ptr [rsp+88h+dwFlags], rax
0x18001c82a  mov     dword ptr [rsp+88h+pcbResult], 236h
0x18001c832  jmp     short loc_18001C7D4
0x18001c834  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18001c83b  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c842  movzx   eax, byte ptr [r9-1]
0x18001c847  mov     rdx, r9
0x18001c84a  dec     r9
0x18001c84d  cmp     al, 5Ch ; '\'
0x18001c84f  jz      short loc_18001C858
0x18001c851  cmp     r9, rcx
0x18001c854  ja      short loc_18001C842
0x18001c856  cmp     al, 5Ch ; '\'
0x18001c858  lea     rax, Class
0x18001c85f  mov     qword ptr [rsp+88h+var_58], rax
0x18001c864  lea     rax, aBcryptcreateha; "BCryptCreateHash"
0x18001c86b  mov     qword ptr [rsp+88h+dwFlags], rax
0x18001c870  mov     dword ptr [rsp+88h+pcbResult], 257h
0x18001c878  jmp     loc_18001C7D4
0x18001c87d  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18001c884  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c88b  movzx   eax, byte ptr [r9-1]
0x18001c890  mov     rdx, r9
0x18001c893  dec     r9
0x18001c896  cmp     al, 5Ch ; '\'
0x18001c898  jz      short loc_18001C8A1
0x18001c89a  cmp     r9, rcx
0x18001c89d  ja      short loc_18001C88B
0x18001c89f  cmp     al, 5Ch ; '\'
0x18001c8a1  lea     rax, Class
0x18001c8a8  mov     qword ptr [rsp+88h+var_58], rax
0x18001c8ad  lea     rax, aBcryptgetprope; "BCryptGetProperty"
0x18001c8b4  mov     qword ptr [rsp+88h+dwFlags], rax
0x18001c8b9  mov     dword ptr [rsp+88h+pcbResult], 240h
0x18001c8c1  jmp     loc_18001C7D4
0x18001c8d0  movzx   eax, byte ptr [r9-1]
0x18001c8d5  mov     rdx, r9
0x18001c8d8  dec     r9
0x18001c8db  cmp     al, 5Ch ; '\'
0x18001c8dd  jz      loc_18001C7B4
0x18001c8e3  cmp     r9, rcx
0x18001c8e6  ja      short loc_18001C8D0
0x18001c8e8  cmp     al, 5Ch ; '\'
0x18001c8ea  jmp     loc_18001C7B4
0x18001c8ef  mov     rdx, rcx; uBytes
0x18001c8f2  mov     ecx, 40h ; '@'; uFlags
0x18001c8f7  call    cs:__imp_LocalAlloc
0x18001c8fd  jmp     loc_18001C684
0x18001c902  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c909  mov     ebx, 0C0000017h
0x18001c90e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c913  mov     r9, rax
0x18001c916  lea     rax, Class
0x18001c91d  mov     qword ptr [rsp+88h+var_58], rax
0x18001c922  lea     rax, aAllocatememory; "AllocateMemory"
0x18001c929  mov     qword ptr [rsp+88h+dwFlags], rax
0x18001c92e  mov     dword ptr [rsp+88h+pcbResult], 24Ch
0x18001c936  jmp     loc_18001C7D8
0x18001c93b  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c942  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c947  mov     r9, rax
0x18001c94a  lea     rax, Class
0x18001c951  mov     qword ptr [rsp+88h+var_58], rax
0x18001c956  lea     rax, aBcrypthashdata; "BCryptHashData"
0x18001c95d  mov     qword ptr [rsp+88h+dwFlags], rax
0x18001c962  mov     dword ptr [rsp+88h+pcbResult], 25Fh
0x18001c96a  jmp     loc_18001C7D8
0x18001c96f  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c976  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c97b  mov     r9, rax
0x18001c97e  lea     rax, Class
0x18001c985  mov     qword ptr [rsp+88h+var_58], rax
0x18001c98a  lea     rax, aBcryptfinishha; "BCryptFinishHash"
0x18001c991  mov     qword ptr [rsp+88h+dwFlags], rax
0x18001c996  mov     dword ptr [rsp+88h+pcbResult], 267h
0x18001c99e  jmp     loc_18001C7D8
0x18001c9a3  mov     ebx, 0C000000Dh
0x18001c9a8  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x18001c9af  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c9b6  jmp     loc_18001C8D0
0x18001c9bb  mov     rcx, rsi; void *
0x18001c9be  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x18001c9c3  jmp     loc_18001C746
```
