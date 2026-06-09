# Pku2uHandlePeer2PeerAsRequest(_PKU2U_CONTEXT *,uchar *,ulong,long *,uchar * *,ulong *)

- ea: `0x180035dc0`
- end: `0x1800370ca`
- name: `?Pku2uHandlePeer2PeerAsRequest@@YAJPEAU_PKU2U_CONTEXT@@PEAEKPEAJPEAPEAEPEAK@Z`
- size: `4874`
- prototype: `__int64 __fastcall(struct _PKU2U_CONTEXT *, struct KERB_KDC_REQUEST_BODY *, unsigned int, int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `58`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b990`

## callees

- `0x180004830`
- `0x180004d60`
- `0x1800057f0`
- `0x180007800`
- `0x180007dc8`
- `0x180010db0`
- `0x180010e50`
- `0x180011060`
- `0x180011170`
- `0x180013b20`
- `0x180014660`
- `0x180014e30`
- `0x180014fe0`
- `0x180015190`
- `0x1800160e0`
- `0x180016a10`
- `0x1800178d0`
- `0x180017940`
- `0x180017df0`
- `0x180018618`
- `0x180018870`
- `0x180018f50`
- `0x180019928`
- `0x180019e5c`
- `0x18001a0b0`
- `0x18001a1d0`
- `0x18001fc04`
- `0x1800201bc`
- `0x1800210f0`
- `0x180021a54`
- `0x180023cb8`
- `0x180023ce0`
- `0x18002b158`
- `0x18002b408`
- `0x18002ff80`
- `0x180030298`
- `0x180030548`
- `0x18003109c`
- `0x1800313c8`
- `0x1800313ec`
- `0x180031430`
- `0x180031498`
- `0x180031534`
- `0x180031678`
- `0x180031b70`
- `0x1800349e0`
- `0x180034af8`
- `0x180034b38`
- `0x180034d88`
- `0x180034e84`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800365bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800365bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036e9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036e9e`
- `ntdll!RtlEqualDomainName` at `0x180036106`
- `ntdll!RtlEqualDomainName` at `0x180036106`
- `ntdll!RtlLeaveCriticalSection` at `0x180036881`
- `ntdll!RtlLeaveCriticalSection` at `0x180036a64`
- `ntdll!RtlLeaveCriticalSection` at `0x180036aa3`
- `ntdll!RtlLeaveCriticalSection` at `0x180036881`
- `ntdll!RtlLeaveCriticalSection` at `0x180036a64`
- `ntdll!RtlLeaveCriticalSection` at `0x180036aa3`
- `ntdll!RtlEnterCriticalSection` at `0x18003682d`
- `ntdll!RtlEnterCriticalSection` at `0x180036a35`
- `ntdll!RtlEnterCriticalSection` at `0x18003682d`
- `ntdll!RtlEnterCriticalSection` at `0x180036a35`
- `ntdll!NtQuerySystemTime` at `0x180036ab5`
- `ntdll!NtQuerySystemTime` at `0x180036ab5`
- `CRYPT32!CertFreeCertificateContext` at `0x180036f15`
- `CRYPT32!CertFreeCertificateContext` at `0x180036f15`
- `CRYPT32!CertCloseStore` at `0x180037079`
- `CRYPT32!CertCloseStore` at `0x180037079`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstValidate` at `0x180036390`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstValidate` at `0x180036390`
- `cryptdll!CDFindCommonCSystem` at `0x180036649`
- `cryptdll!CDFindCommonCSystem` at `0x180036649`
- `cryptdll!CDBuildIntegrityVect` at `0x18003699a`
- `cryptdll!CDBuildIntegrityVect` at `0x18003699a`

## pseudocode

```c
__int64 __fastcall Pku2uHandlePeer2PeerAsRequest(
        struct _PKU2U_CONTEXT *a1,
        struct KERB_KDC_REQUEST_BODY *a2,
        unsigned int a3,
        int *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  struct PKERB_AUTHORIZATION_DATA *v8; // r13
  HANDLE v9; // r14
  struct gss_OID_desc_struct *v10; // rcx
  int inited; // edi
  unsigned int v12; // ebx
  struct _PACTYPE *v13; // r12
  unsigned int v14; // eax
  int v15; // ecx
  int v16; // eax
  __int64 v17; // r9
  int v18; // eax
  struct _UNICODE_STRING *v19; // r8
  struct KERB_KDC_REQUEST_BODY_encryption_type **v20; // r13
  int v21; // ecx
  struct _UNICODE_STRING *v22; // r8
  unsigned int v23; // eax
  struct KERB_PA_DATA *PreAuthDataEntry; // rax
  int v25; // ecx
  unsigned int v26; // eax
  int v27; // r8d
  int v28; // edi
  DWORD LastError; // eax
  int v30; // eax
  struct _CERT_CONTEXT *v31; // rsi
  int v32; // eax
  __int64 v33; // r8
  int v34; // eax
  int v35; // eax
  unsigned int *v36; // r15
  int v37; // eax
  unsigned int Key; // eax
  char *v39; // rax
  int v40; // ecx
  unsigned int v41; // eax
  __int64 v42; // r13
  __int64 v43; // r13
  DWORD v44; // eax
  int v45; // r9d
  int v46; // eax
  int v47; // eax
  struct KERB_KDC_REQUEST_BODY_encryption_type *v48; // rcx
  __int64 *v49; // rcx
  struct KERB_KDC_REQUEST_BODY_encryption_type *v50; // rax
  struct KERB_ENCRYPTION_KEY **v51; // r12
  __int64 v52; // rcx
  union _LARGE_INTEGER *p_SystemTime; // rax
  int v54; // eax
  int v55; // eax
  struct PKERB_HOST_ADDRESSES *v56; // rdx
  struct KERB_KDC_REQUEST_BODY *v57; // rdi
  unsigned int Size; // ebx
  unsigned __int8 *v59; // rax
  int v60; // ecx
  int v61; // eax
  struct PKERB_AUTHORIZATION_DATA *v62; // rdx
  unsigned int inserted; // eax
  unsigned int v64; // r8d
  int v65; // eax
  unsigned int v66; // r8d
  unsigned int v67; // r9d
  __int64 v68; // rcx
  __int64 v69; // rdx
  int v70; // eax
  int v71; // eax
  unsigned int v73; // [rsp+20h] [rbp-E0h]
  struct _CERT_CONTEXT *pCertContext; // [rsp+50h] [rbp-B0h]
  struct KERB_KDC_REQUEST_BODY_encryption_type *v75; // [rsp+58h] [rbp-A8h]
  unsigned int *v76; // [rsp+60h] [rbp-A0h]
  HANDLE hObject; // [rsp+68h] [rbp-98h]
  struct PKERB_AUTHORIZATION_DATA *v78; // [rsp+78h] [rbp-88h]
  unsigned int v79; // [rsp+80h] [rbp-80h] BYREF
  int v80; // [rsp+84h] [rbp-7Ch] BYREF
  void *v81; // [rsp+88h] [rbp-78h] BYREF
  void *v82; // [rsp+90h] [rbp-70h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v84; // [rsp+A0h] [rbp-60h] BYREF
  int v85; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v86; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v87; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v88; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v89; // [rsp+B4h] [rbp-4Ch] BYREF
  HANDLE Token; // [rsp+B8h] [rbp-48h] BYREF
  struct _PACTYPE *Src; // [rsp+C0h] [rbp-40h] BYREF
  struct _KERB_INTERNAL_NAME *v92; // [rsp+C8h] [rbp-38h] BYREF
  struct KERB_KDC_REQUEST_BODY *v93; // [rsp+D0h] [rbp-30h] BYREF
  int v94; // [rsp+D8h] [rbp-28h] BYREF
  struct _CERT_CONTEXT *v95; // [rsp+E0h] [rbp-20h] BYREF
  union _LARGE_INTEGER Time; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int *v97; // [rsp+F0h] [rbp-10h] BYREF
  struct KERB_KDC_REQUEST_BODY_encryption_type *v98; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int8 *v99; // [rsp+100h] [rbp+0h] BYREF
  void *v100; // [rsp+108h] [rbp+8h] BYREF
  struct _KERB_INTERNAL_NAME *v101; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int8 *v102; // [rsp+118h] [rbp+18h] BYREF
  struct _KERB_INTERNAL_NAME *v103; // [rsp+120h] [rbp+20h]
  struct _KERB_INTERNAL_NAME *v104; // [rsp+128h] [rbp+28h] BYREF
  struct _CRYPT_ALGORITHM_IDENTIFIER *v105; // [rsp+130h] [rbp+30h] BYREF
  HCERTSTORE hCertStore; // [rsp+138h] [rbp+38h] BYREF
  void *v107; // [rsp+140h] [rbp+40h]
  int v108; // [rsp+148h] [rbp+48h] BYREF
  struct _CRYPTOAPI_BLOB v109; // [rsp+150h] [rbp+50h] BYREF
  struct _UNICODE_STRING v110; // [rsp+160h] [rbp+60h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+170h] [rbp+70h] BYREF
  int *v112; // [rsp+178h] [rbp+78h]
  __int64 v113; // [rsp+180h] [rbp+80h]
  unsigned __int8 *v114[2]; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int8 *v115[2]; // [rsp+198h] [rbp+98h] BYREF
  struct _UNICODE_STRING DomainName1; // [rsp+1A8h] [rbp+A8h] BYREF
  struct _UNICODE_STRING DomainName2; // [rsp+1B8h] [rbp+B8h] BYREF
  DWORD pcbEncoded[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  struct _CRYPTOAPI_BLOB v119; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v120; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v121; // [rsp+1F8h] [rbp+F8h]
  __int128 v122; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int8 *v123[2]; // [rsp+210h] [rbp+110h]
  unsigned int *v124; // [rsp+220h] [rbp+120h]
  unsigned __int8 **v125; // [rsp+228h] [rbp+128h]
  struct _UNICODE_STRING v126; // [rsp+230h] [rbp+130h] BYREF
  struct _UNICODE_STRING v127; // [rsp+240h] [rbp+140h] BYREF
  _DWORD v128[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v129; // [rsp+260h] [rbp+160h]
  __int128 v130; // [rsp+268h] [rbp+168h] BYREF
  __int128 v131; // [rsp+278h] [rbp+178h]
  __int128 v132; // [rsp+288h] [rbp+188h]
  __int128 v133; // [rsp+298h] [rbp+198h] BYREF
  __int64 v134; // [rsp+2A8h] [rbp+1A8h]
  __int128 v135; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v136; // [rsp+2C0h] [rbp+1C0h]
  _BYTE v137[8]; // [rsp+2D0h] [rbp+1D0h] BYREF
  char *v138; // [rsp+2D8h] [rbp+1D8h]
  _BYTE v139[40]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int16 *v140; // [rsp+308h] [rbp+208h]
  _WORD v141[2]; // [rsp+320h] [rbp+220h] BYREF
  int v142; // [rsp+324h] [rbp+224h]
  int v143; // [rsp+328h] [rbp+228h]
  struct PKERB_AUTHORIZATION_DATA *v144; // [rsp+330h] [rbp+230h]
  __int64 v145; // [rsp+338h] [rbp+238h]
  __int128 v146; // [rsp+340h] [rbp+240h]
  _BYTE v147[8]; // [rsp+350h] [rbp+250h] BYREF
  struct _KERB_INTERNAL_NAME *v148; // [rsp+358h] [rbp+258h] BYREF
  _BYTE v149[40]; // [rsp+360h] [rbp+260h] BYREF
  void *v150; // [rsp+388h] [rbp+288h]
  _BYTE v151[24]; // [rsp+398h] [rbp+298h] BYREF
  void *v152; // [rsp+3B0h] [rbp+2B0h]
  struct _CERT_X942_DH_PARAMETERS v153; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int128 v154; // [rsp+410h] [rbp+310h] BYREF
  __int128 v155; // [rsp+420h] [rbp+320h]
  __int128 v156; // [rsp+430h] [rbp+330h]
  __int16 v157; // [rsp+440h] [rbp+340h] BYREF
  int v158; // [rsp+448h] [rbp+348h]
  int *v159; // [rsp+450h] [rbp+350h]
  __int64 v160; // [rsp+470h] [rbp+370h]
  __int128 v161; // [rsp+478h] [rbp+378h]
  _BYTE v162[64]; // [rsp+4A0h] [rbp+3A0h] BYREF
  struct PKERB_AUTHORIZATION_DATA *v163; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned int v164[8]; // [rsp+4F0h] [rbp+3F0h] BYREF
  void *v165; // [rsp+510h] [rbp+410h]
  int v166; // [rsp+530h] [rbp+430h]
  int *v167; // [rsp+538h] [rbp+438h]
  __int64 v168; // [rsp+590h] [rbp+490h]
  unsigned int v169[20]; // [rsp+5A0h] [rbp+4A0h] BYREF
  unsigned __int8 v170[32]; // [rsp+5F0h] [rbp+4F0h] BYREF

  v93 = a2;
  v112 = a4;
  v125 = a5;
  v124 = a6;
  v84 = a3;
  v81 = 0;
  *(_QWORD *)&DomainName1.Length = 2097182;
  DomainName1.Buffer = (PWSTR)L"WELLKNOWN:PKU2U";
  DomainName2 = 0;
  v101 = 0;
  memset_0(v137, 0, 0x48u);
  memset_0(&v157, 0, 0xA8u);
  v100 = 0;
  v102 = 0;
  v136 = 0;
  v75 = 0;
  v98 = 0;
  v113 = 0;
  v127 = 0;
  v121 = 0;
  v8 = 0;
  v135 = 0;
  v103 = 0;
  v154 = 0;
  v92 = 0;
  v155 = 0;
  v156 = 0;
  Src = 0;
  *(_OWORD *)v114 = 0;
  v86 = 0;
  *(_OWORD *)v115 = 0;
  pCertContext = 0;
  v120 = 0;
  v95 = 0;
  v122 = 0;
  v128[1] = 0;
  *(_OWORD *)v123 = 0;
  v128[3] = 0;
  v105 = 0;
  v82 = 0;
  v78 = 0;
  v88 = 20;
  *(&v109.cbData + 1) = 0;
  *(_QWORD *)&v153.p.cbData = 0;
  memset_0(&v153.p.pbData, 0, 0x40u);
  Time.QuadPart = 0;
  SystemTimeAsFileTime = 0;
  v87 = 0;
  v76 = 0;
  *(_OWORD *)pcbEncoded = 0;
  v97 = 0;
  v119 = 0;
  v134 = 0;
  v133 = 0;
  v79 = 0;
  v130 = 0;
  v131 = 0;
  v94 = 0;
  v108 = 0;
  v132 = 0;
  memset_0(v164, 0, 0xB0u);
  memset_0(v141, 0, 0x98u);
  hCertStore = 0;
  v107 = 0;
  v99 = 0;
  v104 = 0;
  v89 = 0;
  v110 = 0;
  *v112 = 0;
  v9 = 0;
  *a6 = 0;
  *a5 = 0;
  v126 = 0;
  SystemTime.QuadPart = 0;
  hObject = 0;
  Token = 0;
  v80 = 0;
  v85 = 0;
  if ( !(unsigned int)g_verify_token_header(v10, (int *)&v84, (unsigned __int8 **)&v93, 1280, a3) )
  {
    inited = 280;
LABEL_3:
    v12 = 60;
LABEL_4:
    v13 = 0;
LABEL_186:
    v31 = pCertContext;
    goto LABEL_187;
  }
  v14 = KerbUnpackData((unsigned __int8 *)v93, v84, 0x2Fu, &v81);
  v12 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids, v14);
LABEL_9:
    v15 = v12;
LABEL_10:
    v16 = KerbMapKerbError(v15);
LABEL_183:
    inited = v16;
    goto LABEL_184;
  }
  v17 = *((unsigned int *)v81 + 1);
  if ( (_DWORD)v17 != 5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids, v17);
    v12 = 39;
    goto LABEL_9;
  }
  v18 = KerbConvertRealmToUnicodeString(&DomainName2, (char **)v81 + 8);
  v12 = v18;
  if ( v18 )
    goto LABEL_17;
  if ( !RtlEqualDomainName(&DomainName1, &DomainName2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v12 = 68;
    goto LABEL_9;
  }
  v18 = KerbConvertPrincipalNameToKdcName(&v101, (struct KERB_PRINCIPAL_NAME *)((char *)v81 + 72));
  v12 = v18;
  if ( v18 || (v18 = KerbConvertKdcNameToString(&v127, v101, v19), (v12 = v18) != 0) )
  {
LABEL_17:
    inited = KerbMapKerbError(v18);
    goto LABEL_4;
  }
  if ( !Pku2uGlobalDHInitialized )
  {
    inited = Pku2uInitDH();
    if ( inited < 0 )
      goto LABEL_3;
  }
  v20 = (struct KERB_KDC_REQUEST_BODY_encryption_type **)((char *)v81 + 24);
  v93 = (struct KERB_KDC_REQUEST_BODY *)((char *)v81 + 24);
  if ( *((char *)v81 + 24) >= 0 )
  {
    v12 = 6;
    v21 = 6;
LABEL_29:
    inited = KerbMapKerbError(v21);
LABEL_30:
    v8 = 0;
    goto LABEL_4;
  }
  v12 = KerbConvertPrincipalNameToKdcName(&v92, (struct KERB_PRINCIPAL_NAME *)((char *)v81 + 48));
  v103 = v92;
  if ( v12 )
  {
    inited = -1073741670;
    goto LABEL_30;
  }
  v23 = KerbConvertKdcNameToString(&v110, v92, v22);
  v12 = v23;
  if ( v23 )
  {
    v21 = v23;
    goto LABEL_29;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2));
  PreAuthDataEntry = KerbFindPreAuthDataEntry(0x10u, *((struct KERB_KDC_REQUEST_preauth_data **)v81 + 2));
  if ( !PreAuthDataEntry )
  {
    v12 = 25;
LABEL_40:
    v25 = v12;
LABEL_41:
    inited = KerbMapKerbError(v25);
LABEL_42:
    v8 = v78;
LABEL_184:
    v13 = 0;
    goto LABEL_185;
  }
  v26 = KerbUnpackData(*((unsigned __int8 **)PreAuthDataEntry + 2), *((_DWORD *)PreAuthDataEntry + 2), 0x12u, &v100);
  v12 = v26;
  if ( v26 )
  {
LABEL_44:
    v25 = v26;
    goto LABEL_41;
  }
  v28 = ScHelperVerifyPkcsMessage(
          *((BYTE **)v100 + 2),
          *((_DWORD *)v100 + 2),
          v27,
          "1.3.6.1.5.2.3.1",
          &v102,
          &v86,
          (const struct _CERT_CONTEXT **)&v95,
          &hCertStore,
          &v105);
  if ( v28 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids,
        (unsigned int)v28,
        LastError);
    }
    v12 = 41;
    v30 = KerbMapKerbError(41);
    v31 = v95;
    inited = v30;
    goto LABEL_50;
  }
  v31 = v95;
  pCertContext = v95;
  if ( !v95 )
  {
    inited = -1073741715;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
        goto LABEL_42;
      }
      v31 = 0;
    }
