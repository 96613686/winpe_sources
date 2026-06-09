# GenerateCertRequestOld(HKEY__ *,ushort const * *,ulong,ulong,ushort *,ushort *,int,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,ushort * *,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,_ATTESTATION_STATUS *)

- ea: `0x18001b3ac`
- end: `0x18001cc9c`
- name: `?GenerateCertRequestOld@@YAJPEAUHKEY__@@PEAPEBGKKPEAG2HKKKPEBG33PEAPEAEPEAK4545PEAPEAG454545PEAU_ATTESTATION_STATUS@@@Z`
- size: `6384`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, const unsigned __int16 **@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, LPCWCH lpWideCharStr, unsigned __int16 *, int, unsigned int, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int16 **, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, struct _ATTESTATION_STATUS *)`
- caller_count: `1`
- callee_count: `64`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004d410`

## callees

- `0x18000d810`
- `0x18000dd20`
- `0x18000e508`
- `0x180010fcc`
- `0x1800132ec`
- `0x180013b8c`
- `0x1800140d0`
- `0x18001ac7c`
- `0x18001aec8`
- `0x18001af28`
- `0x18001b308`
- `0x18001b3ac`
- `0x18001f23c`
- `0x18001f41c`
- `0x180020cb4`
- `0x18002cda4`
- `0x18002d26c`
- `0x18002d9d0`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x18003aabc`
- `0x18003dba8`
- `0x18004234c`
- `0x1800424fc`
- `0x180042634`
- `0x1800437a4`
- `0x180045d44`
- `0x180045e08`
- `0x180045e9c`
- `0x180045fb0`
- `0x18004c364`
- `0x18004c38c`
- `0x18004ca34`
- `0x180054ebc`
- `0x180054f88`
- `0x180055000`
- `0x180055138`
- `0x180055188`
- `0x180055bb8`
- `0x180055ec8`
- `0x1800560dc`
- `0x1800567d0`
- `0x180056974`
- `0x180056a5c`
- `0x180056d24`
- `0x180057118`
- `0x1800576b0`
- `0x18005773c`
- `0x18005792c`
- `0x180057f28`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001bc68`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001bc68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b7b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b7b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfe9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ba2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c342`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c665`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c7b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ba2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c342`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c665`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c7b9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c34f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c681`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c7d5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c34f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c681`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c7d5`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18001bf9f`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18001bf9f`
- `CRYPT32!CryptFindOIDInfo` at `0x18001b674`
- `CRYPT32!CryptFindOIDInfo` at `0x18001b674`
- `ncrypt!NCryptFreeObject` at `0x18001b7a9`
- `ncrypt!NCryptFreeObject` at `0x18001b7a9`
- `DMCmnUtils!DmDiagnoseEkAikMissingOld` at `0x18001c262`
- `DMCmnUtils!DmDiagnoseEkAikMissingOld` at `0x18001c4b4`
- `DMCmnUtils!DmDiagnoseEkAikMissingOld` at `0x18001c262`
- `DMCmnUtils!DmDiagnoseEkAikMissingOld` at `0x18001c4b4`
- `DMCmnUtils!DmGenerateMaaAttestationClaims` at `0x18001c149`
- `DMCmnUtils!DmGenerateMaaAttestationClaims` at `0x18001c149`
- `DMCmnUtils!DmCheckAikOld` at `0x18001bb10`
- `DMCmnUtils!DmCheckAikOld` at `0x18001bb10`
- `DMCmnUtils!DmCreateTask` at `0x18001c973`
- `DMCmnUtils!DmCreateTask` at `0x18001c973`
- `DMCmnUtils!DmGetTargetAikOld` at `0x18001c06d`
- `DMCmnUtils!DmGetTargetAikOld` at `0x18001c5cc`
- `DMCmnUtils!DmGetTargetAikOld` at `0x18001c06d`
- `DMCmnUtils!DmGetTargetAikOld` at `0x18001c5cc`
- `DMCmnUtils!EncodeBase64W` at `0x18001b982`
- `DMCmnUtils!EncodeBase64W` at `0x18001b9d8`
- `DMCmnUtils!EncodeBase64W` at `0x18001b982`
- `DMCmnUtils!EncodeBase64W` at `0x18001b9d8`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18001be0d`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18001be0d`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18001bea6`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18001c706`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18001bea6`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18001c706`
- `DMCmnUtils!DmRevertToSelf` at `0x18001b949`
- `DMCmnUtils!DmRevertToSelf` at `0x18001b949`
- `DMCmnUtils!DmGetTargetAikWithRetryOld` at `0x18001bd12`
- `DMCmnUtils!DmGetTargetAikWithRetryOld` at `0x18001bd12`
- `dsreg!DsrGetJoinInfo` at `0x18001bec5`
- `dsreg!DsrGetJoinInfo` at `0x18001bec5`
- `dsreg!DsrFreeJoinInfo` at `0x18001c03f`
- `dsreg!DsrFreeJoinInfo` at `0x18001c03f`

## string_xrefs

- `0x18001c95c`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">     <RegistrationInfo>         <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>         <Description>$(@%systemRoot%\system32\deviceenroller.exe,-102)</Description>         <URI>\Microsoft\Windows\EnterpriseMgmt\TestTask</URI>         <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>     </RegistrationInfo>     <Triggers>       <`
- `0x18001b7f7`: `LegacyCreateKeyWithRetry`
- `0x18001be1e`: `DmGetActiveUserSid`
- `0x18001be31`: `DmGetActiveUserSid`
- `0x18001be56`: `DmGetActiveUserSid`
- `0x18001b6bf`: `CRYPT_TEMPLATE_OID_GROUP_ID`
- `0x18001b890`: `LegacyCreatePkcs10RequestFromKey`
- `0x18001bbab`: `CreateKeyWithRetry`
- `0x18001cadf`: `CreateKeyWithRetry`
- `0x18001bac2`: `IsTPMReady`
- `0x18001badb`: `IsTPMReady`
- `0x18001c963`: `Schedule created by enrollment client to reattest client certificate`
- `0x18001cb77`: `CreateCertificateName`
- `0x18001cc0a`: `CreatePkcs10RequestFromKey`
- `0x18001bb9c`: `Failed to create key in TPM`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall GenerateCertRequestOld(
        HKEY a1,
        const unsigned __int16 **a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *lpWideCharStr,
        unsigned __int16 *a6,
        int a7,
        unsigned int a8,
        unsigned int a9,
        DWORD a10,
        wchar_t *a11,
        const unsigned __int16 *a12,
        const unsigned __int16 *a13,
        unsigned __int8 **a14,
        unsigned int *a15,
        unsigned __int8 **a16,
        unsigned int *a17,
        unsigned __int8 **a18,
        unsigned int *a19,
        unsigned __int16 **a20,
        unsigned __int8 **a21,
        unsigned int *a22,
        unsigned __int8 **a23,
        unsigned int *a24,
        unsigned __int8 **a25,
        unsigned int *a26,
        struct _ATTESTATION_STATUS *a27)
{
  const unsigned __int16 **v27; // rdi
  struct _ATTESTATION_STATUS *v29; // r12
  const unsigned __int16 *v30; // rsi
  unsigned int v31; // edi
  CEnrollmentLogger *v32; // rax
  CEnrollmentLogger *v33; // rax
  const unsigned __int16 *v34; // rdx
  int v35; // ebx
  unsigned int v37; // r15d
  void *v38; // rbx
  PCCRYPT_OID_INFO OIDInfo; // rax
  const wchar_t *v40; // r9
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  const unsigned __int16 *v48; // rcx
  NCRYPT_HANDLE v49; // rdi
  unsigned int v50; // r8d
  int v51; // eax
  HLOCAL v52; // rcx
  unsigned __int16 *v53; // rax
  const unsigned __int16 *v54; // r13
  bool v55; // bl
  _QWORD *v56; // rax
  unsigned __int64 v57; // r13
  bool v58; // bl
  int v59; // eax
  CEnrollmentLogger *v60; // rax
  CEnrollmentLogger *v61; // rax
  const unsigned __int16 *v62; // rdx
  int v63; // r15d
  int v64; // eax
  CEnrollmentLogger *v65; // rax
  char v66; // bl
  CEnrollmentLogger *v67; // rax
  const unsigned __int16 *v68; // rdx
  size_t v69; // rax
  unsigned int v70; // ecx
  int v71; // eax
  CEnrollmentLogger *v72; // rax
  CEnrollmentLogger *v73; // rax
  int v74; // eax
  __int64 v75; // rcx
  char v76; // r12
  char v77; // bl
  int ActiveUserSid; // eax
  __int64 v79; // rcx
  CEnrollmentLogger *v80; // rax
  int String; // eax
  int JoinInfo; // eax
  __int64 v83; // rcx
  CEnrollmentLogger *v84; // rax
  int v85; // r8d
  signed int LastError; // eax
  __int64 v87; // rcx
  CEnrollmentLogger *v88; // rbx
  signed int v89; // eax
  char v90; // di
  struct _ATTESTATION_STATUS *v91; // rbx
  int v92; // r15d
  CEnrollmentLogger *v93; // rax
  int MaaAttestationClaims; // eax
  CEnrollmentLogger *v95; // rax
  __int64 v96; // rcx
  const wchar_t *v97; // r8
  CEnrollmentLogger *v98; // rax
  DWORD v99; // ebx
  unsigned int v100; // edx
  bool v101; // di
  char v102; // r12
  char v103; // r15
  int AttestationClaims; // eax
  struct _ATTESTATION_STATUS *v105; // rbx
  CEnrollmentLogger *v106; // rax
  __int64 v107; // rcx
  const wchar_t *v108; // r8
  CEnrollmentLogger *v109; // rax
  CEnrollmentLogger *v110; // rax
  CEnrollmentLogger *v111; // rax
  DWORD v112; // ebx
  bool v113; // di
  const unsigned __int16 *v114; // r12
  int AadAttestationClaims; // eax
  CEnrollmentLogger *v116; // rax
  CEnrollmentLogger *v117; // rax
  const unsigned __int16 **v118; // rbx
  unsigned __int8 **v119; // rax
  int v120; // r15d
  BOOL v121; // edi
  BOOL v122; // ebx
  CEnrollmentLogger *v123; // rax
  CEnrollmentLogger *v124; // rcx
  int v125; // ebx
  _QWORD *v126; // rax
  int v127; // eax
  CEnrollmentLogger *Logger; // rax
  const unsigned __int16 *v129; // rcx
  HKEY v130; // r12
  UINT v131; // edi
  unsigned __int8 *v132; // rbx
  struct IX509CertificateRequestPkcs10 *v133; // rcx
  struct IX509CertificateRequestPkcs10 *v134; // rdi
  HRESULT (__stdcall *get_RawData)(IX509CertificateRequestPkcs10 *, EncodingType, BSTR *); // rbx
  __int64 v136; // rax
  int v137; // eax
  __int64 v138; // rcx
  unsigned __int16 *v139; // rax
  DWORD *pdwKeySpec; // [rsp+20h] [rbp-E0h]
  BOOL *pfCallerFreeProvOrNCryptKey; // [rsp+28h] [rbp-D8h]
  int DeviceID; // [rsp+70h] [rbp-90h] BYREF
  bool v143[4]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v144; // [rsp+78h] [rbp-88h]
  unsigned int v145; // [rsp+7Ch] [rbp-84h]
  struct _ATTESTATION_STATUS *v146; // [rsp+80h] [rbp-80h] BYREF
  BOOL v147; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-70h] BYREF
  char v149; // [rsp+98h] [rbp-68h]
  unsigned int v150; // [rsp+9Ch] [rbp-64h] BYREF
  DWORD v151; // [rsp+A0h] [rbp-60h] BYREF
  const unsigned __int16 **v152; // [rsp+A8h] [rbp-58h]
  int v153; // [rsp+B0h] [rbp-50h] BYREF
  DWORD TickCount; // [rsp+B4h] [rbp-4Ch] BYREF
  struct IX509PrivateKey *v155; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v156[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v157; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 **v158; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int *v159; // [rsp+D8h] [rbp-28h] BYREF
  struct IX509PrivateKey *v160; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v161; // [rsp+E8h] [rbp-18h] BYREF
  DWORD dwErrCode[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v163; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v164; // [rsp+100h] [rbp+0h] BYREF
  struct IX509CertificateRequestPkcs10 *v165; // [rsp+108h] [rbp+8h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int8 *v167; // [rsp+118h] [rbp+18h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+120h] [rbp+20h] BYREF
  unsigned int *v169; // [rsp+128h] [rbp+28h]
  unsigned __int16 *v170; // [rsp+130h] [rbp+30h] BYREF
  OLECHAR *v171; // [rsp+138h] [rbp+38h]
  void *pvKey; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v173; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int16 *v174; // [rsp+150h] [rbp+50h]
  wchar_t *Source; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v176; // [rsp+160h] [rbp+60h]
  const unsigned __int16 *v177; // [rsp+168h] [rbp+68h]
  unsigned __int8 **v178; // [rsp+170h] [rbp+70h]
  unsigned __int8 **v179; // [rsp+178h] [rbp+78h]
  unsigned __int8 **v180; // [rsp+180h] [rbp+80h]
  unsigned __int8 **v181; // [rsp+188h] [rbp+88h]
  unsigned __int16 **v182; // [rsp+190h] [rbp+90h]
  _BYTE v183[16]; // [rsp+198h] [rbp+98h] BYREF
  char v184[8]; // [rsp+1A8h] [rbp+A8h] BYREF
  char v185[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int8 **v186; // [rsp+1B8h] [rbp+B8h]
  unsigned int *v187; // [rsp+1C0h] [rbp+C0h]
  unsigned int *v188; // [rsp+1C8h] [rbp+C8h]
  unsigned int *v189; // [rsp+1D0h] [rbp+D0h]
  char v190[8]; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned int *v191; // [rsp+1E0h] [rbp+E0h]
  char v192[8]; // [rsp+1E8h] [rbp+E8h] BYREF
  unsigned int *v193; // [rsp+1F0h] [rbp+F0h] BYREF
  char v194; // [rsp+1F8h] [rbp+F8h]
  _QWORD v195[2]; // [rsp+200h] [rbp+100h] BYREF
  CHAR MultiByteStr[80]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v197[256]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v198[264]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v199[264]; // [rsp+670h] [rbp+570h] BYREF

  v144 = a4;
  v145 = a3;
  v27 = a2;
  v152 = a2;
  *(_QWORD *)dwErrCode = a1;
  v29 = a27;
  v146 = a27;
  v174 = lpWideCharStr;
  v171 = a6;
  Source = a11;
  v176 = a12;
  v177 = a13;
  v178 = a14;
  v188 = a15;
  v179 = a16;
  v187 = a17;
  v158 = a18;
  v189 = a19;
  v182 = a20;
  v180 = a21;
  v159 = a22;
  v181 = a23;
  v191 = a24;
  v186 = a25;
  v169 = a26;
  DeviceID = 0;
  v167 = 0;
  v157 = 0;
  hObject = 0;
  v173 = 0;
  v155 = 0;
  v160 = 0;
  v165 = 0;
  pvKey = 0;
  v30 = &wszURI;
  v195[0] = "GenerateCertRequestOld";
  v195[1] = &DeviceID;
  if ( !a20 )
  {
    DeviceID = -2147467261;
LABEL_3:
    v31 = v144;
    goto LABEL_4;
  }
  *(_QWORD *)a27 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pvKey,
    0);
  DeviceID = HeapWideToMultiByteChar(lpWideCharStr, (char **)&pvKey);
  if ( DeviceID < 0 )
    goto LABEL_287;
  v37 = a8;
  if ( a7 && (a8 & 0x20) == 0 )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew>::GetImpl'::`2'::impl,
      1);
    v35 = ProcessRenewalRequestWithRetry(a1, a8, a20);
    DeviceID = v35;
    if ( v35 < 0 )
    {
      v30 = L"ProcessRenewalRequestWithRetry";
      goto LABEL_287;
    }
    goto LABEL_8;
  }
  v38 = pvKey;
  OIDInfo = CryptFindOIDInfo(1u, pvKey, 0);
  if ( OIDInfo )
  {
    if ( OIDInfo->dwGroupId == 1 )
      goto LABEL_37;
    v40 = L"UNKNOWN";
    v41 = OIDInfo->dwGroupId - 2;
    if ( v41 )
    {
      v42 = v41 - 1;
      if ( v42 )
      {
        v43 = v42 - 1;
        if ( v43 )
        {
          v44 = v43 - 1;
          if ( v44 )
          {
            v45 = v44 - 1;
            if ( v45 )
            {
              v46 = v45 - 1;
              if ( v46 )
              {
                v47 = v46 - 1;
                if ( v47 )
                {
                  if ( v47 == 1 )
                    v40 = L"CRYPT_TEMPLATE_OID_GROUP_ID";
                }
                else
                {
                  v40 = L"CRYPT_POLICY_OID_GROUP_ID";
                }
              }
              else
              {
                v40 = L"CRYPT_ENHKEY_USAGE_OID_GROUP_ID";
              }
            }
            else
            {
              v40 = L"CRYPT_EXT_OR_ATTR_OID_GROUP_ID";
            }
          }
          else
          {
            v40 = L"CRYPT_RDN_ATTR_OID_GROUP_ID";
          }
        }
        else
        {
          v40 = L"CRYPT_SIGN_ALG_OID_GROUP_ID";
        }
      }
      else
      {
        v40 = L"CRYPT_PUBKEY_ALG_OID_GROUP_ID";
      }
    }
    else
    {
      v40 = L"CRYPT_ENCRYPT_ALG_OID_GROUP_ID";
    }
  }
  else
  {
    v40 = L"UNKNOWN";
  }
  if ( Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits < 0 )
    McTemplateU0zz_EventWriteTransfer(MDM_ENTERPRISE_DIAGNOSTICS_Context, EnterpriseDiagnosticsBadHash, v174, v40);
  if ( (a8 & 0x20) == 0 )
  {
    v37 = a8 | 0x20;
    LOBYTE(a8) = a8 | 0x20;
  }
