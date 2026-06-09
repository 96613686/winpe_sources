# _GetKeyCertChain(_CERT_CONTEXT const * *,ulong,_CERT_CONTEXT const * * *,ulong *)

- ea: `0x180001480`
- end: `0x180001848`
- name: `?_GetKeyCertChain@@YAKPEAPEBU_CERT_CONTEXT@@KPEAPEAPEBU1@PEAK@Z`
- size: `968`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT **, unsigned int, const struct _CERT_CONTEXT ***, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001970`

## callees

- `0x180001480`
- `0x180003750`
- `0x180003ab0`
- `0x180004790`
- `0x18000a7ce`

## import_xrefs

- `CRYPT32!CertGetCertificateChain` at `0x1800015be`
- `CRYPT32!CertGetCertificateChain` at `0x1800015be`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180001791`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180001791`
- `CRYPT32!CertFreeCertificateChain` at `0x18000180f`
- `CRYPT32!CertFreeCertificateChain` at `0x18000180f`
- `CRYPT32!CertCompareCertificate` at `0x180001734`
- `CRYPT32!CertCompareCertificate` at `0x180001734`
- `CRYPT32!CertCloseStore` at `0x18000182e`
- `CRYPT32!CertCloseStore` at `0x18000182e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000181e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000181e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800014e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001662`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800014e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000160b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000160b`

## pseudocode

