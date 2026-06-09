# ScHelperPeer2PeerSignPkcsMessage(_CERT_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,_CRYPT_ALGORITHM_IDENTIFIER *,char *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180017df0`
- end: `0x18001811c`
- name: `?ScHelperPeer2PeerSignPkcsMessage@@YAJPEBU_CERT_CONTEXT@@PEBU_CERT_CHAIN_CONTEXT@@PEAU_CRYPT_ALGORITHM_IDENTIFIER@@PEADPEAEKPEAPEAEPEAK@Z`
- size: `812`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCert@<rcx>, const struct _CERT_CHAIN_CONTEXT *@<rdx>, struct _CRYPT_ALGORITHM_IDENTIFIER *@<r8>, char *@<r9>, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000fc70`
- `0x180035dc0`

## callees

- `0x180017df0`
- `0x180018124`
- `0x180018c80`
- `0x1800210f0`
- `0x180023ce0`
- `0x180044f20`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180aa`
- `CRYPT32!CertGetCertificateChain` at `0x180017e80`
- `CRYPT32!CertGetCertificateChain` at `0x180017e80`
- `CRYPT32!CertCompareCertificateName` at `0x180017f15`
- `CRYPT32!CertCompareCertificateName` at `0x180018023`
- `CRYPT32!CertCompareCertificateName` at `0x180017f15`
- `CRYPT32!CertCompareCertificateName` at `0x180018023`
- `CRYPT32!CertFreeCertificateChain` at `0x1800180f7`
- `CRYPT32!CertFreeCertificateChain` at `0x1800180f7`

## pseudocode

