# CreateCertList(int,int,int,_EAPTLS_CERT_NODE * *,_EAPTLS_CERT_NODE * *,ulong,_EAPTLS_HASH *,ushort const *,ulong *,int,_EAPTLS_FILTER_PROP *,ulong *)

- ea: `0x180022680`
- end: `0x180022f5a`
- name: `?CreateCertList@@YAXHHHPEAPEAU_EAPTLS_CERT_NODE@@0KPEAU_EAPTLS_HASH@@PEBGPEAKHPEAU_EAPTLS_FILTER_PROP@@3@Z`
- size: `2266`
- prototype: `void __usercall(int@<ecx>, int@<edx>, int@<r8d>, struct _EAPTLS_CERT_NODE **@<r9>, struct _EAPTLS_CERT_NODE **, unsigned int, struct _EAPTLS_HASH *, const unsigned __int16 *, unsigned int *, int, struct _EAPTLS_FILTER_PROP *, unsigned int *)`
- caller_count: `5`
- callee_count: `18`
- tags: ``

## callers

- `0x180014a70`
- `0x18006aae8`
- `0x18006e548`
- `0x180070884`
- `0x180070bf8`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180015d00`
- `0x180021afc`
- `0x180022680`
- `0x18002e900`
- `0x18002e954`
- `0x180038270`
- `0x180069758`
- `0x18006c400`
- `0x18006d6b4`
- `0x18006d744`
- `0x18006d864`
- `0x18006da14`
- `0x18006dcbc`
- `0x18006e2e0`
- `0x180071198`
- `0x18007252c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002279a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002279a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f0e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022a9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022a9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022cec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022cfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022d1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022d2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022cec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022cfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022d1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022d2a`
- `CRYPT32!CertFreeCertificateChainList` at `0x180022ed5`
- `CRYPT32!CertFreeCertificateChainList` at `0x180022ed5`
- `CRYPT32!CertCloseStore` at `0x180022ef5`
- `CRYPT32!CertCloseStore` at `0x180022ef5`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800229c4`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800229c4`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180022c16`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180022c16`
- `CRYPT32!CertOpenStore` at `0x18002276c`
- `CRYPT32!CertOpenStore` at `0x18002276c`
- `CRYPT32!CertSelectCertificateChains` at `0x180022853`
- `CRYPT32!CertSelectCertificateChains` at `0x180022853`
- `CRYPT32!CertFreeCertificateChain` at `0x180022eba`
- `CRYPT32!CertFreeCertificateChain` at `0x180022eba`

## pseudocode

```c
void __fastcall CreateCertList(
        int a1,
        int a2,
        int a3,
        struct _EAPTLS_CERT_NODE **a4,
        struct _EAPTLS_CERT_NODE **a5,
        unsigned int a6,
        struct _EAPTLS_HASH *a7,
        unsigned __int16 *pvPara,
        unsigned int *a9,
        int a10,
        struct _EAPTLS_FILTER_PROP *a11,
        unsigned int *a12)
{
  int v12; // esi
  int v13; // r12d
  PCCERT_CONTEXT pCertContext; // r14
  unsigned int v15; // r15d
  DWORD v17; // r9d
  void *v18; // r10
  signed int v19; // ebx
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  unsigned int v24; // edx
  unsigned int v25; // r8d
  unsigned int v26; // r10d
  DWORD v27; // r9d
  const CERT_SELECT_CRITERIA *v28; // rax
  struct _EAPTLS_CONTROL_BLOCK *v29; // rcx
  int v30; // r8d
  int v31; // r13d
  PCCERT_CHAIN_CONTEXT v32; // r14
  __int64 v33; // rdx
  int v34; // r8d
  unsigned __int16 **v35; // rax
  unsigned __int16 **v36; // rsi
  DWORD v37; // eax
  HLOCAL *v38; // r12
  int v39; // r9d
  HLOCAL *v40; // r15
  DWORD v41; // eax
  struct _EAPTLS_CONTROL_BLOCK *v42; // rcx
  __int64 v43; // rdx
  unsigned __int16 CertWeight; // ax
  bool v45; // zf
  unsigned int *v46; // rax
  const char *v47; // rax
  const char *v48; // r9
  const unsigned __int16 *v49; // rcx
  PCCERT_CHAIN_CONTEXT *v50; // rax
  __int64 i; // rbx
  DWORD v52; // eax
  unsigned int v53; // [rsp+50h] [rbp-B0h]
  int v54; // [rsp+54h] [rbp-ACh]
  int v55; // [rsp+58h] [rbp-A8h]
  unsigned int v56; // [rsp+5Ch] [rbp-A4h]
  unsigned int v57; // [rsp+60h] [rbp-A0h]
  unsigned int v58; // [rsp+64h] [rbp-9Ch]
  HCERTSTORE hCertStore; // [rsp+68h] [rbp-98h]
  int v60; // [rsp+70h] [rbp-90h]
  DWORD pcSelection; // [rsp+78h] [rbp-88h] BYREF
  int v63; // [rsp+7Ch] [rbp-84h]
  PCCERT_CHAIN_CONTEXT *prgpSelection; // [rsp+80h] [rbp-80h] BYREF
  int v65[2]; // [rsp+88h] [rbp-78h] BYREF
  int v66; // [rsp+90h] [rbp-70h] BYREF
  int v67; // [rsp+94h] [rbp-6Ch]
  unsigned int v68; // [rsp+98h] [rbp-68h] BYREF
  int v69; // [rsp+9Ch] [rbp-64h]
  unsigned int *v70; // [rsp+A0h] [rbp-60h]
  struct _EAPTLS_CERT_NODE *v71; // [rsp+A8h] [rbp-58h] BYREF
  struct _EAPTLS_FILTER_PROP *v72; // [rsp+B0h] [rbp-50h]
  struct _EAPTLS_CERT_NODE **v73; // [rsp+B8h] [rbp-48h]
  struct _EAPTLS_HASH *v74; // [rsp+C0h] [rbp-40h]
  struct _EAPTLS_CERT_NODE **v75; // [rsp+C8h] [rbp-38h]
  unsigned int *v76; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v77; // [rsp+D8h] [rbp-28h]
  _BYTE rgpCriteria[20]; // [rsp+E0h] [rbp-20h] BYREF
  int v79; // [rsp+F4h] [rbp-Ch]

  v12 = 0;
  v13 = a1;
  v67 = a1;
  pCertContext = 0;
  v73 = a5;
  v15 = 0;
  v74 = a7;
  v76 = a9;
  v70 = a12;
  v75 = a4;
  v69 = a2;
  v72 = a11;
  v77 = pvPara;
  v71 = 0;
  v68 = 0;
  v60 = 0;
  v66 = 1;
  pcSelection = 0;
  prgpSelection = 0;
  v57 = 0;
  v55 = 0;
  v56 = 0;
  v58 = 0;
  v53 = 0;
  if ( a11 )
  {
    v12 = *(_WORD *)a11 & 0x10;
    v60 = v12;
  }
  if ( a1 || (v17 = 98304, a2) )
    v17 = 163840;
  hCertStore = CertOpenStore((LPCSTR)0xA, 0, 0, v17, pvPara);
  v18 = hCertStore;
  if ( !hCertStore )
  {
    v19 = -2143158256;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
LABEL_10:
      v24 = 0;
      v25 = 0;
      v26 = 0;
      goto LABEL_105;
    }
    LastError = GetLastError();
    v21 = WPP_GLOBAL_Control;
    v22 = 83;
    v23 = LastError;
LABEL_9:
    WPP_SF_d(*((_QWORD *)v21 + 2), v22, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v23);
    goto LABEL_10;
  }
  v19 = 0;
  if ( !a3 && !v13 )
  {
    *(_QWORD *)v65 = 0;
    *(_DWORD *)rgpCriteria = 1;
    *(_DWORD *)&rgpCriteria[4] = 1;
    *(_QWORD *)&rgpCriteria[8] = v65;
    if ( v12 )
    {
      v28 = 0;
      v27 = 0;
    }
    else
    {
      *(_QWORD *)v65 = "1.3.6.1.5.5.7.3.2";
      v27 = 1;
      v28 = (const CERT_SELECT_CRITERIA *)rgpCriteria;
    }
    if ( !CertSelectCertificateChains(
            0,
            g_selectSelfSignedCert != 0 ? 128 : 132,
            0,
            v27,
            v28,
            hCertStore,
            &pcSelection,
            &prgpSelection) )
      v19 = GetLastError();
    if ( v19 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_10;
      v22 = 84;
      v23 = (unsigned int)v19;
      goto LABEL_9;
    }
    v18 = hCertStore;
  }
  v29 = WPP_GLOBAL_Control;
  v30 = 0;
  v63 = 0;
  *(_QWORD *)rgpCriteria = 0;
  v31 = a3;
  v54 = 0;
  while ( 1 )
  {
    if ( !v31 && !v13 )
    {
      if ( v29 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)v29 + 2), 88, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
        v29 = WPP_GLOBAL_Control;
        v30 = v54;
      }
      if ( !prgpSelection || !pcSelection || v30 == pcSelection )
      {
        if ( v63 != 1 )
        {
          if ( v29 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)v29 + 2), 89, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
          v19 = -2143158016;
LABEL_100:
          LODWORD(pCertContext) = v55;
          v24 = v53;
          v25 = v56;
          v26 = v57;
          goto LABEL_105;
        }
        LODWORD(pCertContext) = v55;
        v24 = v53;
        v25 = v56;
        v26 = v57;