LABEL_37:
  DeviceID = ULongLongToULong(0x200u, (unsigned int *)&v147);
  if ( DeviceID < 0 )
  {
    v30 = L"DWordMult";
    goto LABEL_287;
  }
  v167 = 0;
  DeviceID = GetDeviceID(&v167, &v157);
  if ( DeviceID < 0 )
  {
    v30 = L"GetDeviceID";
    goto LABEL_287;
  }
  if ( (v37 & 0x20) != 0 )
  {
    v49 = hObject;
    if ( hObject )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)dwErrCode);
      NCryptFreeObject(v49);
      if ( !LOBYTE(dwErrCode[0]) )
        SetLastError(dwErrCode[1]);
    }
    hObject = 0;
    v31 = v144;
    DeviceID = LegacyCreateKeyWithRetry(v48, v34, v144, (v37 & 4) != 0, (NCRYPT_HANDLE)pdwKeySpec, v197, &hObject);
    if ( DeviceID < 0 )
    {
      v30 = L"LegacyCreateKeyWithRetry";
      goto LABEL_288;
    }
    DeviceID = SetNewContainerAndProvider(a1, v197, L"Microsoft Software Key Storage Provider");
    if ( DeviceID < 0 )
    {
      v30 = L"SetNewContainerAndProvider";
      goto LABEL_288;
    }
    v147 = 0;
    TickCount = 0;
    v146 = 0;
    v155 = 0;
    DeviceID = LegacyCreatePkcs10RequestFromKey(a1, v167, v157, hObject, v38, &v155, &v147, &v146, &TickCount);
    if ( DeviceID < 0 )
    {
      v30 = L"LegacyCreatePkcs10RequestFromKey";
LABEL_51:
      wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&v146);
      wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&v155);
      goto LABEL_288;
    }
    hMem = 0;
    if ( a7 )
    {
      v143[0] = 0;
      DeviceID = GetCurKeyContainer(a1, v197, v50);
      if ( DeviceID < 0 )
      {
        v30 = L"GetCurKeyContainer";
LABEL_55:
        wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&hMem);
        goto LABEL_51;
      }
      ImpersonateIfNeededForCertAccess(a1, v143);
      v157 = 0;
      v158 = 0;
      v51 = Pkcs7SignRequest(v146, TickCount, v197);
      DeviceID = v51;
      if ( v143[0] )
      {
        DmRevertToSelf();
        v51 = DeviceID;
      }
      if ( v51 < 0 )
      {
        v30 = L"Pkcs7SignRequest";
LABEL_60:
        wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&v158);
        goto LABEL_55;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &hMem,
        0);
      DeviceID = EncodeBase64W((const unsigned __int8 *)v158, v157, (unsigned __int16 **)&hMem);
      if ( DeviceID < 0 )
      {
        v30 = L"EncodeBase64W for PKCS7";
        goto LABEL_60;
      }
      wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&v158);
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &hMem,
        0);
      DeviceID = EncodeBase64W((const unsigned __int8 *)v146, TickCount, (unsigned __int16 **)&hMem);
      if ( DeviceID < 0 )
      {
        v30 = L"EncodeBase64W for PKCS10";
        goto LABEL_55;
      }
    }
    v52 = hMem;
    hMem = 0;
    v53 = LocalAllocToHeapAlloc(v52);
    *v182 = v53;
    goto LABEL_55;
  }
  v54 = L"Microsoft Software Key Storage Provider";
  LOBYTE(v34) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseTPMForEnrollmentKey>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_UseTPMForEnrollmentKey>::GetImpl'::`2'::impl,
    v34);
  v55 = CheckServerIsVersionOrAbove(v37, 5);
  if ( !v55 || !v27 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogUsingNonCryptoProvidersPath(Logger, v145, v55);
    v160 = 0;
    v127 = CreateKeyWithRetry(
             (OLECHAR *)L"Microsoft Software Key Storage Provider",
             v171,
             v144,
             (v37 & 4) != 0,
             1,
             (const unsigned __int16 *)pfCallerFreeProvOrNCryptKey,
             v197,
             &v160);
    DeviceID = v127;
    v129 = L"CreateKeyWithRetry";
    if ( v127 >= 0 )
      v129 = &wszURI;
    v30 = v129;
    v155 = v160;
    goto LABEL_270;
  }
  v149 = 0;
  TickCount = GetTickCount();
  hMem = 0;
  v56 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::ensure_data(&hMem);
  tip2::details::shared_data<0,0,0>::start(*v56 + 8LL, &v193);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    (char *)a27 + 8,
    L"Generic Failure",
    15);
  v57 = 0;
  while ( 2 )
  {
    if ( v57 >= v145 )
    {
      v54 = L"Microsoft Software Key Storage Provider";
      goto LABEL_264;
    }
    v58 = 0;
    v143[0] = 0;
    if ( !wcscmp_0(v27[v57], L"Microsoft Platform Crypto Provider") )
    {
      v59 = IsTPMReady(v171, v143, (char *)v29 + 8);
      DeviceID = v59;
      if ( v59 < 0 )
      {
        *((_DWORD *)v29 + 1) = v59;
LABEL_74:
        v30 = L"IsTPMReady";
        v60 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogCryptoProviderInUseResult(v60, v27[v57], DeviceID, L"IsTPMReady", v57, v145);
        goto LABEL_222;
      }
      v58 = v143[0];
      if ( !v143[0] )
      {
        DeviceID = -2146893776;
        *((_DWORD *)v29 + 1) = -2146893776;
        goto LABEL_74;
      }
      DmCheckAikOld();
      v61 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogBeginCreateKeyInTPM(v61, v62);
    }
    v160 = 0;
    if ( v155 )
      ((void (__fastcall *)(struct IX509PrivateKey *))v155->lpVtbl->Release)(v155);
    v63 = v37 & 4;
    v64 = CreateKeyWithRetry(
            (OLECHAR *)v152[v57],
            v171,
            v144,
            v63 != 0,
            !v58,
            (const unsigned __int16 *)pfCallerFreeProvOrNCryptKey,
            v197,
            &v160);
    DeviceID = v64;
    if ( v64 < 0 )
    {
      *(_DWORD *)v29 = 11;
      *((_DWORD *)v29 + 1) = v64;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
        (char *)v29 + 8,
        L"Failed to create key in TPM",
        27);
      v30 = L"CreateKeyWithRetry";
      v65 = CEnrollmentLogger::GetLogger();
      v27 = v152;
      CEnrollmentLogger::LogCryptoProviderInUseResult(v65, v152[v57], DeviceID, L"CreateKeyWithRetry", v57, v145);
      v155 = v160;
      goto LABEL_221;
    }
    v30 = &wszURI;
    v150 = 0;
    v155 = v160;
    if ( !v58 )
      goto LABEL_219;
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                            &hMem,
                            v184)
             + 277LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>(v184);
    v66 = 0;
    v153 = 0;
    v156[0] = 0;
    *(_DWORD *)v29 = 10;
    v67 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEndCreateKeyInTPM(v67, v68, DeviceID);
    if ( Source )
    {
      v69 = wcsnlen(Source, 0xFFFFFFFFFFFFFFFFuLL);
      if ( !v69 )
      {
LABEL_92:
        v66 = 1;
        v30 = L"NonceGeneration";
        v72 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogCryptoProviderInUseResult(v72, v152[v57], DeviceID, L"NonceGeneration", v57, v145);
        goto LABEL_93;
      }
      DeviceID = ULongLongToULong(v69, v156);
      if ( DeviceID < 0 )
      {
        v153 = v156[0];
        goto LABEL_92;
      }
      DeviceID = ULongLongToULong(2LL * v156[0], v156);
      if ( DeviceID < 0 )
        goto LABEL_90;
      v70 = v156[0] + 1;
      v71 = -1;
      if ( v156[0] + 1 >= v156[0] )
        v71 = v156[0] + 1;
      v153 = v71;
      DeviceID = v70 < v156[0] ? 0x80070216 : 0;
      if ( v70 < v156[0] )
      {
LABEL_90:
        v153 = 0;
        goto LABEL_92;
      }
    }