LABEL_50:
    v8 = 0;
    v9 = 0;
    v13 = 0;
LABEL_187:
    v36 = v76;
    goto LABEL_188;
  }
  inited = IntPstValidate(0, 1, &hCertStore, v95, 0, &v85);
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&v110);
    goto LABEL_60;
  }
  if ( v85 )
  {
    inited = -1073740917;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&v110);
    v12 = 74;
    goto LABEL_42;
  }
  v26 = KerbUnpackData(v102, v86, 0x29u, &v82);
  v12 = v26;
  if ( v26 )
    goto LABEL_44;
  if ( *((char *)v82 + 8) >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
    v12 = 79;
    goto LABEL_40;
  }
  v129 = *((_QWORD *)v82 + 6);
  v32 = *((_DWORD *)v82 + 10);
  v128[0] = -131;
  v128[2] = v32;
  if ( (int)Pku2uVerifyTgsChecksum(
              (struct KERB_KDC_REQUEST_BODY *)((char *)v81 + 24),
              (struct KERB_ENCRYPTION_KEY *)&v135,
              (struct KERB_CHECKSUM *)v128) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids, 0);
    v25 = 0;
    goto LABEL_41;
  }
  if ( (*(_BYTE *)v82 & 0x80) == 0 )
  {
    v12 = 9;
    goto LABEL_40;
  }
  if ( !(unsigned int)Pku2uEqualOID(
                        *((struct ASN1objectidentifier_s **)v82 + 8),
                        *((struct ASN1objectidentifier_s **)Pku2uGlobalEmpheralDHAlg + 1))
    || (*(_BYTE *)(v33 + 56) & 0x80) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
    v12 = 60;
    v16 = KerbMapKerbError(60);
    v8 = 0;
    goto LABEL_183;
  }
  v109.cbData = *(_DWORD *)(v33 + 72);
  v109.pbData = *(BYTE **)(v33 + 80);
  v26 = Pku2uDecodeDHParameters(&v109, &v153);
  v12 = v26;
  if ( v26 )
    goto LABEL_44;
  if ( (*(_BYTE *)v82 & 0x20) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
    goto LABEL_86;
  }
  if ( !(unsigned int)Pku2uGetDHPublicKey(Pku2uGlobalDHKey, pcbEncoded)
    || (v109.cbData = *((_DWORD *)v82 + 22) >> 3,
        v109.pbData = (BYTE *)*((_QWORD *)v82 + 12),
        !(unsigned int)Pku2uGetSharedKey(Pku2uGlobalDHKey, &v109, &v119)) )
  {
LABEL_86:
    v25 = 60;
LABEL_87:
    v12 = v25;
    goto LABEL_41;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  KerbConvertGeneralizedTimeToLargeInt(
    &Time,
    (struct tagASN1generalizedtime_t *)((char *)v82 + 16),
    *((_DWORD *)v82 + 3));
  if ( Time.QuadPart > *(_QWORD *)&SystemTimeAsFileTime + Pku2uGlobalSkewTime.QuadPart
    || Time.QuadPart < *(_QWORD *)&SystemTimeAsFileTime - Pku2uGlobalSkewTime.QuadPart )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
    v25 = 37;
    goto LABEL_87;
  }
  v34 = KerbConvertCryptListToArray(&v97, &v87, v20[14]);
  v12 = v34;
  if ( !v34 )
  {
    v76 = v97;
    if ( (int)CDFindCommonCSystem(v87, v97, &v79) < 0 )
      goto LABEL_95;
    v37 = WSTRandomFill(v170, 32);
    inited = v37;
    if ( v37 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids,
          (unsigned int)v37);
      goto LABEL_42;
    }
    Key = KerbMakeKeyEx(
            v79,
            *((_DWORD *)v82 + 28),
            *((unsigned __int8 **)v82 + 15),
            0x20u,
            v170,
            v119.cbData,
            v119.pbData,
            (struct KERB_ENCRYPTION_KEY *)&v133);
    v12 = Key;
    if ( Key )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids, Key);
      goto LABEL_40;
    }
    v39 = (char *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, 0x20u);
    v78 = (struct PKERB_AUTHORIZATION_DATA *)v39;
    v8 = (struct PKERB_AUTHORIZATION_DATA *)v39;
    if ( !v39 )
    {
      v15 = 60;
      v12 = 60;
      goto LABEL_10;
    }
    *(_QWORD *)(v39 + 12) = 0;
    *(_QWORD *)(v39 + 20) = 0;
    *((_DWORD *)v39 + 7) = 0;
    *(_QWORD *)v39 = 0;
    *((_DWORD *)v39 + 2) = 17;
    v40 = *((_DWORD *)v82 + 8);
    DWORD2(v154) = 8 * pcbEncoded[0];
    DWORD2(v155) = v40;
    *(_QWORD *)&v155 = *(_QWORD *)&pcbEncoded[2];
    v41 = KerbPackData(&v154, 0xFu, (unsigned int *)v114, &v114[1]);
    v12 = v41;
    if ( v41 )
    {
      v15 = v41;
      goto LABEL_10;
    }
    inited = Pku2uImpersonateToken(*(HANDLE *)(*(_QWORD *)(*((_QWORD *)a1 + 2) + 24LL) + 32LL), &Token, &v80);
    if ( inited < 0 )
    {
      v9 = Token;
      goto LABEL_4;
    }
    v42 = *((_QWORD *)a1 + 2);
    if ( *(_DWORD *)(v42 + 32) )
    {
      v42 = *((_QWORD *)a1 + 4);
      if ( !v42 )
      {
        inited = -2146893042;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
        v9 = Token;
        v8 = v78;
        goto LABEL_4;
      }
    }
    v43 = v42 + 40;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v43);
    inited = ScHelperPeer2PeerSignPkcsMessage(
               *(PCCERT_CONTEXT *)(v43 + 120),
               *(const struct _CERT_CHAIN_CONTEXT **)(v43 + 128),
               v105,
               "1.3.6.1.5.2.3.2",
               v114[1],
               (unsigned int)v114[0],
               &v115[1],
               (unsigned int *)v115);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v43);
    hObject = Token;
    if ( v80 )
    {
      Pku2uRevertImpersonation(Token);
      v80 = 0;
    }
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v44 = GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids,
          (unsigned int)inited,
          v44);
      }
      goto LABEL_42;
    }
    *((unsigned __int8 **)&v131 + 1) = v115[1];
    LODWORD(v131) = v115[0];
    WORD4(v130) |= 0x80u;
    *((_QWORD *)&v132 + 1) = v170;
    LOWORD(v130) = 1;
    LODWORD(v132) = 32;
    v26 = KerbPackData(&v130, 0x26u, (unsigned int *)v78 + 4, (unsigned __int8 **)v78 + 3);
    v12 = v26;
    if ( v26 )
      goto LABEL_44;
    v158 = 32;
    v159 = &v94;
    v166 = 32;
    v167 = &v108;
    v140 = &v157;
    inited = CDBuildIntegrityVect(&v88, v169);
    if ( inited < 0 )
    {
LABEL_60:
      v12 = 60;
      goto LABEL_42;
    }
    v46 = KerbConvertArrayToCryptList(&v98, v169, v88, v45);
    v12 = v46;
    if ( v46 )
    {
      v47 = KerbMapKerbError(v46);
      v48 = v98;
      inited = v47;
      v8 = v78;
      v9 = hObject;
      v13 = 0;
      v31 = pCertContext;
      v36 = v76;
      goto LABEL_189;
    }
    v49 = (__int64 *)*((_QWORD *)v81 + 17);
    v50 = v98;
    v75 = v98;
    v79 = 0;
