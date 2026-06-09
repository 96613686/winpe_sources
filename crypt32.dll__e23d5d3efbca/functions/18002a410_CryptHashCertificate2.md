# CryptHashCertificate2

- ea: `0x18002a410`
- end: `0x18002a7d0`
- name: `CryptHashCertificate2`
- size: `960`
- prototype: `BOOL __stdcall(LPCWSTR pwszCNGHashAlgid, DWORD dwFlags, void *pvReserved, const BYTE *pbEncoded, DWORD cbEncoded, BYTE *pbComputedHash, DWORD *pcbComputedHash)`
- caller_count: `11`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001d504`
- `0x18002a150`
- `0x18002b690`
- `0x18002fe64`
- `0x180060108`
- `0x1800939cc`
- `0x1800a9c1c`
- `0x1800cac00`
- `0x1800e3f18`
- `0x180100770`
- `0x180112d3c`

## callees

- `0x180028d60`
- `0x18002a410`
- `0x18002a7d8`
- `0x18002aa48`
- `0x18002bbd4`
- `0x180081758`
- `0x1800bec20`
- `0x180115040`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a795`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a672`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a6b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a7b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a672`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a6b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a7b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a516`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a721`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a516`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a721`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a4b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a74d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a4b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a74d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a470`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a49d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a4eb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a470`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a49d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a4eb`
- `bcrypt!BCryptFinishHash` at `0x18002a662`
- `bcrypt!BCryptFinishHash` at `0x18002a662`
- `bcrypt!BCryptDestroyHash` at `0x18002a68c`
- `bcrypt!BCryptDestroyHash` at `0x18002a68c`
- `bcrypt!BCryptHashData` at `0x18002a64a`
- `bcrypt!BCryptHashData` at `0x18002a64a`
- `bcrypt!BCryptCreateHash` at `0x18002a62e`
- `bcrypt!BCryptCreateHash` at `0x18002a62e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002a7a8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002a7a8`

## pseudocode

```c
BOOL __stdcall CryptHashCertificate2(
        LPCWSTR pwszCNGHashAlgid,
        DWORD dwFlags,
        void *pvReserved,
        const BYTE *pbEncoded,
        DWORD cbEncoded,
        BYTE *pbComputedHash,
        DWORD *pcbComputedHash)
{
  BOOL v8; // r14d
  UCHAR *p_cbOutput; // r13
  WCHAR *v10; // r12
  WCHAR *CNGAlgorithmProviderContext; // rbx
  __int64 v12; // rdx
  ULONG v13; // eax
  unsigned __int64 v14; // rsi
  UCHAR *v15; // rax
  unsigned __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  NTSTATUS v21; // eax
  DWORD LastError; // esi
  DWORD v23; // ecx
  HLOCAL v25; // rax
  DWORD v26; // eax
  void *v27; // rcx
  DWORD v28; // edi
  __int64 v29; // [rsp+0h] [rbp-40h] BYREF
  ULONG cbOutput; // [rsp+40h] [rbp+0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp+8h] BYREF
  PUCHAR pbInput; // [rsp+50h] [rbp+10h]

  pbInput = (PUCHAR)pbEncoded;
  cbOutput = 0;
  phHash = 0;
  v8 = 1;
  p_cbOutput = 0;
  if ( CompareStringW(0x409u, 1u, pwszCNGHashAlgid, -1, L"ECDSA", -1) == 2
    || CompareStringW(0x409u, 1u, pwszCNGHashAlgid, -1, L"ECDH", -1) == 2 )
  {
    CNGAlgorithmProviderContext = (WCHAR *)CreateCNGAlgorithmProviderContext(2, pwszCNGHashAlgid, 0);
    goto LABEL_10;
  }
  v10 = 0;
  EnterCriticalSection(&stru_18015CDD8);
  CNGAlgorithmProviderContext = (WCHAR *)qword_18015CE10;
  if ( qword_18015CE10 )
  {
    do
    {
      if ( CompareStringW(0x409u, 1u, pwszCNGHashAlgid, -1, *((PCNZWCH *)CNGAlgorithmProviderContext + 2), -1) == 2
        && !*((_DWORD *)CNGAlgorithmProviderContext + 6) )
      {
        break;
      }
      CNGAlgorithmProviderContext = *(WCHAR **)CNGAlgorithmProviderContext;
    }
    while ( CNGAlgorithmProviderContext );
    if ( CNGAlgorithmProviderContext )
      goto LABEL_7;
  }
  LeaveCriticalSection(&stru_18015CDD8);
  v10 = (WCHAR *)CreateCNGAlgorithmProviderContext(2, pwszCNGHashAlgid, 0);
  if ( v10 )
  {
    EnterCriticalSection(&stru_18015CDD8);
    CNGAlgorithmProviderContext = (WCHAR *)FindCNGAlgorithmProviderContext(2, pwszCNGHashAlgid, 0);
    if ( !CNGAlgorithmProviderContext )
    {
      v25 = qword_18015CE10;
      CNGAlgorithmProviderContext = v10;
      v10 = 0;
      qword_18015CE10 = CNGAlgorithmProviderContext;
      *(_QWORD *)CNGAlgorithmProviderContext = v25;
    }
LABEL_7:
    _InterlockedIncrement((volatile signed __int32 *)CNGAlgorithmProviderContext + 2);
    LeaveCriticalSection(&stru_18015CDD8);
  }
  if ( v10 )
    I_CryptReleaseCNGAlgorithmProvider(v10);
LABEL_10:
  if ( CNGAlgorithmProviderContext )
  {
    v13 = *((_DWORD *)CNGAlgorithmProviderContext + 11);
    cbOutput = v13;
    if ( !pbComputedHash )
    {
LABEL_30:
      LastError = 0;
      goto LABEL_34;
    }
    if ( *pcbComputedHash < v13 )
    {
      v23 = 234;
    }
    else
    {
      v14 = *((unsigned int *)CNGAlgorithmProviderContext + 10);
      if ( !*((_DWORD *)CNGAlgorithmProviderContext + 10) )
        goto LABEL_55;
      if ( v14 > g_ulMaxStackAllocSize )
        goto LABEL_55;
      v16 = v14 + g_ulAdditionalProbeSize + 8;
      if ( v16 < v14 || !(unsigned int)VerifyStackAvailable(v16, v12) )
        goto LABEL_55;
      v17 = v14 + 23;
      if ( v14 + 23 <= v14 + 8 )
        v17 = 0xFFFFFFFFFFFFFF0LL;
      v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
      v19 = alloca(v18);
      v20 = alloca(v18);
      p_cbOutput = (UCHAR *)&cbOutput;
      if ( &v29 == (__int64 *)-64LL || (cbOutput = 1801679955, (p_cbOutput = (UCHAR *)&phHash) == 0) )
      {
LABEL_55:
        if ( v14 + 8 >= v14 )
        {
          v15 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
          p_cbOutput = v15;
          if ( v15 )
          {
            *(_DWORD *)v15 = 1885431112;
            p_cbOutput = v15 + 8;
          }
        }
      }
      if ( p_cbOutput )
      {
        v21 = BCryptCreateHash(
                *((BCRYPT_ALG_HANDLE *)CNGAlgorithmProviderContext + 4),
                &phHash,
                p_cbOutput,
                *((_DWORD *)CNGAlgorithmProviderContext + 10),
                0,
                0,
                0);
        if ( !v21 )
        {
          v21 = BCryptHashData(phHash, pbInput, cbEncoded, 0);
          if ( !v21 )
          {
            v21 = BCryptFinishHash(phHash, pbComputedHash, cbOutput, 0);
            if ( !v21 )
              goto LABEL_30;
          }
        }
        v23 = v21;
      }
      else
      {
        v23 = -2147024882;
      }
    }
    SetLastError(v23);
  }
  LastError = GetLastError();
  v8 = 0;
LABEL_34:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_cbOutput && *((_DWORD *)p_cbOutput - 2) == 1885431112 )
    ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_cbOutput - 8);
  if ( CNGAlgorithmProviderContext
    && _InterlockedExchangeAdd((volatile signed __int32 *)CNGAlgorithmProviderContext + 2, 0xFFFFFFFF) == 1 )
  {
    v26 = GetLastError();
    v27 = (void *)*((_QWORD *)CNGAlgorithmProviderContext + 4);
    v28 = v26;
    if ( v27 )
      BCryptCloseAlgorithmProvider(v27, 0);
    PkiDefaultCryptFree(CNGAlgorithmProviderContext);
    SetLastError(v28);
  }
  if ( LastError )
    SetLastError(LastError);
  *pcbComputedHash = cbOutput;
  return v8;
}

