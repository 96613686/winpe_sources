# AddCertificateToStore(void *,_CERT_CONTEXT const *,int,int,ulong *)

- ea: `0x180071f5c`
- end: `0x1800721c1`
- name: `?AddCertificateToStore@@YAHPEAXPEBU_CERT_CONTEXT@@HHPEAK@Z`
- size: `613`
- prototype: `__int64 __usercall@<rax>(HCERTSTORE hCertStore@<rcx>, PCCERT_CONTEXT pCertContext@<rdx>, int@<r8d>, int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180073538`

## callees

- `0x180004bd0`
- `0x18000f350`
- `0x18002c710`
- `0x18007042c`
- `0x180071f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007215c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007215c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071ffb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072004`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072184`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007218e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072197`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800721a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071ffb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072004`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072184`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007218e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072197`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800721a0`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180071fe5`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180071fe5`
- `CRYPT32!CertFreeCertificateContext` at `0x1800720fc`
- `CRYPT32!CertFreeCertificateContext` at `0x1800720fc`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180072122`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180072122`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800720f3`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800720f3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800720b2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800720b2`

## pseudocode

```c
__int64 __fastcall AddCertificateToStore(
        HCERTSTORE hCertStore,
        PCCERT_CONTEXT pCertContext,
        int a3,
        int a4,
        unsigned int *a5)
{
  HCERTSTORE v6; // rax
  unsigned int v7; // r14d
  PCCERT_CONTEXT v8; // rbx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v11; // rax
  DWORD LastError; // eax

  v6 = hCertStore;
  v7 = 1;
  if ( a3 != 1 )
  {
LABEL_17:
    if ( CertAddCertificateContextToStore(v6, pCertContext, 3u, 0) )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, 0);
      ++*a5;
    }
    else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, LastError);
    }
    goto LABEL_23;
  }
  v8 = 0;
  FCertToStr(pCertContext, 0);
  FCertToStr(pCertContext, 1u);
  while ( 1 )
  {
    v8 = CertEnumCertificatesInStore(hCertStore, v8);
    if ( !v8 )
      break;
    LocalFree(0);
    LocalFree(0);
    FCertToStr(v8, 0);
    v9 = 0;
    while ( *v9++ )
      ;
    FCertToStr(v8, 1u);
    v11 = 0;
    while ( *v11++ )
      ;
    if ( a4 && (unsigned int)IsCertNGC(v8) == 1 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, 0);
LABEL_14:
      CertDeleteCertificateFromStore(v8);
      CertFreeCertificateContext(v8);
      --*a5;
      break;
    }
    if ( CompareFileTime(&pCertContext->pCertInfo->NotBefore, &v8->pCertInfo->NotBefore) == 1 )
      goto LABEL_14;
    v7 = 0;
  }
  if ( v7 == 1 )
  {
    v6 = hCertStore;
    goto LABEL_17;
  }
LABEL_23:
  LocalFree(0);
  LocalFree(0);
  LocalFree(0);
  LocalFree(0);
  return v7;
}

```

## disassembly

