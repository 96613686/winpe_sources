# CredSSPGetSerializedCerts

- ea: `0x1800032a0`
- end: `0x180003513`
- name: `CredSSPGetSerializedCerts`
- size: `627`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned int *, _QWORD *, DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002560`

## callees

- `0x1800032a0`
- `0x180003dd9`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003312`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003424`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003312`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003424`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034ef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800032f7`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000333b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800032f7`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000333b`
- `CRYPT32!CertGetCertificateChain` at `0x1800033a1`
- `CRYPT32!CertGetCertificateChain` at `0x1800033a1`
- `CRYPT32!CertFreeCertificateChain` at `0x1800034e1`
- `CRYPT32!CertFreeCertificateChain` at `0x1800034e1`

## pseudocode

```c
__int64 __fastcall CredSSPGetSerializedCerts(
        PCCERT_CONTEXT pCertContext,
        unsigned int *a2,
        _QWORD *a3,
        DWORD *a4,
        _QWORD *a5)
{
  DWORD v5; // r12d
  HLOCAL v9; // rax
  void *v10; // rbx
  unsigned int v11; // esi
  PCCERT_CHAIN_CONTEXT v12; // r8
  HCERTSTORE hCertStore; // r9
  BOOL CertificateChain; // eax
  PCERT_SIMPLE_CHAIN *rgpChain; // rax
  unsigned int v16; // edx
  DWORD v17; // r9d
  DWORD cElement; // r10d
  PCERT_CHAIN_ELEMENT *rgpElement; // r11
  unsigned int v20; // eax
  unsigned __int64 v21; // rax
  unsigned int v22; // r14d
  _DWORD *v23; // rax
  _DWORD *v24; // r15
  DWORD *v25; // r9
  _DWORD *v26; // rbx
  __int64 v27; // rdi
  PCCERT_CONTEXT v28; // rdx
  PCERT_SIMPLE_CHAIN v29; // rdx
  DWORD pcbData; // [rsp+48h] [rbp-51h] BYREF
  PCCERT_CHAIN_CONTEXT ppChainContext; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v33[3]; // [rsp+58h] [rbp-41h]
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+70h] [rbp-29h] BYREF

  v5 = 0;
  v33[0] = 0;
  ppChainContext = 0;
  pcbData = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  if ( CertGetCertificateContextProperty(pCertContext, 0x46u, 0, &pcbData) && pcbData )
  {
    v9 = LocalAlloc(0x40u, pcbData);
    v10 = v9;
    if ( !v9 )
    {
      v11 = -2146893056;
LABEL_5:
      v12 = ppChainContext;
      goto LABEL_25;
    }
    if ( !CertGetCertificateContextProperty(pCertContext, 0x46u, v9, &pcbData) )
    {
      v11 = -2146893043;
      goto LABEL_5;
    }
    *a4 = pcbData;
    *a5 = v10;
  }
  hCertStore = pCertContext->hCertStore;
  *(_OWORD *)&v33[1] = 0;
  *(_OWORD *)(&pChainPara.RequestedUsage.dwType + 1) = *(_OWORD *)((char *)v33 + 4);
  pChainPara.cbSize = 32;
  pChainPara.RequestedUsage.dwType = 0;
  HIDWORD(pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
  CertificateChain = CertGetCertificateChain(0, pCertContext, 0, hCertStore, &pChainPara, 0, 0, &ppChainContext);
  v12 = ppChainContext;
  if ( CertificateChain && ppChainContext->cChain )
  {
    rgpChain = ppChainContext->rgpChain;
    v16 = 0;
    v17 = 0;
    cElement = (*rgpChain)->cElement;
    if ( cElement )
    {
      rgpElement = (*rgpChain)->rgpElement;
      while ( 1 )
      {
        v20 = v16 + rgpElement[v17]->pCertContext->cbCertEncoded;
        if ( v20 < v16 )
          break;
        ++v17;
        v16 = v20;
        if ( v17 >= cElement )
          goto LABEL_16;
      }
    }
    else
    {
LABEL_16:
      v21 = 4LL * v17;
      if ( v21 <= 0xFFFFFFFF )
      {
        v22 = v21 + v16;
        if ( (unsigned int)v21 + v16 >= v16 )
        {
          v23 = LocalAlloc(0x40u, v22);
          v12 = ppChainContext;
          v24 = v23;
          if ( v23 )
          {
            v11 = 0;
            v25 = v23;
            if ( (*ppChainContext->rgpChain)->cElement )
            {
              do
              {
                v26 = v25 + 1;
                v27 = v5;
                *v25 = (*v12->rgpChain)->rgpElement[v5]->pCertContext->cbCertEncoded;
                v28 = (*ppChainContext->rgpChain)->rgpElement[v5]->pCertContext;
                memcpy_0(v25 + 1, v28->pbCertEncoded, v28->cbCertEncoded);
                v12 = ppChainContext;
                ++v5;
                v29 = *ppChainContext->rgpChain;
                v25 = (_DWORD *)((char *)v26 + v29->rgpElement[v27]->pCertContext->cbCertEncoded);
              }
              while ( v5 < v29->cElement );
            }
            *a3 = v24;
            *a2 = v22;
          }
          else
          {
            v11 = -2146893056;
          }
          goto LABEL_24;
        }
      }
    }
    v11 = -1073741675;
  }
  else
  {
    v11 = -2146893043;
  }
LABEL_24:
  v10 = 0;
LABEL_25:
  if ( v12 )
    CertFreeCertificateChain(v12);
  if ( v10 )
    LocalFree(v10);
  return v11;
}

```

