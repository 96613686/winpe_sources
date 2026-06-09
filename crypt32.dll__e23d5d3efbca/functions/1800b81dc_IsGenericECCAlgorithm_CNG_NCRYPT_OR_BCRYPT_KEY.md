# IsGenericECCAlgorithm(_CNG_NCRYPT_OR_BCRYPT_KEY *)

- ea: `0x1800b81dc`
- end: `0x1800b849f`
- name: `?IsGenericECCAlgorithm@@YAHPEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@@Z`
- size: `707`
- prototype: `__int64 __fastcall(struct _CNG_NCRYPT_OR_BCRYPT_KEY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180070274`
- `0x1800ddea4`

## callees

- `0x18002a7d8`
- `0x1800b81dc`
- `0x1800bec20`
- `0x180115040`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b830e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b830e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8308`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8482`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8308`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b8482`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b8425`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b8452`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b8425`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b8452`
- `ncrypt!NCryptGetProperty` at `0x1800b822d`
- `ncrypt!NCryptGetProperty` at `0x1800b82f8`
- `ncrypt!NCryptGetProperty` at `0x1800b822d`
- `ncrypt!NCryptGetProperty` at `0x1800b82f8`
- `bcrypt!BCryptGetProperty` at `0x1800b8322`
- `bcrypt!BCryptGetProperty` at `0x1800b83f3`
- `bcrypt!BCryptGetProperty` at `0x1800b8322`
- `bcrypt!BCryptGetProperty` at `0x1800b83f3`

## pseudocode

```c
__int64 __fastcall IsGenericECCAlgorithm(struct _CNG_NCRYPT_OR_BCRYPT_KEY *a1)
{
  bool v1; // zf
  void *v3; // rcx
  SECURITY_STATUS Property; // eax
  __int64 v5; // rdx
  DWORD *p_cbOutput; // rbx
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  DWORD *v13; // rax
  DWORD v14; // ecx
  DWORD LastError; // esi
  __int64 v16; // rdx
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  DWORD *v23; // rax
  unsigned int v24; // edi
  _BYTE v26[32]; // [rsp+0h] [rbp-30h] BYREF
  DWORD *pcbResult; // [rsp+20h] [rbp-10h]
  DWORD dwFlags; // [rsp+28h] [rbp-8h]
  DWORD cbOutput; // [rsp+30h] [rbp+0h] BYREF
  __int64 v30; // [rsp+38h] [rbp+8h] BYREF

  dwFlags = 0;
  cbOutput = 0;
  v1 = *(_DWORD *)a1 == 0;
  pcbResult = &cbOutput;
  v3 = (void *)*((_QWORD *)a1 + 1);
  if ( !v1 )
  {
    Property = NCryptGetProperty((NCRYPT_HANDLE)v3, L"Algorithm Name", 0, 0, pcbResult, dwFlags);
    if ( !Property )
    {
      p_cbOutput = 0;
      v7 = cbOutput + 2LL;
      if ( v7 > g_ulMaxStackAllocSize )
        goto LABEL_44;
      v8 = v7 + g_ulAdditionalProbeSize + 8;
      if ( v8 < v7 || !(unsigned int)VerifyStackAvailable(v8, v5) )
        goto LABEL_44;
      v9 = v7 + 23;
      if ( v7 + 23 <= v7 + 8 )
        v9 = 0xFFFFFFFFFFFFFF0LL;
      v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
      v11 = alloca(v10);
      v12 = alloca(v10);
      p_cbOutput = &cbOutput;
      if ( v26 == (_BYTE *)-48LL || (cbOutput = 1801679955, (p_cbOutput = (DWORD *)&v30) == 0) )
      {
LABEL_44:
        if ( v7 + 8 >= v7 )
        {
          v13 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_cbOutput = v13;
          if ( v13 )
          {
            *v13 = 1885431112;
            p_cbOutput = v13 + 2;
          }
        }
      }
      if ( p_cbOutput )
      {
        Property = NCryptGetProperty(*((_QWORD *)a1 + 1), L"Algorithm Name", (PBYTE)p_cbOutput, cbOutput, &cbOutput, 0);
        goto LABEL_15;
      }
LABEL_31:
      v14 = -2147024882;
      goto LABEL_17;
    }
LABEL_19:
    p_cbOutput = 0;
    goto LABEL_16;
  }
  Property = BCryptGetProperty(v3, L"AlgorithmName", 0, 0, pcbResult, dwFlags);
  if ( Property )
    goto LABEL_19;
  p_cbOutput = 0;
  v17 = cbOutput + 2LL;
  if ( v17 > g_ulMaxStackAllocSize )
    goto LABEL_45;
  v18 = v17 + g_ulAdditionalProbeSize + 8;
  if ( v18 < v17 || !(unsigned int)VerifyStackAvailable(v18, v16) )
    goto LABEL_45;
  v19 = v17 + 23;
  if ( v17 + 23 <= v17 + 8 )
    v19 = 0xFFFFFFFFFFFFFF0LL;
  v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
  v21 = alloca(v20);
  v22 = alloca(v20);
  p_cbOutput = &cbOutput;
  if ( v26 == (_BYTE *)-48LL || (cbOutput = 1801679955, (p_cbOutput = (DWORD *)&v30) == 0) )
  {
LABEL_45:
    if ( v17 + 8 >= v17 )
    {
      v23 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_cbOutput = v23;
      if ( v23 )
      {
        *v23 = 1885431112;
        p_cbOutput = v23 + 2;
      }
    }
  }
  if ( !p_cbOutput )
    goto LABEL_31;
  Property = BCryptGetProperty(*((BCRYPT_HANDLE *)a1 + 1), L"AlgorithmName", (PUCHAR)p_cbOutput, cbOutput, &cbOutput, 0);
LABEL_15:
  if ( Property )
  {
LABEL_16:
    v14 = Property;
LABEL_17:
    SetLastError(v14);
    LastError = GetLastError();
LABEL_35:
    v24 = 0;
    goto LABEL_36;
  }
  LastError = 0;
  v24 = 1;
  if ( CompareStringW(0x409u, 1u, (PCNZWCH)p_cbOutput, -1, L"ECDSA", -1) != 2
    && CompareStringW(0x409u, 1u, (PCNZWCH)p_cbOutput, -1, L"ECDH", -1) != 2 )
  {
    goto LABEL_35;
  }
LABEL_36:
  if ( p_cbOutput && *(p_cbOutput - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( LastError )
    SetLastError(LastError);
  return v24;
}

```

