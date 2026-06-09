# CRdpWinConnector::StartConnection(RdpXInterfacePropertyStore *,RdpXInterfaceConnectorEvents *,RdpXInterface *)

- ea: `0x1400f6830`
- end: `0x1400f7460`
- name: `?StartConnection@CRdpWinConnector@@UEAA?AW4_XResult32@@PEAURdpXInterfacePropertyStore@@PEAURdpXInterfaceConnectorEvents@@PEAURdpXInterface@@@Z`
- size: `3120`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140004703`
- `0x140008a34`
- `0x14000cf70`
- `0x14000cffc`
- `0x14000d078`
- `0x14001e404`
- `0x140026118`
- `0x14005c318`
- `0x14005e848`
- `0x140063b70`
- `0x140064258`
- `0x1400719e0`
- `0x140071a4c`
- `0x140071b48`
- `0x1400720e0`
- `0x140072270`
- `0x1400722f0`
- `0x140072730`
- `0x1400a22ac`
- `0x1400b5380`
- `0x1400f5cd8`
- `0x1400f6830`
- `0x140109b08`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `ole32!OleInitialize` at `0x1400f6973`
- `ole32!OleInitialize` at `0x1400f6973`
- `ole32!OleUninitialize` at `0x1400f6ccc`
- `ole32!OleUninitialize` at `0x1400f6ccc`
- `OLEAUT32!__imp_SysAllocString` at `0x1400f6fdb`
- `OLEAUT32!__imp_SysAllocString` at `0x1400f6fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f6cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f700a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f6cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f700a`
- `RPCRT4!UuidFromStringW` at `0x1400f6e7d`
- `RPCRT4!UuidFromStringW` at `0x1400f6e7d`

## string_xrefs

- `0x1400f729a`: `Tcp::UseIPV6LinkLocal`
- `0x1400f71f7`: `Failed to create the global context`
- `0x1400f6b51`: `RdpHvSocketServiceId`
- `0x1400f735c`: `Failed to create the TCP connector`
- `0x1400f72d3`: `Failed to enable usage of IPV6 link-local addresses`

## pseudocode

```c
__int64 __fastcall CRdpWinConnector::StartConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // r15
  int v7; // r13d
  OLECHAR *v8; // r14
  __int64 v9; // rdx
  CRdpWinConnector *v10; // rcx
  __int64 v11; // r8
  PVOID *v12; // rax
  int ActivityIdPrefix; // eax
  int v14; // edx
  const char *v15; // rcx
  HRESULT Instance; // edi
  int v17; // eax
  int v18; // edx
  const char *v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  char v22; // r15
  int v23; // eax
  const unsigned __int16 *v24; // rax
  const unsigned __int16 *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  char v29; // bl
  int v30; // eax
  int v31; // eax
  int v32; // edx
  const char *v33; // rcx
  __int64 v34; // rbx
  unsigned int v35; // eax
  char v37; // r12
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  unsigned int v41; // eax
  int v42; // eax
  unsigned int v43; // r15d
  unsigned int i; // ebx
  unsigned int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  unsigned int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  const OLECHAR *v53; // rax
  unsigned __int16 *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  CRdpWinConnector *v61; // rcx
  int v62; // eax
  unsigned int v63; // eax
  int v64; // eax
  int v65; // edx
  const char *v66; // rcx
  struct IUnknown **v67; // rbx
  int v68; // eax
  int v69; // edx
  const char *v70; // rcx
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // r8
  char v74; // di
  int v75; // eax
  struct IUnknown *v76; // rcx
  void **v77; // r9
  __int64 v78; // rdx
  int v79; // eax
  CRdpWinConnector *v81; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v82; // [rsp+50h] [rbp-B0h] BYREF
  int v83; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v84; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v85; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v87; // [rsp+70h] [rbp-90h] BYREF
  __int64 v88; // [rsp+78h] [rbp-88h]
  __int64 v89; // [rsp+80h] [rbp-80h]
  _BYTE v90[48]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v91[32]; // [rsp+C0h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v93[40]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 StringUuid[512]; // [rsp+140h] [rbp+40h] BYREF

  v89 = a3;
  v6 = a1;
  v88 = a4;
  memset_0(StringUuid, 0, sizeof(StringUuid));
  v82 = 0;
  v86 = 0;
  CRDPENCConnectorStringSerializer::CRDPENCConnectorStringSerializer((CRDPENCConnectorStringSerializer *)v90);
  v7 = 0;
  v87 = 0;
  v84 = 0;
  RdpXSPtr<RdpXInterfaceTapProtocolServerEvents>::SafeAddRef(&v84);
  v8 = 0;
  memset_0(v93, 0, 0x4Eu);
  v85 = 0;
  v83 = 0;
  if ( !a2 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v10, v9, v11);
    v14 = 10;
    v15 = "pTransportProps";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)&WPP_bc9beace3504374faa5adebceb123de4_Traceguids,
      ActivityIdPrefix,
      (__int64)v15);
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_7:
    Instance = -2147467261;
    goto LABEL_51;
  }
  if ( !a3 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v10, v9, v11);
    v14 = 11;
    v15 = "pTransportEvents";
    goto LABEL_6;
  }
  Instance = OleInitialize(0);
  if ( Instance < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_59;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpX_GetActivityIdPrefix(v10, v9, v11);
      v18 = 12;
      v19 = "OleInitialize from WinConnector failed!";
LABEL_18:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        (unsigned int)&WPP_bc9beace3504374faa5adebceb123de4_Traceguids,
        v17,
        (__int64)v19,
        Instance);
