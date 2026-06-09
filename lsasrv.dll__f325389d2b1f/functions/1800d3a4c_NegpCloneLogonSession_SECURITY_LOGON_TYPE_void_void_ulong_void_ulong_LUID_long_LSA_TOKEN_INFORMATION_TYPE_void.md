# NegpCloneLogonSession(_SECURITY_LOGON_TYPE,void *,void *,ulong,void * *,ulong *,_LUID *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x1800d3a4c`
- end: `0x1800d5210`
- name: `?NegpCloneLogonSession@@YAJW4_SECURITY_LOGON_TYPE@@PEAX1KPEAPEAXPEAKPEAU_LUID@@PEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@2PEAPEAU_UNICODE_STRING@@77PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `6084`
- prototype: `__int64 __fastcall(enum _SECURITY_LOGON_TYPE, void *, void *, unsigned int, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009ac50`

## callees

- `0x1800030c0`
- `0x180007dd8`
- `0x180008054`
- `0x180009330`
- `0x1800093b0`
- `0x180009410`
- `0x180009470`
- `0x18000c0f0`
- `0x18000c300`
- `0x18000d3b0`
- `0x18000dca0`
- `0x18000dd1c`
- `0x180011278`
- `0x1800163d0`
- `0x180016f70`
- `0x1800268d8`
- `0x18005e150`
- `0x18005e770`
- `0x18005faf0`
- `0x180072a80`
- `0x180074034`
- `0x18007835c`
- `0x180082b20`
- `0x180082b70`
- `0x18008ac70`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x1800d3a4c`
- `0x1800d5920`
- `0x1800f0584`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800d3e9a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800d3e9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d4ff7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d4ff7`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800d4cdd`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800d4cdd`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800d4481`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800d4481`
- `ntdll!NtClose` at `0x1800d51ea`
- `ntdll!NtClose` at `0x1800d51ea`
- `ntdll!RtlLengthSid` at `0x1800d40ec`
- `ntdll!RtlLengthSid` at `0x1800d410f`
- `ntdll!RtlLengthSid` at `0x1800d4694`
- `ntdll!RtlLengthSid` at `0x1800d46b7`
- `ntdll!RtlLengthSid` at `0x1800d40ec`
- `ntdll!RtlLengthSid` at `0x1800d410f`
- `ntdll!RtlLengthSid` at `0x1800d4694`
- `ntdll!RtlLengthSid` at `0x1800d46b7`
- `ntdll!RtlEqualSid` at `0x1800d43da`
- `ntdll!RtlEqualSid` at `0x1800d43fc`
- `ntdll!RtlEqualSid` at `0x1800d441e`
- `ntdll!RtlEqualSid` at `0x1800d4440`
- `ntdll!RtlEqualSid` at `0x1800d4973`
- `ntdll!RtlEqualSid` at `0x1800d499c`
- `ntdll!RtlEqualSid` at `0x1800d49c5`
- `ntdll!RtlEqualSid` at `0x1800d43da`
- `ntdll!RtlEqualSid` at `0x1800d43fc`
- `ntdll!RtlEqualSid` at `0x1800d441e`
- `ntdll!RtlEqualSid` at `0x1800d4440`
- `ntdll!RtlEqualSid` at `0x1800d4973`
- `ntdll!RtlEqualSid` at `0x1800d499c`
- `ntdll!RtlEqualSid` at `0x1800d49c5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d4ae5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d4ae5`
- `ntdll!RtlEnterCriticalSection` at `0x1800d4aaf`
- `ntdll!RtlEnterCriticalSection` at `0x1800d4aaf`
- `ntdll!NtQueryInformationToken` at `0x1800d3f59`
- `ntdll!NtQueryInformationToken` at `0x1800d3fd6`
- `ntdll!NtQueryInformationToken` at `0x1800d40cf`
- `ntdll!NtQueryInformationToken` at `0x1800d416a`
- `ntdll!NtQueryInformationToken` at `0x1800d42ab`
- `ntdll!NtQueryInformationToken` at `0x1800d4579`
- `ntdll!NtQueryInformationToken` at `0x1800d464e`
- `ntdll!NtQueryInformationToken` at `0x1800d471d`
- `ntdll!NtQueryInformationToken` at `0x1800d476a`
- `ntdll!NtQueryInformationToken` at `0x1800d4c92`
- `ntdll!NtQueryInformationToken` at `0x1800d3f59`
- `ntdll!NtQueryInformationToken` at `0x1800d3fd6`
- `ntdll!NtQueryInformationToken` at `0x1800d40cf`
- `ntdll!NtQueryInformationToken` at `0x1800d416a`
- `ntdll!NtQueryInformationToken` at `0x1800d42ab`
- `ntdll!NtQueryInformationToken` at `0x1800d4579`
- `ntdll!NtQueryInformationToken` at `0x1800d464e`
- `ntdll!NtQueryInformationToken` at `0x1800d471d`
- `ntdll!NtQueryInformationToken` at `0x1800d476a`
- `ntdll!NtQueryInformationToken` at `0x1800d4c92`
- `ntdll!NtOpenThreadToken` at `0x1800d3e8c`
- `ntdll!NtOpenThreadToken` at `0x1800d3e8c`
- `ntdll!RtlEqualUnicodeString` at `0x1800d4830`
- `ntdll!RtlEqualUnicodeString` at `0x1800d4830`
- `ntdll!RtlInitUnicodeString` at `0x1800d3b9b`
- `ntdll!RtlInitUnicodeString` at `0x1800d4ef5`
- `ntdll!RtlInitUnicodeString` at `0x1800d3b9b`
- `ntdll!RtlInitUnicodeString` at `0x1800d4ef5`

## pseudocode

```c
__int64 __fastcall NegpCloneLogonSession(
        enum _SECURITY_LOGON_TYPE a1,
        struct _LUID *a2,
        void *a3,
        unsigned int a4,
        void **a5,
        unsigned int *a6,
        struct _LUID *a7,
        int *a8,
        enum _LSA_TOKEN_INFORMATION_TYPE *a9,
        void **a10,
        struct _UNICODE_STRING **a11,
        struct _UNICODE_STRING **a12,
        struct _UNICODE_STRING **a13,
        struct _SECPKG_PRIMARY_CRED *a14,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a15)
{
  struct _SECPKG_PRIMARY_CRED *v15; // r13
  struct _LSAP_LOGON_SESSION *v19; // r15
  struct _RTL_BALANCED_NODE *v20; // r12
  LsaHandleCache *v22; // rcx
  __int64 v23; // rdx
  __int64 LowPart; // r9
  struct _LSAP_LOGON_SESSION *LogonSession; // rax
  struct _LSAP_LOGON_SESSION *v26; // r14
  LsaHandleCache *v27; // rcx
  NTSTATUS v28; // ebx
  __int64 v29; // rdx
  int v30; // eax
  struct _LUID *v31; // rdx
  LsaHandleCache *v32; // rcx
  __int64 v33; // rdx
  enum _SECURITY_LOGON_TYPE v34; // edi
  struct _RTL_BALANCED_NODE **v35; // rsi
  struct _RTL_BALANCED_NODE *Buffer; // rcx
  struct _RTL_BALANCED_NODE **v37; // rsi
  struct _RTL_BALANCED_NODE *v38; // rcx
  struct _RTL_BALANCED_NODE **v39; // rsi
  struct _RTL_BALANCED_NODE *v40; // rcx
  struct _LUID *v41; // rdi
  __int64 v42; // r13
  struct _RTL_BALANCED_NODE *v43; // r14
  NTSTATUS v44; // eax
  struct _TOKEN_GROUPS *v45; // rdx
  struct _RTL_BALANCED_NODE *v46; // rsi
  LsaHandleCache *v47; // rcx
  __int64 v48; // rdx
  NTSTATUS v49; // eax
  __int64 v50; // r8
  __int64 v51; // r9
  int v52; // edi
  unsigned __int64 v53; // rbx
  unsigned __int64 v54; // rcx
  __int64 v55; // rcx
  unsigned __int64 v56; // rcx
  void *v57; // rsp
  void *v58; // rsp
  _DWORD *v59; // rax
  ULONG v60; // eax
  __int64 v61; // rax
  ULONG v62; // eax
  __int64 v63; // r8
  __int64 v64; // r9
  unsigned __int64 v65; // rbx
  struct _RTL_BALANCED_NODE **Groups; // rax
  unsigned __int64 v67; // rcx
  __int64 v68; // rcx
  unsigned __int64 v69; // rcx
  void *v70; // rsp
  void *v71; // rsp
  struct _TOKEN_GROUPS *v72; // rax
  NTSTATUS v73; // eax
  LsaHandleCache *v74; // rcx
  __int64 v75; // rdx
  __int64 v76; // r9
  struct _TOKEN_GROUPS *v77; // r8
  struct _TOKEN_GROUPS *v78; // r9
  __int64 v79; // rcx
  LsaHandleCache *v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // r9
  NTSTATUS v83; // eax
  __int64 v84; // r8
  __int64 v85; // r9
  unsigned __int64 v86; // rbx
  unsigned __int64 v87; // rcx
  __int64 v88; // rcx
  unsigned __int64 v89; // rcx
  void *v90; // rsp
  void *v91; // rsp
  _DWORD *v92; // rax
  LsaHandleCache *v93; // rcx
  __int64 v94; // rdx
  __int64 v95; // r9
  ULONG v96; // eax
  __int64 v97; // rax
  ULONG v98; // eax
  void *v99; // r8
  NTSTATUS v100; // eax
  void *v101; // rax
  LsaHandleCache *v102; // rcx
  __int64 v103; // rdx
  __int64 v104; // r9
  int v105; // eax
  char *v106; // rax
  char *v107; // r15
  LsaHandleCache *v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // r9
  __int64 v111; // rax
  __int64 v112; // rax
  struct _UNICODE_STRING **v113; // rbx
  __int64 v114; // rax
  int LogonSessionAccountInfo; // eax
  __int64 v116; // rax
  bool v117; // zf
  __int64 v118; // r14
  __int64 v119; // rdx
  char *v120; // rcx
  int v121; // eax
  LsaHandleCache *v122; // rcx
  __int64 v123; // rdx
  __int64 v124; // r9
  struct _SECPKG_PRIMARY_CRED *v125; // r15
  struct _RTL_BALANCED_NODE *UserSid; // rcx
  NTSTATUS v127; // eax
  char *v128; // r12
  struct _LSAP_LOGON_SESSION *v129; // rax
  LsaHandleCache *v130; // rcx
  __int64 v131; // rdx
  __int64 v132; // r9
  int v133; // eax
  unsigned __int16 *v134; // r15
  int v135; // eax
  char *v136; // r14
  const void **v137; // rax
  unsigned __int64 v138; // rcx
  char *v139; // rbx
  enum _SECURITY_LOGON_TYPE v140; // r14d
  int v141; // eax
  void **v142; // rdi
  unsigned int *v143; // rsi
  void *v144; // rax
  size_t v145; // r8
  void *v146; // rdx
  LsaHandleCache *v147; // rcx
  __int64 v148; // rdx
  __int64 v149; // r9
  struct _RTL_BALANCED_NODE *v150; // rcx
  struct _TOKEN_GROUPS *v151; // rcx
  struct _RTL_BALANCED_NODE *v152; // rcx
  struct _RTL_BALANCED_NODE *v153; // rcx
  struct _LSAP_LOGON_SESSION *v154; // rax
  _BYTE v155[32]; // [rsp+0h] [rbp-30h] BYREF
  struct _RTL_BALANCED_NODE **v156; // [rsp+30h] [rbp+0h] BYREF
  struct _RTL_BALANCED_NODE *v157; // [rsp+38h] [rbp+8h] BYREF
  struct _LSAP_LOGON_SESSION *v158; // [rsp+40h] [rbp+10h]
  ULONG TokenInformationLength; // [rsp+48h] [rbp+18h] BYREF
  enum _SECURITY_LOGON_TYPE v160; // [rsp+4Ch] [rbp+1Ch]
  struct _LSAP_LOGON_SESSION *v161; // [rsp+50h] [rbp+20h]
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF
  struct _RTL_BALANCED_NODE **v163; // [rsp+60h] [rbp+30h]
  struct _TOKEN_GROUPS *v164; // [rsp+68h] [rbp+38h]
  struct _LUID *v165; // [rsp+70h] [rbp+40h]
  LUID LocallyUniqueId; // [rsp+78h] [rbp+48h] BYREF
  void *v167; // [rsp+80h] [rbp+50h]
  struct _SECPKG_PRIMARY_CRED *v168; // [rsp+88h] [rbp+58h]
  struct _TOKEN_GROUPS *v169; // [rsp+90h] [rbp+60h]
  BOOL v170; // [rsp+98h] [rbp+68h]
  int v171; // [rsp+9Ch] [rbp+6Ch] BYREF
  struct _UNICODE_STRING **v172; // [rsp+A0h] [rbp+70h]
  unsigned int v173; // [rsp+A8h] [rbp+78h]
  struct _UNICODE_STRING **v174; // [rsp+B0h] [rbp+80h]
  struct _MSV1_0_INTERACTIVE_LOGON *v175; // [rsp+B8h] [rbp+88h] BYREF
  struct _UNICODE_STRING **v176; // [rsp+C0h] [rbp+90h]
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v177; // [rsp+C8h] [rbp+98h]
  void *v178; // [rsp+D0h] [rbp+A0h]
  void **v179; // [rsp+D8h] [rbp+A8h]
  unsigned int *v180; // [rsp+E0h] [rbp+B0h]
  LUID *v181; // [rsp+E8h] [rbp+B8h]
  int *v182; // [rsp+F0h] [rbp+C0h]
  enum _LSA_TOKEN_INFORMATION_TYPE *v183; // [rsp+F8h] [rbp+C8h]
  void **v184; // [rsp+100h] [rbp+D0h]
  struct _UNICODE_STRING DestinationString; // [rsp+108h] [rbp+D8h] BYREF
  char Src[8]; // [rsp+120h] [rbp+F0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+128h] [rbp+F8h] BYREF
  __m128i si128; // [rsp+130h] [rbp+100h]
  __int64 v189; // [rsp+148h] [rbp+118h]
  __int64 v190; // [rsp+150h] [rbp+120h]
  int v191; // [rsp+1B8h] [rbp+188h]
  __int128 TokenInformation; // [rsp+1C0h] [rbp+190h] BYREF
  __int128 v193; // [rsp+1D0h] [rbp+1A0h]
  __int128 v194; // [rsp+1E0h] [rbp+1B0h]
  __int64 v195; // [rsp+1F0h] [rbp+1C0h]
  _BYTE v196[128]; // [rsp+200h] [rbp+1D0h] BYREF

  v15 = a14;
  v179 = a5;
  v181 = a7;
  v182 = a8;
  v183 = a9;
  v184 = a10;
  v172 = a11;
  v174 = a12;
  v167 = a2;
  v160 = a1;
  v176 = a13;
  v19 = 0;
  v178 = a3;
  v180 = a6;
  v20 = 0;
  TokenHandle = 0;
  v158 = 0;
  v157 = 0;
  LocallyUniqueId = 0;
  v175 = 0;
  TokenInformationLength = 0;
  v171 = 0;
  v195 = 0;
  v173 = a4;
  v168 = a14;
  v177 = a15;
  TokenInformation = 0;
  v193 = 0;
  v194 = 0;
  memset_0(Src, 0, 0xA0u);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"_SA_{262E99C9-6160-4871-ACEC-4E61736B6F21}");
  *a15 = 0;
  if ( a1 != RemoteInteractive )
  {
    v28 = LsapImpersonateClientEx(0);
    if ( v28 >= 0 )
    {
      v28 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
      RevertToSelf();
      if ( v28 >= 0 )
      {
        v26 = 0;
        v165 = 0;
        v161 = 0;
        goto LABEL_61;
      }
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v28;
      v29 = 39;
    }
    else
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v28;
      v29 = 38;
    }
LABEL_18:
    WPP_SF_d(*((_QWORD *)v27 + 2), v29, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, (unsigned int)v28);
    return (unsigned int)v28;
  }
  if ( !(unsigned __int8)LsaIAllowProtectedCredLogon() )
    return 3221225582LL;
  if ( a4 < 0x40 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 3221225639LL;
    v23 = 33;
    LowPart = a4;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, LowPart);
    return 3221225639LL;
  }
  if ( a2->LowPart != 84 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 3221225639LL;
    LowPart = a2->LowPart;
    v23 = 34;
    goto LABEL_12;
  }
  LogonSession = LsapLocateLogonSession(a2 + 7);
  v161 = LogonSession;
  v26 = LogonSession;
  if ( !LogonSession )
  {
    v27 = WPP_GLOBAL_Control;
    v28 = -1073741729;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v28;
    v29 = 35;
    goto LABEL_18;
  }
  TokenHandle = (void *)*((_QWORD *)LogonSession + 36);
  v165 = a2;
  v30 = LsapDuplicateString(&a2[1], (char *)LogonSession + 176);
  v28 = v30;
  if ( v30 < 0 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    v33 = 36;
LABEL_23:
    WPP_SF_d(*((_QWORD *)v32 + 2), v33, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, (unsigned int)v30);
LABEL_24:
    v34 = v160;
    goto LABEL_25;
  }
  v30 = LsapDuplicateString(&a2[3], (char *)v26 + 160);
  v28 = v30;
  if ( v30 < 0 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    v33 = 37;
    goto LABEL_23;
  }
