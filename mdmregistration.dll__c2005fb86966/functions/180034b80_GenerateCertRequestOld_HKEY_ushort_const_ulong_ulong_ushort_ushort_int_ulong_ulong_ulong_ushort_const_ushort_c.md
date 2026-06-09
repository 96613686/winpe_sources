# GenerateCertRequestOld(HKEY__ *,ushort const * *,ulong,ulong,ushort *,ushort *,int,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,ushort * *,uchar * *,ulong *,uchar * *,ulong *,uchar * *,ulong *,_ATTESTATION_STATUS *)

- ea: `0x180034b80`
- end: `0x180036a6b`
- name: `?GenerateCertRequestOld@@YAJPEAUHKEY__@@PEAPEBGKKPEAG2HKKKPEBG33PEAPEAEPEAK4545PEAPEAG454545PEAU_ATTESTATION_STATUS@@@Z`
- size: `7915`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, const unsigned __int16 **@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, LPCWCH lpWideCharStr, unsigned __int16 *, int, unsigned int, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int16 **, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, struct _ATTESTATION_STATUS *)`
- caller_count: `1`
- callee_count: `56`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f6bc`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x18000b43c`
- `0x180012fcc`
- `0x1800141b0`
- `0x1800194e0`
- `0x180019f44`
- `0x18001b028`
- `0x18001ce44`
- `0x18001d2f0`
- `0x18001d3e8`
- `0x18001d470`
- `0x18001d5ac`
- `0x18001e0b0`
- `0x180021db4`
- `0x180022450`
- `0x18002d0c4`
- `0x18002f04c`
- `0x180030f84`
- `0x1800312e0`
- `0x180031524`
- `0x1800315b0`
- `0x180031628`
- `0x180032204`
- `0x1800322b0`
- `0x180033dac`
- `0x180034184`
- `0x1800344c8`
- `0x180034b80`
- `0x180036a74`
- `0x180036c44`
- `0x180036da0`
- `0x180036ea0`
- `0x180037174`
- `0x180037648`
- `0x180037b18`
- `0x180037f5c`
- `0x18003894c`
- `0x1800389c8`
- `0x180038c6c`
- `0x180039428`
- `0x180039610`
- `0x18003ae5c`
- `0x180041410`
- `0x18004159c`
- `0x180041618`
- `0x180042278`
- `0x1800422f4`
- `0x180042510`
- `0x1800426f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800355d4`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800355d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034e17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034e83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800350e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003510f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035175`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035215`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035273`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035cfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035d24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035dc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035df4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036863`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034e17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034e83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800350e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003510f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035175`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035215`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035273`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035cfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035d24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035dc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035df4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036863`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034e03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034e6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800350cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800350fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035201`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003525f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035ce6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035d10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035db2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035de0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003684f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034e03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034e6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800350cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800350fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035161`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035201`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003525f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035ce6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035d10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035db2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035de0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003684f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034fe3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034fe3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035ad1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003535e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180035f21`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003633d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003649f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003535e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180035f21`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003633d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003649f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180035f34`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003635f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800364c1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180035f34`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003635f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800364c1`
- `DMCmnUtils!DmCreateTask` at `0x180036663`
- `DMCmnUtils!DmCreateTask` at `0x180036663`
- `DMCmnUtils!DmCheckAikOld` at `0x18003545e`
- `DMCmnUtils!DmCheckAikOld` at `0x18003545e`
- `DMCmnUtils!DmGetTargetAikWithRetryOld` at `0x180035682`
- `DMCmnUtils!DmGetTargetAikWithRetryOld` at `0x180035682`
- `DMCmnUtils!DmGenerateMaaAttestationClaims` at `0x180035c03`
- `DMCmnUtils!DmGenerateMaaAttestationClaims` at `0x180035c03`
- `DMCmnUtils!DmDiagnoseEkAikMissingOld` at `0x180035e2e`
- `DMCmnUtils!DmDiagnoseEkAikMissingOld` at `0x180036178`
- `DMCmnUtils!DmDiagnoseEkAikMissingOld` at `0x180035e2e`
- `DMCmnUtils!DmDiagnoseEkAikMissingOld` at `0x180036178`
- `DMCmnUtils!DmGetTargetAikOld` at `0x180035afc`
- `DMCmnUtils!DmGetTargetAikOld` at `0x180036299`
- `DMCmnUtils!DmGetTargetAikOld` at `0x180035afc`
- `DMCmnUtils!DmGetTargetAikOld` at `0x180036299`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800357b3`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800357b3`
- `DMCmnUtils!EncodeBase64W` at `0x180035239`
- `DMCmnUtils!EncodeBase64W` at `0x1800352ae`
- `DMCmnUtils!EncodeBase64W` at `0x180035239`
- `DMCmnUtils!EncodeBase64W` at `0x1800352ae`
- `DMCmnUtils!DmRevertToSelf` at `0x1800351da`
- `DMCmnUtils!DmRevertToSelf` at `0x18003586a`
- `DMCmnUtils!DmRevertToSelf` at `0x180035a5a`
- `DMCmnUtils!DmRevertToSelf` at `0x1800351da`
- `DMCmnUtils!DmRevertToSelf` at `0x18003586a`
- `DMCmnUtils!DmRevertToSelf` at `0x180035a5a`
- `DMCmnUtils!DmImpersonate` at `0x18003582c`
- `DMCmnUtils!DmImpersonate` at `0x18003582c`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1800358a9`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1800363e9`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1800358a9`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1800363e9`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800359b0`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800359b0`
- `CRYPT32!CryptFindOIDInfo` at `0x180034ea7`
- `CRYPT32!CryptFindOIDInfo` at `0x180034ea7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180035a71`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180035aa3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180035a71`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180035aa3`
- `OLEAUT32!__imp_SysFreeString` at `0x180034e43`
- `OLEAUT32!__imp_SysFreeString` at `0x1800369ff`
- `OLEAUT32!__imp_SysFreeString` at `0x180034e43`
- `OLEAUT32!__imp_SysFreeString` at `0x1800369ff`
- `ncrypt!NCryptFreeObject` at `0x180034e59`
- `ncrypt!NCryptFreeObject` at `0x180034fd5`
- `ncrypt!NCryptFreeObject` at `0x180035d39`
- `ncrypt!NCryptFreeObject` at `0x180035d4f`
- `ncrypt!NCryptFreeObject` at `0x180035f92`
- `ncrypt!NCryptFreeObject` at `0x180035fa9`
- `ncrypt!NCryptFreeObject` at `0x180036589`
- `ncrypt!NCryptFreeObject` at `0x1800365a3`
- `ncrypt!NCryptFreeObject` at `0x180036a15`
- `ncrypt!NCryptFreeObject` at `0x180034e59`
- `ncrypt!NCryptFreeObject` at `0x180034fd5`
- `ncrypt!NCryptFreeObject` at `0x180035d39`
- `ncrypt!NCryptFreeObject` at `0x180035d4f`
- `ncrypt!NCryptFreeObject` at `0x180035f92`
- `ncrypt!NCryptFreeObject` at `0x180035fa9`
- `ncrypt!NCryptFreeObject` at `0x180036589`
- `ncrypt!NCryptFreeObject` at `0x1800365a3`
- `ncrypt!NCryptFreeObject` at `0x180036a15`
- `dsreg!DsrFreeJoinInfo` at `0x180035a92`
- `dsreg!DsrFreeJoinInfo` at `0x180035a92`
- `dsreg!DsrGetJoinInfo` at `0x1800358ce`
- `dsreg!DsrGetJoinInfo` at `0x1800358ce`

## string_xrefs

- `0x18003664c`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">     <RegistrationInfo>         <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>         <Description>$(@%systemRoot%\system32\deviceenroller.exe,-102)</Description>         <URI>\Microsoft\Windows\EnterpriseMgmt\TestTask</URI>         <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>     </RegistrationInfo>     <Triggers>       <`
- `0x180035028`: `LegacyCreateKeyWithRetry`
- `0x1800357ca`: `DmGetActiveUserSid`
- `0x1800357dd`: `DmGetActiveUserSid`
- `0x180035806`: `DmGetActiveUserSid`
- `0x180034efa`: `CRYPT_TEMPLATE_OID_GROUP_ID`
- `0x1800350bd`: `LegacyCreatePkcs10RequestFromKey`
- `0x180035411`: `IsTPMReady`
- `0x18003542c`: `IsTPMReady`
- `0x1800353d3`: `CreateKeyWithRetry`
- `0x18003550c`: `CreateKeyWithRetry`
- `0x180036773`: `CreateKeyWithRetry`
- `0x18003680b`: `CreateCertificateName`
- `0x180036653`: `Schedule created by enrollment client to reattest client certificate`
- `0x1800368c6`: `CreatePkcs10RequestFromKey`
- `0x1800354eb`: `Failed to create key in TPM`

## pseudocode

