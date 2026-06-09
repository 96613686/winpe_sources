# __ScHelperSignPkcsMessage(_KERB_PRIMARY_CREDENTIAL *,KerbKeyAgreement *,_CRYPT_ALGORITHM_IDENTIFIER *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x1800bbc48`
- end: `0x1800bbfec`
- name: `?__ScHelperSignPkcsMessage@@YAJPEAU_KERB_PRIMARY_CREDENTIAL@@PEAVKerbKeyAgreement@@PEAU_CRYPT_ALGORITHM_IDENTIFIER@@PEAEKPEAPEAEPEAK@Z`
- size: `932`
- prototype: `__int64 __fastcall(struct _KERB_PRIMARY_CREDENTIAL *, struct KerbKeyAgreement *, struct _CRYPT_ALGORITHM_IDENTIFIER *, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ba688`

## callees

- `0x180007e80`
- `0x18001018c`
- `0x180010328`
- `0x1800107f8`
- `0x180070680`
- `0x18007108c`
- `0x18008b70c`
- `0x1800bbc48`
- `0x1800f1ea0`
- `0x1800f1f00`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbd59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbd59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbf95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbf95`
- `CRYPT32!CertGetCertificateChain` at `0x1800bbd4f`
- `CRYPT32!CertGetCertificateChain` at `0x1800bbd4f`
- `CRYPT32!CertCompareCertificateName` at `0x1800bbdd1`
- `CRYPT32!CertCompareCertificateName` at `0x1800bbed8`
- `CRYPT32!CertCompareCertificateName` at `0x1800bbdd1`
- `CRYPT32!CertCompareCertificateName` at `0x1800bbed8`
- `CRYPT32!CertFreeCertificateChain` at `0x1800bbfa4`
- `CRYPT32!CertFreeCertificateChain` at `0x1800bbfa4`

## pseudocode

```c
__int64 __fastcall __ScHelperSignPkcsMessage(
        struct _UNICODE_STRING **a1,
        struct KerbKeyAgreement *a2,
        struct _CRYPT_ALGORITHM_IDENTIFIER *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  _QWORD *p_pChainContext; // rbx
  struct _LUID *v11; // r15
  int v12; // esi
  int v13; // edi
  __int64 v14; // rdi
  struct _UNICODE_STRING *v15; // rdx
  DWORD LastError; // eax
  PCCERT_CHAIN_CONTEXT v17; // rdx
  __int64 v18; // rsi
  PCCERT_CONTEXT pCertContext; // rcx
  BOOL v20; // eax
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23; // ecx
  unsigned __int64 v24; // rdi
  unsigned __int64 v25; // rcx
  __int64 v26; // rcx
  unsigned __int64 v27; // rcx
  void *v28; // rsp
  void *v29; // rsp
  _DWORD *v30; // rax
  __int64 v31; // rsi
  PCCERT_CONTEXT v32; // rcx
  HANDLE v33; // rsi
  __int64 v35; // [rsp+0h] [rbp-60h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+60h] [rbp+0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp+8h] BYREF
  struct KerbKeyAgreement *v38; // [rsp+70h] [rbp+10h]
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+A0h] [rbp+40h] BYREF
  int v40; // [rsp+D8h] [rbp+78h]

  v38 = a2;
  hObject = 0;
  p_pChainContext = 0;
  pChainContext = 0;
  v11 = (struct _LUID *)(a1 + 36);
  v12 = strncmp_0(a3->pszObjId, "1.3.14.3.2.26", 8u);
  v13 = KerbImpersonateClient(v11, &hObject);
  if ( v13 < 0 )
    goto LABEL_35;
  v13 = KerbSetPin(a1[35], v12 != 0);
  if ( v13 < 0 )
    goto LABEL_35;
  LODWORD(v14) = 0;
  if ( !KerbGlobalSendOnlyLeafCertificate )
  {
    memset_0(&pChainPara, 0, 0x60u);
    v15 = a1[35];
    pChainPara.cbSize = 96;
    v40 = 1000 * KerbGlobalCRLRetrievalTimeout;
    if ( CertGetCertificateChain(
           (HCERTCHAINENGINE)(a1[36] == 0),
           *(PCCERT_CONTEXT *)&v15[2].Length,
           0,
           0,
           &pChainPara,
           0xC0000000,
           0,
           &pChainContext) )
    {
      v17 = pChainContext;
    }
    else
    {
      LastError = GetLastError();
      KerbTracerT::Log(
        2,
        "__ScHelperSignPkcsMessage",
        1080,
        "Failed to get certificate chain for client: %#x\n",
        LastError);
      v17 = 0;
      pChainContext = 0;
    }
    if ( v17 )
    {
      if ( v17->cChain )
      {
        v18 = 0;
        if ( (*v17->rgpChain)->cElement )
        {
          do
          {
            pCertContext = (*v17->rgpChain)->rgpElement[v18]->pCertContext;
            v20 = CertCompareCertificateName(
                    pCertContext->dwCertEncodingType,
                    &pCertContext->pCertInfo->Issuer,
                    &pCertContext->pCertInfo->Subject);
            v17 = pChainContext;
            v23 = v14 + 1;
            if ( v20 )
              v23 = v14;
            v18 = (unsigned int)(v18 + 1);
            LODWORD(v14) = v23;
          }
          while ( (unsigned int)v18 < (*pChainContext->rgpChain)->cElement );
          if ( v23 )
          {
            v24 = 8LL * v23;
            if ( v24 )
            {
              if ( v24 <= g_ulMaxStackAllocSize )
              {
                v25 = v24 + g_ulAdditionalProbeSize + 8;
                if ( v25 >= v24 )
                {
                  if ( (unsigned int)VerifyStackAvailable(v25, pChainContext, v21, v22) )
                  {
                    v26 = v24 + 23;
                    if ( v24 + 23 <= v24 + 8 )
                      v26 = 0xFFFFFFFFFFFFFF0LL;
                    v27 = v26 & 0xFFFFFFFFFFFFFFF0uLL;
                    v28 = alloca(v27);
                    v29 = alloca(v27);
                    p_pChainContext = &pChainContext;
                    if ( &v35 != (__int64 *)-96LL )
                    {
                      LODWORD(pChainContext) = 1801679955;
                      p_pChainContext = &hObject;
                      if ( &hObject )
                        goto LABEL_26;
                    }
                  }
                  v17 = pChainContext;
                }
              }
            }
            if ( v24 + 8 < v24 )
            {
LABEL_27:
              if ( !p_pChainContext )
              {
                v13 = -1073741801;
                goto LABEL_35;
              }
              v14 = 0;
              v31 = 0;
              if ( (*v17->rgpChain)->cElement )
              {
                do
                {
                  v32 = (*v17->rgpChain)->rgpElement[v31]->pCertContext;
                  if ( !CertCompareCertificateName(
                          v32->dwCertEncodingType,
                          &v32->pCertInfo->Issuer,
                          &v32->pCertInfo->Subject) )
                  {
                    p_pChainContext[v14] = (*pChainContext->rgpChain)->rgpElement[v31]->pCertContext;
                    v14 = (unsigned int)(v14 + 1);
                  }
                  v17 = pChainContext;
                  v31 = (unsigned int)(v31 + 1);
                }
                while ( (unsigned int)v31 < (*pChainContext->rgpChain)->cElement );
              }
              goto LABEL_33;
            }
            v30 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64, PCCERT_CHAIN_CONTEXT))g_pfnAllocate)(
                              v24 + 8,
                              v17);
            p_pChainContext = v30;
            if ( v30 )
            {
              *v30 = 1885431112;
              p_pChainContext = v30 + 2;
            }
LABEL_26:
            v17 = pChainContext;
            goto LABEL_27;
          }
        }
      }
    }
  }
