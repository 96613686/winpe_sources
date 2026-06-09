# Microsoft::Diagnostics::XmlFileSignatureVerifier::GenerateCertificateStoreFromKeyInfo(_CRYPT_XML_KEY_INFO const &,void * *)

- ea: `0x180118480`
- end: `0x180118594`
- name: `?GenerateCertificateStoreFromKeyInfo@XmlFileSignatureVerifier@Diagnostics@Microsoft@@CAJAEBU_CRYPT_XML_KEY_INFO@@PEAPEAX@Z`
- size: `276`
- prototype: `__int64 __fastcall(const struct _CRYPT_XML_KEY_INFO *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801179ec`

## callees

- `0x180064e6c`
- `0x180118480`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x180118535`
- `CRYPT32!CertFreeCertificateContext` at `0x180118582`
- `CRYPT32!CertFreeCertificateContext` at `0x180118535`
- `CRYPT32!CertFreeCertificateContext` at `0x180118582`
- `CRYPT32!CertOpenStore` at `0x1801184af`
- `CRYPT32!CertOpenStore` at `0x1801184af`
- `CRYPT32!CertCreateCertificateContext` at `0x18011850d`
- `CRYPT32!CertCreateCertificateContext` at `0x18011850d`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180118528`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180118528`
- `CRYPT32!CertCloseStore` at `0x18011855a`
- `CRYPT32!CertCloseStore` at `0x18011855a`

## string_xrefs

- `0x1801184c2`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x180118542`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x18011856c`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::XmlFileSignatureVerifier::GenerateCertificateStoreFromKeyInfo(
        const struct _CRYPT_XML_KEY_INFO *a1,
        void **a2)
{
  HCERTSTORE v4; // rbx
  const char *v5; // r9
  UINT i; // esi
  CRYPT_XML_KEY_INFO_ITEM *rgKeyInfo; // rax
  unsigned __int64 v9; // rdx
  const CERT_CONTEXT *CertificateContext; // rax
  const char *v11; // r9
  const CERT_CONTEXT *v12; // rdi
  const char *v13; // r9
  unsigned int LastError; // esi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a2 = 0;
  v4 = CertOpenStore((LPCSTR)2, 0, 0, 0x2000u, 0);
  if ( !v4 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x14,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
             v5);
  for ( i = 0; i < a1->cKeyInfo; ++i )
  {
    rgKeyInfo = a1->rgKeyInfo;
    v9 = (unsigned __int64)i << 7;
    if ( *(DWORD *)((char *)&rgKeyInfo->dwType + v9) == 4 )
    {
      CertificateContext = CertCreateCertificateContext(
                             1u,
                             (*(const BYTE ***)((char *)&rgKeyInfo->KeyValue.ECDSAKeyValue.wszNamedCurve + v9))[2],
                             (*(_DWORD **)((char *)&rgKeyInfo->KeyValue.ECDSAKeyValue.wszNamedCurve + v9))[2]);
      v12 = CertificateContext;
      if ( !CertificateContext )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1E,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                      v11);
LABEL_11:
        CertCloseStore(v4, 0);
        return LastError;
      }
      if ( !CertAddCertificateContextToStore(v4, CertificateContext, 3u, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1F,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                      v13);
        CertFreeCertificateContext(v12);
        goto LABEL_11;
      }
      CertFreeCertificateContext(v12);
    }
  }
  *a2 = v4;
  return 0;
}

```

## disassembly

```asm
0x180118480  push    rbx
0x180118482  push    rbp
0x180118483  push    rsi
0x180118484  push    rdi
0x180118485  push    r14
0x180118487  sub     rsp, 30h
0x18011848b  mov     r14, rdx
0x18011848e  mov     qword ptr [rdx], 0
0x180118495  xor     edx, edx; dwEncodingType
0x180118497  mov     [rsp+58h+pvPara], 0; pvPara
0x1801184a0  mov     rbp, rcx
0x1801184a3  mov     r9d, 2000h; dwFlags
0x1801184a9  xor     r8d, r8d; hCryptProv
0x1801184ac  lea     ecx, [rdx+2]; lpszStoreProvider
0x1801184af  call    cs:__imp_CertOpenStore
0x1801184b5  mov     rbx, rax
0x1801184b8  test    rax, rax
0x1801184bb  jnz     short loc_1801184DC
0x1801184bd  mov     rcx, [rsp+58h]; this
0x1801184c2  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x1801184c9  lea     edx, [rax+14h]; void *
0x1801184cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801184d1  add     rsp, 30h
0x1801184d5  pop     r14
0x1801184d7  pop     rdi
0x1801184d8  pop     rsi
0x1801184d9  pop     rbp
0x1801184da  pop     rbx
0x1801184db  retn
0x1801184dc  xor     esi, esi
0x1801184de  cmp     esi, [rbp+10h]
0x1801184e1  jnb     loc_18011858A
0x1801184e7  mov     rax, [rbp+18h]
0x1801184eb  mov     edx, esi
0x1801184ed  shl     rdx, 7
0x1801184f1  cmp     dword ptr [rdx+rax], 4
0x1801184f5  jz      short loc_1801184FB
0x1801184f7  inc     esi
0x1801184f9  jmp     short loc_1801184DE
0x1801184fb  mov     rdx, [rdx+rax+10h]
0x180118500  mov     ecx, 1; dwCertEncodingType
0x180118505  mov     r8d, [rdx+8]; cbCertEncoded
0x180118509  mov     rdx, [rdx+10h]; pbCertEncoded
0x18011850d  call    cs:__imp_CertCreateCertificateContext
0x180118513  mov     rdi, rax
0x180118516  test    rax, rax
0x180118519  jz      short loc_18011853D
0x18011851b  xor     r9d, r9d; ppStoreContext
0x18011851e  mov     rdx, rax; pCertContext
0x180118521  mov     rcx, rbx; hCertStore
0x180118524  lea     r8d, [r9+3]; dwAddDisposition
0x180118528  call    cs:__imp_CertAddCertificateContextToStore
0x18011852e  test    eax, eax
0x180118530  jz      short loc_180118567
0x180118532  mov     rcx, rdi; pCertContext
0x180118535  call    cs:__imp_CertFreeCertificateContext
0x18011853b  jmp     short loc_1801184F7
0x18011853d  mov     rcx, [rsp+58h]; this
0x180118542  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180118549  mov     edx, 1Eh; void *
0x18011854e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180118553  mov     esi, eax
0x180118555  xor     edx, edx; dwFlags
0x180118557  mov     rcx, rbx; hCertStore
0x18011855a  call    cs:__imp_CertCloseStore
0x180118560  mov     eax, esi
0x180118562  jmp     loc_1801184D1
0x180118567  mov     rcx, [rsp+58h]; this
0x18011856c  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x180118573  mov     edx, 1Fh; void *
0x180118578  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011857d  mov     rcx, rdi; pCertContext
0x180118580  mov     esi, eax
0x180118582  call    cs:__imp_CertFreeCertificateContext
0x180118588  jmp     short loc_180118555
0x18011858a  mov     [r14], rbx
0x18011858d  xor     eax, eax
0x18011858f  jmp     loc_1801184D1
```
