# CNG_PROVIDER_ENTRY::CalculateHMAC(ushort const *,uint,BUFFER *,uint)

- ea: `0x180049c40`
- end: `0x180049d54`
- name: `?CalculateHMAC@CNG_PROVIDER_ENTRY@@EEAAJPEBGIPEAVBUFFER@@I@Z`
- size: `276`
- prototype: `int(CNG_PROVIDER_ENTRY *__hidden this, const unsigned __int16 *, unsigned int, struct BUFFER *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180049c40`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180049d41`
- `bcrypt!BCryptDestroyHash` at `0x180049d41`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180049c7e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180049c7e`
- `bcrypt!BCryptHashData` at `0x180049cd7`
- `bcrypt!BCryptHashData` at `0x180049cd7`
- `bcrypt!BCryptFinishHash` at `0x180049d0c`
- `bcrypt!BCryptFinishHash` at `0x180049d0c`
- `bcrypt!BCryptCreateHash` at `0x180049cbd`
- `bcrypt!BCryptCreateHash` at `0x180049cbd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180049d28`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180049d28`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049c92`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049cee`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049c92`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180049cee`

## pseudocode

```c
__int64 __fastcall CNG_PROVIDER_ENTRY::CalculateHMAC(
        CNG_PROVIDER_ENTRY *this,
        UCHAR *a2,
        ULONG a3,
        struct BUFFER *a4,
        unsigned int a5)
{
  NTSTATUS v9; // edi
  UCHAR *pbSecret; // rax
  ULONG v11; // ebx
  unsigned int v12; // edi
  UCHAR *Ptr; // rax
  NTSTATUS v14; // eax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-30h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 8u);
  if ( v9 >= 0 )
  {
    pbSecret = (UCHAR *)BUFFER::QueryPtr((CNG_PROVIDER_ENTRY *)((char *)this + 56));
    v9 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, pbSecret, 0x20u, 0);
    if ( v9 >= 0 )
    {
      v9 = BCryptHashData(phHash, a2, a3, 0);
      if ( v9 >= 0 )
      {
        v11 = *((_DWORD *)this + 83);
        v12 = 0;
        Ptr = (UCHAR *)BUFFER::QueryPtr(a4);
        v14 = BCryptFinishHash(phHash, &Ptr[a5], v11, 0);
        if ( v14 >= 0 )
          goto LABEL_7;
        v9 = v14;
      }
    }
  }
  v12 = v9 | 0x10000000;
LABEL_7:
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v12;
}

```

## disassembly

```asm
0x180049c40  push    rbx
0x180049c42  push    rbp
0x180049c43  push    rsi
0x180049c44  push    rdi
0x180049c45  push    r14
0x180049c47  sub     rsp, 50h
0x180049c4b  mov     r14, r9
0x180049c4e  mov     [rsp+78h+phAlgorithm], 0
0x180049c57  mov     esi, r8d
0x180049c5a  mov     [rsp+78h+phHash], 0
0x180049c63  mov     rbp, rdx
0x180049c66  mov     rbx, rcx
0x180049c69  mov     r9d, 8; dwFlags
0x180049c6f  lea     rdx, pszAlgId; "SHA256"
0x180049c76  xor     r8d, r8d; pszImplementation
0x180049c79  lea     rcx, [rsp+78h+phAlgorithm]; phAlgorithm
0x180049c7e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180049c84  mov     edi, eax
0x180049c86  test    eax, eax
0x180049c88  js      loc_180049D18
0x180049c8e  lea     rcx, [rbx+38h]
0x180049c92  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180049c98  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x180049c9d  lea     rdx, [rsp+78h+phHash]; phHash
0x180049ca2  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180049caa  xor     r9d, r9d; cbHashObject
0x180049cad  mov     [rsp+78h+cbSecret], 20h ; ' '; cbSecret
0x180049cb5  xor     r8d, r8d; pbHashObject
0x180049cb8  mov     [rsp+78h+pbSecret], rax; pbSecret
0x180049cbd  call    cs:__imp_BCryptCreateHash
0x180049cc3  mov     edi, eax
0x180049cc5  test    eax, eax
0x180049cc7  js      short loc_180049D18
0x180049cc9  mov     rcx, [rsp+78h+phHash]; hHash
0x180049cce  xor     r9d, r9d; dwFlags
0x180049cd1  mov     r8d, esi; cbInput
0x180049cd4  mov     rdx, rbp; pbInput
0x180049cd7  call    cs:__imp_BCryptHashData
0x180049cdd  mov     edi, eax
0x180049cdf  test    eax, eax
0x180049ce1  js      short loc_180049D18
0x180049ce3  mov     ebx, [rbx+14Ch]
0x180049ce9  mov     rcx, r14
0x180049cec  xor     edi, edi
0x180049cee  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180049cf4  mov     rcx, [rsp+78h+phHash]; hHash
0x180049cf9  xor     r9d, r9d; dwFlags
0x180049cfc  mov     rdx, rax
0x180049cff  mov     r8d, ebx; cbOutput
0x180049d02  mov     eax, [rsp+78h+arg_20]
0x180049d09  add     rdx, rax; pbOutput
0x180049d0c  call    cs:__imp_BCryptFinishHash
0x180049d12  test    eax, eax
0x180049d14  jns     short loc_180049D1C
0x180049d16  mov     edi, eax
0x180049d18  bts     edi, 1Ch
0x180049d1c  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x180049d21  test    rcx, rcx
0x180049d24  jz      short loc_180049D37
0x180049d26  xor     edx, edx; dwFlags
0x180049d28  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180049d2e  mov     [rsp+78h+phAlgorithm], 0
0x180049d37  mov     rcx, [rsp+78h+phHash]; hHash
0x180049d3c  test    rcx, rcx
0x180049d3f  jz      short loc_180049D47
0x180049d41  call    cs:__imp_BCryptDestroyHash
0x180049d47  mov     eax, edi
0x180049d49  add     rsp, 50h
0x180049d4d  pop     r14
0x180049d4f  pop     rdi
0x180049d50  pop     rsi
0x180049d51  pop     rbp
0x180049d52  pop     rbx
0x180049d53  retn
```