LABEL_104:
        v19 = 0;
        *v75 = v71;
        goto LABEL_105;
      }
      ++v53;
      v54 = v30 + 1;
      v32 = prgpSelection[v30];
      *(_QWORD *)rgpCriteria = v32;
      if ( v29 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)v29 + 2), 90, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      pCertContext = (*(*v32->rgpChain)->rgpElement)->pCertContext;
      if ( !v12 && !(unsigned int)FCheckUsage(pCertContext, 0, 0, 0, a10) )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v33 = 91;
          goto LABEL_36;
        }
LABEL_37:
        v58 = ++v15;
        goto LABEL_87;
      }
      goto LABEL_46;
    }
    pCertContext = CertEnumCertificatesInStore(v18, pCertContext);
    if ( !pCertContext )
      break;
    ++v53;
    if ( !v31 && !(unsigned int)FCheckUsage(pCertContext, 0, v13, 0, a10) )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_37;
      v33 = 86;
      goto LABEL_36;
    }
    if ( !(unsigned int)FCheckTimeValidity(pCertContext) )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_37;
      v33 = 87;
      goto LABEL_36;
    }
LABEL_46:
    if ( (unsigned int)FCheckGenuineWindowsPhoneCert(pCertContext) )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_37;
      v33 = 92;
LABEL_36:
      WPP_SF_(*((_QWORD *)v29 + 2), v33, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      v29 = WPP_GLOBAL_Control;
      goto LABEL_37;
    }
    if ( !v31
      && !v13
      && (unsigned int)FCheckSCardCertAndCanOpenSilentContext(
                         pCertContext,
                         a10,
                         v12,
                         (int *)((unsigned __int64)&v66 & -(__int64)(v70 != 0))) )
    {
      v58 = ++v15;
LABEL_86:
      v29 = WPP_GLOBAL_Control;
      goto LABEL_87;
    }
    v35 = (unsigned __int16 **)LocalAlloc(0x40u, 0x58u);
    v36 = v35;
    if ( v35 )
    {
      FGetFriendlyName(pCertContext, 0, v35 + 5);
      if ( !v13 && (unsigned int)FUserCertToStr(pCertContext, v36 + 4) )
      {
        *((_DWORD *)v36 + 20) = 1;
        goto LABEL_61;
      }
      if ( (unsigned int)FGetFriendlyName(pCertContext, 0, v36 + 4) )
      {
LABEL_61:
        v38 = (HLOCAL *)(v36 + 6);
        if ( (unsigned int)FCertToStr(pCertContext, 1u, 1, v36 + 6) )
        {
          v40 = (HLOCAL *)(v36 + 7);
          if ( (unsigned int)FormatDateString(pCertContext->pCertInfo->NotAfter, v36 + 7, 1, v39) )
          {
            if ( !v72 )
              goto LABEL_73;
            v65[0] = 0;
            v41 = CheckFilterAllowsCert(*(const struct _CERT_CHAIN_CONTEXT **)rgpCriteria, v72, v65);
            if ( v41 )
            {
              v42 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                v43 = 95;
                goto LABEL_71;
              }
LABEL_72:
              ++v55;
              goto LABEL_84;
            }
            if ( !v65[0] )
            {
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
              ++v56;
              goto LABEL_84;
            }
LABEL_73:
            *((_DWORD *)v36 + 2) = 20;
            if ( !CertGetCertificateContextProperty(pCertContext, 3u, (char *)v36 + 12, (DWORD *)v36 + 2) )
            {
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                v41 = GetLastError();
                v42 = WPP_GLOBAL_Control;
                v43 = 97;
LABEL_71:
                WPP_SF_d(*((_QWORD *)v42 + 2), v43, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v41);
              }
              goto LABEL_72;
            }
            v36[8] = (unsigned __int16 *)pCertContext->pCertInfo->NotBefore;
            CertWeight = GetCertWeight(pCertContext);
            v45 = v66 == 0;
            *((_WORD *)v36 + 36) = CertWeight;
            if ( v45 )
            {
              v46 = v70;
              if ( v70 )
              {
                *((_DWORD *)v36 + 19) = 1;
                ++*v46;
              }
            }
            SortedCertInsert(&v71, (struct _EAPTLS_CERT_NODE *)v36);
            ++v57;
            v63 = 1;
            AddCertNodeToSelList(v74, a6, (struct _EAPTLS_CERT_NODE *)v36, v73, &v68);
LABEL_85:
            v15 = v58;
            v13 = v67;
            v12 = v60;
            v31 = a3;
            goto LABEL_86;
          }
          v15 = v58;
        }
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      v38 = (HLOCAL *)(v36 + 6);
      v58 = v15 + 1;
      v40 = (HLOCAL *)(v36 + 7);
