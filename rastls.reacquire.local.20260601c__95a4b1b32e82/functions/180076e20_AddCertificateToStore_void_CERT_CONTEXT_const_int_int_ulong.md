# AddCertificateToStore(void *,_CERT_CONTEXT const *,int,int,ulong *)

- ea: `0x180076e20`
- end: `0x1800770d6`
- name: `?AddCertificateToStore@@YAHPEAXPEBU_CERT_CONTEXT@@HHPEAK@Z`
- size: `694`
- prototype: `__int64 __usercall@<rax>(HCERTSTORE hCertStore@<rcx>, PCCERT_CONTEXT pCertContext@<rdx>, int@<r8d>, int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007865c`

## callees

- `0x180005010`
- `0x180010140`
- `0x18002e900`
- `0x18007510c`
- `0x180076e20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077052`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076ec5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076ed4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077080`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077090`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007709f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800770ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076ec5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076ed4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077080`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077090`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007709f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800770ae`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180076ea9`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180076ea9`
- `CRYPT32!CertFreeCertificateContext` at `0x180076fe2`
- `CRYPT32!CertFreeCertificateContext` at `0x180076fe2`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180077012`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180077012`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180076fd3`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180076fd3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180076f8c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180076f8c`

## pseudocode

```c
__int64 __fastcall AddCertificateToStore(
        HCERTSTORE hCertStore,
        PCCERT_CONTEXT pCertContext,
        int a3,
        int a4,
        unsigned int *a5)
{
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // r15
  HLOCAL v7; // r12
  HCERTSTORE v9; // rax
  unsigned int v10; // r14d
  PCCERT_CONTEXT v11; // rbx
  unsigned __int16 *v12; // rax
  int v13; // ecx
  int v14; // edx
  unsigned __int16 *v15; // rax
  int v16; // ecx
  int v17; // edx
  DWORD LastError; // eax
  HLOCAL hMem; // [rsp+20h] [rbp-20h]
  HLOCAL v21; // [rsp+28h] [rbp-18h] BYREF
  HLOCAL v22[2]; // [rsp+30h] [rbp-10h] BYREF

  v5 = 0;
  v6 = 0;
  v7 = 0;
  v21 = 0;
  hMem = 0;
  v9 = hCertStore;
  v22[0] = 0;
  v10 = 1;
  if ( a3 != 1 )
  {
LABEL_21:
    if ( CertAddCertificateContextToStore(v9, pCertContext, 3u, 0) )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v5);
      ++*a5;
    }
    else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, LastError);
    }
    goto LABEL_27;
  }
  v11 = 0;
  FCertToStr(pCertContext, 0, 0, (unsigned __int16 **)&v21);
  FCertToStr(pCertContext, 1u, 1, (unsigned __int16 **)v22);
  v5 = (unsigned __int16 *)v21;
  v6 = (unsigned __int16 *)v22[0];
  while ( 1 )
  {
    v11 = CertEnumCertificatesInStore(hCertStore, v11);
    if ( !v11 )
      break;
    LocalFree(hMem);
    LocalFree(v7);
    v7 = 0;
    v22[0] = 0;
    v21 = 0;
    FCertToStr(v11, 0, 0, (unsigned __int16 **)v22);
    v12 = v5;
    hMem = v22[0];
    do
    {
      v13 = *(unsigned __int16 *)((char *)v12 + (char *)v22[0] - (char *)v5);
      v14 = *v12 - v13;
      if ( v14 )
        break;
      ++v12;
    }
    while ( v13 );
    if ( !v14 )
    {
      FCertToStr(v11, 1u, 1, (unsigned __int16 **)&v21);
      v7 = v21;
      v15 = v6;
      do
      {
        v16 = *(unsigned __int16 *)((char *)v15 + (_BYTE *)v21 - (_BYTE *)v6);
        v17 = *v15 - v16;
        if ( v17 )
          break;
        ++v15;
      }
      while ( v16 );
      if ( !v17 )
      {
        if ( a4 && (unsigned int)IsCertNGC(v11) == 1 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v5);
LABEL_18:
          CertDeleteCertificateFromStore(v11);
          CertFreeCertificateContext(v11);
          --*a5;
          break;
        }
        if ( CompareFileTime(&pCertContext->pCertInfo->NotBefore, &v11->pCertInfo->NotBefore) == 1 )
          goto LABEL_18;
        v10 = 0;
      }
    }
  }
  if ( v10 == 1 )
  {
    v9 = hCertStore;
    goto LABEL_21;
  }
LABEL_27:
  LocalFree(v5);
  LocalFree(hMem);
  LocalFree(v6);
  LocalFree(v7);
  return v10;
}