```c
__int64 __fastcall ScHelperPeer2PeerSignPkcsMessage(
        PCCERT_CONTEXT pCert,
        const struct _CERT_CHAIN_CONTEXT *a2,
        struct _CRYPT_ALGORITHM_IDENTIFIER *a3,
        char *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  unsigned int v8; // esi
  const struct _CERT_CONTEXT **p_pChainContext; // rdi
  PCCERT_CHAIN_CONTEXT v12; // rbx
  DWORD LastError; // eax
  PCERT_SIMPLE_CHAIN *rgpChain; // rax
  __int64 v16; // r13
  PCERT_SIMPLE_CHAIN v17; // rdx
  PCCERT_CONTEXT pCertContext; // rcx
  bool v19; // zf
  __int64 v20; // rcx
  PCERT_SIMPLE_CHAIN *v21; // rax
  unsigned __int64 v22; // r13
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  _DWORD *v27; // rax
  unsigned int v28; // ebx
  PCERT_SIMPLE_CHAIN *v29; // rcx
  __int64 v30; // r13
  unsigned int v31; // edx
  PCERT_SIMPLE_CHAIN v32; // rax
  PCCERT_CONTEXT v33; // rcx
  unsigned int v34; // edx
  DWORD v35; // eax
  __int64 v37; // [rsp+0h] [rbp-50h] BYREF
  PCERT_CHAIN_PARA pChainPara; // [rsp+20h] [rbp-30h]
  unsigned int v39; // [rsp+50h] [rbp+0h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+58h] [rbp+8h] BYREF
  __int64 v41; // [rsp+60h] [rbp+10h]
  struct _CERT_CHAIN_PARA v42; // [rsp+68h] [rbp+18h] BYREF

  v8 = 0;
  pChainContext = 0;
  p_pChainContext = 0;
  v12 = a2;
  if ( !Pku2uGlobalSendOnlyLeafCertificate )
  {
    if ( a2 )
      goto LABEL_14;
    memset(&v42, 0, sizeof(v42));
    v42.cbSize = 32;
    if ( !CertGetCertificateChain(0, pCert, 0, 0, &v42, 0xC0000004, 0, &pChainContext) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids, LastError);
      }
      pChainContext = 0;
      goto LABEL_35;
    }
    v12 = pChainContext;
    if ( pChainContext )
    {
LABEL_14:
      if ( v12->cChain )
      {
        rgpChain = v12->rgpChain;
        v16 = 0;
        v17 = *rgpChain;
        if ( (*rgpChain)->cElement )
        {
          do
          {
            pCertContext = v17->rgpElement[v16]->pCertContext;
            v19 = !CertCompareCertificateName(
                     pCertContext->dwCertEncodingType,
                     &pCertContext->pCertInfo->Issuer,
                     &pCertContext->pCertInfo->Subject);
            v20 = v8 + 1;
            v21 = v12->rgpChain;
            if ( !v19 )
              v20 = v8;
            v16 = (unsigned int)(v16 + 1);
            v8 = v20;
            v17 = *v21;
          }
          while ( (unsigned int)v16 < (*v21)->cElement );
          if ( (_DWORD)v20 )
          {
            v22 = 8 * v20;
            if ( !(8 * v20)
              || v22 > g_ulMaxStackAllocSize
              || v22 + g_ulAdditionalProbeSize + 8 < v22
              || !(unsigned int)VerifyStackAvailable() )
            {
              goto LABEL_49;
            }
            v23 = v22 + 23;
            if ( v22 + 23 <= v22 + 8 )
              v23 = 0xFFFFFFFFFFFFFF0LL;
            v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
            v25 = alloca(v24);
            v26 = alloca(v24);
            p_pChainContext = (const struct _CERT_CONTEXT **)&v39;
            if ( &v37 == (__int64 *)-80LL
              || (v39 = 1801679955, (p_pChainContext = (const struct _CERT_CONTEXT **)&pChainContext) == 0) )
            {
LABEL_49:
              if ( v22 + 8 >= v22 )
              {
                v27 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
                p_pChainContext = (const struct _CERT_CONTEXT **)v27;
                if ( v27 )
                {
                  *v27 = 1885431112;
                  p_pChainContext = (const struct _CERT_CONTEXT **)(v27 + 2);
                }
              }
            }
            if ( !p_pChainContext )
            {
              v28 = -1073741801;
              goto LABEL_44;
            }
            v29 = v12->rgpChain;
            if ( (*v29)->cElement )
            {
              v30 = 0;
              v31 = 0;
              v39 = 0;
              do
              {
                if ( v31 >= v8 )
                  break;
                v32 = *v29;
                v41 = 8 * v30;
                v33 = v32->rgpElement[v30]->pCertContext;
                if ( CertCompareCertificateName(
                       v33->dwCertEncodingType,
                       &v33->pCertInfo->Issuer,
                       &v33->pCertInfo->Subject) )
                {
                  v31 = v39;
                }
                else
                {
                  v34 = v39;
                  p_pChainContext[v39] = (*v12->rgpChain)->rgpElement[(unsigned __int64)v41 / 8]->pCertContext;
                  v31 = v34 + 1;
                  v39 = v31;
                }
                v29 = v12->rgpChain;
                v30 = (unsigned int)(v30 + 1);
              }
              while ( (unsigned int)v30 < (*v29)->cElement );
            }
          }
        }
      }
    }
  }
LABEL_35:
  v28 = 0;
  if ( !(unsigned int)ScHelperCMSSignMessage(pCert, a3, a5, a6, (int)pChainPara, a4, p_pChainContext, v8, a7, a8) )
  {
    v35 = GetLastError();
    if ( v35 == 234 )
    {
      v28 = -1073741789;
    }
    else
    {
      v28 = -1073740913;
      if ( v35 != -2146893790 )
        v28 = -1073740753;
    }
  }
  if ( p_pChainContext && *((_DWORD *)p_pChainContext - 2) == 1885431112 )
    ((void (__fastcall *)(const struct _CERT_CONTEXT **))g_pfnFree)(p_pChainContext - 1);
LABEL_44:
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  return v28;
}

```

## disassembly