LABEL_93:
    DeviceID = DmGetTargetAikWithRetryOld(TickCount, a10, (enum targetAik *)&v150);
    if ( DeviceID >= 0 && v150
      || (v73 = CEnrollmentLogger::GetLogger(),
          CEnrollmentLogger::LogCryptoProviderInUseResult(
            v73,
            v152[v57],
            DeviceID,
            L"DmGetTargetAikWithRetry",
            v57,
            v145),
          v150) )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                              &hMem,
                              v185)
               + 276LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>(v185);
    }
    if ( !v176 || !v177 || v66 )
    {
      v101 = 1;
      v102 = 0;
      v103 = 0;
      while ( 1 )
      {
        if ( v102 )
        {
          v105 = v146;
        }
        else
        {
          AttestationClaims = GenerateAttestationClaims(v155, (a8 & 4) != 0, v101, v178, v188, v179, v187);
          DeviceID = AttestationClaims;
          v105 = v146;
          if ( AttestationClaims >= 0 )
          {
            v102 = 1;
          }
          else
          {
            v30 = L"GenerateAttestationClaims";
            *((_DWORD *)v146 + 1) = AttestationClaims;
            if ( v101 )
            {
              v106 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogCryptoProviderInUseResult(
                v106,
                v152[v57],
                DeviceID,
                L"GenerateAttestationClaims",
                v57,
                v145);
            }
            if ( !a9 )
            {
LABEL_145:
              wil::com_ptr_t<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>,wil::err_returncode_policy>(&hMem);
              goto LABEL_287;
            }
          }
        }
        if ( !v103 )
        {
          DeviceID = FetchLocalAikCertOld(v155, v101, v158, v189);
          if ( DeviceID < 0 )
          {
            if ( v101 )
            {
              v30 = L"FetchLocalAikCert";
              v153 = 1;
              v151 = 1;
              v147 = 1;
              DmDiagnoseEkAikMissingOld(&v153, (int *)&v151, &v147);
              *((_DWORD *)v105 + 1) = DeviceID;
              if ( !v153 )
              {
                if ( v151 )
                {
                  *(_DWORD *)v105 = 13;
                  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                    (char *)v105 + 8,
                    L"AIK key is not present",
                    22);
                  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
                    goto LABEL_189;
                  v108 = L"DmGetTargetAik can't find AIK key for key attestation";
                }
                else
                {
                  if ( !v147 )
                    goto LABEL_189;
                  *(_DWORD *)v105 = 14;
                  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                    (char *)v105 + 8,
                    L"AIK certificate is not present",
                    30);
                  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
                    goto LABEL_189;
                  v108 = L"DmGetTargetAik can't find AIK cert for key attestation";
                }
LABEL_188:
                McTemplateU0zd_EventWriteTransfer(
                  v107,
                  EnterpriseDiagnosticsTPMFunctionFailure,
                  v108,
                  (unsigned int)DeviceID);
                goto LABEL_189;
              }
              *(_DWORD *)v105 = 12;
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                (char *)v105 + 8,
                L"EK certificate is not present",
                29);
              if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
              {
                v108 = L"DmGetTargetAik can't find EK cert for key attestation";
                goto LABEL_188;
              }
LABEL_189:
              v109 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogCryptoProvidersEkAikMissing(v109, v152[v57], v153, v151, v147);
              v110 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogCryptoProviderInUseResult(
                v110,
                v152[v57],
                DeviceID,
                L"FetchLocalAikCert",
                v57,
                v145);
              if ( !a9 )
                goto LABEL_145;
            }
            if ( (int)DmGetTargetAikOld((enum targetAik *)&v150) >= 0 && v150 > 1 )
            {
              v30 = L"DmGetTargetAik";
              DeviceID = -2146893814;
              *((_DWORD *)v105 + 1) = -2146893814;
              if ( v101 )
              {
                v111 = CEnrollmentLogger::GetLogger();
                CEnrollmentLogger::LogCryptoProviderInUseResult(v111, v152[v57], DeviceID, L"DmGetTargetAik", v57, v145);
              }
              if ( !a9 )
                goto LABEL_145;
              v103 = 1;
            }
            goto LABEL_197;
          }
          v103 = 1;
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                                  &hMem,
                                  v190)
                   + 276LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>(v190);
        }
