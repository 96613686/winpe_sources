# ObjectContextIsValidForSubject(char const *,void *,void *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *)

- ea: `0x18000eb80`
- end: `0x18000ed16`
- name: `?ObjectContextIsValidForSubject@@YAHPEBDPEAX1PEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(const char *, const CRL_CONTEXT *, const CERT_CONTEXT *, struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008f80`
- `0x18000cfa0`
- `0x180017270`

## callees

- `0x18000a990`
- `0x18000eb80`
- `0x1800262c8`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18000ec06`
- `CRYPT32!CertFindExtension` at `0x18000ec06`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x18000ebac`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x18000ebac`
- `CRYPT32!CryptDecodeObject` at `0x18000ec97`
- `CRYPT32!CryptDecodeObject` at `0x18000ec97`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000ecea`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000ecea`

## pseudocode

```c
__int64 __fastcall ObjectContextIsValidForSubject(
        const char *a1,
        const CRL_CONTEXT *a2,
        const CERT_CONTEXT *a3,
        struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *a4)
{
  unsigned int IsValidCRLForCertificate; // esi
  int iDeltaCrlIndicator; // r14d
  PCRYPT_INTEGER_BLOB pDeltaCrlIndicator; // r15
  PCERT_EXTENSION Extension; // rax
  void *v11; // rbx
  BOOL v12; // eax
  DWORD pcbStructInfo[4]; // [rsp+40h] [rbp-28h] BYREF
  DWORD pvStructInfo; // [rsp+70h] [rbp+8h] BYREF

  if ( a1 != (const char *)2 || !a3 )
    return 1;
  IsValidCRLForCertificate = CertIsValidCRLForCertificate(a3, a2, 0, 0);
  if ( IsValidCRLForCertificate && a4 && a4->cbSize > 0x28 )
  {
    iDeltaCrlIndicator = a4->iDeltaCrlIndicator;
    pDeltaCrlIndicator = a4->pDeltaCrlIndicator;
    Extension = CertFindExtension("2.5.29.20", a2->pCrlInfo->cExtension, a2->pCrlInfo->rgExtension);
    if ( iDeltaCrlIndicator <= 0 || pDeltaCrlIndicator )
    {
      if ( iDeltaCrlIndicator == 0x7FFFFFFF && a4->pDeltaCrlIndicator )
      {
        pvStructInfo = 0;
        v11 = 0;
        *(_QWORD *)pcbStructInfo = 0;
        if ( !Extension
          || (v12 = CryptDecodeObjectEx(
                      a2->dwCertEncodingType,
                      (LPCSTR)0x1C,
                      Extension->Value.pbData,
                      Extension->Value.cbData,
                      0x8005u,
                      &PkiDecodePara,
                      pcbStructInfo,
                      &pvStructInfo),
              v11 = *(void **)pcbStructInfo,
              !v12)
          || (unsigned int)I_CertCompareIntegerBlob(*(_QWORD *)pcbStructInfo, pDeltaCrlIndicator) == -1 )
        {
          IsValidCRLForCertificate = 0;
        }
        if ( v11 )
          operator delete(v11);
      }
    }
    else
    {
      pcbStructInfo[0] = 4;
      pvStructInfo = 0;
      if ( !Extension
        || !CryptDecodeObject(
              a2->dwCertEncodingType,
              (LPCSTR)0x1B,
              Extension->Value.pbData,
              Extension->Value.cbData,
              0,
              &pvStructInfo,
              pcbStructInfo)
        || (int)pvStructInfo < iDeltaCrlIndicator )
      {
        return 0;
      }
    }
  }
  return IsValidCRLForCertificate;
}