LABEL_19:
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_51;
    }
    goto LABEL_51;
  }
  v7 = 1;
  v20 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *))(*(_QWORD *)a2 + 208LL))(
          a2,
          L"RdpDirectServerName",
          22,
          &v86);
  Instance = MapXResultToHR(v20);
  if ( Instance >= 0 )
  {
    v21 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *))(*(_QWORD *)a2 + 72LL))(
            a2,
            L"RdpDirectServerTcpPort",
            &v82);
    Instance = MapXResultToHR(v21);
    if ( Instance < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = RdpX_GetActivityIdPrefix(v10, v9, v11);
          v18 = 14;
          v19 = "Failed to get Server port";
          goto LABEL_18;
        }
        goto LABEL_51;
      }
LABEL_58:
      OleUninitialize();
      goto LABEL_59;
    }
    v22 = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *))(*(_QWORD *)a2 + 208LL))(
           a2,
           L"RdpDirectSrvRedirectedAddresses",
           134,
           &v84)
      && v84 )
    {
      RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v84);
      v84 = 0;
      RdpXSPtr<RdpXInterfaceTapProtocolServerEvents>::SafeAddRef(&v84);
    }
    if ( (*(unsigned int (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"RdpHvSocketEnabled",
           &v83) )
    {
      v23 = 0;
      v83 = 0;
    }
    else
    {
      v23 = v83;
    }
    if ( v23 == 1
      && !(*(unsigned int (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *))(*(_QWORD *)a2 + 208LL))(
            a2,
            L"RdpHvSocketServiceId",
            22,
            &v85) )
    {
      v24 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v85 + 24LL))(v85);
      StringCchCopyW(v93, 0x27u, v24);
      v22 = 1;
    }
    v25 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 24LL))(v86);
    StringCchCopyW(StringUuid, 0x200u, v25);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v29 = v82;
      v30 = RdpX_GetActivityIdPrefix(v27, v26, v28);
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)&WPP_bc9beace3504374faa5adebceb123de4_Traceguids,
        v30,
        (__int64)StringUuid,
        v29);
    }
    Instance = CRDPENCConnectorStringSerializer::InitializeInstance((CRDPENCConnectorStringSerializer *)v91);
    if ( Instance < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v31 = RdpX_GetActivityIdPrefix(v10, v9, v11);
        v32 = 16;
        v33 = "Failed to initialize serializer";
LABEL_48:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v32,
          (unsigned int)&WPP_bc9beace3504374faa5adebceb123de4_Traceguids,
          v31,
          (__int64)v33,
          Instance);
LABEL_49:
        v12 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_50;
      }
      goto LABEL_50;
    }
    Instance = CRDPENCConnectorStringSerializer::SetConnectorId((CRDPENCConnectorStringSerializer *)v91, 1u);
    if ( Instance < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v31 = RdpX_GetActivityIdPrefix(v10, v9, v11);
        v32 = 17;
        v33 = "Failed to set the connector Id";
        goto LABEL_48;
      }