```

## disassembly

```asm
0x180076e20  mov     [rsp-38h+arg_8], rbx
0x180076e25  mov     [rsp-38h+arg_18], r9d
0x180076e2a  mov     [rsp-38h+hCertStore], rcx
0x180076e2f  push    rbp
0x180076e30  push    rsi
0x180076e31  push    rdi
0x180076e32  push    r12
0x180076e34  push    r13
0x180076e36  push    r14
0x180076e38  push    r15
0x180076e3a  mov     rbp, rsp
0x180076e3d  sub     rsp, 40h
0x180076e41  mov     rdi, [rbp+arg_20]
0x180076e45  lea     rbx, WPP_GLOBAL_Control
0x180076e4c  xor     esi, esi
0x180076e4e  xor     r15d, r15d
0x180076e51  xor     r12d, r12d
0x180076e54  mov     [rbp+var_18], rsi
0x180076e58  mov     r13, rdx
0x180076e5b  mov     [rbp+hMem], rsi
0x180076e5f  mov     rax, rcx
0x180076e62  mov     [rbp+var_10], r15
0x180076e66  lea     r14d, [rsi+1]
0x180076e6a  cmp     r8d, r14d
0x180076e6d  jnz     loc_180077005
0x180076e73  lea     r9, [rbp+var_18]
0x180076e77  xor     r8d, r8d
0x180076e7a  xor     edx, edx; dwFlags
0x180076e7c  mov     rcx, r13; pCertContext
0x180076e7f  xor     ebx, ebx
0x180076e81  call    FCertToStr
0x180076e86  mov     eax, r14d
0x180076e89  lea     r9, [rbp+var_10]
0x180076e8d  mov     r8d, eax
0x180076e90  mov     edx, eax; dwFlags
0x180076e92  mov     rcx, r13; pCertContext
0x180076e95  call    FCertToStr
0x180076e9a  mov     rsi, [rbp+var_18]
0x180076e9e  mov     r15, [rbp+var_10]
0x180076ea2  mov     rcx, [rbp+hCertStore]; hCertStore
0x180076ea6  mov     rdx, rbx; pPrevCertContext
0x180076ea9  call    cs:__imp_CertEnumCertificatesInStore
0x180076eb0  nop     dword ptr [rax+rax+00h]
0x180076eb5  mov     rbx, rax
0x180076eb8  test    rax, rax
0x180076ebb  jz      loc_180076FF0
0x180076ec1  mov     rcx, [rbp+hMem]; hMem
0x180076ec5  call    cs:__imp_LocalFree
0x180076ecc  nop     dword ptr [rax+rax+00h]
0x180076ed1  mov     rcx, r12; hMem
0x180076ed4  call    cs:__imp_LocalFree
0x180076edb  nop     dword ptr [rax+rax+00h]
0x180076ee0  xor     r12d, r12d
0x180076ee3  mov     [rbp+var_10], 0
0x180076eeb  lea     r9, [rbp+var_10]
0x180076eef  mov     [rbp+var_18], r12
0x180076ef3  xor     r8d, r8d
0x180076ef6  xor     edx, edx; dwFlags
0x180076ef8  mov     rcx, rbx; pCertContext
0x180076efb  call    FCertToStr
0x180076f00  mov     rcx, [rbp+var_10]
0x180076f04  mov     rax, rsi
0x180076f07  mov     r8, rcx
0x180076f0a  mov     [rbp+hMem], rcx
0x180076f0e  sub     r8, rsi
0x180076f11  movzx   edx, word ptr [rax]
0x180076f14  movzx   ecx, word ptr [rax+r8]
0x180076f19  sub     edx, ecx
0x180076f1b  jnz     short loc_180076F25
0x180076f1d  add     rax, 2
0x180076f21  test    ecx, ecx
0x180076f23  jnz     short loc_180076F11
0x180076f25  test    edx, edx
0x180076f27  jnz     loc_180076EA2
0x180076f2d  lea     eax, [rdx+1]
0x180076f30  mov     rcx, rbx; pCertContext
0x180076f33  mov     r8d, eax
0x180076f36  lea     r9, [rbp+var_18]
0x180076f3a  mov     edx, eax; dwFlags
0x180076f3c  call    FCertToStr
0x180076f41  mov     r12, [rbp+var_18]
0x180076f45  mov     rax, r15
0x180076f48  mov     r8, r12
0x180076f4b  sub     r8, r15
0x180076f4e  movzx   edx, word ptr [rax]
0x180076f51  movzx   ecx, word ptr [rax+r8]
0x180076f56  sub     edx, ecx
0x180076f58  jnz     short loc_180076F62
0x180076f5a  add     rax, 2
0x180076f5e  test    ecx, ecx
0x180076f60  jnz     short loc_180076F4E
0x180076f62  test    edx, edx
0x180076f64  jnz     loc_180076EA2
0x180076f6a  cmp     [rbp+arg_18], edx
0x180076f6d  jz      short loc_180076F7C
0x180076f6f  mov     rcx, rbx; pCertContext
0x180076f72  call    ?IsCertNGC@@YAHPEBU_CERT_CONTEXT@@@Z; IsCertNGC(_CERT_CONTEXT const *)
0x180076f77  cmp     eax, 1
0x180076f7a  jz      short loc_180076FA5
0x180076f7c  mov     rdx, [rbx+18h]
0x180076f80  mov     rcx, [r13+18h]
0x180076f84  add     rdx, 40h ; '@'; lpFileTime2
0x180076f88  add     rcx, 40h ; '@'; lpFileTime1
0x180076f8c  call    cs:__imp_CompareFileTime
0x180076f93  nop     dword ptr [rax+rax+00h]
0x180076f98  cmp     eax, 1
0x180076f9b  jz      short loc_180076FD0
0x180076f9d  xor     r14d, r14d
0x180076fa0  jmp     loc_180076EA2
0x180076fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180076fac  lea     rax, WPP_GLOBAL_Control
0x180076fb3  cmp     rcx, rax
0x180076fb6  jz      short loc_180076FD0
0x180076fb8  mov     rcx, [rcx+10h]
0x180076fbc  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180076fc3  mov     edx, 38h ; '8'
0x180076fc8  mov     r9, rsi
0x180076fcb  call    WPP_SF_S
0x180076fd0  mov     rcx, rbx; pCertContext
0x180076fd3  call    cs:__imp_CertDeleteCertificateFromStore
0x180076fda  nop     dword ptr [rax+rax+00h]
0x180076fdf  mov     rcx, rbx; pCertContext
0x180076fe2  call    cs:__imp_CertFreeCertificateContext
0x180076fe9  nop     dword ptr [rax+rax+00h]
0x180076fee  dec     dword ptr [rdi]
0x180076ff0  cmp     r14d, 1
0x180076ff4  jnz     loc_18007707D
0x180076ffa  mov     rax, [rbp+hCertStore]
0x180076ffe  lea     rbx, WPP_GLOBAL_Control
0x180077005  xor     r9d, r9d; ppStoreContext
0x180077008  mov     rdx, r13; pCertContext
0x18007700b  mov     rcx, rax; hCertStore
0x18007700e  lea     r8d, [r9+3]; dwAddDisposition
0x180077012  call    cs:__imp_CertAddCertificateContextToStore
0x180077019  nop     dword ptr [rax+rax+00h]
0x18007701e  cmp     eax, 1
0x180077021  jnz     short loc_180077049
0x180077023  mov     rcx, cs:WPP_GLOBAL_Control
0x18007702a  cmp     rcx, rbx
0x18007702d  jz      short loc_180077045
0x18007702f  mov     rcx, [rcx+10h]
0x180077033  lea     edx, [rax+38h]
0x180077036  mov     r9, rsi
0x180077039  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077040  call    WPP_SF_S
0x180077045  inc     dword ptr [rdi]
0x180077047  jmp     short loc_18007707D
0x180077049  cmp     cs:WPP_GLOBAL_Control, rbx
0x180077050  jz      short loc_18007707D
0x180077052  call    cs:__imp_GetLastError
0x180077059  nop     dword ptr [rax+rax+00h]
0x18007705e  mov     rcx, cs:WPP_GLOBAL_Control
0x180077065  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x18007706c  mov     edx, 3Ah ; ':'
0x180077071  mov     r9d, eax
0x180077074  mov     rcx, [rcx+10h]
0x180077078  call    WPP_SF_d
0x18007707d  mov     rcx, rsi; hMem
0x180077080  call    cs:__imp_LocalFree
0x180077087  nop     dword ptr [rax+rax+00h]
0x18007708c  mov     rcx, [rbp+hMem]; hMem
0x180077090  call    cs:__imp_LocalFree
0x180077097  nop     dword ptr [rax+rax+00h]
0x18007709c  mov     rcx, r15; hMem
0x18007709f  call    cs:__imp_LocalFree
0x1800770a6  nop     dword ptr [rax+rax+00h]
0x1800770ab  mov     rcx, r12; hMem
0x1800770ae  call    cs:__imp_LocalFree
0x1800770b5  nop     dword ptr [rax+rax+00h]
0x1800770ba  mov     rbx, [rsp+40h+arg_8]
0x1800770c2  mov     eax, r14d
0x1800770c5  add     rsp, 40h
0x1800770c9  pop     r15
0x1800770cb  pop     r14
0x1800770cd  pop     r13
0x1800770cf  pop     r12
0x1800770d1  pop     rdi
0x1800770d2  pop     rsi
0x1800770d3  pop     rbp
0x1800770d4  retn
```
