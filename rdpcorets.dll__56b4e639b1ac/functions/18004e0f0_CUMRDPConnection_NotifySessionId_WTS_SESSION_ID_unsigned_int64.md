# CUMRDPConnection::NotifySessionId(_WTS_SESSION_ID *,unsigned __int64)

- ea: `0x18004e0f0`
- end: `0x18004f2ce`
- name: `?NotifySessionId@CUMRDPConnection@@UEAAJPEAU_WTS_SESSION_ID@@_K@Z`
- size: `4574`
- prototype: `__int64 __fastcall(CUMRDPConnection *__hidden this, struct _WTS_SESSION_ID *, unsigned __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800015f0`
- `0x180002ea4`
- `0x1800071c0`
- `0x1800071f0`
- `0x18000f784`
- `0x180010908`
- `0x180012144`
- `0x180012200`
- `0x18001e49c`
- `0x18002bb34`
- `0x180033da0`
- `0x180034970`
- `0x180034c4c`
- `0x18003e988`
- `0x180041e8c`
- `0x18004e0f0`
- `0x1800544d4`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18004e1e5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18004f1ec`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18004e1e5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18004f1ec`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18004e200`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18004ee7b`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18004e200`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18004ee7b`

## string_xrefs

- `0x18004e581`: `IWRdsProtocolConnection`
- `0x18004e6dd`: `Connection failed, can't create Input devices. Error code: 0x%x.`
- `0x18004e70f`: `Connection failed, can't create Input devices.`
- `0x18004e8bc`: `Failed to store connection in protocol manager`
- `0x18004ec2a`: `Connection failed, can't create internal graphics inter-process communication channel. Error code: 0x%x.`
- `0x18004ec8b`: `Connection failed, can't create internal graphics inter-process communication channel. Error code: 0x%x.`
- `0x18004ec55`: `Connection failed, can't create internal graphics inter-process communication channel.`
- `0x18004ecb6`: `Connection failed, can't create internal graphics inter-process communication channel.`
- `0x18004ed0b`: `Connection failed, can't create graphics pipe subsystem. Error code: 0x%x.`
- `0x18004ee24`: `Connection failed, can't create graphics pipe subsystem. Error code: 0x%x.`
- `0x18004ed36`: `Connection failed, can't create graphics pipe subsystem.`
- `0x18004ee4f`: `Connection failed, can't create graphics pipe subsystem.`
- `0x18004ed76`: `Failed to create the pipe plug-in`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::NotifySessionId(
        CUMRDPConnection *this,
        struct _WTS_SESSION_ID *a2,
        const char *a3)
{
  struct IUnknown *v3; // r15
  __int64 v4; // rbx
  __int64 v5; // r13
  GUID v6; // xmm0
  __int64 v7; // rsi
  __int64 v8; // r14
  CUMRDPProtocolManager *v9; // rdi
  __int64 v10; // r12
  __int64 v11; // rdx
  __int64 v12; // r8
  _QWORD *v13; // rax
  const char *v14; // rdx
  signed __int64 v15; // rax
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rdx
  int TermInputMgr; // esi
  __int64 v20; // r8
  int v21; // r9d
  unsigned int v22; // ebx
  int v23; // ecx
  int v24; // r9d
  __int128 v25; // xmm0
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  const char *v32; // rax
  __int16 *v33; // rdx
  signed __int64 v34; // r15
  __int64 v35; // rbx
  const char *v36; // rbx
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  int v40; // eax
  int v41; // r8d
  int v42; // r9d
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  int v52; // eax
  int v53; // ecx
  __int64 v54; // rbx
  int v55; // eax
  int v56; // eax
  struct IUnknown *v57; // rcx
  int v58; // eax
  int v59; // ecx
  int v60; // r8d
  int v61; // r9d
  int v62; // eax
  __int64 v63; // rdx
  __int64 v64; // r8
  int v65; // ecx
  int v66; // r8d
  int v67; // r9d
  CUMRDPConnection *v68; // rdi
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // rcx
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 v98; // rdx
  __int64 v99; // r8
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v103; // [rsp+20h] [rbp-E0h]
  signed __int64 v104; // [rsp+50h] [rbp-B0h] BYREF
  void **v105; // [rsp+58h] [rbp-A8h] BYREF
  const char *v106; // [rsp+60h] [rbp-A0h] BYREF
  const char *v107; // [rsp+68h] [rbp-98h] BYREF
  const char *v108; // [rsp+70h] [rbp-90h] BYREF
  const char *v109; // [rsp+78h] [rbp-88h] BYREF
  void *v110; // [rsp+80h] [rbp-80h] BYREF
  const char *v111; // [rsp+88h] [rbp-78h] BYREF
  int v112; // [rsp+90h] [rbp-70h] BYREF
  __int64 v113; // [rsp+98h] [rbp-68h] BYREF
  __int64 v114; // [rsp+A0h] [rbp-60h] BYREF
  const char *v115; // [rsp+A8h] [rbp-58h] BYREF
  const char *v116; // [rsp+B0h] [rbp-50h] BYREF
  struct IUnknown *v117; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v118; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v119; // [rsp+C8h] [rbp-38h] BYREF
  CUMRDPProtocolManager *v120; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v121; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v122; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v123; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v124; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v125; // [rsp+F8h] [rbp-8h] BYREF
  struct IUnknown *v126; // [rsp+100h] [rbp+0h] BYREF
  __int64 v127; // [rsp+108h] [rbp+8h] BYREF
  __int64 v128; // [rsp+110h] [rbp+10h] BYREF
  CUMRDPConnection *v129; // [rsp+118h] [rbp+18h]
  __int64 v130; // [rsp+120h] [rbp+20h] BYREF
  __int128 v131; // [rsp+128h] [rbp+28h] BYREF
  __int64 v132; // [rsp+138h] [rbp+38h]
  _BYTE v133[136]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v134; // [rsp+1C8h] [rbp+C8h]
  _QWORD v135[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v136; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v137; // [rsp+1F0h] [rbp+F0h]
  GUID ActivityId; // [rsp+1F8h] [rbp+F8h] BYREF
  char Buffer[272]; // [rsp+210h] [rbp+110h] BYREF

  v3 = 0;
  v116 = a3;
  v111 = (const char *)a2;
  v104 = (signed __int64)this;
  v132 = 0;
  v112 = 0;
  v134 = 0;
  v131 = 0;
  v135[0] = 0;
  memset_0(v133, 0, 0x82u);
  memset_0(Buffer, 0, 0x104u);
  v4 = 0;
  v130 = 0;
  v114 = 0;
  v128 = 0;
  v5 = 0;
  v6 = *(GUID *)(v104 + 752);
  v127 = 0;
  v7 = 0;
  v124 = 0;
  v8 = 0;
  ActivityId = v6;
  v123 = 0;
  v9 = 0;
  v122 = 0;
  v10 = 0;
  v121 = 0;
  v120 = 0;
  v126 = 0;
  v119 = 0;
  v125 = 0;
  v113 = 0;
  v110 = 0;
  v118 = 0;
  v117 = 0;
  EventActivityIdControl(4u, &ActivityId);
  v13 = (_QWORD *)v104;
  v115 = (const char *)(v104 + 96);
  if ( *(_DWORD *)(v104 + 104) )
  {
    PAL_System_CritSecEnter(*(_QWORD *)(v104 + 96), v11, v12);
    v13 = (_QWORD *)v104;
  }
  if ( v13[24] )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v127, v11, v12);
    v4 = *(_QWORD *)(v104 + 192);
    v127 = v4;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    v13 = (_QWORD *)v104;
  }
  if ( v13[20] )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v124, v11, v12);
    v5 = *(_QWORD *)(v104 + 160);
    v124 = v5;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v124);
    v13 = (_QWORD *)v104;
  }
  if ( v13[29] )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v123, v11, v12);
    v7 = *(_QWORD *)(v104 + 232);
    v123 = v7;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v123);
    v13 = (_QWORD *)v104;
  }
  if ( v13[22] )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v121, v11, v12);
    v8 = *(_QWORD *)(v104 + 176);
    v121 = v8;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v121);
    v13 = (_QWORD *)v104;
  }
  if ( v13[30] )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v122, v11, v12);
    v122 = *(_QWORD *)(v104 + 240);
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v122);
    v13 = (_QWORD *)v104;
  }
  v14 = v111;
  v129 = (CUMRDPConnection *)(v13 - 7);
  *((_DWORD *)v13 + 164) = *((_DWORD *)v111 + 4);
  v15 = v104;
  if ( *(_QWORD *)(v104 + 576) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v120, v14, v12);
    v9 = *(CUMRDPProtocolManager **)(v104 + 576);
    v120 = v9;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v120);
    v15 = v104;
  }
  if ( *(_QWORD *)(v15 + 584) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v119, v14, v12);
    v10 = *(_QWORD *)(v104 + 584);
    v119 = v10;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v119);
    v15 = v104;
  }
  if ( *(_QWORD *)(v15 + 600) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v113, v14, v12);
    v113 = *(_QWORD *)(v104 + 600);
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v113);
    v15 = v104;
  }
  v105 = (void **)(v15 + 608);
  if ( *(void **)(v15 + 608) != v110 )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v110, v14, v12);
    v110 = *v105;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v110);
  }
  if ( *(_QWORD *)(v104 + 128) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v117, v14, v12);
    v3 = *(struct IUnknown **)(v104 + 128);
    v117 = v3;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v117);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v115);
  if ( !v4 || !v5 || !v7 || !v9 || !v8 )
  {
    TermInputMgr = -2147019873;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v107 = "NotifySessionId";
      v116 = "CUMRDPConnection is not initialized!";
      LODWORD(v105) = 3785;
      v108 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v106 = "Error condition failed";
      LODWORD(v104) = -2147019873;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)"NotifySessionId",
        (unsigned int)byte_180195E1B,
        v16,
        v17,
        (__int64)&v106,
        (__int64)&v104,
        (__int64)&v108,
        (__int64)&v105,
        (__int64)&v107,
        (__int64)&v116);
    }
    goto LABEL_113;
  }
  LOWORD(v131) = 23;
  DWORD2(v131) = *((_DWORD *)v111 + 4);
  TermInputMgr = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int128 *))(*(_QWORD *)v5 + 56LL))(
                   v5,
                   L"SessionID",
                   &v131);
  if ( TermInputMgr < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v104) = 3790;
      v115 = "Failed to set the Session ID property on connection";
      v111 = "NotifySessionId";
      v109 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      LODWORD(v105) = TermInputMgr;
      v106 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)word_180195DCA,
        v20,
        v21,
        (__int64)&v106,
        (__int64)&v105,
        (__int64)&v109,
        (__int64)&v104,
        (__int64)&v111,
        (__int64)&v115);
      goto LABEL_34;
    }
    goto LABEL_113;
  }
  if ( (unsigned int)dword_1801B76C8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
  {
    v108 = (const char *)0x1000000;
    LODWORD(v105) = *((_DWORD *)v111 + 4);
    v25 = *(_OWORD *)(v104 + 752);
    v106 = (const char *)&v136;
    v109 = "IWRdsProtocolConnection";
    v115 = "Stack";
    v107 = "Checkpoint";
    v136 = v25;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)word_180195D62,
      v20,
      v24,
      (__int64)&v107,
      (__int64)&v108,
      (__int64)&v115,
      (__int64)&v109,
      (__int64)&v106,
      (__int64)&v105);
  }
  if ( *(_DWORD *)(v104 + 776) )
    goto LABEL_48;
  TermInputMgr = CUMRDPProtocolManager::GetTermInputMgr(v9, v3, &v126);
  if ( TermInputMgr < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v105) = 3803;
      v107 = "GetTermInputMgr failed";
      v108 = "NotifySessionId";
      v106 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      LODWORD(v104) = TermInputMgr;
      v109 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v26,
        (unsigned int)byte_180195D11,
        v27,
        v28,
        (__int64)&v109,
        (__int64)&v104,
        (__int64)&v106,
        (__int64)&v105,
        (__int64)&v108,
        (__int64)&v107);
