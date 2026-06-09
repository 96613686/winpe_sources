# CCAInfo::_ValidateCaCertificate(ldap *,ulong,ldapmsg *,_CERT_CONTEXT const * *)

- ea: `0x180012114`
- end: `0x180012259`
- name: `?_ValidateCaCertificate@CCAInfo@@KAJPEAUldap@@KPEAUldapmsg@@PEAPEBU_CERT_CONTEXT@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(struct ldap *, unsigned int, struct ldapmsg *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000af94`

## callees

- `0x180008400`
- `0x180008610`
- `0x180012114`
- `0x180012450`
- `0x18001bb30`
- `0x18001dd10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800121f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800121f8`
- `CRYPT32!CertCreateCertificateContext` at `0x18001215a`
- `CRYPT32!CertCreateCertificateContext` at `0x18001215a`
- `CRYPT32!CertFreeCertificateContext` at `0x180012247`
- `CRYPT32!CertFreeCertificateContext` at `0x180012247`
- `WLDAP32!__imp_ldap_value_free_len` at `0x180012239`
- `WLDAP32!__imp_ldap_value_free_len` at `0x180012239`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x180012130`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x180012130`

## pseudocode

```c
__int64 __fastcall CCAInfo::_ValidateCaCertificate(
        struct ldap *a1,
        unsigned int a2,
        struct ldapmsg *a3,
        const struct _CERT_CONTEXT **a4)
{
  DWORD **values_lenW; // rax
  struct berval **v7; // rsi
  PCCERT_CONTEXT CertificateContext; // rbx
  unsigned int v9; // edi
  unsigned int v10; // ecx
  const struct _CRYPTOAPI_BLOB *p_Subject; // rdx
  int v12; // eax
  HLOCAL hMem; // [rsp+40h] [rbp-38h] BYREF

  values_lenW = (DWORD **)ldap_get_values_lenW(a1, a3, (const PWSTR)L"cACertificate");
  v7 = (struct berval **)values_lenW;
  if ( values_lenW && *values_lenW )
  {
    CertificateContext = CertCreateCertificateContext(1u, *((const BYTE **)*values_lenW + 1), **values_lenW);
    if ( CertificateContext )
    {
      if ( (a2 & 0x10) != 0
        || (v9 = myVerifyCertContext(CertificateContext, 2u, 0, 0, (void *)((a2 >> 5) & 1), 0, 0)) == 0 )
      {
        *a4 = CertificateContext;
        CertificateContext = 0;
        v9 = 0;
      }
      else
      {
        p_Subject = &CertificateContext->pCertInfo->Subject;
        hMem = 0;
        v12 = myCertNameToStr(v10, p_Subject, 0x2000003u, (unsigned __int16 **)&hMem);
        if ( v12 )
          CSPrintErrorLineFile(0x1850325u, v12);
        LocalFree(hMem);
        CSPrintErrorLineFileData2((const unsigned __int16 *)hMem, 0x1880325u, v9, 0);
      }
    }
    else
    {
      v9 = myHLastError();
      CSPrintErrorLineFile(0x1630325u, v9);
    }
  }
  else
  {
    v9 = -2147023728;
    CSPrintErrorLineFile(0x16B0325u, -2147023728);
    if ( !v7 )
      return v9;
    CertificateContext = 0;
  }
  ldap_value_free_len(v7);
  if ( CertificateContext )
    CertFreeCertificateContext(CertificateContext);
  return v9;
}

```

## disassembly

