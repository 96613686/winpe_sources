# _VerifyCertContext(bool,_CERT_CONTEXT const *,ulong,char const * const *,void *,void *)

- ea: `0x180001140`
- end: `0x180001478`
- name: `?_VerifyCertContext@@YAJ_NPEBU_CERT_CONTEXT@@KPEBQEBDPEAX3@Z`
- size: `824`
- prototype: `__int64 __fastcall(char, const struct _CERT_CONTEXT *, DWORD, LPSTR *, PCCERT_CHAIN_CONTEXT pChainContext, HCERTSTORE hAdditionalStore)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180001970`
- `0x180005910`
- `0x180006080`

## callees

- `0x180001140`
- `0x180003750`
- `0x180004db0`
- `0x180009bbc`
- `0x18000a7ce`

## import_xrefs

- `CRYPT32!CertGetCertificateChain` at `0x1800011ec`
- `CRYPT32!CertGetCertificateChain` at `0x1800011ec`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18000138f`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18000138f`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180001253`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180001253`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000145b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000145b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800013a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800013a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800011f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000125d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800013f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800011f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000125d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800013f6`

## pseudocode

```c
__int64 __fastcall _VerifyCertContext(
        char a1,
        const struct _CERT_CONTEXT *a2,
        DWORD a3,
        LPSTR *a4,
        PCCERT_CHAIN_CONTEXT pChainContext,
        HCERTSTORE hAdditionalStore)
{
  struct _CTL_USAGE *v10; // rbx
  signed int v11; // eax
  DWORD dwError; // r14d
  signed int LastError; // eax
  PCERT_SIMPLE_CHAIN v14; // rdx
  DWORD cElement; // eax
  __int64 v16; // rcx
  PCERT_CHAIN_ELEMENT v17; // rdx
  PCCERT_CONTEXT pCertContext; // rax
  unsigned int v19; // ecx
  HLOCAL hMem; // [rsp+40h] [rbp-89h] BYREF
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+48h] [rbp-81h] BYREF
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+60h] [rbp-69h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+70h] [rbp-59h] BYREF
  int v25; // [rsp+A8h] [rbp-21h]
  DWORD pcbUsage; // [rsp+130h] [rbp+67h] BYREF

  pChainContext = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  memset_0(&pChainPara, 0, 0x60u);
  pChainPara.cbSize = 96;
  v10 = 0;
  v25 = 0;
  pPolicyPara.pvExtraPolicyPara = 0;
  pPolicyPara.cbSize = 16;
  pPolicyPara.dwFlags = 4;
  if ( a3 && a4 )
  {
    pChainPara.RequestedUsage.dwType = 1;
    pChainPara.RequestedUsage.Usage.cUsageIdentifier = a3;
    pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = a4;
  }
  if ( CertGetCertificateChain((HCERTCHAINENGINE)1, a2, 0, hAdditionalStore, &pChainPara, 0, 0, &pChainContext) )
  {
    *(_QWORD *)&pPolicyStatus.cbSize = 24;
    pPolicyStatus.pvExtraPolicyStatus = 0;
    *(_QWORD *)&pPolicyStatus.lChainIndex = -1;
    if ( CertVerifyCertificateChainPolicy((LPCSTR)1, pChainContext, &pPolicyPara, &pPolicyStatus) )
    {
      dwError = pPolicyStatus.dwError;
      if ( pPolicyStatus.dwError )
      {
        if ( (int)pPolicyStatus.dwError > 0 )
          dwError = LOWORD(pPolicyStatus.dwError) | 0x80070000;
        ekTraceFmt(0xCD12C3u, 1u, "ERROR: PolicyStatus Hr=%x\n", dwError);
        if ( dwError )
        {
          if ( pChainContext->cChain )
          {
            v14 = *pChainContext->rgpChain;
            cElement = v14->cElement;
            if ( cElement )
            {
              v16 = cElement - 1;
              v17 = v14->rgpElement[v16];
              if ( (v17->TrustStatus.dwInfoStatus & 8) == 0 )
              {
                pCertContext = v17->pCertContext;
                hMem = 0;
                _CertNameToStr(v16, &pCertContext->pCertInfo->Issuer, 0x2200003u, (unsigned __int16 **)&hMem);
                ekTraceFmt(0xFB12C3u, 1u, "ERROR: Missing Issuer=%ws\n", hMem);
                LocalFree(hMem);
              }
            }
          }
          if ( a1 )
          {
            if ( a3 && a4 )
            {
              pcbUsage = 0;
              while ( 1 )
              {
                if ( !CertGetEnhancedKeyUsage(a2, 2u, v10, &pcbUsage) )
                {
                  dwError = GetLastError();
                  ekTraceFmt(0x12612C3u, 1u, "ERROR: Missing EKU\n");
                  goto LABEL_38;
                }
                if ( v10 )
                  break;
                v10 = (struct _CTL_USAGE *)LocalAlloc(0, pcbUsage);
                if ( !v10 )
                {
                  dwError = -2147024882;
                  ekTraceFmt(0x13112C3u, 1u, "ERROR: LocalAlloc. Hr=%x\n", -2147024882);
                  goto LABEL_38;
                }
              }
              dwError = _VerifyEKU(v10, a3, (const char *const *)a4);
              if ( dwError )
              {
                v19 = 20845251;
                goto LABEL_37;
              }
              dwError = 0;
            }
          }
          else
          {
            ekTraceFmt(0x10C12C3u, 1u, "ERROR: Cert Chain: Hr=%x\n", dwError);
          }
        }
      }
      else
      {
        dwError = 0;
        if ( a3 )
        {
          if ( a4 )
          {
            dwError = _VerifyEKU(
                        (*(*pChainContext->rgpChain)->rgpElement)->pApplicationUsage,
                        a3,
                        (const char *const *)a4);
            if ( dwError )
            {
              v19 = 14422723;
LABEL_37:
              ekTraceFmt(v19, 1u, "ERROR: _VerifyEKU\n");
            }
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      dwError = LastError;
      if ( LastError > 0 )
        dwError = (unsigned __int16)LastError | 0x80070000;
      ekTraceFmt(0xC412C3u, 1u, "ERROR: CertVerifyCertificateChainPolicy. Hr=%x\n", dwError);
    }
  }
  else
  {
    v11 = GetLastError();
    dwError = v11;
    if ( v11 > 0 )
      dwError = (unsigned __int16)v11 | 0x80070000;
    ekTraceFmt(0xAC12C3u, 1u, "ERROR: CertGetCertificateChain. Hr=%x\n", dwError);
  }
LABEL_38:
  LocalFree(v10);
  return dwError;
}

```

## disassembly

```asm
0x180001140  push    rbp
0x180001142  push    rbx
0x180001143  push    rsi
0x180001144  push    rdi
0x180001145  push    r12
0x180001147  push    r13
0x180001149  push    r14
0x18000114b  push    r15
0x18000114d  lea     rbp, [rsp-0Fh]
0x180001152  sub     rsp, 0D8h
0x180001159  mov     r12d, r8d
0x18000115c  mov     rsi, rdx
0x18000115f  movzx   r15d, cl
0x180001163  xorps   xmm0, xmm0
0x180001166  xor     eax, eax
0x180001168  lea     rcx, [rbp+47h+var_A0]; void *
0x18000116c  xor     edi, edi
0x18000116e  mov     [rbp+47h+pPolicyStatus.pvExtraPolicyStatus], rax
0x180001172  xor     edx, edx; Val
0x180001174  mov     [rbp+47h+pChainContext], rdi
0x180001178  mov     r8d, 60h ; '`'; Size
0x18000117e  mov     r13, r9
0x180001181  movups  xmmword ptr [rsp+110h+pPolicyStatus.cbSize], xmm0
0x180001186  call    memset_0
0x18000118b  mov     [rbp+47h+var_A0.cbSize], 60h ; '`'
0x180001192  mov     ebx, edi
0x180001194  mov     [rbp+47h+var_68], edi
0x180001197  mov     [rbp+47h+pPolicyPara.pvExtraPolicyPara], rdi
0x18000119b  mov     [rbp+47h+pPolicyPara.cbSize], 10h
0x1800011a2  mov     [rbp+47h+pPolicyPara.dwFlags], 4
0x1800011a9  test    r12d, r12d
0x1800011ac  jz      short loc_1800011C2
0x1800011ae  test    r13, r13
0x1800011b1  jz      short loc_1800011C2
0x1800011b3  mov     [rbp+47h+var_A0.RequestedUsage.dwType], 1
0x1800011ba  mov     [rbp+47h+var_A0.RequestedUsage.Usage.cUsageIdentifier], r12d
0x1800011be  mov     [rbp+47h+var_A0.RequestedUsage.Usage.rgpszUsageIdentifier], r13
0x1800011c2  mov     r9, [rbp+47h+hAdditionalStore]; hAdditionalStore
0x1800011c6  lea     rax, [rbp+47h+pChainContext]
0x1800011ca  mov     [rsp+110h+ppChainContext], rax; ppChainContext
0x1800011cf  xor     r8d, r8d; pTime
0x1800011d2  mov     [rsp+110h+pvReserved], rdi; pvReserved
0x1800011d7  lea     rax, [rbp+47h+var_A0]
0x1800011db  mov     [rsp+110h+dwFlags], edi; dwFlags
0x1800011df  mov     rdx, rsi; pCertContext
0x1800011e2  mov     ecx, 1; hChainEngine
0x1800011e7  mov     [rsp+110h+pChainPara], rax; pChainPara
0x1800011ec  call    cs:__imp_CertGetCertificateChain
0x1800011f2  test    eax, eax
0x1800011f4  jnz     short loc_18000122C
0x1800011f6  call    cs:__imp_GetLastError
0x1800011fc  mov     r14d, eax
0x1800011ff  test    eax, eax
0x180001201  jle     short loc_18000120E
0x180001203  movzx   r14d, ax
0x180001207  or      r14d, 80070000h
0x18000120e  mov     r9d, r14d
0x180001211  lea     r8, aErrorCertgetce; "ERROR: CertGetCertificateChain. Hr=%x\n"
0x180001218  mov     edx, 1; unsigned int
0x18000121d  mov     ecx, 0AC12C3h; unsigned int
0x180001222  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001227  jmp     loc_180001458
0x18000122c  mov     rdx, [rbp+47h+pChainContext]; pChainContext
0x180001230  lea     r9, [rsp+110h+pPolicyStatus]; pPolicyStatus
0x180001235  lea     r8, [rbp+47h+pPolicyPara]; pPolicyPara
0x180001239  mov     qword ptr [rsp+110h+pPolicyStatus.cbSize], 18h
0x180001242  mov     ecx, 1; pszPolicyOID
0x180001247  mov     [rbp+47h+pPolicyStatus.pvExtraPolicyStatus], rdi
0x18000124b  mov     qword ptr [rbp+47h+pPolicyStatus.lChainIndex], 0FFFFFFFFFFFFFFFFh
0x180001253  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180001259  test    eax, eax
0x18000125b  jnz     short loc_180001293
0x18000125d  call    cs:__imp_GetLastError
0x180001263  mov     r14d, eax
0x180001266  test    eax, eax
0x180001268  jle     short loc_180001275
0x18000126a  movzx   r14d, ax
0x18000126e  or      r14d, 80070000h
0x180001275  mov     r9d, r14d
0x180001278  lea     r8, aErrorCertverif; "ERROR: CertVerifyCertificateChainPolicy"...
0x18000127f  mov     edx, 1; unsigned int
0x180001284  mov     ecx, 0C412C3h; unsigned int
0x180001289  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000128e  jmp     loc_180001458
0x180001293  mov     r14d, [rbp+47h+pPolicyStatus.dwError]
0x180001297  test    r14d, r14d
0x18000129a  jz      loc_18000140D
0x1800012a0  jle     short loc_1800012AD
0x1800012a2  movzx   r14d, r14w
0x1800012a6  or      r14d, 80070000h
0x1800012ad  mov     r9d, r14d
0x1800012b0  lea     r8, aErrorPolicysta; "ERROR: PolicyStatus Hr=%x\n"
0x1800012b7  mov     edx, 1; unsigned int
0x1800012bc  mov     ecx, 0CD12C3h; unsigned int
0x1800012c1  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800012c6  test    r14d, r14d
0x1800012c9  jz      loc_180001458
0x1800012cf  mov     rax, [rbp+47h+pChainContext]
0x1800012d3  cmp     [rax+0Ch], ebx
0x1800012d6  jbe     short loc_18000133F
0x1800012d8  mov     rax, [rax+10h]
0x1800012dc  mov     rdx, [rax]
0x1800012df  mov     eax, [rdx+0Ch]
0x1800012e2  test    eax, eax
0x1800012e4  jz      short loc_18000133F
0x1800012e6  lea     ecx, [rax-1]; unsigned int
0x1800012e9  mov     rax, [rdx+10h]
0x1800012ed  mov     rdx, [rax+rcx*8]
0x1800012f1  mov     eax, [rdx+14h]
0x1800012f4  test    al, 8
0x1800012f6  jnz     short loc_18000133F
0x1800012f8  mov     rax, [rdx+8]
0x1800012fc  lea     r9, [rsp+110h+hMem]; unsigned __int16 **
0x180001301  mov     r8d, 2200003h; unsigned int
0x180001307  mov     [rsp+110h+hMem], rdi
0x18000130c  mov     rdx, [rax+18h]
0x180001310  add     rdx, 30h ; '0'; struct _CRYPTOAPI_BLOB *
0x180001314  call    ?_CertNameToStr@@YAJKPEBU_CRYPTOAPI_BLOB@@KPEAPEAG@Z; _CertNameToStr(ulong,_CRYPTOAPI_BLOB const *,ulong,ushort * *)
0x180001319  mov     r9, [rsp+110h+hMem]
0x18000131e  lea     r8, aErrorMissingIs; "ERROR: Missing Issuer=%ws\n"
0x180001325  mov     edx, 1; unsigned int
0x18000132a  mov     ecx, 0FB12C3h; unsigned int
0x18000132f  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001334  mov     rcx, [rsp+110h+hMem]; hMem
0x180001339  call    cs:__imp_LocalFree
0x18000133f  test    r15b, r15b
0x180001342  jnz     short loc_180001362
0x180001344  mov     r9d, r14d
0x180001347  lea     r8, aErrorCertChain; "ERROR: Cert Chain: Hr=%x\n"
0x18000134e  mov     edx, 1; unsigned int
0x180001353  mov     ecx, 10C12C3h; unsigned int
0x180001358  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000135d  jmp     loc_180001458
0x180001362  test    r12d, r12d
0x180001365  jz      loc_180001458
0x18000136b  test    r13, r13
0x18000136e  jz      loc_180001458
0x180001374  mov     [rbp+47h+pcbUsage], edi
0x180001377  nop     word ptr [rax+rax+00000000h]
0x180001380  lea     r9, [rbp+47h+pcbUsage]; pcbUsage
0x180001384  mov     r8, rbx; pUsage
0x180001387  mov     edx, 2; dwFlags
0x18000138c  mov     rcx, rsi; pCertContext
0x18000138f  call    cs:__imp_CertGetEnhancedKeyUsage
0x180001395  test    eax, eax
0x180001397  jz      short loc_1800013F6
0x180001399  test    rbx, rbx
0x18000139c  jnz     short loc_1800013D5
0x18000139e  mov     edx, [rbp+47h+pcbUsage]; uBytes
0x1800013a1  xor     ecx, ecx; uFlags
0x1800013a3  call    cs:__imp_LocalAlloc
0x1800013a9  mov     rbx, rax
0x1800013ac  test    rax, rax
0x1800013af  jnz     short loc_180001380
0x1800013b1  mov     r14d, 8007000Eh
0x1800013b7  lea     r8, aErrorLocalallo_1; "ERROR: LocalAlloc. Hr=%x\n"
0x1800013be  mov     r9d, r14d
0x1800013c1  mov     edx, 1; unsigned int
0x1800013c6  mov     ecx, 13112C3h; unsigned int
0x1800013cb  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800013d0  jmp     loc_180001458
0x1800013d5  mov     r8, r13; char **
0x1800013d8  mov     edx, r12d; unsigned int
0x1800013db  mov     rcx, rbx; struct _CTL_USAGE *
0x1800013de  call    ?_VerifyEKU@@YAJPEBU_CTL_USAGE@@KPEBQEBD@Z; _VerifyEKU(_CTL_USAGE const *,ulong,char const * const *)
0x1800013e3  mov     r14d, eax
0x1800013e6  test    eax, eax
0x1800013e8  jz      short loc_1800013F1
0x1800013ea  mov     ecx, 13E12C3h
0x1800013ef  jmp     short loc_180001447
0x1800013f1  mov     r14d, edi
0x1800013f4  jmp     short loc_180001458
0x1800013f6  call    cs:__imp_GetLastError
0x1800013fc  lea     r8, aErrorMissingEk; "ERROR: Missing EKU\n"
0x180001403  mov     ecx, 12612C3h
0x180001408  mov     r14d, eax
0x18000140b  jmp     short loc_18000144E
0x18000140d  mov     r14d, edi
0x180001410  test    r12d, r12d
0x180001413  jz      short loc_180001458
0x180001415  test    r13, r13
0x180001418  jz      short loc_180001458
0x18000141a  mov     rax, [rbp+47h+pChainContext]
0x18000141e  mov     r8, r13; char **
0x180001421  mov     edx, r12d; unsigned int
0x180001424  mov     rcx, [rax+10h]
0x180001428  mov     rax, [rcx]
0x18000142b  mov     rcx, [rax+10h]
0x18000142f  mov     rcx, [rcx]
0x180001432  mov     rcx, [rcx+28h]; struct _CTL_USAGE *
0x180001436  call    ?_VerifyEKU@@YAJPEBU_CTL_USAGE@@KPEBQEBD@Z; _VerifyEKU(_CTL_USAGE const *,ulong,char const * const *)
0x18000143b  mov     r14d, eax
0x18000143e  test    eax, eax
0x180001440  jz      short loc_180001458
0x180001442  mov     ecx, 0DC12C3h; unsigned int
0x180001447  lea     r8, aErrorVerifyeku; "ERROR: _VerifyEKU\n"
0x18000144e  mov     edx, 1; unsigned int
0x180001453  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001458  mov     rcx, rbx; hMem
0x18000145b  call    cs:__imp_LocalFree
0x180001461  mov     eax, r14d
0x180001464  add     rsp, 0D8h
0x18000146b  pop     r15
0x18000146d  pop     r14
0x18000146f  pop     r13
0x180001471  pop     r12
0x180001473  pop     rdi
0x180001474  pop     rsi
0x180001475  pop     rbx
0x180001476  pop     rbp
0x180001477  retn
```