LABEL_61:
  v42 = LsapAllocate(64);
  if ( !v42 )
  {
    v28 = -1073741801;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, 3221225495LL);
    goto LABEL_350;
  }
  v43 = 0;
  v163 = 0;
  v44 = NtQueryInformationToken(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &TokenInformationLength);
  v28 = v44;
  if ( v44 < 0 )
  {
    v46 = 0;
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_332;
    v48 = 41;
    goto LABEL_69;
  }
  *(_QWORD *)v42 = v193;
  TokenInformationLength = 128;
  v49 = NtQueryInformationToken(TokenHandle, TokenUser, v196, 0x80u, &TokenInformationLength);
  v28 = v49;
  v52 = 15;
  if ( v49 == -2147483643 || v49 == -1073741789 )
  {
    v53 = TokenInformationLength;
    v46 = 0;
    v156 = 0;
    if ( !TokenInformationLength )
      goto LABEL_358;
    if ( TokenInformationLength > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_358;
    v54 = TokenInformationLength + g_ulAdditionalProbeSize + 8;
    if ( v54 < TokenInformationLength || !(unsigned int)VerifyStackAvailable(v54, v45, v50, v51) )
      goto LABEL_358;
    v55 = v53 + 23;
    if ( v53 + 23 <= v53 + 8 )
      v55 = 0xFFFFFFFFFFFFFF0LL;
    v56 = v55 & 0xFFFFFFFFFFFFFFF0uLL;
    v57 = alloca(v56);
    v58 = alloca(v56);
    v46 = (struct _RTL_BALANCED_NODE *)&v156;
    v156 = (struct _RTL_BALANCED_NODE **)&v156;
    if ( v155 == (_BYTE *)-48LL || (v46 = (struct _RTL_BALANCED_NODE *)&v157, (v156 = &v157) == 0) )
    {
LABEL_358:
      if ( v53 + 8 >= v53 )
      {
        v59 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v156 = (struct _RTL_BALANCED_NODE **)v59;
        v46 = (struct _RTL_BALANCED_NODE *)v59;
        if ( v59 )
        {
          v46 = (struct _RTL_BALANCED_NODE *)(v59 + 2);
          *v59 = 1885431112;
          v156 = (struct _RTL_BALANCED_NODE **)(v59 + 2);
        }
      }
    }
    if ( !v46 )
    {
      v28 = -1073741801;
LABEL_328:
      v147 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_332;
      v148 = 42;
      v149 = (unsigned int)v28;
LABEL_331:
      WPP_SF_d(*((_QWORD *)v147 + 2), v148, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, v149);
      v46 = (struct _RTL_BALANCED_NODE *)v156;
      goto LABEL_332;
    }
    v28 = NtQueryInformationToken(TokenHandle, TokenUser, v46, TokenInformationLength, &TokenInformationLength);
  }
  else
  {
    v46 = (struct _RTL_BALANCED_NODE *)v196;
    v156 = (struct _RTL_BALANCED_NODE **)v196;
  }
  if ( v28 < 0 )
    goto LABEL_328;
  *(_DWORD *)(v42 + 16) = 0;
  v60 = RtlLengthSid(v46->Children[0]);
  v61 = LsapAllocate(v60);
  *(_QWORD *)(v42 + 8) = v61;
  if ( !v61 )
  {
    v28 = -1073741801;
    v147 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_332;
    v148 = 43;
    v149 = 3221225495LL;
    goto LABEL_331;
  }
  v62 = RtlLengthSid(v46->Children[0]);
  memcpy_0(*(void **)(v42 + 8), v46->Children[0], v62);
  if ( v46 != (struct _RTL_BALANCED_NODE *)v196 && v46[-1].16 == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  v46 = 0;
  v156 = 0;
  v44 = NtQueryInformationToken(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength);
  v28 = v44;
  if ( v44 != -2147483643 && v44 != -1073741789 )
  {
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_332;
    v48 = 44;
    goto LABEL_69;
  }
  v65 = TokenInformationLength;
  Groups = 0;
  v164 = 0;
  if ( !TokenInformationLength )
    goto LABEL_106;
  if ( TokenInformationLength > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_106;
  v67 = TokenInformationLength + g_ulAdditionalProbeSize + 8;
  if ( v67 < TokenInformationLength )
    goto LABEL_106;
  if ( !(unsigned int)VerifyStackAvailable(v67, v45, v63, v64) )
  {
    Groups = 0;
    goto LABEL_106;
  }
  v68 = v65 + 23;
  if ( v65 + 23 <= v65 + 8 )
    v68 = 0xFFFFFFFFFFFFFF0LL;
  v69 = v68 & 0xFFFFFFFFFFFFFFF0uLL;
  v70 = alloca(v69);
  v71 = alloca(v69);
  Groups = (struct _RTL_BALANCED_NODE **)&v156;
  v164 = (struct _TOKEN_GROUPS *)&v156;
  if ( v155 == (_BYTE *)-48LL
    || (LODWORD(v156) = 1801679955, Groups = &v157, (v164 = (struct _TOKEN_GROUPS *)&v157) == 0) )
  {
LABEL_106:
    if ( v65 + 8 >= v65 )
    {
      v72 = (struct _TOKEN_GROUPS *)((__int64 (*)(void))g_pfnAllocate)();
      v164 = v72;
      if ( !v72 )
        goto LABEL_110;
      v72->GroupCount = 1885431112;
      Groups = (struct _RTL_BALANCED_NODE **)v72->Groups;
      v164 = (struct _TOKEN_GROUPS *)Groups;
    }
  }
  if ( !Groups )
  {
LABEL_110:
    v44 = -1073741801;
    v28 = -1073741801;
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_332;
    v48 = 45;
LABEL_69:
    WPP_SF_d(*((_QWORD *)v47 + 2), v48, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, (unsigned int)v44);
    goto LABEL_332;
  }
  v169 = 0;
  v73 = NtQueryInformationToken(TokenHandle, TokenGroups, Groups, TokenInformationLength, &TokenInformationLength);
  v28 = v73;
  if ( v73 < 0 )
  {
    v74 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_285;
    v75 = 46;
LABEL_117:
    v76 = (unsigned int)v73;
    goto LABEL_118;
  }
  LOBYTE(v52) = 0;
  v170 = v52;
  if ( v160 == RemoteInteractive )
  {
    if ( !LsapSidPresentInGroups(v164, *((void **)WellKnownSids + 96)) )
    {
      v28 = -1073741714;
      v74 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_285;
      v75 = 47;
      v76 = 3221225582LL;
LABEL_118:
      WPP_SF_d(*((_QWORD *)v74 + 2), v75, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, v76);
      goto LABEL_285;
    }
    v170 = LsapSidPresentInGroups(v164, *((void **)WellKnownSids + 282)) != 0;
  }
  v169 = (struct _TOKEN_GROUPS *)LsapAllocate(16LL * v164->GroupCount + 24);
  if ( !v169 )
  {
    v73 = -1073741801;
    v28 = -1073741801;
    v74 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_285;
    v75 = 48;
    goto LABEL_117;
  }
  if ( !RtlEqualSid(*(PSID *)(v42 + 8), *((PSID *)WellKnownSids + 90))
    && !RtlEqualSid(*(PSID *)(v42 + 8), *((PSID *)WellKnownSids + 162))
    && !RtlEqualSid(*(PSID *)(v42 + 8), *((PSID *)WellKnownSids + 156))
    && !RtlEqualSid(*(PSID *)(v42 + 8), *((PSID *)WellKnownSids + 168)) )
  {
    LODWORD(v20) = 1;
  }
  while ( 1 )
  {
    v77 = v164;
    if ( (unsigned int)v43 >= v164->GroupCount )
      goto LABEL_143;
    if ( (_DWORD)v20 )
    {
      if ( *RtlSubAuthorityCountSid(v164->Groups[(unsigned int)v43].Sid) <= 2u )
        goto LABEL_142;
      v77 = v164;
    }
    v78 = v169;
    v79 = (unsigned int)v19;
    v169->Groups[v79].Attributes = v77->Groups[(unsigned int)v43].Attributes;
    v28 = LsapDuplicateSid2(&v78->Groups[v79].Sid, v77->Groups[(unsigned int)v43].Sid);
    LODWORD(v19) = (_DWORD)v19 + 1;
    if ( v28 < 0 )
      break;
LABEL_142:
    LODWORD(v43) = (_DWORD)v43 + 1;
  }
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
      (unsigned int)v28);
    v169->GroupCount = (unsigned int)v19;
LABEL_144:
    v80 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v81 = 50;
      v82 = (unsigned int)v28;
      goto LABEL_147;
    }
    goto LABEL_148;
  }
