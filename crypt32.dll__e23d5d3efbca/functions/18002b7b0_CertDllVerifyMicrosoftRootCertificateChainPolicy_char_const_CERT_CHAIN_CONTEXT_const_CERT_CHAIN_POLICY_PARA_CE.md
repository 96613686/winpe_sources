# CertDllVerifyMicrosoftRootCertificateChainPolicy(char const *,_CERT_CHAIN_CONTEXT const *,_CERT_CHAIN_POLICY_PARA *,_CERT_CHAIN_POLICY_STATUS *)

- ea: `0x18002b7b0`
- end: `0x18002bbcc`
- name: `?CertDllVerifyMicrosoftRootCertificateChainPolicy@@YAHPEBDPEBU_CERT_CHAIN_CONTEXT@@PEAU_CERT_CHAIN_POLICY_PARA@@PEAU_CERT_CHAIN_POLICY_STATUS@@@Z`
- size: `1052`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CHAIN_CONTEXT *, struct _CERT_CHAIN_POLICY_PARA *, struct _CERT_CHAIN_POLICY_STATUS *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002a7d8`
- `0x18002a8bc`
- `0x18002b7b0`
- `0x18002bbd4`
- `0x18002c7a0`
- `0x18009be5c`
- `0x1800bec20`
- `0x180115040`
- `0x1801150c4`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b975`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b96f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b96f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b9a9`
- `bcrypt!BCryptFinishHash` at `0x18002b958`
- `bcrypt!BCryptFinishHash` at `0x18002b958`
- `bcrypt!BCryptDestroyHash` at `0x18002b98c`
- `bcrypt!BCryptDestroyHash` at `0x18002b98c`
- `bcrypt!BCryptHashData` at `0x18002b940`
- `bcrypt!BCryptHashData` at `0x18002b940`
- `bcrypt!BCryptCreateHash` at `0x18002b929`
- `bcrypt!BCryptCreateHash` at `0x18002b929`

## pseudocode

```c
__int64 __fastcall CertDllVerifyMicrosoftRootCertificateChainPolicy(
        const char *a1,
        const struct _CERT_CHAIN_CONTEXT *a2,
        struct _CERT_CHAIN_POLICY_PARA *a3,
        struct _CERT_CHAIN_POLICY_STATUS *a4)
{
  PCERT_SIMPLE_CHAIN *rgpChain; // rax
  PCERT_SIMPLE_CHAIN v5; // rax
  DWORD cElement; // ecx
  DWORD dwFlags; // r14d
  PCERT_CHAIN_ELEMENT *rgpElement; // rax
  __int64 v9; // rcx
  UCHAR *p_phHash; // rbx
  ULONG v11; // r12d
  PCERT_INFO pCertInfo; // rax
  ULONG cbData; // esi
  UCHAR *pbData; // r13
  __int64 CNGAlgorithmProvider; // rax
  __int64 v16; // rdx
  __int64 v17; // r15
  unsigned __int64 v18; // rdi
  UCHAR *v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  NTSTATUS v25; // eax
  DWORD LastError; // edi
  int v27; // esi
  DWORD v28; // ecx
  __int64 p_Parameters; // rdi
  __int64 i; // rbx
  __int64 *v31; // rcx
  unsigned int v32; // eax
  LONG v33; // edx
  int v34; // eax
  struct _CERT_CHAIN_POLICY_STATUS *v35; // rcx
  __int64 result; // rax
  __int64 m; // rbx
  __int64 n; // rbx
  __int64 j; // rbx
  __int64 k; // rbx
  __int64 v41; // [rsp+0h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp+0h] BYREF
  LONG v43; // [rsp+48h] [rbp+8h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp+10h]
  struct _CERT_CHAIN_POLICY_STATUS *v45; // [rsp+58h] [rbp+18h]
  UCHAR pbOutput[32]; // [rsp+68h] [rbp+28h] BYREF

