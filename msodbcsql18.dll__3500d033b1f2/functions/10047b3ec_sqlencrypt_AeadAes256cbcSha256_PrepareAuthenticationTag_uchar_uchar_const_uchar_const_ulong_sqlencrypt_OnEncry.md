# sqlencrypt::AeadAes256cbcSha256::PrepareAuthenticationTag(uchar *,uchar const *,uchar * const,ulong,sqlencrypt::OnEncryptionError *)

- ea: `0x10047b3ec`
- end: `0x10047b68e`
- name: `?PrepareAuthenticationTag@AeadAes256cbcSha256@sqlencrypt@@AEAAXPEAEPEBEQEAEKPEAUOnEncryptionError@2@@Z`
- size: `674`
- prototype: `void(sqlencrypt::AeadAes256cbcSha256 *__hidden this, unsigned __int8 *, const unsigned __int8 *, unsigned __int8 *const, unsigned int, struct sqlencrypt::OnEncryptionError *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x100479370`
- `0x10047ad60`

## callees

- `0x10046da50`
- `0x10047b3ec`
- `0x10047dd74`
- `0x10047e63c`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10047b4b6`
- `KERNEL32!GetLastError` at `0x10047b523`
- `KERNEL32!GetLastError` at `0x10047b5b2`
- `KERNEL32!GetLastError` at `0x10047b4b6`
- `KERNEL32!GetLastError` at `0x10047b523`
- `KERNEL32!GetLastError` at `0x10047b5b2`
- `ADVAPI32!CryptDestroyHash` at `0x10047b65e`
- `ADVAPI32!CryptDestroyHash` at `0x10047b65e`
- `ADVAPI32!CryptSetHashParam` at `0x10047b5e6`
- `ADVAPI32!CryptSetHashParam` at `0x10047b5e6`
- `ADVAPI32!CryptHashData` at `0x10047b601`
- `ADVAPI32!CryptHashData` at `0x10047b615`
- `ADVAPI32!CryptHashData` at `0x10047b628`
- `ADVAPI32!CryptHashData` at `0x10047b63c`
- `ADVAPI32!CryptHashData` at `0x10047b601`
- `ADVAPI32!CryptHashData` at `0x10047b615`
- `ADVAPI32!CryptHashData` at `0x10047b628`
- `ADVAPI32!CryptHashData` at `0x10047b63c`
- `ADVAPI32!CryptCreateHash` at `0x10047b556`
- `ADVAPI32!CryptCreateHash` at `0x10047b556`
- `ADVAPI32!CryptGetHashParam` at `0x10047b654`
- `ADVAPI32!CryptGetHashParam` at `0x10047b654`
- `ADVAPI32!CryptDestroyKey` at `0x10047b565`
- `ADVAPI32!CryptDestroyKey` at `0x10047b667`
- `ADVAPI32!CryptDestroyKey` at `0x10047b565`
- `ADVAPI32!CryptDestroyKey` at `0x10047b667`

## pseudocode

```c
void __fastcall sqlencrypt::AeadAes256cbcSha256::PrepareAuthenticationTag(
        sqlencrypt::AeadAes256cbcSha256 *this,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        unsigned __int8 *const a4,
        DWORD dwDataLen,
        struct sqlencrypt::OnEncryptionError *a6)
{
  struct sqlencrypt::OnEncryptionError *v7; // rbx
  DWORD v9; // r13d
  HCRYPTPROV WinCryptProvider; // rsi
  DWORD LastError; // eax
  HCRYPTKEY inited; // rdi
  DWORD v15; // eax
  DWORD v16; // eax
  unsigned __int8 *v17; // [rsp+28h] [rbp-58h]
  unsigned int v18; // [rsp+30h] [rbp-50h]
  struct sqlencrypt::OnEncryptionError *v19; // [rsp+38h] [rbp-48h]
  DWORD pdwDataLen; // [rsp+40h] [rbp-40h] BYREF
  HCRYPTHASH hHash; // [rsp+48h] [rbp-38h] BYREF
  BYTE pbData[8]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v23; // [rsp+58h] [rbp-28h]
  int v24; // [rsp+60h] [rbp-20h]
  __int64 v25; // [rsp+68h] [rbp-18h]
  int v26; // [rsp+70h] [rbp-10h]
  BYTE v27; // [rsp+B0h] [rbp+30h] BYREF