LABEL_143:
  v45 = v169;
  v169->GroupCount = (unsigned int)v19;
  v19 = 0;
  if ( v28 < 0 )
    goto LABEL_144;
  *(_QWORD *)(v42 + 24) = v45;
  v169 = 0;
  TokenInformationLength = 128;
  v83 = NtQueryInformationToken(TokenHandle, TokenPrimaryGroup, v196, 0x80u, &TokenInformationLength);
  v28 = v83;
  if ( v83 == -2147483643 || v83 == -1073741789 )
  {
    v86 = TokenInformationLength;
    v43 = 0;
    if ( !TokenInformationLength )
      goto LABEL_359;
    if ( TokenInformationLength > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_359;
    v87 = TokenInformationLength + g_ulAdditionalProbeSize + 8;
    if ( v87 < TokenInformationLength || !(unsigned int)VerifyStackAvailable(v87, v45, v84, v85) )
      goto LABEL_359;
    v88 = v86 + 23;
    if ( v86 + 23 <= v86 + 8 )
      v88 = 0xFFFFFFFFFFFFFF0LL;
    v89 = v88 & 0xFFFFFFFFFFFFFFF0uLL;
    v90 = alloca(v89);
    v91 = alloca(v89);
    v43 = (struct _RTL_BALANCED_NODE *)&v156;
    if ( v155 == (_BYTE *)-48LL || (LODWORD(v156) = 1801679955, (v43 = (struct _RTL_BALANCED_NODE *)&v157) == 0) )
    {
LABEL_359:
      if ( v86 + 8 >= v86 )
      {
        v92 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v43 = (struct _RTL_BALANCED_NODE *)v92;
        if ( v92 )
        {
          *v92 = 1885431112;
          v43 = (struct _RTL_BALANCED_NODE *)(v92 + 2);
        }
      }
    }
    v28 = NtQueryInformationToken(TokenHandle, TokenPrimaryGroup, v43, TokenInformationLength, &TokenInformationLength);
  }
  else
  {
    v43 = (struct _RTL_BALANCED_NODE *)v196;
  }
  if ( v28 < 0 )
  {
    v93 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v94 = 51;
      v95 = (unsigned int)v28;
      goto LABEL_171;
    }
    goto LABEL_172;
  }
  v96 = RtlLengthSid(v43->Children[0]);
  v97 = LsapAllocate(v96);
  *(_QWORD *)(v42 + 32) = v97;
  if ( v97 )
  {
    v98 = RtlLengthSid(v43->Children[0]);
    memcpy_0(*(void **)(v42 + 32), v43->Children[0], v98);
    if ( v43 != (struct _RTL_BALANCED_NODE *)v196 && v43[-1].16 == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    *(_QWORD *)(v42 + 40) = 0;
    TokenInformationLength = 0;
    v43 = 0;
    v99 = *(void **)(v42 + 40);
    v163 = 0;
    v100 = NtQueryInformationToken(TokenHandle, TokenPrivileges, v99, 0, &TokenInformationLength);
    v28 = v100;
    if ( v100 == -2147483643 || v100 == -1073741789 )
    {
      v101 = (void *)LsapAllocate(TokenInformationLength);
      *(_QWORD *)(v42 + 40) = v101;
      if ( !v101 )
      {
        v28 = -1073741801;
LABEL_183:
        v102 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v103 = 53;
          v104 = (unsigned int)v28;
          goto LABEL_186;
        }
        goto LABEL_150;
      }
      v28 = NtQueryInformationToken(TokenHandle, TokenPrivileges, v101, TokenInformationLength, &TokenInformationLength);
    }
    if ( v28 < 0 )
      goto LABEL_183;
    if ( v160 == RemoteInteractive )
    {
      LsapAuSetLogonPrivilegeStates(
        RemoteInteractive,
        **(_DWORD **)(v42 + 40),
        (struct _LUID_AND_ATTRIBUTES *)(*(_QWORD *)(v42 + 40) + 4LL));
      v106 = (char *)v167;
    }
    else
    {
      v105 = NegpMapLogonRequest(v167, v178, v173, &v175);
      v28 = v105;
      if ( v105 < 0 )
      {
        v102 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v103 = 54;
          v104 = (unsigned int)v105;
LABEL_186:
          WPP_SF_d(*((_QWORD *)v102 + 2), v103, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, v104);
        }
LABEL_150:
        v20 = v43;
LABEL_151:
        v46 = v43;
        goto LABEL_285;
      }
      v106 = (char *)v175;
      v167 = v175;
    }
    v107 = v106 + 40;
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)(v106 + 40), &DestinationString, 1u) )
    {
      v28 = -1073741557;
      v108 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v109 = 55;
        v110 = 3221225739LL;
        goto LABEL_198;
      }
      goto LABEL_149;
    }
    v111 = LsapAllocate(16);
    *v172 = (struct _UNICODE_STRING *)v111;
    if ( !v111 )
    {
      v28 = -1073741801;
      v108 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_149;
      v109 = 56;
      goto LABEL_203;
    }
    v112 = LsapAllocate(16);
    v113 = v174;
    *v174 = (struct _UNICODE_STRING *)v112;
    if ( !v112 )
    {
      v28 = -1073741801;
      v108 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_149;
      v109 = 57;
      goto LABEL_203;
    }
    v114 = LsapAllocate(16);
    *v176 = (struct _UNICODE_STRING *)v114;
    if ( !v114 )
    {
      v28 = -1073741801;
      v108 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_149;
      v109 = 58;
LABEL_203:
      v110 = 3221225495LL;
LABEL_198:
      WPP_SF_d(*((_QWORD *)v108 + 2), v109, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, v110);
LABEL_149:
      v19 = (struct _LSAP_LOGON_SESSION *)v43;
      goto LABEL_150;
    }
    if ( (_DWORD)v20 )
    {
      LogonSessionAccountInfo = LsapGetLogonSessionAccountInfoEx((char *)&TokenInformation + 8, *v172, *v113, 0);
    }
    else
    {
      if ( RtlEqualSid(*(PSID *)(v42 + 8), *((PSID *)WellKnownSids + 156)) )
      {
        v116 = 26;
      }
      else if ( RtlEqualSid(*(PSID *)(v42 + 8), *((PSID *)WellKnownSids + 162)) )
      {
        v116 = 27;
      }
      else
      {
        v117 = RtlEqualSid(*(PSID *)(v42 + 8), *((PSID *)WellKnownSids + 168)) == 0;
        v116 = 15;
        if ( !v117 )
          v116 = 28;
      }
      v118 = 48 * v116;
      v119 = 32;
      v120 = (char *)WellKnownSids + 48 * v116;
      if ( *((_DWORD *)v120 + 2) != 3 )
        v119 = 16;
      v121 = LsapDuplicateString(*v172, &v120[v119]);
      v28 = v121;
      if ( v121 < 0 )
      {
        v80 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v81 = 59;
          v82 = (unsigned int)v121;
LABEL_147:
          WPP_SF_d(*((_QWORD *)v80 + 2), v81, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, v82);
        }
LABEL_148:
        v43 = (struct _RTL_BALANCED_NODE *)v163;
        goto LABEL_149;
      }
      LogonSessionAccountInfo = LsapDuplicateString(*v174, (char *)WellKnownSids + v118 + 32);
      v43 = (struct _RTL_BALANCED_NODE *)v163;
    }
    v28 = LogonSessionAccountInfo;
    if ( LogonSessionAccountInfo < 0 )
    {
      v122 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v123 = 60;
        goto LABEL_231;
      }
