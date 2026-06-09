# LsapDisconnectLocalUser(void *,_LUID *,_GUID *,ulong,uchar *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x180125c28`
- end: `0x180126638`
- name: `?LsapDisconnectLocalUser@@YAJPEAXPEAU_LUID@@PEAU_GUID@@KPEAEPEAU_UNICODE_STRING@@4@Z`
- size: `2576`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct _LUID *@<rdx>, struct _GUID *@<r8>, unsigned int@<r9d>, unsigned __int8 *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `52`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18012a8b0`

## callees

- `0x180001fa0`
- `0x180001fe4`
- `0x180003214`
- `0x1800040d0`
- `0x18000c300`
- `0x18000d3b0`
- `0x180011278`
- `0x18005fa30`
- `0x18005faf0`
- `0x18005fecc`
- `0x18006064c`
- `0x180060cb0`
- `0x180061cb8`
- `0x180063c24`
- `0x180074aa8`
- `0x18007e394`
- `0x18007ee64`
- `0x18007f964`
- `0x18007fbd0`
- `0x18007ff6c`
- `0x180081b18`
- `0x180082da0`
- `0x18008dcd8`
- `0x18009a064`
- `0x1800b66ec`
- `0x1800b7430`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800c69bc`
- `0x1800d7dc0`
- `0x1800d7ed8`
- `0x1800d7f9c`
- `0x1800d8060`
- `0x180123828`
- `0x180123d14`
- `0x180125a04`
- `0x180125c28`
- `0x180127070`
- `0x18012716c`
- `0x180127348`
- `0x1801276e4`
- `0x180127a08`
- `0x180127bf4`
- `0x180127eac`
- `0x180128ff0`
- `0x1801296c0`
- `0x180129ae4`
- `0x180129cec`
- `0x180129f18`
- `0x18012cd8c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012647a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012648f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012647a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012648f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801264ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801264ef`
- `ntdll!RtlAcquireResourceExclusive` at `0x18012615c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18012615c`
- `ntdll!RtlReleaseResource` at `0x18012640b`
- `ntdll!RtlReleaseResource` at `0x18012640b`
- `RPCRT4!UuidEqual` at `0x180125e16`
- `RPCRT4!UuidEqual` at `0x180125e16`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180126389`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180126389`
- `SspiCli!SspiLocalFree` at `0x180125ff4`
- `SspiCli!SspiLocalFree` at `0x180126563`
- `SspiCli!SspiLocalFree` at `0x180125ff4`
- `SspiCli!SspiLocalFree` at `0x180126563`
- `cryptngc!NgcDeleteContainerEx` at `0x1801263a2`
- `cryptngc!NgcDeleteContainerEx` at `0x1801263a2`

## string_xrefs

- `0x180125e9f`: `LsapLocateSidCacheEntry`
- `0x1801262e5`: `DeleteConnectedIdentity`
- `0x1801260b4`: `LsapCreateCredKeyFromPassword`
- `0x1801261b5`: `LsapGetUserHandleBySamUserSid`

## pseudocode

