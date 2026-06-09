# TLSSaveCertAsPKCS7

- ea: `0x180044cb8`
- end: `0x180044f13`
- name: `TLSSaveCertAsPKCS7`
- size: `603`
- prototype: `__int64 __fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012ee0`

## callees

- `0x180022910`
- `0x180044bb0`
- `0x180044cb8`

## import_xrefs

- `CRYPT32!CertSaveStore` at `0x180044e26`
- `CRYPT32!CertSaveStore` at `0x180044eaa`
- `CRYPT32!CertSaveStore` at `0x180044e26`
- `CRYPT32!CertSaveStore` at `0x180044eaa`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180044d9b`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180044d9b`
- `CRYPT32!CertOpenStore` at `0x180044cfb`
- `CRYPT32!CertOpenStore` at `0x180044cfb`
- `CRYPT32!CertCreateCertificateContext` at `0x180044d4a`
- `CRYPT32!CertCreateCertificateContext` at `0x180044d4a`
- `CRYPT32!CertFreeCertificateContext` at `0x180044ecb`
- `CRYPT32!CertFreeCertificateContext` at `0x180044ecb`
- `CRYPT32!CertCloseStore` at `0x180044edf`
- `CRYPT32!CertCloseStore` at `0x180044edf`
- `KERNEL32!GetLastError` at `0x180044d0f`
- `KERNEL32!GetLastError` at `0x180044d5e`
- `KERNEL32!GetLastError` at `0x180044dab`
- `KERNEL32!GetLastError` at `0x180044e36`
- `KERNEL32!GetLastError` at `0x180044e4b`
- `KERNEL32!GetLastError` at `0x180044e7e`
- `KERNEL32!GetLastError` at `0x180044d0f`
- `KERNEL32!GetLastError` at `0x180044d5e`
- `KERNEL32!GetLastError` at `0x180044dab`
- `KERNEL32!GetLastError` at `0x180044e36`
- `KERNEL32!GetLastError` at `0x180044e4b`
- `KERNEL32!GetLastError` at `0x180044e7e`
- `KERNEL32!LocalAlloc` at `0x180044e69`
- `KERNEL32!LocalAlloc` at `0x180044e69`

## pseudocode

```c
__int64 __fastcall TLSSaveCertAsPKCS7(BYTE *pbCertEncoded, DWORD cbCertEncoded, _QWORD *a3, _DWORD *a4)
{
  __int64 LastError; // rbx
  HCERTSTORE v9; // rdi
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v11; // rsi
  __int64 v12; // rcx
  DWORD v13; // eax
  unsigned int v14; // edx
  SIZE_T uBytes[2]; // [rsp+30h] [rbp-20h] BYREF
  struct _EVENT_DESCRIPTOR v17; // [rsp+40h] [rbp-10h] BYREF

  LODWORD(LastError) = 0;
  v9 = CertOpenStore((LPCSTR)2, 0x10001u, g_RdlsCryptProv, 1u, 0);
  if ( v9 )
  {
    CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
    v11 = CertificateContext;
    if ( !CertificateContext )
    {
      LastError = GetLastError();
      v17 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
      TLSLogEvent(&v17, 0xC0110004, LastError);
LABEL_19:
      CertCloseStore(v9, 1u);
      return (_DWORD)LastError != 0 ? 0xC0110011 : 0;
    }
    if ( !CertAddCertificateContextToStore(v9, CertificateContext, 4u, 0)
      || RdlsSecretsCache::g_bHasHydraCert
      && g_hCaStore
      && !(unsigned int)TLSChainIssuerCertificate(v12, g_hCaStore, v9, v11) )
    {
      v13 = GetLastError();
      v14 = -1072627696;
    }
    else
    {
      *(_OWORD *)uBytes = 0;
      if ( CertSaveStore(v9, 0x10001u, 2u, 2u, uBytes, 0)
        || (LODWORD(LastError) = GetLastError(), (_DWORD)LastError == 234) )
      {
        uBytes[1] = (SIZE_T)LocalAlloc(0x40u, LODWORD(uBytes[0]));
        if ( !uBytes[1] )
        {
          LODWORD(LastError) = GetLastError();
          goto LABEL_18;
        }
        if ( CertSaveStore(v9, 0x10001u, 2u, 2u, uBytes, 0) )
        {
          *a3 = uBytes[1];
          *a4 = uBytes[0];
          goto LABEL_18;
        }
      }
      v13 = GetLastError();
      v14 = -1072627695;
    }
    LODWORD(LastError) = v13;
    v17 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
    TLSLogEvent(&v17, v14, v13);
LABEL_18:
    CertFreeCertificateContext(v11);
    goto LABEL_19;
  }
  LastError = GetLastError();
  v17 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
  TLSLogEvent(&v17, 0xC011000F, LastError);
  return (_DWORD)LastError != 0 ? 0xC0110011 : 0;
}

```