```

## disassembly

```asm
0x18002a410  push    rbp
0x18002a412  push    rbx
0x18002a413  push    rsi
0x18002a414  push    rdi
0x18002a415  push    r12
0x18002a417  push    r13
0x18002a419  push    r14
0x18002a41b  push    r15
0x18002a41d  sub     rsp, 78h
0x18002a421  lea     rbp, [rsp+40h]
0x18002a426  mov     rax, cs:__security_cookie
0x18002a42d  xor     rax, rbp
0x18002a430  mov     [rbp+70h+var_50], rax
0x18002a434  xor     ebx, ebx
0x18002a436  mov     [rbp+70h+pbInput], r9
0x18002a43a  mov     edi, 0FFFFFFFFh
0x18002a43f  mov     [rbp+70h+cbOutput], ebx
0x18002a442  mov     rsi, rcx
0x18002a445  mov     [rsp+0B0h+cchCount2], edi; cchCount2
0x18002a449  lea     rax, aEcdsa; "ECDSA"
0x18002a450  mov     [rbp+70h+phHash], rbx
0x18002a454  mov     r8, rcx; lpString1
0x18002a457  mov     [rsp+0B0h+lpString2], rax; lpString2
0x18002a45c  mov     r14d, 1
0x18002a462  mov     r9d, edi; cchCount1
0x18002a465  mov     edx, r14d; dwCmpFlags
0x18002a468  mov     ecx, 409h; Locale
0x18002a46d  mov     r13d, ebx
0x18002a470  call    cs:__imp_CompareStringW
0x18002a476  cmp     eax, 2
0x18002a479  jz      loc_18002A702
0x18002a47f  lea     rax, aEcdh; "ECDH"
0x18002a486  mov     [rsp+0B0h+cchCount2], edi; cchCount2
0x18002a48a  mov     r9d, edi; cchCount1
0x18002a48d  mov     [rsp+0B0h+lpString2], rax; lpString2
0x18002a492  mov     r8, rsi; lpString1
0x18002a495  mov     edx, r14d; dwCmpFlags
0x18002a498  mov     ecx, 409h; Locale
0x18002a49d  call    cs:__imp_CompareStringW
0x18002a4a3  cmp     eax, 2
0x18002a4a6  jz      loc_18002A702
0x18002a4ac  lea     rcx, stru_18015CDD8; lpCriticalSection
0x18002a4b3  mov     r12d, ebx
0x18002a4b6  call    cs:__imp_EnterCriticalSection
0x18002a4bc  mov     rbx, cs:qword_18015CE10
0x18002a4c3  test    rbx, rbx
0x18002a4c6  jz      loc_18002A71A
0x18002a4cc  nop     dword ptr [rax+00h]
0x18002a4d0  mov     rax, [rbx+10h]
0x18002a4d4  mov     r9d, edi; cchCount1
0x18002a4d7  mov     [rsp+0B0h+cchCount2], edi; cchCount2
0x18002a4db  mov     r8, rsi; lpString1
0x18002a4de  mov     edx, r14d; dwCmpFlags
0x18002a4e1  mov     [rsp+0B0h+lpString2], rax; lpString2
0x18002a4e6  mov     ecx, 409h; Locale
0x18002a4eb  call    cs:__imp_CompareStringW
0x18002a4f1  cmp     eax, 2
0x18002a4f4  jz      loc_18002A58D
0x18002a4fa  mov     rbx, [rbx]
0x18002a4fd  test    rbx, rbx
0x18002a500  jnz     short loc_18002A4D0
0x18002a502  test    rbx, rbx
0x18002a505  jz      loc_18002A71A
0x18002a50b  lock inc dword ptr [rbx+8]
0x18002a50f  lea     rcx, stru_18015CDD8; lpCriticalSection
0x18002a516  call    cs:__imp_LeaveCriticalSection
0x18002a51c  test    r12, r12
0x18002a51f  jnz     loc_18002A7C3
0x18002a525  mov     r15, [rbp+70h+pcbComputedHash]
0x18002a52c  test    rbx, rbx
0x18002a52f  jz      loc_18002A678
0x18002a535  mov     r12, [rbp+70h+pbComputedHash]
0x18002a53c  mov     eax, [rbx+2Ch]
0x18002a53f  mov     [rbp+70h+cbOutput], eax
0x18002a542  test    r12, r12
0x18002a545  jz      loc_18002A66C
0x18002a54b  cmp     [r15], eax
0x18002a54e  jb      loc_18002A6F8
0x18002a554  mov     esi, [rbx+28h]
0x18002a557  test    rsi, rsi
0x18002a55a  jnz     short loc_18002A59C
0x18002a55c  lea     rcx, [rsi+8]
0x18002a560  cmp     rcx, rsi
0x18002a563  jb      loc_18002A607
0x18002a569  mov     rax, cs:g_pfnAllocate
0x18002a570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a575  mov     r13, rax
0x18002a578  test    rax, rax
0x18002a57b  jz      loc_18002A607
0x18002a581  mov     dword ptr [rax], 70616548h
0x18002a587  add     r13, 8
0x18002a58b  jmp     short loc_18002A607
0x18002a58d  cmp     [rbx+18h], r12d
0x18002a591  jnz     loc_18002A4FA
0x18002a597  jmp     loc_18002A502
0x18002a59c  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18002a5a3  ja      short loc_18002A55C
0x18002a5a5  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002a5ac  add     rcx, 8
0x18002a5b0  add     rcx, rsi
0x18002a5b3  cmp     rcx, rsi
0x18002a5b6  jb      short loc_18002A55C
0x18002a5b8  call    VerifyStackAvailable
0x18002a5bd  test    eax, eax
0x18002a5bf  jz      short loc_18002A55C
0x18002a5c1  lea     rax, [rsi+8]
0x18002a5c5  lea     rcx, [rax+0Fh]
0x18002a5c9  cmp     rcx, rax
0x18002a5cc  ja      short loc_18002A5D8
0x18002a5ce  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002a5d8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002a5dc  mov     rax, rcx
0x18002a5df  call    _alloca_probe
0x18002a5e4  sub     rsp, rcx
0x18002a5e7  lea     r13, [rsp+0B0h+cbOutput]
0x18002a5ec  test    r13, r13
0x18002a5ef  jz      loc_18002A55C
0x18002a5f5  mov     dword ptr [r13+0], 6B637453h
0x18002a5fd  add     r13, 8
0x18002a601  jz      loc_18002A55C
0x18002a607  test    r13, r13
0x18002a60a  jz      loc_18002A78B
0x18002a610  mov     r9d, [rbx+28h]; cbHashObject
0x18002a614  lea     rdx, [rbp+70h+phHash]; phHash
0x18002a618  mov     rcx, [rbx+20h]; hAlgorithm
0x18002a61c  xor     eax, eax
0x18002a61e  mov     [rsp+0B0h+dwFlags], eax; dwFlags
0x18002a622  mov     r8, r13; pbHashObject
0x18002a625  mov     [rsp+0B0h+cchCount2], eax; cbSecret
0x18002a629  mov     [rsp+0B0h+lpString2], rax; pbSecret
0x18002a62e  call    cs:__imp_BCryptCreateHash
0x18002a634  test    eax, eax
0x18002a636  jnz     short loc_18002A670
0x18002a638  mov     r8d, [rbp+70h+cbEncoded]; cbInput
0x18002a63f  xor     r9d, r9d; dwFlags
0x18002a642  mov     rdx, [rbp+70h+pbInput]; pbInput
0x18002a646  mov     rcx, [rbp+70h+phHash]; hHash
0x18002a64a  call    cs:__imp_BCryptHashData
0x18002a650  test    eax, eax
0x18002a652  jnz     short loc_18002A670
0x18002a654  mov     r8d, [rbp+70h+cbOutput]; cbOutput
0x18002a658  xor     r9d, r9d; dwFlags
0x18002a65b  mov     rcx, [rbp+70h+phHash]; hHash
0x18002a65f  mov     rdx, r12; pbOutput
0x18002a662  call    cs:__imp_BCryptFinishHash
0x18002a668  test    eax, eax
0x18002a66a  jnz     short loc_18002A670
0x18002a66c  xor     esi, esi
0x18002a66e  jmp     short loc_18002A683
0x18002a670  mov     ecx, eax; dwErrCode
0x18002a672  call    cs:__imp_SetLastError
0x18002a678  call    cs:__imp_GetLastError
0x18002a67e  mov     esi, eax
0x18002a680  xor     r14d, r14d
0x18002a683  mov     rcx, [rbp+70h+phHash]; hHash
0x18002a687  test    rcx, rcx
0x18002a68a  jz      short loc_18002A692
0x18002a68c  call    cs:__imp_BCryptDestroyHash
0x18002a692  test    r13, r13
0x18002a695  jnz     short loc_18002A6DC
0x18002a697  test    rbx, rbx
0x18002a69a  jz      short loc_18002A6AA
0x18002a69c  lock xadd [rbx+8], edi
0x18002a6a1  cmp     edi, 1
0x18002a6a4  jz      loc_18002A795
0x18002a6aa  test    esi, esi
0x18002a6ac  jz      short loc_18002A6B6
0x18002a6ae  mov     ecx, esi; dwErrCode
0x18002a6b0  call    cs:__imp_SetLastError
0x18002a6b6  mov     eax, [rbp+70h+cbOutput]
0x18002a6b9  mov     [r15], eax
0x18002a6bc  mov     eax, r14d
0x18002a6bf  mov     rcx, [rbp+70h+var_50]
0x18002a6c3  xor     rcx, rbp; StackCookie
0x18002a6c6  call    __security_check_cookie
0x18002a6cb  lea     rsp, [rbp+38h]
0x18002a6cf  pop     r15
0x18002a6d1  pop     r14
0x18002a6d3  pop     r13
0x18002a6d5  pop     r12
0x18002a6d7  pop     rdi
0x18002a6d8  pop     rsi
0x18002a6d9  pop     rbx
0x18002a6da  pop     rbp
0x18002a6db  retn
0x18002a6dc  cmp     dword ptr [r13-8], 70616548h
0x18002a6e4  lea     rcx, [r13-8]
0x18002a6e8  jnz     short loc_18002A697
0x18002a6ea  mov     rax, cs:g_pfnFree
0x18002a6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6f6  jmp     short loc_18002A697
0x18002a6f8  mov     ecx, 0EAh
0x18002a6fd  jmp     loc_18002A672
0x18002a702  xor     r8d, r8d
0x18002a705  mov     rdx, rsi
0x18002a708  mov     ecx, 2
0x18002a70d  call    CreateCNGAlgorithmProviderContext
0x18002a712  mov     rbx, rax
0x18002a715  jmp     loc_18002A525
0x18002a71a  lea     rcx, stru_18015CDD8; lpCriticalSection
0x18002a721  call    cs:__imp_LeaveCriticalSection
0x18002a727  xor     r8d, r8d
0x18002a72a  mov     rdx, rsi
0x18002a72d  mov     ecx, 2
0x18002a732  call    CreateCNGAlgorithmProviderContext
0x18002a737  mov     r15, rax
0x18002a73a  mov     r12, rax
0x18002a73d  test    rax, rax
0x18002a740  jz      loc_18002A51C
0x18002a746  lea     rcx, stru_18015CDD8; lpCriticalSection
0x18002a74d  call    cs:__imp_EnterCriticalSection
0x18002a753  xor     r8d, r8d
0x18002a756  mov     rdx, rsi
0x18002a759  mov     ecx, 2
0x18002a75e  call    FindCNGAlgorithmProviderContext
0x18002a763  mov     rbx, rax
0x18002a766  test    rax, rax
0x18002a769  jnz     loc_18002A50B
0x18002a76f  mov     rax, cs:qword_18015CE10
0x18002a776  mov     rbx, r12
0x18002a779  xor     r12d, r12d
0x18002a77c  mov     cs:qword_18015CE10, rbx
0x18002a783  mov     [rbx], rax
0x18002a786  jmp     loc_18002A50B
0x18002a78b  mov     ecx, 8007000Eh
0x18002a790  jmp     loc_18002A672
0x18002a795  call    cs:__imp_GetLastError
0x18002a79b  mov     rcx, [rbx+20h]; hAlgorithm
0x18002a79f  mov     edi, eax
0x18002a7a1  test    rcx, rcx
0x18002a7a4  jz      short loc_18002A7AE
0x18002a7a6  xor     edx, edx; dwFlags
0x18002a7a8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002a7ae  mov     rcx, rbx; hMem
0x18002a7b1  call    PkiDefaultCryptFree
0x18002a7b6  mov     ecx, edi; dwErrCode
0x18002a7b8  call    cs:__imp_SetLastError
0x18002a7be  jmp     loc_18002A6AA
0x18002a7c3  mov     rcx, r12; hMem
0x18002a7c6  call    I_CryptReleaseCNGAlgorithmProvider
0x18002a7cb  jmp     loc_18002A525
```
