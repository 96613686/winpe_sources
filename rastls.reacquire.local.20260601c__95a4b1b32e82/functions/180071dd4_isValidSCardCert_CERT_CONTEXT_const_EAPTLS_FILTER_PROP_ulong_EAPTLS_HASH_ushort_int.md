# isValidSCardCert(_CERT_CONTEXT const *,_EAPTLS_FILTER_PROP *,ulong,_EAPTLS_HASH *,ushort * *,int *)

- ea: `0x180071dd4`
- end: `0x1800720c5`
- name: `?isValidSCardCert@@YAKPEBU_CERT_CONTEXT@@PEAU_EAPTLS_FILTER_PROP@@KPEAU_EAPTLS_HASH@@PEAPEAGPEAH@Z`
- size: `753`
- prototype: `unsigned int __usercall@<eax>(PCCERT_CONTEXT pCertContext@<rcx>, struct _EAPTLS_FILTER_PROP *@<rdx>, unsigned int@<r8d>, struct _EAPTLS_HASH *@<r9>, unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180077eb8`
- `0x18007865c`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180021afc`
- `0x18002e900`
- `0x18002fc18`
- `0x180039540`
- `0x18006d374`
- `0x18006d744`
- `0x18006d864`
- `0x180071dd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071ed0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072089`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072089`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180071ec0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180071ec0`
- `CRYPT32!CertGetCertificateChain` at `0x180071fd7`
- `CRYPT32!CertGetCertificateChain` at `0x180071fd7`
- `CRYPT32!CertFreeCertificateChain` at `0x18007209e`
- `CRYPT32!CertFreeCertificateChain` at `0x18007209e`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigCacheOnlyCertValidation` at `0x180071f4c`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigCacheOnlyCertValidation` at `0x180071f4c`

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
    if ( !(unsigned int)FCertToStr(pCertContext, 0, a3 & 1, a5) )
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
0x180071dd4  mov     [rsp-38h+arg_0], rbx
0x180071dd9  mov     [rsp-38h+pcbData], r9
0x180071dde  mov     [rsp-38h+arg_8], rdx
0x180071de3  push    rbp
0x180071de4  push    rsi
0x180071de5  push    rdi
0x180071de6  push    r12
0x180071de8  push    r13
0x180071dea  push    r14
0x180071dec  push    r15
0x180071dee  mov     rbp, rsp
0x180071df1  sub     rsp, 70h
0x180071df5  xor     r15d, r15d
0x180071df8  xor     edi, edi
0x180071dfa  mov     [rbp+var_28], r15
0x180071dfe  mov     r12d, r8d
0x180071e01  mov     [rbp+pChainContext], rdi
0x180071e05  mov     r13, rcx
0x180071e08  test    rdx, rdx
0x180071e0b  jz      short loc_180071E13
0x180071e0d  movzx   edi, word ptr [rdx]
0x180071e10  and     edi, 10h
0x180071e13  mov     rax, [rbp+arg_28]
0x180071e17  mov     [rax], r15d
0x180071e1a  call    ?FCheckTimeValidity@@YAHPEBU_CERT_CONTEXT@@@Z; FCheckTimeValidity(_CERT_CONTEXT const *)
0x180071e1f  test    eax, eax
0x180071e21  jnz     short loc_180071E2D
0x180071e23  mov     ebx, 800B0101h
0x180071e28  jmp     loc_180072086
0x180071e2d  mov     esi, r12d
0x180071e30  mov     r14d, r12d
0x180071e33  and     esi, 4000h
0x180071e39  and     r14d, 10000h
0x180071e40  jnz     short loc_180071E4B
0x180071e42  test    esi, esi
0x180071e44  jnz     short loc_180071E4B
0x180071e46  xor     r9d, r9d
0x180071e49  jmp     short loc_180071E51
0x180071e4b  mov     r9d, 1; int
0x180071e51  xor     r8d, r8d; int
0x180071e54  mov     dword ptr [rsp+70h+pChainPara], edi; int
0x180071e58  lea     rdx, [rbp+var_28]; struct _CTL_USAGE **
0x180071e5c  mov     rcx, r13; pCertContext
0x180071e5f  call    ?DwGetEKUUsage@@YAKPEBU_CERT_CONTEXT@@PEAPEAU_CTL_USAGE@@HHH@Z; DwGetEKUUsage(_CERT_CONTEXT const *,_CTL_USAGE * *,int,int,int)
0x180071e64  mov     r15, [rbp+var_28]
0x180071e68  mov     ebx, eax
0x180071e6a  test    eax, eax
0x180071e6c  jnz     loc_180072086
0x180071e72  test    edi, edi
0x180071e74  jnz     short loc_180071EA7
0x180071e76  test    r14d, r14d
0x180071e79  jnz     short loc_180071E7F
0x180071e7b  test    esi, esi
0x180071e7d  jz      short loc_180071E84
0x180071e7f  mov     eax, 1
0x180071e84  xor     r9d, r9d; int
0x180071e87  mov     dword ptr [rsp+70h+pChainPara], eax; int
0x180071e8b  xor     r8d, r8d; int
0x180071e8e  mov     rdx, r15; struct _CTL_USAGE *
0x180071e91  mov     rcx, r13; pCertContext
0x180071e94  call    ?FCheckUsage@@YAHPEBU_CERT_CONTEXT@@PEAU_CTL_USAGE@@HHH@Z; FCheckUsage(_CERT_CONTEXT const *,_CTL_USAGE *,int,int,int)
0x180071e99  test    eax, eax
0x180071e9b  jnz     short loc_180071EA7
0x180071e9d  mov     ebx, 800B0110h
0x180071ea2  jmp     loc_180072086
0x180071ea7  mov     rax, [rbp+pcbData]
0x180071eab  mov     edx, 3; dwPropId
0x180071eb0  mov     r9, rax; pcbData
0x180071eb3  mov     rcx, r13; pCertContext
0x180071eb6  lea     r8, [rax+4]; pvData
0x180071eba  mov     dword ptr [rax], 14h
0x180071ec0  call    cs:__imp_CertGetCertificateContextProperty
0x180071ec7  nop     dword ptr [rax+rax+00h]
0x180071ecc  test    eax, eax
0x180071ece  jnz     short loc_180071F12
0x180071ed0  call    cs:__imp_GetLastError
0x180071ed7  nop     dword ptr [rax+rax+00h]
0x180071edc  mov     ebx, eax
0x180071ede  mov     rcx, cs:WPP_GLOBAL_Control
0x180071ee5  lea     rdi, WPP_GLOBAL_Control
0x180071eec  cmp     rcx, rdi
0x180071eef  jz      loc_180072086
0x180071ef5  mov     rcx, [rcx+10h]
0x180071ef9  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180071f00  mov     edx, 4Eh ; 'N'
0x180071f05  mov     r9d, eax
0x180071f08  call    WPP_SF_d
0x180071f0d  jmp     loc_180072086
0x180071f12  mov     r9, [rbp+arg_20]
0x180071f16  and     r12d, 1
0x180071f1a  mov     r8d, r12d
0x180071f1d  xor     edx, edx; dwFlags
0x180071f1f  mov     rcx, r13; pCertContext
0x180071f22  call    FCertToStr
0x180071f27  test    eax, eax
0x180071f29  jnz     short loc_180071F35
0x180071f2b  mov     ebx, 80004005h
0x180071f30  jmp     loc_180072086
0x180071f35  call    IsRasTlsExt_GetPinUserBlobPresent
0x180071f3a  lea     rsi, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180071f41  lea     rdi, WPP_GLOBAL_Control
0x180071f48  test    al, al
0x180071f4a  jz      short loc_180071F66
0x180071f4c  call    cs:__imp_RasTlsExt_GetConfigCacheOnlyCertValidation
0x180071f53  nop     dword ptr [rax+rax+00h]
0x180071f58  neg     eax
0x180071f5a  sbb     r14d, r14d
0x180071f5d  and     r14d, 80000004h
0x180071f64  jmp     short loc_180071F85
0x180071f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180071f6d  xor     r14d, r14d
0x180071f70  cmp     rcx, rdi
0x180071f73  jz      short loc_180071F85
0x180071f75  mov     rcx, [rcx+10h]
0x180071f79  lea     edx, [r14+4Fh]
0x180071f7d  mov     r8, rsi
0x180071f80  call    WPP_SF_
0x180071f85  mov     r12, [rbp+arg_8]
0x180071f89  test    r12, r12
0x180071f8c  jz      loc_18007207C
0x180071f92  mov     r9, [r13+20h]; hAdditionalStore
0x180071f96  lea     rax, [rbp+pChainContext]
0x180071f9a  mov     [rsp+70h+ppChainContext], rax; ppChainContext
0x180071f9f  xorps   xmm0, xmm0
0x180071fa2  mov     [rsp+70h+pvReserved], 0; pvReserved
0x180071fab  lea     rax, [rbp+var_20]
0x180071faf  movups  xmmword ptr [rbp+var_20.cbSize], xmm0
0x180071fb3  mov     [rsp+70h+dwFlags], r14d; dwFlags
0x180071fb8  xor     r8d, r8d; pTime
0x180071fbb  mov     rdx, r13; pCertContext
0x180071fbe  mov     [rsp+70h+pChainPara], rax; pChainPara
0x180071fc3  xor     ecx, ecx; hChainEngine
0x180071fc5  mov     dword ptr [rbp+arg_8], 0
0x180071fcc  movups  xmmword ptr [rbp+var_20.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180071fd0  mov     [rbp+var_20.cbSize], 20h ; ' '
0x180071fd7  call    cs:__imp_CertGetCertificateChain
0x180071fde  nop     dword ptr [rax+rax+00h]
0x180071fe3  xor     r13d, r13d
0x180071fe6  test    eax, eax
0x180071fe8  jnz     short loc_180072014
0x180071fea  call    ?EapTlsGetLastError@@YAKXZ; EapTlsGetLastError(void)
0x180071fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180071ff6  cmp     rcx, rdi
0x180071ff9  jz      short loc_18007200E
0x180071ffb  mov     rcx, [rcx+10h]
0x180071fff  lea     edx, [r13+50h]
0x180072003  mov     r9d, eax
0x180072006  mov     r8, rsi
0x180072009  call    WPP_SF_d
0x18007200e  mov     [rbp+pChainContext], r13
0x180072012  jmp     short loc_180072086
0x180072014  mov     rcx, [rbp+pChainContext]; struct _CERT_CHAIN_CONTEXT *
0x180072018  lea     r8, [rbp+arg_8]; int *
0x18007201c  mov     rdx, r12; struct _EAPTLS_FILTER_PROP *
0x18007201f  call    ?CheckFilterAllowsCert@@YAKPEBU_CERT_CHAIN_CONTEXT@@PEAU_EAPTLS_FILTER_PROP@@PEAH@Z; CheckFilterAllowsCert(_CERT_CHAIN_CONTEXT const *,_EAPTLS_FILTER_PROP *,int *)
0x180072024  test    eax, eax
0x180072026  jnz     short loc_180072037
0x180072028  cmp     dword ptr [rbp+arg_8], r13d
0x18007202c  jnz     short loc_18007207C
0x18007202e  mov     rcx, cs:WPP_GLOBAL_Control
0x180072035  jmp     short loc_180072064
0x180072037  mov     rcx, cs:WPP_GLOBAL_Control
0x18007203e  cmp     rcx, rdi
0x180072041  jz      short loc_18007205E
0x180072043  mov     rcx, [rcx+10h]
0x180072047  mov     edx, 51h ; 'Q'
0x18007204c  mov     r9d, eax
0x18007204f  mov     r8, rsi
0x180072052  call    WPP_SF_d
0x180072057  mov     rcx, cs:WPP_GLOBAL_Control
0x18007205e  cmp     dword ptr [rbp+arg_8], r13d
0x180072062  jnz     short loc_180072086
0x180072064  cmp     rcx, rdi
0x180072067  jz      short loc_180072086
0x180072069  mov     rcx, [rcx+10h]
0x18007206d  mov     edx, 52h ; 'R'
0x180072072  mov     r8, rsi
0x180072075  call    WPP_SF_
0x18007207a  jmp     short loc_180072086
0x18007207c  mov     rax, [rbp+arg_28]
0x180072080  mov     dword ptr [rax], 1
0x180072086  mov     rcx, r15; hMem
0x180072089  call    cs:__imp_LocalFree
0x180072090  nop     dword ptr [rax+rax+00h]
0x180072095  mov     rcx, [rbp+pChainContext]; pChainContext
0x180072099  test    rcx, rcx
0x18007209c  jz      short loc_1800720AA
0x18007209e  call    cs:__imp_CertFreeCertificateChain
0x1800720a5  nop     dword ptr [rax+rax+00h]
0x1800720aa  mov     eax, ebx
0x1800720ac  mov     rbx, [rsp+70h+arg_0]
0x1800720b4  add     rsp, 70h
0x1800720b8  pop     r15
0x1800720ba  pop     r14
0x1800720bc  pop     r13
0x1800720be  pop     r12
0x1800720c0  pop     rdi
0x1800720c1  pop     rsi
0x1800720c2  pop     rbp
0x1800720c3  retn
```
