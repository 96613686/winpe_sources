# KerbILogonUserEx3(void * *,_SECURITY_LOGON_TYPE,void *,void *,ulong,_SECPKG_SURROGATE_LOGON *,KERB_CONVERT_WOW_LOGON,void * *,ulong *,_LUID *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x180025680`
- end: `0x180028aa9`
- name: `?KerbILogonUserEx3@@YAJPEAPEAXW4_SECURITY_LOGON_TYPE@@PEAX2KPEAU_SECPKG_SURROGATE_LOGON@@W4KERB_CONVERT_WOW_LOGON@@0PEAKPEAU_LUID@@PEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@0PEAPEAU_UNICODE_STRING@@99PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `13353`
- prototype: `__int64 __fastcall(void **, _SECURITY_LOGON_TYPE, struct _KERB_INTERACTIVE_LOGON *, unsigned __int64, unsigned int, struct _SECPKG_SURROGATE_LOGON *, int, struct _KERB_INTERACTIVE_PROFILE **, unsigned int *, __int64, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, _QWORD *, UNICODE_STRING **, __int64, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `2`
- callee_count: `74`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800255c0`
- `0x1800b3ba4`

## callees

- `0x180001928`
- `0x18000226c`
- `0x1800063e8`
- `0x1800068d0`
- `0x180006920`
- `0x1800069a0`
- `0x1800069e0`
- `0x180008e18`
- `0x1800093f0`
- `0x18000a630`
- `0x18000b300`
- `0x18000b5c0`
- `0x18001deb0`
- `0x18001e5f0`
- `0x180025680`
- `0x1800290c0`
- `0x18002b678`
- `0x18002b788`
- `0x18002f8b0`
- `0x180030a14`
- `0x1800326a0`
- `0x180032964`
- `0x180032bd4`
- `0x180032fd0`
- `0x1800350b4`
- `0x180035de0`
- `0x18003aef0`
- `0x180048970`
- `0x180048cf0`
- `0x18004960c`
- `0x180058f14`
- `0x180059ed0`
- `0x18005de50`
- `0x18005f7fc`
- `0x180060774`
- `0x1800611a0`
- `0x180061b64`
- `0x1800638a0`
- `0x180063e44`
- `0x18006517c`
- `0x18006a9ac`
- `0x18006c36c`
- `0x18006cb94`
- `0x18006d264`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x180078fa4`
- `0x1800819b0`
- `0x18008a304`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002705e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180027f76`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002705e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180027f76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027854`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027965`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027854`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027965`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180027a6f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180027a6f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180026639`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180026639`
- `ntdll!RtlEqualUnicodeString` at `0x180026dc2`
- `ntdll!RtlEqualUnicodeString` at `0x180027c6a`
- `ntdll!RtlEqualUnicodeString` at `0x180027cb0`
- `ntdll!RtlEqualUnicodeString` at `0x180026dc2`
- `ntdll!RtlEqualUnicodeString` at `0x180027c6a`
- `ntdll!RtlEqualUnicodeString` at `0x180027cb0`
- `ntdll!EtwLogTraceEvent` at `0x18002594b`
- `ntdll!EtwLogTraceEvent` at `0x1800289d6`
- `ntdll!EtwLogTraceEvent` at `0x18002594b`
- `ntdll!EtwLogTraceEvent` at `0x1800289d6`
- `ntdll!RtlCopyLuid` at `0x180025db4`
- `ntdll!RtlCopyLuid` at `0x180025db4`
- `ntdll!RtlPrefixUnicodeString` at `0x1800269b3`
- `ntdll!RtlPrefixUnicodeString` at `0x1800269b3`
- `ntdll!RtlInitUnicodeString` at `0x18002699f`
- `ntdll!RtlInitUnicodeString` at `0x18002881e`
- `ntdll!RtlInitUnicodeString` at `0x180028916`
- `ntdll!RtlInitUnicodeString` at `0x18002699f`
- `ntdll!RtlInitUnicodeString` at `0x18002881e`
- `ntdll!RtlInitUnicodeString` at `0x180028916`
- `ntdll!RtlReleaseResource` at `0x180026dd1`
- `ntdll!RtlReleaseResource` at `0x180026ee4`
- `ntdll!RtlReleaseResource` at `0x180027478`
- `ntdll!RtlReleaseResource` at `0x180028796`
- `ntdll!RtlReleaseResource` at `0x180026dd1`
- `ntdll!RtlReleaseResource` at `0x180026ee4`
- `ntdll!RtlReleaseResource` at `0x180027478`
- `ntdll!RtlReleaseResource` at `0x180028796`
- `ntdll!RtlAcquireResourceShared` at `0x180026daf`
- `ntdll!RtlAcquireResourceShared` at `0x180026ec5`
- `ntdll!RtlAcquireResourceShared` at `0x180027456`
- `ntdll!RtlAcquireResourceShared` at `0x180028778`
- `ntdll!RtlAcquireResourceShared` at `0x180026daf`
- `ntdll!RtlAcquireResourceShared` at `0x180026ec5`
- `ntdll!RtlAcquireResourceShared` at `0x180027456`
- `ntdll!RtlAcquireResourceShared` at `0x180028778`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800260b7`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180026f63`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800260b7`
- `ntdll!NtAllocateLocallyUniqueId` at `0x180026f63`
- `ntdll!RtlEnterCriticalSection` at `0x18002742e`
- `ntdll!RtlEnterCriticalSection` at `0x180027b44`
- `ntdll!RtlEnterCriticalSection` at `0x180027c2e`
- `ntdll!RtlEnterCriticalSection` at `0x180027c56`
- `ntdll!RtlEnterCriticalSection` at `0x180027f0b`
- `ntdll!RtlEnterCriticalSection` at `0x18002742e`
- `ntdll!RtlEnterCriticalSection` at `0x180027b44`
- `ntdll!RtlEnterCriticalSection` at `0x180027c2e`
- `ntdll!RtlEnterCriticalSection` at `0x180027c56`
- `ntdll!RtlEnterCriticalSection` at `0x180027f0b`
- `ntdll!RtlLeaveCriticalSection` at `0x180027447`
- `ntdll!RtlLeaveCriticalSection` at `0x180027ba5`
- `ntdll!RtlLeaveCriticalSection` at `0x180027c48`
- `ntdll!RtlLeaveCriticalSection` at `0x180027c97`
- `ntdll!RtlLeaveCriticalSection` at `0x180027cdd`
- `ntdll!RtlLeaveCriticalSection` at `0x180027d5d`
- `ntdll!RtlLeaveCriticalSection` at `0x180027fdf`
- `ntdll!RtlLeaveCriticalSection` at `0x180027447`
- `ntdll!RtlLeaveCriticalSection` at `0x180027ba5`
- `ntdll!RtlLeaveCriticalSection` at `0x180027c48`
- `ntdll!RtlLeaveCriticalSection` at `0x180027c97`
- `ntdll!RtlLeaveCriticalSection` at `0x180027cdd`
- `ntdll!RtlLeaveCriticalSection` at `0x180027d5d`
- `ntdll!RtlLeaveCriticalSection` at `0x180027fdf`
- `KerbClientShared!KerbClientFreeSupplementalCredentials` at `0x1800282fd`
- `KerbClientShared!KerbClientFreeSupplementalCredentials` at `0x180028594`
- `KerbClientShared!KerbClientFreeSupplementalCredentials` at `0x1800282fd`
- `KerbClientShared!KerbClientFreeSupplementalCredentials` at `0x180028594`
- `CRYPT32!CertFreeCertificateContext` at `0x1800284d2`
- `CRYPT32!CertFreeCertificateContext` at `0x1800284d2`
- `LSASRV!LsaIEfsAcceptSmartcardCredentials` at `0x180028395`
- `LSASRV!LsaIEfsAcceptSmartcardCredentials` at `0x180028395`
- `LSASRV!LsaICheckProtectedUserByTokenInfo` at `0x180027bf8`
- `LSASRV!LsaICheckProtectedUserByTokenInfo` at `0x180027bf8`
- `LSASRV!LsaIAddNamesToLogonSession` at `0x18002802d`
- `LSASRV!LsaIAddNamesToLogonSession` at `0x18002802d`
- `LSASRV!LsarClose` at `0x180026b29`
- `LSASRV!LsarClose` at `0x180026b29`
- `LSASRV!LsaIAllowProtectedCredLogon` at `0x180026657`
- `LSASRV!LsaIAllowProtectedCredLogon` at `0x180026657`
- `LSASRV!LsarOpenSecret` at `0x180026a16`
- `LSASRV!LsarOpenSecret` at `0x180026a16`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180026af4`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180026b1c`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180026af4`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180026b1c`
- `LSASRV!LsaISetUserFlags` at `0x180028041`
- `LSASRV!LsaISetUserFlags` at `0x180028041`
- `LSASRV!LsaISetLogonInfo` at `0x180028143`
- `LSASRV!LsaISetLogonInfo` at `0x180028143`
- `LSASRV!LsaISetLogonGuidInLogonSession` at `0x18002816c`
- `LSASRV!LsaISetLogonGuidInLogonSession` at `0x18002816c`
- `LSASRV!LsaISetPackageAttrInLogonSession` at `0x1800283dd`
- `LSASRV!LsaISetPackageAttrInLogonSession` at `0x1800283dd`
- `LSASRV!LsarQuerySecret` at `0x180026a3c`
- `LSASRV!LsarQuerySecret` at `0x180026a3c`

## string_xrefs

- `0x180027d7c`: `Failed to create logon session: 0x%x`
- `0x180027c08`: `LsaICheckProtectedUserByTokenInfo failed: %#x\n`
- `0x180025f1c`: `Out of bounds read attempted using submit buffer.                                         Size: %d, Ex2PackedCredentialsOffset: %d.`
- `0x180025ca8`: `NGC CloudTrust is NOT enabled. LogonType(0x%x), isNgcDataCloudTrustFlagSet(%d), isKerbAsRepCredNull(%d)`
- `0x180026137`: `KerbCreateLogonSession failed with 0x%x`
- `0x18002694a`: `Failed to get the redirected logon SID: %#x\n`
- `0x180027104`: `logon type is neither service nor batch for managed credential: %#x\n`
- `0x180027143`: `the caller failed access check %#x to create the managed primary credential: %#x\n`
- `0x1800264ac`: `KerbCreateSmartCardLogonSession failed %x\n`
- `0x180027219`: `LsaApLogonUserEx3: attempting to logon user %wZ\%wZ\n`
- `0x1800277b3`: `DC not reachable, caller does not want cached logon\n`
- `0x1800277f4`: `No cache data for FIDO\n`
- `0x1800278ca`: `Attempting cached FIDO logon\n`
- `0x1800276b5`: `LogonUser: Failed to create token from logon ticket: 0x%x\n`
- `0x180027bd1`: `logon type is neither service nor batch for DMSA: %#x\n`
- `0x1800281f2`: `KerbCreateSmartcardEx2PackedCreds failed: 0x%x\n`
- `0x18002840d`: `KerbUpdateSecPkgPrimaryCredsForDmsa failed: %#x\n`

## pseudocode

```c
__int64 __fastcall KerbILogonUserEx3(
        void **a1,
        _SECURITY_LOGON_TYPE a2,
        struct _KERB_INTERACTIVE_LOGON *a3,
        unsigned __int64 a4,
        unsigned int a5,
        struct _SECPKG_SURROGATE_LOGON *a6,
        int a7,
        struct _KERB_INTERACTIVE_PROFILE **a8,
        unsigned int *a9,
        __int64 a10,
        int *a11,
        enum _LSA_TOKEN_INFORMATION_TYPE *a12,
        void **a13,
        _QWORD *a14,
        UNICODE_STRING **a15,
        __int64 a16,
        struct _SECPKG_PRIMARY_CRED *a17,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a18)
{
  struct _KERB_INTERACTIVE_LOGON *v19; // rbx
  struct _SECPKG_SURROGATE_LOGON *v22; // rdi
  struct _SECPKG_PRIMARY_CRED *v23; // r13
  unsigned __int16 *v24; // r12
  int TicketGrantingTicket; // edi
  enum _SECURITY_LOGON_TYPE v26; // ebx
  __int64 v27; // r15
  const CERT_CONTEXT *v28; // rsi
  int v29; // ecx
  int v30; // r8d
  _BYTE *v31; // rcx
  __int64 v32; // rax
  _QWORD *v33; // rax
  UNICODE_STRING *v34; // rax
  __int64 v35; // rdx
  struct _KERB_SUPPLEMENTAL_CREDENTIAL *AsRepCred; // r13
  __int64 v37; // r8
  __int64 v38; // rdx
  char *v39; // rsi
  PLUID v40; // rbx
  unsigned __int8 *v41; // r9
  int LowPart_low; // ecx
  __int64 v43; // rdx
  struct _KERB_INTERACTIVE_LOGON *v44; // r10
  char v45; // r14
  int v46; // r15d
  char v47; // si
  int v48; // eax
  __int64 v49; // r8
  int v50; // ecx
  NTSTATUS v51; // eax
  const char *v52; // r9
  __int64 v53; // r8
  int v54; // eax
  const char *v55; // r9
  __int64 v56; // r8
  int v57; // r14d
  struct _LUID v58; // rax
  unsigned __int8 v59; // r8
  _BYTE *v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rcx
  __int128 *v63; // rax
  WCHAR *v64; // rax
  WCHAR *v65; // rbx
  struct _SECPKG_REDIRECTED_LOGON_BUFFER *v66; // rbx
  signed int v67; // eax
  const char *v68; // r9
  __int64 v69; // r8
  enum _SECURITY_LOGON_TYPE v70; // r9d
  NTSTATUS inited; // eax
  const char *v72; // r9
  __int64 v73; // r8
  __int64 (__fastcall *GetSupplementalCreds)(HANDLE, __int64 *); // rax
  __int64 (__fastcall *v75)(HANDLE, PSID *); // rax
  _SECURITY_LOGON_TYPE v76; // edi
  _WORD *v77; // rdx
  _BYTE *v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rcx
  __int128 *v81; // rax
  void *v82; // rax
  struct _UNICODE_STRING *v83; // r14
  unsigned __int64 v84; // rcx
  __int64 Length; // r9
  struct _UNICODE_STRING *v86; // rsi
  unsigned __int64 v87; // rcx
  __int64 v88; // rdx
  _BYTE *v89; // rcx
  __int64 v90; // rax
  __int64 v91; // rcx
  __int128 *v92; // rax
  __int64 v93; // rcx
  __int128 *v94; // rax
  BOOLEAN v95; // bl
  char v96; // bl
  unsigned __int8 v97; // r8
  unsigned __int8 v98; // r8
  bool v99; // sf
  unsigned __int8 v100; // r8
  const wchar_t *v101; // rbx
  unsigned __int8 v102; // r8
  int v103; // eax
  unsigned __int8 v104; // r8
  _KerberosSystemRole *v105; // rcx
  unsigned int v106; // ecx
  struct _KERB_TICKET_CACHE_ENTRY *v107; // r10
  struct _KERB_TICKET_CACHE_ENTRY **v108; // rcx
  struct _KERB_TICKET_CACHE_ENTRY **v109; // rcx
  struct _KERB_INTERNAL_NAME *v110; // rbx
  __int64 v111; // rcx
  __int64 v112; // r8
  const char *v113; // r9
  int v114; // eax
  unsigned __int8 v115; // r8
  char v116; // r14
  const char *v117; // r9
  __int64 v118; // r8
  __int64 v119; // rcx
  int v120; // ebx
  struct _FIDO_CACHE_BLOB *v121; // rsi
  char *v122; // r9
  int v123; // r9d
  struct _UNICODE_STRING *v124; // r8
  struct _UNICODE_STRING *v125; // rdx
  __int128 v126; // xmm7
  __int128 v127; // xmm6
  int v128; // eax
  unsigned __int8 v129; // r8
  unsigned __int8 v130; // r8
  unsigned __int8 v131; // r8
  struct _KERB_LOGON_SESSION *v132; // rcx
  unsigned __int8 v133; // r8
  unsigned __int8 v134; // r8
  int v135; // eax
  const char *v136; // r9
  __int64 v137; // r8
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v138; // rcx
  USHORT v139; // ax
  unsigned __int8 v140; // r8
  unsigned int v141; // ebx
  _WORD *v142; // rcx
  unsigned __int8 v143; // r8
  unsigned __int8 v144; // r8
  struct _KERB_LOGON_SESSION *v145; // rdx
  const wchar_t *v146; // rcx
  int ClientDomain; // eax
  __int64 v148; // rax
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v149; // r8
  char *v150; // rdi
  char *v151; // rbx
  char *v152; // r11
  char *v153; // r10
  char *v154; // rdx
  unsigned __int8 v155; // r8
  char v156; // bl
  ULONG Flags; // eax
  int v158; // eax
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v159; // rcx
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v160; // rsi
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v161; // r8
  __int64 v162; // rcx
  LUID v163; // rax
  LUID v164; // rcx
  int updated; // eax
  __int64 v166; // rdx
  __int128 *v167; // rax
  struct _KERB_INTERACTIVE_PROFILE **v168; // rbx
  struct _KERB_INTERACTIVE_PROFILE *v169; // rdx
  int v170; // eax
  int *v171; // rsi
  void **v172; // rbx
  int v173; // ecx
  void *v174; // rax
  struct _UNICODE_STRING **v175; // r14
  unsigned __int8 v176; // r8
  int v177; // ebx
  const WCHAR *v178; // rax
  int v179; // eax
  PWSTR v180; // rax
  __int64 v181; // rcx
  _BYTE *v182; // rcx
  __int64 v183; // rax
  __int128 *v184; // rax
  size_t Size; // [rsp+28h] [rbp-110h]
  size_t Sizea; // [rsp+28h] [rbp-110h]
  size_t Sizeb; // [rsp+28h] [rbp-110h]
  size_t Sizec; // [rsp+28h] [rbp-110h]
  size_t Sized; // [rsp+28h] [rbp-110h]
  struct _KERB_INTERACTIVE_PROFILE **v191; // [rsp+38h] [rbp-100h]
  _SECURITY_LOGON_TYPE v192; // [rsp+B8h] [rbp-80h] BYREF
  char v193; // [rsp+BCh] [rbp-7Ch]
  PCCERT_CONTEXT pCertContext; // [rsp+C0h] [rbp-78h]
  char v195; // [rsp+C8h] [rbp-70h]
  struct _SECPKG_PRIMARY_CRED *v196; // [rsp+D0h] [rbp-68h]
  char v197; // [rsp+D8h] [rbp-60h]
  char v198; // [rsp+D9h] [rbp-5Fh]
  struct _KERB_LOGON_SESSION *v199; // [rsp+E0h] [rbp-58h] BYREF
  unsigned __int8 v200; // [rsp+E8h] [rbp-50h]
  unsigned __int8 v201[3]; // [rsp+E9h] [rbp-4Fh] BYREF
  int v202; // [rsp+ECh] [rbp-4Ch]
  char v203[8]; // [rsp+F0h] [rbp-48h] BYREF
  LUID LocallyUniqueId; // [rsp+F8h] [rbp-40h] BYREF
  struct _FIDO_CACHE_BLOB *v205; // [rsp+100h] [rbp-38h] BYREF
  __int128 v206; // [rsp+108h] [rbp-30h] BYREF
  void *Source1[2]; // [rsp+118h] [rbp-20h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO4 *v208; // [rsp+128h] [rbp-10h] BYREF
  struct _KERB_INTERACTIVE_LOGON *v209; // [rsp+130h] [rbp-8h] BYREF
  wchar_t *String2[2]; // [rsp+138h] [rbp+0h] BYREF
  UNICODE_STRING String1; // [rsp+148h] [rbp+10h] BYREF
  struct _UNICODE_STRING v212; // [rsp+158h] [rbp+20h] BYREF
  struct _CERT_CONTEXT *v213; // [rsp+168h] [rbp+30h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v214; // [rsp+170h] [rbp+38h] BYREF
  int v215; // [rsp+178h] [rbp+40h] BYREF
  int *v216; // [rsp+180h] [rbp+48h]
  PLUID SourceLuid[2]; // [rsp+188h] [rbp+50h] BYREF
  struct KerbCredIsoApi *v218; // [rsp+198h] [rbp+60h] BYREF
  __int64 v219; // [rsp+1A0h] [rbp+68h] BYREF
  struct _LUID v220; // [rsp+1A8h] [rbp+70h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v221; // [rsp+1B0h] [rbp+78h]
  struct _UNICODE_STRING v222; // [rsp+1B8h] [rbp+80h] BYREF
  void **v223; // [rsp+1C8h] [rbp+90h]
  struct _UNICODE_STRING v224; // [rsp+1D0h] [rbp+98h] BYREF
  unsigned int v225; // [rsp+1E0h] [rbp+A8h] BYREF
  struct _KERB_INTERACTIVE_PROFILE **v226; // [rsp+1E8h] [rbp+B0h]
  struct _KERB_TICKET_CACHE_ENTRY *v227; // [rsp+1F0h] [rbp+B8h] BYREF
  struct _UNICODE_STRING v228; // [rsp+1F8h] [rbp+C0h] BYREF
  __int128 v229; // [rsp+208h] [rbp+D0h] BYREF
  struct _KERB_INTERNAL_NAME *v230; // [rsp+218h] [rbp+E0h] BYREF
  __int128 v231; // [rsp+220h] [rbp+E8h] BYREF
  char v232[8]; // [rsp+230h] [rbp+F8h] BYREF
  unsigned int *v233; // [rsp+238h] [rbp+100h]
  enum _LSA_TOKEN_INFORMATION_TYPE *v234; // [rsp+240h] [rbp+108h]
  PSID pSid1; // [rsp+248h] [rbp+110h] BYREF
  UNICODE_STRING **v236; // [rsp+250h] [rbp+118h]
  struct _KERB_INTERNAL_NAME *v237; // [rsp+258h] [rbp+120h] BYREF
  struct _KERB_INTERNAL_NAME *v238; // [rsp+260h] [rbp+128h] BYREF
  struct _UNICODE_STRING v239; // [rsp+268h] [rbp+130h] BYREF
  _QWORD *v240; // [rsp+278h] [rbp+140h]
  struct _UNICODE_STRING v241; // [rsp+280h] [rbp+148h] BYREF
  __int128 v242; // [rsp+290h] [rbp+158h] BYREF
  __int128 v243; // [rsp+2A0h] [rbp+168h] BYREF
  struct _SECPKG_SURROGATE_LOGON *v244; // [rsp+2B0h] [rbp+178h]
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v245; // [rsp+2B8h] [rbp+180h] BYREF
  struct _LUID v246; // [rsp+2C0h] [rbp+188h] BYREF
  struct _UNICODE_STRING v247; // [rsp+2C8h] [rbp+190h] BYREF
  __int64 v248; // [rsp+2D8h] [rbp+1A0h] BYREF
  struct _UNICODE_STRING v249; // [rsp+2E0h] [rbp+1A8h] BYREF
  struct _UNICODE_STRING v250; // [rsp+2F0h] [rbp+1B8h] BYREF
  struct _UNICODE_STRING v251; // [rsp+300h] [rbp+1C8h] BYREF
  struct _UNICODE_STRING v252; // [rsp+310h] [rbp+1D8h] BYREF
  struct _UNICODE_STRING v253; // [rsp+320h] [rbp+1E8h] BYREF
  __int128 v254; // [rsp+330h] [rbp+1F8h] BYREF
  _OWORD v255[2]; // [rsp+340h] [rbp+208h] BYREF
  __int64 v256; // [rsp+360h] [rbp+228h]
  struct _UNICODE_STRING DestinationString; // [rsp+368h] [rbp+230h] BYREF
  __int128 v258; // [rsp+378h] [rbp+240h] BYREF
  __int64 v259; // [rsp+388h] [rbp+250h]
  int v260[4]; // [rsp+390h] [rbp+258h] BYREF
  __int128 v261; // [rsp+3A0h] [rbp+268h]
  __int64 v262; // [rsp+3B0h] [rbp+278h]
  __int128 v263; // [rsp+3B8h] [rbp+280h] BYREF
  struct _UNICODE_STRING v264[2]; // [rsp+3C8h] [rbp+290h] BYREF
  _DWORD Source2[4]; // [rsp+3E8h] [rbp+2B0h] BYREF
  struct _LUID v266[2]; // [rsp+3F8h] [rbp+2C0h] BYREF
  __int128 v267; // [rsp+408h] [rbp+2D0h] BYREF
  int v268; // [rsp+418h] [rbp+2E0h]
  int v269; // [rsp+41Ch] [rbp+2E4h]
  _WORD v270[2]; // [rsp+428h] [rbp+2F0h] BYREF
  char v271; // [rsp+42Ch] [rbp+2F4h]
  __int128 v272; // [rsp+440h] [rbp+308h]
  int v273; // [rsp+454h] [rbp+31Ch]
  int *v274; // [rsp+458h] [rbp+320h]
  int v275; // [rsp+460h] [rbp+328h]
  struct _UNICODE_STRING *v276; // [rsp+468h] [rbp+330h]
  int v277; // [rsp+470h] [rbp+338h]
  PWSTR Buffer; // [rsp+478h] [rbp+340h]
  int v279; // [rsp+480h] [rbp+348h]
  __int128 *v280; // [rsp+488h] [rbp+350h]
  int v281; // [rsp+490h] [rbp+358h]
  __int64 v282; // [rsp+498h] [rbp+360h]
  int v283; // [rsp+4A0h] [rbp+368h]
  __int128 *v284; // [rsp+4A8h] [rbp+370h]
  int v285; // [rsp+4B0h] [rbp+378h]
  __int64 v286; // [rsp+4B8h] [rbp+380h]
  int v287; // [rsp+4C0h] [rbp+388h]
  struct _GUID v288; // [rsp+4C8h] [rbp+390h] BYREF
  _DWORD v289[2]; // [rsp+4D8h] [rbp+3A0h] BYREF
  char *v290; // [rsp+4E0h] [rbp+3A8h]
  int v291; // [rsp+4E8h] [rbp+3B0h]
  struct _UNICODE_STRING *v292; // [rsp+4F0h] [rbp+3B8h]

  v19 = a3;
  v192 = a2;
  v22 = a6;
  v244 = a6;
  v226 = a8;
  v233 = a9;
  *(_QWORD *)&v229 = a10;
  v216 = a11;
  v234 = a12;
  v223 = a13;
  v240 = a14;
  v236 = a15;
  *(_QWORD *)&v231 = a16;
  v23 = a17;
  v196 = a17;
  v221 = a18;
  KerbTracerT::KerbTracerT((KerbTracerT *)v232, "Logon User", (unsigned int)a3);
  v199 = 0;
  v24 = 0;
  v206 = (unsigned __int64)LocalhostKerbCredIsoObj::IsoObj;
  *(_OWORD *)Source1 = 0;
  v228 = 0;
  String2[0] = 0;
  String2[1] = 0;
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = 0;
  *(_QWORD *)&v241.Length = 0;
  v241.Buffer = 0;
  LocallyUniqueId = 0;
  v220 = 0;
  v246 = 0;
  v214 = 0;
  v227 = 0;
  v254 = 0;
  memset(v255, 0, sizeof(v255));
  v256 = 0;
  v252 = 0;
  v230 = 0;
  v251 = 0;
  v224 = 0;
  v237 = 0;
  v238 = 0;
  v253 = 0;
  v263 = 0;
  v219 = 0;
  DestinationString = 0;
  v225 = 0;
  pCertContext = 0;
  v213 = 0;
  v209 = v19;
  v208 = 0;
  v288 = 0;
  v239 = 0;
  v212 = 0;
  v248 = 0;
  v245 = 0;
  v200 = 0;
  v201[0] = 0;
  Source2[0] = -1027713961;
  Source2[1] = 1212056299;
  Source2[2] = 1752452782;
  Source2[3] = 164959471;
  pSid1 = 0;
  v218 = 0;
  *(_OWORD *)v260 = 0;
  v261 = 0;
  v262 = 0;
  v203[0] = 0;
  v215 = 0;
  v249 = 0;
  v250 = 0;
  v242 = (unsigned __int64)LocalhostKerbCredIsoObj::IsoObj;
  v243 = 0;
  v202 = 0;
  memset_0(v270, 0, 0xA0u);
  *(_QWORD *)&v247.Length = 0;
  v247.Buffer = 0;
  if ( KerbEventTraceFlag )
  {
    v272 = KerbLogonGuid;
    v271 = 1;
    v273 = 0x20000;
    v270[0] = 48;
    EtwLogTraceEvent(KerbTraceLoggerHandle, v270);
  }
  *v226 = 0;
  *v216 = 0;
  *v223 = 0;
  *v240 = 0;
  *v236 = 0;
  *(_QWORD *)v231 = 0;
  *v221 = 0;
  v249.Buffer = 0;
  v250.Buffer = 0;
  memset_0(v23, 0, 0xE0u);
  if ( !KerbGlobalInitialized )
  {
    TicketGrantingTicket = -1073741604;
LABEL_5:
    LOWORD(v26) = v192;
LABEL_6:
    v27 = 32;
LABEL_7:
    v28 = pCertContext;
    goto LABEL_8;
  }
  v33 = MIDL_user_allocate(0x10u);
  *v240 = v33;
  if ( !v33 || (v33[1] = 0, v34 = (UNICODE_STRING *)MIDL_user_allocate(0x10u), (*v236 = v34) == 0) )
  {
    TicketGrantingTicket = -1073741670;
    goto LABEL_5;
  }
  v34->Buffer = 0;
  LocallyUniqueId = 0;
  *(_QWORD *)v229 = 0;
  if ( a2 != Interactive
    && a2 != Network
    && a2 != Batch
    && a2 != Service
    && a2 != NetworkCleartext
    && (unsigned int)(a2 - 10) >= 2 )
  {
    TicketGrantingTicket = -1073741557;
    LOWORD(v26) = v192;
    KerbTracerT::Log(1, "KerbILogonUserEx3", 11240, "Invalid logon type passed to LsaApLogonUserEx3: %d", v192);
    goto LABEL_6;
  }
  v24 = (unsigned __int16 *)v209;
  if ( a5 < 4 )
  {
    TicketGrantingTicket = -1073741811;
    goto LABEL_5;
  }
  v197 = 0;
  LODWORD(v205) = 0;
  AsRepCred = 0;
  if ( v209->MessageType != 513 )
  {
    v258 = 0;
    v259 = 0;
    if ( !((unsigned __int8 (__fastcall *)(__int128 *, __int64, _QWORD))LsaFunctions->GetCallInfo)(&v258, v35, 0) )
    {
      TicketGrantingTicket = -1073741595;
      goto LABEL_36;
    }
    if ( (BYTE8(v258) & 0x40) != 0 && a7 == 1 )
    {
      TicketGrantingTicket = KerbConvertWOWLogonBuffer(v19, (void *)a4, &a5, v209->MessageType, (void **)&v209);
      if ( TicketGrantingTicket < 0 )
        goto LABEL_36;
      v202 = 1;
      v44 = v209;
      v19 = v209;
      v24 = (unsigned __int16 *)v209;
      v195 = 0;
      v193 = 0;
      v47 = 0;
      LOBYTE(SourceLuid[0]) = 0;
      LOBYTE(v43) = 0;
      v198 = 0;
      goto LABEL_74;
    }
    v44 = v209;
LABEL_85:
    v195 = 0;
    v193 = 0;
    v47 = 0;
    LOBYTE(SourceLuid[0]) = 0;
    LOBYTE(v43) = 0;
    v198 = 0;
    if ( AsRepCred )
    {
      v49 = a5;
      v48 = (int)v205;
      goto LABEL_87;
    }
LABEL_74:
    v49 = a5;
    goto LABEL_75;
  }
  if ( a5 < 0x30 )
  {
    LODWORD(Size) = a5;
    v37 = 10112;
LABEL_34:
    KerbTracerT::Log(1, "KerbILogonUserEx3", v37, "Submit buffer to logon too small: %d", Size);
LABEL_35:
    TicketGrantingTicket = -1073741811;
LABEL_36:
    v23 = v196;
    goto LABEL_5;
  }
  v38 = *(unsigned int *)(&v209->UserName.MaximumLength + 1);
  if ( a5 <= (unsigned int)v38 || a5 - (unsigned int)v38 < 0x1C )
  {
    KerbTracerT::Log(
      1,
      "KerbILogonUserEx3",
      10121,
      "Out of bounds read attempted using submit buffer.                                         Size: %d, Ex2PackedCrede"
      "ntialsOffset: %d.",
      a5,
      v38);
    goto LABEL_35;
  }
  v39 = (char *)v209 + v38;
  if ( SEC_WINNT_AUTH_DATA_TYPE_NGC == *(_OWORD *)((char *)&v209->MessageType + v38 + 4) )
  {
    SourceLuid[0] = 0;
    TicketGrantingTicket = KerbConvertEx2ToNgcData(v209, a5, (void **)SourceLuid, (unsigned int *)&v222.Length);
    if ( TicketGrantingTicket < 0 )
      goto LABEL_36;
    v40 = SourceLuid[0];
    if ( (SourceLuid[0][1].LowPart & 8) != 0 )
    {
      AsRepCred = KerbFindAsRepCred(v244);
      KerbTracerT::Log(3, "KerbILogonUserEx3", 10153, "NGC CloudTrust is enabled");
      LODWORD(v205) = 2;
      v212.MaximumLength = a5;
    }
    else
    {
      KerbTracerT::Log(
        3,
        "KerbILogonUserEx3",
        10161,
        "NGC CloudTrust is NOT enabled. LogonType(0x%x), isNgcDataCloudTrustFlagSet(%d), isKerbAsRepCredNull(%d)",
        v192,
        0,
        1);
    }
    v264[0] = 0;
    *(_OWORD *)SourceLuid = 0;
    v222 = 0;
    v222.MaximumLength = (USHORT)v209->LogonDomainName.Buffer;
    v222.Length = v222.MaximumLength;
    if ( v222.MaximumLength )
      v222.Buffer = (PWSTR)((char *)v209 + *(unsigned int *)(&v209->LogonDomainName.MaximumLength + 1));
    WORD1(SourceLuid[0]) = v209->UserName.Length;
    LOWORD(SourceLuid[0]) = WORD1(SourceLuid[0]);
    if ( WORD1(SourceLuid[0]) )
      SourceLuid[1] = (PLUID)((char *)v209 + HIDWORD(v209->LogonDomainName.Buffer));
    v41 = (unsigned __int8 *)v40 + (unsigned int)v40[1].HighPart;
    LowPart_low = LOWORD(v40[2].LowPart);
    v264[0].MaximumLength = v40[3].LowPart;
    v264[0].Length = v264[0].MaximumLength;
    if ( v264[0].MaximumLength )
      v264[0].Buffer = (PWSTR)((char *)v40 + (unsigned int)v40[2].HighPart);
    LODWORD(Size) = LowPart_low;
    TicketGrantingTicket = KerbCreateCertLogonBuffer(
                             v264,
                             (struct _UNICODE_STRING *)SourceLuid,
                             &v222,
                             v41,
                             Size,
                             v40[1].LowPart,
                             (void **)&v209,
                             &a5);
    if ( TicketGrantingTicket < 0 )
      goto LABEL_36;
    if ( *v40 )
    {
      v209->MessageType = KerbCertificateUnlockLogon;
      RtlCopyLuid((PLUID)&v209[1].LogonDomainName.Buffer, v40);
    }
    v202 = 1;
    v197 = 1;
    v212.Buffer = (PWSTR)v39;
    v212.MaximumLength = v24[16];
    v212.Length = v212.MaximumLength;
    v44 = v209;
    v19 = v209;
    v24 = (unsigned __int16 *)v209;
    goto LABEL_85;
  }
  if ( SEC_WINNT_AUTH_DATA_TYPE_FIDO != *(_QWORD *)(v39 + 4) || *(_QWORD *)(v39 + 12) != 0x5C13C6660F46C583LL )
  {
    if ( SEC_WINNT_AUTH_DATA_TYPE_DELEGATION_TOKEN != *(_QWORD *)(v39 + 4)
      || *(_QWORD *)(v39 + 12) != 0x6762222BE49D2090LL )
    {
      TicketGrantingTicket = -1073741821;
      KerbTracerT::Log(1, "KerbILogonUserEx3", 10267, "Unrecognized EX2 credential type is passed to LsaApLogonUserEx3");
      goto LABEL_36;
    }
    AsRepCred = KerbFindAsRepCred(v22);
    if ( !AsRepCred )
    {
      TicketGrantingTicket = -2146893039;
      KerbTracerT::Log(
        1,
        "KerbILogonUserEx3",
        10256,
        "No SECPKG_SURROGATE_LOGON_ENTRY_AS_REP_CREDENTIAL surrogate entry for LsaApLogonUserEx3");
      goto LABEL_36;
    }
    v48 = 3;
    LODWORD(v205) = 3;
    v212.Buffer = (PWSTR)v19;
    v49 = a5;
    v212.MaximumLength = a5;
    v212.Length = a5;
    v195 = 0;
    v193 = 0;
    v47 = 0;
    LOBYTE(SourceLuid[0]) = 0;
    LOBYTE(v43) = 0;
    v198 = 0;
    v44 = v209;
LABEL_87:
    if ( v48 != 2 )
    {
      v45 = v193;
      v46 = (int)v205;
      goto LABEL_89;
    }
LABEL_75:
    v50 = *(_DWORD *)v24;
    if ( *(_DWORD *)v24 != 2 && v50 != 7 )
    {
      switch ( v50 )
      {
        case 6:
          goto LABEL_138;
        case 8:
          v57 = v202;
          if ( (unsigned int)v49 < 0x30 )
          {
            LODWORD(Size) = v49;
            v37 = 11008;
            goto LABEL_34;
          }
          v58 = (struct _LUID)*((_QWORD *)v24 + 5);
          goto LABEL_137;
        case 13:
LABEL_138:
          v26 = v192;
          v54 = KerbCreateSmartCardLogonSession(
                  v44,
                  (void *)a4,
                  v49,
                  v192,
                  v43,
                  v197,
                  &v199,
                  &LocallyUniqueId,
                  (struct _UNICODE_STRING *)String2,
                  &String1,
                  &v228);
          TicketGrantingTicket = v54;
          if ( v54 < 0 )
          {
            v55 = "KerbCreateSmartCardLogonSession failed %x\n";
            v56 = 11069;
            goto LABEL_108;
          }
          v46 = (int)v205;
          if ( (_DWORD)v205 == 2 )
          {
            if ( AsRepCred )
            {
              *((_QWORD *)v199 + 90) = *((_QWORD *)AsRepCred + 10);
              *((_QWORD *)v199 + 91) = *((_QWORD *)AsRepCred + 11);
              *((_DWORD *)v199 + 132) &= ~8u;
            }
            else
            {
              KerbTracerT::Log(
                1,
                "KerbILogonUserEx3",
                11083,
                "AsRepCred is expected to be always present for CloudTrust logons");
              MicrosoftTelemetryAssertTriggeredNoArgs();
            }
            *((_DWORD *)v199 + 233) = 2;
          }
          if ( !String1.Length && (!String2[1] || wcsncmp_0(L"@@@", String2[1], 3u)) )
          {
            TicketGrantingTicket = KerbDuplicateStringEx(&v224, (const struct _UNICODE_STRING *)String2, v59);
            if ( TicketGrantingTicket < 0 )
              goto LABEL_109;
            KerbTracerT::Log(3, "KerbILogonUserEx3", 11106, "UPN logon %wZ\n", &v224);
          }
LABEL_312:
          v45 = v193;
          goto LABEL_313;
      }
      if ( v50 != 15 )
      {
        if ( (unsigned int)(v50 - 10) <= 1 )
        {
          v26 = v192;
          if ( v192 == CachedInteractive )
            goto LABEL_96;
          if ( v50 == 11 )
          {
            if ( (unsigned int)v49 < 0x28 )
            {
              KerbTracerT::Log(1, "KerbILogonUserEx3", 11126, "Submit buffer to logon too small: %d", v49);
              goto LABEL_101;
            }
            v220 = (struct _LUID)*((_QWORD *)v24 + 4);
            v195 = 1;
          }
          TicketGrantingTicket = KerbCreateTicketLogonSession(
                                   v44,
                                   (void *)a4,
                                   v49,
                                   UndefinedLogonType,
                                   &v199,
                                   &LocallyUniqueId,
                                   &v214,
                                   (struct _KERB_MESSAGE_BUFFER *)&v254,
                                   v201);
          if ( TicketGrantingTicket < 0 )
          {
LABEL_109:
            v23 = v196;
            goto LABEL_6;
          }
          v200 = v201[0];
          if ( v201[0] )
          {
            KerbTracerT::Log(
              1,
              "KerbILogonUserEx3",
              11154,
              "Redirected logon flag set on ticket logon, but no redirected logon info provided");
            TicketGrantingTicket = -1073741811;
            goto LABEL_109;
          }
        }
        else
        {
          if ( ((v50 - 12) & 0xFFFFFFFD) != 0 )
          {
            KerbTracerT::Log(3, "KerbILogonUserEx3", 11227, "Invalid info class to logon: %d", v50);
            TicketGrantingTicket = -1073741821;
            goto LABEL_36;
          }
          v26 = v192;
          if ( v192 == CachedInteractive )
            goto LABEL_96;
          if ( v50 == 12 )
          {
            if ( (unsigned int)v49 < 0x28 )
            {
              KerbTracerT::Log(1, "KerbILogonUserEx3", 11184, "Submit buffer to logon too small: %d", v49);
LABEL_101:
              TicketGrantingTicket = -1073741811;
              goto LABEL_97;
            }
          }
          else if ( (unsigned int)v49 < 0x38 )
          {
            KerbTracerT::Log(1, "KerbILogonUserEx3", 11193, "Submit buffer to logon too small: %d", v49);
            goto LABEL_101;
          }
          if ( (unsigned int)(v192 - 3) > 1 )
          {
            KerbTracerT::Log(
              1,
              "KerbILogonUserEx3",
              11201,
              "LogonType %d must be network or batch for S4ULogon\n",
              v192);
LABEL_96:
            TicketGrantingTicket = -1073741557;
LABEL_97:
            v23 = v196;
            goto LABEL_6;
          }
          v54 = KerbS4UToSelfLogon(v44, (void *)a4, v49, &v199, &LocallyUniqueId, &v214, &v238, &v253, &v246);
          TicketGrantingTicket = v54;
          if ( v54 < 0 )
          {
            v55 = "KerbS4UToSelfLogon failed - %x\n";
            v56 = 11220;
LABEL_108:
            LODWORD(Sizea) = v54;
            KerbTracerT::Log(1, "KerbILogonUserEx3", v56, v55, Sizea);
            goto LABEL_109;
          }
          v288 = *(struct _GUID *)((char *)v214 + 408);
        }
        goto LABEL_311;
      }
      v57 = v202;
      if ( (unsigned int)v49 < 0x50 )
      {
        LODWORD(Size) = v49;
        KerbTracerT::Log(1, "KerbILogonUserEx3", 11021, "Submit buffer to certficate logon too small: %d", Size);
        goto LABEL_35;
      }
      v198 = 0;
      if ( *((_DWORD *)v24 + 18) == 999 )
      {
        if ( *((_DWORD *)v24 + 19) )
        {
LABEL_133:
          v58 = (struct _LUID)*((_QWORD *)v24 + 9);
LABEL_137:
          v202 = v57;
          v195 = 1;
          v220 = v58;
          goto LABEL_138;
        }
      }
      else if ( *((_DWORD *)v24 + 18) != 996 || *((_DWORD *)v24 + 19) )
      {
LABEL_132:
        v198 = v43;
        goto LABEL_133;
      }
      memset(v264, 0, sizeof(v264));
      TicketGrantingTicket = ((__int64 (__fastcall *)(struct _UNICODE_STRING *, __int64, __int64, _QWORD))LsaFunctions->GetClientInfo)(
                               v264,
                               v43,
                               v49,
                               0);
      if ( TicketGrantingTicket < 0 )
        goto LABEL_36;
      if ( *((_QWORD *)v24 + 9) != *(_QWORD *)&v264[0].Length && !LOBYTE(v264[1].Length) )
      {
        TicketGrantingTicket = -1073741727;
        goto LABEL_36;
      }
      LOBYTE(v43) = 1;
      LODWORD(v49) = a5;
      v44 = v209;
      goto LABEL_132;
    }
    if ( v192 == CachedInteractive )
    {
      TicketGrantingTicket = -1073741557;
      goto LABEL_36;
    }
    if ( v50 == 2 )
    {
      if ( (unsigned int)v49 < 0x38 )
      {
        LODWORD(Size) = v49;
        v37 = 10375;
        goto LABEL_34;
      }
    }
    else
    {
      if ( (unsigned int)v49 < 0x40 )
      {
        LODWORD(Size) = v49;
        v37 = 10384;
        goto LABEL_34;
      }
      v220 = (struct _LUID)*((_QWORD *)v24 + 7);
      v195 = 1;
    }
    v51 = KerbUnpackLogonInfoPassword(
            v19,
            (void *)a4,
            v49,
            (struct _KERB_INTERACTIVE_LOGON *)v24,
            (struct _KERB_PLAINTEXT_PASSWORD *)&v206);
    TicketGrantingTicket = v51;
    if ( v51 < 0 )
    {
      v52 = "Failed to unpack password from LogonInfo: 0x%x";
      v53 = 10403;
      goto LABEL_91;
    }
    if ( LOWORD(Source1[0]) >= 0x10u && RtlCompareMemory(Source1[1], Source2, 0x10u) == 16 )
    {
      v213 = 0;
      LODWORD(SourceLuid[0]) = 0;
      *(_DWORD *)&v222.Length = 0;
      if ( !(unsigned __int8)LsaIAllowProtectedCredLogon() )
      {
        TicketGrantingTicket = -1073741714;
        goto LABEL_36;
      }
      if ( DWORD2(v206) == 1 )
      {
        v60 = Source1[1];
        if ( Source1[1] )
        {
          v61 = LODWORD(Source1[0]);
          if ( LODWORD(Source1[0]) )
          {
            do
            {
              *v60++ = 0;
              --v61;
            }
            while ( v61 );
          }
          ((void (*)(void))KerbFree)();
        }
      }
      else
      {
        KerbSecureFreeString(Source1);
      }
      v27 = 32;
      v62 = 32;
      v63 = &v206;
      do
      {
        *(_BYTE *)v63 = 0;
        v63 = (__int128 *)((char *)v63 + 1);
        --v62;
      }
      while ( v62 );
      v264[0] = (struct _UNICODE_STRING)(unsigned __int64)LocalhostKerbCredIsoObj::IsoObj;
      v206 = (unsigned __int64)LocalhostKerbCredIsoObj::IsoObj;
      *(_OWORD *)Source1 = 0;
      v64 = (WCHAR *)MIDL_user_allocate(v24[20] + 2LL);
      v65 = v64;
      if ( !v64 )
      {
        TicketGrantingTicket = -1073741670;
LABEL_174:
        v23 = v196;
        LOWORD(v26) = v192;
        goto LABEL_7;
      }
      memcpy_0(v64, *((const void **)v24 + 6), v24[20]);
      TicketGrantingTicket = KerbDecodeSecretEx(
                               v65,
                               0,
                               0,
                               (struct _UNICODE_STRING *)Source1,
                               0,
                               (enum _CRED_PROTECTION_TYPE *)SourceLuid);
      KerbFree(v65);
      if ( TicketGrantingTicket < 0 )
        goto LABEL_174;
      if ( LODWORD(SourceLuid[0]) != 2 )
      {
        TicketGrantingTicket = -1073741595;
        goto LABEL_174;
      }
      if ( LOWORD(Source1[0]) < 0x48u )
      {
        KerbTracerT::Log(1, "KerbILogonUserEx3", 10477, "Redirected logon buffer too small: %d", LOWORD(Source1[0]));
        TicketGrantingTicket = -1073741811;
        goto LABEL_174;
      }
      v66 = (struct _SECPKG_REDIRECTED_LOGON_BUFFER *)Source1[1];
      if ( (int)KerbValidateRedirectedLogonBuffer((struct _SECPKG_REDIRECTED_LOGON_BUFFER *)Source1[1]) < 0 )
        goto LABEL_174;
      v67 = ((__int64 (__fastcall *)(HANDLE, struct _CERT_CONTEXT **, struct _UNICODE_STRING *))v66->GetLogonCreds)(
              v66->RedirectedLogonHandle,
              &v213,
              &v222);
      if ( v67 < 0 )
      {
        v68 = "Failed to retrieve ticket logon buffer using redirected logon info: 0x%x";
        v69 = 10498;
LABEL_183:
        LODWORD(Sizeb) = v67;
        KerbTracerT::Log(1, "KerbILogonUserEx3", v69, v68, Sizeb);
        goto LABEL_174;
      }
      if ( *(_DWORD *)&v222.Length < 0x20u )
      {
        v67 = a5;
        v68 = "Password-marshalled Ticket logon buffer too small: %d";
        v69 = 10504;
        goto LABEL_183;
      }
      if ( v213->dwCertEncodingType != 10 )
      {
        LODWORD(Sizeb) = v213->dwCertEncodingType;
        KerbTracerT::Log(
          1,
          "KerbILogonUserEx3",
          10511,
          "Password-marshalled Ticket logon buffer wasn't a ticket logon buffer: %d",
          Sizeb);
        goto LABEL_174;
      }
      KerbTracerT::Log(3, "KerbILogonUserEx3", 10516, "Creating redirected ticket logon session\n");
      if ( (int)KerbCreateTicketLogonSession(
                  v213,
                  0,
                  *(unsigned int *)&v222.Length,
                  v70,
                  &v199,
                  &LocallyUniqueId,
                  &v214,
                  (struct _KERB_MESSAGE_BUFFER *)&v254,
                  v201) < 0 )
        goto LABEL_174;
      v200 = v201[0];
      if ( !v201[0] )
      {
        KerbTracerT::Log(
          1,
          "KerbILogonUserEx3",
          10536,
          "Redirected logon buffer provided but ticket logon buffer wasn't redirected");
        goto LABEL_174;
      }
      inited = KerbInitRedirectedLogon(a1, &LocallyUniqueId, v66, &v218);
      if ( inited < 0 )
      {
        v72 = "Failed to init redirected logon: %#x";
        v73 = 10549;
LABEL_193:
        LODWORD(Sizec) = inited;
        KerbTracerT::Log(1, "KerbILogonUserEx3", v73, v72, Sizec);
LABEL_194:
        v23 = v196;
        LOWORD(v26) = v192;
        goto LABEL_7;
      }
      GetSupplementalCreds = (__int64 (__fastcall *)(HANDLE, __int64 *))v66->GetSupplementalCreds;
      if ( GetSupplementalCreds )
      {
        inited = GetSupplementalCreds(v66->RedirectedLogonHandle, &v248);
        if ( inited < 0 )
        {
          v72 = "Failed to fetch supplemental credentials: %#x\n";
          v73 = 10561;
          goto LABEL_193;
        }
      }
      v75 = *(__int64 (__fastcall **)(HANDLE, PSID *))&v66[1].RedirectedLogonGuid.Data1;
      if ( v75 )
      {
        inited = v75(v66->RedirectedLogonHandle, &pSid1);
        if ( inited < 0 )
        {
          v72 = "Failed to get the redirected logon SID: %#x\n";
          v73 = 10572;
          goto LABEL_193;
        }
      }
      v24 = (unsigned __int16 *)v213;
      goto LABEL_202;
    }
    *(_OWORD *)(v24 + 20) = 0;
    v76 = v192;
    if ( v192 != Service )
      goto LABEL_224;
    memset(v264, 0, 24);
    RtlInitUnicodeString(&DestinationString, L"_SC_");
    if ( !RtlPrefixUnicodeString(&DestinationString, (PCUNICODE_STRING)Source1, 1u)
      || !((unsigned __int8 (__fastcall *)(struct _UNICODE_STRING *))LsaFunctions->GetCallInfo)(v264)
      || ((__int64)v264[0].Buffer & 0x200) == 0 )
    {
      goto LABEL_224;
    }
    *(_QWORD *)&v222.Length = 0;
    TicketGrantingTicket = LsarOpenSecret(KerbGlobalPolicyHandle, Source1, (unsigned int)(v192 - 3), &v222);
    if ( TicketGrantingTicket >= 0 )
    {
      TicketGrantingTicket = LsarQuerySecret(*(_QWORD *)&v222.Length, &v219, 0, 0, 0);
      if ( TicketGrantingTicket < 0 || (v77 = (_WORD *)v219) == 0 )
      {
LABEL_222:
        LsarClose(&v222);
        if ( TicketGrantingTicket < 0 )
          goto LABEL_58;
        v76 = v192;
LABEL_224:
        v83 = (struct _UNICODE_STRING *)(v24 + 12);
        v84 = *((_QWORD *)v24 + 4);
        if ( v84 >= a4 )
          v84 -= a4;
        if ( !v84 )
          goto LABEL_35;
        if ( v84 > a5 )
          goto LABEL_35;
        Length = v83->Length;
        if ( v84 + Length > a5 )
          goto LABEL_35;
        if ( v84 < 0x38 )
          goto LABEL_35;
        if ( (v84 & 1) != 0 )
          goto LABEL_35;
        *((_QWORD *)v24 + 4) = (char *)v19 + v84;
        v24[13] = Length;
        if ( (Length & 1) != 0 )
          goto LABEL_35;
        v86 = (struct _UNICODE_STRING *)(v24 + 4);
        v87 = *((_QWORD *)v24 + 2);
        v88 = v24[4];
        if ( v87 )
        {
          if ( (_WORD)v88 )
          {
            if ( v87 >= a4 )
            {
              v87 -= a4;
              if ( !v87 )
                goto LABEL_35;
            }
            if ( v87 > a5 )
              goto LABEL_35;
            if ( v87 + v88 > a5 )
              goto LABEL_35;
            if ( v87 < 0x38 )
              goto LABEL_35;
            if ( (v87 & 1) != 0 )
              goto LABEL_35;
            *((_QWORD *)v24 + 2) = (char *)v19 + v87;
            v24[5] = v88;
            if ( (v88 & 1) != 0 )
              goto LABEL_35;
          }
          else
          {
            *((_QWORD *)v24 + 2) = 0;
          }
        }
        else if ( (_WORD)v88 )
        {
          goto LABEL_35;
        }
        if ( (unsigned __int16)Length > 0x200u || LOWORD(Source1[0]) > 0x200u )
        {
          KerbTracerT::Log(1, "KerbILogonUserEx3", 10662, "LsaApLogonUserEx2: Name or password too long.");
          TicketGrantingTicket = -1073741562;
          goto LABEL_36;
        }
        if ( (unsigned __int16)v88 > 2u || LOWORD(Source1[0]) > 2u )
          goto LABEL_261;
        *(_OWORD *)&v266[0].LowPart = 0;
        v267 = 0;
        TicketGrantingTicket = ((__int64 (__fastcall *)(struct _LUID *))LsaFunctions->GetClientInfo)(v266);
        if ( TicketGrantingTicket < 0 )
          goto LABEL_36;
        v76 = v192;
        if ( (unsigned int)KerbProcessUserNameCredential(
                             v266,
                             (struct _UNICODE_STRING *)(v24 + 12),
                             v192,
                             &v249,
                             &v250,
                             (struct _KERB_PLAINTEXT_PASSWORD *)&v242) )
        {
LABEL_261:
          v27 = 32;
        }
        else
        {
          KerbTracerT::Log(2, "KerbILogonUserEx3", 10692, "Using CredMan creds");
          *v83 = v249;
          *v86 = v250;
          if ( DWORD2(v206) == 1 )
          {
            v89 = Source1[1];
            if ( Source1[1] )
            {
              v90 = LODWORD(Source1[0]);
              if ( LODWORD(Source1[0]) )
              {
                do
                {
                  *v89++ = 0;
                  --v90;
                }
                while ( v90 );
              }
              ((void (*)(void))KerbFree)();
            }
          }
          else
          {
            KerbSecureFreeString(Source1);
          }
          v27 = 32;
          v91 = 32;
          v92 = &v206;
          do
          {
            *(_BYTE *)v92 = 0;
            v92 = (__int128 *)((char *)v92 + 1);
            --v91;
          }
          while ( v91 );
          v206 = v242;
          *(_OWORD *)Source1 = v243;
          v93 = 32;
          v94 = &v242;
          do
          {
            *(_BYTE *)v94 = 0;
            v94 = (__int128 *)((char *)v94 + 1);
            --v93;
          }
          while ( v93 );
        }
        KerbTracerT::Log(3, "KerbILogonUserEx3", 10712, "Logging on user %wZ, domain %wZ\n", v24 + 12, v24 + 4);
        RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
        v95 = RtlEqualUnicodeString(&KerbGlobalMachineName, (PCUNICODE_STRING)(v24 + 4), 1u);
        RtlReleaseResource(&KerberosGlobalResource);
        if ( v95 )
          goto LABEL_499;
        if ( BYTE1(KerbGlobalRoles) || ((v76 - 2) & 0xFFFFFFF7) != 0 )
        {
          v96 = v193;
        }
        else
        {
          KerbTracerT::Log(2, "KerbILogonUserEx3", 10732, "Mapping user to MIT principal on realmless workstation\n");
          v96 = 1;
          v193 = 1;
          if ( (int)KerbProcessTargetNames((const struct _UNICODE_STRING *)(v24 + 12), 0, 0, 0, 0, &v225, &v230, &v251) >= 0 )
            KerbMapClientName(&v241, v230, &v251);
        }
        if ( KerbGlobalDomainIsPreNT5 && !v96 || KerbGlobalSafeModeBootOptionPresent )
        {
LABEL_499:
          KerbTracerT::Log(3, "KerbILogonUserEx3", 10761, "Local Logon, bailing out now\n");
          TicketGrantingTicket = -1073741730;
          goto LABEL_174;
        }
        if ( _KerberosSystemRole::IsAnyKdc(0) && v86->Length == 2 && **((_WORD **)v24 + 2) == 46 )
        {
          RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
          TicketGrantingTicket = KerbDuplicateStringEx(&String1, &KerbGlobalDnsDomainName, v98);
          RtlReleaseResource(&KerberosGlobalResource);
          v99 = TicketGrantingTicket < 0;
        }
        else
        {
          if ( !*((_QWORD *)v24 + 2) )
            goto LABEL_278;
          TicketGrantingTicket = KerbDuplicateStringEx(&String1, (const struct _UNICODE_STRING *)(v24 + 4), v97);
          v99 = TicketGrantingTicket < 0;
        }
        if ( v99 )
          goto LABEL_174;
LABEL_278:
        TicketGrantingTicket = KerbCheckUserNameForCert(
                                 0,
                                 1u,
                                 (struct _UNICODE_STRING *)(v24 + 12),
                                 &String1,
                                 (const struct _CERT_CONTEXT **)&v213);
        if ( TicketGrantingTicket < 0 )
          goto LABEL_497;
        v28 = v213;
        pCertContext = v213;
        if ( v213 )
        {
          v47 = 1;
        }
        else
        {
          TicketGrantingTicket = KerbDuplicateStringEx(
                                   (struct _UNICODE_STRING *)String2,
                                   (const struct _UNICODE_STRING *)(v24 + 12),
                                   v100);
          if ( TicketGrantingTicket < 0 )
          {
LABEL_498:
            v23 = v196;
LABEL_390:
            LOWORD(v26) = v192;
            goto LABEL_8;
          }
          v47 = (char)SourceLuid[0];
        }
        inited = NtAllocateLocallyUniqueId(&LocallyUniqueId);
        TicketGrantingTicket = inited;
        if ( inited < 0 )
        {
          v72 = "Failed to allocate locally unique ID: 0x%x";
          v73 = 10846;
          goto LABEL_193;
        }
        if ( v47 )
        {
          v264[0] = String1;
          String1 = 0;
          TicketGrantingTicket = KerbParseHintsFromDomainName(v264, (struct _UNICODE_STRING *)String2, &String1);
          KerbFreeString(v264);
          if ( TicketGrantingTicket < 0 )
            goto LABEL_194;
          if ( DWORD2(v206) )
          {
            TicketGrantingTicket = -1073741595;
            goto LABEL_194;
          }
          TicketGrantingTicket = KerbCreateSmartCardLogonSessionFromCertContextEx(
                                   (const struct _CERT_CONTEXT **)&v213,
                                   &LocallyUniqueId,
                                   &String1,
                                   (struct _UNICODE_STRING *)Source1,
                                   0,
                                   0,
                                   0,
                                   v197 != 0 ? 0x3000000 : 0,
                                   &v199,
                                   (struct _UNICODE_STRING *)String2,
                                   0);
          if ( TicketGrantingTicket >= 0 )
          {
            if ( !LOWORD(String2[0])
              || (v101 = String2[1]) == 0
              || !wcsncmp_0(L"@@@", String2[1], 3u)
              || !wcschr(v101, 0x40u) )
            {
LABEL_296:
              TicketGrantingTicket = KerbDuplicatePassword(&v228, (const struct _UNICODE_STRING *)Source1);
              if ( TicketGrantingTicket >= 0 )
              {
                pCertContext = v213;
LABEL_202:
                v26 = v192;
LABEL_311:
                v46 = (int)v205;
                goto LABEL_312;
              }
              goto LABEL_497;
            }
            TicketGrantingTicket = KerbDuplicateStringEx(&v224, (const struct _UNICODE_STRING *)String2, v102);
            if ( TicketGrantingTicket >= 0 )
            {
              KerbTracerT::Log(3, "KerbILogonUserEx3", 10916, "UPN logon %wZ\n", &v224);
              goto LABEL_296;
            }
          }
LABEL_497:
          v28 = v213;
          goto LABEL_498;
        }
        if ( KerbGmsaIsManagedPassword((struct _KERB_PLAINTEXT_PASSWORD *)&v206)
          || KerbDmsaIsManagedPassword((struct _KERB_PLAINTEXT_PASSWORD *)&v206) )
        {
          v26 = v192;
          if ( (unsigned int)(v192 - 4) > 1 )
          {
            TicketGrantingTicket = -1073741715;
            KerbTracerT::Log(
              1,
              "KerbILogonUserEx3",
              10936,
              "logon type is neither service nor batch for managed credential: %#x\n",
              -1073741715);
            goto LABEL_302;
          }
          v103 = KerbManagedAccountAccessCheck();
          if ( v103 < 0 )
          {
            TicketGrantingTicket = -1073741715;
            KerbTracerT::Log(
              1,
              "KerbILogonUserEx3",
              10945,
              "the caller failed access check %#x to create the managed primary credential: %#x\n",
              v103,
              -1073741715);
            goto LABEL_302;
          }
        }
        else
        {
          v26 = v192;
        }
        TicketGrantingTicket = KerbCreateLogonSession(
                                 &LocallyUniqueId,
                                 (struct _UNICODE_STRING *)String2,
                                 &String1,
                                 (struct _KERB_PLAINTEXT_PASSWORD *)&v206,
                                 0,
                                 1,
                                 0,
                                 0,
                                 (struct _KERB_LOGON_SESSION *)&v199);
        if ( TicketGrantingTicket >= 0 )
        {
          TicketGrantingTicket = KerbCheckLogonSessionForWinlogonCallback(v199);
          if ( TicketGrantingTicket >= 0 )
          {
            if ( String1.Length )
              goto LABEL_311;
            TicketGrantingTicket = KerbDuplicateStringEx(&v224, (const struct _UNICODE_STRING *)String2, v104);
            if ( TicketGrantingTicket >= 0 )
            {
              KerbTracerT::Log(3, "KerbILogonUserEx3", 10994, "UPN logon %wZ\n", &v224);
              goto LABEL_311;
            }
          }
        }
LABEL_302:
        v23 = v196;
        goto LABEL_7;
      }
      if ( DWORD2(v206) == 1 )
      {
        v78 = Source1[1];
        if ( !Source1[1] )
          goto LABEL_217;
        v79 = LODWORD(Source1[0]);
        if ( LODWORD(Source1[0]) )
        {
          do
          {
            *v78++ = 0;
            --v79;
          }
          while ( v79 );
        }
        ((void (*)(void))KerbFree)();
      }
      else
      {
        KerbSecureFreeString(Source1);
      }
      v77 = (_WORD *)v219;
LABEL_217:
      v80 = 32;
      v81 = &v206;
      do
      {
        *(_BYTE *)v81 = 0;
        v81 = (__int128 *)((char *)v81 + 1);
        --v80;
      }
      while ( v80 );
      v266[0] = (struct _LUID)LocalhostKerbCredIsoObj::IsoObj;
      v266[1] = 0;
      v206 = (unsigned __int64)LocalhostKerbCredIsoObj::IsoObj;
      *(_OWORD *)Source1 = 0;
      LOWORD(Source1[0]) = *v77;
      WORD1(Source1[0]) = v77[2];
      v82 = MIDL_user_allocate(*((unsigned int *)v77 + 1));
      Source1[1] = v82;
      if ( !v82 )
      {
        LsaIFree_LSAPR_CR_CIPHER_VALUE(v219);
        TicketGrantingTicket = -1073741801;
        goto LABEL_58;
      }
      memcpy_0(v82, *(const void **)(v219 + 8), *(unsigned int *)(v219 + 4));
      LsaIFree_LSAPR_CR_CIPHER_VALUE(v219);
      goto LABEL_222;
    }
LABEL_58:
    v23 = v196;
LABEL_59:
    LOWORD(v26) = v192;
    goto LABEL_6;
  }
  AsRepCred = KerbFindAsRepCred(v22);
  v45 = 0;
  if ( !AsRepCred )
  {
    TicketGrantingTicket = -2146893039;
    KerbTracerT::Log(
      1,
      "KerbILogonUserEx3",
      10240,
      "No SECPKG_SURROGATE_LOGON_ENTRY_AS_REP_CREDENTIAL surrogate entry for LsaApLogonUserEx3");
    goto LABEL_58;
  }
  v46 = 1;
  v212.Buffer = (PWSTR)v19;
  v212.MaximumLength = a5;
  v212.Length = a5;
  v195 = 0;
  v47 = 0;
  v198 = 0;
LABEL_89:
  v51 = NtAllocateLocallyUniqueId(&LocallyUniqueId);
  TicketGrantingTicket = v51;
  if ( v51 < 0 )
  {
    v52 = "Failed to allocate locally unique ID: 0x%x";
    v53 = 10325;
LABEL_91:
    LODWORD(Size) = v51;
    KerbTracerT::Log(1, "KerbILogonUserEx3", v53, v52, Size);
    goto LABEL_36;
  }
  v51 = KerbCreateLogonSession(
          &LocallyUniqueId,
          &v247,
          &v247,
          0,
          0,
          0,
          ((v46 - 1) & 0xFFFFFFFD) == 0 ? 0x8000000 : 0,
          0,
          (struct _KERB_LOGON_SESSION *)&v199);
  TicketGrantingTicket = v51;
  if ( v51 < 0 )
  {
    v52 = "KerbCreateLogonSession failed with 0x%x";
    v53 = 10344;
    goto LABEL_91;
  }
  *((_QWORD *)v199 + 90) = *((_QWORD *)AsRepCred + 10);
  *((_QWORD *)v199 + 91) = *((_QWORD *)AsRepCred + 11);
  *((_DWORD *)v199 + 132) &= ~8u;
  *((_DWORD *)v199 + 226) &= ~2u;
  *((_DWORD *)v199 + 233) = v46;
  v26 = v192;
LABEL_313:
  KerbTracerT::Log(
    3,
    "KerbILogonUserEx3",
    11247,
    "LsaApLogonUserEx3: attempting to logon user %wZ\\%wZ\n",
    &String1,
    String2);
  if ( _KerberosSystemRole::IsAnyKdc(v105) && !KerbKdcStarted )
  {
    KerbTracerT::Log(12, "KerbILogonUserEx3", 11254, "Waiting for KDC to start\n");
    TicketGrantingTicket = KerbWaitForKdc(v106);
    if ( TicketGrantingTicket < 0 )
    {
      KerbTracerT::Log(12, "KerbILogonUserEx3", 11258, "Failed to wait for KDC to start\n");
      goto LABEL_97;
    }
  }
  v107 = v214;
  if ( v214 )
  {
LABEL_343:
    v23 = v196;
    v114 = KerbCreateTokenFromLogonTicket(
             v107,
             &LocallyUniqueId,
             (struct _KERB_INTERACTIVE_LOGON *)v24,
             (struct _KERB_PLAINTEXT_PASSWORD *)&v206,
             v45,
             v26,
             (struct _KERB_ENCRYPTION_KEY *)v255,
             (struct _KERB_MESSAGE_BUFFER *)&v254,
             &v241,
             v238,
             &v253,
             &v246,
             v218,
             v199,
             v234,
             v223,
             v233,
             (void **)v226,
             v196,
             v221,
             &v208,
             (struct _KERB_TICKET_LOGON_SUPP_CRED *)((unsigned __int64)v260 & -(__int64)(v200 != 0)));
    TicketGrantingTicket = v114;
    v116 = 0;
    if ( v114 < 0 )
    {
      v117 = "LogonUser: Failed to create token from logon ticket: 0x%x\n";
      v118 = 11611;
      v119 = 2;
LABEL_345:
      LODWORD(Sized) = v114;
      KerbTracerT::Log(v119, "KerbILogonUserEx3", v118, v117, Sized);
      goto LABEL_6;
    }
    if ( (*(_DWORD *)v24 == 2 || *(_DWORD *)v24 == 7) && !v47 && !DWORD2(v206) )
    {
      TicketGrantingTicket = KerbDuplicateStringEx(&v196->Password, (const struct _UNICODE_STRING *)Source1, v115);
      if ( TicketGrantingTicket < 0 )
        goto LABEL_6;
      v196->Flags |= 1u;
    }
    if ( v26 == Network )
    {
      if ( ((*(_DWORD *)v24 - 12) & 0xFFFFFFFD) != 0 )
      {
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
        v126 = *(_OWORD *)((char *)v199 + 120);
        *(_OWORD *)((char *)v199 + 120) = 0;
        v127 = *(_OWORD *)((char *)v199 + 136);
        *(_OWORD *)((char *)v199 + 136) = 0;
        KerbFreePrimaryCredentials((struct _KERB_LOGON_SESSION *)((char *)v199 + 120), 0);
        *(_OWORD *)((char *)v199 + 120) = v126;
        *(_OWORD *)((char *)v199 + 136) = v127;
        *((_DWORD *)v199 + 226) |= 0x8003u;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
      }
    }
    else if ( (unsigned int)(v26 - 4) <= 1 )
    {
      goto LABEL_383;
    }
    if ( (*((_BYTE *)v199 + 528) & 0x20) != 0 )
    {
      v114 = -1073741715;
      TicketGrantingTicket = -1073741715;
      v117 = "logon type is neither service nor batch for DMSA: %#x\n";
      v118 = 11673;
      v119 = 1;
      goto LABEL_345;
    }
LABEL_383:
    if ( v200 && (!pSid1 || !EqualSid(pSid1, v23->UserSid)) )
    {
      TicketGrantingTicket = -1073741790;
      goto LABEL_6;
    }
    v128 = LsaICheckProtectedUserByTokenInfo(*v223, (unsigned int)v26, v203);
    TicketGrantingTicket = v128;
    if ( v128 < 0 )
    {
      LODWORD(Sized) = v128;
      KerbTracerT::Log(1, "KerbILogonUserEx3", 11693, "LsaICheckProtectedUserByTokenInfo failed: %#x\n", Sized);
      goto LABEL_6;
    }
    if ( v203[0] )
    {
      v23->Flags |= 0x800u;
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
      *((_DWORD *)v199 + 226) |= 0x100000u;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
    if ( !RtlEqualUnicodeString((PCUNICODE_STRING)String2, &v23->DownlevelName, 1u) )
    {
      KerbFreeString(String2);
      TicketGrantingTicket = KerbDuplicateStringEx((struct _UNICODE_STRING *)String2, &v23->DownlevelName, v129);
      if ( TicketGrantingTicket < 0 )
      {
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
        goto LABEL_6;
      }
    }
    if ( !RtlEqualUnicodeString(&String1, &v23->DomainName, 0) )
    {
      KerbFreeString(&String1);
      TicketGrantingTicket = KerbDuplicateStringEx(&String1, &v23->DomainName, v131);
      if ( TicketGrantingTicket < 0 )
        goto LABEL_412;
    }
    TicketGrantingTicket = KerbDuplicateStringEx((struct _UNICODE_STRING *)((char *)v199 + 472), &v23->DomainName, v130);
    v132 = v199;
    if ( TicketGrantingTicket < 0 )
      goto LABEL_413;
    TicketGrantingTicket = KerbDuplicateStringEx(
                             (struct _UNICODE_STRING *)((char *)v199 + 456),
                             &v23->DownlevelName,
                             v133);
    v132 = v199;
    if ( TicketGrantingTicket < 0 )
      goto LABEL_413;
    TicketGrantingTicket = KerbDuplicateStringEx(
                             (struct _UNICODE_STRING *)((char *)v199 + 488),
                             &v23->DnsDomainName,
                             v134);
    if ( TicketGrantingTicket < 0
      || v23->UserSid && (TicketGrantingTicket = KerbDuplicateSid((char *)v199 + 504), TicketGrantingTicket < 0) )
    {
LABEL_412:
      v132 = v199;
LABEL_413:
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v132 + 2);
      goto LABEL_5;
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
    v135 = ((__int64 (__fastcall *)(LUID *))LsaFunctions->CreateLogonSession)(&LocallyUniqueId);
    TicketGrantingTicket = v135;
    if ( v135 < 0 )
    {
      v136 = "Failed to create logon session: 0x%x";
      v137 = 11806;
LABEL_421:
      LODWORD(Sized) = v135;
      KerbTracerT::Log(1, "KerbILogonUserEx3", v137, v136, Sized);
      goto LABEL_5;
    }
    if ( !v208 )
    {
LABEL_456:
      LsaISetLogonGuidInLogonSession(&LocallyUniqueId, &v288);
      if ( *((_QWORD *)v199 + 50) )
      {
        if ( !v197 )
        {
          TicketGrantingTicket = KerbDuplicatePassword(&v23->Password, &v228);
          if ( TicketGrantingTicket < 0 )
            goto LABEL_5;
          v156 = v195;
          v135 = KerbCreateSmartcardEx2PackedCreds(
                   &v228,
                   (struct _LUID *)((unsigned __int64)&v220 & -(__int64)(v195 != 0)),
                   (unsigned __int8 *)(*((_QWORD *)v199 + 50) + 80LL),
                   *(_DWORD *)(*((_QWORD *)v199 + 50) + 72LL),
                   v209,
                   &v23->Spare1);
          TicketGrantingTicket = v135;
          if ( v135 < 0 )
          {
            v136 = "KerbCreateSmartcardEx2PackedCreds failed: 0x%x\n";
            v137 = 11998;
            goto LABEL_421;
          }
          v23->Flags |= 0x8040u;
LABEL_472:
          if ( v198 )
            v23->Flags |= 0x400u;
          if ( v192 == CachedInteractive )
            v23->Flags |= 0x40000u;
          if ( v116 && (v23->Flags & 8) == 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          *((_QWORD *)v199 + 51) = *((_QWORD *)v199 + 8);
          LODWORD(v159) = v248;
          v160 = v221;
          if ( !v248 )
            v159 = *v221;
          TicketGrantingTicket = AddKerbSuppCreds((int)v159, (int)v199, (int)v260, (int)v24, &v245);
          if ( TicketGrantingTicket >= 0 )
          {
            if ( *v160 )
              KerbClientFreeSupplementalCredentials(v160);
            *v160 = v245;
            if ( v156 )
            {
              KerbUpdateOldLogonSession(
                v199,
                v23,
                v161,
                &v220,
                v214,
                (struct _UNICODE_STRING *)((unsigned __int64)&v228 & -(__int64)(v228.Buffer != 0)));
            }
            else if ( v228.Length )
            {
              v162 = *((_QWORD *)v199 + 50);
              if ( v162 )
              {
                if ( !KerbIsIumCert(*(const struct _CERT_CONTEXT **)(v162 + 32))
                  && (*((_DWORD *)v199 + 226) & 0x1000000) == 0 )
                {
                  LsaIEfsAcceptSmartcardCredentials(*(_QWORD *)(*((_QWORD *)v199 + 50) + 32LL), &v228, &LocallyUniqueId);
                }
              }
            }
            v23->Flags |= 0x1000u;
            v23[1].LogonId = (LUID)KerberosPackageId;
            v163 = LocallyUniqueId;
            v164 = LocallyUniqueId;
            if ( v156 )
              v164 = v220;
            *(LUID *)&v23[1].DownlevelName.Length = v164;
            *(LUID *)v229 = v163;
            if ( v200 )
              LsaISetPackageAttrInLogonSession(&LocallyUniqueId, 0x2000000);
            updated = KerbUpdateSecPkgPrimaryCredsForDmsa(v199, v23, v160, (struct _UNICODE_STRING *)String2, &v215);
            TicketGrantingTicket = updated;
            if ( updated < 0 )
              KerbTracerT::Log(
                1,
                "KerbILogonUserEx3",
                12131,
                "KerbUpdateSecPkgPrimaryCredsForDmsa failed: %#x\n",
                updated);
          }
          goto LABEL_59;
        }
        v23->Flags |= 0x88000u;
      }
      else
      {
        if ( !v46 )
        {
LABEL_471:
          v156 = v195;
          goto LABEL_472;
        }
        v23->Flags |= 0x8000u;
        Flags = v23->Flags;
        if ( v46 == 1 )
        {
          v158 = Flags | 0x100000;
        }
        else
        {
          if ( v46 != 3 )
          {
            LODWORD(Sized) = v46;
            KerbTracerT::Log(1, "KerbILogonUserEx3", 12030, "Unexpected AsRepSourceCred type: %#x\n", Sized);
            goto LABEL_5;
          }
          LODWORD(v23[1].DownlevelName.Buffer) |= 1u;
          v158 = Flags | 0x1000;
        }
        v23->Flags = v158;
      }
      TicketGrantingTicket = KerbDuplicateStringEx(&v23->Spare1, &v212, v155);
      if ( TicketGrantingTicket < 0 )
        goto LABEL_5;
      goto LABEL_471;
    }
    memset(v264, 0, 24);
    KerbTracerT::Log(12, "KerbILogonUserEx3", 11825, "NameDisplay %wZ\n", (char *)v208 + 64);
    v289[0] = 3;
    v138 = v208;
    v290 = (char *)v208 + 64;
    v139 = v224.Length;
    if ( !v224.Length && *((_WORD *)v208 + 152) )
    {
      KerbFreeString(&v224);
      v135 = KerbDuplicateStringEx(&v224, (const struct _UNICODE_STRING *)v208 + 19, v140);
      TicketGrantingTicket = v135;
      if ( v135 < 0 )
      {
        v136 = "LsaApLogonUserEx3 failed to duplicate UPN: %#x";
        v137 = 11842;
        goto LABEL_421;
      }
      v139 = v224.Length;
      v138 = v208;
    }
    v141 = 1;
    if ( v139 )
    {
      KerbTracerT::Log(12, "KerbILogonUserEx3", 11854, "NameUserPrincipal %wZ\n", &v224);
      v291 = 8;
      v292 = &v224;
      v141 = 2;
      v138 = v208;
    }
    v142 = (_WORD *)((char *)v138 + 288);
    if ( *v142 )
    {
      KerbTracerT::Log(12, "KerbILogonUserEx3", 11863, "NameDnsDomain %wZ\n", v142);
      TicketGrantingTicket = KerbDuplicateStringEx(&v239, (const struct _UNICODE_STRING *)v208 + 18, v143);
      goto LABEL_444;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
    if ( !*((_WORD *)v199 + 68) )
    {
LABEL_443:
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
LABEL_444:
      if ( TicketGrantingTicket < 0 )
        goto LABEL_5;
      if ( v239.Length && v239.Buffer )
      {
        v148 = 2LL * v141;
        v289[2 * v148] = 12;
        (&v290)[v148] = (char *)&v239;
        ++v141;
      }
      LsaIAddNamesToLogonSession(&LocallyUniqueId, v141, v289);
      LsaISetUserFlags(&LocallyUniqueId, *((unsigned int *)v208 + 42));
      v149 = v208;
      if ( *(_QWORD *)&v264[0].Length != *((_QWORD *)v208 + 31) || *(_OWORD *)&v264[0].Buffer != *((_OWORD *)v208 + 16) )
      {
        v264[0] = *(struct _UNICODE_STRING *)((char *)v208 + 248);
        *(_QWORD *)&v264[1].Length = *((_QWORD *)v208 + 33);
        KerbTracerT::Log(2, "KerbILogonUserEx3", 11940, "LsaApLogonUserEx3 adding last logon info\n");
        v149 = v208;
      }
      if ( (*((_BYTE *)v149 + 168) & 4) != 0 )
      {
        v154 = 0;
        v153 = 0;
        v152 = 0;
        v151 = 0;
        v150 = 0;
      }
      else
      {
        v150 = (char *)v149 + 40;
        v151 = (char *)v149 + 32;
        v152 = (char *)v149 + 24;
        v153 = (char *)v149 + 16;
        v154 = (char *)v149 + 8;
      }
      v135 = LsaISetLogonInfo(
               &LocallyUniqueId,
               v264,
               (char *)v149 + 80,
               (char *)v149 + 96,
               (char *)v149 + 112,
               (char *)v149 + 128,
               v154,
               v153,
               v152,
               v151,
               v150);
      TicketGrantingTicket = v135;
      if ( v135 < 0 )
      {
        v136 = "LsaApLogonUserEx3 failed to add last logon info: %#x\n";
        v137 = 11959;
        goto LABEL_421;
      }
      goto LABEL_456;
    }
    if ( (*((_BYTE *)v199 + 904) & 0x20) != 0 )
    {
      ClientDomain = KerbGetClientDomain((PCUNICODE_STRING)((char *)v199 + 136), &v239);
      goto LABEL_442;
    }
    KerbTracerT::Log(12, "KerbILogonUserEx3", 11877, "DomainName %wZ\n", (char *)v199 + 136);
    if ( v24 && *(_DWORD *)v24 == 12 )
    {
      v145 = v199;
      v146 = (const wchar_t *)*((_QWORD *)v199 + 18);
      if ( !v146 )
      {
LABEL_440:
        ClientDomain = KerbDuplicateStringEx(&v239, (const struct _UNICODE_STRING *)((char *)v145 + 136), v144);
LABEL_442:
        TicketGrantingTicket = ClientDomain;
        goto LABEL_443;
      }
      if ( !wcschr(v146, 0x2Eu) )
      {
        KerbTracerT::Log(2, "KerbILogonUserEx3", 11898, "DomainName %wZ is not DNS domain name\n", (char *)v199 + 136);
        goto LABEL_443;
      }
    }
    v145 = v199;
    goto LABEL_440;
  }
  if ( v26 == CachedInteractive )
  {
    TicketGrantingTicket = -1073741422;
    goto LABEL_347;
  }
  v108 = &v227;
  if ( !AsRepCred )
  {
    if ( BYTE1(KerbGlobalRoles) )
      v108 = 0;
    TicketGrantingTicket = KerbGetTicketGrantingTicket(
                             v199,
                             0,
                             0,
                             0,
                             0,
                             0,
                             0,
                             v108,
                             (struct _KERB_ENCRYPTION_KEY *)v255,
                             0);
    if ( (*((_BYTE *)v199 + 528) & 1) != 0 && TicketGrantingTicket == -1073741718 )
    {
      LODWORD(v191) = -1073741718;
      KerbTracerT::Log(
        2,
        "KerbILogonUserEx3",
        11325,
        "LogonUser: Failed to get TGT for gMSA (will try force fetch) %wZ\\%wZ : 0x%x\n",
        &String1,
        String2,
        v191);
      *((_DWORD *)v199 + 132) |= 2u;
      v109 = &v227;
      if ( BYTE1(KerbGlobalRoles) )
        v109 = 0;
      TicketGrantingTicket = KerbGetTicketGrantingTicket(
                               v199,
                               0,
                               0,
                               0,
                               0,
                               0,
                               0,
                               v109,
                               (struct _KERB_ENCRYPTION_KEY *)v255,
                               0);
    }
LABEL_331:
    if ( TicketGrantingTicket >= 0 )
      goto LABEL_332;
LABEL_347:
    v111 = 2;
    v112 = 11437;
    v113 = "LogonUser: Failed to get TGT for %wZ\\%wZ : 0x%x\n";
    goto LABEL_348;
  }
  if ( BYTE1(KerbGlobalRoles) )
    v108 = 0;
  TicketGrantingTicket = KerbGetTicketForCredential(v199, 0, 0, 0, 0, 0, 0, v108);
  *((_QWORD *)v199 + 91) = 0;
  if ( TicketGrantingTicket < 0 )
  {
    KerbTracerT::Log(
      3,
      "KerbILogonUserEx3",
      11294,
      "KerbGetTicketGrantingTicketFromAsRepCallback failed with 0x%x",
      TicketGrantingTicket);
    goto LABEL_331;
  }
LABEL_332:
  if ( !BYTE1(KerbGlobalRoles) )
  {
    KerbTracerT::Log(1, "KerbILogonUserEx3", 11415, "Nonjoined workstation\n");
    TicketGrantingTicket = KerbCheckRealmlessLogonPolicy(v227, v230, &v251);
    if ( TicketGrantingTicket < 0 )
    {
      KerbTracerT::Log(1, "KerbILogonUserEx3", 11427, "LogonUser:  Failed check for domainless logon\n");
      goto LABEL_97;
    }
    goto LABEL_342;
  }
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
  *((_DWORD *)v199 + 226) &= ~1u;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v199 + 2);
  RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
  TicketGrantingTicket = KerbDuplicateKdcName(&v237, KerbGlobalMitMachineServiceName);
  RtlReleaseResource(&KerberosGlobalResource);
  if ( TicketGrantingTicket < 0 )
    goto LABEL_97;
  TicketGrantingTicket = KerbGetOurDomainName(&v252);
  if ( TicketGrantingTicket < 0 )
    goto LABEL_97;
  v110 = v237;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_158d5f44375531ecadb51b1a2a87ab5b_Traceguids, v237);
  TicketGrantingTicket = KerbGetServiceTicketEx(
                           v199,
                           0,
                           0,
                           0,
                           0,
                           v110,
                           &v252,
                           v225 | 1,
                           0,
                           0,
                           0,
                           0,
                           0,
                           &v214,
                           &v288,
                           (struct _KERB_ENCRYPTION_KEY *)v255);
  v26 = v192;
  if ( TicketGrantingTicket >= 0 )
  {
LABEL_342:
    v107 = v214;
    goto LABEL_343;
  }
  v111 = 1;
  v112 = 11410;
  v113 = "LogonUser: Failed to get workstation ticket for %wZ\\%wZ: 0x%x";
LABEL_348:
  LODWORD(v191) = TicketGrantingTicket;
  KerbTracerT::Log(v111, "KerbILogonUserEx3", v112, v113, &String1, String2, v191);
  if ( v46 || *((_QWORD *)v199 + 50) )
  {
    v120 = -1073741730;
    if ( TicketGrantingTicket != -1073741730
      && TicketGrantingTicket != -1073741252
      && TicketGrantingTicket != -1073741422 )
    {
      v26 = v192;
      goto LABEL_354;
    }
    memset(v264, 0, 24);
    if ( !((unsigned __int8 (__fastcall *)(struct _UNICODE_STRING *))LsaFunctions->GetCallInfo)(v264) )
    {
      TicketGrantingTicket = -1073741595;
      goto LABEL_58;
    }
    if ( ((__int64)v264[0].Buffer & 0x400) != 0 )
    {
      KerbTracerT::Log(2, "KerbILogonUserEx3", 11466, "DC not reachable, caller does not want cached logon\n");
      goto LABEL_58;
    }
    if ( v46 == 1 )
    {
      v205 = 0;
      KerbLocateFidoCacheFromSurrogateLogon(v244, &v205);
      v121 = v205;
      if ( !v205 )
      {
        KerbTracerT::Log(2, "KerbILogonUserEx3", 11480, "No cache data for FIDO\n");
        goto LABEL_388;
      }
      v266[0].LowPart = 0;
      LOBYTE(v266[0].HighPart) = 0;
      _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(v266);
      if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
      {
        LODWORD(v205) = GetCurrentThreadId();
        v218 = (struct KerbCredIsoApi *)0x1000000;
        if ( LOBYTE(v266[0].HighPart) && (*((_QWORD *)&v267 + 1) || v268 || v269) )
          v122 = (char *)&v267 + 8;
        else
          LODWORD(v122) = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180140048,
          (unsigned int)byte_18012C365,
          (unsigned int)&v266[1],
          (_DWORD)v122,
          (__int64)&v218,
          (__int64)&v205);
      }
      KerbTracerT::Log(3, "KerbILogonUserEx3", 11493, "Attempting cached FIDO logon\n");
      v23 = v196;
      v120 = KerbDoCachedFidoLogon(v199, v121, v234, v223, v233, v226, v196, v221, &v208);
      v266[0].LowPart = 2;
      if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
      {
        LODWORD(v205) = v120;
        LODWORD(SourceLuid[0]) = GetCurrentThreadId();
        v218 = (struct KerbCredIsoApi *)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180140048,
          (unsigned int)&byte_18012C31F,
          (unsigned int)&v266[1],
          v123,
          (__int64)&v218,
          (__int64)SourceLuid,
          (__int64)&v205);
      }
      _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const KerbTraceLogger,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(v266);
    }
    else
    {
      if ( !*((_QWORD *)v199 + 50) )
      {
        v120 = -2146893042;
        KerbTracerT::Log(1, "KerbILogonUserEx3", 11540, "No SC creds: 0x%x; CredType: 0x%x", -2146893042, v46);
        goto LABEL_388;
      }
      if ( ((*(_DWORD *)v24 - 13) & 0xFFFFFFFD) != 0 )
      {
        v124 = 0;
        v125 = 0;
      }
      else
      {
        v124 = (struct _UNICODE_STRING *)(v24 + 4);
        v125 = (struct _UNICODE_STRING *)(v24 + 12);
      }
      v23 = v196;
      v120 = KerbDoLocalSmartCardLogon(v199, v125, v124, v234, v223, v233, v226, v196, v221, &v208);
    }
    if ( v120 >= 0 )
    {
      v116 = 1;
      v26 = v192;
      goto LABEL_383;
    }
LABEL_388:
    KerbTracerT::Log(1, "KerbILogonUserEx3", 11545, "Failed local logon: 0x%x", v120);
    v23 = v196;
    v28 = pCertContext;
    v27 = 32;
    if ( v192 == CachedInteractive )
      TicketGrantingTicket = v120;
    goto LABEL_390;
  }
LABEL_354:
  v23 = v196;
  v28 = pCertContext;
  v27 = 32;
  if ( v26 == CachedInteractive )
    TicketGrantingTicket = -1073741557;
LABEL_8:
  if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
  {
    *(_QWORD *)&v229 = &v252;
    LODWORD(v205) = KerbGlobalIsRunningIsolated;
    LOWORD(SourceLuid[0]) = v26;
    v192 = TicketGrantingTicket;
    v218 = (struct KerbCredIsoApi *)1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>>(
      v29,
      (unsigned int)&dword_18012C2AC,
      v30,
      (unsigned int)&v218,
      (__int64)&v192,
      (__int64)SourceLuid,
      (__int64)&v205,
      (__int64)&v229,
      (__int64)&v215);
  }
  if ( v208 )
    KerbFree(v208);
  KerbFreeString(&v249);
  KerbFreeString(&v250);
  if ( DWORD2(v242) == 1 )
  {
    v31 = (_BYTE *)*((_QWORD *)&v243 + 1);
    if ( *((_QWORD *)&v243 + 1) )
    {
      v32 = (unsigned int)v243;
      if ( (_DWORD)v243 )
      {
        do
        {
          *v31++ = 0;
          --v32;
        }
        while ( v32 );
        v31 = (_BYTE *)*((_QWORD *)&v243 + 1);
      }
      KerbFree(v31);
    }
  }
  else
  {
    KerbSecureFreeString(&v243);
  }
  v166 = 32;
  v167 = &v242;
  do
  {
    *(_BYTE *)v167 = 0;
    v167 = (__int128 *)((char *)v167 + 1);
    --v166;
  }
  while ( v166 );
  KerbFreeString(&v224);
  KerbFreeString(&v239);
  if ( v28 )
    CertFreeCertificateContext(v28);
  KerbFreeTicketLogonSuppCred((struct _KERB_TICKET_LOGON_SUPP_CRED *)v260);
  if ( pSid1 )
    ((void (*)(void))LsaFunctions->FreeLsaHeap)();
  KerbFreeString(&v263);
  KerbFreeKey(v255);
  if ( *v240 )
  {
    *(_OWORD *)*v240 = *(_OWORD *)String2;
    String2[1] = 0;
  }
  if ( *v236 )
  {
    **v236 = String1;
    String1.Buffer = 0;
  }
  if ( TicketGrantingTicket >= 0 )
  {
    v171 = v216;
    goto LABEL_544;
  }
  if ( v199 )
    KerbRemoveLogonSession(v199);
  v168 = v226;
  v169 = *v226;
  if ( *v226 )
  {
    ((void (__fastcall *)(_QWORD))LsaFunctions->FreeClientBuffer)(0);
    *v168 = 0;
  }
  if ( *v221 )
    KerbClientFreeSupplementalCredentials(v221);
  if ( TicketGrantingTicket > -1073740927 )
  {
    if ( (unsigned int)(TicketGrantingTicket + 1073740925) > 0xA
      || (v173 = 2015, !_bittest(&v173, TicketGrantingTicket + 1073740925)) )
    {
      if ( (unsigned int)(TicketGrantingTicket + 1073740788) > 3 )
        goto LABEL_527;
    }
    goto LABEL_542;
  }
  if ( TicketGrantingTicket == -1073740927 )
    goto LABEL_542;
  v170 = -1073741421;
  if ( TicketGrantingTicket > -1073741421 )
  {
    if ( TicketGrantingTicket != -1073741389 && TicketGrantingTicket != -1073741063 )
    {
      if ( TicketGrantingTicket == -1073741062 )
        goto LABEL_538;
      if ( (unsigned int)(TicketGrantingTicket + 1073741024) > 1 && TicketGrantingTicket != -1073740928 )
        goto LABEL_527;
    }
    goto LABEL_542;
  }
  if ( TicketGrantingTicket == -1073741421 )
  {
LABEL_531:
    v171 = v216;
    *v216 = v170;
    goto LABEL_528;
  }
  if ( TicketGrantingTicket == -1073741724 || TicketGrantingTicket == -1073741718 )
  {
LABEL_542:
    v171 = v216;
    *v216 = TicketGrantingTicket;
    TicketGrantingTicket = -1073741715;
    goto LABEL_528;
  }
  v170 = -1073741714;
  if ( TicketGrantingTicket == -1073741714 )
    goto LABEL_531;
  if ( (unsigned int)(TicketGrantingTicket + 1073741713) <= 3 )
  {
LABEL_538:
    v171 = v216;
    *v216 = TicketGrantingTicket;
    TicketGrantingTicket = -1073741714;
    goto LABEL_528;
  }
LABEL_527:
  v171 = v216;
LABEL_528:
  v172 = v223;
  if ( *v223 )
  {
    KerbFree(*v223);
    *v172 = 0;
  }
  KerbFreeSecpkgPrimaryCredentials(v23, (unsigned __int8)v169);
  KerbTracerT::Log(1, "KerbILogonUserEx3", 12303, "LogonUser returned %x, %x\n", TicketGrantingTicket, *v171);
LABEL_544:
  if ( v214 )
    KerbDereferenceTicketCacheEntry(v214);
  if ( v227 )
    KerbDereferenceTicketCacheEntry(v227);
  if ( v199 )
    KerbDereferenceLogonSession(v199);
  KerbFreeKdcName(&v230);
  KerbFreeKdcName(&v238);
  KerbFreeString(&v251);
  KerbFreeString(&v252);
  KerbFreeString(&v241);
  KerbFreeString(String2);
  KerbFreeString(&String1);
  KerbFreeKdcName(&v237);
  KerbFreeString(&v253);
  v174 = MIDL_user_allocate(0x10u);
  v175 = (struct _UNICODE_STRING **)v231;
  *(_QWORD *)v231 = v174;
  if ( v174 )
  {
    RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
    v177 = KerbDuplicateStringEx(*v175, &KerbGlobalMachineName, v176);
    RtlReleaseResource(&KerberosGlobalResource);
    if ( v177 < 0 )
    {
      KerbTracerT::Log(1, "KerbILogonUserEx3", 12365, "Failed to duplicate KerbGlobalMachineName\n");
      **v175 = 0;
    }
  }
  if ( KerbEventTraceFlag )
  {
    v274 = v171;
    v275 = 4;
    v270[0] = 64;
    if ( v24 )
    {
      v212 = 0;
      if ( *(_DWORD *)v24 == 513 )
      {
        v229 = 0;
        v231 = 0;
        WORD1(v231) = v24[8];
        LOWORD(v231) = WORD1(v231);
        if ( WORD1(v231) )
          *((_QWORD *)&v231 + 1) = (char *)v24 + *((unsigned int *)v24 + 3);
        WORD1(v229) = v24[12];
        LOWORD(v229) = WORD1(v229);
        if ( WORD1(v229) )
          *((_QWORD *)&v229 + 1) = (char *)v24 + *((unsigned int *)v24 + 5);
        RtlInitUnicodeString(&v212, L"SEC_WINNT_AUTH_IDENTITY_VERSION_2");
        v276 = &v212;
        v277 = 2;
        Buffer = v212.Buffer;
        v279 = v212.Length;
        v280 = &v231;
        v281 = 2;
        v282 = *((_QWORD *)&v231 + 1);
        v283 = (unsigned __int16)v231;
        v284 = &v229;
        v285 = 2;
        v286 = *((_QWORD *)&v229 + 1);
        v179 = (unsigned __int16)v229;
      }
      else
      {
        v178 = KerbLogonMessageTypeToString((enum _KERB_LOGON_SUBMIT_TYPE)*(_DWORD *)v24);
        RtlInitUnicodeString(&v212, v178);
        v276 = &v212;
        v277 = 2;
        Buffer = v212.Buffer;
        v279 = v212.Length;
        v280 = (__int128 *)(v24 + 12);
        v281 = 2;
        v282 = *((_QWORD *)v24 + 4);
        v283 = v24[12];
        v284 = (__int128 *)(v24 + 4);
        v285 = 2;
        v286 = *((_QWORD *)v24 + 2);
        v179 = v24[4];
      }
      v287 = v179;
      v270[0] += 96;
    }
    v272 = KerbLogonGuid;
    v271 = 2;
    v273 = 1179648;
    EtwLogTraceEvent(KerbTraceLoggerHandle, v270);
  }
  if ( v202 )
    KerbFree(v209);
  v180 = v228.Buffer;
  if ( v228.Buffer )
  {
    v181 = v228.Length;
    if ( v228.Length )
    {
      do
      {
        *(_BYTE *)v180 = 0;
        v180 = (PWSTR)((char *)v180 + 1);
        --v181;
      }
      while ( v181 );
    }
    KerbFreeString(&v228);
  }
  if ( DWORD2(v206) == 1 )
  {
    v182 = Source1[1];
    if ( Source1[1] )
    {
      v183 = LODWORD(Source1[0]);
      if ( LODWORD(Source1[0]) )
      {
        do
        {
          *v182++ = 0;
          --v183;
        }
        while ( v183 );
        v182 = Source1[1];
      }
      KerbFree(v182);
    }
  }
  else
  {
    KerbSecureFreeString(Source1);
  }
  v184 = &v206;
  do
  {
    *(_BYTE *)v184 = 0;
    v184 = (__int128 *)((char *)v184 + 1);
    --v27;
  }
  while ( v27 );
  KerbTracerT::CaptureLastStatus(TicketGrantingTicket);
  KerbTracerT::~KerbTracerT((KerbTracerT *)v232);
  return (unsigned int)TicketGrantingTicket;
}

```

## disassembly

```asm
0x180025680  mov     rax, rsp
0x180025683  push    rbp
0x180025684  push    rbx
0x180025685  push    rsi
0x180025686  push    rdi
0x180025687  push    r12
0x180025689  push    r13
0x18002568b  push    r14
0x18002568d  push    r15
0x18002568f  lea     rbp, [rax-448h]
0x180025696  sub     rsp, 538h
0x18002569d  movaps  xmmword ptr [rax-58h], xmm6
0x1800256a1  movaps  xmmword ptr [rax-68h], xmm7
0x1800256a5  mov     rax, cs:__security_cookie
0x1800256ac  xor     rax, rsp
0x1800256af  mov     [rbp+440h+var_70], rax
0x1800256b6  mov     r15, r9
0x1800256b9  mov     rbx, r8
0x1800256bc  mov     esi, edx
0x1800256be  mov     [rbp+440h+var_4C0], edx
0x1800256c1  mov     r14, rcx
0x1800256c4  mov     rdi, [rbp+440h+arg_28]
0x1800256cb  mov     [rbp+440h+var_2C8], rdi
0x1800256d2  mov     rax, [rbp+440h+arg_38]
0x1800256d9  mov     [rbp+440h+var_390], rax
0x1800256e0  mov     rax, [rbp+440h+arg_40]
0x1800256e7  mov     [rbp+440h+var_340], rax
0x1800256ee  mov     rax, [rbp+440h+arg_48]
0x1800256f5  mov     qword ptr [rbp+440h+var_370], rax
0x1800256fc  mov     rax, [rbp+440h+arg_50]
0x180025703  mov     [rbp+440h+var_3F8], rax
0x180025707  mov     rax, [rbp+440h+arg_58]
0x18002570e  mov     [rbp+440h+var_338], rax
0x180025715  mov     rax, [rbp+440h+arg_60]
0x18002571c  mov     [rbp+440h+var_3B0], rax
0x180025723  mov     rax, [rbp+440h+arg_68]
0x18002572a  mov     [rbp+440h+var_300], rax
0x180025731  mov     rax, [rbp+440h+arg_70]
0x180025738  mov     [rbp+440h+var_328], rax
0x18002573f  mov     rax, [rbp+440h+arg_78]
0x180025746  mov     qword ptr [rbp+440h+var_358], rax
0x18002574d  mov     r13, [rbp+440h+arg_80]
0x180025754  mov     [rbp+440h+var_4A8], r13
0x180025758  mov     rax, [rbp+440h+arg_88]
0x18002575f  mov     [rbp+440h+var_3C8], rax
0x180025763  lea     rdx, aLogonUser; "Logon User"
0x18002576a  lea     rcx, [rbp+440h+var_348]; this
0x180025771  call    ??0KerbTracerT@@QEAA@PEBDK@Z; KerbTracerT::KerbTracerT(char const *,ulong)
0x180025776  nop
0x180025777  xor     edx, edx; Val
0x180025779  mov     [rbp+440h+var_498], rdx
0x18002577d  mov     r12d, edx
0x180025780  mov     rcx, cs:?IsoObj@LocalhostKerbCredIsoObj@@0PEAVKerbCredIsoApi@@EA; KerbCredIsoApi * LocalhostKerbCredIsoObj::IsoObj
0x180025787  mov     qword ptr [rbp+440h+var_470], rcx
0x18002578b  mov     qword ptr [rbp+440h+var_470+8], rdx
0x18002578f  xorps   xmm0, xmm0
0x180025792  movups  xmmword ptr [rbp+440h+Source1], xmm0
0x180025796  xorps   xmm1, xmm1
0x180025799  movups  xmmword ptr [rbp+440h+var_380.Length], xmm1
0x1800257a0  mov     [rbp+440h+String2], rdx
0x1800257a4  mov     [rbp+440h+String2+8], rdx
0x1800257a8  mov     qword ptr [rbp+440h+String1.Length], rdx
0x1800257ac  mov     [rbp+440h+String1.Buffer], rdx
0x1800257b0  mov     qword ptr [rbp+440h+var_2F8.Length], rdx
0x1800257b7  mov     [rbp+440h+var_2F8.Buffer], rdx
0x1800257be  mov     qword ptr [rbp+440h+LocallyUniqueId.LowPart], rdx
0x1800257c2  mov     qword ptr [rbp+440h+var_3D0.LowPart], rdx
0x1800257c6  mov     qword ptr [rbp+440h+var_2B8.LowPart], rdx
0x1800257cd  mov     [rbp+440h+var_408], rdx
0x1800257d1  mov     [rbp+440h+var_388], rdx
0x1800257d8  movups  [rbp+440h+var_248], xmm0
0x1800257df  xor     eax, eax
0x1800257e1  movups  [rbp+440h+var_238], xmm1
0x1800257e8  movups  [rbp+440h+var_228], xmm1
0x1800257ef  mov     [rbp+440h+var_218], rax
0x1800257f6  movups  xmmword ptr [rbp+440h+var_268.Length], xmm0
0x1800257fd  mov     [rbp+440h+var_360], rdx
0x180025804  movups  xmmword ptr [rbp+440h+var_278.Length], xmm1
0x18002580b  movups  xmmword ptr [rbp+440h+var_3A8.Length], xmm0
0x180025812  mov     [rbp+440h+var_320], rdx
0x180025819  mov     [rbp+440h+var_318], rdx
0x180025820  movups  xmmword ptr [rbp+440h+var_258.Length], xmm0
0x180025827  movups  [rbp+440h+var_1C0], xmm1
0x18002582e  mov     [rbp+440h+var_3D8], rdx
0x180025832  movups  xmmword ptr [rbp+440h+DestinationString.Length], xmm0
0x180025839  mov     [rbp+440h+var_398], edx
0x18002583f  mov     [rbp+440h+pCertContext], rdx
0x180025843  mov     [rbp+440h+var_410], rdx
0x180025847  mov     [rbp+440h+var_448], rbx
0x18002584b  mov     [rbp+440h+var_450], rdx
0x18002584f  movups  xmmword ptr [rbp+440h+var_B0.Data1], xmm0
0x180025856  movups  xmmword ptr [rbp+440h+var_310.Length], xmm1
0x18002585d  movups  xmmword ptr [rbp+440h+var_420.Length], xmm0
0x180025861  mov     [rbp+440h+var_2A0], rdx
0x180025868  mov     [rbp+440h+var_2C0], rdx
0x18002586f  mov     [rbp+440h+var_490], dl
0x180025872  mov     [rbp+440h+var_48F], dl
0x180025875  mov     [rbp+440h+Source2], 0C2BE5457h
0x18002587f  mov     [rbp+440h+var_18C], 483E82EBh
0x180025889  mov     [rbp+440h+var_188], 68744EAEh
0x180025893  mov     [rbp+440h+var_184], 9D514EFh
0x18002589d  mov     [rbp+440h+pSid1], rdx
0x1800258a4  mov     [rbp+440h+var_3E0], rdx
0x1800258a8  movups  xmmword ptr [rbp+440h+var_1E8], xmm0
0x1800258af  movups  [rbp+440h+var_1D8], xmm0
0x1800258b6  mov     [rbp+440h+var_1C8], rax
0x1800258bd  mov     [rbp+440h+var_488], dl
0x1800258c0  mov     [rbp+440h+var_400], edx
0x1800258c3  movups  xmmword ptr [rbp+440h+var_298.Length], xmm0
0x1800258ca  movups  xmmword ptr [rbp+440h+var_288.Length], xmm1
0x1800258d1  mov     qword ptr [rbp+440h+var_2E8], rcx
0x1800258d8  mov     qword ptr [rbp+440h+var_2E8+8], rdx
0x1800258df  movups  [rbp+440h+var_2D8], xmm0
0x1800258e6  mov     [rbp+440h+var_48C], edx
0x1800258e9  mov     r8d, 0A0h; Size
0x1800258ef  lea     rcx, [rbp+440h+var_150]; void *
0x1800258f6  call    memset_0
0x1800258fb  xor     ecx, ecx
0x1800258fd  mov     qword ptr [rbp+440h+var_2B0.Length], rcx
0x180025904  mov     [rbp+440h+var_2B0.Buffer], rcx
0x18002590b  lea     eax, [rcx+30h]
0x18002590e  cmp     cs:KerbEventTraceFlag, cl
0x180025914  jz      short loc_180025953
0x180025916  movups  xmm0, cs:KerbLogonGuid
0x18002591d  movdqu  [rbp+440h+var_138], xmm0
0x180025925  mov     [rbp+440h+var_14C], 1
0x18002592c  mov     [rbp+440h+var_124], 20000h
0x180025936  mov     [rbp+440h+var_150], ax
0x18002593d  lea     rdx, [rbp+440h+var_150]
0x180025944  mov     rcx, cs:KerbTraceLoggerHandle
0x18002594b  call    cs:__imp_EtwLogTraceEvent
0x180025951  xor     ecx, ecx
0x180025953  mov     rax, [rbp+440h+var_390]
0x18002595a  mov     [rax], rcx
0x18002595d  mov     rax, [rbp+440h+var_3F8]
0x180025961  mov     [rax], ecx
0x180025963  mov     rax, [rbp+440h+var_3B0]
0x18002596a  mov     [rax], rcx
0x18002596d  mov     rax, [rbp+440h+var_300]
0x180025974  mov     [rax], rcx
0x180025977  mov     rax, [rbp+440h+var_328]
0x18002597e  mov     [rax], rcx
0x180025981  mov     rax, qword ptr [rbp+440h+var_358]
0x180025988  mov     [rax], rcx
0x18002598b  mov     rax, [rbp+440h+var_3C8]
0x18002598f  mov     [rax], rcx
0x180025992  mov     [rbp+440h+var_298.Buffer], rcx
0x180025999  mov     [rbp+440h+var_288.Buffer], rcx
0x1800259a0  xor     edx, edx; Val
0x1800259a2  mov     r8d, 0E0h; Size
0x1800259a8  mov     rcx, r13; void *
0x1800259ab  call    memset_0
0x1800259b0  cmp     cs:?KerbGlobalInitialized@@3EA, r12b; uchar KerbGlobalInitialized
0x1800259b7  jnz     loc_180025AD2
0x1800259bd  mov     edi, 0C00000DCh
0x1800259c2  mov     ebx, [rbp+440h+var_4C0]
0x1800259c5  xor     r14d, r14d
0x1800259c8  mov     r15d, 20h ; ' '
0x1800259ce  mov     rsi, [rbp+440h+pCertContext]
0x1800259d2  mov     eax, cs:dword_180140048
0x1800259d8  cmp     eax, 5
0x1800259db  jbe     loc_180025A67
0x1800259e1  mov     rdx, 400000000000h
0x1800259eb  lea     rcx, dword_180140048
0x1800259f2  call    _tlgKeywordOn
0x1800259f7  test    al, al
0x1800259f9  jz      short loc_180025A67
0x1800259fb  mov     eax, [rbp+440h+var_400]
0x1800259fe  mov     [rbp+440h+var_400], eax
0x180025a01  lea     rax, [rbp+440h+var_268]
0x180025a08  mov     qword ptr [rbp+440h+var_370], rax
0x180025a0f  mov     eax, cs:?KerbGlobalIsRunningIsolated@@3HA; int KerbGlobalIsRunningIsolated
0x180025a15  mov     dword ptr [rbp+440h+var_478], eax
0x180025a18  mov     word ptr [rbp+440h+SourceLuid], bx
0x180025a1c  mov     [rbp+440h+var_4C0], edi
0x180025a1f  mov     [rbp+440h+var_3E0], 1
0x180025a27  lea     rax, [rbp+440h+var_400]
0x180025a2b  mov     [rsp+570h+var_530], rax
0x180025a30  lea     rax, [rbp+440h+var_370]
0x180025a37  mov     [rsp+570h+var_538], rax
0x180025a3c  lea     rax, [rbp+440h+var_478]
0x180025a40  mov     [rsp+570h+var_540], rax
0x180025a45  lea     rax, [rbp+440h+SourceLuid]
0x180025a49  mov     qword ptr [rsp+570h+var_548], rax
0x180025a4e  lea     rax, [rbp+440h+var_4C0]
0x180025a52  mov     [rsp+570h+Size], rax
0x180025a57  lea     r9, [rbp+440h+var_3E0]
0x180025a5b  lea     rdx, dword_18012C2AC
0x180025a62  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &)
0x180025a67  mov     rcx, [rbp+440h+var_450]
0x180025a6b  test    rcx, rcx
0x180025a6e  jz      short loc_180025A75
0x180025a70  call    KerbFree
0x180025a75  lea     rcx, [rbp+440h+var_298]
0x180025a7c  call    KerbFreeString
0x180025a81  lea     rcx, [rbp+440h+var_288]
0x180025a88  call    KerbFreeString
0x180025a8d  cmp     dword ptr [rbp+440h+var_2E8+8], 1
0x180025a94  jnz     loc_180028490
0x180025a9a  mov     rcx, qword ptr [rbp+440h+var_2D8+8]
0x180025aa1  test    rcx, rcx
0x180025aa4  jz      loc_18002849C
0x180025aaa  mov     eax, dword ptr [rbp+440h+var_2D8]
0x180025ab0  test    rax, rax
0x180025ab3  jz      short loc_180025AC8
0x180025ab5  mov     [rcx], r14b
0x180025ab8  inc     rcx
0x180025abb  sub     rax, 1
0x180025abf  jnz     short loc_180025AB5
0x180025ac1  mov     rcx, qword ptr [rbp+440h+var_2D8+8]
0x180025ac8  call    KerbFree
0x180025acd  jmp     loc_18002849C
0x180025ad2  mov     ecx, 10h; size
0x180025ad7  call    MIDL_user_allocate
0x180025adc  mov     rcx, [rbp+440h+var_300]
0x180025ae3  mov     [rcx], rax
0x180025ae6  xor     ecx, ecx
0x180025ae8  test    rax, rax
0x180025aeb  jnz     short loc_180025AF7
0x180025aed  mov     edi, 0C000009Ah
0x180025af2  jmp     loc_1800259C2
0x180025af7  mov     [rax+8], rcx
0x180025afb  mov     ecx, 10h; size
0x180025b00  call    MIDL_user_allocate
0x180025b05  mov     rcx, [rbp+440h+var_328]
0x180025b0c  mov     [rcx], rax
0x180025b0f  xor     r8d, r8d
0x180025b12  test    rax, rax
0x180025b15  jz      short loc_180025AED
0x180025b17  mov     [rax+8], r8
0x180025b1b  mov     qword ptr [rbp+440h+LocallyUniqueId.LowPart], r8
0x180025b1f  mov     eax, r8d
0x180025b22  mov     rcx, qword ptr [rbp+440h+var_370]
0x180025b29  mov     [rcx], rax
0x180025b2c  mov     ecx, esi
0x180025b2e  lea     eax, [r8+2]
0x180025b32  sub     ecx, eax
0x180025b34  jz      short loc_180025B82
0x180025b36  sub     ecx, 1
0x180025b39  jz      short loc_180025B82
0x180025b3b  sub     ecx, 1
0x180025b3e  jz      short loc_180025B82
0x180025b40  sub     ecx, 1
0x180025b43  jz      short loc_180025B82
0x180025b45  sub     ecx, 3
0x180025b48  jz      short loc_180025B82
0x180025b4a  sub     ecx, eax
0x180025b4c  jz      short loc_180025B82
0x180025b4e  cmp     ecx, 1
0x180025b51  jz      short loc_180025B82
0x180025b53  mov     edi, 0C000010Bh
0x180025b58  mov     ebx, [rbp+440h+var_4C0]
0x180025b5b  mov     dword ptr [rsp+570h+Size], ebx
0x180025b5f  lea     r9, aInvalidLogonTy; "Invalid logon type passed to LsaApLogon"...
0x180025b66  mov     r8d, 2BE8h
0x180025b6c  lea     rdx, aKerbilogonuser; "KerbILogonUserEx3"
0x180025b73  mov     ecx, 1
0x180025b78  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180025b7d  jmp     loc_1800259C5
0x180025b82  mov     r12, [rbp+440h+var_448]
0x180025b86  mov     ecx, [rbp+440h+arg_20]
0x180025b8c  cmp     ecx, 4
0x180025b8f  jnb     short loc_180025B9B
0x180025b91  mov     edi, 0C000000Dh
0x180025b96  jmp     loc_1800259C2
0x180025b9b  mov     [rbp+440h+var_4A0], r8b
0x180025b9f  mov     dword ptr [rbp+440h+var_478], r8d
0x180025ba3  mov     r13, r8
0x180025ba6  cmp     dword ptr [r12], 201h
0x180025bae  jnz     loc_180025F3F
0x180025bb4  cmp     ecx, 30h ; '0'
0x180025bb7  jnb     short loc_180025BE9
0x180025bb9  mov     dword ptr [rsp+570h+Size], ecx
0x180025bbd  mov     r8d, 2780h
0x180025bc3  lea     r9, aSubmitBufferTo; "Submit buffer to logon too small: %d"
0x180025bca  lea     rdx, aKerbilogonuser; "KerbILogonUserEx3"
0x180025bd1  mov     ecx, 1
0x180025bd6  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180025bdb  mov     edi, 0C000000Dh
0x180025be0  mov     r13, [rbp+440h+var_4A8]
0x180025be4  jmp     loc_1800259C2
0x180025be9  mov     edx, [r12+1Ch]
0x180025bee  cmp     ecx, edx
0x180025bf0  jbe     loc_180025F14
0x180025bf6  mov     eax, ecx
0x180025bf8  sub     eax, edx
0x180025bfa  cmp     eax, 1Ch
0x180025bfd  jb      loc_180025F14
0x180025c03  lea     rsi, [r12+rdx]
0x180025c07  mov     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_NGC
0x180025c0e  cmp     rax, [rsi+4]
0x180025c12  jnz     loc_180025DE9
0x180025c18  mov     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_NGC+8
0x180025c1f  cmp     rax, [rsi+0Ch]
0x180025c23  jnz     loc_180025DE9
0x180025c29  mov     [rbp+440h+SourceLuid], r8
0x180025c2d  lea     r9, [rbp+440h+var_3C0]; unsigned int *
0x180025c34  lea     r8, [rbp+440h+SourceLuid]; void **
0x180025c38  mov     edx, ecx; unsigned int
0x180025c3a  mov     rcx, r12; void *
  ... truncated ...
```
