# LsapConnectLocalUser(void *,_LUID *,_UNICODE_STRING *,_GUID *,ulong,uchar *,long *,_LocalConnectFailureReason *)

- ea: `0x180124194`
- end: `0x180124e60`
- name: `?LsapConnectLocalUser@@YAJPEAXPEAU_LUID@@PEAU_UNICODE_STRING@@PEAU_GUID@@KPEAEPEAJPEAW4_LocalConnectFailureReason@@@Z`
- size: `3276`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct _LUID *@<rdx>, struct _UNICODE_STRING *@<r8>, struct _GUID *@<r9>, unsigned int, unsigned __int8 *, int *, enum _LocalConnectFailureReason *)`
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18012a610`

## callees

- `0x180001fa0`
- `0x180001fe4`
- `0x1800040d0`
- `0x18000c300`
- `0x180011278`
- `0x18005faf0`
- `0x18005fb34`
- `0x18005fecc`
- `0x18006064c`
- `0x180060888`
- `0x180060cb0`
- `0x180074aa8`
- `0x18007f964`
- `0x18007fbd0`
- `0x18007ff6c`
- `0x180081b18`
- `0x180082da0`
- `0x18008dcd8`
- `0x18009a064`
- `0x1800b66ec`
- `0x1800b86d0`
- `0x1800d7dc0`
- `0x1800d7ed8`
- `0x1800d7f9c`
- `0x1800d8060`
- `0x180123828`
- `0x1801239b0`
- `0x180123d14`
- `0x180123d94`
- `0x180124194`
- `0x180126b7c`
- `0x18012716c`
- `0x180127348`
- `0x1801276e4`
- `0x180127eac`
- `0x180128284`
- `0x180128838`
- `0x180128d2c`
- `0x180129f18`
- `0x18012cd8c`
- `0x18012cebc`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801243f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801243f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124826`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801243e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801243e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180124c38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180124c4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180124c38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180124c4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180124c62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180124cf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180124c62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180124cf0`
- `ntdll!NtPrivilegeCheck` at `0x180124472`
- `ntdll!NtPrivilegeCheck` at `0x180124472`
- `ntdll!RtlAcquireResourceExclusive` at `0x1801248ff`
- `ntdll!RtlAcquireResourceExclusive` at `0x1801248ff`
- `ntdll!RtlReleaseResource` at `0x18012494c`
- `ntdll!RtlReleaseResource` at `0x18012494c`
- `ntdll!NtClose` at `0x180124c23`
- `ntdll!NtClose` at `0x180124c23`
- `RPCRT4!I_RpcMapWin32Status` at `0x180124373`
- `RPCRT4!I_RpcMapWin32Status` at `0x180124373`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18012435f`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18012435f`
- `RPCRT4!UuidEqual` at `0x18012456b`
- `RPCRT4!UuidEqual` at `0x18012456b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801247f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180124ac9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801247f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180124ac9`
- `USERENV!__imp_GetUserProfileDirectoryForUserSidW` at `0x18012487b`
- `USERENV!__imp_GetUserProfileDirectoryForUserSidW` at `0x18012487b`
- `SspiCli!SspiLocalFree` at `0x1801249ea`
- `SspiCli!SspiLocalFree` at `0x180124d7f`
- `SspiCli!SspiLocalFree` at `0x1801249ea`
- `SspiCli!SspiLocalFree` at `0x180124d7f`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalRemoveCredential` at `0x180124adf`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalRemoveCredential` at `0x180124adf`

## string_xrefs

- `0x180124630`: `LsapLocateSidCacheEntry`
- `0x180124381`: `I_RpcOpenClientProcess`
- `0x1801243fe`: `OpenProcessToken`
- `0x180124484`: `NtPrivilegeCheck`
- `0x18012483d`: `ConvertSidToStringSidW`
- `0x1801248d6`: `LsapCreateCredKeyFromPassword`

## pseudocode

