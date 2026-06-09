# NegLogonUserEx3Worker(void * *,_SECURITY_LOGON_TYPE,void *,void *,ulong,_SECPKG_SURROGATE_LOGON *,void * *,ulong *,_LUID *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x18009ac50`
- end: `0x18009c201`
- name: `?NegLogonUserEx3Worker@@YAJPEAPEAXW4_SECURITY_LOGON_TYPE@@PEAX2KPEAU_SECPKG_SURROGATE_LOGON@@0PEAKPEAU_LUID@@PEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@0PEAPEAU_UNICODE_STRING@@88PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `5553`
- prototype: `int(void **, enum _SECURITY_LOGON_TYPE, void *, void *, unsigned int, struct _SECPKG_SURROGATE_LOGON *, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009a340`

## callees

- `0x180009330`
- `0x180009470`
- `0x180009838`
- `0x18000acb0`
- `0x18000c300`
- `0x18000d48c`
- `0x18000dd1c`
- `0x180011278`
- `0x180016abc`
- `0x180016f70`
- `0x1800250c4`
- `0x18002620c`
- `0x1800268d8`
- `0x18005d528`
- `0x180060c8c`
- `0x1800814f4`
- `0x180082b70`
- `0x180088bb0`
- `0x18008ac70`
- `0x1800934c8`
- `0x18009ac50`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x1800cac5c`
- `0x1800d3a4c`
- `0x1800d541c`
- `0x1800d9e54`
- `0x18012fc00`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009bec1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009bec1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009bf1d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009bf1d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009bfd9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009bfd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bf88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bf88`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009bf56`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009bf56`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009acb7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009acd4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009acb7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009acd4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18009b455`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18009b678`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18009b81b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18009b84b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18009b455`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18009b678`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18009b81b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18009b84b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009bfb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c0d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009bfb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c0d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c095`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c095`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b371`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b371`
- `ntdll!RtlReleaseResource` at `0x18009b294`
- `ntdll!RtlReleaseResource` at `0x18009b294`
- `ntdll!RtlAcquireResourceShared` at `0x18009b230`
- `ntdll!RtlAcquireResourceShared` at `0x18009b230`
- `ntdll!NtClose` at `0x18009bfe8`
- `ntdll!NtClose` at `0x18009c0ed`
- `ntdll!NtClose` at `0x18009bfe8`
- `ntdll!NtClose` at `0x18009c0ed`
- `ntdll!NtSetInformationThread` at `0x18009c061`
- `ntdll!NtSetInformationThread` at `0x18009c061`
- `ntdll!NtOpenThreadToken` at `0x18009bde2`
- `ntdll!NtOpenThreadToken` at `0x18009bde2`
- `ntdll!RtlInitUnicodeString` at `0x18009bbfe`
- `ntdll!RtlInitUnicodeString` at `0x18009bbfe`

## pseudocode

```c
__int64 __fastcall NegLogonUserEx3Worker(
        void **a1,
        unsigned int a2,
        struct _RTL_BALANCED_NODE *a3,
        void *a4,
        unsigned int Size,
        struct _SECPKG_SURROGATE_LOGON *a6,
        void **a7,
        unsigned int *a8,
        struct _LUID *a9,
        int *a10,
        enum _LSA_TOKEN_INFORMATION_TYPE *a11,
        void **a12,
        struct _UNICODE_STRING **a13,
        struct _UNICODE_STRING **a14,
        struct _UNICODE_STRING **a15,
        struct _SECPKG_PRIMARY_CRED *a16,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a17)
{
  char *v17; // rbx
  struct _RTL_BALANCED_NODE *v19; // r15
  unsigned int v21; // r12d
  char *Value; // rax
  void *v23; // rdx
  char *v24; // rsi
  int v25; // eax
  int v26; // eax
  __int64 v27; // rdx
  enum _SECURITY_LOGON_TYPE v28; // r9d
  struct _RTL_BALANCED_NODE *v29; // r12
  int IsVirtualAccount; // edi
  __int64 v31; // rbx
  __int64 result; // rax
  struct _RTL_BALANCED_NODE *v33; // rax
  int SystemToken; // eax
  __int64 v35; // rax
  struct _RTL_BALANCED_NODE *v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  unsigned __int64 v39; // rbx
  struct _RTL_BALANCED_NODE *p_Right; // rax
  unsigned __int64 v41; // rcx
  __int64 v42; // rcx
  unsigned __int64 v43; // rcx
  void *v44; // rsp
  void *v45; // rsp
  struct _RTL_BALANCED_NODE *v46; // rax
  __int64 v47; // rbx
  struct _LIST_ENTRY *Flink; // rdx
  struct _RTL_BALANCED_NODE *v49; // r9
  struct _LIST_ENTRY *v50; // r8
  int v51; // eax
  unsigned int v52; // ebx
  int v53; // ecx
  unsigned int v54; // eax
  LsaHandleCache *v55; // rcx
  __int64 v56; // rbx
  size_t v57; // r15
  struct _RTL_BALANCED_NODE *Buffer; // rcx
  struct _RTL_BALANCED_NODE *v59; // rcx
  struct _RTL_BALANCED_NODE *v60; // rcx
  int v61; // esi
  struct _RTL_BALANCED_NODE *v62; // rax
  __int64 (__fastcall *ParentValue)(void **, _QWORD, struct _RTL_BALANCED_NODE *, void *, unsigned int, struct _SECPKG_SURROGATE_LOGON *, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **); // r10
  int v64; // eax
  bool v65; // sf
  bool v66; // zf
  unsigned int v67; // eax
  unsigned int v68; // ebx
  int v69; // eax
  __int64 v70; // r15
  struct _RTL_BALANCED_NODE *v71; // rsi
  void *v72; // rdx
  struct _RTL_BALANCED_NODE *v73; // rcx
  struct _RTL_BALANCED_NODE *v74; // rcx
  struct _RTL_BALANCED_NODE *v75; // rcx
  struct _RTL_BALANCED_NODE *v76; // rcx
  PWSTR v77; // rax
  __int64 Length; // rcx
  PWSTR v79; // rax
  __int64 v80; // rcx
  struct _RTL_BALANCED_NODE *v81; // rcx
  struct _RTL_BALANCED_NODE *UserSid; // rcx
  struct _RTL_BALANCED_NODE *v83; // rcx
  struct _RTL_BALANCED_NODE *v84; // rcx
  struct _RTL_BALANCED_NODE *v85; // rcx
  struct _RTL_BALANCED_NODE *v86; // rcx
  __int64 v87; // rdx
  __int64 v88; // rbx
  struct _RTL_BALANCED_NODE *v89; // r15
  struct _NEG_LOGON_SESSION *v90; // rsi
  LsaHandleCache *v91; // rcx
  struct _UNICODE_STRING **v92; // rbx
  int IsUplevelDomain; // eax
  WCHAR *v94; // rax
  const WCHAR *v95; // r15
  unsigned __int64 v96; // rcx
  const WCHAR *v97; // rbx
  int v98; // eax
  char *v99; // r13
  LsaHandleCache *v100; // rcx
  __int64 v101; // rdx
  NTSTATUS v102; // eax
  LsaHandleCache *v103; // rcx
  __int64 v104; // rdx
  __int64 v105; // r9
  __int64 v106; // rax
  __int64 v107; // rbx
  struct _LUID *v108; // rcx
  struct _NEG_LOGON_SESSION *LogonSession; // rax
  void *v110; // rcx
  void *v111; // rdx
  HANDLE EventW; // rax
  void *v113; // r15
  DWORD LastError; // eax
  void *v115; // rdx
  void *v116; // rcx
  __int64 v117; // rcx
  struct _RTL_BALANCED_NODE *v118; // rax
  struct _RTL_BALANCED_NODE *v119; // rbx
  __int64 v120; // rcx
  struct _RTL_BALANCED_NODE *v121; // rdx
  __int64 v122; // [rsp+0h] [rbp-90h] BYREF
  LPDWORD lpThreadId; // [rsp+28h] [rbp-68h]
  unsigned int v124; // [rsp+90h] [rbp+0h] BYREF
  unsigned int v125; // [rsp+94h] [rbp+4h]
  struct _RTL_BALANCED_NODE *v126; // [rsp+98h] [rbp+8h] BYREF
  unsigned int v127; // [rsp+A0h] [rbp+10h] BYREF
  unsigned int v128; // [rsp+A4h] [rbp+14h] BYREF
  int v129; // [rsp+A8h] [rbp+18h] BYREF
  unsigned int v130; // [rsp+ACh] [rbp+1Ch] BYREF
  void *v131; // [rsp+B0h] [rbp+20h]
  char *v132; // [rsp+B8h] [rbp+28h]
  HKEY hKey; // [rsp+C0h] [rbp+30h] BYREF
  void *Src; // [rsp+C8h] [rbp+38h]
  void *TokenHandle; // [rsp+D0h] [rbp+40h] BYREF
  LPVOID lpTlsValue; // [rsp+D8h] [rbp+48h] BYREF
  int v137; // [rsp+E0h] [rbp+50h] BYREF
  void *v138; // [rsp+E8h] [rbp+58h] BYREF
  void **v139; // [rsp+F0h] [rbp+60h]
  HANDLE hObject; // [rsp+F8h] [rbp+68h]
  _QWORD v141[3]; // [rsp+100h] [rbp+70h] BYREF

  v17 = (char *)a3;
  v139 = a1;
  v126 = a3;
  v19 = a3;
  v138 = 0;
  v130 = 0;
  v21 = Size;
  v131 = a4;
  Src = a3;
  v125 = Size;
  v124 = Size;
  lpTlsValue = TlsGetValue(dwThreadPackage);
  hKey = 0;
  v129 = 0;
  Value = (char *)TlsGetValue(dwCallInfo);
  TokenHandle = 0;
  v24 = Value;
  v132 = Value;
  if ( a2 != 9 && (Size <= 4 || a2 != 10 || *(_DWORD *)v17 != 84 || Value[68] >= 0) )
  {
    hObject = 0;
    if ( Size > 4 && LODWORD(v19->Children[0]) == 82 && a2 <= 0xA )
    {
      v25 = 1076;
      if ( _bittest(&v25, a2) )
      {
        v128 = 0;
        v127 = 0;
        LODWORD(v19->Children[0]) = 2;
        v26 = NegpConvertWOWInteractiveLogonBuffer(v19, v23, &v124, (void **)&v126);
        v29 = v126;
        IsVirtualAccount = v26;
        if ( v26 < 0 )
        {
          LODWORD(v31) = v124;
LABEL_298:
          if ( hKey )
            RegCloseKey(hKey);
          if ( Src != v29 && v29 )
          {
            v117 = (unsigned int)v31;
            v118 = v29;
            if ( (_DWORD)v31 )
            {
              do
              {
                LOBYTE(v118->Children[0]) = 0;
                v118 = (struct _RTL_BALANCED_NODE *)((char *)v118 + 1);
                --v117;
              }
              while ( v117 );
            }
            LsapSubProv_FreeRoutine(v29, (void *)v27);
          }
          if ( hObject )
            CloseHandle(hObject);
          if ( TokenHandle )
            NtClose(TokenHandle);
          return (unsigned int)IsVirtualAccount;
        }
        v125 = v124;
        IsVirtualAccount = NegpIsVirtualAccount(v126, v131, v124, v28, a13, a14, a15, &v128, (int *)&v127);
        if ( IsVirtualAccount >= 0 )
        {
          if ( v127 )
            IsVirtualAccount = NegpMakeVirtualAccountToken(a2, v128, a9, a7, a8, a10, a11, a12, a13, a14, a15, a16, a17);
          else
            IsVirtualAccount = -1073741811;
        }
LABEL_297:
        LODWORD(v31) = v125;
        goto LABEL_298;
      }
    }
    IsVirtualAccount = -1073741730;
    if ( a2 == 5 )
    {
      v127 = 0;
      result = NegpConvertWOWInteractiveLogonBuffer(v19, v23, &v124, (void **)&v126);
      IsVirtualAccount = result;
      if ( (int)result < 0 )
        return result;
      v29 = v126;
      v31 = v124;
      v125 = v124;
      if ( v19 == v126 )
      {
        v33 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v124);
        v29 = v33;
        if ( !v33 )
          return 3221225626LL;
        memcpy_0(v33, v19, Size);
      }
      if ( (unsigned int)NegpIsHardcodedServiceAccount(
                           v29,
                           v131,
                           v31,
                           (struct _RTL_BALANCED_NODE **)a13,
                           a14,
                           a15,
                           &v127) )
      {
        if ( v127 == 8205 )
          SystemToken = NegpMakeSystemToken(a9, a7, a8, a10, a11, a12, a13, a14, a15, a16, a17);
        else
          SystemToken = NegpMakeServiceToken(v127, a9, a7, a8, a10, a11, a12, a13, a14, a15, a16, a17);
        IsVirtualAccount = SystemToken;
        goto LABEL_298;
      }
      if ( v29 )
      {
        v35 = v31;
        v36 = v29;
        if ( (_DWORD)v31 )
        {
          do
          {
            LOBYTE(v36->Children[0]) = 0;
            v36 = (struct _RTL_BALANCED_NODE *)((char *)v36 + 1);
            --v35;
          }
          while ( v35 );
        }
        LsapSubProv_FreeRoutine(v29, v36);
      }
      v21 = v125;
      v17 = 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57824352>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID57824352>::GetImpl'::`2'::impl)
      && ((a2 - 2) & 0xFFFFFFF7) == 0
      && v21 >= 0x30
      && *(_DWORD *)v17 == 513
      && *((_DWORD *)v17 + 2) >= 0x30u )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids);
      IsVirtualAccount = LsapHandlePossiblePlaceholderCredential(v17, v21, &v138, &v130);
      if ( IsVirtualAccount < 0 )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids);
        }
        IsVirtualAccount = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids);
        }
        *((_DWORD *)v24 + 17) |= 0x8000u;
        v21 = v130;
        v19 = (struct _RTL_BALANCED_NODE *)v138;
        Src = v138;
        Size = v130;
        v125 = v130;
      }
    }
    v29 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v21);
    if ( !v29 )
      return 3221225626LL;
    if ( NegPackageCount >= 0x200 )
    {
      IsVirtualAccount = -1073741637;
      goto LABEL_297;
    }
    v39 = 8LL * NegPackageCount;
    p_Right = 0;
    v126 = 0;
    if ( v39 )
    {
      if ( v39 <= g_ulMaxStackAllocSize )
      {
        v41 = v39 + g_ulAdditionalProbeSize + 8;
        if ( v41 >= v39 )
        {
          if ( (unsigned int)VerifyStackAvailable(v41, v27, v37, v38) )
          {
            v42 = v39 + 23;
            if ( v39 + 23 <= v39 + 8 )
              v42 = 0xFFFFFFFFFFFFFF0LL;
            v43 = v42 & 0xFFFFFFFFFFFFFFF0uLL;
            v44 = alloca(v43);
            v45 = alloca(v43);
            p_Right = (struct _RTL_BALANCED_NODE *)&v124;
            v126 = (struct _RTL_BALANCED_NODE *)&v124;
            if ( &v122 != (__int64 *)-144LL )
            {
              v124 = 1801679955;
              p_Right = (struct _RTL_BALANCED_NODE *)&v126;
              v126 = (struct _RTL_BALANCED_NODE *)&v126;
              if ( &v126 )
                goto LABEL_65;
            }
          }
          else
          {
            p_Right = v126;
          }
        }
      }
    }
    if ( v39 + 8 >= v39 )
    {
      v46 = (struct _RTL_BALANCED_NODE *)((__int64 (*)(void))g_pfnAllocate)();
      v126 = v46;
      if ( !v46 )
      {
LABEL_66:
        IsVirtualAccount = -1073741670;
        goto LABEL_297;
      }
      LODWORD(v46->Children[0]) = 1885431112;
      p_Right = (struct _RTL_BALANCED_NODE *)&v46->Right;
      v126 = p_Right;
    }