LABEL_126:
    if ( !v49 )
    {
LABEL_95:
      v25 = 14;
      goto LABEL_87;
    }
    while ( 1 )
    {
      if ( !v50 )
      {
        v49 = (__int64 *)*v49;
        v50 = v98;
        goto LABEL_126;
      }
      if ( *((_DWORD *)v49 + 2) == *((_DWORD *)v50 + 2) )
        break;
      v50 = *(struct KERB_KDC_REQUEST_BODY_encryption_type **)v50;
    }
    v79 = *((_DWORD *)v49 + 2);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v43);
    v51 = (struct KERB_ENCRYPTION_KEY **)(v43 + 144);
    if ( !*(_QWORD *)(v43 + 144) )
    {
      v12 = Pku2uBuildPeer2PeerKeys((unsigned int *)(v43 + 136), (struct KERB_ENCRYPTION_KEY **)(v43 + 144));
      if ( v12 )
      {
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v43);
        goto LABEL_40;
      }
    }
    if ( *(_DWORD *)(v43 + 136) && *v51 )
    {
      v12 = KerbDuplicateKey((struct KERB_ENCRYPTION_KEY *)&v120, *v51);
      v113 = v121;
    }
    else
    {
      v12 = 45;
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v43);
    if ( v12 )
      goto LABEL_40;
    NtQuerySystemTime(&SystemTime);
    KerbConvertLargeIntToGeneralizedTime((struct tagASN1generalizedtime_t *)v162, 0, &SystemTime);
    v52 = 8;
    p_SystemTime = &SystemTime;
    do
    {
      LOBYTE(p_SystemTime->LowPart) = 0;
      p_SystemTime = (union _LARGE_INTEGER *)((char *)p_SystemTime + 1);
      --v52;
    }
    while ( v52 );
    KerbConvertGeneralizedTimeToLargeInt(&SystemTime, (struct tagASN1generalizedtime_t *)v162, 0);
    v54 = Pku2uCreatePac(&SystemTime, 0, pCertContext, &v126, &Src);
    v12 = v54;
    if ( v54
      || (v54 = KerbConvertStringToKdcName(&v104, &v126), (v12 = v54) != 0)
      || ((*((_BYTE *)v81 + 24) & 8) == 0 ? (v56 = 0) : (v56 = (struct PKERB_HOST_ADDRESSES *)*((_QWORD *)v81 + 18)),
          v57 = v93,
          v54 = Pku2uBuildTicketAS(
                  v104,
                  v56,
                  &SystemTime,
                  (union _LARGE_INTEGER *)&pCertContext->pCertInfo->NotAfter,
                  v93,
                  v79,
                  (struct KERB_TICKET *)v137),
          (v12 = v54) != 0) )
    {
      v55 = KerbMapKerbError(v54);
      v13 = Src;
LABEL_143:
      v8 = v78;
      inited = v55;
      goto LABEL_185;
    }
    v13 = Src;
    Size = PAC_GetSize(Src);
    LODWORD(v123[0]) = Size;
    DWORD2(v122) = 128;
    v59 = (unsigned __int8 *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, Size);
    v123[1] = v59;
    if ( v59 )
    {
      PAC_Marshal(v13, Size, v59);
      v61 = Pku2uSignPac((struct KERB_ENCRYPTION_KEY *)&v120, (unsigned int)v123[0], v123[1]);
      v12 = v61;
      if ( !v61 )
      {
        inserted = Pku2uInsertPacIntoAuthData(0, v62, (struct PKERB_AUTHORIZATION_DATA *)&v122, &v163);
        v12 = inserted;
        if ( inserted )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              36,
              &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids,
              inserted);
          v60 = v12;
          goto LABEL_151;
        }
        v157 |= 0x10u;
        v61 = Pku2uBuildReply(
                *((_DWORD *)v57 + 27),
                (struct KERB_PRINCIPAL_NAME *)v139,
                v138,
                (struct KERB_TICKET *)v137,
                (struct KERB_ENCRYPTED_KDC_REPLY *)v164);
        v12 = v61;
        if ( !v61 )
        {
          v145 = v160;
          v141[0] = 128;
          v8 = 0;
          v144 = v78;
          v142 = 5;
          v143 = 11;
          v65 = KerbPackTicket(
                  (struct KERB_TICKET *)v137,
                  (struct KERB_ENCRYPTION_KEY *)&v120,
                  v64,
                  (struct KERB_TICKET *)v147);
          v12 = v65;
          if ( v65 )
          {
            inited = KerbMapKerbError(v65);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_185;
            v68 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v69 = 37;
          }
          else
          {
            v146 = v161;
            v70 = KerbPackKdcReplyBody(
                    (struct KERB_ENCRYPTED_KDC_REPLY *)v164,
                    (struct KERB_ENCRYPTION_KEY *)&v133,
                    v66,
                    v67,
                    v73,
                    (struct KERB_ENCRYPTED_DATA *)v151);
            v12 = v70;
            if ( !v70 )
            {
              v71 = KerbPackData(v141, 0x2Bu, &v89, &v99);
              v12 = v71;
              if ( v71 )
              {
                inited = KerbMapKerbError(v71);
                v107 = v99;
              }
              else
              {
                v107 = v99;
                v12 = 0;
                inited = Pku2uPackContextLevelToken(v99, v89, 1536, v125, v124);
                if ( inited < 0 )
                  v12 = 60;
              }
              goto LABEL_185;
            }
            inited = KerbMapKerbError(v70);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
LABEL_185:
              v9 = hObject;
              goto LABEL_186;
            }
            v68 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v69 = 38;
          }
          WPP_SF_d(v68, v69, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids, v12);
          goto LABEL_185;
        }
      }
      v60 = v61;
    }
    else
    {
      v60 = 60;
      v12 = 60;
    }
