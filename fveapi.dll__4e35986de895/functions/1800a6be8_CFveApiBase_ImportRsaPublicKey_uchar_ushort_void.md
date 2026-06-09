# CFveApiBase::ImportRsaPublicKey(uchar *,ushort,void * *)

- ea: `0x1800a6be8`
- end: `0x1800a6cf9`
- name: `?ImportRsaPublicKey@CFveApiBase@@SAJPEAEGPEAPEAX@Z`
- size: `273`
- prototype: `__int64 __fastcall(PUCHAR pbInput, unsigned __int16, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ebe0`

## callees

- `0x180018b10`
- `0x1800a6be8`
- `0x18011f010`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800a6c46`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800a6c46`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800a6cd1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180124f70`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800a6cd1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180124f70`
- `bcrypt!BCryptImportKeyPair` at `0x1800a6c88`
- `bcrypt!BCryptImportKeyPair` at `0x1800a6c88`
- `bcrypt!BCryptDestroyKey` at `0x1800a6cb4`
- `bcrypt!BCryptDestroyKey` at `0x180124f51`
- `bcrypt!BCryptDestroyKey` at `0x1800a6cb4`
- `bcrypt!BCryptDestroyKey` at `0x180124f51`

## pseudocode

```c
__int64 __fastcall CFveApiBase::ImportRsaPublicKey(PUCHAR pbInput, unsigned __int16 a2, void **a3)
{
  ULONG cbInput; // r14d
  unsigned int v6; // ebx
  BCRYPT_KEY_HANDLE v7; // rcx
  NTSTATUS v8; // eax
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-48h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-40h] BYREF

  cbInput = a2;
  v6 = 0;
  v7 = 0;
  phKey = 0;
  phAlgorithm = 0;
  if ( pbInput && a2 && a3 )
  {
    v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", 0, 0);
    if ( v8 || (v8 = BCryptImportKeyPair(phAlgorithm, 0, L"PUBLICBLOB", &phKey, pbInput, cbInput, 0)) != 0 )
    {
      v6 = FromNtStatus(v8);
      v7 = phKey;
    }
    else
    {
      *a3 = phKey;
      v7 = 0;
      phKey = 0;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( v7 )
  {
    BCryptDestroyKey(v7);
    phKey = 0;
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v6;
}

```

## disassembly

```asm
0x1800a6be8  push    rbx
0x1800a6bea  push    rsi
0x1800a6beb  push    rdi
0x1800a6bec  push    r14
0x1800a6bee  push    r15
0x1800a6bf0  sub     rsp, 60h
0x1800a6bf4  mov     rax, cs:__security_cookie
0x1800a6bfb  xor     rax, rsp
0x1800a6bfe  mov     [rsp+88h+var_38], rax
0x1800a6c03  mov     rdi, r8
0x1800a6c06  movzx   r14d, dx
0x1800a6c0a  mov     rsi, rcx
0x1800a6c0d  xor     r15d, r15d
0x1800a6c10  mov     ebx, r15d
0x1800a6c13  mov     ecx, r15d; hKey
0x1800a6c16  mov     [rsp+88h+phKey], rcx
0x1800a6c1b  mov     [rsp+88h+phAlgorithm], r15
0x1800a6c20  test    rsi, rsi
0x1800a6c23  jz      loc_1800A6CAA
0x1800a6c29  test    r14w, r14w
0x1800a6c2d  jz      short loc_1800A6CAA
0x1800a6c2f  test    r8, r8
0x1800a6c32  jz      short loc_1800A6CAA
0x1800a6c34  xor     r9d, r9d; dwFlags
0x1800a6c37  xor     r8d, r8d; pszImplementation
0x1800a6c3a  lea     rdx, aRsa; "RSA"
0x1800a6c41  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x1800a6c46  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800a6c4d  nop     dword ptr [rax+rax+00h]
0x1800a6c52  test    eax, eax
0x1800a6c54  jz      short loc_1800A6C66
0x1800a6c56  mov     ecx, eax; int
0x1800a6c58  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800a6c5d  mov     ebx, eax
0x1800a6c5f  mov     rcx, [rsp+88h+phKey]
0x1800a6c64  jmp     short loc_1800A6CAF
0x1800a6c66  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x1800a6c6b  mov     [rsp+88h+cbInput], r14d; cbInput
0x1800a6c70  mov     [rsp+88h+pbInput], rsi; pbInput
0x1800a6c75  lea     r9, [rsp+88h+phKey]; phKey
0x1800a6c7a  lea     r8, pszBlobType; "PUBLICBLOB"
0x1800a6c81  xor     edx, edx; hImportKey
0x1800a6c83  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x1800a6c88  call    cs:__imp_BCryptImportKeyPair
0x1800a6c8f  nop     dword ptr [rax+rax+00h]
0x1800a6c94  test    eax, eax
0x1800a6c96  jnz     short loc_1800A6C56
0x1800a6c98  mov     rax, [rsp+88h+phKey]
0x1800a6c9d  mov     [rdi], rax
0x1800a6ca0  mov     rcx, r15
0x1800a6ca3  mov     [rsp+88h+phKey], rcx
0x1800a6ca8  jmp     short loc_1800A6CAF
0x1800a6caa  mov     ebx, 80070057h
0x1800a6caf  test    rcx, rcx
0x1800a6cb2  jz      short loc_1800A6CC5
0x1800a6cb4  call    cs:__imp_BCryptDestroyKey
0x1800a6cbb  nop     dword ptr [rax+rax+00h]
0x1800a6cc0  mov     [rsp+88h+phKey], r15
0x1800a6cc5  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x1800a6cca  test    rcx, rcx
0x1800a6ccd  jz      short loc_1800A6CDD
0x1800a6ccf  xor     edx, edx; dwFlags
0x1800a6cd1  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800a6cd8  nop     dword ptr [rax+rax+00h]
0x1800a6cdd  mov     eax, ebx
0x1800a6cdf  mov     rcx, [rsp+88h+var_38]
0x1800a6ce4  xor     rcx, rsp; StackCookie
0x1800a6ce7  call    __security_check_cookie
0x1800a6cec  add     rsp, 60h
0x1800a6cf0  pop     r15
0x1800a6cf2  pop     r14
0x1800a6cf4  pop     rdi
0x1800a6cf5  pop     rsi
0x1800a6cf6  pop     rbx
0x1800a6cf7  retn
0x180124f3f  push    rbp
0x180124f41  sub     rsp, 40h
0x180124f45  mov     rbp, rdx
0x180124f48  mov     rcx, [rbp+40h]; hKey
0x180124f4c  test    rcx, rcx
0x180124f4f  jz      short loc_180124F65
0x180124f51  call    cs:__imp_BCryptDestroyKey
0x180124f58  nop     dword ptr [rax+rax+00h]
0x180124f5d  mov     qword ptr [rbp+40h], 0
0x180124f65  mov     rcx, [rbp+48h]; hAlgorithm
0x180124f69  test    rcx, rcx
0x180124f6c  jz      short loc_180124F7D
0x180124f6e  xor     edx, edx; dwFlags
0x180124f70  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180124f77  nop     dword ptr [rax+rax+00h]
0x180124f7c  nop
0x180124f7d  add     rsp, 40h
0x180124f81  pop     rbp
0x180124f82  retn
```
