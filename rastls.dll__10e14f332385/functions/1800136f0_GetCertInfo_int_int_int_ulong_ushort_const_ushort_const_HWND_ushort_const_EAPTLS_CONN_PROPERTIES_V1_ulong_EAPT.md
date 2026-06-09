# GetCertInfo(int,int,int,ulong,ushort const *,ushort const *,HWND__ *,ushort const *,_EAPTLS_CONN_PROPERTIES_V1 *,ulong,_EAPTLS_USER_PROPERTIES * *,ushort * *,ulong *,_CERT_CONTEXT const * * *)

- ea: `0x1800136f0`
- end: `0x180014893`
- name: `?GetCertInfo@@YAKHHHKPEBG0PEAUHWND__@@0PEAU_EAPTLS_CONN_PROPERTIES_V1@@KPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAPEAGPEAKPEAPEAPEBU_CERT_CONTEXT@@@Z`
- size: `4515`
- prototype: `unsigned int __fastcall(int, int, int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, HWND hWndParent, const unsigned __int16 *, DWORD pcbData, unsigned int, struct _EAPTLS_USER_PROPERTIES **, unsigned __int16 **, unsigned int *, const struct _CERT_CONTEXT ***)`
- caller_count: `1`
- callee_count: `30`
- tags: ``

## callers

- `0x180071b98`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f350`
- `0x1800136f0`
- `0x18001489c`
- `0x1800154a8`
- `0x180020624`
- `0x18002131c`
- `0x18002c710`
- `0x180031e88`
- `0x18003332c`
- `0x180036254`
- `0x180036930`
- `0x18005a7ac`
- `0x180069408`
- `0x180069634`
- `0x18006c7c0`
- `0x18006c948`
- `0x18006eb30`
- `0x18006ee08`
- `0x18006f378`
- `0x18006f504`
- `0x18006f550`
- `0x18006f7a8`
- `0x18006fcd0`
- `0x18007009c`
- `0x180070e28`
- `0x180070e88`
- `0x180070f9c`
- `0x180071f14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180013cb4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180014177`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180013cb4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180014177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014719`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013c6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014117`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800141ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013c6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014117`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800141ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001391a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013924`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001392e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001393a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800138f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001391a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013924`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001392e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001393a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e66`
- `CRYPT32!CertCloseStore` at `0x180013861`
- `CRYPT32!CertCloseStore` at `0x180013861`
- `CRYPT32!CertFindCertificateInStore` at `0x180013eda`
- `CRYPT32!CertFindCertificateInStore` at `0x180013eda`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180013dfe`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180013f2e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180013dfe`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180013f2e`
- `CRYPT32!CertFreeCertificateContext` at `0x180013851`
- `CRYPT32!CertFreeCertificateContext` at `0x180013851`
- `CRYPT32!CertOpenStore` at `0x180013d24`
- `CRYPT32!CertOpenStore` at `0x180013d24`
- `CRYPT32!CertGetNameStringW` at `0x1800140da`
- `CRYPT32!CertGetNameStringW` at `0x1800141dc`
- `CRYPT32!CertGetNameStringW` at `0x1800140da`
- `CRYPT32!CertGetNameStringW` at `0x1800141dc`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_SelectCertificate` at `0x1800147a8`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_SelectCertificate` at `0x1800147a8`
- `rtutils!TraceDumpExA` at `0x1800139a4`
- `rtutils!TraceDumpExA` at `0x1800139a4`

## pseudocode