LABEL_197:
        v112 = (GetTickCount() - TickCount) / 0x3E8;
        Sleep(0x64u);
        if ( a9 != 2 )
          goto LABEL_201;
        if ( v102 && v103 )
          goto LABEL_202;
        v101 = 0;
        if ( v112 >= a10 )
        {
LABEL_201:
          if ( v102 )
          {
LABEL_202:
            DeviceID = 0;
            if ( (a8 & 8) != 0 )
            {
              v113 = 1;
              if ( (unsigned int)(*(_DWORD *)v146 - 12) > 2 )
                *(_DWORD *)v146 = 15;
              v114 = (const unsigned __int16 *)((unsigned __int64)v199
                                              & -(__int64)(OmaDmRegistryGetString(
                                                             *(HKEY *)dwErrCode,
                                                             0,
                                                             L"AADTenantID",
                                                             v199,
                                                             0x104u) >= 0));
              while ( 1 )
              {
                AadAttestationClaims = GenerateAadAttestationClaims(
                                         (a8 & 4) != 0,
                                         v113,
                                         v114,
                                         v180,
                                         v159,
                                         v181,
                                         v191,
                                         v146);
                DeviceID = AadAttestationClaims;
                if ( AadAttestationClaims < 0 )
                {
                  v30 = L"GenerateAadAttestationClaims";
                  *((_DWORD *)v146 + 1) = AadAttestationClaims;
                  if ( v113 )
                  {
                    v116 = CEnrollmentLogger::GetLogger();
                    CEnrollmentLogger::LogCryptoProviderInUseResult(
                      v116,
                      v152[v57],
                      DeviceID,
                      L"GenerateAadAttestationClaims",
                      v57,
                      v145);
                  }
                  if ( !a9 )
                    goto LABEL_145;
                  v113 = 0;
                  v112 = (GetTickCount() - TickCount) / 0x3E8;
                  Sleep(0x64u);
                }
                if ( a9 != 2 )
                  goto LABEL_216;
                if ( DeviceID >= 0 )
                  break;
                if ( v112 >= a10 )
                  goto LABEL_216;
              }
LABEL_217:
              DeviceID = 0;
              goto LABEL_218;
            }
          }
          else
          {
            DeviceID = -2147467259;
          }
LABEL_216:
          if ( a9 - 1 > 1 )
            goto LABEL_218;
          goto LABEL_217;
        }
      }
    }
    phCryptProvOrNCryptKey = 0;
    v164 = 0;
    v74 = RetrieveNcryptHandle(v155, v63 != 0, &v164);
    DeviceID = v74;
    if ( v74 < 0 )
    {
      v30 = L"RetrieveNcryptHandle";
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v75,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"RetrieveNcryptHandle",
          (unsigned int)v74);
      v117 = CEnrollmentLogger::GetLogger();
      v118 = v152;
      CEnrollmentLogger::LogCryptoProviderInUseResult(v117, v152[v57], DeviceID, L"RetrieveNcryptHandle", v57, v145);
      if ( a9 )
      {
        *((_DWORD *)v29 + 1) = DeviceID;
        DeviceID = 0;
      }
      v54 = v118[v57];
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v164);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phCryptProvOrNCryptKey);
      LOBYTE(v37) = a8;
      goto LABEL_264;
    }
    v76 = 1;
    if ( (a8 & 8) == 0 )
      goto LABEL_129;
    *(_QWORD *)v156 = 0;
    v170 = 0;
    v183[0] = 0;
    v183[2] = 0;
    if ( v63 )
      goto LABEL_108;
    v77 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v170,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v170);
    DeviceID = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      v77 = 1;
      v30 = L"DmGetActiveUserSid";
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v79,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DmGetActiveUserSid",
          (unsigned int)ActiveUserSid);
      v80 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogCryptoProviderInUseResult(v80, v152[v57], DeviceID, L"DmGetActiveUserSid", v57, v145);
    }
    AutoImpersonate::ImpersonateSID((AutoImpersonate *)v183, v170);
    if ( !v77 )
    {
LABEL_108:
      String = OmaDmRegistryGetString(*(HKEY *)dwErrCode, 0, L"AADTenantID", v198, 0x104u);
      JoinInfo = DsrGetJoinInfo((unsigned __int64)v198 & -(__int64)(String >= 0), v156);
      DeviceID = JoinInfo;
      if ( JoinInfo >= 0 )
      {
        if ( *(_QWORD *)v156 )
        {
          v193 = v156;
          v194 = 1;
          v151 = 0;
          v147 = 0;
          if ( !CryptAcquireCertificatePrivateKey(
                  *(PCCERT_CONTEXT *)(*(_QWORD *)v156 + 8LL),
                  0x40040u,
                  0,
                  &phCryptProvOrNCryptKey,
                  &v151,
                  &v147) )
          {
            v30 = L"CryptAcquireCertificatePrivateKey";
            if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              McTemplateU0zd_EventWriteTransfer(
                v87,
                EnterpriseDiagnosticsTPMFunctionFailure,
                L"CryptAcquireCertificatePrivateKey",
                (unsigned int)LastError);
            }
            v88 = CEnrollmentLogger::GetLogger();
            v89 = GetLastError();
            if ( v89 > 0 )
              v89 = (unsigned __int16)v89 | 0x80070000;
            CEnrollmentLogger::LogCryptoProviderInUseResult(
              v88,
              v152[v57],
              v89,
              L"CryptAcquireCertificatePrivateKey",
              v57,
              v145);
          }
          if ( !v63 )
            AutoImpersonate::RevertToSelf((AutoImpersonate *)v183);
          v194 = 0;
          DsrFreeJoinInfo(*(_QWORD *)v156);
          goto LABEL_128;
        }
        v30 = L"DsrGetJoinInfo";
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          McTemplateU0zd_EventWriteTransfer(0, EnterpriseDiagnosticsTPMFunctionFailure, L"DsrGetJoinInfo", 2147500035LL);
        v84 = CEnrollmentLogger::GetLogger();
        v85 = -2147467261;
      }
      else
      {
        v30 = L"DsrGetJoinInfo";
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          McTemplateU0zd_EventWriteTransfer(
            v83,
            EnterpriseDiagnosticsTPMFunctionFailure,
            L"DsrGetJoinInfo",
            (unsigned int)JoinInfo);
        v84 = CEnrollmentLogger::GetLogger();
        v85 = DeviceID;
      }
      CEnrollmentLogger::LogCryptoProviderInUseResult(v84, v152[v57], v85, L"DsrGetJoinInfo", v57, v145);
    }
