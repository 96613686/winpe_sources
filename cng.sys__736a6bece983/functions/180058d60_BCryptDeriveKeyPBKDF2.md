# BCryptDeriveKeyPBKDF2

- ea: `0x180058d60`
- end: `0x18005902c`
- name: `BCryptDeriveKeyPBKDF2`
- size: `716`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hPrf, PUCHAR pbPassword, ULONG cbPassword, PUCHAR pbSalt, ULONG cbSalt, ULONGLONG cIterations, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001ab0`
- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180058d60`
- `0x18009f780`

## string_xrefs

- `0x180058f3a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180058f6a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180059004`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDeriveKeyPBKDF2(
        BCRYPT_ALG_HANDLE hPrf,
        PUCHAR pbPassword,
        ULONG cbPassword,
        PUCHAR pbSalt,
        ULONG cbSalt,
        ULONGLONG cIterations,
        PUCHAR pbDerivedKey,
        ULONG cbDerivedKey,
        ULONG dwFlags)
{
  NTSTATUS Property; // eax
  NTSTATUS v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  ULONG v14; // edi
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  _BYTE *v18; // rsi
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  void *v22; // r14
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  char *v27; // rdi
  ULONG i; // ecx
  int PBKDF2Block; // eax
  _BYTE *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  _BYTE *v33; // rcx
  UCHAR v35[4]; // [rsp+60h] [rbp-20h] BYREF
  ULONG pcbResult; // [rsp+64h] [rbp-1Ch] BYREF
  UCHAR v37[4]; // [rsp+68h] [rbp-18h] BYREF
  UCHAR pbOutput[4]; // [rsp+6Ch] [rbp-14h] BYREF
  ULONG v39; // [rsp+70h] [rbp-10h]
  ULONG v40; // [rsp+74h] [rbp-Ch]

  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  *(_DWORD *)v37 = 0;
  *(_DWORD *)v35 = 0;
  if ( !cIterations || dwFlags || !pbPassword && cbPassword || !pbSalt && cbSalt || !pbDerivedKey || !cbDerivedKey )
  {
    v11 = -1073741811;
    v12 = 7530;
    v13 = 3221225485LL;
    goto LABEL_37;
  }
  if ( BCryptGetProperty(hPrf, L"IsKeyedHash", pbOutput, 4u, &pcbResult, 0) < 0 || !*(_DWORD *)pbOutput )
  {
    v11 = -1073741816;
    v12 = 7543;
    v13 = 3221225480LL;
    goto LABEL_37;
  }
  Property = BCryptGetProperty(hPrf, L"HashDigestLength", v35, 4u, &pcbResult, 0);
  v11 = Property;
  if ( Property < 0 )
  {
    v12 = 7555;
LABEL_13:
    v13 = (unsigned int)Property;
LABEL_37:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v12);
    return v11;
  }
  v14 = (cbDerivedKey + *(_DWORD *)v35 - 1) / *(_DWORD *)v35;
  v39 = v14;
  Property = BCryptGetProperty(hPrf, L"ObjectLength", v37, 4u, &pcbResult, 0);
  v11 = Property;
  if ( Property < 0 )
  {
    v12 = 7572;
    goto LABEL_13;
  }
  v18 = (_BYTE *)MSCryptAlloc(*(unsigned int *)v35, v15, v16, v17);
  v22 = (void *)MSCryptAlloc(*(unsigned int *)v37, v19, v20, v21);
  v26 = MSCryptAlloc(v14 * *(_DWORD *)v35, v23, v24, v25);
  v27 = (char *)v26;
  if ( v18 && v22 && v26 )
  {
    for ( i = 0; i < v39; i = v40 )
    {
      v40 = i + 1;
      PBKDF2Block = GetPBKDF2Block(
                      hPrf,
                      pbPassword,
                      cbPassword,
                      pbSalt,
                      cbSalt,
                      cIterations,
                      i + 1,
                      v22,
                      *(_DWORD *)v37,
                      v18,
                      &v27[*(_DWORD *)v35 * i],
                      *(_DWORD *)v35);
      v11 = PBKDF2Block;
      if ( PBKDF2Block < 0 )
      {
        DebugTraceError(
          (unsigned int)PBKDF2Block,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          7609);
        goto LABEL_26;
      }
    }
    memmove(pbDerivedKey, v27, cbDerivedKey);
    v11 = 0;
    goto LABEL_26;
  }
  DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7589);
  v11 = -1073741801;
  if ( v27 )
  {
LABEL_26:
    v30 = v27;
    v31 = v39 * *(_DWORD *)v35;
    if ( v39 * *(_DWORD *)v35 )
    {
      do
      {
        *v30++ = 0;
        --v31;
      }
      while ( v31 );
    }
    MSCryptFree(v27);
  }
  if ( v22 )
    MSCryptFree(v22);
  if ( v18 )
  {
    v32 = *(unsigned int *)v35;
    v33 = v18;
    if ( *(_DWORD *)v35 )
    {
      do
      {
        *v33++ = 0;
        --v32;
      }
      while ( v32 );
    }
    MSCryptFree(v18);
  }
  return v11;
}

