# ValidateCertificate(uchar * const,ulong)

- ea: `0x18000ee24`
- end: `0x18000ef4b`
- name: `?ValidateCertificate@@YAJQEAEK@Z`
- size: `295`
- prototype: `__int64 __fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e6e0`

## callees

- `0x180006954`
- `0x180006974`
- `0x18000ee24`

## import_xrefs

- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18000ee9c`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18000ee9c`
- `CRYPT32!CertOpenStore` at `0x18000ee50`
- `CRYPT32!CertOpenStore` at `0x18000ee50`
- `CRYPT32!CertFindCertificateInStore` at `0x18000eee4`
- `CRYPT32!CertFindCertificateInStore` at `0x18000eee4`
- `CRYPT32!CertCloseStore` at `0x18000ef2c`
- `CRYPT32!CertCloseStore` at `0x18000ef2c`
- `CRYPT32!CertFreeCertificateContext` at `0x18000ef16`
- `CRYPT32!CertFreeCertificateContext` at `0x18000ef16`

## pseudocode

```c
__int64 __fastcall ValidateCertificate(BYTE *pbCertEncoded, DWORD cbCertEncoded)
{
  HCERTSTORE v4; // rax
  const char *v5; // r9
  void *v6; // rdi
  const char *v8; // r9
  unsigned int LastError; // ebx
  const CERT_CONTEXT *CertificateInStore; // rax
  int pvPara; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = CertOpenStore((LPCSTR)2, 0x10001u, 0, 0, 0);
  v6 = v4;
  if ( !v4 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1D,
             (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
             v5);
  if ( CertAddEncodedCertificateToStore(v4, 0x10001u, pbCertEncoded, cbCertEncoded, 1u, 0) )
  {
    CertificateInStore = CertFindCertificateInStore(v6, 0x10001u, 0, 0, 0, 0);
    if ( CertificateInStore )
    {
      CertFreeCertificateContext(CertificateInStore);
      LastError = 0;
    }
    else
    {
      LastError = -2046820335;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
        (const char *)0x86000011LL,
        pvPara);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x20,
                  (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
                  v8);
  }
  CertCloseStore(v6, 1u);
  return LastError;
}

```

## disassembly

```asm
0x18000ee24  mov     [rsp+arg_0], rbx
0x18000ee29  mov     [rsp+arg_8], rsi
0x18000ee2e  push    rdi
0x18000ee2f  sub     rsp, 30h
0x18000ee33  xor     r9d, r9d; dwFlags
0x18000ee36  mov     [rsp+38h+pvPara], 0; pvPara
0x18000ee3f  mov     ebx, edx
0x18000ee41  mov     rsi, rcx
0x18000ee44  xor     r8d, r8d; hCryptProv
0x18000ee47  mov     edx, 10001h; dwEncodingType
0x18000ee4c  lea     ecx, [r9+2]; lpszStoreProvider
0x18000ee50  call    cs:__imp_CertOpenStore
0x18000ee57  nop     dword ptr [rax+rax+00h]
0x18000ee5c  mov     rdi, rax
0x18000ee5f  test    rax, rax
0x18000ee62  jnz     short loc_18000EE7D
0x18000ee64  mov     rcx, [rsp+38h]; this
0x18000ee69  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000ee70  lea     edx, [rax+1Dh]; void *
0x18000ee73  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ee78  jmp     loc_18000EF3A
0x18000ee7d  mov     [rsp+38h+ppCertContext], 0; ppCertContext
0x18000ee86  mov     r9d, ebx; cbCertEncoded
0x18000ee89  mov     r8, rsi; pbCertEncoded
0x18000ee8c  mov     dword ptr [rsp+38h+pvPara], 1; dwAddDisposition
0x18000ee94  mov     edx, 10001h; dwCertEncodingType
0x18000ee99  mov     rcx, rdi; hCertStore
0x18000ee9c  call    cs:__imp_CertAddEncodedCertificateToStore
0x18000eea3  nop     dword ptr [rax+rax+00h]
0x18000eea8  test    eax, eax
0x18000eeaa  jnz     short loc_18000EEC4
0x18000eeac  mov     rcx, [rsp+38h]; this
0x18000eeb1  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000eeb8  lea     edx, [rax+20h]; void *
0x18000eebb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000eec0  mov     ebx, eax
0x18000eec2  jmp     short loc_18000EF24
0x18000eec4  mov     [rsp+38h+ppCertContext], 0; pPrevCertContext
0x18000eecd  xor     r9d, r9d; dwFindType
0x18000eed0  xor     r8d, r8d; dwFindFlags
0x18000eed3  mov     [rsp+38h+pvPara], 0; int
0x18000eedc  mov     edx, 10001h; dwCertEncodingType
0x18000eee1  mov     rcx, rdi; hCertStore
0x18000eee4  call    cs:__imp_CertFindCertificateInStore
0x18000eeeb  nop     dword ptr [rax+rax+00h]
0x18000eef0  test    rax, rax
0x18000eef3  jnz     short loc_18000EF13
0x18000eef5  mov     rcx, [rsp+38h]; this
0x18000eefa  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000ef01  mov     ebx, 86000011h
0x18000ef06  lea     edx, [rax+24h]; void *
0x18000ef09  mov     r9d, ebx; char *
0x18000ef0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef11  jmp     short loc_18000EF24
0x18000ef13  mov     rcx, rax; pCertContext
0x18000ef16  call    cs:__imp_CertFreeCertificateContext
0x18000ef1d  nop     dword ptr [rax+rax+00h]
0x18000ef22  xor     ebx, ebx
0x18000ef24  mov     edx, 1; dwFlags
0x18000ef29  mov     rcx, rdi; hCertStore
0x18000ef2c  call    cs:__imp_CertCloseStore
0x18000ef33  nop     dword ptr [rax+rax+00h]
0x18000ef38  mov     eax, ebx
0x18000ef3a  mov     rbx, [rsp+38h+arg_0]
0x18000ef3f  mov     rsi, [rsp+38h+arg_8]
0x18000ef44  add     rsp, 30h
0x18000ef48  pop     rdi
0x18000ef49  retn
```
