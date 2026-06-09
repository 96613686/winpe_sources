# _ParseInCerts

- ea: `0x180010748`
- end: `0x180010875`
- name: `_ParseInCerts`
- size: `301`
- prototype: `const CERT_CONTEXT *__fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010d3c`

## callees

- `0x180010748`
- `0x1800164b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010840`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010840`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x1800107fb`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x1800107fb`
- `CRYPT32!CertOpenStore` at `0x180010779`
- `CRYPT32!CertOpenStore` at `0x180010779`
- `CRYPT32!CertCloseStore` at `0x18001085b`
- `CRYPT32!CertCloseStore` at `0x18001085b`
- `CRYPT32!CertFreeCertificateContext` at `0x18001081d`
- `CRYPT32!CertFreeCertificateContext` at `0x18001084e`
- `CRYPT32!CertFreeCertificateContext` at `0x18001081d`
- `CRYPT32!CertFreeCertificateContext` at `0x18001084e`

## pseudocode

```c
const CERT_CONTEXT *__fastcall ParseInCerts(BYTE *pbCertEncoded, DWORD cbCertEncoded, unsigned int a3)
{
  const CERT_CONTEXT *v3; // rbx
  HCERTSTORE v7; // r13
  unsigned int v8; // ebp
  int v9; // r15d
  DWORD v10; // edi
  int v11; // eax
  DWORD v12; // eax
  PCCERT_CONTEXT pCertContext; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v15[80]; // [rsp+38h] [rbp-50h] BYREF
  int v16; // [rsp+A8h] [rbp+20h] BYREF

  v3 = 0;
  v7 = CertOpenStore((LPCSTR)2, 0x10001u, 0, 0x84u, 0);
  if ( v7 )
  {
    v8 = 0;
    v9 = 1;
    while ( 1 )
    {
      pCertContext = 0;
      v16 = 0;
      v10 = cbCertEncoded;
      v11 = Asn1UtilExtractContentEx(pbCertEncoded, cbCertEncoded, &v16, v15);
      if ( v11 >= 0 )
      {
        v12 = v16 + v11;
        if ( v12 < cbCertEncoded )
          v10 = v12;
      }
      if ( !v10 || v10 > cbCertEncoded || v8 >= a3 )
        break;
      if ( !CertAddEncodedCertificateToStore(v7, 0x10001u, pbCertEncoded, v10, 2u, &pCertContext) )
        goto LABEL_18;
      cbCertEncoded -= v10;
      ++v8;
      if ( v9 )
      {
        v3 = pCertContext;
        v9 = 0;
      }
      else
      {
        CertFreeCertificateContext(pCertContext);
      }
      if ( !cbCertEncoded )
      {
        if ( v3 && v8 == a3 )
          goto LABEL_20;
        break;
      }
      pbCertEncoded += v10;
    }
    SetLastError(0xDu);
LABEL_18:
    if ( v3 )
    {
      CertFreeCertificateContext(v3);
      v3 = 0;
    }
LABEL_20:
    CertCloseStore(v7, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x180010748  push    rbx
0x18001074a  push    rbp
0x18001074b  push    rsi
0x18001074c  push    rdi
0x18001074d  push    r12
0x18001074f  push    r13
0x180010751  push    r14
0x180010753  push    r15
0x180010755  sub     rsp, 48h
0x180010759  xor     ebx, ebx
0x18001075b  mov     r12d, r8d
0x18001075e  mov     esi, edx
0x180010760  mov     [rsp+88h+pvPara], rbx; pvPara
0x180010765  mov     r14, rcx
0x180010768  mov     r9d, 84h; dwFlags
0x18001076e  xor     r8d, r8d; hCryptProv
0x180010771  mov     edx, 10001h; dwEncodingType
0x180010776  lea     ecx, [rbx+2]; lpszStoreProvider
0x180010779  call    cs:__imp_CertOpenStore
0x18001077f  mov     r13, rax
0x180010782  test    rax, rax
0x180010785  jz      loc_180010861
0x18001078b  xor     ebp, ebp
0x18001078d  lea     r15d, [rbx+1]
0x180010791  lea     r9, [rsp+88h+var_50]
0x180010796  mov     [rsp+88h+pCertContext], 0
0x18001079f  lea     r8, [rsp+88h+arg_18]
0x1800107a7  mov     [rsp+88h+arg_18], 0
0x1800107b2  mov     edx, esi
0x1800107b4  mov     rcx, r14
0x1800107b7  mov     edi, esi
0x1800107b9  call    Asn1UtilExtractContentEx
0x1800107be  test    eax, eax
0x1800107c0  js      short loc_1800107CE
0x1800107c2  add     eax, [rsp+88h+arg_18]
0x1800107c9  cmp     eax, esi
0x1800107cb  cmovb   edi, eax
0x1800107ce  test    edi, edi
0x1800107d0  jz      short loc_18001083B
0x1800107d2  cmp     edi, esi
0x1800107d4  ja      short loc_18001083B
0x1800107d6  cmp     ebp, r12d
0x1800107d9  jnb     short loc_18001083B
0x1800107db  lea     rax, [rsp+88h+pCertContext]
0x1800107e0  mov     r9d, edi; cbCertEncoded
0x1800107e3  mov     [rsp+88h+ppCertContext], rax; ppCertContext
0x1800107e8  mov     r8, r14; pbCertEncoded
0x1800107eb  mov     edx, 10001h; dwCertEncodingType
0x1800107f0  mov     dword ptr [rsp+88h+pvPara], 2; dwAddDisposition
0x1800107f8  mov     rcx, r13; hCertStore
0x1800107fb  call    cs:__imp_CertAddEncodedCertificateToStore
0x180010801  test    eax, eax
0x180010803  jz      short loc_180010846
0x180010805  sub     esi, edi
0x180010807  inc     ebp
0x180010809  test    r15d, r15d
0x18001080c  jz      short loc_180010818
0x18001080e  mov     rbx, [rsp+88h+pCertContext]
0x180010813  xor     r15d, r15d
0x180010816  jmp     short loc_180010823
0x180010818  mov     rcx, [rsp+88h+pCertContext]; pCertContext
0x18001081d  call    cs:__imp_CertFreeCertificateContext
0x180010823  test    esi, esi
0x180010825  jz      short loc_180010831
0x180010827  mov     eax, edi
0x180010829  add     r14, rax
0x18001082c  jmp     loc_180010791
0x180010831  test    rbx, rbx
0x180010834  jz      short loc_18001083B
0x180010836  cmp     ebp, r12d
0x180010839  jz      short loc_180010856
0x18001083b  mov     ecx, 0Dh; dwErrCode
0x180010840  call    cs:__imp_SetLastError
0x180010846  test    rbx, rbx
0x180010849  jz      short loc_180010856
0x18001084b  mov     rcx, rbx; pCertContext
0x18001084e  call    cs:__imp_CertFreeCertificateContext
0x180010854  xor     ebx, ebx
0x180010856  xor     edx, edx; dwFlags
0x180010858  mov     rcx, r13; hCertStore
0x18001085b  call    cs:__imp_CertCloseStore
0x180010861  mov     rax, rbx
0x180010864  add     rsp, 48h
0x180010868  pop     r15
0x18001086a  pop     r14
0x18001086c  pop     r13
0x18001086e  pop     r12
0x180010870  pop     rdi
0x180010871  pop     rsi
0x180010872  pop     rbp
0x180010873  pop     rbx
0x180010874  retn
```
