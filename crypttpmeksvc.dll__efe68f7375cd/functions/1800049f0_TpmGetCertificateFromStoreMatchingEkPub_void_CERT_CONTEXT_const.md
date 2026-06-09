# _TpmGetCertificateFromStoreMatchingEkPub(void *,_CERT_CONTEXT const * *)

- ea: `0x1800049f0`
- end: `0x180004c4a`
- name: `?_TpmGetCertificateFromStoreMatchingEkPub@@YAJPEAXPEAPEBU_CERT_CONTEXT@@@Z`
- size: `602`
- prototype: `__int64 __fastcall(HCERTSTORE hCertStore, const struct _CERT_CONTEXT **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001970`
- `0x180002b10`

## callees

- `0x180003750`
- `0x1800049f0`
- `0x1800052a0`
- `0x18000a7b6`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x180004c25`
- `CRYPT32!CertFreeCertificateContext` at `0x180004c25`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180004b2c`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180004b2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004ac1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004ac1`
- `ncrypt!NCryptOpenStorageProvider` at `0x180004a49`
- `ncrypt!NCryptOpenStorageProvider` at `0x180004a49`
- `ncrypt!NCryptGetProperty` at `0x180004a9f`
- `ncrypt!NCryptGetProperty` at `0x180004a9f`
- `ncrypt!NCryptFreeObject` at `0x180004c0e`
- `ncrypt!NCryptFreeObject` at `0x180004c0e`

## pseudocode

```c
__int64 __fastcall _TpmGetCertificateFromStoreMatchingEkPub(HCERTSTORE hCertStore, const struct _CERT_CONTEXT **a2)
{
  void *v4; // rsi
  const CERT_CONTEXT *v5; // rdi
  unsigned int v6; // ebx
  DWORD v7; // r12d
  NCRYPT_HANDLE v8; // r13
  BYTE *v9; // r15
  SECURITY_STATUS Property; // eax
  const CERT_CONTEXT *v11; // rdx
  const struct _CERT_CONTEXT *v12; // rax
  unsigned int CertificateRsaKeyPublicBlob; // eax
  DWORD *pcbResult; // [rsp+20h] [rbp-58h]
  void *Buf2; // [rsp+30h] [rbp-48h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+38h] [rbp-40h] BYREF
  DWORD v18; // [rsp+90h] [rbp+18h] BYREF
  size_t Size; // [rsp+98h] [rbp+20h] BYREF

  ekTraceFmt(0x53B12C2u, 2, "TRACE: _TpmGetCertificateFromStoreMatchingEkPub start.\n");
  v4 = 0;
  phProvider = 0;
  Buf2 = 0;
  v5 = 0;
  v6 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0x40u);
  if ( !v6 )
  {
    v7 = 0;
    v8 = phProvider;
    v9 = 0;
    while ( 1 )
    {
      v18 = 0;
      Property = NCryptGetProperty(v8, L"PCP_EKPUB", v9, v7, &v18, 0x40u);
      v6 = Property;
      if ( Property )
      {
        LODWORD(pcbResult) = Property;
        ekTraceFmt(0x4912C2u, 1, "ERROR: NCryptGetProperty(%ws) Hr=%x\n", L"PCP_EKPUB", pcbResult);
        goto LABEL_19;
      }
      if ( v9 )
        break;
      v7 = v18;
      v9 = (BYTE *)LocalAlloc(0, v18);
      if ( !v9 )
      {
        v6 = -2147024882;
        ekTraceFmt(0x5C12C2u, 1, "ERROR: LocalAlloc. Return=%d\n", -2147024882);
        goto LABEL_19;
      }
    }
    if ( v7 == v18 )
    {
      LocalFree(0);
      v11 = 0;
      while ( 1 )
      {
        v12 = CertEnumCertificatesInStore(hCertStore, v11);
        v5 = v12;
        if ( !v12 )
          break;
        LODWORD(Size) = 0;
        CertificateRsaKeyPublicBlob = _GetCertificateRsaKeyPublicBlob(
                                        v12,
                                        (unsigned __int8 **)&Buf2,
                                        (unsigned int *)&Size);
        v4 = Buf2;
        v6 = CertificateRsaKeyPublicBlob;
        if ( CertificateRsaKeyPublicBlob )
          goto LABEL_19;
        if ( v7 == (_DWORD)Size && !memcmp_0(v9, Buf2, (unsigned int)Size) )
        {
          *a2 = v5;
          v5 = 0;
          goto LABEL_19;
        }
        LocalFree(v4);
        v4 = 0;
        v11 = v5;
        Buf2 = 0;
      }
      v6 = -2147023728;
    }
    else
    {
      v6 = -2147024736;
      ekTraceFmt(0x5112C2u, 1, "ERROR: cbProp != cbPropT. Hr=%x\n", -2147024736);
    }
LABEL_19:
    LocalFree(v9);
    if ( v4 )
      LocalFree(v4);
  }
  if ( phProvider )
  {
    NCryptFreeObject(phProvider);
    phProvider = 0;
  }
  if ( v5 )
    CertFreeCertificateContext(v5);
  ekTraceFmt(0x58D12C2u, 2, "TRACE: _TpmGetCertificateFromStoreMatchingEkPub end.\n");
  return v6;
}

