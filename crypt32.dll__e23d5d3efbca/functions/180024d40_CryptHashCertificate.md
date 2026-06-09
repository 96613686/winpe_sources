# CryptHashCertificate

- ea: `0x180024d40`
- end: `0x180024ffa`
- name: `CryptHashCertificate`
- size: `698`
- prototype: `BOOL __stdcall(HCRYPTPROV_LEGACY hCryptProv, ALG_ID Algid, DWORD dwFlags, const BYTE *pbEncoded, DWORD cbEncoded, BYTE *pbComputedHash, DWORD *pcbComputedHash)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800147bc`
- `0x180024a70`
- `0x180050d70`
- `0x18005f450`
- `0x180060108`
- `0x180060a18`
- `0x1800a1220`
- `0x1800a47bc`
- `0x1800a626c`
- `0x1800b9034`
- `0x1800e3414`
- `0x1800f0f60`
- `0x1800f31f8`

## callees

- `0x180024d40`
- `0x180027460`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024f97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024fc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024f97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024fc4`
- `bcrypt!BCryptFinishHash` at `0x180024e2e`
- `bcrypt!BCryptFinishHash` at `0x180024f0c`
- `bcrypt!BCryptFinishHash` at `0x180024e2e`
- `bcrypt!BCryptFinishHash` at `0x180024f0c`
- `bcrypt!BCryptDestroyHash` at `0x180024e40`
- `bcrypt!BCryptDestroyHash` at `0x180024ef4`
- `bcrypt!BCryptDestroyHash` at `0x180024e40`
- `bcrypt!BCryptDestroyHash` at `0x180024ef4`
- `bcrypt!BCryptHashData` at `0x180024e12`
- `bcrypt!BCryptHashData` at `0x180024edc`
- `bcrypt!BCryptHashData` at `0x180024e12`
- `bcrypt!BCryptHashData` at `0x180024edc`
- `bcrypt!BCryptCreateHash` at `0x180024dee`
- `bcrypt!BCryptCreateHash` at `0x180024eb8`
- `bcrypt!BCryptCreateHash` at `0x180024dee`
- `bcrypt!BCryptCreateHash` at `0x180024eb8`
- `CRYPTSP!CryptHashData` at `0x180024f55`
- `CRYPTSP!CryptHashData` at `0x180024f55`
- `CRYPTSP!CryptGetHashParam` at `0x180024f76`
- `CRYPTSP!CryptGetHashParam` at `0x180024f76`
- `CRYPTSP!CryptDestroyHash` at `0x180024f8f`
- `CRYPTSP!CryptDestroyHash` at `0x180024f8f`
- `CRYPTSP!CryptCreateHash` at `0x180024f3d`
- `CRYPTSP!CryptCreateHash` at `0x180024f3d`

## pseudocode

```c
BOOL __stdcall CryptHashCertificate(
        HCRYPTPROV_LEGACY hCryptProv,
        ALG_ID Algid,
        DWORD dwFlags,
        const BYTE *pbEncoded,
        DWORD cbEncoded,
        BYTE *pbComputedHash,
        DWORD *pcbComputedHash)
{
  ALG_ID v7; // ebx
  DWORD v9; // edi
  BOOL v10; // r15d
  DWORD v11; // eax
  DWORD v12; // ebx
  BOOL HashParam; // ebx
  DWORD LastError; // edi
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-30h] BYREF
  HCRYPTHASH v17; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h]

  v7 = 32772;
  v17 = 0;
  v9 = Algid != 0 ? dwFlags : 0;
  if ( Algid )
    v7 = Algid;
  if ( !hCryptProv )
  {
    v10 = 1;
    if ( v7 - 32771 <= 1 )
    {
      if ( pbComputedHash )
        v11 = *pcbComputedHash;
      else
        v11 = 0;
      if ( v7 == 32771 )
      {
        v12 = 16;
        if ( v11 >= 0x10 )
        {
          v19 = 0;
          *(_OWORD *)phHash = 0;
          if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
            __fastfail(7u);
          if ( cbEncoded && BCryptHashData(phHash[0], (PUCHAR)pbEncoded, cbEncoded, 0) < 0 )
            __fastfail(7u);
          if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
            __fastfail(7u);
          BCryptDestroyHash(phHash[0]);
          *(BCRYPT_HASH_HANDLE *)pbComputedHash = phHash[1];
          *((_QWORD *)pbComputedHash + 1) = v19;
LABEL_14:
          *pcbComputedHash = v12;
          return v10;
        }
      }
      else
      {
        v12 = 20;
        if ( v11 >= 0x14 )
        {
          hHash = 0;
          if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &hHash, 0, 0, 0, 0, 0) < 0 )
            __fastfail(7u);
          if ( cbEncoded && BCryptHashData(hHash, (PUCHAR)pbEncoded, cbEncoded, 0) < 0 )
            __fastfail(7u);
          if ( pbComputedHash && BCryptFinishHash(hHash, pbComputedHash, 0x14u, 0) < 0 )
            __fastfail(7u);
          BCryptDestroyHash(hHash);
          goto LABEL_14;
        }
      }
      *pcbComputedHash = v12;
      if ( v11 < v12 && pbComputedHash )
      {
        SetLastError(0xEAu);
        return 0;
      }
      return v10;
    }
    hCryptProv = I_CryptGetDefaultCryptProv(0);
    if ( !hCryptProv )
      goto LABEL_33;
  }
  if ( CryptCreateHash(hCryptProv, v7, 0, v9, &v17) && CryptHashData(v17, pbEncoded, cbEncoded, 0) )
  {
    HashParam = CryptGetHashParam(v17, 2u, pbComputedHash, pcbComputedHash, 0);
  }
  else
  {
LABEL_33:
    HashParam = 0;
    *pcbComputedHash = 0;
  }
  LastError = GetLastError();
  if ( v17 )
    CryptDestroyHash(v17);
  SetLastError(LastError);
  return HashParam;
}