  v7 = a6;
  v9 = dwDataLen;
  if ( (bidGblFlags & 2) != 0 && off_1005E6EA8[0] )
  {
    v19 = a6;
    v18 = dwDataLen;
    v17 = a4;
    bidTraceW(0, 1072128, off_1005E6EA8[0], a2);
  }
  v27 = 1;
  WinCryptProvider = sqlencrypt::SqlSecurityUtility::GetWinCryptProvider();
  if ( !WinCryptProvider )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E6EB0[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, unsigned __int8 *, unsigned int, struct sqlencrypt::OnEncryptionError *))off_1005D39E0[0])(
        bidID,
        0,
        1102848,
        off_1005E6EB0[0],
        0,
        v17,
        v18,
        v19);
    LastError = GetLastError();
    sqlencrypt::AEexceptionUtility::ThrowWinApiException(v7, LastError);
  }
  inited = sqlencrypt::SqlSecurityUtility::InitHMACWithSHA256((const unsigned __int8 *)this + 33, 0x20u);
  if ( !inited )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E6EB8[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, unsigned __int8 *, unsigned int, struct sqlencrypt::OnEncryptionError *))off_1005D39E0[0])(
        bidID,
        0,
        1110016,
        off_1005E6EB8[0],
        0,
        v17,
        v18,
        v19);
    v15 = GetLastError();
    sqlencrypt::AEexceptionUtility::ThrowWinApiException(v7, v15);
  }
  hHash = 0;
  pdwDataLen = 32;
  if ( !CryptCreateHash(WinCryptProvider, 0x8009u, inited, 0, &hHash) )
  {
    CryptDestroyKey(inited);
    if ( (bidGblFlags & 2) != 0 && off_1005E6EC0[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, unsigned __int8 *, unsigned int, struct sqlencrypt::OnEncryptionError *, DWORD))off_1005D39E0[0])(
        bidID,
        0,
        1118208,
        off_1005E6EC0[0],
        0,
        v17,
        v18,
        v19,
        pdwDataLen);
    v16 = GetLastError();
    sqlencrypt::AEexceptionUtility::ThrowWinApiException(v7, v16);
  }
  *(_DWORD *)pbData = 32780;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  CryptSetHashParam(hHash, 5u, pbData, 0);
  CryptHashData(hHash, &sqlencrypt::AeadAes256cbcSha256::ALGORITHM_VERSION, 1u, 0);
  CryptHashData(hHash, a3, 0x10u, 0);
  CryptHashData(hHash, a4, v9, 0);
  CryptHashData(hHash, &v27, 1u, 0);
  CryptGetHashParam(hHash, 2u, a2, &pdwDataLen, 0);
  CryptDestroyHash(hHash);
  CryptDestroyKey(inited);
}