```c
__int64 __fastcall GetCertInfo(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        HWND hWndParent,
        const unsigned __int16 *a8,
        __int64 pcbData,
        unsigned int a10,
        struct _EAPTLS_USER_PROPERTIES **a11,
        unsigned __int16 **a12,
        unsigned int *a13,
        const struct _CERT_CONTEXT ***a14)
{
  int v14; // r15d
  int v15; // ebx
  HCERTSTORE v17; // r14
  WCHAR *v18; // r13
  struct _EAPTLS_CONTROL_BLOCK *v19; // rsi
  int v20; // eax
  __int64 v21; // rdi
  int v22; // ecx
  int v23; // edx
  DWORD v24; // r8d
  DWORD DefaultClientMachineCert; // esi
  struct _EAPTLS_USER_PROPERTIES **v26; // r15
  DWORD v27; // eax
  HLOCAL *v28; // rbx
  HLOCAL *v29; // rcx
  _QWORD *v30; // rcx
  _QWORD *v31; // rbx
  HLOCAL *v32; // rbx
  HLOCAL *v33; // rcx
  BOOL v35; // r10d
  __int64 v36; // r11
  __int64 v37; // rax
  struct _EAPTLS_USER_PROPERTIES *v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rdx
  bool v42; // zf
  BYTE *v43; // r9
  unsigned int v44; // ecx
  _WORD *v45; // r8
  DWORD v46; // edx
  __int64 v47; // rax
  DWORD v48; // eax
  HLOCAL *v49; // rcx
  unsigned int IdentityAndHashFromScard; // eax
  struct _EAPTLS_CONTROL_BLOCK *v51; // rcx
  __int64 v52; // rdx
  HLOCAL *v53; // rcx
  struct _EAPTLS_USER_PROPERTIES *v54; // rdi
  _WORD *v55; // rcx
  unsigned __int16 **v56; // rbx
  __int64 v57; // rsi
  unsigned __int16 *v58; // rax
  DWORD LastError; // eax
  HLOCAL *v60; // r8
  int v61; // edx
  DWORD v62; // eax
  struct _EAPTLS_HASH *v63; // rdi
  PCCERT_CONTEXT CertificateInStore; // rax
  struct _EAPTLS_CONTROL_BLOCK *v65; // rcx
  __int64 v66; // rdx
  int *v67; // r9
  _WORD *v68; // rcx
  unsigned int v69; // ebx
  DWORD v70; // r14d
  DWORD NameStringW; // eax
  __int64 v72; // rsi
  __int64 v73; // rax
  __int64 v74; // rbx
  WCHAR *v75; // rax
  DWORD v76; // eax
  struct _EAPTLS_CONTROL_BLOCK *v77; // rcx
  __int64 v78; // rdx
  WCHAR *v79; // rax
  unsigned int *v80; // rdx
  unsigned int PasswdAndUserBlob; // eax
  struct _EAPTLS_CONTROL_BLOCK *v82; // rcx
  __int64 v83; // rdx
  HLOCAL *v84; // rcx
  int v85; // eax
  _QWORD *v86; // rdx
  int v87; // r8d
  HLOCAL v88; // rax
  unsigned int v89; // ebx
  int v90; // ecx
  unsigned int v91; // eax
  unsigned int v92; // eax
  int v93; // r8d
  unsigned int v94; // eax
  __int64 v95; // rcx
  __int64 v96; // rax
  __int64 v97; // xmm1_8
  const CERT_CONTEXT *CertContextFromNode; // rax
  HWND v99; // rbx
  __int64 v100; // rax
  int v101; // r12d
  unsigned __int16 **v102; // rdx
  int dwGroupSize; // [rsp+20h] [rbp-E0h]
  unsigned int *bAddressPrefix; // [rsp+28h] [rbp-D8h]
  const struct _CERT_CONTEXT ***lpszPrefix; // [rsp+30h] [rbp-D0h]
  int v106; // [rsp+38h] [rbp-C8h]
  unsigned int *v107; // [rsp+48h] [rbp-B8h]
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v109; // [rsp+68h] [rbp-98h] BYREF
  struct _EAPTLS_USER_PROPERTIES *v110; // [rsp+70h] [rbp-90h]
  HLOCAL hMem[2]; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v112[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v113; // [rsp+A0h] [rbp-60h]
  __int128 v114; // [rsp+B0h] [rbp-50h]
  __int128 v115; // [rsp+C0h] [rbp-40h]
  __int128 v116; // [rsp+D0h] [rbp-30h]
  __int128 v117; // [rsp+E0h] [rbp-20h]
  __int64 v118; // [rsp+F0h] [rbp-10h]
  HCERTSTORE v119; // [rsp+100h] [rbp+0h]
  HLOCAL v120[2]; // [rsp+108h] [rbp+8h] BYREF
  HLOCAL v121[2]; // [rsp+118h] [rbp+18h]
  DWORD dwType[6]; // [rsp+128h] [rbp+28h]
  __int128 pvFindPara; // [rsp+140h] [rbp+40h] BYREF
  int v124; // [rsp+1A0h] [rbp+A0h]
  unsigned int SelectedHashesAndEKUList; // [rsp+1A8h] [rbp+A8h]
  unsigned int v127; // [rsp+1B8h] [rbp+B8h] BYREF

  LODWORD(a8) = 1;
  pCertContext = 0;
  v14 = a4 & 1;
  v109 = 0;
  LODWORD(a14) = v14;
  v15 = a4 & 4;
  v118 = 0;
  LODWORD(a13) = 0;
  v17 = 0;
  v127 = 0;
  pvFindPara = 0;
  v18 = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  *(_OWORD *)v120 = 0;
  *(_OWORD *)v121 = 0;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v19 = WPP_GLOBAL_Control;
  }
  memset_0(hMem, 0, 0x78u);
  v20 = (int)hMem[0];
  v21 = pcbData;
  v22 = *(_DWORD *)(pcbData + 8);
  LODWORD(a5) = v22 & 8;
  if ( (v22 & 8) != 0 )
    v20 = 1;
  LODWORD(hMem[0]) = v20;
  v23 = (v22 & 8) != 0;
  *((_QWORD *)&v113 + 1) = a6;
  if ( v14 || (a4 & 0x20) != 0 )
  {
    v24 = 163840;
  }
  else
  {
    v23 |= 2u;
    v24 = 98304;
    LODWORD(hMem[0]) = v23;
  }
  LODWORD(pcbData) = v24;
  if ( (v22 & 0x10) != 0 )
    LODWORD(hMem[0]) = v23 | 4;
  if ( v15 && (v22 & 1) != 0 )
  {
    DefaultClientMachineCert = 785;
    goto LABEL_14;
  }
  SelectedHashesAndEKUList = 0;
  v35 = 0;
  LODWORD(a6) = 0;
  v36 = -1;
  v37 = *(unsigned int *)(v21 + 12);
  v38 = *a11;
  v124 = 0;
  v110 = *a11;
  v39 = 3 * v37;
  v40 = -1;
  v41 = v21 + 8 * v39;
  do
    v42 = *(_WORD *)(v41 + 2 * v40++ + 18) == 0;
  while ( !v42 );
  v43 = (BYTE *)(v41 + 18 + 2 * v40);
  v44 = v21 + *(_DWORD *)(v21 + 4) - (_DWORD)v43;
  if ( v44 >= 6 && *(_WORD *)v43 == 254 )
  {
    v45 = (_WORD *)(v41 + 18 + 2 * v40);
    v46 = 0;
    do
    {
      if ( (unsigned __int16)(*v45 - 250) > 4u )
        break;
      v47 = (unsigned __int16)v45[1];
      v46 += v47;
      v45 = (_WORD *)((char *)v45 + v47);
      v44 -= v47;
    }
    while ( v44 >= 6 );
    SelectedHashesAndEKUList = GetSelectedHashesAndEKUList(v43, v46, (struct _EAPTLS_FILTER_PROP *)v120);
    DefaultClientMachineCert = SelectedHashesAndEKUList;
    if ( SelectedHashesAndEKUList )
      goto LABEL_14;
    LODWORD(a6) = (__int64)v120[0] & 0x10;
    v35 = ((__int64)v120[0] & 0x10) != 0 || ((__int64)v120[0] & 1) != 0;
    v19 = WPP_GLOBAL_Control;
    v36 = -1;
    v24 = pcbData;
    v124 = v35;
  }
  if ( (*(_BYTE *)(v21 + 8) & 1) == 0 )
  {
    if ( (a4 & 0x20) != 0 )
    {
      v48 = 703;
      if ( v19 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)v19 + 2), 67, &WPP_c4e812f99669349517681909258710e2_Traceguids);
        DefaultClientMachineCert = 703;
        goto LABEL_50;
      }
LABEL_179:
      DefaultClientMachineCert = v48;
LABEL_180:
      v26 = a11;
      goto LABEL_15;
    }
    if ( v35 && g_OverrideSCardFilter )
      v35 = 0;
    v26 = a11;
    if ( (a4 & 2) != 0 )
    {
      if ( **((_WORD **)v38 + 5) )
      {
        DefaultClientMachineCert = 0;
LABEL_71:
        v54 = *v26;
        v55 = (_WORD *)*((_QWORD *)*v26 + 5);
        if ( !*v55 )
          goto LABEL_15;
        v56 = a12;
        if ( !a12 )
          goto LABEL_15;
        do
          v42 = v55[++v36] == 0;
        while ( !v42 );
        v57 = (unsigned int)(v36 + 1);
        v58 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v57);
        *v56 = v58;
        if ( v58 )
        {
          _o_wcscpy_s(v58, v57, *((_QWORD *)v54 + 5));
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_c4e812f99669349517681909258710e2_Traceguids, *v56);
          DefaultClientMachineCert = SelectedHashesAndEKUList;
          goto LABEL_15;
        }
        DefaultClientMachineCert = 14;
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_15;
        v52 = 69;
LABEL_66:
        WPP_SF_d(*((_QWORD *)v51 + 2), v52, &WPP_c4e812f99669349517681909258710e2_Traceguids, DefaultClientMachineCert);
        goto LABEL_15;
      }
      v49 = v120;
      if ( !v35 )
        v49 = 0;
      IdentityAndHashFromScard = GetIdentityAndHashFromScard(
                                   (DWORD)v49,
                                   a4,
                                   (struct _EAPTLS_CONN_PROPERTIES_V1 *)v21,
                                   hWndParent,
                                   dwGroupSize,
                                   (struct _CERT_CONTEXT *)v49,
                                   a3,
                                   a11,
                                   (struct _CERT_CONTEXT **)&pCertContext,
                                   v107);
      SelectedHashesAndEKUList = IdentityAndHashFromScard;
      DefaultClientMachineCert = IdentityAndHashFromScard;
      if ( IdentityAndHashFromScard )
      {
        if ( IdentityAndHashFromScard == -2146435060 || IdentityAndHashFromScard == -2146435026 )
          DefaultClientMachineCert = 703;
        goto LABEL_15;
      }
      if ( (*((_BYTE *)*v26 + 12) & 0xC) == 0 )
      {
        DefaultClientMachineCert = 703;
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_15;
        v52 = 68;
        goto LABEL_66;
      }
    }
    else
    {
      v53 = v120;
      if ( !v35 )
        v53 = 0;
      SelectedHashesAndEKUList = GetIdentityHashAndPinFromScard(
                                   (__int64)v53,
                                   a4,
                                   (struct _EAPTLS_CONN_PROPERTIES_V1 *)v21,
                                   hWndParent,
                                   a10,
                                   a11,
                                   (struct _CERT_CONTEXT *)v53,
                                   v106,
                                   (struct _CERT_CONTEXT **)&pCertContext,
                                   v107);
      DefaultClientMachineCert = SelectedHashesAndEKUList;
      if ( SelectedHashesAndEKUList )
        goto LABEL_15;
    }
    v36 = -1;
    goto LABEL_71;
  }
  if ( v35 )
  {
    if ( g_OverrideRegCertFilter )
      v35 = 0;
    v124 = v35;
  }
  v119 = CertOpenStore((LPCSTR)0xA, 1u, 0, v24, L"MY");
  v17 = v119;
  if ( !v119 )
  {
    DefaultClientMachineCert = -2143158256;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      LastError = GetLastError();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_c4e812f99669349517681909258710e2_Traceguids, LastError);
      v26 = a11;
      goto LABEL_15;
    }
    goto LABEL_50;
  }
  if ( (a4 & 0x20) != 0 )
  {
    v60 = v120;
    v61 = 0;
    if ( !v124 )
      v60 = 0;
    LOBYTE(v61) = (a4 & 0x14000) != 0;
    DefaultClientMachineCert = GetDefaultClientMachineCert(v119, v61, (struct _EAPTLS_FILTER_PROP *)v60, &pCertContext);
    if ( !DefaultClientMachineCert )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_c4e812f99669349517681909258710e2_Traceguids);
      *((_DWORD *)v38 + 4) = 20;
      if ( !CertGetCertificateContextProperty(pCertContext, 3u, (char *)v38 + 20, (DWORD *)v38 + 4) )
      {
        v62 = GetLastError();
        DefaultClientMachineCert = v62;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_c4e812f99669349517681909258710e2_Traceguids, v62);
      }
      **((_WORD **)v38 + 5) = 0;
      if ( (unsigned int)FMachineAuthCertToStr(pCertContext, (unsigned __int16 **)&v109)
        || (unsigned int)FCertToStr(pCertContext, 0) )
      {
        RasTlsFFormatMachineIdentity1((const unsigned __int16 *)v109, a12);
        LocalFree(v109);
      }
      else
      {
        v18 = (WCHAR *)v109;
      }
      v26 = a11;
      *a11 = v38;
      goto LABEL_15;
    }
LABEL_14:
    v26 = a11;
    goto LABEL_15;
  }
  v63 = (struct _EAPTLS_USER_PROPERTIES *)((char *)v38 + 16);
  LODWORD(pvFindPara) = *((_DWORD *)v38 + 4);
  pCertContext = 0;
  *((_QWORD *)&pvFindPara + 1) = (char *)v38 + 20;
  while ( 1 )
  {
    CertificateInStore = CertFindCertificateInStore(v17, 1u, 0, 0x10000u, &pvFindPara, pCertContext);
    pCertContext = CertificateInStore;
    if ( !CertificateInStore )
      break;
    LODWORD(pcbData) = 0;
    if ( (unsigned int)FCheckTimeValidity(CertificateInStore) )
    {
      if ( !CertGetCertificateContextProperty(pCertContext, 0x13u, 0, (DWORD *)&pcbData) )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_c4e812f99669349517681909258710e2_Traceguids);
        DefaultClientMachineCert = 0;
        goto LABEL_114;
      }
      v65 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v66 = 76;
LABEL_110:
        WPP_SF_(*((_QWORD *)v65 + 2), v66, &WPP_c4e812f99669349517681909258710e2_Traceguids);
      }
    }
    else
    {
      v65 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v66 = 75;
        goto LABEL_110;
      }
    }
  }
  DefaultClientMachineCert = GetLastError();
  SelectedHashesAndEKUList = DefaultClientMachineCert;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      74,
      &WPP_c4e812f99669349517681909258710e2_Traceguids,
      DefaultClientMachineCert);
LABEL_114:
  if ( pCertContext && (!(_DWORD)a5 || **((_WORD **)v38 + 5)) && (!v14 || (a4 & 2) != 0) && (a4 & 8) == 0 )
  {
    v67 = g_IgnorePasswdCerts || v14 ? 0LL : (int *)&a8;
    if ( !(unsigned int)FCheckSCardCertAndCanOpenSilentContext(pCertContext, (a4 & 0x14000) != 0, (int)a6, v67) )
    {
      v68 = (_WORD *)*((_QWORD *)v38 + 5);
      if ( !(_DWORD)a5 )
      {
        *v68 = 0;
        goto LABEL_129;
      }
      if ( *v68 )
      {
        v73 = -1;
        do
          ++v73;
        while ( v68[v73] );
        v74 = (unsigned int)(v73 + 1);
        v75 = (WCHAR *)LocalAlloc(0x40u, 2 * v74);
        v18 = v75;
        if ( !v75 )
        {
          v76 = GetLastError();
          DefaultClientMachineCert = v76;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_c4e812f99669349517681909258710e2_Traceguids, v76);
            v26 = a11;
            goto LABEL_15;
          }
LABEL_50:
          v26 = a11;
          goto LABEL_15;
        }
        _o_wcscpy_s(v75, v74, *((_QWORD *)v110 + 5));
        v77 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v78 = 80;
          goto LABEL_152;
        }
        goto LABEL_153;
      }
LABEL_129:
      if ( !(unsigned int)FUserCertToStr(pCertContext, (unsigned __int16 **)&v109) )
      {
        dwType[0] = 4;
        v69 = 0;
        dwType[1] = 5;
        dwType[2] = 1;
        dwType[3] = 6;
        dwType[4] = 8;
        while ( 1 )
        {
          v18 = 0;
          if ( v69 >= 5 )
            goto LABEL_144;
          v70 = dwType[v69];
          NameStringW = CertGetNameStringW(pCertContext, v70, 0, 0, 0, 0);
          v72 = NameStringW;
          if ( NameStringW > 1 )
            break;
          ++v69;
        }
        v79 = (WCHAR *)LocalAlloc(0x40u, 2LL * NameStringW);
        v18 = v79;
        if ( v79 )
        {
          memset_0(v79, 0, 2 * v72);
          CertGetNameStringW(pCertContext, v70, 0, 0, v18, v72);
LABEL_144:
          v17 = v119;
          DefaultClientMachineCert = SelectedHashesAndEKUList;
          goto LABEL_150;
        }
        v18 = (WCHAR *)v109;
        v17 = v119;
        v14 = (int)a14;
        DefaultClientMachineCert = SelectedHashesAndEKUList;
        v38 = v110;
        goto LABEL_146;
      }
      v18 = (WCHAR *)v109;
LABEL_150:
      v77 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v78 = 81;
LABEL_152:
        WPP_SF_S(*((_QWORD *)v77 + 2), v78, &WPP_c4e812f99669349517681909258710e2_Traceguids, v18);
      }
LABEL_153:
      v26 = a11;
      if ( (_DWORD)a8
        || (a4 & 2) != 0
        || (PasswdAndUserBlob = GetPasswdAndUserBlob(hWndParent, pCertContext, a10, a11),
            (DefaultClientMachineCert = PasswdAndUserBlob) == 0) )
      {
        *a12 = v18;
        v18 = 0;
      }
      else
      {
        v82 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v83 = 82;
          goto LABEL_158;
        }
      }
      goto LABEL_15;
    }
  }
LABEL_146:
  *(_QWORD *)&v113 = v38;
  if ( g_IgnorePasswdCerts || v14 )
    v80 = 0;
  else
    v80 = &v127;
  v84 = v120;
  v85 = 0;
  if ( !v124 )
    v84 = 0;
  LOBYTE(v85) = (a4 & 0x14000) != 0;
  CreateCertList(
    0,
    v14,
    0,
    (struct _EAPTLS_CERT_NODE **)&hMem[1],
    (struct _EAPTLS_CERT_NODE **)v112,
    1u,
    v63,
    L"MY",
    (unsigned int *)&a13,
    v85,
    (struct _EAPTLS_FILTER_PROP *)v84,
    v80);
  if ( !hMem[1] )
  {
    DefaultClientMachineCert = 798;
    if ( (_DWORD)a13 )
      DefaultClientMachineCert = (unsigned int)a13;
    if ( v14 && (_DWORD)a13 == -2143158016 )
      DefaultClientMachineCert = 798;
    goto LABEL_14;
  }
  v88 = v112[0];
  *(_QWORD *)&v114 = L"MY";
  if ( !v112[0] )
    v88 = hMem[1];
  v112[0] = v88;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_c4e812f99669349517681909258710e2_Traceguids, v127);
  v89 = v127;
  v90 = (int)hMem[0];
  if ( !v127 && ((__int64)hMem[0] & 1) == 0 && !*(_QWORD *)hMem[1] && (!v14 || (a4 & 2) != 0) )
  {
LABEL_178:
    v48 = SelectSingleNonGroupCert((struct _EAPTLS_USER_DIALOG *)hMem, a12, v124);
    goto LABEL_179;
  }
  if ( ((__int64)hMem[0] & 4) == 0 )
    goto LABEL_193;
  v91 = GroupCertificates((struct _EAPTLS_USER_DIALOG *)hMem, &v127, v87);
  DefaultClientMachineCert = v91;
  if ( v91 )
  {
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_50;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_c4e812f99669349517681909258710e2_Traceguids, v91);
    v26 = a11;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_c4e812f99669349517681909258710e2_Traceguids, v127);
  v89 = v127;
  v90 = (int)hMem[0];
  if ( v127 || ((__int64)hMem[0] & 1) != 0 || *(_QWORD *)v112[1] )
  {
LABEL_193:
    if ( (a4 & 2) != 0 )
    {
      v26 = a11;
      DefaultClientMachineCert = 703;
      goto LABEL_15;
    }
  }
  else if ( !v14 || (a4 & 2) != 0 )
  {
    v92 = SelectSingleGroupCert((struct _EAPTLS_USER_DIALOG *)hMem, a12, v124);
    v26 = a11;
    DefaultClientMachineCert = v92;
    goto LABEL_15;
  }
  if ( !v89 )
    goto LABEL_228;
  SkipNonProtectedCerts(v17, (struct _EAPTLS_CERT_NODE **)&hMem[1], (struct _EAPTLS_CERT_NODE **)v112, &v127);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_c4e812f99669349517681909258710e2_Traceguids, v127);
  if ( !hMem[1] )
  {
    v26 = a11;
    DefaultClientMachineCert = 798;
    goto LABEL_15;
  }
  LODWORD(v86) = v127;
  v90 = (int)hMem[0];
  if ( !v127 && ((__int64)hMem[0] & 1) == 0 && !*(_QWORD *)hMem[1] )
    goto LABEL_178;
  if ( ((__int64)hMem[0] & 4) == 0 || v89 == v127 )
    goto LABEL_212;
  DeleteGroupedList((struct _EAPTLS_GROUPED_CERT_NODES *)v112[1]);
  v94 = GroupCertificates((struct _EAPTLS_USER_DIALOG *)hMem, &v127, v93);
  DefaultClientMachineCert = v94;
  if ( v94 )
  {
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_50;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_c4e812f99669349517681909258710e2_Traceguids, v94);
    goto LABEL_180;
  }
  v90 = (int)hMem[0];
  if ( v127 )
    goto LABEL_212;
  if ( ((__int64)hMem[0] & 1) != 0 )
    goto LABEL_228;
  if ( !*(_QWORD *)v112[1] )
  {
    v48 = SelectSingleGroupCert((struct _EAPTLS_USER_DIALOG *)hMem, a12, v124);
    goto LABEL_179;
  }
LABEL_212:
  if ( (v90 & 1) != 0 )
    goto LABEL_228;
  if ( (v90 & 4) == 0 )
  {
    v86 = hMem[1];
    if ( *(_QWORD *)hMem[1] )
      goto LABEL_228;
    if ( hMem[1] )
    {
      v96 = v113;
      v112[0] = hMem[1];
      *(_OWORD *)(v113 + 16) = *(_OWORD *)((char *)hMem[1] + 8);
      v97 = v86[3];
LABEL_219:
      *(_QWORD *)(v96 + 32) = v97;
    }
    CertContextFromNode = GetCertContextFromNode(v17, (struct _EAPTLS_CERT_NODE *)v112[0]);
    v26 = a11;
    pCertContext = CertContextFromNode;
    if ( !CertContextFromNode )
    {
      DefaultClientMachineCert = 1359;
      goto LABEL_15;
    }
    PasswdAndUserBlob = GetPasswdAndUserBlob(hWndParent, pCertContext, a10, a11);
    DefaultClientMachineCert = PasswdAndUserBlob;
    if ( !PasswdAndUserBlob )
    {
      DefaultClientMachineCert = ConstructIdentity((struct _EAPTLS_USER_DIALOG *)hMem, a12);
      if ( !DefaultClientMachineCert && v124 )
        SQMCertSelectData(1, 0);
      goto LABEL_15;
    }
    v82 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_15;
    v83 = 89;
LABEL_158:
    WPP_SF_d(*((_QWORD *)v82 + 2), v83, &WPP_c4e812f99669349517681909258710e2_Traceguids, PasswdAndUserBlob);
    goto LABEL_15;
  }
  if ( !*(_QWORD *)v112[1] )
  {
    v95 = *((_QWORD *)v112[1] + 2);
    v96 = v113;
    v112[0] = (HLOCAL)v95;
    *(_OWORD *)(v113 + 16) = *(_OWORD *)(v95 + 8);
    v97 = *(_QWORD *)(v95 + 24);
    goto LABEL_219;
  }
LABEL_228:
  v99 = hWndParent;
  if ( (v90 & 1) == 0 )
  {
    if ( v124 )
      SQMCertSelectData(1, 1);
    v101 = a4 & 0x200000;
    if ( !v101 )
    {
      if ( !(unsigned __int8)IsRasTlsExt_GetPinUserBlobPresent() )
      {
        v90 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_c4e812f99669349517681909258710e2_Traceguids);
        goto LABEL_251;
      }
      DefaultClientMachineCert = RasTlsExt_SelectCertificate(hMem);
    }
    if ( DefaultClientMachineCert != 127 && DefaultClientMachineCert != 120 && !v101 )
    {
      if ( DefaultClientMachineCert )
        goto LABEL_180;
      goto LABEL_252;
    }
LABEL_251:
    DefaultClientMachineCert = CryptUIDisplayCerts(
                                 v90,
                                 (unsigned int)v86,
                                 v17,
                                 v99,
                                 (struct _EAPTLS_USER_DIALOG *)hMem,
                                 bAddressPrefix,
                                 lpszPrefix);
    if ( DefaultClientMachineCert )
      goto LABEL_50;
    goto LABEL_252;
  }
  DWORD2(v114) = 1;
  v100 = EapTlsLegacyCertSelectDialog(v90, hWndParent, (__int64)hMem);
  if ( v100 == -1 )
  {
    v48 = GetLastError();
    goto LABEL_179;
  }
  if ( v100 != 1 )
  {
    DefaultClientMachineCert = 1223;
    goto LABEL_180;
  }
  if ( v124 )
  {
    if ( ((__int64)hMem[0] & 4) != 0 )
    {
      if ( *(_QWORD *)v112[1] )
        goto LABEL_236;
LABEL_238:
      SQMCertSelectData(1, 0);
    }
    else
    {
      if ( !*(_QWORD *)hMem[1] )
        goto LABEL_238;
LABEL_236:
      SQMCertSelectData(1, 1);
    }
  }
LABEL_252:
  v26 = a11;
  v102 = a12;
  *a11 = (struct _EAPTLS_USER_PROPERTIES *)v113;
  DefaultClientMachineCert = ConstructIdentity((struct _EAPTLS_USER_DIALOG *)hMem, v102);
  if ( !DefaultClientMachineCert && *((_DWORD *)v112[0] + 19) )
  {
    pCertContext = GetCertContextFromNode(v17, (struct _EAPTLS_CERT_NODE *)v112[0]);
    if ( !pCertContext )
    {
      DefaultClientMachineCert = 1359;
      goto LABEL_15;
    }
    PasswdAndUserBlob = GetPasswdAndUserBlob(v99, pCertContext, a10, v26);
    DefaultClientMachineCert = PasswdAndUserBlob;
    if ( PasswdAndUserBlob )
    {
      v82 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v83 = 91;
        goto LABEL_158;
      }
    }
  }
LABEL_15:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v17 && !CertCloseStore(v17, 0) && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v27 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_c4e812f99669349517681909258710e2_Traceguids, v27);
  }
  if ( v18 )
    LocalFree(v18);
  v28 = (HLOCAL *)hMem[1];
  if ( hMem[1] )
  {
    do
    {
      LocalFree(v28[4]);
      LocalFree(v28[5]);
      LocalFree(v28[6]);
      LocalFree(v28[7]);
      v29 = v28;
      v28 = (HLOCAL *)*v28;
      LocalFree(v29);
    }
    while ( v28 );
  }
  v30 = v112[1];
  if ( v112[1] )
  {
    do
    {
      v31 = (_QWORD *)*v30;
      LocalFree(v30);
      v30 = v31;
    }
    while ( v31 );
  }
  LocalFree(v120[1]);
  v32 = (HLOCAL *)v121[0];
  if ( v121[0] )
  {
    do
    {
      LocalFree(v32[1]);
      LocalFree(v32[2]);
      LocalFree(v32[3]);
      v33 = v32;
      v32 = (HLOCAL *)*v32;
      LocalFree(v33);
    }
    while ( v32 );
  }
  *(_OWORD *)v120 = 0;
  *(_OWORD *)v121 = 0;
  if ( !DefaultClientMachineCert )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_c4e812f99669349517681909258710e2_Traceguids);
    TraceDumpExA(g_dwEapTlsTraceId, 0x10006u, (LPBYTE)*v26 + 20, *((_DWORD *)*v26 + 4), 1u, 0, 0);
  }
  return DefaultClientMachineCert;
}

```

