# CProvisioningNode::GetCertificateByUri(IConfigManager2URI *,_CERT_CONTEXT const * *,void * *)

- ea: `0x18000dcb0`
- end: `0x18000ddf8`
- name: `?GetCertificateByUri@CProvisioningNode@@CAJPEAUIConfigManager2URI@@PEAPEBU_CERT_CONTEXT@@PEAPEAX@Z`
- size: `328`
- prototype: `__int64 __fastcall(struct IConfigManager2URI *, const struct _CERT_CONTEXT **, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d750`
- `0x18000db50`

## callees

- `0x180006974`
- `0x180009b80`
- `0x18000dcb0`
- `0x180038010`

## import_xrefs

- `CRYPT32!CertFindCertificateInStore` at `0x18000ddbd`
- `CRYPT32!CertFindCertificateInStore` at `0x18000ddbd`
- `CRYPT32!CertCloseStore` at `0x18000dd88`
- `CRYPT32!CertCloseStore` at `0x18000dd88`

## string_xrefs

- `0x18000dcf7`: `onecoreuap\admin\prov\provcsp\deletechild.cpp`
- `0x18000dd6b`: `onecoreuap\admin\prov\provcsp\deletechild.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningNode::GetCertificateByUri(
        struct IConfigManager2URI *a1,
        const struct _CERT_CONTEXT **a2,
        void **a3)
{
  __int64 v3; // rax
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v10; // rax
  __int64 v11; // rdx
  const struct _CERT_CONTEXT *CertificateInStore; // rax
  int pvFindPara; // [rsp+20h] [rbp-20h]
  void *v14; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int v16; // [rsp+60h] [rbp+20h] BYREF
  HCERTSTORE hCertStore; // [rsp+78h] [rbp+38h] BYREF

  v3 = *(_QWORD *)a1;
  v16 = 0;
  v7 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(v3 + 136))(a1, &v16);
  if ( v7 < 0 )
  {
    v8 = 17;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\deletechild.cpp",
      (const char *)(unsigned int)v7,
      pvFindPara);
    return (unsigned int)v7;
  }
  if ( !v16 )
  {
    v7 = -2147024809;
    v8 = 18;
    goto LABEL_3;
  }
  v10 = *(_QWORD *)a1;
  v14 = 0;
  v7 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, void **))(v10 + 88))(
         a1,
         (unsigned int)(v16 - 1),
         &v14);
  if ( v7 < 0 )
  {
    v8 = 21;
    goto LABEL_3;
  }
  hCertStore = 0;
  v7 = CProvisioningNode::OpenProvisioningCertStore(&hCertStore);
  if ( v7 < 0 )
  {
    v11 = 31;
    goto LABEL_11;
  }
  CertificateInStore = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x140000u, v14, 0);
  if ( !CertificateInStore )
  {
    v7 = -2046820350;
    v11 = 37;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\deletechild.cpp",
      (const char *)(unsigned int)v7,
      pvFindPara);
    if ( hCertStore )
      CertCloseStore(hCertStore, 1u);
    return (unsigned int)v7;
  }
  *a2 = CertificateInStore;
  *a3 = hCertStore;
  return 0;
}

```

## disassembly

