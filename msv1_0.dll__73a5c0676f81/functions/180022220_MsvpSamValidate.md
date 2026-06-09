# MsvpSamValidate

- ea: `0x180022220`
- end: `0x180024bca`
- name: `MsvpSamValidate`
- size: `10666`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, int, const UNICODE_STRING *, PUNICODE_STRING DomainName2, PSID Sid, unsigned int, PUNICODE_STRING DomainName1, int, int, _QWORD *, char *, _BYTE *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021070`

## callees

- `0x1800132c0`
- `0x180020270`
- `0x180021734`
- `0x180022220`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x18002fb90`
- `0x180030844`
- `0x18003536c`
- `0x180035824`
- `0x180035868`
- `0x180035de0`
- `0x180035ff8`
- `0x180036c38`
- `0x180040338`
- `0x180048754`
- `0x180050e28`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024b17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024b29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024b6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024b17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024b29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024b6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023fb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023fb7`
- `ntdll!NtQuerySystemTime` at `0x180022612`
- `ntdll!NtQuerySystemTime` at `0x180022612`
- `ntdll!RtlInitializeSid` at `0x1800226fd`
- `ntdll!RtlInitializeSid` at `0x1800226fd`
- `ntdll!RtlSubAuthoritySid` at `0x180022739`
- `ntdll!RtlSubAuthoritySid` at `0x180022747`
- `ntdll!RtlSubAuthoritySid` at `0x180022766`
- `ntdll!RtlSubAuthoritySid` at `0x180022739`
- `ntdll!RtlSubAuthoritySid` at `0x180022747`
- `ntdll!RtlSubAuthoritySid` at `0x180022766`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800226aa`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800226aa`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002269d`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002269d`
- `ntdll!RtlLengthSid` at `0x180023e96`
- `ntdll!RtlLengthSid` at `0x18002415f`
- `ntdll!RtlLengthSid` at `0x18002417d`
- `ntdll!RtlLengthSid` at `0x18002420c`
- `ntdll!RtlLengthSid` at `0x180023e96`
- `ntdll!RtlLengthSid` at `0x18002415f`
- `ntdll!RtlLengthSid` at `0x18002417d`
- `ntdll!RtlLengthSid` at `0x18002420c`
- `ntdll!RtlLengthRequiredSid` at `0x1800226b7`
- `ntdll!RtlLengthRequiredSid` at `0x1800226b7`
- `ntdll!RtlDowncaseUnicodeString` at `0x18002340b`
- `ntdll!RtlDowncaseUnicodeString` at `0x180023505`
- `ntdll!RtlDowncaseUnicodeString` at `0x18002340b`
- `ntdll!RtlDowncaseUnicodeString` at `0x180023505`
- `ntdll!RtlEqualSid` at `0x180022aad`
- `ntdll!RtlEqualSid` at `0x180022aad`
- `ntdll!WinSqmIncrementDWORD` at `0x180023967`
- `ntdll!WinSqmIncrementDWORD` at `0x180023a6d`
- `ntdll!WinSqmIncrementDWORD` at `0x180023b70`
- `ntdll!WinSqmIncrementDWORD` at `0x180023c6f`
- `ntdll!WinSqmIncrementDWORD` at `0x180023d56`
- `ntdll!WinSqmIncrementDWORD` at `0x180023967`
- `ntdll!WinSqmIncrementDWORD` at `0x180023a6d`
- `ntdll!WinSqmIncrementDWORD` at `0x180023b70`
- `ntdll!WinSqmIncrementDWORD` at `0x180023c6f`
- `ntdll!WinSqmIncrementDWORD` at `0x180023d56`
- `ntdll!RtlCopyUnicodeString` at `0x180024269`
- `ntdll!RtlCopyUnicodeString` at `0x1800242ba`
- `ntdll!RtlCopyUnicodeString` at `0x1800242fa`
- `ntdll!RtlCopyUnicodeString` at `0x180024343`
- `ntdll!RtlCopyUnicodeString` at `0x180024386`
- `ntdll!RtlCopyUnicodeString` at `0x1800243c9`
- `ntdll!RtlCopyUnicodeString` at `0x18002441e`
- `ntdll!RtlCopyUnicodeString` at `0x180024456`
- `ntdll!RtlCopyUnicodeString` at `0x1800244aa`
- `ntdll!RtlCopyUnicodeString` at `0x1800244e2`
- `ntdll!RtlCopyUnicodeString` at `0x180024531`
- `ntdll!RtlCopyUnicodeString` at `0x1800245a0`
- `ntdll!RtlCopyUnicodeString` at `0x1800245f3`
- `ntdll!RtlCopyUnicodeString` at `0x18002463e`
- `ntdll!RtlCopyUnicodeString` at `0x1800246ae`
- `ntdll!RtlCopyUnicodeString` at `0x180024736`
- `ntdll!RtlCopyUnicodeString` at `0x180024786`
- `ntdll!RtlCopyUnicodeString` at `0x180024269`
- `ntdll!RtlCopyUnicodeString` at `0x1800242ba`
- `ntdll!RtlCopyUnicodeString` at `0x1800242fa`
- `ntdll!RtlCopyUnicodeString` at `0x180024343`
- `ntdll!RtlCopyUnicodeString` at `0x180024386`
- `ntdll!RtlCopyUnicodeString` at `0x1800243c9`
- `ntdll!RtlCopyUnicodeString` at `0x18002441e`
- `ntdll!RtlCopyUnicodeString` at `0x180024456`
- `ntdll!RtlCopyUnicodeString` at `0x1800244aa`
- `ntdll!RtlCopyUnicodeString` at `0x1800244e2`
- `ntdll!RtlCopyUnicodeString` at `0x180024531`
- `ntdll!RtlCopyUnicodeString` at `0x1800245a0`
- `ntdll!RtlCopyUnicodeString` at `0x1800245f3`
- `ntdll!RtlCopyUnicodeString` at `0x18002463e`
- `ntdll!RtlCopyUnicodeString` at `0x1800246ae`
- `ntdll!RtlCopyUnicodeString` at `0x180024736`
- `ntdll!RtlCopyUnicodeString` at `0x180024786`
- `ntdll!RtlEqualDomainName` at `0x18002246a`
- `ntdll!RtlEqualDomainName` at `0x18002246a`
- `ntdll!RtlReleaseResource` at `0x1800224e6`
- `ntdll!RtlReleaseResource` at `0x180023fd9`
- `ntdll!RtlReleaseResource` at `0x1800246fc`
- `ntdll!RtlReleaseResource` at `0x1800224e6`
- `ntdll!RtlReleaseResource` at `0x180023fd9`
- `ntdll!RtlReleaseResource` at `0x1800246fc`
- `ntdll!RtlAcquireResourceShared` at `0x180022485`
- `ntdll!RtlAcquireResourceShared` at `0x180023f35`
- `ntdll!RtlAcquireResourceShared` at `0x180022485`
- `ntdll!RtlAcquireResourceShared` at `0x180023f35`
- `ntdll!RtlFreeUnicodeString` at `0x1800234c1`
- `ntdll!RtlFreeUnicodeString` at `0x1800235b1`
- `ntdll!RtlFreeUnicodeString` at `0x1800234c1`
- `ntdll!RtlFreeUnicodeString` at `0x1800235b1`
- `ntdll!RtlInitUnicodeString` at `0x1800225f9`
- `ntdll!RtlInitUnicodeString` at `0x180022605`
- `ntdll!RtlInitUnicodeString` at `0x1800231ce`
- `ntdll!RtlInitUnicodeString` at `0x1800231df`
- `ntdll!RtlInitUnicodeString` at `0x1800231f0`
- `ntdll!RtlInitUnicodeString` at `0x180023201`
- `ntdll!RtlInitUnicodeString` at `0x180023212`
- `ntdll!RtlInitUnicodeString` at `0x180023223`
- `ntdll!RtlInitUnicodeString` at `0x180023f51`
- `ntdll!RtlInitUnicodeString` at `0x180024284`
- `ntdll!RtlInitUnicodeString` at `0x1800242d5`
- `ntdll!RtlInitUnicodeString` at `0x180024315`
- `ntdll!RtlInitUnicodeString` at `0x180024361`
- `ntdll!RtlInitUnicodeString` at `0x1800243a1`
- `ntdll!RtlInitUnicodeString` at `0x1800243e4`
- `ntdll!RtlInitUnicodeString` at `0x180024470`
- `ntdll!RtlInitUnicodeString` at `0x1800244fc`
- `ntdll!RtlInitUnicodeString` at `0x18002454c`
- `ntdll!RtlInitUnicodeString` at `0x1800245bb`
- `ntdll!RtlInitUnicodeString` at `0x1800245d0`
- `ntdll!RtlInitUnicodeString` at `0x18002460e`
- `ntdll!RtlInitUnicodeString` at `0x180024659`
- `ntdll!RtlInitUnicodeString` at `0x1800246cc`
- `ntdll!RtlInitUnicodeString` at `0x18002474d`
- `ntdll!RtlInitUnicodeString` at `0x18002479d`
- `ntdll!RtlInitUnicodeString` at `0x1800225f9`
- `ntdll!RtlInitUnicodeString` at `0x180022605`
- `ntdll!RtlInitUnicodeString` at `0x1800231ce`
- `ntdll!RtlInitUnicodeString` at `0x1800231df`
- `ntdll!RtlInitUnicodeString` at `0x1800231f0`
- `ntdll!RtlInitUnicodeString` at `0x180023201`
- `ntdll!RtlInitUnicodeString` at `0x180023212`
- `ntdll!RtlInitUnicodeString` at `0x180023223`
- `ntdll!RtlInitUnicodeString` at `0x180023f51`
- `ntdll!RtlInitUnicodeString` at `0x180024284`
- `ntdll!RtlInitUnicodeString` at `0x1800242d5`
- `ntdll!RtlInitUnicodeString` at `0x180024315`
- `ntdll!RtlInitUnicodeString` at `0x180024361`
- `ntdll!RtlInitUnicodeString` at `0x1800243a1`
- `ntdll!RtlInitUnicodeString` at `0x1800243e4`
- `ntdll!RtlInitUnicodeString` at `0x180024470`
- `ntdll!RtlInitUnicodeString` at `0x1800244fc`
- `ntdll!RtlInitUnicodeString` at `0x18002454c`
- `ntdll!RtlInitUnicodeString` at `0x1800245bb`
- `ntdll!RtlInitUnicodeString` at `0x1800245d0`
- `ntdll!RtlInitUnicodeString` at `0x18002460e`
- `ntdll!RtlInitUnicodeString` at `0x180024659`
- `ntdll!RtlInitUnicodeString` at `0x1800246cc`
- `ntdll!RtlInitUnicodeString` at `0x18002474d`
- `ntdll!RtlInitUnicodeString` at `0x18002479d`
- `DNSAPI!DnsNameCompare_W` at `0x18002255f`
- `DNSAPI!DnsNameCompare_W` at `0x18002255f`
- `SAMLIB!SamFreeMemory` at `0x180022bc9`
- `SAMLIB!SamFreeMemory` at `0x180022e84`
- `SAMLIB!SamFreeMemory` at `0x180022bc9`
- `SAMLIB!SamFreeMemory` at `0x180022e84`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180024a95`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180024a95`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180023829`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180024ac7`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180023829`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180024ac7`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18002383e`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180024aa4`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18002383e`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180024aa4`
- `SAMSRV!SamrCloseHandle` at `0x18002384f`
- `SAMSRV!SamrCloseHandle` at `0x180024b05`
- `SAMSRV!SamrCloseHandle` at `0x18002384f`
- `SAMSRV!SamrCloseHandle` at `0x180024b05`
- `SAMSRV!SamrSetInformationUser` at `0x180024804`
- `SAMSRV!SamrSetInformationUser` at `0x180024804`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x1800228b2`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180023791`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x1800228b2`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180023791`
- `SAMSRV!SamIFreeVoid` at `0x180024ab6`
- `SAMSRV!SamIFreeVoid` at `0x180024ab6`
- `SAMSRV!SamIAccountRestrictions` at `0x180023144`
- `SAMSRV!SamIAccountRestrictions` at `0x180023144`
- `SAMSRV!SamIUPNFromUserHandle` at `0x18002291d`
- `SAMSRV!SamIUPNFromUserHandle` at `0x18002291d`
- `SAMSRV!SamrQueryInformationDomain` at `0x180022b69`
- `SAMSRV!SamrQueryInformationDomain` at `0x180022e53`
- `SAMSRV!SamrQueryInformationDomain` at `0x180022b69`
- `SAMSRV!SamrQueryInformationDomain` at `0x180022e53`
- `SAMSRV!SamIFree_SAMPR_RETURNED_USTRING_ARRAY` at `0x180024a88`
- `SAMSRV!SamIFree_SAMPR_RETURNED_USTRING_ARRAY` at `0x180024a88`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x1800249bb`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x1800249bb`
- `CRYPTSP!SystemFunction007` at `0x180023478`
- `CRYPTSP!SystemFunction007` at `0x180023572`
- `CRYPTSP!SystemFunction007` at `0x180023478`
- `CRYPTSP!SystemFunction007` at `0x180023572`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-1!GetConfigurationInfo` at `0x180022997`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-1!GetConfigurationInfo` at `0x180022997`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x1800236f9`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x180023e6b`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x18002497b`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x1800236f9`

## pseudocode

```c
__int64 __fastcall MsvpSamValidate(
        __int64 a1,
        unsigned __int8 a2,
        int a3,
        const UNICODE_STRING *a4,
        PUNICODE_STRING DomainName2,
        PSID Sid,
        unsigned int a7,
        PUNICODE_STRING DomainName1,
        int a9,
        int a10,
        _QWORD *a11,
        char *a12,
        _BYTE *a13)
{
  PUNICODE_STRING v13; // rsi
  __int128 v14; // xmm6
  PSID v15; // rdi
  int v17; // eax
  char v18; // bl
  __int64 v20; // rbx
  __int64 v21; // rdi
  unsigned int Length; // esi
  size_t v23; // r8
  WCHAR *v24; // rdx
  size_t v25; // r8
  int v26; // edx
  ULONG v27; // r14d
  struct _SID_IDENTIFIER_AUTHORITY *v28; // rbx
  ULONG v29; // eax
  USHORT v30; // r12
  void *v31; // rax
  void *v32; // rdi
  __int64 v33; // r12
  char *v34; // r13
  NTSTATUS v35; // r15d
  unsigned __int8 v36; // si
  PSID v37; // r12
  void *v38; // r15
  PULONG v39; // rdi
  PULONG v40; // rax
  PULONG v41; // rax
  PWSTR Buffer; // r8
  unsigned int v43; // r10d
  __m128i v44; // xmm1
  int v45; // eax
  unsigned int v46; // ebx
  __int64 v47; // rcx
  int v48; // eax
  __int64 v49; // r9
  __int64 v50; // r12
  char v51; // al
  int v52; // edx
  int v53; // edi
  char v54; // r14
  int v55; // eax
  struct _UNICODE_STRING *v56; // r9
  struct _UNICODE_STRING *v57; // rdx
  struct _UNICODE_STRING *v58; // r8
  PSID v59; // rbx
  void *v60; // rcx
  unsigned int v61; // ebx
  int v62; // ecx
  char v63; // si
  unsigned int v64; // r8d
  int v65; // eax
  struct _UNICODE_STRING *v66; // rdx
  int v67; // ebx
  bool v68; // zf
  unsigned int v69; // ebx
  int MaximumLength_high; // edi
  __int64 v71; // rcx
  __int64 v72; // rax
  __int64 (__fastcall *v73)(_QWORD, PUNICODE_STRING, _QWORD, __int64, int *, unsigned int *, char *, __int64 *, __int64 *); // rax
  __int64 v74; // r9
  __int64 v75; // rdi
  unsigned int v76; // ebx
  __int64 v77; // rax
  __int64 (__fastcall *v78)(_QWORD, PUNICODE_STRING, _QWORD, __int64, __int64, __int128 *, int *); // rax
  char *v79; // rcx
  int v80; // edx
  int v81; // ebx
  __int64 v82; // rsi
  __int64 v83; // rcx
  __m128i v84; // xmm0
  __int16 v85; // cx
  _WORD *v86; // xmm0_8
  int v87; // eax
  unsigned int v88; // ebx
  int v89; // eax
  PCWSTR *v90; // r13
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 (__fastcall *v93)(_QWORD, __int64, _QWORD, __int64, int *, unsigned int *, char *, __int64 *, __int64 *); // rax
  int v94; // eax
  unsigned __int16 v95; // dx
  __int64 v96; // rbx
  char v97; // r8
  __int64 j; // rdx
  char v99; // cl
  char v100; // al
  int v101; // eax
  unsigned __int16 v102; // dx
  __int64 v103; // rbx
  char v104; // r8
  __int64 i; // rdx
  char v106; // cl
  char v107; // al
  int v108; // eax
  char v109; // r8
  __int64 k; // rdx
  char v111; // cl
  char v112; // al
  char v113; // r8
  __int64 m; // rdx
  char v115; // cl
  char v116; // al
  int v117; // eax
  __int64 v118; // rdx
  __int64 v119; // rax
  unsigned __int64 v120; // rcx
  __int64 v121; // rdx
  unsigned int v122; // ecx
  __int64 v123; // r8
  int v124; // eax
  unsigned int v125; // eax
  __int64 v126; // rdx
  unsigned int v127; // ecx
  __int64 v128; // r8
  int v129; // eax
  unsigned int v130; // eax
  __int64 v131; // rdx
  unsigned int v132; // ecx
  __int64 v133; // r8
  int v134; // eax
  unsigned int v135; // eax
  __int64 v136; // rdx
  unsigned int v137; // ecx
  __int64 v138; // r8
  int v139; // eax
  unsigned int v140; // eax
  unsigned int v141; // ecx
  __int64 v142; // r8
  int v143; // eax
  unsigned int v144; // eax
  char v145; // di
  char *v146; // r14
  unsigned int v147; // r13d
  __int64 v148; // rcx
  __int64 v149; // rcx
  ULONG v150; // eax
  int v151; // ebx
  int v152; // eax
  int v153; // eax
  char v154; // al
  SIZE_T v155; // rbx
  char *v156; // rax
  char *v157; // rdi
  int v158; // eax
  int v159; // eax
  __int128 v160; // xmm0
  int v161; // eax
  int v162; // eax
  __int64 v163; // rax
  __int64 v164; // xmm0_8
  void *v165; // rdx
  __int64 v166; // rbx
  char *v167; // rbx
  PSID v168; // rdi
  ULONG v169; // eax
  char *v170; // r13
  int v171; // ecx
  unsigned int v172; // r12d
  __int64 v173; // rax
  __int64 v174; // rdi
  __int64 v175; // rsi
  size_t v176; // rbx
  UNICODE_STRING *v177; // rbx
  struct _UNICODE_STRING *v178; // rcx
  __int64 v179; // rcx
  struct _UNICODE_STRING *v180; // rcx
  __int64 v181; // rcx
  struct _UNICODE_STRING *v182; // rcx
  __int64 v183; // rcx
  struct _UNICODE_STRING *v184; // rcx
  __int64 v185; // rcx
  struct _UNICODE_STRING *v186; // rcx
  __int64 v187; // rcx
  struct _UNICODE_STRING *v188; // rcx
  __int64 v189; // rcx
  struct _UNICODE_STRING *v190; // rcx
  __int64 v191; // rcx
  PCUNICODE_STRING v192; // rdi
  __int64 v193; // rcx
  struct _UNICODE_STRING *v194; // rcx
  __int64 v195; // rcx
  PCUNICODE_STRING v196; // rdi
  __int64 v197; // rcx
  struct _UNICODE_STRING *v198; // rcx
  __int64 v199; // rcx
  __int16 v200; // ax
  __int64 v201; // rcx
  WCHAR *v202; // rbx
  __int64 v203; // rcx
  __int64 v204; // rcx
  __int16 v205; // ax
  __int16 v206; // ax
  __int64 v207; // rcx
  int v208; // eax
  struct _UNICODE_STRING *v209; // rcx
  struct _UNICODE_STRING *v210; // rcx
  int v211; // ebx
  int v212; // eax
  __int128 v213; // xmm0
  const char *v214; // rcx
  const char *v215; // rax
  int InteractiveLogonInfoEnabled; // eax
  NTSTATUS v217; // ebx
  __int64 v218; // rdi
  __int64 v219; // rdx
  char v220[8]; // [rsp+70h] [rbp-90h] BYREF
  PSID SourceSid; // [rsp+78h] [rbp-88h]
  char v222; // [rsp+80h] [rbp-80h]
  unsigned __int8 v223; // [rsp+81h] [rbp-7Fh]
  char v224[6]; // [rsp+82h] [rbp-7Eh] BYREF
  PUNICODE_STRING v225; // [rsp+88h] [rbp-78h]
  unsigned __int8 v226; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v227; // [rsp+91h] [rbp-6Fh]
  char *v228; // [rsp+98h] [rbp-68h]
  unsigned int v229; // [rsp+A0h] [rbp-60h] BYREF
  int v230; // [rsp+A4h] [rbp-5Ch] BYREF
  UNICODE_STRING v231; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING UniDest; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 v233; // [rsp+C8h] [rbp-38h]
  __int64 v234; // [rsp+D0h] [rbp-30h] BYREF
  int v235; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v236; // [rsp+E0h] [rbp-20h] BYREF
  int v237; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v238; // [rsp+F0h] [rbp-10h] BYREF
  struct _UNICODE_STRING v239; // [rsp+F8h] [rbp-8h] BYREF
  int v240; // [rsp+108h] [rbp+8h] BYREF
  int v241; // [rsp+10Ch] [rbp+Ch]
  __int64 v242; // [rsp+110h] [rbp+10h] BYREF
  __int64 v243; // [rsp+118h] [rbp+18h] BYREF
  struct _UNICODE_STRING v244; // [rsp+120h] [rbp+20h] BYREF
  __int64 v245; // [rsp+130h] [rbp+30h] BYREF
  __int64 v246; // [rsp+138h] [rbp+38h]
  __int64 v247; // [rsp+140h] [rbp+40h] BYREF
  PCUNICODE_STRING v248[2]; // [rsp+148h] [rbp+48h] BYREF
  void *v249; // [rsp+158h] [rbp+58h]
  PCUNICODE_STRING v250[2]; // [rsp+160h] [rbp+60h] BYREF
  _DWORD v251[2]; // [rsp+170h] [rbp+70h] BYREF
  void *Src; // [rsp+178h] [rbp+78h]
  struct _UNICODE_STRING DestinationString; // [rsp+180h] [rbp+80h] BYREF
  __int64 DomainRelativeSid; // [rsp+190h] [rbp+90h]
  _DWORD v255[2]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v256; // [rsp+1A0h] [rbp+A0h]
  __m128i v257; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE *v258; // [rsp+1B8h] [rbp+B8h]
  HLOCAL hMem; // [rsp+1C0h] [rbp+C0h]
  __int64 v260; // [rsp+1C8h] [rbp+C8h]
  union _LARGE_INTEGER SystemTime; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v262; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v263; // [rsp+1E0h] [rbp+E0h]
  __int64 v264; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v265; // [rsp+1F0h] [rbp+F0h]
  __int128 v266; // [rsp+1F8h] [rbp+F8h]
  __int64 v267; // [rsp+208h] [rbp+108h]
  _QWORD *v268; // [rsp+210h] [rbp+110h]
  __int128 v269; // [rsp+218h] [rbp+118h] BYREF
  __int64 v270; // [rsp+228h] [rbp+128h]
  struct _UNICODE_STRING v271; // [rsp+230h] [rbp+130h] BYREF
  struct _UNICODE_STRING v272; // [rsp+240h] [rbp+140h] BYREF
  struct _UNICODE_STRING v273; // [rsp+250h] [rbp+150h] BYREF
  struct _UNICODE_STRING v274; // [rsp+260h] [rbp+160h] BYREF
  struct _UNICODE_STRING v275; // [rsp+270h] [rbp+170h] BYREF
  struct _UNICODE_STRING v276; // [rsp+280h] [rbp+180h] BYREF
  __int64 v277; // [rsp+290h] [rbp+190h]
  __int128 v278; // [rsp+2A0h] [rbp+1A0h] BYREF
  UNICODE_STRING SourceString; // [rsp+2B0h] [rbp+1B0h] BYREF
  UNICODE_STRING v280; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v281; // [rsp+2D0h] [rbp+1D0h]
  __int128 v282; // [rsp+2E0h] [rbp+1E0h]
  struct _UNICODE_STRING v283; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int64 v284; // [rsp+300h] [rbp+200h] BYREF
  __int128 v285; // [rsp+308h] [rbp+208h] BYREF
  WCHAR pName2[424]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR pName1[2]; // [rsp+670h] [rbp+570h] BYREF
  __int128 v288; // [rsp+688h] [rbp+588h]

  v13 = DomainName1;
  v14 = 0;
  v15 = Sid;
  v268 = a11;
  *(_QWORD *)&v244.Length = a1;
  v258 = a13;
  LODWORD(v263) = 0;
  LODWORD(v265) = 0;
  LODWORD(v246) = 0;
  v262 = 0;
  v264 = 0;
  v245 = 0;
  v250[0] = a4;
  v233 = a2;
  v228 = a12;
  v225 = DomainName1;
  SourceSid = Sid;
  v238 = 0;
  v243 = 0;
  v251[1] = 0;
  v230 = 0;
  v285 = 0;
  v284 = 0;
  v237 = 0;
  v239 = 0;
  SystemTime.QuadPart = 0;
  v257 = 0;
  v247 = 0;
  v242 = 0;
  DestinationString = 0;
  *(_QWORD *)&v283.Length = 0;
  v255[1] = 0;
  v240 = 0;
  v278 = 0;
  v235 = 0;
  SourceString = 0;
  v223 = 0;
  v280 = 0;
  v226 = 0;
  v281 = 0;
  v227 = 0;
  v282 = 0;
  v220[0] = 0;
  v266 = 0;
  v267 = 0;
  hMem = 0;
  *(_QWORD *)&UniDest.Length = 0;
  v271 = 0;
  v277 = 0;
  v272 = 0;
  v270 = 0;
  v273 = 0;
  v274 = 0;
  v275 = 0;
  v276 = 0;
  v269 = 0;
  if ( (unsigned int)Feature_ID57824352__private_IsEnabledDeviceUsageNoInline() )
    ((void (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v269);
  v17 = *(_DWORD *)&DomainName1[1].Length;
  if ( (v17 & 0x80000) != 0 )
  {
    if ( a9 || !NlpWorkstation || a3 != 1 || a7 != 2 || !DomainName2 || !DomainName2->Length )
    {
      *a12 = 1;
      return 3221225485LL;
    }
    v18 = 1;
    v224[0] = 1;
    v248[0] = &NlpSamDomainName;
    goto LABEL_31;
  }
  v18 = 0;
  v248[0] = DomainName2;
  v224[0] = 0;
  if ( (v17 & 0x400) == 0 || !DomainName1->Length || (v17 & 0x8000) != 0 || RtlEqualDomainName(DomainName1, DomainName2) )
    goto LABEL_31;
  v20 = 0;
  v21 = 0;
  RtlAcquireResourceShared(&NtLmGlobalCritSect, 1u);
  if ( NlpWorkstation )
  {
    Length = NtLmGlobalUnicodeDnsComputerNameString.Length;
    v23 = NtLmGlobalUnicodeDnsComputerNameString.Length;
    if ( (unsigned __int64)NtLmGlobalUnicodeDnsComputerNameString.Length + 2 <= 0x200 )
    {
      v24 = &NtLmGlobalUnicodeDnsComputerName;
LABEL_21:
      memcpy_0(pName1, v24, v23);
      v20 = Length >> 1;
    }
  }
  else
  {
    Length = NtLmGlobalUnicodeDnsDomainNameString.Length;
    v23 = NtLmGlobalUnicodeDnsDomainNameString.Length;
    if ( (unsigned __int64)NtLmGlobalUnicodeDnsDomainNameString.Length + 2 <= 0x200 )
    {
      v24 = &NtLmGlobalUnicodeDnsDomainName;
      goto LABEL_21;
    }
  }
  RtlReleaseResource(&NtLmGlobalCritSect);
  v13 = v225;
  v25 = v225->Length;
  if ( v25 + 2 <= 0x200 )
  {
    v21 = (unsigned int)v25 >> 1;
    memcpy_0(pName2, v225->Buffer, v25);
  }
  if ( (_DWORD)v20 && (_DWORD)v21 )
  {
    if ( (unsigned __int64)(2 * v20) >= 0x200 || (pName1[v20] = 0, (unsigned __int64)(2 * v21) >= 0x200) )
      _report_rangecheckfailure();
    pName2[v21] = 0;
    if ( !DnsNameCompare_W(pName1, pName2) )
    {
      *a12 = 0;
      return 3221225572LL;
    }
  }
  v15 = SourceSid;
  v18 = 0;
LABEL_31:
  LODWORD(v262) = 0;
  v282 = 0;
  DWORD2(v282) = 0;
  *v258 = 0;
  v263 = 0;
  LODWORD(v264) = 0;
  v265 = 0;
  LODWORD(v245) = 0;
  v246 = 0;
  v255[0] = 0;
  v256 = 0;
  v251[0] = 0;
  Src = 0;
  v278 = 0;
  LOBYTE(v282) = 1;
  SourceString = 0;
  v280 = 0;
  v281 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&v239, 0);
  NtQuerySystemTime(&SystemTime);
  LODWORD(v236) = 16;
  *a12 = 1;
  if ( a7 != 1 )
  {
    if ( a7 == 2 )
    {
      v26 = 472;
      if ( a3 != 1 )
        v26 = 464;
      LODWORD(v236) = v26;
    }
    else if ( a7 != 3 )
    {
      return 3221225475LL;
    }
  }
  if ( a10 != 2 && a10 != 3 && a10 != 6 )
    return 3221225475LL;
  v241 = 0;
  *(_QWORD *)&v231.Length = 0;
  v222 = 0;
  DomainRelativeSid = 0;
  v260 = 0;
  if ( a9 )
  {
    v27 = *RtlSubAuthorityCountSid(v15);
    v28 = RtlIdentifierAuthoritySid(v15);
    v29 = RtlLengthRequiredSid(v27 + 1);
    v30 = v29;
    LODWORD(v234) = v29;
    v31 = (void *)((__int64 (__fastcall *)(_QWORD))qword_180088390)(v29);
    v249 = v31;
    v32 = v31;
    if ( !v31 )
    {
      v33 = (__int64)v225;
      v34 = a12;
      *a12 = 0;
      v35 = -1073741670;
LABEL_400:
      v59 = SourceSid;
      goto LABEL_401;
    }
    v35 = RtlInitializeSid(v31, v28, v27 + 1);
    if ( v35 < 0 )
    {
      v34 = v228;
      v33 = (__int64)v225;
      *v228 = 0;
      goto LABEL_400;
    }
    v36 = 0;
    if ( (_BYTE)v27 )
    {
      v37 = SourceSid;
      v38 = v32;
      do
      {
        v39 = RtlSubAuthoritySid(v37, v36);
        v40 = RtlSubAuthoritySid(v38, v36++);
        *v40 = *v39;
      }
      while ( v36 < (unsigned __int8)v27 );
      v30 = v234;
      v32 = v38;
    }
    v41 = RtlSubAuthoritySid(v32, v27);
    Buffer = (PWSTR)v32;
    v13 = v225;
    v43 = 128;
    *v41 = a9;
    v239.Buffer = (PWSTR)v32;
    v239.Length = v30;
    v239.MaximumLength = v30;
  }
  else
  {
    v43 = 0;
    v68 = (*(_DWORD *)&v13[1].Length & 0x8000) == 0;
    v249 = 0;
    if ( v68 )
    {
      if ( v18 )
      {
        v44 = *(__m128i *)DomainName2;
        Buffer = DomainName2->Buffer;
        v43 = 0x4000;
      }
      else
      {
        v44 = (__m128i)v13[2];
        Buffer = v13[2].Buffer;
      }
    }
    else
    {
      v44 = *(__m128i *)v13;
      Buffer = v13->Buffer;
    }
    v239 = (struct _UNICODE_STRING)v44;
    v30 = _mm_cvtsi128_si32(v44);
  }
  v45 = *(_DWORD *)&v13[1].Length;
  v46 = a7;
  if ( (v45 & 0xFF100000) != 0 || a7 != 2 )
  {
    v45 &= ~0x20000u;
    *(_DWORD *)&v13[1].Length = v45;
  }
  if ( !v43 && (!v13->Buffer || !v13->Length) )
  {
    if ( NlpWorkstation )
    {
      if ( (v45 & 0x20000) != 0 )
      {
        v47 = 0;
        if ( v30 >> 1 )
        {
          while ( Buffer[v47] != 64 )
          {
            v47 = (unsigned int)(v47 + 1);
            if ( (unsigned int)v47 >= v30 >> 1 )
              goto LABEL_72;
          }
          v239.Length = 2 * v47;
        }
      }
    }
    else
    {
      v43 = 512;
    }
  }
LABEL_72:
  v33 = (__int64)v225;
  if ( (*(_DWORD *)&v225[1].Length & 0xFF100000) != 0 || NlpSubAuthZeroExists )
  {
    v48 = 33554688;
    if ( NlpWorkstation )
      v48 = 1048832;
    v49 = 0;
  }
  else
  {
    v48 = 0x2000000;
    v49 = 591392719;
    if ( NlpWorkstation )
      v48 = 0x100000;
  }
  v35 = SamIGetUserLogonInformation2(*(_QWORD *)&v244.Length, v43, &v239, v49, v48, 0, &v243, &v245, &v238);
  if ( v35 < 0 )
  {
    v34 = v228;
    v238 = 0;
    *v228 = 0;
    if ( v35 == -1073741275 || v35 == -1073741724 )
      goto LABEL_398;
    if ( v35 != -1073740943 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_02757a6cf13d311f0239b5d699c3efb5_Traceguids,
          (unsigned int)v35);
      if ( v35 != -1073741801 && v35 != -1073741670 )
      {
LABEL_398:
        if ( v35 != -1073741604 )
          v35 = -1073741724;
      }
    }
    goto LABEL_400;
  }
  v50 = v243;
  *(_QWORD *)&v231.Length = v243;
  if ( v224[0] && !*(_QWORD *)(v243 + 480) || a7 != 2 && *(_QWORD *)(v243 + 480) )
  {
    v35 = -1073741724;
LABEL_86:
    v34 = v228;
    v33 = (__int64)v225;
    goto LABEL_400;
  }
  v51 = NlpWorkstation;
  if ( !NlpWorkstation )
  {
    v224[0] = 0;
    SamIUPNFromUserHandle(v238, v224, &DestinationString);
    v51 = NlpWorkstation;
  }
  v52 = a9;
  if ( a9 )
    v239 = *(struct _UNICODE_STRING *)(v50 + 48);
  if ( ((unsigned int)v236 & *(_DWORD *)(v50 + 280)) == 0 )
  {
    v34 = v228;
    v35 = -1073741724;
    v33 = (__int64)v225;
    *v228 = 0;
    goto LABEL_400;
  }
  v53 = *(_DWORD *)(v50 + 272);
  v54 = 1;
  LODWORD(v234) = v53;
  if ( !v51 )
  {
    LODWORD(v236) = 0;
    v229 = 4;
    if ( (int)GetConfigurationInfo(2, &v229, &v236) >= 0 )
    {
      v55 = v236;
      dword_180086484 = v236;
    }
    else
    {
      v55 = dword_180086484;
      LODWORD(v236) = dword_180086484;
    }
    if ( v55 >= 6 && (v53 != 500 || a7 != 1 || (NtLmCheckProcessOption() & 2) == 0) )
    {
      if ( *(_QWORD *)(v243 + 592) && !*(_BYTE *)(v243 + 600) && !NtLmGlobalA2AFromPolicyBypass )
      {
        v56 = (struct _UNICODE_STRING *)(v243 + 552);
        v57 = v225 + 3;
        if ( *(_BYTE *)(v243 + 568) )
        {
          v34 = v228;
          v58 = (struct _UNICODE_STRING *)(v243 + 536);
          v35 = -1073741714;
          *v228 = 1;
          SspLogAuthEventCommon(&v239, v57, v58, v56, 1, 0);
          v33 = (__int64)v225;
          goto LABEL_400;
        }
        SspLogAuthEventCommon(&v239, v57, (struct _UNICODE_STRING *)(v243 + 536), v56, 1, 1);
      }
      v59 = SourceSid;
      DomainRelativeSid = NlpMakeDomainRelativeSid(SourceSid);
      v60 = (void *)DomainRelativeSid;
      if ( !DomainRelativeSid )
      {
        v34 = v228;
        v35 = -1073741670;
        v33 = (__int64)v225;
        *v228 = 0;
LABEL_401:
        v82 = *(_QWORD *)&v231.Length;
        goto LABEL_402;
      }
      v61 = 0;
      if ( (_DWORD)v245 )
      {
        while ( !RtlEqualSid(v60, *(PSID *)(v246 + 16LL * v61)) )
        {
          v60 = (void *)DomainRelativeSid;
          if ( ++v61 >= (unsigned int)v245 )
            goto LABEL_112;
        }
        v33 = (__int64)v225;
        v34 = v228;
        v35 = -1073741714;
        v66 = v225 + 3;
        *v228 = 1;
        SspLogAuthEventCommon(&v239, v66, 0, 0, 0, 0);
        goto LABEL_400;
      }
LABEL_112:
      v46 = a7;
    }
    v52 = a9;
  }
  v62 = *(_DWORD *)(v50 + 280);
  *(_DWORD *)&v283.Length = *(_DWORD *)(v50 + 24);
  v63 = (v62 & 0x1C0) != 0;
  *(_DWORD *)(&v283.MaximumLength + 1) = *(_DWORD *)(v50 + 28);
  v64 = *(_DWORD *)&v225[1].Length;
  v65 = v64 & 0x100000;
  if ( (v64 & 0xFF000000) != 0 )
  {
    if ( !v65 )
    {
      v229 = 0;
      if ( (v62 & 0x400) != 0 && a3 )
      {
        if ( v53 != 500 )
          goto LABEL_125;
        if ( v46 != 1 || (NtLmCheckProcessOption() & 2) == 0 )
        {
          v236 = 0;
          v35 = SamrQueryInformationDomain(*(_QWORD *)&v244.Length, 1, &v236);
          if ( v35 < 0 )
          {
            v34 = v228;
            v33 = (__int64)v225;
            *v228 = 1;
            goto LABEL_400;
          }
          v67 = *(_DWORD *)(v236 + 4);
          SamFreeMemory();
          if ( (v67 & 8) != 0 )
          {
LABEL_125:
            v68 = (*(_BYTE *)(v50 + 280) & 1) == 0;
            v35 = -1073741260;
            v34 = v228;
            v33 = (__int64)v225;
            if ( !v68 )
              v54 = v63;
            *v228 = v54;
            goto LABEL_400;
          }
        }
      }
      LODWORD(v236) = 0;
      v68 = a3 == 1;
      v34 = v228;
      v69 = !v68 | 2;
      if ( !a9 )
        v69 = !v68;
      MaximumLength_high = HIBYTE(v225[1].MaximumLength);
      v71 = HIBYTE(v225[1].MaximumLength);
      *v228 = 1;
      v72 = ReferenceSubAuth(v71, &v236);
      if ( !MaximumLength_high && !v72 )
      {
        NlpSubAuthZeroExists = 0;
        v35 = 0;
LABEL_143:
        v33 = (__int64)v225;
        if ( (v237 & 0xFFDFFFFF) != 0 )
        {
          v35 = -1073741595;
          *v34 = 1;
          goto LABEL_400;
        }
        v230 |= v229;
        v53 = v234;
        goto LABEL_235;
      }
      v35 = v236;
      if ( (_DWORD)v236 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_4dfae3304c4a345cf2ea5346cdf1ae07_Traceguids,
            (unsigned int)v236);
        v33 = (__int64)v225;
LABEL_142:
        if ( v35 < 0 )
          goto LABEL_400;
        goto LABEL_143;
      }
      v73 = *(__int64 (__fastcall **)(_QWORD, PUNICODE_STRING, _QWORD, __int64, int *, unsigned int *, char *, __int64 *, __int64 *))(v72 + 24);
      if ( v73 )
      {
        v74 = v50;
        v33 = (__int64)v225;
        v35 = v73(a7, v225, v69, v74, &v237, &v229, v34, &v247, &v242);
        goto LABEL_142;
      }
      if ( !MaximumLength_high )
      {
        NlpSubAuthZeroExists = 0;
        v35 = 0;
        goto LABEL_143;
      }
LABEL_155:
      v33 = (__int64)v225;
      v35 = -1073741702;
      goto LABEL_400;
    }
  }
  else if ( !v65 )
  {
    goto LABEL_159;
  }
  v75 = v238;
  v229 = 0;
  v76 = (a3 != 1) | 2;
  if ( !v52 )
    v76 = a3 != 1;
  v77 = ReferenceSubAuth(HIBYTE(v64), &v229);
  v35 = v229;
  if ( v229 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4dfae3304c4a345cf2ea5346cdf1ae07_Traceguids, v229);
  }
  else
  {
    v78 = *(__int64 (__fastcall **)(_QWORD, PUNICODE_STRING, _QWORD, __int64, __int64, __int128 *, int *))(v77 + 32);
    if ( !v78 )
    {
      v34 = v228;
      *v228 = v282;
      goto LABEL_155;
    }
    v35 = v78(a7, v225, v76, v50, v75, &v278, &v235);
  }
  v79 = v228;
  *v228 = v282;
  if ( v35 < 0 )
  {
    v33 = (__int64)v225;
    v34 = v79;
    goto LABEL_400;
  }
  v53 = v234;
  v222 = 1;