LABEL_65:
    if ( !p_Right )
      goto LABEL_66;
    v47 = 0;
    v127 = 0;
    RtlAcquireResourceShared(&NegLock, 1u);
    Flink = NegPackageList.Flink;
    if ( NegPackageList.Flink != &NegPackageList )
    {
      v49 = v126;
      do
      {
        v50 = Flink[1].Flink;
        if ( ((__int64)v50[1].Flink & 0x2000) != 0
          && ((__int64)Flink[2].Blink & 4) == 0
          && (v50[12].Flink || v50[28].Flink) )
        {
          v49->Children[v47] = (struct _RTL_BALANCED_NODE *)v50;
          v47 = (unsigned int)(v47 + 1);
        }
        Flink = Flink->Flink;
      }
      while ( Flink != &NegPackageList );
      v127 = v47;
    }
    RtlReleaseResource(&NegLock);
    v51 = *((_DWORD *)v24 + 17);
    v52 = a2;
    v128 = a2;
    v27 = 11;
    if ( (v51 & 0xC00) != 0 || NegEnableLastInteractiveLogonInfo )
    {
      if ( (v51 & 0x400) != 0 && a2 == 11 )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids);
        }
        IsVirtualAccount = -1073741811;
LABEL_295:
        if ( v126[-1].16 == 1885431112 )
          ((void (*)(void))g_pfnFree)();
        goto LABEL_297;
      }
    }
    else
    {
      v53 = v51 & 0x10000;
      if ( (v51 & 0x10000) != 0 && !*((_DWORD *)v24 + 16) )
      {
        v137 = 1;
        v141[0] = L"ForceUnlockLogon";
        v141[2] = 1;
        a2 = 11;
        v141[1] = &v137;
        GetRegistryDwords(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          1u,
          (struct _LSAP_REG_PARAMETER *)v141);
        v54 = Size;
        if ( v137 )
          a2 = v52;
        goto LABEL_92;
      }
      if ( a2 == 2 || v53 )
      {
        if ( NegProductType != NtProductWinNt || (v51 & 0x80u) == 0 || (NegMachineState & 0x10) != 0 )
        {
          if ( a2 == 2 || v53 )
          {
            v65 = (v51 & 0x80u) != 0;
            v54 = Size;
            if ( v65 && Size >= 0x30 && LODWORD(v19->Children[0]) == 513 )
            {
              v66 = (unsigned int)LsapCheckConnectedUserEnabled() == 0;
              v54 = Size;
              if ( !v66 )
                a2 = v27;
            }
            goto LABEL_92;
          }
        }
        else
        {
          a2 = 11;
          if ( RegOpenKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
                 0,
                 0x20019u,
                 &hKey) )
          {
            if ( v52 == 11 )
            {
              IsVirtualAccount = -1073741670;
              goto LABEL_295;
            }
            a2 = v52;
          }
        }
      }
    }
    v54 = Size;