LABEL_34:
      v22 = 4430;
      goto LABEL_114;
    }
    goto LABEL_113;
  }
  TermInputMgr = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IUnknown *, __int64))(*(_QWORD *)v4 + 48LL))(
                   v4,
                   *((unsigned int *)v111 + 4),
                   v126,
                   1);
  if ( TermInputMgr >= 0 )
  {
LABEL_48:
    v34 = v104;
    v35 = v104 & -(__int64)(v129 != 0);
    if ( v35 != v135[0] )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease(v135, v18, v20);
      v135[0] = v35;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(v135);
    }
    v36 = v111;
    TermInputMgr = CUMRDPProtocolManager::SetAutoReconnectInfo(
                     v9,
                     *((_DWORD *)v111 + 4),
                     (struct _UMTS_AUTORECONNECT *)v133);
    if ( TermInputMgr < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v105) = 3816;
        v107 = "SaveConnection";
        v108 = "NotifySessionId";
        v106 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        LODWORD(v104) = TermInputMgr;
        v109 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v37,
          (unsigned int)&byte_180195C6F,
          v38,
          v39,
          (__int64)&v109,
          (__int64)&v104,
          (__int64)&v106,
          (__int64)&v105,
          (__int64)&v108,
          (__int64)&v107);
        goto LABEL_34;
      }
