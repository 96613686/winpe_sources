# I_CryptCAPI1AcquireKeyContext(_CERT_CONTEXT const *,ulong,_CRYPT_KEY_PROV_INFO *,HWND__ *,_CERT_KEY_CONTEXT *)

- ea: `0x18006f5ec`
- end: `0x18006f772`
- name: `?I_CryptCAPI1AcquireKeyContext@@YAHPEBU_CERT_CONTEXT@@KPEAU_CRYPT_KEY_PROV_INFO@@PEAUHWND__@@PEAU_CERT_KEY_CONTEXT@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, unsigned int, struct _CRYPT_KEY_PROV_INFO *, HWND, struct _CERT_KEY_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006f478`

## callees

- `0x18006f5ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f74c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f74c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006f762`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006f762`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006f6b7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18011a7c9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006f6b7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18011a7c9`
- `CRYPTSP!CryptAcquireContextW` at `0x18006f66c`
- `CRYPTSP!CryptAcquireContextW` at `0x18006f6dc`
- `CRYPTSP!CryptAcquireContextW` at `0x18011a7f0`
- `CRYPTSP!CryptAcquireContextW` at `0x18006f66c`
- `CRYPTSP!CryptAcquireContextW` at `0x18006f6dc`
- `CRYPTSP!CryptAcquireContextW` at `0x18011a7f0`
- `CRYPTSP!CryptReleaseContext` at `0x18006f75a`
- `CRYPTSP!CryptReleaseContext` at `0x18006f75a`
- `CRYPTSP!CryptSetProvParam` at `0x18006f6fe`
- `CRYPTSP!CryptSetProvParam` at `0x18006f73b`
- `CRYPTSP!CryptSetProvParam` at `0x18006f6fe`
- `CRYPTSP!CryptSetProvParam` at `0x18006f73b`

## pseudocode

```c
__int64 __fastcall I_CryptCAPI1AcquireKeyContext(
        const struct _CERT_CONTEXT *a1,
        char a2,
        struct _CRYPT_KEY_PROV_INFO *a3,
        HWND a4,
        struct _CERT_KEY_CONTEXT *a5)
{
  struct _CERT_KEY_CONTEXT *v6; // rbp
  unsigned int v7; // edi
  DWORD dwFlags; // r13d
  DWORD *p_dwProvType; // r15
  LPCWSTR *p_pwszProvName; // rsi
  const WCHAR *v11; // r8
  HCRYPTPROV *p_hCryptProv; // r14
  BOOL v13; // eax
  __int64 i; // rsi
  DWORD *v16; // r12
  DWORD LastError; // ebx
  const WCHAR *v18; // r8
  HWND pbData; // [rsp+98h] [rbp+20h] BYREF

  pbData = a4;
  v6 = a5;
  v7 = 1;
  dwFlags = a3->dwFlags & 0xFFFFFFBE | 0x40;
  if ( (a2 & 0x40) == 0 )
    dwFlags = a3->dwFlags & 0xFFFFFFFE;
  a5->dwKeySpec = a3->dwKeySpec;
  if ( a4 && !CryptSetProvParam(0, 1u, (const BYTE *)&pbData, 0) )
    goto LABEL_17;
  p_dwProvType = &a3->dwProvType;
  p_pwszProvName = (LPCWSTR *)&a3->pwszProvName;
  if ( a3->dwProvType == 1 )
  {
    v11 = *p_pwszProvName;
    if ( !*p_pwszProvName
      || !*v11
      || CompareStringW(0x409u, 1u, v11, -1, L"Microsoft Base Cryptographic Provider v1.0", -1) == 2 )
    {
      p_hCryptProv = &v6->hCryptProv;
      v13 = CryptAcquireContextW(
              &v6->hCryptProv,
              a3->pwszContainerName,
              L"Microsoft Enhanced Cryptographic Provider v1.0",
              1u,
              dwFlags);
      goto LABEL_7;
    }
    v16 = &a3->dwProvType;
  }
  else
  {
    v16 = &a3->dwProvType;
  }
  if ( *p_dwProvType == 13 )
  {
    v18 = *p_pwszProvName;
    if ( !*p_pwszProvName
      || !*v18
      || CompareStringW(0x409u, 1u, v18, -1, L"Microsoft Base DSS and Diffie-Hellman Cryptographic Provider", -1) == 2 )
    {
      p_hCryptProv = &v6->hCryptProv;
      v13 = CryptAcquireContextW(
              &v6->hCryptProv,
              a3->pwszContainerName,
              L"Microsoft Enhanced DSS and Diffie-Hellman Cryptographic Provider",
              0xDu,
              dwFlags);
      p_dwProvType = v16;
LABEL_7:
      if ( v13 )
        goto LABEL_8;
      goto LABEL_14;
    }
  }
  p_hCryptProv = &v6->hCryptProv;
  p_dwProvType = v16;
LABEL_14:
  if ( !CryptAcquireContextW(p_hCryptProv, a3->pwszContainerName, *p_pwszProvName, *p_dwProvType, dwFlags) )
  {
    *p_hCryptProv = 0;
LABEL_17:
    if ( v6->hCryptProv )
    {
      LastError = GetLastError();
      CryptReleaseContext(v6->hCryptProv, 0);
      SetLastError(LastError);
      v6->hCryptProv = 0;
    }
    return 0;
  }
LABEL_8:
  for ( i = 0; (unsigned int)i < a3->cProvParam; i = (unsigned int)(i + 1) )
  {
    if ( !CryptSetProvParam(
            v6->hCryptProv,
            a3->rgProvParam[i].dwParam,
            a3->rgProvParam[i].pbData,
            a3->rgProvParam[i].dwFlags) )
      goto LABEL_17;
  }
  return v7;
}

```

