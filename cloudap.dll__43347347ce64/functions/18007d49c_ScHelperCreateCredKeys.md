# ScHelperCreateCredKeys

- ea: `0x18007d49c`
- end: `0x18007db02`
- name: `ScHelperCreateCredKeys`
- size: `1638`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, DWORD dwKeySpec@<edx>, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007db08`
- `0x18007de50`

## callees

- `0x18000a810`
- `0x180042410`
- `0x18007c7cc`
- `0x18007c9a0`
- `0x18007d1a8`
- `0x18007d49c`
- `0x18007e624`
- `0x18007f990`
- `0x180081010`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18007dab3`
- `bcrypt!BCryptDestroyHash` at `0x18007dab3`
- `bcrypt!BCryptFinishHash` at `0x18007d801`
- `bcrypt!BCryptFinishHash` at `0x18007d801`
- `bcrypt!BCryptCreateHash` at `0x18007d7c0`
- `bcrypt!BCryptCreateHash` at `0x18007d7c0`
- `bcrypt!BCryptHashData` at `0x18007d7e2`
- `bcrypt!BCryptHashData` at `0x18007d7e2`
- `ncrypt!NCryptSignHash` at `0x18007d86a`
- `ncrypt!NCryptSignHash` at `0x18007d93a`
- `ncrypt!NCryptSignHash` at `0x18007d86a`
- `ncrypt!NCryptSignHash` at `0x18007d93a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18007da78`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18007da87`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18007da78`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18007da87`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007d5eb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007d9e9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007da09`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007d5eb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007d9e9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007da09`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x18007da2f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x18007da55`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x18007da2f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x18007da55`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007d5d0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007d9cd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007d5d0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007d9cd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x18007d610`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x18007d6cb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x18007d610`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSignHashW` at `0x18007d6cb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18007d58b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18007d58b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18007d564`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18007d564`

## pseudocode

```c
__int64 __fastcall ScHelperCreateCredKeys(
        void *a1,
        DWORD dwKeySpec,
        __int64 a3,
        UCHAR *a4,
        int a5,
        HCRYPTKEY *a6,
        HCRYPTKEY *a7,
        HCRYPTPROV *a8)
{
  UCHAR *p_pcbResult; // r14
  NTSTATUS IsNcryptRsaKey; // ebx
  BYTE *p_hBaseData; // rdi
  HCRYPTPROV v14; // rax
  unsigned __int64 v15; // rbx
  __int64 v16; // rsi
  unsigned __int64 v17; // rsi
  void *v18; // rsp
  void *v19; // rsp
  BYTE *v20; // rax
  void *HelperSha1AlgHandle; // r15
  unsigned __int64 v22; // rbx
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  UCHAR *v27; // rax
  unsigned __int64 v28; // rbx
  __int64 v29; // rcx
  unsigned __int64 v30; // rcx
  void *v31; // rsp
  void *v32; // rsp
  BYTE *v33; // rax
  HCRYPTPROV *v34; // rbx
  _BYTE v36[32]; // [rsp+0h] [rbp-40h] BYREF
  DWORD pcbResult; // [rsp+40h] [rbp+0h] BYREF
  HCRYPTHASH hBaseData; // [rsp+48h] [rbp+8h] BYREF
  int v39; // [rsp+50h] [rbp+10h] BYREF
  HCRYPTHASH phHash; // [rsp+58h] [rbp+18h] BYREF
  HCRYPTPROV phProv; // [rsp+60h] [rbp+20h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+68h] [rbp+28h] BYREF
  const WCHAR *pPaddingInfo; // [rsp+70h] [rbp+30h] BYREF
  PUCHAR pbInput; // [rsp+78h] [rbp+38h]
  __int64 v45; // [rsp+80h] [rbp+40h]
  HCRYPTPROV *v46; // [rsp+88h] [rbp+48h]
  HCRYPTKEY *phKey; // [rsp+90h] [rbp+50h]
  HCRYPTKEY *v48; // [rsp+98h] [rbp+58h]
  UCHAR pbOutput[24]; // [rsp+A8h] [rbp+68h] BYREF

  p_pcbResult = 0;
  pbInput = a4;
  *a8 = 0;
  v45 = a3;
  v48 = a6;
  phKey = a7;
  v46 = a8;
  phHash = 0;
  pcbResult = 0;
  hBaseData = 0;
  hHash = 0;
  if ( !a1 )
    return (unsigned int)-1073741023;
  if ( a4 && a6 && a7 )
  {
    p_hBaseData = 0;
    phProv = 0;
    if ( !g_hProvHelper )
    {
      if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Strong Cryptographic Provider", 1u, 0xF0000000) )
      {
        v14 = phProv;
        goto LABEL_12;
      }
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hProvHelper, phProv, 0) )
        CryptReleaseContext(phProv, 0);
    }
    v14 = g_hProvHelper;