```

## disassembly

```asm
0x1800049f0  push    rbx
0x1800049f2  push    rdi
0x1800049f3  sub     rsp, 68h
0x1800049f7  mov     [rsp+78h+arg_0], rbp
0x1800049ff  lea     r8, aTraceTpmgetcer; "TRACE: _TpmGetCertificateFromStoreMatch"...
0x180004a06  mov     rbp, rcx
0x180004a09  mov     [rsp+78h+var_18], rsi
0x180004a0e  mov     [rsp+78h+var_30], r14
0x180004a13  mov     ecx, 53B12C2h; unsigned int
0x180004a18  mov     r14, rdx
0x180004a1b  mov     edx, 2; unsigned int
0x180004a20  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004a25  xor     esi, esi
0x180004a27  mov     [rsp+78h+phProvider], 0
0x180004a30  mov     r8d, 40h ; '@'; dwFlags
0x180004a36  mov     [rsp+78h+Buf2], rsi
0x180004a3b  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180004a42  xor     edi, edi
0x180004a44  lea     rcx, [rsp+78h+phProvider]; phProvider
0x180004a49  call    cs:__imp_NCryptOpenStorageProvider
0x180004a4f  mov     ebx, eax
0x180004a51  test    eax, eax
0x180004a53  jnz     loc_180004BF2
0x180004a59  mov     [rsp+78h+var_20], r12
0x180004a5e  xor     r12d, r12d
0x180004a61  mov     [rsp+78h+var_28], r13
0x180004a66  mov     r13, [rsp+78h+phProvider]
0x180004a6b  mov     [rsp+78h+var_38], r15
0x180004a70  xor     r15d, r15d
0x180004a73  lea     rax, [rsp+78h+arg_10]
0x180004a7b  mov     [rsp+78h+dwFlags], 40h ; '@'; dwFlags
0x180004a83  mov     r9d, r12d; cbOutput
0x180004a86  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180004a8b  mov     r8, r15; pbOutput
0x180004a8e  mov     [rsp+78h+arg_10], esi
0x180004a95  lea     rdx, aPcpEkpub; "PCP_EKPUB"
0x180004a9c  mov     rcx, r13; hObject
0x180004a9f  call    cs:__imp_NCryptGetProperty
0x180004aa5  mov     ebx, eax
0x180004aa7  test    eax, eax
0x180004aa9  jnz     loc_180004BAB
0x180004aaf  test    r15, r15
0x180004ab2  jnz     short loc_180004AF2
0x180004ab4  mov     r12d, [rsp+78h+arg_10]
0x180004abc  xor     ecx, ecx; uFlags
0x180004abe  mov     edx, r12d; uBytes
0x180004ac1  call    cs:__imp_LocalAlloc
0x180004ac7  mov     r15, rax
0x180004aca  test    rax, rax
0x180004acd  jnz     short loc_180004A73
0x180004acf  mov     ebx, 8007000Eh
0x180004ad4  lea     r8, aErrorLocalallo_0; "ERROR: LocalAlloc. Return=%d\n"
0x180004adb  mov     r9d, ebx
0x180004ade  mov     edx, 1; unsigned int
0x180004ae3  mov     ecx, 5C12C2h; unsigned int
0x180004ae8  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004aed  jmp     loc_180004BCC
0x180004af2  cmp     r12d, [rsp+78h+arg_10]
0x180004afa  jz      short loc_180004B1F
0x180004afc  mov     ebx, 800700A0h
0x180004b01  lea     r8, aErrorCbpropCbp; "ERROR: cbProp != cbPropT. Hr=%x\n"
0x180004b08  mov     r9d, ebx
0x180004b0b  mov     edx, 1; unsigned int
0x180004b10  mov     ecx, 5112C2h; unsigned int
0x180004b15  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004b1a  jmp     loc_180004BCC
0x180004b1f  xor     ecx, ecx; hMem
0x180004b21  call    cs:__imp_LocalFree
0x180004b27  xor     edx, edx; pPrevCertContext
0x180004b29  mov     rcx, rbp; hCertStore
0x180004b2c  call    cs:__imp_CertEnumCertificatesInStore
0x180004b32  mov     rdi, rax
0x180004b35  test    rax, rax
0x180004b38  jz      short loc_180004B9F
0x180004b3a  lea     r8, [rsp+78h+Size]; unsigned int *
0x180004b42  mov     dword ptr [rsp+78h+Size], 0
0x180004b4d  lea     rdx, [rsp+78h+Buf2]; unsigned __int8 **
0x180004b52  mov     rcx, rax; struct _CERT_CONTEXT *
0x180004b55  call    ?_GetCertificateRsaKeyPublicBlob@@YAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z; _GetCertificateRsaKeyPublicBlob(_CERT_CONTEXT const *,uchar * *,ulong *)
0x180004b5a  mov     rsi, [rsp+78h+Buf2]
0x180004b5f  mov     ebx, eax
0x180004b61  test    eax, eax
0x180004b63  jnz     short loc_180004BA4
0x180004b65  mov     eax, dword ptr [rsp+78h+Size]
0x180004b6c  cmp     r12d, eax
0x180004b6f  jnz     short loc_180004B83
0x180004b71  mov     r8d, eax; Size
0x180004b74  mov     rdx, rsi; Buf2
0x180004b77  mov     rcx, r15; Buf1
0x180004b7a  call    memcmp_0
0x180004b7f  test    eax, eax
0x180004b81  jz      short loc_180004B98
0x180004b83  mov     rcx, rsi; hMem
0x180004b86  call    cs:__imp_LocalFree
0x180004b8c  xor     esi, esi
0x180004b8e  mov     rdx, rdi
0x180004b91  mov     [rsp+78h+Buf2], rsi
0x180004b96  jmp     short loc_180004B29
0x180004b98  mov     [r14], rdi
0x180004b9b  xor     edi, edi
0x180004b9d  jmp     short loc_180004BA4
0x180004b9f  mov     ebx, 80070490h
0x180004ba4  test    r15, r15
0x180004ba7  jnz     short loc_180004BCC
0x180004ba9  jmp     short loc_180004BD5
0x180004bab  lea     r9, aPcpEkpub; "PCP_EKPUB"
0x180004bb2  mov     dword ptr [rsp+78h+pcbResult], eax
0x180004bb6  lea     r8, aErrorNcryptget; "ERROR: NCryptGetProperty(%ws) Hr=%x\n"
0x180004bbd  mov     edx, 1; unsigned int
0x180004bc2  mov     ecx, 4912C2h; unsigned int
0x180004bc7  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004bcc  mov     rcx, r15; hMem
0x180004bcf  call    cs:__imp_LocalFree
0x180004bd5  mov     r15, [rsp+78h+var_38]
0x180004bda  mov     r13, [rsp+78h+var_28]
0x180004bdf  mov     r12, [rsp+78h+var_20]
0x180004be4  test    rsi, rsi
0x180004be7  jz      short loc_180004BF2
0x180004be9  mov     rcx, rsi; hMem
0x180004bec  call    cs:__imp_LocalFree
0x180004bf2  mov     rcx, [rsp+78h+phProvider]; hObject
0x180004bf7  mov     r14, [rsp+78h+var_30]
0x180004bfc  mov     rsi, [rsp+78h+var_18]
0x180004c01  mov     rbp, [rsp+78h+arg_0]
0x180004c09  test    rcx, rcx
0x180004c0c  jz      short loc_180004C1D
0x180004c0e  call    cs:__imp_NCryptFreeObject
0x180004c14  mov     [rsp+78h+phProvider], 0
0x180004c1d  test    rdi, rdi
0x180004c20  jz      short loc_180004C2B
0x180004c22  mov     rcx, rdi; pCertContext
0x180004c25  call    cs:__imp_CertFreeCertificateContext
0x180004c2b  lea     r8, aTraceTpmgetcer_0; "TRACE: _TpmGetCertificateFromStoreMatch"...
0x180004c32  mov     edx, 2; unsigned int
0x180004c37  mov     ecx, 58D12C2h; unsigned int
0x180004c3c  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004c41  mov     eax, ebx
0x180004c43  add     rsp, 68h
0x180004c47  pop     rdi
0x180004c48  pop     rbx
0x180004c49  retn
```