## disassembly

```asm
0x1800b81dc  push    rbp
0x1800b81de  push    rbx
0x1800b81df  push    rsi
0x1800b81e0  push    rdi
0x1800b81e1  sub     rsp, 58h
0x1800b81e5  lea     rbp, [rsp+30h]
0x1800b81ea  mov     rax, cs:__security_cookie
0x1800b81f1  xor     rax, rbp
0x1800b81f4  mov     [rbp+40h+var_30], rax
0x1800b81f8  xor     r9d, r9d; cbOutput
0x1800b81fb  mov     [rsp+70h+dwFlags], 0; dwFlags
0x1800b8203  xor     r8d, r8d; pbOutput
0x1800b8206  mov     [rbp+40h+cbOutput], 0
0x1800b820d  cmp     [rcx], r8d
0x1800b8210  lea     rax, [rbp+40h+cbOutput]
0x1800b8214  mov     rsi, rcx
0x1800b8217  mov     [rsp+70h+pcbResult], rax; pcbResult
0x1800b821c  mov     rcx, [rcx+8]; hObject
0x1800b8220  jz      loc_1800B831B
0x1800b8226  lea     rdx, aAlgorithmName; "Algorithm Name"
0x1800b822d  call    cs:__imp_NCryptGetProperty
0x1800b8233  test    eax, eax
0x1800b8235  jnz     loc_1800B832C
0x1800b823b  mov     edi, [rbp+40h+cbOutput]
0x1800b823e  xor     ebx, ebx
0x1800b8240  add     rdi, 2
0x1800b8244  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800b824b  ja      short loc_1800B82A5
0x1800b824d  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800b8254  add     rcx, 8
0x1800b8258  add     rcx, rdi
0x1800b825b  cmp     rcx, rdi
0x1800b825e  jb      short loc_1800B82A5
0x1800b8260  call    VerifyStackAvailable
0x1800b8265  test    eax, eax
0x1800b8267  jz      short loc_1800B82A5
0x1800b8269  lea     rax, [rdi+8]
0x1800b826d  lea     rcx, [rax+0Fh]
0x1800b8271  cmp     rcx, rax
0x1800b8274  ja      short loc_1800B8280
0x1800b8276  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800b8280  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800b8284  mov     rax, rcx
0x1800b8287  call    _alloca_probe
0x1800b828c  sub     rsp, rcx
0x1800b828f  lea     rbx, [rsp+70h+cbOutput]
0x1800b8294  test    rbx, rbx
0x1800b8297  jz      short loc_1800B82A5
0x1800b8299  mov     dword ptr [rbx], 6B637453h
0x1800b829f  add     rbx, 8
0x1800b82a3  jnz     short loc_1800B82CC
0x1800b82a5  lea     rcx, [rdi+8]
0x1800b82a9  cmp     rcx, rdi
0x1800b82ac  jb      short loc_1800B82CC
0x1800b82ae  mov     rax, cs:g_pfnAllocate
0x1800b82b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b82ba  mov     rbx, rax
0x1800b82bd  test    rax, rax
0x1800b82c0  jz      short loc_1800B82CC
0x1800b82c2  mov     dword ptr [rax], 70616548h
0x1800b82c8  add     rbx, 8
0x1800b82cc  test    rbx, rbx
0x1800b82cf  jz      loc_1800B83C6
0x1800b82d5  mov     r9d, [rbp+40h+cbOutput]; cbOutput
0x1800b82d9  lea     rax, [rbp+40h+cbOutput]
0x1800b82dd  mov     rcx, [rsi+8]; hObject
0x1800b82e1  lea     rdx, aAlgorithmName; "Algorithm Name"
0x1800b82e8  mov     [rsp+70h+dwFlags], 0; dwFlags
0x1800b82f0  mov     r8, rbx; pbOutput
0x1800b82f3  mov     [rsp+70h+pcbResult], rax; pcbResult
0x1800b82f8  call    cs:__imp_NCryptGetProperty
0x1800b82fe  test    eax, eax
0x1800b8300  jz      loc_1800B83FE
0x1800b8306  mov     ecx, eax; dwErrCode
0x1800b8308  call    cs:__imp_SetLastError
0x1800b830e  call    cs:__imp_GetLastError
0x1800b8314  mov     esi, eax
0x1800b8316  jmp     loc_1800B845D
0x1800b831b  lea     rdx, aAlgorithmname; "AlgorithmName"
0x1800b8322  call    cs:__imp_BCryptGetProperty
0x1800b8328  test    eax, eax
0x1800b832a  jz      short loc_1800B8330
0x1800b832c  xor     ebx, ebx
0x1800b832e  jmp     short loc_1800B8306
0x1800b8330  mov     edi, [rbp+40h+cbOutput]
0x1800b8333  xor     ebx, ebx
0x1800b8335  add     rdi, 2
0x1800b8339  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800b8340  ja      short loc_1800B839A
0x1800b8342  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800b8349  add     rcx, 8
0x1800b834d  add     rcx, rdi
0x1800b8350  cmp     rcx, rdi
0x1800b8353  jb      short loc_1800B839A
0x1800b8355  call    VerifyStackAvailable
0x1800b835a  test    eax, eax
0x1800b835c  jz      short loc_1800B839A
0x1800b835e  lea     rax, [rdi+8]
0x1800b8362  lea     rcx, [rax+0Fh]
0x1800b8366  cmp     rcx, rax
0x1800b8369  ja      short loc_1800B8375
0x1800b836b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800b8375  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800b8379  mov     rax, rcx
0x1800b837c  call    _alloca_probe
0x1800b8381  sub     rsp, rcx
0x1800b8384  lea     rbx, [rsp+70h+cbOutput]
0x1800b8389  test    rbx, rbx
0x1800b838c  jz      short loc_1800B839A
0x1800b838e  mov     dword ptr [rbx], 6B637453h
0x1800b8394  add     rbx, 8
0x1800b8398  jnz     short loc_1800B83C1
0x1800b839a  lea     rcx, [rdi+8]
0x1800b839e  cmp     rcx, rdi
0x1800b83a1  jb      short loc_1800B83C1
0x1800b83a3  mov     rax, cs:g_pfnAllocate
0x1800b83aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b83af  mov     rbx, rax
0x1800b83b2  test    rax, rax
0x1800b83b5  jz      short loc_1800B83C1
0x1800b83b7  mov     dword ptr [rax], 70616548h
0x1800b83bd  add     rbx, 8
0x1800b83c1  test    rbx, rbx
0x1800b83c4  jnz     short loc_1800B83D0
0x1800b83c6  mov     ecx, 8007000Eh
0x1800b83cb  jmp     loc_1800B8308
0x1800b83d0  mov     r9d, [rbp+40h+cbOutput]; cbOutput
0x1800b83d4  lea     rax, [rbp+40h+cbOutput]
0x1800b83d8  mov     rcx, [rsi+8]; hObject
0x1800b83dc  lea     rdx, aAlgorithmname; "AlgorithmName"
0x1800b83e3  mov     [rsp+70h+dwFlags], 0; dwFlags
0x1800b83eb  mov     r8, rbx; pbOutput
0x1800b83ee  mov     [rsp+70h+pcbResult], rax; pcbResult
0x1800b83f3  call    cs:__imp_BCryptGetProperty
0x1800b83f9  jmp     loc_1800B82FE
0x1800b83fe  lea     rax, aEcdsa; "ECDSA"
0x1800b8405  mov     [rsp+70h+dwFlags], 0FFFFFFFFh; cchCount2
0x1800b840d  xor     esi, esi
0x1800b840f  mov     [rsp+70h+pcbResult], rax; lpString2
0x1800b8414  or      r9d, 0FFFFFFFFh; cchCount1
0x1800b8418  mov     r8, rbx; lpString1
0x1800b841b  mov     ecx, 409h; Locale
0x1800b8420  lea     edi, [rsi+1]
0x1800b8423  mov     edx, edi; dwCmpFlags
0x1800b8425  call    cs:__imp_CompareStringW
0x1800b842b  cmp     eax, 2
0x1800b842e  jz      short loc_1800B845F
0x1800b8430  lea     rax, aEcdh; "ECDH"
0x1800b8437  mov     [rsp+70h+dwFlags], 0FFFFFFFFh; cchCount2
0x1800b843f  or      r9d, 0FFFFFFFFh; cchCount1
0x1800b8443  mov     [rsp+70h+pcbResult], rax; lpString2
0x1800b8448  mov     r8, rbx; lpString1
0x1800b844b  mov     edx, edi; dwCmpFlags
0x1800b844d  mov     ecx, 409h; Locale
0x1800b8452  call    cs:__imp_CompareStringW
0x1800b8458  cmp     eax, 2
0x1800b845b  jz      short loc_1800B845F
0x1800b845d  xor     edi, edi
0x1800b845f  test    rbx, rbx
0x1800b8462  jz      short loc_1800B847C
0x1800b8464  lea     rcx, [rbx-8]
0x1800b8468  cmp     dword ptr [rcx], 70616548h
0x1800b846e  jnz     short loc_1800B847C
0x1800b8470  mov     rax, cs:g_pfnFree
0x1800b8477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b847c  test    esi, esi
0x1800b847e  jz      short loc_1800B8488
0x1800b8480  mov     ecx, esi; dwErrCode
0x1800b8482  call    cs:__imp_SetLastError
0x1800b8488  mov     eax, edi
0x1800b848a  mov     rcx, [rbp+40h+var_30]
0x1800b848e  xor     rcx, rbp; StackCookie
0x1800b8491  call    __security_check_cookie
0x1800b8496  lea     rsp, [rbp+28h]
0x1800b849a  pop     rdi
0x1800b849b  pop     rsi
0x1800b849c  pop     rbx
0x1800b849d  pop     rbp
0x1800b849e  retn
```