```

## disassembly

```asm
0x180024d40  push    rbp
0x180024d42  push    rbx
0x180024d43  push    rsi
0x180024d44  push    rdi
0x180024d45  push    r12
0x180024d47  push    r14
0x180024d49  push    r15
0x180024d4b  mov     rbp, rsp
0x180024d4e  sub     rsp, 70h
0x180024d52  mov     rax, cs:__security_cookie
0x180024d59  xor     rax, rsp
0x180024d5c  mov     [rbp+var_8], rax
0x180024d60  mov     rsi, [rbp+pbComputedHash]
0x180024d64  mov     eax, edx
0x180024d66  mov     r14, [rbp+pcbComputedHash]
0x180024d6a  neg     eax
0x180024d6c  mov     ebx, 8004h
0x180024d71  mov     [rbp+var_28], 0
0x180024d79  sbb     edi, edi
0x180024d7b  mov     r12, r9
0x180024d7e  and     edi, r8d
0x180024d81  test    edx, edx
0x180024d83  cmovnz  ebx, edx
0x180024d86  test    rcx, rcx
0x180024d89  jnz     loc_180024F2C
0x180024d8f  lea     eax, [rbx-8003h]
0x180024d95  lea     r15d, [rcx+1]
0x180024d99  cmp     eax, r15d
0x180024d9c  ja      loc_180024F1D
0x180024da2  test    rsi, rsi
0x180024da5  jz      loc_180024E76
0x180024dab  mov     eax, [r14]
0x180024dae  cmp     ebx, 8003h
0x180024db4  jnz     loc_180024E7D
0x180024dba  mov     ebx, 10h
0x180024dbf  cmp     eax, ebx
0x180024dc1  jb      loc_180024FAB
0x180024dc7  xor     eax, eax
0x180024dc9  lea     rdx, [rbp+phHash]; phHash
0x180024dcd  mov     [rsp+70h+dwFlags], eax; dwFlags
0x180024dd1  lea     ecx, [rbx+11h]; hAlgorithm
0x180024dd4  xorps   xmm0, xmm0
0x180024dd7  mov     [rsp+70h+cbSecret], eax; cbSecret
0x180024ddb  xor     r9d, r9d; cbHashObject
0x180024dde  mov     [rsp+70h+pbSecret], rax; pbSecret
0x180024de3  xor     r8d, r8d; pbHashObject
0x180024de6  mov     [rbp+var_10], rax
0x180024dea  movups  xmmword ptr [rbp+phHash], xmm0
0x180024dee  call    cs:__imp_BCryptCreateHash
0x180024df4  lea     edi, [rbx-9]
0x180024df7  test    eax, eax
0x180024df9  js      loc_180024FDC
0x180024dff  mov     r8d, [rbp+cbEncoded]; cbInput
0x180024e03  test    r8d, r8d
0x180024e06  jz      short loc_180024E20
0x180024e08  mov     rcx, [rbp+phHash]; hHash
0x180024e0c  xor     r9d, r9d; dwFlags
0x180024e0f  mov     rdx, r12; pbInput
0x180024e12  call    cs:__imp_BCryptHashData
0x180024e18  test    eax, eax
0x180024e1a  js      loc_180024FE6
0x180024e20  mov     rcx, [rbp+phHash]; hHash
0x180024e24  lea     rdx, [rbp+phHash+8]; pbOutput
0x180024e28  xor     r9d, r9d; dwFlags
0x180024e2b  mov     r8d, ebx; cbOutput
0x180024e2e  call    cs:__imp_BCryptFinishHash
0x180024e34  test    eax, eax
0x180024e36  js      loc_180024FF0
0x180024e3c  mov     rcx, [rbp+phHash]; hHash
0x180024e40  call    cs:__imp_BCryptDestroyHash
0x180024e46  mov     rax, [rbp+phHash+8]
0x180024e4a  mov     [rsi], rax
0x180024e4d  mov     rax, [rbp+var_10]
0x180024e51  mov     [rsi+8], rax
0x180024e55  mov     [r14], ebx
0x180024e58  mov     eax, r15d
0x180024e5b  mov     rcx, [rbp+var_8]
0x180024e5f  xor     rcx, rsp; StackCookie
0x180024e62  call    __security_check_cookie
0x180024e67  add     rsp, 70h
0x180024e6b  pop     r15
0x180024e6d  pop     r14
0x180024e6f  pop     r12
0x180024e71  pop     rdi
0x180024e72  pop     rsi
0x180024e73  pop     rbx
0x180024e74  pop     rbp
0x180024e75  retn
0x180024e76  xor     eax, eax
0x180024e78  jmp     loc_180024DAE
0x180024e7d  mov     ebx, 14h
0x180024e82  cmp     eax, ebx
0x180024e84  jb      loc_180024FAB
0x180024e8a  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180024e92  lea     rdx, [rbp+hHash]; phHash
0x180024e96  mov     [rsp+70h+cbSecret], 0; cbSecret
0x180024e9e  lea     ecx, [rbx+1Dh]; hAlgorithm
0x180024ea1  xor     r9d, r9d; cbHashObject
0x180024ea4  mov     [rsp+70h+pbSecret], 0; pbSecret
0x180024ead  xor     r8d, r8d; pbHashObject
0x180024eb0  mov     [rbp+hHash], 0
0x180024eb8  call    cs:__imp_BCryptCreateHash
0x180024ebe  lea     edi, [rbx-0Dh]
0x180024ec1  test    eax, eax
0x180024ec3  js      loc_180024FD2
0x180024ec9  mov     r8d, [rbp+cbEncoded]; cbInput
0x180024ecd  test    r8d, r8d
0x180024ed0  jz      short loc_180024EEB
0x180024ed2  mov     rcx, [rbp+hHash]; hHash
0x180024ed6  xor     r9d, r9d; dwFlags
0x180024ed9  mov     rdx, r12; pbInput
0x180024edc  call    cs:__imp_BCryptHashData
0x180024ee2  test    eax, eax
0x180024ee4  jns     short loc_180024EEB
0x180024ee6  mov     rcx, rdi
0x180024ee9  int     29h; Win8: RtlFailFast(ecx)
0x180024eeb  test    rsi, rsi
0x180024eee  jnz     short loc_180024EFF
0x180024ef0  mov     rcx, [rbp+hHash]; hHash
0x180024ef4  call    cs:__imp_BCryptDestroyHash
0x180024efa  jmp     loc_180024E55
0x180024eff  mov     rcx, [rbp+hHash]; hHash
0x180024f03  xor     r9d, r9d; dwFlags
0x180024f06  mov     r8d, ebx; cbOutput
0x180024f09  mov     rdx, rsi; pbOutput
0x180024f0c  call    cs:__imp_BCryptFinishHash
0x180024f12  test    eax, eax
0x180024f14  jns     short loc_180024EF0
0x180024f16  mov     rcx, rdi
0x180024f19  int     29h; Win8: RtlFailFast(ecx)
0x180024f1b  jmp     short loc_180024EF0
0x180024f1d  xor     ecx, ecx
0x180024f1f  call    I_CryptGetDefaultCryptProv
0x180024f24  mov     rcx, rax; hProv
0x180024f27  test    rax, rax
0x180024f2a  jz      short loc_180024FA4
0x180024f2c  lea     rax, [rbp+var_28]
0x180024f30  mov     r9d, edi; dwFlags
0x180024f33  xor     r8d, r8d; hKey
0x180024f36  mov     [rsp+70h+pbSecret], rax; phHash
0x180024f3b  mov     edx, ebx; Algid
0x180024f3d  call    cs:__imp_CryptCreateHash
0x180024f43  test    eax, eax
0x180024f45  jz      short loc_180024FA4
0x180024f47  mov     r8d, [rbp+cbEncoded]; dwDataLen
0x180024f4b  xor     r9d, r9d; dwFlags
0x180024f4e  mov     rcx, [rbp+var_28]; hHash
0x180024f52  mov     rdx, r12; pbData
0x180024f55  call    cs:__imp_CryptHashData
0x180024f5b  test    eax, eax
0x180024f5d  jz      short loc_180024FA4
0x180024f5f  mov     rcx, [rbp+var_28]; hHash
0x180024f63  mov     r9, r14; pdwDataLen
0x180024f66  mov     r8, rsi; pbData
0x180024f69  mov     dword ptr [rsp+70h+pbSecret], 0; dwFlags
0x180024f71  mov     edx, 2; dwParam
0x180024f76  call    cs:__imp_CryptGetHashParam
0x180024f7c  mov     ebx, eax
0x180024f7e  call    cs:__imp_GetLastError
0x180024f84  mov     rcx, [rbp+var_28]; hHash
0x180024f88  mov     edi, eax
0x180024f8a  test    rcx, rcx
0x180024f8d  jz      short loc_180024F95
0x180024f8f  call    cs:__imp_CryptDestroyHash
0x180024f95  mov     ecx, edi; dwErrCode
0x180024f97  call    cs:__imp_SetLastError
0x180024f9d  mov     eax, ebx
0x180024f9f  jmp     loc_180024E5B
0x180024fa4  xor     ebx, ebx
0x180024fa6  mov     [r14], ebx
0x180024fa9  jmp     short loc_180024F7E
0x180024fab  mov     [r14], ebx
0x180024fae  cmp     eax, ebx
0x180024fb0  jnb     loc_180024E58
0x180024fb6  test    rsi, rsi
0x180024fb9  jz      loc_180024E58
0x180024fbf  mov     ecx, 0EAh; dwErrCode
0x180024fc4  call    cs:__imp_SetLastError
0x180024fca  xor     r15d, r15d
0x180024fcd  jmp     loc_180024E58
0x180024fd2  mov     rcx, rdi
0x180024fd5  int     29h; Win8: RtlFailFast(ecx)
0x180024fd7  jmp     loc_180024EC9
0x180024fdc  mov     rcx, rdi
0x180024fdf  int     29h; Win8: RtlFailFast(ecx)
0x180024fe1  jmp     loc_180024DFF
0x180024fe6  mov     rcx, rdi
0x180024fe9  int     29h; Win8: RtlFailFast(ecx)
0x180024feb  jmp     loc_180024E20
0x180024ff0  mov     rcx, rdi
0x180024ff3  int     29h; Win8: RtlFailFast(ecx)
0x180024ff5  jmp     loc_180024E3C
```