```

## disassembly

```asm
0x180058d60  mov     [rsp-38h+arg_18], r9
0x180058d65  mov     [rsp-38h+arg_10], r8d
0x180058d6a  mov     [rsp-38h+arg_8], rdx
0x180058d6f  push    rbp
0x180058d70  push    rbx
0x180058d71  push    rsi
0x180058d72  push    rdi
0x180058d73  push    r12
0x180058d75  push    r14
0x180058d77  push    r15
0x180058d79  mov     rbp, rsp
0x180058d7c  sub     rsp, 80h
0x180058d83  xor     esi, esi
0x180058d85  mov     eax, r8d
0x180058d88  mov     r12, rcx
0x180058d8b  mov     dword ptr [rbp+pbOutput], esi
0x180058d8e  mov     [rbp+var_1C], esi
0x180058d91  mov     dword ptr [rbp+var_18], esi
0x180058d94  mov     dword ptr [rbp+var_20], esi
0x180058d97  cmp     [rbp+cIterations], rsi
0x180058d9b  jz      loc_180058FF4
0x180058da1  cmp     [rbp+dwFlags], esi
0x180058da7  jnz     loc_180058FF4
0x180058dad  test    rdx, rdx
0x180058db0  jnz     short loc_180058DBA
0x180058db2  test    eax, eax
0x180058db4  jnz     loc_180058FF4
0x180058dba  test    r9, r9
0x180058dbd  jnz     short loc_180058DC8
0x180058dbf  cmp     [rbp+cbSalt], esi
0x180058dc2  jnz     loc_180058FF4
0x180058dc8  cmp     [rbp+pbDerivedKey], rsi
0x180058dcc  jz      loc_180058FF4
0x180058dd2  mov     r15d, [rbp+cbDerivedKey]
0x180058dd6  test    r15d, r15d
0x180058dd9  jz      loc_180058FF4
0x180058ddf  lea     rax, [rbp+var_1C]
0x180058de3  mov     [rsp+80h+var_58], esi; dwFlags
0x180058de7  mov     r14d, 4
0x180058ded  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180058df2  mov     r9d, r14d; cbOutput
0x180058df5  lea     r8, [rbp+pbOutput]; pbOutput
0x180058df9  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x180058e00  call    BCryptGetProperty
0x180058e05  test    eax, eax
0x180058e07  js      loc_180058FE2
0x180058e0d  cmp     dword ptr [rbp+pbOutput], esi
0x180058e10  jz      loc_180058FE2
0x180058e16  lea     rax, [rbp+var_1C]
0x180058e1a  mov     [rsp+80h+var_58], esi; dwFlags
0x180058e1e  mov     r9d, r14d; cbOutput
0x180058e21  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180058e26  lea     r8, [rbp+var_20]; pbOutput
0x180058e2a  mov     rcx, r12; hObject
0x180058e2d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180058e34  call    BCryptGetProperty
0x180058e39  mov     ebx, eax
0x180058e3b  test    eax, eax
0x180058e3d  jns     short loc_180058E4C
0x180058e3f  mov     r9d, 1D83h
0x180058e45  mov     ecx, eax
0x180058e47  jmp     loc_180059004
0x180058e4c  mov     ecx, dword ptr [rbp+var_20]
0x180058e4f  lea     r8, [rbp+var_18]; pbOutput
0x180058e53  xor     edx, edx
0x180058e55  mov     [rsp+80h+var_58], esi; dwFlags
0x180058e59  mov     r9d, r14d; cbOutput
0x180058e5c  lea     eax, [rcx-1]
0x180058e5f  add     eax, r15d
0x180058e62  div     ecx
0x180058e64  lea     rdx, aObjectlength; "ObjectLength"
0x180058e6b  mov     rcx, r12; hObject
0x180058e6e  mov     edi, eax
0x180058e70  mov     [rbp+var_10], eax
0x180058e73  lea     rax, [rbp+var_1C]
0x180058e77  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180058e7c  call    BCryptGetProperty
0x180058e81  mov     ebx, eax
0x180058e83  test    eax, eax
0x180058e85  jns     short loc_180058E8F
0x180058e87  mov     r9d, 1D94h
0x180058e8d  jmp     short loc_180058E45
0x180058e8f  mov     ecx, dword ptr [rbp+var_20]
0x180058e92  call    MSCryptAlloc
0x180058e97  mov     ecx, dword ptr [rbp+var_18]
0x180058e9a  mov     rsi, rax
0x180058e9d  call    MSCryptAlloc
0x180058ea2  mov     ecx, dword ptr [rbp+var_20]
0x180058ea5  mov     r14, rax
0x180058ea8  imul    ecx, edi
0x180058eab  call    MSCryptAlloc
0x180058eb0  mov     rdi, rax
0x180058eb3  test    rsi, rsi
0x180058eb6  jz      loc_180058F64
0x180058ebc  test    r14, r14
0x180058ebf  jz      loc_180058F64
0x180058ec5  test    rax, rax
0x180058ec8  jz      loc_180058F64
0x180058ece  xor     ecx, ecx
0x180058ed0  cmp     ecx, [rbp+var_10]
0x180058ed3  jnb     short loc_180058F51
0x180058ed5  mov     edx, dword ptr [rbp+var_20]
0x180058ed8  lea     r8d, [rcx+1]
0x180058edc  mov     eax, dword ptr [rbp+var_18]
0x180058edf  mov     r9, [rbp+arg_18]
0x180058ee3  mov     [rsp+80h+var_28], edx
0x180058ee7  imul    ecx, edx
0x180058eea  mov     rdx, [rbp+arg_8]
0x180058eee  mov     [rbp+var_C], r8d
0x180058ef2  add     rcx, rdi
0x180058ef5  mov     [rsp+80h+var_30], rcx
0x180058efa  mov     rcx, r12
0x180058efd  mov     [rsp+80h+var_38], rsi
0x180058f02  mov     [rsp+80h+var_40], eax
0x180058f06  mov     rax, [rbp+cIterations]
0x180058f0a  mov     [rsp+80h+var_48], r14
0x180058f0f  mov     [rsp+80h+var_50], r8d
0x180058f14  mov     r8d, [rbp+arg_10]
0x180058f18  mov     qword ptr [rsp+80h+var_58], rax
0x180058f1d  mov     eax, [rbp+cbSalt]
0x180058f20  mov     dword ptr [rsp+80h+pcbResult], eax
0x180058f24  call    GetPBKDF2Block
0x180058f29  mov     ebx, eax
0x180058f2b  test    eax, eax
0x180058f2d  js      short loc_180058F34
0x180058f2f  mov     ecx, [rbp+var_C]
0x180058f32  jmp     short loc_180058ED0
0x180058f34  mov     r9d, 1DB9h
0x180058f3a  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058f41  lea     rdx, aStatus; "Status"
0x180058f48  mov     ecx, eax
0x180058f4a  call    DebugTraceError
0x180058f4f  jmp     short loc_180058F8C
0x180058f51  mov     rcx, [rbp+pbDerivedKey]; void *
0x180058f55  mov     r8, r15; Size
0x180058f58  mov     rdx, rdi; Src
0x180058f5b  call    memmove
0x180058f60  xor     ebx, ebx
0x180058f62  jmp     short loc_180058F8C
0x180058f64  mov     r9d, 1DA5h
0x180058f6a  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058f71  lea     rdx, aStatus; "Status"
0x180058f78  mov     ecx, 0C0000017h
0x180058f7d  call    DebugTraceError
0x180058f82  mov     ebx, 0C0000017h
0x180058f87  test    rdi, rdi
0x180058f8a  jz      short loc_180058FAF
0x180058f8c  mov     ecx, dword ptr [rbp+var_20]
0x180058f8f  mov     rax, rdi
0x180058f92  imul    ecx, [rbp+var_10]
0x180058f96  test    rcx, rcx
0x180058f99  jz      short loc_180058FA7
0x180058f9b  mov     byte ptr [rax], 0
0x180058f9e  inc     rax
0x180058fa1  sub     rcx, 1
0x180058fa5  jnz     short loc_180058F9B
0x180058fa7  mov     rcx, rdi; P
0x180058faa  call    MSCryptFree
0x180058faf  test    r14, r14
0x180058fb2  jz      short loc_180058FBC
0x180058fb4  mov     rcx, r14; P
0x180058fb7  call    MSCryptFree
0x180058fbc  test    rsi, rsi
0x180058fbf  jz      short loc_180059017
0x180058fc1  mov     eax, dword ptr [rbp+var_20]
0x180058fc4  mov     rcx, rsi
0x180058fc7  test    rax, rax
0x180058fca  jz      short loc_180058FD8
0x180058fcc  mov     byte ptr [rcx], 0
0x180058fcf  inc     rcx
0x180058fd2  sub     rax, 1
0x180058fd6  jnz     short loc_180058FCC
0x180058fd8  mov     rcx, rsi; P
0x180058fdb  call    MSCryptFree
0x180058fe0  jmp     short loc_180059017
0x180058fe2  mov     ebx, 0C0000008h
0x180058fe7  mov     r9d, 1D77h
0x180058fed  mov     ecx, 0C0000008h
0x180058ff2  jmp     short loc_180059004
0x180058ff4  mov     ebx, 0C000000Dh
0x180058ff9  mov     r9d, 1D6Ah
0x180058fff  mov     ecx, 0C000000Dh
0x180059004  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005900b  lea     rdx, aStatus; "Status"
0x180059012  call    DebugTraceError
0x180059017  mov     eax, ebx
0x180059019  add     rsp, 80h
0x180059020  pop     r15
0x180059022  pop     r14
0x180059024  pop     r12
0x180059026  pop     rdi
0x180059027  pop     rsi
0x180059028  pop     rbx
0x180059029  pop     rbp
0x18005902a  retn
```