LABEL_50:
      v6 = a1;
      goto LABEL_51;
    }
    Instance = CRDPENCConnectorStringSerializer::SetSessionId((CRDPENCConnectorStringSerializer *)v91, 0);
    if ( Instance < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v31 = RdpX_GetActivityIdPrefix(v10, v9, v11);
        v32 = 18;
        v33 = "Failed to set the session Id";
        goto LABEL_48;
      }
      goto LABEL_50;
    }
    v37 = 0;
    if ( v84 )
    {
      v43 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v84 + 32LL))(v84);
      for ( i = 0; ; ++i )
      {
        if ( i >= v43 )
          goto LABEL_89;
        v81 = 0;
        *(_QWORD *)&Uuid.Data1 = 0;
        RdpXSPtr<RdpXInterfaceTapProtocolServerEvents>::SafeAddRef(&Uuid);
        v45 = (*(__int64 (__fastcall **)(__int64, _QWORD, CRdpWinConnector **))(*(_QWORD *)v84 + 40LL))(v84, i, &v81);
        Instance = MapXResultToHR(v45);
        if ( Instance < 0 )
          break;
        v49 = (*(__int64 (__fastcall **)(CRdpWinConnector *, __int64, UUID *))(*(_QWORD *)v81 + 16LL))(v81, 22, &Uuid);
        Instance = MapXResultToHR(v49);
        if ( Instance < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v64 = RdpX_GetActivityIdPrefix(v51, v50, v52);
            v65 = 23;
            v66 = "No string interface on the object contained in the array";
LABEL_118:
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v65,
              (unsigned int)&WPP_bc9beace3504374faa5adebceb123de4_Traceguids,
              v64,
              (__int64)v66,
              Instance);
            goto LABEL_119;
          }
          goto LABEL_119;
        }
        v53 = (const OLECHAR *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&Uuid.Data1 + 24LL))(*(_QWORD *)&Uuid.Data1);
        v54 = SysAllocString(v53);
        v8 = v54;
        if ( !v54 )
        {
          Instance = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v63 = RdpX_GetActivityIdPrefix(v56, v55, v57);
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_bc9beace3504374faa5adebceb123de4_Traceguids, v63);
          }
          goto LABEL_108;
        }
        Instance = CRDPENCConnectorStringSerializer::AddPortMapping(
                     (CRDPENCConnectorStringSerializer *)v90,
                     v54,
                     v82,
                     0);
        if ( Instance < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v62 = RdpX_GetActivityIdPrefix(v59, v58, v60);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              (unsigned int)&WPP_bc9beace3504374faa5adebceb123de4_Traceguids,
              v62,
              (__int64)"Failed to add a redirected port mapping",
              Instance);
          }
LABEL_108:
          RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&Uuid);
          v10 = v81;
          if ( v81 )
          {
            v81 = 0;
            (*(void (__fastcall **)(CRdpWinConnector *))(*(_QWORD *)v10 + 8LL))(v10);
          }
          goto LABEL_49;
        }
        SysFreeString(v8);
        RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&Uuid);
        v61 = v81;
        if ( v81 )
        {
          v81 = 0;
          (*(void (__fastcall **)(CRdpWinConnector *))(*(_QWORD *)v61 + 8LL))(v61);
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v64 = RdpX_GetActivityIdPrefix(v47, v46, v48);
        v65 = 22;
        v66 = "Failed to add string to addresses array";
        goto LABEL_118;
      }
LABEL_119:
      RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&Uuid);
      v10 = v81;
      if ( v81 )
      {
        v81 = 0;
        (*(void (__fastcall **)(CRdpWinConnector *))(*(_QWORD *)v10 + 8LL))(v10);
      }
      v8 = 0;
      goto LABEL_49;
    }
    Uuid = 0;
    if ( v22 )
    {
      Instance = CRDPENCConnectorStringSerializer::AddPortMapping(
                   (CRDPENCConnectorStringSerializer *)v90,
                   StringUuid,
                   v82,
                   v93);
      if ( Instance < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_58;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_50;
        v31 = RdpX_GetActivityIdPrefix(v10, v9, v11);
        v32 = 19;
LABEL_77:
        v33 = "Failed to add the port mapping";
        goto LABEL_48;
      }
    }
    else
    {
      Instance = CRDPENCConnectorStringSerializer::AddPortMapping(
                   (CRDPENCConnectorStringSerializer *)v90,
                   StringUuid,
                   v82,
                   0);
      if ( Instance < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_58;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_50;
        v31 = RdpX_GetActivityIdPrefix(v10, v9, v11);
        v32 = 20;
        goto LABEL_77;
      }
    }
    if ( v83 == 1 && !UuidFromStringW(StringUuid, &Uuid) )
    {
      v37 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v41 = RdpX_GetActivityIdPrefix(v39, v38, v40);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_bc9beace3504374faa5adebceb123de4_Traceguids, v41);
      }
    }
LABEL_89:
    Instance = CRDPENCConnectorStringSerializer::XMLSerialize((CRDPENCConnectorStringSerializer *)v91, &v87);
    if ( Instance < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v42 = RdpX_GetActivityIdPrefix(v10, v9, v11);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)&WPP_bc9beace3504374faa5adebceb123de4_Traceguids,
          v42,
          (__int64)"Failed to serialize the string",
          Instance);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      v8 = 0;
      goto LABEL_50;
    }
    v6 = a1;
    v67 = (struct IUnknown **)(a1 + 72);
    Instance = RDPLOCAL_CreateInstance(0, &CLSID_RDPRuntimeFTContext, &IID_IRDPENCPlatformContext, (void **)(a1 + 72));
    if ( Instance < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v68 = RdpX_GetActivityIdPrefix(v10, v9, v11);
        v69 = 27;
        v70 = "Failed to create the global context";
LABEL_131:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v69,
          (unsigned int)&WPP_bc9beace3504374faa5adebceb123de4_Traceguids,
          v68,
          (__int64)v70,
          Instance);
        v12 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_132;
      }
      goto LABEL_132;
    }
    Instance = ((__int64 (__fastcall *)(struct IUnknown *))(*v67)->lpVtbl[4].QueryInterface)(*v67);
    if ( Instance < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v68 = RdpX_GetActivityIdPrefix(v10, v9, v11);
        v69 = 28;
        v70 = "Failed to initialize the platform context";
        goto LABEL_131;
      }
