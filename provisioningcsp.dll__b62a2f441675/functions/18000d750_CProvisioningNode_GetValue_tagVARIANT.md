# CProvisioningNode::GetValue(tagVARIANT *)

- ea: `0x18000d750`
- end: `0x18000d971`
- name: `?GetValue@CProvisioningNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `545`
- prototype: `int(CProvisioningNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006974`
- `0x18000d750`
- `0x18000dcb0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d8c8`
- `msvcrt!memcpy_s` at `0x18000d8c8`
- `OLEAUT32!__imp_VariantClear` at `0x18000d792`
- `OLEAUT32!__imp_VariantClear` at `0x18000d792`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000d868`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000d868`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000d91c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000d91c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000d8a0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000d8a0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000d8d7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000d8d7`
- `CRYPT32!CertCloseStore` at `0x18000d839`
- `CRYPT32!CertCloseStore` at `0x18000d953`
- `CRYPT32!CertCloseStore` at `0x18000d839`
- `CRYPT32!CertCloseStore` at `0x18000d953`
- `CRYPT32!CertFreeCertificateContext` at `0x18000d81c`
- `CRYPT32!CertFreeCertificateContext` at `0x18000d93a`
- `CRYPT32!CertFreeCertificateContext` at `0x18000d81c`
- `CRYPT32!CertFreeCertificateContext` at `0x18000d93a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CProvisioningNode::GetValue(CProvisioningNode *this, struct tagVARIANT *a2)
{
  HRESULT CertificateByUri; // ebx
  __int64 v5; // rdx
  __int64 v7; // rdx
  SAFEARRAY *v8; // rax
  SAFEARRAY *v9; // rsi
  rsize_t cElements; // r15
  PCCERT_CONTEXT v11; // r14
  __int64 v12; // rdx
  void *ppvData; // [rsp+20h] [rbp-20h] BYREF
  char v14; // [rsp+28h] [rbp-18h]
  PCCERT_CONTEXT *p_pCertContext; // [rsp+30h] [rbp-10h]
  char v16; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  PCCERT_CONTEXT pCertContext; // [rsp+88h] [rbp+48h] BYREF
  HCERTSTORE hCertStore; // [rsp+90h] [rbp+50h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+98h] [rbp+58h] BYREF

  if ( !a2 )
  {
    CertificateByUri = -2147467261;
    v5 = 21;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\getvalue.cpp",
      (const char *)(unsigned int)CertificateByUri,
      (int)ppvData);
    return (unsigned int)CertificateByUri;
  }
  CertificateByUri = VariantClear(a2);
  if ( CertificateByUri < 0 )
  {
    v5 = 22;
    goto LABEL_3;
  }
  if ( *((_DWORD *)this + 11) != 2 )
    return 2248146961LL;
  hCertStore = 0;
  ppvData = &hCertStore;
  v14 = 1;
  pCertContext = 0;
  p_pCertContext = &pCertContext;
  v16 = 1;
  CertificateByUri = CProvisioningNode::GetCertificateByUri(
                       *((struct IConfigManager2URI **)this + 3),
                       &pCertContext,
                       &hCertStore);
  if ( CertificateByUri < 0 )
  {
    v7 = 39;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\getvalue.cpp",
      (const char *)(unsigned int)CertificateByUri,
      (int)ppvData);
    goto LABEL_12;
  }
  rgsabound = 0;
  rgsabound.cElements = pCertContext->cbCertEncoded;
  v8 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v9 = v8;
  if ( !v8 )
  {
    CertificateByUri = -2147024882;
    v7 = 53;
    goto LABEL_11;
  }
  cElements = rgsabound.cElements;
  v11 = pCertContext;
  ppvData = 0;
  CertificateByUri = SafeArrayAccessData(v8, &ppvData);
  if ( CertificateByUri < 0 )
  {
    v12 = 13;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\getvalue.cpp",
      (const char *)(unsigned int)CertificateByUri,
      (int)ppvData);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\getvalue.cpp",
      (const char *)(unsigned int)CertificateByUri,
      (int)ppvData);
    SafeArrayDestroy(v9);
LABEL_12:
    CertFreeCertificateContext(pCertContext);
    if ( hCertStore )
      CertCloseStore(hCertStore, 1u);
    return (unsigned int)CertificateByUri;
  }
  memcpy_s(ppvData, cElements, v11->pbCertEncoded, v11->cbCertEncoded);
  CertificateByUri = SafeArrayUnaccessData(v9);
  if ( CertificateByUri < 0 )
  {
    v12 = 15;
    goto LABEL_20;
  }
  a2->vt = 8209;
  a2->llVal = (LONGLONG)v9;
  CertFreeCertificateContext(pCertContext);
  if ( hCertStore )
    CertCloseStore(hCertStore, 1u);
  return 0;
}

```

## disassembly

```asm
0x18000d750  push    rbp
0x18000d752  push    rbx
0x18000d753  push    rsi
0x18000d754  push    rdi
0x18000d755  push    r13
0x18000d757  push    r14
0x18000d759  push    r15
0x18000d75b  mov     rbp, rsp
0x18000d75e  sub     rsp, 40h
0x18000d762  mov     rdi, rdx
0x18000d765  mov     rsi, rcx
0x18000d768  test    rdx, rdx
0x18000d76b  jnz     short loc_18000D78F
0x18000d76d  mov     ebx, 80004003h
0x18000d772  lea     edx, [rdi+15h]; void *
0x18000d775  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\provcsp\\getva"...
0x18000d77c  mov     r9d, ebx; char *
0x18000d77f  mov     rcx, [rbp+38h]; this
0x18000d783  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d788  mov     eax, ebx
0x18000d78a  jmp     loc_18000D961
0x18000d78f  mov     rcx, rdi; pvarg
0x18000d792  call    cs:__imp_VariantClear
0x18000d799  nop     dword ptr [rax+rax+00h]
0x18000d79e  mov     ebx, eax
0x18000d7a0  test    eax, eax
0x18000d7a2  jns     short loc_18000D7AB
0x18000d7a4  mov     edx, 16h
0x18000d7a9  jmp     short loc_18000D775
0x18000d7ab  cmp     dword ptr [rsi+2Ch], 2
0x18000d7af  jz      short loc_18000D7BB
0x18000d7b1  mov     eax, 86000011h
0x18000d7b6  jmp     loc_18000D961
0x18000d7bb  mov     [rbp+hCertStore], 0
0x18000d7c3  lea     rax, [rbp+hCertStore]
0x18000d7c7  mov     [rbp+ppvData], rax
0x18000d7cb  mov     r13d, 1
0x18000d7d1  mov     [rbp+var_18], r13b
0x18000d7d5  mov     [rbp+pCertContext], 0
0x18000d7dd  lea     rax, [rbp+pCertContext]
0x18000d7e1  mov     [rbp+var_10], rax
0x18000d7e5  mov     [rbp+var_8], r13b
0x18000d7e9  lea     r8, [rbp+hCertStore]; void **
0x18000d7ed  lea     rdx, [rbp+pCertContext]; struct _CERT_CONTEXT **
0x18000d7f1  mov     rcx, [rsi+18h]; struct IConfigManager2URI *
0x18000d7f5  call    ?GetCertificateByUri@CProvisioningNode@@CAJPEAUIConfigManager2URI@@PEAPEBU_CERT_CONTEXT@@PEAPEAX@Z; CProvisioningNode::GetCertificateByUri(IConfigManager2URI *,_CERT_CONTEXT const * *,void * *)
0x18000d7fa  mov     ebx, eax
0x18000d7fc  test    eax, eax
0x18000d7fe  jns     short loc_18000D84A
0x18000d800  lea     edx, [r13+26h]; void *
0x18000d804  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\provcsp\\getva"...
0x18000d80b  mov     r9d, ebx; char *
0x18000d80e  mov     rcx, [rbp+38h]; this
0x18000d812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d817  nop
0x18000d818  mov     rcx, [rbp+pCertContext]; pCertContext
0x18000d81c  call    cs:__imp_CertFreeCertificateContext
0x18000d823  nop     dword ptr [rax+rax+00h]
0x18000d828  nop
0x18000d829  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000d82d  test    rcx, rcx
0x18000d830  jz      loc_18000D788
0x18000d836  mov     edx, r13d; dwFlags
0x18000d839  call    cs:__imp_CertCloseStore
0x18000d840  nop     dword ptr [rax+rax+00h]
0x18000d845  jmp     loc_18000D788
0x18000d84a  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18000d852  mov     rax, [rbp+pCertContext]
0x18000d856  mov     ecx, [rax+10h]
0x18000d859  mov     [rbp+rgsabound.cElements], ecx
0x18000d85c  mov     ecx, 11h; vt
0x18000d861  lea     r8, [rbp+rgsabound]; rgsabound
0x18000d865  mov     edx, r13d; cDims
0x18000d868  call    cs:__imp_SafeArrayCreate
0x18000d86f  nop     dword ptr [rax+rax+00h]
0x18000d874  mov     rsi, rax
0x18000d877  test    rax, rax
0x18000d87a  jnz     short loc_18000D889
0x18000d87c  mov     ebx, 8007000Eh
0x18000d881  lea     edx, [rax+35h]
0x18000d884  jmp     loc_18000D804
0x18000d889  mov     r15d, [rbp+rgsabound.cElements]
0x18000d88d  mov     r14, [rbp+pCertContext]
0x18000d891  mov     [rbp+ppvData], 0
0x18000d899  lea     rdx, [rbp+ppvData]; ppvData
0x18000d89d  mov     rcx, rsi; psa
0x18000d8a0  call    cs:__imp_SafeArrayAccessData
0x18000d8a7  nop     dword ptr [rax+rax+00h]
0x18000d8ac  mov     ebx, eax
0x18000d8ae  test    eax, eax
0x18000d8b0  jns     short loc_18000D8B9
0x18000d8b2  mov     edx, 0Dh
0x18000d8b7  jmp     short loc_18000D8EE
0x18000d8b9  mov     r9d, [r14+10h]; SourceSize
0x18000d8bd  mov     rdx, r15; DestinationSize
0x18000d8c0  mov     r8, [r14+8]; Source
0x18000d8c4  mov     rcx, [rbp+ppvData]; Destination
0x18000d8c8  call    cs:__imp_memcpy_s
0x18000d8cf  nop     dword ptr [rax+rax+00h]
0x18000d8d4  mov     rcx, rsi; psa
0x18000d8d7  call    cs:__imp_SafeArrayUnaccessData
0x18000d8de  nop     dword ptr [rax+rax+00h]
0x18000d8e3  mov     ebx, eax
0x18000d8e5  test    eax, eax
0x18000d8e7  jns     short loc_18000D92D
0x18000d8e9  mov     edx, 0Fh; void *
0x18000d8ee  mov     r9d, ebx; char *
0x18000d8f1  mov     rcx, [rbp+38h]; this
0x18000d8f5  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\provcsp\\getva"...
0x18000d8fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d901  mov     rcx, [rbp+38h]; this
0x18000d905  mov     r9d, ebx; char *
0x18000d908  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\provcsp\\getva"...
0x18000d90f  mov     edx, 38h ; '8'; void *
0x18000d914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d919  mov     rcx, rsi; psa
0x18000d91c  call    cs:__imp_SafeArrayDestroy
0x18000d923  nop     dword ptr [rax+rax+00h]
0x18000d928  jmp     loc_18000D818
0x18000d92d  mov     word ptr [rdi], 2011h
0x18000d932  mov     [rdi+8], rsi
0x18000d936  mov     rcx, [rbp+pCertContext]; pCertContext
0x18000d93a  call    cs:__imp_CertFreeCertificateContext
0x18000d941  nop     dword ptr [rax+rax+00h]
0x18000d946  nop
0x18000d947  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000d94b  test    rcx, rcx
0x18000d94e  jz      short loc_18000D95F
0x18000d950  mov     edx, r13d; dwFlags
0x18000d953  call    cs:__imp_CertCloseStore
0x18000d95a  nop     dword ptr [rax+rax+00h]
0x18000d95f  xor     eax, eax
0x18000d961  add     rsp, 40h
0x18000d965  pop     r15
0x18000d967  pop     r14
0x18000d969  pop     r13
0x18000d96b  pop     rdi
0x18000d96c  pop     rsi
0x18000d96d  pop     rbx
0x18000d96e  pop     rbp
0x18000d96f  retn
```
