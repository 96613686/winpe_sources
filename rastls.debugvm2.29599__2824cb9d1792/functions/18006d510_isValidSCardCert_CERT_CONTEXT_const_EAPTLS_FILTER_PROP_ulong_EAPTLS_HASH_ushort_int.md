# isValidSCardCert(_CERT_CONTEXT const *,_EAPTLS_FILTER_PROP *,ulong,_EAPTLS_HASH *,ushort * *,int *)

- ea: `0x18006d510`
- end: `0x18006d7dc`
- name: `?isValidSCardCert@@YAKPEBU_CERT_CONTEXT@@PEAU_EAPTLS_FILTER_PROP@@KPEAU_EAPTLS_HASH@@PEAPEAGPEAH@Z`
- size: `716`
- prototype: `unsigned int __usercall@<eax>(PCCERT_CONTEXT pCertContext@<rcx>, struct _EAPTLS_FILTER_PROP *@<rdx>, unsigned int@<r8d>, struct _EAPTLS_HASH *@<r9>, unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180072e48`
- `0x180073538`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18001fd50`
- `0x18002c710`
- `0x18002d488`
- `0x180036930`
- `0x1800690c4`
- `0x180069408`
- `0x180069510`
- `0x18006d510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d606`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d7ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d7ad`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18006d5fc`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18006d5fc`
- `CRYPT32!CertGetCertificateChain` at `0x18006d701`
- `CRYPT32!CertGetCertificateChain` at `0x18006d701`
- `CRYPT32!CertFreeCertificateChain` at `0x18006d7bc`
- `CRYPT32!CertFreeCertificateChain` at `0x18006d7bc`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigCacheOnlyCertValidation` at `0x18006d67c`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigCacheOnlyCertValidation` at `0x18006d67c`

## pseudocode

```c
__int64 __fastcall isValidSCardCert(
        PCCERT_CONTEXT pCertContext,
        struct _EAPTLS_FILTER_PROP *a2,
        int a3,
        DWORD *a4,
        unsigned __int16 **a5,
        int *a6)
{
  struct _CTL_USAGE *v6; // r15
  int v7; // edi
  unsigned int v10; // ebx
  BOOL v11; // r9d
  int EKUUsage; // eax
  DWORD *v13; // r9
  DWORD *v14; // r8
  DWORD LastError; // eax
  DWORD dwFlags; // r14d
  struct _EAPTLS_FILTER_PROP *v17; // r12
  HCERTSTORE hCertStore; // r9
  unsigned int v19; // eax
  unsigned int v20; // eax
  struct _EAPTLS_CONTROL_BLOCK *v21; // rcx
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+40h] [rbp-30h] BYREF
  struct _CTL_USAGE *v24; // [rsp+48h] [rbp-28h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+50h] [rbp-20h] BYREF
  struct _EAPTLS_FILTER_PROP *v26; // [rsp+B8h] [rbp+48h] BYREF
  DWORD *pcbData; // [rsp+C8h] [rbp+58h]

  pcbData = a4;
  v26 = a2;
  v6 = 0;
  v7 = 0;
  v24 = 0;
  pChainContext = 0;
  if ( a2 )
    v7 = *(_WORD *)a2 & 0x10;
  *a6 = 0;
  if ( !(unsigned int)FCheckTimeValidity(pCertContext) )
  {
    v10 = -2146762495;
    goto LABEL_39;
  }
  v11 = (a3 & 0x10000) != 0 || (a3 & 0x4000) != 0;
  EKUUsage = DwGetEKUUsage(pCertContext, &v24, 0, v11, v7);
  v6 = v24;
  v10 = EKUUsage;
  if ( !EKUUsage )
  {
    if ( !v7 )
    {
      if ( (a3 & 0x10000) != 0 || (a3 & 0x4000) != 0 )
        EKUUsage = 1;
      if ( !(unsigned int)FCheckUsage(pCertContext, v24, 0, 0, EKUUsage) )
      {
        v10 = -2146762480;
        goto LABEL_39;
      }
    }
    v13 = pcbData;
    v14 = pcbData + 1;
    *pcbData = 20;
    if ( !CertGetCertificateContextProperty(pCertContext, 3u, v14, v13) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, LastError);
      goto LABEL_39;
    }
    if ( !(unsigned int)FCertToStr(pCertContext, 0) )
    {
      v10 = -2147467259;
      goto LABEL_39;
    }
    if ( (unsigned __int8)IsRasTlsExt_GetPinUserBlobPresent() )
    {
      dwFlags = (unsigned int)RasTlsExt_GetConfigCacheOnlyCertValidation() != 0 ? 0x80000004 : 0;
    }
    else
    {
      dwFlags = 0;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
    }
    v17 = v26;
    if ( !v26 )
      goto LABEL_38;
    hCertStore = pCertContext->hCertStore;
    memset(&pChainPara, 0, sizeof(pChainPara));
    LODWORD(v26) = 0;
    pChainPara.cbSize = 32;
    if ( !CertGetCertificateChain(0, pCertContext, 0, hCertStore, &pChainPara, dwFlags, 0, &pChainContext) )
    {
      v19 = EapTlsGetLastError();
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v19);
      pChainContext = 0;
      goto LABEL_39;
    }
    v20 = CheckFilterAllowsCert(pChainContext, v17, (int *)&v26);
    if ( !v20 )
    {
      if ( !(_DWORD)v26 )
      {
        v21 = WPP_GLOBAL_Control;
LABEL_36:
        if ( v21 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)v21 + 2), 82, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
        goto LABEL_39;
      }
LABEL_38:
      *a6 = 1;
      goto LABEL_39;
    }
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v20);
      v21 = WPP_GLOBAL_Control;
    }
    if ( !(_DWORD)v26 )
      goto LABEL_36;
  }
LABEL_39:
  LocalFree(v6);
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  return v10;
}

```

