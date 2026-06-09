# GenerateCompactURI(ushort const *,ushort *,unsigned __int64)

- ea: `0x18005569c`
- end: `0x180055849`
- name: `?GenerateCompactURI@@YAJPEBGPEAG_K@Z`
- size: `429`
- prototype: `__int64 __fastcall(BYTE *pbData, STRSAFE_LPWSTR pszDest, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004168`

## callees

- `0x180024418`
- `0x18005569c`
- `0x180055850`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800556f6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800556f6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180055812`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180055812`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18005581e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18005581e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18005572b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18005572b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800557a4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800557a4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005576e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005576e`

## pseudocode

```c
__int64 __fastcall GenerateCompactURI(BYTE *pbData, STRSAFE_LPWSTR pszDest)
{
  size_t v2; // r14
  unsigned __int16 *v3; // rsi
  int Error; // ebx
  __int64 v6; // rax
  DWORD v7; // edi
  __int64 v9; // [rsp+30h] [rbp-29h]
  unsigned __int16 *v10; // [rsp+40h] [rbp-19h] BYREF
  DWORD pdwDataLen; // [rsp+48h] [rbp-11h] BYREF
  HCRYPTHASH phHash; // [rsp+50h] [rbp-9h] BYREF
  HCRYPTPROV phProv; // [rsp+58h] [rbp-1h] BYREF
  unsigned __int64 v14; // [rsp+60h] [rbp+7h] BYREF
  BYTE pbDataa[32]; // [rsp+68h] [rbp+Fh] BYREF

  v2 = 65;
  v10 = pszDest;
  v14 = 65;
  *pszDest = 0;
  v3 = pszDest;
  phProv = 0;
  if ( CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000040) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    phHash = 0;
    if ( !CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_19;
    }
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&pbData[2 * v6] );
    if ( (unsigned __int64)(2 * v6) > 0xFFFFFFFF )
    {
      Error = -2147024362;
    }
    else if ( CryptHashData(phHash, pbData, 2 * v6, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      pdwDataLen = 32;
      if ( CryptGetHashParam(phHash, 2u, pbDataa, &pdwDataLen, 0) )
      {
        Error = 0;
        goto LABEL_13;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
      {
LABEL_13:
        v7 = 0;
        while ( v7 < pdwDataLen )
        {
          LODWORD(v9) = pbDataa[v7++];
          Error = StringCchPrintfExW(v3, v2, &v10, &v14, 0, L"%02x", v9);
          if ( Error < 0 )
            break;
          v3 = v10;
          v2 = v14;
        }
      }
    }
    CryptDestroyHash(phHash);
LABEL_19:
    CryptReleaseContext(phProv, 0);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18005569c  mov     [rsp-8+arg_10], rbx
0x1800556a1  push    rbp
0x1800556a2  push    rsi
0x1800556a3  push    rdi
0x1800556a4  push    r14
0x1800556a6  push    r15
0x1800556a8  lea     rbp, [rsp-37h]
0x1800556ad  sub     rsp, 90h
0x1800556b4  mov     rax, cs:__security_cookie
0x1800556bb  xor     rax, rsp
0x1800556be  mov     [rbp+57h+var_28], rax
0x1800556c2  mov     r14d, 41h ; 'A'
0x1800556c8  mov     [rbp+57h+var_70], rdx
0x1800556cc  xor     r15d, r15d
0x1800556cf  mov     [rbp+57h+var_50], r14
0x1800556d3  mov     [rdx], r15w
0x1800556d7  mov     rsi, rdx
0x1800556da  mov     rdi, rcx
0x1800556dd  mov     [rbp+57h+phProv], r15
0x1800556e1  lea     r9d, [r14-29h]; dwProvType
0x1800556e5  mov     [rsp+0B0h+dwFlags], 0F0000040h; dwFlags
0x1800556ed  xor     r8d, r8d; szProvider
0x1800556f0  lea     rcx, [rbp+57h+phProv]; phProv
0x1800556f4  xor     edx, edx; szContainer
0x1800556f6  call    cs:__imp_CryptAcquireContextW
0x1800556fc  test    eax, eax
0x1800556fe  jnz     short loc_18005570F
0x180055700  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180055705  mov     ebx, eax
0x180055707  test    eax, eax
0x180055709  js      loc_180055824
0x18005570f  mov     rcx, [rbp+57h+phProv]; hProv
0x180055713  lea     rax, [rbp+57h+phHash]
0x180055717  xor     r9d, r9d; dwFlags
0x18005571a  mov     qword ptr [rsp+0B0h+dwFlags], rax; phHash
0x18005571f  xor     r8d, r8d; hKey
0x180055722  mov     [rbp+57h+phHash], r15
0x180055726  mov     edx, 800Ch; Algid
0x18005572b  call    cs:__imp_CryptCreateHash
0x180055731  test    eax, eax
0x180055733  jnz     short loc_180055744
0x180055735  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005573a  mov     ebx, eax
0x18005573c  test    eax, eax
0x18005573e  js      loc_180055818
0x180055744  or      rax, 0FFFFFFFFFFFFFFFFh
0x180055748  inc     rax
0x18005574b  cmp     [rdi+rax*2], r15w
0x180055750  jnz     short loc_180055748
0x180055752  lea     r8, [rax+rax]; dwDataLen
0x180055756  mov     eax, 0FFFFFFFFh
0x18005575b  cmp     r8, rax
0x18005575e  ja      loc_180055809
0x180055764  mov     rcx, [rbp+57h+phHash]; hHash
0x180055768  xor     r9d, r9d; dwFlags
0x18005576b  mov     rdx, rdi; pbData
0x18005576e  call    cs:__imp_CryptHashData
0x180055774  test    eax, eax
0x180055776  jnz     short loc_180055787
0x180055778  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005577d  mov     ebx, eax
0x18005577f  test    eax, eax
0x180055781  js      loc_18005580E
0x180055787  mov     rcx, [rbp+57h+phHash]; hHash
0x18005578b  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18005578f  lea     r8, [rbp+57h+pbData]; pbData
0x180055793  mov     [rbp+57h+pdwDataLen], 20h ; ' '
0x18005579a  mov     edx, 2; dwParam
0x18005579f  mov     [rsp+0B0h+dwFlags], r15d; dwFlags
0x1800557a4  call    cs:__imp_CryptGetHashParam
0x1800557aa  test    eax, eax
0x1800557ac  jz      short loc_1800557B3
0x1800557ae  mov     ebx, r15d
0x1800557b1  jmp     short loc_1800557BE
0x1800557b3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800557b8  mov     ebx, eax
0x1800557ba  test    eax, eax
0x1800557bc  js      short loc_18005580E
0x1800557be  mov     edi, r15d
0x1800557c1  cmp     edi, [rbp+57h+pdwDataLen]
0x1800557c4  jnb     short loc_18005580E
0x1800557c6  mov     eax, edi
0x1800557c8  lea     r9, [rbp+57h+var_50]; unsigned __int64 *
0x1800557cc  mov     rdx, r14; cchDest
0x1800557cf  mov     rcx, rsi; pszDest
0x1800557d2  movzx   r8d, [rbp+rax+57h+pbData]
0x1800557d8  lea     rax, a02x; "%02x"
0x1800557df  mov     [rsp+0B0h+var_80], r8d
0x1800557e4  lea     r8, [rbp+57h+var_70]; unsigned __int16 **
0x1800557e8  mov     [rsp+0B0h+var_88], rax; unsigned __int16 *
0x1800557ed  mov     qword ptr [rsp+0B0h+dwFlags], r15; dwFlags
0x1800557f2  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800557f7  inc     edi
0x1800557f9  mov     ebx, eax
0x1800557fb  test    eax, eax
0x1800557fd  js      short loc_18005580E
0x1800557ff  mov     rsi, [rbp+57h+var_70]
0x180055803  mov     r14, [rbp+57h+var_50]
0x180055807  jmp     short loc_1800557C1
0x180055809  mov     ebx, 80070216h
0x18005580e  mov     rcx, [rbp+57h+phHash]; hHash
0x180055812  call    cs:__imp_CryptDestroyHash
0x180055818  mov     rcx, [rbp+57h+phProv]; hProv
0x18005581c  xor     edx, edx; dwFlags
0x18005581e  call    cs:__imp_CryptReleaseContext
0x180055824  mov     eax, ebx
0x180055826  mov     rcx, [rbp+57h+var_28]
0x18005582a  xor     rcx, rsp; StackCookie
0x18005582d  call    __security_check_cookie
0x180055832  mov     rbx, [rsp+0B0h+arg_10]
0x18005583a  add     rsp, 90h
0x180055841  pop     r15
0x180055843  pop     r14
0x180055845  pop     rdi
0x180055846  pop     rsi
0x180055847  pop     rbp
0x180055848  retn
```
