# CRpcIOManagerClient::SetRpcSecurity(void *)

- ea: `0x18001b5b0`
- end: `0x18001bfe4`
- name: `?SetRpcSecurity@CRpcIOManagerClient@@AEAAJPEAX@Z`
- size: `2612`
- prototype: `int(CRpcIOManagerClient *__hidden this, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18006e0cc`
- `0x18006e184`

## callees

- `0x180003cf0`
- `0x180006054`
- `0x180006764`
- `0x1800092f4`
- `0x18001b5b0`
- `0x180054968`
- `0x180058be4`
- `0x180062658`
- `0x180070f24`
- `0x180071268`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b73f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b73f`
- `RPCRT4!RpcEpResolveBinding` at `0x18001b8e2`
- `RPCRT4!RpcEpResolveBinding` at `0x18001b8e2`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x18001b94f`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x18001bb9a`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x18001b94f`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x18001bb9a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001b86f`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001bb35`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001be49`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001b86f`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001bb35`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001be49`
- `RPCRT4!RpcStringFreeW` at `0x18001bb80`
- `RPCRT4!RpcStringFreeW` at `0x18001bfa6`
- `RPCRT4!RpcStringFreeW` at `0x18001bb80`
- `RPCRT4!RpcStringFreeW` at `0x18001bfa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf90`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001b661`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001b661`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001bf46`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001bf46`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001bdbb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001bdbb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001bd64`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001bd64`
- `MTXCLU!MtxCluGetVirtualServerToken` at `0x18001bd03`
- `MTXCLU!MtxCluGetVirtualServerToken` at `0x18001bd03`

## string_xrefs

