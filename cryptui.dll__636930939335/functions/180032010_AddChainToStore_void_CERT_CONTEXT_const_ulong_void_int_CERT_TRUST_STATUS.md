# AddChainToStore(void *,_CERT_CONTEXT const *,ulong,void * *,int,_CERT_TRUST_STATUS *)

- ea: `0x180032010`
- end: `0x1800321c6`
- name: `?AddChainToStore@@YAHPEAXPEBU_CERT_CONTEXT@@KPEAPEAXHPEAU_CERT_TRUST_STATUS@@@Z`
- size: `438`
- prototype: `__int64 __usercall@<rax>(HCERTSTORE hCertStore@<rcx>, PCCERT_CONTEXT pCertContext@<rdx>, unsigned int@<r8d>, void **@<r9>, int, struct _CERT_TRUST_STATUS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180020f6c`

## callees

- `0x180032010`
- `0x18003e582`

## import_xrefs

- `CRYPT32!CertAddCertificateContextToStore` at `0x180032138`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180032138`
- `CRYPT32!CertGetCertificateChain` at `0x1800320ce`
- `CRYPT32!CertGetCertificateChain` at `0x1800320ce`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1800321a6`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1800321a6`
- `CRYPT32!CertFreeCertificateChain` at `0x180032197`
- `CRYPT32!CertFreeCertificateChain` at `0x180032197`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180032151`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180032151`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18003207e`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18003207e`
- `CRYPT32!CertFreeCertificateContext` at `0x18003215b`
- `CRYPT32!CertFreeCertificateContext` at `0x18003215b`

## pseudocode

```c
__int64 __fastcall AddChainToStore(
        HCERTSTORE hCertStore,
        PCCERT_CONTEXT pCertContext,
        DWORD a3,
        void **a4,
        int a5,
        struct _CERT_TRUST_STATUS *a6)
{
  PCCERT_CHAIN_CONTEXT v10; // rdx
  __int64 v11; // rbx
  unsigned int v12; // edi
  struct _CERT_TRUST_STATUS *v13; // rcx
  PCCERT_CONTEXT ppStoreContext; // [rsp+40h] [rbp-59h] BYREF
  HCERTCHAINENGINE phChainEngine; // [rsp+48h] [rbp-51h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+50h] [rbp-49h] BYREF
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+70h] [rbp-29h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+108h] [rbp+6Fh] BYREF

  phChainEngine = 0;
  pChainContext = 0;
  ppStoreContext = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  memset_0(&pConfig, 0, 0x58u);
  pConfig.cbSize = 88;
  pConfig.cAdditionalStore = a3;
  pConfig.rghAdditionalStore = a4;
  if ( !CertCreateCertificateChainEngine(&pConfig, &phChainEngine)
    || (memset(&pChainPara, 0, sizeof(pChainPara)),
        pChainPara.cbSize = 32,
        !CertGetCertificateChain(phChainEngine, pCertContext, 0, 0, &pChainPara, 0, 0, &pChainContext)) )
  {
    v10 = pChainContext;
    goto LABEL_14;
  }
  v10 = pChainContext;
  if ( !pChainContext->cChain )
  {
LABEL_14:
    v12 = 0;
    goto LABEL_15;
  }
  v11 = 0;
  v12 = 1;
  if ( (*pChainContext->rgpChain)->cElement )
  {
    do
    {
      if ( !a5 || ((*v10->rgpChain)->rgpElement[v11]->TrustStatus.dwInfoStatus & 8) == 0 )
      {
        CertAddCertificateContextToStore(
          hCertStore,
          (*v10->rgpChain)->rgpElement[v11]->pCertContext,
          3u,
          &ppStoreContext);
        if ( ppStoreContext )
        {
          CertSetCertificateContextProperty(ppStoreContext, 2u, 0, 0);
          CertFreeCertificateContext(ppStoreContext);
        }
        v10 = pChainContext;
      }
      v11 = (unsigned int)(v11 + 1);
    }
    while ( (unsigned int)v11 < (*v10->rgpChain)->cElement );
  }
  v13 = a6;
  if ( a6 )
  {
    a6->dwErrorStatus = v10->TrustStatus.dwErrorStatus;
    v13->dwInfoStatus = v10->TrustStatus.dwInfoStatus;
  }
LABEL_15:
  if ( v10 )
    CertFreeCertificateChain(v10);
  if ( phChainEngine )
    CertFreeCertificateChainEngine(phChainEngine);
  return v12;
}

