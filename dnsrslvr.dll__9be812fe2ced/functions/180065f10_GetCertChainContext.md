# GetCertChainContext

- ea: `0x180065f10`
- end: `0x180066182`
- name: `GetCertChainContext`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180066a28`

## callees

- `0x180008870`
- `0x18000b130`
- `0x18000c640`
- `0x180029f20`
- `0x180046ec0`
- `0x180065ec8`
- `0x180065f10`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800660a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800660a6`
- `CRYPT32!CertFreeCertificateChainList` at `0x18006610e`
- `CRYPT32!CertFreeCertificateChainList` at `0x18006610e`
- `CRYPT32!CertSelectCertificateChains` at `0x1800660d9`
- `CRYPT32!CertSelectCertificateChains` at `0x1800660d9`
- `CRYPT32!CertOpenStore` at `0x180066094`
- `CRYPT32!CertOpenStore` at `0x180066094`
- `CRYPT32!CertCloseStore` at `0x180066153`
- `CRYPT32!CertCloseStore` at `0x180066153`

## pseudocode

```c
__int64 __fastcall GetCertChainContext(__int64 a1, PCCERT_CHAIN_CONTEXT **a2, DWORD *a3)
{
  CERT_SELECT_CRITERIA *v3; // rsi
  void **v4; // r15
  __int64 v5; // r14
  DWORD LastError; // edi
  __int64 v9; // rax
  __int64 v10; // r12
  DWORD v11; // eax
  __int64 v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // rax
  DWORD *v15; // rcx
  __int64 i; // r12
  unsigned int v18; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-3Ch]
  HCERTSTORE hCertStore; // [rsp+48h] [rbp-38h]
  DWORD *v21; // [rsp+50h] [rbp-30h]
  PCCERT_CHAIN_CONTEXT *prgpSelection; // [rsp+58h] [rbp-28h] BYREF
  DWORD pcSelection; // [rsp+60h] [rbp-20h] BYREF
  const char *v24; // [rsp+68h] [rbp-18h] BYREF

  v3 = 0;
  v21 = a3;
  v4 = 0;
  prgpSelection = 0;
  LODWORD(v5) = 0;
  pcSelection = 0;
  hCertStore = 0;
  v18 = 0;
  v24 = "1.3.6.1.5.5.7.3.2";
  if ( a2 )
    *a2 = 0;
  if ( a1 && a2 )
  {
    v5 = *(unsigned int *)(a1 + 40);
    v9 = Dns_Allocate(16LL * (unsigned int)(v5 + 1));
    v3 = (CERT_SELECT_CRITERIA *)v9;
    if ( v9
      && ((*(_DWORD *)v9 = 1, *(_DWORD *)(v9 + 4) = 1, *(_QWORD *)(v9 + 8) = &v24, !(_DWORD)v5)
       || (v4 = (void **)Dns_Allocate(8 * v5)) != 0) )
    {
      v19 = 1;
      v10 = 0;
      while ( 1 )
      {
        if ( (unsigned int)v10 >= (unsigned int)v5 )
        {
          hCertStore = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"my");
          if ( hCertStore && CertSelectCertificateChains(0, 8u, 0, v5 + 1, v3, hCertStore, &pcSelection, &prgpSelection) )
          {
            LastError = 0;
            v15 = v21;
            *a2 = prgpSelection;
            prgpSelection = 0;
            *v15 = pcSelection;
          }
          else
          {
            LastError = GetLastError();
          }
          goto LABEL_21;
        }
        v11 = Dns_CheckedStringLength(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * v10), 256, 1, &v18);
        LastError = v11;
        if ( v11 )
          break;
        v12 = Dns_StringCopyAllocate(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * v10), v18, 1);
        v13 = (__int64 *)&v4[v10];
        *v13 = v12;
        if ( !v12 )
          goto LABEL_4;
        v14 = v19++;
        v10 = (unsigned int)(v10 + 1);
        v3[v14].dwType = 1;
        v3[v14].cPara = 1;
        v3[v14].ppPara = (void **)v13;
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 55, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, v11);
    }
    else
    {
      LastError = 14;
    }
  }
  else
  {
LABEL_4:
    LastError = 87;
  }
LABEL_21:
  FreeCertChain(prgpSelection, pcSelection);
  if ( prgpSelection )
    CertFreeCertificateChainList(prgpSelection);
  if ( v4 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v5; i = (unsigned int)(i + 1) )
    {
      MIDL_user_free(v4[i]);
      v4[i] = 0;
    }
    MIDL_user_free(v4);
  }
  MIDL_user_free(v3);
  CertCloseStore(hCertStore, 2u);
  return LastError;
}

```