LABEL_113:
      v22 = 4430;
      goto LABEL_114;
    }
    v40 = CUMRDPProtocolManager::SetConnectionInfo(
            v9,
            *((_DWORD *)v36 + 4),
            (struct IUMRDPConnection *)((v104 - 8) & -(__int64)(v104 != 56)));
    if ( v40 < 0 && (unsigned int)dword_1801B76C8 > 3 )
    {
      LODWORD(v105) = v40;
      v106 = "HResult failed but continue";
      v108 = "Failed to store connection in protocol manager";
      v107 = "NotifySessionId";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)"NotifySessionId",
        (unsigned int)qword_180195C30,
        v41,
        v42,
        (__int64)&v106,
        (__int64)&v108,
        (__int64)&v105,
        (__int64)&v107);
    }
    (*(void (__fastcall **)(__int64, signed __int64, _QWORD))(*(_QWORD *)v10 + 32LL))(
      v10,
      v104 + 684,
      *((unsigned int *)v36 + 4));
    if ( !*(_DWORD *)(v104 + 772) )
    {
      *(_DWORD *)(v104 + 772) = 1;
      TermInputMgr = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 416LL))(v8, &v114);
      if ( TermInputMgr < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v105) = 3831;
          v107 = "Failed to Get Stack VC MGr";
          v108 = "NotifySessionId";
          v106 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          LODWORD(v104) = TermInputMgr;
          v109 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v43,
            (unsigned int)&byte_180195BDF,
            v44,
            v45,
            (__int64)&v109,
            (__int64)&v104,
            (__int64)&v106,
            (__int64)&v105,
            (__int64)&v108,
            (__int64)&v107);
          goto LABEL_34;
        }
        goto LABEL_113;
      }
      TermInputMgr = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v114)(v114, &IID_IRdpVCMgr, &v125);
      if ( TermInputMgr < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v105) = 3834;
          v107 = "Failed to QI for RdpVcMgr";
          v108 = "NotifySessionId";
          v106 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          LODWORD(v104) = TermInputMgr;
          v109 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v46,
            (unsigned int)&word_180195B8E,
            v47,
            v48,
            (__int64)&v109,
            (__int64)&v104,
            (__int64)&v106,
            (__int64)&v105,
            (__int64)&v108,
            (__int64)&v107);
          goto LABEL_34;
        }
        goto LABEL_113;
      }
      TermInputMgr = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v5 + 32LL))(
                       v5,
                       L"EnableFakeVCMgr",
                       &v112);
      if ( TermInputMgr < 0 && (unsigned int)dword_1801B76C8 > 3 )
      {
        LODWORD(v105) = TermInputMgr;
        v107 = "NotifySessionId";
        v108 = "Failed to get enable Fake VC Mgr property";
        v106 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v49,
          (unsigned int)&byte_180195B4F,
          v50,
          v51,
          (__int64)&v106,
          (__int64)&v108,
          (__int64)&v105,
          (__int64)&v107);
      }
      v52 = v112;
      if ( v112 )
      {
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 424LL))(v8, &v128);
        if ( TermInputMgr < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v105) = 3845;
            v107 = "Failed to Get Stack FakeVC Mgr";
            v108 = "NotifySessionId";
            v106 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
            LODWORD(v104) = TermInputMgr;
            v109 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v53,
              (unsigned int)&word_180195AFE,
              v50,
              v51,
              (__int64)&v109,
              (__int64)&v104,
              (__int64)&v106,
              (__int64)&v105,
              (__int64)&v108,
              (__int64)&v107);
            goto LABEL_34;
          }
          goto LABEL_113;
        }
        v52 = v112;
      }
      if ( !v114 || (v54 = v113) == 0 )
      {
        TermInputMgr = -2147418113;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v105) = 3851;
          v107 = "Plug-in init data not available";
          v108 = "NotifySessionId";
          v106 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          LODWORD(v104) = -2147418113;
          v109 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v114,
            (unsigned int)byte_180195AAD,
            v50,
            v51,
            (__int64)&v109,
            (__int64)&v104,
            (__int64)&v106,
            (__int64)&v105,
            (__int64)&v108,
            (__int64)&v107);
          goto LABEL_34;
        }
        goto LABEL_113;
      }
      if ( v52 )
      {
        v55 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, __int64 *))(*(_QWORD *)v128 + 24LL))(
                v128,
                "rdpgrfx",
                0,
                &v118);
        TermInputMgr = v55;
        if ( v55 < 0 )
        {
          v22 = 4428;
          snprintf_s(
            Buffer,
            0x104u,
            0x103u,
            "Connection failed, can't create internal graphics inter-process communication channel. Error code: 0x%x.",
            v55);
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_114;
          v32 = "Connection failed, can't create internal graphics inter-process communication channel.";
          LODWORD(v105) = 3860;
          v33 = (__int16 *)&dword_180195A5C;
          goto LABEL_47;
        }
      }
      else
      {
        v56 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, __int64 *))(*(_QWORD *)v114 + 24LL))(
                v114,
                "rdpgrfx",
                0,
                &v118);
        TermInputMgr = v56;
        if ( v56 < 0 )
        {
          v22 = 4428;
          snprintf_s(
            Buffer,
            0x104u,
            0x103u,
            "Connection failed, can't create internal graphics inter-process communication channel. Error code: 0x%x.",
            v56);
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_114;
          v32 = "Connection failed, can't create internal graphics inter-process communication channel.";
          LODWORD(v105) = 3869;
          v33 = (__int16 *)byte_180195A0B;
          goto LABEL_47;
        }
      }
      v57 = *(struct IUnknown **)(v34 + 128);
      if ( *(_DWORD *)(v34 + 776) )
      {
        TermInputMgr = __RDPAPIDLL__CreateInstance(v57, &CLSID_PlayBackGfxPlugin, &IID_IUMRDPGFXPlugin, &v110);
        if ( TermInputMgr < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v105) = 3898;
            v107 = "Failed to create the pipe plug-in";
            v108 = "NotifySessionId";
            v106 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
            LODWORD(v104) = TermInputMgr;
            v109 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v59,
              (unsigned int)byte_180195969,
              v60,
              v61,
              (__int64)&v109,
              (__int64)&v104,
              (__int64)&v106,
              (__int64)&v105,
              (__int64)&v108,
              (__int64)&v107);
            goto LABEL_34;
          }
          goto LABEL_113;
        }
      }
      else
      {
        v58 = __RDPAPIDLL__CreateInstance(v57, &CLSID_RdpPipeGfxPlugin, &IID_IUMRDPGFXPlugin, &v110);
        TermInputMgr = v58;
        if ( v58 < 0 )
        {
          v22 = 4429;
          snprintf_s(
            Buffer,
            0x104u,
            0x103u,
            "Connection failed, can't create graphics pipe subsystem. Error code: 0x%x.",
            v58);
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_114;
          v32 = "Connection failed, can't create graphics pipe subsystem.";
          LODWORD(v105) = 3882;
          v33 = word_1801959BA;
          goto LABEL_47;
        }
      }
      v62 = (*(__int64 (__fastcall **)(void *, __int64, __int64, __int64, __int64))(*(_QWORD *)v110 + 24LL))(
              v110,
              v118,
              v54,
              v114,
              v5);
      TermInputMgr = v62;
      if ( v62 < 0 )
      {
        v22 = 4429;
        snprintf_s(
          Buffer,
          0x104u,
          0x103u,
          "Connection failed, can't create graphics pipe subsystem. Error code: 0x%x.",
          v62);
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_114;
        v32 = "Connection failed, can't create graphics pipe subsystem.";
        LODWORD(v105) = 3902;
        v33 = (__int16 *)qword_180195918;
        goto LABEL_47;
      }
      v107 = (const char *)(v34 + 96);
      if ( *(_DWORD *)(v34 + 104) )
        PAL_System_CritSecEnter(*(_QWORD *)(v34 + 96), v63, v64);
      if ( v110 != *(void **)(v34 + 608) )
      {
        TCntPtr<IRdpSQMLogger>::SafeRelease(v34 + 608, v63, v64);
        *(_QWORD *)(v34 + 608) = v110;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(v34 + 608);
      }
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v107);
      if ( v10 )
        (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v10 + 80LL))(
          v10,
          L"Waiting for graphics subsystem");
      TermInputMgr = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v110 + 40LL))(v110);
      if ( TermInputMgr < 0 )
      {
        v137 = 0;
        v136 = 0;
        if ( (*(int (__fastcall **)(void *, __int64 *, _QWORD, _QWORD, int, __int128 *))(*(_QWORD *)v110 + 80LL))(
               v110,
               PROPERTY_TYPE_GET_CAPS_ADVERTISE_STATUS,
               0,
               0,
               1,
               &v136) >= 0
          && DWORD2(v136) == 1 )
        {
          v22 = 4427;
          snprintf_s(
            Buffer,
            0x104u,
            0x103u,
            "Connection failed, timeout reached while waiting for graphics to initialize. Error code: 0x%x.",
            TermInputMgr);
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_114;
          v32 = "Connection failed, timeout reached while waiting for graphics to initialize.";
          LODWORD(v105) = 3929;
          v33 = (__int16 *)&byte_1801958C7;
        }
        else
        {
          v22 = 4465;
          snprintf_s(
            Buffer,
            0x104u,
            0x103u,
            "Connection failed, graphics caps not received before timeout. Error code: 0x%x.",
            TermInputMgr);
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_114;
          v32 = "Connection failed, graphics caps not received before timeout.";
          LODWORD(v105) = 3935;
          v33 = &word_180195876;
        }
LABEL_47:
        v107 = v32;
        v108 = "NotifySessionId";
        v106 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v109 = "Error HResult failed";
        LODWORD(v104) = TermInputMgr;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v29,
          (_DWORD)v33,
          v30,
          v31,
          (__int64)&v109,
          (__int64)&v104,
          (__int64)&v106,
          (__int64)&v105,
          (__int64)&v108,
          (__int64)&v107);
        goto LABEL_114;
      }
      v36 = v111;
    }
    if ( v110 )
    {
      TermInputMgr = (*(__int64 (__fastcall **)(void *, _QWORD, const char *, _QWORD))(*(_QWORD *)v110 + 56LL))(
                       v110,
                       *((unsigned int *)v36 + 4),
                       v116,
                       0);
      if ( TermInputMgr < 0 && (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v105) = 3943;
        v116 = "SetSessionId failed";
        v107 = "NotifySessionId";
        v108 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        LODWORD(v104) = TermInputMgr;
        v106 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v65,
          (unsigned int)byte_180195825,
          v66,
          v67,
          (__int64)&v106,
          (__int64)&v104,
          (__int64)&v108,
          (__int64)&v105,
          (__int64)&v107,
          (__int64)&v116);
        goto LABEL_34;
      }
    }
    else
    {
      TermInputMgr = -2147418113;
    }
    goto LABEL_113;
  }
  v22 = 4469;
  LODWORD(v103) = TermInputMgr;
  if ( TermInputMgr != -2147020577 )
    v22 = 4426;
  snprintf_s(Buffer, 0x104u, 0x103u, "Connection failed, can't create Input devices. Error code: 0x%x.", v103);
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v32 = "Connection failed, can't create Input devices.";
    LODWORD(v105) = 3811;
    v33 = (__int16 *)qword_180195CC0;
    goto LABEL_47;
  }