LABEL_84:
      LocalFree(v36[4]);
      LocalFree(v36[5]);
      LocalFree(*v38);
      LocalFree(*v40);
      LocalFree(v36);
      goto LABEL_85;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v37 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v37);
      v29 = WPP_GLOBAL_Control;
    }
    ++v55;
    v12 = v60;
LABEL_87:
    v30 = v54;
    v18 = hCertStore;
  }
  if ( !v63 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v47 = "Server ";
      v48 = "Root ";
      if ( !v13 )
        v47 = (const char *)&dword_180087A9C;
      if ( !a3 )
        v48 = (const char *)&dword_180087A9C;
      WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)&dword_180087A9C, v34, (_DWORD)v48, (__int64)v47);
    }
    v19 = -2143157760;
    goto LABEL_100;
  }
  v26 = v57;
  LODWORD(pCertContext) = v55;
  v25 = v56;
  v24 = v53;
  if ( v63 == 1 )
    goto LABEL_104;
LABEL_105:
  *v76 = v19;
  if ( v19 > 0 )
    v19 = (unsigned __int16)v19 | 0x80070000;
  if ( v13 || (v49 = L"CERT_SYSTEM_STORE_CURRENT_USER", v69) )
    v49 = L"CERT_SYSTEM_STORE_LOCAL_MACHINE";
  v79 = 1;
  *(_DWORD *)rgpCriteria = a10 != 0 ? 19 : 17;
  *(GUID *)&rgpCriteria[4] = GUID_NULL;
  NetworkingTriageScenario::GetConnected::EAPCreateCertificateListAction(
    (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)rgpCriteria,
    v26,
    (unsigned int)pCertContext,
    v25,
    v15,
    v24,
    v77,
    v49,
    v19);
  v50 = prgpSelection;
  if ( prgpSelection )
  {
    for ( i = 0; (unsigned int)i < pcSelection; i = (unsigned int)(i + 1) )
    {
      CertFreeCertificateChain(v50[i]);
      v50 = prgpSelection;
    }
    CertFreeCertificateChainList(v50);
    prgpSelection = 0;
  }
  if ( hCertStore
    && !CertCloseStore(hCertStore, 0)
    && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v52 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v52);
  }
}