```

## disassembly

```asm
0x180032010  mov     [rsp-8+arg_0], rbx
0x180032015  mov     [rsp-8+arg_8], rsi
0x18003201a  push    rbp
0x18003201b  push    rdi
0x18003201c  push    r14
0x18003201e  lea     rbp, [rsp-37h]
0x180032023  sub     rsp, 0D0h
0x18003202a  xorps   xmm0, xmm0
0x18003202d  mov     [rbp+47h+phChainEngine], 0
0x180032035  mov     rsi, rdx
0x180032038  mov     [rbp+47h+pChainContext], 0
0x180032040  xor     edx, edx; Val
0x180032042  mov     [rbp+47h+ppStoreContext], 0
0x18003204a  mov     ebx, r8d
0x18003204d  mov     r14, rcx
0x180032050  lea     rcx, [rbp+47h+pConfig]; void *
0x180032054  mov     rdi, r9
0x180032057  movups  xmmword ptr [rbp+47h+var_90.cbSize], xmm0
0x18003205b  lea     r8d, [rdx+58h]; Size
0x18003205f  movups  xmmword ptr [rbp+47h+var_90.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180032063  call    memset_0
0x180032068  lea     rdx, [rbp+47h+phChainEngine]; phChainEngine
0x18003206c  mov     [rbp+47h+pConfig.cbSize], 58h ; 'X'
0x180032073  lea     rcx, [rbp+47h+pConfig]; pConfig
0x180032077  mov     [rbp+47h+pConfig.cAdditionalStore], ebx
0x18003207a  mov     [rbp+47h+pConfig.rghAdditionalStore], rdi
0x18003207e  call    cs:__imp_CertCreateCertificateChainEngine
0x180032084  test    eax, eax
0x180032086  jz      loc_180032189
0x18003208c  mov     rcx, [rbp+47h+phChainEngine]; hChainEngine
0x180032090  lea     rax, [rbp+47h+pChainContext]
0x180032094  mov     [rsp+0E0h+ppChainContext], rax; ppChainContext
0x180032099  xorps   xmm0, xmm0
0x18003209c  mov     [rsp+0E0h+pvReserved], 0; pvReserved
0x1800320a5  lea     rax, [rbp+47h+var_90]
0x1800320a9  movups  xmmword ptr [rbp+47h+var_90.cbSize], xmm0
0x1800320ad  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x1800320b5  xor     r9d, r9d; hAdditionalStore
0x1800320b8  xor     r8d, r8d; pTime
0x1800320bb  mov     [rsp+0E0h+pChainPara], rax; pChainPara
0x1800320c0  mov     rdx, rsi; pCertContext
0x1800320c3  mov     [rbp+47h+var_90.cbSize], 20h ; ' '
0x1800320ca  movups  xmmword ptr [rbp+47h+var_90.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x1800320ce  call    cs:__imp_CertGetCertificateChain
0x1800320d4  test    eax, eax
0x1800320d6  jz      loc_180032189
0x1800320dc  mov     rdx, [rbp+47h+pChainContext]
0x1800320e0  cmp     dword ptr [rdx+0Ch], 0
0x1800320e4  jz      loc_18003218D
0x1800320ea  mov     rax, [rdx+10h]
0x1800320ee  xor     ebx, ebx
0x1800320f0  mov     edi, 1
0x1800320f5  mov     rcx, [rax]
0x1800320f8  cmp     [rcx+0Ch], ebx
0x1800320fb  jbe     short loc_180032173
0x1800320fd  cmp     [rbp+47h+arg_20], 0
0x180032101  jz      short loc_180032118
0x180032103  mov     rax, [rdx+10h]
0x180032107  mov     rcx, [rax]
0x18003210a  mov     rax, [rcx+10h]
0x18003210e  mov     rcx, [rax+rbx*8]
0x180032112  test    byte ptr [rcx+14h], 8
0x180032116  jnz     short loc_180032165
0x180032118  mov     rax, [rdx+10h]
0x18003211c  lea     r9, [rbp+47h+ppStoreContext]; ppStoreContext
0x180032120  mov     r8d, 3; dwAddDisposition
0x180032126  mov     rcx, [rax]
0x180032129  mov     rax, [rcx+10h]
0x18003212d  mov     rcx, r14; hCertStore
0x180032130  mov     rdx, [rax+rbx*8]
0x180032134  mov     rdx, [rdx+8]; pCertContext
0x180032138  call    cs:__imp_CertAddCertificateContextToStore
0x18003213e  mov     rcx, [rbp+47h+ppStoreContext]; pCertContext
0x180032142  test    rcx, rcx
0x180032145  jz      short loc_180032161
0x180032147  xor     r9d, r9d; pvData
0x18003214a  xor     r8d, r8d; dwFlags
0x18003214d  lea     edx, [r9+2]; dwPropId
0x180032151  call    cs:__imp_CertSetCertificateContextProperty
0x180032157  mov     rcx, [rbp+47h+ppStoreContext]; pCertContext
0x18003215b  call    cs:__imp_CertFreeCertificateContext
0x180032161  mov     rdx, [rbp+47h+pChainContext]
0x180032165  mov     rax, [rdx+10h]
0x180032169  add     ebx, edi
0x18003216b  mov     rcx, [rax]
0x18003216e  cmp     ebx, [rcx+0Ch]
0x180032171  jb      short loc_1800320FD
0x180032173  mov     rcx, [rbp+47h+arg_28]
0x180032177  test    rcx, rcx
0x18003217a  jz      short loc_18003218F
0x18003217c  mov     eax, [rdx+4]
0x18003217f  mov     [rcx], eax
0x180032181  mov     eax, [rdx+8]
0x180032184  mov     [rcx+4], eax
0x180032187  jmp     short loc_18003218F
0x180032189  mov     rdx, [rbp+47h+pChainContext]
0x18003218d  xor     edi, edi
0x18003218f  test    rdx, rdx
0x180032192  jz      short loc_18003219D
0x180032194  mov     rcx, rdx; pChainContext
0x180032197  call    cs:__imp_CertFreeCertificateChain
0x18003219d  mov     rcx, [rbp+47h+phChainEngine]; hChainEngine
0x1800321a1  test    rcx, rcx
0x1800321a4  jz      short loc_1800321AC
0x1800321a6  call    cs:__imp_CertFreeCertificateChainEngine
0x1800321ac  lea     r11, [rsp+0E0h+var_10]
0x1800321b4  mov     eax, edi
0x1800321b6  mov     rbx, [r11+20h]
0x1800321ba  mov     rsi, [r11+28h]
0x1800321be  mov     rsp, r11
0x1800321c1  pop     r14
0x1800321c3  pop     rdi
0x1800321c4  pop     rbp
0x1800321c5  retn
```
