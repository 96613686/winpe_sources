# CryptoHashString(unsigned __int64,ushort const *,tagSHA_HASH *)

- ea: `0x180082e1c`
- end: `0x180082f2e`
- name: `?CryptoHashString@@YAJ_KPEBGPEAUtagSHA_HASH@@@Z`
- size: `274`
- prototype: `int(unsigned __int64, const unsigned __int16 *, struct tagSHA_HASH *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180022dbc`

## callees

- `0x180082e1c`

## import_xrefs

- `CRYPTSP!CryptReleaseContext` at `0x180082f15`
- `CRYPTSP!CryptReleaseContext` at `0x180082f15`
- `CRYPTSP!CryptDestroyHash` at `0x180082f05`
- `CRYPTSP!CryptDestroyHash` at `0x180082f05`
- `CRYPTSP!CryptGetHashParam` at `0x180082ef5`
- `CRYPTSP!CryptGetHashParam` at `0x180082ef5`
- `CRYPTSP!CryptAcquireContextW` at `0x180082e6a`
- `CRYPTSP!CryptAcquireContextW` at `0x180082e6a`
- `CRYPTSP!CryptHashData` at `0x180082ecf`
- `CRYPTSP!CryptHashData` at `0x180082ecf`
- `CRYPTSP!CryptCreateHash` at `0x180082ea5`
- `CRYPTSP!CryptCreateHash` at `0x180082ea5`

## pseudocode

```c
__int64 __fastcall CryptoHashString(__int64 a1, const BYTE *a2, struct tagSHA_HASH *a3)
{
  int v4; // edi
  unsigned int v6; // ebx
  HCRYPTPROV v7; // rcx
  __int64 v8; // r8
  __int64 pdwDataLen; // [rsp+60h] [rbp+30h] BYREF
  HCRYPTHASH phHash; // [rsp+70h] [rbp+40h] BYREF
  HCRYPTPROV phProv; // [rsp+78h] [rbp+48h] BYREF

  pdwDataLen = a1;
  *(_OWORD *)a3 = 0;
  *((_DWORD *)a3 + 4) = 0;
  v4 = 1;
  phProv = 0;
  v6 = -2147467259;
  if ( CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000) )
  {
    v7 = phProv;
  }
  else
  {
    v7 = 0;
    v4 = 0;
    phProv = 0;
  }
  if ( v7 )
  {
    phHash = 0;
    if ( CryptCreateHash(v7, 0x8004u, 0, 0, &phHash) )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&a2[2 * v8] );
      if ( CryptHashData(phHash, a2, 2 * v8 + 2, 0) )
      {
        LODWORD(pdwDataLen) = 20;
        if ( CryptGetHashParam(phHash, 2u, (BYTE *)a3, (DWORD *)&pdwDataLen, 0) )
          v6 = 0;
      }
      CryptDestroyHash(phHash);
    }
    if ( v4 )
      CryptReleaseContext(phProv, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x180082e1c  mov     [rsp-28h+arg_8], rbx
0x180082e21  mov     [rsp-28h+pdwDataLen], rcx
0x180082e26  push    rbp
0x180082e27  push    rsi
0x180082e28  push    rdi
0x180082e29  push    r14
0x180082e2b  push    r15
0x180082e2d  mov     rbp, rsp
0x180082e30  sub     rsp, 30h
0x180082e34  xor     eax, eax
0x180082e36  mov     [rsp+30h+dwFlags], 0F0000000h; dwFlags
0x180082e3e  xorps   xmm0, xmm0
0x180082e41  lea     rcx, [rbp+phProv]; phProv
0x180082e45  movups  xmmword ptr [r8], xmm0
0x180082e49  mov     r14, r8
0x180082e4c  mov     [r8+10h], eax
0x180082e50  lea     edi, [rax+1]
0x180082e53  mov     rsi, rdx
0x180082e56  xor     r15d, r15d
0x180082e59  mov     r9d, edi; dwProvType
0x180082e5c  xor     r8d, r8d; szProvider
0x180082e5f  mov     [rbp+phProv], r15
0x180082e63  xor     edx, edx; szContainer
0x180082e65  mov     ebx, 80004005h
0x180082e6a  call    cs:__imp_CryptAcquireContextW
0x180082e70  test    eax, eax
0x180082e72  jz      short loc_180082E7A
0x180082e74  mov     rcx, [rbp+phProv]
0x180082e78  jmp     short loc_180082E84
0x180082e7a  mov     rcx, r15; hProv
0x180082e7d  mov     edi, r15d
0x180082e80  mov     [rbp+phProv], rcx
0x180082e84  test    rcx, rcx
0x180082e87  jz      loc_180082F1B
0x180082e8d  lea     rax, [rbp+phHash]
0x180082e91  mov     [rbp+phHash], r15
0x180082e95  xor     r9d, r9d; dwFlags
0x180082e98  mov     qword ptr [rsp+30h+dwFlags], rax; phHash
0x180082e9d  xor     r8d, r8d; hKey
0x180082ea0  mov     edx, 8004h; Algid
0x180082ea5  call    cs:__imp_CryptCreateHash
0x180082eab  test    eax, eax
0x180082ead  jz      short loc_180082F0B
0x180082eaf  or      r8, 0FFFFFFFFFFFFFFFFh
0x180082eb3  inc     r8
0x180082eb6  cmp     [rsi+r8*2], r15w
0x180082ebb  jnz     short loc_180082EB3
0x180082ebd  mov     rcx, [rbp+phHash]; hHash
0x180082ec1  lea     r8d, ds:2[r8*2]; dwDataLen
0x180082ec9  xor     r9d, r9d; dwFlags
0x180082ecc  mov     rdx, rsi; pbData
0x180082ecf  call    cs:__imp_CryptHashData
0x180082ed5  test    eax, eax
0x180082ed7  jz      short loc_180082F01
0x180082ed9  mov     rcx, [rbp+phHash]; hHash
0x180082edd  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180082ee1  mov     r8, r14; pbData
0x180082ee4  mov     dword ptr [rbp+pdwDataLen], 14h
0x180082eeb  mov     edx, 2; dwParam
0x180082ef0  mov     [rsp+30h+dwFlags], r15d; dwFlags
0x180082ef5  call    cs:__imp_CryptGetHashParam
0x180082efb  test    eax, eax
0x180082efd  cmovnz  ebx, r15d
0x180082f01  mov     rcx, [rbp+phHash]; hHash
0x180082f05  call    cs:__imp_CryptDestroyHash
0x180082f0b  test    edi, edi
0x180082f0d  jz      short loc_180082F1B
0x180082f0f  mov     rcx, [rbp+phProv]; hProv
0x180082f13  xor     edx, edx; dwFlags
0x180082f15  call    cs:__imp_CryptReleaseContext
0x180082f1b  mov     eax, ebx
0x180082f1d  mov     rbx, [rsp+30h+arg_8]
0x180082f22  add     rsp, 30h
0x180082f26  pop     r15
0x180082f28  pop     r14
0x180082f2a  pop     rdi
0x180082f2b  pop     rsi
0x180082f2c  pop     rbp
0x180082f2d  retn
```