## disassembly

```asm
0x18006d510  mov     [rsp-38h+arg_0], rbx
0x18006d515  mov     [rsp-38h+pcbData], r9
0x18006d51a  mov     [rsp-38h+arg_8], rdx
0x18006d51f  push    rbp
0x18006d520  push    rsi
0x18006d521  push    rdi
0x18006d522  push    r12
0x18006d524  push    r13
0x18006d526  push    r14
0x18006d528  push    r15
0x18006d52a  mov     rbp, rsp
0x18006d52d  sub     rsp, 70h
0x18006d531  xor     r15d, r15d
0x18006d534  xor     edi, edi
0x18006d536  mov     [rbp+var_28], r15
0x18006d53a  mov     r12d, r8d
0x18006d53d  mov     [rbp+pChainContext], rdi
0x18006d541  mov     r13, rcx
0x18006d544  test    rdx, rdx
0x18006d547  jz      short loc_18006D54F
0x18006d549  movzx   edi, word ptr [rdx]
0x18006d54c  and     edi, 10h
0x18006d54f  mov     rax, [rbp+arg_28]
0x18006d553  mov     [rax], r15d
0x18006d556  call    ?FCheckTimeValidity@@YAHPEBU_CERT_CONTEXT@@@Z; FCheckTimeValidity(_CERT_CONTEXT const *)
0x18006d55b  test    eax, eax
0x18006d55d  jnz     short loc_18006D569
0x18006d55f  mov     ebx, 800B0101h
0x18006d564  jmp     loc_18006D7AA
0x18006d569  mov     esi, r12d
0x18006d56c  mov     r14d, r12d
0x18006d56f  and     esi, 4000h
0x18006d575  and     r14d, 10000h
0x18006d57c  jnz     short loc_18006D587
0x18006d57e  test    esi, esi
0x18006d580  jnz     short loc_18006D587
0x18006d582  xor     r9d, r9d
0x18006d585  jmp     short loc_18006D58D
0x18006d587  mov     r9d, 1; int
0x18006d58d  xor     r8d, r8d; int
0x18006d590  mov     dword ptr [rsp+70h+pChainPara], edi; int
0x18006d594  lea     rdx, [rbp+var_28]; struct _CTL_USAGE **
0x18006d598  mov     rcx, r13; pCertContext
0x18006d59b  call    ?DwGetEKUUsage@@YAKPEBU_CERT_CONTEXT@@PEAPEAU_CTL_USAGE@@HHH@Z; DwGetEKUUsage(_CERT_CONTEXT const *,_CTL_USAGE * *,int,int,int)
0x18006d5a0  mov     r15, [rbp+var_28]
0x18006d5a4  mov     ebx, eax
0x18006d5a6  test    eax, eax
0x18006d5a8  jnz     loc_18006D7AA
0x18006d5ae  test    edi, edi
0x18006d5b0  jnz     short loc_18006D5E3
0x18006d5b2  test    r14d, r14d
0x18006d5b5  jnz     short loc_18006D5BB
0x18006d5b7  test    esi, esi
0x18006d5b9  jz      short loc_18006D5C0
0x18006d5bb  mov     eax, 1
0x18006d5c0  xor     r9d, r9d; int
0x18006d5c3  mov     dword ptr [rsp+70h+pChainPara], eax; int
0x18006d5c7  xor     r8d, r8d; int
0x18006d5ca  mov     rdx, r15; struct _CTL_USAGE *
0x18006d5cd  mov     rcx, r13; pCertContext
0x18006d5d0  call    ?FCheckUsage@@YAHPEBU_CERT_CONTEXT@@PEAU_CTL_USAGE@@HHH@Z; FCheckUsage(_CERT_CONTEXT const *,_CTL_USAGE *,int,int,int)
0x18006d5d5  test    eax, eax
0x18006d5d7  jnz     short loc_18006D5E3
0x18006d5d9  mov     ebx, 800B0110h
0x18006d5de  jmp     loc_18006D7AA
0x18006d5e3  mov     rax, [rbp+pcbData]
0x18006d5e7  mov     edx, 3; dwPropId
0x18006d5ec  mov     r9, rax; pcbData
0x18006d5ef  mov     rcx, r13; pCertContext
0x18006d5f2  lea     r8, [rax+4]; pvData
0x18006d5f6  mov     dword ptr [rax], 14h
0x18006d5fc  call    cs:__imp_CertGetCertificateContextProperty
0x18006d602  test    eax, eax
0x18006d604  jnz     short loc_18006D642
0x18006d606  call    cs:__imp_GetLastError
0x18006d60c  mov     ebx, eax
0x18006d60e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d615  lea     rdi, WPP_GLOBAL_Control
0x18006d61c  cmp     rcx, rdi
0x18006d61f  jz      loc_18006D7AA
0x18006d625  mov     rcx, [rcx+10h]
0x18006d629  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006d630  mov     edx, 4Eh ; 'N'
0x18006d635  mov     r9d, eax
0x18006d638  call    WPP_SF_d
0x18006d63d  jmp     loc_18006D7AA
0x18006d642  mov     r9, [rbp+arg_20]
0x18006d646  and     r12d, 1
0x18006d64a  mov     r8d, r12d
0x18006d64d  xor     edx, edx; dwFlags
0x18006d64f  mov     rcx, r13; pCertContext
0x18006d652  call    FCertToStr
0x18006d657  test    eax, eax
0x18006d659  jnz     short loc_18006D665
0x18006d65b  mov     ebx, 80004005h
0x18006d660  jmp     loc_18006D7AA
0x18006d665  call    IsRasTlsExt_GetPinUserBlobPresent
0x18006d66a  lea     rsi, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006d671  lea     rdi, WPP_GLOBAL_Control
0x18006d678  test    al, al
0x18006d67a  jz      short loc_18006D690
0x18006d67c  call    cs:__imp_RasTlsExt_GetConfigCacheOnlyCertValidation
0x18006d682  neg     eax
0x18006d684  sbb     r14d, r14d
0x18006d687  and     r14d, 80000004h
0x18006d68e  jmp     short loc_18006D6AF
0x18006d690  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d697  xor     r14d, r14d
0x18006d69a  cmp     rcx, rdi
0x18006d69d  jz      short loc_18006D6AF
0x18006d69f  mov     rcx, [rcx+10h]
0x18006d6a3  lea     edx, [r14+4Fh]
0x18006d6a7  mov     r8, rsi
0x18006d6aa  call    WPP_SF_
0x18006d6af  mov     r12, [rbp+arg_8]
0x18006d6b3  test    r12, r12
0x18006d6b6  jz      loc_18006D7A0
0x18006d6bc  mov     r9, [r13+20h]; hAdditionalStore
0x18006d6c0  lea     rax, [rbp+pChainContext]
0x18006d6c4  mov     [rsp+70h+ppChainContext], rax; ppChainContext
0x18006d6c9  xorps   xmm0, xmm0
0x18006d6cc  mov     [rsp+70h+pvReserved], 0; pvReserved
0x18006d6d5  lea     rax, [rbp+var_20]
0x18006d6d9  movups  xmmword ptr [rbp+var_20.cbSize], xmm0
0x18006d6dd  mov     [rsp+70h+dwFlags], r14d; dwFlags
0x18006d6e2  xor     r8d, r8d; pTime
0x18006d6e5  mov     rdx, r13; pCertContext
0x18006d6e8  mov     [rsp+70h+pChainPara], rax; pChainPara
0x18006d6ed  xor     ecx, ecx; hChainEngine
0x18006d6ef  mov     dword ptr [rbp+arg_8], 0
0x18006d6f6  movups  xmmword ptr [rbp+var_20.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x18006d6fa  mov     [rbp+var_20.cbSize], 20h ; ' '
0x18006d701  call    cs:__imp_CertGetCertificateChain
0x18006d707  xor     r13d, r13d
0x18006d70a  test    eax, eax
0x18006d70c  jnz     short loc_18006D738
0x18006d70e  call    ?EapTlsGetLastError@@YAKXZ; EapTlsGetLastError(void)
0x18006d713  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d71a  cmp     rcx, rdi
0x18006d71d  jz      short loc_18006D732
0x18006d71f  mov     rcx, [rcx+10h]
0x18006d723  lea     edx, [r13+50h]
0x18006d727  mov     r9d, eax
0x18006d72a  mov     r8, rsi
0x18006d72d  call    WPP_SF_d
0x18006d732  mov     [rbp+pChainContext], r13
0x18006d736  jmp     short loc_18006D7AA
0x18006d738  mov     rcx, [rbp+pChainContext]; struct _CERT_CHAIN_CONTEXT *
0x18006d73c  lea     r8, [rbp+arg_8]; int *
0x18006d740  mov     rdx, r12; struct _EAPTLS_FILTER_PROP *
0x18006d743  call    ?CheckFilterAllowsCert@@YAKPEBU_CERT_CHAIN_CONTEXT@@PEAU_EAPTLS_FILTER_PROP@@PEAH@Z; CheckFilterAllowsCert(_CERT_CHAIN_CONTEXT const *,_EAPTLS_FILTER_PROP *,int *)
0x18006d748  test    eax, eax
0x18006d74a  jnz     short loc_18006D75B
0x18006d74c  cmp     dword ptr [rbp+arg_8], r13d
0x18006d750  jnz     short loc_18006D7A0
0x18006d752  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d759  jmp     short loc_18006D788
0x18006d75b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d762  cmp     rcx, rdi
0x18006d765  jz      short loc_18006D782
0x18006d767  mov     rcx, [rcx+10h]
0x18006d76b  mov     edx, 51h ; 'Q'
0x18006d770  mov     r9d, eax
0x18006d773  mov     r8, rsi
0x18006d776  call    WPP_SF_d
0x18006d77b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d782  cmp     dword ptr [rbp+arg_8], r13d
0x18006d786  jnz     short loc_18006D7AA
0x18006d788  cmp     rcx, rdi
0x18006d78b  jz      short loc_18006D7AA
0x18006d78d  mov     rcx, [rcx+10h]
0x18006d791  mov     edx, 52h ; 'R'
0x18006d796  mov     r8, rsi
0x18006d799  call    WPP_SF_
0x18006d79e  jmp     short loc_18006D7AA
0x18006d7a0  mov     rax, [rbp+arg_28]
0x18006d7a4  mov     dword ptr [rax], 1
0x18006d7aa  mov     rcx, r15; hMem
0x18006d7ad  call    cs:__imp_LocalFree
0x18006d7b3  mov     rcx, [rbp+pChainContext]; pChainContext
0x18006d7b7  test    rcx, rcx
0x18006d7ba  jz      short loc_18006D7C2
0x18006d7bc  call    cs:__imp_CertFreeCertificateChain
0x18006d7c2  mov     eax, ebx
0x18006d7c4  mov     rbx, [rsp+70h+arg_0]
0x18006d7cc  add     rsp, 70h
0x18006d7d0  pop     r15
0x18006d7d2  pop     r14
0x18006d7d4  pop     r13
0x18006d7d6  pop     r12
0x18006d7d8  pop     rdi
0x18006d7d9  pop     rsi
0x18006d7da  pop     rbp
0x18006d7db  retn
```