## disassembly

```asm
0x1800136f0  mov     [rsp-8+arg_10], r8d
0x1800136f5  mov     [rsp-8+arg_8], edx
0x1800136f9  mov     [rsp-8+arg_0], ecx
0x1800136fd  push    rbp
0x1800136fe  push    rbx
0x1800136ff  push    rsi
0x180013700  push    rdi
0x180013701  push    r12
0x180013703  push    r13
0x180013705  push    r14
0x180013707  push    r15
0x180013709  lea     rbp, [rsp-58h]
0x18001370e  sub     rsp, 158h
0x180013715  xorps   xmm0, xmm0
0x180013718  mov     dword ptr [rbp+90h+arg_38], 1
0x180013722  xor     ecx, ecx
0x180013724  xor     eax, eax
0x180013726  mov     r15d, r9d
0x180013729  mov     [rsp+190h+pCertContext], rcx
0x18001372e  and     r15d, 1
0x180013732  mov     [rsp+190h+var_128], rcx
0x180013737  mov     ebx, r9d
0x18001373a  mov     dword ptr [rbp+90h+arg_68], r15d
0x180013741  and     ebx, 4
0x180013744  mov     [rbp+90h+var_A0], rax
0x180013748  mov     r12d, r9d
0x18001374b  mov     dword ptr [rbp+90h+arg_60], ecx
0x180013751  mov     r14d, ecx
0x180013754  mov     [rbp+90h+arg_18], ecx
0x18001375a  movups  [rbp+90h+pvFindPara], xmm0
0x18001375e  mov     r13d, ecx
0x180013761  movups  xmmword ptr [rbp+90h+hMem], xmm0
0x180013765  movups  xmmword ptr [rbp+90h+var_100], xmm0
0x180013769  movups  [rbp+90h+var_F0], xmm0
0x18001376d  movups  [rbp+90h+var_E0], xmm0
0x180013771  movups  [rbp+90h+var_D0], xmm0
0x180013775  movups  [rbp+90h+var_C0], xmm0
0x180013779  movups  [rbp+90h+var_B0], xmm0
0x18001377d  movups  xmmword ptr [rbp+90h+var_88], xmm0
0x180013781  movups  xmmword ptr [rbp+90h+var_78], xmm0
0x180013785  mov     rsi, cs:WPP_GLOBAL_Control
0x18001378c  lea     rax, WPP_GLOBAL_Control
0x180013793  cmp     rsi, rax
0x180013796  jz      short loc_1800137A8
0x180013798  mov     rcx, [rsi+10h]
0x18001379c  call    WPP_SF_L
0x1800137a1  mov     rsi, cs:WPP_GLOBAL_Control
0x1800137a8  xor     edx, edx; Val
0x1800137aa  lea     rcx, [rbp+90h+hMem]; void *
0x1800137ae  mov     r8d, 78h ; 'x'; Size
0x1800137b4  call    memset_0
0x1800137b9  mov     eax, dword ptr [rbp+90h+hMem]
0x1800137bc  mov     edx, 1
0x1800137c1  mov     rdi, [rbp+90h+pcbData]
0x1800137c8  mov     ecx, [rdi+8]
0x1800137cb  mov     r8d, ecx
0x1800137ce  and     r8d, 8
0x1800137d2  mov     dword ptr [rbp+90h+arg_20], r8d
0x1800137d9  cmovnz  eax, edx
0x1800137dc  xor     edx, edx
0x1800137de  test    r8d, r8d
0x1800137e1  mov     dword ptr [rbp+90h+hMem], eax
0x1800137e4  mov     rax, [rbp+90h+arg_28]
0x1800137eb  setnz   dl
0x1800137ee  mov     qword ptr [rbp+90h+var_F0+8], rax
0x1800137f2  test    r15d, r15d
0x1800137f5  jnz     short loc_18001380B
0x1800137f7  test    r12b, 20h
0x1800137fb  jnz     short loc_18001380B
0x1800137fd  or      edx, 2
0x180013800  mov     r8d, 18000h
0x180013806  mov     dword ptr [rbp+90h+hMem], edx
0x180013809  jmp     short loc_180013811
0x18001380b  mov     r8d, 28000h
0x180013811  mov     dword ptr [rbp+90h+pcbData], r8d
0x180013818  test    cl, 10h
0x18001381b  jz      short loc_180013823
0x18001381d  or      edx, 4
0x180013820  mov     dword ptr [rbp+90h+hMem], edx
0x180013823  test    ebx, ebx
0x180013825  jz      loc_1800139C0
0x18001382b  test    cl, 1
0x18001382e  jz      loc_1800139C0
0x180013834  mov     esi, 311h
0x180013839  mov     r15, [rbp+90h+arg_50]
0x180013840  lea     rdi, WPP_GLOBAL_Control
0x180013847  mov     rcx, [rsp+190h+pCertContext]; pCertContext
0x18001384c  test    rcx, rcx
0x18001384f  jz      short loc_180013857
0x180013851  call    cs:__imp_CertFreeCertificateContext
0x180013857  test    r14, r14
0x18001385a  jz      short loc_180013899
0x18001385c  xor     edx, edx; dwFlags
0x18001385e  mov     rcx, r14; hCertStore
0x180013861  call    cs:__imp_CertCloseStore
0x180013867  test    eax, eax
0x180013869  jnz     short loc_180013899
0x18001386b  cmp     cs:WPP_GLOBAL_Control, rdi
0x180013872  jz      short loc_180013899
0x180013874  call    cs:__imp_GetLastError
0x18001387a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013881  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180013888  mov     edx, 5Dh ; ']'
0x18001388d  mov     r9d, eax
0x180013890  mov     rcx, [rcx+10h]
0x180013894  call    WPP_SF_d
0x180013899  test    r13, r13
0x18001389c  jz      short loc_1800138A7
0x18001389e  mov     rcx, r13; hMem
0x1800138a1  call    cs:__imp_LocalFree
0x1800138a7  mov     rbx, [rbp+90h+hMem+8]
0x1800138ab  test    rbx, rbx
0x1800138ae  jz      short loc_1800138E9
0x1800138b0  mov     rcx, [rbx+20h]; hMem
0x1800138b4  call    cs:__imp_LocalFree
0x1800138ba  mov     rcx, [rbx+28h]; hMem
0x1800138be  call    cs:__imp_LocalFree
0x1800138c4  mov     rcx, [rbx+30h]; hMem
0x1800138c8  call    cs:__imp_LocalFree
0x1800138ce  mov     rcx, [rbx+38h]; hMem
0x1800138d2  call    cs:__imp_LocalFree
0x1800138d8  mov     rcx, rbx; hMem
0x1800138db  mov     rbx, [rbx]
0x1800138de  call    cs:__imp_LocalFree
0x1800138e4  test    rbx, rbx
0x1800138e7  jnz     short loc_1800138B0
0x1800138e9  mov     rcx, [rbp+90h+var_100+8]; hMem
0x1800138ed  test    rcx, rcx
0x1800138f0  jz      short loc_180013903
0x1800138f2  mov     rbx, [rcx]
0x1800138f5  call    cs:__imp_LocalFree
0x1800138fb  mov     rcx, rbx
0x1800138fe  test    rbx, rbx
0x180013901  jnz     short loc_1800138F2
0x180013903  mov     rcx, [rbp+90h+var_88+8]; hMem
0x180013907  call    cs:__imp_LocalFree
0x18001390d  mov     rbx, [rbp+90h+var_78]
0x180013911  test    rbx, rbx
0x180013914  jz      short loc_180013945
0x180013916  mov     rcx, [rbx+8]; hMem
0x18001391a  call    cs:__imp_LocalFree
0x180013920  mov     rcx, [rbx+10h]; hMem
0x180013924  call    cs:__imp_LocalFree
0x18001392a  mov     rcx, [rbx+18h]; hMem
0x18001392e  call    cs:__imp_LocalFree
0x180013934  mov     rcx, rbx; hMem
0x180013937  mov     rbx, [rbx]
0x18001393a  call    cs:__imp_LocalFree
0x180013940  test    rbx, rbx
0x180013943  jnz     short loc_180013916
0x180013945  xorps   xmm0, xmm0
0x180013948  movups  xmmword ptr [rbp+90h+var_88], xmm0
0x18001394c  movups  xmmword ptr [rbp+90h+var_78], xmm0
0x180013950  test    esi, esi
0x180013952  jnz     short loc_1800139AA
0x180013954  mov     rcx, cs:WPP_GLOBAL_Control
0x18001395b  cmp     rcx, rdi
0x18001395e  jz      short loc_180013975
0x180013960  mov     rcx, [rcx+10h]
0x180013964  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18001396b  mov     edx, 5Eh ; '^'
0x180013970  call    WPP_SF_
0x180013975  mov     r9, [r15]
0x180013978  mov     edx, 10006h; dwFlags
0x18001397d  mov     ecx, cs:?g_dwEapTlsTraceId@@3KA; dwTraceID
0x180013983  mov     [rsp+190h+lpszPrefix], 0; lpszPrefix
0x18001398c  mov     [rsp+190h+bAddressPrefix], 0; bAddressPrefix
0x180013994  lea     r8, [r9+14h]; lpbBytes
0x180013998  mov     [rsp+190h+dwGroupSize], 1; dwGroupSize
0x1800139a0  mov     r9d, [r9+10h]; dwByteCount
0x1800139a4  call    cs:__imp_TraceDumpExA
0x1800139aa  mov     eax, esi
0x1800139ac  add     rsp, 158h
0x1800139b3  pop     r15
0x1800139b5  pop     r14
0x1800139b7  pop     r13
0x1800139b9  pop     r12
0x1800139bb  pop     rdi
0x1800139bc  pop     rsi
0x1800139bd  pop     rbx
0x1800139be  pop     rbp
0x1800139bf  retn
0x1800139c0  mov     rbx, [rbp+90h+arg_50]
0x1800139c7  xor     eax, eax
0x1800139c9  mov     [rbp+90h+arg_8], eax
0x1800139cf  xor     r10d, r10d
0x1800139d2  mov     dword ptr [rbp+90h+arg_28], eax
0x1800139d8  mov     r11, 0FFFFFFFFFFFFFFFFh
0x1800139df  mov     eax, [rdi+0Ch]
0x1800139e2  mov     rbx, [rbx]
0x1800139e5  mov     [rbp+90h+arg_0], r10d
0x1800139ec  mov     [rsp+190h+var_120], rbx
0x1800139f1  lea     rcx, [rax+rax*2]
0x1800139f5  mov     rax, r11
0x1800139f8  lea     rdx, [rdi+rcx*8]
0x1800139fc  nop     dword ptr [rax+00h]
0x180013a00  cmp     [rdx+rax*2+12h], r10w
0x180013a06  lea     rax, [rax+1]
0x180013a0a  jnz     short loc_180013A00
0x180013a0c  mov     ecx, [rdi+4]
0x180013a0f  lea     r9, [rdx+12h]
0x180013a13  lea     r9, [r9+rax*2]
0x180013a17  sub     ecx, r9d
0x180013a1a  add     ecx, edi
0x180013a1c  cmp     ecx, 6
0x180013a1f  jb      loc_180013AA9
0x180013a25  mov     eax, 0FEh
0x180013a2a  cmp     [r9], ax
0x180013a2e  jnz     short loc_180013AA9
0x180013a30  mov     r8, r9
0x180013a33  xor     edx, edx
0x180013a35  mov     r10d, 0FAh
0x180013a3b  movzx   eax, word ptr [r8]
0x180013a3f  sub     ax, r10w
0x180013a43  cmp     ax, 4
0x180013a47  ja      short loc_180013A5A
0x180013a49  movzx   eax, word ptr [r8+2]
0x180013a4e  add     edx, eax; dwByteCount
0x180013a50  add     r8, rax
0x180013a53  sub     ecx, eax
0x180013a55  cmp     ecx, 6
0x180013a58  jnb     short loc_180013A3B
0x180013a5a  lea     r8, [rbp+90h+var_88]; struct _EAPTLS_FILTER_PROP *
0x180013a5e  mov     rcx, r9; lpbBytes
0x180013a61  call    ?GetSelectedHashesAndEKUList@@YAKPEAEKPEAU_EAPTLS_FILTER_PROP@@@Z; GetSelectedHashesAndEKUList(uchar *,ulong,_EAPTLS_FILTER_PROP *)
0x180013a66  mov     [rbp+90h+arg_8], eax
0x180013a6c  mov     esi, eax
0x180013a6e  test    eax, eax
0x180013a70  jnz     loc_180013839
0x180013a76  mov     eax, dword ptr [rbp+90h+var_88]
0x180013a79  mov     ecx, eax
0x180013a7b  and     ecx, 10h
0x180013a7e  mov     dword ptr [rbp+90h+arg_28], ecx
0x180013a84  jnz     short loc_180013AFB
0x180013a86  test    al, 1
0x180013a88  jnz     short loc_180013AFB
0x180013a8a  xor     r10d, r10d
0x180013a8d  mov     rsi, cs:WPP_GLOBAL_Control
0x180013a94  mov     r11, 0FFFFFFFFFFFFFFFFh
0x180013a9b  mov     r8d, dword ptr [rbp+90h+pcbData]
0x180013aa2  mov     [rbp+90h+arg_0], r10d
0x180013aa9  test    byte ptr [rdi+8], 1
0x180013aad  jnz     loc_180013CF0
0x180013ab3  test    r12b, 20h
0x180013ab7  jz      short loc_180013B03
0x180013ab9  mov     eax, 2BFh
0x180013abe  mov     [rbp+90h+arg_8], eax
0x180013ac4  lea     rdi, WPP_GLOBAL_Control
0x180013acb  cmp     rsi, rdi
0x180013ace  jz      loc_1800143F4
0x180013ad4  mov     rcx, [rsi+10h]
0x180013ad8  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180013adf  mov     edx, 43h ; 'C'
0x180013ae4  call    WPP_SF_
0x180013ae9  mov     esi, [rbp+90h+arg_8]
0x180013aef  mov     r15, [rbp+90h+arg_50]
0x180013af6  jmp     loc_180013847
0x180013afb  mov     r10d, 1
0x180013b01  jmp     short loc_180013A8D
0x180013b03  test    r10d, r10d
0x180013b06  jz      short loc_180013B14
0x180013b08  xor     eax, eax
0x180013b0a  cmp     cs:?g_OverrideSCardFilter@@3HA, eax; int g_OverrideSCardFilter
0x180013b10  cmovnz  r10d, eax
0x180013b14  mov     r15, [rbp+90h+arg_50]
0x180013b1b  test    r12b, 2
0x180013b1f  jz      loc_180013BDD
0x180013b25  mov     rcx, [rbx+28h]
0x180013b29  xor     eax, eax
0x180013b2b  cmp     ax, [rcx]
0x180013b2e  jnz     loc_180013CA2
0x180013b34  mov     r9, [rbp+90h+hWndParent]; HWND
0x180013b3b  lea     rcx, [rbp+90h+var_88]
0x180013b3f  test    r10d, r10d
0x180013b42  mov     r8, rdi; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x180013b45  mov     edx, r12d; unsigned int
0x180013b48  cmovz   rcx, rax; int
0x180013b4c  lea     rax, [rsp+190h+pCertContext]
0x180013b51  mov     [rsp+190h+var_150], rax; struct _CERT_CONTEXT **
0x180013b56  mov     eax, [rbp+90h+arg_10]
0x180013b5c  mov     [rsp+190h+var_158], r15; struct _EAPTLS_USER_PROPERTIES **
0x180013b61  mov     dword ptr [rsp+190h+lpszPrefix], eax; int
0x180013b65  mov     qword ptr [rsp+190h+bAddressPrefix], rcx; struct _EAPTLS_FILTER_PROP *
0x180013b6a  call    ?GetIdentityAndHashFromScard@@YAKHKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAUHWND__@@HPEAU_EAPTLS_FILTER_PROP@@HPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAPEBU_CERT_CONTEXT@@PEAKPEAPEAPEBU5@@Z; GetIdentityAndHashFromScard(int,ulong,_EAPTLS_CONN_PROPERTIES_V1 *,HWND__ *,int,_EAPTLS_FILTER_PROP *,int,_EAPTLS_USER_PROPERTIES * *,_CERT_CONTEXT const * *,ulong *,_CERT_CONTEXT const * * *)
0x180013b6f  mov     [rbp+90h+arg_8], eax
0x180013b75  mov     esi, eax
0x180013b77  test    eax, eax
0x180013b79  jz      short loc_180013B97
0x180013b7b  cmp     eax, 8010000Ch
0x180013b80  jz      short loc_180013B8D
0x180013b82  cmp     eax, 8010002Eh
0x180013b87  jnz     loc_180013840
0x180013b8d  mov     esi, 2BFh
0x180013b92  jmp     loc_180013840
0x180013b97  mov     rax, [r15]
0x180013b9a  test    byte ptr [rax+0Ch], 0Ch
0x180013b9e  jnz     loc_180013C2A
0x180013ba4  mov     esi, 2BFh
0x180013ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bb0  lea     rdi, WPP_GLOBAL_Control
  ... truncated ...
```
