# CreateCertList(int,int,int,_EAPTLS_CERT_NODE * *,_EAPTLS_CERT_NODE * *,ulong,_EAPTLS_HASH *,ushort const *,ulong *,int,_EAPTLS_FILTER_PROP *,ulong *)

- ea: `0x180020624`
- end: `0x180020e8e`
- name: `?CreateCertList@@YAXHHHPEAPEAU_EAPTLS_CERT_NODE@@0KPEAU_EAPTLS_HASH@@PEBGPEAKHPEAU_EAPTLS_FILTER_PROP@@3@Z`
- size: `2154`
- prototype: `void __usercall(int@<ecx>, int@<edx>, int@<r8d>, struct _EAPTLS_CERT_NODE **@<r9>, struct _EAPTLS_CERT_NODE **, unsigned int, struct _EAPTLS_HASH *, const unsigned __int16 *, unsigned int *, int, struct _EAPTLS_FILTER_PROP *, unsigned int *)`
- caller_count: `5`
- callee_count: `18`
- tags: ``

## callers

- `0x1800136f0`
- `0x180066c8c`
- `0x18006a0e0`
- `0x18006c11c`
- `0x18006c46c`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18001489c`
- `0x18001fd50`
- `0x180020624`
- `0x18002c710`
- `0x18002c764`
- `0x180035680`
- `0x180065ac4`
- `0x1800682e0`
- `0x180069380`
- `0x180069408`
- `0x180069510`
- `0x180069634`
- `0x1800698ac`
- `0x180069e80`
- `0x18006c9c0`
- `0x18006dc10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020a25`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020a25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c7d`
- `CRYPT32!CertFreeCertificateChainList` at `0x180020e1c`
- `CRYPT32!CertFreeCertificateChainList` at `0x180020e1c`
- `CRYPT32!CertCloseStore` at `0x180020e36`
- `CRYPT32!CertCloseStore` at `0x180020e36`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180020950`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180020950`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180020b90`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180020b90`
- `CRYPT32!CertOpenStore` at `0x180020710`
- `CRYPT32!CertOpenStore` at `0x180020710`
- `CRYPT32!CertSelectCertificateChains` at `0x1800207eb`
- `CRYPT32!CertSelectCertificateChains` at `0x1800207eb`
- `CRYPT32!CertFreeCertificateChain` at `0x180020e07`
- `CRYPT32!CertFreeCertificateChain` at `0x180020e07`

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
        if ( (unsigned int)FCertToStr(pCertContext, 1u) )
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
        v47 = (const char *)&dword_180081A9C;
      if ( !a3 )
        v48 = (const char *)&dword_180081A9C;
      WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)&dword_180081A9C, v34, (_DWORD)v48, (__int64)v47);
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
0x180020624  push    rbp
0x180020626  push    rbx
0x180020627  push    rsi
0x180020628  push    rdi
0x180020629  push    r12
0x18002062b  push    r13
0x18002062d  push    r14
0x18002062f  push    r15
0x180020631  lea     rbp, [rsp-8]
0x180020636  sub     rsp, 108h
0x18002063d  mov     rax, cs:__security_cookie
0x180020644  xor     rax, rsp
0x180020647  mov     [rbp+40h+var_48], rax
0x18002064b  mov     rax, [rbp+40h+arg_50]
0x180020652  xor     esi, esi
0x180020654  mov     r12d, ecx
0x180020657  mov     [rbp+40h+var_AC], ecx
0x18002065a  mov     rcx, [rbp+40h+arg_20]
0x18002065e  xor     r14d, r14d
0x180020661  mov     [rbp+40h+var_88], rcx
0x180020665  xor     r15d, r15d
0x180020668  mov     rcx, [rbp+40h+arg_30]
0x18002066f  mov     edi, r8d
0x180020672  mov     [rbp+40h+var_80], rcx
0x180020676  mov     rcx, [rbp+40h+arg_40]
0x18002067d  mov     [rbp+40h+var_70], rcx
0x180020681  mov     rcx, [rbp+40h+arg_58]
0x180020688  mov     [rsp+140h+var_CC], r8d
0x18002068d  mov     r8, [rbp+40h+arg_38]
0x180020694  mov     [rbp+40h+var_A0], rcx
0x180020698  mov     [rbp+40h+var_78], r9
0x18002069c  mov     [rbp+40h+var_A4], edx
0x18002069f  mov     [rbp+40h+var_90], rax
0x1800206a3  mov     [rbp+40h+var_68], r8
0x1800206a7  mov     [rbp+40h+var_98], 0
0x1800206af  mov     [rbp+40h+var_A8], 0
0x1800206b6  mov     [rsp+140h+var_D0], esi
0x1800206ba  mov     [rbp+40h+var_B0], 1
0x1800206c1  mov     [rsp+140h+var_C8], esi
0x1800206c5  mov     [rbp+40h+prgpSelection], rsi
0x1800206c9  mov     [rsp+140h+var_E0], esi
0x1800206cd  mov     [rsp+140h+var_E8], r14d
0x1800206d2  mov     [rsp+140h+var_E4], esi
0x1800206d6  mov     [rsp+140h+var_DC], r15d
0x1800206db  mov     [rsp+140h+var_F0], esi
0x1800206df  test    rax, rax
0x1800206e2  jz      short loc_1800206EE
0x1800206e4  movzx   esi, word ptr [rax]
0x1800206e7  and     esi, 10h
0x1800206ea  mov     [rsp+140h+var_D0], esi
0x1800206ee  test    r12d, r12d
0x1800206f1  jnz     short loc_1800206FD
0x1800206f3  mov     r9d, 18000h
0x1800206f9  test    edx, edx
0x1800206fb  jz      short loc_180020703
0x1800206fd  mov     r9d, 28000h; dwFlags
0x180020703  xor     edx, edx; dwEncodingType
0x180020705  mov     [rsp+140h+pvPara], r8; pvPara
0x18002070a  xor     r8d, r8d; hCryptProv
0x18002070d  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180020710  call    cs:__imp_CertOpenStore
0x180020716  mov     [rsp+140h+hCertStore], rax
0x18002071b  mov     r10, rax
0x18002071e  test    rax, rax
0x180020721  jnz     short loc_18002076B
0x180020723  mov     ebx, 80420010h
0x180020728  lea     rdi, WPP_GLOBAL_Control
0x18002072f  cmp     cs:WPP_GLOBAL_Control, rdi
0x180020736  jz      short loc_18002075D
0x180020738  call    cs:__imp_GetLastError
0x18002073e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020745  mov     edx, 53h ; 'S'
0x18002074a  mov     r9d, eax
0x18002074d  mov     rcx, [rcx+10h]
0x180020751  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180020758  call    WPP_SF_d
0x18002075d  mov     edx, r14d
0x180020760  mov     r8d, edx
0x180020763  mov     r10d, edx
0x180020766  jmp     loc_180020D75
0x18002076b  xor     ebx, ebx
0x18002076d  test    edi, edi
0x18002076f  jnz     loc_18002082A
0x180020775  test    r12d, r12d
0x180020778  jnz     loc_18002082A
0x18002077e  mov     eax, cs:?g_selectSelfSignedCert@@3HA; int g_selectSelfSignedCert
0x180020784  neg     eax
0x180020786  mov     qword ptr [rbp+40h+var_B8], rbx
0x18002078a  lea     rax, [rbp+40h+var_B8]
0x18002078e  mov     dword ptr [rbp+40h+rgpCriteria], 1
0x180020795  sbb     edx, edx
0x180020797  mov     dword ptr [rbp+40h+rgpCriteria+4], 1
0x18002079e  and     edx, 0FFFFFFFCh
0x1800207a1  mov     qword ptr [rbp+40h+rgpCriteria+8], rax
0x1800207a5  add     edx, 84h; dwFlags
0x1800207ab  test    esi, esi
0x1800207ad  jnz     short loc_1800207C4
0x1800207af  lea     rax, Buf1; "1.3.6.1.5.5.7.3.2"
0x1800207b6  mov     qword ptr [rbp+40h+var_B8], rax
0x1800207ba  lea     r9d, [rbx+1]
0x1800207be  lea     rax, [rbp+40h+rgpCriteria]
0x1800207c2  jmp     short loc_1800207C9
0x1800207c4  xor     eax, eax
0x1800207c6  xor     r9d, r9d; cCriteria
0x1800207c9  lea     rcx, [rbp+40h+prgpSelection]
0x1800207cd  xor     r8d, r8d; pChainParameters
0x1800207d0  mov     [rsp+140h+pprgpSelection], rcx; pprgpSelection
0x1800207d5  lea     rcx, [rsp+140h+var_C8]
0x1800207da  mov     [rsp+140h+pcSelection], rcx; pcSelection
0x1800207df  xor     ecx, ecx; pSelectionContext
0x1800207e1  mov     [rsp+140h+hStore], r10; hStore
0x1800207e6  mov     [rsp+140h+pvPara], rax; rgpCriteria
0x1800207eb  call    cs:__imp_CertSelectCertificateChains
0x1800207f1  test    eax, eax
0x1800207f3  jnz     short loc_1800207FD
0x1800207f5  call    cs:__imp_GetLastError
0x1800207fb  mov     ebx, eax
0x1800207fd  test    ebx, ebx
0x1800207ff  jz      short loc_180020825
0x180020801  mov     rcx, cs:WPP_GLOBAL_Control
0x180020808  lea     rdi, WPP_GLOBAL_Control
0x18002080f  cmp     rcx, rdi
0x180020812  jz      loc_18002075D
0x180020818  mov     edx, 54h ; 'T'
0x18002081d  mov     r9d, ebx
0x180020820  jmp     loc_18002074D
0x180020825  mov     r10, [rsp+140h+hCertStore]
0x18002082a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020831  lea     rdi, WPP_GLOBAL_Control
0x180020838  xor     r13d, r13d
0x18002083b  xor     r8d, r8d
0x18002083e  mov     [rsp+140h+var_C4], r13d
0x180020843  mov     qword ptr [rbp+40h+rgpCriteria], r13
0x180020847  mov     r13d, [rsp+140h+var_CC]
0x18002084c  mov     [rsp+140h+var_EC], r8d
0x180020851  test    r13d, r13d
0x180020854  jnz     loc_18002094A
0x18002085a  test    r12d, r12d
0x18002085d  jnz     loc_18002094A
0x180020863  cmp     rcx, rdi
0x180020866  jz      short loc_180020888
0x180020868  mov     rcx, [rcx+10h]
0x18002086c  lea     edx, [r13+58h]
0x180020870  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180020877  call    WPP_SF_
0x18002087c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020883  mov     r8d, [rsp+140h+var_EC]
0x180020888  mov     rdx, [rbp+40h+prgpSelection]
0x18002088c  test    rdx, rdx
0x18002088f  jz      loc_180020CAB
0x180020895  mov     eax, [rsp+140h+var_C8]
0x180020899  test    eax, eax
0x18002089b  jz      loc_180020CAB
0x1800208a1  cmp     r8d, eax
0x1800208a4  jz      loc_180020CAB
0x1800208aa  inc     [rsp+140h+var_F0]
0x1800208ae  mov     eax, r8d
0x1800208b1  inc     r8d
0x1800208b4  mov     [rsp+140h+var_EC], r8d
0x1800208b9  mov     r14, [rdx+rax*8]
0x1800208bd  mov     qword ptr [rbp+40h+rgpCriteria], r14
0x1800208c1  cmp     rcx, rdi
0x1800208c4  jz      short loc_1800208DB
0x1800208c6  mov     rcx, [rcx+10h]
0x1800208ca  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800208d1  mov     edx, 5Ah ; 'Z'
0x1800208d6  call    WPP_SF_
0x1800208db  mov     rax, [r14+10h]
0x1800208df  mov     rcx, [rax]
0x1800208e2  mov     rax, [rcx+10h]
0x1800208e6  mov     rcx, [rax]
0x1800208e9  mov     r14, [rcx+8]
0x1800208ed  test    esi, esi
0x1800208ef  jnz     loc_1800209BA
0x1800208f5  mov     eax, [rbp+40h+arg_48]
0x1800208fb  xor     r9d, r9d; int
0x1800208fe  xor     r8d, r8d; int
0x180020901  mov     dword ptr [rsp+140h+pvPara], eax; int
0x180020905  xor     edx, edx; struct _CTL_USAGE *
0x180020907  mov     rcx, r14; pCertContext
0x18002090a  call    ?FCheckUsage@@YAHPEBU_CERT_CONTEXT@@PEAU_CTL_USAGE@@HHH@Z; FCheckUsage(_CERT_CONTEXT const *,_CTL_USAGE *,int,int,int)
0x18002090f  test    eax, eax
0x180020911  jnz     loc_1800209BA
0x180020917  mov     rcx, cs:WPP_GLOBAL_Control
0x18002091e  cmp     rcx, rdi
0x180020921  jz      short loc_18002093D
0x180020923  lea     edx, [rsi+5Bh]
0x180020926  mov     rcx, [rcx+10h]
0x18002092a  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180020931  call    WPP_SF_
0x180020936  mov     rcx, cs:WPP_GLOBAL_Control
0x18002093d  inc     r15d
0x180020940  mov     [rsp+140h+var_DC], r15d
0x180020945  jmp     loc_180020C9C
0x18002094a  mov     rdx, r14; pPrevCertContext
0x18002094d  mov     rcx, r10; hCertStore
0x180020950  call    cs:__imp_CertEnumCertificatesInStore
0x180020956  mov     r14, rax
0x180020959  test    rax, rax
0x18002095c  jz      loc_180020CD7
0x180020962  inc     [rsp+140h+var_F0]
0x180020966  test    r13d, r13d
0x180020969  jnz     short loc_18002099A
0x18002096b  mov     eax, [rbp+40h+arg_48]
0x180020971  xor     r9d, r9d; int
0x180020974  mov     r8d, r12d; int
0x180020977  mov     dword ptr [rsp+140h+pvPara], eax; int
0x18002097b  xor     edx, edx; struct _CTL_USAGE *
0x18002097d  mov     rcx, r14; pCertContext
0x180020980  call    ?FCheckUsage@@YAHPEBU_CERT_CONTEXT@@PEAU_CTL_USAGE@@HHH@Z; FCheckUsage(_CERT_CONTEXT const *,_CTL_USAGE *,int,int,int)
0x180020985  test    eax, eax
0x180020987  jnz     short loc_18002099A
0x180020989  mov     rcx, cs:WPP_GLOBAL_Control
0x180020990  cmp     rcx, rdi
0x180020993  jz      short loc_18002093D
0x180020995  lea     edx, [rax+56h]
0x180020998  jmp     short loc_180020926
0x18002099a  mov     rcx, r14; struct _CERT_CONTEXT *
0x18002099d  call    ?FCheckTimeValidity@@YAHPEBU_CERT_CONTEXT@@@Z; FCheckTimeValidity(_CERT_CONTEXT const *)
0x1800209a2  test    eax, eax
0x1800209a4  jnz     short loc_1800209BA
0x1800209a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209ad  cmp     rcx, rdi
0x1800209b0  jz      short loc_18002093D
0x1800209b2  lea     edx, [rax+57h]
0x1800209b5  jmp     loc_180020926
0x1800209ba  mov     rcx, r14; struct _CERT_CONTEXT *
0x1800209bd  call    ?FCheckGenuineWindowsPhoneCert@@YAHPEBU_CERT_CONTEXT@@@Z; FCheckGenuineWindowsPhoneCert(_CERT_CONTEXT const *)
0x1800209c2  test    eax, eax
0x1800209c4  jz      short loc_1800209E0
0x1800209c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209cd  cmp     rcx, rdi
0x1800209d0  jz      loc_18002093D
0x1800209d6  mov     edx, 5Ch ; '\'
0x1800209db  jmp     loc_180020926
0x1800209e0  test    r13d, r13d
0x1800209e3  jnz     short loc_180020A1D
0x1800209e5  test    r12d, r12d
0x1800209e8  jnz     short loc_180020A1D
0x1800209ea  mov     rax, [rbp+40h+var_A0]
0x1800209ee  mov     r8d, esi; int
0x1800209f1  mov     edx, [rbp+40h+arg_48]; int
0x1800209f7  neg     rax
0x1800209fa  lea     rax, [rbp+40h+var_B0]
0x1800209fe  mov     rcx, r14; pCertContext
0x180020a01  sbb     r9, r9
0x180020a04  and     r9, rax; int *
0x180020a07  call    ?FCheckSCardCertAndCanOpenSilentContext@@YAHPEBU_CERT_CONTEXT@@HHPEAH@Z; FCheckSCardCertAndCanOpenSilentContext(_CERT_CONTEXT const *,int,int,int *)
0x180020a0c  test    eax, eax
0x180020a0e  jz      short loc_180020A1D
0x180020a10  inc     r15d
0x180020a13  mov     [rsp+140h+var_DC], r15d
0x180020a18  jmp     loc_180020C95
0x180020a1d  mov     edx, 58h ; 'X'; uBytes
0x180020a22  lea     ecx, [rdx-18h]; uFlags
0x180020a25  call    cs:__imp_LocalAlloc
0x180020a2b  mov     rsi, rax
0x180020a2e  test    rax, rax
0x180020a31  jnz     short loc_180020A76
0x180020a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a3a  cmp     rcx, rdi
0x180020a3d  jz      short loc_180020A69
0x180020a3f  call    cs:__imp_GetLastError
0x180020a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a4c  lea     edx, [rsi+5Dh]
0x180020a4f  mov     r9d, eax
0x180020a52  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180020a59  mov     rcx, [rcx+10h]
0x180020a5d  call    WPP_SF_d
0x180020a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a69  inc     [rsp+140h+var_E8]
0x180020a6d  mov     esi, [rsp+140h+var_D0]
0x180020a71  jmp     loc_180020C9C
0x180020a76  lea     r8, [rax+28h]; unsigned __int16 **
0x180020a7a  xor     edx, edx; dwFlags
0x180020a7c  mov     rcx, r14; pCertContext
0x180020a7f  call    ?FGetFriendlyName@@YAHPEBU_CERT_CONTEXT@@KPEAPEAG@Z; FGetFriendlyName(_CERT_CONTEXT const *,ulong,ushort * *)
0x180020a84  lea     r13, [rsi+20h]
0x180020a88  test    r12d, r12d
0x180020a8b  jnz     short loc_180020AA5
0x180020a8d  mov     rdx, r13; unsigned __int16 **
0x180020a90  mov     rcx, r14; struct _CERT_CONTEXT *
0x180020a93  call    ?FUserCertToStr@@YAHPEBU_CERT_CONTEXT@@PEAPEAG@Z; FUserCertToStr(_CERT_CONTEXT const *,ushort * *)
0x180020a98  test    eax, eax
0x180020a9a  jz      short loc_180020AA5
0x180020a9c  mov     dword ptr [rsi+50h], 1
0x180020aa3  jmp     short loc_180020ABA
0x180020aa5  mov     r8, r13; unsigned __int16 **
0x180020aa8  xor     edx, edx; dwFlags
0x180020aaa  mov     rcx, r14; pCertContext
0x180020aad  call    ?FGetFriendlyName@@YAHPEBU_CERT_CONTEXT@@KPEAPEAG@Z; FGetFriendlyName(_CERT_CONTEXT const *,ulong,ushort * *)
0x180020ab2  test    eax, eax
0x180020ab4  jz      loc_180020C22
0x180020aba  mov     edx, 1; dwFlags
0x180020abf  lea     r12, [rsi+30h]
0x180020ac3  mov     r9, r12
0x180020ac6  mov     r8d, edx
0x180020ac9  mov     rcx, r14; pCertContext
0x180020acc  call    FCertToStr
0x180020ad1  test    eax, eax
  ... truncated ...
```