LABEL_159:
  v80 = v235;
  if ( (v235 & 0x80u) == 0 && (*(_DWORD *)(v50 + 280) & 0x400) != 0 && a3 )
  {
    if ( v53 != 500 )
      goto LABEL_125;
    if ( a7 != 1 || (NtLmCheckProcessOption() & 2) == 0 )
    {
      v234 = 0;
      v35 = SamrQueryInformationDomain(*(_QWORD *)&v244.Length, 1, &v234);
      if ( v35 < 0 )
      {
        v34 = v228;
        v33 = (__int64)v225;
        *v228 = 1;
        goto LABEL_400;
      }
      v81 = *(_DWORD *)(v234 + 4);
      SamFreeMemory();
      if ( (v81 & 8) != 0 )
        goto LABEL_125;
    }
    v80 = v235;
  }
  if ( (v80 & 2) != 0 || (*(_DWORD *)&v225[1].Length & 0x20000) != 0 )
  {
    v80 |= 0x20u;
    v235 = v80;
  }
  else if ( a3 )
  {
    if ( a7 != 2 && (*(_DWORD *)(v50 + 280) & 0x1000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_02757a6cf13d311f0239b5d699c3efb5_Traceguids, &v239);
      v34 = v228;
      v35 = -1073741062;
      v33 = (__int64)v225;
      goto LABEL_400;
    }
    v35 = MsvpValidateLogonWithUserPassword(
            v233,
            a7,
            (_DWORD)v225,
            *(_DWORD *)&v244.Length,
            v238,
            a9,
            v63,
            v243,
            (__int64)v220,
            (__int64)&v226,
            (__int64)&v230,
            (__int64)&v285,
            (__int64)&v284,
            (__int64)v228);
    v223 = v226;
    v227 = v220[0];
    if ( v35 < 0 )
      goto LABEL_86;
    LOBYTE(v80) = v235;
  }
  if ( (v80 & 1) == 0 )
  {
    if ( (!(unsigned int)Feature_ID57824352__private_IsEnabledDeviceUsageNoInline() || (DWORD2(v269) & 0x80000) == 0)
      && (*(_BYTE *)(v50 + 280) & 1) != 0 )
    {
      v34 = v228;
      v35 = -1073741710;
      v33 = (__int64)v225;
      *v228 = v63;
      goto LABEL_400;
    }
    LOBYTE(v80) = v235;
  }
  v82 = *(_QWORD *)&v231.Length;
  if ( v53 != 500 && (v80 & 0x10) == 0 )
  {
    v83 = *(unsigned int *)(*(_QWORD *)&v231.Length + 24LL);
    *(_DWORD *)(&v283.MaximumLength + 1) = *(_DWORD *)(*(_QWORD *)&v231.Length + 28LL);
    *(_DWORD *)&v283.Length = v83;
    if ( v83 | ((unsigned __int64)*(unsigned int *)(&v283.MaximumLength + 1) << 32) )
    {
      if ( SystemTime.QuadPart >= (__int64)(v83 | ((unsigned __int64)*(unsigned int *)(&v283.MaximumLength + 1) << 32)) )
      {
        v34 = v228;
        v35 = -1073741421;
        v33 = (__int64)v225;
        v59 = SourceSid;
        *v228 = 1;
        goto LABEL_402;
      }
    }
  }
  v33 = (__int64)v225;
  if ( (v80 & 0x20) == 0
    && (*(_DWORD *)&v225[1].Length & 0x20000) == 0
    && a3
    && SystemTime.QuadPart >= *(_QWORD *)(*(_QWORD *)&v231.Length + 40LL) )
  {
    if ( !*(_QWORD *)(*(_QWORD *)&v231.Length + 16LL) )
    {
      v34 = v228;
      v35 = -1073741276;
      v59 = SourceSid;
      *v228 = 1;
      goto LABEL_402;
    }
    if ( v53 != 500 )
    {
      v34 = v228;
      v35 = -1073741711;
      v59 = SourceSid;
      *v228 = 1;
      goto LABEL_402;
    }
    v35 = 0;
  }
  v84 = (__m128i)v225[3];
  v85 = _mm_cvtsi128_si32(v84);
  v257 = v84;
  if ( v85 )
  {
    v86 = (_WORD *)_mm_srli_si128(v84, 8).m128i_u64[0];
    if ( *v86 == 92 && v86[1] == 92 )
    {
      v257.m128i_i64[1] = (__int64)(v86 + 2);
      v257.m128i_i16[1] -= 4;
      v257.m128i_i16[0] = v85 - 4;
    }
  }
  v87 = *(_DWORD *)&v225[1].Length;
  if ( (v87 & 0x20000) == 0 || (v87 & 0x40000) != 0 )
  {
    v35 = SamIAccountRestrictions(
            v238,
            &v257,
            *(_QWORD *)&v231.Length + 160LL,
            *(_QWORD *)&v231.Length + 288LL,
            &v247,
            &v242);
    if ( v35 < 0 )
    {
      v34 = v228;
      v59 = SourceSid;
      *v228 = 1;
      goto LABEL_402;
    }
  }
  if ( !NlpSubAuthZeroExists )
  {
    v34 = v228;
    goto LABEL_235;
  }
  v229 = 0;
  *(_DWORD *)&v271.Length = 1;
  v88 = (a3 != 1) | 2;
  if ( !a9 )
    v88 = a3 != 1;
  v89 = MsvExtractTargetInfo(a7, v33, &UniDest, (unsigned int *)&v234);
  v90 = *(PCWSTR **)&UniDest.Length;
  hMem = *(HLOCAL *)&UniDest.Length;
  if ( v89 >= 0 && *(_QWORD *)&UniDest.Length )
  {
    RtlInitUnicodeString((PUNICODE_STRING)&v271.Buffer, *(PCWSTR *)(*(_QWORD *)&UniDest.Length + 8LL));
    RtlInitUnicodeString((PUNICODE_STRING)&v272.Buffer, v90[2]);
    RtlInitUnicodeString((PUNICODE_STRING)&v273.Buffer, v90[3]);
    RtlInitUnicodeString((PUNICODE_STRING)&v274.Buffer, v90[4]);
    RtlInitUnicodeString((PUNICODE_STRING)&v275.Buffer, v90[5]);
    RtlInitUnicodeString((PUNICODE_STRING)&v276.Buffer, v90[8]);
  }
  v91 = NlpMakeDomainRelativeSid(SourceSid);
  v34 = v228;
  v260 = v91;
  if ( !v91 )
  {
    v59 = SourceSid;
    v35 = -1073741670;
    *v228 = 0;
    goto LABEL_402;
  }
  v35 = Msv1_0SubAuthenticationRoutineZeroEx(a7, v33, (unsigned int)&v271, v88, 0, v91, (__int64)v228);
  if ( v35 < 0 )
    goto LABEL_389;
  if ( *(_DWORD *)(v33 + 16) < 0x1000000u )
  {
    LODWORD(v234) = 0;
    *v34 = 1;
    v92 = ReferenceSubAuth(0, &v234);
    if ( v92 )
    {
      v35 = v234;
      if ( (_DWORD)v234 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_4dfae3304c4a345cf2ea5346cdf1ae07_Traceguids,
            (unsigned int)v234);
      }
      else
      {
        v93 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, int *, unsigned int *, char *, __int64 *, __int64 *))(v92 + 24);
        if ( !v93 )
        {
          NlpSubAuthZeroExists = 0;
          v35 = 0;
          goto LABEL_231;
        }
        v35 = v93(a7, v33, v88, v82, &v237, &v229, v34, &v247, &v242);
      }
      if ( v35 < 0 )
        goto LABEL_389;
      goto LABEL_231;
    }
    NlpSubAuthZeroExists = 0;
    v35 = 0;
  }
  else
  {
    v35 = 0;
  }
