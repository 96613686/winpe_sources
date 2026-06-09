# CUMRDPConnection::ProtocolComplete(ulong)

- ea: `0x1800211c0`
- end: `0x180021bca`
- name: `?ProtocolComplete@CUMRDPConnection@@UEAAJK@Z`
- size: `2570`
- prototype: `__int64 __fastcall(CUMRDPConnection *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800013e8`
- `0x1800015f0`
- `0x180002ea4`
- `0x1800071c0`
- `0x1800071f0`
- `0x180009628`
- `0x180012200`
- `0x18001e49c`
- `0x1800211c0`
- `0x180033da0`
- `0x1800453cc`
- `0x1800544d4`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002122a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180021b3c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002122a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180021b3c`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180021241`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180021745`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180021241`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180021745`
- `RDPBASE!RDPServerStackDiagnostics_LogCheckpoint` at `0x18002150b`
- `RDPBASE!RDPServerStackDiagnostics_LogCheckpoint` at `0x18002150b`

## string_xrefs

- `0x180021341`: `ProtocolProvider`
- `0x180021ab7`: `m_spLicensingPlugin is not initialized!`
- `0x1800212d0`: `ProtocolComplete`
- `0x1800213d4`: `ProtocolComplete failed`
- `0x1800213e8`: `ProtocolComplete`
- `0x18002147b`: `ProtocolComplete`
- `0x1800214df`: `ProtocolComplete`
- `0x180021ac5`: `ProtocolComplete`
- `0x180021784`: `StartDirectlyWithSideTransport`
- `0x1800217e7`: `Failed to QI for side band data source interface`
- `0x180021a22`: `Side band data callbacks were set.`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::ProtocolComplete(CUMRDPConnection *this, unsigned int a2)
{
  GUID v2; // xmm0
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  _QWORD *v8; // r15
  __int64 v9; // r14
  __int64 v10; // rdi
  int v11; // ecx
  __int64 v12; // r8
  int v13; // r9d
  __int128 v14; // xmm0
  int v15; // eax
  int v16; // edi
  char *v17; // rdx
  const char **v18; // rax
  CUMRDPConnection *v19; // rcx
  __int64 v20; // rdx
  __int64 (__fastcall ***v21)(_QWORD, GUID *, const char **); // rcx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  __int16 *v25; // rdx
  const char **v26; // rax
  const char *v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v29)(_QWORD, GUID *, const char **); // rax
  __int64 (__fastcall *v30)(_QWORD, GUID *, const char **); // rdi
  const char *v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v33)(_QWORD, GUID *, const char **); // rax
  __int64 (__fastcall *v34)(_QWORD, GUID *, const char **); // rdi
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  const char *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // r8
  const char **v52; // [rsp+30h] [rbp-A9h]
  const char **v53; // [rsp+30h] [rbp-A9h]
  const char **v54; // [rsp+40h] [rbp-99h]
  const char **v55; // [rsp+40h] [rbp-99h]
  const char **v56; // [rsp+48h] [rbp-91h]
  const char **v57; // [rsp+48h] [rbp-91h]
  int v58; // [rsp+50h] [rbp-89h] BYREF
  const char *v59; // [rsp+58h] [rbp-81h] BYREF
  __int64 v60; // [rsp+60h] [rbp-79h] BYREF
  const char *v61; // [rsp+68h] [rbp-71h] BYREF
  const char *v62; // [rsp+70h] [rbp-69h] BYREF
  const char *v63; // [rsp+78h] [rbp-61h] BYREF
  const char *v64; // [rsp+80h] [rbp-59h] BYREF
  const char *v65; // [rsp+88h] [rbp-51h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, _QWORD, _QWORD); // [rsp+90h] [rbp-49h] BYREF
  int v67; // [rsp+98h] [rbp-41h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-39h] BYREF
  __int64 (__fastcall ***v69)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-31h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v72; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v73; // [rsp+C8h] [rbp-11h] BYREF
  __int128 v74; // [rsp+D0h] [rbp-9h] BYREF
  GUID ActivityId; // [rsp+E0h] [rbp+7h] BYREF

  v2 = *(GUID *)((char *)this + 744);
  v72 = 0;
  v5 = 0;
  v66 = 0;
  v71 = 0;
  v70 = 0;
  v69 = 0;
  v73 = 0;
  v68 = 0;
  v67 = 0;
  ActivityId = v2;
  EventActivityIdControl(4u, &ActivityId);
  v8 = (_QWORD *)((char *)this + 88);
  v61 = (char *)this + 88;
  if ( *((_DWORD *)this + 24) )
    PAL_System_CritSecEnter(*v8, v6, v7);
  v9 = 0;
  if ( *((_QWORD *)this + 26) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v72, v6, v7);
    v9 = *((_QWORD *)this + 26);
    v72 = v9;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v72);
  }
  if ( *((_QWORD *)this + 21) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v71, v6, v7);
    v5 = *((_QWORD *)this + 21);
    v71 = v5;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v71);
  }
  v10 = 0;
  if ( *((_QWORD *)this + 72) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v68, v6, v7);
    v10 = *((_QWORD *)this + 72);
    v68 = v10;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v68);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v61);
  if ( v10 )
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v10 + 80LL))(v10, L"ProtocolComplete");
  if ( (unsigned int)dword_1801B76C8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
  {
    v14 = *(_OWORD *)((char *)this + 744);
    v60 = 0x1000000;
    v74 = v14;
    v58 = a2 == 1;
    v61 = (const char *)&v74;
    v63 = "ProtocolProvider";
    v62 = "Stack";
    v59 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)&unk_1801937E0,
      v12,
      v13,
      (__int64)&v59,
      (__int64)&v60,
      (__int64)&v62,
      (__int64)&v63,
      (__int64)&v61,
      (__int64)&v58);
  }
  if ( !v9 )
  {
    v16 = -2147019873;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_67;
    v38 = "m_spLicensingPlugin is not initialized!";
    LODWORD(v60) = 6026;
    v17 = (char *)&word_18019373E;
    goto LABEL_65;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 48LL))(v9, a2);
  v16 = v15;
  if ( v15 >= 0 )
  {
    if ( !v5 )
    {
      v16 = -2147467261;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_67;
      LODWORD(v60) = 6030;
      v59 = "spRDPStack is NULL";
      v61 = "ProtocolComplete";
      v63 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v17 = byte_1801936ED;
      v62 = "Error condition failed";
      v56 = &v59;
      v54 = &v61;
      v52 = &v63;
      v18 = &v62;
      goto LABEL_66;
    }
    v19 = (CUMRDPConnection *)((char *)this - 64);
    if ( a2 )
    {
      if ( *((_DWORD *)v19 + 210) )
      {
        v74 = *(_OWORD *)((char *)this + 744);
        RDPServerStackDiagnostics_LogCheckpoint(&v74, 702);
      }
      if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        LODWORD(v60) = 702;
        v59 = "LicenseCheck";
        v61 = "Connection checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)v19,
          (unsigned int)word_18019369A,
          v12,
          v13,
          (__int64)&v61,
          (__int64)&v60,
          (__int64)&v59);
      }
    }
    else
    {
      CUMRDPConnection::SetDisconnectReasonAndLogDiagnosticsEvent(v19, 0x102u, v15, "ProtocolComplete");
    }
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v5 + 416LL))(
            v5,
            &v69);
    if ( v16 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_67;
      v61 = "ProtocolComplete";
      v59 = "Failed to Get Stack VC MGr";
      v17 = byte_180193649;
      LODWORD(v60) = 6063;
      v63 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v62 = "Error HResult failed";
      v56 = &v59;
      v54 = &v61;
      v52 = &v63;
      v18 = &v62;
      goto LABEL_66;
    }
    v16 = (**v69)(v69, &IID_IRdpVCMgr, &v70);
    if ( v16 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_67;
      v61 = "ProtocolComplete";
      v59 = "Failed to QI for RdpVcMgr";
      v17 = (char *)qword_1801935F8;
      LODWORD(v60) = 6066;
      v63 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v62 = "Error HResult failed";
      v56 = &v59;
      v54 = &v61;
      v52 = &v63;
      v18 = &v62;
      goto LABEL_66;
    }
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v70 + 32LL))(
            v70,
            &v66);
    if ( v16 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_67;
      v61 = "ProtocolComplete";
      v59 = "Failed to Get DVC MGr";
      v17 = &byte_1801935A7;
      LODWORD(v60) = 6069;
      v63 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v62 = "Error HResult failed";
      v56 = &v59;
      v54 = &v61;
      v52 = &v63;
      v18 = &v62;
      goto LABEL_66;
    }
    v59 = (char *)this + 88;
    if ( *((_DWORD *)this + 24) )
      PAL_System_CritSecEnter(*v8, v20, v12);
    if ( v66 != *((__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))this + 29) )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 232, v20, v12);
      *((_QWORD *)this + 29) = v66;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 232);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v59);
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 15) + 32LL))(
           *((_QWORD *)this + 15),
           L"StartDirectlyWithSideTransport",
           &v67) >= 0
      && v67 )
    {
      v21 = (__int64 (__fastcall ***)(_QWORD, GUID *, const char **))*((_QWORD *)this + 32);
      v63 = 0;
      v61 = 0;
      v62 = 0;
      v16 = (**v21)(v21, &IID_IRdpSideBandDataSource, &v61);
      if ( v16 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
        {
LABEL_46:
          wil::com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>::~com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>(&v62);
          wil::com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>::~com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>(&v61);
          wil::com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>::~com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>(&v63);
          goto LABEL_67;
        }
        v64 = "ProtocolComplete";
        v59 = "Failed to QI for side band data source interface";
        v25 = &word_180193556;
        LODWORD(v60) = 6086;
        v65 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        *(_QWORD *)&v74 = "Error HResult failed";
        v57 = &v59;
        v55 = &v64;
        v53 = &v65;
        v26 = (const char **)&v74;
LABEL_45:
        v58 = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v22,
          (_DWORD)v25,
          v23,
          v24,
          (__int64)v26,
          (__int64)&v58,
          (__int64)v53,
          (__int64)&v60,
          (__int64)v55,
          (__int64)v57);
        goto LABEL_46;
      }
      v27 = v63;
      v28 = v66;
      v29 = (__int64 (__fastcall **)(_QWORD, GUID *, const char **))*v66;
      v63 = 0;
      v30 = *v29;
      if ( v27 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v27 + 16LL))(v27);
      v16 = v30(v28, &IID_IRdpIceToStackCallback, &v63);
      if ( v16 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_46;
        v65 = "ProtocolComplete";
        *(_QWORD *)&v74 = "Failed to QI for ICE to stack callback interface";
        v25 = (__int16 *)byte_180193505;
        LODWORD(v60) = 6089;
        v64 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v59 = "Error HResult failed";
        v57 = (const char **)&v74;
        v55 = &v65;
        v53 = &v64;
        v26 = &v59;
        goto LABEL_45;
      }
      v31 = v62;
      v32 = v66;
      v33 = (__int64 (__fastcall **)(_QWORD, GUID *, const char **))*v66;
      v62 = 0;
      v34 = *v33;
      if ( v31 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v31 + 16LL))(v31);
      v16 = v34(v32, &IID_IRDPWDUMX_StackChannelMgrEvents, &v62);
      if ( v16 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_46;
        v65 = "ProtocolComplete";
        *(_QWORD *)&v74 = "Failed to QI for stack channel manager callbacks interface";
        v25 = (__int16 *)&dword_1801934B4;
        LODWORD(v60) = 6092;
        v64 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v59 = "Error HResult failed";
        v57 = (const char **)&v74;
        v55 = &v65;
        v53 = &v64;
        v26 = &v59;
        goto LABEL_45;
      }
      (*(void (__fastcall **)(const char *, const char *))(*(_QWORD *)v61 + 24LL))(v61, v63);
      (*(void (__fastcall **)(const char *, _QWORD))(*(_QWORD *)v62 + 112LL))(v62, *((_QWORD *)this + 32));
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        *(_QWORD *)&v74 = "Side band data callbacks were set.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v35,
          (unsigned int)&byte_18019348F,
          v36,
          v37,
          (__int64)&v74);
      }
      wil::com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>::~com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>(&v62);
      wil::com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>::~com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>(&v61);
      wil::com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>::~com_ptr_t<IRdpSideBandDataSource,wil::err_returncode_policy>(&v63);
    }
    v16 = (**v69)(v69, &IID_IRDPCoreChannelManagerEx, &v73);
    if ( v16 >= 0 || (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_67;
    v38 = "Failed to QI for the channel manager ex interface";
    LODWORD(v60) = 6102;
    v17 = (char *)&word_18019343E;
LABEL_65:
    *(_QWORD *)&v74 = v38;
    v64 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v59 = "Error HResult failed";
    v56 = (const char **)&v74;
    v54 = &v65;
    v52 = &v64;
    v18 = &v59;
    v65 = "ProtocolComplete";
LABEL_66:
    v58 = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v11,
      (_DWORD)v17,
      v12,
      v13,
      (__int64)v18,
      (__int64)&v58,
      (__int64)v52,
      (__int64)&v60,
      (__int64)v54,
      (__int64)v56);
    goto LABEL_67;
  }
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v58 = 6022;
    v59 = "ProtocolComplete failed";
    v61 = "ProtocolComplete";
    v63 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    LODWORD(v60) = v15;
    v62 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)&byte_18019378F,
      v12,
      v13,
      (__int64)&v62,
      (__int64)&v60,
      (__int64)&v63,
      (__int64)&v58,
      (__int64)&v61,
      (__int64)&v59);
  }
LABEL_67:
  EventActivityIdControl(2u, &ActivityId);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v68, v39, v40);
  v43 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v69, v41, v42);
  v46 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v66, v44, v45);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v71, v47, v48);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v72, v49, v50);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800211c0  mov     [rsp-8+arg_10], rbx
0x1800211c5  push    rbp
0x1800211c6  push    rsi
0x1800211c7  push    rdi
0x1800211c8  push    r12
0x1800211ca  push    r13
0x1800211cc  push    r14
0x1800211ce  push    r15
0x1800211d0  lea     rbp, [rsp-27h]
0x1800211d5  sub     rsp, 100h
0x1800211dc  mov     rax, cs:__security_cookie
0x1800211e3  xor     rax, rsp
0x1800211e6  mov     [rbp+57h+var_40], rax
0x1800211ea  movups  xmm0, xmmword ptr [rcx+2E8h]
0x1800211f1  xor     r13d, r13d
0x1800211f4  mov     r12d, edx
0x1800211f7  mov     rsi, rcx
0x1800211fa  mov     [rbp+57h+var_70], r13
0x1800211fe  mov     ebx, r13d
0x180021201  mov     [rbp+57h+var_A0], r13
0x180021205  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180021209  mov     [rbp+57h+var_78], rbx
0x18002120d  lea     ecx, [r13+4]; ControlCode
0x180021211  mov     [rbp+57h+var_80], r13
0x180021215  mov     [rbp+57h+var_88], r13
0x180021219  mov     [rbp+57h+var_68], r13
0x18002121d  mov     [rbp+57h+var_90], r13
0x180021221  mov     [rbp+57h+var_98], r13d
0x180021225  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x18002122a  call    cs:__imp_EventActivityIdControl
0x180021230  lea     r15, [rsi+58h]
0x180021234  mov     [rbp+57h+var_C8], r15
0x180021238  cmp     [r15+8], r13d
0x18002123c  jz      short loc_180021247
0x18002123e  mov     rcx, [r15]
0x180021241  call    cs:__imp_PAL_System_CritSecEnter
0x180021247  mov     r14, r13
0x18002124a  cmp     [rsi+0D0h], r13
0x180021251  jz      short loc_180021270
0x180021253  lea     rcx, [rbp+57h+var_70]
0x180021257  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18002125c  mov     r14, [rsi+0D0h]
0x180021263  lea     rcx, [rbp+57h+var_70]
0x180021267  mov     [rbp+57h+var_70], r14
0x18002126b  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180021270  cmp     [rsi+0A8h], r13
0x180021277  jz      short loc_180021296
0x180021279  lea     rcx, [rbp+57h+var_78]
0x18002127d  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180021282  mov     rbx, [rsi+0A8h]
0x180021289  lea     rcx, [rbp+57h+var_78]
0x18002128d  mov     [rbp+57h+var_78], rbx
0x180021291  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180021296  mov     rdi, r13
0x180021299  cmp     [rsi+240h], r13
0x1800212a0  jz      short loc_1800212BF
0x1800212a2  lea     rcx, [rbp+57h+var_90]
0x1800212a6  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800212ab  mov     rdi, [rsi+240h]
0x1800212b2  lea     rcx, [rbp+57h+var_90]
0x1800212b6  mov     [rbp+57h+var_90], rdi
0x1800212ba  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800212bf  lea     rcx, [rbp+57h+var_C8]; this
0x1800212c3  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800212c8  test    rdi, rdi
0x1800212cb  jz      short loc_1800212E3
0x1800212cd  mov     rax, [rdi]
0x1800212d0  lea     rdx, aProtocolcomple_0; "ProtocolComplete"
0x1800212d7  mov     rcx, rdi
0x1800212da  mov     rax, [rax+50h]
0x1800212de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212e3  mov     eax, cs:dword_1801B76C8
0x1800212e9  cmp     eax, 4
0x1800212ec  jbe     loc_1800213A0
0x1800212f2  mov     rdx, 470000000000h
0x1800212fc  lea     rcx, dword_1801B76C8
0x180021303  call    _tlgKeywordOn
0x180021308  test    al, al
0x18002130a  jz      loc_1800213A0
0x180021310  movups  xmm0, xmmword ptr [rsi+2E8h]
0x180021317  mov     eax, r13d
0x18002131a  mov     [rbp+57h+var_D0], 1000000h
0x180021322  cmp     r12d, 1
0x180021326  lea     rdx, unk_1801937E0
0x18002132d  movdqu  [rbp+57h+var_60], xmm0
0x180021332  setz    al
0x180021335  mov     [rsp+130h+var_E0], eax
0x180021339  lea     rax, [rbp+57h+var_60]
0x18002133d  mov     [rbp+57h+var_C8], rax
0x180021341  lea     rax, aProtocolprovid; "ProtocolProvider"
0x180021348  mov     [rbp+57h+var_B8], rax
0x18002134c  lea     rax, aStack; "Stack"
0x180021353  mov     [rbp+57h+var_C0], rax
0x180021357  lea     rax, aCheckpoint; "Checkpoint"
0x18002135e  mov     [rsp+130h+var_D8], rax
0x180021363  lea     rax, [rsp+130h+var_E0]
0x180021368  mov     [rsp+130h+var_E8], rax
0x18002136d  lea     rax, [rbp+57h+var_C8]
0x180021371  mov     [rsp+130h+var_F0], rax
0x180021376  lea     rax, [rbp+57h+var_B8]
0x18002137a  mov     [rsp+130h+var_F8], rax
0x18002137f  lea     rax, [rbp+57h+var_C0]
0x180021383  mov     [rsp+130h+var_100], rax
0x180021388  lea     rax, [rbp+57h+var_D0]
0x18002138c  mov     [rsp+130h+var_108], rax
0x180021391  lea     rax, [rsp+130h+var_D8]
0x180021396  mov     [rsp+130h+var_110], rax
0x18002139b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800213a0  test    r14, r14
0x1800213a3  jz      loc_180021AA7
0x1800213a9  mov     rax, [r14]
0x1800213ac  mov     edx, r12d
0x1800213af  mov     rcx, r14
0x1800213b2  mov     rax, [rax+30h]
0x1800213b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213bb  mov     edi, eax
0x1800213bd  test    eax, eax
0x1800213bf  jns     loc_18002144B
0x1800213c5  mov     ecx, cs:dword_1801B76C8
0x1800213cb  cmp     ecx, 2
0x1800213ce  jbe     loc_180021B33
0x1800213d4  lea     rax, aProtocolcomple_1; "ProtocolComplete failed"
0x1800213db  mov     [rsp+130h+var_E0], 1786h
0x1800213e3  mov     [rsp+130h+var_D8], rax
0x1800213e8  lea     r14, aProtocolcomple; "ProtocolComplete"
0x1800213ef  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800213f6  mov     [rbp+57h+var_C8], r14
0x1800213fa  mov     [rbp+57h+var_B8], rax
0x1800213fe  lea     rdx, byte_18019378F
0x180021405  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18002140c  mov     dword ptr [rbp+57h+var_D0], edi
0x18002140f  mov     [rbp+57h+var_C0], rax
0x180021413  lea     rax, [rsp+130h+var_D8]
0x180021418  mov     [rsp+130h+var_E8], rax
0x18002141d  lea     rax, [rbp+57h+var_C8]
0x180021421  mov     [rsp+130h+var_F0], rax
0x180021426  lea     rax, [rsp+130h+var_E0]
0x18002142b  mov     [rsp+130h+var_F8], rax
0x180021430  lea     rax, [rbp+57h+var_B8]
0x180021434  mov     [rsp+130h+var_100], rax
0x180021439  lea     rax, [rbp+57h+var_D0]
0x18002143d  mov     [rsp+130h+var_108], rax
0x180021442  lea     rax, [rbp+57h+var_C0]
0x180021446  jmp     loc_180021B29
0x18002144b  test    rbx, rbx
0x18002144e  jnz     loc_1800214DB
0x180021454  mov     eax, cs:dword_1801B76C8
0x18002145a  mov     edi, 80004003h
0x18002145f  cmp     eax, 2
0x180021462  jbe     loc_180021B33
0x180021468  lea     rax, aSprdpstackIsNu; "spRDPStack is NULL"
0x18002146f  mov     dword ptr [rbp+57h+var_D0], 178Eh
0x180021476  mov     [rsp+130h+var_D8], rax
0x18002147b  lea     r14, aProtocolcomple; "ProtocolComplete"
0x180021482  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180021489  mov     [rbp+57h+var_C8], r14
0x18002148d  mov     [rbp+57h+var_B8], rax
0x180021491  lea     rdx, byte_1801936ED
0x180021498  lea     rax, aErrorCondition; "Error condition failed"
0x18002149f  mov     [rbp+57h+var_C0], rax
0x1800214a3  lea     rax, [rsp+130h+var_D8]
0x1800214a8  mov     [rsp+130h+var_E8], rax
0x1800214ad  lea     rax, [rbp+57h+var_C8]
0x1800214b1  mov     [rsp+130h+var_F0], rax
0x1800214b6  lea     rax, [rbp+57h+var_D0]
0x1800214ba  mov     [rsp+130h+var_F8], rax
0x1800214bf  lea     rax, [rbp+57h+var_B8]
0x1800214c3  mov     [rsp+130h+var_100], rax
0x1800214c8  lea     rax, [rsp+130h+var_E0]
0x1800214cd  mov     [rsp+130h+var_108], rax
0x1800214d2  lea     rax, [rbp+57h+var_C0]
0x1800214d6  jmp     loc_180021B25
0x1800214db  lea     rcx, [rsi-40h]; this
0x1800214df  lea     r14, aProtocolcomple; "ProtocolComplete"
0x1800214e6  test    r12d, r12d
0x1800214e9  jz      short loc_180021560
0x1800214eb  mov     edi, 2BEh
0x1800214f0  cmp     [rcx+348h], r13d
0x1800214f7  jz      short loc_180021511
0x1800214f9  movups  xmm0, xmmword ptr [rsi+2E8h]
0x180021500  mov     edx, edi
0x180021502  lea     rcx, [rbp+57h+var_60]
0x180021506  movdqu  [rbp+57h+var_60], xmm0
0x18002150b  call    cs:__imp_RDPServerStackDiagnostics_LogCheckpoint
0x180021511  mov     eax, cs:dword_1801B76C8
0x180021517  cmp     eax, 3
0x18002151a  jbe     short loc_180021570
0x18002151c  lea     rax, aLicensecheck; "LicenseCheck"
0x180021523  mov     dword ptr [rbp+57h+var_D0], edi
0x180021526  mov     [rsp+130h+var_D8], rax
0x18002152b  lea     rdx, word_18019369A
0x180021532  lea     rax, aConnectionChec; "Connection checkpoint"
0x180021539  mov     [rbp+57h+var_C8], rax
0x18002153d  lea     rax, [rsp+130h+var_D8]
0x180021542  mov     [rsp+130h+var_100], rax
0x180021547  lea     rax, [rbp+57h+var_D0]
0x18002154b  mov     [rsp+130h+var_108], rax
0x180021550  lea     rax, [rbp+57h+var_C8]
0x180021554  mov     [rsp+130h+var_110], rax
0x180021559  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002155e  jmp     short loc_180021570
0x180021560  mov     r9, r14; char *
0x180021563  mov     r8d, edi; int
0x180021566  mov     edx, 102h; unsigned int
0x18002156b  call    ?SetDisconnectReasonAndLogDiagnosticsEvent@CUMRDPConnection@@IEAAXKJPEBD@Z; CUMRDPConnection::SetDisconnectReasonAndLogDiagnosticsEvent(ulong,long,char const *)
0x180021570  mov     rax, [rbx]
0x180021573  lea     rdx, [rbp+57h+var_88]
0x180021577  mov     rcx, rbx
0x18002157a  mov     rax, [rax+1A0h]
0x180021581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021586  mov     edi, eax
0x180021588  test    eax, eax
0x18002158a  jns     short loc_180021607
0x18002158c  mov     eax, cs:dword_1801B76C8
0x180021592  cmp     eax, 2
0x180021595  jbe     loc_180021B33
0x18002159b  lea     rax, aFailedToGetSta_0; "Failed to Get Stack VC MGr"
0x1800215a2  mov     [rbp+57h+var_C8], r14
0x1800215a6  mov     [rsp+130h+var_D8], rax
0x1800215ab  lea     rdx, byte_180193649
0x1800215b2  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800215b9  mov     dword ptr [rbp+57h+var_D0], 17AFh
0x1800215c0  mov     [rbp+57h+var_B8], rax
0x1800215c4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800215cb  mov     [rbp+57h+var_C0], rax
0x1800215cf  lea     rax, [rsp+130h+var_D8]
0x1800215d4  mov     [rsp+130h+var_E8], rax
0x1800215d9  lea     rax, [rbp+57h+var_C8]
0x1800215dd  mov     [rsp+130h+var_F0], rax
0x1800215e2  lea     rax, [rbp+57h+var_D0]
0x1800215e6  mov     [rsp+130h+var_F8], rax
0x1800215eb  lea     rax, [rbp+57h+var_B8]
0x1800215ef  mov     [rsp+130h+var_100], rax
0x1800215f4  lea     rax, [rsp+130h+var_E0]
0x1800215f9  mov     [rsp+130h+var_108], rax
0x1800215fe  lea     rax, [rbp+57h+var_C0]
0x180021602  jmp     loc_180021B25
0x180021607  mov     rcx, [rbp+57h+var_88]
0x18002160b  lea     r8, [rbp+57h+var_80]
0x18002160f  lea     rdx, IID_IRdpVCMgr
0x180021616  mov     rax, [rcx]
0x180021619  mov     rax, [rax]
0x18002161c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021621  mov     edi, eax
0x180021623  test    eax, eax
0x180021625  jns     short loc_1800216A2
0x180021627  mov     eax, cs:dword_1801B76C8
0x18002162d  cmp     eax, 2
0x180021630  jbe     loc_180021B33
0x180021636  lea     rax, aFailedToQiForR_0; "Failed to QI for RdpVcMgr"
0x18002163d  mov     [rbp+57h+var_C8], r14
0x180021641  mov     [rsp+130h+var_D8], rax
0x180021646  lea     rdx, qword_1801935F8
0x18002164d  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180021654  mov     dword ptr [rbp+57h+var_D0], 17B2h
0x18002165b  mov     [rbp+57h+var_B8], rax
0x18002165f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180021666  mov     [rbp+57h+var_C0], rax
0x18002166a  lea     rax, [rsp+130h+var_D8]
0x18002166f  mov     [rsp+130h+var_E8], rax
0x180021674  lea     rax, [rbp+57h+var_C8]
0x180021678  mov     [rsp+130h+var_F0], rax
0x18002167d  lea     rax, [rbp+57h+var_D0]
0x180021681  mov     [rsp+130h+var_F8], rax
0x180021686  lea     rax, [rbp+57h+var_B8]
0x18002168a  mov     [rsp+130h+var_100], rax
0x18002168f  lea     rax, [rsp+130h+var_E0]
0x180021694  mov     [rsp+130h+var_108], rax
0x180021699  lea     rax, [rbp+57h+var_C0]
0x18002169d  jmp     loc_180021B25
0x1800216a2  mov     rcx, [rbp+57h+var_80]
0x1800216a6  lea     rdx, [rbp+57h+var_A0]
0x1800216aa  mov     rax, [rcx]
0x1800216ad  mov     rax, [rax+20h]
0x1800216b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216b6  mov     edi, eax
0x1800216b8  test    eax, eax
0x1800216ba  jns     short loc_180021737
0x1800216bc  mov     eax, cs:dword_1801B76C8
0x1800216c2  cmp     eax, 2
0x1800216c5  jbe     loc_180021B33
0x1800216cb  lea     rax, aFailedToGetDvc; "Failed to Get DVC MGr"
0x1800216d2  mov     [rbp+57h+var_C8], r14
0x1800216d6  mov     [rsp+130h+var_D8], rax
0x1800216db  lea     rdx, byte_1801935A7
0x1800216e2  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800216e9  mov     dword ptr [rbp+57h+var_D0], 17B5h
0x1800216f0  mov     [rbp+57h+var_B8], rax
0x1800216f4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800216fb  mov     [rbp+57h+var_C0], rax
0x1800216ff  lea     rax, [rsp+130h+var_D8]
0x180021704  mov     [rsp+130h+var_E8], rax
0x180021709  lea     rax, [rbp+57h+var_C8]
0x18002170d  mov     [rsp+130h+var_F0], rax
0x180021712  lea     rax, [rbp+57h+var_D0]
0x180021716  mov     [rsp+130h+var_F8], rax
0x18002171b  lea     rax, [rbp+57h+var_B8]
0x18002171f  mov     [rsp+130h+var_100], rax
0x180021724  lea     rax, [rsp+130h+var_E0]
0x180021729  mov     [rsp+130h+var_108], rax
  ... truncated ...
```