LABEL_128:
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v183);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v170);
LABEL_129:
    v90 = 1;
    v91 = v146;
    v92 = *(_DWORD *)v146;
    do
    {
      *(_DWORD *)v91 = v92;
      DeviceID = DmGetTargetAikOld((enum targetAik *)&v150);
      if ( DeviceID < 0 || !v150 )
      {
        DeviceID = -2147467259;
        if ( !v90 )
          goto LABEL_161;
        v147 = 1;
        v151 = 1;
        v156[0] = 1;
        DmDiagnoseEkAikMissingOld(&v147, (int *)&v151, (int *)v156);
        *((_DWORD *)v91 + 1) = DeviceID;
        v90 = 0;
        if ( v147 )
        {
          *(_DWORD *)v91 = 12;
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            (char *)v91 + 8,
            L"EK certificate is not present",
            29);
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          {
            v97 = L"DmGetTargetAik can't find EK cert for key attestation on MAA";
LABEL_159:
            McTemplateU0zd_EventWriteTransfer(v96, EnterpriseDiagnosticsTPMFunctionFailure, v97, (unsigned int)DeviceID);
          }
        }
        else
        {
          if ( !v151 )
          {
            if ( !v156[0] )
              goto LABEL_160;
            *(_DWORD *)v91 = 14;
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
              (char *)v91 + 8,
              L"AIK certificate is not present",
              30);
            if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
              goto LABEL_160;
            v97 = L"DmGetTargetAik can't find AIK cert for key attestation on MAA";
            goto LABEL_159;
          }
          *(_DWORD *)v91 = 13;
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            (char *)v91 + 8,
            L"AIK key is not present",
            22);
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          {
            v97 = L"DmGetTargetAik can't find AIK key for key attestation on MAA";
            goto LABEL_159;
          }
        }
LABEL_160:
        v98 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogCryptoProvidersEkAikMissing(v98, v152[v57], v147, v151, v156[0]);
        v30 = L"DmGetTargetAik";
        goto LABEL_161;
      }
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                              &hMem,
                              v192)
               + 276LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>(v192);
      if ( v76 )
      {
        v93 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAikChoice(v93, v150);
      }
      v163 = 0;
      v161 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v161,
        0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v163,
        0);
      LODWORD(pfCallerFreeProvOrNCryptKey) = v153;
      MaaAttestationClaims = DmGenerateMaaAttestationClaims(v164, phCryptProvOrNCryptKey, v177, v176, Source);
      DeviceID = MaaAttestationClaims;
      if ( MaaAttestationClaims )
      {
        v30 = L"DmGenerateMaaAttestationClaims";
        *((_DWORD *)v91 + 1) = MaaAttestationClaims;
        if ( v76 )
        {
          v95 = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogCryptoProviderInUseResult(
            v95,
            v152[v57],
            DeviceID,
            L"DmGenerateMaaAttestationClaims",
            v57,
            v145);
          if ( v163 )
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
              (char *)v91 + 8,
              v163);
          if ( v161 )
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
              (char *)v91 + 40,
              v161);
          MaaAttestationClaims = DeviceID;
        }
        if ( !a9 )
        {
          if ( MaaAttestationClaims == 1 )
            DeviceID = -2147467259;
          wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&v161);
          wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&v163);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v164);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phCryptProvOrNCryptKey);
          goto LABEL_145;
        }
      }
      else if ( v161 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (char *)v91 + 40,
          v161);
      }
      v76 = 0;
      wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&v161);
      wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&v163);
LABEL_161:
      v99 = GetTickCount();
      Sleep(0x64u);
      if ( a9 != 2 )
        break;
      if ( !DeviceID )
        break;
      v100 = (v99 - TickCount) / 0x3E8;
      v91 = v146;
    }
    while ( v100 < a10 );
    v149 = 1;
    if ( a9 - 1 <= 1 )
      DeviceID = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v164);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phCryptProvOrNCryptKey);
LABEL_218:
    v29 = v146;
LABEL_219:
    if ( DeviceID < 0 )
    {
      v27 = v152;
LABEL_221:
      LOBYTE(v37) = a8;
LABEL_222:
      ++v57;
      continue;
    }
    break;
  }
  if ( !v178 || !*v178 || !v179 )
  {
    v119 = v158;
LABEL_236:
    v120 = 0;
    goto LABEL_237;
  }
  v119 = v158;
  if ( !*v179 || !v158 || !*v158 )
    goto LABEL_236;
  v120 = 1;