```c
__int64 __fastcall _GetKeyCertChain(
        const struct _CERT_CONTEXT **a1,
        unsigned int a2,
        const struct _CERT_CONTEXT ***a3,
        unsigned int *a4)
{
  unsigned int v5; // ebp
  unsigned int *v7; // r13
  unsigned int v8; // esi
  _QWORD *v9; // r14
  DWORD LastError; // edi
  DWORD IntermediateCertificateStore; // eax
  HCERTSTORE v12; // rbx
  unsigned int v13; // edi
  unsigned int v14; // r12d
  PCCERT_CHAIN_CONTEXT *ppChainContext; // rsi
  PCCERT_CHAIN_CONTEXT v16; // rax
  int v17; // esi
  const struct _CERT_CONTEXT **v18; // rdi
  unsigned int v19; // eax
  __int64 v20; // r8
  unsigned int v21; // r15d
  char *v22; // rbx
  unsigned int v23; // r14d
  char v24; // r12
  const CERT_CONTEXT *v25; // r13
  __int64 i; // r15
  unsigned __int16 *VolatileCertIdString; // rax
  const char *v28; // rdx
  PCCERT_CONTEXT v29; // rax
  __int64 v30; // rcx
  const CERT_CHAIN_CONTEXT *v31; // rcx
  PCERT_CHAIN_PARA pChainPara; // [rsp+20h] [rbp-D8h]
  unsigned int v34; // [rsp+40h] [rbp-B8h]
  unsigned int v35; // [rsp+40h] [rbp-B8h]
  HCERTSTORE hAdditionalStore; // [rsp+48h] [rbp-B0h] BYREF
  char *v37; // [rsp+50h] [rbp-A8h]
  _QWORD *v38; // [rsp+58h] [rbp-A0h]
  struct _CERT_CHAIN_PARA v39; // [rsp+60h] [rbp-98h] BYREF

  v5 = a2;
  v7 = a4;
  memset_0(&v39, 0, 0x60u);
  v8 = 0;
  *a3 = 0;
  *v7 = 0;
  ekTraceFmt(0x80B12C2u, 2, "cEKCertContext=%u\n", v5);
  v38 = LocalAlloc(0x40u, 8LL * v5);
  v9 = v38;
  if ( !v38 )
  {
    LastError = 14;
    ekTraceFmt(0x81212C2u, 1, "ERROR: LocalAlloc. Return=%d\n", 14);
    return LastError;
  }
  hAdditionalStore = 0;
  IntermediateCertificateStore = _TpmEndorsementKeyGetIntermediateCertificateStore(&hAdditionalStore);
  LastError = IntermediateCertificateStore;
  if ( !IntermediateCertificateStore )
  {
    v12 = hAdditionalStore;
    v13 = 0;
    v14 = 0;
    v34 = 0;
    while ( v13 < v5 )
    {
      memset_0(&v39.cbSize + 1, 0, 0x5Cu);
      v39.cbSize = 96;
      ppChainContext = (PCCERT_CHAIN_CONTEXT *)&v9[v13];
      if ( !CertGetCertificateChain(0, a1[v13], 0, v12, &v39, 0, 0, ppChainContext) )
      {
        LastError = GetLastError();
        ekTraceFmt(0x83812C2u, 1, "ERROR: CertGetCertificateChain. Return=%d\n", LastError);
        v8 = 0;
        goto LABEL_35;
      }
      v16 = *ppChainContext;
      if ( (*ppChainContext)->cChain )
      {
        v17 = (*v16->rgpChain)->cElement - 1;
        v34 = v17;
        if ( (*v16->rgpChain)->cElement != 1 )
        {
          ekTraceFmt(0x84312C2u, 2, "cCert[%u]=%u\n", v13, v17);
          v14 += v17;
        }
      }
      ++v13;
    }
    v8 = 0;
    v18 = 0;
    ekTraceFmt(0x84912C2u, 2, "cMaxCert=%u\n", v14);
    if ( v14 )
    {
      v18 = (const struct _CERT_CONTEXT **)LocalAlloc(0, 8LL * v14);
      if ( !v18 )
      {
        LastError = 14;
        ekTraceFmt(0x85212C2u, 1, "ERROR: LocalAlloc. Return=%d\n", 14);
        goto LABEL_35;
      }
      v19 = 0;
      v34 = 0;
      if ( !v5 )
      {
LABEL_34:
        *v7 = v19;
        *a3 = v18;
        LastError = 0;
        goto LABEL_35;
      }
      do
      {
        v20 = v9[v8];
        v37 = (char *)&v9[v8];
        if ( *(_DWORD *)(v20 + 12) )
        {
          v21 = 0;
          if ( *(_DWORD *)(**(_QWORD **)(v20 + 16) + 12LL) != 1 )
          {
            v22 = v37;
            v23 = v34;
            do
            {
              v35 = v21 + 1;
              v24 = 0;
              v25 = *(const CERT_CONTEXT **)(*(_QWORD *)(*(_QWORD *)(**(_QWORD **)(v20 + 16) + 16LL) + 8LL * (v21 + 1))
                                           + 8LL);
              ekTraceFmt(0x86A12C2u, 2, "cert[%u][%u]\n", v8, v21 + 1);
              for ( i = 0; (unsigned int)i < v23; i = (unsigned int)(i + 1) )
              {
                if ( CertCompareCertificate(0x10001u, v18[i]->pCertInfo, v25->pCertInfo) )
                {
                  v24 = 1;
                  break;
                }
              }
              VolatileCertIdString = _GetVolatileCertIdString(v25);
              v21 = v35;
              v28 = "dup";
              if ( !v24 )
                v28 = "add";
              LODWORD(pChainPara) = v35;
              ekTraceFmt(0x87612C2u, 2, "cert[%u][%u]: %hs %ws\n", v8, pChainPara, v28, VolatileCertIdString);
              if ( !v24 )
              {
                v29 = CertDuplicateCertificateContext(v25);
                v30 = v23++;
                v18[v30] = v29;
              }
              v20 = *(_QWORD *)v22;
            }
            while ( v35 < *(_DWORD *)(**(_QWORD **)(*(_QWORD *)v22 + 16LL) + 12LL) - 1 );
            v5 = a2;
            v34 = v23;
            v9 = v38;
          }
        }
        ++v8;
      }
      while ( v8 < v5 );
      v12 = hAdditionalStore;
      v8 = 0;
      v7 = a4;
    }
    v19 = v34;
    goto LABEL_34;
  }
  ekTraceFmt(
    0x81E12C2u,
    1,
    "ERROR: _TpmEndorsementKeyGetIntermediateCertificateStore. Return=%d\n",
    IntermediateCertificateStore);
  v12 = hAdditionalStore;
LABEL_35:
  if ( v5 )
  {
    do
    {
      v31 = (const CERT_CHAIN_CONTEXT *)v9[v8];
      if ( v31 )
        CertFreeCertificateChain(v31);
      ++v8;
    }
    while ( v8 < v5 );
  }
  LocalFree(v9);
  if ( v12 )
    CertCloseStore(v12, 0);
  return LastError;
}

```

## disassembly

