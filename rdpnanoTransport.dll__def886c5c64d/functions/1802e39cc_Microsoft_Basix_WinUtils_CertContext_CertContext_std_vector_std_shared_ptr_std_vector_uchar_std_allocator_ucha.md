# Microsoft::Basix::WinUtils::CertContext::CertContext(std::vector<std::shared_ptr<std::vector<uchar,std::allocator<uchar>>>,std::allocator<std::shared_ptr<std::vector<uchar,std::allocator<uchar>>>>> const &)

- ea: `0x1802e39cc`
- end: `0x1802e3c03`
- name: `??0CertContext@WinUtils@Basix@Microsoft@@QEAA@AEBV?$vector@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@V?$allocator@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@2@@std@@@Z`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1802e2950`

## callees

- `0x180024700`
- `0x1802e39cc`
- `0x1802e3f10`
- `0x1802e9b68`
- `0x18032f050`
- `0x180330b40`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x1802e3a76`
- `CRYPT32!CertOpenStore` at `0x1802e3a76`
- `CRYPT32!CertCreateCertificateContext` at `0x1802e3a38`
- `CRYPT32!CertCreateCertificateContext` at `0x1802e3ab8`
- `CRYPT32!CertCreateCertificateContext` at `0x1802e3a38`
- `CRYPT32!CertCreateCertificateContext` at `0x1802e3ab8`
- `CRYPT32!CertFreeCertificateContext` at `0x1802e3add`
- `CRYPT32!CertFreeCertificateContext` at `0x1802e3add`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1802e3ad4`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1802e3ad4`

## string_xrefs

