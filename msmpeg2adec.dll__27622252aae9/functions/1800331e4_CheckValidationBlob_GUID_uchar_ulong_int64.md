# CheckValidationBlob(_GUID,uchar *,ulong,__int64)

- ea: `0x1800331e4`
- end: `0x180033509`
- name: `?CheckValidationBlob@@YAJU_GUID@@PEAEK_J@Z`
- size: `805`
- prototype: `int(struct _GUID *__struct_ptr, unsigned __int8 *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180033510`

## callees

- `0x1800331e4`
- `0x1800886f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033489`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800333a8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800334ad`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800333a8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800334ad`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x180033301`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x1800333fb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x180033301`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptImportKey` at `0x1800333fb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800334d9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800334d9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180033351`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180033443`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180033351`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180033443`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18003332d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180033423`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18003332d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180033423`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180033284`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800332c8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180033284`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800332c8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x1800333c5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x1800334c2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x1800333c5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x1800334c2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptVerifySignatureW` at `0x18003338b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptVerifySignatureW` at `0x180033479`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptVerifySignatureW` at `0x18003338b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptVerifySignatureW` at `0x180033479`

## pseudocode

```c
__int64 __fastcall CheckValidationBlob(struct _GUID *a1, unsigned __int8 *a2, unsigned int a3, __int64 a4)
{
  signed int v6; // ebx
  signed int LastError; // eax
  HCRYPTKEY hPubKey; // [rsp+30h] [rbp-20h] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-18h] BYREF
  __int128 Buf2; // [rsp+40h] [rbp-10h] BYREF
  HCRYPTHASH phHash; // [rsp+68h] [rbp+18h] BYREF

  phProv = 0;
  hPubKey = 0;
  phHash = 0;
  if ( a2 )
  {
    if ( a3 >= 4 )
    {
      Buf2 = *(_OWORD *)(a2 + 40);
      if ( a3 == 472 )
      {
        if ( *((_DWORD *)a2 + 1) != 2 || memcmp_0(a1, &Buf2, 0x10u) || *((_QWORD *)a2 + 42) != a4 )
          return (unsigned int)-2147467259;
        v6 = 0;
        if ( CryptAcquireContextW(
               &phProv,
               0,
               L"Microsoft Enhanced RSA and AES Cryptographic Provider",
               0x18u,
               0xF0000000) )
        {
          goto LABEL_38;
        }
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError != -2146893802 )
          goto LABEL_24;
        if ( CryptAcquireContextW(
               &phProv,
               0,
               L"Microsoft Enhanced RSA and AES Cryptographic Provider",
               0x18u,
               0xF0000008) )
        {
LABEL_38:
          if ( CryptImportKey(phProv, &pbData, 0x94u, 0, 0, &hPubKey)
            && CryptCreateHash(phProv, 0x800Eu, 0, 0, &phHash)
            && CryptHashData(phHash, a2, 0xD0u, 0)
            && CryptVerifySignatureW(phHash, a2 + 208, 0x80u, hPubKey, 0, 0) )
          {
            if ( phHash )
            {
              CryptDestroyHash(phHash);
              phHash = 0;
            }
            if ( hPubKey )
            {
              CryptDestroyKey(hPubKey);
              hPubKey = 0;
            }
            if ( CryptImportKey(phProv, a2 + 56, 0x98u, 0, 0, &hPubKey)
              && CryptCreateHash(phProv, 0x800Eu, 0, 0, &phHash)
              && CryptHashData(phHash, a2, 0x158u, 0)
              && CryptVerifySignatureW(phHash, a2 + 344, 0x80u, hPubKey, 0, 0) )
            {
              goto LABEL_26;
            }
          }
        }
        LastError = GetLastError();
        v6 = LastError;
LABEL_24:
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_26:
        if ( phHash )
          CryptDestroyHash(phHash);
        if ( hPubKey )
          CryptDestroyKey(hPubKey);
        if ( phProv )
          CryptReleaseContext(phProv, 0);
        if ( v6 >= 0 )
          return 3;
        return (unsigned int)v6;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800331e4  mov     [rsp-8+arg_0], rbx
0x1800331e9  mov     [rsp-8+arg_10], rdi
0x1800331ee  push    rbp
0x1800331ef  mov     rbp, rsp
0x1800331f2  sub     rsp, 50h
0x1800331f6  mov     [rbp+phProv], 0
0x1800331fe  mov     rbx, r9
0x180033201  mov     [rbp+hPubKey], 0
0x180033209  mov     rdi, rdx
0x18003320c  mov     [rbp+phHash], 0
0x180033214  test    rdx, rdx
0x180033217  jz      loc_1800334F3
0x18003321d  cmp     r8d, 4
0x180033221  jb      loc_1800334F3
0x180033227  movups  xmm0, xmmword ptr [rdx+28h]
0x18003322b  movdqu  [rbp+Buf2], xmm0
0x180033230  cmp     r8d, 1D8h
0x180033237  jnz     loc_1800334F3
0x18003323d  cmp     dword ptr [rdx+4], 2
0x180033241  jz      short loc_18003324D
0x180033243  mov     ebx, 80004005h
0x180033248  jmp     loc_1800334EF
0x18003324d  mov     r8d, 10h; Size
0x180033253  lea     rdx, [rbp+Buf2]; Buf2
0x180033257  call    memcmp_0
0x18003325c  test    eax, eax
0x18003325e  jnz     short loc_180033243
0x180033260  cmp     [rdi+150h], rbx
0x180033267  jnz     short loc_180033243
0x180033269  lea     r9d, [rax+18h]; dwProvType
0x18003326d  mov     [rsp+50h+dwFlags], 0F0000000h; dwFlags
0x180033275  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18003327c  xor     edx, edx; szContainer
0x18003327e  lea     rcx, [rbp+phProv]; phProv
0x180033282  xor     ebx, ebx
0x180033284  call    cs:__imp_CryptAcquireContextW
0x18003328b  nop     dword ptr [rax+rax+00h]
0x180033290  test    eax, eax
0x180033292  jnz     short loc_1800332DC
0x180033294  call    cs:__imp_GetLastError
0x18003329b  nop     dword ptr [rax+rax+00h]
0x1800332a0  mov     ebx, eax
0x1800332a2  cmp     eax, 80090016h
0x1800332a7  jnz     loc_180033497
0x1800332ad  mov     r9d, 18h; dwProvType
0x1800332b3  mov     [rsp+50h+dwFlags], 0F0000008h; dwFlags
0x1800332bb  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x1800332c2  xor     edx, edx; szContainer
0x1800332c4  lea     rcx, [rbp+phProv]; phProv
0x1800332c8  call    cs:__imp_CryptAcquireContextW
0x1800332cf  nop     dword ptr [rax+rax+00h]
0x1800332d4  test    eax, eax
0x1800332d6  jz      loc_180033489
0x1800332dc  mov     rcx, [rbp+phProv]; hProv
0x1800332e0  lea     rax, [rbp+hPubKey]
0x1800332e4  mov     [rsp+50h+phKey], rax; phKey
0x1800332e9  lea     rdx, pbData; pbData
0x1800332f0  xor     r9d, r9d; hPubKey
0x1800332f3  mov     [rsp+50h+dwFlags], 0; dwFlags
0x1800332fb  mov     r8d, 94h; dwDataLen
0x180033301  call    cs:__imp_CryptImportKey
0x180033308  nop     dword ptr [rax+rax+00h]
0x18003330d  test    eax, eax
0x18003330f  jz      loc_180033489
0x180033315  mov     rcx, [rbp+phProv]; hProv
0x180033319  lea     rax, [rbp+phHash]
0x18003331d  xor     r9d, r9d; dwFlags
0x180033320  mov     qword ptr [rsp+50h+dwFlags], rax; phHash
0x180033325  xor     r8d, r8d; hKey
0x180033328  mov     edx, 800Eh; Algid
0x18003332d  call    cs:__imp_CryptCreateHash
0x180033334  nop     dword ptr [rax+rax+00h]
0x180033339  test    eax, eax
0x18003333b  jz      loc_180033489
0x180033341  mov     rcx, [rbp+phHash]; hHash
0x180033345  xor     r9d, r9d; dwFlags
0x180033348  mov     r8d, 0D0h; dwDataLen
0x18003334e  mov     rdx, rdi; pbData
0x180033351  call    cs:__imp_CryptHashData
0x180033358  nop     dword ptr [rax+rax+00h]
0x18003335d  test    eax, eax
0x18003335f  jz      loc_180033489
0x180033365  mov     r9, [rbp+hPubKey]; hPubKey
0x180033369  lea     rdx, [rdi+0D0h]; pbSignature
0x180033370  mov     rcx, [rbp+phHash]; hHash
0x180033374  mov     r8d, 80h; dwSigLen
0x18003337a  mov     dword ptr [rsp+50h+phKey], 0; dwFlags
0x180033382  mov     qword ptr [rsp+50h+dwFlags], 0; szDescription
0x18003338b  call    cs:__imp_CryptVerifySignatureW
0x180033392  nop     dword ptr [rax+rax+00h]
0x180033397  test    eax, eax
0x180033399  jz      loc_180033489
0x18003339f  mov     rcx, [rbp+phHash]; hHash
0x1800333a3  test    rcx, rcx
0x1800333a6  jz      short loc_1800333BC
0x1800333a8  call    cs:__imp_CryptDestroyHash
0x1800333af  nop     dword ptr [rax+rax+00h]
0x1800333b4  mov     [rbp+phHash], 0
0x1800333bc  mov     rcx, [rbp+hPubKey]; hKey
0x1800333c0  test    rcx, rcx
0x1800333c3  jz      short loc_1800333D9
0x1800333c5  call    cs:__imp_CryptDestroyKey
0x1800333cc  nop     dword ptr [rax+rax+00h]
0x1800333d1  mov     [rbp+hPubKey], 0
0x1800333d9  mov     rcx, [rbp+phProv]; hProv
0x1800333dd  lea     rax, [rbp+hPubKey]
0x1800333e1  mov     [rsp+50h+phKey], rax; phKey
0x1800333e6  lea     rdx, [rdi+38h]; pbData
0x1800333ea  xor     r9d, r9d; hPubKey
0x1800333ed  mov     [rsp+50h+dwFlags], 0; dwFlags
0x1800333f5  mov     r8d, 98h; dwDataLen
0x1800333fb  call    cs:__imp_CryptImportKey
0x180033402  nop     dword ptr [rax+rax+00h]
0x180033407  test    eax, eax
0x180033409  jz      short loc_180033489
0x18003340b  mov     rcx, [rbp+phProv]; hProv
0x18003340f  lea     rax, [rbp+phHash]
0x180033413  xor     r9d, r9d; dwFlags
0x180033416  mov     qword ptr [rsp+50h+dwFlags], rax; phHash
0x18003341b  xor     r8d, r8d; hKey
0x18003341e  mov     edx, 800Eh; Algid
0x180033423  call    cs:__imp_CryptCreateHash
0x18003342a  nop     dword ptr [rax+rax+00h]
0x18003342f  test    eax, eax
0x180033431  jz      short loc_180033489
0x180033433  mov     rcx, [rbp+phHash]; hHash
0x180033437  xor     r9d, r9d; dwFlags
0x18003343a  mov     r8d, 158h; dwDataLen
0x180033440  mov     rdx, rdi; pbData
0x180033443  call    cs:__imp_CryptHashData
0x18003344a  nop     dword ptr [rax+rax+00h]
0x18003344f  test    eax, eax
0x180033451  jz      short loc_180033489
0x180033453  mov     r9, [rbp+hPubKey]; hPubKey
0x180033457  lea     rdx, [rdi+158h]; pbSignature
0x18003345e  mov     rcx, [rbp+phHash]; hHash
0x180033462  mov     r8d, 80h; dwSigLen
0x180033468  mov     dword ptr [rsp+50h+phKey], 0; dwFlags
0x180033470  mov     qword ptr [rsp+50h+dwFlags], 0; szDescription
0x180033479  call    cs:__imp_CryptVerifySignatureW
0x180033480  nop     dword ptr [rax+rax+00h]
0x180033485  test    eax, eax
0x180033487  jnz     short loc_1800334A4
0x180033489  call    cs:__imp_GetLastError
0x180033490  nop     dword ptr [rax+rax+00h]
0x180033495  mov     ebx, eax
0x180033497  test    eax, eax
0x180033499  jle     short loc_1800334A4
0x18003349b  movzx   ebx, ax
0x18003349e  or      ebx, 80070000h
0x1800334a4  mov     rcx, [rbp+phHash]; hHash
0x1800334a8  test    rcx, rcx
0x1800334ab  jz      short loc_1800334B9
0x1800334ad  call    cs:__imp_CryptDestroyHash
0x1800334b4  nop     dword ptr [rax+rax+00h]
0x1800334b9  mov     rcx, [rbp+hPubKey]; hKey
0x1800334bd  test    rcx, rcx
0x1800334c0  jz      short loc_1800334CE
0x1800334c2  call    cs:__imp_CryptDestroyKey
0x1800334c9  nop     dword ptr [rax+rax+00h]
0x1800334ce  mov     rcx, [rbp+phProv]; hProv
0x1800334d2  test    rcx, rcx
0x1800334d5  jz      short loc_1800334E5
0x1800334d7  xor     edx, edx; dwFlags
0x1800334d9  call    cs:__imp_CryptReleaseContext
0x1800334e0  nop     dword ptr [rax+rax+00h]
0x1800334e5  test    ebx, ebx
0x1800334e7  mov     eax, 3
0x1800334ec  cmovns  ebx, eax
0x1800334ef  mov     eax, ebx
0x1800334f1  jmp     short loc_1800334F8
0x1800334f3  mov     eax, 80070057h
0x1800334f8  mov     rbx, [rsp+50h+arg_0]
0x1800334fd  mov     rdi, [rsp+50h+arg_10]
0x180033502  add     rsp, 50h
0x180033506  pop     rbp
0x180033507  retn
```