```

## disassembly

```asm
0x10047b3ec  mov     r11, rsp
0x10047b3ef  mov     [r11+10h], rbx
0x10047b3f3  mov     [r11+18h], rsi
0x10047b3f7  mov     [r11+20h], rdi
0x10047b3fb  push    rbp
0x10047b3fc  push    r12
0x10047b3fe  push    r13
0x10047b400  push    r14
0x10047b402  push    r15
0x10047b404  mov     rbp, rsp
0x10047b407  sub     rsp, 80h
0x10047b40e  test    byte ptr cs:_bidGblFlags, 2
0x10047b415  mov     r14, r9
0x10047b418  mov     rbx, [rbp+arg_28]
0x10047b41c  mov     r15, r8
0x10047b41f  mov     r13d, [rbp+dwDataLen]
0x10047b423  mov     r12, rdx
0x10047b426  mov     rdi, rcx
0x10047b429  jz      short loc_10047B45E
0x10047b42b  mov     rax, cs:off_1005E6EA8; "<sqlencrypt::AeadAes256cbcSha256::Prepa"...
0x10047b432  test    rax, rax
0x10047b435  jz      short loc_10047B45E
0x10047b437  mov     [r11-70h], rbx
0x10047b43b  xor     ecx, ecx
0x10047b43d  mov     [r11-78h], r13d
0x10047b441  mov     [r11-80h], r9
0x10047b445  mov     r9, rdx
0x10047b448  mov     [rsp+80h+phHash], r8
0x10047b44d  mov     edx, 105C00h
0x10047b452  mov     r8, cs:off_1005E6EA8; "<sqlencrypt::AeadAes256cbcSha256::Prepa"...
0x10047b459  call    _bidTraceW
0x10047b45e  mov     [rbp+arg_0], 1
0x10047b462  call    ?GetWinCryptProvider@SqlSecurityUtility@sqlencrypt@@SA_KXZ; sqlencrypt::SqlSecurityUtility::GetWinCryptProvider(void)
0x10047b467  mov     rsi, rax
0x10047b46a  test    rax, rax
0x10047b46d  jnz     short loc_10047B4C6
0x10047b46f  test    byte ptr cs:_bidGblFlags, 2
0x10047b476  jz      short loc_10047B4B6
0x10047b478  mov     rcx, cs:off_1005E6EB0; "<sqlencrypt::AeadAes256cbcSha256::Prepa"...
0x10047b47f  test    rcx, rcx
0x10047b482  jz      short loc_10047B4B6
0x10047b484  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10047b48c  jz      short loc_10047B4B6
0x10047b48e  mov     r9, cs:off_1005E6EB0; "<sqlencrypt::AeadAes256cbcSha256::Prepa"...
0x10047b495  xor     edx, edx
0x10047b497  mov     rcx, cs:_bidID
0x10047b49e  mov     r8d, 10D400h
0x10047b4a4  mov     rax, cs:off_1005D39E0
0x10047b4ab  and     [rsp+80h+phHash], rsi
0x10047b4b0  call    cs:__guard_dispatch_icall_fptr
0x10047b4b6  call    cs:__imp_GetLastError
0x10047b4bc  mov     edx, eax; unsigned int
0x10047b4be  mov     rcx, rbx; struct sqlencrypt::OnEncryptionError *
0x10047b4c1  call    ?ThrowWinApiException@AEexceptionUtility@sqlencrypt@@SAXPEAUOnEncryptionError@2@K@Z; sqlencrypt::AEexceptionUtility::ThrowWinApiException(sqlencrypt::OnEncryptionError *,ulong)
0x10047b4c6  lea     rcx, [rdi+21h]; Source
0x10047b4ca  mov     edx, 20h ; ' '; SourceSize
0x10047b4cf  call    ?InitHMACWithSHA256@SqlSecurityUtility@sqlencrypt@@SA_KPEBE_K@Z; sqlencrypt::SqlSecurityUtility::InitHMACWithSHA256(uchar const *,unsigned __int64)
0x10047b4d4  mov     rdi, rax
0x10047b4d7  test    rax, rax
0x10047b4da  jnz     short loc_10047B533
0x10047b4dc  test    byte ptr cs:_bidGblFlags, 2
0x10047b4e3  jz      short loc_10047B523
0x10047b4e5  mov     rcx, cs:off_1005E6EB8; "<sqlencrypt::AeadAes256cbcSha256::Prepa"...
0x10047b4ec  test    rcx, rcx
0x10047b4ef  jz      short loc_10047B523
0x10047b4f1  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10047b4f9  jz      short loc_10047B523
0x10047b4fb  mov     r9, cs:off_1005E6EB8; "<sqlencrypt::AeadAes256cbcSha256::Prepa"...
0x10047b502  xor     edx, edx
0x10047b504  mov     rcx, cs:_bidID
0x10047b50b  mov     r8d, 10F000h
0x10047b511  mov     rax, cs:off_1005D39E0
0x10047b518  and     [rsp+80h+phHash], rdi
0x10047b51d  call    cs:__guard_dispatch_icall_fptr
0x10047b523  call    cs:__imp_GetLastError
0x10047b529  mov     edx, eax; unsigned int
0x10047b52b  mov     rcx, rbx; struct sqlencrypt::OnEncryptionError *
0x10047b52e  call    ?ThrowWinApiException@AEexceptionUtility@sqlencrypt@@SAXPEAUOnEncryptionError@2@K@Z; sqlencrypt::AEexceptionUtility::ThrowWinApiException(sqlencrypt::OnEncryptionError *,ulong)
0x10047b533  and     [rbp+hHash], 0
0x10047b538  lea     rax, [rbp+hHash]
0x10047b53c  xor     r9d, r9d; dwFlags
0x10047b53f  mov     [rsp+80h+phHash], rax; phHash
0x10047b544  mov     r8, rdi; hKey
0x10047b547  mov     [rbp+pdwDataLen], 20h ; ' '
0x10047b54e  mov     edx, 8009h; Algid
0x10047b553  mov     rcx, rsi; hProv
0x10047b556  call    cs:__imp_CryptCreateHash
0x10047b55c  xor     esi, esi
0x10047b55e  test    eax, eax
0x10047b560  jnz     short loc_10047B5C2
0x10047b562  mov     rcx, rdi; hKey
0x10047b565  call    cs:__imp_CryptDestroyKey
0x10047b56b  test    byte ptr cs:_bidGblFlags, 2
0x10047b572  jz      short loc_10047B5B2
0x10047b574  mov     rax, cs:off_1005E6EC0; "<sqlencrypt::AeadAes256cbcSha256::Prepa"...
0x10047b57b  test    rax, rax
0x10047b57e  jz      short loc_10047B5B2
0x10047b580  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10047b588  jz      short loc_10047B5B2
0x10047b58a  mov     r9, cs:off_1005E6EC0; "<sqlencrypt::AeadAes256cbcSha256::Prepa"...
0x10047b591  xor     edx, edx
0x10047b593  mov     rcx, cs:_bidID
0x10047b59a  mov     r8d, 111000h
0x10047b5a0  mov     rax, cs:off_1005D39E0
0x10047b5a7  mov     [rsp+80h+phHash], rsi
0x10047b5ac  call    cs:__guard_dispatch_icall_fptr
0x10047b5b2  call    cs:__imp_GetLastError
0x10047b5b8  mov     edx, eax; unsigned int
0x10047b5ba  mov     rcx, rbx; struct sqlencrypt::OnEncryptionError *
0x10047b5bd  call    ?ThrowWinApiException@AEexceptionUtility@sqlencrypt@@SAXPEAUOnEncryptionError@2@K@Z; sqlencrypt::AEexceptionUtility::ThrowWinApiException(sqlencrypt::OnEncryptionError *,ulong)
0x10047b5c2  mov     rcx, [rbp+hHash]; hHash
0x10047b5c6  lea     r8, [rbp+pbData]; pbData
0x10047b5ca  xor     r9d, r9d; dwFlags
0x10047b5cd  mov     dword ptr [rbp+pbData], 800Ch
0x10047b5d4  mov     [rbp+var_28], rsi
0x10047b5d8  mov     [rbp+var_20], esi
0x10047b5db  mov     [rbp+var_18], rsi
0x10047b5df  lea     edx, [r9+5]; dwParam
0x10047b5e3  mov     [rbp+var_10], esi
0x10047b5e6  call    cs:__imp_CryptSetHashParam
0x10047b5ec  mov     rcx, [rbp+hHash]; hHash
0x10047b5f0  lea     rdx, ?ALGORITHM_VERSION@AeadAes256cbcSha256@sqlencrypt@@0EB; pbData
0x10047b5f7  xor     r9d, r9d; dwFlags
0x10047b5fa  lea     ebx, [r9+1]
0x10047b5fe  mov     r8d, ebx; dwDataLen
0x10047b601  call    cs:__imp_CryptHashData
0x10047b607  mov     rcx, [rbp+hHash]; hHash
0x10047b60b  lea     r8d, [rbx+0Fh]; dwDataLen
0x10047b60f  xor     r9d, r9d; dwFlags
0x10047b612  mov     rdx, r15; pbData
0x10047b615  call    cs:__imp_CryptHashData
0x10047b61b  mov     rcx, [rbp+hHash]; hHash
0x10047b61f  xor     r9d, r9d; dwFlags
0x10047b622  mov     r8d, r13d; dwDataLen
0x10047b625  mov     rdx, r14; pbData
0x10047b628  call    cs:__imp_CryptHashData
0x10047b62e  mov     rcx, [rbp+hHash]; hHash
0x10047b632  lea     rdx, [rbp+arg_0]; pbData
0x10047b636  xor     r9d, r9d; dwFlags
0x10047b639  mov     r8d, ebx; dwDataLen
0x10047b63c  call    cs:__imp_CryptHashData
0x10047b642  mov     rcx, [rbp+hHash]; hHash
0x10047b646  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x10047b64a  mov     r8, r12; pbData
0x10047b64d  mov     dword ptr [rsp+80h+phHash], esi; dwFlags
0x10047b651  lea     edx, [rbx+1]; dwParam
0x10047b654  call    cs:__imp_CryptGetHashParam
0x10047b65a  mov     rcx, [rbp+hHash]; hHash
0x10047b65e  call    cs:__imp_CryptDestroyHash
0x10047b664  mov     rcx, rdi; hKey
0x10047b667  call    cs:__imp_CryptDestroyKey
0x10047b66d  lea     r11, [rsp+80h+var_s0]
0x10047b675  mov     rbx, [r11+38h]
0x10047b679  mov     rsi, [r11+40h]
0x10047b67d  mov     rdi, [r11+48h]
0x10047b681  mov     rsp, r11
0x10047b684  pop     r15
0x10047b686  pop     r14
0x10047b688  pop     r13
0x10047b68a  pop     r12
0x10047b68c  pop     rbp
0x10047b68d  retn
```
