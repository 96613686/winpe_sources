# Pku2uBuildPeer2PeerAsRequest(_PKU2U_CONTEXT *,KERB_ERROR *,uchar * *,ulong *)

- ea: `0x18000fc70`
- end: `0x180010d9e`
- name: `?Pku2uBuildPeer2PeerAsRequest@@YAJPEAU_PKU2U_CONTEXT@@PEAUKERB_ERROR@@PEAPEAEPEAK@Z`
- size: `4398`
- prototype: `__int64 __fastcall(struct _PKU2U_CONTEXT *, struct KERB_ERROR *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001cc90`

## callees

- `0x1800057f0`
- `0x180007dc8`
- `0x18000fc70`
- `0x180010db0`
- `0x180010e50`
- `0x180010ea4`
- `0x180011060`
- `0x180011170`
- `0x180011410`
- `0x180011880`
- `0x180013b20`
- `0x180016a10`
- `0x1800178d0`
- `0x180017df0`
- `0x180018618`
- `0x180018870`
- `0x18001fbc0`
- `0x18001ff04`
- `0x1800210f0`
- `0x180021a54`
- `0x180023cb8`
- `0x180023ce0`
- `0x18002b408`
- `0x1800313ec`
- `0x180031430`
- `0x1800370d0`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fd93`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fd93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010d93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010d93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010378`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010378`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180010b3d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180010b3d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010ad2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010ad2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180010af5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180010af5`
- `MSASN1!ASN1_CreateEncoder` at `0x1800108db`
- `MSASN1!ASN1_CreateEncoder` at `0x1800108db`
- `MSASN1!ASN1_CloseEncoder` at `0x180010a26`
- `MSASN1!ASN1_CloseEncoder` at `0x180010a26`
- `MSASN1!ASN1_Encode` at `0x180010945`
- `MSASN1!ASN1_Encode` at `0x180010945`
- `MSASN1!ASN1_FreeEncoded` at `0x180010a16`
- `MSASN1!ASN1_FreeEncoded` at `0x180010a16`
- `MSASN1!ASN1_CreateModule` at `0x1800108b2`
- `MSASN1!ASN1_CreateModule` at `0x1800108b2`
- `ntdll!RtlLeaveCriticalSection` at `0x180010614`
- `ntdll!RtlLeaveCriticalSection` at `0x180010640`
- `ntdll!RtlLeaveCriticalSection` at `0x18001072a`
- `ntdll!RtlLeaveCriticalSection` at `0x180010a33`
- `ntdll!RtlLeaveCriticalSection` at `0x180010c3b`
- `ntdll!RtlLeaveCriticalSection` at `0x180010614`
- `ntdll!RtlLeaveCriticalSection` at `0x180010640`
- `ntdll!RtlLeaveCriticalSection` at `0x18001072a`
- `ntdll!RtlLeaveCriticalSection` at `0x180010a33`
- `ntdll!RtlLeaveCriticalSection` at `0x180010c3b`
- `ntdll!RtlEnterCriticalSection` at `0x1800105cb`
- `ntdll!RtlEnterCriticalSection` at `0x180010bf5`
- `ntdll!RtlEnterCriticalSection` at `0x1800105cb`
- `ntdll!RtlEnterCriticalSection` at `0x180010bf5`
- `ntdll!RtlTimeToTimeFields` at `0x180010146`
- `ntdll!RtlTimeToTimeFields` at `0x1800101ff`
- `ntdll!RtlTimeToTimeFields` at `0x180010146`
- `ntdll!RtlTimeToTimeFields` at `0x1800101ff`
- `ntdll!NtSetInformationThread` at `0x180010bd0`
- `ntdll!NtSetInformationThread` at `0x180010bd0`
- `ntdll!NtOpenThreadToken` at `0x180010b86`
- `ntdll!NtOpenThreadToken` at `0x180010b86`
- `CRYPTSP!CryptDestroyKey` at `0x1800105f4`
- `CRYPTSP!CryptDestroyKey` at `0x1800105f4`
- `cryptdll!CDGenerateRandomBits` at `0x18001055e`
- `cryptdll!CDGenerateRandomBits` at `0x18001055e`
- `cryptdll!CDLocateCheckSum` at `0x1800106a1`
- `cryptdll!CDLocateCheckSum` at `0x1800106a1`
- `cryptdll!CDBuildIntegrityVect` at `0x1800103f7`
- `cryptdll!CDBuildIntegrityVect` at `0x1800103f7`

## pseudocode