## disassembly

```asm
0x1800032a0  mov     rax, rsp
0x1800032a3  mov     [rax+10h], rdx
0x1800032a7  push    rbp
0x1800032a8  push    rbx
0x1800032a9  push    rsi
0x1800032aa  push    rdi
0x1800032ab  push    r12
0x1800032ad  push    r13
0x1800032af  push    r14
0x1800032b1  push    r15
0x1800032b3  lea     rbp, [rax-57h]
0x1800032b7  sub     rsp, 0A8h
0x1800032be  xor     r12d, r12d
0x1800032c1  movaps  xmmword ptr [rax-58h], xmm6
0x1800032c5  xorps   xmm0, xmm0
0x1800032c8  mov     qword ptr [rbp+4Fh+var_90], r12
0x1800032cc  mov     rsi, r9
0x1800032cf  mov     [rbp+4Fh+ppChainContext], r12
0x1800032d3  mov     r13, r8
0x1800032d6  mov     [rbp+4Fh+pcbData], r12d
0x1800032da  lea     r14d, [r12+46h]
0x1800032df  xor     r8d, r8d; pvData
0x1800032e2  mov     edx, r14d; dwPropId
0x1800032e5  lea     r9, [rbp+4Fh+pcbData]; pcbData
0x1800032e9  mov     rdi, rcx
0x1800032ec  xorps   xmm6, xmm6
0x1800032ef  movups  xmmword ptr [rbp+4Fh+var_78.cbSize], xmm0
0x1800032f3  movups  xmmword ptr [rbp+4Fh+var_78.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x1800032f7  call    cs:__imp_CertGetCertificateContextProperty
0x1800032fd  lea     r15d, [r12+40h]
0x180003302  test    eax, eax
0x180003304  jz      short loc_180003358
0x180003306  mov     eax, [rbp+4Fh+pcbData]
0x180003309  test    eax, eax
0x18000330b  jz      short loc_180003358
0x18000330d  mov     edx, eax; uBytes
0x18000330f  mov     ecx, r15d; uFlags
0x180003312  call    cs:__imp_LocalAlloc
0x180003318  mov     rbx, rax
0x18000331b  test    rax, rax
0x18000331e  jnz     short loc_18000332E
0x180003320  mov     esi, 80090300h
0x180003325  mov     r8, [rbp+4Fh+ppChainContext]
0x180003329  jmp     loc_1800034D9
0x18000332e  lea     r9, [rbp+4Fh+pcbData]; pcbData
0x180003332  mov     r8, rbx; pvData
0x180003335  mov     edx, r14d; dwPropId
0x180003338  mov     rcx, rdi; pCertContext
0x18000333b  call    cs:__imp_CertGetCertificateContextProperty
0x180003341  test    eax, eax
0x180003343  jnz     short loc_18000334C
0x180003345  mov     esi, 8009030Dh
0x18000334a  jmp     short loc_180003325
0x18000334c  mov     eax, [rbp+4Fh+pcbData]
0x18000334f  mov     [rsi], eax
0x180003351  mov     rax, [rbp+4Fh+arg_20]
0x180003355  mov     [rax], rbx
0x180003358  mov     r9, [rdi+20h]; hAdditionalStore
0x18000335c  lea     rax, [rbp+4Fh+ppChainContext]
0x180003360  mov     [rsp+38h], rax; ppChainContext
0x180003365  xor     r8d, r8d; pTime
0x180003368  movups  xmmword ptr [rbp+4Fh+var_90+8], xmm6
0x18000336c  mov     [rsp+0E0h+pvReserved], r12; pvReserved
0x180003371  lea     rax, [rbp+4Fh+var_78]
0x180003375  movups  xmm0, xmmword ptr [rbp+4Fh+var_90+4]
0x180003379  mov     rdx, rdi; pCertContext
0x18000337c  mov     [rsp+0E0h+dwFlags], r12d; dwFlags
0x180003381  psrldq  xmm6, 0Ch
0x180003386  xor     ecx, ecx; hChainEngine
0x180003388  movups  xmmword ptr [rbp+4Fh+var_78.RequestedUsage+4], xmm0
0x18000338c  mov     [rsp+0E0h+pChainPara], rax; pChainPara
0x180003391  mov     [rbp+4Fh+var_78.cbSize], 20h ; ' '
0x180003398  mov     [rbp+4Fh+var_78.RequestedUsage.dwType], r12d
0x18000339c  movd    dword ptr [rbp+4Fh+var_78.RequestedUsage.Usage.rgpszUsageIdentifier+4], xmm6
0x1800033a1  call    cs:__imp_CertGetCertificateChain
0x1800033a7  mov     r8, [rbp+4Fh+ppChainContext]
0x1800033ab  test    eax, eax
0x1800033ad  jnz     short loc_1800033B9
0x1800033af  mov     esi, 8009030Dh
0x1800033b4  jmp     loc_1800034D6
0x1800033b9  cmp     [r8+0Ch], r12d
0x1800033bd  jz      short loc_1800033AF
0x1800033bf  mov     rax, [r8+10h]
0x1800033c3  mov     edx, r12d
0x1800033c6  mov     r9d, r12d
0x1800033c9  mov     rcx, [rax]
0x1800033cc  mov     r10d, [rcx+0Ch]
0x1800033d0  test    r10d, r10d
0x1800033d3  jz      short loc_1800033FB
0x1800033d5  mov     r11, [rcx+10h]
0x1800033d9  mov     eax, r9d
0x1800033dc  mov     rcx, [r11+rax*8]
0x1800033e0  mov     rax, [rcx+8]
0x1800033e4  mov     eax, [rax+10h]
0x1800033e7  add     eax, edx
0x1800033e9  cmp     eax, edx
0x1800033eb  jb      loc_1800034D1
0x1800033f1  inc     r9d
0x1800033f4  mov     edx, eax
0x1800033f6  cmp     r9d, r10d
0x1800033f9  jb      short loc_1800033D9
0x1800033fb  mov     eax, r9d
0x1800033fe  mov     r9d, 0FFFFFFFFh
0x180003404  shl     rax, 2
0x180003408  cmp     rax, r9
0x18000340b  ja      loc_1800034D1
0x180003411  lea     r14d, [rax+rdx]
0x180003415  cmp     r14d, edx
0x180003418  jb      loc_1800034D1
0x18000341e  mov     edx, r14d; uBytes
0x180003421  mov     ecx, r15d; uFlags
0x180003424  call    cs:__imp_LocalAlloc
0x18000342a  mov     r8, [rbp+4Fh+ppChainContext]
0x18000342e  mov     r15, rax
0x180003431  test    rax, rax
0x180003434  jnz     short loc_180003440
0x180003436  mov     esi, 80090300h
0x18000343b  jmp     loc_1800034D6
0x180003440  mov     rax, [r8+10h]
0x180003444  mov     esi, r12d
0x180003447  mov     r9, r15
0x18000344a  mov     rcx, [rax]
0x18000344d  cmp     [rcx+0Ch], r12d
0x180003451  jbe     short loc_1800034C1
0x180003453  mov     rax, [r8+10h]
0x180003457  lea     rbx, [r9+4]
0x18000345b  mov     edi, r12d
0x18000345e  mov     rcx, [rax]
0x180003461  mov     rax, [rcx+10h]
0x180003465  mov     rcx, [rax+rdi*8]
0x180003469  mov     rax, [rcx+8]
0x18000346d  mov     ecx, [rax+10h]
0x180003470  mov     [r9], ecx
0x180003473  mov     rax, [rbp+4Fh+ppChainContext]
0x180003477  mov     rcx, [rax+10h]
0x18000347b  mov     rax, [rcx]
0x18000347e  mov     rcx, [rax+10h]
0x180003482  mov     rax, [rcx+rdi*8]
0x180003486  mov     rcx, rbx; void *
0x180003489  mov     rdx, [rax+8]
0x18000348d  mov     r8d, [rdx+10h]; Size
0x180003491  mov     rdx, [rdx+8]; Src
0x180003495  call    memcpy_0
0x18000349a  mov     r8, [rbp+4Fh+ppChainContext]
0x18000349e  inc     r12d
0x1800034a1  mov     rax, [r8+10h]
0x1800034a5  mov     rdx, [rax]
0x1800034a8  mov     rax, [rdx+10h]
0x1800034ac  mov     rcx, [rax+rdi*8]
0x1800034b0  mov     rax, [rcx+8]
0x1800034b4  mov     r9d, [rax+10h]
0x1800034b8  add     r9, rbx
0x1800034bb  cmp     r12d, [rdx+0Ch]
0x1800034bf  jb      short loc_180003453
0x1800034c1  mov     rax, [rbp+4Fh+arg_8]
0x1800034c5  xor     r12d, r12d
0x1800034c8  mov     [r13+0], r15
0x1800034cc  mov     [rax], r14d
0x1800034cf  jmp     short loc_1800034D6
0x1800034d1  mov     esi, 0C0000095h
0x1800034d6  mov     rbx, r12
0x1800034d9  test    r8, r8
0x1800034dc  jz      short loc_1800034E7
0x1800034de  mov     rcx, r8; pChainContext
0x1800034e1  call    cs:__imp_CertFreeCertificateChain
0x1800034e7  test    rbx, rbx
0x1800034ea  jz      short loc_1800034F5
0x1800034ec  mov     rcx, rbx; hMem
0x1800034ef  call    cs:__imp_LocalFree
0x1800034f5  movaps  xmm6, [rsp+0E0h+var_58+8]
0x1800034fd  mov     eax, esi
0x1800034ff  add     rsp, 0A8h
0x180003506  pop     r15
0x180003508  pop     r14
0x18000350a  pop     r13
0x18000350c  pop     r12
0x18000350e  pop     rdi
0x18000350f  pop     rsi
0x180003510  pop     rbx
0x180003511  pop     rbp
0x180003512  retn
```