```c
// Hidden C++ exception states: #wind=73
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
        unsigned int a10,
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
  const unsigned __int16 **v27; // r13
  HKEY v28; // rbx
  struct _ATTESTATION_STATUS *v29; // rsi
  void *v30; // rdi
  const unsigned __int16 *v31; // r14
  __int64 v32; // rcx
  unsigned int v33; // r12d
  unsigned int v34; // r8d
  int v35; // edi
  void *v36; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v38; // rbx
  HANDLE v39; // rax
  PCCRYPT_OID_INFO OIDInfo; // rax
  const wchar_t *v42; // r9
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  unsigned __int8 **v50; // rax
  const unsigned __int16 *v51; // rdx
  const unsigned __int16 *v52; // rcx
  NCRYPT_HANDLE v53; // rdi
  DWORD LastError; // ebx
  unsigned int v55; // esi
  __int64 v56; // rax
  unsigned int v57; // r8d
  void *v58; // rbx
  HANDLE v59; // rax
  struct _ATTESTATION_STATUS *v60; // rbx
  HANDLE v61; // rax
  HLOCAL v62; // rbx
  HANDLE v63; // rax
  unsigned __int16 *v64; // rbx
  HANDLE v65; // rax
  unsigned __int16 **v66; // rax
  unsigned __int16 *v67; // rbx
  HANDLE v68; // rax
  HLOCAL v69; // rcx
  unsigned __int16 *v70; // rax
  unsigned __int16 **v71; // rax
  const WCHAR *v72; // rdi
  unsigned int v73; // r8d
  bool v74; // bl
  void **v75; // rax
  char *v76; // rbx
  unsigned __int64 v77; // rdi
  char v78; // bl
  int v79; // eax
  CEnrollmentLogger *v80; // rax
  CEnrollmentLogger *v81; // rax
  const unsigned __int16 *v82; // rdx
  int v83; // r12d
  bool v84; // r13
  int v85; // eax
  CEnrollmentLogger *v86; // rax
  unsigned int v87; // ebx
  void *v88; // rax
  void *v89; // rcx
  CEnrollmentLogger *v90; // rax
  const unsigned __int16 *v91; // rdx
  size_t v92; // rax
  int v93; // ecx
  unsigned __int64 v94; // rdx
  unsigned int v95; // eax
  int v96; // esi
  CEnrollmentLogger *v97; // rax
  CEnrollmentLogger *v98; // rax
  void *v99; // rax
  void *v100; // rcx
  int v101; // eax
  __int64 v102; // rcx
  char v103; // di
  char v104; // si
  char v105; // bl
  int ActiveUserSid; // eax
  __int64 v107; // rcx
  CEnrollmentLogger *v108; // rax
  LPVOID v109; // r13
  HRESULT v110; // eax
  int String; // eax
  int JoinInfo; // eax
  __int64 v113; // rcx
  CEnrollmentLogger *v114; // rax
  int v115; // r8d
  signed int v116; // eax
  __int64 v117; // rcx
  CEnrollmentLogger *v118; // rbx
  signed int v119; // eax
  HRESULT v120; // ecx
  char v121; // si
  char v122; // r12
  struct _ATTESTATION_STATUS *v123; // rax
  int v124; // r13d
  NCRYPT_HANDLE v125; // rbx
  void *v126; // rax
  void *v127; // rcx
  CEnrollmentLogger *v128; // rax
  int MaaAttestationClaims; // eax
  CEnrollmentLogger *v130; // rax
  __int64 v131; // r8
  void *v132; // rdi
  __int64 v133; // r8
  HANDLE v134; // rax
  void *v135; // rdi
  HANDLE v136; // rax
  __int64 v137; // r8
  HANDLE v138; // rax
  void *v139; // rdi
  HANDLE v140; // rax
  struct _ATTESTATION_STATUS *v141; // rcx
  __int64 v142; // rcx
  const wchar_t *v143; // r8
  CEnrollmentLogger *v144; // rax
  DWORD v145; // edi
  unsigned int v146; // edx
  bool v147; // r12
  int v148; // ebx
  __int64 v149; // rcx
  struct IX509PrivateKey *v150; // rsi
  bool v151; // bl
  char v152; // r12
  char v153; // si
  int AttestationClaims; // eax
  CEnrollmentLogger *v155; // rax
  struct _ATTESTATION_STATUS *v156; // rcx
  __int64 v157; // rcx
  const wchar_t *v158; // r8
  CEnrollmentLogger *v159; // rax
  CEnrollmentLogger *v160; // rax
  CEnrollmentLogger *v161; // rax
  DWORD v162; // edi
  bool v163; // bl
  struct _ATTESTATION_STATUS *v164; // r13
  const unsigned __int16 *v165; // r12
  int AadAttestationClaims; // eax
  CEnrollmentLogger *v167; // rax
  CEnrollmentLogger *v168; // rax
  const unsigned __int16 **v169; // rbx
  unsigned __int8 **v170; // rax
  int v171; // esi
  int v172; // edi
  int v173; // ebx
  LPVOID v174; // r13
  CEnrollmentLogger *v175; // rax
  CEnrollmentLogger *v176; // rcx
  CEnrollmentLogger *Logger; // rax
  const unsigned __int16 *v178; // rcx
  const unsigned __int16 *v179; // r8
  HKEY v180; // rdi
  UINT v181; // ebx
  unsigned __int16 **v182; // rax
  unsigned __int16 *v183; // rbx
  HANDLE v184; // rax
  struct IX509CertificateRequestPkcs10 *v185; // rcx
  struct IX509CertificateRequestPkcs10 *v186; // rdi
  HRESULT (__stdcall *get_RawData)(IX509CertificateRequestPkcs10 *, EncodingType, BSTR *); // rbx
  __int64 v188; // rax
  int v189; // eax
  __int64 v190; // rcx
  unsigned __int16 *v191; // rax
  CEnrollmentLogger *v192; // rax
  CEnrollmentLogger *v193; // rax
  unsigned int v194; // ebx
  DWORD *pdwKeySpec; // [rsp+20h] [rbp-E0h]
  int pdwKeySpeca; // [rsp+20h] [rbp-E0h]
  BOOL *pfCallerFreeProvOrNCryptKey; // [rsp+28h] [rbp-D8h]
  int DeviceID; // [rsp+70h] [rbp-90h] BYREF
  bool v199; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v200; // [rsp+78h] [rbp-88h]
  unsigned int v201; // [rsp+7Ch] [rbp-84h]
  LPVOID lpMem; // [rsp+80h] [rbp-80h] BYREF
  struct _ATTESTATION_STATUS *v203; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v204; // [rsp+90h] [rbp-70h] BYREF
  BOOL v205; // [rsp+98h] [rbp-68h] BYREF
  __int16 v206; // [rsp+9Ch] [rbp-64h]
  HLOCAL v207; // [rsp+A0h] [rbp-60h] BYREF
  char v208[4]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v209; // [rsp+ACh] [rbp-54h] BYREF
  DWORD v210; // [rsp+B0h] [rbp-50h] BYREF
  const unsigned __int16 **v211; // [rsp+B8h] [rbp-48h]
  DWORD TickCount; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v213; // [rsp+C4h] [rbp-3Ch] BYREF
  __int16 v214; // [rsp+C8h] [rbp-38h]
  int v215[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v216; // [rsp+D8h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+E0h] [rbp-20h] BYREF
  struct IX509PrivateKey *v218; // [rsp+E8h] [rbp-18h]
  int v219; // [rsp+F0h] [rbp-10h]
  struct IX509PrivateKey *v220; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID v221; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 **v222; // [rsp+108h] [rbp+8h]
  struct IX509CertificateRequestPkcs10 *v223; // [rsp+110h] [rbp+10h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int8 *v225; // [rsp+120h] [rbp+20h] BYREF
  unsigned int *v226; // [rsp+128h] [rbp+28h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+130h] [rbp+30h] BYREF
  unsigned int *v228; // [rsp+138h] [rbp+38h] BYREF
  LPVOID v229; // [rsp+140h] [rbp+40h] BYREF
  LPVOID v230; // [rsp+148h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+150h] [rbp+50h] BYREF
  HKEY v232; // [rsp+158h] [rbp+58h]
  OLECHAR *v233; // [rsp+160h] [rbp+60h]
  BSTR bstrString; // [rsp+168h] [rbp+68h] BYREF
  LPVOID v235; // [rsp+170h] [rbp+70h] BYREF
  LPVOID v236; // [rsp+178h] [rbp+78h] BYREF
  NCRYPT_HANDLE v237; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 **v238; // [rsp+188h] [rbp+88h]
  unsigned __int16 *v239; // [rsp+190h] [rbp+90h]
  unsigned __int8 **v240; // [rsp+198h] [rbp+98h]
  unsigned __int8 **v241; // [rsp+1A0h] [rbp+A0h]
  unsigned __int8 **v242; // [rsp+1A8h] [rbp+A8h]
  unsigned __int8 **v243; // [rsp+1B0h] [rbp+B0h]
  unsigned int *v244; // [rsp+1B8h] [rbp+B8h]
  wchar_t *Source; // [rsp+1C0h] [rbp+C0h]
  char v246[8]; // [rsp+1C8h] [rbp+C8h] BYREF
  const unsigned __int16 *v247; // [rsp+1D0h] [rbp+D0h]
  const unsigned __int16 *v248; // [rsp+1D8h] [rbp+D8h]
  char v249; // [rsp+1E0h] [rbp+E0h]
  char v250; // [rsp+1E2h] [rbp+E2h]
  unsigned __int8 **v251; // [rsp+1F0h] [rbp+F0h]
  unsigned int *v252; // [rsp+1F8h] [rbp+F8h]
  unsigned int *v253; // [rsp+200h] [rbp+100h]
  unsigned int *v254; // [rsp+208h] [rbp+108h]
  _QWORD v255[2]; // [rsp+210h] [rbp+110h] BYREF
  int *v256; // [rsp+220h] [rbp+120h] BYREF
  char v257; // [rsp+228h] [rbp+128h]
  CHAR MultiByteStr[80]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v259[256]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v260[264]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v261[264]; // [rsp+690h] [rbp+590h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8F8h] [rbp+7F8h]

  v200 = a4;
  v201 = a3;
  v27 = a2;
  v211 = a2;
  v28 = a1;
  v232 = a1;
  v29 = a27;
  v203 = a27;
  v239 = lpWideCharStr;
  v233 = a6;
  Source = a11;
  v247 = a12;
  v248 = a13;
  v240 = a14;
  v253 = a15;
  v241 = a16;
  v252 = a17;
  v222 = a18;
  v254 = a19;
  v238 = a20;
  v242 = a21;
  v226 = a22;
  v243 = a23;
  v228 = a24;
  v251 = a25;
  v244 = a26;
  DeviceID = 0;
  v225 = 0;
  v213 = 0;
  hObject = 0;
  bstrString = 0;
  v218 = 0;
  v220 = 0;
  v223 = 0;
  v30 = 0;
  lpMem = 0;
  v31 = &String2;
  v255[0] = "GenerateCertRequestOld";
  v255[1] = &DeviceID;
  if ( !a20 )
  {
    DeviceID = -2147467261;
    goto LABEL_373;
  }
  *(_QWORD *)a27 = 0;
  lpMem = 0;
  DeviceID = HeapWideToMultiByteChar(lpWideCharStr, (char **)&lpMem);
  if ( DeviceID < 0 )
    goto LABEL_368;
  v33 = a8;
  if ( a7 && (a8 & 0x20) == 0 )
  {
    v34 = *(_DWORD *)Feature_Bypass3rdPartyKspsInRenew__descriptor;
    if ( (*(_DWORD *)Feature_Bypass3rdPartyKspsInRenew__descriptor & 4) == 0 )
    {
      pv = *(LPVOID *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew>::GetCachedFeatureEnabledState(
                        v32,
                        &v226);
      v34 = (unsigned int)pv;
    }
    v213 = 0;
    v214 = 3;
    wil::details::ReportUsageToService(&qword_180070F08, 53191337, (v34 >> 10) & 1, (v34 >> 11) & 1, &v213, 1);
    v35 = ProcessRenewalRequestWithRetry(v28, a8, v238);
    DeviceID = v35;
    if ( v35 < 0 )
    {
      v31 = L"ProcessRenewalRequestWithRetry";
      goto LABEL_368;
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v255);
    v36 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v36);
    }
    if ( v223 )
      ((void (__fastcall *)(struct IX509CertificateRequestPkcs10 *))v223->lpVtbl->Release)(v223);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( hObject )
      NCryptFreeObject(hObject);
    v38 = v225;
    if ( v225 )
    {
      v39 = GetProcessHeap();
      HeapFree(v39, 0, v38);
    }
    return (unsigned int)v35;
  }
  v30 = lpMem;
  OIDInfo = CryptFindOIDInfo(1u, lpMem, 0);
  if ( OIDInfo )
  {
    if ( OIDInfo->dwGroupId == 1 )
      goto LABEL_44;
    v42 = L"UNKNOWN";
    v43 = OIDInfo->dwGroupId - 2;
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
              v48 = v47 - 1;
              if ( v48 )
              {
                v49 = v48 - 1;
                if ( v49 )
                {
                  if ( v49 == 1 )
                    v42 = L"CRYPT_TEMPLATE_OID_GROUP_ID";
                }
                else
                {
                  v42 = L"CRYPT_POLICY_OID_GROUP_ID";
                }
              }
              else
              {
                v42 = L"CRYPT_ENHKEY_USAGE_OID_GROUP_ID";
              }
            }
            else
            {
              v42 = L"CRYPT_EXT_OR_ATTR_OID_GROUP_ID";
            }
          }
          else
          {
            v42 = L"CRYPT_RDN_ATTR_OID_GROUP_ID";
          }
        }
        else
        {
          v42 = L"CRYPT_SIGN_ALG_OID_GROUP_ID";
        }
      }
      else
      {
        v42 = L"CRYPT_PUBKEY_ALG_OID_GROUP_ID";
      }
    }
    else
    {
      v42 = L"CRYPT_ENCRYPT_ALG_OID_GROUP_ID";
    }
  }
  else
  {
    v42 = L"UNKNOWN";
  }
  if ( Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits < 0 )
    McTemplateU0zz_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, EnterpriseDiagnosticsBadHash, v239, v42);
  if ( (a8 & 0x20) == 0 )
  {
    v33 = a8 | 0x20;
    LOBYTE(a8) = a8 | 0x20;
  }
LABEL_44:
  DeviceID = 0;
  v50 = (unsigned __int8 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&v225);
  DeviceID = GetDeviceID(v50, &v213);
  if ( DeviceID < 0 )
  {
    v31 = L"GetDeviceID";
    goto LABEL_369;
  }
  if ( (v33 & 0x20) != 0 )
  {
    v53 = hObject;
    if ( hObject )
    {
      LastError = GetLastError();
      NCryptFreeObject(v53);
      SetLastError(LastError);
      v28 = v232;
    }
    hObject = 0;
    v55 = v200;
    DeviceID = LegacyCreateKeyWithRetry(
                 v52,
                 v51,
                 v200,
                 (v33 & 4) != 0,
                 (const unsigned __int16 *)pdwKeySpec,
                 v259,
                 &hObject);
    if ( DeviceID < 0 )
    {
      v31 = L"LegacyCreateKeyWithRetry";
LABEL_51:
      v30 = lpMem;
      goto LABEL_370;
    }
    DeviceID = SetNewContainerAndProvider(v28, v259, L"Microsoft Software Key Storage Provider");
    if ( DeviceID < 0 )
    {
      v31 = L"SetNewContainerAndProvider";
      goto LABEL_51;
    }
    v205 = 0;
    v204 = 0;
    TickCount = 0;
    v56 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&v204);
    v203 = 0;
    v30 = lpMem;
    DeviceID = LegacyCreatePkcs10RequestFromKey(v28, v225, v213, hObject, lpMem, &v203, &v205, v56, &TickCount);
    if ( DeviceID < 0 )
    {
      v31 = L"LegacyCreatePkcs10RequestFromKey";
LABEL_56:
      v58 = v204;
      if ( v204 )
      {
        v59 = GetProcessHeap();
        HeapFree(v59, 0, v58);
      }
      v60 = v203;
      if ( v203 )
      {
        v61 = GetProcessHeap();
        HeapFree(v61, 0, v60);
      }
      goto LABEL_370;
    }
    v207 = 0;
    if ( a7 )
    {
      v199 = 0;
      DeviceID = GetCurKeyContainer(v28, v259, v57);
      if ( DeviceID < 0 )
      {
        v31 = L"GetCurKeyContainer";
        goto LABEL_63;
      }
      ImpersonateIfNeededForCertAccess(v28, &v199);
      v216 = 0;
      v213 = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&v216);
      DeviceID = Pkcs7SignRequest(v204, TickCount, v259);
      if ( v199 )
        DmRevertToSelf();
      if ( DeviceID < 0 )
      {
        v31 = L"Pkcs7SignRequest";
        goto LABEL_69;
      }
      v66 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&v207);
      DeviceID = EncodeBase64W((const unsigned __int8 *)v216, v213, v66);
      if ( DeviceID < 0 )
      {
        v31 = L"EncodeBase64W for PKCS7";
LABEL_69:
        v64 = v216;
        if ( v216 )
        {
          v65 = GetProcessHeap();
          HeapFree(v65, 0, v64);
        }
        goto LABEL_63;
      }
      v67 = v216;
      if ( v216 )
      {
        v68 = GetProcessHeap();
        HeapFree(v68, 0, v67);
      }
    }
    else
    {
      v71 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&v207);
      DeviceID = EncodeBase64W((const unsigned __int8 *)v204, TickCount, v71);
      if ( DeviceID < 0 )
      {
        v31 = L"EncodeBase64W for PKCS10";
LABEL_63:
        v62 = v207;
        if ( v207 )
        {
          v63 = GetProcessHeap();
          HeapFree(v63, 0, v62);
        }
        goto LABEL_56;
      }
    }
    v69 = v207;
    v207 = 0;
    v70 = LocalAllocToHeapAlloc(v69);
    *v238 = v70;
    goto LABEL_63;
  }
  v72 = L"Microsoft Software Key Storage Provider";
  v73 = *(_DWORD *)Feature_UseTPMForEnrollmentKey__descriptor;
  if ( (*(_DWORD *)Feature_UseTPMForEnrollmentKey__descriptor & 4) == 0 )
  {
    pv = *(LPVOID *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseTPMForEnrollmentKey>::GetCachedFeatureEnabledState(
                      v52,
                      v246);
    v73 = (unsigned int)pv;
  }
  v205 = 0;
  v206 = 3;
  wil::details::ReportUsageToService(&qword_180070E18, 31513978, (v73 >> 10) & 1, (v73 >> 11) & 1, &v205, 1);
  v74 = CheckServerIsVersionOrAbove(v33, 5);
  if ( !v74 || !v27 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogUsingNonCryptoProvidersPath(Logger, v201, v74);
    v220 = 0;
    DeviceID = CreateKeyWithRetry(
                 (OLECHAR *)L"Microsoft Software Key Storage Provider",
                 v233,
                 v200,
                 (v33 & 4) != 0,
                 1,
                 (const unsigned __int16 *)pfCallerFreeProvOrNCryptKey,
                 v259,
                 &v220);
    v178 = L"CreateKeyWithRetry";
    if ( DeviceID >= 0 )
      v178 = &String2;
    v31 = v178;
    v150 = v220;
    v218 = v220;
    goto LABEL_349;
  }
  v199 = 0;
  TickCount = GetTickCount();
  v75 = (void **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>,>(&pv);
  v76 = (char *)*v75;
  *v75 = 0;
  v207 = v76;
  if ( pv )
    tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(pv);
  tip2::details::shared_data<0,0,0>::start(v76 + 8, &v256);
  pv = (char *)a27 + 8;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    (char *)a27 + 8,
    L"Generic Failure",
    15);
  v77 = 0;
  v204 = 0;
  if ( !v201 )
    goto LABEL_244;
LABEL_85:
  v31 = L"CreateKeyWithRetry";
  v78 = 0;
  v208[0] = 0;
  if ( !wcscmp_0(v27[v77], L"Microsoft Platform Crypto Provider") )
  {
    v79 = IsTPMReady(v233, v208, (char *)v29 + 8);
    DeviceID = v79;
    if ( v79 < 0 )
      goto LABEL_87;
    v78 = v208[0];
    if ( !v208[0] )
    {
      v79 = -2146893776;
      DeviceID = -2146893776;
LABEL_87:
      v31 = L"IsTPMReady";
      *((_DWORD *)v29 + 1) = v79;
      v80 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogCryptoProviderInUseResult(v80, v27[v77], DeviceID, L"IsTPMReady", v77, v201);
      goto LABEL_243;
    }
    DmCheckAikOld();
    v81 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogBeginCreateKeyInTPM(v81, v82);
  }
  v220 = 0;
  if ( v218 )
    ((void (__fastcall *)(struct IX509PrivateKey *))v218->lpVtbl->Release)(v218);
  v83 = v33 & 4;
  v84 = v83 != 0;
  v85 = CreateKeyWithRetry(
          (OLECHAR *)v211[v77],
          v233,
          v200,
          v83 != 0,
          v78 == 0,
          (const unsigned __int16 *)pfCallerFreeProvOrNCryptKey,
          v259,
          &v220);
  DeviceID = v85;
  if ( v85 < 0 )
  {
    *(_DWORD *)v29 = 11;
    *((_DWORD *)v29 + 1) = v85;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      (char *)v29 + 8,
      L"Failed to create key in TPM",
      27);
    v86 = CEnrollmentLogger::GetLogger();
    v27 = v211;
    CEnrollmentLogger::LogCryptoProviderInUseResult(v86, v211[v77], DeviceID, L"CreateKeyWithRetry", v77, v201);
    v218 = v220;
    goto LABEL_242;
  }
  v31 = &String2;
  v209 = 0;
  v218 = v220;
  if ( !v78 )
  {
    v147 = v199;
    goto LABEL_240;
  }
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                          &v207,
                          &v229)
           + 277LL) = 1;
  LOBYTE(v87) = 0;
  if ( v229 )
  {
    tip2::details::shared_data<0,0,0>::end_update((char *)v229 + 8);
    v88 = v229;
    v89 = 0;
    v229 = 0;
    if ( v88 )
    {
      tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(v88);
      v89 = v229;
    }
    if ( v89 )
      tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(v89);
  }
  v219 = 0;
  *(_DWORD *)v29 = 10;
  v90 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogEndCreateKeyInTPM(v90, v91, DeviceID);
  if ( !Source )
    goto LABEL_117;
  v92 = wcsnlen(Source, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v92 )
  {
    v93 = -1;
    if ( v92 > 0xFFFFFFFF )
    {
      v219 = -1;
    }
    else
    {
      v94 = 2LL * (unsigned int)v92;
      if ( v94 <= 0xFFFFFFFF )
      {
        v95 = v94 + 1;
        if ( (int)v94 + 1 >= (unsigned int)v94 )
          v93 = v94 + 1;
        DeviceID = v95 < (unsigned int)v94 ? 0x80070216 : 0;
        v87 = (unsigned int)DeviceID >> 31;
        v96 = 0;
        if ( v95 >= (unsigned int)v94 )
          v96 = v93;
        v219 = v96;
        v29 = v203;
LABEL_113:
        if ( !(_BYTE)v87 )
          goto LABEL_117;
        goto LABEL_116;
      }
      v219 = 0;
    }
    LOBYTE(v87) = 1;
    DeviceID = -2147024362;
    goto LABEL_113;
  }
  LOBYTE(v87) = 1;
LABEL_116:
  v31 = L"NonceGeneration";
  v97 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogCryptoProviderInUseResult(v97, v211[v77], DeviceID, L"NonceGeneration", v77, v201);
LABEL_117:
  DeviceID = DmGetTargetAikWithRetryOld(TickCount, a10, (enum targetAik *)&v209);
  if ( DeviceID >= 0 && v209
    || (v98 = CEnrollmentLogger::GetLogger(),
        CEnrollmentLogger::LogCryptoProviderInUseResult(v98, v211[v77], DeviceID, L"DmGetTargetAikWithRetry", v77, v201),
        v209) )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                            &v207,
                            &v230)
             + 276LL) = 1;
    if ( v230 )
    {
      tip2::details::shared_data<0,0,0>::end_update((char *)v230 + 8);
      v99 = v230;
      v100 = 0;
      v230 = 0;
      if ( v99 )
      {
        tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(v99);
        v100 = v230;
      }
      if ( v100 )
        tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(v100);
    }
  }
  if ( v247 && v248 && !(_BYTE)v87 )
  {
    phCryptProvOrNCryptKey = 0;
    v237 = 0;
    v101 = RetrieveNcryptHandle(v218, v83 != 0, &v237);
    DeviceID = v101;
    if ( v101 < 0 )
    {
      v31 = L"RetrieveNcryptHandle";
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v102,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"RetrieveNcryptHandle",
          (unsigned int)v101);
      v168 = CEnrollmentLogger::GetLogger();
      v169 = v211;
      CEnrollmentLogger::LogCryptoProviderInUseResult(v168, v211[v77], DeviceID, L"RetrieveNcryptHandle", v77, v201);
      if ( a9 )
      {
        *((_DWORD *)v29 + 1) = DeviceID;
        DeviceID = 0;
      }
      v72 = v169[v77];
      if ( v237 )
        NCryptFreeObject(v237);
      if ( phCryptProvOrNCryptKey )
        NCryptFreeObject(phCryptProvOrNCryptKey);
      goto LABEL_245;
    }
    if ( (a8 & 8) == 0 )
      goto LABEL_176;
    *(_QWORD *)v215 = 0;
    hMem = 0;
    v103 = 0;
    v249 = 0;
    v104 = 0;
    v250 = 0;
    if ( v83 )
    {
      v109 = v204;
    }
    else
    {
      v105 = 0;
      hMem = 0;
      ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
      DeviceID = ActiveUserSid;
      if ( ActiveUserSid >= 0 )
      {
        v109 = v204;
      }
      else
      {
        v105 = 1;
        v31 = L"DmGetActiveUserSid";
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          McTemplateU0zd_EventWriteTransfer(
            v107,
            EnterpriseDiagnosticsTPMFunctionFailure,
            L"DmGetActiveUserSid",
            (unsigned int)ActiveUserSid);
        v108 = CEnrollmentLogger::GetLogger();
        v109 = v204;
        CEnrollmentLogger::LogCryptoProviderInUseResult(
          v108,
          v211[(_QWORD)v204],
          DeviceID,
          L"DmGetActiveUserSid",
          (unsigned int)v204,
          v201);
      }
      if ( (int)DmImpersonate((const unsigned __int16 *)hMem) >= 0 )
      {
        v103 = 1;
        v249 = 1;
        v104 = 1;
        v250 = 1;
      }
      if ( v105 )
      {
LABEL_139:
        v110 = 0;
        if ( v103 )
        {
          if ( v104 )
          {
            v110 = DmRevertToSelf();
            if ( v110 >= 0 )
            {
              v250 = 0;
LABEL_171:
              v249 = 0;
            }
          }
          else
          {
            v110 = CoRevertToSelf();
            if ( v110 >= 0 )
              goto LABEL_171;
          }
        }
        if ( v110 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x2C,
            (unsigned int)"onecoreuap\\admin\\dm\\published\\inc\\dmraii.hxx",
            (const char *)(unsigned int)v110,
            pdwKeySpeca);
        if ( hMem )
          LocalFree(hMem);
        v77 = (unsigned __int64)v204;
LABEL_176:
        v121 = 1;
        v122 = 1;
        v123 = v203;
        v124 = *(_DWORD *)v203;
        v125 = v237;
        while ( 1 )
        {
          *(_DWORD *)v123 = v124;
          DeviceID = DmGetTargetAikOld((enum targetAik *)&v209);
          if ( DeviceID >= 0 && v209 )
          {
            *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                                    &v207,
                                    &v235)
                     + 276LL) = 1;
            if ( v235 )
            {
              tip2::details::shared_data<0,0,0>::end_update((char *)v235 + 8);
              v126 = v235;
              v127 = 0;
              v235 = 0;
              if ( v126 )
              {
                tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(v126);
                v127 = v235;
              }
              if ( v127 )
                tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(v127);
            }
            if ( v121 )
            {
              v128 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogAikChoice(v128, v209);
            }
            v236 = 0;
            v221 = 0;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&v221);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&v236);
            LODWORD(pfCallerFreeProvOrNCryptKey) = v219;
            MaaAttestationClaims = DmGenerateMaaAttestationClaims(v125, phCryptProvOrNCryptKey, v248, v247, Source);
            DeviceID = MaaAttestationClaims;
            if ( MaaAttestationClaims )
            {
              v31 = L"DmGenerateMaaAttestationClaims";
              *((_DWORD *)v203 + 1) = MaaAttestationClaims;
              if ( !v121 )
                goto LABEL_196;
              v130 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogCryptoProviderInUseResult(
                v130,
                v211[(_QWORD)v204],
                DeviceID,
                L"DmGenerateMaaAttestationClaims",
                (unsigned int)v204,
                v201);
              if ( v236 )
              {
                v131 = -1;
                do
                  ++v131;
                while ( *((_WORD *)v236 + v131) );
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                  pv,
                  v236,
                  v131);
              }
              v132 = v221;
              if ( v221 )
              {
                v133 = -1;
                do
                  ++v133;
                while ( *((_WORD *)v221 + v133) );
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                  (char *)v203 + 40,
                  v221,
                  v133);
LABEL_196:
                v132 = v221;
              }
              if ( !a9 )
              {
                if ( DeviceID == 1 )
                  DeviceID = -2147467259;
                if ( v132 )
                {
                  v134 = GetProcessHeap();
                  HeapFree(v134, 0, v132);
                }
                v135 = v236;
                if ( v236 )
                {
                  v136 = GetProcessHeap();
                  HeapFree(v136, 0, v135);
                }
                if ( v125 )
                  NCryptFreeObject(v125);
                if ( phCryptProvOrNCryptKey )
                  NCryptFreeObject(phCryptProvOrNCryptKey);
                goto LABEL_208;
              }
            }
            else
            {
              v132 = v221;
              if ( v221 )
              {
                v137 = -1;
                do
                  ++v137;
                while ( *((_WORD *)v221 + v137) );
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                  (char *)v203 + 40,
                  v221,
                  v137);
                v132 = v221;
              }
            }
            v121 = 0;
            if ( v132 )
            {
              v138 = GetProcessHeap();
              HeapFree(v138, 0, v132);
            }
            v139 = v236;
            if ( v236 )
            {
              v140 = GetProcessHeap();
              HeapFree(v140, 0, v139);
            }
            goto LABEL_230;
          }
          DeviceID = -2147467259;
          if ( v122 )
            break;
LABEL_230:
          v145 = GetTickCount();
          Sleep(0x64u);
          if ( a9 == 2 )
          {
            if ( DeviceID )
            {
              v146 = (v145 - TickCount) / 0x3E8;
              v77 = (unsigned __int64)v204;
              v123 = v203;
              if ( v146 < a10 )
                continue;
            }
          }
          v147 = 1;
          v199 = 1;
          if ( a9 - 1 <= 1 )
            DeviceID = 0;
          if ( v125 )
            NCryptFreeObject(v125);
          if ( phCryptProvOrNCryptKey )
            NCryptFreeObject(phCryptProvOrNCryptKey);
LABEL_239:
          v29 = v203;
          v77 = (unsigned __int64)v204;
LABEL_240:
          if ( DeviceID < 0 )
          {
            v27 = v211;
LABEL_242:
            LOBYTE(v33) = a8;
LABEL_243:
            v204 = (LPVOID)++v77;
            if ( v77 >= v201 )
            {
LABEL_244:
              v72 = L"Microsoft Software Key Storage Provider";
              goto LABEL_245;
            }
            goto LABEL_85;
          }
          if ( v240 && *v240 && v241 )
          {
            v170 = v222;
            if ( *v241 && v222 && *v222 )
            {
              v171 = 1;
LABEL_322:
              if ( !v242 || !*v242 || !v243 || !*v243 || !v170 || (v172 = 1, !*v170) )
                v172 = 0;
              if ( !v244 || (v173 = 1, !*v244) )
                v173 = 0;
              if ( (!v170 || !*v170) && !v173 )
              {
                LODWORD(pfCallerFreeProvOrNCryptKey) = 0;
                DmCreateTask(
                  L"\\Microsoft\\Windows\\EnterpriseMgmt",
                  0,
                  L"Schedule created by enrollment client to reattest client certificate",
                  L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-mic"
                   "rosoft-com:asm.v3\">     <RegistrationInfo>         <Author>$(@%systemRoot%\\system32\\deviceenroller"
                   ".exe,-101)</Author>         <Description>$(@%systemRoot%\\system32\\deviceenroller.exe,-102)</Descrip"
                   "tion>         <URI>\\Microsoft\\Windows\\EnterpriseMgmt\\TestTask</URI>         <SecurityDescriptor>D"
                   ":(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)</SecurityDescriptor>     </RegistrationInfo>     <Triggers>  "
                   "     <!-- trigger WNF_TPM_PROVISION_STATUS = {0xa3bc4875, 0x418b1e39} -->       <WnfStateChangeTrigge"
                   "r id=\"TPMProvisioningTrigger\">         <StateName>7548bca3391e8b41</StateName>         <Data>7f</Da"
                   "ta>         <DataOffset>1</DataOffset>     </WnfStateChangeTrigger>     </Triggers>     <Principals> "
                   "        <Principal id=\"LocalSystem\">             <UserId>S-1-5-18</UserId>             <RunLevel>Hi"
                   "ghestAvailable</RunLevel>         </Principal>     </Principals>     <Settings>         <MultipleInst"
                   "ancesPolicy>IgnoreNew</MultipleInstancesPolicy>         <DisallowStartIfOnBatteries>false</DisallowSt"
                   "artIfOnBatteries>         <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>         <AllowHardTe"
                   "rminate>false</AllowHardTerminate>         <StartWhenAvailable>true</StartWhenAvailable>         <Run"
                   "OnlyIfNetworkAvailable>true</RunOnlyIfNetworkAvailable>         <AllowStartOnDemand>true</AllowStartO"
                   "nDemand>         <Hidden>false</Hidden>         <RunOnlyIfIdle>false</RunOnlyIfIdle>         <UseUnif"
                   "iedSchedulingEngine>true</UseUnifiedSchedulingEngine>     </Settings>     <Actions Context=\"LocalSys"
                   "tem\">         <Exec>             <Command>%windir%\\system32\\deviceenroller.exe</Command>          "
                   "   <Arguments>-InitiateReattest</Arguments>         </Exec>     </Actions> </Task>",
                  0,
                  pfCallerFreeProvOrNCryptKey);
              }
              if ( v171 == 1 && (v172 == 1 || (a8 & 8) == 0) || v173 )
              {
                *(_QWORD *)v203 = 1;
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                  pv,
                  &String2,
                  0);
              }
              v174 = v204;
              pv = (LPVOID)v211[(_QWORD)v204];
              v175 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogCryptoProviderInUseResult(
                v175,
                v211[(_QWORD)v174],
                DeviceID,
                v31,
                (unsigned int)v174,
                v201);
              v176 = CEnrollmentLogger::GetLogger();
              if ( v147 )
                CEnrollmentLogger::LogAzureAttestationStatus(v176, v173);
              else
                CEnrollmentLogger::LogAttestationStatus(v176, v171, v172);
              v72 = (const WCHAR *)pv;
              if ( a9 - 1 <= 1 )
                DeviceID = 0;
LABEL_245:
              v148 = *((_DWORD *)v203 + 1);
              if ( !v148 )
                v148 = DeviceID;
              *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                                       &v207,
                                       &v226)
                        + 272LL) = v148;
              tip2::test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>(&v226);
              v149 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                                  &v207,
                                  &v228)
                   + 8LL;
              *(_DWORD *)(v149 + 64) |= 0xB00u;
              if ( *(_QWORD *)(v149 + 240) )
                tip2::details::shared_data<0,0,0>::complete_helper(v149, 10);
              tip2::test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>(&v228);
              if ( v207 )
                tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(v207);
              LOBYTE(v33) = a8;
              v150 = v218;
LABEL_349:
              if ( DeviceID >= 0 )
              {
                v179 = v72;
                v180 = v232;
                DeviceID = SetNewContainerAndProvider(v232, v259, v179);
                if ( DeviceID >= 0 )
                {
                  memset_0(MultiByteStr, 0, 0x45u);
                  v205 = 69;
                  v181 = v213;
                  DeviceID = CreateCertificateName(1, v180, v225, v213, MultiByteStr, (unsigned int *)&v205);
                  if ( DeviceID >= 0 )
                  {
                    v216 = 0;
                    v182 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,int (*)(void *),&int SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&v216);
                    DeviceID = HeapMultiByteToWideChar(MultiByteStr, v182);
                    if ( DeviceID >= 0 )
                    {
                      v185 = v223;
                      v223 = 0;
                      if ( v185 )
                        ((void (__fastcall *)(struct IX509CertificateRequestPkcs10 *))v185->lpVtbl->Release)(v185);
                      DeviceID = CreatePkcs10RequestFromKey(
                                   v150,
                                   (v33 & 4) != 0,
                                   v216,
                                   v239,
                                   (const CHAR *)v225,
                                   v181,
                                   &v223);
                      if ( DeviceID >= 0 )
                      {
                        v186 = v223;
                        get_RawData = v223->lpVtbl->get_RawData;
                        v188 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&bstrString);
                        v189 = ((__int64 (__fastcall *)(struct IX509CertificateRequestPkcs10 *, __int64, __int64))get_RawData)(
                                 v186,
                                 1,
                                 v188);
                        DeviceID = v189;
                        if ( v189 >= 0 )
                        {
                          v191 = HeapStrDup(bstrString);
                          *v238 = v191;
                        }
                        else
                        {
                          if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
                            McTemplateU0zq_EventWriteTransfer(
                              v190,
                              FunctionFailedEvent,
                              L"IX509CertificateRequestPkcs7->get_RawData",
                              (unsigned int)v189);
                          v31 = L"IX509CertificateRequestPkcs10->get_RawData";
                        }
                      }
                      else
                      {
                        v31 = L"CreatePkcs10RequestFromKey";
                      }
                      if ( v216 )
                        SafeHeapFree(v216);
                    }
                    else
                    {
                      v31 = L"HeapMultiByteToWideChar";
                      v183 = v216;
                      if ( v216 )
                      {
                        v184 = GetProcessHeap();
                        HeapFree(v184, 0, v183);
                      }
                    }
                  }
                  else
                  {
                    v31 = L"CreateCertificateName";
                  }
                }
                else
                {
                  v31 = L"SetNewContainerAndProvider";
                }
                goto LABEL_368;
              }
              v30 = lpMem;
LABEL_373:
              v55 = v200;
              goto LABEL_374;
            }
          }
          else
          {
            v170 = v222;
          }
          v171 = 0;
          goto LABEL_322;
        }
        v205 = 1;
        v210 = 1;
        v215[0] = 1;
        DmDiagnoseEkAikMissingOld(&v205, (int *)&v210, v215);
        v141 = v203;
        *((_DWORD *)v203 + 1) = DeviceID;
        v122 = 0;
        if ( v205 )
        {
          *(_DWORD *)v141 = 12;
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            (char *)v141 + 8,
            L"EK certificate is not present",
            29);
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          {
            v143 = L"DmGetTargetAik can't find EK cert for key attestation on MAA";
LABEL_228:
            McTemplateU0zd_EventWriteTransfer(
              v142,
              EnterpriseDiagnosticsTPMFunctionFailure,
              v143,
              (unsigned int)DeviceID);
          }
        }
        else
        {
          if ( !v210 )
          {
            if ( !v215[0] )
              goto LABEL_229;
            *(_DWORD *)v141 = 14;
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
              (char *)v141 + 8,
              L"AIK certificate is not present",
              30);
            if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
              goto LABEL_229;
            v143 = L"DmGetTargetAik can't find AIK cert for key attestation on MAA";
            goto LABEL_228;
          }
          *(_DWORD *)v141 = 13;
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            (char *)v141 + 8,
            L"AIK key is not present",
            22);
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
          {
            v143 = L"DmGetTargetAik can't find AIK key for key attestation on MAA";
            goto LABEL_228;
          }
        }
LABEL_229:
        v144 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogCryptoProvidersEkAikMissing(v144, v211[v77], v205, v210, v215[0]);
        v31 = L"DmGetTargetAik";
        goto LABEL_230;
      }
    }
    String = OmaDmRegistryGetString(v232, 0, L"AADTenantID", v260, 0x104u);
    JoinInfo = DsrGetJoinInfo((unsigned __int64)v260 & -(__int64)(String >= 0), v215);
    DeviceID = JoinInfo;
    if ( JoinInfo < 0 )
    {
      v31 = L"DsrGetJoinInfo";
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v113,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"DsrGetJoinInfo",
          (unsigned int)JoinInfo);
      v114 = CEnrollmentLogger::GetLogger();
      v115 = DeviceID;
LABEL_152:
      CEnrollmentLogger::LogCryptoProviderInUseResult(
        v114,
        v211[(_QWORD)v109],
        v115,
        L"DsrGetJoinInfo",
        (unsigned int)v109,
        v201);
      goto LABEL_139;
    }
    if ( !*(_QWORD *)v215 )
    {
      v31 = L"DsrGetJoinInfo";
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(0, EnterpriseDiagnosticsTPMFunctionFailure, L"DsrGetJoinInfo", 2147500035LL);
      v114 = CEnrollmentLogger::GetLogger();
      v115 = -2147467261;
      goto LABEL_152;
    }
    v256 = v215;
    v257 = 1;
    v210 = 0;
    v205 = 0;
    if ( !CryptAcquireCertificatePrivateKey(
            *(PCCERT_CONTEXT *)(*(_QWORD *)v215 + 8LL),
            0x40040u,
            0,
            &phCryptProvOrNCryptKey,
            &v210,
            &v205) )
    {
      v31 = L"CryptAcquireCertificatePrivateKey";
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v116 = GetLastError();
        if ( v116 > 0 )
          v116 = (unsigned __int16)v116 | 0x80070000;
        McTemplateU0zd_EventWriteTransfer(
          v117,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"CryptAcquireCertificatePrivateKey",
          (unsigned int)v116);
      }
      v118 = CEnrollmentLogger::GetLogger();
      v119 = GetLastError();
      if ( v119 > 0 )
        v119 = (unsigned __int16)v119 | 0x80070000;
      CEnrollmentLogger::LogCryptoProviderInUseResult(
        v118,
        v211[(_QWORD)v109],
        v119,
        L"CryptAcquireCertificatePrivateKey",
        (unsigned int)v109,
        v201);
    }
    if ( !v83 && v103 )
    {
      if ( !v104 )
      {
        v120 = CoRevertToSelf();
LABEL_167:
        if ( v120 >= 0 )
          v103 = 0;
        goto LABEL_169;
      }
      v120 = DmRevertToSelf();
      if ( v120 >= 0 )
      {
        v104 = 0;
        goto LABEL_167;
      }
    }
LABEL_169:
    v257 = 0;
    DsrFreeJoinInfo(*(_QWORD *)v215);
    goto LABEL_139;
  }
  v151 = 1;
  v152 = 0;
  v153 = 0;
  while ( 1 )
  {
    if ( v152 )
      goto LABEL_261;
    AttestationClaims = GenerateAttestationClaims(v218, v84, v151, v240, v253, v241, v252);
    DeviceID = AttestationClaims;
    if ( AttestationClaims >= 0 )
    {
      v152 = 1;
      goto LABEL_261;
    }
    v31 = L"GenerateAttestationClaims";
    *((_DWORD *)v203 + 1) = AttestationClaims;
    if ( v151 )
    {
      v155 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogCryptoProviderInUseResult(
        v155,
        v211[v77],
        DeviceID,
        L"GenerateAttestationClaims",
        v77,
        v201);
    }
    if ( !a9 )
      break;
LABEL_261:
    if ( v153 )
      goto LABEL_282;
    DeviceID = FetchLocalAikCertOld(v218, v151, v222, v254);
    if ( DeviceID >= 0 )
    {
      v153 = 1;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::operator->(
                              &v207,
                              v246)
               + 276LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>>(v246);
      goto LABEL_282;
    }
    if ( v151 )
    {
      v31 = L"FetchLocalAikCert";
      v215[0] = 1;
      v210 = 1;
      v205 = 1;
      DmDiagnoseEkAikMissingOld(v215, (int *)&v210, &v205);
      v156 = v203;
      *((_DWORD *)v203 + 1) = DeviceID;
      if ( v215[0] )
      {
        *(_DWORD *)v156 = 12;
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (char *)v156 + 8,
          L"EK certificate is not present",
          29);
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        {
          v158 = L"DmGetTargetAik can't find EK cert for key attestation";
          goto LABEL_273;
        }
LABEL_274:
        v159 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogCryptoProvidersEkAikMissing(v159, v211[v77], v215[0], v210, v205);
        v160 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogCryptoProviderInUseResult(v160, v211[v77], DeviceID, L"FetchLocalAikCert", v77, v201);
        if ( !a9 )
          break;
        goto LABEL_275;
      }
      if ( v210 )
      {
        *(_DWORD *)v156 = 13;
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (char *)v156 + 8,
          L"AIK key is not present",
          22);
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
          goto LABEL_274;
        v158 = L"DmGetTargetAik can't find AIK key for key attestation";
      }
      else
      {
        if ( !v205 )
          goto LABEL_274;
        *(_DWORD *)v156 = 14;
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (char *)v156 + 8,
          L"AIK certificate is not present",
          30);
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) == 0 )
          goto LABEL_274;
        v158 = L"DmGetTargetAik can't find AIK cert for key attestation";
      }
LABEL_273:
      McTemplateU0zd_EventWriteTransfer(v157, EnterpriseDiagnosticsTPMFunctionFailure, v158, (unsigned int)DeviceID);
      goto LABEL_274;
    }
LABEL_275:
    if ( (int)DmGetTargetAikOld((enum targetAik *)&v209) >= 0 && v209 > 1 )
    {
      v31 = L"DmGetTargetAik";
      DeviceID = -2146893814;
      *((_DWORD *)v203 + 1) = -2146893814;
      if ( v151 )
      {
        v161 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogCryptoProviderInUseResult(v161, v211[v77], DeviceID, L"DmGetTargetAik", v77, v201);
      }
      if ( !a9 )
        break;
      v153 = 1;
    }
LABEL_282:
    v162 = (GetTickCount() - TickCount) / 0x3E8;
    Sleep(0x64u);
    if ( a9 != 2 )
      goto LABEL_286;
    if ( v152 && v153 )
      goto LABEL_287;
    v151 = 0;
    if ( v162 >= a10 )
    {
LABEL_286:
      if ( v152 )
      {
LABEL_287:
        DeviceID = 0;
        if ( (a8 & 8) != 0 )
        {
          v163 = 1;
          v164 = v203;
          if ( (unsigned int)(*(_DWORD *)v203 - 12) > 2 )
            *(_DWORD *)v203 = 15;
          v165 = (const unsigned __int16 *)((unsigned __int64)v261
                                          & -(__int64)(OmaDmRegistryGetString(v232, 0, L"AADTenantID", v261, 0x104u) >= 0));
          while ( 1 )
          {
            AadAttestationClaims = GenerateAadAttestationClaims((a8 & 4) != 0, v163, v165, v242, v226, v243, v228, v164);
            DeviceID = AadAttestationClaims;
            if ( AadAttestationClaims < 0 )
            {
              v31 = L"GenerateAadAttestationClaims";
              *((_DWORD *)v164 + 1) = AadAttestationClaims;
              if ( v163 )
              {
                v167 = CEnrollmentLogger::GetLogger();
                CEnrollmentLogger::LogCryptoProviderInUseResult(
                  v167,
                  v211[(_QWORD)v204],
                  DeviceID,
                  L"GenerateAadAttestationClaims",
                  (unsigned int)v204,
                  v201);
              }
              if ( !a9 )
                goto LABEL_208;
              v163 = 0;
              v162 = (GetTickCount() - TickCount) / 0x3E8;
              Sleep(0x64u);
            }
            if ( a9 != 2 )
              goto LABEL_301;
            if ( DeviceID >= 0 )
              break;
            if ( v162 >= a10 )
              goto LABEL_301;
          }
LABEL_302:
          DeviceID = 0;
LABEL_303:
          v147 = v199;
          goto LABEL_239;
        }
      }
      else
      {
        DeviceID = -2147467259;
      }
LABEL_301:
      if ( a9 - 1 <= 1 )
        goto LABEL_302;
      goto LABEL_303;
    }
    v77 = (unsigned __int64)v204;
  }
LABEL_208:
  if ( v207 )
    tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::Release(v207);
LABEL_368:
  v30 = lpMem;
LABEL_369:
  v55 = v200;
LABEL_370:
  if ( DeviceID < 0 )
  {
LABEL_374:
    if ( a7 )
    {
      v192 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogEnrollCertificateRenewFailed(v192, v31, DeviceID);
    }
    v193 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollCertificateFailedDetailedFunction(v193, v55, v239, v233, v31, DeviceID);
  }
  v194 = DeviceID;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v255);
  if ( v30 )
    SafeHeapFree(v30);
  if ( v223 )
    ((void (__fastcall *)(struct IX509CertificateRequestPkcs10 *))v223->lpVtbl->Release)(v223);
  if ( v218 )
    ((void (__fastcall *)(struct IX509PrivateKey *))v218->lpVtbl->Release)(v218);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( hObject )
    NCryptFreeObject(hObject);
  if ( v225 )
    SafeHeapFree(v225);
  return v194;
}

```

