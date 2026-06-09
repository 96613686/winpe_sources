# CRAEncryption::DeriveBytes(ushort *,uchar *,uint)

- ea: `0x140040a30`
- end: `0x140040cae`
- name: `?DeriveBytes@CRAEncryption@@QEAAJPEAGPEAEI@Z`
- size: `638`
- prototype: `__int64 __fastcall(CRAEncryption *__hidden this, unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x140026270`
- `0x140027f24`
- `0x140040614`

## callees

- `0x140002156`
- `0x140002463`
- `0x140034ce4`
- `0x140040458`
- `0x140040a30`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `ADVAPI32!CryptGetHashParam` at `0x140040ba1`
- `ADVAPI32!CryptGetHashParam` at `0x140040ba1`
- `ADVAPI32!CryptDestroyHash` at `0x140040bb6`
- `ADVAPI32!CryptDestroyHash` at `0x140040c7c`
- `ADVAPI32!CryptDestroyHash` at `0x140040bb6`
- `ADVAPI32!CryptDestroyHash` at `0x140040c7c`
- `ADVAPI32!CryptCreateHash` at `0x140040b4f`
- `ADVAPI32!CryptCreateHash` at `0x140040b4f`
- `ADVAPI32!CryptHashData` at `0x140040b74`
- `ADVAPI32!CryptHashData` at `0x140040b74`

## pseudocode