LABEL_237:
  v121 = v180 && *v180 && v181 && *v181 && v119 && *v119;
  v122 = v169 && *v169;
  if ( (!v119 || !*v119) && !v122 )
  {
    LODWORD(pfCallerFreeProvOrNCryptKey) = 0;
    DmCreateTask(
      L"\\Microsoft\\Windows\\EnterpriseMgmt",
      0,
      L"Schedule created by enrollment client to reattest client certificate",
      L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-microsoft-com:a"
       "sm.v3\">     <RegistrationInfo>         <Author>$(@%systemRoot%\\system32\\deviceenroller.exe,-101)</Author>     "
       "    <Description>$(@%systemRoot%\\system32\\deviceenroller.exe,-102)</Description>         <URI>\\Microsoft\\Wind"
       "ows\\EnterpriseMgmt\\TestTask</URI>         <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</Securit"
       "yDescriptor>     </RegistrationInfo>     <Triggers>       <!-- trigger WNF_TPM_PROVISION_STATUS = {0xa3bc4875, 0x"
       "418b1e39} -->       <WnfStateChangeTrigger id=\"TPMProvisioningTrigger\">         <StateName>7548bca3391e8b41</St"
       "ateName>         <Data>7f</Data>         <DataOffset>1</DataOffset>     </WnfStateChangeTrigger>     </Triggers> "
       "    <Principals>         <Principal id=\"LocalSystem\">             <UserId>S-1-5-18</UserId>             <RunLev"
       "el>HighestAvailable</RunLevel>         </Principal>     </Principals>     <Settings>         <MultipleInstancesPo"
       "licy>IgnoreNew</MultipleInstancesPolicy>         <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>  "
       "       <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>         <AllowHardTerminate>false</AllowHardTermina"
       "te>         <StartWhenAvailable>true</StartWhenAvailable>         <RunOnlyIfNetworkAvailable>true</RunOnlyIfNetwo"
       "rkAvailable>         <AllowStartOnDemand>true</AllowStartOnDemand>         <Hidden>false</Hidden>         <RunOnl"
       "yIfIdle>false</RunOnlyIfIdle>         <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>     </Setting"
       "s>     <Actions Context=\"LocalSystem\">         <Exec>             <Command>%windir%\\system32\\deviceenroller.e"
       "xe</Command>             <Arguments>-InitiateReattest</Arguments>         </Exec>     </Actions> </Task>",
      0,
      pfCallerFreeProvOrNCryptKey);
  }
  if ( v120 == 1 && (v121 || (a8 & 8) == 0) || v122 )
  {
    *(_QWORD *)v29 = 1;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      (char *)v29 + 8,
      &wszURI,
      0);
  }
  v169 = (unsigned int *)v152[v57];
  v123 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogCryptoProviderInUseResult(v123, v152[v57], DeviceID, v30, v57, v145);
  v124 = CEnrollmentLogger::GetLogger();
  if ( v149 )
    CEnrollmentLogger::LogAzureAttestationStatus(v124, v122);
  else
    CEnrollmentLogger::LogAttestationStatus(v124, v120, v121);
  LOBYTE(v37) = a8;
  v54 = (const unsigned __int16 *)v169;
  if ( a9 - 1 <= 1 )
    DeviceID = 0;
LABEL_264:
  v125 = *((_DWORD *)v29 + 1);
  if ( !v125 )
    v125 = DeviceID;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                           &hMem,
                           &v159)
            + 272LL) = v125;
  tip2::test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>(&v159);
  v126 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                     &hMem,
                     &v159);
  tip2::details::shared_data<0,0,0>::complete(*v126 + 8LL);
  tip2::test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>(&v159);
  wil::com_ptr_t<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>,wil::err_returncode_policy>(&hMem);
  v127 = DeviceID;
LABEL_270:
  if ( v127 < 0 )
    goto LABEL_3;
  v130 = *(HKEY *)dwErrCode;
  DeviceID = SetNewContainerAndProvider(*(HKEY *)dwErrCode, v197, v54);
  if ( DeviceID >= 0 )
  {
    memset_0(MultiByteStr, 0, 0x45u);
    v147 = 69;
    v131 = v157;
    v132 = v167;
    DeviceID = CreateCertificateName(1u, v130, (const char *)v167, v157, MultiByteStr, (unsigned int *)&v147);
    if ( DeviceID >= 0 )
    {
      v146 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v146,
        0);
      DeviceID = HeapMultiByteToWideChar(MultiByteStr, (unsigned __int16 **)&v146);
      if ( DeviceID >= 0 )
      {
        v133 = v165;
        v165 = 0;
        if ( v133 )
          ((void (__fastcall *)(struct IX509CertificateRequestPkcs10 *))v133->lpVtbl->Release)(v133);
        DeviceID = CreatePkcs10RequestFromKey(
                     v155,
                     (v37 & 4) != 0,
                     (const unsigned __int16 *)v146,
                     v174,
                     (const CHAR *)v132,
                     v131,
                     &v165);
        if ( DeviceID >= 0 )
        {
          v134 = v165;
          get_RawData = v165->lpVtbl->get_RawData;
          v136 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v173);
          v137 = ((__int64 (__fastcall *)(struct IX509CertificateRequestPkcs10 *, __int64, __int64))get_RawData)(
                   v134,
                   1,
                   v136);
          DeviceID = v137;
          if ( v137 >= 0 )
          {
            v139 = HeapStrDup(v173);
            *v182 = v139;
          }
          else
          {
            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
              McTemplateU0zq_EventWriteTransfer(
                v138,
                FunctionFailedEvent,
                L"IX509CertificateRequestPkcs7->get_RawData",
                (unsigned int)v137);
            v30 = L"IX509CertificateRequestPkcs10->get_RawData";
          }
        }
        else
        {
          v30 = L"CreatePkcs10RequestFromKey";
        }
      }
      else
      {
        v30 = L"HeapMultiByteToWideChar";
      }
      wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&v146);
    }
    else
    {
      v30 = L"CreateCertificateName";
    }
  }
  else
  {
    v30 = L"SetNewContainerAndProvider";
  }
LABEL_287:
  v31 = v144;
LABEL_288:
  if ( DeviceID < 0 )
  {
LABEL_4:
    if ( a7 )
    {
      v32 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollCertificateRenewFailed(v32, v30, DeviceID);
    }
    v33 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollCertificateFailedDetailedFunction(v33, v31, v174, v171, v30, DeviceID);
  }
  v35 = DeviceID;