```

## disassembly

```asm
0x180022680  push    rbp
0x180022682  push    rbx
0x180022683  push    rsi
0x180022684  push    rdi
0x180022685  push    r12
0x180022687  push    r13
0x180022689  push    r14
0x18002268b  push    r15
0x18002268d  lea     rbp, [rsp-8]
0x180022692  sub     rsp, 108h
0x180022699  mov     rax, cs:__security_cookie
0x1800226a0  xor     rax, rsp
0x1800226a3  mov     [rbp+40h+var_48], rax
0x1800226a7  mov     rax, [rbp+40h+arg_50]
0x1800226ae  xor     esi, esi
0x1800226b0  mov     r12d, ecx
0x1800226b3  mov     [rbp+40h+var_AC], ecx
0x1800226b6  mov     rcx, [rbp+40h+arg_20]
0x1800226ba  xor     r14d, r14d
0x1800226bd  mov     [rbp+40h+var_88], rcx
0x1800226c1  xor     r15d, r15d
0x1800226c4  mov     rcx, [rbp+40h+arg_30]
0x1800226cb  mov     edi, r8d
0x1800226ce  mov     [rbp+40h+var_80], rcx
0x1800226d2  mov     rcx, [rbp+40h+arg_40]
0x1800226d9  mov     [rbp+40h+var_70], rcx
0x1800226dd  mov     rcx, [rbp+40h+arg_58]
0x1800226e4  mov     [rsp+140h+var_CC], r8d
0x1800226e9  mov     r8, [rbp+40h+arg_38]
0x1800226f0  mov     [rbp+40h+var_A0], rcx
0x1800226f4  mov     [rbp+40h+var_78], r9
0x1800226f8  mov     [rbp+40h+var_A4], edx
0x1800226fb  mov     [rbp+40h+var_90], rax
0x1800226ff  mov     [rbp+40h+var_68], r8
0x180022703  mov     [rbp+40h+var_98], 0
0x18002270b  mov     [rbp+40h+var_A8], 0
0x180022712  mov     [rsp+140h+var_D0], esi
0x180022716  mov     [rbp+40h+var_B0], 1
0x18002271d  mov     [rsp+140h+var_C8], esi
0x180022721  mov     [rbp+40h+prgpSelection], rsi
0x180022725  mov     [rsp+140h+var_E0], esi
0x180022729  mov     [rsp+140h+var_E8], r14d
0x18002272e  mov     [rsp+140h+var_E4], esi
0x180022732  mov     [rsp+140h+var_DC], r15d
0x180022737  mov     [rsp+140h+var_F0], esi
0x18002273b  test    rax, rax
0x18002273e  jz      short loc_18002274A
0x180022740  movzx   esi, word ptr [rax]
0x180022743  and     esi, 10h
0x180022746  mov     [rsp+140h+var_D0], esi
0x18002274a  test    r12d, r12d
0x18002274d  jnz     short loc_180022759
0x18002274f  mov     r9d, 18000h
0x180022755  test    edx, edx
0x180022757  jz      short loc_18002275F
0x180022759  mov     r9d, 28000h; dwFlags
0x18002275f  xor     edx, edx; dwEncodingType
0x180022761  mov     [rsp+140h+pvPara], r8; pvPara
0x180022766  xor     r8d, r8d; hCryptProv
0x180022769  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18002276c  call    cs:__imp_CertOpenStore
0x180022773  nop     dword ptr [rax+rax+00h]
0x180022778  mov     [rsp+140h+hCertStore], rax
0x18002277d  mov     r10, rax
0x180022780  test    rax, rax
0x180022783  jnz     short loc_1800227D3
0x180022785  mov     ebx, 80420010h
0x18002278a  lea     rdi, WPP_GLOBAL_Control
0x180022791  cmp     cs:WPP_GLOBAL_Control, rdi
0x180022798  jz      short loc_1800227C5
0x18002279a  call    cs:__imp_GetLastError
0x1800227a1  nop     dword ptr [rax+rax+00h]
0x1800227a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227ad  mov     edx, 53h ; 'S'
0x1800227b2  mov     r9d, eax
0x1800227b5  mov     rcx, [rcx+10h]
0x1800227b9  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800227c0  call    WPP_SF_d
0x1800227c5  mov     edx, r14d
0x1800227c8  mov     r8d, edx
0x1800227cb  mov     r10d, edx
0x1800227ce  jmp     loc_180022E28
0x1800227d3  xor     ebx, ebx
0x1800227d5  test    edi, edi
0x1800227d7  jnz     loc_18002289E
0x1800227dd  test    r12d, r12d
0x1800227e0  jnz     loc_18002289E
0x1800227e6  mov     eax, cs:?g_selectSelfSignedCert@@3HA; int g_selectSelfSignedCert
0x1800227ec  neg     eax
0x1800227ee  mov     qword ptr [rbp+40h+var_B8], rbx
0x1800227f2  lea     rax, [rbp+40h+var_B8]
0x1800227f6  mov     dword ptr [rbp+40h+rgpCriteria], 1
0x1800227fd  sbb     edx, edx
0x1800227ff  mov     dword ptr [rbp+40h+rgpCriteria+4], 1
0x180022806  and     edx, 0FFFFFFFCh
0x180022809  mov     qword ptr [rbp+40h+rgpCriteria+8], rax
0x18002280d  add     edx, 84h; dwFlags
0x180022813  test    esi, esi
0x180022815  jnz     short loc_18002282C
0x180022817  lea     rax, Buf1; "1.3.6.1.5.5.7.3.2"
0x18002281e  mov     qword ptr [rbp+40h+var_B8], rax
0x180022822  lea     r9d, [rbx+1]
0x180022826  lea     rax, [rbp+40h+rgpCriteria]
0x18002282a  jmp     short loc_180022831
0x18002282c  xor     eax, eax
0x18002282e  xor     r9d, r9d; cCriteria
0x180022831  lea     rcx, [rbp+40h+prgpSelection]
0x180022835  xor     r8d, r8d; pChainParameters
0x180022838  mov     [rsp+140h+pprgpSelection], rcx; pprgpSelection
0x18002283d  lea     rcx, [rsp+140h+var_C8]
0x180022842  mov     [rsp+140h+pcSelection], rcx; pcSelection
0x180022847  xor     ecx, ecx; pSelectionContext
0x180022849  mov     [rsp+140h+hStore], r10; hStore
0x18002284e  mov     [rsp+140h+pvPara], rax; rgpCriteria
0x180022853  call    cs:__imp_CertSelectCertificateChains
0x18002285a  nop     dword ptr [rax+rax+00h]
0x18002285f  test    eax, eax
0x180022861  jnz     short loc_180022871
0x180022863  call    cs:__imp_GetLastError
0x18002286a  nop     dword ptr [rax+rax+00h]
0x18002286f  mov     ebx, eax
0x180022871  test    ebx, ebx
0x180022873  jz      short loc_180022899
0x180022875  mov     rcx, cs:WPP_GLOBAL_Control
0x18002287c  lea     rdi, WPP_GLOBAL_Control
0x180022883  cmp     rcx, rdi
0x180022886  jz      loc_1800227C5
0x18002288c  mov     edx, 54h ; 'T'
0x180022891  mov     r9d, ebx
0x180022894  jmp     loc_1800227B5
0x180022899  mov     r10, [rsp+140h+hCertStore]
0x18002289e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228a5  lea     rdi, WPP_GLOBAL_Control
0x1800228ac  xor     r13d, r13d
0x1800228af  xor     r8d, r8d
0x1800228b2  mov     [rsp+140h+var_C4], r13d
0x1800228b7  mov     qword ptr [rbp+40h+rgpCriteria], r13
0x1800228bb  mov     r13d, [rsp+140h+var_CC]
0x1800228c0  mov     [rsp+140h+var_EC], r8d
0x1800228c5  test    r13d, r13d
0x1800228c8  jnz     loc_1800229BE
0x1800228ce  test    r12d, r12d
0x1800228d1  jnz     loc_1800229BE
0x1800228d7  cmp     rcx, rdi
0x1800228da  jz      short loc_1800228FC
0x1800228dc  mov     rcx, [rcx+10h]
0x1800228e0  lea     edx, [r13+58h]
0x1800228e4  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800228eb  call    WPP_SF_
0x1800228f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228f7  mov     r8d, [rsp+140h+var_EC]
0x1800228fc  mov     rdx, [rbp+40h+prgpSelection]
0x180022900  test    rdx, rdx
0x180022903  jz      loc_180022D5E
0x180022909  mov     eax, [rsp+140h+var_C8]
0x18002290d  test    eax, eax
0x18002290f  jz      loc_180022D5E
0x180022915  cmp     r8d, eax
0x180022918  jz      loc_180022D5E
0x18002291e  inc     [rsp+140h+var_F0]
0x180022922  mov     eax, r8d
0x180022925  inc     r8d
0x180022928  mov     [rsp+140h+var_EC], r8d
0x18002292d  mov     r14, [rdx+rax*8]
0x180022931  mov     qword ptr [rbp+40h+rgpCriteria], r14
0x180022935  cmp     rcx, rdi
0x180022938  jz      short loc_18002294F
0x18002293a  mov     rcx, [rcx+10h]
0x18002293e  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180022945  mov     edx, 5Ah ; 'Z'
0x18002294a  call    WPP_SF_
0x18002294f  mov     rax, [r14+10h]
0x180022953  mov     rcx, [rax]
0x180022956  mov     rax, [rcx+10h]
0x18002295a  mov     rcx, [rax]
0x18002295d  mov     r14, [rcx+8]
0x180022961  test    esi, esi
0x180022963  jnz     loc_180022A34
0x180022969  mov     eax, [rbp+40h+arg_48]
0x18002296f  xor     r9d, r9d; int
0x180022972  xor     r8d, r8d; int
0x180022975  mov     dword ptr [rsp+140h+pvPara], eax; int
0x180022979  xor     edx, edx; struct _CTL_USAGE *
0x18002297b  mov     rcx, r14; pCertContext
0x18002297e  call    ?FCheckUsage@@YAHPEBU_CERT_CONTEXT@@PEAU_CTL_USAGE@@HHH@Z; FCheckUsage(_CERT_CONTEXT const *,_CTL_USAGE *,int,int,int)
0x180022983  test    eax, eax
0x180022985  jnz     loc_180022A34
0x18002298b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022992  cmp     rcx, rdi
0x180022995  jz      short loc_1800229B1
0x180022997  lea     edx, [rsi+5Bh]
0x18002299a  mov     rcx, [rcx+10h]
0x18002299e  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800229a5  call    WPP_SF_
0x1800229aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229b1  inc     r15d
0x1800229b4  mov     [rsp+140h+var_DC], r15d
0x1800229b9  jmp     loc_180022D4F
0x1800229be  mov     rdx, r14; pPrevCertContext
0x1800229c1  mov     rcx, r10; hCertStore
0x1800229c4  call    cs:__imp_CertEnumCertificatesInStore
0x1800229cb  nop     dword ptr [rax+rax+00h]
0x1800229d0  mov     r14, rax
0x1800229d3  test    rax, rax
0x1800229d6  jz      loc_180022D8A
0x1800229dc  inc     [rsp+140h+var_F0]
0x1800229e0  test    r13d, r13d
0x1800229e3  jnz     short loc_180022A14
0x1800229e5  mov     eax, [rbp+40h+arg_48]
0x1800229eb  xor     r9d, r9d; int
0x1800229ee  mov     r8d, r12d; int
0x1800229f1  mov     dword ptr [rsp+140h+pvPara], eax; int
0x1800229f5  xor     edx, edx; struct _CTL_USAGE *
0x1800229f7  mov     rcx, r14; pCertContext
0x1800229fa  call    ?FCheckUsage@@YAHPEBU_CERT_CONTEXT@@PEAU_CTL_USAGE@@HHH@Z; FCheckUsage(_CERT_CONTEXT const *,_CTL_USAGE *,int,int,int)
0x1800229ff  test    eax, eax
0x180022a01  jnz     short loc_180022A14
0x180022a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a0a  cmp     rcx, rdi
0x180022a0d  jz      short loc_1800229B1
0x180022a0f  lea     edx, [rax+56h]
0x180022a12  jmp     short loc_18002299A
0x180022a14  mov     rcx, r14; struct _CERT_CONTEXT *
0x180022a17  call    ?FCheckTimeValidity@@YAHPEBU_CERT_CONTEXT@@@Z; FCheckTimeValidity(_CERT_CONTEXT const *)
0x180022a1c  test    eax, eax
0x180022a1e  jnz     short loc_180022A34
0x180022a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a27  cmp     rcx, rdi
0x180022a2a  jz      short loc_1800229B1
0x180022a2c  lea     edx, [rax+57h]
0x180022a2f  jmp     loc_18002299A
0x180022a34  mov     rcx, r14; struct _CERT_CONTEXT *
0x180022a37  call    ?FCheckGenuineWindowsPhoneCert@@YAHPEBU_CERT_CONTEXT@@@Z; FCheckGenuineWindowsPhoneCert(_CERT_CONTEXT const *)
0x180022a3c  test    eax, eax
0x180022a3e  jz      short loc_180022A5A
0x180022a40  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a47  cmp     rcx, rdi
0x180022a4a  jz      loc_1800229B1
0x180022a50  mov     edx, 5Ch ; '\'
0x180022a55  jmp     loc_18002299A
0x180022a5a  test    r13d, r13d
0x180022a5d  jnz     short loc_180022A97
0x180022a5f  test    r12d, r12d
0x180022a62  jnz     short loc_180022A97
0x180022a64  mov     rax, [rbp+40h+var_A0]
0x180022a68  mov     r8d, esi; int
0x180022a6b  mov     edx, [rbp+40h+arg_48]; int
0x180022a71  neg     rax
0x180022a74  lea     rax, [rbp+40h+var_B0]
0x180022a78  mov     rcx, r14; pCertContext
0x180022a7b  sbb     r9, r9
0x180022a7e  and     r9, rax; int *
0x180022a81  call    ?FCheckSCardCertAndCanOpenSilentContext@@YAHPEBU_CERT_CONTEXT@@HHPEAH@Z; FCheckSCardCertAndCanOpenSilentContext(_CERT_CONTEXT const *,int,int,int *)
0x180022a86  test    eax, eax
0x180022a88  jz      short loc_180022A97
0x180022a8a  inc     r15d
0x180022a8d  mov     [rsp+140h+var_DC], r15d
0x180022a92  jmp     loc_180022D48
0x180022a97  mov     edx, 58h ; 'X'; uBytes
0x180022a9c  lea     ecx, [rdx-18h]; uFlags
0x180022a9f  call    cs:__imp_LocalAlloc
0x180022aa6  nop     dword ptr [rax+rax+00h]
0x180022aab  mov     rsi, rax
0x180022aae  test    rax, rax
0x180022ab1  jnz     short loc_180022AFC
0x180022ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180022aba  cmp     rcx, rdi
0x180022abd  jz      short loc_180022AEF
0x180022abf  call    cs:__imp_GetLastError
0x180022ac6  nop     dword ptr [rax+rax+00h]
0x180022acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ad2  lea     edx, [rsi+5Dh]
0x180022ad5  mov     r9d, eax
0x180022ad8  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180022adf  mov     rcx, [rcx+10h]
0x180022ae3  call    WPP_SF_d
0x180022ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180022aef  inc     [rsp+140h+var_E8]
0x180022af3  mov     esi, [rsp+140h+var_D0]
0x180022af7  jmp     loc_180022D4F
0x180022afc  lea     r8, [rax+28h]; unsigned __int16 **
0x180022b00  xor     edx, edx; dwFlags
0x180022b02  mov     rcx, r14; pCertContext
0x180022b05  call    ?FGetFriendlyName@@YAHPEBU_CERT_CONTEXT@@KPEAPEAG@Z; FGetFriendlyName(_CERT_CONTEXT const *,ulong,ushort * *)
0x180022b0a  lea     r13, [rsi+20h]
0x180022b0e  test    r12d, r12d
0x180022b11  jnz     short loc_180022B2B
0x180022b13  mov     rdx, r13; unsigned __int16 **
0x180022b16  mov     rcx, r14; struct _CERT_CONTEXT *
0x180022b19  call    ?FUserCertToStr@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; FUserCertToStr(_CERT_CONTEXT const *,ushort * *)
0x180022b1e  test    eax, eax
0x180022b20  jz      short loc_180022B2B
0x180022b22  mov     dword ptr [rsi+50h], 1
0x180022b29  jmp     short loc_180022B40
0x180022b2b  mov     r8, r13; unsigned __int16 **
0x180022b2e  xor     edx, edx; dwFlags
0x180022b30  mov     rcx, r14; pCertContext
0x180022b33  call    ?FGetFriendlyName@@YAHPEBU_CERT_CONTEXT@@KPEAPEAG@Z; FGetFriendlyName(_CERT_CONTEXT const *,ulong,ushort * *)
0x180022b38  test    eax, eax
0x180022b3a  jz      loc_180022CB7
  ... truncated ...
```