LABEL_233:
      v19 = v158;
      goto LABEL_172;
    }
    if ( v160 != RemoteInteractive )
    {
      v128 = (char *)v167;
      v127 = LsapDuplicateString(&v168->DomainName, (char *)v167 + 8);
      v28 = v127;
      if ( v127 >= 0 )
      {
        v127 = LsapDuplicateString(&v168->DownlevelName, v128 + 24);
        v28 = v127;
        if ( v127 >= 0 )
        {
          v127 = LsapDuplicateString(&v168->Password, v107);
          v28 = v127;
          if ( v127 >= 0 )
          {
            v125 = v168;
            v127 = LsapDuplicateSid(&v168->UserSid, *(_QWORD *)(v42 + 8));
            v28 = v127;
            if ( v127 >= 0 )
            {
              v125->Flags = 1;
              goto LABEL_268;
            }
            v122 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_233;
            }
            v123 = 66;
          }
          else
          {
            v122 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_233;
            }
            v123 = 65;
          }
        }
        else
        {
          v122 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_233;
          }
          v123 = 64;
        }
      }
      else
      {
        v122 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_233;
        }
        v123 = 63;
      }
LABEL_247:
      v124 = (unsigned int)v127;
LABEL_232:
      WPP_SF_d(*((_QWORD *)v122 + 2), v123, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, v124);
      goto LABEL_233;
    }
    if ( LsapDisableRestrictedAdminOutboundCreds )
    {
      v125 = v168;
    }
    else
    {
      RtlEnterCriticalSection(&NegComputerNamesLock);
      v125 = v168;
      v28 = NegpCopyCredsToBuffer(&NegPrimarySystemCredentials, NegSupplementalSystemCredentials, v168, v177);
      RtlLeaveCriticalSection(&NegComputerNamesLock);
      if ( v28 < 0 )
      {
        v122 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_233;
        }
        v123 = 61;
LABEL_231:
        v124 = (unsigned int)v28;
        goto LABEL_232;
      }
      UserSid = (struct _RTL_BALANCED_NODE *)v125->UserSid;
      if ( UserSid )
      {
        LsapSubProv_FreeRoutine(UserSid, v45);
        v125->UserSid = 0;
      }
    }
    v127 = LsapDuplicateSid(&v125->UserSid, *(_QWORD *)(v42 + 8));
    v28 = v127;
    if ( v127 < 0 )
    {
      v122 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v123 = 62;
      goto LABEL_247;
    }
    if ( v170 )
      v125->Flags |= 0x40u;
    v125->Flags |= 0x4000u;
    v128 = (char *)v167;