LABEL_231:
  if ( (v237 & 0xFFDFFFFF) != 0 )
  {
    v59 = SourceSid;
    v35 = -1073741595;
    *v34 = 1;
    goto LABEL_402;
  }
  v230 |= v229;
LABEL_235:
  if ( *(_QWORD *)&v283.Length && v242 > *(__int64 *)&v283.Length )
    v242 = *(_QWORD *)&v283.Length;
  v82 = *(_QWORD *)&v231.Length;
  v94 = *(_DWORD *)(*(_QWORD *)&v231.Length + 280LL);
  if ( (v94 & 0x1C0) != 0 )
  {
    if ( (v94 & 0x40) != 0 )
    {
      v59 = SourceSid;
      v35 = -1073741416;
      *v34 = 1;
      goto LABEL_402;
    }
    if ( (v94 & 0x80u) == 0 )
    {
      if ( (v94 & 0x100) == 0 )
      {
        v35 = -1073741724;
        goto LABEL_289;
      }
      if ( (*(_BYTE *)(v33 + 16) & 0x20) == 0 )
      {
        v59 = SourceSid;
        v35 = -1073741414;
        *v34 = 1;
        goto LABEL_402;
      }
      UniDest = 0;
      if ( RtlDowncaseUnicodeString(&UniDest, (PCUNICODE_STRING)(*(_QWORD *)&v231.Length + 48LL), 1u) >= 0 )
      {
        v102 = UniDest.Length >> 1;
        if ( UniDest.Length >> 1 )
        {
          if ( UniDest.Buffer[v102 - 1] == 36 )
            UniDest.Length -= 2;
          if ( v102 > 0xEu )
            UniDest.Length = 28;
        }
        if ( *(_BYTE *)(v82 + 313) )
        {
          v103 = *(_QWORD *)(v82 + 232);
          v283 = 0;
          SystemFunction007(&UniDest, &v283);
          v104 = 0;
          for ( i = 0; i != 16; ++i )
          {
            v106 = *((_BYTE *)&v283.Length + i);
            v107 = *(_BYTE *)(v103 + i);
            v104 |= v107 ^ v106;
          }
          v108 = v35;
          if ( !v104 )
            v108 = -1073741414;
          v35 = v108;
        }
        RtlFreeUnicodeString(&UniDest);
      }
      v230 |= 0x80u;
    }
    else
    {
      if ( (*(_DWORD *)(v33 + 16) & 0x800) == 0 )
      {
        v59 = SourceSid;
        v35 = -1073741415;
        *v34 = 1;
        goto LABEL_402;
      }
      UniDest = 0;
      if ( RtlDowncaseUnicodeString(&UniDest, (PCUNICODE_STRING)(*(_QWORD *)&v231.Length + 48LL), 1u) >= 0 )
      {
        v95 = UniDest.Length >> 1;
        if ( UniDest.Length >> 1 )
        {
          if ( UniDest.Buffer[v95 - 1] == 36 )
            UniDest.Length -= 2;
          if ( v95 > 0xEu )
            UniDest.Length = 28;
        }
        if ( *(_BYTE *)(v82 + 313) )
        {
          v96 = *(_QWORD *)(v82 + 232);
          v283 = 0;
          SystemFunction007(&UniDest, &v283);
          v97 = 0;
          for ( j = 0; j != 16; ++j )
          {
            v99 = *((_BYTE *)&v283.Length + j);
            v100 = *(_BYTE *)(j + v96);
            v97 |= v100 ^ v99;
          }
          v101 = v35;
          if ( !v97 )
            v101 = -1073741415;
          v35 = v101;
        }
        RtlFreeUnicodeString(&UniDest);
      }
    }
    if ( v35 >= 0 )
      goto LABEL_275;
LABEL_289:
    v59 = SourceSid;
    *v34 = 1;
    goto LABEL_402;
  }