## disassembly

```asm
0x180034b80  push    rbp
0x180034b82  push    rbx
0x180034b83  push    rsi
0x180034b84  push    rdi
0x180034b85  push    r12
0x180034b87  push    r13
0x180034b89  push    r14
0x180034b8b  push    r15
0x180034b8d  lea     rbp, [rsp-7B8h]
0x180034b95  sub     rsp, 8B8h
0x180034b9c  mov     rax, cs:__security_cookie
0x180034ba3  xor     rax, rsp
0x180034ba6  mov     [rbp+7F0h+var_50], rax
0x180034bad  mov     [rsp+8F0h+var_878], r9d
0x180034bb2  mov     [rsp+8F0h+var_874], r8d
0x180034bb7  mov     r13, rdx
0x180034bba  mov     [rbp+7F0h+var_838], rdx
0x180034bbe  mov     rbx, rcx
0x180034bc1  mov     [rbp+7F0h+var_798], rcx
0x180034bc5  mov     rsi, [rbp+7F0h+arg_D0]
0x180034bcc  mov     [rbp+7F0h+var_868], rsi
0x180034bd0  mov     r8, [rbp+7F0h+lpWideCharStr]
0x180034bd7  mov     [rbp+7F0h+var_760], r8
0x180034bde  mov     rax, [rbp+7F0h+arg_28]
0x180034be5  mov     [rbp+7F0h+var_790], rax
0x180034be9  mov     rax, [rbp+7F0h+arg_50]
0x180034bf0  mov     [rbp+7F0h+Source], rax
0x180034bf7  mov     rax, [rbp+7F0h+arg_58]
0x180034bfe  mov     [rbp+7F0h+var_720], rax
0x180034c05  mov     rax, [rbp+7F0h+arg_60]
0x180034c0c  mov     [rbp+7F0h+var_718], rax
0x180034c13  mov     rax, [rbp+7F0h+arg_68]
0x180034c1a  mov     [rbp+7F0h+var_758], rax
0x180034c21  mov     rax, [rbp+7F0h+arg_70]
0x180034c28  mov     [rbp+7F0h+var_6F0], rax
0x180034c2f  mov     rax, [rbp+7F0h+arg_78]
0x180034c36  mov     [rbp+7F0h+var_750], rax
0x180034c3d  mov     rax, [rbp+7F0h+arg_80]
0x180034c44  mov     [rbp+7F0h+var_6F8], rax
0x180034c4b  mov     rax, [rbp+7F0h+arg_88]
0x180034c52  mov     [rbp+7F0h+var_7E8], rax
0x180034c56  mov     rax, [rbp+7F0h+arg_90]
0x180034c5d  mov     [rbp+7F0h+var_6E8], rax
0x180034c64  mov     rcx, [rbp+7F0h+arg_98]
0x180034c6b  mov     [rbp+7F0h+var_768], rcx
0x180034c72  mov     rax, [rbp+7F0h+arg_A0]
0x180034c79  mov     [rbp+7F0h+var_748], rax
0x180034c80  mov     rax, [rbp+7F0h+arg_A8]
0x180034c87  mov     [rbp+7F0h+var_7C8], rax
0x180034c8b  mov     rax, [rbp+7F0h+arg_B0]
0x180034c92  mov     [rbp+7F0h+var_740], rax
0x180034c99  mov     rax, [rbp+7F0h+arg_B8]
0x180034ca0  mov     [rbp+7F0h+var_7B8], rax
0x180034ca4  mov     rax, [rbp+7F0h+arg_C0]
0x180034cab  mov     [rbp+7F0h+var_700], rax
0x180034cb2  mov     rax, [rbp+7F0h+arg_C8]
0x180034cb9  mov     [rbp+7F0h+var_738], rax
0x180034cc0  xor     r15d, r15d
0x180034cc3  mov     [rsp+8F0h+var_880], r15d
0x180034cc8  mov     [rbp+7F0h+var_7D0], r15
0x180034ccc  mov     [rbp+7F0h+var_82C], r15d
0x180034cd0  mov     [rbp+7F0h+hObject], r15
0x180034cd4  mov     [rbp+7F0h+bstrString], r15
0x180034cd8  mov     eax, r15d
0x180034cdb  mov     [rbp+7F0h+var_808], rax
0x180034cdf  mov     [rbp+7F0h+var_7F8], rax
0x180034ce3  mov     [rbp+7F0h+var_7E0], r15
0x180034ce7  mov     edi, r15d
0x180034cea  mov     [rbp+7F0h+lpMem], r15
0x180034cee  lea     r14, String2
0x180034cf5  lea     rax, aGeneratecertre; "GenerateCertRequestOld"
0x180034cfc  mov     [rbp+7F0h+var_6E0], rax
0x180034d03  lea     rax, [rsp+8F0h+var_880]
0x180034d08  mov     [rbp+7F0h+var_6D8], rax
0x180034d0f  test    rcx, rcx
0x180034d12  jnz     short loc_180034D24
0x180034d14  mov     [rsp+8F0h+var_880], 80004003h
0x180034d1c  xor     r13d, r13d
0x180034d1f  jmp     loc_180036962
0x180034d24  mov     [rsi], r15
0x180034d27  mov     [rbp+7F0h+lpMem], r15
0x180034d2b  lea     rdx, [rbp+7F0h+lpMem]; char **
0x180034d2f  mov     rcx, r8; lpWideCharStr
0x180034d32  call    ?HeapWideToMultiByteChar@@YAJPEBGPEAPEAD@Z; HeapWideToMultiByteChar(ushort const *,char * *)
0x180034d37  mov     [rsp+8F0h+var_880], eax
0x180034d3b  test    eax, eax
0x180034d3d  js      loc_18003694A
0x180034d43  mov     r12d, [rbp+7F0h+arg_38]
0x180034d4a  cmp     [rbp+7F0h+arg_30], r15d
0x180034d51  jz      loc_180034E96
0x180034d57  test    r12b, 20h
0x180034d5b  jnz     loc_180034E96
0x180034d61  mov     rax, cs:Feature_Bypass3rdPartyKspsInRenew__descriptor
0x180034d68  mov     r8d, [rax]
0x180034d6b  test    r8b, 4
0x180034d6f  jnz     short loc_180034D84
0x180034d71  lea     rdx, [rbp+7F0h+var_7C8]
0x180034d75  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bypass3rdPartyKspsInRenew>::GetCachedFeatureEnabledState(void)
0x180034d7a  mov     rcx, [rax]
0x180034d7d  mov     [rbp+7F0h+pv], rcx
0x180034d81  mov     r8d, ecx
0x180034d84  xor     r13d, r13d
0x180034d87  mov     [rbp+7F0h+var_82C], r13d
0x180034d8b  mov     [rbp+7F0h+var_828], 3
0x180034d91  mov     r9d, r8d
0x180034d94  shr     r9d, 0Bh
0x180034d98  lea     r15d, [r13+1]
0x180034d9c  and     r9d, r15d
0x180034d9f  shr     r8d, 0Ah
0x180034da3  and     r8d, r15d
0x180034da6  mov     dword ptr [rsp+8F0h+pfCallerFreeProvOrNCryptKey], r15d
0x180034dab  lea     rax, [rbp+7F0h+var_82C]
0x180034daf  mov     [rsp+8F0h+pdwKeySpec], rax
0x180034db4  mov     edx, 32BA2A9h
0x180034db9  lea     rcx, qword_180070F08
0x180034dc0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180034dc5  mov     r8, [rbp+7F0h+var_768]; unsigned __int16 **
0x180034dcc  mov     edx, r12d; unsigned int
0x180034dcf  mov     rcx, rbx; HKEY
0x180034dd2  call    ?ProcessRenewalRequestWithRetry@@YAJPEAUHKEY__@@KPEAPEAG@Z; ProcessRenewalRequestWithRetry(HKEY__ *,ulong,ushort * *)
0x180034dd7  mov     edi, eax
0x180034dd9  mov     [rsp+8F0h+var_880], eax
0x180034ddd  test    eax, eax
0x180034ddf  jns     short loc_180034DED
0x180034de1  lea     r14, aProcessrenewal; "ProcessRenewalRequestWithRetry"
0x180034de8  jmp     loc_18003694D
0x180034ded  lea     rcx, [rbp+7F0h+var_6E0]; this
0x180034df4  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180034df9  nop
0x180034dfa  mov     rbx, [rbp+7F0h+lpMem]
0x180034dfe  test    rbx, rbx
0x180034e01  jz      short loc_180034E24
0x180034e03  call    cs:__imp_GetProcessHeap
0x180034e0a  nop     dword ptr [rax+rax+00h]
0x180034e0f  mov     rcx, rax; hHeap
0x180034e12  mov     r8, rbx; lpMem
0x180034e15  xor     edx, edx; dwFlags
0x180034e17  call    cs:__imp_HeapFree
0x180034e1e  nop     dword ptr [rax+rax+00h]
0x180034e23  nop
0x180034e24  mov     rcx, [rbp+7F0h+var_7E0]
0x180034e28  test    rcx, rcx
0x180034e2b  jz      short loc_180034E3A
0x180034e2d  mov     rax, [rcx]
0x180034e30  mov     rax, [rax+10h]
0x180034e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e39  nop
0x180034e3a  mov     rcx, [rbp+7F0h+bstrString]; bstrString
0x180034e3e  test    rcx, rcx
0x180034e41  jz      short loc_180034E50
0x180034e43  call    cs:__imp_SysFreeString
0x180034e4a  nop     dword ptr [rax+rax+00h]
0x180034e4f  nop
0x180034e50  mov     rcx, [rbp+7F0h+hObject]; hObject
0x180034e54  test    rcx, rcx
0x180034e57  jz      short loc_180034E66
0x180034e59  call    cs:__imp_NCryptFreeObject
0x180034e60  nop     dword ptr [rax+rax+00h]
0x180034e65  nop
0x180034e66  mov     rbx, [rbp+7F0h+var_7D0]
0x180034e6a  test    rbx, rbx
0x180034e6d  jz      short loc_180034E8F
0x180034e6f  call    cs:__imp_GetProcessHeap
0x180034e76  nop     dword ptr [rax+rax+00h]
0x180034e7b  mov     rcx, rax; hHeap
0x180034e7e  mov     r8, rbx; lpMem
0x180034e81  xor     edx, edx; dwFlags
0x180034e83  call    cs:__imp_HeapFree
0x180034e8a  nop     dword ptr [rax+rax+00h]
0x180034e8f  mov     eax, edi
0x180034e91  jmp     loc_180036A32
0x180034e96  xor     r8d, r8d; dwGroupId
0x180034e99  mov     rdi, [rbp+7F0h+lpMem]
0x180034e9d  mov     rdx, rdi; pvKey
0x180034ea0  lea     r15d, [r8+1]
0x180034ea4  mov     ecx, r15d; dwKeyType
0x180034ea7  call    cs:__imp_CryptFindOIDInfo
0x180034eae  nop     dword ptr [rax+rax+00h]
0x180034eb3  xor     edx, edx
0x180034eb5  test    rax, rax
0x180034eb8  jz      loc_180034F42
0x180034ebe  cmp     [rax+18h], r15d
0x180034ec2  jz      loc_180034F7E
0x180034ec8  lea     r9, aUnknown; "UNKNOWN"
0x180034ecf  mov     eax, [rax+18h]
0x180034ed2  sub     eax, 2
0x180034ed5  jz      short loc_180034F39
0x180034ed7  sub     eax, r15d
0x180034eda  jz      short loc_180034F30
0x180034edc  sub     eax, r15d
0x180034edf  jz      short loc_180034F27
0x180034ee1  sub     eax, r15d
0x180034ee4  jz      short loc_180034F1E
0x180034ee6  sub     eax, r15d
0x180034ee9  jz      short loc_180034F15
0x180034eeb  sub     eax, r15d
0x180034eee  jz      short loc_180034F0C
0x180034ef0  sub     eax, r15d
0x180034ef3  jz      short loc_180034F03
0x180034ef5  cmp     eax, r15d
0x180034ef8  jnz     short loc_180034F49
0x180034efa  lea     r9, aCryptTemplateO; "CRYPT_TEMPLATE_OID_GROUP_ID"
0x180034f01  jmp     short loc_180034F49
0x180034f03  lea     r9, aCryptPolicyOid; "CRYPT_POLICY_OID_GROUP_ID"
0x180034f0a  jmp     short loc_180034F49
0x180034f0c  lea     r9, aCryptEnhkeyUsa; "CRYPT_ENHKEY_USAGE_OID_GROUP_ID"
0x180034f13  jmp     short loc_180034F49
0x180034f15  lea     r9, aCryptExtOrAttr; "CRYPT_EXT_OR_ATTR_OID_GROUP_ID"
0x180034f1c  jmp     short loc_180034F49
0x180034f1e  lea     r9, aCryptRdnAttrOi; "CRYPT_RDN_ATTR_OID_GROUP_ID"
0x180034f25  jmp     short loc_180034F49
0x180034f27  lea     r9, aCryptSignAlgOi; "CRYPT_SIGN_ALG_OID_GROUP_ID"
0x180034f2e  jmp     short loc_180034F49
0x180034f30  lea     r9, aCryptPubkeyAlg; "CRYPT_PUBKEY_ALG_OID_GROUP_ID"
0x180034f37  jmp     short loc_180034F49
0x180034f39  lea     r9, aCryptEncryptAl; "CRYPT_ENCRYPT_ALG_OID_GROUP_ID"
0x180034f40  jmp     short loc_180034F49
0x180034f42  lea     r9, aUnknown; "UNKNOWN"
0x180034f49  cmp     cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, dl
0x180034f4f  jge     short loc_180034F6D
0x180034f51  mov     r8, [rbp+7F0h+var_760]
0x180034f58  lea     rdx, EnterpriseDiagnosticsBadHash
0x180034f5f  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180034f66  call    McTemplateU0zz_EventWriteTransfer
0x180034f6b  xor     edx, edx
0x180034f6d  test    r12b, 20h
0x180034f71  jnz     short loc_180034F7E
0x180034f73  or      r12d, 20h
0x180034f77  mov     [rbp+7F0h+arg_38], r12d
0x180034f7e  mov     [rsp+8F0h+var_880], edx
0x180034f82  lea     rcx, [rbp+7F0h+var_7D0]
0x180034f86  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)
0x180034f8b  mov     rcx, rax; unsigned __int8 **
0x180034f8e  lea     rdx, [rbp+7F0h+var_82C]; unsigned int *
0x180034f92  call    ?GetDeviceID@@YAJPEAPEAEAEAK@Z; GetDeviceID(uchar * *,ulong &)
0x180034f97  mov     [rsp+8F0h+var_880], eax
0x180034f9b  test    eax, eax
0x180034f9d  jns     short loc_180034FAE
0x180034f9f  lea     r14, aGetdeviceid; "GetDeviceID"
0x180034fa6  xor     r13d, r13d
0x180034fa9  jmp     loc_180036951
0x180034fae  test    r12b, 20h
0x180034fb2  jz      loc_1800352CE
0x180034fb8  mov     rdi, [rbp+7F0h+hObject]
0x180034fbc  xor     r13d, r13d
0x180034fbf  test    rdi, rdi
0x180034fc2  jz      short loc_180034FF3
0x180034fc4  call    cs:__imp_GetLastError
0x180034fcb  nop     dword ptr [rax+rax+00h]
0x180034fd0  mov     ebx, eax
0x180034fd2  mov     rcx, rdi; hObject
0x180034fd5  call    cs:__imp_NCryptFreeObject
0x180034fdc  nop     dword ptr [rax+rax+00h]
0x180034fe1  mov     ecx, ebx; dwErrCode
0x180034fe3  call    cs:__imp_SetLastError
0x180034fea  nop     dword ptr [rax+rax+00h]
0x180034fef  mov     rbx, [rbp+7F0h+var_798]
0x180034ff3  mov     [rbp+7F0h+hObject], r13
0x180034ff7  test    r12b, 4
0x180034ffb  setnbe  r9b; bool
0x180034fff  lea     rax, [rbp+7F0h+hObject]
0x180035003  mov     [rsp+8F0h+var_8C0], rax; unsigned __int64 *
0x180035008  lea     rax, [rbp+7F0h+var_670]
0x18003500f  mov     [rsp+8F0h+pfCallerFreeProvOrNCryptKey], rax; unsigned __int16 *
0x180035014  mov     esi, [rsp+8F0h+var_878]
0x180035018  mov     r8d, esi; unsigned int
0x18003501b  call    ?LegacyCreateKeyWithRetry@@YAJPEBG0K_N0PEAGPEA_K@Z; LegacyCreateKeyWithRetry(ushort const *,ushort const *,ulong,bool,ushort const *,ushort *,unsigned __int64 *)
0x180035020  mov     [rsp+8F0h+var_880], eax
0x180035024  test    eax, eax
0x180035026  jns     short loc_180035038
0x180035028  lea     r14, aLegacycreateke; "LegacyCreateKeyWithRetry"
0x18003502f  mov     rdi, [rbp+7F0h+lpMem]
0x180035033  jmp     loc_180036955
0x180035038  lea     r8, pszProviderName; "Microsoft Software Key Storage Provider"
0x18003503f  lea     rdx, [rbp+7F0h+var_670]; unsigned __int16 *
0x180035046  mov     rcx, rbx; HKEY
0x180035049  call    ?SetNewContainerAndProvider@@YAJPEAUHKEY__@@PEAGPEBG@Z; SetNewContainerAndProvider(HKEY__ *,ushort *,ushort const *)
0x18003504e  mov     [rsp+8F0h+var_880], eax
0x180035052  test    eax, eax
0x180035054  jns     short loc_18003505F
0x180035056  lea     r14, aSetnewcontaine; "SetNewContainerAndProvider"
0x18003505d  jmp     short loc_18003502F
0x18003505f  mov     [rbp+7F0h+var_858], r13d
0x180035063  mov     [rbp+7F0h+var_860], r13
0x180035067  mov     [rbp+7F0h+var_830], r13d
0x18003506b  lea     rcx, [rbp+7F0h+var_860]
0x18003506f  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AHPEAX@Z$1?SafeHeapFree@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,int (*)(void *),&SafeHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)
0x180035074  mov     [rbp+7F0h+var_868], r13
0x180035078  lea     rcx, [rbp+7F0h+var_830]
0x18003507c  mov     [rsp+8F0h+var_8B0], rcx
0x180035081  mov     [rsp+8F0h+var_8B8], rax
0x180035086  lea     rax, [rbp+7F0h+var_858]
0x18003508a  mov     [rsp+8F0h+var_8C0], rax
0x18003508f  lea     rax, [rbp+7F0h+var_868]
0x180035093  mov     [rsp+8F0h+pfCallerFreeProvOrNCryptKey], rax
0x180035098  mov     rdi, [rbp+7F0h+lpMem]
0x18003509c  mov     [rsp+8F0h+pdwKeySpec], rdi
0x1800350a1  mov     r9, [rbp+7F0h+hObject]
0x1800350a5  mov     r8d, [rbp+7F0h+var_82C]
0x1800350a9  mov     rdx, [rbp+7F0h+var_7D0]
  ... truncated ...
```