LABEL_132:
      v8 = 0;
      goto LABEL_51;
    }
    if ( (unsigned int)CRdpWinConnector::IsRequiredCheckLoopback(v10) == 1 )
      ((void (__fastcall *)(struct IUnknown *, const wchar_t *, __int64))(*v67)->lpVtbl[2].Release)(
        *v67,
        L"RequireCheckLoopback",
        1);
    v71 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, __int64))(*v67)->lpVtbl[2].Release)(
            *v67,
            L"Tcp::UseIPV6LinkLocal",
            1);
    v74 = v71;
    if ( v71 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v75 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v72, v73);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_bc9beace3504374faa5adebceb123de4_Traceguids,
        v75,
        (__int64)"Failed to enable usage of IPV6 link-local addresses",
        v74);
    }
    v76 = *v67;
    v77 = (void **)(a1 + 80);
    if ( v37 )
    {
      *(_DWORD *)(a1 + 96) = 1;
      Instance = RDPLOCAL_CreateInstance(v76, &CLSID_RDPENCHvDirectConnector, &IID_IRDPENCTcpOutboundConnector, v77);
      if ( Instance < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_58;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_132;
        v68 = RdpX_GetActivityIdPrefix(v10, v9, v11);
        v69 = 30;
LABEL_151:
        v70 = "Failed to create the TCP connector";
        goto LABEL_131;
      }
    }
    else
    {
      Instance = RDPLOCAL_CreateInstance(v76, &CLSID_RDPENCTcpDirectConnector, &IID_IRDPENCTcpOutboundConnector, v77);
      if ( Instance < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_58;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_132;
        v68 = RdpX_GetActivityIdPrefix(v10, v9, v11);
        v69 = 31;
        goto LABEL_151;
      }
    }
    v78 = v89;
    *(_QWORD *)(a1 + 64) = v88;
    RdpXSPtr<RdpXTapProtocolString>::operator=(a1 + 88, v78);
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int16 *, __int64, _QWORD))(**(_QWORD **)(a1 + 80) + 24LL))(
                 *(_QWORD *)(a1 + 80),
                 0,
                 200,
                 v87,
                 (a1 + 8) & -(__int64)(a1 != 0),
                 0);
    if ( Instance < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_132;
      v79 = RdpX_GetActivityIdPrefix(v10, v9, v11);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_bc9beace3504374faa5adebceb123de4_Traceguids,
        v79,
        (__int64)"Failed to init the direct connector",
        Instance);
    }
    v8 = 0;
    goto LABEL_19;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_58;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = RdpX_GetActivityIdPrefix(v10, v9, v11);
    v18 = 13;
    v19 = "Failed to get ServerName";
    goto LABEL_18;
  }
LABEL_51:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x800) != 0 && *((_BYTE *)v12 + 25) >= 4u )
  {
    v34 = *(_QWORD *)(v6 + 88);
    v35 = RdpX_GetActivityIdPrefix(v10, v9, v11);
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_bc9beace3504374faa5adebceb123de4_Traceguids, v35, v34);
  }
  if ( v8 )
    SysFreeString(v8);
  if ( v7 )
    goto LABEL_58;
LABEL_59:
  RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v85);
  RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v84);
  CRDPENCConnectorStringSerializer::~CRDPENCConnectorStringSerializer((CRDPENCConnectorStringSerializer *)v90);
  RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v86);
  return MapHRToXResult((unsigned int)Instance);
}