LABEL_268:
    v127 = NtQueryInformationToken(TokenHandle, TokenElevationType, &v171, 4u, &TokenInformationLength);
    v28 = v127;
    if ( v127 < 0 )
    {
      v122 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v123 = 67;
      goto LABEL_247;
    }
    if ( v160 != RemoteInteractive && v171 == 3 )
      v125->Flags |= 0x20u;
    NtAllocateLocallyUniqueId(&LocallyUniqueId);
    v127 = LsapCreateLogonSession(&LocallyUniqueId);
    v28 = v127;
    if ( v127 < 0 )
    {
      v122 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_233;
      v123 = 68;
      goto LABEL_247;
    }
    v129 = LsapLocateLogonSession(&LocallyUniqueId);
    v158 = v129;
    v19 = v129;
    if ( !v129 )
    {
      v28 = -1073741729;
      v130 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v131 = 69;
        v132 = 3221225567LL;
        goto LABEL_283;
      }
      goto LABEL_284;
    }
    v133 = LsapDuplicateString((char *)v129 + 560, v128 + 8);
    v28 = v133;
    if ( v133 >= 0 )
    {
      v134 = (unsigned __int16 *)v167;
      v135 = LsapDuplicateString((char *)v158 + 544, (char *)v167 + 24);
      v28 = v135;
      if ( v135 < 0 )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
            (unsigned int)v135);
        }
        v19 = v158;
        goto LABEL_284;
      }
      v157 = (struct _RTL_BALANCED_NODE *)NegpBuildLogonSession(
                                            &LocallyUniqueId,
                                            0,
                                            *(unsigned __int64 *)&NegPackageId,
                                            *(unsigned __int64 *)&NegPackageId);
      if ( v157 )
      {
        v136 = (char *)LsapAllocate(v134[12] + 4LL + *((unsigned __int16 *)v128 + 4));
        if ( v136 )
        {
          memcpy_0(v136, *((const void **)v167 + 2), *((unsigned __int16 *)v128 + 4));
          v137 = (const void **)v167;
          v138 = (unsigned __int64)*((unsigned __int16 *)v128 + 4) >> 1;
          *(_WORD *)&v136[2 * v138] = 92;
          v139 = &v136[2 * v138];
          memcpy_0(v139 + 2, v137[4], v134[12]);
          v20 = v157;
          *(_WORD *)&v139[2 * ((unsigned __int64)v134[12] >> 1) + 2] = 0;
          RtlInitUnicodeString((PUNICODE_STRING)&v20[2].Right, (PCWSTR)v136);
        }
        else
        {
          v20 = v157;
        }
        v140 = v160;
        v20[3].Children[1] = (struct _RTL_BALANCED_NODE *)*((_QWORD *)&TokenInformation + 1);
        if ( v140 != RemoteInteractive )
          HIDWORD(v20[3].ParentValue) = 1;
        NegpDerefLogonSession(v20, 0);
        v168->LogonId = LocallyUniqueId;
        v141 = LsapMergeDsNamesToLogonSession((struct _LUID *)&v20[3].Right, &LocallyUniqueId);
        v28 = v141;
        if ( v141 < 0 )
        {
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              73,
              WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
              (unsigned int)v141);
          }
          v43 = (struct _RTL_BALANCED_NODE *)v163;
          v19 = v158;
          goto LABEL_151;
        }
        v142 = v179;
        v143 = v180;
        v19 = v158;
        *v179 = 0;
        *v143 = 0;
        if ( v140 == RemoteInteractive )
        {
          if ( !LsapDisableRestrictedAdminOutboundCreds )
            *((_DWORD *)v19 + 78) |= 0x40000000u;
          *((_DWORD *)v19 + 78) |= 0x1000000u;
          v144 = LsapClientAllocate(0xA0u);
          *v142 = v144;
          if ( v144 )
          {
            *v143 = 160;
            memset_0(Src, 0, 0xA0u);
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            v145 = *v143;
            v146 = *v142;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v189 = 0x7FFFFFFFFFFFFFFFLL;
            v190 = 0x7FFFFFFFFFFFFFFFLL;
            v191 = 163872;
            LsapCopyToClient(Src, v146, v145);
          }
        }
        *v181 = LocallyUniqueId;
        *v182 = 0;
        *v183 = LsaTokenInformationV1;
        *v184 = (void *)v42;
        v42 = 0;
        v43 = 0;
        v46 = 0;
      }
      else
      {
        v28 = -1073741801;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            72,
            WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
            3221225495LL);
        }
        v19 = v158;
        v20 = v157;
        v46 = (struct _RTL_BALANCED_NODE *)v156;
      }
    }
    else
    {
      v130 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v131 = 70;
        v132 = (unsigned int)v133;
LABEL_283:
        WPP_SF_d(*((_QWORD *)v130 + 2), v131, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, v132);
      }