LABEL_12:
    *a8 = v14;
    if ( !v14 )
    {
LABEL_13:
      IsNcryptRsaKey = -1073741023;
      goto LABEL_78;
    }
    if ( dwKeySpec - 1 > 0xFFFFFFFD )
    {
      pPaddingInfo = 0;
      v39 = 0;
      HelperSha1AlgHandle = I_ScHelperGetHelperSha1AlgHandle();
      if ( !HelperSha1AlgHandle )
      {
        IsNcryptRsaKey = -1073741670;
        goto LABEL_78;
      }
      v22 = g_cbHashObjectLength;
      if ( !g_cbHashObjectLength
        || g_cbHashObjectLength > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)g_cbHashObjectLength + g_ulAdditionalProbeSize + 8 < g_cbHashObjectLength
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_94;
      }
      v23 = v22 + 23;
      if ( v22 + 23 <= v22 + 8 )
        v23 = 0xFFFFFFFFFFFFFF0LL;
      v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
      v25 = alloca(v24);
      v26 = alloca(v24);
      p_pcbResult = (UCHAR *)&pcbResult;
      if ( v36 == (_BYTE *)-64LL || (pcbResult = 1801679955, (p_pcbResult = (UCHAR *)&hBaseData) == 0) )
      {
LABEL_94:
        if ( v22 + 8 >= v22 )
        {
          v27 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcbResult = v27;
          if ( v27 )
          {
            *(_DWORD *)v27 = 1885431112;
            p_pcbResult = v27 + 8;
          }
        }
      }
      if ( p_pcbResult )
      {
        IsNcryptRsaKey = BCryptCreateHash(HelperSha1AlgHandle, &hHash, p_pcbResult, g_cbHashObjectLength, 0, 0, 0);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_78;
        IsNcryptRsaKey = BCryptHashData(hHash, pbInput, 0x20u, 0);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_78;
        IsNcryptRsaKey = BCryptFinishHash(hHash, pbOutput, 0x14u, 0);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_78;
        IsNcryptRsaKey = ScHelperIsNcryptRsaKey(1, a1, &v39);
        if ( IsNcryptRsaKey < 0 )
          goto LABEL_78;
        if ( !v39 )
        {
          IsNcryptRsaKey = -1073741637;
          goto LABEL_78;
        }
        pPaddingInfo = L"SHA1";
        IsNcryptRsaKey = NCryptSignHash((NCRYPT_KEY_HANDLE)a1, &pPaddingInfo, pbOutput, 0x14u, 0, 0, &pcbResult, 2u);
        if ( IsNcryptRsaKey < 0 )
        {
LABEL_78:
          if ( phHash )
            CryptDestroyHash(phHash);
          if ( hBaseData )
            CryptDestroyHash(hBaseData);
          if ( p_hBaseData && *((_DWORD *)p_hBaseData - 2) == 1885431112 )
            ((void (*)(void))g_pfnFree)();
          if ( hHash )
            BCryptDestroyHash(hHash);
          if ( p_pcbResult )
          {
            if ( *((_DWORD *)p_pcbResult - 2) == 1885431112 )
              ((void (*)(void))g_pfnFree)();
          }
          return (unsigned int)IsNcryptRsaKey;
        }
        v28 = pcbResult;
        if ( !pcbResult
          || pcbResult > (unsigned __int64)g_ulMaxStackAllocSize
          || (unsigned __int64)pcbResult + g_ulAdditionalProbeSize + 8 < pcbResult
          || !(unsigned int)VerifyStackAvailable() )
        {
          goto LABEL_95;
        }
        v29 = v28 + 23;
        if ( v28 + 23 <= v28 + 8 )
          v29 = 0xFFFFFFFFFFFFFF0LL;
        v30 = v29 & 0xFFFFFFFFFFFFFFF0uLL;
        v31 = alloca(v30);
        v32 = alloca(v30);
        p_hBaseData = (BYTE *)&pcbResult;
        if ( v36 == (_BYTE *)-64LL || (pcbResult = 1801679955, (p_hBaseData = (BYTE *)&hBaseData) == 0) )
        {
LABEL_95:
          if ( v28 + 8 >= v28 )
          {
            v33 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
            p_hBaseData = v33;
            if ( v33 )
            {
              *(_DWORD *)v33 = 1885431112;
              p_hBaseData = v33 + 8;
            }
          }
        }
        if ( p_hBaseData )
        {
          IsNcryptRsaKey = NCryptSignHash(
                             (NCRYPT_KEY_HANDLE)a1,
                             &pPaddingInfo,
                             pbOutput,
                             0x14u,
                             p_hBaseData,
                             pcbResult,
                             &pcbResult,
                             2u);
          if ( IsNcryptRsaKey < 0 )
            goto LABEL_78;
          goto LABEL_65;
        }
      }
    }
    else
    {
      if ( !CryptCreateHash((HCRYPTPROV)a1, 0x8004u, 0, 0, &phHash) )
        goto LABEL_13;
      if ( !CryptHashData(phHash, a4, 0x20u, 0) )
        goto LABEL_13;
      CryptSignHashW(phHash, dwKeySpec, 0, 0, 0, &pcbResult);
      if ( !pcbResult )
        goto LABEL_13;
      v15 = pcbResult;
      if ( pcbResult > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)pcbResult + g_ulAdditionalProbeSize + 8 < pcbResult
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_96;
      }
      v16 = v15 + 23;
      if ( v15 + 23 <= v15 + 8 )
        v16 = 0xFFFFFFFFFFFFFF0LL;
      v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
      v18 = alloca(v17);
      v19 = alloca(v17);
      p_hBaseData = (BYTE *)&pcbResult;
      if ( v36 == (_BYTE *)-64LL || (pcbResult = 1801679955, (p_hBaseData = (BYTE *)&hBaseData) == 0) )
      {
LABEL_96:
        if ( v15 + 8 >= v15 )
        {
          v20 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
          p_hBaseData = v20;
          if ( v20 )
          {
            *(_DWORD *)v20 = 1885431112;
            p_hBaseData = v20 + 8;
          }
        }
      }
      if ( p_hBaseData )
      {
        if ( !CryptSignHashW(phHash, dwKeySpec, 0, 0, p_hBaseData, &pcbResult) )
          goto LABEL_13;
LABEL_65:
        if ( a5 )
        {
          if ( dwKeySpec - 1 <= 0xFFFFFFFD )
            ReverseBytes(p_hBaseData, pcbResult);
          if ( (unsigned int)ScHelperVerifyMessage(v45, L"SHA1", pbInput, 32, p_hBaseData, pcbResult) )
            goto LABEL_13;
        }
        else if ( ((dwKeySpec + 1) & 0xFFFFFFFE) != 0 )
        {
LABEL_72:
          v34 = v46;
          if ( CryptCreateHash(*v46, 0x8004u, 0, 0, &hBaseData)
            && CryptHashData(hBaseData, p_hBaseData, pcbResult, 0)
            && CryptHashData(hBaseData, pbInput + 32, 0x20u, 0)
            && CryptDeriveKey(*v34, 0x6801u, hBaseData, 0, phKey) )
          {
            IsNcryptRsaKey = !CryptDeriveKey(*v34, 0x6602u, hBaseData, 0, v48) ? 0xC0000321 : 0;
            goto LABEL_78;
          }
          goto LABEL_13;
        }
        ReverseBytes(p_hBaseData, pcbResult);
        goto LABEL_72;
      }
    }
    IsNcryptRsaKey = -1073741801;
    goto LABEL_78;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x18007d49c  push    rbp
