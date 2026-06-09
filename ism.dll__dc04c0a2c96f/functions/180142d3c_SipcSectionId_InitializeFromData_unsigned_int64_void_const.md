# SipcSectionId::InitializeFromData(unsigned __int64,void const *)

- ea: `0x180142d3c`
- end: `0x180142e73`
- name: `?InitializeFromData@SipcSectionId@@QEAAJ_KPEBX@Z`
- size: `311`
- prototype: `__int64 __fastcall(SipcSectionId *__hidden this, ULONG cbInput, PUCHAR pbInput)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801421e0`

## callees

- `0x1800e795c`
- `0x180142d3c`
- `0x180142f28`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180142de4`
- `bcrypt!BCryptDestroyHash` at `0x180142e49`
- `bcrypt!BCryptDestroyHash` at `0x180142de4`
- `bcrypt!BCryptDestroyHash` at `0x180142e49`
- `bcrypt!BCryptFinishHash` at `0x180142e19`
- `bcrypt!BCryptFinishHash` at `0x180142e19`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180142d8c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180142e62`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180142d8c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180142e62`
- `bcrypt!BCryptHashData` at `0x180142e01`
- `bcrypt!BCryptHashData` at `0x180142e01`
- `bcrypt!BCryptCreateHash` at `0x180142dc4`
- `bcrypt!BCryptCreateHash` at `0x180142dc4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180142d6a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180142d6a`

## pseudocode

```c
__int64 __fastcall SipcSectionId::InitializeFromData(UCHAR *this, ULONG cbInput, PUCHAR pbInput)
{
  NTSTATUS v6; // eax
  BCRYPT_ALG_HANDLE v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  NTSTATUS v11; // eax
  BCRYPT_HASH_HANDLE v12; // rcx
  int v13; // eax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+98h] [rbp+40h] BYREF

  phAlgorithm = 0;
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  v7 = phAlgorithm;
  if ( v6 < 0 )
  {
    v8 = v6 | 0x10000000;
    v9 = -2147418113;
    if ( v8 < 0 )
      v9 = v8;
LABEL_4:
    if ( v7 )
      BCryptCloseAlgorithmProvider(v7, 0);
    return v9;
  }
  phHash = 0;
  v11 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  v12 = phHash;
  if ( v11 < 0 || (v11 = BCryptHashData(phHash, pbInput, cbInput, 0), v12 = phHash, v11 < 0) )
  {
LABEL_8:
    v13 = v11 | 0x10000000;
    v9 = -2147418113;
    if ( v13 < 0 )
      v9 = v13;
    if ( v12 )
    {
      BCryptDestroyHash(v12);
      phHash = 0;
    }
    v7 = phAlgorithm;
    goto LABEL_4;
  }
  v11 = BCryptFinishHash(phHash, this, 0x20u, 0);
  if ( v11 < 0 )
  {
    v12 = phHash;
    goto LABEL_8;
  }
  if ( !SipcSectionId::IsInitialized((SipcSectionId *)this) )
  {
    SipcFailFast(2147549183LL);
    __debugbreak();
  }
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return 0;
}

```

## disassembly

```asm
0x180142d3c  push    rbp
0x180142d3e  push    rbx
0x180142d3f  push    rsi
0x180142d40  push    rdi
0x180142d41  mov     rbp, rsp
0x180142d44  sub     rsp, 58h
0x180142d48  mov     rdi, r8
0x180142d4b  mov     [rbp+phAlgorithm], 0
0x180142d53  mov     rsi, rdx
0x180142d56  mov     rbx, rcx
0x180142d59  xor     r8d, r8d; pszImplementation
0x180142d5c  lea     rdx, pszAlgId; "SHA256"
0x180142d63  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180142d67  xor     r9d, r9d; dwFlags
0x180142d6a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180142d70  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180142d74  test    eax, eax
0x180142d76  jns     short loc_180142D99
0x180142d78  or      eax, 10000000h
0x180142d7d  mov     ebx, 8000FFFFh
0x180142d82  cmovl   ebx, eax
0x180142d85  test    rcx, rcx
0x180142d88  jz      short loc_180142D92
0x180142d8a  xor     edx, edx; dwFlags
0x180142d8c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180142d92  mov     eax, ebx
0x180142d94  jmp     loc_180142E6A
0x180142d99  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180142da1  lea     rdx, [rbp+phHash]; phHash
0x180142da5  mov     [rsp+58h+cbSecret], 0; cbSecret
0x180142dad  xor     r9d, r9d; cbHashObject
0x180142db0  xor     r8d, r8d; pbHashObject
0x180142db3  mov     [rsp+58h+pbSecret], 0; pbSecret
0x180142dbc  mov     [rbp+phHash], 0
0x180142dc4  call    cs:__imp_BCryptCreateHash
0x180142dca  mov     rcx, [rbp+phHash]; hHash
0x180142dce  test    eax, eax
0x180142dd0  jns     short loc_180142DF8
0x180142dd2  or      eax, 10000000h
0x180142dd7  mov     ebx, 8000FFFFh
0x180142ddc  cmovl   ebx, eax
0x180142ddf  test    rcx, rcx
0x180142de2  jz      short loc_180142DF2
0x180142de4  call    cs:__imp_BCryptDestroyHash
0x180142dea  mov     [rbp+phHash], 0
0x180142df2  mov     rcx, [rbp+phAlgorithm]
0x180142df6  jmp     short loc_180142D85
0x180142df8  mov     r8d, esi; cbInput
0x180142dfb  xor     r9d, r9d; dwFlags
0x180142dfe  mov     rdx, rdi; pbInput
0x180142e01  call    cs:__imp_BCryptHashData
0x180142e07  mov     rcx, [rbp+phHash]; hHash
0x180142e0b  test    eax, eax
0x180142e0d  js      short loc_180142DD2
0x180142e0f  xor     r9d, r9d; dwFlags
0x180142e12  mov     rdx, rbx; pbOutput
0x180142e15  lea     r8d, [r9+20h]; cbOutput
0x180142e19  call    cs:__imp_BCryptFinishHash
0x180142e1f  test    eax, eax
0x180142e21  jns     short loc_180142E29
0x180142e23  mov     rcx, [rbp+phHash]
0x180142e27  jmp     short loc_180142DD2
0x180142e29  mov     rcx, rbx; this
0x180142e2c  call    ?IsInitialized@SipcSectionId@@QEBA_NXZ; SipcSectionId::IsInitialized(void)
0x180142e31  test    al, al
0x180142e33  jnz     short loc_180142E40
0x180142e35  mov     ecx, 8000FFFFh
0x180142e3a  call    SipcFailFast
0x180142e3f  int     3; Trap to Debugger
0x180142e40  mov     rcx, [rbp+phHash]; hHash
0x180142e44  test    rcx, rcx
0x180142e47  jz      short loc_180142E57
0x180142e49  call    cs:__imp_BCryptDestroyHash
0x180142e4f  mov     [rbp+phHash], 0
0x180142e57  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180142e5b  test    rcx, rcx
0x180142e5e  jz      short loc_180142E68
0x180142e60  xor     edx, edx; dwFlags
0x180142e62  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180142e68  xor     eax, eax
0x180142e6a  add     rsp, 58h
0x180142e6e  pop     rdi
0x180142e6f  pop     rsi
0x180142e70  pop     rbx
0x180142e71  pop     rbp
0x180142e72  retn
```
