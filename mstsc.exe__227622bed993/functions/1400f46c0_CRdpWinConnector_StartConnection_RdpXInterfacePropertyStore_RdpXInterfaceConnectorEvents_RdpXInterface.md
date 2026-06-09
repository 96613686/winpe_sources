# CRdpWinConnector::StartConnection(RdpXInterfacePropertyStore *,RdpXInterfaceConnectorEvents *,RdpXInterface *)

- ea: `0x1400f46c0`
- end: `0x1400f52f0`
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
- `0x14005a1a8`
- `0x14005c6d8`
- `0x140061a00`
- `0x1400620e8`
- `0x14006f870`
- `0x14006f8dc`
- `0x14006f9d8`
- `0x14006ff70`
- `0x140070100`
- `0x140070180`
- `0x1400705c0`
- `0x1400a013c`
- `0x1400b3210`
- `0x1400f3b68`
- `0x1400f46c0`
- `0x140107998`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `ole32!OleInitialize` at `0x1400f4803`
- `ole32!OleInitialize` at `0x1400f4803`
- `ole32!OleUninitialize` at `0x1400f4b5c`
- `ole32!OleUninitialize` at `0x1400f4b5c`
- `OLEAUT32!__imp_SysAllocString` at `0x1400f4e6b`
- `OLEAUT32!__imp_SysAllocString` at `0x1400f4e6b`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f4b51`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f4e9a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f4b51`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f4e9a`
- `RPCRT4!UuidFromStringW` at `0x1400f4d0d`
- `RPCRT4!UuidFromStringW` at `0x1400f4d0d`

## string_xrefs

- `0x1400f512a`: `Tcp::UseIPV6LinkLocal`
- `0x1400f5087`: `Failed to create the global context`
- `0x1400f49e1`: `RdpHvSocketServiceId`
- `0x1400f51ec`: `Failed to create the TCP connector`
- `0x1400f5163`: `Failed to enable usage of IPV6 link-local addresses`

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
0x1400f46c0  mov     [rsp-8+arg_18], rbx
0x1400f46c5  push    rbp
0x1400f46c6  push    rsi
0x1400f46c7  push    rdi
0x1400f46c8  push    r12
0x1400f46ca  push    r13
0x1400f46cc  push    r14
0x1400f46ce  push    r15
0x1400f46d0  lea     rbp, [rsp-450h]
0x1400f46d8  sub     rsp, 550h
0x1400f46df  mov     rax, cs:__security_cookie
0x1400f46e6  xor     rax, rsp
0x1400f46e9  mov     [rbp+480h+var_40], rax
0x1400f46f0  mov     rdi, r8
0x1400f46f3  mov     [rbp+480h+var_500], r8
0x1400f46f7  mov     rbx, rdx
0x1400f46fa  mov     [rsp+580h+var_540], rcx
0x1400f46ff  mov     r15, rcx
0x1400f4702  mov     [rsp+580h+var_508], r9
0x1400f4707  xor     edx, edx; Val
0x1400f4709  lea     rcx, [rbp+480h+StringUuid]; void *
0x1400f470d  mov     r8d, 400h; Size
0x1400f4713  call    memset_0
0x1400f4718  lea     rcx, [rbp+480h+var_4F0]; this
0x1400f471c  mov     [rsp+580h+var_530], 0
0x1400f4724  mov     [rsp+580h+var_518], 0
0x1400f472d  call    ??0CRDPENCConnectorStringSerializer@@QEAA@XZ; CRDPENCConnectorStringSerializer::CRDPENCConnectorStringSerializer(void)
0x1400f4732  xor     r13d, r13d
0x1400f4735  mov     [rsp+580h+var_510], 0
0x1400f473e  lea     rcx, [rsp+580h+var_528]
0x1400f4743  mov     [rsp+580h+var_528], r13
0x1400f4748  call    ?SafeAddRef@?$RdpXSPtr@URdpXInterfaceTapProtocolServerEvents@@@@AEAAXXZ; RdpXSPtr<RdpXInterfaceTapProtocolServerEvents>::SafeAddRef(void)
0x1400f474d  xor     edx, edx; Val
0x1400f474f  lea     r8d, [r13+4Eh]; Size
0x1400f4753  lea     rcx, [rbp+480h+var_490]; void *
0x1400f4757  xor     r14d, r14d
0x1400f475a  call    memset_0
0x1400f475f  mov     [rsp+580h+var_520], r13
0x1400f4764  mov     [rsp+580h+var_52C], r13d
0x1400f4769  test    rbx, rbx
0x1400f476c  jnz     short loc_1400F47CC
0x1400f476e  mov     rax, cs:WPP_GLOBAL_Control
0x1400f4775  lea     rsi, WPP_GLOBAL_Control
0x1400f477c  cmp     rax, rsi
0x1400f477f  jz      short loc_1400F47C2
0x1400f4781  test    byte ptr [rax+1Ch], 8
0x1400f4785  jz      short loc_1400F47C2
0x1400f4787  cmp     byte ptr [rax+19h], 2
0x1400f478b  jb      short loc_1400F47C2
0x1400f478d  call    RdpX_GetActivityIdPrefix
0x1400f4792  lea     edx, [rbx+0Ah]
0x1400f4795  lea     rcx, aPtransportprop; "pTransportProps"
0x1400f479c  mov     [rsp+580h+var_560], rcx
0x1400f47a1  lea     r8, WPP_bc9beace3504374faa5adebceb123de4_Traceguids
0x1400f47a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f47af  mov     r9d, eax
0x1400f47b2  mov     rcx, [rcx+10h]
0x1400f47b6  call    WPP_SF_Ds
0x1400f47bb  mov     rax, cs:WPP_GLOBAL_Control
0x1400f47c2  mov     edi, 80004003h
0x1400f47c7  jmp     loc_1400F4B08
0x1400f47cc  test    rdi, rdi
0x1400f47cf  jnz     short loc_1400F4801
0x1400f47d1  mov     rax, cs:WPP_GLOBAL_Control
0x1400f47d8  lea     rsi, WPP_GLOBAL_Control
0x1400f47df  cmp     rax, rsi
0x1400f47e2  jz      short loc_1400F47C2
0x1400f47e4  test    byte ptr [rax+1Ch], 8
0x1400f47e8  jz      short loc_1400F47C2
0x1400f47ea  cmp     byte ptr [rax+19h], 2
0x1400f47ee  jb      short loc_1400F47C2
0x1400f47f0  call    RdpX_GetActivityIdPrefix
0x1400f47f5  lea     edx, [rdi+0Bh]
0x1400f47f8  lea     rcx, aPtransporteven; "pTransportEvents"
0x1400f47ff  jmp     short loc_1400F479C
0x1400f4801  xor     ecx, ecx; pvReserved
0x1400f4803  call    cs:__imp_OleInitialize
0x1400f4809  mov     edi, eax
0x1400f480b  test    eax, eax
0x1400f480d  jns     short loc_1400F487A
0x1400f480f  mov     rax, cs:WPP_GLOBAL_Control
0x1400f4816  lea     rsi, WPP_GLOBAL_Control
0x1400f481d  cmp     rax, rsi
0x1400f4820  jz      loc_1400F4B62
0x1400f4826  test    byte ptr [rax+1Ch], 8
0x1400f482a  jz      loc_1400F4B08
0x1400f4830  cmp     byte ptr [rax+19h], 2
0x1400f4834  jb      loc_1400F4B08
0x1400f483a  call    RdpX_GetActivityIdPrefix
0x1400f483f  mov     edx, 0Ch
0x1400f4844  lea     rcx, aOleinitializeF; "OleInitialize from WinConnector failed!"
0x1400f484b  mov     dword ptr [rsp+580h+var_558], edi
0x1400f484f  lea     r8, WPP_bc9beace3504374faa5adebceb123de4_Traceguids
0x1400f4856  mov     [rsp+580h+var_560], rcx
0x1400f485b  mov     r9d, eax
0x1400f485e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f4865  mov     rcx, [rcx+10h]
0x1400f4869  call    WPP_SF_DsD
0x1400f486e  mov     rax, cs:WPP_GLOBAL_Control
0x1400f4875  jmp     loc_1400F4B08
0x1400f487a  mov     rax, [rbx]
0x1400f487d  lea     r9, [rsp+580h+var_518]
0x1400f4882  mov     r13d, 1
0x1400f4888  lea     rdx, aRdpdirectserve; "RdpDirectServerName"
0x1400f488f  mov     rcx, rbx
0x1400f4892  mov     rax, [rax+0D0h]
0x1400f4899  lea     esi, [r13+15h]
0x1400f489d  mov     r8d, esi
0x1400f48a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f48a5  mov     ecx, eax
0x1400f48a7  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1400f48ac  mov     edi, eax
0x1400f48ae  test    eax, eax
0x1400f48b0  jns     short loc_1400F48F2
0x1400f48b2  mov     rax, cs:WPP_GLOBAL_Control
0x1400f48b9  lea     rsi, WPP_GLOBAL_Control
0x1400f48c0  cmp     rax, rsi
0x1400f48c3  jz      loc_1400F4B5C
0x1400f48c9  test    byte ptr [rax+1Ch], 8
0x1400f48cd  jz      loc_1400F4B08
0x1400f48d3  cmp     byte ptr [rax+19h], 2
0x1400f48d7  jb      loc_1400F4B08
0x1400f48dd  call    RdpX_GetActivityIdPrefix
0x1400f48e2  lea     edx, [r13+0Ch]
0x1400f48e6  lea     rcx, aFailedToGetSer; "Failed to get ServerName"
0x1400f48ed  jmp     loc_1400F484B
0x1400f48f2  mov     rax, [rbx]
0x1400f48f5  lea     r8, [rsp+580h+var_530]
0x1400f48fa  lea     rdx, aRdpdirectserve_0; "RdpDirectServerTcpPort"
0x1400f4901  mov     rcx, rbx
0x1400f4904  mov     rax, [rax+48h]
0x1400f4908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f490d  mov     ecx, eax
0x1400f490f  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1400f4914  mov     edi, eax
0x1400f4916  test    eax, eax
0x1400f4918  jns     short loc_1400F495B
0x1400f491a  mov     rax, cs:WPP_GLOBAL_Control
0x1400f4921  lea     rsi, WPP_GLOBAL_Control
0x1400f4928  cmp     rax, rsi
0x1400f492b  jz      loc_1400F4B5C
0x1400f4931  test    byte ptr [rax+1Ch], 8
0x1400f4935  jz      loc_1400F4B08
0x1400f493b  cmp     byte ptr [rax+19h], 2
0x1400f493f  jb      loc_1400F4B08
0x1400f4945  call    RdpX_GetActivityIdPrefix
0x1400f494a  mov     edx, 0Eh
0x1400f494f  lea     rcx, aFailedToGetSer_0; "Failed to get Server port"
0x1400f4956  jmp     loc_1400F484B
0x1400f495b  mov     rax, [rbx]
0x1400f495e  lea     r9, [rsp+580h+var_528]
0x1400f4963  mov     r8d, 86h
0x1400f4969  lea     rdx, aRdpdirectsrvre; "RdpDirectSrvRedirectedAddresses"
0x1400f4970  mov     rcx, rbx
0x1400f4973  xor     r15b, r15b
0x1400f4976  mov     rax, [rax+0D0h]
0x1400f497d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f4982  test    eax, eax
0x1400f4984  jz      short loc_1400F49A6
0x1400f4986  cmp     [rsp+580h+var_528], r14
0x1400f498b  jz      short loc_1400F49A6
0x1400f498d  lea     rcx, [rsp+580h+var_528]
0x1400f4992  call    ?SafeRelease@?$RdpXSPtr@VRdpXTapVcCallbackItem@@@@AEAAXXZ; RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(void)
0x1400f4997  lea     rcx, [rsp+580h+var_528]
0x1400f499c  mov     [rsp+580h+var_528], r14
0x1400f49a1  call    ?SafeAddRef@?$RdpXSPtr@URdpXInterfaceTapProtocolServerEvents@@@@AEAAXXZ; RdpXSPtr<RdpXInterfaceTapProtocolServerEvents>::SafeAddRef(void)
0x1400f49a6  mov     rax, [rbx]
0x1400f49a9  lea     r8, [rsp+580h+var_52C]
0x1400f49ae  lea     rdx, aRdphvsocketena; "RdpHvSocketEnabled"
0x1400f49b5  mov     rcx, rbx
0x1400f49b8  mov     rax, [rax+18h]
0x1400f49bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f49c1  test    eax, eax
0x1400f49c3  jz      short loc_1400F49CD
0x1400f49c5  xor     eax, eax
0x1400f49c7  mov     [rsp+580h+var_52C], eax
0x1400f49cb  jmp     short loc_1400F49D1
0x1400f49cd  mov     eax, [rsp+580h+var_52C]
0x1400f49d1  cmp     eax, r13d
0x1400f49d4  jnz     short loc_1400F4A20
0x1400f49d6  mov     rax, [rbx]
0x1400f49d9  lea     r9, [rsp+580h+var_520]
0x1400f49de  mov     r8d, esi
0x1400f49e1  lea     rdx, aRdphvsocketser; "RdpHvSocketServiceId"
0x1400f49e8  mov     rcx, rbx
0x1400f49eb  mov     rax, [rax+0D0h]
0x1400f49f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f49f7  test    eax, eax
0x1400f49f9  jnz     short loc_1400F4A20
0x1400f49fb  mov     rcx, [rsp+580h+var_520]
0x1400f4a00  mov     rax, [rcx]
0x1400f4a03  mov     rax, [rax+18h]
0x1400f4a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f4a0c  mov     r8, rax; unsigned __int16 *
0x1400f4a0f  lea     rcx, [rbp+480h+var_490]; unsigned __int16 *
0x1400f4a13  mov     edx, 27h ; '''; unsigned __int64
0x1400f4a18  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400f4a1d  mov     r15b, r13b
0x1400f4a20  mov     rcx, [rsp+580h+var_518]
0x1400f4a25  mov     rax, [rcx]
0x1400f4a28  mov     rax, [rax+18h]
0x1400f4a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f4a31  mov     r8, rax; unsigned __int16 *
0x1400f4a34  lea     rcx, [rbp+480h+StringUuid]; unsigned __int16 *
0x1400f4a38  mov     edx, 200h; unsigned __int64
0x1400f4a3d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400f4a42  mov     rax, cs:WPP_GLOBAL_Control
0x1400f4a49  lea     rsi, WPP_GLOBAL_Control
0x1400f4a50  cmp     rax, rsi
0x1400f4a53  jz      short loc_1400F4A99
0x1400f4a55  test    dword ptr [rax+1Ch], 800h
0x1400f4a5c  jz      short loc_1400F4A99
0x1400f4a5e  cmp     byte ptr [rax+19h], 4
0x1400f4a62  jb      short loc_1400F4A99
0x1400f4a64  mov     ebx, [rsp+580h+var_530]
0x1400f4a68  call    RdpX_GetActivityIdPrefix
0x1400f4a6d  lea     rcx, [rbp+480h+StringUuid]
0x1400f4a71  mov     dword ptr [rsp+580h+var_558], ebx
0x1400f4a75  mov     [rsp+580h+var_560], rcx
0x1400f4a7a  lea     r8, WPP_bc9beace3504374faa5adebceb123de4_Traceguids
0x1400f4a81  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f4a88  mov     edx, 0Fh
0x1400f4a8d  mov     r9d, eax
0x1400f4a90  mov     rcx, [rcx+10h]
0x1400f4a94  call    WPP_SF_DSd
0x1400f4a99  lea     rcx, [rbp+480h+var_4C0]; this
0x1400f4a9d  call    ?InitializeInstance@CRDPENCConnectorStringSerializer@@UEAAJXZ; CRDPENCConnectorStringSerializer::InitializeInstance(void)
0x1400f4aa2  mov     edi, eax
0x1400f4aa4  test    eax, eax
0x1400f4aa6  jns     loc_1400F4BBA
0x1400f4aac  mov     rax, cs:WPP_GLOBAL_Control
0x1400f4ab3  cmp     rax, rsi
0x1400f4ab6  jz      loc_1400F4B5C
0x1400f4abc  test    byte ptr [rax+1Ch], 8
0x1400f4ac0  jz      short loc_1400F4B03
0x1400f4ac2  cmp     byte ptr [rax+19h], 2
0x1400f4ac6  jb      short loc_1400F4B03
0x1400f4ac8  call    RdpX_GetActivityIdPrefix
0x1400f4acd  mov     edx, 10h
0x1400f4ad2  lea     rcx, aFailedToInitia_37; "Failed to initialize serializer"
0x1400f4ad9  mov     dword ptr [rsp+580h+var_558], edi
0x1400f4add  lea     r8, WPP_bc9beace3504374faa5adebceb123de4_Traceguids
0x1400f4ae4  mov     [rsp+580h+var_560], rcx
0x1400f4ae9  mov     r9d, eax
0x1400f4aec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f4af3  mov     rcx, [rcx+10h]
0x1400f4af7  call    WPP_SF_DsD
0x1400f4afc  mov     rax, cs:WPP_GLOBAL_Control
0x1400f4b03  mov     r15, [rsp+580h+var_540]
0x1400f4b08  cmp     rax, rsi
0x1400f4b0b  jz      short loc_1400F4B49
0x1400f4b0d  test    dword ptr [rax+1Ch], 800h
0x1400f4b14  jz      short loc_1400F4B49
0x1400f4b16  cmp     byte ptr [rax+19h], 4
0x1400f4b1a  jb      short loc_1400F4B49
0x1400f4b1c  mov     rbx, [r15+58h]
0x1400f4b20  call    RdpX_GetActivityIdPrefix
0x1400f4b25  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f4b2c  lea     r8, WPP_bc9beace3504374faa5adebceb123de4_Traceguids
0x1400f4b33  mov     edx, 21h ; '!'
0x1400f4b38  mov     [rsp+580h+var_560], rbx
0x1400f4b3d  mov     r9d, eax
0x1400f4b40  mov     rcx, [rcx+10h]
0x1400f4b44  call    WPP_SF_Dq
0x1400f4b49  test    r14, r14
0x1400f4b4c  jz      short loc_1400F4B57
0x1400f4b4e  mov     rcx, r14; bstrString
0x1400f4b51  call    cs:__imp_SysFreeString
0x1400f4b57  test    r13d, r13d
0x1400f4b5a  jz      short loc_1400F4B62
0x1400f4b5c  call    cs:__imp_OleUninitialize
0x1400f4b62  lea     rcx, [rsp+580h+var_520]
0x1400f4b67  call    ?SafeRelease@?$RdpXSPtr@VRdpXTapVcCallbackItem@@@@AEAAXXZ; RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(void)
0x1400f4b6c  lea     rcx, [rsp+580h+var_528]
0x1400f4b71  call    ?SafeRelease@?$RdpXSPtr@VRdpXTapVcCallbackItem@@@@AEAAXXZ; RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(void)
0x1400f4b76  lea     rcx, [rbp+480h+var_4F0]; this
0x1400f4b7a  call    ??1CRDPENCConnectorStringSerializer@@UEAA@XZ; CRDPENCConnectorStringSerializer::~CRDPENCConnectorStringSerializer(void)
0x1400f4b7f  lea     rcx, [rsp+580h+var_518]
0x1400f4b84  call    ?SafeRelease@?$RdpXSPtr@VRdpXTapVcCallbackItem@@@@AEAAXXZ; RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(void)
0x1400f4b89  mov     ecx, edi
0x1400f4b8b  call    ?MapHRToXResult@@YA?AW4_XResult32@@J@Z; MapHRToXResult(long)
0x1400f4b90  mov     rcx, [rbp+480h+var_40]
0x1400f4b97  xor     rcx, rsp; StackCookie
0x1400f4b9a  call    __security_check_cookie
0x1400f4b9f  mov     rbx, [rsp+580h+arg_18]
0x1400f4ba7  add     rsp, 550h
0x1400f4bae  pop     r15
0x1400f4bb0  pop     r14
0x1400f4bb2  pop     r13
0x1400f4bb4  pop     r12
0x1400f4bb6  pop     rdi
0x1400f4bb7  pop     rsi
0x1400f4bb8  pop     rbp
0x1400f4bb9  retn
0x1400f4bba  mov     edx, r13d; unsigned int
0x1400f4bbd  lea     rcx, [rbp+480h+var_4C0]; this
0x1400f4bc1  call    ?SetConnectorId@CRDPENCConnectorStringSerializer@@UEAAJK@Z; CRDPENCConnectorStringSerializer::SetConnectorId(ulong)
0x1400f4bc6  mov     edi, eax
0x1400f4bc8  test    eax, eax
0x1400f4bca  jns     short loc_1400F4C02
  ... truncated ...
```
