# CProvisioningNode::QueryRegStoreForCertificateByUri(IConfigManager2URI *)

- ea: `0x180009d78`
- end: `0x180009e96`
- name: `?QueryRegStoreForCertificateByUri@CProvisioningNode@@CAJPEAUIConfigManager2URI@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009890`

## callees

- `0x180006974`
- `0x180009b80`
- `0x180009d78`
- `0x180038010`

## import_xrefs

- `CRYPT32!CertFindCertificateInStore` at `0x180009e3b`
- `CRYPT32!CertFindCertificateInStore` at `0x180009e3b`
- `CRYPT32!CertCloseStore` at `0x180009dd7`
- `CRYPT32!CertCloseStore` at `0x180009e77`
- `CRYPT32!CertCloseStore` at `0x180009dd7`
- `CRYPT32!CertCloseStore` at `0x180009e77`
- `CRYPT32!CertFreeCertificateContext` at `0x180009e5c`
- `CRYPT32!CertFreeCertificateContext` at `0x180009e5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProvisioningNode::QueryRegStoreForCertificateByUri(struct IConfigManager2URI *a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  const CERT_CONTEXT *CertificateInStore; // rax
  int pvFindPara; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  HCERTSTORE hCertStore; // [rsp+58h] [rbp+18h] BYREF
  void *v9; // [rsp+60h] [rbp+20h] BYREF

  hCertStore = 0;
  v2 = CProvisioningNode::OpenProvisioningCertStore(&hCertStore);
  if ( v2 < 0 )
  {
    v3 = 50;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provisioningnode.cpp",
      (const char *)(unsigned int)v2,
      pvFindPara);
    if ( hCertStore )
      CertCloseStore(hCertStore, 1u);
    return (unsigned int)v2;
  }
  v9 = 0;
  v2 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, void **))(*(_QWORD *)a1 + 88LL))(a1, 2, &v9);
  if ( v2 < 0 )
  {
    v3 = 55;
    goto LABEL_3;
  }
  CertificateInStore = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x140000u, v9, 0);
  if ( !CertificateInStore )
  {
    v2 = -2046820350;
    v3 = 60;
    goto LABEL_3;
  }
  CertFreeCertificateContext(CertificateInStore);
  if ( hCertStore )
    CertCloseStore(hCertStore, 1u);
  return 0;
}

```

## disassembly

```asm
0x180009d78  mov     [rsp-8+arg_0], rbx
0x180009d7d  mov     [rsp-8+arg_18], rdi
0x180009d82  push    rbp
0x180009d83  mov     rbp, rsp
0x180009d86  sub     rsp, 40h
0x180009d8a  mov     rdi, rcx
0x180009d8d  mov     [rbp+hCertStore], 0
0x180009d95  lea     rax, [rbp+hCertStore]
0x180009d99  mov     [rbp+var_10], rax
0x180009d9d  mov     [rbp+var_8], 1
0x180009da1  lea     rcx, [rbp+hCertStore]; void **
0x180009da5  call    ?OpenProvisioningCertStore@CProvisioningNode@@CAJPEAPEAX@Z; CProvisioningNode::OpenProvisioningCertStore(void * *)
0x180009daa  mov     ebx, eax
0x180009dac  test    eax, eax
0x180009dae  jns     short loc_180009DEA
0x180009db0  mov     edx, 32h ; '2'; void *
0x180009db5  mov     rcx, [rbp+8]; this
0x180009db9  mov     r9d, ebx; char *
0x180009dbc  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\provcsp\\provi"...
0x180009dc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009dc8  nop
0x180009dc9  mov     rcx, [rbp+hCertStore]; hCertStore
0x180009dcd  test    rcx, rcx
0x180009dd0  jz      short loc_180009DE3
0x180009dd2  mov     edx, 1; dwFlags
0x180009dd7  call    cs:__imp_CertCloseStore
0x180009dde  nop     dword ptr [rax+rax+00h]
0x180009de3  mov     eax, ebx
0x180009de5  jmp     loc_180009E85
0x180009dea  mov     [rbp+arg_10], 0
0x180009df2  mov     rax, [rdi]
0x180009df5  lea     r8, [rbp+arg_10]
0x180009df9  mov     edx, 2
0x180009dfe  mov     rcx, rdi
0x180009e01  mov     rax, [rax+58h]
0x180009e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e0a  mov     ebx, eax
0x180009e0c  test    eax, eax
0x180009e0e  jns     short loc_180009E17
0x180009e10  mov     edx, 37h ; '7'
0x180009e15  jmp     short loc_180009DB5
0x180009e17  mov     [rsp+40h+pPrevCertContext], 0; pPrevCertContext
0x180009e20  mov     rax, [rbp+arg_10]
0x180009e24  mov     [rsp+40h+pvFindPara], rax; pvFindPara
0x180009e29  mov     r9d, 140000h; dwFindType
0x180009e2f  xor     r8d, r8d; dwFindFlags
0x180009e32  mov     edx, 10001h; dwCertEncodingType
0x180009e37  mov     rcx, [rbp+hCertStore]; hCertStore
0x180009e3b  call    cs:__imp_CertFindCertificateInStore
0x180009e42  nop     dword ptr [rax+rax+00h]
0x180009e47  test    rax, rax
0x180009e4a  jnz     short loc_180009E59
0x180009e4c  mov     ebx, 86000002h
0x180009e51  lea     edx, [rax+3Ch]
0x180009e54  jmp     loc_180009DB5
0x180009e59  mov     rcx, rax; pCertContext
0x180009e5c  call    cs:__imp_CertFreeCertificateContext
0x180009e63  nop     dword ptr [rax+rax+00h]
0x180009e68  nop
0x180009e69  mov     rcx, [rbp+hCertStore]; hCertStore
0x180009e6d  test    rcx, rcx
0x180009e70  jz      short loc_180009E83
0x180009e72  mov     edx, 1; dwFlags
0x180009e77  call    cs:__imp_CertCloseStore
0x180009e7e  nop     dword ptr [rax+rax+00h]
0x180009e83  xor     eax, eax
0x180009e85  mov     rbx, [rsp+40h+arg_0]
0x180009e8a  mov     rdi, [rsp+40h+arg_18]
0x180009e8f  add     rsp, 40h
0x180009e93  pop     rbp
0x180009e94  retn
```