```asm
0x180012114  push    rbx
0x180012116  push    rsi
0x180012117  push    rdi
0x180012118  push    r14
0x18001211a  sub     rsp, 58h
0x18001211e  mov     rax, r8
0x180012121  mov     edi, edx
0x180012123  mov     rdx, rax; Message
0x180012126  lea     r8, aCacertificate; "cACertificate"
0x18001212d  mov     r14, r9
0x180012130  call    cs:__imp_ldap_get_values_lenW
0x180012136  mov     rsi, rax
0x180012139  test    rax, rax
0x18001213c  jz      loc_18001221E
0x180012142  mov     rdx, [rax]
0x180012145  test    rdx, rdx
0x180012148  jz      loc_18001221E
0x18001214e  mov     r8d, [rdx]; cbCertEncoded
0x180012151  mov     ecx, 1; dwCertEncodingType
0x180012156  mov     rdx, [rdx+8]; pbCertEncoded
0x18001215a  call    cs:__imp_CertCreateCertificateContext
0x180012160  mov     rbx, rax
0x180012163  test    rax, rax
0x180012166  jnz     short loc_180012180
0x180012168  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001216d  mov     edx, eax; int
0x18001216f  mov     ecx, 1630325h; unsigned int
0x180012174  mov     edi, eax
0x180012176  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001217b  jmp     loc_180012236
0x180012180  test    dil, 10h
0x180012184  jnz     loc_180012215
0x18001218a  xor     r9d, r9d; char **
0x18001218d  mov     [rsp+78h+var_48], 0; unsigned __int16 **
0x180012196  mov     eax, edi
0x180012198  mov     [rsp+78h+var_50], 0; void *
0x1800121a1  shr     rax, 5
0x1800121a5  xor     r8d, r8d; unsigned int
0x1800121a8  and     eax, 1
0x1800121ab  mov     rcx, rbx; struct _CERT_CONTEXT *
0x1800121ae  lea     edx, [r9+2]; unsigned int
0x1800121b2  mov     [rsp+78h+var_58], rax; void *
0x1800121b7  call    ?myVerifyCertContext@@YAJPEBU_CERT_CONTEXT@@KKPEBQEBDPEAX2PEAPEAG@Z; myVerifyCertContext(_CERT_CONTEXT const *,ulong,ulong,char const * const *,void *,void *,ushort * *)
0x1800121bc  mov     edi, eax
0x1800121be  test    eax, eax
0x1800121c0  jz      short loc_180012215
0x1800121c2  mov     rdx, [rbx+18h]
0x1800121c6  lea     r9, [rsp+78h+hMem]; unsigned __int16 **
0x1800121cb  add     rdx, 50h ; 'P'; struct _CRYPTOAPI_BLOB *
0x1800121cf  mov     [rsp+78h+hMem], 0
0x1800121d8  mov     r8d, 2000003h; unsigned int
0x1800121de  call    ?myCertNameToStr@@YAJKPEBU_CRYPTOAPI_BLOB@@KPEAPEAG@Z; myCertNameToStr(ulong,_CRYPTOAPI_BLOB const *,ulong,ushort * *)
0x1800121e3  test    eax, eax
0x1800121e5  jz      short loc_1800121F3
0x1800121e7  mov     edx, eax; int
0x1800121e9  mov     ecx, 1850325h; unsigned int
0x1800121ee  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800121f3  mov     rcx, [rsp+78h+hMem]; hMem
0x1800121f8  call    cs:__imp_LocalFree
0x1800121fe  mov     rcx, [rsp+78h+hMem]; unsigned __int16 *
0x180012203  xor     r9d, r9d; int
0x180012206  mov     r8d, edi; int
0x180012209  mov     edx, 1880325h; unsigned int
0x18001220e  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180012213  jmp     short loc_180012236
0x180012215  mov     [r14], rbx
0x180012218  xor     ebx, ebx
0x18001221a  xor     edi, edi
0x18001221c  jmp     short loc_180012236
0x18001221e  mov     edi, 80070490h
0x180012223  mov     ecx, 16B0325h; unsigned int
0x180012228  mov     edx, edi; int
0x18001222a  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001222f  test    rsi, rsi
0x180012232  jz      short loc_18001224D
0x180012234  xor     ebx, ebx
0x180012236  mov     rcx, rsi; vals
0x180012239  call    cs:__imp_ldap_value_free_len
0x18001223f  test    rbx, rbx
0x180012242  jz      short loc_18001224D
0x180012244  mov     rcx, rbx; pCertContext
0x180012247  call    cs:__imp_CertFreeCertificateContext
0x18001224d  mov     eax, edi
0x18001224f  add     rsp, 58h
0x180012253  pop     r14
0x180012255  pop     rdi
0x180012256  pop     rsi
0x180012257  pop     rbx
0x180012258  retn
```
