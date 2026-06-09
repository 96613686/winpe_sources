# EndpointDlp::Common::Certificate::VerifyMessageSignatureInternal(std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,uint)

- ea: `0x180062994`
- end: `0x180062bbb`
- name: `?VerifyMessageSignatureInternal@Certificate@Common@EndpointDlp@@AEBA_NAEBV?$vector@EV?$allocator@E@std@@@std@@0I@Z`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180060ac8`

## callees

- `0x180062994`
- `0x180064774`
- `0x18010cb40`
- `0x18016adec`
- `0x18016ae9c`

## import_xrefs

- `ADVAPI32!CryptReleaseContext` at `0x180062b9c`
- `ADVAPI32!CryptReleaseContext` at `0x180062b9c`
- `ADVAPI32!CryptDestroyHash` at `0x180062a2d`
- `ADVAPI32!CryptDestroyHash` at `0x180062b8a`
- `ADVAPI32!CryptDestroyHash` at `0x180062a2d`
- `ADVAPI32!CryptDestroyHash` at `0x180062b8a`
- `ADVAPI32!CryptHashData` at `0x180062a9d`
- `ADVAPI32!CryptHashData` at `0x180062a9d`
- `ADVAPI32!CryptDestroyKey` at `0x180062ae2`
- `ADVAPI32!CryptDestroyKey` at `0x180062b7a`
- `ADVAPI32!CryptDestroyKey` at `0x180062ae2`
- `ADVAPI32!CryptDestroyKey` at `0x180062b7a`
- `ADVAPI32!CryptAcquireContextW` at `0x1800629e8`
- `ADVAPI32!CryptAcquireContextW` at `0x1800629e8`
- `ADVAPI32!CryptVerifySignatureW` at `0x180062b64`
- `ADVAPI32!CryptVerifySignatureW` at `0x180062b64`
- `ADVAPI32!CryptCreateHash` at `0x180062a5c`
- `ADVAPI32!CryptCreateHash` at `0x180062a5c`
- `CRYPT32!CryptImportPublicKeyInfo` at `0x180062b11`
- `CRYPT32!CryptImportPublicKeyInfo` at `0x180062b11`

## string_xrefs

- `0x180062a07`: `src\epp\Dlp\EndpointDlp\Common\src\Certificate.cpp`
- `0x180062a7b`: `src\epp\Dlp\EndpointDlp\Common\src\Certificate.cpp`
- `0x180062abc`: `src\epp\Dlp\EndpointDlp\Common\src\Certificate.cpp`
- `0x180062b30`: `src\epp\Dlp\EndpointDlp\Common\src\Certificate.cpp`
- `0x180062aac`: `Computing hash object failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall EndpointDlp::Common::Certificate::VerifyMessageSignatureInternal(__int64 a1, __int64 a2, __int64 a3)
{
  BOOL v6; // eax
  BOOL v7; // eax
  BOOL v8; // eax
  HCRYPTKEY v9; // rbx
  BOOL v10; // eax
  bool v11; // bl
  const char *v13; // [rsp+28h] [rbp-38h]
  const char *v14; // [rsp+28h] [rbp-38h]
  const char *v15; // [rsp+28h] [rbp-38h]
  const char *v16; // [rsp+28h] [rbp-38h]
  _BYTE v17[8]; // [rsp+30h] [rbp-30h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-28h] BYREF
  HCRYPTKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  HCRYPTPROV phProv; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  hKey = 0;
  phProv = 0;
  v6 = CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000000);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0xCE,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\Certificate.cpp",
    (const char *)v6,
    (bool)"Acquiring cryptographic provider failed",
    v13);
  hHash = 0;
  v7 = CryptCreateHash(phProv, 0x800Cu, 0, 0, &hHash);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0xD2,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\Certificate.cpp",
    (const char *)v7,
    (bool)"Creating hash object failed",
    v14);
  v8 = CryptHashData(hHash, *(const BYTE **)a2, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2, 0);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0xD6,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\Certificate.cpp",
    (const char *)v8,
    (bool)"Computing hash object failed",
    v15);
  v9 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v17);
    CryptDestroyKey(v9);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v17);
  }
  hKey = 0;
  v10 = CryptImportPublicKeyInfo(
          phProv,
          0x10001u,
          (PCERT_PUBLIC_KEY_INFO)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 96LL),
          &hKey);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0xDE,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\Certificate.cpp",
    (const char *)v10,
    (bool)"Importing pubic key failed",
    v16);
  v11 = CryptVerifySignatureW(hHash, *(const BYTE **)a3, *(_DWORD *)(a3 + 8) - *(_DWORD *)a3, hKey, 0, 0);
  if ( hKey )
    CryptDestroyKey(hKey);
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return v11;
}