  rgpChain = a2->rgpChain;
  v45 = a4;
  v5 = *rgpChain;
  cElement = v5->cElement;
  if ( a3 && a3->cbSize > 4 )
    dwFlags = a3->dwFlags;
  else
    dwFlags = 0;
  rgpElement = v5->rgpElement;
  v9 = cElement - 1;
  p_phHash = 0;
  v43 = v9;
  v11 = 0;
  phHash = 0;
  pCertContext = rgpElement[v9]->pCertContext;
  pCertInfo = pCertContext->pCertInfo;
  cbData = pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData;
  pbData = pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData;
  CNGAlgorithmProvider = I_CryptGetCNGAlgorithmProvider(2, L"SHA256");
  v17 = CNGAlgorithmProvider;
  if ( CNGAlgorithmProvider )
  {
    v11 = *(_DWORD *)(CNGAlgorithmProvider + 44);
    if ( v11 > 0x20 )
    {
      v28 = 234;
    }
    else
    {
      v18 = *(unsigned int *)(CNGAlgorithmProvider + 40);
      if ( !*(_DWORD *)(CNGAlgorithmProvider + 40) )
        goto LABEL_74;
      if ( v18 > g_ulMaxStackAllocSize )
        goto LABEL_74;
      v20 = v18 + g_ulAdditionalProbeSize + 8;
      if ( v20 < v18 || !(unsigned int)VerifyStackAvailable(v20, v16) )
        goto LABEL_74;
      v21 = v18 + 23;
      if ( v18 + 23 <= v18 + 8 )
        v21 = 0xFFFFFFFFFFFFFF0LL;
      v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
      v23 = alloca(v22);
      v24 = alloca(v22);
      p_phHash = (UCHAR *)&phHash;
      if ( &v41 == (__int64 *)-64LL || (LODWORD(phHash) = 1801679955, (p_phHash = (UCHAR *)&v43) == 0) )
      {
LABEL_74:
        if ( v18 + 8 >= v18 )
        {
          v19 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
          p_phHash = v19;
          if ( v19 )
          {
            *(_DWORD *)v19 = 1885431112;
            p_phHash = v19 + 8;
          }
        }
      }
      if ( p_phHash )
      {
        v25 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(v17 + 32), &phHash, p_phHash, *(_DWORD *)(v17 + 40), 0, 0, 0);
        if ( !v25 )
        {
          v25 = BCryptHashData(phHash, pbData, cbData, 0);
          if ( !v25 )
          {
            v25 = BCryptFinishHash(phHash, pbOutput, v11, 0);
            if ( !v25 )
            {
              LastError = 0;
              v27 = 1;
              goto LABEL_25;
            }
          }
        }
        v28 = v25;
      }
      else
      {
        v28 = -2147024882;
      }
    }
    SetLastError(v28);
  }
  v27 = 0;
  LastError = GetLastError();
LABEL_25:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_phHash && *((_DWORD *)p_phHash - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  I_CryptReleaseCNGAlgorithmProvider((HLOCAL)v17);
  if ( LastError )
    SetLastError(LastError);
  if ( !v27 || v11 != 32 )
  {
LABEL_42:
    v33 = v43;
    v34 = -2146762487;
    goto LABEL_43;
  }
  p_Parameters = (__int64)&pCertContext->pCertInfo->SubjectPublicKeyInfo.Algorithm.Parameters;
  if ( (dwFlags & 0x20000) == 0 )
  {
    for ( i = 0; (unsigned int)i < 6; i = (unsigned int)(i + 1) )
    {
      if ( !memcmp_0(&qword_180127E38[5 * i], pbOutput, 0x20u) )
      {
        v31 = (&off_180127E30)[5 * i];
        v32 = *(_DWORD *)p_Parameters;
        if ( *(_DWORD *)v31 == *(_DWORD *)p_Parameters
          && (!v32 || !memcmp_0((const void *)v31[1], *(const void **)(p_Parameters + 8), v32)) )
        {
          goto LABEL_61;
        }
      }
    }
    if ( (dwFlags & 0x40000) == 0 && (unsigned int)IPR_IsFlightRootsAllowed() )
    {
      for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)IsRootEntryMatch(&_ImageBase[20 * j + 605832], pbOutput, p_Parameters) )
          goto LABEL_61;
      }
    }
    if ( (dwFlags & 0x10000) != 0 )
    {
      for ( k = 0; (unsigned int)k < 4; k = (unsigned int)(k + 1) )
      {
        if ( (unsigned int)IsRootEntryMatch(&_ImageBase[20 * k + 605896], pbOutput, p_Parameters) )
          goto LABEL_61;
      }
    }
    goto LABEL_42;
  }
  if ( (dwFlags & 0x10000) == 0 )
  {
    for ( m = 0; !(_DWORD)m; m = 1 )
    {
      if ( (unsigned int)IsRootEntryMatch(&_ImageBase[20 * m + 605872], pbOutput, p_Parameters) )
      {
LABEL_61:
        v34 = 0;
        goto LABEL_54;
      }
    }
    if ( (dwFlags & 0x40000) == 0 && (unsigned int)IPR_IsFlightRootsAllowed() )
    {
      for ( n = 0; (unsigned int)n < 2; n = (unsigned int)(n + 1) )
      {
        if ( (unsigned int)IsRootEntryMatch(&_ImageBase[20 * n + 605832], pbOutput, p_Parameters) )
          goto LABEL_61;
      }
    }
    goto LABEL_42;
  }
  v34 = -2147024809;