LABEL_284:
      v20 = v157;
      v46 = v157;
    }
  }
  else
  {
    v28 = -1073741801;
    v93 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v94 = 52;
      v95 = 3221225495LL;
LABEL_171:
      WPP_SF_d(*((_QWORD *)v93 + 2), v94, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, v95);
    }
LABEL_172:
    v20 = (struct _RTL_BALANCED_NODE *)v19;
    v46 = (struct _RTL_BALANCED_NODE *)v19;
  }
LABEL_285:
  if ( v164[-1].Groups[0].Attributes == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v169 )
    LsapFreeTokenGroups(v169);
  if ( v42 )
  {
LABEL_332:
    v150 = *(struct _RTL_BALANCED_NODE **)(v42 + 8);
    if ( v150 )
      LsapSubProv_FreeRoutine(v150, v45);
    v151 = *(struct _TOKEN_GROUPS **)(v42 + 24);
    if ( v151 )
      LsapFreeTokenGroups(v151);
    v152 = *(struct _RTL_BALANCED_NODE **)(v42 + 40);
    if ( v152 )
      LsapSubProv_FreeRoutine(v152, v45);
    v153 = *(struct _RTL_BALANCED_NODE **)(v42 + 32);
    if ( v153 )
      LsapSubProv_FreeRoutine(v153, v45);
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v42, v45);
  }
  v31 = v165;
  v154 = v161;
  if ( v46 != (struct _RTL_BALANCED_NODE *)v196 && v46 && v46[-1].16 == 1885431112 )
  {
    ((void (__fastcall *)(union _RTL_BALANCED_NODE::$9BF36C84E3411792BEB9166F3629864E *, struct _LUID *))g_pfnFree)(
      &v46[-1].16,
      v165);
    v154 = v161;
    v31 = v165;
  }
  if ( v43 == (struct _RTL_BALANCED_NODE *)v196 )
  {
LABEL_349:
    v26 = v161;
  }
  else
  {
    v161 = v154;
    v165 = v31;
    if ( v43 && v43[-1].16 == 1885431112 )
    {
      ((void (*)(void))g_pfnFree)();
      goto LABEL_349;
    }
    v165 = v31;
    v26 = v154;
  }