LABEL_33:
  v13 = (*(__int64 (__fastcall **)(_QWORD, struct KerbKeyAgreement *, _QWORD, _QWORD *, _DWORD, struct _CRYPT_ALGORITHM_IDENTIFIER *, const char *, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *))(**(_QWORD **)&a1[35][4].Length + 8LL))(
          *(_QWORD *)&a1[35][4].Length,
          v38,
          *(_QWORD *)&a1[35][2].Length,
          p_pChainContext,
          v14,
          a3,
          "1.3.6.1.5.2.3.1",
          a4,
          a5,
          a6,
          a7);
  if ( v13 >= 0 )
    HIDWORD(a1[35][3].Buffer) &= ~0x800u;
LABEL_35:
  v33 = hObject;
  KerbRevertImpersonation(hObject);
  if ( v33 )
    CloseHandle(v33);
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( p_pChainContext && *((_DWORD *)p_pChainContext - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800bbc48  push    rbp
0x1800bbc4a  push    rbx
0x1800bbc4b  push    rsi
0x1800bbc4c  push    rdi
0x1800bbc4d  push    r12
0x1800bbc4f  push    r13
0x1800bbc51  push    r14
0x1800bbc53  push    r15
0x1800bbc55  sub     rsp, 118h
0x1800bbc5c  lea     rbp, [rsp+60h]
0x1800bbc61  mov     rax, cs:__security_cookie
0x1800bbc68  xor     rax, rbp
0x1800bbc6b  mov     [rbp+0F0h+var_50], rax
0x1800bbc72  mov     r12, r8
0x1800bbc75  mov     [rbp+0F0h+var_E0], rdx
0x1800bbc79  mov     r14, rcx
0x1800bbc7c  mov     [rbp+0F0h+hObject], 0
0x1800bbc84  xor     ebx, ebx
0x1800bbc86  mov     [rbp+0F0h+pChainContext], 0
0x1800bbc8e  lea     rdx, a13143226; "1.3.14.3.2.26"
0x1800bbc95  mov     r13, r9
0x1800bbc98  mov     rcx, [r12]; Str1
0x1800bbc9c  lea     r8d, [rbx+8]; MaxCount
0x1800bbca0  call    strncmp_0
0x1800bbca5  lea     r15, [r14+120h]
0x1800bbcac  mov     esi, eax
0x1800bbcae  mov     rcx, r15; struct _LUID *
0x1800bbcb1  lea     rdx, [rbp+0F0h+hObject]; void **
0x1800bbcb5  call    ?KerbImpersonateClient@@YAJPEAU_LUID@@PEAPEAX@Z; KerbImpersonateClient(_LUID *,void * *)
0x1800bbcba  mov     edi, eax
0x1800bbcbc  test    eax, eax
0x1800bbcbe  js      loc_1800BBF81
0x1800bbcc4  mov     rcx, [r14+118h]; struct _UNICODE_STRING *
0x1800bbccb  xor     edx, edx
0x1800bbccd  test    esi, esi
0x1800bbccf  setnz   dl; int
0x1800bbcd2  call    ?KerbSetPin@@YAJPEAU_KERB_PUBLIC_KEY_CREDENTIALS@@H@Z; KerbSetPin(_KERB_PUBLIC_KEY_CREDENTIALS *,int)
0x1800bbcd7  mov     edi, eax
0x1800bbcd9  test    eax, eax
0x1800bbcdb  js      loc_1800BBF81
0x1800bbce1  xor     edi, edi
0x1800bbce3  cmp     cs:?KerbGlobalSendOnlyLeafCertificate@@3KA, ebx; ulong KerbGlobalSendOnlyLeafCertificate
0x1800bbce9  jnz     loc_1800BBF11
0x1800bbcef  lea     esi, [rbx+60h]
0x1800bbcf2  xor     edx, edx; Val
0x1800bbcf4  mov     r8d, esi; Size
0x1800bbcf7  lea     rcx, [rbp+0F0h+var_B0]; void *
0x1800bbcfb  call    memset_0
0x1800bbd00  imul    eax, cs:?KerbGlobalCRLRetrievalTimeout@@3JA, 3E8h; long KerbGlobalCRLRetrievalTimeout
0x1800bbd0a  mov     ecx, ebx
0x1800bbd0c  mov     rdx, [r14+118h]
0x1800bbd13  mov     [rbp+0F0h+var_B0.cbSize], esi
0x1800bbd16  mov     [rbp+0F0h+var_78], eax
0x1800bbd19  mov     eax, [r14+124h]
0x1800bbd20  or      eax, [r15]
0x1800bbd23  mov     rdx, [rdx+20h]; pCertContext
0x1800bbd27  lea     rax, [rbp+0F0h+pChainContext]
0x1800bbd2b  mov     [rsp+150h+ppChainContext], rax; ppChainContext
0x1800bbd30  setz    cl; hChainEngine
0x1800bbd33  mov     [rsp+150h+pvReserved], rbx; pvReserved
0x1800bbd38  lea     rax, [rbp+0F0h+var_B0]
0x1800bbd3c  mov     [rsp+150h+dwFlags], 0C0000000h; dwFlags
0x1800bbd44  xor     r9d, r9d; hAdditionalStore
0x1800bbd47  xor     r8d, r8d; pTime
0x1800bbd4a  mov     [rsp+150h+pChainPara], rax; pChainPara
0x1800bbd4f  call    cs:__imp_CertGetCertificateChain
0x1800bbd55  test    eax, eax
0x1800bbd57  jnz     short loc_1800BBD87
0x1800bbd59  call    cs:__imp_GetLastError
0x1800bbd5f  lea     r9, aFailedToGetCer_1; "Failed to get certificate chain for cli"...
0x1800bbd66  mov     r8d, 438h
0x1800bbd6c  lea     rdx, aSchelpersignpk; "__ScHelperSignPkcsMessage"
0x1800bbd73  mov     dword ptr [rsp+150h+pChainPara], eax
0x1800bbd77  lea     ecx, [rbx+2]
0x1800bbd7a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800bbd7f  xor     edx, edx
0x1800bbd81  mov     [rbp+0F0h+pChainContext], rdx
0x1800bbd85  jmp     short loc_1800BBD8B
0x1800bbd87  mov     rdx, [rbp+0F0h+pChainContext]
0x1800bbd8b  test    rdx, rdx
0x1800bbd8e  jz      loc_1800BBF11
0x1800bbd94  cmp     dword ptr [rdx+0Ch], 1
0x1800bbd98  jb      loc_1800BBF11
0x1800bbd9e  mov     rax, [rdx+10h]
0x1800bbda2  xor     esi, esi
0x1800bbda4  mov     rcx, [rax]
0x1800bbda7  cmp     [rcx+0Ch], ebx
0x1800bbdaa  jbe     loc_1800BBF11
0x1800bbdb0  mov     rax, [rdx+10h]
0x1800bbdb4  mov     rax, [rax]
0x1800bbdb7  mov     rax, [rax+10h]
0x1800bbdbb  mov     rcx, [rax+rsi*8]
0x1800bbdbf  mov     rcx, [rcx+8]
0x1800bbdc3  mov     rdx, [rcx+18h]
0x1800bbdc7  mov     ecx, [rcx]; dwCertEncodingType
0x1800bbdc9  lea     r8, [rdx+50h]; pCertName2
0x1800bbdcd  add     rdx, 30h ; '0'; pCertName1
0x1800bbdd1  call    cs:__imp_CertCompareCertificateName
0x1800bbdd7  mov     rdx, [rbp+0F0h+pChainContext]
0x1800bbddb  lea     ecx, [rdi+1]
0x1800bbdde  test    eax, eax
0x1800bbde0  cmovnz  ecx, edi
0x1800bbde3  inc     esi
0x1800bbde5  mov     rax, [rdx+10h]
0x1800bbde9  mov     edi, ecx
0x1800bbdeb  mov     rcx, [rax]
0x1800bbdee  cmp     esi, [rcx+0Ch]
0x1800bbdf1  jb      short loc_1800BBDB0
0x1800bbdf3  test    edi, edi
0x1800bbdf5  jz      loc_1800BBF11
0x1800bbdfb  lea     rdi, ds:0[rdi*8]
0x1800bbe03  test    rdi, rdi
0x1800bbe06  jz      short loc_1800BBE6D
0x1800bbe08  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800bbe0f  ja      short loc_1800BBE6D
0x1800bbe11  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800bbe18  add     rcx, 8
0x1800bbe1c  add     rcx, rdi
0x1800bbe1f  cmp     rcx, rdi
0x1800bbe22  jb      short loc_1800BBE6D
0x1800bbe24  call    VerifyStackAvailable
0x1800bbe29  test    eax, eax
0x1800bbe2b  jz      short loc_1800BBE69
0x1800bbe2d  lea     rax, [rdi+8]
0x1800bbe31  lea     rcx, [rax+0Fh]
0x1800bbe35  cmp     rcx, rax
0x1800bbe38  ja      short loc_1800BBE44
0x1800bbe3a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800bbe44  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800bbe48  mov     rax, rcx
0x1800bbe4b  call    _alloca_probe
0x1800bbe50  sub     rsp, rcx
0x1800bbe53  lea     rbx, [rsp+150h+pChainContext]
0x1800bbe58  test    rbx, rbx
0x1800bbe5b  jz      short loc_1800BBE69
0x1800bbe5d  mov     dword ptr [rbx], 6B637453h
0x1800bbe63  add     rbx, 8
0x1800bbe67  jnz     short loc_1800BBE94
0x1800bbe69  mov     rdx, [rbp+0F0h+pChainContext]
0x1800bbe6d  lea     rcx, [rdi+8]
0x1800bbe71  cmp     rcx, rdi
0x1800bbe74  jb      short loc_1800BBE98
0x1800bbe76  mov     rax, cs:g_pfnAllocate
0x1800bbe7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbe82  mov     rbx, rax
0x1800bbe85  test    rax, rax
0x1800bbe88  jz      short loc_1800BBE94
0x1800bbe8a  mov     dword ptr [rax], 70616548h
0x1800bbe90  add     rbx, 8
0x1800bbe94  mov     rdx, [rbp+0F0h+pChainContext]
0x1800bbe98  test    rbx, rbx
0x1800bbe9b  jnz     short loc_1800BBEA7
0x1800bbe9d  mov     edi, 0C0000017h
0x1800bbea2  jmp     loc_1800BBF81
0x1800bbea7  mov     rax, [rdx+10h]
0x1800bbeab  xor     edi, edi
0x1800bbead  xor     esi, esi
0x1800bbeaf  mov     rcx, [rax]
0x1800bbeb2  cmp     [rcx+0Ch], esi
0x1800bbeb5  jbe     short loc_1800BBF11
0x1800bbeb7  mov     rax, [rdx+10h]
0x1800bbebb  mov     rcx, [rax]
0x1800bbebe  mov     rax, [rcx+10h]
0x1800bbec2  mov     rcx, [rax+rsi*8]
0x1800bbec6  mov     rcx, [rcx+8]
0x1800bbeca  mov     rdx, [rcx+18h]
0x1800bbece  mov     ecx, [rcx]; dwCertEncodingType
0x1800bbed0  lea     r8, [rdx+50h]; pCertName2
0x1800bbed4  add     rdx, 30h ; '0'; pCertName1
0x1800bbed8  call    cs:__imp_CertCompareCertificateName
0x1800bbede  test    eax, eax
0x1800bbee0  jnz     short loc_1800BBEFF
0x1800bbee2  mov     rax, [rbp+0F0h+pChainContext]
0x1800bbee6  mov     rcx, [rax+10h]
0x1800bbeea  mov     rax, [rcx]
0x1800bbeed  mov     rcx, [rax+10h]
0x1800bbef1  mov     rax, [rcx+rsi*8]
0x1800bbef5  mov     rax, [rax+8]
0x1800bbef9  mov     [rbx+rdi*8], rax
0x1800bbefd  inc     edi
0x1800bbeff  mov     rdx, [rbp+0F0h+pChainContext]
0x1800bbf03  inc     esi
0x1800bbf05  mov     rax, [rdx+10h]
0x1800bbf09  mov     rcx, [rax]
0x1800bbf0c  cmp     esi, [rcx+0Ch]
0x1800bbf0f  jb      short loc_1800BBEB7
0x1800bbf11  mov     r8, [r14+118h]
0x1800bbf18  mov     r9, rbx
0x1800bbf1b  mov     rdx, [rbp+0F0h+arg_30]
0x1800bbf22  mov     [rsp+150h+var_100], rdx
0x1800bbf27  mov     rdx, [rbp+0F0h+arg_28]
0x1800bbf2e  mov     rcx, [r8+40h]
0x1800bbf32  mov     r8, [r8+20h]
0x1800bbf36  mov     [rsp+150h+var_108], rdx
0x1800bbf3b  mov     edx, [rbp+0F0h+arg_20]
0x1800bbf41  mov     rax, [rcx]
0x1800bbf44  mov     [rsp+150h+var_110], edx
0x1800bbf48  lea     rdx, a13615231; "1.3.6.1.5.2.3.1"
0x1800bbf4f  mov     [rsp+150h+ppChainContext], r13
0x1800bbf54  mov     [rsp+150h+pvReserved], rdx
0x1800bbf59  mov     rax, [rax+8]
0x1800bbf5d  mov     rdx, [rbp+0F0h+var_E0]
0x1800bbf61  mov     qword ptr [rsp+150h+dwFlags], r12
0x1800bbf66  mov     dword ptr [rsp+150h+pChainPara], edi
0x1800bbf6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbf6f  mov     edi, eax
0x1800bbf71  test    eax, eax
0x1800bbf73  js      short loc_1800BBF81
0x1800bbf75  mov     rax, [r14+118h]
0x1800bbf7c  btr     dword ptr [rax+3Ch], 0Bh
0x1800bbf81  mov     rsi, [rbp+0F0h+hObject]
0x1800bbf85  mov     rcx, rsi; Token
0x1800bbf88  call    ?KerbRevertImpersonation@@YAXPEAX@Z; KerbRevertImpersonation(void *)
0x1800bbf8d  test    rsi, rsi
0x1800bbf90  jz      short loc_1800BBF9B
0x1800bbf92  mov     rcx, rsi; hObject
0x1800bbf95  call    cs:__imp_CloseHandle
0x1800bbf9b  mov     rcx, [rbp+0F0h+pChainContext]; pChainContext
0x1800bbf9f  test    rcx, rcx
0x1800bbfa2  jz      short loc_1800BBFAA
0x1800bbfa4  call    cs:__imp_CertFreeCertificateChain
0x1800bbfaa  test    rbx, rbx
0x1800bbfad  jz      short loc_1800BBFC7
0x1800bbfaf  lea     rcx, [rbx-8]
0x1800bbfb3  cmp     dword ptr [rcx], 70616548h
0x1800bbfb9  jnz     short loc_1800BBFC7
0x1800bbfbb  mov     rax, cs:g_pfnFree
0x1800bbfc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbfc7  mov     eax, edi
0x1800bbfc9  mov     rcx, [rbp+0F0h+var_50]
0x1800bbfd0  xor     rcx, rbp; StackCookie
0x1800bbfd3  call    __security_check_cookie
0x1800bbfd8  lea     rsp, [rbp+0B8h]
0x1800bbfdf  pop     r15
0x1800bbfe1  pop     r14
0x1800bbfe3  pop     r13
0x1800bbfe5  pop     r12
0x1800bbfe7  pop     rdi
0x1800bbfe8  pop     rsi
0x1800bbfe9  pop     rbx
0x1800bbfea  pop     rbp
0x1800bbfeb  retn
```