0x18007d49e  push    rbx
0x18007d49f  push    rsi
0x18007d4a0  push    rdi
0x18007d4a1  push    r12
0x18007d4a3  push    r13
0x18007d4a5  push    r14
0x18007d4a7  push    r15
0x18007d4a9  sub     rsp, 0D8h
0x18007d4b0  lea     rbp, [rsp+40h]
0x18007d4b5  mov     rax, cs:__security_cookie
0x18007d4bc  xor     rax, rbp
0x18007d4bf  mov     [rbp+0D0h+var_50], rax
0x18007d4c6  mov     rbx, [rbp+0D0h+arg_38]
0x18007d4cd  xor     r14d, r14d
0x18007d4d0  mov     rax, [rbp+0D0h+arg_30]
0x18007d4d7  mov     r12, rcx
0x18007d4da  mov     rcx, [rbp+0D0h+arg_28]
0x18007d4e1  mov     rsi, r9
0x18007d4e4  mov     [rbp+0D0h+pbInput], r9
0x18007d4e8  mov     r13d, edx
0x18007d4eb  mov     [rbx], r14
0x18007d4ee  mov     [rbp+0D0h+var_90], r8
0x18007d4f2  mov     [rbp+0D0h+var_78], rcx
0x18007d4f6  mov     [rbp+0D0h+phKey], rax
0x18007d4fa  mov     [rbp+0D0h+var_88], rbx
0x18007d4fe  mov     [rbp+0D0h+phHash], r14
0x18007d502  mov     [rbp+0D0h+pcbResult], r14d
0x18007d506  mov     [rbp+0D0h+hBaseData], r14
0x18007d50a  mov     [rbp+0D0h+hHash], r14
0x18007d50e  test    r12, r12
0x18007d511  jnz     short loc_18007D51D
0x18007d513  mov     ebx, 0C0000321h
0x18007d518  jmp     loc_18007DAD6
0x18007d51d  test    rsi, rsi
0x18007d520  jz      loc_18007DADA
0x18007d526  test    rcx, rcx
0x18007d529  jz      loc_18007DADA
0x18007d52f  test    rax, rax
0x18007d532  jz      loc_18007DADA
0x18007d538  mov     rax, cs:?g_hProvHelper@@3_KC; unsigned __int64 volatile g_hProvHelper
0x18007d53f  mov     rdi, r14
0x18007d542  mov     [rbp+0D0h+phProv], r14
0x18007d546  test    rax, rax
0x18007d549  jnz     short loc_18007D591
0x18007d54b  lea     r9d, [rax+1]; dwProvType
0x18007d54f  mov     [rsp+110h+dwFlags], 0F0000000h; dwFlags
0x18007d557  lea     r8, szProvider; "Microsoft Strong Cryptographic Provider"
0x18007d55e  xor     edx, edx; szContainer
0x18007d560  lea     rcx, [rbp+0D0h+phProv]; phProv
0x18007d564  call    cs:__imp_CryptAcquireContextW
0x18007d56a  test    eax, eax
0x18007d56c  jnz     short loc_18007D574
0x18007d56e  mov     rax, [rbp+0D0h+phProv]
0x18007d572  jmp     short loc_18007D598
0x18007d574  mov     rcx, [rbp+0D0h+phProv]
0x18007d578  xor     eax, eax
0x18007d57a  lock cmpxchg cs:?g_hProvHelper@@3_KC, rcx; unsigned __int64 volatile g_hProvHelper
0x18007d583  jz      short loc_18007D591
0x18007d585  mov     rcx, [rbp+0D0h+phProv]; hProv
0x18007d589  xor     edx, edx; dwFlags
0x18007d58b  call    cs:__imp_CryptReleaseContext
0x18007d591  mov     rax, cs:?g_hProvHelper@@3_KC; unsigned __int64 volatile g_hProvHelper
0x18007d598  mov     [rbx], rax
0x18007d59b  xor     ebx, ebx
0x18007d59d  test    rax, rax
0x18007d5a0  jnz     short loc_18007D5AC
0x18007d5a2  mov     ebx, 0C0000321h
0x18007d5a7  jmp     loc_18007DA6F
0x18007d5ac  lea     eax, [r13-1]
0x18007d5b0  cmp     eax, 0FFFFFFFDh
0x18007d5b3  ja      loc_18007D6DE
0x18007d5b9  lea     rax, [rbp+0D0h+phHash]
0x18007d5bd  xor     r9d, r9d; dwFlags
0x18007d5c0  xor     r8d, r8d; hKey
0x18007d5c3  mov     qword ptr [rsp+110h+dwFlags], rax; phHash
0x18007d5c8  mov     edx, 8004h; Algid
0x18007d5cd  mov     rcx, r12; hProv
0x18007d5d0  call    cs:__imp_CryptCreateHash
0x18007d5d6  test    eax, eax
0x18007d5d8  jz      short loc_18007D5A2
0x18007d5da  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18007d5de  xor     r9d, r9d; dwFlags
0x18007d5e1  mov     rdx, rsi; pbData
0x18007d5e4  lea     r15d, [r9+20h]
0x18007d5e8  mov     r8d, r15d; dwDataLen
0x18007d5eb  call    cs:__imp_CryptHashData
0x18007d5f1  test    eax, eax
0x18007d5f3  jz      short loc_18007D5A2
0x18007d5f5  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18007d5f9  lea     rax, [rbp+0D0h+pcbResult]
0x18007d5fd  mov     [rsp+110h+pdwSigLen], rax; pdwSigLen
0x18007d602  xor     r9d, r9d; dwFlags
0x18007d605  xor     r8d, r8d; szDescription
0x18007d608  mov     qword ptr [rsp+110h+dwFlags], rbx; pbSignature
0x18007d60d  mov     edx, r13d; dwKeySpec
0x18007d610  call    cs:__imp_CryptSignHashW
0x18007d616  mov     eax, [rbp+0D0h+pcbResult]
0x18007d619  test    eax, eax
0x18007d61b  jz      short loc_18007D5A2
0x18007d61d  cmp     rax, cs:g_ulMaxStackAllocSize
0x18007d624  mov     ebx, eax
0x18007d626  ja      short loc_18007D680
0x18007d628  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007d62f  add     rcx, 8
0x18007d633  add     rcx, rax
0x18007d636  cmp     rcx, rax
0x18007d639  jb      short loc_18007D680
0x18007d63b  call    VerifyStackAvailable
0x18007d640  test    eax, eax
0x18007d642  jz      short loc_18007D680
0x18007d644  lea     rax, [rbx+8]
0x18007d648  lea     rsi, [rax+0Fh]
0x18007d64c  cmp     rsi, rax
0x18007d64f  ja      short loc_18007D65B
0x18007d651  mov     rsi, 0FFFFFFFFFFFFFF0h
0x18007d65b  and     rsi, 0FFFFFFFFFFFFFFF0h
0x18007d65f  mov     rax, rsi
0x18007d662  call    _alloca_probe
0x18007d667  sub     rsp, rsi
0x18007d66a  lea     rdi, [rsp+110h+pcbResult]
0x18007d66f  test    rdi, rdi
0x18007d672  jz      short loc_18007D680
0x18007d674  mov     dword ptr [rdi], 6B637453h
0x18007d67a  add     rdi, 8
0x18007d67e  jnz     short loc_18007D6A7
0x18007d680  lea     rcx, [rbx+8]
0x18007d684  cmp     rcx, rbx
0x18007d687  jb      short loc_18007D6A7
0x18007d689  mov     rax, cs:g_pfnAllocate
0x18007d690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d695  mov     rdi, rax
0x18007d698  test    rax, rax
0x18007d69b  jz      short loc_18007D6A7
0x18007d69d  mov     dword ptr [rax], 70616548h
0x18007d6a3  add     rdi, 8
0x18007d6a7  test    rdi, rdi
0x18007d6aa  jz      loc_18007D798
0x18007d6b0  mov     rcx, [rbp+0D0h+phHash]; hHash
0x18007d6b4  lea     rax, [rbp+0D0h+pcbResult]
0x18007d6b8  mov     [rsp+110h+pdwSigLen], rax; pdwSigLen
0x18007d6bd  xor     r9d, r9d; dwFlags
0x18007d6c0  xor     r8d, r8d; szDescription
0x18007d6c3  mov     qword ptr [rsp+110h+dwFlags], rdi; pbSignature
0x18007d6c8  mov     edx, r13d; dwKeySpec
0x18007d6cb  call    cs:__imp_CryptSignHashW
0x18007d6d1  test    eax, eax
0x18007d6d3  jnz     loc_18007D94A
0x18007d6d9  jmp     loc_18007D5A2
0x18007d6de  mov     [rbp+0D0h+pPaddingInfo], rbx
0x18007d6e2  mov     [rbp+0D0h+var_C0], ebx
0x18007d6e5  call    ?I_ScHelperGetHelperSha1AlgHandle@@YAPEAXXZ; I_ScHelperGetHelperSha1AlgHandle(void)
0x18007d6ea  mov     r15, rax
0x18007d6ed  test    rax, rax
0x18007d6f0  jnz     short loc_18007D6FC
0x18007d6f2  mov     ebx, 0C000009Ah
0x18007d6f7  jmp     loc_18007DA6F
0x18007d6fc  mov     ebx, cs:?g_cbHashObjectLength@@3KA; ulong g_cbHashObjectLength
0x18007d702  mov     rsi, 0FFFFFFFFFFFFFF0h
0x18007d70c  test    rbx, rbx
0x18007d70f  jz      short loc_18007D76C
0x18007d711  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18007d718  ja      short loc_18007D76C
0x18007d71a  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007d721  add     rcx, 8
0x18007d725  add     rcx, rbx
0x18007d728  cmp     rcx, rbx
0x18007d72b  jb      short loc_18007D76C
0x18007d72d  call    VerifyStackAvailable
0x18007d732  test    eax, eax
0x18007d734  jz      short loc_18007D76C
0x18007d736  lea     rax, [rbx+8]
0x18007d73a  lea     rcx, [rax+0Fh]
0x18007d73e  cmp     rcx, rax
0x18007d741  ja      short loc_18007D746
0x18007d743  mov     rcx, rsi
0x18007d746  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18007d74a  mov     rax, rcx
0x18007d74d  call    _alloca_probe
0x18007d752  sub     rsp, rcx
0x18007d755  lea     r14, [rsp+110h+pcbResult]
0x18007d75a  test    r14, r14
0x18007d75d  jz      short loc_18007D76C
0x18007d75f  mov     dword ptr [r14], 6B637453h
0x18007d766  add     r14, 8
0x18007d76a  jnz     short loc_18007D793
0x18007d76c  lea     rcx, [rbx+8]
0x18007d770  cmp     rcx, rbx
0x18007d773  jb      short loc_18007D793
0x18007d775  mov     rax, cs:g_pfnAllocate
0x18007d77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d781  mov     r14, rax
0x18007d784  test    rax, rax
0x18007d787  jz      short loc_18007D793
0x18007d789  mov     dword ptr [rax], 70616548h
0x18007d78f  add     r14, 8
0x18007d793  test    r14, r14
0x18007d796  jnz     short loc_18007D7A2
0x18007d798  mov     ebx, 0C0000017h
0x18007d79d  jmp     loc_18007DA6F
0x18007d7a2  mov     r9d, cs:?g_cbHashObjectLength@@3KA; cbHashObject
0x18007d7a9  lea     rdx, [rbp+0D0h+hHash]; phHash
0x18007d7ad  mov     [rsp+110h+var_E0], edi; dwFlags
0x18007d7b1  mov     r8, r14; pbHashObject
0x18007d7b4  mov     dword ptr [rsp+110h+pdwSigLen], edi; cbSecret
0x18007d7b8  mov     rcx, r15; hAlgorithm
0x18007d7bb  mov     qword ptr [rsp+110h+dwFlags], rdi; pbSecret
0x18007d7c0  call    cs:__imp_BCryptCreateHash
0x18007d7c6  mov     ebx, eax
0x18007d7c8  test    eax, eax
0x18007d7ca  js      loc_18007DA6F
0x18007d7d0  mov     rdx, [rbp+0D0h+pbInput]; pbInput
0x18007d7d4  xor     r9d, r9d; dwFlags
0x18007d7d7  mov     rcx, [rbp+0D0h+hHash]; hHash
0x18007d7db  lea     r15d, [r9+20h]
0x18007d7df  mov     r8d, r15d; cbInput
0x18007d7e2  call    cs:__imp_BCryptHashData
0x18007d7e8  mov     ebx, eax
0x18007d7ea  test    eax, eax
0x18007d7ec  js      loc_18007DA6F
0x18007d7f2  mov     rcx, [rbp+0D0h+hHash]; hHash
0x18007d7f6  lea     r8d, [r15-0Ch]; cbOutput
0x18007d7fa  xor     r9d, r9d; dwFlags
0x18007d7fd  lea     rdx, [rbp+0D0h+pbOutput]; pbOutput
0x18007d801  call    cs:__imp_BCryptFinishHash
0x18007d807  mov     ebx, eax
0x18007d809  test    eax, eax
0x18007d80b  js      loc_18007DA6F
0x18007d811  lea     r8, [rbp+0D0h+var_C0]; int *
0x18007d815  mov     rdx, r12; void *
0x18007d818  lea     ecx, [r15-1Fh]; int
0x18007d81c  call    ?ScHelperIsNcryptRsaKey@@YAJHPEAXPEAH@Z; ScHelperIsNcryptRsaKey(int,void *,int *)
0x18007d821  xor     ecx, ecx
0x18007d823  mov     ebx, eax
0x18007d825  test    eax, eax
0x18007d827  js      loc_18007DA6F
0x18007d82d  cmp     [rbp+0D0h+var_C0], ecx
0x18007d830  jz      loc_18007DA6A
0x18007d836  mov     [rsp+110h+var_D8], 2; dwFlags
0x18007d83e  lea     rax, aSha1; "SHA1"
0x18007d845  mov     [rbp+0D0h+pPaddingInfo], rax
0x18007d849  lea     r9d, [r15-0Ch]; cbHashValue
0x18007d84d  lea     rax, [rbp+0D0h+pcbResult]
0x18007d851  mov     qword ptr [rsp+110h+var_E0], rax; pcbResult
0x18007d856  lea     r8, [rbp+0D0h+pbOutput]; pbHashValue
0x18007d85a  mov     dword ptr [rsp+110h+pdwSigLen], ecx; cbSignature
0x18007d85e  lea     rdx, [rbp+0D0h+pPaddingInfo]; pPaddingInfo
0x18007d862  mov     qword ptr [rsp+110h+dwFlags], rcx; pbSignature
0x18007d867  mov     rcx, r12; hKey
0x18007d86a  call    cs:__imp_NCryptSignHash
0x18007d870  mov     ebx, eax
0x18007d872  test    eax, eax
0x18007d874  js      loc_18007DA6F
0x18007d87a  mov     ebx, [rbp+0D0h+pcbResult]
0x18007d87d  test    rbx, rbx
0x18007d880  jz      short loc_18007D8DC
0x18007d882  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18007d889  ja      short loc_18007D8DC
0x18007d88b  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007d892  add     rcx, 8
0x18007d896  add     rcx, rbx
0x18007d899  cmp     rcx, rbx
0x18007d89c  jb      short loc_18007D8DC
0x18007d89e  call    VerifyStackAvailable
0x18007d8a3  test    eax, eax
0x18007d8a5  jz      short loc_18007D8DC
0x18007d8a7  lea     rax, [rbx+8]
0x18007d8ab  lea     rcx, [rax+0Fh]
0x18007d8af  cmp     rcx, rax
0x18007d8b2  ja      short loc_18007D8B7
0x18007d8b4  mov     rcx, rsi
0x18007d8b7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18007d8bb  mov     rax, rcx
0x18007d8be  call    _alloca_probe
0x18007d8c3  sub     rsp, rcx
0x18007d8c6  lea     rdi, [rsp+110h+pcbResult]
0x18007d8cb  test    rdi, rdi
0x18007d8ce  jz      short loc_18007D8DC
0x18007d8d0  mov     dword ptr [rdi], 6B637453h
0x18007d8d6  add     rdi, 8
0x18007d8da  jnz     short loc_18007D903
0x18007d8dc  lea     rcx, [rbx+8]
0x18007d8e0  cmp     rcx, rbx
0x18007d8e3  jb      short loc_18007D903
0x18007d8e5  mov     rax, cs:g_pfnAllocate
0x18007d8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8f1  mov     rdi, rax
0x18007d8f4  test    rax, rax
0x18007d8f7  jz      short loc_18007D903
0x18007d8f9  mov     dword ptr [rax], 70616548h
0x18007d8ff  add     rdi, 8
0x18007d903  test    rdi, rdi
0x18007d906  jz      loc_18007D798
0x18007d90c  lea     rax, [rbp+0D0h+pcbResult]
0x18007d910  mov     [rsp+110h+var_D8], 2; dwFlags
0x18007d918  mov     qword ptr [rsp+110h+var_E0], rax; pcbResult
0x18007d91d  lea     r8, [rbp+0D0h+pbOutput]; pbHashValue
0x18007d921  mov     eax, [rbp+0D0h+pcbResult]
0x18007d924  lea     rdx, [rbp+0D0h+pPaddingInfo]; pPaddingInfo
0x18007d928  mov     dword ptr [rsp+110h+pdwSigLen], eax; cbSignature
  ... truncated ...
```