```

## disassembly

```asm
0x180062994  push    rbp
0x180062996  push    rbx
0x180062997  push    rsi
0x180062998  push    rdi
0x180062999  push    r14
0x18006299b  mov     rbp, rsp
0x18006299e  sub     rsp, 60h
0x1800629a2  mov     rax, cs:__security_cookie
0x1800629a9  xor     rax, rsp
0x1800629ac  mov     [rbp+var_10], rax
0x1800629b0  mov     rdi, r8
0x1800629b3  mov     rsi, rdx
0x1800629b6  mov     r14, rcx
0x1800629b9  mov     [rbp+hHash], 0
0x1800629c1  mov     [rbp+hKey], 0
0x1800629c9  mov     [rbp+phProv], 0
0x1800629d1  mov     [rsp+60h+dwFlags], 0F0000000h; dwFlags
0x1800629d9  mov     r9d, 18h; dwProvType
0x1800629df  xor     r8d, r8d; szProvider
0x1800629e2  xor     edx, edx; szContainer
0x1800629e4  lea     rcx, [rbp+phProv]; phProv
0x1800629e8  call    cs:__imp_CryptAcquireContextW
0x1800629ee  test    eax, eax
0x1800629f0  setnz   al
0x1800629f3  mov     rcx, [rbp+28h]; this
0x1800629f7  lea     rdx, aAcquiringCrypt; "Acquiring cryptographic provider failed"
0x1800629fe  mov     qword ptr [rsp+60h+dwFlags], rdx; bool
0x180062a03  movzx   r9d, al; char *
0x180062a07  lea     r8, aSrcEppDlpEndpo_0; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x180062a0e  mov     edx, 0CEh; void *
0x180062a13  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180062a18  mov     rbx, [rbp+hHash]
0x180062a1c  test    rbx, rbx
0x180062a1f  jz      short loc_180062A3C
0x180062a21  lea     rcx, [rbp+var_30]; this
0x180062a25  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180062a2a  mov     rcx, rbx; hHash
0x180062a2d  call    cs:__imp_CryptDestroyHash
0x180062a33  lea     rcx, [rbp+var_30]; this
0x180062a37  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180062a3c  mov     [rbp+hHash], 0
0x180062a44  lea     rax, [rbp+hHash]
0x180062a48  mov     qword ptr [rsp+60h+dwFlags], rax; phHash
0x180062a4d  xor     r9d, r9d; dwFlags
0x180062a50  xor     r8d, r8d; hKey
0x180062a53  mov     edx, 800Ch; Algid
0x180062a58  mov     rcx, [rbp+phProv]; hProv
0x180062a5c  call    cs:__imp_CryptCreateHash
0x180062a62  test    eax, eax
0x180062a64  setnz   al
0x180062a67  mov     rcx, [rbp+28h]; this
0x180062a6b  lea     rdx, aCreatingHashOb; "Creating hash object failed"
0x180062a72  mov     qword ptr [rsp+60h+dwFlags], rdx; bool
0x180062a77  movzx   r9d, al; char *
0x180062a7b  lea     r8, aSrcEppDlpEndpo_0; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x180062a82  mov     edx, 0D2h; void *
0x180062a87  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180062a8c  mov     r8d, [rsi+8]
0x180062a90  sub     r8d, [rsi]; dwDataLen
0x180062a93  xor     r9d, r9d; dwFlags
0x180062a96  mov     rdx, [rsi]; pbData
0x180062a99  mov     rcx, [rbp+hHash]; hHash
0x180062a9d  call    cs:__imp_CryptHashData
0x180062aa3  test    eax, eax
0x180062aa5  setnz   al
0x180062aa8  mov     rcx, [rbp+28h]; this
0x180062aac  lea     rdx, aComputingHashO; "Computing hash object failed"
0x180062ab3  mov     qword ptr [rsp+60h+dwFlags], rdx; bool
0x180062ab8  movzx   r9d, al; char *
0x180062abc  lea     r8, aSrcEppDlpEndpo_0; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x180062ac3  mov     edx, 0D6h; void *
0x180062ac8  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180062acd  mov     rbx, [rbp+hKey]
0x180062ad1  test    rbx, rbx
0x180062ad4  jz      short loc_180062AF1
0x180062ad6  lea     rcx, [rbp+var_30]; this
0x180062ada  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180062adf  mov     rcx, rbx; hKey
0x180062ae2  call    cs:__imp_CryptDestroyKey
0x180062ae8  lea     rcx, [rbp+var_30]; this
0x180062aec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180062af1  mov     [rbp+hKey], 0
0x180062af9  mov     rax, [r14]
0x180062afc  mov     r8, [rax+18h]
0x180062b00  add     r8, 60h ; '`'; pInfo
0x180062b04  lea     r9, [rbp+hKey]; phKey
0x180062b08  mov     edx, 10001h; dwCertEncodingType
0x180062b0d  mov     rcx, [rbp+phProv]; hCryptProv
0x180062b11  call    cs:__imp_CryptImportPublicKeyInfo
0x180062b17  test    eax, eax
0x180062b19  setnz   al
0x180062b1c  mov     rcx, [rbp+28h]; this
0x180062b20  lea     rdx, aImportingPubic; "Importing pubic key failed"
0x180062b27  mov     qword ptr [rsp+60h+dwFlags], rdx; bool
0x180062b2c  movzx   r9d, al; char *
0x180062b30  lea     r8, aSrcEppDlpEndpo_0; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x180062b37  mov     edx, 0DEh; void *
0x180062b3c  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180062b41  mov     r8d, [rdi+8]
0x180062b45  sub     r8d, [rdi]; dwSigLen
0x180062b48  mov     dword ptr [rsp+60h+var_38], 0; dwFlags
0x180062b50  mov     qword ptr [rsp+60h+dwFlags], 0; szDescription
0x180062b59  mov     r9, [rbp+hKey]; hPubKey
0x180062b5d  mov     rdx, [rdi]; pbSignature
0x180062b60  mov     rcx, [rbp+hHash]; hHash
0x180062b64  call    cs:__imp_CryptVerifySignatureW
0x180062b6a  nop
0x180062b6b  cmp     eax, 1
0x180062b6e  setz    bl
0x180062b71  mov     rcx, [rbp+hKey]; hKey
0x180062b75  test    rcx, rcx
0x180062b78  jz      short loc_180062B81
0x180062b7a  call    cs:__imp_CryptDestroyKey
0x180062b80  nop
0x180062b81  mov     rcx, [rbp+hHash]; hHash
0x180062b85  test    rcx, rcx
0x180062b88  jz      short loc_180062B91
0x180062b8a  call    cs:__imp_CryptDestroyHash
0x180062b90  nop
0x180062b91  mov     rcx, [rbp+phProv]; hProv
0x180062b95  test    rcx, rcx
0x180062b98  jz      short loc_180062BA2
0x180062b9a  xor     edx, edx; dwFlags
0x180062b9c  call    cs:__imp_CryptReleaseContext
0x180062ba2  mov     al, bl
0x180062ba4  mov     rcx, [rbp+var_10]
0x180062ba8  xor     rcx, rsp; StackCookie
0x180062bab  call    __security_check_cookie
0x180062bb0  add     rsp, 60h
0x180062bb4  pop     r14
0x180062bb6  pop     rdi
0x180062bb7  pop     rsi
0x180062bb8  pop     rbx
0x180062bb9  pop     rbp
0x180062bba  retn
```