## disassembly

```asm
0x180065f10  mov     [rsp-38h+arg_18], rbx
0x180065f15  push    rbp
0x180065f16  push    rsi
0x180065f17  push    rdi
0x180065f18  push    r12
0x180065f1a  push    r13
0x180065f1c  push    r14
0x180065f1e  push    r15
0x180065f20  mov     rbp, rsp
0x180065f23  sub     rsp, 80h
0x180065f2a  mov     rax, cs:__security_cookie
0x180065f31  xor     rax, rsp
0x180065f34  mov     [rbp+var_10], rax
0x180065f38  xor     esi, esi
0x180065f3a  mov     [rbp+var_30], r8
0x180065f3e  xor     r15d, r15d
0x180065f41  mov     [rbp+prgpSelection], 0
0x180065f49  xor     r14d, r14d
0x180065f4c  mov     [rbp+var_20], 0
0x180065f53  mov     [rbp+hCertStore], 0
0x180065f5b  lea     rax, a136155732; "1.3.6.1.5.5.7.3.2"
0x180065f62  mov     [rbp+var_40], esi
0x180065f65  mov     rbx, rdx
0x180065f68  mov     [rbp+var_18], rax
0x180065f6c  mov     r13, rcx
0x180065f6f  test    rdx, rdx
0x180065f72  jz      short loc_180065F77
0x180065f74  mov     [rdx], rsi
0x180065f77  test    r13, r13
0x180065f7a  jnz     short loc_180065F86
0x180065f7c  mov     edi, 57h ; 'W'
0x180065f81  jmp     loc_1800660F9
0x180065f86  test    rbx, rbx
0x180065f89  jz      short loc_180065F7C
0x180065f8b  mov     r14d, [rcx+28h]
0x180065f8f  lea     ecx, [r14+1]
0x180065f93  shl     rcx, 4
0x180065f97  call    Dns_Allocate
0x180065f9c  mov     rsi, rax
0x180065f9f  test    rax, rax
0x180065fa2  jnz     short loc_180065FAE
0x180065fa4  mov     edi, 0Eh
0x180065fa9  jmp     loc_1800660F9
0x180065fae  mov     edi, 1
0x180065fb3  mov     [rax], edi
0x180065fb5  mov     [rax+4], edi
0x180065fb8  lea     rax, [rbp+var_18]
0x180065fbc  mov     [rsi+8], rax
0x180065fc0  test    r14d, r14d
0x180065fc3  jz      short loc_180065FD9
0x180065fc5  mov     rcx, r14
0x180065fc8  shl     rcx, 3
0x180065fcc  call    Dns_Allocate
0x180065fd1  mov     r15, rax
0x180065fd4  test    rax, rax
0x180065fd7  jz      short loc_180065FA4
0x180065fd9  mov     [rbp+var_3C], edi
0x180065fdc  xor     r12d, r12d
0x180065fdf  cmp     r12d, r14d
0x180065fe2  jnb     loc_18006607A
0x180065fe8  mov     rcx, [r13+20h]
0x180065fec  lea     r9, [rbp+var_40]
0x180065ff0  mov     r8d, edi
0x180065ff3  mov     edx, 100h
0x180065ff8  mov     rcx, [rcx+r12*8]
0x180065ffc  call    Dns_CheckedStringLength
0x180066001  mov     edi, eax
0x180066003  test    eax, eax
0x180066005  jnz     short loc_180066052
0x180066007  mov     rcx, [r13+20h]
0x18006600b  lea     r9d, [rax+3]
0x18006600f  mov     edx, [rbp+var_40]
0x180066012  lea     r8d, [rax+1]
0x180066016  mov     rcx, [rcx+r12*8]
0x18006601a  call    Dns_StringCopyAllocate
0x18006601f  lea     rdx, [r15+r12*8]
0x180066023  mov     [rdx], rax
0x180066026  test    rax, rax
0x180066029  jz      loc_180065F7C
0x18006602f  mov     ecx, [rbp+var_3C]
0x180066032  mov     edi, 1
0x180066037  mov     eax, ecx
0x180066039  add     ecx, edi
0x18006603b  add     rax, rax
0x18006603e  mov     [rbp+var_3C], ecx
0x180066041  add     r12d, edi
0x180066044  mov     [rsi+rax*8], edi
0x180066047  mov     [rsi+rax*8+4], edi
0x18006604b  mov     [rsi+rax*8+8], rdx
0x180066050  jmp     short loc_180065FDF
0x180066052  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180066059  jz      loc_1800660F9
0x18006605f  mov     edx, 37h ; '7'
0x180066064  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18006606b  mov     ecx, 40Bh
0x180066070  mov     r9d, eax
0x180066073  call    WPP_SF_d
0x180066078  jmp     short loc_1800660F9
0x18006607a  xor     edx, edx; dwEncodingType
0x18006607c  lea     rax, aMy; "my"
0x180066083  mov     r9d, 28000h; dwFlags
0x180066089  mov     [rsp+80h+pvPara], rax; pvPara
0x18006608e  xor     r8d, r8d; hCryptProv
0x180066091  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180066094  call    cs:__imp_CertOpenStore
0x18006609a  mov     [rbp+hCertStore], rax
0x18006609e  mov     r12, rax
0x1800660a1  test    rax, rax
0x1800660a4  jnz     short loc_1800660B0
0x1800660a6  call    cs:__imp_GetLastError
0x1800660ac  mov     edi, eax
0x1800660ae  jmp     short loc_1800660F9
0x1800660b0  lea     rax, [rbp+prgpSelection]
0x1800660b4  xor     r8d, r8d; pChainParameters
0x1800660b7  mov     [rsp+80h+pprgpSelection], rax; pprgpSelection
0x1800660bc  lea     r9d, [r14+1]; cCriteria
0x1800660c0  lea     rax, [rbp+var_20]
0x1800660c4  xor     ecx, ecx; pSelectionContext
0x1800660c6  mov     [rsp+80h+pcSelection], rax; pcSelection
0x1800660cb  mov     [rsp+80h+hStore], r12; hStore
0x1800660d0  lea     edx, [r8+8]; dwFlags
0x1800660d4  mov     [rsp+80h+pvPara], rsi; rgpCriteria
0x1800660d9  call    cs:__imp_CertSelectCertificateChains
0x1800660df  test    eax, eax
0x1800660e1  jz      short loc_1800660A6
0x1800660e3  mov     rax, [rbp+prgpSelection]
0x1800660e7  xor     edi, edi
0x1800660e9  mov     rcx, [rbp+var_30]
0x1800660ed  mov     [rbx], rax
0x1800660f0  mov     eax, [rbp+var_20]
0x1800660f3  mov     [rbp+prgpSelection], rdi
0x1800660f7  mov     [rcx], eax
0x1800660f9  mov     edx, [rbp+var_20]
0x1800660fc  mov     rcx, [rbp+prgpSelection]
0x180066100  call    FreeCertChain
0x180066105  mov     rcx, [rbp+prgpSelection]; prgpSelection
0x180066109  test    rcx, rcx
0x18006610c  jz      short loc_180066114
0x18006610e  call    cs:__imp_CertFreeCertificateChainList
0x180066114  test    r15, r15
0x180066117  jz      short loc_180066142
0x180066119  xor     r12d, r12d
0x18006611c  test    r14d, r14d
0x18006611f  jz      short loc_18006613A
0x180066121  mov     rcx, [r15+r12*8]; void *
0x180066125  call    MIDL_user_free
0x18006612a  mov     qword ptr [r15+r12*8], 0
0x180066132  inc     r12d
0x180066135  cmp     r12d, r14d
0x180066138  jb      short loc_180066121
0x18006613a  mov     rcx, r15; void *
0x18006613d  call    MIDL_user_free
0x180066142  mov     rcx, rsi; void *
0x180066145  call    MIDL_user_free
0x18006614a  mov     rcx, [rbp+hCertStore]; hCertStore
0x18006614e  mov     edx, 2; dwFlags
0x180066153  call    cs:__imp_CertCloseStore
0x180066159  mov     eax, edi
0x18006615b  mov     rcx, [rbp+var_10]
0x18006615f  xor     rcx, rsp; StackCookie
0x180066162  call    __security_check_cookie
0x180066167  mov     rbx, [rsp+80h+arg_18]
0x18006616f  add     rsp, 80h
0x180066176  pop     r15
0x180066178  pop     r14
0x18006617a  pop     r13
0x18006617c  pop     r12
0x18006617e  pop     rdi
0x18006617f  pop     rsi
0x180066180  pop     rbp
0x180066181  retn
```