LABEL_92:
    v55 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      v56 = 0;
      v124 = 0;
      if ( v127 )
      {
        v57 = v54;
        while ( 1 )
        {
          if ( *a15 )
          {
            Buffer = (struct _RTL_BALANCED_NODE *)(*a15)->Buffer;
            if ( Buffer )
              LsapSubProv_FreeRoutine(Buffer, (void *)v27);
            LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)*a15, (void *)v27);
            *a15 = 0;
          }
          if ( *a13 )
          {
            v59 = (struct _RTL_BALANCED_NODE *)(*a13)->Buffer;
            if ( v59 )
              LsapSubProv_FreeRoutine(v59, (void *)v27);
            LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)*a13, (void *)v27);
            *a13 = 0;
          }
          if ( *a14 )
          {
            v60 = (struct _RTL_BALANCED_NODE *)(*a14)->Buffer;
            if ( v60 )
              LsapSubProv_FreeRoutine(v60, (void *)v27);
            LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)*a14, (void *)v27);
            *a14 = 0;
          }
          memcpy_0(v29, Src, v57);
          TlsSetValue(dwThreadPackage, v126->Children[v56]->Children[0]);
          v61 = IsVirtualAccount;
          v62 = v126->Children[v56];
          ParentValue = (__int64 (__fastcall *)(void **, _QWORD, struct _RTL_BALANCED_NODE *, void *, unsigned int, struct _SECPKG_SURROGATE_LOGON *, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **))v62[18].ParentValue;
          LODWORD(v56) = HIDWORD(v62->ParentValue);
          v64 = ParentValue
              ? ParentValue(v139, a2, v29, v131, Size, a6, a7, a8, a9, a10, a11, a12, a13, a14, a15, a16, a17)
              : ((unsigned __int64 (__fastcall *)(void **, _QWORD, struct _RTL_BALANCED_NODE *, void *, unsigned int, void **, unsigned int *, struct _LUID *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **))v62[8].Children[0])(
                  v139,
                  a2,
                  v29,
                  v131,
                  Size,
                  a7,
                  a8,
                  a9,
                  a10,
                  a11,
                  a12,
                  a13,
                  a14,
                  a15,
                  a16,
                  a17);
          if ( ((IsVirtualAccount = v64, TlsSetValue(dwThreadPackage, lpTlsValue), IsVirtualAccount == -1073741424)
             || IsVirtualAccount == -1073741427)
            && (NegMachineState & 4) != 0 )
          {
            IsVirtualAccount = -1073741730;
          }
          else if ( IsVirtualAccount != -1073741730
                 && IsVirtualAccount != -1073741422
                 && IsVirtualAccount != -2146893039
                 && IsVirtualAccount != -2146958527
                 && IsVirtualAccount != -1073741059
                 && IsVirtualAccount != -1073741811
                 && IsVirtualAccount != -1073741557
                 && IsVirtualAccount != -1073741821
                 && IsVirtualAccount != -1073741252
                 && IsVirtualAccount != -1073741657 )
          {
            v55 = WPP_GLOBAL_Control;
            goto LABEL_143;
          }
          v67 = v124 + 1;
          v124 = v67;
          if ( v67 >= v127 )
            break;
          v56 = v67;
        }
        v55 = WPP_GLOBAL_Control;
      }
      else
      {
        v61 = 0;
      }
      if ( IsVirtualAccount != -1073741657 )
      {
LABEL_143:
        if ( IsVirtualAccount != -1073741637 )
          goto LABEL_147;
      }
      if ( (_DWORD)v56 != 16 && v61 < 0 )
        IsVirtualAccount = v61;