```asm
0x180017df0  push    rbp
0x180017df2  push    rbx
0x180017df3  push    rsi
0x180017df4  push    rdi
0x180017df5  push    r12
0x180017df7  push    r13
0x180017df9  push    r14
0x180017dfb  push    r15
0x180017dfd  sub     rsp, 98h
0x180017e04  lea     rbp, [rsp+50h]
0x180017e09  mov     rax, cs:__security_cookie
0x180017e10  xor     rax, rbp
0x180017e13  mov     [rbp+80h+var_48], rax
0x180017e17  xor     esi, esi
0x180017e19  mov     [rbp+80h+pChainContext], 0
0x180017e21  xor     edi, edi
0x180017e23  mov     r15, r9
0x180017e26  cmp     cs:?Pku2uGlobalSendOnlyLeafCertificate@@3KA, esi; ulong Pku2uGlobalSendOnlyLeafCertificate
0x180017e2c  mov     r12, r8
0x180017e2f  mov     rbx, rdx
0x180017e32  mov     r14, rcx
0x180017e35  jnz     loc_180018065
0x180017e3b  test    rdx, rdx
0x180017e3e  jnz     loc_180017EDE
0x180017e44  xorps   xmm0, xmm0
0x180017e47  lea     rax, [rbp+80h+pChainContext]
0x180017e4b  mov     [rsp+0D0h+ppChainContext], rax; ppChainContext
0x180017e50  mov     rdx, rcx; pCertContext
0x180017e53  mov     [rsp+0D0h+pvReserved], rsi; pvReserved
0x180017e58  lea     rax, [rbp+80h+var_68]
0x180017e5c  movups  xmmword ptr [rbp+80h+var_68.cbSize], xmm0
0x180017e60  mov     [rsp+0D0h+dwFlags], 0C0000004h; dwFlags
0x180017e68  xor     r9d, r9d; hAdditionalStore
0x180017e6b  xor     r8d, r8d; pTime
0x180017e6e  mov     [rsp+0D0h+pChainPara], rax; int
0x180017e73  xor     ecx, ecx; hChainEngine
0x180017e75  mov     [rbp+80h+var_68.cbSize], 20h ; ' '
0x180017e7c  movups  xmmword ptr [rbp+80h+var_68.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180017e80  call    cs:__imp_CertGetCertificateChain
0x180017e86  test    eax, eax
0x180017e88  jnz     short loc_180017ED1
0x180017e8a  mov     rax, cs:WPP_GLOBAL_Control
0x180017e91  lea     rcx, WPP_GLOBAL_Control
0x180017e98  cmp     rax, rcx
0x180017e9b  jz      short loc_180017EC8
0x180017e9d  test    byte ptr [rax+1Ch], 2
0x180017ea1  jz      short loc_180017EC8
0x180017ea3  call    cs:__imp_GetLastError
0x180017ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x180017eb0  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x180017eb7  mov     edx, 0Ah
0x180017ebc  mov     r9d, eax
0x180017ebf  mov     rcx, [rcx+10h]
0x180017ec3  call    WPP_SF_d
0x180017ec8  mov     [rbp+80h+pChainContext], rsi
0x180017ecc  jmp     loc_180018065
0x180017ed1  mov     rbx, [rbp+80h+pChainContext]
0x180017ed5  test    rbx, rbx
0x180017ed8  jz      loc_180018065
0x180017ede  cmp     dword ptr [rbx+0Ch], 1
0x180017ee2  jb      loc_180018065
0x180017ee8  mov     rax, [rbx+10h]
0x180017eec  xor     r13d, r13d
0x180017eef  mov     rdx, [rax]
0x180017ef2  cmp     [rdx+0Ch], esi
0x180017ef5  jbe     loc_180018065
0x180017efb  mov     rax, [rdx+10h]
0x180017eff  mov     rcx, [rax+r13*8]
0x180017f03  mov     rcx, [rcx+8]
0x180017f07  mov     rdx, [rcx+18h]
0x180017f0b  mov     ecx, [rcx]; dwCertEncodingType
0x180017f0d  lea     r8, [rdx+50h]; pCertName2
0x180017f11  add     rdx, 30h ; '0'; pCertName1
0x180017f15  call    cs:__imp_CertCompareCertificateName
0x180017f1b  test    eax, eax
0x180017f1d  lea     ecx, [rsi+1]
0x180017f20  mov     rax, [rbx+10h]
0x180017f24  cmovnz  ecx, esi
0x180017f27  inc     r13d
0x180017f2a  mov     esi, ecx
0x180017f2c  mov     rdx, [rax]
0x180017f2f  cmp     r13d, [rdx+0Ch]
0x180017f33  jb      short loc_180017EFB
0x180017f35  test    ecx, ecx
0x180017f37  jz      loc_180018065
0x180017f3d  lea     r13, ds:0[rcx*8]
0x180017f45  test    r13, r13
0x180017f48  jz      short loc_180017FAB
0x180017f4a  cmp     r13, cs:g_ulMaxStackAllocSize
0x180017f51  ja      short loc_180017FAB
0x180017f53  mov     rcx, cs:g_ulAdditionalProbeSize
0x180017f5a  add     rcx, 8
0x180017f5e  add     rcx, r13
0x180017f61  cmp     rcx, r13
0x180017f64  jb      short loc_180017FAB
0x180017f66  call    VerifyStackAvailable
0x180017f6b  test    eax, eax
0x180017f6d  jz      short loc_180017FAB
0x180017f6f  lea     rax, [r13+8]
0x180017f73  lea     rcx, [rax+0Fh]
0x180017f77  cmp     rcx, rax
0x180017f7a  ja      short loc_180017F86
0x180017f7c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180017f86  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180017f8a  mov     rax, rcx
0x180017f8d  call    _alloca_probe
0x180017f92  sub     rsp, rcx
0x180017f95  lea     rdi, [rsp+0D0h+var_80]
0x180017f9a  test    rdi, rdi
0x180017f9d  jz      short loc_180017FAB
0x180017f9f  mov     dword ptr [rdi], 6B637453h
0x180017fa5  add     rdi, 8
0x180017fa9  jnz     short loc_180017FD2
0x180017fab  lea     rcx, [r13+8]
0x180017faf  cmp     rcx, r13
0x180017fb2  jb      short loc_180017FD2
0x180017fb4  mov     rax, cs:g_pfnAllocate
0x180017fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fc0  mov     rdi, rax
0x180017fc3  test    rax, rax
0x180017fc6  jz      short loc_180017FD2
0x180017fc8  mov     dword ptr [rax], 70616548h
0x180017fce  add     rdi, 8
0x180017fd2  test    rdi, rdi
0x180017fd5  jnz     short loc_180017FE1
0x180017fd7  mov     ebx, 0C0000017h
0x180017fdc  jmp     loc_1800180EE
0x180017fe1  mov     rcx, [rbx+10h]
0x180017fe5  mov     rax, [rcx]
0x180017fe8  cmp     dword ptr [rax+0Ch], 0
0x180017fec  jbe     short loc_180018065
0x180017fee  xor     r13d, r13d
0x180017ff1  xor     edx, edx
0x180017ff3  mov     [rbp+80h+var_80], edx
0x180017ff6  cmp     edx, esi
0x180017ff8  jnb     short loc_180018065
0x180017ffa  mov     rax, [rcx]
0x180017ffd  lea     rdx, ds:0[r13*8]
0x180018005  mov     [rbp+80h+var_70], rdx
0x180018009  mov     rcx, [rax+10h]
0x18001800d  mov     rax, [rcx+rdx]
0x180018011  mov     rcx, [rax+8]
0x180018015  mov     rdx, [rcx+18h]
0x180018019  mov     ecx, [rcx]; dwCertEncodingType
0x18001801b  lea     r8, [rdx+50h]; pCertName2
0x18001801f  add     rdx, 30h ; '0'; pCertName1
0x180018023  call    cs:__imp_CertCompareCertificateName
0x180018029  test    eax, eax
0x18001802b  jnz     short loc_180018052
0x18001802d  mov     rax, [rbx+10h]
0x180018031  mov     edx, [rbp+80h+var_80]
0x180018034  mov     rcx, [rax]
0x180018037  mov     rax, [rcx+10h]
0x18001803b  mov     rcx, [rbp+80h+var_70]
0x18001803f  mov     rax, [rax+rcx]
0x180018043  mov     rax, [rax+8]
0x180018047  mov     [rdi+rdx*8], rax
0x18001804b  inc     edx
0x18001804d  mov     [rbp+80h+var_80], edx
0x180018050  jmp     short loc_180018055
0x180018052  mov     edx, [rbp+80h+var_80]
0x180018055  mov     rcx, [rbx+10h]
0x180018059  inc     r13d
0x18001805c  mov     rax, [rcx]
0x18001805f  cmp     r13d, [rax+0Ch]
0x180018063  jb      short loc_180017FF6
0x180018065  mov     rax, [rbp+80h+arg_38]
0x18001806c  mov     rdx, r12; struct _CRYPT_ALGORITHM_IDENTIFIER *
0x18001806f  mov     r9d, [rbp+80h+arg_28]; unsigned int
0x180018076  mov     rcx, r14; pCert
0x180018079  mov     r8, [rbp+80h+arg_20]; unsigned __int8 *
0x180018080  xor     ebx, ebx
0x180018082  mov     [rsp+0D0h+var_88], rax; unsigned int *
0x180018087  mov     rax, [rbp+80h+arg_30]
0x18001808e  mov     [rsp+0D0h+var_90], rax; unsigned __int8 **
0x180018093  mov     dword ptr [rsp+0D0h+ppChainContext], esi; unsigned int
0x180018097  mov     [rsp+0D0h+pvReserved], rdi; struct _CERT_CONTEXT **
0x18001809c  mov     qword ptr [rsp+0D0h+dwFlags], r15; pszInnerContentObjID
0x1800180a1  call    ?ScHelperCMSSignMessage@@YAHPEBU_CERT_CONTEXT@@PEAU_CRYPT_ALGORITHM_IDENTIFIER@@PEAEKHPEADPEAPEBU1@KPEAPEAEPEAK@Z; ScHelperCMSSignMessage(_CERT_CONTEXT const *,_CRYPT_ALGORITHM_IDENTIFIER *,uchar *,ulong,int,char *,_CERT_CONTEXT const * *,ulong,uchar * *,ulong *)
0x1800180a6  test    eax, eax
0x1800180a8  jnz     short loc_1800180D0
0x1800180aa  call    cs:__imp_GetLastError
0x1800180b0  cmp     eax, 0EAh
0x1800180b5  jz      short loc_1800180CB
0x1800180b7  cmp     eax, 80090022h
0x1800180bc  mov     ebx, 0C000038Fh
0x1800180c1  mov     ecx, 0C000042Fh
0x1800180c6  cmovnz  ebx, ecx
0x1800180c9  jmp     short loc_1800180D0
0x1800180cb  mov     ebx, 0C0000023h
0x1800180d0  test    rdi, rdi
0x1800180d3  jz      short loc_1800180EE
0x1800180d5  cmp     dword ptr [rdi-8], 70616548h
0x1800180dc  lea     rcx, [rdi-8]
0x1800180e0  jnz     short loc_1800180EE
0x1800180e2  mov     rax, cs:g_pfnFree
0x1800180e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180ee  mov     rcx, [rbp+80h+pChainContext]; pChainContext
0x1800180f2  test    rcx, rcx
0x1800180f5  jz      short loc_1800180FD
0x1800180f7  call    cs:__imp_CertFreeCertificateChain
0x1800180fd  mov     eax, ebx
0x1800180ff  mov     rcx, [rbp+80h+var_48]
0x180018103  xor     rcx, rbp; StackCookie
0x180018106  call    __security_check_cookie
0x18001810b  lea     rsp, [rbp+48h]
0x18001810f  pop     r15
0x180018111  pop     r14
0x180018113  pop     r13
0x180018115  pop     r12
0x180018117  pop     rdi
0x180018118  pop     rsi
0x180018119  pop     rbx
0x18001811a  pop     rbp
0x18001811b  retn
```