- `0x18001b68d`: `CheckCurrentTokenForLocalSystem`
- `0x18001b67d`: `CheckTokenMembership(NULL) failed checking token for LocalSystem.`
- `0x18001b69f`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`
- `0x18001bdda`: `Error from ImpersonateLoggedOnUser`
- `0x18001bd83`: `Error from DuplicateTokenEx`
- `0x18001b700`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18001b77c`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18001b8af`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18001b922`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18001b95e`: `com\complus\dtc\dtc\cm\src\iomgrclt.cpp`
- `0x18001b6ee`: `CRpcIOManagerClient::SetRpcSecurity`
- `0x18001b775`: `CRpcIOManagerClient::SetRpcSecurity`
- `0x18001b89d`: `CRpcIOManagerClient::SetRpcSecurity`
- `0x18001b910`: `CRpcIOManagerClient::SetRpcSecurity`
- `0x18001b957`: `CRpcIOManagerClient::SetRpcSecurity`
- `0x18001b7d3`: `[Remote:%s %.8s] Error from StringCchCopyW copying PhysicalNodeName`
- `0x18001bcce`: `We are a cluster resource - Impersonate the virtual server name %s`
- `0x18001bd0f`: `Error from MtxCluGetVirtualServerToken`
- `0x18001bde9`: `Successfully impersonated the virtual server name`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRpcIOManagerClient::SetRpcSecurity(CRpcIOManagerClient *this, void *a2)
{
  int v4; // r15d
  __int64 v5; // rax
  unsigned int v6; // r12d
  __int128 *AuthIdentity; // rbx
  signed int LastError; // eax
  signed int PhysicalNodeNameW; // ebx
  __int64 v10; // rsi
  __int64 v11; // rax
  unsigned __int16 *v12; // rbx
  __int64 v13; // rax
  unsigned __int64 v14; // r14
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r15
  const wchar_t *v17; // rax
  __int64 v18; // r9
  RPC_STATUS v19; // eax
  RPC_STATUS v20; // ebx
  RPC_STATUS v21; // eax
  RPC_STATUS v22; // ebx
  int v23; // ecx
  __int64 v24; // rcx
  __int64 v25; // rdx
  RPC_STATUS v26; // r15d
  __int64 v27; // r9
  RPC_STATUS v28; // eax
  const wchar_t *v29; // rax
  __int64 v30; // r9
  signed int v31; // eax
  const wchar_t *v32; // rax
  __int64 v33; // r9
  signed int v34; // eax
  void *v35; // r9
  unsigned int AuthzSvc[2]; // [rsp+28h] [rbp-B1h]
  unsigned int AuthzSvca[2]; // [rsp+28h] [rbp-B1h]
  const wchar_t *SecurityQOS; // [rsp+30h] [rbp-A9h]
  void *Src; // [rsp+38h] [rbp-A1h]
  void *Srca; // [rsp+38h] [rbp-A1h]
  int v42[2]; // [rsp+40h] [rbp-99h]
  int v43[2]; // [rsp+40h] [rbp-99h]
  RPC_WSTR ServerPrincName; // [rsp+50h] [rbp-89h] BYREF
  WINBOOL IsMember; // [rsp+58h] [rbp-81h] BYREF
  int v46; // [rsp+5Ch] [rbp-7Dh]
  LPVOID v47; // [rsp+60h] [rbp-79h] BYREF
  void *phNewToken; // [rsp+68h] [rbp-71h] BYREF
  HANDLE hExistingToken; // [rsp+70h] [rbp-69h] BYREF
  LPVOID v50; // [rsp+78h] [rbp-61h] BYREF
  unsigned __int16 *v51; // [rsp+80h] [rbp-59h] BYREF
  LPVOID v52; // [rsp+88h] [rbp-51h]
  LPVOID pv[2]; // [rsp+90h] [rbp-49h] BYREF
  RPC_WSTR v54[2]; // [rsp+A0h] [rbp-39h] BYREF
  int v55; // [rsp+B0h] [rbp-29h]
  __int128 v56; // [rsp+B8h] [rbp-21h] BYREF
  __int128 v57; // [rsp+C8h] [rbp-11h]
  __int128 v58; // [rsp+D8h] [rbp-1h]
  RPC_SECURITY_QOS v59; // [rsp+E8h] [rbp+Fh] BYREF

  v4 = 0;
  ServerPrincName = 0;
  v55 = 0;
  *(_OWORD *)v54 = 0;
  v59 = 0;
  v5 = *((_QWORD *)this + 9);
  v6 = *(_DWORD *)(v5 + 36);
  v46 = 0;
  hExistingToken = 0;
  phNewToken = 0;
  v47 = 0;
  v50 = 0;
  AuthIdentity = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  IsMember = 0;
  v51 = 0;
  v52 = 0;
  *(_QWORD *)&v59.Version = 1;
  v59.IdentityTracking = *(_DWORD *)(v5 + 32);
  v59.ImpersonationType = 2;
  if ( *((_DWORD *)this + 12) == 1 )
  {
    v6 = 10;
    goto LABEL_22;
  }
  if ( !CheckTokenMembership(0, &LocalSystemSid, &IsMember) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    AuthzSvc[0] = LastError;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
      1072,
      L"CheckCurrentTokenForLocalSystem",
      *(_QWORD *)AuthzSvc,
      L"CheckTokenMembership(NULL) failed checking token for LocalSystem.");
  }
  if ( IsMember )
  {
    PhysicalNodeNameW = GetPhysicalNodeNameW(&v51);
    if ( PhysicalNodeNameW < 0 )
    {
      AuthzSvc[0] = PhysicalNodeNameW;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
        488,
        L"CRpcIOManagerClient::SetRpcSecurity",
        *(_QWORD *)AuthzSvc,
        L"[Remote:%s %.8s] Call to GetPhysicalNodeName failed",
        *((_QWORD *)this + 2),
        *((_QWORD *)this + 3));
      goto LABEL_74;
    }
    v10 = -1;
    v11 = -1;
    v12 = v51;
    do
      ++v11;
    while ( v51[v11] );
    v13 = (unsigned int)(v11 + 2);
    v14 = (unsigned int)v13;
    v15 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13);
    v16 = v15;
    v52 = v15;
    if ( !v15 )
    {
      PhysicalNodeNameW = -2147024882;
      *(_QWORD *)v42 = *((_QWORD *)this + 3);
      Src = (void *)*((_QWORD *)this + 2);
      v17 = L"[Remote:%s %.8s] Unable to allocate space for node name plus dollar sign";
      v18 = 498;
LABEL_14:
      AuthzSvc[0] = PhysicalNodeNameW;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
        v18,
        L"CRpcIOManagerClient::SetRpcSecurity",
        *(_QWORD *)AuthzSvc,
        v17,
        Src,
        *(_QWORD *)v42);
      goto LABEL_74;
    }
    PhysicalNodeNameW = StringCchCopyW(v15, v14, v12);
    if ( PhysicalNodeNameW < 0 )
    {
      *(_QWORD *)v42 = *((_QWORD *)this + 3);
      Src = (void *)*((_QWORD *)this + 2);
      v17 = L"[Remote:%s %.8s] Error from StringCchCopyW copying PhysicalNodeName";
      v18 = 506;
      goto LABEL_14;
    }
    PhysicalNodeNameW = StringCchCatW(v16, v14, L"$");
    if ( PhysicalNodeNameW < 0 )
    {
      *(_QWORD *)v42 = *((_QWORD *)this + 3);
      Src = (void *)*((_QWORD *)this + 2);
      v17 = L"[Remote:%s %.8s] Error from StringCchCatW concatenating a dollar sign";
      v18 = 514;
      goto LABEL_14;
    }
    *(_QWORD *)&v56 = v16;
    do
      ++v10;
    while ( v16[v10] );
    DWORD2(v56) = v10;
    v4 = 0;
    *(_QWORD *)&v57 = 0;
    DWORD2(v57) = 0;
    *(_QWORD *)&v58 = 0;
    *((_QWORD *)&v58 + 1) = 0x200000000LL;
    AuthIdentity = &v56;
  }
LABEL_22:
  v19 = RpcBindingSetAuthInfoExW(a2, 0, 6u, 0xAu, AuthIdentity, 0, &v59);
  v20 = v19;
  if ( v19 )
  {
    AuthzSvc[0] = v19;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
      548,
      L"CRpcIOManagerClient::SetRpcSecurity",
      *(_QWORD *)AuthzSvc,
      L"[Remote:%s %.8s] Call to RpcBindingSetAuthInfoEx failed",
      *((_QWORD *)this + 2),
      *((_QWORD *)this + 3));
LABEL_24:
    PhysicalNodeNameW = RpcStatusToHresult(v20);
    goto LABEL_73;
  }
  v20 = RpcEpResolveBinding(a2, qword_18008BBE0);
  if ( v20 )
  {
    AuthzSvc[0] = v20;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
      559,
      L"CRpcIOManagerClient::SetRpcSecurity",
      *(_QWORD *)AuthzSvc,
      L"[Remote:%s %.8s] Call to RpcEpResolveBinding failed",
      *((_QWORD *)this + 2),
      *((_QWORD *)this + 3));
    TraceRpcEEInfo();
    goto LABEL_24;
  }
  v21 = RpcMgmtInqServerPrincNameW(a2, v6, &ServerPrincName);
  v22 = v21;
  if ( v21 )
  {
    if ( v6 != 16 && v6 != 9 )
    {
      if ( v21 == 1723 || v21 == 1747 )
      {
        AuthzSvc[0] = v21;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
          598,
          L"CRpcIOManagerClient::SetRpcSecurity",
          *(_QWORD *)AuthzSvc,
          L"[Remote:%s %.8s] Call to RpcMgmtInqServerPrincName failed.  The partner does not support secure calls",
          *((_QWORD *)this + 2),
          *((_QWORD *)this + 3));
        *(_DWORD *)(*((_QWORD *)this + 1) + 20LL) = 0;
        PhysicalNodeNameW = 0;
        goto LABEL_73;
      }
      AuthzSvc[0] = v21;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
        607,
        L"CRpcIOManagerClient::SetRpcSecurity",
        *(_QWORD *)AuthzSvc,
        L"[Remote:%s %.8s] Call to RpcMgmtInqServerPrincName failed.  Could not determine if partner supports secure calls",
        *((_QWORD *)this + 2),
        *((_QWORD *)this + 3));
      v23 = v22;
      goto LABEL_72;
    }
    v4 = 1;
    TraceStringInline(
      1,
      3,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
      582,
      L"CRpcIOManagerClient::SetRpcSecurity",
      0,
      L"[Remote:%s %.8s] Call to RpcMgmtInqServerPrincName will be retried with Negotiate/Kerbros",
      *((_QWORD *)this + 2),
      *((_QWORD *)this + 3));
  }
  v24 = *((_QWORD *)this + 1);
  if ( !*(_DWORD *)(v24 + 20) )
  {
    TraceStringInline(
      1,
      3,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
      618,
      L"CRpcIOManagerClient::SetRpcSecurity",
      0,
      L"[Remote:%s %.8s] Using unsecure rpc since GetMutualAuthFlag() returned FALSE",
      *((_QWORD *)this + 2),
      *((_QWORD *)this + 3));
LABEL_37:
    PhysicalNodeNameW = 0;
    goto LABEL_78;
  }
  PhysicalNodeNameW = (*(__int64 (__fastcall **)(_QWORD, RPC_WSTR *))(**(_QWORD **)(v24 + 88) + 96LL))(
                        *(_QWORD *)(v24 + 88),
                        v54);
  v25 = 0;
  if ( PhysicalNodeNameW < 0 )
  {
    *(_QWORD *)v42 = *((_QWORD *)this + 3);
    Src = (void *)*((_QWORD *)this + 2);
    v17 = L"[Remote:%s %.8s] Call to m_pCSessObj->m_pINameObjPartners->GetSPN failed.";
    v18 = 631;
    goto LABEL_14;
  }
  if ( !v4 )
    goto LABEL_50;
  v59.Capabilities = *(_DWORD *)(*((_QWORD *)this + 9) + 28LL);
  v26 = RpcBindingSetAuthInfoExW(a2, v54[1], 6u, v6, 0, 0, &v59);
  if ( !v26 )
  {
    if ( ServerPrincName )
    {
      RpcStringFreeW(&ServerPrincName);
      ServerPrincName = 0;
    }
    v28 = RpcMgmtInqServerPrincNameW(a2, v6, &ServerPrincName);
    v26 = v28;
    if ( v28 == 1723 || v28 == 1747 )
    {
      AuthzSvc[0] = v28;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
        683,
        L"CRpcIOManagerClient::SetRpcSecurity",
        *(_QWORD *)AuthzSvc,
        L"[Remote:%s %.8s] Call to RpcMgmtInqServerPrincName failed.  The partner does not support secure calls",
        *((_QWORD *)this + 2),
        *((_QWORD *)this + 3));
      *(_DWORD *)(*((_QWORD *)this + 1) + 20LL) = 0;
      goto LABEL_37;
    }
    if ( v28 )
    {
      *(_QWORD *)v43 = *((_QWORD *)this + 3);
      Srca = (void *)*((_QWORD *)this + 2);
      SecurityQOS = L"[Remote:%s %.8s] Call to RpcMgmtInqServerPrincName failed.  Could not determine if partner supports secure calls";
      v27 = 693;
      goto LABEL_71;
    }
LABEL_50:
    if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 1) + 88LL) + 56LL))(
            *(_QWORD *)(*((_QWORD *)this + 1) + 88LL),
            v25)
      && (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 9) + 64LL) + 24LL))(*(_QWORD *)(*((_QWORD *)this + 9) + 64LL)) )
    {
      PhysicalNodeNameW = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)(*((_QWORD *)this + 9) + 64LL)
                                                                      + 40LL))(
                            *(_QWORD *)(*((_QWORD *)this + 9) + 64LL),
                            &v47);
      if ( PhysicalNodeNameW < 0 )
      {
        v29 = L"Error from ITmInstance::GetHostName";
        v30 = 708;
LABEL_58:
        AuthzSvc[0] = PhysicalNodeNameW;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
          v30,
          L"CRpcIOManagerClient::SetRpcSecurity",
          *(_QWORD *)AuthzSvc,
          v29);
        goto LABEL_74;
      }
      PhysicalNodeNameW = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)(*((_QWORD *)this + 9) + 64LL)
                                                                      + 64LL))(
                            *(_QWORD *)(*((_QWORD *)this + 9) + 64LL),
                            &v50);
      if ( PhysicalNodeNameW < 0 )
      {
        v29 = L"Error from ITmInstance::GetResourceName";
        v30 = 715;
        goto LABEL_58;
      }
      TraceStringInline(
        1,
        4,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
        719,
        L"CRpcIOManagerClient::SetRpcSecurity",
        0,
        L"We are a cluster resource - Impersonate the virtual server name %s",
        v47);
      PhysicalNodeNameW = MtxCluGetVirtualServerToken(v47, v50, &hExistingToken);
      if ( PhysicalNodeNameW < 0 )
      {
        v29 = L"Error from MtxCluGetVirtualServerToken";
        v30 = 724;
        goto LABEL_58;
      }
      if ( !DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
      {
        v31 = GetLastError();
        PhysicalNodeNameW = v31;
        if ( v31 > 0 )
          PhysicalNodeNameW = (unsigned __int16)v31 | 0x80070000;
        v32 = L"Error from DuplicateTokenEx";
        v33 = 738;
LABEL_63:
        AuthzSvca[0] = PhysicalNodeNameW;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
          v33,
          L"CRpcIOManagerClient::SetRpcSecurity",
          *(_QWORD *)AuthzSvca,
          v32);
        goto LABEL_73;
      }
      if ( !ImpersonateLoggedOnUser(phNewToken) )
      {
        v34 = GetLastError();
        PhysicalNodeNameW = v34;
        if ( v34 > 0 )
          PhysicalNodeNameW = (unsigned __int16)v34 | 0x80070000;
        v32 = L"Error from ImpersonateLoggedOnUser";
        v33 = 746;
        goto LABEL_63;
      }
      TraceStringInline(
        1,
        4,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
        750,
        L"CRpcIOManagerClient::SetRpcSecurity",
        0,
        L"Successfully impersonated the virtual server name");
      v46 = 1;
    }
    v59.Capabilities = *(_DWORD *)(*((_QWORD *)this + 9) + 28LL);
    v26 = RpcBindingSetAuthInfoExW(a2, v54[1], 6u, v6, 0, 0, &v59);
    if ( !v26 )
      goto LABEL_73;
    *(_QWORD *)v43 = *((_QWORD *)this + 3);
    Srca = (void *)*((_QWORD *)this + 2);
    SecurityQOS = L"[Remote:%s %.8s] Call to RpcBindingSetAuthInfoEx failed";
    v27 = 770;
    goto LABEL_71;
  }
  *(_QWORD *)v43 = *((_QWORD *)this + 3);
  Srca = (void *)*((_QWORD *)this + 2);
  SecurityQOS = L"[Remote:%s %.8s] Call to RpcBindingSetAuthInfoEx failed";
  v27 = 656;
LABEL_71:
  AuthzSvc[0] = v26;
  TraceStringInline(
    1,
    1,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
    v27,
    L"CRpcIOManagerClient::SetRpcSecurity",
    *(_QWORD *)AuthzSvc,
    SecurityQOS,
    Srca,
    *(_QWORD *)v43);
  v23 = v26;
LABEL_72:
  PhysicalNodeNameW = RpcStatusToHresult(v23);
LABEL_73:
  if ( PhysicalNodeNameW < 0 )
  {
LABEL_74:
    if ( !*(_DWORD *)(*((_QWORD *)this + 9) + 40LL) )
    {
      *(_OWORD *)pv = 0;
      MakeStringW((unsigned __int16 **)pv, L"%X", (unsigned int)PhysicalNodeNameW);
      pv[1] = *((LPVOID *)this + 2);
      AuthzSvc[0] = 0;
      DtcWriteToEventLoggerExW(2u, 3u, 0x8000130F, v35, 2u, *(size_t *)AuthzSvc, (const unsigned __int16 **)pv, 0, 1);
      CoTaskMemFree(pv[0]);
    }
  }
  if ( v46 )
  {
    TraceStringInline(
      1,
      4,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrclt.cpp",
      799,
      L"CRpcIOManagerClient::SetRpcSecurity",
      0,
      L"Reverting back to self");
    RevertToSelf();
  }
LABEL_78:
  CoTaskMemFree(v47);
  CoTaskMemFree(v50);
  CoTaskMemFree(v51);
  CoTaskMemFree(v52);
  if ( phNewToken )
  {
    CloseHandle(phNewToken);
    phNewToken = 0;
  }
  if ( hExistingToken )
  {
    CloseHandle(hExistingToken);
    hExistingToken = 0;
  }
  if ( ServerPrincName )
  {
    RpcStringFreeW(&ServerPrincName);
    ServerPrincName = 0;
  }
  CSTRING::Clear((CSTRING *)v54);
  return (unsigned int)PhysicalNodeNameW;
}

```