LABEL_54:
  v33 = 0;
LABEL_43:
  v35 = v45;
  v45->dwError = v34;
  result = 1;
  v35->lChainIndex = 0;
  v35->lElementIndex = v33;
  return result;
}

```

## disassembly

```asm
0x18002b7b0  push    rbp
0x18002b7b2  push    rsi
0x18002b7b3  push    rdi
0x18002b7b4  push    r12
0x18002b7b6  push    r13
0x18002b7b8  push    r14
0x18002b7ba  push    r15
0x18002b7bc  sub     rsp, 90h
0x18002b7c3  lea     rbp, [rsp+40h]
0x18002b7c8  mov     [rbp+80h+arg_0], rbx
0x18002b7cf  mov     rax, cs:__security_cookie
0x18002b7d6  xor     rax, rbp
0x18002b7d9  mov     [rbp+80h+var_38], rax
0x18002b7dd  mov     rax, [rdx+10h]
0x18002b7e1  mov     [rbp+80h+var_68], r9
0x18002b7e5  mov     rax, [rax]
0x18002b7e8  mov     ecx, [rax+0Ch]
0x18002b7eb  test    r8, r8
0x18002b7ee  jz      loc_18002BA90
0x18002b7f4  cmp     dword ptr [r8], 4
0x18002b7f8  jbe     loc_18002BA90
0x18002b7fe  mov     r14d, [r8+4]
0x18002b802  mov     rax, [rax+10h]
0x18002b806  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x18002b80d  dec     ecx
0x18002b80f  xor     ebx, ebx
0x18002b811  mov     [rbp+80h+var_78], ecx
0x18002b814  xor     r8d, r8d
0x18002b817  xor     r12d, r12d
0x18002b81a  mov     [rbp+80h+phHash], rbx
0x18002b81e  mov     rcx, [rax+rcx*8]
0x18002b822  mov     rax, [rcx+8]
0x18002b826  lea     ecx, [rbx+2]
0x18002b829  mov     [rbp+80h+var_70], rax
0x18002b82d  mov     rax, [rax+18h]
0x18002b831  mov     esi, [rax+78h]
0x18002b834  mov     r13, [rax+80h]
0x18002b83b  call    I_CryptGetCNGAlgorithmProvider
0x18002b840  mov     r15, rax
0x18002b843  test    rax, rax
0x18002b846  jz      loc_18002B975
0x18002b84c  mov     r12d, [rax+2Ch]
0x18002b850  cmp     r12d, 20h ; ' '
0x18002b854  ja      loc_18002BAF6
0x18002b85a  mov     edi, [rax+28h]
0x18002b85d  test    rdi, rdi
0x18002b860  jnz     short loc_18002B88F
0x18002b862  lea     rcx, [rdi+8]
0x18002b866  cmp     rcx, rdi
0x18002b869  jb      loc_18002B8F8
0x18002b86f  mov     rax, cs:g_pfnAllocate
0x18002b876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b87b  mov     rbx, rax
0x18002b87e  test    rax, rax
0x18002b881  jz      short loc_18002B8F8
0x18002b883  mov     dword ptr [rax], 70616548h
0x18002b889  add     rbx, 8
0x18002b88d  jmp     short loc_18002B8F8
0x18002b88f  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18002b896  ja      short loc_18002B862
0x18002b898  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002b89f  add     rcx, 8
0x18002b8a3  add     rcx, rdi
0x18002b8a6  cmp     rcx, rdi
0x18002b8a9  jb      short loc_18002B862
0x18002b8ab  call    VerifyStackAvailable
0x18002b8b0  test    eax, eax
0x18002b8b2  jz      short loc_18002B862
0x18002b8b4  lea     rax, [rdi+8]
0x18002b8b8  lea     rcx, [rax+0Fh]
0x18002b8bc  cmp     rcx, rax
0x18002b8bf  ja      short loc_18002B8CB
0x18002b8c1  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002b8cb  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002b8cf  mov     rax, rcx
0x18002b8d2  call    _alloca_probe
0x18002b8d7  sub     rsp, rcx
0x18002b8da  lea     rbx, [rsp+0C0h+phHash]
0x18002b8df  test    rbx, rbx
0x18002b8e2  jz      loc_18002B862
0x18002b8e8  mov     dword ptr [rbx], 6B637453h
0x18002b8ee  add     rbx, 8
0x18002b8f2  jz      loc_18002B862
0x18002b8f8  test    rbx, rbx
0x18002b8fb  jz      loc_18002BBC2
0x18002b901  mov     r9d, [r15+28h]; cbHashObject
0x18002b905  lea     rdx, [rbp+80h+phHash]; phHash
0x18002b909  mov     rcx, [r15+20h]; hAlgorithm
0x18002b90d  mov     r8, rbx; pbHashObject
0x18002b910  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x18002b918  mov     [rsp+0C0h+cbSecret], 0; cbSecret
0x18002b920  mov     [rsp+0C0h+pbSecret], 0; pbSecret
0x18002b929  call    cs:__imp_BCryptCreateHash
0x18002b92f  test    eax, eax
0x18002b931  jnz     short loc_18002B96D
0x18002b933  mov     rcx, [rbp+80h+phHash]; hHash
0x18002b937  xor     r9d, r9d; dwFlags
0x18002b93a  mov     r8d, esi; cbInput
0x18002b93d  mov     rdx, r13; pbInput
0x18002b940  call    cs:__imp_BCryptHashData
0x18002b946  test    eax, eax
0x18002b948  jnz     short loc_18002B96D
0x18002b94a  mov     rcx, [rbp+80h+phHash]; hHash
0x18002b94e  lea     rdx, [rbp+80h+pbOutput]; pbOutput
0x18002b952  xor     r9d, r9d; dwFlags
0x18002b955  mov     r8d, r12d; cbOutput
0x18002b958  call    cs:__imp_BCryptFinishHash
0x18002b95e  test    eax, eax
0x18002b960  jnz     short loc_18002B96D
0x18002b962  lea     r13d, [rax+1]
0x18002b966  xor     edi, edi
0x18002b968  mov     esi, r13d
0x18002b96b  jmp     short loc_18002B983
0x18002b96d  mov     ecx, eax; dwErrCode
0x18002b96f  call    cs:__imp_SetLastError
0x18002b975  call    cs:__imp_GetLastError
0x18002b97b  xor     esi, esi
0x18002b97d  mov     edi, eax
0x18002b97f  lea     r13d, [rsi+1]
0x18002b983  mov     rcx, [rbp+80h+phHash]; hHash
0x18002b987  test    rcx, rcx
0x18002b98a  jz      short loc_18002B992
0x18002b98c  call    cs:__imp_BCryptDestroyHash
0x18002b992  test    rbx, rbx
0x18002b995  jnz     loc_18002BAD5
0x18002b99b  mov     rcx, r15; hMem
0x18002b99e  call    I_CryptReleaseCNGAlgorithmProvider
0x18002b9a3  test    edi, edi
0x18002b9a5  jz      short loc_18002B9AF
0x18002b9a7  mov     ecx, edi; dwErrCode
0x18002b9a9  call    cs:__imp_SetLastError
0x18002b9af  test    esi, esi
0x18002b9b1  jz      loc_18002BA51
0x18002b9b7  cmp     r12d, 20h ; ' '
0x18002b9bb  jnz     loc_18002BA51
0x18002b9c1  mov     rdi, [rbp+80h+var_70]
0x18002b9c5  mov     rdi, [rdi+18h]
0x18002b9c9  add     rdi, 68h ; 'h'
0x18002b9cd  bt      r14d, 11h
0x18002b9d2  jb      loc_18002BA98
0x18002b9d8  xor     ebx, ebx
0x18002b9da  lea     rsi, __ImageBase
0x18002b9e1  cmp     ebx, 6
0x18002b9e4  jnb     short loc_18002BA3B
0x18002b9e6  lea     r15, [rbx+rbx*4]
0x18002b9ea  mov     r8d, 20h ; ' '; Size
0x18002b9f0  lea     rcx, rva qword_180127E38[rsi]
0x18002b9f7  lea     rcx, [rcx+r15*8]; Buf1
0x18002b9fb  lea     rdx, [rbp+80h+pbOutput]; Buf2
0x18002b9ff  call    memcmp_0
0x18002ba04  test    eax, eax
0x18002ba06  jnz     short loc_18002BA36
0x18002ba08  mov     rcx, ds:rva off_180127E30[rsi+r15*8]
0x18002ba10  mov     eax, [rdi]
0x18002ba12  cmp     [rcx], eax
0x18002ba14  jnz     short loc_18002BA36
0x18002ba16  test    eax, eax
0x18002ba18  jz      loc_18002BB53
0x18002ba1e  mov     rdx, [rdi+8]; Buf2
0x18002ba22  mov     r8d, eax; Size
0x18002ba25  mov     rcx, [rcx+8]; Buf1
0x18002ba29  call    memcmp_0
0x18002ba2e  test    eax, eax
0x18002ba30  jz      loc_18002BB53
0x18002ba36  add     ebx, r13d
0x18002ba39  jmp     short loc_18002B9E1
0x18002ba3b  bt      r14d, 12h
0x18002ba40  jnb     loc_18002BB57
0x18002ba46  bt      r14d, 10h
0x18002ba4b  jb      loc_18002BB93
0x18002ba51  mov     edx, [rbp+80h+var_78]
0x18002ba54  mov     eax, 800B0109h
0x18002ba59  mov     rcx, [rbp+80h+var_68]
0x18002ba5d  mov     [rcx+4], eax
0x18002ba60  mov     eax, r13d
0x18002ba63  mov     dword ptr [rcx+8], 0
0x18002ba6a  mov     [rcx+0Ch], edx
0x18002ba6d  mov     rcx, [rbp+80h+var_38]
0x18002ba71  xor     rcx, rbp; StackCookie
0x18002ba74  call    __security_check_cookie
0x18002ba79  mov     rbx, [rbp+80h+arg_0]
0x18002ba80  lea     rsp, [rbp+50h]
0x18002ba84  pop     r15
0x18002ba86  pop     r14
0x18002ba88  pop     r13
0x18002ba8a  pop     r12
0x18002ba8c  pop     rdi
0x18002ba8d  pop     rsi
0x18002ba8e  pop     rbp
0x18002ba8f  retn
0x18002ba90  xor     r14d, r14d
0x18002ba93  jmp     loc_18002B802
0x18002ba98  bt      r14d, 10h
0x18002ba9d  jb      short loc_18002BB00
0x18002ba9f  xor     ebx, ebx
0x18002baa1  lea     rsi, __ImageBase
0x18002baa8  cmp     ebx, r13d
0x18002baab  jnb     short loc_18002BB0C
0x18002baad  lea     rcx, [rbx+rbx*4]
0x18002bab1  mov     r8, rdi
0x18002bab4  lea     rcx, ds:127D60h[rcx*8]
0x18002babc  add     rcx, rsi
0x18002babf  lea     rdx, [rbp+80h+pbOutput]
0x18002bac3  call    IsRootEntryMatch
0x18002bac8  test    eax, eax
0x18002baca  jnz     loc_18002BB53
0x18002bad0  add     ebx, r13d
0x18002bad3  jmp     short loc_18002BAA8
0x18002bad5  lea     rcx, [rbx-8]
0x18002bad9  cmp     dword ptr [rcx], 70616548h
0x18002badf  jnz     loc_18002B99B
0x18002bae5  mov     rax, cs:g_pfnFree
0x18002baec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002baf1  jmp     loc_18002B99B
0x18002baf6  mov     ecx, 0EAh
0x18002bafb  jmp     loc_18002B96F
0x18002bb00  mov     eax, 80070057h
0x18002bb05  xor     edx, edx
0x18002bb07  jmp     loc_18002BA59
0x18002bb0c  bt      r14d, 12h
0x18002bb11  jb      loc_18002BA51
0x18002bb17  call    ?IPR_IsFlightRootsAllowed@@YAHXZ; IPR_IsFlightRootsAllowed(void)
0x18002bb1c  test    eax, eax
0x18002bb1e  jz      loc_18002BA51
0x18002bb24  xor     ebx, ebx
0x18002bb26  cmp     ebx, 2
0x18002bb29  jnb     loc_18002BA51
0x18002bb2f  lea     rcx, [rbx+rbx*4]
0x18002bb33  mov     r8, rdi
0x18002bb36  lea     rcx, ds:127D10h[rcx*8]
0x18002bb3e  add     rcx, rsi
0x18002bb41  lea     rdx, [rbp+80h+pbOutput]
0x18002bb45  call    IsRootEntryMatch
0x18002bb4a  test    eax, eax
0x18002bb4c  jnz     short loc_18002BB53
0x18002bb4e  add     ebx, r13d
0x18002bb51  jmp     short loc_18002BB26
0x18002bb53  xor     eax, eax
0x18002bb55  jmp     short loc_18002BB05
0x18002bb57  call    ?IPR_IsFlightRootsAllowed@@YAHXZ; IPR_IsFlightRootsAllowed(void)
0x18002bb5c  test    eax, eax
0x18002bb5e  jz      loc_18002BA46
0x18002bb64  xor     ebx, ebx
0x18002bb66  cmp     ebx, 2
0x18002bb69  jnb     loc_18002BA46
0x18002bb6f  lea     rcx, [rbx+rbx*4]
0x18002bb73  mov     r8, rdi
0x18002bb76  lea     rcx, ds:127D10h[rcx*8]
0x18002bb7e  add     rcx, rsi
0x18002bb81  lea     rdx, [rbp+80h+pbOutput]
0x18002bb85  call    IsRootEntryMatch
0x18002bb8a  test    eax, eax
0x18002bb8c  jnz     short loc_18002BB53
0x18002bb8e  add     ebx, r13d
0x18002bb91  jmp     short loc_18002BB66
0x18002bb93  xor     ebx, ebx
0x18002bb95  cmp     ebx, 4
0x18002bb98  jnb     loc_18002BA51
0x18002bb9e  lea     rcx, [rbx+rbx*4]
0x18002bba2  mov     r8, rdi
0x18002bba5  lea     rcx, ds:127D90h[rcx*8]
0x18002bbad  add     rcx, rsi
0x18002bbb0  lea     rdx, [rbp+80h+pbOutput]
0x18002bbb4  call    IsRootEntryMatch
0x18002bbb9  test    eax, eax
0x18002bbbb  jnz     short loc_18002BB53
0x18002bbbd  add     ebx, r13d
0x18002bbc0  jmp     short loc_18002BB95
0x18002bbc2  mov     ecx, 8007000Eh
0x18002bbc7  jmp     loc_18002B96F
```