LABEL_8:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v195, (__int64)v34);
  wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&pvKey);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v165);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v160);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v173);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(&v167);
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x18001b3ac  push    rbp
0x18001b3ae  push    rbx
0x18001b3af  push    rsi
0x18001b3b0  push    rdi
0x18001b3b1  push    r12
0x18001b3b3  push    r13
0x18001b3b5  push    r14
0x18001b3b7  push    r15
0x18001b3b9  lea     rbp, [rsp-798h]
0x18001b3c1  sub     rsp, 898h
0x18001b3c8  mov     rax, cs:__security_cookie
0x18001b3cf  xor     rax, rsp
0x18001b3d2  mov     [rbp+7D0h+var_50], rax
0x18001b3d9  mov     [rsp+8D0h+var_858], r9d
0x18001b3de  mov     [rsp+8D0h+var_854], r8d
0x18001b3e3  mov     rdi, rdx
0x18001b3e6  mov     [rbp+7D0h+var_828], rdx
0x18001b3ea  mov     r13, rcx
0x18001b3ed  mov     qword ptr [rbp+7D0h+dwErrCode], rcx
0x18001b3f1  mov     r12, [rbp+7D0h+arg_D0]
0x18001b3f8  mov     [rbp+7D0h+var_850], r12
0x18001b3fc  mov     r14, [rbp+7D0h+lpWideCharStr]
0x18001b403  mov     [rbp+7D0h+var_780], r14
0x18001b407  mov     rax, [rbp+7D0h+arg_28]
0x18001b40e  mov     [rbp+7D0h+var_798], rax
0x18001b412  mov     rax, [rbp+7D0h+arg_50]
0x18001b419  mov     [rbp+7D0h+Source], rax
0x18001b41d  mov     rax, [rbp+7D0h+arg_58]
0x18001b424  mov     [rbp+7D0h+var_770], rax
0x18001b428  mov     rax, [rbp+7D0h+arg_60]
0x18001b42f  mov     [rbp+7D0h+var_768], rax
0x18001b433  mov     rax, [rbp+7D0h+arg_68]
0x18001b43a  mov     [rbp+7D0h+var_760], rax
0x18001b43e  mov     rax, [rbp+7D0h+arg_70]
0x18001b445  mov     [rbp+7D0h+var_708], rax
0x18001b44c  mov     rax, [rbp+7D0h+arg_78]
0x18001b453  mov     [rbp+7D0h+var_758], rax
0x18001b457  mov     rax, [rbp+7D0h+arg_80]
0x18001b45e  mov     [rbp+7D0h+var_710], rax
0x18001b465  mov     rax, [rbp+7D0h+arg_88]
0x18001b46c  mov     [rbp+7D0h+var_800], rax
0x18001b470  mov     rax, [rbp+7D0h+arg_90]
0x18001b477  mov     [rbp+7D0h+var_700], rax
0x18001b47e  mov     rbx, [rbp+7D0h+arg_98]
0x18001b485  mov     [rbp+7D0h+var_740], rbx
0x18001b48c  mov     rax, [rbp+7D0h+arg_A0]
0x18001b493  mov     [rbp+7D0h+var_750], rax
0x18001b49a  mov     rax, [rbp+7D0h+arg_A8]
0x18001b4a1  mov     [rbp+7D0h+var_7F8], rax
0x18001b4a5  mov     rax, [rbp+7D0h+arg_B0]
0x18001b4ac  mov     [rbp+7D0h+var_748], rax
0x18001b4b3  mov     rax, [rbp+7D0h+arg_B8]
0x18001b4ba  mov     [rbp+7D0h+var_6F0], rax
0x18001b4c1  mov     rax, [rbp+7D0h+arg_C0]
0x18001b4c8  mov     [rbp+7D0h+var_718], rax
0x18001b4cf  mov     rax, [rbp+7D0h+arg_C8]
0x18001b4d6  mov     [rbp+7D0h+var_7A8], rax
0x18001b4da  xor     esi, esi
0x18001b4dc  mov     [rsp+8D0h+var_860], esi
0x18001b4e0  mov     [rbp+7D0h+var_7B8], rsi
0x18001b4e4  mov     [rbp+7D0h+var_808], esi
0x18001b4e7  mov     [rbp+7D0h+hObject], rsi
0x18001b4eb  mov     [rbp+7D0h+var_788], rsi
0x18001b4ef  mov     eax, esi
0x18001b4f1  mov     [rbp+7D0h+var_818], rax
0x18001b4f5  mov     [rbp+7D0h+var_7F0], rax
0x18001b4f9  mov     [rbp+7D0h+var_7C8], rsi
0x18001b4fd  mov     [rbp+7D0h+pvKey], rsi
0x18001b501  lea     rsi, wszURI
0x18001b508  lea     rax, aGeneratecertre; "GenerateCertRequestOld"
0x18001b50f  mov     [rbp+7D0h+var_6D0], rax
0x18001b516  lea     rax, [rsp+8D0h+var_860]
0x18001b51b  mov     [rbp+7D0h+var_6C8], rax
0x18001b522  xor     r15d, r15d
0x18001b525  test    rbx, rbx
0x18001b528  jnz     loc_18001B5ED
0x18001b52e  mov     [rsp+8D0h+var_860], 80004003h
0x18001b536  mov     edi, [rsp+8D0h+var_858]
0x18001b53a  cmp     [rbp+7D0h+arg_30], 0
0x18001b541  jz      short loc_18001B558
0x18001b543  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001b548  mov     r8d, [rsp+8D0h+var_860]; int
0x18001b54d  mov     rdx, rsi; unsigned __int16 *
0x18001b550  mov     rcx, rax; this
0x18001b553  call    ?LogEnrollCertificateRenewFailed@CEnrollmentLogger@@QEAAXPEBGJ@Z; CEnrollmentLogger::LogEnrollCertificateRenewFailed(ushort const *,long)
0x18001b558  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001b55d  mov     ecx, [rsp+8D0h+var_860]
0x18001b561  mov     dword ptr [rsp+8D0h+pfCallerFreeProvOrNCryptKey], ecx; int
0x18001b565  mov     [rsp+8D0h+pdwKeySpec], rsi; unsigned __int16 *
0x18001b56a  mov     r9, [rbp+7D0h+var_798]; unsigned __int16 *
0x18001b56e  mov     r8, [rbp+7D0h+var_780]; unsigned __int16 *
0x18001b572  mov     edx, edi; unsigned int
0x18001b574  mov     rcx, rax; this
0x18001b577  call    ?LogEnrollCertificateFailedDetailedFunction@CEnrollmentLogger@@QEAAXKPEBG00J@Z; CEnrollmentLogger::LogEnrollCertificateFailedDetailedFunction(ulong,ushort const *,ushort const *,ushort const *,long)
0x18001b57c  mov     ebx, [rsp+8D0h+var_860]
0x18001b580  lea     rcx, [rbp+7D0h+var_6D0]; this
0x18001b587  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001b58c  nop
0x18001b58d  lea     rcx, [rbp+7D0h+pvKey]
0x18001b591  call    ??1?$unique_storage@U?$resource_policy@PEAU_CERT_PUBLIC_KEY_INFO@@P6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(void)
0x18001b596  nop
0x18001b597  lea     rcx, [rbp+7D0h+var_7C8]
0x18001b59b  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18001b5a0  nop
0x18001b5a1  lea     rcx, [rbp+7D0h+var_7F0]
0x18001b5a5  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18001b5aa  nop
0x18001b5ab  lea     rcx, [rbp+7D0h+var_788]
0x18001b5af  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b5b4  nop
0x18001b5b5  lea     rcx, [rbp+7D0h+hObject]
0x18001b5b9  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001b5be  nop
0x18001b5bf  lea     rcx, [rbp+7D0h+var_7B8]
0x18001b5c3  call    ??1?$unique_storage@U?$resource_policy@PEAU_CERT_PUBLIC_KEY_INFO@@P6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(void)
0x18001b5c8  mov     eax, ebx
0x18001b5ca  mov     rcx, [rbp+7D0h+var_50]
0x18001b5d1  xor     rcx, rsp; StackCookie
0x18001b5d4  call    __security_check_cookie
0x18001b5d9  add     rsp, 898h
0x18001b5e0  pop     r15
0x18001b5e2  pop     r14
0x18001b5e4  pop     r13
0x18001b5e6  pop     r12
0x18001b5e8  pop     rdi
0x18001b5e9  pop     rsi
0x18001b5ea  pop     rbx
0x18001b5eb  pop     rbp
0x18001b5ec  retn
0x18001b5ed  mov     [r12], r15
0x18001b5f1  xor     edx, edx
0x18001b5f3  lea     rcx, [rbp+7D0h+pvKey]
0x18001b5f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b5fc  lea     rdx, [rbp+7D0h+pvKey]; char **
0x18001b600  mov     rcx, r14; lpWideCharStr
0x18001b603  call    ?HeapWideToMultiByteChar@@YAJPEBGPEAPEAD@Z; HeapWideToMultiByteChar(ushort const *,char * *)
0x18001b608  mov     [rsp+8D0h+var_860], eax
0x18001b60c  test    eax, eax
0x18001b60e  js      loc_18001CC87
0x18001b614  cmp     [rbp+7D0h+arg_30], r15d
0x18001b61b  mov     r15d, [rbp+7D0h+arg_38]
0x18001b622  jz      short loc_18001B663
0x18001b624  test    r15b, 20h
0x18001b628  jnz     short loc_18001B663
0x18001b62a  mov     edx, 1
0x18001b62f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew> `wil::Feature<__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew>::GetImpl(void)'::`2'::impl
0x18001b636  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001b63b  mov     r8, rbx; unsigned __int16 **
0x18001b63e  mov     edx, r15d; unsigned int
0x18001b641  mov     rcx, r13; HKEY
0x18001b644  call    ?ProcessRenewalRequestWithRetry@@YAJPEAUHKEY__@@KPEAPEAG@Z; ProcessRenewalRequestWithRetry(HKEY__ *,ulong,ushort * *)
0x18001b649  mov     ebx, eax
0x18001b64b  mov     [rsp+8D0h+var_860], eax
0x18001b64f  test    eax, eax
0x18001b651  jns     loc_18001B580
0x18001b657  lea     rsi, aProcessrenewal; "ProcessRenewalRequestWithRetry"
0x18001b65e  jmp     loc_18001CC87
0x18001b663  xor     r8d, r8d; dwGroupId
0x18001b666  mov     rbx, [rbp+7D0h+pvKey]
0x18001b66a  mov     rdx, rbx; pvKey
0x18001b66d  lea     r14d, [r8+1]
0x18001b671  mov     ecx, r14d; dwKeyType
0x18001b674  call    cs:__imp_CryptFindOIDInfo
0x18001b67a  test    rax, rax
0x18001b67d  jz      loc_18001B707
0x18001b683  cmp     [rax+18h], r14d
0x18001b687  jz      loc_18001B73F
0x18001b68d  lea     r9, aUnknown_0; "UNKNOWN"
0x18001b694  mov     eax, [rax+18h]
0x18001b697  sub     eax, 2
0x18001b69a  jz      short loc_18001B6FE
0x18001b69c  sub     eax, r14d
0x18001b69f  jz      short loc_18001B6F5
0x18001b6a1  sub     eax, r14d
0x18001b6a4  jz      short loc_18001B6EC
0x18001b6a6  sub     eax, r14d
0x18001b6a9  jz      short loc_18001B6E3
0x18001b6ab  sub     eax, r14d
0x18001b6ae  jz      short loc_18001B6DA
0x18001b6b0  sub     eax, r14d
0x18001b6b3  jz      short loc_18001B6D1
0x18001b6b5  sub     eax, r14d
0x18001b6b8  jz      short loc_18001B6C8
0x18001b6ba  cmp     eax, r14d
0x18001b6bd  jnz     short loc_18001B70E
0x18001b6bf  lea     r9, aCryptTemplateO; "CRYPT_TEMPLATE_OID_GROUP_ID"
0x18001b6c6  jmp     short loc_18001B70E
0x18001b6c8  lea     r9, aCryptPolicyOid; "CRYPT_POLICY_OID_GROUP_ID"
0x18001b6cf  jmp     short loc_18001B70E
0x18001b6d1  lea     r9, aCryptEnhkeyUsa; "CRYPT_ENHKEY_USAGE_OID_GROUP_ID"
0x18001b6d8  jmp     short loc_18001B70E
0x18001b6da  lea     r9, aCryptExtOrAttr; "CRYPT_EXT_OR_ATTR_OID_GROUP_ID"
0x18001b6e1  jmp     short loc_18001B70E
0x18001b6e3  lea     r9, aCryptRdnAttrOi; "CRYPT_RDN_ATTR_OID_GROUP_ID"
0x18001b6ea  jmp     short loc_18001B70E
0x18001b6ec  lea     r9, aCryptSignAlgOi; "CRYPT_SIGN_ALG_OID_GROUP_ID"
0x18001b6f3  jmp     short loc_18001B70E
0x18001b6f5  lea     r9, aCryptPubkeyAlg; "CRYPT_PUBKEY_ALG_OID_GROUP_ID"
0x18001b6fc  jmp     short loc_18001B70E
0x18001b6fe  lea     r9, aCryptEncryptAl; "CRYPT_ENCRYPT_ALG_OID_GROUP_ID"
0x18001b705  jmp     short loc_18001B70E
0x18001b707  lea     r9, aUnknown_0; "UNKNOWN"
0x18001b70e  cmp     cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 0
0x18001b715  jge     short loc_18001B72E
0x18001b717  mov     r8, [rbp+7D0h+var_780]
0x18001b71b  lea     rdx, EnterpriseDiagnosticsBadHash
0x18001b722  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18001b729  call    McTemplateU0zz_EventWriteTransfer
0x18001b72e  test    r15b, 20h
0x18001b732  jnz     short loc_18001B73F
0x18001b734  or      r15d, 20h
0x18001b738  mov     [rbp+7D0h+arg_38], r15d
0x18001b73f  lea     rdx, [rbp+7D0h+var_848]; unsigned int *
0x18001b743  mov     ecx, 200h; unsigned __int64
0x18001b748  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001b74d  mov     [rsp+8D0h+var_860], eax
0x18001b751  test    eax, eax
0x18001b753  jns     short loc_18001B761
0x18001b755  lea     rsi, aDwordmult; "DWordMult"
0x18001b75c  jmp     loc_18001CC87
0x18001b761  mov     [rbp+7D0h+var_7B8], 0
0x18001b769  lea     rdx, [rbp+7D0h+var_808]; unsigned int *
0x18001b76d  lea     rcx, [rbp+7D0h+var_7B8]; unsigned __int8 **
0x18001b771  call    ?GetDeviceID@@YAJPEAPEAEAEAK@Z; GetDeviceID(uchar * *,ulong &)
0x18001b776  mov     [rsp+8D0h+var_860], eax
0x18001b77a  test    eax, eax
0x18001b77c  jns     short loc_18001B78A
0x18001b77e  lea     rsi, aGetdeviceid; "GetDeviceID"
0x18001b785  jmp     loc_18001CC87
0x18001b78a  test    r15b, 20h
0x18001b78e  jz      loc_18001B9F2
0x18001b794  mov     rdi, [rbp+7D0h+hObject]
0x18001b798  test    rdi, rdi
0x18001b79b  jz      short loc_18001B7BE
0x18001b79d  lea     rcx, [rbp+7D0h+dwErrCode]; this
0x18001b7a1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001b7a6  mov     rcx, rdi; hObject
0x18001b7a9  call    cs:__imp_NCryptFreeObject
0x18001b7af  cmp     byte ptr [rbp+7D0h+dwErrCode], 0
0x18001b7b3  jnz     short loc_18001B7BE
0x18001b7b5  mov     ecx, [rbp+7D0h+dwErrCode+4]; dwErrCode
0x18001b7b8  call    cs:__imp_SetLastError
0x18001b7be  mov     [rbp+7D0h+hObject], 0
0x18001b7c6  test    r15b, 4
0x18001b7ca  setnbe  r9b; bool
0x18001b7ce  lea     rax, [rbp+7D0h+hObject]
0x18001b7d2  mov     [rsp+8D0h+phKey], rax; phKey
0x18001b7d7  lea     rax, [rbp+7D0h+var_670]
0x18001b7de  mov     [rsp+8D0h+pfCallerFreeProvOrNCryptKey], rax; unsigned __int16 *
0x18001b7e3  mov     edi, [rsp+8D0h+var_858]
0x18001b7e7  mov     r8d, edi; unsigned int
0x18001b7ea  call    ?LegacyCreateKeyWithRetry@@YAJPEBG0K_N0PEAGPEA_K@Z; LegacyCreateKeyWithRetry(ushort const *,ushort const *,ulong,bool,ushort const *,ushort *,unsigned __int64 *)
0x18001b7ef  mov     [rsp+8D0h+var_860], eax
0x18001b7f3  test    eax, eax
0x18001b7f5  jns     short loc_18001B803
0x18001b7f7  lea     rsi, aLegacycreateke; "LegacyCreateKeyWithRetry"
0x18001b7fe  jmp     loc_18001CC8B
0x18001b803  lea     r8, pszProviderName; "Microsoft Software Key Storage Provider"
0x18001b80a  lea     rdx, [rbp+7D0h+var_670]; unsigned __int16 *
0x18001b811  mov     rcx, r13; HKEY
0x18001b814  call    ?SetNewContainerAndProvider@@YAJPEAUHKEY__@@PEAGPEBG@Z; SetNewContainerAndProvider(HKEY__ *,ushort *,ushort const *)
0x18001b819  mov     [rsp+8D0h+var_860], eax
0x18001b81d  test    eax, eax
0x18001b81f  jns     short loc_18001B82D
0x18001b821  lea     rsi, aSetnewcontaine; "SetNewContainerAndProvider"
0x18001b828  jmp     loc_18001CC8B
0x18001b82d  mov     [rbp+7D0h+var_848], 0
0x18001b834  mov     [rbp+7D0h+var_81C], 0
0x18001b83b  mov     [rbp+7D0h+var_850], 0
0x18001b843  mov     [rbp+7D0h+var_818], 0
0x18001b84b  lea     rax, [rbp+7D0h+var_81C]
0x18001b84f  mov     [rsp+8D0h+var_890], rax
0x18001b854  lea     rax, [rbp+7D0h+var_850]
0x18001b858  mov     [rsp+8D0h+var_898], rax
0x18001b85d  lea     rax, [rbp+7D0h+var_848]
0x18001b861  mov     [rsp+8D0h+phKey], rax
0x18001b866  lea     rax, [rbp+7D0h+var_818]
0x18001b86a  mov     [rsp+8D0h+pfCallerFreeProvOrNCryptKey], rax
0x18001b86f  mov     [rsp+8D0h+pdwKeySpec], rbx
0x18001b874  mov     r9, [rbp+7D0h+hObject]
0x18001b878  mov     r8d, [rbp+7D0h+var_808]
0x18001b87c  mov     rdx, [rbp+7D0h+var_7B8]
0x18001b880  mov     rcx, r13
0x18001b883  call    LegacyCreatePkcs10RequestFromKey
0x18001b888  mov     [rsp+8D0h+var_860], eax
0x18001b88c  test    eax, eax
0x18001b88e  jns     short loc_18001B8AF
0x18001b890  lea     rsi, aLegacycreatepk; "LegacyCreatePkcs10RequestFromKey"
0x18001b897  lea     rcx, [rbp+7D0h+var_850]
0x18001b89b  call    ??1?$unique_storage@U?$resource_policy@PEAU_CERT_PUBLIC_KEY_INFO@@P6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(void)
0x18001b8a0  nop
0x18001b8a1  lea     rcx, [rbp+7D0h+var_818]
0x18001b8a5  call    ??1?$unique_storage@U?$resource_policy@PEAU_CERT_PUBLIC_KEY_INFO@@P6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_PUBLIC_KEY_INFO *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,_CERT_PUBLIC_KEY_INFO *,_CERT_PUBLIC_KEY_INFO *,0,std::nullptr_t>>(void)
0x18001b8aa  jmp     loc_18001CC8B
0x18001b8af  mov     [rbp+7D0h+hMem], 0
0x18001b8b7  cmp     [rbp+7D0h+arg_30], 0
0x18001b8be  jz      loc_18001B9C2
0x18001b8c4  mov     [rsp+8D0h+var_85C], 0
0x18001b8c9  lea     rdx, [rbp+7D0h+var_670]; unsigned __int16 *
0x18001b8d0  mov     rcx, r13; HKEY
  ... truncated ...
```