```c
__int64 __fastcall Pku2uBuildPeer2PeerAsRequest(
        struct _PKU2U_CONTEXT *a1,
        struct KERB_ERROR *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  struct _KERB_INTERNAL_NAME *v6; // rsi
  void *v7; // r14
  unsigned __int8 *v8; // r15
  unsigned __int8 *v9; // r12
  int inited; // ebx
  int v11; // r8d
  struct _FILETIME v12; // rax
  __int64 v13; // rax
  struct _KERB_INTERNAL_NAME *v14; // rcx
  __int64 *v15; // r14
  void *v16; // r15
  unsigned int v17; // ebx
  __int64 v18; // rdi
  char *v19; // rax
  char *v20; // rsi
  __int64 v21; // rax
  __int64 *v22; // rax
  __int16 *v23; // rsi
  __int64 *v24; // r15
  unsigned int v25; // ebx
  void *v26; // r12
  char *v27; // rax
  char *v28; // r14
  __int64 v29; // rax
  __int64 *v30; // rax
  union _LARGE_INTEGER v31; // rax
  int v32; // eax
  struct PKERB_HOST_ADDRESSES *v33; // r13
  char *v34; // rax
  unsigned int v36; // r14d
  struct KERB_KDC_REQUEST_BODY_encryption_type *v37; // r15
  _QWORD *v38; // rdi
  unsigned int i; // ebx
  int v40; // eax
  __int64 v41; // rax
  struct KERB_KDC_REQUEST_BODY_encryption_type *v42; // rbx
  __int64 v43; // r14
  __int64 v44; // rbx
  __int64 v45; // rcx
  int v46; // edx
  struct _CERT_X942_DH_PARAMETERS *v47; // rcx
  int DHKey; // edi
  void *v49; // rdi
  void *v50; // r12
  int v51; // esi
  __int64 (__fastcall *v52)(void *, _QWORD, _QWORD, __int64, struct _UNICODE_STRING *); // rax
  int v53; // eax
  __int64 (__fastcall *v54)(void *, _QWORD, __int64, struct _UNICODE_STRING *); // rax
  int v55; // eax
  int v56; // esi
  unsigned int v57; // r15d
  __int64 Module; // rax
  unsigned int v59; // eax
  int v60; // ebx
  int v61; // eax
  size_t v62; // rbx
  unsigned __int8 *v63; // rdi
  struct PKERB_HOST_ADDRESSES *v64; // rcx
  unsigned __int8 *v65; // rax
  __int64 v66; // rax
  __int64 v67; // rcx
  void *v68; // rdi
  void *v69; // r14
  DWORD LastError; // eax
  bool v71; // sf
  NTSTATUS v72; // eax
  PRTL_CRITICAL_SECTION v73; // r14
  DWORD v74; // eax
  struct PKERB_AUTHORIZATION_DATA *v75; // rax
  unsigned __int8 *v76; // rcx
  int v77; // [rsp+60h] [rbp-A0h] BYREF
  struct PKERB_HOST_ADDRESSES *v78; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING IsMember; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 *v80; // [rsp+80h] [rbp-80h] BYREF
  int v81; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v82; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v83; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v84; // [rsp+94h] [rbp-6Ch] BYREF
  struct _KERB_INTERNAL_NAME *v85; // [rsp+98h] [rbp-68h] BYREF
  union _LARGE_INTEGER Time; // [rsp+A0h] [rbp-60h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v88; // [rsp+B0h] [rbp-50h] BYREF
  void *v89; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *v90; // [rsp+C0h] [rbp-40h]
  void *v91; // [rsp+C8h] [rbp-38h]
  void *ThreadInformation; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 *Src; // [rsp+D8h] [rbp-28h] BYREF
  void *v94[2]; // [rsp+E0h] [rbp-20h]
  DWORD pcbEncoded[4]; // [rsp+F0h] [rbp-10h] BYREF
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+100h] [rbp+0h]
  unsigned int *v97; // [rsp+108h] [rbp+8h]
  unsigned __int8 **v98; // [rsp+110h] [rbp+10h]
  __int128 v99; // [rsp+118h] [rbp+18h]
  struct _CRYPT_ALGORITHM_IDENTIFIER v100; // [rsp+130h] [rbp+30h] BYREF
  __int128 v101; // [rsp+148h] [rbp+48h] BYREF
  __int128 v102; // [rsp+158h] [rbp+58h]
  __int128 v103; // [rsp+168h] [rbp+68h]
  _WORD v104[2]; // [rsp+180h] [rbp+80h] BYREF
  int v105; // [rsp+184h] [rbp+84h]
  int v106; // [rsp+188h] [rbp+88h]
  struct PKERB_AUTHORIZATION_DATA *v107; // [rsp+190h] [rbp+90h]
  __int16 v108; // [rsp+198h] [rbp+98h] BYREF
  int v109; // [rsp+1A0h] [rbp+A0h]
  int *v110; // [rsp+1A8h] [rbp+A8h]
  int v111; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v112; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _KERB_INTERNAL_NAME *v113; // [rsp+1C0h] [rbp+C0h] BYREF
  int v114; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v115; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v116; // [rsp+1E6h] [rbp+E6h]
  int v117; // [rsp+1EEh] [rbp+EEh]
  __int16 v118; // [rsp+1F2h] [rbp+F2h]
  __int64 v119; // [rsp+1F4h] [rbp+F4h]
  int v120; // [rsp+1FCh] [rbp+FCh]
  __int16 v121; // [rsp+200h] [rbp+100h]
  int v122; // [rsp+204h] [rbp+104h]
  struct KERB_KDC_REQUEST_BODY_encryption_type *v123; // [rsp+208h] [rbp+108h]
  struct PKERB_HOST_ADDRESSES *v124; // [rsp+210h] [rbp+110h]
  __int16 v125; // [rsp+240h] [rbp+140h] BYREF
  __int16 v126; // [rsp+248h] [rbp+148h]
  int v127; // [rsp+24Ch] [rbp+14Ch]
  char v128[16]; // [rsp+250h] [rbp+150h] BYREF
  int v129; // [rsp+260h] [rbp+160h]
  int v130; // [rsp+268h] [rbp+168h]
  void *v131; // [rsp+270h] [rbp+170h]
  __int16 v132; // [rsp+278h] [rbp+178h]
  __int64 v133; // [rsp+280h] [rbp+180h]
  DWORD cbData; // [rsp+288h] [rbp+188h]
  BYTE *pbData; // [rsp+290h] [rbp+190h]
  DWORD v136; // [rsp+298h] [rbp+198h]
  __int64 v137; // [rsp+2A0h] [rbp+1A0h]
  int v138; // [rsp+2B0h] [rbp+1B0h]
  __int64 v139; // [rsp+2B8h] [rbp+1B8h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority[2]; // [rsp+2C0h] [rbp+1C0h] BYREF
  struct _TIME_FIELDS TimeFields; // [rsp+2D0h] [rbp+1D0h] BYREF
  _DWORD v142[20]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v98 = a3;
  *(_QWORD *)pIdentifierAuthority[0].Value = a1;
  v97 = a4;
  v81 = 20;
  memset_0(v104, 0, 0xC0u);
  *(_QWORD *)&IsMember.Length = 2097182;
  IsMember.Buffer = (PWSTR)L"WELLKNOWN:PKU2U";
  v85 = 0;
  Src = 0;
  v101 = 0;
  v6 = 0;
  v84 = 0;
  v102 = 0;
  v103 = 0;
  memset_0(&v125, 0, 0x80u);
  v83 = 0;
  v7 = 0;
  v100.pszObjId = "1.3.14.3.2.26";
  v91 = 0;
  v88 = 0;
  v8 = 0;
  v90 = 0;
  v9 = 0;
  v80 = 0;
  v82 = 0;
  SystemTimeAsFileTime = 0;
  v100.Parameters = 0;
  v89 = 0;
  *(_OWORD *)pcbEncoded = 0;
  ThreadInformation = 0;
  v99 = 0;
  v78 = 0;
  v77 = 0;
  Time.QuadPart = 0;
  if ( Pku2uGlobalDHInitialized || (inited = Pku2uInitDH(), inited >= 0) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( a2 )
    {
      v11 = *((_DWORD *)a2 + 12);
      *(_QWORD *)&TimeFields.Year = 0;
      KerbConvertGeneralizedTimeToLargeInt((PLARGE_INTEGER)&TimeFields, (struct KERB_ERROR *)((char *)a2 + 32), v11);
      v12 = *(struct _FILETIME *)&TimeFields.Year;
      *((_QWORD *)a1 + 20) = *(_QWORD *)&TimeFields.Year - *(_QWORD *)&SystemTimeAsFileTime;
      SystemTimeAsFileTime = v12;
    }
    v13 = *((_QWORD *)a1 + 2);
    if ( *(_DWORD *)(v13 + 32) )
    {
      v13 = *((_QWORD *)a1 + 4);
      if ( !v13 )
      {
        inited = -2146893042;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
LABEL_61:
        v9 = v80;
        goto LABEL_62;
      }
    }
    CriticalSection = (PRTL_CRITICAL_SECTION)(v13 + 40);
    inited = Pku2uProcessTargetNames((struct _UNICODE_STRING *)(v13 + 88), &v85);
    if ( inited < 0 )
      goto LABEL_60;
    v14 = v85;
    v15 = &v112;
    *(_OWORD *)v94 = 0;
    v16 = 0;
    v17 = 0;
    v18 = -1;
    v111 = *(__int16 *)v85;
    v112 = 0;
    while ( v17 < *((unsigned __int16 *)v14 + 1) )
    {
      *(_QWORD *)&TimeFields.Year = 0;
      v19 = KerbAllocUtf8StrFromUnicodeString((struct _UNICODE_STRING *)((char *)v14 + 16 * v17 + 8));
      *(_QWORD *)&TimeFields.Minute = v19;
      v20 = v19;
      if ( !v19 )
        goto LABEL_23;
      *(_QWORD *)&TimeFields.Minute = v19;
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
      if ( (unsigned int)v21 > 0xFFFD )
      {
        Pku2uFree(v20);
LABEL_23:
        KerbFreePrincipalName((struct KERB_PRINCIPAL_NAME *)&v111);
        if ( v16 )
          Pku2uFree(v16);
        goto LABEL_25;
      }
      TimeFields.Year = v21;
      TimeFields.Month = v21 + 1;
      *(struct _TIME_FIELDS *)v94 = TimeFields;
      if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      {
        v22 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(16);
        if ( !v22 )
          goto LABEL_19;
      }
      else
      {
        v22 = (__int64 *)(**((__int64 (__fastcall ***)(__int64))Pku2uGlobalBaseSSP + 31))(16);
        if ( !v22 )
        {
LABEL_19:
          v16 = v94[1];
          goto LABEL_23;
        }
      }
      v14 = v85;
      *v22 = 0;
      v16 = 0;
      v22[1] = (__int64)v20;
      ++v17;
      *v15 = (__int64)v22;
      v15 = v22;
    }
    v23 = (__int16 *)*((_QWORD *)a1 + 10);
    v24 = &v115;
    v108 |= 0x80u;
    v25 = 0;
    *(_OWORD *)v94 = 0;
    v26 = 0;
    v114 = *v23;
    v115 = 0;
    while ( v25 < (unsigned __int16)v23[1] )
    {
      *(_QWORD *)&TimeFields.Year = 0;
      v27 = KerbAllocUtf8StrFromUnicodeString((struct _UNICODE_STRING *)&v23[8 * v25 + 4]);
      *(_QWORD *)&TimeFields.Minute = v27;
      v28 = v27;
      if ( !v27 )
        goto LABEL_38;
      *(_QWORD *)&TimeFields.Minute = v27;
      v29 = -1;
      do
        ++v29;
      while ( v28[v29] );
      if ( (unsigned int)v29 > 0xFFFD )
      {
        Pku2uFree(v28);
LABEL_38:
        KerbFreePrincipalName((struct KERB_PRINCIPAL_NAME *)&v114);
        if ( v26 )
        {
          Pku2uFree(v26);
          inited = -1073741670;
          goto LABEL_60;
        }
LABEL_25:
        inited = -1073741670;
        goto LABEL_60;
      }
      TimeFields.Year = v29;
      TimeFields.Month = v29 + 1;
      *(struct _TIME_FIELDS *)v94 = TimeFields;
      if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      {
        v30 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(16);
        if ( !v30 )
          goto LABEL_34;
      }
      else
      {
        v30 = (__int64 *)(**((__int64 (__fastcall ***)(__int64))Pku2uGlobalBaseSSP + 31))(16);
        if ( !v30 )
        {
LABEL_34:
          v26 = v94[1];
          goto LABEL_38;
        }
      }
      v30[1] = (__int64)v28;
      *v30 = 0;
      v26 = 0;
      *v24 = (__int64)v30;
      ++v25;
      v24 = v30;
    }
    v108 |= 0x40u;
    v77 = 268468544;
    v110 = &v77;
    v31 = Pku2uGlobalInfinity;
    v109 = 32;
    Time = Pku2uGlobalInfinity;
    TimeFields = 0;
    if ( Pku2uGlobalInfinity.QuadPart )
    {
      RtlTimeToTimeFields(&Time, &TimeFields);
      LOWORD(v116) = 9999;
      if ( TimeFields.Year <= 9999 )
        LOWORD(v116) = TimeFields.Year;
      BYTE2(v116) = TimeFields.Month;
      BYTE3(v116) = TimeFields.Day;
      BYTE4(v116) = TimeFields.Hour;
      BYTE5(v116) = TimeFields.Minute;
      BYTE6(v116) = TimeFields.Second;
      v31 = Time;
      LOWORD(v117) = 0;
      v118 = 0;
    }
    else
    {
      v116 = 16844722;
      v117 = 0;
      v118 = 0;
    }
    BYTE2(v117) = 1;
    TimeFields = 0;
    if ( v31.QuadPart )
    {
      RtlTimeToTimeFields(&Time, &TimeFields);
      LOWORD(v119) = 9999;
      if ( TimeFields.Year <= 9999 )
        LOWORD(v119) = TimeFields.Year;
      BYTE2(v119) = TimeFields.Month;
      BYTE3(v119) = TimeFields.Day;
      BYTE4(v119) = TimeFields.Hour;
      BYTE5(v119) = TimeFields.Minute;
      BYTE6(v119) = TimeFields.Second;
      LOWORD(v120) = 0;
      v121 = 0;
    }
    else
    {
      v119 = 16844722;
      v120 = 0;
      v121 = 0;
    }
    v108 |= 0x10u;
    BYTE2(v120) = 1;
    v32 = Pku2uBuildHostAddresses(&v78);
    v33 = v78;
    inited = v32;
    if ( v32 < 0 )
      goto LABEL_58;
    if ( v78 )
    {
      v108 |= 8u;
      v124 = v78;
    }
    v105 = 5;
    v106 = 10;
    v113 = 0;
    v34 = KerbAllocUtf8StrFromUnicodeString(&IsMember);
    if ( !v34 )
    {
LABEL_57:
      inited = -1073741670;
      goto LABEL_58;
    }
    do
      ++v18;
    while ( v34[v18] );
    if ( (unsigned int)v18 > 0xFFFD )
    {
      Pku2uFree(v34);
      goto LABEL_57;
    }
    v113 = (struct _KERB_INTERNAL_NAME *)v34;
    inited = CDBuildIntegrityVect(&v81, v142);
    if ( inited < 0 )
    {
LABEL_58:
      if ( v33 )
        Pku2uFreeHostAddresses(v33);
LABEL_60:
      KerbFreeCryptList(v123);
      KerbFreePrincipalName((struct KERB_PRINCIPAL_NAME *)&v111);
      KerbFreePrincipalName((struct KERB_PRINCIPAL_NAME *)&v114);
      KerbFreeKdcName(&v113);
      v6 = v85;
      v7 = v89;
      v8 = v90;
      goto LABEL_61;
    }
    v36 = v81;
    if ( !v81 )
    {
      v123 = 0;
LABEL_98:
      *(_DWORD *)&IsMember.Length = 0;
      KerbConvertLargeIntToGeneralizedTime(
        (struct tagASN1generalizedtime_t *)v128,
        (int *)&IsMember,
        (union _LARGE_INTEGER *)&SystemTimeAsFileTime);
      v125 |= 0x80u;
      v43 = *(_QWORD *)pIdentifierAuthority[0].Value;
      v127 = *(_DWORD *)&IsMember.Length;
      v44 = *(_QWORD *)pIdentifierAuthority[0].Value + 128LL;
      v122 = *(_DWORD *)(*(_QWORD *)pIdentifierAuthority[0].Value + 168LL);
      v129 = v122;
      v45 = *((_QWORD *)Pku2uGlobalEmpheralDHAlg + 1);
      v132 |= 0x80u;
      v133 = v45;
      if ( !(unsigned __int8)CDGenerateRandomBits(*(_QWORD *)pIdentifierAuthority[0].Value + 128LL, 32) )
      {
        inited = -1073741670;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            55,
            &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids,
            3221225626LL);
        goto LABEL_58;
      }
      v125 |= 0x20u;
      v138 = 32;
      v139 = v44;
      RtlEnterCriticalSection(&Pku2uGlobalDHParametersLock);
      v47 = *(struct _CERT_X942_DH_PARAMETERS **)(v43 + 120);
      cbData = Pku2uGlobalDHAlgorithm.Parameters.cbData;
      pbData = Pku2uGlobalDHAlgorithm.Parameters.pbData;
      if ( v47 )
      {
        CryptDestroyKey((HCRYPTKEY)v47);
        *(_QWORD *)(v43 + 120) = 0;
      }
      DHKey = Pku2uGenerateDHKey(v47, v46, (unsigned __int64 *)(v43 + 120));
      if ( DHKey )
      {
        RtlLeaveCriticalSection(&Pku2uGlobalDHParametersLock);
        inited = KerbMapKerbError(DHKey);
        goto LABEL_58;
      }
      if ( !(unsigned int)Pku2uGetDHPublicKey(*(_QWORD *)(v43 + 120), pcbEncoded) )
      {
        RtlLeaveCriticalSection(&Pku2uGlobalDHParametersLock);
        goto LABEL_57;
      }
      *(_QWORD *)pIdentifierAuthority[0].Value = 0;
      *(_QWORD *)&IsMember.Length = 0;
      v49 = 0;
      *(_QWORD *)&TimeFields.Minute = 0;
      *(_QWORD *)&TimeFields.Year = 0;
      v136 = 8 * pcbEncoded[0];
      v50 = 0;
      v137 = *(_QWORD *)&pcbEncoded[2];
      v89 = 0;
      v99 = 0;
      inited = CDLocateCheckSum(4294967165LL, pIdentifierAuthority);
      if ( inited >= 0 )
      {
        v89 = basessp::BaseSSP::WSTAllocate(
                Pku2uGlobalBaseSSP,
                *(unsigned int *)(*(_QWORD *)pIdentifierAuthority[0].Value + 4LL));
        v50 = v89;
        if ( v89 )
        {
          v51 = *(_DWORD *)(*(_QWORD *)pIdentifierAuthority[0].Value + 4LL);
          v52 = *(__int64 (__fastcall **)(void *, _QWORD, _QWORD, __int64, struct _UNICODE_STRING *))(*(_QWORD *)pIdentifierAuthority[0].Value + 56LL);
          if ( v52 )
          {
            v53 = v52(
                    ThreadInformation,
                    (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)),
                    0,
                    6,
                    &IsMember);
          }
          else
          {
            v54 = *(__int64 (__fastcall **)(void *, _QWORD, __int64, struct _UNICODE_STRING *))(*(_QWORD *)pIdentifierAuthority[0].Value
                                                                                              + 48LL);
            if ( !v54 )
            {
              inited = -1073741069;
              goto LABEL_112;
            }
            v53 = v54(ThreadInformation, (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)), 6, &IsMember);
          }
          inited = v53;
          if ( v53 >= 0 )
          {
            v55 = KerbPackData(&v108, 0x2Au, (unsigned int *)&TimeFields, (unsigned __int8 **)&TimeFields.Minute);
            v49 = *(void **)&TimeFields.Minute;
            if ( v55 )
            {
              inited = -1073741670;
            }
            else
            {
              inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)pIdentifierAuthority[0].Value
                                                                         + 24LL))(
                         *(_QWORD *)&IsMember.Length,
                         *(unsigned int *)&TimeFields.Year,
                         *(_QWORD *)&TimeFields.Minute);
              if ( inited >= 0 )
                inited = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)pIdentifierAuthority[0].Value + 32LL))(
                           *(_QWORD *)&IsMember.Length,
                           v50);
            }
          }
LABEL_112:
          if ( *(_QWORD *)&IsMember.Length && *(_QWORD *)pIdentifierAuthority[0].Value )
            (*(void (__fastcall **)(struct _UNICODE_STRING *))(*(_QWORD *)pIdentifierAuthority[0].Value + 40LL))(&IsMember);
          if ( v49 )
            Pku2uFree(v49);
          if ( inited < 0 )
          {
            if ( v50 )
            {
              Pku2uFree(v50);
              v89 = 0;
            }
            RtlLeaveCriticalSection(&Pku2uGlobalDHParametersLock);
            goto LABEL_58;
          }
          v130 = v51;
          v126 |= 0x80u;
          v56 = 0;
          v57 = 0;
          v131 = v50;
          v78 = 0;
          if ( fKRB5ModuleStarted )
          {
            Module = PKU2UMSG_Module;
          }
          else
          {
            fKRB5ModuleStarted = 1;
            Module = ASN1_CreateModule(
                       0x10000,
                       1024,
                       4096,
                       49,
                       off_180047350,
                       off_1800471C0,
                       off_180047030,
                       qword_180049F80,
                       846556016);
            PKU2UMSG_Module = Module;
          }
          v59 = ASN1_CreateEncoder(Module, &v78, 0, 0, 0);
          if ( v59 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v59);
              v60 = 60;
              goto LABEL_151;
            }
            goto LABEL_142;
          }
          v61 = ASN1_Encode(v78, &v125, 41, 16, 0, 0);
          if ( v61 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                78,
                &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
                (unsigned int)v61);
LABEL_142:
            v60 = 60;
            goto LABEL_151;
          }
          v62 = *((unsigned int *)v78 + 7);
          if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
          {
            v63 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))((unsigned int)v62);
          }
          else
          {
            v65 = (unsigned __int8 *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))((unsigned int)v62);
            v63 = v65;
            if ( v65 )
            {
              memset_0(v65, 0, v62);
              v90 = v63;
              goto LABEL_149;
            }
          }
          v90 = v63;
          if ( !v63 )
          {
            v64 = v78;
            v60 = 60;
LABEL_150:
            ASN1_FreeEncoded(v64, *((_QWORD *)v64 + 2));
LABEL_151:
            if ( v78 )
              ASN1_CloseEncoder();
            RtlLeaveCriticalSection(&Pku2uGlobalDHParametersLock);
            if ( v60 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
              inited = KerbMapKerbError(v60);
              goto LABEL_58;
            }
            v66 = *(_QWORD *)(v43 + 16);
            inited = 0;
            *(_QWORD *)&TimeFields.Year = 0;
            *(_DWORD *)pIdentifierAuthority[0].Value = 0;
            *(_WORD *)&pIdentifierAuthority[0].Value[4] = 1280;
            v67 = *(_QWORD *)(v66 + 24);
            v68 = 0;
            *(_DWORD *)&IsMember.Length = 0;
            v69 = *(void **)(v67 + 32);
            if ( AllocateAndInitializeSid(pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, (PSID *)&TimeFields) )
            {
              if ( !CheckTokenMembership(v69, *(PSID *)&TimeFields.Year, (PBOOL)&IsMember) )
              {
                LastError = GetLastError();
                inited = LastError;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    14,
                    WPP_145765ada38d35d83bd68130d412160b_Traceguids,
                    LastError);
              }
            }
            else
            {
              inited = GetLastError();
            }
            if ( *(_QWORD *)&TimeFields.Year )
              FreeSid(*(PSID *)&TimeFields.Year);
            v71 = inited < 0;
            if ( inited > 0 )
            {
              inited = (unsigned __int16)inited | 0xC0070000;
              v71 = inited < 0;
            }
            if ( !v71 )
            {
              if ( *(_DWORD *)&IsMember.Length )
                goto LABEL_176;
              ThreadInformation = v69;
              *(_QWORD *)pIdentifierAuthority[0].Value = 0;
              inited = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, (PHANDLE)pIdentifierAuthority);
              if ( (int)(inited + 0x80000000) < 0 || inited == -1073741700 )
              {
                v56 = 1;
                v72 = NtSetInformationThread(
                        (HANDLE)0xFFFFFFFFFFFFFFFELL,
                        ThreadImpersonationToken,
                        &ThreadInformation,
                        8u);
                v68 = *(void **)pIdentifierAuthority[0].Value;
                inited = v72;
                *(_QWORD *)pIdentifierAuthority[0].Value = 0;
              }
              else if ( *(_QWORD *)pIdentifierAuthority[0].Value )
              {
                CloseHandle(*(HANDLE *)pIdentifierAuthority[0].Value);
              }
            }
            if ( inited < 0 )
            {
LABEL_189:
              if ( v56 )
                Pku2uRevertImpersonation(v68);
              if ( v68 )
                CloseHandle(v68);
              goto LABEL_58;
            }
LABEL_176:
            v73 = CriticalSection;
            RtlEnterCriticalSection(CriticalSection);
            inited = ScHelperPeer2PeerSignPkcsMessage(
                       (PCCERT_CONTEXT)v73[3].DebugInfo,
                       *(const struct _CERT_CHAIN_CONTEXT **)&v73[3].LockCount,
                       &v100,
                       "1.3.6.1.5.2.3.1",
                       v90,
                       v57,
                       &v80,
                       &v82);
            RtlLeaveCriticalSection(v73);
            if ( v56 )
            {
              Pku2uRevertImpersonation(v68);
              v56 = 0;
            }
            if ( inited >= 0 )
            {
              *(_QWORD *)&v102 = v80;
              DWORD2(v101) = v82;
              if ( (unsigned int)KerbPackData(&v101, 0x12u, &v83, &v88) )
              {
                inited = -1073741670;
                v91 = v88;
              }
              else
              {
                v75 = (struct PKERB_AUTHORIZATION_DATA *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, 0x20u);
                v107 = v75;
                if ( v75 )
                {
                  v76 = v88;
                  *((_DWORD *)v75 + 2) = 16;
                  *((_QWORD *)v107 + 3) = v76;
                  *((_DWORD *)v107 + 4) = v83;
                  v104[0] |= 0x80u;
                  v91 = 0;
                  if ( (unsigned int)KerbPackData(v104, 0x2Fu, &v84, &Src) )
                    inited = -1073741670;
                  else
                    inited = Pku2uPackContextLevelToken(Src, v84, 1280, v98, (unsigned __int8 *)v97);
                }
                else
                {
                  inited = -1073741670;
                  v91 = v88;
                }
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v74 = GetLastError();
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                57,
                &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids,
                (unsigned int)inited,
                v74);
            }
            goto LABEL_189;
          }
LABEL_149:
          v60 = 0;
          memcpy_0(v63, *((const void **)v78 + 2), *((unsigned int *)v78 + 7));
          v64 = v78;
          v57 = *((_DWORD *)v78 + 7);
          goto LABEL_150;
        }
        inited = -1073741801;
      }
      v51 = DWORD2(v99);
      goto LABEL_112;
    }
    v37 = 0;
    v38 = 0;
    for ( i = 0; ; ++i )
    {
      while ( 1 )
      {
        if ( i >= v36 )
        {
          v123 = v37;
          goto LABEL_98;
        }
        v40 = v142[i];
        if ( v40 != -128 && v40 != -133 )
          break;
LABEL_96:
        ++i;
      }
      if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      {
        v41 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(16);
        if ( !v41 )
          goto LABEL_88;
      }
      else
      {
        v41 = (**((__int64 (__fastcall ***)(__int64))Pku2uGlobalBaseSSP + 31))(16);
        if ( !v41 )
        {
LABEL_88:
          if ( v37 )
          {
            do
            {
              v42 = *(struct KERB_KDC_REQUEST_BODY_encryption_type **)v37;
              Pku2uFree(v37);
              v37 = v42;
            }
            while ( v42 );
          }
          goto LABEL_57;
        }
        *(_OWORD *)v41 = 0;
      }
      *(_DWORD *)(v41 + 8) = v142[i];
      *(_QWORD *)v41 = 0;
      if ( !v38 )
      {
        v37 = (struct KERB_KDC_REQUEST_BODY_encryption_type *)v41;
        v38 = (_QWORD *)v41;
        goto LABEL_96;
      }
      *v38 = v41;
      v38 = (_QWORD *)v41;
    }
  }
LABEL_62:
  if ( v107 )
    KerbFreeAuthData(v107);
  if ( v91 )
    Pku2uFree(v91);
  if ( v8 )
    Pku2uFree(v8);
  if ( v9 )
    LocalFree(v9);
  if ( *(_QWORD *)&pcbEncoded[2] )
    Pku2uFree(*(void **)&pcbEncoded[2]);
  if ( v7 )
    Pku2uFree(v7);
  if ( v6 )
    KerbFreeKdcName(&v85);
  if ( Src )
    Pku2uFree(Src);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000fc70  push    rbp
0x18000fc72  push    rbx
0x18000fc73  push    rsi
0x18000fc74  push    rdi
0x18000fc75  push    r12
0x18000fc77  push    r13
0x18000fc79  push    r14
0x18000fc7b  push    r15
0x18000fc7d  lea     rbp, [rsp-258h]
0x18000fc85  sub     rsp, 358h
0x18000fc8c  movaps  [rsp+390h+var_50], xmm6
0x18000fc94  mov     rax, cs:__security_cookie
0x18000fc9b  xor     rax, rsp
0x18000fc9e  mov     [rbp+290h+var_60], rax
0x18000fca5  mov     [rbp+290h+var_280], r8
0x18000fca9  mov     rdi, rdx
0x18000fcac  mov     r13, rcx
0x18000fcaf  mov     qword ptr [rbp+290h+pIdentifierAuthority.Value], rcx
0x18000fcb6  xor     edx, edx; Val
0x18000fcb8  mov     [rbp+290h+var_288], r9
0x18000fcbc  mov     r8d, 0C0h; Size
0x18000fcc2  mov     [rbp+290h+var_308], 14h
0x18000fcc9  lea     rcx, [rbp+290h+var_210]; void *
0x18000fcd0  call    memset_0
0x18000fcd5  xorps   xmm0, xmm0
0x18000fcd8  mov     qword ptr [rsp+390h+IsMember], 20001Eh
0x18000fce1  xor     ebx, ebx
0x18000fce3  lea     rax, WideCharStr; "WELLKNOWN:PKU2U"
0x18000fcea  xor     edx, edx; Val
0x18000fcec  mov     [rsp+390h+var_318], rax
0x18000fcf1  mov     r8d, 80h; Size
0x18000fcf7  mov     [rbp+290h+var_2F8], rbx
0x18000fcfb  lea     rcx, [rbp+290h+var_150]; void *
0x18000fd02  mov     [rbp+290h+Src], rbx
0x18000fd06  movups  [rbp+290h+var_248], xmm0
0x18000fd0a  mov     esi, ebx
0x18000fd0c  mov     [rbp+290h+var_2FC], ebx
0x18000fd0f  movups  [rbp+290h+var_238], xmm0
0x18000fd13  movups  [rbp+290h+var_228], xmm0
0x18000fd17  call    memset_0
0x18000fd1c  lea     rax, a13143226; "1.3.14.3.2.26"
0x18000fd23  mov     [rbp+290h+var_300], ebx
0x18000fd26  xor     r14d, r14d
0x18000fd29  mov     [rbp+290h+var_260.pszObjId], rax
0x18000fd2d  xor     eax, eax
0x18000fd2f  mov     [rbp+290h+var_2C8], rbx
0x18000fd33  cmp     cs:?Pku2uGlobalDHInitialized@@3HA, eax; int Pku2uGlobalDHInitialized
0x18000fd39  xorps   xmm0, xmm0
0x18000fd3c  xorps   xmm1, xmm1
0x18000fd3f  mov     [rbp+290h+var_2E0], rbx
0x18000fd43  mov     r15d, ebx
0x18000fd46  mov     [rbp+290h+var_2D0], rbx
0x18000fd4a  mov     r12d, ebx
0x18000fd4d  mov     [rbp+290h+var_310], rbx
0x18000fd51  mov     [rbp+290h+var_304], ebx
0x18000fd54  xorps   xmm6, xmm6
0x18000fd57  mov     qword ptr [rbp+290h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18000fd5b  movups  xmmword ptr [rbp+290h+var_260.Parameters.cbData], xmm0
0x18000fd5f  mov     [rbp+290h+var_2D8], r14
0x18000fd63  movups  xmmword ptr [rbp+290h+pcbEncoded], xmm1
0x18000fd67  mov     [rbp+290h+ThreadInformation], rax
0x18000fd6b  movups  [rbp+290h+var_278], xmm0
0x18000fd6f  mov     [rsp+390h+var_328], rbx
0x18000fd74  mov     [rsp+390h+var_330], ebx
0x18000fd78  mov     qword ptr [rbp+290h+Time], rbx
0x18000fd7c  jnz     short loc_18000FD8F
0x18000fd7e  call    ?Pku2uInitDH@@YAJXZ; Pku2uInitDH(void)
0x18000fd83  mov     ebx, eax
0x18000fd85  test    eax, eax
0x18000fd87  js      loc_180010341
0x18000fd8d  xor     ebx, ebx
0x18000fd8f  lea     rcx, [rbp+290h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000fd93  call    cs:__imp_GetSystemTimeAsFileTime
0x18000fd99  test    rdi, rdi
0x18000fd9c  jz      short loc_18000FDD5
0x18000fd9e  mov     r8d, [rdi+30h]; int
0x18000fda2  lea     rdx, [rdi+20h]; struct tagASN1generalizedtime_t *
0x18000fda6  lea     rcx, [rbp+290h+TimeFields]; Time
0x18000fdad  mov     qword ptr [rbp+290h+TimeFields.Year], rbx
0x18000fdb4  call    ?KerbConvertGeneralizedTimeToLargeInt@@YAXPEAT_LARGE_INTEGER@@PEAUtagASN1generalizedtime_t@@H@Z; KerbConvertGeneralizedTimeToLargeInt(_LARGE_INTEGER *,tagASN1generalizedtime_t *,int)
0x18000fdb9  mov     rax, qword ptr [rbp+290h+SystemTimeAsFileTime.dwLowDateTime]
0x18000fdbd  mov     rcx, qword ptr [rbp+290h+TimeFields.Year]
0x18000fdc4  sub     rcx, rax
0x18000fdc7  add     rax, rcx
0x18000fdca  mov     [r13+0A0h], rcx
0x18000fdd1  mov     qword ptr [rbp+290h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000fdd5  mov     rax, [r13+10h]
0x18000fdd9  cmp     [rax+20h], esi
0x18000fddc  jz      short loc_18000FE27
0x18000fdde  mov     rax, [r13+20h]
0x18000fde2  test    rax, rax
0x18000fde5  jnz     short loc_18000FE27
0x18000fde7  mov     ebx, 8009030Eh
0x18000fdec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdf3  lea     r12, WPP_GLOBAL_Control
0x18000fdfa  cmp     rcx, r12
0x18000fdfd  jz      loc_18001033D
0x18000fe03  test    byte ptr [rcx+1Ch], 1
0x18000fe07  jz      loc_18001033D
0x18000fe0d  mov     rcx, [rcx+10h]
0x18000fe11  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x18000fe18  mov     edx, 36h ; '6'
0x18000fe1d  call    WPP_SF_
0x18000fe22  jmp     loc_18001033D
0x18000fe27  add     rax, 28h ; '('
0x18000fe2b  lea     rdx, [rbp+290h+var_2F8]; struct _KERB_INTERNAL_NAME **
0x18000fe2f  mov     [rbp+290h+CriticalSection], rax
0x18000fe33  lea     rcx, [rax+30h]; struct _UNICODE_STRING *
0x18000fe37  call    ?Pku2uProcessTargetNames@@YAJPEAU_UNICODE_STRING@@PEAPEAU_KERB_INTERNAL_NAME@@@Z; Pku2uProcessTargetNames(_UNICODE_STRING *,_KERB_INTERNAL_NAME * *)
0x18000fe3c  mov     ebx, eax
0x18000fe3e  test    eax, eax
0x18000fe40  js      loc_180010301
0x18000fe46  mov     rcx, [rbp+290h+var_2F8]
0x18000fe4a  lea     r14, [rbp+290h+var_1D8]
0x18000fe51  xor     edx, edx
0x18000fe53  xorps   xmm0, xmm0
0x18000fe56  movups  xmmword ptr [rbp+290h+var_2B0], xmm0
0x18000fe5a  mov     r15, [rbp+290h+var_2B0+8]
0x18000fe5e  mov     ebx, edx
0x18000fe60  movsx   eax, word ptr [rcx]
0x18000fe63  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000fe6a  mov     [rbp+290h+var_1E0], eax
0x18000fe70  mov     [rbp+290h+var_1D8], rdx
0x18000fe77  movzx   eax, word ptr [rcx+2]
0x18000fe7b  cmp     ebx, eax
0x18000fe7d  jnb     loc_18000FF85
0x18000fe83  mov     eax, ebx
0x18000fe85  shl     rax, 4
0x18000fe89  add     rax, 8
0x18000fe8d  mov     qword ptr [rbp+290h+TimeFields.Year], rdx
0x18000fe94  add     rcx, rax; struct _UNICODE_STRING *
0x18000fe97  call    ?KerbAllocUtf8StrFromUnicodeString@@YAPEADPEAU_UNICODE_STRING@@@Z; KerbAllocUtf8StrFromUnicodeString(_UNICODE_STRING *)
0x18000fe9c  mov     qword ptr [rbp+290h+TimeFields.Minute], rax
0x18000fea3  mov     rsi, rax
0x18000fea6  test    rax, rax
0x18000fea9  jz      loc_18000FF62
0x18000feaf  mov     qword ptr [rbp+290h+TimeFields.Minute], rax
0x18000feb6  mov     rax, rdi
0x18000feb9  nop     dword ptr [rax+00000000h]
0x18000fec0  inc     rax
0x18000fec3  cmp     [rsi+rax], r12b
0x18000fec7  jnz     short loc_18000FEC0
0x18000fec9  cmp     eax, 0FFFDh
0x18000fece  ja      loc_18000FF5A
0x18000fed4  mov     [rbp+290h+TimeFields.Year], ax
0x18000fedb  inc     ax
0x18000fede  mov     [rbp+290h+TimeFields.Month], ax
0x18000fee5  movaps  xmm0, xmmword ptr [rbp+290h+TimeFields.Year]
0x18000feec  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x18000fef3  movdqa  xmmword ptr [rbp+290h+var_2B0], xmm0
0x18000fef8  cmp     dword ptr [rax+0D0h], 1
0x18000feff  jnz     short loc_18000FF24
0x18000ff01  mov     rax, [rax+0F0h]
0x18000ff08  mov     ecx, 10h
0x18000ff0d  mov     rax, [rax+180h]
0x18000ff14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff19  test    rax, rax
0x18000ff1c  jnz     short loc_18000FF3D
0x18000ff1e  mov     r15, [rbp+290h+var_2B0+8]
0x18000ff22  jmp     short loc_18000FF62
0x18000ff24  mov     rax, [rax+0F8h]
0x18000ff2b  mov     ecx, 10h
0x18000ff30  mov     rax, [rax]
0x18000ff33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff38  test    rax, rax
0x18000ff3b  jz      short loc_18000FF1E
0x18000ff3d  mov     rcx, [rbp+290h+var_2F8]
0x18000ff41  xor     edx, edx
0x18000ff43  mov     [rax], rdx
0x18000ff46  mov     r15d, edx
0x18000ff49  mov     [rax+8], rsi
0x18000ff4d  inc     ebx
0x18000ff4f  mov     [r14], rax
0x18000ff52  mov     r14, rax
0x18000ff55  jmp     loc_18000FE77
0x18000ff5a  mov     rcx, rsi; void *
0x18000ff5d  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18000ff62  lea     rcx, [rbp+290h+var_1E0]; struct KERB_PRINCIPAL_NAME *
0x18000ff69  call    ?KerbFreePrincipalName@@YAXPEAUKERB_PRINCIPAL_NAME@@@Z; KerbFreePrincipalName(KERB_PRINCIPAL_NAME *)
0x18000ff6e  test    r15, r15
0x18000ff71  jz      short loc_18000FF7B
0x18000ff73  mov     rcx, r15; void *
0x18000ff76  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18000ff7b  mov     ebx, 0C000009Ah
0x18000ff80  jmp     loc_180010301
0x18000ff85  mov     rsi, [r13+50h]
0x18000ff89  lea     r15, [rbp+290h+var_1C0]
0x18000ff90  mov     eax, 80h
0x18000ff95  xorps   xmm0, xmm0
0x18000ff98  or      [rbp+290h+var_1F8], ax
0x18000ff9f  mov     ebx, edx
0x18000ffa1  movups  xmmword ptr [rbp+290h+var_2B0], xmm0
0x18000ffa5  movsx   eax, word ptr [rsi]
0x18000ffa8  mov     r12, [rbp+290h+var_2B0+8]
0x18000ffac  mov     [rbp+290h+var_1C8], eax
0x18000ffb2  mov     [rbp+290h+var_1C0], rdx
0x18000ffb9  movzx   eax, word ptr [rsi+2]
0x18000ffbd  cmp     ebx, eax
0x18000ffbf  jnb     loc_1800100C6
0x18000ffc5  mov     ecx, ebx
0x18000ffc7  shl     rcx, 4
0x18000ffcb  add     rcx, 8
0x18000ffcf  mov     qword ptr [rbp+290h+TimeFields.Year], rdx
0x18000ffd6  add     rcx, rsi; struct _UNICODE_STRING *
0x18000ffd9  call    ?KerbAllocUtf8StrFromUnicodeString@@YAPEADPEAU_UNICODE_STRING@@@Z; KerbAllocUtf8StrFromUnicodeString(_UNICODE_STRING *)
0x18000ffde  mov     qword ptr [rbp+290h+TimeFields.Minute], rax
0x18000ffe5  mov     r14, rax
0x18000ffe8  test    rax, rax
0x18000ffeb  jz      loc_18001009F
0x18000fff1  mov     qword ptr [rbp+290h+TimeFields.Minute], rax
0x18000fff8  mov     rax, rdi
0x18000fffb  nop     dword ptr [rax+rax+00h]
0x180010000  inc     rax
0x180010003  cmp     byte ptr [r14+rax], 0
0x180010008  jnz     short loc_180010000
0x18001000a  cmp     eax, 0FFFDh
0x18001000f  ja      loc_180010097
0x180010015  mov     [rbp+290h+TimeFields.Year], ax
0x18001001c  inc     ax
0x18001001f  mov     [rbp+290h+TimeFields.Month], ax
0x180010026  movaps  xmm0, xmmword ptr [rbp+290h+TimeFields.Year]
0x18001002d  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180010034  movdqa  xmmword ptr [rbp+290h+var_2B0], xmm0
0x180010039  cmp     dword ptr [rax+0D0h], 1
0x180010040  jnz     short loc_180010065
0x180010042  mov     rax, [rax+0F0h]
0x180010049  mov     ecx, 10h
0x18001004e  mov     rax, [rax+180h]
0x180010055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001005a  test    rax, rax
0x18001005d  jnz     short loc_18001007E
0x18001005f  mov     r12, [rbp+290h+var_2B0+8]
0x180010063  jmp     short loc_18001009F
0x180010065  mov     rax, [rax+0F8h]
0x18001006c  mov     ecx, 10h
0x180010071  mov     rax, [rax]
0x180010074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010079  test    rax, rax
0x18001007c  jz      short loc_18001005F
0x18001007e  xor     edx, edx
0x180010080  mov     [rax+8], r14
0x180010084  mov     [rax], rdx
0x180010087  mov     r12d, edx
0x18001008a  mov     [r15], rax
0x18001008d  inc     ebx
0x18001008f  mov     r15, rax
0x180010092  jmp     loc_18000FFB9
0x180010097  mov     rcx, r14; void *
0x18001009a  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18001009f  lea     rcx, [rbp+290h+var_1C8]; struct KERB_PRINCIPAL_NAME *
0x1800100a6  call    ?KerbFreePrincipalName@@YAXPEAUKERB_PRINCIPAL_NAME@@@Z; KerbFreePrincipalName(KERB_PRINCIPAL_NAME *)
0x1800100ab  test    r12, r12
0x1800100ae  jz      loc_18000FF7B
0x1800100b4  mov     rcx, r12; void *
0x1800100b7  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x1800100bc  mov     ebx, 0C000009Ah
0x1800100c1  jmp     loc_180010301
0x1800100c6  or      [rbp+290h+var_1F8], 40h
0x1800100ce  xorps   xmm0, xmm0
0x1800100d1  mov     [rsp+390h+var_330], 10008140h
0x1800100d9  mov     esi, 270Fh
0x1800100de  mov     eax, [rsp+390h+var_330]
0x1800100e2  mov     [rsp+390h+var_330], eax
0x1800100e6  lea     rax, [rsp+390h+var_330]
0x1800100eb  mov     [rbp+290h+var_1E8], rax
0x1800100f2  mov     rax, cs:?Pku2uGlobalInfinity@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER Pku2uGlobalInfinity
0x1800100f9  mov     [rbp+290h+var_1F0], 20h ; ' '
0x180010103  mov     qword ptr [rbp+290h+Time], rax
0x180010107  movups  xmmword ptr [rbp+290h+TimeFields.Year], xmm0
0x18001010e  test    rax, rax
0x180010111  jnz     short loc_18001013B
0x180010113  xor     ecx, ecx
0x180010115  mov     [rbp+290h+var_1AA], rcx
0x18001011c  xor     r12d, r12d
0x18001011f  mov     dword ptr [rbp+290h+var_1AA], 10107B2h
0x180010129  mov     [rbp+290h+var_1A2], ecx
0x18001012f  mov     [rbp+290h+var_19E], cx
0x180010136  jmp     loc_1800101BE
0x18001013b  lea     rdx, [rbp+290h+TimeFields]; TimeFields
0x180010142  lea     rcx, [rbp+290h+Time]; Time
0x180010146  call    cs:__imp_RtlTimeToTimeFields
0x18001014c  movzx   eax, [rbp+290h+TimeFields.Year]
0x180010153  mov     word ptr [rbp+290h+var_1AA], si
0x18001015a  cmp     ax, si
0x18001015d  jg      short loc_180010166
0x18001015f  mov     word ptr [rbp+290h+var_1AA], ax
0x180010166  movzx   eax, byte ptr [rbp+290h+TimeFields.Month]
0x18001016d  xor     r12d, r12d
0x180010170  mov     byte ptr [rbp+290h+var_1AA+2], al
0x180010176  movzx   eax, byte ptr [rbp+290h+TimeFields.Day]
0x18001017d  mov     byte ptr [rbp+290h+var_1AA+3], al
0x180010183  movzx   eax, byte ptr [rbp+290h+TimeFields.Hour]
0x18001018a  mov     byte ptr [rbp+290h+var_1AA+4], al
0x180010190  movzx   eax, byte ptr [rbp+290h+TimeFields.Minute]
0x180010197  mov     byte ptr [rbp+290h+var_1AA+5], al
0x18001019d  movzx   eax, byte ptr [rbp+290h+TimeFields.Second]
0x1800101a4  mov     byte ptr [rbp+290h+var_1AA+6], al
0x1800101aa  mov     rax, qword ptr [rbp+290h+Time]
0x1800101ae  mov     word ptr [rbp+290h+var_1A2], r12w
0x1800101b6  mov     [rbp+290h+var_19E], r12w
  ... truncated ...
```