```c
__int64 __fastcall CRAEncryption::DeriveBytes(
        HCRYPTPROV *this,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  size_t v5; // r12
  __int64 v8; // rcx
  int v9; // ebx
  signed int v10; // eax
  unsigned int v11; // r9d
  unsigned __int16 *v12; // rax
  size_t v13; // rdi
  int v14; // esi
  CEventLogger *v15; // rcx
  int v16; // eax
  unsigned int v17; // r9d
  HCRYPTHASH hHash; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pdwDataLen; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Src[16]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+50h] [rbp-B0h]
  BYTE pbData[16]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v24[2004]; // [rsp+70h] [rbp-90h]

  v5 = a4;
  v22 = 0;
  *(_OWORD *)Src = 0;
  memset_0(pbData, 0, 0x1F54u);
  pdwDataLen = 20;
  hHash = 0;
  if ( !a3 )
  {
    v9 = -2147467261;
    CEventLogger::LogError(
      (CEventLogger *)v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raencryption.cpp",
      0x435u,
      L"CRAEncryption::DeriveBytes",
      0x80004003);
    goto LABEL_28;
  }
  if ( !*this )
  {
    v10 = CRAEncryption::AcquireContext(this);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = 1090;
LABEL_27:
      CEventLogger::LogError(
        (CEventLogger *)v8,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raencryption.cpp",
        v11,
        L"CRAEncryption::DeriveBytes",
        v10);
      goto LABEL_28;
    }
  }
  if ( !a2 )
  {
    v9 = -2147024809;
LABEL_26:
    v10 = v9;
    v11 = 1101;
    goto LABEL_27;
  }
  v12 = a2;
  v8 = 0x3FFFFFFF;
  while ( *v12 )
  {
    ++v12;
    if ( !--v8 )
    {
      v9 = -2147024809;
      v13 = 0;
      goto LABEL_12;
    }
  }
  v9 = 0;
  v13 = 2 * (0x3FFFFFFF - v8);
LABEL_12:
  if ( v9 < 0 )
    goto LABEL_26;
  if ( v13 > 0x1F40 )
    v13 = 8000;
  memcpy_0(pbData, a2, v13);
  v14 = 0;
  while ( CryptCreateHash(*this, 0x8004u, 0, 0, &hHash) )
  {
    if ( !CryptHashData(hHash, pbData, v13 + 20, 0) )
    {
      v17 = 1119;
      goto LABEL_24;
    }
    if ( !CryptGetHashParam(hHash, 2u, Src, &pdwDataLen, 0) )
    {
      v17 = 1126;
      goto LABEL_24;
    }
    CryptDestroyHash(hHash);
    v16 = v22;
    ++v14;
    hHash = 0;
    pdwDataLen = 20;
    *(_OWORD *)&pbData[v13] = *(_OWORD *)Src;
    *(_DWORD *)((char *)v24 + v13) = v16;
    if ( v14 >= 100000 )
    {
      memcpy_0(a3, Src, v5);
      goto LABEL_28;
    }
  }
  v17 = 1113;
LABEL_24:
  CEventLogger::LogError(
    v15,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\core\\lib\\raencryption.cpp",
    v17,
    L"CRAEncryption::DeriveBytes",
    0);
  v9 = -2147467259;
LABEL_28:
  if ( hHash )
    CryptDestroyHash(hHash);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140040a30  push    rbp
0x140040a32  push    rbx
0x140040a33  push    rsi
0x140040a34  push    rdi
0x140040a35  push    r12
0x140040a37  push    r13
0x140040a39  push    r14
0x140040a3b  push    r15
0x140040a3d  lea     rbp, [rsp-1ED8h]
0x140040a45  mov     eax, 1FD8h
0x140040a4a  call    _alloca_probe
0x140040a4f  sub     rsp, rax
0x140040a52  mov     rax, cs:__security_cookie
0x140040a59  xor     rax, rsp
0x140040a5c  mov     [rbp+1F10h+var_50], rax
0x140040a63  mov     r15, r8
0x140040a66  mov     r12d, r9d
0x140040a69  mov     rsi, rdx
0x140040a6c  mov     r14, rcx
0x140040a6f  xorps   xmm0, xmm0
0x140040a72  lea     rcx, [rsp+2010h+pbData]; void *
0x140040a77  xor     eax, eax
0x140040a79  xor     edx, edx; Val
0x140040a7b  mov     r8d, 1F54h; Size
0x140040a81  mov     [rsp+2010h+var_1FC0], eax
0x140040a85  movups  xmmword ptr [rsp+2010h+Src], xmm0
0x140040a8a  call    memset_0
0x140040a8f  xor     r13d, r13d
0x140040a92  mov     [rsp+2010h+pdwDataLen], 14h
0x140040a9a  mov     [rsp+2010h+hHash], r13
0x140040a9f  test    r15, r15
0x140040aa2  jnz     short loc_140040ABC
0x140040aa4  mov     ebx, 80004003h
0x140040aa9  mov     [rsp+2010h+var_1FE8], 80004003h
0x140040ab1  mov     r9d, 435h
0x140040ab7  jmp     loc_140040C53
0x140040abc  cmp     [r14], r13
0x140040abf  jnz     short loc_140040ADA
0x140040ac1  mov     rcx, r14; phProv
0x140040ac4  call    ?AcquireContext@CRAEncryption@@QEAAJXZ; CRAEncryption::AcquireContext(void)
0x140040ac9  mov     ebx, eax
0x140040acb  test    eax, eax
0x140040acd  jns     short loc_140040ADA
0x140040acf  mov     r9d, 442h
0x140040ad5  jmp     loc_140040C4F
0x140040ada  test    rsi, rsi
0x140040add  jz      loc_140040C42
0x140040ae3  mov     edi, 3FFFFFFFh
0x140040ae8  mov     rax, rsi
0x140040aeb  mov     ecx, edi
0x140040aed  cmp     [rax], r13w
0x140040af1  jz      short loc_140040B07
0x140040af3  add     rax, 2
0x140040af7  sub     rcx, 1
0x140040afb  jnz     short loc_140040AED
0x140040afd  mov     ebx, 80070057h
0x140040b02  mov     rdi, r13
0x140040b05  jmp     short loc_140040B10
0x140040b07  sub     rdi, rcx
0x140040b0a  mov     ebx, r13d
0x140040b0d  add     rdi, rdi
0x140040b10  test    ebx, ebx
0x140040b12  js      loc_140040C47
0x140040b18  mov     eax, 1F40h
0x140040b1d  lea     rcx, [rsp+2010h+pbData]; void *
0x140040b22  cmp     rdi, rax
0x140040b25  mov     rdx, rsi; Src
0x140040b28  cmova   rdi, rax
0x140040b2c  mov     r8, rdi; Size
0x140040b2f  call    memcpy_0
0x140040b34  mov     esi, r13d
0x140040b37  mov     rcx, [r14]; hProv
0x140040b3a  lea     rax, [rsp+2010h+hHash]
0x140040b3f  xor     r9d, r9d; dwFlags
0x140040b42  mov     [rsp+2010h+phHash], rax; phHash
0x140040b47  xor     r8d, r8d; hKey
0x140040b4a  mov     edx, 8004h; Algid
0x140040b4f  call    cs:__imp_CryptCreateHash
0x140040b56  nop     dword ptr [rax+rax+00h]
0x140040b5b  test    eax, eax
0x140040b5d  jz      loc_140040C11
0x140040b63  mov     rcx, [rsp+2010h+hHash]; hHash
0x140040b68  lea     r8d, [rdi+14h]; dwDataLen
0x140040b6c  xor     r9d, r9d; dwFlags
0x140040b6f  lea     rdx, [rsp+2010h+pbData]; pbData
0x140040b74  call    cs:__imp_CryptHashData
0x140040b7b  nop     dword ptr [rax+rax+00h]
0x140040b80  test    eax, eax
0x140040b82  jz      loc_140040C09
0x140040b88  mov     rcx, [rsp+2010h+hHash]; hHash
0x140040b8d  lea     r9, [rsp+2010h+pdwDataLen]; pdwDataLen
0x140040b92  lea     r8, [rsp+2010h+Src]; pbData
0x140040b97  mov     dword ptr [rsp+2010h+phHash], r13d; dwFlags
0x140040b9c  mov     edx, 2; dwParam
0x140040ba1  call    cs:__imp_CryptGetHashParam
0x140040ba8  nop     dword ptr [rax+rax+00h]
0x140040bad  test    eax, eax
0x140040baf  jz      short loc_140040C01
0x140040bb1  mov     rcx, [rsp+2010h+hHash]; hHash
0x140040bb6  call    cs:__imp_CryptDestroyHash
0x140040bbd  nop     dword ptr [rax+rax+00h]
0x140040bc2  movups  xmm0, xmmword ptr [rsp+2010h+Src]
0x140040bc7  mov     eax, [rsp+2010h+var_1FC0]
0x140040bcb  inc     esi
0x140040bcd  mov     [rsp+2010h+hHash], r13
0x140040bd2  mov     [rsp+2010h+pdwDataLen], 14h
0x140040bda  movups  xmmword ptr [rsp+rdi+2010h+pbData], xmm0
0x140040bdf  mov     [rsp+rdi+2010h+var_1FA0], eax
0x140040be3  cmp     esi, 186A0h
0x140040be9  jl      loc_140040B37
0x140040bef  mov     r8, r12; Size
0x140040bf2  lea     rdx, [rsp+2010h+Src]; Src
0x140040bf7  mov     rcx, r15; void *
0x140040bfa  call    memcpy_0
0x140040bff  jmp     short loc_140040C72
0x140040c01  mov     r9d, 466h
0x140040c07  jmp     short loc_140040C17
0x140040c09  mov     r9d, 45Fh
0x140040c0f  jmp     short loc_140040C17
0x140040c11  mov     r9d, 459h; unsigned int
0x140040c17  lea     rax, aCraencryptionD_0; "CRAEncryption::DeriveBytes"
0x140040c1e  mov     [rsp+2010h+var_1FE8], r13d; unsigned int
0x140040c23  lea     r8, aBaseDiagnosisR_29; "base\\diagnosis\\ra\\core\\lib\\raencry"...
0x140040c2a  mov     [rsp+2010h+phHash], rax; unsigned __int16 *
0x140040c2f  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140040c36  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140040c3b  mov     ebx, 80004005h
0x140040c40  jmp     short loc_140040C72
0x140040c42  mov     ebx, 80070057h
0x140040c47  mov     eax, ebx
0x140040c49  mov     r9d, 44Dh; unsigned int
0x140040c4f  mov     [rsp+2010h+var_1FE8], eax; unsigned int
0x140040c53  lea     rax, aCraencryptionD_0; "CRAEncryption::DeriveBytes"
0x140040c5a  lea     r8, aBaseDiagnosisR_29; "base\\diagnosis\\ra\\core\\lib\\raencry"...
0x140040c61  mov     [rsp+2010h+phHash], rax; unsigned __int16 *
0x140040c66  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140040c6d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140040c72  mov     rcx, [rsp+2010h+hHash]; hHash
0x140040c77  test    rcx, rcx
0x140040c7a  jz      short loc_140040C88
0x140040c7c  call    cs:__imp_CryptDestroyHash
0x140040c83  nop     dword ptr [rax+rax+00h]
0x140040c88  mov     eax, ebx
0x140040c8a  mov     rcx, [rbp+1F10h+var_50]
0x140040c91  xor     rcx, rsp; StackCookie
0x140040c94  call    __security_check_cookie
0x140040c99  add     rsp, 1FD8h
0x140040ca0  pop     r15
0x140040ca2  pop     r14
0x140040ca4  pop     r13
0x140040ca6  pop     r12
0x140040ca8  pop     rdi
0x140040ca9  pop     rsi
0x140040caa  pop     rbx
0x140040cab  pop     rbp
0x140040cac  retn
```