LABEL_147:
      v129 = 0;
      if ( a2 != 11 || (v68 = v128, v128 == 11) )
      {
        LODWORD(v70) = v124;
        goto LABEL_211;
      }
      if ( IsVirtualAccount < 0 )
      {
        LODWORD(v70) = v124;
      }
      else
      {
        if ( v55 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v55 + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)v55 + 2), 88, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids);
        v69 = NegpCheckCachedLogonPolicy(a9, *a12, *a7, *a8, hKey, *((_DWORD *)v132 + 17) & 0x10000, &v129);
        IsVirtualAccount = v69;
        if ( v69 >= 0 )
        {
          LODWORD(v70) = v124;
          goto LABEL_214;
        }
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            89,
            WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
            (unsigned int)v69);
        }
        v70 = v124;
        v71 = v126;
        TlsSetValue(dwThreadPackage, v126->Children[v124]->Children[0]);
        ((void (__fastcall *)(struct _LUID *))v71->Children[v70][6].ParentValue)(a9);
        TlsSetValue(dwThreadPackage, lpTlsValue);
        if ( *a7 )
        {
          LsapClientFree(*a7);
          *a7 = 0;
        }
        *a8 = 0;
        if ( *a12 )
        {
          LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)*a12, v72);
          *a12 = 0;
        }
        if ( *a13 )
        {
          v73 = (struct _RTL_BALANCED_NODE *)(*a13)->Buffer;
          if ( v73 )
            LsapSubProv_FreeRoutine(v73, v72);
          LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)*a13, v72);
          *a13 = 0;
        }
        if ( *a14 )
        {
          v74 = (struct _RTL_BALANCED_NODE *)(*a14)->Buffer;
          if ( v74 )
            LsapSubProv_FreeRoutine(v74, v72);
          LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)*a14, v72);
          *a14 = 0;
        }
        if ( *a15 )
        {
          v75 = (struct _RTL_BALANCED_NODE *)(*a15)->Buffer;
          if ( v75 )
            LsapSubProv_FreeRoutine(v75, v72);
          LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)*a15, v72);
          *a15 = 0;
        }
        v76 = (struct _RTL_BALANCED_NODE *)a16->DownlevelName.Buffer;
        if ( v76 )
          LsapSubProv_FreeRoutine(v76, v72);
        v77 = a16->Password.Buffer;
        if ( v77 )
        {
          Length = a16->Password.Length;
          if ( a16->Password.Length )
          {
            do
            {
              *(_BYTE *)v77 = 0;
              v77 = (PWSTR)((char *)v77 + 1);
              --Length;
            }
            while ( Length );
          }
          LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)a16->Password.Buffer, v72);
        }
        v79 = a16->OldPassword.Buffer;
        if ( v79 )
        {
          v80 = a16->OldPassword.Length;
          if ( a16->OldPassword.Length )
          {
            do
            {
              *(_BYTE *)v79 = 0;
              v79 = (PWSTR)((char *)v79 + 1);
              --v80;
            }
            while ( v80 );
          }
          LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)a16->OldPassword.Buffer, v72);
        }
        v81 = (struct _RTL_BALANCED_NODE *)a16->DomainName.Buffer;
        if ( v81 )
          LsapSubProv_FreeRoutine(v81, v72);
        UserSid = (struct _RTL_BALANCED_NODE *)a16->UserSid;
        if ( UserSid )
          LsapSubProv_FreeRoutine(UserSid, v72);
        v83 = (struct _RTL_BALANCED_NODE *)a16->LogonServer.Buffer;
        if ( v83 )
          LsapSubProv_FreeRoutine(v83, v72);
        v84 = (struct _RTL_BALANCED_NODE *)a16->DnsDomainName.Buffer;
        if ( v84 )
          LsapSubProv_FreeRoutine(v84, v72);
        v85 = (struct _RTL_BALANCED_NODE *)a16->Upn.Buffer;
        if ( v85 )
          LsapSubProv_FreeRoutine(v85, v72);
        v86 = (struct _RTL_BALANCED_NODE *)a16->Spare1.Buffer;
        if ( v86 )
          LsapSubProv_FreeRoutine(v86, v72);
        memset_0(a16, 0, sizeof(struct _SECPKG_PRIMARY_CRED));
        LsapFreeSupplementalCredentials(a17);
        LsapDeleteLogonSession(a9);
        v55 = WPP_GLOBAL_Control;
        v68 = v128;
      }
      v27 = (__int64)&WPP_GLOBAL_Control;
      if ( v55 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v55 + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)v55 + 2),
          90,
          WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
          (unsigned int)IsVirtualAccount);
        v55 = WPP_GLOBAL_Control;
        v27 = (__int64)&WPP_GLOBAL_Control;
      }
      if ( *a10 == -1073740928 )
      {
        if ( v55 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v55 + 28) & 2) != 0 )
        {
          v87 = 91;
          goto LABEL_206;
        }
LABEL_211:
        if ( IsVirtualAccount < 0 )
          goto LABEL_295;