## disassembly

```asm
0x18001b5b0  mov     [rsp-8+arg_10], rbx
0x18001b5b5  push    rbp
0x18001b5b6  push    rsi
0x18001b5b7  push    rdi
0x18001b5b8  push    r12
0x18001b5ba  push    r13
0x18001b5bc  push    r14
0x18001b5be  push    r15
0x18001b5c0  lea     rbp, [rsp-27h]
0x18001b5c5  sub     rsp, 100h
0x18001b5cc  mov     rax, cs:__security_cookie
0x18001b5d3  xor     rax, rsp
0x18001b5d6  mov     [rbp+57h+var_38], rax
0x18001b5da  mov     r13, rdx
0x18001b5dd  mov     rdi, rcx
0x18001b5e0  xor     r15d, r15d
0x18001b5e3  mov     [rsp+130h+ServerPrincName], r15
0x18001b5e8  mov     [rbp+57h+var_80], r15d
0x18001b5ec  xorps   xmm0, xmm0
0x18001b5ef  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x18001b5f4  movups  xmmword ptr [rbp+57h+var_48.Version], xmm0
0x18001b5f8  mov     rax, [rcx+48h]
0x18001b5fc  mov     r12d, [rax+24h]
0x18001b600  mov     [rbp+57h+var_D4], r15d
0x18001b604  mov     [rbp+57h+hExistingToken], r15
0x18001b608  mov     [rbp+57h+phNewToken], r15
0x18001b60c  mov     [rbp+57h+var_D0], r15
0x18001b610  mov     [rbp+57h+var_B8], r15
0x18001b614  mov     ebx, r15d
0x18001b617  movups  [rbp+57h+var_78], xmm0
0x18001b61b  movups  [rbp+57h+var_68], xmm0
0x18001b61f  movups  [rbp+57h+var_58], xmm0
0x18001b623  mov     [rsp+130h+IsMember], r15d
0x18001b628  mov     [rbp+57h+var_B0], r15
0x18001b62c  mov     [rbp+57h+var_A8], r15
0x18001b630  lea     esi, [r15+1]
0x18001b634  mov     qword ptr [rbp+57h+var_48.Version], rsi
0x18001b638  mov     eax, [rax+20h]
0x18001b63b  mov     [rbp+57h+var_48.IdentityTracking], eax
0x18001b63e  mov     [rbp+57h+var_48.ImpersonationType], 2
0x18001b645  cmp     [rcx+30h], esi
0x18001b648  jnz     short loc_18001B653
0x18001b64a  lea     r12d, [r15+0Ah]
0x18001b64e  jmp     loc_18001B84F
0x18001b653  lea     r8, [rsp+130h+IsMember]; IsMember
0x18001b658  lea     rdx, ?LocalSystemSid@@3U_SID1@@A; SidToCheck
0x18001b65f  xor     ecx, ecx; TokenHandle
0x18001b661  call    cs:__imp_CheckTokenMembership
0x18001b667  test    eax, eax
0x18001b669  jnz     short loc_18001B6B2
0x18001b66b  call    cs:__imp_GetLastError
0x18001b671  test    eax, eax
0x18001b673  jle     short loc_18001B67D
0x18001b675  movzx   eax, ax
0x18001b678  or      eax, 80070000h
0x18001b67d  lea     rcx, aChecktokenmemb_0; "CheckTokenMembership(NULL) failed check"...
0x18001b684  mov     [rsp+130h+SecurityQOS], rcx
0x18001b689  mov     [rsp+130h+AuthzSvc], eax
0x18001b68d  lea     rax, aCheckcurrentto; "CheckCurrentTokenForLocalSystem"
0x18001b694  mov     [rsp+130h+AuthIdentity], rax
0x18001b699  mov     r9d, 430h
0x18001b69f  lea     r8, aComComplusDtcS_12; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x18001b6a6  mov     edx, esi
0x18001b6a8  mov     ecx, 7
0x18001b6ad  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b6b2  cmp     [rsp+130h+IsMember], r15d
0x18001b6b7  jz      loc_18001B84F
0x18001b6bd  lea     rcx, [rbp+57h+var_B0]; unsigned __int16 **
0x18001b6c1  call    ?GetPhysicalNodeNameW@@YAJPEAPEAG@Z; GetPhysicalNodeNameW(ushort * *)
0x18001b6c6  mov     ebx, eax
0x18001b6c8  test    eax, eax
0x18001b6ca  jns     short loc_18001B720
0x18001b6cc  mov     rcx, [rdi+18h]
0x18001b6d0  mov     qword ptr [rsp+130h+var_F0], rcx
0x18001b6d5  mov     rcx, [rdi+10h]
0x18001b6d9  mov     [rsp+130h+Src], rcx
0x18001b6de  lea     rax, aRemoteS8sCallT_1; "[Remote:%s %.8s] Call to GetPhysicalNod"...
0x18001b6e5  mov     [rsp+130h+SecurityQOS], rax
0x18001b6ea  mov     [rsp+130h+AuthzSvc], ebx
0x18001b6ee  lea     r14, aCrpciomanagerc_8; "CRpcIOManagerClient::SetRpcSecurity"
0x18001b6f5  mov     [rsp+130h+AuthIdentity], r14
0x18001b6fa  mov     r9d, 1E8h
0x18001b700  lea     rsi, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18001b707  mov     r8, rsi
0x18001b70a  mov     r12d, 1
0x18001b710  mov     edx, r12d
0x18001b713  mov     ecx, r12d
0x18001b716  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b71b  jmp     loc_18001BEA9
0x18001b720  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001b724  mov     rax, rsi
0x18001b727  mov     rbx, [rbp+57h+var_B0]
0x18001b72b  inc     rax
0x18001b72e  cmp     [rbx+rax*2], r15w
0x18001b733  jnz     short loc_18001B72B
0x18001b735  add     eax, 2
0x18001b738  mov     r14d, eax
0x18001b73b  lea     rcx, [rax+rax]; cb
0x18001b73f  call    cs:__imp_CoTaskMemAlloc
0x18001b745  mov     r15, rax
0x18001b748  mov     [rbp+57h+var_A8], rax
0x18001b74c  test    rax, rax
0x18001b74f  jnz     short loc_18001B7AD
0x18001b751  mov     ebx, 8007000Eh
0x18001b756  mov     rcx, [rdi+18h]
0x18001b75a  mov     qword ptr [rsp+130h+var_F0], rcx
0x18001b75f  mov     rcx, [rdi+10h]
0x18001b763  mov     [rsp+130h+Src], rcx
0x18001b768  lea     rax, aRemoteS8sUnabl; "[Remote:%s %.8s] Unable to allocate spa"...
0x18001b76f  mov     r9d, 1F2h
0x18001b775  lea     r14, aCrpciomanagerc_8; "CRpcIOManagerClient::SetRpcSecurity"
0x18001b77c  lea     rsi, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18001b783  mov     [rsp+130h+SecurityQOS], rax
0x18001b788  mov     [rsp+130h+AuthzSvc], ebx
0x18001b78c  mov     [rsp+130h+AuthIdentity], r14
0x18001b791  mov     r8, rsi
0x18001b794  mov     r12d, 1
0x18001b79a  mov     edx, r12d
0x18001b79d  mov     ecx, r12d
0x18001b7a0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b7a5  xor     r15d, r15d
0x18001b7a8  jmp     loc_18001BEA9
0x18001b7ad  mov     r8, rbx; unsigned __int16 *
0x18001b7b0  mov     rdx, r14; unsigned __int64
0x18001b7b3  mov     rcx, r15; unsigned __int16 *
0x18001b7b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b7bb  mov     ebx, eax
0x18001b7bd  test    eax, eax
0x18001b7bf  jns     short loc_18001B7E2
0x18001b7c1  mov     rax, [rdi+18h]
0x18001b7c5  mov     qword ptr [rsp+130h+var_F0], rax
0x18001b7ca  mov     rax, [rdi+10h]
0x18001b7ce  mov     [rsp+130h+Src], rax
0x18001b7d3  lea     rax, aRemoteS8sError_0; "[Remote:%s %.8s] Error from StringCchCo"...
0x18001b7da  mov     r9d, 1FAh
0x18001b7e0  jmp     short loc_18001B775
0x18001b7e2  lea     r8, asc_1800B5ED8; "$"
0x18001b7e9  mov     rdx, r14; unsigned __int64
0x18001b7ec  mov     rcx, r15; unsigned __int16 *
0x18001b7ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001b7f4  mov     ebx, eax
0x18001b7f6  xor     eax, eax
0x18001b7f8  test    ebx, ebx
0x18001b7fa  jns     short loc_18001B820
0x18001b7fc  mov     rax, [rdi+18h]
0x18001b800  mov     qword ptr [rsp+130h+var_F0], rax
0x18001b805  mov     rax, [rdi+10h]
0x18001b809  mov     [rsp+130h+Src], rax
0x18001b80e  lea     rax, aRemoteS8sError; "[Remote:%s %.8s] Error from StringCchCa"...
0x18001b815  mov     r9d, 202h
0x18001b81b  jmp     loc_18001B775
0x18001b820  mov     qword ptr [rbp+57h+var_78], r15
0x18001b824  inc     rsi
0x18001b827  cmp     [r15+rsi*2], ax
0x18001b82c  jnz     short loc_18001B824
0x18001b82e  mov     dword ptr [rbp+57h+var_78+8], esi
0x18001b831  xor     r15d, r15d
0x18001b834  mov     qword ptr [rbp+57h+var_68], r15
0x18001b838  mov     dword ptr [rbp+57h+var_68+8], r15d
0x18001b83c  mov     qword ptr [rbp+57h+var_58], r15
0x18001b840  mov     dword ptr [rbp+57h+var_58+8], r15d
0x18001b844  mov     dword ptr [rbp+57h+var_58+0Ch], 2
0x18001b84b  lea     rbx, [rbp+57h+var_78]
0x18001b84f  lea     rax, [rbp+57h+var_48]
0x18001b853  mov     [rsp+130h+SecurityQOS], rax; SecurityQOS
0x18001b858  mov     [rsp+130h+AuthzSvc], r15d; AuthzSvc
0x18001b85d  mov     [rsp+130h+AuthIdentity], rbx; AuthIdentity
0x18001b862  xor     edx, edx; ServerPrincName
0x18001b864  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18001b868  lea     r8d, [rdx+6]; AuthnLevel
0x18001b86c  mov     rcx, r13; Binding
0x18001b86f  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18001b875  mov     ebx, eax
0x18001b877  test    eax, eax
0x18001b879  jz      short loc_18001B8D8
0x18001b87b  mov     rcx, [rdi+18h]
0x18001b87f  mov     qword ptr [rsp+130h+var_F0], rcx
0x18001b884  mov     rcx, [rdi+10h]
0x18001b888  mov     [rsp+130h+Src], rcx
0x18001b88d  lea     rcx, aRemoteS8sCallT_0; "[Remote:%s %.8s] Call to RpcBindingSetA"...
0x18001b894  mov     [rsp+130h+SecurityQOS], rcx
0x18001b899  mov     [rsp+130h+AuthzSvc], eax
0x18001b89d  lea     r14, aCrpciomanagerc_8; "CRpcIOManagerClient::SetRpcSecurity"
0x18001b8a4  mov     [rsp+130h+AuthIdentity], r14
0x18001b8a9  mov     r9d, 224h
0x18001b8af  lea     rsi, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18001b8b6  mov     r8, rsi
0x18001b8b9  mov     r12d, 1
0x18001b8bf  mov     edx, r12d
0x18001b8c2  mov     ecx, r12d
0x18001b8c5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b8ca  mov     ecx, ebx; int
0x18001b8cc  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18001b8d1  mov     ebx, eax
0x18001b8d3  jmp     loc_18001BEA5
0x18001b8d8  lea     rdx, qword_18008BBE0; IfSpec
0x18001b8df  mov     rcx, r13; Binding
0x18001b8e2  call    cs:__imp_RpcEpResolveBinding
0x18001b8e8  mov     ebx, eax
0x18001b8ea  test    eax, eax
0x18001b8ec  jz      short loc_18001B944
0x18001b8ee  mov     rcx, [rdi+18h]
0x18001b8f2  mov     qword ptr [rsp+130h+var_F0], rcx
0x18001b8f7  mov     rcx, [rdi+10h]
0x18001b8fb  mov     [rsp+130h+Src], rcx
0x18001b900  lea     rax, aRemoteS8sCallT_3; "[Remote:%s %.8s] Call to RpcEpResolveBi"...
0x18001b907  mov     [rsp+130h+SecurityQOS], rax
0x18001b90c  mov     [rsp+130h+AuthzSvc], ebx
0x18001b910  lea     r14, aCrpciomanagerc_8; "CRpcIOManagerClient::SetRpcSecurity"
0x18001b917  mov     [rsp+130h+AuthIdentity], r14
0x18001b91c  mov     r9d, 22Fh
0x18001b922  lea     rsi, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18001b929  mov     r8, rsi
0x18001b92c  mov     r12d, 1
0x18001b932  mov     edx, r12d
0x18001b935  mov     ecx, r12d
0x18001b938  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b93d  call    ?TraceRpcEEInfo@@YAXXZ; TraceRpcEEInfo(void)
0x18001b942  jmp     short loc_18001B8CA
0x18001b944  lea     r8, [rsp+130h+ServerPrincName]; ServerPrincName
0x18001b949  mov     edx, r12d; AuthnSvc
0x18001b94c  mov     rcx, r13; Binding
0x18001b94f  call    cs:__imp_RpcMgmtInqServerPrincNameW
0x18001b955  mov     ebx, eax
0x18001b957  lea     r14, aCrpciomanagerc_8; "CRpcIOManagerClient::SetRpcSecurity"
0x18001b95e  lea     rsi, aComComplusDtcD_29; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrc"...
0x18001b965  xor     ecx, ecx
0x18001b967  test    eax, eax
0x18001b969  jz      loc_18001BA6E
0x18001b96f  cmp     r12d, 10h
0x18001b973  jz      loc_18001BA2B
0x18001b979  cmp     r12d, 9
0x18001b97d  jz      loc_18001BA2B
0x18001b983  cmp     eax, 6BBh
0x18001b988  jz      short loc_18001B9D7
0x18001b98a  cmp     eax, 6D3h
0x18001b98f  jz      short loc_18001B9D7
0x18001b991  mov     rax, [rdi+18h]
0x18001b995  mov     qword ptr [rsp+130h+var_F0], rax
0x18001b99a  mov     rax, [rdi+10h]
0x18001b99e  mov     [rsp+130h+Src], rax
0x18001b9a3  lea     rax, aRemoteS8sCallT_5; "[Remote:%s %.8s] Call to RpcMgmtInqServ"...
0x18001b9aa  mov     [rsp+130h+SecurityQOS], rax
0x18001b9af  mov     [rsp+130h+AuthzSvc], ebx
0x18001b9b3  mov     [rsp+130h+AuthIdentity], r14
0x18001b9b8  mov     r9d, 25Fh
0x18001b9be  mov     r8, rsi
0x18001b9c1  lea     r12d, [rcx+1]
0x18001b9c5  mov     edx, r12d
0x18001b9c8  mov     ecx, r12d
0x18001b9cb  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b9d0  mov     ecx, ebx
0x18001b9d2  jmp     loc_18001BE9B
0x18001b9d7  mov     rax, [rdi+18h]
0x18001b9db  mov     qword ptr [rsp+130h+var_F0], rax
0x18001b9e0  mov     rax, [rdi+10h]
0x18001b9e4  mov     [rsp+130h+Src], rax
0x18001b9e9  lea     rax, aRemoteS8sCallT_2; "[Remote:%s %.8s] Call to RpcMgmtInqServ"...
0x18001b9f0  mov     [rsp+130h+SecurityQOS], rax
0x18001b9f5  mov     [rsp+130h+AuthzSvc], ebx
0x18001b9f9  mov     [rsp+130h+AuthIdentity], r14
0x18001b9fe  mov     r9d, 256h
0x18001ba04  mov     r8, rsi
0x18001ba07  mov     r12d, 1
0x18001ba0d  mov     edx, r12d
0x18001ba10  mov     ecx, r12d
0x18001ba13  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001ba18  mov     rax, [rdi+8]
0x18001ba1c  xor     r15d, r15d
0x18001ba1f  mov     [rax+14h], r15d
0x18001ba23  mov     ebx, r15d
0x18001ba26  jmp     loc_18001BEA5
0x18001ba2b  mov     r15d, 1
0x18001ba31  mov     rax, [rdi+18h]
0x18001ba35  mov     qword ptr [rsp+130h+var_F0], rax
0x18001ba3a  mov     rax, [rdi+10h]
0x18001ba3e  mov     [rsp+130h+Src], rax
0x18001ba43  lea     rax, aRemoteS8sCallT_6; "[Remote:%s %.8s] Call to RpcMgmtInqServ"...
0x18001ba4a  mov     [rsp+130h+SecurityQOS], rax
0x18001ba4f  mov     qword ptr [rsp+130h+AuthzSvc], rcx
0x18001ba54  mov     [rsp+130h+AuthIdentity], r14
0x18001ba59  mov     r9d, 246h
0x18001ba5f  mov     r8, rsi
0x18001ba62  lea     edx, [r15+2]
0x18001ba66  mov     ecx, r15d
0x18001ba69  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001ba6e  mov     rcx, [rdi+8]
0x18001ba72  cmp     dword ptr [rcx+14h], 0
0x18001ba76  jnz     short loc_18001BAC0
0x18001ba78  mov     rax, [rdi+18h]
0x18001ba7c  mov     qword ptr [rsp+130h+var_F0], rax
0x18001ba81  mov     rax, [rdi+10h]
0x18001ba85  mov     [rsp+130h+Src], rax
0x18001ba8a  lea     rax, aRemoteS8sUsing; "[Remote:%s %.8s] Using unsecure rpc sin"...
0x18001ba91  mov     [rsp+130h+SecurityQOS], rax
0x18001ba96  xor     r15d, r15d
0x18001ba99  mov     qword ptr [rsp+130h+AuthzSvc], r15
0x18001ba9e  mov     [rsp+130h+AuthIdentity], r14
0x18001baa3  mov     r9d, 26Ah
0x18001baa9  mov     r8, rsi
  ... truncated ...
```
