# CProvisioningNode::DeleteChild(IConfigManager2URI *)

- ea: `0x18000db50`
- end: `0x18000dca9`
- name: `?DeleteChild@CProvisioningNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `345`
- prototype: `int(CProvisioningNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180006954`
- `0x180006974`
- `0x180008ab0`
- `0x18000db50`
- `0x18000dcb0`
- `0x18000de00`

## import_xrefs

- `CRYPT32!CertDeleteCertificateFromStore` at `0x18000dc34`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18000dc34`
- `CRYPT32!CertCloseStore` at `0x18000dc22`
- `CRYPT32!CertCloseStore` at `0x18000dc67`
- `CRYPT32!CertCloseStore` at `0x18000dc8f`
- `CRYPT32!CertCloseStore` at `0x18000dc22`
- `CRYPT32!CertCloseStore` at `0x18000dc67`
- `CRYPT32!CertCloseStore` at `0x18000dc8f`

## string_xrefs

- `0x18000db6e`: `onecoreuap\admin\prov\provcsp\deletechild.cpp`
- `0x18000dc02`: `onecoreuap\admin\prov\provcsp\deletechild.cpp`
- `0x18000dc48`: `onecoreuap\admin\prov\provcsp\deletechild.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProvisioningNode::DeleteChild(CProvisioningNode *this, struct IConfigManager2URI *a2)
{
  int LastError; // ebx
  __int64 v3; // rdx
  int v5; // ecx
  CProvisioningNode *v6; // rcx
  int CertificateByUri; // eax
  const char *v8; // r9
  HCERTSTORE *p_hCertStore; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  HCERTSTORE hCertStore; // [rsp+48h] [rbp+18h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp+20h] BYREF

  if ( !a2 )
  {
    LastError = -2147467261;
    v3 = 87;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\deletechild.cpp",
      (const char *)(unsigned int)LastError,
      (int)p_hCertStore);
    return (unsigned int)LastError;
  }
  v5 = *((_DWORD *)this + 11) - 1;
  if ( !v5 )
  {
    hCertStore = 0;
    p_hCertStore = &hCertStore;
    pCertContext = 0;
    CertificateByUri = CProvisioningNode::GetCertificateByUri(a2, &pCertContext, &hCertStore);
    LastError = CertificateByUri;
    if ( CertificateByUri < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\deletechild.cpp",
        (const char *)(unsigned int)CertificateByUri,
        (int)&hCertStore);
      if ( hCertStore )
        CertCloseStore(hCertStore, 1u);
LABEL_18:
      v3 = 92;
      goto LABEL_3;
    }
    if ( CertDeleteCertificateFromStore(pCertContext) )
    {
      if ( hCertStore )
        CertCloseStore(hCertStore, 1u);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x39,
                    (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\deletechild.cpp",
                    v8);
      if ( hCertStore )
        CertCloseStore(hCertStore, 1u);
      if ( LastError < 0 )
        goto LABEL_18;
    }
    return 0;
  }
  v6 = (CProvisioningNode *)(unsigned int)(v5 - 6);
  if ( !(_DWORD)v6 )
  {
    LastError = CProvisioningNode::RemoveRequestByName(v6, a2);
    if ( LastError < 0 )
    {
      v3 = 96;
      goto LABEL_3;
    }
    return 0;
  }
  if ( (_DWORD)v6 != 13 )
  {
    LastError = -2046820335;
    v3 = 104;
    goto LABEL_3;
  }
  return InstalledPackageNode::Remove(a2);
}

```

## disassembly

```asm
0x18000db50  mov     [rsp-8+arg_0], rbx
0x18000db55  push    rbp
0x18000db56  mov     rbp, rsp
0x18000db59  sub     rsp, 30h
0x18000db5d  mov     r9, rdx
0x18000db60  test    rdx, rdx
0x18000db63  jnz     short loc_18000DB88
0x18000db65  mov     ebx, 80004003h
0x18000db6a  lea     edx, [r9+57h]; void *
0x18000db6e  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provcsp\\delet"...
0x18000db75  mov     r9d, ebx; char *
0x18000db78  mov     rcx, [rbp+8]; this
0x18000db7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db81  mov     eax, ebx
0x18000db83  jmp     loc_18000DC9D
0x18000db88  mov     ecx, [rcx+2Ch]
0x18000db8b  sub     ecx, 1
0x18000db8e  jz      short loc_18000DBC9
0x18000db90  sub     ecx, 6; this
0x18000db93  jz      short loc_18000DBB3
0x18000db95  cmp     ecx, 0Dh
0x18000db98  jz      short loc_18000DBA6
0x18000db9a  mov     ebx, 86000011h
0x18000db9f  mov     edx, 68h ; 'h'
0x18000dba4  jmp     short loc_18000DB6E
0x18000dba6  mov     rcx, r9; struct IConfigManager2URI *
0x18000dba9  call    ?Remove@InstalledPackageNode@@SAJPEAUIConfigManager2URI@@@Z; InstalledPackageNode::Remove(IConfigManager2URI *)
0x18000dbae  jmp     loc_18000DC9D
0x18000dbb3  call    ?RemoveRequestByName@CProvisioningNode@@AEAAJPEAUIConfigManager2URI@@@Z; CProvisioningNode::RemoveRequestByName(IConfigManager2URI *)
0x18000dbb8  mov     ebx, eax
0x18000dbba  test    eax, eax
0x18000dbbc  jns     loc_18000DC9B
0x18000dbc2  mov     edx, 60h ; '`'
0x18000dbc7  jmp     short loc_18000DB6E
0x18000dbc9  mov     [rbp+hCertStore], 0
0x18000dbd1  lea     rax, [rbp+hCertStore]
0x18000dbd5  mov     [rbp+var_10], rax
0x18000dbd9  mov     [rbp+var_8], 1
0x18000dbdd  mov     [rbp+pCertContext], 0
0x18000dbe5  lea     r8, [rbp+hCertStore]; void **
0x18000dbe9  lea     rdx, [rbp+pCertContext]; struct _CERT_CONTEXT **
0x18000dbed  mov     rcx, r9; struct IConfigManager2URI *
0x18000dbf0  call    ?GetCertificateByUri@CProvisioningNode@@CAJPEAUIConfigManager2URI@@PEAPEBU_CERT_CONTEXT@@PEAPEAX@Z; CProvisioningNode::GetCertificateByUri(IConfigManager2URI *,_CERT_CONTEXT const * *,void * *)
0x18000dbf5  mov     ebx, eax
0x18000dbf7  test    eax, eax
0x18000dbf9  jns     short loc_18000DC30
0x18000dbfb  mov     rcx, [rbp+8]; this
0x18000dbff  mov     r9d, eax; char *
0x18000dc02  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provcsp\\delet"...
0x18000dc09  mov     edx, 38h ; '8'; void *
0x18000dc0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc13  nop
0x18000dc14  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000dc18  test    rcx, rcx
0x18000dc1b  jz      short loc_18000DC77
0x18000dc1d  mov     edx, 1; dwFlags
0x18000dc22  call    cs:__imp_CertCloseStore
0x18000dc29  nop     dword ptr [rax+rax+00h]
0x18000dc2e  jmp     short loc_18000DC77
0x18000dc30  mov     rcx, [rbp+pCertContext]; pCertContext
0x18000dc34  call    cs:__imp_CertDeleteCertificateFromStore
0x18000dc3b  nop     dword ptr [rax+rax+00h]
0x18000dc40  test    eax, eax
0x18000dc42  jnz     short loc_18000DC81
0x18000dc44  mov     rcx, [rbp+8]; this
0x18000dc48  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provcsp\\delet"...
0x18000dc4f  lea     edx, [rax+39h]; void *
0x18000dc52  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dc57  mov     ebx, eax
0x18000dc59  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000dc5d  test    rcx, rcx
0x18000dc60  jz      short loc_18000DC73
0x18000dc62  mov     edx, 1; dwFlags
0x18000dc67  call    cs:__imp_CertCloseStore
0x18000dc6e  nop     dword ptr [rax+rax+00h]
0x18000dc73  test    ebx, ebx
0x18000dc75  jns     short loc_18000DC9B
0x18000dc77  mov     edx, 5Ch ; '\'
0x18000dc7c  jmp     loc_18000DB6E
0x18000dc81  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000dc85  test    rcx, rcx
0x18000dc88  jz      short loc_18000DC9B
0x18000dc8a  mov     edx, 1; dwFlags
0x18000dc8f  call    cs:__imp_CertCloseStore
0x18000dc96  nop     dword ptr [rax+rax+00h]
0x18000dc9b  xor     eax, eax
0x18000dc9d  mov     rbx, [rsp+30h+arg_0]
0x18000dca2  add     rsp, 30h
0x18000dca6  pop     rbp
0x18000dca7  retn
```
