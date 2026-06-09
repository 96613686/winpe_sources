# isCertSelfSigned(_CERT_CONTEXT const *)

- ea: `0x18006d3b0`
- end: `0x18006d40a`
- name: `?isCertSelfSigned@@YAHPEBU_CERT_CONTEXT@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pIssuer)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004b518`
- `0x18006a24c`

## callees

- `0x18006d3b0`

## import_xrefs

- `CRYPT32!CertCompareCertificateName` at `0x18006d3cf`
- `CRYPT32!CertCompareCertificateName` at `0x18006d3cf`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18006d3ec`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18006d3ec`

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
0x18006d3b0  push    rbx
0x18006d3b2  sub     rsp, 20h
0x18006d3b6  mov     rdx, [rcx+18h]
0x18006d3ba  mov     rbx, rcx
0x18006d3bd  mov     ecx, [rcx]; dwCertEncodingType
0x18006d3bf  mov     [rsp+28h+pdwFlags], 0
0x18006d3c7  lea     r8, [rdx+30h]; pCertName2
0x18006d3cb  add     rdx, 50h ; 'P'; pCertName1
0x18006d3cf  call    cs:__imp_CertCompareCertificateName
0x18006d3d5  test    eax, eax
0x18006d3d7  jz      short loc_18006D402
0x18006d3d9  lea     r8, [rsp+28h+pdwFlags]; pdwFlags
0x18006d3de  mov     [rsp+28h+pdwFlags], 1
0x18006d3e6  mov     rdx, rbx; pIssuer
0x18006d3e9  mov     rcx, rbx; pSubject
0x18006d3ec  call    cs:__imp_CertVerifySubjectCertificateContext
0x18006d3f2  cmp     eax, 1
0x18006d3f5  jnz     short loc_18006D402
0x18006d3f7  xor     eax, eax
0x18006d3f9  cmp     [rsp+28h+pdwFlags], eax
0x18006d3fd  setz    al
0x18006d400  jmp     short loc_18006D404
0x18006d402  xor     eax, eax
0x18006d404  add     rsp, 20h
0x18006d408  pop     rbx
0x18006d409  retn
```