LABEL_114:
  v68 = v129;
  CUMRDPConnection::CheckHrAndLogRCMConnectionObjectErrorEvent(v129, TermInputMgr);
  if ( TermInputMgr < 0 )
    CUMRDPConnection::SetDisconnectReasonAndLogDiagnosticsEvent(v68, v22, TermInputMgr, "NotifySessionId");
  EventActivityIdControl(2u, &ActivityId);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v117, v69, v70);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v118, v71, v72);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v110, v73, v74);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v113, v75, v76);
  v79 = v125;
  if ( v125 )
  {
    v125 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v119, v77, v78);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v126, v80, v81);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v120, v82, v83);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v121, v84, v85);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v122, v86, v87);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v123, v88, v89);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v124, v90, v91);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v127, v92, v93);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v128, v94, v95);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v114, v96, v97);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v130, v98, v99);
  TCntPtr<IRdpSQMLogger>::SafeRelease(v135, v100, v101);
  return (unsigned int)TermInputMgr;
}

```

## disassembly

```asm
0x18004e0f0  mov     [rsp-8+arg_18], rbx
0x18004e0f5  push    rbp
0x18004e0f6  push    rsi
0x18004e0f7  push    rdi
0x18004e0f8  push    r12
0x18004e0fa  push    r13
0x18004e0fc  push    r14
0x18004e0fe  push    r15
0x18004e100  lea     rbp, [rsp-230h]
0x18004e108  sub     rsp, 330h
0x18004e10f  mov     rax, cs:__security_cookie
0x18004e116  xor     rax, rsp
0x18004e119  mov     [rbp+260h+var_40], rax
0x18004e120  xor     r15d, r15d
0x18004e123  mov     [rbp+260h+var_2B0], r8
0x18004e127  mov     [rbp+260h+var_2D8], rdx
0x18004e12b  xorps   xmm0, xmm0
0x18004e12e  mov     [rsp+360h+var_310], rcx
0x18004e133  xor     eax, eax
0x18004e135  xor     edx, edx; Val
0x18004e137  mov     [rbp+260h+var_228], rax
0x18004e13b  mov     r8d, 82h; Size
0x18004e141  mov     [rbp+260h+var_2D0], r15d
0x18004e145  lea     rcx, [rbp+260h+var_220]; void *
0x18004e149  mov     [rbp+260h+var_198], r15
0x18004e150  movups  [rbp+260h+var_238], xmm0
0x18004e154  mov     [rbp+260h+var_190], r15
0x18004e15b  call    memset_0
0x18004e160  xor     edx, edx; Val
0x18004e162  lea     rcx, [rbp+260h+Buffer]; void *
0x18004e169  mov     r8d, 104h; Size
0x18004e16f  call    memset_0
0x18004e174  mov     rax, [rsp+360h+var_310]
0x18004e179  lea     rdx, [rbp+260h+ActivityId]; ActivityId
0x18004e180  mov     ebx, r15d
0x18004e183  mov     [rbp+260h+var_240], r15
0x18004e187  lea     ecx, [r15+4]; ControlCode
0x18004e18b  mov     [rbp+260h+var_2C0], r15
0x18004e18f  mov     [rbp+260h+var_250], r15
0x18004e193  mov     r13d, r15d
0x18004e196  movups  xmm0, xmmword ptr [rax+2F0h]
0x18004e19d  mov     [rbp+260h+var_258], rbx
0x18004e1a1  mov     esi, r15d
0x18004e1a4  mov     [rbp+260h+var_270], r15
0x18004e1a8  mov     r14d, r15d
0x18004e1ab  movdqu  xmmword ptr [rbp+260h+ActivityId.Data1], xmm0
0x18004e1b3  mov     [rbp+260h+var_278], r15
0x18004e1b7  mov     edi, r15d
0x18004e1ba  mov     [rbp+260h+var_280], r15
0x18004e1be  mov     r12d, r15d
0x18004e1c1  mov     [rbp+260h+var_288], r15
0x18004e1c5  mov     [rbp+260h+var_290], r15
0x18004e1c9  mov     [rbp+260h+var_260], r15
0x18004e1cd  mov     [rbp+260h+var_298], r15
0x18004e1d1  mov     [rbp+260h+var_268], r15
0x18004e1d5  mov     [rbp+260h+var_2C8], r15
0x18004e1d9  mov     [rbp+260h+var_2E0], r15
0x18004e1dd  mov     [rbp+260h+var_2A0], r15
0x18004e1e1  mov     [rbp+260h+var_2A8], r15
0x18004e1e5  call    cs:__imp_EventActivityIdControl
0x18004e1eb  mov     rax, [rsp+360h+var_310]
0x18004e1f0  lea     rcx, [rax+60h]
0x18004e1f4  mov     [rbp+260h+var_2B8], rcx
0x18004e1f8  cmp     [rcx+8], ebx
0x18004e1fb  jz      short loc_18004E20B
0x18004e1fd  mov     rcx, [rcx]
0x18004e200  call    cs:__imp_PAL_System_CritSecEnter
0x18004e206  mov     rax, [rsp+360h+var_310]
0x18004e20b  cmp     [rax+0C0h], rbx
0x18004e212  jz      short loc_18004E246
0x18004e214  lea     rcx, [rbp+260h+var_258]
0x18004e218  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ
0x18004e21d  mov     rbx, [rsp+360h+var_310]
0x18004e222  mov     rbx, [rbx+0C0h]
0x18004e229  mov     [rbp+260h+var_258], rbx
0x18004e22d  test    rbx, rbx
0x18004e230  jz      short loc_18004E241
0x18004e232  mov     rax, [rbx]
0x18004e235  mov     rcx, rbx
0x18004e238  mov     rax, [rax+8]
0x18004e23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e241  mov     rax, [rsp+360h+var_310]
0x18004e246  cmp     [rax+0A0h], rsi
0x18004e24d  jz      short loc_18004E276
0x18004e24f  lea     rcx, [rbp+260h+var_270]
0x18004e253  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ
0x18004e258  mov     rax, [rsp+360h+var_310]
0x18004e25d  lea     rcx, [rbp+260h+var_270]
0x18004e261  mov     r13, [rax+0A0h]
0x18004e268  mov     [rbp+260h+var_270], r13
0x18004e26c  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ
0x18004e271  mov     rax, [rsp+360h+var_310]
0x18004e276  cmp     [rax+0E8h], rsi
0x18004e27d  jz      short loc_18004E2A6
0x18004e27f  lea     rcx, [rbp+260h+var_278]
0x18004e283  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ
0x18004e288  mov     rax, [rsp+360h+var_310]
0x18004e28d  lea     rcx, [rbp+260h+var_278]
0x18004e291  mov     rsi, [rax+0E8h]
0x18004e298  mov     [rbp+260h+var_278], rsi
0x18004e29c  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ
0x18004e2a1  mov     rax, [rsp+360h+var_310]
0x18004e2a6  cmp     [rax+0B0h], rdi
0x18004e2ad  jz      short loc_18004E2D6
0x18004e2af  lea     rcx, [rbp+260h+var_288]
0x18004e2b3  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ
0x18004e2b8  mov     rax, [rsp+360h+var_310]
0x18004e2bd  lea     rcx, [rbp+260h+var_288]
0x18004e2c1  mov     r14, [rax+0B0h]
0x18004e2c8  mov     [rbp+260h+var_288], r14
0x18004e2cc  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ
0x18004e2d1  mov     rax, [rsp+360h+var_310]
0x18004e2d6  cmp     [rax+0F0h], rdi
0x18004e2dd  jz      short loc_18004E306
0x18004e2df  lea     rcx, [rbp+260h+var_280]
0x18004e2e3  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ
0x18004e2e8  mov     rcx, [rsp+360h+var_310]
0x18004e2ed  mov     rax, [rcx+0F0h]
0x18004e2f4  lea     rcx, [rbp+260h+var_280]
0x18004e2f8  mov     [rbp+260h+var_280], rax
0x18004e2fc  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ
0x18004e301  mov     rax, [rsp+360h+var_310]
0x18004e306  mov     rdx, [rbp+260h+var_2D8]
0x18004e30a  lea     rcx, [rax-38h]
0x18004e30e  mov     [rbp+260h+var_248], rcx
0x18004e312  mov     eax, [rdx+10h]
0x18004e315  mov     [rcx+2C8h], eax
0x18004e31b  mov     rax, [rsp+360h+var_310]
0x18004e320  cmp     [rax+240h], rdi
0x18004e327  jz      short loc_18004E350
0x18004e329  lea     rcx, [rbp+260h+var_290]
0x18004e32d  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ
0x18004e332  mov     rax, [rsp+360h+var_310]
0x18004e337  lea     rcx, [rbp+260h+var_290]
0x18004e33b  mov     rdi, [rax+240h]
0x18004e342  mov     [rbp+260h+var_290], rdi
0x18004e346  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ
0x18004e34b  mov     rax, [rsp+360h+var_310]
0x18004e350  cmp     [rax+248h], r12
0x18004e357  jz      short loc_18004E380
0x18004e359  lea     rcx, [rbp+260h+var_298]
0x18004e35d  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ
0x18004e362  mov     rax, [rsp+360h+var_310]
0x18004e367  lea     rcx, [rbp+260h+var_298]
0x18004e36b  mov     r12, [rax+248h]
0x18004e372  mov     [rbp+260h+var_298], r12
0x18004e376  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ
0x18004e37b  mov     rax, [rsp+360h+var_310]
0x18004e380  cmp     [rax+258h], r15
0x18004e387  jz      short loc_18004E3B0
0x18004e389  lea     rcx, [rbp+260h+var_2C8]
0x18004e38d  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ
0x18004e392  mov     rcx, [rsp+360h+var_310]
0x18004e397  mov     rax, [rcx+258h]
0x18004e39e  lea     rcx, [rbp+260h+var_2C8]
0x18004e3a2  mov     [rbp+260h+var_2C8], rax
0x18004e3a6  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ
0x18004e3ab  mov     rax, [rsp+360h+var_310]
0x18004e3b0  lea     rcx, [rax+260h]
0x18004e3b7  mov     rax, [rbp+260h+var_2E0]
0x18004e3bb  mov     [rsp+360h+var_308], rcx
0x18004e3c0  cmp     [rcx], rax
0x18004e3c3  jz      short loc_18004E3E3
0x18004e3c5  lea     rcx, [rbp+260h+var_2E0]
0x18004e3c9  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ
0x18004e3ce  mov     rcx, [rsp+360h+var_308]
0x18004e3d3  mov     rax, [rcx]
0x18004e3d6  lea     rcx, [rbp+260h+var_2E0]
0x18004e3da  mov     [rbp+260h+var_2E0], rax
0x18004e3de  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ
0x18004e3e3  mov     rax, [rsp+360h+var_310]
0x18004e3e8  cmp     [rax+80h], r15
0x18004e3ef  jz      short loc_18004E413
0x18004e3f1  lea     rcx, [rbp+260h+var_2A8]
0x18004e3f5  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ
0x18004e3fa  mov     rax, [rsp+360h+var_310]
0x18004e3ff  lea     rcx, [rbp+260h+var_2A8]
0x18004e403  mov     r15, [rax+80h]
0x18004e40a  mov     [rbp+260h+var_2A8], r15
0x18004e40e  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ
0x18004e413  lea     rcx, [rbp+260h+var_2B8]; this
0x18004e417  call    ??1CTSAutoLock@@QEAA@XZ
0x18004e41c  lea     rcx, aNotifysessioni
0x18004e423  test    rbx, rbx
0x18004e426  jz      loc_18004F127
0x18004e42c  test    r13, r13
0x18004e42f  jz      loc_18004F127
0x18004e435  test    rsi, rsi
0x18004e438  jz      loc_18004F127
0x18004e43e  test    rdi, rdi
0x18004e441  jz      loc_18004F127
0x18004e447  test    r14, r14
0x18004e44a  jz      loc_18004F127
0x18004e450  mov     eax, 17h
0x18004e455  lea     r8, [rbp+260h+var_238]
0x18004e459  mov     word ptr [rbp+260h+var_238], ax
0x18004e45d  lea     rdx, aSessionid
0x18004e464  mov     rax, [rbp+260h+var_2D8]
0x18004e468  mov     rcx, r13
0x18004e46b  mov     eax, [rax+10h]
0x18004e46e  mov     dword ptr [rbp+260h+var_238+8], eax
0x18004e471  mov     rax, [r13+0]
0x18004e475  mov     rax, [rax+38h]
0x18004e479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e47e  mov     esi, eax
0x18004e480  test    eax, eax
0x18004e482  jns     loc_18004E521
0x18004e488  mov     ecx, cs:dword_1801B76C8
0x18004e48e  cmp     ecx, 2
0x18004e491  jbe     loc_18004F1B2
0x18004e497  lea     rax, aFailedToSetThe_15
0x18004e49e  mov     dword ptr [rsp+360h+var_310], 0ECEh
0x18004e4a6  mov     [rbp+260h+var_2B8], rax
0x18004e4aa  lea     r14, aNotifysessioni
0x18004e4b1  lea     rax, aClientcoreTerm_12
0x18004e4b8  mov     [rbp+260h+var_2D8], r14
0x18004e4bc  mov     [rsp+360h+var_2E8], rax
0x18004e4c1  lea     rdx, word_180195DCA
0x18004e4c8  lea     rax, aErrorHresultFa
0x18004e4cf  mov     dword ptr [rsp+360h+var_308], esi
0x18004e4d3  mov     [rsp+360h+var_300], rax
0x18004e4d8  lea     rax, [rbp+260h+var_2B8]
0x18004e4dc  mov     [rsp+360h+var_318], rax
0x18004e4e1  lea     rax, [rbp+260h+var_2D8]
0x18004e4e5  mov     [rsp+360h+var_320], rax
0x18004e4ea  lea     rax, [rsp+360h+var_310]
0x18004e4ef  mov     [rsp+360h+var_328], rax
0x18004e4f4  lea     rax, [rsp+360h+var_2E8]
0x18004e4f9  mov     [rsp+360h+var_330], rax
0x18004e4fe  lea     rax, [rsp+360h+var_308]
0x18004e503  mov     [rsp+360h+var_338], rax
0x18004e508  lea     rax, [rsp+360h+var_300]
0x18004e50d  mov     [rsp+360h+var_340], rax
0x18004e512  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z
0x18004e517  mov     ebx, 114Eh
0x18004e51c  jmp     loc_18004F1BE
0x18004e521  mov     eax, cs:dword_1801B76C8
0x18004e527  cmp     eax, 4
0x18004e52a  jbe     loc_18004E5EC
0x18004e530  mov     rdx, 470000000000h
0x18004e53a  lea     rcx, dword_1801B76C8
0x18004e541  call    _tlgKeywordOn
0x18004e546  test    al, al
0x18004e548  jz      loc_18004E5EC
0x18004e54e  mov     rax, [rbp+260h+var_2D8]
0x18004e552  lea     rdx, word_180195D62
0x18004e559  mov     [rsp+360h+var_2F0], 1000000h
0x18004e562  mov     eax, [rax+10h]
0x18004e565  mov     dword ptr [rsp+360h+var_308], eax
0x18004e569  mov     rax, [rsp+360h+var_310]
0x18004e56e  movups  xmm0, xmmword ptr [rax+2F0h]
0x18004e575  lea     rax, [rbp+260h+var_180]
0x18004e57c  mov     [rsp+360h+var_300], rax
0x18004e581  lea     rax, aIwrdsprotocolc
0x18004e588  mov     [rsp+360h+var_2E8], rax
0x18004e58d  lea     rax, aStack
0x18004e594  mov     [rbp+260h+var_2B8], rax
0x18004e598  lea     rax, aCheckpoint
0x18004e59f  mov     [rsp+360h+var_2F8], rax
0x18004e5a4  lea     rax, [rsp+360h+var_308]
0x18004e5a9  mov     [rsp+360h+var_318], rax
0x18004e5ae  lea     rax, [rsp+360h+var_300]
0x18004e5b3  mov     [rsp+360h+var_320], rax
0x18004e5b8  lea     rax, [rsp+360h+var_2E8]
0x18004e5bd  mov     [rsp+360h+var_328], rax
0x18004e5c2  lea     rax, [rbp+260h+var_2B8]
0x18004e5c6  mov     [rsp+360h+var_330], rax
0x18004e5cb  lea     rax, [rsp+360h+var_2F0]
0x18004e5d0  mov     [rsp+360h+var_338], rax
0x18004e5d5  lea     rax, [rsp+360h+var_2F8]
0x18004e5da  mov     [rsp+360h+var_340], rax
0x18004e5df  movdqu  [rbp+260h+var_180], xmm0
0x18004e5e7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z
0x18004e5ec  mov     rax, [rsp+360h+var_310]
0x18004e5f1  cmp     dword ptr [rax+308h], 0
0x18004e5f8  jnz     loc_18004E798
0x18004e5fe  lea     r8, [rbp+260h+var_260]; struct IUnknown **
0x18004e602  mov     rdx, r15; struct IUnknown *
0x18004e605  mov     rcx, rdi; this
0x18004e608  call    ?GetTermInputMgr@CUMRDPProtocolManager@@QEAAJPEAUIUnknown@@PEAPEAU2@@Z
0x18004e60d  mov     esi, eax
0x18004e60f  test    eax, eax
0x18004e611  jns     loc_18004E6A5
0x18004e617  mov     eax, cs:dword_1801B76C8
0x18004e61d  cmp     eax, 2
0x18004e620  jbe     loc_18004F1B2
0x18004e626  lea     rax, aGetterminputmg_0
0x18004e62d  mov     dword ptr [rsp+360h+var_308], 0EDBh
0x18004e635  mov     [rsp+360h+var_2F8], rax
0x18004e63a  lea     r14, aNotifysessioni
0x18004e641  lea     rax, aClientcoreTerm_12
0x18004e648  mov     [rsp+360h+var_2F0], r14
0x18004e64d  mov     [rsp+360h+var_300], rax
0x18004e652  lea     rdx, byte_180195D11
0x18004e659  lea     rax, aErrorHresultFa
0x18004e660  mov     dword ptr [rsp+360h+var_310], esi
0x18004e664  mov     [rsp+360h+var_2E8], rax
0x18004e669  lea     rax, [rsp+360h+var_2F8]
0x18004e66e  mov     [rsp+360h+var_318], rax
0x18004e673  lea     rax, [rsp+360h+var_2F0]
  ... truncated ...
```