LABEL_151:
    v55 = KerbMapKerbError(v60);
    goto LABEL_143;
  }
  v35 = KerbMapKerbError(v34);
  v36 = v97;
  inited = v35;
  v8 = 0;
  v9 = 0;
  v13 = 0;
  v31 = pCertContext;
LABEL_188:
  v48 = v75;
LABEL_189:
  *v112 = v12;
  KerbFreeCryptList(v48);
  if ( v80 )
    Pku2uRevertImpersonation(v9);
  if ( v9 )
    CloseHandle(v9);
  if ( v81 )
    KerbFreeData(0x2Fu, v81);
  if ( v8 )
    KerbFreeAuthData(v8);
  if ( v100 )
    KerbFreeData(0x12u, v100);
  KerbFreeString(&DomainName2);
  KerbFreeKdcName(&v101);
  if ( v102 )
    ScHelperFree(v102);
  if ( v82 )
    KerbFreeData(0x29u, v82);
  if ( v31 )
    CertFreeCertificateContext(v31);
  if ( v36 )
    Pku2uFree(v36);
  if ( *(_QWORD *)&pcbEncoded[2] )
    Pku2uFree(*(void **)&pcbEncoded[2]);
  if ( v119.pbData )
    Pku2uFree(v119.pbData);
  Pku2uFreeDHParameters(&v153);
  if ( v114[1] )
    Pku2uFree(v114[1]);
  if ( v115[1] )
    ScHelperFree(v115[1]);
  if ( v113 )
    KerbFreeKey((struct KERB_ENCRYPTION_KEY *)&v120);
  if ( v123[1] )
    Pku2uFree(v123[1]);
  if ( v13 )
    Pku2uFree(v13);
  KerbFreeInternalTicket((struct KERB_TICKET *)v137);
  if ( v103 )
    KerbFreeKdcName(&v92);
  if ( v110.Buffer )
    KerbFreeString(&v110);
  KerbFreeString2(&v126);
  KerbFreeKdcName(&v104);
  if ( v105 )
    ScHelperFree(v105);
  KerbFreeKey((struct KERB_ENCRYPTION_KEY *)&v133);
  if ( v165 )
  {
    Pku2uFree(v165);
    v165 = 0;
  }
  v168 = 0;
  KerbFreePrincipalName((struct KERB_PRINCIPAL_NAME *)v149);
  KerbFreeKdcName(&v148);
  if ( v150 )
    Pku2uFree(v150);
  if ( v152 )
    Pku2uFree(v152);
  if ( v144 )
    KerbFreeAuthData(v144);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( v107 )
    Pku2uFree(v107);
  if ( v127.Buffer )
    KerbFreeString(&v127);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180035dc0  push    rbp