- `0x1802e3bca`: `CertCreateCertificateContext failed`
- `0x1802e3b36`: `Failed to open temporary store`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Basix::WinUtils::CertContext::CertContext(__int64 a1, __int64 a2)
{
  PCCERT_CONTEXT CertificateContext; // rax
  HCERTSTORE v5; // rax
  unsigned __int64 v6; // rsi
  const BYTE ***v7; // rcx
  __int64 v8; // r14
  const CERT_CONTEXT *v9; // rax
  const CERT_CONTEXT *v10; // r15
  _BYTE v12[32]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+70h] [rbp-39h] BYREF

  *(_QWORD *)a1 = &Microsoft::Basix::WinUtils::CertContext::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  if ( *(_QWORD *)a2 == *(_QWORD *)(a2 + 8) )
  {
    std::string::string(v12, "C:\\__w\\1\\s\\src\\libbasix\\winutils\\windowscertcontext.cpp");
    std::string::string(v13, "Certificate chain is empty!");
    Microsoft::Basix::Exception::Exception(pExceptionObject, v13, v12, 135);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  CertificateContext = CertCreateCertificateContext(
                         0x10001u,
                         ***(const BYTE ****)a2,
                         *(_DWORD *)(**(_QWORD **)a2 + 8LL) - ***(_DWORD ***)a2);
  *(_QWORD *)(a1 + 16) = CertificateContext;
  if ( !CertificateContext )
  {
    std::string::string(v13, "C:\\__w\\1\\s\\src\\libbasix\\winutils\\windowscertcontext.cpp");
    std::string::string(v12, "CertCreateCertificateContext failed");
    Microsoft::Basix::Exception::Exception(pExceptionObject, v12, v13, 143);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  if ( (unsigned __int64)((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 4) > 1 )
  {
    v5 = CertOpenStore((LPCSTR)2, 1u, 0, 0, 0);
    *(_QWORD *)(a1 + 8) = v5;
    if ( !v5 )
    {
      std::string::string(v13, "C:\\__w\\1\\s\\src\\libbasix\\winutils\\windowscertcontext.cpp");
      std::string::string(v12, "Failed to open temporary store");
      Microsoft::Basix::Exception::Exception(pExceptionObject, v12, v13, 148);
      throw (Microsoft::Basix::Exception *)pExceptionObject;
    }
    v6 = 1;
    v7 = *(const BYTE ****)a2;
    if ( (unsigned __int64)((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 4) > 1 )
    {
      v8 = 2;
      do
      {
        v9 = CertCreateCertificateContext(0x10001u, *v7[v8], *((_DWORD *)v7[v8] + 2) - *(_DWORD *)v7[v8]);
        v10 = v9;
        if ( v9 )
        {
          CertAddCertificateContextToStore(*(HCERTSTORE *)(a1 + 8), v9, 3u, 0);
          CertFreeCertificateContext(v10);
        }
        ++v6;
        v8 += 2;
        v7 = *(const BYTE ****)a2;
      }
      while ( v6 < (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 4 );
    }
  }
  Microsoft::Basix::WinUtils::CertContext::BuildCertificateChain((Microsoft::Basix::WinUtils::CertContext *)a1);
  return a1;
}

```

## disassembly

```asm
0x1802e39cc  mov     rax, rsp
0x1802e39cf  mov     [rax+8], rbx
0x1802e39d3  mov     [rax+10h], rsi
0x1802e39d7  mov     [rax+18h], rdi
0x1802e39db  push    rbp
0x1802e39dc  push    r14
0x1802e39de  push    r15
0x1802e39e0  lea     rbp, [rax-5Fh]
0x1802e39e4  mov     eax, 0F0h
0x1802e39e9  call    _alloca_probe
0x1802e39ee  sub     rsp, rax
0x1802e39f1  mov     rdi, rdx
0x1802e39f4  mov     rbx, rcx
0x1802e39f7  lea     rax, ??_7CertContext@WinUtils@Basix@Microsoft@@6B@; const Microsoft::Basix::WinUtils::CertContext::`vftable'
0x1802e39fe  mov     [rcx], rax
0x1802e3a01  mov     qword ptr [rcx+8], 0
0x1802e3a09  mov     qword ptr [rcx+10h], 0
0x1802e3a11  mov     qword ptr [rcx+18h], 0
0x1802e3a19  mov     rax, [rdx]
0x1802e3a1c  cmp     rax, [rdx+8]
0x1802e3a20  jz      loc_1802E3B6F
0x1802e3a26  mov     rax, [rax]
0x1802e3a29  mov     r8d, [rax+8]
0x1802e3a2d  sub     r8d, [rax]; cbCertEncoded
0x1802e3a30  mov     rdx, [rax]; pbCertEncoded
0x1802e3a33  mov     ecx, 10001h; dwCertEncodingType
0x1802e3a38  call    cs:__imp_CertCreateCertificateContext
0x1802e3a3e  mov     [rbx+10h], rax
0x1802e3a42  test    rax, rax
0x1802e3a45  jz      loc_1802E3BB9
0x1802e3a4b  mov     rax, [rdi+8]
0x1802e3a4f  sub     rax, [rdi]
0x1802e3a52  sar     rax, 4
0x1802e3a56  cmp     rax, 1
0x1802e3a5a  jbe     loc_1802E3AFD
0x1802e3a60  mov     [rsp+100h+pvPara], 0; pvPara
0x1802e3a69  xor     r9d, r9d; dwFlags
0x1802e3a6c  xor     r8d, r8d; hCryptProv
0x1802e3a6f  lea     edx, [r9+1]; dwEncodingType
0x1802e3a73  lea     ecx, [rdx+1]; lpszStoreProvider
0x1802e3a76  call    cs:__imp_CertOpenStore
0x1802e3a7c  mov     [rbx+8], rax
0x1802e3a80  test    rax, rax
0x1802e3a83  jz      loc_1802E3B25
0x1802e3a89  mov     esi, 1
0x1802e3a8e  mov     rcx, [rdi]
0x1802e3a91  mov     rax, [rdi+8]
0x1802e3a95  sub     rax, rcx
0x1802e3a98  sar     rax, 4
0x1802e3a9c  cmp     rax, rsi
0x1802e3a9f  jbe     short loc_1802E3AFD
0x1802e3aa1  lea     r14d, [rsi+0Fh]
0x1802e3aa5  mov     rax, [r14+rcx]
0x1802e3aa9  mov     r8d, [rax+8]
0x1802e3aad  sub     r8d, [rax]; cbCertEncoded
0x1802e3ab0  mov     rdx, [rax]; pbCertEncoded
0x1802e3ab3  mov     ecx, 10001h; dwCertEncodingType
0x1802e3ab8  call    cs:__imp_CertCreateCertificateContext
0x1802e3abe  mov     r15, rax
0x1802e3ac1  test    rax, rax
0x1802e3ac4  jz      short loc_1802E3AE3
0x1802e3ac6  xor     r9d, r9d; ppStoreContext
0x1802e3ac9  lea     r8d, [r9+3]; dwAddDisposition
0x1802e3acd  mov     rdx, rax; pCertContext
0x1802e3ad0  mov     rcx, [rbx+8]; hCertStore
0x1802e3ad4  call    cs:__imp_CertAddCertificateContextToStore
0x1802e3ada  mov     rcx, r15; pCertContext
0x1802e3add  call    cs:__imp_CertFreeCertificateContext
0x1802e3ae3  inc     rsi
0x1802e3ae6  add     r14, 10h
0x1802e3aea  mov     rcx, [rdi]
0x1802e3aed  mov     rax, [rdi+8]
0x1802e3af1  sub     rax, rcx
0x1802e3af4  sar     rax, 4
0x1802e3af8  cmp     rsi, rax
0x1802e3afb  jb      short loc_1802E3AA5
0x1802e3afd  mov     rcx, rbx; this
0x1802e3b00  call    ?BuildCertificateChain@CertContext@WinUtils@Basix@Microsoft@@IEAAXXZ; Microsoft::Basix::WinUtils::CertContext::BuildCertificateChain(void)
0x1802e3b05  mov     rax, rbx
0x1802e3b08  lea     r11, [rsp+100h+var_10]
0x1802e3b10  mov     rbx, [r11+20h]
0x1802e3b14  mov     rsi, [r11+28h]
0x1802e3b18  mov     rdi, [r11+30h]
0x1802e3b1c  mov     rsp, r11
0x1802e3b1f  pop     r15
0x1802e3b21  pop     r14
0x1802e3b23  pop     rbp
0x1802e3b24  retn
0x1802e3b25  lea     rdx, aCW1SSrcLibbasi_20; "C:\\__w\\1\\s\\src\\libbasix\\winutils"...
0x1802e3b2c  lea     rcx, [rbp+57h+var_B0]
0x1802e3b30  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802e3b35  nop
0x1802e3b36  lea     rdx, aFailedToOpenTe; "Failed to open temporary store"
0x1802e3b3d  lea     rcx, [rbp+57h+var_D0]
0x1802e3b41  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802e3b46  nop
0x1802e3b47  mov     r9d, 94h
0x1802e3b4d  lea     r8, [rbp+57h+var_B0]
0x1802e3b51  lea     rdx, [rbp+57h+var_D0]
0x1802e3b55  lea     rcx, [rbp+57h+pExceptionObject]
0x1802e3b59  call    ??0Exception@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0_K@Z; Microsoft::Basix::Exception::Exception(std::string const &,std::string const &,unsigned __int64)
0x1802e3b5e  lea     rdx, _TI4?AVException@Basix@Microsoft@@; pThrowInfo
0x1802e3b65  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1802e3b69  call    _CxxThrowException
0x1802e3b6f  lea     rdx, aCW1SSrcLibbasi_20; "C:\\__w\\1\\s\\src\\libbasix\\winutils"...
0x1802e3b76  lea     rcx, [rbp+57h+var_D0]
0x1802e3b7a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802e3b7f  nop
0x1802e3b80  lea     rdx, aCertificateCha; "Certificate chain is empty!"
0x1802e3b87  lea     rcx, [rbp+57h+var_B0]
0x1802e3b8b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802e3b90  nop
0x1802e3b91  mov     r9d, 87h
0x1802e3b97  lea     r8, [rbp+57h+var_D0]
0x1802e3b9b  lea     rdx, [rbp+57h+var_B0]
0x1802e3b9f  lea     rcx, [rbp+57h+pExceptionObject]
0x1802e3ba3  call    ??0Exception@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0_K@Z; Microsoft::Basix::Exception::Exception(std::string const &,std::string const &,unsigned __int64)
0x1802e3ba8  lea     rdx, _TI4?AVException@Basix@Microsoft@@; pThrowInfo
0x1802e3baf  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1802e3bb3  call    _CxxThrowException
0x1802e3bb9  lea     rdx, aCW1SSrcLibbasi_20; "C:\\__w\\1\\s\\src\\libbasix\\winutils"...
0x1802e3bc0  lea     rcx, [rbp+57h+var_B0]
0x1802e3bc4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802e3bc9  nop
0x1802e3bca  lea     rdx, aCertcreatecert; "CertCreateCertificateContext failed"
0x1802e3bd1  lea     rcx, [rbp+57h+var_D0]
0x1802e3bd5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802e3bda  nop
0x1802e3bdb  mov     r9d, 8Fh
0x1802e3be1  lea     r8, [rbp+57h+var_B0]
0x1802e3be5  lea     rdx, [rbp+57h+var_D0]
0x1802e3be9  lea     rcx, [rbp+57h+pExceptionObject]
0x1802e3bed  call    ??0Exception@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0_K@Z; Microsoft::Basix::Exception::Exception(std::string const &,std::string const &,unsigned __int64)
0x1802e3bf2  lea     rdx, _TI4?AVException@Basix@Microsoft@@; pThrowInfo
0x1802e3bf9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1802e3bfd  call    _CxxThrowException
```