LABEL_275:
  if ( v53 != 501 && (*(_DWORD *)(v33 + 16) & 0x20000) == 0 && !NtLmGlobalAllowBlankPassword )
  {
    if ( !*(_BYTE *)(v82 + 313) )
      goto LABEL_595;
    v109 = 0;
    for ( k = 0; k != 16; ++k )
    {
      v111 = *(_BYTE *)(k + *(_QWORD *)(v82 + 232));
      v112 = *((_BYTE *)&NlpNullNtOwfPassword + k);
      v109 |= v112 ^ v111;
    }
    if ( !v109 )
    {
LABEL_595:
      if ( !*(_BYTE *)(v82 + 312) )
        goto LABEL_286;
      v113 = 0;
      for ( m = 0; m != 16; ++m )
      {
        v115 = *(_BYTE *)(m + *(_QWORD *)(v82 + 216));
        v116 = *((_BYTE *)NlpNullLmOwfPassword + m);
        v113 |= v116 ^ v115;
      }
      if ( !v113 )
      {
LABEL_286:
        if ( (NtLmCheckProcessOption() & 1) == 0 )
        {
          v59 = SourceSid;
          v35 = -1073741714;
          *v34 = 0;
          goto LABEL_402;
        }
      }
    }
  }
  v59 = SourceSid;
  v35 = MsvpFilterGroupMembership(&v245, SourceSid, v251, v255, &v240);
  if ( v35 < 0 )
  {
    *v34 = 0;
    goto LABEL_402;
  }
  if ( a7 != 1 )
  {
    if ( a7 != 2 )
      goto LABEL_389;
    v120 = (unsigned __int64)MEMORY[0x7FFE0004] << 32;
    if ( (v230 & 0x800) != 0 )
    {
      v121 = (v120 * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
      v122 = _InterlockedIncrement(&dword_180086D68);
      if ( !_InterlockedCompareExchange(&dword_180086CF0, 1, 0) )
      {
        if ( (unsigned __int64)(v121 - qword_180086D20) <= 0xDBBA0 )
        {
          if ( v122 < dword_180086480 )
          {
            v59 = SourceSid;
            _InterlockedExchange(&dword_180086CF0, 0);
            goto LABEL_402;
          }
          v123 = (unsigned int)_InterlockedExchange(&dword_180086D68, 0);
          v124 = dword_180086D00 - 1;
        }
        else
        {
          v123 = (unsigned int)_InterlockedExchange(&dword_180086D68, 0);
          v124 = dword_180086D00 + 1;
        }
        dword_180086D68 = 0;
        qword_180086D20 = v121;
        dword_180086D00 = v124;
        if ( v124 > -3 )
        {
          if ( v124 < 3 )
            goto LABEL_328;
          dword_180086D00 = 0;
          if ( (unsigned int)dword_180086480 <= 1 )
            goto LABEL_328;
          v125 = (unsigned int)dword_180086480 >> 1;
        }
        else
        {
          dword_180086D00 = 0;
          if ( (unsigned int)dword_180086480 >= 0x200 )
          {
LABEL_328:
            _InterlockedExchange(&dword_180086CF0, 0);
            WinSqmIncrementDWORD(0, 6914, v123);
            v59 = SourceSid;
            goto LABEL_402;
          }
          v125 = 2 * dword_180086480;
        }
        dword_180086480 = v125;
        goto LABEL_328;
      }
LABEL_389:
      v59 = SourceSid;
      goto LABEL_402;
    }
    if ( (v230 & 0x3000) != 0 )
    {
      v126 = (v120 * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
      v127 = _InterlockedIncrement(&dword_180086DB4);
      if ( _InterlockedCompareExchange(&dword_180086D38, 1, 0) )
        goto LABEL_389;
      if ( (unsigned __int64)(v126 - qword_180086CC8) <= 0xDBBA0 )
      {
        if ( v127 < dword_18008647C )
        {
          v59 = SourceSid;
          _InterlockedExchange(&dword_180086D38, 0);
          goto LABEL_402;
        }
        v128 = (unsigned int)_InterlockedExchange(&dword_180086DB4, 0);
        v129 = dword_180086DA0 - 1;
      }
      else
      {
        v128 = (unsigned int)_InterlockedExchange(&dword_180086DB4, 0);
        v129 = dword_180086DA0 + 1;
      }
      dword_180086DB4 = 0;
      qword_180086CC8 = v126;
      dword_180086DA0 = v129;
      if ( v129 > -3 )
      {
        if ( v129 < 3 )
          goto LABEL_343;
        dword_180086DA0 = 0;
        if ( (unsigned int)dword_18008647C <= 1 )
          goto LABEL_343;
        v130 = (unsigned int)dword_18008647C >> 1;
      }
      else
      {
        dword_180086DA0 = 0;
        if ( (unsigned int)dword_18008647C >= 0x200 )
        {
LABEL_343:
          _InterlockedExchange(&dword_180086D38, 0);
          WinSqmIncrementDWORD(0, 6911, v128);
          v59 = SourceSid;
          goto LABEL_402;
        }
        v130 = 2 * dword_18008647C;
      }
      dword_18008647C = v130;
      goto LABEL_343;
    }
    if ( (v230 & 8) != 0 )
    {
      v131 = (v120 * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
      v132 = _InterlockedIncrement(&dword_180086D28);
      if ( _InterlockedCompareExchange(&dword_180086D90, 1, 0) )
        goto LABEL_389;
      if ( (unsigned __int64)(v131 - qword_180086D50) <= 0xDBBA0 )
      {
        if ( v132 < dword_180086488 )
        {
          v59 = SourceSid;
          _InterlockedExchange(&dword_180086D90, 0);
          goto LABEL_402;
        }
        v133 = (unsigned int)_InterlockedExchange(&dword_180086D28, 0);
        v134 = dword_180086D5C - 1;
      }
      else
      {
        v133 = (unsigned int)_InterlockedExchange(&dword_180086D28, 0);
        v134 = dword_180086D5C + 1;
      }
      dword_180086D28 = 0;
      qword_180086D50 = v131;
      dword_180086D5C = v134;
      if ( v134 > -3 )
      {
        if ( v134 < 3 )
          goto LABEL_358;
        dword_180086D5C = 0;
        if ( (unsigned int)dword_180086488 <= 1 )
          goto LABEL_358;
        v135 = (unsigned int)dword_180086488 >> 1;
      }
      else
      {
        dword_180086D5C = 0;
        if ( (unsigned int)dword_180086488 >= 0x200 )
        {
LABEL_358:
          _InterlockedExchange(&dword_180086D90, 0);
          WinSqmIncrementDWORD(0, 6910, v133);
          v59 = SourceSid;
          goto LABEL_402;
        }
        v135 = 2 * dword_180086488;
      }
      dword_180086488 = v135;
      goto LABEL_358;
    }
    v136 = (v120 * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
    if ( *(char *)(v33 + 16) < 0 )
    {
      v137 = _InterlockedIncrement(&dword_180086DB0);
      if ( _InterlockedCompareExchange(&dword_180086CD0, 1, 0) )
        goto LABEL_389;
      if ( (unsigned __int64)(v136 - qword_180086CF8) <= 0xDBBA0 )
      {
        if ( v137 < dword_18008648C )
        {
          v59 = SourceSid;
          _InterlockedExchange(&dword_180086CD0, 0);
          goto LABEL_402;
        }
        v138 = (unsigned int)_InterlockedExchange(&dword_180086DB0, 0);
        v139 = dword_180086CEC - 1;
      }
      else
      {
        v138 = (unsigned int)_InterlockedExchange(&dword_180086DB0, 0);
        v139 = dword_180086CEC + 1;
      }
      dword_180086DB0 = 0;
      qword_180086CF8 = v136;
      dword_180086CEC = v139;
      if ( v139 > -3 )
      {
        if ( v139 < 3 )
          goto LABEL_373;
        dword_180086CEC = 0;
        if ( (unsigned int)dword_18008648C <= 1 )
          goto LABEL_373;
        v140 = (unsigned int)dword_18008648C >> 1;
      }
      else
      {
        dword_180086CEC = 0;
        if ( (unsigned int)dword_18008648C >= 0x200 )
        {
LABEL_373:
          _InterlockedExchange(&dword_180086CD0, 0);
          WinSqmIncrementDWORD(0, 6913, v138);
          v59 = SourceSid;
          goto LABEL_402;
        }
        v140 = 2 * dword_18008648C;
      }
      dword_18008648C = v140;
      goto LABEL_373;
    }
    v141 = _InterlockedIncrement(&dword_180086CE8);
    if ( _InterlockedCompareExchange(&dword_180086D80, 1, 0) )
      goto LABEL_389;
    if ( (unsigned __int64)(v136 - qword_180086DA8) <= 0xDBBA0 )
    {
      if ( v141 < dword_180086478 )
      {
        _InterlockedExchange(&dword_180086D80, 0);
        goto LABEL_389;
      }
      v142 = (unsigned int)_InterlockedExchange(&dword_180086CE8, 0);
      v143 = dword_180086D58 - 1;
    }
    else
    {
      v142 = (unsigned int)_InterlockedExchange(&dword_180086CE8, 0);
      v143 = dword_180086D58 + 1;
    }
    dword_180086CE8 = 0;
    qword_180086DA8 = v136;
    dword_180086D58 = v143;
    if ( v143 > -3 )
    {
      if ( v143 < 3 )
        goto LABEL_387;
      dword_180086D58 = 0;
      if ( (unsigned int)dword_180086478 <= 1 )
        goto LABEL_387;
      v144 = (unsigned int)dword_180086478 >> 1;
    }
    else
    {
      dword_180086D58 = 0;
      if ( (unsigned int)dword_180086478 >= 0x200 )
      {
LABEL_387:
        _InterlockedExchange(&dword_180086D80, 0);
        WinSqmIncrementDWORD(0, 6912, v142);
        v59 = SourceSid;
        goto LABEL_402;
      }
      v144 = 2 * dword_180086478;
    }
    dword_180086478 = v144;
    goto LABEL_387;
  }
  if ( (*(_DWORD *)(v82 + 280) & 0x1C0) != 0
    || !(unsigned int)((__int64 (*)(void))LsaIIsLastInteractiveLogonInfoEnabled)() )
  {
    goto LABEL_389;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_02757a6cf13d311f0239b5d699c3efb5_Traceguids);
  v234 = 0;
  *(_QWORD *)&v283.Length = 0;
  UniDest = 0;
  v117 = SamIGetUserLogonInformation2(*(_QWORD *)&v244.Length, 8, v82 + 48, 4, 512, 0, &v283, &UniDest, &v234);
  v35 = v117;
  if ( v117 >= 0 )
  {
    v118 = *(_QWORD *)&v283.Length;
    v119 = *(_QWORD *)(*(_QWORD *)&v283.Length + 392LL);
    *((_QWORD *)&v266 + 1) = *(_QWORD *)(*(_QWORD *)&v283.Length + 400LL);
    LODWORD(v267) = *(_DWORD *)(*(_QWORD *)&v283.Length + 408LL);
    if ( !v119 )
      v119 = 0x7FFFFFFFFFFFFFFFLL;
    *(_QWORD *)&v266 = v119;
    v14 = v266;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_02757a6cf13d311f0239b5d699c3efb5_Traceguids,
        v82 + 48,
        v117);
    v118 = *(_QWORD *)&v283.Length;
  }
  if ( UniDest.Buffer )
  {
    SamIFreeSidAndAttributesList(&UniDest, v118);
    v118 = *(_QWORD *)&v283.Length;
  }
  if ( v118 )
    SamIFree_UserInternal6Information(v118);
  if ( v234 )
    SamrCloseHandle(&v234);
  v59 = SourceSid;
  if ( v35 < 0 )
    *v34 = 0;
LABEL_402:
  v145 = v222;
  if ( v35 >= 0 || (v146 = 0, v222) )
  {
    v220[0] = 0;
    UniDest = 0;
    v150 = RtlLengthSid(v59);
    v151 = v250[0]->Length + 486 + *(unsigned __int16 *)(v82 + 48) + v150 + 8 * v251[0] + v248[0]->Length;
    if ( a7 != 2 )
      v151 += *(unsigned __int16 *)(v82 + 64)
            + *(unsigned __int16 *)(v82 + 96)
            + *(unsigned __int16 *)(v82 + 112)
            + *(unsigned __int16 *)(v82 + 128)
            + *(unsigned __int16 *)(v82 + 80)
            + 10;
    v152 = *(_DWORD *)(v33 + 16);
    if ( (v152 & 8) != 0 )
    {
      v153 = *(unsigned __int16 *)(v82 + 192);
    }
    else
    {
      if ( (v152 & 0x200) == 0 )
        goto LABEL_419;
      v153 = *(unsigned __int16 *)(v82 + 128);
    }
    v151 += v153 + 2;
LABEL_419:
    if ( a10 == 3 || a10 == 6 )
    {
      v151 += v240;
      if ( a10 == 6 )
      {
        RtlAcquireResourceShared(&NtLmGlobalCritSect, 1u);
        v154 = NlpWorkstation;
        if ( NlpWorkstation )
        {
          RtlInitUnicodeString(&UniDest, &::Src);
          v154 = NlpWorkstation;
        }
        else
        {
          UniDest = NtLmGlobalUnicodeDnsDomainNameString;
        }
        v151 += UniDest.Length + 2;
        if ( DestinationString.Buffer )
        {
          v220[0] = 0;
          v151 += DestinationString.Length + 2;
        }
        else
        {
          v220[0] = 1;
          if ( !v154 )
            v151 += UniDest.Length + *(unsigned __int16 *)(v82 + 48) + 4;
        }
      }
    }
    v155 = (v151 + 1) & 0xFFFFFFFE;
    v156 = (char *)LocalAlloc(0x40u, v155);
    v146 = v156;
    if ( !v156 )
    {
      v145 = 0;
      *v34 = 0;
      v35 = -1073741801;
      RtlReleaseResource(&NtLmGlobalCritSect);
      goto LABEL_553;
    }
    memset_0(v156, 0, v155);
    v157 = v146 + 480;
    if ( (BYTE8(v282) & 1) != 0 )
    {
      *((_DWORD *)v146 + 2) = v278;
      v158 = DWORD1(v278);
    }
    else
    {
      *((_DWORD *)v146 + 2) = v247;
      v158 = HIDWORD(v247);
    }
    *((_DWORD *)v146 + 3) = v158;
    if ( (BYTE8(v282) & 2) != 0 )
    {
      *((_DWORD *)v146 + 4) = DWORD2(v278);
      v159 = HIDWORD(v278);
    }
    else
    {
      *((_DWORD *)v146 + 4) = v242;
      v159 = HIDWORD(v242);
    }
    *((_DWORD *)v146 + 5) = v159;
    if ( (BYTE8(v282) & 0x10) != 0 )
      v160 = v281;
    else
      v160 = v285;
    *(_OWORD *)(v146 + 172) = v160;
    v161 = v230;
    if ( (BYTE8(v282) & 0x20) != 0 )
      v161 = DWORD1(v282);
    *((_DWORD *)v146 + 42) = v161;
    v162 = HIDWORD(v282);
    if ( (BYTE8(v282) & 0x40) == 0 )
      v162 = *(_DWORD *)(v82 + 272);
    v68 = v222 == 0;
    *((_DWORD *)v146 + 37) = v162;
    *(_QWORD *)v146 = *(_QWORD *)v82;
    *((_QWORD *)v146 + 3) = *(_QWORD *)(v82 + 16);
    *((_QWORD *)v146 + 4) = *(_QWORD *)(v82 + 32);
    *((_QWORD *)v146 + 5) = *(_QWORD *)(v82 + 40);
    *((_WORD *)v146 + 72) = *(_WORD *)(v82 + 306);
    *((_WORD *)v146 + 73) = *(_WORD *)(v82 + 304);
    *((_DWORD *)v146 + 38) = *(_DWORD *)(v82 + 276);
    *((_DWORD *)v146 + 39) = v251[0];
    *((_QWORD *)v146 + 29) = v284;
    *((_DWORD *)v146 + 60) = *(_DWORD *)(v82 + 280);
    if ( !v68 )
      *((_DWORD *)v146 + 61) = v35;
    v163 = v251[0];
    v164 = v267;
    v165 = Src;
    *(_OWORD *)(v146 + 248) = v14;
    v166 = 8 * v163;
    *((_QWORD *)v146 + 33) = v164;
    memcpy_0(v146 + 480, v165, 8 * v163);
    *((_QWORD *)v146 + 20) = v157;
    v167 = &v157[v166];
    v168 = SourceSid;
    v169 = RtlLengthSid(SourceSid);
    memcpy_0(v167, v168, v169);
    *((_QWORD *)v146 + 28) = v167;
    v170 = &v167[RtlLengthSid(v168)];
    if ( a10 == 3 || a10 == 6 )
    {
      *((_DWORD *)v146 + 42) |= 0x20u;
      if ( v240 )
      {
        v171 = v255[0];
        v172 = 0;
        v173 = v255[0];
        *((_QWORD *)v146 + 35) = v170;
        v170 += 16 * v173;
        *((_DWORD *)v146 + 68) = v171;
        if ( v171 )
        {
          do
          {
            v174 = v256;
            v175 = 2LL * v172;
            *(_DWORD *)(*((_QWORD *)v146 + 35) + 8 * v175 + 8) = *(_DWORD *)(v256 + 16LL * v172 + 8);
            *(_QWORD *)(*((_QWORD *)v146 + 35) + 8 * v175) = v170;
            v176 = RtlLengthSid(*(PSID *)(v174 + 16LL * v172));
            memcpy_0(*(void **)(*((_QWORD *)v146 + 35) + 16LL * v172), *(const void **)(v174 + 16LL * v172), v176);
            v170 += v176;
            ++v172;
          }
          while ( v172 < *((_DWORD *)v146 + 68) );
          v82 = *(_QWORD *)&v231.Length;
        }
        v33 = (__int64)v225;
      }
    }
    v177 = (UNICODE_STRING *)((unsigned __int64)(v170 + 1) & 0xFFFFFFFFFFFFFFFEuLL);
    v178 = (struct _UNICODE_STRING *)(v146 + 48);
    if ( *(_WORD *)(v82 + 48) )
    {
      *((_QWORD *)v146 + 7) = v177;
      *((_WORD *)v146 + 25) = *(_WORD *)(v82 + 48) + 2;
      RtlCopyUnicodeString(v178, (PCUNICODE_STRING)(v82 + 48));
      v179 = *(unsigned __int16 *)(v82 + 48);
      *(USHORT *)((char *)&v177->Length + v179) = 0;
      v177 = (UNICODE_STRING *)((char *)v177 + v179 + 2);
    }
    else
    {
      RtlInitUnicodeString(v178, 0);
    }
    v147 = a7;
    if ( a7 != 2 )
    {
      v180 = (struct _UNICODE_STRING *)(v146 + 64);
      if ( *(_WORD *)(v82 + 64) )
      {
        *((_QWORD *)v146 + 9) = v177;
        *((_WORD *)v146 + 33) = *(_WORD *)(v82 + 64) + 2;
        RtlCopyUnicodeString(v180, (PCUNICODE_STRING)(v82 + 64));
        v181 = *(unsigned __int16 *)(v82 + 64);
        *(USHORT *)((char *)&v177->Length + v181) = 0;
        v177 = (UNICODE_STRING *)((char *)v177 + v181 + 2);
      }
      else
      {
        RtlInitUnicodeString(v180, 0);
      }
      v182 = (struct _UNICODE_STRING *)(v146 + 80);
      if ( *(_WORD *)(v82 + 112) )
      {
        *((_QWORD *)v146 + 11) = v177;
        *((_WORD *)v146 + 41) = *(_WORD *)(v82 + 112) + 2;
        RtlCopyUnicodeString(v182, (PCUNICODE_STRING)(v82 + 112));
        v183 = *(unsigned __int16 *)(v82 + 112);
        *(USHORT *)((char *)&v177->Length + v183) = 0;
        v177 = (UNICODE_STRING *)((char *)v177 + v183 + 2);
      }
      else
      {
        RtlInitUnicodeString(v182, 0);
      }
      v184 = (struct _UNICODE_STRING *)(v146 + 96);
      if ( *(_WORD *)(v82 + 128) )
      {
        *((_QWORD *)v146 + 13) = v177;
        *((_WORD *)v146 + 49) = *(_WORD *)(v82 + 128) + 2;
        RtlCopyUnicodeString(v184, (PCUNICODE_STRING)(v82 + 128));
        v185 = *(unsigned __int16 *)(v82 + 128);
        *(USHORT *)((char *)&v177->Length + v185) = 0;
        v177 = (UNICODE_STRING *)((char *)v177 + v185 + 2);
      }
      else
      {
        RtlInitUnicodeString(v184, 0);
      }
      v186 = (struct _UNICODE_STRING *)(v146 + 112);
      if ( *(_WORD *)(v82 + 80) )
      {
        *((_QWORD *)v146 + 15) = v177;
        *((_WORD *)v146 + 57) = *(_WORD *)(v82 + 80) + 2;
        RtlCopyUnicodeString(v186, (PCUNICODE_STRING)(v82 + 80));
        v187 = *(unsigned __int16 *)(v82 + 80);
        *(USHORT *)((char *)&v177->Length + v187) = 0;
        v177 = (UNICODE_STRING *)((char *)v177 + v187 + 2);
      }
      else
      {
        RtlInitUnicodeString(v186, 0);
      }
      v188 = (struct _UNICODE_STRING *)(v146 + 128);
      if ( *(_WORD *)(v82 + 96) )
      {
        *((_QWORD *)v146 + 17) = v177;
        *((_WORD *)v146 + 65) = *(_WORD *)(v82 + 96) + 2;
        RtlCopyUnicodeString(v188, (PCUNICODE_STRING)(v82 + 96));
        v189 = *(unsigned __int16 *)(v82 + 96);
        *(USHORT *)((char *)&v177->Length + v189) = 0;
        v177 = (UNICODE_STRING *)((char *)v177 + v189 + 2);
      }
      else
      {
        RtlInitUnicodeString(v188, 0);
      }
    }
    v190 = (struct _UNICODE_STRING *)(v146 + 192);
    if ( (BYTE8(v282) & 4) != 0 )
    {
      if ( SourceString.Length )
      {
        *((_QWORD *)v146 + 25) = v177;
        *((_WORD *)v146 + 97) = SourceString.Length + 2;
        RtlCopyUnicodeString(v190, &SourceString);
        v191 = SourceString.Length;
        *(USHORT *)((char *)&v177->Length + SourceString.Length) = 0;
        v177 = (UNICODE_STRING *)((char *)v177 + v191 + 2);
        goto LABEL_478;
      }
    }
    else
    {
      v192 = v250[0];
      if ( v250[0]->Length )
      {
        *((_QWORD *)v146 + 25) = v177;
        *((_WORD *)v146 + 97) = v192->Length + 2;
        RtlCopyUnicodeString(v190, v192);
        v193 = v192->Length;
        *(USHORT *)((char *)&v177->Length + v193) = 0;
        v177 = (UNICODE_STRING *)((char *)v177 + v193 + 2);
        goto LABEL_478;
      }
    }
    RtlInitUnicodeString(v190, 0);
LABEL_478:
    v194 = (struct _UNICODE_STRING *)(v146 + 208);
    if ( (BYTE8(v282) & 8) != 0 )
    {
      if ( v280.Length )
      {
        *((_QWORD *)v146 + 27) = v177;
        *((_WORD *)v146 + 105) = v280.Length + 2;
        RtlCopyUnicodeString(v194, &v280);
        v195 = v280.Length;
        *(USHORT *)((char *)&v177->Length + v280.Length) = 0;
        v177 = (UNICODE_STRING *)((char *)v177 + v195 + 2);
        goto LABEL_484;
      }
    }
    else
    {
      v196 = v248[0];
      if ( v248[0]->Length )
      {
        *((_QWORD *)v146 + 27) = v177;
        *((_WORD *)v146 + 105) = v196->Length + 2;
        RtlCopyUnicodeString(v194, v196);
        v197 = v196->Length;
        *(USHORT *)((char *)&v177->Length + v197) = 0;
        v177 = (UNICODE_STRING *)((char *)v177 + v197 + 2);
        goto LABEL_484;
      }
    }
    RtlInitUnicodeString(v194, 0);
LABEL_484:
    if ( a10 == 6 )
    {
      v198 = (struct _UNICODE_STRING *)(v146 + 288);
      if ( UniDest.Length )
      {
        *((_QWORD *)v146 + 37) = v177;
        *((_WORD *)v146 + 145) = UniDest.Length + 2;
        RtlCopyUnicodeString(v198, &UniDest);
        v199 = UniDest.Length;
        *(USHORT *)((char *)&v177->Length + UniDest.Length) = 0;
        v177 = (UNICODE_STRING *)((char *)v177 + v199 + 2);
      }
      else
      {
        RtlInitUnicodeString(v198, 0);
      }
      if ( !NlpWorkstation )
      {
        if ( v220[0] )
        {
          v200 = *(_WORD *)(v82 + 48);
          *(_OWORD *)v250 = 0;
          v244 = 0;
          v283 = 0;
          v231 = 0;
          if ( v200 )
          {
            v250[1] = v177;
            WORD1(v250[0]) = v200 + 2;
            RtlCopyUnicodeString((PUNICODE_STRING)v250, (PCUNICODE_STRING)(v82 + 48));
            v201 = *(unsigned __int16 *)(v82 + 48);
            *(USHORT *)((char *)&v177->Length + v201) = 0;
            v177 = (UNICODE_STRING *)((char *)v177 + v201 + 2);
          }
          else
          {
            RtlInitUnicodeString((PUNICODE_STRING)v250, 0);
          }
          v202 = (WCHAR *)&v177[-1].Buffer + 3;
          RtlInitUnicodeString(&v231, L"@");
          if ( v231.Length )
          {
            v244.Buffer = v202;
            v244.MaximumLength = v231.Length + 2;
            RtlCopyUnicodeString(&v244, &v231);
            v203 = v231.Length;
            *(WCHAR *)((char *)v202 + v231.Length) = 0;
            v202 = (WCHAR *)((char *)v202 + v203 + 2);
          }
          else
          {
            RtlInitUnicodeString(&v244, 0);
          }
          v177 = (UNICODE_STRING *)(v202 - 1);
          if ( UniDest.Length )
          {
            v283.Buffer = &v177->Length;
            v283.MaximumLength = UniDest.Length + 2;
            RtlCopyUnicodeString(&v283, &UniDest);
            v204 = UniDest.Length;
            *(USHORT *)((char *)&v177->Length + UniDest.Length) = 0;
            v177 = (UNICODE_STRING *)((char *)v177 + v204 + 2);
          }
          else
          {
            RtlInitUnicodeString(&v283, 0);
          }
          *((PCUNICODE_STRING *)v146 + 39) = v250[1];
          v205 = LOWORD(v250[0]) + v244.Length + v283.Length;
          *((_WORD *)v146 + 152) = v205;
          v206 = v205 + 2;
        }
        else
        {
          *(_OWORD *)v248 = 0;
          if ( DestinationString.Length )
          {
            v248[1] = v177;
            WORD1(v248[0]) = DestinationString.Length + 2;
            RtlCopyUnicodeString((PUNICODE_STRING)v248, &DestinationString);
            v207 = DestinationString.Length;
            *(USHORT *)((char *)&v177->Length + DestinationString.Length) = 0;
            v177 = (UNICODE_STRING *)((char *)v177 + v207 + 2);
          }
          else
          {
            RtlInitUnicodeString((PUNICODE_STRING)v248, 0);
          }
          v177 = (UNICODE_STRING *)((char *)v177 - 2);
          *((PCUNICODE_STRING *)v146 + 39) = v248[1];
          v206 = (__int16)v248[0];
          *((_WORD *)v146 + 152) = v248[0];
        }
        *((_WORD *)v146 + 153) = v206;
      }
      RtlReleaseResource(&NtLmGlobalCritSect);
    }
    v208 = *(_DWORD *)(v33 + 16);
    if ( (v208 & 8) != 0 )
    {
      v209 = (struct _UNICODE_STRING *)(v146 + 128);
      if ( *(_WORD *)(v82 + 192) )
      {
        *((_QWORD *)v146 + 17) = v177;
        *((_WORD *)v146 + 65) = *(_WORD *)(v82 + 192) + 2;
        RtlCopyUnicodeString(v209, (PCUNICODE_STRING)(v82 + 192));
        *(USHORT *)((char *)&v177->Length + *(unsigned __int16 *)(v82 + 192)) = 0;
      }
      else
      {
        RtlInitUnicodeString(v209, 0);
      }
    }
    else if ( (v208 & 0x200) != 0 )
    {
      v210 = (struct _UNICODE_STRING *)(v146 + 128);
      if ( *(_WORD *)(v82 + 128) )
      {
        *((_QWORD *)v146 + 17) = v177;
        *((_WORD *)v146 + 65) = *(_WORD *)(v82 + 128) + 2;
        RtlCopyUnicodeString(v210, (PCUNICODE_STRING)(v82 + 128));
        *(USHORT *)((char *)&v177->Length + *(unsigned __int16 *)(v82 + 128)) = 0;
      }
      else
      {
        RtlInitUnicodeString(v210, 0);
      }
      *((_DWORD *)v146 + 42) |= 0x400u;
    }
    v211 = v241;
    v145 = v222;
    if ( v222 )
      v211 = v35;
    v35 = 0;
    v68 = (v237 & 0x200000) == 0;
    *v228 = 1;
    v241 = v211;
    if ( !v68 )
    {
      memset_0(pName2, 0, sizeof(pName2));
      *(_OWORD *)pName2 = *(_OWORD *)(v82 + 192);
      v35 = SamrSetInformationUser(v238, 20, pName2);
    }
    if ( v211 < 0 )
      goto LABEL_553;
    if ( v35 >= 0 )
      goto LABEL_407;
    goto LABEL_405;
  }
  v147 = a7;
LABEL_405:
  if ( v35 != -1073741718 && v35 != -1073741730 )
    goto LABEL_553;
LABEL_407:
  memset_0(pName1, 0, 0xC0u);
  if ( v35 < 0 )
  {
    if ( v35 != -1073741718 )
    {
      LODWORD(v149) = 0x800000;
      if ( v147 == 1 )
        LODWORD(v149) = 10485760;
      goto LABEL_552;
    }
    v213 = *(_OWORD *)(v33 + 48);
    v149 = 0x10000000;
    *(_DWORD *)pName1 = 0x10000000;
    v288 = v213;
    if ( v227 || v223 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
      {
        v214 = "true";
        v215 = "true";
        if ( !v223 )
          v215 = "false";
        if ( !v227 )
          v214 = "false";
        WPP_SF_Zdss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v223,
          v227,
          (unsigned int)&v239,
          a9,
          (__int64)v214,
          (__int64)v215);
        v149 = *(unsigned int *)pName1;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_02757a6cf13d311f0239b5d699c3efb5_Traceguids,
          (unsigned int)&v239,
          a9);
        v149 = *(unsigned int *)pName1;
      }
      LODWORD(v149) = v149 | 0x8000000;
      *(_DWORD *)pName1 = v149;
    }
    if ( v147 == 1 && (*(_DWORD *)(v82 + 280) & 0x1C0) == 0 )
    {
      InteractiveLogonInfoEnabled = LsaIIsLastInteractiveLogonInfoEnabled(v149);
      LODWORD(v149) = *(_DWORD *)pName1;
      if ( InteractiveLogonInfoEnabled )
        LODWORD(v149) = *(_DWORD *)pName1 | 0x40000;
    }
    goto LABEL_548;
  }
  if ( v147 == 1 )
  {
    if ( (*(_DWORD *)(v82 + 280) & 0x1C0) != 0 || !(unsigned int)LsaIIsLastInteractiveLogonInfoEnabled(v148) )
      LODWORD(v149) = 0x1000000;
    else
      LODWORD(v149) = 17039360;
  }
  else
  {
    v212 = *(_DWORD *)(v33 + 16);
    LODWORD(v149) = 1077936128;
    if ( (v212 & 4) == 0 && !*(_WORD *)(v82 + 304) )
      goto LABEL_548;
    if ( (v212 & 0x20000) == 0 )
      LODWORD(v149) = 0x40000000;
  }
  if ( *(_WORD *)(v82 + 304) && (*(_DWORD *)(v33 + 16) & 0x20000) == 0 )
    *v258 = 1;
LABEL_548:
  if ( (_DWORD)v149 )
  {
LABEL_552:
    *(_DWORD *)pName1 = v149 | 0x2000000;
    SamIUpdateLogonStatistics(v238, pName1);
  }
LABEL_553:
  if ( a9 && v35 < 0 )
    goto LABEL_565;
  v217 = v35;
  if ( v35 >= 0 && v145 )
    v217 = v241;
  if ( v146 )
    v218 = NlpMakeDomainRelativeSid(*((PSID *)v146 + 28));
  else
    v218 = 0;
  LsaIAuditAccountLogonEx(680, v217 >= 0, &NlpMsv1_0PackageName, &v239, v33 + 48, 0, 0, v217, v218);
  if ( v146 && v218 )
    ((void (__fastcall *)(__int64))LsaFunctions->FreeLsaHeap)(v218);
  if ( v35 < 0 )
  {
LABEL_565:
    if ( v146 )
    {
      LocalFree(v146);
      v146 = 0;
    }
  }
  *v268 = v146;
  SamIFree_SAMPR_RETURNED_USTRING_ARRAY(&v262);
  SamIFree_SAMPR_ULONG_ARRAY(&v264);
  if ( v243 )
    SamIFree_UserInternal6Information(v243);
  if ( DestinationString.Buffer )
    SamIFreeVoid();
  if ( v246 )
    SamIFreeSidAndAttributesList(&v245, v219);
  if ( Src )
    ((void (*)(void))qword_180088398)();
  if ( v256 )
    ((void (*)(void))qword_180088398)();
  if ( v238 )
    SamrCloseHandle(&v238);
  if ( v280.Buffer )
    LocalFree(v280.Buffer);
  if ( SourceString.Buffer )
    LocalFree(SourceString.Buffer);
  if ( v249 )
    ((void (__fastcall *)(void *))qword_180088398)(v249);
  if ( DomainRelativeSid )
    ((void (__fastcall *)(__int64))qword_180088240)(DomainRelativeSid);
  if ( hMem )
    LocalFree(hMem);
  if ( v260 )
    ((void (__fastcall *)(__int64))qword_180088240)(v260);
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x180022220  push    rbp
0x180022222  push    rsi
0x180022223  push    rdi
0x180022224  push    r12
0x180022226  push    r13
0x180022228  push    r14
0x18002222a  push    r15
0x18002222c  lea     rbp, [rsp-790h]
0x180022234  sub     rsp, 890h
0x18002223b  movaps  [rsp+8C0h+var_40], xmm6
0x180022243  mov     rax, cs:__security_cookie
0x18002224a  xor     rax, rsp
0x18002224d  mov     [rbp+7C0h+var_50], rax
0x180022254  mov     rax, [rbp+7C0h+arg_50]
0x18002225b  xorps   xmm0, xmm0
0x18002225e  mov     r15, [rbp+7C0h+arg_58]
0x180022265  xorps   xmm1, xmm1
0x180022268  mov     rsi, [rbp+7C0h+DomainName1]
0x18002226f  xorps   xmm6, xmm6
0x180022272  mov     rdi, [rbp+7C0h+Sid]
0x180022279  mov     r13d, r8d
0x18002227c  mov     r14, [rbp+7C0h+DomainName2]
0x180022283  mov     [rbp+7C0h+var_6B0], rax
0x18002228a  mov     rax, [rbp+7C0h+arg_60]
0x180022291  mov     qword ptr [rbp+7C0h+var_7A0.Length], rcx
0x180022295  xor     ecx, ecx
0x180022297  mov     [rbp+7C0h+var_708], rax
0x18002229e  xor     eax, eax
0x1800222a0  mov     qword ptr [rbp+7C0h+var_6E4], rax
0x1800222a7  mov     qword ptr [rbp+7C0h+var_6D4], rax
0x1800222ae  mov     qword ptr [rbp+7C0h+var_78C], rax
0x1800222b2  mov     [rbp+0D8h], rax
0x1800222b9  mov     [rbp+0E8h], rax
0x1800222c0  mov     [rbp+30h], rax
0x1800222c4  mov     [rbp+7C0h+var_760], r9
0x1800222c8  mov     [rbp+7C0h+var_7F8], dl
0x1800222cb  mov     [rbp+7C0h+var_828], r15
0x1800222cf  mov     [rbp+7C0h+var_838], rsi
0x1800222d3  mov     [rsp+8C0h+SourceSid], rdi
0x1800222d8  mov     [rbp+7C0h+var_7D0], rcx
0x1800222dc  mov     [rbp+7C0h+var_7A8], rcx
0x1800222e0  mov     [rbp+7C0h+var_74C], ecx
0x1800222e3  mov     dword ptr [rbp+7C0h+var_820+4], ecx
0x1800222e6  movups  [rbp+7C0h+var_5B8], xmm0
0x1800222ed  mov     [rbp+7C0h+var_5C0], rcx
0x1800222f4  mov     [rbp+7C0h+var_7D8], ecx
0x1800222f7  movups  xmmword ptr [rbp+7C0h+var_7C8.Length], xmm0
0x1800222fb  mov     qword ptr [rbp+7C0h+SystemTime], rcx
0x180022302  movups  [rbp+7C0h+var_718], xmm1
0x180022309  mov     [rbp+7C0h+var_780], rcx
0x18002230d  mov     [rbp+7C0h+var_7B0], rcx
0x180022311  movups  xmmword ptr [rbp+7C0h+DestinationString.Length], xmm0
0x180022318  mov     qword ptr [rbp+7C0h+var_5D0.Length], rcx
0x18002231f  mov     [rbp+7C0h+var_724], ecx
0x180022325  mov     [rbp+7C0h+var_7B8], ecx
0x180022328  movups  [rbp+7C0h+var_620], xmm0
0x18002232f  mov     [rbp+7C0h+var_7E8], ecx
0x180022332  movups  xmmword ptr [rbp+7C0h+SourceString.Length], xmm0
0x180022339  mov     [rbp+7C0h+var_83F], al
0x18002233c  movups  xmmword ptr [rbp+7C0h+var_600.Length], xmm0
0x180022343  mov     [rbp+7C0h+var_830], al
0x180022346  movups  [rbp+7C0h+var_5F0], xmm0
0x18002234d  mov     [rbp+7C0h+var_82F], al
0x180022350  movups  [rbp+7C0h+var_5E0], xmm0
0x180022357  mov     [rsp+8C0h+var_850], al
0x18002235b  movups  [rbp+7C0h+var_6C8], xmm6
0x180022362  mov     [rbp+7C0h+var_6B8], rax
0x180022369  mov     [rbp+7C0h+hMem], rcx
0x180022370  mov     qword ptr [rbp+7C0h+UniDest.Length], rcx
0x180022374  movups  xmmword ptr [rbp+7C0h+var_690.Length], xmm0
0x18002237b  mov     [rbp+7C0h+var_630], rax
0x180022382  movups  xmmword ptr [rbp+7C0h+var_680.Length], xmm0
0x180022389  mov     [rbp+7C0h+var_698], rax
0x180022390  movups  xmmword ptr [rbp+7C0h+var_670.Length], xmm0
0x180022397  movups  xmmword ptr [rbp+7C0h+var_660.Length], xmm0
0x18002239e  movups  xmmword ptr [rbp+7C0h+var_650.Length], xmm0
0x1800223a5  movups  xmmword ptr [rbp+7C0h+var_640.Length], xmm0
0x1800223ac  movups  [rbp+7C0h+var_6A8], xmm0
0x1800223b3  call    Feature_ID57824352__private_IsEnabledDeviceUsageNoInline
0x1800223b8  test    eax, eax
0x1800223ba  jz      short loc_1800223D6
0x1800223bc  mov     rax, cs:LsaFunctions
0x1800223c3  lea     rcx, [rbp+7C0h+var_6A8]
0x1800223ca  mov     rax, [rax+0C0h]
0x1800223d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223d6  mov     eax, [rsi+10h]
0x1800223d9  mov     r12d, [rbp+7C0h+arg_30]
0x1800223e0  mov     [rsp+8C0h+arg_10], rbx
0x1800223e8  bt      eax, 13h
0x1800223ec  jnb     short loc_18002243D
0x1800223ee  cmp     [rbp+7C0h+arg_40], 0
0x1800223f5  jnz     short loc_18002242F
0x1800223f7  cmp     cs:NlpWorkstation, 0
0x1800223fe  jz      short loc_18002242F
0x180022400  cmp     r13d, 1
0x180022404  jnz     short loc_18002242F
0x180022406  cmp     r12d, 2
0x18002240a  jnz     short loc_18002242F
0x18002240c  test    r14, r14
0x18002240f  jz      short loc_18002242F
0x180022411  cmp     word ptr [r14], 0
0x180022416  jz      short loc_18002242F
0x180022418  movzx   ebx, r13b
0x18002241c  lea     rax, NlpSamDomainName
0x180022423  mov     [rbp+7C0h+var_83E], bl
0x180022426  mov     [rbp+7C0h+var_778], rax
0x18002242a  jmp     loc_18002257D
0x18002242f  mov     byte ptr [r15], 1
0x180022433  mov     eax, 0C000000Dh
0x180022438  jmp     loc_180024B92
0x18002243d  xor     bl, bl
0x18002243f  mov     [rbp+7C0h+var_778], r14
0x180022443  mov     [rbp+7C0h+var_83E], bl
0x180022446  bt      eax, 0Ah
0x18002244a  jnb     loc_18002257D
0x180022450  cmp     word ptr [rsi], 0
0x180022454  jz      loc_18002257D
0x18002245a  bt      eax, 0Fh
0x18002245e  jb      loc_18002257D
0x180022464  mov     rdx, r14; DomainName2
0x180022467  mov     rcx, rsi; DomainName1
0x18002246a  call    cs:__imp_RtlEqualDomainName
0x180022470  test    al, al
0x180022472  jnz     loc_18002257D
0x180022478  mov     dl, 1; Wait
0x18002247a  lea     rcx, NtLmGlobalCritSect; Resource
0x180022481  xor     ebx, ebx
0x180022483  xor     edi, edi
0x180022485  call    cs:__imp_RtlAcquireResourceShared
0x18002248b  cmp     cs:NlpWorkstation, bl
0x180022491  jz      short loc_1800224B2
0x180022493  movzx   esi, cs:NtLmGlobalUnicodeDnsComputerNameString.Length
0x18002249a  mov     r8d, esi
0x18002249d  lea     rax, [rsi+2]
0x1800224a1  cmp     rax, 200h
0x1800224a7  ja      short loc_1800224DF
0x1800224a9  lea     rdx, NtLmGlobalUnicodeDnsComputerName
0x1800224b0  jmp     short loc_1800224CF
0x1800224b2  movzx   esi, cs:NtLmGlobalUnicodeDnsDomainNameString.Length
0x1800224b9  mov     r8d, esi; Size
0x1800224bc  lea     rax, [rsi+2]
0x1800224c0  cmp     rax, 200h
0x1800224c6  ja      short loc_1800224DF
0x1800224c8  lea     rdx, NtLmGlobalUnicodeDnsDomainName; Src
0x1800224cf  lea     rcx, [rbp+7C0h+pName1]; void *
0x1800224d6  call    memcpy_0
0x1800224db  mov     ebx, esi
0x1800224dd  shr     ebx, 1
0x1800224df  lea     rcx, NtLmGlobalCritSect; Resource
0x1800224e6  call    cs:__imp_RtlReleaseResource
0x1800224ec  mov     rsi, [rbp+7C0h+var_838]
0x1800224f0  movzx   r8d, word ptr [rsi]; Size
0x1800224f4  lea     rax, [r8+2]
0x1800224f8  cmp     rax, 200h
0x1800224fe  ja      short loc_180022515
0x180022500  mov     rdx, [rsi+8]; Src
0x180022504  lea     rcx, [rbp+7C0h+pName2]; void *
0x18002250b  mov     edi, r8d
0x18002250e  shr     edi, 1
0x180022510  call    memcpy_0
0x180022515  test    ebx, ebx
0x180022517  jz      short loc_180022576
0x180022519  test    edi, edi
0x18002251b  jz      short loc_180022576
0x18002251d  lea     rcx, [rbx+rbx]
0x180022521  cmp     rcx, 200h
0x180022528  jnb     loc_180024BC4
0x18002252e  xor     eax, eax
0x180022530  mov     [rbp+rcx+7C0h+pName1], ax
0x180022538  lea     rcx, [rdi+rdi]
0x18002253c  cmp     rcx, 200h
0x180022543  jnb     loc_180024BC4
0x180022549  mov     [rbp+rcx+7C0h+pName2], ax
0x180022551  lea     rdx, [rbp+7C0h+pName2]; pName2
0x180022558  lea     rcx, [rbp+7C0h+pName1]; pName1
0x18002255f  call    cs:__imp_DnsNameCompare_W
0x180022565  test    eax, eax
0x180022567  jnz     short loc_180022576
0x180022569  mov     [r15], al
0x18002256c  mov     eax, 0C0000064h
0x180022571  jmp     loc_180024B92
0x180022576  mov     rdi, [rsp+8C0h+SourceSid]
0x18002257b  xor     bl, bl
0x18002257d  mov     rax, [rbp+7C0h+var_708]
0x180022584  xor     ecx, ecx
0x180022586  xorps   xmm0, xmm0
0x180022589  mov     [rbp+7C0h+var_6E8], ecx
0x18002258f  movups  [rbp+7C0h+var_5E0], xmm0
0x180022596  mov     dword ptr [rbp+7C0h+var_5E0+8], ecx
0x18002259c  xor     edx, edx; SourceString
0x18002259e  mov     [rax], cl
0x1800225a0  mov     qword ptr [rbp+7C0h+var_6E4+4], rcx
0x1800225a7  mov     [rbp+7C0h+var_6D8], ecx
0x1800225ad  mov     qword ptr [rbp+7C0h+var_6D4+4], rcx
0x1800225b4  mov     [rbp+7C0h+var_790], ecx
0x1800225b7  mov     qword ptr [rbp+7C0h+var_78C+4], rcx
0x1800225bb  mov     [rbp+7C0h+var_728], ecx
0x1800225c1  mov     [rbp+7C0h+var_720], rcx
0x1800225c8  mov     [rbp+7C0h+var_750], ecx
0x1800225cb  mov     [rbp+7C0h+Src], rcx
0x1800225cf  lea     rcx, [rbp+7C0h+DestinationString]; DestinationString
0x1800225d6  movups  [rbp+7C0h+var_620], xmm0
0x1800225dd  mov     byte ptr [rbp+7C0h+var_5E0], 1
0x1800225e4  movups  xmmword ptr [rbp+7C0h+SourceString.Length], xmm0
0x1800225eb  movups  xmmword ptr [rbp+7C0h+var_600.Length], xmm0
0x1800225f2  movups  [rbp+7C0h+var_5F0], xmm0
0x1800225f9  call    cs:__imp_RtlInitUnicodeString
0x1800225ff  xor     edx, edx; SourceString
0x180022601  lea     rcx, [rbp+7C0h+var_7C8]; DestinationString
0x180022605  call    cs:__imp_RtlInitUnicodeString
0x18002260b  lea     rcx, [rbp+7C0h+SystemTime]; SystemTime
0x180022612  call    cs:__imp_NtQuerySystemTime
0x180022618  mov     ecx, r12d
0x18002261b  mov     dword ptr [rbp+7C0h+var_7E0], 10h
0x180022622  mov     byte ptr [r15], 1
0x180022626  sub     ecx, 1
0x180022629  jz      short loc_180022653
0x18002262b  sub     ecx, 1
0x18002262e  jz      short loc_18002263F
0x180022630  cmp     ecx, 1
0x180022633  jz      short loc_180022653
0x180022635  mov     eax, 0C0000003h
0x18002263a  jmp     loc_180024B92
0x18002263f  cmp     r13d, 1
0x180022643  mov     edx, 1D8h
0x180022648  mov     eax, 1D0h
0x18002264d  cmovnz  edx, eax
0x180022650  mov     dword ptr [rbp+7C0h+var_7E0], edx
0x180022653  mov     ecx, [rbp+7C0h+arg_48]
0x180022659  sub     ecx, 2
0x18002265c  jz      short loc_180022672
0x18002265e  sub     ecx, 1
0x180022661  jz      short loc_180022672
0x180022663  cmp     ecx, 3
0x180022666  jz      short loc_180022672
0x180022668  mov     eax, 0C0000003h
0x18002266d  jmp     loc_180024B92
0x180022672  xor     ecx, ecx
0x180022674  xor     al, al
0x180022676  mov     [rbp+7C0h+var_7B4], ecx
0x180022679  mov     qword ptr [rbp+7C0h+var_818.Length], rcx
0x18002267d  mov     [rbp+7C0h+var_840], al
0x180022680  mov     [rbp+7C0h+var_730], rcx
0x180022687  mov     [rbp+7C0h+var_6F8], rcx
0x18002268e  cmp     [rbp+7C0h+arg_40], ecx
0x180022694  jz      loc_180022791
0x18002269a  mov     rcx, rdi; Sid
0x18002269d  call    cs:__imp_RtlSubAuthorityCountSid
0x1800226a3  mov     rcx, rdi; Sid
0x1800226a6  movzx   r14d, byte ptr [rax]
0x1800226aa  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800226b0  lea     ecx, [r14+1]; SubAuthorityCount
0x1800226b4  mov     rbx, rax
0x1800226b7  call    cs:__imp_RtlLengthRequiredSid
0x1800226bd  mov     r12d, eax
0x1800226c0  mov     ecx, eax
0x1800226c2  mov     rax, cs:qword_180088390
0x1800226c9  mov     dword ptr [rbp+7C0h+var_7F0], r12d
0x1800226cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226d2  mov     [rbp+7C0h+var_768], rax
0x1800226d6  mov     rdi, rax
0x1800226d9  test    rax, rax
0x1800226dc  jnz     short loc_1800226F3
0x1800226de  mov     r12, [rbp+7C0h+var_838]
0x1800226e2  mov     r13, r15
0x1800226e5  mov     [r15], al
0x1800226e8  mov     r15d, 0C000009Ah
0x1800226ee  jmp     loc_180023DFD
0x1800226f3  lea     r8d, [r14+1]; SubAuthorityCount
0x1800226f7  mov     rdx, rbx; IdentifierAuthority
0x1800226fa  mov     rcx, rax; Sid
0x1800226fd  call    cs:__imp_RtlInitializeSid
0x180022703  mov     r15d, eax
0x180022706  test    eax, eax
0x180022708  jns     short loc_18002271C
0x18002270a  mov     r13, [rbp+7C0h+var_828]
0x18002270e  mov     r12, [rbp+7C0h+var_838]
0x180022712  mov     byte ptr [r13+0], 0
0x180022717  jmp     loc_180023DFD
0x18002271c  xor     sil, sil
0x18002271f  test    r14b, r14b
0x180022722  jz      short loc_180022760
0x180022724  mov     r12, [rsp+8C0h+SourceSid]
0x180022729  mov     r15, rdi
0x18002272c  nop     dword ptr [rax+00h]
0x180022730  movzx   ebx, sil
0x180022734  mov     rcx, r12; Sid
0x180022737  mov     edx, ebx; SubAuthority
0x180022739  call    cs:__imp_RtlSubAuthoritySid
0x18002273f  mov     edx, ebx; SubAuthority
0x180022741  mov     rcx, r15; Sid
0x180022744  mov     rdi, rax
0x180022747  call    cs:__imp_RtlSubAuthoritySid
0x18002274d  mov     ecx, [rdi]
0x18002274f  inc     sil
0x180022752  mov     [rax], ecx
0x180022754  cmp     sil, r14b
0x180022757  jb      short loc_180022730
0x180022759  mov     r12d, dword ptr [rbp+7C0h+var_7F0]
0x18002275d  mov     rdi, r15
  ... truncated ...
```