## disassembly

```asm
0x18006f5ec  mov     [rsp+pbData], r9
0x18006f5f1  push    rbx
0x18006f5f2  push    rbp
0x18006f5f3  push    rsi
0x18006f5f4  push    rdi
0x18006f5f5  push    r12
0x18006f5f7  push    r13
0x18006f5f9  push    r14
0x18006f5fb  push    r15
0x18006f5fd  sub     rsp, 38h
0x18006f601  mov     eax, [r8+14h]
0x18006f605  mov     rbx, r8
0x18006f608  mov     rbp, [rsp+78h+arg_20]
0x18006f610  and     eax, 0FFFFFFFEh
0x18006f613  mov     r13d, eax
0x18006f616  mov     edi, 1
0x18006f61b  or      r13d, 40h
0x18006f61f  test    dl, 40h
0x18006f622  cmovz   r13d, eax
0x18006f626  mov     eax, [r8+28h]
0x18006f62a  mov     [rbp+10h], eax
0x18006f62d  test    r9, r9
0x18006f630  jnz     loc_18006F6EF
0x18006f636  lea     r15, [rbx+10h]
0x18006f63a  or      r14d, 0FFFFFFFFh
0x18006f63e  lea     rsi, [rbx+8]
0x18006f642  cmp     [r15], edi
0x18006f645  jnz     loc_18006F71A
0x18006f64b  mov     r8, [rsi]; lpString1
0x18006f64e  test    r8, r8
0x18006f651  jnz     short loc_18006F694
0x18006f653  mov     rdx, [rbx]; szContainer
0x18006f656  lea     r14, [rbp+8]
0x18006f65a  mov     rcx, r14; phProv
0x18006f65d  mov     [rsp+78h+dwFlags], r13d; dwFlags
0x18006f662  mov     r9d, edi; dwProvType
0x18006f665  lea     r8, aMicrosoftEnhan_1; "Microsoft Enhanced Cryptographic Provid"...
0x18006f66c  call    cs:__imp_CryptAcquireContextW
0x18006f672  test    eax, eax
0x18006f674  jz      short loc_18006F6CB
0x18006f676  xor     esi, esi
0x18006f678  cmp     esi, [rbx+18h]
0x18006f67b  jb      loc_18006F722
0x18006f681  mov     eax, edi
0x18006f683  add     rsp, 38h
0x18006f687  pop     r15
0x18006f689  pop     r14
0x18006f68b  pop     r13
0x18006f68d  pop     r12
0x18006f68f  pop     rdi
0x18006f690  pop     rsi
0x18006f691  pop     rbp
0x18006f692  pop     rbx
0x18006f693  retn
0x18006f694  xor     eax, eax
0x18006f696  cmp     ax, [r8]
0x18006f69a  jz      short loc_18006F653
0x18006f69c  lea     rax, aMicrosoftBaseC_0; "Microsoft Base Cryptographic Provider v"...
0x18006f6a3  mov     [rsp+78h+cchCount2], r14d; cchCount2
0x18006f6a8  mov     r9d, r14d; cchCount1
0x18006f6ab  mov     qword ptr [rsp+78h+dwFlags], rax; lpString2
0x18006f6b0  mov     edx, edi; dwCmpFlags
0x18006f6b2  mov     ecx, 409h; Locale
0x18006f6b7  call    cs:__imp_CompareStringW
0x18006f6bd  cmp     eax, 2
0x18006f6c0  jz      short loc_18006F653
0x18006f6c2  lea     r12, [rbx+10h]
0x18006f6c6  jmp     loc_18011A798
0x18006f6cb  mov     r9d, [r15]; dwProvType
0x18006f6ce  mov     rcx, r14; phProv
0x18006f6d1  mov     r8, [rsi]; szProvider
0x18006f6d4  mov     rdx, [rbx]; szContainer
0x18006f6d7  mov     [rsp+78h+dwFlags], r13d; dwFlags
0x18006f6dc  call    cs:__imp_CryptAcquireContextW
0x18006f6e2  test    eax, eax
0x18006f6e4  jnz     short loc_18006F676
0x18006f6e6  mov     qword ptr [r14], 0
0x18006f6ed  jmp     short loc_18006F70C
0x18006f6ef  xor     r9d, r9d; dwFlags
0x18006f6f2  lea     r8, [rsp+78h+pbData]; pbData
0x18006f6fa  mov     edx, edi; dwParam
0x18006f6fc  xor     ecx, ecx; hProv
0x18006f6fe  call    cs:__imp_CryptSetProvParam
0x18006f704  test    eax, eax
0x18006f706  jnz     loc_18006F636
0x18006f70c  cmp     qword ptr [rbp+8], 0
0x18006f711  jnz     short loc_18006F74C
0x18006f713  xor     edi, edi
0x18006f715  jmp     loc_18006F681
0x18006f71a  mov     r12, r15
0x18006f71d  jmp     loc_18011A798
0x18006f722  mov     rdx, [rbx+20h]
0x18006f726  lea     rcx, [rsi+rsi*2]
0x18006f72a  mov     r9d, [rdx+rcx*8+14h]; dwFlags
0x18006f72f  mov     r8, [rdx+rcx*8+8]; pbData
0x18006f734  mov     edx, [rdx+rcx*8]; dwParam
0x18006f737  mov     rcx, [rbp+8]; hProv
0x18006f73b  call    cs:__imp_CryptSetProvParam
0x18006f741  test    eax, eax
0x18006f743  jz      short loc_18006F70C
0x18006f745  add     esi, edi
0x18006f747  jmp     loc_18006F678
0x18006f74c  call    cs:__imp_GetLastError
0x18006f752  mov     rcx, [rbp+8]; hProv
0x18006f756  xor     edx, edx; dwFlags
0x18006f758  mov     ebx, eax
0x18006f75a  call    cs:__imp_CryptReleaseContext
0x18006f760  mov     ecx, ebx; dwErrCode
0x18006f762  call    cs:__imp_SetLastError
0x18006f768  mov     qword ptr [rbp+8], 0
0x18006f770  jmp     short loc_18006F713
0x18011a798  cmp     dword ptr [r15], 0Dh
0x18011a79c  jnz     short loc_18011A7FE
0x18011a79e  mov     r8, [rsi]; lpString1
0x18011a7a1  test    r8, r8
0x18011a7a4  jz      short loc_18011A7D4
0x18011a7a6  xor     eax, eax
0x18011a7a8  cmp     ax, [r8]
0x18011a7ac  jz      short loc_18011A7D4
0x18011a7ae  lea     rax, aMicrosoftBaseD; "Microsoft Base DSS and Diffie-Hellman C"...
0x18011a7b5  mov     [rsp+78h+cchCount2], r14d; cchCount2
0x18011a7ba  mov     r9d, r14d; cchCount1
0x18011a7bd  mov     qword ptr [rsp+78h+dwFlags], rax; lpString2
0x18011a7c2  mov     edx, edi; dwCmpFlags
0x18011a7c4  mov     ecx, 409h; Locale
0x18011a7c9  call    cs:__imp_CompareStringW
0x18011a7cf  cmp     eax, 2
0x18011a7d2  jnz     short loc_18011A7FE
0x18011a7d4  mov     rdx, [rbx]; szContainer
0x18011a7d7  lea     r14, [rbp+8]
0x18011a7db  mov     rcx, r14; phProv
0x18011a7de  mov     [rsp+78h+dwFlags], r13d; dwFlags
0x18011a7e3  mov     r9d, 0Dh; dwProvType
0x18011a7e9  lea     r8, aMicrosoftEnhan_2; "Microsoft Enhanced DSS and Diffie-Hellm"...
0x18011a7f0  call    cs:__imp_CryptAcquireContextW
0x18011a7f6  mov     r15, r12
0x18011a7f9  jmp     loc_18006F672
0x18011a7fe  lea     r14, [rbp+8]
0x18011a802  mov     r15, r12
0x18011a805  jmp     loc_18006F6CB
```