LABEL_214:
        v88 = (unsigned int)v70;
        v89 = v126;
        v90 = NegpBuildLogonSession(
                a9,
                (*((_DWORD *)v132 + 17) >> 7) & 1,
                (unsigned __int64)v126->Children[v88]->Children[0],
                (unsigned __int64)v126->Children[v88]->Children[0]);
        if ( !v90 )
          goto LABEL_229;
        if ( HIDWORD(v89->Children[v88]->ParentValue) != 10 )
        {
          v92 = a14;
          goto LABEL_226;
        }
        v91 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids);
        }
        v92 = a14;
        IsUplevelDomain = NegpIsUplevelDomain(v91, a2, *a14);
        if ( IsUplevelDomain != 3 )
        {
          if ( !IsUplevelDomain )
          {
            if ( (a16->Flags & 0xFF000000) != 0xA000000 )
              *((_QWORD *)v90 + 6) = -1;
LABEL_226:
            v94 = (WCHAR *)LsapAllocate((*a13)->Length + 4LL + (*v92)->Length);
            v95 = v94;
            if ( v94 )
            {
              memcpy_0(v94, (*v92)->Buffer, (*v92)->Length);
              v96 = (unsigned __int64)(*v92)->Length >> 1;
              v95[v96] = 92;
              v97 = &v95[v96];
              memcpy_0((void *)(v97 + 1), (*a13)->Buffer, (*a13)->Length);
              v97[((unsigned __int64)(*a13)->Length >> 1) + 1] = 0;
              RtlInitUnicodeString((PUNICODE_STRING)((char *)v90 + 56), v95);
            }
            NegpDerefLogonSession((struct _RTL_BALANCED_NODE *)v90, 0);
            v90 = 0;
LABEL_229:
            if ( v129 )
            {
              if ( a2 != 11 )
                goto LABEL_295;
            }
            else if ( a2 != 11 )
            {
              if ( NegProductType == NtProductWinNt && (NegMachineState & 0x10) == 0 )
              {
                v98 = *((_DWORD *)v132 + 17);
                if ( (v98 & 0x800) != 0 || (v98 & 0x10080) == 0x80 )
                {
                  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      94,
                      WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
                      a2);
                  }
                  NegpUpdateCachedLogonPolicy(*a12, *a7, *a8, hKey);
                }
              }
              goto LABEL_295;
            }
            if ( a2 == v128 )
              goto LABEL_295;
            v99 = v132;
            if ( (*((_DWORD *)v132 + 17) & 0x800) != 0 )
              goto LABEL_295;
            if ( v132[68] < 0 )
            {
              if ( *a10 != -1073741232 )
                goto LABEL_252;
              v100 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_295;
              }
              v101 = 96;
LABEL_247:
              WPP_SF_(*((_QWORD *)v100 + 2), v101, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids);
              goto LABEL_295;
            }
            if ( (*((_DWORD *)v132 + 17) & 0x10000) == 0 )
            {
              v100 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_295;
              }
              v101 = 95;
              goto LABEL_247;
            }
LABEL_252:
            if ( (v132[32] & 0x40) != 0 )
            {
              v100 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_295;
              }
              v101 = 97;
              goto LABEL_247;
            }
            v102 = LsapImpersonateClientEx(0);
            if ( v102 < 0 )
            {
              v103 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v104 = 98;
                goto LABEL_260;
              }
              goto LABEL_294;
            }
            v102 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, &TokenHandle);
            if ( v102 >= 0 )
            {
              if ( Size < 0xFFFFFFD0 )
              {
                v106 = LsapAllocate(Size + 48);
                v107 = v106;
                if ( v106 )
                {
                  *(_DWORD *)(v106 + 16) = Size;
                  *(_QWORD *)(v106 + 8) = v106 + 48;
                  *(_DWORD *)v106 = 7;
                  if ( (*((_DWORD *)v99 + 17) & 0x10000) == 0
                    || (v108 = (struct _LUID *)(v99 + 400), !*((_QWORD *)v99 + 50)) )
                  {
                    LogonSession = NegpLocateLogonSession(a9);
                    v90 = LogonSession;
                    if ( LogonSession )
                    {
                      v110 = (void *)*((_QWORD *)LogonSession + 12);
                      if ( v110 )
                        ResetEvent(v110);
                    }
                    v108 = a9;
                  }
                  *(struct _LUID *)(v107 + 32) = *v108;
                  if ( v128 == 10 )
                    *(_DWORD *)(v107 + 4) |= 1u;
                  if ( (*((_DWORD *)v99 + 17) & 0x10000) != 0 )
                    *(_DWORD *)(v107 + 4) |= 2u;
                  v111 = Src;
                  *(_QWORD *)(v107 + 24) = TokenHandle;
                  TokenHandle = 0;
                  memcpy_0(*(void **)(v107 + 8), v111, Size);
                  EventW = CreateEventW(0, 0, 0, 0);
                  lpThreadId = 0;
                  *(_QWORD *)(v107 + 40) = EventW;
                  *((_QWORD *)v99 + 51) = EventW;
                  v113 = EventW;
                  hObject = CreateThread(0, 0, NegpAsyncUpdateWorker, (LPVOID)v107, 0, lpThreadId);
                  if ( !hObject )
                  {
                    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      LastError = GetLastError();
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        102,
                        WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
                        LastError);
                    }
                    CloseHandle(*(HANDLE *)(v107 + 24));
                    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v107, v115);
                    if ( v90 )
                    {
                      v116 = (void *)*((_QWORD *)v90 + 12);
                      if ( v116 )
                        SetEvent(v116);
                    }
                    NtClose(v113);
                    *((_QWORD *)v99 + 51) = 0;
                  }
                  if ( v90 )
                    NegpDerefLogonSession((struct _RTL_BALANCED_NODE *)v90, 0);
                }
                else if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids);
                }
                goto LABEL_294;
              }
              v103 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
LABEL_294:
                lpTlsValue = 0;
                NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &lpTlsValue, 8u);
                goto LABEL_295;
              }
              v104 = 100;
              v105 = 3221225621LL;
            }
            else
            {
              v103 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_294;
              }
              v104 = 99;
LABEL_260:
              v105 = (unsigned int)v102;
            }
            WPP_SF_d(*((_QWORD *)v103 + 2), v104, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, v105);
            goto LABEL_294;
          }
          if ( IsUplevelDomain != 1 )
            goto LABEL_226;
        }
        *((_QWORD *)v90 + 6) = *(_QWORD *)&NegPackageId;
        goto LABEL_226;
      }
      if ( *a10 == -1073740927 )
      {
        if ( v55 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v55 + 28) & 2) != 0 )
        {
          v87 = 92;
LABEL_206:
          WPP_SF_(*((_QWORD *)v55 + 2), v87, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids);
          goto LABEL_211;
        }
        goto LABEL_211;
      }
      v54 = Size;
      a2 = v68;
    }
  }
  result = NegpConvertWOWInteractiveLogonBuffer(v19, v23, &v124, (void **)&v126);
  if ( (int)result < 0 )
    return result;
  v119 = v126;
  IsVirtualAccount = NegpCloneLogonSession(
                       (enum _SECURITY_LOGON_TYPE)a2,
                       (struct _LUID *)v126,
                       a4,
                       v124,
                       a7,
                       a8,
                       a9,
                       a10,
                       a11,
                       a12,
                       a13,
                       a14,
                       a15,
                       a16,
                       a17);
  if ( v19 != v119 )
  {
    v120 = v124;
    v121 = v119;
    if ( v124 )
    {
      do
      {
        LOBYTE(v121->Children[0]) = 0;
        v121 = (struct _RTL_BALANCED_NODE *)((char *)v121 + 1);
        --v120;
      }
      while ( v120 );
    }
    LsapSubProv_FreeRoutine(v119, v121);
  }
  return (unsigned int)IsVirtualAccount;
}

