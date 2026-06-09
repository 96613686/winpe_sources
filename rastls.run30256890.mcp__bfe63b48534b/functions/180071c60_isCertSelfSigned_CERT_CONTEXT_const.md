# isCertSelfSigned(_CERT_CONTEXT const *)

- ea: `0x180071c60`
- end: `0x180071cc7`
- name: `?isCertSelfSigned@@YAHPEBU_CERT_CONTEXT@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pIssuer)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004de18`
- `0x18006e6c4`

## callees

- `0x180071c60`

## import_xrefs

- `CRYPT32!CertCompareCertificateName` at `0x180071c7f`
- `CRYPT32!CertCompareCertificateName` at `0x180071c7f`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x180071ca2`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x180071ca2`

## pseudocode

```c
_BOOL8 __fastcall isCertSelfSigned(PCCERT_CONTEXT pIssuer)
{
  PCERT_INFO pCertInfo; // rdx
  DWORD dwCertEncodingType; // ecx
  DWORD pdwFlags; // [rsp+30h] [rbp+8h] BYREF

  pCertInfo = pIssuer->pCertInfo;
  dwCertEncodingType = pIssuer->dwCertEncodingType;
  pdwFlags = 0;
  if ( CertCompareCertificateName(dwCertEncodingType, &pCertInfo->Subject, &pCertInfo->Issuer)
    && (pdwFlags = 1, CertVerifySubjectCertificateContext(pIssuer, pIssuer, &pdwFlags)) )
  {
    return pdwFlags == 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180071c60  push    rbx
0x180071c62  sub     rsp, 20h
0x180071c66  mov     rdx, [rcx+18h]
0x180071c6a  mov     rbx, rcx
0x180071c6d  mov     ecx, [rcx]; dwCertEncodingType
0x180071c6f  mov     [rsp+28h+pdwFlags], 0
0x180071c77  lea     r8, [rdx+30h]; pCertName2
0x180071c7b  add     rdx, 50h ; 'P'; pCertName1
0x180071c7f  call    cs:__imp_CertCompareCertificateName
0x180071c86  nop     dword ptr [rax+rax+00h]
0x180071c8b  test    eax, eax
0x180071c8d  jz      short loc_180071CBE
0x180071c8f  lea     r8, [rsp+28h+pdwFlags]; pdwFlags
0x180071c94  mov     [rsp+28h+pdwFlags], 1
0x180071c9c  mov     rdx, rbx; pIssuer
0x180071c9f  mov     rcx, rbx; pSubject
0x180071ca2  call    cs:__imp_CertVerifySubjectCertificateContext
0x180071ca9  nop     dword ptr [rax+rax+00h]
0x180071cae  cmp     eax, 1
0x180071cb1  jnz     short loc_180071CBE
0x180071cb3  xor     eax, eax
0x180071cb5  cmp     [rsp+28h+pdwFlags], eax
0x180071cb9  setz    al
0x180071cbc  jmp     short loc_180071CC0
0x180071cbe  xor     eax, eax
0x180071cc0  add     rsp, 20h
0x180071cc4  pop     rbx
0x180071cc5  retn
```