```asm
0x18000dcb0  mov     [rsp-18h+arg_8], rbx
0x18000dcb5  mov     [rsp-18h+arg_10], rsi
0x18000dcba  push    rbp
0x18000dcbb  push    rdi
0x18000dcbc  push    r14
0x18000dcbe  mov     rbp, rsp
0x18000dcc1  sub     rsp, 40h
0x18000dcc5  mov     rax, [rcx]
0x18000dcc8  mov     r14, rdx
0x18000dccb  lea     rdx, [rbp+arg_0]
0x18000dccf  mov     [rbp+arg_0], 0
0x18000dcd6  mov     rsi, r8
0x18000dcd9  mov     rdi, rcx
0x18000dcdc  mov     rax, [rax+88h]
0x18000dce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce8  mov     ebx, eax
0x18000dcea  test    eax, eax
0x18000dcec  jns     short loc_18000DD0D
0x18000dcee  mov     edx, 11h; void *
0x18000dcf3  mov     rcx, [rbp+18h]; this
0x18000dcf7  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provcsp\\delet"...
0x18000dcfe  mov     r9d, ebx; char *
0x18000dd01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd06  mov     eax, ebx
0x18000dd08  jmp     loc_18000DDE4
0x18000dd0d  mov     edx, [rbp+arg_0]
0x18000dd10  cmp     edx, 1
0x18000dd13  jnb     short loc_18000DD21
0x18000dd15  mov     ebx, 80070057h
0x18000dd1a  mov     edx, 12h
0x18000dd1f  jmp     short loc_18000DCF3
0x18000dd21  mov     rax, [rdi]
0x18000dd24  lea     r8, [rbp+var_10]
0x18000dd28  dec     edx
0x18000dd2a  mov     [rbp+var_10], 0
0x18000dd32  mov     rcx, rdi
0x18000dd35  mov     rax, [rax+58h]
0x18000dd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd3e  mov     ebx, eax
0x18000dd40  test    eax, eax
0x18000dd42  jns     short loc_18000DD4B
0x18000dd44  mov     edx, 15h
0x18000dd49  jmp     short loc_18000DCF3
0x18000dd4b  lea     rcx, [rbp+hCertStore]; void **
0x18000dd4f  mov     [rbp+hCertStore], 0
0x18000dd57  call    ?OpenProvisioningCertStore@CProvisioningNode@@CAJPEAPEAX@Z; CProvisioningNode::OpenProvisioningCertStore(void * *)
0x18000dd5c  mov     ebx, eax
0x18000dd5e  test    eax, eax
0x18000dd60  jns     short loc_18000DD99
0x18000dd62  mov     edx, 1Fh; void *
0x18000dd67  mov     rcx, [rbp+18h]; this
0x18000dd6b  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provcsp\\delet"...
0x18000dd72  mov     r9d, ebx; char *
0x18000dd75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd7a  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000dd7e  test    rcx, rcx
0x18000dd81  jz      short loc_18000DD06
0x18000dd83  mov     edx, 1; dwFlags
0x18000dd88  call    cs:__imp_CertCloseStore
0x18000dd8f  nop     dword ptr [rax+rax+00h]
0x18000dd94  jmp     loc_18000DD06
0x18000dd99  mov     rax, [rbp+var_10]
0x18000dd9d  mov     r9d, 140000h; dwFindType
0x18000dda3  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000dda7  xor     r8d, r8d; dwFindFlags
0x18000ddaa  mov     [rsp+40h+pPrevCertContext], 0; pPrevCertContext
0x18000ddb3  mov     edx, 10001h; dwCertEncodingType
0x18000ddb8  mov     [rsp+40h+pvFindPara], rax; pvFindPara
0x18000ddbd  call    cs:__imp_CertFindCertificateInStore
0x18000ddc4  nop     dword ptr [rax+rax+00h]
0x18000ddc9  test    rax, rax
0x18000ddcc  jnz     short loc_18000DDD8
0x18000ddce  mov     ebx, 86000002h
0x18000ddd3  lea     edx, [rax+25h]
0x18000ddd6  jmp     short loc_18000DD67
0x18000ddd8  mov     [r14], rax
0x18000dddb  mov     rax, [rbp+hCertStore]
0x18000dddf  mov     [rsi], rax
0x18000dde2  xor     eax, eax
0x18000dde4  mov     rbx, [rsp+40h+arg_8]
0x18000dde9  mov     rsi, [rsp+40h+arg_10]
0x18000ddee  add     rsp, 40h
0x18000ddf2  pop     r14
0x18000ddf4  pop     rdi
0x18000ddf5  pop     rbp
0x18000ddf6  retn
```