```

## disassembly

```asm
0x1400f6830  mov     [rsp-8+arg_18], rbx
0x1400f6835  push    rbp
0x1400f6836  push    rsi
0x1400f6837  push    rdi
0x1400f6838  push    r12
0x1400f683a  push    r13
0x1400f683c  push    r14
0x1400f683e  push    r15
0x1400f6840  lea     rbp, [rsp-450h]
0x1400f6848  sub     rsp, 550h
0x1400f684f  mov     rax, cs:__security_cookie
0x1400f6856  xor     rax, rsp
0x1400f6859  mov     [rbp+480h+var_40], rax
0x1400f6860  mov     rdi, r8
0x1400f6863  mov     [rbp+480h+var_500], r8
0x1400f6867  mov     rbx, rdx
0x1400f686a  mov     [rsp+580h+var_540], rcx
0x1400f686f  mov     r15, rcx
0x1400f6872  mov     [rsp+580h+var_508], r9
0x1400f6877  xor     edx, edx; Val
0x1400f6879  lea     rcx, [rbp+480h+StringUuid]; void *
0x1400f687d  mov     r8d, 400h; Size
0x1400f6883  call    memset_0
0x1400f6888  lea     rcx, [rbp+480h+var_4F0]; this
0x1400f688c  mov     [rsp+580h+var_530], 0
0x1400f6894  mov     [rsp+580h+var_518], 0
0x1400f689d  call    ??0CRDPENCConnectorStringSerializer@@QEAA@XZ; CRDPENCConnectorStringSerializer::CRDPENCConnectorStringSerializer(void)
0x1400f68a2  xor     r13d, r13d
0x1400f68a5  mov     [rsp+580h+var_510], 0
0x1400f68ae  lea     rcx, [rsp+580h+var_528]
0x1400f68b3  mov     [rsp+580h+var_528], r13
0x1400f68b8  call    ?SafeAddRef@?$RdpXSPtr@URdpXInterfaceTapProtocolServerEvents@@@@AEAAXXZ; RdpXSPtr<RdpXInterfaceTapProtocolServerEvents>::SafeAddRef(void)
0x1400f68bd  xor     edx, edx; Val
0x1400f68bf  lea     r8d, [r13+4Eh]; Size
0x1400f68c3  lea     rcx, [rbp+480h+var_490]; void *
0x1400f68c7  xor     r14d, r14d
0x1400f68ca  call    memset_0
0x1400f68cf  mov     [rsp+580h+var_520], r13
0x1400f68d4  mov     [rsp+580h+var_52C], r13d
0x1400f68d9  test    rbx, rbx
0x1400f68dc  jnz     short loc_1400F693C
0x1400f68de  mov     rax, cs:WPP_GLOBAL_Control
0x1400f68e5  lea     rsi, WPP_GLOBAL_Control
0x1400f68ec  cmp     rax, rsi
0x1400f68ef  jz      short loc_1400F6932
0x1400f68f1  test    byte ptr [rax+1Ch], 8
0x1400f68f5  jz      short loc_1400F6932
0x1400f68f7  cmp     byte ptr [rax+19h], 2
0x1400f68fb  jb      short loc_1400F6932
0x1400f68fd  call    RdpX_GetActivityIdPrefix
0x1400f6902  lea     edx, [rbx+0Ah]
0x1400f6905  lea     rcx, aPtransportprop; "pTransportProps"
0x1400f690c  mov     [rsp+580h+var_560], rcx
0x1400f6911  lea     r8, WPP_bc9beace3504374faa5adebceb123de4_Traceguids
0x1400f6918  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f691f  mov     r9d, eax
0x1400f6922  mov     rcx, [rcx+10h]
0x1400f6926  call    WPP_SF_Ds
0x1400f692b  mov     rax, cs:WPP_GLOBAL_Control
0x1400f6932  mov     edi, 80004003h
0x1400f6937  jmp     loc_1400F6C78
0x1400f693c  test    rdi, rdi
0x1400f693f  jnz     short loc_1400F6971
0x1400f6941  mov     rax, cs:WPP_GLOBAL_Control
0x1400f6948  lea     rsi, WPP_GLOBAL_Control
0x1400f694f  cmp     rax, rsi
0x1400f6952  jz      short loc_1400F6932
0x1400f6954  test    byte ptr [rax+1Ch], 8
0x1400f6958  jz      short loc_1400F6932
0x1400f695a  cmp     byte ptr [rax+19h], 2
0x1400f695e  jb      short loc_1400F6932
0x1400f6960  call    RdpX_GetActivityIdPrefix
0x1400f6965  lea     edx, [rdi+0Bh]
0x1400f6968  lea     rcx, aPtransporteven; "pTransportEvents"
0x1400f696f  jmp     short loc_1400F690C
0x1400f6971  xor     ecx, ecx; pvReserved
0x1400f6973  call    cs:__imp_OleInitialize
0x1400f6979  mov     edi, eax
0x1400f697b  test    eax, eax
0x1400f697d  jns     short loc_1400F69EA
0x1400f697f  mov     rax, cs:WPP_GLOBAL_Control
0x1400f6986  lea     rsi, WPP_GLOBAL_Control
0x1400f698d  cmp     rax, rsi
0x1400f6990  jz      loc_1400F6CD2
0x1400f6996  test    byte ptr [rax+1Ch], 8
0x1400f699a  jz      loc_1400F6C78
0x1400f69a0  cmp     byte ptr [rax+19h], 2
0x1400f69a4  jb      loc_1400F6C78
0x1400f69aa  call    RdpX_GetActivityIdPrefix
0x1400f69af  mov     edx, 0Ch
0x1400f69b4  lea     rcx, aOleinitializeF; "OleInitialize from WinConnector failed!"
0x1400f69bb  mov     dword ptr [rsp+580h+var_558], edi
0x1400f69bf  lea     r8, WPP_bc9beace3504374faa5adebceb123de4_Traceguids
0x1400f69c6  mov     [rsp+580h+var_560], rcx
0x1400f69cb  mov     r9d, eax
0x1400f69ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f69d5  mov     rcx, [rcx+10h]
0x1400f69d9  call    WPP_SF_DsD
0x1400f69de  mov     rax, cs:WPP_GLOBAL_Control
0x1400f69e5  jmp     loc_1400F6C78
0x1400f69ea  mov     rax, [rbx]
0x1400f69ed  lea     r9, [rsp+580h+var_518]
0x1400f69f2  mov     r13d, 1
0x1400f69f8  lea     rdx, aRdpdirectserve; "RdpDirectServerName"
0x1400f69ff  mov     rcx, rbx
0x1400f6a02  mov     rax, [rax+0D0h]
0x1400f6a09  lea     esi, [r13+15h]
0x1400f6a0d  mov     r8d, esi
0x1400f6a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f6a15  mov     ecx, eax
0x1400f6a17  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1400f6a1c  mov     edi, eax
0x1400f6a1e  test    eax, eax
0x1400f6a20  jns     short loc_1400F6A62
0x1400f6a22  mov     rax, cs:WPP_GLOBAL_Control
0x1400f6a29  lea     rsi, WPP_GLOBAL_Control
0x1400f6a30  cmp     rax, rsi
0x1400f6a33  jz      loc_1400F6CCC
0x1400f6a39  test    byte ptr [rax+1Ch], 8
0x1400f6a3d  jz      loc_1400F6C78
0x1400f6a43  cmp     byte ptr [rax+19h], 2
0x1400f6a47  jb      loc_1400F6C78
0x1400f6a4d  call    RdpX_GetActivityIdPrefix
0x1400f6a52  lea     edx, [r13+0Ch]
0x1400f6a56  lea     rcx, aFailedToGetSer; "Failed to get ServerName"
0x1400f6a5d  jmp     loc_1400F69BB
0x1400f6a62  mov     rax, [rbx]
0x1400f6a65  lea     r8, [rsp+580h+var_530]
0x1400f6a6a  lea     rdx, aRdpdirectserve_0; "RdpDirectServerTcpPort"
0x1400f6a71  mov     rcx, rbx
0x1400f6a74  mov     rax, [rax+48h]
0x1400f6a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f6a7d  mov     ecx, eax
0x1400f6a7f  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1400f6a84  mov     edi, eax
0x1400f6a86  test    eax, eax
0x1400f6a88  jns     short loc_1400F6ACB
0x1400f6a8a  mov     rax, cs:WPP_GLOBAL_Control
0x1400f6a91  lea     rsi, WPP_GLOBAL_Control
0x1400f6a98  cmp     rax, rsi
0x1400f6a9b  jz      loc_1400F6CCC
0x1400f6aa1  test    byte ptr [rax+1Ch], 8
0x1400f6aa5  jz      loc_1400F6C78
0x1400f6aab  cmp     byte ptr [rax+19h], 2
0x1400f6aaf  jb      loc_1400F6C78
0x1400f6ab5  call    RdpX_GetActivityIdPrefix
0x1400f6aba  mov     edx, 0Eh
0x1400f6abf  lea     rcx, aFailedToGetSer_0; "Failed to get Server port"
0x1400f6ac6  jmp     loc_1400F69BB
0x1400f6acb  mov     rax, [rbx]
0x1400f6ace  lea     r9, [rsp+580h+var_528]
0x1400f6ad3  mov     r8d, 86h
0x1400f6ad9  lea     rdx, aRdpdirectsrvre; "RdpDirectSrvRedirectedAddresses"
0x1400f6ae0  mov     rcx, rbx
0x1400f6ae3  xor     r15b, r15b
0x1400f6ae6  mov     rax, [rax+0D0h]
0x1400f6aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f6af2  test    eax, eax
0x1400f6af4  jz      short loc_1400F6B16
0x1400f6af6  cmp     [rsp+580h+var_528], r14
0x1400f6afb  jz      short loc_1400F6B16
0x1400f6afd  lea     rcx, [rsp+580h+var_528]
0x1400f6b02  call    ?SafeRelease@?$RdpXSPtr@VRdpXTapVcCallbackItem@@@@AEAAXXZ; RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(void)
0x1400f6b07  lea     rcx, [rsp+580h+var_528]
0x1400f6b0c  mov     [rsp+580h+var_528], r14
0x1400f6b11  call    ?SafeAddRef@?$RdpXSPtr@URdpXInterfaceTapProtocolServerEvents@@@@AEAAXXZ; RdpXSPtr<RdpXInterfaceTapProtocolServerEvents>::SafeAddRef(void)
0x1400f6b16  mov     rax, [rbx]
0x1400f6b19  lea     r8, [rsp+580h+var_52C]
0x1400f6b1e  lea     rdx, aRdphvsocketena; "RdpHvSocketEnabled"
0x1400f6b25  mov     rcx, rbx
0x1400f6b28  mov     rax, [rax+18h]
0x1400f6b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f6b31  test    eax, eax
0x1400f6b33  jz      short loc_1400F6B3D
0x1400f6b35  xor     eax, eax
0x1400f6b37  mov     [rsp+580h+var_52C], eax
0x1400f6b3b  jmp     short loc_1400F6B41
0x1400f6b3d  mov     eax, [rsp+580h+var_52C]
0x1400f6b41  cmp     eax, r13d
0x1400f6b44  jnz     short loc_1400F6B90
0x1400f6b46  mov     rax, [rbx]
0x1400f6b49  lea     r9, [rsp+580h+var_520]
0x1400f6b4e  mov     r8d, esi
0x1400f6b51  lea     rdx, aRdphvsocketser; "RdpHvSocketServiceId"
0x1400f6b58  mov     rcx, rbx
0x1400f6b5b  mov     rax, [rax+0D0h]
0x1400f6b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f6b67  test    eax, eax
0x1400f6b69  jnz     short loc_1400F6B90
0x1400f6b6b  mov     rcx, [rsp+580h+var_520]
0x1400f6b70  mov     rax, [rcx]
0x1400f6b73  mov     rax, [rax+18h]
0x1400f6b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f6b7c  mov     r8, rax; unsigned __int16 *
0x1400f6b7f  lea     rcx, [rbp+480h+var_490]; unsigned __int16 *
0x1400f6b83  mov     edx, 27h ; '''; unsigned __int64
0x1400f6b88  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400f6b8d  mov     r15b, r13b
0x1400f6b90  mov     rcx, [rsp+580h+var_518]
0x1400f6b95  mov     rax, [rcx]
0x1400f6b98  mov     rax, [rax+18h]
0x1400f6b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f6ba1  mov     r8, rax; unsigned __int16 *
0x1400f6ba4  lea     rcx, [rbp+480h+StringUuid]; unsigned __int16 *
0x1400f6ba8  mov     edx, 200h; unsigned __int64
0x1400f6bad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400f6bb2  mov     rax, cs:WPP_GLOBAL_Control
0x1400f6bb9  lea     rsi, WPP_GLOBAL_Control
0x1400f6bc0  cmp     rax, rsi
0x1400f6bc3  jz      short loc_1400F6C09
0x1400f6bc5  test    dword ptr [rax+1Ch], 800h
0x1400f6bcc  jz      short loc_1400F6C09
0x1400f6bce  cmp     byte ptr [rax+19h], 4
0x1400f6bd2  jb      short loc_1400F6C09
0x1400f6bd4  mov     ebx, [rsp+580h+var_530]
0x1400f6bd8  call    RdpX_GetActivityIdPrefix
0x1400f6bdd  lea     rcx, [rbp+480h+StringUuid]
0x1400f6be1  mov     dword ptr [rsp+580h+var_558], ebx
0x1400f6be5  mov     [rsp+580h+var_560], rcx
0x1400f6bea  lea     r8, WPP_bc9beace3504374faa5adebceb123de4_Traceguids
0x1400f6bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f6bf8  mov     edx, 0Fh
0x1400f6bfd  mov     r9d, eax
0x1400f6c00  mov     rcx, [rcx+10h]
0x1400f6c04  call    WPP_SF_DSd
0x1400f6c09  lea     rcx, [rbp+480h+var_4C0]; this
0x1400f6c0d  call    ?InitializeInstance@CRDPENCConnectorStringSerializer@@UEAAJXZ; CRDPENCConnectorStringSerializer::InitializeInstance(void)
0x1400f6c12  mov     edi, eax
0x1400f6c14  test    eax, eax
0x1400f6c16  jns     loc_1400F6D2A
0x1400f6c1c  mov     rax, cs:WPP_GLOBAL_Control
0x1400f6c23  cmp     rax, rsi
0x1400f6c26  jz      loc_1400F6CCC
0x1400f6c2c  test    byte ptr [rax+1Ch], 8
0x1400f6c30  jz      short loc_1400F6C73
0x1400f6c32  cmp     byte ptr [rax+19h], 2
0x1400f6c36  jb      short loc_1400F6C73
0x1400f6c38  call    RdpX_GetActivityIdPrefix
0x1400f6c3d  mov     edx, 10h
0x1400f6c42  lea     rcx, aFailedToInitia_37; "Failed to initialize serializer"
0x1400f6c49  mov     dword ptr [rsp+580h+var_558], edi
0x1400f6c4d  lea     r8, WPP_bc9beace3504374faa5adebceb123de4_Traceguids
0x1400f6c54  mov     [rsp+580h+var_560], rcx
0x1400f6c59  mov     r9d, eax
0x1400f6c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f6c63  mov     rcx, [rcx+10h]
0x1400f6c67  call    WPP_SF_DsD
0x1400f6c6c  mov     rax, cs:WPP_GLOBAL_Control
0x1400f6c73  mov     r15, [rsp+580h+var_540]
0x1400f6c78  cmp     rax, rsi
0x1400f6c7b  jz      short loc_1400F6CB9
0x1400f6c7d  test    dword ptr [rax+1Ch], 800h
0x1400f6c84  jz      short loc_1400F6CB9
0x1400f6c86  cmp     byte ptr [rax+19h], 4
0x1400f6c8a  jb      short loc_1400F6CB9
0x1400f6c8c  mov     rbx, [r15+58h]
0x1400f6c90  call    RdpX_GetActivityIdPrefix
0x1400f6c95  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f6c9c  lea     r8, WPP_bc9beace3504374faa5adebceb123de4_Traceguids
0x1400f6ca3  mov     edx, 21h ; '!'
0x1400f6ca8  mov     [rsp+580h+var_560], rbx
0x1400f6cad  mov     r9d, eax
0x1400f6cb0  mov     rcx, [rcx+10h]
0x1400f6cb4  call    WPP_SF_Dq
0x1400f6cb9  test    r14, r14
0x1400f6cbc  jz      short loc_1400F6CC7
0x1400f6cbe  mov     rcx, r14; bstrString
0x1400f6cc1  call    cs:__imp_SysFreeString
0x1400f6cc7  test    r13d, r13d
0x1400f6cca  jz      short loc_1400F6CD2
0x1400f6ccc  call    cs:__imp_OleUninitialize
0x1400f6cd2  lea     rcx, [rsp+580h+var_520]
0x1400f6cd7  call    ?SafeRelease@?$RdpXSPtr@VRdpXTapVcCallbackItem@@@@AEAAXXZ; RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(void)
0x1400f6cdc  lea     rcx, [rsp+580h+var_528]
0x1400f6ce1  call    ?SafeRelease@?$RdpXSPtr@VRdpXTapVcCallbackItem@@@@AEAAXXZ; RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(void)
0x1400f6ce6  lea     rcx, [rbp+480h+var_4F0]; this
0x1400f6cea  call    ??1CRDPENCConnectorStringSerializer@@UEAA@XZ; CRDPENCConnectorStringSerializer::~CRDPENCConnectorStringSerializer(void)
0x1400f6cef  lea     rcx, [rsp+580h+var_518]
0x1400f6cf4  call    ?SafeRelease@?$RdpXSPtr@VRdpXTapVcCallbackItem@@@@AEAAXXZ; RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(void)
0x1400f6cf9  mov     ecx, edi
0x1400f6cfb  call    ?MapHRToXResult@@YA?AW4_XResult32@@J@Z; MapHRToXResult(long)
0x1400f6d00  mov     rcx, [rbp+480h+var_40]
0x1400f6d07  xor     rcx, rsp; StackCookie
0x1400f6d0a  call    __security_check_cookie
0x1400f6d0f  mov     rbx, [rsp+580h+arg_18]
0x1400f6d17  add     rsp, 550h
0x1400f6d1e  pop     r15
0x1400f6d20  pop     r14
0x1400f6d22  pop     r13
0x1400f6d24  pop     r12
0x1400f6d26  pop     rdi
0x1400f6d27  pop     rsi
0x1400f6d28  pop     rbp
0x1400f6d29  retn
0x1400f6d2a  mov     edx, r13d; unsigned int
0x1400f6d2d  lea     rcx, [rbp+480h+var_4C0]; this
0x1400f6d31  call    ?SetConnectorId@CRDPENCConnectorStringSerializer@@UEAAJK@Z; CRDPENCConnectorStringSerializer::SetConnectorId(ulong)
0x1400f6d36  mov     edi, eax
0x1400f6d38  test    eax, eax
0x1400f6d3a  jns     short loc_1400F6D72
  ... truncated ...
```