LABEL_350:
  v34 = v160;
  if ( v160 != RemoteInteractive && TokenHandle )
    NtClose(TokenHandle);
  if ( v28 < 0 )
  {
    v15 = v168;
LABEL_25:
    v35 = (struct _RTL_BALANCED_NODE **)v174;
    if ( *v174 )
    {
      Buffer = (struct _RTL_BALANCED_NODE *)(*v174)->Buffer;
      if ( Buffer )
        LsapSubProv_FreeRoutine(Buffer, v31);
      LsapSubProv_FreeRoutine(*v35, v31);
      *v35 = 0;
    }
    v37 = (struct _RTL_BALANCED_NODE **)v172;
    if ( *v172 )
    {
      v38 = (struct _RTL_BALANCED_NODE *)(*v172)->Buffer;
      if ( v38 )
        LsapSubProv_FreeRoutine(v38, v31);
      LsapSubProv_FreeRoutine(*v37, v31);
      *v37 = 0;
    }
    v39 = (struct _RTL_BALANCED_NODE **)v176;
    if ( *v176 )
    {
      v40 = (struct _RTL_BALANCED_NODE *)(*v176)->Buffer;
      if ( v40 )
        LsapSubProv_FreeRoutine(v40, v31);
      LsapSubProv_FreeRoutine(*v39, v31);
      *v39 = 0;
    }
    NegpFreePrimaryCred(v15);
    LsapFreeSupplementalCredentials(v177);
    if ( v20 )
      NegpDerefLogonSession(v20, 0);
    if ( LocallyUniqueId )
      LsapDeleteLogonSession(&LocallyUniqueId);
  }
  if ( v19 )
    LsapReleaseLogonSession(v19);
  if ( v26 )
    LsapReleaseLogonSession(v26);
  if ( v34 == RemoteInteractive )
  {
    v41 = v165;
    LsapFreeString(&v165[1]);
    LsapFreeString(&v41[3]);
  }
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x1800d3a4c  push    rbp
0x1800d3a4e  push    rsi
0x1800d3a4f  push    rdi
0x1800d3a50  push    r12
0x1800d3a52  push    r13
0x1800d3a54  push    r14
0x1800d3a56  push    r15
0x1800d3a58  sub     rsp, 290h
0x1800d3a5f  lea     rbp, [rsp+30h]
0x1800d3a64  mov     [rbp+290h+arg_0], rbx
0x1800d3a6b  mov     rax, cs:__security_cookie
0x1800d3a72  xor     rax, rbp
0x1800d3a75  mov     [rbp+290h+var_40], rax
0x1800d3a7c  mov     rax, [rbp+290h+arg_20]
0x1800d3a83  xorps   xmm0, xmm0
0x1800d3a86  mov     r13, [rbp+290h+arg_68]
0x1800d3a8d  mov     rsi, rdx
0x1800d3a90  mov     r14, [rbp+290h+arg_70]
0x1800d3a97  mov     edi, ecx
0x1800d3a99  mov     [rbp+290h+var_1E8], rax
0x1800d3aa0  mov     ebx, r9d
0x1800d3aa3  mov     rax, [rbp+290h+arg_30]
0x1800d3aaa  mov     [rbp+290h+var_1D8], rax
0x1800d3ab1  mov     rax, [rbp+290h+arg_38]
0x1800d3ab8  mov     [rbp+290h+var_1D0], rax
0x1800d3abf  mov     rax, [rbp+290h+arg_40]
0x1800d3ac6  mov     [rbp+290h+var_1C8], rax
0x1800d3acd  mov     rax, [rbp+290h+arg_48]
0x1800d3ad4  mov     [rbp+290h+var_1C0], rax
0x1800d3adb  mov     rax, [rbp+290h+arg_50]
0x1800d3ae2  mov     [rbp+290h+var_220], rax
0x1800d3ae6  mov     rax, [rbp+290h+arg_58]
0x1800d3aed  mov     [rbp+290h+var_210], rax
0x1800d3af4  mov     rax, [rbp+290h+arg_60]
0x1800d3afb  mov     [rbp+290h+var_240], rdx
0x1800d3aff  mov     rdx, [rbp+290h+arg_28]
0x1800d3b06  mov     [rbp+290h+var_274], ecx
0x1800d3b09  xor     ecx, ecx
0x1800d3b0b  mov     [rbp+290h+var_200], rax
0x1800d3b12  mov     r15d, ecx
0x1800d3b15  xor     eax, eax
0x1800d3b17  mov     [rbp+290h+var_1F0], r8
0x1800d3b1e  mov     [rbp+290h+var_1E0], rdx
0x1800d3b25  mov     r12d, ecx
0x1800d3b28  mov     [rbp+290h+TokenHandle], rcx
0x1800d3b2c  xor     edx, edx; Val
0x1800d3b2e  mov     [rbp+290h+var_280], rcx
0x1800d3b32  mov     r8d, 0A0h; Size
0x1800d3b38  mov     [rbp+290h+var_288], rcx
0x1800d3b3c  mov     qword ptr [rbp+290h+LocallyUniqueId.LowPart], rcx
0x1800d3b40  mov     [rbp+290h+var_208], rcx
0x1800d3b47  mov     [rbp+290h+TokenInformationLength], ecx
0x1800d3b4a  mov     [rbp+290h+var_224], ecx
0x1800d3b4d  lea     rcx, [rbp+290h+Src]; void *
0x1800d3b54  mov     [rbp+290h+var_D0], rax
0x1800d3b5b  mov     [rbp+290h+var_218], ebx
0x1800d3b5e  mov     [rbp+290h+var_238], r13
0x1800d3b62  mov     [rbp+290h+var_1F8], r14
0x1800d3b69  movups  [rbp+290h+TokenInformation], xmm0
0x1800d3b70  movups  [rbp+290h+var_F0], xmm0
0x1800d3b77  movups  [rbp+290h+var_E0], xmm0
0x1800d3b7e  call    memset_0
0x1800d3b83  xorps   xmm0, xmm0
0x1800d3b86  lea     rdx, aSa262e99c96160; "_SA_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x1800d3b8d  lea     rcx, [rbp+290h+DestinationString]; DestinationString
0x1800d3b94  movups  xmmword ptr [rbp+290h+DestinationString.Length], xmm0
0x1800d3b9b  call    cs:__imp_RtlInitUnicodeString
0x1800d3ba2  nop     dword ptr [rax+rax+00h]
0x1800d3ba7  mov     [r14], r12
0x1800d3baa  lea     r14d, [r12+1]
0x1800d3baf  cmp     edi, 0Ah
0x1800d3bb2  jnz     loc_1800D3E41
0x1800d3bb8  call    LsaIAllowProtectedCredLogon
0x1800d3bbd  test    al, al
0x1800d3bbf  jnz     short loc_1800D3BCB
0x1800d3bc1  mov     eax, 0C000006Eh
0x1800d3bc6  jmp     loc_1800D3DD2
0x1800d3bcb  cmp     ebx, 40h ; '@'
0x1800d3bce  jnb     short loc_1800D3BF3
0x1800d3bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3bd7  lea     rdi, WPP_GLOBAL_Control
0x1800d3bde  cmp     rcx, rdi
0x1800d3be1  jz      short loc_1800D3C29
0x1800d3be3  test    [rcx+1Ch], r14b
0x1800d3be7  jz      short loc_1800D3C29
0x1800d3be9  mov     edx, 21h ; '!'
0x1800d3bee  mov     r9d, ebx
0x1800d3bf1  jmp     short loc_1800D3C19
0x1800d3bf3  cmp     dword ptr [rsi], 54h ; 'T'
0x1800d3bf6  jz      short loc_1800D3C33
0x1800d3bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3bff  lea     rdi, WPP_GLOBAL_Control
0x1800d3c06  cmp     rcx, rdi
0x1800d3c09  jz      short loc_1800D3C29
0x1800d3c0b  test    [rcx+1Ch], r14b
0x1800d3c0f  jz      short loc_1800D3C29
0x1800d3c11  mov     r9d, [rsi]
0x1800d3c14  mov     edx, 22h ; '"'
0x1800d3c19  mov     rcx, [rcx+10h]
0x1800d3c1d  lea     r8, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids
0x1800d3c24  call    WPP_SF_d
0x1800d3c29  mov     eax, 0C00000A7h
0x1800d3c2e  jmp     loc_1800D3DD2
0x1800d3c33  lea     rcx, [rsi+38h]; struct _LUID *
0x1800d3c37  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x1800d3c3c  mov     [rbp+290h+var_270], rax
0x1800d3c40  mov     r14, rax
0x1800d3c43  test    rax, rax
0x1800d3c46  jnz     short loc_1800D3C89
0x1800d3c48  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3c4f  lea     rdi, WPP_GLOBAL_Control
0x1800d3c56  mov     ebx, 0C000005Fh
0x1800d3c5b  cmp     rcx, rdi
0x1800d3c5e  jz      loc_1800D3DD0
0x1800d3c64  test    byte ptr [rcx+1Ch], 1
0x1800d3c68  jz      loc_1800D3DD0
0x1800d3c6e  lea     edx, [rax+23h]
0x1800d3c71  mov     rcx, [rcx+10h]
0x1800d3c75  lea     r8, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids
0x1800d3c7c  mov     r9d, ebx
0x1800d3c7f  call    WPP_SF_d
0x1800d3c84  jmp     loc_1800D3DD0
0x1800d3c89  mov     rax, [rax+120h]
0x1800d3c90  lea     rdx, [r14+0B0h]
0x1800d3c97  lea     rcx, [rsi+8]
0x1800d3c9b  mov     [rbp+290h+TokenHandle], rax
0x1800d3c9f  mov     [rbp+290h+var_250], rsi
0x1800d3ca3  call    LsapDuplicateString
0x1800d3ca8  mov     ebx, eax
0x1800d3caa  test    eax, eax
0x1800d3cac  jns     loc_1800D3DFC
0x1800d3cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3cb9  lea     rdi, WPP_GLOBAL_Control
0x1800d3cc0  cmp     rcx, rdi
0x1800d3cc3  jz      short loc_1800D3CE3
0x1800d3cc5  test    byte ptr [rcx+1Ch], 1
0x1800d3cc9  jz      short loc_1800D3CE3
0x1800d3ccb  mov     edx, 24h ; '$'
0x1800d3cd0  mov     rcx, [rcx+10h]
0x1800d3cd4  lea     r8, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids
0x1800d3cdb  mov     r9d, eax
0x1800d3cde  call    WPP_SF_d
0x1800d3ce3  mov     edi, [rbp+290h+var_274]
0x1800d3ce6  mov     rsi, [rbp+290h+var_210]
0x1800d3ced  mov     rax, [rsi]
0x1800d3cf0  test    rax, rax
0x1800d3cf3  jz      short loc_1800D3D12
0x1800d3cf5  mov     rcx, [rax+8]; struct _RTL_BALANCED_NODE *
0x1800d3cf9  test    rcx, rcx
0x1800d3cfc  jz      short loc_1800D3D03
0x1800d3cfe  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800d3d03  mov     rcx, [rsi]; struct _RTL_BALANCED_NODE *
0x1800d3d06  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800d3d0b  mov     qword ptr [rsi], 0
0x1800d3d12  mov     rsi, [rbp+290h+var_220]
0x1800d3d16  mov     rax, [rsi]
0x1800d3d19  test    rax, rax
0x1800d3d1c  jz      short loc_1800D3D3B
0x1800d3d1e  mov     rcx, [rax+8]; struct _RTL_BALANCED_NODE *
0x1800d3d22  test    rcx, rcx
0x1800d3d25  jz      short loc_1800D3D2C
0x1800d3d27  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800d3d2c  mov     rcx, [rsi]; struct _RTL_BALANCED_NODE *
0x1800d3d2f  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800d3d34  mov     qword ptr [rsi], 0
0x1800d3d3b  mov     rsi, [rbp+290h+var_200]
0x1800d3d42  mov     rax, [rsi]
0x1800d3d45  test    rax, rax
0x1800d3d48  jz      short loc_1800D3D67
0x1800d3d4a  mov     rcx, [rax+8]; struct _RTL_BALANCED_NODE *
0x1800d3d4e  test    rcx, rcx
0x1800d3d51  jz      short loc_1800D3D58
0x1800d3d53  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800d3d58  mov     rcx, [rsi]; struct _RTL_BALANCED_NODE *
0x1800d3d5b  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800d3d60  mov     qword ptr [rsi], 0
0x1800d3d67  mov     rcx, r13; struct _SECPKG_PRIMARY_CRED *
0x1800d3d6a  call    ?NegpFreePrimaryCred@@YAXPEAU_SECPKG_PRIMARY_CRED@@@Z; NegpFreePrimaryCred(_SECPKG_PRIMARY_CRED *)
0x1800d3d6f  mov     rcx, [rbp+290h+var_1F8]; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x1800d3d76  call    ?LsapFreeSupplementalCredentials@@YAXPEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; LsapFreeSupplementalCredentials(_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x1800d3d7b  test    r12, r12
0x1800d3d7e  jz      short loc_1800D3D8A
0x1800d3d80  xor     edx, edx; unsigned __int8
0x1800d3d82  mov     rcx, r12; struct _RTL_BALANCED_NODE *
0x1800d3d85  call    ?NegpDerefLogonSession@@YAXPEAU_NEG_LOGON_SESSION@@E@Z; NegpDerefLogonSession(_NEG_LOGON_SESSION *,uchar)
0x1800d3d8a  mov     eax, [rbp+290h+LocallyUniqueId.HighPart]
0x1800d3d8d  or      eax, [rbp+290h+LocallyUniqueId.LowPart]
0x1800d3d90  jz      short loc_1800D3D9B
0x1800d3d92  lea     rcx, [rbp+290h+LocallyUniqueId]; struct _LUID *
0x1800d3d96  call    ?LsapDeleteLogonSession@@YAJPEAU_LUID@@@Z; LsapDeleteLogonSession(_LUID *)
0x1800d3d9b  test    r15, r15
0x1800d3d9e  jz      short loc_1800D3DA8
0x1800d3da0  mov     rcx, r15; struct _LSAP_LOGON_SESSION *
0x1800d3da3  call    ?LsapReleaseLogonSession@@YAXPEAU_LSAP_LOGON_SESSION@@@Z; LsapReleaseLogonSession(_LSAP_LOGON_SESSION *)
0x1800d3da8  test    r14, r14
0x1800d3dab  jz      short loc_1800D3DB5
0x1800d3dad  mov     rcx, r14; struct _LSAP_LOGON_SESSION *
0x1800d3db0  call    ?LsapReleaseLogonSession@@YAXPEAU_LSAP_LOGON_SESSION@@@Z; LsapReleaseLogonSession(_LSAP_LOGON_SESSION *)
0x1800d3db5  cmp     edi, 0Ah
0x1800d3db8  jnz     short loc_1800D3DD0
0x1800d3dba  mov     rdi, [rbp+290h+var_250]
0x1800d3dbe  lea     rcx, [rdi+8]
0x1800d3dc2  call    LsapFreeString
0x1800d3dc7  lea     rcx, [rdi+18h]
0x1800d3dcb  call    LsapFreeString
0x1800d3dd0  mov     eax, ebx
0x1800d3dd2  mov     rcx, [rbp+290h+var_40]
0x1800d3dd9  xor     rcx, rbp; StackCookie
0x1800d3ddc  call    __security_check_cookie
0x1800d3de1  mov     rbx, [rbp+290h+arg_0]
0x1800d3de8  lea     rsp, [rbp+260h]
0x1800d3def  pop     r15
0x1800d3df1  pop     r14
0x1800d3df3  pop     r13
0x1800d3df5  pop     r12
0x1800d3df7  pop     rdi
0x1800d3df8  pop     rsi
0x1800d3df9  pop     rbp
0x1800d3dfa  retn
0x1800d3dfc  lea     rdx, [r14+0A0h]
0x1800d3e03  lea     rcx, [rsi+18h]
0x1800d3e07  call    LsapDuplicateString
0x1800d3e0c  mov     ebx, eax
0x1800d3e0e  test    eax, eax
0x1800d3e10  jns     loc_1800D3EE0
0x1800d3e16  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3e1d  lea     rdi, WPP_GLOBAL_Control
0x1800d3e24  cmp     rcx, rdi
0x1800d3e27  jz      loc_1800D3CE3
0x1800d3e2d  test    byte ptr [rcx+1Ch], 1
0x1800d3e31  jz      loc_1800D3CE3
0x1800d3e37  mov     edx, 25h ; '%'
0x1800d3e3c  jmp     loc_1800D3CD0
0x1800d3e41  xor     ecx, ecx; int *
0x1800d3e43  call    ?LsapImpersonateClientEx@@YAJPEAH@Z; LsapImpersonateClientEx(int *)
0x1800d3e48  mov     ebx, eax
0x1800d3e4a  test    eax, eax
0x1800d3e4c  jns     short loc_1800D3E79
0x1800d3e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3e55  lea     rdi, WPP_GLOBAL_Control
0x1800d3e5c  cmp     rcx, rdi
0x1800d3e5f  jz      loc_1800D3DD0
0x1800d3e65  test    [rcx+1Ch], r14b
0x1800d3e69  jz      loc_1800D3DD0
0x1800d3e6f  mov     edx, 26h ; '&'
0x1800d3e74  jmp     loc_1800D3C71
0x1800d3e79  lea     r9, [rbp+290h+TokenHandle]; TokenHandle
0x1800d3e7d  mov     r8b, r14b; OpenAsSelf
0x1800d3e80  mov     edx, 8; DesiredAccess
0x1800d3e85  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800d3e8c  call    cs:__imp_NtOpenThreadToken
0x1800d3e93  nop     dword ptr [rax+rax+00h]
0x1800d3e98  mov     ebx, eax
0x1800d3e9a  call    cs:__imp_RevertToSelf
0x1800d3ea1  nop     dword ptr [rax+rax+00h]
0x1800d3ea6  test    ebx, ebx
0x1800d3ea8  jns     short loc_1800D3ED5
0x1800d3eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3eb1  lea     rdi, WPP_GLOBAL_Control
0x1800d3eb8  cmp     rcx, rdi
0x1800d3ebb  jz      loc_1800D3DD0
0x1800d3ec1  test    [rcx+1Ch], r14b
0x1800d3ec5  jz      loc_1800D3DD0
0x1800d3ecb  mov     edx, 27h ; '''
0x1800d3ed0  jmp     loc_1800D3C71
0x1800d3ed5  xor     r14d, r14d
0x1800d3ed8  mov     [rbp+290h+var_250], r12
0x1800d3edc  mov     [rbp+290h+var_270], r14
0x1800d3ee0  mov     ecx, 40h ; '@'
0x1800d3ee5  call    LsapAllocate
0x1800d3eea  mov     r13, rax
0x1800d3eed  test    rax, rax
0x1800d3ef0  jnz     short loc_1800D3F36
0x1800d3ef2  mov     eax, 0C0000017h
0x1800d3ef7  mov     ebx, eax
0x1800d3ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3f00  lea     rdi, WPP_GLOBAL_Control
0x1800d3f07  cmp     rcx, rdi
0x1800d3f0a  jz      loc_1800D51D9
0x1800d3f10  test    byte ptr [rcx+1Ch], 1
0x1800d3f14  jz      loc_1800D51D9
0x1800d3f1a  mov     rcx, [rcx+10h]
0x1800d3f1e  lea     edx, [r13+28h]
0x1800d3f22  mov     r9d, eax
0x1800d3f25  lea     r8, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids
0x1800d3f2c  call    WPP_SF_d
0x1800d3f31  jmp     loc_1800D51D9
0x1800d3f36  mov     rcx, [rbp+290h+TokenHandle]; TokenHandle
0x1800d3f3a  lea     rax, [rbp+290h+TokenInformationLength]
0x1800d3f3e  xor     r14d, r14d
0x1800d3f41  mov     [rsp+2C0h+ReturnLength], rax; ReturnLength
0x1800d3f46  lea     r8, [rbp+290h+TokenInformation]; TokenInformation
0x1800d3f4d  mov     [rbp+290h+var_260], r14
0x1800d3f51  lea     r9d, [r14+38h]; TokenInformationLength
0x1800d3f55  lea     edx, [r14+0Ah]; TokenInformationClass
0x1800d3f59  call    cs:__imp_NtQueryInformationToken
0x1800d3f60  nop     dword ptr [rax+rax+00h]
0x1800d3f65  mov     ebx, eax
0x1800d3f67  test    eax, eax
0x1800d3f69  jns     short loc_1800D3FA9
  ... truncated ...
```