```

## disassembly

```asm
0x18000eb80  push    rbx
0x18000eb82  push    rdi
0x18000eb83  sub     rsp, 58h
0x18000eb87  mov     rbx, r9
0x18000eb8a  mov     rax, r8
0x18000eb8d  mov     rdi, rdx
0x18000eb90  cmp     rcx, 2
0x18000eb94  jnz     short loc_18000EBCE
0x18000eb96  test    rax, rax
0x18000eb99  jz      short loc_18000EBCE
0x18000eb9b  xor     r9d, r9d; pvReserved
0x18000eb9e  mov     [rsp+68h+arg_10], rsi
0x18000eba6  xor     r8d, r8d; dwFlags
0x18000eba9  mov     rcx, rax; pCert
0x18000ebac  call    cs:__imp_CertIsValidCRLForCertificate
0x18000ebb2  mov     esi, eax
0x18000ebb4  test    eax, eax
0x18000ebb6  jz      short loc_18000EBBD
0x18000ebb8  test    rbx, rbx
0x18000ebbb  jnz     short loc_18000EBD5
0x18000ebbd  mov     eax, esi
0x18000ebbf  mov     rsi, [rsp+68h+arg_10]
0x18000ebc7  add     rsp, 58h
0x18000ebcb  pop     rdi
0x18000ebcc  pop     rbx
0x18000ebcd  retn
0x18000ebce  mov     eax, 1
0x18000ebd3  jmp     short loc_18000EBC7
0x18000ebd5  cmp     dword ptr [rbx], 28h ; '('
0x18000ebd8  jbe     short loc_18000EBBD
0x18000ebda  mov     rdx, [rdi+18h]
0x18000ebde  lea     rcx, a252920; "2.5.29.20"
0x18000ebe5  mov     [rsp+68h+arg_18], r14
0x18000ebed  mov     r14d, [rbx+4]
0x18000ebf1  mov     [rsp+68h+var_18], r15
0x18000ebf6  mov     r8, [rdx+58h]; rgExtensions
0x18000ebfa  mov     edx, [rdx+50h]; cExtensions
0x18000ebfd  mov     r15, [rbx+28h]
0x18000ec01  mov     [rsp+68h+arg_8], rbp
0x18000ec06  call    cs:__imp_CertFindExtension
0x18000ec0c  test    r14d, r14d
0x18000ec0f  jg      short loc_18000EC58
0x18000ec11  cmp     r14d, 7FFFFFFFh
0x18000ec18  jz      short loc_18000EC2E
0x18000ec1a  mov     rbp, [rsp+68h+arg_8]
0x18000ec1f  mov     r14, [rsp+68h+arg_18]
0x18000ec27  mov     r15, [rsp+68h+var_18]
0x18000ec2c  jmp     short loc_18000EBBD
0x18000ec2e  cmp     qword ptr [rbx+28h], 0
0x18000ec33  jz      short loc_18000EC1A
0x18000ec35  xor     ebp, ebp
0x18000ec37  mov     [rsp+68h+arg_0], ebp
0x18000ec3b  mov     ebx, ebp
0x18000ec3d  mov     qword ptr [rsp+68h+var_28], rbx
0x18000ec42  test    rax, rax
0x18000ec45  jnz     short loc_18000ECB3
0x18000ec47  mov     esi, ebp
0x18000ec49  test    rbx, rbx
0x18000ec4c  jz      short loc_18000EC1A
0x18000ec4e  mov     rcx, rbx; hMem
0x18000ec51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ec56  jmp     short loc_18000EC1A
0x18000ec58  test    r15, r15
0x18000ec5b  jnz     short loc_18000EC11
0x18000ec5d  xor     ebp, ebp
0x18000ec5f  mov     [rsp+68h+var_28], 4
0x18000ec67  mov     [rsp+68h+arg_0], ebp
0x18000ec6b  test    rax, rax
0x18000ec6e  jz      short loc_18000ECAC
0x18000ec70  mov     r9d, [rax+10h]; cbEncoded
0x18000ec74  lea     rcx, [rsp+68h+var_28]
0x18000ec79  mov     r8, [rax+18h]; pbEncoded
0x18000ec7d  mov     edx, 1Bh; lpszStructType
0x18000ec82  mov     [rsp+68h+pcbStructInfo], rcx; pcbStructInfo
0x18000ec87  lea     rcx, [rsp+68h+arg_0]
0x18000ec8c  mov     [rsp+68h+pvStructInfo], rcx; pvStructInfo
0x18000ec91  mov     ecx, [rdi]; dwCertEncodingType
0x18000ec93  mov     [rsp+68h+dwFlags], ebp; dwFlags
0x18000ec97  call    cs:__imp_CryptDecodeObject
0x18000ec9d  test    eax, eax
0x18000ec9f  jz      short loc_18000ECAC
0x18000eca1  cmp     [rsp+68h+arg_0], r14d
0x18000eca6  jge     loc_18000EC1A
0x18000ecac  mov     esi, ebp
0x18000ecae  jmp     loc_18000EC1A
0x18000ecb3  mov     r9d, [rax+10h]; cbEncoded
0x18000ecb7  lea     rcx, [rsp+68h+arg_0]
0x18000ecbc  mov     r8, [rax+18h]; pbEncoded
0x18000ecc0  mov     edx, 1Ch; lpszStructType
0x18000ecc5  mov     [rsp+68h+var_30], rcx; pcbStructInfo
0x18000ecca  lea     rcx, [rsp+68h+var_28]
0x18000eccf  mov     [rsp+68h+pcbStructInfo], rcx; pvStructInfo
0x18000ecd4  lea     rcx, PkiDecodePara
0x18000ecdb  mov     [rsp+68h+pvStructInfo], rcx; pDecodePara
0x18000ece0  mov     ecx, [rdi]; dwCertEncodingType
0x18000ece2  mov     [rsp+68h+dwFlags], 8005h; dwFlags
0x18000ecea  call    cs:__imp_CryptDecodeObjectEx
0x18000ecf0  mov     rbx, qword ptr [rsp+68h+var_28]
0x18000ecf5  test    eax, eax
0x18000ecf7  jz      loc_18000EC47
0x18000ecfd  mov     rdx, r15
0x18000ed00  mov     rcx, rbx
0x18000ed03  call    I_CertCompareIntegerBlob
0x18000ed08  cmp     eax, 0FFFFFFFFh
0x18000ed0b  jnz     loc_18000EC49
0x18000ed11  jmp     loc_18000EC47
```
