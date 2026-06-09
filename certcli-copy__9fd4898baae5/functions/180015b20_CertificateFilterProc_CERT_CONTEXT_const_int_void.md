# CertificateFilterProc(_CERT_CONTEXT const *,int *,void *)

- ea: `0x180015b20`
- end: `0x180015bda`
- name: `?CertificateFilterProc@@YAHPEBU_CERT_CONTEXT@@PEAHPEAX@Z`
- size: `186`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, int *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180015b20`
- `0x1800168e8`
- `0x180021438`

## import_xrefs

- `CRYPT32!CertAddCertificateLinkToStore` at `0x180015b8b`
- `CRYPT32!CertAddCertificateLinkToStore` at `0x180015b8b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180015b5a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180015b5a`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x180015ba4`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x180015ba4`

## pseudocode

```c
_BOOL8 __fastcall CertificateFilterProc(PCCERT_CONTEXT pCertContext, int *a2, HCERTSTORE *a3)
{
  int matched; // eax
  int v6; // ebx
  bool v7; // cl
  int v8; // eax
  bool v10; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v10 = 0;
  matched = cpCertMatchFilter(pCertContext, (struct _CERTFILTERDATA *)(a3 + 4), &v10);
  v6 = matched;
  if ( !matched )
  {
    v7 = v10;
    if ( v10 )
    {
      if ( !CertAddCertificateLinkToStore(a3[3], pCertContext, (*(_DWORD *)a3 & 0x100000) != 0 ? 4 : 1, 0) )
      {
        v8 = myHLastError();
        CSPrintErrorLineFile2(0xB1C019Bu, v8, v8);
        v6 = 0;
        v7 = 0;
        goto LABEL_8;
      }
      v7 = 1;
    }
    v6 = 0;
    goto LABEL_8;
  }
  CSPrintErrorLineFile(0xB09019Bu, matched);
  v7 = v10;
LABEL_8:
  if ( !*((_DWORD *)a3 + 4) || v7 && *((_DWORD *)a3 + 4) == 1 )
    *((_DWORD *)a3 + 4) = v6;
  return v7;
}

```

## disassembly

```asm
0x180015b20  mov     rax, rsp
0x180015b23  mov     [rax+8], rbx
0x180015b27  mov     [rax+18h], rsi
0x180015b2b  push    rdi
0x180015b2c  sub     rsp, 20h
0x180015b30  mov     dword ptr [rdx], 0
0x180015b36  mov     rdi, r8
0x180015b39  lea     rdx, [r8+20h]; struct _CERTFILTERDATA *
0x180015b3d  mov     byte ptr [rax+10h], 0
0x180015b41  lea     r8, [rax+10h]; bool *
0x180015b45  mov     rsi, rcx
0x180015b48  call    ?cpCertMatchFilter@@YAJPEBU_CERT_CONTEXT@@PEAU_CERTFILTERDATA@@PEA_N@Z; cpCertMatchFilter(_CERT_CONTEXT const *,_CERTFILTERDATA *,bool *)
0x180015b4d  mov     ebx, eax
0x180015b4f  test    eax, eax
0x180015b51  jz      short loc_180015B66
0x180015b53  mov     edx, eax
0x180015b55  mov     ecx, 0B09019Bh
0x180015b5a  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180015b60  mov     cl, [rsp+28h+arg_8]
0x180015b64  jmp     short loc_180015BB4
0x180015b66  mov     cl, [rsp+28h+arg_8]
0x180015b6a  test    cl, cl
0x180015b6c  jz      short loc_180015BB2
0x180015b6e  mov     eax, [rdi]
0x180015b70  mov     rdx, rsi; pCertContext
0x180015b73  mov     rcx, [rdi+18h]; hCertStore
0x180015b77  and     eax, 100000h
0x180015b7c  neg     eax
0x180015b7e  sbb     r8d, r8d
0x180015b81  xor     r9d, r9d; ppStoreContext
0x180015b84  and     r8d, 3
0x180015b88  inc     r8d; dwAddDisposition
0x180015b8b  call    cs:__imp_CertAddCertificateLinkToStore
0x180015b91  test    eax, eax
0x180015b93  jnz     short loc_180015BB0
0x180015b95  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180015b9a  mov     r8d, eax
0x180015b9d  mov     edx, eax
0x180015b9f  mov     ecx, 0B1C019Bh
0x180015ba4  call    cs:__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z; CSPrintErrorLineFile2(ulong,long,long)
0x180015baa  xor     ebx, ebx
0x180015bac  xor     cl, cl
0x180015bae  jmp     short loc_180015BB4
0x180015bb0  mov     cl, 1
0x180015bb2  xor     ebx, ebx
0x180015bb4  cmp     dword ptr [rdi+10h], 0
0x180015bb8  jz      short loc_180015BC4
0x180015bba  test    cl, cl
0x180015bbc  jz      short loc_180015BC7
0x180015bbe  cmp     dword ptr [rdi+10h], 1
0x180015bc2  jnz     short loc_180015BC7
0x180015bc4  mov     [rdi+10h], ebx
0x180015bc7  mov     rbx, [rsp+28h+arg_0]
0x180015bcc  mov     rsi, [rsp+28h+arg_10]
0x180015bd1  movzx   eax, cl
0x180015bd4  add     rsp, 20h
0x180015bd8  pop     rdi
0x180015bd9  retn
```