```c
__int64 __fastcall LsapConnectLocalUser(
        void *a1,
        struct _LUID *a2,
        struct _UNICODE_STRING *a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        int *a7,
        enum _LocalConnectFailureReason *a8)
{
  struct _LSAP_PER_SID_INFO *v9; // r13
  struct _LUID *v11; // r12
  struct _UNICODE_STRING *v12; // rax
  const char *v13; // rcx
  RPC_STATUS v14; // eax
  unsigned int v15; // eax
  void *v16; // rdx
  int v17; // edi
  LsaHandleCache *v18; // rcx
  __int64 v19; // rdx
  DWORD LastError; // eax
  NTSTATUS v21; // eax
  __int64 v22; // rdx
  char v23; // r12
  LsaHandleCache *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // eax
  void *v28; // rbx
  int started; // eax
  int UserNameAndAuthBuffer; // eax
  const char *v31; // rcx
  int LocalUserName; // eax
  struct _RTL_BALANCED_NODE *v33; // rsi
  struct _UNICODE_STRING *v34; // r14
  PSID v35; // rdi
  const char *v36; // rcx
  __int64 v37; // rdx
  char v38; // r12
  int v39; // eax
  const char *v40; // rcx
  struct _LUID *v41; // rdi
  __int64 (__fastcall *ParentValue)(struct _RTL_BALANCED_NODE *, void *, struct _LUID *, PWSTR, PVOID, unsigned int, int *); // rax
  unsigned int v43; // ebx
  _BYTE *v44; // rsi
  int v45; // eax
  __int64 v46; // rdx
  _BYTE *i; // rax
  struct _RTL_BALANCED_NODE *v48; // rbx
  LsaHandleCache *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // r9
  struct _RTL_BALANCED_NODE *v52; // rax
  __int64 v53; // rcx
  struct _CREDENTIAL_KEY *v54; // rdx
  __int64 v55; // rax
  void *v56; // rdx
  PWSTR Buffer; // rax
  __int64 Length; // rcx
  _BYTE *v59; // rax
  __int64 v60; // rcx
  char v62; // [rsp+60h] [rbp-A0h]
  bool v63; // [rsp+70h] [rbp-90h]
  struct _RTL_BALANCED_NODE *v64; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 Result[8]; // [rsp+80h] [rbp-80h] BYREF
  struct _LUID *v66; // [rsp+88h] [rbp-78h]
  PSID Sid; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v68; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v69; // [rsp+9Ch] [rbp-64h] BYREF
  struct _LSAP_PER_SID_INFO *v70; // [rsp+A0h] [rbp-60h] BYREF
  struct _CREDENTIAL_KEY *v71; // [rsp+A8h] [rbp-58h] BYREF
  PVOID DataBuffer; // [rsp+B0h] [rbp-50h] BYREF
  void *v73; // [rsp+B8h] [rbp-48h] BYREF
  struct _RTL_BALANCED_NODE *v74; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v75; // [rsp+C8h] [rbp-38h] BYREF
  struct _LUID v76; // [rsp+D8h] [rbp-28h] BYREF
  void *ClientProcess; // [rsp+E0h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+E8h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+F0h] [rbp-10h] BYREF
  LPWSTR v80; // [rsp+F8h] [rbp-8h] BYREF
  LPWSTR StringSid; // [rsp+100h] [rbp+0h] BYREF
  struct _UNICODE_STRING *v82; // [rsp+108h] [rbp+8h]
  RPC_STATUS Status; // [rsp+110h] [rbp+10h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+118h] [rbp+18h] BYREF
  struct _UNICODE_STRING v85; // [rsp+128h] [rbp+28h] BYREF
  _OWORD v86[2]; // [rsp+138h] [rbp+38h] BYREF
  struct _GUID *v87; // [rsp+158h] [rbp+58h]
  int *v88; // [rsp+160h] [rbp+60h]
  struct _UNICODE_STRING v89; // [rsp+168h] [rbp+68h] BYREF
  struct _UNICODE_STRING v90; // [rsp+178h] [rbp+78h] BYREF
  struct _UNICODE_STRING v91; // [rsp+188h] [rbp+88h] BYREF
  struct _UNICODE_STRING v92; // [rsp+198h] [rbp+98h] BYREF
  struct _UNICODE_STRING v93; // [rsp+1A8h] [rbp+A8h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+1B8h] [rbp+B8h] BYREF
  int v95; // [rsp+1D0h] [rbp+D0h] BYREF
  char v96; // [rsp+1D4h] [rbp+D4h]
  struct _GUID v97; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v98[528]; // [rsp+200h] [rbp+100h] BYREF

  v88 = a7;
  v63 = 0;
  DestinationString = 0;
  v9 = 0;
  v85 = 0;
  v74 = 0;
  v75 = 0;
  v71 = 0;
  v11 = a2;
  hObject = 0;
  v76 = 0;
  v64 = 0;
  v73 = 0;
  v69 = 0;
  v62 = 0;
  DataBuffer = 0;
  v68 = 0;
  v70 = 0;
  memset(v86, 0, sizeof(v86));
  Sid = 0;
  StringSid = 0;
  v89 = 0;
  ClientProcess = 0;
  v91 = 0;
  TokenHandle = 0;
  v90 = 0;
  v80 = 0;
  v92 = 0;
  v87 = a4;
  v93 = 0;
  v82 = a3;
  v66 = a2;
  CONNECTED_TRACE_ENTER("LsapConnectLocalUser");
  v95 = 0;
  v96 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const LsaSrvTraceLogger,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v95);
  if ( (unsigned int)dword_18019A2B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18019A2B0, 0x200000000000LL) )
  {
    if ( v96 )
      _tlgGuidIsZero(&v97);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18019A2B0,
      (__int64)byte_180180015);
  }
  if ( !a4 || (v12 = v82) == 0 || !a6 || !a7 || !a8 )
  {
    v13 = "A required parameter is NULL";
    goto LABEL_119;
  }
  *a7 = 0;
  *(_DWORD *)a8 = 0;
  if ( (LsapInspectString(v12) & 0x47) != 0 )
  {
    v13 = "LsapInspectString(EncodedLocalPassword)";
LABEL_119:
    v22 = 3221225485LL;
    v17 = -1073741811;
    goto LABEL_120;
  }
  if ( *(_DWORD *)a6 == 84 )
  {
    v14 = I_RpcOpenClientProcess(0, 0x1000u, &ClientProcess);
    if ( v14 )
    {
      v15 = I_RpcMapWin32Status(v14);
      CONNECTED_TRACE_ERROR("I_RpcOpenClientProcess", v15);
      v17 = -1073741790;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_121;
      v19 = 38;
      goto LABEL_18;
    }
    if ( !OpenProcessToken(ClientProcess, 0xEu, &TokenHandle) )
    {
      LastError = GetLastError();
      CONNECTED_TRACE_ERROR("OpenProcessToken", LastError);
      v17 = -1073741790;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_121;
      v19 = 39;
      goto LABEL_18;
    }
    RequiredPrivileges.Privilege[0].Luid = LsapTcbPrivilege;
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.Privilege[0].Attributes = 0;
    Result[0] = 0;
    v21 = NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result);
    if ( v21 < 0 )
    {
      CONNECTED_TRACE_ERROR("NtPrivilegeCheck", (unsigned int)v21);
      v17 = -1073741790;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_121;
      v19 = 40;
      goto LABEL_18;
    }
    if ( !Result[0] )
    {
      v17 = -1073741790;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_121;
      v19 = 41;
      goto LABEL_18;
    }
  }
  else if ( !(unsigned int)LsapHasConnectPermission(a1) )
  {
    v17 = -1073741790;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_121;
    v19 = 42;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids, 3221225506LL);
LABEL_121:
    v28 = 0;
    goto LABEL_122;
  }
  v17 = LsapRefIdProvByGuidEx(a4, 1, (struct _LSAP_IDPROV_REG_ENTRY **)&v64);
  if ( v17 < 0 )
  {
    v22 = (unsigned int)v17;
    v13 = "LsapRefIdProvByGuid";
LABEL_120:
    CONNECTED_TRACE_ERROR(v13, v22);
    goto LABEL_121;
  }
  Status = 0;
  if ( UuidEqual(a4, (UUID *)&stru_1801625B0, &Status) )
  {
    v23 = 1;
    goto LABEL_49;
  }
  if ( (LsapNoConnectedUser & 3) != 0 )
  {
    v17 = -1073741790;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_121;
    v25 = 43;
    v26 = 3221225506LL;
    goto LABEL_43;
  }
  if ( ((__int64)v64[2].Right & 1) == 0 )
  {
    v17 = -1073741637;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_121;
    v25 = 44;
    v26 = 3221225659LL;
LABEL_43:
    WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids, v26);
    goto LABEL_121;
  }
  v23 = 0;
  v63 = 1;
LABEL_49:
  v27 = LsapLocateSidCacheEntry(v66, &v70);
  v17 = v27;
  if ( v27 < 0 )
  {
    CONNECTED_TRACE_ERROR("LsapLocateSidCacheEntry", (unsigned int)v27);
    v9 = v70;
LABEL_51:
    v11 = v66;
    v28 = 0;
LABEL_122:
    v33 = v64;
    goto LABEL_123;
  }
  v9 = v70;
  started = LsapTryStartAccountTransition(v70);
  v17 = started;
  if ( started < 0 )
  {
    CONNECTED_TRACE_WARNING("LsapStartAccountTransition", (unsigned int)started);
    goto LABEL_51;
  }
  v62 = 1;
  UserNameAndAuthBuffer = LsapGetUserNameAndAuthBuffer(a1, a6, a5, (unsigned __int8 **)&DataBuffer, &v68, &v75);
  v17 = UserNameAndAuthBuffer;
  if ( UserNameAndAuthBuffer < 0 )
  {
    v31 = "LsapGetUserNameAndAuthBuffer";
LABEL_56:
    CONNECTED_TRACE_ERROR(v31, (unsigned int)UserNameAndAuthBuffer);
    goto LABEL_51;
  }
  if ( !v75.Buffer || !v75.Length )
  {
    v17 = -1073741811;
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_51;
    v50 = 45;
    v51 = 3221225485LL;
LABEL_114:
    WPP_SF_d(*((_QWORD *)v49 + 2), v50, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids, v51);
    goto LABEL_51;
  }
  UserNameAndAuthBuffer = LsapDecryptPassword(a1, v82, &v85);
  v17 = UserNameAndAuthBuffer;
  if ( UserNameAndAuthBuffer < 0 )
  {
    v31 = "LsapDecryptPassword";
    goto LABEL_56;
  }
  LocalUserName = LsapGetLocalUserName(*((PSID *)v9 + 3), &DestinationString, a8);
  if ( LocalUserName < 0 )
  {
    CONNECTED_TRACE_ERROR("LsapGetLocalUserName", (unsigned int)LocalUserName);
    v17 = -1073741790;
    goto LABEL_51;
  }
  if ( DestinationString.Length > 0x200u || (LsapInspectString(&DestinationString) & 0x10) != 0 )
  {
    v17 = -1073741595;
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_51;
    v50 = 46;
    v51 = 3221225701LL;
    goto LABEL_114;
  }
  v33 = v64;
  v34 = (struct _UNICODE_STRING *)&v64[1].16;
  if ( LsapResolveIdentityInternetSid(
         a1,
         &v75,
         (struct _UNICODE_STRING *)&v64[1].16,
         &Sid,
         &v91,
         &v90,
         &v89,
         &v93,
         &v92) >= 0 )
  {
    v35 = Sid;
    if ( Sid )
    {
      if ( (int)LsapFindConnectedUserByInternetSid(Sid, 0) >= 0 )
      {
        v36 = "ConnectedAccounts: Internet account is a connected account.";
LABEL_69:
        v37 = 3221225571LL;
        *(_DWORD *)a8 = 2;
        v17 = -1073741725;
LABEL_70:
        CONNECTED_TRACE_ERROR(v36, v37);
        v28 = 0;
LABEL_71:
        v11 = v66;
        goto LABEL_123;
      }
      if ( (int)LsapFindMappedSidInternal(v35) >= 0 )
      {
        v36 = "ConnectedAccounts: Internet account is a connected AAD account.";
        goto LABEL_69;
      }
      if ( !ConvertSidToStringSidW(v35, &StringSid) )
      {
        if ( (int)GetLastError() > 0 )
          v17 = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          v17 = GetLastError();
        CONNECTED_TRACE_ERROR("ConvertSidToStringSidW", (unsigned int)v17);
        v38 = 1;
        v62 = 1;
        if ( v17 >= 0 )
        {
LABEL_127:
          v48 = (struct _RTL_BALANCED_NODE *)Sid;
          goto LABEL_128;
        }
        v11 = v66;
        v28 = 0;
LABEL_123:
        if ( (BYTE4(v86[0]) & 1) != 0 )
        {
          LsapRollbackFailedConnect(
            v63,
            &DestinationString,
            &v85,
            &v75,
            (struct _CONNECT_OPERATION_SAM_RECOVERY_INFO *)v86,
            (struct _LSAP_IDPROV_REG_ENTRY *)v33,
            *((PSID *)v9 + 3),
            &v76,
            v28,
            hObject,
            v73);
          if ( v11 )
            LsapInvalidateDsNames(v11, 0, v63);
        }
        v38 = v62;
        goto LABEL_127;
      }
      LODWORD(v70) = 261;
      if ( (unsigned int)GetUserProfileDirectoryForUserSidW(StringSid, v98, &v70) )
      {
        v36 = "ConnectedAccounts: Internet account is an existing account on the machine.";
        goto LABEL_69;
      }
    }
  }
  v39 = LsapLogonUserWithPassword(&DestinationString, &v85, &hObject);
  v28 = 0;
  v17 = v39;
  if ( v39 < 0 )
  {
    v40 = "LsapLogonUserWithPassword";
LABEL_101:
    CONNECTED_TRACE_ERROR(v40, (unsigned int)v39);
    goto LABEL_71;
  }
  v39 = LsapCreateCredKeyFromPassword(&v85, (struct _CREDENTIAL_KEY **)&v74);
  v17 = v39;
  if ( v39 < 0 )
  {
    v40 = "LsapCreateCredKeyFromPassword";
    goto LABEL_101;
  }
  v39 = LsapPrimeDPAPI(a1);
  v17 = v39;
  if ( v39 < 0 )
  {
    v40 = "LsapPrimeDPAPI";
    goto LABEL_101;
  }
  RtlAcquireResourceExclusive(&g_ConnectedAccountStoreLock, 1u);
  v17 = LsapConnectAccountInSam(
          &DestinationString,
          &v75,
          v34,
          v87,
          v63,
          &v73,
          &v69,
          (struct _CONNECT_OPERATION_SAM_RECOVERY_INFO *)v86);
  RtlReleaseResource(&g_ConnectedAccountStoreLock);
  if ( v17 < 0 )
  {
    v37 = (unsigned int)v17;
    v36 = "LsapConnectAccountInSam";
    goto LABEL_70;
  }
  if ( v63 )
    *(_QWORD *)&v86[0] |= 0x4005F0000uLL;
  v41 = v66;
  LsapInvalidateDsNames(v66, 1, v63);
  ParentValue = (__int64 (__fastcall *)(struct _RTL_BALANCED_NODE *, void *, struct _LUID *, PWSTR, PVOID, unsigned int, int *))v33[9].ParentValue;
  if ( ParentValue )
  {
    v43 = v68;
    v44 = DataBuffer;
    v45 = ParentValue(v64, a1, v41, v75.Buffer, DataBuffer, v68, v88);
    v46 = v43;
    v17 = v45;
    v28 = 0;
    for ( i = v44; v46; --v46 )
      *i++ = 0;
    SspiLocalFree(v44);
    DataBuffer = 0;
    if ( v17 < 0 )
    {
      CONNECTED_TRACE_ERROR("ConnectLocalUser", (unsigned int)v17);
      v11 = v66;
      goto LABEL_122;
    }
    v28 = a1;
    v33 = v64;
    v76 = *v66;
  }
  else
  {
    v28 = 0;
  }
  DWORD1(v86[0]) |= 8u;
  v39 = ((__int64 (__fastcall *)(struct _RTL_BALANCED_NODE *, struct _LUID *, _QWORD, struct _CREDENTIAL_KEY **))v33[10].ParentValue)(
          v33,
          &v76,
          0,
          &v71);
  v17 = v39;
  if ( v39 < 0 )
  {
    v40 = "Prov->ProviderTable.GetCredentialKey";
    goto LABEL_101;
  }
  v39 = (*((__int64 (__fastcall **)(void *, struct _RTL_BALANCED_NODE *, struct _CREDENTIAL_KEY *, __int64))LsapDpapiIfTable
         + 5))(
          v28,
          v74,
          v71,
          1);
  v17 = v39;
  if ( v39 < 0 )
  {
    v40 = "LsaIfNotifyCredentialKeyChange";
    goto LABEL_101;
  }
  LsapSetSidCacheAuthorityName(v9, v34);
  LsapSetSidCacheCredKey(v9, v71);
  LsapClearLogonStatistics(v73);
  if ( v23 )
  {
    if ( ConvertSidToStringSidW(*((PSID *)v9 + 3), &v80) )
      NgcLocalRemoveCredential(v80, 0);
    v48 = (struct _RTL_BALANCED_NODE *)Sid;
    if ( Sid )
      LsapAdjustGroupMembership(*((struct _RPC_SID **)v9 + 3), Sid);
  }
  else
  {
    v48 = (struct _RTL_BALANCED_NODE *)Sid;
  }
  v38 = 1;
  v17 = 0;
LABEL_128:
  if ( ClientProcess )
    NtClose(ClientProcess);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( hObject )
    CloseHandle(hObject);
  if ( v80 )
    LocalFree(v80);
  v52 = v74;
  if ( v74 )
  {
    v53 = LODWORD(v74->Children[0]);
    if ( LODWORD(v74->Children[0]) )
    {
      do
      {
        LOBYTE(v52->Children[0]) = 0;
        v52 = (struct _RTL_BALANCED_NODE *)((char *)v52 + 1);
        --v53;
      }
      while ( v53 );
    }
    LsapSubProv_FreeRoutine(v74, v16);
  }
  v54 = v71;
  if ( v71 )
  {
    v55 = *(unsigned int *)v71;
    if ( *(_DWORD *)v71 )
    {
      do
      {
        *(_BYTE *)v54 = 0;
        v54 = (struct _CREDENTIAL_KEY *)((char *)v54 + 1);
        --v55;
      }
      while ( v55 );
    }
    ((void (__fastcall *)(struct _RTL_BALANCED_NODE *))v33[4].Children[0])(v33);
  }
  LsapFreeString(&DestinationString);
  LsapSecureFreeString(&v85);
  LsapFreeString(&v75);
  if ( v48 )
  {
    LsapSubProv_FreeRoutine(v48, v56);
    if ( StringSid )
      LocalFree(StringSid);
    LsapFreeString(&v89);
    LsapFreeString(&v90);
    LsapFreeString(&v91);
    LsapFreeString(&v92);
    LsapFreeString(&v93);
  }
  if ( v82 )
  {
    if ( v82->Length )
    {
      Buffer = v82->Buffer;
      if ( Buffer )
      {
        Length = v82->Length;
        if ( v82->Length )
        {
          do
          {
            *(_BYTE *)Buffer = 0;
            Buffer = (PWSTR)((char *)Buffer + 1);
            --Length;
          }
          while ( Length );
        }
      }
    }
  }
  v59 = DataBuffer;
  if ( DataBuffer )
  {
    v60 = v68;
    if ( v68 )
    {
      do
      {
        *v59++ = 0;
        --v60;
      }
      while ( v60 );
    }
    SspiLocalFree(DataBuffer);
  }
  if ( v73 )
    LsapSamExtCloseHandle(&v73);
  LsapDerefIdProv(v33);
  if ( v38 )
    LsapCompleteAccountTransition(v9);
  if ( v9 )
    LsapReleaseSidCacheEntry(v9);
  LsapFreeString((char *)v86 + 8);
  v95 = 2;
  if ( (unsigned int)dword_18019A2B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18019A2B0, 0x200000000000LL) )
  {
    v69 = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18019A2B0,
      (__int64)byte_18017FFE5);
  }
  CONNECTED_TRACE_EXIT_EX(1, "LsapConnectLocalUser", (unsigned int)v17);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const LsaSrvTraceLogger,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const LsaSrvTraceLogger,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v95);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180124194  push    rbp
0x180124196  push    rbx
0x180124197  push    rsi
0x180124198  push    rdi
0x180124199  push    r12
0x18012419b  push    r13
0x18012419d  push    r14
0x18012419f  push    r15
0x1801241a1  lea     rbp, [rsp-328h]
0x1801241a9  sub     rsp, 428h
0x1801241b0  mov     rax, cs:__security_cookie
0x1801241b7  xor     rax, rsp
0x1801241ba  mov     [rbp+360h+var_50], rax
0x1801241c1  mov     rdi, [rbp+360h+arg_30]
0x1801241c8  xor     eax, eax
0x1801241ca  mov     rsi, [rbp+360h+arg_28]
0x1801241d1  xorps   xmm0, xmm0
0x1801241d4  mov     rbx, [rbp+360h+arg_38]
0x1801241db  xorps   xmm1, xmm1
0x1801241de  mov     r15, rcx
0x1801241e1  mov     [rbp+360h+var_300], rdi
0x1801241e5  lea     rcx, aLsapconnectloc; "LsapConnectLocalUser"
0x1801241ec  mov     [rsp+460h+var_3F0], al
0x1801241f0  movups  xmmword ptr [rbp+360h+DestinationString.Length], xmm0
0x1801241f4  mov     [rsp+460h+var_3F8], rax
0x1801241f9  mov     r13d, eax
0x1801241fc  movups  xmmword ptr [rbp+360h+var_338.Length], xmm1
0x180124200  mov     [rbp+360h+var_3A0], rax
0x180124204  mov     r14, r9
0x180124207  movups  xmmword ptr [rbp+360h+var_398.Length], xmm0
0x18012420b  mov     [rbp+360h+var_3B8], rax
0x18012420f  mov     r12, rdx
0x180124212  mov     [rbp+360h+hObject], rax
0x180124216  mov     qword ptr [rbp+360h+var_388.LowPart], rax
0x18012421a  mov     [rsp+460h+var_3E8], rax
0x18012421f  mov     [rbp+360h+var_3A8], rax
0x180124223  mov     [rbp+360h+var_3C4], eax
0x180124226  mov     [rsp+460h+var_400], al
0x18012422a  mov     [rbp+360h+DataBuffer], rax
0x18012422e  mov     [rbp+360h+var_3C8], eax
0x180124231  mov     [rbp+360h+var_3C0], rax
0x180124235  movups  [rbp+360h+var_328], xmm0
0x180124239  mov     [rbp+360h+Sid], rax
0x18012423d  movups  [rbp+360h+var_318], xmm0
0x180124241  mov     [rbp+360h+StringSid], rax
0x180124245  movups  xmmword ptr [rbp+360h+var_2F8.Length], xmm0
0x180124249  mov     [rbp+360h+ClientProcess], rax
0x18012424d  movups  xmmword ptr [rbp+360h+var_2D8.Length], xmm1
0x180124254  mov     [rbp+360h+TokenHandle], rax
0x180124258  movups  xmmword ptr [rbp+360h+var_2E8.Length], xmm0
0x18012425c  mov     [rbp+360h+var_368], rax
0x180124260  movups  xmmword ptr [rbp+360h+var_2C8.Length], xmm1
0x180124267  mov     [rbp+360h+var_308], r9
0x18012426b  movups  xmmword ptr [rbp+360h+var_2B8.Length], xmm0
0x180124272  mov     [rbp+360h+var_358], r8
0x180124276  mov     [rbp+360h+var_3D8], rdx
0x18012427a  call    CONNECTED_TRACE_ENTER
0x18012427f  xor     eax, eax
0x180124281  lea     rcx, [rbp+360h+var_290]
0x180124288  mov     [rbp+360h+var_290], eax
0x18012428e  mov     [rbp+360h+var_28C], al
0x180124294  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?LsaSrvTraceLogger@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const LsaSrvTraceLogger,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180124299  mov     eax, cs:dword_18019A2B0
0x18012429f  cmp     eax, 5
0x1801242a2  jbe     short loc_1801242FC
0x1801242a4  mov     rdx, 200000000000h
0x1801242ae  lea     rcx, dword_18019A2B0
0x1801242b5  call    _tlgKeywordOn
0x1801242ba  xor     edx, edx
0x1801242bc  test    al, al
0x1801242be  jz      short loc_1801242FE
0x1801242c0  cmp     [rbp+360h+var_28C], dl
0x1801242c6  jz      short loc_1801242DF
0x1801242c8  lea     rcx, [rbp+360h+var_278]; struct _GUID *
0x1801242cf  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1801242d4  lea     r9, [rbp+360h+var_278]
0x1801242db  test    al, al
0x1801242dd  jz      short loc_1801242E2
0x1801242df  mov     r9, rdx
0x1801242e2  lea     r8, [rbp+360h+var_288]
0x1801242e9  lea     rdx, byte_180180015
0x1801242f0  lea     rcx, dword_18019A2B0
0x1801242f7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801242fc  xor     edx, edx
0x1801242fe  test    r14, r14
0x180124301  jz      loc_180124B8C
0x180124307  mov     rax, [rbp+360h+var_358]
0x18012430b  test    rax, rax
0x18012430e  jz      loc_180124B8C
0x180124314  test    rsi, rsi
0x180124317  jz      loc_180124B8C
0x18012431d  test    rdi, rdi
0x180124320  jz      loc_180124B8C
0x180124326  test    rbx, rbx
0x180124329  jz      loc_180124B8C
0x18012432f  mov     [rdi], edx
0x180124331  mov     rcx, rax; struct _UNICODE_STRING *
0x180124334  mov     [rbx], edx
0x180124336  call    ?LsapInspectString@@YAKPEAU_UNICODE_STRING@@@Z; LsapInspectString(_UNICODE_STRING *)
0x18012433b  test    al, 47h
0x18012433d  jz      short loc_18012434B
0x18012433f  lea     rcx, aLsapinspectstr_1; "LsapInspectString(EncodedLocalPassword)"
0x180124346  jmp     loc_180124B93
0x18012434b  cmp     dword ptr [rsi], 54h ; 'T'
0x18012434e  jnz     loc_1801244F6
0x180124354  lea     r8, [rbp+360h+ClientProcess]; ClientProcess
0x180124358  mov     edx, 1000h; DesiredAccess
0x18012435d  xor     ecx, ecx; Binding
0x18012435f  call    cs:__imp_I_RpcOpenClientProcess
0x180124366  nop     dword ptr [rax+rax+00h]
0x18012436b  xor     edi, edi
0x18012436d  test    eax, eax
0x18012436f  jz      short loc_1801243D3
0x180124371  mov     ecx, eax; Status
0x180124373  call    cs:__imp_I_RpcMapWin32Status
0x18012437a  nop     dword ptr [rax+rax+00h]
0x18012437f  mov     edx, eax
0x180124381  lea     rcx, aIRpcopenclient_1; "I_RpcOpenClientProcess"
0x180124388  call    CONNECTED_TRACE_ERROR
0x18012438d  mov     edi, 0C0000022h
0x180124392  mov     rcx, cs:WPP_GLOBAL_Control
0x180124399  lea     rax, WPP_GLOBAL_Control
0x1801243a0  cmp     rcx, rax
0x1801243a3  jz      loc_180124B9F
0x1801243a9  test    byte ptr [rcx+1Ch], 1
0x1801243ad  jz      loc_180124B9F
0x1801243b3  mov     edx, 26h ; '&'
0x1801243b8  mov     rcx, [rcx+10h]
0x1801243bc  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x1801243c3  mov     r9d, 0C0000022h
0x1801243c9  call    WPP_SF_d
0x1801243ce  jmp     loc_180124B9F
0x1801243d3  mov     rcx, [rbp+360h+ClientProcess]; ProcessHandle
0x1801243d7  lea     r8, [rbp+360h+TokenHandle]; TokenHandle
0x1801243db  mov     edx, 0Eh; DesiredAccess
0x1801243e0  call    cs:__imp_OpenProcessToken
0x1801243e7  nop     dword ptr [rax+rax+00h]
0x1801243ec  test    eax, eax
0x1801243ee  jnz     short loc_180124437
0x1801243f0  call    cs:__imp_GetLastError
0x1801243f7  nop     dword ptr [rax+rax+00h]
0x1801243fc  mov     edx, eax
0x1801243fe  lea     rcx, aOpenprocesstok; "OpenProcessToken"
0x180124405  call    CONNECTED_TRACE_ERROR
0x18012440a  mov     edi, 0C0000022h
0x18012440f  mov     rcx, cs:WPP_GLOBAL_Control
0x180124416  lea     rax, WPP_GLOBAL_Control
0x18012441d  cmp     rcx, rax
0x180124420  jz      loc_180124B9F
0x180124426  test    byte ptr [rcx+1Ch], 1
0x18012442a  jz      loc_180124B9F
0x180124430  mov     edx, 27h ; '''
0x180124435  jmp     short loc_1801243B8
0x180124437  mov     rax, cs:?LsapTcbPrivilege@@3U_LUID@@A; _LUID LsapTcbPrivilege
0x18012443e  lea     r8, [rbp+360h+Result]; Result
0x180124442  mov     rcx, [rbp+360h+TokenHandle]; ClientToken
0x180124446  lea     rdx, [rbp+360h+RequiredPrivileges]; RequiredPrivileges
0x18012444d  mov     qword ptr [rbp+360h+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x180124454  mov     [rbp+360h+RequiredPrivileges.PrivilegeCount], 1
0x18012445e  mov     [rbp+360h+RequiredPrivileges.Control], 1
0x180124468  mov     [rbp+360h+RequiredPrivileges.Privilege.Attributes], edi
0x18012446e  mov     [rbp+360h+Result], dil
0x180124472  call    cs:__imp_NtPrivilegeCheck
0x180124479  nop     dword ptr [rax+rax+00h]
0x18012447e  test    eax, eax
0x180124480  jns     short loc_1801244C0
0x180124482  mov     edx, eax
0x180124484  lea     rcx, aNtprivilegeche; "NtPrivilegeCheck"
0x18012448b  call    CONNECTED_TRACE_ERROR
0x180124490  mov     edi, 0C0000022h
0x180124495  mov     rcx, cs:WPP_GLOBAL_Control
0x18012449c  lea     rax, WPP_GLOBAL_Control
0x1801244a3  cmp     rcx, rax
0x1801244a6  jz      loc_180124B9F
0x1801244ac  test    byte ptr [rcx+1Ch], 1
0x1801244b0  jz      loc_180124B9F
0x1801244b6  mov     edx, 28h ; '('
0x1801244bb  jmp     loc_1801243B8
0x1801244c0  cmp     [rbp+360h+Result], dil
0x1801244c4  jnz     short loc_180124532
0x1801244c6  mov     edi, 0C0000022h
0x1801244cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801244d2  lea     rax, WPP_GLOBAL_Control
0x1801244d9  cmp     rcx, rax
0x1801244dc  jz      loc_180124B9F
0x1801244e2  test    byte ptr [rcx+1Ch], 1
0x1801244e6  jz      loc_180124B9F
0x1801244ec  mov     edx, 29h ; ')'
0x1801244f1  jmp     loc_1801243B8
0x1801244f6  mov     rcx, r15; ClientToken
0x1801244f9  call    ?LsapHasConnectPermission@@YAHPEAX@Z; LsapHasConnectPermission(void *)
0x1801244fe  test    eax, eax
0x180124500  jnz     short loc_180124532
0x180124502  mov     edi, 0C0000022h
0x180124507  mov     rcx, cs:WPP_GLOBAL_Control
0x18012450e  lea     rax, WPP_GLOBAL_Control
0x180124515  cmp     rcx, rax
0x180124518  jz      loc_180124B9F
0x18012451e  test    byte ptr [rcx+1Ch], 1
0x180124522  jz      loc_180124B9F
0x180124528  mov     edx, 2Ah ; '*'
0x18012452d  jmp     loc_1801243B8
0x180124532  lea     r8, [rsp+460h+var_3E8]; struct _LSAP_IDPROV_REG_ENTRY **
0x180124537  mov     edx, 1; int
0x18012453c  mov     rcx, r14; struct _GUID *
0x18012453f  call    ?LsapRefIdProvByGuidEx@@YAJPEAU_GUID@@HPEAPEAU_LSAP_IDPROV_REG_ENTRY@@@Z; LsapRefIdProvByGuidEx(_GUID *,int,_LSAP_IDPROV_REG_ENTRY * *)
0x180124544  mov     edi, eax
0x180124546  xor     eax, eax
0x180124548  test    edi, edi
0x18012454a  jns     short loc_18012455A
0x18012454c  mov     edx, edi
0x18012454e  lea     rcx, aLsaprefidprovb_2; "LsapRefIdProvByGuid"
0x180124555  jmp     loc_180124B9A
0x18012455a  lea     r8, [rbp+360h+Status]; Status
0x18012455e  mov     [rbp+360h+Status], eax
0x180124561  lea     rdx, stru_1801625B0; Uuid2
0x180124568  mov     rcx, r14; Uuid1
0x18012456b  call    cs:__imp_UuidEqual
0x180124572  nop     dword ptr [rax+rax+00h]
0x180124577  xor     r14d, r14d
0x18012457a  test    eax, eax
0x18012457c  jz      short loc_180124586
0x18012457e  mov     r12b, 1
0x180124581  jmp     loc_18012461B
0x180124586  test    byte ptr cs:?LsapNoConnectedUser@@3KA, 3; ulong LsapNoConnectedUser
0x18012458d  jz      short loc_1801245D5
0x18012458f  mov     edi, 0C0000022h
0x180124594  mov     rcx, cs:WPP_GLOBAL_Control
0x18012459b  lea     rax, WPP_GLOBAL_Control
0x1801245a2  cmp     rcx, rax
0x1801245a5  jz      loc_180124BA2
0x1801245ab  test    byte ptr [rcx+1Ch], 1
0x1801245af  jz      loc_180124BA2
0x1801245b5  mov     edx, 2Bh ; '+'
0x1801245ba  mov     r9d, 0C0000022h
0x1801245c0  mov     rcx, [rcx+10h]
0x1801245c4  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x1801245cb  call    WPP_SF_d
0x1801245d0  jmp     loc_180124BA2
0x1801245d5  mov     rcx, [rsp+460h+var_3E8]
0x1801245da  test    byte ptr [rcx+38h], 1
0x1801245de  jnz     short loc_180124613
0x1801245e0  mov     edi, 0C00000BBh
0x1801245e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801245ec  lea     rax, WPP_GLOBAL_Control
0x1801245f3  cmp     rcx, rax
0x1801245f6  jz      loc_180124BA2
0x1801245fc  test    byte ptr [rcx+1Ch], 1
0x180124600  jz      loc_180124BA2
0x180124606  mov     edx, 2Ch ; ','
0x18012460b  mov     r9d, 0C00000BBh
0x180124611  jmp     short loc_1801245C0
0x180124613  mov     r12b, r14b
0x180124616  mov     [rsp+460h+var_3F0], 1
0x18012461b  mov     rcx, [rbp+360h+var_3D8]; struct _LUID *
0x18012461f  lea     rdx, [rbp+360h+var_3C0]; struct _LSAP_PER_SID_INFO **
0x180124623  call    ?LsapLocateSidCacheEntry@@YAJPEAU_LUID@@PEAPEAU_LSAP_PER_SID_INFO@@@Z; LsapLocateSidCacheEntry(_LUID *,_LSAP_PER_SID_INFO * *)
0x180124628  mov     edi, eax
0x18012462a  test    eax, eax
0x18012462c  jns     short loc_18012464C
0x18012462e  mov     edx, eax
0x180124630  lea     rcx, aLsaplocatesidc; "LsapLocateSidCacheEntry"
0x180124637  call    CONNECTED_TRACE_ERROR
0x18012463c  mov     r13, [rbp+360h+var_3C0]
0x180124640  mov     r12, [rbp+360h+var_3D8]
0x180124644  mov     rbx, r14
0x180124647  jmp     loc_180124BA5
0x18012464c  mov     r13, [rbp+360h+var_3C0]
0x180124650  mov     rcx, r13; struct _LSAP_PER_SID_INFO *
0x180124653  call    ?LsapTryStartAccountTransition@@YAJPEAU_LSAP_PER_SID_INFO@@@Z; LsapTryStartAccountTransition(_LSAP_PER_SID_INFO *)
0x180124658  mov     edi, eax
0x18012465a  test    eax, eax
0x18012465c  jns     short loc_18012466E
0x18012465e  mov     edx, eax
0x180124660  lea     rcx, aLsapstartaccou; "LsapStartAccountTransition"
0x180124667  call    CONNECTED_TRACE_WARNING
0x18012466c  jmp     short loc_180124640
0x18012466e  mov     r8d, [rbp+360h+arg_20]; unsigned int
0x180124675  lea     rax, [rbp+360h+var_398]
0x180124679  mov     [rsp+460h+var_438], rax; struct _UNICODE_STRING *
0x18012467e  lea     r9, [rbp+360h+DataBuffer]; unsigned __int8 **
0x180124682  lea     rax, [rbp+360h+var_3C8]
0x180124686  mov     [rsp+460h+var_400], 1
0x18012468b  mov     rdx, rsi; unsigned __int8 *
0x18012468e  mov     [rsp+460h+var_440], rax; unsigned int *
0x180124693  mov     rcx, r15; void *
0x180124696  call    ?LsapGetUserNameAndAuthBuffer@@YAJPEAXPEAEKPEAPEAEPEAKPEAU_UNICODE_STRING@@@Z; LsapGetUserNameAndAuthBuffer(void *,uchar *,ulong,uchar * *,ulong *,_UNICODE_STRING *)
0x18012469b  mov     edi, eax
0x18012469d  test    eax, eax
0x18012469f  jns     short loc_1801246B1
0x1801246a1  lea     rcx, aLsapgetusernam; "LsapGetUserNameAndAuthBuffer"
0x1801246a8  mov     edx, eax
0x1801246aa  call    CONNECTED_TRACE_ERROR
0x1801246af  jmp     short loc_180124640
0x1801246b1  cmp     [rbp+360h+var_398.Buffer], r14
0x1801246b5  jz      loc_180124B59
0x1801246bb  cmp     [rbp+360h+var_398.Length], r14w
0x1801246c0  jz      loc_180124B59
0x1801246c6  mov     rdx, [rbp+360h+var_358]; struct _UNICODE_STRING *
0x1801246ca  lea     r8, [rbp+360h+var_338]; struct _UNICODE_STRING *
  ... truncated ...
```