```c
__int64 __fastcall LsapDisconnectLocalUser(
        void *a1,
        struct _LUID *a2,
        struct _GUID *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        struct _UNICODE_STRING *a6,
        struct _UNICODE_STRING *a7)
{
  PSID v9; // r15
  const char *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  signed int v14; // ebx
  unsigned __int8 v15; // si
  int v16; // eax
  int started; // eax
  int v18; // eax
  int UserNameAndAuthBuffer; // eax
  _BYTE *v20; // r14
  unsigned int v21; // eax
  _BYTE *v22; // rdi
  int v23; // eax
  __int64 v24; // rdx
  _BYTE *v25; // rax
  __int64 v26; // rdx
  const char *v27; // rcx
  struct _LSAP_PER_SID_INFO *v28; // rdi
  int IsSameUser; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int inited; // eax
  struct _RTL_BALANCED_NODE *v34; // r12
  int QualifiedIdentityName; // eax
  const char *v36; // rcx
  int v37; // edi
  struct _RTL_BALANCED_NODE *v38; // rax
  struct _LSAP_PER_SID_INFO *v39; // rsi
  int v40; // eax
  int v41; // eax
  int v42; // ebx
  __int64 v43; // r8
  __int64 v44; // r9
  void *v45; // rdx
  struct _RTL_BALANCED_NODE *v46; // rax
  __int64 v47; // rcx
  unsigned int *v48; // rdx
  __int64 v49; // rax
  struct _RTL_BALANCED_NODE *v50; // rdi
  PWSTR Buffer; // rax
  __int64 Length; // rcx
  __int64 v53; // rax
  _BYTE *v54; // rdx
  char v56; // [rsp+30h] [rbp-D0h]
  char v57; // [rsp+31h] [rbp-CFh]
  unsigned __int8 v58; // [rsp+32h] [rbp-CEh] BYREF
  char v59; // [rsp+33h] [rbp-CDh]
  unsigned int v60; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE *v61; // [rsp+38h] [rbp-C8h]
  struct _LSAP_PER_SID_INFO *v62; // [rsp+40h] [rbp-C0h] BYREF
  void *v63; // [rsp+48h] [rbp-B8h] BYREF
  PVOID DataBuffer; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTL_BALANCED_NODE *v65; // [rsp+58h] [rbp-A8h] BYREF
  struct _RTL_BALANCED_NODE *v66; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v68; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v69; // [rsp+78h] [rbp-88h] BYREF
  RPC_STATUS Status; // [rsp+88h] [rbp-78h] BYREF
  struct _LUID *v71; // [rsp+90h] [rbp-70h]
  int *v72; // [rsp+98h] [rbp-68h] BYREF
  HANDLE TokenHandle; // [rsp+A0h] [rbp-60h] BYREF
  PSID Sid; // [rsp+A8h] [rbp-58h] BYREF
  LPWSTR StringSid; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v76; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING String2; // [rsp+C8h] [rbp-38h] BYREF
  struct _LUID v78; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING *v79; // [rsp+E0h] [rbp-20h]
  struct _UNICODE_STRING v80; // [rsp+E8h] [rbp-18h] BYREF
  struct _GUID *v81; // [rsp+F8h] [rbp-8h]
  _BYTE v82[16]; // [rsp+100h] [rbp+0h] BYREF
  struct _USER_INTERNAL6_INFORMATION *v83; // [rsp+110h] [rbp+10h]
  char v84[16]; // [rsp+118h] [rbp+18h] BYREF
  char v85[16]; // [rsp+128h] [rbp+28h] BYREF
  char v86[24]; // [rsp+138h] [rbp+38h] BYREF
  int v87; // [rsp+150h] [rbp+50h]
  int v88; // [rsp+160h] [rbp+60h] BYREF
  char v89; // [rsp+164h] [rbp+64h]
  struct _GUID v90; // [rsp+178h] [rbp+78h] BYREF

  v81 = a3;
  v71 = a2;
  Sid = 0;
  TokenHandle = 0;
  v9 = 0;
  hObject = 0;
  v78 = 0;
  v66 = 0;
  v56 = 0;
  v68 = 0;
  v65 = 0;
  v61 = 0;
  DataBuffer = 0;
  v60 = 0;
  v58 = 0;
  v57 = 0;
  v79 = a7;
  String2 = 0;
  v76 = 0;
  v80 = 0;
  v69 = 0;
  memset_0(v82, 0, 0x58u);
  v63 = 0;
  StringSid = 0;
  v62 = 0;
  v72 = 0;
  CONNECTED_TRACE_ENTER("LsapDisconnectLocalUser");
  v88 = 0;
  v89 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const LsaSrvTraceLogger,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v88);
  if ( (unsigned int)dword_18019A2B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18019A2B0, 0x200000000000LL) )
  {
    if ( v89 )
      _tlgGuidIsZero(&v90);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18019A2B0,
      (__int64)byte_18017FFB9);
  }
  if ( !a5 || !a3 || !a6 || !a7 )
  {
    v11 = "A required parameter is NULL";
    goto LABEL_95;
  }
  if ( (LsapInspectString(a6) & 0x47) != 0 )
  {
    v11 = "LsapInspectString(LocalUserName)";
LABEL_95:
    v12 = 3221225485LL;
    goto LABEL_96;
  }
  if ( (LsapInspectString(a7) & 0x47) != 0 )
  {
    v11 = "LsapInspectString(EncodedLocalPassword)";
    goto LABEL_95;
  }
  if ( !(unsigned int)LsapHasConnectPermission(a1) )
  {
    v12 = 3221225506LL;
    v11 = "LsapHasConnectPermission";
LABEL_96:
    v14 = v12;
    goto LABEL_97;
  }
  v13 = LsapRefIdProvByGuidEx(a3, 1, (struct _LSAP_IDPROV_REG_ENTRY **)&v66);
  v14 = v13;
  if ( v13 < 0 )
  {
    v12 = (unsigned int)v13;
    v11 = "LsapRefIdProvByGuid";
LABEL_97:
    CONNECTED_TRACE_ERROR(v11, v12);
    goto LABEL_98;
  }
  Status = 0;
  if ( UuidEqual(a3, (UUID *)&stru_1801625B0, &Status) )
  {
    v59 = 1;
    v15 = 0;
  }
  else
  {
    if ( ((__int64)v66[2].Right & 1) == 0 )
    {
      v14 = -1073741637;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids, 3221225659LL);
      goto LABEL_98;
    }
    v59 = 0;
    v15 = 1;
  }
  v16 = LsapLocateSidCacheEntry(v71, &v62);
  v14 = v16;
  if ( v16 < 0 )
  {
    v12 = (unsigned int)v16;
    v11 = "LsapLocateSidCacheEntry";
    goto LABEL_97;
  }
  started = LsapTryStartAccountTransition(v62);
  v14 = started;
  if ( started < 0 )
  {
    CONNECTED_TRACE_WARNING("LsapStartAccountTransition", (unsigned int)started);
LABEL_98:
    v20 = v61;
LABEL_99:
    if ( (v82[8] & 1) != 0 )
      LsapRollbackFailedDisconnect(v63, v9, (struct _DISCONNECT_OPERATION_SAM_RECOVERY_INFO *)v82);
LABEL_101:
    v39 = v62;
    goto LABEL_102;
  }
  v57 = 1;
  v18 = LsapDuplicateString(&v76, a6);
  v14 = v18;
  if ( v18 < 0 )
  {
    v12 = (unsigned int)v18;
    v11 = "LsapDuplicateString";
    goto LABEL_97;
  }
  UserNameAndAuthBuffer = LsapGetUserNameAndAuthBuffer(a1, a5, a4, (unsigned __int8 **)&DataBuffer, &v60, &String2);
  v14 = UserNameAndAuthBuffer;
  if ( UserNameAndAuthBuffer < 0 )
  {
    CONNECTED_TRACE_ERROR("LsapGetUserNameAndAuthBuffer", (unsigned int)UserNameAndAuthBuffer);
    v20 = DataBuffer;
    goto LABEL_99;
  }
  if ( String2.Length > 0x200u )
  {
    v14 = -1073741811;
LABEL_36:
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        WPP_da3d202165313132ccfab67d2692d0fe_Traceguids,
        (unsigned int)v14);
    v20 = DataBuffer;
    v56 = 0;
    v57 = 1;
    if ( v14 >= 0 )
      goto LABEL_101;
    goto LABEL_99;
  }
  v21 = LsapInspectString(&String2) & 0x10;
  v14 = v21 != 0 ? 0xC000000D : 0;
  if ( v21 )
    goto LABEL_36;
  v22 = DataBuffer;
  v23 = LsapLogonUserWithCred(a1, (unsigned __int8 *)DataBuffer, v60, &TokenHandle, &v78);
  v24 = v60;
  v14 = v23;
  v25 = v22;
  if ( v60 )
  {
    do
    {
      *v25++ = 0;
      --v24;
    }
    while ( v24 );
  }
  SspiLocalFree(v22);
  v20 = 0;
  if ( v14 < 0 )
  {
    v26 = (unsigned int)v14;
    v27 = "LsapLogonUserWithCred";
LABEL_49:
    CONNECTED_TRACE_ERROR(v27, v26);
    goto LABEL_99;
  }
  v28 = v62;
  IsSameUser = LsapIsSameUser(TokenHandle, *((PSID *)v62 + 3), &v58);
  v14 = IsSameUser;
  if ( IsSameUser < 0 )
  {
    v26 = (unsigned int)IsSameUser;
    v27 = "LsapIsSameUser";
    goto LABEL_49;
  }
  if ( !v58 )
  {
    v26 = 3221225506LL;
    v27 = "Disconnect requires same user";
    v14 = -1073741790;
    goto LABEL_49;
  }
  v30 = LsapDecryptPassword(a1, v79, &v69);
  v14 = v30;
  if ( v30 < 0 )
  {
    v26 = (unsigned int)v30;
    v27 = "LsapDecryptPassword";
    goto LABEL_49;
  }
  v31 = LsapValidateNewLocalAccountPassword(a1, &v76, &v69);
  v14 = v31;
  if ( v31 < 0 )
  {
    v26 = (unsigned int)v31;
    v27 = "LsapValidateNewLocalAccountPassword";
    goto LABEL_49;
  }
  v32 = LsapCreateCredKeyFromPassword(&v69, (struct _CREDENTIAL_KEY **)&v65);
  v14 = v32;
  if ( v32 < 0 )
  {
    v26 = (unsigned int)v32;
    v27 = "LsapCreateCredKeyFromPassword";
    goto LABEL_49;
  }
  inited = LsapLazyInitSamConnection();
  v14 = inited;
  if ( inited < 0 )
  {
    v26 = (unsigned int)inited;
    v27 = "LsapLazyInitSamConnection";
    goto LABEL_49;
  }
  v34 = v66;
  QualifiedIdentityName = LsapMakeQualifiedIdentityName(&String2, (struct _UNICODE_STRING *)&v66[1].16, &v80);
  v14 = QualifiedIdentityName;
  if ( QualifiedIdentityName < 0 )
  {
    v36 = "LsapMakeQualifiedIdentityName";
LABEL_60:
    CONNECTED_TRACE_ERROR(v36, (unsigned int)QualifiedIdentityName);
    goto LABEL_99;
  }
  if ( v15 )
  {
    QualifiedIdentityName = LsapFindConnectedUserByInternetName(&v80, 0, &Sid);
    v14 = QualifiedIdentityName;
    if ( QualifiedIdentityName < 0 )
    {
      v36 = "LsapFindConnectedUserByInternetName";
      goto LABEL_60;
    }
    v9 = Sid;
  }
  else
  {
    v9 = (PSID)*((_QWORD *)v28 + 3);
  }
  QualifiedIdentityName = LsapValidateNewLocalAccountName(&v76, v9);
  v14 = QualifiedIdentityName;
  if ( QualifiedIdentityName < 0 )
  {
    v36 = "LsapValidateNewLocalAccountName";
    goto LABEL_60;
  }
  if ( v15 )
  {
    RtlAcquireResourceExclusive(&g_ConnectedAccountStoreLock, 1u);
    v56 = 1;
    QualifiedIdentityName = LsapSnapshotSamConnectedAccountAttributes(
                              &String2,
                              &v80,
                              v81,
                              &v63,
                              (struct _DISCONNECT_OPERATION_SAM_RECOVERY_INFO *)v82);
    v14 = QualifiedIdentityName;
    if ( QualifiedIdentityName < 0 )
    {
      v36 = "LsapSnapshotSamConnectedAccountAttributes";
      goto LABEL_60;
    }
  }
  else
  {
    QualifiedIdentityName = LsapGetUserHandleBySamUserSid(
                              v9,
                              &v63,
                              (struct _DISCONNECT_OPERATION_SAM_RECOVERY_INFO *)v82);
    v14 = QualifiedIdentityName;
    if ( QualifiedIdentityName < 0 )
    {
      v36 = "LsapGetUserHandleBySamUserSid";
      goto LABEL_60;
    }
  }
  QualifiedIdentityName = LsapSamExtQueryInformationUser(v63, 16, &v72);
  v14 = QualifiedIdentityName;
  if ( QualifiedIdentityName < 0 )
  {
    v36 = "LsapSamExtQueryInformationUser";
    goto LABEL_60;
  }
  v87 = *v72;
  v14 = ((__int64 (__fastcall *)(struct _RTL_BALANCED_NODE *, struct _LUID *, _QWORD, unsigned int **))v34[10].ParentValue)(
          v34,
          &v78,
          0,
          &v68);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        WPP_da3d202165313132ccfab67d2692d0fe_Traceguids,
        (unsigned int)v14);
    goto LABEL_99;
  }
  v37 = v15;
  QualifiedIdentityName = LsapDisconnectAccountInSam(
                            v63,
                            &v76,
                            &v69,
                            v9,
                            v15,
                            (struct _DISCONNECT_OPERATION_SAM_RECOVERY_INFO *)v82);
  v14 = QualifiedIdentityName;
  if ( QualifiedIdentityName < 0 )
  {
    v36 = "LsapDisconnectAccountInSam";
    goto LABEL_60;
  }
  QualifiedIdentityName = LsapLogonUserWithPassword(&v76, &v69, &hObject);
  v14 = QualifiedIdentityName;
  if ( QualifiedIdentityName < 0 )
  {
    v36 = "LsapLogonUserWithPassword";
    goto LABEL_60;
  }
  v38 = v34[10].Children[0];
  v39 = v62;
  if ( v38 )
  {
    v40 = ((__int64 (__fastcall *)(struct _RTL_BALANCED_NODE *, void *, HANDLE, struct _LUID *, _QWORD))v38)(
            v34,
            a1,
            hObject,
            v71,
            *((_QWORD *)v62 + 3));
    if ( v40 < 0 )
      CONNECTED_TRACE_ERROR("DeleteConnectedIdentity", (unsigned int)v40);
  }
  v41 = (*((__int64 (__fastcall **)(HANDLE, unsigned int *, struct _RTL_BALANCED_NODE *, __int64))LsapDpapiIfTable + 5))(
          hObject,
          v68,
          v65,
          1);
  v42 = v41;
  if ( v41 < 0 )
    CONNECTED_TRACE_ERROR("LsaIfNotifyCredentialKeyChange", (unsigned int)v41);
  LsapSetSidCacheAuthorityName(v39, 0);
  if ( v42 >= 0 )
  {
    LsapInvalidateDsNames(v71, 0, v37);
    LsapSetSidCacheCredKey(v39, (struct _CREDENTIAL_KEY *)v65);
    LsapClearLogonStatistics(v63);
    LsapNotifyNewPassword(v9, &v69, v43, v44);
    if ( v59 )
    {
      if ( ConvertSidToStringSidW(v9, &StringSid) )
        NgcDeleteContainerEx(StringSid, 1);
    }
    else
    {
      LsapTransitionNGCToPasswordStuffer(v9, &v69);
    }
  }
  v14 = 0;
LABEL_102:
  if ( v72 )
    LsapSamExtFreeUserInfoBuffer(v72, 16);
  if ( v56 )
    RtlReleaseResource(&g_ConnectedAccountStoreLock);
  LsapFreeString(v84);
  LsapFreeString(v85);
  LsapFreeString(v86);
  if ( v83 )
    LsapSamExtFreeUserInternal6Information(v83);
  LsapFreeString(&v76);
  v46 = v65;
  if ( v65 )
  {
    v47 = LODWORD(v65->Children[0]);
    if ( LODWORD(v65->Children[0]) )
    {
      do
      {
        LOBYTE(v46->Children[0]) = 0;
        v46 = (struct _RTL_BALANCED_NODE *)((char *)v46 + 1);
        --v47;
      }
      while ( v47 );
    }
    LsapSubProv_FreeRoutine(v65, v45);
  }
  if ( hObject )
    CloseHandle(hObject);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Sid )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)Sid, v45);
  v48 = v68;
  if ( v68 )
  {
    v49 = *v68;
    if ( *v68 )
    {
      do
      {
        *(_BYTE *)v48 = 0;
        v48 = (unsigned int *)((char *)v48 + 1);
        --v49;
      }
      while ( v49 );
    }
    v50 = v66;
    ((void (__fastcall *)(struct _RTL_BALANCED_NODE *))v66[4].Children[0])(v66);
  }
  else
  {
    v50 = v66;
  }
  if ( StringSid )
    LocalFree(StringSid);
  LsapSecureFreeString(&v69);
  LsapFreeString(&String2);
  LsapFreeString(&v80);
  if ( v79 )
  {
    if ( v79->Length )
    {
      Buffer = v79->Buffer;
      if ( Buffer )
      {
        Length = v79->Length;
        if ( v79->Length )
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
  if ( v20 )
  {
    v53 = v60;
    v54 = v20;
    if ( v60 )
    {
      do
      {
        *v54++ = 0;
        --v53;
      }
      while ( v53 );
    }
    SspiLocalFree(v20);
  }
  if ( v63 )
    LsapSamExtCloseHandle(&v63);
  LsapDerefIdProv(v50);
  if ( v57 )
    LsapCompleteAccountTransition(v39);
  if ( v39 )
    LsapReleaseSidCacheEntry(v39);
  v88 = 2;
  if ( (unsigned int)dword_18019A2B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18019A2B0, 0x200000000000LL) )
  {
    v60 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18019A2B0,
      (__int64)&word_18017FF86);
  }
  CONNECTED_TRACE_EXIT_EX(1, "LsapDisconnectLocalUser", (unsigned int)v14);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const LsaSrvTraceLogger,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const LsaSrvTraceLogger,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v88);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180125c28  push    rbp
0x180125c2a  push    rbx
0x180125c2b  push    rsi
0x180125c2c  push    rdi
0x180125c2d  push    r12
0x180125c2f  push    r13
0x180125c31  push    r14
0x180125c33  push    r15
0x180125c35  lea     rbp, [rsp-98h]
0x180125c3d  sub     rsp, 198h
0x180125c44  mov     rax, cs:__security_cookie
0x180125c4b  xor     rax, rsp
0x180125c4e  mov     [rbp+0D0h+var_48], rax
0x180125c55  mov     rbx, [rbp+0D0h+arg_30]
0x180125c5c  mov     r13, rcx
0x180125c5f  mov     r14, [rbp+0D0h+arg_20]
0x180125c66  xor     ecx, ecx
0x180125c68  mov     rdi, [rbp+0D0h+arg_28]
0x180125c6f  xorps   xmm0, xmm0
0x180125c72  xorps   xmm1, xmm1
0x180125c75  mov     [rbp+0D0h+var_D8], r8
0x180125c79  mov     rsi, r8
0x180125c7c  mov     [rbp+0D0h+var_140], rdx
0x180125c80  lea     r8d, [rcx+58h]; Size
0x180125c84  mov     [rbp+0D0h+Sid], rcx
0x180125c88  mov     [rbp+0D0h+TokenHandle], rcx
0x180125c8c  mov     r15d, ecx
0x180125c8f  mov     [rsp+1D0h+hObject], rcx
0x180125c94  xor     edx, edx; Val
0x180125c96  mov     qword ptr [rbp+0D0h+var_F8.LowPart], rcx
0x180125c9a  mov     r12d, r9d
0x180125c9d  mov     [rsp+1D0h+var_170], rcx
0x180125ca2  mov     [rsp+1D0h+var_1A0], cl
0x180125ca6  mov     [rsp+1D0h+var_160], rcx
0x180125cab  mov     [rsp+1D0h+var_178], rcx
0x180125cb0  mov     [rsp+1D0h+var_198], rcx
0x180125cb5  mov     [rsp+1D0h+DataBuffer], rcx
0x180125cba  mov     [rsp+1D0h+var_19C], ecx
0x180125cbe  mov     [rsp+1D0h+var_19E], cl
0x180125cc2  mov     [rsp+1D0h+var_19F], cl
0x180125cc6  lea     rcx, [rbp+0D0h+var_D0]; void *
0x180125cca  mov     [rbp+0D0h+var_F0], rbx
0x180125cce  movups  xmmword ptr [rbp+0D0h+String2.Length], xmm0
0x180125cd2  movups  xmmword ptr [rbp+0D0h+var_118.Length], xmm1
0x180125cd6  movups  xmmword ptr [rbp+0D0h+var_E8.Length], xmm0
0x180125cda  movups  xmmword ptr [rsp+1D0h+var_158.Length], xmm1
0x180125cdf  call    memset_0
0x180125ce4  xor     eax, eax
0x180125ce6  lea     rcx, aLsapdisconnect; "LsapDisconnectLocalUser"
0x180125ced  mov     [rsp+1D0h+var_188], rax
0x180125cf2  mov     [rbp+0D0h+StringSid], rax
0x180125cf6  mov     [rsp+1D0h+var_190], rax
0x180125cfb  mov     [rbp+0D0h+var_138], rax
0x180125cff  call    CONNECTED_TRACE_ENTER
0x180125d04  lea     rcx, [rbp+0D0h+var_70]
0x180125d08  mov     [rbp+0D0h+var_70], r15d
0x180125d0c  mov     [rbp+0D0h+var_6C], r15b
0x180125d10  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?LsaSrvTraceLogger@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const LsaSrvTraceLogger,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180125d15  mov     eax, cs:dword_18019A2B0
0x180125d1b  cmp     eax, 5
0x180125d1e  jbe     short loc_180125D6D
0x180125d20  mov     rdx, 200000000000h
0x180125d2a  lea     rcx, dword_18019A2B0
0x180125d31  call    _tlgKeywordOn
0x180125d36  test    al, al
0x180125d38  jz      short loc_180125D6D
0x180125d3a  cmp     [rbp+0D0h+var_6C], r15b
0x180125d3e  jz      short loc_180125D53
0x180125d40  lea     rcx, [rbp+0D0h+var_58]; struct _GUID *
0x180125d44  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180125d49  test    al, al
0x180125d4b  jnz     short loc_180125D53
0x180125d4d  lea     r9, [rbp+0D0h+var_58]
0x180125d51  jmp     short loc_180125D56
0x180125d53  xor     r9d, r9d
0x180125d56  lea     r8, [rbp+0D0h+var_68]
0x180125d5a  lea     rdx, byte_18017FFB9
0x180125d61  lea     rcx, dword_18019A2B0
0x180125d68  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180125d6d  test    r14, r14
0x180125d70  jz      loc_1801263B3
0x180125d76  test    rsi, rsi
0x180125d79  jz      loc_1801263B3
0x180125d7f  test    rdi, rdi
0x180125d82  jz      loc_1801263B3
0x180125d88  test    rbx, rbx
0x180125d8b  jz      loc_1801263B3
0x180125d91  mov     rcx, rdi; struct _UNICODE_STRING *
0x180125d94  call    ?LsapInspectString@@YAKPEAU_UNICODE_STRING@@@Z; LsapInspectString(_UNICODE_STRING *)
0x180125d99  test    al, 47h
0x180125d9b  jz      short loc_180125DA9
0x180125d9d  lea     rcx, aLsapinspectstr; "LsapInspectString(LocalUserName)"
0x180125da4  jmp     loc_1801263BA
0x180125da9  mov     rcx, rbx; struct _UNICODE_STRING *
0x180125dac  call    ?LsapInspectString@@YAKPEAU_UNICODE_STRING@@@Z; LsapInspectString(_UNICODE_STRING *)
0x180125db1  test    al, 47h
0x180125db3  jz      short loc_180125DC1
0x180125db5  lea     rcx, aLsapinspectstr_1; "LsapInspectString(EncodedLocalPassword)"
0x180125dbc  jmp     loc_1801263BA
0x180125dc1  mov     rcx, r13; ClientToken
0x180125dc4  call    ?LsapHasConnectPermission@@YAHPEAX@Z; LsapHasConnectPermission(void *)
0x180125dc9  test    eax, eax
0x180125dcb  jnz     short loc_180125DDE
0x180125dcd  mov     edx, 0C0000022h
0x180125dd2  lea     rcx, aLsaphasconnect; "LsapHasConnectPermission"
0x180125dd9  jmp     loc_1801263BF
0x180125dde  lea     r8, [rsp+1D0h+var_170]; struct _LSAP_IDPROV_REG_ENTRY **
0x180125de3  mov     edx, 1; int
0x180125de8  mov     rcx, rsi; struct _GUID *
0x180125deb  call    ?LsapRefIdProvByGuidEx@@YAJPEAU_GUID@@HPEAPEAU_LSAP_IDPROV_REG_ENTRY@@@Z; LsapRefIdProvByGuidEx(_GUID *,int,_LSAP_IDPROV_REG_ENTRY * *)
0x180125df0  mov     ebx, eax
0x180125df2  test    eax, eax
0x180125df4  jns     short loc_180125E04
0x180125df6  mov     edx, eax
0x180125df8  lea     rcx, aLsaprefidprovb_2; "LsapRefIdProvByGuid"
0x180125dff  jmp     loc_1801263C1
0x180125e04  lea     r8, [rbp+0D0h+Status]; Status
0x180125e08  mov     [rbp+0D0h+Status], r15d
0x180125e0c  lea     rdx, stru_1801625B0; Uuid2
0x180125e13  mov     rcx, rsi; Uuid1
0x180125e16  call    cs:__imp_UuidEqual
0x180125e1d  nop     dword ptr [rax+rax+00h]
0x180125e22  test    eax, eax
0x180125e24  jz      short loc_180125E30
0x180125e26  mov     [rsp+1D0h+var_19D], 1
0x180125e2b  xor     sil, sil
0x180125e2e  jmp     short loc_180125E89
0x180125e30  mov     rax, [rsp+1D0h+var_170]
0x180125e35  test    byte ptr [rax+38h], 1
0x180125e39  jnz     short loc_180125E81
0x180125e3b  mov     ebx, 0C00000BBh
0x180125e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180125e47  lea     rax, WPP_GLOBAL_Control
0x180125e4e  cmp     rcx, rax
0x180125e51  jz      loc_1801263C6
0x180125e57  test    byte ptr [rcx+1Ch], 1
0x180125e5b  jz      loc_1801263C6
0x180125e61  mov     rcx, [rcx+10h]
0x180125e65  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x180125e6c  mov     edx, 3Fh ; '?'
0x180125e71  mov     r9d, 0C00000BBh
0x180125e77  call    WPP_SF_d
0x180125e7c  jmp     loc_1801263C6
0x180125e81  mov     [rsp+1D0h+var_19D], r15b
0x180125e86  mov     sil, 1
0x180125e89  mov     rcx, [rbp+0D0h+var_140]; struct _LUID *
0x180125e8d  lea     rdx, [rsp+1D0h+var_190]; struct _LSAP_PER_SID_INFO **
0x180125e92  call    ?LsapLocateSidCacheEntry@@YAJPEAU_LUID@@PEAPEAU_LSAP_PER_SID_INFO@@@Z; LsapLocateSidCacheEntry(_LUID *,_LSAP_PER_SID_INFO * *)
0x180125e97  mov     ebx, eax
0x180125e99  test    eax, eax
0x180125e9b  jns     short loc_180125EAB
0x180125e9d  mov     edx, eax
0x180125e9f  lea     rcx, aLsaplocatesidc; "LsapLocateSidCacheEntry"
0x180125ea6  jmp     loc_1801263C1
0x180125eab  mov     rcx, [rsp+1D0h+var_190]; struct _LSAP_PER_SID_INFO *
0x180125eb0  call    ?LsapTryStartAccountTransition@@YAJPEAU_LSAP_PER_SID_INFO@@@Z; LsapTryStartAccountTransition(_LSAP_PER_SID_INFO *)
0x180125eb5  mov     ebx, eax
0x180125eb7  test    eax, eax
0x180125eb9  jns     short loc_180125ECE
0x180125ebb  mov     edx, eax
0x180125ebd  lea     rcx, aLsapstartaccou; "LsapStartAccountTransition"
0x180125ec4  call    CONNECTED_TRACE_WARNING
0x180125ec9  jmp     loc_1801263C6
0x180125ece  mov     rdx, rdi
0x180125ed1  mov     [rsp+1D0h+var_19F], 1
0x180125ed6  lea     rcx, [rbp+0D0h+var_118]
0x180125eda  call    LsapDuplicateString
0x180125edf  mov     ebx, eax
0x180125ee1  test    eax, eax
0x180125ee3  jns     short loc_180125EF3
0x180125ee5  mov     edx, eax
0x180125ee7  lea     rcx, aLsapduplicates_2; "LsapDuplicateString"
0x180125eee  jmp     loc_1801263C1
0x180125ef3  lea     rax, [rbp+0D0h+String2]
0x180125ef7  mov     r8d, r12d; unsigned int
0x180125efa  mov     [rsp+1D0h+var_1A8], rax; struct _UNICODE_STRING *
0x180125eff  lea     r9, [rsp+1D0h+DataBuffer]; unsigned __int8 **
0x180125f04  lea     rax, [rsp+1D0h+var_19C]
0x180125f09  mov     rdx, r14; unsigned __int8 *
0x180125f0c  mov     rcx, r13; void *
0x180125f0f  mov     [rsp+1D0h+var_1B0], rax; unsigned int *
0x180125f14  call    ?LsapGetUserNameAndAuthBuffer@@YAJPEAXPEAEKPEAPEAEPEAKPEAU_UNICODE_STRING@@@Z; LsapGetUserNameAndAuthBuffer(void *,uchar *,ulong,uchar * *,ulong *,_UNICODE_STRING *)
0x180125f19  xor     r12d, r12d
0x180125f1c  mov     ebx, eax
0x180125f1e  test    eax, eax
0x180125f20  jns     short loc_180125F3A
0x180125f22  mov     edx, eax
0x180125f24  lea     rcx, aLsapgetusernam; "LsapGetUserNameAndAuthBuffer"
0x180125f2b  call    CONNECTED_TRACE_ERROR
0x180125f30  mov     r14, [rsp+1D0h+DataBuffer]
0x180125f35  jmp     loc_1801263CE
0x180125f3a  mov     eax, 200h
0x180125f3f  cmp     [rbp+0D0h+String2.Length], ax
0x180125f43  jbe     short loc_180125F4C
0x180125f45  mov     ebx, 0C000000Dh
0x180125f4a  jmp     short loc_180125F68
0x180125f4c  lea     rcx, [rbp+0D0h+String2]; struct _UNICODE_STRING *
0x180125f50  call    ?LsapInspectString@@YAKPEAU_UNICODE_STRING@@@Z; LsapInspectString(_UNICODE_STRING *)
0x180125f55  and     eax, 10h
0x180125f58  mov     ecx, eax
0x180125f5a  neg     ecx
0x180125f5c  sbb     ebx, ebx
0x180125f5e  and     ebx, 0C000000Dh
0x180125f64  test    eax, eax
0x180125f66  jz      short loc_180125FB5
0x180125f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180125f6f  lea     rax, WPP_GLOBAL_Control
0x180125f76  cmp     rcx, rax
0x180125f79  jz      short loc_180125F99
0x180125f7b  test    byte ptr [rcx+1Ch], 1
0x180125f7f  jz      short loc_180125F99
0x180125f81  mov     rcx, [rcx+10h]
0x180125f85  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x180125f8c  mov     edx, 40h ; '@'
0x180125f91  mov     r9d, ebx
0x180125f94  call    WPP_SF_d
0x180125f99  mov     r14, [rsp+1D0h+DataBuffer]
0x180125f9e  mov     [rsp+1D0h+var_1A0], r12b
0x180125fa3  mov     [rsp+1D0h+var_19F], 1
0x180125fa8  test    ebx, ebx
0x180125faa  js      loc_1801263CE
0x180125fb0  jmp     loc_1801263E5
0x180125fb5  mov     rdi, [rsp+1D0h+DataBuffer]
0x180125fba  lea     rax, [rbp+0D0h+var_F8]
0x180125fbe  mov     r8d, [rsp+1D0h+var_19C]; unsigned int
0x180125fc3  lea     r9, [rbp+0D0h+TokenHandle]; void **
0x180125fc7  mov     rdx, rdi; unsigned __int8 *
0x180125fca  mov     [rsp+1D0h+var_1B0], rax; struct _LUID *
0x180125fcf  mov     rcx, r13; void *
0x180125fd2  call    ?LsapLogonUserWithCred@@YAJPEAXPEAEKPEAPEAXPEAU_LUID@@@Z; LsapLogonUserWithCred(void *,uchar *,ulong,void * *,_LUID *)
0x180125fd7  mov     edx, [rsp+1D0h+var_19C]
0x180125fdb  mov     ebx, eax
0x180125fdd  mov     rax, rdi
0x180125fe0  test    rdx, rdx
0x180125fe3  jz      short loc_180125FF1
0x180125fe5  mov     [rax], r12b
0x180125fe8  inc     rax
0x180125feb  sub     rdx, 1
0x180125fef  jnz     short loc_180125FE5
0x180125ff1  mov     rcx, rdi; DataBuffer
0x180125ff4  call    cs:__imp_SspiLocalFree
0x180125ffb  nop     dword ptr [rax+rax+00h]
0x180126000  mov     r14, r12
0x180126003  test    ebx, ebx
0x180126005  jns     short loc_180126012
0x180126007  mov     edx, ebx
0x180126009  lea     rcx, aLsaplogonuserw; "LsapLogonUserWithCred"
0x180126010  jmp     short loc_18012604F
0x180126012  mov     rdi, [rsp+1D0h+var_190]
0x180126017  lea     r8, [rsp+1D0h+var_19E]; unsigned __int8 *
0x18012601c  mov     rcx, [rbp+0D0h+TokenHandle]; TokenHandle
0x180126020  mov     rdx, [rdi+18h]; Sid1
0x180126024  call    ?LsapIsSameUser@@YAJPEAX0PEAE@Z; LsapIsSameUser(void *,void *,uchar *)
0x180126029  mov     ebx, eax
0x18012602b  test    eax, eax
0x18012602d  jns     short loc_18012603A
0x18012602f  mov     edx, eax
0x180126031  lea     rcx, aLsapissameuser; "LsapIsSameUser"
0x180126038  jmp     short loc_18012604F
0x18012603a  cmp     [rsp+1D0h+var_19E], r12b
0x18012603f  jnz     short loc_180126059
0x180126041  mov     edx, 0C0000022h
0x180126046  lea     rcx, aDisconnectRequ; "Disconnect requires same user"
0x18012604d  mov     ebx, edx
0x18012604f  call    CONNECTED_TRACE_ERROR
0x180126054  jmp     loc_1801263CE
0x180126059  mov     rdx, [rbp+0D0h+var_F0]; struct _UNICODE_STRING *
0x18012605d  lea     r8, [rsp+1D0h+var_158]; struct _UNICODE_STRING *
0x180126062  mov     rcx, r13; void *
0x180126065  call    ?LsapDecryptPassword@@YAJPEAXPEAU_UNICODE_STRING@@1@Z; LsapDecryptPassword(void *,_UNICODE_STRING *,_UNICODE_STRING *)
0x18012606a  mov     ebx, eax
0x18012606c  test    eax, eax
0x18012606e  jns     short loc_18012607B
0x180126070  mov     edx, eax
0x180126072  lea     rcx, aLsapdecryptpas; "LsapDecryptPassword"
0x180126079  jmp     short loc_18012604F
0x18012607b  lea     r8, [rsp+1D0h+var_158]; struct _UNICODE_STRING *
0x180126080  mov     rcx, r13; void *
0x180126083  lea     rdx, [rbp+0D0h+var_118]; struct _UNICODE_STRING *
0x180126087  call    ?LsapValidateNewLocalAccountPassword@@YAJPEAXPEAU_UNICODE_STRING@@1@Z; LsapValidateNewLocalAccountPassword(void *,_UNICODE_STRING *,_UNICODE_STRING *)
0x18012608c  mov     ebx, eax
0x18012608e  test    eax, eax
0x180126090  jns     short loc_18012609D
0x180126092  mov     edx, eax
0x180126094  lea     rcx, aLsapvalidatene_0; "LsapValidateNewLocalAccountPassword"
0x18012609b  jmp     short loc_18012604F
0x18012609d  lea     rdx, [rsp+1D0h+var_178]; struct _CREDENTIAL_KEY **
0x1801260a2  lea     rcx, [rsp+1D0h+var_158]; struct _UNICODE_STRING *
0x1801260a7  call    ?LsapCreateCredKeyFromPassword@@YAJPEAU_UNICODE_STRING@@PEAPEAU_CREDENTIAL_KEY@@@Z; LsapCreateCredKeyFromPassword(_UNICODE_STRING *,_CREDENTIAL_KEY * *)
0x1801260ac  mov     ebx, eax
0x1801260ae  test    eax, eax
0x1801260b0  jns     short loc_1801260BD
0x1801260b2  mov     edx, eax
0x1801260b4  lea     rcx, aLsapcreatecred; "LsapCreateCredKeyFromPassword"
0x1801260bb  jmp     short loc_18012604F
0x1801260bd  call    ?LsapLazyInitSamConnection@@YAJXZ; LsapLazyInitSamConnection(void)
0x1801260c2  mov     ebx, eax
0x1801260c4  test    eax, eax
0x1801260c6  jns     short loc_1801260D6
0x1801260c8  mov     edx, eax
  ... truncated ...
```