```

## disassembly

```asm
0x18009ac50  push    rbp
0x18009ac52  push    rbx
0x18009ac53  push    rsi
0x18009ac54  push    rdi
0x18009ac55  push    r12
0x18009ac57  push    r13
0x18009ac59  push    r14
0x18009ac5b  push    r15
0x18009ac5d  sub     rsp, 128h
0x18009ac64  lea     rbp, [rsp+90h]
0x18009ac6c  mov     rax, cs:__security_cookie
0x18009ac73  xor     rax, rbp
0x18009ac76  mov     [rbp+0D0h+var_48], rax
0x18009ac7d  mov     edi, dword ptr [rbp+0D0h+Size]
0x18009ac83  mov     rbx, r8
0x18009ac86  mov     [rbp+0D0h+var_70], rcx
0x18009ac8a  xor     esi, esi
0x18009ac8c  mov     ecx, cs:?dwThreadPackage@@3KA; dwTlsIndex
0x18009ac92  mov     r14, r9
0x18009ac95  mov     [rbp+0D0h+var_C8], rbx
0x18009ac99  mov     r15, r8
0x18009ac9c  mov     [rbp+0D0h+var_78], rsi
0x18009aca0  mov     r13d, edx
0x18009aca3  mov     [rbp+0D0h+var_B4], esi
0x18009aca6  mov     r12d, edi
0x18009aca9  mov     [rbp+0D0h+var_B0], r9
0x18009acad  mov     [rbp+0D0h+Src], r8
0x18009acb1  mov     [rbp+0D0h+var_CC], edi
0x18009acb4  mov     [rbp+0D0h+var_D0], edi
0x18009acb7  call    cs:__imp_TlsGetValue
0x18009acbe  nop     dword ptr [rax+rax+00h]
0x18009acc3  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x18009acc9  mov     [rbp+0D0h+lpTlsValue], rax
0x18009accd  mov     [rbp+0D0h+hKey], rsi
0x18009acd1  mov     [rbp+0D0h+var_B8], esi
0x18009acd4  call    cs:__imp_TlsGetValue
0x18009acdb  nop     dword ptr [rax+rax+00h]
0x18009ace0  mov     [rbp+0D0h+TokenHandle], 0
0x18009ace8  mov     rsi, rax
0x18009aceb  mov     [rbp+0D0h+var_A8], rax
0x18009acef  cmp     r13d, 9
0x18009acf3  jz      loc_18009C0FE
0x18009acf9  cmp     edi, 4
0x18009acfc  jbe     short loc_18009AD13
0x18009acfe  cmp     r13d, 0Ah
0x18009ad02  jnz     short loc_18009AD13
0x18009ad04  cmp     dword ptr [rbx], 54h ; 'T'
0x18009ad07  jnz     short loc_18009AD13
0x18009ad09  test    byte ptr [rax+44h], 80h
0x18009ad0d  jnz     loc_18009C0FE
0x18009ad13  mov     [rbp+0D0h+hObject], 0
0x18009ad1b  mov     r14d, 1
0x18009ad21  cmp     edi, 4
0x18009ad24  jbe     loc_18009AE63
0x18009ad2a  cmp     dword ptr [r15], 52h ; 'R'
0x18009ad2e  jnz     loc_18009AE63
0x18009ad34  cmp     r13d, 0Ah
0x18009ad38  ja      loc_18009AE63
0x18009ad3e  mov     eax, 434h
0x18009ad43  bt      eax, r13d
0x18009ad47  jnb     loc_18009AE63
0x18009ad4d  lea     r9, [rbp+0D0h+var_C8]; void **
0x18009ad51  mov     [rbp+0D0h+var_BC], 0
0x18009ad58  lea     r8, [rbp+0D0h+var_D0]; unsigned int *
0x18009ad5c  mov     [rbp+0D0h+var_C0], 0
0x18009ad63  mov     rcx, r15; void *
0x18009ad66  mov     dword ptr [r15], 2
0x18009ad6d  call    ?NegpConvertWOWInteractiveLogonBuffer@@YAJPEAX0PEAKPEAPEAX@Z; NegpConvertWOWInteractiveLogonBuffer(void *,void *,ulong *,void * *)
0x18009ad72  mov     r12, [rbp+0D0h+var_C8]
0x18009ad76  mov     edi, eax
0x18009ad78  test    eax, eax
0x18009ad7a  js      loc_18009AE5B
0x18009ad80  mov     r8d, [rbp+0D0h+var_D0]; unsigned int
0x18009ad84  lea     rax, [rbp+0D0h+var_C0]
0x18009ad88  mov     rbx, [rbp+0D0h+arg_70]
0x18009ad8f  mov     rcx, r12; void *
0x18009ad92  mov     rsi, [rbp+0D0h+arg_68]
0x18009ad99  mov     r15, [rbp+0D0h+arg_60]
0x18009ada0  mov     rdx, [rbp+0D0h+var_B0]; void *
0x18009ada4  mov     [rsp+160h+var_120], rax; int *
0x18009ada9  lea     rax, [rbp+0D0h+var_BC]
0x18009adad  mov     [rsp+160h+var_128], rax; unsigned int *
0x18009adb2  mov     [rsp+160h+var_130], rbx; struct _UNICODE_STRING **
0x18009adb7  mov     [rsp+160h+lpThreadId], rsi; struct _UNICODE_STRING **
0x18009adbc  mov     [rsp+160h+phkResult], r15; struct _UNICODE_STRING **
0x18009adc1  mov     [rbp+0D0h+var_CC], r8d
0x18009adc5  call    ?NegpIsVirtualAccount@@YAJPEAX0KW4_SECURITY_LOGON_TYPE@@PEAPEAU_UNICODE_STRING@@22PEAKPEAH@Z; NegpIsVirtualAccount(void *,void *,ulong,_SECURITY_LOGON_TYPE,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,ulong *,int *)
0x18009adca  mov     edi, eax
0x18009adcc  test    eax, eax
0x18009adce  js      loc_18009C089
0x18009add4  cmp     [rbp+0D0h+var_C0], 0
0x18009add8  jnz     short loc_18009ADE4
0x18009adda  mov     edi, 0C000000Dh
0x18009addf  jmp     loc_18009C089
0x18009ade4  mov     rax, [rbp+0D0h+arg_80]
0x18009adeb  mov     ecx, r13d; enum _SECURITY_LOGON_TYPE
0x18009adee  mov     r9, [rbp+0D0h+arg_30]; void **
0x18009adf5  mov     r8, [rbp+0D0h+arg_40]; struct _LUID *
0x18009adfc  mov     edx, [rbp+0D0h+var_BC]; unsigned int
0x18009adff  mov     [rsp+160h+var_100], rax; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x18009ae04  mov     rax, [rbp+0D0h+arg_78]
0x18009ae0b  mov     [rsp+160h+var_108], rax; struct _SECPKG_PRIMARY_CRED *
0x18009ae10  mov     rax, [rbp+0D0h+arg_58]
0x18009ae17  mov     [rsp+160h+var_110], rbx; struct _UNICODE_STRING **
0x18009ae1c  mov     [rsp+160h+var_118], rsi; struct _UNICODE_STRING **
0x18009ae21  mov     [rsp+160h+var_120], r15; struct _UNICODE_STRING **
0x18009ae26  mov     [rsp+160h+var_128], rax; void **
0x18009ae2b  mov     rax, [rbp+0D0h+arg_50]
0x18009ae32  mov     [rsp+160h+var_130], rax; enum _LSA_TOKEN_INFORMATION_TYPE *
0x18009ae37  mov     rax, [rbp+0D0h+arg_48]
0x18009ae3e  mov     [rsp+160h+lpThreadId], rax; int *
0x18009ae43  mov     rax, [rbp+0D0h+arg_38]
0x18009ae4a  mov     [rsp+160h+phkResult], rax; unsigned int *
0x18009ae4f  call    ?NegpMakeVirtualAccountToken@@YAJW4_SECURITY_LOGON_TYPE@@KPEAU_LUID@@PEAPEAXPEAKPEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@2PEAPEAU_UNICODE_STRING@@66PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; NegpMakeVirtualAccountToken(_SECURITY_LOGON_TYPE,ulong,_LUID *,void * *,ulong *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x18009ae54  mov     edi, eax
0x18009ae56  jmp     loc_18009C089
0x18009ae5b  mov     ebx, [rbp+0D0h+var_D0]
0x18009ae5e  jmp     loc_18009C08C
0x18009ae63  mov     edi, 0C000005Eh
0x18009ae68  cmp     r13d, 5
0x18009ae6c  jnz     loc_18009B02A
0x18009ae72  lea     r9, [rbp+0D0h+var_C8]; void **
0x18009ae76  mov     [rbp+0D0h+var_C0], 0
0x18009ae7d  lea     r8, [rbp+0D0h+var_D0]; unsigned int *
0x18009ae81  mov     rcx, r15; void *
0x18009ae84  call    ?NegpConvertWOWInteractiveLogonBuffer@@YAJPEAX0PEAKPEAPEAX@Z; NegpConvertWOWInteractiveLogonBuffer(void *,void *,ulong *,void * *)
0x18009ae89  mov     edi, eax
0x18009ae8b  test    eax, eax
0x18009ae8d  js      loc_18009C1DD
0x18009ae93  mov     r12, [rbp+0D0h+var_C8]
0x18009ae97  mov     ebx, [rbp+0D0h+var_D0]
0x18009ae9a  mov     [rbp+0D0h+var_CC], ebx
0x18009ae9d  cmp     r15, r12
0x18009aea0  jnz     short loc_18009AEC7
0x18009aea2  mov     ecx, ebx
0x18009aea4  call    LsapAllocate
0x18009aea9  mov     r12, rax
0x18009aeac  test    rax, rax
0x18009aeaf  jz      loc_18009B140
0x18009aeb5  mov     r8d, dword ptr [rbp+0D0h+Size]; Size
0x18009aebc  mov     rdx, r15; Src
0x18009aebf  mov     rcx, rax; void *
0x18009aec2  call    memcpy_0
0x18009aec7  mov     rcx, [rbp+0D0h+arg_70]
0x18009aece  lea     rax, [rbp+0D0h+var_C0]
0x18009aed2  mov     r9, [rbp+0D0h+arg_60]; struct _UNICODE_STRING **
0x18009aed9  mov     r8d, ebx; unsigned int
0x18009aedc  mov     rdx, [rbp+0D0h+var_B0]; void *
0x18009aee0  mov     [rsp+160h+var_130], rax; unsigned int *
0x18009aee5  mov     [rsp+160h+lpThreadId], rcx; struct _UNICODE_STRING **
0x18009aeea  mov     rcx, [rbp+0D0h+arg_68]
0x18009aef1  mov     [rsp+160h+phkResult], rcx; struct _UNICODE_STRING **
0x18009aef6  mov     rcx, r12; void *
0x18009aef9  call    ?NegpIsHardcodedServiceAccount@@YAHPEAX0KPEAPEAU_UNICODE_STRING@@11PEAK@Z; NegpIsHardcodedServiceAccount(void *,void *,ulong,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,ulong *)
0x18009aefe  test    eax, eax
0x18009af00  jz      loc_18009B002
0x18009af06  mov     ecx, [rbp+0D0h+var_C0]; unsigned int
0x18009af09  mov     rax, [rbp+0D0h+arg_80]
0x18009af10  cmp     ecx, 200Dh
0x18009af16  jnz     short loc_18009AF8D
0x18009af18  mov     r9, [rbp+0D0h+arg_48]; int *
0x18009af1f  mov     r8, [rbp+0D0h+arg_38]; unsigned int *
0x18009af26  mov     rdx, [rbp+0D0h+arg_30]; void **
0x18009af2d  mov     rcx, [rbp+0D0h+arg_40]; struct _LUID *
0x18009af34  mov     [rsp+160h+var_110], rax; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x18009af39  mov     rax, [rbp+0D0h+arg_78]
0x18009af40  mov     [rsp+160h+var_118], rax; struct _SECPKG_PRIMARY_CRED *
0x18009af45  mov     rax, [rbp+0D0h+arg_70]
0x18009af4c  mov     [rsp+160h+var_120], rax; struct _UNICODE_STRING **
0x18009af51  mov     rax, [rbp+0D0h+arg_68]
0x18009af58  mov     [rsp+160h+var_128], rax; struct _UNICODE_STRING **
0x18009af5d  mov     rax, [rbp+0D0h+arg_60]
0x18009af64  mov     [rsp+160h+var_130], rax; struct _UNICODE_STRING **
0x18009af69  mov     rax, [rbp+0D0h+arg_58]
0x18009af70  mov     [rsp+160h+lpThreadId], rax; void **
0x18009af75  mov     rax, [rbp+0D0h+arg_50]
0x18009af7c  mov     [rsp+160h+phkResult], rax; enum _LSA_TOKEN_INFORMATION_TYPE *
0x18009af81  call    ?NegpMakeSystemToken@@YAJPEAU_LUID@@PEAPEAXPEAKPEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@1PEAPEAU_UNICODE_STRING@@55PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; NegpMakeSystemToken(_LUID *,void * *,ulong *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x18009af86  mov     edi, eax
0x18009af88  jmp     loc_18009C08C
0x18009af8d  mov     r9, [rbp+0D0h+arg_38]; unsigned int *
0x18009af94  mov     r8, [rbp+0D0h+arg_30]; void **
0x18009af9b  mov     rdx, [rbp+0D0h+arg_40]; struct _LUID *
0x18009afa2  mov     [rsp+160h+var_108], rax; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x18009afa7  mov     rax, [rbp+0D0h+arg_78]
0x18009afae  mov     [rsp+160h+var_110], rax; struct _SECPKG_PRIMARY_CRED *
0x18009afb3  mov     rax, [rbp+0D0h+arg_70]
0x18009afba  mov     [rsp+160h+var_118], rax; struct _UNICODE_STRING **
0x18009afbf  mov     rax, [rbp+0D0h+arg_68]
0x18009afc6  mov     [rsp+160h+var_120], rax; struct _UNICODE_STRING **
0x18009afcb  mov     rax, [rbp+0D0h+arg_60]
0x18009afd2  mov     [rsp+160h+var_128], rax; struct _UNICODE_STRING **
0x18009afd7  mov     rax, [rbp+0D0h+arg_58]
0x18009afde  mov     [rsp+160h+var_130], rax; void **
0x18009afe3  mov     rax, [rbp+0D0h+arg_50]
0x18009afea  mov     [rsp+160h+lpThreadId], rax; enum _LSA_TOKEN_INFORMATION_TYPE *
0x18009afef  mov     rax, [rbp+0D0h+arg_48]
0x18009aff6  mov     [rsp+160h+phkResult], rax; int *
0x18009affb  call    ?NegpMakeServiceToken@@YAJKPEAU_LUID@@PEAPEAXPEAKPEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@1PEAPEAU_UNICODE_STRING@@55PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; NegpMakeServiceToken(ulong,_LUID *,void * *,ulong *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x18009b000  jmp     short loc_18009AF86
0x18009b002  test    r12, r12
0x18009b005  jz      short loc_18009B024
0x18009b007  mov     rax, rbx
0x18009b00a  mov     rdx, r12
0x18009b00d  test    ebx, ebx
0x18009b00f  jz      short loc_18009B01C
0x18009b011  mov     byte ptr [rdx], 0
0x18009b014  add     rdx, r14; void *
0x18009b017  sub     rax, r14
0x18009b01a  jnz     short loc_18009B011
0x18009b01c  mov     rcx, r12; struct _RTL_BALANCED_NODE *
0x18009b01f  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18009b024  mov     r12d, [rbp+0D0h+var_CC]
0x18009b028  xor     ebx, ebx
0x18009b02a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID57824352@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID57824352@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57824352> `wil::Feature<__WilFeatureTraits_Feature_ID57824352>::GetImpl(void)'::`2'::impl
0x18009b031  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID57824352@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57824352>::__private_IsEnabled(void)
0x18009b036  lea     rdx, WPP_GLOBAL_Control
0x18009b03d  test    al, al
0x18009b03f  jz      loc_18009B130
0x18009b045  lea     eax, [r13-2]
0x18009b049  test    eax, 0FFFFFFF7h
0x18009b04e  jnz     loc_18009B130
0x18009b054  cmp     r12d, 30h ; '0'
0x18009b058  jb      loc_18009B130
0x18009b05e  cmp     dword ptr [rbx], 201h
0x18009b064  jnz     loc_18009B130
0x18009b06a  cmp     dword ptr [rbx+8], 30h ; '0'
0x18009b06e  jb      loc_18009B130
0x18009b074  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b07b  cmp     rcx, rdx
0x18009b07e  jz      short loc_18009B09B
0x18009b080  test    byte ptr [rcx+1Ch], 4
0x18009b084  jz      short loc_18009B09B
0x18009b086  mov     rcx, [rcx+10h]
0x18009b08a  lea     r8, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids
0x18009b091  mov     edx, 54h ; 'T'
0x18009b096  call    WPP_SF_
0x18009b09b  lea     r9, [rbp+0D0h+var_B4]; unsigned int *
0x18009b09f  mov     edx, r12d; AuthIdentityLength
0x18009b0a2  lea     r8, [rbp+0D0h+var_78]; void **
0x18009b0a6  mov     rcx, rbx; AuthIdentityByteArray
0x18009b0a9  call    ?LsapHandlePossiblePlaceholderCredential@@YAJPEAXKPEAPEAXPEAK@Z; LsapHandlePossiblePlaceholderCredential(void *,ulong,void * *,ulong *)
0x18009b0ae  mov     edi, eax
0x18009b0b0  test    eax, eax
0x18009b0b2  js      short loc_18009B100
0x18009b0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b0bb  lea     rdx, WPP_GLOBAL_Control
0x18009b0c2  cmp     rcx, rdx
0x18009b0c5  jz      short loc_18009B0E2
0x18009b0c7  test    byte ptr [rcx+1Ch], 4
0x18009b0cb  jz      short loc_18009B0E2
0x18009b0cd  mov     rcx, [rcx+10h]
0x18009b0d1  lea     r8, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids
0x18009b0d8  mov     edx, 55h ; 'U'
0x18009b0dd  call    WPP_SF_
0x18009b0e2  bts     dword ptr [rsi+44h], 0Fh
0x18009b0e7  mov     eax, [rbp+0D0h+var_B4]
0x18009b0ea  mov     r12d, eax
0x18009b0ed  mov     r15, [rbp+0D0h+var_78]
0x18009b0f1  mov     [rbp+0D0h+Src], r15
0x18009b0f5  mov     dword ptr [rbp+0D0h+Size], eax
0x18009b0fb  mov     [rbp+0D0h+var_CC], eax
0x18009b0fe  jmp     short loc_18009B130
0x18009b100  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b107  lea     rdx, WPP_GLOBAL_Control
0x18009b10e  cmp     rcx, rdx
0x18009b111  jz      short loc_18009B12E
0x18009b113  test    byte ptr [rcx+1Ch], 4
0x18009b117  jz      short loc_18009B12E
0x18009b119  mov     rcx, [rcx+10h]
0x18009b11d  lea     r8, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids
0x18009b124  mov     edx, 56h ; 'V'
0x18009b129  call    WPP_SF_
0x18009b12e  xor     edi, edi
0x18009b130  mov     ecx, r12d
0x18009b133  call    LsapAllocate
0x18009b138  mov     r12, rax
0x18009b13b  test    rax, rax
0x18009b13e  jnz     short loc_18009B14A
0x18009b140  mov     eax, 0C000009Ah
0x18009b145  jmp     loc_18009C1DD
0x18009b14a  mov     eax, cs:?NegPackageCount@@3KA; ulong NegPackageCount
0x18009b150  cmp     eax, 200h
0x18009b155  jb      short loc_18009B161
0x18009b157  mov     edi, 0C00000BBh
0x18009b15c  jmp     loc_18009C089
0x18009b161  lea     rbx, ds:0[rax*8]
0x18009b169  xor     eax, eax
0x18009b16b  mov     [rbp+0D0h+var_C8], rax
0x18009b16f  test    rbx, rbx
0x18009b172  jz      short loc_18009B1E6
0x18009b174  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18009b17b  ja      short loc_18009B1E6
0x18009b17d  mov     rcx, cs:g_ulAdditionalProbeSize
0x18009b184  add     rcx, 8
0x18009b188  add     rcx, rbx
0x18009b18b  cmp     rcx, rbx
0x18009b18e  jb      short loc_18009B1E6
0x18009b190  call    VerifyStackAvailable
0x18009b195  test    eax, eax
  ... truncated ...
```