0x180035dc2  push    rbx
0x180035dc3  push    rsi
0x180035dc4  push    rdi
0x180035dc5  push    r12
0x180035dc7  push    r13
0x180035dc9  push    r14
0x180035dcb  push    r15
0x180035dcd  lea     rbp, [rsp-528h]
0x180035dd5  sub     rsp, 628h
0x180035ddc  mov     rax, cs:__security_cookie
0x180035de3  xor     rax, rsp
0x180035de6  mov     [rbp+560h+var_50], rax
0x180035ded  mov     rsi, [rbp+560h+arg_20]
0x180035df4  lea     rax, WideCharStr; "WELLKNOWN:PKU2U"
0x180035dfb  mov     r15, [rbp+560h+arg_28]
0x180035e02  xor     edi, edi
0x180035e04  mov     ebx, r8d
0x180035e07  mov     [rbp+560h+var_590], rdx
0x180035e0b  mov     r12, rcx
0x180035e0e  mov     [rbp+560h+var_4E8], r9
0x180035e12  xorps   xmm0, xmm0
0x180035e15  mov     [rbp+560h+var_438], rsi
0x180035e1c  lea     r8d, [rdi+48h]; Size
0x180035e20  mov     [rbp+560h+var_440], r15
0x180035e27  xor     edx, edx; Val
0x180035e29  mov     [rbp+560h+var_5C0], ebx
0x180035e2c  lea     rcx, [rbp+560h+var_390]; void *
0x180035e33  mov     [rbp+560h+var_5D8], rdi
0x180035e37  mov     qword ptr [rbp+560h+DomainName1.Length], 20001Eh
0x180035e42  mov     [rbp+560h+DomainName1.Buffer], rax
0x180035e49  movups  xmmword ptr [rbp+560h+DomainName2.Length], xmm0
0x180035e50  mov     [rbp+560h+var_550], rdi
0x180035e54  call    memset_0
0x180035e59  xor     edx, edx; Val
0x180035e5b  lea     rcx, [rbp+560h+var_220]; void *
0x180035e62  mov     r8d, 0A8h; Size
0x180035e68  call    memset_0
0x180035e6d  xorps   xmm0, xmm0
0x180035e70  mov     [rbp+560h+var_558], rdi
0x180035e74  xor     eax, eax
0x180035e76  mov     [rbp+560h+var_548], rdi
0x180035e7a  xorps   xmm1, xmm1
0x180035e7d  mov     [rbp+560h+var_3A0], rax
0x180035e84  xor     edx, edx; Val
0x180035e86  mov     [rsp+660h+var_608], rax
0x180035e8b  lea     r8d, [rdi+40h]; Size
0x180035e8f  mov     [rbp+560h+var_568], rax
0x180035e93  lea     rcx, [rbp+560h+var_2A0.p.pbData]; void *
0x180035e9a  mov     [rbp+560h+var_4E0], rax
0x180035ea1  movups  xmmword ptr [rbp+560h+var_420.Length], xmm0
0x180035ea8  mov     [rbp+560h+var_468], rax
0x180035eaf  mov     r13d, edi
0x180035eb2  movups  [rbp+560h+var_3B0], xmm0
0x180035eb9  mov     [rbp+560h+var_540], rax
0x180035ebd  movups  [rbp+560h+var_250], xmm0
0x180035ec4  mov     [rbp+560h+var_598], rax
0x180035ec8  movups  [rbp+560h+var_240], xmm0
0x180035ecf  mov     [rsp+660h+var_5F0], rax
0x180035ed4  movups  [rbp+560h+var_230], xmm0
0x180035edb  mov     [rbp+560h+Src], rax
0x180035edf  movups  xmmword ptr [rbp+560h+var_4D8], xmm0
0x180035ee6  mov     [rbp+560h+var_5B8], edi
0x180035ee9  movups  xmmword ptr [rbp+560h+var_4C8], xmm1
0x180035ef0  mov     [rsp+660h+pCertContext], rdi
0x180035ef5  movups  [rbp+560h+var_478], xmm0
0x180035efc  mov     [rbp+560h+var_580], rdi
0x180035f00  movups  [rbp+560h+var_460], xmm0
0x180035f07  mov     [rbp+560h+var_40C], edi
0x180035f0d  movups  xmmword ptr [rbp+560h+var_450], xmm0
0x180035f14  mov     [rbp+560h+var_404], edi
0x180035f1a  mov     [rbp+560h+var_530], rdi
0x180035f1e  mov     [rbp+560h+var_5D0], rdi
0x180035f22  mov     [rsp+660h+var_5E8], rdi
0x180035f27  mov     [rbp+560h+var_5B0], 14h
0x180035f2e  mov     dword ptr [rbp+560h+var_510+4], edi
0x180035f31  mov     qword ptr [rbp+560h+var_2A0.p.cbData], rdi
0x180035f38  call    memset_0
0x180035f3d  xorps   xmm1, xmm1
0x180035f40  mov     qword ptr [rbp+560h+Time], rdi
0x180035f44  xorps   xmm0, xmm0
0x180035f47  mov     qword ptr [rbp+560h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180035f4b  mov     edx, edi; Val
0x180035f4d  mov     [rbp+560h+var_5B4], edi
0x180035f50  xor     eax, eax
0x180035f52  mov     [rsp+660h+var_600], rdx
0x180035f57  movups  xmmword ptr [rbp+560h+pcbEncoded], xmm0
0x180035f5e  mov     [rbp+560h+var_570], rdx
0x180035f62  movups  xmmword ptr [rbp+560h+var_488.cbData], xmm1
0x180035f69  mov     [rbp+560h+var_3B8], rax
0x180035f70  movups  [rbp+560h+var_3C8], xmm0
0x180035f77  mov     [rbp+560h+var_5E0], edi
0x180035f7a  movups  [rbp+560h+var_3F8], xmm1
0x180035f81  movups  [rbp+560h+var_3E8], xmm1
0x180035f88  mov     r8d, 0B0h; Size
0x180035f8e  mov     [rbp+560h+var_588], edi
0x180035f91  lea     rcx, [rbp+560h+var_170]; void *
0x180035f98  mov     [rbp+560h+var_518], edi
0x180035f9b  movups  [rbp+560h+var_3D8], xmm1
0x180035fa2  call    memset_0
0x180035fa7  xor     edx, edx; Val
0x180035fa9  lea     rcx, [rbp+560h+var_340]; void *
0x180035fb0  mov     r8d, 98h; Size
0x180035fb6  call    memset_0
0x180035fbb  mov     eax, edi
0x180035fbd  mov     [rbp+560h+hCertStore], rdi
0x180035fc1  mov     [rbp+560h+var_520], rax
0x180035fc5  lea     r8, [rbp+560h+var_590]; unsigned __int8 **
0x180035fc9  mov     [rbp+560h+var_560], rax
0x180035fcd  lea     rdx, [rbp+560h+var_5C0]; int *
0x180035fd1  mov     rax, [rbp+560h+var_4E8]
0x180035fd5  xorps   xmm0, xmm0
0x180035fd8  xorps   xmm1, xmm1
0x180035fdb  mov     [rbp+560h+var_538], rdi
0x180035fdf  mov     r9d, 500h; int
0x180035fe5  mov     [rbp+560h+var_5AC], edi
0x180035fe8  movups  xmmword ptr [rbp+560h+var_500.Length], xmm0
0x180035fec  mov     [rax], edi
0x180035fee  mov     r14d, edi
0x180035ff1  mov     [r15], edi
0x180035ff4  mov     [rsi], rdi
0x180035ff7  movups  xmmword ptr [rbp+560h+var_430.Length], xmm1
0x180035ffe  mov     qword ptr [rbp+560h+SystemTime], rdi
0x180036002  mov     [rsp+660h+hObject], rdi
0x180036007  mov     [rbp+560h+Token], rdi
0x18003600b  mov     [rbp+560h+var_5DC], edi
0x18003600e  mov     [rbp+560h+var_5BC], edi
0x180036011  mov     dword ptr [rsp+660h+var_640], ebx; int
0x180036015  call    ?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z; g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)
0x18003601a  test    eax, eax
0x18003601c  jnz     short loc_180036032
0x18003601e  mov     edi, 118h
0x180036023  mov     ebx, 3Ch ; '<'
0x180036028  mov     r12, [rsp+660h+var_5F0]
0x18003602d  jmp     loc_180036E6D
0x180036032  mov     edx, [rbp+560h+var_5C0]; unsigned int
0x180036035  lea     r9, [rbp+560h+var_5D8]; void **
0x180036039  mov     rcx, [rbp+560h+var_590]; unsigned __int8 *
0x18003603d  mov     r8d, 2Fh ; '/'; unsigned int
0x180036043  call    ?KerbUnpackData@@YAJPEAEKKPEAPEAX@Z; KerbUnpackData(uchar *,ulong,ulong,void * *)
0x180036048  mov     ebx, eax
0x18003604a  test    eax, eax
0x18003604c  jz      short loc_18003608E
0x18003604e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036055  lea     r14, WPP_GLOBAL_Control
0x18003605c  cmp     rcx, r14
0x18003605f  jz      short loc_180036082
0x180036061  mov     esi, 1
0x180036066  test    [rcx+1Ch], sil
0x18003606a  jz      short loc_180036082
0x18003606c  mov     rcx, [rcx+10h]
0x180036070  lea     edx, [rsi+12h]
0x180036073  mov     r9d, eax
0x180036076  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x18003607d  call    WPP_SF_d
0x180036082  mov     ecx, ebx; int
0x180036084  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x180036089  jmp     loc_180036E61
0x18003608e  mov     rdx, [rbp+560h+var_5D8]
0x180036092  mov     r9d, [rdx+4]
0x180036096  cmp     r9d, 5
0x18003609a  jz      short loc_1800360D4
0x18003609c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360a3  lea     r14, WPP_GLOBAL_Control
0x1800360aa  cmp     rcx, r14
0x1800360ad  jz      short loc_1800360CD
0x1800360af  mov     esi, 1
0x1800360b4  test    [rcx+1Ch], sil
0x1800360b8  jz      short loc_1800360CD
0x1800360ba  mov     rcx, [rcx+10h]
0x1800360be  lea     edx, [rsi+13h]
0x1800360c1  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x1800360c8  call    WPP_SF_d
0x1800360cd  mov     ebx, 27h ; '''
0x1800360d2  jmp     short loc_180036082
0x1800360d4  add     rdx, 40h ; '@'; char **
0x1800360d8  lea     rcx, [rbp+560h+DomainName2]; struct _UNICODE_STRING *
0x1800360df  call    ?KerbConvertRealmToUnicodeString@@YAJPEAU_UNICODE_STRING@@PEAPEAD@Z; KerbConvertRealmToUnicodeString(_UNICODE_STRING *,char * *)
0x1800360e4  mov     ebx, eax
0x1800360e6  test    eax, eax
0x1800360e8  jz      short loc_1800360F8
0x1800360ea  mov     ecx, eax; int
0x1800360ec  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x1800360f1  mov     edi, eax
0x1800360f3  jmp     loc_180036028
0x1800360f8  lea     rdx, [rbp+560h+DomainName2]; DomainName2
0x1800360ff  lea     rcx, [rbp+560h+DomainName1]; DomainName1
0x180036106  call    cs:__imp_RtlEqualDomainName
0x18003610c  test    al, al
0x18003610e  jnz     short loc_180036152
0x180036110  mov     rcx, cs:WPP_GLOBAL_Control
0x180036117  lea     r14, WPP_GLOBAL_Control
0x18003611e  cmp     rcx, r14
0x180036121  jz      short loc_180036148
0x180036123  mov     esi, 1
0x180036128  test    [rcx+1Ch], sil
0x18003612c  jz      short loc_180036148
0x18003612e  mov     rcx, [rcx+10h]; LoggerHandle
0x180036132  lea     edx, [rsi+14h]
0x180036135  lea     r9, [rbp+560h+DomainName2]
0x18003613c  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x180036143  call    WPP_SF_Z
0x180036148  mov     ebx, 44h ; 'D'
0x18003614d  jmp     loc_180036082
0x180036152  mov     rdx, [rbp+560h+var_5D8]
0x180036156  lea     rcx, [rbp+560h+var_550]; struct _KERB_INTERNAL_NAME **
0x18003615a  add     rdx, 48h ; 'H'; struct KERB_PRINCIPAL_NAME *
0x18003615e  call    ?KerbConvertPrincipalNameToKdcName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToKdcName(_KERB_INTERNAL_NAME * *,KERB_PRINCIPAL_NAME *)
0x180036163  mov     ebx, eax
0x180036165  test    eax, eax
0x180036167  jnz     short loc_1800360EA
0x180036169  mov     rdx, [rbp+560h+var_550]; struct _KERB_INTERNAL_NAME *
0x18003616d  lea     rcx, [rbp+560h+var_420]; struct _UNICODE_STRING *
0x180036174  call    ?KerbConvertKdcNameToString@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z; KerbConvertKdcNameToString(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)
0x180036179  mov     ebx, eax
0x18003617b  test    eax, eax
0x18003617d  jnz     loc_1800360EA
0x180036183  cmp     cs:?Pku2uGlobalDHInitialized@@3HA, edi; int Pku2uGlobalDHInitialized
0x180036189  jnz     short loc_18003619A
0x18003618b  call    ?Pku2uInitDH@@YAJXZ; Pku2uInitDH(void)
0x180036190  mov     edi, eax
0x180036192  test    eax, eax
0x180036194  js      loc_180036023
0x18003619a  mov     r13, [rbp+560h+var_5D8]
0x18003619e  add     r13, 18h
0x1800361a2  mov     [rbp+560h+var_590], r13
0x1800361a6  test    byte ptr [r13+0], 80h
0x1800361ab  jnz     short loc_1800361C3
0x1800361ad  mov     ebx, 6
0x1800361b2  mov     ecx, ebx; int
0x1800361b4  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x1800361b9  mov     edi, eax
0x1800361bb  mov     r13, r14
0x1800361be  jmp     loc_180036028
0x1800361c3  lea     rdx, [r13+18h]; struct KERB_PRINCIPAL_NAME *
0x1800361c7  lea     rcx, [rbp+560h+var_598]; struct _KERB_INTERNAL_NAME **
0x1800361cb  call    ?KerbConvertPrincipalNameToKdcName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToKdcName(_KERB_INTERNAL_NAME * *,KERB_PRINCIPAL_NAME *)
0x1800361d0  mov     ebx, eax
0x1800361d2  test    eax, eax
0x1800361d4  mov     rax, [rbp+560h+var_598]
0x1800361d8  mov     [rbp+560h+var_540], rax
0x1800361dc  jz      short loc_1800361E5
0x1800361de  mov     edi, 0C000009Ah
0x1800361e3  jmp     short loc_1800361BB
0x1800361e5  mov     rdx, rax; struct _KERB_INTERNAL_NAME *
0x1800361e8  lea     rcx, [rbp+560h+var_500]; struct _UNICODE_STRING *
0x1800361ec  call    ?KerbConvertKdcNameToString@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z; KerbConvertKdcNameToString(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)
0x1800361f1  mov     ebx, eax
0x1800361f3  test    eax, eax
0x1800361f5  jz      short loc_1800361FB
0x1800361f7  mov     ecx, eax
0x1800361f9  jmp     short loc_1800361B4
0x1800361fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180036202  lea     r14, WPP_GLOBAL_Control
0x180036209  lea     r15, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x180036210  cmp     rcx, r14
0x180036213  jz      short loc_180036230
0x180036215  test    byte ptr [rcx+1Ch], 4
0x180036219  jz      short loc_180036230
0x18003621b  mov     rcx, [rcx+10h]; LoggerHandle
0x18003621f  lea     r9, [rbp+560h+var_500]
0x180036223  mov     edx, 16h
0x180036228  mov     r8, r15
0x18003622b  call    WPP_SF_Z
0x180036230  mov     rdx, [rbp+560h+var_5D8]
0x180036234  mov     ecx, 10h; unsigned int
0x180036239  mov     rdx, [rdx+10h]; struct KERB_KDC_REQUEST_preauth_data *
0x18003623d  call    ?KerbFindPreAuthDataEntry@@YAPEAUKERB_PA_DATA@@KPEAUKERB_KDC_REQUEST_preauth_data@@@Z; KerbFindPreAuthDataEntry(ulong,KERB_KDC_REQUEST_preauth_data *)
0x180036242  test    rax, rax
0x180036245  jnz     short loc_18003625D
0x180036247  lea     ebx, [rax+19h]
0x18003624a  mov     ecx, ebx; int
0x18003624c  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x180036251  mov     edi, eax
0x180036253  mov     r13, [rsp+660h+var_5E8]
0x180036258  jmp     loc_180036E63
0x18003625d  mov     edx, [rax+8]; unsigned int
0x180036260  lea     r9, [rbp+560h+var_558]; void **
0x180036264  mov     rcx, [rax+10h]; unsigned __int8 *
0x180036268  mov     r8d, 12h; unsigned int
0x18003626e  call    ?KerbUnpackData@@YAJPEAEKKPEAPEAX@Z; KerbUnpackData(uchar *,ulong,ulong,void * *)
0x180036273  mov     ebx, eax
0x180036275  test    eax, eax
0x180036277  jz      short loc_18003627D
0x180036279  mov     ecx, eax
0x18003627b  jmp     short loc_18003624C
0x18003627d  mov     rcx, [rbp+560h+var_558]
0x180036281  lea     rax, [rbp+560h+var_530]
0x180036285  mov     [rsp+660h+var_620], rax; struct _CRYPT_ALGORITHM_IDENTIFIER **
0x18003628a  lea     r9, a13615231; "1.3.6.1.5.2.3.1"
0x180036291  lea     rax, [rbp+560h+hCertStore]
0x180036295  mov     [rsp+660h+var_628], rax; void **
0x18003629a  lea     rax, [rbp+560h+var_580]
0x18003629e  mov     edx, [rcx+8]; cbSignedBlob
0x1800362a1  mov     rcx, [rcx+10h]; pbSignedBlob
0x1800362a5  mov     [rsp+660h+var_630], rax; struct _CERT_CONTEXT **
0x1800362aa  lea     rax, [rbp+560h+var_5B8]
0x1800362ae  mov     [rsp+660h+var_638], rax; unsigned int *
0x1800362b3  lea     rax, [rbp+560h+var_548]
0x1800362b7  mov     [rsp+660h+var_640], rax; unsigned __int8 **
  ... truncated ...
```