```asm
0x180001480  mov     [rsp+arg_18], r9
0x180001485  mov     [rsp+arg_10], r8
0x18000148a  mov     [rsp+arg_8], edx
0x18000148e  push    rbx
0x18000148f  push    rbp
0x180001490  push    rsi
0x180001491  push    rdi
0x180001492  push    r13
0x180001494  push    r14
0x180001496  push    r15
0x180001498  sub     rsp, 0C0h
0x18000149f  mov     rbx, r8
0x1800014a2  mov     ebp, edx
0x1800014a4  mov     r15, rcx
0x1800014a7  xor     edx, edx; Val
0x1800014a9  mov     r8d, 60h ; '`'; Size
0x1800014af  lea     rcx, [rsp+0F8h+var_98]; void *
0x1800014b4  mov     r13, r9
0x1800014b7  call    memset_0
0x1800014bc  xor     esi, esi
0x1800014be  lea     r8, aCekcertcontext; "cEKCertContext=%u\n"
0x1800014c5  mov     r9d, ebp
0x1800014c8  mov     [rbx], rsi
0x1800014cb  mov     edx, 2; unsigned int
0x1800014d0  mov     [r13+0], esi
0x1800014d4  mov     ecx, 80B12C2h; unsigned int
0x1800014d9  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800014de  mov     edx, ebp
0x1800014e0  mov     ecx, 40h ; '@'; uFlags
0x1800014e5  shl     rdx, 3; uBytes
0x1800014e9  call    cs:__imp_LocalAlloc
0x1800014ef  mov     [rsp+0F8h+var_A0], rax
0x1800014f4  mov     r14, rax
0x1800014f7  test    rax, rax
0x1800014fa  jnz     short loc_18000151F
0x1800014fc  mov     edi, 0Eh
0x180001501  lea     r8, aErrorLocalallo_0; "ERROR: LocalAlloc. Return=%d\n"
0x180001508  mov     r9d, edi
0x18000150b  mov     edx, 1; unsigned int
0x180001510  mov     ecx, 81212C2h; unsigned int
0x180001515  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000151a  jmp     loc_180001834
0x18000151f  lea     rcx, [rsp+0F8h+hAdditionalStore]; void **
0x180001524  mov     [rsp+0F8h+hAdditionalStore], rsi
0x180001529  call    ?_TpmEndorsementKeyGetIntermediateCertificateStore@@YAJPEAPEAX@Z; _TpmEndorsementKeyGetIntermediateCertificateStore(void * *)
0x18000152e  mov     edi, eax
0x180001530  test    eax, eax
0x180001532  jz      short loc_180001557
0x180001534  mov     r9d, eax
0x180001537  lea     r8, aErrorTpmendors; "ERROR: _TpmEndorsementKeyGetIntermediat"...
0x18000153e  mov     edx, 1; unsigned int
0x180001543  mov     ecx, 81E12C2h; unsigned int
0x180001548  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000154d  mov     rbx, [rsp+0F8h+hAdditionalStore]
0x180001552  jmp     loc_180001800
0x180001557  mov     rbx, [rsp+0F8h+hAdditionalStore]
0x18000155c  mov     edi, esi
0x18000155e  mov     [rsp+0F8h+arg_0], r12
0x180001566  mov     r12d, esi
0x180001569  mov     [rsp+0F8h+var_B8], esi
0x18000156d  nop     dword ptr [rax]
0x180001570  cmp     edi, ebp
0x180001572  jnb     loc_180001633
0x180001578  xor     edx, edx; Val
0x18000157a  lea     rcx, [rsp+0F8h+var_98+4]; void *
0x18000157f  mov     r8d, 5Ch ; '\'; Size
0x180001585  call    memset_0
0x18000158a  xor     ecx, ecx
0x18000158c  mov     eax, edi
0x18000158e  mov     r9, rbx; hAdditionalStore
0x180001591  mov     [rsp+0F8h+var_98.cbSize], 60h ; '`'
0x180001599  xor     r8d, r8d; pTime
0x18000159c  mov     rdx, [r15+rax*8]; pCertContext
0x1800015a0  lea     rsi, [r14+rax*8]
0x1800015a4  mov     [rsp+0F8h+ppChainContext], rsi; ppChainContext
0x1800015a9  mov     [rsp+0F8h+pvReserved], rcx; pvReserved
0x1800015ae  mov     [rsp+0F8h+dwFlags], ecx; dwFlags
0x1800015b2  lea     rcx, [rsp+0F8h+var_98]
0x1800015b7  mov     [rsp+0F8h+pChainPara], rcx; pChainPara
0x1800015bc  xor     ecx, ecx; hChainEngine
0x1800015be  call    cs:__imp_CertGetCertificateChain
0x1800015c4  test    eax, eax
0x1800015c6  jz      short loc_18000160B
0x1800015c8  mov     rax, [rsi]
0x1800015cb  cmp     dword ptr [rax+0Ch], 0
0x1800015cf  jbe     short loc_180001604
0x1800015d1  mov     rax, [rax+10h]
0x1800015d5  mov     rcx, [rax]
0x1800015d8  mov     esi, [rcx+0Ch]
0x1800015db  sub     esi, 1
0x1800015de  mov     [rsp+0F8h+var_B8], esi
0x1800015e2  jz      short loc_180001604
0x1800015e4  mov     r9d, edi
0x1800015e7  mov     dword ptr [rsp+0F8h+pChainPara], esi
0x1800015eb  lea     r8, aCcertUU; "cCert[%u]=%u\n"
0x1800015f2  mov     edx, 2; unsigned int
0x1800015f7  mov     ecx, 84312C2h; unsigned int
0x1800015fc  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001601  add     r12d, esi
0x180001604  inc     edi
0x180001606  jmp     loc_180001570
0x18000160b  call    cs:__imp_GetLastError
0x180001611  lea     r8, aErrorCertgetce_0; "ERROR: CertGetCertificateChain. Return="...
0x180001618  mov     edx, 1; unsigned int
0x18000161d  mov     r9d, eax
0x180001620  mov     ecx, 83812C2h; unsigned int
0x180001625  mov     edi, eax
0x180001627  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000162c  xor     esi, esi
0x18000162e  jmp     loc_1800017F8
0x180001633  xor     esi, esi
0x180001635  lea     r8, aCmaxcertU; "cMaxCert=%u\n"
0x18000163c  mov     r9d, r12d
0x18000163f  mov     edx, 2; unsigned int
0x180001644  mov     ecx, 84912C2h; unsigned int
0x180001649  mov     edi, esi
0x18000164b  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001650  test    r12d, r12d
0x180001653  jz      loc_1800017E3
0x180001659  mov     edx, r12d
0x18000165c  xor     ecx, ecx; uFlags
0x18000165e  shl     rdx, 3; uBytes
0x180001662  call    cs:__imp_LocalAlloc
0x180001668  mov     rdi, rax
0x18000166b  test    rax, rax
0x18000166e  jnz     short loc_180001693
0x180001670  mov     edi, 0Eh
0x180001675  lea     r8, aErrorLocalallo_0; "ERROR: LocalAlloc. Return=%d\n"
0x18000167c  mov     r9d, edi
0x18000167f  mov     edx, 1; unsigned int
0x180001684  mov     ecx, 85212C2h; unsigned int
0x180001689  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000168e  jmp     loc_1800017F8
0x180001693  mov     eax, esi
0x180001695  mov     [rsp+0F8h+var_B8], eax
0x180001699  test    ebp, ebp
0x18000169b  jz      loc_1800017E7
0x1800016a1  mov     eax, esi
0x1800016a3  mov     r8, [r14+rax*8]
0x1800016a7  lea     rax, [r14+rax*8]
0x1800016ab  mov     [rsp+0F8h+var_A8], rax
0x1800016b0  cmp     dword ptr [r8+0Ch], 0
0x1800016b5  jbe     loc_1800017CA
0x1800016bb  mov     rax, [r8+10h]
0x1800016bf  xor     r15d, r15d
0x1800016c2  mov     rcx, [rax]
0x1800016c5  cmp     dword ptr [rcx+0Ch], 1
0x1800016c9  jz      loc_1800017CA
0x1800016cf  mov     rbx, [rsp+0F8h+var_A8]
0x1800016d4  lea     rbp, aAdd; "add"
0x1800016db  mov     r14d, [rsp+0F8h+var_B8]
0x1800016e0  mov     rax, [r8+10h]
0x1800016e4  lea     edx, [r15+1]
0x1800016e8  mov     [rsp+0F8h+var_B8], edx
0x1800016ec  lea     r8, aCertUU; "cert[%u][%u]\n"
0x1800016f3  mov     dword ptr [rsp+0F8h+pChainPara], edx
0x1800016f7  mov     r9d, esi
0x1800016fa  xor     r12b, r12b
0x1800016fd  mov     rax, [rax]
0x180001700  mov     rax, [rax+10h]
0x180001704  mov     rcx, [rax+rdx*8]
0x180001708  mov     edx, 2; unsigned int
0x18000170d  mov     r13, [rcx+8]
0x180001711  mov     ecx, 86A12C2h; unsigned int
0x180001716  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000171b  xor     r15d, r15d
0x18000171e  cmp     r15d, r14d
0x180001721  jnb     short loc_180001746
0x180001723  mov     rdx, [rdi+r15*8]
0x180001727  mov     ecx, 10001h; dwCertEncodingType
0x18000172c  mov     r8, [r13+18h]; pCertId2
0x180001730  mov     rdx, [rdx+18h]; pCertId1
0x180001734  call    cs:__imp_CertCompareCertificate
0x18000173a  test    eax, eax
0x18000173c  jnz     short loc_180001743
0x18000173e  inc     r15d
0x180001741  jmp     short loc_18000171E
0x180001743  mov     r12b, 1
0x180001746  mov     rcx, r13; pCertContext
0x180001749  call    ?_GetVolatileCertIdString@@YAPEAGPEBU_CERT_CONTEXT@@@Z; _GetVolatileCertIdString(_CERT_CONTEXT const *)
0x18000174e  mov     r15d, [rsp+0F8h+var_B8]
0x180001753  lea     rdx, aDup; "dup"
0x18000175a  mov     [rsp+0F8h+pvReserved], rax
0x18000175f  lea     r8, aCertUUHsWs; "cert[%u][%u]: %hs %ws\n"
0x180001766  test    r12b, r12b
0x180001769  mov     r9d, esi
0x18000176c  mov     ecx, 87612C2h; unsigned int
0x180001771  cmovz   rdx, rbp
0x180001775  mov     qword ptr [rsp+0F8h+dwFlags], rdx
0x18000177a  mov     edx, 2; unsigned int
0x18000177f  mov     dword ptr [rsp+0F8h+pChainPara], r15d
0x180001784  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001789  test    r12b, r12b
0x18000178c  jnz     short loc_1800017A1
0x18000178e  mov     rcx, r13; pCertContext
0x180001791  call    cs:__imp_CertDuplicateCertificateContext
0x180001797  mov     ecx, r14d
0x18000179a  inc     r14d
0x18000179d  mov     [rdi+rcx*8], rax
0x1800017a1  mov     r8, [rbx]
0x1800017a4  mov     rax, [r8+10h]
0x1800017a8  mov     rcx, [rax]
0x1800017ab  mov     eax, [rcx+0Ch]
0x1800017ae  dec     eax
0x1800017b0  cmp     r15d, eax
0x1800017b3  jb      loc_1800016E0
0x1800017b9  mov     ebp, [rsp+0F8h+arg_8]
0x1800017c0  mov     [rsp+0F8h+var_B8], r14d
0x1800017c5  mov     r14, [rsp+0F8h+var_A0]
0x1800017ca  inc     esi
0x1800017cc  cmp     esi, ebp
0x1800017ce  jb      loc_1800016A1
0x1800017d4  mov     rbx, [rsp+0F8h+hAdditionalStore]
0x1800017d9  xor     esi, esi
0x1800017db  mov     r13, [rsp+0F8h+arg_18]
0x1800017e3  mov     eax, [rsp+0F8h+var_B8]
0x1800017e7  mov     [r13+0], eax
0x1800017eb  mov     rax, [rsp+0F8h+arg_10]
0x1800017f3  mov     [rax], rdi
0x1800017f6  mov     edi, esi
0x1800017f8  mov     r12, [rsp+0F8h+arg_0]
0x180001800  test    ebp, ebp
0x180001802  jz      short loc_18000181B
0x180001804  mov     eax, esi
0x180001806  mov     rcx, [r14+rax*8]; pChainContext
0x18000180a  test    rcx, rcx
0x18000180d  jz      short loc_180001815
0x18000180f  call    cs:__imp_CertFreeCertificateChain
0x180001815  inc     esi
0x180001817  cmp     esi, ebp
0x180001819  jb      short loc_180001804
0x18000181b  mov     rcx, r14; hMem
0x18000181e  call    cs:__imp_LocalFree
0x180001824  test    rbx, rbx
0x180001827  jz      short loc_180001834
0x180001829  xor     edx, edx; dwFlags
0x18000182b  mov     rcx, rbx; hCertStore
0x18000182e  call    cs:__imp_CertCloseStore
0x180001834  mov     eax, edi
0x180001836  add     rsp, 0C0h
0x18000183d  pop     r15
0x18000183f  pop     r14
0x180001841  pop     r13
0x180001843  pop     rdi
0x180001844  pop     rsi
0x180001845  pop     rbp
0x180001846  pop     rbx
0x180001847  retn
```