```asm
0x180071f5c  mov     [rsp-38h+arg_8], rbx
0x180071f61  mov     [rsp-38h+arg_18], r9d
0x180071f66  mov     [rsp-38h+hCertStore], rcx
0x180071f6b  push    rbp
0x180071f6c  push    rsi
0x180071f6d  push    rdi
0x180071f6e  push    r12
0x180071f70  push    r13
0x180071f72  push    r14
0x180071f74  push    r15
0x180071f76  mov     rbp, rsp
0x180071f79  sub     rsp, 40h
0x180071f7d  mov     rdi, [rbp+arg_20]
0x180071f81  lea     rbx, WPP_GLOBAL_Control
0x180071f88  xor     esi, esi
0x180071f8a  xor     r15d, r15d
0x180071f8d  xor     r12d, r12d
0x180071f90  mov     [rbp+var_18], rsi
0x180071f94  mov     r13, rdx
0x180071f97  mov     [rbp+hMem], rsi
0x180071f9b  mov     rax, rcx
0x180071f9e  mov     [rbp+var_10], r15
0x180071fa2  lea     r14d, [rsi+1]
0x180071fa6  cmp     r8d, r14d
0x180071fa9  jnz     loc_180072115
0x180071faf  lea     r9, [rbp+var_18]
0x180071fb3  xor     r8d, r8d
0x180071fb6  xor     edx, edx; dwFlags
0x180071fb8  mov     rcx, r13; pCertContext
0x180071fbb  xor     ebx, ebx
0x180071fbd  call    FCertToStr
0x180071fc2  mov     eax, r14d
0x180071fc5  lea     r9, [rbp+var_10]
0x180071fc9  mov     r8d, eax
0x180071fcc  mov     edx, eax; dwFlags
0x180071fce  mov     rcx, r13; pCertContext
0x180071fd1  call    FCertToStr
0x180071fd6  mov     rsi, [rbp+var_18]
0x180071fda  mov     r15, [rbp+var_10]
0x180071fde  mov     rcx, [rbp+hCertStore]; hCertStore
0x180071fe2  mov     rdx, rbx; pPrevCertContext
0x180071fe5  call    cs:__imp_CertEnumCertificatesInStore
0x180071feb  mov     rbx, rax
0x180071fee  test    rax, rax
0x180071ff1  jz      loc_180072104
0x180071ff7  mov     rcx, [rbp+hMem]; hMem
0x180071ffb  call    cs:__imp_LocalFree
0x180072001  mov     rcx, r12; hMem
0x180072004  call    cs:__imp_LocalFree
0x18007200a  xor     r12d, r12d
0x18007200d  mov     [rbp+var_10], 0
0x180072015  lea     r9, [rbp+var_10]
0x180072019  mov     [rbp+var_18], r12
0x18007201d  xor     r8d, r8d
0x180072020  xor     edx, edx; dwFlags
0x180072022  mov     rcx, rbx; pCertContext
0x180072025  call    FCertToStr
0x18007202a  mov     rcx, [rbp+var_10]
0x18007202e  mov     rax, rsi
0x180072031  mov     r8, rcx
0x180072034  mov     [rbp+hMem], rcx
0x180072038  sub     r8, rsi
0x18007203b  movzx   edx, word ptr [rax]
0x18007203e  movzx   ecx, word ptr [rax+r8]
0x180072043  sub     edx, ecx
0x180072045  jnz     short loc_18007204F
0x180072047  add     rax, 2
0x18007204b  test    ecx, ecx
0x18007204d  jnz     short loc_18007203B
0x18007204f  test    edx, edx
0x180072051  jnz     short loc_180071FDE
0x180072053  lea     eax, [rdx+1]
0x180072056  mov     rcx, rbx; pCertContext
0x180072059  mov     r8d, eax
0x18007205c  lea     r9, [rbp+var_18]
0x180072060  mov     edx, eax; dwFlags
0x180072062  call    FCertToStr
0x180072067  mov     r12, [rbp+var_18]
0x18007206b  mov     rax, r15
0x18007206e  mov     r8, r12
0x180072071  sub     r8, r15
0x180072074  movzx   edx, word ptr [rax]
0x180072077  movzx   ecx, word ptr [rax+r8]
0x18007207c  sub     edx, ecx
0x18007207e  jnz     short loc_180072088
0x180072080  add     rax, 2
0x180072084  test    ecx, ecx
0x180072086  jnz     short loc_180072074
0x180072088  test    edx, edx
0x18007208a  jnz     loc_180071FDE
0x180072090  cmp     [rbp+arg_18], edx
0x180072093  jz      short loc_1800720A2
0x180072095  mov     rcx, rbx; pCertContext
0x180072098  call    ?IsCertNGC@@YAHPEBU_CERT_CONTEXT@@@Z; IsCertNGC(_CERT_CONTEXT const *)
0x18007209d  cmp     eax, 1
0x1800720a0  jz      short loc_1800720C5
0x1800720a2  mov     rdx, [rbx+18h]
0x1800720a6  mov     rcx, [r13+18h]
0x1800720aa  add     rdx, 40h ; '@'; lpFileTime2
0x1800720ae  add     rcx, 40h ; '@'; lpFileTime1
0x1800720b2  call    cs:__imp_CompareFileTime
0x1800720b8  cmp     eax, 1
0x1800720bb  jz      short loc_1800720F0
0x1800720bd  xor     r14d, r14d
0x1800720c0  jmp     loc_180071FDE
0x1800720c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800720cc  lea     rax, WPP_GLOBAL_Control
0x1800720d3  cmp     rcx, rax
0x1800720d6  jz      short loc_1800720F0
0x1800720d8  mov     rcx, [rcx+10h]
0x1800720dc  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x1800720e3  mov     edx, 38h ; '8'
0x1800720e8  mov     r9, rsi
0x1800720eb  call    WPP_SF_S
0x1800720f0  mov     rcx, rbx; pCertContext
0x1800720f3  call    cs:__imp_CertDeleteCertificateFromStore
0x1800720f9  mov     rcx, rbx; pCertContext
0x1800720fc  call    cs:__imp_CertFreeCertificateContext
0x180072102  dec     dword ptr [rdi]
0x180072104  cmp     r14d, 1
0x180072108  jnz     short loc_180072181
0x18007210a  mov     rax, [rbp+hCertStore]
0x18007210e  lea     rbx, WPP_GLOBAL_Control
0x180072115  xor     r9d, r9d; ppStoreContext
0x180072118  mov     rdx, r13; pCertContext
0x18007211b  mov     rcx, rax; hCertStore
0x18007211e  lea     r8d, [r9+3]; dwAddDisposition
0x180072122  call    cs:__imp_CertAddCertificateContextToStore
0x180072128  cmp     eax, 1
0x18007212b  jnz     short loc_180072153
0x18007212d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072134  cmp     rcx, rbx
0x180072137  jz      short loc_18007214F
0x180072139  mov     rcx, [rcx+10h]
0x18007213d  lea     edx, [rax+38h]
0x180072140  mov     r9, rsi
0x180072143  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x18007214a  call    WPP_SF_S
0x18007214f  inc     dword ptr [rdi]
0x180072151  jmp     short loc_180072181
0x180072153  cmp     cs:WPP_GLOBAL_Control, rbx
0x18007215a  jz      short loc_180072181
0x18007215c  call    cs:__imp_GetLastError
0x180072162  mov     rcx, cs:WPP_GLOBAL_Control
0x180072169  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180072170  mov     edx, 3Ah ; ':'
0x180072175  mov     r9d, eax
0x180072178  mov     rcx, [rcx+10h]
0x18007217c  call    WPP_SF_d
0x180072181  mov     rcx, rsi; hMem
0x180072184  call    cs:__imp_LocalFree
0x18007218a  mov     rcx, [rbp+hMem]; hMem
0x18007218e  call    cs:__imp_LocalFree
0x180072194  mov     rcx, r15; hMem
0x180072197  call    cs:__imp_LocalFree
0x18007219d  mov     rcx, r12; hMem
0x1800721a0  call    cs:__imp_LocalFree
0x1800721a6  mov     rbx, [rsp+40h+arg_8]
0x1800721ae  mov     eax, r14d
0x1800721b1  add     rsp, 40h
0x1800721b5  pop     r15
0x1800721b7  pop     r14
0x1800721b9  pop     r13
0x1800721bb  pop     r12
0x1800721bd  pop     rdi
0x1800721be  pop     rsi
0x1800721bf  pop     rbp
0x1800721c0  retn
```
