# GetCertInfo(int,int,int,ulong,ushort const *,ushort const *,HWND__ *,ushort const *,_EAPTLS_CONN_PROPERTIES_V1 *,ulong,_EAPTLS_USER_PROPERTIES * *,ushort * *,ulong *,_CERT_CONTEXT const * * *)

- ea: `0x180014a70`
- end: `0x180015cf7`
- name: `?GetCertInfo@@YAKHHHKPEBG0PEAUHWND__@@0PEAU_EAPTLS_CONN_PROPERTIES_V1@@KPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAPEAGPEAKPEAPEAPEBU_CERT_CONTEXT@@@Z`
- size: `4743`
- prototype: `unsigned int __fastcall(int, int, int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, HWND hWndParent, const unsigned __int16 *, DWORD pcbData, unsigned int, struct _EAPTLS_USER_PROPERTIES **, unsigned __int16 **, unsigned int *, const struct _CERT_CONTEXT ***)`
- caller_count: `1`
- callee_count: `30`
- tags: ``

## callers

- `0x180076a1c`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180010140`
- `0x180014a70`
- `0x180015d00`
- `0x180016a18`
- `0x180022680`
- `0x18002318c`
- `0x18002e900`
- `0x1800346b4`
- `0x180035c50`
- `0x180038e64`
- `0x180039540`
- `0x18005db88`
- `0x18006d744`
- `0x18006da14`
- `0x180070f78`
- `0x180071118`
- `0x1800735a8`
- `0x1800738b4`
- `0x180073ee4`
- `0x180074114`
- `0x180074168`
- `0x180074358`
- `0x18007488c`
- `0x180074cb8`
- `0x180075bb0`
- `0x180075c10`
- `0x180075d2c`
- `0x180076dd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800150aa`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800155b9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800150aa`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800155b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b71`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001505e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001554d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800155f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001505e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001554d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800155f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014cab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014cc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ce4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014cf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014d04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014d16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001527a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014cab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014cc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ce4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014cf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014d04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014d16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001527a`
- `CRYPT32!CertCloseStore` at `0x180014be7`
- `CRYPT32!CertCloseStore` at `0x180014be7`
- `CRYPT32!CertFindCertificateInStore` at `0x1800152f4`
- `CRYPT32!CertFindCertificateInStore` at `0x1800152f4`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180015206`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001534e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180015206`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001534e`
- `CRYPT32!CertFreeCertificateContext` at `0x180014bd1`
- `CRYPT32!CertFreeCertificateContext` at `0x180014bd1`
- `CRYPT32!CertOpenStore` at `0x180015120`
- `CRYPT32!CertOpenStore` at `0x180015120`
- `CRYPT32!CertGetNameStringW` at `0x18001550a`
- `CRYPT32!CertGetNameStringW` at `0x18001562a`
- `CRYPT32!CertGetNameStringW` at `0x18001550a`
- `CRYPT32!CertGetNameStringW` at `0x18001562a`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_SelectCertificate` at `0x180015c06`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_SelectCertificate` at `0x180015c06`
- `rtutils!TraceDumpExA` at `0x180014d86`
- `rtutils!TraceDumpExA` at `0x180014d86`

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
  const struct _CERT_CONTEXT ***v108; // [rsp+50h] [rbp-B0h]
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v110; // [rsp+68h] [rbp-98h] BYREF
  struct _EAPTLS_USER_PROPERTIES *v111; // [rsp+70h] [rbp-90h]
  HLOCAL hMem[2]; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v113[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v114; // [rsp+A0h] [rbp-60h]
  __int128 v115; // [rsp+B0h] [rbp-50h]
  __int128 v116; // [rsp+C0h] [rbp-40h]
  __int128 v117; // [rsp+D0h] [rbp-30h]
  __int128 v118; // [rsp+E0h] [rbp-20h]
  __int64 v119; // [rsp+F0h] [rbp-10h]
  HCERTSTORE v120; // [rsp+100h] [rbp+0h]
  HLOCAL v121[2]; // [rsp+108h] [rbp+8h] BYREF
  HLOCAL v122[2]; // [rsp+118h] [rbp+18h]
  DWORD dwType[6]; // [rsp+128h] [rbp+28h]
  __int128 pvFindPara; // [rsp+140h] [rbp+40h] BYREF
  int v125; // [rsp+1A0h] [rbp+A0h]
  unsigned int SelectedHashesAndEKUList; // [rsp+1A8h] [rbp+A8h]
  unsigned int v128; // [rsp+1B8h] [rbp+B8h] BYREF

  LODWORD(a8) = 1;
  pCertContext = 0;
  v14 = a4 & 1;
  v110 = 0;
  LODWORD(a14) = v14;
  v15 = a4 & 4;
  v119 = 0;
  LODWORD(a13) = 0;
  v17 = 0;
  v128 = 0;
  pvFindPara = 0;
  v18 = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v113 = 0;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  *(_OWORD *)v121 = 0;
  *(_OWORD *)v122 = 0;
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
  *((_QWORD *)&v114 + 1) = a6;
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
  v125 = 0;
  v111 = *a11;
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
    SelectedHashesAndEKUList = GetSelectedHashesAndEKUList(v43, v46, (struct _EAPTLS_FILTER_PROP *)v121);
    DefaultClientMachineCert = SelectedHashesAndEKUList;
    if ( SelectedHashesAndEKUList )
      goto LABEL_14;
    LODWORD(a6) = (__int64)v121[0] & 0x10;
    v35 = ((__int64)v121[0] & 0x10) != 0 || ((__int64)v121[0] & 1) != 0;
    v19 = WPP_GLOBAL_Control;
    v36 = -1;
    v24 = pcbData;
    v125 = v35;
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
      v49 = v121;
      if ( !v35 )
        v49 = 0;
      IdentityAndHashFromScard = GetIdentityAndHashFromScard(
                                   (int)v49,
                                   a4,
                                   (struct _EAPTLS_CONN_PROPERTIES_V1 *)v21,
                                   hWndParent,
                                   dwGroupSize,
                                   (struct _EAPTLS_FILTER_PROP *)v49,
                                   a3,
                                   a11,
                                   &pCertContext,
                                   v107,
                                   v108);
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
      v53 = v121;
      if ( !v35 )
        v53 = 0;
      SelectedHashesAndEKUList = GetIdentityHashAndPinFromScard(
                                   (int)v53,
                                   a4,
                                   (struct _EAPTLS_CONN_PROPERTIES_V1 *)v21,
                                   hWndParent,
                                   a10,
                                   a11,
                                   (struct _EAPTLS_FILTER_PROP *)v53,
                                   v106,
                                   &pCertContext,
                                   v107,
                                   v108);
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
    v125 = v35;
  }
  v120 = CertOpenStore((LPCSTR)0xA, 1u, 0, v24, L"MY");
  v17 = v120;
  if ( !v120 )
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
    v60 = v121;
    v61 = 0;
    if ( !v125 )
      v60 = 0;
    LOBYTE(v61) = (a4 & 0x14000) != 0;
    DefaultClientMachineCert = GetDefaultClientMachineCert(v120, v61, (struct _EAPTLS_FILTER_PROP *)v60, &pCertContext);
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
      if ( (unsigned int)FMachineAuthCertToStr(pCertContext, (unsigned __int16 **)&v110)
        || (unsigned int)FCertToStr(pCertContext, 0) )
      {
        RasTlsFFormatMachineIdentity1((const unsigned __int16 *)v110, a12);
        LocalFree(v110);
      }
      else
      {
        v18 = (WCHAR *)v110;
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
        _o_wcscpy_s(v75, v74, *((_QWORD *)v111 + 5));
        v77 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v78 = 80;
          goto LABEL_152;
        }
        goto LABEL_153;
      }
LABEL_129:
      if ( !(unsigned int)FUserCertToStr(pCertContext, (unsigned __int16 **)&v110) )
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
          v17 = v120;
          DefaultClientMachineCert = SelectedHashesAndEKUList;
          goto LABEL_150;
        }
        v18 = (WCHAR *)v110;
        v17 = v120;
        v14 = (int)a14;
        DefaultClientMachineCert = SelectedHashesAndEKUList;
        v38 = v111;
        goto LABEL_146;
      }
      v18 = (WCHAR *)v110;
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
  *(_QWORD *)&v114 = v38;
  if ( g_IgnorePasswdCerts || v14 )
    v80 = 0;
  else
    v80 = &v128;
  v84 = v121;
  v85 = 0;
  if ( !v125 )
    v84 = 0;
  LOBYTE(v85) = (a4 & 0x14000) != 0;
  CreateCertList(
    0,
    v14,
    0,
    (struct _EAPTLS_CERT_NODE **)&hMem[1],
    (struct _EAPTLS_CERT_NODE **)v113,
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
  v88 = v113[0];
  *(_QWORD *)&v115 = L"MY";
  if ( !v113[0] )
    v88 = hMem[1];
  v113[0] = v88;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_c4e812f99669349517681909258710e2_Traceguids, v128);
  v89 = v128;
  v90 = (int)hMem[0];
  if ( !v128 && ((__int64)hMem[0] & 1) == 0 && !*(_QWORD *)hMem[1] && (!v14 || (a4 & 2) != 0) )
  {
LABEL_178:
    v48 = SelectSingleNonGroupCert((struct _EAPTLS_USER_DIALOG *)hMem, a12, v125);
    goto LABEL_179;
  }
  if ( ((__int64)hMem[0] & 4) == 0 )
    goto LABEL_193;
  v91 = GroupCertificates((struct _EAPTLS_USER_DIALOG *)hMem, &v128, v87);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_c4e812f99669349517681909258710e2_Traceguids, v128);
  v89 = v128;
  v90 = (int)hMem[0];
  if ( v128 || ((__int64)hMem[0] & 1) != 0 || *(_QWORD *)v113[1] )
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
    v92 = SelectSingleGroupCert((struct _EAPTLS_USER_DIALOG *)hMem, a12, v125);
    v26 = a11;
    DefaultClientMachineCert = v92;
    goto LABEL_15;
  }
  if ( !v89 )
    goto LABEL_228;
  SkipNonProtectedCerts(v17, (struct _EAPTLS_CERT_NODE **)&hMem[1], (struct _EAPTLS_CERT_NODE **)v113, &v128);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_c4e812f99669349517681909258710e2_Traceguids, v128);
  if ( !hMem[1] )
  {
    v26 = a11;
    DefaultClientMachineCert = 798;
    goto LABEL_15;
  }
  LODWORD(v86) = v128;
  v90 = (int)hMem[0];
  if ( !v128 && ((__int64)hMem[0] & 1) == 0 && !*(_QWORD *)hMem[1] )
    goto LABEL_178;
  if ( ((__int64)hMem[0] & 4) == 0 || v89 == v128 )
    goto LABEL_212;
  DeleteGroupedList((struct _EAPTLS_GROUPED_CERT_NODES *)v113[1]);
  v94 = GroupCertificates((struct _EAPTLS_USER_DIALOG *)hMem, &v128, v93);
  DefaultClientMachineCert = v94;
  if ( v94 )
  {
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_50;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_c4e812f99669349517681909258710e2_Traceguids, v94);
    goto LABEL_180;
  }
  v90 = (int)hMem[0];
  if ( v128 )
    goto LABEL_212;
  if ( ((__int64)hMem[0] & 1) != 0 )
    goto LABEL_228;
  if ( !*(_QWORD *)v113[1] )
  {
    v48 = SelectSingleGroupCert((struct _EAPTLS_USER_DIALOG *)hMem, a12, v125);
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
      v96 = v114;
      v113[0] = hMem[1];
      *(_OWORD *)(v114 + 16) = *(_OWORD *)((char *)hMem[1] + 8);
      v97 = v86[3];
LABEL_219:
      *(_QWORD *)(v96 + 32) = v97;
    }
    CertContextFromNode = GetCertContextFromNode(v17, (struct _EAPTLS_CERT_NODE *)v113[0]);
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
      if ( !DefaultClientMachineCert && v125 )
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
  if ( !*(_QWORD *)v113[1] )
  {
    v95 = *((_QWORD *)v113[1] + 2);
    v96 = v114;
    v113[0] = (HLOCAL)v95;
    *(_OWORD *)(v114 + 16) = *(_OWORD *)(v95 + 8);
    v97 = *(_QWORD *)(v95 + 24);
    goto LABEL_219;
  }
LABEL_228:
  v99 = hWndParent;
  if ( (v90 & 1) == 0 )
  {
    if ( v125 )
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
  DWORD2(v115) = 1;
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
  if ( v125 )
  {
    if ( ((__int64)hMem[0] & 4) != 0 )
    {
      if ( *(_QWORD *)v113[1] )
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
  *a11 = (struct _EAPTLS_USER_PROPERTIES *)v114;
  DefaultClientMachineCert = ConstructIdentity((struct _EAPTLS_USER_DIALOG *)hMem, v102);
  if ( !DefaultClientMachineCert && *((_DWORD *)v113[0] + 19) )
  {
    pCertContext = GetCertContextFromNode(v17, (struct _EAPTLS_CERT_NODE *)v113[0]);
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
  v30 = v113[1];
  if ( v113[1] )
  {
    do
    {
      v31 = (_QWORD *)*v30;
      LocalFree(v30);
      v30 = v31;
    }
    while ( v31 );
  }
  LocalFree(v121[1]);
  v32 = (HLOCAL *)v122[0];
  if ( v122[0] )
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
  *(_OWORD *)v121 = 0;
  *(_OWORD *)v122 = 0;
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
0x180014a70  mov     [rsp-8+arg_10], r8d
0x180014a75  mov     [rsp-8+arg_8], edx
0x180014a79  mov     [rsp-8+arg_0], ecx
0x180014a7d  push    rbp
0x180014a7e  push    rbx
0x180014a7f  push    rsi
0x180014a80  push    rdi
0x180014a81  push    r12
0x180014a83  push    r13
0x180014a85  push    r14
0x180014a87  push    r15
0x180014a89  lea     rbp, [rsp-58h]
0x180014a8e  sub     rsp, 158h
0x180014a95  xorps   xmm0, xmm0
0x180014a98  mov     dword ptr [rbp+90h+arg_38], 1
0x180014aa2  xor     ecx, ecx
0x180014aa4  xor     eax, eax
0x180014aa6  mov     r15d, r9d
0x180014aa9  mov     [rsp+190h+pCertContext], rcx
0x180014aae  and     r15d, 1
0x180014ab2  mov     [rsp+190h+var_128], rcx
0x180014ab7  mov     ebx, r9d
0x180014aba  mov     dword ptr [rbp+90h+arg_68], r15d
0x180014ac1  and     ebx, 4
0x180014ac4  mov     [rbp+90h+var_A0], rax
0x180014ac8  mov     r12d, r9d
0x180014acb  mov     dword ptr [rbp+90h+arg_60], ecx
0x180014ad1  mov     r14d, ecx
0x180014ad4  mov     [rbp+90h+arg_18], ecx
0x180014ada  movups  [rbp+90h+pvFindPara], xmm0
0x180014ade  mov     r13d, ecx
0x180014ae1  movups  xmmword ptr [rbp+90h+hMem], xmm0
0x180014ae5  movups  xmmword ptr [rbp+90h+var_100], xmm0
0x180014ae9  movups  [rbp+90h+var_F0], xmm0
0x180014aed  movups  [rbp+90h+var_E0], xmm0
0x180014af1  movups  [rbp+90h+var_D0], xmm0
0x180014af5  movups  [rbp+90h+var_C0], xmm0
0x180014af9  movups  [rbp+90h+var_B0], xmm0
0x180014afd  movups  xmmword ptr [rbp+90h+var_88], xmm0
0x180014b01  movups  xmmword ptr [rbp+90h+var_78], xmm0
0x180014b05  mov     rsi, cs:WPP_GLOBAL_Control
0x180014b0c  lea     rax, WPP_GLOBAL_Control
0x180014b13  cmp     rsi, rax
0x180014b16  jz      short loc_180014B28
0x180014b18  mov     rcx, [rsi+10h]
0x180014b1c  call    WPP_SF_L
0x180014b21  mov     rsi, cs:WPP_GLOBAL_Control
0x180014b28  xor     edx, edx; Val
0x180014b2a  lea     rcx, [rbp+90h+hMem]; void *
0x180014b2e  mov     r8d, 78h ; 'x'; Size
0x180014b34  call    memset_0
0x180014b39  mov     eax, dword ptr [rbp+90h+hMem]
0x180014b3c  mov     edx, 1
0x180014b41  mov     rdi, [rbp+90h+pcbData]
0x180014b48  mov     ecx, [rdi+8]
0x180014b4b  mov     r8d, ecx
0x180014b4e  and     r8d, 8
0x180014b52  mov     dword ptr [rbp+90h+arg_20], r8d
0x180014b59  cmovnz  eax, edx
0x180014b5c  xor     edx, edx
0x180014b5e  test    r8d, r8d
0x180014b61  mov     dword ptr [rbp+90h+hMem], eax
0x180014b64  mov     rax, [rbp+90h+arg_28]
0x180014b6b  setnz   dl
0x180014b6e  mov     qword ptr [rbp+90h+var_F0+8], rax
0x180014b72  test    r15d, r15d
0x180014b75  jnz     short loc_180014B8B
0x180014b77  test    r12b, 20h
0x180014b7b  jnz     short loc_180014B8B
0x180014b7d  or      edx, 2
0x180014b80  mov     r8d, 18000h
0x180014b86  mov     dword ptr [rbp+90h+hMem], edx
0x180014b89  jmp     short loc_180014B91
0x180014b8b  mov     r8d, 28000h
0x180014b91  mov     dword ptr [rbp+90h+pcbData], r8d
0x180014b98  test    cl, 10h
0x180014b9b  jz      short loc_180014BA3
0x180014b9d  or      edx, 4
0x180014ba0  mov     dword ptr [rbp+90h+hMem], edx
0x180014ba3  test    ebx, ebx
0x180014ba5  jz      loc_180014DA9
0x180014bab  test    cl, 1
0x180014bae  jz      loc_180014DA9
0x180014bb4  mov     esi, 311h
0x180014bb9  mov     r15, [rbp+90h+arg_50]
0x180014bc0  lea     rdi, WPP_GLOBAL_Control
0x180014bc7  mov     rcx, [rsp+190h+pCertContext]; pCertContext
0x180014bcc  test    rcx, rcx
0x180014bcf  jz      short loc_180014BDD
0x180014bd1  call    cs:__imp_CertFreeCertificateContext
0x180014bd8  nop     dword ptr [rax+rax+00h]
0x180014bdd  test    r14, r14
0x180014be0  jz      short loc_180014C2B
0x180014be2  xor     edx, edx; dwFlags
0x180014be4  mov     rcx, r14; hCertStore
0x180014be7  call    cs:__imp_CertCloseStore
0x180014bee  nop     dword ptr [rax+rax+00h]
0x180014bf3  test    eax, eax
0x180014bf5  jnz     short loc_180014C2B
0x180014bf7  cmp     cs:WPP_GLOBAL_Control, rdi
0x180014bfe  jz      short loc_180014C2B
0x180014c00  call    cs:__imp_GetLastError
0x180014c07  nop     dword ptr [rax+rax+00h]
0x180014c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c13  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180014c1a  mov     edx, 5Dh ; ']'
0x180014c1f  mov     r9d, eax
0x180014c22  mov     rcx, [rcx+10h]
0x180014c26  call    WPP_SF_d
0x180014c2b  test    r13, r13
0x180014c2e  jz      short loc_180014C3F
0x180014c30  mov     rcx, r13; hMem
0x180014c33  call    cs:__imp_LocalFree
0x180014c3a  nop     dword ptr [rax+rax+00h]
0x180014c3f  mov     rbx, [rbp+90h+hMem+8]
0x180014c43  test    rbx, rbx
0x180014c46  jz      short loc_180014C9F
0x180014c48  mov     rcx, [rbx+20h]; hMem
0x180014c4c  call    cs:__imp_LocalFree
0x180014c53  nop     dword ptr [rax+rax+00h]
0x180014c58  mov     rcx, [rbx+28h]; hMem
0x180014c5c  call    cs:__imp_LocalFree
0x180014c63  nop     dword ptr [rax+rax+00h]
0x180014c68  mov     rcx, [rbx+30h]; hMem
0x180014c6c  call    cs:__imp_LocalFree
0x180014c73  nop     dword ptr [rax+rax+00h]
0x180014c78  mov     rcx, [rbx+38h]; hMem
0x180014c7c  call    cs:__imp_LocalFree
0x180014c83  nop     dword ptr [rax+rax+00h]
0x180014c88  mov     rcx, rbx; hMem
0x180014c8b  mov     rbx, [rbx]
0x180014c8e  call    cs:__imp_LocalFree
0x180014c95  nop     dword ptr [rax+rax+00h]
0x180014c9a  test    rbx, rbx
0x180014c9d  jnz     short loc_180014C48
0x180014c9f  mov     rcx, [rbp+90h+var_100+8]; hMem
0x180014ca3  test    rcx, rcx
0x180014ca6  jz      short loc_180014CBF
0x180014ca8  mov     rbx, [rcx]
0x180014cab  call    cs:__imp_LocalFree
0x180014cb2  nop     dword ptr [rax+rax+00h]
0x180014cb7  mov     rcx, rbx
0x180014cba  test    rbx, rbx
0x180014cbd  jnz     short loc_180014CA8
0x180014cbf  mov     rcx, [rbp+90h+var_88+8]; hMem
0x180014cc3  call    cs:__imp_LocalFree
0x180014cca  nop     dword ptr [rax+rax+00h]
0x180014ccf  mov     rbx, [rbp+90h+var_78]
0x180014cd3  test    rbx, rbx
0x180014cd6  jz      short loc_180014D27
0x180014cd8  nop     dword ptr [rax+rax+00000000h]
0x180014ce0  mov     rcx, [rbx+8]; hMem
0x180014ce4  call    cs:__imp_LocalFree
0x180014ceb  nop     dword ptr [rax+rax+00h]
0x180014cf0  mov     rcx, [rbx+10h]; hMem
0x180014cf4  call    cs:__imp_LocalFree
0x180014cfb  nop     dword ptr [rax+rax+00h]
0x180014d00  mov     rcx, [rbx+18h]; hMem
0x180014d04  call    cs:__imp_LocalFree
0x180014d0b  nop     dword ptr [rax+rax+00h]
0x180014d10  mov     rcx, rbx; hMem
0x180014d13  mov     rbx, [rbx]
0x180014d16  call    cs:__imp_LocalFree
0x180014d1d  nop     dword ptr [rax+rax+00h]
0x180014d22  test    rbx, rbx
0x180014d25  jnz     short loc_180014CE0
0x180014d27  xorps   xmm0, xmm0
0x180014d2a  movups  xmmword ptr [rbp+90h+var_88], xmm0
0x180014d2e  movups  xmmword ptr [rbp+90h+var_78], xmm0
0x180014d32  test    esi, esi
0x180014d34  jnz     short loc_180014D92
0x180014d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d3d  cmp     rcx, rdi
0x180014d40  jz      short loc_180014D57
0x180014d42  mov     rcx, [rcx+10h]
0x180014d46  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180014d4d  mov     edx, 5Eh ; '^'
0x180014d52  call    WPP_SF_
0x180014d57  mov     r9, [r15]
0x180014d5a  mov     edx, 10006h; dwFlags
0x180014d5f  mov     ecx, cs:?g_dwEapTlsTraceId@@3KA; dwTraceID
0x180014d65  mov     [rsp+190h+lpszPrefix], 0; lpszPrefix
0x180014d6e  mov     [rsp+190h+bAddressPrefix], 0; bAddressPrefix
0x180014d76  lea     r8, [r9+14h]; lpbBytes
0x180014d7a  mov     [rsp+190h+dwGroupSize], 1; dwGroupSize
0x180014d82  mov     r9d, [r9+10h]; dwByteCount
0x180014d86  call    cs:__imp_TraceDumpExA
0x180014d8d  nop     dword ptr [rax+rax+00h]
0x180014d92  mov     eax, esi
0x180014d94  add     rsp, 158h
0x180014d9b  pop     r15
0x180014d9d  pop     r14
0x180014d9f  pop     r13
0x180014da1  pop     r12
0x180014da3  pop     rdi
0x180014da4  pop     rsi
0x180014da5  pop     rbx
0x180014da6  pop     rbp
0x180014da7  retn
0x180014da9  mov     rbx, [rbp+90h+arg_50]
0x180014db0  xor     eax, eax
0x180014db2  mov     [rbp+90h+arg_8], eax
0x180014db8  xor     r10d, r10d
0x180014dbb  mov     dword ptr [rbp+90h+arg_28], eax
0x180014dc1  mov     r11, 0FFFFFFFFFFFFFFFFh
0x180014dc8  mov     eax, [rdi+0Ch]
0x180014dcb  mov     rbx, [rbx]
0x180014dce  mov     [rbp+90h+arg_0], r10d
0x180014dd5  mov     [rsp+190h+var_120], rbx
0x180014dda  lea     rcx, [rax+rax*2]
0x180014dde  mov     rax, r11
0x180014de1  lea     rdx, [rdi+rcx*8]
0x180014de5  nop     word ptr [rax+rax+00000000h]
0x180014df0  cmp     [rdx+rax*2+12h], r10w
0x180014df6  lea     rax, [rax+1]
0x180014dfa  jnz     short loc_180014DF0
0x180014dfc  mov     ecx, [rdi+4]
0x180014dff  lea     r9, [rdx+12h]
0x180014e03  lea     r9, [r9+rax*2]
0x180014e07  sub     ecx, r9d
0x180014e0a  add     ecx, edi
0x180014e0c  cmp     ecx, 6
0x180014e0f  jb      loc_180014E99
0x180014e15  mov     eax, 0FEh
0x180014e1a  cmp     [r9], ax
0x180014e1e  jnz     short loc_180014E99
0x180014e20  mov     r8, r9
0x180014e23  xor     edx, edx
0x180014e25  mov     r10d, 0FAh
0x180014e2b  movzx   eax, word ptr [r8]
0x180014e2f  sub     ax, r10w
0x180014e33  cmp     ax, 4
0x180014e37  ja      short loc_180014E4A
0x180014e39  movzx   eax, word ptr [r8+2]
0x180014e3e  add     edx, eax; dwByteCount
0x180014e40  add     r8, rax
0x180014e43  sub     ecx, eax
0x180014e45  cmp     ecx, 6
0x180014e48  jnb     short loc_180014E2B
0x180014e4a  lea     r8, [rbp+90h+var_88]; struct _EAPTLS_FILTER_PROP *
0x180014e4e  mov     rcx, r9; lpbBytes
0x180014e51  call    ?GetSelectedHashesAndEKUList@@YAKPEAEKPEAU_EAPTLS_FILTER_PROP@@@Z; GetSelectedHashesAndEKUList(uchar *,ulong,_EAPTLS_FILTER_PROP *)
0x180014e56  mov     [rbp+90h+arg_8], eax
0x180014e5c  mov     esi, eax
0x180014e5e  test    eax, eax
0x180014e60  jnz     loc_180014BB9
0x180014e66  mov     eax, dword ptr [rbp+90h+var_88]
0x180014e69  mov     ecx, eax
0x180014e6b  and     ecx, 10h
0x180014e6e  mov     dword ptr [rbp+90h+arg_28], ecx
0x180014e74  jnz     short loc_180014EEB
0x180014e76  test    al, 1
0x180014e78  jnz     short loc_180014EEB
0x180014e7a  xor     r10d, r10d
0x180014e7d  mov     rsi, cs:WPP_GLOBAL_Control
0x180014e84  mov     r11, 0FFFFFFFFFFFFFFFFh
0x180014e8b  mov     r8d, dword ptr [rbp+90h+pcbData]
0x180014e92  mov     [rbp+90h+arg_0], r10d
0x180014e99  test    byte ptr [rdi+8], 1
0x180014e9d  jnz     loc_1800150EC
0x180014ea3  test    r12b, 20h
0x180014ea7  jz      short loc_180014EF3
0x180014ea9  mov     eax, 2BFh
0x180014eae  mov     [rbp+90h+arg_8], eax
0x180014eb4  lea     rdi, WPP_GLOBAL_Control
0x180014ebb  cmp     rsi, rdi
0x180014ebe  jz      loc_180015848
0x180014ec4  mov     rcx, [rsi+10h]
0x180014ec8  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180014ecf  mov     edx, 43h ; 'C'
0x180014ed4  call    WPP_SF_
0x180014ed9  mov     esi, [rbp+90h+arg_8]
0x180014edf  mov     r15, [rbp+90h+arg_50]
0x180014ee6  jmp     loc_180014BC7
0x180014eeb  mov     r10d, 1
0x180014ef1  jmp     short loc_180014E7D
0x180014ef3  test    r10d, r10d
0x180014ef6  jz      short loc_180014F04
0x180014ef8  xor     eax, eax
0x180014efa  cmp     cs:?g_OverrideSCardFilter@@3HA, eax; int g_OverrideSCardFilter
0x180014f00  cmovnz  r10d, eax
0x180014f04  mov     r15, [rbp+90h+arg_50]
0x180014f0b  test    r12b, 2
0x180014f0f  jz      loc_180014FCD
0x180014f15  mov     rcx, [rbx+28h]
0x180014f19  xor     eax, eax
0x180014f1b  cmp     ax, [rcx]
0x180014f1e  jnz     loc_180015098
0x180014f24  mov     r9, [rbp+90h+hWndParent]; HWND
0x180014f2b  lea     rcx, [rbp+90h+var_88]
0x180014f2f  test    r10d, r10d
0x180014f32  mov     r8, rdi; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x180014f35  mov     edx, r12d; unsigned int
0x180014f38  cmovz   rcx, rax; int
0x180014f3c  lea     rax, [rsp+190h+pCertContext]
0x180014f41  mov     [rsp+190h+var_150], rax; struct _CERT_CONTEXT **
0x180014f46  mov     eax, [rbp+90h+arg_10]
0x180014f4c  mov     [rsp+190h+var_158], r15; struct _EAPTLS_USER_PROPERTIES **
0x180014f51  mov     dword ptr [rsp+190h+lpszPrefix], eax; int
0x180014f55  mov     qword ptr [rsp+190h+bAddressPrefix], rcx; struct _EAPTLS_FILTER_PROP *
  ... truncated ...
```
