# CCertRequest::_FindIssuedCertificate(uchar const *,ulong,_CERT_CONTEXT const * *)

- ea: `0x1800101a0`
- end: `0x180010275`
- name: `?_FindIssuedCertificate@CCertRequest@@AEAAJPEBEKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(CCertRequest *this, const unsigned __int8 *, int, const struct _CERT_CONTEXT **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e9c0`
- `0x18000f9a4`

## callees

- `0x1800101a0`
- `0x180021438`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x1800101de`
- `CRYPT32!CertCreateCertificateContext` at `0x1800101de`
- `CRYPT32!CertFindCertificateInStore` at `0x18001024d`
- `CRYPT32!CertFindCertificateInStore` at `0x18001024d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010208`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010208`

## pseudocode

```c
__int64 __fastcall CCertRequest::_FindIssuedCertificate(
        CCertRequest *this,
        const unsigned __int8 *a2,
        int a3,
        const struct _CERT_CONTEXT **a4)
{
  const BYTE *v5; // rdx
  const struct _CERT_CONTEXT *CertificateContext; // rax
  unsigned int v7; // ebx
  int v8; // edx
  unsigned int v9; // ecx
  void *v10; // rcx
  const struct _CERT_CONTEXT *CertificateInStore; // rax
  _DWORD pvFindPara[2]; // [rsp+30h] [rbp-18h] BYREF
  const unsigned __int8 *v14; // [rsp+38h] [rbp-10h]

  pvFindPara[1] = 0;
  *a4 = 0;
  if ( a2 )
  {
    v10 = (void *)*((_QWORD *)this + 26);
    if ( v10 )
    {
      v14 = a2;
      pvFindPara[0] = a3;
      CertificateInStore = CertFindCertificateInStore(v10, 0x10001u, 0, 0x10000u, pvFindPara, 0);
      *a4 = CertificateInStore;
      if ( !CertificateInStore )
      {
        v7 = myHLastError();
        v8 = v7;
        v9 = 176554692;
        goto LABEL_8;
      }
      return 0;
    }
    v9 = 175571652;
LABEL_7:
    v8 = -2146877436;
    v7 = -2146877436;
    goto LABEL_8;
  }
  if ( *((_DWORD *)this + 56) > 1u || (v5 = (const BYTE *)*((_QWORD *)this + 20)) == 0 )
  {
    v9 = 174457540;
    goto LABEL_7;
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, v5, *((_DWORD *)this + 42));
  *a4 = CertificateContext;
  if ( CertificateContext )
    return 0;
  v7 = myHLastError();
  v8 = v7;
  v9 = 175047364;
LABEL_8:
  CSPrintErrorLineFile(v9, v8);
  return v7;
}

```

## disassembly

```asm
0x1800101a0  push    rbx
0x1800101a2  sub     rsp, 40h
0x1800101a6  mov     [rsp+48h+var_14], 0
0x1800101ae  mov     rbx, r9
0x1800101b1  mov     qword ptr [r9], 0
0x1800101b8  test    rdx, rdx
0x1800101bb  jnz     short loc_180010210
0x1800101bd  cmp     dword ptr [rcx+0E0h], 1
0x1800101c4  ja      short loc_1800101FC
0x1800101c6  mov     rdx, [rcx+0A0h]; pbCertEncoded
0x1800101cd  test    rdx, rdx
0x1800101d0  jz      short loc_1800101FC
0x1800101d2  mov     r8d, [rcx+0A8h]; cbCertEncoded
0x1800101d9  mov     ecx, 10001h; dwCertEncodingType
0x1800101de  call    cs:__imp_CertCreateCertificateContext
0x1800101e4  mov     [rbx], rax
0x1800101e7  test    rax, rax
0x1800101ea  jnz     short loc_18001026B
0x1800101ec  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800101f1  mov     ebx, eax
0x1800101f3  mov     edx, eax
0x1800101f5  mov     ecx, 0A6F02C4h
0x1800101fa  jmp     short loc_180010208
0x1800101fc  mov     ecx, 0A6602C4h
0x180010201  mov     edx, 80094004h
0x180010206  mov     ebx, edx
0x180010208  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001020e  jmp     short loc_18001026D
0x180010210  mov     rcx, [rcx+0D0h]; hCertStore
0x180010217  test    rcx, rcx
0x18001021a  jnz     short loc_180010223
0x18001021c  mov     ecx, 0A7702C4h
0x180010221  jmp     short loc_180010201
0x180010223  mov     r9d, 10000h; dwFindType
0x180010229  mov     [rsp+48h+var_10], rdx
0x18001022e  mov     [rsp+48h+var_18], r8d
0x180010233  lea     rax, [rsp+48h+var_18]
0x180010238  mov     [rsp+48h+pPrevCertContext], 0; pPrevCertContext
0x180010241  xor     r8d, r8d; dwFindFlags
0x180010244  mov     [rsp+48h+pvFindPara], rax; pvFindPara
0x180010249  lea     edx, [r9+1]; dwCertEncodingType
0x18001024d  call    cs:__imp_CertFindCertificateInStore
0x180010253  mov     [rbx], rax
0x180010256  test    rax, rax
0x180010259  jnz     short loc_18001026B
0x18001025b  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010260  mov     ebx, eax
0x180010262  mov     edx, eax
0x180010264  mov     ecx, 0A8602C4h
0x180010269  jmp     short loc_180010208
0x18001026b  xor     ebx, ebx
0x18001026d  mov     eax, ebx
0x18001026f  add     rsp, 40h
0x180010273  pop     rbx
0x180010274  retn
```