## disassembly

```asm
0x180044cb8  mov     rax, rsp
0x180044cbb  mov     [rax+8], rbx
0x180044cbf  mov     [rax+10h], rsi
0x180044cc3  mov     [rax+18h], rdi
0x180044cc7  mov     [rax+20h], r12
0x180044ccb  push    rbp
0x180044ccc  push    r14
0x180044cce  push    r15
0x180044cd0  mov     rbp, rsp
0x180044cd3  sub     rsp, 50h
0x180044cd7  xor     ebx, ebx
0x180044cd9  mov     r15, r9
0x180044cdc  and     [rax-48h], rbx
0x180044ce0  mov     r12, r8
0x180044ce3  mov     r8, cs:?g_RdlsCryptProv@@3VRdlsCryptHandle@@A; hCryptProv
0x180044cea  mov     esi, edx
0x180044cec  mov     r14, rcx
0x180044cef  mov     edx, 10001h; dwEncodingType
0x180044cf4  lea     r9d, [rbx+1]; dwFlags
0x180044cf8  lea     ecx, [rbx+2]; lpszStoreProvider
0x180044cfb  call    cs:__imp_CertOpenStore
0x180044d02  nop     dword ptr [rax+rax+00h]
0x180044d07  mov     rdi, rax
0x180044d0a  test    rax, rax
0x180044d0d  jnz     short loc_180044D3F
0x180044d0f  call    cs:__imp_GetLastError
0x180044d16  nop     dword ptr [rax+rax+00h]
0x180044d1b  movups  xmm0, cs:TLS_E_GENERATECLIENTELICENSE
0x180044d22  mov     r8d, eax
0x180044d25  lea     rcx, [rbp+var_10]; struct _EVENT_DESCRIPTOR
0x180044d29  mov     edx, 0C011000Fh; unsigned int
0x180044d2e  mov     ebx, eax
0x180044d30  movdqu  xmmword ptr [rbp+var_10.Id], xmm0
0x180044d35  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180044d3a  jmp     loc_180044EEB
0x180044d3f  mov     r8d, esi; cbCertEncoded
0x180044d42  mov     rdx, r14; pbCertEncoded
0x180044d45  mov     ecx, 1; dwCertEncodingType
0x180044d4a  call    cs:__imp_CertCreateCertificateContext
0x180044d51  nop     dword ptr [rax+rax+00h]
0x180044d56  mov     rsi, rax
0x180044d59  test    rax, rax
0x180044d5c  jnz     short loc_180044D8E
0x180044d5e  call    cs:__imp_GetLastError
0x180044d65  nop     dword ptr [rax+rax+00h]
0x180044d6a  movups  xmm0, cs:TLS_E_GENERATECLIENTELICENSE
0x180044d71  mov     r8d, eax
0x180044d74  lea     rcx, [rbp+var_10]; struct _EVENT_DESCRIPTOR
0x180044d78  mov     edx, 0C0110004h; unsigned int
0x180044d7d  mov     ebx, eax
0x180044d7f  movdqu  xmmword ptr [rbp+var_10.Id], xmm0
0x180044d84  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180044d89  jmp     loc_180044ED7
0x180044d8e  xor     r9d, r9d; ppStoreContext
0x180044d91  mov     rdx, rsi; pCertContext
0x180044d94  mov     rcx, rdi; hCertStore
0x180044d97  lea     r8d, [r9+4]; dwAddDisposition
0x180044d9b  call    cs:__imp_CertAddCertificateContextToStore
0x180044da2  nop     dword ptr [rax+rax+00h]
0x180044da7  test    eax, eax
0x180044da9  jnz     short loc_180044DDB
0x180044dab  call    cs:__imp_GetLastError
0x180044db2  nop     dword ptr [rax+rax+00h]
0x180044db7  mov     edx, 0C0110010h; unsigned int
0x180044dbc  movups  xmm0, cs:TLS_E_GENERATECLIENTELICENSE
0x180044dc3  mov     r8d, eax
0x180044dc6  lea     rcx, [rbp+var_10]; struct _EVENT_DESCRIPTOR
0x180044dca  mov     ebx, eax
0x180044dcc  movdqu  xmmword ptr [rbp+var_10.Id], xmm0
0x180044dd1  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180044dd6  jmp     loc_180044EC8
0x180044ddb  cmp     cs:?g_bHasHydraCert@RdlsSecretsCache@@2HA, ebx; int RdlsSecretsCache::g_bHasHydraCert
0x180044de1  jz      short loc_180044DFE
0x180044de3  mov     rdx, cs:?g_hCaStore@@3PEAXEA; void * g_hCaStore
0x180044dea  test    rdx, rdx
0x180044ded  jz      short loc_180044DFE
0x180044def  mov     r9, rsi
0x180044df2  mov     r8, rdi
0x180044df5  call    TLSChainIssuerCertificate
0x180044dfa  test    eax, eax
0x180044dfc  jz      short loc_180044DAB
0x180044dfe  and     [rsp+50h+var_28], ebx
0x180044e02  lea     rax, [rbp+uBytes]
0x180044e06  mov     r14d, 2
0x180044e0c  mov     [rsp+50h+pvSaveToPara], rax; pvSaveToPara
0x180044e11  xorps   xmm0, xmm0
0x180044e14  mov     r9d, r14d; dwSaveTo
0x180044e17  mov     r8d, r14d; dwSaveAs
0x180044e1a  mov     edx, 10001h; dwEncodingType
0x180044e1f  mov     rcx, rdi; hCertStore
0x180044e22  movups  xmmword ptr [rbp+uBytes], xmm0
0x180044e26  call    cs:__imp_CertSaveStore
0x180044e2d  nop     dword ptr [rax+rax+00h]
0x180044e32  test    eax, eax
0x180044e34  jnz     short loc_180044E61
0x180044e36  call    cs:__imp_GetLastError
0x180044e3d  nop     dword ptr [rax+rax+00h]
0x180044e42  mov     ebx, eax
0x180044e44  cmp     eax, 0EAh
0x180044e49  jz      short loc_180044E61
0x180044e4b  call    cs:__imp_GetLastError
0x180044e52  nop     dword ptr [rax+rax+00h]
0x180044e57  mov     edx, 0C0110011h
0x180044e5c  jmp     loc_180044DBC
0x180044e61  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180044e64  mov     ecx, 40h ; '@'; uFlags
0x180044e69  call    cs:__imp_LocalAlloc
0x180044e70  nop     dword ptr [rax+rax+00h]
0x180044e75  mov     [rbp+uBytes+8], rax
0x180044e79  test    rax, rax
0x180044e7c  jnz     short loc_180044E8E
0x180044e7e  call    cs:__imp_GetLastError
0x180044e85  nop     dword ptr [rax+rax+00h]
0x180044e8a  mov     ebx, eax
0x180044e8c  jmp     short loc_180044EC8
0x180044e8e  and     [rsp+50h+var_28], 0
0x180044e93  lea     rax, [rbp+uBytes]
0x180044e97  mov     r9d, r14d; dwSaveTo
0x180044e9a  mov     [rsp+50h+pvSaveToPara], rax; pvSaveToPara
0x180044e9f  mov     r8d, r14d; dwSaveAs
0x180044ea2  mov     edx, 10001h; dwEncodingType
0x180044ea7  mov     rcx, rdi; hCertStore
0x180044eaa  call    cs:__imp_CertSaveStore
0x180044eb1  nop     dword ptr [rax+rax+00h]
0x180044eb6  test    eax, eax
0x180044eb8  jz      short loc_180044E4B
0x180044eba  mov     rax, [rbp+uBytes+8]
0x180044ebe  mov     [r12], rax
0x180044ec2  mov     eax, dword ptr [rbp+uBytes]
0x180044ec5  mov     [r15], eax
0x180044ec8  mov     rcx, rsi; pCertContext
0x180044ecb  call    cs:__imp_CertFreeCertificateContext
0x180044ed2  nop     dword ptr [rax+rax+00h]
0x180044ed7  mov     edx, 1; dwFlags
0x180044edc  mov     rcx, rdi; hCertStore
0x180044edf  call    cs:__imp_CertCloseStore
0x180044ee6  nop     dword ptr [rax+rax+00h]
0x180044eeb  lea     r11, [rsp+50h+var_s0]
0x180044ef0  neg     ebx
0x180044ef2  mov     rbx, [r11+20h]
0x180044ef6  mov     rsi, [r11+28h]
0x180044efa  sbb     eax, eax
0x180044efc  mov     rdi, [r11+30h]
0x180044f00  and     eax, 0C0110011h
0x180044f05  mov     r12, [r11+38h]
0x180044f09  mov     rsp, r11
0x180044f0c  pop     r15
0x180044f0e  pop     r14
0x180044f10  pop     rbp
0x180044f11  retn
```
